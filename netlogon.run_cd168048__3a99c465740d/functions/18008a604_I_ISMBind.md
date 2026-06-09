# I_ISMBind

- ea: `0x18008a604`
- end: `0x18008a84d`
- name: `I_ISMBind`
- size: `585`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *Binding)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008a878`

## callees

- `0x18000e910`
- `0x18008a604`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a737`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a737`
- `RPCRT4!RpcStringFreeA` at `0x18008a7e8`
- `RPCRT4!RpcStringFreeA` at `0x18008a7e8`
- `RPCRT4!RpcBindingFree` at `0x18008a819`
- `RPCRT4!RpcBindingFree` at `0x18008a819`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800904ba`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800904ba`
- `RPCRT4!RpcBindingFromStringBindingA` at `0x18008a6d7`
- `RPCRT4!RpcBindingFromStringBindingA` at `0x18008a6d7`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18008a7b8`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18008a7b8`
- `RPCRT4!RpcStringBindingComposeA` at `0x18008a6b5`
- `RPCRT4!RpcStringBindingComposeA` at `0x18008a6b5`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18008a801`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18008a801`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18008a727`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18008a727`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18008a77d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18008a77d`

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
0x18008a604  mov     [rsp+arg_8], rbx
0x18008a609  mov     [rsp+arg_10], rsi
0x18008a60e  push    rdi
0x18008a60f  sub     rsp, 2C0h
0x18008a616  mov     rax, cs:__security_cookie
0x18008a61d  xor     rax, rsp
0x18008a620  mov     [rsp+2C8h+var_18], rax
0x18008a628  mov     rsi, rcx
0x18008a62b  mov     [rsp+2C8h+var_240], rcx
0x18008a633  xor     ebx, ebx
0x18008a635  mov     [rsp+2C8h+String], rbx
0x18008a63a  mov     dword ptr [rsp+2C8h+pIdentifierAuthority.Value], ebx
0x18008a641  mov     word ptr [rsp+2C8h+pIdentifierAuthority.Value+4], 500h
0x18008a64b  mov     [rsp+2C8h+Sid], rbx
0x18008a653  mov     eax, 80h
0x18008a658  mov     [rsp+2C8h+cchName], eax
0x18008a65c  mov     [rsp+2C8h+cchReferencedDomainName], eax
0x18008a660  mov     [rsp+2C8h+peUse], ebx
0x18008a664  mov     [rcx], rbx
0x18008a667  mov     [rsp+2C8h+SecurityQOS.Version], 1
0x18008a672  mov     [rsp+2C8h+SecurityQOS.Capabilities], 1
0x18008a67d  mov     [rsp+2C8h+SecurityQOS.IdentityTracking], 1
0x18008a688  mov     [rsp+2C8h+SecurityQOS.ImpersonationType], 2
0x18008a693  lea     rax, [rsp+2C8h+String]
0x18008a698  mov     [rsp+2C8h+StringBinding], rax; StringBinding
0x18008a69d  mov     [rsp+2C8h+Options], rbx; Options
0x18008a6a2  lea     r9, aIsmservLpc; "ISMSERV_LPC"
0x18008a6a9  xor     r8d, r8d; NetworkAddr
0x18008a6ac  lea     rdx, aNcalrpc_0; "ncalrpc"
0x18008a6b3  xor     ecx, ecx; ObjUuid
0x18008a6b5  call    cs:__imp_RpcStringBindingComposeA
0x18008a6bc  nop     dword ptr [rax+rax+00h]
0x18008a6c1  mov     edi, eax
0x18008a6c3  mov     [rsp+2C8h+var_268], eax
0x18008a6c7  test    eax, eax
0x18008a6c9  jnz     loc_18008A7CA
0x18008a6cf  mov     rdx, rsi; Binding
0x18008a6d2  mov     rcx, [rsp+2C8h+String]; StringBinding
0x18008a6d7  call    cs:__imp_RpcBindingFromStringBindingA
0x18008a6de  nop     dword ptr [rax+rax+00h]
0x18008a6e3  mov     edi, eax
0x18008a6e5  mov     [rsp+2C8h+var_268], eax
0x18008a6e9  test    eax, eax
0x18008a6eb  jnz     loc_18008A7CA
0x18008a6f1  lea     rax, [rsp+2C8h+Sid]
0x18008a6f9  mov     [rsp+2C8h+pSid], rax; pSid
0x18008a6fe  mov     [rsp+2C8h+nSubAuthority7], ebx; nSubAuthority7
0x18008a702  mov     [rsp+2C8h+nSubAuthority6], ebx; nSubAuthority6
0x18008a706  mov     [rsp+2C8h+nSubAuthority5], ebx; nSubAuthority5
0x18008a70a  mov     [rsp+2C8h+nSubAuthority4], ebx; nSubAuthority4
0x18008a70e  mov     dword ptr [rsp+2C8h+StringBinding], ebx; nSubAuthority3
0x18008a712  mov     dword ptr [rsp+2C8h+Options], ebx; nSubAuthority2
0x18008a716  xor     r9d, r9d; nSubAuthority1
0x18008a719  lea     r8d, [rbx+12h]; nSubAuthority0
0x18008a71d  mov     dl, 1; nSubAuthorityCount
0x18008a71f  lea     rcx, [rsp+2C8h+pIdentifierAuthority]; pIdentifierAuthority
0x18008a727  call    cs:__imp_AllocateAndInitializeSid
0x18008a72e  nop     dword ptr [rax+rax+00h]
0x18008a733  test    eax, eax
0x18008a735  jnz     short loc_18008A745
0x18008a737  call    cs:__imp_GetLastError
0x18008a73e  nop     dword ptr [rax+rax+00h]
0x18008a743  jmp     short loc_18008A7C4
0x18008a745  lea     rax, [rsp+2C8h+peUse]
0x18008a74a  mov     qword ptr [rsp+2C8h+nSubAuthority4], rax; peUse
0x18008a74f  lea     rax, [rsp+2C8h+cchReferencedDomainName]
0x18008a754  mov     [rsp+2C8h+StringBinding], rax; cchReferencedDomainName
0x18008a759  lea     rax, [rsp+2C8h+ReferencedDomainName]
0x18008a761  mov     [rsp+2C8h+Options], rax; ReferencedDomainName
0x18008a766  lea     r9, [rsp+2C8h+cchName]; cchName
0x18008a76b  lea     r8, [rsp+2C8h+Name]; Name
0x18008a773  mov     rdx, [rsp+2C8h+Sid]; Sid
0x18008a77b  xor     ecx, ecx; lpSystemName
0x18008a77d  call    cs:__imp_LookupAccountSidW
0x18008a784  nop     dword ptr [rax+rax+00h]
0x18008a789  test    eax, eax
0x18008a78b  jz      short loc_18008A737
0x18008a78d  lea     rax, [rsp+2C8h+SecurityQOS]
0x18008a795  mov     qword ptr [rsp+2C8h+nSubAuthority4], rax; SecurityQOS
0x18008a79a  mov     dword ptr [rsp+2C8h+StringBinding], ebx; AuthzSvc
0x18008a79e  mov     [rsp+2C8h+Options], rbx; AuthIdentity
0x18008a7a3  mov     r9d, 0Ah; AuthnSvc
0x18008a7a9  lea     r8d, [r9-4]; AuthnLevel
0x18008a7ad  lea     rdx, [rsp+2C8h+Name]; ServerPrincName
0x18008a7b5  mov     rcx, [rsi]; Binding
0x18008a7b8  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18008a7bf  nop     dword ptr [rax+rax+00h]
0x18008a7c4  mov     edi, eax
0x18008a7c6  mov     [rsp+2C8h+var_268], eax
0x18008a7ca  jmp     short loc_18008A7DC
0x18008a7cc  mov     edi, eax
0x18008a7ce  mov     [rsp+2C8h+var_268], eax
0x18008a7d2  xor     ebx, ebx
0x18008a7d4  mov     rsi, [rsp+2C8h+var_240]
0x18008a7dc  cmp     [rsp+2C8h+String], rbx
0x18008a7e1  jz      short loc_18008A7F4
0x18008a7e3  lea     rcx, [rsp+2C8h+String]; String
0x18008a7e8  call    cs:__imp_RpcStringFreeA
0x18008a7ef  nop     dword ptr [rax+rax+00h]
0x18008a7f4  mov     rcx, [rsp+2C8h+Sid]; pSid
0x18008a7fc  test    rcx, rcx
0x18008a7ff  jz      short loc_18008A80D
0x18008a801  call    cs:__imp_FreeSid
0x18008a808  nop     dword ptr [rax+rax+00h]
0x18008a80d  test    edi, edi
0x18008a80f  jz      short loc_18008A825
0x18008a811  cmp     [rsi], rbx
0x18008a814  jz      short loc_18008A825
0x18008a816  mov     rcx, rsi; Binding
0x18008a819  call    cs:__imp_RpcBindingFree
0x18008a820  nop     dword ptr [rax+rax+00h]
0x18008a825  mov     eax, edi
0x18008a827  mov     rcx, [rsp+2C8h+var_18]
0x18008a82f  xor     rcx, rsp; StackCookie
0x18008a832  call    __security_check_cookie
0x18008a837  lea     r11, [rsp+2C8h+var_8]
0x18008a83f  mov     rbx, [r11+18h]
0x18008a843  mov     rsi, [r11+20h]
0x18008a847  mov     rsp, r11
0x18008a84a  pop     rdi
0x18008a84b  retn
0x1800904ac  push    rbp
0x1800904ae  sub     rsp, 60h
0x1800904b2  mov     rbp, rdx
0x1800904b5  mov     rcx, [rcx]
0x1800904b8  mov     ecx, [rcx]; ExceptionCode
0x1800904ba  call    cs:__imp_I_RpcExceptionFilter
0x1800904c1  nop     dword ptr [rax+rax+00h]
0x1800904c6  nop
0x1800904c7  add     rsp, 60h
0x1800904cb  pop     rbp
0x1800904cc  retn
```
