# LsaDeleteMachineCertificate

- ea: `0x18008a354`
- end: `0x18008a455`
- name: `LsaDeleteMachineCertificate`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180070d64`

## callees

- `0x18008a354`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x18008a421`
- `RPCRT4!I_RpcMapWin32Status` at `0x18008a421`
- `RPCRT4!RpcStringFreeW` at `0x18008a3d2`
- `RPCRT4!RpcStringFreeW` at `0x18008a3d2`
- `RPCRT4!RpcBindingFree` at `0x18008a440`
- `RPCRT4!RpcBindingFree` at `0x180090449`
- `RPCRT4!RpcBindingFree` at `0x18008a440`
- `RPCRT4!RpcBindingFree` at `0x180090449`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18008a3bf`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18008a3bf`
- `RPCRT4!NdrClientCall3` at `0x18008a405`
- `RPCRT4!NdrClientCall3` at `0x18008a405`
- `RPCRT4!RpcStringBindingComposeW` at `0x18008a38f`
- `RPCRT4!RpcStringBindingComposeW` at `0x18008a38f`
- `RPCRT4!I_RpcExceptionFilter` at `0x180090428`
- `RPCRT4!I_RpcExceptionFilter` at `0x180090428`

## pseudocode

```c
__int64 LsaDeleteMachineCertificate()
{
  RPC_STATUS v0; // eax
  RPC_STATUS Pointer; // ebx
  CLIENT_CALL_RETURN v2; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+50h] [rbp+8h] BYREF
  RPC_WSTR StringBinding; // [rsp+58h] [rbp+10h] BYREF
  CLIENT_CALL_RETURN v6; // [rsp+60h] [rbp+18h]

  Binding = 0;
  StringBinding = 0;
  v0 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"LSA_IUM_MK_ENDPOINT", 0, &StringBinding);
  Pointer = v0;
  if ( v0 )
  {
    if ( v0 > 0 )
    {
      Pointer = (unsigned __int16)v0;
LABEL_4:
      Pointer |= 0xC0070000;
    }
  }
  else
  {
    Pointer = RpcBindingFromStringBindingW(StringBinding, &Binding);
    RpcStringFreeW(&StringBinding);
    if ( !Pointer )
    {
      v6.Simple = 0;
      v2.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, Binding).Pointer;
      Pointer = (RPC_STATUS)v2.Pointer;
      v6.Pointer = v2.Pointer;
      RpcBindingFree(&Binding);
      return (unsigned int)Pointer;
    }
    if ( Pointer > 0 )
    {
      Pointer = (unsigned __int16)Pointer;
      goto LABEL_4;
    }
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18008a354  mov     r11, rsp
0x18008a357  push    rbx
0x18008a358  sub     rsp, 40h
0x18008a35c  mov     qword ptr [r11+8], 0
0x18008a364  mov     qword ptr [r11+10h], 0
0x18008a36c  lea     rax, [r11+10h]
0x18008a370  mov     [r11-20h], rax
0x18008a374  mov     qword ptr [r11-28h], 0
0x18008a37c  lea     r9, aLsaIumMkEndpoi; "LSA_IUM_MK_ENDPOINT"
0x18008a383  xor     r8d, r8d; NetworkAddr
0x18008a386  lea     rdx, ProtSeq; "ncalrpc"
0x18008a38d  xor     ecx, ecx; ObjUuid
0x18008a38f  call    cs:__imp_RpcStringBindingComposeW
0x18008a396  nop     dword ptr [rax+rax+00h]
0x18008a39b  mov     ebx, eax
0x18008a39d  test    eax, eax
0x18008a39f  jz      short loc_18008A3B5
0x18008a3a1  jle     loc_18008A44C
0x18008a3a7  movzx   ebx, ax
0x18008a3aa  or      ebx, 0C0070000h
0x18008a3b0  jmp     loc_18008A44C
0x18008a3b5  lea     rdx, [rsp+48h+Binding]; Binding
0x18008a3ba  mov     rcx, [rsp+48h+StringBinding]; StringBinding
0x18008a3bf  call    cs:__imp_RpcBindingFromStringBindingW
0x18008a3c6  nop     dword ptr [rax+rax+00h]
0x18008a3cb  mov     ebx, eax
0x18008a3cd  lea     rcx, [rsp+48h+StringBinding]; String
0x18008a3d2  call    cs:__imp_RpcStringFreeW
0x18008a3d9  nop     dword ptr [rax+rax+00h]
0x18008a3de  test    ebx, ebx
0x18008a3e0  jz      short loc_18008A3E9
0x18008a3e2  jle     short loc_18008A44C
0x18008a3e4  movzx   ebx, bx
0x18008a3e7  jmp     short loc_18008A3AA
0x18008a3e9  mov     [rsp+48h+arg_10], 0
0x18008a3f2  mov     r9, [rsp+48h+Binding]
0x18008a3f7  xor     r8d, r8d; pReturnValue
0x18008a3fa  lea     edx, [r8+1]; nProcNum
0x18008a3fe  lea     rcx, pProxyInfo; pProxyInfo
0x18008a405  call    cs:__imp_NdrClientCall3
0x18008a40c  nop     dword ptr [rax+rax+00h]
0x18008a411  mov     rbx, rax
0x18008a414  mov     [rsp+48h+arg_10], rax
0x18008a419  mov     [rsp+48h+var_18], eax
0x18008a41d  jmp     short loc_18008A43B
0x18008a41f  mov     ecx, eax; Status
0x18008a421  call    cs:__imp_I_RpcMapWin32Status
0x18008a428  nop     dword ptr [rax+rax+00h]
0x18008a42d  mov     ebx, 0C0000001h
0x18008a432  test    eax, eax
0x18008a434  cmovs   ebx, eax
0x18008a437  mov     [rsp+48h+var_18], ebx
0x18008a43b  lea     rcx, [rsp+48h+Binding]; Binding
0x18008a440  call    cs:__imp_RpcBindingFree
0x18008a447  nop     dword ptr [rax+rax+00h]
0x18008a44c  mov     eax, ebx
0x18008a44e  add     rsp, 40h
0x18008a452  pop     rbx
0x18008a453  retn
0x18009041a  push    rbp
0x18009041c  sub     rsp, 30h
0x180090420  mov     rbp, rdx
0x180090423  mov     rcx, [rcx]
0x180090426  mov     ecx, [rcx]; ExceptionCode
0x180090428  call    cs:__imp_I_RpcExceptionFilter
0x18009042f  nop     dword ptr [rax+rax+00h]
0x180090434  nop
0x180090435  add     rsp, 30h
0x180090439  pop     rbp
0x18009043a  retn
0x18009043c  push    rbp
0x18009043e  sub     rsp, 30h
0x180090442  mov     rbp, rdx
0x180090445  lea     rcx, [rbp+50h]; Binding
0x180090449  call    cs:__imp_RpcBindingFree
0x180090450  nop     dword ptr [rax+rax+00h]
0x180090455  nop
0x180090456  add     rsp, 30h
0x18009045a  pop     rbp
0x18009045b  retn
```
