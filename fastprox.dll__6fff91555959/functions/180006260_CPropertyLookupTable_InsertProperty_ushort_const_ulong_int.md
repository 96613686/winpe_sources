# CPropertyLookupTable::InsertProperty(ushort const *,ulong,int &)

- ea: `0x180006260`
- end: `0x180006706`
- name: `?InsertProperty@CPropertyLookupTable@@QEAAJPEBGKAEAH@Z`
- size: `1190`
- prototype: `__int64 __fastcall(CPropertyLookupTable *__hidden this, const unsigned __int16 *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180004190`

## callees

- `0x180006260`
- `0x1800067a0`
- `0x180007220`
- `0x1800072d0`
- `0x180011e40`
- `0x180011ec0`
- `0x180014f30`
- `0x180021c90`
- `0x180035b08`
- `0x180037120`
- `0x18006fa4c`
- `0x180091972`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800065b8`
- `wbemcomn!GetMemLogObject` at `0x18000662e`
- `wbemcomn!GetMemLogObject` at `0x180006674`
- `wbemcomn!GetMemLogObject` at `0x1800066ae`
- `wbemcomn!GetMemLogObject` at `0x1800065b8`
- `wbemcomn!GetMemLogObject` at `0x18000662e`
- `wbemcomn!GetMemLogObject` at `0x180006674`
- `wbemcomn!GetMemLogObject` at `0x1800066ae`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800065c6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000663c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180006682`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800066bc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800065c6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000663c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180006682`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800066bc`

## pseudocode

```c
__int64 __fastcall CPropertyLookupTable::InsertProperty(
        CPropertyLookupTable *this,
        unsigned __int16 *a2,
        int a3,
        int *a4)
{
  __int64 v6; // rax
  int *v7; // r10
  int v8; // r12d
  CFastHeap *v9; // rsi
  int v10; // edi
  int v11; // r13d
  __int64 v12; // rbx
  int v13; // edx
  unsigned int v14; // r11d
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // eax
  CDataTable *v21; // rax
  _DWORD *v22; // rdi
  int v23; // ecx
  __int64 v24; // rcx
  __int64 v25; // r15
  unsigned __int64 v26; // rax
  __int64 v27; // rbx
  int v28; // eax
  CPropertyLookupTable *v29; // rdi
  unsigned int v30; // r14d
  __int64 v31; // rax
  __int64 *v32; // rax
  __int64 v33; // rbx
  unsigned int v34; // eax
  int v35; // edx
  unsigned __int16 *v36; // rbx
  int KnownStringIndex; // eax
  unsigned int (__fastcall ***v39)(_QWORD, unsigned __int8 *, _QWORD, _QWORD); // r15
  unsigned __int8 *Start; // rax
  int v41; // r8d
  _DWORD *v42; // rax
  CMemoryLog *v43; // rax
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v45; // rcx
  __int64 v46; // rdx
  CMemoryLog *v47; // rax
  CMemoryLog *v48; // rax
  unsigned int v49; // [rsp+30h] [rbp-18h]
  CPropertyLookupTable *v50; // [rsp+90h] [rbp+48h] BYREF
  unsigned __int16 *v51; // [rsp+98h] [rbp+50h]
  int pExceptionObject; // [rsp+A0h] [rbp+58h] BYREF
  int *v53; // [rsp+A8h] [rbp+60h]

  v53 = a4;
  v51 = a2;
  v50 = this;
  v6 = (***((__int64 (__fastcall ****)(_QWORD))this + 1))(*((_QWORD *)this + 1));
  v7 = *(int **)this;
  v8 = 0;
  v9 = (CFastHeap *)v6;
  v10 = 0;
  pExceptionObject = 0;
  v11 = 0;
  v12 = v6 + 8;
  if ( *v7 > 0 )
  {
    v13 = 0;
    v14 = *(_DWORD *)(*(_QWORD *)v12 + 4LL);
    do
    {
      if ( v7[2 * v13 + 2] > v14 )
        throw (CX_Exception *)&pExceptionObject;
      v15 = (unsigned int)v7[2 * v13 + 2];
      v16 = *(_QWORD *)v9;
      v17 = *(_DWORD *)(v15 + *(_QWORD *)v9);
      if ( (v17 & 0xFFFu) > 0x7F )
      {
        v18 = 0;
      }
      else if ( (v17 & 0x2000) != 0 )
      {
        v18 = 4;
      }
      else
      {
        v18 = *((_DWORD *)&m_staticLengths + (v17 & 0xFFF));
      }
      v19 = *(_DWORD *)(v15 + v16 + 6) + v18;
      if ( v19 > v10 )
        v10 = v19;
      v20 = *(unsigned __int16 *)(v15 + v16 + 4) + 1;
      pExceptionObject = v10;
      if ( v20 > v11 )
        v11 = v20;
      ++v13;
    }
    while ( v13 < *v7 );
  }
  if ( (a3 & 0xFFFu) <= 0x7F )
  {
    if ( (a3 & 0x2000) != 0 )
      v8 = 4;
    else
      v8 = *((_DWORD *)&m_staticLengths + (a3 & 0xFFF));
  }
  v21 = (CDataTable *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 24LL))(*((_QWORD *)this + 1));
  if ( !(unsigned int)CDataTable::ExtendTo(v21, v11, v8 + v10) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217402);
    v45 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749894LL;
    }
    v46 = 21;
    goto LABEL_57;
  }
  v22 = *(_DWORD **)v12;
  v23 = *(_DWORD *)(*(_QWORD *)v12 + 4LL);
  if ( (unsigned int)(**(_DWORD **)v12 - v23) < 0x12 )
  {
    v39 = (unsigned int (__fastcall ***)(_QWORD, unsigned __int8 *, _QWORD, _QWORD))*((_QWORD *)v9 + 4);
    if ( !v39 )
    {
      v43 = GetMemLogObject();
      CMemoryLog::Write(v43, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_5079cb25a27f37742ccdcc8b2574b31c_Traceguids,
          "CX_Exception()");
      }
      throw (CX_Exception *)&pExceptionObject;
    }
    v49 = v23 + 50;
    Start = CFastHeap::GetStart(v9);
    v41 = 4;
    if ( v22 != (_DWORD *)((char *)v9 + 16) )
      v41 = 12;
    if ( !(**v39)(v39, Start, (unsigned int)(*v22 + v41), v49) )
    {
      v47 = GetMemLogObject();
      CMemoryLog::Write(v47, -2147217402);
      v45 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 2147749894LL;
      }
      v46 = 22;
      goto LABEL_57;
    }
    v42 = (_DWORD *)*((_QWORD *)v9 + 1);
    *v42 += v49;
    if ( *((CFastHeap **)v9 + 1) == (CFastHeap *)((char *)v9 + 16) )
      *(_DWORD *)(*(_QWORD *)v9 - 4LL) = *v42 | 0x80000000;
  }
  v24 = *((_QWORD *)v9 + 1);
  v25 = *(unsigned int *)(v24 + 4);
  *(_DWORD *)(v24 + 4) = v25 + 18;
  v26 = -1;
  do
    ++v26;
  while ( v51[v26] );
  if ( v26 > 2 && *v51 == 95 )
    a3 |= 0x4000u;
  if ( (unsigned int)v25 > *(_DWORD *)(*(_QWORD *)v12 + 4LL) )
    throw (CX_Exception *)&pExceptionObject;
  v27 = *(_QWORD *)v9;
  v28 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v50 + 1) + 32LL))(*((_QWORD *)v50 + 1), 0);
  v29 = v50;
  *(_DWORD *)(v25 + v27) = a3;
  v30 = pExceptionObject;
  *(_DWORD *)(v25 + v27 + 10) = v28;
  *(_WORD *)(v25 + v27 + 4) = v11;
  *(_DWORD *)(v25 + v27 + 6) = v30;
  *(_DWORD *)(v25 + v27 + 14) = 4;
  v31 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v29 + 1) + 24LL))(*((_QWORD *)v29 + 1));
  memset_0((void *)(*(_QWORD *)(v31 + 8) + v30), 255, v8);
  v32 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v29 + 1) + 24LL))(*((_QWORD *)v29 + 1));
  if ( v11 < 0 )
  {
    pExceptionObject = 534;
    throw (SafeIntException *)&pExceptionObject;
  }
  v33 = *v32;
  SafeInt<unsigned __int64>::MixedSizeMultiply<int>(&v50, v11, 2);
  SafeInt<unsigned __int64>::MixedSizeAddition<int>(&v50, (unsigned __int64)v50, 0);
  v34 = (unsigned int)v50;
  v35 = (int)v50 >> 31;
  v50 = 0;
  *(_DWORD *)(v33 + 4LL * (int)(__SPAIR64__(v35, v34) / 32)) = *(_DWORD *)(v33 + 4LL * (int)(__SPAIR64__(v35, v34) / 32))
                                                             | (1 << (__SPAIR64__(v35, v34) % 32));
  v36 = v51;
  KnownStringIndex = CKnownStringTable::GetKnownStringIndex(v51);
  if ( KnownStringIndex >= 0 )
  {
    LODWORD(v50) = KnownStringIndex | 0x80000000;
    goto LABEL_24;
  }
  if ( (unsigned int)CFastHeap::AllocateString(v9, v36, (unsigned int *)&v50) )
  {
LABEL_24:
    HIDWORD(v50) = v25;
    return CPropertyLookupTable::InsertProperty(v29, (const struct CPropertyLookup *)&v50, v53);
  }
  v48 = GetMemLogObject();
  CMemoryLog::Write(v48, -2147217402);
  v45 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v46 = 23;
LABEL_57:
    WPP_SF_d(*((_QWORD *)v45 + 2), v46, WPP_8db10d0debd535326cee342840d89e0d_Traceguids, 2147749894LL);
  }
  return 2147749894LL;
}

```

## disassembly

```asm
0x180006260  mov     [rsp-40h+arg_18], r9
0x180006265  mov     [rsp-40h+arg_8], rdx
0x18000626a  mov     [rsp-40h+arg_0], rcx
0x18000626f  push    rbp
0x180006270  push    rbx
0x180006271  push    rsi
0x180006272  push    rdi
0x180006273  push    r12
0x180006275  push    r13
0x180006277  push    r14
0x180006279  push    r15
0x18000627b  mov     rbp, rsp
0x18000627e  sub     rsp, 48h
0x180006282  mov     r15, rcx
0x180006285  mov     r14d, r8d
0x180006288  mov     rcx, [rcx+8]
0x18000628c  mov     rax, [rcx]
0x18000628f  mov     rax, [rax]
0x180006292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006297  mov     r10, [r15]
0x18000629a  lea     rcx, ?m_staticLengths@@3PAKA; ulong near * m_staticLengths
0x1800062a1  xor     r12d, r12d
0x1800062a4  mov     rsi, rax
0x1800062a7  mov     edi, r12d
0x1800062aa  mov     [rbp+pExceptionObject], r12d
0x1800062ae  mov     r13d, r12d
0x1800062b1  lea     rbx, [rax+8]
0x1800062b5  cmp     [r10], r12d
0x1800062b8  jle     short loc_18000632E
0x1800062ba  mov     rax, [rbx]
0x1800062bd  mov     edx, r12d
0x1800062c0  mov     r11d, [rax+4]
0x1800062c4  lea     eax, ds:0[rdx*8]
0x1800062cb  movsxd  rcx, eax
0x1800062ce  cmp     [rcx+r10+8], r11d
0x1800062d3  ja      loc_18000657E
0x1800062d9  mov     r8d, [rcx+r10+8]
0x1800062de  mov     r9, [rsi]
0x1800062e1  mov     ecx, [r8+r9]
0x1800062e5  mov     eax, ecx
0x1800062e7  and     eax, 0FFFh
0x1800062ec  cmp     eax, 7Fh
0x1800062ef  ja      loc_1800065F0
0x1800062f5  bt      ecx, 0Dh
0x1800062f9  jnb     loc_1800064CB
0x1800062ff  mov     ecx, 4
0x180006304  add     ecx, [r8+r9+6]
0x180006309  movzx   eax, word ptr [r8+r9+4]
0x18000630f  cmp     ecx, edi
0x180006311  cmovg   edi, ecx
0x180006314  inc     eax
0x180006316  cmp     eax, r13d
0x180006319  mov     [rbp+pExceptionObject], edi
0x18000631c  cmovg   r13d, eax
0x180006320  inc     edx
0x180006322  cmp     edx, [r10]
0x180006325  jl      short loc_1800062C4
0x180006327  lea     rcx, ?m_staticLengths@@3PAKA; ulong near * m_staticLengths
0x18000632e  mov     eax, r14d
0x180006331  and     eax, 0FFFh
0x180006336  cmp     eax, 7Fh
0x180006339  ja      short loc_18000634C
0x18000633b  bt      r14d, 0Dh
0x180006340  jnb     loc_180006559
0x180006346  mov     r12d, 4
0x18000634c  mov     rcx, [r15+8]
0x180006350  mov     rax, [rcx]
0x180006353  mov     rax, [rax+18h]
0x180006357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000635c  lea     r8d, [r12+rdi]; unsigned int
0x180006360  movzx   edx, r13w; unsigned __int16
0x180006364  mov     rcx, rax; this
0x180006367  call    ?ExtendTo@CDataTable@@QEAAHGK@Z; CDataTable::ExtendTo(ushort,ulong)
0x18000636c  xor     edx, edx
0x18000636e  test    eax, eax
0x180006370  jz      loc_18000662E
0x180006376  mov     rdi, [rbx]
0x180006379  mov     eax, [rdi]
0x18000637b  mov     ecx, [rdi+4]
0x18000637e  sub     eax, ecx
0x180006380  cmp     eax, 12h
0x180006383  jb      loc_1800064E0
0x180006389  mov     rcx, [rsi+8]
0x18000638d  mov     r15d, [rcx+4]
0x180006391  lea     eax, [r15+12h]
0x180006395  mov     [rcx+4], eax
0x180006398  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000639c  mov     rcx, [rbp+arg_8]
0x1800063a0  inc     rax
0x1800063a3  cmp     [rcx+rax*2], dx
0x1800063a7  jnz     short loc_1800063A0
0x1800063a9  cmp     rax, 2
0x1800063ad  ja      loc_18000656A
0x1800063b3  mov     rax, [rbx]
0x1800063b6  cmp     r15d, [rax+4]
0x1800063ba  ja      loc_18000658F
0x1800063c0  mov     rcx, [rbp+arg_0]
0x1800063c4  mov     rbx, [rsi]
0x1800063c7  mov     rcx, [rcx+8]
0x1800063cb  mov     rax, [rcx]
0x1800063ce  mov     rax, [rax+20h]
0x1800063d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063d7  mov     rdi, [rbp+arg_0]
0x1800063db  mov     [r15+rbx], r14d
0x1800063df  mov     r14d, [rbp+pExceptionObject]
0x1800063e3  mov     [r15+rbx+0Ah], eax
0x1800063e8  mov     [r15+rbx+4], r13w
0x1800063ee  mov     [r15+rbx+6], r14d
0x1800063f3  mov     dword ptr [r15+rbx+0Eh], 4
0x1800063fc  mov     rcx, [rdi+8]
0x180006400  mov     rax, [rcx]
0x180006403  mov     rax, [rax+18h]
0x180006407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000640c  mov     ecx, r14d
0x18000640f  movsxd  r8, r12d; Size
0x180006412  mov     edx, 0FFh; Val
0x180006417  add     rcx, [rax+8]; void *
0x18000641b  call    memset_0
0x180006420  mov     rcx, [rdi+8]
0x180006424  mov     rax, [rcx]
0x180006427  mov     rax, [rax+18h]
0x18000642b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006430  xor     r14d, r14d
0x180006433  test    r13d, r13d
0x180006436  js      loc_1800065A0
0x18000643c  mov     rbx, [rax]
0x18000643f  lea     r8d, [r14+2]
0x180006443  movsxd  rdx, r13d
0x180006446  lea     rcx, [rbp+arg_0]
0x18000644a  call    ??$MixedSizeMultiply@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeMultiply<int>(SafeInt<unsigned __int64>,int)
0x18000644f  mov     rdx, [rbp+arg_0]
0x180006453  lea     rcx, [rbp+arg_0]
0x180006457  xor     r8d, r8d
0x18000645a  call    ??$MixedSizeAddition@H@?$SafeInt@_K@@CA?AV0@V0@H@Z; SafeInt<unsigned __int64>::MixedSizeAddition<int>(SafeInt<unsigned __int64>,int)
0x18000645f  mov     eax, dword ptr [rbp+arg_0]
0x180006462  lea     ecx, [r14+20h]
0x180006466  cdq
0x180006467  mov     [rbp+arg_0], r14
0x18000646b  idiv    ecx
0x18000646d  movsxd  r8, eax
0x180006470  mov     eax, [rbx+r8*4]
0x180006474  bts     eax, edx
0x180006477  mov     [rbx+r8*4], eax
0x18000647b  mov     rbx, [rbp+arg_8]
0x18000647f  mov     rcx, rbx; unsigned __int16 *
0x180006482  call    ?GetKnownStringIndex@CKnownStringTable@@SAHPEBG@Z; CKnownStringTable::GetKnownStringIndex(ushort const *)
0x180006487  test    eax, eax
0x180006489  jns     loc_1800065F8
0x18000648f  lea     r8, [rbp+arg_0]; unsigned int *
0x180006493  mov     rdx, rbx; unsigned __int16 *
0x180006496  mov     rcx, rsi; this
0x180006499  call    ?AllocateString@CFastHeap@@QEAAHPEBGAEFAK@Z; CFastHeap::AllocateString(ushort const *,ulong &)
0x18000649e  test    eax, eax
0x1800064a0  jz      loc_1800066AE
0x1800064a6  mov     r8, [rbp+arg_18]; int *
0x1800064aa  lea     rdx, [rbp+arg_0]; struct CPropertyLookup *
0x1800064ae  mov     rcx, rdi; this
0x1800064b1  mov     dword ptr [rbp+arg_0+4], r15d
0x1800064b5  call    ?InsertProperty@CPropertyLookupTable@@QEAAJAEBUCPropertyLookup@@AEAH@Z; CPropertyLookupTable::InsertProperty(CPropertyLookup const &,int &)
0x1800064ba  add     rsp, 48h
0x1800064be  pop     r15
0x1800064c0  pop     r14
0x1800064c2  pop     r13
0x1800064c4  pop     r12
0x1800064c6  pop     rdi
0x1800064c7  pop     rsi
0x1800064c8  pop     rbx
0x1800064c9  pop     rbp
0x1800064ca  retn
0x1800064cb  and     ecx, 0FFFh
0x1800064d1  lea     rax, ?m_staticLengths@@3PAKA; ulong near * m_staticLengths
0x1800064d8  mov     ecx, [rax+rcx*4]
0x1800064db  jmp     loc_180006304
0x1800064e0  mov     r15, [rsi+20h]
0x1800064e4  test    r15, r15
0x1800064e7  jz      loc_1800065B8
0x1800064ed  lea     eax, [rcx+32h]
0x1800064f0  mov     rcx, rsi; this
0x1800064f3  mov     [rbp+var_18], eax
0x1800064f6  call    ?GetStart@CFastHeap@@QEAAPEAEXZ; CFastHeap::GetStart(void)
0x1800064fb  mov     r8d, 4
0x180006501  lea     rcx, [rsi+10h]
0x180006505  cmp     rdi, rcx
0x180006508  mov     rdx, rax
0x18000650b  mov     rax, [r15]
0x18000650e  mov     rcx, r15
0x180006511  lea     r9d, [r8+8]
0x180006515  cmovnz  r8d, r9d
0x180006519  add     r8d, [rdi]
0x18000651c  mov     edi, [rbp+var_18]
0x18000651f  mov     r9d, edi
0x180006522  mov     rax, [rax]
0x180006525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000652a  xor     edx, edx
0x18000652c  test    eax, eax
0x18000652e  jz      loc_180006674
0x180006534  mov     rax, [rsi+8]
0x180006538  add     [rax], edi
0x18000653a  mov     ecx, [rax]
0x18000653c  lea     rax, [rsi+10h]
0x180006540  cmp     [rsi+8], rax
0x180006544  jnz     loc_180006389
0x18000654a  mov     rax, [rsi]
0x18000654d  bts     ecx, 1Fh
0x180006551  mov     [rax-4], ecx
0x180006554  jmp     loc_180006389
0x180006559  mov     eax, r14d
0x18000655c  and     eax, 0FFFh
0x180006561  mov     r12d, [rcx+rax*4]
0x180006565  jmp     loc_18000634C
0x18000656a  cmp     word ptr [rcx], 5Fh ; '_'
0x18000656e  jnz     loc_1800063B3
0x180006574  bts     r14d, 0Eh
0x180006579  jmp     loc_1800063B3
0x18000657e  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x180006585  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180006589  call    _CxxThrowException_0
0x18000658f  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x180006596  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000659a  call    _CxxThrowException_0
0x1800065a0  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x1800065a7  mov     [rbp+pExceptionObject], 216h
0x1800065ae  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800065b2  call    _CxxThrowException_0
0x1800065b8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800065be  mov     rcx, rax
0x1800065c1  mov     edx, 0FFFFFFFEh
0x1800065c6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800065cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065d3  lea     rax, WPP_GLOBAL_Control
0x1800065da  cmp     rcx, rax
0x1800065dd  jnz     short loc_180006604
0x1800065df  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x1800065e6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800065ea  call    _CxxThrowException_0
0x1800065f0  mov     ecx, r12d
0x1800065f3  jmp     loc_180006304
0x1800065f8  bts     eax, 1Fh
0x1800065fc  mov     dword ptr [rbp+arg_0], eax
0x1800065ff  jmp     loc_1800064A6
0x180006604  test    byte ptr [rcx+1Ch], 1
0x180006608  jz      short loc_1800065DF
0x18000660a  cmp     byte ptr [rcx+19h], 2
0x18000660e  jb      short loc_1800065DF
0x180006610  mov     rcx, [rcx+10h]
0x180006614  lea     r9, aCxException; "CX_Exception()"
0x18000661b  mov     edx, 0Dh
0x180006620  lea     r8, WPP_5079cb25a27f37742ccdcc8b2574b31c_Traceguids
0x180006627  call    WPP_SF_s
0x18000662c  jmp     short loc_1800065DF
0x18000662e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180006634  mov     rcx, rax
0x180006637  mov     edx, 80041006h
0x18000663c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180006642  mov     rcx, cs:WPP_GLOBAL_Control
0x180006649  lea     rax, WPP_GLOBAL_Control
0x180006650  cmp     rcx, rax
0x180006653  jz      loc_1800066FC
0x180006659  test    byte ptr [rcx+1Ch], 1
0x18000665d  jz      loc_1800066FC
0x180006663  cmp     byte ptr [rcx+19h], 2
0x180006667  jb      loc_1800066FC
0x18000666d  mov     edx, 15h
0x180006672  jmp     short loc_1800066E6
0x180006674  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000667a  mov     rcx, rax
0x18000667d  mov     edx, 80041006h
0x180006682  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180006688  mov     rcx, cs:WPP_GLOBAL_Control
0x18000668f  lea     rax, WPP_GLOBAL_Control
0x180006696  cmp     rcx, rax
0x180006699  jz      short loc_1800066FC
0x18000669b  test    byte ptr [rcx+1Ch], 1
0x18000669f  jz      short loc_1800066FC
0x1800066a1  cmp     byte ptr [rcx+19h], 2
0x1800066a5  jb      short loc_1800066FC
0x1800066a7  mov     edx, 16h
0x1800066ac  jmp     short loc_1800066E6
0x1800066ae  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800066b4  mov     rcx, rax
0x1800066b7  mov     edx, 80041006h
0x1800066bc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800066c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066c9  lea     rax, WPP_GLOBAL_Control
0x1800066d0  cmp     rcx, rax
0x1800066d3  jz      short loc_1800066FC
0x1800066d5  test    byte ptr [rcx+1Ch], 1
0x1800066d9  jz      short loc_1800066FC
0x1800066db  cmp     byte ptr [rcx+19h], 2
0x1800066df  jb      short loc_1800066FC
0x1800066e1  mov     edx, 17h
0x1800066e6  mov     rcx, [rcx+10h]
0x1800066ea  lea     r8, WPP_8db10d0debd535326cee342840d89e0d_Traceguids
0x1800066f1  mov     r9d, 80041006h
0x1800066f7  call    WPP_SF_d
0x1800066fc  mov     eax, 80041006h
0x180006701  jmp     loc_1800064BA
```
