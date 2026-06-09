# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000da70`
- end: `0x18000df3c`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `1228`
- prototype: ``
- caller_count: `26`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d958`
- `0x18000d9e4`
- `0x18006847c`
- `0x1800687a4`
- `0x18007e27c`
- `0x18007e308`
- `0x18007e394`
- `0x18007e420`
- `0x180085750`
- `0x1800898cc`
- `0x18008be14`
- `0x18008dbe0`
- `0x18009095c`
- `0x1800af9c8`
- `0x1800b3d68`
- `0x1800bb814`
- `0x1800bb8a0`
- `0x1800bd720`
- `0x1800c2508`
- `0x1800c2594`
- `0x1800c262c`
- `0x1800ca748`
- `0x1800cc558`
- `0x1800d247c`
- `0x1800d88b0`
- `0x1800dcb20`

## callees

- `0x18000da70`
- `0x18000df44`
- `0x18000e550`
- `0x18000e594`
- `0x18000e5e8`
- `0x18000e618`
- `0x180030694`
- `0x18007aaf4`
- `0x180080b90`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dc27`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dc27`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000de2b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000de2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dc01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000dc01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dbd1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000dbea`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000dbea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportUsageToService(
        volatile signed __int32 *i,
        unsigned int a2,
        int a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        int a7,
        unsigned __int8 a8)
{
  __int64 v10; // r9
  volatile signed __int32 *v11; // rdi
  unsigned int v12; // ebx
  BOOL v13; // esi
  DWORD LastError; // edi
  PTP_TIMER ThreadpoolTimer; // rax
  signed __int32 v16; // r8d
  unsigned __int32 v17; // eax
  unsigned __int32 v18; // eax
  unsigned __int32 v19; // ett
  int v20; // ebx
  int v21; // edx
  unsigned int v22; // r8d
  wil *v23; // rcx
  unsigned int v24; // edx
  const char *v25; // [rsp+20h] [rbp-88h]
  _DWORD Src[2]; // [rsp+50h] [rbp-58h] BYREF
  volatile signed __int32 *v27; // [rsp+58h] [rbp-50h]
  unsigned int v28[4]; // [rsp+60h] [rbp-48h] BYREF
  _BOOL8 v29; // [rsp+70h] [rbp-38h]

  v10 = a2;
  v11 = i;
  if ( !a7 )
    return;
  if ( a7 == 3 )
  {
    v12 = 6;
    if ( a6 )
      v12 = 2;
  }
  else
  {
    switch ( a7 )
    {
      case 0:
        goto LABEL_22;
      case 1:
        v12 = 0;
        if ( !a6 )
          v12 = 4;
        break;
      case 2:
        v12 = 1;
        if ( !a6 )
          v12 = 5;
        break;
      case 4:
        v12 = 3;
        if ( !a6 )
          v12 = 7;
        break;
      case 5:
        v12 = 8;
        if ( !a6 )
          v12 = 10;
        break;
      case 6:
        v12 = 9;
        if ( !a6 )
          v12 = 11;
        break;
      default:
        if ( (unsigned __int8)(a7 - 100) > 0x31u )
        {
LABEL_22:
          v12 = 255;
        }
        else
        {
          v20 = 100;
          if ( !a6 )
            v20 = 150;
          v12 = (unsigned __int8)(a7 - 100) + v20;
        }
        break;
    }
  }
  a8 = *(_BYTE *)(a5 + 4);
  *(_OWORD *)v28 = 0;
  v29 = 0;
  if ( v12 == 4 )
  {
LABEL_6:
    wil_details_FeatureReporting_IncrementUsageInCache(i, v12, 2, v28);
LABEL_7:
    v10 = a2;
    v13 = v29;
    goto LABEL_8;
  }
  switch ( v12 )
  {
    case 0u:
      goto LABEL_6;
    case 1u:
    case 5u:
      wil_details_FeatureReporting_IncrementOpportunityInCache(i, v12, 2, v28);
      goto LABEL_7;
    case 2u:
    case 3u:
    case 6u:
    case 7u:
      v21 = 0;
      switch ( v12 )
      {
        case 2u:
          v21 = 2;
          break;
        case 3u:
          v21 = 8;
          break;
        case 6u:
          v21 = 4;
          break;
        case 7u:
          v21 = 16;
          break;
      }
      for ( i = (volatile signed __int32 *)*(unsigned int *)i; ; i = (volatile signed __int32 *)v17 )
      {
        v13 = ((unsigned int)i | v21) == (_DWORD)i;
        v16 = (unsigned int)i | v21 | 1;
        if ( ((unsigned int)i | v21) == (_DWORD)i )
          v16 = (unsigned int)i | v21;
        v17 = _InterlockedCompareExchange(v11, v16, (signed __int32)i);
        if ( (_DWORD)i == v17 )
          break;
      }
      v28[0] = (v16 & 1) != 0 && ((unsigned __int8)i & 1) == 0;
      goto LABEL_8;
    default:
      v22 = v12 - 320;
      if ( (int)(v12 - 320) >= 64 )
      {
        v13 = v29;
LABEL_74:
        v28[2] = v12;
        v28[1] = 1;
        goto LABEL_8;
      }
      v18 = *((_DWORD *)i + 1);
      do
      {
        v13 = (v18 & 0x10) != 0 && ((v18 >> 5) & 0x3F) == v22;
        i = (volatile signed __int32 *)(v18 ^ ((unsigned __int16)v18 ^ (unsigned __int16)(32 * v22)) & 0x7E0 | 0x10);
        v19 = v18;
        v18 = _InterlockedCompareExchange(v11 + 1, (signed __int32)i, v18);
      }
      while ( v19 != v18 );
      if ( !v13 )
        goto LABEL_74;
LABEL_8:
      if ( g_wil_details_RecordSRUMFeatureUsage )
      {
        i = (volatile signed __int32 *)(v12 - 100);
        if ( (unsigned int)i <= 0x31 || !v12 )
          g_wil_details_RecordSRUMFeatureUsage((unsigned int)v10, v12, 1);
      }
      if ( v28[0] && wil::details::g_enabledStateManager && !wil::ProcessShutdownInProgress((wil *)i) )
      {
        AcquireSRWLockExclusive(&SRWLock);
        if ( wil::details::g_enabledStateManager )
        {
          if ( !wil::ProcessShutdownInProgress(v23) )
          {
            Src[0] = a2;
            Src[1] = 0;
            v27 = v11;
            wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180140728, Src, 0x10u);
            if ( !byte_180140720 )
            {
              if ( !qword_180140718 )
              {
                LastError = GetLastError();
                ThreadpoolTimer = CreateThreadpoolTimer(
                                    _lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_,
                                    &wil::details::g_enabledStateManager,
                                    0);
                wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
                  &qword_180140718,
                  ThreadpoolTimer);
                SetLastError(LastError);
              }
              wil::details::EnsureCoalescedTimer_SetTimer(&qword_180140718, &byte_180140720, 300000);
            }
          }
        }
        ReleaseSRWLockExclusive(&SRWLock);
      }
      if ( v28[1] )
        wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v28[2], v28[1], v10, v25);
      if ( !v13 )
        wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
          (wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager,
          (void (*)(void *))_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_);
      if ( a3 )
      {
        v24 = v12 | 0x80000000;
        if ( !a4 )
          v24 = v12;
        wil::details::WilApi_RecordFeatureUsage((wil::details *)a2, v24, 0, v10, v25);
      }
      if ( !v13 )
      {
        if ( g_wil_details_realtimeFeatureUsageHook )
          g_wil_details_realtimeFeatureUsageHook(a2, v12, a8, v10);
        if ( g_wil_details_pfnFeatureLoggingHook )
          g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, 0, 1);
      }
      return;
  }
}

```

## disassembly

```asm
0x18000da70  mov     rax, rsp
0x18000da73  mov     [rax+8], rbx
0x18000da77  mov     [rax+18h], rsi
0x18000da7b  mov     [rax+10h], edx
0x18000da7e  push    rdi
0x18000da7f  push    r12
0x18000da81  push    r13
0x18000da83  push    r14
0x18000da85  push    r15
0x18000da87  sub     rsp, 80h
0x18000da8e  mov     r12d, r9d
0x18000da91  mov     r14d, r8d
0x18000da94  mov     r9d, edx
0x18000da97  mov     rdi, rcx
0x18000da9a  movsxd  r10, dword ptr [rax+38h]
0x18000da9e  test    r10d, r10d
0x18000daa1  jz      loc_18000DB6B
0x18000daa7  mov     r11d, 4
0x18000daad  mov     r8d, 2
0x18000dab3  mov     r15d, [rsp+0A8h+arg_28]
0x18000dabb  lea     rdx, __ImageBase
0x18000dac2  cmp     r10d, 3
0x18000dac6  jnz     loc_18000DBA6
0x18000dacc  mov     ebx, 6
0x18000dad1  test    r15d, r15d
0x18000dad4  cmovnz  ebx, r8d
0x18000dad8  mov     r13, [rsp+0A8h+arg_20]
0x18000dae0  movzx   eax, byte ptr [r13+4]
0x18000dae5  mov     [rsp+0A8h+arg_38], al
0x18000daec  xorps   xmm0, xmm0
0x18000daef  xor     eax, eax
0x18000daf1  movups  xmmword ptr [rsp+0A8h+var_48], xmm0
0x18000daf6  mov     [rsp+0A8h+var_38], rax
0x18000dafb  cmp     ebx, r11d
0x18000dafe  jnz     loc_18000DD4D
0x18000db04  lea     r9, [rsp+0A8h+var_48]; jumptable 000000018000DD5F case 0
0x18000db09  mov     edx, ebx
0x18000db0b  mov     rcx, rdi
0x18000db0e  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18000db13  mov     r9d, dword ptr [rsp+0A8h+arg_8]; unsigned int
0x18000db1b  mov     esi, dword ptr [rsp+0A8h+var_38]
0x18000db1f  mov     rax, cs:g_wil_details_RecordSRUMFeatureUsage
0x18000db26  test    rax, rax
0x18000db29  jnz     short loc_18000DB88
0x18000db2b  cmp     [rsp+0A8h+var_48], 0
0x18000db30  jz      short loc_18000DB40
0x18000db32  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000db38  test    eax, eax
0x18000db3a  jnz     loc_18000DE17
0x18000db40  mov     edi, dword ptr [rsp+0A8h+arg_8]
0x18000db47  cmp     [rsp+0A8h+var_48+4], 0
0x18000db4c  ja      loc_18000DE51
0x18000db52  test    esi, esi
0x18000db54  jz      loc_18000DE66
0x18000db5a  test    r14d, r14d
0x18000db5d  jnz     loc_18000DE7E
0x18000db63  test    esi, esi
0x18000db65  jz      loc_18000DE99
0x18000db6b  lea     r11, [rsp+0A8h+var_28]
0x18000db73  mov     rbx, [r11+30h]
0x18000db77  mov     rsi, [r11+40h]
0x18000db7b  mov     rsp, r11
0x18000db7e  pop     r15
0x18000db80  pop     r14
0x18000db82  pop     r13
0x18000db84  pop     r12
0x18000db86  pop     rdi
0x18000db87  retn
0x18000db88  lea     ecx, [rbx-64h]
0x18000db8b  cmp     ecx, 31h ; '1'
0x18000db8e  jbe     short loc_18000DB94
0x18000db90  test    ebx, ebx
0x18000db92  jnz     short loc_18000DB2B
0x18000db94  mov     r8d, 1
0x18000db9a  mov     edx, ebx
0x18000db9c  mov     ecx, r9d
0x18000db9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dba4  jmp     short loc_18000DB2B
0x18000dba6  cmp     r10d, 6; switch 7 cases
0x18000dbaa  ja      def_18000DBBB; jumptable 000000018000DBBB default case, case 3
0x18000dbb0  mov     ecx, ds:(jpt_18000DBBB - 180000000h)[rdx+r10*4]
0x18000dbb8  add     rcx, rdx
0x18000dbbb  jmp     rcx; switch jump
0x18000dbbd  mov     ebx, 0FFh; jumptable 000000018000DBBB case 0
0x18000dbc2  jmp     loc_18000DAD8
0x18000dbc7  cmp     cs:qword_180140718, 0
0x18000dbcf  jnz     short loc_18000DC07
0x18000dbd1  call    cs:__imp_GetLastError
0x18000dbd7  mov     edi, eax
0x18000dbd9  xor     r8d, r8d; pcbe
0x18000dbdc  lea     rdx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000dbe3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000dbea  call    cs:__imp_CreateThreadpoolTimer
0x18000dbf0  mov     rdx, rax
0x18000dbf3  lea     rcx, qword_180140718
0x18000dbfa  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000dbff  mov     ecx, edi; dwErrCode
0x18000dc01  call    cs:__imp_SetLastError
0x18000dc07  mov     r8d, 493E0h
0x18000dc0d  lea     rdx, byte_180140720
0x18000dc14  lea     rcx, qword_180140718
0x18000dc1b  call    ?EnsureCoalescedTimer_SetTimer@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@AEA_N_J@Z; wil::details::EnsureCoalescedTimer_SetTimer(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> &,bool &,__int64)
0x18000dc20  lea     rcx, SRWLock; SRWLock
0x18000dc27  call    cs:__imp_ReleaseSRWLockExclusive
0x18000dc2d  jmp     loc_18000DB40
0x18000dc32  mov     eax, edx
0x18000dc34  or      eax, ecx
0x18000dc36  xor     esi, esi
0x18000dc38  cmp     eax, ecx
0x18000dc3a  setz    sil
0x18000dc3e  mov     r8d, eax
0x18000dc41  or      r8d, 1
0x18000dc45  test    esi, esi
0x18000dc47  cmovnz  r8d, eax
0x18000dc4b  mov     eax, ecx
0x18000dc4d  lock cmpxchg [rdi], r8d
0x18000dc52  jz      loc_18000DD96
0x18000dc58  mov     ecx, eax
0x18000dc5a  jmp     short loc_18000DC32
0x18000dc5c  mov     ecx, edx
0x18000dc5e  xor     ecx, eax
0x18000dc60  and     ecx, 7E0h
0x18000dc66  xor     ecx, eax
0x18000dc68  or      ecx, 10h
0x18000dc6b  lock cmpxchg [rdi+4], ecx
0x18000dc70  jnz     loc_18000DDE0
0x18000dc76  test    esi, esi
0x18000dc78  jz      loc_18000DE06
0x18000dc7e  jmp     loc_18000DB1F
0x18000dc83  mov     eax, dword ptr [rsp+0A8h+arg_8]
0x18000dc8a  mov     [rsp+0A8h+Src], eax
0x18000dc8e  xor     eax, eax
0x18000dc90  mov     [rsp+0A8h+var_54], eax
0x18000dc94  mov     [rsp+0A8h+var_50], rdi
0x18000dc99  mov     r8d, 10h; Size
0x18000dc9f  lea     rdx, [rsp+0A8h+Src]; Src
0x18000dca4  lea     rcx, qword_180140728; this
0x18000dcab  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000dcb0  cmp     cs:byte_180140720, 0
0x18000dcb7  jnz     loc_18000DC20
0x18000dcbd  jmp     loc_18000DBC7
0x18000dcc2  xor     ebx, ebx; jumptable 000000018000DBBB case 1
0x18000dcc4  test    r15d, r15d
0x18000dcc7  cmovz   ebx, r11d
0x18000dccb  jmp     loc_18000DAD8
0x18000dcd0  mov     ebx, 1; jumptable 000000018000DBBB case 2
0x18000dcd5  mov     eax, 5
0x18000dcda  test    r15d, r15d
0x18000dcdd  cmovz   ebx, eax
0x18000dce0  jmp     loc_18000DAD8
0x18000dce5  mov     ebx, 3; jumptable 000000018000DBBB case 4
0x18000dcea  mov     eax, 7
0x18000dcef  test    r15d, r15d
0x18000dcf2  cmovz   ebx, eax
0x18000dcf5  jmp     loc_18000DAD8
0x18000dcfa  mov     ebx, 8; jumptable 000000018000DBBB case 5
0x18000dcff  mov     eax, 0Ah
0x18000dd04  test    r15d, r15d
0x18000dd07  cmovz   ebx, eax
0x18000dd0a  jmp     loc_18000DAD8
0x18000dd0f  mov     ebx, 9; jumptable 000000018000DBBB case 6
0x18000dd14  mov     eax, 0Bh
0x18000dd19  test    r15d, r15d
0x18000dd1c  cmovz   ebx, eax
0x18000dd1f  jmp     loc_18000DAD8
0x18000dd24  sub     r10b, 64h ; 'd'; jumptable 000000018000DBBB default case, case 3
0x18000dd28  cmp     r10b, 31h ; '1'
0x18000dd2c  ja      loc_18000DBBD; jumptable 000000018000DBBB case 0
0x18000dd32  mov     ebx, 64h ; 'd'
0x18000dd37  mov     eax, 96h
0x18000dd3c  test    r15d, r15d
0x18000dd3f  cmovz   ebx, eax
0x18000dd42  movzx   eax, r10b
0x18000dd46  add     ebx, eax
0x18000dd48  jmp     loc_18000DAD8
0x18000dd4d  cmp     ebx, 7; switch 8 cases
0x18000dd50  ja      short def_18000DD5F; jumptable 000000018000DD5F default case, case 4
0x18000dd52  movsxd  rax, ebx
0x18000dd55  mov     ecx, ds:(jpt_18000DD5F - 180000000h)[rdx+rax*4]
0x18000dd5c  add     rcx, rdx
0x18000dd5f  jmp     rcx; switch jump
0x18000dd61  xor     edx, edx; jumptable 000000018000DD5F cases 2,3,6,7
0x18000dd63  mov     ecx, ebx
0x18000dd65  sub     ecx, r8d
0x18000dd68  jz      short loc_18000DD8C
0x18000dd6a  sub     ecx, 1
0x18000dd6d  jz      short loc_18000DD85
0x18000dd6f  sub     ecx, 3
0x18000dd72  jz      short loc_18000DD80
0x18000dd74  cmp     ecx, 1
0x18000dd77  jnz     short loc_18000DD8F
0x18000dd79  mov     edx, 10h
0x18000dd7e  jmp     short loc_18000DD8F
0x18000dd80  mov     edx, r11d
0x18000dd83  jmp     short loc_18000DD8F
0x18000dd85  mov     edx, 8
0x18000dd8a  jmp     short loc_18000DD8F
0x18000dd8c  mov     edx, r8d
0x18000dd8f  mov     ecx, [rdi]
0x18000dd91  jmp     loc_18000DC32
0x18000dd96  test    r8b, 1
0x18000dd9a  setnz   dl
0x18000dd9d  test    cl, 1
0x18000dda0  setz    al
0x18000dda3  test    al, dl
0x18000dda5  mov     eax, 0
0x18000ddaa  setnz   al
0x18000ddad  mov     [rsp+0A8h+var_48], eax
0x18000ddb1  jmp     loc_18000DB1F
0x18000ddb6  lea     r9, [rsp+0A8h+var_48]; jumptable 000000018000DD5F cases 1,5
0x18000ddbb  mov     edx, ebx
0x18000ddbd  mov     rcx, rdi
0x18000ddc0  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18000ddc5  jmp     loc_18000DB13
0x18000ddca  lea     r8d, [rbx-140h]; jumptable 000000018000DD5F default case, case 4
0x18000ddd1  cmp     r8d, 40h ; '@'
0x18000ddd5  jge     short loc_18000DE02
0x18000ddd7  mov     eax, [rdi+4]
0x18000ddda  mov     edx, r8d
0x18000dddd  shl     edx, 5
0x18000dde0  test    al, 10h
0x18000dde2  jz      short loc_18000DDFB
0x18000dde4  mov     ecx, eax
0x18000dde6  shr     ecx, 5
0x18000dde9  and     ecx, 3Fh
0x18000ddec  cmp     ecx, r8d
0x18000ddef  jnz     short loc_18000DDFB
0x18000ddf1  mov     esi, 1
0x18000ddf6  jmp     loc_18000DC5C
0x18000ddfb  xor     esi, esi
0x18000ddfd  jmp     loc_18000DC5C
0x18000de02  mov     esi, dword ptr [rsp+0A8h+var_38]
0x18000de06  mov     [rsp+0A8h+var_48+8], ebx
0x18000de0a  mov     [rsp+0A8h+var_48+4], 1
0x18000de12  jmp     loc_18000DB1F
0x18000de17  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000de1c  test    al, al
0x18000de1e  jnz     loc_18000DB40
0x18000de24  lea     rcx, SRWLock; SRWLock
0x18000de2b  call    cs:__imp_AcquireSRWLockExclusive
0x18000de31  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000de37  test    eax, eax
0x18000de39  jz      loc_18000DC20
0x18000de3f  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18000de44  test    al, al
0x18000de46  jnz     loc_18000DC20
0x18000de4c  jmp     loc_18000DC83
0x18000de51  mov     r8d, [rsp+0A8h+var_48+4]; unsigned int
0x18000de56  mov     edx, [rsp+0A8h+var_48+8]; unsigned int
0x18000de5a  mov     ecx, edi; this
0x18000de5c  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000de61  jmp     loc_18000DB52
0x18000de66  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x18000de6d  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000de74  call    ?EnsureSubscribedToUsageFlush@EnabledStateManager@details@wil@@QEAAXP6AXPEAX@Z@Z; wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(void (*)(void *))
0x18000de79  jmp     loc_18000DB5A
0x18000de7e  mov     edx, ebx
0x18000de80  bts     edx, 1Fh
0x18000de84  test    r12d, r12d
0x18000de87  cmovz   edx, ebx; unsigned int
0x18000de8a  xor     r8d, r8d; unsigned int
0x18000de8d  mov     ecx, edi; this
0x18000de8f  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000de94  jmp     loc_18000DB63
0x18000de99  mov     rax, cs:g_wil_details_realtimeFeatureUsageHook
0x18000dea0  test    rax, rax
0x18000dea3  jz      short loc_18000DEB7
0x18000dea5  movzx   r8d, [rsp+0A8h+arg_38]
0x18000deae  mov     edx, ebx
0x18000deb0  mov     ecx, edi
0x18000deb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000deb7  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000debe  test    rax, rax
0x18000dec1  jz      loc_18000DB6B
0x18000dec7  mov     [rsp+0A8h+var_70], 1
0x18000ded0  mov     [rsp+0A8h+var_78], 0
0x18000ded5  mov     [rsp+0A8h+var_80], 0
0x18000dede  lea     rcx, [rsp+0A8h+arg_30]
0x18000dee6  mov     [rsp+0A8h+var_88], rcx
0x18000deeb  mov     r9d, r15d
0x18000deee  xor     r8d, r8d
0x18000def1  mov     rdx, r13
0x18000def4  mov     ecx, edi
0x18000def6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000defb  jmp     loc_18000DB6B
```
