# CopyPageFilesToTIF(void * const,_PAGEDUMP_DATA * const)

- ea: `0x1800e0b50`
- end: `0x1800e0cf2`
- name: `?CopyPageFilesToTIF@@YAJQEAXQEAU_PAGEDUMP_DATA@@@Z`
- size: `418`
- prototype: `__int64 __fastcall(HANDLE hFile, struct _PAGEDUMP_DATA *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800d5a44`

## callees

- `0x1800727b8`
- `0x1800793cc`
- `0x1800e0b50`
- `0x1800f13ec`
- `0x1800f1720`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0bfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0c4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0c64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0bfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0c4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e0c64`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800e0c3a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800e0c3a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800e0bee`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800e0bee`

## string_xrefs

- `0x1800e0c0a`: `Reading pagefile data failed, error %#x\n`
- `0x1800e0cb2`: `Reading pagefile data returned fewer bytes than expected`
- `0x1800e0ccd`: `Allocating copy buffer failed`

## pseudocode

```c
__int64 __fastcall CopyPageFilesToTIF(HANDLE hFile, struct _PAGEDUMP_DATA *const a2)
{
  const struct std::nothrow_t *v4; // rdx
  void *v5; // rbp
  signed int v6; // ebx
  unsigned int v7; // edi
  unsigned int v8; // r15d
  __int64 v9; // r12
  unsigned __int64 v10; // rsi
  DWORD v11; // edi
  void *v12; // rcx
  DWORD v13; // eax
  DWORD LastError; // eax
  signed int v15; // eax
  DWORD NumberOfBytesRead; // [rsp+90h] [rbp+18h] BYREF

  v5 = operator new[](0x100000u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v5 )
  {
    v6 = 0;
    v7 = 0;
LABEL_3:
    if ( v7 < *((_DWORD *)a2 + 70) )
    {
      v8 = v7 + 1;
      dprintf(L"Adding pagefile %u of %u...\n", v7 + 1);
      v9 = v7;
      v10 = (unsigned int)(*((_DWORD *)a2 + 2 * v7 + 5) << 12);
      while ( 1 )
      {
        v11 = 0x100000;
        if ( v10 <= 0x100000 )
          v11 = v10;
        v12 = (void *)*((_QWORD *)a2 + v9 + 19);
        NumberOfBytesRead = 0;
        if ( !ReadFile(v12, v5, v11, &NumberOfBytesRead, 0) )
          break;
        if ( NumberOfBytesRead != v11 )
        {
          ErrOut(L"Reading pagefile data returned fewer bytes than expected");
          goto LABEL_22;
        }
        if ( !WriteFile(hFile, v5, v11, &NumberOfBytesRead, 0) )
        {
          LastError = GetLastError();
          ErrOut(L"Writing page dump data failed, error %#x\n", LastError);
LABEL_12:
          v15 = GetLastError();
          v6 = v15;
          if ( v15 > 0 )
            v6 = (unsigned __int16)v15 | 0x80070000;
          goto LABEL_16;
        }
        if ( NumberOfBytesRead != v11 )
        {
          ErrOut(L"Writing pagefile data wrote fewer bytes than expected");
LABEL_22:
          v6 = -2147418113;
          goto LABEL_23;
        }
        v10 -= v11;
LABEL_16:
        if ( v6 < 0 || !v10 )
        {
          v7 = v8;
          if ( v6 >= 0 )
            goto LABEL_3;
          goto LABEL_23;
        }
      }
      v13 = GetLastError();
      ErrOut(L"Reading pagefile data failed, error %#x\n", v13);
      goto LABEL_12;
    }
LABEL_23:
    operator delete(v5, v4);
  }
  else
  {
    ErrOut(L"Allocating copy buffer failed");
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800e0b50  push    rbx
0x1800e0b52  push    rbp
0x1800e0b53  push    rsi
0x1800e0b54  push    rdi
0x1800e0b55  push    r12
0x1800e0b57  push    r13
0x1800e0b59  push    r14
0x1800e0b5b  push    r15
0x1800e0b5d  sub     rsp, 38h
0x1800e0b61  mov     r14, rdx
0x1800e0b64  mov     r13, rcx
0x1800e0b67  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800e0b6e  mov     ecx, 100000h; unsigned __int64
0x1800e0b73  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800e0b78  mov     rbp, rax
0x1800e0b7b  test    rax, rax
0x1800e0b7e  jz      loc_1800E0CCD
0x1800e0b84  xor     ebx, ebx
0x1800e0b86  xor     edi, edi
0x1800e0b88  mov     r8d, [r14+118h]
0x1800e0b8f  cmp     edi, r8d
0x1800e0b92  jnb     loc_1800E0CC3
0x1800e0b98  lea     r15d, [rdi+1]
0x1800e0b9c  mov     edx, r15d
0x1800e0b9f  lea     rcx, aAddingPagefile; "Adding pagefile %u of %u...\n"
0x1800e0ba6  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1800e0bab  mov     r12d, edi
0x1800e0bae  mov     esi, [r14+r12*8+14h]
0x1800e0bb3  shl     esi, 0Ch
0x1800e0bb6  mov     eax, 100000h
0x1800e0bbb  mov     edi, eax
0x1800e0bbd  cmp     rsi, rax
0x1800e0bc0  ja      short loc_1800E0BC4
0x1800e0bc2  mov     edi, esi
0x1800e0bc4  mov     rcx, [r14+r12*8+98h]; hFile
0x1800e0bcc  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800e0bd4  mov     r8d, edi; nNumberOfBytesToRead
0x1800e0bd7  mov     [rsp+78h+NumberOfBytesRead], 0
0x1800e0be2  mov     rdx, rbp; lpBuffer
0x1800e0be5  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800e0bee  call    cs:__imp_ReadFile
0x1800e0bf5  nop     dword ptr [rax+rax+00h]
0x1800e0bfa  test    eax, eax
0x1800e0bfc  jnz     short loc_1800E0C13
0x1800e0bfe  call    cs:__imp_GetLastError
0x1800e0c05  nop     dword ptr [rax+rax+00h]
0x1800e0c0a  lea     rcx, aReadingPagefil; "Reading pagefile data failed, error %#x"...
0x1800e0c11  jmp     short loc_1800E0C5D
0x1800e0c13  cmp     [rsp+78h+NumberOfBytesRead], edi
0x1800e0c1a  jnz     loc_1800E0CB2
0x1800e0c20  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesWritten
0x1800e0c28  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x1800e0c31  mov     r8d, edi; nNumberOfBytesToWrite
0x1800e0c34  mov     rdx, rbp; lpBuffer
0x1800e0c37  mov     rcx, r13; hFile
0x1800e0c3a  call    cs:__imp_WriteFile
0x1800e0c41  nop     dword ptr [rax+rax+00h]
0x1800e0c46  test    eax, eax
0x1800e0c48  jnz     short loc_1800E0C81
0x1800e0c4a  call    cs:__imp_GetLastError
0x1800e0c51  nop     dword ptr [rax+rax+00h]
0x1800e0c56  lea     rcx, aWritingPageDum_1; "Writing page dump data failed, error %#"...
0x1800e0c5d  mov     edx, eax
0x1800e0c5f  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800e0c64  call    cs:__imp_GetLastError
0x1800e0c6b  nop     dword ptr [rax+rax+00h]
0x1800e0c70  mov     ebx, eax
0x1800e0c72  test    eax, eax
0x1800e0c74  jle     short loc_1800E0C8F
0x1800e0c76  movzx   ebx, ax
0x1800e0c79  or      ebx, 80070000h
0x1800e0c7f  jmp     short loc_1800E0C8F
0x1800e0c81  cmp     [rsp+78h+NumberOfBytesRead], edi
0x1800e0c88  jnz     short loc_1800E0CA9
0x1800e0c8a  mov     eax, edi
0x1800e0c8c  sub     rsi, rax
0x1800e0c8f  test    ebx, ebx
0x1800e0c91  js      short loc_1800E0C9C
0x1800e0c93  test    rsi, rsi
0x1800e0c96  jnz     loc_1800E0BB6
0x1800e0c9c  mov     edi, r15d
0x1800e0c9f  test    ebx, ebx
0x1800e0ca1  jns     loc_1800E0B88
0x1800e0ca7  jmp     short loc_1800E0CC3
0x1800e0ca9  lea     rcx, aWritingPagefil; "Writing pagefile data wrote fewer bytes"...
0x1800e0cb0  jmp     short loc_1800E0CB9
0x1800e0cb2  lea     rcx, aReadingPagefil_0; "Reading pagefile data returned fewer by"...
0x1800e0cb9  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800e0cbe  mov     ebx, 8000FFFFh
0x1800e0cc3  mov     rcx, rbp; void *
0x1800e0cc6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e0ccb  jmp     short loc_1800E0CDE
0x1800e0ccd  lea     rcx, aAllocatingCopy; "Allocating copy buffer failed"
0x1800e0cd4  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800e0cd9  mov     ebx, 8007000Eh
0x1800e0cde  mov     eax, ebx
0x1800e0ce0  add     rsp, 38h
0x1800e0ce4  pop     r15
0x1800e0ce6  pop     r14
0x1800e0ce8  pop     r13
0x1800e0cea  pop     r12
0x1800e0cec  pop     rdi
0x1800e0ced  pop     rsi
0x1800e0cee  pop     rbp
0x1800e0cef  pop     rbx
0x1800e0cf0  retn
```
