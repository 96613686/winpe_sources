# _AlertDataCollector::put_AlertThresholds(tagSAFEARRAY *)

- ea: `0x1800f9060`
- end: `0x1800f9a58`
- name: `?put_AlertThresholds@_AlertDataCollector@@UEAAJPEAUtagSAFEARRAY@@@Z`
- size: `2552`
- prototype: `int(_AlertDataCollector *__hidden this, struct tagSAFEARRAY *)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x180018420`
- `0x1800198b0`
- `0x18002b3a0`
- `0x1800f9060`
- `0x180116404`
- `0x18013aee0`

## import_xrefs

- `msvcrt!wcscspn` at `0x1800f9580`
- `msvcrt!wcscspn` at `0x1800f9580`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f99dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f99dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f99b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f99b4`
- `pdh!PdhTranslate009CounterW` at `0x1800f95e6`
- `pdh!PdhTranslate009CounterW` at `0x1800f95e6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800f99c6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800f9a26`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800f99c6`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800f9a26`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f93ae`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f94c0`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f93ae`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800f94c0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f99fd`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f9a10`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f99fd`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800f9a10`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800f923f`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800f923f`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800f9433`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800f9433`

## pseudocode

```c
__int64 __fastcall _AlertDataCollector::put_AlertThresholds(_AlertDataCollector *this, struct tagSAFEARRAY *a2)
{
  int v2; // eax
  struct tagSAFEARRAY *v3; // rsi
  SAFEARRAY *v5; // r13
  int v6; // ebx
  __int64 v7; // rdi
  HRESULT Vartype; // eax
  __int64 v9; // rdi
  __int64 v10; // rdi
  HRESULT v11; // eax
  __int64 v12; // rdi
  SAFEARRAY *Vector; // rax
  __int64 v14; // rdi
  HRESULT v15; // eax
  __int64 v16; // rdi
  ULONG v17; // r12d
  __int64 v18; // rdi
  const wchar_t *v19; // rcx
  size_t v20; // rbx
  unsigned __int64 v21; // rcx
  unsigned __int16 *i; // rsi
  unsigned __int16 v23; // bx
  LPCVOID v24; // rdx
  unsigned int v25; // eax
  int v26; // eax
  const char *v27; // rdx
  int v28; // r8d
  unsigned __int16 *v29; // rax
  const unsigned __int16 *v30; // r8
  const unsigned __int16 *v31; // rsi
  int v32; // eax
  const char *v33; // rdx
  int v34; // r8d
  unsigned __int16 *v35; // rax
  SAFEARRAY *v36; // rcx
  int v38; // [rsp+20h] [rbp-E0h]
  __int64 v39; // [rsp+48h] [rbp-B8h]
  __int64 v40; // [rsp+50h] [rbp-B0h]
  int v41; // [rsp+70h] [rbp-90h] BYREF
  int v42; // [rsp+78h] [rbp-88h] BYREF
  VARTYPE pvt; // [rsp+80h] [rbp-80h] BYREF
  void *v44; // [rsp+88h] [rbp-78h] BYREF
  struct tagSAFEARRAY *v45; // [rsp+90h] [rbp-70h]
  void *ppvData; // [rsp+98h] [rbp-68h] BYREF
  int v47; // [rsp+A0h] [rbp-60h] BYREF
  LPCVOID lpMem; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 v49[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v50[64]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v51[64]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v52[64]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v53[64]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v54[64]; // [rsp+330h] [rbp+230h] BYREF
  unsigned __int16 v55[64]; // [rsp+3B0h] [rbp+2B0h] BYREF
  unsigned __int16 v56[64]; // [rsp+430h] [rbp+330h] BYREF
  unsigned __int16 v57[64]; // [rsp+4B0h] [rbp+3B0h] BYREF
  unsigned __int16 v58[64]; // [rsp+530h] [rbp+430h] BYREF
  unsigned __int16 v59[64]; // [rsp+5B0h] [rbp+4B0h] BYREF

  v2 = *((_DWORD *)this + 14);
  v3 = a2;
  v45 = a2;
  pvt = 0;
  v5 = 0;
  v47 = 0;
  ppvData = 0;
  v44 = 0;
  v41 = v2;
  lpMem = this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_METHOD,
      3,
      "_AlertDataCollector::put_AlertThresholds",
      41,
      &lpMem,
      8,
      &v41,
      4,
      v39,
      v40);
  }
  lpMem = PlaiAlloc(0x800u, 1, 0, qword_180147320, v38);
  if ( lpMem )
  {
    Vartype = SafeArrayGetVartype(v3, &pvt);
    v6 = Vartype;
    if ( Vartype < 0 )
    {
      v42 = 0;
      v41 = Vartype;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_103;
      }
      PlaiWhoAmI(v50, 0x4000000000000800uLL);
      v9 = -1;
      do
        ++v9;
      while ( v50[v9] );
      goto LABEL_95;
    }
    if ( pvt != 8 )
    {
      v6 = PlaiHResultFromWin32(0x65Du);
      v42 = 0;
      v41 = v6;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_103;
      }
      PlaiWhoAmI(v51, 0x4000000000000800uLL);
      v10 = -1;
      do
        ++v10;
      while ( v51[v10] );
      goto LABEL_95;
    }
    v11 = SafeArrayAccessData(v3, &ppvData);
    v6 = v11;
    if ( v11 < 0 )
    {
      v42 = 0;
      v41 = v11;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_103;
      }
      PlaiWhoAmI(v52, 0x4000000000000800uLL);
      v12 = -1;
      do
        ++v12;
      while ( v52[v12] );
      goto LABEL_95;
    }
    Vector = SafeArrayCreateVector(8u, 0, v3->rgsabound[0].cElements);
    v5 = Vector;
    if ( !Vector )
    {
      v6 = -2147024882;
      v41 = -2147024882;
      v42 = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_103;
      }
      PlaiWhoAmI(v53, 0x4000000000000800uLL);
      v14 = -1;
      do
        ++v14;
      while ( v53[v14] );
      goto LABEL_95;
    }
    v15 = SafeArrayAccessData(Vector, &v44);
    v6 = v15;
    if ( v15 < 0 )
    {
      v42 = 0;
      v41 = v15;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_103;
      }
      PlaiWhoAmI(v54, 0x4000000000000800uLL);
      v16 = -1;
      do
        ++v16;
      while ( v54[v16] );
      goto LABEL_95;
    }
    v17 = 0;
    v18 = -1;
    while ( 2 )
    {
      if ( v17 >= v3->rgsabound[0].cElements )
      {
        if ( *((_DWORD *)this + 2) )
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
        v36 = (SAFEARRAY *)*((_QWORD *)this + 20);
        if ( v36 )
          SafeArrayDestroy(v36);
        *((_QWORD *)this + 20) = v5;
        if ( *((_DWORD *)this + 2) )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
        v6 = 0;
        goto LABEL_103;
      }
      v19 = (const wchar_t *)*((_QWORD *)ppvData + v17);
      if ( !v19 )
        goto LABEL_90;
      v20 = -1;
      do
        ++v20;
      while ( v19[v20] );
      if ( !v20 || wcscspn(v19, L"*?") < v20 )
      {
LABEL_90:
        v6 = -2147024809;
        v42 = 0;
        v41 = -2147024809;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_103;
        }
        PlaiWhoAmI(v59, 0x4000000000000800uLL);
        do
          ++v18;
        while ( v59[v18] );
LABEL_95:
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
          "_AlertDataCollector::put_AlertThresholds",
          41);
        goto LABEL_103;
      }
      v21 = *((_QWORD *)ppvData + v17);
      for ( i = (unsigned __int16 *)(v21 + 2 * (v20 - 1)); (unsigned __int64)i > v21; --i )
      {
        if ( *i == 62 )
          goto LABEL_60;
        if ( *i == 60 )
          break;
      }
      if ( (unsigned __int64)i > v21 )
      {
LABEL_60:
        v23 = *i;
        v24 = lpMem;
        *i = 0;
        v47 = 1024;
        v25 = PdhTranslate009CounterW(*((_QWORD *)ppvData + v17), v24, &v47);
        v26 = PlaiHResultFromWin32(v25);
        *i = v23;
        if ( v26 >= 0 )
        {
          v30 = i;
          v31 = (const unsigned __int16 *)lpMem;
          v32 = StringCchCatW((unsigned __int16 *)lpMem, 0x400u, v30);
          v6 = v32;
          if ( v32 < 0 )
          {
            v41 = v32;
            v42 = 0;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_89;
            }
            PlaiWhoAmI(v57, 0x4000000000000800uLL);
            do
              ++v18;
            while ( v57[v18] );
            goto LABEL_88;
          }
          PlaiFreeString(*((BSTR *)v44 + v17));
          *((_QWORD *)v44 + v17) = 0;
          v35 = PlaiAllocStringEx(v31, v33, v34);
          *((_QWORD *)v44 + v17) = v35;
          if ( !*((_QWORD *)v44 + v17) )
          {
            v6 = -2147024882;
            v42 = 0;
            v41 = -2147024882;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_89;
            }
            PlaiWhoAmI(v56, 0x4000000000000800uLL);
            do
              ++v18;
            while ( v56[v18] );
            goto LABEL_88;
          }
        }
        else
        {
          PlaiFreeString(*((BSTR *)v44 + v17));
          *((_QWORD *)v44 + v17) = 0;
          v29 = PlaiAllocStringEx(*((const unsigned __int16 **)ppvData + v17), v27, v28);
          *((_QWORD *)v44 + v17) = v29;
          if ( !*((_QWORD *)v44 + v17) )
          {
            v6 = -2147024882;
            v42 = 0;
            v41 = -2147024882;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_89;
            }
            PlaiWhoAmI(v55, 0x4000000000000800uLL);
            do
              ++v18;
            while ( v55[v18] );
LABEL_88:
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
              "_AlertDataCollector::put_AlertThresholds",
              41);
LABEL_89:
            v3 = v45;
LABEL_103:
            PlaiFree(lpMem, 1);
            goto LABEL_104;
          }
        }
        v3 = v45;
        ++v17;
        continue;
      }
      break;
    }
    v6 = -2147024809;
    v42 = 0;
    v41 = -2147024809;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_89;
    }
    PlaiWhoAmI(v58, 0x4000000000000800uLL);
    do
      ++v18;
    while ( v58[v18] );
    goto LABEL_88;
  }
  v6 = -2147024882;
  v42 = -2147024882;
  v41 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v49, 0x4000000000000800uLL);
    v7 = -1;
    do
      ++v7;
    while ( v49[v7] );
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
      "_AlertDataCollector::put_AlertThresholds",
      41);
  }
LABEL_104:
  if ( ppvData )
  {
    SafeArrayUnaccessData(v3);
    ppvData = 0;
  }
  if ( v44 )
  {
    SafeArrayUnaccessData(v5);
    v44 = 0;
  }
  if ( v6 < 0 && v5 )
    SafeArrayDestroy(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800f9060  mov     [rsp-8+arg_10], rbx
0x1800f9065  push    rbp
0x1800f9066  push    rsi
0x1800f9067  push    rdi
0x1800f9068  push    r12
0x1800f906a  push    r13
0x1800f906c  push    r14
0x1800f906e  push    r15
0x1800f9070  lea     rbp, [rsp-540h]
0x1800f9078  sub     rsp, 640h
0x1800f907f  mov     rax, cs:__security_cookie
0x1800f9086  xor     rax, rsp
0x1800f9089  mov     [rbp+570h+var_40], rax
0x1800f9090  mov     eax, [rcx+38h]
0x1800f9093  xor     r15d, r15d
0x1800f9096  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f909d  mov     rsi, rdx
0x1800f90a0  mov     [rbp+570h+var_5E0], rdx
0x1800f90a4  mov     r14, rcx
0x1800f90a7  mov     [rbp+570h+pvt], r15w
0x1800f90ac  mov     r13d, r15d
0x1800f90af  lea     edi, [r15+8]
0x1800f90b3  mov     [rbp+570h+var_5D0], r15d
0x1800f90b7  lea     r12d, [r15+4]
0x1800f90bb  mov     [rbp+570h+ppvData], r15
0x1800f90bf  mov     [rbp+570h+var_5E8], r15
0x1800f90c3  mov     [rsp+670h+var_600], eax
0x1800f90c7  mov     [rbp+570h+lpMem], rcx
0x1800f90cb  jz      short loc_1800F9137
0x1800f90cd  mov     rdx, 4000000000000400h
0x1800f90d7  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f90de  jz      short loc_1800F9137
0x1800f90e0  mov     rax, cs:qword_180169748
0x1800f90e7  and     rax, rdx
0x1800f90ea  cmp     cs:qword_180169748, rax
0x1800f90f1  jnz     short loc_1800F9137
0x1800f90f3  mov     [rsp+670h+var_630], r12
0x1800f90f8  lea     rax, [rsp+670h+var_600]
0x1800f90fd  mov     [rsp+670h+var_638], rax
0x1800f9102  lea     r9, aAlertdatacolle_3; "_AlertDataCollector::put_AlertThreshold"...
0x1800f9109  lea     rax, [rbp+570h+lpMem]
0x1800f910d  mov     [rsp+670h+var_640], rdi
0x1800f9112  mov     [rsp+670h+var_648], rax
0x1800f9117  lea     r8d, [r15+3]
0x1800f911b  lea     rdx, PLA_EVENT_METHOD
0x1800f9122  mov     qword ptr [rsp+670h+var_650], 29h ; ')'; int
0x1800f912b  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800f9132  call    EventingWriteEvent
0x1800f9137  xor     r8d, r8d; int
0x1800f913a  lea     r9, qword_180147320; char *
0x1800f9141  mov     ecx, 800h; dwBytes
0x1800f9146  lea     edx, [r8+1]; int
0x1800f914a  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800f914f  mov     [rbp+570h+lpMem], rax
0x1800f9153  test    rax, rax
0x1800f9156  jnz     loc_1800F9238
0x1800f915c  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f9163  mov     eax, 8007000Eh
0x1800f9168  mov     ebx, eax
0x1800f916a  mov     [rsp+670h+var_5F8], eax
0x1800f916e  mov     [rsp+670h+var_600], r15d
0x1800f9173  jz      loc_1800F99F4
0x1800f9179  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f9183  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f918a  jz      loc_1800F99F4
0x1800f9190  mov     rax, cs:qword_180169748
0x1800f9197  and     rax, rdx
0x1800f919a  cmp     cs:qword_180169748, rax
0x1800f91a1  jnz     loc_1800F99F4
0x1800f91a7  lea     rcx, [rbp+570h+var_5C0]; unsigned __int16 *
0x1800f91ab  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f91b0  lea     rax, [rbp+570h+var_5C0]
0x1800f91b4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800f91b8  inc     rdi
0x1800f91bb  cmp     [rax+rdi*2], r15w
0x1800f91c0  jnz     short loc_1800F91B8
0x1800f91c2  lea     rax, [rbp+570h+var_5C0]
0x1800f91c6  mov     r8d, 5
0x1800f91cc  lea     ecx, [rdi+rdi]
0x1800f91cf  add     rcx, 2
0x1800f91d3  lea     r9, [rsp+670h+var_5F8]
0x1800f91d8  mov     [rsp+670h+var_610], rcx
0x1800f91dd  lea     rdx, PLA_EVENT_ERROR
0x1800f91e4  mov     [rsp+670h+var_618], rax
0x1800f91e9  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800f91f0  mov     [rsp+670h+var_620], 29h ; ')'
0x1800f91f9  lea     rax, aAlertdatacolle_3; "_AlertDataCollector::put_AlertThreshold"...
0x1800f9200  mov     [rsp+670h+var_628], rax
0x1800f9205  lea     rax, [rsp+670h+var_600]
0x1800f920a  mov     [rsp+670h+var_630], r12
0x1800f920f  mov     [rsp+670h+var_638], rax
0x1800f9214  lea     rax, qword_180147320
0x1800f921b  mov     [rsp+670h+var_640], 1
0x1800f9224  mov     [rsp+670h+var_648], rax
0x1800f9229  mov     qword ptr [rsp+670h+var_650], r12
0x1800f922e  call    EventingWriteEvent
0x1800f9233  jmp     loc_1800F99F4
0x1800f9238  lea     rdx, [rbp+570h+pvt]; pvt
0x1800f923c  mov     rcx, rsi; psa
0x1800f923f  call    cs:__imp_SafeArrayGetVartype
0x1800f9245  mov     ebx, eax
0x1800f9247  test    eax, eax
0x1800f9249  jns     loc_1800F9324
0x1800f924f  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f9256  mov     [rsp+670h+var_5F8], r15d
0x1800f925b  mov     [rsp+670h+var_600], eax
0x1800f925f  jz      loc_1800F99E6
0x1800f9265  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f926f  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f9276  jz      loc_1800F99E6
0x1800f927c  mov     rax, cs:qword_180169748
0x1800f9283  and     rax, rdx
0x1800f9286  cmp     cs:qword_180169748, rax
0x1800f928d  jnz     loc_1800F99E6
0x1800f9293  lea     rcx, [rbp+570h+var_540]; unsigned __int16 *
0x1800f9297  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f929c  lea     rax, [rbp+570h+var_540]
0x1800f92a0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800f92a4  inc     rdi
0x1800f92a7  cmp     [rax+rdi*2], r15w
0x1800f92ac  jnz     short loc_1800F92A4
0x1800f92ae  lea     rax, [rbp+570h+var_540]
0x1800f92b2  lea     ecx, [rdi+rdi]
0x1800f92b5  add     rcx, 2
0x1800f92b9  mov     [rsp+670h+var_610], rcx
0x1800f92be  mov     [rsp+670h+var_618], rax
0x1800f92c3  lea     rax, aAlertdatacolle_3; "_AlertDataCollector::put_AlertThreshold"...
0x1800f92ca  mov     [rsp+670h+var_620], 29h ; ')'
0x1800f92d3  mov     [rsp+670h+var_628], rax
0x1800f92d8  lea     rax, [rsp+670h+var_5F8]
0x1800f92dd  mov     [rsp+670h+var_630], r12
0x1800f92e2  mov     [rsp+670h+var_638], rax
0x1800f92e7  lea     rax, qword_180147320
0x1800f92ee  mov     [rsp+670h+var_640], 1
0x1800f92f7  mov     [rsp+670h+var_648], rax
0x1800f92fc  mov     qword ptr [rsp+670h+var_650], r12
0x1800f9301  lea     r9, [rsp+670h+var_600]
0x1800f9306  mov     r8d, 5
0x1800f930c  lea     rdx, PLA_EVENT_ERROR
0x1800f9313  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800f931a  call    EventingWriteEvent
0x1800f931f  jmp     loc_1800F99E6
0x1800f9324  cmp     di, [rbp+570h+pvt]
0x1800f9328  jz      short loc_1800F93A7
0x1800f932a  mov     ecx, 65Dh; unsigned int
0x1800f932f  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800f9334  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f933b  mov     ebx, eax
0x1800f933d  mov     [rsp+670h+var_5F8], r15d
0x1800f9342  mov     [rsp+670h+var_600], eax
0x1800f9346  jz      loc_1800F99E6
0x1800f934c  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f9356  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f935d  jz      loc_1800F99E6
0x1800f9363  mov     rax, cs:qword_180169748
0x1800f936a  and     rax, rdx
0x1800f936d  cmp     cs:qword_180169748, rax
0x1800f9374  jnz     loc_1800F99E6
0x1800f937a  lea     rcx, [rbp+570h+var_4C0]; unsigned __int16 *
0x1800f9381  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f9386  lea     rax, [rbp+570h+var_4C0]
0x1800f938d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800f9391  inc     rdi
0x1800f9394  cmp     [rax+rdi*2], r15w
0x1800f9399  jnz     short loc_1800F9391
0x1800f939b  lea     rax, [rbp+570h+var_4C0]
0x1800f93a2  jmp     loc_1800F92B2
0x1800f93a7  lea     rdx, [rbp+570h+ppvData]; ppvData
0x1800f93ab  mov     rcx, rsi; psa
0x1800f93ae  call    cs:__imp_SafeArrayAccessData
0x1800f93b4  mov     ebx, eax
0x1800f93b6  test    eax, eax
0x1800f93b8  jns     short loc_1800F942B
0x1800f93ba  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f93c1  mov     [rsp+670h+var_5F8], r15d
0x1800f93c6  mov     [rsp+670h+var_600], eax
0x1800f93ca  jz      loc_1800F99E6
0x1800f93d0  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f93da  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f93e1  jz      loc_1800F99E6
0x1800f93e7  mov     rax, cs:qword_180169748
0x1800f93ee  and     rax, rdx
0x1800f93f1  cmp     cs:qword_180169748, rax
0x1800f93f8  jnz     loc_1800F99E6
0x1800f93fe  lea     rcx, [rbp+570h+var_440]; unsigned __int16 *
0x1800f9405  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f940a  lea     rax, [rbp+570h+var_440]
0x1800f9411  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800f9415  inc     rdi
0x1800f9418  cmp     [rax+rdi*2], r15w
0x1800f941d  jnz     short loc_1800F9415
0x1800f941f  lea     rax, [rbp+570h+var_440]
0x1800f9426  jmp     loc_1800F92B2
0x1800f942b  mov     r8d, [rsi+18h]; cElements
0x1800f942f  mov     ecx, edi; vt
0x1800f9431  xor     edx, edx; lLbound
0x1800f9433  call    cs:__imp_SafeArrayCreateVector
0x1800f9439  mov     r13, rax
0x1800f943c  test    rax, rax
0x1800f943f  jnz     short loc_1800F94B9
0x1800f9441  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f9448  mov     eax, 8007000Eh
0x1800f944d  mov     ebx, eax
0x1800f944f  mov     [rsp+670h+var_600], eax
0x1800f9453  mov     [rsp+670h+var_5F8], r15d
0x1800f9458  jz      loc_1800F99E6
0x1800f945e  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f9468  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f946f  jz      loc_1800F99E6
0x1800f9475  mov     rax, cs:qword_180169748
0x1800f947c  and     rax, rdx
0x1800f947f  cmp     cs:qword_180169748, rax
0x1800f9486  jnz     loc_1800F99E6
0x1800f948c  lea     rcx, [rbp+570h+var_3C0]; unsigned __int16 *
0x1800f9493  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f9498  lea     rax, [rbp+570h+var_3C0]
0x1800f949f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800f94a3  inc     rdi
0x1800f94a6  cmp     [rax+rdi*2], r15w
0x1800f94ab  jnz     short loc_1800F94A3
0x1800f94ad  lea     rax, [rbp+570h+var_3C0]
0x1800f94b4  jmp     loc_1800F92B2
0x1800f94b9  lea     rdx, [rbp+570h+var_5E8]; ppvData
0x1800f94bd  mov     rcx, r13; psa
0x1800f94c0  call    cs:__imp_SafeArrayAccessData
0x1800f94c6  mov     ebx, eax
0x1800f94c8  test    eax, eax
0x1800f94ca  jns     short loc_1800F953D
0x1800f94cc  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800f94d3  mov     [rsp+670h+var_5F8], r15d
0x1800f94d8  mov     [rsp+670h+var_600], eax
0x1800f94dc  jz      loc_1800F99E6
0x1800f94e2  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f94ec  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f94f3  jz      loc_1800F99E6
0x1800f94f9  mov     rax, cs:qword_180169748
0x1800f9500  and     rax, rdx
0x1800f9503  cmp     cs:qword_180169748, rax
0x1800f950a  jnz     loc_1800F99E6
0x1800f9510  lea     rcx, [rbp+570h+var_340]; unsigned __int16 *
0x1800f9517  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f951c  lea     rax, [rbp+570h+var_340]
0x1800f9523  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800f9527  inc     rdi
0x1800f952a  cmp     [rax+rdi*2], r15w
0x1800f952f  jnz     short loc_1800F9527
0x1800f9531  lea     rax, [rbp+570h+var_340]
0x1800f9538  jmp     loc_1800F92B2
0x1800f953d  mov     r12d, r15d
0x1800f9540  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800f9544  cmp     r12d, [rsi+18h]
0x1800f9548  jnb     loc_1800F99A7
0x1800f954e  mov     rax, [rbp+570h+ppvData]
0x1800f9552  mov     r15d, r12d
0x1800f9555  mov     rcx, [rax+r15*8]; String
0x1800f9559  xor     eax, eax
0x1800f955b  test    rcx, rcx
0x1800f955e  jz      loc_1800F98DC
0x1800f9564  mov     rbx, rdi
0x1800f9567  inc     rbx
0x1800f956a  cmp     [rcx+rbx*2], ax
0x1800f956e  jnz     short loc_1800F9567
0x1800f9570  test    rbx, rbx
0x1800f9573  jz      loc_1800F98DC
0x1800f9579  lea     rdx, Control; "*?"
0x1800f9580  call    cs:__imp_wcscspn
0x1800f9586  cmp     rax, rbx
0x1800f9589  jb      loc_1800F98DC
0x1800f958f  mov     rax, [rbp+570h+ppvData]
0x1800f9593  lea     rsi, [rbx-1]
0x1800f9597  mov     rcx, [rax+r15*8]
0x1800f959b  lea     rsi, [rcx+rsi*2]
0x1800f959f  jmp     short loc_1800F95B9
0x1800f95a1  mov     eax, 3Eh ; '>'
0x1800f95a6  cmp     ax, [rsi]
0x1800f95a9  jz      short loc_1800F95C7
0x1800f95ab  mov     eax, 3Ch ; '<'
0x1800f95b0  cmp     ax, [rsi]
0x1800f95b3  jz      short loc_1800F95BE
0x1800f95b5  sub     rsi, 2
0x1800f95b9  cmp     rsi, rcx
0x1800f95bc  ja      short loc_1800F95A1
0x1800f95be  cmp     rsi, rcx
0x1800f95c1  jbe     loc_1800F97F1
0x1800f95c7  movzx   ebx, word ptr [rsi]
0x1800f95ca  lea     r8, [rbp+570h+var_5D0]
0x1800f95ce  mov     rdx, [rbp+570h+lpMem]
0x1800f95d2  xor     eax, eax
0x1800f95d4  mov     [rsi], ax
0x1800f95d7  mov     rcx, [rbp+570h+ppvData]
0x1800f95db  mov     [rbp+570h+var_5D0], 400h
0x1800f95e2  mov     rcx, [rcx+r15*8]
0x1800f95e6  call    cs:__imp_PdhTranslate009CounterW
0x1800f95ec  mov     ecx, eax; unsigned int
0x1800f95ee  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800f95f3  mov     [rsi], bx
0x1800f95f6  xor     ebx, ebx
0x1800f95f8  test    eax, eax
0x1800f95fa  jns     loc_1800F96AF
0x1800f9600  mov     rcx, [rbp+570h+var_5E8]
  ... truncated ...
```
