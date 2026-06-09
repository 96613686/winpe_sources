# IProfileSecurityCallBack(void *,void *)

- ea: `0x180024f10`
- end: `0x180025047`
- name: `?IProfileSecurityCallBack@@YAJPEAX0@Z`
- size: `311`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180024f10`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180024f9e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180024f9e`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180024f2c`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180024f2c`
- `RPCRT4!RpcStringBindingParseW` at `0x180024f65`
- `RPCRT4!RpcStringBindingParseW` at `0x180024f65`
- `RPCRT4!RpcStringFreeW` at `0x180024fb5`
- `RPCRT4!RpcStringFreeW` at `0x180024fc6`
- `RPCRT4!RpcStringFreeW` at `0x180024fb5`
- `RPCRT4!RpcStringFreeW` at `0x180024fc6`
- `RPCRT4!RpcRaiseException` at `0x180025013`
- `RPCRT4!RpcRaiseException` at `0x18002503a`
- `RPCRT4!RpcRaiseException` at `0x180025013`
- `RPCRT4!RpcRaiseException` at `0x18002503a`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x180024ffe`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x180024ffe`

## pseudocode

```c
__int64 __fastcall IProfileSecurityCallBack(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  int v3; // ebx
  RPC_WSTR StringBinding; // [rsp+30h] [rbp-18h] BYREF
  RPC_AUTHZ_HANDLE Privs; // [rsp+38h] [rbp-10h] BYREF
  unsigned int AuthnLevel; // [rsp+60h] [rbp+18h] BYREF
  RPC_WSTR Protseq; // [rsp+68h] [rbp+20h] BYREF

  StringBinding = 0;
  if ( RpcBindingToStringBindingW(Context, &StringBinding) )
    goto LABEL_9;
  v3 = 0;
  Protseq = 0;
  if ( !RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0) )
  {
    LOBYTE(v3) = CompareStringW(0x7Fu, 1u, Protseq, -1, L"ncalrpc", -1) == 2;
    RpcStringFreeW(&Protseq);
  }
  RpcStringFreeW(&StringBinding);
  if ( !v3 )
LABEL_9:
    RpcRaiseException(1233);
  Privs = 0;
  AuthnLevel = 0;
  if ( RpcBindingInqAuthClientW(Context, &Privs, 0, &AuthnLevel, 0, 0) || AuthnLevel < 4 )
    RpcRaiseException(5);
  return 0;
}

```

## disassembly

```asm
0x180024f10  mov     [rsp+arg_8], rsi
0x180024f15  push    rdi
0x180024f16  sub     rsp, 40h
0x180024f1a  mov     rdi, rdx
0x180024f1d  xor     esi, esi
0x180024f1f  mov     rcx, rdi; Binding
0x180024f22  mov     [rsp+48h+StringBinding], rsi
0x180024f27  lea     rdx, [rsp+48h+StringBinding]; StringBinding
0x180024f2c  call    cs:__imp_RpcBindingToStringBindingW
0x180024f33  nop     dword ptr [rax+rax+00h]
0x180024f38  test    eax, eax
0x180024f3a  jnz     loc_180025035
0x180024f40  mov     rcx, [rsp+48h+StringBinding]; StringBinding
0x180024f45  lea     r8, [rsp+48h+Protseq]; Protseq
0x180024f4a  mov     [rsp+48h+arg_0], rbx
0x180024f4f  xor     r9d, r9d; NetworkAddr
0x180024f52  mov     [rsp+48h+NetworkOptions], rsi; NetworkOptions
0x180024f57  xor     edx, edx; ObjUuid
0x180024f59  mov     ebx, esi
0x180024f5b  mov     [rsp+48h+Endpoint], rsi; Endpoint
0x180024f60  mov     [rsp+48h+Protseq], rsi
0x180024f65  call    cs:__imp_RpcStringBindingParseW
0x180024f6c  nop     dword ptr [rax+rax+00h]
0x180024f71  test    eax, eax
0x180024f73  jnz     short loc_180024FC1
0x180024f75  mov     r8, [rsp+48h+Protseq]; lpString1
0x180024f7a  lea     rax, aNcalrpc; "ncalrpc"
0x180024f81  mov     dword ptr [rsp+48h+NetworkOptions], 0FFFFFFFFh; cchCount2
0x180024f89  mov     r9d, 0FFFFFFFFh; cchCount1
0x180024f8f  mov     edx, 1; dwCmpFlags
0x180024f94  mov     [rsp+48h+Endpoint], rax; lpString2
0x180024f99  mov     ecx, 7Fh; Locale
0x180024f9e  call    cs:__imp_CompareStringW
0x180024fa5  nop     dword ptr [rax+rax+00h]
0x180024faa  cmp     eax, 2
0x180024fad  lea     rcx, [rsp+48h+Protseq]; String
0x180024fb2  setz    bl
0x180024fb5  call    cs:__imp_RpcStringFreeW
0x180024fbc  nop     dword ptr [rax+rax+00h]
0x180024fc1  lea     rcx, [rsp+48h+StringBinding]; String
0x180024fc6  call    cs:__imp_RpcStringFreeW
0x180024fcd  nop     dword ptr [rax+rax+00h]
0x180024fd2  test    ebx, ebx
0x180024fd4  mov     rbx, [rsp+48h+arg_0]
0x180024fd9  jz      short loc_180025035
0x180024fdb  mov     [rsp+48h+NetworkOptions], rsi; AuthzSvc
0x180024fe0  lea     r9, [rsp+48h+AuthnLevel]; AuthnLevel
0x180024fe5  xor     r8d, r8d; ServerPrincName
0x180024fe8  mov     [rsp+48h+Endpoint], rsi; AuthnSvc
0x180024fed  lea     rdx, [rsp+48h+Privs]; Privs
0x180024ff2  mov     [rsp+48h+Privs], rsi
0x180024ff7  mov     rcx, rdi; ClientBinding
0x180024ffa  mov     [rsp+48h+AuthnLevel], esi
0x180024ffe  call    cs:__imp_RpcBindingInqAuthClientW
0x180025005  nop     dword ptr [rax+rax+00h]
0x18002500a  test    eax, eax
0x18002500c  jz      short loc_180025020
0x18002500e  mov     ecx, 5; exception
0x180025013  call    cs:__imp_RpcRaiseException
0x18002501a  nop     dword ptr [rax+rax+00h]
0x18002501f  int     3; Trap to Debugger
0x180025020  cmp     [rsp+48h+AuthnLevel], 4
0x180025025  jb      short loc_18002500E
0x180025027  mov     rsi, [rsp+48h+arg_8]
0x18002502c  xor     eax, eax
0x18002502e  add     rsp, 40h
0x180025032  pop     rdi
0x180025033  retn
0x180025035  mov     ecx, 4D1h; exception
0x18002503a  call    cs:__imp_RpcRaiseException
0x180025041  nop     dword ptr [rax+rax+00h]
0x180025046  int     3; Trap to Debugger
```
