# AddPropertySchemaPathToRegistry(ushort const *,IMigrationContext *,bool *,bool *,SCHEMA_REGISTRATION_DATA * *,HKEY__ * *,ushort * *,ushort * *)

- ea: `0x1800926e8`
- end: `0x180092a9e`
- name: `?AddPropertySchemaPathToRegistry@@YAJPEBGPEAUIMigrationContext@@PEA_N2PEAPEAUSCHEMA_REGISTRATION_DATA@@PEAPEAUHKEY__@@PEAPEAG5@Z`
- size: `950`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszPath@<rcx>, struct IMigrationContext *@<rdx>, bool *@<r8>, bool *@<r9>, struct SCHEMA_REGISTRATION_DATA **, HKEY *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task`

## callers

- `0x180091974`

## callees

- `0x180003698`
- `0x180003c70`
- `0x180004148`
- `0x18000457c`
- `0x180025dd4`
- `0x18006114c`
- `0x180064148`
- `0x180069234`
- `0x18006958c`
- `0x18006dad4`
- `0x18006ed20`
- `0x18008fc28`
- `0x1800926e8`
- `0x180092cb0`
- `0x180093068`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009282c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800928eb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009282c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800928eb`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x1800929ce`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x1800929ce`

## string_xrefs

- `0x180092797`: `onecoreuap\shell\propsys\schemacachehelpers.cpp`
- `0x1800927cb`: `onecoreuap\shell\propsys\schemacachehelpers.cpp`
- `0x18009283d`: `onecoreuap\shell\propsys\schemacachehelpers.cpp`
- `0x1800928fc`: `onecoreuap\shell\propsys\schemacachehelpers.cpp`
- `0x180092929`: `onecoreuap\shell\propsys\schemacachehelpers.cpp`
- `0x180092994`: `onecoreuap\shell\propsys\schemacachehelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall AddPropertySchemaPathToRegistry(
        LPCWSTR pszPath,
        struct IMigrationContext *a2,
        bool *a3,
        bool *a4,
        struct SCHEMA_REGISTRATION_DATA **a5,
        HKEY *a6,
        unsigned __int16 **a7,
        unsigned __int16 **a8)
{
  bool v11; // r13
  struct IMigrationContext *v12; // rdx
  int SchemaLocation; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  int v17; // ebx
  int MigrationRegistryKeyHKLM; // eax
  unsigned int v19; // eax
  unsigned __int16 *v20; // rbx
  int NextAvailableKeyName; // eax
  unsigned int v22; // eax
  unsigned int v23; // edx
  SCHEMA_REGISTRATION_DATA *v24; // rcx
  unsigned int v25; // edx
  SCHEMA_REGISTRATION_DATA *v26; // rcx
  HKEY v27; // rax
  unsigned __int16 *v28; // rax
  int dwOptions; // [rsp+20h] [rbp-99h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-99h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-99h]
  int dwOptionsc; // [rsp+20h] [rbp-99h]
  bool v34; // [rsp+50h] [rbp-69h] BYREF
  bool v35; // [rsp+51h] [rbp-68h] BYREF
  unsigned __int16 *v36; // [rsp+58h] [rbp-61h] BYREF
  unsigned __int16 *v37; // [rsp+60h] [rbp-59h]
  LPCWSTR v38; // [rsp+68h] [rbp-51h]
  unsigned int v39[2]; // [rsp+70h] [rbp-49h]
  SCHEMA_REGISTRATION_DATA **v40; // [rsp+78h] [rbp-41h] BYREF
  struct SCHEMA_REGISTRATION_DATA *v41; // [rsp+80h] [rbp-39h] BYREF
  char v42; // [rsp+88h] [rbp-31h]
  HKEY hKey; // [rsp+90h] [rbp-29h] BYREF
  LPCWSTR pszSubKey; // [rsp+98h] [rbp-21h] BYREF
  LPCWSTR lpSubKey; // [rsp+A0h] [rbp-19h] BYREF
  HKEY phkResult; // [rsp+A8h] [rbp-11h] BYREF
  SCHEMA_REGISTRATION_DATA *v47; // [rsp+B0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+3Fh]

  v38 = pszPath;
  *(_QWORD *)v39 = a5;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v11 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v36,
    0);
  SchemaLocation = VerifyAndGetSchemaLocation(pszPath, v12, (const char **)&v36);
  v17 = SchemaLocation;
  if ( SchemaLocation < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x218,
      (unsigned int)"onecoreuap\\shell\\propsys\\schemacachehelpers.cpp",
      (const char *)(unsigned int)SchemaLocation,
      dwOptions);
    goto LABEL_49;
  }
  lpSubKey = 0;
  MigrationRegistryKeyHKLM = MaybeGetMigrationRegistryKeyHKLM(v15, v14, v16, &lpSubKey);
  v17 = MigrationRegistryKeyHKLM;
  if ( MigrationRegistryKeyHKLM < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21C,
      (unsigned int)"onecoreuap\\shell\\propsys\\schemacachehelpers.cpp",
      (const char *)(unsigned int)MigrationRegistryKeyHKLM,
      dwOptions);
LABEL_17:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
    goto LABEL_49;
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v19 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0xCu, 0, &hKey, 0);
  if ( v19 )
  {
    v17 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x21F,
            (unsigned int)"onecoreuap\\shell\\propsys\\schemacachehelpers.cpp",
            (const char *)v19,
            dwOptionsa);
LABEL_20:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_17;
  }
  v20 = v36;
  v37 = v36;
  pszSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pszSubKey,
    0);
  NextAvailableKeyName = SHRegFindNextAvailableKeyName(hKey, v20, &pszSubKey);
  v17 = NextAvailableKeyName;
  if ( NextAvailableKeyName == 1 )
  {
    v11 = 1;
    v34 = 1;
  }
  else if ( NextAvailableKeyName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22A,
      (unsigned int)"onecoreuap\\shell\\propsys\\schemacachehelpers.cpp",
      (const char *)(unsigned int)NextAvailableKeyName,
      dwOptionsa);
    goto LABEL_28;
  }
  SchemaCacheMigrationLogMessage(0, L"Creating Key for %ws as %ws", v38, pszSubKey);
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v22 = RegCreateKeyExW(hKey, pszSubKey, 0, 0, 0, 0x20006u, 0, &phkResult, 0);
  if ( v22 )
  {
    v17 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x22E,
            (unsigned int)"onecoreuap\\shell\\propsys\\schemacachehelpers.cpp",
            (const char *)v22,
            dwOptionsb);
LABEL_25:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
LABEL_28:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszSubKey);
    goto LABEL_20;
  }
  v47 = 0;
  v40 = &v47;
  v41 = 0;
  v42 = 1;
  v17 = GenerateSchemaRegistrationData(v37, phkResult, &v34, &v35, &v41);
  wil::details::out_param_t<wistd::unique_ptr<SCHEMA_REGISTRATION_DATA,wistd::default_delete<SCHEMA_REGISTRATION_DATA>>>::~out_param_t<wistd::unique_ptr<SCHEMA_REGISTRATION_DATA,wistd::default_delete<SCHEMA_REGISTRATION_DATA>>>(&v40);
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23B,
      (unsigned int)"onecoreuap\\shell\\propsys\\schemacachehelpers.cpp",
      (const char *)(unsigned int)v17,
      dwOptionsc);
    v24 = v47;
    v47 = 0;
    if ( v24 )
      SCHEMA_REGISTRATION_DATA::`scalar deleting destructor'(v24, v23);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    SHDeleteKeyW(hKey, pszSubKey);
    goto LABEL_25;
  }
  v25 = v39[0];
  if ( *(_QWORD *)v39 )
  {
    v26 = 0;
    **(_QWORD **)v39 = v47;
  }
  else
  {
    v26 = v47;
  }
  if ( a6 )
  {
    v27 = hKey;
    hKey = 0;
    *a6 = v27;
  }
  if ( a7 )
  {
    v28 = (unsigned __int16 *)pszSubKey;
    pszSubKey = 0;
    *a7 = v28;
  }
  if ( a8 )
  {
    v36 = 0;
    *a8 = v37;
  }
  if ( a3 )
    *a3 = v11;
  if ( a4 )
    *a4 = v35;
  v47 = 0;
  if ( v26 )
    SCHEMA_REGISTRATION_DATA::`scalar deleting destructor'(v26, v25);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszSubKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpSubKey);
  v17 = 0;
LABEL_49:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v36);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800926e8  mov     [rsp-8+arg_8], rbx
0x1800926ed  push    rbp
0x1800926ee  push    rsi
0x1800926ef  push    rdi
0x1800926f0  push    r12
0x1800926f2  push    r13
0x1800926f4  push    r14
0x1800926f6  push    r15
0x1800926f8  lea     rbp, [rsp-7]
0x1800926fd  sub     rsp, 0C0h
0x180092704  mov     rax, cs:__security_cookie
0x18009270b  xor     rax, rsp
0x18009270e  mov     [rbp+37h+var_38], rax
0x180092712  mov     rdi, r9
0x180092715  mov     rsi, r8
0x180092718  mov     rbx, rcx
0x18009271b  mov     [rbp+37h+var_88], rcx
0x18009271f  mov     rax, [rbp+37h+arg_20]
0x180092723  mov     qword ptr [rbp+37h+var_80], rax
0x180092727  mov     r14, [rbp+37h+arg_28]
0x18009272b  mov     r15, [rbp+37h+arg_30]
0x18009272f  mov     r12, [rbp+37h+arg_38]
0x180092733  xor     ecx, ecx
0x180092735  test    rax, rax
0x180092738  jz      short loc_18009273D
0x18009273a  mov     [rax], rcx
0x18009273d  test    r14, r14
0x180092740  jz      short loc_180092745
0x180092742  mov     [r14], rcx
0x180092745  test    r15, r15
0x180092748  jz      short loc_18009274D
0x18009274a  mov     [r15], rcx
0x18009274d  test    r12, r12
0x180092750  jz      short loc_180092756
0x180092752  mov     [r12], rcx
0x180092756  test    rsi, rsi
0x180092759  jz      short loc_18009275E
0x18009275b  mov     [r8], cl
0x18009275e  test    rdi, rdi
0x180092761  jz      short loc_180092766
0x180092763  mov     [r9], cl
0x180092766  mov     r13b, cl
0x180092769  mov     [rbp+37h+var_A0], cl
0x18009276c  mov     [rbp+37h+var_9F], cl
0x18009276f  mov     [rbp+37h+var_98], rcx
0x180092773  xor     edx, edx
0x180092775  lea     rcx, [rbp+37h+var_98]
0x180092779  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18009277e  lea     r8, [rbp+37h+var_98]; unsigned __int16 **
0x180092782  mov     rcx, rbx; pszPath
0x180092785  call    ?VerifyAndGetSchemaLocation@@YAJPEBGPEAUIMigrationContext@@PEAPEAG@Z; VerifyAndGetSchemaLocation(ushort const *,IMigrationContext *,ushort * *)
0x18009278a  mov     ebx, eax
0x18009278c  test    eax, eax
0x18009278e  jns     short loc_1800927AD
0x180092790  mov     rcx, [rbp+3Fh]; this
0x180092794  mov     r9d, eax; char *
0x180092797  lea     r8, aOnecoreuapShel_11; "onecoreuap\\shell\\propsys\\schemacache"...
0x18009279e  mov     edx, 218h; void *
0x1800927a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800927a8  jmp     loc_180092A6C
0x1800927ad  mov     [rbp+37h+lpSubKey], 0
0x1800927b5  lea     r9, [rbp+37h+lpSubKey]
0x1800927b9  call    ?MaybeGetMigrationRegistryKeyHKLM@@YAJKPEBGPEAUIMigrationContext@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; MaybeGetMigrationRegistryKeyHKLM(ulong,ushort const *,IMigrationContext *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1800927be  mov     ebx, eax
0x1800927c0  test    eax, eax
0x1800927c2  jns     short loc_1800927EB
0x1800927c4  mov     rcx, [rbp+3Fh]; this
0x1800927c8  mov     r9d, eax; char *
0x1800927cb  lea     r8, aOnecoreuapShel_11; "onecoreuap\\shell\\propsys\\schemacache"...
0x1800927d2  mov     edx, 21Ch; void *
0x1800927d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800927dc  nop
0x1800927dd  lea     rcx, [rbp+37h+lpSubKey]
0x1800927e1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800927e6  jmp     loc_180092A6C
0x1800927eb  xor     ebx, ebx
0x1800927ed  mov     [rbp+37h+hKey], rbx
0x1800927f1  xor     edx, edx
0x1800927f3  lea     rcx, [rbp+37h+hKey]
0x1800927f7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800927fc  mov     [rsp+0F0h+lpdwDisposition], rbx; lpdwDisposition
0x180092801  lea     rax, [rbp+37h+hKey]
0x180092805  mov     [rsp+0F0h+phkResult], rax; phkResult
0x18009280a  mov     [rsp+0F0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18009280f  mov     [rsp+0F0h+samDesired], 0Ch; samDesired
0x180092817  mov     [rsp+0F0h+dwOptions], ebx; int
0x18009281b  xor     r9d, r9d; lpClass
0x18009281e  xor     r8d, r8d; Reserved
0x180092821  mov     rdx, [rbp+37h+lpSubKey]; lpSubKey
0x180092825  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009282c  call    cs:__imp_RegCreateKeyExW
0x180092832  test    eax, eax
0x180092834  jz      short loc_18009285B
0x180092836  mov     rcx, [rbp+3Fh]; this
0x18009283a  mov     r9d, eax; char *
0x18009283d  lea     r8, aOnecoreuapShel_11; "onecoreuap\\shell\\propsys\\schemacache"...
0x180092844  mov     edx, 21Fh; void *
0x180092849  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009284e  mov     ebx, eax
0x180092850  lea     rcx, [rbp+37h+hKey]
0x180092854  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180092859  jmp     short loc_1800927DD
0x18009285b  mov     rbx, [rbp+37h+var_98]
0x18009285f  mov     [rbp+37h+var_90], rbx
0x180092863  mov     [rbp+37h+pszSubKey], 0
0x18009286b  xor     edx, edx
0x18009286d  lea     rcx, [rbp+37h+pszSubKey]
0x180092871  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180092876  lea     r8, [rbp+37h+pszSubKey]
0x18009287a  mov     rdx, rbx
0x18009287d  mov     rcx, [rbp+37h+hKey]
0x180092881  call    SHRegFindNextAvailableKeyName
0x180092886  mov     ebx, eax
0x180092888  cmp     eax, 1
0x18009288b  jnz     loc_18009291A
0x180092891  mov     r13b, al
0x180092894  mov     [rbp+37h+var_A0], al
0x180092897  mov     r9, [rbp+37h+pszSubKey]
0x18009289b  mov     r8, [rbp+37h+var_88]
0x18009289f  lea     rdx, aCreatingKeyFor; "Creating Key for %ws as %ws"
0x1800928a6  xor     ecx, ecx; struct IMigrationContext *
0x1800928a8  call    ?SchemaCacheMigrationLogMessage@@YAXPEAUIMigrationContext@@PEBGZZ; SchemaCacheMigrationLogMessage(IMigrationContext *,ushort const *,...)
0x1800928ad  xor     ebx, ebx
0x1800928af  mov     [rbp+37h+var_48], rbx
0x1800928b3  xor     edx, edx
0x1800928b5  lea     rcx, [rbp+37h+var_48]
0x1800928b9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800928be  mov     [rsp+0F0h+lpdwDisposition], rbx; lpdwDisposition
0x1800928c3  lea     rax, [rbp+37h+var_48]
0x1800928c7  mov     [rsp+0F0h+phkResult], rax; phkResult
0x1800928cc  mov     [rsp+0F0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800928d1  mov     [rsp+0F0h+samDesired], 20006h; samDesired
0x1800928d9  mov     [rsp+0F0h+dwOptions], ebx; unsigned int
0x1800928dd  xor     r9d, r9d; lpClass
0x1800928e0  xor     r8d, r8d; Reserved
0x1800928e3  mov     rdx, [rbp+37h+pszSubKey]; lpSubKey
0x1800928e7  mov     rcx, [rbp+37h+hKey]; hKey
0x1800928eb  call    cs:__imp_RegCreateKeyExW
0x1800928f1  test    eax, eax
0x1800928f3  jz      short loc_180092949
0x1800928f5  mov     rcx, [rbp+3Fh]; this
0x1800928f9  mov     r9d, eax; char *
0x1800928fc  lea     r8, aOnecoreuapShel_11; "onecoreuap\\shell\\propsys\\schemacache"...
0x180092903  mov     edx, 22Eh; void *
0x180092908  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009290d  mov     ebx, eax
0x18009290f  lea     rcx, [rbp+37h+var_48]
0x180092913  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180092918  jmp     short loc_18009293B
0x18009291a  test    eax, eax
0x18009291c  jns     loc_180092897
0x180092922  mov     rcx, [rbp+3Fh]; this
0x180092926  mov     r9d, eax; char *
0x180092929  lea     r8, aOnecoreuapShel_11; "onecoreuap\\shell\\propsys\\schemacache"...
0x180092930  mov     edx, 22Ah; void *
0x180092935  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009293a  nop
0x18009293b  lea     rcx, [rbp+37h+pszSubKey]
0x18009293f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180092944  jmp     loc_180092850
0x180092949  mov     [rbp+37h+var_40], rbx
0x18009294d  lea     rax, [rbp+37h+var_40]
0x180092951  mov     [rbp+37h+var_78], rax
0x180092955  mov     [rbp+37h+var_70], rbx
0x180092959  mov     [rbp+37h+var_68], 1
0x18009295d  lea     rax, [rbp+37h+var_70]
0x180092961  mov     qword ptr [rsp+0F0h+dwOptions], rax; int
0x180092966  lea     r9, [rbp+37h+var_9F]; bool *
0x18009296a  lea     r8, [rbp+37h+var_A0]; bool *
0x18009296e  mov     rdx, [rbp+37h+var_48]; HKEY
0x180092972  mov     rcx, [rbp+37h+var_90]; unsigned __int16 *
0x180092976  call    ?GenerateSchemaRegistrationData@@YAJPEBGPEAUHKEY__@@AEA_N2PEAPEAUSCHEMA_REGISTRATION_DATA@@@Z; GenerateSchemaRegistrationData(ushort const *,HKEY__ *,bool &,bool &,SCHEMA_REGISTRATION_DATA * *)
0x18009297b  mov     ebx, eax
0x18009297d  lea     rcx, [rbp+37h+var_78]
0x180092981  call    ??1?$out_param_t@V?$unique_ptr@USCHEMA_REGISTRATION_DATA@@U?$default_delete@USCHEMA_REGISTRATION_DATA@@@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SCHEMA_REGISTRATION_DATA,wistd::default_delete<SCHEMA_REGISTRATION_DATA>>>::~out_param_t<wistd::unique_ptr<SCHEMA_REGISTRATION_DATA,wistd::default_delete<SCHEMA_REGISTRATION_DATA>>>(void)
0x180092986  xor     r8d, r8d
0x180092989  test    ebx, ebx
0x18009298b  jns     short loc_1800929D9
0x18009298d  mov     rcx, [rbp+3Fh]; this
0x180092991  mov     r9d, ebx; char *
0x180092994  lea     r8, aOnecoreuapShel_11; "onecoreuap\\shell\\propsys\\schemacache"...
0x18009299b  mov     edx, 23Bh; void *
0x1800929a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800929a5  mov     rcx, [rbp+37h+var_40]; this
0x1800929a9  mov     [rbp+37h+var_40], 0
0x1800929b1  test    rcx, rcx
0x1800929b4  jz      short loc_1800929BB
0x1800929b6  call    ??_GSCHEMA_REGISTRATION_DATA@@QEAAPEAXI@Z; SCHEMA_REGISTRATION_DATA::`scalar deleting destructor'(uint)
0x1800929bb  xor     edx, edx
0x1800929bd  lea     rcx, [rbp+37h+var_48]
0x1800929c1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800929c6  mov     rdx, [rbp+37h+pszSubKey]; pszSubKey
0x1800929ca  mov     rcx, [rbp+37h+hKey]; hkey
0x1800929ce  call    cs:__imp_SHDeleteKeyW
0x1800929d4  jmp     loc_18009290F
0x1800929d9  mov     rdx, qword ptr [rbp+37h+var_80]; unsigned int
0x1800929dd  test    rdx, rdx
0x1800929e0  jz      short loc_1800929EE
0x1800929e2  mov     rax, [rbp+37h+var_40]
0x1800929e6  mov     rcx, r8
0x1800929e9  mov     [rdx], rax
0x1800929ec  jmp     short loc_1800929F2
0x1800929ee  mov     rcx, [rbp+37h+var_40]; this
0x1800929f2  test    r14, r14
0x1800929f5  jz      short loc_180092A02
0x1800929f7  mov     rax, [rbp+37h+hKey]
0x1800929fb  mov     [rbp+37h+hKey], r8
0x1800929ff  mov     [r14], rax
0x180092a02  test    r15, r15
0x180092a05  jz      short loc_180092A12
0x180092a07  mov     rax, [rbp+37h+pszSubKey]
0x180092a0b  mov     [rbp+37h+pszSubKey], r8
0x180092a0f  mov     [r15], rax
0x180092a12  test    r12, r12
0x180092a15  jz      short loc_180092A23
0x180092a17  mov     [rbp+37h+var_98], r8
0x180092a1b  mov     rax, [rbp+37h+var_90]
0x180092a1f  mov     [r12], rax
0x180092a23  test    rsi, rsi
0x180092a26  jz      short loc_180092A2B
0x180092a28  mov     [rsi], r13b
0x180092a2b  test    rdi, rdi
0x180092a2e  jz      short loc_180092A35
0x180092a30  mov     al, [rbp+37h+var_9F]
0x180092a33  mov     [rdi], al
0x180092a35  mov     [rbp+37h+var_40], r8
0x180092a39  test    rcx, rcx
0x180092a3c  jz      short loc_180092A43
0x180092a3e  call    ??_GSCHEMA_REGISTRATION_DATA@@QEAAPEAXI@Z; SCHEMA_REGISTRATION_DATA::`scalar deleting destructor'(uint)
0x180092a43  lea     rcx, [rbp+37h+var_48]
0x180092a47  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180092a4c  nop
0x180092a4d  lea     rcx, [rbp+37h+pszSubKey]
0x180092a51  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180092a56  nop
0x180092a57  lea     rcx, [rbp+37h+hKey]
0x180092a5b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180092a60  nop
0x180092a61  lea     rcx, [rbp+37h+lpSubKey]
0x180092a65  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180092a6a  xor     ebx, ebx
0x180092a6c  lea     rcx, [rbp+37h+var_98]
0x180092a70  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180092a75  mov     eax, ebx
0x180092a77  mov     rcx, [rbp+37h+var_38]
0x180092a7b  xor     rcx, rsp; StackCookie
0x180092a7e  call    __security_check_cookie
0x180092a83  mov     rbx, [rsp+0F0h+arg_8]
0x180092a8b  add     rsp, 0C0h
0x180092a92  pop     r15
0x180092a94  pop     r14
0x180092a96  pop     r13
0x180092a98  pop     r12
0x180092a9a  pop     rdi
0x180092a9b  pop     rsi
0x180092a9c  pop     rbp
0x180092a9d  retn
```
