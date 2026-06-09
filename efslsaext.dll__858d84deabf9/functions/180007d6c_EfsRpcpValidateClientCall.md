# EfsRpcpValidateClientCall

- ea: `0x180007d6c`
- end: `0x180007e55`
- name: `EfsRpcpValidateClientCall`
- size: `233`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE Binding, _DWORD *)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007320`
- `0x180007460`
- `0x180007590`
- `0x180007750`
- `0x180007890`
- `0x1800079c0`
- `0x180007a30`
- `0x180007b10`
- `0x180007c20`

## callees

- `0x180007d6c`
- `0x180008368`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180007e0e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180007e0e`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180007db6`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180007db6`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180007d9e`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x180007d9e`
- `RPCRT4!RpcStringFreeW` at `0x180007e2f`
- `RPCRT4!RpcStringFreeW` at `0x180007e40`
- `RPCRT4!RpcStringFreeW` at `0x180007e2f`
- `RPCRT4!RpcStringFreeW` at `0x180007e40`
- `RPCRT4!RpcStringBindingParseW` at `0x180007de1`
- `RPCRT4!RpcStringBindingParseW` at `0x180007de1`

## pseudocode

```c
__int64 __fastcall EfsRpcpValidateClientCall(RPC_BINDING_HANDLE Binding, _DWORD *a2)
{
  unsigned int IsClientLocal; // ebx
  RPC_WSTR StringBinding[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int ClientLocalFlag; // [rsp+70h] [rbp+30h] BYREF
  RPC_WSTR Protseq; // [rsp+78h] [rbp+38h] BYREF

  ClientLocalFlag = 0;
  Protseq = 0;
  StringBinding[0] = 0;
  IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  if ( !IsClientLocal && !ClientLocalFlag )
  {
    IsClientLocal = RpcBindingToStringBindingW(Binding, StringBinding);
    if ( !IsClientLocal )
    {
      IsClientLocal = RpcStringBindingParseW(StringBinding[0], 0, &Protseq, 0, 0, 0);
      if ( !IsClientLocal
        && CompareStringW(0x7Fu, 1u, Protseq, -1, L"ncacn_np", -1) == 2
        && !(unsigned int)EfsEnforceClientAuthentication() )
      {
        *a2 = 1;
      }
    }
  }
  if ( Protseq )
    RpcStringFreeW(&Protseq);
  if ( StringBinding[0] )
    RpcStringFreeW(StringBinding);
  return IsClientLocal;
}

```

## disassembly

```asm
0x180007d6c  mov     [rsp-18h+arg_0], rbx
0x180007d71  push    rbp
0x180007d72  push    rsi
0x180007d73  push    rdi
0x180007d74  mov     rbp, rsp
0x180007d77  sub     rsp, 40h
0x180007d7b  mov     rsi, rdx
0x180007d7e  mov     [rbp+ClientLocalFlag], 0
0x180007d85  mov     rdi, rcx
0x180007d88  mov     [rbp+Protseq], 0
0x180007d90  lea     rdx, [rbp+ClientLocalFlag]; ClientLocalFlag
0x180007d94  mov     [rbp+StringBinding], 0
0x180007d9c  xor     ecx, ecx; BindingHandle
0x180007d9e  call    cs:__imp_I_RpcBindingIsClientLocal
0x180007da4  mov     ebx, eax
0x180007da6  test    eax, eax
0x180007da8  jnz     short loc_180007E24
0x180007daa  cmp     [rbp+ClientLocalFlag], eax
0x180007dad  jnz     short loc_180007E24
0x180007daf  lea     rdx, [rbp+StringBinding]; StringBinding
0x180007db3  mov     rcx, rdi; Binding
0x180007db6  call    cs:__imp_RpcBindingToStringBindingW
0x180007dbc  mov     ebx, eax
0x180007dbe  test    eax, eax
0x180007dc0  jnz     short loc_180007E24
0x180007dc2  mov     rcx, [rbp+StringBinding]; StringBinding
0x180007dc6  lea     r8, [rbp+Protseq]; Protseq
0x180007dca  mov     [rsp+40h+NetworkOptions], 0; NetworkOptions
0x180007dd3  xor     r9d, r9d; NetworkAddr
0x180007dd6  xor     edx, edx; ObjUuid
0x180007dd8  mov     [rsp+40h+Endpoint], 0; Endpoint
0x180007de1  call    cs:__imp_RpcStringBindingParseW
0x180007de7  mov     ebx, eax
0x180007de9  test    eax, eax
0x180007deb  jnz     short loc_180007E24
0x180007ded  mov     r8, [rbp+Protseq]; lpString1
0x180007df1  lea     rax, ProtSeq; "ncacn_np"
0x180007df8  or      r9d, 0FFFFFFFFh; cchCount1
0x180007dfc  lea     edi, [rbx+1]
0x180007dff  mov     dword ptr [rsp+40h+NetworkOptions], r9d; cchCount2
0x180007e04  lea     ecx, [rbx+7Fh]; Locale
0x180007e07  mov     edx, edi; dwCmpFlags
0x180007e09  mov     [rsp+40h+Endpoint], rax; lpString2
0x180007e0e  call    cs:__imp_CompareStringW
0x180007e14  cmp     eax, 2
0x180007e17  jnz     short loc_180007E24
0x180007e19  call    EfsEnforceClientAuthentication
0x180007e1e  test    eax, eax
0x180007e20  jnz     short loc_180007E24
0x180007e22  mov     [rsi], edi
0x180007e24  cmp     [rbp+Protseq], 0
0x180007e29  jz      short loc_180007E35
0x180007e2b  lea     rcx, [rbp+Protseq]; String
0x180007e2f  call    cs:__imp_RpcStringFreeW
0x180007e35  cmp     [rbp+StringBinding], 0
0x180007e3a  jz      short loc_180007E46
0x180007e3c  lea     rcx, [rbp+StringBinding]; String
0x180007e40  call    cs:__imp_RpcStringFreeW
0x180007e46  mov     eax, ebx
0x180007e48  mov     rbx, [rsp+40h+arg_0]
0x180007e4d  add     rsp, 40h
0x180007e51  pop     rdi
0x180007e52  pop     rsi
0x180007e53  pop     rbp
0x180007e54  retn
```
