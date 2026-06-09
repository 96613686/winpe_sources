# Microsoft::VisualStudio::PkgDef::CPkgDefManagement::SaveConfigInitializationToRegistry(CPkgDefCache const &,bool)

- ea: `0x14001b484`
- end: `0x14001bb25`
- name: `?SaveConfigInitializationToRegistry@CPkgDefManagement@PkgDef@VisualStudio@Microsoft@@AEBAJAEBVCPkgDefCache@@_N@Z`
- size: `1697`
- prototype: `__int64 __fastcall(Microsoft::VisualStudio::PkgDef::CPkgDefManagement *__hidden this, const struct CPkgDefCache *, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140017580`
- `0x14001b3f0`

## callees

- `0x140002c10`
- `0x140003070`
- `0x140003160`
- `0x140007740`
- `0x14000bfa8`
- `0x14001b484`
- `0x14001bb30`
- `0x140033ab0`
- `0x140034b7c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14001b647`
- `ADVAPI32!RegCloseKey` at `0x14001bad9`
- `ADVAPI32!RegCloseKey` at `0x14001baf3`
- `ADVAPI32!RegCloseKey` at `0x14001b647`
- `ADVAPI32!RegCloseKey` at `0x14001bad9`
- `ADVAPI32!RegCloseKey` at `0x14001baf3`
- `ADVAPI32!RegCreateKeyExW` at `0x14001b632`
- `ADVAPI32!RegCreateKeyExW` at `0x14001b632`
- `ADVAPI32!RegOpenKeyExW` at `0x14001b551`
- `ADVAPI32!RegOpenKeyExW` at `0x14001b551`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14001b4f3`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x14001b4f3`
- `ADVAPI32!RevertToSelf` at `0x14001bae4`
- `ADVAPI32!RevertToSelf` at `0x14001bae4`

## string_xrefs

- `0x14001b6ee`: `PkgDefSearchPath`
- `0x14001b742`: `ImageManifestSearchPath`
- `0x14001b7ea`: `ApplicationExtensionsFolder`
- `0x14001b69c`: `RelativeRootFolderPath`
- `0x14001ba22`: `LoadedUserExtensions`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Microsoft::VisualStudio::PkgDef::CPkgDefManagement::SaveConfigInitializationToRegistry(
        Microsoft::VisualStudio::PkgDef::CPkgDefManagement *this,
        const struct CPkgDefCache *a2,
        char a3)
{
  char *v5; // rdi
  HKEY v6; // r14
  bool v7; // bl
  volatile signed __int32 *v8; // r15
  WCHAR *v9; // r10
  HKEY v10; // rcx
  LSTATUS v11; // eax
  char *v12; // r12
  char *v13; // r13
  signed int v14; // r15d
  volatile signed __int32 *v15; // rcx
  WCHAR *v16; // r15
  HKEY v17; // rcx
  HKEY v18; // rdi
  const struct CPkgDefCache *v19; // r13
  DWORD v20; // eax
  LSTATUS v21; // eax
  signed int v22; // edi
  HKEY v23; // rdx
  HKEY v24; // rdx
  HKEY v25; // rdx
  HKEY v26; // rdx
  HKEY v27; // rdx
  HKEY v28; // rdx
  const char *v29; // rdx
  HKEY v30; // rdx
  HKEY v31; // rdx
  volatile signed __int32 *v32; // r15
  volatile signed __int32 *v33; // r12
  HKEY v34; // rdx
  unsigned int v35; // eax
  unsigned __int16 *v36; // r9
  int v37; // eax
  _QWORD *v38; // rsi
  int v39; // r15d
  struct ATL::IAtlStringMgr *Instance; // rax
  HKEY v41; // rax
  _QWORD *v42; // r8
  struct _SECURITY_ATTRIBUTES *lpSecurityAttributes; // [rsp+30h] [rbp-39h]
  HKEY v45; // [rsp+50h] [rbp-19h] BYREF
  volatile signed __int32 *v46; // [rsp+58h] [rbp-11h]
  __int128 v47; // [rsp+60h] [rbp-9h] BYREF
  __int64 v48; // [rsp+70h] [rbp+7h]
  HKEY hKey[2]; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v50; // [rsp+88h] [rbp+1Fh]
  HKEY phkResult; // [rsp+E8h] [rbp+7Fh] BYREF

  if ( (*((_DWORD *)this + 15) & 4) != 0 )
    return 0;
  v5 = (char *)this + 16;
  if ( !a3 && !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 80LL))(*(_QWORD *)v5) )
    return 0;
  v6 = 0;
  v47 = 0u;
  v48 = 0;
  v7 = ImpersonateLoggedOnUser(*((HANDLE *)this + 24));
  v8 = (volatile signed __int32 *)((char *)a2 + 184);
  v46 = v8;
  v9 = (WCHAR *)(ATL::CSimpleStringT<unsigned short,0>::CloneData(*(_QWORD *)v8 - 24LL) + 24);
  v45 = (HKEY)v9;
  v10 = ::hKey;
  if ( *(_QWORD *)(*(_QWORD *)v5 + 232LL) )
    v10 = *(HKEY *)(*(_QWORD *)v5 + 232LL);
  phkResult = 0;
  v11 = RegOpenKeyExW(v10, v9, 0, 0x20006u, &phkResult);
  v12 = (char *)v8;
  v13 = v5;
  if ( !v11 )
  {
    v6 = phkResult;
    *(_QWORD *)&v47 = phkResult;
    DWORD2(v47) = 0;
    v12 = (char *)a2 + 184;
    v13 = (char *)this + 16;
  }
  v14 = (unsigned __int16)v11 | 0x80070000;
  if ( v11 <= 0 )
    v14 = v11;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v45 - 2, 0xFFFFFFFF) > 1 )
  {
    v15 = v46;
  }
  else
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v45 - 3) + 8LL))(*((_QWORD *)v45 - 3));
    v15 = (volatile signed __int32 *)v12;
    v5 = v13;
  }
  if ( v14 >= 0 )
  {
    v19 = a2;
  }
  else
  {
    v16 = (WCHAR *)(ATL::CSimpleStringT<unsigned short,0>::CloneData(*(_QWORD *)v15 - 24LL) + 24);
    phkResult = (HKEY)v16;
    v17 = *(HKEY *)(*(_QWORD *)v5 + 232LL);
    v18 = ::hKey;
    if ( v17 )
      v18 = v17;
    v19 = a2;
    v20 = (*(__int64 (__fastcall **)(const struct CPkgDefCache *))(*(_QWORD *)a2 + 32LL))(a2);
    v45 = 0;
    v21 = RegCreateKeyExW(v18, v16, 0, 0, v20, 0x2001Fu, 0, &v45, (LPDWORD)&phkResult);
    if ( !v21 )
    {
      v21 = 0;
      if ( v6 )
        v21 = RegCloseKey(v6);
      v6 = v45;
      *(_QWORD *)&v47 = v45;
      DWORD2(v47) = 0;
    }
    v22 = (unsigned __int16)v21 | 0x80070000;
    if ( v21 <= 0 )
      v22 = v21;
    if ( _InterlockedDecrement((volatile signed __int32 *)v16 - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v16 - 3) + 8LL))(*((_QWORD *)v16 - 3));
    }
    if ( v22 < 0 )
      goto LABEL_71;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &phkResult,
    L"RelativeRootFolderPath");
  v22 = SetRegistryValue(&v47, &phkResult, (char *)this + 96);
  v23 = phkResult - 6;
  if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v23 + 8LL))(*(_QWORD *)v23);
  }
  if ( v22 >= 0 )
  {
    _mm_lfence();
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &phkResult,
      L"PkgDefSearchPath");
    v22 = SetRegistryValue(&v47, &phkResult, (char *)this + 144);
    v24 = phkResult - 6;
    if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v24 + 8LL))(*(_QWORD *)v24);
    }
    if ( v22 >= 0 )
    {
      _mm_lfence();
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &phkResult,
        L"ImageManifestSearchPath");
      v22 = SetRegistryValue(&v47, &phkResult, (char *)this + 176);
      v25 = phkResult - 6;
      if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
      {
        _mm_lfence();
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v25 + 8LL))(*(_QWORD *)v25);
      }
      if ( v22 >= 0 )
      {
        _mm_lfence();
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &phkResult,
          L"UserFilesFolder");
        v22 = SetRegistryValue(&v47, &phkResult, (char *)this + 136);
        v26 = phkResult - 6;
        if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v26 + 8LL))(*(_QWORD *)v26);
        }
        if ( v22 >= 0 )
        {
          _mm_lfence();
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &phkResult,
            L"ApplicationExtensionsFolder");
          v22 = SetRegistryValue(&v47, &phkResult, (char *)this + 160);
          v27 = phkResult - 6;
          if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v27 + 8LL))(*(_QWORD *)v27);
          }
          if ( v22 >= 0 )
          {
            _mm_lfence();
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &phkResult,
              L"PkgDefExclusionDirectories");
            v22 = SetRegistryValue(&v47, &phkResult, (char *)this + 152);
            v28 = phkResult - 6;
            if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v28 + 8LL))(*(_QWORD *)v28);
            }
            if ( v22 >= 0 )
            {
              _mm_lfence();
              v29 = "false";
              if ( *((_BYTE *)this + 43) )
                v29 = "true";
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                &v45,
                v29);
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                &phkResult,
                L"IsClientMode");
              v22 = SetRegistryValue(&v47, &phkResult, &v45);
              v30 = phkResult - 6;
              if ( _InterlockedDecrement((volatile signed __int32 *)phkResult - 2) <= 0 )
              {
                _mm_lfence();
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v30 + 8LL))(*(_QWORD *)v30);
              }
              v31 = v45 - 6;
              if ( _InterlockedDecrement((volatile signed __int32 *)v45 - 2) <= 0 )
              {
                _mm_lfence();
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v31 + 8LL))(*(_QWORD *)v31);
              }
              if ( v22 >= 0 )
              {
                _mm_lfence();
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                  &phkResult,
                  L"ClientAppDataFolder");
                v32 = (volatile signed __int32 *)ATL::CSimpleStringT<unsigned short,0>::CloneData(*(_QWORD *)(*((_QWORD *)this + 2) + 128LL) - 24LL);
                v46 = v32 + 6;
                v33 = (volatile signed __int32 *)ATL::CSimpleStringT<unsigned short,0>::CloneData(v32);
                v45 = (HKEY)(v33 + 6);
                v22 = SetRegistryValue(&v47, &phkResult, &v45);
                if ( _InterlockedExchangeAdd(v33 + 4, 0xFFFFFFFF) <= 1 )
                {
                  _mm_lfence();
                  (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v33 + 8LL))(
                    *(_QWORD *)v33,
                    v33);
                }
                if ( _InterlockedExchangeAdd(v32 + 4, 0xFFFFFFFF) <= 1 )
                {
                  _mm_lfence();
                  (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v32 + 8LL))(
                    *(_QWORD *)v32,
                    v32);
                }
                v34 = phkResult - 6;
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)phkResult - 2, 0xFFFFFFFF) <= 1 )
                {
                  _mm_lfence();
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v34 + 8LL))(*(_QWORD *)v34);
                }
                if ( v22 >= 0 && *((_QWORD *)this + 27) )
                {
                  hKey[0] = 0;
                  hKey[1] = 0;
                  v50 = 0;
                  v35 = (*(__int64 (__fastcall **)(const struct CPkgDefCache *))(*(_QWORD *)v19 + 32LL))(v19);
                  v37 = ATL::CRegKey::Create(
                          (ATL::CRegKey *)hKey,
                          v6,
                          L"LoadedUserExtensions",
                          v36,
                          v35,
                          0x2001Fu,
                          lpSecurityAttributes,
                          0);
                  v22 = (unsigned __int16)v37 | 0x80070000;
                  if ( v37 <= 0 )
                    v22 = v37;
                  if ( v22 >= 0 )
                  {
                    _mm_lfence();
                    v38 = (_QWORD *)*((_QWORD *)this + 25);
                    v39 = 0;
                    Instance = ATL::CAtlStringMgr::GetInstance();
                    if ( !Instance )
                      ATL::AtlThrowImpl(-2147467259);
                    v41 = (HKEY)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                               + 24);
                    phkResult = v41;
                    if ( v38 )
                    {
                      do
                      {
                        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
                          &phkResult,
                          L"ext%.3d",
                          (unsigned int)++v39);
                        v42 = v38;
                        v38 = (_QWORD *)*v38;
                        SetRegistryValue(hKey, &phkResult, v42 + 2);
                      }
                      while ( v38 );
                      v41 = phkResult;
                    }
                    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v41 - 2, 0xFFFFFFFF) <= 1 )
                    {
                      _mm_lfence();
                      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v41 - 3) + 8LL))(*((_QWORD *)v41 - 3));
                    }
                  }
                  if ( hKey[0] )
                    RegCloseKey(hKey[0]);
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_71:
  if ( v7 )
    RevertToSelf();
  if ( v6 )
    RegCloseKey(v6);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x14001b484  mov     [rsp-8+arg_10], rbx
0x14001b489  mov     [rsp-8+arg_8], rdx
0x14001b48e  push    rbp
0x14001b48f  push    rsi
0x14001b490  push    rdi
0x14001b491  push    r12
0x14001b493  push    r13
0x14001b495  push    r14
0x14001b497  push    r15
0x14001b499  lea     rbp, [rsp-27h]
0x14001b49e  sub     rsp, 90h
0x14001b4a5  mov     r15, rdx
0x14001b4a8  mov     rsi, rcx
0x14001b4ab  xor     r12d, r12d
0x14001b4ae  mov     eax, [rcx+3Ch]
0x14001b4b1  shr     eax, 2
0x14001b4b4  test    al, 1
0x14001b4b6  jnz     loc_14001BAFD
0x14001b4bc  lea     rdi, [rcx+10h]
0x14001b4c0  test    r8b, r8b
0x14001b4c3  jnz     short loc_14001B4D6
0x14001b4c5  mov     rcx, [rdi]
0x14001b4c8  mov     rax, [rcx]
0x14001b4cb  call    qword ptr [rax+50h]
0x14001b4ce  test    al, al
0x14001b4d0  jz      loc_14001BAFD
0x14001b4d6  xorps   xmm0, xmm0
0x14001b4d9  movups  [rbp+57h+var_60], xmm0
0x14001b4dd  mov     r14, r12
0x14001b4e0  mov     qword ptr [rbp+57h+var_60], r12
0x14001b4e4  mov     dword ptr [rbp+57h+var_60+8], r12d
0x14001b4e8  mov     [rbp+57h+var_50], r12
0x14001b4ec  mov     rcx, [rsi+0C0h]; hToken
0x14001b4f3  call    cs:__imp_ImpersonateLoggedOnUser
0x14001b4f9  test    eax, eax
0x14001b4fb  setnz   bl
0x14001b4fe  mov     [rbp+57h+arg_0], bl
0x14001b501  add     r15, 0B8h
0x14001b508  mov     [rbp+57h+var_68], r15
0x14001b50c  mov     rcx, [r15]
0x14001b50f  sub     rcx, 18h
0x14001b513  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001b518  lea     r10, [rax+18h]
0x14001b51c  mov     [rbp+57h+var_70], r10
0x14001b520  mov     rax, [rdi]
0x14001b523  mov     rdx, [rax+0E8h]
0x14001b52a  mov     rcx, cs:hKey
0x14001b531  test    rdx, rdx
0x14001b534  cmovnz  rcx, rdx; hKey
0x14001b538  mov     [rbp+57h+arg_18], r12
0x14001b53c  lea     rax, [rbp+57h+arg_18]
0x14001b540  mov     [rsp+0C0h+phkResult], rax; phkResult
0x14001b545  mov     r9d, 20006h; samDesired
0x14001b54b  xor     r8d, r8d; ulOptions
0x14001b54e  mov     rdx, r10; lpSubKey
0x14001b551  call    cs:__imp_RegOpenKeyExW
0x14001b557  mov     r12, r15
0x14001b55a  mov     r13, rdi
0x14001b55d  test    eax, eax
0x14001b55f  jnz     short loc_14001B57B
0x14001b561  mov     r14, [rbp+57h+arg_18]
0x14001b565  mov     qword ptr [rbp+57h+var_60], r14
0x14001b569  and     dword ptr [rbp+57h+var_60+8], eax
0x14001b56c  mov     r12, [rbp+57h+arg_8]
0x14001b570  add     r12, 0B8h
0x14001b577  lea     r13, [rsi+10h]
0x14001b57b  movzx   r15d, ax
0x14001b57f  or      r15d, 80070000h
0x14001b586  test    eax, eax
0x14001b588  cmovle  r15d, eax
0x14001b58c  mov     rdx, [rbp+57h+var_70]
0x14001b590  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001b594  or      eax, 0FFFFFFFFh
0x14001b597  lock xadd [rdx+10h], eax
0x14001b59c  sub     eax, 1
0x14001b59f  jg      short loc_14001B5B5
0x14001b5a1  lfence
0x14001b5a4  mov     rcx, [rdx]
0x14001b5a7  mov     rax, [rcx]
0x14001b5aa  call    qword ptr [rax+8]
0x14001b5ad  mov     rcx, r12
0x14001b5b0  mov     rdi, r13
0x14001b5b3  jmp     short loc_14001B5B9
0x14001b5b5  mov     rcx, [rbp+57h+var_68]
0x14001b5b9  xor     r12d, r12d
0x14001b5bc  test    r15d, r15d
0x14001b5bf  jns     loc_14001B694
0x14001b5c5  mov     rcx, [rcx]
0x14001b5c8  sub     rcx, 18h
0x14001b5cc  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14001b5d1  lea     r15, [rax+18h]
0x14001b5d5  mov     [rbp+57h+arg_18], r15
0x14001b5d9  mov     rax, [rdi]
0x14001b5dc  mov     rcx, [rax+0E8h]
0x14001b5e3  mov     rdi, cs:hKey
0x14001b5ea  test    rcx, rcx
0x14001b5ed  cmovnz  rdi, rcx
0x14001b5f1  mov     r13, [rbp+57h+arg_8]
0x14001b5f5  mov     rax, [r13+0]
0x14001b5f9  mov     rcx, r13
0x14001b5fc  call    qword ptr [rax+20h]
0x14001b5ff  mov     [rbp+57h+var_70], r12
0x14001b603  lea     rcx, [rbp+57h+arg_18]
0x14001b607  mov     [rsp+0C0h+lpdwDisposition], rcx; lpdwDisposition
0x14001b60c  lea     rcx, [rbp+57h+var_70]
0x14001b610  mov     [rsp+0C0h+var_88], rcx; phkResult
0x14001b615  mov     [rsp+0C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x14001b61a  mov     [rsp+0C0h+samDesired], 2001Fh; samDesired
0x14001b622  mov     dword ptr [rsp+0C0h+phkResult], eax; dwOptions
0x14001b626  xor     r9d, r9d; lpClass
0x14001b629  xor     r8d, r8d; Reserved
0x14001b62c  mov     rdx, r15; lpSubKey
0x14001b62f  mov     rcx, rdi; hKey
0x14001b632  call    cs:__imp_RegCreateKeyExW
0x14001b638  test    eax, eax
0x14001b63a  jnz     short loc_14001B659
0x14001b63c  mov     eax, r12d
0x14001b63f  test    r14, r14
0x14001b642  jz      short loc_14001B64D
0x14001b644  mov     rcx, r14; hKey
0x14001b647  call    cs:__imp_RegCloseKey
0x14001b64d  mov     r14, [rbp+57h+var_70]
0x14001b651  mov     qword ptr [rbp+57h+var_60], r14
0x14001b655  mov     dword ptr [rbp+57h+var_60+8], r12d
0x14001b659  movzx   edi, ax
0x14001b65c  or      edi, 80070000h
0x14001b662  test    eax, eax
0x14001b664  cmovle  edi, eax
0x14001b667  lea     rdx, [r15-18h]
0x14001b66b  or      r15d, 0FFFFFFFFh
0x14001b66f  mov     eax, r15d
0x14001b672  lock xadd [rdx+10h], eax
0x14001b677  add     eax, r15d
0x14001b67a  test    eax, eax
0x14001b67c  jg      short loc_14001B68A
0x14001b67e  lfence
0x14001b681  mov     rcx, [rdx]
0x14001b684  mov     rax, [rcx]
0x14001b687  call    qword ptr [rax+8]
0x14001b68a  test    edi, edi
0x14001b68c  js      loc_14001BAE0
0x14001b692  jmp     short loc_14001B69C
0x14001b694  mov     r13, [rbp+57h+arg_8]
0x14001b698  or      r15d, 0FFFFFFFFh
0x14001b69c  lea     rdx, aRelativerootfo; "RelativeRootFolderPath"
0x14001b6a3  lea     rcx, [rbp+57h+arg_18]
0x14001b6a7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001b6ac  lea     r8, [rsi+60h]
0x14001b6b0  lea     rdx, [rbp+57h+arg_18]
0x14001b6b4  lea     rcx, [rbp+57h+var_60]
0x14001b6b8  call    ?SetRegistryValue@@YAJAEAVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@1@Z; SetRegistryValue(ATL::CRegKey &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001b6bd  mov     edi, eax
0x14001b6bf  mov     rdx, [rbp+57h+arg_18]
0x14001b6c3  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001b6c7  mov     ecx, r15d
0x14001b6ca  lock xadd [rdx+10h], ecx
0x14001b6cf  add     ecx, r15d
0x14001b6d2  test    ecx, ecx
0x14001b6d4  jg      short loc_14001B6E3
0x14001b6d6  lfence
0x14001b6d9  mov     rcx, [rdx]
0x14001b6dc  mov     r8, [rcx]
0x14001b6df  call    qword ptr [r8+8]
0x14001b6e3  test    edi, edi
0x14001b6e5  js      loc_14001BAE0
0x14001b6eb  lfence
0x14001b6ee  lea     rdx, aPkgdefsearchpa; "PkgDefSearchPath"
0x14001b6f5  lea     rcx, [rbp+57h+arg_18]
0x14001b6f9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001b6fe  lea     r8, [rsi+90h]
0x14001b705  lea     rdx, [rbp+57h+arg_18]
0x14001b709  lea     rcx, [rbp+57h+var_60]
0x14001b70d  call    ?SetRegistryValue@@YAJAEAVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@1@Z; SetRegistryValue(ATL::CRegKey &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001b712  mov     edi, eax
0x14001b714  mov     rdx, [rbp+57h+arg_18]
0x14001b718  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001b71c  mov     eax, r15d
0x14001b71f  lock xadd [rdx+10h], eax
0x14001b724  add     eax, r15d
0x14001b727  test    eax, eax
0x14001b729  jg      short loc_14001B737
0x14001b72b  lfence
0x14001b72e  mov     rcx, [rdx]
0x14001b731  mov     rax, [rcx]
0x14001b734  call    qword ptr [rax+8]
0x14001b737  test    edi, edi
0x14001b739  js      loc_14001BAE0
0x14001b73f  lfence
0x14001b742  lea     rdx, aImagemanifests; "ImageManifestSearchPath"
0x14001b749  lea     rcx, [rbp+57h+arg_18]
0x14001b74d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001b752  lea     r8, [rsi+0B0h]
0x14001b759  lea     rdx, [rbp+57h+arg_18]
0x14001b75d  lea     rcx, [rbp+57h+var_60]
0x14001b761  call    ?SetRegistryValue@@YAJAEAVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@1@Z; SetRegistryValue(ATL::CRegKey &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001b766  mov     edi, eax
0x14001b768  mov     rdx, [rbp+57h+arg_18]
0x14001b76c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001b770  mov     eax, r15d
0x14001b773  lock xadd [rdx+10h], eax
0x14001b778  add     eax, r15d
0x14001b77b  test    eax, eax
0x14001b77d  jg      short loc_14001B78B
0x14001b77f  lfence
0x14001b782  mov     rcx, [rdx]
0x14001b785  mov     rax, [rcx]
0x14001b788  call    qword ptr [rax+8]
0x14001b78b  test    edi, edi
0x14001b78d  js      loc_14001BAE0
0x14001b793  lfence
0x14001b796  lea     rdx, aUserfilesfolde; "UserFilesFolder"
0x14001b79d  lea     rcx, [rbp+57h+arg_18]
0x14001b7a1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001b7a6  lea     r8, [rsi+88h]
0x14001b7ad  lea     rdx, [rbp+57h+arg_18]
0x14001b7b1  lea     rcx, [rbp+57h+var_60]
0x14001b7b5  call    ?SetRegistryValue@@YAJAEAVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@1@Z; SetRegistryValue(ATL::CRegKey &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001b7ba  mov     edi, eax
0x14001b7bc  mov     rdx, [rbp+57h+arg_18]
0x14001b7c0  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001b7c4  mov     eax, r15d
0x14001b7c7  lock xadd [rdx+10h], eax
0x14001b7cc  add     eax, r15d
0x14001b7cf  test    eax, eax
0x14001b7d1  jg      short loc_14001B7DF
0x14001b7d3  lfence
0x14001b7d6  mov     rcx, [rdx]
0x14001b7d9  mov     rax, [rcx]
0x14001b7dc  call    qword ptr [rax+8]
0x14001b7df  test    edi, edi
0x14001b7e1  js      loc_14001BAE0
0x14001b7e7  lfence
0x14001b7ea  lea     rdx, aApplicationext; "ApplicationExtensionsFolder"
0x14001b7f1  lea     rcx, [rbp+57h+arg_18]
0x14001b7f5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001b7fa  lea     r8, [rsi+0A0h]
0x14001b801  lea     rdx, [rbp+57h+arg_18]
0x14001b805  lea     rcx, [rbp+57h+var_60]
0x14001b809  call    ?SetRegistryValue@@YAJAEAVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@1@Z; SetRegistryValue(ATL::CRegKey &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001b80e  mov     edi, eax
0x14001b810  mov     rdx, [rbp+57h+arg_18]
0x14001b814  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001b818  mov     eax, r15d
0x14001b81b  lock xadd [rdx+10h], eax
0x14001b820  add     eax, r15d
0x14001b823  test    eax, eax
0x14001b825  jg      short loc_14001B833
0x14001b827  lfence
0x14001b82a  mov     rcx, [rdx]
0x14001b82d  mov     rax, [rcx]
0x14001b830  call    qword ptr [rax+8]
0x14001b833  test    edi, edi
0x14001b835  js      loc_14001BAE0
0x14001b83b  lfence
0x14001b83e  lea     rdx, aPkgdefexclusio; "PkgDefExclusionDirectories"
0x14001b845  lea     rcx, [rbp+57h+arg_18]
0x14001b849  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001b84e  lea     r8, [rsi+98h]
0x14001b855  lea     rdx, [rbp+57h+arg_18]
0x14001b859  lea     rcx, [rbp+57h+var_60]
0x14001b85d  call    ?SetRegistryValue@@YAJAEAVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@1@Z; SetRegistryValue(ATL::CRegKey &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001b862  mov     edi, eax
0x14001b864  mov     rdx, [rbp+57h+arg_18]
0x14001b868  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001b86c  mov     eax, r15d
0x14001b86f  lock xadd [rdx+10h], eax
0x14001b874  add     eax, r15d
0x14001b877  test    eax, eax
0x14001b879  jg      short loc_14001B887
0x14001b87b  lfence
0x14001b87e  mov     rcx, [rdx]
0x14001b881  mov     rax, [rcx]
0x14001b884  call    qword ptr [rax+8]
0x14001b887  test    edi, edi
0x14001b889  js      loc_14001BAE0
0x14001b88f  lfence
0x14001b892  lea     rax, aTrue_0; "true"
0x14001b899  lea     rdx, aFalse; "false"
0x14001b8a0  cmp     [rsi+2Bh], r12b
0x14001b8a4  cmovnz  rdx, rax
0x14001b8a8  lea     rcx, [rbp+57h+var_70]
0x14001b8ac  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x14001b8b1  nop
0x14001b8b2  lea     rdx, aIsclientmode; "IsClientMode"
0x14001b8b9  lea     rcx, [rbp+57h+arg_18]
0x14001b8bd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x14001b8c2  lea     r8, [rbp+57h+var_70]
0x14001b8c6  lea     rdx, [rbp+57h+arg_18]
0x14001b8ca  lea     rcx, [rbp+57h+var_60]
0x14001b8ce  call    ?SetRegistryValue@@YAJAEAVCRegKey@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@1@Z; SetRegistryValue(ATL::CRegKey &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14001b8d3  mov     edi, eax
0x14001b8d5  mov     rdx, [rbp+57h+arg_18]
0x14001b8d9  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001b8dd  mov     eax, r15d
0x14001b8e0  lock xadd [rdx+10h], eax
0x14001b8e5  add     eax, r15d
0x14001b8e8  test    eax, eax
0x14001b8ea  jg      short loc_14001B8F9
0x14001b8ec  lfence
0x14001b8ef  mov     rcx, [rdx]
  ... truncated ...
```
