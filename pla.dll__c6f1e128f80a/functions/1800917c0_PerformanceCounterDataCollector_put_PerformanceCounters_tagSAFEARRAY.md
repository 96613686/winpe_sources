# _PerformanceCounterDataCollector::put_PerformanceCounters(tagSAFEARRAY *)

- ea: `0x1800917c0`
- end: `0x180092024`
- name: `?put_PerformanceCounters@_PerformanceCounterDataCollector@@UEAAJPEAUtagSAFEARRAY@@@Z`
- size: `2148`
- prototype: `int(_PerformanceCounterDataCollector *__hidden this, struct tagSAFEARRAY *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x180018420`
- `0x1800198b0`
- `0x18002b3a0`
- `0x1800917c0`
- `0x18013aee0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180091cf0`
- `msvcrt!_wcsicmp` at `0x180091cf0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180091faa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180091faa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180091f81`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180091f81`
- `pdh!PdhTranslate009CounterW` at `0x180091d19`
- `pdh!PdhTranslate009CounterW` at `0x180091d19`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180091f93`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180091ff2`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180091f93`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180091ff2`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180091b18`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180091c30`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180091b18`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180091c30`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180091fc9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180091fdc`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180091fc9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180091fdc`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18009199f`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18009199f`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180091ba0`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180091ba0`

## pseudocode

```c
__int64 __fastcall _PerformanceCounterDataCollector::put_PerformanceCounters(
        _PerformanceCounterDataCollector *this,
        struct tagSAFEARRAY *a2)
{
  int v2; // eax
  SAFEARRAY *v5; // r15
  const unsigned __int16 *v6; // r12
  int v7; // ebx
  __int64 v8; // rax
  HRESULT Vartype; // eax
  __int64 v10; // rax
  __int64 v11; // rax
  HRESULT v12; // eax
  __int64 v13; // rax
  SAFEARRAY *Vector; // rax
  __int64 v15; // rax
  HRESULT v16; // eax
  __int64 v17; // rax
  ULONG v18; // esi
  const wchar_t **v19; // rcx
  __int64 v20; // rbx
  _WORD *v21; // rdx
  ULONG i; // r14d
  unsigned int v23; // eax
  int v24; // eax
  OLECHAR *v25; // rcx
  const char *v26; // rdx
  int v27; // r8d
  unsigned __int16 *v28; // rax
  __int64 v29; // rax
  const char *v30; // rdx
  int v31; // r8d
  unsigned __int16 *v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  SAFEARRAY *v36; // rcx
  int v38; // [rsp+20h] [rbp-E0h]
  __int64 v39; // [rsp+48h] [rbp-B8h]
  __int64 v40; // [rsp+50h] [rbp-B0h]
  int v41; // [rsp+70h] [rbp-90h] BYREF
  _PerformanceCounterDataCollector *v42; // [rsp+78h] [rbp-88h] BYREF
  VARTYPE pvt; // [rsp+80h] [rbp-80h] BYREF
  void *v44; // [rsp+88h] [rbp-78h] BYREF
  void *ppvData; // [rsp+90h] [rbp-70h] BYREF
  int v46; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v47[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v48[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v49[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v50[64]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v51[64]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v52[64]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v53[64]; // [rsp+3A0h] [rbp+2A0h] BYREF
  unsigned __int16 v54[64]; // [rsp+420h] [rbp+320h] BYREF
  unsigned __int16 v55[64]; // [rsp+4A0h] [rbp+3A0h] BYREF
  unsigned __int16 v56[64]; // [rsp+520h] [rbp+420h] BYREF

  v2 = *((_DWORD *)this + 14);
  pvt = 0;
  v46 = 0;
  v5 = 0;
  ppvData = 0;
  v44 = 0;
  v41 = v2;
  v42 = this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_METHOD,
      3,
      "_PerformanceCounterDataCollector::put_PerformanceCounters",
      58,
      &v42,
      8,
      &v41,
      4,
      v39,
      v40);
  }
  v6 = (const unsigned __int16 *)PlaiAlloc(0x800u, 1, 0, qword_180147320, v38);
  if ( v6 )
  {
    Vartype = SafeArrayGetVartype(a2, &pvt);
    v7 = Vartype;
    if ( Vartype >= 0 )
    {
      if ( pvt == 8 )
      {
        v12 = SafeArrayAccessData(a2, &ppvData);
        v7 = v12;
        if ( v12 >= 0 )
        {
          Vector = SafeArrayCreateVector(8u, 0, a2->rgsabound[0].cElements);
          v5 = Vector;
          if ( Vector )
          {
            v16 = SafeArrayAccessData(Vector, &v44);
            v7 = v16;
            if ( v16 >= 0 )
            {
              v18 = 0;
              while ( 2 )
              {
                if ( v18 >= a2->rgsabound[0].cElements )
                {
                  if ( *((_DWORD *)this + 2) )
                    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
                  v36 = (SAFEARRAY *)*((_QWORD *)this + 21);
                  if ( v36 )
                    SafeArrayDestroy(v36);
                  *((_QWORD *)this + 21) = v5;
                  if ( *((_DWORD *)this + 2) )
                    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
                  v7 = 0;
                  goto LABEL_89;
                }
                v19 = (const wchar_t **)ppvData;
                v20 = v18;
                v21 = (_WORD *)*((_QWORD *)ppvData + v18);
                if ( v21 && *v21 )
                {
                  for ( i = ++v18; i < a2->rgsabound[0].cElements; ++i )
                  {
                    if ( !_wcsicmp(v19[v20], v19[i]) )
                    {
                      v7 = -2144337651;
                      LODWORD(v42) = 0;
                      v41 = -2144337651;
                      if ( (_DWORD)xmmword_180169738
                        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                      {
                        PlaiWhoAmI(v53, 0x4000000000000800uLL);
                        v34 = -1;
                        do
                          ++v34;
                        while ( v53[v34] );
                        goto LABEL_18;
                      }
                      goto LABEL_89;
                    }
                    v19 = (const wchar_t **)ppvData;
                  }
                  v46 = 1024;
                  v23 = PdhTranslate009CounterW(v19[v20], v6, &v46);
                  v24 = PlaiHResultFromWin32(v23);
                  v25 = (OLECHAR *)*((_QWORD *)v44 + v20);
                  if ( v24 < 0 )
                  {
                    PlaiFreeString(v25);
                    *((_QWORD *)v44 + v20) = 0;
                    v32 = PlaiAllocStringEx(*((const unsigned __int16 **)ppvData + v20), v30, v31);
                    *((_QWORD *)v44 + v20) = v32;
                    if ( *((_QWORD *)v44 + v20) )
                      continue;
                    v7 = -2147024882;
                    v41 = -2147024882;
                    LODWORD(v42) = 0;
                    if ( (_DWORD)xmmword_180169738
                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                    {
                      PlaiWhoAmI(v55, 0x4000000000000800uLL);
                      v33 = -1;
                      do
                        ++v33;
                      while ( v55[v33] );
                      goto LABEL_18;
                    }
                  }
                  else
                  {
                    PlaiFreeString(v25);
                    *((_QWORD *)v44 + v20) = 0;
                    v28 = PlaiAllocStringEx(v6, v26, v27);
                    *((_QWORD *)v44 + v20) = v28;
                    if ( *((_QWORD *)v44 + v20) )
                      continue;
                    v7 = -2147024882;
                    v41 = -2147024882;
                    LODWORD(v42) = 0;
                    if ( (_DWORD)xmmword_180169738
                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                    {
                      PlaiWhoAmI(v54, 0x4000000000000800uLL);
                      v29 = -1;
                      do
                        ++v29;
                      while ( v54[v29] );
                      goto LABEL_18;
                    }
                  }
                  goto LABEL_89;
                }
                break;
              }
              v7 = -2147024809;
              v41 = -2147024809;
              LODWORD(v42) = 0;
              if ( !(_DWORD)xmmword_180169738
                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
              {
LABEL_89:
                PlaiFree(v6, 1);
                goto LABEL_90;
              }
              PlaiWhoAmI(v56, 0x4000000000000800uLL);
              v35 = -1;
              do
                ++v35;
              while ( v56[v35] );
            }
            else
            {
              LODWORD(v42) = 0;
              v41 = v16;
              if ( !(_DWORD)xmmword_180169738
                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
              {
                goto LABEL_89;
              }
              PlaiWhoAmI(v52, 0x4000000000000800uLL);
              v17 = -1;
              do
                ++v17;
              while ( v52[v17] );
            }
          }
          else
          {
            v7 = -2147024882;
            v41 = -2147024882;
            LODWORD(v42) = 0;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_89;
            }
            PlaiWhoAmI(v51, 0x4000000000000800uLL);
            v15 = -1;
            do
              ++v15;
            while ( v51[v15] );
          }
        }
        else
        {
          LODWORD(v42) = 0;
          v41 = v12;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_89;
          }
          PlaiWhoAmI(v50, 0x4000000000000800uLL);
          v13 = -1;
          do
            ++v13;
          while ( v50[v13] );
        }
      }
      else
      {
        v7 = PlaiHResultFromWin32(0x65Du);
        LODWORD(v42) = 0;
        v41 = v7;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_89;
        }
        PlaiWhoAmI(v49, 0x4000000000000800uLL);
        v11 = -1;
        do
          ++v11;
        while ( v49[v11] );
      }
    }
    else
    {
      LODWORD(v42) = 0;
      v41 = Vartype;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_89;
      }
      PlaiWhoAmI(v48, 0x4000000000000800uLL);
      v10 = -1;
      do
        ++v10;
      while ( v48[v10] );
    }
LABEL_18:
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v41,
      4,
      qword_180147320,
      1,
      &v42,
      4,
      "_PerformanceCounterDataCollector::put_PerformanceCounters",
      58);
    goto LABEL_89;
  }
  v7 = -2147024882;
  LODWORD(v42) = -2147024882;
  v41 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v47, 0x4000000000000800uLL);
    v8 = -1;
    do
      ++v8;
    while ( v47[v8] );
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v42,
      4,
      qword_180147320,
      1,
      &v41,
      4,
      "_PerformanceCounterDataCollector::put_PerformanceCounters",
      58);
  }
LABEL_90:
  if ( ppvData )
  {
    SafeArrayUnaccessData(a2);
    ppvData = 0;
  }
  if ( v44 )
  {
    SafeArrayUnaccessData(v5);
    v44 = 0;
  }
  if ( v7 < 0 && v5 )
    SafeArrayDestroy(v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800917c0  mov     [rsp-8+arg_10], rbx
0x1800917c5  push    rbp
0x1800917c6  push    rsi
0x1800917c7  push    rdi
0x1800917c8  push    r12
0x1800917ca  push    r13
0x1800917cc  push    r14
0x1800917ce  push    r15
0x1800917d0  lea     rbp, [rsp-4B0h]
0x1800917d8  sub     rsp, 5B0h
0x1800917df  mov     rax, cs:__security_cookie
0x1800917e6  xor     rax, rsp
0x1800917e9  mov     [rbp+4E0h+var_40], rax
0x1800917f0  mov     eax, [rcx+38h]
0x1800917f3  xor     r14d, r14d
0x1800917f6  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800917fd  mov     r13, rdx
0x180091800  mov     rdi, rcx
0x180091803  mov     [rbp+4E0h+pvt], r14w
0x180091808  mov     [rbp+4E0h+var_548], r14d
0x18009180c  mov     r15d, r14d
0x18009180f  lea     esi, [r14+8]
0x180091813  mov     [rbp+4E0h+ppvData], r14
0x180091817  mov     [rbp+4E0h+var_558], r14
0x18009181b  mov     [rsp+5E0h+var_570], eax
0x18009181f  mov     [rsp+5E0h+var_568], rcx
0x180091824  jz      short loc_180091895
0x180091826  mov     rdx, 4000000000000400h
0x180091830  test    qword ptr cs:xmmword_180169738+8, rdx
0x180091837  jz      short loc_180091895
0x180091839  mov     rax, cs:qword_180169748
0x180091840  and     rax, rdx
0x180091843  cmp     cs:qword_180169748, rax
0x18009184a  jnz     short loc_180091895
0x18009184c  mov     [rsp+5E0h+var_5A0], 4
0x180091855  lea     rax, [rsp+5E0h+var_570]
0x18009185a  mov     [rsp+5E0h+var_5A8], rax
0x18009185f  lea     r9, aPerformancecou_12; "_PerformanceCounterDataCollector::put_P"...
0x180091866  lea     rax, [rsp+5E0h+var_568]
0x18009186b  mov     [rsp+5E0h+var_5B0], rsi
0x180091870  mov     [rsp+5E0h+var_5B8], rax
0x180091875  lea     r8d, [r14+3]
0x180091879  lea     rdx, PLA_EVENT_METHOD
0x180091880  mov     qword ptr [rsp+5E0h+var_5C0], 3Ah ; ':'; int
0x180091889  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180091890  call    EventingWriteEvent
0x180091895  xor     r8d, r8d; int
0x180091898  lea     r9, qword_180147320; char *
0x18009189f  mov     ecx, 800h; dwBytes
0x1800918a4  lea     edx, [r8+1]; int
0x1800918a8  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800918ad  mov     r12, rax
0x1800918b0  test    rax, rax
0x1800918b3  jnz     loc_180091998
0x1800918b9  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800918c0  mov     eax, 8007000Eh
0x1800918c5  mov     ebx, eax
0x1800918c7  mov     dword ptr [rsp+5E0h+var_568], eax
0x1800918cb  mov     [rsp+5E0h+var_570], r14d
0x1800918d0  jz      loc_180091FC0
0x1800918d6  mov     rdx, 4000000000000800h; unsigned __int64
0x1800918e0  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800918e7  jz      loc_180091FC0
0x1800918ed  mov     rax, cs:qword_180169748
0x1800918f4  and     rax, rdx
0x1800918f7  cmp     cs:qword_180169748, rax
0x1800918fe  jnz     loc_180091FC0
0x180091904  lea     rcx, [rbp+4E0h+var_540]; unsigned __int16 *
0x180091908  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009190d  lea     rcx, [rbp+4E0h+var_540]
0x180091911  or      rax, 0FFFFFFFFFFFFFFFFh
0x180091915  inc     rax
0x180091918  cmp     [rcx+rax*2], r14w
0x18009191d  jnz     short loc_180091915
0x18009191f  lea     ecx, [rax+rax]
0x180091922  mov     edx, 4
0x180091927  add     rcx, 2
0x18009192b  lea     rax, [rbp+4E0h+var_540]
0x18009192f  mov     [rsp+5E0h+var_580], rcx
0x180091934  lea     r9, [rsp+5E0h+var_568]
0x180091939  mov     [rsp+5E0h+var_588], rax
0x18009193e  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180091945  mov     [rsp+5E0h+var_590], 3Ah ; ':'
0x18009194e  lea     rax, aPerformancecou_12; "_PerformanceCounterDataCollector::put_P"...
0x180091955  mov     [rsp+5E0h+var_598], rax
0x18009195a  lea     r8d, [rdx+1]
0x18009195e  mov     [rsp+5E0h+var_5A0], rdx
0x180091963  lea     rax, [rsp+5E0h+var_570]
0x180091968  mov     [rsp+5E0h+var_5A8], rax
0x18009196d  lea     rax, qword_180147320
0x180091974  mov     [rsp+5E0h+var_5B0], 1
0x18009197d  mov     [rsp+5E0h+var_5B8], rax
0x180091982  mov     qword ptr [rsp+5E0h+var_5C0], rdx
0x180091987  lea     rdx, PLA_EVENT_ERROR
0x18009198e  call    EventingWriteEvent
0x180091993  jmp     loc_180091FC0
0x180091998  lea     rdx, [rbp+4E0h+pvt]; pvt
0x18009199c  mov     rcx, r13; psa
0x18009199f  call    cs:__imp_SafeArrayGetVartype
0x1800919a5  mov     ebx, eax
0x1800919a7  test    eax, eax
0x1800919a9  jns     loc_180091A87
0x1800919af  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800919b6  mov     dword ptr [rsp+5E0h+var_568], r14d
0x1800919bb  mov     [rsp+5E0h+var_570], eax
0x1800919bf  jz      loc_180091FB3
0x1800919c5  mov     rdx, 4000000000000800h; unsigned __int64
0x1800919cf  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800919d6  jz      loc_180091FB3
0x1800919dc  mov     rax, cs:qword_180169748
0x1800919e3  and     rax, rdx
0x1800919e6  cmp     cs:qword_180169748, rax
0x1800919ed  jnz     loc_180091FB3
0x1800919f3  lea     rcx, [rbp+4E0h+var_4C0]; unsigned __int16 *
0x1800919f7  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800919fc  lea     rcx, [rbp+4E0h+var_4C0]
0x180091a00  or      rax, 0FFFFFFFFFFFFFFFFh
0x180091a04  inc     rax
0x180091a07  cmp     [rcx+rax*2], r14w
0x180091a0c  jnz     short loc_180091A04
0x180091a0e  lea     ecx, [rax+rax]
0x180091a11  lea     rax, [rbp+4E0h+var_4C0]
0x180091a15  mov     edx, 4
0x180091a1a  lea     r9, [rsp+5E0h+var_570]
0x180091a1f  add     rcx, 2
0x180091a23  mov     [rsp+5E0h+var_580], rcx
0x180091a28  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180091a2f  mov     [rsp+5E0h+var_588], rax
0x180091a34  lea     rax, aPerformancecou_12; "_PerformanceCounterDataCollector::put_P"...
0x180091a3b  mov     [rsp+5E0h+var_590], 3Ah ; ':'
0x180091a44  lea     r8d, [rdx+1]
0x180091a48  mov     [rsp+5E0h+var_598], rax
0x180091a4d  lea     rax, [rsp+5E0h+var_568]
0x180091a52  mov     [rsp+5E0h+var_5A0], rdx
0x180091a57  mov     [rsp+5E0h+var_5A8], rax
0x180091a5c  lea     rax, qword_180147320
0x180091a63  mov     [rsp+5E0h+var_5B0], 1
0x180091a6c  mov     [rsp+5E0h+var_5B8], rax
0x180091a71  mov     qword ptr [rsp+5E0h+var_5C0], rdx
0x180091a76  lea     rdx, PLA_EVENT_ERROR
0x180091a7d  call    EventingWriteEvent
0x180091a82  jmp     loc_180091FB3
0x180091a87  cmp     si, [rbp+4E0h+pvt]
0x180091a8b  jz      loc_180091B11
0x180091a91  mov     ecx, 65Dh; unsigned int
0x180091a96  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180091a9b  cmp     dword ptr cs:xmmword_180169738, r14d
0x180091aa2  mov     ebx, eax
0x180091aa4  mov     dword ptr [rsp+5E0h+var_568], r14d
0x180091aa9  mov     [rsp+5E0h+var_570], eax
0x180091aad  jz      loc_180091FB3
0x180091ab3  mov     rdx, 4000000000000800h; unsigned __int64
0x180091abd  test    qword ptr cs:xmmword_180169738+8, rdx
0x180091ac4  jz      loc_180091FB3
0x180091aca  mov     rax, cs:qword_180169748
0x180091ad1  and     rax, rdx
0x180091ad4  cmp     cs:qword_180169748, rax
0x180091adb  jnz     loc_180091FB3
0x180091ae1  lea     rcx, [rbp+4E0h+var_440]; unsigned __int16 *
0x180091ae8  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180091aed  lea     rcx, [rbp+4E0h+var_440]
0x180091af4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180091af8  inc     rax
0x180091afb  cmp     [rcx+rax*2], r14w
0x180091b00  jnz     short loc_180091AF8
0x180091b02  lea     ecx, [rax+rax]
0x180091b05  lea     rax, [rbp+4E0h+var_440]
0x180091b0c  jmp     loc_180091A15
0x180091b11  lea     rdx, [rbp+4E0h+ppvData]; ppvData
0x180091b15  mov     rcx, r13; psa
0x180091b18  call    cs:__imp_SafeArrayAccessData
0x180091b1e  mov     ebx, eax
0x180091b20  test    eax, eax
0x180091b22  jns     short loc_180091B98
0x180091b24  cmp     dword ptr cs:xmmword_180169738, r14d
0x180091b2b  mov     dword ptr [rsp+5E0h+var_568], r14d
0x180091b30  mov     [rsp+5E0h+var_570], eax
0x180091b34  jz      loc_180091FB3
0x180091b3a  mov     rdx, 4000000000000800h; unsigned __int64
0x180091b44  test    qword ptr cs:xmmword_180169738+8, rdx
0x180091b4b  jz      loc_180091FB3
0x180091b51  mov     rax, cs:qword_180169748
0x180091b58  and     rax, rdx
0x180091b5b  cmp     cs:qword_180169748, rax
0x180091b62  jnz     loc_180091FB3
0x180091b68  lea     rcx, [rbp+4E0h+var_3C0]; unsigned __int16 *
0x180091b6f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180091b74  lea     rcx, [rbp+4E0h+var_3C0]
0x180091b7b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180091b7f  inc     rax
0x180091b82  cmp     [rcx+rax*2], r14w
0x180091b87  jnz     short loc_180091B7F
0x180091b89  lea     ecx, [rax+rax]
0x180091b8c  lea     rax, [rbp+4E0h+var_3C0]
0x180091b93  jmp     loc_180091A15
0x180091b98  mov     r8d, [r13+18h]; cElements
0x180091b9c  mov     ecx, esi; vt
0x180091b9e  xor     edx, edx; lLbound
0x180091ba0  call    cs:__imp_SafeArrayCreateVector
0x180091ba6  mov     r15, rax
0x180091ba9  test    rax, rax
0x180091bac  jnz     short loc_180091C29
0x180091bae  cmp     dword ptr cs:xmmword_180169738, r14d
0x180091bb5  mov     eax, 8007000Eh
0x180091bba  mov     ebx, eax
0x180091bbc  mov     [rsp+5E0h+var_570], eax
0x180091bc0  mov     dword ptr [rsp+5E0h+var_568], r14d
0x180091bc5  jz      loc_180091FB3
0x180091bcb  mov     rdx, 4000000000000800h; unsigned __int64
0x180091bd5  test    qword ptr cs:xmmword_180169738+8, rdx
0x180091bdc  jz      loc_180091FB3
0x180091be2  mov     rax, cs:qword_180169748
0x180091be9  and     rax, rdx
0x180091bec  cmp     cs:qword_180169748, rax
0x180091bf3  jnz     loc_180091FB3
0x180091bf9  lea     rcx, [rbp+4E0h+var_340]; unsigned __int16 *
0x180091c00  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180091c05  lea     rcx, [rbp+4E0h+var_340]
0x180091c0c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180091c10  inc     rax
0x180091c13  cmp     [rcx+rax*2], r14w
0x180091c18  jnz     short loc_180091C10
0x180091c1a  lea     ecx, [rax+rax]
0x180091c1d  lea     rax, [rbp+4E0h+var_340]
0x180091c24  jmp     loc_180091A15
0x180091c29  lea     rdx, [rbp+4E0h+var_558]; ppvData
0x180091c2d  mov     rcx, r15; psa
0x180091c30  call    cs:__imp_SafeArrayAccessData
0x180091c36  mov     ebx, eax
0x180091c38  test    eax, eax
0x180091c3a  jns     short loc_180091CB0
0x180091c3c  cmp     dword ptr cs:xmmword_180169738, r14d
0x180091c43  mov     dword ptr [rsp+5E0h+var_568], r14d
0x180091c48  mov     [rsp+5E0h+var_570], eax
0x180091c4c  jz      loc_180091FB3
0x180091c52  mov     rdx, 4000000000000800h; unsigned __int64
0x180091c5c  test    qword ptr cs:xmmword_180169738+8, rdx
0x180091c63  jz      loc_180091FB3
0x180091c69  mov     rax, cs:qword_180169748
0x180091c70  and     rax, rdx
0x180091c73  cmp     cs:qword_180169748, rax
0x180091c7a  jnz     loc_180091FB3
0x180091c80  lea     rcx, [rbp+4E0h+var_2C0]; unsigned __int16 *
0x180091c87  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180091c8c  lea     rcx, [rbp+4E0h+var_2C0]
0x180091c93  or      rax, 0FFFFFFFFFFFFFFFFh
0x180091c97  inc     rax
0x180091c9a  cmp     [rcx+rax*2], r14w
0x180091c9f  jnz     short loc_180091C97
0x180091ca1  lea     ecx, [rax+rax]
0x180091ca4  lea     rax, [rbp+4E0h+var_2C0]
0x180091cab  jmp     loc_180091A15
0x180091cb0  mov     esi, r14d
0x180091cb3  cmp     esi, [r13+18h]
0x180091cb7  jnb     loc_180091F77
0x180091cbd  mov     rcx, [rbp+4E0h+ppvData]
0x180091cc1  mov     ebx, esi
0x180091cc3  mov     rdx, [rcx+rbx*8]
0x180091cc7  test    rdx, rdx
0x180091cca  jz      loc_180091F06
0x180091cd0  cmp     r14w, [rdx]
0x180091cd4  jz      loc_180091F06
0x180091cda  inc     esi
0x180091cdc  mov     r14d, esi
0x180091cdf  cmp     r14d, [r13+18h]
0x180091ce3  jnb     short loc_180091D07
0x180091ce5  mov     edx, r14d
0x180091ce8  mov     rdx, [rcx+rdx*8]; String2
0x180091cec  mov     rcx, [rcx+rbx*8]; String1
0x180091cf0  call    cs:__imp__wcsicmp
0x180091cf6  test    eax, eax
0x180091cf8  jz      loc_180091E8A
0x180091cfe  mov     rcx, [rbp+4E0h+ppvData]
0x180091d02  inc     r14d
0x180091d05  jmp     short loc_180091CDF
0x180091d07  mov     [rbp+4E0h+var_548], 400h
0x180091d0e  lea     r8, [rbp+4E0h+var_548]
0x180091d12  mov     rcx, [rcx+rbx*8]
0x180091d16  mov     rdx, r12
0x180091d19  call    cs:__imp_PdhTranslate009CounterW
0x180091d1f  mov     ecx, eax; unsigned int
0x180091d21  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180091d26  mov     rcx, [rbp+4E0h+var_558]
0x180091d2a  xor     r14d, r14d
0x180091d2d  mov     rcx, [rcx+rbx*8]; bstrString
0x180091d31  test    eax, eax
0x180091d33  js      loc_180091DDF
0x180091d39  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x180091d3e  mov     rax, [rbp+4E0h+var_558]
0x180091d42  mov     rcx, r12; unsigned __int16 *
0x180091d45  mov     [rax+rbx*8], r14
0x180091d49  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x180091d4e  mov     rcx, [rbp+4E0h+var_558]
0x180091d52  mov     [rcx+rbx*8], rax
0x180091d56  mov     rax, [rbp+4E0h+var_558]
0x180091d5a  cmp     [rax+rbx*8], r14
0x180091d5e  jnz     loc_180091CB3
0x180091d64  cmp     dword ptr cs:xmmword_180169738, r14d
0x180091d6b  mov     eax, 8007000Eh
0x180091d70  mov     ebx, eax
  ... truncated ...
```
