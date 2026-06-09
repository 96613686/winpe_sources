# CMemFileReader::Read(ulong,void *)

- ea: `0x18012a4e0`
- end: `0x18012a776`
- name: `?Read@CMemFileReader@@UEAAJKPEAX@Z`
- size: `662`
- prototype: `int(CMemFileReader *__hidden this, unsigned int, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180003d80`
- `0x180129c30`
- `0x18012a4e0`
- `0x1801a65e1`
- `0x1801a65f0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18012a638`
- `KERNEL32!GetLastError` at `0x18012a734`
- `KERNEL32!GetLastError` at `0x18012a638`
- `KERNEL32!GetLastError` at `0x18012a734`
- `KERNEL32!UnmapViewOfFile` at `0x18012a624`
- `KERNEL32!UnmapViewOfFile` at `0x18012a624`
- `KERNEL32!MapViewOfFile` at `0x18012a697`
- `KERNEL32!MapViewOfFile` at `0x18012a697`
- `KERNEL32!ReadFile` at `0x18012a72a`
- `KERNEL32!ReadFile` at `0x18012a72a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18012a582`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18012a5ab`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18012a5e5`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18012a5f8`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18012a582`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18012a5ab`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18012a5e5`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18012a5f8`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18012a58e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18012a604`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18012a58e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18012a604`

## pseudocode

```c
__int64 __fastcall CMemFileReader::Read(CMemFileReader *this, DWORD a2, char *a3)
{
  char *v3; // r14
  unsigned int v4; // r13d
  unsigned int v6; // edi
  unsigned int v7; // eax
  unsigned __int64 v8; // r12
  __int64 v9; // r15
  signed int LastError; // eax
  __int64 v11; // r9
  __int64 v12; // rcx
  unsigned int v13; // ecx
  LPVOID v14; // rax
  void *v15; // rcx
  signed int v16; // eax
  DWORD NumberOfBytesRead; // [rsp+50h] [rbp-48h] BYREF

  v3 = a3;
  v4 = a2;
  v6 = 0;
  if ( *((_DWORD *)this + 8) )
  {
    if ( !a3 )
      return (unsigned int)-2147024809;
    if ( (signed __int64)(*((_QWORD *)this + 7) + a2) > *((_QWORD *)this + 2) )
      return (unsigned int)-2147221300;
    v7 = *((_DWORD *)this + 18);
    v8 = *((_DWORD *)this + 19) - v7;
    while ( 1 )
    {
      NumberOfBytesRead = v8;
      v9 = *((_QWORD *)this + 6) + v7;
      if ( (unsigned int)v8 >= v4 )
      {
        if ( v4 )
        {
          if ( v3 )
          {
            if ( v9 )
            {
              memcpy_0(v3, (const void *)(*((_QWORD *)this + 6) + v7), v4);
              goto LABEL_14;
            }
            memset_0(v3, 0, v4);
          }
          *_errno() = 22;
          _invalid_parameter_noinfo();
        }
LABEL_14:
        *((_QWORD *)this + 7) += v4;
        *((_DWORD *)this + 18) += v4;
        return v6;
      }
      if ( v8 )
      {
        if ( !v3 )
          goto LABEL_17;
        if ( v9 && v4 >= v8 )
        {
          memcpy_0(v3, (const void *)(*((_QWORD *)this + 6) + v7), v8);
          goto LABEL_25;
        }
        memset_0(v3, 0, v4);
        if ( v9 )
        {
          if ( v4 >= v8 )
            goto LABEL_25;
          *_errno() = 34;
        }
        else
        {
LABEL_17:
          *_errno() = 22;
        }
        _invalid_parameter_noinfo();
      }
LABEL_25:
      v4 -= NumberOfBytesRead;
      *((_QWORD *)this + 7) += v8;
      v3 += v8;
      if ( !UnmapViewOfFile(*((LPCVOID *)this + 6)) )
      {
        CMemFileReader::HandleMappingFailure(this, 0);
        LastError = GetLastError();
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
        return (unsigned int)LastError;
      }
      v11 = *((_QWORD *)this + 8) + *((unsigned int *)this + 19);
      *((_QWORD *)this + 8) = v11;
      v12 = *((_QWORD *)this + 2);
      if ( v12 - v11 <= 0x100000 )
        v13 = v12 - v11;
      else
        v13 = 0x100000;
      *((_DWORD *)this + 19) = v13;
      v14 = MapViewOfFile(*((HANDLE *)this + 5), 4u, HIDWORD(v11), v11, v13);
      *((_QWORD *)this + 6) = v14;
      if ( !v14 )
      {
        (*(void (__fastcall **)(CMemFileReader *))(*(_QWORD *)this + 56LL))(this);
        *((_DWORD *)this + 6) = 0;
        return (unsigned int)-2147221299;
      }
      *((_DWORD *)this + 18) = 0;
      v8 = *((unsigned int *)this + 19);
      v7 = 0;
    }
  }
  NumberOfBytesRead = 0;
  if ( !a3 )
    return (unsigned int)-2147024809;
  v15 = (void *)*((_QWORD *)this + 1);
  if ( v15 == (void *)-1LL )
  {
    return (unsigned int)-2147221301;
  }
  else if ( ReadFile(v15, a3, a2, &NumberOfBytesRead, 0) )
  {
    if ( !NumberOfBytesRead )
      return (unsigned int)-2147221300;
  }
  else
  {
    v16 = GetLastError();
    v6 = v16;
    if ( v16 > 0 )
      return (unsigned __int16)v16 | 0x80070000;
  }
  return v6;
}

```

## disassembly

```asm
0x18012a4e0  push    rbx
0x18012a4e2  push    rsi
0x18012a4e3  push    rdi
0x18012a4e4  push    r12
0x18012a4e6  push    r13
0x18012a4e8  push    r14
0x18012a4ea  push    r15
0x18012a4ec  sub     rsp, 60h
0x18012a4f0  mov     rax, cs:__security_cookie
0x18012a4f7  xor     rax, rsp
0x18012a4fa  mov     [rsp+98h+var_40], rax
0x18012a4ff  mov     r14, r8
0x18012a502  mov     r13d, edx
0x18012a505  mov     rbx, rcx
0x18012a508  mov     [rsp+98h+var_58], rcx
0x18012a50d  xor     edi, edi
0x18012a50f  cmp     [rcx+20h], edi
0x18012a512  jz      loc_18012A6FC
0x18012a518  test    r8, r8
0x18012a51b  jnz     short loc_18012A527
0x18012a51d  mov     edi, 80070057h
0x18012a522  jmp     loc_18012A757
0x18012a527  mov     rax, r13
0x18012a52a  add     rax, [rcx+38h]
0x18012a52e  cmp     rax, [rcx+10h]
0x18012a532  jle     short loc_18012A53E
0x18012a534  mov     edi, 800400CCh
0x18012a539  jmp     loc_18012A757
0x18012a53e  mov     eax, [rcx+48h]
0x18012a541  mov     r12d, [rcx+4Ch]
0x18012a545  sub     r12d, eax
0x18012a548  mov     [rsp+98h+NumberOfBytesRead], r12d
0x18012a54d  mov     esi, r13d
0x18012a550  mov     r15d, eax
0x18012a553  add     r15, [rbx+30h]
0x18012a557  cmp     r12d, r13d
0x18012a55a  jb      short loc_18012A5A1
0x18012a55c  test    r13d, r13d
0x18012a55f  jz      short loc_18012A594
0x18012a561  test    r14, r14
0x18012a564  jz      short loc_18012A582
0x18012a566  mov     r8d, esi; Size
0x18012a569  mov     rcx, r14; void *
0x18012a56c  test    r15, r15
0x18012a56f  jz      short loc_18012A57B
0x18012a571  mov     rdx, r15; Src
0x18012a574  call    memcpy_0
0x18012a579  jmp     short loc_18012A594
0x18012a57b  xor     edx, edx; Val
0x18012a57d  call    memset_0
0x18012a582  call    cs:__imp__errno
0x18012a588  mov     dword ptr [rax], 16h
0x18012a58e  call    cs:__imp__invalid_parameter_noinfo
0x18012a594  add     [rbx+38h], rsi
0x18012a598  add     [rbx+48h], r13d
0x18012a59c  jmp     loc_18012A757
0x18012a5a1  test    r12, r12
0x18012a5a4  jz      short loc_18012A60A
0x18012a5a6  test    r14, r14
0x18012a5a9  jnz     short loc_18012A5B9
0x18012a5ab  call    cs:__imp__errno
0x18012a5b1  mov     dword ptr [rax], 16h
0x18012a5b7  jmp     short loc_18012A604
0x18012a5b9  test    r15, r15
0x18012a5bc  jz      short loc_18012A5D3
0x18012a5be  cmp     rsi, r12
0x18012a5c1  jb      short loc_18012A5D3
0x18012a5c3  mov     r8, r12; Size
0x18012a5c6  mov     rdx, r15; Src
0x18012a5c9  mov     rcx, r14; void *
0x18012a5cc  call    memcpy_0
0x18012a5d1  jmp     short loc_18012A60A
0x18012a5d3  mov     r8, rsi; Size
0x18012a5d6  xor     edx, edx; Val
0x18012a5d8  mov     rcx, r14; void *
0x18012a5db  call    memset_0
0x18012a5e0  test    r15, r15
0x18012a5e3  jnz     short loc_18012A5F3
0x18012a5e5  call    cs:__imp__errno
0x18012a5eb  mov     dword ptr [rax], 16h
0x18012a5f1  jmp     short loc_18012A604
0x18012a5f3  cmp     rsi, r12
0x18012a5f6  jnb     short loc_18012A60A
0x18012a5f8  call    cs:__imp__errno
0x18012a5fe  mov     dword ptr [rax], 22h ; '"'
0x18012a604  call    cs:__imp__invalid_parameter_noinfo
0x18012a60a  sub     r13d, [rsp+98h+NumberOfBytesRead]
0x18012a60f  mov     [rsp+98h+var_60], r13d
0x18012a614  add     [rbx+38h], r12
0x18012a618  add     r14, r12
0x18012a61b  mov     [rsp+98h+var_50], r14
0x18012a620  mov     rcx, [rbx+30h]; lpBaseAddress
0x18012a624  call    cs:__imp_UnmapViewOfFile
0x18012a62a  test    eax, eax
0x18012a62c  jnz     short loc_18012A655
0x18012a62e  xor     edx, edx
0x18012a630  mov     rcx, rbx
0x18012a633  call    ?HandleMappingFailure@CMemFileReader@@IEAAXW4EMappingFailureRead@@@Z; CMemFileReader::HandleMappingFailure(EMappingFailureRead)
0x18012a638  call    cs:__imp_GetLastError
0x18012a63e  test    eax, eax
0x18012a640  jle     short loc_18012A64A
0x18012a642  movzx   eax, ax
0x18012a645  or      eax, 80070000h
0x18012a64a  mov     edi, eax
0x18012a64c  mov     [rsp+98h+var_68], eax
0x18012a650  jmp     loc_18012A757
0x18012a655  mov     r9d, [rbx+4Ch]
0x18012a659  add     r9, [rbx+40h]; dwFileOffsetLow
0x18012a65d  mov     [rbx+40h], r9
0x18012a661  mov     r8, r9
0x18012a664  shr     r8, 20h; dwFileOffsetHigh
0x18012a668  mov     rcx, [rbx+10h]
0x18012a66c  mov     rax, rcx
0x18012a66f  sub     rax, r9
0x18012a672  cmp     rax, 100000h
0x18012a678  jle     short loc_18012A681
0x18012a67a  mov     ecx, 100000h
0x18012a67f  jmp     short loc_18012A684
0x18012a681  sub     ecx, r9d
0x18012a684  mov     [rbx+4Ch], ecx
0x18012a687  mov     eax, ecx
0x18012a689  mov     [rsp+98h+dwNumberOfBytesToMap], rax; dwNumberOfBytesToMap
0x18012a68e  mov     edx, 4; dwDesiredAccess
0x18012a693  mov     rcx, [rbx+28h]; hFileMappingObject
0x18012a697  call    cs:__imp_MapViewOfFile
0x18012a69d  mov     [rbx+30h], rax
0x18012a6a1  test    rax, rax
0x18012a6a4  jnz     short loc_18012A6C7
0x18012a6a6  mov     rax, [rbx]
0x18012a6a9  mov     rcx, rbx
0x18012a6ac  mov     rax, [rax+38h]
0x18012a6b0  call    cs:__guard_dispatch_icall_fptr
0x18012a6b6  mov     [rbx+18h], edi
0x18012a6b9  mov     edi, 800400CDh
0x18012a6be  mov     [rsp+98h+var_68], edi
0x18012a6c2  jmp     loc_18012A757
0x18012a6c7  mov     [rbx+48h], edi
0x18012a6ca  mov     r12d, [rbx+4Ch]
0x18012a6ce  mov     eax, edi
0x18012a6d0  jmp     loc_18012A548
0x18012a6d5  mov     rbx, [rsp+98h+var_58]
0x18012a6da  mov     rax, [rbx]
0x18012a6dd  mov     rcx, rbx
0x18012a6e0  mov     rax, [rax+38h]
0x18012a6e4  call    cs:__guard_dispatch_icall_fptr
0x18012a6ea  mov     dword ptr [rbx+18h], 0
0x18012a6f1  mov     edi, 800400CDh
0x18012a6f6  mov     [rsp+98h+var_68], edi
0x18012a6fa  jmp     short loc_18012A757
0x18012a6fc  mov     [rsp+98h+NumberOfBytesRead], edi
0x18012a700  test    r14, r14
0x18012a703  jz      loc_18012A51D
0x18012a709  mov     rcx, [rcx+8]; hFile
0x18012a70d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18012a711  jnz     short loc_18012A71A
0x18012a713  mov     edi, 800400CBh
0x18012a718  jmp     short loc_18012A757
0x18012a71a  mov     [rsp+98h+dwNumberOfBytesToMap], rdi; lpOverlapped
0x18012a71f  lea     r9, [rsp+98h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18012a724  mov     r8d, r13d; nNumberOfBytesToRead
0x18012a727  mov     rdx, r14; lpBuffer
0x18012a72a  call    cs:__imp_ReadFile
0x18012a730  test    eax, eax
0x18012a732  jnz     short loc_18012A74B
0x18012a734  call    cs:__imp_GetLastError
0x18012a73a  mov     edi, eax
0x18012a73c  test    eax, eax
0x18012a73e  jle     short loc_18012A757
0x18012a740  movzx   edi, ax
0x18012a743  or      edi, 80070000h
0x18012a749  jmp     short loc_18012A757
0x18012a74b  mov     eax, 800400CCh
0x18012a750  cmp     [rsp+98h+NumberOfBytesRead], edi
0x18012a754  cmovz   edi, eax
0x18012a757  mov     eax, edi
0x18012a759  mov     rcx, [rsp+98h+var_40]
0x18012a75e  xor     rcx, rsp; StackCookie
0x18012a761  call    __security_check_cookie
0x18012a766  add     rsp, 60h
0x18012a76a  pop     r15
0x18012a76c  pop     r14
0x18012a76e  pop     r13
0x18012a770  pop     r12
0x18012a772  pop     rdi
0x18012a773  pop     rsi
0x18012a774  pop     rbx
0x18012a775  retn
```
