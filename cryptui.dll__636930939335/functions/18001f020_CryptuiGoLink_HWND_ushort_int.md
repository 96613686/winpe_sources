# CryptuiGoLink(HWND__ *,ushort *,int)

- ea: `0x18001f020`
- end: `0x18001f21f`
- name: `?CryptuiGoLink@@YAXPEAUHWND__@@PEAGH@Z`
- size: `511`
- prototype: `void __fastcall(HWND hwnd, LPCWSTR lpFile, UINT wRemoveMsg)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007e20`
- `0x180007f18`
- `0x180012250`

## callees

- `0x1800050ac`
- `0x18001f020`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f108`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001f108`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f1c7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f1e2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f1c7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001f1e2`
- `USER32!SetWindowPos` at `0x18001f071`
- `USER32!SetWindowPos` at `0x18001f071`
- `USER32!LoadCursorA` at `0x18001f07e`
- `USER32!LoadCursorA` at `0x18001f07e`
- `USER32!PeekMessageA` at `0x18001f0f8`
- `USER32!PeekMessageA` at `0x18001f0f8`
- `USER32!SetCursor` at `0x18001f087`
- `USER32!SetCursor` at `0x18001f1d0`
- `USER32!SetCursor` at `0x18001f1ff`
- `USER32!SetCursor` at `0x18001f087`
- `USER32!SetCursor` at `0x18001f1d0`
- `USER32!SetCursor` at `0x18001f1ff`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001f190`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001f1ef`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001f190`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001f1ef`
- `ole32!CoInitialize` at `0x18001f0bc`
- `ole32!CoInitialize` at `0x18001f0bc`
- `ole32!CreateBindCtx` at `0x18001f138`
- `ole32!CreateBindCtx` at `0x18001f138`
- `SHELL32!ShellExecuteW` at `0x18001f1b9`
- `SHELL32!ShellExecuteW` at `0x18001f1b9`

## string_xrefs

- `0x18001f095`: `urlmon.dll`
- `0x18001f0fe`: `HlinkSimpleNavigateToString`

## pseudocode

```c
void __fastcall CryptuiGoLink(HWND hwnd, LPCWSTR lpFile, UINT wRemoveMsg)
{
  HCURSOR CursorA; // rax
  HCURSOR v7; // r14
  HMODULE LibraryW; // rbx
  FARPROC ProcAddress; // rdi
  tagMSG Msg; // [rsp+68h] [rbp-50h] BYREF
  LPBC ppbc; // [rsp+D8h] [rbp+20h] BYREF

  SetWindowPos(hwnd, (HWND)0xFFFFFFFFFFFFFFFELL, 0, 0, 0, 0, 3u);
  CursorA = LoadCursorA(0, (LPCSTR)0x7F02);
  v7 = SetCursor(CursorA);
  LibraryW = (HMODULE)IsolationAwareLoadLibraryW(L"urlmon.dll");
  if ( !LibraryW || wRemoveMsg )
  {
    ShellExecuteW(hwnd, L"open", lpFile, 0, 0, 1);
  }
  else if ( CoInitialize(0) >= 0 )
  {
    memset(&Msg, 0, sizeof(Msg));
    PeekMessageA(&Msg, 0, 0, 0, 0);
    ProcAddress = GetProcAddress(LibraryW, "HlinkSimpleNavigateToString");
    if ( ProcAddress )
    {
      ppbc = 0;
      CreateBindCtx(0, &ppbc);
      ((void (__fastcall *)(LPCWSTR, _QWORD, _QWORD, _QWORD, LPBC, _QWORD, int, _DWORD))ProcAddress)(
        lpFile,
        0,
        0,
        0,
        ppbc,
        0,
        2,
        0);
      if ( ppbc )
        ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    }
    CoUninitialize();
  }
  if ( LibraryW )
    FreeLibrary(LibraryW);
  SetCursor(v7);
}

```

## disassembly

```asm
0x18001f020  mov     rax, rsp
0x18001f023  mov     [rax+8], rbx
0x18001f027  mov     [rax+10h], rsi
0x18001f02b  push    rdi
0x18001f02c  push    r14
0x18001f02e  push    r15
0x18001f030  sub     rsp, 0A0h
0x18001f037  mov     edi, r8d
0x18001f03a  mov     r15, rdx
0x18001f03d  mov     rsi, rcx
0x18001f040  mov     qword ptr [rax-60h], 0
0x18001f048  mov     dword ptr [rax-68h], 0
0x18001f04f  mov     [rsp+0B8h+uFlags], 3; uFlags
0x18001f057  mov     [rsp+0B8h+cy], 0; cy
0x18001f05f  mov     [rsp+0B8h+wRemoveMsg], 0; cx
0x18001f067  xor     r9d, r9d; Y
0x18001f06a  xor     r8d, r8d; X
0x18001f06d  lea     rdx, [r9-2]; hWndInsertAfter
0x18001f071  call    cs:__imp_SetWindowPos
0x18001f077  mov     edx, 7F02h; lpCursorName
0x18001f07c  xor     ecx, ecx; hInstance
0x18001f07e  call    cs:__imp_LoadCursorA
0x18001f084  mov     rcx, rax; hCursor
0x18001f087  call    cs:__imp_SetCursor
0x18001f08d  mov     r14, rax
0x18001f090  mov     [rsp+0B8h+hCursor], rax
0x18001f095  lea     rcx, aUrlmonDll; "urlmon.dll"
0x18001f09c  call    IsolationAwareLoadLibraryW
0x18001f0a1  mov     rbx, rax
0x18001f0a4  mov     [rsp+0B8h+hLibModule], rax
0x18001f0a9  test    rax, rax
0x18001f0ac  jz      loc_18001F198
0x18001f0b2  test    edi, edi
0x18001f0b4  jnz     loc_18001F198
0x18001f0ba  xor     ecx, ecx; pvReserved
0x18001f0bc  call    cs:__imp_CoInitialize
0x18001f0c2  test    eax, eax
0x18001f0c4  js      loc_18001F1BF
0x18001f0ca  mov     [rsp+0B8h+var_68], 1
0x18001f0d2  xorps   xmm0, xmm0
0x18001f0d5  movups  xmmword ptr [rsp+0B8h+Msg.hwnd], xmm0
0x18001f0da  movups  xmmword ptr [rsp+0B8h+Msg.wParam], xmm0
0x18001f0df  movups  xmmword ptr [rsp+0B8h+Msg.time], xmm0
0x18001f0e7  mov     [rsp+0B8h+wRemoveMsg], edi; wRemoveMsg
0x18001f0eb  xor     r9d, r9d; wMsgFilterMax
0x18001f0ee  xor     r8d, r8d; wMsgFilterMin
0x18001f0f1  xor     edx, edx; hWnd
0x18001f0f3  lea     rcx, [rsp+0B8h+Msg]; lpMsg
0x18001f0f8  call    cs:__imp_PeekMessageA
0x18001f0fe  lea     rdx, aHlinksimplenav; "HlinkSimpleNavigateToString"
0x18001f105  mov     rcx, rbx; hModule
0x18001f108  call    cs:__imp_GetProcAddress
0x18001f10e  mov     rdi, rax
0x18001f111  test    rax, rax
0x18001f114  jz      short loc_18001F190
0x18001f116  mov     [rsp+0B8h+ppbc], 0
0x18001f122  mov     [rsp+0B8h+ppbc], 0
0x18001f12e  lea     rdx, [rsp+0B8h+ppbc]; ppbc
0x18001f136  xor     ecx, ecx; reserved
0x18001f138  call    cs:__imp_CreateBindCtx
0x18001f13e  mov     [rsp+0B8h+var_80], 0
0x18001f146  mov     [rsp+0B8h+uFlags], 2
0x18001f14e  mov     qword ptr [rsp+0B8h+cy], 0
0x18001f157  mov     rcx, [rsp+0B8h+ppbc]
0x18001f15f  mov     qword ptr [rsp+0B8h+wRemoveMsg], rcx
0x18001f164  xor     r9d, r9d
0x18001f167  xor     r8d, r8d
0x18001f16a  xor     edx, edx
0x18001f16c  mov     rcx, r15
0x18001f16f  mov     rax, rdi
0x18001f172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f177  mov     rcx, [rsp+0B8h+ppbc]
0x18001f17f  test    rcx, rcx
0x18001f182  jz      short loc_18001F190
0x18001f184  mov     rax, [rcx]
0x18001f187  mov     rax, [rax+10h]
0x18001f18b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f190  call    cs:__imp_CoUninitialize
0x18001f196  jmp     short loc_18001F1BF
0x18001f198  mov     [rsp+0B8h+cy], 1; nShowCmd
0x18001f1a0  mov     qword ptr [rsp+0B8h+wRemoveMsg], 0; lpDirectory
0x18001f1a9  xor     r9d, r9d; lpParameters
0x18001f1ac  mov     r8, r15; lpFile
0x18001f1af  lea     rdx, Operation; "open"
0x18001f1b6  mov     rcx, rsi; hwnd
0x18001f1b9  call    cs:__imp_ShellExecuteW
0x18001f1bf  test    rbx, rbx
0x18001f1c2  jz      short loc_18001F1CD
0x18001f1c4  mov     rcx, rbx; hLibModule
0x18001f1c7  call    cs:__imp_FreeLibrary
0x18001f1cd  mov     rcx, r14; hCursor
0x18001f1d0  call    cs:__imp_SetCursor
0x18001f1d6  jmp     short loc_18001F206
0x18001f1d8  mov     rcx, [rsp+0B8h+hLibModule]; hLibModule
0x18001f1dd  test    rcx, rcx
0x18001f1e0  jz      short loc_18001F1E8
0x18001f1e2  call    cs:__imp_FreeLibrary
0x18001f1e8  cmp     [rsp+0B8h+var_68], 0
0x18001f1ed  jz      short loc_18001F1F5
0x18001f1ef  call    cs:__imp_CoUninitialize
0x18001f1f5  mov     rcx, [rsp+0B8h+hCursor]; hCursor
0x18001f1fa  test    rcx, rcx
0x18001f1fd  jz      short loc_18001F206
0x18001f1ff  call    cs:__imp_SetCursor
0x18001f205  nop
0x18001f206  lea     r11, [rsp+0B8h+var_18]
0x18001f20e  mov     rbx, [r11+20h]
0x18001f212  mov     rsi, [r11+28h]
0x18001f216  mov     rsp, r11
0x18001f219  pop     r15
0x18001f21b  pop     r14
0x18001f21d  pop     rdi
0x18001f21e  retn
```
