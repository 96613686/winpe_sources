# FwMoneisInitialize

- ea: `0x1800b80c0`
- end: `0x1800b879a`
- name: `FwMoneisInitialize`
- size: `1754`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000177c`
- `0x18000ae9c`
- `0x18000af3c`
- `0x18005cf9c`
- `0x180069bb4`
- `0x18006f520`
- `0x18006f614`
- `0x18006ffc8`
- `0x180073480`
- `0x1800b4880`
- `0x1800b4a80`
- `0x1800b4cb0`
- `0x1800b4df0`
- `0x1800b4e50`
- `0x1800b4eb0`
- `0x1800b5480`
- `0x1800b80c0`
- `0x1800b913c`
- `0x1800bb440`
- `0x1800bdfe0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b842c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b842c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800b8417`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800b8417`
- `fwbase!FwRegQueryDWord` at `0x1800b83ed`
- `fwbase!FwRegQueryDWord` at `0x1800b83ed`
- `fwbase!FwHResultToWindowsError` at `0x1800b84bd`
- `fwbase!FwHResultToWindowsError` at `0x1800b854e`
- `fwbase!FwHResultToWindowsError` at `0x1800b8594`
- `fwbase!FwHResultToWindowsError` at `0x1800b85de`
- `fwbase!FwHResultToWindowsError` at `0x1800b8660`
- `fwbase!FwHResultToWindowsError` at `0x1800b86e2`
- `fwbase!FwHResultToWindowsError` at `0x1800b84bd`
- `fwbase!FwHResultToWindowsError` at `0x1800b854e`
- `fwbase!FwHResultToWindowsError` at `0x1800b8594`
- `fwbase!FwHResultToWindowsError` at `0x1800b85de`
- `fwbase!FwHResultToWindowsError` at `0x1800b8660`
- `fwbase!FwHResultToWindowsError` at `0x1800b86e2`
- `fwbase!FwCriticalSectionCreate` at `0x1800b8546`
- `fwbase!FwCriticalSectionCreate` at `0x1800b858c`
- `fwbase!FwCriticalSectionCreate` at `0x1800b85d6`
- `fwbase!FwCriticalSectionCreate` at `0x1800b86da`
- `fwbase!FwCriticalSectionCreate` at `0x1800b8546`
- `fwbase!FwCriticalSectionCreate` at `0x1800b858c`
- `fwbase!FwCriticalSectionCreate` at `0x1800b85d6`
- `fwbase!FwCriticalSectionCreate` at `0x1800b86da`
- `FWPolicyIOMgr!FwOpenAppCDbPolicyStore` at `0x1800b84b5`
- `FWPolicyIOMgr!FwOpenAppCDbPolicyStore` at `0x1800b84b5`

## string_xrefs

- `0x1800b8366`: `ACService`
- `0x1800b82be`: `FwMoneisIntializeRegPaths`
- `0x1800b830f`: `FwMoneisInitializeSids`
- `0x1800b84c9`: `FwOpenAppCDbPolicyStore`
- `0x1800b8502`: `FwMoneisLoadAppCConfig`
- `0x1800b8425`: `ConvertStringSecurityDescriptorToSecurityDescriptorW`
- `0x1800b8627`: `FwMoneisLoadDaGPConfigHint`

## pseudocode

```c
__int64 FwMoneisInitialize()
{
  appIsolation::AppContainerDatabase *v0; // rax
  appIsolation::AppContainerDatabase *v1; // rbx
  appIsolation::AppContainerDatabase *v2; // rcx
  appIsolation::IsolationEvents **v3; // rax
  appIsolation::IsolationEvents *v4; // rdx
  appIsolation::IsolationEvents *v5; // rcx
  void *v6; // rcx
  appIsolation::EnterpriseDomainProtection **v7; // rax
  appIsolation::EnterpriseDomainProtection *v8; // rdx
  appIsolation::EnterpriseDomainProtection *v9; // rcx
  void *v10; // rcx
  PSID **v11; // rax
  PSID *v12; // rdx
  PSID *v13; // rcx
  void *v14; // rcx
  appIsolation::InboxAppContainerManager *v15; // rax
  appIsolation::InboxAppContainerManager *v16; // rbx
  appIsolation::InboxAppContainerManager *v17; // rcx
  int v18; // eax
  int v19; // ebx
  const char *v20; // rdi
  DWORD LastError; // eax
  __int64 v22; // rcx
  __int64 v23; // rdx
  int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  __int64 v31; // r8
  __int64 v32; // r9
  void *Block; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v35; // [rsp+38h] [rbp-C8h] BYREF
  __int32 v36; // [rsp+40h] [rbp-C0h] BYREF
  BOOL v37[3]; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 v38[264]; // [rsp+50h] [rbp-B0h] BYREF

  v37[0] = 0;
  memset_0(v38, 0, 0x208u);
  v0 = (appIsolation::AppContainerDatabase *)operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
  v1 = v0;
  if ( v0 )
    memset_0(v0, 0, 0x80u);
  else
    v1 = 0;
  v2 = gFwIsolationManager;
  gFwIsolationManager = v1;
  if ( v2 )
  {
    operator delete(v2);
    v1 = gFwIsolationManager;
  }
  if ( !v1 )
    return 2147942414LL;
  v3 = (appIsolation::IsolationEvents **)wil::make_unique_nothrow<appIsolation::IsolationEvents,>(&Block);
  v4 = *v3;
  *v3 = 0;
  v5 = ::Block;
  ::Block = v4;
  if ( v5 )
    operator delete(v5);
  v6 = Block;
  Block = 0;
  if ( v6 )
    operator delete(v6);
  if ( !::Block )
    return 2147942414LL;
  v7 = (appIsolation::EnterpriseDomainProtection **)wil::make_unique_nothrow<appIsolation::EnterpriseDomainProtection,>(&Block);
  v8 = *v7;
  *v7 = 0;
  v9 = gEnterpriseDomainProtectionManager;
  gEnterpriseDomainProtectionManager = v8;
  if ( v9 )
    operator delete(v9);
  v10 = Block;
  Block = 0;
  if ( v10 )
    operator delete(v10);
  if ( !gEnterpriseDomainProtectionManager )
    return 2147942414LL;
  v11 = (PSID **)wil::make_unique_nothrow<appIsolation::SidManagement,>(&Block);
  v12 = *v11;
  *v11 = 0;
  v13 = gSidManager;
  gSidManager = v12;
  if ( v13 )
    operator delete(v13);
  v14 = Block;
  Block = 0;
  if ( v14 )
    operator delete(v14);
  if ( !gSidManager )
    return 2147942414LL;
  v15 = (appIsolation::InboxAppContainerManager *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v16 = v15;
  if ( v15 )
    memset_0(v15, 0, 0x40u);
  else
    v16 = 0;
  v17 = gInboxAppContainerManager;
  gInboxAppContainerManager = v16;
  if ( v17 )
  {
    operator delete(v17);
    v16 = gInboxAppContainerManager;
  }
  if ( !v16 )
    return 2147942414LL;
  dword_18012C680 = 0;
  v18 = appIsolation::AppContainerDatabase::IntializeRegPaths(gFwIsolationManager);
  if ( v18 < 0 )
  {
    v19 = 0;
    v20 = "FwMoneisIntializeRegPaths";
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_Ds(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        24,
        (unsigned int)WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids,
        v18,
        (__int64)"FwMoneisIntializeRegPaths");
    goto LABEL_87;
  }
  v20 = "FwMoneisInitializeSids";
  LastError = appIsolation::SidManagement::InitializeSids(gSidManager);
  v19 = LastError;
  if ( LastError )
  {
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_87;
    v23 = 25;
    goto LABEL_37;
  }
  v24 = StringCchPrintfW(v38, 0x104u, L"%ls\\%ls", *((_QWORD *)gFwIsolationManager + 13), L"ACService");
  if ( v24 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_Ds(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        26,
        (unsigned int)WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids,
        v24,
        (__int64)"FwMoneisInitialize::StringCchPrintf");
    goto LABEL_87;
  }
  v36 = 0;
  FwRegQueryDWord(-2147483646, v38, L"TmpEdpAppHsviRefCnt", &v36, v37);
  _InterlockedExchange((volatile __int32 *)gEnterpriseDomainProtectionManager + 13, v36);
  v37[0] = ConvertStringSecurityDescriptorToSecurityDescriptorW((LPCWSTR)gSidManager[14], 1u, gSidManager + 15, 0);
  if ( !v37[0] )
  {
    v20 = "ConvertStringSecurityDescriptorToSecurityDescriptorW";
    LastError = GetLastError();
    v19 = LastError;
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_87;
    v23 = 27;
    goto LABEL_37;
  }
  LastError = appIsolation::IsolationEvents::FwMoneisRegistrationApiInitialize(::Block);
  v19 = LastError;
  if ( LastError )
  {
    v20 = "FwMoneisRegistrationApiInitialize";
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_87;
    v23 = 28;
    goto LABEL_37;
  }
  v25 = FwOpenAppCDbPolicyStore(0, 2, (char *)gFwIsolationManager + 96);
  LastError = FwHResultToWindowsError(v25);
  v19 = LastError;
  if ( LastError )
  {
    v20 = "FwOpenAppCDbPolicyStore";
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_87;
    v23 = 29;
    goto LABEL_37;
  }
  v20 = "FwMoneisLoadAppCConfig";
  LastError = appIsolation::AppContainerDatabase::LoadAppCConfig(gFwIsolationManager);
  v19 = LastError;
  if ( LastError )
  {
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_87;
    v23 = 30;
    goto LABEL_37;
  }
  v26 = FwCriticalSectionCreate(gFwIsolationManager);
  LastError = FwHResultToWindowsError(v26);
  v19 = LastError;
  if ( LastError )
  {
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_87;
    v23 = 31;
    goto LABEL_37;
  }
  v27 = FwCriticalSectionCreate(gEnterpriseDomainProtectionManager);
  LastError = FwHResultToWindowsError(v27);
  v19 = LastError;
  if ( LastError )
  {
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_87;
    v23 = 32;
    goto LABEL_37;
  }
  v28 = FwCriticalSectionCreate((char *)gFwIsolationManager + 48);
  LastError = FwHResultToWindowsError(v28);
  v19 = LastError;
  if ( LastError )
  {
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_87;
    v23 = 33;
    goto LABEL_37;
  }
  LastError = appIsolation::AppContainerDatabase::LoadDaGPConfigHint(gFwIsolationManager);
  v19 = LastError;
  if ( LastError )
  {
    v20 = "FwMoneisLoadDaGPConfigHint";
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_87;
    v23 = 34;
    goto LABEL_37;
  }
  v29 = FwMoneisDiagInitialize();
  LastError = FwHResultToWindowsError(v29);
  v19 = LastError;
  if ( LastError )
  {
    v20 = "FwMoneisDiagInitialize";
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_87;
    v23 = 35;
    goto LABEL_37;
  }
  v20 = "FwMoneisInboxAppCServicingInitialize";
  LastError = FwMoneisInboxAppCServicingInitialize();
  v19 = LastError;
  if ( LastError )
  {
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_87;
    v23 = 36;
    goto LABEL_37;
  }
  v30 = FwCriticalSectionCreate(&g_fwEventCriticalSection);
  LastError = FwHResultToWindowsError(v30);
  v19 = LastError;
  if ( LastError )
  {
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_87;
    v23 = 37;
LABEL_37:
    WPP_SF_d(*(_QWORD *)(v22 + 16), v23, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids, LastError);
    goto LABEL_87;
  }
  v20 = 0;
LABEL_87:
  if ( (unsigned int)dword_1801263B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801263B0, 0x4000000000000LL) )
  {
    LODWORD(Block) = v19;
    v35 = (__int64)v20;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (int)&dword_1801263B0,
      (int)byte_180110BD5,
      v31,
      v32,
      (const char **)&v35,
      (__int64)&Block);
  }
  if ( v19 > 0 )
    return (unsigned __int16)v19 | 0x80070000;
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1800b80c0  push    rbp
0x1800b80c2  push    rbx
0x1800b80c3  push    rsi
0x1800b80c4  push    rdi
0x1800b80c5  lea     rbp, [rsp-178h]
0x1800b80cd  sub     rsp, 278h
0x1800b80d4  mov     rax, cs:__security_cookie
0x1800b80db  xor     rax, rsp
0x1800b80de  mov     [rbp+190h+var_30], rax
0x1800b80e5  xor     esi, esi
0x1800b80e7  lea     rcx, [rsp+290h+var_240]; void *
0x1800b80ec  xor     edx, edx; Val
0x1800b80ee  mov     [rsp+290h+var_24C], esi
0x1800b80f2  mov     r8d, 208h; Size
0x1800b80f8  call    memset_0
0x1800b80fd  mov     edi, 80h
0x1800b8102  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b8109  mov     ecx, edi; unsigned __int64
0x1800b810b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800b8110  mov     rbx, rax
0x1800b8113  test    rax, rax
0x1800b8116  jz      short loc_1800B8127
0x1800b8118  mov     r8d, edi; Size
0x1800b811b  xor     edx, edx; Val
0x1800b811d  mov     rcx, rax; void *
0x1800b8120  call    memset_0
0x1800b8125  jmp     short loc_1800B812A
0x1800b8127  mov     rbx, rsi
0x1800b812a  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; Block
0x1800b8131  mov     cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A, rbx; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800b8138  test    rcx, rcx
0x1800b813b  jz      short loc_1800B814C
0x1800b813d  mov     rdx, rdi
0x1800b8140  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b8145  mov     rbx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800b814c  test    rbx, rbx
0x1800b814f  jz      loc_1800B877A
0x1800b8155  lea     rcx, [rsp+290h+Block]
0x1800b815a  call    ??$make_unique_nothrow@VIsolationEvents@appIsolation@@$$V@wil@@YA?AV?$unique_ptr@VIsolationEvents@appIsolation@@U?$default_delete@VIsolationEvents@appIsolation@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<appIsolation::IsolationEvents,>(void)
0x1800b815f  mov     ebx, 60h ; '`'
0x1800b8164  mov     rdx, [rax]
0x1800b8167  mov     [rax], rsi
0x1800b816a  mov     rcx, cs:Block; Block
0x1800b8171  mov     cs:Block, rdx
0x1800b8178  test    rcx, rcx
0x1800b817b  jz      short loc_1800B8184
0x1800b817d  mov     edx, ebx
0x1800b817f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b8184  mov     rcx, [rsp+290h+Block]; Block
0x1800b8189  mov     [rsp+290h+Block], rsi
0x1800b818e  test    rcx, rcx
0x1800b8191  jz      short loc_1800B819B
0x1800b8193  mov     rdx, rbx
0x1800b8196  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b819b  cmp     cs:Block, rsi
0x1800b81a2  jz      loc_1800B877A
0x1800b81a8  lea     rcx, [rsp+290h+Block]
0x1800b81ad  call    ??$make_unique_nothrow@VEnterpriseDomainProtection@appIsolation@@$$V@wil@@YA?AV?$unique_ptr@VEnterpriseDomainProtection@appIsolation@@U?$default_delete@VEnterpriseDomainProtection@appIsolation@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<appIsolation::EnterpriseDomainProtection,>(void)
0x1800b81b2  mov     ebx, 38h ; '8'
0x1800b81b7  mov     rdx, [rax]
0x1800b81ba  mov     [rax], rsi
0x1800b81bd  mov     rcx, cs:?gEnterpriseDomainProtectionManager@@3V?$unique_ptr@VEnterpriseDomainProtection@appIsolation@@U?$default_delete@VEnterpriseDomainProtection@appIsolation@@@wistd@@@wistd@@A; Block
0x1800b81c4  mov     cs:?gEnterpriseDomainProtectionManager@@3V?$unique_ptr@VEnterpriseDomainProtection@appIsolation@@U?$default_delete@VEnterpriseDomainProtection@appIsolation@@@wistd@@@wistd@@A, rdx; wistd::unique_ptr<appIsolation::EnterpriseDomainProtection,wistd::default_delete<appIsolation::EnterpriseDomainProtection>> gEnterpriseDomainProtectionManager
0x1800b81cb  test    rcx, rcx
0x1800b81ce  jz      short loc_1800B81D7
0x1800b81d0  mov     edx, ebx
0x1800b81d2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b81d7  mov     rcx, [rsp+290h+Block]; Block
0x1800b81dc  mov     [rsp+290h+Block], rsi
0x1800b81e1  test    rcx, rcx
0x1800b81e4  jz      short loc_1800B81EE
0x1800b81e6  mov     rdx, rbx
0x1800b81e9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b81ee  cmp     cs:?gEnterpriseDomainProtectionManager@@3V?$unique_ptr@VEnterpriseDomainProtection@appIsolation@@U?$default_delete@VEnterpriseDomainProtection@appIsolation@@@wistd@@@wistd@@A, rsi; wistd::unique_ptr<appIsolation::EnterpriseDomainProtection,wistd::default_delete<appIsolation::EnterpriseDomainProtection>> gEnterpriseDomainProtectionManager
0x1800b81f5  jz      loc_1800B877A
0x1800b81fb  lea     rcx, [rsp+290h+Block]
0x1800b8200  call    ??$make_unique_nothrow@VSidManagement@appIsolation@@$$V@wil@@YA?AV?$unique_ptr@VSidManagement@appIsolation@@U?$default_delete@VSidManagement@appIsolation@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<appIsolation::SidManagement,>(void)
0x1800b8205  mov     ebx, 88h
0x1800b820a  mov     rdx, [rax]
0x1800b820d  mov     [rax], rsi
0x1800b8210  mov     rcx, cs:?gSidManager@@3V?$unique_ptr@VSidManagement@appIsolation@@U?$default_delete@VSidManagement@appIsolation@@@wistd@@@wistd@@A; Block
0x1800b8217  mov     cs:?gSidManager@@3V?$unique_ptr@VSidManagement@appIsolation@@U?$default_delete@VSidManagement@appIsolation@@@wistd@@@wistd@@A, rdx; wistd::unique_ptr<appIsolation::SidManagement,wistd::default_delete<appIsolation::SidManagement>> gSidManager
0x1800b821e  test    rcx, rcx
0x1800b8221  jz      short loc_1800B822A
0x1800b8223  mov     edx, ebx
0x1800b8225  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b822a  mov     rcx, [rsp+290h+Block]; Block
0x1800b822f  mov     [rsp+290h+Block], rsi
0x1800b8234  test    rcx, rcx
0x1800b8237  jz      short loc_1800B8241
0x1800b8239  mov     rdx, rbx
0x1800b823c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b8241  cmp     cs:?gSidManager@@3V?$unique_ptr@VSidManagement@appIsolation@@U?$default_delete@VSidManagement@appIsolation@@@wistd@@@wistd@@A, rsi; wistd::unique_ptr<appIsolation::SidManagement,wistd::default_delete<appIsolation::SidManagement>> gSidManager
0x1800b8248  jz      loc_1800B877A
0x1800b824e  mov     edi, 40h ; '@'
0x1800b8253  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b825a  mov     ecx, edi; unsigned __int64
0x1800b825c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800b8261  mov     rbx, rax
0x1800b8264  test    rax, rax
0x1800b8267  jz      short loc_1800B8278
0x1800b8269  mov     r8d, edi; Size
0x1800b826c  xor     edx, edx; Val
0x1800b826e  mov     rcx, rax; void *
0x1800b8271  call    memset_0
0x1800b8276  jmp     short loc_1800B827B
0x1800b8278  mov     rbx, rsi
0x1800b827b  mov     rcx, cs:?gInboxAppContainerManager@@3V?$unique_ptr@VInboxAppContainerManager@appIsolation@@U?$default_delete@VInboxAppContainerManager@appIsolation@@@wistd@@@wistd@@A; Block
0x1800b8282  mov     cs:?gInboxAppContainerManager@@3V?$unique_ptr@VInboxAppContainerManager@appIsolation@@U?$default_delete@VInboxAppContainerManager@appIsolation@@@wistd@@@wistd@@A, rbx; wistd::unique_ptr<appIsolation::InboxAppContainerManager,wistd::default_delete<appIsolation::InboxAppContainerManager>> gInboxAppContainerManager
0x1800b8289  test    rcx, rcx
0x1800b828c  jz      short loc_1800B829D
0x1800b828e  mov     rdx, rdi
0x1800b8291  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b8296  mov     rbx, cs:?gInboxAppContainerManager@@3V?$unique_ptr@VInboxAppContainerManager@appIsolation@@U?$default_delete@VInboxAppContainerManager@appIsolation@@@wistd@@@wistd@@A; wistd::unique_ptr<appIsolation::InboxAppContainerManager,wistd::default_delete<appIsolation::InboxAppContainerManager>> gInboxAppContainerManager
0x1800b829d  test    rbx, rbx
0x1800b82a0  jz      loc_1800B877A
0x1800b82a6  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; this
0x1800b82ad  mov     cs:dword_18012C680, esi
0x1800b82b3  call    ?IntializeRegPaths@AppContainerDatabase@appIsolation@@QEAAJXZ; appIsolation::AppContainerDatabase::IntializeRegPaths(void)
0x1800b82b8  test    eax, eax
0x1800b82ba  jns     short loc_1800B8308
0x1800b82bc  mov     ebx, esi
0x1800b82be  lea     rdi, aFwmoneisintial; "FwMoneisIntializeRegPaths"
0x1800b82c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b82cc  lea     rdx, WPP_GLOBAL_Control
0x1800b82d3  cmp     rcx, rdx
0x1800b82d6  jz      loc_1800B8714
0x1800b82dc  test    byte ptr [rcx+1Ch], 1
0x1800b82e0  jz      loc_1800B8714
0x1800b82e6  mov     edx, 18h
0x1800b82eb  mov     [rsp+290h+var_270], rdi
0x1800b82f0  mov     rcx, [rcx+10h]
0x1800b82f4  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x1800b82fb  mov     r9d, eax
0x1800b82fe  call    WPP_SF_Ds
0x1800b8303  jmp     loc_1800B8714
0x1800b8308  mov     rcx, cs:?gSidManager@@3V?$unique_ptr@VSidManagement@appIsolation@@U?$default_delete@VSidManagement@appIsolation@@@wistd@@@wistd@@A; Sid
0x1800b830f  lea     rdi, aFwmoneisinitia; "FwMoneisInitializeSids"
0x1800b8316  call    ?InitializeSids@SidManagement@appIsolation@@QEAAKXZ; appIsolation::SidManagement::InitializeSids(void)
0x1800b831b  mov     ebx, eax
0x1800b831d  test    eax, eax
0x1800b831f  jz      short loc_1800B835F
0x1800b8321  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b8328  lea     rdx, WPP_GLOBAL_Control
0x1800b832f  cmp     rcx, rdx
0x1800b8332  jz      loc_1800B8714
0x1800b8338  test    byte ptr [rcx+1Ch], 1
0x1800b833c  jz      loc_1800B8714
0x1800b8342  mov     edx, 19h
0x1800b8347  mov     rcx, [rcx+10h]
0x1800b834b  lea     r8, WPP_f2b9ef332e653b3ba80d2c59b36f5ad8_Traceguids
0x1800b8352  mov     r9d, eax
0x1800b8355  call    WPP_SF_d
0x1800b835a  jmp     loc_1800B8714
0x1800b835f  mov     r9, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800b8366  lea     rax, aAcservice; "ACService"
0x1800b836d  lea     r8, aLsLs; "%ls\\%ls"
0x1800b8374  mov     [rsp+290h+var_270], rax
0x1800b8379  mov     edx, 104h; unsigned __int64
0x1800b837e  lea     rcx, [rsp+290h+var_240]; unsigned __int16 *
0x1800b8383  mov     r9, [r9+68h]
0x1800b8387  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b838c  test    eax, eax
0x1800b838e  jns     short loc_1800B83C7
0x1800b8390  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b8397  lea     rdx, WPP_GLOBAL_Control
0x1800b839e  cmp     rcx, rdx
0x1800b83a1  jz      loc_1800B8714
0x1800b83a7  test    byte ptr [rcx+1Ch], 1
0x1800b83ab  jz      loc_1800B8714
0x1800b83b1  lea     r8, aFwmoneisinitia_0; "FwMoneisInitialize::StringCchPrintf"
0x1800b83b8  mov     edx, 1Ah
0x1800b83bd  mov     [rsp+290h+var_270], r8
0x1800b83c2  jmp     loc_1800B82F0
0x1800b83c7  lea     rax, [rsp+290h+var_24C]
0x1800b83cc  mov     [rsp+290h+var_250], esi
0x1800b83d0  lea     r9, [rsp+290h+var_250]
0x1800b83d5  mov     [rsp+290h+var_270], rax
0x1800b83da  lea     r8, aTmpedpapphsvir; "TmpEdpAppHsviRefCnt"
0x1800b83e1  mov     rcx, 0FFFFFFFF80000002h
0x1800b83e8  lea     rdx, [rsp+290h+var_240]
0x1800b83ed  call    cs:__imp_FwRegQueryDWord
0x1800b83f3  mov     rcx, cs:?gEnterpriseDomainProtectionManager@@3V?$unique_ptr@VEnterpriseDomainProtection@appIsolation@@U?$default_delete@VEnterpriseDomainProtection@appIsolation@@@wistd@@@wistd@@A; wistd::unique_ptr<appIsolation::EnterpriseDomainProtection,wistd::default_delete<appIsolation::EnterpriseDomainProtection>> gEnterpriseDomainProtectionManager
0x1800b83fa  xor     r9d, r9d; SecurityDescriptorSize
0x1800b83fd  mov     eax, [rsp+290h+var_250]
0x1800b8401  xchg    eax, [rcx+34h]
0x1800b8404  mov     rcx, cs:?gSidManager@@3V?$unique_ptr@VSidManagement@appIsolation@@U?$default_delete@VSidManagement@appIsolation@@@wistd@@@wistd@@A; wistd::unique_ptr<appIsolation::SidManagement,wistd::default_delete<appIsolation::SidManagement>> gSidManager
0x1800b840b  lea     edx, [r9+1]; StringSDRevision
0x1800b840f  lea     r8, [rcx+78h]; SecurityDescriptor
0x1800b8413  mov     rcx, [rcx+70h]; StringSecurityDescriptor
0x1800b8417  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800b841d  mov     [rsp+290h+var_24C], eax
0x1800b8421  test    eax, eax
0x1800b8423  jnz     short loc_1800B845F
0x1800b8425  lea     rdi, aConvertstrings_1; "ConvertStringSecurityDescriptorToSecuri"...
0x1800b842c  call    cs:__imp_GetLastError
0x1800b8432  mov     ebx, eax
0x1800b8434  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b843b  lea     rdx, WPP_GLOBAL_Control
0x1800b8442  cmp     rcx, rdx
0x1800b8445  jz      loc_1800B8714
0x1800b844b  test    byte ptr [rcx+1Ch], 1
0x1800b844f  jz      loc_1800B8714
0x1800b8455  mov     edx, 1Bh
0x1800b845a  jmp     loc_1800B8347
0x1800b845f  mov     rcx, cs:Block; this
0x1800b8466  call    ?FwMoneisRegistrationApiInitialize@IsolationEvents@appIsolation@@QEAAKXZ; appIsolation::IsolationEvents::FwMoneisRegistrationApiInitialize(void)
0x1800b846b  mov     ebx, eax
0x1800b846d  test    eax, eax
0x1800b846f  jz      short loc_1800B84A3
0x1800b8471  lea     rdi, aFwmoneisregist; "FwMoneisRegistrationApiInitialize"
0x1800b8478  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b847f  lea     rdx, WPP_GLOBAL_Control
0x1800b8486  cmp     rcx, rdx
0x1800b8489  jz      loc_1800B8714
0x1800b848f  test    byte ptr [rcx+1Ch], 1
0x1800b8493  jz      loc_1800B8714
0x1800b8499  mov     edx, 1Ch
0x1800b849e  jmp     loc_1800B8347
0x1800b84a3  mov     r8, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800b84aa  mov     edx, 2
0x1800b84af  add     r8, 60h ; '`'
0x1800b84b3  xor     ecx, ecx
0x1800b84b5  call    cs:__imp_FwOpenAppCDbPolicyStore
0x1800b84bb  mov     ecx, eax
0x1800b84bd  call    cs:__imp_FwHResultToWindowsError
0x1800b84c3  mov     ebx, eax
0x1800b84c5  test    eax, eax
0x1800b84c7  jz      short loc_1800B84FB
0x1800b84c9  lea     rdi, aFwopenappcdbpo_0; "FwOpenAppCDbPolicyStore"
0x1800b84d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b84d7  lea     rdx, WPP_GLOBAL_Control
0x1800b84de  cmp     rcx, rdx
0x1800b84e1  jz      loc_1800B8714
0x1800b84e7  test    byte ptr [rcx+1Ch], 1
0x1800b84eb  jz      loc_1800B8714
0x1800b84f1  mov     edx, 1Dh
0x1800b84f6  jmp     loc_1800B8347
0x1800b84fb  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; this
0x1800b8502  lea     rdi, aFwmoneisloadap; "FwMoneisLoadAppCConfig"
0x1800b8509  call    ?LoadAppCConfig@AppContainerDatabase@appIsolation@@QEAAKXZ; appIsolation::AppContainerDatabase::LoadAppCConfig(void)
0x1800b850e  mov     ebx, eax
0x1800b8510  test    eax, eax
0x1800b8512  jz      short loc_1800B853F
0x1800b8514  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b851b  lea     rdx, WPP_GLOBAL_Control
0x1800b8522  cmp     rcx, rdx
0x1800b8525  jz      loc_1800B8714
0x1800b852b  test    byte ptr [rcx+1Ch], 1
0x1800b852f  jz      loc_1800B8714
0x1800b8535  mov     edx, 1Eh
0x1800b853a  jmp     loc_1800B8347
0x1800b853f  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800b8546  call    cs:__imp_FwCriticalSectionCreate
0x1800b854c  mov     ecx, eax
0x1800b854e  call    cs:__imp_FwHResultToWindowsError
0x1800b8554  mov     ebx, eax
0x1800b8556  test    eax, eax
0x1800b8558  jz      short loc_1800B8585
0x1800b855a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b8561  lea     rdx, WPP_GLOBAL_Control
0x1800b8568  cmp     rcx, rdx
0x1800b856b  jz      loc_1800B8714
0x1800b8571  test    byte ptr [rcx+1Ch], 1
0x1800b8575  jz      loc_1800B8714
0x1800b857b  mov     edx, 1Fh
0x1800b8580  jmp     loc_1800B8347
0x1800b8585  mov     rcx, cs:?gEnterpriseDomainProtectionManager@@3V?$unique_ptr@VEnterpriseDomainProtection@appIsolation@@U?$default_delete@VEnterpriseDomainProtection@appIsolation@@@wistd@@@wistd@@A; wistd::unique_ptr<appIsolation::EnterpriseDomainProtection,wistd::default_delete<appIsolation::EnterpriseDomainProtection>> gEnterpriseDomainProtectionManager
0x1800b858c  call    cs:__imp_FwCriticalSectionCreate
0x1800b8592  mov     ecx, eax
0x1800b8594  call    cs:__imp_FwHResultToWindowsError
0x1800b859a  mov     ebx, eax
0x1800b859c  test    eax, eax
0x1800b859e  jz      short loc_1800B85CB
0x1800b85a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b85a7  lea     rdx, WPP_GLOBAL_Control
0x1800b85ae  cmp     rcx, rdx
0x1800b85b1  jz      loc_1800B8714
0x1800b85b7  test    byte ptr [rcx+1Ch], 1
0x1800b85bb  jz      loc_1800B8714
0x1800b85c1  mov     edx, 20h ; ' '
0x1800b85c6  jmp     loc_1800B8347
0x1800b85cb  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800b85d2  add     rcx, 30h ; '0'
0x1800b85d6  call    cs:__imp_FwCriticalSectionCreate
0x1800b85dc  mov     ecx, eax
0x1800b85de  call    cs:__imp_FwHResultToWindowsError
0x1800b85e4  mov     ebx, eax
0x1800b85e6  test    eax, eax
0x1800b85e8  jz      short loc_1800B8615
0x1800b85ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b85f1  lea     rdx, WPP_GLOBAL_Control
0x1800b85f8  cmp     rcx, rdx
0x1800b85fb  jz      loc_1800B8714
0x1800b8601  test    byte ptr [rcx+1Ch], 1
0x1800b8605  jz      loc_1800B8714
0x1800b860b  mov     edx, 21h ; '!'
0x1800b8610  jmp     loc_1800B8347
0x1800b8615  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; this
0x1800b861c  call    ?LoadDaGPConfigHint@AppContainerDatabase@appIsolation@@QEAAKXZ; appIsolation::AppContainerDatabase::LoadDaGPConfigHint(void)
  ... truncated ...
```
