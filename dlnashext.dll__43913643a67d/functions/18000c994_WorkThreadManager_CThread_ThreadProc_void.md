# WorkThreadManager::CThread::ThreadProc(void)

- ea: `0x18000c994`
- end: `0x18000cb47`
- name: `?ThreadProc@CThread@WorkThreadManager@@AEAAXXZ`
- size: `435`
- prototype: `void __fastcall(WorkThreadManager::CThread *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000a694`

## callees

- `0x180003f8c`
- `0x180003fc0`
- `0x180007620`
- `0x1800098a0`
- `0x1800098f0`
- `0x18000c994`
- `0x18000cb50`
- `0x18000cbdc`
- `0x18000cbec`
- `0x18000ccc8`
- `0x18001272e`
- `0x18003132c`
- `0x1800316ac`
- `0x18003268c`
- `0x180032958`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000cb40`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000cae1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000cae1`
- `api-ms-win-shcore-thread-l1-1-0!SHSetThreadRef` at `0x18000cb14`
- `api-ms-win-shcore-thread-l1-1-0!SHSetThreadRef` at `0x18000cb14`

## pseudocode

```c
void __fastcall WorkThreadManager::CThread::ThreadProc(RTL_SRWLOCK *this)
{
  DWORD CurrentThreadId_0; // eax
  _DWORD *Ptr; // rdx
  __int64 v4; // rax
  int v5; // eax
  void *v6; // rdx
  wil::details *v7; // rcx
  WorkThreadManager::TaskData *v8; // rcx
  bool v9; // di
  bool v10; // zf
  __int64 v11; // rax
  PVOID v12; // rcx
  void *v13; // rdx
  wil::details *v14; // rcx
  char v15; // [rsp+30h] [rbp+8h] BYREF

  CurrentThreadId_0 = GetCurrentThreadId_0();
  Ptr = this[14].Ptr;
  LODWORD(this[10].Ptr) = CurrentThreadId_0;
  Ptr[4] = CurrentThreadId_0;
  *((_DWORD *)this[15].Ptr + 4) = this[10].Ptr;
  v4 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v15, this);
  v5 = _lambda_103564c3136a6d89c1bf4e8d5a4b0eab_::operator()(v4);
  HIDWORD(this[5].Ptr) = v5;
  if ( v5 < 0 )
  {
    if ( this[7].Ptr )
    {
      v11 = wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>(
              &v15,
              &this[7]);
      WorkThreadManager::s_AttachAndRecoverTask(v11);
    }
    v12 = this[20].Ptr;
    if ( v12 )
      SetEvent(v12);
    _InterlockedDecrement((volatile signed __int32 *)&WorkThreadManager::s_cThreadsStarting);
    WorkThreadManager::s_TryRemoveThread((struct WorkThreadManager::CThread *)this, 1, 0);
    WorkThreadManager::TaskList::Clear((WorkThreadManager::TaskList *)&this[3]);
    v14 = (wil::details *)this[6].Ptr;
    if ( v14 )
      wil::details::SetEvent(v14, v13);
  }
  else
  {
    v7 = (wil::details *)this[6].Ptr;
    if ( v7 )
      wil::details::SetEvent(v7, v6);
    v8 = (WorkThreadManager::TaskData *)this[7].Ptr;
    this[7].Ptr = 0;
    if ( v8 )
      WorkThreadManager::TaskData::`scalar deleting destructor'(v8, (unsigned int)v6);
    LOBYTE(this[11].Ptr) = 0;
    v9 = 1;
    _InterlockedDecrement((volatile signed __int32 *)&WorkThreadManager::s_cThreadsStarting);
    do
    {
      while ( 1 )
      {
        if ( !this[24].Ptr )
        {
          v10 = HIDWORD(this[10].Ptr) == 1;
          if ( SHIDWORD(this[10].Ptr) > 1 )
          {
            WorkThreadManager::CThread::WaitForThreadUpdate((WorkThreadManager::CThread *)this, 0xFFFFFFFF);
            v10 = HIDWORD(this[10].Ptr) == 1;
          }
          if ( v10 )
          {
            v9 = 1;
            if ( LOBYTE(this[5].Ptr) || SHIDWORD(this[16].Ptr) > 1 )
            {
              WorkThreadManager::CThread::WaitForWork((WorkThreadManager::CThread *)this, (unsigned int)v6);
            }
            else
            {
              if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)&WorkThreadManager::s_cThreadsLingering) <= 0xA )
              {
                WorkThreadManager::CThread::WaitForWork((WorkThreadManager::CThread *)this, (unsigned int)v6);
                v9 = 0;
              }
              _InterlockedDecrement((volatile signed __int32 *)&WorkThreadManager::s_cThreadsLingering);
            }
          }
          if ( !this[24].Ptr )
            break;
        }
        WorkThreadManager::CThread::RunCurrentTaskUnderLock(this);
        WorkThreadManager::s_ClearOrGetNextTask((struct WorkThreadManager::CThread *)this);
      }
    }
    while ( SHIDWORD(this[10].Ptr) > 1
         || SHIDWORD(this[16].Ptr) > 1
         || !WorkThreadManager::s_TryRemoveThread((struct WorkThreadManager::CThread *)this, 0, v9) );
  }
  SHSetThreadRef(0);
  this[17].Ptr = 0;
  LODWORD(this[16].Ptr) = 0x7FFFFFFF;
  SetTlsSlotData(0);
  CoUninitialize();
}

```

## disassembly

```asm
0x18000c994  mov     [rsp+arg_8], rbx
0x18000c999  push    rdi
0x18000c99a  sub     rsp, 20h
0x18000c99e  mov     rbx, rcx
0x18000c9a1  call    GetCurrentThreadId_0
0x18000c9a6  mov     rdx, [rbx+70h]
0x18000c9aa  lea     rcx, [rsp+28h+arg_0]
0x18000c9af  mov     [rbx+50h], eax
0x18000c9b2  mov     [rdx+10h], eax
0x18000c9b5  mov     rdx, [rbx+78h]
0x18000c9b9  mov     eax, [rbx+50h]
0x18000c9bc  mov     [rdx+10h], eax
0x18000c9bf  mov     rdx, rbx
0x18000c9c2  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18000c9c7  mov     rcx, rax
0x18000c9ca  call    ??R_lambda_103564c3136a6d89c1bf4e8d5a4b0eab_@@QEBA@XZ; _lambda_103564c3136a6d89c1bf4e8d5a4b0eab_::operator()(void)
0x18000c9cf  mov     [rbx+2Ch], eax
0x18000c9d2  test    eax, eax
0x18000c9d4  js      loc_18000CAB9
0x18000c9da  mov     rcx, [rbx+30h]; this
0x18000c9de  test    rcx, rcx
0x18000c9e1  jz      short loc_18000C9E8
0x18000c9e3  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18000c9e8  mov     rcx, [rbx+38h]; this
0x18000c9ec  mov     qword ptr [rbx+38h], 0
0x18000c9f4  test    rcx, rcx
0x18000c9f7  jz      short loc_18000C9FE
0x18000c9f9  call    ??_GTaskData@WorkThreadManager@@QEAAPEAXI@Z; WorkThreadManager::TaskData::`scalar deleting destructor'(uint)
0x18000c9fe  mov     byte ptr [rbx+58h], 0
0x18000ca02  mov     dil, 1
0x18000ca05  lock dec cs:?s_cThreadsStarting@WorkThreadManager@@0KA; ulong WorkThreadManager::s_cThreadsStarting
0x18000ca0c  cmp     qword ptr [rbx+0C0h], 0
0x18000ca14  jz      short loc_18000CA28
0x18000ca16  mov     rcx, rbx; this
0x18000ca19  call    ?RunCurrentTaskUnderLock@CThread@WorkThreadManager@@QEAAXXZ; WorkThreadManager::CThread::RunCurrentTaskUnderLock(void)
0x18000ca1e  mov     rcx, rbx; struct WorkThreadManager::CThread *
0x18000ca21  call    ?s_ClearOrGetNextTask@WorkThreadManager@@CAXPEAVCThread@1@@Z; WorkThreadManager::s_ClearOrGetNextTask(WorkThreadManager::CThread *)
0x18000ca26  jmp     short loc_18000CA0C
0x18000ca28  cmp     dword ptr [rbx+54h], 1
0x18000ca2c  jle     short loc_18000CA3D
0x18000ca2e  or      edx, 0FFFFFFFFh; unsigned int
0x18000ca31  mov     rcx, rbx; this
0x18000ca34  call    ?WaitForThreadUpdate@CThread@WorkThreadManager@@AEAAJK@Z; WorkThreadManager::CThread::WaitForThreadUpdate(ulong)
0x18000ca39  cmp     dword ptr [rbx+54h], 1
0x18000ca3d  jnz     short loc_18000CA81
0x18000ca3f  cmp     byte ptr [rbx+28h], 0
0x18000ca43  mov     dil, 1
0x18000ca46  jnz     short loc_18000CA51
0x18000ca48  cmp     dword ptr [rbx+84h], 1
0x18000ca4f  jle     short loc_18000CA5B
0x18000ca51  mov     rcx, rbx; this
0x18000ca54  call    ?WaitForWork@CThread@WorkThreadManager@@AEAAXK@Z; WorkThreadManager::CThread::WaitForWork(ulong)
0x18000ca59  jmp     short loc_18000CA81
0x18000ca5b  mov     eax, 1
0x18000ca60  lock xadd cs:?s_cThreadsLingering@WorkThreadManager@@0KA, eax; ulong WorkThreadManager::s_cThreadsLingering
0x18000ca68  inc     eax
0x18000ca6a  cmp     eax, 0Ah
0x18000ca6d  ja      short loc_18000CA7A
0x18000ca6f  mov     rcx, rbx; this
0x18000ca72  call    ?WaitForWork@CThread@WorkThreadManager@@AEAAXK@Z; WorkThreadManager::CThread::WaitForWork(ulong)
0x18000ca77  xor     dil, dil
0x18000ca7a  lock dec cs:?s_cThreadsLingering@WorkThreadManager@@0KA; ulong WorkThreadManager::s_cThreadsLingering
0x18000ca81  cmp     qword ptr [rbx+0C0h], 0
0x18000ca89  jnz     short loc_18000CA16
0x18000ca8b  cmp     dword ptr [rbx+54h], 1
0x18000ca8f  jg      loc_18000CA0C
0x18000ca95  cmp     dword ptr [rbx+84h], 1
0x18000ca9c  jg      loc_18000CA0C
0x18000caa2  mov     r8b, dil; bool
0x18000caa5  xor     edx, edx; bool
0x18000caa7  mov     rcx, rbx; struct WorkThreadManager::CThread *
0x18000caaa  call    ?s_TryRemoveThread@WorkThreadManager@@CA_NPEAVCThread@1@_N1@Z; WorkThreadManager::s_TryRemoveThread(WorkThreadManager::CThread *,bool,bool)
0x18000caaf  test    al, al
0x18000cab1  jz      loc_18000CA0C
0x18000cab7  jmp     short loc_18000CB12
0x18000cab9  lea     rdx, [rbx+38h]
0x18000cabd  cmp     qword ptr [rdx], 0
0x18000cac1  jz      short loc_18000CAD5
0x18000cac3  lea     rcx, [rsp+28h+arg_0]
0x18000cac8  call    ??0?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>(wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>> &&)
0x18000cacd  mov     rcx, rax
0x18000cad0  call    ?s_AttachAndRecoverTask@WorkThreadManager@@CAXV?$unique_ptr@UTaskData@WorkThreadManager@@U?$default_delete@UTaskData@WorkThreadManager@@@wistd@@@wistd@@@Z; WorkThreadManager::s_AttachAndRecoverTask(wistd::unique_ptr<WorkThreadManager::TaskData,wistd::default_delete<WorkThreadManager::TaskData>>)
0x18000cad5  mov     rcx, [rbx+0A0h]; hEvent
0x18000cadc  test    rcx, rcx
0x18000cadf  jz      short loc_18000CAE7
0x18000cae1  call    cs:__imp_SetEvent
0x18000cae7  lock dec cs:?s_cThreadsStarting@WorkThreadManager@@0KA; ulong WorkThreadManager::s_cThreadsStarting
0x18000caee  xor     r8d, r8d; bool
0x18000caf1  mov     dl, 1; bool
0x18000caf3  mov     rcx, rbx; struct WorkThreadManager::CThread *
0x18000caf6  call    ?s_TryRemoveThread@WorkThreadManager@@CA_NPEAVCThread@1@_N1@Z; WorkThreadManager::s_TryRemoveThread(WorkThreadManager::CThread *,bool,bool)
0x18000cafb  lea     rcx, [rbx+18h]; this
0x18000caff  call    ?Clear@TaskList@WorkThreadManager@@QEAAXXZ; WorkThreadManager::TaskList::Clear(void)
0x18000cb04  mov     rcx, [rbx+30h]; this
0x18000cb08  test    rcx, rcx
0x18000cb0b  jz      short loc_18000CB12
0x18000cb0d  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18000cb12  xor     ecx, ecx; punk
0x18000cb14  call    cs:__imp_SHSetThreadRef
0x18000cb1a  xor     ecx, ecx; lpTlsValue
0x18000cb1c  mov     qword ptr [rbx+88h], 0
0x18000cb27  mov     dword ptr [rbx+80h], 7FFFFFFFh
0x18000cb31  call    SetTlsSlotData
0x18000cb36  mov     rbx, [rsp+28h+arg_8]
0x18000cb3b  add     rsp, 20h
0x18000cb3f  pop     rdi
0x18000cb40  jmp     cs:__imp_CoUninitialize
```
