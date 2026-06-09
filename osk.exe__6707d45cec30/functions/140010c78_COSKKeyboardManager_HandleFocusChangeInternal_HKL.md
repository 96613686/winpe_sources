# COSKKeyboardManager::HandleFocusChangeInternal(HKL__ *)

- ea: `0x140010c78`
- end: `0x140010e0a`
- name: `?HandleFocusChangeInternal@COSKKeyboardManager@@AEAAXPEAUHKL__@@@Z`
- size: `402`
- prototype: `void(COSKKeyboardManager *__hidden this, HKL)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140010c54`

## callees

- `0x140002de3`
- `0x140010c78`
- `0x140011f04`
- `0x140012b80`
- `0x14001a018`
- `0x14001abf8`
- `0x140025d42`
- `0x140025d70`

## import_xrefs

- `USER32!GetGUIThreadInfo` at `0x140010d06`
- `USER32!GetGUIThreadInfo` at `0x140010d06`
- `USER32!KillTimer` at `0x140010cbe`
- `USER32!KillTimer` at `0x140010cbe`
- `USER32!GetClassNameW` at `0x140010d2b`
- `USER32!GetClassNameW` at `0x140010d2b`
- `USER32!GetForegroundWindow` at `0x140010cc4`
- `USER32!GetForegroundWindow` at `0x140010db2`
- `USER32!GetForegroundWindow` at `0x140010cc4`
- `USER32!GetForegroundWindow` at `0x140010db2`
- `USER32!GetKeyboardLayout` at `0x140010d67`
- `USER32!GetKeyboardLayout` at `0x140010d67`
- `USER32!GetWindowThreadProcessId` at `0x140010d5b`
- `USER32!GetWindowThreadProcessId` at `0x140010d5b`
- `USER32!GetPropW` at `0x140010dc7`
- `USER32!GetPropW` at `0x140010dc7`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140010cad`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x140010cad`

## pseudocode

```c
void __fastcall COSKKeyboardManager::HandleFocusChangeInternal(COSKKeyboardManager *this, HKL KeyboardLayout)
{
  COSKKeyboardManager *v2; // rdi
  HWND HWND; // rbx
  DWORD WindowThreadProcessId; // eax
  COSKPredictionManager *v6; // rcx
  HWND ForegroundWindow; // rax
  tagGUITHREADINFO pgui; // [rsp+20h] [rbp-E8h] BYREF
  WCHAR ClassName[64]; // [rsp+70h] [rbp-98h] BYREF

  v2 = COSKKeyboardManager::s_pCOSKKeyboardManager;
  HWND = DirectUI::NativeHWNDHost::GetHWND(*((DirectUI::NativeHWNDHost **)COSKKeyboardManager::s_pCOSKKeyboardManager
                                           + 16));
  KillTimer(HWND, 0x7D3u);
  if ( HWND != GetForegroundWindow() && !*((_BYTE *)v2 + 220) )
  {
    *((_BYTE *)v2 + 220) = 1;
    memset_0(&pgui, 0, sizeof(pgui));
    pgui.cbSize = 72;
    if ( GetGUIThreadInfo(0, &pgui) && pgui.hwndFocus )
    {
      if ( GetClassNameW(pgui.hwndFocus, ClassName, 64) <= 0
        || (ClassName[63] = 0, wcscmp_0(ClassName, L"ConsoleWindowClass")) )
      {
        WindowThreadProcessId = GetWindowThreadProcessId(pgui.hwndFocus, 0);
        if ( WindowThreadProcessId )
          KeyboardLayout = GetKeyboardLayout(WindowThreadProcessId);
      }
      if ( KeyboardLayout )
      {
        if ( *((HKL *)v2 + 18) != KeyboardLayout )
        {
          *((_QWORD *)v2 + 18) = KeyboardLayout;
          COSKKeyboardManager::RefreshKeyboards(v2);
          COSKKeyboardManager::InitializeScanModeData(v2);
          v6 = (COSKPredictionManager *)*((_QWORD *)v2 + 29);
          if ( v6 )
            COSKPredictionManager::UpdateHKL(v6, KeyboardLayout);
        }
      }
    }
    if ( *((_BYTE *)v2 + 223) )
    {
      ForegroundWindow = GetForegroundWindow();
      if ( !ForegroundWindow || !GetPropW(ForegroundWindow, L"StartMenuTag") )
        COSKPredictionManager::HandleFocusChange(*((COSKPredictionManager **)v2 + 29));
    }
    *((_BYTE *)v2 + 220) = 0;
  }
}

```

## disassembly

```asm
0x140010c78  mov     [rsp+arg_0], rbx
0x140010c7d  mov     [rsp+arg_8], rsi
0x140010c82  push    rdi
0x140010c83  sub     rsp, 100h
0x140010c8a  mov     rax, cs:__security_cookie
0x140010c91  xor     rax, rsp
0x140010c94  mov     [rsp+108h+var_18], rax
0x140010c9c  mov     rdi, cs:?s_pCOSKKeyboardManager@COSKKeyboardManager@@0PEAV1@EA; COSKKeyboardManager * COSKKeyboardManager::s_pCOSKKeyboardManager
0x140010ca3  mov     rsi, rdx
0x140010ca6  mov     rcx, [rdi+80h]
0x140010cad  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x140010cb3  mov     rcx, rax; hWnd
0x140010cb6  mov     edx, 7D3h; uIDEvent
0x140010cbb  mov     rbx, rax
0x140010cbe  call    cs:__imp_KillTimer
0x140010cc4  call    cs:__imp_GetForegroundWindow
0x140010cca  cmp     rbx, rax
0x140010ccd  jz      loc_140010DE5
0x140010cd3  cmp     byte ptr [rdi+0DCh], 0
0x140010cda  jnz     loc_140010DE5
0x140010ce0  mov     ebx, 48h ; 'H'
0x140010ce5  mov     byte ptr [rdi+0DCh], 1
0x140010cec  mov     r8d, ebx; Size
0x140010cef  lea     rcx, [rsp+108h+pgui]; void *
0x140010cf4  xor     edx, edx; Val
0x140010cf6  call    memset_0
0x140010cfb  lea     rdx, [rsp+108h+pgui]; pgui
0x140010d00  mov     [rsp+108h+pgui.cbSize], ebx
0x140010d04  xor     ecx, ecx; idThread
0x140010d06  call    cs:__imp_GetGUIThreadInfo
0x140010d0c  test    eax, eax
0x140010d0e  jz      loc_140010DA9
0x140010d14  mov     rcx, [rsp+108h+pgui.hwndFocus]; hWnd
0x140010d19  test    rcx, rcx
0x140010d1c  jz      loc_140010DA9
0x140010d22  lea     r8d, [rbx-8]; nMaxCount
0x140010d26  lea     rdx, [rsp+108h+ClassName]; lpClassName
0x140010d2b  call    cs:__imp_GetClassNameW
0x140010d31  test    eax, eax
0x140010d33  jle     short loc_140010D54
0x140010d35  xor     eax, eax
0x140010d37  lea     rdx, aConsolewindowc; "ConsoleWindowClass"
0x140010d3e  lea     rcx, [rsp+108h+ClassName]; String1
0x140010d43  mov     [rsp+108h+var_1A], ax
0x140010d4b  call    wcscmp_0
0x140010d50  test    eax, eax
0x140010d52  jz      short loc_140010D70
0x140010d54  mov     rcx, [rsp+108h+pgui.hwndFocus]; hWnd
0x140010d59  xor     edx, edx; lpdwProcessId
0x140010d5b  call    cs:__imp_GetWindowThreadProcessId
0x140010d61  test    eax, eax
0x140010d63  jz      short loc_140010D70
0x140010d65  mov     ecx, eax; idThread
0x140010d67  call    cs:__imp_GetKeyboardLayout
0x140010d6d  mov     rsi, rax
0x140010d70  test    rsi, rsi
0x140010d73  jz      short loc_140010DA9
0x140010d75  cmp     [rdi+90h], rsi
0x140010d7c  jz      short loc_140010DA9
0x140010d7e  mov     rcx, rdi; this
0x140010d81  mov     [rdi+90h], rsi
0x140010d88  call    ?RefreshKeyboards@COSKKeyboardManager@@AEAAXXZ; COSKKeyboardManager::RefreshKeyboards(void)
0x140010d8d  mov     rcx, rdi; this
0x140010d90  call    ?InitializeScanModeData@COSKKeyboardManager@@AEAAJXZ; COSKKeyboardManager::InitializeScanModeData(void)
0x140010d95  mov     rcx, [rdi+0E8h]; this
0x140010d9c  test    rcx, rcx
0x140010d9f  jz      short loc_140010DA9
0x140010da1  mov     rdx, rsi; HKL
0x140010da4  call    ?UpdateHKL@COSKPredictionManager@@QEAAXPEAUHKL__@@@Z; COSKPredictionManager::UpdateHKL(HKL__ *)
0x140010da9  cmp     byte ptr [rdi+0DFh], 0
0x140010db0  jz      short loc_140010DDE
0x140010db2  call    cs:__imp_GetForegroundWindow
0x140010db8  test    rax, rax
0x140010dbb  jz      short loc_140010DD2
0x140010dbd  lea     rdx, String; "StartMenuTag"
0x140010dc4  mov     rcx, rax; hWnd
0x140010dc7  call    cs:__imp_GetPropW
0x140010dcd  test    rax, rax
0x140010dd0  jnz     short loc_140010DDE
0x140010dd2  mov     rcx, [rdi+0E8h]; this
0x140010dd9  call    ?HandleFocusChange@COSKPredictionManager@@QEAAXXZ; COSKPredictionManager::HandleFocusChange(void)
0x140010dde  mov     byte ptr [rdi+0DCh], 0
0x140010de5  mov     rcx, [rsp+108h+var_18]
0x140010ded  xor     rcx, rsp; StackCookie
0x140010df0  call    __security_check_cookie
0x140010df5  lea     r11, [rsp+108h+var_8]
0x140010dfd  mov     rbx, [r11+10h]
0x140010e01  mov     rsi, [r11+18h]
0x140010e05  mov     rsp, r11
0x140010e08  pop     rdi
0x140010e09  retn
```
