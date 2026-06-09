# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x18007ad30`
- end: `0x18007b094`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `868`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18007fab0`

## callees

- `0x18005ad2c`
- `0x18007ad30`
- `0x18007b6b0`
- `0x180098010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18007afd2`
- `msvcrt!memcpy_s` at `0x18007b06d`
- `msvcrt!memcpy_s` at `0x18007afd2`
- `msvcrt!memcpy_s` at `0x18007b06d`
- `KERNEL32!HeapFree` at `0x18007b005`
- `KERNEL32!HeapFree` at `0x18007b005`
- `KERNEL32!SetLastError` at `0x18007af55`
- `KERNEL32!SetLastError` at `0x18007b030`
- `KERNEL32!SetLastError` at `0x18007af55`
- `KERNEL32!SetLastError` at `0x18007b030`
- `KERNEL32!GetLastError` at `0x18007af2b`
- `KERNEL32!GetLastError` at `0x18007af2b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007adb2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007ae17`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007af6d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007adb2`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007ae17`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007af6d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007ad8f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007aeb3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007ad8f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007aeb3`
- `KERNEL32!GetProcessHeap` at `0x18007aff1`
- `KERNEL32!GetProcessHeap` at `0x18007aff1`

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
  v4 = dword_1800B90D4;
  if ( !dword_1800B90D4 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( qword_1800B90D8 )
      {
        v4 = dword_1800B90D4;
LABEL_6:
        ReleaseSRWLockExclusive(&SRWLock);
        goto LABEL_13;
      }
      v5 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      qword_1800B90D8 = 0;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v5 = (void (__fastcall *)(__int64 *, __int64 (__fastcall *)(void *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v5(
          &qword_1800B90D8,
          _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_,
          &wil::details::g_enabledStateManager);
        if ( qword_1800B90D8 )
        {
          v4 = 1;
          dword_1800B90D4 = 1;
          goto LABEL_6;
        }
      }
      ReleaseSRWLockExclusive(&SRWLock);
    }
    v4 = 0;
  }
LABEL_13:
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
    goto LABEL_32;
  AcquireSRWLockExclusive(&SRWLock);
  if ( !v4 || v4 != dword_1800B90D4 )
    goto LABEL_30;
  v11 = Destination;
  v12 = qword_1800B9118;
  v13 = qword_1800B9118 - qword_1800B9108;
  Source[0] = 3;
  Source[1] = Feature_TestAccPerf__descriptor;
  if ( (unsigned __int64)Destination - qword_1800B9108 + 16 < qword_1800B9118 - qword_1800B9108 )
    goto LABEL_38;
  v14 = 16;
  if ( 2 * v13 > 0x10 )
    v14 = 2 * v13;
  if ( v13 >= v14 )
  {
LABEL_38:
    v23 = 0;
    if ( (unsigned __int64)v11 < v12 )
      v23 = v12 - (_QWORD)v11;
    memcpy_s(v11, v23, Source, 0x10u);
    Destination = (char *)Destination + 16;
    goto LABEL_31;
  }
  LastError = GetLastError();
  v16 = (v14 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
  v17 = (char *)wil::details::ProcessHeapAlloc(0, v16);
  v18 = v17;
  if ( v17 )
  {
    v20 = (char *)Destination - qword_1800B9108;
    memcpy_s(v17, v16, qword_1800B9108, (rsize_t)Destination - qword_1800B9108);
    v21 = lpMem;
    lpMem = v18;
    if ( v21 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v21);
    }
    qword_1800B9108 = v18;
    Destination = &v18[(_QWORD)v20];
    qword_1800B9118 = (__int64)&v18[v16];
    SetLastError(LastError);
    v12 = qword_1800B9118;
    v11 = Destination;
    goto LABEL_38;
  }
  SetLastError(LastError);
LABEL_30:
  _InterlockedAnd((volatile signed __int32 *)Feature_TestAccPerf__descriptor, 0xFFFFFFFB);
LABEL_31:
  ReleaseSRWLockExclusive(&SRWLock);
LABEL_32:
  if ( (*(_DWORD *)a2 & 2) == 0 )
    *(_DWORD *)a2 = *(_DWORD *)a2 & 0xFFFFF63E | v7 & 0x9C1;
  return a2;
}

```

## disassembly

```asm
0x18007ad30  mov     [rsp+arg_0], rcx
0x18007ad35  push    rdi
0x18007ad36  push    r13
0x18007ad38  push    r14
0x18007ad3a  sub     rsp, 50h
0x18007ad3e  mov     r14, cs:Feature_TestAccPerf__descriptor
0x18007ad45  xor     r13d, r13d
0x18007ad48  mov     [rdx], r13
0x18007ad4b  mov     rdi, rdx
0x18007ad4e  mov     eax, [r14]
0x18007ad51  mov     [rdx], eax
0x18007ad53  and     eax, 6
0x18007ad56  cmp     al, 6
0x18007ad58  jz      loc_18007B086
0x18007ad5e  mov     [rsp+68h+arg_10], rbx
0x18007ad66  mov     [rsp+68h+var_28], rsi
0x18007ad6b  mov     esi, cs:dword_1800B90D4
0x18007ad71  nop
0x18007ad72  test    esi, esi
0x18007ad74  jnz     loc_18007AE26
0x18007ad7a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007ad80  test    eax, eax
0x18007ad82  jz      loc_18007AE23
0x18007ad88  lea     rcx, SRWLock; SRWLock
0x18007ad8f  call    cs:__imp_AcquireSRWLockExclusive
0x18007ad96  nop     dword ptr [rax+rax+00h]
0x18007ad9b  cmp     cs:qword_1800B90D8, r13
0x18007ada2  jz      short loc_18007ADC0
0x18007ada4  mov     esi, cs:dword_1800B90D4
0x18007adaa  nop
0x18007adab  lea     rcx, SRWLock; SRWLock
0x18007adb2  call    cs:__imp_ReleaseSRWLockExclusive
0x18007adb9  nop     dword ptr [rax+rax+00h]
0x18007adbe  jmp     short loc_18007AE26
0x18007adc0  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18007adc7  mov     cs:qword_1800B90D8, r13
0x18007adce  test    rax, rax
0x18007add1  jnz     short loc_18007ADDF
0x18007add3  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18007adda  test    rax, rax
0x18007addd  jz      short loc_18007AE10
0x18007addf  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007ade6  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18007aded  lea     rcx, qword_1800B90D8
0x18007adf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007adf9  cmp     cs:qword_1800B90D8, r13
0x18007ae00  jz      short loc_18007AE10
0x18007ae02  mov     esi, 1
0x18007ae07  nop
0x18007ae08  mov     cs:dword_1800B90D4, esi
0x18007ae0e  jmp     short loc_18007ADAB
0x18007ae10  lea     rcx, SRWLock; SRWLock
0x18007ae17  call    cs:__imp_ReleaseSRWLockExclusive
0x18007ae1e  nop     dword ptr [rax+rax+00h]
0x18007ae23  mov     esi, r13d
0x18007ae26  lea     r8, [rsp+68h+arg_0]
0x18007ae2b  mov     dword ptr [rsp+68h+arg_0], r13d
0x18007ae30  lea     rdx, [rsp+68h+arg_8]
0x18007ae35  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x18007ae3a  mov     eax, [rdi]
0x18007ae3c  mov     rbx, [rsp+68h+arg_8]
0x18007ae41  mov     edx, eax
0x18007ae43  mov     [rdi], eax
0x18007ae45  mov     ecx, eax
0x18007ae47  cmp     dword ptr [rsp+68h+arg_0], r13d
0x18007ae4c  jz      short loc_18007AE67
0x18007ae4e  test    dl, 2
0x18007ae51  jnz     short loc_18007AE67
0x18007ae53  and     ecx, 0FFFFF63Eh
0x18007ae59  mov     eax, ebx
0x18007ae5b  and     eax, 9C1h
0x18007ae60  or      ecx, eax
0x18007ae62  or      ecx, 2
0x18007ae65  mov     [rdi], ecx
0x18007ae67  mov     r8d, edx
0x18007ae6a  and     r8d, 4
0x18007ae6e  jnz     short loc_18007AE82
0x18007ae70  btr     ecx, 0Ah
0x18007ae74  mov     eax, ebx
0x18007ae76  and     eax, 400h
0x18007ae7b  or      ecx, eax
0x18007ae7d  or      ecx, 4
0x18007ae80  mov     [rdi], ecx
0x18007ae82  mov     eax, edx
0x18007ae84  lock cmpxchg [r14], ecx
0x18007ae89  jnz     short loc_18007AE41
0x18007ae8b  test    r8d, r8d
0x18007ae8e  jnz     loc_18007AF83
0x18007ae94  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007ae9a  test    eax, eax
0x18007ae9c  jz      loc_18007AF83
0x18007aea2  mov     [rsp+68h+var_20], rbp
0x18007aea7  lea     rcx, SRWLock; SRWLock
0x18007aeae  mov     [rsp+68h+var_38], r15
0x18007aeb3  call    cs:__imp_AcquireSRWLockExclusive
0x18007aeba  nop     dword ptr [rax+rax+00h]
0x18007aebf  mov     eax, cs:dword_1800B90D4
0x18007aec5  test    esi, esi
0x18007aec7  jz      loc_18007AF61
0x18007aecd  cmp     esi, eax
0x18007aecf  jnz     loc_18007AF61
0x18007aed5  mov     r10, cs:Destination
0x18007aedc  mov     r8, cs:qword_1800B9118
0x18007aee3  mov     rax, r10
0x18007aee6  sub     rax, cs:qword_1800B9108
0x18007aeed  mov     rdx, r8
0x18007aef0  sub     rdx, cs:qword_1800B9108
0x18007aef7  add     rax, 10h
0x18007aefb  mov     [rsp+68h+Source], 3
0x18007af04  mov     [rsp+68h+var_40], r14
0x18007af09  cmp     rax, rdx
0x18007af0c  jb      loc_18007B04F
0x18007af12  lea     rax, [rdx+rdx]
0x18007af16  mov     esi, 10h
0x18007af1b  cmp     rax, rsi
0x18007af1e  cmova   rsi, rax
0x18007af22  cmp     rdx, rsi
0x18007af25  jnb     loc_18007B04F
0x18007af2b  call    cs:__imp_GetLastError
0x18007af32  nop     dword ptr [rax+rax+00h]
0x18007af37  and     rsi, 0FFFFFFFFFFFFFFC0h
0x18007af3b  xor     ecx, ecx; dwFlags
0x18007af3d  mov     ebp, eax
0x18007af3f  lea     r15, [rsi+40h]
0x18007af43  mov     rdx, r15; dwBytes
0x18007af46  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18007af4b  mov     rsi, rax
0x18007af4e  test    rax, rax
0x18007af51  jnz     short loc_18007AFB3
0x18007af53  mov     ecx, ebp; dwErrCode
0x18007af55  call    cs:__imp_SetLastError
0x18007af5c  nop     dword ptr [rax+rax+00h]
0x18007af61  lock and dword ptr [r14], 0FFFFFFFBh
0x18007af66  lea     rcx, SRWLock; SRWLock
0x18007af6d  call    cs:__imp_ReleaseSRWLockExclusive
0x18007af74  nop     dword ptr [rax+rax+00h]
0x18007af79  mov     r15, [rsp+68h+var_38]
0x18007af7e  mov     rbp, [rsp+68h+var_20]
0x18007af83  mov     eax, [rdi]
0x18007af85  mov     rsi, [rsp+68h+var_28]
0x18007af8a  test    al, 2
0x18007af8c  jnz     short loc_18007AF9D
0x18007af8e  and     ebx, 9C1h
0x18007af94  and     eax, 0FFFFF63Eh
0x18007af99  or      ebx, eax
0x18007af9b  mov     [rdi], ebx
0x18007af9d  mov     rbx, [rsp+68h+arg_10]
0x18007afa5  mov     rax, rdi
0x18007afa8  add     rsp, 50h
0x18007afac  pop     r14
0x18007afae  pop     r13
0x18007afb0  pop     rdi
0x18007afb1  retn
0x18007afb3  mov     r8, cs:qword_1800B9108; Source
0x18007afba  mov     rdx, r15; DestinationSize
0x18007afbd  mov     r14, cs:Destination
0x18007afc4  mov     rcx, rsi; Destination
0x18007afc7  sub     r14, r8
0x18007afca  mov     [rsp+68h+var_30], r12
0x18007afcf  mov     r9, r14; SourceSize
0x18007afd2  call    cs:__imp_memcpy_s
0x18007afd9  nop     dword ptr [rax+rax+00h]
0x18007afde  mov     r12, cs:lpMem
0x18007afe5  mov     cs:lpMem, rsi
0x18007afec  test    r12, r12
0x18007afef  jz      short loc_18007B011
0x18007aff1  call    cs:__imp_GetProcessHeap
0x18007aff8  nop     dword ptr [rax+rax+00h]
0x18007affd  mov     r8, r12; lpMem
0x18007b000  xor     edx, edx; dwFlags
0x18007b002  mov     rcx, rax; hHeap
0x18007b005  call    cs:__imp_HeapFree
0x18007b00c  nop     dword ptr [rax+rax+00h]
0x18007b011  lea     rax, [r14+rsi]
0x18007b015  mov     cs:qword_1800B9108, rsi
0x18007b01c  mov     cs:Destination, rax
0x18007b023  mov     ecx, ebp; dwErrCode
0x18007b025  lea     rax, [r15+rsi]
0x18007b029  mov     cs:qword_1800B9118, rax
0x18007b030  call    cs:__imp_SetLastError
0x18007b037  nop     dword ptr [rax+rax+00h]
0x18007b03c  mov     r8, cs:qword_1800B9118
0x18007b043  mov     r10, cs:Destination
0x18007b04a  mov     r12, [rsp+68h+var_30]
0x18007b04f  mov     rax, r8
0x18007b052  mov     rdx, r13
0x18007b055  sub     rax, r10
0x18007b058  mov     r9d, 10h; SourceSize
0x18007b05e  cmp     r10, r8
0x18007b061  mov     rcx, r10; Destination
0x18007b064  lea     r8, [rsp+68h+Source]; Source
0x18007b069  cmovb   rdx, rax; DestinationSize
0x18007b06d  call    cs:__imp_memcpy_s
0x18007b074  nop     dword ptr [rax+rax+00h]
0x18007b079  add     cs:Destination, 10h
0x18007b081  jmp     loc_18007AF66
0x18007b086  mov     rax, rdi
0x18007b089  add     rsp, 50h
0x18007b08d  pop     r14
0x18007b08f  pop     r13
0x18007b091  pop     rdi
0x18007b092  retn
```
