# CCheckGroupMembership::InternalIsInAllowedGroups(ushort *,int *)

- ea: `0x180018d48`
- end: `0x18001906c`
- name: `?InternalIsInAllowedGroups@CCheckGroupMembership@@CAJPEAGPEAH@Z`
- size: `804`
- prototype: `__int64 __fastcall(LPCWSTR lpAccountName, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001e864`

## callees

- `0x180018d48`
- `0x180055880`
- `0x180055940`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ea4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018eda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018fa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018fdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018e28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ea4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018eda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018f21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018fa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018fdd`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x180018ed0`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x180018ed0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180018e69`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001900e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180018e69`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001900e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180018fd3`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180018fd3`
- `AUTHZ!AuthzInitializeResourceManager` at `0x180018e9a`
- `AUTHZ!AuthzInitializeResourceManager` at `0x180018e9a`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x180018f17`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x180018f17`
- `AUTHZ!AuthzFreeResourceManager` at `0x180019041`
- `AUTHZ!AuthzFreeResourceManager` at `0x180019041`
- `AUTHZ!AuthzFreeContext` at `0x180019032`
- `AUTHZ!AuthzFreeContext` at `0x180019032`
- `AUTHZ!AuthzGetInformationFromContext` at `0x180018f51`
- `AUTHZ!AuthzGetInformationFromContext` at `0x180018f98`
- `AUTHZ!AuthzGetInformationFromContext` at `0x180018f51`
- `AUTHZ!AuthzGetInformationFromContext` at `0x180018f98`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180018dc6`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180018e1e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180018dc6`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x180018e1e`

## pseudocode

```c
__int64 __fastcall CCheckGroupMembership::InternalIsInAllowedGroups(LPCWSTR lpAccountName, int *a2)
{
  unsigned int v2; // r13d
  unsigned int v5; // ebx
  unsigned __int64 v6; // rax
  void *v7; // rsp
  DWORD *p_cbSid; // rsi
  signed int LastError; // eax
  unsigned int i; // edi
  signed int v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rax
  void *v16; // rsp
  void *v17; // rsp
  DWORD *v18; // rdi
  signed int v19; // eax
  DWORD v20; // r14d
  void *v21; // r15
  signed int v22; // eax
  unsigned int j; // esi
  DWORD cbSid; // [rsp+40h] [rbp+0h] BYREF
  DWORD pSizeRequired; // [rsp+44h] [rbp+4h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp+8h] BYREF
  DWORD cchReferencedDomainName; // [rsp+4Ch] [rbp+Ch] BYREF
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext; // [rsp+50h] [rbp+10h] BYREF
  AUTHZ_RESOURCE_MANAGER_HANDLE phAuthzResourceManager; // [rsp+58h] [rbp+18h] BYREF
  _LUID Luid; // [rsp+60h] [rbp+20h] BYREF
  WCHAR ReferencedDomainName[20]; // [rsp+68h] [rbp+28h] BYREF

  v2 = dword_1800733D8;
  *a2 = 0;
  phAuthzResourceManager = 0;
  hAuthzClientContext = 0;
  Luid = 0;
  pSizeRequired = 0;
  v5 = 0;
  cchReferencedDomainName = 16;
  peUse = 0;
  cbSid = 0;
  if ( LookupAccountNameLocalW(lpAccountName, 0, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    p_cbSid = 0;
  }
  else
  {
    v6 = cbSid + 1 + 15LL;
    if ( v6 <= cbSid + 1 )
      v6 = 0xFFFFFFFFFFFFFF0LL;
    v7 = alloca(v6 & 0xFFFFFFFFFFFFFFF0uLL);
    p_cbSid = &cbSid;
    if ( !LookupAccountNameLocalW(lpAccountName, &cbSid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( v5 )
        goto LABEL_48;
    }
  }
  for ( i = 0; i < v2; ++i )
  {
    if ( EqualSid(p_cbSid, *((PSID *)CCheckGroupMembership::sm_apSid + (int)i)) )
    {
      *a2 = 1;
      goto LABEL_48;
    }
  }
  if ( AuthzInitializeResourceManager(1u, 0, 0, 0, 0, &phAuthzResourceManager) )
    goto LABEL_26;
  v11 = GetLastError();
  v5 = v11;
  if ( v11 > 0 )
    v5 = (unsigned __int16)v11 | 0x80070000;
  if ( !v5 )
  {
LABEL_26:
    if ( AllocateLocallyUniqueId(&Luid) )
      goto LABEL_55;
    v12 = GetLastError();
    v5 = v12;
    if ( v12 > 0 )
      v5 = (unsigned __int16)v12 | 0x80070000;
    if ( !v5 )
    {
LABEL_55:
      if ( AuthzInitializeContextFromSid(0, p_cbSid, phAuthzResourceManager, 0, Luid, 0, &hAuthzClientContext) )
        goto LABEL_56;
      v13 = GetLastError();
      v5 = v13;
      if ( v13 > 0 )
        v5 = (unsigned __int16)v13 | 0x80070000;
      if ( !v5 )
      {
LABEL_56:
        if ( AuthzGetInformationFromContext(hAuthzClientContext, AuthzContextInfoGroupsSids, 0, &pSizeRequired, 0) )
        {
          v18 = 0;
        }
        else
        {
          v14 = pSizeRequired + 1 + 15LL;
          if ( v14 <= pSizeRequired + 1 )
            v14 = 0xFFFFFFFFFFFFFF0LL;
          v15 = v14 & 0xFFFFFFFFFFFFFFF0uLL;
          v16 = alloca(v15);
          v17 = alloca(v15);
          v18 = &cbSid;
          if ( !AuthzGetInformationFromContext(
                  hAuthzClientContext,
                  AuthzContextInfoGroupsSids,
                  pSizeRequired,
                  &pSizeRequired,
                  &cbSid) )
          {
            v19 = GetLastError();
            v5 = v19;
            if ( v19 > 0 )
              v5 = (unsigned __int16)v19 | 0x80070000;
            if ( v5 )
              goto LABEL_48;
          }
        }
        v20 = 0;
LABEL_37:
        if ( v20 < *v18 )
        {
          v21 = *(void **)&v18[4 * v20 + 2];
          if ( IsValidSid(v21) )
            goto LABEL_42;
          v22 = GetLastError();
          v5 = v22;
          if ( v22 > 0 )
            v5 = (unsigned __int16)v22 | 0x80070000;
          if ( !v5 )
          {
LABEL_42:
            for ( j = 0; ; ++j )
            {
              if ( j >= v2 )
              {
                ++v20;
                goto LABEL_37;
              }
              if ( EqualSid(v21, *((PSID *)CCheckGroupMembership::sm_apSid + (int)j)) )
                break;
            }
            *a2 = 1;
          }
        }
      }
    }
  }
LABEL_48:
  if ( hAuthzClientContext )
    AuthzFreeContext(hAuthzClientContext);
  if ( phAuthzResourceManager )
    AuthzFreeResourceManager(phAuthzResourceManager);
  return v5;
}

```

## disassembly

```asm
0x180018d48  push    rbp
0x180018d4a  push    rsi
0x180018d4b  push    rdi
0x180018d4c  push    r12
0x180018d4e  push    r13
0x180018d50  push    r14
0x180018d52  push    r15
0x180018d54  sub     rsp, 0A0h
0x180018d5b  lea     rbp, [rsp+40h]
0x180018d60  mov     [rbp+90h+arg_10], rbx
0x180018d67  mov     rax, cs:__security_cookie
0x180018d6e  xor     rax, rbp
0x180018d71  mov     [rbp+90h+var_40], rax
0x180018d75  mov     r13d, cs:dword_1800733D8
0x180018d7c  lea     rax, [rbp+90h+var_88]
0x180018d80  xor     r15d, r15d
0x180018d83  mov     [rsp+0D0h+peUse], rax; peUse
0x180018d88  lea     rax, [rbp+90h+var_84]
0x180018d8c  mov     [rdx], r15d
0x180018d8f  mov     r12, rdx
0x180018d92  mov     [rsp+0D0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180018d97  lea     r9, [rbp+90h+ReferencedDomainName]; ReferencedDomainName
0x180018d9b  mov     [rbp+90h+phAuthzResourceManager], r15
0x180018d9f  lea     r8, [rbp+90h+cbSid]; cbSid
0x180018da3  mov     [rbp+90h+hAuthzClientContext], r15
0x180018da7  xor     edx, edx; Sid
0x180018da9  mov     qword ptr [rbp+90h+Luid.LowPart], r15
0x180018dad  mov     rdi, rcx
0x180018db0  mov     [rbp+90h+pSizeRequired], r15d
0x180018db4  mov     ebx, r15d
0x180018db7  mov     [rbp+90h+var_84], 10h
0x180018dbe  mov     [rbp+90h+var_88], r15d
0x180018dc2  mov     [rbp+90h+cbSid], r15d
0x180018dc6  call    cs:__imp_LookupAccountNameLocalW
0x180018dcc  mov     rdx, 0FFFFFFFFFFFFFF0h
0x180018dd6  test    eax, eax
0x180018dd8  jnz     short loc_180018E47
0x180018dda  mov     eax, [rbp+90h+cbSid]
0x180018ddd  inc     eax
0x180018ddf  mov     ecx, eax
0x180018de1  add     rax, 0Fh
0x180018de5  cmp     rax, rcx
0x180018de8  ja      short loc_180018DED
0x180018dea  mov     rax, rdx
0x180018ded  and     rax, 0FFFFFFFFFFFFFFF0h
0x180018df1  call    _alloca_probe
0x180018df6  sub     rsp, rax
0x180018df9  lea     r9, [rbp+90h+ReferencedDomainName]; ReferencedDomainName
0x180018dfd  lea     rax, [rbp+90h+var_88]
0x180018e01  mov     rcx, rdi; lpAccountName
0x180018e04  lea     r8, [rbp+90h+cbSid]; cbSid
0x180018e08  mov     [rsp+0D0h+peUse], rax; peUse
0x180018e0d  lea     rsi, [rsp+0D0h+cbSid]
0x180018e12  lea     rax, [rbp+90h+var_84]
0x180018e16  mov     rdx, rsi; Sid
0x180018e19  mov     [rsp+0D0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180018e1e  call    cs:__imp_LookupAccountNameLocalW
0x180018e24  test    eax, eax
0x180018e26  jnz     short loc_180018E4A
0x180018e28  call    cs:__imp_GetLastError
0x180018e2e  mov     ebx, eax
0x180018e30  test    eax, eax
0x180018e32  jle     short loc_180018E3D
0x180018e34  movzx   ebx, ax
0x180018e37  or      ebx, 80070000h
0x180018e3d  test    ebx, ebx
0x180018e3f  jnz     loc_180019029
0x180018e45  jmp     short loc_180018E4A
0x180018e47  mov     rsi, r15
0x180018e4a  mov     edi, r15d
0x180018e4d  mov     r14d, 1
0x180018e53  cmp     edi, r13d
0x180018e56  jnb     short loc_180018E81
0x180018e58  mov     rdx, cs:?sm_apSid@CCheckGroupMembership@@0V?$Array@PEAE@@A; Array<uchar *> CCheckGroupMembership::sm_apSid
0x180018e5f  mov     rcx, rsi; pSid1
0x180018e62  movsxd  rax, edi
0x180018e65  mov     rdx, [rdx+rax*8]; pSid2
0x180018e69  call    cs:__imp_EqualSid
0x180018e6f  test    eax, eax
0x180018e71  jnz     short loc_180018E78
0x180018e73  add     edi, r14d
0x180018e76  jmp     short loc_180018E53
0x180018e78  mov     [r12], r14d
0x180018e7c  jmp     loc_180019029
0x180018e81  lea     rax, [rbp+90h+phAuthzResourceManager]
0x180018e85  xor     r9d, r9d; pfnFreeDynamicGroups
0x180018e88  mov     [rsp+0D0h+peUse], rax; phAuthzResourceManager
0x180018e8d  xor     r8d, r8d; pfnComputeDynamicGroups
0x180018e90  xor     edx, edx; pfnDynamicAccessCheck
0x180018e92  mov     [rsp+0D0h+cchReferencedDomainName], r15; szResourceManagerName
0x180018e97  mov     ecx, r14d; Flags
0x180018e9a  call    cs:__imp_AuthzInitializeResourceManager
0x180018ea0  test    eax, eax
0x180018ea2  jnz     short loc_180018EC6
0x180018ea4  call    cs:__imp_GetLastError
0x180018eaa  mov     ebx, eax
0x180018eac  mov     r14d, 80070000h
0x180018eb2  test    eax, eax
0x180018eb4  jle     short loc_180018EBC
0x180018eb6  movzx   ebx, ax
0x180018eb9  or      ebx, r14d
0x180018ebc  test    ebx, ebx
0x180018ebe  jnz     loc_180019029
0x180018ec4  jmp     short loc_180018ECC
0x180018ec6  mov     r14d, 80070000h
0x180018ecc  lea     rcx, [rbp+90h+Luid]; Luid
0x180018ed0  call    cs:__imp_AllocateLocallyUniqueId
0x180018ed6  test    eax, eax
0x180018ed8  jnz     short loc_180018EF4
0x180018eda  call    cs:__imp_GetLastError
0x180018ee0  mov     ebx, eax
0x180018ee2  test    eax, eax
0x180018ee4  jle     short loc_180018EEC
0x180018ee6  movzx   ebx, ax
0x180018ee9  or      ebx, r14d
0x180018eec  test    ebx, ebx
0x180018eee  jnz     loc_180019029
0x180018ef4  mov     r8, [rbp+90h+phAuthzResourceManager]; hAuthzResourceManager
0x180018ef8  lea     rax, [rbp+90h+hAuthzClientContext]
0x180018efc  mov     [rsp+0D0h+phAuthzClientContext], rax; phAuthzClientContext
0x180018f01  xor     r9d, r9d; pExpirationTime
0x180018f04  mov     rax, qword ptr [rbp+90h+Luid.LowPart]
0x180018f08  mov     rdx, rsi; UserSid
0x180018f0b  mov     [rsp+0D0h+peUse], r15; DynamicGroupArgs
0x180018f10  xor     ecx, ecx; Flags
0x180018f12  mov     [rsp+0D0h+cchReferencedDomainName], rax; Identifier
0x180018f17  call    cs:__imp_AuthzInitializeContextFromSid
0x180018f1d  test    eax, eax
0x180018f1f  jnz     short loc_180018F3B
0x180018f21  call    cs:__imp_GetLastError
0x180018f27  mov     ebx, eax
0x180018f29  test    eax, eax
0x180018f2b  jle     short loc_180018F33
0x180018f2d  movzx   ebx, ax
0x180018f30  or      ebx, r14d
0x180018f33  test    ebx, ebx
0x180018f35  jnz     loc_180019029
0x180018f3b  mov     rcx, [rbp+90h+hAuthzClientContext]; hAuthzClientContext
0x180018f3f  lea     r9, [rbp+90h+pSizeRequired]; pSizeRequired
0x180018f43  xor     r8d, r8d; BufferSize
0x180018f46  mov     [rsp+0D0h+cchReferencedDomainName], r15; Buffer
0x180018f4b  lea     esi, [r8+2]
0x180018f4f  mov     edx, esi; InfoClass
0x180018f51  call    cs:__imp_AuthzGetInformationFromContext
0x180018f57  test    eax, eax
0x180018f59  jnz     short loc_180018FBA
0x180018f5b  mov     r8d, [rbp+90h+pSizeRequired]
0x180018f5f  lea     eax, [r8+1]
0x180018f63  mov     ecx, eax
0x180018f65  add     rax, 0Fh
0x180018f69  cmp     rax, rcx
0x180018f6c  ja      short loc_180018F78
0x180018f6e  mov     rax, 0FFFFFFFFFFFFFF0h
0x180018f78  and     rax, 0FFFFFFFFFFFFFFF0h
0x180018f7c  call    _alloca_probe
0x180018f81  mov     rcx, [rbp+90h+hAuthzClientContext]; hAuthzClientContext
0x180018f85  lea     r9, [rbp+90h+pSizeRequired]; pSizeRequired
0x180018f89  sub     rsp, rax
0x180018f8c  mov     edx, esi; InfoClass
0x180018f8e  lea     rdi, [rsp+0D0h+cbSid]
0x180018f93  mov     [rsp+0D0h+cchReferencedDomainName], rdi; Buffer
0x180018f98  call    cs:__imp_AuthzGetInformationFromContext
0x180018f9e  test    eax, eax
0x180018fa0  jnz     short loc_180018FBD
0x180018fa2  call    cs:__imp_GetLastError
0x180018fa8  mov     ebx, eax
0x180018faa  test    eax, eax
0x180018fac  jle     short loc_180018FB4
0x180018fae  movzx   ebx, ax
0x180018fb1  or      ebx, r14d
0x180018fb4  test    ebx, ebx
0x180018fb6  jnz     short loc_180019029
0x180018fb8  jmp     short loc_180018FBD
0x180018fba  mov     rdi, r15
0x180018fbd  mov     r14d, r15d
0x180018fc0  cmp     r14d, [rdi]
0x180018fc3  jnb     short loc_180019029
0x180018fc5  mov     eax, r14d
0x180018fc8  add     rax, rax
0x180018fcb  mov     r15, [rdi+rax*8+8]
0x180018fd0  mov     rcx, r15; pSid
0x180018fd3  call    cs:__imp_IsValidSid
0x180018fd9  test    eax, eax
0x180018fdb  jnz     short loc_180018FF6
0x180018fdd  call    cs:__imp_GetLastError
0x180018fe3  mov     ebx, eax
0x180018fe5  test    eax, eax
0x180018fe7  jle     short loc_180018FF2
0x180018fe9  movzx   ebx, ax
0x180018fec  or      ebx, 80070000h
0x180018ff2  test    ebx, ebx
0x180018ff4  jnz     short loc_180019029
0x180018ff6  xor     esi, esi
0x180018ff8  cmp     esi, r13d
0x180018ffb  jnb     short loc_18001901C
0x180018ffd  mov     rdx, cs:?sm_apSid@CCheckGroupMembership@@0V?$Array@PEAE@@A; Array<uchar *> CCheckGroupMembership::sm_apSid
0x180019004  mov     rcx, r15; pSid1
0x180019007  movsxd  rax, esi
0x18001900a  mov     rdx, [rdx+rax*8]; pSid2
0x18001900e  call    cs:__imp_EqualSid
0x180019014  test    eax, eax
0x180019016  jnz     short loc_180019021
0x180019018  inc     esi
0x18001901a  jmp     short loc_180018FF8
0x18001901c  inc     r14d
0x18001901f  jmp     short loc_180018FC0
0x180019021  mov     dword ptr [r12], 1
0x180019029  mov     rcx, [rbp+90h+hAuthzClientContext]; hAuthzClientContext
0x18001902d  test    rcx, rcx
0x180019030  jz      short loc_180019038
0x180019032  call    cs:__imp_AuthzFreeContext
0x180019038  mov     rcx, [rbp+90h+phAuthzResourceManager]; hAuthzResourceManager
0x18001903c  test    rcx, rcx
0x18001903f  jz      short loc_180019047
0x180019041  call    cs:__imp_AuthzFreeResourceManager
0x180019047  mov     eax, ebx
0x180019049  mov     rcx, [rbp+90h+var_40]
0x18001904d  xor     rcx, rbp; StackCookie
0x180019050  call    __security_check_cookie
0x180019055  mov     rbx, [rbp+90h+arg_10]
0x18001905c  lea     rsp, [rbp+60h]
0x180019060  pop     r15
0x180019062  pop     r14
0x180019064  pop     r13
0x180019066  pop     r12
0x180019068  pop     rdi
0x180019069  pop     rsi
0x18001906a  pop     rbp
0x18001906b  retn
```
