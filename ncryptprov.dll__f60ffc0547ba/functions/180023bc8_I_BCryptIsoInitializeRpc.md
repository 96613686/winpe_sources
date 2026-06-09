# I_BCryptIsoInitializeRpc

- ea: `0x180023bc8`
- end: `0x180023dd8`
- name: `I_BCryptIsoInitializeRpc`
- size: `528`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800167fc`
- `0x18003ac40`
- `0x18003f3b0`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x180023bc8`
- `0x180028114`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x180062992`
- `RPCRT4!I_RpcExceptionFilter` at `0x180062992`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180023c65`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180023c65`
- `RPCRT4!RpcStringBindingComposeW` at `0x180023c0b`
- `RPCRT4!RpcStringBindingComposeW` at `0x180023c0b`
- `RPCRT4!RpcStringFreeW` at `0x180023dc7`
- `RPCRT4!RpcStringFreeW` at `0x180023dc7`
- `RPCRT4!RpcBindingFree` at `0x180023d3b`
- `RPCRT4!RpcBindingFree` at `0x180023d3b`
- `RPCRT4!NdrClientCall3` at `0x180023c9f`
- `RPCRT4!NdrClientCall3` at `0x180023c9f`

## string_xrefs

- `0x180023d5b`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisotrustlet.cpp`
- `0x180023d7f`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisotrustlet.cpp`

## pseudocode

```c
__int64 I_BCryptIsoInitializeRpc()
{
  RPC_STATUS v0; // eax
  int v1; // r8d
  unsigned int v2; // edi
  unsigned int v4; // eax
  CLIENT_CALL_RETURN v5; // rax
  int v6; // r8d
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp+8h] BYREF
  RPC_WSTR StringBinding; // [rsp+68h] [rbp+10h] BYREF
  void *v9; // [rsp+70h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v10; // [rsp+78h] [rbp+20h]

  StringBinding = 0;
  Binding = 0;
  v9 = 0;
  v0 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, Endpoint, 0, &StringBinding);
  v2 = v0;
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp",
        v1,
        (unsigned int)"rpcStatus",
        v0,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp",
        25);
  }
  else
  {
    v4 = RpcBindingFromStringBindingW(StringBinding, &Binding);
    v2 = v4;
    if ( v4 )
    {
      DebugTraceError(v4, "rpcStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp", 801);
    }
    else
    {
      v10.Simple = 0;
      v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&BCryptIum_ProxyInfo, 0, 0, Binding, &v9).Pointer;
      v10.Pointer = v5.Pointer;
      if ( SLODWORD(v5.Simple) >= 0 )
      {
        v2 = 0;
        g_hVirtualIsoBinding = Binding;
        g_VirtualIsoClientContext = v9;
        Binding = 0;
        v9 = 0;
      }
      else
      {
        v2 = -2146893767;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp",
            v6,
            (unsigned int)"ntStatus",
            v5.Simple,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisotrustlet.cpp",
            51);
      }
    }
  }
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  return v2;
}

```

## disassembly

```asm
0x180023bc8  mov     r11, rsp
0x180023bcb  push    rdi
0x180023bcc  sub     rsp, 50h
0x180023bd0  mov     qword ptr [r11+10h], 0
0x180023bd8  mov     qword ptr [r11+8], 0
0x180023be0  mov     qword ptr [r11+18h], 0
0x180023be8  lea     rax, [r11+10h]
0x180023bec  mov     [r11-30h], rax
0x180023bf0  mov     qword ptr [r11-38h], 0
0x180023bf8  lea     r9, Endpoint; "LSA_ISO_RPC_SERVER"
0x180023bff  xor     r8d, r8d; NetworkAddr
0x180023c02  lea     rdx, ProtSeq; "ncalrpc"
0x180023c09  xor     ecx, ecx; ObjUuid
0x180023c0b  call    cs:__imp_RpcStringBindingComposeW
0x180023c12  nop     dword ptr [rax+rax+00h]
0x180023c17  mov     edi, eax
0x180023c19  test    eax, eax
0x180023c1b  jz      short loc_180023C5B
0x180023c1d  lea     rdx, WPP_GLOBAL_Control
0x180023c24  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c2b  cmp     rcx, rdx
0x180023c2e  jz      short loc_180023C3A
0x180023c30  test    byte ptr [rcx+1Ch], 1
0x180023c34  jnz     loc_180023D4C
0x180023c3a  cmp     [rsp+58h+Binding], 0
0x180023c40  jnz     loc_180023D36
0x180023c46  cmp     [rsp+58h+StringBinding], 0
0x180023c4c  jnz     loc_180023DC2
0x180023c52  mov     eax, edi
0x180023c54  add     rsp, 50h
0x180023c58  pop     rdi
0x180023c59  retn
0x180023c5b  lea     rdx, [rsp+58h+Binding]; Binding
0x180023c60  mov     rcx, [rsp+58h+StringBinding]; StringBinding
0x180023c65  call    cs:__imp_RpcBindingFromStringBindingW
0x180023c6c  nop     dword ptr [rax+rax+00h]
0x180023c71  mov     edi, eax
0x180023c73  test    eax, eax
0x180023c75  jnz     loc_180023D79
0x180023c7b  mov     [rsp+58h+arg_18], 0
0x180023c84  lea     rax, [rsp+58h+arg_10]
0x180023c89  mov     [rsp+58h+var_38], rax
0x180023c8e  mov     r9, [rsp+58h+Binding]
0x180023c93  xor     r8d, r8d; pReturnValue
0x180023c96  xor     edx, edx; nProcNum
0x180023c98  lea     rcx, ?BCryptIum_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180023c9f  call    cs:__imp_NdrClientCall3
0x180023ca6  nop     dword ptr [rax+rax+00h]
0x180023cab  mov     [rsp+58h+arg_18], rax
0x180023cb0  mov     [rsp+58h+var_18], eax
0x180023cb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180023cbb  jmp     short loc_180023CFE
0x180023cbd  lea     rdx, WPP_GLOBAL_Control
0x180023cc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ccb  cmp     rcx, rdx
0x180023cce  jz      short loc_180023CF5
0x180023cd0  test    byte ptr [rcx+1Ch], 1
0x180023cd4  jz      short loc_180023CF5
0x180023cd6  mov     r9d, eax
0x180023cd9  mov     edx, 10h
0x180023cde  lea     r8, WPP_a6b47fe3e7aa3dc67b817b99b29667f9_Traceguids
0x180023ce5  mov     rcx, [rcx+10h]
0x180023ce9  call    WPP_SF_D
0x180023cee  mov     rcx, cs:WPP_GLOBAL_Control
0x180023cf5  mov     eax, 0C0000001h
0x180023cfa  mov     [rsp+58h+var_18], eax
0x180023cfe  test    eax, eax
0x180023d00  jns     loc_180023D99
0x180023d06  mov     edi, 80090039h
0x180023d0b  lea     rdx, WPP_GLOBAL_Control
0x180023d12  cmp     rcx, rdx
0x180023d15  jz      loc_180023C3A
0x180023d1b  test    byte ptr [rcx+1Ch], 1
0x180023d1f  jz      loc_180023C3A
0x180023d25  mov     [rsp+58h+var_28], 333h
0x180023d2d  lea     r9, aNtstatus; "ntStatus"
0x180023d34  jmp     short loc_180023D5B
0x180023d36  lea     rcx, [rsp+58h+Binding]; Binding
0x180023d3b  call    cs:__imp_RpcBindingFree
0x180023d42  nop     dword ptr [rax+rax+00h]
0x180023d47  jmp     loc_180023C46
0x180023d4c  mov     [rsp+58h+var_28], 319h
0x180023d54  lea     r9, aRpcstatus; "rpcStatus"
0x180023d5b  lea     rdx, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023d62  mov     [rsp+58h+var_30], rdx
0x180023d67  mov     dword ptr [rsp+58h+var_38], eax
0x180023d6b  mov     rcx, [rcx+10h]
0x180023d6f  call    WPP_SF_sDsd
0x180023d74  jmp     loc_180023C3A
0x180023d79  mov     r9d, 321h
0x180023d7f  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180023d86  lea     rdx, aRpcstatus; "rpcStatus"
0x180023d8d  mov     ecx, eax
0x180023d8f  call    DebugTraceError
0x180023d94  jmp     loc_180023C3A
0x180023d99  xor     edi, edi
0x180023d9b  mov     rax, [rsp+58h+Binding]
0x180023da0  mov     cs:?g_hVirtualIsoBinding@@3PEAXEA, rax; void * g_hVirtualIsoBinding
0x180023da7  mov     rax, [rsp+58h+arg_10]
0x180023dac  mov     cs:?g_VirtualIsoClientContext@@3PEAXEA, rax; void * g_VirtualIsoClientContext
0x180023db3  mov     [rsp+58h+Binding], rdi
0x180023db8  mov     [rsp+58h+arg_10], rdi
0x180023dbd  jmp     loc_180023C3A
0x180023dc2  lea     rcx, [rsp+58h+StringBinding]; String
0x180023dc7  call    cs:__imp_RpcStringFreeW
0x180023dce  nop     dword ptr [rax+rax+00h]
0x180023dd3  jmp     loc_180023C52
0x180062984  push    rbp
0x180062986  sub     rsp, 40h
0x18006298a  mov     rbp, rdx
0x18006298d  mov     rcx, [rcx]
0x180062990  mov     ecx, [rcx]; ExceptionCode
0x180062992  call    cs:__imp_I_RpcExceptionFilter
0x180062999  nop     dword ptr [rax+rax+00h]
0x18006299e  nop
0x18006299f  add     rsp, 40h
0x1800629a3  pop     rbp
0x1800629a4  retn
```
