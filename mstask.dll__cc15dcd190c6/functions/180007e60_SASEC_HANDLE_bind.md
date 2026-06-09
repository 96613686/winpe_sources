# SASEC_HANDLE_bind

- ea: `0x180007e60`
- end: `0x180008073`
- name: `SASEC_HANDLE_bind`
- size: `531`
- prototype: `__int64 __fastcall(LPCWSTR ServiceName)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180007e60`
- `0x18000807c`
- `0x18000bac4`
- `0x18001aac0`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180007f31`
- `RPCRT4!RpcBindingFree` at `0x180007f31`
- `RPCRT4!RpcEpResolveBinding` at `0x180007eb3`
- `RPCRT4!RpcEpResolveBinding` at `0x180007eb3`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180008035`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180008035`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180007fdd`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180007fdd`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180007f84`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180007f84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008069`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008069`
- `DSPARSE!DsMakeSpnW` at `0x180007f19`
- `DSPARSE!DsMakeSpnW` at `0x180007f19`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180007fd0`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180007fd0`

## pseudocode

```c
RPC_BINDING_HANDLE __fastcall SASEC_HANDLE_bind(unsigned __int16 *ServiceName, unsigned __int16 *a2)
{
  LPCWSTR v2; // rbx
  RPC_BINDING_HANDLE v3; // rsi
  BOOL v5; // edi
  RPC_BINDING_HANDLE Sid; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+70h] [rbp-90h] BYREF
  _SID_NAME_USE peUse; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchReferencedDomainName; // [rsp+7Ch] [rbp-84h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp-80h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v2 = ServiceName;
  Binding = 0;
  if ( ServiceName )
  {
    BindNamedPipe(ServiceName, &Binding);
  }
  else if ( !BindViaProtocol(0, a2, &Binding) )
  {
    RpcEpResolveBinding(Binding, &unk_18001CC90);
  }
  v3 = Binding;
  if ( !Binding )
    return v3;
  cchName = 261;
  if ( v2 )
  {
    if ( *v2 == 92 && v2[1] == 92 )
      v2 += 2;
    if ( DsMakeSpnW(L"atsvc", v2, 0, 0, 0, &cchName, Name) )
      goto LABEL_11;
LABEL_14:
    SecurityQOS.Version = 1;
    SecurityQOS.Capabilities = 1;
    SecurityQOS.IdentityTracking = 1;
    SecurityQOS.ImpersonationType = 3;
    if ( RpcBindingSetAuthInfoExW(v3, Name, 6u, 10 - (v2 != 0), 0, 0, &SecurityQOS) )
    {
LABEL_11:
      Sid = v3;
      RpcBindingFree(&Sid);
      return 0;
    }
    return v3;
  }
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  Sid = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid) )
  {
    cchReferencedDomainName = 261;
    peUse = 0;
    v5 = LookupAccountSidLocalW(Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse);
    FreeSid(Sid);
    if ( v5 )
      goto LABEL_14;
  }
  GetLastError();
  return 0;
}

```

## disassembly

```asm
0x180007e60  mov     [rsp-8+arg_10], rbx
0x180007e65  push    rbp
0x180007e66  push    rsi
0x180007e67  push    r14
0x180007e69  lea     rbp, [rsp-3D0h]
0x180007e71  sub     rsp, 4D0h
0x180007e78  mov     rax, cs:__security_cookie
0x180007e7f  xor     rax, rsp
0x180007e82  mov     [rbp+3E0h+var_20], rax
0x180007e89  xor     r14d, r14d
0x180007e8c  mov     rbx, rcx
0x180007e8f  mov     [rsp+4E0h+Binding], r14
0x180007e94  test    rcx, rcx
0x180007e97  jnz     short loc_180007EBB
0x180007e99  lea     r8, [rsp+4E0h+Binding]; void **
0x180007e9e  call    ?BindViaProtocol@@YAJPEAG0PEAPEAX@Z; BindViaProtocol(ushort *,ushort *,void * *)
0x180007ea3  test    eax, eax
0x180007ea5  jnz     short loc_180007EC5
0x180007ea7  mov     rcx, [rsp+4E0h+Binding]; Binding
0x180007eac  lea     rdx, unk_18001CC90; IfSpec
0x180007eb3  call    cs:__imp_RpcEpResolveBinding
0x180007eb9  jmp     short loc_180007EC5
0x180007ebb  lea     rdx, [rsp+4E0h+Binding]; void **
0x180007ec0  call    ?BindNamedPipe@@YAJPEAGPEAPEAX@Z; BindNamedPipe(ushort *,void * *)
0x180007ec5  mov     rsi, [rsp+4E0h+Binding]
0x180007eca  test    rsi, rsi
0x180007ecd  jz      loc_180008043
0x180007ed3  mov     [rsp+4E0h+cchName], 105h
0x180007edb  test    rbx, rbx
0x180007ede  jz      short loc_180007F3E
0x180007ee0  cmp     word ptr [rbx], 5Ch ; '\'
0x180007ee4  jnz     short loc_180007EF1
0x180007ee6  cmp     word ptr [rbx+2], 5Ch ; '\'
0x180007eeb  jnz     short loc_180007EF1
0x180007eed  add     rbx, 4
0x180007ef1  lea     rax, [rbp+3E0h+Name]
0x180007ef5  xor     r9d, r9d; InstancePort
0x180007ef8  mov     [rsp+4E0h+pszSpn], rax; pszSpn
0x180007efd  lea     rcx, ServiceClass; "atsvc"
0x180007f04  lea     rax, [rsp+4E0h+cchName]
0x180007f09  xor     r8d, r8d; InstanceName
0x180007f0c  mov     [rsp+4E0h+pcSpnLength], rax; pcSpnLength
0x180007f11  mov     rdx, rbx; ServiceName
0x180007f14  mov     [rsp+4E0h+Referrer], r14; Referrer
0x180007f19  call    cs:__imp_DsMakeSpnW
0x180007f1f  test    eax, eax
0x180007f21  jz      loc_180007FEF
0x180007f27  lea     rcx, [rsp+4E0h+Sid]; Binding
0x180007f2c  mov     [rsp+4E0h+Sid], rsi
0x180007f31  call    cs:__imp_RpcBindingFree
0x180007f37  xor     eax, eax
0x180007f39  jmp     loc_180008046
0x180007f3e  lea     rax, [rsp+4E0h+Sid]
0x180007f43  mov     dword ptr [rbp+3E0h+pIdentifierAuthority.Value], r14d
0x180007f47  mov     [rsp+4E0h+pSid], rax; pSid
0x180007f4c  lea     rcx, [rbp+3E0h+pIdentifierAuthority]; pIdentifierAuthority
0x180007f50  mov     [rsp+4E0h+nSubAuthority7], r14d; nSubAuthority7
0x180007f55  xor     r9d, r9d; nSubAuthority1
0x180007f58  mov     [rsp+4E0h+nSubAuthority6], r14d; nSubAuthority6
0x180007f5d  mov     r8d, 12h; nSubAuthority0
0x180007f63  mov     [rsp+4E0h+nSubAuthority5], r14d; nSubAuthority5
0x180007f68  mov     dl, 1; nSubAuthorityCount
0x180007f6a  mov     dword ptr [rsp+4E0h+pszSpn], r14d; nSubAuthority4
0x180007f6f  mov     dword ptr [rsp+4E0h+pcSpnLength], r14d; nSubAuthority3
0x180007f74  mov     dword ptr [rsp+4E0h+Referrer], r14d; nSubAuthority2
0x180007f79  mov     word ptr [rbp+3E0h+pIdentifierAuthority.Value+4], 500h
0x180007f7f  mov     [rsp+4E0h+Sid], r14
0x180007f84  call    cs:__imp_AllocateAndInitializeSid
0x180007f8a  test    eax, eax
0x180007f8c  jz      loc_180008069
0x180007f92  mov     rcx, [rsp+4E0h+Sid]; Sid
0x180007f97  lea     rax, [rsp+4E0h+peUse]
0x180007f9c  mov     [rsp+4E0h+pcSpnLength], rax; peUse
0x180007fa1  lea     r9, [rbp+3E0h+ReferencedDomainName]; ReferencedDomainName
0x180007fa8  lea     rax, [rsp+4E0h+cchReferencedDomainName]
0x180007fad  mov     [rsp+4E0h+arg_8], rdi
0x180007fb5  lea     r8, [rsp+4E0h+cchName]; cchName
0x180007fba  mov     [rsp+4E0h+Referrer], rax; cchReferencedDomainName
0x180007fbf  lea     rdx, [rbp+3E0h+Name]; Name
0x180007fc3  mov     [rsp+4E0h+cchReferencedDomainName], 105h
0x180007fcb  mov     [rsp+4E0h+peUse], r14d
0x180007fd0  call    cs:__imp_LookupAccountSidLocalW
0x180007fd6  mov     rcx, [rsp+4E0h+Sid]; pSid
0x180007fdb  mov     edi, eax
0x180007fdd  call    cs:__imp_FreeSid
0x180007fe3  test    edi, edi
0x180007fe5  mov     rdi, [rsp+4E0h+arg_8]
0x180007fed  jz      short loc_180008069
0x180007fef  lea     rax, [rbp+3E0h+SecurityQOS]
0x180007ff3  mov     [rbp+3E0h+SecurityQOS.Version], 1
0x180007ffa  mov     [rsp+4E0h+pszSpn], rax; SecurityQOS
0x180007fff  lea     rdx, [rbp+3E0h+Name]; ServerPrincName
0x180008003  neg     rbx
0x180008006  mov     dword ptr [rsp+4E0h+pcSpnLength], r14d; AuthzSvc
0x18000800b  mov     r8d, 6; AuthnLevel
0x180008011  mov     [rbp+3E0h+SecurityQOS.Capabilities], 1
0x180008018  sbb     r9d, r9d
0x18000801b  mov     [rbp+3E0h+SecurityQOS.IdentityTracking], 1
0x180008022  add     r9d, 0Ah; AuthnSvc
0x180008026  mov     [rbp+3E0h+SecurityQOS.ImpersonationType], 3
0x18000802d  mov     rcx, rsi; Binding
0x180008030  mov     [rsp+4E0h+Referrer], r14; AuthIdentity
0x180008035  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000803b  test    eax, eax
0x18000803d  jnz     loc_180007F27
0x180008043  mov     rax, rsi
0x180008046  mov     rcx, [rbp+3E0h+var_20]
0x18000804d  xor     rcx, rsp; StackCookie
0x180008050  call    __security_check_cookie
0x180008055  mov     rbx, [rsp+4E0h+arg_10]
0x18000805d  add     rsp, 4D0h
0x180008064  pop     r14
0x180008066  pop     rsi
0x180008067  pop     rbp
0x180008068  retn
0x180008069  call    cs:__imp_GetLastError
0x18000806f  xor     eax, eax
0x180008071  jmp     short loc_180008046
```
