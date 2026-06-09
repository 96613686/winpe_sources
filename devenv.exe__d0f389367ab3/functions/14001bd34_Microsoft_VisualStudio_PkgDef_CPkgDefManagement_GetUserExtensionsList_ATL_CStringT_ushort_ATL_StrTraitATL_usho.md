# Microsoft::VisualStudio::PkgDef::CPkgDefManagement::GetUserExtensionsList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &,bool)

- ea: `0x14001bd34`
- end: `0x14001c378`
- name: `?GetUserExtensionsList@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@6@_N@Z`
- size: `1604`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001bb90`
- `0x14001c440`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140002dd0`
- `0x140003160`
- `0x1400094b8`
- `0x14000fb64`
- `0x14001bd34`
- `0x14001c380`
- `0x14001c8f8`
- `0x140027c20`
- `0x140033ab0`
- `0x1400464b0`
- `0x140046514`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14001c31c`
- `ADVAPI32!RegCloseKey` at `0x14001c337`
- `ADVAPI32!RegCloseKey` at `0x14001c31c`
- `ADVAPI32!RegCloseKey` at `0x14001c337`
- `ADVAPI32!RegOpenKeyExW` at `0x14001bde8`
- `ADVAPI32!RegOpenKeyExW` at `0x14001be9b`
- `ADVAPI32!RegOpenKeyExW` at `0x14001bde8`
- `ADVAPI32!RegOpenKeyExW` at `0x14001be9b`
- `ADVAPI32!RegEnumValueW` at `0x14001bf37`
- `ADVAPI32!RegEnumValueW` at `0x14001c2da`
- `ADVAPI32!RegEnumValueW` at `0x14001bf37`
- `ADVAPI32!RegEnumValueW` at `0x14001c2da`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14001bda3`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14001bda3`
- `ADVAPI32!RevertToSelf` at `0x14001c328`
- `ADVAPI32!RevertToSelf` at `0x14001c328`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x14001c178`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x14001c178`

## string_xrefs

- `0x14001be2f`: `Error while accessing list of extensions`
- `0x14001bed7`: `Error while accessing list of extension types`
- `0x14001bf8f`: `Error while enumerating extensions list`
- `0x14001c023`: `Expected only strings in enabled extensions list`
- `0x14001c114`: `Could not query type for extension.`
- `0x14001c234`: `Error while retrieving enabled extension path`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall Microsoft::VisualStudio::PkgDef::CPkgDefManagement::GetUserExtensionsList(
        __int64 a1,
        LPCWSTR *a2,
        LPCWSTR *a3,
        __int64 a4,
        char a5)
{
  LPCWSTR *v6; // r15
  HKEY v8; // rsi
  bool v9; // di
  __int64 v10; // rax
  HKEY v11; // rcx
  LSTATUS v12; // eax
  signed int v13; // edx
  HKEY v14; // rbx
  __int64 v15; // rax
  HKEY v16; // rcx
  LSTATUS v17; // eax
  signed int v18; // edx
  struct ATL::IAtlStringMgr *Instance; // rax
  DWORD v20; // r12d
  LSTATUS v21; // eax
  signed int v22; // ebx
  __int64 v23; // rax
  const unsigned __int16 **v24; // rax
  _QWORD *v25; // rdx
  __int64 v26; // rdx
  volatile signed __int32 *v27; // rdx
  __int64 v28; // rax
  const unsigned __int16 **v29; // rax
  _QWORD *v30; // rdx
  bool v31; // r15
  struct ATL::IAtlStringMgr *v32; // rax
  __int64 v33; // rax
  unsigned __int16 *v34; // rbx
  int v35; // eax
  signed int v36; // r14d
  __int64 v37; // rax
  const unsigned __int16 **v38; // rax
  _QWORD *v39; // rdx
  _QWORD *v40; // rdx
  int RegistryValue; // ebx
  _QWORD *v42; // rdx
  __int64 v43; // rax
  const unsigned __int16 **v44; // rax
  _QWORD *v45; // rdx
  _QWORD *v46; // rdx
  HKEY v47; // rdx
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  bool v49; // [rsp+48h] [rbp-B8h]
  unsigned int v50; // [rsp+4Ch] [rbp-B4h] BYREF
  LPCWSTR *v51; // [rsp+50h] [rbp-B0h]
  __int128 v52; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v53; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v54; // [rsp+70h] [rbp-90h] BYREF
  __int64 v55; // [rsp+78h] [rbp-88h] BYREF
  __int128 v56; // [rsp+80h] [rbp-80h] BYREF
  __int64 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h] BYREF
  __int64 v59; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v60; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v61; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR *v62; // [rsp+B8h] [rbp-48h]
  __int64 v63; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v64; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v65; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v66; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v67; // [rsp+E0h] [rbp-20h]
  DWORD cchValueName; // [rsp+E8h] [rbp-18h] BYREF
  DWORD Type; // [rsp+ECh] [rbp-14h] BYREF
  WCHAR ValueName[264]; // [rsp+F0h] [rbp-10h] BYREF

  v67 = a4;
  v62 = a3;
  v6 = a2;
  v51 = a2;
  ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(a4);
  v53 = 0;
  v8 = 0;
  v52 = 0u;
  v9 = ImpersonateLoggedOnUser(*(HANDLE *)(a1 + 192));
  v49 = v9;
  v10 = *(_QWORD *)(a1 + 16);
  v11 = hKey;
  if ( *(_QWORD *)(v10 + 232) )
    v11 = *(HKEY *)(v10 + 232);
  phkResult = 0;
  v12 = RegOpenKeyExW(v11, *v6, 0, 0x20019u, &phkResult);
  if ( !v12 )
  {
    v8 = phkResult;
    *(_QWORD *)&v52 = phkResult;
    DWORD2(v52) = 0;
  }
  v13 = (unsigned __int16)(v12 != 0 ? v12 : 0) | 0x80070000;
  if ( (v12 != 0 ? v12 : 0) <= 0 )
    v13 = v12 != 0 ? v12 : 0;
  if ( v13 < 0 )
  {
    if ( (_WORD)v13 != 2 )
    {
      _mm_lfence();
      CLogger::LogWarn(L"Error while accessing list of extensions", v13, *v6);
    }
    goto LABEL_64;
  }
  v57 = 0;
  v14 = 0;
  v56 = 0u;
  if ( a5 )
    goto LABEL_19;
  v15 = *(_QWORD *)(a1 + 16);
  v16 = hKey;
  if ( *(_QWORD *)(v15 + 232) )
    v16 = *(HKEY *)(v15 + 232);
  phkResult = 0;
  v17 = RegOpenKeyExW(v16, *a3, 0, 0x20019u, &phkResult);
  if ( !v17 )
  {
    v14 = phkResult;
    *(_QWORD *)&v56 = phkResult;
    DWORD2(v56) = 0;
  }
  v18 = (unsigned __int16)(v17 != 0 ? v17 : 0) | 0x80070000;
  if ( (v17 != 0 ? v17 : 0) <= 0 )
    v18 = v17 != 0 ? v17 : 0;
  if ( v18 >= 0 )
  {
LABEL_19:
    cchValueName = 261;
    Instance = ATL::CAtlStringMgr::GetInstance();
    if ( !Instance )
      ATL::AtlThrowImpl(-2147467259);
    phkResult = (HKEY)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                     + 24);
    v20 = 0;
    v21 = RegEnumValueW(v8, 0, ValueName, &cchValueName, 0, &Type, 0, 0);
    if ( v21 == 259 )
    {
LABEL_60:
      v47 = phkResult - 6;
      if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v47 + 8LL))(*(_QWORD *)v47);
      }
      goto LABEL_62;
    }
    while ( 1 )
    {
      v22 = (unsigned __int16)v21 | 0x80070000;
      if ( v21 <= 0 )
        v22 = v21;
      if ( v22 < 0 )
        break;
      if ( Type != 1 )
      {
        v28 = ATL::operator+(&v61, v6, L"\\");
        v29 = (const unsigned __int16 **)ATL::operator+(&v60, v28, ValueName);
        CLogger::LogError(L"Expected only strings in enabled extensions list", -2147418113, *v29);
        v30 = (_QWORD *)(v60 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v60 - 24 + 16)) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v30 + 8LL))(*v30);
        }
        v26 = v61;
        goto LABEL_27;
      }
      v31 = 0;
      if ( a5 )
        goto LABEL_48;
      v32 = ATL::CAtlStringMgr::GetInstance();
      if ( !v32 )
        ATL::AtlThrowImpl(-2147467259);
      v33 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v32 + 24LL))(v32);
      v34 = (unsigned __int16 *)(v33 + 24);
      v54 = (unsigned __int16 *)(v33 + 24);
      v50 = 260;
      if ( ((1 - *(_DWORD *)(v33 + 16)) | (*(_DWORD *)(v33 + 12) - 260)) < 0 )
      {
        ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v54, 260);
        v34 = v54;
      }
      v35 = ATL::CRegKey::QueryStringValue((ATL::CRegKey *)&v56, ValueName, v34, &v50);
      v36 = (unsigned __int16)v35 | 0x80070000;
      if ( v35 <= 0 )
        v36 = v35;
      if ( v36 >= 0 )
      {
        v31 = _wcsicmp(v34, L"Microsoft.VisualStudio.Sample") == 0;
      }
      else
      {
        _mm_lfence();
        v37 = ATL::operator+(&v64, v62, L"\\");
        v38 = (const unsigned __int16 **)ATL::operator+(&v63, v37, ValueName);
        CLogger::LogWarn(L"Could not query type for extension.", v36, *v38);
        v39 = (_QWORD *)(v63 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v63 - 24 + 16)) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v39 + 8LL))(*v39);
        }
        v40 = (_QWORD *)(v64 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v64 - 24 + 16)) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v40 + 8LL))(*v40);
        }
      }
      if ( _InterlockedDecrement((volatile signed __int32 *)v34 - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v34 - 3) + 8LL))(*((_QWORD *)v34 - 3));
      }
      if ( !v31 )
      {
LABEL_48:
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v55,
          ValueName);
        RegistryValue = GetRegistryValue(&v52, &v55, &phkResult);
        v42 = (_QWORD *)(v55 - 24);
        if ( _InterlockedDecrement((volatile signed __int32 *)(v55 - 24 + 16)) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v42 + 8LL))(*v42);
        }
        if ( RegistryValue < 0 )
        {
          _mm_lfence();
          v6 = v51;
          v43 = ATL::operator+(&v66, v51, L"\\");
          v44 = (const unsigned __int16 **)ATL::operator+(&v65, v43, ValueName);
          CLogger::LogError(L"Error while retrieving enabled extension path", RegistryValue, *v44);
          v45 = (_QWORD *)(v65 - 24);
          if ( _InterlockedDecrement((volatile signed __int32 *)(v65 - 24 + 16)) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v45 + 8LL))(*v45);
          }
          v46 = (_QWORD *)(v66 - 24);
          if ( _InterlockedDecrement((volatile signed __int32 *)(v66 - 24 + 16)) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v46 + 8LL))(*v46);
          }
          v8 = (HKEY)v52;
          goto LABEL_58;
        }
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddTail(
          v67,
          phkResult);
        v8 = (HKEY)v52;
      }
      v6 = v51;
LABEL_58:
      ++v20;
      cchValueName = 261;
      v21 = RegEnumValueW(v8, v20, ValueName, &cchValueName, 0, &Type, 0, 0);
      if ( v21 == 259 )
      {
        v14 = (HKEY)v56;
        goto LABEL_60;
      }
    }
    _mm_lfence();
    v23 = ATL::operator+(&v59, v6, L"\\");
    v24 = (const unsigned __int16 **)ATL::operator+(&v58, v23, ValueName);
    CLogger::LogError(L"Error while enumerating extensions list", v22, *v24);
    v25 = (_QWORD *)(v58 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v58 - 24 + 16)) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v25 + 8LL))(*v25);
    }
    v26 = v59;
LABEL_27:
    v27 = (volatile signed __int32 *)(v26 - 24);
    if ( _InterlockedDecrement(v27 + 4) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v27 + 8LL))(*(_QWORD *)v27);
    }
    goto LABEL_58;
  }
  _mm_lfence();
  CLogger::LogError(L"Error while accessing list of extension types", v18, *a3);
LABEL_62:
  if ( v14 )
    RegCloseKey(v14);
LABEL_64:
  if ( v9 )
    RevertToSelf();
  if ( v8 )
    RegCloseKey(v8);
}

```

## disassembly

```asm
0x14001bd34  push    rbp
0x14001bd36  push    rbx
0x14001bd37  push    rsi
0x14001bd38  push    rdi
0x14001bd39  push    r12
0x14001bd3b  push    r14
0x14001bd3d  push    r15
0x14001bd3f  lea     rbp, [rsp-210h]
0x14001bd47  sub     rsp, 310h
0x14001bd4e  mov     rax, cs:__security_cookie
0x14001bd55  xor     rax, rsp
0x14001bd58  mov     [rbp+240h+var_40], rax
0x14001bd5f  mov     [rbp+240h+var_260], r9
0x14001bd63  mov     r12, r8
0x14001bd66  mov     [rbp+240h+var_288], r8
0x14001bd6a  mov     r15, rdx
0x14001bd6d  mov     [rsp+340h+var_2F0], rdx
0x14001bd72  mov     r14, rcx
0x14001bd75  mov     rcx, r9
0x14001bd78  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x14001bd7d  xorps   xmm0, xmm0
0x14001bd80  xor     eax, eax
0x14001bd82  movups  [rsp+340h+var_2E8], xmm0
0x14001bd87  mov     [rsp+340h+var_2D8], rax
0x14001bd8c  xor     esi, esi
0x14001bd8e  mov     qword ptr [rsp+340h+var_2E8], rsi
0x14001bd93  and     dword ptr [rsp+340h+var_2E8+8], eax
0x14001bd97  and     [rsp+340h+var_2D8], rax
0x14001bd9c  mov     rcx, [r14+0C0h]; hToken
0x14001bda3  call    cs:__imp_ImpersonateLoggedOnUser
0x14001bda9  test    eax, eax
0x14001bdab  setnz   dil
0x14001bdaf  mov     [rsp+340h+var_2F8], dil
0x14001bdb4  mov     rax, [r14+10h]
0x14001bdb8  mov     rdx, [rax+0E8h]
0x14001bdbf  mov     rcx, cs:hKey
0x14001bdc6  test    rdx, rdx
0x14001bdc9  cmovnz  rcx, rdx; hKey
0x14001bdcd  and     [rsp+340h+var_300], rsi
0x14001bdd2  lea     rax, [rsp+340h+var_300]
0x14001bdd7  mov     [rsp+340h+phkResult], rax; lpReserved
0x14001bddc  mov     r9d, 20019h; samDesired
0x14001bde2  xor     r8d, r8d; ulOptions
0x14001bde5  mov     rdx, [r15]; lpSubKey
0x14001bde8  call    cs:__imp_RegOpenKeyExW
0x14001bdee  test    eax, eax
0x14001bdf0  jnz     short loc_14001BE00
0x14001bdf2  mov     rsi, [rsp+340h+var_300]
0x14001bdf7  mov     qword ptr [rsp+340h+var_2E8], rsi
0x14001bdfc  and     dword ptr [rsp+340h+var_2E8+8], eax
0x14001be00  mov     ecx, eax
0x14001be02  neg     ecx
0x14001be04  sbb     r9d, r9d
0x14001be07  and     r9d, eax
0x14001be0a  movzx   edx, r9w
0x14001be0e  or      edx, 80070000h
0x14001be14  test    r9d, r9d
0x14001be17  cmovle  edx, r9d; int
0x14001be1b  test    edx, edx
0x14001be1d  jns     short loc_14001BE40
0x14001be1f  cmp     dx, 2
0x14001be23  jz      loc_14001C323
0x14001be29  lfence
0x14001be2c  mov     r8, [r15]; unsigned __int16 *
0x14001be2f  lea     rcx, aErrorWhileAcce; "Error while accessing list of extension"...
0x14001be36  call    ?LogWarn@CLogger@@SAXPEBGJ0@Z; CLogger::LogWarn(ushort const *,long,ushort const *)
0x14001be3b  jmp     loc_14001C323
0x14001be40  xorps   xmm0, xmm0
0x14001be43  xor     eax, eax
0x14001be45  movups  [rbp+240h+var_2C0], xmm0
0x14001be49  mov     [rbp+240h+var_2B0], rax
0x14001be4d  xor     ebx, ebx
0x14001be4f  mov     qword ptr [rbp+240h+var_2C0], rbx
0x14001be53  and     dword ptr [rbp+240h+var_2C0+8], eax
0x14001be56  and     [rbp+240h+var_2B0], rax
0x14001be5a  cmp     [rbp+240h+arg_20], bl
0x14001be60  jnz     loc_14001BEE8
0x14001be66  mov     rax, [r14+10h]
0x14001be6a  mov     rdx, [rax+0E8h]
0x14001be71  mov     rcx, cs:hKey
0x14001be78  test    rdx, rdx
0x14001be7b  cmovnz  rcx, rdx; hKey
0x14001be7f  and     [rsp+340h+var_300], rbx
0x14001be84  lea     rax, [rsp+340h+var_300]
0x14001be89  mov     [rsp+340h+phkResult], rax; phkResult
0x14001be8e  mov     r9d, 20019h; samDesired
0x14001be94  xor     r8d, r8d; ulOptions
0x14001be97  mov     rdx, [r12]; lpSubKey
0x14001be9b  call    cs:__imp_RegOpenKeyExW
0x14001bea1  test    eax, eax
0x14001bea3  jnz     short loc_14001BEB1
0x14001bea5  mov     rbx, [rsp+340h+var_300]
0x14001beaa  mov     qword ptr [rbp+240h+var_2C0], rbx
0x14001beae  and     dword ptr [rbp+240h+var_2C0+8], eax
0x14001beb1  mov     ecx, eax
0x14001beb3  neg     ecx
0x14001beb5  sbb     r9d, r9d
0x14001beb8  and     r9d, eax
0x14001bebb  movzx   edx, r9w
0x14001bebf  or      edx, 80070000h
0x14001bec5  test    r9d, r9d
0x14001bec8  cmovle  edx, r9d; int
0x14001becc  test    edx, edx
0x14001bece  jns     short loc_14001BEE8
0x14001bed0  lfence
0x14001bed3  mov     r8, [r12]; unsigned __int16 *
0x14001bed7  lea     rcx, aErrorWhileAcce_0; "Error while accessing list of extension"...
0x14001bede  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x14001bee3  jmp     loc_14001C314
0x14001bee8  mov     [rbp+240h+cchValueName], 105h
0x14001beef  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14001bef4  mov     rcx, rax
0x14001bef7  test    rax, rax
0x14001befa  jz      loc_14001C35E
0x14001bf00  mov     rax, [rax]
0x14001bf03  call    qword ptr [rax+18h]
0x14001bf06  add     rax, 18h
0x14001bf0a  mov     [rsp+340h+var_300], rax
0x14001bf0f  xor     r12d, r12d
0x14001bf12  and     [rsp+340h+var_308], r12
0x14001bf17  and     [rsp+340h+var_310], r12
0x14001bf1c  lea     rax, [rbp+240h+Type]
0x14001bf20  mov     [rsp+340h+lpType], rax; lpType
0x14001bf25  and     [rsp+340h+phkResult], r12
0x14001bf2a  lea     r9, [rbp+240h+cchValueName]; lpcchValueName
0x14001bf2e  lea     r8, [rbp+240h+ValueName]; lpValueName
0x14001bf32  xor     edx, edx; dwIndex
0x14001bf34  mov     rcx, rsi; hKey
0x14001bf37  call    cs:__imp_RegEnumValueW
0x14001bf3d  or      r14d, 0FFFFFFFFh
0x14001bf41  cmp     eax, 103h
0x14001bf46  jz      loc_14001C2EF
0x14001bf4c  movzx   ebx, ax
0x14001bf4f  or      ebx, 80070000h
0x14001bf55  test    eax, eax
0x14001bf57  cmovle  ebx, eax
0x14001bf5a  test    ebx, ebx
0x14001bf5c  jns     loc_14001BFF0
0x14001bf62  lfence
0x14001bf65  lea     r8, SubBlock; "\\"
0x14001bf6c  mov     rdx, r15
0x14001bf6f  lea     rcx, [rbp+240h+var_2A0]
0x14001bf73  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x14001bf78  nop
0x14001bf79  lea     r8, [rbp+240h+ValueName]
0x14001bf7d  mov     rdx, rax
0x14001bf80  lea     rcx, [rbp+240h+var_2A8]
0x14001bf84  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x14001bf89  nop
0x14001bf8a  mov     r8, [rax]; unsigned __int16 *
0x14001bf8d  mov     edx, ebx; int
0x14001bf8f  lea     rcx, aErrorWhileEnum; "Error while enumerating extensions list"
0x14001bf96  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x14001bf9b  nop
0x14001bf9c  nop     dword ptr [rax+00h]
0x14001bfa0  mov     rdx, [rbp+240h+var_2A8]
0x14001bfa4  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001bfa8  mov     eax, r14d
0x14001bfab  lock xadd [rdx+10h], eax
0x14001bfb0  add     eax, r14d
0x14001bfb3  test    eax, eax
0x14001bfb5  jg      short loc_14001BFC4
0x14001bfb7  lfence
0x14001bfba  mov     rcx, [rdx]
0x14001bfbd  mov     rax, [rcx]
0x14001bfc0  call    qword ptr [rax+8]
0x14001bfc3  nop
0x14001bfc4  mov     rdx, [rbp+240h+var_2A0]
0x14001bfc8  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001bfcc  mov     eax, r14d
0x14001bfcf  lock xadd [rdx+10h], eax
0x14001bfd4  add     eax, r14d
0x14001bfd7  test    eax, eax
0x14001bfd9  jg      loc_14001C2A7
0x14001bfdf  lfence
0x14001bfe2  mov     rcx, [rdx]
0x14001bfe5  mov     rax, [rcx]
0x14001bfe8  call    qword ptr [rax+8]
0x14001bfeb  jmp     loc_14001C2A7
0x14001bff0  cmp     [rbp+240h+Type], 1
0x14001bff4  jz      short loc_14001C05D
0x14001bff6  lea     r8, SubBlock; "\\"
0x14001bffd  mov     rdx, r15
0x14001c000  lea     rcx, [rbp+240h+var_290]
0x14001c004  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x14001c009  nop
0x14001c00a  lea     r8, [rbp+240h+ValueName]
0x14001c00e  mov     rdx, rax
0x14001c011  lea     rcx, [rbp+240h+var_298]
0x14001c015  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x14001c01a  nop
0x14001c01b  mov     r8, [rax]; unsigned __int16 *
0x14001c01e  mov     edx, 8000FFFFh; int
0x14001c023  lea     rcx, aExpectedOnlySt; "Expected only strings in enabled extens"...
0x14001c02a  call    ?LogError@CLogger@@SAXPEBGJ0@Z; CLogger::LogError(ushort const *,long,ushort const *)
0x14001c02f  nop
0x14001c030  mov     rdx, [rbp+240h+var_298]
0x14001c034  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001c038  mov     eax, r14d
0x14001c03b  lock xadd [rdx+10h], eax
0x14001c040  add     eax, r14d
0x14001c043  test    eax, eax
0x14001c045  jg      short loc_14001C054
0x14001c047  lfence
0x14001c04a  mov     rcx, [rdx]
0x14001c04d  mov     rax, [rcx]
0x14001c050  call    qword ptr [rax+8]
0x14001c053  nop
0x14001c054  mov     rdx, [rbp+240h+var_290]
0x14001c058  jmp     loc_14001BFC8
0x14001c05d  xor     r15b, r15b
0x14001c060  cmp     [rbp+240h+arg_20], r15b
0x14001c067  jnz     loc_14001C1B0
0x14001c06d  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14001c072  mov     rcx, rax
0x14001c075  test    rax, rax
0x14001c078  jz      loc_14001C36D
0x14001c07e  mov     rax, [rax]
0x14001c081  call    qword ptr [rax+18h]
0x14001c084  lea     rbx, [rax+18h]
0x14001c088  mov     [rsp+340h+var_2D0], rbx
0x14001c08d  mov     edx, 104h
0x14001c092  mov     [rsp+340h+var_2F4], edx
0x14001c096  mov     ecx, 1
0x14001c09b  sub     ecx, [rbx-8]
0x14001c09e  mov     eax, [rbx-0Ch]
0x14001c0a1  sub     eax, edx
0x14001c0a3  or      eax, ecx
0x14001c0a5  jge     short loc_14001C0B6
0x14001c0a7  lea     rcx, [rsp+340h+var_2D0]
0x14001c0ac  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14001c0b1  mov     rbx, [rsp+340h+var_2D0]
0x14001c0b6  lea     r9, [rsp+340h+var_2F4]; unsigned int *
0x14001c0bb  mov     r8, rbx; unsigned __int16 *
0x14001c0be  lea     rdx, [rbp+240h+ValueName]; unsigned __int16 *
0x14001c0c2  lea     rcx, [rbp+240h+var_2C0]; this
0x14001c0c6  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14001c0cb  movzx   r14d, ax
0x14001c0cf  or      r14d, 80070000h
0x14001c0d6  test    eax, eax
0x14001c0d8  cmovle  r14d, eax
0x14001c0dc  test    r14d, r14d
0x14001c0df  jns     loc_14001C16E
0x14001c0e5  lfence
0x14001c0e8  lea     r8, SubBlock; "\\"
0x14001c0ef  mov     rdx, [rbp+240h+var_288]
0x14001c0f3  lea     rcx, [rbp+240h+var_278]
0x14001c0f7  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x14001c0fc  nop
0x14001c0fd  lea     r8, [rbp+240h+ValueName]
0x14001c101  mov     rdx, rax
0x14001c104  lea     rcx, [rbp+240h+var_280]
0x14001c108  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x14001c10d  nop
0x14001c10e  mov     r8, [rax]; unsigned __int16 *
0x14001c111  mov     edx, r14d; int
0x14001c114  lea     rcx, aCouldNotQueryT; "Could not query type for extension."
0x14001c11b  call    ?LogWarn@CLogger@@SAXPEBGJ0@Z; CLogger::LogWarn(ushort const *,long,ushort const *)
0x14001c120  nop
0x14001c121  mov     rdx, [rbp+240h+var_280]
0x14001c125  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001c129  or      r14d, 0FFFFFFFFh
0x14001c12d  mov     eax, r14d
0x14001c130  lock xadd [rdx+10h], eax
0x14001c135  add     eax, r14d
0x14001c138  test    eax, eax
0x14001c13a  jg      short loc_14001C149
0x14001c13c  lfence
0x14001c13f  mov     rcx, [rdx]
0x14001c142  mov     rax, [rcx]
0x14001c145  call    qword ptr [rax+8]
0x14001c148  nop
0x14001c149  mov     rdx, [rbp+240h+var_278]
0x14001c14d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001c151  mov     eax, r14d
0x14001c154  lock xadd [rdx+10h], eax
0x14001c159  add     eax, r14d
0x14001c15c  test    eax, eax
0x14001c15e  jg      short loc_14001C188
0x14001c160  lfence
0x14001c163  mov     rcx, [rdx]
0x14001c166  mov     rax, [rcx]
0x14001c169  call    qword ptr [rax+8]
0x14001c16c  jmp     short loc_14001C188
0x14001c16e  lea     rdx, aMicrosoftVisua_3; "Microsoft.VisualStudio.Sample"
0x14001c175  mov     rcx, rbx; String1
0x14001c178  call    cs:__imp__wcsicmp
0x14001c17e  test    eax, eax
0x14001c180  setz    r15b
0x14001c184  or      r14d, 0FFFFFFFFh
0x14001c188  lea     rdx, [rbx-18h]
0x14001c18c  mov     eax, r14d
0x14001c18f  lock xadd [rdx+10h], eax
0x14001c194  add     eax, r14d
0x14001c197  test    eax, eax
0x14001c199  jg      short loc_14001C1A7
0x14001c19b  lfence
0x14001c19e  mov     rcx, [rdx]
0x14001c1a1  mov     rax, [rcx]
0x14001c1a4  call    qword ptr [rax+8]
  ... truncated ...
```
