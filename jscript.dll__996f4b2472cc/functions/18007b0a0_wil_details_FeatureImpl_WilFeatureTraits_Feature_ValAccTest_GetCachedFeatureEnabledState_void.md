# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18007b0a0`
- end: `0x18007b404`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `868`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18007fb00`

## callees

- `0x18005ad2c`
- `0x18007b0a0`
- `0x18007b7d0`
- `0x180098010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18007b342`
- `msvcrt!memcpy_s` at `0x18007b3dd`
- `msvcrt!memcpy_s` at `0x18007b342`
- `msvcrt!memcpy_s` at `0x18007b3dd`
- `KERNEL32!HeapFree` at `0x18007b375`
- `KERNEL32!HeapFree` at `0x18007b375`
- `KERNEL32!SetLastError` at `0x18007b2c5`
- `KERNEL32!SetLastError` at `0x18007b3a0`
- `KERNEL32!SetLastError` at `0x18007b2c5`
- `KERNEL32!SetLastError` at `0x18007b3a0`
- `KERNEL32!GetLastError` at `0x18007b29b`
- `KERNEL32!GetLastError` at `0x18007b29b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007b122`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007b187`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007b2dd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007b122`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007b187`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007b2dd`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007b0ff`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007b223`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007b0ff`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007b223`
- `KERNEL32!GetProcessHeap` at `0x18007b361`
- `KERNEL32!GetProcessHeap` at `0x18007b361`

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
    goto LABEL_32;
  AcquireSRWLockExclusive(&SRWLock);
  if ( !v4 || v4 != dword_1800B90D4 )
    goto LABEL_30;
  v11 = Destination;
  v12 = qword_1800B9118;
  v13 = qword_1800B9118 - qword_1800B9108;
  Source[0] = 3;
  Source[1] = Feature_ValAccTest__descriptor;
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
  _InterlockedAnd((volatile signed __int32 *)Feature_ValAccTest__descriptor, 0xFFFFFFFB);
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
0x18007b0a0  mov     [rsp+arg_0], rcx
0x18007b0a5  push    rdi
0x18007b0a6  push    r13
0x18007b0a8  push    r14
0x18007b0aa  sub     rsp, 50h
0x18007b0ae  mov     r14, cs:Feature_ValAccTest__descriptor
0x18007b0b5  xor     r13d, r13d
0x18007b0b8  mov     [rdx], r13
0x18007b0bb  mov     rdi, rdx
0x18007b0be  mov     eax, [r14]
0x18007b0c1  mov     [rdx], eax
0x18007b0c3  and     eax, 6
0x18007b0c6  cmp     al, 6
0x18007b0c8  jz      loc_18007B3F6
0x18007b0ce  mov     [rsp+68h+arg_10], rbx
0x18007b0d6  mov     [rsp+68h+var_28], rsi
0x18007b0db  mov     esi, cs:dword_1800B90D4
0x18007b0e1  nop
0x18007b0e2  test    esi, esi
0x18007b0e4  jnz     loc_18007B196
0x18007b0ea  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007b0f0  test    eax, eax
0x18007b0f2  jz      loc_18007B193
0x18007b0f8  lea     rcx, SRWLock; SRWLock
0x18007b0ff  call    cs:__imp_AcquireSRWLockExclusive
0x18007b106  nop     dword ptr [rax+rax+00h]
0x18007b10b  cmp     cs:qword_1800B90D8, r13
0x18007b112  jz      short loc_18007B130
0x18007b114  mov     esi, cs:dword_1800B90D4
0x18007b11a  nop
0x18007b11b  lea     rcx, SRWLock; SRWLock
0x18007b122  call    cs:__imp_ReleaseSRWLockExclusive
0x18007b129  nop     dword ptr [rax+rax+00h]
0x18007b12e  jmp     short loc_18007B196
0x18007b130  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18007b137  mov     cs:qword_1800B90D8, r13
0x18007b13e  test    rax, rax
0x18007b141  jnz     short loc_18007B14F
0x18007b143  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18007b14a  test    rax, rax
0x18007b14d  jz      short loc_18007B180
0x18007b14f  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007b156  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18007b15d  lea     rcx, qword_1800B90D8
0x18007b164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007b169  cmp     cs:qword_1800B90D8, r13
0x18007b170  jz      short loc_18007B180
0x18007b172  mov     esi, 1
0x18007b177  nop
0x18007b178  mov     cs:dword_1800B90D4, esi
0x18007b17e  jmp     short loc_18007B11B
0x18007b180  lea     rcx, SRWLock; SRWLock
0x18007b187  call    cs:__imp_ReleaseSRWLockExclusive
0x18007b18e  nop     dword ptr [rax+rax+00h]
0x18007b193  mov     esi, r13d
0x18007b196  lea     r8, [rsp+68h+arg_0]
0x18007b19b  mov     dword ptr [rsp+68h+arg_0], r13d
0x18007b1a0  lea     rdx, [rsp+68h+arg_8]
0x18007b1a5  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x18007b1aa  mov     eax, [rdi]
0x18007b1ac  mov     rbx, [rsp+68h+arg_8]
0x18007b1b1  mov     edx, eax
0x18007b1b3  mov     [rdi], eax
0x18007b1b5  mov     ecx, eax
0x18007b1b7  cmp     dword ptr [rsp+68h+arg_0], r13d
0x18007b1bc  jz      short loc_18007B1D7
0x18007b1be  test    dl, 2
0x18007b1c1  jnz     short loc_18007B1D7
0x18007b1c3  and     ecx, 0FFFFF63Eh
0x18007b1c9  mov     eax, ebx
0x18007b1cb  and     eax, 9C1h
0x18007b1d0  or      ecx, eax
0x18007b1d2  or      ecx, 2
0x18007b1d5  mov     [rdi], ecx
0x18007b1d7  mov     r8d, edx
0x18007b1da  and     r8d, 4
0x18007b1de  jnz     short loc_18007B1F2
0x18007b1e0  btr     ecx, 0Ah
0x18007b1e4  mov     eax, ebx
0x18007b1e6  and     eax, 400h
0x18007b1eb  or      ecx, eax
0x18007b1ed  or      ecx, 4
0x18007b1f0  mov     [rdi], ecx
0x18007b1f2  mov     eax, edx
0x18007b1f4  lock cmpxchg [r14], ecx
0x18007b1f9  jnz     short loc_18007B1B1
0x18007b1fb  test    r8d, r8d
0x18007b1fe  jnz     loc_18007B2F3
0x18007b204  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007b20a  test    eax, eax
0x18007b20c  jz      loc_18007B2F3
0x18007b212  mov     [rsp+68h+var_20], rbp
0x18007b217  lea     rcx, SRWLock; SRWLock
0x18007b21e  mov     [rsp+68h+var_38], r15
0x18007b223  call    cs:__imp_AcquireSRWLockExclusive
0x18007b22a  nop     dword ptr [rax+rax+00h]
0x18007b22f  mov     eax, cs:dword_1800B90D4
0x18007b235  test    esi, esi
0x18007b237  jz      loc_18007B2D1
0x18007b23d  cmp     esi, eax
0x18007b23f  jnz     loc_18007B2D1
0x18007b245  mov     r10, cs:Destination
0x18007b24c  mov     r8, cs:qword_1800B9118
0x18007b253  mov     rax, r10
0x18007b256  sub     rax, cs:qword_1800B9108
0x18007b25d  mov     rdx, r8
0x18007b260  sub     rdx, cs:qword_1800B9108
0x18007b267  add     rax, 10h
0x18007b26b  mov     [rsp+68h+Source], 3
0x18007b274  mov     [rsp+68h+var_40], r14
0x18007b279  cmp     rax, rdx
0x18007b27c  jb      loc_18007B3BF
0x18007b282  lea     rax, [rdx+rdx]
0x18007b286  mov     esi, 10h
0x18007b28b  cmp     rax, rsi
0x18007b28e  cmova   rsi, rax
0x18007b292  cmp     rdx, rsi
0x18007b295  jnb     loc_18007B3BF
0x18007b29b  call    cs:__imp_GetLastError
0x18007b2a2  nop     dword ptr [rax+rax+00h]
0x18007b2a7  and     rsi, 0FFFFFFFFFFFFFFC0h
0x18007b2ab  xor     ecx, ecx; dwFlags
0x18007b2ad  mov     ebp, eax
0x18007b2af  lea     r15, [rsi+40h]
0x18007b2b3  mov     rdx, r15; dwBytes
0x18007b2b6  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18007b2bb  mov     rsi, rax
0x18007b2be  test    rax, rax
0x18007b2c1  jnz     short loc_18007B323
0x18007b2c3  mov     ecx, ebp; dwErrCode
0x18007b2c5  call    cs:__imp_SetLastError
0x18007b2cc  nop     dword ptr [rax+rax+00h]
0x18007b2d1  lock and dword ptr [r14], 0FFFFFFFBh
0x18007b2d6  lea     rcx, SRWLock; SRWLock
0x18007b2dd  call    cs:__imp_ReleaseSRWLockExclusive
0x18007b2e4  nop     dword ptr [rax+rax+00h]
0x18007b2e9  mov     r15, [rsp+68h+var_38]
0x18007b2ee  mov     rbp, [rsp+68h+var_20]
0x18007b2f3  mov     eax, [rdi]
0x18007b2f5  mov     rsi, [rsp+68h+var_28]
0x18007b2fa  test    al, 2
0x18007b2fc  jnz     short loc_18007B30D
0x18007b2fe  and     ebx, 9C1h
0x18007b304  and     eax, 0FFFFF63Eh
0x18007b309  or      ebx, eax
0x18007b30b  mov     [rdi], ebx
0x18007b30d  mov     rbx, [rsp+68h+arg_10]
0x18007b315  mov     rax, rdi
0x18007b318  add     rsp, 50h
0x18007b31c  pop     r14
0x18007b31e  pop     r13
0x18007b320  pop     rdi
0x18007b321  retn
0x18007b323  mov     r8, cs:qword_1800B9108; Source
0x18007b32a  mov     rdx, r15; DestinationSize
0x18007b32d  mov     r14, cs:Destination
0x18007b334  mov     rcx, rsi; Destination
0x18007b337  sub     r14, r8
0x18007b33a  mov     [rsp+68h+var_30], r12
0x18007b33f  mov     r9, r14; SourceSize
0x18007b342  call    cs:__imp_memcpy_s
0x18007b349  nop     dword ptr [rax+rax+00h]
0x18007b34e  mov     r12, cs:lpMem
0x18007b355  mov     cs:lpMem, rsi
0x18007b35c  test    r12, r12
0x18007b35f  jz      short loc_18007B381
0x18007b361  call    cs:__imp_GetProcessHeap
0x18007b368  nop     dword ptr [rax+rax+00h]
0x18007b36d  mov     r8, r12; lpMem
0x18007b370  xor     edx, edx; dwFlags
0x18007b372  mov     rcx, rax; hHeap
0x18007b375  call    cs:__imp_HeapFree
0x18007b37c  nop     dword ptr [rax+rax+00h]
0x18007b381  lea     rax, [r14+rsi]
0x18007b385  mov     cs:qword_1800B9108, rsi
0x18007b38c  mov     cs:Destination, rax
0x18007b393  mov     ecx, ebp; dwErrCode
0x18007b395  lea     rax, [r15+rsi]
0x18007b399  mov     cs:qword_1800B9118, rax
0x18007b3a0  call    cs:__imp_SetLastError
0x18007b3a7  nop     dword ptr [rax+rax+00h]
0x18007b3ac  mov     r8, cs:qword_1800B9118
0x18007b3b3  mov     r10, cs:Destination
0x18007b3ba  mov     r12, [rsp+68h+var_30]
0x18007b3bf  mov     rax, r8
0x18007b3c2  mov     rdx, r13
0x18007b3c5  sub     rax, r10
0x18007b3c8  mov     r9d, 10h; SourceSize
0x18007b3ce  cmp     r10, r8
0x18007b3d1  mov     rcx, r10; Destination
0x18007b3d4  lea     r8, [rsp+68h+Source]; Source
0x18007b3d9  cmovb   rdx, rax; DestinationSize
0x18007b3dd  call    cs:__imp_memcpy_s
0x18007b3e4  nop     dword ptr [rax+rax+00h]
0x18007b3e9  add     cs:Destination, 10h
0x18007b3f1  jmp     loc_18007B2D6
0x18007b3f6  mov     rax, rdi
0x18007b3f9  add     rsp, 50h
0x18007b3fd  pop     r14
0x18007b3ff  pop     r13
0x18007b401  pop     rdi
0x18007b402  retn
```
