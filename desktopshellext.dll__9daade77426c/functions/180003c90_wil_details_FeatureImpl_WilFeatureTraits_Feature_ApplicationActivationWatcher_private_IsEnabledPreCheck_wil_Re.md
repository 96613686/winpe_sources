# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ApplicationActivationWatcher>::__private_IsEnabledPreCheck(wil::ReportingKind)

- ea: `0x180003c90`
- end: `0x1800040f9`
- name: `?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_ApplicationActivationWatcher@@@details@wil@@QEAA_NW4ReportingKind@3@@Z`
- size: `1129`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800035b0`

## callees

- `0x180002d90`
- `0x180003c90`
- `0x180004900`
- `0x180004950`
- `0x180004980`
- `0x180004a10`
- `0x18000d2a0`
- `0x180030c8c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003f55`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000403a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800040b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003f55`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000403a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800040b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003f43`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003f8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004085`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003f43`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003f8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004085`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003eed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003eed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003f1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003f1d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180003f06`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180003f06`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ApplicationActivationWatcher>::__private_IsEnabledPreCheck(
        __int64 a1,
        char a2,
        __int64 a3,
        unsigned int a4)
{
  signed __int32 v5; // ebx
  signed __int32 v6; // edi
  unsigned int v7; // r15d
  __int64 (__fastcall *v8)(__int64, __int64, int *); // rax
  int v9; // eax
  unsigned int v10; // edx
  __int16 v11; // ax
  __int16 v12; // si
  unsigned __int16 v13; // si
  int v14; // edx
  bool v15; // zf
  signed __int32 v16; // eax
  volatile signed __int32 *v17; // rdi
  wil *i; // rcx
  signed __int32 v19; // edx
  BOOL v20; // esi
  unsigned __int32 v21; // eax
  unsigned int v22; // ebp
  DWORD LastError; // edi
  struct _TP_TIMER *ThreadpoolTimer; // rax
  void *v26; // r9
  unsigned int v27; // edx
  wil *v28; // rcx
  const char *v29; // [rsp+20h] [rbp-98h]
  __int64 v30; // [rsp+50h] [rbp-68h] BYREF
  __int64 *v31; // [rsp+58h] [rbp-60h]
  unsigned int v32[4]; // [rsp+60h] [rbp-58h]
  int v33; // [rsp+C0h] [rbp+8h] BYREF
  int v34; // [rsp+C8h] [rbp+10h] BYREF
  int v35; // [rsp+D0h] [rbp+18h] BYREF
  __int16 v36; // [rsp+D4h] [rbp+1Ch]

  LOBYTE(v34) = a2;
  v5 = *(_DWORD *)Feature_ApplicationActivationWatcher__descriptor;
  if ( (*(_DWORD *)Feature_ApplicationActivationWatcher__descriptor & 4) != 0 )
    goto LABEL_21;
  v6 = *(_DWORD *)Feature_ApplicationActivationWatcher__descriptor;
  if ( (*(_BYTE *)Feature_ApplicationActivationWatcher__descriptor & 6) == 6 )
  {
    LOWORD(v5) = *(_DWORD *)Feature_ApplicationActivationWatcher__descriptor;
    goto LABEL_21;
  }
  v7 = dword_1800ACD84;
  if ( !dword_1800ACD84 )
    v7 = wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
  v34 = 0;
  v8 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v8 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v9 = v8(21726163, 3, &v34);
    a3 = (unsigned __int8)v9 & 0x80;
    v10 = v9 & 0xFFFFFF3F;
    v11 = 32 * (v9 & 0x40 | (4 * (v9 & 3)));
    if ( v10 )
    {
      a4 = 0;
      if ( v10 == 2 )
        a4 = 64;
      goto LABEL_8;
    }
  }
  else
  {
    a3 = 0;
    v11 = 0;
  }
  a4 = 64;
LABEL_8:
  v12 = 1;
  if ( (_DWORD)a3 )
    v12 = 1025;
  v13 = a4 | v11 | v12;
  do
  {
    if ( !v34 || (v6 & 2) != 0 )
      v5 = v6;
    else
      v5 = v6 ^ ((unsigned __int16)v6 ^ v13) & 0x9C1 | 2;
    v14 = v6 & 4;
    if ( (v6 & 4) == 0 )
      v5 = ((unsigned __int16)v5 ^ v13) & 0x400 ^ v5 | 4;
    v16 = _InterlockedCompareExchange(
            (volatile signed __int32 *)Feature_ApplicationActivationWatcher__descriptor,
            v5,
            v6);
    v15 = v6 == v16;
    v6 = v16;
  }
  while ( !v15 );
  if ( !v14 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !v7
      || v7 != dword_1800ACD84
      || (v30 = 3,
          v31 = Feature_ApplicationActivationWatcher__descriptor,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800ACDA8, &v30, 0x10u)) )
    {
      _InterlockedAnd((volatile signed __int32 *)Feature_ApplicationActivationWatcher__descriptor, 0xFFFFFFFB);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( (v5 & 2) == 0 )
    LOWORD(v5) = (v5 ^ v13) & 0x9C1 ^ v5;
LABEL_21:
  v35 = 0;
  v36 = 3;
  v33 = 3;
  v17 = (volatile signed __int32 *)(a1 + 8);
  *(_OWORD *)v32 = 0;
  for ( i = (wil *)*(unsigned int *)(a1 + 8); ; i = (wil *)v21 )
  {
    v19 = (unsigned int)i | 2;
    v20 = ((unsigned int)i | 2) == (_DWORD)i;
    if ( ((unsigned int)i | 2) != (_DWORD)i )
      v19 = (unsigned int)i | 3;
    v21 = _InterlockedCompareExchange(v17, v19, (signed __int32)i);
    if ( (_DWORD)i == v21 )
      break;
  }
  v22 = v32[1];
  if ( (v19 & 1) != 0
    && ((unsigned __int8)i & 1) == 0
    && wil::details::g_enabledStateManager
    && !wil::ProcessShutdownInProgress(i) )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( wil::details::g_enabledStateManager )
    {
      if ( !wil::ProcessShutdownInProgress(v28) )
      {
        v30 = 21726163;
        v31 = (__int64 *)v17;
        wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800ACD88, &v30, 0x10u);
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
          }
          wil::details::EnsureCoalescedTimer_SetTimer((struct _TP_TIMER **)&qword_1800ACD78, &byte_1800ACD80, 300000);
        }
      }
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( v22 )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x14B83D3, v32[2], v22, a4, v29);
  if ( !v20 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !qword_1800ACDD0 )
    {
      qword_1800ACDD0 = 0;
      wil::details::WilApi_SubscribeFeatureStateChangeNotification(
        (wil::details *)&qword_1800ACDD0,
        (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **)_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_,
        (void (*)(void *))0xFFFFFFFFFFFFFFFFLL,
        v26);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( (v5 & 0x400) != 0 )
  {
    v27 = 2;
    if ( (v5 & 0x800) != 0 )
      v27 = -2147483646;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0x14B83D3, v27, 0, a4, v29);
  }
  if ( !v20 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(a3) = 3;
      g_wil_details_realtimeFeatureUsageHook(21726163, 2, a3);
    }
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(21726163, &v35, 0, 1, &v33, 0, 0, 1);
  }
  return 1;
}

```

## disassembly

```asm
0x180003c90  mov     byte ptr [rsp+arg_8], dl
0x180003c94  push    rbx
0x180003c95  push    rbp
0x180003c96  push    rsi
0x180003c97  push    rdi
0x180003c98  push    r12
0x180003c9a  push    r14
0x180003c9c  push    r15
0x180003c9e  sub     rsp, 80h
0x180003ca5  mov     rbp, rcx
0x180003ca8  mov     rbx, cs:Feature_ApplicationActivationWatcher__descriptor
0x180003caf  mov     ebx, [rbx]
0x180003cb1  xor     r12d, r12d
0x180003cb4  test    bl, 4
0x180003cb7  jnz     loc_180003DBE
0x180003cbd  mov     r14, cs:Feature_ApplicationActivationWatcher__descriptor
0x180003cc4  mov     edi, [r14]
0x180003cc7  mov     eax, edi
0x180003cc9  and     eax, 6
0x180003ccc  cmp     al, 6
0x180003cce  jz      loc_180003E0D
0x180003cd4  mov     r15d, cs:dword_1800ACD84
0x180003cdb  nop
0x180003cdc  test    r15d, r15d
0x180003cdf  jz      loc_180003FF0
0x180003ce5  mov     [rsp+0B8h+arg_8], r12d
0x180003ced  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180003cf4  test    rax, rax
0x180003cf7  jz      loc_180004004
0x180003cfd  lea     r8, [rsp+0B8h+arg_8]
0x180003d05  mov     edx, 3
0x180003d0a  mov     ecx, 14B83D3h
0x180003d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d14  mov     ecx, eax
0x180003d16  mov     r8d, eax
0x180003d19  and     r8d, 80h
0x180003d20  mov     edx, eax
0x180003d22  and     edx, 0FFFFFF3Fh
0x180003d28  mov     eax, edx
0x180003d2a  and     eax, 3
0x180003d2d  shl     eax, 2
0x180003d30  and     ecx, 40h
0x180003d33  or      eax, ecx
0x180003d35  shl     eax, 5
0x180003d38  test    edx, edx
0x180003d3a  jnz     loc_18000401F
0x180003d40  mov     r9d, 40h ; '@'; unsigned int
0x180003d46  mov     esi, 1
0x180003d4b  mov     ecx, 401h
0x180003d50  test    r8d, r8d
0x180003d53  cmovnz  esi, ecx
0x180003d56  or      esi, eax
0x180003d58  or      esi, r9d
0x180003d5b  cmp     [rsp+0B8h+arg_8], r12d
0x180003d63  jz      loc_180003E11
0x180003d69  test    dil, 2
0x180003d6d  jnz     loc_180003E11
0x180003d73  mov     ebx, esi
0x180003d75  xor     ebx, edi
0x180003d77  and     ebx, 9C1h
0x180003d7d  xor     ebx, edi
0x180003d7f  or      ebx, 2
0x180003d82  mov     edx, edi
0x180003d84  and     edx, 4
0x180003d87  jnz     short loc_180003D98
0x180003d89  mov     ecx, esi
0x180003d8b  xor     ecx, ebx
0x180003d8d  and     ecx, 400h
0x180003d93  xor     ebx, ecx
0x180003d95  or      ebx, 4
0x180003d98  mov     eax, edi
0x180003d9a  lock cmpxchg [r14], ebx
0x180003d9f  mov     edi, eax
0x180003da1  jnz     short loc_180003D5B
0x180003da3  test    edx, edx
0x180003da5  jnz     short loc_180003DB5
0x180003da7  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180003dad  test    eax, eax
0x180003daf  jnz     loc_180004033
0x180003db5  test    bl, 2
0x180003db8  jz      loc_180004090
0x180003dbe  mov     [rsp+0B8h+arg_10], r12d
0x180003dc6  mov     [rsp+0B8h+arg_14], 3
0x180003dd0  mov     [rsp+0B8h+arg_0], 3
0x180003ddb  lea     rdi, [rbp+8]
0x180003ddf  xorps   xmm0, xmm0
0x180003de2  movups  xmmword ptr [rsp+0B8h+var_58], xmm0
0x180003de7  mov     ecx, [rdi]; this
0x180003de9  mov     edx, ecx
0x180003deb  or      edx, 2
0x180003dee  mov     esi, r12d
0x180003df1  cmp     edx, ecx
0x180003df3  setz    sil
0x180003df7  mov     eax, edx
0x180003df9  or      eax, 1
0x180003dfc  cmp     edx, ecx
0x180003dfe  cmovnz  edx, eax
0x180003e01  mov     eax, ecx
0x180003e03  lock cmpxchg [rdi], edx
0x180003e07  jz      short loc_180003E18
0x180003e09  mov     ecx, eax
0x180003e0b  jmp     short loc_180003DE9
0x180003e0d  mov     ebx, edi
0x180003e0f  jmp     short loc_180003DBE
0x180003e11  mov     ebx, edi
0x180003e13  jmp     loc_180003D82
0x180003e18  test    dl, 1
0x180003e1b  setnz   dl
0x180003e1e  test    cl, 1
0x180003e21  setz    al
0x180003e24  test    al, dl
0x180003e26  mov     eax, r12d
0x180003e29  setnz   al
0x180003e2c  mov     ebp, [rsp+0B8h+var_58+4]
0x180003e30  test    eax, eax
0x180003e32  jz      short loc_180003E42
0x180003e34  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180003e3a  test    eax, eax
0x180003e3c  jnz     loc_18000409F
0x180003e42  test    ebp, ebp
0x180003e44  jnz     loc_1800040D9
0x180003e4a  test    esi, esi
0x180003e4c  jnz     short loc_180003E5C
0x180003e4e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180003e54  test    eax, eax
0x180003e56  jnz     loc_180003F4E
0x180003e5c  bt      ebx, 0Ah
0x180003e60  jb      loc_180003F98
0x180003e66  test    esi, esi
0x180003e68  jnz     short loc_180003ECF
0x180003e6a  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180003e71  test    rax, rax
0x180003e74  jz      short loc_180003E88
0x180003e76  mov     r8b, 3
0x180003e79  mov     edx, 2
0x180003e7e  mov     ecx, 14B83D3h
0x180003e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e88  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180003e8f  test    rax, rax
0x180003e92  jz      short loc_180003ECF
0x180003e94  mov     [rsp+0B8h+var_80], 1
0x180003e9d  mov     [rsp+0B8h+var_88], 0
0x180003ea2  mov     [rsp+0B8h+var_90], r12
0x180003ea7  lea     rdx, [rsp+0B8h+arg_0]
0x180003eaf  mov     [rsp+0B8h+var_98], rdx
0x180003eb4  mov     r9d, 1
0x180003eba  xor     r8d, r8d
0x180003ebd  lea     rdx, [rsp+0B8h+arg_10]
0x180003ec5  mov     ecx, 14B83D3h
0x180003eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ecf  mov     al, 1
0x180003ed1  add     rsp, 80h
0x180003ed8  pop     r15
0x180003eda  pop     r14
0x180003edc  pop     r12
0x180003ede  pop     rdi
0x180003edf  pop     rsi
0x180003ee0  pop     rbp
0x180003ee1  pop     rbx
0x180003ee2  retn
0x180003ee3  cmp     cs:qword_1800ACD78, 0
0x180003eeb  jnz     short loc_180003F23
0x180003eed  call    cs:__imp_GetLastError
0x180003ef3  mov     edi, eax
0x180003ef5  xor     r8d, r8d; pcbe
0x180003ef8  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180003eff  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180003f06  call    cs:__imp_CreateThreadpoolTimer
0x180003f0c  mov     rdx, rax
0x180003f0f  lea     rcx, qword_1800ACD78
0x180003f16  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180003f1b  mov     ecx, edi; dwErrCode
0x180003f1d  call    cs:__imp_SetLastError
0x180003f23  mov     r8d, 493E0h
0x180003f29  lea     rdx, byte_1800ACD80
0x180003f30  lea     rcx, qword_1800ACD78
0x180003f37  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x180003f3c  lea     rcx, SRWLock; SRWLock
0x180003f43  call    cs:__imp_ReleaseSRWLockExclusive
0x180003f49  jmp     loc_180003E42
0x180003f4e  lea     rcx, SRWLock; SRWLock
0x180003f55  call    cs:__imp_AcquireSRWLockExclusive
0x180003f5b  cmp     cs:qword_1800ACDD0, 0
0x180003f63  jnz     short loc_180003F86
0x180003f65  mov     cs:qword_1800ACDD0, r12
0x180003f6c  mov     r8, 0FFFFFFFFFFFFFFFFh; void (*)(void *)
0x180003f73  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x180003f7a  lea     rcx, qword_1800ACDD0; this
0x180003f81  call    ?WilApi_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details::WilApi_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180003f86  lea     rcx, SRWLock; SRWLock
0x180003f8d  call    cs:__imp_ReleaseSRWLockExclusive
0x180003f93  jmp     loc_180003E5C
0x180003f98  mov     edx, 2; unsigned int
0x180003f9d  bt      ebx, 0Bh
0x180003fa1  jb      loc_1800040EF
0x180003fa7  xor     r8d, r8d; unsigned int
0x180003faa  mov     ecx, 14B83D3h; this
0x180003faf  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180003fb4  jmp     loc_180003E66
0x180003fb9  mov     [rsp+0B8h+var_68], 14B83D3h
0x180003fc2  mov     [rsp+0B8h+var_60], rdi
0x180003fc7  mov     r8d, 10h; unsigned __int64
0x180003fcd  lea     rdx, [rsp+0B8h+var_68]; void *
0x180003fd2  lea     rcx, qword_1800ACD88; this
0x180003fd9  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180003fde  cmp     cs:byte_1800ACD80, 0
0x180003fe5  jnz     loc_180003F3C
0x180003feb  jmp     loc_180003EE3
0x180003ff0  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180003ff7  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x180003ffc  mov     r15d, eax
0x180003fff  jmp     loc_180003CE5
0x180004004  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000400b  test    rax, rax
0x18000400e  jnz     loc_180003CFD
0x180004014  mov     r8d, r12d
0x180004017  mov     eax, r12d
0x18000401a  jmp     loc_180003D40
0x18000401f  mov     r9d, r12d
0x180004022  mov     ecx, 40h ; '@'
0x180004027  cmp     edx, 2
0x18000402a  cmovz   r9d, ecx
0x18000402e  jmp     loc_180003D46
0x180004033  lea     rcx, SRWLock; SRWLock
0x18000403a  call    cs:__imp_AcquireSRWLockExclusive
0x180004040  mov     eax, cs:dword_1800ACD84
0x180004046  test    r15d, r15d
0x180004049  jz      short loc_180004079
0x18000404b  cmp     r15d, eax
0x18000404e  jnz     short loc_180004079
0x180004050  mov     [rsp+0B8h+var_68], 3
0x180004059  mov     [rsp+0B8h+var_60], r14
0x18000405e  mov     r8d, 10h; unsigned __int64
0x180004064  lea     rdx, [rsp+0B8h+var_68]; void *
0x180004069  lea     rcx, qword_1800ACDA8; this
0x180004070  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180004075  test    al, al
0x180004077  jnz     short loc_18000407E
0x180004079  lock and dword ptr [r14], 0FFFFFFFBh
0x18000407e  lea     rcx, SRWLock; SRWLock
0x180004085  call    cs:__imp_ReleaseSRWLockExclusive
0x18000408b  jmp     loc_180003DB5
0x180004090  xor     esi, ebx
0x180004092  and     esi, 9C1h
0x180004098  xor     ebx, esi
0x18000409a  jmp     loc_180003DBE
0x18000409f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800040a4  test    al, al
0x1800040a6  jnz     loc_180003E42
0x1800040ac  lea     rcx, SRWLock; SRWLock
0x1800040b3  call    cs:__imp_AcquireSRWLockExclusive
0x1800040b9  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800040bf  test    eax, eax
0x1800040c1  jz      loc_180003F3C
0x1800040c7  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x1800040cc  test    al, al
0x1800040ce  jnz     loc_180003F3C
0x1800040d4  jmp     loc_180003FB9
0x1800040d9  mov     r8d, ebp; unsigned int
0x1800040dc  mov     edx, [rsp+0B8h+var_58+8]; unsigned int
0x1800040e0  mov     ecx, 14B83D3h; this
0x1800040e5  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800040ea  jmp     loc_180003E4A
0x1800040ef  mov     edx, 80000002h
0x1800040f4  jmp     loc_180003FA7
```
