# CVmAllowListRpcClient::Initialize(void)

- ea: `0x1800771f0`
- end: `0x18007737e`
- name: `?Initialize@CVmAllowListRpcClient@@QEAAJXZ`
- size: `398`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800764f0`
- `0x180076c3c`

## callees

- `0x1800771f0`

## import_xrefs

- `RDPBASE!TRC_TraceBufferW` at `0x180077344`
- `RDPBASE!TRC_TraceBufferW` at `0x180077344`
- `RPCRT4!RpcBindingFree` at `0x18007736a`
- `RPCRT4!RpcBindingFree` at `0x18007736a`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800772ef`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800772ef`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18007728e`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18007728e`
- `RPCRT4!RpcStringBindingComposeW` at `0x180077258`
- `RPCRT4!RpcStringBindingComposeW` at `0x180077258`
- `RPCRT4!RpcStringFreeW` at `0x180077354`
- `RPCRT4!RpcStringFreeW` at `0x180077354`

## string_xrefs

- `0x180077241`: `Security=Identification Dynamic True`
- `0x180077275`: `RpcStringBindingCompose hr[0x%x]`

## pseudocode

```c
__int64 __fastcall CVmAllowListRpcClient::Initialize(RPC_BINDING_HANDLE *Binding)
{
  signed int v2; // ebx
  RPC_STATUS v3; // eax
  RPC_STATUS v4; // eax
  RPC_BINDING_HANDLE v5; // rcx
  RPC_STATUS v6; // eax
  RPC_SECURITY_QOS SecurityQOS; // [rsp+40h] [rbp-38h] BYREF
  __int128 v9; // [rsp+50h] [rbp-28h]
  __int128 v10; // [rsp+60h] [rbp-18h]
  RPC_WSTR String; // [rsp+A0h] [rbp+28h] BYREF

  String = 0;
  SecurityQOS = 0;
  v9 = 0;
  v10 = 0;
  if ( *Binding )
  {
    v2 = -2147418113;
    TRC_TraceBufferW(
      3,
      4096,
      44,
      L"CVmAllowListRpcClient::Initialize",
      L"clientcore\\termsrv\\rap\\allow\\lib\\vmrpcclient.cpp",
      0,
      L"Invalid m_hRpcBinding hr[0x%x]",
      -2147418113,
      *(_QWORD *)&SecurityQOS.Version,
      *(_QWORD *)&SecurityQOS.IdentityTracking,
      v9,
      v10);
  }
  else
  {
    v2 = 0;
    v3 = RpcStringBindingComposeW(
           0,
           (RPC_WSTR)L"ncalrpc",
           0,
           (RPC_WSTR)L"RdvVmAllowListRpc",
           (RPC_WSTR)L"Security=Identification Dynamic True",
           &String);
    if ( v3 )
    {
      if ( v3 > 0 )
        v2 = (unsigned __int16)v3 | 0x80070000;
      else
        v2 = v3;
      TRC_TraceBufferW(
        3,
        4096,
        57,
        L"CVmAllowListRpcClient::Initialize",
        L"clientcore\\termsrv\\rap\\allow\\lib\\vmrpcclient.cpp",
        0,
        L"RpcStringBindingCompose hr[0x%x]",
        v2,
        *(_QWORD *)&SecurityQOS.Version,
        *(_QWORD *)&SecurityQOS.IdentityTracking,
        v9,
        v10);
    }
    else
    {
      v4 = RpcBindingFromStringBindingW(String, Binding);
      if ( v4 )
      {
        if ( v4 > 0 )
          v2 = (unsigned __int16)v4 | 0x80070000;
        else
          v2 = v4;
        TRC_TraceBufferW(
          3,
          4096,
          64,
          L"CVmAllowListRpcClient::Initialize",
          L"clientcore\\termsrv\\rap\\allow\\lib\\vmrpcclient.cpp",
          0,
          L"RpcBindingFromStringBinding hr[0x%x]",
          v2,
          *(_QWORD *)&SecurityQOS.Version,
          *(_QWORD *)&SecurityQOS.IdentityTracking,
          v9,
          v10);
      }
      else
      {
        v5 = *Binding;
        *(_QWORD *)&SecurityQOS.Version = 4;
        SecurityQOS.IdentityTracking = 1;
        SecurityQOS.ImpersonationType = 2;
        v6 = RpcBindingSetAuthInfoExW(v5, 0, 6u, 0xAu, 0, 0, &SecurityQOS);
        if ( v6 )
        {
          if ( v6 > 0 )
            v2 = (unsigned __int16)v6 | 0x80070000;
          else
            v2 = v6;
          TRC_TraceBufferW(
            3,
            4096,
            82,
            L"CVmAllowListRpcClient::Initialize",
            L"clientcore\\termsrv\\rap\\allow\\lib\\vmrpcclient.cpp",
            0,
            L"RpcBindingSetAuthInfoEx hr[0x%x]",
            v2,
            *(_QWORD *)&SecurityQOS.Version,
            *(_QWORD *)&SecurityQOS.IdentityTracking,
            v9,
            v10);
        }
      }
    }
  }
  if ( String )
  {
    RpcStringFreeW(&String);
    String = 0;
  }
  if ( v2 < 0 && *Binding )
  {
    RpcBindingFree(Binding);
    *Binding = 0;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800771f0  push    rbp
0x1800771f2  push    rbx
0x1800771f3  push    rsi
0x1800771f4  push    rdi
0x1800771f5  mov     rbp, rsp
0x1800771f8  sub     rsp, 78h
0x1800771fc  xorps   xmm0, xmm0
0x1800771ff  xor     esi, esi
0x180077201  mov     rdi, rcx
0x180077204  mov     [rbp+String], rsi
0x180077208  movups  xmmword ptr [rbp+var_38.Version], xmm0
0x18007720c  movups  [rbp+var_28], xmm0
0x180077210  movups  [rbp+var_18], xmm0
0x180077214  cmp     [rcx], rsi
0x180077217  jz      short loc_18007722E
0x180077219  mov     ebx, 8000FFFFh
0x18007721e  lea     rax, aInvalidMHrpcbi; "Invalid m_hRpcBinding hr[0x%x]"
0x180077225  lea     r8d, [rsi+2Ch]
0x180077229  jmp     loc_180077319
0x18007722e  lea     rax, [rbp+String]
0x180077232  xor     r8d, r8d; NetworkAddr
0x180077235  mov     [rsp+78h+StringBinding], rax; StringBinding
0x18007723a  lea     r9, Endpoint; "RdvVmAllowListRpc"
0x180077241  lea     rax, Options; "Security=Identification Dynamic True"
0x180077248  xor     ecx, ecx; ObjUuid
0x18007724a  lea     rdx, ProtSeq; "ncalrpc"
0x180077251  mov     [rsp+78h+Options], rax; Options
0x180077256  mov     ebx, esi
0x180077258  call    cs:__imp_RpcStringBindingComposeW
0x18007725e  test    eax, eax
0x180077260  jz      short loc_180077287
0x180077262  jg      short loc_180077268
0x180077264  mov     ebx, eax
0x180077266  jmp     short loc_180077271
0x180077268  movzx   ebx, ax
0x18007726b  or      ebx, 80070000h
0x180077271  test    ebx, ebx
0x180077273  jns     short loc_180077287
0x180077275  lea     rax, aRpcstringbindi_0; "RpcStringBindingCompose hr[0x%x]"
0x18007727c  mov     r8d, 39h ; '9'
0x180077282  jmp     loc_180077319
0x180077287  mov     rcx, [rbp+String]; StringBinding
0x18007728b  mov     rdx, rdi; Binding
0x18007728e  call    cs:__imp_RpcBindingFromStringBindingW
0x180077294  test    eax, eax
0x180077296  jz      short loc_1800772BA
0x180077298  jg      short loc_18007729E
0x18007729a  mov     ebx, eax
0x18007729c  jmp     short loc_1800772A7
0x18007729e  movzx   ebx, ax
0x1800772a1  or      ebx, 80070000h
0x1800772a7  test    ebx, ebx
0x1800772a9  jns     short loc_1800772BA
0x1800772ab  lea     rax, aRpcbindingfrom_0; "RpcBindingFromStringBinding hr[0x%x]"
0x1800772b2  mov     r8d, 40h ; '@'
0x1800772b8  jmp     short loc_180077319
0x1800772ba  mov     rcx, [rdi]; Binding
0x1800772bd  lea     rax, [rbp+var_38]
0x1800772c1  xor     edx, edx; ServerPrincName
0x1800772c3  mov     [rsp+78h+SecurityQOS], rax; SecurityQOS
0x1800772c8  mov     dword ptr [rsp+78h+StringBinding], esi; AuthzSvc
0x1800772cc  mov     qword ptr [rbp+var_38.Version], 4
0x1800772d4  mov     [rbp+var_38.IdentityTracking], 1
0x1800772db  lea     r9d, [rdx+0Ah]; AuthnSvc
0x1800772df  mov     [rbp+var_38.ImpersonationType], 2
0x1800772e6  lea     r8d, [rdx+6]; AuthnLevel
0x1800772ea  mov     [rsp+78h+Options], rsi; AuthIdentity
0x1800772ef  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800772f5  test    eax, eax
0x1800772f7  jz      short loc_18007734A
0x1800772f9  jg      short loc_1800772FF
0x1800772fb  mov     ebx, eax
0x1800772fd  jmp     short loc_180077308
0x1800772ff  movzx   ebx, ax
0x180077302  or      ebx, 80070000h
0x180077308  test    ebx, ebx
0x18007730a  jns     short loc_18007734A
0x18007730c  lea     rax, aRpcbindingseta_0; "RpcBindingSetAuthInfoEx hr[0x%x]"
0x180077313  mov     r8d, 52h ; 'R'
0x180077319  mov     [rsp+78h+var_40], ebx
0x18007731d  lea     r9, aCvmallowlistrp_0; "CVmAllowListRpcClient::Initialize"
0x180077324  mov     [rsp+78h+SecurityQOS], rax
0x180077329  mov     edx, 1000h
0x18007732e  lea     rax, aClientcoreTerm; "clientcore\\termsrv\\rap\\allow\\lib\\v"...
0x180077335  mov     [rsp+78h+StringBinding], rsi
0x18007733a  mov     ecx, 3
0x18007733f  mov     [rsp+78h+Options], rax
0x180077344  call    cs:__imp_TRC_TraceBufferW
0x18007734a  cmp     [rbp+String], rsi
0x18007734e  jz      short loc_18007735E
0x180077350  lea     rcx, [rbp+String]; String
0x180077354  call    cs:__imp_RpcStringFreeW
0x18007735a  mov     [rbp+String], rsi
0x18007735e  test    ebx, ebx
0x180077360  jns     short loc_180077373
0x180077362  cmp     [rdi], rsi
0x180077365  jz      short loc_180077373
0x180077367  mov     rcx, rdi; Binding
0x18007736a  call    cs:__imp_RpcBindingFree
0x180077370  mov     [rdi], rsi
0x180077373  mov     eax, ebx
0x180077375  add     rsp, 78h
0x180077379  pop     rdi
0x18007737a  pop     rsi
0x18007737b  pop     rbx
0x18007737c  pop     rbp
0x18007737d  retn
```
