# HPerformanceCounterDataCollector::Load(void)

- ea: `0x1800fe570`
- end: `0x1800fed0e`
- name: `?Load@HPerformanceCounterDataCollector@@UEAAJXZ`
- size: `1950`
- prototype: `__int64 __fastcall(HPerformanceCounterDataCollector *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18008e6f4`
- `0x1800c4850`
- `0x1800fe570`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `pdh!PdhCloseQuery` at `0x1800fe5c2`
- `pdh!PdhCloseQuery` at `0x1800fe5c2`
- `pdh!PdhOpenQueryW` at `0x1800fe5d2`
- `pdh!PdhOpenQueryW` at `0x1800fe5d2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800fece2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800fece2`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800fe900`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800fe900`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800feccf`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800feccf`

## pseudocode

```c
__int64 __fastcall HPerformanceCounterDataCollector::Load(HPerformanceCounterDataCollector *this)
{
  PDH_HQUERY *v1; // rbx
  void *v3; // rcx
  PDH_STATUS v4; // eax
  __int64 v5; // rbx
  int v6; // eax
  __int64 v7; // rbx
  int v8; // eax
  __int64 v9; // rbx
  int v10; // ecx
  _WORD *v11; // rdx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  __int64 v15; // rbx
  HRESULT v16; // eax
  __int64 v17; // rbx
  __int64 v18; // rbx
  ULONG i; // r14d
  __int64 v20; // r8
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // r9
  __int64 v24; // rax
  __int64 v25; // rcx
  int v26; // eax
  int v27; // eax
  int v28; // eax
  __int64 v30; // [rsp+48h] [rbp-B8h]
  __int64 v31; // [rsp+50h] [rbp-B0h]
  int v32; // [rsp+70h] [rbp-90h] BYREF
  PDH_STATUS v33; // [rsp+78h] [rbp-88h] BYREF
  int v34; // [rsp+80h] [rbp-80h] BYREF
  int v35; // [rsp+84h] [rbp-7Ch] BYREF
  void *ppvData; // [rsp+88h] [rbp-78h] BYREF
  SAFEARRAY *psa; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v38[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v39[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v40[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v41[64]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v42[64]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v43[64]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v44[64]; // [rsp+3A0h] [rbp+2A0h] BYREF
  unsigned __int16 v45[64]; // [rsp+420h] [rbp+320h] BYREF
  unsigned __int16 v46[64]; // [rsp+4A0h] [rbp+3A0h] BYREF

  v1 = (PDH_HQUERY *)((char *)this + 232);
  v34 = 0;
  v3 = (void *)*((_QWORD *)this + 29);
  v35 = 0;
  ppvData = 0;
  psa = 0;
  if ( v3 )
  {
    PdhCloseQuery(v3);
    *v1 = 0;
  }
  v4 = PdhOpenQueryW(0, 0, v1);
  v34 = v4;
  if ( v4 < 0 )
  {
    v32 = 0;
    v33 = v4;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v38, 0x4000000000000800uLL);
      v5 = -1;
      do
        ++v5;
      while ( v38[v5] );
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v33,
        4,
        qword_180147320,
        1,
        &v32,
        4,
        "HPerformanceCounterDataCollector::Load",
        39);
    }
    goto LABEL_104;
  }
  v6 = HDataCollector::Load(this);
  v34 = v6;
  if ( v6 < 0 )
  {
    v33 = 0;
    v32 = v6;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_104;
    }
    PlaiWhoAmI(v39, 0x4000000000000800uLL);
    v7 = -1;
    do
      ++v7;
    while ( v39[v7] );
    goto LABEL_103;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 27) + 288LL))(*((_QWORD *)this + 27), &v35);
  v34 = v8;
  if ( v8 < 0 )
  {
    v33 = 0;
    v32 = v8;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_104;
    }
    PlaiWhoAmI(v40, 0x4000000000000800uLL);
    v9 = -1;
    do
      ++v9;
    while ( v40[v9] );
    goto LABEL_103;
  }
  switch ( v35 )
  {
    case 0:
      *((_DWORD *)this + 64) = 1;
      v10 = 1;
      goto LABEL_31;
    case 1:
      *((_DWORD *)this + 64) = 2;
      v10 = 2;
      goto LABEL_31;
    case 2:
      *((_DWORD *)this + 64) = 7;
      v10 = 7;
LABEL_31:
      *((_DWORD *)this + 56) = 1;
      goto LABEL_32;
  }
  *((_DWORD *)this + 56) = 0;
  v10 = 8;
  *((_DWORD *)this + 64) = 8;
LABEL_32:
  v11 = (_WORD *)*((_QWORD *)this + 11);
  if ( v11 && *v11 )
    *((_DWORD *)this + 65) |= 0x1000000u;
  if ( v10 == 8 && *((_WORD *)this + 24) )
    *((_DWORD *)this + 65) |= 0x8000000u;
  v12 = *((_DWORD *)this + 65);
  if ( *((_WORD *)this + 26) )
  {
    v13 = v12 | 2;
  }
  else if ( *((_WORD *)this + 24) )
  {
    v13 = v12 | 3;
  }
  else
  {
    v13 = v12 | 1;
  }
  *((_DWORD *)this + 65) = v13;
  if ( v10 == 7 )
    *((_DWORD *)this + 29) = 0;
  if ( *((_WORD *)this + 25) && *((_DWORD *)this + 29) )
    *((_DWORD *)this + 65) = v13 | 0x2000000;
  v14 = (*(__int64 (__fastcall **)(_QWORD, SAFEARRAY **, __int64, __int64))(**((_QWORD **)this + 27) + 272LL))(
          *((_QWORD *)this + 27),
          &psa,
          8,
          7);
  v34 = v14;
  if ( v14 < 0 )
  {
    v33 = 0;
    v32 = v14;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_104;
    }
    PlaiWhoAmI(v41, 0x4000000000000800uLL);
    v15 = -1;
    do
      ++v15;
    while ( v41[v15] );
    goto LABEL_103;
  }
  v16 = SafeArrayAccessData(psa, &ppvData);
  v34 = v16;
  if ( v16 < 0 )
  {
    v33 = 0;
    v32 = v16;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_104;
    }
    PlaiWhoAmI(v42, 0x4000000000000800uLL);
    v17 = -1;
    do
      ++v17;
    while ( v42[v17] );
LABEL_103:
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v32,
      4,
      qword_180147320,
      1,
      &v33,
      4,
      "HPerformanceCounterDataCollector::Load",
      39);
    goto LABEL_104;
  }
  v18 = -1;
  for ( i = 0; i < psa->rgsabound[0].cElements; ++i )
  {
    v34 = HPerformanceCounterDataCollector::AddCounter(this, *((unsigned __int16 **)ppvData + i));
    if ( v34 < 0 )
    {
      v20 = *((_QWORD *)ppvData + i);
      if ( v20 )
      {
        v21 = -1;
        do
          ++v21;
        while ( *(_WORD *)(v20 + 2 * v21) );
        v22 = (unsigned int)(2 * v21) + 2LL;
      }
      else
      {
        v22 = 0;
      }
      v23 = *((_QWORD *)this + 7);
      if ( v23 )
      {
        v24 = -1;
        do
          ++v24;
        while ( *(_WORD *)(v23 + 2 * v24) );
        v25 = (unsigned int)(2 * v24) + 2LL;
      }
      else
      {
        v25 = 0;
      }
      v34 = EventingWriteEvent(&g_Eventing, PLA_EVENTLOG_CNTRADD_FAILED, 3, v23, v25, v20, v22, &v34, 4, v30, v31);
      if ( v34 < 0 )
      {
        v32 = v34;
        v33 = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v43, 0x4000000000000800uLL);
          do
            ++v18;
          while ( v43[v18] );
          goto LABEL_103;
        }
        goto LABEL_104;
      }
    }
  }
  v26 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 27) + 304LL))(
          *((_QWORD *)this + 27),
          (char *)this + 204);
  v34 = v26;
  if ( v26 >= 0 )
  {
    v27 = (*(__int64 (__fastcall **)(HPerformanceCounterDataCollector *, _QWORD))(*(_QWORD *)this + 48LL))(
            this,
            *((unsigned int *)this + 51));
    v34 = v27;
    if ( v27 >= 0 )
    {
      v28 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 27) + 320LL))(
              *((_QWORD *)this + 27),
              (char *)this + 208);
      v34 = v28;
      if ( v28 < 0 )
      {
        v33 = 0;
        v32 = v28;
        if ( (_DWORD)xmmword_180169738 )
        {
          if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v46, 0x4000000000000800uLL);
            do
              ++v18;
            while ( v46[v18] );
            goto LABEL_103;
          }
        }
      }
    }
    else
    {
      v33 = 0;
      v32 = v27;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v45, 0x4000000000000800uLL);
        do
          ++v18;
        while ( v45[v18] );
        goto LABEL_103;
      }
    }
  }
  else
  {
    v33 = 0;
    v32 = v26;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v44, 0x4000000000000800uLL);
      do
        ++v18;
      while ( v44[v18] );
      goto LABEL_103;
    }
  }
LABEL_104:
  if ( ppvData )
  {
    SafeArrayUnaccessData(psa);
    ppvData = 0;
  }
  if ( psa )
    SafeArrayDestroy(psa);
  return (unsigned int)v34;
}

```

## disassembly

```asm
0x1800fe570  push    rbp
0x1800fe572  push    rbx
0x1800fe573  push    rsi
0x1800fe574  push    rdi
0x1800fe575  push    r12
0x1800fe577  push    r13
0x1800fe579  push    r14
0x1800fe57b  push    r15
0x1800fe57d  lea     rbp, [rsp-438h]
0x1800fe585  sub     rsp, 538h
0x1800fe58c  mov     rax, cs:__security_cookie
0x1800fe593  xor     rax, rsp
0x1800fe596  mov     [rbp+470h+var_50], rax
0x1800fe59d  xor     r13d, r13d
0x1800fe5a0  lea     rbx, [rcx+0E8h]
0x1800fe5a7  mov     rdi, rcx
0x1800fe5aa  mov     [rbp+470h+var_4F0], r13d
0x1800fe5ae  mov     rcx, [rbx]; hQuery
0x1800fe5b1  mov     [rbp+470h+var_4EC], r13d
0x1800fe5b5  mov     [rbp+470h+ppvData], r13
0x1800fe5b9  mov     [rbp+470h+psa], r13
0x1800fe5bd  test    rcx, rcx
0x1800fe5c0  jz      short loc_1800FE5CB
0x1800fe5c2  call    cs:__imp_PdhCloseQuery
0x1800fe5c8  mov     [rbx], r13
0x1800fe5cb  mov     r8, rbx; phQuery
0x1800fe5ce  xor     edx, edx; dwUserData
0x1800fe5d0  xor     ecx, ecx; szDataSource
0x1800fe5d2  call    cs:__imp_PdhOpenQueryW
0x1800fe5d8  mov     [rbp+470h+var_4F0], eax
0x1800fe5db  test    eax, eax
0x1800fe5dd  jns     loc_1800FE685
0x1800fe5e3  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800fe5ea  mov     [rsp+570h+var_500], r13d
0x1800fe5ef  mov     [rsp+570h+var_4F8], eax
0x1800fe5f3  jz      loc_1800FECC5
0x1800fe5f9  mov     rdx, 4000000000000800h; unsigned __int64
0x1800fe603  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800fe60a  jz      loc_1800FECC5
0x1800fe610  mov     rax, cs:qword_180169748
0x1800fe617  and     rax, rdx
0x1800fe61a  cmp     cs:qword_180169748, rax
0x1800fe621  jnz     loc_1800FECC5
0x1800fe627  lea     rcx, [rbp+470h+var_4D0]; unsigned __int16 *
0x1800fe62b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800fe630  lea     rax, [rbp+470h+var_4D0]
0x1800fe634  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800fe638  inc     rbx
0x1800fe63b  cmp     [rax+rbx*2], r13w
0x1800fe640  jnz     short loc_1800FE638
0x1800fe642  lea     rax, [rbp+470h+var_4D0]
0x1800fe646  mov     r15d, 4
0x1800fe64c  lea     ecx, [rbx+rbx]
0x1800fe64f  add     rcx, 2
0x1800fe653  lea     r9, [rsp+570h+var_4F8]
0x1800fe658  mov     [rsp+570h+var_510], rcx
0x1800fe65d  mov     [rsp+570h+var_518], rax
0x1800fe662  lea     esi, [r15-3]
0x1800fe666  lea     rax, aHperformanceco_0; "HPerformanceCounterDataCollector::Load"
0x1800fe66d  mov     [rsp+570h+var_520], 27h ; '''
0x1800fe676  mov     [rsp+570h+var_528], rax
0x1800fe67b  lea     rax, [rsp+570h+var_500]
0x1800fe680  jmp     loc_1800FEC8C
0x1800fe685  mov     rcx, rdi; this
0x1800fe688  call    ?Load@HDataCollector@@UEAAJXZ; HDataCollector::Load(void)
0x1800fe68d  mov     [rbp+470h+var_4F0], eax
0x1800fe690  test    eax, eax
0x1800fe692  jns     short loc_1800FE707
0x1800fe694  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800fe69b  mov     [rsp+570h+var_4F8], r13d
0x1800fe6a0  mov     [rsp+570h+var_500], eax
0x1800fe6a4  jz      loc_1800FECC5
0x1800fe6aa  mov     rdx, 4000000000000800h; unsigned __int64
0x1800fe6b4  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800fe6bb  jz      loc_1800FECC5
0x1800fe6c1  mov     rax, cs:qword_180169748
0x1800fe6c8  and     rax, rdx
0x1800fe6cb  cmp     cs:qword_180169748, rax
0x1800fe6d2  jnz     loc_1800FECC5
0x1800fe6d8  lea     rcx, [rbp+470h+var_450]; unsigned __int16 *
0x1800fe6dc  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800fe6e1  lea     rax, [rbp+470h+var_450]
0x1800fe6e5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800fe6e9  inc     rbx
0x1800fe6ec  cmp     [rax+rbx*2], r13w
0x1800fe6f1  jnz     short loc_1800FE6E9
0x1800fe6f3  lea     rax, [rbp+470h+var_450]
0x1800fe6f7  mov     esi, 1
0x1800fe6fc  mov     r15d, 4
0x1800fe702  jmp     loc_1800FEC5C
0x1800fe707  mov     rcx, [rdi+0D8h]
0x1800fe70e  lea     rdx, [rbp+470h+var_4EC]
0x1800fe712  mov     rax, [rcx]
0x1800fe715  mov     rax, [rax+120h]
0x1800fe71c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe721  mov     [rbp+470h+var_4F0], eax
0x1800fe724  test    eax, eax
0x1800fe726  jns     short loc_1800FE799
0x1800fe728  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800fe72f  mov     [rsp+570h+var_4F8], r13d
0x1800fe734  mov     [rsp+570h+var_500], eax
0x1800fe738  jz      loc_1800FECC5
0x1800fe73e  mov     rdx, 4000000000000800h; unsigned __int64
0x1800fe748  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800fe74f  jz      loc_1800FECC5
0x1800fe755  mov     rax, cs:qword_180169748
0x1800fe75c  and     rax, rdx
0x1800fe75f  cmp     cs:qword_180169748, rax
0x1800fe766  jnz     loc_1800FECC5
0x1800fe76c  lea     rcx, [rbp+470h+var_3D0]; unsigned __int16 *
0x1800fe773  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800fe778  lea     rax, [rbp+470h+var_3D0]
0x1800fe77f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800fe783  inc     rbx
0x1800fe786  cmp     [rax+rbx*2], r13w
0x1800fe78b  jnz     short loc_1800FE783
0x1800fe78d  lea     rax, [rbp+470h+var_3D0]
0x1800fe794  jmp     loc_1800FE6F7
0x1800fe799  mov     ecx, [rbp+470h+var_4EC]
0x1800fe79c  mov     esi, 1
0x1800fe7a1  lea     r8d, [rsi+7]
0x1800fe7a5  lea     r9d, [rsi+6]
0x1800fe7a9  test    ecx, ecx
0x1800fe7ab  jz      short loc_1800FE7E7
0x1800fe7ad  sub     ecx, esi
0x1800fe7af  jz      short loc_1800FE7D6
0x1800fe7b1  sub     ecx, esi
0x1800fe7b3  jz      short loc_1800FE7CA
0x1800fe7b5  cmp     ecx, esi
0x1800fe7b7  mov     [rdi+0E0h], r13d
0x1800fe7be  mov     ecx, r8d
0x1800fe7c1  mov     [rdi+100h], r8d
0x1800fe7c8  jmp     short loc_1800FE7F5
0x1800fe7ca  mov     [rdi+100h], r9d
0x1800fe7d1  mov     ecx, r9d
0x1800fe7d4  jmp     short loc_1800FE7EF
0x1800fe7d6  mov     dword ptr [rdi+100h], 2
0x1800fe7e0  mov     ecx, 2
0x1800fe7e5  jmp     short loc_1800FE7EF
0x1800fe7e7  mov     [rdi+100h], esi
0x1800fe7ed  mov     ecx, esi
0x1800fe7ef  mov     [rdi+0E0h], esi
0x1800fe7f5  mov     rdx, [rdi+58h]
0x1800fe7f9  test    rdx, rdx
0x1800fe7fc  jz      short loc_1800FE80C
0x1800fe7fe  cmp     r13w, [rdx]
0x1800fe802  jz      short loc_1800FE80C
0x1800fe804  bts     dword ptr [rdi+104h], 18h
0x1800fe80c  cmp     ecx, r8d
0x1800fe80f  jnz     short loc_1800FE820
0x1800fe811  cmp     [rdi+30h], r13w
0x1800fe816  jz      short loc_1800FE820
0x1800fe818  bts     dword ptr [rdi+104h], 1Bh
0x1800fe820  mov     eax, [rdi+104h]
0x1800fe826  cmp     [rdi+34h], r13w
0x1800fe82b  jz      short loc_1800FE832
0x1800fe82d  or      eax, 2
0x1800fe830  jmp     short loc_1800FE840
0x1800fe832  cmp     [rdi+30h], r13w
0x1800fe837  jz      short loc_1800FE83E
0x1800fe839  or      eax, 3
0x1800fe83c  jmp     short loc_1800FE840
0x1800fe83e  or      eax, esi
0x1800fe840  mov     [rdi+104h], eax
0x1800fe846  cmp     ecx, r9d
0x1800fe849  jnz     short loc_1800FE84F
0x1800fe84b  mov     [rdi+74h], r13d
0x1800fe84f  cmp     [rdi+32h], r13w
0x1800fe854  jz      short loc_1800FE866
0x1800fe856  cmp     [rdi+74h], r13d
0x1800fe85a  jbe     short loc_1800FE866
0x1800fe85c  bts     eax, 19h
0x1800fe860  mov     [rdi+104h], eax
0x1800fe866  mov     rcx, [rdi+0D8h]
0x1800fe86d  lea     rdx, [rbp+470h+psa]
0x1800fe871  mov     rax, [rcx]
0x1800fe874  mov     rax, [rax+110h]
0x1800fe87b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe880  mov     [rbp+470h+var_4F0], eax
0x1800fe883  test    eax, eax
0x1800fe885  jns     short loc_1800FE8F8
0x1800fe887  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800fe88e  mov     [rsp+570h+var_4F8], r13d
0x1800fe893  mov     [rsp+570h+var_500], eax
0x1800fe897  jz      loc_1800FECC5
0x1800fe89d  mov     rdx, 4000000000000800h; unsigned __int64
0x1800fe8a7  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800fe8ae  jz      loc_1800FECC5
0x1800fe8b4  mov     rax, cs:qword_180169748
0x1800fe8bb  and     rax, rdx
0x1800fe8be  cmp     cs:qword_180169748, rax
0x1800fe8c5  jnz     loc_1800FECC5
0x1800fe8cb  lea     rcx, [rbp+470h+var_350]; unsigned __int16 *
0x1800fe8d2  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800fe8d7  lea     rax, [rbp+470h+var_350]
0x1800fe8de  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800fe8e2  inc     rbx
0x1800fe8e5  cmp     [rax+rbx*2], r13w
0x1800fe8ea  jnz     short loc_1800FE8E2
0x1800fe8ec  lea     rax, [rbp+470h+var_350]
0x1800fe8f3  jmp     loc_1800FE6FC
0x1800fe8f8  mov     rcx, [rbp+470h+psa]; psa
0x1800fe8fc  lea     rdx, [rbp+470h+ppvData]; ppvData
0x1800fe900  call    cs:__imp_SafeArrayAccessData
0x1800fe906  mov     [rbp+470h+var_4F0], eax
0x1800fe909  test    eax, eax
0x1800fe90b  jns     short loc_1800FE97E
0x1800fe90d  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800fe914  mov     [rsp+570h+var_4F8], r13d
0x1800fe919  mov     [rsp+570h+var_500], eax
0x1800fe91d  jz      loc_1800FECC5
0x1800fe923  mov     rdx, 4000000000000800h; unsigned __int64
0x1800fe92d  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800fe934  jz      loc_1800FECC5
0x1800fe93a  mov     rax, cs:qword_180169748
0x1800fe941  and     rax, rdx
0x1800fe944  cmp     cs:qword_180169748, rax
0x1800fe94b  jnz     loc_1800FECC5
0x1800fe951  lea     rcx, [rbp+470h+var_2D0]; unsigned __int16 *
0x1800fe958  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800fe95d  lea     rax, [rbp+470h+var_2D0]
0x1800fe964  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800fe968  inc     rbx
0x1800fe96b  cmp     [rax+rbx*2], r13w
0x1800fe970  jnz     short loc_1800FE968
0x1800fe972  lea     rax, [rbp+470h+var_2D0]
0x1800fe979  jmp     loc_1800FE6FC
0x1800fe97e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800fe982  mov     r14d, r13d
0x1800fe985  lea     r15d, [rbx+5]
0x1800fe989  mov     rax, [rbp+470h+psa]
0x1800fe98d  cmp     r14d, [rax+18h]
0x1800fe991  jnb     loc_1800FEAB2
0x1800fe997  mov     rdx, [rbp+470h+ppvData]
0x1800fe99b  mov     rcx, rdi; this
0x1800fe99e  mov     r12d, r14d
0x1800fe9a1  mov     rdx, [rdx+r12*8]; unsigned __int16 *
0x1800fe9a5  call    ?AddCounter@HPerformanceCounterDataCollector@@IEAAJPEAG@Z; HPerformanceCounterDataCollector::AddCounter(ushort *)
0x1800fe9aa  mov     [rbp+470h+var_4F0], eax
0x1800fe9ad  test    eax, eax
0x1800fe9af  jns     loc_1800FEA3A
0x1800fe9b5  mov     rax, [rbp+470h+ppvData]
0x1800fe9b9  mov     r8, [rax+r12*8]
0x1800fe9bd  test    r8, r8
0x1800fe9c0  jz      short loc_1800FE9D8
0x1800fe9c2  mov     rax, rbx
0x1800fe9c5  inc     rax
0x1800fe9c8  cmp     [r8+rax*2], r13w
0x1800fe9cd  jnz     short loc_1800FE9C5
0x1800fe9cf  lea     edx, [rax+rax]
0x1800fe9d2  add     rdx, 2
0x1800fe9d6  jmp     short loc_1800FE9DB
0x1800fe9d8  mov     rdx, r13
0x1800fe9db  mov     r9, [rdi+38h]
0x1800fe9df  test    r9, r9
0x1800fe9e2  jz      short loc_1800FE9FA
0x1800fe9e4  mov     rax, rbx
0x1800fe9e7  inc     rax
0x1800fe9ea  cmp     [r9+rax*2], r13w
0x1800fe9ef  jnz     short loc_1800FE9E7
0x1800fe9f1  lea     ecx, [rax+rax]
0x1800fe9f4  add     rcx, 2
0x1800fe9f8  jmp     short loc_1800FE9FD
0x1800fe9fa  mov     rcx, r13
0x1800fe9fd  mov     [rsp+570h+var_530], r15
0x1800fea02  lea     rax, [rbp+470h+var_4F0]
0x1800fea06  mov     [rsp+570h+var_538], rax
0x1800fea0b  mov     [rsp+570h+var_540], rdx
0x1800fea10  lea     rdx, PLA_EVENTLOG_CNTRADD_FAILED
0x1800fea17  mov     [rsp+570h+var_548], r8
0x1800fea1c  mov     r8d, 3
0x1800fea22  mov     [rsp+570h+var_550], rcx
0x1800fea27  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800fea2e  call    EventingWriteEvent
0x1800fea33  mov     [rbp+470h+var_4F0], eax
0x1800fea36  test    eax, eax
0x1800fea38  js      short loc_1800FEA42
0x1800fea3a  add     r14d, esi
0x1800fea3d  jmp     loc_1800FE989
0x1800fea42  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800fea49  mov     eax, [rbp+470h+var_4F0]
0x1800fea4c  mov     [rsp+570h+var_500], eax
0x1800fea50  mov     [rsp+570h+var_4F8], r13d
0x1800fea55  jz      loc_1800FECC5
0x1800fea5b  mov     rdx, 4000000000000800h; unsigned __int64
0x1800fea65  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800fea6c  jz      loc_1800FECC5
0x1800fea72  mov     rax, cs:qword_180169748
0x1800fea79  and     rax, rdx
0x1800fea7c  cmp     cs:qword_180169748, rax
0x1800fea83  jnz     loc_1800FECC5
0x1800fea89  lea     rcx, [rbp+470h+var_250]; unsigned __int16 *
0x1800fea90  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800fea95  lea     rax, [rbp+470h+var_250]
0x1800fea9c  inc     rbx
0x1800fea9f  cmp     [rax+rbx*2], r13w
0x1800feaa4  jnz     short loc_1800FEA9C
0x1800feaa6  lea     rax, [rbp+470h+var_250]
0x1800feaad  jmp     loc_1800FEC5C
0x1800feab2  mov     rcx, [rdi+0D8h]
  ... truncated ...
```
