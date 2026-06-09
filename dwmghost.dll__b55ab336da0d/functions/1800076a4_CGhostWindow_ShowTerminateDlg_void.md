# CGhostWindow::ShowTerminateDlg(void)

- ea: `0x1800076a4`
- end: `0x180007742`
- name: `?ShowTerminateDlg@CGhostWindow@@AEAAJXZ`
- size: `158`
- prototype: `__int64 __fastcall(LPARAM dwInitParam)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800075e0`

## callees

- `0x1800076a4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800076d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800076d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076fe`
- `USER32!CreateDialogParamW` at `0x1800076ef`
- `USER32!CreateDialogParamW` at `0x1800076ef`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800076c3`
- `USER32!SetThreadDpiAwarenessContext` at `0x180007716`
- `USER32!SetThreadDpiAwarenessContext` at `0x1800076c3`
- `USER32!SetThreadDpiAwarenessContext` at `0x180007716`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x18000772a`
- `ext-ms-win-ntuser-window-l1-1-0!ShowWindow` at `0x18000772a`

## pseudocode

```c
__int64 __fastcall CGhostWindow::ShowTerminateDlg(LPARAM dwInitParam)
{
  unsigned int v2; // edi
  __int64 v3; // rax
  HWND v4; // rbx
  __int64 v5; // rbp
  HMODULE ModuleHandleW; // rax
  HWND DialogParamW; // rax
  signed int LastError; // eax
  HWND v9; // rcx

  v2 = -2147467259;
  if ( !*(_QWORD *)(dwInitParam + 64) )
  {
    v3 = SetThreadDpiAwarenessContext(-4);
    v4 = *(HWND *)(dwInitParam + 48);
    v5 = v3;
    ModuleHandleW = GetModuleHandleW(0);
    DialogParamW = CreateDialogParamW(ModuleHandleW, (LPCWSTR)0x3E8, v4, CGhostWindow::s_TerminateDlgProc, dwInitParam);
    *(_QWORD *)(dwInitParam + 64) = DialogParamW;
    if ( !DialogParamW )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
    SetThreadDpiAwarenessContext(v5);
  }
  v9 = *(HWND *)(dwInitParam + 64);
  if ( v9 && ShowWindow(v9, 5) )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x1800076a4  push    rbx
0x1800076a6  push    rbp
0x1800076a7  push    rsi
0x1800076a8  push    rdi
0x1800076a9  sub     rsp, 38h
0x1800076ad  cmp     qword ptr [rcx+40h], 0
0x1800076b2  mov     rsi, rcx
0x1800076b5  mov     edi, 80004005h
0x1800076ba  jnz     short loc_18000771C
0x1800076bc  mov     rcx, 0FFFFFFFFFFFFFFFCh
0x1800076c3  call    cs:__imp_SetThreadDpiAwarenessContext
0x1800076c9  mov     rbx, [rsi+30h]
0x1800076cd  xor     ecx, ecx; lpModuleName
0x1800076cf  mov     rbp, rax
0x1800076d2  call    cs:__imp_GetModuleHandleW
0x1800076d8  lea     r9, ?s_TerminateDlgProc@CGhostWindow@@CA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x1800076df  mov     [rsp+58h+dwInitParam], rsi; dwInitParam
0x1800076e4  mov     rcx, rax; hInstance
0x1800076e7  mov     r8, rbx; hWndParent
0x1800076ea  mov     edx, 3E8h; lpTemplateName
0x1800076ef  call    cs:__imp_CreateDialogParamW
0x1800076f5  mov     [rsi+40h], rax
0x1800076f9  test    rax, rax
0x1800076fc  jnz     short loc_180007713
0x1800076fe  call    cs:__imp_GetLastError
0x180007704  mov     edi, eax
0x180007706  test    eax, eax
0x180007708  jle     short loc_180007713
0x18000770a  movzx   edi, ax
0x18000770d  or      edi, 80070000h
0x180007713  mov     rcx, rbp
0x180007716  call    cs:__imp_SetThreadDpiAwarenessContext
0x18000771c  mov     rcx, [rsi+40h]; hWnd
0x180007720  test    rcx, rcx
0x180007723  jz      short loc_180007737
0x180007725  mov     edx, 5; nCmdShow
0x18000772a  call    cs:__imp_ShowWindow
0x180007730  xor     ecx, ecx
0x180007732  test    eax, eax
0x180007734  cmovnz  edi, ecx
0x180007737  mov     eax, edi
0x180007739  add     rsp, 38h
0x18000773d  pop     rdi
0x18000773e  pop     rsi
0x18000773f  pop     rbp
0x180007740  pop     rbx
0x180007741  retn
```
