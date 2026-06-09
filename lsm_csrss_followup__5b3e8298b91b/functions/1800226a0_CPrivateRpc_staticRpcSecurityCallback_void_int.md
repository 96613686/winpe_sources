# CPrivateRpc::staticRpcSecurityCallback(void *,int)

- ea: `0x1800226a0`
- end: `0x180022890`
- name: `?staticRpcSecurityCallback@CPrivateRpc@@CAJPEAXH@Z`
- size: `496`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE ClientBinding, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022670`
- `0x180022690`

## callees

- `0x1800074c0`
- `0x1800125c0`
- `0x1800226a0`
- `0x18004a0e4`
- `0x18004b460`
- `0x18004bf44`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002273a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002273a`
- `RPCRT4!RpcBindingToStringBindingW` at `0x1800226ea`
- `RPCRT4!RpcBindingToStringBindingW` at `0x1800226ea`
- `RPCRT4!RpcStringFreeW` at `0x180022729`
- `RPCRT4!RpcStringFreeW` at `0x180022746`
- `RPCRT4!RpcStringFreeW` at `0x180022836`
- `RPCRT4!RpcStringFreeW` at `0x180022729`
- `RPCRT4!RpcStringFreeW` at `0x180022746`
- `RPCRT4!RpcStringFreeW` at `0x180022836`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180022772`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180022772`
- `RPCRT4!RpcImpersonateClient` at `0x180022791`
- `RPCRT4!RpcImpersonateClient` at `0x180022791`
- `RPCRT4!RpcRevertToSelf` at `0x1800227a8`
- `RPCRT4!RpcRevertToSelf` at `0x180022876`
- `RPCRT4!RpcRevertToSelf` at `0x1800227a8`
- `RPCRT4!RpcRevertToSelf` at `0x180022876`
- `RPCRT4!RpcStringBindingParseW` at `0x180022717`
- `RPCRT4!RpcStringBindingParseW` at `0x180022717`

## string_xrefs

- `0x180022815`: `Cannot impersonate client: %d`
- `0x180022861`: `staticRpcSecurityCallback: Callers have to be system`
- `0x180022858`: `staticRpcSecurityCallback: Callers must be system or admin`

## pseudocode

```c
__int64 __fastcall CPrivateRpc::staticRpcSecurityCallback(RPC_BINDING_HANDLE ClientBinding, int a2)
{
  unsigned int v4; // eax
  RPC_STATUS v5; // eax
  int v6; // ebx
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  const char *v11; // rdx
  RPC_WSTR StringBinding; // [rsp+30h] [rbp-69h] BYREF
  RPC_WSTR Protseq; // [rsp+38h] [rbp-61h] BYREF
  __int64 RpcCallAttributes; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v15[32]; // [rsp+48h] [rbp-51h] BYREF
  int v16; // [rsp+68h] [rbp-31h]
  int v17; // [rsp+70h] [rbp-29h]

  StringBinding = 0;
  Protseq = 0;
  memset_0(&RpcCallAttributes, 0, 0x78u);
  v4 = RpcBindingToStringBindingW(ClientBinding, &StringBinding);
  if ( v4 )
  {
    _DbgPrintMessage(8, "RpcBindingToStringBinding failed - %d", v4);
    return 5;
  }
  v5 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
  if ( v5 )
  {
    _DbgPrintMessage(8, "RpcStringBindingParse failed - %d", v5);
    RpcStringFreeW(&StringBinding);
    return 5;
  }
  RpcStringFreeW(&StringBinding);
  v6 = _o__wcsicmp(Protseq, L"ncalrpc");
  RpcStringFreeW(&Protseq);
  if ( v6 )
  {
    _DbgPrintMessage(8, "Client is not using LPC!");
    return 5;
  }
  memset_0(v15, 0, 0x70u);
  RpcCallAttributes = 3;
  v7 = RpcServerInqCallAttributesW(ClientBinding, &RpcCallAttributes);
  if ( v7 )
  {
    _DbgPrintMessage(8, "RpcServerInqCallAttributes failed - %d", v7);
    return 5;
  }
  if ( v16 != 6 )
  {
    _DbgPrintMessage(8, "AuthLevel != RPC_C_AUTHN_LEVEL_PKT_PRIVACY");
    return 5;
  }
  if ( v17 )
  {
    _DbgPrintMessage(8, "NULL SESSION!");
    return 5;
  }
  v8 = RpcImpersonateClient(0);
  if ( v8 )
  {
    _DbgPrintMessage(8, "Cannot impersonate client: %d", v8);
    return 5;
  }
  if ( (unsigned int)CUtils::IsCallerSystem() && (!a2 || (unsigned int)CUtils::IsCallerAdmin()) )
  {
    v11 = "staticRpcSecurityCallback: Callers have to be system";
    if ( a2 )
      v11 = "staticRpcSecurityCallback: Callers must be system or admin";
    _DbgPrintMessage(8, v11);
    v9 = RpcRevertToSelf();
    if ( !v9 )
      return 5;
    goto LABEL_10;
  }
  v9 = RpcRevertToSelf();
  if ( v9 )
  {
LABEL_10:
    _DbgPrintMessage(8, "RpcRevertToSelf failed: %d", v9);
    return 5;
  }
  return 0;
}

```

## disassembly

```asm
0x1800226a0  push    rbp
0x1800226a2  push    rbx
0x1800226a3  push    rsi
0x1800226a4  push    rdi
0x1800226a5  lea     rbp, [rsp-3Fh]
0x1800226aa  sub     rsp, 0D8h
0x1800226b1  mov     rax, cs:__security_cookie
0x1800226b8  xor     rax, rsp
0x1800226bb  mov     [rbp+57h+var_30], rax
0x1800226bf  mov     edi, edx
0x1800226c1  mov     [rbp+57h+StringBinding], 0
0x1800226c9  xor     edx, edx; Val
0x1800226cb  mov     [rbp+57h+Protseq], 0
0x1800226d3  mov     rsi, rcx
0x1800226d6  lea     rcx, [rbp+57h+RpcCallAttributes]; void *
0x1800226da  lea     r8d, [rdx+78h]; Size
0x1800226de  call    memset_0
0x1800226e3  lea     rdx, [rbp+57h+StringBinding]; StringBinding
0x1800226e7  mov     rcx, rsi; Binding
0x1800226ea  call    cs:__imp_RpcBindingToStringBindingW
0x1800226f0  test    eax, eax
0x1800226f2  jnz     loc_18002280C
0x1800226f8  mov     rcx, [rbp+57h+StringBinding]; StringBinding
0x1800226fc  lea     r8, [rbp+57h+Protseq]; Protseq
0x180022700  mov     [rsp+0F0h+NetworkOptions], 0; NetworkOptions
0x180022709  xor     r9d, r9d; NetworkAddr
0x18002270c  xor     edx, edx; ObjUuid
0x18002270e  mov     [rsp+0F0h+Endpoint], 0; Endpoint
0x180022717  call    cs:__imp_RpcStringBindingParseW
0x18002271d  test    eax, eax
0x18002271f  jnz     loc_18002281E
0x180022725  lea     rcx, [rbp+57h+StringBinding]; String
0x180022729  call    cs:__imp_RpcStringFreeW
0x18002272f  mov     rcx, [rbp+57h+Protseq]
0x180022733  lea     rdx, ProtSeq; "ncalrpc"
0x18002273a  call    cs:__imp__o__wcsicmp
0x180022740  lea     rcx, [rbp+57h+Protseq]; String
0x180022744  mov     ebx, eax
0x180022746  call    cs:__imp_RpcStringFreeW
0x18002274c  test    ebx, ebx
0x18002274e  jnz     loc_1800227E7
0x180022754  xor     edx, edx; Val
0x180022756  lea     r8d, [rbx+70h]; Size
0x18002275a  lea     rcx, [rbp+57h+var_A8]; void *
0x18002275e  call    memset_0
0x180022763  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x180022767  mov     [rbp+57h+RpcCallAttributes], 3
0x18002276f  mov     rcx, rsi; ClientBinding
0x180022772  call    cs:__imp_RpcServerInqCallAttributesW
0x180022778  test    eax, eax
0x18002277a  jnz     loc_180022803
0x180022780  cmp     [rbp+57h+var_88], 6
0x180022784  jnz     loc_18002283E
0x18002278a  cmp     [rbp+57h+var_80], eax
0x18002278d  jnz     short loc_1800227FA
0x18002278f  xor     ecx, ecx; BindingHandle
0x180022791  call    cs:__imp_RpcImpersonateClient
0x180022797  test    eax, eax
0x180022799  jnz     short loc_180022815
0x18002279b  call    ?IsCallerSystem@CUtils@@SAJXZ; CUtils::IsCallerSystem(void)
0x1800227a0  test    eax, eax
0x1800227a2  jnz     loc_180022847
0x1800227a8  call    cs:__imp_RpcRevertToSelf
0x1800227ae  test    eax, eax
0x1800227b0  jz      loc_180022889
0x1800227b6  lea     rdx, aRpcreverttosel_0; "RpcRevertToSelf failed: %d"
0x1800227bd  mov     r8d, eax
0x1800227c0  mov     ecx, 8; int
0x1800227c5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800227ca  mov     eax, 5
0x1800227cf  mov     rcx, [rbp+57h+var_30]
0x1800227d3  xor     rcx, rsp; StackCookie
0x1800227d6  call    __security_check_cookie
0x1800227db  add     rsp, 0D8h
0x1800227e2  pop     rdi
0x1800227e3  pop     rsi
0x1800227e4  pop     rbx
0x1800227e5  pop     rbp
0x1800227e6  retn
0x1800227e7  lea     rdx, aClientIsNotUsi; "Client is not using LPC!"
0x1800227ee  mov     ecx, 8; int
0x1800227f3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800227f8  jmp     short loc_1800227CA
0x1800227fa  lea     rdx, aNullSession; "NULL SESSION!"
0x180022801  jmp     short loc_1800227EE
0x180022803  lea     rdx, aRpcserverinqca; "RpcServerInqCallAttributes failed - %d"
0x18002280a  jmp     short loc_1800227BD
0x18002280c  lea     rdx, aRpcbindingtost; "RpcBindingToStringBinding failed - %d"
0x180022813  jmp     short loc_1800227BD
0x180022815  lea     rdx, aCannotImperson; "Cannot impersonate client: %d"
0x18002281c  jmp     short loc_1800227BD
0x18002281e  mov     r8d, eax
0x180022821  lea     rdx, aRpcstringbindi; "RpcStringBindingParse failed - %d"
0x180022828  mov     ecx, 8; int
0x18002282d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022832  lea     rcx, [rbp+57h+StringBinding]; String
0x180022836  call    cs:__imp_RpcStringFreeW
0x18002283c  jmp     short loc_1800227CA
0x18002283e  lea     rdx, aAuthlevelRpcCA; "AuthLevel != RPC_C_AUTHN_LEVEL_PKT_PRIV"...
0x180022845  jmp     short loc_1800227EE
0x180022847  test    edi, edi
0x180022849  jz      short loc_180022858
0x18002284b  call    ?IsCallerAdmin@CUtils@@SAJXZ; CUtils::IsCallerAdmin(void)
0x180022850  test    eax, eax
0x180022852  jz      loc_1800227A8
0x180022858  lea     rax, aStaticrpcsecur; "staticRpcSecurityCallback: Callers must"...
0x18002285f  test    edi, edi
0x180022861  lea     rdx, aStaticrpcsecur_0; "staticRpcSecurityCallback: Callers have"...
0x180022868  mov     ecx, 8; int
0x18002286d  cmovnz  rdx, rax; char *
0x180022871  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180022876  call    cs:__imp_RpcRevertToSelf
0x18002287c  test    eax, eax
0x18002287e  jz      loc_1800227CA
0x180022884  jmp     loc_1800227B6
0x180022889  xor     eax, eax
0x18002288b  jmp     loc_1800227CF
```
