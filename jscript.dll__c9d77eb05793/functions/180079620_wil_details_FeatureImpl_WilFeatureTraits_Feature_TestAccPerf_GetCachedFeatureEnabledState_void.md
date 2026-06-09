# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x180079620`
- end: `0x180079947`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `807`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18007e140`

## callees

- `0x180059cd4`
- `0x180079620`
- `0x180079f00`
- `0x180096010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800798a4`
- `msvcrt!memcpy_s` at `0x180079927`
- `msvcrt!memcpy_s` at `0x1800798a4`
- `msvcrt!memcpy_s` at `0x180079927`
- `KERNEL32!HeapFree` at `0x1800798cb`
- `KERNEL32!HeapFree` at `0x1800798cb`
- `KERNEL32!SetLastError` at `0x180079834`
- `KERNEL32!SetLastError` at `0x1800798f0`
- `KERNEL32!SetLastError` at `0x180079834`
- `KERNEL32!SetLastError` at `0x1800798f0`
- `KERNEL32!GetLastError` at `0x180079810`
- `KERNEL32!GetLastError` at `0x180079810`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007969c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800796f9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180079708`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180079846`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007969c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800796f9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180079708`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180079846`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007967f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007979e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007967f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007979e`
- `KERNEL32!GetProcessHeap` at `0x1800798bd`
- `KERNEL32!GetProcessHeap` at `0x1800798bd`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // esi
  void (__fastcall *v5)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax
  signed __int32 v6; // eax
  __int16 v7; // bx
  signed __int32 v8; // edx
  unsigned int v9; // ecx
  int v10; // r8d
  void *v11; // r10
  unsigned __int64 v12; // r8
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rsi
  DWORD LastError; // ebp
  unsigned __int64 v16; // r15
  char *v17; // rax
  char *v18; // rsi
  char *v20; // r14
  void *v21; // r12
  HANDLE ProcessHeap; // rax
  rsize_t v23; // rdx
  _QWORD Source[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v25; // [rsp+70h] [rbp+8h] BYREF
  __int64 v26; // [rsp+78h] [rbp+10h] BYREF

  v25 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = dword_1800B70DC;
  if ( !dword_1800B70DC )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800B7120 )
      {
        v4 = dword_1800B70DC;
        ReleaseSRWLockExclusive(&SRWLock);
        goto LABEL_12;
      }
      v5 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_1800B7120 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v5 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v5(
          &qword_1800B7120,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
        if ( qword_1800B7120 )
        {
          v4 = 1;
          dword_1800B70DC = 1;
          ReleaseSRWLockExclusive(&SRWLock);
          goto LABEL_12;
        }
      }
      ReleaseSRWLockExclusive(&SRWLock);
    }
    v4 = 0;
  }
LABEL_12:
  LODWORD(v25) = 0;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(a1, &v26, &v25);
  v6 = *(_DWORD *)a2;
  v7 = v26;
  do
  {
    v8 = v6;
    *(_DWORD *)a2 = v6;
    v9 = v6;
    if ( (_DWORD)v25 && (v6 & 2) == 0 )
    {
      v9 = v7 & 0x9C1 | v6 & 0xFFFFF63E | 2;
      *(_DWORD *)a2 = v9;
    }
    v10 = v6 & 4;
    if ( (v6 & 4) == 0 )
    {
      v9 = v7 & 0x400 | v9 & 0xFFFFFBFF | 4;
      *(_DWORD *)a2 = v9;
    }
    v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v9, v6);
  }
  while ( v8 != v6 );
  if ( v10 || !wil::details::g_enabledStateManager )
    goto LABEL_31;
  AcquireSRWLockExclusive(&SRWLock);
  if ( !v4 || v4 != dword_1800B70DC )
    goto LABEL_29;
  v11 = Destination;
  v12 = qword_1800B7110;
  v13 = qword_1800B7110 - qword_1800B7100;
  Source[0] = 3;
  Source[1] = Feature_TestAccPerf__descriptor;
  if ( (unsigned __int64)Destination - qword_1800B7100 + 16 < qword_1800B7110 - qword_1800B7100 )
    goto LABEL_37;
  v14 = 16;
  if ( 2 * v13 > 0x10 )
    v14 = 2 * v13;
  if ( v13 >= v14 )
  {
LABEL_37:
    v23 = 0;
    if ( (unsigned __int64)v11 < v12 )
      v23 = v12 - (_QWORD)v11;
    memcpy_s(v11, v23, Source, 0x10u);
    Destination = (char *)Destination + 16;
    goto LABEL_30;
  }
  LastError = GetLastError();
  v16 = (v14 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
  v17 = (char *)wil::details::ProcessHeapAlloc(0, v16);
  v18 = v17;
  if ( v17 )
  {
    v20 = (char *)Destination - qword_1800B7100;
    memcpy_s(v17, v16, qword_1800B7100, (rsize_t)Destination - qword_1800B7100);
    v21 = lpMem;
    lpMem = v18;
    if ( v21 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v21);
    }
    qword_1800B7100 = v18;
    Destination = &v18[(_QWORD)v20];
    qword_1800B7110 = (__int64)&v18[v16];
    SetLastError(LastError);
    v12 = qword_1800B7110;
    v11 = Destination;
    goto LABEL_37;
  }
  SetLastError(LastError);
LABEL_29:
  _InterlockedAnd((volatile signed __int32 *)Feature_TestAccPerf__descriptor, 0xFFFFFFFB);
LABEL_30:
  ReleaseSRWLockExclusive(&SRWLock);
LABEL_31:
  if ( (*(_DWORD *)a2 & 2) == 0 )
    *(_DWORD *)a2 = *(_DWORD *)a2 & 0xFFFFF63E | v7 & 0x9C1;
  return a2;
}

```

## disassembly

```asm
0x180079620  mov     [rsp+arg_0], rcx
0x180079625  push    rdi
0x180079626  push    r13
0x180079628  push    r14
0x18007962a  sub     rsp, 50h
0x18007962e  mov     r14, cs:Feature_TestAccPerf__descriptor
0x180079635  xor     r13d, r13d
0x180079638  mov     [rdx], r13
0x18007963b  mov     rdi, rdx
0x18007963e  mov     eax, [r14]
0x180079641  mov     [rdx], eax
0x180079643  and     eax, 6
0x180079646  cmp     al, 6
0x180079648  jz      loc_18007993A
0x18007964e  mov     [rsp+68h+arg_10], rbx
0x180079656  mov     [rsp+68h+var_28], rsi
0x18007965b  mov     esi, cs:dword_1800B70DC
0x180079661  nop
0x180079662  test    esi, esi
0x180079664  jnz     loc_180079711
0x18007966a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180079670  test    eax, eax
0x180079672  jz      loc_18007970E
0x180079678  lea     rcx, SRWLock; SRWLock
0x18007967f  call    cs:__imp_AcquireSRWLockExclusive
0x180079685  cmp     cs:qword_1800B7120, r13
0x18007968c  jz      short loc_1800796A4
0x18007968e  mov     esi, cs:dword_1800B70DC
0x180079694  lea     rcx, SRWLock; SRWLock
0x18007969b  nop
0x18007969c  call    cs:__imp_ReleaseSRWLockExclusive
0x1800796a2  jmp     short loc_180079711
0x1800796a4  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800796ab  mov     cs:qword_1800B7120, r13
0x1800796b2  test    rax, rax
0x1800796b5  jnz     short loc_1800796C3
0x1800796b7  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800796be  test    rax, rax
0x1800796c1  jz      short loc_180079701
0x1800796c3  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800796ca  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x1800796d1  lea     rcx, qword_1800B7120
0x1800796d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800796dd  cmp     cs:qword_1800B7120, r13
0x1800796e4  jz      short loc_180079701
0x1800796e6  nop
0x1800796e7  lea     rcx, SRWLock; SRWLock
0x1800796ee  mov     esi, 1
0x1800796f3  mov     cs:dword_1800B70DC, esi
0x1800796f9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800796ff  jmp     short loc_180079711
0x180079701  lea     rcx, SRWLock; SRWLock
0x180079708  call    cs:__imp_ReleaseSRWLockExclusive
0x18007970e  mov     esi, r13d
0x180079711  lea     r8, [rsp+68h+arg_0]
0x180079716  mov     dword ptr [rsp+68h+arg_0], r13d
0x18007971b  lea     rdx, [rsp+68h+arg_8]
0x180079720  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x180079725  mov     eax, [rdi]
0x180079727  mov     rbx, [rsp+68h+arg_8]
0x18007972c  mov     edx, eax
0x18007972e  mov     [rdi], eax
0x180079730  mov     ecx, eax
0x180079732  cmp     dword ptr [rsp+68h+arg_0], r13d
0x180079737  jz      short loc_180079752
0x180079739  test    dl, 2
0x18007973c  jnz     short loc_180079752
0x18007973e  and     ecx, 0FFFFF63Eh
0x180079744  mov     eax, ebx
0x180079746  and     eax, 9C1h
0x18007974b  or      ecx, eax
0x18007974d  or      ecx, 2
0x180079750  mov     [rdi], ecx
0x180079752  mov     r8d, edx
0x180079755  and     r8d, 4
0x180079759  jnz     short loc_18007976D
0x18007975b  btr     ecx, 0Ah
0x18007975f  mov     eax, ebx
0x180079761  and     eax, 400h
0x180079766  or      ecx, eax
0x180079768  or      ecx, 4
0x18007976b  mov     [rdi], ecx
0x18007976d  mov     eax, edx
0x18007976f  lock cmpxchg [r14], ecx
0x180079774  jnz     short loc_18007972C
0x180079776  test    r8d, r8d
0x180079779  jnz     loc_180079856
0x18007977f  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180079785  test    eax, eax
0x180079787  jz      loc_180079856
0x18007978d  mov     [rsp+68h+var_20], rbp
0x180079792  lea     rcx, SRWLock; SRWLock
0x180079799  mov     [rsp+68h+var_38], r15
0x18007979e  call    cs:__imp_AcquireSRWLockExclusive
0x1800797a4  mov     eax, cs:dword_1800B70DC
0x1800797aa  test    esi, esi
0x1800797ac  jz      loc_18007983A
0x1800797b2  cmp     esi, eax
0x1800797b4  jnz     loc_18007983A
0x1800797ba  mov     r10, cs:Destination
0x1800797c1  mov     r8, cs:qword_1800B7110
0x1800797c8  mov     rax, r10
0x1800797cb  sub     rax, cs:qword_1800B7100
0x1800797d2  mov     rdx, r8
0x1800797d5  sub     rdx, cs:qword_1800B7100
0x1800797dc  add     rax, 10h
0x1800797e0  mov     [rsp+68h+Source], 3
0x1800797e9  mov     [rsp+68h+var_40], r14
0x1800797ee  cmp     rax, rdx
0x1800797f1  jb      loc_180079909
0x1800797f7  lea     rax, [rdx+rdx]
0x1800797fb  mov     esi, 10h
0x180079800  cmp     rax, rsi
0x180079803  cmova   rsi, rax
0x180079807  cmp     rdx, rsi
0x18007980a  jnb     loc_180079909
0x180079810  call    cs:__imp_GetLastError
0x180079816  and     rsi, 0FFFFFFFFFFFFFFC0h
0x18007981a  xor     ecx, ecx; dwFlags
0x18007981c  mov     ebp, eax
0x18007981e  lea     r15, [rsi+40h]
0x180079822  mov     rdx, r15; dwBytes
0x180079825  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18007982a  mov     rsi, rax
0x18007982d  test    rax, rax
0x180079830  jnz     short loc_180079885
0x180079832  mov     ecx, ebp; dwErrCode
0x180079834  call    cs:__imp_SetLastError
0x18007983a  lock and dword ptr [r14], 0FFFFFFFBh
0x18007983f  lea     rcx, SRWLock; SRWLock
0x180079846  call    cs:__imp_ReleaseSRWLockExclusive
0x18007984c  mov     r15, [rsp+68h+var_38]
0x180079851  mov     rbp, [rsp+68h+var_20]
0x180079856  mov     eax, [rdi]
0x180079858  mov     rsi, [rsp+68h+var_28]
0x18007985d  test    al, 2
0x18007985f  jnz     short loc_180079870
0x180079861  and     ebx, 9C1h
0x180079867  and     eax, 0FFFFF63Eh
0x18007986c  or      ebx, eax
0x18007986e  mov     [rdi], ebx
0x180079870  mov     rbx, [rsp+68h+arg_10]
0x180079878  mov     rax, rdi
0x18007987b  add     rsp, 50h
0x18007987f  pop     r14
0x180079881  pop     r13
0x180079883  pop     rdi
0x180079884  retn
0x180079885  mov     r8, cs:qword_1800B7100; Source
0x18007988c  mov     rdx, r15; DestinationSize
0x18007988f  mov     r14, cs:Destination
0x180079896  mov     rcx, rsi; Destination
0x180079899  sub     r14, r8
0x18007989c  mov     [rsp+68h+var_30], r12
0x1800798a1  mov     r9, r14; SourceSize
0x1800798a4  call    cs:__imp_memcpy_s
0x1800798aa  mov     r12, cs:lpMem
0x1800798b1  mov     cs:lpMem, rsi
0x1800798b8  test    r12, r12
0x1800798bb  jz      short loc_1800798D1
0x1800798bd  call    cs:__imp_GetProcessHeap
0x1800798c3  mov     r8, r12; lpMem
0x1800798c6  xor     edx, edx; dwFlags
0x1800798c8  mov     rcx, rax; hHeap
0x1800798cb  call    cs:__imp_HeapFree
0x1800798d1  lea     rax, [r14+rsi]
0x1800798d5  mov     cs:qword_1800B7100, rsi
0x1800798dc  mov     cs:Destination, rax
0x1800798e3  mov     ecx, ebp; dwErrCode
0x1800798e5  lea     rax, [r15+rsi]
0x1800798e9  mov     cs:qword_1800B7110, rax
0x1800798f0  call    cs:__imp_SetLastError
0x1800798f6  mov     r8, cs:qword_1800B7110
0x1800798fd  mov     r10, cs:Destination
0x180079904  mov     r12, [rsp+68h+var_30]
0x180079909  mov     rax, r8
0x18007990c  mov     rdx, r13
0x18007990f  sub     rax, r10
0x180079912  mov     r9d, 10h; SourceSize
0x180079918  cmp     r10, r8
0x18007991b  mov     rcx, r10; Destination
0x18007991e  lea     r8, [rsp+68h+Source]; Source
0x180079923  cmovb   rdx, rax; DestinationSize
0x180079927  call    cs:__imp_memcpy_s
0x18007992d  add     cs:Destination, 10h
0x180079935  jmp     loc_18007983F
0x18007993a  mov     rax, rdi
0x18007993d  add     rsp, 50h
0x180079941  pop     r14
0x180079943  pop     r13
0x180079945  pop     rdi
0x180079946  retn
```
