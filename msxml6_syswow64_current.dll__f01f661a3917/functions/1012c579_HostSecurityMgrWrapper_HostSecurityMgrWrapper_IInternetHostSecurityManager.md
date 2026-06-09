# HostSecurityMgrWrapper::HostSecurityMgrWrapper(IInternetHostSecurityManager *)

- ea: `0x1012c579`
- end: `0x1012c62e`
- name: `??0HostSecurityMgrWrapper@@QAE@PAUIInternetHostSecurityManager@@@Z`
- size: `181`
- prototype: `HostSecurityMgrWrapper *__thiscall(HostSecurityMgrWrapper *this, IInternetHostSecurityManager *pHostSecMgr)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1012faef`
- `0x1012fb66`

## callees

- `0x1003f548`
- `0x10067bc0`
- `0x10128a79`
- `0x1012c532`
- `0x1012c550`
- `0x1012c579`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1012c5f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1012c5f3`

## pseudocode

```c
HostSecurityMgrWrapper *__thiscall HostSecurityMgrWrapper::HostSecurityMgrWrapper(
        HostSecurityMgrWrapper *this,
        IInternetHostSecurityManager *pHostSecMgr)
{
  HostSecurityMgrDispatchWrapper *v3; // eax
  HostSecurityMgrDispatchWrapper *v4; // edi
  DWORD CurrentThreadId; // eax
  IDispatch *pDisp; // [esp+Ch] [ebp-4h] BYREF

  _unknown<IInternetHostSecurityManager,&_GUID const IID_IInternetHostSecurityManager>::_unknown<IInternetHostSecurityManager,&_GUID const IID_IInternetHostSecurityManager>(this);
  this->_unknown<IInternetHostSecurityManager,&IID_IInternetHostSecurityManager>::IInternetHostSecurityManager::IUnknown::__vftable = (HostSecurityMgrWrapper_vtbl *)HostSecurityMgrWrapper::`vftable'{for `IInternetHostSecurityManager'};
  this->_unknown<IInternetHostSecurityManager,&IID_IInternetHostSecurityManager>::__unknown::_xunknown::__vftable = (__unknown_vtbl *)HostSecurityMgrWrapper::`vftable'{for `__unknown'};
  this->_pHostSecMgr = 0;
  this->_pNext = 0;
  v3 = (HostSecurityMgrDispatchWrapper *)_MemAlloc(0x14u, 4);
  v4 = HostSecurityMgrDispatchWrapper::HostSecurityMgrDispatchWrapper(v3, pHostSecMgr);
  pDisp = 0;
  ((void (__thiscall *)(HRESULT (__stdcall *)(IDispatch *, const _GUID *, void **), HostSecurityMgrDispatchWrapper *, GUID *, IDispatch **))v4->QueryInterface)(
    v4->QueryInterface,
    v4,
    &IID_IDispatch,
    &pDisp);
  ((void (__thiscall *)(unsigned int (__stdcall *)(IDispatch *), HostSecurityMgrDispatchWrapper *))v4->Release)(
    v4->Release,
    v4);
  if ( RegisterInterfaceInGlobal(pDisp, &IID_IDispatch, &this->_dwCookie) >= 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    this->_pHostSecMgr = pHostSecMgr;
    this->_dwMainThread = CurrentThreadId;
    ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IInternetHostSecurityManager *))pHostSecMgr->AddRef)(
      pHostSecMgr->AddRef,
      pHostSecMgr);
  }
  ((void (__thiscall *)(unsigned int (__stdcall *)(IUnknown *), IDispatch *))pDisp->Release)(pDisp->Release, pDisp);
  return this;
}

```

## disassembly

```asm
0x1012c579  mov     edi, edi
0x1012c57b  push    ebp
0x1012c57c  mov     ebp, esp
0x1012c57e  push    this
0x1012c57f  push    ebx
0x1012c580  push    esi
0x1012c581  push    edi
0x1012c582  mov     ebx, this
0x1012c584  call    ??0?$_unknown@UIInternetHostSecurityManager@@$1?IID_IInternetHostSecurityManager@@3U_GUID@@B@@QAE@XZ; _unknown<IInternetHostSecurityManager,&_GUID const IID_IInternetHostSecurityManager>::_unknown<IInternetHostSecurityManager,&_GUID const IID_IInternetHostSecurityManager>(void)
0x1012c589  push    4
0x1012c58b  pop     edx; dwFlags
0x1012c58c  push    14h
0x1012c58e  xor     esi, esi
0x1012c590  mov     dword ptr [ebx], offset ??_7HostSecurityMgrWrapper@@6BIInternetHostSecurityManager@@@; const HostSecurityMgrWrapper::`vftable'{for `IInternetHostSecurityManager'}
0x1012c596  pop     this; cb
0x1012c597  mov     dword ptr [ebx+4], offset ??_7HostSecurityMgrWrapper@@6B__unknown@@@; const HostSecurityMgrWrapper::`vftable'{for `__unknown'}
0x1012c59e  mov     [ebx+18h], esi
0x1012c5a1  mov     [ebx+1Ch], esi
0x1012c5a4  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x1012c5a9  push    [ebp+pHostSecMgr]; pIHSMgr
0x1012c5ac  mov     this, eax; this
0x1012c5ae  call    ??0HostSecurityMgrDispatchWrapper@@QAE@PAUIInternetHostSecurityManager@@@Z; HostSecurityMgrDispatchWrapper::HostSecurityMgrDispatchWrapper(IInternetHostSecurityManager *)
0x1012c5b3  mov     edi, eax
0x1012c5b5  mov     [ebp+pDisp], esi
0x1012c5b8  lea     eax, [ebp+pDisp]
0x1012c5bb  push    eax
0x1012c5bc  push    offset _IID_IDispatch
0x1012c5c1  mov     esi, [edi]
0x1012c5c3  push    edi
0x1012c5c4  mov     this, [esi]; this
0x1012c5c6  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012c5cc  call    dword ptr [esi]
0x1012c5ce  mov     eax, [edi]
0x1012c5d0  push    edi
0x1012c5d1  mov     esi, [eax+8]
0x1012c5d4  mov     this, esi; this
0x1012c5d6  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012c5dc  call    esi
0x1012c5de  mov     this, [ebp+pDisp]; ptr
0x1012c5e1  lea     eax, [ebx+14h]
0x1012c5e4  push    eax; pcookie
0x1012c5e5  mov     edx, offset _IID_IDispatch; iid
0x1012c5ea  call    ?RegisterInterfaceInGlobal@@YGJPAUIUnknown@@ABU_GUID@@PAK@Z; RegisterInterfaceInGlobal(IUnknown *,_GUID const &,ulong *)
0x1012c5ef  test    eax, eax
0x1012c5f1  js      short loc_1012C612
0x1012c5f3  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1012c5f9  mov     this, [ebp+pHostSecMgr]
0x1012c5fc  mov     [ebx+18h], this
0x1012c5ff  mov     [ebx+10h], eax
0x1012c602  push    this
0x1012c603  mov     eax, [this]
0x1012c605  mov     esi, [eax+4]
0x1012c608  mov     this, esi; this
0x1012c60a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012c610  call    esi
0x1012c612  mov     eax, [ebp+pDisp]
0x1012c615  push    eax
0x1012c616  mov     this, [eax]
0x1012c618  mov     esi, [this+8]
0x1012c61b  mov     this, esi; this
0x1012c61d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012c623  call    esi
0x1012c625  pop     edi
0x1012c626  pop     esi
0x1012c627  mov     eax, ebx
0x1012c629  pop     ebx
0x1012c62a  leave
0x1012c62b  retn    4
```
