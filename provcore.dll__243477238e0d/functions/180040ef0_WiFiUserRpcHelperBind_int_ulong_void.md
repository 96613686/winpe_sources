# WiFiUserRpcHelperBind(int,ulong,void * *)

- ea: `0x180040ef0`
- end: `0x180040ff7`
- name: `?WiFiUserRpcHelperBind@@YAKHKPEAPEAX@Z`
- size: `263`
- prototype: `unsigned int __fastcall(int phBinding, unsigned int bAllowImpersonation, void **ulTimeoutMilliseconds)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180040dc8`

## callees

- `0x180002790`
- `0x180040ef0`
- `0x180041000`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x180040fa0`
- `RPCRT4!RpcBindingCreateW` at `0x180040fa0`
- `RPCRT4!RpcBindingBind` at `0x180040fb8`
- `RPCRT4!RpcBindingBind` at `0x180040fb8`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180040fce`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180040fce`

## pseudocode

```c
__int64 __fastcall WiFiUserRpcHelperBind(int phBinding, unsigned int bAllowImpersonation, void **ulTimeoutMilliseconds)
{
  unsigned int v4; // ebx
  _RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+20h] [rbp-49h] BYREF
  _RPC_SECURITY_QOS_V5_W SecurityQos; // [rsp+48h] [rbp-21h] BYREF
  _RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+80h] [rbp+17h] BYREF

  *(_QWORD *)&Template.ProtocolSequence = 3;
  memset(&SecurityQos.AdditionalSecurityInfoType, 0, 40);
  Security.ServerPrincName = 0;
  Security.AuthIdentity = 0;
  *(_QWORD *)&Template.Version = 1;
  SecurityQos.IdentityTracking = 1;
  *(_QWORD *)&Security.Version = 1;
  Security.SecurityQos = (_RPC_SECURITY_QOS *)&SecurityQos;
  memset(&Template.NetworkAddress, 0, 40);
  *(_QWORD *)&SecurityQos.Version = 5;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  SecurityQos.ImpersonationType = 4;
  v4 = RpcBindingCreateW(&Template, &Security, 0, ulTimeoutMilliseconds);
  if ( v4 || (v4 = RpcBindingBind(0, *ulTimeoutMilliseconds, &WiFiUser___RpcClientInterface)) != 0 )
    WiFiUserRpcHelperUnbind(ulTimeoutMilliseconds);
  FreeTransientObjectSecurityDescriptor(0);
  return v4;
}

```

## disassembly

```asm
0x180040ef0  mov     [rsp-8+arg_0], rbx
0x180040ef5  mov     [rsp-8+arg_8], rdi
0x180040efa  push    rbp
0x180040efb  lea     rbp, [rsp-57h]
0x180040f00  sub     rsp, 0C0h
0x180040f07  mov     rax, cs:__security_cookie
0x180040f0e  xor     rax, rsp
0x180040f11  mov     [rbp+57h+var_8], rax
0x180040f15  xor     eax, eax
0x180040f17  mov     qword ptr [rbp+57h+Template.ProtocolSequence], 3
0x180040f1f  mov     ecx, 1
0x180040f24  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data2], rax
0x180040f28  xorps   xmm0, xmm0
0x180040f2b  mov     dword ptr [rbp+57h+Template.ObjectUuid.Data4+4], eax
0x180040f2e  mov     qword ptr [rbp+57h+SecurityQos.AdditionalSecurityInfoType], rax
0x180040f32  lea     rdx, [rbp+57h+Security]; Security
0x180040f36  mov     qword ptr [rbp+57h+SecurityQos.EffectiveOnly], rax
0x180040f3a  mov     rdi, phBinding
0x180040f3d  mov     [rbp+57h+Security.ServerPrincName], rax
0x180040f41  mov     r9, phBinding; Binding
0x180040f44  mov     [rbp+57h+Security.AuthIdentity], rax
0x180040f48  xor     r8d, r8d; Options
0x180040f4b  lea     rax, [rbp+57h+SecurityQos]
0x180040f4f  mov     qword ptr [rbp+57h+Template.Version], rcx
0x180040f53  mov     [rbp+57h+SecurityQos.IdentityTracking], ecx
0x180040f56  mov     qword ptr [rbp+57h+Security.Version], rcx
0x180040f5a  lea     rcx, [rbp+57h+Template]; Template
0x180040f5e  mov     [rbp+57h+Security.SecurityQos], rax
0x180040f62  movdqu  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x180040f67  mov     qword ptr [rbp+57h+Template.u1], 0
0x180040f6f  mov     [rbp+57h+Template.ObjectUuid.Data1], 0
0x180040f76  mov     qword ptr [rbp+57h+SecurityQos.Version], 5
0x180040f7e  movdqu  xmmword ptr [rbp+57h+SecurityQos.u], xmm0
0x180040f83  mov     [rbp+57h+Security.AuthnLevel], 6
0x180040f8a  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x180040f91  mov     [rbp+57h+SecurityQos.ImpersonationType], 4
0x180040f98  mov     [rbp+57h+SecurityQos.ServerSecurityDescriptor], 0
0x180040fa0  call    cs:__imp_RpcBindingCreateW
0x180040fa6  mov     ebx, eax
0x180040fa8  test    eax, eax
0x180040faa  jnz     short loc_180040FC4
0x180040fac  mov     rdx, [rdi]; Binding
0x180040faf  lea     phBinding, WiFiUser___RpcClientInterface; IfSpec
0x180040fb6  xor     ecx, ecx; pAsync
0x180040fb8  call    cs:__imp_RpcBindingBind
0x180040fbe  mov     ebx, eax
0x180040fc0  test    eax, eax
0x180040fc2  jz      short loc_180040FCC
0x180040fc4  mov     rcx, rdi; phBinding
0x180040fc7  call    ?WiFiUserRpcHelperUnbind@@YAKPEAPEAX@Z; WiFiUserRpcHelperUnbind(void * *)
0x180040fcc  xor     ecx, ecx
0x180040fce  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180040fd4  mov     eax, ebx
0x180040fd6  mov     rcx, [rbp+57h+var_8]
0x180040fda  xor     rcx, rsp; StackCookie
0x180040fdd  call    __security_check_cookie
0x180040fe2  lea     r11, [rsp+0C0h+var_s0]
0x180040fea  mov     rbx, [r11+10h]
0x180040fee  mov     rdi, [r11+18h]
0x180040ff2  mov     rsp, r11
0x180040ff5  pop     rbp
0x180040ff6  retn
```
