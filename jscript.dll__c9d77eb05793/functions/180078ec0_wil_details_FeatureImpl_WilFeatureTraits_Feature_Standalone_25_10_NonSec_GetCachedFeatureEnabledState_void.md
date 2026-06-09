# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180078ec0`
- end: `0x180079266`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `934`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18007a020`

## callees

- `0x180059cd4`
- `0x180078ec0`
- `0x180096010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800791c3`
- `msvcrt!memcpy_s` at `0x180079247`
- `msvcrt!memcpy_s` at `0x1800791c3`
- `msvcrt!memcpy_s` at `0x180079247`
- `KERNEL32!HeapFree` at `0x1800791ea`
- `KERNEL32!HeapFree` at `0x1800791ea`
- `KERNEL32!SetLastError` at `0x180079142`
- `KERNEL32!SetLastError` at `0x180079210`
- `KERNEL32!SetLastError` at `0x180079142`
- `KERNEL32!SetLastError` at `0x180079210`
- `KERNEL32!GetLastError` at `0x18007911c`
- `KERNEL32!GetLastError` at `0x18007911c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180078f37`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180078f94`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180078fa3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180079153`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180078f37`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180078f94`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180078fa3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180079153`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180078f1a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800790aa`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180078f1a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800790aa`
- `KERNEL32!GetProcessHeap` at `0x1800791dc`
- `KERNEL32!GetProcessHeap` at `0x1800791dc`

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
  v6 = (__int64 (__fastcall *)(__int64, __int64, __int64 *))g_wil_details_internalGetFeatureEnabledState;
  LODWORD(v30) = 0;
  if ( !g_wil_details_internalGetFeatureEnabledState )
  {
    v6 = (__int64 (__fastcall *)(__int64, __int64, __int64 *))g_wil_details_apiGetFeatureEnabledState;
    if ( !g_wil_details_apiGetFeatureEnabledState )
    {
      v9 = 0;
      goto LABEL_19;
    }
  }
  v7 = v6(45036792, 3, &v30);
  v8 = v7 & 0xFFFFFF3F;
  v9 = 8 * (v7 & 0x80 | (4 * (v7 & 0x40 | (4 * (v7 & 3)))));
  if ( (v7 & 0xFFFFFF3F) == 0 )
  {
LABEL_19:
    v10 = 64;
    goto LABEL_20;
  }
  v10 = 0;
  if ( v8 == 2 )
    v10 = 64;
LABEL_20:
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
    goto LABEL_39;
  AcquireSRWLockExclusive(&SRWLock);
  if ( !v4 || v4 != dword_1800B70DC )
    goto LABEL_37;
  v15 = Destination;
  v16 = qword_1800B7110;
  v17 = qword_1800B7110 - qword_1800B7100;
  Source[0] = 3;
  Source[1] = Feature_Standalone_25_10_NonSec__descriptor;
  if ( (unsigned __int64)Destination - qword_1800B7100 + 16 < qword_1800B7110 - qword_1800B7100 )
    goto LABEL_45;
  v18 = 16;
  if ( 2 * v17 > 0x10 )
    v18 = 2 * v17;
  if ( v17 >= v18 )
  {
LABEL_45:
    v28 = 0;
    if ( (unsigned __int64)v15 < v16 )
      v28 = v16 - (_QWORD)v15;
    memcpy_s(v15, v28, Source, 0x10u);
    Destination = (char *)Destination + 16;
    goto LABEL_38;
  }
  LastError = GetLastError();
  v20 = (v18 & 0xFFFFFFFFFFFFFFC0uLL) + 64;
  v21 = (char *)wil::details::ProcessHeapAlloc(0, v20);
  v22 = v21;
  if ( v21 )
  {
    v25 = (char *)Destination - qword_1800B7100;
    memcpy_s(v21, v20, qword_1800B7100, (rsize_t)Destination - qword_1800B7100);
    v26 = lpMem;
    lpMem = v22;
    if ( v26 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v26);
    }
    qword_1800B7100 = v22;
    Destination = &v22[(_QWORD)v25];
    qword_1800B7110 = (__int64)&v22[v20];
    SetLastError(LastError);
    v16 = qword_1800B7110;
    v15 = Destination;
    goto LABEL_45;
  }
  SetLastError(LastError);
LABEL_37:
  _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, 0xFFFFFFFB);
LABEL_38:
  ReleaseSRWLockExclusive(&SRWLock);
LABEL_39:
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
0x180078ec0  mov     [rsp+arg_0], rcx
0x180078ec5  push    rbx
0x180078ec6  push    rdi
0x180078ec7  push    r13
0x180078ec9  sub     rsp, 40h
0x180078ecd  mov     rdi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180078ed4  xor     r13d, r13d
0x180078ed7  mov     [rdx], r13
0x180078eda  mov     rbx, rdx
0x180078edd  mov     eax, [rdi]
0x180078edf  mov     [rdx], eax
0x180078ee1  and     eax, 6
0x180078ee4  cmp     al, 6
0x180078ee6  jz      loc_18007925A
0x180078eec  mov     [rsp+58h+arg_8], rbp
0x180078ef1  mov     ebp, cs:dword_1800B70DC
0x180078ef7  nop
0x180078ef8  mov     [rsp+58h+arg_10], rsi
0x180078efd  test    ebp, ebp
0x180078eff  jnz     loc_180078FAC
0x180078f05  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180078f0b  test    eax, eax
0x180078f0d  jz      loc_180078FA9
0x180078f13  lea     rcx, SRWLock; SRWLock
0x180078f1a  call    cs:__imp_AcquireSRWLockExclusive
0x180078f20  cmp     cs:qword_1800B7120, r13
0x180078f27  jz      short loc_180078F3F
0x180078f29  mov     ebp, cs:dword_1800B70DC
0x180078f2f  lea     rcx, SRWLock; SRWLock
0x180078f36  nop
0x180078f37  call    cs:__imp_ReleaseSRWLockExclusive
0x180078f3d  jmp     short loc_180078FAC
0x180078f3f  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180078f46  mov     cs:qword_1800B7120, r13
0x180078f4d  test    rax, rax
0x180078f50  jnz     short loc_180078F5E
0x180078f52  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180078f59  test    rax, rax
0x180078f5c  jz      short loc_180078F9C
0x180078f5e  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180078f65  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180078f6c  lea     rcx, qword_1800B7120
0x180078f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078f78  cmp     cs:qword_1800B7120, r13
0x180078f7f  jz      short loc_180078F9C
0x180078f81  nop
0x180078f82  lea     rcx, SRWLock; SRWLock
0x180078f89  mov     ebp, 1
0x180078f8e  mov     cs:dword_1800B70DC, ebp
0x180078f94  call    cs:__imp_ReleaseSRWLockExclusive
0x180078f9a  jmp     short loc_180078FAC
0x180078f9c  lea     rcx, SRWLock; SRWLock
0x180078fa3  call    cs:__imp_ReleaseSRWLockExclusive
0x180078fa9  mov     ebp, r13d
0x180078fac  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180078fb3  mov     dword ptr [rsp+58h+arg_0], r13d
0x180078fb8  test    rax, rax
0x180078fbb  jnz     short loc_180078FC9
0x180078fbd  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180078fc4  test    rax, rax
0x180078fc7  jz      short loc_18007901F
0x180078fc9  lea     r8, [rsp+58h+arg_0]
0x180078fce  mov     edx, 3
0x180078fd3  mov     ecx, 2AF34F8h
0x180078fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078fdd  mov     r8d, eax
0x180078fe0  mov     edx, eax
0x180078fe2  and     r8d, 0FFFFFF3Fh
0x180078fe9  and     eax, 40h
0x180078fec  and     edx, 80h
0x180078ff2  mov     ecx, r8d
0x180078ff5  and     ecx, 3
0x180078ff8  shl     ecx, 2
0x180078ffb  or      ecx, eax
0x180078ffd  shl     ecx, 2
0x180079000  or      ecx, edx
0x180079002  lea     esi, ds:0[rcx*8]
0x180079009  test    r8d, r8d
0x18007900c  jz      short loc_180079022
0x18007900e  cmp     r8d, 2
0x180079012  mov     eax, r13d
0x180079015  mov     ecx, 40h ; '@'
0x18007901a  cmovz   eax, ecx
0x18007901d  jmp     short loc_180079027
0x18007901f  mov     esi, r13d
0x180079022  mov     eax, 40h ; '@'
0x180079027  or      esi, eax
0x180079029  mov     eax, [rbx]
0x18007902b  mov     edx, eax
0x18007902d  mov     [rbx], eax
0x18007902f  cmp     dword ptr [rsp+58h+arg_0], r13d
0x180079034  jz      short loc_180079060
0x180079036  test    dl, 2
0x180079039  jnz     short loc_180079060
0x18007903b  xor     eax, esi
0x18007903d  and     eax, 180h
0x180079042  xor     eax, edx
0x180079044  mov     ecx, eax
0x180079046  xor     ecx, esi
0x180079048  and     ecx, 40h
0x18007904b  xor     ecx, eax
0x18007904d  or      ecx, 1
0x180079050  mov     eax, ecx
0x180079052  xor     eax, esi
0x180079054  and     eax, 800h
0x180079059  xor     eax, ecx
0x18007905b  or      eax, 2
0x18007905e  mov     [rbx], eax
0x180079060  mov     r8d, edx
0x180079063  mov     ecx, eax
0x180079065  and     r8d, 4
0x180079069  jnz     short loc_18007907A
0x18007906b  xor     ecx, esi
0x18007906d  and     ecx, 400h
0x180079073  xor     ecx, eax
0x180079075  or      ecx, 4
0x180079078  mov     [rbx], ecx
0x18007907a  mov     eax, edx
0x18007907c  lock cmpxchg [rdi], ecx
0x180079080  jnz     short loc_18007902B
0x180079082  test    r8d, r8d
0x180079085  jnz     loc_180079163
0x18007908b  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180079091  test    eax, eax
0x180079093  jz      loc_180079163
0x180079099  mov     [rsp+58h+var_20], r14
0x18007909e  lea     rcx, SRWLock; SRWLock
0x1800790a5  mov     [rsp+58h+var_28], r15
0x1800790aa  call    cs:__imp_AcquireSRWLockExclusive
0x1800790b0  mov     eax, cs:dword_1800B70DC
0x1800790b6  test    ebp, ebp
0x1800790b8  jz      loc_180079148
0x1800790be  cmp     ebp, eax
0x1800790c0  jnz     loc_180079148
0x1800790c6  mov     r10, cs:Destination
0x1800790cd  mov     r8, cs:qword_1800B7110
0x1800790d4  mov     rax, r10
0x1800790d7  sub     rax, cs:qword_1800B7100
0x1800790de  mov     rdx, r8
0x1800790e1  sub     rdx, cs:qword_1800B7100
0x1800790e8  add     rax, 10h
0x1800790ec  mov     [rsp+58h+Source], 3
0x1800790f5  mov     [rsp+58h+var_30], rdi
0x1800790fa  cmp     rax, rdx
0x1800790fd  jb      loc_180079229
0x180079103  lea     rax, [rdx+rdx]
0x180079107  mov     ebp, 10h
0x18007910c  cmp     rax, rbp
0x18007910f  cmova   rbp, rax
0x180079113  cmp     rdx, rbp
0x180079116  jnb     loc_180079229
0x18007911c  call    cs:__imp_GetLastError
0x180079122  and     rbp, 0FFFFFFFFFFFFFFC0h
0x180079126  xor     ecx, ecx; dwFlags
0x180079128  mov     r15d, eax
0x18007912b  lea     r14, [rbp+40h]
0x18007912f  mov     rdx, r14; dwBytes
0x180079132  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180079137  mov     rbp, rax
0x18007913a  test    rax, rax
0x18007913d  jnz     short loc_1800791A4
0x18007913f  mov     ecx, r15d; dwErrCode
0x180079142  call    cs:__imp_SetLastError
0x180079148  lock and dword ptr [rdi], 0FFFFFFFBh
0x18007914c  lea     rcx, SRWLock; SRWLock
0x180079153  call    cs:__imp_ReleaseSRWLockExclusive
0x180079159  mov     r15, [rsp+58h+var_28]
0x18007915e  mov     r14, [rsp+58h+var_20]
0x180079163  mov     ecx, [rbx]
0x180079165  mov     rbp, [rsp+58h+arg_8]
0x18007916a  test    cl, 2
0x18007916d  jnz     short loc_180079193
0x18007916f  mov     eax, ecx
0x180079171  xor     eax, esi
0x180079173  and     eax, 180h
0x180079178  xor     eax, ecx
0x18007917a  mov     ecx, eax
0x18007917c  xor     ecx, esi
0x18007917e  and     ecx, 40h
0x180079181  xor     ecx, eax
0x180079183  or      ecx, 1
0x180079186  mov     eax, ecx
0x180079188  xor     eax, esi
0x18007918a  and     eax, 800h
0x18007918f  xor     eax, ecx
0x180079191  mov     [rbx], eax
0x180079193  mov     rsi, [rsp+58h+arg_10]
0x180079198  mov     rax, rbx
0x18007919b  add     rsp, 40h
0x18007919f  pop     r13
0x1800791a1  pop     rdi
0x1800791a2  pop     rbx
0x1800791a3  retn
0x1800791a4  mov     r8, cs:qword_1800B7100; Source
0x1800791ab  mov     rdx, r14; DestinationSize
0x1800791ae  mov     rdi, cs:Destination
0x1800791b5  mov     rcx, rbp; Destination
0x1800791b8  sub     rdi, r8
0x1800791bb  mov     [rsp+58h+arg_18], r12
0x1800791c0  mov     r9, rdi; SourceSize
0x1800791c3  call    cs:__imp_memcpy_s
0x1800791c9  mov     r12, cs:lpMem
0x1800791d0  mov     cs:lpMem, rbp
0x1800791d7  test    r12, r12
0x1800791da  jz      short loc_1800791F0
0x1800791dc  call    cs:__imp_GetProcessHeap
0x1800791e2  mov     r8, r12; lpMem
0x1800791e5  xor     edx, edx; dwFlags
0x1800791e7  mov     rcx, rax; hHeap
0x1800791ea  call    cs:__imp_HeapFree
0x1800791f0  lea     rax, [rdi+rbp]
0x1800791f4  mov     cs:qword_1800B7100, rbp
0x1800791fb  mov     cs:Destination, rax
0x180079202  mov     ecx, r15d; dwErrCode
0x180079205  lea     rax, [r14+rbp]
0x180079209  mov     cs:qword_1800B7110, rax
0x180079210  call    cs:__imp_SetLastError
0x180079216  mov     r8, cs:qword_1800B7110
0x18007921d  mov     r10, cs:Destination
0x180079224  mov     r12, [rsp+58h+arg_18]
0x180079229  mov     rax, r8
0x18007922c  mov     rdx, r13
0x18007922f  sub     rax, r10
0x180079232  mov     r9d, 10h; SourceSize
0x180079238  cmp     r10, r8
0x18007923b  mov     rcx, r10; Destination
0x18007923e  lea     r8, [rsp+58h+Source]; Source
0x180079243  cmovb   rdx, rax; DestinationSize
0x180079247  call    cs:__imp_memcpy_s
0x18007924d  add     cs:Destination, 10h
0x180079255  jmp     loc_18007914C
0x18007925a  mov     rax, rbx
0x18007925d  add     rsp, 40h
0x180079261  pop     r13
0x180079263  pop     rdi
0x180079264  pop     rbx
0x180079265  retn
```
