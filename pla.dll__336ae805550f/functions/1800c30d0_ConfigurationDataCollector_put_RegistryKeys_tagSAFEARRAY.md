# _ConfigurationDataCollector::put_RegistryKeys(tagSAFEARRAY *)

- ea: `0x1800c30d0`
- end: `0x1800c3a23`
- name: `?put_RegistryKeys@_ConfigurationDataCollector@@UEAAJPEAUtagSAFEARRAY@@@Z`
- size: `2387`
- prototype: `int(_ConfigurationDataCollector *__hidden this, struct tagSAFEARRAY *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800198b0`
- `0x18002b3a0`
- `0x180056190`
- `0x1800c30d0`
- `0x180114a94`
- `0x180116460`
- `0x18013aee0`

## import_xrefs

- `msvcrt!wcschr` at `0x1800c346a`
- `msvcrt!wcschr` at `0x1800c346a`
- `msvcrt!_wcsicmp` at `0x1800c3752`
- `msvcrt!_wcsicmp` at `0x1800c3752`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c39d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c39d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c3833`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c3833`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c3941`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c3956`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c3941`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c3956`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c3375`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c3375`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c39f1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c39f1`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800c3844`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800c3844`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800c31bb`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800c31bb`

## string_xrefs

- `0x1800c3182`: `_ConfigurationDataCollector::put_RegistryKeys`
- `0x1800c3244`: `_ConfigurationDataCollector::put_RegistryKeys`
- `0x1800c3333`: `_ConfigurationDataCollector::put_RegistryKeys`
- `0x1800c37ea`: `_ConfigurationDataCollector::put_RegistryKeys`
- `0x1800c38e9`: `_ConfigurationDataCollector::put_RegistryKeys`

## pseudocode

```c
__int64 __fastcall _ConfigurationDataCollector::put_RegistryKeys(
        _ConfigurationDataCollector *this,
        struct tagSAFEARRAY *a2)
{
  int v2; // eax
  HRESULT Vartype; // eax
  HRESULT v6; // ebx
  __int64 v7; // rax
  HKEY *v8; // r9
  __int64 v9; // rax
  HRESULT v10; // eax
  __int64 v11; // rax
  ULONG v12; // esi
  ULONG cElements; // eax
  unsigned __int16 *v14; // rcx
  int v15; // eax
  int v16; // eax
  const wchar_t *v17; // rbx
  wchar_t *k; // r11
  wchar_t *v19; // rax
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  ULONG i; // esi
  __int64 j; // rbx
  __int64 v28; // rax
  HRESULT v29; // eax
  __int64 v30; // rax
  SAFEARRAY *v31; // rcx
  __int64 v32; // rax
  HKEY *v34; // [rsp+38h] [rbp-C8h]
  int v35; // [rsp+70h] [rbp-90h] BYREF
  HKEY v36; // [rsp+78h] [rbp-88h] BYREF
  VARTYPE pvt; // [rsp+80h] [rbp-80h] BYREF
  SAFEARRAY *ppsaOut; // [rsp+88h] [rbp-78h] BYREF
  void *ppvData; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v40; // [rsp+98h] [rbp-68h] BYREF
  BSTR bstrString[2]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *Str[2]; // [rsp+B0h] [rbp-50h]
  __int128 v43; // [rsp+C0h] [rbp-40h]
  unsigned __int16 v44[64]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v45[64]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v46[64]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int16 v47[64]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 v48[64]; // [rsp+2D0h] [rbp+1D0h] BYREF
  unsigned __int16 v49[64]; // [rsp+350h] [rbp+250h] BYREF
  unsigned __int16 v50[64]; // [rsp+3D0h] [rbp+2D0h] BYREF
  unsigned __int16 v51[64]; // [rsp+450h] [rbp+350h] BYREF
  unsigned __int16 v52[64]; // [rsp+4D0h] [rbp+3D0h] BYREF
  unsigned __int16 v53[64]; // [rsp+550h] [rbp+450h] BYREF
  unsigned __int16 v54[64]; // [rsp+5D0h] [rbp+4D0h] BYREF

  v2 = *((_DWORD *)this + 14);
  pvt = 0;
  ppvData = 0;
  v36 = 0;
  v40 = 0;
  v35 = v2;
  *(_OWORD *)bstrString = 0;
  ppsaOut = (SAFEARRAY *)this;
  *(_OWORD *)Str = 0;
  v43 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(
      &g_Eventing,
      &PLA_EVENT_METHOD,
      3,
      "_ConfigurationDataCollector::put_RegistryKeys",
      46,
      &ppsaOut,
      8,
      &v35,
      4);
  }
  Vartype = SafeArrayGetVartype(a2, &pvt);
  v6 = Vartype;
  if ( Vartype < 0 )
  {
    v35 = 0;
    LODWORD(v36) = Vartype;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_106;
    }
    PlaiWhoAmI(v44, 0x4000000000000800uLL);
    v7 = -1;
    do
      ++v7;
    while ( v44[v7] );
    v8 = &v36;
    v34 = (HKEY *)&v35;
    goto LABEL_12;
  }
  if ( pvt != 8 )
  {
    v6 = PlaiHResultFromWin32(0x65Du);
    LODWORD(v36) = 0;
    v35 = v6;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_106;
    }
    PlaiWhoAmI(v45, 0x4000000000000800uLL);
    v9 = -1;
    do
      ++v9;
    while ( v45[v9] );
LABEL_19:
    v34 = &v36;
    goto LABEL_20;
  }
  v10 = SafeArrayAccessData(a2, &ppvData);
  v6 = v10;
  if ( v10 < 0 )
  {
    LODWORD(v36) = 0;
    v35 = v10;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_106;
    }
    PlaiWhoAmI(v46, 0x4000000000000800uLL);
    v11 = -1;
    do
      ++v11;
    while ( v46[v11] );
    goto LABEL_19;
  }
  v12 = 0;
LABEL_29:
  cElements = a2->rgsabound[0].cElements;
  if ( v12 >= cElements )
  {
    for ( i = 0; i < cElements; ++i )
    {
      for ( j = i + 1; ; j = (unsigned int)(j + 1) )
      {
        cElements = a2->rgsabound[0].cElements;
        if ( (unsigned int)j >= cElements )
          break;
        if ( !_wcsicmp(*((const wchar_t **)ppvData + i), *((const wchar_t **)ppvData + j)) )
        {
          v6 = -2144337651;
          v35 = -2144337651;
          LODWORD(v36) = 0;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_106;
          }
          PlaiWhoAmI(v52, 0x4000000000000800uLL);
          v28 = -1;
          do
            ++v28;
          while ( v52[v28] );
          v34 = &v36;
LABEL_20:
          v8 = (HKEY *)&v35;
LABEL_12:
          EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v8, 4, byte_180147320, 1, v34, 4);
          goto LABEL_106;
        }
      }
    }
    if ( *((_DWORD *)this + 2) )
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    ppsaOut = 0;
    v29 = SafeArrayCopy(a2, &ppsaOut);
    v6 = v29;
    if ( v29 >= 0 )
    {
      v31 = (SAFEARRAY *)*((_QWORD *)this + 21);
      if ( v31 )
      {
        v6 = SafeArrayDestroy(v31);
        if ( v6 < 0 )
        {
          if ( ppsaOut )
            SafeArrayDestroy(ppsaOut);
          LODWORD(v36) = 0;
          v35 = v6;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_104;
          }
          PlaiWhoAmI(v54, 0x4000000000000800uLL);
          v32 = -1;
          do
            ++v32;
          while ( v54[v32] );
          goto LABEL_92;
        }
      }
      *((_QWORD *)this + 21) = ppsaOut;
    }
    else
    {
      LODWORD(v36) = 0;
      v35 = v29;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v53, 0x4000000000000800uLL);
        v30 = -1;
        do
          ++v30;
        while ( v53[v30] );
LABEL_92:
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v35, 4, byte_180147320, 1, &v36, 4);
      }
    }
LABEL_104:
    if ( *((_DWORD *)this + 2) )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    goto LABEL_106;
  }
  v14 = (unsigned __int16 *)*((_QWORD *)ppvData + v12);
  if ( !v14 || !*v14 )
  {
    v6 = -2147024809;
    v35 = -2147024809;
    LODWORD(v36) = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_106;
    }
    PlaiWhoAmI(v51, 0x4000000000000800uLL);
    v25 = -1;
    do
      ++v25;
    while ( v51[v25] );
    goto LABEL_19;
  }
  v15 = ParsePath(v14, (struct _QUERY_PATH *)bstrString);
  v6 = v15;
  if ( v15 < 0 )
  {
    LODWORD(v36) = 0;
    v35 = v15;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_106;
    }
    PlaiWhoAmI(v50, 0x4000000000000800uLL);
    v24 = -1;
    do
      ++v24;
    while ( v50[v24] );
    goto LABEL_19;
  }
  v16 = PlaiStringToRegKey(Str[0], &v36);
  v6 = v16;
  if ( v16 < 0 )
  {
    LODWORD(v36) = 0;
    v35 = v16;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_106;
    }
    PlaiWhoAmI(v49, 0x4000000000000800uLL);
    v23 = -1;
    do
      ++v23;
    while ( v49[v23] );
    goto LABEL_19;
  }
  v17 = Str[1];
  for ( k = Str[1]; ; v17 = k + 1 )
  {
    if ( !k )
    {
      PlaiFreeString(bstrString[0]);
      ++v12;
      bstrString[0] = 0;
      goto LABEL_29;
    }
    v19 = wcschr(v17, 0x5Cu);
    k = v19;
    if ( !v19 )
      break;
    if ( (__int64)(((char *)v19 - (char *)v17) & 0xFFFFFFFFFFFFFFFEuLL) > 508 )
    {
      v6 = -2147024809;
      v35 = -2147024809;
      LODWORD(v36) = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v47, 0x4000000000000800uLL);
        v20 = -1;
        do
          ++v20;
        while ( v47[v20] );
        goto LABEL_19;
      }
      goto LABEL_106;
    }
LABEL_45:
    ;
  }
  v21 = StringCchLengthW(v17, 0xFEu, &v40);
  v6 = v21;
  if ( v21 >= 0 )
    goto LABEL_45;
  LODWORD(v36) = 0;
  v35 = v21;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v48, 0x4000000000000800uLL);
    v22 = -1;
    do
      ++v22;
    while ( v48[v22] );
    goto LABEL_19;
  }
LABEL_106:
  PlaiFreeString(bstrString[0]);
  if ( ppvData )
    SafeArrayUnaccessData(a2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800c30d0  mov     [rsp-8+arg_10], rbx
0x1800c30d5  push    rbp
0x1800c30d6  push    rsi
0x1800c30d7  push    rdi
0x1800c30d8  push    r12
0x1800c30da  push    r13
0x1800c30dc  push    r14
0x1800c30de  push    r15
0x1800c30e0  lea     rbp, [rsp-560h]
0x1800c30e8  sub     rsp, 660h
0x1800c30ef  mov     rax, cs:__security_cookie
0x1800c30f6  xor     rax, rsp
0x1800c30f9  mov     [rbp+590h+var_40], rax
0x1800c3100  mov     eax, [rcx+38h]
0x1800c3103  xor     r12d, r12d
0x1800c3106  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800c310d  xorps   xmm0, xmm0
0x1800c3110  mov     r13, rdx
0x1800c3113  mov     [rbp+590h+pvt], r12w
0x1800c3118  mov     rdi, rcx
0x1800c311b  mov     [rbp+590h+ppvData], r12
0x1800c311f  lea     esi, [r12+8]
0x1800c3124  mov     [rsp+690h+var_618], r12
0x1800c3129  lea     r14d, [r12+4]
0x1800c312e  mov     [rbp+590h+var_5F8], r12
0x1800c3132  lea     r15d, [r12+2Eh]
0x1800c3137  mov     [rsp+690h+var_620], eax
0x1800c313b  movups  xmmword ptr [rbp+590h+bstrString], xmm0
0x1800c313f  mov     [rbp+590h+ppsaOut], rcx
0x1800c3143  movups  xmmword ptr [rbp+590h+Str], xmm0
0x1800c3147  movups  [rbp+590h+var_5D0], xmm0
0x1800c314b  jz      short loc_1800C31B4
0x1800c314d  mov     rdx, 4000000000000400h
0x1800c3157  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c315e  jz      short loc_1800C31B4
0x1800c3160  mov     rax, cs:qword_180169748
0x1800c3167  and     rax, rdx
0x1800c316a  cmp     cs:qword_180169748, rax
0x1800c3171  jnz     short loc_1800C31B4
0x1800c3173  mov     [rsp+690h+var_650], r14
0x1800c3178  lea     rax, [rsp+690h+var_620]
0x1800c317d  mov     [rsp+690h+var_658], rax
0x1800c3182  lea     r9, aConfigurationd_5; "_ConfigurationDataCollector::put_Regist"...
0x1800c3189  lea     rax, [rbp+590h+ppsaOut]
0x1800c318d  mov     [rsp+690h+var_660], rsi
0x1800c3192  mov     [rsp+690h+var_668], rax
0x1800c3197  lea     r8d, [r12+3]
0x1800c319c  lea     rdx, PLA_EVENT_METHOD
0x1800c31a3  mov     [rsp+690h+var_670], r15
0x1800c31a8  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800c31af  call    EventingWriteEvent
0x1800c31b4  lea     rdx, [rbp+590h+pvt]; pvt
0x1800c31b8  mov     rcx, r13; psa
0x1800c31bb  call    cs:__imp_SafeArrayGetVartype
0x1800c31c1  mov     ebx, eax
0x1800c31c3  test    eax, eax
0x1800c31c5  jns     loc_1800C329E
0x1800c31cb  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800c31d2  mov     [rsp+690h+var_620], r12d
0x1800c31d7  mov     dword ptr [rsp+690h+var_618], eax
0x1800c31db  jz      loc_1800C39DF
0x1800c31e1  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c31eb  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c31f2  jz      loc_1800C39DF
0x1800c31f8  mov     rax, cs:qword_180169748
0x1800c31ff  and     rax, rdx
0x1800c3202  cmp     cs:qword_180169748, rax
0x1800c3209  jnz     loc_1800C39DF
0x1800c320f  lea     rcx, [rbp+590h+var_5C0]; unsigned __int16 *
0x1800c3213  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c3218  lea     rcx, [rbp+590h+var_5C0]
0x1800c321c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c3220  inc     rax
0x1800c3223  cmp     [rcx+rax*2], r12w
0x1800c3228  jnz     short loc_1800C3220
0x1800c322a  lea     ecx, [rax+rax]
0x1800c322d  lea     rax, [rbp+590h+var_5C0]
0x1800c3231  add     rcx, 2
0x1800c3235  mov     [rsp+690h+var_630], rcx
0x1800c323a  lea     r9, [rsp+690h+var_618]
0x1800c323f  mov     [rsp+690h+var_638], rax
0x1800c3244  lea     rax, aConfigurationd_5; "_ConfigurationDataCollector::put_Regist"...
0x1800c324b  mov     [rsp+690h+var_640], r15
0x1800c3250  mov     r15d, 1
0x1800c3256  mov     [rsp+690h+var_648], rax
0x1800c325b  lea     rax, [rsp+690h+var_620]
0x1800c3260  mov     [rsp+690h+var_650], r14
0x1800c3265  mov     [rsp+690h+var_658], rax
0x1800c326a  lea     rax, byte_180147320
0x1800c3271  mov     [rsp+690h+var_660], r15
0x1800c3276  mov     [rsp+690h+var_668], rax
0x1800c327b  mov     [rsp+690h+var_670], r14
0x1800c3280  mov     r8d, 5
0x1800c3286  lea     rdx, PLA_EVENT_ERROR
0x1800c328d  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800c3294  call    EventingWriteEvent
0x1800c3299  jmp     loc_1800C39DF
0x1800c329e  cmp     si, [rbp+590h+pvt]
0x1800c32a2  jz      loc_1800C336E
0x1800c32a8  mov     ecx, 65Dh; unsigned int
0x1800c32ad  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800c32b2  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800c32b9  mov     ebx, eax
0x1800c32bb  mov     dword ptr [rsp+690h+var_618], r12d
0x1800c32c0  mov     [rsp+690h+var_620], eax
0x1800c32c4  jz      loc_1800C39DF
0x1800c32ca  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c32d4  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c32db  jz      loc_1800C39DF
0x1800c32e1  mov     rax, cs:qword_180169748
0x1800c32e8  and     rax, rdx
0x1800c32eb  cmp     cs:qword_180169748, rax
0x1800c32f2  jnz     loc_1800C39DF
0x1800c32f8  lea     rcx, [rbp+590h+var_540]; unsigned __int16 *
0x1800c32fc  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c3301  lea     rcx, [rbp+590h+var_540]
0x1800c3305  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c3309  inc     rax
0x1800c330c  cmp     [rcx+rax*2], r12w
0x1800c3311  jnz     short loc_1800C3309
0x1800c3313  lea     ecx, [rax+rax]
0x1800c3316  lea     rax, [rbp+590h+var_540]
0x1800c331a  add     rcx, 2
0x1800c331e  mov     [rsp+690h+var_630], rcx
0x1800c3323  mov     [rsp+690h+var_638], rax
0x1800c3328  mov     [rsp+690h+var_640], r15
0x1800c332d  mov     r15d, 1
0x1800c3333  lea     rax, aConfigurationd_5; "_ConfigurationDataCollector::put_Regist"...
0x1800c333a  mov     [rsp+690h+var_648], rax
0x1800c333f  lea     rax, [rsp+690h+var_618]
0x1800c3344  mov     [rsp+690h+var_650], r14
0x1800c3349  mov     [rsp+690h+var_658], rax
0x1800c334e  lea     rax, byte_180147320
0x1800c3355  mov     [rsp+690h+var_660], r15
0x1800c335a  mov     [rsp+690h+var_668], rax
0x1800c335f  mov     [rsp+690h+var_670], r14
0x1800c3364  lea     r9, [rsp+690h+var_620]
0x1800c3369  jmp     loc_1800C3280
0x1800c336e  lea     rdx, [rbp+590h+ppvData]; ppvData
0x1800c3372  mov     rcx, r13; psa
0x1800c3375  call    cs:__imp_SafeArrayAccessData
0x1800c337b  mov     ebx, eax
0x1800c337d  test    eax, eax
0x1800c337f  jns     short loc_1800C33F5
0x1800c3381  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800c3388  mov     dword ptr [rsp+690h+var_618], r12d
0x1800c338d  mov     [rsp+690h+var_620], eax
0x1800c3391  jz      loc_1800C39DF
0x1800c3397  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c33a1  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c33a8  jz      loc_1800C39DF
0x1800c33ae  mov     rax, cs:qword_180169748
0x1800c33b5  and     rax, rdx
0x1800c33b8  cmp     cs:qword_180169748, rax
0x1800c33bf  jnz     loc_1800C39DF
0x1800c33c5  lea     rcx, [rbp+590h+var_4C0]; unsigned __int16 *
0x1800c33cc  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c33d1  lea     rcx, [rbp+590h+var_4C0]
0x1800c33d8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c33dc  inc     rax
0x1800c33df  cmp     [rcx+rax*2], r12w
0x1800c33e4  jnz     short loc_1800C33DC
0x1800c33e6  lea     ecx, [rax+rax]
0x1800c33e9  lea     rax, [rbp+590h+var_4C0]
0x1800c33f0  jmp     loc_1800C331A
0x1800c33f5  mov     esi, r12d
0x1800c33f8  mov     r15d, 1
0x1800c33fe  mov     eax, [r13+18h]
0x1800c3402  cmp     esi, eax
0x1800c3404  jnb     loc_1800C372E
0x1800c340a  mov     rax, [rbp+590h+ppvData]
0x1800c340e  mov     ecx, esi
0x1800c3410  mov     rcx, [rax+rcx*8]; unsigned __int16 *
0x1800c3414  test    rcx, rcx
0x1800c3417  jz      loc_1800C369C
0x1800c341d  cmp     r12w, [rcx]
0x1800c3421  jz      loc_1800C369C
0x1800c3427  lea     rdx, [rbp+590h+bstrString]; struct _QUERY_PATH *
0x1800c342b  call    ?ParsePath@@YAJPEAGPEAU_QUERY_PATH@@@Z; ParsePath(ushort *,_QUERY_PATH *)
0x1800c3430  mov     ebx, eax
0x1800c3432  test    eax, eax
0x1800c3434  js      loc_1800C362B
0x1800c343a  mov     rcx, [rbp+590h+Str]; String1
0x1800c343e  lea     rdx, [rsp+690h+var_618]; HKEY *
0x1800c3443  call    ?PlaiStringToRegKey@@YAJPEBGPEAPEAUHKEY__@@@Z; PlaiStringToRegKey(ushort const *,HKEY__ * *)
0x1800c3448  mov     ebx, eax
0x1800c344a  test    eax, eax
0x1800c344c  js      loc_1800C35B7
0x1800c3452  mov     rbx, [rbp+590h+Str+8]
0x1800c3456  mov     r11, rbx
0x1800c3459  test    r11, r11
0x1800c345c  jz      loc_1800C352E
0x1800c3462  mov     edx, 5Ch ; '\'; Ch
0x1800c3467  mov     rcx, rbx; Str
0x1800c346a  call    cs:__imp_wcschr
0x1800c3470  mov     r11, rax
0x1800c3473  test    rax, rax
0x1800c3476  jz      loc_1800C350E
0x1800c347c  mov     rcx, rax
0x1800c347f  sub     rcx, rbx
0x1800c3482  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1800c3486  cmp     rcx, 1FCh
0x1800c348d  jle     loc_1800C3525
0x1800c3493  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800c349a  mov     eax, 80070057h
0x1800c349f  mov     ebx, eax
0x1800c34a1  mov     [rsp+690h+var_620], eax
0x1800c34a5  mov     dword ptr [rsp+690h+var_618], r12d
0x1800c34aa  jz      loc_1800C39DF
0x1800c34b0  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c34ba  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c34c1  jz      loc_1800C39DF
0x1800c34c7  mov     rax, cs:qword_180169748
0x1800c34ce  and     rax, rdx
0x1800c34d1  cmp     cs:qword_180169748, rax
0x1800c34d8  jnz     loc_1800C39DF
0x1800c34de  lea     rcx, [rbp+590h+var_440]; unsigned __int16 *
0x1800c34e5  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c34ea  lea     rcx, [rbp+590h+var_440]
0x1800c34f1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c34f5  inc     rax
0x1800c34f8  cmp     [rcx+rax*2], r12w
0x1800c34fd  jnz     short loc_1800C34F5
0x1800c34ff  lea     ecx, [rax+rax]
0x1800c3502  lea     rax, [rbp+590h+var_440]
0x1800c3509  jmp     loc_1800C3712
0x1800c350e  lea     r8, [rbp+590h+var_5F8]; unsigned __int64 *
0x1800c3512  mov     edx, 0FEh; unsigned __int64
0x1800c3517  mov     rcx, rbx; unsigned __int16 *
0x1800c351a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800c351f  mov     ebx, eax
0x1800c3521  test    eax, eax
0x1800c3523  js      short loc_1800C3543
0x1800c3525  lea     rbx, [r11+2]
0x1800c3529  jmp     loc_1800C3459
0x1800c352e  mov     rcx, [rbp+590h+bstrString]; bstrString
0x1800c3532  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x1800c3537  add     esi, r15d
0x1800c353a  mov     [rbp+590h+bstrString], r12
0x1800c353e  jmp     loc_1800C33FE
0x1800c3543  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800c354a  mov     dword ptr [rsp+690h+var_618], r12d
0x1800c354f  mov     [rsp+690h+var_620], eax
0x1800c3553  jz      loc_1800C39DF
0x1800c3559  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c3563  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c356a  jz      loc_1800C39DF
0x1800c3570  mov     rax, cs:qword_180169748
0x1800c3577  and     rax, rdx
0x1800c357a  cmp     cs:qword_180169748, rax
0x1800c3581  jnz     loc_1800C39DF
0x1800c3587  lea     rcx, [rbp+590h+var_3C0]; unsigned __int16 *
0x1800c358e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c3593  lea     rcx, [rbp+590h+var_3C0]
0x1800c359a  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c359e  inc     rax
0x1800c35a1  cmp     [rcx+rax*2], r12w
0x1800c35a6  jnz     short loc_1800C359E
0x1800c35a8  lea     ecx, [rax+rax]
0x1800c35ab  lea     rax, [rbp+590h+var_3C0]
0x1800c35b2  jmp     loc_1800C3712
0x1800c35b7  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800c35be  mov     dword ptr [rsp+690h+var_618], r12d
0x1800c35c3  mov     [rsp+690h+var_620], eax
0x1800c35c7  jz      loc_1800C39DF
0x1800c35cd  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c35d7  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c35de  jz      loc_1800C39DF
0x1800c35e4  mov     rax, cs:qword_180169748
0x1800c35eb  and     rax, rdx
0x1800c35ee  cmp     cs:qword_180169748, rax
0x1800c35f5  jnz     loc_1800C39DF
0x1800c35fb  lea     rcx, [rbp+590h+var_340]; unsigned __int16 *
0x1800c3602  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c3607  lea     rcx, [rbp+590h+var_340]
0x1800c360e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c3612  inc     rax
0x1800c3615  cmp     [rcx+rax*2], r12w
0x1800c361a  jnz     short loc_1800C3612
0x1800c361c  lea     ecx, [rax+rax]
0x1800c361f  lea     rax, [rbp+590h+var_340]
0x1800c3626  jmp     loc_1800C3712
0x1800c362b  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800c3632  mov     dword ptr [rsp+690h+var_618], r12d
0x1800c3637  mov     [rsp+690h+var_620], eax
0x1800c363b  jz      loc_1800C39DF
0x1800c3641  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c364b  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c3652  jz      loc_1800C39DF
0x1800c3658  mov     rax, cs:qword_180169748
0x1800c365f  and     rax, rdx
0x1800c3662  cmp     cs:qword_180169748, rax
0x1800c3669  jnz     loc_1800C39DF
0x1800c366f  lea     rcx, [rbp+590h+var_2C0]; unsigned __int16 *
0x1800c3676  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c367b  lea     rcx, [rbp+590h+var_2C0]
0x1800c3682  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c3686  inc     rax
0x1800c3689  cmp     [rcx+rax*2], r12w
0x1800c368e  jnz     short loc_1800C3686
  ... truncated ...
```
