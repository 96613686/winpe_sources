# SetHiveFileAccessInternal(ushort const *,void *,ushort const *,ulong,int)

- ea: `0x18002dc54`
- end: `0x18002df42`
- name: `?SetHiveFileAccessInternal@@YAJPEBGPEAX0KH@Z`
- size: `750`
- prototype: `__int64 __usercall@<rax>(LPWSTR pObjectName@<rcx>, void *@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180050b70`

## callees

- `0x18000d2c0`
- `0x18000e1a0`
- `0x18002793c`
- `0x18002dc54`
- `0x18002df48`
- `0x180030ad0`
- `0x180031060`
- `0x180037140`
- `0x18003bc70`
- `0x18003c870`
- `0x18004fa3c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002dcc9`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002dd48`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002dcc9`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002dd48`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002ddc6`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002ddc6`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002de08`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002de5d`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002de08`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002de5d`

## string_xrefs

- `0x18002dce6`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002de27`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002debd`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002dedf`: `StrictHiveSecuritySet`

## pseudocode

```c
__int64 __fastcall SetHiveFileAccessInternal(LPWSTR pObjectName, void *a2, const unsigned __int16 *a3, int a4, int a5)
{
  const char *v9; // r9
  __int64 v10; // rdx
  DWORD v12; // ebx
  const char *v13; // r9
  __int64 v14; // rdx
  DWORD v15; // eax
  unsigned int v16; // ebx
  int ProfileListKeyNameFromSid; // eax
  HKEY v18; // rcx
  __int64 v19; // rdx
  unsigned int psidGroup; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v21; // [rsp+40h] [rbp-C0h] BYREF
  PACL NewAcl; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h]
  DWORD cbSid; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v25; // [rsp+5Ch] [rbp-A4h] BYREF
  PACL pDacl[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+70h] [rbp-90h] BYREF
  int v28; // [rsp+A0h] [rbp-60h]
  int v29; // [rsp+A4h] [rbp-5Ch]
  int v30; // [rsp+A8h] [rbp-58h]
  int v31; // [rsp+BCh] [rbp-44h]
  int v32; // [rsp+C0h] [rbp-40h]
  _BYTE *v33; // [rsp+C8h] [rbp-38h]
  int v34; // [rsp+D0h] [rbp-30h]
  int v35; // [rsp+D4h] [rbp-2Ch]
  int v36; // [rsp+D8h] [rbp-28h]
  int v37; // [rsp+ECh] [rbp-14h]
  int v38; // [rsp+F0h] [rbp-10h]
  void *v39; // [rsp+F8h] [rbp-8h]
  _BYTE pSid[80]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v41[80]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  memset_0(&pListOfExplicitEntries, 0, 0x90u);
  cbSid = 68;
  memset_0(pSid, 0, 0x44u);
  if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
  {
    v10 = 81;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v10,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
             v9);
  }
  pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
  pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
  pListOfExplicitEntries.grfInheritance = 3;
  pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
  v25 = 68;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
  memset_0(v41, 0, 0x44u);
  if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, v41, &v25) )
  {
    v10 = 97;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v10,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
             v9);
  }
  v29 = 2;
  v32 = 2;
  v35 = 2;
  v33 = v41;
  v28 = a4;
  v30 = 3;
  v31 = 0;
  v34 = a4;
  v36 = 3;
  v37 = 0;
  v38 = 1;
  v39 = a2;
  pDacl[0] = 0;
  v21 = (unsigned __int16 *)pDacl;
  NewAcl = 0;
  LOBYTE(v23) = 1;
  v12 = SetEntriesInAclW(3u, &pListOfExplicitEntries, 0, &NewAcl);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>>>(&v21);
  if ( v12 )
  {
    v13 = (const char *)v12;
    v14 = 115;
LABEL_11:
    v16 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v14,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
            v13,
            psidGroup);
    goto LABEL_20;
  }
  v15 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 1u, pSid, 0, 0, 0);
  if ( v15 )
  {
    v14 = 125;
LABEL_10:
    v13 = (const char *)v15;
    goto LABEL_11;
  }
  v15 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 0x80000004, 0, 0, pDacl[0], 0);
  if ( v15 )
  {
    v14 = 134;
    goto LABEL_10;
  }
  v21 = 0;
  NewAcl = 0;
  v23 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v21);
  NewAcl = (PACL)-1LL;
  v23 = -1;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(a3, &v21, 0);
  v16 = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid >= 0 )
  {
    ProfileListKeyNameFromSid = SHRegSetBOOL(v18, v21, L"StrictHiveSecuritySet", a5);
    v16 = ProfileListKeyNameFromSid;
    if ( ProfileListKeyNameFromSid >= 0 )
    {
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v21);
      v16 = 0;
      goto LABEL_20;
    }
    v19 = 138;
  }
  else
  {
    v19 = 137;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v19,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
    (const char *)(unsigned int)ProfileListKeyNameFromSid,
    psidGroup);
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v21);
LABEL_20:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(pDacl);
  return v16;
}

```

## disassembly

```asm
0x18002dc54  mov     [rsp-8+arg_8], rbx
0x18002dc59  mov     [rsp-8+arg_18], rsi
0x18002dc5e  push    rbp
0x18002dc5f  push    rdi
0x18002dc60  push    r12
0x18002dc62  push    r14
0x18002dc64  push    r15
0x18002dc66  lea     rbp, [rsp-0B0h]
0x18002dc6e  sub     rsp, 1B0h
0x18002dc75  mov     rax, cs:__security_cookie
0x18002dc7c  xor     rax, rsp
0x18002dc7f  mov     [rbp+0D0h+var_30], rax
0x18002dc86  mov     rsi, r8
0x18002dc89  mov     r14, rdx
0x18002dc8c  mov     rdi, rcx
0x18002dc8f  xor     edx, edx; Val
0x18002dc91  mov     r8d, 90h; Size
0x18002dc97  lea     rcx, [rsp+1D0h+pListOfExplicitEntries]; void *
0x18002dc9c  mov     ebx, r9d
0x18002dc9f  call    memset_0
0x18002dca4  mov     eax, 44h ; 'D'
0x18002dca9  lea     rcx, [rbp+0D0h+pSid]; void *
0x18002dcad  mov     r8d, eax; Size
0x18002dcb0  mov     [rsp+1D0h+cbSid], eax
0x18002dcb4  xor     edx, edx; Val
0x18002dcb6  call    memset_0
0x18002dcbb  xor     edx, edx; DomainSid
0x18002dcbd  lea     r9, [rsp+1D0h+cbSid]; cbSid
0x18002dcc2  lea     r8, [rbp+0D0h+pSid]; pSid
0x18002dcc6  lea     ecx, [rdx+16h]; WellKnownSidType
0x18002dcc9  call    cs:__imp_CreateWellKnownSid
0x18002dcd0  nop     dword ptr [rax+rax+00h]
0x18002dcd5  xor     r15d, r15d
0x18002dcd8  test    eax, eax
0x18002dcda  jnz     short loc_18002DCF7
0x18002dcdc  lea     edx, [rax+51h]; void *
0x18002dcdf  mov     rcx, [rbp+0D8h]; this
0x18002dce6  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002dced  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002dcf2  jmp     loc_18002DF16
0x18002dcf7  mov     r12d, 2
0x18002dcfd  mov     [rsp+1D0h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x18002dd05  lea     rax, [rbp+0D0h+pSid]
0x18002dd09  mov     [rsp+1D0h+pListOfExplicitEntries.grfAccessMode], r12d
0x18002dd0e  xor     edx, edx; Val
0x18002dd10  mov     [rsp+1D0h+pListOfExplicitEntries.grfInheritance], 3
0x18002dd18  lea     rcx, [rbp+0D0h+var_80]; void *
0x18002dd1c  mov     [rbp+0D0h+pListOfExplicitEntries.Trustee.TrusteeForm], r15d
0x18002dd20  lea     r8d, [r12+42h]; Size
0x18002dd25  mov     [rbp+0D0h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x18002dd2c  mov     [rsp+1D0h+var_174], r8d
0x18002dd31  mov     [rbp+0D0h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18002dd35  call    memset_0
0x18002dd3a  xor     edx, edx; DomainSid
0x18002dd3c  lea     r9, [rsp+1D0h+var_174]; cbSid
0x18002dd41  lea     r8, [rbp+0D0h+var_80]; pSid
0x18002dd45  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18002dd48  call    cs:__imp_CreateWellKnownSid
0x18002dd4f  nop     dword ptr [rax+rax+00h]
0x18002dd54  test    eax, eax
0x18002dd56  jnz     short loc_18002DD5D
0x18002dd58  lea     edx, [rax+61h]
0x18002dd5b  jmp     short loc_18002DCDF
0x18002dd5d  mov     [rbp+0D0h+var_12C], r12d
0x18002dd61  lea     rax, [rbp+0D0h+var_80]
0x18002dd65  mov     [rbp+0D0h+var_110], r12d
0x18002dd69  lea     r9, [rsp+1D0h+NewAcl]; NewAcl
0x18002dd6e  mov     [rbp+0D0h+var_FC], r12d
0x18002dd72  lea     rdx, [rsp+1D0h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18002dd77  mov     r12d, 1
0x18002dd7d  mov     [rbp+0D0h+var_108], rax
0x18002dd81  lea     rax, [rsp+1D0h+var_170]
0x18002dd86  mov     [rbp+0D0h+var_130], ebx
0x18002dd89  xor     r8d, r8d; OldAcl
0x18002dd8c  mov     [rbp+0D0h+var_128], 3
0x18002dd93  mov     [rbp+0D0h+var_114], r15d
0x18002dd97  lea     ecx, [r12+2]; cCountOfExplicitEntries
0x18002dd9c  mov     [rbp+0D0h+var_100], ebx
0x18002dd9f  mov     [rbp+0D0h+var_F8], 3
0x18002dda6  mov     [rbp+0D0h+var_E4], r15d
0x18002ddaa  mov     [rbp+0D0h+var_E0], r12d
0x18002ddae  mov     [rbp+0D0h+var_D8], r14
0x18002ddb2  mov     [rsp+1D0h+var_170], r15
0x18002ddb7  mov     [rsp+1D0h+var_190], rax
0x18002ddbc  mov     [rsp+1D0h+NewAcl], r15
0x18002ddc1  mov     byte ptr [rsp+1D0h+var_180], r12b
0x18002ddc6  call    cs:__imp_SetEntriesInAclW
0x18002ddcd  nop     dword ptr [rax+rax+00h]
0x18002ddd2  lea     rcx, [rsp+1D0h+var_190]
0x18002ddd7  mov     ebx, eax
0x18002ddd9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_ACL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>>>(void)
0x18002ddde  test    ebx, ebx
0x18002dde0  jz      short loc_18002DDEC
0x18002dde2  mov     r9d, ebx
0x18002dde5  lea     edx, [r12+72h]
0x18002ddea  jmp     short loc_18002DE20
0x18002ddec  mov     [rsp+1D0h+pSacl], r15; pSacl
0x18002ddf1  lea     r9, [rbp+0D0h+pSid]; psidOwner
0x18002ddf5  mov     [rsp+1D0h+pDacl], r15; pDacl
0x18002ddfa  mov     r8d, r12d; SecurityInfo
0x18002ddfd  mov     edx, r12d; ObjectType
0x18002de00  mov     [rsp+1D0h+psidGroup], r15; unsigned int
0x18002de05  mov     rcx, rdi; pObjectName
0x18002de08  call    cs:__imp_SetNamedSecurityInfoW
0x18002de0f  nop     dword ptr [rax+rax+00h]
0x18002de14  test    eax, eax
0x18002de16  jz      short loc_18002DE3A
0x18002de18  mov     edx, 7Dh ; '}'; void *
0x18002de1d  mov     r9d, eax; char *
0x18002de20  mov     rcx, [rbp+0D8h]; this
0x18002de27  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002de2e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002de33  mov     ebx, eax
0x18002de35  jmp     loc_18002DF0A
0x18002de3a  mov     rax, [rsp+1D0h+var_170]
0x18002de3f  xor     r9d, r9d; psidOwner
0x18002de42  mov     [rsp+1D0h+pSacl], r15; pSacl
0x18002de47  mov     r8d, 80000004h; SecurityInfo
0x18002de4d  mov     [rsp+1D0h+pDacl], rax; pDacl
0x18002de52  mov     edx, r12d; ObjectType
0x18002de55  mov     rcx, rdi; pObjectName
0x18002de58  mov     [rsp+1D0h+psidGroup], r15; int
0x18002de5d  call    cs:__imp_SetNamedSecurityInfoW
0x18002de64  nop     dword ptr [rax+rax+00h]
0x18002de69  test    eax, eax
0x18002de6b  jz      short loc_18002DE74
0x18002de6d  mov     edx, 86h
0x18002de72  jmp     short loc_18002DE1D
0x18002de74  lea     rcx, [rsp+1D0h+var_190]
0x18002de79  mov     [rsp+1D0h+var_190], r15
0x18002de7e  mov     [rsp+1D0h+NewAcl], r15
0x18002de83  mov     [rsp+1D0h+var_180], r15
0x18002de88  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002de8d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002de91  lea     rdx, [rsp+1D0h+var_190]; unsigned __int16 **
0x18002de96  xor     r8d, r8d; int *
0x18002de99  mov     [rsp+1D0h+NewAcl], rax
0x18002de9e  mov     rcx, rsi; lpString1
0x18002dea1  mov     [rsp+1D0h+var_180], rax
0x18002dea6  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x18002deab  mov     ebx, eax
0x18002dead  test    eax, eax
0x18002deaf  jns     short loc_18002DED8
0x18002deb1  mov     edx, 89h; void *
0x18002deb6  mov     rcx, [rbp+0D8h]; this
0x18002debd  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002dec4  mov     r9d, eax; char *
0x18002dec7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002decc  lea     rcx, [rsp+1D0h+var_190]
0x18002ded1  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002ded6  jmp     short loc_18002DF0A
0x18002ded8  mov     r9d, [rbp+0D0h+arg_20]; int
0x18002dedf  lea     r8, aStricthivesecu; "StrictHiveSecuritySet"
0x18002dee6  mov     rdx, [rsp+1D0h+var_190]; unsigned __int16 *
0x18002deeb  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x18002def0  mov     ebx, eax
0x18002def2  test    eax, eax
0x18002def4  jns     short loc_18002DEFD
0x18002def6  mov     edx, 8Ah
0x18002defb  jmp     short loc_18002DEB6
0x18002defd  lea     rcx, [rsp+1D0h+var_190]
0x18002df02  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002df07  mov     ebx, r15d
0x18002df0a  lea     rcx, [rsp+1D0h+var_170]
0x18002df0f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002df14  mov     eax, ebx
0x18002df16  mov     rcx, [rbp+0D0h+var_30]
0x18002df1d  xor     rcx, rsp; StackCookie
0x18002df20  call    __security_check_cookie
0x18002df25  lea     r11, [rsp+1D0h+var_20]
0x18002df2d  mov     rbx, [r11+38h]
0x18002df31  mov     rsi, [r11+48h]
0x18002df35  mov     rsp, r11
0x18002df38  pop     r15
0x18002df3a  pop     r14
0x18002df3c  pop     r12
0x18002df3e  pop     rdi
0x18002df3f  pop     rbp
0x18002df40  retn
```
