# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x18000252c`
- end: `0x18000279c`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `624`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180002890`
- `0x180005b1c`
- `0x180005e3c`

## callees

- `0x1800016f0`
- `0x180002310`
- `0x18000252c`
- `0x1800039a4`

## import_xrefs

- `msvcrt!free` at `0x180002754`
- `msvcrt!free` at `0x18000275e`
- `msvcrt!free` at `0x180002754`
- `msvcrt!free` at `0x18000275e`
- `msvcrt!memcpy_s` at `0x18000266d`
- `msvcrt!memcpy_s` at `0x1800026a9`
- `msvcrt!memcpy_s` at `0x18000266d`
- `msvcrt!memcpy_s` at `0x1800026a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CExpansionVector::Add(
        ATL::CExpansionVector *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // r13
  const unsigned __int16 *v4; // r15
  ATL::CExpansionVector *v5; // r14
  __int64 v6; // rax
  size_t v7; // rax
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
      v8 = operator new(v7);
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
      v10 = operator new(saturated_mul(DestinationSize, 2u));
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
      free(v10);
      free(v19);
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
0x18000252c  mov     [rsp+arg_10], r8
0x180002531  mov     [rsp+arg_8], rdx
0x180002536  mov     [rsp+arg_0], rcx
0x18000253b  push    rbx
0x18000253c  push    rsi
0x18000253d  push    rdi
0x18000253e  push    r12
0x180002540  push    r13
0x180002542  push    r14
0x180002544  push    r15
0x180002546  sub     rsp, 40h
0x18000254a  mov     r13, r8
0x18000254d  mov     r15, rdx
0x180002550  mov     r14, rcx
0x180002553  xor     esi, esi
0x180002555  test    rdx, rdx
0x180002558  jz      loc_180002769
0x18000255e  test    r8, r8
0x180002561  jz      loc_180002769
0x180002567  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000256b  mov     rax, rbx
0x18000256e  inc     rax
0x180002571  cmp     [rdx+rax*2], si
0x180002575  jnz     short loc_18000256E
0x180002577  lea     rcx, ds:2[rax*2]
0x18000257f  mov     [rsp+78h+SourceSize], rcx
0x180002584  mov     [rsp+78h+arg_18], rsi
0x18000258c  mov     eax, 2
0x180002591  mul     rcx
0x180002594  cmovb   rax, rbx
0x180002598  mov     rcx, rax; Size
0x18000259b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800025a0  mov     r12, rax
0x1800025a3  mov     [rsp+78h+arg_18], rax
0x1800025ab  jmp     short loc_1800025D3
0x1800025ad  xor     esi, esi
0x1800025af  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800025b3  mov     r14, [rsp+78h+arg_0]
0x1800025bb  mov     r13, [rsp+78h+arg_10]
0x1800025c3  mov     r15, [rsp+78h+arg_8]
0x1800025cb  mov     r12, [rsp+78h+arg_18]
0x1800025d3  mov     rdi, r12
0x1800025d6  mov     [rsp+78h+var_48], r12
0x1800025db  mov     rcx, rbx
0x1800025de  inc     rcx
0x1800025e1  cmp     [r13+rcx*2+0], si
0x1800025e7  jnz     short loc_1800025DE
0x1800025e9  inc     ecx
0x1800025eb  movsxd  rcx, ecx
0x1800025ee  add     rcx, rcx
0x1800025f1  mov     [rsp+78h+DestinationSize], rcx
0x1800025f6  mov     [rsp+78h+var_58], rsi
0x1800025fb  mov     eax, 2
0x180002600  mul     rcx
0x180002603  cmovb   rax, rbx
0x180002607  mov     rcx, rax; Size
0x18000260a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000260f  mov     rbx, rax
0x180002612  mov     [rsp+78h+var_58], rax
0x180002617  jmp     short loc_180002645
0x180002619  xor     esi, esi
0x18000261b  mov     r14, [rsp+78h+arg_0]
0x180002623  mov     r13, [rsp+78h+arg_10]
0x18000262b  mov     r15, [rsp+78h+arg_8]
0x180002633  mov     r12, [rsp+78h+arg_18]
0x18000263b  mov     rdi, [rsp+78h+var_48]
0x180002640  mov     rbx, [rsp+78h+var_58]
0x180002645  mov     [rsp+78h+arg_8], rbx
0x18000264d  test    r12, r12
0x180002650  jz      loc_18000274E
0x180002656  test    rbx, rbx
0x180002659  jz      loc_18000274E
0x18000265f  mov     rdx, [rsp+78h+SourceSize]; DestinationSize
0x180002664  mov     r9, rdx; SourceSize
0x180002667  mov     r8, r15; Source
0x18000266a  mov     rcx, r12; Destination
0x18000266d  call    cs:__imp_memcpy_s
0x180002673  test    eax, eax
0x180002675  jz      short loc_18000269B
0x180002677  cmp     eax, 0Ch
0x18000267a  jz      loc_180002791
0x180002680  cmp     eax, 16h
0x180002683  jz      loc_180002786
0x180002689  cmp     eax, 22h ; '"'
0x18000268c  jz      loc_180002786
0x180002692  cmp     eax, 50h ; 'P'
0x180002695  jnz     loc_18000277B
0x18000269b  mov     r9, [rsp+78h+DestinationSize]; SourceSize
0x1800026a0  mov     r8, r13; Source
0x1800026a3  mov     rdx, r9; DestinationSize
0x1800026a6  mov     rcx, rbx; Destination
0x1800026a9  call    cs:__imp_memcpy_s
0x1800026af  test    eax, eax
0x1800026b1  jz      short loc_1800026D7
0x1800026b3  cmp     eax, 0Ch
0x1800026b6  jz      loc_180002791
0x1800026bc  cmp     eax, 16h
0x1800026bf  jz      loc_180002786
0x1800026c5  cmp     eax, 22h ; '"'
0x1800026c8  jz      loc_180002786
0x1800026ce  cmp     eax, 50h ; 'P'
0x1800026d1  jnz     loc_18000277B
0x1800026d7  mov     eax, [r14+10h]
0x1800026db  mov     r15d, 1
0x1800026e1  add     eax, r15d
0x1800026e4  movsxd  rdx, eax; Count
0x1800026e7  lea     r13d, [r15+7]
0x1800026eb  mov     r8d, r13d; Size
0x1800026ee  mov     rcx, [r14]; Block
0x1800026f1  call    cs:__imp__recalloc
0x1800026f7  test    rax, rax
0x1800026fa  jz      short loc_18000274E
0x1800026fc  mov     [r14], rax
0x1800026ff  mov     eax, [r14+10h]
0x180002703  add     eax, r15d
0x180002706  movsxd  rdx, eax; Count
0x180002709  mov     r8d, r13d; Size
0x18000270c  mov     rcx, [r14+8]; Block
0x180002710  call    cs:__imp__recalloc
0x180002716  test    rax, rax
0x180002719  jz      short loc_18000274E
0x18000271b  mov     [r14+8], rax
0x18000271f  movsxd  rdx, dword ptr [r14+10h]
0x180002723  mov     rax, [r14]
0x180002726  lea     rcx, [rax+rdx*8]
0x18000272a  test    rcx, rcx
0x18000272d  jz      short loc_180002732
0x18000272f  mov     [rcx], r12
0x180002732  mov     rax, [r14+8]
0x180002736  lea     rcx, [rax+rdx*8]
0x18000273a  test    rcx, rcx
0x18000273d  jz      short loc_180002742
0x18000273f  mov     [rcx], rbx
0x180002742  add     [r14+10h], r15d
0x180002746  mov     rdi, rsi
0x180002749  mov     rbx, rsi
0x18000274c  jmp     short loc_180002751
0x18000274e  mov     r15d, esi
0x180002751  mov     rcx, rbx; Block
0x180002754  call    cs:__imp_free
0x18000275a  nop
0x18000275b  mov     rcx, rdi; Block
0x18000275e  call    cs:__imp_free
0x180002764  mov     eax, r15d
0x180002767  jmp     short loc_18000276B
0x180002769  xor     eax, eax
0x18000276b  add     rsp, 40h
0x18000276f  pop     r15
0x180002771  pop     r14
0x180002773  pop     r13
0x180002775  pop     r12
0x180002777  pop     rdi
0x180002778  pop     rsi
0x180002779  pop     rbx
0x18000277a  retn
0x18000277b  mov     ecx, 80004005h; int
0x180002780  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002786  mov     ecx, 80070057h; int
0x18000278b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002791  mov     ecx, 8007000Eh; int
0x180002796  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
