# _lambda_0964cb12d581548b002dfee14ea98ac5_::operator()(void)

- ea: `0x14014eb3c`
- end: `0x14014ee7a`
- name: `??R_lambda_0964cb12d581548b002dfee14ea98ac5_@@QEBAJXZ`
- size: `830`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400875d4`

## callees

- `0x140011a10`
- `0x140011a30`
- `0x140078078`
- `0x14008ac34`
- `0x14008bebc`
- `0x14008c2e4`
- `0x1400936ec`
- `0x1400987b8`
- `0x14014eb3c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14014ecbc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14014ecbc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14014ebad`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14014edf0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14014ebad`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14014edf0`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x14014ed45`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x14014ed45`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x14014ec76`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x14014ec76`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14014ecf1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14014ecf1`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x14014ec24`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x14014ec24`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x14014ed79`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x14014ed79`

## string_xrefs

- `0x14014ebc6`: `shell\lib\logontasks\logontasks.cpp`
- `0x14014ec32`: `shell\lib\logontasks\logontasks.cpp`
- `0x14014ec8f`: `shell\lib\logontasks\logontasks.cpp`
- `0x14014ed0f`: `shell\lib\logontasks\logontasks.cpp`
- `0x14014ed87`: `shell\lib\logontasks\logontasks.cpp`
- `0x14014ee09`: `shell\lib\logontasks\logontasks.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_0964cb12d581548b002dfee14ea98ac5_::operator()(__int64 a1)
{
  unsigned int v1; // ebx
  unsigned int LastError; // ebx
  DWORD NamedSecurityInfoW; // eax
  BOOL v4; // ebx
  const char *v5; // r9
  BOOL v6; // ebx
  const char *v7; // r9
  __int64 v8; // rdx
  unsigned int v9; // eax
  DWORD v10; // eax
  unsigned int v11; // ebx
  unsigned int dwOptions; // [rsp+20h] [rbp-39h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-39h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-39h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-39h]
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+50h] [rbp-9h] BYREF
  __int64 v18; // [rsp+58h] [rbp-1h] BYREF
  __int64 v19; // [rsp+60h] [rbp+7h] BYREF
  PACL pDacl; // [rsp+68h] [rbp+Fh] BYREF
  PACL ppDacl; // [rsp+70h] [rbp+17h] BYREF
  __int64 *p_lpString1; // [rsp+78h] [rbp+1Fh] BYREF
  HKEY phkResult; // [rsp+80h] [rbp+27h] BYREF
  char v24; // [rsp+88h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  WINBOOL bDaclDefaulted; // [rsp+C0h] [rbp+67h] BYREF
  WINBOOL bDaclPresent; // [rsp+C8h] [rbp+6Fh] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor; // [rsp+D0h] [rbp+77h] BYREF
  LPCWCH lpString1; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( (*(_DWORD *)(**(_QWORD **)a1 + 216LL) & 0x3300) == 0 )
  {
    v24 = 1;
    p_lpString1 = &v19;
    v19 = 0;
    phkResult = 0;
    v1 = RegCreateKeyExW(
           HKEY_CURRENT_USER,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSX",
           0,
           0,
           0,
           0xF003Fu,
           0,
           &phkResult,
           0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpString1);
    if ( v1 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x28F7,
                    (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
                    (const char *)v1,
                    dwOptions);
LABEL_22:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v19);
      return LastError;
    }
    ppDacl = 0;
    ppSecurityDescriptor = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &ppSecurityDescriptor,
      0);
    NamedSecurityInfoW = GetNamedSecurityInfoW(
                           L"CURRENT_USER\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSX",
                           SE_REGISTRY_KEY,
                           4u,
                           0,
                           0,
                           &ppDacl,
                           0,
                           &ppSecurityDescriptor);
    if ( NamedSecurityInfoW )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x28FD,
                    (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
                    (const char *)NamedSecurityInfoW,
                    dwOptionsa);
LABEL_21:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppSecurityDescriptor);
      goto LABEL_22;
    }
    p_lpString1 = (__int64 *)&lpString1;
    lpString1 = 0;
    phkResult = 0;
    v24 = 1;
    v4 = ConvertSecurityDescriptorToStringSecurityDescriptorW(ppSecurityDescriptor, 1u, 4u, (LPWSTR *)&phkResult, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_lpString1);
    if ( !v4 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2901,
                    (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
                    v5);
LABEL_20:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpString1);
      goto LABEL_21;
    }
    if ( CompareStringOrdinal(
           lpString1,
           -1,
           L"D:AI(A;OICIID;KA;;;SY)(A;OICIID;KA;;;BA)(A;OICIID;KR;;;RC)(A;CI;KA;;;S-1-15-3-1024-3167453650-624722384-88920"
            "5278-321484983-714554697-3592933102-807660695-1632717421)",
           -1,
           0) != 2 )
    {
      pSecurityDescriptor = 0;
      phkResult = 0;
      p_lpString1 = (__int64 *)&pSecurityDescriptor;
      v24 = 1;
      v6 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
             L"D:AI(A;OICIID;KA;;;SY)(A;OICIID;KA;;;BA)(A;OICIID;KR;;;RC)(A;CI;KA;;;S-1-15-3-1024-3167453650-624722384-889"
              "205278-321484983-714554697-3592933102-807660695-1632717421)",
             1u,
             (PSECURITY_DESCRIPTOR *)&phkResult,
             0);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_lpString1);
      if ( !v6 )
      {
        v8 = 10505;
LABEL_11:
        v9 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v8,
               (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
               v7);
LABEL_12:
        LastError = v9;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pSecurityDescriptor);
        goto LABEL_20;
      }
      bDaclPresent = 0;
      pDacl = 0;
      bDaclDefaulted = 0;
      if ( !GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
      {
        v8 = 10510;
        goto LABEL_11;
      }
      v10 = SetNamedSecurityInfoW(
              (LPWSTR)L"CURRENT_USER\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSX",
              SE_REGISTRY_KEY,
              4u,
              0,
              0,
              pDacl,
              0);
      if ( v10 )
      {
        v9 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x2910,
               (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
               (const char *)v10,
               dwOptionsb);
        goto LABEL_12;
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pSecurityDescriptor);
    }
    p_lpString1 = &v18;
    v18 = 0;
    phkResult = 0;
    v24 = 1;
    v11 = RegCreateKeyExW(
            HKEY_CURRENT_USER,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSX\\WSXPacks",
            0,
            0,
            0,
            0xF003Fu,
            0,
            &phkResult,
            0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpString1);
    if ( v11 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x2916,
                    (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
                    (const char *)v11,
                    dwOptionsc);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v18);
      goto LABEL_20;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v18);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpString1);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ppSecurityDescriptor);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v19);
  }
  return 0;
}

```

## disassembly

```asm
0x14014eb3c  push    rbp
0x14014eb3e  push    rbx
0x14014eb3f  push    rdi
0x14014eb40  push    r14
0x14014eb42  lea     rbp, [rsp-3Fh]
0x14014eb47  sub     rsp, 98h
0x14014eb4e  mov     rax, [rcx]
0x14014eb51  mov     rcx, [rax]
0x14014eb54  test    dword ptr [rcx+0D8h], 3300h
0x14014eb5e  jnz     loc_14014EE6B
0x14014eb64  xor     edi, edi
0x14014eb66  mov     [rbp+57h+var_28], 1
0x14014eb6a  mov     [rsp+0B0h+lpdwDisposition], rdi; lpdwDisposition
0x14014eb6f  lea     rax, [rbp+57h+var_50]
0x14014eb73  mov     [rbp+57h+var_38], rax
0x14014eb77  lea     rdx, aSoftwareMicros_115; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14014eb7e  lea     rax, [rbp+57h+var_30]
0x14014eb82  mov     [rbp+57h+var_50], rdi
0x14014eb86  mov     [rsp+0B0h+phkResult], rax; phkResult
0x14014eb8b  xor     r9d, r9d; lpClass
0x14014eb8e  mov     [rsp+0B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x14014eb93  xor     r8d, r8d; Reserved
0x14014eb96  mov     [rsp+0B0h+samDesired], 0F003Fh; samDesired
0x14014eb9e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14014eba5  mov     [rsp+0B0h+dwOptions], edi; unsigned int
0x14014eba9  mov     [rbp+57h+var_30], rdi
0x14014ebad  call    cs:__imp_RegCreateKeyExW
0x14014ebb3  lea     rcx, [rbp+57h+var_38]
0x14014ebb7  mov     ebx, eax
0x14014ebb9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x14014ebbe  test    ebx, ebx
0x14014ebc0  jz      short loc_14014EBE1
0x14014ebc2  mov     rcx, [rbp+5Fh]; this
0x14014ebc6  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14014ebcd  mov     r9d, ebx; char *
0x14014ebd0  mov     edx, 28F7h; void *
0x14014ebd5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14014ebda  mov     ebx, eax
0x14014ebdc  jmp     loc_14014EE3A
0x14014ebe1  xor     edx, edx
0x14014ebe3  mov     [rbp+57h+ppDacl], rdi
0x14014ebe7  lea     rcx, [rbp+57h+ppSecurityDescriptor]
0x14014ebeb  mov     [rbp+57h+ppSecurityDescriptor], rdi
0x14014ebef  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x14014ebf4  xor     r9d, r9d; ppsidOwner
0x14014ebf7  lea     rax, [rbp+57h+ppSecurityDescriptor]
0x14014ebfb  mov     [rsp+0B0h+phkResult], rax; ppSecurityDescriptor
0x14014ec00  lea     rcx, pObjectName; "CURRENT_USER\\SOFTWARE\\Microsoft\\Wind"...
0x14014ec07  lea     rax, [rbp+57h+ppDacl]
0x14014ec0b  mov     [rsp+0B0h+lpSecurityAttributes], rdi; ppSacl
0x14014ec10  mov     qword ptr [rsp+0B0h+samDesired], rax; ppDacl
0x14014ec15  lea     r14d, [r9+4]
0x14014ec19  mov     qword ptr [rsp+0B0h+dwOptions], rdi; unsigned int
0x14014ec1e  mov     r8d, r14d; SecurityInfo
0x14014ec21  mov     edx, r14d; ObjectType
0x14014ec24  call    cs:__imp_GetNamedSecurityInfoW
0x14014ec2a  test    eax, eax
0x14014ec2c  jz      short loc_14014EC4D
0x14014ec2e  mov     rcx, [rbp+5Fh]; this
0x14014ec32  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14014ec39  mov     r9d, eax; char *
0x14014ec3c  mov     edx, 28FDh; void *
0x14014ec41  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14014ec46  mov     ebx, eax
0x14014ec48  jmp     loc_14014EE31
0x14014ec4d  mov     rcx, [rbp+57h+ppSecurityDescriptor]; SecurityDescriptor
0x14014ec51  lea     rax, [rbp+57h+lpString1]
0x14014ec55  lea     r9, [rbp+57h+var_30]; StringSecurityDescriptor
0x14014ec59  mov     [rbp+57h+var_38], rax
0x14014ec5d  mov     r8d, r14d; SecurityInformation
0x14014ec60  mov     [rbp+57h+lpString1], rdi
0x14014ec64  mov     edx, 1; RequestedStringSDRevision
0x14014ec69  mov     [rbp+57h+var_30], rdi
0x14014ec6d  mov     [rbp+57h+var_28], 1
0x14014ec71  mov     qword ptr [rsp+0B0h+dwOptions], rdi; StringSecurityDescriptorLen
0x14014ec76  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x14014ec7c  lea     rcx, [rbp+57h+var_38]
0x14014ec80  mov     ebx, eax
0x14014ec82  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x14014ec87  test    ebx, ebx
0x14014ec89  jnz     short loc_14014ECA7
0x14014ec8b  mov     rcx, [rbp+5Fh]; this
0x14014ec8f  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14014ec96  mov     edx, 2901h; void *
0x14014ec9b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14014eca0  mov     ebx, eax
0x14014eca2  jmp     loc_14014EE28
0x14014eca7  mov     rcx, [rbp+57h+lpString1]; lpString1
0x14014ecab  lea     r8, StringSecurityDescriptor; "D:AI(A;OICIID;KA;;;SY)(A;OICIID;KA;;;BA"...
0x14014ecb2  or      edx, 0FFFFFFFFh; cchCount1
0x14014ecb5  mov     [rsp+0B0h+dwOptions], edi; bIgnoreCase
0x14014ecb9  mov     r9d, edx; cchCount2
0x14014ecbc  call    cs:__imp_CompareStringOrdinal
0x14014ecc2  cmp     eax, 2
0x14014ecc5  jz      loc_14014EDA9
0x14014eccb  xor     r9d, r9d; SecurityDescriptorSize
0x14014ecce  mov     [rbp+57h+pSecurityDescriptor], rdi
0x14014ecd2  lea     rax, [rbp+57h+pSecurityDescriptor]
0x14014ecd6  mov     [rbp+57h+var_30], rdi
0x14014ecda  lea     r8, [rbp+57h+var_30]; SecurityDescriptor
0x14014ecde  mov     [rbp+57h+var_38], rax
0x14014ece2  lea     rcx, StringSecurityDescriptor; "D:AI(A;OICIID;KA;;;SY)(A;OICIID;KA;;;BA"...
0x14014ece9  mov     [rbp+57h+var_28], 1
0x14014eced  lea     edx, [r9+1]; StringSDRevision
0x14014ecf1  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14014ecf7  lea     rcx, [rbp+57h+var_38]
0x14014ecfb  mov     ebx, eax
0x14014ecfd  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x14014ed02  test    ebx, ebx
0x14014ed04  jnz     short loc_14014ED2B
0x14014ed06  mov     edx, 2909h; void *
0x14014ed0b  mov     rcx, [rbp+5Fh]; this
0x14014ed0f  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14014ed16  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14014ed1b  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x14014ed1f  mov     ebx, eax
0x14014ed21  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x14014ed26  jmp     loc_14014EE28
0x14014ed2b  mov     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x14014ed2f  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x14014ed33  lea     r8, [rbp+57h+pDacl]; pDacl
0x14014ed37  mov     [rbp+57h+bDaclPresent], edi
0x14014ed3a  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x14014ed3e  mov     [rbp+57h+pDacl], rdi
0x14014ed42  mov     [rbp+57h+bDaclDefaulted], edi
0x14014ed45  call    cs:__imp_GetSecurityDescriptorDacl
0x14014ed4b  test    eax, eax
0x14014ed4d  jnz     short loc_14014ED56
0x14014ed4f  mov     edx, 290Eh
0x14014ed54  jmp     short loc_14014ED0B
0x14014ed56  mov     rax, [rbp+57h+pDacl]
0x14014ed5a  lea     rcx, pObjectName; "CURRENT_USER\\SOFTWARE\\Microsoft\\Wind"...
0x14014ed61  mov     [rsp+0B0h+lpSecurityAttributes], rdi; pSacl
0x14014ed66  xor     r9d, r9d; psidOwner
0x14014ed69  mov     qword ptr [rsp+0B0h+samDesired], rax; pDacl
0x14014ed6e  mov     r8d, r14d; SecurityInfo
0x14014ed71  mov     edx, r14d; ObjectType
0x14014ed74  mov     qword ptr [rsp+0B0h+dwOptions], rdi; unsigned int
0x14014ed79  call    cs:__imp_SetNamedSecurityInfoW
0x14014ed7f  test    eax, eax
0x14014ed81  jz      short loc_14014EDA0
0x14014ed83  mov     rcx, [rbp+5Fh]; this
0x14014ed87  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14014ed8e  mov     r9d, eax; char *
0x14014ed91  mov     edx, 2910h; void *
0x14014ed96  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14014ed9b  jmp     loc_14014ED1B
0x14014eda0  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x14014eda4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x14014eda9  mov     [rsp+0B0h+lpdwDisposition], rdi; lpdwDisposition
0x14014edae  lea     rax, [rbp+57h+var_58]
0x14014edb2  mov     [rbp+57h+var_38], rax
0x14014edb6  lea     rdx, aSoftwareMicros_77; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14014edbd  lea     rax, [rbp+57h+var_30]
0x14014edc1  mov     [rbp+57h+var_58], rdi
0x14014edc5  mov     [rsp+0B0h+phkResult], rax; phkResult
0x14014edca  xor     r9d, r9d; lpClass
0x14014edcd  mov     [rsp+0B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x14014edd2  xor     r8d, r8d; Reserved
0x14014edd5  mov     [rsp+0B0h+samDesired], 0F003Fh; samDesired
0x14014eddd  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14014ede4  mov     [rsp+0B0h+dwOptions], edi; unsigned int
0x14014ede8  mov     [rbp+57h+var_30], rdi
0x14014edec  mov     [rbp+57h+var_28], 1
0x14014edf0  call    cs:__imp_RegCreateKeyExW
0x14014edf6  lea     rcx, [rbp+57h+var_38]
0x14014edfa  mov     ebx, eax
0x14014edfc  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x14014ee01  test    ebx, ebx
0x14014ee03  jz      short loc_14014EE47
0x14014ee05  mov     rcx, [rbp+5Fh]; this
0x14014ee09  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14014ee10  mov     r9d, ebx; char *
0x14014ee13  mov     edx, 2916h; void *
0x14014ee18  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14014ee1d  lea     rcx, [rbp+57h+var_58]
0x14014ee21  mov     ebx, eax
0x14014ee23  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14014ee28  lea     rcx, [rbp+57h+lpString1]
0x14014ee2c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x14014ee31  lea     rcx, [rbp+57h+ppSecurityDescriptor]
0x14014ee35  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x14014ee3a  lea     rcx, [rbp+57h+var_50]
0x14014ee3e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14014ee43  mov     eax, ebx
0x14014ee45  jmp     short loc_14014EE6D
0x14014ee47  lea     rcx, [rbp+57h+var_58]
0x14014ee4b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14014ee50  lea     rcx, [rbp+57h+lpString1]
0x14014ee54  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x14014ee59  lea     rcx, [rbp+57h+ppSecurityDescriptor]
0x14014ee5d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x14014ee62  lea     rcx, [rbp+57h+var_50]
0x14014ee66  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14014ee6b  xor     eax, eax
0x14014ee6d  add     rsp, 98h
0x14014ee74  pop     r14
0x14014ee76  pop     rdi
0x14014ee77  pop     rbx
0x14014ee78  pop     rbp
0x14014ee79  retn
```
