# CComRegCatalog::GetProcessInfoInternal(ulong,IUserToken *,_GUID const &,_GUID const &,void * *)

- ea: `0x18010f600`
- end: `0x18010fde1`
- name: `?GetProcessInfoInternal@CComRegCatalog@@UEAAJKPEAUIUserToken@@AEBU_GUID@@1PEAPEAX@Z`
- size: `2017`
- prototype: `HRESULT __fastcall(CComRegCatalog *this, unsigned int flags, IUserToken *pUserToken, const _GUID *guidProcess, const _GUID *riid, void **ppv)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801e0440`

## callees

- `0x180020140`
- `0x18003a8bc`
- `0x18004768c`
- `0x1800865b8`
- `0x180087660`
- `0x18008db2c`
- `0x1800bac6c`
- `0x18010f600`
- `0x18014b304`
- `0x18015ddc0`
- `0x1801999b0`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18010fb4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18010fb4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010fadf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010fd4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010fadf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010fd4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010fa09`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010fa09`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18010f9e2`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18010fa1e`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18010f9e2`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x18010fa1e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18010f87c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18010f87c`

## string_xrefs

- `0x18010f6ad`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18010f7e1`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18010fb22`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18010fdbb`: `onecore\com\combase\catalog\regcat.cxx`
- `0x18010f691`: `CComRegCatalog::GetProcessInfoInternal`
- `0x18010f7da`: `CComRegCatalog::GetProcessInfoInternal`
- `0x18010fdaf`: `CComRegCatalog::GetProcessInfoInternal`

## pseudocode

```c
__int64 __fastcall CComRegCatalog::GetProcessInfoInternal(
        CComRegCatalog *this,
        unsigned int flags,
        IUserToken *pUserToken,
        _GUID *guidProcess,
        const _GUID *riid,
        void **ppv)
{
  void *v7; // rdx
  _GUID *v8; // r13
  IUserToken *v9; // rsi
  const _GUID *v11; // r9
  wchar_t *v12; // rax
  TraceLevel v13; // r10d
  unsigned int v14; // ecx
  char v15; // al
  HKEY__ **p_m_source; // rdi
  int v18; // r12d
  int v19; // eax
  HRESULT v20; // ebx
  TraceLevel v21; // r9d
  IUserToken_vtbl *v22; // rax
  __int64 v23; // rcx
  const wchar_t *v24; // r8
  __int64 v25; // rdx
  wchar_t *v26; // rax
  wchar_t *v27; // rcx
  const int *v28; // r9
  _GUID *v29; // r10
  unsigned int v30; // eax
  unsigned __int8 Data1; // dl
  __int64 v32; // r8
  wchar_t v33; // ax
  wchar_t v34; // ax
  int v35; // r15d
  unsigned __int16 v36; // r13
  HKEY__ *v37; // rbx
  int v38; // eax
  HKEY__ *v39; // rax
  HRESULT v40; // eax
  CComProcessInfo *v41; // rax
  unsigned __int8 *v42; // rax
  char v43; // al
  HKEY__ *v44; // rcx
  char v45; // al
  HKEY__ *v46; // rcx
  char v47; // al
  HKEY__ *v48; // rcx
  char v49; // al
  HKEY__ *v50; // rcx
  char v51; // al
  HKEY__ *v52; // rcx
  char v53; // al
  HKEY__ *v54; // rcx
  char supportsProcessMitigationPolicy; // r12
  bool v56; // r13
  char supportsAppIDFlags; // r15
  char supportsActivateAtStorage; // r14
  char v59; // si
  char ignoreRunAsInteractiveUser; // bl
  int v61; // edi
  HKEY v62; // rax
  unsigned __int8 *v63; // rdi
  unsigned int v64; // edx
  wchar_t *v65; // rax
  int fMachineHive; // [rsp+30h] [rbp-F0h]
  bool supportsApplicationId; // [rsp+40h] [rbp-E0h]
  bool supportsROTAndMGOTFlags[4]; // [rsp+A0h] [rbp-80h] BYREF
  int fForceToHKLM; // [rsp+A4h] [rbp-7Ch] BYREF
  bool isPackaged; // [rsp+A8h] [rbp-78h]
  bool supportsProtectionLevel; // [rsp+A9h] [rbp-77h]
  bool supportsLoadUserSettings; // [rsp+AAh] [rbp-76h]
  bool supportsPreferredServerBitness; // [rsp+ABh] [rbp-75h]
  bool supportsSRPTrustLevel; // [rsp+ACh] [rbp-74h]
  unsigned __int16 cbSid; // [rsp+B0h] [rbp-70h] BYREF
  HKEY__ *hKeyRoot; // [rsp+B8h] [rbp-68h] BYREF
  int v77; // [rsp+C0h] [rbp-60h]
  HKEY__ *hKey; // [rsp+C8h] [rbp-58h] BYREF
  IUserTokenInternal *userTokenInternal; // [rsp+D0h] [rbp-50h] BYREF
  int fImpersonating; // [rsp+D8h] [rbp-48h] BYREF
  unsigned __int8 *pSid; // [rsp+E0h] [rbp-40h] BYREF
  HKEY__ **v82; // [rsp+E8h] [rbp-38h]
  _GUID *rclsid; // [rsp+F0h] [rbp-30h]
  IUserToken *v84; // [rsp+F8h] [rbp-28h]
  void **v85; // [rsp+100h] [rbp-20h]
  const _GUID *v86; // [rsp+108h] [rbp-18h]
  CGuidStr v87; // [rsp+110h] [rbp-10h] BYREF
  wchar_t wszAppidString[48]; // [rsp+160h] [rbp+40h] BYREF
  void *retaddr; // [rsp+218h] [rbp+F8h]

  v7 = 0;
  v8 = guidProcess;
  rclsid = guidProcess;
  v9 = pUserToken;
  v84 = pUserToken;
  v86 = riid;
  v85 = ppv;
  hKey = 0;
  hKeyRoot = 0;
  userTokenInternal = 0;
  fImpersonating = 0;
  if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
  {
    CGuidStr::CGuidStr(&v87, v11);
    ComTraceMessageT<void *>(
      "onecore\\com\\combase\\catalog\\regcat.cxx",
      "CComRegCatalog::GetProcessInfoInternal",
      552,
      v13,
      L"AppID %ws",
      v12);
    v7 = 0;
  }
  *ppv = v7;
  v14 = flags & 0x10000;
  fForceToHKLM = flags & 0x10000;
  if ( (flags & 0x10000) != 0 )
  {
    v15 = (*(__int64 (__fastcall **)(const RegistrationSource *))(*(_QWORD *)&this[-1].m_source + 168LL))(&this[-1].m_source);
    LODWORD(v7) = 0;
    if ( !v15 )
      return 2147746132LL;
    v14 = fForceToHKLM;
  }
  v77 = (int)v7;
  p_m_source = (HKEY__ **)&this[-1].m_source;
  v82 = (HKEY__ **)&this[-1].m_source;
  v18 = (int)v7;
  if ( !v9 )
  {
    hKeyRoot = p_m_source[3];
    goto LABEL_33;
  }
  if ( v14 )
  {
    hKeyRoot = p_m_source[3];
  }
  else
  {
    v19 = (*((__int64 (__fastcall **)(const RegistrationSource *, IUserToken *, HKEY__ **))*p_m_source + 15))(
            &this[-1].m_source,
            v9,
            &hKeyRoot);
    v20 = v19;
    if ( v19 == -2147024894 )
    {
      if ( !(*((unsigned __int8 (__fastcall **)(const RegistrationSource *))*p_m_source + 21))(&this[-1].m_source) )
      {
        v20 = -2147221164;
        goto $Cleanup_5;
      }
      hKeyRoot = *(HKEY__ **)&this->m_regView;
      fForceToHKLM = 1;
      goto LABEL_28;
    }
    if ( v19 < 0 )
      goto $Cleanup_5;
    if ( !hKeyRoot )
    {
      v20 = -2147418113;
      goto $Cleanup_5;
    }
    v14 = fForceToHKLM;
    v18 = 1;
    v77 = 1;
  }
  if ( !v14 )
    goto LABEL_30;
LABEL_28:
  if ( (flags & 0x20000) != 0
    || (v22 = v9->__vftable, pSid = 0, cbSid = 0, v22->GetUserSid(v9, &pSid, &cbSid), !EqualSid(pSid, gSidAnonymous)) )
  {
LABEL_30:
    v20 = v9->QueryInterface(v9, &GUID_000001fc_0000_0000_cfff_123045660046, (void **)&userTokenInternal);
    if ( v20 < 0 )
      goto $Cleanup_5;
  }
LABEL_33:
  if ( userTokenInternal )
  {
    v20 = userTokenInternal->Impersonate(userTokenInternal, 0, &fImpersonating);
    if ( v20 < 0 )
    {
      userTokenInternal->Release(userTokenInternal);
      userTokenInternal = 0;
      goto LABEL_16;
    }
  }
  while ( 1 )
  {
    v23 = 2147483646;
    v24 = g_wszAppidTemplate;
    v25 = 45;
    v26 = wszAppidString;
    do
    {
      if ( !v23 )
        break;
      if ( !*v24 )
        break;
      *v26++ = *v24++;
      --v23;
      --v25;
    }
    while ( v25 );
    v27 = v26 - 1;
    if ( v25 )
      v27 = v26;
    *v27 = 0;
    v20 = v25 == 0 ? 0x8007007A : 0;
    if ( !v25 )
      goto $Cleanup_5;
    v28 = guidByteToStringPosition;
    v29 = v8;
    v30 = 6;
    do
    {
      Data1 = v29->Data1;
      ++v28;
      v32 = v30;
      v29 = (_GUID *)((char *)v29 + 1);
      v33 = (Data1 >> 4) + 55;
      if ( (unsigned __int16)((Data1 >> 4) + 48) <= 0x39u )
        v33 = (Data1 >> 4) + 48;
      wszAppidString[v32 + 7] = v33;
      v34 = (Data1 & 0xF) + 55;
      if ( (unsigned __int16)((Data1 & 0xF) + 48) <= 0x39u )
        v34 = (Data1 & 0xF) + 48;
      wszAppidString[v32 + 8] = v34;
      v30 = *v28;
    }
    while ( *v28 >= 0 );
    v35 = (int)this->IGetProcessInfoInternal::IUnknown::__vftable;
    v36 = 0;
    v37 = hKeyRoot;
    wszAppidString[15] = 45;
    wszAppidString[20] = 45;
    wszAppidString[25] = 45;
    wszAppidString[30] = 45;
    if ( v35 == 512 )
      v36 = Wow64SetThreadDefaultGuestMachine(WORD2(this->IGetProcessInfoInternal::IUnknown::__vftable));
    v20 = RegOpenKeyExW(v37, wszAppidString, 0, v35 | 0x20019, &hKey);
    if ( v35 == 512 )
      Wow64SetThreadDefaultGuestMachine(v36);
    if ( v20 )
      break;
    v38 = fForceToHKLM;
    if ( !fForceToHKLM )
    {
      v20 = (*((__int64 (__fastcall **)(const RegistrationSource *, HKEY__ *, int *))*p_m_source + 20))(
              &this[-1].m_source,
              hKey,
              &fForceToHKLM);
      if ( v20 < 0 )
        goto LABEL_75;
      v38 = fForceToHKLM;
    }
    if ( !g_bInSCM || v38 )
      goto LABEL_66;
    v20 = (*((__int64 (__fastcall **)(const RegistrationSource *, HKEY__ *, int *))*p_m_source + 46))(
            &this[-1].m_source,
            hKey,
            &fForceToHKLM);
    if ( v20 < 0 )
      goto LABEL_75;
    if ( !fForceToHKLM )
    {
LABEL_66:
      v39 = *p_m_source;
      supportsROTAndMGOTFlags[0] = 0;
      v40 = (*((__int64 (__fastcall **)(const RegistrationSource *, IUserToken *, bool *))v39 + 29))(
              &this[-1].m_source,
              v9,
              supportsROTAndMGOTFlags);
      v20 = v40;
      if ( v40 < 0 )
      {
        wil::details::in1diag3::Return_Hr(retaddr, 0x2ACu, "onecore\\com\\combase\\catalog\\regcat.cxx", v40);
        return (unsigned int)v20;
      }
      v41 = (CComProcessInfo *)HeapAlloc(g_hHeap, 0, 0x118u);
      if ( v41
        && (CComProcessInfo::CComProcessInfo(v41, (RegistrationSource)this->m_hkeyClassesRoot), (pSid = v42) != 0) )
      {
        v43 = (*((__int64 (__fastcall **)(const RegistrationSource *))*p_m_source + 39))(&this[-1].m_source);
        v44 = *p_m_source;
        isPackaged = v43;
        v45 = (*((__int64 (__fastcall **)(const RegistrationSource *))v44 + 37))(&this[-1].m_source);
        v46 = *p_m_source;
        supportsProtectionLevel = v45;
        v47 = (*((__int64 (__fastcall **)(const RegistrationSource *))v46 + 35))(&this[-1].m_source);
        v48 = *p_m_source;
        supportsLoadUserSettings = v47;
        v49 = (*((__int64 (__fastcall **)(const RegistrationSource *))v48 + 34))(&this[-1].m_source);
        v50 = *p_m_source;
        supportsPreferredServerBitness = v49;
        v51 = (*((__int64 (__fastcall **)(const RegistrationSource *))v50 + 33))(&this[-1].m_source);
        v52 = *p_m_source;
        supportsSRPTrustLevel = v51;
        v53 = (*((__int64 (__fastcall **)(const RegistrationSource *))v52 + 32))(&this[-1].m_source);
        v54 = *p_m_source;
        LOBYTE(cbSid) = v53;
        supportsProcessMitigationPolicy = (*((__int64 (__fastcall **)(const RegistrationSource *))v54 + 31))(&this[-1].m_source);
        v56 = supportsROTAndMGOTFlags[0];
        supportsAppIDFlags = (*((__int64 (__fastcall **)(const RegistrationSource *))*p_m_source + 28))(&this[-1].m_source);
        supportsActivateAtStorage = (*((__int64 (__fastcall **)(const RegistrationSource *))*p_m_source + 27))(&this[-1].m_source);
        v59 = (*((__int64 (__fastcall **)(HKEY__ **))*p_m_source + 26))(p_m_source);
        ignoreRunAsInteractiveUser = (*((__int64 (__fastcall **)(HKEY__ **))*p_m_source + 25))(p_m_source);
        v61 = fForceToHKLM;
        v62 = (HKEY)(*((__int64 (__fastcall **)(HKEY__ **, HKEY__ *))*v82 + 30))(v82, hKeyRoot);
        supportsApplicationId = v59;
        v9 = v84;
        fMachineHive = v61;
        v63 = pSid;
        v20 = CComProcessInfo::FinalConstruct(
                (CComProcessInfo *)pSid,
                v84,
                rclsid,
                wszAppidString,
                hKey,
                v62,
                fMachineHive,
                ignoreRunAsInteractiveUser,
                supportsApplicationId,
                supportsActivateAtStorage,
                supportsAppIDFlags,
                v56,
                supportsProcessMitigationPolicy,
                cbSid,
                supportsSRPTrustLevel,
                supportsPreferredServerBitness,
                supportsLoadUserSettings,
                supportsProtectionLevel,
                isPackaged);
        if ( v20 < 0 )
        {
          CComProcessInfo::`scalar deleting destructor'((CComProcessInfo *)v63, v64);
        }
        else
        {
          (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v63 + 8LL))(v63);
          v20 = (**(__int64 (__fastcall ***)(unsigned __int8 *, const _GUID *, void **))v63)(v63, v86, v85);
          (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v63 + 16LL))(v63);
        }
        p_m_source = v82;
      }
      else
      {
        v20 = -2147024882;
      }
      goto LABEL_75;
    }
    if ( !(*((unsigned __int8 (__fastcall **)(const RegistrationSource *))*p_m_source + 21))(&this[-1].m_source) )
    {
      v20 = -2147221161;
LABEL_75:
      RegCloseKey(hKey);
      goto $Cleanup_5;
    }
    if ( v18 )
    {
      (*((void (__fastcall **)(const RegistrationSource *, IUserToken *))*p_m_source + 16))(&this[-1].m_source, v9);
      v18 = 0;
      v77 = 0;
    }
    hKeyRoot = *(HKEY__ **)&this->m_regView;
    RegCloseKey(hKey);
    v8 = rclsid;
  }
  if ( v20 == 2 )
  {
    v20 = -2147221164;
  }
  else if ( v20 > 0 )
  {
    v20 = (unsigned __int16)v20 | 0x80070000;
  }
  if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 || gfEnableTracing && IsWppLevelEnabled(ERRORS) )
  {
    CGuidStr::CGuidStr(&v87, rclsid);
    ComTraceMessageT<unsigned short *,unsigned short *,long>(
      "onecore\\com\\combase\\catalog\\regcat.cxx",
      "CComRegCatalog::GetProcessInfoInternal",
      738,
      ERRORS,
      L"APPID:%wsValue:%ws %!HRESULT!",
      v65,
      wszAppidString,
      v20);
  }
$Cleanup_5:
  if ( userTokenInternal )
  {
    userTokenInternal->Revert(userTokenInternal, fImpersonating);
    userTokenInternal->Release(userTokenInternal);
  }
LABEL_16:
  if ( v77 )
    (*((void (__fastcall **)(HKEY__ **, IUserToken *))*p_m_source + 16))(p_m_source, v9);
  if ( gfEnableTracing )
  {
    if ( IsWppLevelEnabled(VERBOSE) )
      ComTraceMessageT<long>(
        "onecore\\com\\combase\\catalog\\regcat.cxx",
        "CComRegCatalog::GetProcessInfoInternal",
        750,
        v21,
        L"Returning %!HRESULT!",
        v20);
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x18010f600  push    rbp
0x18010f602  push    rbx
0x18010f603  push    rsi
0x18010f604  push    rdi
0x18010f605  push    r12
0x18010f607  push    r13
0x18010f609  push    r14
0x18010f60b  push    r15
0x18010f60d  lea     rbp, [rsp-0B8h]
0x18010f615  sub     rsp, 1D8h
0x18010f61c  mov     rax, cs:__security_cookie
0x18010f623  xor     rax, rsp
0x18010f626  mov     [rbp+0F0h+var_50], rax
0x18010f62d  mov     rax, [rbp+0F0h+arg_20]
0x18010f634  mov     r15d, flags
0x18010f637  mov     rbx, [rbp+0F0h+arg_28]
0x18010f63e  xor     flags, flags
0x18010f640  cmp     cs:?gfEnableTracing@@3HA, flags; int gfEnableTracing
0x18010f646  mov     r13, guidProcess
0x18010f649  mov     [rbp+0F0h+rclsid], guidProcess
0x18010f64d  mov     rsi, pUserToken
0x18010f650  mov     [rbp+0F0h+var_118], pUserToken
0x18010f654  mov     r14, this
0x18010f657  lea     r10d, [rdx+3]
0x18010f65b  mov     [rbp+0F0h+var_108], rax
0x18010f65f  mov     [rbp+0F0h+var_110], rbx
0x18010f663  mov     [rbp+0F0h+hKey], rdx
0x18010f667  mov     [rbp+0F0h+hKeyRoot], rdx
0x18010f66b  mov     [rbp+0F0h+userTokenInternal], rdx
0x18010f66f  mov     [rbp+0F0h+fImpersonating], flags
0x18010f672  jz      short loc_18010F6BB
0x18010f674  mov     ecx, r10d; level
0x18010f677  call    IsWppLevelEnabled
0x18010f67c  test    al, al
0x18010f67e  jz      short loc_18010F6BB
0x18010f680  mov     rdx, guidProcess; rguid
0x18010f683  lea     this, [rbp+0F0h+var_100]; this
0x18010f687  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x18010f68c  mov     qword ptr [rsp+210h+var_1E8], rax; <args_0>
0x18010f691  lea     rdx, aCcomregcatalog; "CComRegCatalog::GetProcessInfoInternal"
0x18010f698  lea     rax, aAppidWs; "AppID %ws"
0x18010f69f  mov     r9d, r10d; level
0x18010f6a2  mov     r8d, 228h; line
0x18010f6a8  mov     [rsp+210h+format], rax; format
0x18010f6ad  lea     this, aOnecoreComComb_68; "onecore\\com\\combase\\catalog\\regcat."...
0x18010f6b4  call    ??$ComTraceMessageT@PEAX@@YAXPEBD0HW4TraceLevel@@PEBGPEAX@Z; ComTraceMessageT<void *>(char const *,char const *,int,TraceLevel,ushort const *,void *)
0x18010f6b9  xor     flags, flags
0x18010f6bb  mov     ecx, r15d
0x18010f6be  mov     [rbx], rdx
0x18010f6c1  and     ecx, 10000h
0x18010f6c7  mov     [rbp+0F0h+fForceToHKLM], ecx
0x18010f6ca  jz      short loc_18010F6F2
0x18010f6cc  lea     this, [r14-8]
0x18010f6d0  mov     rax, [this]
0x18010f6d3  mov     rax, [rax+0A8h]
0x18010f6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f6df  xor     flags, flags
0x18010f6e1  test    al, al
0x18010f6e3  jnz     short loc_18010F6EF
0x18010f6e5  mov     eax, 80040154h
0x18010f6ea  jmp     loc_18010F7EF
0x18010f6ef  mov     ecx, [rbp+0F0h+fForceToHKLM]
0x18010f6f2  mov     [rbp+0F0h+var_150], flags
0x18010f6f5  lea     rdi, [r14-8]
0x18010f6f9  mov     [rbp+0F0h+var_128], rdi
0x18010f6fd  mov     r12d, flags
0x18010f700  test    rsi, rsi
0x18010f703  jz      loc_18010F8B0
0x18010f709  test    ecx, ecx
0x18010f70b  jnz     loc_18010F83B
0x18010f711  mov     rax, [rdi]
0x18010f714  lea     pUserToken, [rbp+0F0h+hKeyRoot]
0x18010f718  mov     rdx, rsi
0x18010f71b  mov     this, rdi
0x18010f71e  mov     rax, [rax+78h]
0x18010f722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f727  mov     ebx, eax
0x18010f729  cmp     eax, 80070002h
0x18010f72e  jnz     loc_18010F812
0x18010f734  mov     rax, [rdi]
0x18010f737  mov     this, rdi
0x18010f73a  mov     rax, [rax+0A8h]
0x18010f741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f746  test    al, al
0x18010f748  jz      short loc_18010F75E
0x18010f74a  mov     rax, [r14+10h]
0x18010f74e  mov     [rbp+0F0h+hKeyRoot], rax
0x18010f752  mov     [rbp+0F0h+fForceToHKLM], 1
0x18010f759  jmp     loc_18010F847
0x18010f75e  mov     ebx, 80040154h
0x18010f763  xor     r15d, r15d
0x18010f766  mov     this, [rbp+0F0h+userTokenInternal]
0x18010f76a  test    this, this
0x18010f76d  jz      short loc_18010F78E
0x18010f76f  mov     rax, [this]
0x18010f772  mov     flags, [rbp+0F0h+fImpersonating]
0x18010f775  mov     rax, [rax+68h]
0x18010f779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f77e  mov     this, [rbp+0F0h+userTokenInternal]
0x18010f782  mov     rax, [this]
0x18010f785  mov     rax, [rax+10h]
0x18010f789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f78e  cmp     [rbp+0F0h+var_150], r15d
0x18010f792  jz      short loc_18010F7A9
0x18010f794  mov     rax, [rdi]
0x18010f797  mov     rdx, rsi
0x18010f79a  mov     this, rdi
0x18010f79d  mov     rax, [rax+80h]
0x18010f7a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f7a9  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18010f7b0  jz      short loc_18010F7ED
0x18010f7b2  mov     r9d, 3
0x18010f7b8  mov     ecx, r9d; level
0x18010f7bb  call    IsWppLevelEnabled
0x18010f7c0  test    al, al
0x18010f7c2  jz      short loc_18010F7ED
0x18010f7c4  lea     rax, aReturningHresu_0; "Returning %!HRESULT!"
0x18010f7cb  mov     [rsp+210h+var_1E8], ebx; <args_0>
0x18010f7cf  mov     r8d, 2EEh; line
0x18010f7d5  mov     [rsp+210h+format], rax; format
0x18010f7da  lea     rdx, aCcomregcatalog; "CComRegCatalog::GetProcessInfoInternal"
0x18010f7e1  lea     this, aOnecoreComComb_68; "onecore\\com\\combase\\catalog\\regcat."...
0x18010f7e8  call    ??$ComTraceMessageT@J@@YAXPEBD0HW4TraceLevel@@PEBGJ@Z; ComTraceMessageT<long>(char const *,char const *,int,TraceLevel,ushort const *,long)
0x18010f7ed  mov     eax, ebx
0x18010f7ef  mov     this, [rbp+0F0h+var_50]
0x18010f7f6  xor     this, rsp; StackCookie
0x18010f7f9  call    __security_check_cookie
0x18010f7fe  add     rsp, 1D8h
0x18010f805  pop     r15
0x18010f807  pop     r14
0x18010f809  pop     r13
0x18010f80b  pop     r12
0x18010f80d  pop     rdi
0x18010f80e  pop     rsi
0x18010f80f  pop     rbx
0x18010f810  pop     rbp
0x18010f811  retn
0x18010f812  xor     flags, flags
0x18010f814  test    eax, eax
0x18010f816  js      loc_18010F763
0x18010f81c  cmp     [rbp+0F0h+hKeyRoot], rdx
0x18010f820  jnz     short loc_18010F82C
0x18010f822  mov     ebx, 8000FFFFh
0x18010f827  jmp     loc_18010F763
0x18010f82c  mov     ecx, [rbp+0F0h+fForceToHKLM]
0x18010f82f  mov     r12d, 1
0x18010f835  mov     [rbp+0F0h+var_150], r12d
0x18010f839  jmp     short loc_18010F843
0x18010f83b  mov     rax, [rdi+18h]
0x18010f83f  mov     [rbp+0F0h+hKeyRoot], rax
0x18010f843  test    ecx, ecx
0x18010f845  jz      short loc_18010F888
0x18010f847  bt      r15d, 11h
0x18010f84c  jb      short loc_18010F888
0x18010f84e  mov     rax, [rsi]
0x18010f851  lea     pUserToken, [rbp+0F0h+cbSid]
0x18010f855  xor     r15d, r15d
0x18010f858  lea     rdx, [rbp+0F0h+pSid]
0x18010f85c  mov     this, rsi
0x18010f85f  mov     [rbp+0F0h+pSid], r15
0x18010f863  mov     [rbp+0F0h+cbSid], r15w
0x18010f868  mov     rax, [rax+28h]
0x18010f86c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f871  mov     rdx, cs:?gSidAnonymous@@3PEAXEA; pSid2
0x18010f878  mov     this, [rbp+0F0h+pSid]; pSid1
0x18010f87c  call    cs:__imp_EqualSid
0x18010f882  test    eax, eax
0x18010f884  jnz     short loc_18010F8BB
0x18010f886  jmp     short loc_18010F88B
0x18010f888  xor     r15d, r15d
0x18010f88b  mov     rax, [rsi]
0x18010f88e  lea     pUserToken, [rbp+0F0h+userTokenInternal]
0x18010f892  lea     rdx, _GUID_000001fc_0000_0000_cfff_123045660046
0x18010f899  mov     this, rsi
0x18010f89c  mov     rax, [rax]
0x18010f89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f8a4  mov     ebx, eax
0x18010f8a6  test    eax, eax
0x18010f8a8  js      $Cleanup_5
0x18010f8ae  jmp     short loc_18010F8BB
0x18010f8b0  mov     rax, [rdi+18h]
0x18010f8b4  xor     r15d, r15d
0x18010f8b7  mov     [rbp+0F0h+hKeyRoot], rax
0x18010f8bb  mov     this, [rbp+0F0h+userTokenInternal]
0x18010f8bf  test    this, this
0x18010f8c2  jz      short loc_18010F8F5
0x18010f8c4  mov     rax, [this]
0x18010f8c7  lea     pUserToken, [rbp+0F0h+fImpersonating]
0x18010f8cb  xor     flags, flags
0x18010f8cd  mov     rax, [rax+60h]
0x18010f8d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f8d6  mov     ebx, eax
0x18010f8d8  test    eax, eax
0x18010f8da  jns     short loc_18010F8F5
0x18010f8dc  mov     this, [rbp+0F0h+userTokenInternal]
0x18010f8e0  mov     rax, [this]
0x18010f8e3  mov     rax, [rax+10h]
0x18010f8e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f8ec  mov     [rbp+0F0h+userTokenInternal], r15
0x18010f8f0  jmp     loc_18010F78E
0x18010f8f5  mov     r11d, 2Dh ; '-'
0x18010f8fb  mov     ecx, 7FFFFFFEh
0x18010f900  lea     pUserToken, g_wszAppidTemplate
0x18010f907  mov     flags, r11d
0x18010f90a  lea     rax, [rbp+0F0h+wszAppidString]
0x18010f90e  test    this, this
0x18010f911  jz      short loc_18010F932
0x18010f913  movzx   r9d, word ptr [pUserToken]
0x18010f917  test    r9w, r9w
0x18010f91b  jz      short loc_18010F932
0x18010f91d  mov     [rax], r9w
0x18010f921  add     pUserToken, 2
0x18010f925  add     rax, 2
0x18010f929  dec     this
0x18010f92c  sub     rdx, 1
0x18010f930  jnz     short loc_18010F90E
0x18010f932  test    rdx, rdx
0x18010f935  lea     this, [rax-2]
0x18010f939  cmovnz  this, rax
0x18010f93d  mov     rax, rdx
0x18010f940  neg     rax
0x18010f943  sbb     ebx, ebx
0x18010f945  not     ebx
0x18010f947  mov     [this], r15w
0x18010f94b  and     ebx, 8007007Ah
0x18010f951  test    rdx, rdx
0x18010f954  jz      $Cleanup_5
0x18010f95a  lea     guidProcess, guidByteToStringPosition
0x18010f961  mov     r10, r13
0x18010f964  mov     eax, 6
0x18010f969  mov     dl, [r10]
0x18010f96c  lea     guidProcess, [guidProcess+4]
0x18010f970  mov     r8d, eax
0x18010f973  inc     r10
0x18010f976  mov     al, dl
0x18010f978  shr     al, 4
0x18010f97b  movzx   ecx, al
0x18010f97e  add     cx, 30h ; '0'
0x18010f982  cmp     cx, 39h ; '9'
0x18010f986  lea     eax, [this+7]
0x18010f989  cmovbe  ax, cx
0x18010f98d  and     dl, 0Fh
0x18010f990  mov     [rbp+pUserToken*2+0F0h+wszAppidString+0Eh], ax
0x18010f996  movzx   ecx, dl
0x18010f999  add     cx, 30h ; '0'
0x18010f99d  cmp     cx, 39h ; '9'
0x18010f9a1  lea     eax, [this+7]
0x18010f9a4  cmovbe  ax, cx
0x18010f9a8  mov     [rbp+pUserToken*2+0F0h+wszAppidString+10h], ax
0x18010f9ae  mov     eax, [guidProcess]
0x18010f9b1  test    eax, eax
0x18010f9b3  jns     short loc_18010F969
0x18010f9b5  mov     r15d, [r14+8]
0x18010f9b9  xor     r13d, r13d
0x18010f9bc  mov     rbx, [rbp+0F0h+hKeyRoot]
0x18010f9c0  mov     [rbp+0F0h+wszAppidString+1Eh], r11w
0x18010f9c5  mov     [rbp+0F0h+wszAppidString+28h], r11w
0x18010f9ca  mov     [rbp+0F0h+wszAppidString+32h], r11w
0x18010f9cf  mov     [rbp+0F0h+wszAppidString+3Ch], r11w
0x18010f9d4  cmp     r15d, 200h
0x18010f9db  jnz     short loc_18010F9EC
0x18010f9dd  movzx   ecx, word ptr [r14+0Ch]
0x18010f9e2  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x18010f9e8  movzx   r13d, ax
0x18010f9ec  mov     r9d, r15d
0x18010f9ef  lea     rax, [rbp+0F0h+hKey]
0x18010f9f3  or      r9d, 20019h; samDesired
0x18010f9fa  mov     [rsp+210h+format], rax; phkResult
0x18010f9ff  xor     r8d, r8d; ulOptions
0x18010fa02  lea     rdx, [rbp+0F0h+wszAppidString]; lpSubKey
0x18010fa06  mov     this, rbx; hKey
0x18010fa09  call    cs:__imp_RegOpenKeyExW
0x18010fa0f  mov     ebx, eax
0x18010fa11  cmp     r15d, 200h
0x18010fa18  jnz     short loc_18010FA24
0x18010fa1a  movzx   ecx, r13w
0x18010fa1e  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x18010fa24  xor     r15d, r15d
0x18010fa27  test    ebx, ebx
0x18010fa29  jnz     loc_18010FD56
0x18010fa2f  mov     eax, [rbp+0F0h+fForceToHKLM]
0x18010fa32  test    eax, eax
0x18010fa34  jnz     short loc_18010FA5D
0x18010fa36  mov     rax, [rdi]
0x18010fa39  lea     pUserToken, [rbp+0F0h+fForceToHKLM]
0x18010fa3d  mov     rdx, [rbp+0F0h+hKey]
0x18010fa41  mov     this, rdi
0x18010fa44  mov     rax, [rax+0A0h]
0x18010fa4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fa50  mov     ebx, eax
0x18010fa52  test    eax, eax
0x18010fa54  js      loc_18010FD47
0x18010fa5a  mov     eax, [rbp+0F0h+fForceToHKLM]
0x18010fa5d  cmp     cs:?g_bInSCM@@3JA, r15d; long g_bInSCM
0x18010fa64  jz      loc_18010FAF8
0x18010fa6a  test    eax, eax
0x18010fa6c  jnz     loc_18010FAF8
0x18010fa72  mov     rax, [rdi]
0x18010fa75  lea     pUserToken, [rbp+0F0h+fForceToHKLM]
0x18010fa79  mov     rdx, [rbp+0F0h+hKey]
  ... truncated ...
```
