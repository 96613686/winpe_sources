# wil::details::FeatureImpl<__WilFeatureTraits_Feature_RequestFromAppModelWatcher>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x180003760`
- end: `0x180003c88`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RequestFromAppModelWatcher@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `1320`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800035b0`

## callees

- `0x180002cf0`
- `0x180002d90`
- `0x180003760`
- `0x180004900`
- `0x180004950`
- `0x180004980`
- `0x180004a10`
- `0x18000d2a0`
- `0x180030c8c`
- `0x180033de8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003ab7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003b9a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003ab7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003b9a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003b66`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003bd2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003b66`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003bd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b3d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180003b26`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180003b26`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_RequestFromAppModelWatcher>::ReportUsage(
        __int64 a1,
        unsigned __int8 a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v4; // r14d
  signed __int32 v6; // ebx
  signed __int32 v7; // edi
  unsigned int v8; // r10d
  __int64 (__fastcall *v9)(__int64, __int64, int *); // rax
  int v10; // eax
  unsigned int v11; // edx
  __int16 v12; // ax
  __int16 v13; // r9
  __int16 v14; // si
  unsigned __int16 v15; // si
  int v16; // edx
  bool v17; // zf
  signed __int32 v18; // eax
  volatile signed __int32 *v19; // r15
  unsigned int v20; // r13d
  unsigned int v21; // edi
  int v22; // edx
  signed __int32 i; // ecx
  BOOL v24; // esi
  signed __int32 v25; // eax
  unsigned __int64 v26; // rcx
  unsigned int v27; // r9d
  unsigned int v28; // r14d
  signed __int32 v29; // eax
  signed __int32 v30; // ett
  signed __int32 v31; // ecx
  unsigned int v32; // eax
  unsigned int v33; // edx
  unsigned int v34; // r8d
  signed __int32 v35; // eax
  wil *v36; // rcx
  DWORD LastError; // edi
  struct _TP_TIMER *ThreadpoolTimer; // rax
  void *v39; // r9
  unsigned int v40; // edx
  const char *v41; // [rsp+20h] [rbp-58h]
  int v42; // [rsp+50h] [rbp-28h] BYREF
  __int16 v43; // [rsp+54h] [rbp-24h]
  unsigned int v44[4]; // [rsp+58h] [rbp-20h] BYREF
  _BOOL8 v45; // [rsp+68h] [rbp-10h]
  int v46; // [rsp+C0h] [rbp+48h] BYREF
  int v47; // [rsp+C8h] [rbp+50h] BYREF
  unsigned int v48; // [rsp+D0h] [rbp+58h]
  __int64 v49; // [rsp+D8h] [rbp+60h]

  v49 = a4;
  LOBYTE(v48) = a3;
  v4 = a2;
  v6 = *(_DWORD *)Feature_RequestFromAppModelWatcher__descriptor;
  if ( (*(_DWORD *)Feature_RequestFromAppModelWatcher__descriptor & 4) != 0 )
    goto LABEL_28;
  v7 = *(_DWORD *)Feature_RequestFromAppModelWatcher__descriptor;
  if ( (*(_BYTE *)Feature_RequestFromAppModelWatcher__descriptor & 6) == 6 )
  {
    LOWORD(v6) = *(_DWORD *)Feature_RequestFromAppModelWatcher__descriptor;
    goto LABEL_28;
  }
  v8 = dword_1800ACD84;
  v48 = dword_1800ACD84;
  if ( !dword_1800ACD84 )
  {
    v8 = wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
    v48 = v8;
  }
  v47 = 0;
  v9 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v9 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v10 = v9(20819441, 3, &v47);
    a3 = (unsigned __int8)v10 & 0x80;
    v11 = v10 & 0xFFFFFF3F;
    v12 = 32 * (v10 & 0x40 | (4 * (v10 & 3)));
    v8 = v48;
    if ( v11 )
    {
      v13 = 0;
      if ( v11 == 2 )
        v13 = 64;
      goto LABEL_13;
    }
  }
  else
  {
    a3 = 0;
    v12 = 0;
  }
  v13 = 64;
LABEL_13:
  v14 = 1;
  if ( (_DWORD)a3 )
    v14 = 1025;
  v15 = v13 | v12 | v14;
  do
  {
    if ( !v47 || (v7 & 2) != 0 )
      v6 = v7;
    else
      v6 = v7 ^ ((unsigned __int16)v7 ^ v15) & 0x9C1 | 2;
    v16 = v7 & 4;
    if ( (v7 & 4) == 0 )
      v6 = ((unsigned __int16)v6 ^ v15) & 0x400 ^ v6 | 4;
    v18 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_RequestFromAppModelWatcher__descriptor, v6, v7);
    v17 = v7 == v18;
    v7 = v18;
  }
  while ( !v17 );
  if ( !v16 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
      Feature_RequestFromAppModelWatcher__descriptor,
      3,
      v8);
  if ( (v6 & 2) == 0 )
    LOWORD(v6) = (v6 ^ v15) & 0x9C1 ^ v6;
LABEL_28:
  v42 = 0;
  v43 = 3;
  v46 = 3;
  v19 = (volatile signed __int32 *)(a1 + 8);
  v20 = v4;
  v21 = 4 * (v4 ^ 1) + 2;
  LODWORD(v49) = v21;
  *(_OWORD *)v44 = 0;
  v45 = 0;
  switch ( 4 * (v4 ^ 1) )
  {
    case 0xFFFFFFFE:
      v31 = *v19;
      v27 = v44[2];
      while ( 1 )
      {
        v28 = 0;
        v32 = v31 | 1;
        if ( (v31 & 0x4000) != 0 )
        {
          if ( ((v32 >> 5) & 0x1FF) != 0 )
          {
            v27 = 0;
            v28 = (v32 >> 5) & 0x1FF;
            v32 = v31 & 0xFFFFC01E | 1;
          }
          v32 &= ~0x4000u;
        }
        v33 = (v32 >> 5) & 0x1FF;
        v34 = v33 + 1;
        if ( v33 + 1 > 0x1FF || v34 < v33 )
        {
          LOWORD(v34) = 1;
          v27 = v21;
          v28 = (v32 >> 5) & 0x1FF;
        }
        a3 = v32 ^ ((unsigned __int16)v32 ^ (unsigned __int16)(32 * v34)) & 0x3FE0;
        v35 = _InterlockedCompareExchange(v19, a3, v31);
        if ( v31 == v35 )
          break;
        v31 = v35;
      }
      v48 = v27;
      v26 = (v31 & 1) == 0;
      v24 = 0;
      break;
    case 0xFFFFFFFF:
    case 3u:
      wil_details_FeatureReporting_IncrementOpportunityInCache(v19, v21, a3, v44);
      v24 = v45;
      v27 = v44[2];
      v48 = v44[2];
      v28 = v44[1];
      v26 = v44[0];
      break;
    case 0u:
    case 1u:
    case 4u:
    case 5u:
      v22 = 0;
      if ( 4 * (v4 ^ 1) )
      {
        switch ( 4 * (v4 ^ 1) )
        {
          case 1u:
            v22 = 8;
            break;
          case 4u:
            v22 = 4;
            break;
          case 5u:
            v22 = 16;
            break;
        }
      }
      else
      {
        v22 = 2;
      }
      for ( i = *v19; ; i = v25 )
      {
        a3 = i | (unsigned int)v22;
        v24 = a3 == i;
        if ( (_DWORD)a3 != i )
          a3 = i | v22 | 1u;
        v25 = _InterlockedCompareExchange(v19, a3, i);
        if ( i == v25 )
          break;
      }
      v26 = (a3 & 1) != 0 && (i & 1) == 0;
      v27 = v44[2];
      v48 = v44[2];
      v28 = v44[1];
      break;
    case 2u:
      v29 = *((_DWORD *)v19 + 1);
      do
      {
        v24 = 0;
        v30 = v29;
        v29 = _InterlockedCompareExchange(
                v19 + 1,
                v29 ^ ((unsigned __int16)(32 * (v21 - 320)) ^ (unsigned __int16)v29) & 0x7E0 | 0x10,
                v29);
      }
      while ( v30 != v29 );
      v48 = 4 * (v4 ^ 1) + 2;
      v28 = 1;
      v26 = v44[0];
      v27 = v21;
      break;
  }
  if ( (_DWORD)v26 && wil::details::g_enabledStateManager )
  {
    if ( !wil::ProcessShutdownInProgress((wil *)v26) )
    {
      AcquireSRWLockExclusive(&SRWLock);
      if ( wil::details::g_enabledStateManager )
      {
        if ( !wil::ProcessShutdownInProgress(v36) )
        {
          *(_QWORD *)v44 = 20819441;
          *(_QWORD *)&v44[2] = v19;
          wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800ACD88, v44, 0x10u);
          if ( !byte_1800ACD80 )
          {
            if ( !qword_1800ACD78 )
            {
              LastError = GetLastError();
              ThreadpoolTimer = CreateThreadpoolTimer(
                                  _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                  &wil::details::g_enabledStateManager,
                                  0);
              wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
                (struct _TP_TIMER **)&qword_1800ACD78,
                ThreadpoolTimer);
              SetLastError(LastError);
              v21 = v49;
            }
            wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)&qword_1800ACD78, &byte_1800ACD80, 300000);
          }
        }
      }
      ReleaseSRWLockExclusive(&SRWLock);
    }
    v27 = v48;
  }
  if ( v28 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x13DADF1, v27, v28, v27, v41);
  if ( !v24 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_1800ACDD0 )
    {
      qword_1800ACDD0 = 0;
      wil::details::WilApi_SubscribeFeatureStateChangeNotification(
        (wil::details *)&qword_1800ACDD0,
        (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **)_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_,
        (void (*)(void *))0xFFFFFFFFFFFFFFFFLL,
        v39);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( (v6 & 0x400) != 0 )
  {
    v40 = v21;
    if ( (v6 & 0x800) != 0 )
      v40 = v21 | 0x80000000;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x13DADF1, v40, 0, v27, v41);
  }
  if ( !v24 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(a3) = 3;
      g_wil_details_realtimeFeatureUsageHook(20819441, v21, a3);
    }
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(20819441, &v42, 0, v20, &v46, 0, 0, 1);
  }
}

```

## disassembly

```asm
0x180003760  mov     [rsp-40h+arg_18], r9
0x180003765  mov     byte ptr [rsp-40h+arg_10], r8b
0x18000376a  push    rbp
0x18000376b  push    rbx
0x18000376c  push    rsi
0x18000376d  push    rdi
0x18000376e  push    r12
0x180003770  push    r13
0x180003772  push    r14
0x180003774  push    r15
0x180003776  mov     rbp, rsp
0x180003779  sub     rsp, 78h
0x18000377d  movzx   r14d, dl
0x180003781  mov     r15, rcx
0x180003784  mov     rbx, cs:Feature_RequestFromAppModelWatcher__descriptor
0x18000378b  mov     ebx, [rbx]
0x18000378d  xor     r12d, r12d
0x180003790  test    bl, 4
0x180003793  jnz     loc_1800038C9
0x180003799  mov     r13, cs:Feature_RequestFromAppModelWatcher__descriptor
0x1800037a0  mov     edi, [r13+0]
0x1800037a4  mov     eax, edi
0x1800037a6  and     eax, 6
0x1800037a9  cmp     al, 6
0x1800037ab  jz      loc_1800038C7
0x1800037b1  mov     r10d, cs:dword_1800ACD84
0x1800037b8  mov     [rbp+arg_10], r10d
0x1800037bc  nop
0x1800037bd  test    r10d, r10d
0x1800037c0  jnz     short loc_1800037D4
0x1800037c2  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x1800037c9  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x1800037ce  mov     r10d, eax
0x1800037d1  mov     [rbp+arg_10], eax
0x1800037d4  mov     [rbp+arg_8], r12d
0x1800037d8  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800037df  test    rax, rax
0x1800037e2  jnz     short loc_1800037F0
0x1800037e4  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800037eb  test    rax, rax
0x1800037ee  jz      short loc_180003840
0x1800037f0  lea     r8, [rbp+arg_8]
0x1800037f4  mov     edx, 3
0x1800037f9  mov     ecx, 13DADF1h
0x1800037fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003803  mov     ecx, eax
0x180003805  mov     r8d, eax
0x180003808  and     r8d, 80h
0x18000380f  mov     edx, eax
0x180003811  and     edx, 0FFFFFF3Fh
0x180003817  mov     eax, edx
0x180003819  and     eax, 3
0x18000381c  shl     eax, 2
0x18000381f  and     ecx, 40h
0x180003822  or      eax, ecx
0x180003824  shl     eax, 5
0x180003827  mov     r10d, [rbp+arg_10]
0x18000382b  test    edx, edx
0x18000382d  jz      short loc_180003846
0x18000382f  mov     r9d, r12d
0x180003832  mov     ecx, 40h ; '@'
0x180003837  cmp     edx, 2
0x18000383a  cmovz   r9d, ecx
0x18000383e  jmp     short loc_18000384C
0x180003840  mov     r8d, r12d
0x180003843  mov     eax, r12d
0x180003846  mov     r9d, 40h ; '@'
0x18000384c  mov     esi, 1
0x180003851  mov     ecx, 401h
0x180003856  test    r8d, r8d
0x180003859  cmovnz  esi, ecx
0x18000385c  or      esi, eax
0x18000385e  or      esi, r9d
0x180003861  cmp     [rbp+arg_8], r12d
0x180003865  jz      short loc_18000387E
0x180003867  test    dil, 2
0x18000386b  jnz     short loc_18000387E
0x18000386d  mov     ebx, esi
0x18000386f  xor     ebx, edi
0x180003871  and     ebx, 9C1h
0x180003877  xor     ebx, edi
0x180003879  or      ebx, 2
0x18000387c  jmp     short loc_180003880
0x18000387e  mov     ebx, edi
0x180003880  mov     edx, edi
0x180003882  and     edx, 4
0x180003885  jnz     short loc_180003896
0x180003887  mov     ecx, esi
0x180003889  xor     ecx, ebx
0x18000388b  and     ecx, 400h
0x180003891  xor     ebx, ecx
0x180003893  or      ebx, 4
0x180003896  mov     eax, edi
0x180003898  lock cmpxchg [r13+0], ebx
0x18000389e  mov     edi, eax
0x1800038a0  jnz     short loc_180003861
0x1800038a2  test    edx, edx
0x1800038a4  jnz     short loc_1800038B6
0x1800038a6  mov     r8d, r10d
0x1800038a9  mov     edx, 3
0x1800038ae  mov     rcx, r13
0x1800038b1  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800038b6  test    bl, 2
0x1800038b9  jnz     short loc_1800038C9
0x1800038bb  xor     esi, ebx
0x1800038bd  and     esi, 9C1h
0x1800038c3  xor     ebx, esi
0x1800038c5  jmp     short loc_1800038C9
0x1800038c7  mov     ebx, edi
0x1800038c9  mov     [rbp+var_28], 0
0x1800038d0  mov     [rbp+var_24], 3
0x1800038d6  mov     [rbp+arg_0], 3
0x1800038dd  add     r15, 8
0x1800038e1  mov     r13d, r14d
0x1800038e4  mov     eax, r14d
0x1800038e7  xor     eax, 1
0x1800038ea  lea     edi, ds:2[rax*4]
0x1800038f1  mov     dword ptr [rbp+arg_18], edi
0x1800038f4  xorps   xmm0, xmm0
0x1800038f7  xor     eax, eax
0x1800038f9  movups  xmmword ptr [rbp+var_20], xmm0
0x1800038fd  mov     [rbp+var_10], rax
0x180003901  movsxd  rax, edi
0x180003904  lea     rdx, __ImageBase
0x18000390b  mov     ecx, ds:(jpt_180003915 - 180000000h)[rdx+rax*4]; switch 8 cases
0x180003912  add     rcx, rdx
0x180003915  jmp     rcx; switch jump
0x180003917  mov     edx, r12d; jumptable 0000000180003915 cases 2,3,6,7
0x18000391a  mov     ecx, edi
0x18000391c  sub     ecx, 2
0x18000391f  jz      short loc_180003945
0x180003921  sub     ecx, 1
0x180003924  jz      short loc_18000393E
0x180003926  sub     ecx, 3
0x180003929  jz      short loc_180003937
0x18000392b  cmp     ecx, 1
0x18000392e  jnz     short loc_18000394A
0x180003930  mov     edx, 10h
0x180003935  jmp     short loc_18000394A
0x180003937  mov     edx, 4
0x18000393c  jmp     short loc_18000394A
0x18000393e  mov     edx, 8
0x180003943  jmp     short loc_18000394A
0x180003945  mov     edx, 2
0x18000394a  mov     ecx, [r15]
0x18000394d  mov     r8d, edx
0x180003950  or      r8d, ecx
0x180003953  mov     esi, r12d
0x180003956  cmp     r8d, ecx
0x180003959  setz    sil
0x18000395d  mov     eax, r8d
0x180003960  or      eax, 1
0x180003963  cmp     r8d, ecx
0x180003966  cmovnz  r8d, eax
0x18000396a  mov     eax, ecx
0x18000396c  lock cmpxchg [r15], r8d
0x180003971  jz      short loc_180003977
0x180003973  mov     ecx, eax
0x180003975  jmp     short loc_18000394D
0x180003977  test    r8b, 1
0x18000397b  setnz   dl
0x18000397e  test    cl, 1
0x180003981  setz    al
0x180003984  test    al, dl
0x180003986  mov     ecx, r12d
0x180003989  setnz   cl
0x18000398c  mov     r9d, [rbp+var_20+8]
0x180003990  mov     [rbp+arg_10], r9d
0x180003994  mov     r14d, [rbp+var_20+4]
0x180003998  jmp     loc_180003A8D
0x18000399d  lea     r9, [rbp+var_20]; jumptable 0000000180003915 cases 1,5
0x1800039a1  mov     edx, edi
0x1800039a3  mov     rcx, r15
0x1800039a6  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x1800039ab  mov     esi, dword ptr [rbp+var_10]
0x1800039ae  mov     r9d, [rbp+var_20+8]
0x1800039b2  mov     [rbp+arg_10], r9d
0x1800039b6  mov     r14d, [rbp+var_20+4]
0x1800039ba  mov     ecx, [rbp+var_20]
0x1800039bd  jmp     loc_180003A8D
0x1800039c2  mov     eax, [r15+4]; jumptable 0000000180003915 case 4
0x1800039c6  lea     edx, [rdi-140h]
0x1800039cc  shl     edx, 5
0x1800039cf  mov     esi, r12d
0x1800039d2  mov     ecx, eax
0x1800039d4  xor     ecx, edx
0x1800039d6  and     ecx, 7E0h
0x1800039dc  xor     ecx, eax
0x1800039de  or      ecx, 10h
0x1800039e1  lock cmpxchg [r15+4], ecx
0x1800039e7  jnz     short loc_1800039CF
0x1800039e9  mov     [rbp+arg_10], edi
0x1800039ec  mov     r14d, 1
0x1800039f2  mov     ecx, [rbp+var_20]
0x1800039f5  mov     r9d, edi
0x1800039f8  jmp     loc_180003A8D
0x1800039fd  mov     ecx, [r15]; jumptable 0000000180003915 case 0
0x180003a00  mov     r9d, [rbp+var_20+8]
0x180003a04  nop     dword ptr [rax+00h]
0x180003a08  nop     dword ptr [rax+rax+00000000h]
0x180003a10  mov     r14d, r12d
0x180003a13  mov     eax, ecx
0x180003a15  or      eax, 1
0x180003a18  bt      eax, 0Eh
0x180003a1c  jnb     short loc_180003A3A
0x180003a1e  mov     edx, eax
0x180003a20  shr     edx, 5
0x180003a23  and     edx, 1FFh
0x180003a29  jbe     short loc_180003A36
0x180003a2b  mov     r9d, r12d
0x180003a2e  mov     r14d, edx
0x180003a31  and     eax, 0FFFFC01Fh
0x180003a36  btr     eax, 0Eh
0x180003a3a  mov     edx, eax
0x180003a3c  shr     edx, 5
0x180003a3f  and     edx, 1FFh
0x180003a45  lea     r8d, [rdx+1]
0x180003a49  cmp     r8d, 1FFh
0x180003a50  ja      short loc_180003A57
0x180003a52  cmp     r8d, edx
0x180003a55  jnb     short loc_180003A63
0x180003a57  mov     r8d, 1
0x180003a5d  mov     r9d, edi
0x180003a60  mov     r14d, edx
0x180003a63  shl     r8d, 5
0x180003a67  xor     r8d, eax
0x180003a6a  and     r8d, 3FE0h
0x180003a71  xor     r8d, eax
0x180003a74  mov     eax, ecx
0x180003a76  lock cmpxchg [r15], r8d
0x180003a7b  jz      short loc_180003A81
0x180003a7d  mov     ecx, eax
0x180003a7f  jmp     short loc_180003A10
0x180003a81  mov     [rbp+arg_10], r9d
0x180003a85  not     cl
0x180003a87  and     ecx, 1; this
0x180003a8a  mov     esi, r12d
0x180003a8d  test    ecx, ecx
0x180003a8f  jz      loc_180003B70
0x180003a95  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180003a9b  test    eax, eax
0x180003a9d  jz      loc_180003B70
0x180003aa3  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180003aa8  test    al, al
0x180003aaa  jnz     loc_180003B6C
0x180003ab0  lea     rcx, SRWLock; SRWLock
0x180003ab7  call    cs:__imp_AcquireSRWLockExclusive
0x180003abd  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180003ac3  test    eax, eax
0x180003ac5  jz      loc_180003B5F
0x180003acb  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180003ad0  test    al, al
0x180003ad2  jnz     loc_180003B5F
0x180003ad8  mov     qword ptr [rbp+var_20], 13DADF1h
0x180003ae0  mov     qword ptr [rbp+var_20+8], r15
0x180003ae4  mov     r8d, 10h; unsigned __int64
0x180003aea  lea     rdx, [rbp+var_20]; void *
0x180003aee  lea     rcx, qword_1800ACD88; this
0x180003af5  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180003afa  cmp     cs:byte_1800ACD80, 0
0x180003b01  jnz     short loc_180003B5F
0x180003b03  cmp     cs:qword_1800ACD78, 0
0x180003b0b  jnz     short loc_180003B46
0x180003b0d  call    cs:__imp_GetLastError
0x180003b13  mov     edi, eax
0x180003b15  xor     r8d, r8d; pcbe
0x180003b18  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180003b1f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180003b26  call    cs:__imp_CreateThreadpoolTimer
0x180003b2c  mov     rdx, rax
0x180003b2f  lea     rcx, qword_1800ACD78
0x180003b36  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180003b3b  mov     ecx, edi; dwErrCode
0x180003b3d  call    cs:__imp_SetLastError
0x180003b43  mov     edi, dword ptr [rbp+arg_18]
0x180003b46  mov     r8d, 493E0h
0x180003b4c  lea     rdx, byte_1800ACD80
0x180003b53  lea     rcx, qword_1800ACD78
0x180003b5a  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180003b5f  lea     rcx, SRWLock; SRWLock
0x180003b66  call    cs:__imp_ReleaseSRWLockExclusive
0x180003b6c  mov     r9d, [rbp+arg_10]; unsigned int
0x180003b70  test    r14d, r14d
0x180003b73  jz      short loc_180003B85
0x180003b75  mov     r8d, r14d; unsigned int
0x180003b78  mov     edx, r9d; unsigned int
0x180003b7b  mov     ecx, 13DADF1h; this
0x180003b80  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180003b85  test    esi, esi
0x180003b87  jnz     short loc_180003BD9
0x180003b89  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180003b8f  test    eax, eax
0x180003b91  jz      short loc_180003BD9
0x180003b93  lea     rcx, SRWLock; SRWLock
0x180003b9a  call    cs:__imp_AcquireSRWLockExclusive
0x180003ba0  cmp     cs:qword_1800ACDD0, 0
0x180003ba8  jnz     short loc_180003BCB
0x180003baa  mov     cs:qword_1800ACDD0, r12
0x180003bb1  mov     r8, 0FFFFFFFFFFFFFFFFh; void (*)(void *)
0x180003bb8  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
  ... truncated ...
```
