# WorkThreadManager::CThread::StartThreadWithFallback(void)

- ea: `0x18000c3f4`
- end: `0x18000c541`
- name: `?StartThreadWithFallback@CThread@WorkThreadManager@@QEAAJXZ`
- size: `333`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032b10`

## callees

- `0x180009740`
- `0x18000c3f4`
- `0x18000c548`
- `0x18000cd54`
- `0x180011954`
- `0x1800316ac`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4e1`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000c4d7`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18000c4d7`

## string_xrefs

- `0x18000c416`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`
- `0x18000c494`: `onecore\shell\shcore\libs\comtaskpool\taskpoolprivate.cpp`

## pseudocode

```c
__int64 __fastcall WorkThreadManager::CThread::StartThreadWithFallback(WorkThreadManager::CThread *pv)
{
  signed int started; // edi
  __int64 v3; // rdx
  void *v5; // rax
  unsigned int v6; // edx
  WorkThreadManager::TaskData *v7; // rcx
  signed int LastError; // eax
  unsigned int v9; // edx
  WorkThreadManager::TaskData *v10; // rcx
  int v11[2]; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  started = WorkThreadManager::CThread::StartThreadCommon(pv);
  if ( started < 0 )
  {
    v3 = 679;
    goto LABEL_3;
  }
  v5 = operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v5 )
  {
    *(_QWORD *)v11 = *((_QWORD *)pv + 20);
    v5 = (void *)WorkThreadManager::TaskData::TaskData(
                   v5,
                   *((unsigned int *)pv + 36),
                   *((unsigned int *)pv + 37),
                   *((unsigned int *)pv + 38));
  }
  v7 = (WorkThreadManager::TaskData *)*((_QWORD *)pv + 7);
  *((_QWORD *)pv + 7) = v5;
  if ( v7 )
    WorkThreadManager::TaskData::`scalar deleting destructor'(v7, v6);
  if ( *((_QWORD *)pv + 7) )
  {
    _InterlockedIncrement((volatile signed __int32 *)&WorkThreadManager::s_cThreadsStarting);
    (*(void (__fastcall **)(WorkThreadManager::CThread *))(*(_QWORD *)pv + 8LL))(pv);
    if ( !TrySubmitThreadpoolCallback(_lambda_142c425290ac4fbd4d5aee2fc3f7d711_::_lambda_invoker_cdecl_, pv, 0) )
    {
      LastError = GetLastError();
      started = LastError;
      if ( LastError > 0 )
        started = (unsigned __int16)LastError | 0x80070000;
      (*(void (__fastcall **)(WorkThreadManager::CThread *))(*(_QWORD *)pv + 16LL))(pv);
      v10 = (WorkThreadManager::TaskData *)*((_QWORD *)pv + 7);
      *((_QWORD *)pv + 7) = 0;
      if ( v10 )
        WorkThreadManager::TaskData::`scalar deleting destructor'(v10, v9);
      _InterlockedDecrement((volatile signed __int32 *)&WorkThreadManager::s_cThreadsStarting);
      if ( started >= 0 )
        return (unsigned int)started;
      v3 = 699;
LABEL_3:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v3,
        (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
        (const char *)(unsigned int)started,
        v11[0]);
      return (unsigned int)started;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A9,
      (unsigned int)"onecore\\shell\\shcore\\libs\\comtaskpool\\taskpoolprivate.cpp",
      (const char *)0x8007000ELL,
      v11[0]);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000c3f4  mov     [rsp+arg_0], rbx
0x18000c3f9  push    rdi
0x18000c3fa  sub     rsp, 30h
0x18000c3fe  mov     rbx, rcx
0x18000c401  call    ?StartThreadCommon@CThread@WorkThreadManager@@QEAAJXZ; WorkThreadManager::CThread::StartThreadCommon(void)
0x18000c406  mov     edi, eax
0x18000c408  test    eax, eax
0x18000c40a  jns     short loc_18000C42C
0x18000c40c  mov     edx, 2A7h; void *
0x18000c411  mov     rcx, [rsp+38h]; this
0x18000c416  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000c41d  mov     r9d, edi; char *
0x18000c420  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c425  mov     eax, edi
0x18000c427  jmp     loc_18000C536
0x18000c42c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c433  mov     ecx, 48h ; 'H'; unsigned __int64
0x18000c438  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c43d  test    rax, rax
0x18000c440  jz      short loc_18000C476
0x18000c442  mov     rcx, [rbx+0C0h]
0x18000c449  mov     r9d, [rbx+98h]
0x18000c450  mov     r8d, [rbx+94h]
0x18000c457  mov     edx, [rbx+90h]
0x18000c45d  mov     [rsp+38h+var_10], rcx
0x18000c462  mov     rcx, [rbx+0A0h]
0x18000c469  mov     qword ptr [rsp+38h+var_18], rcx; int
0x18000c46e  mov     rcx, rax
0x18000c471  call    ??0TaskData@WorkThreadManager@@QEAA@W4TaskApartment@Internal@Windows@@W4TaskOptions@34@KPEAXPEAUIComPoolTask@34@@Z; WorkThreadManager::TaskData::TaskData(Windows::Internal::TaskApartment,Windows::Internal::TaskOptions,ulong,void *,Windows::Internal::IComPoolTask *)
0x18000c476  mov     rcx, [rbx+38h]; this
0x18000c47a  mov     [rbx+38h], rax
0x18000c47e  test    rcx, rcx
0x18000c481  jz      short loc_18000C488
0x18000c483  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x18000c488  cmp     qword ptr [rbx+38h], 0
0x18000c48d  jnz     short loc_18000C4B4
0x18000c48f  mov     rcx, [rsp+38h]; this
0x18000c494  lea     r8, aOnecoreShellSh; "onecore\\shell\\shcore\\libs\\comtaskpo"...
0x18000c49b  mov     ebx, 8007000Eh
0x18000c4a0  mov     edx, 2A9h; void *
0x18000c4a5  mov     r9d, ebx; char *
0x18000c4a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c4ad  mov     eax, ebx
0x18000c4af  jmp     loc_18000C536
0x18000c4b4  lock inc cs:?s_cThreadsStarting@WorkThreadManager@@0KA; ulong WorkThreadManager::s_cThreadsStarting
0x18000c4bb  mov     rax, [rbx]
0x18000c4be  mov     rcx, rbx
0x18000c4c1  mov     rax, [rax+8]
0x18000c4c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4ca  xor     r8d, r8d; pcbe
0x18000c4cd  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_142c425290ac4fbd4d5aee2fc3f7d711_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18000c4d4  mov     rdx, rbx; pv
0x18000c4d7  call    cs:__imp_TrySubmitThreadpoolCallback
0x18000c4dd  test    eax, eax
0x18000c4df  jnz     short loc_18000C534
0x18000c4e1  call    cs:__imp_GetLastError
0x18000c4e7  mov     edi, eax
0x18000c4e9  test    eax, eax
0x18000c4eb  jle     short loc_18000C4F6
0x18000c4ed  movzx   edi, ax
0x18000c4f0  or      edi, 80070000h
0x18000c4f6  mov     rax, [rbx]
0x18000c4f9  mov     rcx, rbx
0x18000c4fc  mov     rax, [rax+10h]
0x18000c500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c505  mov     rcx, [rbx+38h]; this
0x18000c509  mov     qword ptr [rbx+38h], 0
0x18000c511  test    rcx, rcx
0x18000c514  jz      short loc_18000C51B
0x18000c516  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x18000c51b  lock dec cs:?s_cThreadsStarting@WorkThreadManager@@0KA; ulong WorkThreadManager::s_cThreadsStarting
0x18000c522  test    edi, edi
0x18000c524  jns     loc_18000C425
0x18000c52a  mov     edx, 2BBh
0x18000c52f  jmp     loc_18000C411
0x18000c534  xor     eax, eax
0x18000c536  mov     rbx, [rsp+38h+arg_0]
0x18000c53b  add     rsp, 30h
0x18000c53f  pop     rdi
0x18000c540  retn
```
