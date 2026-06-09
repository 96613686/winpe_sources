# bcpWriteSeek(tagDBC *,BCPFILE *,__int64)

- ea: `0x1004b829c`
- end: `0x1004b835a`
- name: `?bcpWriteSeek@@YAFPEAUtagDBC@@PEAUBCPFILE@@_J@Z`
- size: `190`
- prototype: `__int16(struct tagDBC *, struct BCPFILE *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1004b5c74`

## callees

- `0x1004b5b5c`
- `0x1004b829c`
- `0x1005212b4`
- `0x100546a7c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1004b8302`
- `KERNEL32!GetLastError` at `0x1004b8302`
- `KERNEL32!SetFilePointer` at `0x1004b82f7`
- `KERNEL32!SetFilePointer` at `0x1004b82f7`

## pseudocode

```c
__int64 __fastcall bcpWriteSeek(struct tagDBC *a1, struct BCPFILE *a2, __int64 a3)
{
  unsigned __int16 v5; // bx
  __int64 v6; // rdx
  void *v7; // rcx
  LONG DistanceToMoveHigh; // [rsp+5Ch] [rbp+24h] BYREF

  v5 = bcpWrite(a1, a2, 0xFFFFFFFFLL, 0);
  if ( v5 )
  {
    if ( (bidGblFlags & 2) == 0 )
      return v5;
    v6 = 6947849;
    goto LABEL_4;
  }
  v7 = *(void **)a2;
  DistanceToMoveHigh = HIDWORD(a3);
  if ( SetFilePointer(v7, a3, &DistanceToMoveHigh, 0) == -1 && GetLastError() )
  {
    v5 = -1;
    *((_QWORD *)a2 + 6) = a3;
    if ( (bidGblFlags & 2) == 0 )
      return v5;
    v6 = 6958089;
LABEL_4:
    bidTraceMark(0, v6);
    goto LABEL_10;
  }
  *((_QWORD *)a2 + 6) = a3;
LABEL_10:
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned __int16)_bidx_SNACOdbc_ErrCode(0, 0x6A4409u, v5);
  return v5;
}

```

## disassembly

```asm
0x1004b829c  mov     [rsp+arg_0], rbx
0x1004b82a1  mov     [rsp+arg_8], rsi
0x1004b82a6  push    rdi
0x1004b82a7  push    r14
0x1004b82a9  push    r15
0x1004b82ab  sub     rsp, 20h
0x1004b82af  mov     rdi, r8
0x1004b82b2  mov     r15d, 0FFFFFFFFh
0x1004b82b8  mov     r8d, r15d; __int64
0x1004b82bb  xor     r9d, r9d; unsigned __int8 *
0x1004b82be  mov     rsi, rdx
0x1004b82c1  call    ?bcpWrite@@YAFPEAUtagDBC@@PEAUBCPFILE@@_JPEBE@Z; bcpWrite(tagDBC *,BCPFILE *,__int64,uchar const *)
0x1004b82c6  movzx   ebx, ax
0x1004b82c9  test    ax, ax
0x1004b82cc  jz      short loc_1004B82E5
0x1004b82ce  test    byte ptr cs:_bidGblFlags, 2
0x1004b82d5  jz      short loc_1004B8343
0x1004b82d7  mov     edx, 6A0409h
0x1004b82dc  xor     ecx, ecx
0x1004b82de  call    _bidTraceMark
0x1004b82e3  jmp     short loc_1004B8327
0x1004b82e5  mov     rcx, [rsi]; hFile
0x1004b82e8  lea     r8, [rsp+38h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x1004b82ed  xor     r9d, r9d; dwMoveMethod
0x1004b82f0  mov     [rsp+58h], rdi
0x1004b82f5  mov     edx, edi; lDistanceToMove
0x1004b82f7  call    cs:__imp_SetFilePointer
0x1004b82fd  cmp     eax, r15d
0x1004b8300  jnz     short loc_1004B8323
0x1004b8302  call    cs:__imp_GetLastError
0x1004b8308  test    eax, eax
0x1004b830a  jz      short loc_1004B8323
0x1004b830c  or      ebx, 0FFFFFFFFh
0x1004b830f  mov     [rsi+30h], rdi
0x1004b8313  test    byte ptr cs:_bidGblFlags, 2
0x1004b831a  jz      short loc_1004B8343
0x1004b831c  mov     edx, 6A2C09h
0x1004b8321  jmp     short loc_1004B82DC
0x1004b8323  mov     [rsi+30h], rdi
0x1004b8327  test    byte ptr cs:_bidGblFlags, 2
0x1004b832e  jz      short loc_1004B8343
0x1004b8330  movzx   r8d, bx; __int16
0x1004b8334  mov     edx, 6A4409h; unsigned __int64
0x1004b8339  xor     ecx, ecx; unsigned __int64
0x1004b833b  call    ?_bidx_SNACOdbc_ErrCode@@YAF_K0F@Z; _bidx_SNACOdbc_ErrCode(unsigned __int64,unsigned __int64,short)
0x1004b8340  movzx   ebx, ax
0x1004b8343  mov     rsi, [rsp+38h+arg_8]
0x1004b8348  movzx   eax, bx
0x1004b834b  mov     rbx, [rsp+38h+arg_0]
0x1004b8350  add     rsp, 20h
0x1004b8354  pop     r15
0x1004b8356  pop     r14
0x1004b8358  pop     rdi
0x1004b8359  retn
```
