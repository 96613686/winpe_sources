# CertBindA

- ea: `0x180056fb0`
- end: `0x18005714a`
- name: `CertBindA`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180056de0`

## callees

- `0x180056fb0`
- `0x180057150`
- `0x1800bec20`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180057094`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180057094`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180057106`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180057106`
- `RPCRT4!RpcStringBindingComposeA` at `0x180057020`
- `RPCRT4!RpcStringBindingComposeA` at `0x180057020`
- `RPCRT4!RpcBindingFromStringBindingA` at `0x180057038`
- `RPCRT4!RpcBindingFromStringBindingA` at `0x180057038`
- `RPCRT4!RpcBindingFree` at `0x180057137`
- `RPCRT4!RpcBindingFree` at `0x180057137`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800570e1`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800570e1`
- `RPCRT4!RpcEpResolveBinding` at `0x180057053`
- `RPCRT4!RpcEpResolveBinding` at `0x180057053`
- `RPCRT4!RpcStringFreeA` at `0x1800570f7`
- `RPCRT4!RpcStringFreeA` at `0x1800570f7`

## pseudocode

```c
__int64 __fastcall CertBindA(__int64 a1, RPC_BINDING_HANDLE *a2)
{
  unsigned int v3; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp-19h] BYREF
  RPC_CSTR String; // [rsp+68h] [rbp-11h] BYREF
  PSID pSid; // [rsp+70h] [rbp-9h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+78h] [rbp-1h] BYREF
  __int128 v9; // [rsp+88h] [rbp+Fh]
  PSID v10; // [rsp+98h] [rbp+1Fh]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  String = 0;
  Binding = 0;
  SecurityQOS = 0;
  v10 = 0;
  v9 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid = 0;
  WaitForCryptService();
  v3 = RpcStringBindingComposeA(0, (RPC_CSTR)"ncalrpc", 0, (RPC_CSTR)"keysvc", 0, &String);
  if ( !v3 )
  {
    v3 = RpcBindingFromStringBindingA(String, &Binding);
    if ( !v3 )
    {
      v3 = RpcEpResolveBinding(Binding, qword_180123300);
      if ( !v3 )
      {
        if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
        {
          SecurityQOS.Version = 3;
          SecurityQOS.ImpersonationType = 3;
          v10 = pSid;
          v9 = 0u;
          SecurityQOS.Capabilities = 1;
          SecurityQOS.IdentityTracking = 1;
          v3 = RpcBindingSetAuthInfoExW(Binding, 0, 4u, 0xAu, 0, 0, &SecurityQOS);
          if ( !v3 )
            goto LABEL_6;
        }
        else
        {
          v3 = 14;
        }
      }
    }
  }
  if ( Binding )
  {
    RpcBindingFree(&Binding);
    Binding = 0;
  }
LABEL_6:
  if ( String )
    RpcStringFreeA(&String);
  if ( pSid )
    FreeSid(pSid);
  *a2 = Binding;
  return v3;
}

```

## disassembly

```asm
0x180056fb0  push    rbp
0x180056fb2  push    rbx
0x180056fb3  push    rsi
0x180056fb4  push    rdi
0x180056fb5  lea     rbp, [rsp-3Fh]
0x180056fba  sub     rsp, 0B8h
0x180056fc1  mov     rax, cs:__security_cookie
0x180056fc8  xor     rax, rsp
0x180056fcb  mov     [rbp+57h+var_28], rax
0x180056fcf  xor     esi, esi
0x180056fd1  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180056fd7  xorps   xmm0, xmm0
0x180056fda  mov     [rbp+57h+String], rsi
0x180056fde  xor     eax, eax
0x180056fe0  mov     [rbp+57h+Binding], rsi
0x180056fe4  movups  xmmword ptr [rbp+57h+SecurityQOS.Version], xmm0
0x180056fe8  mov     [rbp+57h+var_38], rax
0x180056fec  mov     rdi, rdx
0x180056fef  movups  [rbp+57h+var_48], xmm0
0x180056ff3  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x180056ff6  mov     [rbp+57h+var_60], rsi
0x180056ffa  call    WaitForCryptService
0x180056fff  lea     rax, [rbp+57h+String]
0x180057003  xor     r8d, r8d; NetworkAddr
0x180057006  mov     [rsp+0D0h+StringBinding], rax; StringBinding
0x18005700b  lea     r9, Endpoint; "keysvc"
0x180057012  lea     rdx, ProtSeq; "ncalrpc"
0x180057019  mov     [rsp+0D0h+Options], rsi; Options
0x18005701e  xor     ecx, ecx; ObjUuid
0x180057020  call    cs:__imp_RpcStringBindingComposeA
0x180057026  mov     ebx, eax
0x180057028  test    eax, eax
0x18005702a  jnz     loc_18005712D
0x180057030  mov     rcx, [rbp+57h+String]; StringBinding
0x180057034  lea     rdx, [rbp+57h+Binding]; Binding
0x180057038  call    cs:__imp_RpcBindingFromStringBindingA
0x18005703e  mov     ebx, eax
0x180057040  test    eax, eax
0x180057042  jnz     loc_18005712D
0x180057048  mov     rcx, [rbp+57h+Binding]; Binding
0x18005704c  lea     rdx, qword_180123300; IfSpec
0x180057053  call    cs:__imp_RpcEpResolveBinding
0x180057059  mov     ebx, eax
0x18005705b  test    eax, eax
0x18005705d  jnz     loc_18005712D
0x180057063  lea     rax, [rbp+57h+var_60]
0x180057067  xor     r9d, r9d; nSubAuthority1
0x18005706a  mov     [rsp+0D0h+pSid], rax; pSid
0x18005706f  lea     ebx, [rsi+1]
0x180057072  mov     [rsp+0D0h+nSubAuthority7], esi; nSubAuthority7
0x180057076  lea     r8d, [rsi+14h]; nSubAuthority0
0x18005707a  mov     [rsp+0D0h+nSubAuthority6], esi; nSubAuthority6
0x18005707e  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180057082  mov     [rsp+0D0h+nSubAuthority5], esi; nSubAuthority5
0x180057086  mov     dl, bl; nSubAuthorityCount
0x180057088  mov     [rsp+0D0h+nSubAuthority4], esi; nSubAuthority4
0x18005708c  mov     dword ptr [rsp+0D0h+StringBinding], esi; nSubAuthority3
0x180057090  mov     dword ptr [rsp+0D0h+Options], esi; nSubAuthority2
0x180057094  call    cs:__imp_AllocateAndInitializeSid
0x18005709a  test    eax, eax
0x18005709c  jz      loc_180057143
0x1800570a2  mov     rcx, [rbp+57h+Binding]; Binding
0x1800570a6  lea     eax, [rsi+3]
0x1800570a9  mov     [rbp+57h+SecurityQOS.Version], eax
0x1800570ac  lea     r9d, [rsi+0Ah]; AuthnSvc
0x1800570b0  mov     [rbp+57h+SecurityQOS.ImpersonationType], eax
0x1800570b3  lea     r8d, [rsi+4]; AuthnLevel
0x1800570b7  mov     rax, [rbp+57h+var_60]
0x1800570bb  xor     edx, edx; ServerPrincName
0x1800570bd  mov     [rbp+57h+var_38], rax
0x1800570c1  lea     rax, [rbp+57h+SecurityQOS]
0x1800570c5  mov     qword ptr [rsp+0D0h+nSubAuthority4], rax; SecurityQOS
0x1800570ca  mov     dword ptr [rsp+0D0h+StringBinding], esi; AuthzSvc
0x1800570ce  mov     [rsp+0D0h+Options], rsi; AuthIdentity
0x1800570d3  mov     qword ptr [rbp+57h+var_48], rsi
0x1800570d7  mov     [rbp+57h+SecurityQOS.Capabilities], ebx
0x1800570da  mov     [rbp+57h+SecurityQOS.IdentityTracking], ebx
0x1800570dd  mov     qword ptr [rbp+57h+var_48+8], rsi
0x1800570e1  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800570e7  mov     ebx, eax
0x1800570e9  test    eax, eax
0x1800570eb  jnz     short loc_18005712D
0x1800570ed  cmp     [rbp+57h+String], rsi
0x1800570f1  jz      short loc_1800570FD
0x1800570f3  lea     rcx, [rbp+57h+String]; String
0x1800570f7  call    cs:__imp_RpcStringFreeA
0x1800570fd  mov     rcx, [rbp+57h+var_60]; pSid
0x180057101  test    rcx, rcx
0x180057104  jz      short loc_18005710C
0x180057106  call    cs:__imp_FreeSid
0x18005710c  mov     rax, [rbp+57h+Binding]
0x180057110  mov     [rdi], rax
0x180057113  mov     eax, ebx
0x180057115  mov     rcx, [rbp+57h+var_28]
0x180057119  xor     rcx, rsp; StackCookie
0x18005711c  call    __security_check_cookie
0x180057121  add     rsp, 0B8h
0x180057128  pop     rdi
0x180057129  pop     rsi
0x18005712a  pop     rbx
0x18005712b  pop     rbp
0x18005712c  retn
0x18005712d  cmp     [rbp+57h+Binding], rsi
0x180057131  jz      short loc_1800570ED
0x180057133  lea     rcx, [rbp+57h+Binding]; Binding
0x180057137  call    cs:__imp_RpcBindingFree
0x18005713d  mov     [rbp+57h+Binding], rsi
0x180057141  jmp     short loc_1800570ED
0x180057143  mov     ebx, 0Eh
0x180057148  jmp     short loc_18005712D
```
