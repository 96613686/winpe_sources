# LsaDeleteMachineCertificate

- ea: `0x1800842b4`
- end: `0x18008438d`
- name: `LsaDeleteMachineCertificate`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18006bc60`

## callees

- `0x1800842b4`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x180084366`
- `RPCRT4!I_RpcMapWin32Status` at `0x180084366`
- `RPCRT4!RpcStringFreeW` at `0x180084323`
- `RPCRT4!RpcStringFreeW` at `0x180084323`
- `RPCRT4!RpcBindingFree` at `0x18008437f`
- `RPCRT4!RpcBindingFree` at `0x180089cd7`
- `RPCRT4!RpcBindingFree` at `0x18008437f`
- `RPCRT4!RpcBindingFree` at `0x180089cd7`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180084316`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180084316`
- `RPCRT4!NdrClientCall3` at `0x180084350`
- `RPCRT4!NdrClientCall3` at `0x180084350`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800842ef`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800842ef`
- `RPCRT4!I_RpcExceptionFilter` at `0x180089cbc`
- `RPCRT4!I_RpcExceptionFilter` at `0x180089cbc`

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
0x1800842b4  mov     r11, rsp
0x1800842b7  push    rbx
0x1800842b8  sub     rsp, 40h
0x1800842bc  mov     qword ptr [r11+8], 0
0x1800842c4  mov     qword ptr [r11+10h], 0
0x1800842cc  lea     rax, [r11+10h]
0x1800842d0  mov     [r11-20h], rax
0x1800842d4  mov     qword ptr [r11-28h], 0
0x1800842dc  lea     r9, aLsaIumMkEndpoi; "LSA_IUM_MK_ENDPOINT"
0x1800842e3  xor     r8d, r8d; NetworkAddr
0x1800842e6  lea     rdx, ProtSeq; "ncalrpc"
0x1800842ed  xor     ecx, ecx; ObjUuid
0x1800842ef  call    cs:__imp_RpcStringBindingComposeW
0x1800842f5  mov     ebx, eax
0x1800842f7  test    eax, eax
0x1800842f9  jz      short loc_18008430C
0x1800842fb  jle     loc_180084385
0x180084301  movzx   ebx, ax
0x180084304  or      ebx, 0C0070000h
0x18008430a  jmp     short loc_180084385
0x18008430c  lea     rdx, [rsp+48h+Binding]; Binding
0x180084311  mov     rcx, [rsp+48h+StringBinding]; StringBinding
0x180084316  call    cs:__imp_RpcBindingFromStringBindingW
0x18008431c  mov     ebx, eax
0x18008431e  lea     rcx, [rsp+48h+StringBinding]; String
0x180084323  call    cs:__imp_RpcStringFreeW
0x180084329  test    ebx, ebx
0x18008432b  jz      short loc_180084334
0x18008432d  jle     short loc_180084385
0x18008432f  movzx   ebx, bx
0x180084332  jmp     short loc_180084304
0x180084334  mov     [rsp+48h+arg_10], 0
0x18008433d  mov     r9, [rsp+48h+Binding]
0x180084342  xor     r8d, r8d; pReturnValue
0x180084345  lea     edx, [r8+1]; nProcNum
0x180084349  lea     rcx, pProxyInfo; pProxyInfo
0x180084350  call    cs:__imp_NdrClientCall3
0x180084356  mov     rbx, rax
0x180084359  mov     [rsp+48h+arg_10], rax
0x18008435e  mov     [rsp+48h+var_18], eax
0x180084362  jmp     short loc_18008437A
0x180084364  mov     ecx, eax; Status
0x180084366  call    cs:__imp_I_RpcMapWin32Status
0x18008436c  mov     ebx, 0C0000001h
0x180084371  test    eax, eax
0x180084373  cmovs   ebx, eax
0x180084376  mov     [rsp+48h+var_18], ebx
0x18008437a  lea     rcx, [rsp+48h+Binding]; Binding
0x18008437f  call    cs:__imp_RpcBindingFree
0x180084385  mov     eax, ebx
0x180084387  add     rsp, 40h
0x18008438b  pop     rbx
0x18008438c  retn
0x180089cae  push    rbp
0x180089cb0  sub     rsp, 30h
0x180089cb4  mov     rbp, rdx
0x180089cb7  mov     rcx, [rcx]
0x180089cba  mov     ecx, [rcx]; ExceptionCode
0x180089cbc  call    cs:__imp_I_RpcExceptionFilter
0x180089cc2  nop
0x180089cc3  add     rsp, 30h
0x180089cc7  pop     rbp
0x180089cc8  retn
0x180089cca  push    rbp
0x180089ccc  sub     rsp, 30h
0x180089cd0  mov     rbp, rdx
0x180089cd3  lea     rcx, [rbp+50h]; Binding
0x180089cd7  call    cs:__imp_RpcBindingFree
0x180089cdd  nop
0x180089cde  add     rsp, 30h
0x180089ce2  pop     rbp
0x180089ce3  retn
```
