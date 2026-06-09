# _PerformanceCounterDataCollector::get_PerformanceCounters(tagSAFEARRAY * *)

- ea: `0x18007cce0`
- end: `0x18007d2db`
- name: `?get_PerformanceCounters@_PerformanceCounterDataCollector@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `1531`
- prototype: `__int64 __fastcall(_PerformanceCounterDataCollector *__hidden this, struct tagSAFEARRAY **)`
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
- `0x18007cce0`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d25b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d25b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cebd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cebd`
- `pdh!PdhTranslateLocaleCounterW` at `0x18007d0cc`
- `pdh!PdhTranslateLocaleCounterW` at `0x18007d0cc`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18007d2a9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18007d2a9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18007cedb`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18007d022`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18007cedb`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18007d022`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18007d280`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18007d293`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18007d280`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18007d293`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18007cf92`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18007cf92`

## pseudocode

```c
__int64 __fastcall _PerformanceCounterDataCollector::get_PerformanceCounters(
        _PerformanceCounterDataCollector *this,
        struct tagSAFEARRAY **a2)
{
  int v2; // eax
  unsigned int v3; // r14d
  SAFEARRAY *v6; // r12
  const unsigned __int16 *v7; // r13
  int v8; // esi
  __int64 v9; // rax
  SAFEARRAY *v10; // rcx
  HRESULT v11; // eax
  __int64 v12; // rax
  SAFEARRAY *Vector; // rax
  __int64 v14; // rax
  HRESULT v15; // eax
  __int64 v16; // rax
  unsigned int v17; // eax
  int v18; // eax
  OLECHAR *v19; // rcx
  const char *v20; // rdx
  int v21; // r8d
  unsigned __int16 *v22; // rax
  __int64 v23; // rax
  const char *v24; // rdx
  int v25; // r8d
  unsigned __int16 *v26; // rax
  __int64 v27; // rax
  int v29; // [rsp+20h] [rbp-E0h]
  __int64 v30; // [rsp+48h] [rbp-B8h]
  __int64 v31; // [rsp+50h] [rbp-B0h]
  int v32; // [rsp+70h] [rbp-90h] BYREF
  _PerformanceCounterDataCollector *v33; // [rsp+78h] [rbp-88h] BYREF
  void *v34; // [rsp+80h] [rbp-80h] BYREF
  int v35; // [rsp+88h] [rbp-78h] BYREF
  void *ppvData; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v37[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v38[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v39[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v40[64]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v41[64]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v42[64]; // [rsp+320h] [rbp+220h] BYREF

  v2 = *((_DWORD *)this + 14);
  v3 = 0;
  v35 = 0;
  ppvData = 0;
  v6 = 0;
  v34 = 0;
  v32 = v2;
  v33 = this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_METHOD,
      3,
      "_PerformanceCounterDataCollector::get_PerformanceCounters",
      58,
      &v33,
      8,
      &v32,
      4,
      v30,
      v31);
  }
  v7 = (const unsigned __int16 *)PlaiAlloc(0x800u, 1, 0, qword_180147320, v29);
  if ( !v7 )
  {
    v8 = -2147024882;
    LODWORD(v33) = -2147024882;
    v32 = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v37, 0x4000000000000800uLL);
      v9 = -1;
      do
        ++v9;
      while ( v37[v9] );
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
        "_PerformanceCounterDataCollector::get_PerformanceCounters",
        58);
    }
    goto LABEL_56;
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v10 = (SAFEARRAY *)*((_QWORD *)this + 21);
  if ( !v10 )
  {
    *a2 = 0;
LABEL_55:
    v8 = 0;
    goto LABEL_56;
  }
  v11 = SafeArrayAccessData(v10, &ppvData);
  v8 = v11;
  if ( v11 < 0 )
  {
    LODWORD(v33) = 0;
    v32 = v11;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_56;
    }
    PlaiWhoAmI(v38, 0x4000000000000800uLL);
    v12 = -1;
    do
      ++v12;
    while ( v38[v12] );
    goto LABEL_22;
  }
  Vector = SafeArrayCreateVector(8u, 0, *(_DWORD *)(*((_QWORD *)this + 21) + 24LL));
  v6 = Vector;
  if ( !Vector )
  {
    v8 = -2147024882;
    v32 = -2147024882;
    LODWORD(v33) = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_56;
    }
    PlaiWhoAmI(v39, 0x4000000000000800uLL);
    v14 = -1;
    do
      ++v14;
    while ( v39[v14] );
    goto LABEL_22;
  }
  v15 = SafeArrayAccessData(Vector, &v34);
  v8 = v15;
  if ( v15 < 0 )
  {
    LODWORD(v33) = 0;
    v32 = v15;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_56;
    }
    PlaiWhoAmI(v40, 0x4000000000000800uLL);
    v16 = -1;
    do
      ++v16;
    while ( v40[v16] );
LABEL_22:
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
      "_PerformanceCounterDataCollector::get_PerformanceCounters",
      58);
    goto LABEL_56;
  }
  while ( 1 )
  {
    if ( v3 >= *(_DWORD *)(*((_QWORD *)this + 21) + 24LL) )
    {
      *a2 = v6;
      goto LABEL_55;
    }
    v35 = 1024;
    v17 = PdhTranslateLocaleCounterW(*((_QWORD *)ppvData + v3), v7, &v35);
    v18 = PlaiHResultFromWin32(v17);
    v19 = (OLECHAR *)*((_QWORD *)v34 + v3);
    if ( v18 < 0 )
      break;
    PlaiFreeString(v19);
    *((_QWORD *)v34 + v3) = 0;
    v22 = PlaiAllocStringEx(v7, v20, v21);
    *((_QWORD *)v34 + v3) = v22;
    if ( !*((_QWORD *)v34 + v3) )
    {
      v8 = -2147024882;
      LODWORD(v33) = 0;
      v32 = -2147024882;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v41, 0x4000000000000800uLL);
        v23 = -1;
        do
          ++v23;
        while ( v41[v23] );
        goto LABEL_22;
      }
      goto LABEL_56;
    }
LABEL_47:
    ++v3;
  }
  PlaiFreeString(v19);
  *((_QWORD *)v34 + v3) = 0;
  v26 = PlaiAllocStringEx(*((const unsigned __int16 **)ppvData + v3), v24, v25);
  *((_QWORD *)v34 + v3) = v26;
  if ( *((_QWORD *)v34 + v3) )
    goto LABEL_47;
  v8 = -2147024882;
  LODWORD(v33) = 0;
  v32 = -2147024882;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v42, 0x4000000000000800uLL);
    v27 = -1;
    do
      ++v27;
    while ( v42[v27] );
    goto LABEL_22;
  }
LABEL_56:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v7 )
    PlaiFree(v7, 1);
  if ( ppvData )
  {
    SafeArrayUnaccessData(*((SAFEARRAY **)this + 21));
    ppvData = 0;
  }
  if ( v34 )
  {
    SafeArrayUnaccessData(v6);
    v34 = 0;
  }
  if ( v8 < 0 && v6 )
    SafeArrayDestroy(v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18007cce0  mov     [rsp-8+arg_10], rbx
0x18007cce5  push    rbp
0x18007cce6  push    rsi
0x18007cce7  push    rdi
0x18007cce8  push    r12
0x18007ccea  push    r13
0x18007ccec  push    r14
0x18007ccee  push    r15
0x18007ccf0  lea     rbp, [rsp-2B0h]
0x18007ccf8  sub     rsp, 3B0h
0x18007ccff  mov     rax, cs:__security_cookie
0x18007cd06  xor     rax, rsp
0x18007cd09  mov     [rbp+2E0h+var_40], rax
0x18007cd10  mov     eax, [rcx+38h]
0x18007cd13  xor     r14d, r14d
0x18007cd16  cmp     dword ptr cs:xmmword_180169738, r14d
0x18007cd1d  mov     r15, rdx
0x18007cd20  mov     rdi, rcx
0x18007cd23  mov     [rbp+2E0h+var_358], r14d
0x18007cd27  mov     [rbp+2E0h+ppvData], r14
0x18007cd2b  mov     r12d, r14d
0x18007cd2e  lea     ebx, [r14+8]
0x18007cd32  mov     [rbp+2E0h+var_360], r14
0x18007cd36  mov     [rsp+3E0h+var_370], eax
0x18007cd3a  mov     [rsp+3E0h+var_368], rcx
0x18007cd3f  jz      short loc_18007CDB0
0x18007cd41  mov     rdx, 4000000000000400h
0x18007cd4b  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007cd52  jz      short loc_18007CDB0
0x18007cd54  mov     rax, cs:qword_180169748
0x18007cd5b  and     rax, rdx
0x18007cd5e  cmp     cs:qword_180169748, rax
0x18007cd65  jnz     short loc_18007CDB0
0x18007cd67  mov     [rsp+3E0h+var_3A0], 4
0x18007cd70  lea     rax, [rsp+3E0h+var_370]
0x18007cd75  mov     [rsp+3E0h+var_3A8], rax
0x18007cd7a  lea     r9, aPerformancecou_4; "_PerformanceCounterDataCollector::get_P"...
0x18007cd81  lea     rax, [rsp+3E0h+var_368]
0x18007cd86  mov     [rsp+3E0h+var_3B0], rbx
0x18007cd8b  mov     [rsp+3E0h+var_3B8], rax
0x18007cd90  lea     r8d, [r14+3]
0x18007cd94  lea     rdx, PLA_EVENT_METHOD
0x18007cd9b  mov     qword ptr [rsp+3E0h+var_3C0], 3Ah ; ':'; int
0x18007cda4  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18007cdab  call    EventingWriteEvent
0x18007cdb0  xor     r8d, r8d; int
0x18007cdb3  lea     r9, qword_180147320; char *
0x18007cdba  mov     ecx, 800h; dwBytes
0x18007cdbf  lea     edx, [r8+1]; int
0x18007cdc3  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x18007cdc8  mov     r13, rax
0x18007cdcb  test    rax, rax
0x18007cdce  jnz     loc_18007CEB3
0x18007cdd4  cmp     dword ptr cs:xmmword_180169738, r14d
0x18007cddb  mov     eax, 8007000Eh
0x18007cde0  mov     esi, eax
0x18007cde2  mov     dword ptr [rsp+3E0h+var_368], eax
0x18007cde6  mov     [rsp+3E0h+var_370], r14d
0x18007cdeb  jz      loc_18007D24B
0x18007cdf1  mov     rdx, 4000000000000800h; unsigned __int64
0x18007cdfb  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007ce02  jz      loc_18007D24B
0x18007ce08  mov     rax, cs:qword_180169748
0x18007ce0f  and     rax, rdx
0x18007ce12  cmp     cs:qword_180169748, rax
0x18007ce19  jnz     loc_18007D24B
0x18007ce1f  lea     rcx, [rbp+2E0h+var_340]; unsigned __int16 *
0x18007ce23  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18007ce28  lea     rcx, [rbp+2E0h+var_340]
0x18007ce2c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007ce30  inc     rax
0x18007ce33  cmp     [rcx+rax*2], r14w
0x18007ce38  jnz     short loc_18007CE30
0x18007ce3a  lea     ecx, [rax+rax]
0x18007ce3d  lea     rax, [rbp+2E0h+var_340]
0x18007ce41  add     rcx, 2
0x18007ce45  mov     [rsp+3E0h+var_380], rcx
0x18007ce4a  lea     r9, [rsp+3E0h+var_368]
0x18007ce4f  mov     [rsp+3E0h+var_388], rax
0x18007ce54  lea     rax, aPerformancecou_4; "_PerformanceCounterDataCollector::get_P"...
0x18007ce5b  mov     [rsp+3E0h+var_390], 3Ah ; ':'
0x18007ce64  mov     [rsp+3E0h+var_398], rax
0x18007ce69  lea     rax, [rsp+3E0h+var_370]
0x18007ce6e  mov     ecx, 4
0x18007ce73  lea     rdx, PLA_EVENT_ERROR
0x18007ce7a  mov     [rsp+3E0h+var_3A0], rcx
0x18007ce7f  mov     [rsp+3E0h+var_3A8], rax
0x18007ce84  lea     rax, qword_180147320
0x18007ce8b  mov     [rsp+3E0h+var_3B0], 1
0x18007ce94  mov     [rsp+3E0h+var_3B8], rax
0x18007ce99  lea     r8d, [rcx+1]
0x18007ce9d  mov     qword ptr [rsp+3E0h+var_3C0], rcx
0x18007cea2  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18007cea9  call    EventingWriteEvent
0x18007ceae  jmp     loc_18007D24B
0x18007ceb3  cmp     [rdi+8], r14d
0x18007ceb7  jz      short loc_18007CEC3
0x18007ceb9  lea     rcx, [rdi+10h]; lpCriticalSection
0x18007cebd  call    cs:__imp_EnterCriticalSection
0x18007cec3  mov     rcx, [rdi+0A8h]; psa
0x18007ceca  test    rcx, rcx
0x18007cecd  jnz     short loc_18007CED7
0x18007cecf  mov     [r15], r14
0x18007ced2  jmp     loc_18007D248
0x18007ced7  lea     rdx, [rbp+2E0h+ppvData]; ppvData
0x18007cedb  call    cs:__imp_SafeArrayAccessData
0x18007cee1  mov     esi, eax
0x18007cee3  test    eax, eax
0x18007cee5  jns     loc_18007CF83
0x18007ceeb  cmp     dword ptr cs:xmmword_180169738, r14d
0x18007cef2  mov     dword ptr [rsp+3E0h+var_368], r14d
0x18007cef7  mov     [rsp+3E0h+var_370], eax
0x18007cefb  jz      loc_18007D24B
0x18007cf01  mov     rdx, 4000000000000800h; unsigned __int64
0x18007cf0b  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007cf12  jz      loc_18007D24B
0x18007cf18  mov     rax, cs:qword_180169748
0x18007cf1f  and     rax, rdx
0x18007cf22  cmp     cs:qword_180169748, rax
0x18007cf29  jnz     loc_18007D24B
0x18007cf2f  lea     rcx, [rbp+2E0h+var_2C0]; unsigned __int16 *
0x18007cf33  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18007cf38  lea     rcx, [rbp+2E0h+var_2C0]
0x18007cf3c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007cf40  inc     rax
0x18007cf43  cmp     [rcx+rax*2], r14w
0x18007cf48  jnz     short loc_18007CF40
0x18007cf4a  lea     ecx, [rax+rax]
0x18007cf4d  lea     rax, [rbp+2E0h+var_2C0]
0x18007cf51  add     rcx, 2
0x18007cf55  lea     r9, [rsp+3E0h+var_370]
0x18007cf5a  mov     [rsp+3E0h+var_380], rcx
0x18007cf5f  mov     [rsp+3E0h+var_388], rax
0x18007cf64  lea     rax, aPerformancecou_4; "_PerformanceCounterDataCollector::get_P"...
0x18007cf6b  mov     [rsp+3E0h+var_390], 3Ah ; ':'
0x18007cf74  mov     [rsp+3E0h+var_398], rax
0x18007cf79  lea     rax, [rsp+3E0h+var_368]
0x18007cf7e  jmp     loc_18007CE6E
0x18007cf83  mov     r8, [rdi+0A8h]
0x18007cf8a  mov     ecx, ebx; vt
0x18007cf8c  xor     edx, edx; lLbound
0x18007cf8e  mov     r8d, [r8+18h]; cElements
0x18007cf92  call    cs:__imp_SafeArrayCreateVector
0x18007cf98  mov     r12, rax
0x18007cf9b  test    rax, rax
0x18007cf9e  jnz     short loc_18007D01B
0x18007cfa0  cmp     dword ptr cs:xmmword_180169738, r14d
0x18007cfa7  mov     eax, 8007000Eh
0x18007cfac  mov     esi, eax
0x18007cfae  mov     [rsp+3E0h+var_370], eax
0x18007cfb2  mov     dword ptr [rsp+3E0h+var_368], r14d
0x18007cfb7  jz      loc_18007D24B
0x18007cfbd  mov     rdx, 4000000000000800h; unsigned __int64
0x18007cfc7  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007cfce  jz      loc_18007D24B
0x18007cfd4  mov     rax, cs:qword_180169748
0x18007cfdb  and     rax, rdx
0x18007cfde  cmp     cs:qword_180169748, rax
0x18007cfe5  jnz     loc_18007D24B
0x18007cfeb  lea     rcx, [rbp+2E0h+var_240]; unsigned __int16 *
0x18007cff2  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18007cff7  lea     rcx, [rbp+2E0h+var_240]
0x18007cffe  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007d002  inc     rax
0x18007d005  cmp     [rcx+rax*2], r14w
0x18007d00a  jnz     short loc_18007D002
0x18007d00c  lea     ecx, [rax+rax]
0x18007d00f  lea     rax, [rbp+2E0h+var_240]
0x18007d016  jmp     loc_18007CF51
0x18007d01b  lea     rdx, [rbp+2E0h+var_360]; ppvData
0x18007d01f  mov     rcx, r12; psa
0x18007d022  call    cs:__imp_SafeArrayAccessData
0x18007d028  mov     esi, eax
0x18007d02a  test    eax, eax
0x18007d02c  jns     short loc_18007D0A2
0x18007d02e  cmp     dword ptr cs:xmmword_180169738, r14d
0x18007d035  mov     dword ptr [rsp+3E0h+var_368], r14d
0x18007d03a  mov     [rsp+3E0h+var_370], eax
0x18007d03e  jz      loc_18007D24B
0x18007d044  mov     rdx, 4000000000000800h; unsigned __int64
0x18007d04e  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007d055  jz      loc_18007D24B
0x18007d05b  mov     rax, cs:qword_180169748
0x18007d062  and     rax, rdx
0x18007d065  cmp     cs:qword_180169748, rax
0x18007d06c  jnz     loc_18007D24B
0x18007d072  lea     rcx, [rbp+2E0h+var_1C0]; unsigned __int16 *
0x18007d079  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18007d07e  lea     rcx, [rbp+2E0h+var_1C0]
0x18007d085  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007d089  inc     rax
0x18007d08c  cmp     [rcx+rax*2], r14w
0x18007d091  jnz     short loc_18007D089
0x18007d093  lea     ecx, [rax+rax]
0x18007d096  lea     rax, [rbp+2E0h+var_1C0]
0x18007d09d  jmp     loc_18007CF51
0x18007d0a2  mov     rax, [rdi+0A8h]
0x18007d0a9  cmp     r14d, [rax+18h]
0x18007d0ad  jnb     loc_18007D242
0x18007d0b3  mov     rcx, [rbp+2E0h+ppvData]
0x18007d0b7  lea     r8, [rbp+2E0h+var_358]
0x18007d0bb  mov     [rbp+2E0h+var_358], 400h
0x18007d0c2  mov     rdx, r13
0x18007d0c5  mov     esi, r14d
0x18007d0c8  mov     rcx, [rcx+rsi*8]
0x18007d0cc  call    cs:__imp_PdhTranslateLocaleCounterW
0x18007d0d2  mov     ecx, eax; unsigned int
0x18007d0d4  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18007d0d9  mov     rcx, [rbp+2E0h+var_360]
0x18007d0dd  mov     rcx, [rcx+rsi*8]; bstrString
0x18007d0e1  test    eax, eax
0x18007d0e3  js      loc_18007D197
0x18007d0e9  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x18007d0ee  mov     rax, [rbp+2E0h+var_360]
0x18007d0f2  mov     rcx, r13; unsigned __int16 *
0x18007d0f5  mov     qword ptr [rax+rsi*8], 0
0x18007d0fd  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x18007d102  mov     rcx, [rbp+2E0h+var_360]
0x18007d106  mov     [rcx+rsi*8], rax
0x18007d10a  mov     rax, [rbp+2E0h+var_360]
0x18007d10e  cmp     qword ptr [rax+rsi*8], 0
0x18007d113  jnz     loc_18007D1C8
0x18007d119  xor     r14d, r14d
0x18007d11c  mov     eax, 8007000Eh
0x18007d121  cmp     dword ptr cs:xmmword_180169738, r14d
0x18007d128  mov     esi, eax
0x18007d12a  mov     dword ptr [rsp+3E0h+var_368], r14d
0x18007d12f  mov     [rsp+3E0h+var_370], eax
0x18007d133  jz      loc_18007D24B
0x18007d139  mov     rdx, 4000000000000800h; unsigned __int64
0x18007d143  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007d14a  jz      loc_18007D24B
0x18007d150  mov     rax, cs:qword_180169748
0x18007d157  and     rax, rdx
0x18007d15a  cmp     cs:qword_180169748, rax
0x18007d161  jnz     loc_18007D24B
0x18007d167  lea     rcx, [rbp+2E0h+var_140]; unsigned __int16 *
0x18007d16e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18007d173  lea     rcx, [rbp+2E0h+var_140]
0x18007d17a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007d17e  inc     rax
0x18007d181  cmp     [rcx+rax*2], r14w
0x18007d186  jnz     short loc_18007D17E
0x18007d188  lea     ecx, [rax+rax]
0x18007d18b  lea     rax, [rbp+2E0h+var_140]
0x18007d192  jmp     loc_18007CF51
0x18007d197  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x18007d19c  mov     rax, [rbp+2E0h+var_360]
0x18007d1a0  mov     qword ptr [rax+rsi*8], 0
0x18007d1a8  mov     rcx, [rbp+2E0h+ppvData]
0x18007d1ac  mov     rcx, [rcx+rsi*8]; unsigned __int16 *
0x18007d1b0  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x18007d1b5  mov     rcx, [rbp+2E0h+var_360]
0x18007d1b9  mov     [rcx+rsi*8], rax
0x18007d1bd  mov     rax, [rbp+2E0h+var_360]
0x18007d1c1  cmp     qword ptr [rax+rsi*8], 0
0x18007d1c6  jz      short loc_18007D1D0
0x18007d1c8  inc     r14d
0x18007d1cb  jmp     loc_18007D0A2
0x18007d1d0  xor     r14d, r14d
0x18007d1d3  mov     eax, 8007000Eh
0x18007d1d8  cmp     dword ptr cs:xmmword_180169738, r14d
0x18007d1df  mov     esi, eax
0x18007d1e1  mov     dword ptr [rsp+3E0h+var_368], r14d
0x18007d1e6  mov     [rsp+3E0h+var_370], eax
0x18007d1ea  jz      short loc_18007D24B
0x18007d1ec  mov     rdx, 4000000000000800h; unsigned __int64
0x18007d1f6  test    qword ptr cs:xmmword_180169738+8, rdx
0x18007d1fd  jz      short loc_18007D24B
0x18007d1ff  mov     rax, cs:qword_180169748
0x18007d206  and     rax, rdx
0x18007d209  cmp     cs:qword_180169748, rax
0x18007d210  jnz     short loc_18007D24B
0x18007d212  lea     rcx, [rbp+2E0h+var_C0]; unsigned __int16 *
0x18007d219  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18007d21e  lea     rcx, [rbp+2E0h+var_C0]
0x18007d225  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007d229  inc     rax
0x18007d22c  cmp     [rcx+rax*2], r14w
0x18007d231  jnz     short loc_18007D229
0x18007d233  lea     ecx, [rax+rax]
0x18007d236  lea     rax, [rbp+2E0h+var_C0]
0x18007d23d  jmp     loc_18007CF51
0x18007d242  xor     r14d, r14d
0x18007d245  mov     [r15], r12
0x18007d248  mov     esi, r14d
0x18007d24b  mov     rax, rdi
0x18007d24e  cmp     [rbx+rax], r14d
0x18007d252  jz      short loc_18007D261
0x18007d254  lea     rcx, [rbx+8]
0x18007d258  add     rcx, rax; lpCriticalSection
0x18007d25b  call    cs:__imp_LeaveCriticalSection
0x18007d261  test    r13, r13
0x18007d264  jz      short loc_18007D273
0x18007d266  mov     edx, 1; int
0x18007d26b  mov     rcx, r13; lpMem
0x18007d26e  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x18007d273  cmp     [rbp+2E0h+ppvData], r14
0x18007d277  jz      short loc_18007D28A
0x18007d279  mov     rcx, [rdi+0A8h]; psa
  ... truncated ...
```
