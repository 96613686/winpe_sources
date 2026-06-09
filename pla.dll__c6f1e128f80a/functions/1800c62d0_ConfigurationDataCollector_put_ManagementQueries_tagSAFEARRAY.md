# _ConfigurationDataCollector::put_ManagementQueries(tagSAFEARRAY *)

- ea: `0x1800c62d0`
- end: `0x1800c661a`
- name: `?put_ManagementQueries@_ConfigurationDataCollector@@UEAAJPEAUtagSAFEARRAY@@@Z`
- size: `842`
- prototype: `int(_ConfigurationDataCollector *__hidden this, struct tagSAFEARRAY *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18006e574`
- `0x1800c62d0`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c65e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c65e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c639e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c639e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c654f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c6564`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c654f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c6564`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800c649b`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800c649b`

## string_xrefs

- `0x1800c635f`: `_ConfigurationDataCollector::put_ManagementQueries`
- `0x1800c643c`: `_ConfigurationDataCollector::put_ManagementQueries`
- `0x1800c6524`: `_ConfigurationDataCollector::put_ManagementQueries`

## pseudocode

```c
__int64 __fastcall _ConfigurationDataCollector::put_ManagementQueries(
        _ConfigurationDataCollector *this,
        struct tagSAFEARRAY *a2)
{
  HRESULT v4; // ebx
  int v5; // eax
  __int64 v6; // rax
  HRESULT v7; // eax
  __int64 v8; // rax
  SAFEARRAY *v9; // rcx
  __int64 v10; // rax
  __int64 v12; // [rsp+48h] [rbp-B8h]
  __int64 v13; // [rsp+50h] [rbp-B0h]
  HRESULT v14; // [rsp+70h] [rbp-90h] BYREF
  int v15; // [rsp+78h] [rbp-88h] BYREF
  SAFEARRAY *ppsaOut[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v17[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v18[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v19[64]; // [rsp+190h] [rbp+90h] BYREF

  v14 = *((_DWORD *)this + 14);
  v4 = 0;
  ppsaOut[0] = (SAFEARRAY *)this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_METHOD,
      3,
      "_ConfigurationDataCollector::put_ManagementQueries",
      51,
      ppsaOut,
      8,
      &v14,
      4,
      v12,
      v13);
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  ppsaOut[0] = 0;
  if ( a2 )
  {
    v5 = PlaiValidateSafeArray(a2);
    v4 = v5;
    if ( v5 < 0 )
    {
      v14 = 0;
      v15 = v5;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v17, 0x4000000000000800uLL);
        v6 = -1;
        do
          ++v6;
        while ( v17[v6] );
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v15,
          4,
          qword_180147320,
          1,
          &v14,
          4,
          "_ConfigurationDataCollector::put_ManagementQueries",
          51);
      }
      goto LABEL_33;
    }
    v7 = SafeArrayCopy(a2, ppsaOut);
    v4 = v7;
    if ( v7 < 0 )
    {
      v15 = 0;
      v14 = v7;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_33;
      }
      PlaiWhoAmI(v18, 0x4000000000000800uLL);
      v8 = -1;
      do
        ++v8;
      while ( v18[v8] );
LABEL_21:
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v14,
        4,
        qword_180147320,
        1,
        &v15,
        4,
        "_ConfigurationDataCollector::put_ManagementQueries",
        51);
      goto LABEL_33;
    }
  }
  v9 = (SAFEARRAY *)*((_QWORD *)this + 23);
  if ( !v9 || (v4 = SafeArrayDestroy(v9), v4 >= 0) )
  {
    *((SAFEARRAY **)this + 23) = ppsaOut[0];
    goto LABEL_33;
  }
  if ( ppsaOut[0] )
    SafeArrayDestroy(ppsaOut[0]);
  v15 = 0;
  v14 = v4;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v19, 0x4000000000000800uLL);
    v10 = -1;
    do
      ++v10;
    while ( v19[v10] );
    goto LABEL_21;
  }
LABEL_33:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800c62d0  mov     [rsp-8+arg_10], rbx
0x1800c62d5  mov     [rsp-8+arg_18], rsi
0x1800c62da  push    rbp
0x1800c62db  push    rdi
0x1800c62dc  push    r12
0x1800c62de  push    r14
0x1800c62e0  push    r15
0x1800c62e2  lea     rbp, [rsp-120h]
0x1800c62ea  sub     rsp, 220h
0x1800c62f1  mov     rax, cs:__security_cookie
0x1800c62f8  xor     rax, rsp
0x1800c62fb  mov     [rbp+140h+var_30], rax
0x1800c6302  mov     eax, [rcx+38h]
0x1800c6305  xor     r14d, r14d
0x1800c6308  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800c630f  mov     rsi, rdx
0x1800c6312  mov     rdi, rcx
0x1800c6315  mov     [rsp+240h+var_1D0], eax
0x1800c6319  mov     ebx, r14d
0x1800c631c  mov     [rbp+140h+ppsaOut], rcx
0x1800c6320  lea     r15d, [r14+4]
0x1800c6324  lea     r12d, [r14+33h]
0x1800c6328  jz      short loc_1800C6394
0x1800c632a  mov     rdx, 4000000000000400h
0x1800c6334  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c633b  jz      short loc_1800C6394
0x1800c633d  mov     rax, cs:qword_180169748
0x1800c6344  and     rax, rdx
0x1800c6347  cmp     cs:qword_180169748, rax
0x1800c634e  jnz     short loc_1800C6394
0x1800c6350  mov     [rsp+240h+var_200], r15
0x1800c6355  lea     rax, [rsp+240h+var_1D0]
0x1800c635a  mov     [rsp+240h+var_208], rax
0x1800c635f  lea     r9, aConfigurationd_11; "_ConfigurationDataCollector::put_Manage"...
0x1800c6366  lea     rax, [rbp+140h+ppsaOut]
0x1800c636a  mov     [rsp+240h+var_210], 8
0x1800c6373  mov     [rsp+240h+var_218], rax
0x1800c6378  lea     r8d, [r14+3]
0x1800c637c  lea     rdx, PLA_EVENT_METHOD
0x1800c6383  mov     [rsp+240h+var_220], r12
0x1800c6388  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800c638f  call    EventingWriteEvent
0x1800c6394  cmp     [rdi+8], r14d
0x1800c6398  jz      short loc_1800C63A4
0x1800c639a  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800c639e  call    cs:__imp_EnterCriticalSection
0x1800c63a4  mov     [rbp+140h+ppsaOut], r14
0x1800c63a8  test    rsi, rsi
0x1800c63ab  jz      loc_1800C653F
0x1800c63b1  mov     rcx, rsi; psa
0x1800c63b4  call    ?PlaiValidateSafeArray@@YAJPEAUtagSAFEARRAY@@@Z; PlaiValidateSafeArray(tagSAFEARRAY *)
0x1800c63b9  mov     ebx, eax
0x1800c63bb  test    eax, eax
0x1800c63bd  jns     loc_1800C6494
0x1800c63c3  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800c63ca  mov     [rsp+240h+var_1D0], r14d
0x1800c63cf  mov     [rsp+240h+var_1C8], eax
0x1800c63d3  jz      loc_1800C65DD
0x1800c63d9  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c63e3  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c63ea  jz      loc_1800C65DD
0x1800c63f0  mov     rax, cs:qword_180169748
0x1800c63f7  and     rax, rdx
0x1800c63fa  cmp     cs:qword_180169748, rax
0x1800c6401  jnz     loc_1800C65DD
0x1800c6407  lea     rcx, [rbp+140h+var_1B0]; unsigned __int16 *
0x1800c640b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c6410  lea     rcx, [rbp+140h+var_1B0]
0x1800c6414  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c6418  inc     rax
0x1800c641b  cmp     [rcx+rax*2], r14w
0x1800c6420  jnz     short loc_1800C6418
0x1800c6422  lea     ecx, [rax+rax]
0x1800c6425  lea     rax, [rbp+140h+var_1B0]
0x1800c6429  add     rcx, 2
0x1800c642d  mov     [rsp+240h+var_1E0], rcx
0x1800c6432  lea     r9, [rsp+240h+var_1C8]
0x1800c6437  mov     [rsp+240h+var_1E8], rax
0x1800c643c  lea     rax, aConfigurationd_11; "_ConfigurationDataCollector::put_Manage"...
0x1800c6443  mov     [rsp+240h+var_1F0], r12
0x1800c6448  mov     [rsp+240h+var_1F8], rax
0x1800c644d  lea     rax, [rsp+240h+var_1D0]
0x1800c6452  mov     [rsp+240h+var_200], r15
0x1800c6457  lea     rdx, PLA_EVENT_ERROR
0x1800c645e  mov     [rsp+240h+var_208], rax
0x1800c6463  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800c646a  lea     rax, qword_180147320
0x1800c6471  mov     [rsp+240h+var_210], 1
0x1800c647a  mov     [rsp+240h+var_218], rax
0x1800c647f  mov     r8d, 5
0x1800c6485  mov     [rsp+240h+var_220], r15
0x1800c648a  call    EventingWriteEvent
0x1800c648f  jmp     loc_1800C65DD
0x1800c6494  lea     rdx, [rbp+140h+ppsaOut]; ppsaOut
0x1800c6498  mov     rcx, rsi; psa
0x1800c649b  call    cs:__imp_SafeArrayCopy
0x1800c64a1  mov     ebx, eax
0x1800c64a3  test    eax, eax
0x1800c64a5  jns     loc_1800C653F
0x1800c64ab  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800c64b2  mov     [rsp+240h+var_1C8], r14d
0x1800c64b7  mov     [rsp+240h+var_1D0], eax
0x1800c64bb  jz      loc_1800C65DD
0x1800c64c1  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c64cb  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c64d2  jz      loc_1800C65DD
0x1800c64d8  mov     rax, cs:qword_180169748
0x1800c64df  and     rax, rdx
0x1800c64e2  cmp     cs:qword_180169748, rax
0x1800c64e9  jnz     loc_1800C65DD
0x1800c64ef  lea     rcx, [rbp+140h+var_130]; unsigned __int16 *
0x1800c64f3  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c64f8  lea     rcx, [rbp+140h+var_130]
0x1800c64fc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c6500  inc     rax
0x1800c6503  cmp     [rcx+rax*2], r14w
0x1800c6508  jnz     short loc_1800C6500
0x1800c650a  lea     ecx, [rax+rax]
0x1800c650d  lea     rax, [rbp+140h+var_130]
0x1800c6511  add     rcx, 2
0x1800c6515  lea     r9, [rsp+240h+var_1D0]
0x1800c651a  mov     [rsp+240h+var_1E0], rcx
0x1800c651f  mov     [rsp+240h+var_1E8], rax
0x1800c6524  lea     rax, aConfigurationd_11; "_ConfigurationDataCollector::put_Manage"...
0x1800c652b  mov     [rsp+240h+var_1F0], r12
0x1800c6530  mov     [rsp+240h+var_1F8], rax
0x1800c6535  lea     rax, [rsp+240h+var_1C8]
0x1800c653a  jmp     loc_1800C6452
0x1800c653f  mov     rcx, [rdi+0B8h]; psa
0x1800c6546  test    rcx, rcx
0x1800c6549  jz      loc_1800C65D2
0x1800c654f  call    cs:__imp_SafeArrayDestroy
0x1800c6555  mov     ebx, eax
0x1800c6557  test    eax, eax
0x1800c6559  jns     short loc_1800C65D2
0x1800c655b  mov     rcx, [rbp+140h+ppsaOut]; psa
0x1800c655f  test    rcx, rcx
0x1800c6562  jz      short loc_1800C656A
0x1800c6564  call    cs:__imp_SafeArrayDestroy
0x1800c656a  cmp     dword ptr cs:xmmword_180169738, r14d
0x1800c6571  mov     [rsp+240h+var_1C8], r14d
0x1800c6576  mov     [rsp+240h+var_1D0], ebx
0x1800c657a  jz      short loc_1800C65DD
0x1800c657c  mov     rdx, 4000000000000800h; unsigned __int64
0x1800c6586  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800c658d  jz      short loc_1800C65DD
0x1800c658f  mov     rax, cs:qword_180169748
0x1800c6596  and     rax, rdx
0x1800c6599  cmp     cs:qword_180169748, rax
0x1800c65a0  jnz     short loc_1800C65DD
0x1800c65a2  lea     rcx, [rbp+140h+var_B0]; unsigned __int16 *
0x1800c65a9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800c65ae  lea     rcx, [rbp+140h+var_B0]
0x1800c65b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c65b9  inc     rax
0x1800c65bc  cmp     [rcx+rax*2], r14w
0x1800c65c1  jnz     short loc_1800C65B9
0x1800c65c3  lea     ecx, [rax+rax]
0x1800c65c6  lea     rax, [rbp+140h+var_B0]
0x1800c65cd  jmp     loc_1800C6511
0x1800c65d2  mov     rax, [rbp+140h+ppsaOut]
0x1800c65d6  mov     [rdi+0B8h], rax
0x1800c65dd  cmp     [rdi+8], r14d
0x1800c65e1  jz      short loc_1800C65ED
0x1800c65e3  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800c65e7  call    cs:__imp_LeaveCriticalSection
0x1800c65ed  mov     eax, ebx
0x1800c65ef  mov     rcx, [rbp+140h+var_30]
0x1800c65f6  xor     rcx, rsp; StackCookie
0x1800c65f9  call    __security_check_cookie
0x1800c65fe  lea     r11, [rsp+240h+var_20]
0x1800c6606  mov     rbx, [r11+40h]
0x1800c660a  mov     rsi, [r11+48h]
0x1800c660e  mov     rsp, r11
0x1800c6611  pop     r15
0x1800c6613  pop     r14
0x1800c6615  pop     r12
0x1800c6617  pop     rdi
0x1800c6618  pop     rbp
0x1800c6619  retn
```
