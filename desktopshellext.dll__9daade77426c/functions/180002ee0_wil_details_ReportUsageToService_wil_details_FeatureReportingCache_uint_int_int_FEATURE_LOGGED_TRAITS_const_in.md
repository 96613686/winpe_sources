# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180002ee0`
- end: `0x1800034dc`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `1532`
- prototype: `void __high(struct wil_details_FeatureReportingCache *, unsigned int, int, int, const struct FEATURE_LOGGED_TRAITS *, int, enum wil_ReportingKind, unsigned __int64)`
- caller_count: `81`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800212a8`
- `0x1800316c8`
- `0x180037a50`
- `0x180037b98`
- `0x1800390c4`
- `0x180039150`
- `0x1800391e8`
- `0x180039270`
- `0x1800392fc`
- `0x18004cc9c`
- `0x18004cdd0`
- `0x18004d068`
- `0x18004d1bc`
- `0x18004d310`
- `0x18004d550`
- `0x18004dca0`
- `0x18004dd2c`
- `0x18004ddb4`
- `0x18004de40`
- `0x18004decc`
- `0x18004df58`
- `0x18004dfdc`
- `0x18004e064`
- `0x18004e0ec`
- `0x18004e174`
- `0x18004e1fc`
- `0x180057b00`
- `0x180057b8c`
- `0x180062230`
- `0x1800656a4`
- `0x180065730`
- `0x1800657bc`
- `0x180065844`
- `0x1800658dc`
- `0x180065974`
- `0x180065a0c`
- `0x18007234c`
- `0x1800725cc`
- `0x180072954`
- `0x180072a80`
- `0x180072bd0`
- `0x180072d18`
- `0x180073008`
- `0x1800732cc`
- `0x180073518`
- `0x180073748`
- `0x18007389c`
- `0x1800739c8`
- `0x180073b04`
- `0x1800767a4`

## callees

- `0x180002d90`
- `0x180002ee0`
- `0x180004900`
- `0x180004950`
- `0x180004980`
- `0x180004a10`
- `0x18000d2a0`
- `0x180033de8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800031cc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003445`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800031cc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003445`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003166`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003208`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003166`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003110`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003140`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003140`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180003129`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180003129`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::ReportUsageToService(
        volatile signed __int32 *i,
        unsigned int a2,
        int a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        int a7,
        unsigned __int8 a8)
{
  unsigned int v8; // r15d
  volatile signed __int32 *v11; // rsi
  unsigned int v12; // r13d
  unsigned int v13; // ebx
  unsigned int v14; // r10d
  unsigned int v15; // eax
  unsigned int v16; // edx
  unsigned int v17; // r8d
  unsigned __int32 v18; // eax
  BOOL v19; // edi
  BOOL v20; // r12d
  DWORD LastError; // edi
  struct _TP_TIMER *ThreadpoolTimer; // rax
  signed __int32 v23; // r8d
  unsigned __int32 v24; // eax
  unsigned __int32 v25; // eax
  unsigned __int32 v26; // ett
  void *v27; // r9
  int v28; // ebx
  int v29; // edx
  unsigned int v30; // r8d
  int v31; // r13d
  int v32; // r8d
  wil *v33; // rcx
  unsigned int v34; // edx
  const char *v35; // [rsp+20h] [rbp-98h]
  unsigned __int64 v36; // [rsp+50h] [rbp-68h]
  __int128 v37; // [rsp+58h] [rbp-60h] BYREF
  _BOOL8 v38; // [rsp+68h] [rbp-50h]

  v8 = a4;
  v11 = i;
  if ( a7 )
  {
    v12 = a6;
    if ( a7 == 3 )
    {
      v13 = 6;
      if ( a6 )
        v13 = 2;
    }
    else
    {
      switch ( a7 )
      {
        case 0:
          goto LABEL_32;
        case 1:
          v13 = 0;
          if ( !a6 )
            v13 = 4;
          break;
        case 2:
          v13 = 1;
          if ( !a6 )
            v13 = 5;
          break;
        case 4:
          v13 = 3;
          if ( !a6 )
            v13 = 7;
          break;
        case 5:
          v13 = 8;
          if ( !a6 )
            v13 = 10;
          break;
        case 6:
          v13 = 9;
          if ( !a6 )
            v13 = 11;
          break;
        default:
          if ( (unsigned __int8)(a7 - 100) > 0x31u )
          {
LABEL_32:
            v13 = 255;
          }
          else
          {
            v28 = 100;
            if ( !a6 )
              v28 = 150;
            v13 = (unsigned __int8)(a7 - 100) + v28;
          }
          break;
      }
    }
    a8 = *(_BYTE *)(a5 + 4);
    v37 = 0;
    v38 = 0;
    if ( v13 == 4 )
    {
LABEL_6:
      i = (volatile signed __int32 *)*(unsigned int *)i;
      a4 = v13 == 4;
      HIDWORD(v36) = DWORD2(v37);
      while ( 1 )
      {
        v14 = 0;
        LODWORD(v36) = 0;
        v15 = (unsigned int)i | 1;
        if ( ((((unsigned int)i | 1) >> 14) & 1) != a4 )
        {
          if ( ((v15 >> 5) & 0x1FF) != 0 )
          {
            v31 = 0;
            if ( !v13 )
              v31 = 4;
            v14 = (v15 >> 5) & 0x1FF;
            v36 = __PAIR64__(v31, v14);
            v15 = (unsigned int)i & 0xFFFFC01E | 1;
          }
          v32 = 0;
          if ( v13 == 4 )
            v32 = 0x4000;
          v15 = v15 & 0xFFFFBFFF | v32;
        }
        v16 = (v15 >> 5) & 0x1FF;
        v17 = v16 + 1;
        if ( v16 + 1 > 0x1FF || v17 < v16 )
        {
          LOWORD(v17) = 1;
          v14 = (v15 >> 5) & 0x1FF;
          v36 = __PAIR64__(v13, v14);
        }
        v18 = _InterlockedCompareExchange(
                v11,
                v15 ^ ((unsigned __int16)v15 ^ (unsigned __int16)(32 * v17)) & 0x3FE0,
                (signed __int32)i);
        if ( (_DWORD)i == v18 )
          break;
        i = (volatile signed __int32 *)v18;
      }
      v19 = ((unsigned __int8)i & 1) == 0;
      v20 = 0;
      v12 = a6;
    }
    else
    {
      switch ( v13 )
      {
        case 0u:
          goto LABEL_6;
        case 1u:
        case 5u:
          wil_details_FeatureReporting_IncrementOpportunityInCache(i, v13, 2, &v37);
          v20 = v38;
          goto LABEL_80;
        case 2u:
        case 3u:
        case 6u:
        case 7u:
          v29 = 0;
          switch ( v13 )
          {
            case 2u:
              v29 = 2;
              break;
            case 3u:
              v29 = 8;
              break;
            case 6u:
              v29 = 4;
              break;
            case 7u:
              v29 = 16;
              break;
          }
          for ( i = (volatile signed __int32 *)*(unsigned int *)i; ; i = (volatile signed __int32 *)v24 )
          {
            v20 = ((unsigned int)i | v29) == (_DWORD)i;
            v23 = (unsigned int)i | v29 | 1;
            if ( ((unsigned int)i | v29) == (_DWORD)i )
              v23 = (unsigned int)i | v29;
            v24 = _InterlockedCompareExchange(v11, v23, (signed __int32)i);
            if ( (_DWORD)i == v24 )
              break;
          }
          LOBYTE(i) = ((unsigned __int8)i & 1) == 0;
          v19 = ((unsigned __int8)i & ((v23 & 1) != 0)) != 0;
          v14 = DWORD1(v37);
          v36 = *(_QWORD *)((char *)&v37 + 4);
          break;
        default:
          v30 = v13 - 320;
          if ( (int)(v13 - 320) >= 64 )
          {
            v20 = v38;
          }
          else
          {
            v25 = *((_DWORD *)i + 1);
            do
            {
              v20 = (v25 & 0x10) != 0 && ((v25 >> 5) & 0x3F) == v30;
              i = (volatile signed __int32 *)(v25 ^ ((unsigned __int16)v25 ^ (unsigned __int16)(32 * v30)) & 0x7E0 | 0x10);
              v26 = v25;
              v25 = _InterlockedCompareExchange(v11 + 1, (signed __int32)i, v25);
            }
            while ( v26 != v25 );
            if ( v20 )
            {
LABEL_80:
              v14 = DWORD1(v37);
              v36 = *(_QWORD *)((char *)&v37 + 4);
              v19 = v37;
              break;
            }
          }
          HIDWORD(v36) = v13;
          v14 = 1;
          LODWORD(v36) = 1;
          v19 = v37;
          break;
      }
    }
    if ( g_wil_details_RecordSRUMFeatureUsage )
    {
      i = (volatile signed __int32 *)(v13 - 100);
      if ( (unsigned int)i <= 0x31 || !v13 )
      {
        g_wil_details_RecordSRUMFeatureUsage(a2, v13, 1);
        v14 = v36;
      }
    }
    if ( v19 )
    {
      if ( wil::details::g_enabledStateManager && !wil::ProcessShutdownInProgress((wil *)i) )
      {
        AcquireSRWLockExclusive(&SRWLock);
        if ( wil::details::g_enabledStateManager )
        {
          if ( !wil::ProcessShutdownInProgress(v33) )
          {
            *(_QWORD *)&v37 = a2;
            *((_QWORD *)&v37 + 1) = v11;
            wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800ACD88, &v37, 0x10u);
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
              wil::details::EnsureCoalescedTimer_SetTimer(&qword_1800ACD78, &byte_1800ACD80, 300000);
            }
          }
        }
        ReleaseSRWLockExclusive(&SRWLock);
      }
      v14 = v36;
    }
    if ( v14 )
      wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, HIDWORD(v36), v14, a4, v35);
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
          v27);
      }
      ReleaseSRWLockExclusive(&SRWLock);
    }
    if ( a3 )
    {
      v34 = v13;
      if ( v8 )
        v34 = v13 | 0x80000000;
      wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v34, 0, a4, v35);
    }
    if ( !v20 )
    {
      if ( g_wil_details_realtimeFeatureUsageHook )
        g_wil_details_realtimeFeatureUsageHook(a2, v13, a8);
      if ( g_wil_details_pfnFeatureLoggingHook )
        g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, v12, &a7, 0, 0, 1);
    }
  }
}

```

## disassembly

```asm
0x180002ee0  push    rbx
0x180002ee2  push    rbp
0x180002ee3  push    rsi
0x180002ee4  push    rdi
0x180002ee5  push    r12
0x180002ee7  push    r13
0x180002ee9  push    r14
0x180002eeb  push    r15
0x180002eed  sub     rsp, 78h
0x180002ef1  mov     r15d, r9d
0x180002ef4  mov     ebp, r8d
0x180002ef7  mov     r14d, edx
0x180002efa  mov     rsi, rcx
0x180002efd  movsxd  r10, [rsp+0B8h+arg_30]
0x180002f05  test    r10d, r10d
0x180002f08  jz      loc_180003040
0x180002f0e  mov     edi, 4
0x180002f13  mov     r8d, 2
0x180002f19  mov     r13d, [rsp+0B8h+arg_28]
0x180002f21  lea     rdx, __ImageBase
0x180002f28  cmp     r10d, 3
0x180002f2c  jnz     loc_1800030E5
0x180002f32  mov     ebx, 6
0x180002f37  test    r13d, r13d
0x180002f3a  cmovnz  ebx, r8d
0x180002f3e  mov     rax, [rsp+0B8h+arg_20]
0x180002f46  movzx   eax, byte ptr [rax+4]
0x180002f4a  mov     [rsp+0B8h+arg_38], al
0x180002f51  xorps   xmm0, xmm0
0x180002f54  xor     eax, eax
0x180002f56  movups  [rsp+0B8h+var_60], xmm0
0x180002f5b  mov     [rsp+0B8h+var_50], rax
0x180002f60  cmp     ebx, edi
0x180002f62  jnz     loc_1800032D6
0x180002f68  mov     ecx, [rsi]; jumptable 00000001800032EC case 0
0x180002f6a  xor     r9d, r9d
0x180002f6d  cmp     ebx, edi
0x180002f6f  setz    r9b; unsigned int
0x180002f73  mov     r12d, 4000h
0x180002f79  mov     r11d, dword ptr [rsp+0B8h+var_60+8]
0x180002f7e  mov     dword ptr [rsp+0B8h+var_68+4], r11d
0x180002f83  xor     r10d, r10d
0x180002f86  mov     dword ptr [rsp+0B8h+var_68], r10d
0x180002f8b  mov     eax, ecx
0x180002f8d  or      eax, 1
0x180002f90  mov     edx, eax
0x180002f92  shr     edx, 0Eh
0x180002f95  and     edx, 1
0x180002f98  cmp     edx, r9d
0x180002f9b  jnz     loc_1800033DB
0x180002fa1  mov     edx, eax
0x180002fa3  shr     edx, 5
0x180002fa6  and     edx, 1FFh
0x180002fac  lea     r8d, [rdx+1]
0x180002fb0  cmp     r8d, 1FFh
0x180002fb7  ja      loc_18000341B
0x180002fbd  cmp     r8d, edx
0x180002fc0  jb      loc_18000341B
0x180002fc6  shl     r8d, 5
0x180002fca  xor     r8d, eax
0x180002fcd  and     r8d, 3FE0h
0x180002fd4  xor     r8d, eax
0x180002fd7  mov     eax, ecx
0x180002fd9  lock cmpxchg [rsi], r8d
0x180002fde  jnz     short loc_180003051
0x180002fe0  movzx   edi, cl
0x180002fe3  not     dil
0x180002fe6  and     edi, 1
0x180002fe9  xor     r12d, r12d
0x180002fec  mov     r13d, [rsp+0B8h+arg_28]
0x180002ff4  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x180002ffb  test    rax, rax
0x180002ffe  jnz     short loc_180003058
0x180003000  test    edi, edi
0x180003002  jz      short loc_180003017
0x180003004  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000300a  test    eax, eax
0x18000300c  jnz     loc_180003431
0x180003012  mov     r10d, dword ptr [rsp+0B8h+var_68]
0x180003017  test    r10d, r10d
0x18000301a  jnz     loc_18000346B
0x180003020  test    r12d, r12d
0x180003023  jnz     short loc_180003033
0x180003025  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000302b  test    eax, eax
0x18000302d  jnz     loc_1800031C5
0x180003033  test    ebp, ebp
0x180003035  jnz     loc_18000347F
0x18000303b  test    r12d, r12d
0x18000303e  jz      short loc_18000307B
0x180003040  add     rsp, 78h
0x180003044  pop     r15
0x180003046  pop     r14
0x180003048  pop     r13
0x18000304a  pop     r12
0x18000304c  pop     rdi
0x18000304d  pop     rsi
0x18000304e  pop     rbp
0x18000304f  pop     rbx
0x180003050  retn
0x180003051  mov     ecx, eax
0x180003053  jmp     loc_180002F83
0x180003058  lea     ecx, [rbx-64h]
0x18000305b  cmp     ecx, 31h ; '1'
0x18000305e  jbe     short loc_180003064
0x180003060  test    ebx, ebx
0x180003062  jnz     short loc_180003000
0x180003064  mov     r8d, 1
0x18000306a  mov     edx, ebx
0x18000306c  mov     ecx, r14d
0x18000306f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003074  mov     r10d, dword ptr [rsp+0B8h+var_68]
0x180003079  jmp     short loc_180003000
0x18000307b  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x180003082  test    rax, rax
0x180003085  jz      short loc_18000309A
0x180003087  movzx   r8d, [rsp+0B8h+arg_38]
0x180003090  mov     edx, ebx
0x180003092  mov     ecx, r14d
0x180003095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000309a  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800030a1  test    rax, rax
0x1800030a4  jz      short loc_180003040
0x1800030a6  mov     [rsp+0B8h+var_80], 1
0x1800030af  mov     [rsp+0B8h+var_88], 0
0x1800030b4  mov     [rsp+0B8h+var_90], 0
0x1800030bd  lea     rcx, [rsp+0B8h+arg_30]
0x1800030c5  mov     [rsp+0B8h+var_98], rcx
0x1800030ca  mov     r9d, r13d
0x1800030cd  xor     r8d, r8d
0x1800030d0  mov     rdx, [rsp+0B8h+arg_20]
0x1800030d8  mov     ecx, r14d
0x1800030db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030e0  jmp     loc_180003040
0x1800030e5  cmp     r10d, 6; switch 7 cases
0x1800030e9  ja      def_1800030FA; jumptable 00000001800030FA default case, case 3
0x1800030ef  mov     ecx, ds:(jpt_1800030FA - 180000000h)[rdx+r10*4]
0x1800030f7  add     rcx, rdx
0x1800030fa  jmp     rcx; switch jump
0x1800030fc  mov     ebx, 0FFh; jumptable 00000001800030FA case 0
0x180003101  jmp     loc_180002F3E
0x180003106  cmp     cs:qword_1800ACD78, 0
0x18000310e  jnz     short loc_180003146
0x180003110  call    cs:__imp_GetLastError
0x180003116  mov     edi, eax
0x180003118  xor     r8d, r8d; pcbe
0x18000311b  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x180003122  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180003129  call    cs:__imp_CreateThreadpoolTimer
0x18000312f  mov     rdx, rax
0x180003132  lea     rcx, qword_1800ACD78
0x180003139  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000313e  mov     ecx, edi; dwErrCode
0x180003140  call    cs:__imp_SetLastError
0x180003146  mov     r8d, 493E0h
0x18000314c  lea     rdx, byte_1800ACD80
0x180003153  lea     rcx, qword_1800ACD78
0x18000315a  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000315f  lea     rcx, SRWLock; SRWLock
0x180003166  call    cs:__imp_ReleaseSRWLockExclusive
0x18000316c  jmp     loc_180003012
0x180003171  mov     eax, edx
0x180003173  or      eax, ecx
0x180003175  xor     r12d, r12d
0x180003178  cmp     eax, ecx
0x18000317a  setz    r12b
0x18000317e  mov     r8d, eax
0x180003181  or      r8d, 1
0x180003185  test    r12d, r12d
0x180003188  cmovnz  r8d, eax
0x18000318c  mov     eax, ecx
0x18000318e  lock cmpxchg [rsi], r8d
0x180003193  jz      loc_180003322
0x180003199  mov     ecx, eax
0x18000319b  jmp     short loc_180003171
0x18000319d  mov     ecx, edx
0x18000319f  xor     ecx, eax
0x1800031a1  and     ecx, 7E0h
0x1800031a7  xor     ecx, eax
0x1800031a9  or      ecx, 10h
0x1800031ac  lock cmpxchg [rsi+4], ecx
0x1800031b1  jnz     loc_18000339A
0x1800031b7  test    r12d, r12d
0x1800031ba  jz      loc_1800033C3
0x1800031c0  jmp     loc_180003367
0x1800031c5  lea     rcx, SRWLock; SRWLock
0x1800031cc  call    cs:__imp_AcquireSRWLockExclusive
0x1800031d2  cmp     cs:qword_1800ACDD0, 0
0x1800031da  jnz     short loc_180003201
0x1800031dc  mov     cs:qword_1800ACDD0, 0
0x1800031e7  mov     r8, 0FFFFFFFFFFFFFFFFh; void (*)(void *)
0x1800031ee  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x1800031f5  lea     rcx, qword_1800ACDD0; this
0x1800031fc  call    ?WilApi_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details::WilApi_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x180003201  lea     rcx, SRWLock; SRWLock
0x180003208  call    cs:__imp_ReleaseSRWLockExclusive
0x18000320e  jmp     loc_180003033
0x180003213  mov     dword ptr [rsp+0B8h+var_60], r14d
0x180003218  xor     eax, eax
0x18000321a  mov     dword ptr [rsp+0B8h+var_60+4], eax
0x18000321e  mov     qword ptr [rsp+0B8h+var_60+8], rsi
0x180003223  mov     r8d, 10h; unsigned __int64
0x180003229  lea     rdx, [rsp+0B8h+var_60]; void *
0x18000322e  lea     rcx, qword_1800ACD88; this
0x180003235  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000323a  cmp     cs:byte_1800ACD80, 0
0x180003241  jnz     loc_18000315F
0x180003247  jmp     loc_180003106
0x18000324c  xor     ebx, ebx; jumptable 00000001800030FA case 1
0x18000324e  test    r13d, r13d
0x180003251  cmovz   ebx, edi
0x180003254  jmp     loc_180002F3E
0x180003259  mov     ebx, 1; jumptable 00000001800030FA case 2
0x18000325e  mov     eax, 5
0x180003263  test    r13d, r13d
0x180003266  cmovz   ebx, eax
0x180003269  jmp     loc_180002F3E
0x18000326e  mov     ebx, 3; jumptable 00000001800030FA case 4
0x180003273  mov     eax, 7
0x180003278  test    r13d, r13d
0x18000327b  cmovz   ebx, eax
0x18000327e  jmp     loc_180002F3E
0x180003283  mov     ebx, 8; jumptable 00000001800030FA case 5
0x180003288  mov     eax, 0Ah
0x18000328d  test    r13d, r13d
0x180003290  cmovz   ebx, eax
0x180003293  jmp     loc_180002F3E
0x180003298  mov     ebx, 9; jumptable 00000001800030FA case 6
0x18000329d  mov     eax, 0Bh
0x1800032a2  test    r13d, r13d
0x1800032a5  cmovz   ebx, eax
0x1800032a8  jmp     loc_180002F3E
0x1800032ad  sub     r10b, 64h ; 'd'; jumptable 00000001800030FA default case, case 3
0x1800032b1  cmp     r10b, 31h ; '1'
0x1800032b5  ja      loc_1800030FC; jumptable 00000001800030FA case 0
0x1800032bb  mov     ebx, 64h ; 'd'
0x1800032c0  mov     eax, 96h
0x1800032c5  test    r13d, r13d
0x1800032c8  cmovz   ebx, eax
0x1800032cb  movzx   eax, r10b
0x1800032cf  add     ebx, eax
0x1800032d1  jmp     loc_180002F3E
0x1800032d6  cmp     ebx, 7; switch 8 cases
0x1800032d9  ja      def_1800032EC; jumptable 00000001800032EC default case, case 4
0x1800032df  movsxd  rax, ebx
0x1800032e2  mov     ecx, ds:(jpt_1800032EC - 180000000h)[rdx+rax*4]
0x1800032e9  add     rcx, rdx
0x1800032ec  jmp     rcx; switch jump
0x1800032ee  xor     edx, edx; jumptable 00000001800032EC cases 2,3,6,7
0x1800032f0  mov     ecx, ebx
0x1800032f2  sub     ecx, r8d
0x1800032f5  jz      short loc_180003318
0x1800032f7  sub     ecx, 1
0x1800032fa  jz      short loc_180003311
0x1800032fc  sub     ecx, 3
0x1800032ff  jz      short loc_18000330D
0x180003301  cmp     ecx, 1
0x180003304  jnz     short loc_18000331B
0x180003306  mov     edx, 10h
0x18000330b  jmp     short loc_18000331B
0x18000330d  mov     edx, edi
0x18000330f  jmp     short loc_18000331B
0x180003311  mov     edx, 8
0x180003316  jmp     short loc_18000331B
0x180003318  mov     edx, r8d
0x18000331b  mov     ecx, [rsi]
0x18000331d  jmp     loc_180003171
0x180003322  test    cl, 1
0x180003325  setz    cl
0x180003328  test    r8b, 1
0x18000332c  setnz   al
0x18000332f  test    al, cl
0x180003331  mov     edi, 0
0x180003336  setnz   dil
0x18000333a  mov     r11d, dword ptr [rsp+0B8h+var_60+8]
0x18000333f  mov     dword ptr [rsp+0B8h+var_68+4], r11d
0x180003344  mov     r10d, dword ptr [rsp+0B8h+var_60+4]
0x180003349  mov     dword ptr [rsp+0B8h+var_68], r10d
0x18000334e  jmp     loc_180002FF4
0x180003353  lea     r9, [rsp+0B8h+var_60]; jumptable 00000001800032EC cases 1,5
0x180003358  mov     edx, ebx
0x18000335a  mov     rcx, rsi
0x18000335d  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180003362  mov     r12d, dword ptr [rsp+0B8h+var_50]
0x180003367  mov     r11d, dword ptr [rsp+0B8h+var_60+8]
0x18000336c  mov     dword ptr [rsp+0B8h+var_68+4], r11d
0x180003371  mov     r10d, dword ptr [rsp+0B8h+var_60+4]
0x180003376  mov     dword ptr [rsp+0B8h+var_68], r10d
0x18000337b  mov     edi, dword ptr [rsp+0B8h+var_60]
0x18000337f  jmp     loc_180002FF4
0x180003384  lea     r8d, [rbx-140h]; jumptable 00000001800032EC default case, case 4
0x18000338b  cmp     r8d, 40h ; '@'
0x18000338f  jge     short loc_1800033BE
0x180003391  mov     eax, [rsi+4]
0x180003394  mov     edx, r8d
0x180003397  shl     edx, 5
0x18000339a  test    al, 10h
0x18000339c  jz      short loc_1800033B6
0x18000339e  mov     ecx, eax
0x1800033a0  shr     ecx, 5
  ... truncated ...
```
