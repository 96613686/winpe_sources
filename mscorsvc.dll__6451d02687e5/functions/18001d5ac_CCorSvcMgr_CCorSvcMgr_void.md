# CCorSvcMgr::~CCorSvcMgr(void)

- ea: `0x18001d5ac`
- end: `0x18001d773`
- name: `??1CCorSvcMgr@@QEAA@XZ`
- size: `455`
- prototype: `void __fastcall(CCorSvcMgr *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x18002d380`

## callees

- `0x1800011d0`
- `0x180006aa8`
- `0x180013954`
- `0x18001d5ac`
- `0x18002d960`
- `0x18002dae8`
- `0x18003f280`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001d664`
- `KERNEL32!DeleteCriticalSection` at `0x18001d664`
- `KERNEL32!CloseHandle` at `0x18001d6a6`
- `KERNEL32!CloseHandle` at `0x18001d6a6`
- `ole32!CoUninitialize` at `0x18001d657`
- `ole32!CoUninitialize` at `0x18001d657`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d6d0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d6ed`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d70a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d71f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d740`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d6d0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d6ed`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d70a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d71f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d740`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall CCorSvcMgr::~CCorSvcMgr(CCorSvcMgr *this)
{
  __int64 v2; // rcx
  HANDLE *v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  OLECHAR *v7; // rcx

  *(_QWORD *)this = &CCorSvcMgr::`vftable'{for `ICorSvcInstaller'};
  *((_QWORD *)this + 1) = &CCorSvcMgr::`vftable'{for `ICorSvcAdvancedInstaller'};
  *((_QWORD *)this + 2) = &CCorSvcMgr::`vftable'{for `ICorSvcOptimizer3'};
  *((_QWORD *)this + 3) = &CCorSvcMgr::`vftable'{for `ICorSvcLogger'};
  *((_QWORD *)this + 4) = &CCorSvcMgr::`vftable'{for `ICorSvcRepository'};
  *((_QWORD *)this + 5) = &CCorSvcMgr::`vftable'{for `ICorSvcSetPrivateAttributes'};
  *((_QWORD *)this + 6) = &CCorSvcMgr::`vftable'{for `ICorSvcManager'};
  *((_QWORD *)this + 7) = &CCorSvcMgr::`vftable'{for `ICorSvcManager2'};
  *((_QWORD *)this + 8) = &CCorSvcMgr::`vftable'{for `ICorSvcSetLegacyServiceBehavior'};
  *((_QWORD *)this + 9) = &CCorSvcMgr::`vftable'{for `ICorSvcSetTaskBootTriggerState'};
  *((_QWORD *)this + 10) = &CCorSvcMgr::`vftable'{for `ICorSvcSetTaskDelayStartTriggerState'};
  v2 = *((_QWORD *)this + 12);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 12) = 0;
  }
  CoUninitialize();
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  if ( _InterlockedExchangeAdd(&CCorSvcMgr::corSvcMgrCount, 0xFFFFFFFF) == 1 )
    DeleteRootList();
  AssemblyExclusion::~AssemblyExclusion((CCorSvcMgr *)((char *)this + 1320));
  v3 = (HANDLE *)((char *)this + 1296);
  if ( *((_DWORD *)this + 326) )
  {
    if ( *v3 )
      CloseHandle(*v3);
    *((_DWORD *)this + 326) = 0;
  }
  ThreadPool::~ThreadPool((CCorSvcMgr *)((char *)this + 352));
  if ( *((_DWORD *)this + 84) )
  {
    SysFreeString(*((BSTR *)this + 41));
    *((_DWORD *)this + 84) = 0;
  }
  if ( *((_DWORD *)this + 80) )
  {
    SysFreeString(*((BSTR *)this + 39));
    *((_DWORD *)this + 80) = 0;
  }
  if ( *((_DWORD *)this + 76) )
  {
    SysFreeString(*((BSTR *)this + 37));
    *((_DWORD *)this + 76) = 0;
  }
  v7 = (OLECHAR *)*((_QWORD *)this + 35);
  if ( v7 )
  {
    SysFreeString(v7);
    *((_QWORD *)this + 35) = 0;
  }
  if ( *((_DWORD *)this + 64) )
  {
    SysFreeString(*((BSTR *)this + 31));
    *((_DWORD *)this + 64) = 0;
  }
  SArray<SString,0>::~SArray<SString,0>((char *)this + 224, v4, v5, v6);
  WorkQueue::~WorkQueue((CCorSvcMgr *)((char *)this + 104));
}

```

## disassembly

```asm
0x18001d5ac  mov     [rsp+arg_10], rbx
0x18001d5b1  mov     [rsp+arg_18], rsi
0x18001d5b6  mov     [rsp+arg_0], rcx
0x18001d5bb  push    rdi
0x18001d5bc  sub     rsp, 20h
0x18001d5c0  mov     rbx, rcx
0x18001d5c3  lea     rax, ??_7CCorSvcMgr@@6BICorSvcInstaller@@@; const CCorSvcMgr::`vftable'{for `ICorSvcInstaller'}
0x18001d5ca  mov     [rcx], rax
0x18001d5cd  lea     rax, ??_7CCorSvcMgr@@6BICorSvcAdvancedInstaller@@@; const CCorSvcMgr::`vftable'{for `ICorSvcAdvancedInstaller'}
0x18001d5d4  mov     [rcx+8], rax
0x18001d5d8  lea     rax, ??_7CCorSvcMgr@@6BICorSvcOptimizer3@@@; const CCorSvcMgr::`vftable'{for `ICorSvcOptimizer3'}
0x18001d5df  mov     [rcx+10h], rax
0x18001d5e3  lea     rax, ??_7CCorSvcMgr@@6BICorSvcLogger@@@; const CCorSvcMgr::`vftable'{for `ICorSvcLogger'}
0x18001d5ea  mov     [rcx+18h], rax
0x18001d5ee  lea     rax, ??_7CCorSvcMgr@@6BICorSvcRepository@@@; const CCorSvcMgr::`vftable'{for `ICorSvcRepository'}
0x18001d5f5  mov     [rcx+20h], rax
0x18001d5f9  lea     rax, ??_7CCorSvcMgr@@6BICorSvcSetPrivateAttributes@@@; const CCorSvcMgr::`vftable'{for `ICorSvcSetPrivateAttributes'}
0x18001d600  mov     [rcx+28h], rax
0x18001d604  lea     rax, ??_7CCorSvcMgr@@6BICorSvcManager@@@; const CCorSvcMgr::`vftable'{for `ICorSvcManager'}
0x18001d60b  mov     [rcx+30h], rax
0x18001d60f  lea     rax, ??_7CCorSvcMgr@@6BICorSvcManager2@@@; const CCorSvcMgr::`vftable'{for `ICorSvcManager2'}
0x18001d616  mov     [rcx+38h], rax
0x18001d61a  lea     rax, ??_7CCorSvcMgr@@6BICorSvcSetLegacyServiceBehavior@@@; const CCorSvcMgr::`vftable'{for `ICorSvcSetLegacyServiceBehavior'}
0x18001d621  mov     [rcx+40h], rax
0x18001d625  lea     rax, ??_7CCorSvcMgr@@6BICorSvcSetTaskBootTriggerState@@@; const CCorSvcMgr::`vftable'{for `ICorSvcSetTaskBootTriggerState'}
0x18001d62c  mov     [rcx+48h], rax
0x18001d630  lea     rax, ??_7CCorSvcMgr@@6BICorSvcSetTaskDelayStartTriggerState@@@; const CCorSvcMgr::`vftable'{for `ICorSvcSetTaskDelayStartTriggerState'}
0x18001d637  mov     [rcx+50h], rax
0x18001d63b  mov     rcx, [rcx+60h]
0x18001d63f  xor     esi, esi
0x18001d641  test    rcx, rcx
0x18001d644  jz      short loc_18001D657
0x18001d646  mov     rax, [rcx]
0x18001d649  mov     rax, [rax+10h]
0x18001d64d  call    cs:__guard_dispatch_icall_fptr
0x18001d653  mov     [rbx+60h], rsi
0x18001d657  call    cs:__imp_CoUninitialize
0x18001d65d  lea     rcx, [rbx+98h]; lpCriticalSection
0x18001d664  call    cs:__imp_DeleteCriticalSection
0x18001d66a  or      eax, 0FFFFFFFFh
0x18001d66d  lock xadd cs:?corSvcMgrCount@CCorSvcMgr@@0JA, eax; long CCorSvcMgr::corSvcMgrCount
0x18001d675  cmp     eax, 1
0x18001d678  jnz     short loc_18001D680
0x18001d67a  call    ?DeleteRootList@@YAXXZ; DeleteRootList(void)
0x18001d67f  nop
0x18001d680  lea     rcx, [rbx+528h]; this
0x18001d687  call    ??1AssemblyExclusion@@QEAA@XZ; AssemblyExclusion::~AssemblyExclusion(void)
0x18001d68c  nop
0x18001d68d  lea     rdi, [rbx+510h]
0x18001d694  mov     [rsp+28h+arg_8], rdi
0x18001d699  cmp     [rdi+8], esi
0x18001d69c  jz      short loc_18001D6AF
0x18001d69e  mov     rcx, [rdi]; hObject
0x18001d6a1  test    rcx, rcx
0x18001d6a4  jz      short loc_18001D6AC
0x18001d6a6  call    cs:__imp_CloseHandle
0x18001d6ac  mov     [rdi+8], esi
0x18001d6af  lea     rcx, [rbx+160h]; this
0x18001d6b6  call    ??1ThreadPool@@QEAA@XZ; ThreadPool::~ThreadPool(void)
0x18001d6bb  nop
0x18001d6bc  lea     rdi, [rbx+148h]
0x18001d6c3  mov     [rsp+28h+arg_8], rdi
0x18001d6c8  cmp     [rdi+8], esi
0x18001d6cb  jz      short loc_18001D6D9
0x18001d6cd  mov     rcx, [rdi]; bstrString
0x18001d6d0  call    cs:__imp_SysFreeString
0x18001d6d6  mov     [rdi+8], esi
0x18001d6d9  lea     rdi, [rbx+138h]
0x18001d6e0  mov     [rsp+28h+arg_8], rdi
0x18001d6e5  cmp     [rdi+8], esi
0x18001d6e8  jz      short loc_18001D6F6
0x18001d6ea  mov     rcx, [rdi]; bstrString
0x18001d6ed  call    cs:__imp_SysFreeString
0x18001d6f3  mov     [rdi+8], esi
0x18001d6f6  lea     rdi, [rbx+128h]
0x18001d6fd  mov     [rsp+28h+arg_8], rdi
0x18001d702  cmp     [rdi+8], esi
0x18001d705  jz      short loc_18001D713
0x18001d707  mov     rcx, [rdi]; bstrString
0x18001d70a  call    cs:__imp_SysFreeString
0x18001d710  mov     [rdi+8], esi
0x18001d713  mov     rcx, [rbx+118h]; bstrString
0x18001d71a  test    rcx, rcx
0x18001d71d  jz      short loc_18001D72C
0x18001d71f  call    cs:__imp_SysFreeString
0x18001d725  mov     [rbx+118h], rsi
0x18001d72c  lea     rdi, [rbx+0F8h]
0x18001d733  mov     [rsp+28h+arg_8], rdi
0x18001d738  cmp     [rdi+8], esi
0x18001d73b  jz      short loc_18001D749
0x18001d73d  mov     rcx, [rdi]; bstrString
0x18001d740  call    cs:__imp_SysFreeString
0x18001d746  mov     [rdi+8], esi
0x18001d749  lea     rcx, [rbx+0E0h]
0x18001d750  mov     [rsp+28h+arg_8], rcx
0x18001d755  call    ??1?$SArray@VSString@@$0A@@@QEAA@XZ; SArray<SString,0>::~SArray<SString,0>(void)
0x18001d75a  nop
0x18001d75b  lea     rcx, [rbx+68h]; this
0x18001d75f  mov     rbx, [rsp+28h+arg_10]
0x18001d764  mov     rsi, [rsp+28h+arg_18]
0x18001d769  add     rsp, 20h
0x18001d76d  pop     rdi
0x18001d76e  jmp     ??1WorkQueue@@QEAA@XZ; WorkQueue::~WorkQueue(void)
```
