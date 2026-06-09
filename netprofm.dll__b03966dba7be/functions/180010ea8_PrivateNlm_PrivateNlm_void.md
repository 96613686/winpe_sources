# PrivateNlm::PrivateNlm(void)

- ea: `0x180010ea8`
- end: `0x180010f5b`
- name: `??0PrivateNlm@@QEAA@XZ`
- size: `179`
- prototype: `LPVOID *__fastcall(LPVOID *ppv)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f888`
- `0x180034420`

## callees

- `0x180010ea8`
- `0x18002a928`
- `0x180037e38`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180010f2e`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180010f2e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010ed5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010ed5`

## string_xrefs

- `0x180010eef`: `onecore\net\netprofiles\service\src\netshnlmplugin\privatenetworklistmanager.cpp`
- `0x180010f49`: `onecore\net\netprofiles\service\src\netshnlmplugin\privatenetworklistmanager.cpp`
- `0x180010ee0`: `CoCreateInstance(INetworkListManagerPrivate)`

## pseudocode

```c
// Hidden C++ exception states: #wind=44
LPVOID *__fastcall PrivateNlm::PrivateNlm(LPVOID *ppv)
{
  unsigned int Instance; // eax
  HRESULT v3; // eax
  int ppva; // [rsp+20h] [rbp-28h]
  const char *dwImpLevel; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *ppv = 0;
  Instance = CoCreateInstance(&CLSID_CNetworkListManager, 0, 4u, &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b, ppv);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x3E9,
    (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\privatenetworklistmanager.cpp",
    (const char *)Instance,
    (int)"CoCreateInstance(INetworkListManagerPrivate)",
    dwImpLevel);
  v3 = CoSetProxyBlanket((IUnknown *)*ppv, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3F4,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\netshnlmplugin\\privatenetworklistmanager.cpp",
      (const char *)(unsigned int)v3,
      ppva);
  return ppv;
}

```

## disassembly

```asm
0x180010ea8  mov     [rsp+arg_0], rcx
0x180010ead  push    rbx
0x180010eae  sub     rsp, 40h
0x180010eb2  mov     rbx, rcx
0x180010eb5  mov     qword ptr [rcx], 0
0x180010ebc  mov     [rsp+48h+ppv], rcx; ppv
0x180010ec1  lea     r9, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b; riid
0x180010ec8  xor     edx, edx; pUnkOuter
0x180010eca  lea     r8d, [rdx+4]; dwClsContext
0x180010ece  lea     rcx, CLSID_CNetworkListManager; rclsid
0x180010ed5  call    cs:__imp_CoCreateInstance
0x180010edb  mov     rcx, [rsp+48h]; this
0x180010ee0  lea     rdx, aCocreateinstan_0; "CoCreateInstance(INetworkListManagerPri"...
0x180010ee7  mov     [rsp+48h+ppv], rdx; int
0x180010eec  mov     r9d, eax; char *
0x180010eef  lea     r8, aOnecoreNetNetp_3; "onecore\\net\\netprofiles\\service\\src"...
0x180010ef6  mov     edx, 3E9h; void *
0x180010efb  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180010f00  mov     [rsp+48h+dwCapabilities], 20h ; ' '; dwCapabilities
0x180010f08  mov     [rsp+48h+pAuthInfo], 0; pAuthInfo
0x180010f11  mov     dword ptr [rsp+48h+dwImpLevel], 3; dwImpLevel
0x180010f19  mov     dword ptr [rsp+48h+ppv], 0; int
0x180010f21  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180010f25  xor     r8d, r8d; dwAuthzSvc
0x180010f28  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180010f2b  mov     rcx, [rbx]; pProxy
0x180010f2e  call    cs:__imp_CoSetProxyBlanket
0x180010f34  mov     rcx, [rsp+48h]; this
0x180010f39  test    eax, eax
0x180010f3b  js      short loc_180010F46
0x180010f3d  mov     rax, rbx
0x180010f40  add     rsp, 40h
0x180010f44  pop     rbx
0x180010f45  retn
0x180010f46  mov     r9d, eax; char *
0x180010f49  lea     r8, aOnecoreNetNetp_3; "onecore\\net\\netprofiles\\service\\src"...
0x180010f50  mov     edx, 3F4h; void *
0x180010f55  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
