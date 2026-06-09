# EfsRpcInit

- ea: `0x140057d14`
- end: `0x140057e48`
- name: `EfsRpcInit`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004da14`

## callees

- `0x14000c230`
- `0x140057d14`
- `0x14005ab08`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140057e0a`
- `ntoskrnl!KeInitializeEvent` at `0x140057e0a`
- `ntoskrnl!SeExports` at `0x140057d85`
- `msrpc!RpcBindingCreateW` at `0x140057de1`
- `msrpc!RpcBindingCreateW` at `0x140057de1`

## pseudocode

```c
__int64 EfsRpcInit()
{
  unsigned int v0; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-49h] BYREF
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+28h] [rbp-41h] BYREF
  _DWORD v4[4]; // [rsp+50h] [rbp-19h] BYREF
  __int128 v5; // [rsp+60h] [rbp-9h]
  PSID SeLocalSystemSid; // [rsp+70h] [rbp+7h]
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+78h] [rbp+Fh] BYREF

  SeLocalSystemSid = 0;
  LODWORD(Security.SecurityQos) = 0;
  g_RpcBindingHandle = 0;
  Binding = 0;
  memset(&Security, 0, 32);
  v4[1] = 1;
  v4[0] = 3;
  memset(&Template, 0, sizeof(Template));
  Template.ProtocolSequence = 3;
  v4[3] = 3;
  Template.Version = 1;
  v5 = 0;
  v4[2] = 1;
  SeLocalSystemSid = SeExports->SeLocalSystemSid;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v4;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  v0 = RpcBindingCreateW(&Template, &Security, 0, &Binding);
  if ( !v0 )
  {
    g_RpcBindingHandle = Binding;
    KeInitializeEvent(&g_RpcBindingEvent, SynchronizationEvent, 1u);
    TlgRegisterAggregateProviderEx(&dword_140017168);
  }
  return v0;
}

```

## disassembly

```asm
0x140057d14  mov     [rsp-8+arg_0], rbx
0x140057d19  mov     [rsp-8+arg_8], rdi
0x140057d1e  push    rbp
0x140057d1f  lea     rbp, [rsp-57h]
0x140057d24  sub     rsp, 0C0h
0x140057d2b  mov     rax, cs:__security_cookie
0x140057d32  xor     rax, rsp
0x140057d35  mov     [rbp+57h+var_10], rax
0x140057d39  xor     eax, eax
0x140057d3b  mov     [rbp+57h+var_50], 0
0x140057d43  xorps   xmm0, xmm0
0x140057d46  mov     dword ptr [rbp+57h+Security.SecurityQos], eax
0x140057d49  mov     cs:g_RpcBindingHandle, rax
0x140057d50  lea     r9, [rbp+57h+Binding]; Binding
0x140057d54  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data4], rax
0x140057d58  lea     rdx, [rbp+57h+Security]; Security
0x140057d5c  lea     edi, [rax+1]
0x140057d5f  mov     [rbp+57h+Binding], 0
0x140057d67  movups  xmmword ptr [rbp+57h+Security.Version], xmm0
0x140057d6b  lea     eax, [rdi+2]
0x140057d6e  mov     [rbp+57h+var_6C], edi
0x140057d71  movups  xmmword ptr [rbp+57h+Security.AuthnLevel], xmm0
0x140057d75  mov     [rbp+57h+var_70], eax
0x140057d78  xor     r8d, r8d; Options
0x140057d7b  movups  xmmword ptr [rbp+57h+Template.Version], xmm0
0x140057d7f  mov     [rbp+57h+Template.ProtocolSequence], eax
0x140057d82  mov     [rbp+57h+var_64], eax
0x140057d85  mov     rax, cs:__imp_SeExports
0x140057d8c  movups  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x140057d90  mov     [rbp+57h+Template.Version], edi
0x140057d93  movups  xmmword ptr [rbp+57h+Template.u1], xmm0
0x140057d97  mov     rcx, [rax]
0x140057d9a  movdqu  [rbp+57h+var_60], xmm0
0x140057d9f  mov     [rbp+57h+var_68], edi
0x140057da2  mov     rax, [rcx+108h]
0x140057da9  lea     rcx, [rbp+57h+Template]; Template
0x140057dad  mov     [rbp+57h+var_50], rax
0x140057db1  lea     rax, [rbp+57h+var_70]
0x140057db5  mov     [rbp+57h+Security.SecurityQos], rax
0x140057db9  mov     qword ptr [rbp+57h+Security+4], 0
0x140057dc1  mov     dword ptr [rbp+57h+Security.ServerPrincName+4], 0
0x140057dc8  mov     [rbp+57h+Security.AuthIdentity], 0
0x140057dd0  mov     [rbp+57h+Security.Version], edi
0x140057dd3  mov     [rbp+57h+Security.AuthnLevel], 6
0x140057dda  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x140057de1  call    cs:__imp_RpcBindingCreateW
0x140057de8  nop     dword ptr [rax+rax+00h]
0x140057ded  mov     ebx, eax
0x140057def  test    eax, eax
0x140057df1  jnz     short loc_140057E24
0x140057df3  mov     rax, [rbp+57h+Binding]
0x140057df7  lea     rcx, g_RpcBindingEvent; Event
0x140057dfe  mov     r8b, dil; State
0x140057e01  mov     cs:g_RpcBindingHandle, rax
0x140057e08  mov     edx, edi; Type
0x140057e0a  call    cs:__imp_KeInitializeEvent
0x140057e11  nop     dword ptr [rax+rax+00h]
0x140057e16  xor     edx, edx
0x140057e18  lea     rcx, dword_140017168; CallbackContext
0x140057e1f  call    TlgRegisterAggregateProviderEx
0x140057e24  mov     eax, ebx
0x140057e26  mov     rcx, [rbp+57h+var_10]
0x140057e2a  xor     rcx, rsp; StackCookie
0x140057e2d  call    __security_check_cookie
0x140057e32  lea     r11, [rsp+0C0h+var_s0]
0x140057e3a  mov     rbx, [r11+10h]
0x140057e3e  mov     rdi, [r11+18h]
0x140057e42  mov     rsp, r11
0x140057e45  pop     rbp
0x140057e46  retn
```
