# DaclContainsPackageSid_(void *)

- ea: `0x180003754`
- end: `0x180003847`
- name: `?DaclContainsPackageSid_@@YAHPEAX@Z`
- size: `243`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003fa4`
- `0x180004540`

## callees

- `0x180003754`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800037bc`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800037bc`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180003824`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180003824`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800037f0`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800037f0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180003781`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180003781`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800037dc`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800037dc`

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
                 - *(_DWORD *)&`DaclContainsPackageSid_'::`2'::AppPackageAuthority.Revision;
              if ( *(_DWORD *)SidIdentifierAuthority->Value == *(_DWORD *)&`DaclContainsPackageSid_'::`2'::AppPackageAuthority.Revision )
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
0x180003754  push    rbp
0x180003756  push    rbx
0x180003757  push    rdi
0x180003758  mov     rbp, rsp
0x18000375b  sub     rsp, 30h
0x18000375f  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180003763  mov     [rbp+pDacl], 0
0x18000376b  lea     r8, [rbp+pDacl]; pDacl
0x18000376f  mov     [rbp+bDaclPresent], 0
0x180003776  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18000377a  mov     [rbp+bDaclDefaulted], 0
0x180003781  call    cs:__imp_GetSecurityDescriptorDacl
0x180003788  nop     dword ptr [rax+rax+00h]
0x18000378d  test    eax, eax
0x18000378f  jz      loc_180003843
0x180003795  mov     rcx, [rbp+pDacl]; pAcl
0x180003799  test    rcx, rcx
0x18000379c  jz      loc_180003843
0x1800037a2  cmp     [rbp+bDaclPresent], 0
0x1800037a6  jz      loc_180003843
0x1800037ac  mov     [rbp+pAce], 0
0x1800037b4  xor     ebx, ebx
0x1800037b6  lea     r8, [rbp+pAce]; pAce
0x1800037ba  mov     edx, ebx; dwAceIndex
0x1800037bc  call    cs:__imp_GetAce
0x1800037c3  nop     dword ptr [rax+rax+00h]
0x1800037c8  test    eax, eax
0x1800037ca  jz      short loc_180003843
0x1800037cc  mov     rax, [rbp+pAce]
0x1800037d0  cmp     byte ptr [rax], 0
0x1800037d3  jnz     short loc_180003817
0x1800037d5  lea     rdi, [rax+8]
0x1800037d9  mov     rcx, rdi; pSid
0x1800037dc  call    cs:__imp_GetSidSubAuthorityCount
0x1800037e3  nop     dword ptr [rax+rax+00h]
0x1800037e8  cmp     byte ptr [rax], 2
0x1800037eb  jb      short loc_180003817
0x1800037ed  mov     rcx, rdi; pSid
0x1800037f0  call    cs:__imp_GetSidIdentifierAuthority
0x1800037f7  nop     dword ptr [rax+rax+00h]
0x1800037fc  mov     edx, [rax]
0x1800037fe  sub     edx, cs:?AppPackageAuthority@?1??DaclContainsPackageSid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B; _SID_IDENTIFIER_AUTHORITY const `DaclContainsPackageSid_(void *)'::`2'::AppPackageAuthority
0x180003804  jnz     short loc_180003813
0x180003806  movzx   edx, word ptr [rax+4]
0x18000380a  movzx   eax, cs:word_180062F64
0x180003811  sub     edx, eax
0x180003813  test    edx, edx
0x180003815  jz      short loc_18000381F
0x180003817  mov     rcx, [rbp+pDacl]
0x18000381b  inc     ebx
0x18000381d  jmp     short loc_1800037B6
0x18000381f  xor     edx, edx; nSubAuthority
0x180003821  mov     rcx, rdi; pSid
0x180003824  call    cs:__imp_GetSidSubAuthority
0x18000382b  nop     dword ptr [rax+rax+00h]
0x180003830  cmp     dword ptr [rax], 2
0x180003833  jnz     short loc_180003817
0x180003835  mov     eax, 1
0x18000383a  add     rsp, 30h
0x18000383e  pop     rdi
0x18000383f  pop     rbx
0x180003840  pop     rbp
0x180003841  retn
0x180003843  xor     eax, eax
0x180003845  jmp     short loc_18000383A
```
