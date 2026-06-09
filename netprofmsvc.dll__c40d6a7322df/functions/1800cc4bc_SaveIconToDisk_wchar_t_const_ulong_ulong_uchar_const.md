# SaveIconToDisk(wchar_t const *,ulong,ulong,uchar const *)

- ea: `0x1800cc4bc`
- end: `0x1800cc5cc`
- name: `?SaveIconToDisk@@YAJPEB_WKKPEBE@Z`
- size: `272`
- prototype: `__int64 __fastcall(const wchar_t *, int, DWORD, const unsigned __int8 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800cee2c`
- `0x1800e55a0`

## callees

- `0x180014d80`
- `0x1800a88a0`
- `0x1800caf10`
- `0x1800cc4bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc584`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc584`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc597`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cc58f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800cc58f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800cc550`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800cc550`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800cc57a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800cc57a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SaveIconToDisk(const wchar_t *a1, int a2, DWORD a3, const unsigned __int8 *a4)
{
  int System32Directory; // ebx
  HANDLE FileW; // rax
  void *v10; // rdi
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-668h] BYREF
  wchar_t v13[264]; // [rsp+50h] [rbp-658h] BYREF
  WCHAR FileName[520]; // [rsp+260h] [rbp-448h] BYREF

  System32Directory = GetSystem32Directory(v13);
  if ( !System32Directory )
  {
    StringCchPrintfW(FileName, 0x208u, L"%s\\networklist\\icons\\%s_%d.bin", v13, a1, a2);
    FileW = CreateFileW(FileName, 0xC0000000, 0, 0, 2u, 0x80u, 0);
    v10 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      System32Directory = GetLastError();
    }
    else
    {
      NumberOfBytesWritten = System32Directory;
      if ( !WriteFile(FileW, a4, a3, &NumberOfBytesWritten, 0) )
        System32Directory = GetLastError();
      CloseHandle(v10);
    }
  }
  if ( System32Directory > 0 )
    return (unsigned __int16)System32Directory | 0x80070000;
  return (unsigned int)System32Directory;
}

```

## disassembly

```asm
0x1800cc4bc  push    rbx
0x1800cc4be  push    rbp
0x1800cc4bf  push    rsi
0x1800cc4c0  push    rdi
0x1800cc4c1  push    r14
0x1800cc4c3  sub     rsp, 680h
0x1800cc4ca  mov     rax, cs:__security_cookie
0x1800cc4d1  xor     rax, rsp
0x1800cc4d4  mov     [rsp+6A8h+var_38], rax
0x1800cc4dc  mov     rdi, rcx
0x1800cc4df  mov     rbp, r9
0x1800cc4e2  lea     rcx, [rsp+6A8h+var_658]; wchar_t *
0x1800cc4e7  mov     esi, r8d
0x1800cc4ea  mov     r14d, edx
0x1800cc4ed  call    ?GetSystem32Directory@@YAKPEA_W@Z; GetSystem32Directory(wchar_t *)
0x1800cc4f2  mov     ebx, eax
0x1800cc4f4  test    eax, eax
0x1800cc4f6  jnz     loc_1800CC59F
0x1800cc4fc  mov     [rsp+6A8h+dwFlagsAndAttributes], r14d
0x1800cc501  lea     r9, [rsp+6A8h+var_658]
0x1800cc506  lea     r8, aSNetworklistIc_0; "%s\\networklist\\icons\\%s_%d.bin"
0x1800cc50d  mov     qword ptr [rsp+6A8h+dwCreationDisposition], rdi
0x1800cc512  mov     edx, 208h; unsigned __int64
0x1800cc517  lea     rcx, [rsp+6A8h+FileName]; wchar_t *
0x1800cc51f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800cc524  mov     [rsp+6A8h+hTemplateFile], 0; hTemplateFile
0x1800cc52d  lea     rcx, [rsp+6A8h+FileName]; lpFileName
0x1800cc535  mov     [rsp+6A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800cc53d  xor     r9d, r9d; lpSecurityAttributes
0x1800cc540  xor     r8d, r8d; dwShareMode
0x1800cc543  mov     [rsp+6A8h+dwCreationDisposition], 2; dwCreationDisposition
0x1800cc54b  mov     edx, 0C0000000h; dwDesiredAccess
0x1800cc550  call    cs:__imp_CreateFileW
0x1800cc556  mov     rdi, rax
0x1800cc559  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800cc55d  jz      short loc_1800CC597
0x1800cc55f  lea     r9, [rsp+6A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800cc564  mov     [rsp+6A8h+NumberOfBytesWritten], ebx
0x1800cc568  mov     r8d, esi; nNumberOfBytesToWrite
0x1800cc56b  mov     qword ptr [rsp+6A8h+dwCreationDisposition], 0; lpOverlapped
0x1800cc574  mov     rdx, rbp; lpBuffer
0x1800cc577  mov     rcx, rax; hFile
0x1800cc57a  call    cs:__imp_WriteFile
0x1800cc580  test    eax, eax
0x1800cc582  jnz     short loc_1800CC58C
0x1800cc584  call    cs:__imp_GetLastError
0x1800cc58a  mov     ebx, eax
0x1800cc58c  mov     rcx, rdi; hObject
0x1800cc58f  call    cs:__imp_CloseHandle
0x1800cc595  jmp     short loc_1800CC59F
0x1800cc597  call    cs:__imp_GetLastError
0x1800cc59d  mov     ebx, eax
0x1800cc59f  test    ebx, ebx
0x1800cc5a1  jle     short loc_1800CC5AC
0x1800cc5a3  movzx   ebx, bx
0x1800cc5a6  or      ebx, 80070000h
0x1800cc5ac  mov     eax, ebx
0x1800cc5ae  mov     rcx, [rsp+6A8h+var_38]
0x1800cc5b6  xor     rcx, rsp; StackCookie
0x1800cc5b9  call    __security_check_cookie
0x1800cc5be  add     rsp, 680h
0x1800cc5c5  pop     r14
0x1800cc5c7  pop     rdi
0x1800cc5c8  pop     rsi
0x1800cc5c9  pop     rbp
0x1800cc5ca  pop     rbx
0x1800cc5cb  retn
```
