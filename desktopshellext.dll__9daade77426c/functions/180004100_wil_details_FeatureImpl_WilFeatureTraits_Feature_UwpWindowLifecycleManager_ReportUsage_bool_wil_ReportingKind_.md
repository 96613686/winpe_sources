# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UwpWindowLifecycleManager>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x180004100`
- end: `0x180004628`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_UwpWindowLifecycleManager@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `1320`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800034f0`

## callees

- `0x180002cf0`
- `0x180002d90`
- `0x180004100`
- `0x180004900`
- `0x180004950`
- `0x180004980`
- `0x180004a10`
- `0x18000d2a0`
- `0x180030c8c`
- `0x180033de8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004457`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000453a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004457`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000453a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004506`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004572`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004506`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004572`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044dd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800044c6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800044c6`

## pseudocode

```c
void __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UwpWindowLifecycleManager>::ReportUsage(
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
  v6 = *(_DWORD *)Feature_UwpWindowLifecycleManager__descriptor;
  if ( (*(_DWORD *)Feature_UwpWindowLifecycleManager__descriptor & 4) != 0 )
    goto LABEL_28;
  v7 = *(_DWORD *)Feature_UwpWindowLifecycleManager__descriptor;
  if ( (*(_BYTE *)Feature_UwpWindowLifecycleManager__descriptor & 6) == 6 )
  {
    LOWORD(v6) = *(_DWORD *)Feature_UwpWindowLifecycleManager__descriptor;
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
    v10 = v9(22782356, 3, &v47);
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
    v18 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UwpWindowLifecycleManager__descriptor, v6, v7);
    v17 = v7 == v18;
    v7 = v18;
  }
  while ( !v17 );
  if ( !v16 )
    wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_UwpWindowLifecycleManager__descriptor, 3, v8);
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
          *(_QWORD *)v44 = 22782356;
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
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x15BA194, v27, v28, v27, v41);
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
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x15BA194, v40, 0, v27, v41);
  }
  if ( !v24 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(a3) = 3;
      g_wil_details_realtimeFeatureUsageHook(22782356, v21, a3);
    }
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(22782356, &v42, 0, v20, &v46, 0, 0, 1);
  }
}

```

## disassembly

```asm
0x180004100  mov     [rsp-40h+arg_18], r9
0x180004105  mov     byte ptr [rsp-40h+arg_10], r8b
0x18000410a  push    rbp
0x18000410b  push    rbx
0x18000410c  push    rsi
0x18000410d  push    rdi
0x18000410e  push    r12
0x180004110  push    r13
0x180004112  push    r14
0x180004114  push    r15
0x180004116  mov     rbp, rsp
0x180004119  sub     rsp, 78h
0x18000411d  movzx   r14d, dl
0x180004121  mov     r15, rcx
0x180004124  mov     rbx, cs:Feature_UwpWindowLifecycleManager__descriptor
0x18000412b  mov     ebx, [rbx]
0x18000412d  xor     r12d, r12d
0x180004130  test    bl, 4
0x180004133  jnz     loc_180004269
0x180004139  mov     r13, cs:Feature_UwpWindowLifecycleManager__descriptor
0x180004140  mov     edi, [r13+0]
0x180004144  mov     eax, edi
0x180004146  and     eax, 6
0x180004149  cmp     al, 6
0x18000414b  jz      loc_180004267
0x180004151  mov     r10d, cs:dword_1800ACD84
0x180004158  mov     [rbp+arg_10], r10d
0x18000415c  nop
0x18000415d  test    r10d, r10d
0x180004160  jnz     short loc_180004174
0x180004162  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180004169  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x18000416e  mov     r10d, eax
0x180004171  mov     [rbp+arg_10], eax
0x180004174  mov     [rbp+arg_8], r12d
0x180004178  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000417f  test    rax, rax
0x180004182  jnz     short loc_180004190
0x180004184  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000418b  test    rax, rax
0x18000418e  jz      short loc_1800041E0
0x180004190  lea     r8, [rbp+arg_8]
0x180004194  mov     edx, 3
0x180004199  mov     ecx, 15BA194h
0x18000419e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041a3  mov     ecx, eax
0x1800041a5  mov     r8d, eax
0x1800041a8  and     r8d, 80h
0x1800041af  mov     edx, eax
0x1800041b1  and     edx, 0FFFFFF3Fh
0x1800041b7  mov     eax, edx
0x1800041b9  and     eax, 3
0x1800041bc  shl     eax, 2
0x1800041bf  and     ecx, 40h
0x1800041c2  or      eax, ecx
0x1800041c4  shl     eax, 5
0x1800041c7  mov     r10d, [rbp+arg_10]
0x1800041cb  test    edx, edx
0x1800041cd  jz      short loc_1800041E6
0x1800041cf  mov     r9d, r12d
0x1800041d2  mov     ecx, 40h ; '@'
0x1800041d7  cmp     edx, 2
0x1800041da  cmovz   r9d, ecx
0x1800041de  jmp     short loc_1800041EC
0x1800041e0  mov     r8d, r12d
0x1800041e3  mov     eax, r12d
0x1800041e6  mov     r9d, 40h ; '@'
0x1800041ec  mov     esi, 1
0x1800041f1  mov     ecx, 401h
0x1800041f6  test    r8d, r8d
0x1800041f9  cmovnz  esi, ecx
0x1800041fc  or      esi, eax
0x1800041fe  or      esi, r9d
0x180004201  cmp     [rbp+arg_8], r12d
0x180004205  jz      short loc_18000421E
0x180004207  test    dil, 2
0x18000420b  jnz     short loc_18000421E
0x18000420d  mov     ebx, esi
0x18000420f  xor     ebx, edi
0x180004211  and     ebx, 9C1h
0x180004217  xor     ebx, edi
0x180004219  or      ebx, 2
0x18000421c  jmp     short loc_180004220
0x18000421e  mov     ebx, edi
0x180004220  mov     edx, edi
0x180004222  and     edx, 4
0x180004225  jnz     short loc_180004236
0x180004227  mov     ecx, esi
0x180004229  xor     ecx, ebx
0x18000422b  and     ecx, 400h
0x180004231  xor     ebx, ecx
0x180004233  or      ebx, 4
0x180004236  mov     eax, edi
0x180004238  lock cmpxchg [r13+0], ebx
0x18000423e  mov     edi, eax
0x180004240  jnz     short loc_180004201
0x180004242  test    edx, edx
0x180004244  jnz     short loc_180004256
0x180004246  mov     r8d, r10d
0x180004249  mov     edx, 3
0x18000424e  mov     rcx, r13
0x180004251  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180004256  test    bl, 2
0x180004259  jnz     short loc_180004269
0x18000425b  xor     esi, ebx
0x18000425d  and     esi, 9C1h
0x180004263  xor     ebx, esi
0x180004265  jmp     short loc_180004269
0x180004267  mov     ebx, edi
0x180004269  mov     [rbp+var_28], 0
0x180004270  mov     [rbp+var_24], 3
0x180004276  mov     [rbp+arg_0], 3
0x18000427d  add     r15, 8
0x180004281  mov     r13d, r14d
0x180004284  mov     eax, r14d
0x180004287  xor     eax, 1
0x18000428a  lea     edi, ds:2[rax*4]
0x180004291  mov     dword ptr [rbp+arg_18], edi
0x180004294  xorps   xmm0, xmm0
0x180004297  xor     eax, eax
0x180004299  movups  xmmword ptr [rbp+var_20], xmm0
0x18000429d  mov     [rbp+var_10], rax
0x1800042a1  movsxd  rax, edi
0x1800042a4  lea     rdx, __ImageBase
0x1800042ab  mov     ecx, ds:(jpt_1800042B5 - 180000000h)[rdx+rax*4]; switch 8 cases
0x1800042b2  add     rcx, rdx
0x1800042b5  jmp     rcx; switch jump
0x1800042b7  mov     edx, r12d; jumptable 00000001800042B5 cases 2,3,6,7
0x1800042ba  mov     ecx, edi
0x1800042bc  sub     ecx, 2
0x1800042bf  jz      short loc_1800042E5
0x1800042c1  sub     ecx, 1
0x1800042c4  jz      short loc_1800042DE
0x1800042c6  sub     ecx, 3
0x1800042c9  jz      short loc_1800042D7
0x1800042cb  cmp     ecx, 1
0x1800042ce  jnz     short loc_1800042EA
0x1800042d0  mov     edx, 10h
0x1800042d5  jmp     short loc_1800042EA
0x1800042d7  mov     edx, 4
0x1800042dc  jmp     short loc_1800042EA
0x1800042de  mov     edx, 8
0x1800042e3  jmp     short loc_1800042EA
0x1800042e5  mov     edx, 2
0x1800042ea  mov     ecx, [r15]
0x1800042ed  mov     r8d, edx
0x1800042f0  or      r8d, ecx
0x1800042f3  mov     esi, r12d
0x1800042f6  cmp     r8d, ecx
0x1800042f9  setz    sil
0x1800042fd  mov     eax, r8d
0x180004300  or      eax, 1
0x180004303  cmp     r8d, ecx
0x180004306  cmovnz  r8d, eax
0x18000430a  mov     eax, ecx
0x18000430c  lock cmpxchg [r15], r8d
0x180004311  jz      short loc_180004317
0x180004313  mov     ecx, eax
0x180004315  jmp     short loc_1800042ED
0x180004317  test    r8b, 1
0x18000431b  setnz   dl
0x18000431e  test    cl, 1
0x180004321  setz    al
0x180004324  test    al, dl
0x180004326  mov     ecx, r12d
0x180004329  setnz   cl
0x18000432c  mov     r9d, [rbp+var_20+8]
0x180004330  mov     [rbp+arg_10], r9d
0x180004334  mov     r14d, [rbp+var_20+4]
0x180004338  jmp     loc_18000442D
0x18000433d  lea     r9, [rbp+var_20]; jumptable 00000001800042B5 cases 1,5
0x180004341  mov     edx, edi
0x180004343  mov     rcx, r15
0x180004346  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18000434b  mov     esi, dword ptr [rbp+var_10]
0x18000434e  mov     r9d, [rbp+var_20+8]
0x180004352  mov     [rbp+arg_10], r9d
0x180004356  mov     r14d, [rbp+var_20+4]
0x18000435a  mov     ecx, [rbp+var_20]
0x18000435d  jmp     loc_18000442D
0x180004362  mov     eax, [r15+4]; jumptable 00000001800042B5 case 4
0x180004366  lea     edx, [rdi-140h]
0x18000436c  shl     edx, 5
0x18000436f  mov     esi, r12d
0x180004372  mov     ecx, eax
0x180004374  xor     ecx, edx
0x180004376  and     ecx, 7E0h
0x18000437c  xor     ecx, eax
0x18000437e  or      ecx, 10h
0x180004381  lock cmpxchg [r15+4], ecx
0x180004387  jnz     short loc_18000436F
0x180004389  mov     [rbp+arg_10], edi
0x18000438c  mov     r14d, 1
0x180004392  mov     ecx, [rbp+var_20]
0x180004395  mov     r9d, edi
0x180004398  jmp     loc_18000442D
0x18000439d  mov     ecx, [r15]; jumptable 00000001800042B5 case 0
0x1800043a0  mov     r9d, [rbp+var_20+8]
0x1800043a4  nop     dword ptr [rax+00h]
0x1800043a8  nop     dword ptr [rax+rax+00000000h]
0x1800043b0  mov     r14d, r12d
0x1800043b3  mov     eax, ecx
0x1800043b5  or      eax, 1
0x1800043b8  bt      eax, 0Eh
0x1800043bc  jnb     short loc_1800043DA
0x1800043be  mov     edx, eax
0x1800043c0  shr     edx, 5
0x1800043c3  and     edx, 1FFh
0x1800043c9  jbe     short loc_1800043D6
0x1800043cb  mov     r9d, r12d
0x1800043ce  mov     r14d, edx
0x1800043d1  and     eax, 0FFFFC01Fh
0x1800043d6  btr     eax, 0Eh
0x1800043da  mov     edx, eax
0x1800043dc  shr     edx, 5
0x1800043df  and     edx, 1FFh
0x1800043e5  lea     r8d, [rdx+1]
0x1800043e9  cmp     r8d, 1FFh
0x1800043f0  ja      short loc_1800043F7
0x1800043f2  cmp     r8d, edx
0x1800043f5  jnb     short loc_180004403
0x1800043f7  mov     r8d, 1
0x1800043fd  mov     r9d, edi
0x180004400  mov     r14d, edx
0x180004403  shl     r8d, 5
0x180004407  xor     r8d, eax
0x18000440a  and     r8d, 3FE0h
0x180004411  xor     r8d, eax
0x180004414  mov     eax, ecx
0x180004416  lock cmpxchg [r15], r8d
0x18000441b  jz      short loc_180004421
0x18000441d  mov     ecx, eax
0x18000441f  jmp     short loc_1800043B0
0x180004421  mov     [rbp+arg_10], r9d
0x180004425  not     cl
0x180004427  and     ecx, 1; this
0x18000442a  mov     esi, r12d
0x18000442d  test    ecx, ecx
0x18000442f  jz      loc_180004510
0x180004435  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000443b  test    eax, eax
0x18000443d  jz      loc_180004510
0x180004443  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180004448  test    al, al
0x18000444a  jnz     loc_18000450C
0x180004450  lea     rcx, SRWLock; SRWLock
0x180004457  call    cs:__imp_AcquireSRWLockExclusive
0x18000445d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004463  test    eax, eax
0x180004465  jz      loc_1800044FF
0x18000446b  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x180004470  test    al, al
0x180004472  jnz     loc_1800044FF
0x180004478  mov     qword ptr [rbp+var_20], 15BA194h
0x180004480  mov     qword ptr [rbp+var_20+8], r15
0x180004484  mov     r8d, 10h; unsigned __int64
0x18000448a  lea     rdx, [rbp+var_20]; void *
0x18000448e  lea     rcx, qword_1800ACD88; this
0x180004495  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000449a  cmp     cs:byte_1800ACD80, 0
0x1800044a1  jnz     short loc_1800044FF
0x1800044a3  cmp     cs:qword_1800ACD78, 0
0x1800044ab  jnz     short loc_1800044E6
0x1800044ad  call    cs:__imp_GetLastError
0x1800044b3  mov     edi, eax
0x1800044b5  xor     r8d, r8d; pcbe
0x1800044b8  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x1800044bf  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800044c6  call    cs:__imp_CreateThreadpoolTimer
0x1800044cc  mov     rdx, rax
0x1800044cf  lea     rcx, qword_1800ACD78
0x1800044d6  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800044db  mov     ecx, edi; dwErrCode
0x1800044dd  call    cs:__imp_SetLastError
0x1800044e3  mov     edi, dword ptr [rbp+arg_18]
0x1800044e6  mov     r8d, 493E0h
0x1800044ec  lea     rdx, byte_1800ACD80
0x1800044f3  lea     rcx, qword_1800ACD78
0x1800044fa  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x1800044ff  lea     rcx, SRWLock; SRWLock
0x180004506  call    cs:__imp_ReleaseSRWLockExclusive
0x18000450c  mov     r9d, [rbp+arg_10]; unsigned int
0x180004510  test    r14d, r14d
0x180004513  jz      short loc_180004525
0x180004515  mov     r8d, r14d; unsigned int
0x180004518  mov     edx, r9d; unsigned int
0x18000451b  mov     ecx, 15BA194h; this
0x180004520  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180004525  test    esi, esi
0x180004527  jnz     short loc_180004579
0x180004529  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000452f  test    eax, eax
0x180004531  jz      short loc_180004579
0x180004533  lea     rcx, SRWLock; SRWLock
0x18000453a  call    cs:__imp_AcquireSRWLockExclusive
0x180004540  cmp     cs:qword_1800ACDD0, 0
0x180004548  jnz     short loc_18000456B
0x18000454a  mov     cs:qword_1800ACDD0, r12
0x180004551  mov     r8, 0FFFFFFFFFFFFFFFFh; void (*)(void *)
0x180004558  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
  ... truncated ...
```
