# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x1800025d8`
- end: `0x180002848`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180002900`
- `0x180005074`

## callees

- `0x180001228`
- `0x180001b50`
- `0x1800025d8`
- `0x1800030b4`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180002800`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000280a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002800`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000280a`
- `msvcrt!memcpy_s` at `0x180002719`
- `msvcrt!memcpy_s` at `0x180002755`
- `msvcrt!memcpy_s` at `0x180002719`
- `msvcrt!memcpy_s` at `0x180002755`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::Add(
        ATL::CExpansionVector *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // r13
  const unsigned __int16 *v4; // r15
  ATL::CExpansionVector *v5; // r14
  __int64 v6; // rax
  unsigned __int64 v7; // rax
  void *v8; // r12
  __int64 v9; // rcx
  void *v10; // rbx
  errno_t v11; // eax
  errno_t v12; // eax
  unsigned int v13; // r15d
  void *v14; // rax
  void *v15; // rax
  __int64 v16; // rdx
  _QWORD *v17; // rcx
  _QWORD *v18; // rcx
  void *v19; // rdi
  void *v21; // [rsp+20h] [rbp-58h]
  rsize_t DestinationSize; // [rsp+28h] [rbp-50h]
  void *v24; // [rsp+30h] [rbp-48h]
  rsize_t SourceSize; // [rsp+38h] [rbp-40h]
  void *v36; // [rsp+98h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = this;
  if ( a2 && a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    SourceSize = 2 * v6 + 2;
    v7 = 2 * SourceSize;
    if ( !is_mul_ok(SourceSize, 2u) )
      v7 = -1;
    try
    {
      v8 = operator new[](v7);
      v36 = v8;
    }
    catch ( ... )
    {
      v5 = this;
      v3 = a3;
      v4 = a2;
      v8 = v36;
    }
    try
    {
      v19 = v8;
      v24 = v8;
      v9 = -1;
      do
        ++v9;
      while ( v3[v9] );
      DestinationSize = 2LL * ((int)v9 + 1);
      v10 = operator new[](saturated_mul(DestinationSize, 2u));
      v21 = v10;
    }
    catch ( ... )
    {
      v5 = this;
      v3 = a3;
      v4 = a2;
      v8 = v36;
      v19 = v24;
      v10 = v21;
    }
    if ( !v8 || !v10 )
      goto LABEL_28;
    v11 = memcpy_s(v8, SourceSize, v4, SourceSize);
    if ( v11 )
    {
      if ( v11 == 12 )
        goto LABEL_33;
      if ( v11 == 22 || v11 == 34 )
        goto LABEL_32;
      if ( v11 != 80 )
        goto LABEL_31;
    }
    v12 = memcpy_s(v10, DestinationSize, v3, DestinationSize);
    if ( !v12 )
    {
LABEL_21:
      v13 = 1;
      v14 = _recalloc(*(void **)v5, *((_DWORD *)v5 + 4) + 1, 8u);
      if ( v14 )
      {
        *(_QWORD *)v5 = v14;
        v15 = _recalloc(*((void **)v5 + 1), *((_DWORD *)v5 + 4) + 1, 8u);
        if ( v15 )
        {
          *((_QWORD *)v5 + 1) = v15;
          v16 = *((int *)v5 + 4);
          v17 = (_QWORD *)(*(_QWORD *)v5 + 8 * v16);
          if ( v17 )
            *v17 = v8;
          v18 = (_QWORD *)(*((_QWORD *)v5 + 1) + 8 * v16);
          if ( v18 )
            *v18 = v10;
          ++*((_DWORD *)v5 + 4);
          v19 = 0;
          v10 = 0;
          goto LABEL_29;
        }
      }
LABEL_28:
      v13 = 0;
LABEL_29:
      operator delete[](v10);
      operator delete[](v19);
      return v13;
    }
    if ( v12 != 12 )
    {
      if ( v12 != 22 && v12 != 34 )
      {
        if ( v12 == 80 )
          goto LABEL_21;
LABEL_31:
        ATL::AtlThrowImpl(-2147467259);
      }
LABEL_32:
      ATL::AtlThrowImpl(-2147024809);
    }
LABEL_33:
    ATL::AtlThrowImpl(-2147024882);
  }
  return 0;
}

```

## disassembly

```asm
0x1800025d8  mov     [rsp+arg_10], r8
0x1800025dd  mov     [rsp+arg_8], rdx
0x1800025e2  mov     [rsp+arg_0], rcx
0x1800025e7  push    rbx
0x1800025e8  push    rsi
0x1800025e9  push    rdi
0x1800025ea  push    r12
0x1800025ec  push    r13
0x1800025ee  push    r14
0x1800025f0  push    r15
0x1800025f2  sub     rsp, 40h
0x1800025f6  mov     r13, r8
0x1800025f9  mov     r15, rdx
0x1800025fc  mov     r14, rcx
0x1800025ff  xor     esi, esi
0x180002601  test    rdx, rdx
0x180002604  jz      loc_180002815
0x18000260a  test    r8, r8
0x18000260d  jz      loc_180002815
0x180002613  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180002617  mov     rax, rbx
0x18000261a  inc     rax
0x18000261d  cmp     [rdx+rax*2], si
0x180002621  jnz     short loc_18000261A
0x180002623  lea     rcx, ds:2[rax*2]
0x18000262b  mov     [rsp+78h+SourceSize], rcx
0x180002630  mov     [rsp+78h+arg_18], rsi
0x180002638  mov     eax, 2
0x18000263d  mul     rcx
0x180002640  cmovb   rax, rbx
0x180002644  mov     rcx, rax; unsigned __int64
0x180002647  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000264c  mov     r12, rax
0x18000264f  mov     [rsp+78h+arg_18], rax
0x180002657  jmp     short loc_18000267F
0x180002659  xor     esi, esi
0x18000265b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000265f  mov     r14, [rsp+78h+arg_0]
0x180002667  mov     r13, [rsp+78h+arg_10]
0x18000266f  mov     r15, [rsp+78h+arg_8]
0x180002677  mov     r12, [rsp+78h+arg_18]
0x18000267f  mov     rdi, r12
0x180002682  mov     [rsp+78h+var_48], r12
0x180002687  mov     rcx, rbx
0x18000268a  inc     rcx
0x18000268d  cmp     [r13+rcx*2+0], si
0x180002693  jnz     short loc_18000268A
0x180002695  inc     ecx
0x180002697  movsxd  rcx, ecx
0x18000269a  add     rcx, rcx
0x18000269d  mov     [rsp+78h+DestinationSize], rcx
0x1800026a2  mov     [rsp+78h+var_58], rsi
0x1800026a7  mov     eax, 2
0x1800026ac  mul     rcx
0x1800026af  cmovb   rax, rbx
0x1800026b3  mov     rcx, rax; unsigned __int64
0x1800026b6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800026bb  mov     rbx, rax
0x1800026be  mov     [rsp+78h+var_58], rax
0x1800026c3  jmp     short loc_1800026F1
0x1800026c5  xor     esi, esi
0x1800026c7  mov     r14, [rsp+78h+arg_0]
0x1800026cf  mov     r13, [rsp+78h+arg_10]
0x1800026d7  mov     r15, [rsp+78h+arg_8]
0x1800026df  mov     r12, [rsp+78h+arg_18]
0x1800026e7  mov     rdi, [rsp+78h+var_48]
0x1800026ec  mov     rbx, [rsp+78h+var_58]
0x1800026f1  mov     [rsp+78h+arg_8], rbx
0x1800026f9  test    r12, r12
0x1800026fc  jz      loc_1800027FA
0x180002702  test    rbx, rbx
0x180002705  jz      loc_1800027FA
0x18000270b  mov     rdx, [rsp+78h+SourceSize]; DestinationSize
0x180002710  mov     r9, rdx; SourceSize
0x180002713  mov     r8, r15; Source
0x180002716  mov     rcx, r12; Destination
0x180002719  call    cs:__imp_memcpy_s
0x18000271f  test    eax, eax
0x180002721  jz      short loc_180002747
0x180002723  cmp     eax, 0Ch
0x180002726  jz      loc_18000283D
0x18000272c  cmp     eax, 16h
0x18000272f  jz      loc_180002832
0x180002735  cmp     eax, 22h ; '"'
0x180002738  jz      loc_180002832
0x18000273e  cmp     eax, 50h ; 'P'
0x180002741  jnz     loc_180002827
0x180002747  mov     r9, [rsp+78h+DestinationSize]; SourceSize
0x18000274c  mov     r8, r13; Source
0x18000274f  mov     rdx, r9; DestinationSize
0x180002752  mov     rcx, rbx; Destination
0x180002755  call    cs:__imp_memcpy_s
0x18000275b  test    eax, eax
0x18000275d  jz      short loc_180002783
0x18000275f  cmp     eax, 0Ch
0x180002762  jz      loc_18000283D
0x180002768  cmp     eax, 16h
0x18000276b  jz      loc_180002832
0x180002771  cmp     eax, 22h ; '"'
0x180002774  jz      loc_180002832
0x18000277a  cmp     eax, 50h ; 'P'
0x18000277d  jnz     loc_180002827
0x180002783  mov     eax, [r14+10h]
0x180002787  mov     r15d, 1
0x18000278d  add     eax, r15d
0x180002790  movsxd  rdx, eax; Count
0x180002793  lea     r13d, [r15+7]
0x180002797  mov     r8d, r13d; Size
0x18000279a  mov     rcx, [r14]; Block
0x18000279d  call    cs:__imp__recalloc
0x1800027a3  test    rax, rax
0x1800027a6  jz      short loc_1800027FA
0x1800027a8  mov     [r14], rax
0x1800027ab  mov     eax, [r14+10h]
0x1800027af  add     eax, r15d
0x1800027b2  movsxd  rdx, eax; Count
0x1800027b5  mov     r8d, r13d; Size
0x1800027b8  mov     rcx, [r14+8]; Block
0x1800027bc  call    cs:__imp__recalloc
0x1800027c2  test    rax, rax
0x1800027c5  jz      short loc_1800027FA
0x1800027c7  mov     [r14+8], rax
0x1800027cb  movsxd  rdx, dword ptr [r14+10h]
0x1800027cf  mov     rax, [r14]
0x1800027d2  lea     rcx, [rax+rdx*8]
0x1800027d6  test    rcx, rcx
0x1800027d9  jz      short loc_1800027DE
0x1800027db  mov     [rcx], r12
0x1800027de  mov     rax, [r14+8]
0x1800027e2  lea     rcx, [rax+rdx*8]
0x1800027e6  test    rcx, rcx
0x1800027e9  jz      short loc_1800027EE
0x1800027eb  mov     [rcx], rbx
0x1800027ee  add     [r14+10h], r15d
0x1800027f2  mov     rdi, rsi
0x1800027f5  mov     rbx, rsi
0x1800027f8  jmp     short loc_1800027FD
0x1800027fa  mov     r15d, esi
0x1800027fd  mov     rcx, rbx
0x180002800  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180002806  nop
0x180002807  mov     rcx, rdi
0x18000280a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180002810  mov     eax, r15d
0x180002813  jmp     short loc_180002817
0x180002815  xor     eax, eax
0x180002817  add     rsp, 40h
0x18000281b  pop     r15
0x18000281d  pop     r14
0x18000281f  pop     r13
0x180002821  pop     r12
0x180002823  pop     rdi
0x180002824  pop     rsi
0x180002825  pop     rbx
0x180002826  retn
0x180002827  mov     ecx, 80004005h; int
0x18000282c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002832  mov     ecx, 80070057h; int
0x180002837  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000283d  mov     ecx, 8007000Eh; int
0x180002842  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
