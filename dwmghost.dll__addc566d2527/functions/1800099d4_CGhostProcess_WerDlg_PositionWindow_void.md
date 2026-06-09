# CGhostProcess::WerDlg_PositionWindow(void)

- ea: `0x1800099d4`
- end: `0x180009ce7`
- name: `?WerDlg_PositionWindow@CGhostProcess@@AEAAJXZ`
- size: `787`
- prototype: `__int64 __fastcall(CGhostProcess *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800096f0`

## callees

- `0x180001190`
- `0x1800099d4`
- `0x180009f60`
- `0x180009f70`

## import_xrefs

- `USER32!MonitorFromPoint` at `0x180009bd5`
- `USER32!MonitorFromPoint` at `0x180009bd5`
- `USER32!MonitorFromWindow` at `0x180009ab0`
- `USER32!MonitorFromWindow` at `0x180009ab0`
- `USER32!GetSystemMetrics` at `0x180009ba5`
- `USER32!GetSystemMetrics` at `0x180009bf8`
- `USER32!GetSystemMetrics` at `0x180009c05`
- `USER32!GetSystemMetrics` at `0x180009ba5`
- `USER32!GetSystemMetrics` at `0x180009bf8`
- `USER32!GetSystemMetrics` at `0x180009c05`
- `USER32!GetWindowDpiAwarenessContext` at `0x180009a5f`
- `USER32!GetWindowDpiAwarenessContext` at `0x180009a5f`
- `USER32!GetWindowLongPtrW` at `0x180009b94`
- `USER32!GetWindowLongPtrW` at `0x180009b94`
- `USER32!SetThreadDpiAwarenessContext` at `0x180009a68`
- `USER32!SetThreadDpiAwarenessContext` at `0x180009c91`
- `USER32!SetThreadDpiAwarenessContext` at `0x180009a68`
- `USER32!SetThreadDpiAwarenessContext` at `0x180009c91`
- `USER32!GetMonitorInfoW` at `0x180009ac4`
- `USER32!GetMonitorInfoW` at `0x180009be9`
- `USER32!GetMonitorInfoW` at `0x180009ac4`
- `USER32!GetMonitorInfoW` at `0x180009be9`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180009c85`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180009c85`
- `ext-ms-win-ntuser-window-l1-1-0!IsIconic` at `0x180009a9e`
- `ext-ms-win-ntuser-window-l1-1-0!IsIconic` at `0x180009a9e`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x180009c6b`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x180009c6b`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x180009a3b`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x180009a3b`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x180009a7c`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x180009b1a`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x180009a7c`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowRect` at `0x180009b1a`
- `ext-ms-win-ntuser-window-l1-1-1!LogicalToPhysicalPoint` at `0x180009b2f`
- `ext-ms-win-ntuser-window-l1-1-1!LogicalToPhysicalPoint` at `0x180009b44`
- `ext-ms-win-ntuser-window-l1-1-1!LogicalToPhysicalPoint` at `0x180009b2f`
- `ext-ms-win-ntuser-window-l1-1-1!LogicalToPhysicalPoint` at `0x180009b44`
- `ext-ms-win-ntuser-window-l1-1-1!IsWindowVisible` at `0x180009a24`
- `ext-ms-win-ntuser-window-l1-1-1!IsWindowVisible` at `0x180009a24`

## pseudocode

```c
__int64 __fastcall CGhostProcess::WerDlg_PositionWindow(CGhostProcess *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  int v3; // r15d
  HWND v4; // rcx
  HWND v5; // r14
  HWND Window; // rsi
  __int64 WindowDpiAwarenessContext; // rax
  __int64 v8; // r12
  HMONITOR v9; // rax
  int v10; // edi
  int v11; // ebx
  int v12; // edx
  int v13; // r12d
  int v14; // r13d
  HMONITOR v15; // rax
  int SystemMetrics; // esi
  int v17; // edx
  __int64 v19; // [rsp+40h] [rbp-49h]
  struct tagRECT Rect; // [rsp+50h] [rbp-39h] BYREF
  struct tagRECT v21; // [rsp+60h] [rbp-29h] BYREF
  tagMONITORINFO mi; // [rsp+70h] [rbp-19h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v3 = 0;
  Rect = 0;
  CLock::Acquire((LPCRITICAL_SECTION)((char *)this + 16));
  v4 = (HWND)*((_QWORD *)this + 16);
  if ( v4 && IsWindowVisible(v4) )
  {
    v5 = (HWND)*((_QWORD *)this + 16);
    Window = GetWindow(v5, 4u);
  }
  else
  {
    v5 = 0;
    Window = 0;
  }
  CLock::Release(v1);
  if ( Window )
  {
    WindowDpiAwarenessContext = GetWindowDpiAwarenessContext(v5);
    v8 = SetThreadDpiAwarenessContext(WindowDpiAwarenessContext);
    v19 = v8;
    if ( GetWindowRect(v5, &Rect) )
    {
      memset(&mi, 0, sizeof(mi));
      if ( IsIconic(Window) )
      {
        v9 = MonitorFromWindow(Window, 2u);
        mi.cbSize = 40;
        if ( GetMonitorInfoW(v9, &mi) )
        {
          v10 = (mi.rcWork.right - mi.rcWork.left) / 2 - (Rect.right - Rect.left) / 2;
          v11 = (mi.rcWork.bottom - mi.rcWork.top) / 2 - (Rect.bottom - Rect.top) / 2;
          goto LABEL_24;
        }
      }
      else
      {
        v21 = 0;
        if ( GetWindowRect(Window, &v21)
          && LogicalToPhysicalPoint(Window, (LPPOINT)&v21)
          && LogicalToPhysicalPoint(Window, (LPPOINT)&v21.right) )
        {
          v10 = v21.left + (v21.right - v21.left) / 2 - (Rect.right - Rect.left) / 2;
          v11 = v21.top + (v21.bottom - v21.top) / 2 - (Rect.bottom - Rect.top) / 2;
          if ( (GetWindowLongPtrW(Window, -16) & 0xC00000) != 0 )
          {
            v12 = v21.top + 2 * GetSystemMetrics(4);
            if ( v11 < v12 )
              v11 = v12;
          }
          v13 = Rect.right - Rect.left;
          v14 = Rect.bottom - Rect.top;
          v15 = MonitorFromPoint((POINT)__PAIR64__(v11, v10), 2u);
          mi.cbSize = 40;
          if ( GetMonitorInfoW(v15, &mi) )
          {
            SystemMetrics = GetSystemMetrics(5);
            v17 = GetSystemMetrics(6);
            if ( v10 >= SystemMetrics + mi.rcWork.left )
            {
              if ( v13 + v10 > mi.rcWork.right - SystemMetrics )
                v10 = mi.rcWork.right - v13 - SystemMetrics;
            }
            else
            {
              v10 = SystemMetrics + mi.rcWork.left;
            }
            if ( v11 >= v17 + mi.rcWork.top )
            {
              v8 = v19;
              if ( v11 + v14 > mi.rcWork.bottom - v17 )
                v11 = mi.rcWork.bottom - v14 - v17;
              goto LABEL_24;
            }
            v11 = v17 + mi.rcWork.top;
          }
          v8 = v19;
LABEL_24:
          if ( v10 == Rect.left && v11 == Rect.top || SetWindowPos(v5, 0, v10, v11, 0, 0, 0x215u) )
            v3 = SendMessageW(v5, CGhostMgr::s_uHangRepMsg, 7u, 0);
        }
      }
    }
    SetThreadDpiAwarenessContext(v8);
  }
  return v3 == 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x1800099d4  push    rbp
0x1800099d6  push    rbx
0x1800099d7  push    rsi
0x1800099d8  push    rdi
0x1800099d9  push    r12
0x1800099db  push    r13
0x1800099dd  push    r14
0x1800099df  push    r15
0x1800099e1  lea     rbp, [rsp-1Fh]
0x1800099e6  sub     rsp, 0A8h
0x1800099ed  mov     rax, cs:__security_cookie
0x1800099f4  xor     rax, rsp
0x1800099f7  mov     [rbp+57h+var_48], rax
0x1800099fb  lea     rbx, [rcx+10h]
0x1800099ff  mov     r14, rcx
0x180009a02  xorps   xmm0, xmm0
0x180009a05  mov     rcx, rbx; lpCriticalSection
0x180009a08  xor     r15d, r15d
0x180009a0b  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180009a0f  call    ?Acquire@CLock@@QEAAXXZ; CLock::Acquire(void)
0x180009a14  mov     rcx, [r14+80h]; hWnd
0x180009a1b  lea     r13d, [r15+4]
0x180009a1f  test    rcx, rcx
0x180009a22  jz      short loc_180009A46
0x180009a24  call    cs:__imp_IsWindowVisible
0x180009a2a  test    eax, eax
0x180009a2c  jz      short loc_180009A46
0x180009a2e  mov     r14, [r14+80h]
0x180009a35  mov     edx, r13d; uCmd
0x180009a38  mov     rcx, r14; hWnd
0x180009a3b  call    cs:__imp_GetWindow
0x180009a41  mov     rsi, rax
0x180009a44  jmp     short loc_180009A4B
0x180009a46  xor     r14d, r14d
0x180009a49  xor     esi, esi
0x180009a4b  mov     rcx, rbx; lpCriticalSection
0x180009a4e  call    ?Release@CLock@@QEAAXXZ; CLock::Release(void)
0x180009a53  test    rsi, rsi
0x180009a56  jz      loc_180009C97
0x180009a5c  mov     rcx, r14
0x180009a5f  call    cs:__imp_GetWindowDpiAwarenessContext
0x180009a65  mov     rcx, rax
0x180009a68  call    cs:__imp_SetThreadDpiAwarenessContext
0x180009a6e  lea     rdx, [rbp+57h+Rect]; lpRect
0x180009a72  mov     rcx, r14; hWnd
0x180009a75  mov     r12, rax
0x180009a78  mov     [rbp+57h+var_A0], rax
0x180009a7c  call    cs:__imp_GetWindowRect
0x180009a82  test    eax, eax
0x180009a84  jz      loc_180009C8E
0x180009a8a  xorps   xmm0, xmm0
0x180009a8d  xor     eax, eax
0x180009a8f  mov     rcx, rsi; hWnd
0x180009a92  mov     qword ptr [rbp+57h+mi.rcWork.bottom], rax
0x180009a96  movups  xmmword ptr [rbp+57h+mi.cbSize], xmm0
0x180009a9a  movups  xmmword ptr [rbp+57h+mi.rcMonitor.bottom], xmm0
0x180009a9e  call    cs:__imp_IsIconic
0x180009aa4  mov     rcx, rsi; hWnd
0x180009aa7  test    eax, eax
0x180009aa9  jz      short loc_180009B0F
0x180009aab  mov     edx, 2; dwFlags
0x180009ab0  call    cs:__imp_MonitorFromWindow
0x180009ab6  lea     rdx, [rbp+57h+mi]; lpmi
0x180009aba  mov     [rbp+57h+mi.cbSize], 28h ; '('
0x180009ac1  mov     rcx, rax; hMonitor
0x180009ac4  call    cs:__imp_GetMonitorInfoW
0x180009aca  test    eax, eax
0x180009acc  jz      loc_180009C8E
0x180009ad2  mov     eax, [rbp+57h+Rect.right]
0x180009ad5  sub     eax, [rbp+57h+Rect.left]
0x180009ad8  cdq
0x180009ad9  sub     eax, edx
0x180009adb  sar     eax, 1
0x180009add  mov     ecx, eax
0x180009adf  mov     eax, [rbp+57h+mi.rcWork.right]
0x180009ae2  sub     eax, [rbp+57h+mi.rcWork.left]
0x180009ae5  cdq
0x180009ae6  sub     eax, edx
0x180009ae8  sar     eax, 1
0x180009aea  mov     edi, eax
0x180009aec  mov     eax, [rbp+57h+Rect.bottom]
0x180009aef  sub     eax, [rbp+57h+Rect.top]
0x180009af2  sub     edi, ecx
0x180009af4  cdq
0x180009af5  sub     eax, edx
0x180009af7  sar     eax, 1
0x180009af9  mov     ecx, eax
0x180009afb  mov     eax, [rbp+57h+mi.rcWork.bottom]
0x180009afe  sub     eax, [rbp+57h+mi.rcWork.top]
0x180009b01  cdq
0x180009b02  sub     eax, edx
0x180009b04  sar     eax, 1
0x180009b06  mov     ebx, eax
0x180009b08  sub     ebx, ecx
0x180009b0a  jmp     loc_180009C44
0x180009b0f  xorps   xmm0, xmm0
0x180009b12  lea     rdx, [rbp+57h+var_80]; lpRect
0x180009b16  movups  xmmword ptr [rbp+57h+var_80.left], xmm0
0x180009b1a  call    cs:__imp_GetWindowRect
0x180009b20  test    eax, eax
0x180009b22  jz      loc_180009C8E
0x180009b28  lea     rdx, [rbp+57h+var_80]; lpPoint
0x180009b2c  mov     rcx, rsi; hWnd
0x180009b2f  call    cs:__imp_LogicalToPhysicalPoint
0x180009b35  test    eax, eax
0x180009b37  jz      loc_180009C8E
0x180009b3d  lea     rdx, [rbp+57h+var_80.right]; lpPoint
0x180009b41  mov     rcx, rsi; hWnd
0x180009b44  call    cs:__imp_LogicalToPhysicalPoint
0x180009b4a  test    eax, eax
0x180009b4c  jz      loc_180009C8E
0x180009b52  mov     eax, [rbp+57h+var_80.right]
0x180009b55  mov     rcx, rsi; hWnd
0x180009b58  sub     eax, [rbp+57h+var_80.left]
0x180009b5b  cdq
0x180009b5c  sub     eax, edx
0x180009b5e  sar     eax, 1
0x180009b60  mov     edi, eax
0x180009b62  mov     eax, [rbp+57h+Rect.right]
0x180009b65  sub     eax, [rbp+57h+Rect.left]
0x180009b68  cdq
0x180009b69  sub     eax, edx
0x180009b6b  sar     eax, 1
0x180009b6d  sub     edi, eax
0x180009b6f  mov     eax, [rbp+57h+var_80.bottom]
0x180009b72  sub     eax, [rbp+57h+var_80.top]
0x180009b75  add     edi, [rbp+57h+var_80.left]
0x180009b78  cdq
0x180009b79  sub     eax, edx
0x180009b7b  sar     eax, 1
0x180009b7d  mov     ebx, eax
0x180009b7f  mov     eax, [rbp+57h+Rect.bottom]
0x180009b82  sub     eax, [rbp+57h+Rect.top]
0x180009b85  cdq
0x180009b86  sub     eax, edx
0x180009b88  mov     edx, 0FFFFFFF0h; nIndex
0x180009b8d  sar     eax, 1
0x180009b8f  sub     ebx, eax
0x180009b91  add     ebx, [rbp+57h+var_80.top]
0x180009b94  call    cs:__imp_GetWindowLongPtrW
0x180009b9a  test    rax, 0C00000h
0x180009ba0  jz      short loc_180009BB6
0x180009ba2  mov     ecx, r13d; nIndex
0x180009ba5  call    cs:__imp_GetSystemMetrics
0x180009bab  mov     ecx, [rbp+57h+var_80.top]
0x180009bae  lea     edx, [rcx+rax*2]
0x180009bb1  cmp     ebx, edx
0x180009bb3  cmovl   ebx, edx
0x180009bb6  mov     r12d, [rbp+57h+Rect.right]
0x180009bba  mov     edx, 2; dwFlags
0x180009bbf  mov     r13d, [rbp+57h+Rect.bottom]
0x180009bc3  sub     r12d, [rbp+57h+Rect.left]
0x180009bc7  sub     r13d, [rbp+57h+Rect.top]
0x180009bcb  mov     [rbp+57h+pt.x], edi
0x180009bce  mov     [rbp+57h+pt.y], ebx
0x180009bd1  mov     rcx, qword ptr [rbp+57h+pt.x]; pt
0x180009bd5  call    cs:__imp_MonitorFromPoint
0x180009bdb  lea     rdx, [rbp+57h+mi]; lpmi
0x180009bdf  mov     [rbp+57h+mi.cbSize], 28h ; '('
0x180009be6  mov     rcx, rax; hMonitor
0x180009be9  call    cs:__imp_GetMonitorInfoW
0x180009bef  test    eax, eax
0x180009bf1  jz      short loc_180009C40
0x180009bf3  mov     ecx, 5; nIndex
0x180009bf8  call    cs:__imp_GetSystemMetrics
0x180009bfe  mov     ecx, 6; nIndex
0x180009c03  mov     esi, eax
0x180009c05  call    cs:__imp_GetSystemMetrics
0x180009c0b  mov     edx, eax
0x180009c0d  mov     eax, [rbp+57h+mi.rcWork.left]
0x180009c10  add     eax, esi
0x180009c12  cmp     edi, eax
0x180009c14  jge     short loc_180009C1A
0x180009c16  mov     edi, eax
0x180009c18  jmp     short loc_180009C31
0x180009c1a  mov     ecx, [rbp+57h+mi.rcWork.right]
0x180009c1d  lea     r8d, [r12+rdi]
0x180009c21  mov     eax, ecx
0x180009c23  sub     eax, esi
0x180009c25  cmp     r8d, eax
0x180009c28  jle     short loc_180009C31
0x180009c2a  sub     ecx, r8d
0x180009c2d  sub     ecx, esi
0x180009c2f  add     edi, ecx
0x180009c31  mov     ecx, [rbp+57h+mi.rcWork.top]
0x180009c34  add     ecx, edx
0x180009c36  cmp     ebx, ecx
0x180009c38  jge     loc_180009CC3
0x180009c3e  mov     ebx, ecx
0x180009c40  mov     r12, [rbp+57h+var_A0]
0x180009c44  cmp     edi, [rbp+57h+Rect.left]
0x180009c47  jnz     short loc_180009C4E
0x180009c49  cmp     ebx, [rbp+57h+Rect.top]
0x180009c4c  jz      short loc_180009C75
0x180009c4e  mov     [rsp+0E0h+uFlags], 215h; uFlags
0x180009c56  mov     r9d, ebx; Y
0x180009c59  mov     [rsp+0E0h+cy], r15d; cy
0x180009c5e  mov     r8d, edi; X
0x180009c61  xor     edx, edx; hWndInsertAfter
0x180009c63  mov     [rsp+0E0h+var_C0], r15d; cx
0x180009c68  mov     rcx, r14; hWnd
0x180009c6b  call    cs:__imp_SetWindowPos
0x180009c71  test    eax, eax
0x180009c73  jz      short loc_180009C8E
0x180009c75  mov     edx, cs:?s_uHangRepMsg@CGhostMgr@@2IA; Msg
0x180009c7b  xor     r9d, r9d; lParam
0x180009c7e  mov     rcx, r14; hWnd
0x180009c81  lea     r8d, [r9+7]; wParam
0x180009c85  call    cs:__imp_SendMessageW
0x180009c8b  mov     r15, rax
0x180009c8e  mov     rcx, r12
0x180009c91  call    cs:__imp_SetThreadDpiAwarenessContext
0x180009c97  neg     r15d
0x180009c9a  sbb     eax, eax
0x180009c9c  not     eax
0x180009c9e  and     eax, 80004005h
0x180009ca3  mov     rcx, [rbp+57h+var_48]
0x180009ca7  xor     rcx, rsp; StackCookie
0x180009caa  call    __security_check_cookie
0x180009caf  add     rsp, 0A8h
0x180009cb6  pop     r15
0x180009cb8  pop     r14
0x180009cba  pop     r13
0x180009cbc  pop     r12
0x180009cbe  pop     rdi
0x180009cbf  pop     rsi
0x180009cc0  pop     rbx
0x180009cc1  pop     rbp
0x180009cc2  retn
0x180009cc3  mov     ecx, [rbp+57h+mi.rcWork.bottom]
0x180009cc6  lea     r8d, [rbx+r13]
0x180009cca  mov     r12, [rbp+57h+var_A0]
0x180009cce  mov     eax, ecx
0x180009cd0  sub     eax, edx
0x180009cd2  cmp     r8d, eax
0x180009cd5  jle     loc_180009C44
0x180009cdb  sub     ecx, r8d
0x180009cde  sub     ecx, edx
0x180009ce0  add     ebx, ecx
0x180009ce2  jmp     loc_180009C44
```
