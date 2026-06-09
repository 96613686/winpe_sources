# Microsoft::VisualStudio::PkgDef::CPkgDefManagement::ShouldLoadUserExtensions(void)

- ea: `0x14000a060`
- end: `0x14000a662`
- name: `?ShouldLoadUserExtensions@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@UEBA_NXZ`
- size: `1538`
- prototype: `bool __fastcall(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x140001020`
- `0x140002618`
- `0x140002c10`
- `0x140003160`
- `0x140007740`
- `0x1400095f4`
- `0x140009fb0`
- `0x14000a060`
- `0x14000a670`
- `0x14001c380`
- `0x140032de0`
- `0x140033ab0`
- `0x140036788`
- `0x1400464b0`
- `0x140046514`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000a3e3`
- `ADVAPI32!RegCloseKey` at `0x14000a604`
- `ADVAPI32!RegCloseKey` at `0x14000a3e3`
- `ADVAPI32!RegCloseKey` at `0x14000a604`
- `ADVAPI32!RegOpenKeyExW` at `0x14000a153`
- `ADVAPI32!RegOpenKeyExW` at `0x14000a3ce`
- `ADVAPI32!RegOpenKeyExW` at `0x14000a153`
- `ADVAPI32!RegOpenKeyExW` at `0x14000a3ce`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14000a11f`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14000a11f`
- `ADVAPI32!RevertToSelf` at `0x14000a5d4`
- `ADVAPI32!RevertToSelf` at `0x14000a5d4`

## string_xrefs

- `0x14000a0fd`: `ExtensionManager`
- `0x14000a337`: `ExtensionManager`
- `0x14000a478`: `EnableAdminExtensions`
- `0x14000a47f`: `EnableUserExtensions`
- `0x14000a51b`: `User extensions %s by setting`
- `0x14000a198`: `DisableUserExtensions`
- `0x14000a22f`: `DisableUserExtensions`
- `0x14000a0a5`: `Cannot check user extensions before pkgdef cache is created`
- `0x14000a248`: `User extensions disabled by global user extensions setting`
- `0x14000a2e0`: `Error while checking for global user extensions setting: `
- `0x14000a417`: `Error while checking for user extensions: `

## pseudocode

```c
// Hidden C++ exception states: #wind=9
bool __fastcall Microsoft::VisualStudio::PkgDef::CPkgDefManagement::ShouldLoadUserExtensions(
        Microsoft::VisualStudio::PkgDef::CPkgDefManagement *this)
{
  HKEY v3; // rbx
  ATL::CAtlTransactionManager *v4; // r12
  struct ATL::IAtlStringMgr *Instance; // rax
  bool v6; // r14
  LPCWSTR v7; // rdi
  LSTATUS v8; // eax
  signed int v9; // r15d
  bool v10; // r13
  int RegistryValue; // eax
  signed int v12; // ebx
  bool v13; // bl
  unsigned __int16 *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rax
  const unsigned __int16 **v17; // rax
  unsigned __int16 *v18; // rdx
  _QWORD *v19; // rdx
  _QWORD *v20; // rdx
  const unsigned __int16 **v21; // rax
  _QWORD *v22; // rdx
  _QWORD *UserSettingsRoot; // rax
  _QWORD *v24; // rdx
  __int64 v25; // rax
  HKEY v26; // rcx
  LSTATUS v27; // eax
  unsigned int v28; // ecx
  signed int v29; // esi
  const unsigned __int16 **v30; // rax
  _QWORD *v31; // rdx
  int v32; // eax
  const wchar_t *v33; // rdx
  int v34; // eax
  signed int v35; // ecx
  struct ATL::IAtlStringMgr *v36; // rax
  struct ATL::IAtlStringMgr *v37; // rax
  const wchar_t *v38; // r8
  unsigned __int16 *v39; // rbx
  HKEY v40; // rsi
  _QWORD *v41; // rdx
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-29h] BYREF
  bool v43; // [rsp+40h] [rbp-21h]
  unsigned __int16 *v44; // [rsp+48h] [rbp-19h] BYREF
  __int64 v45; // [rsp+50h] [rbp-11h] BYREF
  HKEY hKey[2]; // [rsp+58h] [rbp-9h] BYREF
  ATL::CAtlTransactionManager *v47; // [rsp+68h] [rbp+7h]
  __int64 v48; // [rsp+70h] [rbp+Fh] BYREF
  __int64 v49; // [rsp+78h] [rbp+17h] BYREF
  int v50; // [rsp+80h] [rbp+1Fh] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+27h] BYREF

  if ( !*((_QWORD *)this + 2) )
  {
    CLogger::LogError(L"Cannot check user extensions before pkgdef cache is created", -2147418113, 0);
    return 0;
  }
  if ( (*(unsigned __int8 (__fastcall **)(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *))(*(_QWORD *)this + 264LL))(this) )
    return 0;
  v3 = 0;
  hKey[0] = 0;
  hKey[1] = 0;
  v4 = 0;
  v47 = 0;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  lpSubKey = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                     + 24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &lpSubKey,
    L"%s\\%s",
    *((_QWORD *)this + 14),
    L"ExtensionManager");
  v6 = ImpersonateLoggedOnUser(*((HANDLE *)this + 24));
  v43 = v6;
  phkResult = 0;
  v7 = lpSubKey;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &phkResult);
  if ( !v8 )
  {
    v3 = phkResult;
    hKey[0] = phkResult;
    LODWORD(hKey[1]) = 0;
  }
  v9 = (unsigned __int16)(v8 != 0 ? v8 : 0) | 0x80070000;
  if ( (v8 != 0 ? v8 : 0) <= 0 )
    v9 = v8 != 0 ? v8 : 0;
  v10 = 1;
  if ( v9 < 0 )
  {
    if ( (_WORD)v9 != 2 )
    {
      _mm_lfence();
      v21 = (const unsigned __int16 **)ATL::operator+(
                                         &v45,
                                         L"Error while checking for global user extensions setting: ",
                                         &lpSubKey);
      CLogger::LogWarn(*v21, v9, 0);
      v22 = (_QWORD *)(v45 - 24);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v45 - 24 + 16), 0xFFFFFFFF) <= 1 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v22 + 8LL))(*v22);
      }
    }
  }
  else
  {
    LODWORD(phkResult) = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v44,
      L"DisableUserExtensions");
    RegistryValue = GetRegistryValue(hKey, &v44, &phkResult);
    v12 = (unsigned __int16)RegistryValue | 0x80070000;
    if ( RegistryValue <= 0 )
      v12 = RegistryValue;
    v13 = v12 >= 0;
    v14 = v44 - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)v44 - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
    }
    if ( v13 && (_DWORD)phkResult )
    {
      v15 = ATL::operator+(&v45, L"HKEY_LOCAL_MACHINE\\", &lpSubKey);
      v16 = ATL::operator+(&v49, v15, L"\\");
      v17 = (const unsigned __int16 **)ATL::operator+(&v44, v16, L"DisableUserExtensions");
      CLogger::LogInfo(L"User extensions disabled by global user extensions setting", 0, *v17);
      v18 = v44 - 12;
      if ( _InterlockedDecrement((volatile signed __int32 *)v44 - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v18 + 8LL))(*(_QWORD *)v18);
      }
      v19 = (_QWORD *)(v49 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v49 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 8LL))(*v19);
      }
      v20 = (_QWORD *)(v45 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v45 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 8LL))(*v20);
      }
      v10 = 0;
      goto LABEL_63;
    }
    v4 = v47;
    v3 = hKey[0];
  }
  UserSettingsRoot = (_QWORD *)CPkgDefCache::GetUserSettingsRoot(*((_QWORD *)this + 2), &v45);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &lpSubKey,
    L"%s\\%s",
    *UserSettingsRoot,
    L"ExtensionManager");
  v24 = (_QWORD *)(v45 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v45 - 24 + 16), 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v24 + 8LL))(*v24);
  }
  v25 = *((_QWORD *)this + 2);
  v26 = ::hKey;
  if ( *(_QWORD *)(v25 + 232) )
    v26 = *(HKEY *)(v25 + 232);
  phkResult = 0;
  v7 = lpSubKey;
  if ( v4 )
    v27 = ATL::CAtlTransactionManager::RegOpenKeyExW(v4, v26, lpSubKey, 0, 0x20019u, &phkResult);
  else
    v27 = RegOpenKeyExW(v26, lpSubKey, 0, 0x20019u, &phkResult);
  if ( !v27 )
  {
    v27 = 0;
    if ( v3 )
      v27 = RegCloseKey(v3);
    v3 = phkResult;
    hKey[0] = phkResult;
    LODWORD(hKey[1]) = 0;
  }
  v29 = (unsigned __int16)v27 | 0x80070000;
  if ( v27 <= 0 )
    v29 = v27;
  if ( v29 < 0 )
  {
    if ( (_WORD)v29 != 2 )
    {
      _mm_lfence();
      v30 = (const unsigned __int16 **)ATL::operator+(&v45, L"Error while checking for user extensions: ", &lpSubKey);
      CLogger::LogWarn(*v30, v29, 0);
      v31 = (_QWORD *)(v45 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v45 - 24 + 16)) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v31 + 8LL))(*v31);
      }
    }
    goto LABEL_64;
  }
  v32 = IsUserInGroupRID(v28);
  v48 = 0;
  v33 = L"EnableUserExtensions";
  if ( v32 )
    v33 = L"EnableAdminExtensions";
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v48,
    v33);
  v34 = GetRegistryValue(hKey, &v48, &v50);
  v35 = (unsigned __int16)v34 | 0x80070000;
  if ( v34 <= 0 )
    v35 = v34;
  if ( v35 < 0 )
  {
    v50 = 1;
  }
  else if ( CLogger::ms_bLoggingOn )
  {
    v36 = ATL::CAtlStringMgr::GetInstance();
    if ( !v36 )
      ATL::AtlThrowImpl(-2147467259);
    phkResult = (HKEY)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v36 + 24LL))(v36) + 24);
    v37 = ATL::CAtlStringMgr::GetInstance();
    if ( !v37 )
      ATL::AtlThrowImpl(-2147467259);
    v44 = (unsigned __int16 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v37 + 24LL))(v37) + 24);
    v38 = L"disabled";
    if ( v50 )
      v38 = L"enabled";
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &phkResult,
      L"User extensions %s by setting",
      v38);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &v44,
      L"HKEY_CURRENT_USER\\%s\\%s",
      v7,
      v48);
    v39 = v44;
    v40 = phkResult;
    CLogger::LogInfo((const unsigned __int16 *)phkResult, 0, v44);
    if ( _InterlockedDecrement((volatile signed __int32 *)v39 - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v39 - 3) + 8LL))(*((_QWORD *)v39 - 3));
    }
    if ( _InterlockedDecrement((volatile signed __int32 *)v40 - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v40 - 3) + 8LL))(*((_QWORD *)v40 - 3));
    }
  }
  v10 = v50 != 0;
  v41 = (_QWORD *)(v48 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v48 - 24 + 16)) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v41 + 8LL))(*v41);
  }
LABEL_63:
  v3 = hKey[0];
LABEL_64:
  if ( v6 )
    RevertToSelf();
  if ( _InterlockedDecrement((volatile signed __int32 *)v7 - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 - 3) + 8LL))(*((_QWORD *)v7 - 3));
  }
  if ( v3 )
    RegCloseKey(v3);
  return v10;
}

```

## disassembly

```asm
0x14000a060  mov     rax, rsp
0x14000a063  mov     [rax+10h], rbx
0x14000a067  mov     [rax+18h], rsi
0x14000a06b  mov     [rax+20h], rdi
0x14000a06f  push    rbp
0x14000a070  push    r12
0x14000a072  push    r13
0x14000a074  push    r14
0x14000a076  push    r15
0x14000a078  lea     rbp, [rax-5Fh]
0x14000a07c  sub     rsp, 90h
0x14000a083  mov     rax, cs:__security_cookie
0x14000a08a  xor     rax, rsp
0x14000a08d  mov     [rbp+57h+var_28], rax
0x14000a091  mov     rsi, rcx
0x14000a094  xor     r13d, r13d
0x14000a097  cmp     [rcx+10h], r13
0x14000a09b  jnz     short loc_14000A0B8
0x14000a09d  xor     r8d, r8d; unsigned __int16 *
0x14000a0a0  mov     edx, 8000FFFFh; int
0x14000a0a5  lea     rcx, aCannotCheckUse; "Cannot check user extensions before pkg"...
0x14000a0ac  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x14000a0b1  xor     al, al
0x14000a0b3  jmp     loc_14000A60D
0x14000a0b8  mov     rax, [rcx]
0x14000a0bb  call    qword ptr [rax+108h]
0x14000a0c1  test    al, al
0x14000a0c3  jnz     short loc_14000A0B1
0x14000a0c5  xorps   xmm0, xmm0
0x14000a0c8  movups  xmmword ptr [rbp+57h+hKey], xmm0
0x14000a0cc  mov     rbx, r13
0x14000a0cf  mov     [rbp+57h+hKey], rbx
0x14000a0d3  mov     dword ptr [rbp+57h+hKey+8], r13d
0x14000a0d7  mov     r12, r13
0x14000a0da  mov     [rbp+57h+var_50], r13
0x14000a0de  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14000a0e3  mov     rcx, rax
0x14000a0e6  test    rax, rax
0x14000a0e9  jz      loc_14000A649
0x14000a0ef  mov     rax, [rax]
0x14000a0f2  call    qword ptr [rax+18h]
0x14000a0f5  add     rax, 18h
0x14000a0f9  mov     [rbp+57h+lpSubKey], rax
0x14000a0fd  lea     r9, aExtensionmanag_1; "ExtensionManager"
0x14000a104  mov     r8, [rsi+70h]
0x14000a108  lea     rdx, aSS_2; "%s\\%s"
0x14000a10f  lea     rcx, [rbp+57h+lpSubKey]
0x14000a113  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x14000a118  mov     rcx, [rsi+0C0h]; hToken
0x14000a11f  call    cs:__imp_ImpersonateLoggedOnUser
0x14000a125  test    eax, eax
0x14000a127  setnz   r14b
0x14000a12b  mov     [rbp+57h+var_78], r14b
0x14000a12f  mov     [rbp+57h+var_30], r13
0x14000a133  lea     rax, [rbp+57h+var_30]
0x14000a137  mov     [rsp+0B0h+phkResult], rax; phkResult
0x14000a13c  mov     r9d, 20019h; samDesired
0x14000a142  xor     r8d, r8d; ulOptions
0x14000a145  mov     rdi, [rbp+57h+lpSubKey]
0x14000a149  mov     rdx, rdi; lpSubKey
0x14000a14c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000a153  call    cs:__imp_RegOpenKeyExW
0x14000a159  test    eax, eax
0x14000a15b  jnz     short loc_14000A169
0x14000a15d  mov     rbx, [rbp+57h+var_30]
0x14000a161  mov     [rbp+57h+hKey], rbx
0x14000a165  mov     dword ptr [rbp+57h+hKey+8], r13d
0x14000a169  mov     ecx, eax
0x14000a16b  neg     ecx
0x14000a16d  sbb     edx, edx
0x14000a16f  and     edx, eax
0x14000a171  movzx   r15d, dx
0x14000a175  or      r15d, 80070000h
0x14000a17c  test    edx, edx
0x14000a17e  cmovle  r15d, edx
0x14000a182  mov     r13d, 1
0x14000a188  test    r15d, r15d
0x14000a18b  js      loc_14000A2D2
0x14000a191  xor     r15d, r15d
0x14000a194  mov     dword ptr [rbp+57h+var_30], r15d
0x14000a198  lea     rdx, aDisableuserext; "DisableUserExtensions"
0x14000a19f  lea     rcx, [rbp+57h+var_70]
0x14000a1a3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14000a1a8  lea     r8, [rbp+57h+var_30]
0x14000a1ac  lea     rdx, [rbp+57h+var_70]
0x14000a1b0  lea     rcx, [rbp+57h+hKey]
0x14000a1b4  call    ?GetRegistryValue@@YAJAEBVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAK@Z; GetRegistryValue(ATL::CRegKey const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong &)
0x14000a1b9  movzx   ebx, ax
0x14000a1bc  or      ebx, 80070000h
0x14000a1c2  test    eax, eax
0x14000a1c4  cmovle  ebx, eax
0x14000a1c7  shr     ebx, 1Fh
0x14000a1ca  xor     bl, r13b
0x14000a1cd  mov     rdx, [rbp+57h+var_70]
0x14000a1d1  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000a1d5  or      r12d, 0FFFFFFFFh
0x14000a1d9  mov     eax, r12d
0x14000a1dc  lock xadd [rdx+10h], eax
0x14000a1e1  add     eax, r12d
0x14000a1e4  test    eax, eax
0x14000a1e6  jg      short loc_14000A1F4
0x14000a1e8  lfence
0x14000a1eb  mov     rcx, [rdx]
0x14000a1ee  mov     rax, [rcx]
0x14000a1f1  call    qword ptr [rax+8]
0x14000a1f4  test    bl, bl
0x14000a1f6  jz      loc_14000A2C8
0x14000a1fc  cmp     dword ptr [rbp+57h+var_30], r15d
0x14000a200  jz      loc_14000A2C8
0x14000a206  lea     r8, [rbp+57h+lpSubKey]
0x14000a20a  lea     rdx, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE\\"
0x14000a211  lea     rcx, [rbp+57h+var_68]
0x14000a215  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBGAEBV10@@Z; ATL::operator+(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000a21a  nop
0x14000a21b  lea     r8, SubBlock; "\\"
0x14000a222  mov     rdx, rax
0x14000a225  lea     rcx, [rbp+57h+var_40]
0x14000a229  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x14000a22e  nop
0x14000a22f  lea     r8, aDisableuserext; "DisableUserExtensions"
0x14000a236  mov     rdx, rax
0x14000a239  lea     rcx, [rbp+57h+var_70]
0x14000a23d  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x14000a242  nop
0x14000a243  mov     r8, [rax]; unsigned __int16 *
0x14000a246  xor     edx, edx; int
0x14000a248  lea     rcx, aUserExtensions_0; "User extensions disabled by global user"...
0x14000a24f  call    ?LogInfo@CLogger@@SAXPEBGJ0@Z; CLogger::LogInfo(ushort const *,long,ushort const *)
0x14000a254  nop
0x14000a255  mov     rdx, [rbp+57h+var_70]
0x14000a259  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000a25d  mov     eax, r12d
0x14000a260  lock xadd [rdx+10h], eax
0x14000a265  add     eax, r12d
0x14000a268  test    eax, eax
0x14000a26a  jg      short loc_14000A279
0x14000a26c  lfence
0x14000a26f  mov     rcx, [rdx]
0x14000a272  mov     rax, [rcx]
0x14000a275  call    qword ptr [rax+8]
0x14000a278  nop
0x14000a279  mov     rdx, [rbp+57h+var_40]
0x14000a27d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000a281  mov     eax, r12d
0x14000a284  lock xadd [rdx+10h], eax
0x14000a289  add     eax, r12d
0x14000a28c  test    eax, eax
0x14000a28e  jg      short loc_14000A29D
0x14000a290  lfence
0x14000a293  mov     rcx, [rdx]
0x14000a296  mov     rax, [rcx]
0x14000a299  call    qword ptr [rax+8]
0x14000a29c  nop
0x14000a29d  mov     rdx, [rbp+57h+var_68]
0x14000a2a1  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000a2a5  mov     eax, r12d
0x14000a2a8  lock xadd [rdx+10h], eax
0x14000a2ad  add     eax, r12d
0x14000a2b0  test    eax, eax
0x14000a2b2  jg      short loc_14000A2C0
0x14000a2b4  lfence
0x14000a2b7  mov     rcx, [rdx]
0x14000a2ba  mov     rax, [rcx]
0x14000a2bd  call    qword ptr [rax+8]
0x14000a2c0  mov     r13b, r15b
0x14000a2c3  jmp     loc_14000A5CB
0x14000a2c8  mov     r12, [rbp+57h+var_50]
0x14000a2cc  mov     rbx, [rbp+57h+hKey]
0x14000a2d0  jmp     short loc_14000A329
0x14000a2d2  cmp     r15w, 2
0x14000a2d7  jz      short loc_14000A326
0x14000a2d9  lfence
0x14000a2dc  lea     r8, [rbp+57h+lpSubKey]
0x14000a2e0  lea     rdx, aErrorWhileChec; "Error while checking for global user ex"...
0x14000a2e7  lea     rcx, [rbp+57h+var_68]
0x14000a2eb  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBGAEBV10@@Z; ATL::operator+(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000a2f0  nop
0x14000a2f1  xor     r8d, r8d; unsigned __int16 *
0x14000a2f4  mov     edx, r15d; int
0x14000a2f7  mov     rcx, [rax]; unsigned __int16 *
0x14000a2fa  call    ?LogWarn@CLogger@@SAXPEBGJ0@Z; CLogger::LogWarn(ushort const *,long,ushort const *)
0x14000a2ff  nop
0x14000a300  mov     rdx, [rbp+57h+var_68]
0x14000a304  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000a308  or      eax, 0FFFFFFFFh
0x14000a30b  lock xadd [rdx+10h], eax
0x14000a310  xor     r15d, r15d
0x14000a313  sub     eax, 1
0x14000a316  jg      short loc_14000A329
0x14000a318  lfence
0x14000a31b  mov     rcx, [rdx]
0x14000a31e  mov     rax, [rcx]
0x14000a321  call    qword ptr [rax+8]
0x14000a324  jmp     short loc_14000A329
0x14000a326  xor     r15d, r15d
0x14000a329  lea     rdx, [rbp+57h+var_68]
0x14000a32d  mov     rcx, [rsi+10h]
0x14000a331  call    ?GetUserSettingsRoot@CPkgDefCache@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPkgDefCache::GetUserSettingsRoot(void)
0x14000a336  nop
0x14000a337  lea     r9, aExtensionmanag_1; "ExtensionManager"
0x14000a33e  mov     r8, [rax]
0x14000a341  lea     rdx, aSS_2; "%s\\%s"
0x14000a348  lea     rcx, [rbp+57h+lpSubKey]
0x14000a34c  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x14000a351  nop
0x14000a352  mov     rdx, [rbp+57h+var_68]
0x14000a356  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000a35a  or      eax, 0FFFFFFFFh
0x14000a35d  lock xadd [rdx+10h], eax
0x14000a362  sub     eax, 1
0x14000a365  jg      short loc_14000A373
0x14000a367  lfence
0x14000a36a  mov     rcx, [rdx]
0x14000a36d  mov     rax, [rcx]
0x14000a370  call    qword ptr [rax+8]
0x14000a373  mov     rax, [rsi+10h]
0x14000a377  mov     r8, [rax+0E8h]
0x14000a37e  mov     rcx, cs:hKey
0x14000a385  test    r8, r8
0x14000a388  cmovnz  rcx, r8; hKey
0x14000a38c  mov     [rbp+57h+var_30], r15
0x14000a390  lea     rax, [rbp+57h+var_30]
0x14000a394  mov     rdi, [rbp+57h+lpSubKey]
0x14000a398  test    r12, r12
0x14000a39b  jz      short loc_14000A3BD
0x14000a39d  mov     [rsp+0B0h+var_88], rax; HKEY *
0x14000a3a2  mov     dword ptr [rsp+0B0h+phkResult], 20019h; unsigned int
0x14000a3aa  xor     r9d, r9d; unsigned int
0x14000a3ad  mov     r8, rdi; unsigned __int16 *
0x14000a3b0  mov     rdx, rcx; HKEY
0x14000a3b3  mov     rcx, r12; this
0x14000a3b6  call    ?RegOpenKeyExW@CAtlTransactionManager@ATL@@QEAAJPEAUHKEY__@@PEBGKKPEAPEAU3@@Z; ATL::CAtlTransactionManager::RegOpenKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x14000a3bb  jmp     short loc_14000A3D4
0x14000a3bd  mov     [rsp+0B0h+phkResult], rax; phkResult
0x14000a3c2  mov     r9d, 20019h; samDesired
0x14000a3c8  xor     r8d, r8d; ulOptions
0x14000a3cb  mov     rdx, rdi; lpSubKey
0x14000a3ce  call    cs:__imp_RegOpenKeyExW
0x14000a3d4  test    eax, eax
0x14000a3d6  jnz     short loc_14000A3F5
0x14000a3d8  mov     eax, r15d
0x14000a3db  test    rbx, rbx
0x14000a3de  jz      short loc_14000A3E9
0x14000a3e0  mov     rcx, rbx; hKey
0x14000a3e3  call    cs:__imp_RegCloseKey
0x14000a3e9  mov     rbx, [rbp+57h+var_30]
0x14000a3ed  mov     [rbp+57h+hKey], rbx
0x14000a3f1  mov     dword ptr [rbp+57h+hKey+8], r15d
0x14000a3f5  movzx   esi, ax
0x14000a3f8  mov     r12d, 80070000h
0x14000a3fe  or      esi, r12d
0x14000a401  test    eax, eax
0x14000a403  cmovle  esi, eax
0x14000a406  test    esi, esi
0x14000a408  jns     short loc_14000A46F
0x14000a40a  cmp     si, 2
0x14000a40e  jz      short loc_14000A466
0x14000a410  lfence
0x14000a413  lea     r8, [rbp+57h+lpSubKey]
0x14000a417  lea     rdx, aErrorWhileChec_0; "Error while checking for user extension"...
0x14000a41e  lea     rcx, [rbp+57h+var_68]
0x14000a422  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@PEBGAEBV10@@Z; ATL::operator+(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000a427  nop
0x14000a428  xor     r8d, r8d; unsigned __int16 *
0x14000a42b  mov     edx, esi; int
0x14000a42d  mov     rcx, [rax]; unsigned __int16 *
0x14000a430  call    ?LogWarn@CLogger@@SAXPEBGJ0@Z; CLogger::LogWarn(ushort const *,long,ushort const *)
0x14000a435  nop
0x14000a436  mov     rdx, [rbp+57h+var_68]
0x14000a43a  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14000a43e  or      r12d, 0FFFFFFFFh
0x14000a442  mov     eax, r12d
0x14000a445  lock xadd [rdx+10h], eax
0x14000a44a  add     eax, r12d
0x14000a44d  test    eax, eax
0x14000a44f  jg      loc_14000A5CF
0x14000a455  lfence
0x14000a458  mov     rcx, [rdx]
0x14000a45b  mov     rax, [rcx]
0x14000a45e  call    qword ptr [rax+8]
0x14000a461  jmp     loc_14000A5CF
0x14000a466  or      r12d, 0FFFFFFFFh
0x14000a46a  jmp     loc_14000A5CF
0x14000a46f  call    ?IsUserInGroupRID@@YAHK@Z; IsUserInGroupRID(ulong)
0x14000a474  mov     [rbp+57h+var_48], r15
0x14000a478  lea     rcx, aEnableadminext; "EnableAdminExtensions"
0x14000a47f  lea     rdx, aEnableuserexte; "EnableUserExtensions"
0x14000a486  test    eax, eax
0x14000a488  cmovnz  rdx, rcx
0x14000a48c  lea     rcx, [rbp+57h+var_48]
0x14000a490  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14000a495  nop
0x14000a496  lea     r8, [rbp+57h+var_38]
0x14000a49a  lea     rdx, [rbp+57h+var_48]
0x14000a49e  lea     rcx, [rbp+57h+hKey]
0x14000a4a2  call    ?GetRegistryValue@@YAJAEBVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAK@Z; GetRegistryValue(ATL::CRegKey const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong &)
0x14000a4a7  movzx   ecx, ax
0x14000a4aa  or      ecx, r12d
0x14000a4ad  test    eax, eax
0x14000a4af  cmovle  ecx, eax
  ... truncated ...
```
