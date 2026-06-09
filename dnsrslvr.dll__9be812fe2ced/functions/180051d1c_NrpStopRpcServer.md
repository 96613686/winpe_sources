# NrpStopRpcServer

- ea: `0x180051d1c`
- end: `0x180051def`
- name: `NrpStopRpcServer`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18003cfc0`

## callees

- `0x180046ec0`
- `0x180051c5c`
- `0x180051d1c`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `RPCRT4!RpcServerUnregisterIfEx` at `0x180051da5`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x180051da5`
- `RPCRT4!RpcBindingVectorFree` at `0x180051d92`
- `RPCRT4!RpcBindingVectorFree` at `0x180051d92`
- `RPCRT4!RpcEpUnregister` at `0x180051d87`
- `RPCRT4!RpcEpUnregister` at `0x180051d87`
- `RPCRT4!RpcServerInqBindings` at `0x180051d6e`
- `RPCRT4!RpcServerInqBindings` at `0x180051d6e`
- `WS2_32!__imp_WSACleanup` at `0x180051dad`
- `WS2_32!__imp_WSACleanup` at `0x180051dad`

## pseudocode

```c
void NrpStopRpcServer()
{
  unsigned int v0; // ebx
  RPC_BINDING_VECTOR *BindingVector; // [rsp+20h] [rbp-18h] BYREF

  BindingVector = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_(1035, 22, WPP_f7a7b403e64b309f267ad22af7388cf2_Traceguids);
  if ( RpcServerInitialized )
  {
    NrpNotifyAfd(0);
    if ( !RpcServerInqBindings(&BindingVector) )
    {
      RpcEpUnregister(qword_180091050, BindingVector, 0);
      RpcBindingVectorFree(&BindingVector);
    }
    v0 = RpcServerUnregisterIfEx(qword_180091050, 0, 1);
    WSACleanup();
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 23, WPP_f7a7b403e64b309f267ad22af7388cf2_Traceguids, v0);
    RpcServerInitialized = 0;
  }
}

```

## disassembly

```asm
0x180051d1c  push    rbx
0x180051d1e  sub     rsp, 30h
0x180051d22  mov     rax, cs:__security_cookie
0x180051d29  xor     rax, rsp
0x180051d2c  mov     [rsp+38h+var_10], rax
0x180051d31  mov     [rsp+38h+BindingVector], 0
0x180051d3a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180051d41  jz      short loc_180051D59
0x180051d43  mov     edx, 16h
0x180051d48  lea     r8, WPP_f7a7b403e64b309f267ad22af7388cf2_Traceguids
0x180051d4f  mov     ecx, 40Bh
0x180051d54  call    WPP_SF_
0x180051d59  cmp     cs:RpcServerInitialized, 0
0x180051d60  jz      short loc_180051DDC
0x180051d62  xor     ecx, ecx
0x180051d64  call    NrpNotifyAfd
0x180051d69  lea     rcx, [rsp+38h+BindingVector]; BindingVector
0x180051d6e  call    cs:__imp_RpcServerInqBindings
0x180051d74  test    eax, eax
0x180051d76  jnz     short loc_180051D98
0x180051d78  mov     rdx, [rsp+38h+BindingVector]; BindingVector
0x180051d7d  lea     rcx, qword_180091050; IfSpec
0x180051d84  xor     r8d, r8d; UuidVector
0x180051d87  call    cs:__imp_RpcEpUnregister
0x180051d8d  lea     rcx, [rsp+38h+BindingVector]; BindingVector
0x180051d92  call    cs:__imp_RpcBindingVectorFree
0x180051d98  xor     edx, edx; MgrTypeUuid
0x180051d9a  lea     rcx, qword_180091050; IfSpec
0x180051da1  lea     r8d, [rdx+1]; RundownContextHandles
0x180051da5  call    cs:__imp_RpcServerUnregisterIfEx
0x180051dab  mov     ebx, eax
0x180051dad  call    cs:__imp_WSACleanup
0x180051db3  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180051dba  jz      short loc_180051DD5
0x180051dbc  mov     edx, 17h
0x180051dc1  lea     r8, WPP_f7a7b403e64b309f267ad22af7388cf2_Traceguids
0x180051dc8  mov     ecx, 40Bh
0x180051dcd  mov     r9d, ebx
0x180051dd0  call    WPP_SF_d
0x180051dd5  mov     cs:RpcServerInitialized, 0
0x180051ddc  mov     rcx, [rsp+38h+var_10]
0x180051de1  xor     rcx, rsp; StackCookie
0x180051de4  call    __security_check_cookie
0x180051de9  add     rsp, 30h
0x180051ded  pop     rbx
0x180051dee  retn
```
