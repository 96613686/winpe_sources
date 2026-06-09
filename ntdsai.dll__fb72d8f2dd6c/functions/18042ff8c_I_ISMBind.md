# I_ISMBind

- ea: `0x18042ff8c`
- end: `0x18043019e`
- name: `I_ISMBind`
- size: `530`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1804301a4`
- `0x18043027c`
- `0x180430330`
- `0x180430410`
- `0x1804304c0`

## callees

- `0x18001e090`
- `0x18042ff8c`

## import_xrefs

- `RPCRT4!I_RpcExceptionFilter` at `0x180477c01`
- `RPCRT4!I_RpcExceptionFilter` at `0x180477c01`
- `RPCRT4!RpcBindingFromStringBindingA` at `0x180430059`
- `RPCRT4!RpcBindingFromStringBindingA` at `0x180430059`
- `RPCRT4!RpcStringBindingComposeA` at `0x18043003d`
- `RPCRT4!RpcStringBindingComposeA` at `0x18043003d`
- `RPCRT4!RpcBindingFree` at `0x180430171`
- `RPCRT4!RpcBindingFree` at `0x180430171`
- `RPCRT4!RpcStringFreeA` at `0x18043014c`
- `RPCRT4!RpcStringFreeA` at `0x18043014c`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180430122`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180430122`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1804300a3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1804300a3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18043015f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18043015f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804300ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1804300ad`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1804300ed`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1804300ed`

## pseudocode

```c
__int64 __fastcall I_ISMBind(RPC_BINDING_HANDLE *Binding)
{
  unsigned int v2; // edi
  DWORD LastError; // eax
  RPC_CSTR String; // [rsp+68h] [rbp-260h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+70h] [rbp-258h] BYREF
  DWORD cchReferencedDomainName; // [rsp+74h] [rbp-254h] BYREF
  DWORD cchName; // [rsp+78h] [rbp-250h] BYREF
  PSID Sid[2]; // [rsp+80h] [rbp-248h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp-238h] BYREF
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
0x18042ff8c  mov     [rsp+arg_8], rbx
0x18042ff91  mov     [rsp+arg_10], rsi
0x18042ff96  push    rdi
0x18042ff97  sub     rsp, 2C0h
0x18042ff9e  mov     rax, cs:__security_cookie
0x18042ffa5  xor     rax, rsp
0x18042ffa8  mov     [rsp+2C8h+var_18], rax
0x18042ffb0  mov     rsi, rcx
0x18042ffb3  mov     [rsp+2C8h+var_240], rcx
0x18042ffbb  xor     ebx, ebx
0x18042ffbd  mov     [rsp+2C8h+String], rbx
0x18042ffc2  mov     dword ptr [rsp+2C8h+pIdentifierAuthority.Value], ebx
0x18042ffc9  mov     word ptr [rsp+2C8h+pIdentifierAuthority.Value+4], 500h
0x18042ffd3  mov     [rsp+2C8h+Sid], rbx
0x18042ffdb  mov     eax, 80h
0x18042ffe0  mov     [rsp+2C8h+cchName], eax
0x18042ffe4  mov     [rsp+2C8h+cchReferencedDomainName], eax
0x18042ffe8  mov     [rsp+2C8h+peUse], ebx
0x18042ffec  mov     [rcx], rbx
0x18042ffef  mov     [rsp+2C8h+SecurityQOS.Version], 1
0x18042fffa  mov     [rsp+2C8h+SecurityQOS.Capabilities], 1
0x180430005  mov     [rsp+2C8h+SecurityQOS.IdentityTracking], 1
0x180430010  mov     [rsp+2C8h+SecurityQOS.ImpersonationType], 2
0x18043001b  lea     rax, [rsp+2C8h+String]
0x180430020  mov     [rsp+2C8h+StringBinding], rax; StringBinding
0x180430025  mov     [rsp+2C8h+Options], rbx; Options
0x18043002a  lea     r9, Endpoint; "ISMSERV_LPC"
0x180430031  xor     r8d, r8d; NetworkAddr
0x180430034  lea     rdx, aNcalrpc_0; "ncalrpc"
0x18043003b  xor     ecx, ecx; ObjUuid
0x18043003d  call    cs:__imp_RpcStringBindingComposeA
0x180430043  mov     edi, eax
0x180430045  mov     [rsp+2C8h+var_268], eax
0x180430049  test    eax, eax
0x18043004b  jnz     loc_18043012E
0x180430051  mov     rdx, rsi; Binding
0x180430054  mov     rcx, [rsp+2C8h+String]; StringBinding
0x180430059  call    cs:__imp_RpcBindingFromStringBindingA
0x18043005f  mov     edi, eax
0x180430061  mov     [rsp+2C8h+var_268], eax
0x180430065  test    eax, eax
0x180430067  jnz     loc_18043012E
0x18043006d  lea     rax, [rsp+2C8h+Sid]
0x180430075  mov     [rsp+2C8h+pSid], rax; pSid
0x18043007a  mov     [rsp+2C8h+nSubAuthority7], ebx; nSubAuthority7
0x18043007e  mov     [rsp+2C8h+nSubAuthority6], ebx; nSubAuthority6
0x180430082  mov     [rsp+2C8h+nSubAuthority5], ebx; nSubAuthority5
0x180430086  mov     [rsp+2C8h+nSubAuthority4], ebx; nSubAuthority4
0x18043008a  mov     dword ptr [rsp+2C8h+StringBinding], ebx; nSubAuthority3
0x18043008e  mov     dword ptr [rsp+2C8h+Options], ebx; nSubAuthority2
0x180430092  xor     r9d, r9d; nSubAuthority1
0x180430095  lea     r8d, [rbx+12h]; nSubAuthority0
0x180430099  mov     dl, 1; nSubAuthorityCount
0x18043009b  lea     rcx, [rsp+2C8h+pIdentifierAuthority]; pIdentifierAuthority
0x1804300a3  call    cs:__imp_AllocateAndInitializeSid
0x1804300a9  test    eax, eax
0x1804300ab  jnz     short loc_1804300B5
0x1804300ad  call    cs:__imp_GetLastError
0x1804300b3  jmp     short loc_180430128
0x1804300b5  lea     rax, [rsp+2C8h+peUse]
0x1804300ba  mov     qword ptr [rsp+2C8h+nSubAuthority4], rax; peUse
0x1804300bf  lea     rax, [rsp+2C8h+cchReferencedDomainName]
0x1804300c4  mov     [rsp+2C8h+StringBinding], rax; cchReferencedDomainName
0x1804300c9  lea     rax, [rsp+2C8h+ReferencedDomainName]
0x1804300d1  mov     [rsp+2C8h+Options], rax; ReferencedDomainName
0x1804300d6  lea     r9, [rsp+2C8h+cchName]; cchName
0x1804300db  lea     r8, [rsp+2C8h+Name]; Name
0x1804300e3  mov     rdx, [rsp+2C8h+Sid]; Sid
0x1804300eb  xor     ecx, ecx; lpSystemName
0x1804300ed  call    cs:__imp_LookupAccountSidW
0x1804300f3  test    eax, eax
0x1804300f5  jz      short loc_1804300AD
0x1804300f7  lea     rax, [rsp+2C8h+SecurityQOS]
0x1804300ff  mov     qword ptr [rsp+2C8h+nSubAuthority4], rax; SecurityQOS
0x180430104  mov     dword ptr [rsp+2C8h+StringBinding], ebx; AuthzSvc
0x180430108  mov     [rsp+2C8h+Options], rbx; AuthIdentity
0x18043010d  mov     r9d, 0Ah; AuthnSvc
0x180430113  lea     r8d, [r9-4]; AuthnLevel
0x180430117  lea     rdx, [rsp+2C8h+Name]; ServerPrincName
0x18043011f  mov     rcx, [rsi]; Binding
0x180430122  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180430128  mov     edi, eax
0x18043012a  mov     [rsp+2C8h+var_268], eax
0x18043012e  jmp     short loc_180430140
0x180430130  mov     edi, eax
0x180430132  mov     [rsp+2C8h+var_268], eax
0x180430136  xor     ebx, ebx
0x180430138  mov     rsi, [rsp+2C8h+var_240]
0x180430140  cmp     [rsp+2C8h+String], rbx
0x180430145  jz      short loc_180430152
0x180430147  lea     rcx, [rsp+2C8h+String]; String
0x18043014c  call    cs:__imp_RpcStringFreeA
0x180430152  mov     rcx, [rsp+2C8h+Sid]; pSid
0x18043015a  test    rcx, rcx
0x18043015d  jz      short loc_180430165
0x18043015f  call    cs:__imp_FreeSid
0x180430165  test    edi, edi
0x180430167  jz      short loc_180430177
0x180430169  cmp     [rsi], rbx
0x18043016c  jz      short loc_180430177
0x18043016e  mov     rcx, rsi; Binding
0x180430171  call    cs:__imp_RpcBindingFree
0x180430177  mov     eax, edi
0x180430179  mov     rcx, [rsp+2C8h+var_18]
0x180430181  xor     rcx, rsp; StackCookie
0x180430184  call    __security_check_cookie
0x180430189  lea     r11, [rsp+2C8h+var_8]
0x180430191  mov     rbx, [r11+18h]
0x180430195  mov     rsi, [r11+20h]
0x180430199  mov     rsp, r11
0x18043019c  pop     rdi
0x18043019d  retn
0x180477bf3  push    rbp
0x180477bf5  sub     rsp, 60h
0x180477bf9  mov     rbp, rdx
0x180477bfc  mov     rcx, [rcx]
0x180477bff  mov     ecx, [rcx]; ExceptionCode
0x180477c01  call    cs:__imp_I_RpcExceptionFilter
0x180477c07  nop
0x180477c08  add     rsp, 60h
0x180477c0c  pop     rbp
0x180477c0d  retn
```
