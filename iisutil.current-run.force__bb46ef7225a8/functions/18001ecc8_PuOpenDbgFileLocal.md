# PuOpenDbgFileLocal

- ea: `0x18001ecc8`
- end: `0x18001ed9b`
- name: `PuOpenDbgFileLocal`
- size: `211`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800109e0`
- `0x18001f360`

## callees

- `0x18001ecc8`
- `0x18002c4c0`

## import_xrefs

- `msvcrt!sprintf_s` at `0x18001ed63`
- `msvcrt!sprintf_s` at `0x18001ed63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed43`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001ed6e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18001ed6e`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18001ed30`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18001ed30`

## string_xrefs

- `0x18001ed4c`: ` Critical Error: Unable to Open File %s. Error = %d\n`

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
0x18001ecc8  mov     [rsp+arg_8], rbx
0x18001eccd  push    rdi
0x18001ecce  sub     rsp, 450h
0x18001ecd5  mov     rax, cs:__security_cookie
0x18001ecdc  xor     rax, rsp
0x18001ecdf  mov     [rsp+458h+var_18], rax
0x18001ece7  mov     rbx, rcx
0x18001ecea  test    rcx, rcx
0x18001eced  jnz     short loc_18001ECF7
0x18001ecef  lea     eax, [rcx+57h]
0x18001ecf2  jmp     loc_18001ED7A
0x18001ecf7  cmp     qword ptr [rcx+270h], 0FFFFFFFFFFFFFFFFh
0x18001ecff  jnz     short loc_18001ED78
0x18001ed01  xor     r9d, r9d; lpSecurityAttributes
0x18001ed04  mov     [rsp+458h+hTemplateFile], 0; hTemplateFile
0x18001ed0d  lea     rdi, [rcx+168h]
0x18001ed14  mov     [rsp+458h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001ed1c  mov     edx, 40000000h; dwDesiredAccess
0x18001ed21  mov     [rsp+458h+dwCreationDisposition], 4; dwCreationDisposition
0x18001ed29  mov     rcx, rdi; lpFileName
0x18001ed2c  lea     r8d, [r9+3]; dwShareMode
0x18001ed30  call    cs:__imp_CreateFileA
0x18001ed36  mov     [rbx+270h], rax
0x18001ed3d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ed41  jnz     short loc_18001ED78
0x18001ed43  call    cs:__imp_GetLastError
0x18001ed49  mov     r9, rdi
0x18001ed4c  lea     r8, aCriticalErrorU; " Critical Error: Unable to Open File %s"...
0x18001ed53  lea     rcx, [rsp+458h+Buffer]; Buffer
0x18001ed58  mov     [rsp+458h+dwCreationDisposition], eax
0x18001ed5c  mov     edx, 400h; BufferCount
0x18001ed61  mov     ebx, eax
0x18001ed63  call    cs:__imp_sprintf_s
0x18001ed69  lea     rcx, [rsp+458h+Buffer]; lpOutputString
0x18001ed6e  call    cs:__imp_OutputDebugStringA
0x18001ed74  mov     eax, ebx
0x18001ed76  jmp     short loc_18001ED7A
0x18001ed78  xor     eax, eax
0x18001ed7a  mov     rcx, [rsp+458h+var_18]
0x18001ed82  xor     rcx, rsp; StackCookie
0x18001ed85  call    __security_check_cookie
0x18001ed8a  mov     rbx, [rsp+458h+arg_8]
0x18001ed92  add     rsp, 450h
0x18001ed99  pop     rdi
0x18001ed9a  retn
```
