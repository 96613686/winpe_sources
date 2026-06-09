# DoMessage

- ea: `0x1800080c4`
- end: `0x180008233`
- name: `DoMessage`
- size: `367`
- prototype: `int __fastcall(HWND hWnd, LPCWSTR lpText, UINT uType)`
- caller_count: `9`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180004e80`
- `0x180005530`
- `0x180007c0c`
- `0x1800085c8`
- `0x18000af80`
- `0x18000b9c0`
- `0x18000c388`
- `0x18000cfc4`
- `0x18000dc70`

## callees

- `0x1800080c4`
- `0x180008348`
- `0x18000a378`
- `0x180014ae0`
- `0x180015010`

## import_xrefs

- `USER32!ReleaseDC` at `0x180008156`
- `USER32!ReleaseDC` at `0x180008156`
- `USER32!GetDC` at `0x18000813a`
- `USER32!GetDC` at `0x18000813a`
- `USER32!GetWindowTextW` at `0x1800081b6`
- `USER32!GetWindowTextW` at `0x1800081b6`
- `USER32!GetParent` at `0x180008180`
- `USER32!GetParent` at `0x180008191`
- `USER32!GetParent` at `0x180008180`
- `USER32!GetParent` at `0x180008191`
- `USER32!GetDesktopWindow` at `0x18000816d`
- `USER32!GetDesktopWindow` at `0x18000816d`
- `USER32!MessageBoxW` at `0x180008206`
- `USER32!MessageBoxW` at `0x180008206`
- `KERNEL32!GetModuleHandleW` at `0x18000810d`
- `KERNEL32!GetModuleHandleW` at `0x18000810d`
- `KERNEL32!GetProcAddress` at `0x180008129`
- `KERNEL32!GetProcAddress` at `0x180008129`

## string_xrefs

- `0x180008106`: `gdi32.dll`

## pseudocode

```c
int __fastcall DoMessage(HWND hWnd, LPCWSTR lpText, UINT uType)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rdi
  HDC DC; // rbx
  int v9; // edi
  HWND v10; // rdi
  HWND Parent; // rax
  HWND v12; // rbx
  WCHAR *i; // rcx
  WCHAR String[128]; // [rsp+20h] [rbp-138h] BYREF

  if ( hWnd )
  {
    ModuleHandleW = hModule;
    if ( hModule || (ModuleHandleW = GetModuleHandleW(L"gdi32.dll"), (hModule = ModuleHandleW) != 0) )
    {
      ProcAddress = GetProcAddress(ModuleHandleW, "GetLayout");
      if ( ProcAddress )
      {
        DC = GetDC(hWnd);
        v9 = ((__int64 (__fastcall *)(HDC))ProcAddress)(DC);
        ReleaseDC(hWnd, DC);
        if ( v9 != -1 && (v9 & 1) != 0 )
          uType |= 0x180000u;
      }
    }
  }
  v10 = 0;
  if ( hWnd != GetDesktopWindow() )
    v10 = hWnd;
  Parent = GetParent(v10);
  if ( Parent )
  {
    do
    {
      v12 = Parent;
      Parent = GetParent(Parent);
    }
    while ( Parent );
  }
  else
  {
    v12 = v10;
  }
  if ( v12 && GetWindowTextW(v12, String, 128) )
  {
    if ( !(unsigned int)IsODBCAD32() )
    {
      for ( i = String; *i; ++i )
      {
        if ( *i == 45 )
        {
          *i = 0;
          return MessageBoxW(v10, lpText, String, uType);
        }
      }
    }
  }
  else
  {
    SetString(String, 128);
  }
  return MessageBoxW(v10, lpText, String, uType);
}

```

## disassembly

```asm
0x1800080c4  mov     [rsp+arg_18], rbx
0x1800080c9  push    rbp
0x1800080ca  push    rsi
0x1800080cb  push    rdi
0x1800080cc  push    r14
0x1800080ce  push    r15
0x1800080d0  sub     rsp, 130h
0x1800080d7  mov     rax, cs:__security_cookie
0x1800080de  xor     rax, rsp
0x1800080e1  mov     [rsp+158h+var_38], rax
0x1800080e9  xor     r15d, r15d
0x1800080ec  mov     ebp, r8d
0x1800080ef  mov     r14, rdx
0x1800080f2  mov     rsi, rcx
0x1800080f5  test    rcx, rcx
0x1800080f8  jz      short loc_18000816D
0x1800080fa  mov     rax, cs:hModule
0x180008101  test    rax, rax
0x180008104  jnz     short loc_18000811F
0x180008106  lea     rcx, ModuleName; "gdi32.dll"
0x18000810d  call    cs:__imp_GetModuleHandleW
0x180008113  mov     cs:hModule, rax
0x18000811a  test    rax, rax
0x18000811d  jz      short loc_18000816D
0x18000811f  lea     rdx, aGetlayout; "GetLayout"
0x180008126  mov     rcx, rax; hModule
0x180008129  call    cs:__imp_GetProcAddress
0x18000812f  mov     rdi, rax
0x180008132  test    rax, rax
0x180008135  jz      short loc_18000816D
0x180008137  mov     rcx, rsi; hWnd
0x18000813a  call    cs:__imp_GetDC
0x180008140  mov     rbx, rax
0x180008143  mov     rcx, rax
0x180008146  mov     rax, rdi
0x180008149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000814e  mov     rdx, rbx; hDC
0x180008151  mov     rcx, rsi; hWnd
0x180008154  mov     edi, eax
0x180008156  call    cs:__imp_ReleaseDC
0x18000815c  cmp     edi, 0FFFFFFFFh
0x18000815f  jz      short loc_18000816D
0x180008161  test    dil, 1
0x180008165  jz      short loc_18000816D
0x180008167  or      ebp, 180000h
0x18000816d  call    cs:__imp_GetDesktopWindow
0x180008173  cmp     rsi, rax
0x180008176  mov     rdi, r15
0x180008179  cmovnz  rdi, rsi
0x18000817d  mov     rcx, rdi; hWnd
0x180008180  call    cs:__imp_GetParent
0x180008186  test    rax, rax
0x180008189  jz      short loc_18000819E
0x18000818b  mov     rcx, rax; hWnd
0x18000818e  mov     rbx, rax
0x180008191  call    cs:__imp_GetParent
0x180008197  test    rax, rax
0x18000819a  jnz     short loc_18000818B
0x18000819c  jmp     short loc_1800081A1
0x18000819e  mov     rbx, rdi
0x1800081a1  mov     esi, 80h
0x1800081a6  test    rbx, rbx
0x1800081a9  jz      short loc_1800081E6
0x1800081ab  mov     r8d, esi; nMaxCount
0x1800081ae  lea     rdx, [rsp+158h+String]; lpString
0x1800081b3  mov     rcx, rbx; hWnd
0x1800081b6  call    cs:__imp_GetWindowTextW
0x1800081bc  test    eax, eax
0x1800081be  jz      short loc_1800081E6
0x1800081c0  call    IsODBCAD32
0x1800081c5  test    eax, eax
0x1800081c7  jnz     short loc_1800081F8
0x1800081c9  lea     rcx, [rsp+158h+String]
0x1800081ce  cmp     [rcx], r15w
0x1800081d2  jz      short loc_1800081F8
0x1800081d4  cmp     word ptr [rcx], 2Dh ; '-'
0x1800081d8  jz      short loc_1800081E0
0x1800081da  add     rcx, 2
0x1800081de  jmp     short loc_1800081CE
0x1800081e0  mov     [rcx], r15w
0x1800081e4  jmp     short loc_1800081F8
0x1800081e6  mov     r8d, 522h
0x1800081ec  lea     rcx, [rsp+158h+String]; lpBuffer
0x1800081f1  mov     edx, esi; cchBufferMax
0x1800081f3  call    SetString
0x1800081f8  mov     r9d, ebp; uType
0x1800081fb  lea     r8, [rsp+158h+String]; lpCaption
0x180008200  mov     rdx, r14; lpText
0x180008203  mov     rcx, rdi; hWnd
0x180008206  call    cs:__imp_MessageBoxW
0x18000820c  mov     rcx, [rsp+158h+var_38]
0x180008214  xor     rcx, rsp; StackCookie
0x180008217  call    __security_check_cookie
0x18000821c  mov     rbx, [rsp+158h+arg_18]
0x180008224  add     rsp, 130h
0x18000822b  pop     r15
0x18000822d  pop     r14
0x18000822f  pop     rdi
0x180008230  pop     rsi
0x180008231  pop     rbp
0x180008232  retn
```
