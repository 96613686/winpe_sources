# DeliveryOptimizationUser::RequestCurrentUserToken(void)

- ea: `0x18000c4f0`
- end: `0x18000c684`
- name: `?RequestCurrentUserToken@DeliveryOptimizationUser@@UEAAJXZ`
- size: `404`
- prototype: `__int64 __fastcall(DeliveryOptimizationUser *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180005964`
- `0x18000c1cc`
- `0x18000c4f0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000c5bf`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000c5bf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c54c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c54c`

## pseudocode

```c
__int64 __fastcall DeliveryOptimizationUser::RequestCurrentUserToken(DeliveryOptimizationUser *this)
{
  int v1; // eax
  unsigned int v2; // ebx
  HRESULT Instance; // eax
  IUnknown *v5; // rcx
  HRESULT v6; // eax
  IUnknown *v7; // rcx
  int v8; // eax
  IUnknown *v9; // rcx
  IUnknown *v10; // rcx
  int ppv; // [rsp+20h] [rbp-20h]
  int ppva; // [rsp+20h] [rbp-20h]
  int ppvb; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  IUnknown *pProxy; // [rsp+58h] [rbp+18h] BYREF

  v1 = CheckCallerAccess();
  v2 = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecore\\enduser\\deliveryoptimization\\management\\user.cpp",
      (const char *)(unsigned int)v1,
      ppv);
    return v2;
  }
  pProxy = 0;
  Instance = CoCreateInstance(
               &GUID_5b99fa76_721c_423c_adac_56d03c8a8007,
               0,
               4u,
               &GUID_6692fd56_3b9b_433a_ac04_3ffb442556dd,
               (LPVOID *)&pProxy);
  v2 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\enduser\\deliveryoptimization\\management\\user.cpp",
      (const char *)(unsigned int)Instance,
      ppva);
    v5 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v5->lpVtbl->Release)(v5);
    }
    return v2;
  }
  v6 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x20u);
  v2 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecore\\enduser\\deliveryoptimization\\management\\user.cpp",
      (const char *)(unsigned int)v6,
      ppvb);
    v7 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v7->lpVtbl->Release)(v7);
    }
    return v2;
  }
  v8 = ((__int64 (__fastcall *)(IUnknown *))pProxy->lpVtbl[1].QueryInterface)(pProxy);
  v2 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecore\\enduser\\deliveryoptimization\\management\\user.cpp",
      (const char *)(unsigned int)v8,
      ppvb);
    v9 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v9->lpVtbl->Release)(v9);
    }
    return v2;
  }
  v10 = pProxy;
  if ( pProxy )
  {
    pProxy = 0;
    ((void (__fastcall *)(IUnknown *))v10->lpVtbl->Release)(v10);
  }
  return 0;
}

```

## disassembly

```asm
0x18000c4f0  mov     [rsp-8+arg_0], rbx
0x18000c4f5  push    rbp
0x18000c4f6  mov     rbp, rsp
0x18000c4f9  sub     rsp, 40h
0x18000c4fd  call    ?CheckCallerAccess@@YAJXZ; CheckCallerAccess(void)
0x18000c502  mov     ebx, eax
0x18000c504  test    eax, eax
0x18000c506  jns     short loc_18000C527
0x18000c508  mov     rcx, [rbp+8]; this
0x18000c50c  mov     r9d, eax; char *
0x18000c50f  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\deliveryoptimization"...
0x18000c516  mov     edx, 34h ; '4'; void *
0x18000c51b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c520  mov     eax, ebx
0x18000c522  jmp     loc_18000C679
0x18000c527  mov     [rbp+pProxy], 0
0x18000c52f  lea     rax, [rbp+pProxy]
0x18000c533  mov     [rsp+40h+ppv], rax; int
0x18000c538  lea     r9, _GUID_6692fd56_3b9b_433a_ac04_3ffb442556dd; riid
0x18000c53f  xor     edx, edx; pUnkOuter
0x18000c541  lea     r8d, [rdx+4]; dwClsContext
0x18000c545  lea     rcx, _GUID_5b99fa76_721c_423c_adac_56d03c8a8007; rclsid
0x18000c54c  call    cs:__imp_CoCreateInstance
0x18000c552  mov     ebx, eax
0x18000c554  test    eax, eax
0x18000c556  jns     short loc_18000C591
0x18000c558  mov     rcx, [rbp+8]; this
0x18000c55c  mov     r9d, eax; char *
0x18000c55f  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\deliveryoptimization"...
0x18000c566  mov     edx, 37h ; '7'; void *
0x18000c56b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c570  nop
0x18000c571  mov     rcx, [rbp+pProxy]
0x18000c575  test    rcx, rcx
0x18000c578  jz      short loc_18000C58F
0x18000c57a  mov     [rbp+pProxy], 0
0x18000c582  mov     rax, [rcx]
0x18000c585  mov     rax, [rax+10h]
0x18000c589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c58e  nop
0x18000c58f  jmp     short loc_18000C520
0x18000c591  mov     [rsp+40h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18000c599  mov     [rsp+40h+pAuthInfo], 0; pAuthInfo
0x18000c5a2  mov     [rsp+40h+dwImpLevel], 3; dwImpLevel
0x18000c5aa  mov     dword ptr [rsp+40h+ppv], 0; int
0x18000c5b2  xor     r9d, r9d; pServerPrincName
0x18000c5b5  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18000c5b8  mov     r8d, edx; dwAuthzSvc
0x18000c5bb  mov     rcx, [rbp+pProxy]; pProxy
0x18000c5bf  call    cs:__imp_CoSetProxyBlanket
0x18000c5c5  mov     ebx, eax
0x18000c5c7  test    eax, eax
0x18000c5c9  jns     short loc_18000C607
0x18000c5cb  mov     rcx, [rbp+8]; this
0x18000c5cf  mov     r9d, eax; char *
0x18000c5d2  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\deliveryoptimization"...
0x18000c5d9  mov     edx, 3Bh ; ';'; void *
0x18000c5de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c5e3  nop
0x18000c5e4  mov     rcx, [rbp+pProxy]
0x18000c5e8  test    rcx, rcx
0x18000c5eb  jz      short loc_18000C602
0x18000c5ed  mov     [rbp+pProxy], 0
0x18000c5f5  mov     rax, [rcx]
0x18000c5f8  mov     rax, [rax+10h]
0x18000c5fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c601  nop
0x18000c602  jmp     loc_18000C520
0x18000c607  mov     rcx, [rbp+pProxy]
0x18000c60b  mov     rax, [rcx]
0x18000c60e  mov     rax, [rax+18h]
0x18000c612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c617  mov     ebx, eax
0x18000c619  test    eax, eax
0x18000c61b  jns     short loc_18000C659
0x18000c61d  mov     rcx, [rbp+8]; this
0x18000c621  mov     r9d, eax; char *
0x18000c624  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\deliveryoptimization"...
0x18000c62b  mov     edx, 3Dh ; '='; void *
0x18000c630  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c635  nop
0x18000c636  mov     rcx, [rbp+pProxy]
0x18000c63a  test    rcx, rcx
0x18000c63d  jz      short loc_18000C654
0x18000c63f  mov     [rbp+pProxy], 0
0x18000c647  mov     rax, [rcx]
0x18000c64a  mov     rax, [rax+10h]
0x18000c64e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c653  nop
0x18000c654  jmp     loc_18000C520
0x18000c659  mov     rcx, [rbp+pProxy]
0x18000c65d  test    rcx, rcx
0x18000c660  jz      short loc_18000C677
0x18000c662  mov     [rbp+pProxy], 0
0x18000c66a  mov     rax, [rcx]
0x18000c66d  mov     rax, [rax+10h]
0x18000c671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c676  nop
0x18000c677  xor     eax, eax
0x18000c679  mov     rbx, [rsp+40h+arg_0]
0x18000c67e  add     rsp, 40h
0x18000c682  pop     rbp
0x18000c683  retn
```
