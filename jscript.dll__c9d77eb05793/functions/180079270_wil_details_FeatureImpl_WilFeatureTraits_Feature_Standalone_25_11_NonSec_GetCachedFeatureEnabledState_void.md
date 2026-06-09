# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180079270`
- end: `0x180079616`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `934`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180079f00`

## callees

- `0x180059cd4`
- `0x180079270`
- `0x180096010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180079573`
- `msvcrt!memcpy_s` at `0x1800795f7`
- `msvcrt!memcpy_s` at `0x180079573`
- `msvcrt!memcpy_s` at `0x1800795f7`
- `KERNEL32!HeapFree` at `0x18007959a`
- `KERNEL32!HeapFree` at `0x18007959a`
- `KERNEL32!SetLastError` at `0x1800794f2`
- `KERNEL32!SetLastError` at `0x1800795c0`
- `KERNEL32!SetLastError` at `0x1800794f2`
- `KERNEL32!SetLastError` at `0x1800795c0`
- `KERNEL32!GetLastError` at `0x1800794cc`
- `KERNEL32!GetLastError` at `0x1800794cc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800792e7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180079344`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180079353`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180079503`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800792e7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180079344`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180079353`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180079503`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800792ca`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007945a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800792ca`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18007945a`
- `KERNEL32!GetProcessHeap` at `0x18007958c`
- `KERNEL32!GetProcessHeap` at `0x18007958c`

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
  v7 = v6(45036797, 3, &v30);
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
    v12 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, v14, v13);
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
  Source[1] = Feature_Standalone_25_11_NonSec__descriptor;
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
  _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, 0xFFFFFFFB);
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
0x180079270  mov     [rsp+arg_0], rcx
0x180079275  push    rbx
0x180079276  push    rdi
0x180079277  push    r13
0x180079279  sub     rsp, 40h
0x18007927d  mov     rdi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x180079284  xor     r13d, r13d
0x180079287  mov     [rdx], r13
0x18007928a  mov     rbx, rdx
0x18007928d  mov     eax, [rdi]
0x18007928f  mov     [rdx], eax
0x180079291  and     eax, 6
0x180079294  cmp     al, 6
0x180079296  jz      loc_18007960A
0x18007929c  mov     [rsp+58h+arg_8], rbp
0x1800792a1  mov     ebp, cs:dword_1800B70DC
0x1800792a7  nop
0x1800792a8  mov     [rsp+58h+arg_10], rsi
0x1800792ad  test    ebp, ebp
0x1800792af  jnz     loc_18007935C
0x1800792b5  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800792bb  test    eax, eax
0x1800792bd  jz      loc_180079359
0x1800792c3  lea     rcx, SRWLock; SRWLock
0x1800792ca  call    cs:__imp_AcquireSRWLockExclusive
0x1800792d0  cmp     cs:qword_1800B7120, r13
0x1800792d7  jz      short loc_1800792EF
0x1800792d9  mov     ebp, cs:dword_1800B70DC
0x1800792df  lea     rcx, SRWLock; SRWLock
0x1800792e6  nop
0x1800792e7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800792ed  jmp     short loc_18007935C
0x1800792ef  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1800792f6  mov     cs:qword_1800B7120, r13
0x1800792fd  test    rax, rax
0x180079300  jnz     short loc_18007930E
0x180079302  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180079309  test    rax, rax
0x18007930c  jz      short loc_18007934C
0x18007930e  lea     r8, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180079315  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x18007931c  lea     rcx, qword_1800B7120
0x180079323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079328  cmp     cs:qword_1800B7120, r13
0x18007932f  jz      short loc_18007934C
0x180079331  nop
0x180079332  lea     rcx, SRWLock; SRWLock
0x180079339  mov     ebp, 1
0x18007933e  mov     cs:dword_1800B70DC, ebp
0x180079344  call    cs:__imp_ReleaseSRWLockExclusive
0x18007934a  jmp     short loc_18007935C
0x18007934c  lea     rcx, SRWLock; SRWLock
0x180079353  call    cs:__imp_ReleaseSRWLockExclusive
0x180079359  mov     ebp, r13d
0x18007935c  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180079363  mov     dword ptr [rsp+58h+arg_0], r13d
0x180079368  test    rax, rax
0x18007936b  jnz     short loc_180079379
0x18007936d  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x180079374  test    rax, rax
0x180079377  jz      short loc_1800793CF
0x180079379  lea     r8, [rsp+58h+arg_0]
0x18007937e  mov     edx, 3
0x180079383  mov     ecx, 2AF34FDh
0x180079388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007938d  mov     r8d, eax
0x180079390  mov     edx, eax
0x180079392  and     r8d, 0FFFFFF3Fh
0x180079399  and     eax, 40h
0x18007939c  and     edx, 80h
0x1800793a2  mov     ecx, r8d
0x1800793a5  and     ecx, 3
0x1800793a8  shl     ecx, 2
0x1800793ab  or      ecx, eax
0x1800793ad  shl     ecx, 2
0x1800793b0  or      ecx, edx
0x1800793b2  lea     esi, ds:0[rcx*8]
0x1800793b9  test    r8d, r8d
0x1800793bc  jz      short loc_1800793D2
0x1800793be  cmp     r8d, 2
0x1800793c2  mov     eax, r13d
0x1800793c5  mov     ecx, 40h ; '@'
0x1800793ca  cmovz   eax, ecx
0x1800793cd  jmp     short loc_1800793D7
0x1800793cf  mov     esi, r13d
0x1800793d2  mov     eax, 40h ; '@'
0x1800793d7  or      esi, eax
0x1800793d9  mov     eax, [rbx]
0x1800793db  mov     edx, eax
0x1800793dd  mov     [rbx], eax
0x1800793df  cmp     dword ptr [rsp+58h+arg_0], r13d
0x1800793e4  jz      short loc_180079410
0x1800793e6  test    dl, 2
0x1800793e9  jnz     short loc_180079410
0x1800793eb  xor     eax, esi
0x1800793ed  and     eax, 180h
0x1800793f2  xor     eax, edx
0x1800793f4  mov     ecx, eax
0x1800793f6  xor     ecx, esi
0x1800793f8  and     ecx, 40h
0x1800793fb  xor     ecx, eax
0x1800793fd  or      ecx, 1
0x180079400  mov     eax, ecx
0x180079402  xor     eax, esi
0x180079404  and     eax, 800h
0x180079409  xor     eax, ecx
0x18007940b  or      eax, 2
0x18007940e  mov     [rbx], eax
0x180079410  mov     r8d, edx
0x180079413  mov     ecx, eax
0x180079415  and     r8d, 4
0x180079419  jnz     short loc_18007942A
0x18007941b  xor     ecx, esi
0x18007941d  and     ecx, 400h
0x180079423  xor     ecx, eax
0x180079425  or      ecx, 4
0x180079428  mov     [rbx], ecx
0x18007942a  mov     eax, edx
0x18007942c  lock cmpxchg [rdi], ecx
0x180079430  jnz     short loc_1800793DB
0x180079432  test    r8d, r8d
0x180079435  jnz     loc_180079513
0x18007943b  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180079441  test    eax, eax
0x180079443  jz      loc_180079513
0x180079449  mov     [rsp+58h+var_20], r14
0x18007944e  lea     rcx, SRWLock; SRWLock
0x180079455  mov     [rsp+58h+var_28], r15
0x18007945a  call    cs:__imp_AcquireSRWLockExclusive
0x180079460  mov     eax, cs:dword_1800B70DC
0x180079466  test    ebp, ebp
0x180079468  jz      loc_1800794F8
0x18007946e  cmp     ebp, eax
0x180079470  jnz     loc_1800794F8
0x180079476  mov     r10, cs:Destination
0x18007947d  mov     r8, cs:qword_1800B7110
0x180079484  mov     rax, r10
0x180079487  sub     rax, cs:qword_1800B7100
0x18007948e  mov     rdx, r8
0x180079491  sub     rdx, cs:qword_1800B7100
0x180079498  add     rax, 10h
0x18007949c  mov     [rsp+58h+Source], 3
0x1800794a5  mov     [rsp+58h+var_30], rdi
0x1800794aa  cmp     rax, rdx
0x1800794ad  jb      loc_1800795D9
0x1800794b3  lea     rax, [rdx+rdx]
0x1800794b7  mov     ebp, 10h
0x1800794bc  cmp     rax, rbp
0x1800794bf  cmova   rbp, rax
0x1800794c3  cmp     rdx, rbp
0x1800794c6  jnb     loc_1800795D9
0x1800794cc  call    cs:__imp_GetLastError
0x1800794d2  and     rbp, 0FFFFFFFFFFFFFFC0h
0x1800794d6  xor     ecx, ecx; dwFlags
0x1800794d8  mov     r15d, eax
0x1800794db  lea     r14, [rbp+40h]
0x1800794df  mov     rdx, r14; dwBytes
0x1800794e2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800794e7  mov     rbp, rax
0x1800794ea  test    rax, rax
0x1800794ed  jnz     short loc_180079554
0x1800794ef  mov     ecx, r15d; dwErrCode
0x1800794f2  call    cs:__imp_SetLastError
0x1800794f8  lock and dword ptr [rdi], 0FFFFFFFBh
0x1800794fc  lea     rcx, SRWLock; SRWLock
0x180079503  call    cs:__imp_ReleaseSRWLockExclusive
0x180079509  mov     r15, [rsp+58h+var_28]
0x18007950e  mov     r14, [rsp+58h+var_20]
0x180079513  mov     ecx, [rbx]
0x180079515  mov     rbp, [rsp+58h+arg_8]
0x18007951a  test    cl, 2
0x18007951d  jnz     short loc_180079543
0x18007951f  mov     eax, ecx
0x180079521  xor     eax, esi
0x180079523  and     eax, 180h
0x180079528  xor     eax, ecx
0x18007952a  mov     ecx, eax
0x18007952c  xor     ecx, esi
0x18007952e  and     ecx, 40h
0x180079531  xor     ecx, eax
0x180079533  or      ecx, 1
0x180079536  mov     eax, ecx
0x180079538  xor     eax, esi
0x18007953a  and     eax, 800h
0x18007953f  xor     eax, ecx
0x180079541  mov     [rbx], eax
0x180079543  mov     rsi, [rsp+58h+arg_10]
0x180079548  mov     rax, rbx
0x18007954b  add     rsp, 40h
0x18007954f  pop     r13
0x180079551  pop     rdi
0x180079552  pop     rbx
0x180079553  retn
0x180079554  mov     r8, cs:qword_1800B7100; Source
0x18007955b  mov     rdx, r14; DestinationSize
0x18007955e  mov     rdi, cs:Destination
0x180079565  mov     rcx, rbp; Destination
0x180079568  sub     rdi, r8
0x18007956b  mov     [rsp+58h+arg_18], r12
0x180079570  mov     r9, rdi; SourceSize
0x180079573  call    cs:__imp_memcpy_s
0x180079579  mov     r12, cs:lpMem
0x180079580  mov     cs:lpMem, rbp
0x180079587  test    r12, r12
0x18007958a  jz      short loc_1800795A0
0x18007958c  call    cs:__imp_GetProcessHeap
0x180079592  mov     r8, r12; lpMem
0x180079595  xor     edx, edx; dwFlags
0x180079597  mov     rcx, rax; hHeap
0x18007959a  call    cs:__imp_HeapFree
0x1800795a0  lea     rax, [rdi+rbp]
0x1800795a4  mov     cs:qword_1800B7100, rbp
0x1800795ab  mov     cs:Destination, rax
0x1800795b2  mov     ecx, r15d; dwErrCode
0x1800795b5  lea     rax, [r14+rbp]
0x1800795b9  mov     cs:qword_1800B7110, rax
0x1800795c0  call    cs:__imp_SetLastError
0x1800795c6  mov     r8, cs:qword_1800B7110
0x1800795cd  mov     r10, cs:Destination
0x1800795d4  mov     r12, [rsp+58h+arg_18]
0x1800795d9  mov     rax, r8
0x1800795dc  mov     rdx, r13
0x1800795df  sub     rax, r10
0x1800795e2  mov     r9d, 10h; SourceSize
0x1800795e8  cmp     r10, r8
0x1800795eb  mov     rcx, r10; Destination
0x1800795ee  lea     r8, [rsp+58h+Source]; Source
0x1800795f3  cmovb   rdx, rax; DestinationSize
0x1800795f7  call    cs:__imp_memcpy_s
0x1800795fd  add     cs:Destination, 10h
0x180079605  jmp     loc_1800794FC
0x18007960a  mov     rax, rbx
0x18007960d  add     rsp, 40h
0x180079611  pop     r13
0x180079613  pop     rdi
0x180079614  pop     rbx
0x180079615  retn
```
