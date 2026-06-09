# SetProfileDirectorySecurity(ushort const *,ushort const *)

- ea: `0x1800487e8`
- end: `0x18004893e`
- name: `?SetProfileDirectorySecurity@@YAJPEBG0@Z`
- size: `342`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800393e4`

## callees

- `0x180010f30`
- `0x1800111a0`
- `0x180025254`
- `0x18002d2d8`
- `0x18002db38`
- `0x18002e648`
- `0x1800487e8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800488b7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800488b7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180048864`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180048864`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800488ef`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800488ef`

## string_xrefs

- `0x180048832`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x180048875`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x1800488fd`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`

## pseudocode

```c
__int64 __fastcall SetProfileDirectorySecurity(LPWSTR pObjectName, const unsigned __int16 *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  const char *v5; // r9
  __int64 v6; // rdx
  int LastError; // eax
  DWORD v8; // eax
  int psidGroup; // [rsp+20h] [rbp-50h]
  unsigned int psidGroupa; // [rsp+20h] [rbp-50h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-30h] BYREF
  PACL pDacl; // [rsp+48h] [rbp-28h] BYREF
  LPCWSTR StringSecurityDescriptor[4]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  WINBOOL bDaclDefaulted; // [rsp+90h] [rbp+20h] BYREF
  WINBOOL bDaclPresent; // [rsp+98h] [rbp+28h] BYREF

  memset(StringSecurityDescriptor, 0, 24);
  v3 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
         StringSecurityDescriptor,
         L"D:PAI(A;OICI;FA;;;%s)(A;OICI;FA;;;SY)(A;OICI;FA;;;BA)",
         a2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    SecurityDescriptor = 0;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor[0], 1u, &SecurityDescriptor, 0) )
    {
      bDaclPresent = 0;
      bDaclDefaulted = 0;
      pDacl = 0;
      if ( GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      {
        v8 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 0x80000004, 0, 0, pDacl, 0);
        if ( !v8 )
        {
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&SecurityDescriptor);
          v4 = 0;
          goto LABEL_12;
        }
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x38,
                      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
                      (const char *)v8,
                      psidGroupa);
        goto LABEL_6;
      }
      v6 = 52;
    }
    else
    {
      v6 = 44;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v6,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
                  v5);
LABEL_6:
    v4 = LastError;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&SecurityDescriptor);
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x24,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmap.cpp",
    (const char *)(unsigned int)v3,
    psidGroup);
LABEL_12:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)StringSecurityDescriptor);
  return v4;
}

```

## disassembly

```asm
0x1800487e8  mov     [rsp-8+arg_0], rbx
0x1800487ed  mov     [rsp-8+arg_8], rdi
0x1800487f2  push    rbp
0x1800487f3  mov     rbp, rsp
0x1800487f6  sub     rsp, 70h
0x1800487fa  mov     rdi, rcx
0x1800487fd  mov     [rbp+StringSecurityDescriptor], 0
0x180048805  mov     r8, rdx
0x180048808  mov     [rbp+var_18], 0
0x180048810  lea     rdx, aDPaiAOiciFaSAO; "D:PAI(A;OICI;FA;;;%s)(A;OICI;FA;;;SY)(A"...
0x180048817  mov     [rbp+var_10], 0
0x18004881f  lea     rcx, [rbp+StringSecurityDescriptor]
0x180048823  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180048828  mov     ebx, eax
0x18004882a  test    eax, eax
0x18004882c  jns     short loc_18004884B
0x18004882e  mov     rcx, [rbp+8]; this
0x180048832  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x180048839  mov     r9d, eax; char *
0x18004883c  mov     edx, 24h ; '$'; void *
0x180048841  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048846  jmp     loc_180048921
0x18004884b  mov     rcx, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18004884f  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180048853  xor     r9d, r9d; SecurityDescriptorSize
0x180048856  mov     [rbp+SecurityDescriptor], 0
0x18004885e  lea     ebx, [r9+1]
0x180048862  mov     edx, ebx; StringSDRevision
0x180048864  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004886a  test    eax, eax
0x18004886c  jnz     short loc_180048891
0x18004886e  lea     edx, [rbx+2Bh]; void *
0x180048871  mov     rcx, [rbp+8]; this
0x180048875  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004887c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180048881  lea     rcx, [rbp+SecurityDescriptor]
0x180048885  mov     ebx, eax
0x180048887  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004888c  jmp     loc_180048921
0x180048891  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x180048895  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180048899  lea     r8, [rbp+pDacl]; pDacl
0x18004889d  mov     [rbp+bDaclPresent], 0
0x1800488a4  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800488a8  mov     [rbp+bDaclDefaulted], 0
0x1800488af  mov     [rbp+pDacl], 0
0x1800488b7  call    cs:__imp_GetSecurityDescriptorDacl
0x1800488bd  test    eax, eax
0x1800488bf  jnz     short loc_1800488C6
0x1800488c1  lea     edx, [rax+34h]
0x1800488c4  jmp     short loc_180048871
0x1800488c6  mov     rax, [rbp+pDacl]
0x1800488ca  xor     r9d, r9d; psidOwner
0x1800488cd  mov     [rsp+70h+pSacl], 0; pSacl
0x1800488d6  mov     r8d, 80000004h; SecurityInfo
0x1800488dc  mov     [rsp+70h+var_48], rax; pDacl
0x1800488e1  mov     edx, ebx; ObjectType
0x1800488e3  mov     rcx, rdi; pObjectName
0x1800488e6  mov     [rsp+70h+psidGroup], 0; unsigned int
0x1800488ef  call    cs:__imp_SetNamedSecurityInfoW
0x1800488f5  test    eax, eax
0x1800488f7  jz      short loc_180048916
0x1800488f9  mov     rcx, [rbp+8]; this
0x1800488fd  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x180048904  mov     r9d, eax; char *
0x180048907  mov     edx, 38h ; '8'; void *
0x18004890c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180048911  jmp     loc_180048881
0x180048916  lea     rcx, [rbp+SecurityDescriptor]
0x18004891a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004891f  xor     ebx, ebx
0x180048921  lea     rcx, [rbp+StringSecurityDescriptor]
0x180048925  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004892a  lea     r11, [rsp+70h+var_s0]
0x18004892f  mov     eax, ebx
0x180048931  mov     rbx, [r11+10h]
0x180048935  mov     rdi, [r11+18h]
0x180048939  mov     rsp, r11
0x18004893c  pop     rbp
0x18004893d  retn
```
