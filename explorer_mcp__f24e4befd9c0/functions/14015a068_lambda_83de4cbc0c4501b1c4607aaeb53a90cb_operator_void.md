# _lambda_83de4cbc0c4501b1c4607aaeb53a90cb_::operator()(void)

- ea: `0x14015a068`
- end: `0x14015a3d7`
- name: `??R_lambda_83de4cbc0c4501b1c4607aaeb53a90cb_@@QEBAJXZ`
- size: `879`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14008cff8`

## callees

- `0x1400485bc`
- `0x1400485e0`
- `0x14007bf4c`
- `0x140090258`
- `0x1400911c0`
- `0x14009153c`
- `0x140098dc4`
- `0x14009de4c`
- `0x14015a068`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14015a1fa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14015a1fa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14015a0d9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14015a346`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14015a0d9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14015a346`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x14015a28f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x14015a28f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x14015a1ae`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x14015a1ae`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14015a235`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14015a235`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x14015a156`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x14015a156`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x14015a2c9`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x14015a2c9`

## string_xrefs

- `0x14015a0f8`: `shell\lib\logontasks\logontasks.cpp`
- `0x14015a16a`: `shell\lib\logontasks\logontasks.cpp`
- `0x14015a1cd`: `shell\lib\logontasks\logontasks.cpp`
- `0x14015a259`: `shell\lib\logontasks\logontasks.cpp`
- `0x14015a2dd`: `shell\lib\logontasks\logontasks.cpp`
- `0x14015a365`: `shell\lib\logontasks\logontasks.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_83de4cbc0c4501b1c4607aaeb53a90cb_::operator()(__int64 a1)
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
                    (void *)0x2916,
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
                    (void *)0x291C,
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
                    (void *)0x2920,
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
        v8 = 10536;
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
        v8 = 10541;
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
               (void *)0x292F,
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
                    (void *)0x2935,
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
0x14015a068  push    rbp
0x14015a06a  push    rbx
0x14015a06b  push    rdi
0x14015a06c  push    r14
0x14015a06e  lea     rbp, [rsp-3Fh]
0x14015a073  sub     rsp, 98h
0x14015a07a  mov     rax, [rcx]
0x14015a07d  mov     rcx, [rax]
0x14015a080  test    dword ptr [rcx+0D8h], 3300h
0x14015a08a  jnz     loc_14015A3C7
0x14015a090  xor     edi, edi
0x14015a092  mov     [rbp+57h+var_28], 1
0x14015a096  mov     [rsp+0B0h+lpdwDisposition], rdi; lpdwDisposition
0x14015a09b  lea     rax, [rbp+57h+var_50]
0x14015a09f  mov     [rbp+57h+var_38], rax
0x14015a0a3  lea     rdx, aSoftwareMicros_116; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14015a0aa  lea     rax, [rbp+57h+var_30]
0x14015a0ae  mov     [rbp+57h+var_50], rdi
0x14015a0b2  mov     [rsp+0B0h+phkResult], rax; phkResult
0x14015a0b7  xor     r9d, r9d; lpClass
0x14015a0ba  mov     [rsp+0B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x14015a0bf  xor     r8d, r8d; Reserved
0x14015a0c2  mov     [rsp+0B0h+samDesired], 0F003Fh; samDesired
0x14015a0ca  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14015a0d1  mov     [rsp+0B0h+dwOptions], edi; unsigned int
0x14015a0d5  mov     [rbp+57h+var_30], rdi
0x14015a0d9  call    cs:__imp_RegCreateKeyExW
0x14015a0e0  nop     dword ptr [rax+rax+00h]
0x14015a0e5  lea     rcx, [rbp+57h+var_38]
0x14015a0e9  mov     ebx, eax
0x14015a0eb  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x14015a0f0  test    ebx, ebx
0x14015a0f2  jz      short loc_14015A113
0x14015a0f4  mov     rcx, [rbp+5Fh]; this
0x14015a0f8  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14015a0ff  mov     r9d, ebx; char *
0x14015a102  mov     edx, 2916h; void *
0x14015a107  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14015a10c  mov     ebx, eax
0x14015a10e  jmp     loc_14015A396
0x14015a113  xor     edx, edx
0x14015a115  mov     [rbp+57h+ppDacl], rdi
0x14015a119  lea     rcx, [rbp+57h+ppSecurityDescriptor]
0x14015a11d  mov     [rbp+57h+ppSecurityDescriptor], rdi
0x14015a121  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x14015a126  xor     r9d, r9d; ppsidOwner
0x14015a129  lea     rax, [rbp+57h+ppSecurityDescriptor]
0x14015a12d  mov     [rsp+0B0h+phkResult], rax; ppSecurityDescriptor
0x14015a132  lea     rcx, pObjectName; "CURRENT_USER\\SOFTWARE\\Microsoft\\Wind"...
0x14015a139  lea     rax, [rbp+57h+ppDacl]
0x14015a13d  mov     [rsp+0B0h+lpSecurityAttributes], rdi; ppSacl
0x14015a142  mov     qword ptr [rsp+0B0h+samDesired], rax; ppDacl
0x14015a147  lea     r14d, [r9+4]
0x14015a14b  mov     qword ptr [rsp+0B0h+dwOptions], rdi; unsigned int
0x14015a150  mov     r8d, r14d; SecurityInfo
0x14015a153  mov     edx, r14d; ObjectType
0x14015a156  call    cs:__imp_GetNamedSecurityInfoW
0x14015a15d  nop     dword ptr [rax+rax+00h]
0x14015a162  test    eax, eax
0x14015a164  jz      short loc_14015A185
0x14015a166  mov     rcx, [rbp+5Fh]; this
0x14015a16a  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14015a171  mov     r9d, eax; char *
0x14015a174  mov     edx, 291Ch; void *
0x14015a179  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14015a17e  mov     ebx, eax
0x14015a180  jmp     loc_14015A38D
0x14015a185  mov     rcx, [rbp+57h+ppSecurityDescriptor]; SecurityDescriptor
0x14015a189  lea     rax, [rbp+57h+lpString1]
0x14015a18d  lea     r9, [rbp+57h+var_30]; StringSecurityDescriptor
0x14015a191  mov     [rbp+57h+var_38], rax
0x14015a195  mov     r8d, r14d; SecurityInformation
0x14015a198  mov     [rbp+57h+lpString1], rdi
0x14015a19c  mov     edx, 1; RequestedStringSDRevision
0x14015a1a1  mov     [rbp+57h+var_30], rdi
0x14015a1a5  mov     [rbp+57h+var_28], 1
0x14015a1a9  mov     qword ptr [rsp+0B0h+dwOptions], rdi; StringSecurityDescriptorLen
0x14015a1ae  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x14015a1b5  nop     dword ptr [rax+rax+00h]
0x14015a1ba  lea     rcx, [rbp+57h+var_38]
0x14015a1be  mov     ebx, eax
0x14015a1c0  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x14015a1c5  test    ebx, ebx
0x14015a1c7  jnz     short loc_14015A1E5
0x14015a1c9  mov     rcx, [rbp+5Fh]; this
0x14015a1cd  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14015a1d4  mov     edx, 2920h; void *
0x14015a1d9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14015a1de  mov     ebx, eax
0x14015a1e0  jmp     loc_14015A384
0x14015a1e5  mov     rcx, [rbp+57h+lpString1]; lpString1
0x14015a1e9  lea     r8, StringSecurityDescriptor; "D:AI(A;OICIID;KA;;;SY)(A;OICIID;KA;;;BA"...
0x14015a1f0  or      edx, 0FFFFFFFFh; cchCount1
0x14015a1f3  mov     [rsp+0B0h+dwOptions], edi; bIgnoreCase
0x14015a1f7  mov     r9d, edx; cchCount2
0x14015a1fa  call    cs:__imp_CompareStringOrdinal
0x14015a201  nop     dword ptr [rax+rax+00h]
0x14015a206  cmp     eax, 2
0x14015a209  jz      loc_14015A2FF
0x14015a20f  xor     r9d, r9d; SecurityDescriptorSize
0x14015a212  mov     [rbp+57h+pSecurityDescriptor], rdi
0x14015a216  lea     rax, [rbp+57h+pSecurityDescriptor]
0x14015a21a  mov     [rbp+57h+var_30], rdi
0x14015a21e  lea     r8, [rbp+57h+var_30]; SecurityDescriptor
0x14015a222  mov     [rbp+57h+var_38], rax
0x14015a226  lea     rcx, StringSecurityDescriptor; "D:AI(A;OICIID;KA;;;SY)(A;OICIID;KA;;;BA"...
0x14015a22d  mov     [rbp+57h+var_28], 1
0x14015a231  lea     edx, [r9+1]; StringSDRevision
0x14015a235  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14015a23c  nop     dword ptr [rax+rax+00h]
0x14015a241  lea     rcx, [rbp+57h+var_38]
0x14015a245  mov     ebx, eax
0x14015a247  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x14015a24c  test    ebx, ebx
0x14015a24e  jnz     short loc_14015A275
0x14015a250  mov     edx, 2928h; void *
0x14015a255  mov     rcx, [rbp+5Fh]; this
0x14015a259  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14015a260  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14015a265  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x14015a269  mov     ebx, eax
0x14015a26b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x14015a270  jmp     loc_14015A384
0x14015a275  mov     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x14015a279  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x14015a27d  lea     r8, [rbp+57h+pDacl]; pDacl
0x14015a281  mov     [rbp+57h+bDaclPresent], edi
0x14015a284  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x14015a288  mov     [rbp+57h+pDacl], rdi
0x14015a28c  mov     [rbp+57h+bDaclDefaulted], edi
0x14015a28f  call    cs:__imp_GetSecurityDescriptorDacl
0x14015a296  nop     dword ptr [rax+rax+00h]
0x14015a29b  test    eax, eax
0x14015a29d  jnz     short loc_14015A2A6
0x14015a29f  mov     edx, 292Dh
0x14015a2a4  jmp     short loc_14015A255
0x14015a2a6  mov     rax, [rbp+57h+pDacl]
0x14015a2aa  lea     rcx, pObjectName; "CURRENT_USER\\SOFTWARE\\Microsoft\\Wind"...
0x14015a2b1  mov     [rsp+0B0h+lpSecurityAttributes], rdi; pSacl
0x14015a2b6  xor     r9d, r9d; psidOwner
0x14015a2b9  mov     qword ptr [rsp+0B0h+samDesired], rax; pDacl
0x14015a2be  mov     r8d, r14d; SecurityInfo
0x14015a2c1  mov     edx, r14d; ObjectType
0x14015a2c4  mov     qword ptr [rsp+0B0h+dwOptions], rdi; unsigned int
0x14015a2c9  call    cs:__imp_SetNamedSecurityInfoW
0x14015a2d0  nop     dword ptr [rax+rax+00h]
0x14015a2d5  test    eax, eax
0x14015a2d7  jz      short loc_14015A2F6
0x14015a2d9  mov     rcx, [rbp+5Fh]; this
0x14015a2dd  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14015a2e4  mov     r9d, eax; char *
0x14015a2e7  mov     edx, 292Fh; void *
0x14015a2ec  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14015a2f1  jmp     loc_14015A265
0x14015a2f6  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x14015a2fa  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x14015a2ff  mov     [rsp+0B0h+lpdwDisposition], rdi; lpdwDisposition
0x14015a304  lea     rax, [rbp+57h+var_58]
0x14015a308  mov     [rbp+57h+var_38], rax
0x14015a30c  lea     rdx, aSoftwareMicros_77; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14015a313  lea     rax, [rbp+57h+var_30]
0x14015a317  mov     [rbp+57h+var_58], rdi
0x14015a31b  mov     [rsp+0B0h+phkResult], rax; phkResult
0x14015a320  xor     r9d, r9d; lpClass
0x14015a323  mov     [rsp+0B0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x14015a328  xor     r8d, r8d; Reserved
0x14015a32b  mov     [rsp+0B0h+samDesired], 0F003Fh; samDesired
0x14015a333  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14015a33a  mov     [rsp+0B0h+dwOptions], edi; unsigned int
0x14015a33e  mov     [rbp+57h+var_30], rdi
0x14015a342  mov     [rbp+57h+var_28], 1
0x14015a346  call    cs:__imp_RegCreateKeyExW
0x14015a34d  nop     dword ptr [rax+rax+00h]
0x14015a352  lea     rcx, [rbp+57h+var_38]
0x14015a356  mov     ebx, eax
0x14015a358  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x14015a35d  test    ebx, ebx
0x14015a35f  jz      short loc_14015A3A3
0x14015a361  mov     rcx, [rbp+5Fh]; this
0x14015a365  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14015a36c  mov     r9d, ebx; char *
0x14015a36f  mov     edx, 2935h; void *
0x14015a374  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14015a379  lea     rcx, [rbp+57h+var_58]
0x14015a37d  mov     ebx, eax
0x14015a37f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14015a384  lea     rcx, [rbp+57h+lpString1]
0x14015a388  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x14015a38d  lea     rcx, [rbp+57h+ppSecurityDescriptor]
0x14015a391  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x14015a396  lea     rcx, [rbp+57h+var_50]
0x14015a39a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14015a39f  mov     eax, ebx
0x14015a3a1  jmp     short loc_14015A3C9
0x14015a3a3  lea     rcx, [rbp+57h+var_58]
0x14015a3a7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14015a3ac  lea     rcx, [rbp+57h+lpString1]
0x14015a3b0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x14015a3b5  lea     rcx, [rbp+57h+ppSecurityDescriptor]
0x14015a3b9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x14015a3be  lea     rcx, [rbp+57h+var_50]
0x14015a3c2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14015a3c7  xor     eax, eax
0x14015a3c9  add     rsp, 98h
0x14015a3d0  pop     r14
0x14015a3d2  pop     rdi
0x14015a3d3  pop     rbx
0x14015a3d4  pop     rbp
0x14015a3d5  retn
```
