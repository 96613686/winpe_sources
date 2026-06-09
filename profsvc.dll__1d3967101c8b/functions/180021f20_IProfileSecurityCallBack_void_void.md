# IProfileSecurityCallBack(void *,void *)

- ea: `0x180021f20`
- end: `0x180022026`
- name: `?IProfileSecurityCallBack@@YAJPEAX0@Z`
- size: `262`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180021f20`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180021fa2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180021fa2`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180021f3c`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180021f3c`
- `RPCRT4!RpcStringBindingParseW` at `0x180021f6f`
- `RPCRT4!RpcStringBindingParseW` at `0x180021f6f`
- `RPCRT4!RpcStringFreeW` at `0x180021fb3`
- `RPCRT4!RpcStringFreeW` at `0x180021fbe`
- `RPCRT4!RpcStringFreeW` at `0x180021fb3`
- `RPCRT4!RpcStringFreeW` at `0x180021fbe`
- `RPCRT4!RpcRaiseException` at `0x180021fff`
- `RPCRT4!RpcRaiseException` at `0x18002201f`
- `RPCRT4!RpcRaiseException` at `0x180021fff`
- `RPCRT4!RpcRaiseException` at `0x18002201f`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x180021ff0`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x180021ff0`

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
0x180021f20  mov     [rsp+arg_8], rsi
0x180021f25  push    rdi
0x180021f26  sub     rsp, 40h
0x180021f2a  mov     rdi, rdx
0x180021f2d  xor     esi, esi
0x180021f2f  mov     rcx, rdi; Binding
0x180021f32  mov     [rsp+48h+StringBinding], rsi
0x180021f37  lea     rdx, [rsp+48h+StringBinding]; StringBinding
0x180021f3c  call    cs:__imp_RpcBindingToStringBindingW
0x180021f42  test    eax, eax
0x180021f44  jnz     loc_18002201A
0x180021f4a  mov     rcx, [rsp+48h+StringBinding]; StringBinding
0x180021f4f  lea     r8, [rsp+48h+Protseq]; Protseq
0x180021f54  mov     [rsp+48h+arg_0], rbx
0x180021f59  xor     r9d, r9d; NetworkAddr
0x180021f5c  mov     [rsp+48h+NetworkOptions], rsi; NetworkOptions
0x180021f61  xor     edx, edx; ObjUuid
0x180021f63  mov     ebx, esi
0x180021f65  mov     [rsp+48h+Endpoint], rsi; Endpoint
0x180021f6a  mov     [rsp+48h+Protseq], rsi
0x180021f6f  call    cs:__imp_RpcStringBindingParseW
0x180021f75  test    eax, eax
0x180021f77  jnz     short loc_180021FB9
0x180021f79  mov     r8, [rsp+48h+Protseq]; lpString1
0x180021f7e  lea     rax, aNcalrpc; "ncalrpc"
0x180021f85  mov     dword ptr [rsp+48h+NetworkOptions], 0FFFFFFFFh; cchCount2
0x180021f8d  mov     r9d, 0FFFFFFFFh; cchCount1
0x180021f93  mov     edx, 1; dwCmpFlags
0x180021f98  mov     [rsp+48h+Endpoint], rax; lpString2
0x180021f9d  mov     ecx, 7Fh; Locale
0x180021fa2  call    cs:__imp_CompareStringW
0x180021fa8  cmp     eax, 2
0x180021fab  lea     rcx, [rsp+48h+Protseq]; String
0x180021fb0  setz    bl
0x180021fb3  call    cs:__imp_RpcStringFreeW
0x180021fb9  lea     rcx, [rsp+48h+StringBinding]; String
0x180021fbe  call    cs:__imp_RpcStringFreeW
0x180021fc4  test    ebx, ebx
0x180021fc6  mov     rbx, [rsp+48h+arg_0]
0x180021fcb  jz      short loc_18002201A
0x180021fcd  mov     [rsp+48h+NetworkOptions], rsi; AuthzSvc
0x180021fd2  lea     r9, [rsp+48h+AuthnLevel]; AuthnLevel
0x180021fd7  xor     r8d, r8d; ServerPrincName
0x180021fda  mov     [rsp+48h+Endpoint], rsi; AuthnSvc
0x180021fdf  lea     rdx, [rsp+48h+Privs]; Privs
0x180021fe4  mov     [rsp+48h+Privs], rsi
0x180021fe9  mov     rcx, rdi; ClientBinding
0x180021fec  mov     [rsp+48h+AuthnLevel], esi
0x180021ff0  call    cs:__imp_RpcBindingInqAuthClientW
0x180021ff6  test    eax, eax
0x180021ff8  jz      short loc_180022006
0x180021ffa  mov     ecx, 5; exception
0x180021fff  call    cs:__imp_RpcRaiseException
0x180022005  int     3; Trap to Debugger
0x180022006  cmp     [rsp+48h+AuthnLevel], 4
0x18002200b  jb      short loc_180021FFA
0x18002200d  mov     rsi, [rsp+48h+arg_8]
0x180022012  xor     eax, eax
0x180022014  add     rsp, 40h
0x180022018  pop     rdi
0x180022019  retn
0x18002201a  mov     ecx, 4D1h; exception
0x18002201f  call    cs:__imp_RpcRaiseException
```
