# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18007a940`
- end: `0x18007ad23`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `995`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18007b6b0`

## callees

- `0x18005ad2c`
- `0x18007a940`
- `0x180098010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18007ac61`
- `msvcrt!memcpy_s` at `0x18007acfd`
- `msvcrt!memcpy_s` at `0x18007ac61`
- `msvcrt!memcpy_s` at `0x18007acfd`
- `KERNEL32!HeapFree` at `0x18007ac94`
- `KERNEL32!HeapFree` at `0x18007ac94`
- `KERNEL32!SetLastError` at `0x18007abd3`
- `KERNEL32!SetLastError` at `0x18007acc0`
- `KERNEL32!SetLastError` at `0x18007abd3`
- `KERNEL32!SetLastError` at `0x18007acc0`
- `KERNEL32!GetLastError` at `0x18007aba7`
- `KERNEL32!GetLastError` at `0x18007aba7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007a9bd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007aa22`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007abea`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007a9bd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007aa22`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18007abea`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007a99a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007ab2f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007a99a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007ab2f`
- `KERNEL32!GetProcessHeap` at `0x18007ac80`
- `KERNEL32!GetProcessHeap` at `0x18007ac80`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
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
  v7 = v6(45036797, 3, &v30);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, v14, v13);
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
  Source[1] = Feature_Standalone_25_11_NonSec__descriptor;
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
  _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, 0xFFFFFFFB);
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
0x18007a940  mov     [rsp+arg_0], rcx
0x18007a945  push    rbx
0x18007a946  push    rdi
0x18007a947  push    r13
0x18007a949  sub     rsp, 40h
0x18007a94d  mov     rdi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18007a954  xor     r13d, r13d
0x18007a957  mov     [rdx], r13
0x18007a95a  mov     rbx, rdx
0x18007a95d  mov     eax, [rdi]
0x18007a95f  mov     [rdx], eax
0x18007a961  and     eax, 6
0x18007a964  cmp     al, 6
0x18007a966  jz      loc_18007AD16
0x18007a96c  mov     [rsp+58h+arg_8], rbp
0x18007a971  mov     ebp, cs:dword_1800B90D4
0x18007a977  nop
0x18007a978  mov     [rsp+58h+arg_10], rsi
0x18007a97d  test    ebp, ebp
0x18007a97f  jnz     loc_18007AA31
0x18007a985  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007a98b  test    eax, eax
0x18007a98d  jz      loc_18007AA2E
0x18007a993  lea     rcx, SRWLock; SRWLock
0x18007a99a  call    cs:__imp_AcquireSRWLockExclusive
0x18007a9a1  nop     dword ptr [rax+rax+00h]
0x18007a9a6  cmp     cs:qword_1800B90D8, r13
0x18007a9ad  jz      short loc_18007A9CB
0x18007a9af  mov     ebp, cs:dword_1800B90D4
0x18007a9b5  nop
0x18007a9b6  lea     rcx, SRWLock; SRWLock
0x18007a9bd  call    cs:__imp_ReleaseSRWLockExclusive
0x18007a9c4  nop     dword ptr [rax+rax+00h]
0x18007a9c9  jmp     short loc_18007AA31
0x18007a9cb  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x18007a9d2  mov     cs:qword_1800B90D8, r13
0x18007a9d9  test    rax, rax
0x18007a9dc  jnz     short loc_18007A9EA
0x18007a9de  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x18007a9e5  test    rax, rax
0x18007a9e8  jz      short loc_18007AA1B
0x18007a9ea  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007a9f1  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18007a9f8  lea     rcx, qword_1800B90D8
0x18007a9ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aa04  cmp     cs:qword_1800B90D8, r13
0x18007aa0b  jz      short loc_18007AA1B
0x18007aa0d  mov     ebp, 1
0x18007aa12  nop
0x18007aa13  mov     cs:dword_1800B90D4, ebp
0x18007aa19  jmp     short loc_18007A9B6
0x18007aa1b  lea     rcx, SRWLock; SRWLock
0x18007aa22  call    cs:__imp_ReleaseSRWLockExclusive
0x18007aa29  nop     dword ptr [rax+rax+00h]
0x18007aa2e  mov     ebp, r13d
0x18007aa31  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18007aa38  mov     dword ptr [rsp+58h+arg_0], r13d
0x18007aa3d  test    rax, rax
0x18007aa40  jnz     short loc_18007AA4E
0x18007aa42  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18007aa49  test    rax, rax
0x18007aa4c  jz      short loc_18007AAA4
0x18007aa4e  lea     r8, [rsp+58h+arg_0]
0x18007aa53  mov     edx, 3
0x18007aa58  mov     ecx, 2AF34FDh
0x18007aa5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aa62  mov     r8d, eax
0x18007aa65  mov     edx, eax
0x18007aa67  and     r8d, 0FFFFFF3Fh
0x18007aa6e  and     eax, 40h
0x18007aa71  and     edx, 80h
0x18007aa77  mov     ecx, r8d
0x18007aa7a  and     ecx, 3
0x18007aa7d  shl     ecx, 2
0x18007aa80  or      ecx, eax
0x18007aa82  shl     ecx, 2
0x18007aa85  or      ecx, edx
0x18007aa87  lea     esi, ds:0[rcx*8]
0x18007aa8e  test    r8d, r8d
0x18007aa91  jz      short loc_18007AAA7
0x18007aa93  cmp     r8d, 2
0x18007aa97  mov     eax, r13d
0x18007aa9a  mov     ecx, 40h ; '@'
0x18007aa9f  cmovz   eax, ecx
0x18007aaa2  jmp     short loc_18007AAAC
0x18007aaa4  mov     esi, r13d
0x18007aaa7  mov     eax, 40h ; '@'
0x18007aaac  or      esi, eax
0x18007aaae  mov     eax, [rbx]
0x18007aab0  mov     edx, eax
0x18007aab2  mov     [rbx], eax
0x18007aab4  cmp     dword ptr [rsp+58h+arg_0], r13d
0x18007aab9  jz      short loc_18007AAE5
0x18007aabb  test    dl, 2
0x18007aabe  jnz     short loc_18007AAE5
0x18007aac0  xor     eax, esi
0x18007aac2  and     eax, 180h
0x18007aac7  xor     eax, edx
0x18007aac9  mov     ecx, eax
0x18007aacb  xor     ecx, esi
0x18007aacd  and     ecx, 40h
0x18007aad0  xor     ecx, eax
0x18007aad2  or      ecx, 1
0x18007aad5  mov     eax, ecx
0x18007aad7  xor     eax, esi
0x18007aad9  and     eax, 800h
0x18007aade  xor     eax, ecx
0x18007aae0  or      eax, 2
0x18007aae3  mov     [rbx], eax
0x18007aae5  mov     r8d, edx
0x18007aae8  mov     ecx, eax
0x18007aaea  and     r8d, 4
0x18007aaee  jnz     short loc_18007AAFF
0x18007aaf0  xor     ecx, esi
0x18007aaf2  and     ecx, 400h
0x18007aaf8  xor     ecx, eax
0x18007aafa  or      ecx, 4
0x18007aafd  mov     [rbx], ecx
0x18007aaff  mov     eax, edx
0x18007ab01  lock cmpxchg [rdi], ecx
0x18007ab05  jnz     short loc_18007AAB0
0x18007ab07  test    r8d, r8d
0x18007ab0a  jnz     loc_18007AC00
0x18007ab10  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18007ab16  test    eax, eax
0x18007ab18  jz      loc_18007AC00
0x18007ab1e  mov     [rsp+58h+var_20], r14
0x18007ab23  lea     rcx, SRWLock; SRWLock
0x18007ab2a  mov     [rsp+58h+var_28], r15
0x18007ab2f  call    cs:__imp_AcquireSRWLockExclusive
0x18007ab36  nop     dword ptr [rax+rax+00h]
0x18007ab3b  mov     eax, cs:dword_1800B90D4
0x18007ab41  test    ebp, ebp
0x18007ab43  jz      loc_18007ABDF
0x18007ab49  cmp     ebp, eax
0x18007ab4b  jnz     loc_18007ABDF
0x18007ab51  mov     r10, cs:Destination
0x18007ab58  mov     r8, cs:qword_1800B9118
0x18007ab5f  mov     rax, r10
0x18007ab62  sub     rax, cs:qword_1800B9108
0x18007ab69  mov     rdx, r8
0x18007ab6c  sub     rdx, cs:qword_1800B9108
0x18007ab73  add     rax, 10h
0x18007ab77  mov     [rsp+58h+Source], 3
0x18007ab80  mov     [rsp+58h+var_30], rdi
0x18007ab85  cmp     rax, rdx
0x18007ab88  jb      loc_18007ACDF
0x18007ab8e  lea     rax, [rdx+rdx]
0x18007ab92  mov     ebp, 10h
0x18007ab97  cmp     rax, rbp
0x18007ab9a  cmova   rbp, rax
0x18007ab9e  cmp     rdx, rbp
0x18007aba1  jnb     loc_18007ACDF
0x18007aba7  call    cs:__imp_GetLastError
0x18007abae  nop     dword ptr [rax+rax+00h]
0x18007abb3  and     rbp, 0FFFFFFFFFFFFFFC0h
0x18007abb7  xor     ecx, ecx; dwFlags
0x18007abb9  mov     r15d, eax
0x18007abbc  lea     r14, [rbp+40h]
0x18007abc0  mov     rdx, r14; dwBytes
0x18007abc3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18007abc8  mov     rbp, rax
0x18007abcb  test    rax, rax
0x18007abce  jnz     short loc_18007AC42
0x18007abd0  mov     ecx, r15d; dwErrCode
0x18007abd3  call    cs:__imp_SetLastError
0x18007abda  nop     dword ptr [rax+rax+00h]
0x18007abdf  lock and dword ptr [rdi], 0FFFFFFFBh
0x18007abe3  lea     rcx, SRWLock; SRWLock
0x18007abea  call    cs:__imp_ReleaseSRWLockExclusive
0x18007abf1  nop     dword ptr [rax+rax+00h]
0x18007abf6  mov     r15, [rsp+58h+var_28]
0x18007abfb  mov     r14, [rsp+58h+var_20]
0x18007ac00  mov     ecx, [rbx]
0x18007ac02  mov     rbp, [rsp+58h+arg_8]
0x18007ac07  test    cl, 2
0x18007ac0a  jnz     short loc_18007AC30
0x18007ac0c  mov     eax, ecx
0x18007ac0e  xor     eax, esi
0x18007ac10  and     eax, 180h
0x18007ac15  xor     eax, ecx
0x18007ac17  mov     ecx, eax
0x18007ac19  xor     ecx, esi
0x18007ac1b  and     ecx, 40h
0x18007ac1e  xor     ecx, eax
0x18007ac20  or      ecx, 1
0x18007ac23  mov     eax, ecx
0x18007ac25  xor     eax, esi
0x18007ac27  and     eax, 800h
0x18007ac2c  xor     eax, ecx
0x18007ac2e  mov     [rbx], eax
0x18007ac30  mov     rsi, [rsp+58h+arg_10]
0x18007ac35  mov     rax, rbx
0x18007ac38  add     rsp, 40h
0x18007ac3c  pop     r13
0x18007ac3e  pop     rdi
0x18007ac3f  pop     rbx
0x18007ac40  retn
0x18007ac42  mov     r8, cs:qword_1800B9108; Source
0x18007ac49  mov     rdx, r14; DestinationSize
0x18007ac4c  mov     rdi, cs:Destination
0x18007ac53  mov     rcx, rbp; Destination
0x18007ac56  sub     rdi, r8
0x18007ac59  mov     [rsp+58h+arg_18], r12
0x18007ac5e  mov     r9, rdi; SourceSize
0x18007ac61  call    cs:__imp_memcpy_s
0x18007ac68  nop     dword ptr [rax+rax+00h]
0x18007ac6d  mov     r12, cs:lpMem
0x18007ac74  mov     cs:lpMem, rbp
0x18007ac7b  test    r12, r12
0x18007ac7e  jz      short loc_18007ACA0
0x18007ac80  call    cs:__imp_GetProcessHeap
0x18007ac87  nop     dword ptr [rax+rax+00h]
0x18007ac8c  mov     r8, r12; lpMem
0x18007ac8f  xor     edx, edx; dwFlags
0x18007ac91  mov     rcx, rax; hHeap
0x18007ac94  call    cs:__imp_HeapFree
0x18007ac9b  nop     dword ptr [rax+rax+00h]
0x18007aca0  lea     rax, [rdi+rbp]
0x18007aca4  mov     cs:qword_1800B9108, rbp
0x18007acab  mov     cs:Destination, rax
0x18007acb2  mov     ecx, r15d; dwErrCode
0x18007acb5  lea     rax, [r14+rbp]
0x18007acb9  mov     cs:qword_1800B9118, rax
0x18007acc0  call    cs:__imp_SetLastError
0x18007acc7  nop     dword ptr [rax+rax+00h]
0x18007accc  mov     r8, cs:qword_1800B9118
0x18007acd3  mov     r10, cs:Destination
0x18007acda  mov     r12, [rsp+58h+arg_18]
0x18007acdf  mov     rax, r8
0x18007ace2  mov     rdx, r13
0x18007ace5  sub     rax, r10
0x18007ace8  mov     r9d, 10h; SourceSize
0x18007acee  cmp     r10, r8
0x18007acf1  mov     rcx, r10; Destination
0x18007acf4  lea     r8, [rsp+58h+Source]; Source
0x18007acf9  cmovb   rdx, rax; DestinationSize
0x18007acfd  call    cs:__imp_memcpy_s
0x18007ad04  nop     dword ptr [rax+rax+00h]
0x18007ad09  add     cs:Destination, 10h
0x18007ad11  jmp     loc_18007ABE3
0x18007ad16  mov     rax, rbx
0x18007ad19  add     rsp, 40h
0x18007ad1d  pop     r13
0x18007ad1f  pop     rdi
0x18007ad20  pop     rbx
0x18007ad21  retn
```
