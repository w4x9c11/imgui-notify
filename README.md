# imgui-notify
imGui Component Notification

# main 引入代码
```c++
#include "notify.h"
#include "tahoma.h"
#include "ctime"
#include "fstream"

// 设置字体 (必须)
void init()
{
    ImGuiIO* io = &ImGui::GetIO();
    ImFontConfig font_cfg;
    font_cfg.FontDataOwnedByAtlas = false;
    io->Fonts->AddFontFromMemoryTTF((void*)tahoma, sizeof(tahoma), 17.f, &font_cfg);
    ImGui::MergeIconsWithLatestFont(16.f, false);
}

// 通知示例代码
void render()
{
    ImGui::Begin("Hello World!", NULL, NULL);
        if (ImGui::Button("None"))
        {
            ImGui::InsertNotification({ ImGuiToastType_None, 3000, "Hello World:)" });
        }
        ImGui::SameLine();
        if (ImGui::Button("Success"))
        {
            ImGui::InsertNotification({ ImGuiToastType_Success, 3000, "Hello World! This is a success! %s", "We can also format here:)" });
        }
        ImGui::SameLine();
        if (ImGui::Button("Warning"))
        {
            ImGui::InsertNotification({ ImGuiToastType_Warning, 3000, "Hello World! This is a warning!" });
        }
        ImGui::SameLine();
        if (ImGui::Button("Error"))
        {
            ImGui::InsertNotification({ ImGuiToastType_Error, 3000, "Hello World! This is an error!" });
        }
        ImGui::SameLine();
        if (ImGui::Button("Info"))
        {
            ImGui::InsertNotification({ ImGuiToastType_Info, 3000, "Hello World! This is an info!" });
        }
        ImGui::SameLine();
        if (ImGui::Button("Info Long"))
        {
            ImGui::InsertNotification({ ImGuiToastType_Info, 3000, "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation" });
        }
    ImGui::End();

    ImGui::PushStyleVar(ImGuiStyleVar_WindowRounding, 5.f);
    ImGui::PushStyleColor(ImGuiCol_WindowBg, ImVec4(43.f / 255.f, 43.f / 255.f, 43.f / 255.f, 100.f / 255.f));
    ImGui::RenderNotifications();
    ImGui::PopStyleVar(1);
    ImGui::PopStyleColor(1);
}

// Main Code
init();

// Main Loop
render();
```

# 示例 视频
product_video: 'https://www.bilibili.com/video/BV1eBU8YuEqX'
