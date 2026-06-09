# COMSafeControlRoot::getSecurityManagerFromSite(IUnknown *,IInternetSecurityManager * *,IInternetHostSecurityManager * *)

- ea: `0x1012dcf2`
- end: `0x1012de4d`
- name: `?getSecurityManagerFromSite@COMSafeControlRoot@@SGJPAUIUnknown@@PAPAUIInternetSecurityManager@@PAPAUIInternetHostSecurityManager@@@Z`
- size: `347`
- prototype: `HRESULT __userpurge@<eax>(IUnknown *pSite@<ecx>, IInternetSecurityManager **ppISecMgr@<edx>, IInternetHostSecurityManager **ppIHostSecMgr)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1012c8a0`
- `0x1012df64`

## callees

- `0x1003f4b8`
- `0x1003fb13`
- `0x10040bb4`
- `0x10067b20`
- `0x1012dcf2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1012dd23`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1012dd23`

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
0x1012dcf2  mov     edi, edi
0x1012dcf4  push    ebp
0x1012dcf5  mov     ebp, esp
0x1012dcf7  sub     esp, 14h
0x1012dcfa  push    ebx
0x1012dcfb  push    esi
0x1012dcfc  push    edi
0x1012dcfd  lea     eax, [ebp+pInetSecMgrGlobal]
0x1012dd00  mov     esi, pSite
0x1012dd02  push    eax; ppv
0x1012dd03  xor     pSite, pSite
0x1012dd05  mov     [ebp+var_14], esi
0x1012dd08  push    offset _IID_IInternetSecurityManager; riid
0x1012dd0d  push    1; dwClsContext
0x1012dd0f  push    pSite; pUnkOuter
0x1012dd10  push    offset _CLSID_InternetSecurityManager; rclsid
0x1012dd15  mov     ebx, ppISecMgr
0x1012dd17  mov     [ebp+pInetSecMgrGlobal._p], pSite
0x1012dd1a  mov     [ebp+pInetSecMgrLocal._p], pSite
0x1012dd1d  mov     [ebp+pServiceProvider._p], pSite
0x1012dd20  mov     [ebp+pInetSecMgrSite._p], pSite
0x1012dd23  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x1012dd29  mov     edi, eax
0x1012dd2b  test    edi, edi
0x1012dd2d  js      loc_1012DDC9
0x1012dd33  mov     pSite, [esi]
0x1012dd35  lea     eax, [ebp+pServiceProvider]
0x1012dd38  push    eax
0x1012dd39  push    offset _IID_IServiceProvider
0x1012dd3e  push    [ebp+var_14]
0x1012dd41  mov     esi, [pSite]
0x1012dd43  mov     pSite, esi; this
0x1012dd45  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012dd4b  call    esi
0x1012dd4d  test    eax, eax
0x1012dd4f  js      CleanUp_426
0x1012dd55  mov     pSite, [ebp+pServiceProvider._p]
0x1012dd58  mov     eax, [pSite]
0x1012dd5a  mov     esi, [eax+0Ch]
0x1012dd5d  lea     eax, [ebp+pInetSecMgrLocal]
0x1012dd60  push    eax
0x1012dd61  mov     eax, offset _IID_IInternetSecurityManager
0x1012dd66  push    eax
0x1012dd67  push    eax
0x1012dd68  push    pSite
0x1012dd69  mov     pSite, esi; this
0x1012dd6b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012dd71  call    esi
0x1012dd73  test    eax, eax
0x1012dd75  js      loc_1012DE1D
0x1012dd7b  push    10h
0x1012dd7d  xor     ppISecMgr, ppISecMgr; dwFlags
0x1012dd7f  pop     pSite; cb
0x1012dd80  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x1012dd85  mov     esi, eax
0x1012dd87  test    esi, esi
0x1012dd89  jz      short loc_1012DDB2
0x1012dd8b  mov     ppISecMgr, [ebp+pInetSecMgrLocal._p]; pref
0x1012dd8e  lea     pSite, [esi+0Ch]; ppref
0x1012dd91  mov     dword ptr [esi], offset ??_7MsxmlInternetSecurityMgrSite@@6BIInternetSecurityMgrSite@@@; const MsxmlInternetSecurityMgrSite::`vftable'{for `IInternetSecurityMgrSite'}
0x1012dd97  mov     dword ptr [esi+4], offset ??_7MsxmlInternetSecurityMgrSite@@6BIServiceProvider@@@; const MsxmlInternetSecurityMgrSite::`vftable'{for `IServiceProvider'}
0x1012dd9e  mov     dword ptr [pSite], 0
0x1012dda4  mov     dword ptr [esi+8], 0
0x1012ddab  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1012ddb0  jmp     short loc_1012DDB4
0x1012ddb2  xor     esi, esi
0x1012ddb4  mov     ppISecMgr, esi; pref
0x1012ddb6  lea     pSite, [ebp+pInetSecMgrSite]; ppref
0x1012ddb9  call    ?assign@@YGXPAPAUIUnknown@@PAX@Z; assign(IUnknown * *,void *)
0x1012ddbe  cmp     [ebp+pInetSecMgrSite._p], 0
0x1012ddc2  jnz     short loc_1012DE01
0x1012ddc4  mov     edi, 8007000Eh
0x1012ddc9  mov     eax, [ebp+ppIHostSecMgr]
0x1012ddcc  mov     dword ptr [ebx], 0
0x1012ddd2  mov     dword ptr [eax], 0
0x1012ddd8  lea     pSite, [ebp+pInetSecMgrSite]; ppref
0x1012dddb  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1012dde0  lea     pSite, [ebp+pServiceProvider]; ppref
0x1012dde3  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1012dde8  lea     pSite, [ebp+pInetSecMgrLocal]; ppref
0x1012ddeb  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1012ddf0  lea     pSite, [ebp+pInetSecMgrGlobal]; ppref
0x1012ddf3  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1012ddf8  mov     eax, edi
0x1012ddfa  pop     edi
0x1012ddfb  pop     esi
0x1012ddfc  pop     ebx
0x1012ddfd  leave
0x1012ddfe  retn    4
0x1012de01  mov     pSite, [ebp+pInetSecMgrGlobal._p]
0x1012de04  push    [ebp+pInetSecMgrSite._p]
0x1012de07  push    pSite
0x1012de08  mov     eax, [pSite]
0x1012de0a  mov     esi, [eax+0Ch]
0x1012de0d  mov     pSite, esi; this
0x1012de0f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012de15  call    esi
0x1012de17  mov     edi, eax
0x1012de19  test    edi, edi
0x1012de1b  js      short loc_1012DDC9
0x1012de1d  cmp     [ebp+ppIHostSecMgr], 0
0x1012de21  jz      short CleanUp_426
0x1012de23  mov     eax, [ebp+pServiceProvider._p]
0x1012de26  mov     pSite, offset _IID_IInternetHostSecurityManager
0x1012de2b  push    [ebp+ppIHostSecMgr]
0x1012de2e  push    pSite
0x1012de2f  mov     esi, [eax]
0x1012de31  push    pSite
0x1012de32  push    eax
0x1012de33  mov     pSite, [esi+0Ch]; this
0x1012de36  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1012de3c  call    dword ptr [esi+0Ch]
0x1012de3f  mov     eax, [ebp+pInetSecMgrGlobal._p]
0x1012de42  mov     [ebp+pInetSecMgrGlobal._p], 0
0x1012de49  mov     [ebx], eax
0x1012de4b  jmp     short loc_1012DDD8
```
