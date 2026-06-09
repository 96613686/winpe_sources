# I_ISMBind

- ea: `0x18008450c`
- end: `0x18008471e`
- name: `I_ISMBind`
- size: `530`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180084740`

## callees

- `0x18000e270`
- `0x18008450c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008462d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008462d`
- `RPCRT4!RpcStringFreeA` at `0x1800846cc`
- `RPCRT4!RpcStringFreeA` at `0x1800846cc`
- `RPCRT4!RpcBindingFree` at `0x1800846f1`
- `RPCRT4!RpcBindingFree` at `0x1800846f1`
- `RPCRT4!I_RpcExceptionFilter` at `0x180089d36`
- `RPCRT4!I_RpcExceptionFilter` at `0x180089d36`
- `RPCRT4!RpcBindingFromStringBindingA` at `0x1800845d9`
- `RPCRT4!RpcBindingFromStringBindingA` at `0x1800845d9`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800846a2`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800846a2`
- `RPCRT4!RpcStringBindingComposeA` at `0x1800845bd`
- `RPCRT4!RpcStringBindingComposeA` at `0x1800845bd`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800846df`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800846df`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180084623`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180084623`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18008466d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18008466d`

## pseudocode

```c
__int64 __fastcall I_ISMBind(RPC_BINDING_HANDLE *Binding)
{
  unsigned int v2; // edi
  DWORD LastError; // eax
  RPC_CSTR String; // [rsp+68h] [rbp-260h] BYREF
  _SID_NAME_USE peUse; // [rsp+70h] [rbp-258h] BYREF
  DWORD cchReferencedDomainName; // [rsp+74h] [rbp-254h] BYREF
  DWORD cchName; // [rsp+78h] [rbp-250h] BYREF
  PSID Sid[2]; // [rsp+80h] [rbp-248h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp-238h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+98h] [rbp-230h] BYREF
  WCHAR Name[128]; // [rsp+B0h] [rbp-218h] BYREF
  WCHAR ReferencedDomainName[128]; // [rsp+1B0h] [rbp-118h] BYREF

  Sid[1] = Binding;
  String = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  Sid[0] = 0;
  cchName = 128;
  cchReferencedDomainName = 128;
  peUse = 0;
  *Binding = 0;
  SecurityQOS.Version = 1;
  SecurityQOS.Capabilities = 1;
  SecurityQOS.IdentityTracking = 1;
  SecurityQOS.ImpersonationType = 2;
  v2 = RpcStringBindingComposeA(0, (RPC_CSTR)"ncalrpc", 0, (RPC_CSTR)"ISMSERV_LPC", 0, &String);
  if ( !v2 )
  {
    v2 = RpcBindingFromStringBindingA(String, Binding);
    if ( !v2 )
    {
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, Sid)
        && LookupAccountSidW(0, Sid[0], Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
      {
        LastError = RpcBindingSetAuthInfoExW(*Binding, Name, 6u, 0xAu, 0, 0, &SecurityQOS);
      }
      else
      {
        LastError = GetLastError();
      }
      v2 = LastError;
    }
  }
  if ( String )
    RpcStringFreeA(&String);
  if ( Sid[0] )
    FreeSid(Sid[0]);
  if ( v2 && *Binding )
    RpcBindingFree(Binding);
  return v2;
}

```

## disassembly

```asm
0x18008450c  mov     [rsp+arg_8], rbx
0x180084511  mov     [rsp+arg_10], rsi
0x180084516  push    rdi
0x180084517  sub     rsp, 2C0h
0x18008451e  mov     rax, cs:__security_cookie
0x180084525  xor     rax, rsp
0x180084528  mov     [rsp+2C8h+var_18], rax
0x180084530  mov     rsi, rcx
0x180084533  mov     [rsp+2C8h+var_240], rcx
0x18008453b  xor     ebx, ebx
0x18008453d  mov     [rsp+2C8h+String], rbx
0x180084542  mov     dword ptr [rsp+2C8h+pIdentifierAuthority.Value], ebx
0x180084549  mov     word ptr [rsp+2C8h+pIdentifierAuthority.Value+4], 500h
0x180084553  mov     [rsp+2C8h+Sid], rbx
0x18008455b  mov     eax, 80h
0x180084560  mov     [rsp+2C8h+cchName], eax
0x180084564  mov     [rsp+2C8h+cchReferencedDomainName], eax
0x180084568  mov     [rsp+2C8h+peUse], ebx
0x18008456c  mov     [rcx], rbx
0x18008456f  mov     [rsp+2C8h+SecurityQOS.Version], 1
0x18008457a  mov     [rsp+2C8h+SecurityQOS.Capabilities], 1
0x180084585  mov     [rsp+2C8h+SecurityQOS.IdentityTracking], 1
0x180084590  mov     [rsp+2C8h+SecurityQOS.ImpersonationType], 2
0x18008459b  lea     rax, [rsp+2C8h+String]
0x1800845a0  mov     [rsp+2C8h+StringBinding], rax; StringBinding
0x1800845a5  mov     [rsp+2C8h+Options], rbx; Options
0x1800845aa  lea     r9, aIsmservLpc; "ISMSERV_LPC"
0x1800845b1  xor     r8d, r8d; NetworkAddr
0x1800845b4  lea     rdx, aNcalrpc_0; "ncalrpc"
0x1800845bb  xor     ecx, ecx; ObjUuid
0x1800845bd  call    cs:__imp_RpcStringBindingComposeA
0x1800845c3  mov     edi, eax
0x1800845c5  mov     [rsp+2C8h+var_268], eax
0x1800845c9  test    eax, eax
0x1800845cb  jnz     loc_1800846AE
0x1800845d1  mov     rdx, rsi; Binding
0x1800845d4  mov     rcx, [rsp+2C8h+String]; StringBinding
0x1800845d9  call    cs:__imp_RpcBindingFromStringBindingA
0x1800845df  mov     edi, eax
0x1800845e1  mov     [rsp+2C8h+var_268], eax
0x1800845e5  test    eax, eax
0x1800845e7  jnz     loc_1800846AE
0x1800845ed  lea     rax, [rsp+2C8h+Sid]
0x1800845f5  mov     [rsp+2C8h+pSid], rax; pSid
0x1800845fa  mov     [rsp+2C8h+nSubAuthority7], ebx; nSubAuthority7
0x1800845fe  mov     [rsp+2C8h+nSubAuthority6], ebx; nSubAuthority6
0x180084602  mov     [rsp+2C8h+nSubAuthority5], ebx; nSubAuthority5
0x180084606  mov     [rsp+2C8h+nSubAuthority4], ebx; nSubAuthority4
0x18008460a  mov     dword ptr [rsp+2C8h+StringBinding], ebx; nSubAuthority3
0x18008460e  mov     dword ptr [rsp+2C8h+Options], ebx; nSubAuthority2
0x180084612  xor     r9d, r9d; nSubAuthority1
0x180084615  lea     r8d, [rbx+12h]; nSubAuthority0
0x180084619  mov     dl, 1; nSubAuthorityCount
0x18008461b  lea     rcx, [rsp+2C8h+pIdentifierAuthority]; pIdentifierAuthority
0x180084623  call    cs:__imp_AllocateAndInitializeSid
0x180084629  test    eax, eax
0x18008462b  jnz     short loc_180084635
0x18008462d  call    cs:__imp_GetLastError
0x180084633  jmp     short loc_1800846A8
0x180084635  lea     rax, [rsp+2C8h+peUse]
0x18008463a  mov     qword ptr [rsp+2C8h+nSubAuthority4], rax; peUse
0x18008463f  lea     rax, [rsp+2C8h+cchReferencedDomainName]
0x180084644  mov     [rsp+2C8h+StringBinding], rax; cchReferencedDomainName
0x180084649  lea     rax, [rsp+2C8h+ReferencedDomainName]
0x180084651  mov     [rsp+2C8h+Options], rax; ReferencedDomainName
0x180084656  lea     r9, [rsp+2C8h+cchName]; cchName
0x18008465b  lea     r8, [rsp+2C8h+Name]; Name
0x180084663  mov     rdx, [rsp+2C8h+Sid]; Sid
0x18008466b  xor     ecx, ecx; lpSystemName
0x18008466d  call    cs:__imp_LookupAccountSidW
0x180084673  test    eax, eax
0x180084675  jz      short loc_18008462D
0x180084677  lea     rax, [rsp+2C8h+SecurityQOS]
0x18008467f  mov     qword ptr [rsp+2C8h+nSubAuthority4], rax; SecurityQOS
0x180084684  mov     dword ptr [rsp+2C8h+StringBinding], ebx; AuthzSvc
0x180084688  mov     [rsp+2C8h+Options], rbx; AuthIdentity
0x18008468d  mov     r9d, 0Ah; AuthnSvc
0x180084693  lea     r8d, [r9-4]; AuthnLevel
0x180084697  lea     rdx, [rsp+2C8h+Name]; ServerPrincName
0x18008469f  mov     rcx, [rsi]; Binding
0x1800846a2  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800846a8  mov     edi, eax
0x1800846aa  mov     [rsp+2C8h+var_268], eax
0x1800846ae  jmp     short loc_1800846C0
0x1800846b0  mov     edi, eax
0x1800846b2  mov     [rsp+2C8h+var_268], eax
0x1800846b6  xor     ebx, ebx
0x1800846b8  mov     rsi, [rsp+2C8h+var_240]
0x1800846c0  cmp     [rsp+2C8h+String], rbx
0x1800846c5  jz      short loc_1800846D2
0x1800846c7  lea     rcx, [rsp+2C8h+String]; String
0x1800846cc  call    cs:__imp_RpcStringFreeA
0x1800846d2  mov     rcx, [rsp+2C8h+Sid]; pSid
0x1800846da  test    rcx, rcx
0x1800846dd  jz      short loc_1800846E5
0x1800846df  call    cs:__imp_FreeSid
0x1800846e5  test    edi, edi
0x1800846e7  jz      short loc_1800846F7
0x1800846e9  cmp     [rsi], rbx
0x1800846ec  jz      short loc_1800846F7
0x1800846ee  mov     rcx, rsi; Binding
0x1800846f1  call    cs:__imp_RpcBindingFree
0x1800846f7  mov     eax, edi
0x1800846f9  mov     rcx, [rsp+2C8h+var_18]
0x180084701  xor     rcx, rsp; StackCookie
0x180084704  call    __security_check_cookie
0x180084709  lea     r11, [rsp+2C8h+var_8]
0x180084711  mov     rbx, [r11+18h]
0x180084715  mov     rsi, [r11+20h]
0x180084719  mov     rsp, r11
0x18008471c  pop     rdi
0x18008471d  retn
0x180089d28  push    rbp
0x180089d2a  sub     rsp, 60h
0x180089d2e  mov     rbp, rdx
0x180089d31  mov     rcx, [rcx]
0x180089d34  mov     ecx, [rcx]; ExceptionCode
0x180089d36  call    cs:__imp_I_RpcExceptionFilter
0x180089d3c  nop
0x180089d3d  add     rsp, 60h
0x180089d41  pop     rbp
0x180089d42  retn
```
