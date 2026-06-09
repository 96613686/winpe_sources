# COMSafeControlRoot::getSecurityManagerFromSite(IUnknown *,IInternetSecurityManager * *,IInternetHostSecurityManager * *)

- ea: `0x1801518e0`
- end: `0x180151a89`
- name: `?getSecurityManagerFromSite@COMSafeControlRoot@@SAJPEAUIUnknown@@PEAPEAUIInternetSecurityManager@@PEAPEAUIInternetHostSecurityManager@@@Z`
- size: `425`
- prototype: `HRESULT __fastcall(IUnknown *pSite, IInternetSecurityManager **ppISecMgr, IInternetHostSecurityManager **ppIHostSecMgr)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801501a0`
- `0x180151b8c`

## callees

- `0x180009490`
- `0x18000d7d0`
- `0x18003617c`
- `0x1801518e0`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18015193b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18015193b`

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
0x1801518e0  mov     [rsp-18h+arg_0], rbx
0x1801518e5  mov     [rsp-18h+arg_8], rsi
0x1801518ea  push    rbp
0x1801518eb  push    rdi
0x1801518ec  push    r14
0x1801518ee  mov     rbp, rsp
0x1801518f1  sub     rsp, 50h
0x1801518f5  mov     rsi, ppISecMgr
0x1801518f8  mov     [rbp+pInetSecMgrGlobal._p], 0
0x180151900  xor     edx, edx; pUnkOuter
0x180151902  mov     [rbp+pInetSecMgrLocal._p], 0
0x18015190a  mov     rdi, ppIHostSecMgr
0x18015190d  mov     [rbp+pServiceProvider._p], 0
0x180151915  mov     r14, pSite
0x180151918  mov     [rbp+pInetSecMgrSite._p], 0
0x180151920  lea     rax, [rbp+pInetSecMgrGlobal]
0x180151924  lea     r8d, [ppISecMgr+1]; dwClsContext
0x180151928  mov     [rsp+50h+ppv], rax; ppv
0x18015192d  lea     r9, IID_IInternetSecurityManager; riid
0x180151934  lea     pSite, CLSID_InternetSecurityManager; rclsid
0x18015193b  call    cs:__imp_CoCreateInstance
0x180151941  mov     ebx, eax
0x180151943  test    eax, eax
0x180151945  js      loc_1801519F6
0x18015194b  mov     pSite, [r14]
0x18015194e  lea     ppIHostSecMgr, [rbp+pServiceProvider]
0x180151952  lea     ppISecMgr, IID_IServiceProvider
0x180151959  mov     rax, [pSite]
0x18015195c  mov     pSite, r14
0x18015195f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151964  test    eax, eax
0x180151966  js      $CleanUp_490
0x18015196c  mov     pSite, [rbp+pServiceProvider._p]
0x180151970  lea     r9, [rbp+pInetSecMgrLocal]
0x180151974  lea     ppIHostSecMgr, IID_IInternetSecurityManager
0x18015197b  lea     ppISecMgr, IID_IInternetSecurityManager
0x180151982  mov     rax, [pSite]
0x180151985  mov     rax, [rax+18h]
0x180151989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015198e  test    eax, eax
0x180151990  js      loc_180151A53
0x180151996  xor     edx, edx; dwFlags
0x180151998  lea     ecx, [ppISecMgr+20h]; cb
0x18015199b  call    ?_MemAlloc@@YAPEAX_KK@Z; _MemAlloc(unsigned __int64,ulong)
0x1801519a0  mov     rbx, rax
0x1801519a3  test    rax, rax
0x1801519a6  jz      short loc_1801519DA
0x1801519a8  mov     ppISecMgr, [rbp+pInetSecMgrLocal._p]; pref
0x1801519ac  lea     rax, ??_7MsxmlInternetSecurityMgrSite@@6BIInternetSecurityMgrSite@@@; const MsxmlInternetSecurityMgrSite::`vftable'{for `IInternetSecurityMgrSite'}
0x1801519b3  mov     [rbx], rax
0x1801519b6  lea     pSite, [rbx+18h]; ppref
0x1801519ba  lea     rax, ??_7MsxmlInternetSecurityMgrSite@@6BIServiceProvider@@@; const MsxmlInternetSecurityMgrSite::`vftable'{for `IServiceProvider'}
0x1801519c1  mov     [rbx+8], rax
0x1801519c5  mov     qword ptr [pSite], 0
0x1801519cc  mov     dword ptr [rbx+10h], 0
0x1801519d3  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801519d8  jmp     short loc_1801519DC
0x1801519da  xor     ebx, ebx
0x1801519dc  mov     ppISecMgr, rbx; pref
0x1801519df  lea     pSite, [rbp+pInetSecMgrSite]; ppref
0x1801519e3  call    ?assign@@YAXPEAPEAUIUnknown@@PEAX@Z; assign(IUnknown * *,void *)
0x1801519e8  mov     ppISecMgr, [rbp+pInetSecMgrSite._p]
0x1801519ec  test    ppISecMgr, ppISecMgr
0x1801519ef  jnz     short loc_180151A3D
0x1801519f1  mov     ebx, 8007000Eh
0x1801519f6  mov     qword ptr [rsi], 0
0x1801519fd  mov     qword ptr [rdi], 0
0x180151a04  lea     pSite, [rbp+pInetSecMgrSite]; ppref
0x180151a08  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180151a0d  lea     pSite, [rbp+pServiceProvider]; ppref
0x180151a11  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180151a16  lea     pSite, [rbp+pInetSecMgrLocal]; ppref
0x180151a1a  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180151a1f  lea     pSite, [rbp+pInetSecMgrGlobal]; ppref
0x180151a23  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x180151a28  mov     rsi, [rsp+50h+arg_8]
0x180151a2d  mov     eax, ebx
0x180151a2f  mov     rbx, [rsp+50h+arg_0]
0x180151a34  add     rsp, 50h
0x180151a38  pop     r14
0x180151a3a  pop     rdi
0x180151a3b  pop     rbp
0x180151a3c  retn
0x180151a3d  mov     pSite, [rbp+pInetSecMgrGlobal._p]
0x180151a41  mov     rax, [pSite]
0x180151a44  mov     rax, [rax+18h]
0x180151a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151a4d  mov     ebx, eax
0x180151a4f  test    eax, eax
0x180151a51  js      short loc_1801519F6
0x180151a53  test    rdi, rdi
0x180151a56  jz      short $CleanUp_490
0x180151a58  mov     pSite, [rbp+pServiceProvider._p]
0x180151a5c  lea     ppISecMgr, IID_IInternetHostSecurityManager
0x180151a63  mov     r9, rdi
0x180151a66  mov     ppIHostSecMgr, ppISecMgr
0x180151a69  mov     rax, [pSite]
0x180151a6c  mov     rax, [rax+18h]
0x180151a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180151a75  mov     rax, [rbp+pInetSecMgrGlobal._p]
0x180151a79  mov     [rsi], rax
0x180151a7c  mov     [rbp+pInetSecMgrGlobal._p], 0
0x180151a84  jmp     loc_180151A04
```
