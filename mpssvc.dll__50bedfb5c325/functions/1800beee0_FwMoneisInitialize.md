# FwMoneisInitialize

- ea: `0x1800beee0`
- end: `0x1800bf590`
- name: `FwMoneisInitialize`
- size: `1712`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001784`
- `0x18000a66c`
- `0x18000a710`
- `0x180061c90`
- `0x18006c8ac`
- `0x1800729c0`
- `0x180072ab4`
- `0x180073488`
- `0x180076940`
- `0x1800bb410`
- `0x1800bb5d0`
- `0x1800bb630`
- `0x1800bbbc0`
- `0x1800bc65c`
- `0x1800bc734`
- `0x1800bc8b4`
- `0x1800beee0`
- `0x1800bff64`
- `0x1800c25c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf1d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf1d4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800bf1b9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800bf1b9`
- `fwbase!FwHResultToWindowsError` at `0x1800bf271`
- `fwbase!FwHResultToWindowsError` at `0x1800bf30b`
- `fwbase!FwHResultToWindowsError` at `0x1800bf35d`
- `fwbase!FwHResultToWindowsError` at `0x1800bf3b3`
- `fwbase!FwHResultToWindowsError` at `0x1800bf43b`
- `fwbase!FwHResultToWindowsError` at `0x1800bf4c9`
- `fwbase!FwHResultToWindowsError` at `0x1800bf271`
- `fwbase!FwHResultToWindowsError` at `0x1800bf30b`
- `fwbase!FwHResultToWindowsError` at `0x1800bf35d`
- `fwbase!FwHResultToWindowsError` at `0x1800bf3b3`
- `fwbase!FwHResultToWindowsError` at `0x1800bf43b`
- `fwbase!FwHResultToWindowsError` at `0x1800bf4c9`
- `fwbase!FwRegQueryDWord` at `0x1800bf18a`
- `fwbase!FwRegQueryDWord` at `0x1800bf18a`
- `fwbase!FwCriticalSectionCreate` at `0x1800bf2fd`
- `fwbase!FwCriticalSectionCreate` at `0x1800bf34f`
- `fwbase!FwCriticalSectionCreate` at `0x1800bf3a5`
- `fwbase!FwCriticalSectionCreate` at `0x1800bf4bb`
- `fwbase!FwCriticalSectionCreate` at `0x1800bf2fd`
- `fwbase!FwCriticalSectionCreate` at `0x1800bf34f`
- `fwbase!FwCriticalSectionCreate` at `0x1800bf3a5`
- `fwbase!FwCriticalSectionCreate` at `0x1800bf4bb`
- `FWPolicyIOMgr!FwOpenAppCDbPolicyStore` at `0x1800bf263`
- `FWPolicyIOMgr!FwOpenAppCDbPolicyStore` at `0x1800bf263`

## string_xrefs

- `0x1800bf0a9`: `FwMoneisInitializeSids`
- `0x1800bf100`: `ACService`
- `0x1800bf061`: `FwMoneisIntializeRegPaths`
- `0x1800bf1cd`: `ConvertStringSecurityDescriptorToSecurityDescriptorW`
- `0x1800bf402`: `FwMoneisLoadDaGPConfigHint`
- `0x1800bf283`: `FwOpenAppCDbPolicyStore`
- `0x1800bf2b5`: `FwMoneisLoadAppCConfig`

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
  int v11; // eax
  int v12; // ebx
  const char *v13; // rdi
  DWORD LastError; // eax
  __int64 v15; // rcx
  __int64 v16; // rdx
  int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  void *Block; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+38h] [rbp-C8h] BYREF
  __int32 v27; // [rsp+40h] [rbp-C0h] BYREF
  BOOL v28[3]; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 v29[264]; // [rsp+50h] [rbp-B0h] BYREF

  v28[0] = 0;
  memset_0(v29, 0, 0x208u);
  gFwMoneis = 4;
  off_18012FBB8 = (struct _FW_AC_SID_INFO near *)&pMoneisSidInfoTable;
  v0 = (appIsolation::AppContainerDatabase *)operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
  v1 = v0;
  if ( v0 )
    memset_0(v0, 0, 0x88u);
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
  dword_180132850 = 0;
  v11 = FwMoneisIntializeRegPaths();
  if ( v11 < 0 )
  {
    v12 = 0;
    v13 = "FwMoneisIntializeRegPaths";
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_Ds(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        24,
        (unsigned int)WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids,
        v11,
        (__int64)"FwMoneisIntializeRegPaths");
    goto LABEL_76;
  }
  v13 = "FwMoneisInitializeSids";
  LastError = FwMoneisInitializeSids();
  v12 = LastError;
  if ( LastError )
  {
    v15 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_76;
    v16 = 25;
    goto LABEL_26;
  }
  v17 = StringCchPrintfW(v29, 0x104u, L"%ls\\%ls", *(_QWORD *)gFwIsolationManager, L"ACService");
  if ( v17 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_Ds(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        26,
        (unsigned int)WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids,
        v17,
        (__int64)"FwMoneisInitialize::StringCchPrintf");
    goto LABEL_76;
  }
  v27 = 0;
  FwRegQueryDWord(-2147483646, v29, L"TmpEdpAppHsviRefCnt", &v27, v28);
  _InterlockedExchange((volatile __int32 *)gEnterpriseDomainProtectionManager + 13, v27);
  v28[0] = ConvertStringSecurityDescriptorToSecurityDescriptorW(off_18012FBC0, 1u, &SecurityDescriptor, 0);
  if ( !v28[0] )
  {
    v13 = "ConvertStringSecurityDescriptorToSecurityDescriptorW";
    LastError = GetLastError();
    v12 = LastError;
    v15 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_76;
    v16 = 27;
    goto LABEL_26;
  }
  LastError = appIsolation::IsolationEvents::FwMoneisRegistrationApiInitialize(::Block);
  v12 = LastError;
  if ( LastError )
  {
    v13 = "FwMoneisRegistrationApiInitialize";
    v15 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_76;
    v16 = 28;
    goto LABEL_26;
  }
  v18 = FwOpenAppCDbPolicyStore(0, 2, (char *)gFwIsolationManager + 72);
  LastError = FwHResultToWindowsError(v18);
  v12 = LastError;
  if ( LastError )
  {
    v13 = "FwOpenAppCDbPolicyStore";
    v15 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_76;
    v16 = 29;
    goto LABEL_26;
  }
  v13 = "FwMoneisLoadAppCConfig";
  LastError = FwMoneisLoadAppCConfig();
  v12 = LastError;
  if ( LastError )
  {
    v15 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_76;
    v16 = 30;
    goto LABEL_26;
  }
  v19 = FwCriticalSectionCreate((char *)gFwIsolationManager + 24);
  LastError = FwHResultToWindowsError(v19);
  v12 = LastError;
  if ( LastError )
  {
    v15 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_76;
    v16 = 31;
    goto LABEL_26;
  }
  v20 = FwCriticalSectionCreate(gEnterpriseDomainProtectionManager);
  LastError = FwHResultToWindowsError(v20);
  v12 = LastError;
  if ( LastError )
  {
    v15 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_76;
    v16 = 32;
    goto LABEL_26;
  }
  v21 = FwCriticalSectionCreate((char *)gFwIsolationManager + 88);
  LastError = FwHResultToWindowsError(v21);
  v12 = LastError;
  if ( LastError )
  {
    v15 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_76;
    v16 = 33;
    goto LABEL_26;
  }
  LastError = appIsolation::AppContainerDatabase::LoadDaGPConfigHint(gFwIsolationManager);
  v12 = LastError;
  if ( LastError )
  {
    v13 = "FwMoneisLoadDaGPConfigHint";
    v15 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_76;
    v16 = 34;
    goto LABEL_26;
  }
  v22 = FwMoneisDiagInitialize();
  LastError = FwHResultToWindowsError(v22);
  v12 = LastError;
  if ( LastError )
  {
    v13 = "FwMoneisDiagInitialize";
    v15 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_76;
    v16 = 35;
    goto LABEL_26;
  }
  v13 = "FwMoneisInboxAppCServicingInitialize";
  LastError = FwMoneisInboxAppCServicingInitialize();
  v12 = LastError;
  if ( LastError )
  {
    v15 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_76;
    v16 = 36;
    goto LABEL_26;
  }
  v23 = FwCriticalSectionCreate(&g_fwEventCriticalSection);
  LastError = FwHResultToWindowsError(v23);
  v12 = LastError;
  if ( LastError )
  {
    v15 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_76;
    v16 = 37;
LABEL_26:
    WPP_SF_d(*(_QWORD *)(v15 + 16), v16, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids, LastError);
    goto LABEL_76;
  }
  v13 = 0;
LABEL_76:
  if ( (unsigned int)dword_18012C3B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18012C3B0, 0x4000000000000LL) )
  {
    LODWORD(Block) = v12;
    v26 = (__int64)v13;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (int)&dword_18012C3B0,
      (__int64)&v26,
      (__int64)&Block);
  }
  if ( v12 > 0 )
    return (unsigned __int16)v12 | 0x80070000;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800beee0  mov     [rsp-8+arg_0], rbx
0x1800beee5  mov     [rsp-8+arg_8], rdi
0x1800beeea  push    rbp
0x1800beeeb  lea     rbp, [rsp-170h]
0x1800beef3  sub     rsp, 270h
0x1800beefa  mov     rax, cs:__security_cookie
0x1800bef01  xor     rax, rsp
0x1800bef04  mov     [rbp+170h+var_10], rax
0x1800bef0b  xor     edx, edx; Val
0x1800bef0d  mov     [rsp+270h+var_22C], 0
0x1800bef15  mov     r8d, 208h; Size
0x1800bef1b  lea     rcx, [rsp+270h+var_220]; void *
0x1800bef20  call    memset_0
0x1800bef25  lea     rax, ?pMoneisSidInfoTable@@3PAU_FW_AC_SID_INFO@@A; _FW_AC_SID_INFO near * pMoneisSidInfoTable
0x1800bef2c  mov     cs:?gFwMoneis@@3UFW_MONEIS_COMPONENT_@@A, 4; FW_MONEIS_COMPONENT_ gFwMoneis
0x1800bef36  mov     edi, 88h
0x1800bef3b  mov     cs:off_18012FBB8, rax
0x1800bef42  mov     ecx, edi; unsigned __int64
0x1800bef44  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800bef4b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800bef50  mov     rbx, rax
0x1800bef53  test    rax, rax
0x1800bef56  jz      short loc_1800BEF67
0x1800bef58  mov     r8d, edi; Size
0x1800bef5b  xor     edx, edx; Val
0x1800bef5d  mov     rcx, rax; void *
0x1800bef60  call    memset_0
0x1800bef65  jmp     short loc_1800BEF69
0x1800bef67  xor     ebx, ebx
0x1800bef69  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; Block
0x1800bef70  mov     cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A, rbx; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800bef77  test    rcx, rcx
0x1800bef7a  jz      short loc_1800BEF8B
0x1800bef7c  mov     rdx, rdi
0x1800bef7f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bef84  mov     rbx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800bef8b  test    rbx, rbx
0x1800bef8e  jz      loc_1800BF566
0x1800bef94  lea     rcx, [rsp+270h+Block]
0x1800bef99  call    ??$make_unique_nothrow@VIsolationEvents@appIsolation@@$$V@wil@@YA?AV?$unique_ptr@VIsolationEvents@appIsolation@@U?$default_delete@VIsolationEvents@appIsolation@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<appIsolation::IsolationEvents,>(void)
0x1800bef9e  mov     ebx, 60h ; '`'
0x1800befa3  mov     rdx, [rax]
0x1800befa6  mov     qword ptr [rax], 0
0x1800befad  mov     rcx, cs:Block; Block
0x1800befb4  mov     cs:Block, rdx
0x1800befbb  test    rcx, rcx
0x1800befbe  jz      short loc_1800BEFC7
0x1800befc0  mov     edx, ebx
0x1800befc2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800befc7  mov     rcx, [rsp+270h+Block]; Block
0x1800befcc  mov     [rsp+270h+Block], 0
0x1800befd5  test    rcx, rcx
0x1800befd8  jz      short loc_1800BEFE2
0x1800befda  mov     rdx, rbx
0x1800befdd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800befe2  cmp     cs:Block, 0
0x1800befea  jz      loc_1800BF566
0x1800beff0  lea     rcx, [rsp+270h+Block]
0x1800beff5  call    ??$make_unique_nothrow@VEnterpriseDomainProtection@appIsolation@@$$V@wil@@YA?AV?$unique_ptr@VEnterpriseDomainProtection@appIsolation@@U?$default_delete@VEnterpriseDomainProtection@appIsolation@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<appIsolation::EnterpriseDomainProtection,>(void)
0x1800beffa  mov     ebx, 38h ; '8'
0x1800befff  mov     rdx, [rax]
0x1800bf002  mov     qword ptr [rax], 0
0x1800bf009  mov     rcx, cs:?gEnterpriseDomainProtectionManager@@3V?$unique_ptr@VEnterpriseDomainProtection@appIsolation@@U?$default_delete@VEnterpriseDomainProtection@appIsolation@@@wistd@@@wistd@@A; Block
0x1800bf010  mov     cs:?gEnterpriseDomainProtectionManager@@3V?$unique_ptr@VEnterpriseDomainProtection@appIsolation@@U?$default_delete@VEnterpriseDomainProtection@appIsolation@@@wistd@@@wistd@@A, rdx; wistd::unique_ptr<appIsolation::EnterpriseDomainProtection,wistd::default_delete<appIsolation::EnterpriseDomainProtection>> gEnterpriseDomainProtectionManager
0x1800bf017  test    rcx, rcx
0x1800bf01a  jz      short loc_1800BF023
0x1800bf01c  mov     edx, ebx
0x1800bf01e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bf023  mov     rcx, [rsp+270h+Block]; Block
0x1800bf028  mov     [rsp+270h+Block], 0
0x1800bf031  test    rcx, rcx
0x1800bf034  jz      short loc_1800BF03E
0x1800bf036  mov     rdx, rbx
0x1800bf039  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bf03e  cmp     cs:?gEnterpriseDomainProtectionManager@@3V?$unique_ptr@VEnterpriseDomainProtection@appIsolation@@U?$default_delete@VEnterpriseDomainProtection@appIsolation@@@wistd@@@wistd@@A, 0; wistd::unique_ptr<appIsolation::EnterpriseDomainProtection,wistd::default_delete<appIsolation::EnterpriseDomainProtection>> gEnterpriseDomainProtectionManager
0x1800bf046  jz      loc_1800BF566
0x1800bf04c  mov     cs:dword_180132850, 0
0x1800bf056  call    ?FwMoneisIntializeRegPaths@@YAJXZ; FwMoneisIntializeRegPaths(void)
0x1800bf05b  test    eax, eax
0x1800bf05d  jns     short loc_1800BF0A9
0x1800bf05f  xor     ebx, ebx
0x1800bf061  lea     rdi, aFwmoneisintial; "FwMoneisIntializeRegPaths"
0x1800bf068  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf06f  lea     rdx, WPP_GLOBAL_Control
0x1800bf076  cmp     rcx, rdx
0x1800bf079  jz      loc_1800BF500
0x1800bf07f  test    byte ptr [rcx+1Ch], 1
0x1800bf083  jz      loc_1800BF500
0x1800bf089  lea     edx, [rbx+18h]
0x1800bf08c  mov     [rsp+270h+var_250], rdi
0x1800bf091  mov     rcx, [rcx+10h]
0x1800bf095  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x1800bf09c  mov     r9d, eax
0x1800bf09f  call    WPP_SF_Ds
0x1800bf0a4  jmp     loc_1800BF500
0x1800bf0a9  lea     rdi, aFwmoneisinitia; "FwMoneisInitializeSids"
0x1800bf0b0  call    ?FwMoneisInitializeSids@@YAKXZ; FwMoneisInitializeSids(void)
0x1800bf0b5  mov     ebx, eax
0x1800bf0b7  test    eax, eax
0x1800bf0b9  jz      short loc_1800BF0F9
0x1800bf0bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf0c2  lea     rdx, WPP_GLOBAL_Control
0x1800bf0c9  cmp     rcx, rdx
0x1800bf0cc  jz      loc_1800BF500
0x1800bf0d2  test    byte ptr [rcx+1Ch], 1
0x1800bf0d6  jz      loc_1800BF500
0x1800bf0dc  mov     edx, 19h
0x1800bf0e1  mov     rcx, [rcx+10h]
0x1800bf0e5  lea     r8, WPP_63b07f154e59352ff1fc5e97167f3127_Traceguids
0x1800bf0ec  mov     r9d, eax
0x1800bf0ef  call    WPP_SF_d
0x1800bf0f4  jmp     loc_1800BF500
0x1800bf0f9  mov     r9, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800bf100  lea     rax, aAcservice; "ACService"
0x1800bf107  lea     r8, aLsLs; "%ls\\%ls"
0x1800bf10e  mov     [rsp+270h+var_250], rax
0x1800bf113  mov     edx, 104h; unsigned __int64
0x1800bf118  lea     rcx, [rsp+270h+var_220]; unsigned __int16 *
0x1800bf11d  mov     r9, [r9]
0x1800bf120  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800bf125  test    eax, eax
0x1800bf127  jns     short loc_1800BF160
0x1800bf129  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf130  lea     rdx, WPP_GLOBAL_Control
0x1800bf137  cmp     rcx, rdx
0x1800bf13a  jz      loc_1800BF500
0x1800bf140  test    byte ptr [rcx+1Ch], 1
0x1800bf144  jz      loc_1800BF500
0x1800bf14a  lea     r8, aFwmoneisinitia_0; "FwMoneisInitialize::StringCchPrintf"
0x1800bf151  mov     edx, 1Ah
0x1800bf156  mov     [rsp+270h+var_250], r8
0x1800bf15b  jmp     loc_1800BF091
0x1800bf160  lea     rax, [rsp+270h+var_22C]
0x1800bf165  mov     [rsp+270h+var_230], 0
0x1800bf16d  lea     r9, [rsp+270h+var_230]
0x1800bf172  mov     [rsp+270h+var_250], rax
0x1800bf177  lea     r8, aTmpedpapphsvir; "TmpEdpAppHsviRefCnt"
0x1800bf17e  mov     rcx, 0FFFFFFFF80000002h
0x1800bf185  lea     rdx, [rsp+270h+var_220]
0x1800bf18a  call    cs:__imp_FwRegQueryDWord
0x1800bf191  nop     dword ptr [rax+rax+00h]
0x1800bf196  mov     rcx, cs:?gEnterpriseDomainProtectionManager@@3V?$unique_ptr@VEnterpriseDomainProtection@appIsolation@@U?$default_delete@VEnterpriseDomainProtection@appIsolation@@@wistd@@@wistd@@A; wistd::unique_ptr<appIsolation::EnterpriseDomainProtection,wistd::default_delete<appIsolation::EnterpriseDomainProtection>> gEnterpriseDomainProtectionManager
0x1800bf19d  lea     r8, SecurityDescriptor; SecurityDescriptor
0x1800bf1a4  mov     eax, [rsp+270h+var_230]
0x1800bf1a8  xor     r9d, r9d; SecurityDescriptorSize
0x1800bf1ab  xchg    eax, [rcx+34h]
0x1800bf1ae  mov     rcx, cs:off_18012FBC0; StringSecurityDescriptor
0x1800bf1b5  lea     edx, [r9+1]; StringSDRevision
0x1800bf1b9  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800bf1c0  nop     dword ptr [rax+rax+00h]
0x1800bf1c5  mov     [rsp+270h+var_22C], eax
0x1800bf1c9  test    eax, eax
0x1800bf1cb  jnz     short loc_1800BF20D
0x1800bf1cd  lea     rdi, aConvertstrings_2; "ConvertStringSecurityDescriptorToSecuri"...
0x1800bf1d4  call    cs:__imp_GetLastError
0x1800bf1db  nop     dword ptr [rax+rax+00h]
0x1800bf1e0  mov     ebx, eax
0x1800bf1e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf1e9  lea     rdx, WPP_GLOBAL_Control
0x1800bf1f0  cmp     rcx, rdx
0x1800bf1f3  jz      loc_1800BF500
0x1800bf1f9  test    byte ptr [rcx+1Ch], 1
0x1800bf1fd  jz      loc_1800BF500
0x1800bf203  mov     edx, 1Bh
0x1800bf208  jmp     loc_1800BF0E1
0x1800bf20d  mov     rcx, cs:Block; this
0x1800bf214  call    ?FwMoneisRegistrationApiInitialize@IsolationEvents@appIsolation@@QEAAKXZ; appIsolation::IsolationEvents::FwMoneisRegistrationApiInitialize(void)
0x1800bf219  mov     ebx, eax
0x1800bf21b  test    eax, eax
0x1800bf21d  jz      short loc_1800BF251
0x1800bf21f  lea     rdi, aFwmoneisregist; "FwMoneisRegistrationApiInitialize"
0x1800bf226  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf22d  lea     rdx, WPP_GLOBAL_Control
0x1800bf234  cmp     rcx, rdx
0x1800bf237  jz      loc_1800BF500
0x1800bf23d  test    byte ptr [rcx+1Ch], 1
0x1800bf241  jz      loc_1800BF500
0x1800bf247  mov     edx, 1Ch
0x1800bf24c  jmp     loc_1800BF0E1
0x1800bf251  mov     r8, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800bf258  mov     edx, 2
0x1800bf25d  add     r8, 48h ; 'H'
0x1800bf261  xor     ecx, ecx
0x1800bf263  call    cs:__imp_FwOpenAppCDbPolicyStore
0x1800bf26a  nop     dword ptr [rax+rax+00h]
0x1800bf26f  mov     ecx, eax
0x1800bf271  call    cs:__imp_FwHResultToWindowsError
0x1800bf278  nop     dword ptr [rax+rax+00h]
0x1800bf27d  mov     ebx, eax
0x1800bf27f  test    eax, eax
0x1800bf281  jz      short loc_1800BF2B5
0x1800bf283  lea     rdi, aFwopenappcdbpo_0; "FwOpenAppCDbPolicyStore"
0x1800bf28a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf291  lea     rdx, WPP_GLOBAL_Control
0x1800bf298  cmp     rcx, rdx
0x1800bf29b  jz      loc_1800BF500
0x1800bf2a1  test    byte ptr [rcx+1Ch], 1
0x1800bf2a5  jz      loc_1800BF500
0x1800bf2ab  mov     edx, 1Dh
0x1800bf2b0  jmp     loc_1800BF0E1
0x1800bf2b5  lea     rdi, aFwmoneisloadap; "FwMoneisLoadAppCConfig"
0x1800bf2bc  call    ?FwMoneisLoadAppCConfig@@YAKXZ; FwMoneisLoadAppCConfig(void)
0x1800bf2c1  mov     ebx, eax
0x1800bf2c3  test    eax, eax
0x1800bf2c5  jz      short loc_1800BF2F2
0x1800bf2c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf2ce  lea     rdx, WPP_GLOBAL_Control
0x1800bf2d5  cmp     rcx, rdx
0x1800bf2d8  jz      loc_1800BF500
0x1800bf2de  test    byte ptr [rcx+1Ch], 1
0x1800bf2e2  jz      loc_1800BF500
0x1800bf2e8  mov     edx, 1Eh
0x1800bf2ed  jmp     loc_1800BF0E1
0x1800bf2f2  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800bf2f9  add     rcx, 18h
0x1800bf2fd  call    cs:__imp_FwCriticalSectionCreate
0x1800bf304  nop     dword ptr [rax+rax+00h]
0x1800bf309  mov     ecx, eax
0x1800bf30b  call    cs:__imp_FwHResultToWindowsError
0x1800bf312  nop     dword ptr [rax+rax+00h]
0x1800bf317  mov     ebx, eax
0x1800bf319  test    eax, eax
0x1800bf31b  jz      short loc_1800BF348
0x1800bf31d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf324  lea     rdx, WPP_GLOBAL_Control
0x1800bf32b  cmp     rcx, rdx
0x1800bf32e  jz      loc_1800BF500
0x1800bf334  test    byte ptr [rcx+1Ch], 1
0x1800bf338  jz      loc_1800BF500
0x1800bf33e  mov     edx, 1Fh
0x1800bf343  jmp     loc_1800BF0E1
0x1800bf348  mov     rcx, cs:?gEnterpriseDomainProtectionManager@@3V?$unique_ptr@VEnterpriseDomainProtection@appIsolation@@U?$default_delete@VEnterpriseDomainProtection@appIsolation@@@wistd@@@wistd@@A; wistd::unique_ptr<appIsolation::EnterpriseDomainProtection,wistd::default_delete<appIsolation::EnterpriseDomainProtection>> gEnterpriseDomainProtectionManager
0x1800bf34f  call    cs:__imp_FwCriticalSectionCreate
0x1800bf356  nop     dword ptr [rax+rax+00h]
0x1800bf35b  mov     ecx, eax
0x1800bf35d  call    cs:__imp_FwHResultToWindowsError
0x1800bf364  nop     dword ptr [rax+rax+00h]
0x1800bf369  mov     ebx, eax
0x1800bf36b  test    eax, eax
0x1800bf36d  jz      short loc_1800BF39A
0x1800bf36f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf376  lea     rdx, WPP_GLOBAL_Control
0x1800bf37d  cmp     rcx, rdx
0x1800bf380  jz      loc_1800BF500
0x1800bf386  test    byte ptr [rcx+1Ch], 1
0x1800bf38a  jz      loc_1800BF500
0x1800bf390  mov     edx, 20h ; ' '
0x1800bf395  jmp     loc_1800BF0E1
0x1800bf39a  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; _tag_FW_NETWORK_ISOLATION_COMPONENT gFwIsolationManager
0x1800bf3a1  add     rcx, 58h ; 'X'
0x1800bf3a5  call    cs:__imp_FwCriticalSectionCreate
0x1800bf3ac  nop     dword ptr [rax+rax+00h]
0x1800bf3b1  mov     ecx, eax
0x1800bf3b3  call    cs:__imp_FwHResultToWindowsError
0x1800bf3ba  nop     dword ptr [rax+rax+00h]
0x1800bf3bf  mov     ebx, eax
0x1800bf3c1  test    eax, eax
0x1800bf3c3  jz      short loc_1800BF3F0
0x1800bf3c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf3cc  lea     rdx, WPP_GLOBAL_Control
0x1800bf3d3  cmp     rcx, rdx
0x1800bf3d6  jz      loc_1800BF500
0x1800bf3dc  test    byte ptr [rcx+1Ch], 1
0x1800bf3e0  jz      loc_1800BF500
0x1800bf3e6  mov     edx, 21h ; '!'
0x1800bf3eb  jmp     loc_1800BF0E1
0x1800bf3f0  mov     rcx, cs:?gFwIsolationManager@@3U_tag_FW_NETWORK_ISOLATION_COMPONENT@@A; this
0x1800bf3f7  call    ?LoadDaGPConfigHint@AppContainerDatabase@appIsolation@@QEAAKXZ; appIsolation::AppContainerDatabase::LoadDaGPConfigHint(void)
0x1800bf3fc  mov     ebx, eax
0x1800bf3fe  test    eax, eax
0x1800bf400  jz      short loc_1800BF434
0x1800bf402  lea     rdi, aFwmoneisloadda; "FwMoneisLoadDaGPConfigHint"
0x1800bf409  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf410  lea     rdx, WPP_GLOBAL_Control
0x1800bf417  cmp     rcx, rdx
0x1800bf41a  jz      loc_1800BF500
0x1800bf420  test    byte ptr [rcx+1Ch], 1
0x1800bf424  jz      loc_1800BF500
0x1800bf42a  mov     edx, 22h ; '"'
0x1800bf42f  jmp     loc_1800BF0E1
0x1800bf434  call    FwMoneisDiagInitialize
0x1800bf439  mov     ecx, eax
0x1800bf43b  call    cs:__imp_FwHResultToWindowsError
0x1800bf442  nop     dword ptr [rax+rax+00h]
0x1800bf447  mov     ebx, eax
0x1800bf449  test    eax, eax
0x1800bf44b  jz      short loc_1800BF47F
0x1800bf44d  lea     rdi, aFwmoneisdiagin; "FwMoneisDiagInitialize"
0x1800bf454  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf45b  lea     rdx, WPP_GLOBAL_Control
0x1800bf462  cmp     rcx, rdx
0x1800bf465  jz      loc_1800BF500
0x1800bf46b  test    byte ptr [rcx+1Ch], 1
0x1800bf46f  jz      loc_1800BF500
0x1800bf475  mov     edx, 23h ; '#'
0x1800bf47a  jmp     loc_1800BF0E1
0x1800bf47f  lea     rdi, aFwmoneisinboxa; "FwMoneisInboxAppCServicingInitialize"
0x1800bf486  call    ?FwMoneisInboxAppCServicingInitialize@@YAKXZ; FwMoneisInboxAppCServicingInitialize(void)
0x1800bf48b  mov     ebx, eax
0x1800bf48d  test    eax, eax
  ... truncated ...
```
