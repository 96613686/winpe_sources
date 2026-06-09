# _SwitchToAnotherInstanceOfCleanMgrAlreadyRunning(HINSTANCE__ *)

- ea: `0x14000a534`
- end: `0x14000a667`
- name: `?_SwitchToAnotherInstanceOfCleanMgrAlreadyRunning@@YAXPEAUHINSTANCE__@@@Z`
- size: `307`
- prototype: `void __fastcall(HINSTANCE hInstance)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140009d34`

## callees

- `0x1400029a0`
- `0x14000a534`
- `0x140016d7c`

## import_xrefs

- `USER32!LoadStringW` at `0x14000a5ae`
- `USER32!LoadStringW` at `0x14000a5d7`
- `USER32!LoadStringW` at `0x14000a600`
- `USER32!LoadStringW` at `0x14000a629`
- `USER32!LoadStringW` at `0x14000a5ae`
- `USER32!LoadStringW` at `0x14000a5d7`
- `USER32!LoadStringW` at `0x14000a600`
- `USER32!LoadStringW` at `0x14000a629`
- `USER32!EnumWindows` at `0x14000a58b`
- `USER32!EnumWindows` at `0x14000a5c2`
- `USER32!EnumWindows` at `0x14000a5eb`
- `USER32!EnumWindows` at `0x14000a614`
- `USER32!EnumWindows` at `0x14000a63d`
- `USER32!EnumWindows` at `0x14000a58b`
- `USER32!EnumWindows` at `0x14000a5c2`
- `USER32!EnumWindows` at `0x14000a5eb`
- `USER32!EnumWindows` at `0x14000a614`
- `USER32!EnumWindows` at `0x14000a63d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000a594`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000a594`

## pseudocode

```c
void __fastcall _SwitchToAnotherInstanceOfCleanMgrAlreadyRunning(HINSTANCE hInstance)
{
  unsigned __int16 *v2; // rax
  unsigned __int16 *v3; // rdi
  WCHAR Buffer[64]; // [rsp+20h] [rbp-49h] BYREF

  v2 = SHFormatMessage(0x64u, &String, &String);
  v3 = v2;
  if ( v2 )
  {
    EnumWindows(EnumWindowsProc, (LPARAM)v2);
    LocalFree(v3);
  }
  LoadStringW(hInstance, 0x4BAu, Buffer, 64);
  if ( Buffer[0] )
    EnumWindows(EnumWindowsProc, (LPARAM)Buffer);
  LoadStringW(hInstance, 0x1Cu, Buffer, 64);
  if ( Buffer[0] )
    EnumWindows(EnumWindowsProc, (LPARAM)Buffer);
  LoadStringW(hInstance, 0x4B0u, Buffer, 64);
  if ( Buffer[0] )
    EnumWindows(EnumWindowsProc, (LPARAM)Buffer);
  LoadStringW(hInstance, 0x4B6u, Buffer, 64);
  if ( Buffer[0] )
    EnumWindows(EnumWindowsProc, (LPARAM)Buffer);
}

```

## disassembly

```asm
0x14000a534  mov     [rsp-8+arg_8], rbx
0x14000a539  mov     [rsp-8+arg_10], rsi
0x14000a53e  push    rbp
0x14000a53f  push    rdi
0x14000a540  push    r14
0x14000a542  lea     rbp, [rsp-47h]
0x14000a547  sub     rsp, 0B0h
0x14000a54e  mov     rax, cs:__security_cookie
0x14000a555  xor     rax, rsp
0x14000a558  mov     [rbp+57h+var_20], rax
0x14000a55c  lea     rdx, String
0x14000a563  mov     rbx, rcx
0x14000a566  mov     r8, rdx
0x14000a569  mov     ecx, 64h ; 'd'; dwMessageId
0x14000a56e  call    ?SHFormatMessage@@YAPEAGKZZ; SHFormatMessage(ulong,...)
0x14000a573  xor     r14d, r14d
0x14000a576  lea     rsi, ?EnumWindowsProc@@YAHPEAUHWND__@@_J@Z; EnumWindowsProc(HWND__ *,__int64)
0x14000a57d  mov     rdi, rax
0x14000a580  test    rax, rax
0x14000a583  jz      short loc_14000A59A
0x14000a585  mov     rdx, rax; lParam
0x14000a588  mov     rcx, rsi; lpEnumFunc
0x14000a58b  call    cs:__imp_EnumWindows
0x14000a591  mov     rcx, rdi; hMem
0x14000a594  call    cs:__imp_LocalFree
0x14000a59a  mov     edi, 40h ; '@'
0x14000a59f  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x14000a5a3  mov     r9d, edi; cchBufferMax
0x14000a5a6  mov     edx, 4BAh; uID
0x14000a5ab  mov     rcx, rbx; hInstance
0x14000a5ae  call    cs:__imp_LoadStringW
0x14000a5b4  cmp     [rbp+57h+Buffer], r14w
0x14000a5b9  jz      short loc_14000A5C8
0x14000a5bb  lea     rdx, [rbp+57h+Buffer]; lParam
0x14000a5bf  mov     rcx, rsi; lpEnumFunc
0x14000a5c2  call    cs:__imp_EnumWindows
0x14000a5c8  mov     r9d, edi; cchBufferMax
0x14000a5cb  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x14000a5cf  mov     edx, 1Ch; uID
0x14000a5d4  mov     rcx, rbx; hInstance
0x14000a5d7  call    cs:__imp_LoadStringW
0x14000a5dd  cmp     [rbp+57h+Buffer], r14w
0x14000a5e2  jz      short loc_14000A5F1
0x14000a5e4  lea     rdx, [rbp+57h+Buffer]; lParam
0x14000a5e8  mov     rcx, rsi; lpEnumFunc
0x14000a5eb  call    cs:__imp_EnumWindows
0x14000a5f1  mov     r9d, edi; cchBufferMax
0x14000a5f4  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x14000a5f8  mov     edx, 4B0h; uID
0x14000a5fd  mov     rcx, rbx; hInstance
0x14000a600  call    cs:__imp_LoadStringW
0x14000a606  cmp     [rbp+57h+Buffer], r14w
0x14000a60b  jz      short loc_14000A61A
0x14000a60d  lea     rdx, [rbp+57h+Buffer]; lParam
0x14000a611  mov     rcx, rsi; lpEnumFunc
0x14000a614  call    cs:__imp_EnumWindows
0x14000a61a  mov     r9d, edi; cchBufferMax
0x14000a61d  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x14000a621  mov     edx, 4B6h; uID
0x14000a626  mov     rcx, rbx; hInstance
0x14000a629  call    cs:__imp_LoadStringW
0x14000a62f  cmp     [rbp+57h+Buffer], r14w
0x14000a634  jz      short loc_14000A643
0x14000a636  lea     rdx, [rbp+57h+Buffer]; lParam
0x14000a63a  mov     rcx, rsi; lpEnumFunc
0x14000a63d  call    cs:__imp_EnumWindows
0x14000a643  mov     rcx, [rbp+57h+var_20]
0x14000a647  xor     rcx, rsp; StackCookie
0x14000a64a  call    __security_check_cookie
0x14000a64f  lea     r11, [rsp+0C0h+var_10]
0x14000a657  mov     rbx, [r11+28h]
0x14000a65b  mov     rsi, [r11+30h]
0x14000a65f  mov     rsp, r11
0x14000a662  pop     r14
0x14000a664  pop     rdi
0x14000a665  pop     rbp
0x14000a666  retn
```
