# SetHiveFileAccessInternal(ushort const *,void *,ushort const *,ulong,int)

- ea: `0x18002f224`
- end: `0x18002f4f3`
- name: `?SetHiveFileAccessInternal@@YAJPEBGPEAX0KH@Z`
- size: `719`
- prototype: `__int64 __usercall@<rax>(LPWSTR pObjectName@<rcx>, void *@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18004d854`

## callees

- `0x18000f1b0`
- `0x1800111a0`
- `0x180025254`
- `0x18002d2d8`
- `0x18002db38`
- `0x18002e648`
- `0x18002f224`
- `0x180036a6c`
- `0x18003a730`
- `0x18003b310`
- `0x18004ca14`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002f299`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002f312`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002f299`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002f312`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002f38a`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x18002f38a`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002f3c6`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002f415`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002f3c6`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18002f415`

## string_xrefs

- `0x18002f2b0`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002f3df`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002f46f`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002f491`: `StrictHiveSecuritySet`

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
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>>>((__int64)&v21);
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
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v21);
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
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v21);
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
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v21);
LABEL_20:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)pDacl);
  return v16;
}

```

## disassembly

```asm
0x18002f224  mov     [rsp-8+arg_8], rbx
0x18002f229  mov     [rsp-8+arg_18], rsi
0x18002f22e  push    rbp
0x18002f22f  push    rdi
0x18002f230  push    r12
0x18002f232  push    r14
0x18002f234  push    r15
0x18002f236  lea     rbp, [rsp-0B0h]
0x18002f23e  sub     rsp, 1B0h
0x18002f245  mov     rax, cs:__security_cookie
0x18002f24c  xor     rax, rsp
0x18002f24f  mov     [rbp+0D0h+var_30], rax
0x18002f256  mov     rsi, r8
0x18002f259  mov     r14, rdx
0x18002f25c  mov     rdi, rcx
0x18002f25f  xor     edx, edx; Val
0x18002f261  mov     r8d, 90h; Size
0x18002f267  lea     rcx, [rsp+1D0h+pListOfExplicitEntries]; void *
0x18002f26c  mov     ebx, r9d
0x18002f26f  call    memset_0
0x18002f274  mov     eax, 44h ; 'D'
0x18002f279  lea     rcx, [rbp+0D0h+pSid]; void *
0x18002f27d  mov     r8d, eax; Size
0x18002f280  mov     [rsp+1D0h+cbSid], eax
0x18002f284  xor     edx, edx; Val
0x18002f286  call    memset_0
0x18002f28b  xor     edx, edx; DomainSid
0x18002f28d  lea     r9, [rsp+1D0h+cbSid]; cbSid
0x18002f292  lea     r8, [rbp+0D0h+pSid]; pSid
0x18002f296  lea     ecx, [rdx+16h]; WellKnownSidType
0x18002f299  call    cs:__imp_CreateWellKnownSid
0x18002f29f  xor     r15d, r15d
0x18002f2a2  test    eax, eax
0x18002f2a4  jnz     short loc_18002F2C1
0x18002f2a6  lea     edx, [rax+51h]; void *
0x18002f2a9  mov     rcx, [rbp+0D8h]; this
0x18002f2b0  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002f2b7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002f2bc  jmp     loc_18002F4C8
0x18002f2c1  mov     r12d, 2
0x18002f2c7  mov     [rsp+1D0h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x18002f2cf  lea     rax, [rbp+0D0h+pSid]
0x18002f2d3  mov     [rsp+1D0h+pListOfExplicitEntries.grfAccessMode], r12d
0x18002f2d8  xor     edx, edx; Val
0x18002f2da  mov     [rsp+1D0h+pListOfExplicitEntries.grfInheritance], 3
0x18002f2e2  lea     rcx, [rbp+0D0h+var_80]; void *
0x18002f2e6  mov     [rbp+0D0h+pListOfExplicitEntries.Trustee.TrusteeForm], r15d
0x18002f2ea  lea     r8d, [r12+42h]; Size
0x18002f2ef  mov     [rbp+0D0h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x18002f2f6  mov     [rsp+1D0h+var_174], r8d
0x18002f2fb  mov     [rbp+0D0h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18002f2ff  call    memset_0
0x18002f304  xor     edx, edx; DomainSid
0x18002f306  lea     r9, [rsp+1D0h+var_174]; cbSid
0x18002f30b  lea     r8, [rbp+0D0h+var_80]; pSid
0x18002f30f  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x18002f312  call    cs:__imp_CreateWellKnownSid
0x18002f318  test    eax, eax
0x18002f31a  jnz     short loc_18002F321
0x18002f31c  lea     edx, [rax+61h]
0x18002f31f  jmp     short loc_18002F2A9
0x18002f321  mov     [rbp+0D0h+var_12C], r12d
0x18002f325  lea     rax, [rbp+0D0h+var_80]
0x18002f329  mov     [rbp+0D0h+var_110], r12d
0x18002f32d  lea     r9, [rsp+1D0h+NewAcl]; NewAcl
0x18002f332  mov     [rbp+0D0h+var_FC], r12d
0x18002f336  lea     rdx, [rsp+1D0h+pListOfExplicitEntries]; pListOfExplicitEntries
0x18002f33b  mov     r12d, 1
0x18002f341  mov     [rbp+0D0h+var_108], rax
0x18002f345  lea     rax, [rsp+1D0h+var_170]
0x18002f34a  mov     [rbp+0D0h+var_130], ebx
0x18002f34d  xor     r8d, r8d; OldAcl
0x18002f350  mov     [rbp+0D0h+var_128], 3
0x18002f357  mov     [rbp+0D0h+var_114], r15d
0x18002f35b  lea     ecx, [r12+2]; cCountOfExplicitEntries
0x18002f360  mov     [rbp+0D0h+var_100], ebx
0x18002f363  mov     [rbp+0D0h+var_F8], 3
0x18002f36a  mov     [rbp+0D0h+var_E4], r15d
0x18002f36e  mov     [rbp+0D0h+var_E0], r12d
0x18002f372  mov     [rbp+0D0h+var_D8], r14
0x18002f376  mov     [rsp+1D0h+var_170], r15
0x18002f37b  mov     [rsp+1D0h+var_190], rax
0x18002f380  mov     [rsp+1D0h+NewAcl], r15
0x18002f385  mov     byte ptr [rsp+1D0h+var_180], r12b
0x18002f38a  call    cs:__imp_SetEntriesInAclW
0x18002f390  lea     rcx, [rsp+1D0h+var_190]
0x18002f395  mov     ebx, eax
0x18002f397  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_ACL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_ACL *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_ACL *,_ACL *,0,std::nullptr_t>>>>(void)
0x18002f39c  test    ebx, ebx
0x18002f39e  jz      short loc_18002F3AA
0x18002f3a0  mov     r9d, ebx
0x18002f3a3  lea     edx, [r12+72h]
0x18002f3a8  jmp     short loc_18002F3D8
0x18002f3aa  mov     [rsp+1D0h+pSacl], r15; pSacl
0x18002f3af  lea     r9, [rbp+0D0h+pSid]; psidOwner
0x18002f3b3  mov     [rsp+1D0h+pDacl], r15; pDacl
0x18002f3b8  mov     r8d, r12d; SecurityInfo
0x18002f3bb  mov     edx, r12d; ObjectType
0x18002f3be  mov     [rsp+1D0h+psidGroup], r15; unsigned int
0x18002f3c3  mov     rcx, rdi; pObjectName
0x18002f3c6  call    cs:__imp_SetNamedSecurityInfoW
0x18002f3cc  test    eax, eax
0x18002f3ce  jz      short loc_18002F3F2
0x18002f3d0  mov     edx, 7Dh ; '}'; void *
0x18002f3d5  mov     r9d, eax; char *
0x18002f3d8  mov     rcx, [rbp+0D8h]; this
0x18002f3df  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002f3e6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002f3eb  mov     ebx, eax
0x18002f3ed  jmp     loc_18002F4BC
0x18002f3f2  mov     rax, [rsp+1D0h+var_170]
0x18002f3f7  xor     r9d, r9d; psidOwner
0x18002f3fa  mov     [rsp+1D0h+pSacl], r15; pSacl
0x18002f3ff  mov     r8d, 80000004h; SecurityInfo
0x18002f405  mov     [rsp+1D0h+pDacl], rax; pDacl
0x18002f40a  mov     edx, r12d; ObjectType
0x18002f40d  mov     rcx, rdi; pObjectName
0x18002f410  mov     [rsp+1D0h+psidGroup], r15; int
0x18002f415  call    cs:__imp_SetNamedSecurityInfoW
0x18002f41b  test    eax, eax
0x18002f41d  jz      short loc_18002F426
0x18002f41f  mov     edx, 86h
0x18002f424  jmp     short loc_18002F3D5
0x18002f426  lea     rcx, [rsp+1D0h+var_190]
0x18002f42b  mov     [rsp+1D0h+var_190], r15
0x18002f430  mov     [rsp+1D0h+NewAcl], r15
0x18002f435  mov     [rsp+1D0h+var_180], r15
0x18002f43a  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002f43f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002f443  lea     rdx, [rsp+1D0h+var_190]; unsigned __int16 **
0x18002f448  xor     r8d, r8d; int *
0x18002f44b  mov     [rsp+1D0h+NewAcl], rax
0x18002f450  mov     rcx, rsi; lpString1
0x18002f453  mov     [rsp+1D0h+var_180], rax
0x18002f458  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x18002f45d  mov     ebx, eax
0x18002f45f  test    eax, eax
0x18002f461  jns     short loc_18002F48A
0x18002f463  mov     edx, 89h; void *
0x18002f468  mov     rcx, [rbp+0D8h]; this
0x18002f46f  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002f476  mov     r9d, eax; char *
0x18002f479  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f47e  lea     rcx, [rsp+1D0h+var_190]
0x18002f483  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002f488  jmp     short loc_18002F4BC
0x18002f48a  mov     r9d, [rbp+0D0h+arg_20]; int
0x18002f491  lea     r8, aStricthivesecu; "StrictHiveSecuritySet"
0x18002f498  mov     rdx, [rsp+1D0h+var_190]; unsigned __int16 *
0x18002f49d  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x18002f4a2  mov     ebx, eax
0x18002f4a4  test    eax, eax
0x18002f4a6  jns     short loc_18002F4AF
0x18002f4a8  mov     edx, 8Ah
0x18002f4ad  jmp     short loc_18002F468
0x18002f4af  lea     rcx, [rsp+1D0h+var_190]
0x18002f4b4  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002f4b9  mov     ebx, r15d
0x18002f4bc  lea     rcx, [rsp+1D0h+var_170]
0x18002f4c1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002f4c6  mov     eax, ebx
0x18002f4c8  mov     rcx, [rbp+0D0h+var_30]
0x18002f4cf  xor     rcx, rsp; StackCookie
0x18002f4d2  call    __security_check_cookie
0x18002f4d7  lea     r11, [rsp+1D0h+var_20]
0x18002f4df  mov     rbx, [r11+38h]
0x18002f4e3  mov     rsi, [r11+48h]
0x18002f4e7  mov     rsp, r11
0x18002f4ea  pop     r15
0x18002f4ec  pop     r14
0x18002f4ee  pop     r12
0x18002f4f0  pop     rdi
0x18002f4f1  pop     rbp
0x18002f4f2  retn
```
