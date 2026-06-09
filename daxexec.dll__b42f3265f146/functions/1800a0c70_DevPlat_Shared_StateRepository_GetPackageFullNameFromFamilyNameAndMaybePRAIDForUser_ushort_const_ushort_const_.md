# DevPlat::Shared::StateRepository::GetPackageFullNameFromFamilyNameAndMaybePRAIDForUser(ushort const *,ushort const *,ushort const *,HSTRING__ * *)

- ea: `0x1800a0c70`
- end: `0x1800a13b8`
- name: `?GetPackageFullNameFromFamilyNameAndMaybePRAIDForUser@StateRepository@Shared@DevPlat@@YAJPEBG00PEAPEAUHSTRING__@@@Z`
- size: `1864`
- prototype: `int(DevPlat::Shared::StateRepository *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, HSTRING *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18003fa14`

## callees

- `0x180004f70`
- `0x1800057fc`
- `0x1800059a8`
- `0x18000ff04`
- `0x18000ff24`
- `0x1800160a0`
- `0x18003ad7c`
- `0x18003c4a0`
- `0x18003f050`
- `0x1800a04f0`
- `0x1800a0a1c`
- `0x1800a0b04`
- `0x1800a0c70`
- `0x1800a16ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a0e1f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a0e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0e00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0e00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0e11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0e6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0ed1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0f4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0e11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0e6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0ed1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0f4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a1279`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800a1279`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a0e39`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a0e39`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a1086`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a1143`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a120d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a12c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a1327`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a138a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a1086`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a1143`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a120d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a12c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a1327`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800a138a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a0d12`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a0d92`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a0f31`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a0fda`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a10a2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a115f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a1229`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a12e0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a1343`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a13a6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a0d12`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a0d92`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a0f31`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a0fda`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a10a2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a115f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a1229`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a12e0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a1343`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800a13a6`

## string_xrefs

- `0x1800a104a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x1800a0dc5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800a0e50`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800a0eb5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800a0ee8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall DevPlat::Shared::StateRepository::GetPackageFullNameFromFamilyNameAndMaybePRAIDForUser(
        DevPlat::Shared::StateRepository *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        HSTRING *a4)
{
  unsigned int LastError; // ebx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // r8
  int v12; // eax
  __int64 v13; // rcx
  int token_information; // eax
  HLOCAL v15; // rcx
  HLOCAL v16; // rdi
  void *v17; // r14
  __int64 v18; // r8
  const char *v19; // r9
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v30; // eax
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rdx
  HRESULT String; // eax
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  int *v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v46; // [rsp+38h] [rbp-C8h] BYREF
  bool v47; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v49; // [rsp+50h] [rbp-B0h] BYREF
  int v50; // [rsp+58h] [rbp-A8h]
  __int64 v51; // [rsp+60h] [rbp-A0h]
  __int64 v52; // [rsp+68h] [rbp-98h] BYREF
  PCNZWCH sourceString[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v54; // [rsp+80h] [rbp-80h]
  __int64 v55; // [rsp+88h] [rbp-78h]
  __int64 v56; // [rsp+90h] [rbp-70h]
  __int64 v57; // [rsp+98h] [rbp-68h]
  __int64 v58; // [rsp+A0h] [rbp-60h]
  __int64 v59; // [rsp+A8h] [rbp-58h]
  __int128 v60; // [rsp+B0h] [rbp-50h]
  int v61; // [rsp+C0h] [rbp-40h]
  __int64 v62; // [rsp+C8h] [rbp-38h]
  __int64 v63; // [rsp+D0h] [rbp-30h]
  __int64 v64; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v65[72]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v66; // [rsp+130h] [rbp+30h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  if ( !a4 )
  {
    LastError = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\staterepoutil.cpp",
      (const char *)0x80004003LL,
      (int)v42);
    return LastError;
  }
  v46 = 0;
  v9 = StateRepository::Cache::Manager_NoThrow::Open((StateRepository::Cache::Manager_NoThrow *)&v46);
  LastError = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\staterepoutil.cpp",
      (const char *)(unsigned int)v9,
      (int)v42);
    v10 = v46;
    v46 = 0;
    if ( v10 )
      SRCacheManager_Close();
    return LastError;
  }
  v64 = 0;
  memset_0(v65, 0, 0x44u);
  v66 = 0;
  LOBYTE(v45) = 0;
  if ( this )
  {
    v42 = &v45;
    v12 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(&v46, this, v11, &v64);
    LastError = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x31,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\staterepoutil.cpp",
        (const char *)(unsigned int)v12,
        (int)&v45);
      v13 = v46;
      v46 = 0;
      if ( v13 )
        SRCacheManager_Close();
      return LastError;
    }
    goto LABEL_34;
  }
  hMem = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&hMem, 0);
  LastError = token_information;
  if ( token_information < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)token_information,
      (int)v42);
    v15 = hMem;
    if ( hMem )
      goto LABEL_26;
    goto LABEL_27;
  }
  v16 = hMem;
  v17 = *(void **)hMem;
  hMem = 0;
  if ( ConvertSidToStringSidW(v17, (LPWSTR *)&hMem) )
  {
    v42 = &v45;
    v20 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(&v46, hMem, v18, &v64);
    LastError = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
        (const char *)(unsigned int)v20,
        (int)&v45);
      if ( hMem )
        LocalFree(hMem);
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x160,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
        (const char *)LastError,
        (int)v42);
      if ( v16 )
      {
        v15 = v16;
LABEL_26:
        operator delete(v15);
      }
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\staterepoutil.cpp",
        (const char *)LastError,
        v43);
      v21 = v46;
      v46 = 0;
      if ( v21 )
        SRCacheManager_Close();
      return LastError;
    }
    if ( hMem )
      LocalFree(hMem);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xDC,
                  (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
                  v19);
    if ( hMem )
      LocalFree(hMem);
    if ( (LastError & 0x80000000) != 0 )
      goto LABEL_24;
  }
  if ( v16 )
    operator delete(v16);
LABEL_34:
  if ( (_BYTE)v45 )
  {
    v52 = 0;
    v22 = StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
            (struct StateRepository::Cache::Manager_NoThrow *)&v46,
            a2,
            &v52);
    LastError = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\staterepoutil.cpp",
        (const char *)(unsigned int)v22,
        (int)v42);
      v23 = v46;
      v46 = 0;
      if ( v23 )
        SRCacheManager_Close();
      return LastError;
    }
    if ( v52 )
    {
      v49 = 0;
      v50 = 0;
      v51 = 0;
      v24 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(
              (StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *)&v49,
              (struct StateRepository::Cache::Manager_NoThrow *)&v46,
              v52);
      LastError = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x81F,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
          (const char *)(unsigned int)v24,
          (int)v42);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3E,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\staterepoutil.cpp",
          (const char *)LastError,
          v44);
        v25 = v49;
        v49 = 0;
        if ( v25 )
          SRCacheContext_Close();
        v26 = v46;
        v46 = 0;
        if ( v26 )
          SRCacheManager_Close();
        return LastError;
      }
      LOBYTE(v45) = 0;
      *(_OWORD *)sourceString = 0;
      v54 = 0;
      v55 = 0;
      v56 = 0;
      v57 = 0;
      v58 = 0;
      v59 = 0;
      v60 = 0;
      v61 = 0;
      v62 = 0;
      v63 = 0;
      v27 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(&v49, 5, sourceString, &v45);
      LastError = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x45,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\staterepoutil.cpp",
          (const char *)(unsigned int)v27,
          (int)v42);
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)sourceString);
        v28 = v49;
        v49 = 0;
        if ( v28 )
          SRCacheContext_Close();
        v29 = v46;
        v46 = 0;
        if ( v29 )
          SRCacheManager_Close();
        return LastError;
      }
      while ( 1 )
      {
        if ( !(_BYTE)v45 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6C,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\staterepoutil.cpp",
            (const char *)0x80070490LL,
            (int)v42);
          StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)sourceString);
          v32 = v49;
          v49 = 0;
          if ( v32 )
            SRCacheContext_Close();
          goto LABEL_61;
        }
        if ( (v55 & 1) != 0 )
        {
          v47 = 0;
          v30 = StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
                  (struct StateRepository::Cache::Manager_NoThrow *)&v46,
                  v64,
                  (__int64)sourceString[0],
                  &v47);
          LastError = v30;
          if ( v30 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4C,
              (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\staterepoutil.cpp",
              (const char *)(unsigned int)v30,
              (int)v42);
            StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)sourceString);
            v38 = v49;
            v49 = 0;
            if ( v38 )
              SRCacheContext_Close();
            v39 = v46;
            v46 = 0;
            if ( v39 )
              SRCacheManager_Close();
            return LastError;
          }
          if ( v47 )
          {
            v34 = -1;
            do
              ++v34;
            while ( sourceString[1][v34] );
            String = WindowsCreateString(sourceString[1], v34, a4);
            LastError = String;
            if ( String < 0 )
            {
              *a4 = 0;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x64,
                (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\staterepoutil.cpp",
                (const char *)(unsigned int)String,
                (int)v42);
            }
            StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)sourceString);
            v36 = v49;
            v49 = 0;
            if ( v36 )
              SRCacheContext_Close();
            v37 = v46;
            v46 = 0;
            if ( v37 )
              SRCacheManager_Close();
            return LastError;
          }
        }
        ++v50;
        v31 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(&v49, 5, sourceString, &v45);
        LastError = v31;
        if ( v31 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x68,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\staterepoutil.cpp",
            (const char *)(unsigned int)v31,
            (int)v42);
          StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)sourceString);
          v40 = v49;
          v49 = 0;
          if ( v40 )
            SRCacheContext_Close();
          v41 = v46;
          v46 = 0;
          if ( v41 )
            SRCacheManager_Close();
          return LastError;
        }
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\staterepoutil.cpp",
      (const char *)0x80070490LL,
      (int)v42);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\staterepoutil.cpp",
      (const char *)0x80070490LL,
      (int)v42);
  }
LABEL_61:
  v33 = v46;
  v46 = 0;
  if ( v33 )
    SRCacheManager_Close();
  return 2147943568LL;
}

```

## disassembly

```asm
0x1800a0c70  mov     [rsp-8+arg_10], rbx
0x1800a0c75  push    rbp
0x1800a0c76  push    rsi
0x1800a0c77  push    rdi
0x1800a0c78  push    r12
0x1800a0c7a  push    r13
0x1800a0c7c  push    r14
0x1800a0c7e  push    r15
0x1800a0c80  lea     rbp, [rsp-50h]
0x1800a0c85  sub     rsp, 150h
0x1800a0c8c  mov     rax, cs:__security_cookie
0x1800a0c93  xor     rax, rsp
0x1800a0c96  mov     [rbp+80h+var_40], rax
0x1800a0c9a  mov     r12, r9
0x1800a0c9d  mov     r15, rdx
0x1800a0ca0  mov     rdi, rcx
0x1800a0ca3  xor     r13d, r13d
0x1800a0ca6  test    r9, r9
0x1800a0ca9  jnz     short loc_1800A0CD2
0x1800a0cab  mov     rcx, [rbp+88h]; this
0x1800a0cb2  mov     ebx, 80004003h
0x1800a0cb7  mov     r9d, ebx; char *
0x1800a0cba  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800a0cc1  lea     edx, [r12+29h]; void *
0x1800a0cc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0ccb  mov     eax, ebx
0x1800a0ccd  jmp     loc_1800A123B
0x1800a0cd2  mov     [rsp+180h+var_148], r13
0x1800a0cd7  lea     rcx, [rsp+180h+var_148]; this
0x1800a0cdc  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJXZ; StateRepository::Cache::Manager_NoThrow::Open(void)
0x1800a0ce1  mov     ebx, eax
0x1800a0ce3  test    eax, eax
0x1800a0ce5  jns     short loc_1800A0D21
0x1800a0ce7  mov     rcx, [rbp+88h]; this
0x1800a0cee  mov     r9d, eax; char *
0x1800a0cf1  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800a0cf8  mov     edx, 2Bh ; '+'; void *
0x1800a0cfd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0d02  nop
0x1800a0d03  mov     rcx, [rsp+180h+var_148]
0x1800a0d08  mov     [rsp+180h+var_148], r13
0x1800a0d0d  test    rcx, rcx
0x1800a0d10  jz      short loc_1800A0D1F
0x1800a0d12  call    cs:__imp_SRCacheManager_Close
0x1800a0d19  nop     dword ptr [rax+rax+00h]
0x1800a0d1e  nop
0x1800a0d1f  jmp     short loc_1800A0CCB
0x1800a0d21  mov     [rbp+80h+var_A0], r13
0x1800a0d25  xor     edx, edx; Val
0x1800a0d27  lea     r8d, [rdx+44h]; Size
0x1800a0d2b  lea     rcx, [rbp+80h+var_98]; void *
0x1800a0d2f  call    memset_0
0x1800a0d34  mov     [rbp+80h+var_50], r13
0x1800a0d38  mov     byte ptr [rsp+180h+var_150], r13b
0x1800a0d3d  test    rdi, rdi
0x1800a0d40  jz      short loc_1800A0DA4
0x1800a0d42  lea     rax, [rsp+180h+var_150]
0x1800a0d47  mov     qword ptr [rsp+180h+var_160], rax; int
0x1800a0d4c  lea     r9, [rbp+80h+var_A0]
0x1800a0d50  mov     rdx, rdi
0x1800a0d53  lea     rcx, [rsp+180h+var_148]
0x1800a0d58  call    ?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,StateRepository::Cache::Entity::User_NoThrow &,bool &)
0x1800a0d5d  mov     ebx, eax
0x1800a0d5f  test    eax, eax
0x1800a0d61  jns     loc_1800A0F67
0x1800a0d67  mov     rcx, [rbp+88h]; this
0x1800a0d6e  mov     r9d, eax; char *
0x1800a0d71  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800a0d78  mov     edx, 31h ; '1'; void *
0x1800a0d7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0d82  nop
0x1800a0d83  mov     rcx, [rsp+180h+var_148]
0x1800a0d88  mov     [rsp+180h+var_148], r13
0x1800a0d8d  test    rcx, rcx
0x1800a0d90  jz      short loc_1800A0D9F
0x1800a0d92  call    cs:__imp_SRCacheManager_Close
0x1800a0d99  nop     dword ptr [rax+rax+00h]
0x1800a0d9e  nop
0x1800a0d9f  jmp     loc_1800A0CCB
0x1800a0da4  mov     [rsp+180h+hMem], r13
0x1800a0da9  xor     edx, edx
0x1800a0dab  lea     rcx, [rsp+180h+hMem]
0x1800a0db0  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1800a0db5  mov     ebx, eax
0x1800a0db7  test    eax, eax
0x1800a0db9  jns     short loc_1800A0DE9
0x1800a0dbb  mov     rcx, [rbp+88h]; this
0x1800a0dc2  mov     r9d, eax; char *
0x1800a0dc5  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a0dcc  mov     edx, 15Fh; void *
0x1800a0dd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0dd6  mov     rcx, [rsp+180h+hMem]
0x1800a0ddb  test    rcx, rcx
0x1800a0dde  jz      loc_1800A0F06
0x1800a0de4  jmp     loc_1800A0F01
0x1800a0de9  mov     rdi, [rsp+180h+hMem]
0x1800a0dee  mov     r14, [rdi]
0x1800a0df1  mov     [rsp+180h+hMem], r13
0x1800a0df6  mov     rsi, [rsp+180h+hMem]
0x1800a0dfb  test    rsi, rsi
0x1800a0dfe  jz      short loc_1800A0E2C
0x1800a0e00  call    cs:__imp_GetLastError
0x1800a0e07  nop     dword ptr [rax+rax+00h]
0x1800a0e0c  mov     ebx, eax
0x1800a0e0e  mov     rcx, rsi; hMem
0x1800a0e11  call    cs:__imp_LocalFree
0x1800a0e18  nop     dword ptr [rax+rax+00h]
0x1800a0e1d  mov     ecx, ebx; dwErrCode
0x1800a0e1f  call    cs:__imp_SetLastError
0x1800a0e26  nop     dword ptr [rax+rax+00h]
0x1800a0e2b  nop
0x1800a0e2c  mov     [rsp+180h+hMem], r13
0x1800a0e31  lea     rdx, [rsp+180h+hMem]; StringSid
0x1800a0e36  mov     rcx, r14; Sid
0x1800a0e39  call    cs:__imp_ConvertSidToStringSidW
0x1800a0e40  nop     dword ptr [rax+rax+00h]
0x1800a0e45  test    eax, eax
0x1800a0e47  jnz     short loc_1800A0E84
0x1800a0e49  mov     rcx, [rbp+88h]; this
0x1800a0e50  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a0e57  mov     edx, 0DCh; void *
0x1800a0e5c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a0e61  mov     ebx, eax
0x1800a0e63  mov     rcx, [rsp+180h+hMem]; hMem
0x1800a0e68  test    rcx, rcx
0x1800a0e6b  jz      short loc_1800A0E7A
0x1800a0e6d  call    cs:__imp_LocalFree
0x1800a0e74  nop     dword ptr [rax+rax+00h]
0x1800a0e79  nop
0x1800a0e7a  test    ebx, ebx
0x1800a0e7c  jns     loc_1800A0F5A
0x1800a0e82  jmp     short loc_1800A0EDE
0x1800a0e84  lea     rax, [rsp+180h+var_150]
0x1800a0e89  mov     qword ptr [rsp+180h+var_160], rax; int
0x1800a0e8e  lea     r9, [rbp+80h+var_A0]
0x1800a0e92  mov     rdx, [rsp+180h+hMem]
0x1800a0e97  lea     rcx, [rsp+180h+var_148]
0x1800a0e9c  call    ?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,StateRepository::Cache::Entity::User_NoThrow &,bool &)
0x1800a0ea1  mov     ebx, eax
0x1800a0ea3  test    eax, eax
0x1800a0ea5  jns     loc_1800A0F43
0x1800a0eab  mov     rcx, [rbp+88h]; this
0x1800a0eb2  mov     r9d, eax; char *
0x1800a0eb5  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a0ebc  mov     edx, 0DEh; void *
0x1800a0ec1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0ec6  nop
0x1800a0ec7  mov     rcx, [rsp+180h+hMem]; hMem
0x1800a0ecc  test    rcx, rcx
0x1800a0ecf  jz      short loc_1800A0EDE
0x1800a0ed1  call    cs:__imp_LocalFree
0x1800a0ed8  nop     dword ptr [rax+rax+00h]
0x1800a0edd  nop
0x1800a0ede  mov     rcx, [rbp+88h]; this
0x1800a0ee5  mov     r9d, ebx; char *
0x1800a0ee8  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a0eef  mov     edx, 160h; void *
0x1800a0ef4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0ef9  test    rdi, rdi
0x1800a0efc  jz      short loc_1800A0F06
0x1800a0efe  mov     rcx, rdi; Block
0x1800a0f01  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a0f06  mov     rcx, [rbp+88h]; this
0x1800a0f0d  mov     r9d, ebx; char *
0x1800a0f10  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800a0f17  mov     edx, 35h ; '5'; void *
0x1800a0f1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0f21  nop
0x1800a0f22  mov     rcx, [rsp+180h+var_148]
0x1800a0f27  mov     [rsp+180h+var_148], r13
0x1800a0f2c  test    rcx, rcx
0x1800a0f2f  jz      short loc_1800A0F3E
0x1800a0f31  call    cs:__imp_SRCacheManager_Close
0x1800a0f38  nop     dword ptr [rax+rax+00h]
0x1800a0f3d  nop
0x1800a0f3e  jmp     loc_1800A0CCB
0x1800a0f43  mov     rcx, [rsp+180h+hMem]; hMem
0x1800a0f48  test    rcx, rcx
0x1800a0f4b  jz      short loc_1800A0F5A
0x1800a0f4d  call    cs:__imp_LocalFree
0x1800a0f54  nop     dword ptr [rax+rax+00h]
0x1800a0f59  nop
0x1800a0f5a  test    rdi, rdi
0x1800a0f5d  jz      short loc_1800A0F67
0x1800a0f5f  mov     rcx, rdi; Block
0x1800a0f62  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a0f67  cmp     byte ptr [rsp+180h+var_150], r13b
0x1800a0f6c  jnz     short loc_1800A0F92
0x1800a0f6e  mov     rcx, [rbp+88h]; this
0x1800a0f75  mov     r9d, 80070490h; char *
0x1800a0f7b  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800a0f82  mov     edx, 37h ; '7'; void *
0x1800a0f87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0f8c  nop
0x1800a0f8d  jmp     loc_1800A121A
0x1800a0f92  mov     [rsp+180h+var_118], r13
0x1800a0f97  lea     r8, [rsp+180h+var_118]; __int64 *
0x1800a0f9c  mov     rdx, r15; unsigned __int16 *
0x1800a0f9f  lea     rcx, [rsp+180h+var_148]; struct StateRepository::Cache::Manager_NoThrow *
0x1800a0fa4  call    ?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x1800a0fa9  mov     ebx, eax
0x1800a0fab  test    eax, eax
0x1800a0fad  jns     short loc_1800A0FEC
0x1800a0faf  mov     rcx, [rbp+88h]; this
0x1800a0fb6  mov     r9d, eax; char *
0x1800a0fb9  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800a0fc0  mov     edx, 3Ah ; ':'; void *
0x1800a0fc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0fca  nop
0x1800a0fcb  mov     rcx, [rsp+180h+var_148]
0x1800a0fd0  mov     [rsp+180h+var_148], r13
0x1800a0fd5  test    rcx, rcx
0x1800a0fd8  jz      short loc_1800A0FE7
0x1800a0fda  call    cs:__imp_SRCacheManager_Close
0x1800a0fe1  nop     dword ptr [rax+rax+00h]
0x1800a0fe6  nop
0x1800a0fe7  jmp     loc_1800A0CCB
0x1800a0fec  cmp     [rsp+180h+var_118], r13
0x1800a0ff1  jnz     short loc_1800A1017
0x1800a0ff3  mov     rcx, [rbp+88h]; this
0x1800a0ffa  mov     r9d, 80070490h; char *
0x1800a1000  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800a1007  mov     edx, 3Bh ; ';'; void *
0x1800a100c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1011  nop
0x1800a1012  jmp     loc_1800A121A
0x1800a1017  mov     [rsp+180h+var_130], r13
0x1800a101c  mov     [rsp+180h+var_128], r13d
0x1800a1021  mov     [rsp+180h+var_120], r13
0x1800a1026  mov     r8, [rsp+180h+var_118]; __int64
0x1800a102b  lea     rdx, [rsp+180h+var_148]; struct StateRepository::Cache::Manager_NoThrow *
0x1800a1030  lea     rcx, [rsp+180h+var_130]; this
0x1800a1035  call    ?OpenByPackageFamily@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64)
0x1800a103a  mov     ebx, eax
0x1800a103c  test    eax, eax
0x1800a103e  jns     short loc_1800A10B4
0x1800a1040  mov     rcx, [rbp+88h]; this
0x1800a1047  mov     r9d, eax; char *
0x1800a104a  lea     r8, aOnecorePrivate_15; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800a1051  mov     edx, 81Fh; void *
0x1800a1056  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a105b  mov     rcx, [rbp+88h]; this
0x1800a1062  mov     r9d, ebx; char *
0x1800a1065  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800a106c  mov     edx, 3Eh ; '>'; void *
0x1800a1071  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1076  nop
0x1800a1077  mov     rcx, [rsp+180h+var_130]
0x1800a107c  mov     [rsp+180h+var_130], r13
0x1800a1081  test    rcx, rcx
0x1800a1084  jz      short loc_1800A1093
0x1800a1086  call    cs:__imp_SRCacheContext_Close
0x1800a108d  nop     dword ptr [rax+rax+00h]
0x1800a1092  nop
0x1800a1093  mov     rcx, [rsp+180h+var_148]
0x1800a1098  mov     [rsp+180h+var_148], r13
0x1800a109d  test    rcx, rcx
0x1800a10a0  jz      short loc_1800A10AF
0x1800a10a2  call    cs:__imp_SRCacheManager_Close
0x1800a10a9  nop     dword ptr [rax+rax+00h]
0x1800a10ae  nop
0x1800a10af  jmp     loc_1800A0CCB
0x1800a10b4  mov     byte ptr [rsp+180h+var_150], r13b
0x1800a10b9  xorps   xmm0, xmm0
0x1800a10bc  movdqa  xmmword ptr [rsp+180h+sourceString], xmm0
0x1800a10c2  mov     [rbp+80h+var_100], r13
0x1800a10c6  mov     [rbp+80h+var_F8], r13
0x1800a10ca  mov     [rbp+80h+var_F0], r13
0x1800a10ce  mov     [rbp+80h+var_E8], r13
0x1800a10d2  mov     [rbp+80h+var_E0], r13
0x1800a10d6  mov     [rbp+80h+var_D8], r13
0x1800a10da  movdqa  [rbp+80h+var_D0], xmm0
0x1800a10df  mov     [rbp+80h+var_C0], r13d
0x1800a10e3  mov     [rbp+80h+var_B8], r13
0x1800a10e7  mov     [rbp+80h+var_B0], r13
0x1800a10eb  lea     r9, [rsp+180h+var_150]
0x1800a10f0  lea     r8, [rsp+180h+sourceString]
0x1800a10f5  mov     edi, 5
0x1800a10fa  mov     edx, edi
0x1800a10fc  lea     rcx, [rsp+180h+var_130]
0x1800a1101  call    ?Get@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x1800a1106  mov     ebx, eax
0x1800a1108  test    eax, eax
0x1800a110a  jns     loc_1800A11CE
0x1800a1110  mov     rcx, [rbp+88h]; this
0x1800a1117  mov     r9d, eax; char *
0x1800a111a  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800a1121  lea     edx, [rdi+40h]; void *
0x1800a1124  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1129  lea     rcx, [rsp+180h+sourceString]; this
0x1800a112e  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1800a1133  nop
0x1800a1134  mov     rcx, [rsp+180h+var_130]
0x1800a1139  mov     [rsp+180h+var_130], r13
0x1800a113e  test    rcx, rcx
0x1800a1141  jz      short loc_1800A1150
0x1800a1143  call    cs:__imp_SRCacheContext_Close
0x1800a114a  nop     dword ptr [rax+rax+00h]
0x1800a114f  nop
0x1800a1150  mov     rcx, [rsp+180h+var_148]
  ... truncated ...
```
