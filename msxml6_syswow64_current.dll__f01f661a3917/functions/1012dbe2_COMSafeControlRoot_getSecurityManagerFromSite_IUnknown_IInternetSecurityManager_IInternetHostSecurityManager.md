# COMSafeControlRoot::getSecurityManagerFromSite(IUnknown *,IInternetSecurityManager * *,IInternetHostSecurityManager * *)

- ea: `0x1012dbe2`
- end: `0x1012dd3d`
- name: `?getSecurityManagerFromSite@COMSafeControlRoot@@SGJPAUIUnknown@@PAPAUIInternetSecurityManager@@PAPAUIInternetHostSecurityManager@@@Z`
- size: `347`
- prototype: `HRESULT __userpurge@<eax>(IUnknown *pSite@<ecx>, IInternetSecurityManager **ppISecMgr@<edx>, IInternetHostSecurityManager **ppIHostSecMgr)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1012c790`
- `0x1012de54`

## callees

- `0x1003f548`
- `0x1003fba3`
- `0x10040c44`
- `0x10067bc0`
- `0x1012dbe2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1012dc13`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1012dc13`

## pseudocode

```c
HRESULT __fastcall COMSafeControlRoot::getSecurityManagerFromSite(
        IUnknown *pSite,
        IInternetSecurityManager **ppISecMgr,
        IInternetHostSecurityManager **ppIHostSecMgr)
{
  HRESULT Instance; // edi
  IUnknown **v6; // eax
  IUnknown **v7; // esi
  IInternetSecurityManager *v8; // edx
  IInternetSecurityManager *p; // eax
  _reference<IInternetSecurityManager> pInetSecMgrLocal; // [esp+10h] [ebp-10h] BYREF
  _reference<IServiceProvider> pServiceProvider; // [esp+14h] [ebp-Ch] BYREF
  _reference<IInternetSecurityMgrSite> pInetSecMgrSite; // [esp+18h] [ebp-8h] BYREF
  _reference<IInternetSecurityManager> pInetSecMgrGlobal; // [esp+1Ch] [ebp-4h] BYREF

  pInetSecMgrGlobal._p = 0;
  pInetSecMgrLocal._p = 0;
  pServiceProvider._p = 0;
  pInetSecMgrSite._p = 0;
  Instance = CoCreateInstance(
               &CLSID_InternetSecurityManager,
               0,
               1u,
               &IID_IInternetSecurityManager,
               (LPVOID *)&pInetSecMgrGlobal._p);
  if ( Instance < 0 )
    goto LABEL_9;
  if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IUnknown *, GUID *, _reference<IServiceProvider> *))pSite->QueryInterface)(
         pSite->QueryInterface,
         pSite,
         &IID_IServiceProvider,
         &pServiceProvider) < 0 )
  {
CleanUp_426:
    p = pInetSecMgrGlobal._p;
    pInetSecMgrGlobal._p = 0;
    *ppISecMgr = p;
    goto LABEL_10;
  }
  if ( ((int (__thiscall *)(HRESULT (__stdcall *)(IServiceProvider *, const _GUID *, const _GUID *, void **), IServiceProvider *, GUID *, GUID *, _reference<IInternetSecurityManager> *))pServiceProvider._p->QueryService)(
         pServiceProvider._p->QueryService,
         pServiceProvider._p,
         &IID_IInternetSecurityManager,
         &IID_IInternetSecurityManager,
         &pInetSecMgrLocal) < 0 )
  {
LABEL_12:
    if ( ppIHostSecMgr )
      ((void (__thiscall *)(HRESULT (__stdcall *)(IServiceProvider *, const _GUID *, const _GUID *, void **), IServiceProvider *, GUID *, GUID *, IInternetHostSecurityManager **))pServiceProvider._p->QueryService)(
        pServiceProvider._p->QueryService,
        pServiceProvider._p,
        &IID_IInternetHostSecurityManager,
        &IID_IInternetHostSecurityManager,
        ppIHostSecMgr);
    goto CleanUp_426;
  }
  v6 = (IUnknown **)_MemAlloc(0x10u, 0);
  v7 = v6;
  if ( v6 )
  {
    v8 = pInetSecMgrLocal._p;
    *v6 = (IUnknown *)MsxmlInternetSecurityMgrSite::`vftable'{for `IInternetSecurityMgrSite'};
    v6[1] = (IUnknown *)MsxmlInternetSecurityMgrSite::`vftable'{for `IServiceProvider'};
    v6[3] = 0;
    v6[2] = 0;
    assign(v6 + 3, v8);
  }
  else
  {
    v7 = 0;
  }
  assign(&pInetSecMgrSite._p, v7);
  if ( pInetSecMgrSite._p )
  {
    Instance = ((int (__thiscall *)(HRESULT (__stdcall *)(IInternetSecurityManager *, IInternetSecurityMgrSite *), IInternetSecurityManager *, IInternetSecurityMgrSite *))pInetSecMgrGlobal._p->SetSecuritySite)(
                 pInetSecMgrGlobal._p->SetSecuritySite,
                 pInetSecMgrGlobal._p,
                 pInetSecMgrSite._p);
    if ( Instance < 0 )
      goto LABEL_9;
    goto LABEL_12;
  }
  Instance = -2147024882;
LABEL_9:
  *ppISecMgr = 0;
  *ppIHostSecMgr = 0;
LABEL_10:
  release(&pInetSecMgrSite._p);
  release(&pServiceProvider._p);
  release(&pInetSecMgrLocal._p);
  release(&pInetSecMgrGlobal._p);
  return Instance;
}

```

## disassembly

```asm
0x1012dbe2  mov     edi, edi
0x1012dbe4  push    ebp
0x1012dbe5  mov     ebp, esp
0x1012dbe7  sub     esp, 14h
0x1012dbea  push    ebx
0x1012dbeb  push    esi
0x1012dbec  push    edi
0x1012dbed  lea     eax, [ebp+pInetSecMgrGlobal]
0x1012dbf0  mov     esi, pSite
0x1012dbf2  push    eax; ppv
0x1012dbf3  xor     pSite, pSite
0x1012dbf5  mov     [ebp+var_14], esi
0x1012dbf8  push    offset _IID_IInternetSecurityManager; riid
0x1012dbfd  push    1; dwClsContext
0x1012dbff  push    pSite; pUnkOuter
0x1012dc00  push    offset _CLSID_InternetSecurityManager; rclsid
0x1012dc05  mov     ebx, ppISecMgr
0x1012dc07  mov     [ebp+pInetSecMgrGlobal._p], pSite
0x1012dc0a  mov     [ebp+pInetSecMgrLocal._p], pSite
0x1012dc0d  mov     [ebp+pServiceProvider._p], pSite
0x1012dc10  mov     [ebp+pInetSecMgrSite._p], pSite
0x1012dc13  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x1012dc19  mov     edi, eax
0x1012dc1b  test    edi, edi
0x1012dc1d  js      loc_1012DCB9
0x1012dc23  mov     pSite, [esi]
0x1012dc25  lea     eax, [ebp+pServiceProvider]
0x1012dc28  push    eax
0x1012dc29  push    offset _IID_IServiceProvider
0x1012dc2e  push    [ebp+var_14]
0x1012dc31  mov     esi, [pSite]
0x1012dc33  mov     pSite, esi; this
0x1012dc35  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012dc3b  call    esi
0x1012dc3d  test    eax, eax
0x1012dc3f  js      CleanUp_426
0x1012dc45  mov     pSite, [ebp+pServiceProvider._p]
0x1012dc48  mov     eax, [pSite]
0x1012dc4a  mov     esi, [eax+0Ch]
0x1012dc4d  lea     eax, [ebp+pInetSecMgrLocal]
0x1012dc50  push    eax
0x1012dc51  mov     eax, offset _IID_IInternetSecurityManager
0x1012dc56  push    eax
0x1012dc57  push    eax
0x1012dc58  push    pSite
0x1012dc59  mov     pSite, esi; this
0x1012dc5b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012dc61  call    esi
0x1012dc63  test    eax, eax
0x1012dc65  js      loc_1012DD0D
0x1012dc6b  push    10h
0x1012dc6d  xor     ppISecMgr, ppISecMgr; dwFlags
0x1012dc6f  pop     pSite; cb
0x1012dc70  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x1012dc75  mov     esi, eax
0x1012dc77  test    esi, esi
0x1012dc79  jz      short loc_1012DCA2
0x1012dc7b  mov     ppISecMgr, [ebp+pInetSecMgrLocal._p]; pref
0x1012dc7e  lea     pSite, [esi+0Ch]; ppref
0x1012dc81  mov     dword ptr [esi], offset ??_7MsxmlInternetSecurityMgrSite@@6BIInternetSecurityMgrSite@@@; const MsxmlInternetSecurityMgrSite::`vftable'{for `IInternetSecurityMgrSite'}
0x1012dc87  mov     dword ptr [esi+4], offset ??_7MsxmlInternetSecurityMgrSite@@6BIServiceProvider@@@; const MsxmlInternetSecurityMgrSite::`vftable'{for `IServiceProvider'}
0x1012dc8e  mov     dword ptr [pSite], 0
0x1012dc94  mov     dword ptr [esi+8], 0
0x1012dc9b  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1012dca0  jmp     short loc_1012DCA4
0x1012dca2  xor     esi, esi
0x1012dca4  mov     ppISecMgr, esi; pref
0x1012dca6  lea     pSite, [ebp+pInetSecMgrSite]; ppref
0x1012dca9  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1012dcae  cmp     [ebp+pInetSecMgrSite._p], 0
0x1012dcb2  jnz     short loc_1012DCF1
0x1012dcb4  mov     edi, 8007000Eh
0x1012dcb9  mov     eax, [ebp+ppIHostSecMgr]
0x1012dcbc  mov     dword ptr [ebx], 0
0x1012dcc2  mov     dword ptr [eax], 0
0x1012dcc8  lea     pSite, [ebp+pInetSecMgrSite]; ppref
0x1012dccb  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1012dcd0  lea     pSite, [ebp+pServiceProvider]; ppref
0x1012dcd3  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1012dcd8  lea     pSite, [ebp+pInetSecMgrLocal]; ppref
0x1012dcdb  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1012dce0  lea     pSite, [ebp+pInetSecMgrGlobal]; ppref
0x1012dce3  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1012dce8  mov     eax, edi
0x1012dcea  pop     edi
0x1012dceb  pop     esi
0x1012dcec  pop     ebx
0x1012dced  leave
0x1012dcee  retn    4
0x1012dcf1  mov     pSite, [ebp+pInetSecMgrGlobal._p]
0x1012dcf4  push    [ebp+pInetSecMgrSite._p]
0x1012dcf7  push    pSite
0x1012dcf8  mov     eax, [pSite]
0x1012dcfa  mov     esi, [eax+0Ch]
0x1012dcfd  mov     pSite, esi; this
0x1012dcff  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012dd05  call    esi
0x1012dd07  mov     edi, eax
0x1012dd09  test    edi, edi
0x1012dd0b  js      short loc_1012DCB9
0x1012dd0d  cmp     [ebp+ppIHostSecMgr], 0
0x1012dd11  jz      short CleanUp_426
0x1012dd13  mov     eax, [ebp+pServiceProvider._p]
0x1012dd16  mov     pSite, offset _IID_IInternetHostSecurityManager
0x1012dd1b  push    [ebp+ppIHostSecMgr]
0x1012dd1e  push    pSite
0x1012dd1f  mov     esi, [eax]
0x1012dd21  push    pSite
0x1012dd22  push    eax
0x1012dd23  mov     pSite, [esi+0Ch]; this
0x1012dd26  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012dd2c  call    dword ptr [esi+0Ch]
0x1012dd2f  mov     eax, [ebp+pInetSecMgrGlobal._p]
0x1012dd32  mov     [ebp+pInetSecMgrGlobal._p], 0
0x1012dd39  mov     [ebx], eax
0x1012dd3b  jmp     short loc_1012DCC8
```
