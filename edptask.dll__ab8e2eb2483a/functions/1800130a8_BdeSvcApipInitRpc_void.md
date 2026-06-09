# BdeSvcApipInitRpc(void * *)

- ea: `0x1800130a8`
- end: `0x180013230`
- name: `?BdeSvcApipInitRpc@@YAJPEAPEAX@Z`
- size: `392`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012e30`
- `0x180012eb4`

## callees

- `0x1800130a8`
- `0x180013410`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001317b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001317b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180013171`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180013171`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800131fc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800131fc`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180013137`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180013137`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800131c2`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800131c2`
- `RPCRT4!RpcStringFreeW` at `0x1800131e9`
- `RPCRT4!RpcStringFreeW` at `0x1800131e9`
- `RPCRT4!RpcBindingFree` at `0x180013210`
- `RPCRT4!RpcBindingFree` at `0x180013210`
- `RPCRT4!RpcStringBindingComposeW` at `0x18001310f`
- `RPCRT4!RpcStringBindingComposeW` at `0x18001310f`

## pseudocode

```c
__int64 __fastcall BdeSvcApipInitRpc(void **a1)
{
  signed int LastError; // eax
  unsigned int v3; // ebx
  bool v4; // cc
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp-19h] BYREF
  RPC_WSTR String; // [rsp+68h] [rbp-11h] BYREF
  PSID pSid; // [rsp+70h] [rbp-9h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+78h] [rbp-1h] BYREF
  __int128 v10; // [rsp+88h] [rbp+Fh]
  PSID v11; // [rsp+98h] [rbp+1Fh]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  Binding = 0;
  v11 = 0;
  String = 0;
  pSid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SecurityQOS = 0;
  v10 = 0;
  LastError = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &String);
  v3 = LastError;
  v4 = LastError <= 0;
  if ( !LastError )
  {
    LastError = RpcBindingFromStringBindingW(String, &Binding);
    v3 = LastError;
    v4 = LastError <= 0;
    if ( !LastError )
    {
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
      {
        SecurityQOS.Version = 3;
        SecurityQOS.ImpersonationType = 3;
        v11 = pSid;
        *(_QWORD *)&SecurityQOS.Capabilities = 1;
        LastError = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 0, &SecurityQOS);
        v3 = LastError;
        v4 = LastError <= 0;
        if ( !LastError )
        {
          v3 = 0;
          *a1 = Binding;
          Binding = 0;
          goto LABEL_9;
        }
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        v4 = LastError <= 0;
      }
    }
  }
  if ( !v4 )
    v3 = (unsigned __int16)LastError | 0x80070000;
LABEL_9:
  if ( String )
  {
    RpcStringFreeW(&String);
    String = 0;
  }
  if ( pSid )
  {
    FreeSid(pSid);
    pSid = 0;
  }
  if ( Binding )
    RpcBindingFree(&Binding);
  return v3;
}

```

## disassembly

```asm
0x1800130a8  push    rbp
0x1800130aa  push    rbx
0x1800130ab  push    rsi
0x1800130ac  push    rdi
0x1800130ad  lea     rbp, [rsp-3Fh]
0x1800130b2  sub     rsp, 0B8h
0x1800130b9  mov     rax, cs:__security_cookie
0x1800130c0  xor     rax, rsp
0x1800130c3  mov     [rbp+57h+var_28], rax
0x1800130c7  xor     esi, esi
0x1800130c9  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800130cf  xor     eax, eax
0x1800130d1  mov     [rbp+57h+Binding], rsi
0x1800130d5  xorps   xmm0, xmm0
0x1800130d8  mov     [rbp+57h+var_38], rax
0x1800130dc  lea     rax, [rbp+57h+String]
0x1800130e0  mov     [rbp+57h+String], rsi
0x1800130e4  mov     rdi, rcx
0x1800130e7  mov     [rsp+0D0h+StringBinding], rax; StringBinding
0x1800130ec  xor     r9d, r9d; Endpoint
0x1800130ef  mov     [rsp+0D0h+Options], rsi; Options
0x1800130f4  xor     r8d, r8d; NetworkAddr
0x1800130f7  mov     [rbp+57h+var_60], rsi
0x1800130fb  lea     rdx, ProtSeq; "ncalrpc"
0x180013102  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x180013105  xor     ecx, ecx; ObjUuid
0x180013107  movups  xmmword ptr [rbp+57h+SecurityQOS.Version], xmm0
0x18001310b  movups  [rbp+57h+var_48], xmm0
0x18001310f  call    cs:__imp_RpcStringBindingComposeW
0x180013115  mov     ebx, eax
0x180013117  test    eax, eax
0x180013119  jz      short loc_18001312F
0x18001311b  jle     loc_1800131DF
0x180013121  movzx   ebx, ax
0x180013124  or      ebx, 80070000h
0x18001312a  jmp     loc_1800131DF
0x18001312f  mov     rcx, [rbp+57h+String]; StringBinding
0x180013133  lea     rdx, [rbp+57h+Binding]; Binding
0x180013137  call    cs:__imp_RpcBindingFromStringBindingW
0x18001313d  mov     ebx, eax
0x18001313f  test    eax, eax
0x180013141  jnz     short loc_18001311B
0x180013143  lea     rax, [rbp+57h+var_60]
0x180013147  xor     r9d, r9d; nSubAuthority1
0x18001314a  mov     [rsp+0D0h+pSid], rax; pSid
0x18001314f  lea     r8d, [rbx+12h]; nSubAuthority0
0x180013153  mov     [rsp+0D0h+nSubAuthority7], esi; nSubAuthority7
0x180013157  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18001315b  mov     [rsp+0D0h+nSubAuthority6], esi; nSubAuthority6
0x18001315f  mov     dl, 1; nSubAuthorityCount
0x180013161  mov     [rsp+0D0h+nSubAuthority5], esi; nSubAuthority5
0x180013165  mov     [rsp+0D0h+nSubAuthority4], esi; nSubAuthority4
0x180013169  mov     dword ptr [rsp+0D0h+StringBinding], esi; nSubAuthority3
0x18001316d  mov     dword ptr [rsp+0D0h+Options], esi; nSubAuthority2
0x180013171  call    cs:__imp_AllocateAndInitializeSid
0x180013177  test    eax, eax
0x180013179  jnz     short loc_180013187
0x18001317b  call    cs:__imp_GetLastError
0x180013181  mov     ebx, eax
0x180013183  test    eax, eax
0x180013185  jmp     short loc_18001311B
0x180013187  mov     rcx, [rbp+57h+Binding]; Binding
0x18001318b  mov     eax, 3
0x180013190  mov     [rbp+57h+SecurityQOS.Version], eax
0x180013193  xor     edx, edx; ServerPrincName
0x180013195  mov     [rbp+57h+SecurityQOS.ImpersonationType], eax
0x180013198  mov     rax, [rbp+57h+var_60]
0x18001319c  mov     [rbp+57h+var_38], rax
0x1800131a0  lea     rax, [rbp+57h+SecurityQOS]
0x1800131a4  mov     qword ptr [rsp+0D0h+nSubAuthority4], rax; SecurityQOS
0x1800131a9  lea     r9d, [rdx+0Ah]; AuthnSvc
0x1800131ad  mov     dword ptr [rsp+0D0h+StringBinding], esi; AuthzSvc
0x1800131b1  lea     r8d, [rdx+6]; AuthnLevel
0x1800131b5  mov     [rsp+0D0h+Options], rsi; AuthIdentity
0x1800131ba  mov     qword ptr [rbp+57h+SecurityQOS.Capabilities], 1
0x1800131c2  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800131c8  mov     ebx, eax
0x1800131ca  test    eax, eax
0x1800131cc  jnz     loc_18001311B
0x1800131d2  mov     rax, [rbp+57h+Binding]
0x1800131d6  mov     ebx, esi
0x1800131d8  mov     [rdi], rax
0x1800131db  mov     [rbp+57h+Binding], rsi
0x1800131df  cmp     [rbp+57h+String], rsi
0x1800131e3  jz      short loc_1800131F3
0x1800131e5  lea     rcx, [rbp+57h+String]; String
0x1800131e9  call    cs:__imp_RpcStringFreeW
0x1800131ef  mov     [rbp+57h+String], rsi
0x1800131f3  mov     rcx, [rbp+57h+var_60]; pSid
0x1800131f7  test    rcx, rcx
0x1800131fa  jz      short loc_180013206
0x1800131fc  call    cs:__imp_FreeSid
0x180013202  mov     [rbp+57h+var_60], rsi
0x180013206  cmp     [rbp+57h+Binding], rsi
0x18001320a  jz      short loc_180013216
0x18001320c  lea     rcx, [rbp+57h+Binding]; Binding
0x180013210  call    cs:__imp_RpcBindingFree
0x180013216  mov     eax, ebx
0x180013218  mov     rcx, [rbp+57h+var_28]
0x18001321c  xor     rcx, rsp; StackCookie
0x18001321f  call    __security_check_cookie
0x180013224  add     rsp, 0B8h
0x18001322b  pop     rdi
0x18001322c  pop     rsi
0x18001322d  pop     rbx
0x18001322e  pop     rbp
0x18001322f  retn
```
