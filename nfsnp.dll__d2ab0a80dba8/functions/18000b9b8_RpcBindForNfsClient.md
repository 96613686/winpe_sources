# RpcBindForNfsClient

- ea: `0x18000b9b8`
- end: `0x18000bb66`
- name: `RpcBindForNfsClient`
- size: `430`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009660`
- `0x180009948`
- `0x180009f04`
- `0x18000a468`
- `0x18000a92c`
- `0x18000adf4`
- `0x18000b134`
- `0x18000b314`
- `0x18000b560`

## callees

- `0x18000b9b8`
- `0x180011ba0`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x18000baab`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18000baab`
- `ADVAPI32!LookupAccountSidW` at `0x18000bae9`
- `ADVAPI32!LookupAccountSidW` at `0x18000bae9`
- `RPCRT4!RpcStringFreeW` at `0x18000ba5e`
- `RPCRT4!RpcStringFreeW` at `0x18000ba5e`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000bb26`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000bb26`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000ba37`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000ba37`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000ba51`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000ba51`
- `RPCRT4!RpcBindingFree` at `0x18000bb37`
- `RPCRT4!RpcBindingFree` at `0x18000bb37`

## string_xrefs

- `0x18000b9f3`: `DiskAccess`

## pseudocode

```c
__int64 __fastcall RpcBindForNfsClient(RPC_BINDING_HANDLE *a1)
{
  unsigned int v2; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp-A0h] BYREF
  _SID_NAME_USE peUse; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchReferencedDomainName; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-90h] BYREF
  RPC_WSTR String; // [rsp+78h] [rbp-88h] BYREF
  PSID Sid; // [rsp+80h] [rbp-80h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp-78h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+90h] [rbp-70h] BYREF
  char v12; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Name[264]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+320h] [rbp+220h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  String = 0;
  cchName = 260;
  cchReferencedDomainName = 260;
  peUse = 0;
  Sid = &v12;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  Binding = 0;
  SecurityQOS = 0;
  v2 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"DiskAccess", 0, &String);
  if ( v2 )
    return v2;
  v2 = RpcBindingFromStringBindingW(String, &Binding);
  RpcStringFreeW(&String);
  if ( v2 )
    return v2;
  SecurityQOS.ImpersonationType = 2;
  SecurityQOS.Version = 1;
  SecurityQOS.Capabilities = 1;
  SecurityQOS.IdentityTracking = 1;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &Sid) )
  {
    v2 = 14;
LABEL_8:
    RpcBindingFree(&Binding);
    return v2;
  }
  if ( !LookupAccountSidW(0, Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    v2 = 1332;
    goto LABEL_8;
  }
  Name[259] = 0;
  v2 = RpcBindingSetAuthInfoExW(Binding, Name, 6u, 0xAu, 0, 0, &SecurityQOS);
  if ( v2 )
    goto LABEL_8;
  *a1 = Binding;
  return 0;
}

```

## disassembly

```asm
0x18000b9b8  push    rbp
0x18000b9ba  push    rbx
0x18000b9bb  push    rsi
0x18000b9bc  push    rdi
0x18000b9bd  lea     rbp, [rsp-448h]
0x18000b9c5  sub     rsp, 548h
0x18000b9cc  mov     rax, cs:__security_cookie
0x18000b9d3  xor     rax, rsp
0x18000b9d6  mov     [rbp+460h+var_30], rax
0x18000b9dd  xor     esi, esi
0x18000b9df  mov     word ptr [rbp+460h+pIdentifierAuthority.Value+4], 500h
0x18000b9e5  mov     eax, 104h
0x18000b9ea  mov     [rsp+560h+String], rsi
0x18000b9ef  mov     [rsp+560h+cchName], eax
0x18000b9f3  lea     r9, Endpoint; "DiskAccess"
0x18000b9fa  mov     [rsp+560h+cchReferencedDomainName], eax
0x18000b9fe  lea     rdx, ProtSeq; "ncalrpc"
0x18000ba05  lea     rax, [rbp+460h+var_4C0]
0x18000ba09  mov     [rsp+560h+peUse], esi
0x18000ba0d  mov     [rbp+460h+Sid], rax
0x18000ba11  mov     rdi, rcx
0x18000ba14  lea     rax, [rsp+560h+String]
0x18000ba19  mov     dword ptr [rbp+460h+pIdentifierAuthority.Value], esi
0x18000ba1c  xorps   xmm0, xmm0
0x18000ba1f  mov     [rsp+560h+StringBinding], rax; StringBinding
0x18000ba24  xor     r8d, r8d; NetworkAddr
0x18000ba27  mov     [rsp+560h+Options], rsi; Options
0x18000ba2c  xor     ecx, ecx; ObjUuid
0x18000ba2e  mov     [rsp+560h+Binding], rsi
0x18000ba33  movups  xmmword ptr [rbp+460h+SecurityQOS.Version], xmm0
0x18000ba37  call    cs:__imp_RpcStringBindingComposeW
0x18000ba3d  mov     ebx, eax
0x18000ba3f  test    eax, eax
0x18000ba41  jnz     loc_18000BB3D
0x18000ba47  mov     rcx, [rsp+560h+String]; StringBinding
0x18000ba4c  lea     rdx, [rsp+560h+Binding]; Binding
0x18000ba51  call    cs:__imp_RpcBindingFromStringBindingW
0x18000ba57  lea     rcx, [rsp+560h+String]; String
0x18000ba5c  mov     ebx, eax
0x18000ba5e  call    cs:__imp_RpcStringFreeW
0x18000ba64  test    ebx, ebx
0x18000ba66  jnz     loc_18000BB3D
0x18000ba6c  lea     edx, [rsi+1]; nSubAuthorityCount
0x18000ba6f  mov     [rbp+460h+SecurityQOS.ImpersonationType], 2
0x18000ba76  lea     rax, [rbp+460h+Sid]
0x18000ba7a  mov     [rbp+460h+SecurityQOS.Version], edx
0x18000ba7d  mov     [rsp+560h+pSid], rax; pSid
0x18000ba82  lea     r8d, [rsi+14h]; nSubAuthority0
0x18000ba86  mov     [rsp+560h+nSubAuthority7], esi; nSubAuthority7
0x18000ba8a  lea     rcx, [rbp+460h+pIdentifierAuthority]; pIdentifierAuthority
0x18000ba8e  mov     [rsp+560h+nSubAuthority6], esi; nSubAuthority6
0x18000ba92  xor     r9d, r9d; nSubAuthority1
0x18000ba95  mov     [rsp+560h+nSubAuthority5], esi; nSubAuthority5
0x18000ba99  mov     [rsp+560h+nSubAuthority4], esi; nSubAuthority4
0x18000ba9d  mov     dword ptr [rsp+560h+StringBinding], esi; nSubAuthority3
0x18000baa1  mov     dword ptr [rsp+560h+Options], esi; nSubAuthority2
0x18000baa5  mov     [rbp+460h+SecurityQOS.Capabilities], edx
0x18000baa8  mov     [rbp+460h+SecurityQOS.IdentityTracking], edx
0x18000baab  call    cs:__imp_AllocateAndInitializeSid
0x18000bab1  test    eax, eax
0x18000bab3  jnz     short loc_18000BABA
0x18000bab5  lea     ebx, [rsi+0Eh]
0x18000bab8  jmp     short loc_18000BB32
0x18000baba  mov     rdx, [rbp+460h+Sid]; Sid
0x18000babe  lea     rax, [rsp+560h+peUse]
0x18000bac3  mov     qword ptr [rsp+560h+nSubAuthority4], rax; peUse
0x18000bac8  lea     r9, [rsp+560h+cchName]; cchName
0x18000bacd  lea     rax, [rsp+560h+cchReferencedDomainName]
0x18000bad2  xor     ecx, ecx; lpSystemName
0x18000bad4  mov     [rsp+560h+StringBinding], rax; cchReferencedDomainName
0x18000bad9  lea     r8, [rbp+460h+Name]; Name
0x18000badd  lea     rax, [rbp+460h+ReferencedDomainName]
0x18000bae4  mov     [rsp+560h+Options], rax; ReferencedDomainName
0x18000bae9  call    cs:__imp_LookupAccountSidW
0x18000baef  test    eax, eax
0x18000baf1  jnz     short loc_18000BAFA
0x18000baf3  mov     ebx, 534h
0x18000baf8  jmp     short loc_18000BB32
0x18000bafa  mov     rcx, [rsp+560h+Binding]; Binding
0x18000baff  lea     rax, [rbp+460h+SecurityQOS]
0x18000bb03  mov     qword ptr [rsp+560h+nSubAuthority4], rax; SecurityQOS
0x18000bb08  lea     rdx, [rbp+460h+Name]; ServerPrincName
0x18000bb0c  mov     r9d, 0Ah; AuthnSvc
0x18000bb12  mov     dword ptr [rsp+560h+StringBinding], esi; AuthzSvc
0x18000bb16  mov     [rbp+460h+var_24A], si
0x18000bb1d  mov     [rsp+560h+Options], rsi; AuthIdentity
0x18000bb22  lea     r8d, [r9-4]; AuthnLevel
0x18000bb26  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000bb2c  mov     ebx, eax
0x18000bb2e  test    eax, eax
0x18000bb30  jz      short loc_18000BB5A
0x18000bb32  lea     rcx, [rsp+560h+Binding]; Binding
0x18000bb37  call    cs:__imp_RpcBindingFree
0x18000bb3d  mov     eax, ebx
0x18000bb3f  mov     rcx, [rbp+460h+var_30]
0x18000bb46  xor     rcx, rsp; StackCookie
0x18000bb49  call    __security_check_cookie
0x18000bb4e  add     rsp, 548h
0x18000bb55  pop     rdi
0x18000bb56  pop     rsi
0x18000bb57  pop     rbx
0x18000bb58  pop     rbp
0x18000bb59  retn
0x18000bb5a  mov     rax, [rsp+560h+Binding]
0x18000bb5f  mov     [rdi], rax
0x18000bb62  xor     eax, eax
0x18000bb64  jmp     short loc_18000BB3F
```
