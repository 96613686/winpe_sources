# BdeSvcApipInitRpc(void * *)

- ea: `0x180013dd0`
- end: `0x180013f58`
- name: `?BdeSvcApipInitRpc@@YAJPEAPEAX@Z`
- size: `392`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013be4`

## callees

- `0x180001bb0`
- `0x180013dd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180013ea3`
- `KERNEL32!GetLastError` at `0x180013ea3`
- `ADVAPI32!FreeSid` at `0x180013f24`
- `ADVAPI32!FreeSid` at `0x180013f24`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180013e99`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180013e99`
- `RPCRT4!RpcBindingFree` at `0x180013f38`
- `RPCRT4!RpcBindingFree` at `0x180013f38`
- `RPCRT4!RpcStringBindingComposeW` at `0x180013e37`
- `RPCRT4!RpcStringBindingComposeW` at `0x180013e37`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180013eea`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180013eea`
- `RPCRT4!RpcStringFreeW` at `0x180013f11`
- `RPCRT4!RpcStringFreeW` at `0x180013f11`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180013e5f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180013e5f`

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
0x180013dd0  push    rbp
0x180013dd2  push    rbx
0x180013dd3  push    rsi
0x180013dd4  push    rdi
0x180013dd5  lea     rbp, [rsp-3Fh]
0x180013dda  sub     rsp, 0B8h
0x180013de1  mov     rax, cs:__security_cookie
0x180013de8  xor     rax, rsp
0x180013deb  mov     [rbp+57h+var_28], rax
0x180013def  xor     esi, esi
0x180013df1  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180013df7  xor     eax, eax
0x180013df9  mov     [rbp+57h+Binding], rsi
0x180013dfd  xorps   xmm0, xmm0
0x180013e00  mov     [rbp+57h+var_38], rax
0x180013e04  lea     rax, [rbp+57h+String]
0x180013e08  mov     [rbp+57h+String], rsi
0x180013e0c  mov     rdi, rcx
0x180013e0f  mov     [rsp+0D0h+StringBinding], rax; StringBinding
0x180013e14  xor     r9d, r9d; Endpoint
0x180013e17  mov     [rsp+0D0h+Options], rsi; Options
0x180013e1c  xor     r8d, r8d; NetworkAddr
0x180013e1f  mov     [rbp+57h+var_60], rsi
0x180013e23  lea     rdx, ProtSeq; "ncalrpc"
0x180013e2a  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x180013e2d  xor     ecx, ecx; ObjUuid
0x180013e2f  movups  xmmword ptr [rbp+57h+SecurityQOS.Version], xmm0
0x180013e33  movups  [rbp+57h+var_48], xmm0
0x180013e37  call    cs:__imp_RpcStringBindingComposeW
0x180013e3d  mov     ebx, eax
0x180013e3f  test    eax, eax
0x180013e41  jz      short loc_180013E57
0x180013e43  jle     loc_180013F07
0x180013e49  movzx   ebx, ax
0x180013e4c  or      ebx, 80070000h
0x180013e52  jmp     loc_180013F07
0x180013e57  mov     rcx, [rbp+57h+String]; StringBinding
0x180013e5b  lea     rdx, [rbp+57h+Binding]; Binding
0x180013e5f  call    cs:__imp_RpcBindingFromStringBindingW
0x180013e65  mov     ebx, eax
0x180013e67  test    eax, eax
0x180013e69  jnz     short loc_180013E43
0x180013e6b  lea     rax, [rbp+57h+var_60]
0x180013e6f  xor     r9d, r9d; nSubAuthority1
0x180013e72  mov     [rsp+0D0h+pSid], rax; pSid
0x180013e77  lea     r8d, [rbx+12h]; nSubAuthority0
0x180013e7b  mov     [rsp+0D0h+nSubAuthority7], esi; nSubAuthority7
0x180013e7f  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180013e83  mov     [rsp+0D0h+nSubAuthority6], esi; nSubAuthority6
0x180013e87  mov     dl, 1; nSubAuthorityCount
0x180013e89  mov     [rsp+0D0h+nSubAuthority5], esi; nSubAuthority5
0x180013e8d  mov     [rsp+0D0h+nSubAuthority4], esi; nSubAuthority4
0x180013e91  mov     dword ptr [rsp+0D0h+StringBinding], esi; nSubAuthority3
0x180013e95  mov     dword ptr [rsp+0D0h+Options], esi; nSubAuthority2
0x180013e99  call    cs:__imp_AllocateAndInitializeSid
0x180013e9f  test    eax, eax
0x180013ea1  jnz     short loc_180013EAF
0x180013ea3  call    cs:__imp_GetLastError
0x180013ea9  mov     ebx, eax
0x180013eab  test    eax, eax
0x180013ead  jmp     short loc_180013E43
0x180013eaf  mov     rcx, [rbp+57h+Binding]; Binding
0x180013eb3  mov     eax, 3
0x180013eb8  mov     [rbp+57h+SecurityQOS.Version], eax
0x180013ebb  xor     edx, edx; ServerPrincName
0x180013ebd  mov     [rbp+57h+SecurityQOS.ImpersonationType], eax
0x180013ec0  mov     rax, [rbp+57h+var_60]
0x180013ec4  mov     [rbp+57h+var_38], rax
0x180013ec8  lea     rax, [rbp+57h+SecurityQOS]
0x180013ecc  mov     qword ptr [rsp+0D0h+nSubAuthority4], rax; SecurityQOS
0x180013ed1  lea     r9d, [rdx+0Ah]; AuthnSvc
0x180013ed5  mov     dword ptr [rsp+0D0h+StringBinding], esi; AuthzSvc
0x180013ed9  lea     r8d, [rdx+6]; AuthnLevel
0x180013edd  mov     [rsp+0D0h+Options], rsi; AuthIdentity
0x180013ee2  mov     qword ptr [rbp+57h+SecurityQOS.Capabilities], 1
0x180013eea  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180013ef0  mov     ebx, eax
0x180013ef2  test    eax, eax
0x180013ef4  jnz     loc_180013E43
0x180013efa  mov     rax, [rbp+57h+Binding]
0x180013efe  mov     ebx, esi
0x180013f00  mov     [rdi], rax
0x180013f03  mov     [rbp+57h+Binding], rsi
0x180013f07  cmp     [rbp+57h+String], rsi
0x180013f0b  jz      short loc_180013F1B
0x180013f0d  lea     rcx, [rbp+57h+String]; String
0x180013f11  call    cs:__imp_RpcStringFreeW
0x180013f17  mov     [rbp+57h+String], rsi
0x180013f1b  mov     rcx, [rbp+57h+var_60]; pSid
0x180013f1f  test    rcx, rcx
0x180013f22  jz      short loc_180013F2E
0x180013f24  call    cs:__imp_FreeSid
0x180013f2a  mov     [rbp+57h+var_60], rsi
0x180013f2e  cmp     [rbp+57h+Binding], rsi
0x180013f32  jz      short loc_180013F3E
0x180013f34  lea     rcx, [rbp+57h+Binding]; Binding
0x180013f38  call    cs:__imp_RpcBindingFree
0x180013f3e  mov     eax, ebx
0x180013f40  mov     rcx, [rbp+57h+var_28]
0x180013f44  xor     rcx, rsp; StackCookie
0x180013f47  call    __security_check_cookie
0x180013f4c  add     rsp, 0B8h
0x180013f53  pop     rdi
0x180013f54  pop     rsi
0x180013f55  pop     rbx
0x180013f56  pop     rbp
0x180013f57  retn
```
