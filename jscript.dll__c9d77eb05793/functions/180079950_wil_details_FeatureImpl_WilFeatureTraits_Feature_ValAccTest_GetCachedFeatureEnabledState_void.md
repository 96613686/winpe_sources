# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180079950`
- end: `0x180079c77`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `807`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18007e190`

## callees

- `0x180059cd4`
- `0x180079950`
- `0x18007a020`
- `0x180096010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180079bd4`
- `msvcrt!memcpy_s` at `0x180079c57`
- `msvcrt!memcpy_s` at `0x180079bd4`
- `msvcrt!memcpy_s` at `0x180079c57`
- `KERNEL32!HeapFree` at `0x180079bfb`
- `KERNEL32!HeapFree` at `0x180079bfb`
- `KERNEL32!SetLastError` at `0x180079b64`
- `KERNEL32!SetLastError` at `0x180079c20`
- `KERNEL32!SetLastError` at `0x180079b64`
- `KERNEL32!SetLastError` at `0x180079c20`
- `KERNEL32!GetLastError` at `0x180079b40`
- `KERNEL32!GetLastError` at `0x180079b40`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800799cc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180079a29`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180079a38`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180079b76`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800799cc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180079a29`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180079a38`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180079b76`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800799af`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180079ace`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800799af`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180079ace`
- `KERNEL32!GetProcessHeap` at `0x180079bed`
- `KERNEL32!GetProcessHeap` at `0x180079bed`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
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
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(a1, &v26, &v25);
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
    v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v9, v6);
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
  Source[1] = Feature_ValAccTest__descriptor;
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
  _InterlockedAnd((volatile signed __int32 *)Feature_ValAccTest__descriptor, 0xFFFFFFFB);
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
0x180079950  mov     [rsp+arg_0], rcx
0x180079955  push    rdi
0x180079956  push    r13
0x180079958  push    r14
0x18007995a  sub     rsp, 50h
0x18007995e  mov     r14, cs:Feature_ValAccTest__descriptor
0x180079965  xor     r13d, r13d
0x180079968  mov     [rdx], r13
0x18007996b  mov     rdi, rdx
0x18007996e  mov     eax, [r14]
0x180079971  mov     [rdx], eax
0x180079973  and     eax, 6
0x180079976  cmp     al, 6
0x180079978  jz      loc_180079C6A
0x18007997e  mov     [rsp+68h+arg_10], rbx
0x180079986  mov     [rsp+68h+var_28], rsi
0x18007998b  mov     esi, cs:dword_1800B70DC
0x180079991  nop
0x180079992  test    esi, esi
0x180079994  jnz     loc_180079A41
0x18007999a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800799a0  test    eax, eax
0x1800799a2  jz      loc_180079A3E
0x1800799a8  lea     rcx, SRWLock; SRWLock
0x1800799af  call    cs:__imp_AcquireSRWLockExclusive
0x1800799b5  cmp     cs:qword_1800B7120, r13
0x1800799bc  jz      short loc_1800799D4
0x1800799be  mov     esi, cs:dword_1800B70DC
0x1800799c4  lea     rcx, SRWLock; SRWLock
0x1800799cb  nop
0x1800799cc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800799d2  jmp     short loc_180079A41
0x1800799d4  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800799db  mov     cs:qword_1800B7120, r13
0x1800799e2  test    rax, rax
0x1800799e5  jnz     short loc_1800799F3
0x1800799e7  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1800799ee  test    rax, rax
0x1800799f1  jz      short loc_180079A31
0x1800799f3  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800799fa  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180079a01  lea     rcx, qword_1800B7120
0x180079a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079a0d  cmp     cs:qword_1800B7120, r13
0x180079a14  jz      short loc_180079A31
0x180079a16  nop
0x180079a17  lea     rcx, SRWLock; SRWLock
0x180079a1e  mov     esi, 1
0x180079a23  mov     cs:dword_1800B70DC, esi
0x180079a29  call    cs:__imp_ReleaseSRWLockExclusive
0x180079a2f  jmp     short loc_180079A41
0x180079a31  lea     rcx, SRWLock; SRWLock
0x180079a38  call    cs:__imp_ReleaseSRWLockExclusive
0x180079a3e  mov     esi, r13d
0x180079a41  lea     r8, [rsp+68h+arg_0]
0x180079a46  mov     dword ptr [rsp+68h+arg_0], r13d
0x180079a4b  lea     rdx, [rsp+68h+arg_8]
0x180079a50  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x180079a55  mov     eax, [rdi]
0x180079a57  mov     rbx, [rsp+68h+arg_8]
0x180079a5c  mov     edx, eax
0x180079a5e  mov     [rdi], eax
0x180079a60  mov     ecx, eax
0x180079a62  cmp     dword ptr [rsp+68h+arg_0], r13d
0x180079a67  jz      short loc_180079A82
0x180079a69  test    dl, 2
0x180079a6c  jnz     short loc_180079A82
0x180079a6e  and     ecx, 0FFFFF63Eh
0x180079a74  mov     eax, ebx
0x180079a76  and     eax, 9C1h
0x180079a7b  or      ecx, eax
0x180079a7d  or      ecx, 2
0x180079a80  mov     [rdi], ecx
0x180079a82  mov     r8d, edx
0x180079a85  and     r8d, 4
0x180079a89  jnz     short loc_180079A9D
0x180079a8b  btr     ecx, 0Ah
0x180079a8f  mov     eax, ebx
0x180079a91  and     eax, 400h
0x180079a96  or      ecx, eax
0x180079a98  or      ecx, 4
0x180079a9b  mov     [rdi], ecx
0x180079a9d  mov     eax, edx
0x180079a9f  lock cmpxchg [r14], ecx
0x180079aa4  jnz     short loc_180079A5C
0x180079aa6  test    r8d, r8d
0x180079aa9  jnz     loc_180079B86
0x180079aaf  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180079ab5  test    eax, eax
0x180079ab7  jz      loc_180079B86
0x180079abd  mov     [rsp+68h+var_20], rbp
0x180079ac2  lea     rcx, SRWLock; SRWLock
0x180079ac9  mov     [rsp+68h+var_38], r15
0x180079ace  call    cs:__imp_AcquireSRWLockExclusive
0x180079ad4  mov     eax, cs:dword_1800B70DC
0x180079ada  test    esi, esi
0x180079adc  jz      loc_180079B6A
0x180079ae2  cmp     esi, eax
0x180079ae4  jnz     loc_180079B6A
0x180079aea  mov     r10, cs:Destination
0x180079af1  mov     r8, cs:qword_1800B7110
0x180079af8  mov     rax, r10
0x180079afb  sub     rax, cs:qword_1800B7100
0x180079b02  mov     rdx, r8
0x180079b05  sub     rdx, cs:qword_1800B7100
0x180079b0c  add     rax, 10h
0x180079b10  mov     [rsp+68h+Source], 3
0x180079b19  mov     [rsp+68h+var_40], r14
0x180079b1e  cmp     rax, rdx
0x180079b21  jb      loc_180079C39
0x180079b27  lea     rax, [rdx+rdx]
0x180079b2b  mov     esi, 10h
0x180079b30  cmp     rax, rsi
0x180079b33  cmova   rsi, rax
0x180079b37  cmp     rdx, rsi
0x180079b3a  jnb     loc_180079C39
0x180079b40  call    cs:__imp_GetLastError
0x180079b46  and     rsi, 0FFFFFFFFFFFFFFC0h
0x180079b4a  xor     ecx, ecx; dwFlags
0x180079b4c  mov     ebp, eax
0x180079b4e  lea     r15, [rsi+40h]
0x180079b52  mov     rdx, r15; dwBytes
0x180079b55  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180079b5a  mov     rsi, rax
0x180079b5d  test    rax, rax
0x180079b60  jnz     short loc_180079BB5
0x180079b62  mov     ecx, ebp; dwErrCode
0x180079b64  call    cs:__imp_SetLastError
0x180079b6a  lock and dword ptr [r14], 0FFFFFFFBh
0x180079b6f  lea     rcx, SRWLock; SRWLock
0x180079b76  call    cs:__imp_ReleaseSRWLockExclusive
0x180079b7c  mov     r15, [rsp+68h+var_38]
0x180079b81  mov     rbp, [rsp+68h+var_20]
0x180079b86  mov     eax, [rdi]
0x180079b88  mov     rsi, [rsp+68h+var_28]
0x180079b8d  test    al, 2
0x180079b8f  jnz     short loc_180079BA0
0x180079b91  and     ebx, 9C1h
0x180079b97  and     eax, 0FFFFF63Eh
0x180079b9c  or      ebx, eax
0x180079b9e  mov     [rdi], ebx
0x180079ba0  mov     rbx, [rsp+68h+arg_10]
0x180079ba8  mov     rax, rdi
0x180079bab  add     rsp, 50h
0x180079baf  pop     r14
0x180079bb1  pop     r13
0x180079bb3  pop     rdi
0x180079bb4  retn
0x180079bb5  mov     r8, cs:qword_1800B7100; Source
0x180079bbc  mov     rdx, r15; DestinationSize
0x180079bbf  mov     r14, cs:Destination
0x180079bc6  mov     rcx, rsi; Destination
0x180079bc9  sub     r14, r8
0x180079bcc  mov     [rsp+68h+var_30], r12
0x180079bd1  mov     r9, r14; SourceSize
0x180079bd4  call    cs:__imp_memcpy_s
0x180079bda  mov     r12, cs:lpMem
0x180079be1  mov     cs:lpMem, rsi
0x180079be8  test    r12, r12
0x180079beb  jz      short loc_180079C01
0x180079bed  call    cs:__imp_GetProcessHeap
0x180079bf3  mov     r8, r12; lpMem
0x180079bf6  xor     edx, edx; dwFlags
0x180079bf8  mov     rcx, rax; hHeap
0x180079bfb  call    cs:__imp_HeapFree
0x180079c01  lea     rax, [r14+rsi]
0x180079c05  mov     cs:qword_1800B7100, rsi
0x180079c0c  mov     cs:Destination, rax
0x180079c13  mov     ecx, ebp; dwErrCode
0x180079c15  lea     rax, [r15+rsi]
0x180079c19  mov     cs:qword_1800B7110, rax
0x180079c20  call    cs:__imp_SetLastError
0x180079c26  mov     r8, cs:qword_1800B7110
0x180079c2d  mov     r10, cs:Destination
0x180079c34  mov     r12, [rsp+68h+var_30]
0x180079c39  mov     rax, r8
0x180079c3c  mov     rdx, r13
0x180079c3f  sub     rax, r10
0x180079c42  mov     r9d, 10h; SourceSize
0x180079c48  cmp     r10, r8
0x180079c4b  mov     rcx, r10; Destination
0x180079c4e  lea     r8, [rsp+68h+Source]; Source
0x180079c53  cmovb   rdx, rax; DestinationSize
0x180079c57  call    cs:__imp_memcpy_s
0x180079c5d  add     cs:Destination, 10h
0x180079c65  jmp     loc_180079B6F
0x180079c6a  mov     rax, rdi
0x180079c6d  add     rsp, 50h
0x180079c71  pop     r14
0x180079c73  pop     r13
0x180079c75  pop     rdi
0x180079c76  retn
```
