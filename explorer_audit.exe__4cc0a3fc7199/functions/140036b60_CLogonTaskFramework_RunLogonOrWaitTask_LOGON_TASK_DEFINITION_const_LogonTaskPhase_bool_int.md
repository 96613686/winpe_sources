# CLogonTaskFramework::_RunLogonOrWaitTask(LOGON_TASK_DEFINITION const &,LogonTaskPhase,bool,int)

- ea: `0x140036b60`
- end: `0x14003735a`
- name: `?_RunLogonOrWaitTask@CLogonTaskFramework@@AEAAXAEBULOGON_TASK_DEFINITION@@W4LogonTaskPhase@@_NH@Z`
- size: `2042`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000ce78`

## callees

- `0x14000a800`
- `0x14000d7e0`
- `0x14000edf8`
- `0x14000f2ac`
- `0x14000f4ac`
- `0x1400175d0`
- `0x140017a50`
- `0x14001a070`
- `0x14001f420`
- `0x140036b60`
- `0x14003738c`
- `0x1400376c8`
- `0x140037880`
- `0x140037ab8`
- `0x140037ff0`
- `0x140078fc0`
- `0x14008fb84`
- `0x14008fc9c`
- `0x14008fe48`
- `0x1400a2cf4`
- `0x1400aa438`
- `0x1400ac8c4`
- `0x1400aea90`
- `0x1401040e0`
- `0x1401044a0`
- `0x140104cc8`
- `0x140137070`
- `0x1401b2210`
- `0x1401db010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400371b6`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400371b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140036de9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140037244`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140036de9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140037244`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x140036e07`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x140036e07`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140036ffe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140036ffe`

## string_xrefs

- `0x14003701a`: `LogonTask`
- `0x14003703b`: `LogonTask_Critical`

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
  _InterlockedExchange((volatile __int32 *)(a1 + 528), *((_DWORD *)a2 + 6));
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
  LogonTaskDurationsTest::StartLogonTask(a1 + 584, *((unsigned int *)a2 + 6), &v43);
  if ( a4 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58790537>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ID58790537>::GetImpl'::`2'::impl)
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
      LogonTaskBlackBox::RecordEventTime(a1 + 472, (unsigned int)a5, 12);
      if ( a5 >= 0 && *(_QWORD *)(a1 + 520) )
        *(_DWORD *)(*(_QWORD *)(a1 + 520) + 24LL * a5 + 16) = GetTickCount();
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
            a1 + 608);
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
            a1 + 608);
        LogonFrameworkTelemetry::LogonTask_Critical::StartActivity(
          (LogonFrameworkTelemetry::LogonTask_Critical *)v49,
          (const unsigned __int16 *)*a2,
          1,
          1);
      }
      v36 = ((__int64 (__fastcall *)(__int64, _QWORD *))a2[2])(a1, v50);
      if ( (byte_140253B84 & 8) != 0 )
        McTemplateU0qz_EventWriteTransfer(v34, &LogonPerformance_TaskRunTime_Stop, *(unsigned int *)(a1 + 216), *a2);
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
      LogonTaskBlackBox::TaskWaited((LogonTaskBlackBox *)(a1 + 472), a5);
      v49[0] = &LogonFrameworkTelemetry::LogonTask_Critical::`vftable';
      wil::ActivityBase<LogonFrameworkLogging,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v49);
      wil::ActivityBase<LogonFrameworkLogging,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonFrameworkLogging,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v49);
      LogonFrameworkTelemetry::LogonTask::~LogonTask((LogonFrameworkTelemetry::LogonTask *)v50);
    }
  }
  else
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58790537>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ID58790537>::GetImpl'::`2'::impl)
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
        SHTaskPoolQueueTask(1, 0, v27, 0);
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
  result = LogonTaskDurationsTest::CompleteLogonTask(a1 + 584, *((unsigned int *)a2 + 6));
  _InterlockedExchange((volatile __int32 *)(a1 + 528), 1);
  return result;
}

```

## disassembly

```asm
0x140036b60  mov     rax, rsp
0x140036b63  mov     [rax+18h], rbx
0x140036b67  push    rbp
0x140036b68  push    rsi
0x140036b69  push    rdi
0x140036b6a  push    r12
0x140036b6c  push    r13
0x140036b6e  push    r14
0x140036b70  push    r15
0x140036b72  lea     rbp, [rax-2F8h]
0x140036b79  sub     rsp, 3C0h
0x140036b80  movaps  xmmword ptr [rax-48h], xmm6
0x140036b84  movaps  xmmword ptr [rax-58h], xmm7
0x140036b88  movaps  xmmword ptr [rax-68h], xmm8
0x140036b8d  movaps  xmmword ptr [rax-78h], xmm9
0x140036b92  mov     rax, cs:__security_cookie
0x140036b99  xor     rax, rsp
0x140036b9c  mov     [rbp+2F0h+var_80], rax
0x140036ba3  movzx   r12d, r9b
0x140036ba7  movzx   r13d, r8b
0x140036bab  mov     [rsp+3F0h+var_3B0], r8b
0x140036bb0  mov     r15, rdx
0x140036bb3  mov     r14, rcx
0x140036bb6  mov     eax, [rdx+18h]
0x140036bb9  xchg    eax, [rcx+210h]
0x140036bbf  mov     [rsp+3F0h+var_380], rcx
0x140036bc4  mov     [rsp+3F0h+var_378], 1
0x140036bc9  mov     rsi, [rdx]
0x140036bcc  xorps   xmm0, xmm0
0x140036bcf  movups  [rsp+3F0h+var_3A8+8], xmm0
0x140036bd4  xor     edi, edi
0x140036bd6  mov     [rsp+3F0h+var_390], rdi
0x140036bdb  mov     [rsp+3F0h+var_388], rdi
0x140036be0  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x140036be7  inc     rbx
0x140036bea  cmp     [rsi+rbx*2], di
0x140036bee  jnz     short loc_140036BE7
0x140036bf0  mov     r8, 7FFFFFFFFFFFFFFEh
0x140036bfa  cmp     rbx, r8
0x140036bfd  ja      loc_1400371AF
0x140036c03  cmp     rbx, 7
0x140036c07  ja      loc_140036F6E
0x140036c0d  mov     [rsp+3F0h+var_390], rbx
0x140036c12  mov     [rsp+3F0h+var_388], 7
0x140036c1b  add     rbx, rbx
0x140036c1e  mov     r8, rbx; Size
0x140036c21  mov     rdx, rsi; Src
0x140036c24  lea     rcx, [rsp+3F0h+var_3A8+8]; void *
0x140036c29  call    memcpy_0
0x140036c2e  mov     word ptr [rsp+rbx+3F0h+var_3A8+8], di
0x140036c33  lea     r8, [rsp+3F0h+var_3A8+8]
0x140036c38  mov     edx, [r15+18h]
0x140036c3c  lea     rcx, [r14+248h]
0x140036c43  call    ?StartLogonTask@LogonTaskDurationsTest@@QEAAXW4LogonTaskId@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LogonTaskDurationsTest::StartLogonTask(LogonTaskId,std::wstring)
0x140036c48  mov     edi, 1
0x140036c4d  test    r12b, r12b
0x140036c50  jz      loc_14003729E
0x140036c56  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID58790537@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID58790537@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58790537> `wil::Feature<__WilFeatureTraits_Feature_ID58790537>::GetImpl(void)'::`2'::impl
0x140036c5d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID58790537@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58790537>::__private_IsEnabled(void)
0x140036c62  test    al, al
0x140036c64  jnz     short loc_140036C83
0x140036c66  mov     eax, [r14+0D8h]
0x140036c6d  bt      eax, 13h
0x140036c71  jnb     loc_1400371BD
0x140036c77  movzx   eax, byte ptr [r15+2Eh]
0x140036c7c  movzx   ecx, byte ptr [r15+30h]
0x140036c81  jmp     short loc_140036C9A
0x140036c83  test    dword ptr [r14+0D8h], 400000h
0x140036c8e  jz      short loc_140036C66
0x140036c90  movzx   eax, byte ptr [r15+31h]
0x140036c95  movzx   ecx, byte ptr [r15+33h]
0x140036c9a  test    al, al
0x140036c9c  jnz     loc_140037230
0x140036ca2  mov     edx, [r15+18h]
0x140036ca6  lea     rcx, [r14+248h]
0x140036cad  call    ?CompleteLogonTask@LogonTaskDurationsTest@@QEAAXW4LogonTaskId@@@Z; LogonTaskDurationsTest::CompleteLogonTask(LogonTaskId)
0x140036cb2  nop
0x140036cb3  xchg    edi, [r14+210h]
0x140036cba  mov     rcx, [rbp+2F0h+var_80]
0x140036cc1  xor     rcx, rsp; StackCookie
0x140036cc4  call    __security_check_cookie
0x140036cc9  lea     r11, [rsp+3F0h+var_30]
0x140036cd1  mov     rbx, [r11+50h]
0x140036cd5  movaps  xmm6, xmmword ptr [r11-10h]
0x140036cda  movaps  xmm7, xmmword ptr [r11-20h]
0x140036cdf  movaps  xmm8, xmmword ptr [r11-30h]
0x140036ce4  movaps  xmm9, xmmword ptr [r11-40h]
0x140036ce9  mov     rsp, r11
0x140036cec  pop     r15
0x140036cee  pop     r14
0x140036cf0  pop     r13
0x140036cf2  pop     r12
0x140036cf4  pop     rdi
0x140036cf5  pop     rsi
0x140036cf6  pop     rbp
0x140036cf7  retn
0x140036cf8  movzx   eax, byte ptr [r15+31h]
0x140036cfd  movzx   ecx, byte ptr [r15+32h]
0x140036d02  test    al, al
0x140036d04  jz      short loc_140036CA2
0x140036d06  cmp     cl, r13b
0x140036d09  jnz     short loc_140036CA2
0x140036d0b  cmp     qword ptr [r15+8], 0
0x140036d10  jz      short loc_140036CA2
0x140036d12  cmp     al, dil
0x140036d15  jz      loc_140036EAC
0x140036d1b  mov     eax, [r14+0Ch]
0x140036d1f  cmp     eax, 7FFFFFFFh
0x140036d24  jz      short loc_140036D35
0x140036d26  lea     ecx, [rax+1]
0x140036d29  lock cmpxchg [r14+0Ch], ecx
0x140036d2f  jnz     loc_140036ED2
0x140036d35  mov     r12, r14
0x140036d38  mov     eax, [r14+0Ch]
0x140036d3c  cmp     eax, 7FFFFFFFh
0x140036d41  jz      short loc_140036D52
0x140036d43  lea     ecx, [rax+1]
0x140036d46  lock cmpxchg [r14+0Ch], ecx
0x140036d4c  jnz     loc_140036EE6
0x140036d52  movups  xmm6, xmmword ptr [r15]
0x140036d56  movups  xmm7, xmmword ptr [r15+10h]
0x140036d5b  movups  xmm8, xmmword ptr [r15+20h]
0x140036d60  movsd   xmm9, qword ptr [r15+30h]
0x140036d66  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140036d6d  mov     ecx, 58h ; 'X'; unsigned __int64
0x140036d72  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140036d77  mov     rbx, rax
0x140036d7a  test    rax, rax
0x140036d7d  jz      loc_140037352
0x140036d83  mov     rcx, rax
0x140036d86  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIImmersiveApplication@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IImmersiveApplication>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IImmersiveApplication>(void)
0x140036d8b  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIComPoolTask@Internal@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Internal::IComPoolTask>::`vftable'
0x140036d92  mov     [rbx], rcx
0x140036d95  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140036d9c  test    rcx, rcx
0x140036d9f  jnz     loc_140037341
0x140036da5  lea     rcx, [rbx+10h]
0x140036da9  mov     qword ptr [rcx], 0
0x140036db0  lea     rax, [rbp+2F0h+var_370]
0x140036db4  cmp     rcx, rax
0x140036db7  jz      short loc_140036DBF
0x140036db9  mov     [rcx], r14
0x140036dbc  xor     r12d, r12d
0x140036dbf  movups  xmmword ptr [rcx+8], xmm6
0x140036dc3  movups  xmmword ptr [rcx+18h], xmm7
0x140036dc7  movups  xmmword ptr [rcx+28h], xmm8
0x140036dcc  movsd   qword ptr [rcx+38h], xmm9
0x140036dd2  mov     [rcx+40h], r13b
0x140036dd6  mov     eax, [rbp+2F0h+arg_20]
0x140036ddc  mov     [rcx+44h], eax
0x140036ddf  lea     rax, ??_7?$CTaskWrapper@V_lambda_6803cedb9cee91ceb5d38b0568067134_@@@ComTaskPool@Internal@Windows@@6B@; const Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_6803cedb9cee91ceb5d38b0568067134_>::`vftable'
0x140036de6  mov     [rbx], rax
0x140036de9  call    cs:__imp_GetCurrentThreadId
0x140036def  mov     qword ptr [rsp+3F0h+var_3C8], 0
0x140036df8  mov     [rsp+3F0h+var_3D0], rbx
0x140036dfd  xor     r9d, r9d
0x140036e00  mov     r8d, eax
0x140036e03  xor     edx, edx
0x140036e05  mov     ecx, edi
0x140036e07  call    cs:__imp_SHTaskPoolQueueTask
0x140036e0d  nop
0x140036e0e  test    rbx, rbx
0x140036e11  jz      short loc_140036E23
0x140036e13  mov     rax, [rbx]
0x140036e16  mov     rcx, rbx
0x140036e19  mov     rax, [rax+10h]
0x140036e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036e22  nop
0x140036e23  test    r12, r12
0x140036e26  jz      short loc_140036E52
0x140036e28  mov     edx, [r12+0Ch]
0x140036e2d  cmp     edx, 7FFFFFFFh
0x140036e33  jz      short loc_140036E47
0x140036e35  lea     ecx, [rdx-1]
0x140036e38  mov     eax, edx
0x140036e3a  lock cmpxchg [r12+0Ch], ecx
0x140036e41  jnz     loc_140036EFA
0x140036e47  lea     eax, [rdx-1]
0x140036e4a  test    eax, eax
0x140036e4c  jz      loc_140036F25
0x140036e52  mov     edx, [r14+0Ch]
0x140036e56  cmp     edx, 7FFFFFFFh
0x140036e5c  jz      short loc_140036E6F
0x140036e5e  lea     ecx, [rdx-1]
0x140036e61  mov     eax, edx
0x140036e63  lock cmpxchg [r14+0Ch], ecx
0x140036e69  jnz     loc_140036F10
0x140036e6f  lea     eax, [rdx-1]
0x140036e72  test    eax, eax
0x140036e74  jnz     loc_140036CA2
0x140036e7a  mov     rax, [r14]
0x140036e7d  mov     edx, edi
0x140036e7f  mov     rcx, r14
0x140036e82  mov     rax, [rax+20h]
0x140036e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036e8b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140036e92  test    rcx, rcx
0x140036e95  jz      loc_140036CA2
0x140036e9b  mov     rax, [rcx]
0x140036e9e  mov     rax, [rax+10h]
0x140036ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036ea7  jmp     loc_140036CA2
0x140036eac  cmp     r13b, 6
0x140036eb0  setnz   r9b
0x140036eb4  mov     eax, [rbp+2F0h+arg_20]
0x140036eba  mov     dword ptr [rsp+3F0h+var_3D0], eax
0x140036ebe  movzx   r8d, r13b
0x140036ec2  mov     rdx, r15
0x140036ec5  mov     rcx, r14
0x140036ec8  call    ?_ExecuteTaskFunction@CLogonTaskFramework@@AEAAXAEBULOGON_TASK_DEFINITION@@W4LogonTaskPhase@@_NH@Z; CLogonTaskFramework::_ExecuteTaskFunction(LOGON_TASK_DEFINITION const &,LogonTaskPhase,bool,int)
0x140036ecd  jmp     loc_140036CA2
0x140036ed2  mov     eax, [r14+0Ch]
0x140036ed6  cmp     eax, 7FFFFFFFh
0x140036edb  jnz     loc_140036D26
0x140036ee1  jmp     loc_140036D35
0x140036ee6  mov     eax, [r14+0Ch]
0x140036eea  cmp     eax, 7FFFFFFFh
0x140036eef  jnz     loc_140036D43
0x140036ef5  jmp     loc_140036D52
0x140036efa  mov     edx, [r12+0Ch]
0x140036eff  cmp     edx, 7FFFFFFFh
0x140036f05  jnz     loc_140036E35
0x140036f0b  jmp     loc_140036E47
0x140036f10  mov     edx, [r14+0Ch]
0x140036f14  cmp     edx, 7FFFFFFFh
0x140036f1a  jnz     loc_140036E5E
0x140036f20  jmp     loc_140036E6F
0x140036f25  mov     rax, [r12]
0x140036f29  mov     edx, edi
0x140036f2b  mov     rcx, r12
0x140036f2e  mov     rax, [rax+20h]
0x140036f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036f37  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140036f3e  test    rcx, rcx
0x140036f41  jz      loc_140036E52
0x140036f47  mov     rax, [rcx]
0x140036f4a  mov     rax, [rax+10h]
0x140036f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140036f53  jmp     loc_140036E52
0x140036f58  test    dword ptr [r14+0D8h], 400000h
0x140036f63  jz      loc_1400372B2
0x140036f69  jmp     loc_140036CF8
0x140036f6e  mov     edx, 7
0x140036f73  mov     rcx, rbx
0x140036f76  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x140036f7b  mov     r13, rax
0x140036f7e  lea     rcx, [rax+1]
0x140036f82  mov     rax, 7FFFFFFFFFFFFFFFh
0x140036f8c  cmp     rcx, rax
0x140036f8f  jbe     short loc_140036F97
0x140036f91  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x140036f97  add     rcx, rcx; dwBytes
0x140036f9a  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x140036f9f  mov     rdi, rax
0x140036fa2  mov     qword ptr [rsp+3F0h+var_3A8+8], rax
0x140036fa7  mov     [rsp+3F0h+var_390], rbx
0x140036fac  mov     [rsp+3F0h+var_388], r13
0x140036fb1  add     rbx, rbx
0x140036fb4  mov     r8, rbx; Size
0x140036fb7  mov     rdx, rsi; Src
0x140036fba  mov     rcx, rax; void *
0x140036fbd  call    memcpy_0
0x140036fc2  xor     ecx, ecx
0x140036fc4  mov     [rbx+rdi], cx
0x140036fc8  movzx   r13d, [rsp+3F0h+var_3B0]
0x140036fce  jmp     loc_140036C33
0x140036fd3  mov     r8d, 0Ch
0x140036fd9  movsxd  r13, [rbp+2F0h+arg_20]
0x140036fe0  mov     edx, r13d
0x140036fe3  lea     rcx, [r14+1D8h]
0x140036fea  call    ?RecordEventTime@LogonTaskBlackBox@@AEAAXHPEQLOGONTASK_BLACKBOX_TASK_INFORMATION@@K@Z; LogonTaskBlackBox::RecordEventTime(int,ulong LOGONTASK_BLACKBOX_TASK_INFORMATION::*)
0x140036fef  test    r13d, r13d
0x140036ff2  js      short loc_14003701A
0x140036ff4  cmp     qword ptr [r14+208h], 0
0x140036ffc  jz      short loc_14003701A
0x140036ffe  call    cs:__imp_GetTickCount
0x140037004  lea     rdx, ds:0[r13*2]
0x14003700c  add     rdx, r13
0x14003700f  mov     rcx, [r14+208h]
0x140037016  mov     [rcx+rdx*8+10h], eax
0x14003701a  lea     rdx, aLogontask; "LogonTask"
0x140037021  lea     rcx, [rbp+2F0h+var_1D0]
0x140037028  call    ??0?$ActivityBase@VLogonFrameworkLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogonFrameworkLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonFrameworkLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14003702d  lea     rax, ??_7LogonTask@LogonFrameworkTelemetry@@6B@; const LogonFrameworkTelemetry::LogonTask::`vftable'
0x140037034  mov     [rbp+2F0h+var_1D0], rax
0x14003703b  lea     rdx, aLogontaskCriti; "LogonTask_Critical"
0x140037042  lea     rcx, [rbp+2F0h+var_320]
0x140037046  call    ??0?$ActivityBase@VLogonFrameworkLogging@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogonFrameworkLogging,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogonFrameworkLogging,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14003704b  lea     rax, ??_7LogonTask_Critical@LogonFrameworkTelemetry@@6B@; const LogonFrameworkTelemetry::LogonTask_Critical::`vftable'
0x140037052  mov     [rbp+2F0h+var_320], rax
0x140037056  mov     rdx, [r15]; unsigned __int16 *
0x140037059  call    ?_ShouldLogCriticalTelemetryForTask@CLogonTaskFramework@@AEBA_NPEBG@Z; CLogonTaskFramework::_ShouldLogCriticalTelemetryForTask(ushort const *)
0x14003705e  movzx   r12d, al
0x140037062  mov     [rsp+3F0h+var_3B0+1], al
0x140037066  cmp     byte ptr [r14+0EDh], 0
0x14003706e  jz      short loc_14003709F
0x140037070  cmp     [rsp+3F0h+var_3B0], 6
0x140037075  jz      short loc_14003708A
0x140037077  lea     rdx, [r14+260h]
0x14003707e  lea     rcx, [rbp+2F0h+var_1D0]
  ... truncated ...
```
