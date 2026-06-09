# COMSafeControlRoot::getSecurityManagerFromSite(IUnknown *,IInternetSecurityManager * *,IInternetHostSecurityManager * *)

- ea: `0x180154ce4`
- end: `0x180154e94`
- name: `?getSecurityManagerFromSite@COMSafeControlRoot@@SAJPEAUIUnknown@@PEAPEAUIInternetSecurityManager@@PEAPEAUIInternetHostSecurityManager@@@Z`
- size: `432`
- prototype: `HRESULT __fastcall(IUnknown *pSite, IInternetSecurityManager **ppISecMgr, IInternetHostSecurityManager **ppIHostSecMgr)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180153540`
- `0x180154f9c`

## callees

- `0x1800101e4`
- `0x180015a80`
- `0x180019e20`
- `0x180154ce4`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180154d3f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180154d3f`

## pseudocode

```c
__int64 __fastcall COMSafeControlRoot::getSecurityManagerFromSite(
        IUnknown *pSite,
        IInternetSecurityManager **ppISecMgr,
        IInternetHostSecurityManager **ppIHostSecMgr)
{
  HRESULT Instance; // ebx
  IUnknown **v7; // rax
  IUnknown **v8; // rbx
  IInternetSecurityManager *p; // rdx
  _reference<IServiceProvider> pServiceProvider; // [rsp+30h] [rbp-20h] BYREF
  _reference<IInternetSecurityMgrSite> pInetSecMgrSite; // [rsp+38h] [rbp-18h] BYREF
  _reference<IInternetSecurityManager> pInetSecMgrLocal; // [rsp+40h] [rbp-10h] BYREF
  _reference<IInternetSecurityManager> pInetSecMgrGlobal; // [rsp+88h] [rbp+38h] BYREF

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
  if ( pSite->QueryInterface(pSite, &IID_IServiceProvider, (void **)&pServiceProvider) < 0 )
  {
$CleanUp_490:
    *ppISecMgr = pInetSecMgrGlobal._p;
    pInetSecMgrGlobal._p = 0;
    goto LABEL_10;
  }
  if ( pServiceProvider._p->QueryService(
         pServiceProvider._p,
         &IID_IInternetSecurityManager,
         &IID_IInternetSecurityManager,
         (void **)&pInetSecMgrLocal) < 0 )
  {
LABEL_12:
    if ( ppIHostSecMgr )
      pServiceProvider._p->QueryService(
        pServiceProvider._p,
        &IID_IInternetHostSecurityManager,
        &IID_IInternetHostSecurityManager,
        (void **)ppIHostSecMgr);
    goto $CleanUp_490;
  }
  v7 = (IUnknown **)_MemAlloc(0x20u, 0);
  v8 = v7;
  if ( v7 )
  {
    p = pInetSecMgrLocal._p;
    *v7 = (IUnknown *)MsxmlInternetSecurityMgrSite::`vftable'{for `IInternetSecurityMgrSite'};
    v7[1] = (IUnknown *)MsxmlInternetSecurityMgrSite::`vftable'{for `IServiceProvider'};
    v7[3] = 0;
    *((_DWORD *)v7 + 4) = 0;
    assign(v7 + 3, p);
  }
  else
  {
    v8 = 0;
  }
  assign(&pInetSecMgrSite._p, v8);
  if ( pInetSecMgrSite._p )
  {
    Instance = ((__int64 (__fastcall *)(IInternetSecurityManager *))pInetSecMgrGlobal._p->SetSecuritySite)(pInetSecMgrGlobal._p);
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
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180154ce4  mov     [rsp-18h+arg_0], rbx
0x180154ce9  mov     [rsp-18h+arg_8], rsi
0x180154cee  push    rbp
0x180154cef  push    rdi
0x180154cf0  push    r14
0x180154cf2  mov     rbp, rsp
0x180154cf5  sub     rsp, 50h
0x180154cf9  mov     rsi, ppISecMgr
0x180154cfc  mov     [rbp+pInetSecMgrGlobal._p], 0
0x180154d04  xor     edx, edx; pUnkOuter
0x180154d06  mov     [rbp+pInetSecMgrLocal._p], 0
0x180154d0e  mov     rdi, ppIHostSecMgr
0x180154d11  mov     [rbp+pServiceProvider._p], 0
0x180154d19  mov     r14, pSite
0x180154d1c  mov     [rbp+pInetSecMgrSite._p], 0
0x180154d24  lea     rax, [rbp+pInetSecMgrGlobal]
0x180154d28  lea     r8d, [ppISecMgr+1]; dwClsContext
0x180154d2c  mov     [rsp+50h+ppv], rax; ppv
0x180154d31  lea     r9, IID_IInternetSecurityManager; riid
0x180154d38  lea     pSite, CLSID_InternetSecurityManager; rclsid
0x180154d3f  call    cs:__imp_CoCreateInstance
0x180154d46  nop     dword ptr [rax+rax+00h]
0x180154d4b  mov     ebx, eax
0x180154d4d  test    eax, eax
0x180154d4f  js      loc_180154E00
0x180154d55  mov     pSite, [r14]
0x180154d58  lea     ppIHostSecMgr, [rbp+pServiceProvider]
0x180154d5c  lea     ppISecMgr, IID_IServiceProvider
0x180154d63  mov     rax, [pSite]
0x180154d66  mov     pSite, r14
0x180154d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154d6e  test    eax, eax
0x180154d70  js      $CleanUp_490
0x180154d76  mov     pSite, [rbp+pServiceProvider._p]
0x180154d7a  lea     r9, [rbp+pInetSecMgrLocal]
0x180154d7e  lea     ppIHostSecMgr, IID_IInternetSecurityManager
0x180154d85  lea     ppISecMgr, IID_IInternetSecurityManager
0x180154d8c  mov     rax, [pSite]
0x180154d8f  mov     rax, [rax+18h]
0x180154d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154d98  test    eax, eax
0x180154d9a  js      loc_180154E5E
0x180154da0  xor     edx, edx; dwFlags
0x180154da2  lea     ecx, [ppISecMgr+20h]; cb
0x180154da5  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x180154daa  mov     rbx, rax
0x180154dad  test    rax, rax
0x180154db0  jz      short loc_180154DE4
0x180154db2  mov     ppISecMgr, [rbp+pInetSecMgrLocal._p]; pref
0x180154db6  lea     rax, ??_7MsxmlInternetSecurityMgrSite@@6BIInternetSecurityMgrSite@@@; const MsxmlInternetSecurityMgrSite::`vftable'{for `IInternetSecurityMgrSite'}
0x180154dbd  mov     [rbx], rax
0x180154dc0  lea     pSite, [rbx+18h]; ppref
0x180154dc4  lea     rax, ??_7MsxmlInternetSecurityMgrSite@@6BIServiceProvider@@@; const MsxmlInternetSecurityMgrSite::`vftable'{for `IServiceProvider'}
0x180154dcb  mov     [rbx+8], rax
0x180154dcf  mov     qword ptr [pSite], 0
0x180154dd6  mov     dword ptr [rbx+10h], 0
0x180154ddd  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180154de2  jmp     short loc_180154DE6
0x180154de4  xor     ebx, ebx
0x180154de6  mov     ppISecMgr, rbx; pref
0x180154de9  lea     pSite, [rbp+pInetSecMgrSite]; ppref
0x180154ded  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x180154df2  mov     ppISecMgr, [rbp+pInetSecMgrSite._p]
0x180154df6  test    ppISecMgr, ppISecMgr
0x180154df9  jnz     short loc_180154E48
0x180154dfb  mov     ebx, 8007000Eh
0x180154e00  mov     qword ptr [rsi], 0
0x180154e07  mov     qword ptr [rdi], 0
0x180154e0e  lea     pSite, [rbp+pInetSecMgrSite]; ppref
0x180154e12  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180154e17  lea     pSite, [rbp+pServiceProvider]; ppref
0x180154e1b  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180154e20  lea     pSite, [rbp+pInetSecMgrLocal]; ppref
0x180154e24  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180154e29  lea     pSite, [rbp+pInetSecMgrGlobal]; ppref
0x180154e2d  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180154e32  mov     rsi, [rsp+50h+arg_8]
0x180154e37  mov     eax, ebx
0x180154e39  mov     rbx, [rsp+50h+arg_0]
0x180154e3e  add     rsp, 50h
0x180154e42  pop     r14
0x180154e44  pop     rdi
0x180154e45  pop     rbp
0x180154e46  retn
0x180154e48  mov     pSite, [rbp+pInetSecMgrGlobal._p]
0x180154e4c  mov     rax, [pSite]
0x180154e4f  mov     rax, [rax+18h]
0x180154e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154e58  mov     ebx, eax
0x180154e5a  test    eax, eax
0x180154e5c  js      short loc_180154E00
0x180154e5e  test    rdi, rdi
0x180154e61  jz      short $CleanUp_490
0x180154e63  mov     pSite, [rbp+pServiceProvider._p]
0x180154e67  lea     ppISecMgr, IID_IInternetHostSecurityManager
0x180154e6e  mov     r9, rdi
0x180154e71  mov     ppIHostSecMgr, ppISecMgr
0x180154e74  mov     rax, [pSite]
0x180154e77  mov     rax, [rax+18h]
0x180154e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154e80  mov     rax, [rbp+pInetSecMgrGlobal._p]
0x180154e84  mov     [rsi], rax
0x180154e87  mov     [rbp+pInetSecMgrGlobal._p], 0
0x180154e8f  jmp     loc_180154E0E
```
