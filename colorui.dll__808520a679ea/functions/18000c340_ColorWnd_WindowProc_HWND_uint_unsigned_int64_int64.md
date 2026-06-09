# ColorWnd::WindowProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18000c340`
- end: `0x18000c404`
- name: `?WindowProc@ColorWnd@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `196`
- prototype: `LRESULT __fastcall(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c340`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x18000c378`
- `KERNEL32!ReleaseMutex` at `0x18000c378`
- `KERNEL32!CloseHandle` at `0x18000c385`
- `KERNEL32!CloseHandle` at `0x18000c385`
- `USER32!OpenIcon` at `0x18000c3a1`
- `USER32!OpenIcon` at `0x18000c3a1`
- `USER32!CallWindowProcW` at `0x18000c3f5`
- `USER32!CallWindowProcW` at `0x18000c3f5`
- `USER32!SetWindowPos` at `0x18000c3d3`
- `USER32!SetWindowPos` at `0x18000c3d3`
- `USER32!ChangeWindowMessageFilterEx` at `0x18000c36b`
- `USER32!ChangeWindowMessageFilterEx` at `0x18000c36b`
- `USER32!SetForegroundWindow` at `0x18000c3aa`
- `USER32!SetForegroundWindow` at `0x18000c3aa`

## pseudocode

```c
LRESULT __fastcall ColorWnd::WindowProc(HWND hWnd, UINT Msg, WPARAM wParam, LPARAM lParam)
{
  if ( g_hStartupMutex )
  {
    ChangeWindowMessageFilterEx(hWnd, g_uMsgActivateColorCpl, 1u, 0);
    ReleaseMutex(g_hStartupMutex);
    CloseHandle(g_hStartupMutex);
    g_hStartupMutex = 0;
  }
  if ( g_uMsgActivateColorCpl != Msg )
    return CallWindowProcW(ColorWnd::m_pfnWndProc, hWnd, Msg, wParam, lParam);
  OpenIcon(hWnd);
  SetForegroundWindow(hWnd);
  SetWindowPos(hWnd, 0, 0, 0, 0, 0, 3u);
  return 1;
}

```

## disassembly

```asm
0x18000c340  push    rbx
0x18000c342  push    rbp
0x18000c343  push    rsi
0x18000c344  push    rdi
0x18000c345  sub     rsp, 48h
0x18000c349  cmp     cs:?g_hStartupMutex@@3PEAXEA, 0; void * g_hStartupMutex
0x18000c351  mov     rsi, r9
0x18000c354  mov     rbp, r8
0x18000c357  mov     edi, edx
0x18000c359  mov     rbx, rcx
0x18000c35c  jz      short loc_18000C396
0x18000c35e  mov     edx, cs:?g_uMsgActivateColorCpl@@3IA; message
0x18000c364  xor     r9d, r9d; pChangeFilterStruct
0x18000c367  lea     r8d, [r9+1]; action
0x18000c36b  call    cs:__imp_ChangeWindowMessageFilterEx
0x18000c371  mov     rcx, cs:?g_hStartupMutex@@3PEAXEA; hMutex
0x18000c378  call    cs:__imp_ReleaseMutex
0x18000c37e  mov     rcx, cs:?g_hStartupMutex@@3PEAXEA; hObject
0x18000c385  call    cs:__imp_CloseHandle
0x18000c38b  mov     cs:?g_hStartupMutex@@3PEAXEA, 0; void * g_hStartupMutex
0x18000c396  cmp     cs:?g_uMsgActivateColorCpl@@3IA, edi; uint g_uMsgActivateColorCpl
0x18000c39c  jnz     short loc_18000C3E0
0x18000c39e  mov     rcx, rbx; hWnd
0x18000c3a1  call    cs:__imp_OpenIcon
0x18000c3a7  mov     rcx, rbx; hWnd
0x18000c3aa  call    cs:__imp_SetForegroundWindow
0x18000c3b0  mov     [rsp+68h+uFlags], 3; uFlags
0x18000c3b8  xor     r9d, r9d; Y
0x18000c3bb  mov     [rsp+68h+cy], 0; cy
0x18000c3c3  xor     r8d, r8d; X
0x18000c3c6  xor     edx, edx; hWndInsertAfter
0x18000c3c8  mov     dword ptr [rsp+68h+lParam], 0; cx
0x18000c3d0  mov     rcx, rbx; hWnd
0x18000c3d3  call    cs:__imp_SetWindowPos
0x18000c3d9  mov     eax, 1
0x18000c3de  jmp     short loc_18000C3FB
0x18000c3e0  mov     rcx, cs:?m_pfnWndProc@ColorWnd@@0P6A_JPEAUHWND__@@I_K_J@ZEA; lpPrevWndFunc
0x18000c3e7  mov     r9, rbp; wParam
0x18000c3ea  mov     r8d, edi; Msg
0x18000c3ed  mov     [rsp+68h+lParam], rsi; lParam
0x18000c3f2  mov     rdx, rbx; hWnd
0x18000c3f5  call    cs:__imp_CallWindowProcW
0x18000c3fb  add     rsp, 48h
0x18000c3ff  pop     rdi
0x18000c400  pop     rsi
0x18000c401  pop     rbp
0x18000c402  pop     rbx
0x18000c403  retn
```
