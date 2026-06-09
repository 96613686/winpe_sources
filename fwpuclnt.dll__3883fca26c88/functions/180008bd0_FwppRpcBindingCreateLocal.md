# FwppRpcBindingCreateLocal

- ea: `0x180008bd0`
- end: `0x180008d17`
- name: `FwppRpcBindingCreateLocal`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007550`

## callees

- `0x180007e38`
- `0x180008bd0`
- `0x18000bd54`
- `0x180012bd0`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x180008c7b`
- `RPCRT4!RpcBindingCreateW` at `0x180008c7b`
- `RPCRT4!RpcBindingSetOption` at `0x180008c9a`
- `RPCRT4!RpcBindingSetOption` at `0x180008c9a`
- `RPCRT4!RpcBindingFree` at `0x180008cd5`
- `RPCRT4!RpcBindingFree` at `0x180008cd5`

## string_xrefs

- `0x180008ce1`: `FwppRpcBindingCreateLocal`
- `0x180008cf5`: `RpcBindingCreateW`

## pseudocode

```c
__int64 __fastcall FwppRpcBindingCreateLocal(__int64 a1, SEC_WINNT_AUTH_IDENTITY_W *a2, RPC_BINDING_HANDLE *a3)
{
  unsigned int v4; // eax
  __int64 v5; // rcx
  __int64 result; // rax
  const char *v7; // rdx
  __int64 v8; // rbx
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-59h] BYREF
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+28h] [rbp-51h] BYREF
  int v11; // [rsp+50h] [rbp-29h] BYREF
  __int64 v12; // [rsp+54h] [rbp-25h]
  int v13; // [rsp+5Ch] [rbp-1Dh]
  __int128 v14; // [rsp+60h] [rbp-19h]
  __int64 v15; // [rsp+70h] [rbp-9h]
  __int64 v16; // [rsp+78h] [rbp-1h]
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+80h] [rbp+7h] BYREF

  v15 = a1;
  Security.AuthIdentity = a2;
  *a3 = 0;
  memset(&Template, 0, sizeof(Template));
  Binding = 0;
  Security.SecurityQos = (RPC_SECURITY_QOS *)&v11;
  Template.Version = 1;
  Template.ProtocolSequence = 3;
  v16 = 1;
  v11 = 4;
  v12 = 1;
  v14 = 0;
  v13 = 2;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  v4 = RpcBindingCreateW(&Template, &Security, 0, &Binding);
  if ( v4 )
  {
    v7 = "RpcBindingCreateW";
  }
  else
  {
    v4 = RpcBindingSetOption(Binding, 9u, 1u);
    if ( !v4 )
    {
      result = 0;
      *a3 = Binding;
      return result;
    }
    v7 = "RpcBindingSetOption";
  }
  v8 = WfpReportSysErrorAsRpcStatus(v5, v7, v4);
  if ( v8 )
  {
    if ( Binding )
      RpcBindingFree(&Binding);
    WfpReportError(v8, "FwppRpcBindingCreateLocal");
  }
  return v8;
}

```

## disassembly

```asm
0x180008bd0  push    rbp
0x180008bd2  push    rbx
0x180008bd3  push    rdi
0x180008bd4  lea     rbp, [rsp-47h]
0x180008bd9  sub     rsp, 0C0h
0x180008be0  mov     rax, cs:__security_cookie
0x180008be7  xor     rax, rsp
0x180008bea  mov     [rbp+57h+var_18], rax
0x180008bee  xorps   xmm0, xmm0
0x180008bf1  mov     [rbp+57h+var_60], rcx
0x180008bf5  xor     edi, edi
0x180008bf7  mov     [rbp+57h+Security.AuthIdentity], rdx
0x180008bfb  xor     eax, eax
0x180008bfd  mov     [r8], rdi
0x180008c00  movups  xmmword ptr [rbp+57h+Template.Version], xmm0
0x180008c04  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data4], rax
0x180008c08  lea     r9, [rbp+57h+Binding]; Binding
0x180008c0c  lea     rax, [rbp+57h+var_80]
0x180008c10  mov     [rbp+57h+Binding], rdi
0x180008c14  mov     rbx, r8
0x180008c17  mov     [rbp+57h+Security.SecurityQos], rax
0x180008c1b  xor     r8d, r8d; Options
0x180008c1e  mov     [rbp+57h+Template.Version], 1
0x180008c25  lea     rdx, [rbp+57h+Security]; Security
0x180008c29  mov     [rbp+57h+Template.ProtocolSequence], 3
0x180008c30  lea     rcx, [rbp+57h+Template]; Template
0x180008c34  mov     [rbp+57h+var_58], 1
0x180008c3c  movups  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x180008c40  mov     [rbp+57h+var_80], 4
0x180008c47  movups  xmmword ptr [rbp+57h+Template.u1], xmm0
0x180008c4b  mov     [rbp+57h+var_7C], 1
0x180008c53  movdqu  [rbp+57h+var_70], xmm0
0x180008c58  mov     [rbp+57h+var_74], 2
0x180008c5f  mov     qword ptr [rbp+57h+Security+4], rdi
0x180008c63  mov     dword ptr [rbp+57h+Security.ServerPrincName+4], edi
0x180008c66  mov     [rbp+57h+Security.Version], 1
0x180008c6d  mov     [rbp+57h+Security.AuthnLevel], 6
0x180008c74  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x180008c7b  call    cs:__imp_RpcBindingCreateW
0x180008c82  nop     dword ptr [rax+rax+00h]
0x180008c87  test    eax, eax
0x180008c89  jnz     short loc_180008CF5
0x180008c8b  mov     rcx, [rbp+57h+Binding]; hBinding
0x180008c8f  mov     edx, 9; option
0x180008c94  mov     r8d, 1; optionValue
0x180008c9a  call    cs:__imp_RpcBindingSetOption
0x180008ca1  nop     dword ptr [rax+rax+00h]
0x180008ca6  test    eax, eax
0x180008ca8  jnz     short loc_180008CFE
0x180008caa  mov     rcx, [rbp+57h+Binding]
0x180008cae  mov     eax, edi
0x180008cb0  mov     [rbx], rcx
0x180008cb3  mov     rcx, [rbp+57h+var_18]
0x180008cb7  xor     rcx, rsp; StackCookie
0x180008cba  call    __security_check_cookie
0x180008cbf  add     rsp, 0C0h
0x180008cc6  pop     rdi
0x180008cc7  pop     rbx
0x180008cc8  pop     rbp
0x180008cc9  retn
0x180008ccb  cmp     [rbp+57h+Binding], rdi
0x180008ccf  jz      short loc_180008CE1
0x180008cd1  lea     rcx, [rbp+57h+Binding]; Binding
0x180008cd5  call    cs:__imp_RpcBindingFree
0x180008cdc  nop     dword ptr [rax+rax+00h]
0x180008ce1  lea     rdx, aFwpprpcbinding; "FwppRpcBindingCreateLocal"
0x180008ce8  mov     rcx, rbx
0x180008ceb  call    WfpReportError
0x180008cf0  mov     rax, rbx
0x180008cf3  jmp     short loc_180008CB3
0x180008cf5  lea     rdx, aRpcbindingcrea_0; "RpcBindingCreateW"
0x180008cfc  jmp     short loc_180008D05
0x180008cfe  lea     rdx, aRpcbindingseto_0; "RpcBindingSetOption"
0x180008d05  mov     r8d, eax
0x180008d08  call    WfpReportSysErrorAsRpcStatus
0x180008d0d  mov     rbx, rax
0x180008d10  test    rax, rax
0x180008d13  jz      short loc_180008CF0
0x180008d15  jmp     short loc_180008CCB
```
