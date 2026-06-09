# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18007a550`
- end: `0x18007a933`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `995`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18007b7d0`

## callees

- `0x18005ad2c`
- `0x18007a550`
- `0x180098010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18007a871`
- `msvcrt!memcpy_s` at `0x18007a90d`
- `msvcrt!memcpy_s` at `0x18007a871`
- `msvcrt!memcpy_s` at `0x18007a90d`
- `KERNEL32!HeapFree` at `0x18007a8a4`
- `KERNEL32!HeapFree` at `0x18007a8a4`
- `KERNEL32!SetLastError` at `0x18007a7e3`
- `KERNEL32!SetLastError` at `0x18007a8d0`
- `KERNEL32!SetLastError` at `0x18007a7e3`
- `KERNEL32!SetLastError` at `0x18007a8d0`
- `KERNEL32!GetLastError` at `0x18007a7b7`
- `KERNEL32!GetLastError` at `0x18007a7b7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007a5cd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007a632`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007a7fa`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007a5cd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007a632`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007a7fa`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007a5aa`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007a73f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007a5aa`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007a73f`
- `KERNEL32!GetProcessHeap` at `0x18007a890`
- `KERNEL32!GetProcessHeap` at `0x18007a890`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  void (__fastcall *v5)(__int64 *, __int64 (__fastcall *)(void *), void *); // rax
  __int64 (__fastcall *v6)(__int64, __int64, __int64 *); // rax
  int v7; // eax
  unsigned int v8; // r8d
  __int16 v9; // si
  __int16 v10; // ax
  unsigned __int16 v11; // si
  int v12; // eax
  signed __int32 v13; // edx
  signed __int32 v14; // ecx
  void *v15; // r10
  unsigned __int64 v16; // r8
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rbp
  DWORD LastError; // r15d
  unsigned __int64 v20; // r14
  char *v21; // rax
  char *v22; // rbp
  int v23; // ecx
  char *v25; // rdi
  void *v26; // r12
  HANDLE ProcessHeap; // rax
  rsize_t v28; // rdx
  _QWORD Source[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v30; // [rsp+60h] [rbp+8h] BYREF

  v30 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
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
  v6 = (__int64 (__fastcall *)(__int64, __int64, __int64 *))g_wil_details_internalGetFeatureEnabledState;
  LODWORD(v30) = 0;
  if ( !g_wil_details_internalGetFeatureEnabledState )
  {
    v6 = (__int64 (__fastcall *)(__int64, __int64, __int64 *))g_wil_details_apiGetFeatureEnabledState;
    if ( !g_wil_details_apiGetFeatureEnabledState )
    {
      v9 = 0;
      goto LABEL_20;
    }
  }
  v7 = v6(45036792, 3, &v30);
  v8 = v7 & 0xFFFFFF3F;
  v9 = 8 * (v7 & 0x80 | (4 * (v7 & 0x40 | (4 * (v7 & 3)))));
  if ( (v7 & 0xFFFFFF3F) == 0 )
  {
LABEL_20:
    v10 = 64;
    goto LABEL_21;
  }
  v10 = 0;
  if ( v8 == 2 )
    v10 = 64;
LABEL_21:
  v11 = v10 | v9;
  v12 = *(_DWORD *)a2;
  do
  {
    v13 = v12;
    *(_DWORD *)a2 = v12;
    if ( (_DWORD)v30 && (v12 & 2) == 0 )
    {
      v12 = (v12
           ^ (v11
            ^ (unsigned __int16)v12)
           & 0x180
           ^ ((unsigned __int8)v11
            ^ (unsigned __int8)(v12 ^ (v11 ^ v12) & 0x80))
           & 0x40
           | 1)
          ^ (v11
           ^ ((unsigned __int16)(v12
                               ^ (v11
                                ^ v12)
                               & 0x180
                               ^ ((unsigned __int8)v11
                                ^ (unsigned __int8)(v12 ^ (v11 ^ v12) & 0x80))
                               & 0x40)
            | 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v12;
    }
    v14 = v12;
    if ( (v13 & 4) == 0 )
    {
      v14 = v12 ^ (v11 ^ (unsigned __int16)v12) & 0x400 | 4;
      *(_DWORD *)a2 = v14;
    }
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v14, v13);
  }
  while ( v13 != v12 );
  if ( (v13 & 4) != 0 || !wil::details::g_enabledStateManager )
    goto LABEL_40;
  AcquireSRWLockExclusive(&SRWLock);
  if ( !v4 || v4 != dword_1800B90D4 )
    goto LABEL_38;
  v15 = Destination;
  v16 = qword_1800B9118;
  v17 = qword_1800B9118 - qword_1800B9108;
  Source[0] = 3;
  Source[1] = Feature_Standalone_25_10_NonSec__descriptor;
  if ( (unsigned __int64)Destination - qword_1800B9108 + 16 < qword_1800B9118 - qword_1800B9108 )
    goto LABEL_46;
  v18 = 16;
  if ( 2 * v17 > 0x10 )
    v18 = 2 * v17;
  if ( v17 >= v18 )
  {
LABEL_46:
    v28 = 0;
    if ( (unsigned __int64)v15 < v16 )
      v28 = v16 - (_QWORD)v15;
    memcpy_s(v15, v28, Source, 0x10u);
    Destination = (char *)Destination + 16;
    goto LABEL_39;
  }
  LastError = GetLastError();
  v20 = (v18 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
  v21 = (char *)wil::details::ProcessHeapAlloc(0, v20);
  v22 = v21;
  if ( v21 )
  {
    v25 = (char *)Destination - qword_1800B9108;
    memcpy_s(v21, v20, qword_1800B9108, (rsize_t)Destination - qword_1800B9108);
    v26 = lpMem;
    lpMem = v22;
    if ( v26 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v26);
    }
    qword_1800B9108 = v22;
    Destination = &v22[(_QWORD)v25];
    qword_1800B9118 = (__int64)&v22[v20];
    SetLastError(LastError);
    v16 = qword_1800B9118;
    v15 = Destination;
    goto LABEL_46;
  }
  SetLastError(LastError);
LABEL_38:
  _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, 0xFFFFFFFB);
LABEL_39:
  ReleaseSRWLockExclusive(&SRWLock);
LABEL_40:
  if ( (*(_DWORD *)a2 & 2) == 0 )
  {
    v23 = *(_DWORD *)a2
        ^ (v11
         ^ (unsigned __int16)*(_DWORD *)a2)
        & 0x180
        ^ ((unsigned __int8)v11
         ^ (unsigned __int8)(*(_DWORD *)a2 ^ (v11 ^ *(_DWORD *)a2) & 0x80))
        & 0x40
        | 1;
    *(_DWORD *)a2 = v23 ^ (v11 ^ (unsigned __int16)v23) & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x18007a550  mov     [rsp+arg_0], rcx
0x18007a555  push    rbx
0x18007a556  push    rdi
0x18007a557  push    r13
0x18007a559  sub     rsp, 40h
0x18007a55d  mov     rdi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x18007a564  xor     r13d, r13d
0x18007a567  mov     [rdx], r13
0x18007a56a  mov     rbx, rdx
0x18007a56d  mov     eax, [rdi]
0x18007a56f  mov     [rdx], eax
0x18007a571  and     eax, 6
0x18007a574  cmp     al, 6
0x18007a576  jz      loc_18007A926
0x18007a57c  mov     [rsp+58h+arg_8], rbp
0x18007a581  mov     ebp, cs:dword_1800B90D4
0x18007a587  nop
0x18007a588  mov     [rsp+58h+arg_10], rsi
0x18007a58d  test    ebp, ebp
0x18007a58f  jnz     loc_18007A641
0x18007a595  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007a59b  test    eax, eax
0x18007a59d  jz      loc_18007A63E
0x18007a5a3  lea     rcx, SRWLock; SRWLock
0x18007a5aa  call    cs:__imp_AcquireSRWLockExclusive
0x18007a5b1  nop     dword ptr [rax+rax+00h]
0x18007a5b6  cmp     cs:qword_1800B90D8, r13
0x18007a5bd  jz      short loc_18007A5DB
0x18007a5bf  mov     ebp, cs:dword_1800B90D4
0x18007a5c5  nop
0x18007a5c6  lea     rcx, SRWLock; SRWLock
0x18007a5cd  call    cs:__imp_ReleaseSRWLockExclusive
0x18007a5d4  nop     dword ptr [rax+rax+00h]
0x18007a5d9  jmp     short loc_18007A641
0x18007a5db  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18007a5e2  mov     cs:qword_1800B90D8, r13
0x18007a5e9  test    rax, rax
0x18007a5ec  jnz     short loc_18007A5FA
0x18007a5ee  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18007a5f5  test    rax, rax
0x18007a5f8  jz      short loc_18007A62B
0x18007a5fa  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007a601  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18007a608  lea     rcx, qword_1800B90D8
0x18007a60f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a614  cmp     cs:qword_1800B90D8, r13
0x18007a61b  jz      short loc_18007A62B
0x18007a61d  mov     ebp, 1
0x18007a622  nop
0x18007a623  mov     cs:dword_1800B90D4, ebp
0x18007a629  jmp     short loc_18007A5C6
0x18007a62b  lea     rcx, SRWLock; SRWLock
0x18007a632  call    cs:__imp_ReleaseSRWLockExclusive
0x18007a639  nop     dword ptr [rax+rax+00h]
0x18007a63e  mov     ebp, r13d
0x18007a641  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18007a648  mov     dword ptr [rsp+58h+arg_0], r13d
0x18007a64d  test    rax, rax
0x18007a650  jnz     short loc_18007A65E
0x18007a652  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18007a659  test    rax, rax
0x18007a65c  jz      short loc_18007A6B4
0x18007a65e  lea     r8, [rsp+58h+arg_0]
0x18007a663  mov     edx, 3
0x18007a668  mov     ecx, 2AF34F8h
0x18007a66d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a672  mov     r8d, eax
0x18007a675  mov     edx, eax
0x18007a677  and     r8d, 0FFFFFF3Fh
0x18007a67e  and     eax, 40h
0x18007a681  and     edx, 80h
0x18007a687  mov     ecx, r8d
0x18007a68a  and     ecx, 3
0x18007a68d  shl     ecx, 2
0x18007a690  or      ecx, eax
0x18007a692  shl     ecx, 2
0x18007a695  or      ecx, edx
0x18007a697  lea     esi, ds:0[rcx*8]
0x18007a69e  test    r8d, r8d
0x18007a6a1  jz      short loc_18007A6B7
0x18007a6a3  cmp     r8d, 2
0x18007a6a7  mov     eax, r13d
0x18007a6aa  mov     ecx, 40h ; '@'
0x18007a6af  cmovz   eax, ecx
0x18007a6b2  jmp     short loc_18007A6BC
0x18007a6b4  mov     esi, r13d
0x18007a6b7  mov     eax, 40h ; '@'
0x18007a6bc  or      esi, eax
0x18007a6be  mov     eax, [rbx]
0x18007a6c0  mov     edx, eax
0x18007a6c2  mov     [rbx], eax
0x18007a6c4  cmp     dword ptr [rsp+58h+arg_0], r13d
0x18007a6c9  jz      short loc_18007A6F5
0x18007a6cb  test    dl, 2
0x18007a6ce  jnz     short loc_18007A6F5
0x18007a6d0  xor     eax, esi
0x18007a6d2  and     eax, 180h
0x18007a6d7  xor     eax, edx
0x18007a6d9  mov     ecx, eax
0x18007a6db  xor     ecx, esi
0x18007a6dd  and     ecx, 40h
0x18007a6e0  xor     ecx, eax
0x18007a6e2  or      ecx, 1
0x18007a6e5  mov     eax, ecx
0x18007a6e7  xor     eax, esi
0x18007a6e9  and     eax, 800h
0x18007a6ee  xor     eax, ecx
0x18007a6f0  or      eax, 2
0x18007a6f3  mov     [rbx], eax
0x18007a6f5  mov     r8d, edx
0x18007a6f8  mov     ecx, eax
0x18007a6fa  and     r8d, 4
0x18007a6fe  jnz     short loc_18007A70F
0x18007a700  xor     ecx, esi
0x18007a702  and     ecx, 400h
0x18007a708  xor     ecx, eax
0x18007a70a  or      ecx, 4
0x18007a70d  mov     [rbx], ecx
0x18007a70f  mov     eax, edx
0x18007a711  lock cmpxchg [rdi], ecx
0x18007a715  jnz     short loc_18007A6C0
0x18007a717  test    r8d, r8d
0x18007a71a  jnz     loc_18007A810
0x18007a720  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007a726  test    eax, eax
0x18007a728  jz      loc_18007A810
0x18007a72e  mov     [rsp+58h+var_20], r14
0x18007a733  lea     rcx, SRWLock; SRWLock
0x18007a73a  mov     [rsp+58h+var_28], r15
0x18007a73f  call    cs:__imp_AcquireSRWLockExclusive
0x18007a746  nop     dword ptr [rax+rax+00h]
0x18007a74b  mov     eax, cs:dword_1800B90D4
0x18007a751  test    ebp, ebp
0x18007a753  jz      loc_18007A7EF
0x18007a759  cmp     ebp, eax
0x18007a75b  jnz     loc_18007A7EF
0x18007a761  mov     r10, cs:Destination
0x18007a768  mov     r8, cs:qword_1800B9118
0x18007a76f  mov     rax, r10
0x18007a772  sub     rax, cs:qword_1800B9108
0x18007a779  mov     rdx, r8
0x18007a77c  sub     rdx, cs:qword_1800B9108
0x18007a783  add     rax, 10h
0x18007a787  mov     [rsp+58h+Source], 3
0x18007a790  mov     [rsp+58h+var_30], rdi
0x18007a795  cmp     rax, rdx
0x18007a798  jb      loc_18007A8EF
0x18007a79e  lea     rax, [rdx+rdx]
0x18007a7a2  mov     ebp, 10h
0x18007a7a7  cmp     rax, rbp
0x18007a7aa  cmova   rbp, rax
0x18007a7ae  cmp     rdx, rbp
0x18007a7b1  jnb     loc_18007A8EF
0x18007a7b7  call    cs:__imp_GetLastError
0x18007a7be  nop     dword ptr [rax+rax+00h]
0x18007a7c3  and     rbp, 0FFFFFFFFFFFFFFC0h
0x18007a7c7  xor     ecx, ecx; dwFlags
0x18007a7c9  mov     r15d, eax
0x18007a7cc  lea     r14, [rbp+40h]
0x18007a7d0  mov     rdx, r14; dwBytes
0x18007a7d3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18007a7d8  mov     rbp, rax
0x18007a7db  test    rax, rax
0x18007a7de  jnz     short loc_18007A852
0x18007a7e0  mov     ecx, r15d; dwErrCode
0x18007a7e3  call    cs:__imp_SetLastError
0x18007a7ea  nop     dword ptr [rax+rax+00h]
0x18007a7ef  lock and dword ptr [rdi], 0FFFFFFFBh
0x18007a7f3  lea     rcx, SRWLock; SRWLock
0x18007a7fa  call    cs:__imp_ReleaseSRWLockExclusive
0x18007a801  nop     dword ptr [rax+rax+00h]
0x18007a806  mov     r15, [rsp+58h+var_28]
0x18007a80b  mov     r14, [rsp+58h+var_20]
0x18007a810  mov     ecx, [rbx]
0x18007a812  mov     rbp, [rsp+58h+arg_8]
0x18007a817  test    cl, 2
0x18007a81a  jnz     short loc_18007A840
0x18007a81c  mov     eax, ecx
0x18007a81e  xor     eax, esi
0x18007a820  and     eax, 180h
0x18007a825  xor     eax, ecx
0x18007a827  mov     ecx, eax
0x18007a829  xor     ecx, esi
0x18007a82b  and     ecx, 40h
0x18007a82e  xor     ecx, eax
0x18007a830  or      ecx, 1
0x18007a833  mov     eax, ecx
0x18007a835  xor     eax, esi
0x18007a837  and     eax, 800h
0x18007a83c  xor     eax, ecx
0x18007a83e  mov     [rbx], eax
0x18007a840  mov     rsi, [rsp+58h+arg_10]
0x18007a845  mov     rax, rbx
0x18007a848  add     rsp, 40h
0x18007a84c  pop     r13
0x18007a84e  pop     rdi
0x18007a84f  pop     rbx
0x18007a850  retn
0x18007a852  mov     r8, cs:qword_1800B9108; Source
0x18007a859  mov     rdx, r14; DestinationSize
0x18007a85c  mov     rdi, cs:Destination
0x18007a863  mov     rcx, rbp; Destination
0x18007a866  sub     rdi, r8
0x18007a869  mov     [rsp+58h+arg_18], r12
0x18007a86e  mov     r9, rdi; SourceSize
0x18007a871  call    cs:__imp_memcpy_s
0x18007a878  nop     dword ptr [rax+rax+00h]
0x18007a87d  mov     r12, cs:lpMem
0x18007a884  mov     cs:lpMem, rbp
0x18007a88b  test    r12, r12
0x18007a88e  jz      short loc_18007A8B0
0x18007a890  call    cs:__imp_GetProcessHeap
0x18007a897  nop     dword ptr [rax+rax+00h]
0x18007a89c  mov     r8, r12; lpMem
0x18007a89f  xor     edx, edx; dwFlags
0x18007a8a1  mov     rcx, rax; hHeap
0x18007a8a4  call    cs:__imp_HeapFree
0x18007a8ab  nop     dword ptr [rax+rax+00h]
0x18007a8b0  lea     rax, [rdi+rbp]
0x18007a8b4  mov     cs:qword_1800B9108, rbp
0x18007a8bb  mov     cs:Destination, rax
0x18007a8c2  mov     ecx, r15d; dwErrCode
0x18007a8c5  lea     rax, [r14+rbp]
0x18007a8c9  mov     cs:qword_1800B9118, rax
0x18007a8d0  call    cs:__imp_SetLastError
0x18007a8d7  nop     dword ptr [rax+rax+00h]
0x18007a8dc  mov     r8, cs:qword_1800B9118
0x18007a8e3  mov     r10, cs:Destination
0x18007a8ea  mov     r12, [rsp+58h+arg_18]
0x18007a8ef  mov     rax, r8
0x18007a8f2  mov     rdx, r13
0x18007a8f5  sub     rax, r10
0x18007a8f8  mov     r9d, 10h; SourceSize
0x18007a8fe  cmp     r10, r8
0x18007a901  mov     rcx, r10; Destination
0x18007a904  lea     r8, [rsp+58h+Source]; Source
0x18007a909  cmovb   rdx, rax; DestinationSize
0x18007a90d  call    cs:__imp_memcpy_s
0x18007a914  nop     dword ptr [rax+rax+00h]
0x18007a919  add     cs:Destination, 10h
0x18007a921  jmp     loc_18007A7F3
0x18007a926  mov     rax, rbx
0x18007a929  add     rsp, 40h
0x18007a92d  pop     r13
0x18007a92f  pop     rdi
0x18007a930  pop     rbx
0x18007a931  retn
```
