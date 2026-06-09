# PuOpenDbgFileLocal

- ea: `0x18001fed8`
- end: `0x18001ffc8`
- name: `PuOpenDbgFileLocal`
- size: `240`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180011c40`
- `0x1800205f0`

## callees

- `0x18001fed8`
- `0x18002e560`

## import_xrefs

- `msvcrt!sprintf_s` at `0x18001ff83`
- `msvcrt!sprintf_s` at `0x18001ff83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff5d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001ff94`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001ff94`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18001ff44`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18001ff44`

## string_xrefs

- `0x18001ff6c`: ` Critical Error: Unable to Open File %s. Error = %d\n`

## pseudocode

```c
__int64 __fastcall PuOpenDbgFileLocal(__int64 a1)
{
  const char *v3; // rdi
  HANDLE FileA; // rax
  DWORD LastError; // ebx
  char Buffer[1024]; // [rsp+40h] [rbp-418h] BYREF

  if ( !a1 )
    return 87;
  if ( *(_QWORD *)(a1 + 624) != -1 )
    return 0;
  v3 = (const char *)(a1 + 360);
  FileA = CreateFileA((LPCSTR)(a1 + 360), 0x40000000u, 3u, 0, 4u, 0x80u, 0);
  *(_QWORD *)(a1 + 624) = FileA;
  if ( FileA != (HANDLE)-1LL )
    return 0;
  LastError = GetLastError();
  sprintf_s(Buffer, 0x400u, " Critical Error: Unable to Open File %s. Error = %d\n", v3, LastError);
  OutputDebugStringA(Buffer);
  return LastError;
}

```

## disassembly

```asm
0x18001fed8  mov     [rsp+arg_8], rbx
0x18001fedd  push    rdi
0x18001fede  sub     rsp, 450h
0x18001fee5  mov     rax, cs:__security_cookie
0x18001feec  xor     rax, rsp
0x18001feef  mov     [rsp+458h+var_18], rax
0x18001fef7  mov     rbx, rcx
0x18001fefa  test    rcx, rcx
0x18001fefd  jnz     short loc_18001FF07
0x18001feff  lea     eax, [rcx+57h]
0x18001ff02  jmp     loc_18001FFA6
0x18001ff07  cmp     qword ptr [rcx+270h], 0FFFFFFFFFFFFFFFFh
0x18001ff0f  jnz     loc_18001FFA4
0x18001ff15  xor     r9d, r9d; lpSecurityAttributes
0x18001ff18  mov     [rsp+458h+hTemplateFile], 0; hTemplateFile
0x18001ff21  lea     rdi, [rcx+168h]
0x18001ff28  mov     [rsp+458h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001ff30  mov     edx, 40000000h; dwDesiredAccess
0x18001ff35  mov     [rsp+458h+dwCreationDisposition], 4; dwCreationDisposition
0x18001ff3d  mov     rcx, rdi; lpFileName
0x18001ff40  lea     r8d, [r9+3]; dwShareMode
0x18001ff44  call    cs:__imp_CreateFileA
0x18001ff4b  nop     dword ptr [rax+rax+00h]
0x18001ff50  mov     [rbx+270h], rax
0x18001ff57  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ff5b  jnz     short loc_18001FFA4
0x18001ff5d  call    cs:__imp_GetLastError
0x18001ff64  nop     dword ptr [rax+rax+00h]
0x18001ff69  mov     r9, rdi
0x18001ff6c  lea     r8, aCriticalErrorU; " Critical Error: Unable to Open File %s"...
0x18001ff73  lea     rcx, [rsp+458h+Buffer]; Buffer
0x18001ff78  mov     [rsp+458h+dwCreationDisposition], eax
0x18001ff7c  mov     edx, 400h; BufferCount
0x18001ff81  mov     ebx, eax
0x18001ff83  call    cs:__imp_sprintf_s
0x18001ff8a  nop     dword ptr [rax+rax+00h]
0x18001ff8f  lea     rcx, [rsp+458h+Buffer]; lpOutputString
0x18001ff94  call    cs:__imp_OutputDebugStringA
0x18001ff9b  nop     dword ptr [rax+rax+00h]
0x18001ffa0  mov     eax, ebx
0x18001ffa2  jmp     short loc_18001FFA6
0x18001ffa4  xor     eax, eax
0x18001ffa6  mov     rcx, [rsp+458h+var_18]
0x18001ffae  xor     rcx, rsp; StackCookie
0x18001ffb1  call    __security_check_cookie
0x18001ffb6  mov     rbx, [rsp+458h+arg_8]
0x18001ffbe  add     rsp, 450h
0x18001ffc5  pop     rdi
0x18001ffc6  retn
```
