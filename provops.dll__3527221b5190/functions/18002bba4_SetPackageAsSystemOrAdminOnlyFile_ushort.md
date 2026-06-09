# SetPackageAsSystemOrAdminOnlyFile(ushort *)

- ea: `0x18002bba4`
- end: `0x18002bdd3`
- name: `?SetPackageAsSystemOrAdminOnlyFile@@YAJPEAG@Z`
- size: `559`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002b410`

## callees

- `0x180007654`
- `0x180007674`
- `0x180017914`
- `0x18002bba4`
- `0x180033e9a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd08`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bd1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bd1b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002bbd1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002bc07`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002bbd1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002bc07`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bc63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bd13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bd57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bda2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bdab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bdb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bc63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bd13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bd57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bda2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bdab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002bdb7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002bc41`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002bc7a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002bc41`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002bc7a`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002bd85`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002bd85`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002bce9`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002bce9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SetPackageAsSystemOrAdminOnlyFile(LPWSTR pObjectName)
{
  WCHAR *v1; // rbx
  HLOCAL v2; // rsi
  unsigned int v3; // ebx
  HLOCAL v4; // rdi
  const char *v5; // r9
  __int64 v6; // rdx
  DWORD v7; // r12d
  PACL v8; // r13
  HLOCAL v9; // r15
  DWORD LastError; // ebx
  const char *v11; // r9
  __int64 v12; // rdx
  DWORD v13; // eax
  unsigned int psidGroup; // [rsp+20h] [rbp-89h]
  PACL NewAcl; // [rsp+48h] [rbp-61h] BYREF
  char v17; // [rsp+50h] [rbp-59h]
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+60h] [rbp-49h] BYREF
  int v19; // [rsp+90h] [rbp-19h]
  __int64 v20; // [rsp+94h] [rbp-15h]
  int v21; // [rsp+ACh] [rbp+3h]
  int v22; // [rsp+B0h] [rbp+7h]
  HLOCAL v23; // [rsp+B8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  SIZE_T uBytes; // [rsp+118h] [rbp+6Fh] BYREF
  DWORD cbSid; // [rsp+120h] [rbp+77h] BYREF
  HLOCAL hMem; // [rsp+128h] [rbp+7Fh]

  v1 = pObjectName;
  cbSid = 68;
  LODWORD(uBytes) = 68;
  v2 = LocalAlloc(0, 0x44u);
  if ( v2 )
  {
    v4 = LocalAlloc(0, (unsigned int)uBytes);
    if ( !v4 )
    {
      v3 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecopier.cpp",
        (const char *)0x8007000ELL,
        psidGroup);
LABEL_24:
      LocalFree(v2);
      return v3;
    }
    if ( CreateWellKnownSid(WinLocalSystemSid, 0, v2, &cbSid) )
    {
      if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v4, (DWORD *)&uBytes) )
      {
        memset_0(&pListOfExplicitEntries.grfAccessMode, 0, 0x5Cu);
        pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
        *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
        pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
        v19 = 0x10000000;
        pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
        pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)v2;
        v20 = 2;
        v21 = 0;
        v22 = 2;
        v23 = v4;
        hMem = 0;
        NewAcl = 0;
        v17 = 1;
        v7 = SetEntriesInAclW(2u, &pListOfExplicitEntries, 0, &NewAcl);
        if ( v17 )
        {
          v8 = NewAcl;
          v9 = hMem;
          if ( hMem )
          {
            LastError = GetLastError();
            LocalFree(v9);
            SetLastError(LastError);
            v1 = pObjectName;
          }
          hMem = v8;
        }
        if ( v7 )
        {
          v11 = (const char *)v7;
          v12 = 48;
        }
        else
        {
          v13 = SetNamedSecurityInfoW(v1, SE_FILE_OBJECT, 0x80000004, 0, 0, (PACL)hMem, 0);
          if ( !v13 )
          {
            if ( hMem )
              LocalFree(hMem);
            LocalFree(v4);
            v3 = 0;
            goto LABEL_24;
          }
          v11 = (const char *)v13;
          v12 = 57;
        }
        v3 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v12,
               (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecopier.cpp",
               v11,
               psidGroup);
        if ( hMem )
          LocalFree(hMem);
        goto LABEL_8;
      }
      v6 = 28;
    }
    else
    {
      v6 = 26;
    }
    v3 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)v6,
           (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecopier.cpp",
           v5);
LABEL_8:
    LocalFree(v4);
    goto LABEL_24;
  }
  v3 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x15,
    (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecopier.cpp",
    (const char *)0x8007000ELL,
    psidGroup);
  return v3;
}

```

## disassembly

```asm
0x18002bba4  mov     [rsp-8+arg_0], rcx
0x18002bba9  push    rbp
0x18002bbaa  push    rbx
0x18002bbab  push    rsi
0x18002bbac  push    rdi
0x18002bbad  push    r12
0x18002bbaf  push    r13
0x18002bbb1  push    r14
0x18002bbb3  push    r15
0x18002bbb5  lea     rbp, [rsp-1Fh]
0x18002bbba  sub     rsp, 0C8h
0x18002bbc1  mov     edx, 44h ; 'D'; uBytes
0x18002bbc6  mov     rbx, rcx
0x18002bbc9  xor     ecx, ecx; uFlags
0x18002bbcb  mov     [rbp+57h+cbSid], edx
0x18002bbce  mov     dword ptr [rbp+57h+uBytes], edx
0x18002bbd1  call    cs:__imp_LocalAlloc
0x18002bbd7  xor     r14d, r14d
0x18002bbda  mov     rsi, rax
0x18002bbdd  test    rax, rax
0x18002bbe0  jnz     short loc_18002BC02
0x18002bbe2  mov     rcx, [rbp+5Fh]; this
0x18002bbe6  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x18002bbed  mov     ebx, 8007000Eh
0x18002bbf2  lea     edx, [rax+15h]; void *
0x18002bbf5  mov     r9d, ebx; char *
0x18002bbf8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bbfd  jmp     loc_18002BDBD
0x18002bc02  mov     edx, dword ptr [rbp+57h+uBytes]; uBytes
0x18002bc05  xor     ecx, ecx; uFlags
0x18002bc07  call    cs:__imp_LocalAlloc
0x18002bc0d  mov     rdi, rax
0x18002bc10  test    rax, rax
0x18002bc13  jnz     short loc_18002BC35
0x18002bc15  mov     rcx, [rbp+5Fh]; this
0x18002bc19  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x18002bc20  mov     ebx, 8007000Eh
0x18002bc25  lea     edx, [rax+18h]; void *
0x18002bc28  mov     r9d, ebx; char *
0x18002bc2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bc30  jmp     loc_18002BDB4
0x18002bc35  xor     edx, edx; DomainSid
0x18002bc37  lea     r9, [rbp+57h+cbSid]; cbSid
0x18002bc3b  mov     r8, rsi; pSid
0x18002bc3e  lea     ecx, [rdx+16h]; WellKnownSidType
0x18002bc41  call    cs:__imp_CreateWellKnownSid
0x18002bc47  test    eax, eax
0x18002bc49  jnz     short loc_18002BC6E
0x18002bc4b  lea     edx, [rax+1Ah]; void *
0x18002bc4e  mov     rcx, [rbp+5Fh]; this
0x18002bc52  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x18002bc59  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002bc5e  mov     ebx, eax
0x18002bc60  mov     rcx, rdi; hMem
0x18002bc63  call    cs:__imp_LocalFree
0x18002bc69  jmp     loc_18002BDB4
0x18002bc6e  xor     edx, edx; DomainSid
0x18002bc70  lea     r9, [rbp+57h+uBytes]; cbSid
0x18002bc74  mov     r8, rdi; pSid
0x18002bc77  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18002bc7a  call    cs:__imp_CreateWellKnownSid
0x18002bc80  test    eax, eax
0x18002bc82  jnz     short loc_18002BC89
0x18002bc84  lea     edx, [rax+1Ch]
0x18002bc87  jmp     short loc_18002BC4E
0x18002bc89  xor     edx, edx; Val
0x18002bc8b  lea     rcx, [rbp+57h+pListOfExplicitEntries.grfAccessMode]; void *
0x18002bc8f  lea     r8d, [rdx+5Ch]; Size
0x18002bc93  call    memset_0
0x18002bc98  mov     ecx, 2; cCountOfExplicitEntries
0x18002bc9d  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], r14d
0x18002bca1  mov     eax, 10000000h
0x18002bca6  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfAccessMode], rcx
0x18002bcaa  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], eax
0x18002bcad  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x18002bcb1  mov     [rbp+57h+var_70], eax
0x18002bcb4  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18002bcb8  lea     rax, [rbp+57h+hMem]
0x18002bcbc  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x18002bcc3  xor     r8d, r8d; OldAcl
0x18002bcc6  mov     [rbp+57h+var_C0], rax
0x18002bcca  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rsi
0x18002bcce  mov     [rbp+57h+var_6C], rcx
0x18002bcd2  mov     [rbp+57h+var_54], r14d
0x18002bcd6  mov     [rbp+57h+var_50], ecx
0x18002bcd9  mov     [rbp+57h+var_48], rdi
0x18002bcdd  mov     [rbp+57h+hMem], r14
0x18002bce1  mov     [rbp+57h+NewAcl], r14
0x18002bce5  mov     [rbp+57h+var_B0], 1
0x18002bce9  call    cs:__imp_SetEntriesInAclW
0x18002bcef  mov     r12d, eax
0x18002bcf2  cmp     [rbp+57h+var_B0], r14b
0x18002bcf6  jz      short loc_18002BD2B
0x18002bcf8  mov     r14, [rbp+57h+var_C0]
0x18002bcfc  mov     r13, [rbp+57h+NewAcl]
0x18002bd00  mov     r15, [r14]
0x18002bd03  test    r15, r15
0x18002bd06  jz      short loc_18002BD25
0x18002bd08  call    cs:__imp_GetLastError
0x18002bd0e  mov     rcx, r15; hMem
0x18002bd11  mov     ebx, eax
0x18002bd13  call    cs:__imp_LocalFree
0x18002bd19  mov     ecx, ebx; dwErrCode
0x18002bd1b  call    cs:__imp_SetLastError
0x18002bd21  mov     rbx, [rbp+57h+arg_0]
0x18002bd25  mov     [r14], r13
0x18002bd28  xor     r14d, r14d
0x18002bd2b  test    r12d, r12d
0x18002bd2e  jz      short loc_18002BD62
0x18002bd30  mov     r9d, r12d; char *
0x18002bd33  mov     edx, 30h ; '0'; void *
0x18002bd38  mov     rcx, [rbp+5Fh]; this
0x18002bd3c  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x18002bd43  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002bd48  mov     rcx, [rbp+57h+hMem]; hMem
0x18002bd4c  mov     ebx, eax
0x18002bd4e  test    rcx, rcx
0x18002bd51  jz      loc_18002BC60
0x18002bd57  call    cs:__imp_LocalFree
0x18002bd5d  jmp     loc_18002BC60
0x18002bd62  mov     rax, [rbp+57h+hMem]
0x18002bd66  xor     r9d, r9d; psidOwner
0x18002bd69  mov     [rsp+100h+pSacl], r14; pSacl
0x18002bd6e  mov     r8d, 80000004h; SecurityInfo
0x18002bd74  mov     [rsp+100h+pDacl], rax; pDacl
0x18002bd79  mov     rcx, rbx; pObjectName
0x18002bd7c  mov     [rsp+100h+psidGroup], r14; psidGroup
0x18002bd81  lea     edx, [r9+1]; ObjectType
0x18002bd85  call    cs:__imp_SetNamedSecurityInfoW
0x18002bd8b  test    eax, eax
0x18002bd8d  jz      short loc_18002BD99
0x18002bd8f  mov     r9d, eax
0x18002bd92  mov     edx, 39h ; '9'
0x18002bd97  jmp     short loc_18002BD38
0x18002bd99  mov     rcx, [rbp+57h+hMem]; hMem
0x18002bd9d  test    rcx, rcx
0x18002bda0  jz      short loc_18002BDA8
0x18002bda2  call    cs:__imp_LocalFree
0x18002bda8  mov     rcx, rdi; hMem
0x18002bdab  call    cs:__imp_LocalFree
0x18002bdb1  mov     ebx, r14d
0x18002bdb4  mov     rcx, rsi; hMem
0x18002bdb7  call    cs:__imp_LocalFree
0x18002bdbd  mov     eax, ebx
0x18002bdbf  add     rsp, 0C8h
0x18002bdc6  pop     r15
0x18002bdc8  pop     r14
0x18002bdca  pop     r13
0x18002bdcc  pop     r12
0x18002bdce  pop     rdi
0x18002bdcf  pop     rsi
0x18002bdd0  pop     rbx
0x18002bdd1  pop     rbp
0x18002bdd2  retn
```
