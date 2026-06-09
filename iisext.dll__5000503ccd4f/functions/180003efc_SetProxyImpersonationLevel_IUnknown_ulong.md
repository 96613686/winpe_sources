# SetProxyImpersonationLevel(IUnknown *,ulong)

- ea: `0x180003efc`
- end: `0x180003fd3`
- name: `?SetProxyImpersonationLevel@@YAJPEAUIUnknown@@K@Z`
- size: `215`
- prototype: `__int64 __fastcall(IUnknown *pProxy)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation, service_task`

## callers

- `0x180003ab8`
- `0x180005e50`
- `0x1800076d0`
- `0x180007e60`
- `0x180008c40`
- `0x1800094c0`

## callees

- `0x180003efc`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180003fc3`
- `ole32!CoTaskMemFree` at `0x180003fc3`
- `ole32!CoSetProxyBlanket` at `0x180003fb2`
- `ole32!CoSetProxyBlanket` at `0x180003fb2`
- `ole32!CoQueryProxyBlanket` at `0x180003f6f`
- `ole32!CoQueryProxyBlanket` at `0x180003f6f`

## pseudocode

```c
__int64 __fastcall SetProxyImpersonationLevel(IUnknown *pProxy)
{
  HRESULT v2; // ebx
  DWORD dwCapabilities; // eax
  DWORD pwAuthnSvc; // [rsp+40h] [rbp-20h] BYREF
  DWORD v6; // [rsp+44h] [rbp-1Ch] BYREF
  LPOLESTR pServerPrincName; // [rsp+48h] [rbp-18h] BYREF
  RPC_AUTH_IDENTITY_HANDLE pAuthInfo; // [rsp+50h] [rbp-10h] BYREF
  DWORD v9; // [rsp+88h] [rbp+28h] BYREF
  DWORD dwAuthnLevel; // [rsp+90h] [rbp+30h] BYREF
  DWORD pAuthzSvc; // [rsp+98h] [rbp+38h] BYREF

  pwAuthnSvc = 0;
  pAuthzSvc = 0;
  dwAuthnLevel = 0;
  v6 = 0;
  v9 = 0;
  pServerPrincName = 0;
  pAuthInfo = 0;
  v2 = CoQueryProxyBlanket(pProxy, &pwAuthnSvc, &pAuthzSvc, &pServerPrincName, &dwAuthnLevel, &v6, &pAuthInfo, &v9);
  if ( v2 >= 0 )
  {
    dwCapabilities = v9;
    if ( (v9 & 0x20) == 0 )
    {
      dwCapabilities = v9 | 0x40;
      v9 |= 0x40u;
    }
    v2 = CoSetProxyBlanket(pProxy, pwAuthnSvc, pAuthzSvc, pServerPrincName, dwAuthnLevel, 3u, pAuthInfo, dwCapabilities);
  }
  if ( pServerPrincName )
    CoTaskMemFree(pServerPrincName);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180003efc  mov     [rsp-18h+arg_8], edx
0x180003f00  mov     r11, rsp
0x180003f03  push    rbp
0x180003f04  push    rbx
0x180003f05  push    rdi
0x180003f06  mov     rbp, rsp
0x180003f09  sub     rsp, 60h
0x180003f0d  lea     rax, [rbp+arg_8]
0x180003f11  mov     [rbp+pwAuthnSvc], 0
0x180003f18  mov     [r11-40h], rax
0x180003f1c  lea     r9, [rbp+pServerPrincName]; pServerPrincName
0x180003f20  lea     rax, [rbp+var_10]
0x180003f24  mov     [rbp+pAuthzSvc], 0
0x180003f2b  mov     [r11-48h], rax
0x180003f2f  lea     r8, [rbp+pAuthzSvc]; pAuthzSvc
0x180003f33  lea     rax, [rbp+var_1C]
0x180003f37  mov     [rbp+arg_10], 0
0x180003f3e  mov     [r11-50h], rax
0x180003f42  lea     rdx, [rbp+pwAuthnSvc]; pwAuthnSvc
0x180003f46  lea     rax, [rbp+arg_10]
0x180003f4a  mov     [rbp+var_1C], 0
0x180003f51  mov     [r11-58h], rax
0x180003f55  mov     rdi, rcx
0x180003f58  mov     [rbp+arg_8], 0
0x180003f5f  mov     [rbp+pServerPrincName], 0
0x180003f67  mov     [rbp+var_10], 0
0x180003f6f  call    cs:__imp_CoQueryProxyBlanket
0x180003f75  mov     ebx, eax
0x180003f77  test    eax, eax
0x180003f79  js      short loc_180003FBA
0x180003f7b  mov     eax, [rbp+arg_8]
0x180003f7e  test    al, 20h
0x180003f80  jnz     short loc_180003F88
0x180003f82  or      eax, 40h
0x180003f85  mov     [rbp+arg_8], eax
0x180003f88  mov     r9, [rbp+pServerPrincName]; pServerPrincName
0x180003f8c  mov     rcx, rdi; pProxy
0x180003f8f  mov     r8d, [rbp+pAuthzSvc]; dwAuthzSvc
0x180003f93  mov     edx, [rbp+pwAuthnSvc]; dwAuthnSvc
0x180003f96  mov     [rsp+60h+dwCapabilities], eax; dwCapabilities
0x180003f9a  mov     rax, [rbp+var_10]
0x180003f9e  mov     [rsp+60h+pAuthInfo], rax; pAuthInfo
0x180003fa3  mov     eax, [rbp+arg_10]
0x180003fa6  mov     [rsp+60h+dwImpLevel], 3; dwImpLevel
0x180003fae  mov     [rsp+60h+dwAuthnLevel], eax; dwAuthnLevel
0x180003fb2  call    cs:__imp_CoSetProxyBlanket
0x180003fb8  mov     ebx, eax
0x180003fba  mov     rcx, [rbp+pServerPrincName]; pv
0x180003fbe  test    rcx, rcx
0x180003fc1  jz      short loc_180003FC9
0x180003fc3  call    cs:__imp_CoTaskMemFree
0x180003fc9  mov     eax, ebx
0x180003fcb  add     rsp, 60h
0x180003fcf  pop     rdi
0x180003fd0  pop     rbx
0x180003fd1  pop     rbp
0x180003fd2  retn
```
