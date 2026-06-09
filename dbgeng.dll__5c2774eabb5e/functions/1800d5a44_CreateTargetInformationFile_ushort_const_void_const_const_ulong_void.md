# CreateTargetInformationFile(ushort const *,void * const * const,ulong,void * *)

- ea: `0x1800d5a44`
- end: `0x1800d5d28`
- name: `?CreateTargetInformationFile@@YAJPEBGQEBQEAXKPEAPEAX@Z`
- size: `740`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void *const *const, unsigned int, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180274314`

## callees

- `0x1800793cc`
- `0x1800d5a44`
- `0x1800e0b50`
- `0x1800f0f40`
- `0x1800f13ec`
- `0x1800f1720`
- `0x1802744cc`
- `0x1804da4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5ac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5bd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5bef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5ca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5cc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5ac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5bd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5bef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5ca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5cc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d5b51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d5b51`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d5bc1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d5c99`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d5bc1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800d5c99`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d5aaf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d5aaf`

## string_xrefs

- `0x1800d5cb7`: `Writing page directory failed, error %#x\n`
- `0x1800d5ad3`: `Could not create output file %ls, error %#x\n`
- `0x1800d5c3f`: `Allocating page directory array failed`
- `0x1800d5ce7`: `Writing page directory wrote fewer bytes than expected`

## pseudocode

```c
__int64 __fastcall CreateTargetInformationFile(
        const unsigned __int16 *a1,
        void *const *const a2,
        unsigned int a3,
        void **a4)
{
  __int64 FileW; // rdi
  __int64 LastError; // rbx
  __int64 v10; // rsi
  int v11; // eax
  DWORD v13; // r14d
  DWORD v14; // eax
  signed int v15; // eax
  unsigned __int64 v16; // rax
  void *v17; // rax
  void *v18; // rsi
  __int64 i; // rcx
  const struct std::nothrow_t *v20; // rdx
  DWORD v21; // eax
  signed int v22; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD Buffer[36]; // [rsp+50h] [rbp-B0h] BYREF

  *a4 = (void *)-1LL;
  if ( a3 <= 0x10 )
  {
    LODWORD(LastError) = 0;
    FileW = (__int64)CreateFileW(a1, 0xC0000000, 7u, 0, 2u, 0x4000000u, 0);
    if ( FileW == -1 )
    {
      LastError = GetLastError();
      ErrOut(L"Could not create output file %ls, error %#x\n", a1, LastError);
      if ( (int)LastError > 0 )
        LODWORD(LastError) = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    FileW = -1;
    LODWORD(LastError) = -2147024809;
  }
  memset(Buffer, 0, sizeof(Buffer));
  NumberOfBytesWritten = 0;
  if ( (int)LastError < 0 )
    goto LABEL_12;
  v10 = 0;
  v11 = 1;
  if ( a3 )
  {
    do
    {
      if ( v11 != 1 )
        break;
      v11 = OpenPageFileToBeAddedToPageDump(a2[v10], (struct _PAGEDUMP_DATA *)Buffer);
      v10 = (unsigned int)(v10 + 1);
    }
    while ( (unsigned int)v10 < a3 );
    if ( !v11 )
    {
      LODWORD(LastError) = -2147467259;
      goto LABEL_12;
    }
  }
  Buffer[0] = 0x504D442E45474150LL;
  v13 = 4 * HIDWORD(Buffer[35]);
  LODWORD(Buffer[2]) = 4 * HIDWORD(Buffer[35]) + 148;
  if ( WriteFile((HANDLE)FileW, Buffer, 0x94u, &NumberOfBytesWritten, 0) )
  {
    if ( NumberOfBytesWritten != 148 )
    {
      ErrOut(L"Writing page dump header wrote fewer bytes than expected");
      LODWORD(LastError) = -2147418113;
      goto LABEL_12;
    }
  }
  else
  {
    v14 = GetLastError();
    ErrOut(L"Writing page dump header failed, error %#x\n", v14);
    v15 = GetLastError();
    LODWORD(LastError) = v15;
    if ( v15 > 0 )
      LODWORD(LastError) = (unsigned __int16)v15 | 0x80070000;
    if ( (int)LastError < 0 )
      goto LABEL_12;
  }
  v16 = 4LL * HIDWORD(Buffer[35]);
  if ( !is_mul_ok(HIDWORD(Buffer[35]), 4u) )
    v16 = -1;
  v17 = operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
  v18 = v17;
  if ( v17 )
  {
    for ( i = 0; (unsigned int)i < HIDWORD(Buffer[35]); i = (unsigned int)(i + 1) )
      *((_DWORD *)v17 + i) = i;
    if ( WriteFile((HANDLE)FileW, v17, v13, &NumberOfBytesWritten, 0) )
    {
      if ( NumberOfBytesWritten != v13 )
      {
        ErrOut(L"Writing page directory wrote fewer bytes than expected");
        LODWORD(LastError) = -2147418113;
      }
    }
    else
    {
      v21 = GetLastError();
      ErrOut(L"Writing page directory failed, error %#x\n", v21);
      v22 = GetLastError();
      LODWORD(LastError) = v22;
      if ( v22 > 0 )
        LODWORD(LastError) = (unsigned __int16)v22 | 0x80070000;
    }
    operator delete(v18, v20);
    if ( (int)LastError >= 0 )
    {
      LODWORD(LastError) = CopyPageFilesToTIF((HANDLE)FileW, (struct _PAGEDUMP_DATA *const)Buffer);
      if ( (int)LastError >= 0 )
      {
        *a4 = (void *)FileW;
        return (unsigned int)LastError;
      }
    }
  }
  else
  {
    ErrOut(L"Allocating page directory array failed");
    LODWORD(LastError) = -2147024882;
  }
LABEL_12:
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800d5a44  push    rbp
0x1800d5a46  push    rbx
0x1800d5a47  push    rsi
0x1800d5a48  push    rdi
0x1800d5a49  push    r12
0x1800d5a4b  push    r14
0x1800d5a4d  push    r15
0x1800d5a4f  lea     rbp, [rsp-80h]
0x1800d5a54  sub     rsp, 180h
0x1800d5a5b  mov     rax, cs:__security_cookie
0x1800d5a62  xor     rax, rsp
0x1800d5a65  mov     [rbp+0B0h+var_40], rax
0x1800d5a69  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d5a6d  mov     r12, r9
0x1800d5a70  mov     [r9], rax
0x1800d5a73  mov     r14d, r8d
0x1800d5a76  mov     r15, rdx
0x1800d5a79  mov     rsi, rcx
0x1800d5a7c  cmp     r8d, 10h
0x1800d5a80  jbe     short loc_1800D5A8C
0x1800d5a82  mov     rdi, rax
0x1800d5a85  mov     ebx, 80070057h
0x1800d5a8a  jmp     short loc_1800D5AF1
0x1800d5a8c  xor     ebx, ebx
0x1800d5a8e  xor     r9d, r9d; lpSecurityAttributes
0x1800d5a91  mov     [rsp+1B0h+hTemplateFile], rbx; hTemplateFile
0x1800d5a96  mov     edx, 0C0000000h; dwDesiredAccess
0x1800d5a9b  mov     [rsp+1B0h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x1800d5aa3  mov     [rsp+1B0h+dwCreationDisposition], 2; dwCreationDisposition
0x1800d5aab  lea     r8d, [rbx+7]; dwShareMode
0x1800d5aaf  call    cs:__imp_CreateFileW
0x1800d5ab6  nop     dword ptr [rax+rax+00h]
0x1800d5abb  mov     rdi, rax
0x1800d5abe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d5ac2  jnz     short loc_1800D5AF1
0x1800d5ac4  call    cs:__imp_GetLastError
0x1800d5acb  nop     dword ptr [rax+rax+00h]
0x1800d5ad0  mov     rdx, rsi
0x1800d5ad3  lea     rcx, aCouldNotCreate; "Could not create output file %ls, error"...
0x1800d5ada  mov     r8d, eax
0x1800d5add  mov     ebx, eax
0x1800d5adf  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800d5ae4  test    ebx, ebx
0x1800d5ae6  jle     short loc_1800D5AF1
0x1800d5ae8  movzx   ebx, bx
0x1800d5aeb  or      ebx, 80070000h
0x1800d5af1  xor     eax, eax
0x1800d5af3  mov     byte ptr [rsp+1B0h+Buffer], 0
0x1800d5af8  xor     edx, edx; Val
0x1800d5afa  mov     [rbp+0B0h+var_CC], eax
0x1800d5afd  mov     r8d, 11Fh; Size
0x1800d5b03  lea     rcx, [rsp+1B0h+Buffer+1]; void *
0x1800d5b08  call    memset
0x1800d5b0d  mov     [rsp+1B0h+NumberOfBytesWritten], 0
0x1800d5b15  test    ebx, ebx
0x1800d5b17  js      short loc_1800D5B48
0x1800d5b19  xor     esi, esi
0x1800d5b1b  mov     eax, 1
0x1800d5b20  test    r14d, r14d
0x1800d5b23  jz      short loc_1800D5B7E
0x1800d5b25  cmp     eax, 1
0x1800d5b28  jnz     short loc_1800D5B3F
0x1800d5b2a  mov     rcx, [r15+rsi*8]; hFile
0x1800d5b2e  lea     rdx, [rsp+1B0h+Buffer]; struct _PAGEDUMP_DATA *
0x1800d5b33  call    ?OpenPageFileToBeAddedToPageDump@@YAHPEAXPEAU_PAGEDUMP_DATA@@@Z; OpenPageFileToBeAddedToPageDump(void *,_PAGEDUMP_DATA *)
0x1800d5b38  inc     esi
0x1800d5b3a  cmp     esi, r14d
0x1800d5b3d  jb      short loc_1800D5B25
0x1800d5b3f  test    eax, eax
0x1800d5b41  jnz     short loc_1800D5B7E
0x1800d5b43  mov     ebx, 80004005h
0x1800d5b48  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800d5b4c  jz      short loc_1800D5B5D
0x1800d5b4e  mov     rcx, rdi; hObject
0x1800d5b51  call    cs:__imp_CloseHandle
0x1800d5b58  nop     dword ptr [rax+rax+00h]
0x1800d5b5d  mov     eax, ebx
0x1800d5b5f  mov     rcx, [rbp+0B0h+var_40]
0x1800d5b63  xor     rcx, rsp; StackCookie
0x1800d5b66  call    __security_check_cookie
0x1800d5b6b  add     rsp, 180h
0x1800d5b72  pop     r15
0x1800d5b74  pop     r14
0x1800d5b76  pop     r12
0x1800d5b78  pop     rdi
0x1800d5b79  pop     rsi
0x1800d5b7a  pop     rbx
0x1800d5b7b  pop     rbp
0x1800d5b7c  retn
0x1800d5b7e  mov     rax, 504D442E45474150h
0x1800d5b88  mov     qword ptr [rsp+1B0h+dwCreationDisposition], 0; lpOverlapped
0x1800d5b91  mov     [rsp+1B0h+Buffer], rax
0x1800d5b96  lea     r9, [rsp+1B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800d5b9b  mov     eax, [rbp+0B0h+var_44]
0x1800d5b9e  lea     rdx, [rsp+1B0h+Buffer]; lpBuffer
0x1800d5ba3  mov     esi, 94h
0x1800d5ba8  mov     rcx, rdi; hFile
0x1800d5bab  mov     r8d, esi; nNumberOfBytesToWrite
0x1800d5bae  lea     r14d, ds:0[rax*4]
0x1800d5bb6  lea     eax, [r14+94h]
0x1800d5bbd  mov     [rsp+1B0h+var_150], eax
0x1800d5bc1  call    cs:__imp_WriteFile
0x1800d5bc8  nop     dword ptr [rax+rax+00h]
0x1800d5bcd  test    eax, eax
0x1800d5bcf  jnz     loc_1800D5C55
0x1800d5bd5  call    cs:__imp_GetLastError
0x1800d5bdc  nop     dword ptr [rax+rax+00h]
0x1800d5be1  mov     edx, eax
0x1800d5be3  lea     rcx, aWritingPageDum_0; "Writing page dump header failed, error "...
0x1800d5bea  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800d5bef  call    cs:__imp_GetLastError
0x1800d5bf6  nop     dword ptr [rax+rax+00h]
0x1800d5bfb  mov     ebx, eax
0x1800d5bfd  test    eax, eax
0x1800d5bff  jle     short loc_1800D5C0A
0x1800d5c01  movzx   ebx, ax
0x1800d5c04  or      ebx, 80070000h
0x1800d5c0a  test    ebx, ebx
0x1800d5c0c  js      loc_1800D5B48
0x1800d5c12  mov     ecx, [rbp+0B0h+var_44]
0x1800d5c15  mov     eax, 4
0x1800d5c1a  mul     rcx
0x1800d5c1d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800d5c24  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800d5c2b  cmovb   rax, rcx
0x1800d5c2f  mov     rcx, rax; unsigned __int64
0x1800d5c32  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800d5c37  mov     rsi, rax
0x1800d5c3a  test    rax, rax
0x1800d5c3d  jnz     short loc_1800D5C71
0x1800d5c3f  lea     rcx, aAllocatingPage; "Allocating page directory array failed"
0x1800d5c46  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800d5c4b  mov     ebx, 8007000Eh
0x1800d5c50  jmp     loc_1800D5B48
0x1800d5c55  cmp     [rsp+1B0h+NumberOfBytesWritten], esi
0x1800d5c59  jz      short loc_1800D5C12
0x1800d5c5b  lea     rcx, aWritingPageDum; "Writing page dump header wrote fewer by"...
0x1800d5c62  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800d5c67  mov     ebx, 8000FFFFh
0x1800d5c6c  jmp     loc_1800D5B48
0x1800d5c71  xor     ecx, ecx
0x1800d5c73  cmp     [rbp+0B0h+var_44], ecx
0x1800d5c76  jbe     short loc_1800D5C82
0x1800d5c78  mov     [rax+rcx*4], ecx
0x1800d5c7b  inc     ecx
0x1800d5c7d  cmp     ecx, [rbp+0B0h+var_44]
0x1800d5c80  jb      short loc_1800D5C78
0x1800d5c82  lea     r9, [rsp+1B0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800d5c87  mov     qword ptr [rsp+1B0h+dwCreationDisposition], 0; lpOverlapped
0x1800d5c90  mov     r8d, r14d; nNumberOfBytesToWrite
0x1800d5c93  mov     rdx, rsi; lpBuffer
0x1800d5c96  mov     rcx, rdi; hFile
0x1800d5c99  call    cs:__imp_WriteFile
0x1800d5ca0  nop     dword ptr [rax+rax+00h]
0x1800d5ca5  test    eax, eax
0x1800d5ca7  jnz     short loc_1800D5CE0
0x1800d5ca9  call    cs:__imp_GetLastError
0x1800d5cb0  nop     dword ptr [rax+rax+00h]
0x1800d5cb5  mov     edx, eax
0x1800d5cb7  lea     rcx, aWritingPageDir_0; "Writing page directory failed, error %#"...
0x1800d5cbe  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800d5cc3  call    cs:__imp_GetLastError
0x1800d5cca  nop     dword ptr [rax+rax+00h]
0x1800d5ccf  mov     ebx, eax
0x1800d5cd1  test    eax, eax
0x1800d5cd3  jle     short loc_1800D5CF8
0x1800d5cd5  movzx   ebx, ax
0x1800d5cd8  or      ebx, 80070000h
0x1800d5cde  jmp     short loc_1800D5CF8
0x1800d5ce0  cmp     [rsp+1B0h+NumberOfBytesWritten], r14d
0x1800d5ce5  jz      short loc_1800D5CF8
0x1800d5ce7  lea     rcx, aWritingPageDir; "Writing page directory wrote fewer byte"...
0x1800d5cee  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800d5cf3  mov     ebx, 8000FFFFh
0x1800d5cf8  mov     rcx, rsi; void *
0x1800d5cfb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d5d00  test    ebx, ebx
0x1800d5d02  js      loc_1800D5B48
0x1800d5d08  lea     rdx, [rsp+1B0h+Buffer]; struct _PAGEDUMP_DATA *
0x1800d5d0d  mov     rcx, rdi; hFile
0x1800d5d10  call    ?CopyPageFilesToTIF@@YAJQEAXQEAU_PAGEDUMP_DATA@@@Z; CopyPageFilesToTIF(void * const,_PAGEDUMP_DATA * const)
0x1800d5d15  mov     ebx, eax
0x1800d5d17  test    eax, eax
0x1800d5d19  js      loc_1800D5B48
0x1800d5d1f  mov     [r12], rdi
0x1800d5d23  jmp     loc_1800D5B5D
```
