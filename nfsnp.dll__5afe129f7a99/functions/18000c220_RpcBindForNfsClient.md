# RpcBindForNfsClient

- ea: `0x18000c220`
- end: `0x18000c3fc`
- name: `RpcBindForNfsClient`
- size: `476`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE *)`
- caller_count: `9`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009d1c`
- `0x18000a020`
- `0x18000a61c`
- `0x18000abcc`
- `0x18000b0d8`
- `0x18000b600`
- `0x18000b954`
- `0x18000bb40`
- `0x18000bda4`

## callees

- `0x18000c220`
- `0x180012e70`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x18000c325`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18000c325`
- `ADVAPI32!LookupAccountSidW` at `0x18000c36c`
- `ADVAPI32!LookupAccountSidW` at `0x18000c36c`
- `RPCRT4!RpcStringFreeW` at `0x18000c2d2`
- `RPCRT4!RpcStringFreeW` at `0x18000c2d2`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000c3af`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000c3af`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000c29f`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000c29f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000c2bf`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000c2bf`
- `RPCRT4!RpcBindingFree` at `0x18000c3c6`
- `RPCRT4!RpcBindingFree` at `0x18000c3c6`

## string_xrefs

- `0x18000c25b`: `DiskAccess`

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
0x18000c220  push    rbp
0x18000c222  push    rbx
0x18000c223  push    rsi
0x18000c224  push    rdi
0x18000c225  lea     rbp, [rsp-448h]
0x18000c22d  sub     rsp, 548h
0x18000c234  mov     rax, cs:__security_cookie
0x18000c23b  xor     rax, rsp
0x18000c23e  mov     [rbp+460h+var_30], rax
0x18000c245  xor     esi, esi
0x18000c247  mov     word ptr [rbp+460h+pIdentifierAuthority.Value+4], 500h
0x18000c24d  mov     eax, 104h
0x18000c252  mov     [rsp+560h+String], rsi
0x18000c257  mov     [rsp+560h+cchName], eax
0x18000c25b  lea     r9, Endpoint; "DiskAccess"
0x18000c262  mov     [rsp+560h+cchReferencedDomainName], eax
0x18000c266  lea     rdx, ProtSeq; "ncalrpc"
0x18000c26d  lea     rax, [rbp+460h+var_4C0]
0x18000c271  mov     [rsp+560h+peUse], esi
0x18000c275  mov     [rbp+460h+Sid], rax
0x18000c279  mov     rdi, rcx
0x18000c27c  lea     rax, [rsp+560h+String]
0x18000c281  mov     dword ptr [rbp+460h+pIdentifierAuthority.Value], esi
0x18000c284  xorps   xmm0, xmm0
0x18000c287  mov     [rsp+560h+StringBinding], rax; StringBinding
0x18000c28c  xor     r8d, r8d; NetworkAddr
0x18000c28f  mov     [rsp+560h+Options], rsi; Options
0x18000c294  xor     ecx, ecx; ObjUuid
0x18000c296  mov     [rsp+560h+Binding], rsi
0x18000c29b  movups  xmmword ptr [rbp+460h+SecurityQOS.Version], xmm0
0x18000c29f  call    cs:__imp_RpcStringBindingComposeW
0x18000c2a6  nop     dword ptr [rax+rax+00h]
0x18000c2ab  mov     ebx, eax
0x18000c2ad  test    eax, eax
0x18000c2af  jnz     loc_18000C3D2
0x18000c2b5  mov     rcx, [rsp+560h+String]; StringBinding
0x18000c2ba  lea     rdx, [rsp+560h+Binding]; Binding
0x18000c2bf  call    cs:__imp_RpcBindingFromStringBindingW
0x18000c2c6  nop     dword ptr [rax+rax+00h]
0x18000c2cb  lea     rcx, [rsp+560h+String]; String
0x18000c2d0  mov     ebx, eax
0x18000c2d2  call    cs:__imp_RpcStringFreeW
0x18000c2d9  nop     dword ptr [rax+rax+00h]
0x18000c2de  test    ebx, ebx
0x18000c2e0  jnz     loc_18000C3D2
0x18000c2e6  lea     edx, [rsi+1]; nSubAuthorityCount
0x18000c2e9  mov     [rbp+460h+SecurityQOS.ImpersonationType], 2
0x18000c2f0  lea     rax, [rbp+460h+Sid]
0x18000c2f4  mov     [rbp+460h+SecurityQOS.Version], edx
0x18000c2f7  mov     [rsp+560h+pSid], rax; pSid
0x18000c2fc  lea     r8d, [rsi+14h]; nSubAuthority0
0x18000c300  mov     [rsp+560h+nSubAuthority7], esi; nSubAuthority7
0x18000c304  lea     rcx, [rbp+460h+pIdentifierAuthority]; pIdentifierAuthority
0x18000c308  mov     [rsp+560h+nSubAuthority6], esi; nSubAuthority6
0x18000c30c  xor     r9d, r9d; nSubAuthority1
0x18000c30f  mov     [rsp+560h+nSubAuthority5], esi; nSubAuthority5
0x18000c313  mov     [rsp+560h+nSubAuthority4], esi; nSubAuthority4
0x18000c317  mov     dword ptr [rsp+560h+StringBinding], esi; nSubAuthority3
0x18000c31b  mov     dword ptr [rsp+560h+Options], esi; nSubAuthority2
0x18000c31f  mov     [rbp+460h+SecurityQOS.Capabilities], edx
0x18000c322  mov     [rbp+460h+SecurityQOS.IdentityTracking], edx
0x18000c325  call    cs:__imp_AllocateAndInitializeSid
0x18000c32c  nop     dword ptr [rax+rax+00h]
0x18000c331  test    eax, eax
0x18000c333  jnz     short loc_18000C33D
0x18000c335  lea     ebx, [rsi+0Eh]
0x18000c338  jmp     loc_18000C3C1
0x18000c33d  mov     rdx, [rbp+460h+Sid]; Sid
0x18000c341  lea     rax, [rsp+560h+peUse]
0x18000c346  mov     qword ptr [rsp+560h+nSubAuthority4], rax; peUse
0x18000c34b  lea     r9, [rsp+560h+cchName]; cchName
0x18000c350  lea     rax, [rsp+560h+cchReferencedDomainName]
0x18000c355  xor     ecx, ecx; lpSystemName
0x18000c357  mov     [rsp+560h+StringBinding], rax; cchReferencedDomainName
0x18000c35c  lea     r8, [rbp+460h+Name]; Name
0x18000c360  lea     rax, [rbp+460h+ReferencedDomainName]
0x18000c367  mov     [rsp+560h+Options], rax; ReferencedDomainName
0x18000c36c  call    cs:__imp_LookupAccountSidW
0x18000c373  nop     dword ptr [rax+rax+00h]
0x18000c378  test    eax, eax
0x18000c37a  jnz     short loc_18000C383
0x18000c37c  mov     ebx, 534h
0x18000c381  jmp     short loc_18000C3C1
0x18000c383  mov     rcx, [rsp+560h+Binding]; Binding
0x18000c388  lea     rax, [rbp+460h+SecurityQOS]
0x18000c38c  mov     qword ptr [rsp+560h+nSubAuthority4], rax; SecurityQOS
0x18000c391  lea     rdx, [rbp+460h+Name]; ServerPrincName
0x18000c395  mov     r9d, 0Ah; AuthnSvc
0x18000c39b  mov     dword ptr [rsp+560h+StringBinding], esi; AuthzSvc
0x18000c39f  mov     [rbp+460h+var_24A], si
0x18000c3a6  mov     [rsp+560h+Options], rsi; AuthIdentity
0x18000c3ab  lea     r8d, [r9-4]; AuthnLevel
0x18000c3af  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000c3b6  nop     dword ptr [rax+rax+00h]
0x18000c3bb  mov     ebx, eax
0x18000c3bd  test    eax, eax
0x18000c3bf  jz      short loc_18000C3F0
0x18000c3c1  lea     rcx, [rsp+560h+Binding]; Binding
0x18000c3c6  call    cs:__imp_RpcBindingFree
0x18000c3cd  nop     dword ptr [rax+rax+00h]
0x18000c3d2  mov     eax, ebx
0x18000c3d4  mov     rcx, [rbp+460h+var_30]
0x18000c3db  xor     rcx, rsp; StackCookie
0x18000c3de  call    __security_check_cookie
0x18000c3e3  add     rsp, 548h
0x18000c3ea  pop     rdi
0x18000c3eb  pop     rsi
0x18000c3ec  pop     rbx
0x18000c3ed  pop     rbp
0x18000c3ee  retn
0x18000c3f0  mov     rax, [rsp+560h+Binding]
0x18000c3f5  mov     [rdi], rax
0x18000c3f8  xor     eax, eax
0x18000c3fa  jmp     short loc_18000C3D4
```
