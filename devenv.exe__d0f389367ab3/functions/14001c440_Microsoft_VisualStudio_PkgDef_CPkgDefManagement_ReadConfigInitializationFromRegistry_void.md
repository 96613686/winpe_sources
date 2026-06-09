# Microsoft::VisualStudio::PkgDef::CPkgDefManagement::ReadConfigInitializationFromRegistry(void)

- ea: `0x14001c440`
- end: `0x14001c8f8`
- name: `?ReadConfigInitializationFromRegistry@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEAAJXZ`
- size: `1208`
- prototype: `__int64 __fastcall(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140016980`

## callees

- `0x140001020`
- `0x140002c10`
- `0x140003070`
- `0x140003160`
- `0x140004950`
- `0x140007740`
- `0x14001bd34`
- `0x14001c440`
- `0x14001c8f8`
- `0x140033ab0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14001c89f`
- `ADVAPI32!RegCloseKey` at `0x14001c89f`
- `ADVAPI32!RegOpenKeyExW` at `0x14001c4f8`
- `ADVAPI32!RegOpenKeyExW` at `0x14001c4f8`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14001c49e`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14001c49e`
- `ADVAPI32!RevertToSelf` at `0x14001c890`
- `ADVAPI32!RevertToSelf` at `0x14001c890`

## string_xrefs

- `0x14001c613`: `PkgDefSearchPath`
- `0x14001c669`: `ImageManifestSearchPath`
- `0x14001c713`: `ApplicationExtensionsFolder`
- `0x14001c572`: `RelativeRootFolderPath`
- `0x14001c7a6`: `LoadedUserExtensions`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::VisualStudio::PkgDef::CPkgDefManagement::ReadConfigInitializationFromRegistry(
        Microsoft::VisualStudio::PkgDef::CPkgDefManagement *this)
{
  HKEY v3; // rbx
  bool v4; // di
  _QWORD *v5; // r15
  __int64 v6; // rax
  HKEY v7; // rcx
  LSTATUS v8; // eax
  signed int RegistryValue; // esi
  struct ATL::IAtlStringMgr *Instance; // rax
  bool v11; // si
  HKEY v12; // rdx
  __int64 v13; // rbx
  HKEY v14; // rdx
  HKEY v15; // rdx
  HKEY v16; // rdx
  HKEY v17; // rdx
  HKEY v18; // rdx
  struct ATL::IAtlStringMgr *v19; // rax
  volatile signed __int32 *v20; // r15
  struct ATL::IAtlStringMgr *v21; // rax
  LPCWSTR v22; // rdx
  HKEY v23; // rdx
  HKEY phkResult; // [rsp+30h] [rbp-40h] BYREF
  bool v25; // [rsp+38h] [rbp-38h]
  __int128 v26; // [rsp+40h] [rbp-30h] BYREF
  __int64 v27; // [rsp+50h] [rbp-20h]
  volatile signed __int32 *v28; // [rsp+58h] [rbp-18h] BYREF
  __int64 v29; // [rsp+60h] [rbp-10h] BYREF

  if ( *((_BYTE *)this + 41) )
    return 0;
  v27 = 0;
  v3 = 0;
  v26 = 0u;
  v4 = ImpersonateLoggedOnUser(*((HANDLE *)this + 24));
  v25 = v4;
  v5 = (_QWORD *)ATL::CSimpleStringT<unsigned short,0>::CloneData(*(_QWORD *)(*((_QWORD *)this + 2) + 184LL) - 24LL);
  v6 = *((_QWORD *)this + 2);
  v7 = hKey;
  if ( *(_QWORD *)(v6 + 232) )
    v7 = *(HKEY *)(v6 + 232);
  phkResult = 0;
  v8 = RegOpenKeyExW(v7, (LPCWSTR)v5 + 12, 0, 0x2001Fu, &phkResult);
  if ( !v8 )
  {
    v3 = phkResult;
    *(_QWORD *)&v26 = phkResult;
    DWORD2(v26) = 0;
  }
  RegistryValue = (unsigned __int16)(v8 != 0 ? v8 : 0) | 0x80070000;
  if ( (v8 != 0 ? v8 : 0) <= 0 )
    RegistryValue = v8 != 0 ? v8 : 0;
  if ( _InterlockedDecrement((volatile signed __int32 *)v5 + 4) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v5 + 8LL))(*v5, v5);
  }
  if ( RegistryValue >= 0 )
  {
    Instance = ATL::CAtlStringMgr::GetInstance();
    if ( !Instance )
      ATL::AtlThrowImpl(-2147467259);
    v29 = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &phkResult,
      L"RelativeRootFolderPath");
    v11 = (int)GetRegistryValue(&v26, &phkResult, &v29) >= 0;
    v12 = phkResult - 6;
    if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v12 + 8LL))(*(_QWORD *)v12);
    }
    v13 = v29;
    if ( v11 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &phkResult,
        v29);
      ATL::CSimpleStringT<unsigned short,0>::operator=((char *)this + 96, &phkResult);
      v14 = phkResult - 6;
      if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 8LL))(*(_QWORD *)v14);
      }
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &phkResult,
      L"PkgDefSearchPath");
    RegistryValue = GetRegistryValue(&v26, &phkResult, (char *)this + 144);
    v15 = phkResult - 6;
    if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v15 + 8LL))(*(_QWORD *)v15);
    }
    if ( RegistryValue >= 0 )
    {
      _mm_lfence();
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &phkResult,
        L"ImageManifestSearchPath");
      RegistryValue = GetRegistryValue(&v26, &phkResult, (char *)this + 176);
      v16 = phkResult - 6;
      if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 8LL))(*(_QWORD *)v16);
      }
      if ( RegistryValue >= 0 )
      {
        _mm_lfence();
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &phkResult,
          L"UserFilesFolder");
        RegistryValue = GetRegistryValue(&v26, &phkResult, (char *)this + 136);
        v17 = phkResult - 6;
        if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v17 + 8LL))(*(_QWORD *)v17);
        }
        if ( RegistryValue >= 0 )
        {
          _mm_lfence();
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &phkResult,
            L"ApplicationExtensionsFolder");
          RegistryValue = GetRegistryValue(&v26, &phkResult, (char *)this + 160);
          v18 = phkResult - 6;
          if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v18 + 8LL))(*(_QWORD *)v18);
          }
          if ( RegistryValue >= 0 )
          {
            v19 = ATL::CAtlStringMgr::GetInstance();
            if ( !v19 )
              ATL::AtlThrowImpl(-2147467259);
            _mm_lfence();
            phkResult = (HKEY)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v19 + 24LL))(v19) + 24);
            v20 = (volatile signed __int32 *)ATL::CSimpleStringT<unsigned short,0>::CloneData(*(_QWORD *)(*((_QWORD *)this + 2) + 184LL) - 24LL);
            v28 = v20 + 6;
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
              &phkResult,
              L"%s\\%s",
              v20 + 6,
              L"LoadedUserExtensions");
            if ( _InterlockedDecrement(v20 + 4) <= 0 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v20 + 8LL))(*(_QWORD *)v20, v20);
            }
            v21 = ATL::CAtlStringMgr::GetInstance();
            if ( !v21 )
              ATL::AtlThrowImpl(-2147467259);
            _mm_lfence();
            v28 = (volatile signed __int32 *)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v21 + 24LL))(v21)
                                            + 24);
            Microsoft::VisualStudio::PkgDef::CPkgDefManagement::GetUserExtensionsList(
              (__int64)this,
              (LPCWSTR *)&phkResult,
              (LPCWSTR *)&v28,
              (__int64)this + 200,
              1);
            v22 = (LPCWSTR)(v28 - 6);
            if ( _InterlockedDecrement(v28 - 2) <= 0 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v22 + 8LL))(*(_QWORD *)v22);
            }
            *((_BYTE *)this + 41) = 1;
            v23 = phkResult - 6;
            if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v23 + 8LL))(*(_QWORD *)v23);
            }
          }
        }
      }
    }
    if ( _InterlockedDecrement((volatile signed __int32 *)(v13 - 24 + 16)) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v13 - 24) + 8LL))(*(_QWORD *)(v13 - 24));
    }
    v3 = (HKEY)v26;
  }
  if ( v4 )
    RevertToSelf();
  if ( v3 )
    RegCloseKey(v3);
  return (unsigned int)RegistryValue;
}

```

## disassembly

```asm
0x14001c440  mov     rax, rsp
0x14001c443  mov     [rax+8], rbx
0x14001c447  mov     [rax+10h], rsi
0x14001c44b  mov     [rax+18h], rdi
0x14001c44f  mov     [rax+20h], r13
0x14001c453  push    rbp
0x14001c454  push    r14
0x14001c456  push    r15
0x14001c458  mov     rbp, rsp
0x14001c45b  sub     rsp, 70h
0x14001c45f  mov     rax, cs:__security_cookie
0x14001c466  xor     rax, rsp
0x14001c469  mov     [rbp+var_8], rax
0x14001c46d  mov     r14, rcx
0x14001c470  cmp     byte ptr [rcx+29h], 0
0x14001c474  jz      short loc_14001C47D
0x14001c476  xor     eax, eax
0x14001c478  jmp     loc_14001C8A7
0x14001c47d  xorps   xmm0, xmm0
0x14001c480  xor     eax, eax
0x14001c482  movups  [rbp+var_30], xmm0
0x14001c486  mov     [rbp+var_20], rax
0x14001c48a  xor     ebx, ebx
0x14001c48c  mov     qword ptr [rbp+var_30], rbx
0x14001c490  and     dword ptr [rbp+var_30+8], eax
0x14001c493  and     [rbp+var_20], rax
0x14001c497  mov     rcx, [rcx+0C0h]; hToken
0x14001c49e  call    cs:__imp_ImpersonateLoggedOnUser
0x14001c4a4  test    eax, eax
0x14001c4a6  setnz   dil
0x14001c4aa  mov     [rbp+var_38], dil
0x14001c4ae  mov     rax, [r14+10h]
0x14001c4b2  mov     rcx, [rax+0B8h]
0x14001c4b9  sub     rcx, 18h
0x14001c4bd  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001c4c2  mov     r15, rax
0x14001c4c5  lea     rdx, [rax+18h]; lpSubKey
0x14001c4c9  mov     rax, [r14+10h]
0x14001c4cd  mov     r8, [rax+0E8h]
0x14001c4d4  mov     rcx, cs:hKey
0x14001c4db  test    r8, r8
0x14001c4de  cmovnz  rcx, r8; hKey
0x14001c4e2  and     [rbp+var_40], rbx
0x14001c4e6  lea     rax, [rbp+var_40]
0x14001c4ea  mov     [rsp+70h+phkResult], rax; phkResult
0x14001c4ef  mov     r9d, 2001Fh; samDesired
0x14001c4f5  xor     r8d, r8d; ulOptions
0x14001c4f8  call    cs:__imp_RegOpenKeyExW
0x14001c4fe  test    eax, eax
0x14001c500  jnz     short loc_14001C50D
0x14001c502  mov     rbx, [rbp+var_40]
0x14001c506  mov     qword ptr [rbp+var_30], rbx
0x14001c50a  and     dword ptr [rbp+var_30+8], eax
0x14001c50d  mov     ecx, eax
0x14001c50f  neg     ecx
0x14001c511  sbb     r8d, r8d
0x14001c514  and     r8d, eax
0x14001c517  movzx   esi, r8w
0x14001c51b  or      esi, 80070000h
0x14001c521  test    r8d, r8d
0x14001c524  cmovle  esi, r8d
0x14001c528  or      r13d, 0FFFFFFFFh
0x14001c52c  mov     eax, r13d
0x14001c52f  lock xadd [r15+10h], eax
0x14001c535  add     eax, r13d
0x14001c538  test    eax, eax
0x14001c53a  jg      short loc_14001C54B
0x14001c53c  lfence
0x14001c53f  mov     rcx, [r15]
0x14001c542  mov     rax, [rcx]
0x14001c545  mov     rdx, r15
0x14001c548  call    qword ptr [rax+8]
0x14001c54b  test    esi, esi
0x14001c54d  js      loc_14001C88B
0x14001c553  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14001c558  mov     rcx, rax
0x14001c55b  test    rax, rax
0x14001c55e  jz      loc_14001C8DF
0x14001c564  mov     rax, [rax]
0x14001c567  call    qword ptr [rax+18h]
0x14001c56a  add     rax, 18h
0x14001c56e  mov     [rbp+var_10], rax
0x14001c572  lea     rdx, aRelativerootfo; "RelativeRootFolderPath"
0x14001c579  lea     rcx, [rbp+var_40]
0x14001c57d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001c582  nop
0x14001c583  lea     r8, [rbp+var_10]
0x14001c587  lea     rdx, [rbp+var_40]
0x14001c58b  lea     rcx, [rbp+var_30]
0x14001c58f  call    ?GetRegistryValue@@YAJAEBVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAV32@@Z; GetRegistryValue(ATL::CRegKey const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x14001c594  mov     esi, eax
0x14001c596  shr     esi, 1Fh
0x14001c599  xor     sil, 1
0x14001c59d  mov     rdx, [rbp+var_40]
0x14001c5a1  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001c5a5  mov     ecx, r13d
0x14001c5a8  lock xadd [rdx+10h], ecx
0x14001c5ad  add     ecx, r13d
0x14001c5b0  test    ecx, ecx
0x14001c5b2  jg      short loc_14001C5C0
0x14001c5b4  lfence
0x14001c5b7  mov     rcx, [rdx]
0x14001c5ba  mov     rax, [rcx]
0x14001c5bd  call    qword ptr [rax+8]
0x14001c5c0  mov     rbx, [rbp+var_10]
0x14001c5c4  test    sil, sil
0x14001c5c7  jz      short loc_14001C613
0x14001c5c9  mov     rdx, rbx
0x14001c5cc  lea     rcx, [rbp+var_40]
0x14001c5d0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001c5d5  nop
0x14001c5d6  lea     rcx, [r14+60h]
0x14001c5da  lea     rdx, [rbp+var_40]
0x14001c5de  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x14001c5e3  nop
0x14001c5e4  nop     dword ptr [rax+00h]
0x14001c5e8  nop     dword ptr [rax+rax+00000000h]
0x14001c5f0  mov     rdx, [rbp+var_40]
0x14001c5f4  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001c5f8  mov     eax, r13d
0x14001c5fb  lock xadd [rdx+10h], eax
0x14001c600  add     eax, r13d
0x14001c603  test    eax, eax
0x14001c605  jg      short loc_14001C613
0x14001c607  lfence
0x14001c60a  mov     rcx, [rdx]
0x14001c60d  mov     rax, [rcx]
0x14001c610  call    qword ptr [rax+8]
0x14001c613  lea     rdx, aPkgdefsearchpa; "PkgDefSearchPath"
0x14001c61a  lea     rcx, [rbp+var_40]
0x14001c61e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001c623  nop
0x14001c624  lea     r8, [r14+90h]
0x14001c62b  lea     rdx, [rbp+var_40]
0x14001c62f  lea     rcx, [rbp+var_30]
0x14001c633  call    ?GetRegistryValue@@YAJAEBVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAV32@@Z; GetRegistryValue(ATL::CRegKey const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x14001c638  mov     esi, eax
0x14001c63a  mov     rdx, [rbp+var_40]
0x14001c63e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001c642  mov     ecx, r13d
0x14001c645  lock xadd [rdx+10h], ecx
0x14001c64a  add     ecx, r13d
0x14001c64d  test    ecx, ecx
0x14001c64f  jg      short loc_14001C65E
0x14001c651  lfence
0x14001c654  mov     rcx, [rdx]
0x14001c657  mov     r8, [rcx]
0x14001c65a  call    qword ptr [r8+8]
0x14001c65e  test    esi, esi
0x14001c660  js      loc_14001C868
0x14001c666  lfence
0x14001c669  lea     rdx, aImagemanifests; "ImageManifestSearchPath"
0x14001c670  lea     rcx, [rbp+var_40]
0x14001c674  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001c679  nop
0x14001c67a  lea     r8, [r14+0B0h]
0x14001c681  lea     rdx, [rbp+var_40]
0x14001c685  lea     rcx, [rbp+var_30]
0x14001c689  call    ?GetRegistryValue@@YAJAEBVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAV32@@Z; GetRegistryValue(ATL::CRegKey const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x14001c68e  mov     esi, eax
0x14001c690  mov     rdx, [rbp+var_40]
0x14001c694  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001c698  mov     eax, r13d
0x14001c69b  lock xadd [rdx+10h], eax
0x14001c6a0  add     eax, r13d
0x14001c6a3  test    eax, eax
0x14001c6a5  jg      short loc_14001C6B3
0x14001c6a7  lfence
0x14001c6aa  mov     rcx, [rdx]
0x14001c6ad  mov     rax, [rcx]
0x14001c6b0  call    qword ptr [rax+8]
0x14001c6b3  test    esi, esi
0x14001c6b5  js      loc_14001C868
0x14001c6bb  lfence
0x14001c6be  lea     rdx, aUserfilesfolde; "UserFilesFolder"
0x14001c6c5  lea     rcx, [rbp+var_40]
0x14001c6c9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001c6ce  nop
0x14001c6cf  lea     r8, [r14+88h]
0x14001c6d6  lea     rdx, [rbp+var_40]
0x14001c6da  lea     rcx, [rbp+var_30]
0x14001c6de  call    ?GetRegistryValue@@YAJAEBVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAV32@@Z; GetRegistryValue(ATL::CRegKey const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x14001c6e3  mov     esi, eax
0x14001c6e5  mov     rdx, [rbp+var_40]
0x14001c6e9  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001c6ed  mov     eax, r13d
0x14001c6f0  lock xadd [rdx+10h], eax
0x14001c6f5  add     eax, r13d
0x14001c6f8  test    eax, eax
0x14001c6fa  jg      short loc_14001C708
0x14001c6fc  lfence
0x14001c6ff  mov     rcx, [rdx]
0x14001c702  mov     rax, [rcx]
0x14001c705  call    qword ptr [rax+8]
0x14001c708  test    esi, esi
0x14001c70a  js      loc_14001C868
0x14001c710  lfence
0x14001c713  lea     rdx, aApplicationext; "ApplicationExtensionsFolder"
0x14001c71a  lea     rcx, [rbp+var_40]
0x14001c71e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001c723  nop
0x14001c724  lea     r8, [r14+0A0h]
0x14001c72b  lea     rdx, [rbp+var_40]
0x14001c72f  lea     rcx, [rbp+var_30]
0x14001c733  call    ?GetRegistryValue@@YAJAEBVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@AEAV32@@Z; GetRegistryValue(ATL::CRegKey const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x14001c738  mov     esi, eax
0x14001c73a  mov     rdx, [rbp+var_40]
0x14001c73e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001c742  mov     eax, r13d
0x14001c745  lock xadd [rdx+10h], eax
0x14001c74a  add     eax, r13d
0x14001c74d  test    eax, eax
0x14001c74f  jg      short loc_14001C75D
0x14001c751  lfence
0x14001c754  mov     rcx, [rdx]
0x14001c757  mov     rax, [rcx]
0x14001c75a  call    qword ptr [rax+8]
0x14001c75d  test    esi, esi
0x14001c75f  js      loc_14001C868
0x14001c765  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14001c76a  mov     rcx, rax
0x14001c76d  test    rax, rax
0x14001c770  jz      loc_14001C8ED
0x14001c776  lfence
0x14001c779  mov     rax, [rax]
0x14001c77c  call    qword ptr [rax+18h]
0x14001c77f  add     rax, 18h
0x14001c783  mov     [rbp+var_40], rax
0x14001c787  mov     rax, [r14+10h]
0x14001c78b  mov     rcx, [rax+0B8h]
0x14001c792  sub     rcx, 18h
0x14001c796  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001c79b  mov     r15, rax
0x14001c79e  lea     r8, [rax+18h]
0x14001c7a2  mov     [rbp+var_18], r8
0x14001c7a6  lea     r9, aLoadeduserexte; "LoadedUserExtensions"
0x14001c7ad  lea     rdx, aSS_2; "%s\\%s"
0x14001c7b4  lea     rcx, [rbp+var_40]
0x14001c7b8  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x14001c7bd  nop
0x14001c7be  mov     eax, r13d
0x14001c7c1  lock xadd [r15+10h], eax
0x14001c7c7  add     eax, r13d
0x14001c7ca  test    eax, eax
0x14001c7cc  jg      short loc_14001C7DD
0x14001c7ce  lfence
0x14001c7d1  mov     rcx, [r15]
0x14001c7d4  mov     rax, [rcx]
0x14001c7d7  mov     rdx, r15
0x14001c7da  call    qword ptr [rax+8]
0x14001c7dd  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14001c7e2  mov     rcx, rax
0x14001c7e5  test    rax, rax
0x14001c7e8  jz      loc_14001C8D1
0x14001c7ee  lfence
0x14001c7f1  mov     rax, [rax]
0x14001c7f4  call    qword ptr [rax+18h]
0x14001c7f7  add     rax, 18h
0x14001c7fb  mov     [rbp+var_18], rax
0x14001c7ff  lea     r9, [r14+0C8h]
0x14001c806  mov     byte ptr [rsp+70h+phkResult], 1
0x14001c80b  lea     r8, [rbp+var_18]
0x14001c80f  lea     rdx, [rbp+var_40]
0x14001c813  mov     rcx, r14
0x14001c816  call    ?GetUserExtensionsList@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEBAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0AEAV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@6@_N@Z; Microsoft::VisualStudio::PkgDef::CPkgDefManagement::GetUserExtensionsList(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &,bool)
0x14001c81b  nop
0x14001c81c  mov     rdx, [rbp+var_18]
0x14001c820  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001c824  mov     eax, r13d
0x14001c827  lock xadd [rdx+10h], eax
0x14001c82c  add     eax, r13d
0x14001c82f  test    eax, eax
0x14001c831  jg      short loc_14001C83F
0x14001c833  lfence
0x14001c836  mov     rcx, [rdx]
0x14001c839  mov     rax, [rcx]
0x14001c83c  call    qword ptr [rax+8]
0x14001c83f  mov     byte ptr [r14+29h], 1
0x14001c844  mov     rdx, [rbp+var_40]
0x14001c848  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001c84c  mov     eax, r13d
0x14001c84f  lock xadd [rdx+10h], eax
0x14001c854  add     eax, r13d
0x14001c857  test    eax, eax
0x14001c859  jg      short loc_14001C868
0x14001c85b  lfence
0x14001c85e  mov     rcx, [rdx]
0x14001c861  mov     rax, [rcx]
0x14001c864  call    qword ptr [rax+8]
0x14001c867  nop
0x14001c868  lea     rdx, [rbx-18h]
0x14001c86c  mov     eax, r13d
0x14001c86f  lock xadd [rdx+10h], eax
0x14001c874  add     eax, r13d
0x14001c877  test    eax, eax
0x14001c879  jg      short loc_14001C887
0x14001c87b  lfence
0x14001c87e  mov     rcx, [rdx]
0x14001c881  mov     rax, [rcx]
0x14001c884  call    qword ptr [rax+8]
  ... truncated ...
```
