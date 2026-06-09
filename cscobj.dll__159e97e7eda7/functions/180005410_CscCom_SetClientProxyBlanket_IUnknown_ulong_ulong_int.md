# CscCom_SetClientProxyBlanket(IUnknown *,ulong,ulong,int)

- ea: `0x180005410`
- end: `0x180005604`
- name: `?CscCom_SetClientProxyBlanket@@YAJPEAUIUnknown@@KKH@Z`
- size: `500`
- prototype: `__int64 __fastcall(IUnknown *pProxy, unsigned int, unsigned int, int)`
- caller_count: `8`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003950`
- `0x180004770`
- `0x180004a20`
- `0x180004cf0`
- `0x1800052c0`
- `0x180008f28`
- `0x18000e710`
- `0x18000eb90`

## callees

- `0x180005410`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x180005467`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x180005524`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x180005467`
- `api-ms-win-core-com-l1-1-0!CoQueryProxyBlanket` at `0x180005524`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800054ab`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000556a`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800055b6`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800055f7`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800054ab`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000556a`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800055b6`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800055f7`

## pseudocode

```c
HRESULT __fastcall CscCom_SetClientProxyBlanket(IUnknown *pProxy)
{
  HRESULT result; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  IUnknown *v4; // rdi
  HRESULT v5; // eax
  HRESULT v6; // ebx
  DWORD dwImpLevel; // [rsp+40h] [rbp-10h] BYREF
  DWORD dwAuthnLevel; // [rsp+44h] [rbp-Ch] BYREF
  IUnknown *pProxya; // [rsp+48h] [rbp-8h] BYREF
  DWORD pwAuthnSvc; // [rsp+78h] [rbp+28h] BYREF
  DWORD pAuthzSvc; // [rsp+80h] [rbp+30h] BYREF
  DWORD dwCapabilities; // [rsp+88h] [rbp+38h] BYREF

  pwAuthnSvc = 0;
  pAuthzSvc = 0;
  dwAuthnLevel = 0;
  dwImpLevel = 0;
  dwCapabilities = 0;
  result = CoQueryProxyBlanket(pProxy, &pwAuthnSvc, &pAuthzSvc, 0, &dwAuthnLevel, &dwImpLevel, 0, &dwCapabilities);
  if ( result == -2147467262
    || result >= 0
    && (CoSetProxyBlanket(pProxy, pwAuthnSvc, pAuthzSvc, 0, 6u, 3u, 0, dwCapabilities & 0xFFFFFF9F | 0x40) >= 0
     || (result = CoSetProxyBlanket(pProxy, pwAuthnSvc, pAuthzSvc, 0, dwAuthnLevel, dwImpLevel, 0, dwCapabilities),
         result >= 0)) )
  {
    lpVtbl = pProxy->lpVtbl;
    pProxya = 0;
    result = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))lpVtbl->QueryInterface)(
               pProxy,
               &IID_IUnknown,
               &pProxya);
    if ( result >= 0 )
    {
      v4 = pProxya;
      pwAuthnSvc = 0;
      pAuthzSvc = 0;
      dwImpLevel = 0;
      dwAuthnLevel = 0;
      dwCapabilities = 0;
      v5 = CoQueryProxyBlanket(pProxya, &pwAuthnSvc, &pAuthzSvc, 0, &dwImpLevel, &dwAuthnLevel, 0, &dwCapabilities);
      v6 = v5;
      if ( v5 == -2147467262 )
      {
        v6 = 0;
      }
      else if ( v5 >= 0 )
      {
        v6 = CoSetProxyBlanket(v4, pwAuthnSvc, pAuthzSvc, 0, 6u, 3u, 0, dwCapabilities & 0xFFFFFF9F | 0x40);
        if ( v6 < 0 )
          v6 = CoSetProxyBlanket(v4, pwAuthnSvc, pAuthzSvc, 0, dwImpLevel, dwAuthnLevel, 0, dwCapabilities);
      }
      ((void (__fastcall *)(IUnknown *))pProxya->lpVtbl->Release)(pProxya);
      return v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005410  mov     [rsp-18h+dwCapabilities], r9d
0x180005415  mov     [rsp-18h+pAuthzSvc], r8d
0x18000541a  mov     [rsp-18h+pwAuthnSvc], edx
0x18000541e  push    rbp
0x18000541f  push    rbx
0x180005420  push    rsi
0x180005421  mov     rbp, rsp
0x180005424  sub     rsp, 50h
0x180005428  xor     esi, esi
0x18000542a  lea     rax, [rbp+dwCapabilities]
0x18000542e  mov     [rsp+50h+pCapabilites], rax; pCapabilites
0x180005433  lea     r8, [rbp+pAuthzSvc]; pAuthzSvc
0x180005437  lea     rax, [rbp+dwImpLevel]
0x18000543b  mov     [rsp+50h+pAuthInfo], rsi; pAuthInfo
0x180005440  mov     [rsp+50h+pImpLevel], rax; pImpLevel
0x180005445  lea     rdx, [rbp+pwAuthnSvc]; pwAuthnSvc
0x180005449  lea     rax, [rbp+dwAuthnLevel]
0x18000544d  mov     [rbp+pwAuthnSvc], esi
0x180005450  xor     r9d, r9d; pServerPrincName
0x180005453  mov     [rsp+50h+pAuthnLevel], rax; pAuthnLevel
0x180005458  mov     rbx, rcx
0x18000545b  mov     [rbp+pAuthzSvc], esi
0x18000545e  mov     [rbp+dwAuthnLevel], esi
0x180005461  mov     [rbp+dwImpLevel], esi
0x180005464  mov     [rbp+dwCapabilities], esi
0x180005467  call    cs:__imp_CoQueryProxyBlanket
0x18000546d  cmp     eax, 80004002h
0x180005472  jz      short loc_1800054B9
0x180005474  test    eax, eax
0x180005476  js      loc_1800055C4
0x18000547c  mov     eax, [rbp+dwCapabilities]
0x18000547f  xor     r9d, r9d; pServerPrincName
0x180005482  mov     r8d, [rbp+pAuthzSvc]; dwAuthzSvc
0x180005486  and     eax, 0FFFFFFDFh
0x180005489  mov     edx, [rbp+pwAuthnSvc]; dwAuthnSvc
0x18000548c  or      eax, 40h
0x18000548f  mov     dword ptr [rsp+50h+pCapabilites], eax; dwCapabilities
0x180005493  mov     rcx, rbx; pProxy
0x180005496  mov     [rsp+50h+pAuthInfo], rsi; pAuthInfo
0x18000549b  mov     dword ptr [rsp+50h+pImpLevel], 3; dwImpLevel
0x1800054a3  mov     dword ptr [rsp+50h+pAuthnLevel], 6; dwAuthnLevel
0x1800054ab  call    cs:__imp_CoSetProxyBlanket
0x1800054b1  test    eax, eax
0x1800054b3  js      loc_18000558F
0x1800054b9  mov     rax, [rbx]
0x1800054bc  lea     r8, [rbp+pProxy]
0x1800054c0  lea     rdx, IID_IUnknown
0x1800054c7  mov     [rbp+pProxy], rsi
0x1800054cb  mov     rcx, rbx
0x1800054ce  mov     rax, [rax]
0x1800054d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054d6  test    eax, eax
0x1800054d8  js      loc_1800055C4
0x1800054de  lea     rax, [rbp+dwCapabilities]
0x1800054e2  mov     [rsp+50h+arg_0], rdi
0x1800054e7  mov     rdi, [rbp+pProxy]
0x1800054eb  lea     r8, [rbp+pAuthzSvc]; pAuthzSvc
0x1800054ef  mov     [rsp+50h+pCapabilites], rax; pCapabilites
0x1800054f4  lea     rdx, [rbp+pwAuthnSvc]; pwAuthnSvc
0x1800054f8  lea     rax, [rbp+dwAuthnLevel]
0x1800054fc  mov     [rsp+50h+pAuthInfo], rsi; pAuthInfo
0x180005501  mov     [rsp+50h+pImpLevel], rax; pImpLevel
0x180005506  xor     r9d, r9d; pServerPrincName
0x180005509  lea     rax, [rbp+dwImpLevel]
0x18000550d  mov     [rbp+pwAuthnSvc], esi
0x180005510  mov     rcx, rdi; pProxy
0x180005513  mov     [rsp+50h+pAuthnLevel], rax; pAuthnLevel
0x180005518  mov     [rbp+pAuthzSvc], esi
0x18000551b  mov     [rbp+dwImpLevel], esi
0x18000551e  mov     [rbp+dwAuthnLevel], esi
0x180005521  mov     [rbp+dwCapabilities], esi
0x180005524  call    cs:__imp_CoQueryProxyBlanket
0x18000552a  mov     ebx, eax
0x18000552c  cmp     eax, 80004002h
0x180005531  jz      loc_1800055CC
0x180005537  test    eax, eax
0x180005539  js      short loc_180005576
0x18000553b  mov     eax, [rbp+dwCapabilities]
0x18000553e  xor     r9d, r9d; pServerPrincName
0x180005541  mov     r8d, [rbp+pAuthzSvc]; dwAuthzSvc
0x180005545  and     eax, 0FFFFFFDFh
0x180005548  mov     edx, [rbp+pwAuthnSvc]; dwAuthnSvc
0x18000554b  or      eax, 40h
0x18000554e  mov     dword ptr [rsp+50h+pCapabilites], eax; dwCapabilities
0x180005552  mov     rcx, rdi; pProxy
0x180005555  mov     [rsp+50h+pAuthInfo], rsi; pAuthInfo
0x18000555a  mov     dword ptr [rsp+50h+pImpLevel], 3; dwImpLevel
0x180005562  mov     dword ptr [rsp+50h+pAuthnLevel], 6; dwAuthnLevel
0x18000556a  call    cs:__imp_CoSetProxyBlanket
0x180005570  mov     ebx, eax
0x180005572  test    eax, eax
0x180005574  js      short loc_1800055D0
0x180005576  mov     rcx, [rbp+pProxy]
0x18000557a  mov     rdx, [rcx]
0x18000557d  mov     rax, [rdx+10h]
0x180005581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005586  mov     rdi, [rsp+50h+arg_0]
0x18000558b  mov     eax, ebx
0x18000558d  jmp     short loc_1800055C4
0x18000558f  mov     eax, [rbp+dwCapabilities]
0x180005592  xor     r9d, r9d; pServerPrincName
0x180005595  mov     r8d, [rbp+pAuthzSvc]; dwAuthzSvc
0x180005599  mov     rcx, rbx; pProxy
0x18000559c  mov     edx, [rbp+pwAuthnSvc]; dwAuthnSvc
0x18000559f  mov     dword ptr [rsp+50h+pCapabilites], eax; dwCapabilities
0x1800055a3  mov     eax, [rbp+dwImpLevel]
0x1800055a6  mov     [rsp+50h+pAuthInfo], rsi; pAuthInfo
0x1800055ab  mov     dword ptr [rsp+50h+pImpLevel], eax; dwImpLevel
0x1800055af  mov     eax, [rbp+dwAuthnLevel]
0x1800055b2  mov     dword ptr [rsp+50h+pAuthnLevel], eax; dwAuthnLevel
0x1800055b6  call    cs:__imp_CoSetProxyBlanket
0x1800055bc  test    eax, eax
0x1800055be  jns     loc_1800054B9
0x1800055c4  add     rsp, 50h
0x1800055c8  pop     rsi
0x1800055c9  pop     rbx
0x1800055ca  pop     rbp
0x1800055cb  retn
0x1800055cc  mov     ebx, esi
0x1800055ce  jmp     short loc_180005576
0x1800055d0  mov     eax, [rbp+dwCapabilities]
0x1800055d3  xor     r9d, r9d; pServerPrincName
0x1800055d6  mov     r8d, [rbp+pAuthzSvc]; dwAuthzSvc
0x1800055da  mov     rcx, rdi; pProxy
0x1800055dd  mov     edx, [rbp+pwAuthnSvc]; dwAuthnSvc
0x1800055e0  mov     dword ptr [rsp+50h+pCapabilites], eax; dwCapabilities
0x1800055e4  mov     eax, [rbp+dwAuthnLevel]
0x1800055e7  mov     [rsp+50h+pAuthInfo], rsi; pAuthInfo
0x1800055ec  mov     dword ptr [rsp+50h+pImpLevel], eax; dwImpLevel
0x1800055f0  mov     eax, [rbp+dwImpLevel]
0x1800055f3  mov     dword ptr [rsp+50h+pAuthnLevel], eax; dwAuthnLevel
0x1800055f7  call    cs:__imp_CoSetProxyBlanket
0x1800055fd  mov     ebx, eax
0x1800055ff  jmp     loc_180005576
```
