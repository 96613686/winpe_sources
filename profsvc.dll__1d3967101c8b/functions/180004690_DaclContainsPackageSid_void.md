# DaclContainsPackageSid_(void *)

- ea: `0x180004690`
- end: `0x180004760`
- name: `?DaclContainsPackageSid_@@YAHPEAX@Z`
- size: `208`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003e40`
- `0x180004330`

## callees

- `0x180004690`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800046ee`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800046ee`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180004744`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180004744`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180004716`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x180004716`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800046bd`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800046bd`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180004708`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180004708`

## pseudocode

```c
__int64 __fastcall DaclContainsPackageSid_(void *a1)
{
  struct _ACL *v1; // rcx
  DWORD i; // ebx
  char *v3; // rdi
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  int v5; // edx
  LPVOID pAce; // [rsp+20h] [rbp-10h] BYREF
  WINBOOL bDaclPresent; // [rsp+58h] [rbp+28h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+60h] [rbp+30h] BYREF
  PACL pDacl; // [rsp+68h] [rbp+38h] BYREF

  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  if ( GetSecurityDescriptorDacl(a1, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    v1 = pDacl;
    if ( pDacl )
    {
      if ( bDaclPresent )
      {
        pAce = 0;
        for ( i = 0; GetAce(v1, i, &pAce); ++i )
        {
          if ( !*(_BYTE *)pAce )
          {
            v3 = (char *)pAce + 8;
            if ( *GetSidSubAuthorityCount((char *)pAce + 8) >= 2u )
            {
              SidIdentifierAuthority = GetSidIdentifierAuthority(v3);
              v5 = *(_DWORD *)SidIdentifierAuthority->Value
                 - `DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority[0];
              if ( *(_DWORD *)SidIdentifierAuthority->Value == `DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority[0] )
                v5 = *(unsigned __int16 *)&SidIdentifierAuthority->Value[4] - 3840;
              if ( !v5 && *GetSidSubAuthority(v3, 0) == 2 )
                return 1;
            }
          }
          v1 = pDacl;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004690  push    rbp
0x180004692  push    rbx
0x180004693  push    rdi
0x180004694  mov     rbp, rsp
0x180004697  sub     rsp, 30h
0x18000469b  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18000469f  mov     [rbp+pDacl], 0
0x1800046a7  lea     r8, [rbp+pDacl]; pDacl
0x1800046ab  mov     [rbp+bDaclPresent], 0
0x1800046b2  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800046b6  mov     [rbp+bDaclDefaulted], 0
0x1800046bd  call    cs:__imp_GetSecurityDescriptorDacl
0x1800046c3  test    eax, eax
0x1800046c5  jz      loc_18000475C
0x1800046cb  mov     rcx, [rbp+pDacl]; pAcl
0x1800046cf  test    rcx, rcx
0x1800046d2  jz      loc_18000475C
0x1800046d8  cmp     [rbp+bDaclPresent], 0
0x1800046dc  jz      short loc_18000475C
0x1800046de  mov     [rbp+pAce], 0
0x1800046e6  xor     ebx, ebx
0x1800046e8  lea     r8, [rbp+pAce]; pAce
0x1800046ec  mov     edx, ebx; dwAceIndex
0x1800046ee  call    cs:__imp_GetAce
0x1800046f4  test    eax, eax
0x1800046f6  jz      short loc_18000475C
0x1800046f8  mov     rax, [rbp+pAce]
0x1800046fc  cmp     byte ptr [rax], 0
0x1800046ff  jnz     short loc_180004737
0x180004701  lea     rdi, [rax+8]
0x180004705  mov     rcx, rdi; pSid
0x180004708  call    cs:__imp_GetSidSubAuthorityCount
0x18000470e  cmp     byte ptr [rax], 2
0x180004711  jb      short loc_180004737
0x180004713  mov     rcx, rdi; pSid
0x180004716  call    cs:__imp_GetSidIdentifierAuthority
0x18000471c  mov     edx, [rax]
0x18000471e  sub     edx, cs:?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; _SID_IDENTIFIER_AUTHORITY const `DaclContainsPackageAndLpacCapabilitySid_(void *)'::`2'::AppPackageAuthority ...
0x180004724  jnz     short loc_180004733
0x180004726  movzx   edx, word ptr [rax+4]
0x18000472a  movzx   eax, cs:word_180060090
0x180004731  sub     edx, eax
0x180004733  test    edx, edx
0x180004735  jz      short loc_18000473F
0x180004737  mov     rcx, [rbp+pDacl]
0x18000473b  inc     ebx
0x18000473d  jmp     short loc_1800046E8
0x18000473f  xor     edx, edx; nSubAuthority
0x180004741  mov     rcx, rdi; pSid
0x180004744  call    cs:__imp_GetSidSubAuthority
0x18000474a  cmp     dword ptr [rax], 2
0x18000474d  jnz     short loc_180004737
0x18000474f  mov     eax, 1
0x180004754  add     rsp, 30h
0x180004758  pop     rdi
0x180004759  pop     rbx
0x18000475a  pop     rbp
0x18000475b  retn
0x18000475c  xor     eax, eax
0x18000475e  jmp     short loc_180004754
```
