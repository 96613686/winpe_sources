# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x180003414`
- end: `0x180003684`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003740`
- `0x180006164`

## callees

- `0x180001170`
- `0x180001c40`
- `0x18000278c`
- `0x180003414`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180003555`
- `msvcrt!memcpy_s` at `0x180003591`
- `msvcrt!memcpy_s` at `0x180003555`
- `msvcrt!memcpy_s` at `0x180003591`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000363c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003646`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000363c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003646`

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
0x180003414  mov     [rsp+arg_10], r8
0x180003419  mov     [rsp+arg_8], rdx
0x18000341e  mov     [rsp+arg_0], rcx
0x180003423  push    rbx
0x180003424  push    rsi
0x180003425  push    rdi
0x180003426  push    r12
0x180003428  push    r13
0x18000342a  push    r14
0x18000342c  push    r15
0x18000342e  sub     rsp, 40h
0x180003432  mov     r13, r8
0x180003435  mov     r15, rdx
0x180003438  mov     r14, rcx
0x18000343b  xor     esi, esi
0x18000343d  test    rdx, rdx
0x180003440  jz      loc_180003651
0x180003446  test    r8, r8
0x180003449  jz      loc_180003651
0x18000344f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003453  mov     rax, rbx
0x180003456  inc     rax
0x180003459  cmp     [rdx+rax*2], si
0x18000345d  jnz     short loc_180003456
0x18000345f  lea     rcx, ds:2[rax*2]
0x180003467  mov     [rsp+78h+SourceSize], rcx
0x18000346c  mov     [rsp+78h+arg_18], rsi
0x180003474  mov     eax, 2
0x180003479  mul     rcx
0x18000347c  cmovb   rax, rbx
0x180003480  mov     rcx, rax; unsigned __int64
0x180003483  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003488  mov     r12, rax
0x18000348b  mov     [rsp+78h+arg_18], rax
0x180003493  jmp     short loc_1800034BB
0x180003495  xor     esi, esi
0x180003497  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000349b  mov     r14, [rsp+78h+arg_0]
0x1800034a3  mov     r13, [rsp+78h+arg_10]
0x1800034ab  mov     r15, [rsp+78h+arg_8]
0x1800034b3  mov     r12, [rsp+78h+arg_18]
0x1800034bb  mov     rdi, r12
0x1800034be  mov     [rsp+78h+var_48], r12
0x1800034c3  mov     rcx, rbx
0x1800034c6  inc     rcx
0x1800034c9  cmp     [r13+rcx*2+0], si
0x1800034cf  jnz     short loc_1800034C6
0x1800034d1  inc     ecx
0x1800034d3  movsxd  rcx, ecx
0x1800034d6  add     rcx, rcx
0x1800034d9  mov     [rsp+78h+DestinationSize], rcx
0x1800034de  mov     [rsp+78h+var_58], rsi
0x1800034e3  mov     eax, 2
0x1800034e8  mul     rcx
0x1800034eb  cmovb   rax, rbx
0x1800034ef  mov     rcx, rax; unsigned __int64
0x1800034f2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800034f7  mov     rbx, rax
0x1800034fa  mov     [rsp+78h+var_58], rax
0x1800034ff  jmp     short loc_18000352D
0x180003501  xor     esi, esi
0x180003503  mov     r14, [rsp+78h+arg_0]
0x18000350b  mov     r13, [rsp+78h+arg_10]
0x180003513  mov     r15, [rsp+78h+arg_8]
0x18000351b  mov     r12, [rsp+78h+arg_18]
0x180003523  mov     rdi, [rsp+78h+var_48]
0x180003528  mov     rbx, [rsp+78h+var_58]
0x18000352d  mov     [rsp+78h+arg_8], rbx
0x180003535  test    r12, r12
0x180003538  jz      loc_180003636
0x18000353e  test    rbx, rbx
0x180003541  jz      loc_180003636
0x180003547  mov     rdx, [rsp+78h+SourceSize]; DestinationSize
0x18000354c  mov     r9, rdx; SourceSize
0x18000354f  mov     r8, r15; Source
0x180003552  mov     rcx, r12; Destination
0x180003555  call    cs:__imp_memcpy_s
0x18000355b  test    eax, eax
0x18000355d  jz      short loc_180003583
0x18000355f  cmp     eax, 0Ch
0x180003562  jz      loc_180003679
0x180003568  cmp     eax, 16h
0x18000356b  jz      loc_18000366E
0x180003571  cmp     eax, 22h ; '"'
0x180003574  jz      loc_18000366E
0x18000357a  cmp     eax, 50h ; 'P'
0x18000357d  jnz     loc_180003663
0x180003583  mov     r9, [rsp+78h+DestinationSize]; SourceSize
0x180003588  mov     r8, r13; Source
0x18000358b  mov     rdx, r9; DestinationSize
0x18000358e  mov     rcx, rbx; Destination
0x180003591  call    cs:__imp_memcpy_s
0x180003597  test    eax, eax
0x180003599  jz      short loc_1800035BF
0x18000359b  cmp     eax, 0Ch
0x18000359e  jz      loc_180003679
0x1800035a4  cmp     eax, 16h
0x1800035a7  jz      loc_18000366E
0x1800035ad  cmp     eax, 22h ; '"'
0x1800035b0  jz      loc_18000366E
0x1800035b6  cmp     eax, 50h ; 'P'
0x1800035b9  jnz     loc_180003663
0x1800035bf  mov     eax, [r14+10h]
0x1800035c3  mov     r15d, 1
0x1800035c9  add     eax, r15d
0x1800035cc  movsxd  rdx, eax; Count
0x1800035cf  lea     r13d, [r15+7]
0x1800035d3  mov     r8d, r13d; Size
0x1800035d6  mov     rcx, [r14]; Block
0x1800035d9  call    cs:__imp__recalloc
0x1800035df  test    rax, rax
0x1800035e2  jz      short loc_180003636
0x1800035e4  mov     [r14], rax
0x1800035e7  mov     eax, [r14+10h]
0x1800035eb  add     eax, r15d
0x1800035ee  movsxd  rdx, eax; Count
0x1800035f1  mov     r8d, r13d; Size
0x1800035f4  mov     rcx, [r14+8]; Block
0x1800035f8  call    cs:__imp__recalloc
0x1800035fe  test    rax, rax
0x180003601  jz      short loc_180003636
0x180003603  mov     [r14+8], rax
0x180003607  movsxd  rdx, dword ptr [r14+10h]
0x18000360b  mov     rax, [r14]
0x18000360e  lea     rcx, [rax+rdx*8]
0x180003612  test    rcx, rcx
0x180003615  jz      short loc_18000361A
0x180003617  mov     [rcx], r12
0x18000361a  mov     rax, [r14+8]
0x18000361e  lea     rcx, [rax+rdx*8]
0x180003622  test    rcx, rcx
0x180003625  jz      short loc_18000362A
0x180003627  mov     [rcx], rbx
0x18000362a  add     [r14+10h], r15d
0x18000362e  mov     rdi, rsi
0x180003631  mov     rbx, rsi
0x180003634  jmp     short loc_180003639
0x180003636  mov     r15d, esi
0x180003639  mov     rcx, rbx
0x18000363c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003642  nop
0x180003643  mov     rcx, rdi
0x180003646  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000364c  mov     eax, r15d
0x18000364f  jmp     short loc_180003653
0x180003651  xor     eax, eax
0x180003653  add     rsp, 40h
0x180003657  pop     r15
0x180003659  pop     r14
0x18000365b  pop     r13
0x18000365d  pop     r12
0x18000365f  pop     rdi
0x180003660  pop     rsi
0x180003661  pop     rbx
0x180003662  retn
0x180003663  mov     ecx, 80004005h; int
0x180003668  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000366e  mov     ecx, 80070057h; int
0x180003673  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003679  mov     ecx, 8007000Eh; int
0x18000367e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
