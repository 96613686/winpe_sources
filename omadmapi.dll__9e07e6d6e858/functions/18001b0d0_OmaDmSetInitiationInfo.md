# OmaDmSetInitiationInfo

- ea: `0x18001b0d0`
- end: `0x18001b58f`
- name: `OmaDmSetInitiationInfo`
- size: `1215`
- prototype: `__int64 __fastcall(void *, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180019684`

## callees

- `0x1800031b0`
- `0x180003db8`
- `0x1800075f0`
- `0x180007930`
- `0x180008600`
- `0x18000979c`
- `0x180009bf4`
- `0x180009ec8`
- `0x18000c718`
- `0x18000c974`
- `0x18000ca60`
- `0x18000e004`
- `0x18000e0f0`
- `0x180011920`
- `0x180013df4`
- `0x18001b0d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b363`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b387`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b4fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b523`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b533`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b363`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b387`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b4fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b523`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b533`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b31a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b31a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001b22b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001b33b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001b550`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001b22b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001b33b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001b550`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001b287`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001b492`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001b287`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001b492`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x18001b3e1`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x18001b3e1`

## string_xrefs

- `0x18001b3d5`: `SessionAutoDeleteKey`

## pseudocode

```c
__int64 __fastcall OmaDmSetInitiationInfo(WCHAR *a1, __int64 a2, unsigned int a3)
{
  int v3; // r13d
  HKEY v7; // rsi
  __int64 v8; // rdx
  const unsigned __int16 *v9; // rcx
  signed int IndexedString; // ebx
  __int64 v11; // rcx
  unsigned int v12; // r8d
  int AccountRootKeyByInitiationId; // eax
  LSTATUS v14; // eax
  bool v15; // cc
  HKEY *v16; // rax
  const WCHAR *v17; // rdx
  const WCHAR *v18; // rdx
  unsigned int v19; // r14d
  __int64 v20; // rax
  unsigned __int64 v21; // r15
  __int64 v22; // r9
  HKEY v24; // [rsp+50h] [rbp-89h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-81h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-79h] BYREF
  HKEY v27; // [rsp+68h] [rbp-71h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-69h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp-61h] BYREF
  __int64 v30; // [rsp+80h] [rbp-59h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+88h] [rbp-51h] BYREF
  __int128 v32; // [rsp+98h] [rbp-41h]
  WCHAR SubKey[32]; // [rsp+B0h] [rbp-29h] BYREF

  v3 = 0;
  hObject = 0;
  phkResult = 0;
  v27 = 0;
  dwDisposition = 0;
  memset_0(SubKey, 0, sizeof(SubKey));
  hKey = 0;
  v7 = 0;
  if ( !a2 || *(_DWORD *)a2 != 64 || !(unsigned int)IsValidInitiationID(a1) )
    goto LABEL_45;
  v9 = *(const unsigned __int16 **)(a2 + 56);
  if ( v9 && !(unsigned int)IsValidUserSid(v9) )
  {
    IndexedString = -2102788085;
    goto LABEL_46;
  }
  v11 = *(unsigned int *)(a2 + 16);
  if ( (_DWORD)v11 )
  {
    v11 = (unsigned int)(v11 - 1);
    if ( (_DWORD)v11 )
    {
      v11 = (unsigned int)(v11 - 1);
      if ( (_DWORD)v11 )
      {
        v11 = (unsigned int)(v11 - 1);
        if ( (unsigned int)v11 > 1 )
          goto LABEL_45;
      }
    }
  }
  IndexedString = 0;
  v12 = *(_DWORD *)Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor;
  if ( (*(_DWORD *)Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor & 4) == 0 )
  {
    v30 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask>::GetCachedFeatureEnabledState(
                       v11,
                       &v30);
    v12 = v30;
  }
  LODWORD(v24) = 0;
  WORD2(v24) = 3;
  wil::details::ReportUsageToService(&qword_180032C90, v8, (v12 >> 10) & 1, (v12 >> 11) & 1, &v24, 1);
  if ( *(_DWORD *)(a2 + 40) != 57 )
  {
    IndexedString = AcquireOmaDmMutex(&hObject);
    if ( IndexedString >= 0 )
    {
      AccountRootKeyByInitiationId = GetAccountRootKeyByInitiationId(a1, &hKey);
      v7 = hKey;
      IndexedString = AccountRootKeyByInitiationId;
      if ( AccountRootKeyByInitiationId >= 0 )
      {
        v14 = RegDeleteTreeW(hKey, a1);
        IndexedString = v14;
        if ( (v14 & 0xFFFFFFFD) != 0 )
        {
          v15 = v14 <= 0;
          goto LABEL_18;
        }
        v14 = RegCreateKeyExW(v7, a1, 0, 0, 0, 0x20106u, 0, &phkResult, &dwDisposition);
        IndexedString = v14;
        v15 = v14 <= 0;
        if ( v14 )
        {
LABEL_18:
          if ( !v15 )
            IndexedString = (unsigned __int16)v14 | 0x80070000;
          goto LABEL_46;
        }
        if ( dwDisposition != 1 )
        {
          IndexedString = -2147418113;
          goto LABEL_46;
        }
        if ( v7 == HKEY_LOCAL_MACHINE )
        {
          v24 = 0;
          *(_OWORD *)lpSubKey = 0;
          v32 = 0;
          std::wstring::_Construct<1,unsigned short const *>(lpSubKey, L"VirtualStore\\MACHINE\\", 21);
          std::wstring::append(lpSubKey, a1);
          v16 = (HKEY *)ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v24);
          v17 = (const WCHAR *)lpSubKey;
          if ( *((_QWORD *)&v32 + 1) > 7u )
            v17 = lpSubKey[0];
          if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, v17, 0, 0x20019u, v16) )
          {
            v18 = (const WCHAR *)lpSubKey;
            if ( *((_QWORD *)&v32 + 1) > 7u )
              v18 = lpSubKey[0];
            RegDeleteTreeW(HKEY_CLASSES_ROOT, v18);
            IndexedString = -2147024891;
            std::wstring::~wstring(lpSubKey);
            if ( v24 )
              RegCloseKey(v24);
            goto LABEL_46;
          }
          std::wstring::~wstring(lpSubKey);
          if ( v24 )
            RegCloseKey(v24);
        }
        IndexedString = SaveStructInRegistry(phkResult, 8, a2, 64, 0, 0);
        if ( IndexedString < 0 )
          goto LABEL_46;
        IndexedString = OmaDmRegistrySetDWORD(phkResult, 0, L"SessionAutoDeleteKey", a3);
        if ( IndexedString < 0 )
          goto LABEL_46;
        v19 = 0;
        if ( !*(_DWORD *)(a2 + 32) )
          goto LABEL_46;
        while ( 1 )
        {
          v20 = *(_QWORD *)(a2 + 24);
          v21 = (unsigned __int64)v19 << 6;
          if ( *(_DWORD *)(v21 + v20) == 64 )
          {
            v3 = 1;
          }
          else if ( *(_DWORD *)(v21 + v20) != 56 )
          {
            break;
          }
          if ( !*(_QWORD *)(v21 + v20 + 24) )
            break;
          IndexedString = GenerateIndexedString(L"Alert", v19, SubKey, 0x20u);
          if ( IndexedString < 0 )
            goto LABEL_46;
          v14 = RegCreateKeyExW(phkResult, SubKey, 0, 0, 0, 0x20106u, 0, &v27, &dwDisposition);
          IndexedString = v14;
          v15 = v14 <= 0;
          if ( v14 )
            goto LABEL_18;
          v22 = 2LL * v3;
          v3 = 0;
          IndexedString = SaveStructInRegistry(
                            v27,
                            (int)(&off_180025C38)[v22 + 1],
                            v21 + *(_QWORD *)(a2 + 24),
                            64,
                            0,
                            0);
          if ( IndexedString >= 0 )
          {
            RegCloseKey(v27);
            ++v19;
            v27 = 0;
            if ( v19 < *(_DWORD *)(a2 + 32) )
              continue;
          }
          goto LABEL_46;
        }
LABEL_45:
        IndexedString = -2147024809;
      }
    }
  }
LABEL_46:
  RegCloseKey(phkResult);
  RegCloseKey(v27);
  if ( IndexedString < 0 && phkResult )
    RegDeleteTreeW(v7, a1);
  ReleaseOmaDmMutex(hObject);
  return (unsigned int)IndexedString;
}

```

## disassembly

```asm
0x18001b0d0  mov     [rsp-8+arg_18], rbx
0x18001b0d5  push    rbp
0x18001b0d6  push    rsi
0x18001b0d7  push    rdi
0x18001b0d8  push    r12
0x18001b0da  push    r13
0x18001b0dc  push    r14
0x18001b0de  push    r15
0x18001b0e0  lea     rbp, [rsp-27h]
0x18001b0e5  sub     rsp, 100h
0x18001b0ec  mov     rax, cs:__security_cookie
0x18001b0f3  xor     rax, rsp
0x18001b0f6  mov     [rbp+57h+var_40], rax
0x18001b0fa  xor     r13d, r13d
0x18001b0fd  mov     r14d, r8d
0x18001b100  mov     rdi, rdx
0x18001b103  mov     [rbp+57h+hObject], r13
0x18001b107  mov     r12, rcx
0x18001b10a  mov     [rbp+57h+var_D0], r13
0x18001b10e  xor     edx, edx; Val
0x18001b110  mov     [rbp+57h+var_C8], r13
0x18001b114  lea     r8d, [r13+40h]; Size
0x18001b118  mov     [rsp+130h+dwDisposition], r13d
0x18001b11d  lea     rcx, [rbp+57h+SubKey]; void *
0x18001b121  call    memset_0
0x18001b126  mov     [rbp+57h+hKey], r13
0x18001b12a  mov     esi, r13d
0x18001b12d  test    rdi, rdi
0x18001b130  jz      loc_18001B51A
0x18001b136  cmp     dword ptr [rdi], 40h ; '@'
0x18001b139  jnz     loc_18001B51A
0x18001b13f  mov     rcx, r12
0x18001b142  call    IsValidInitiationID
0x18001b147  test    eax, eax
0x18001b149  jz      loc_18001B51A
0x18001b14f  mov     rcx, [rdi+38h]; unsigned __int16 *
0x18001b153  test    rcx, rcx
0x18001b156  jz      short loc_18001B16B
0x18001b158  call    ?IsValidUserSid@@YAHPEBG@Z; IsValidUserSid(ushort const *)
0x18001b15d  test    eax, eax
0x18001b15f  jnz     short loc_18001B16B
0x18001b161  mov     ebx, 82AA000Bh
0x18001b166  jmp     loc_18001B51F
0x18001b16b  mov     ecx, [rdi+10h]
0x18001b16e  test    ecx, ecx
0x18001b170  jz      short loc_18001B18A
0x18001b172  sub     ecx, 1
0x18001b175  jz      short loc_18001B18A
0x18001b177  sub     ecx, 1
0x18001b17a  jz      short loc_18001B18A
0x18001b17c  sub     ecx, 1
0x18001b17f  jz      short loc_18001B18A
0x18001b181  cmp     ecx, 1
0x18001b184  jnz     loc_18001B51A
0x18001b18a  mov     rax, cs:Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor
0x18001b191  mov     ebx, r13d
0x18001b194  mov     r8d, [rax]
0x18001b197  test    r8b, 4
0x18001b19b  jnz     short loc_18001B1B0
0x18001b19d  lea     rdx, [rbp+57h+var_B0]
0x18001b1a1  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask>::GetCachedFeatureEnabledState(void)
0x18001b1a6  mov     rcx, [rax]
0x18001b1a9  mov     [rbp+57h+var_B0], rcx
0x18001b1ad  mov     r8d, ecx
0x18001b1b0  mov     r9d, r8d
0x18001b1b3  mov     dword ptr [rsp+130h+var_E0], r13d
0x18001b1b8  mov     r15d, 1
0x18001b1be  shr     r9d, 0Bh
0x18001b1c2  shr     r8d, 0Ah
0x18001b1c6  lea     rax, [rsp+130h+var_E0]
0x18001b1cb  and     r9d, r15d
0x18001b1ce  mov     [rsp+130h+samDesired], r15d
0x18001b1d3  and     r8d, r15d
0x18001b1d6  mov     word ptr [rsp+130h+var_E0+4], 3
0x18001b1dd  lea     rcx, qword_180032C90
0x18001b1e4  mov     qword ptr [rsp+130h+dwOptions], rax
0x18001b1e9  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18001b1ee  cmp     dword ptr [rdi+28h], 39h ; '9'
0x18001b1f2  jz      loc_18001B51F
0x18001b1f8  lea     rcx, [rbp+57h+hObject]; void **
0x18001b1fc  call    ?AcquireOmaDmMutex@@YAJPEAPEAX@Z; AcquireOmaDmMutex(void * *)
0x18001b201  mov     ebx, eax
0x18001b203  test    eax, eax
0x18001b205  js      loc_18001B51F
0x18001b20b  lea     rdx, [rbp+57h+hKey]
0x18001b20f  mov     rcx, r12
0x18001b212  call    GetAccountRootKeyByInitiationId
0x18001b217  mov     rsi, [rbp+57h+hKey]
0x18001b21b  mov     ebx, eax
0x18001b21d  test    eax, eax
0x18001b21f  js      loc_18001B51F
0x18001b225  mov     rdx, r12; lpSubKey
0x18001b228  mov     rcx, rsi; hKey
0x18001b22b  call    cs:__imp_RegDeleteTreeW
0x18001b232  nop     dword ptr [rax+rax+00h]
0x18001b237  mov     ebx, eax
0x18001b239  test    eax, 0FFFFFFFDh
0x18001b23e  jz      short loc_18001B256
0x18001b240  test    eax, eax
0x18001b242  jle     loc_18001B51F
0x18001b248  movzx   ebx, ax
0x18001b24b  or      ebx, 80070000h
0x18001b251  jmp     loc_18001B51F
0x18001b256  lea     rax, [rsp+130h+dwDisposition]
0x18001b25b  xor     r9d, r9d; lpClass
0x18001b25e  mov     [rsp+130h+lpdwDisposition], rax; lpdwDisposition
0x18001b263  xor     r8d, r8d; Reserved
0x18001b266  lea     rax, [rbp+57h+var_D0]
0x18001b26a  mov     rdx, r12; lpSubKey
0x18001b26d  mov     [rsp+130h+phkResult], rax; phkResult
0x18001b272  mov     rcx, rsi; hKey
0x18001b275  mov     [rsp+130h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18001b27a  mov     [rsp+130h+samDesired], 20106h; samDesired
0x18001b282  mov     [rsp+130h+dwOptions], r13d; dwOptions
0x18001b287  call    cs:__imp_RegCreateKeyExW
0x18001b28e  nop     dword ptr [rax+rax+00h]
0x18001b293  mov     ebx, eax
0x18001b295  test    eax, eax
0x18001b297  jnz     short loc_18001B242
0x18001b299  cmp     [rsp+130h+dwDisposition], r15d
0x18001b29e  jz      short loc_18001B2AA
0x18001b2a0  mov     ebx, 8000FFFFh
0x18001b2a5  jmp     loc_18001B51F
0x18001b2aa  cmp     rsi, 0FFFFFFFF80000002h
0x18001b2b1  jnz     loc_18001B393
0x18001b2b7  xorps   xmm0, xmm0
0x18001b2ba  mov     [rsp+130h+var_E0], r13
0x18001b2bf  xorps   xmm1, xmm1
0x18001b2c2  lea     rdx, aVirtualstoreMa; "VirtualStore\\MACHINE\\"
0x18001b2c9  mov     r8d, 15h
0x18001b2cf  lea     rcx, [rbp+57h+lpSubKey]
0x18001b2d3  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x18001b2d7  movdqu  [rbp+57h+var_98], xmm1
0x18001b2dc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001b2e1  mov     rdx, r12; void *
0x18001b2e4  lea     rcx, [rbp+57h+lpSubKey]; Src
0x18001b2e8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001b2ed  lea     rcx, [rsp+130h+var_E0]
0x18001b2f2  call    ??$replace@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18001b2f7  cmp     qword ptr [rbp+57h+var_98+8], 7
0x18001b2fc  lea     rdx, [rbp+57h+lpSubKey]
0x18001b300  lea     rbx, [rsi-2]
0x18001b304  mov     qword ptr [rsp+130h+dwOptions], rax; phkResult
0x18001b309  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18001b30e  mov     r9d, 20019h; samDesired
0x18001b314  xor     r8d, r8d; ulOptions
0x18001b317  mov     rcx, rbx; hKey
0x18001b31a  call    cs:__imp_RegOpenKeyExW
0x18001b321  nop     dword ptr [rax+rax+00h]
0x18001b326  test    eax, eax
0x18001b328  jnz     short loc_18001B374
0x18001b32a  cmp     qword ptr [rbp+57h+var_98+8], 7
0x18001b32f  lea     rdx, [rbp+57h+lpSubKey]
0x18001b333  mov     rcx, rbx; hKey
0x18001b336  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18001b33b  call    cs:__imp_RegDeleteTreeW
0x18001b342  nop     dword ptr [rax+rax+00h]
0x18001b347  lea     rcx, [rbp+57h+lpSubKey]
0x18001b34b  mov     ebx, 80070005h
0x18001b350  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b355  mov     rcx, [rsp+130h+var_E0]; hKey
0x18001b35a  test    rcx, rcx
0x18001b35d  jz      loc_18001B51F
0x18001b363  call    cs:__imp_RegCloseKey
0x18001b36a  nop     dword ptr [rax+rax+00h]
0x18001b36f  jmp     loc_18001B51F
0x18001b374  lea     rcx, [rbp+57h+lpSubKey]
0x18001b378  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b37d  mov     rcx, [rsp+130h+var_E0]; hKey
0x18001b382  test    rcx, rcx
0x18001b385  jz      short loc_18001B393
0x18001b387  call    cs:__imp_RegCloseKey
0x18001b38e  nop     dword ptr [rax+rax+00h]
0x18001b393  mov     rcx, [rbp+57h+var_D0]; hKey
0x18001b397  lea     r9, off_180025EC0; "UIMode"
0x18001b39e  mov     dword ptr [rsp+130h+lpdwDisposition], r13d; unsigned int
0x18001b3a3  xor     r8d, r8d
0x18001b3a6  mov     [rsp+130h+phkResult], r13; unsigned __int8 *
0x18001b3ab  xor     edx, edx
0x18001b3ad  mov     dword ptr [rsp+130h+lpSecurityAttributes], 40h ; '@'; int
0x18001b3b5  mov     qword ptr [rsp+130h+samDesired], rdi; __int64
0x18001b3ba  mov     [rsp+130h+dwOptions], 8; int
0x18001b3c2  call    SaveStructInRegistry
0x18001b3c7  mov     ebx, eax
0x18001b3c9  test    eax, eax
0x18001b3cb  js      loc_18001B51F
0x18001b3d1  mov     rcx, [rbp+57h+var_D0]
0x18001b3d5  lea     r8, aSessionautodel; "SessionAutoDeleteKey"
0x18001b3dc  mov     r9d, r14d
0x18001b3df  xor     edx, edx
0x18001b3e1  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18001b3e8  nop     dword ptr [rax+rax+00h]
0x18001b3ed  mov     ebx, eax
0x18001b3ef  test    eax, eax
0x18001b3f1  js      loc_18001B51F
0x18001b3f7  mov     r14d, r13d
0x18001b3fa  cmp     [rdi+20h], r13d
0x18001b3fe  jbe     loc_18001B51F
0x18001b404  mov     rax, [rdi+18h]
0x18001b408  mov     r15d, r14d
0x18001b40b  shl     r15, 6
0x18001b40f  cmp     dword ptr [r15+rax], 40h ; '@'
0x18001b414  jnz     short loc_18001B41E
0x18001b416  mov     r13d, 1
0x18001b41c  jmp     short loc_18001B429
0x18001b41e  cmp     dword ptr [r15+rax], 38h ; '8'
0x18001b423  jnz     loc_18001B51A
0x18001b429  cmp     qword ptr [r15+rax+18h], 0
0x18001b42f  jz      loc_18001B51A
0x18001b435  mov     r9d, 20h ; ' '; unsigned int
0x18001b43b  lea     r8, [rbp+57h+SubKey]; unsigned __int16 *
0x18001b43f  mov     edx, r14d; unsigned int
0x18001b442  lea     rcx, aAlert; "Alert"
0x18001b449  call    ?GenerateIndexedString@@YAJPEBGKPEAGK@Z; GenerateIndexedString(ushort const *,ulong,ushort *,ulong)
0x18001b44e  mov     ebx, eax
0x18001b450  test    eax, eax
0x18001b452  js      loc_18001B51F
0x18001b458  mov     rcx, [rbp+57h+var_D0]; hKey
0x18001b45c  lea     rax, [rsp+130h+dwDisposition]
0x18001b461  mov     [rsp+130h+lpdwDisposition], rax; lpdwDisposition
0x18001b466  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18001b46a  lea     rax, [rbp+57h+var_C8]
0x18001b46e  xor     r9d, r9d; lpClass
0x18001b471  mov     [rsp+130h+phkResult], rax; phkResult
0x18001b476  xor     r8d, r8d; Reserved
0x18001b479  mov     [rsp+130h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001b482  mov     [rsp+130h+samDesired], 20106h; samDesired
0x18001b48a  mov     [rsp+130h+dwOptions], 0; dwOptions
0x18001b492  call    cs:__imp_RegCreateKeyExW
0x18001b499  nop     dword ptr [rax+rax+00h]
0x18001b49e  mov     ebx, eax
0x18001b4a0  test    eax, eax
0x18001b4a2  jnz     loc_18001B242
0x18001b4a8  mov     rcx, [rdi+18h]
0x18001b4ac  xor     r8d, r8d
0x18001b4af  add     rcx, r15
0x18001b4b2  movsxd  r9, r13d
0x18001b4b5  add     r9, r9
0x18001b4b8  xor     r13d, r13d
0x18001b4bb  mov     dword ptr [rsp+130h+lpdwDisposition], r13d; unsigned int
0x18001b4c0  xor     edx, edx
0x18001b4c2  mov     [rsp+130h+phkResult], r13; unsigned __int8 *
0x18001b4c7  mov     dword ptr [rsp+130h+lpSecurityAttributes], 40h ; '@'; int
0x18001b4cf  mov     qword ptr [rsp+130h+samDesired], rcx; __int64
0x18001b4d4  lea     rcx, off_180025C38
0x18001b4db  mov     eax, [rcx+r9*8+8]
0x18001b4e0  mov     r9, [rcx+r9*8]
0x18001b4e4  mov     rcx, [rbp+57h+var_C8]; hKey
0x18001b4e8  mov     [rsp+130h+dwOptions], eax; int
0x18001b4ec  call    SaveStructInRegistry
0x18001b4f1  mov     ebx, eax
0x18001b4f3  test    eax, eax
0x18001b4f5  js      short loc_18001B51F
0x18001b4f7  mov     rcx, [rbp+57h+var_C8]; hKey
0x18001b4fb  call    cs:__imp_RegCloseKey
0x18001b502  nop     dword ptr [rax+rax+00h]
0x18001b507  inc     r14d
0x18001b50a  mov     [rbp+57h+var_C8], r13
0x18001b50e  cmp     r14d, [rdi+20h]
0x18001b512  jb      loc_18001B404
0x18001b518  jmp     short loc_18001B51F
0x18001b51a  mov     ebx, 80070057h
0x18001b51f  mov     rcx, [rbp+57h+var_D0]; hKey
0x18001b523  call    cs:__imp_RegCloseKey
0x18001b52a  nop     dword ptr [rax+rax+00h]
0x18001b52f  mov     rcx, [rbp+57h+var_C8]; hKey
0x18001b533  call    cs:__imp_RegCloseKey
0x18001b53a  nop     dword ptr [rax+rax+00h]
0x18001b53f  test    ebx, ebx
0x18001b541  jns     short loc_18001B55C
0x18001b543  cmp     [rbp+57h+var_D0], 0
0x18001b548  jz      short loc_18001B55C
0x18001b54a  mov     rdx, r12; lpSubKey
0x18001b54d  mov     rcx, rsi; hKey
0x18001b550  call    cs:__imp_RegDeleteTreeW
0x18001b557  nop     dword ptr [rax+rax+00h]
0x18001b55c  mov     rcx, [rbp+57h+hObject]; hObject
0x18001b560  call    ?ReleaseOmaDmMutex@@YAXPEAX@Z; ReleaseOmaDmMutex(void *)
0x18001b565  mov     eax, ebx
0x18001b567  mov     rcx, [rbp+57h+var_40]
0x18001b56b  xor     rcx, rsp; StackCookie
0x18001b56e  call    __security_check_cookie
0x18001b573  mov     rbx, [rsp+130h+arg_18]
0x18001b57b  add     rsp, 100h
0x18001b582  pop     r15
0x18001b584  pop     r14
0x18001b586  pop     r13
0x18001b588  pop     r12
0x18001b58a  pop     rdi
0x18001b58b  pop     rsi
0x18001b58c  pop     rbp
0x18001b58d  retn
```
