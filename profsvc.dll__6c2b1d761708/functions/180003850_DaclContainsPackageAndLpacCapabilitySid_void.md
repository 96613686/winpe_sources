# DaclContainsPackageAndLpacCapabilitySid_(void *)

- ea: `0x180003850`
- end: `0x1800039e0`
- name: `?DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z`
- size: `400`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003fa4`
- `0x180004540`

## callees

- `0x180003850`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800038bb`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800038bb`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000396e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180003985`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800039c4`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000396e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180003985`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800039c4`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800038fc`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180003942`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800038fc`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180003942`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180003879`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180003879`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800038e8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000392e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800038e8`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000392e`

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
0x180003850  push    rbx
0x180003852  push    rbp
0x180003853  push    rsi
0x180003854  push    rdi
0x180003855  push    r14
0x180003857  sub     rsp, 30h
0x18000385b  xor     ebp, ebp
0x18000385d  lea     r9, [rsp+58h+bDaclDefaulted]; lpbDaclDefaulted
0x180003862  lea     r8, [rsp+58h+pDacl]; pDacl
0x180003867  mov     [rsp+58h+pDacl], rbp
0x18000386c  lea     rdx, [rsp+58h+bDaclPresent]; lpbDaclPresent
0x180003871  mov     [rsp+58h+bDaclPresent], ebp
0x180003875  mov     [rsp+58h+bDaclDefaulted], ebp
0x180003879  call    cs:__imp_GetSecurityDescriptorDacl
0x180003880  nop     dword ptr [rax+rax+00h]
0x180003885  test    eax, eax
0x180003887  jz      loc_1800039DC
0x18000388d  mov     rcx, [rsp+58h+pDacl]; pAcl
0x180003892  test    rcx, rcx
0x180003895  jz      loc_1800039DC
0x18000389b  cmp     [rsp+58h+bDaclPresent], ebp
0x18000389f  jz      loc_1800039DC
0x1800038a5  mov     ebx, ebp
0x1800038a7  mov     [rsp+58h+pAce], rbp
0x1800038ac  mov     esi, ebp
0x1800038ae  mov     r14d, 1
0x1800038b4  lea     r8, [rsp+58h+pAce]; pAce
0x1800038b9  mov     edx, ebp; dwAceIndex
0x1800038bb  call    cs:__imp_GetAce
0x1800038c2  nop     dword ptr [rax+rax+00h]
0x1800038c7  test    eax, eax
0x1800038c9  jz      loc_1800039DC
0x1800038cf  mov     rax, [rsp+58h+pAce]
0x1800038d4  cmp     byte ptr [rax], 0
0x1800038d7  jnz     loc_1800039A4
0x1800038dd  lea     rdi, [rax+8]
0x1800038e1  test    ebx, ebx
0x1800038e3  jnz     short loc_180003927
0x1800038e5  mov     rcx, rdi; pSid
0x1800038e8  call    cs:__imp_GetSidSubAuthorityCount
0x1800038ef  nop     dword ptr [rax+rax+00h]
0x1800038f4  cmp     byte ptr [rax], 2
0x1800038f7  jb      short loc_180003927
0x1800038f9  mov     rcx, rdi; pSid
0x1800038fc  call    cs:__imp_GetSidIdentifierAuthority
0x180003903  nop     dword ptr [rax+rax+00h]
0x180003908  mov     ecx, [rax]
0x18000390a  sub     ecx, dword ptr cs:?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.Revision; _SID_IDENTIFIER_AUTHORITY const `DaclContainsPackageAndLpacCapabilitySid_(void *)'::`2'::AppPackageAuthority ...
0x180003910  jnz     short loc_18000391F
0x180003912  movzx   ecx, word ptr [rax+4]
0x180003916  movzx   eax, word ptr cs:?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.IdentifierAuthority.Value+2; _SID_IDENTIFIER_AUTHORITY const `DaclContainsPackageAndLpacCapabilitySid_(void *)'::`2'::AppPackageAuthority ...
0x18000391d  sub     ecx, eax
0x18000391f  test    ecx, ecx
0x180003921  jz      loc_1800039BF
0x180003927  test    esi, esi
0x180003929  jnz     short loc_18000399C
0x18000392b  mov     rcx, rdi; pSid
0x18000392e  call    cs:__imp_GetSidSubAuthorityCount
0x180003935  nop     dword ptr [rax+rax+00h]
0x18000393a  cmp     byte ptr [rax], 0Ah
0x18000393d  jnz     short loc_18000399C
0x18000393f  mov     rcx, rdi; pSid
0x180003942  call    cs:__imp_GetSidIdentifierAuthority
0x180003949  nop     dword ptr [rax+rax+00h]
0x18000394e  mov     ecx, [rax]
0x180003950  sub     ecx, dword ptr cs:?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.Revision; _SID_IDENTIFIER_AUTHORITY const `DaclContainsPackageAndLpacCapabilitySid_(void *)'::`2'::AppPackageAuthority ...
0x180003956  jnz     short loc_180003965
0x180003958  movzx   ecx, word ptr [rax+4]
0x18000395c  movzx   eax, word ptr cs:?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.IdentifierAuthority.Value+2; _SID_IDENTIFIER_AUTHORITY const `DaclContainsPackageAndLpacCapabilitySid_(void *)'::`2'::AppPackageAuthority ...
0x180003963  sub     ecx, eax
0x180003965  test    ecx, ecx
0x180003967  jnz     short loc_18000399C
0x180003969  xor     edx, edx; nSubAuthority
0x18000396b  mov     rcx, rdi; pSid
0x18000396e  call    cs:__imp_GetSidSubAuthority
0x180003975  nop     dword ptr [rax+rax+00h]
0x18000397a  cmp     dword ptr [rax], 3
0x18000397d  jnz     short loc_18000399C
0x18000397f  mov     edx, r14d; nSubAuthority
0x180003982  mov     rcx, rdi; pSid
0x180003985  call    cs:__imp_GetSidSubAuthority
0x18000398c  nop     dword ptr [rax+rax+00h]
0x180003991  cmp     dword ptr [rax], 400h
0x180003997  jnz     short loc_18000399C
0x180003999  mov     esi, r14d
0x18000399c  test    ebx, ebx
0x18000399e  jz      short loc_1800039A4
0x1800039a0  test    esi, esi
0x1800039a2  jnz     short loc_1800039B0
0x1800039a4  mov     rcx, [rsp+58h+pDacl]
0x1800039a9  inc     ebp
0x1800039ab  jmp     loc_1800038B4
0x1800039b0  mov     eax, r14d
0x1800039b3  add     rsp, 30h
0x1800039b7  pop     r14
0x1800039b9  pop     rdi
0x1800039ba  pop     rsi
0x1800039bb  pop     rbp
0x1800039bc  pop     rbx
0x1800039bd  retn
0x1800039bf  xor     edx, edx; nSubAuthority
0x1800039c1  mov     rcx, rdi; pSid
0x1800039c4  call    cs:__imp_GetSidSubAuthority
0x1800039cb  nop     dword ptr [rax+rax+00h]
0x1800039d0  cmp     dword ptr [rax], 2
0x1800039d3  cmovz   ebx, r14d
0x1800039d7  jmp     loc_180003927
0x1800039dc  xor     eax, eax
0x1800039de  jmp     short loc_1800039B3
```
