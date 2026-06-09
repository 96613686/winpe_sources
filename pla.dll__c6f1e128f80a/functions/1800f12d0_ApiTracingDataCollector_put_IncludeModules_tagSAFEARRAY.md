# _ApiTracingDataCollector::put_IncludeModules(tagSAFEARRAY *)

- ea: `0x1800f12d0`
- end: `0x1800f161a`
- name: `?put_IncludeModules@_ApiTracingDataCollector@@UEAAJPEAUtagSAFEARRAY@@@Z`
- size: `842`
- prototype: `int(_ApiTracingDataCollector *__hidden this, struct tagSAFEARRAY *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18006e574`
- `0x1800f12d0`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f15e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800f15e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f139e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800f139e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800f154f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800f1564`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800f154f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800f1564`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800f149b`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800f149b`

## pseudocode

```c
__int64 __fastcall _ApiTracingDataCollector::put_IncludeModules(
        _ApiTracingDataCollector *this,
        struct tagSAFEARRAY *a2)
{
  HRESULT v4; // ebx
  int v5; // eax
  __int64 v6; // rax
  int *v7; // r9
  HRESULT v8; // eax
  __int64 v9; // rax
  SAFEARRAY *v10; // rcx
  __int64 v11; // rax
  HRESULT v13; // [rsp+70h] [rbp-90h] BYREF
  int v14; // [rsp+78h] [rbp-88h] BYREF
  SAFEARRAY *ppsaOut; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v16[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v17[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v18[64]; // [rsp+190h] [rbp+90h] BYREF

  v13 = *((_DWORD *)this + 14);
  v4 = 0;
  ppsaOut = (SAFEARRAY *)this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(
      (__int64)&g_Eventing,
      (__int64)PLA_EVENT_METHOD,
      3,
      (__int64)"_ApiTracingDataCollector::put_IncludeModules");
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  ppsaOut = 0;
  if ( a2 )
  {
    v5 = PlaiValidateSafeArray(a2);
    v4 = v5;
    if ( v5 < 0 )
    {
      v13 = 0;
      v14 = v5;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v16, 0x4000000000000800uLL);
        v6 = -1;
        do
          ++v6;
        while ( v16[v6] );
        v7 = &v14;
        goto LABEL_15;
      }
      goto LABEL_34;
    }
    v8 = SafeArrayCopy(a2, &ppsaOut);
    v4 = v8;
    if ( v8 < 0 )
    {
      v14 = 0;
      v13 = v8;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_34;
      }
      PlaiWhoAmI(v17, 0x4000000000000800uLL);
      v9 = -1;
      do
        ++v9;
      while ( v17[v9] );
LABEL_22:
      v7 = &v13;
LABEL_15:
      EventingWriteEvent((__int64)&g_Eventing, (__int64)PLA_EVENT_ERROR, 5, (__int64)v7);
      goto LABEL_34;
    }
  }
  v10 = (SAFEARRAY *)*((_QWORD *)this + 20);
  if ( !v10 || (v4 = SafeArrayDestroy(v10), v4 >= 0) )
  {
    *((_QWORD *)this + 20) = ppsaOut;
    goto LABEL_34;
  }
  if ( ppsaOut )
    SafeArrayDestroy(ppsaOut);
  v14 = 0;
  v13 = v4;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v18, 0x4000000000000800uLL);
    v11 = -1;
    do
      ++v11;
    while ( v18[v11] );
    goto LABEL_22;
  }
LABEL_34:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800f12d0  mov     [rsp-8+arg_10], rbx
0x1800f12d5  mov     [rsp-8+arg_18], rsi
0x1800f12da  push    rbp
0x1800f12db  push    rdi
0x1800f12dc  push    r12
0x1800f12de  push    r14
0x1800f12e0  push    r15
0x1800f12e2  lea     rbp, [rsp-120h]
0x1800f12ea  sub     rsp, 220h
0x1800f12f1  mov     rax, cs:__security_cookie
0x1800f12f8  xor     rax, rsp
0x1800f12fb  mov     [rbp+140h+var_30], rax
0x1800f1302  mov     eax, [rcx+38h]
0x1800f1305  xor     r14d, r14d
0x1800f1308  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800f130f  mov     rsi, rdx
0x1800f1312  mov     rdi, rcx
0x1800f1315  mov     [rsp+240h+var_1D0], eax
0x1800f1319  mov     ebx, r14d
0x1800f131c  mov     [rbp+140h+ppsaOut], rcx
0x1800f1320  lea     r15d, [r14+4]
0x1800f1324  lea     r12d, [r14+2Dh]
0x1800f1328  jz      short loc_1800F1394
0x1800f132a  mov     rdx, 4000000000000400h
0x1800f1334  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f133b  jz      short loc_1800F1394
0x1800f133d  mov     rax, cs:qword_180169748
0x1800f1344  and     rax, rdx
0x1800f1347  cmp     cs:qword_180169748, rax
0x1800f134e  jnz     short loc_1800F1394
0x1800f1350  mov     [rsp+240h+var_200], r15
0x1800f1355  lea     rax, [rsp+240h+var_1D0]
0x1800f135a  mov     [rsp+240h+var_208], rax
0x1800f135f  lea     r9, aApitracingdata_5; "_ApiTracingDataCollector::put_IncludeMo"...
0x1800f1366  lea     rax, [rbp+140h+ppsaOut]
0x1800f136a  mov     [rsp+240h+var_210], 8
0x1800f1373  mov     [rsp+240h+var_218], rax
0x1800f1378  lea     r8d, [r14+3]
0x1800f137c  lea     rdx, PLA_EVENT_METHOD
0x1800f1383  mov     [rsp+240h+var_220], r12
0x1800f1388  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800f138f  call    EventingWriteEvent
0x1800f1394  cmp     [rdi+8], r14d
0x1800f1398  jz      short loc_1800F13A4
0x1800f139a  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800f139e  call    cs:__imp_EnterCriticalSection
0x1800f13a4  mov     [rbp+140h+ppsaOut], r14
0x1800f13a8  test    rsi, rsi
0x1800f13ab  jz      loc_1800F153F
0x1800f13b1  mov     rcx, rsi; psa
0x1800f13b4  call    ?PlaiValidateSafeArray@@YAJPEAUtagSAFEARRAY@@@Z; PlaiValidateSafeArray(tagSAFEARRAY *)
0x1800f13b9  mov     ebx, eax
0x1800f13bb  test    eax, eax
0x1800f13bd  jns     loc_1800F1494
0x1800f13c3  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800f13ca  mov     [rsp+240h+var_1D0], r14d
0x1800f13cf  mov     [rsp+240h+var_1C8], eax
0x1800f13d3  jz      loc_1800F15DD
0x1800f13d9  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f13e3  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f13ea  jz      loc_1800F15DD
0x1800f13f0  mov     rax, cs:qword_180169748
0x1800f13f7  and     rax, rdx
0x1800f13fa  cmp     cs:qword_180169748, rax
0x1800f1401  jnz     loc_1800F15DD
0x1800f1407  lea     rcx, [rbp+140h+var_1B0]; unsigned __int16 *
0x1800f140b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f1410  lea     rcx, [rbp+140h+var_1B0]
0x1800f1414  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f1418  inc     rax
0x1800f141b  cmp     [rcx+rax*2], r14w
0x1800f1420  jnz     short loc_1800F1418
0x1800f1422  lea     ecx, [rax+rax]
0x1800f1425  lea     rax, [rbp+140h+var_1B0]
0x1800f1429  add     rcx, 2
0x1800f142d  mov     [rsp+240h+var_1E0], rcx
0x1800f1432  lea     r9, [rsp+240h+var_1C8]
0x1800f1437  mov     [rsp+240h+var_1E8], rax
0x1800f143c  lea     rax, aApitracingdata_5; "_ApiTracingDataCollector::put_IncludeMo"...
0x1800f1443  mov     [rsp+240h+var_1F0], r12
0x1800f1448  mov     [rsp+240h+var_1F8], rax
0x1800f144d  lea     rax, [rsp+240h+var_1D0]
0x1800f1452  mov     [rsp+240h+var_200], r15
0x1800f1457  lea     rdx, PLA_EVENT_ERROR
0x1800f145e  mov     [rsp+240h+var_208], rax
0x1800f1463  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800f146a  lea     rax, qword_180147320
0x1800f1471  mov     [rsp+240h+var_210], 1
0x1800f147a  mov     [rsp+240h+var_218], rax
0x1800f147f  mov     r8d, 5
0x1800f1485  mov     [rsp+240h+var_220], r15
0x1800f148a  call    EventingWriteEvent
0x1800f148f  jmp     loc_1800F15DD
0x1800f1494  lea     rdx, [rbp+140h+ppsaOut]; ppsaOut
0x1800f1498  mov     rcx, rsi; psa
0x1800f149b  call    cs:__imp_SafeArrayCopy
0x1800f14a1  mov     ebx, eax
0x1800f14a3  test    eax, eax
0x1800f14a5  jns     loc_1800F153F
0x1800f14ab  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800f14b2  mov     [rsp+240h+var_1C8], r14d
0x1800f14b7  mov     [rsp+240h+var_1D0], eax
0x1800f14bb  jz      loc_1800F15DD
0x1800f14c1  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f14cb  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f14d2  jz      loc_1800F15DD
0x1800f14d8  mov     rax, cs:qword_180169748
0x1800f14df  and     rax, rdx
0x1800f14e2  cmp     cs:qword_180169748, rax
0x1800f14e9  jnz     loc_1800F15DD
0x1800f14ef  lea     rcx, [rbp+140h+var_130]; unsigned __int16 *
0x1800f14f3  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f14f8  lea     rcx, [rbp+140h+var_130]
0x1800f14fc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f1500  inc     rax
0x1800f1503  cmp     [rcx+rax*2], r14w
0x1800f1508  jnz     short loc_1800F1500
0x1800f150a  lea     ecx, [rax+rax]
0x1800f150d  lea     rax, [rbp+140h+var_130]
0x1800f1511  add     rcx, 2
0x1800f1515  lea     r9, [rsp+240h+var_1D0]
0x1800f151a  mov     [rsp+240h+var_1E0], rcx
0x1800f151f  mov     [rsp+240h+var_1E8], rax
0x1800f1524  lea     rax, aApitracingdata_5; "_ApiTracingDataCollector::put_IncludeMo"...
0x1800f152b  mov     [rsp+240h+var_1F0], r12
0x1800f1530  mov     [rsp+240h+var_1F8], rax
0x1800f1535  lea     rax, [rsp+240h+var_1C8]
0x1800f153a  jmp     loc_1800F1452
0x1800f153f  mov     rcx, [rdi+0A0h]; psa
0x1800f1546  test    rcx, rcx
0x1800f1549  jz      loc_1800F15D2
0x1800f154f  call    cs:__imp_SafeArrayDestroy
0x1800f1555  mov     ebx, eax
0x1800f1557  test    eax, eax
0x1800f1559  jns     short loc_1800F15D2
0x1800f155b  mov     rcx, [rbp+140h+ppsaOut]; psa
0x1800f155f  test    rcx, rcx
0x1800f1562  jz      short loc_1800F156A
0x1800f1564  call    cs:__imp_SafeArrayDestroy
0x1800f156a  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800f1571  mov     [rsp+240h+var_1C8], r14d
0x1800f1576  mov     [rsp+240h+var_1D0], ebx
0x1800f157a  jz      short loc_1800F15DD
0x1800f157c  mov     rdx, 4000000000000800h; unsigned __int64
0x1800f1586  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800f158d  jz      short loc_1800F15DD
0x1800f158f  mov     rax, cs:qword_180169748
0x1800f1596  and     rax, rdx
0x1800f1599  cmp     cs:qword_180169748, rax
0x1800f15a0  jnz     short loc_1800F15DD
0x1800f15a2  lea     rcx, [rbp+140h+var_B0]; unsigned __int16 *
0x1800f15a9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800f15ae  lea     rcx, [rbp+140h+var_B0]
0x1800f15b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f15b9  inc     rax
0x1800f15bc  cmp     [rcx+rax*2], r14w
0x1800f15c1  jnz     short loc_1800F15B9
0x1800f15c3  lea     ecx, [rax+rax]
0x1800f15c6  lea     rax, [rbp+140h+var_B0]
0x1800f15cd  jmp     loc_1800F1511
0x1800f15d2  mov     rax, [rbp+140h+ppsaOut]
0x1800f15d6  mov     [rdi+0A0h], rax
0x1800f15dd  cmp     [rdi+8], r14d
0x1800f15e1  jz      short loc_1800F15ED
0x1800f15e3  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800f15e7  call    cs:__imp_LeaveCriticalSection
0x1800f15ed  mov     eax, ebx
0x1800f15ef  mov     rcx, [rbp+140h+var_30]
0x1800f15f6  xor     rcx, rsp; StackCookie
0x1800f15f9  call    __security_check_cookie
0x1800f15fe  lea     r11, [rsp+240h+var_20]
0x1800f1606  mov     rbx, [r11+40h]
0x1800f160a  mov     rsi, [r11+48h]
0x1800f160e  mov     rsp, r11
0x1800f1611  pop     r15
0x1800f1613  pop     r14
0x1800f1615  pop     r12
0x1800f1617  pop     rdi
0x1800f1618  pop     rbp
0x1800f1619  retn
```
