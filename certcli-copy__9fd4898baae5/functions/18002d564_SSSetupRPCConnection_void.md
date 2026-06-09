# _SSSetupRPCConnection(void * *)

- ea: `0x18002d564`
- end: `0x18002d89d`
- name: `?_SSSetupRPCConnection@@YAKPEAPEAX@Z`
- size: `825`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18002d8a4`

## callees

- `0x18002d564`
- `0x18002da88`
- `0x18002de54`
- `0x180039740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d5e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d601`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d5e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d601`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7df`
- `RPCRT4!RpcStringFreeW` at `0x18002d859`
- `RPCRT4!RpcStringFreeW` at `0x18002d859`
- `RPCRT4!RpcStringBindingComposeW` at `0x18002d63d`
- `RPCRT4!RpcStringBindingComposeW` at `0x18002d63d`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18002d68a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18002d68a`
- `RPCRT4!RpcEpResolveBinding` at `0x18002d6ca`
- `RPCRT4!RpcEpResolveBinding` at `0x18002d6ca`
- `RPCRT4!RpcBindingFree` at `0x18002d86b`
- `RPCRT4!RpcBindingFree` at `0x18002d86b`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18002d811`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18002d811`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002d74b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18002d74b`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002d87a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002d87a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18002d7bc`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18002d7bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall _SSSetupRPCConnection(void **a1)
{
  DWORD LastError; // eax
  __int64 v3; // r8
  DWORD v4; // eax
  unsigned int v5; // ecx
  unsigned int v7; // ebx
  __int64 v8; // r8
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  DWORD v12; // eax
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp-A0h] BYREF
  RPC_WSTR String; // [rsp+68h] [rbp-98h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchReferencedDomainName; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cchName; // [rsp+78h] [rbp-88h] BYREF
  PSID Sid; // [rsp+80h] [rbp-80h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp-78h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Name[64]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ReferencedDomainName[256]; // [rsp+120h] [rbp+20h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  String = 0;
  SecurityQOS = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  Sid = 0;
  peUse = 0;
  Binding = 0;
  *a1 = 0;
  cchName = 64;
  cchReferencedDomainName = 256;
  if ( !(unsigned int)WaitForCryptService() )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v3, LastError);
    }
    v4 = GetLastError();
    v5 = 1062;
    if ( v4 == 1058 )
      return 1058;
    return v5;
  }
  v7 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, (RPC_WSTR)L"keysvc", 0, &String);
  if ( v7 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_36;
    v10 = 11;
  }
  else
  {
    v7 = RpcBindingFromStringBindingW(String, &Binding);
    if ( v7 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_36;
      v10 = 12;
    }
    else
    {
      v7 = RpcEpResolveBinding(Binding, qword_18004DA40);
      if ( !v7 )
      {
        SecurityQOS.Version = 1;
        SecurityQOS.Capabilities = 1;
        SecurityQOS.IdentityTracking = 1;
        SecurityQOS.ImpersonationType = 3;
        if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &Sid) )
        {
          if ( LookupAccountSidW(0, Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
          {
            v7 = RpcBindingSetAuthInfoExW(Binding, Name, 4u, 0xAu, 0, 0, &SecurityQOS);
            if ( !v7 )
            {
              *a1 = Binding;
              Binding = 0;
              goto LABEL_36;
            }
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_36;
            v10 = 16;
            goto LABEL_12;
          }
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_36;
          v12 = GetLastError();
          v10 = 15;
        }
        else
        {
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_36;
          v12 = GetLastError();
          v10 = 14;
        }
        v9 = WPP_GLOBAL_Control;
        v11 = v12;
        goto LABEL_13;
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_36;
      v10 = 13;
    }
  }
LABEL_12:
  v11 = v7;
LABEL_13:
  WPP_SF_d(v9[2], v10, v8, v11);
LABEL_36:
  if ( String )
    RpcStringFreeW(&String);
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( Sid )
    FreeSid(Sid);
  return v7;
}

```

## disassembly

```asm
0x18002d564  push    rbp
0x18002d566  push    rbx
0x18002d567  push    rsi
0x18002d568  push    rdi
0x18002d569  lea     rbp, [rsp-238h]
0x18002d571  sub     rsp, 338h
0x18002d578  mov     rax, cs:__security_cookie
0x18002d57f  xor     rax, rsp
0x18002d582  mov     [rbp+250h+var_30], rax
0x18002d589  xor     esi, esi
0x18002d58b  mov     word ptr [rbp+250h+pIdentifierAuthority.Value+4], 500h
0x18002d591  xorps   xmm0, xmm0
0x18002d594  mov     [rsp+350h+String], rsi
0x18002d599  movups  xmmword ptr [rbp+250h+SecurityQOS.Version], xmm0
0x18002d59d  mov     dword ptr [rbp+250h+pIdentifierAuthority.Value], esi
0x18002d5a0  mov     rdi, rcx
0x18002d5a3  mov     [rbp+250h+Sid], rsi
0x18002d5a7  mov     [rsp+350h+peUse], esi
0x18002d5ab  mov     [rsp+350h+Binding], rsi
0x18002d5b0  mov     [rcx], rsi
0x18002d5b3  mov     [rsp+350h+cchName], 40h ; '@'
0x18002d5bb  mov     [rsp+350h+cchReferencedDomainName], 100h
0x18002d5c3  call    WaitForCryptService
0x18002d5c8  test    eax, eax
0x18002d5ca  jnz     short loc_18002D61B
0x18002d5cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d5d3  lea     rax, WPP_GLOBAL_Control
0x18002d5da  cmp     rcx, rax
0x18002d5dd  jz      short loc_18002D601
0x18002d5df  test    byte ptr [rcx+1Ch], 1
0x18002d5e3  jz      short loc_18002D601
0x18002d5e5  call    cs:__imp_GetLastError
0x18002d5eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d5f2  lea     edx, [rsi+0Ah]
0x18002d5f5  mov     r9d, eax
0x18002d5f8  mov     rcx, [rcx+10h]
0x18002d5fc  call    WPP_SF_d
0x18002d601  call    cs:__imp_GetLastError
0x18002d607  mov     ecx, 426h
0x18002d60c  lea     edx, [rcx-4]
0x18002d60f  cmp     eax, edx
0x18002d611  cmovz   ecx, edx
0x18002d614  mov     eax, ecx
0x18002d616  jmp     loc_18002D882
0x18002d61b  lea     rax, [rsp+350h+String]
0x18002d620  xor     r8d, r8d; NetworkAddr
0x18002d623  mov     [rsp+350h+StringBinding], rax; StringBinding
0x18002d628  lea     r9, Endpoint; "keysvc"
0x18002d62f  lea     rdx, ProtSeq; "ncalrpc"
0x18002d636  mov     [rsp+350h+Options], rsi; Options
0x18002d63b  xor     ecx, ecx; ObjUuid
0x18002d63d  call    cs:__imp_RpcStringBindingComposeW
0x18002d643  mov     ebx, eax
0x18002d645  test    eax, eax
0x18002d647  jz      short loc_18002D680
0x18002d649  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d650  lea     rax, WPP_GLOBAL_Control
0x18002d657  cmp     rcx, rax
0x18002d65a  jz      loc_18002D84D
0x18002d660  test    byte ptr [rcx+1Ch], 1
0x18002d664  jz      loc_18002D84D
0x18002d66a  mov     edx, 0Bh
0x18002d66f  mov     r9d, ebx
0x18002d672  mov     rcx, [rcx+10h]
0x18002d676  call    WPP_SF_d
0x18002d67b  jmp     loc_18002D84D
0x18002d680  mov     rcx, [rsp+350h+String]; StringBinding
0x18002d685  lea     rdx, [rsp+350h+Binding]; Binding
0x18002d68a  call    cs:__imp_RpcBindingFromStringBindingW
0x18002d690  mov     ebx, eax
0x18002d692  test    eax, eax
0x18002d694  jz      short loc_18002D6BE
0x18002d696  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d69d  lea     rax, WPP_GLOBAL_Control
0x18002d6a4  cmp     rcx, rax
0x18002d6a7  jz      loc_18002D84D
0x18002d6ad  test    byte ptr [rcx+1Ch], 1
0x18002d6b1  jz      loc_18002D84D
0x18002d6b7  mov     edx, 0Ch
0x18002d6bc  jmp     short loc_18002D66F
0x18002d6be  mov     rcx, [rsp+350h+Binding]; Binding
0x18002d6c3  lea     rdx, qword_18004DA40; IfSpec
0x18002d6ca  call    cs:__imp_RpcEpResolveBinding
0x18002d6d0  mov     ebx, eax
0x18002d6d2  test    eax, eax
0x18002d6d4  jz      short loc_18002D701
0x18002d6d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d6dd  lea     rax, WPP_GLOBAL_Control
0x18002d6e4  cmp     rcx, rax
0x18002d6e7  jz      loc_18002D84D
0x18002d6ed  test    byte ptr [rcx+1Ch], 1
0x18002d6f1  jz      loc_18002D84D
0x18002d6f7  mov     edx, 0Dh
0x18002d6fc  jmp     loc_18002D66F
0x18002d701  lea     rax, [rbp+250h+Sid]
0x18002d705  mov     [rbp+250h+SecurityQOS.Version], 1
0x18002d70c  mov     [rsp+350h+pSid], rax; pSid
0x18002d711  lea     rcx, [rbp+250h+pIdentifierAuthority]; pIdentifierAuthority
0x18002d715  mov     [rsp+350h+nSubAuthority7], esi; nSubAuthority7
0x18002d719  xor     r9d, r9d; nSubAuthority1
0x18002d71c  mov     [rsp+350h+nSubAuthority6], esi; nSubAuthority6
0x18002d720  mov     dl, 1; nSubAuthorityCount
0x18002d722  mov     [rsp+350h+nSubAuthority5], esi; nSubAuthority5
0x18002d726  mov     [rsp+350h+nSubAuthority4], esi; nSubAuthority4
0x18002d72a  mov     dword ptr [rsp+350h+StringBinding], esi; nSubAuthority3
0x18002d72e  lea     r8d, [r9+14h]; nSubAuthority0
0x18002d732  mov     dword ptr [rsp+350h+Options], esi; nSubAuthority2
0x18002d736  mov     [rbp+250h+SecurityQOS.Capabilities], 1
0x18002d73d  mov     [rbp+250h+SecurityQOS.IdentityTracking], 1
0x18002d744  mov     [rbp+250h+SecurityQOS.ImpersonationType], 3
0x18002d74b  call    cs:__imp_AllocateAndInitializeSid
0x18002d751  test    eax, eax
0x18002d753  jnz     short loc_18002D790
0x18002d755  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d75c  lea     rax, WPP_GLOBAL_Control
0x18002d763  cmp     rcx, rax
0x18002d766  jz      loc_18002D84D
0x18002d76c  test    byte ptr [rcx+1Ch], 1
0x18002d770  jz      loc_18002D84D
0x18002d776  call    cs:__imp_GetLastError
0x18002d77c  mov     edx, 0Eh
0x18002d781  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d788  mov     r9d, eax
0x18002d78b  jmp     loc_18002D672
0x18002d790  mov     rdx, [rbp+250h+Sid]; Sid
0x18002d794  lea     rax, [rsp+350h+peUse]
0x18002d799  mov     qword ptr [rsp+350h+nSubAuthority4], rax; peUse
0x18002d79e  lea     r9, [rsp+350h+cchName]; cchName
0x18002d7a3  lea     rax, [rsp+350h+cchReferencedDomainName]
0x18002d7a8  xor     ecx, ecx; lpSystemName
0x18002d7aa  mov     [rsp+350h+StringBinding], rax; cchReferencedDomainName
0x18002d7af  lea     r8, [rbp+250h+Name]; Name
0x18002d7b3  lea     rax, [rbp+250h+ReferencedDomainName]
0x18002d7b7  mov     [rsp+350h+Options], rax; ReferencedDomainName
0x18002d7bc  call    cs:__imp_LookupAccountSidW
0x18002d7c2  test    eax, eax
0x18002d7c4  jnz     short loc_18002D7EC
0x18002d7c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d7cd  lea     rax, WPP_GLOBAL_Control
0x18002d7d4  cmp     rcx, rax
0x18002d7d7  jz      short loc_18002D84D
0x18002d7d9  test    byte ptr [rcx+1Ch], 1
0x18002d7dd  jz      short loc_18002D84D
0x18002d7df  call    cs:__imp_GetLastError
0x18002d7e5  mov     edx, 0Fh
0x18002d7ea  jmp     short loc_18002D781
0x18002d7ec  mov     rcx, [rsp+350h+Binding]; Binding
0x18002d7f1  lea     rax, [rbp+250h+SecurityQOS]
0x18002d7f5  mov     qword ptr [rsp+350h+nSubAuthority4], rax; SecurityQOS
0x18002d7fa  lea     rdx, [rbp+250h+Name]; ServerPrincName
0x18002d7fe  mov     r9d, 0Ah; AuthnSvc
0x18002d804  mov     dword ptr [rsp+350h+StringBinding], esi; AuthzSvc
0x18002d808  mov     [rsp+350h+Options], rsi; AuthIdentity
0x18002d80d  lea     r8d, [r9-6]; AuthnLevel
0x18002d811  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18002d817  mov     ebx, eax
0x18002d819  test    eax, eax
0x18002d81b  jz      short loc_18002D840
0x18002d81d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d824  lea     rax, WPP_GLOBAL_Control
0x18002d82b  cmp     rcx, rax
0x18002d82e  jz      short loc_18002D84D
0x18002d830  test    byte ptr [rcx+1Ch], 1
0x18002d834  jz      short loc_18002D84D
0x18002d836  mov     edx, 10h
0x18002d83b  jmp     loc_18002D66F
0x18002d840  mov     rax, [rsp+350h+Binding]
0x18002d845  mov     [rdi], rax
0x18002d848  mov     [rsp+350h+Binding], rsi
0x18002d84d  cmp     [rsp+350h+String], rsi
0x18002d852  jz      short loc_18002D85F
0x18002d854  lea     rcx, [rsp+350h+String]; String
0x18002d859  call    cs:__imp_RpcStringFreeW
0x18002d85f  cmp     [rsp+350h+Binding], rsi
0x18002d864  jz      short loc_18002D871
0x18002d866  lea     rcx, [rsp+350h+Binding]; Binding
0x18002d86b  call    cs:__imp_RpcBindingFree
0x18002d871  mov     rcx, [rbp+250h+Sid]; pSid
0x18002d875  test    rcx, rcx
0x18002d878  jz      short loc_18002D880
0x18002d87a  call    cs:__imp_FreeSid
0x18002d880  mov     eax, ebx
0x18002d882  mov     rcx, [rbp+250h+var_30]
0x18002d889  xor     rcx, rsp; StackCookie
0x18002d88c  call    __security_check_cookie
0x18002d891  add     rsp, 338h
0x18002d898  pop     rdi
0x18002d899  pop     rsi
0x18002d89a  pop     rbx
0x18002d89b  pop     rbp
0x18002d89c  retn
```
