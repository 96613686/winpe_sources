# bcpWrite(tagDBC *,BCPFILE *,__int64,uchar const *)

- ea: `0x1004b5b5c`
- end: `0x1004b5c6d`
- name: `?bcpWrite@@YAFPEAUtagDBC@@PEAUBCPFILE@@_JPEBE@Z`
- size: `273`
- prototype: `__int16(struct tagDBC *, struct BCPFILE *, __int64, const unsigned __int8 *)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x100499e40`
- `0x10049de40`
- `0x1004aca40`
- `0x1004aeae4`
- `0x1004b5c74`
- `0x1004b829c`

## callees

- `0x1004b5b5c`
- `0x1005212b4`
- `0x100546a7c`

## import_xrefs

- `KERNEL32!WriteFile` at `0x1004b5bb2`
- `KERNEL32!WriteFile` at `0x1004b5c00`
- `KERNEL32!WriteFile` at `0x1004b5bb2`
- `KERNEL32!WriteFile` at `0x1004b5c00`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004b5c2a`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004b5c2a`

## pseudocode

```c
__int64 __fastcall bcpWrite(struct tagDBC *a1, struct BCPFILE *a2, __int64 a3, const unsigned __int8 *a4)
{
  unsigned __int16 v4; // bx
  DWORD *v5; // rdi
  __int64 v9; // rcx
  __int64 v10; // rdx
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp+18h] BYREF

  v4 = 0;
  v5 = (DWORD *)((char *)a2 + 40);
  if ( a3 != 0xFFFFFFFFLL )
  {
    v9 = *(_QWORD *)v5;
    if ( (unsigned __int64)(*(_QWORD *)v5 + a3) <= 0x10000 )
      goto LABEL_8;
  }
  if ( !WriteFile(*(HANDLE *)a2, *((LPCVOID *)a2 + 3), *v5, &NumberOfBytesWritten, 0) )
  {
    v4 = -1;
    *(_QWORD *)v5 = 0x10000;
    if ( (bidGblFlags & 2) == 0 )
      return v4;
    v10 = 6990857;
    goto LABEL_6;
  }
  *(_QWORD *)v5 = 0;
  v9 = 0;
  if ( a3 != 0xFFFFFFFFLL )
  {
LABEL_8:
    if ( a3 <= 0x10000 )
    {
      memcpy_s((void *const)(*((_QWORD *)a2 + 3) + v9), a3, a4, a3);
      *(_QWORD *)v5 += a3;
    }
    else if ( !WriteFile(*(HANDLE *)a2, a4, a3, &NumberOfBytesWritten, 0) )
    {
      v4 = -1;
      if ( (bidGblFlags & 2) == 0 )
        return v4;
      v10 = 7011337;
LABEL_6:
      bidTraceMark(0, v10);
      goto LABEL_14;
    }
    *((_QWORD *)a2 + 6) += a3;
  }
LABEL_14:
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned __int16)_bidx_SNACOdbc_ErrCode(0, 0x6B2C09u, v4);
  return v4;
}

```

## disassembly

```asm
0x1004b5b5c  mov     [rsp+arg_0], rbx
0x1004b5b61  mov     [rsp+arg_8], rbp
0x1004b5b66  push    rsi
0x1004b5b67  push    rdi
0x1004b5b68  push    r12
0x1004b5b6a  push    r13
0x1004b5b6c  push    r14
0x1004b5b6e  sub     rsp, 30h
0x1004b5b72  xor     ebx, ebx
0x1004b5b74  lea     rdi, [rdx+28h]
0x1004b5b78  mov     r13d, 0FFFFFFFFh
0x1004b5b7e  mov     rbp, r9
0x1004b5b81  mov     rsi, r8
0x1004b5b84  mov     r14, rdx
0x1004b5b87  mov     r12d, 10000h
0x1004b5b8d  cmp     r8, r13
0x1004b5b90  jz      short loc_1004B5B9E
0x1004b5b92  mov     rcx, [rdi]
0x1004b5b95  lea     rax, [rcx+r8]
0x1004b5b99  cmp     rax, r12
0x1004b5b9c  jbe     short loc_1004B5BE8
0x1004b5b9e  mov     r8d, [rdi]; nNumberOfBytesToWrite
0x1004b5ba1  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1004b5ba6  mov     rdx, [rdx+18h]; lpBuffer
0x1004b5baa  mov     rcx, [r14]; hFile
0x1004b5bad  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x1004b5bb2  call    cs:__imp_WriteFile
0x1004b5bb8  test    eax, eax
0x1004b5bba  jnz     short loc_1004B5BDD
0x1004b5bbc  or      ebx, 0FFFFFFFFh
0x1004b5bbf  mov     [rdi], r12
0x1004b5bc2  test    byte ptr cs:_bidGblFlags, 2
0x1004b5bc9  jz      loc_1004B5C53
0x1004b5bcf  mov     edx, 6AAC09h
0x1004b5bd4  xor     ecx, ecx
0x1004b5bd6  call    _bidTraceMark
0x1004b5bdb  jmp     short loc_1004B5C37
0x1004b5bdd  mov     [rdi], rbx
0x1004b5be0  mov     rcx, rbx
0x1004b5be3  cmp     rsi, r13
0x1004b5be6  jz      short loc_1004B5C37
0x1004b5be8  cmp     rsi, r12
0x1004b5beb  jle     short loc_1004B5C1D
0x1004b5bed  mov     rcx, [r14]; hFile
0x1004b5bf0  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1004b5bf5  mov     r8d, esi; nNumberOfBytesToWrite
0x1004b5bf8  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x1004b5bfd  mov     rdx, rbp; lpBuffer
0x1004b5c00  call    cs:__imp_WriteFile
0x1004b5c06  test    eax, eax
0x1004b5c08  jnz     short loc_1004B5C33
0x1004b5c0a  or      ebx, 0FFFFFFFFh
0x1004b5c0d  test    byte ptr cs:_bidGblFlags, 2
0x1004b5c14  jz      short loc_1004B5C53
0x1004b5c16  mov     edx, 6AFC09h
0x1004b5c1b  jmp     short loc_1004B5BD4
0x1004b5c1d  add     rcx, [r14+18h]; Destination
0x1004b5c21  mov     r9, rsi; SourceSize
0x1004b5c24  mov     r8, rbp; Source
0x1004b5c27  mov     rdx, rsi; DestinationSize
0x1004b5c2a  call    cs:__imp_memcpy_s
0x1004b5c30  add     [rdi], rsi
0x1004b5c33  add     [r14+30h], rsi
0x1004b5c37  test    byte ptr cs:_bidGblFlags, 2
0x1004b5c3e  jz      short loc_1004B5C53
0x1004b5c40  movzx   r8d, bx; __int16
0x1004b5c44  mov     edx, 6B2C09h; unsigned __int64
0x1004b5c49  xor     ecx, ecx; unsigned __int64
0x1004b5c4b  call    ?_bidx_SNACOdbc_ErrCode@@YAF_K0F@Z; _bidx_SNACOdbc_ErrCode(unsigned __int64,unsigned __int64,short)
0x1004b5c50  movzx   ebx, ax
0x1004b5c53  mov     rbp, [rsp+58h+arg_8]
0x1004b5c58  movzx   eax, bx
0x1004b5c5b  mov     rbx, [rsp+58h+arg_0]
0x1004b5c60  add     rsp, 30h
0x1004b5c64  pop     r14
0x1004b5c66  pop     r13
0x1004b5c68  pop     r12
0x1004b5c6a  pop     rdi
0x1004b5c6b  pop     rsi
0x1004b5c6c  retn
```
