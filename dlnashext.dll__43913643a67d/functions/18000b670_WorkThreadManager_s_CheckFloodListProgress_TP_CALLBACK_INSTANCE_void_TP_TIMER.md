# WorkThreadManager::s_CheckFloodListProgress(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18000b670`
- end: `0x18000b7cc`
- name: `?s_CheckFloodListProgress@WorkThreadManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `348`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task`

## callees

- `0x180004fd0`
- `0x18000503c`
- `0x18000b670`
- `0x18000c0dc`
- `0x18000c5bc`
- `0x18000c620`
- `0x180012673`
- `0x18003132c`
- `0x1800316ac`
- `0x180032958`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b7c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b7c1`

## pseudocode

```c
void __fastcall WorkThreadManager::s_CheckFloodListProgress(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_TIMER Timer)
{
  WorkThreadManager::TaskData *v3; // rbx
  __int64 v4; // rax
  unsigned int v5; // edx
  unsigned int v6; // ecx
  __int64 v7; // rax
  unsigned int v8; // edx
  WorkThreadManager::TaskData *v9; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-10h] BYREF
  RTL_SRWLOCK *v11; // [rsp+28h] [rbp-8h] BYREF
  WorkThreadManager::TaskData *v12; // [rsp+58h] [rbp+28h] BYREF

  v3 = 0;
  v12 = 0;
  AcquireSRWLockExclusive_0(&WorkThreadManager::s_rwLock);
  v11 = &WorkThreadManager::s_rwLock;
  if ( WorkThreadManager::s_taskFloodingList == (_UNKNOWN *)&WorkThreadManager::s_taskFloodingList )
  {
    WorkThreadManager::s_floodCheckPeriod = 25;
    WorkThreadManager::s_anyThreadMadeProgress = 0;
LABEL_3:
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      &WorkThreadManager::s_floodListTimer,
      0);
    goto LABEL_4;
  }
  if ( WorkThreadManager::s_anyThreadMadeProgress )
  {
    v6 = WorkThreadManager::s_floodCheckPeriod;
    WorkThreadManager::s_anyThreadMadeProgress = 0;
  }
  else
  {
    v7 = WorkThreadManager::TaskList::PopFront(&WorkThreadManager::s_taskFloodingList, &pftDueTime);
    wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::operator=(
      &v12,
      v7);
    v9 = (WorkThreadManager::TaskData *)pftDueTime;
    pftDueTime = 0;
    if ( v9 )
      WorkThreadManager::TaskData::`scalar deleting destructor'(v9, v8);
    if ( WorkThreadManager::s_taskFloodingList == (_UNKNOWN *)&WorkThreadManager::s_taskFloodingList )
    {
      v6 = WorkThreadManager::s_floodCheckPeriod;
    }
    else
    {
      v6 = 2000;
      if ( WorkThreadManager::s_floodCheckPeriod + 25 > 0x7D0 )
        v6 = WorkThreadManager::s_floodCheckPeriod + 25;
      WorkThreadManager::s_floodCheckPeriod = v6;
    }
    v3 = v12;
  }
  if ( !v6 )
    goto LABEL_3;
  pftDueTime = (struct _FILETIME)(-10000LL * v6);
  SetThreadpoolTimer(WorkThreadManager::s_floodListTimer, &pftDueTime, 0, 0);
LABEL_4:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
    &v11,
    0);
  if ( v3 )
  {
    *((_DWORD *)v3 + 1) |= 0x10u;
    v4 = wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>(
           &pftDueTime,
           &v12);
    WorkThreadManager::s_AttachAndRecoverTask(v4);
    v3 = v12;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  if ( v3 )
    WorkThreadManager::TaskData::`scalar deleting destructor'(v3, v5);
}

```

## disassembly

```asm
0x18000b670  mov     [rsp-8+arg_0], rbx
0x18000b675  mov     [rsp-8+arg_8], rdi
0x18000b67a  push    rbp
0x18000b67b  mov     rbp, rsp
0x18000b67e  sub     rsp, 30h
0x18000b682  lea     rdi, ?s_rwLock@WorkThreadManager@@0Vsrwlock@wil@@A; wil::srwlock WorkThreadManager::s_rwLock
0x18000b689  xor     ebx, ebx
0x18000b68b  mov     rcx, rdi; SRWLock
0x18000b68e  mov     [rbp+arg_18], rbx
0x18000b692  call    AcquireSRWLockExclusive_0
0x18000b697  mov     [rbp+var_8], rdi
0x18000b69b  lea     rdi, ?s_taskFloodingList@WorkThreadManager@@0VTaskList@1@A; WorkThreadManager::TaskList WorkThreadManager::s_taskFloodingList
0x18000b6a2  cmp     cs:?s_taskFloodingList@WorkThreadManager@@0VTaskList@1@A, rdi; WorkThreadManager::TaskList WorkThreadManager::s_taskFloodingList
0x18000b6a9  jnz     short loc_18000B71C
0x18000b6ab  mov     cs:?s_floodCheckPeriod@WorkThreadManager@@0KA, 19h; ulong WorkThreadManager::s_floodCheckPeriod
0x18000b6b5  mov     cs:?s_anyThreadMadeProgress@WorkThreadManager@@0_NA, bl; bool WorkThreadManager::s_anyThreadMadeProgress
0x18000b6bb  xor     edx, edx
0x18000b6bd  lea     rcx, ?s_floodListTimer@WorkThreadManager@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>> WorkThreadManager::s_floodListTimer
0x18000b6c4  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000b6c9  xor     edx, edx
0x18000b6cb  lea     rcx, [rbp+var_8]
0x18000b6cf  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x18000b6d4  test    rbx, rbx
0x18000b6d7  jz      short loc_18000B6F6
0x18000b6d9  or      dword ptr [rbx+4], 10h
0x18000b6dd  lea     rdx, [rbp+arg_18]
0x18000b6e1  lea     rcx, [rbp+pftDueTime]
0x18000b6e5  call    ??0?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>(wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>> &&)
0x18000b6ea  mov     rcx, rax
0x18000b6ed  call    ?s_AttachAndRecoverTask@WorkThreadManager@@CAXV?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@@Z; WorkThreadManager::s_AttachAndRecoverTask(wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>)
0x18000b6f2  mov     rbx, [rbp+arg_18]
0x18000b6f6  lea     rcx, [rbp+var_8]
0x18000b6fa  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b6ff  test    rbx, rbx
0x18000b702  jz      short loc_18000B70C
0x18000b704  mov     rcx, rbx; this
0x18000b707  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x18000b70c  mov     rbx, [rsp+30h+arg_0]
0x18000b711  mov     rdi, [rsp+30h+arg_8]
0x18000b716  add     rsp, 30h
0x18000b71a  pop     rbp
0x18000b71b  retn
0x18000b71c  cmp     cs:?s_anyThreadMadeProgress@WorkThreadManager@@0_NA, bl; bool WorkThreadManager::s_anyThreadMadeProgress
0x18000b722  jz      short loc_18000B732
0x18000b724  mov     ecx, cs:?s_floodCheckPeriod@WorkThreadManager@@0KA; ulong WorkThreadManager::s_floodCheckPeriod
0x18000b72a  mov     cs:?s_anyThreadMadeProgress@WorkThreadManager@@0_NA, bl; bool WorkThreadManager::s_anyThreadMadeProgress
0x18000b730  jmp     short loc_18000B78A
0x18000b732  lea     rdx, [rbp+pftDueTime]
0x18000b736  mov     rcx, rdi
0x18000b739  call    ?PopFront@TaskList@WorkThreadManager@@QEAA?AV?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@XZ; WorkThreadManager::TaskList::PopFront(void)
0x18000b73e  mov     rdx, rax
0x18000b741  lea     rcx, [rbp+arg_18]
0x18000b745  call    ??4?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::operator=(wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>> &&)
0x18000b74a  mov     rcx, qword ptr [rbp+pftDueTime.dwLowDateTime]; this
0x18000b74e  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rbx
0x18000b752  test    rcx, rcx
0x18000b755  jz      short loc_18000B75C
0x18000b757  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x18000b75c  cmp     cs:?s_taskFloodingList@WorkThreadManager@@0VTaskList@1@A, rdi; WorkThreadManager::TaskList WorkThreadManager::s_taskFloodingList
0x18000b763  jz      short loc_18000B780
0x18000b765  mov     eax, cs:?s_floodCheckPeriod@WorkThreadManager@@0KA; ulong WorkThreadManager::s_floodCheckPeriod
0x18000b76b  mov     ecx, 7D0h
0x18000b770  add     eax, 19h
0x18000b773  cmp     eax, ecx
0x18000b775  cmova   ecx, eax
0x18000b778  mov     cs:?s_floodCheckPeriod@WorkThreadManager@@0KA, ecx; ulong WorkThreadManager::s_floodCheckPeriod
0x18000b77e  jmp     short loc_18000B786
0x18000b780  mov     ecx, cs:?s_floodCheckPeriod@WorkThreadManager@@0KA; ulong WorkThreadManager::s_floodCheckPeriod
0x18000b786  mov     rbx, [rbp+arg_18]
0x18000b78a  test    ecx, ecx
0x18000b78c  jz      loc_18000B6BB
0x18000b792  mov     eax, ecx
0x18000b794  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x18000b798  imul    rax, 0FFFFFFFFFFFFD8F0h
0x18000b79f  xor     r9d, r9d; msWindowLength
0x18000b7a2  xor     r8d, r8d; msPeriod
0x18000b7a5  mov     rcx, rax
0x18000b7a8  mov     [rbp+pftDueTime.dwLowDateTime], eax
0x18000b7ab  shr     rcx, 20h
0x18000b7af  mov     [rbp+pftDueTime.dwHighDateTime], ecx
0x18000b7b2  mov     rax, qword ptr [rbp+pftDueTime.dwLowDateTime]
0x18000b7b6  mov     rcx, cs:?s_floodListTimer@WorkThreadManager@@0V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; pti
0x18000b7bd  mov     qword ptr [rbp+pftDueTime.dwLowDateTime], rax
0x18000b7c1  call    cs:__imp_SetThreadpoolTimer
0x18000b7c7  jmp     loc_18000B6C9
```
