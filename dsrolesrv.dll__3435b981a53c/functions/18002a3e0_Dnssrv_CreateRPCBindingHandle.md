# Dnssrv_CreateRPCBindingHandle

- ea: `0x18002a3e0`
- end: `0x18002a71e`
- name: `Dnssrv_CreateRPCBindingHandle`
- size: `830`
- prototype: `RPC_BINDING_HANDLE __fastcall(__int64, __int64, char)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180029220`
- `0x1800295c0`

## callees

- `0x1800237ac`
- `0x180029b54`
- `0x18002a270`
- `0x18002a2b8`
- `0x18002a3e0`
- `0x18002a788`
- `0x18002a7c4`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a6e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a6e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a6f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a6f5`
- `RPCRT4!RpcStringBindingComposeW` at `0x18002a4e5`
- `RPCRT4!RpcStringBindingComposeW` at `0x18002a4e5`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18002a532`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18002a532`
- `RPCRT4!RpcBindingSetOption` at `0x18002a6af`
- `RPCRT4!RpcBindingSetOption` at `0x18002a6af`
- `RPCRT4!RpcBindingSetAuthInfoA` at `0x18002a63b`
- `RPCRT4!RpcBindingSetAuthInfoA` at `0x18002a63b`
- `RPCRT4!RpcBindingSetAuthInfoExA` at `0x18002a611`
- `RPCRT4!RpcBindingSetAuthInfoExA` at `0x18002a611`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18002a5c8`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18002a5c8`
- `RPCRT4!RpcMgmtSetComTimeout` at `0x18002a676`
- `RPCRT4!RpcMgmtSetComTimeout` at `0x18002a676`
- `RPCRT4!RpcStringFreeW` at `0x18002a6e0`
- `RPCRT4!RpcStringFreeW` at `0x18002a6e0`

## string_xrefs

- `0x18002a490`: `Security=Impersonation Static True`
- `0x18002a4b1`: `Security=Impersonation Static True`

## pseudocode

```c
RPC_BINDING_HANDLE __fastcall Dnssrv_CreateRPCBindingHandle(__int64 a1, __int64 a2, char a3)
{
  RPC_WSTR v3; // rsi
  unsigned int ProtocolToUse; // eax
  unsigned int v6; // edi
  RPC_STATUS v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  DWORD v10; // ebx
  RPC_STATUS v11; // eax
  int v12; // edx
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  _QWORD *v16; // rcx
  int v17; // edx
  RPC_STATUS v18; // r9d
  RPC_STATUS v19; // eax
  unsigned int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  int Options; // [rsp+20h] [rbp-50h]
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-30h] BYREF
  RPC_WSTR String; // [rsp+48h] [rbp-28h] BYREF
  RPC_WSTR ServerPrincName; // [rsp+50h] [rbp-20h] BYREF
  RPC_SECURITY_QOS SecurityQos; // [rsp+58h] [rbp-18h] BYREF

  v3 = 0;
  String = 0;
  Binding = 0;
  ServerPrincName = 0;
  SecurityQos.Version = 1;
  SecurityQos.Capabilities = 1;
  if ( (a3 & 2) != 0 )
  {
    *(_QWORD *)&SecurityQos.Capabilities = 9;
    SecurityQos.ImpersonationType = 4;
  }
  else
  {
    SecurityQos.IdentityTracking = 0;
    SecurityQos.ImpersonationType = 3;
  }
  ProtocolToUse = FindProtocolToUse();
  v6 = ProtocolToUse;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)&WPP_87a2ea4a098c37aacff7f2976f8d2488_Traceguids,
      ProtocolToUse);
  }
  if ( v6 == 4 )
  {
    v7 = RpcStringBindingComposeW(
           0,
           (RPC_WSTR)L"ncalrpc",
           0,
           L"DNSSERVERLPC",
           L"Security=Impersonation Static True",
           &String);
  }
  else if ( v6 == 2 )
  {
    v7 = RpcStringBindingComposeW(
           0,
           L"ncacn_np",
           0,
           L"\\PIPE\\DNSSERVER",
           L"Security=Impersonation Static True",
           &String);
  }
  else
  {
    v7 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncacn_ip_tcp", 0, (RPC_WSTR)&base, 0, &String);
  }
  v10 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, v6, v7);
    }
    goto LABEL_49;
  }
  v11 = RpcBindingFromStringBindingW(String, &Binding);
  v10 = v11;
  if ( v11 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_49;
    }
    v17 = 15;
    goto LABEL_23;
  }
  if ( v6 == 1 )
  {
    if ( (a3 & 1) != 0 )
    {
      v19 = RpcBindingSetAuthInfoA(Binding, (RPC_CSTR)"DnsServerApp", 2u, 0xAu, 0, 0);
    }
    else
    {
      if ( !(unsigned int)makeSpn(v13, v12, v14, v15, Options, (__int64)&ServerPrincName) )
      {
        v3 = ServerPrincName;
        v11 = RpcBindingSetAuthInfoExW(Binding, ServerPrincName, 6u, 9u, 0, 0, &SecurityQos);
        v10 = v11;
        if ( v11 )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          {
            goto LABEL_49;
          }
          v17 = 16;
LABEL_23:
          v18 = v11;
LABEL_24:
          WPP_SF_d(v16[2], v17, (unsigned int)&WPP_87a2ea4a098c37aacff7f2976f8d2488_Traceguids, v18);
          goto LABEL_49;
        }
        goto LABEL_40;
      }
      v19 = RpcBindingSetAuthInfoExA(Binding, (RPC_CSTR)"DnsServerApp", 2u, 9u, 0, 0, &SecurityQos);
      v3 = ServerPrincName;
    }
    v10 = v19;
    if ( v19 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_49;
      }
      v17 = 17;
      v18 = v19;
      goto LABEL_24;
    }
  }
LABEL_40:
  v20 = RpcMgmtSetComTimeout(Binding, 0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, v22, v20);
  }
  RpcBindingSetOption(Binding, 0xCu, 0x493E0u);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2));
  }
  v10 = 0;
LABEL_49:
  RpcStringFreeW(&String);
  LocalFree(v3);
  if ( !v10 )
    return Binding;
  SetLastError(v10);
  return 0;
}

```

## disassembly

```asm
0x18002a3e0  push    rbp
0x18002a3e2  push    rbx
0x18002a3e3  push    rsi
0x18002a3e4  push    rdi
0x18002a3e5  push    r13
0x18002a3e7  push    r14
0x18002a3e9  push    r15
0x18002a3eb  mov     rbp, rsp
0x18002a3ee  sub     rsp, 70h
0x18002a3f2  mov     rax, cs:__security_cookie
0x18002a3f9  xor     rax, rsp
0x18002a3fc  mov     [rbp+var_8], rax
0x18002a400  xor     esi, esi
0x18002a402  mov     [rbp+String], 0
0x18002a40a  mov     [rbp+Binding], 0
0x18002a412  mov     r14d, r8d
0x18002a415  mov     [rbp+ServerPrincName], rsi
0x18002a419  lea     eax, [rsi+1]
0x18002a41c  mov     [rbp+SecurityQos.Version], eax
0x18002a41f  lea     r15d, [rsi+4]
0x18002a423  mov     [rbp+SecurityQos.Capabilities], eax
0x18002a426  test    r8b, 2
0x18002a42a  jz      short loc_18002A43A
0x18002a42c  mov     qword ptr [rbp+SecurityQos.Capabilities], 9
0x18002a434  mov     [rbp+SecurityQos.ImpersonationType], r15d
0x18002a438  jmp     short loc_18002A444
0x18002a43a  mov     [rbp+SecurityQos.IdentityTracking], esi
0x18002a43d  mov     [rbp+SecurityQos.ImpersonationType], 3
0x18002a444  call    FindProtocolToUse
0x18002a449  mov     edi, eax
0x18002a44b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a452  lea     r13, WPP_GLOBAL_Control
0x18002a459  cmp     rcx, r13
0x18002a45c  jz      short loc_18002A482
0x18002a45e  test    [rcx+1Ch], r15b
0x18002a462  jz      short loc_18002A482
0x18002a464  cmp     [rcx+19h], r15b
0x18002a468  jb      short loc_18002A482
0x18002a46a  mov     rcx, [rcx+10h]
0x18002a46e  lea     r8, WPP_87a2ea4a098c37aacff7f2976f8d2488_Traceguids
0x18002a475  mov     edx, 0Dh
0x18002a47a  mov     r9d, eax
0x18002a47d  call    WPP_SF_d
0x18002a482  lea     rax, [rbp+String]
0x18002a486  mov     [rsp+70h+StringBinding], rax; StringBinding
0x18002a48b  cmp     edi, r15d
0x18002a48e  jnz     short loc_18002A4AC
0x18002a490  lea     rax, aSecurityImpers; "Security=Impersonation Static True"
0x18002a497  mov     [rsp+70h+Options], rax
0x18002a49c  lea     r9, aDnsserverlpc; "DNSSERVERLPC"
0x18002a4a3  lea     rdx, String1; "ncalrpc"
0x18002a4aa  jmp     short loc_18002A4E0
0x18002a4ac  cmp     edi, 2
0x18002a4af  jnz     short loc_18002A4CD
0x18002a4b1  lea     rax, aSecurityImpers; "Security=Impersonation Static True"
0x18002a4b8  mov     [rsp+70h+Options], rax
0x18002a4bd  lea     r9, aPipeDnsserver; "\\PIPE\\DNSSERVER"
0x18002a4c4  lea     rdx, aNcacnNp; "ncacn_np"
0x18002a4cb  jmp     short loc_18002A4E0
0x18002a4cd  mov     [rsp+70h+Options], rsi; Options
0x18002a4d2  lea     r9, base; Endpoint
0x18002a4d9  lea     rdx, ProtSeq; "ncacn_ip_tcp"
0x18002a4e0  xor     r8d, r8d; NetworkAddr
0x18002a4e3  xor     ecx, ecx; ObjUuid
0x18002a4e5  call    cs:__imp_RpcStringBindingComposeW
0x18002a4eb  mov     ebx, eax
0x18002a4ed  test    eax, eax
0x18002a4ef  jz      short loc_18002A52A
0x18002a4f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a4f8  cmp     rcx, r13
0x18002a4fb  jz      loc_18002A6DC
0x18002a501  test    [rcx+1Ch], r15b
0x18002a505  jz      loc_18002A6DC
0x18002a50b  cmp     [rcx+19h], r15b
0x18002a50f  jb      loc_18002A6DC
0x18002a515  mov     rcx, [rcx+10h]
0x18002a519  mov     r9d, edi
0x18002a51c  mov     dword ptr [rsp+70h+Options], eax
0x18002a520  call    WPP_SF_dd
0x18002a525  jmp     loc_18002A6DC
0x18002a52a  mov     rcx, [rbp+String]; StringBinding
0x18002a52e  lea     rdx, [rbp+Binding]; Binding
0x18002a532  call    cs:__imp_RpcBindingFromStringBindingW
0x18002a538  mov     ebx, eax
0x18002a53a  test    eax, eax
0x18002a53c  jz      short loc_18002A57F
0x18002a53e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a545  cmp     rcx, r13
0x18002a548  jz      loc_18002A6DC
0x18002a54e  test    [rcx+1Ch], r15b
0x18002a552  jz      loc_18002A6DC
0x18002a558  cmp     [rcx+19h], r15b
0x18002a55c  jb      loc_18002A6DC
0x18002a562  mov     edx, 0Fh
0x18002a567  mov     r9d, eax
0x18002a56a  mov     rcx, [rcx+10h]
0x18002a56e  lea     r8, WPP_87a2ea4a098c37aacff7f2976f8d2488_Traceguids
0x18002a575  call    WPP_SF_d
0x18002a57a  jmp     loc_18002A6DC
0x18002a57f  cmp     edi, 1
0x18002a582  jnz     loc_18002A670
0x18002a588  test    dil, r14b
0x18002a58b  jnz     loc_18002A61D
0x18002a591  lea     rax, [rbp+ServerPrincName]
0x18002a595  mov     [rsp+70h+StringBinding], rax
0x18002a59a  call    makeSpn
0x18002a59f  mov     rcx, [rbp+Binding]; Binding
0x18002a5a3  lea     r9d, [rdi+8]; AuthnSvc
0x18002a5a7  test    eax, eax
0x18002a5a9  lea     rax, [rbp+SecurityQos]
0x18002a5ad  mov     [rsp+70h+SecurityQOS], rax; SecurityQos
0x18002a5b2  mov     dword ptr [rsp+70h+StringBinding], esi; AuthzSvc
0x18002a5b6  mov     [rsp+70h+Options], rsi; AuthIdentity
0x18002a5bb  jnz     short loc_18002A604
0x18002a5bd  mov     rsi, [rbp+ServerPrincName]
0x18002a5c1  lea     r8d, [rdi+5]; AuthnLevel
0x18002a5c5  mov     rdx, rsi; ServerPrincName
0x18002a5c8  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18002a5ce  mov     ebx, eax
0x18002a5d0  test    eax, eax
0x18002a5d2  jz      loc_18002A670
0x18002a5d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a5df  cmp     rcx, r13
0x18002a5e2  jz      loc_18002A6DC
0x18002a5e8  test    [rcx+1Ch], r15b
0x18002a5ec  jz      loc_18002A6DC
0x18002a5f2  cmp     [rcx+19h], r15b
0x18002a5f6  jb      loc_18002A6DC
0x18002a5fc  lea     edx, [rdi+0Fh]
0x18002a5ff  jmp     loc_18002A567
0x18002a604  mov     r8d, 2; AuthnLevel
0x18002a60a  lea     rdx, aDnsserverapp; "DnsServerApp"
0x18002a611  call    cs:__imp_RpcBindingSetAuthInfoExA
0x18002a617  mov     rsi, [rbp+ServerPrincName]
0x18002a61b  jmp     short loc_18002A641
0x18002a61d  mov     rcx, [rbp+Binding]; Binding
0x18002a621  lea     rdx, aDnsserverapp; "DnsServerApp"
0x18002a628  mov     r9d, 0Ah; AuthnSvc
0x18002a62e  mov     dword ptr [rsp+70h+StringBinding], esi; AuthzSvc
0x18002a632  mov     [rsp+70h+Options], rsi; AuthIdentity
0x18002a637  lea     r8d, [r9-8]; AuthnLevel
0x18002a63b  call    cs:__imp_RpcBindingSetAuthInfoA
0x18002a641  mov     ebx, eax
0x18002a643  test    eax, eax
0x18002a645  jz      short loc_18002A670
0x18002a647  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a64e  cmp     rcx, r13
0x18002a651  jz      loc_18002A6DC
0x18002a657  test    [rcx+1Ch], r15b
0x18002a65b  jz      short loc_18002A6DC
0x18002a65d  cmp     [rcx+19h], r15b
0x18002a661  jb      short loc_18002A6DC
0x18002a663  mov     edx, 11h
0x18002a668  mov     r9d, eax
0x18002a66b  jmp     loc_18002A56A
0x18002a670  mov     rcx, [rbp+Binding]; Binding
0x18002a674  xor     edx, edx; Timeout
0x18002a676  call    cs:__imp_RpcMgmtSetComTimeout
0x18002a67c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a683  cmp     rcx, r13
0x18002a686  jz      short loc_18002A6A0
0x18002a688  test    [rcx+1Ch], r15b
0x18002a68c  jz      short loc_18002A6A0
0x18002a68e  cmp     [rcx+19h], r15b
0x18002a692  jb      short loc_18002A6A0
0x18002a694  mov     rcx, [rcx+10h]
0x18002a698  mov     r9d, eax
0x18002a69b  call    WPP_SF_D
0x18002a6a0  mov     rcx, [rbp+Binding]; hBinding
0x18002a6a4  mov     edx, 0Ch; option
0x18002a6a9  mov     r8d, 493E0h; optionValue
0x18002a6af  call    cs:__imp_RpcBindingSetOption
0x18002a6b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a6bc  cmp     rcx, r13
0x18002a6bf  jz      short loc_18002A6DA
0x18002a6c1  test    [rcx+1Ch], r15b
0x18002a6c5  jz      short loc_18002A6DA
0x18002a6c7  cmp     [rcx+19h], r15b
0x18002a6cb  jb      short loc_18002A6DA
0x18002a6cd  mov     rcx, [rcx+10h]
0x18002a6d1  mov     dword ptr [rsp+70h+Options], eax
0x18002a6d5  call    WPP_SF_dD
0x18002a6da  xor     ebx, ebx
0x18002a6dc  lea     rcx, [rbp+String]; String
0x18002a6e0  call    cs:__imp_RpcStringFreeW
0x18002a6e6  mov     rcx, rsi; hMem
0x18002a6e9  call    cs:__imp_LocalFree
0x18002a6ef  test    ebx, ebx
0x18002a6f1  jz      short loc_18002A6FF
0x18002a6f3  mov     ecx, ebx; dwErrCode
0x18002a6f5  call    cs:__imp_SetLastError
0x18002a6fb  xor     eax, eax
0x18002a6fd  jmp     short loc_18002A703
0x18002a6ff  mov     rax, [rbp+Binding]
0x18002a703  mov     rcx, [rbp+var_8]
0x18002a707  xor     rcx, rsp; StackCookie
0x18002a70a  call    __security_check_cookie
0x18002a70f  add     rsp, 70h
0x18002a713  pop     r15
0x18002a715  pop     r14
0x18002a717  pop     r13
0x18002a719  pop     rdi
0x18002a71a  pop     rsi
0x18002a71b  pop     rbx
0x18002a71c  pop     rbp
0x18002a71d  retn
```
