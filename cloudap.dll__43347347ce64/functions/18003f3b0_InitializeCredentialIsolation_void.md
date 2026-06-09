# InitializeCredentialIsolation(void)

- ea: `0x18003f3b0`
- end: `0x18003f5e4`
- name: `?InitializeCredentialIsolation@@YAJXZ`
- size: `564`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004b1e0`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18003f3b0`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x18003f587`
- `RPCRT4!RpcStringFreeW` at `0x18003f587`
- `RPCRT4!NdrClientCall3` at `0x18003f4e3`
- `RPCRT4!NdrClientCall3` at `0x18003f4e3`
- `RPCRT4!RpcStringBindingComposeW` at `0x18003f3f6`
- `RPCRT4!RpcStringBindingComposeW` at `0x18003f3f6`
- `RPCRT4!RpcBindingFree` at `0x18003f59a`
- `RPCRT4!RpcBindingFree` at `0x18003f59a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18003f471`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18003f471`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003f402`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003f47d`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003f4fc`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003f402`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003f47d`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003f4fc`

## string_xrefs

- `0x18003f411`: `onecore\ds\ext\cloudap\dll\crediso.cpp`
- `0x18003f485`: `onecore\ds\ext\cloudap\dll\crediso.cpp`
- `0x18003f508`: `onecore\ds\ext\cloudap\dll\crediso.cpp`
- `0x18003f43d`: `RpcStringBindingCompose`

## pseudocode

```c
__int64 InitializeCredentialIsolation(void)
{
  RPC_STATUS v0; // eax
  CLIENT_CALL_RETURN v1; // rbx
  const char *v2; // r9
  const char *v3; // rax
  bool v4; // zf
  RPC_STATUS v5; // eax
  const char *v6; // r9
  const char *v7; // r9
  const char *v8; // rax
  __int64 v10; // [rsp+20h] [rbp-48h]
  __int64 v11; // [rsp+20h] [rbp-48h]
  RPC_BINDING_HANDLE Binding; // [rsp+70h] [rbp+8h] BYREF
  RPC_WSTR StringBinding; // [rsp+78h] [rbp+10h] BYREF
  void *v14; // [rsp+80h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v15; // [rsp+88h] [rbp+20h]

  Binding = 0;
  StringBinding = 0;
  v14 = 0;
  v0 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, Endpoint, 0, &StringBinding);
  if ( v0 )
  {
    LODWORD(v1.Pointer) = I_RpcMapWin32Status(v0);
    v2 = "";
    while ( 1 )
    {
      v3 = v2--;
      v4 = *v2 == 92;
      if ( *v2 == 92 )
        break;
      if ( v2 <= "onecore\\ds\\ext\\cloudap\\dll\\crediso.cpp" )
      {
        v4 = *v2 == 92;
        break;
      }
    }
    if ( v4 )
      v2 = v3;
    LODWORD(v10) = 48;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LODWORD(v1.Pointer), v2, v10, "RpcStringBindingCompose", &Class);
  }
  else
  {
    v5 = RpcBindingFromStringBindingW(StringBinding, &Binding);
    if ( v5 )
    {
      LODWORD(v1.Pointer) = I_RpcMapWin32Status(v5);
      v6 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\crediso.cpp");
      LODWORD(v10) = 56;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LODWORD(v1.Pointer), v6, v10, "RpcBindingFromStringBinding", &Class);
    }
    else
    {
      v15.Simple = 0;
      v1.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&CloudApIumRpc::CloudApIum_ProxyInfo, 0, 0, Binding, &v14).Pointer;
      v15.Pointer = v1.Pointer;
      if ( SLODWORD(v1.Simple) >= 0 )
      {
        g_cloudApIumRpcBinding = Binding;
        Binding = 0;
        g_cloudApIumContext = v14;
        v14 = 0;
      }
      else
      {
        v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\crediso.cpp");
        LODWORD(v11) = 66;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LODWORD(v1.Pointer), v7, v11, "CloudApIumGetContext", &Class);
      }
    }
  }
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( LODWORD(v1.Pointer) )
  {
    v8 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\crediso.cpp");
    LODWORD(v11) = 85;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LODWORD(v1.Pointer), v8, v11, "InitializeCredentialIsolation", &Class);
  }
  return LODWORD(v1.Pointer);
}

```

## disassembly

```asm
0x18003f3b0  mov     r11, rsp
0x18003f3b3  push    rbx
0x18003f3b4  push    rsi
0x18003f3b5  push    r14
0x18003f3b7  sub     rsp, 50h
0x18003f3bb  mov     qword ptr [r11+8], 0
0x18003f3c3  mov     qword ptr [r11+10h], 0
0x18003f3cb  mov     qword ptr [r11+18h], 0
0x18003f3d3  lea     rax, [r11+10h]
0x18003f3d7  mov     [r11-40h], rax
0x18003f3db  mov     qword ptr [r11-48h], 0
0x18003f3e3  lea     r9, Endpoint; "LSA_ISO_RPC_SERVER"
0x18003f3ea  xor     r8d, r8d; NetworkAddr
0x18003f3ed  lea     rdx, ProtSeq; "ncalrpc"
0x18003f3f4  xor     ecx, ecx; ObjUuid
0x18003f3f6  call    cs:__imp_RpcStringBindingComposeW
0x18003f3fc  test    eax, eax
0x18003f3fe  jz      short loc_18003F467
0x18003f400  mov     ecx, eax; Status
0x18003f402  call    cs:__imp_I_RpcMapWin32Status
0x18003f408  mov     ebx, eax
0x18003f40a  lea     r9, aOnecoreDsExtCl_1+26h; ""
0x18003f411  lea     rsi, aOnecoreDsExtCl_1; "onecore\\ds\\ext\\cloudap\\dll\\crediso"...
0x18003f418  mov     rax, r9
0x18003f41b  dec     r9
0x18003f41e  cmp     byte ptr [r9], 5Ch ; '\'
0x18003f422  jz      short loc_18003F42D
0x18003f424  cmp     r9, rsi
0x18003f427  ja      short loc_18003F418
0x18003f429  cmp     byte ptr [r9], 5Ch ; '\'
0x18003f42d  cmovz   r9, rax
0x18003f431  lea     r14, Class
0x18003f438  mov     [rsp+68h+var_38], r14
0x18003f43d  lea     rax, aRpcstringbindi; "RpcStringBindingCompose"
0x18003f444  mov     [rsp+68h+var_40], rax
0x18003f449  mov     dword ptr [rsp+68h+var_48], 30h ; '0'
0x18003f451  mov     r8d, ebx
0x18003f454  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003f45b  xor     ecx, ecx
0x18003f45d  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18003f462  jmp     loc_18003F57A
0x18003f467  lea     rdx, [rsp+68h+Binding]; Binding
0x18003f46c  mov     rcx, [rsp+68h+StringBinding]; StringBinding
0x18003f471  call    cs:__imp_RpcBindingFromStringBindingW
0x18003f477  test    eax, eax
0x18003f479  jz      short loc_18003F4B9
0x18003f47b  mov     ecx, eax; Status
0x18003f47d  call    cs:__imp_I_RpcMapWin32Status
0x18003f483  mov     ebx, eax
0x18003f485  lea     rsi, aOnecoreDsExtCl_1; "onecore\\ds\\ext\\cloudap\\dll\\crediso"...
0x18003f48c  mov     rcx, rsi; char *
0x18003f48f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003f494  mov     r9, rax
0x18003f497  lea     r14, Class
0x18003f49e  mov     [rsp+68h+var_38], r14
0x18003f4a3  lea     rax, aRpcbindingfrom; "RpcBindingFromStringBinding"
0x18003f4aa  mov     [rsp+68h+var_40], rax
0x18003f4af  mov     dword ptr [rsp+68h+var_48], 38h ; '8'
0x18003f4b7  jmp     short loc_18003F451
0x18003f4b9  mov     [rsp+68h+arg_18], 0
0x18003f4c5  lea     rax, [rsp+68h+arg_10]
0x18003f4cd  mov     [rsp+68h+var_48], rax
0x18003f4d2  mov     r9, [rsp+68h+Binding]
0x18003f4d7  xor     r8d, r8d; pReturnValue
0x18003f4da  xor     edx, edx; nProcNum
0x18003f4dc  lea     rcx, ?CloudApIum_ProxyInfo@CloudApIumRpc@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18003f4e3  call    cs:__imp_NdrClientCall3
0x18003f4e9  mov     rbx, rax
0x18003f4ec  mov     [rsp+68h+arg_18], rax
0x18003f4f4  mov     [rsp+68h+var_28], eax
0x18003f4f8  jmp     short loc_18003F508
0x18003f4fa  mov     ecx, eax; Status
0x18003f4fc  call    cs:__imp_I_RpcMapWin32Status
0x18003f502  mov     ebx, eax
0x18003f504  mov     [rsp+68h+var_28], eax
0x18003f508  lea     rsi, aOnecoreDsExtCl_1; "onecore\\ds\\ext\\cloudap\\dll\\crediso"...
0x18003f50f  test    ebx, ebx
0x18003f511  jns     short loc_18003F543
0x18003f513  mov     rcx, rsi; char *
0x18003f516  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003f51b  mov     r9, rax
0x18003f51e  lea     r14, Class
0x18003f525  mov     [rsp+68h+var_38], r14
0x18003f52a  lea     rax, aCloudapiumgetc; "CloudApIumGetContext"
0x18003f531  mov     [rsp+68h+var_40], rax
0x18003f536  mov     dword ptr [rsp+68h+var_48], 42h ; 'B'
0x18003f53e  jmp     loc_18003F451
0x18003f543  mov     rax, [rsp+68h+Binding]
0x18003f548  mov     cs:?g_cloudApIumRpcBinding@@3PEAXEA, rax; void * g_cloudApIumRpcBinding
0x18003f54f  mov     [rsp+68h+Binding], 0
0x18003f558  mov     rax, [rsp+68h+arg_10]
0x18003f560  mov     cs:?g_cloudApIumContext@@3PEAXEA, rax; void * g_cloudApIumContext
0x18003f567  mov     [rsp+68h+arg_10], 0
0x18003f573  lea     r14, Class
0x18003f57a  cmp     [rsp+68h+StringBinding], 0
0x18003f580  jz      short loc_18003F58D
0x18003f582  lea     rcx, [rsp+68h+StringBinding]; String
0x18003f587  call    cs:__imp_RpcStringFreeW
0x18003f58d  cmp     [rsp+68h+Binding], 0
0x18003f593  jz      short loc_18003F5A0
0x18003f595  lea     rcx, [rsp+68h+Binding]; Binding
0x18003f59a  call    cs:__imp_RpcBindingFree
0x18003f5a0  test    ebx, ebx
0x18003f5a2  jz      short loc_18003F5D9
0x18003f5a4  mov     rcx, rsi; char *
0x18003f5a7  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003f5ac  mov     r9, rax
0x18003f5af  mov     [rsp+68h+var_38], r14
0x18003f5b4  lea     rax, aInitializecred; "InitializeCredentialIsolation"
0x18003f5bb  mov     [rsp+68h+var_40], rax
0x18003f5c0  mov     dword ptr [rsp+68h+var_48], 55h ; 'U'
0x18003f5c8  mov     r8d, ebx
0x18003f5cb  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003f5d2  xor     ecx, ecx
0x18003f5d4  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18003f5d9  mov     eax, ebx
0x18003f5db  add     rsp, 50h
0x18003f5df  pop     r14
0x18003f5e1  pop     rsi
0x18003f5e2  pop     rbx
0x18003f5e3  retn
0x18007fbfc  push    rbp
0x18007fbfe  sub     rsp, 40h
0x18007fc02  mov     rbp, rdx
0x18007fc05  mov     rcx, [rcx]
0x18007fc08  mov     ecx, [rcx]; ExceptionCode
0x18007fc0a  call    cs:__imp_RpcExceptionFilter
0x18007fc10  nop
0x18007fc11  add     rsp, 40h
0x18007fc15  pop     rbp
0x18007fc16  retn
```
