# HostSecurityMgrWrapper::HostSecurityMgrWrapper(IInternetHostSecurityManager *)

- ea: `0x1012c68b`
- end: `0x1012c740`
- name: `??0HostSecurityMgrWrapper@@QAE@PAUIInternetHostSecurityManager@@@Z`
- size: `181`
- prototype: `HostSecurityMgrWrapper *__thiscall(HostSecurityMgrWrapper *this, IInternetHostSecurityManager *pHostSecMgr)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1012fbff`
- `0x1012fc76`

## callees

- `0x1003f4b8`
- `0x10067b20`
- `0x10128b89`
- `0x1012c644`
- `0x1012c662`
- `0x1012c68b`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1012c705`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1012c705`

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
  v3 = (HostSecurityMgrDispatchWrapper *)_MemAlloc(0x14u, 4u);
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
0x1012c68b  mov     edi, edi
0x1012c68d  push    ebp
0x1012c68e  mov     ebp, esp
0x1012c690  push    this
0x1012c691  push    ebx
0x1012c692  push    esi
0x1012c693  push    edi
0x1012c694  mov     ebx, this
0x1012c696  call    ??0?$_unknown@UIInternetHostSecurityManager@@$1?IID_IInternetHostSecurityManager@@3U_GUID@@B@@QAE@XZ; _unknown<IInternetHostSecurityManager,&_GUID const IID_IInternetHostSecurityManager>::_unknown<IInternetHostSecurityManager,&_GUID const IID_IInternetHostSecurityManager>(void)
0x1012c69b  push    4
0x1012c69d  pop     edx; dwFlags
0x1012c69e  push    14h
0x1012c6a0  xor     esi, esi
0x1012c6a2  mov     dword ptr [ebx], offset ??_7HostSecurityMgrWrapper@@6BIInternetHostSecurityManager@@@; const HostSecurityMgrWrapper::`vftable'{for `IInternetHostSecurityManager'}
0x1012c6a8  pop     this; cb
0x1012c6a9  mov     dword ptr [ebx+4], offset ??_7HostSecurityMgrWrapper@@6B__unknown@@@; const HostSecurityMgrWrapper::`vftable'{for `__unknown'}
0x1012c6b0  mov     [ebx+18h], esi
0x1012c6b3  mov     [ebx+1Ch], esi
0x1012c6b6  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x1012c6bb  push    [ebp+pHostSecMgr]; pIHSMgr
0x1012c6be  mov     this, eax; this
0x1012c6c0  call    ??0HostSecurityMgrDispatchWrapper@@QAE@PAUIInternetHostSecurityManager@@@Z; HostSecurityMgrDispatchWrapper::HostSecurityMgrDispatchWrapper(IInternetHostSecurityManager *)
0x1012c6c5  mov     edi, eax
0x1012c6c7  mov     [ebp+pDisp], esi
0x1012c6ca  lea     eax, [ebp+pDisp]
0x1012c6cd  push    eax
0x1012c6ce  push    offset _IID_IDispatch
0x1012c6d3  mov     esi, [edi]
0x1012c6d5  push    edi
0x1012c6d6  mov     this, [esi]; this
0x1012c6d8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012c6de  call    dword ptr [esi]
0x1012c6e0  mov     eax, [edi]
0x1012c6e2  push    edi
0x1012c6e3  mov     esi, [eax+8]
0x1012c6e6  mov     this, esi; this
0x1012c6e8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012c6ee  call    esi
0x1012c6f0  mov     this, [ebp+pDisp]; ptr
0x1012c6f3  lea     eax, [ebx+14h]
0x1012c6f6  push    eax; pcookie
0x1012c6f7  mov     edx, offset _IID_IDispatch; iid
0x1012c6fc  call    ?RegisterInterfaceInGlobal@@YGJPAUIUnknown@@ABU_GUID@@PAK@Z; RegisterInterfaceInGlobal(IUnknown *,_GUID const &,ulong *)
0x1012c701  test    eax, eax
0x1012c703  js      short loc_1012C724
0x1012c705  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1012c70b  mov     this, [ebp+pHostSecMgr]
0x1012c70e  mov     [ebx+18h], this
0x1012c711  mov     [ebx+10h], eax
0x1012c714  push    this
0x1012c715  mov     eax, [this]
0x1012c717  mov     esi, [eax+4]
0x1012c71a  mov     this, esi; this
0x1012c71c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012c722  call    esi
0x1012c724  mov     eax, [ebp+pDisp]
0x1012c727  push    eax
0x1012c728  mov     this, [eax]
0x1012c72a  mov     esi, [this+8]
0x1012c72d  mov     this, esi; this
0x1012c72f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012c735  call    esi
0x1012c737  pop     edi
0x1012c738  pop     esi
0x1012c739  mov     eax, ebx
0x1012c73b  pop     ebx
0x1012c73c  leave
0x1012c73d  retn    4
```
