# SetProfileDirectorySecurity(ushort const *,ushort const *)

- ea: `0x18004a9f0`
- end: `0x18004ab59`
- name: `?SetProfileDirectorySecurity@@YAJPEBG0@Z`
- size: `361`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002f844`

## callees

- `0x18000d030`
- `0x18000e1a0`
- `0x18002793c`
- `0x18002df48`
- `0x180030ad0`
- `0x180031060`
- `0x18004a9f0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004aac5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18004aac5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004aa6c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004aa6c`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18004ab03`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18004ab03`

## string_xrefs

- `0x18004aa3a`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18004aa83`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`
- `0x18004ab17`: `onecore\ds\security\gina\profile\profsvc\profmap.cpp`

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
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(StringSecurityDescriptor);
  return v4;
}

```

## disassembly

```asm
0x18004a9f0  mov     [rsp-8+arg_0], rbx
0x18004a9f5  mov     [rsp-8+arg_8], rdi
0x18004a9fa  push    rbp
0x18004a9fb  mov     rbp, rsp
0x18004a9fe  sub     rsp, 70h
0x18004aa02  mov     rdi, rcx
0x18004aa05  mov     [rbp+StringSecurityDescriptor], 0
0x18004aa0d  mov     r8, rdx
0x18004aa10  mov     [rbp+var_18], 0
0x18004aa18  lea     rdx, aDPaiAOiciFaSAO; "D:PAI(A;OICI;FA;;;%s)(A;OICI;FA;;;SY)(A"...
0x18004aa1f  mov     [rbp+var_10], 0
0x18004aa27  lea     rcx, [rbp+StringSecurityDescriptor]
0x18004aa2b  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18004aa30  mov     ebx, eax
0x18004aa32  test    eax, eax
0x18004aa34  jns     short loc_18004AA53
0x18004aa36  mov     rcx, [rbp+8]; this
0x18004aa3a  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004aa41  mov     r9d, eax; char *
0x18004aa44  mov     edx, 24h ; '$'; void *
0x18004aa49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004aa4e  jmp     loc_18004AB3B
0x18004aa53  mov     rcx, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x18004aa57  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18004aa5b  xor     r9d, r9d; SecurityDescriptorSize
0x18004aa5e  mov     [rbp+SecurityDescriptor], 0
0x18004aa66  lea     ebx, [r9+1]
0x18004aa6a  mov     edx, ebx; StringSDRevision
0x18004aa6c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004aa73  nop     dword ptr [rax+rax+00h]
0x18004aa78  test    eax, eax
0x18004aa7a  jnz     short loc_18004AA9F
0x18004aa7c  lea     edx, [rbx+2Bh]; void *
0x18004aa7f  mov     rcx, [rbp+8]; this
0x18004aa83  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004aa8a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004aa8f  lea     rcx, [rbp+SecurityDescriptor]
0x18004aa93  mov     ebx, eax
0x18004aa95  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004aa9a  jmp     loc_18004AB3B
0x18004aa9f  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18004aaa3  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18004aaa7  lea     r8, [rbp+pDacl]; pDacl
0x18004aaab  mov     [rbp+bDaclPresent], 0
0x18004aab2  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18004aab6  mov     [rbp+bDaclDefaulted], 0
0x18004aabd  mov     [rbp+pDacl], 0
0x18004aac5  call    cs:__imp_GetSecurityDescriptorDacl
0x18004aacc  nop     dword ptr [rax+rax+00h]
0x18004aad1  test    eax, eax
0x18004aad3  jnz     short loc_18004AADA
0x18004aad5  lea     edx, [rax+34h]
0x18004aad8  jmp     short loc_18004AA7F
0x18004aada  mov     rax, [rbp+pDacl]
0x18004aade  xor     r9d, r9d; psidOwner
0x18004aae1  mov     [rsp+70h+pSacl], 0; pSacl
0x18004aaea  mov     r8d, 80000004h; SecurityInfo
0x18004aaf0  mov     [rsp+70h+var_48], rax; pDacl
0x18004aaf5  mov     edx, ebx; ObjectType
0x18004aaf7  mov     rcx, rdi; pObjectName
0x18004aafa  mov     [rsp+70h+psidGroup], 0; unsigned int
0x18004ab03  call    cs:__imp_SetNamedSecurityInfoW
0x18004ab0a  nop     dword ptr [rax+rax+00h]
0x18004ab0f  test    eax, eax
0x18004ab11  jz      short loc_18004AB30
0x18004ab13  mov     rcx, [rbp+8]; this
0x18004ab17  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004ab1e  mov     r9d, eax; char *
0x18004ab21  mov     edx, 38h ; '8'; void *
0x18004ab26  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004ab2b  jmp     loc_18004AA8F
0x18004ab30  lea     rcx, [rbp+SecurityDescriptor]
0x18004ab34  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004ab39  xor     ebx, ebx
0x18004ab3b  lea     rcx, [rbp+StringSecurityDescriptor]
0x18004ab3f  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004ab44  lea     r11, [rsp+70h+var_s0]
0x18004ab49  mov     eax, ebx
0x18004ab4b  mov     rbx, [r11+10h]
0x18004ab4f  mov     rdi, [r11+18h]
0x18004ab53  mov     rsp, r11
0x18004ab56  pop     rbp
0x18004ab57  retn
```
