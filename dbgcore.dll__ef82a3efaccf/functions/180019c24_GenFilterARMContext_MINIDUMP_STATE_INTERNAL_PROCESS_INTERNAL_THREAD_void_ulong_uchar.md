# GenFilterARMContext(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,void *,ulong,uchar)

- ea: `0x180019c24`
- end: `0x180019e35`
- name: `?GenFilterARMContext@@YAJPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@PEAXKE@Z`
- size: `529`
- prototype: `__int64 __usercall@<rax>(struct _MINIDUMP_STATE *@<rcx>, struct _INTERNAL_PROCESS *@<rdx>, struct _INTERNAL_THREAD *@<r8>, void *@<r9>, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180019e3c`

## callees

- `0x1800021f4`
- `0x180016930`
- `0x180019c24`

## pseudocode

```c
__int64 __fastcall GenFilterARMContext(
        struct _MINIDUMP_STATE *a1,
        struct _INTERNAL_PROCESS *a2,
        struct _INTERNAL_THREAD *a3,
        _DWORD *a4,
        unsigned int a5,
        unsigned __int8 a6)
{
  unsigned int v10; // r14d
  int v12; // [rsp+20h] [rbp-48h]

  if ( a5 >= 0x1A0 )
  {
    v10 = 0;
    memset_0(a4 + 20, 170, 0x100u);
    if ( !a6 )
    {
      if ( a4[1] && !AddressReferenced(a1, a2, a3, (unsigned int)a4[1], v12) )
        a4[1] = -1431655766;
      if ( a4[2] && !AddressReferenced(a1, a2, a3, (unsigned int)a4[2], v12) )
        a4[2] = -1431655766;
      if ( a4[3] && !AddressReferenced(a1, a2, a3, (unsigned int)a4[3], v12) )
        a4[3] = -1431655766;
      if ( a4[4] && !AddressReferenced(a1, a2, a3, (unsigned int)a4[4], v12) )
        a4[4] = -1431655766;
      if ( a4[5] && !AddressReferenced(a1, a2, a3, (unsigned int)a4[5], v12) )
        a4[5] = -1431655766;
      if ( a4[6] && !AddressReferenced(a1, a2, a3, (unsigned int)a4[6], v12) )
        a4[6] = -1431655766;
      if ( a4[7] && !AddressReferenced(a1, a2, a3, (unsigned int)a4[7], v12) )
        a4[7] = -1431655766;
      if ( a4[8] && !AddressReferenced(a1, a2, a3, (unsigned int)a4[8], v12) )
        a4[8] = -1431655766;
      if ( a4[9] && !AddressReferenced(a1, a2, a3, (unsigned int)a4[9], v12) )
        a4[9] = -1431655766;
      if ( a4[10] && !AddressReferenced(a1, a2, a3, (unsigned int)a4[10], v12) )
        a4[10] = -1431655766;
      if ( a4[11] && !AddressReferenced(a1, a2, a3, (unsigned int)a4[11], v12) )
        a4[11] = -1431655766;
      if ( a4[12] && !AddressReferenced(a1, a2, a3, (unsigned int)a4[12], v12) )
        a4[12] = -1431655766;
      if ( a4[13] && !AddressReferenced(a1, a2, a3, (unsigned int)a4[13], v12) )
        a4[13] = -1431655766;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v10;
}

```

## disassembly

```asm
0x180019c24  push    rbx
0x180019c26  push    rbp
0x180019c27  push    rsi
0x180019c28  push    rdi
0x180019c29  push    r12
0x180019c2b  push    r14
0x180019c2d  push    r15
0x180019c2f  sub     rsp, 30h
0x180019c33  cmp     [rsp+68h+arg_20], 1A0h
0x180019c3e  mov     rbx, r9
0x180019c41  mov     rdi, r8
0x180019c44  mov     rsi, rdx
0x180019c47  mov     rbp, rcx
0x180019c4a  jnb     short loc_180019C57
0x180019c4c  mov     r14d, 80070057h
0x180019c52  jmp     loc_180019E23
0x180019c57  mov     edx, 0AAh; Val
0x180019c5c  lea     rcx, [r9+50h]; void *
0x180019c60  xor     r15d, r15d
0x180019c63  mov     r14d, r15d
0x180019c66  lea     r8d, [rdx+56h]; Size
0x180019c6a  call    memset_0
0x180019c6f  cmp     [rsp+68h+arg_28], r15b
0x180019c77  jnz     loc_180019E23
0x180019c7d  mov     r12d, 0AAAAAAAAh
0x180019c83  cmp     [rbx+4], r15d
0x180019c87  jz      short loc_180019CA3
0x180019c89  mov     r9d, [rbx+4]; unsigned __int64
0x180019c8d  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019c90  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019c93  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019c96  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019c9b  test    al, al
0x180019c9d  jnz     short loc_180019CA3
0x180019c9f  mov     [rbx+4], r12d
0x180019ca3  cmp     [rbx+8], r15d
0x180019ca7  jz      short loc_180019CC3
0x180019ca9  mov     r9d, [rbx+8]; unsigned __int64
0x180019cad  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019cb0  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019cb3  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019cb6  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019cbb  test    al, al
0x180019cbd  jnz     short loc_180019CC3
0x180019cbf  mov     [rbx+8], r12d
0x180019cc3  cmp     [rbx+0Ch], r15d
0x180019cc7  jz      short loc_180019CE3
0x180019cc9  mov     r9d, [rbx+0Ch]; unsigned __int64
0x180019ccd  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019cd0  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019cd3  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019cd6  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019cdb  test    al, al
0x180019cdd  jnz     short loc_180019CE3
0x180019cdf  mov     [rbx+0Ch], r12d
0x180019ce3  cmp     [rbx+10h], r15d
0x180019ce7  jz      short loc_180019D03
0x180019ce9  mov     r9d, [rbx+10h]; unsigned __int64
0x180019ced  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019cf0  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019cf3  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019cf6  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019cfb  test    al, al
0x180019cfd  jnz     short loc_180019D03
0x180019cff  mov     [rbx+10h], r12d
0x180019d03  cmp     [rbx+14h], r15d
0x180019d07  jz      short loc_180019D23
0x180019d09  mov     r9d, [rbx+14h]; unsigned __int64
0x180019d0d  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019d10  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019d13  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019d16  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019d1b  test    al, al
0x180019d1d  jnz     short loc_180019D23
0x180019d1f  mov     [rbx+14h], r12d
0x180019d23  cmp     [rbx+18h], r15d
0x180019d27  jz      short loc_180019D43
0x180019d29  mov     r9d, [rbx+18h]; unsigned __int64
0x180019d2d  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019d30  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019d33  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019d36  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019d3b  test    al, al
0x180019d3d  jnz     short loc_180019D43
0x180019d3f  mov     [rbx+18h], r12d
0x180019d43  cmp     [rbx+1Ch], r15d
0x180019d47  jz      short loc_180019D63
0x180019d49  mov     r9d, [rbx+1Ch]; unsigned __int64
0x180019d4d  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019d50  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019d53  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019d56  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019d5b  test    al, al
0x180019d5d  jnz     short loc_180019D63
0x180019d5f  mov     [rbx+1Ch], r12d
0x180019d63  cmp     [rbx+20h], r15d
0x180019d67  jz      short loc_180019D83
0x180019d69  mov     r9d, [rbx+20h]; unsigned __int64
0x180019d6d  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019d70  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019d73  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019d76  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019d7b  test    al, al
0x180019d7d  jnz     short loc_180019D83
0x180019d7f  mov     [rbx+20h], r12d
0x180019d83  cmp     [rbx+24h], r15d
0x180019d87  jz      short loc_180019DA3
0x180019d89  mov     r9d, [rbx+24h]; unsigned __int64
0x180019d8d  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019d90  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019d93  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019d96  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019d9b  test    al, al
0x180019d9d  jnz     short loc_180019DA3
0x180019d9f  mov     [rbx+24h], r12d
0x180019da3  cmp     [rbx+28h], r15d
0x180019da7  jz      short loc_180019DC3
0x180019da9  mov     r9d, [rbx+28h]; unsigned __int64
0x180019dad  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019db0  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019db3  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019db6  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019dbb  test    al, al
0x180019dbd  jnz     short loc_180019DC3
0x180019dbf  mov     [rbx+28h], r12d
0x180019dc3  cmp     [rbx+2Ch], r15d
0x180019dc7  jz      short loc_180019DE3
0x180019dc9  mov     r9d, [rbx+2Ch]; unsigned __int64
0x180019dcd  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019dd0  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019dd3  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019dd6  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019ddb  test    al, al
0x180019ddd  jnz     short loc_180019DE3
0x180019ddf  mov     [rbx+2Ch], r12d
0x180019de3  cmp     [rbx+30h], r15d
0x180019de7  jz      short loc_180019E03
0x180019de9  mov     r9d, [rbx+30h]; unsigned __int64
0x180019ded  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019df0  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019df3  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019df6  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019dfb  test    al, al
0x180019dfd  jnz     short loc_180019E03
0x180019dff  mov     [rbx+30h], r12d
0x180019e03  cmp     [rbx+34h], r15d
0x180019e07  jz      short loc_180019E23
0x180019e09  mov     r9d, [rbx+34h]; unsigned __int64
0x180019e0d  mov     r8, rdi; struct _INTERNAL_THREAD *
0x180019e10  mov     rdx, rsi; struct _INTERNAL_PROCESS *
0x180019e13  mov     rcx, rbp; struct _MINIDUMP_STATE *
0x180019e16  call    ?AddressReferenced@@YAEPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@PEAU_INTERNAL_THREAD@@_KEE@Z; AddressReferenced(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,_INTERNAL_THREAD *,unsigned __int64,uchar,uchar)
0x180019e1b  test    al, al
0x180019e1d  jnz     short loc_180019E23
0x180019e1f  mov     [rbx+34h], r12d
0x180019e23  mov     eax, r14d
0x180019e26  add     rsp, 30h
0x180019e2a  pop     r15
0x180019e2c  pop     r14
0x180019e2e  pop     r12
0x180019e30  pop     rdi
0x180019e31  pop     rsi
0x180019e32  pop     rbp
0x180019e33  pop     rbx
0x180019e34  retn
```
