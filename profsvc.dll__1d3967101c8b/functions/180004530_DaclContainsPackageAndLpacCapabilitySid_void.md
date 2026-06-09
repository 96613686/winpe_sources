# DaclContainsPackageAndLpacCapabilitySid_(void *)

- ea: `0x180004530`
- end: `0x180004687`
- name: `?DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z`
- size: `343`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003e40`
- `0x180004330`

## callees

- `0x180004530`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180004597`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180004597`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180004628`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180004639`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180004671`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180004628`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180004639`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180004671`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800045cc`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180004602`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800045cc`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180004602`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180004559`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180004559`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800045be`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800045f4`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800045be`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800045f4`

## pseudocode

```c
__int64 __fastcall DaclContainsPackageAndLpacCapabilitySid_(void *a1)
{
  DWORD v1; // ebp
  struct _ACL *v2; // rcx
  int v3; // ebx
  int v4; // esi
  char *v5; // rdi
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  int v7; // ecx
  PSID_IDENTIFIER_AUTHORITY v8; // rax
  int v9; // ecx
  LPVOID pAce; // [rsp+20h] [rbp-38h] BYREF
  WINBOOL bDaclPresent; // [rsp+68h] [rbp+10h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+70h] [rbp+18h] BYREF
  PACL pDacl; // [rsp+78h] [rbp+20h] BYREF

  v1 = 0;
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( GetSecurityDescriptorDacl(a1, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    v2 = pDacl;
    if ( pDacl )
    {
      if ( bDaclPresent )
      {
        v3 = 0;
        pAce = 0;
        v4 = 0;
        while ( GetAce(v2, v1, &pAce) )
        {
          if ( !*(_BYTE *)pAce )
          {
            v5 = (char *)pAce + 8;
            if ( !v3 && *GetSidSubAuthorityCount((char *)pAce + 8) >= 2u )
            {
              SidIdentifierAuthority = GetSidIdentifierAuthority(v5);
              v7 = *(_DWORD *)SidIdentifierAuthority->Value
                 - *(_DWORD *)&`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.Revision;
              if ( *(_DWORD *)SidIdentifierAuthority->Value == *(_DWORD *)&`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.Revision )
                v7 = *(unsigned __int16 *)&SidIdentifierAuthority->Value[4]
                   - *(unsigned __int16 *)&`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.IdentifierAuthority.Value[2];
              if ( !v7 && *GetSidSubAuthority(v5, 0) == 2 )
                v3 = 1;
            }
            if ( !v4 && *GetSidSubAuthorityCount(v5) == 10 )
            {
              v8 = GetSidIdentifierAuthority(v5);
              v9 = *(_DWORD *)v8->Value
                 - *(_DWORD *)&`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.Revision;
              if ( *(_DWORD *)v8->Value == *(_DWORD *)&`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.Revision )
                v9 = *(unsigned __int16 *)&v8->Value[4]
                   - *(unsigned __int16 *)&`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.IdentifierAuthority.Value[2];
              if ( !v9 && *GetSidSubAuthority(v5, 0) == 3 && *GetSidSubAuthority(v5, 1u) == 1024 )
                v4 = 1;
            }
            if ( v3 && v4 )
              return 1;
          }
          v2 = pDacl;
          ++v1;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004530  push    rbx
0x180004532  push    rbp
0x180004533  push    rsi
0x180004534  push    rdi
0x180004535  push    r14
0x180004537  sub     rsp, 30h
0x18000453b  xor     ebp, ebp
0x18000453d  lea     r9, [rsp+58h+bDaclDefaulted]; lpbDaclDefaulted
0x180004542  lea     r8, [rsp+58h+pDacl]; pDacl
0x180004547  mov     [rsp+58h+pDacl], rbp
0x18000454c  lea     rdx, [rsp+58h+bDaclPresent]; lpbDaclPresent
0x180004551  mov     [rsp+58h+bDaclPresent], ebp
0x180004555  mov     [rsp+58h+bDaclDefaulted], ebp
0x180004559  call    cs:__imp_GetSecurityDescriptorDacl
0x18000455f  test    eax, eax
0x180004561  jz      loc_180004683
0x180004567  mov     rcx, [rsp+58h+pDacl]; pAcl
0x18000456c  test    rcx, rcx
0x18000456f  jz      loc_180004683
0x180004575  cmp     [rsp+58h+bDaclPresent], ebp
0x180004579  jz      loc_180004683
0x18000457f  mov     ebx, ebp
0x180004581  mov     [rsp+58h+pAce], rbp
0x180004586  mov     esi, ebp
0x180004588  mov     r14d, 1
0x18000458e  xchg    ax, ax
0x180004590  lea     r8, [rsp+58h+pAce]; pAce
0x180004595  mov     edx, ebp; dwAceIndex
0x180004597  call    cs:__imp_GetAce
0x18000459d  test    eax, eax
0x18000459f  jz      loc_180004683
0x1800045a5  mov     rax, [rsp+58h+pAce]
0x1800045aa  cmp     byte ptr [rax], 0
0x1800045ad  jnz     loc_180004652
0x1800045b3  lea     rdi, [rax+8]
0x1800045b7  test    ebx, ebx
0x1800045b9  jnz     short loc_1800045ED
0x1800045bb  mov     rcx, rdi; pSid
0x1800045be  call    cs:__imp_GetSidSubAuthorityCount
0x1800045c4  cmp     byte ptr [rax], 2
0x1800045c7  jb      short loc_1800045ED
0x1800045c9  mov     rcx, rdi; pSid
0x1800045cc  call    cs:__imp_GetSidIdentifierAuthority
0x1800045d2  mov     ecx, [rax]
0x1800045d4  sub     ecx, dword ptr cs:?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.Revision; _SID_IDENTIFIER_AUTHORITY const `DaclContainsPackageAndLpacCapabilitySid_(void *)'::`2'::AppPackageAuthority ...
0x1800045da  jnz     short loc_1800045E9
0x1800045dc  movzx   ecx, word ptr [rax+4]
0x1800045e0  movzx   eax, word ptr cs:?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.IdentifierAuthority.Value+2; _SID_IDENTIFIER_AUTHORITY const `DaclContainsPackageAndLpacCapabilitySid_(void *)'::`2'::AppPackageAuthority ...
0x1800045e7  sub     ecx, eax
0x1800045e9  test    ecx, ecx
0x1800045eb  jz      short loc_18000466C
0x1800045ed  test    esi, esi
0x1800045ef  jnz     short loc_18000464A
0x1800045f1  mov     rcx, rdi; pSid
0x1800045f4  call    cs:__imp_GetSidSubAuthorityCount
0x1800045fa  cmp     byte ptr [rax], 0Ah
0x1800045fd  jnz     short loc_18000464A
0x1800045ff  mov     rcx, rdi; pSid
0x180004602  call    cs:__imp_GetSidIdentifierAuthority
0x180004608  mov     ecx, [rax]
0x18000460a  sub     ecx, dword ptr cs:?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.Revision; _SID_IDENTIFIER_AUTHORITY const `DaclContainsPackageAndLpacCapabilitySid_(void *)'::`2'::AppPackageAuthority ...
0x180004610  jnz     short loc_18000461F
0x180004612  movzx   ecx, word ptr [rax+4]
0x180004616  movzx   eax, word ptr cs:?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.IdentifierAuthority.Value+2; _SID_IDENTIFIER_AUTHORITY const `DaclContainsPackageAndLpacCapabilitySid_(void *)'::`2'::AppPackageAuthority ...
0x18000461d  sub     ecx, eax
0x18000461f  test    ecx, ecx
0x180004621  jnz     short loc_18000464A
0x180004623  xor     edx, edx; nSubAuthority
0x180004625  mov     rcx, rdi; pSid
0x180004628  call    cs:__imp_GetSidSubAuthority
0x18000462e  cmp     dword ptr [rax], 3
0x180004631  jnz     short loc_18000464A
0x180004633  mov     edx, r14d; nSubAuthority
0x180004636  mov     rcx, rdi; pSid
0x180004639  call    cs:__imp_GetSidSubAuthority
0x18000463f  cmp     dword ptr [rax], 400h
0x180004645  jnz     short loc_18000464A
0x180004647  mov     esi, r14d
0x18000464a  test    ebx, ebx
0x18000464c  jz      short loc_180004652
0x18000464e  test    esi, esi
0x180004650  jnz     short loc_18000465E
0x180004652  mov     rcx, [rsp+58h+pDacl]
0x180004657  inc     ebp
0x180004659  jmp     loc_180004590
0x18000465e  mov     eax, r14d
0x180004661  add     rsp, 30h
0x180004665  pop     r14
0x180004667  pop     rdi
0x180004668  pop     rsi
0x180004669  pop     rbp
0x18000466a  pop     rbx
0x18000466b  retn
0x18000466c  xor     edx, edx; nSubAuthority
0x18000466e  mov     rcx, rdi; pSid
0x180004671  call    cs:__imp_GetSidSubAuthority
0x180004677  cmp     dword ptr [rax], 2
0x18000467a  cmovz   ebx, r14d
0x18000467e  jmp     loc_1800045ED
0x180004683  xor     eax, eax
0x180004685  jmp     short loc_180004661
```
