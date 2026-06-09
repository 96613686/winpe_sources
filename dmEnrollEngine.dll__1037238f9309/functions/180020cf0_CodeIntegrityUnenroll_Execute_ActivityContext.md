# CodeIntegrityUnenroll::Execute(ActivityContext *)

- ea: `0x180020cf0`
- end: `0x180021243`
- name: `?Execute@CodeIntegrityUnenroll@@UEAAJPEAVActivityContext@@@Z`
- size: `1363`
- prototype: `int(CodeIntegrityUnenroll *__hidden this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800071c0`
- `0x18001a86c`
- `0x18001e770`
- `0x180020cf0`
- `0x18002124c`
- `0x18002e1a0`
- `0x18003061c`
- `0x180032f20`
- `0x18003a96c`
- `0x180065f3c`
- `0x18006bc74`
- `0x18006c41c`
- `0x18006c448`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020db1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020dc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020e15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020e2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800211f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002120b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020db1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020dc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020e15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020e2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800211f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002120b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002113a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002113a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021114`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021114`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020d9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020dff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800211df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020d9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020dff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800211df`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180021046`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180021046`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180021180`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180021180`
- `ext-ms-win-ci-management-l1-1-0!ManageCI_BeginRemoveSBCPToken` at `0x180020f88`
- `ext-ms-win-ci-management-l1-1-0!ManageCI_BeginRemoveSBCPToken` at `0x180020f88`
- `ext-ms-win-ci-management-l1-1-0!ManageCI_ValidateState` at `0x180020f96`
- `ext-ms-win-ci-management-l1-1-0!ManageCI_ValidateState` at `0x180020f96`
- `ext-ms-win-ci-management-l1-1-0!ManageCI_End` at `0x180020fda`
- `ext-ms-win-ci-management-l1-1-0!ManageCI_End` at `0x180020fda`
- `ext-ms-win-ci-management-l1-1-0!ManageCI_Start` at `0x180020e38`
- `ext-ms-win-ci-management-l1-1-0!ManageCI_Start` at `0x180020e38`
- `ext-ms-win-ci-management-l1-1-0!ManageCI_Commit` at `0x180020fb8`
- `ext-ms-win-ci-management-l1-1-0!ManageCI_Commit` at `0x180020fb8`
- `ext-ms-win-ci-management-l1-1-0!ManageCI_GetAllSBCPTokens` at `0x180020f46`
- `ext-ms-win-ci-management-l1-1-0!ManageCI_GetAllSBCPTokens` at `0x180020f46`
- `ext-ms-win-ci-management-l1-1-0!ManageCI_GetAllCIPolicies` at `0x180020e9a`
- `ext-ms-win-ci-management-l1-1-0!ManageCI_GetAllCIPolicies` at `0x180020e9a`
- `ext-ms-win-ci-management-l1-1-0!ManageCI_BeginRemoveCIPolicy` at `0x180020f1e`
- `ext-ms-win-ci-management-l1-1-0!ManageCI_BeginRemoveCIPolicy` at `0x180020f1e`
- `ext-ms-win-ci-management-l1-1-0!ManageCI_BeginTransaction` at `0x180020e5a`
- `ext-ms-win-ci-management-l1-1-0!ManageCI_BeginTransaction` at `0x180020e5a`
- `ext-ms-win-ci-management-l1-1-3!ManageCI_ShouldIgnoreRemoval` at `0x180020eed`
- `ext-ms-win-ci-management-l1-1-3!ManageCI_ShouldIgnoreRemoval` at `0x180020eed`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall CodeIntegrityUnenroll::Execute(CodeIntegrityUnenroll *this, struct ActivityContext *a2)
{
  int v4; // eax
  int v5; // eax
  int AllCIPolicies; // eax
  unsigned int i; // edi
  __int64 v8; // rsi
  int ShouldIgnoreRemoval; // eax
  int AllSBCPTokens; // eax
  unsigned int j; // edi
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int KeyAsString; // eax
  signed int PersistedRegistryLocationW; // eax
  int v17; // eax
  int v18; // eax
  LSTATUS v19; // eax
  signed int v20; // edi
  void *v21; // rdx
  unsigned int v22; // r8d
  int v23; // eax
  int v24; // eax
  HLOCAL v25; // rcx
  HLOCAL v26; // rcx
  int phkResult; // [rsp+20h] [rbp-2D8h]
  int phkResulta; // [rsp+20h] [rbp-2D8h]
  _BYTE v29[4]; // [rsp+30h] [rbp-2C8h] BYREF
  unsigned int v30; // [rsp+34h] [rbp-2C4h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-2C0h] BYREF
  HLOCAL v32; // [rsp+40h] [rbp-2B8h] BYREF
  unsigned int v33; // [rsp+48h] [rbp-2B0h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-2A8h] BYREF
  void *p_hMem; // [rsp+58h] [rbp-2A0h] BYREF
  HKEY v36; // [rsp+60h] [rbp-298h] BYREF
  char v37; // [rsp+68h] [rbp-290h]
  unsigned __int16 v38[40]; // [rsp+70h] [rbp-288h] BYREF
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+0h]

  if ( !(unsigned __int8)IsManageCIPresent(this) )
    return 0;
  v32 = 0;
  v33 = 0;
  hMem = 0;
  v30 = 0;
  hKey = 0;
  if ( *((_DWORD *)a2 + 243) == 63 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\activities\\src\\mdmunenroll\\codeintegrityunenroll.cpp",
      (const char *)0x8000FFFFLL,
      phkResult);
  if ( ((1LL << *((_DWORD *)a2 + 243)) & 0xD402061) != 0 )
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_CodeIntegrity_Unenroll_Fix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_CodeIntegrity_Unenroll_Fix>::GetImpl'::`2'::impl)
      || ((*((_DWORD *)a2 + 243) - 24) & 0xFFFFFFFD) != 0 )
    {
      v4 = ManageCI_Start();
      if ( v4 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x33,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\activities\\src\\mdmunenroll\\codeintegrityunenroll.cpp",
          (const char *)(unsigned int)v4,
          phkResult);
      v5 = ManageCI_BeginTransaction(retaddr);
      if ( v5 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x35,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\activities\\src\\mdmunenroll\\codeintegrityunenroll.cpp",
          (const char *)(unsigned int)v5,
          phkResult);
      p_hMem = &hMem;
      v36 = 0;
      v37 = 1;
      AllCIPolicies = ManageCI_GetAllCIPolicies(&v36, &v30);
      if ( AllCIPolicies < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x37,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\activities\\src\\mdmunenroll\\codeintegrityunenroll.cpp",
          (const char *)(unsigned int)AllCIPolicies,
          phkResult);
      wil::details::out_param_t<wistd::unique_ptr<_GUID [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_hMem);
      for ( i = 0; i < v30; ++i )
      {
        v29[0] = 0;
        v8 = 16LL * i;
        ShouldIgnoreRemoval = ManageCI_ShouldIgnoreRemoval((char *)hMem + v8, 1, v29);
        if ( ShouldIgnoreRemoval < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x3C,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\activities\\src\\mdmunenroll\\codeintegrityunenroll.cpp",
            (const char *)(unsigned int)ShouldIgnoreRemoval,
            phkResult);
        if ( !v29[0] )
          ManageCI_BeginRemoveCIPolicy((char *)hMem + v8);
      }
      p_hMem = &v32;
      v36 = 0;
      v37 = 1;
      AllSBCPTokens = ManageCI_GetAllSBCPTokens(&v36, &v33);
      if ( AllSBCPTokens < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x44,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\activities\\src\\mdmunenroll\\codeintegrityunenroll.cpp",
          (const char *)(unsigned int)AllSBCPTokens,
          phkResult);
      wil::details::out_param_t<wistd::unique_ptr<_GUID [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_hMem);
      for ( j = 0; j < v33; ++j )
        ManageCI_BeginRemoveSBCPToken(*((_QWORD *)v32 + j));
      v12 = ManageCI_ValidateState();
      if ( v12 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x4A,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\activities\\src\\mdmunenroll\\codeintegrityunenroll.cpp",
          (const char *)(unsigned int)v12,
          phkResult);
      v13 = ManageCI_Commit(retaddr);
      if ( v13 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x4B,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\activities\\src\\mdmunenroll\\codeintegrityunenroll.cpp",
          (const char *)(unsigned int)v13,
          phkResult);
      v14 = ManageCI_End(retaddr);
      if ( v14 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x4D,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\activities\\src\\mdmunenroll\\codeintegrityunenroll.cpp",
          (const char *)(unsigned int)v14,
          phkResult);
      KeyAsString = ActivityContext::get_KeyAsString(a2, v38);
      if ( KeyAsString < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x50,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\activities\\src\\mdmunenroll\\codeintegrityunenroll.cpp",
          (const char *)(unsigned int)KeyAsString,
          phkResult);
      PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                     L"CIEnrollments",
                                     L"SYSTEM\\CurrentControlSet\\Control\\CI\\Enrollments",
                                     SubKey,
                                     522);
      if ( PersistedRegistryLocationW > 0 )
        PersistedRegistryLocationW = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
      if ( PersistedRegistryLocationW < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x58,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\activities\\src\\mdmunenroll\\codeintegrityunenroll.cpp",
          (const char *)(unsigned int)PersistedRegistryLocationW,
          0);
      v17 = StringCchCatW(SubKey, 0x105u, L"\\");
      if ( v17 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x5A,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\activities\\src\\mdmunenroll\\codeintegrityunenroll.cpp",
          (const char *)(unsigned int)v17,
          0);
      v18 = StringCchCatW(SubKey, 0x105u, v38);
      if ( v18 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x5B,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\activities\\src\\mdmunenroll\\codeintegrityunenroll.cpp",
          (const char *)(unsigned int)v18,
          0);
      p_hMem = &hKey;
      v36 = 0;
      v37 = 1;
      v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2000Fu, &v36);
      v20 = v19;
      if ( v19 > 0 )
        v20 = (unsigned __int16)v19 | 0x80070000;
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hMem);
      if ( v20 < 0 )
      {
        if ( v20 != -2147024894 )
          wil::details::in1diag3::Throw_Hr(retaddr, v21, v22, (const char *)(unsigned int)v20, phkResulta);
      }
      else
      {
        v23 = RegDeleteTreeW(hKey, 0);
        if ( v23 > 0 )
          v23 = (unsigned __int16)v23 | 0x80070000;
        if ( v23 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x6A,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\activities\\src\\mdmunenroll\\codeintegrityunenroll.cpp",
            (const char *)(unsigned int)v23,
            phkResulta);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hKey,
          0);
        v24 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, SubKey);
        if ( v24 > 0 )
          v24 = (unsigned __int16)v24 | 0x80070000;
        if ( v24 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x72,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\activities\\src\\mdmunenroll\\codeintegrityunenroll.cpp",
            (const char *)(unsigned int)v24,
            phkResulta);
      }
      ManageCIProvider::InstrumentUnenroll(v38, *((unsigned int *)a2 + 243));
      if ( hKey )
        RegCloseKey(hKey);
      v25 = hMem;
      hMem = 0;
      if ( v25 )
        LocalFree(v25);
      v26 = v32;
      v32 = 0;
      if ( v26 )
        LocalFree(v26);
      return 0;
    }
    else
    {
      hMem = 0;
      v32 = 0;
      return 0;
    }
  }
  else
  {
    hMem = 0;
    v32 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x180020cf0  mov     [rsp+arg_0], rbx
0x180020cf5  mov     [rsp+arg_10], rsi
0x180020cfa  push    rdi
0x180020cfb  push    r14
0x180020cfd  push    r15
0x180020cff  sub     rsp, 2E0h
0x180020d06  mov     rax, cs:__security_cookie
0x180020d0d  xor     rax, rsp
0x180020d10  mov     [rsp+2F8h+var_28], rax
0x180020d18  mov     r14, rdx
0x180020d1b  call    IsManageCIPresent
0x180020d20  xor     r15d, r15d
0x180020d23  test    al, al
0x180020d25  jnz     short loc_180020D2E
0x180020d27  xor     eax, eax
0x180020d29  jmp     loc_180021219
0x180020d2e  mov     [rsp+2F8h+var_2B8], r15
0x180020d33  mov     [rsp+2F8h+var_2B0], r15d
0x180020d38  mov     [rsp+2F8h+hMem], r15
0x180020d3d  mov     [rsp+2F8h+var_2C4], r15d
0x180020d42  mov     rax, r15
0x180020d45  mov     [rsp+2F8h+hKey], rax
0x180020d4a  mov     rcx, [rsp+2F8h]; this
0x180020d52  lea     rbx, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180020d59  cmp     dword ptr [r14+3CCh], 3Fh ; '?'
0x180020d61  jnz     short loc_180020D7B
0x180020d63  mov     r9d, 8000FFFFh; char *
0x180020d69  mov     r8, rbx; unsigned int
0x180020d6c  mov     edx, 22h ; '"'; void *
0x180020d71  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020d76  mov     rax, [rsp+2F8h+hKey]
0x180020d7b  mov     ecx, [r14+3CCh]
0x180020d82  mov     edx, 1
0x180020d87  shl     rdx, cl
0x180020d8a  test    rdx, 0D402061h
0x180020d91  jnz     short loc_180020DD4
0x180020d93  test    rax, rax
0x180020d96  jz      short loc_180020DA2
0x180020d98  mov     rcx, rax; hKey
0x180020d9b  call    cs:__imp_RegCloseKey
0x180020da1  nop
0x180020da2  mov     rcx, [rsp+2F8h+hMem]; hMem
0x180020da7  mov     [rsp+2F8h+hMem], r15
0x180020dac  test    rcx, rcx
0x180020daf  jz      short loc_180020DB8
0x180020db1  call    cs:__imp_LocalFree
0x180020db7  nop
0x180020db8  mov     rcx, [rsp+2F8h+var_2B8]; hMem
0x180020dbd  mov     [rsp+2F8h+var_2B8], r15
0x180020dc2  test    rcx, rcx
0x180020dc5  jz      short loc_180020DCD
0x180020dc7  call    cs:__imp_LocalFree
0x180020dcd  xor     eax, eax
0x180020dcf  jmp     loc_180021219
0x180020dd4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_CodeIntegrity_Unenroll_Fix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_CodeIntegrity_Unenroll_Fix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_CodeIntegrity_Unenroll_Fix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_CodeIntegrity_Unenroll_Fix>::GetImpl(void)'::`2'::impl
0x180020ddb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_CodeIntegrity_Unenroll_Fix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_CodeIntegrity_Unenroll_Fix>::__private_IsEnabled(void)
0x180020de0  test    al, al
0x180020de2  jz      short loc_180020E38
0x180020de4  mov     eax, [r14+3CCh]
0x180020deb  sub     eax, 18h
0x180020dee  test    eax, 0FFFFFFFDh
0x180020df3  jnz     short loc_180020E38
0x180020df5  mov     rcx, [rsp+2F8h+hKey]; hKey
0x180020dfa  test    rcx, rcx
0x180020dfd  jz      short loc_180020E06
0x180020dff  call    cs:__imp_RegCloseKey
0x180020e05  nop
0x180020e06  mov     rcx, [rsp+2F8h+hMem]; hMem
0x180020e0b  mov     [rsp+2F8h+hMem], r15
0x180020e10  test    rcx, rcx
0x180020e13  jz      short loc_180020E1C
0x180020e15  call    cs:__imp_LocalFree
0x180020e1b  nop
0x180020e1c  mov     rcx, [rsp+2F8h+var_2B8]; hMem
0x180020e21  mov     [rsp+2F8h+var_2B8], r15
0x180020e26  test    rcx, rcx
0x180020e29  jz      short loc_180020E31
0x180020e2b  call    cs:__imp_LocalFree
0x180020e31  xor     eax, eax
0x180020e33  jmp     loc_180021219
0x180020e38  call    cs:__imp_ManageCI_Start
0x180020e3e  mov     rcx, [rsp+2F8h]; this
0x180020e46  test    eax, eax
0x180020e48  jns     short loc_180020E5A
0x180020e4a  mov     r9d, eax; char *
0x180020e4d  mov     r8, rbx; unsigned int
0x180020e50  mov     edx, 33h ; '3'; void *
0x180020e55  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020e5a  call    cs:__imp_ManageCI_BeginTransaction
0x180020e60  mov     rcx, [rsp+2F8h]; this
0x180020e68  test    eax, eax
0x180020e6a  jns     short loc_180020E7C
0x180020e6c  mov     r9d, eax; char *
0x180020e6f  mov     r8, rbx; unsigned int
0x180020e72  mov     edx, 35h ; '5'; void *
0x180020e77  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020e7c  lea     rax, [rsp+2F8h+hMem]
0x180020e81  mov     [rsp+2F8h+var_2A0], rax
0x180020e86  mov     [rsp+2F8h+var_298], r15
0x180020e8b  mov     [rsp+2F8h+var_290], 1
0x180020e90  lea     rdx, [rsp+2F8h+var_2C4]
0x180020e95  lea     rcx, [rsp+2F8h+var_298]
0x180020e9a  call    cs:__imp_ManageCI_GetAllCIPolicies
0x180020ea0  mov     rcx, [rsp+2F8h]; this
0x180020ea8  test    eax, eax
0x180020eaa  jns     short loc_180020EBD
0x180020eac  mov     r9d, eax; char *
0x180020eaf  mov     r8, rbx; unsigned int
0x180020eb2  mov     edx, 37h ; '7'; void *
0x180020eb7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020ebd  lea     rcx, [rsp+2F8h+var_2A0]
0x180020ec2  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@U_GUID@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180020ec7  mov     edi, r15d
0x180020eca  cmp     edi, [rsp+2F8h+var_2C4]
0x180020ece  jnb     short loc_180020F28
0x180020ed0  mov     [rsp+2F8h+var_2C8], r15b
0x180020ed5  mov     esi, edi
0x180020ed7  shl     rsi, 4
0x180020edb  mov     rcx, [rsp+2F8h+hMem]
0x180020ee0  add     rcx, rsi
0x180020ee3  lea     r8, [rsp+2F8h+var_2C8]
0x180020ee8  mov     edx, 1
0x180020eed  call    cs:__imp_ManageCI_ShouldIgnoreRemoval
0x180020ef3  mov     rcx, [rsp+2F8h]; this
0x180020efb  test    eax, eax
0x180020efd  jns     short loc_180020F0F
0x180020eff  mov     r9d, eax; char *
0x180020f02  mov     r8, rbx; unsigned int
0x180020f05  mov     edx, 3Ch ; '<'; void *
0x180020f0a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020f0f  cmp     [rsp+2F8h+var_2C8], r15b
0x180020f14  jnz     short loc_180020F24
0x180020f16  mov     rcx, [rsp+2F8h+hMem]
0x180020f1b  add     rcx, rsi
0x180020f1e  call    cs:__imp_ManageCI_BeginRemoveCIPolicy
0x180020f24  inc     edi
0x180020f26  jmp     short loc_180020ECA
0x180020f28  lea     rax, [rsp+2F8h+var_2B8]
0x180020f2d  mov     [rsp+2F8h+var_2A0], rax
0x180020f32  mov     [rsp+2F8h+var_298], r15
0x180020f37  mov     [rsp+2F8h+var_290], 1
0x180020f3c  lea     rdx, [rsp+2F8h+var_2B0]
0x180020f41  lea     rcx, [rsp+2F8h+var_298]
0x180020f46  call    cs:__imp_ManageCI_GetAllSBCPTokens
0x180020f4c  mov     rcx, [rsp+2F8h]; this
0x180020f54  test    eax, eax
0x180020f56  jns     short loc_180020F69
0x180020f58  mov     r9d, eax; char *
0x180020f5b  mov     r8, rbx; unsigned int
0x180020f5e  mov     edx, 44h ; 'D'; void *
0x180020f63  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020f69  lea     rcx, [rsp+2F8h+var_2A0]
0x180020f6e  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@U_GUID@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180020f73  mov     edi, r15d
0x180020f76  cmp     [rsp+2F8h+var_2B0], r15d
0x180020f7b  jbe     short loc_180020F96
0x180020f7d  mov     eax, edi
0x180020f7f  mov     rcx, [rsp+2F8h+var_2B8]
0x180020f84  mov     rcx, [rcx+rax*8]
0x180020f88  call    cs:__imp_ManageCI_BeginRemoveSBCPToken
0x180020f8e  inc     edi
0x180020f90  cmp     edi, [rsp+2F8h+var_2B0]
0x180020f94  jb      short loc_180020F7D
0x180020f96  call    cs:__imp_ManageCI_ValidateState
0x180020f9c  mov     rcx, [rsp+2F8h]; this
0x180020fa4  test    eax, eax
0x180020fa6  jns     short loc_180020FB8
0x180020fa8  mov     r9d, eax; char *
0x180020fab  mov     r8, rbx; unsigned int
0x180020fae  mov     edx, 4Ah ; 'J'; void *
0x180020fb3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020fb8  call    cs:__imp_ManageCI_Commit
0x180020fbe  mov     rcx, [rsp+2F8h]; this
0x180020fc6  test    eax, eax
0x180020fc8  jns     short loc_180020FDA
0x180020fca  mov     r9d, eax; char *
0x180020fcd  mov     r8, rbx; unsigned int
0x180020fd0  mov     edx, 4Bh ; 'K'; void *
0x180020fd5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020fda  call    cs:__imp_ManageCI_End
0x180020fe0  mov     rcx, [rsp+2F8h]; this
0x180020fe8  test    eax, eax
0x180020fea  jns     short loc_180020FFC
0x180020fec  mov     r9d, eax; char *
0x180020fef  mov     r8, rbx; unsigned int
0x180020ff2  mov     edx, 4Dh ; 'M'; void *
0x180020ff7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020ffc  lea     rdx, [rsp+2F8h+var_288]; unsigned __int16 *
0x180021001  mov     rcx, r14; this
0x180021004  call    ?get_KeyAsString@ActivityContext@@QEAAJQEAG@Z; ActivityContext::get_KeyAsString(ushort * const)
0x180021009  mov     rcx, [rsp+2F8h]; this
0x180021011  test    eax, eax
0x180021013  jns     short loc_180021025
0x180021015  mov     r9d, eax; char *
0x180021018  mov     r8, rbx; unsigned int
0x18002101b  mov     edx, 50h ; 'P'; void *
0x180021020  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180021025  mov     qword ptr [rsp+2F8h+phkResult], r15; int
0x18002102a  mov     r9d, 20Ah
0x180021030  lea     r8, [rsp+2F8h+SubKey]
0x180021038  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\CI"...
0x18002103f  lea     rcx, aCienrollments; "CIEnrollments"
0x180021046  call    cs:__imp_GetPersistedRegistryLocationW
0x18002104c  mov     esi, 80070000h
0x180021051  test    eax, eax
0x180021053  jle     short loc_18002105A
0x180021055  movzx   eax, ax
0x180021058  or      eax, esi
0x18002105a  mov     rcx, [rsp+2F8h]; this
0x180021062  test    eax, eax
0x180021064  jns     short loc_180021076
0x180021066  mov     r9d, eax; char *
0x180021069  mov     r8, rbx; unsigned int
0x18002106c  mov     edx, 58h ; 'X'; void *
0x180021071  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180021076  lea     r8, asc_18007FF94; "\\"
0x18002107d  mov     edi, 105h
0x180021082  mov     edx, edi; unsigned __int64
0x180021084  lea     rcx, [rsp+2F8h+SubKey]; unsigned __int16 *
0x18002108c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180021091  mov     rcx, [rsp+2F8h]; this
0x180021099  test    eax, eax
0x18002109b  jns     short loc_1800210AD
0x18002109d  mov     r9d, eax; char *
0x1800210a0  mov     r8, rbx; unsigned int
0x1800210a3  mov     edx, 5Ah ; 'Z'; void *
0x1800210a8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800210ad  lea     r8, [rsp+2F8h+var_288]; unsigned __int16 *
0x1800210b2  mov     rdx, rdi; unsigned __int64
0x1800210b5  lea     rcx, [rsp+2F8h+SubKey]; unsigned __int16 *
0x1800210bd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800210c2  mov     rcx, [rsp+2F8h]; this
0x1800210ca  test    eax, eax
0x1800210cc  jns     short loc_1800210DE
0x1800210ce  mov     r9d, eax; char *
0x1800210d1  mov     r8, rbx; unsigned int
0x1800210d4  mov     edx, 5Bh ; '['; void *
0x1800210d9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800210de  lea     rax, [rsp+2F8h+hKey]
0x1800210e3  mov     [rsp+2F8h+var_2A0], rax
0x1800210e8  mov     [rsp+2F8h+var_298], r15
0x1800210ed  mov     [rsp+2F8h+var_290], 1
0x1800210f2  lea     rax, [rsp+2F8h+var_298]
0x1800210f7  mov     qword ptr [rsp+2F8h+phkResult], rax; int
0x1800210fc  mov     r9d, 2000Fh; samDesired
0x180021102  xor     r8d, r8d; ulOptions
0x180021105  lea     rdx, [rsp+2F8h+SubKey]; lpSubKey
0x18002110d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021114  call    cs:__imp_RegOpenKeyExW
0x18002111a  mov     edi, eax
0x18002111c  test    eax, eax
0x18002111e  jle     short loc_180021125
0x180021120  movzx   edi, ax
0x180021123  or      edi, esi
0x180021125  lea     rcx, [rsp+2F8h+var_2A0]
0x18002112a  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18002112f  test    edi, edi
0x180021131  js      short loc_1800211AB
0x180021133  xor     edx, edx; lpSubKey
0x180021135  mov     rcx, [rsp+2F8h+hKey]; hKey
0x18002113a  call    cs:__imp_RegDeleteTreeW
0x180021140  test    eax, eax
0x180021142  jle     short loc_180021149
0x180021144  movzx   eax, ax
0x180021147  or      eax, esi
0x180021149  mov     rcx, [rsp+2F8h]; this
0x180021151  test    eax, eax
0x180021153  jns     short loc_180021165
0x180021155  mov     r9d, eax; char *
0x180021158  mov     r8, rbx; unsigned int
0x18002115b  mov     edx, 6Ah ; 'j'; void *
0x180021160  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180021165  xor     edx, edx
0x180021167  lea     rcx, [rsp+2F8h+hKey]
0x18002116c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180021171  lea     rdx, [rsp+2F8h+SubKey]; lpSubKey
0x180021179  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021180  call    cs:__imp_RegDeleteKeyW
0x180021186  test    eax, eax
0x180021188  jle     short loc_18002118F
0x18002118a  movzx   eax, ax
0x18002118d  or      eax, esi
0x18002118f  mov     rcx, [rsp+2F8h]; this
0x180021197  test    eax, eax
0x180021199  jns     short loc_1800211C3
0x18002119b  mov     r9d, eax; char *
0x18002119e  mov     r8, rbx; unsigned int
0x1800211a1  mov     edx, 72h ; 'r'; void *
0x1800211a6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800211ab  cmp     edi, 80070002h
0x1800211b1  jz      short loc_1800211C3
0x1800211b3  mov     rcx, [rsp+2F8h]; this
0x1800211bb  mov     r9d, edi; char *
0x1800211be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800211c3  mov     edx, [r14+3CCh]
0x1800211ca  lea     rcx, [rsp+2F8h+var_288]
0x1800211cf  call    ?InstrumentUnenroll@ManageCIProvider@@SAXPEBGW4EnrollmentEnrollType@@@Z; ManageCIProvider::InstrumentUnenroll(ushort const *,EnrollmentEnrollType)
0x1800211d4  nop
0x1800211d5  mov     rcx, [rsp+2F8h+hKey]; hKey
0x1800211da  test    rcx, rcx
  ... truncated ...
```
