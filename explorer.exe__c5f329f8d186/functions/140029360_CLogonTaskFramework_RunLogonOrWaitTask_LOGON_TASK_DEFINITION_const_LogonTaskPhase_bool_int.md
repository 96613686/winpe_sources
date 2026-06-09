# CLogonTaskFramework::_RunLogonOrWaitTask(LOGON_TASK_DEFINITION const &,LogonTaskPhase,bool,int)

- ea: `0x140029360`
- end: `0x140029b79`
- name: `?_RunLogonOrWaitTask@CLogonTaskFramework@@AEAAXAEBULOGON_TASK_DEFINITION@@W4LogonTaskPhase@@_NH@Z`
- size: `2073`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000b0e4`

## callees

- `0x14000ba70`
- `0x14000e0d0`
- `0x14001cfa0`
- `0x14001d364`
- `0x140029360`
- `0x140029b80`
- `0x140029bcc`
- `0x140029f20`
- `0x14002a0dc`
- `0x14002a32c`
- `0x14002a840`
- `0x14002a9f8`
- `0x14002ac38`
- `0x14002af70`
- `0x14002afa4`
- `0x14007dc78`
- `0x1400954c8`
- `0x1400955ec`
- `0x1400957a8`
- `0x1400a8d78`
- `0x1400b0050`
- `0x1400b2920`
- `0x1400b8c7c`
- `0x14010e160`
- `0x14010e520`
- `0x14010ed78`
- `0x1401431b4`
- `0x1401b0654`
- `0x1401d9010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400299c9`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400299c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400295ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140029a5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400295ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140029a5d`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x14002960e`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x14002960e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002980b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002980b`

## string_xrefs

- `0x14002982d`: `LogonTask`
- `0x14002984e`: `LogonTask_Critical`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CLogonTaskFramework::_RunLogonOrWaitTask(__int64 a1, _QWORD *a2, char a3, char a4, int a5)
{
  unsigned __int8 v6; // r13
  _WORD *v9; // rsi
  unsigned __int64 v10; // rbx
  size_t v11; // rbx
  int v12; // eax
  char v13; // al
  char v14; // cl
  __int64 result; // rax
  char v16; // al
  char v17; // cl
  signed __int32 i; // eax
  volatile signed __int32 *v19; // r12
  signed __int32 j; // eax
  __int128 v21; // xmm6
  __int128 v22; // xmm7
  __int128 v23; // xmm8
  __int64 v24; // xmm9_8
  char *v25; // rax
  char *v26; // rbx
  DWORD v27; // eax
  signed __int32 k; // edx
  signed __int32 m; // edx
  __int64 v30; // r13
  size_t v31; // rbx
  CLogonTaskFramework *v32; // rcx
  bool ShouldLogCriticalTelemetryForTask; // r12
  __int64 v34; // rcx
  int v35; // r8d
  unsigned int v36; // r12d
  DWORD CurrentThreadId; // r8d
  __int64 v38; // r9
  int v39; // eax
  bool v41; // [rsp+49h] [rbp-BFh]
  DWORD v42; // [rsp+50h] [rbp-B8h]
  __int128 v43; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 v44; // [rsp+68h] [rbp-A0h]
  __int64 v45; // [rsp+70h] [rbp-98h]
  __int64 v46; // [rsp+78h] [rbp-90h]
  char v47; // [rsp+80h] [rbp-88h]
  char v48; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v49[42]; // [rsp+D8h] [rbp-30h] BYREF
  _QWORD v50[42]; // [rsp+228h] [rbp+120h] BYREF

  v6 = a3;
  _InterlockedExchange((volatile __int32 *)(a1 + 544), *((_DWORD *)a2 + 6));
  v46 = a1;
  v47 = 1;
  v9 = (_WORD *)*a2;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v10 = -1;
  do
    ++v10;
  while ( v9[v10] );
  if ( v10 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v10 > 7 )
  {
    v30 = std::wstring::_Calculate_growth(v10, 7);
    if ( (unsigned __int64)(v30 + 1) > 0x7FFFFFFFFFFFFFFFLL )
      std::_Throw_bad_array_new_length();
    *(_QWORD *)&v43 = std::_Allocate<16,std::_Default_allocate_traits>(2 * (v30 + 1));
    v44 = v10;
    v45 = v30;
    v31 = 2 * v10;
    memcpy_0((void *)v43, v9, v31);
    *(_WORD *)(v31 + v43) = 0;
    v6 = a3;
  }
  else
  {
    v44 = v10;
    v45 = 7;
    v11 = 2 * v10;
    memcpy_0(&v43, v9, v11);
    *(_WORD *)((char *)&v43 + v11) = 0;
  }
  LogonTaskDurationsTest::StartLogonTask(a1 + 600, *((unsigned int *)a2 + 6), &v43);
  if ( a4 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58790537>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID58790537>::GetImpl'::`2'::impl)
      && (*(_DWORD *)(a1 + 216) & 0x400000) != 0 )
    {
      v13 = *((_BYTE *)a2 + 49);
      v14 = *((_BYTE *)a2 + 51);
    }
    else
    {
      v12 = *(_DWORD *)(a1 + 216);
      if ( (v12 & 0x80000) != 0 )
      {
        v13 = *((_BYTE *)a2 + 46);
        v14 = *((_BYTE *)a2 + 48);
      }
      else if ( (v12 & 0x800) != 0 )
      {
        v13 = *((_BYTE *)a2 + 40);
        v14 = *((_BYTE *)a2 + 42);
      }
      else if ( (v12 & 0x40000) != 0 )
      {
        v13 = *((_BYTE *)a2 + 43);
        v14 = *((_BYTE *)a2 + 45);
      }
      else if ( (v12 & 8) != 0 )
      {
        v13 = *((_BYTE *)a2 + 37);
        v14 = *((_BYTE *)a2 + 39);
      }
      else if ( (v12 & 1) != 0 )
      {
        if ( (v12 & 0x10) != 0 )
        {
          v13 = *((_BYTE *)a2 + 31);
          v14 = *((_BYTE *)a2 + 33);
        }
        else
        {
          v13 = *((_BYTE *)a2 + 28);
          v14 = *((_BYTE *)a2 + 30);
        }
      }
      else
      {
        v13 = *((_BYTE *)a2 + 34);
        v14 = *((_BYTE *)a2 + 36);
      }
    }
    if ( v13 && v14 == v6 && a2[2] )
    {
      CurrentThreadId = GetCurrentThreadId();
      v42 = CurrentThreadId;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_DDSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, CurrentThreadId, CurrentThreadId, CurrentThreadId, *a2, v6);
      LogonTaskBlackBox::RecordEventTime(a1 + 488, (unsigned int)a5, 12);
      if ( a5 >= 0 && *(_QWORD *)(a1 + 536) )
        *(_DWORD *)(*(_QWORD *)(a1 + 536) + 24LL * a5 + 16) = GetTickCount();
      wil::ActivityBase<LogonFrameworkLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonFrameworkLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
        v50,
        "LogonTask");
      v50[0] = &LogonFrameworkTelemetry::LogonTask::`vftable';
      wil::ActivityBase<LogonFrameworkLogging,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonFrameworkLogging,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        v49,
        "LogonTask_Critical");
      v49[0] = &LogonFrameworkTelemetry::LogonTask_Critical::`vftable';
      ShouldLogCriticalTelemetryForTask = CLogonTaskFramework::_ShouldLogCriticalTelemetryForTask(
                                            v32,
                                            (const unsigned __int16 *)*a2);
      v41 = ShouldLogCriticalTelemetryForTask;
      if ( *(_BYTE *)(a1 + 237) )
      {
        if ( a3 != 6 )
          wil::ActivityBase<LogonFrameworkLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivity<LogonFrameworkTelemetry::AllLogonTasks>(
            v50,
            a1 + 624);
        LogonFrameworkTelemetry::LogonTask::StartActivity(
          (LogonFrameworkTelemetry::LogonTask *)v50,
          (const unsigned __int16 *)*a2,
          1,
          1);
      }
      if ( ShouldLogCriticalTelemetryForTask )
      {
        if ( a3 != 6 )
          wil::ActivityBase<LogonFrameworkLogging,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivity<LogonFrameworkTelemetry::AllLogonTasks>(
            v49,
            a1 + 624);
        LogonFrameworkTelemetry::LogonTask_Critical::StartActivity(
          (LogonFrameworkTelemetry::LogonTask_Critical *)v49,
          (const unsigned __int16 *)*a2,
          1,
          1);
      }
      v36 = ((__int64 (__fastcall *)(__int64, _QWORD *))a2[2])(a1, v50);
      if ( (byte_14024FCC4 & 8) != 0 )
        McTemplateU0qz_EventWriteTransfer(v34, LogonPerformance_TaskRunTime_Stop, *(unsigned int *)(a1 + 216), *a2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_DDSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v35, v42, v42, *a2, a3);
      if ( v41 )
        wil::ActivityBase<LogonFrameworkLogging,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
          v49,
          v36);
      if ( *(_BYTE *)(a1 + 237) )
        wil::ActivityBase<LogonFrameworkLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
          v50,
          v36);
      LogonTaskBlackBox::TaskWaited((LogonTaskBlackBox *)(a1 + 488), a5);
      v49[0] = &LogonFrameworkTelemetry::LogonTask_Critical::`vftable';
      wil::ActivityBase<LogonFrameworkLogging,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v49);
      wil::ActivityBase<LogonFrameworkLogging,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonFrameworkLogging,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v49);
      LogonFrameworkTelemetry::LogonTask::~LogonTask((LogonFrameworkTelemetry::LogonTask *)v50);
    }
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58790537>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID58790537>::GetImpl'::`2'::impl)
      && (*(_DWORD *)(a1 + 216) & 0x400000) != 0 )
    {
      v16 = *((_BYTE *)a2 + 49);
      v17 = *((_BYTE *)a2 + 50);
    }
    else
    {
      v39 = *(_DWORD *)(a1 + 216);
      if ( (v39 & 0x80000) != 0 )
      {
        v16 = *((_BYTE *)a2 + 46);
        v17 = *((_BYTE *)a2 + 47);
      }
      else if ( (v39 & 0x800) != 0 )
      {
        v16 = *((_BYTE *)a2 + 40);
        v17 = *((_BYTE *)a2 + 41);
      }
      else if ( (v39 & 0x40000) != 0 )
      {
        v16 = *((_BYTE *)a2 + 43);
        v17 = *((_BYTE *)a2 + 44);
      }
      else if ( (v39 & 8) != 0 )
      {
        v16 = *((_BYTE *)a2 + 37);
        v17 = *((_BYTE *)a2 + 38);
      }
      else if ( (v39 & 1) != 0 )
      {
        if ( (v39 & 0x10) != 0 )
        {
          v16 = *((_BYTE *)a2 + 31);
          v17 = *((_BYTE *)a2 + 32);
        }
        else
        {
          v16 = *((_BYTE *)a2 + 28);
          v17 = *((_BYTE *)a2 + 29);
        }
      }
      else
      {
        v16 = *((_BYTE *)a2 + 34);
        v17 = *((_BYTE *)a2 + 35);
      }
    }
    if ( v16 && v17 == v6 && a2[1] )
    {
      if ( v16 == 1 )
      {
        LOBYTE(v38) = v6 != 6;
        CLogonTaskFramework::_ExecuteTaskFunction(a1, a2, v6, v38, a5);
      }
      else
      {
        for ( i = *(_DWORD *)(a1 + 12); i != 0x7FFFFFFF; i = *(_DWORD *)(a1 + 12) )
        {
          if ( i == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 12), i + 1, i) )
            break;
        }
        v19 = (volatile signed __int32 *)a1;
        for ( j = *(_DWORD *)(a1 + 12); j != 0x7FFFFFFF; j = *(_DWORD *)(a1 + 12) )
        {
          if ( j == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 12), j + 1, j) )
            break;
        }
        v21 = *(_OWORD *)a2;
        v22 = *((_OWORD *)a2 + 1);
        v23 = *((_OWORD *)a2 + 2);
        v24 = a2[6];
        v25 = (char *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
        v26 = v25;
        if ( v25 )
        {
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IImmersiveApplication>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IImmersiveApplication>(v25);
          *(_QWORD *)v26 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable';
          if ( Microsoft::WRL::Details::ModuleBase::module_ )
            (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                 + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
          *((_QWORD *)v26 + 2) = 0;
          if ( v26 + 16 != &v48 )
          {
            *((_QWORD *)v26 + 2) = a1;
            v19 = 0;
          }
          *(_OWORD *)(v26 + 24) = v21;
          *(_OWORD *)(v26 + 40) = v22;
          *(_OWORD *)(v26 + 56) = v23;
          *((_QWORD *)v26 + 9) = v24;
          v26[80] = v6;
          *((_DWORD *)v26 + 21) = a5;
          *(_QWORD *)v26 = &Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_6803cedb9cee91ceb5d38b0568067134_>::`vftable';
        }
        else
        {
          v26 = 0;
        }
        v27 = GetCurrentThreadId();
        SHTaskPoolQueueTask(1, 0, v27, 0, v26, 0);
        if ( v26 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v26 + 16LL))(v26);
        if ( v19 )
        {
          for ( k = *((_DWORD *)v19 + 3); k != 0x7FFFFFFF; k = *((_DWORD *)v19 + 3) )
          {
            if ( k == _InterlockedCompareExchange(v19 + 3, k - 1, k) )
              break;
          }
          if ( k == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v19 + 32LL))(v19, 1);
            if ( Microsoft::WRL::Details::ModuleBase::module_ )
              (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                   + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
          }
        }
        for ( m = *(_DWORD *)(a1 + 12); m != 0x7FFFFFFF; m = *(_DWORD *)(a1 + 12) )
        {
          if ( m == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 12), m - 1, m) )
            break;
        }
        if ( m == 1 )
        {
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 32LL))(a1, 1);
          if ( Microsoft::WRL::Details::ModuleBase::module_ )
            (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                 + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
        }
      }
    }
  }
  result = LogonTaskDurationsTest::CompleteLogonTask(a1 + 600, *((unsigned int *)a2 + 6));
  _InterlockedExchange((volatile __int32 *)(a1 + 544), 1);
  return result;
}

```

## disassembly

```asm
0x140029360  mov     rax, rsp
0x140029363  mov     [rax+18h], rbx
0x140029367  push    rbp
0x140029368  push    rsi
0x140029369  push    rdi
0x14002936a  push    r12
0x14002936c  push    r13
0x14002936e  push    r14
0x140029370  push    r15
0x140029372  lea     rbp, [rax-2F8h]
0x140029379  sub     rsp, 3C0h
0x140029380  movaps  xmmword ptr [rax-48h], xmm6
0x140029384  movaps  xmmword ptr [rax-58h], xmm7
0x140029388  movaps  xmmword ptr [rax-68h], xmm8
0x14002938d  movaps  xmmword ptr [rax-78h], xmm9
0x140029392  mov     rax, cs:__security_cookie
0x140029399  xor     rax, rsp
0x14002939c  mov     [rbp+2F0h+var_80], rax
0x1400293a3  movzx   r12d, r9b
0x1400293a7  movzx   r13d, r8b
0x1400293ab  mov     [rsp+3F0h+var_3B0], r8b
0x1400293b0  mov     r15, rdx
0x1400293b3  mov     r14, rcx
0x1400293b6  mov     eax, [rdx+18h]
0x1400293b9  xchg    eax, [rcx+220h]
0x1400293bf  mov     [rsp+3F0h+var_380], rcx
0x1400293c4  mov     [rsp+3F0h+var_378], 1
0x1400293c9  mov     rsi, [rdx]
0x1400293cc  xorps   xmm0, xmm0
0x1400293cf  movups  [rsp+3F0h+var_3A8+8], xmm0
0x1400293d4  xor     edi, edi
0x1400293d6  mov     [rsp+3F0h+var_390], rdi
0x1400293db  mov     [rsp+3F0h+var_388], rdi
0x1400293e0  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1400293e7  inc     rbx
0x1400293ea  cmp     [rsi+rbx*2], di
0x1400293ee  jnz     short loc_1400293E7
0x1400293f0  mov     r8, 7FFFFFFFFFFFFFFEh
0x1400293fa  cmp     rbx, r8
0x1400293fd  ja      loc_1400299C2
0x140029403  cmp     rbx, 7
0x140029407  ja      loc_14002977B
0x14002940d  mov     [rsp+3F0h+var_390], rbx
0x140029412  mov     [rsp+3F0h+var_388], 7
0x14002941b  add     rbx, rbx
0x14002941e  mov     r8, rbx; Size
0x140029421  mov     rdx, rsi; Src
0x140029424  lea     rcx, [rsp+3F0h+var_3A8+8]; void *
0x140029429  call    memcpy_0
0x14002942e  mov     word ptr [rsp+rbx+3F0h+var_3A8+8], di
0x140029433  lea     r8, [rsp+3F0h+var_3A8+8]
0x140029438  mov     edx, [r15+18h]
0x14002943c  lea     rcx, [r14+258h]
0x140029443  call    ?StartLogonTask@LogonTaskDurationsTest@@QEAAXW4LogonTaskId@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LogonTaskDurationsTest::StartLogonTask(LogonTaskId,std::wstring)
0x140029448  mov     edi, 1
0x14002944d  test    r12b, r12b
0x140029450  jz      loc_140029ABD
0x140029456  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID58790537@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID58790537@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58790537> `wil::Feature<__WilFeatureTraits_Feature_ID58790537>::GetImpl(void)'::`2'::impl
0x14002945d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID58790537@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58790537>::__private_IsEnabled(void)
0x140029462  test    al, al
0x140029464  jnz     short loc_140029483
0x140029466  mov     eax, [r14+0D8h]
0x14002946d  bt      eax, 13h
0x140029471  jnb     loc_1400299D6
0x140029477  movzx   eax, byte ptr [r15+2Eh]
0x14002947c  movzx   ecx, byte ptr [r15+30h]
0x140029481  jmp     short loc_14002949A
0x140029483  test    dword ptr [r14+0D8h], 400000h
0x14002948e  jz      short loc_140029466
0x140029490  movzx   eax, byte ptr [r15+31h]
0x140029495  movzx   ecx, byte ptr [r15+33h]
0x14002949a  test    al, al
0x14002949c  jnz     loc_140029A49
0x1400294a2  mov     edx, [r15+18h]
0x1400294a6  lea     rcx, [r14+258h]
0x1400294ad  call    ?CompleteLogonTask@LogonTaskDurationsTest@@QEAAXW4LogonTaskId@@@Z; LogonTaskDurationsTest::CompleteLogonTask(LogonTaskId)
0x1400294b2  nop
0x1400294b3  xchg    edi, [r14+220h]
0x1400294ba  mov     rcx, [rbp+2F0h+var_80]
0x1400294c1  xor     rcx, rsp; StackCookie
0x1400294c4  call    __security_check_cookie
0x1400294c9  lea     r11, [rsp+3F0h+var_30]
0x1400294d1  mov     rbx, [r11+50h]
0x1400294d5  movaps  xmm6, xmmword ptr [r11-10h]
0x1400294da  movaps  xmm7, xmmword ptr [r11-20h]
0x1400294df  movaps  xmm8, xmmword ptr [r11-30h]
0x1400294e4  movaps  xmm9, xmmword ptr [r11-40h]
0x1400294e9  mov     rsp, r11
0x1400294ec  pop     r15
0x1400294ee  pop     r14
0x1400294f0  pop     r13
0x1400294f2  pop     r12
0x1400294f4  pop     rdi
0x1400294f5  pop     rsi
0x1400294f6  pop     rbp
0x1400294f7  retn
0x1400294f9  movzx   eax, byte ptr [r15+31h]
0x1400294fe  movzx   ecx, byte ptr [r15+32h]
0x140029503  test    al, al
0x140029505  jz      short loc_1400294A2
0x140029507  cmp     cl, r13b
0x14002950a  jnz     short loc_1400294A2
0x14002950c  cmp     qword ptr [r15+8], 0
0x140029511  jz      short loc_1400294A2
0x140029513  cmp     al, dil
0x140029516  jz      loc_1400296B9
0x14002951c  mov     eax, [r14+0Ch]
0x140029520  cmp     eax, 7FFFFFFFh
0x140029525  jz      short loc_140029536
0x140029527  lea     ecx, [rax+1]
0x14002952a  lock cmpxchg [r14+0Ch], ecx
0x140029530  jnz     loc_1400296DF
0x140029536  mov     r12, r14
0x140029539  mov     eax, [r14+0Ch]
0x14002953d  cmp     eax, 7FFFFFFFh
0x140029542  jz      short loc_140029553
0x140029544  lea     ecx, [rax+1]
0x140029547  lock cmpxchg [r14+0Ch], ecx
0x14002954d  jnz     loc_1400296F3
0x140029553  movups  xmm6, xmmword ptr [r15]
0x140029557  movups  xmm7, xmmword ptr [r15+10h]
0x14002955c  movups  xmm8, xmmword ptr [r15+20h]
0x140029561  movsd   xmm9, qword ptr [r15+30h]
0x140029567  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002956e  mov     ecx, 58h ; 'X'; unsigned __int64
0x140029573  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140029578  mov     rbx, rax
0x14002957b  test    rax, rax
0x14002957e  jz      loc_140029B71
0x140029584  mov     rcx, rax
0x140029587  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIImmersiveApplication@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IImmersiveApplication>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IImmersiveApplication>(void)
0x14002958c  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable'
0x140029593  mov     [rbx], rcx
0x140029596  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14002959d  test    rcx, rcx
0x1400295a0  jnz     loc_140029B60
0x1400295a6  lea     rcx, [rbx+10h]
0x1400295aa  mov     qword ptr [rcx], 0
0x1400295b1  lea     rax, [rbp+2F0h+var_370]
0x1400295b5  cmp     rcx, rax
0x1400295b8  jz      short loc_1400295C0
0x1400295ba  mov     [rcx], r14
0x1400295bd  xor     r12d, r12d
0x1400295c0  movups  xmmword ptr [rcx+8], xmm6
0x1400295c4  movups  xmmword ptr [rcx+18h], xmm7
0x1400295c8  movups  xmmword ptr [rcx+28h], xmm8
0x1400295cd  movsd   qword ptr [rcx+38h], xmm9
0x1400295d3  mov     [rcx+40h], r13b
0x1400295d7  mov     eax, [rbp+2F0h+arg_20]
0x1400295dd  mov     [rcx+44h], eax
0x1400295e0  lea     rax, ??_7?$CTaskWrapper@V_lambda_6803cedb9cee91ceb5d38b0568067134_@@@ComTaskPool@Internal@Windows@@6B@; const Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_6803cedb9cee91ceb5d38b0568067134_>::`vftable'
0x1400295e7  mov     [rbx], rax
0x1400295ea  call    cs:__imp_GetCurrentThreadId
0x1400295f1  nop     dword ptr [rax+rax+00h]
0x1400295f6  mov     qword ptr [rsp+3F0h+var_3C8], 0
0x1400295ff  mov     [rsp+3F0h+var_3D0], rbx
0x140029604  xor     r9d, r9d
0x140029607  mov     r8d, eax
0x14002960a  xor     edx, edx
0x14002960c  mov     ecx, edi
0x14002960e  call    cs:__imp_SHTaskPoolQueueTask
0x140029615  nop     dword ptr [rax+rax+00h]
0x14002961a  nop
0x14002961b  test    rbx, rbx
0x14002961e  jz      short loc_140029630
0x140029620  mov     rax, [rbx]
0x140029623  mov     rcx, rbx
0x140029626  mov     rax, [rax+10h]
0x14002962a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002962f  nop
0x140029630  test    r12, r12
0x140029633  jz      short loc_14002965F
0x140029635  mov     edx, [r12+0Ch]
0x14002963a  cmp     edx, 7FFFFFFFh
0x140029640  jz      short loc_140029654
0x140029642  lea     ecx, [rdx-1]
0x140029645  mov     eax, edx
0x140029647  lock cmpxchg [r12+0Ch], ecx
0x14002964e  jnz     loc_140029707
0x140029654  lea     eax, [rdx-1]
0x140029657  test    eax, eax
0x140029659  jz      loc_140029732
0x14002965f  mov     edx, [r14+0Ch]
0x140029663  cmp     edx, 7FFFFFFFh
0x140029669  jz      short loc_14002967C
0x14002966b  lea     ecx, [rdx-1]
0x14002966e  mov     eax, edx
0x140029670  lock cmpxchg [r14+0Ch], ecx
0x140029676  jnz     loc_14002971D
0x14002967c  lea     eax, [rdx-1]
0x14002967f  test    eax, eax
0x140029681  jnz     loc_1400294A2
0x140029687  mov     rax, [r14]
0x14002968a  mov     edx, edi
0x14002968c  mov     rcx, r14
0x14002968f  mov     rax, [rax+20h]
0x140029693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029698  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14002969f  test    rcx, rcx
0x1400296a2  jz      loc_1400294A2
0x1400296a8  mov     rax, [rcx]
0x1400296ab  mov     rax, [rax+10h]
0x1400296af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400296b4  jmp     loc_1400294A2
0x1400296b9  cmp     r13b, 6
0x1400296bd  setnz   r9b
0x1400296c1  mov     eax, [rbp+2F0h+arg_20]
0x1400296c7  mov     dword ptr [rsp+3F0h+var_3D0], eax
0x1400296cb  movzx   r8d, r13b
0x1400296cf  mov     rdx, r15
0x1400296d2  mov     rcx, r14
0x1400296d5  call    ?_ExecuteTaskFunction@CLogonTaskFramework@@AEAAXAEBULOGON_TASK_DEFINITION@@W4LogonTaskPhase@@_NH@Z; CLogonTaskFramework::_ExecuteTaskFunction(LOGON_TASK_DEFINITION const &,LogonTaskPhase,bool,int)
0x1400296da  jmp     loc_1400294A2
0x1400296df  mov     eax, [r14+0Ch]
0x1400296e3  cmp     eax, 7FFFFFFFh
0x1400296e8  jnz     loc_140029527
0x1400296ee  jmp     loc_140029536
0x1400296f3  mov     eax, [r14+0Ch]
0x1400296f7  cmp     eax, 7FFFFFFFh
0x1400296fc  jnz     loc_140029544
0x140029702  jmp     loc_140029553
0x140029707  mov     edx, [r12+0Ch]
0x14002970c  cmp     edx, 7FFFFFFFh
0x140029712  jnz     loc_140029642
0x140029718  jmp     loc_140029654
0x14002971d  mov     edx, [r14+0Ch]
0x140029721  cmp     edx, 7FFFFFFFh
0x140029727  jnz     loc_14002966B
0x14002972d  jmp     loc_14002967C
0x140029732  mov     rax, [r12]
0x140029736  mov     edx, edi
0x140029738  mov     rcx, r12
0x14002973b  mov     rax, [rax+20h]
0x14002973f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029744  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14002974b  test    rcx, rcx
0x14002974e  jz      loc_14002965F
0x140029754  mov     rax, [rcx]
0x140029757  mov     rax, [rax+10h]
0x14002975b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029760  jmp     loc_14002965F
0x140029765  test    dword ptr [r14+0D8h], 400000h
0x140029770  jz      loc_140029AD1
0x140029776  jmp     loc_1400294F9
0x14002977b  mov     edx, 7
0x140029780  mov     rcx, rbx
0x140029783  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x140029788  mov     r13, rax
0x14002978b  lea     rcx, [rax+1]
0x14002978f  mov     rax, 7FFFFFFFFFFFFFFFh
0x140029799  cmp     rcx, rax
0x14002979c  jbe     short loc_1400297A4
0x14002979e  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x1400297a4  add     rcx, rcx; dwBytes
0x1400297a7  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1400297ac  mov     rdi, rax
0x1400297af  mov     qword ptr [rsp+3F0h+var_3A8+8], rax
0x1400297b4  mov     [rsp+3F0h+var_390], rbx
0x1400297b9  mov     [rsp+3F0h+var_388], r13
0x1400297be  add     rbx, rbx
0x1400297c1  mov     r8, rbx; Size
0x1400297c4  mov     rdx, rsi; Src
0x1400297c7  mov     rcx, rax; void *
0x1400297ca  call    memcpy_0
0x1400297cf  xor     ecx, ecx
0x1400297d1  mov     [rbx+rdi], cx
0x1400297d5  movzx   r13d, [rsp+3F0h+var_3B0]
0x1400297db  jmp     loc_140029433
0x1400297e0  mov     r8d, 0Ch
0x1400297e6  movsxd  r13, [rbp+2F0h+arg_20]
0x1400297ed  mov     edx, r13d
0x1400297f0  lea     rcx, [r14+1E8h]
0x1400297f7  call    ?RecordEventTime@LogonTaskBlackBox@@AEAAXHPEQLOGONTASK_BLACKBOX_TASK_INFORMATION@@K@Z; LogonTaskBlackBox::RecordEventTime(int,ulong LOGONTASK_BLACKBOX_TASK_INFORMATION::*)
0x1400297fc  test    r13d, r13d
0x1400297ff  js      short loc_14002982D
0x140029801  cmp     qword ptr [r14+218h], 0
0x140029809  jz      short loc_14002982D
0x14002980b  call    cs:__imp_GetTickCount
0x140029812  nop     dword ptr [rax+rax+00h]
0x140029817  lea     rdx, ds:0[r13*2]
0x14002981f  add     rdx, r13
0x140029822  mov     rcx, [r14+218h]
0x140029829  mov     [rcx+rdx*8+10h], eax
0x14002982d  lea     rdx, aLogontask; "LogonTask"
0x140029834  lea     rcx, [rbp+2F0h+var_1D0]
0x14002983b  call    ??0?$ActivityBase@VLogonFrameworkLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogonFrameworkLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonFrameworkLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140029840  lea     rax, ??_7LogonTask@LogonFrameworkTelemetry@@6B@; const LogonFrameworkTelemetry::LogonTask::`vftable'
0x140029847  mov     [rbp+2F0h+var_1D0], rax
0x14002984e  lea     rdx, aLogontaskCriti; "LogonTask_Critical"
0x140029855  lea     rcx, [rbp+2F0h+var_320]
0x140029859  call    ??0?$ActivityBase@VLogonFrameworkLogging@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogonFrameworkLogging,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonFrameworkLogging,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14002985e  lea     rax, ??_7LogonTask_Critical@LogonFrameworkTelemetry@@6B@; const LogonFrameworkTelemetry::LogonTask_Critical::`vftable'
0x140029865  mov     [rbp+2F0h+var_320], rax
0x140029869  mov     rdx, [r15]; unsigned __int16 *
0x14002986c  call    ?_ShouldLogCriticalTelemetryForTask@CLogonTaskFramework@@AEBA_NPEBG@Z; CLogonTaskFramework::_ShouldLogCriticalTelemetryForTask(ushort const *)
0x140029871  movzx   r12d, al
0x140029875  mov     [rsp+3F0h+var_3B0+1], al
0x140029879  cmp     byte ptr [r14+0EDh], 0
0x140029881  jz      short loc_1400298B2
0x140029883  cmp     [rsp+3F0h+var_3B0], 6
  ... truncated ...
```
