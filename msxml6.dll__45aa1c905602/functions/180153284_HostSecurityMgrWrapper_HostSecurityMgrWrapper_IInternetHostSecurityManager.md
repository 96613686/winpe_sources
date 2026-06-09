# HostSecurityMgrWrapper::HostSecurityMgrWrapper(IInternetHostSecurityManager *)

- ea: `0x180153284`
- end: `0x180153370`
- name: `??0HostSecurityMgrWrapper@@QEAA@PEAUIInternetHostSecurityManager@@@Z`
- size: `236`
- prototype: `void __fastcall(HostSecurityMgrWrapper *this, IInternetHostSecurityManager *pHostSecMgr)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180156288`
- `0x180156318`

## callees

- `0x1800101e4`
- `0x180071be0`
- `0x18015322c`
- `0x180153250`
- `0x180153284`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180153329`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180153329`

## pseudocode

```c
void __fastcall HostSecurityMgrWrapper::HostSecurityMgrWrapper(
        HostSecurityMgrWrapper *this,
        IInternetHostSecurityManager *pHostSecMgr)
{
  HostSecurityMgrDispatchWrapper *v4; // rax
  void (__fastcall ***v5)(_QWORD, GUID *, IDispatch **); // rax
  void (__fastcall ***v6)(_QWORD, GUID *, IDispatch **); // rbx
  DWORD CurrentThreadId; // eax
  IDispatch *pDisp; // [rsp+30h] [rbp+8h] BYREF

  _unknown<IInternetHostSecurityManager,&_GUID const IID_IInternetHostSecurityManager>::_unknown<IInternetHostSecurityManager,&_GUID const IID_IInternetHostSecurityManager>(this);
  this->_pHostSecMgr = 0;
  this->_unknown<IInternetHostSecurityManager,&IID_IInternetHostSecurityManager>::IInternetHostSecurityManager::IUnknown::__vftable = (HostSecurityMgrWrapper_vtbl *)HostSecurityMgrWrapper::`vftable'{for `IInternetHostSecurityManager'};
  this->_pNext = 0;
  this->_unknown<IInternetHostSecurityManager,&IID_IInternetHostSecurityManager>::__unknown::_xunknown::__vftable = (__unknown_vtbl *)HostSecurityMgrWrapper::`vftable'{for `__unknown'};
  v4 = (HostSecurityMgrDispatchWrapper *)_MemAlloc(0x28u, 4u);
  HostSecurityMgrDispatchWrapper::HostSecurityMgrDispatchWrapper(v4, pHostSecMgr);
  v6 = v5;
  pDisp = 0;
  (**v5)(v5, &IID_IDispatch, &pDisp);
  ((void (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, IDispatch **)))(*v6)[2])(v6);
  if ( RegisterInterfaceInGlobal(pDisp, &IID_IDispatch, &this->_dwCookie) >= 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    this->_pHostSecMgr = pHostSecMgr;
    this->_dwMainThread = CurrentThreadId;
    pHostSecMgr->AddRef(pHostSecMgr);
  }
  pDisp->Release(pDisp);
}

```

## disassembly

```asm
0x180153284  mov     [rsp+arg_8], rbx
0x180153289  mov     [rsp+arg_10], rsi
0x18015328e  push    rdi
0x18015328f  sub     rsp, 20h
0x180153293  mov     rsi, pHostSecMgr
0x180153296  mov     rdi, this
0x180153299  call    ??0?$_unknown@UIInternetHostSecurityManager@@$1?IID_IInternetHostSecurityManager@@3U_GUID@@B@@QEAA@XZ; _unknown<IInternetHostSecurityManager,&_GUID const IID_IInternetHostSecurityManager>::_unknown<IInternetHostSecurityManager,&_GUID const IID_IInternetHostSecurityManager>(void)
0x18015329e  lea     this, ??_7HostSecurityMgrWrapper@@6BIInternetHostSecurityManager@@@; const HostSecurityMgrWrapper::`vftable'{for `IInternetHostSecurityManager'}
0x1801532a5  mov     qword ptr [rdi+28h], 0
0x1801532ad  mov     edx, 4; dwFlags
0x1801532b2  mov     [rdi], this
0x1801532b5  lea     rax, ??_7HostSecurityMgrWrapper@@6B__unknown@@@; const HostSecurityMgrWrapper::`vftable'{for `__unknown'}
0x1801532bc  mov     qword ptr [rdi+30h], 0
0x1801532c4  mov     [rdi+8], rax
0x1801532c8  lea     ecx, [pHostSecMgr+24h]; cb
0x1801532cb  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x1801532d0  mov     pHostSecMgr, rsi; pIHSMgr
0x1801532d3  mov     this, rax; this
0x1801532d6  call    ??0HostSecurityMgrDispatchWrapper@@QEAA@PEAUIInternetHostSecurityManager@@@Z; HostSecurityMgrDispatchWrapper::HostSecurityMgrDispatchWrapper(IInternetHostSecurityManager *)
0x1801532db  mov     rbx, rax
0x1801532de  mov     [rsp+28h+pDisp], 0
0x1801532e7  lea     r8, [rsp+28h+pDisp]
0x1801532ec  lea     pHostSecMgr, IID_IDispatch
0x1801532f3  mov     this, [rax]
0x1801532f6  mov     rax, [this]
0x1801532f9  mov     this, rbx
0x1801532fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180153301  mov     this, [rbx]
0x180153304  mov     rax, [this+10h]
0x180153308  mov     this, rbx
0x18015330b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180153310  mov     this, [rsp+28h+pDisp]; ptr
0x180153315  lea     r8, [rdi+24h]; pcookie
0x180153319  lea     pHostSecMgr, IID_IDispatch; iid
0x180153320  call    ?RegisterInterfaceInGlobal@@YAJPEAUIUnknown@@AEBU_GUID@@PEAK@Z; RegisterInterfaceInGlobal(IUnknown *,_GUID const &,ulong *)
0x180153325  test    eax, eax
0x180153327  js      short loc_18015334B
0x180153329  call    cs:__imp_GetCurrentThreadId
0x180153330  nop     dword ptr [rax+rax+00h]
0x180153335  mov     [rdi+28h], rsi
0x180153339  mov     this, rsi
0x18015333c  mov     [rdi+20h], eax
0x18015333f  mov     rax, [rsi]
0x180153342  mov     rax, [rax+8]
0x180153346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015334b  mov     this, [rsp+28h+pDisp]
0x180153350  mov     rax, [this]
0x180153353  mov     rax, [rax+10h]
0x180153357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015335c  mov     rbx, [rsp+28h+arg_8]
0x180153361  mov     rax, rdi
0x180153364  mov     rsi, [rsp+28h+arg_10]
0x180153369  add     rsp, 20h
0x18015336d  pop     rdi
0x18015336e  retn
```
