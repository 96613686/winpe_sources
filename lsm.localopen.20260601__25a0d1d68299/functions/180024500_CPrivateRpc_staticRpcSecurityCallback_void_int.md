# CPrivateRpc::staticRpcSecurityCallback(void *,int)

- ea: `0x180024500`
- end: `0x180024731`
- name: `?staticRpcSecurityCallback@CPrivateRpc@@CAJPEAXH@Z`
- size: `561`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE ClientBinding, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800244d0`
- `0x1800244f0`

## callees

- `0x1800077a0`
- `0x1800163b4`
- `0x180024500`
- `0x18004d3f4`
- `0x18004e850`
- `0x18004f354`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800245ac`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800245ac`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18002454a`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18002454a`
- `RPCRT4!RpcStringFreeW` at `0x180024595`
- `RPCRT4!RpcStringFreeW` at `0x1800245be`
- `RPCRT4!RpcStringFreeW` at `0x1800246cb`
- `RPCRT4!RpcStringFreeW` at `0x180024595`
- `RPCRT4!RpcStringFreeW` at `0x1800245be`
- `RPCRT4!RpcStringFreeW` at `0x1800246cb`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800245f0`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800245f0`
- `RPCRT4!RpcImpersonateClient` at `0x180024615`
- `RPCRT4!RpcImpersonateClient` at `0x180024615`
- `RPCRT4!RpcRevertToSelf` at `0x180024636`
- `RPCRT4!RpcRevertToSelf` at `0x180024711`
- `RPCRT4!RpcRevertToSelf` at `0x180024636`
- `RPCRT4!RpcRevertToSelf` at `0x180024711`
- `RPCRT4!RpcStringBindingParseW` at `0x18002457d`
- `RPCRT4!RpcStringBindingParseW` at `0x18002457d`

## string_xrefs

- `0x1800246aa`: `Cannot impersonate client: %d`
- `0x1800246fc`: `staticRpcSecurityCallback: Callers have to be system`
- `0x1800246f3`: `staticRpcSecurityCallback: Callers must be system or admin`

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
0x180024500  push    rbp
0x180024502  push    rbx
0x180024503  push    rsi
0x180024504  push    rdi
0x180024505  lea     rbp, [rsp-3Fh]
0x18002450a  sub     rsp, 0D8h
0x180024511  mov     rax, cs:__security_cookie
0x180024518  xor     rax, rsp
0x18002451b  mov     [rbp+57h+var_30], rax
0x18002451f  mov     edi, edx
0x180024521  mov     [rbp+57h+StringBinding], 0
0x180024529  xor     edx, edx; Val
0x18002452b  mov     [rbp+57h+Protseq], 0
0x180024533  mov     rsi, rcx
0x180024536  lea     rcx, [rbp+57h+RpcCallAttributes]; void *
0x18002453a  lea     r8d, [rdx+78h]; Size
0x18002453e  call    memset_0
0x180024543  lea     rdx, [rbp+57h+StringBinding]; StringBinding
0x180024547  mov     rcx, rsi; Binding
0x18002454a  call    cs:__imp_RpcBindingToStringBindingW
0x180024551  nop     dword ptr [rax+rax+00h]
0x180024556  test    eax, eax
0x180024558  jnz     loc_1800246A1
0x18002455e  mov     rcx, [rbp+57h+StringBinding]; StringBinding
0x180024562  lea     r8, [rbp+57h+Protseq]; Protseq
0x180024566  mov     [rsp+0F0h+NetworkOptions], 0; NetworkOptions
0x18002456f  xor     r9d, r9d; NetworkAddr
0x180024572  xor     edx, edx; ObjUuid
0x180024574  mov     [rsp+0F0h+Endpoint], 0; Endpoint
0x18002457d  call    cs:__imp_RpcStringBindingParseW
0x180024584  nop     dword ptr [rax+rax+00h]
0x180024589  test    eax, eax
0x18002458b  jnz     loc_1800246B3
0x180024591  lea     rcx, [rbp+57h+StringBinding]; String
0x180024595  call    cs:__imp_RpcStringFreeW
0x18002459c  nop     dword ptr [rax+rax+00h]
0x1800245a1  mov     rcx, [rbp+57h+Protseq]
0x1800245a5  lea     rdx, ProtSeq; "ncalrpc"
0x1800245ac  call    cs:__imp__o__wcsicmp
0x1800245b3  nop     dword ptr [rax+rax+00h]
0x1800245b8  lea     rcx, [rbp+57h+Protseq]; String
0x1800245bc  mov     ebx, eax
0x1800245be  call    cs:__imp_RpcStringFreeW
0x1800245c5  nop     dword ptr [rax+rax+00h]
0x1800245ca  test    ebx, ebx
0x1800245cc  jnz     loc_18002467C
0x1800245d2  xor     edx, edx; Val
0x1800245d4  lea     r8d, [rbx+70h]; Size
0x1800245d8  lea     rcx, [rbp+57h+var_A8]; void *
0x1800245dc  call    memset_0
0x1800245e1  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x1800245e5  mov     [rbp+57h+RpcCallAttributes], 3
0x1800245ed  mov     rcx, rsi; ClientBinding
0x1800245f0  call    cs:__imp_RpcServerInqCallAttributesW
0x1800245f7  nop     dword ptr [rax+rax+00h]
0x1800245fc  test    eax, eax
0x1800245fe  jnz     loc_180024698
0x180024604  cmp     [rbp+57h+var_88], 6
0x180024608  jnz     loc_1800246D9
0x18002460e  cmp     [rbp+57h+var_80], eax
0x180024611  jnz     short loc_18002468F
0x180024613  xor     ecx, ecx; BindingHandle
0x180024615  call    cs:__imp_RpcImpersonateClient
0x18002461c  nop     dword ptr [rax+rax+00h]
0x180024621  test    eax, eax
0x180024623  jnz     loc_1800246AA
0x180024629  call    ?IsCallerSystem@CUtils@@SAJXZ; CUtils::IsCallerSystem(void)
0x18002462e  test    eax, eax
0x180024630  jnz     loc_1800246E2
0x180024636  call    cs:__imp_RpcRevertToSelf
0x18002463d  nop     dword ptr [rax+rax+00h]
0x180024642  test    eax, eax
0x180024644  jz      loc_18002472A
0x18002464a  lea     rdx, aRpcreverttosel_0; "RpcRevertToSelf failed: %d"
0x180024651  mov     r8d, eax
0x180024654  mov     ecx, 8; int
0x180024659  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002465e  mov     eax, 5
0x180024663  mov     rcx, [rbp+57h+var_30]
0x180024667  xor     rcx, rsp; StackCookie
0x18002466a  call    __security_check_cookie
0x18002466f  add     rsp, 0D8h
0x180024676  pop     rdi
0x180024677  pop     rsi
0x180024678  pop     rbx
0x180024679  pop     rbp
0x18002467a  retn
0x18002467c  lea     rdx, aClientIsNotUsi; "Client is not using LPC!"
0x180024683  mov     ecx, 8; int
0x180024688  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002468d  jmp     short loc_18002465E
0x18002468f  lea     rdx, aNullSession; "NULL SESSION!"
0x180024696  jmp     short loc_180024683
0x180024698  lea     rdx, aRpcserverinqca; "RpcServerInqCallAttributes failed - %d"
0x18002469f  jmp     short loc_180024651
0x1800246a1  lea     rdx, aRpcbindingtost; "RpcBindingToStringBinding failed - %d"
0x1800246a8  jmp     short loc_180024651
0x1800246aa  lea     rdx, aCannotImperson; "Cannot impersonate client: %d"
0x1800246b1  jmp     short loc_180024651
0x1800246b3  mov     r8d, eax
0x1800246b6  lea     rdx, aRpcstringbindi; "RpcStringBindingParse failed - %d"
0x1800246bd  mov     ecx, 8; int
0x1800246c2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800246c7  lea     rcx, [rbp+57h+StringBinding]; String
0x1800246cb  call    cs:__imp_RpcStringFreeW
0x1800246d2  nop     dword ptr [rax+rax+00h]
0x1800246d7  jmp     short loc_18002465E
0x1800246d9  lea     rdx, aAuthlevelRpcCA; "AuthLevel != RPC_C_AUTHN_LEVEL_PKT_PRIV"...
0x1800246e0  jmp     short loc_180024683
0x1800246e2  test    edi, edi
0x1800246e4  jz      short loc_1800246F3
0x1800246e6  call    ?IsCallerAdmin@CUtils@@SAJXZ; CUtils::IsCallerAdmin(void)
0x1800246eb  test    eax, eax
0x1800246ed  jz      loc_180024636
0x1800246f3  lea     rax, aStaticrpcsecur; "staticRpcSecurityCallback: Callers must"...
0x1800246fa  test    edi, edi
0x1800246fc  lea     rdx, aStaticrpcsecur_0; "staticRpcSecurityCallback: Callers have"...
0x180024703  mov     ecx, 8; int
0x180024708  cmovnz  rdx, rax; char *
0x18002470c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180024711  call    cs:__imp_RpcRevertToSelf
0x180024718  nop     dword ptr [rax+rax+00h]
0x18002471d  test    eax, eax
0x18002471f  jz      loc_18002465E
0x180024725  jmp     loc_18002464A
0x18002472a  xor     eax, eax
0x18002472c  jmp     loc_180024663
```
