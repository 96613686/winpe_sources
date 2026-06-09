# Enumerator::GetNamedItem<IDataCollectorSet>(tagVARIANT,long (IDataCollectorSet::*)(ushort * *),IDataCollectorSet * *)

- ea: `0x180121054`
- end: `0x180121402`
- name: `??$GetNamedItem@UIDataCollectorSet@@@Enumerator@@QEAAJUtagVARIANT@@P8IDataCollectorSet@@EAAJPEAPEAG@ZPEAPEAU2@@Z`
- size: `942`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800d33f0`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180120bfc`
- `0x180121054`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801213c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801213c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180121129`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180121129`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18012123b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18012123b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1801213d0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1801213d0`

## pseudocode

```c
__int64 __fastcall Enumerator::GetNamedItem<IDataCollectorSet>(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // eax
  IRecordInfo *v8; // xmm1_8
  int v9; // eax
  unsigned int v10; // esi
  __int64 v11; // rax
  SAFEARRAY **v12; // rbx
  HRESULT v13; // eax
  __int64 v14; // rax
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64); // rcx
  int v16; // eax
  __int64 v17; // rax
  __int64 v19; // [rsp+48h] [rbp-B8h]
  __int64 v20; // [rsp+50h] [rbp-B0h]
  int v21; // [rsp+70h] [rbp-90h] BYREF
  int v22; // [rsp+78h] [rbp-88h] BYREF
  void *ppvData; // [rsp+80h] [rbp-80h] BYREF
  __int64 v24; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v25; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v26[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v27[64]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v28[64]; // [rsp+1B0h] [rbp+B0h] BYREF

  v4 = *(_DWORD *)(a1 + 56);
  v21 = 0;
  ppvData = 0;
  v22 = v4;
  v24 = a1;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(&g_Eventing, PLA_EVENT_METHOD, 3, "Enumerator::GetNamedItem", 25, &v24, 8, &v22, 4, v19, v20);
  }
  if ( *(_DWORD *)(a1 + 8) )
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v8 = *(IRecordInfo **)(a2 + 16);
  *(_OWORD *)&v25.vt = *(_OWORD *)a2;
  v25.pRecInfo = v8;
  v9 = Enumerator::GetIndex<IDataCollectorSet>(a1, &v25, a3, (unsigned int *)&v21);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v12 = (SAFEARRAY **)(a1 + 64);
    v13 = SafeArrayAccessData(*(SAFEARRAY **)(a1 + 64), &ppvData);
    v10 = v13;
    if ( v13 >= 0 )
    {
      v15 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*((_QWORD *)ppvData + 3 * (unsigned int)v21 + 1);
      v16 = (**v15)(v15, &GUID_03837520_098b_11d8_9414_505054503030, a4);
      v10 = v16;
      if ( v16 >= 0 )
        goto LABEL_29;
      v22 = 0;
      v21 = v16;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_29;
      }
      PlaiWhoAmI(v28, 0x4000000000000800uLL);
      v17 = -1;
      do
        ++v17;
      while ( v28[v17] );
    }
    else
    {
      v22 = 0;
      v21 = v13;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_29;
      }
      PlaiWhoAmI(v27, 0x4000000000000800uLL);
      v14 = -1;
      do
        ++v14;
      while ( v27[v14] );
    }
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v21,
      4,
      qword_180147320,
      1,
      &v22,
      4,
      "Enumerator::GetNamedItem",
      25);
    goto LABEL_29;
  }
  v22 = 0;
  v21 = v9;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v26, 0x4000000000000800uLL);
    v11 = -1;
    do
      ++v11;
    while ( v26[v11] );
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v21,
      4,
      qword_180147320,
      1,
      &v22,
      4,
      "Enumerator::GetNamedItem",
      25);
  }
  v12 = (SAFEARRAY **)(a1 + 64);
LABEL_29:
  if ( *(_DWORD *)(a1 + 8) )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( ppvData )
    SafeArrayUnaccessData(*v12);
  return v10;
}

```

## disassembly

```asm
0x180121054  mov     [rsp-8+arg_10], rbx
0x180121059  push    rbp
0x18012105a  push    rsi
0x18012105b  push    rdi
0x18012105c  push    r12
0x18012105e  push    r13
0x180121060  push    r14
0x180121062  push    r15
0x180121064  lea     rbp, [rsp-140h]
0x18012106c  sub     rsp, 240h
0x180121073  mov     rax, cs:__security_cookie
0x18012107a  xor     rax, rsp
0x18012107d  mov     [rbp+170h+var_40], rax
0x180121084  mov     eax, [rcx+38h]
0x180121087  xor     r15d, r15d
0x18012108a  cmp     dword ptr cs:xmmword_180169738, r15d
0x180121091  mov     r14, r9
0x180121094  mov     rbx, rdx
0x180121097  mov     [rsp+270h+var_200], r15d
0x18012109c  mov     rdi, rcx
0x18012109f  mov     [rbp+170h+ppvData], r15
0x1801210a3  lea     r12d, [r15+4]
0x1801210a7  mov     [rsp+270h+var_1F8], eax
0x1801210ab  lea     r13d, [r15+19h]
0x1801210af  mov     [rbp+170h+var_1E8], rcx
0x1801210b3  jz      short loc_18012111F
0x1801210b5  mov     rdx, 4000000000000400h
0x1801210bf  test    qword ptr cs:xmmword_180169738+8, rdx
0x1801210c6  jz      short loc_18012111F
0x1801210c8  mov     rax, cs:qword_180169748
0x1801210cf  and     rax, rdx
0x1801210d2  cmp     cs:qword_180169748, rax
0x1801210d9  jnz     short loc_18012111F
0x1801210db  mov     [rsp+270h+var_230], r12
0x1801210e0  lea     rax, [rsp+270h+var_1F8]
0x1801210e5  mov     [rsp+270h+var_238], rax
0x1801210ea  lea     r9, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x1801210f1  lea     rax, [rbp+170h+var_1E8]
0x1801210f5  mov     [rsp+270h+var_240], 8
0x1801210fe  mov     [rsp+270h+var_248], rax
0x180121103  lea     r8d, [r15+3]
0x180121107  lea     rdx, PLA_EVENT_METHOD
0x18012110e  mov     [rsp+270h+var_250], r13
0x180121113  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18012111a  call    EventingWriteEvent
0x18012111f  cmp     [rdi+8], r15d
0x180121123  jz      short loc_18012112F
0x180121125  lea     rcx, [rdi+10h]; lpCriticalSection
0x180121129  call    cs:__imp_EnterCriticalSection
0x18012112f  movaps  xmm0, xmmword ptr [rbx]
0x180121132  lea     r9, [rsp+270h+var_200]
0x180121137  movsd   xmm1, qword ptr [rbx+10h]
0x18012113c  lea     rdx, [rbp+170h+var_1E0]
0x180121140  mov     rcx, rdi
0x180121143  movaps  [rbp+170h+var_1E0], xmm0
0x180121147  movsd   [rbp+170h+var_1D0], xmm1
0x18012114c  call    ??$GetIndex@UIDataCollectorSet@@@Enumerator@@IEAAJUtagVARIANT@@P8IDataCollectorSet@@EAAJPEAPEAG@ZPEAK@Z; Enumerator::GetIndex<IDataCollectorSet>(tagVARIANT,long (IDataCollectorSet::*)(ushort * *),ulong *)
0x180121151  mov     esi, eax
0x180121153  test    eax, eax
0x180121155  jns     loc_180121230
0x18012115b  cmp     dword ptr cs:xmmword_180169738, r15d
0x180121162  mov     [rsp+270h+var_1F8], r15d
0x180121167  mov     [rsp+270h+var_200], eax
0x18012116b  jz      loc_180121227
0x180121171  mov     rdx, 4000000000000800h; unsigned __int64
0x18012117b  test    qword ptr cs:xmmword_180169738+8, rdx
0x180121182  jz      loc_180121227
0x180121188  mov     rax, cs:qword_180169748
0x18012118f  and     rax, rdx
0x180121192  cmp     cs:qword_180169748, rax
0x180121199  jnz     loc_180121227
0x18012119f  lea     rcx, [rbp+170h+var_1C0]; unsigned __int16 *
0x1801211a3  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1801211a8  lea     rcx, [rbp+170h+var_1C0]
0x1801211ac  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801211b0  inc     rax
0x1801211b3  cmp     [rcx+rax*2], r15w
0x1801211b8  jnz     short loc_1801211B0
0x1801211ba  lea     ecx, [rax+rax]
0x1801211bd  mov     r8d, 5
0x1801211c3  add     rcx, 2
0x1801211c7  lea     rax, [rbp+170h+var_1C0]
0x1801211cb  mov     [rsp+270h+var_210], rcx
0x1801211d0  lea     r9, [rsp+270h+var_200]
0x1801211d5  mov     [rsp+270h+var_218], rax
0x1801211da  lea     rdx, PLA_EVENT_ERROR
0x1801211e1  mov     [rsp+270h+var_220], r13
0x1801211e6  lea     rax, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x1801211ed  mov     [rsp+270h+var_228], rax
0x1801211f2  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1801211f9  mov     [rsp+270h+var_230], r12
0x1801211fe  lea     rax, [rsp+270h+var_1F8]
0x180121203  mov     [rsp+270h+var_238], rax
0x180121208  lea     rax, qword_180147320
0x18012120f  mov     [rsp+270h+var_240], 1
0x180121218  mov     [rsp+270h+var_248], rax
0x18012121d  mov     [rsp+270h+var_250], r12
0x180121222  call    EventingWriteEvent
0x180121227  lea     rbx, [rdi+40h]
0x18012122b  jmp     loc_1801213B7
0x180121230  lea     rbx, [rdi+40h]
0x180121234  mov     rcx, [rbx]; psa
0x180121237  lea     rdx, [rbp+170h+ppvData]; ppvData
0x18012123b  call    cs:__imp_SafeArrayAccessData
0x180121241  mov     esi, eax
0x180121243  test    eax, eax
0x180121245  jns     short loc_1801212B2
0x180121247  cmp     dword ptr cs:xmmword_180169738, r15d
0x18012124e  mov     [rsp+270h+var_1F8], r15d
0x180121253  mov     [rsp+270h+var_200], eax
0x180121257  jz      loc_1801213B7
0x18012125d  mov     rdx, 4000000000000800h; unsigned __int64
0x180121267  test    qword ptr cs:xmmword_180169738+8, rdx
0x18012126e  jz      loc_1801213B7
0x180121274  mov     rax, cs:qword_180169748
0x18012127b  and     rax, rdx
0x18012127e  cmp     cs:qword_180169748, rax
0x180121285  jnz     loc_1801213B7
0x18012128b  lea     rcx, [rbp+170h+var_140]; unsigned __int16 *
0x18012128f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180121294  lea     rcx, [rbp+170h+var_140]
0x180121298  or      rax, 0FFFFFFFFFFFFFFFFh
0x18012129c  inc     rax
0x18012129f  cmp     [rcx+rax*2], r15w
0x1801212a4  jnz     short loc_18012129C
0x1801212a6  lea     ecx, [rax+rax]
0x1801212a9  lea     rax, [rbp+170h+var_140]
0x1801212ad  jmp     loc_180121351
0x1801212b2  mov     eax, [rsp+270h+var_200]
0x1801212b6  lea     rdx, _GUID_03837520_098b_11d8_9414_505054503030
0x1801212bd  mov     r8, r14
0x1801212c0  lea     rcx, [rax+rax*2]
0x1801212c4  mov     rax, [rbp+170h+ppvData]
0x1801212c8  mov     rcx, [rax+rcx*8+8]
0x1801212cd  mov     rax, [rcx]
0x1801212d0  mov     rax, [rax]
0x1801212d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801212d8  mov     esi, eax
0x1801212da  test    eax, eax
0x1801212dc  jns     loc_1801213B7
0x1801212e2  cmp     dword ptr cs:xmmword_180169738, r15d
0x1801212e9  mov     [rsp+270h+var_1F8], r15d
0x1801212ee  mov     [rsp+270h+var_200], eax
0x1801212f2  jz      loc_1801213B7
0x1801212f8  mov     rdx, 4000000000000800h; unsigned __int64
0x180121302  test    qword ptr cs:xmmword_180169738+8, rdx
0x180121309  jz      loc_1801213B7
0x18012130f  mov     rax, cs:qword_180169748
0x180121316  and     rax, rdx
0x180121319  cmp     cs:qword_180169748, rax
0x180121320  jnz     loc_1801213B7
0x180121326  lea     rcx, [rbp+170h+var_C0]; unsigned __int16 *
0x18012132d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180121332  lea     rcx, [rbp+170h+var_C0]
0x180121339  or      rax, 0FFFFFFFFFFFFFFFFh
0x18012133d  inc     rax
0x180121340  cmp     [rcx+rax*2], r15w
0x180121345  jnz     short loc_18012133D
0x180121347  lea     ecx, [rax+rax]
0x18012134a  lea     rax, [rbp+170h+var_C0]
0x180121351  add     rcx, 2
0x180121355  lea     r9, [rsp+270h+var_200]
0x18012135a  mov     [rsp+270h+var_210], rcx
0x18012135f  lea     rdx, PLA_EVENT_ERROR
0x180121366  mov     [rsp+270h+var_218], rax
0x18012136b  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180121372  mov     [rsp+270h+var_220], r13
0x180121377  lea     rax, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x18012137e  mov     [rsp+270h+var_228], rax
0x180121383  mov     r8d, 5
0x180121389  mov     [rsp+270h+var_230], r12
0x18012138e  lea     rax, [rsp+270h+var_1F8]
0x180121393  mov     [rsp+270h+var_238], rax
0x180121398  lea     rax, qword_180147320
0x18012139f  mov     [rsp+270h+var_240], 1
0x1801213a8  mov     [rsp+270h+var_248], rax
0x1801213ad  mov     [rsp+270h+var_250], r12
0x1801213b2  call    EventingWriteEvent
0x1801213b7  cmp     [rdi+8], r15d
0x1801213bb  jz      short loc_1801213C7
0x1801213bd  lea     rcx, [rdi+10h]; lpCriticalSection
0x1801213c1  call    cs:__imp_LeaveCriticalSection
0x1801213c7  cmp     [rbp+170h+ppvData], r15
0x1801213cb  jz      short loc_1801213D6
0x1801213cd  mov     rcx, [rbx]; psa
0x1801213d0  call    cs:__imp_SafeArrayUnaccessData
0x1801213d6  mov     eax, esi
0x1801213d8  mov     rcx, [rbp+170h+var_40]
0x1801213df  xor     rcx, rsp; StackCookie
0x1801213e2  call    __security_check_cookie
0x1801213e7  mov     rbx, [rsp+270h+arg_10]
0x1801213ef  add     rsp, 240h
0x1801213f6  pop     r15
0x1801213f8  pop     r14
0x1801213fa  pop     r13
0x1801213fc  pop     r12
0x1801213fe  pop     rdi
0x1801213ff  pop     rsi
0x180121400  pop     rbp
0x180121401  retn
```
