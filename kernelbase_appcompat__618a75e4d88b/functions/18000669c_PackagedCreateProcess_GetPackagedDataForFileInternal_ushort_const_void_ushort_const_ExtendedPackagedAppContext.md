# PackagedCreateProcess::GetPackagedDataForFileInternal(ushort const *,void *,ushort const *,ExtendedPackagedAppContext *)

- ea: `0x18000669c`
- end: `0x180007627`
- name: `?GetPackagedDataForFileInternal@PackagedCreateProcess@@CAJPEBGPEAX0PEAVExtendedPackagedAppContext@@@Z`
- size: `3979`
- prototype: `__int64 __fastcall(const unsigned __int16 *Source, void *, const unsigned __int16 *, struct ExtendedPackagedAppContext *)`
- caller_count: `2`
- callee_count: `30`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004558`
- `0x18016059c`

## callees

- `0x180004370`
- `0x1800056f8`
- `0x180005e70`
- `0x180006508`
- `0x18000669c`
- `0x180007630`
- `0x180007910`
- `0x180007c94`
- `0x180007ff0`
- `0x180008cb0`
- `0x1800090b0`
- `0x18000a9c4`
- `0x18000b014`
- `0x18000b5e4`
- `0x180012c44`
- `0x180037920`
- `0x1800391f0`
- `0x180039600`
- `0x18005b2c4`
- `0x1800bdc30`
- `0x1800e31e0`
- `0x1800e32d4`
- `0x1800ee67c`
- `0x180115764`
- `0x18011eb9c`
- `0x18011ec04`
- `0x180128e1c`
- `0x18012b090`
- `0x18012d2e0`
- `0x180160a34`

## import_xrefs

- `ntdll!memcpy_s` at `0x180006924`
- `ntdll!memcpy_s` at `0x180006a0b`
- `ntdll!memcpy_s` at `0x180006b0c`
- `ntdll!memcpy_s` at `0x180006924`
- `ntdll!memcpy_s` at `0x180006a0b`
- `ntdll!memcpy_s` at `0x180006b0c`
- `ntdll!RtlFreeSid` at `0x180006dae`
- `ntdll!RtlFreeSid` at `0x18000713d`
- `ntdll!RtlFreeSid` at `0x1800072ae`
- `ntdll!RtlFreeSid` at `0x180006dae`
- `ntdll!RtlFreeSid` at `0x18000713d`
- `ntdll!RtlFreeSid` at `0x1800072ae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18000681b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18000681b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800066f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x1800066f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180006be9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180006c3d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180006c9c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180006e32`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180006f8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180006fb7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180006ff0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800070f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007264`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007567`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180006be9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180006c3d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180006c9c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180006e32`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180006f8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180006fb7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180006ff0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800070f1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007264`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180007567`

## string_xrefs

- `0x180006743`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180006b98`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180006c04`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180006c75`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180006cda`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180006cf8`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180006dc6`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180006df6`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180006efa`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180006f6d`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180007044`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x1800071f8`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180007220`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180007292`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x1800072ff`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180007329`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18000735c`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x1800073af`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180007537`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180199360`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x180006c5a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180006cb2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18000744e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180007433`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180006720`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-manager.hpp`
- `0x1800075f9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180007615`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180006f4d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DependencyGraph.hpp`
- `0x1800075e6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DependencyGraph.hpp`
- `0x1801992dc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DependencyGraph.hpp`
- `0x1801992ec`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DependencyGraph.hpp`
- `0x18019932b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DependencyGraph.hpp`

## pseudocode

```c
__int64 __fastcall PackagedCreateProcess::GetPackagedDataForFileInternal(
        const unsigned __int16 *Source,
        void *a2,
        const unsigned __int16 *a3,
        struct ExtendedPackagedAppContext *a4)
{
  const unsigned __int16 *v5; // r14
  unsigned int v8; // ebx
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int Next; // eax
  __int64 v16; // r13
  __int64 v17; // rcx
  const unsigned __int16 *v18; // rax
  rsize_t v19; // rdi
  char *v20; // rax
  char *v21; // rbx
  unsigned __int16 *v22; // rbx
  int MatchingAppUserModelIdIfPresent; // eax
  HRESULT WindowsPplTrustLabelSid; // edi
  const WCHAR *v25; // rdx
  const WCHAR *v26; // rcx
  int v27; // eax
  const char *v28; // r9
  void *v29; // r15
  __int64 v30; // rcx
  char *v31; // rax
  rsize_t v32; // rsi
  WCHAR *v33; // rax
  WCHAR *v34; // rdi
  __int64 v35; // r8
  WCHAR *v36; // rsi
  int v37; // ecx
  void *v38; // rax
  __int64 v39; // rcx
  const char *v40; // r9
  char *v41; // rax
  rsize_t v42; // r14
  unsigned __int16 *v43; // rax
  unsigned __int16 *v44; // rdi
  unsigned int v45; // r13d
  _WORD *v46; // r9
  _WORD *v47; // r8
  __int64 v48; // rax
  __int64 v49; // rdx
  _WORD *v50; // rcx
  signed int v51; // r14d
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rdx
  unsigned __int64 v56; // r9
  __int64 v57; // rdx
  bool v58; // r9
  __int64 v59; // rdx
  __int64 v60; // rcx
  int v61; // eax
  void *v62; // r14
  int v63; // eax
  __int64 v64; // rdx
  int v65; // eax
  int v66; // esi
  __int64 v67; // rdx
  __int64 *v68; // rcx
  __int64 v69; // rcx
  __int64 *v70; // rcx
  __int64 v71; // rcx
  int v72; // eax
  __int64 v73; // rcx
  __int64 v74; // rdx
  int v75; // eax
  __int64 *v76; // rcx
  int v77; // edx
  int v78; // eax
  __int64 v79; // r8
  __int64 v80; // rdx
  int v81; // eax
  __int64 v82; // r8
  __int64 v83; // rdx
  bool *v84; // [rsp+28h] [rbp-E0h]
  int v85; // [rsp+28h] [rbp-E0h]
  int v86; // [rsp+28h] [rbp-E0h]
  int v87; // [rsp+28h] [rbp-E0h]
  int v88; // [rsp+28h] [rbp-E0h]
  bool v89[8]; // [rsp+38h] [rbp-D0h] BYREF
  void *Sourcea; // [rsp+40h] [rbp-C8h] BYREF
  bool v91[8]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v92; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v93; // [rsp+58h] [rbp-B0h]
  __int64 v94; // [rsp+60h] [rbp-A8h]
  HLOCAL hMem; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v96; // [rsp+70h] [rbp-98h] BYREF
  __int64 *v97; // [rsp+78h] [rbp-90h] BYREF
  __int64 v98; // [rsp+80h] [rbp-88h] BYREF
  __int64 v99; // [rsp+88h] [rbp-80h]
  PSID Sid; // [rsp+90h] [rbp-78h] BYREF
  __int64 v101; // [rsp+98h] [rbp-70h] BYREF
  __int64 v102[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v103; // [rsp+B8h] [rbp-50h]
  __int64 v104; // [rsp+C0h] [rbp-48h]
  __int64 v105; // [rsp+C8h] [rbp-40h]
  __int64 v106; // [rsp+D0h] [rbp-38h]
  __int64 v107; // [rsp+D8h] [rbp-30h]
  __int64 v108; // [rsp+E0h] [rbp-28h]
  __int128 v109; // [rsp+E8h] [rbp-20h]
  int v110; // [rsp+F8h] [rbp-10h]
  __int64 v111; // [rsp+100h] [rbp-8h]
  __int64 v112; // [rsp+108h] [rbp+0h]
  __int64 v113; // [rsp+118h] [rbp+10h] BYREF
  __int128 v114; // [rsp+120h] [rbp+18h] BYREF
  __int128 v115; // [rsp+130h] [rbp+28h]
  __int64 v116; // [rsp+140h] [rbp+38h]
  __int128 v117; // [rsp+148h] [rbp+40h] BYREF
  __int64 v118; // [rsp+158h] [rbp+50h]
  __int128 v119; // [rsp+160h] [rbp+58h]
  __int64 v120; // [rsp+170h] [rbp+68h]
  __int64 v121; // [rsp+178h] [rbp+70h]
  __int64 v122; // [rsp+180h] [rbp+78h]
  __int128 v123; // [rsp+188h] [rbp+80h]
  int v124; // [rsp+198h] [rbp+90h]
  __int64 v125; // [rsp+1A0h] [rbp+98h]
  __int64 v126; // [rsp+1A8h] [rbp+A0h]
  wil::details::in1diag3 *retaddr; // [rsp+1F0h] [rbp+E8h]

  LOBYTE(v99) = 1;
  v5 = Source;
  v97 = &v96;
  v96 = 0;
  v98 = 0;
  v8 = SRCacheManager_Open(0, &v98);
  if ( (_BYTE)v99 )
    wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(v97, v98);
  if ( (v8 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-manager.hpp",
      (const char *)v8,
      (int)v84);
    v9 = v8;
    v10 = 375;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
      (const char *)v9,
      (int)v84);
    goto LABEL_6;
  }
  v113 = 0;
  v12 = StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
          (struct StateRepository::Cache::Manager_NoThrow *)&v96,
          a3,
          &v113);
  v8 = v12;
  if ( v12 < 0 )
  {
    v9 = (unsigned int)v12;
    v10 = 377;
    goto LABEL_5;
  }
  if ( !v113 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17A,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
      (const char *)0x80070057LL,
      (int)v84);
    v8 = -2147024809;
    goto LABEL_6;
  }
  v92 = 0;
  LODWORD(v93) = 0;
  v94 = 0;
  v13 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(
          (StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *)&v92,
          (struct StateRepository::Cache::Manager_NoThrow *)&v96,
          v113);
  v8 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v13,
      (int)v84);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17E,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
      (const char *)v8,
      v85);
    goto LABEL_65;
  }
  *(_OWORD *)v102 = 0;
  v103 = 0;
  v104 = 0;
  v105 = 0;
  v106 = 0;
  v107 = 0;
  v108 = 0;
  v109 = 0;
  v110 = 0;
  v111 = 0;
  v112 = 0;
  v89[1] = 0;
  if ( v92 )
  {
    Sourcea = 0;
    v14 = SRCacheContext_EnumerateData(v92, (unsigned int)v93, &Sourcea);
    v8 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v14,
        (int)v84);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x755,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
        (const char *)v8,
        v87);
      v55 = 1901;
    }
    else
    {
      if ( !Sourcea )
        goto LABEL_14;
      v84 = &v89[1];
      v8 = StateRepository::Cache::Entity::Package_NoThrow::Get(v94, Sourcea, 1853, v102);
      if ( (v8 & 0x80000000) == 0 )
        goto LABEL_14;
      v55 = 1906;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v55,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v8,
      (int)v84);
    v56 = v8;
    v57 = 395;
LABEL_69:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v57,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
      (const char *)v56,
      (int)v84);
    goto LABEL_70;
  }
LABEL_14:
  v101 = 0;
  Next = StateRepository::Cache::Entity::User_NoThrow::GetByToken(
           (struct StateRepository::Cache::Manager_NoThrow *)&v96,
           a2,
           &v101);
  v8 = Next;
  if ( Next < 0 )
  {
    v57 = 398;
LABEL_117:
    v56 = (unsigned int)Next;
    goto LABEL_69;
  }
  v16 = 0x7FFFFFFF;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        if ( !v89[1] )
        {
          StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v102);
          v73 = v92;
          v92 = 0;
          goto LABEL_143;
        }
        if ( (v104 & 0x21) != 0 )
        {
          v89[0] = 0;
          Next = StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
                   (struct StateRepository::Cache::Manager_NoThrow *)&v96,
                   v101,
                   v102[0],
                   v89);
          v8 = Next;
          if ( Next < 0 )
          {
            v57 = 407;
            goto LABEL_117;
          }
          if ( v89[0] )
            break;
        }
LABEL_115:
        Next = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::GetNext(&v92, 1853, v102, &v89[1]);
        v8 = Next;
        if ( Next < 0 )
        {
          v57 = 530;
          goto LABEL_117;
        }
      }
      *((_DWORD *)a4 + 137) = 0;
      hMem = 0;
      if ( v5 )
        break;
      if ( (int)PackagedCreateProcess::GetNewFilePathIfPresent(
                  *((PCWSTR *)a4 + 75),
                  *((_DWORD *)a4 + 157),
                  (__int64)&hMem) >= 0 )
        goto LABEL_27;
      v72 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::GetNext(&v92, 1853, v102, &v89[1]);
      v8 = v72;
      if ( v72 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A6,
          (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
          (const char *)(unsigned int)v72,
          (int)v84);
        if ( hMem )
          LocalFree(hMem);
LABEL_70:
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v102);
LABEL_65:
        v54 = v92;
        v92 = 0;
        if ( v54 )
          SRCacheContext_Close(v54);
        goto LABEL_6;
      }
      if ( hMem )
        LocalFree(hMem);
    }
    v17 = 0x7FFFFFFF;
    v18 = v5;
    do
    {
      if ( !*v18 )
        break;
      ++v18;
      --v17;
    }
    while ( v17 );
    v19 = 2 * (v18 - v5);
    v20 = (char *)LocalAlloc(0, v19 + 2);
    v21 = v20;
    if ( v20 )
    {
      memcpy_s(v20, v19 + 2, v5, v19);
      *(_WORD *)&v21[v19] = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &hMem,
      v21);
LABEL_27:
    v22 = (unsigned __int16 *)hMem;
    if ( !hMem )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AA,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)0x8007000ELL,
        (int)v84);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v102);
      v53 = v92;
      v92 = 0;
      goto LABEL_61;
    }
    MatchingAppUserModelIdIfPresent = PackagedCreateProcess::GetMatchingAppUserModelIdIfPresent(
                                        (const unsigned __int16 *)hMem,
                                        (const struct StateRepository::Cache::Entity::Package_NoThrow *)v102,
                                        v101,
                                        (struct StateRepository::Cache::Manager_NoThrow *)&v96,
                                        a4);
    WindowsPplTrustLabelSid = MatchingAppUserModelIdIfPresent;
    if ( MatchingAppUserModelIdIfPresent < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AC,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)(unsigned int)MatchingAppUserModelIdIfPresent,
        (int)v84);
      goto LABEL_87;
    }
    if ( !*((_DWORD *)a4 + 137) )
    {
      v97 = 0;
      LODWORD(v98) = 0;
      v99 = 0;
      v65 = StateRepository::Cache::Entity::DependencyGraphIndexIterator_NoThrow::OpenByUserAndDependentPackageAndDependencyType(
              &v97,
              &v96,
              v101,
              v102[0]);
      v66 = v65;
      if ( v65 >= 0 )
      {
        v114 = 0;
        v116 = 0;
        v115 = 0;
        v89[0] = 0;
        if ( !v97 )
          goto LABEL_169;
        Sourcea = 0;
        v81 = StateRepository::Cache::Context_NoThrow::EnumerateData(
                (StateRepository::Cache::Context_NoThrow *)&v97,
                v98,
                (__int64 *)&Sourcea);
        v66 = v81;
        if ( v81 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x17A,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DependencyGraph.hpp",
            (const char *)(unsigned int)v81,
            (int)v84);
          v83 = 402;
        }
        else
        {
          if ( !Sourcea
            || (v84 = v89,
                v66 = StateRepository::Cache::Entity::DependencyGraph_NoThrow::Get(v99, Sourcea, v82, &v114),
                v66 >= 0) )
          {
            while ( 1 )
            {
LABEL_169:
              if ( !v89[0] )
                goto LABEL_111;
              v84 = v89;
              v117 = 0;
              v123 = 0;
              v118 = 0;
              v120 = 0;
              v119 = 0;
              v121 = 0;
              v122 = 0;
              v124 = 0;
              v125 = 0;
              v126 = 0;
              v89[0] = 0;
              StateRepository::Cache::Entity::Package_NoThrow::Get(&v96, *((_QWORD *)&v115 + 1), 1853, &v117);
              if ( v89[0] )
              {
                v75 = PackagedCreateProcess::GetMatchingAppUserModelIdIfPresent(
                        v22,
                        (const struct StateRepository::Cache::Entity::Package_NoThrow *)&v117,
                        v101,
                        (struct StateRepository::Cache::Manager_NoThrow *)&v96,
                        a4);
                WindowsPplTrustLabelSid = v75;
                if ( v75 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x1C1,
                    (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
                    (const char *)(unsigned int)v75,
                    (int)v84);
                  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v117);
                  v76 = v97;
                  v97 = 0;
                  if ( v76 )
                    SRCacheContext_Close(v76);
                  goto LABEL_87;
                }
                if ( *((_DWORD *)a4 + 137) )
                  break;
              }
              v77 = v98 + 1;
              v89[0] = 0;
              LODWORD(v98) = v98 + 1;
              if ( v97 )
              {
                Sourcea = 0;
                v78 = StateRepository::Cache::Context_NoThrow::EnumerateData(
                        (StateRepository::Cache::Context_NoThrow *)&v97,
                        v77,
                        (__int64 *)&Sourcea);
                v66 = v78;
                if ( v78 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x17A,
                    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DependencyGraph.hpp",
                    (const char *)(unsigned int)v78,
                    (int)v84);
                  v80 = 402;
                  goto LABEL_190;
                }
                if ( Sourcea )
                {
                  v84 = v89;
                  v66 = StateRepository::Cache::Entity::DependencyGraph_NoThrow::Get(v99, Sourcea, v79, &v114);
                  if ( v66 < 0 )
                  {
                    v80 = 407;
LABEL_190:
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)v80,
                      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DependencyGraph.hpp",
                      (const char *)(unsigned int)v66,
                      (int)v84);
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x1C8,
                      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
                      (const char *)(unsigned int)v66,
                      v88);
                    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v117);
                    goto LABEL_104;
                  }
                }
              }
              StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v117);
            }
            StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v117);
LABEL_111:
            v70 = v97;
            v97 = 0;
            if ( v70 )
              SRCacheContext_Close(v70);
            if ( !*((_DWORD *)a4 + 137) )
            {
              LocalFree(v22);
              goto LABEL_115;
            }
            goto LABEL_30;
          }
          v83 = 407;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v83,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DependencyGraph.hpp",
          (const char *)(unsigned int)v66,
          (int)v84);
        v67 = 439;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x24A,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DependencyGraph.hpp",
          (const char *)(unsigned int)v65,
          (int)v84);
        v67 = 434;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v67,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)(unsigned int)v66,
        v86);
LABEL_104:
      v68 = v97;
      v97 = 0;
      if ( v68 )
        SRCacheContext_Close(v68);
      LocalFree(v22);
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v102);
      v69 = v92;
      v92 = 0;
      if ( v69 )
        SRCacheContext_Close(v69);
      v8 = v66;
      goto LABEL_6;
    }
LABEL_30:
    v25 = (const WCHAR *)*((_QWORD *)a4 + 75);
    v26 = (const WCHAR *)*((_QWORD *)a4 + 74);
    Sourcea = 0;
    v27 = PathAllocCombine(v26, v25, 1u, (unsigned __int16 **)&Sourcea);
    WindowsPplTrustLabelSid = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D1,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)(unsigned int)v27,
        (int)v84);
      if ( Sourcea )
        LocalFree(Sourcea);
      goto LABEL_87;
    }
    v29 = Sourcea;
    if ( !Sourcea )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v28);
    v30 = 0x7FFFFFFF;
    v31 = (char *)Sourcea;
    do
    {
      if ( !*(_WORD *)v31 )
        break;
      v31 += 2;
      --v30;
    }
    while ( v30 );
    v32 = 2 * ((v31 - (_BYTE *)Sourcea) >> 1);
    v33 = (WCHAR *)LocalAlloc(0, v32 + 2);
    v34 = v33;
    if ( !v33 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D3,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)0x8007000ELL,
        (int)v84);
      goto LABEL_72;
    }
    memcpy_s(v33, v32 + 2, v29, v32);
    v35 = 0x7FFFFFFF;
    v34[v32 / 2] = 0;
    v36 = v34;
    do
    {
      if ( !*v34 )
        break;
      ++v34;
      --v35;
    }
    while ( v35 );
    WindowsPplTrustLabelSid = v35 == 0 ? 0x80070057 : 0;
    if ( !v35 )
    {
      v59 = 469;
      goto LABEL_84;
    }
    WindowsPplTrustLabelSid = PathCchRemoveFileSpec(
                                v36,
                                (0x7FFFFFFF - v35) & ((unsigned __int128)-(__int128)(unsigned __int64)v35 >> 64));
    if ( WindowsPplTrustLabelSid < 0 )
    {
      v59 = 470;
LABEL_84:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v59,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)(unsigned int)WindowsPplTrustLabelSid,
        (int)v84);
      goto LABEL_85;
    }
    v37 = HIDWORD(v104);
    *((_BYTE *)a4 + 624) = BYTE4(v104) & 1;
    *((_BYTE *)a4 + 625) = (v37 & 0x800) != 0;
    v38 = (void *)v102[1];
    *((_BYTE *)a4 + 626) = (v37 & 0x400000) != 0;
    v39 = *((unsigned int *)a4 + 157);
    Sourcea = v38;
    if ( !(unsigned __int8)PackagedCreateProcess::IsTrustLabelAceSupported(v39) )
      goto LABEL_42;
    if ( !HIDWORD(v105) )
      break;
    if ( HIDWORD(v105) != 3 )
      goto LABEL_42;
    v91[0] = 0;
    Sid = 0;
    WindowsPplTrustLabelSid = TrustLabelAceHelpers::GetWindowsPplTrustLabelSid(&Sid);
    if ( WindowsPplTrustLabelSid < 0 )
    {
      v74 = 493;
      goto LABEL_147;
    }
    WindowsPplTrustLabelSid = TrustLabelAceHelpers::IsFileSystemObjectTrustable(
                                (const unsigned __int16 *)v29,
                                Sid,
                                0,
                                v58,
                                1,
                                v91);
    if ( WindowsPplTrustLabelSid < 0 )
    {
      v74 = 495;
LABEL_147:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v74,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)(unsigned int)WindowsPplTrustLabelSid,
        (int)v84);
      if ( Sid )
        RtlFreeSid(Sid);
LABEL_85:
      LocalFree(v36);
      if ( v29 )
        LocalFree(v29);
LABEL_87:
      LocalFree(v22);
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v102);
      v60 = v92;
      v92 = 0;
      if ( v60 )
        SRCacheContext_Close(v60);
      v8 = WindowsPplTrustLabelSid;
      goto LABEL_6;
    }
    if ( v91[0] )
    {
      if ( Sid )
        RtlFreeSid(Sid);
LABEL_42:
      *(_BYTE *)a4 = 1;
      if ( !v29 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xF89,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v40);
      v41 = (char *)v29;
      do
      {
        if ( !*(_WORD *)v41 )
          break;
        v41 += 2;
        --v16;
      }
      while ( v16 );
      v42 = 2 * ((v41 - (_BYTE *)v29) >> 1);
      v43 = (unsigned __int16 *)LocalAlloc(0, v42 + 2);
      v44 = v43;
      if ( v43 )
      {
        memcpy_s(v43, v42 + 2, v29, v42);
        v45 = 0;
        v44[v42 / 2] = 0;
        if ( *((_DWORD *)a4 + 137) != 1 )
        {
          v46 = Sourcea;
          v47 = (_WORD *)((char *)a4 + 262);
          v48 = 2147483646;
          v49 = 128;
          do
          {
            if ( !v48 )
              break;
            if ( !*v46 )
              break;
            *v47++ = *v46++;
            --v48;
            --v49;
          }
          while ( v49 );
          v50 = v47 - 1;
          v51 = v49 == 0 ? 0x8007007A : 0;
          if ( v49 )
            v50 = v47;
          *v50 = 0;
          if ( !v49 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x207,
              (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
              (const char *)(unsigned int)v51,
              (int)v84);
            goto LABEL_56;
          }
LABEL_97:
          v51 = ExtendedPackagedAppContext::SetFinalPath(a4, v44);
          if ( v51 < 0 )
          {
            v64 = 522;
            goto LABEL_99;
          }
          v51 = ExtendedPackagedAppContext::SetCurrentDirectoryW(a4, v36);
          if ( v51 < 0 )
          {
            v64 = 523;
          }
          else
          {
            v51 = ExtendedPackagedAppContext::SetPackageFamilyName(a4, a3);
            if ( v51 >= 0 )
            {
              if ( v44 )
                LocalFree(v44);
              LocalFree(v36);
              LocalFree(v29);
              goto LABEL_126;
            }
            v64 = 524;
          }
LABEL_99:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v64,
            (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
            (const char *)(unsigned int)v51,
            (int)v84);
          if ( v44 )
LABEL_56:
            LocalFree(v44);
          LocalFree(v36);
          LocalFree(v29);
          LocalFree(v22);
          StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v102);
          v52 = v92;
          v92 = 0;
          if ( v52 )
            SRCacheContext_Close(v52);
          v8 = v51;
          goto LABEL_6;
        }
        Sourcea = 0;
        hMem = 0;
        v61 = wil::GetSystemDirectoryW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(&Sourcea);
        v51 = v61;
        if ( v61 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x201,
            (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
            (const char *)(unsigned int)v61,
            (int)v84);
          if ( Sourcea )
            LocalFree(Sourcea);
          goto LABEL_56;
        }
        v62 = Sourcea;
        v63 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short *,unsigned short [23]>(
                &hMem,
                &Sourcea);
        v45 = v63;
        if ( v63 >= 0 )
        {
          v45 = 0;
          Sourcea = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &Sourcea,
            hMem);
          hMem = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &hMem,
            v44);
          if ( hMem )
            LocalFree(hMem);
          if ( v62 )
            LocalFree(v62);
          v44 = (unsigned __int16 *)Sourcea;
          goto LABEL_97;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x202,
          (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
          (const char *)(unsigned int)v63,
          (int)v84);
        if ( hMem )
          LocalFree(hMem);
        if ( v62 )
          LocalFree(v62);
        LocalFree(v44);
        LocalFree(v36);
        LocalFree(v29);
LABEL_126:
        LocalFree(v22);
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v102);
        v71 = v92;
        v92 = 0;
        if ( v71 )
          SRCacheContext_Close(v71);
        v8 = v45;
LABEL_6:
        wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(&v96, 0);
        return v8;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1FC,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)0x8007000ELL,
        (int)v84);
      LocalFree(v36);
LABEL_72:
      if ( v29 )
        LocalFree(v29);
      LocalFree(v22);
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v102);
      v53 = v92;
      v92 = 0;
LABEL_61:
      if ( v53 )
        SRCacheContext_Close(v53);
      v8 = -2147024882;
      goto LABEL_6;
    }
    WindowsPplTrustLabelSid = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::GetNext(
                                &v92,
                                1853,
                                v102,
                                &v89[1]);
    if ( WindowsPplTrustLabelSid < 0 )
    {
      v74 = 500;
      goto LABEL_147;
    }
    if ( Sid )
      RtlFreeSid(Sid);
    LocalFree(v36);
    if ( v29 )
      LocalFree(v29);
    LocalFree(v22);
    v5 = Source;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E6,
    (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
    (const char *)0x80070490LL,
    (int)v84);
  LocalFree(v36);
  if ( v29 )
    LocalFree(v29);
  LocalFree(v22);
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v102);
  v73 = v92;
  v92 = 0;
LABEL_143:
  if ( v73 )
    SRCacheContext_Close(v73);
  wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(&v96, 0);
  return 2147943568LL;
}

```

## disassembly

```asm
0x18000669c  mov     rax, rsp
0x18000669f  mov     [rax+10h], rbx
0x1800066a3  mov     [rax+18h], r8
0x1800066a7  mov     [rax+8], rcx
0x1800066ab  push    rbp
0x1800066ac  push    rsi
0x1800066ad  push    rdi
0x1800066ae  push    r12
0x1800066b0  push    r13
0x1800066b2  push    r14
0x1800066b4  push    r15
0x1800066b6  lea     rbp, [rax-0E8h]
0x1800066bd  sub     rsp, 1B0h
0x1800066c4  mov     rdi, rdx
0x1800066c7  mov     byte ptr [rbp+0E0h+var_160], 1
0x1800066cb  mov     r14, rcx
0x1800066ce  lea     rax, [rsp+1E0h+var_178]
0x1800066d3  xor     r15d, r15d
0x1800066d6  mov     [rsp+1E0h+var_170], rax
0x1800066db  lea     rdx, [rsp+1E0h+var_168]
0x1800066e0  mov     [rsp+1E0h+var_178], r15
0x1800066e5  xor     ecx, ecx
0x1800066e7  mov     [rsp+1E0h+var_168], r15
0x1800066ec  mov     r12, r9
0x1800066ef  mov     rsi, r8
0x1800066f2  call    cs:__imp_SRCacheManager_Open
0x1800066f9  nop     dword ptr [rax+rax+00h]
0x1800066fe  mov     ebx, eax
0x180006700  cmp     byte ptr [rbp+0E0h+var_160], r15b
0x180006704  jz      short loc_180006715
0x180006706  mov     rdx, [rsp+1E0h+var_168]
0x18000670b  mov     rcx, [rsp+1E0h+var_170]
0x180006710  call    ?reset@?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheManager@@@Z; wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(SRCacheManager *)
0x180006715  test    ebx, ebx
0x180006717  jns     short loc_180006779
0x180006719  mov     rcx, [rbp+0E8h]; this
0x180006720  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180006727  mov     r9d, ebx; char *
0x18000672a  mov     edx, 0A5h; void *
0x18000672f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006734  mov     r9d, ebx; char *
0x180006737  mov     edx, 177h; void *
0x18000673c  mov     rcx, [rbp+0E8h]; this
0x180006743  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x18000674a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000674f  xor     edx, edx
0x180006751  lea     rcx, [rsp+1E0h+var_178]
0x180006756  call    ?reset@?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@QEAAXPEAUSRCacheManager@@@Z; wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(SRCacheManager *)
0x18000675b  mov     eax, ebx
0x18000675d  mov     rbx, [rsp+1E0h+arg_8]
0x180006765  add     rsp, 1B0h
0x18000676c  pop     r15
0x18000676e  pop     r14
0x180006770  pop     r13
0x180006772  pop     r12
0x180006774  pop     rdi
0x180006775  pop     rsi
0x180006776  pop     rbp
0x180006777  retn
0x180006779  lea     r8, [rbp+0E0h+var_D0]; __int64 *
0x18000677d  mov     [rbp+0E0h+var_D0], r15
0x180006781  mov     rdx, rsi; unsigned __int16 *
0x180006784  lea     rcx, [rsp+1E0h+var_178]; struct StateRepository::Cache::Manager_NoThrow *
0x180006789  call    ?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18000678e  mov     ebx, eax
0x180006790  test    eax, eax
0x180006792  js      loc_1800072BF
0x180006798  mov     r8, [rbp+0E0h+var_D0]; __int64
0x18000679c  test    r8, r8
0x18000679f  jz      loc_1800071F1
0x1800067a5  lea     rdx, [rsp+1E0h+var_178]; struct StateRepository::Cache::Manager_NoThrow *
0x1800067aa  mov     [rsp+1E0h+var_198], r15
0x1800067af  lea     rcx, [rsp+1E0h+var_198]; this
0x1800067b4  mov     dword ptr [rsp+1E0h+var_190], r15d
0x1800067b9  mov     [rsp+1E0h+var_188], r15
0x1800067be  call    ?OpenByPackageFamily@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64)
0x1800067c3  mov     ebx, eax
0x1800067c5  test    eax, eax
0x1800067c7  js      loc_180006C53
0x1800067cd  mov     rcx, [rsp+1E0h+var_198]
0x1800067d2  xorps   xmm0, xmm0
0x1800067d5  movdqa  xmmword ptr [rbp+0E0h+var_140], xmm0
0x1800067da  mov     [rbp+0E0h+var_130], r15
0x1800067de  mov     [rbp+0E0h+var_128], r15
0x1800067e2  mov     [rbp+0E0h+var_120], r15
0x1800067e6  mov     [rbp+0E0h+var_118], r15
0x1800067ea  mov     [rbp+0E0h+var_110], r15
0x1800067ee  mov     [rbp+0E0h+var_108], r15
0x1800067f2  movdqa  [rbp+0E0h+var_100], xmm0
0x1800067f7  mov     [rbp+0E0h+var_F0], r15d
0x1800067fb  mov     [rbp+0E0h+var_E8], r15
0x1800067ff  mov     [rbp+0E0h+var_E0], r15
0x180006803  mov     [rsp+1E0h+var_1B0+1], r15b
0x180006808  test    rcx, rcx
0x18000680b  jz      short loc_180006863
0x18000680d  mov     edx, dword ptr [rsp+1E0h+var_190]
0x180006811  lea     r8, [rsp+1E0h+Source]
0x180006816  mov     [rsp+1E0h+Source], r15
0x18000681b  call    cs:__imp_SRCacheContext_EnumerateData
0x180006822  nop     dword ptr [rax+rax+00h]
0x180006827  mov     ebx, eax
0x180006829  test    eax, eax
0x18000682b  js      loc_18000742C
0x180006831  mov     rdx, [rsp+1E0h+Source]
0x180006836  test    rdx, rdx
0x180006839  jz      short loc_180006863
0x18000683b  mov     rcx, [rsp+1E0h+var_188]
0x180006840  lea     rax, [rsp+1E0h+var_1B0+1]
0x180006845  lea     r9, [rbp+0E0h+var_140]
0x180006849  mov     [rsp+1E0h+var_1C0], rax; int
0x18000684e  mov     r8d, 73Dh
0x180006854  call    ?Get@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180006859  mov     ebx, eax
0x18000685b  test    eax, eax
0x18000685d  js      loc_180006CAD
0x180006863  lea     r8, [rbp+0E0h+var_150]; __int64 *
0x180006867  mov     [rbp+0E0h+var_150], r15
0x18000686b  mov     rdx, rdi; void *
0x18000686e  lea     rcx, [rsp+1E0h+var_178]; struct StateRepository::Cache::Manager_NoThrow *
0x180006873  call    ?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x180006878  mov     ebx, eax
0x18000687a  test    eax, eax
0x18000687c  js      loc_1800072CC
0x180006882  mov     r13d, 7FFFFFFFh
0x180006888  cmp     [rsp+1E0h+var_1B0+1], r15b
0x18000688d  jz      loc_18000724C
0x180006893  test    byte ptr [rbp+0E0h+var_128], 21h
0x180006897  jz      loc_180007012
0x18000689d  mov     r8, [rbp+0E0h+var_140]; __int64
0x1800068a1  lea     r9, [rsp+1E0h+var_1B0]; bool *
0x1800068a6  mov     rdx, [rbp+0E0h+var_150]; __int64
0x1800068aa  lea     rcx, [rsp+1E0h+var_178]; struct StateRepository::Cache::Manager_NoThrow *
0x1800068af  mov     [rsp+1E0h+var_1B0], r15b
0x1800068b4  call    ?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z; StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)
0x1800068b9  mov     ebx, eax
0x1800068bb  test    eax, eax
0x1800068bd  js      loc_180007318
0x1800068c3  cmp     [rsp+1E0h+var_1B0], r15b
0x1800068c8  jz      loc_180007012
0x1800068ce  mov     [r12+224h], r15d
0x1800068d6  mov     [rsp+1E0h+hMem], r15
0x1800068db  test    r14, r14
0x1800068de  jz      loc_180007175
0x1800068e4  mov     rcx, r13
0x1800068e7  mov     rax, r14
0x1800068ea  cmp     [rax], r15w
0x1800068ee  jz      short loc_1800068FA
0x1800068f0  add     rax, 2
0x1800068f4  sub     rcx, 1
0x1800068f8  jnz     short loc_1800068EA
0x1800068fa  sub     rax, r14
0x1800068fd  xor     ecx, ecx; uFlags
0x1800068ff  sar     rax, 1
0x180006902  lea     rdi, [rax+rax]
0x180006906  lea     rdx, [rdi+2]; uBytes
0x18000690a  call    LocalAlloc
0x18000690f  mov     rbx, rax
0x180006912  test    rax, rax
0x180006915  jz      short loc_180006935
0x180006917  mov     r9, rdi; SourceSize
0x18000691a  lea     rdx, [rdi+2]; DestinationSize
0x18000691e  mov     r8, r14; Source
0x180006921  mov     rcx, rax; Destination
0x180006924  call    cs:__imp_memcpy_s
0x18000692b  nop     dword ptr [rax+rax+00h]
0x180006930  mov     [rbx+rdi], r15w
0x180006935  mov     rdx, rbx
0x180006938  lea     rcx, [rsp+1E0h+hMem]
0x18000693d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180006942  mov     rbx, [rsp+1E0h+hMem]
0x180006947  test    rbx, rbx
0x18000694a  jz      loc_180006BFD
0x180006950  mov     r8, [rbp+0E0h+var_150]; __int64
0x180006954  lea     r9, [rsp+1E0h+var_178]; struct StateRepository::Cache::Manager_NoThrow *
0x180006959  lea     rdx, [rbp+0E0h+var_140]; struct StateRepository::Cache::Entity::Package_NoThrow *
0x18000695d  mov     [rsp+1E0h+var_1C0], r12; int
0x180006962  mov     rcx, rbx; unsigned __int16 *
0x180006965  call    ?GetMatchingAppUserModelIdIfPresent@PackagedCreateProcess@@CAJPEBGAEBVPackage_NoThrow@Entity@Cache@StateRepository@@_JAEAVManager_NoThrow@45@PEAVExtendedPackagedAppContext@@@Z; PackagedCreateProcess::GetMatchingAppUserModelIdIfPresent(ushort const *,StateRepository::Cache::Entity::Package_NoThrow const &,__int64,StateRepository::Cache::Manager_NoThrow &,ExtendedPackagedAppContext *)
0x18000696a  mov     edi, eax
0x18000696c  test    eax, eax
0x18000696e  js      loc_1800072F8
0x180006974  cmp     [r12+224h], r15d
0x18000697c  jz      loc_180006F17
0x180006982  mov     rdx, [r12+258h]; pszMore
0x18000698a  lea     r9, [rsp+1E0h+Source]; unsigned __int16 **
0x18000698f  mov     rcx, [r12+250h]; pszPathIn
0x180006997  mov     r8d, 1; dwFlags
0x18000699d  mov     [rsp+1E0h+Source], r15
0x1800069a2  call    ?PathAllocCombine@@YAJPEBG0W4PATHCCH_OPTIONS@@PEAPEAG@Z; PathAllocCombine(ushort const *,ushort const *,PATHCCH_OPTIONS,ushort * *)
0x1800069a7  mov     rcx, [rbp+0E8h]; this
0x1800069ae  mov     edi, eax
0x1800069b0  test    eax, eax
0x1800069b2  js      loc_180007041
0x1800069b8  mov     r15, [rsp+1E0h+Source]
0x1800069bd  xor     edx, edx
0x1800069bf  test    r15, r15
0x1800069c2  jz      loc_180007615
0x1800069c8  mov     rcx, r13
0x1800069cb  mov     rax, r15
0x1800069ce  cmp     [rax], dx
0x1800069d1  jz      short loc_1800069DD
0x1800069d3  add     rax, 2
0x1800069d7  sub     rcx, 1
0x1800069db  jnz     short loc_1800069CE
0x1800069dd  sub     rax, r15
0x1800069e0  xor     ecx, ecx; uFlags
0x1800069e2  sar     rax, 1
0x1800069e5  lea     rsi, [rax+rax]
0x1800069e9  lea     rdx, [rsi+2]; uBytes
0x1800069ed  call    LocalAlloc
0x1800069f2  mov     rdi, rax
0x1800069f5  test    rax, rax
0x1800069f8  jz      loc_180006CF1
0x1800069fe  mov     r9, rsi; SourceSize
0x180006a01  lea     rdx, [rsi+2]; DestinationSize
0x180006a05  mov     r8, r15; Source
0x180006a08  mov     rcx, rax; Destination
0x180006a0b  call    cs:__imp_memcpy_s
0x180006a12  nop     dword ptr [rax+rax+00h]
0x180006a17  xor     r14d, r14d
0x180006a1a  mov     r8, r13
0x180006a1d  mov     [rdi+rsi], r14w
0x180006a22  mov     rsi, rdi
0x180006a25  cmp     [rdi], r14w
0x180006a29  jz      short loc_180006A35
0x180006a2b  add     rdi, 2
0x180006a2f  sub     r8, 1
0x180006a33  jnz     short loc_180006A25
0x180006a35  mov     rax, r8
0x180006a38  mov     rcx, r13
0x180006a3b  neg     rax
0x180006a3e  mov     rax, r8
0x180006a41  sbb     edi, edi
0x180006a43  sub     rcx, r8
0x180006a46  not     edi
0x180006a48  and     edi, 80070057h
0x180006a4e  neg     rax
0x180006a51  sbb     rdx, rdx
0x180006a54  and     rdx, rcx; cchPath
0x180006a57  test    r8, r8
0x180006a5a  jz      loc_18000760B
0x180006a60  mov     rcx, rsi; pszPath
0x180006a63  call    PathCchRemoveFileSpec
0x180006a68  mov     edi, eax
0x180006a6a  test    eax, eax
0x180006a6c  js      loc_180006DEA
0x180006a72  mov     al, byte ptr [rbp+0E0h+var_128+4]
0x180006a75  mov     ecx, dword ptr [rbp+0E0h+var_128+4]
0x180006a78  and     al, 1
0x180006a7a  mov     [r12+270h], al
0x180006a82  mov     eax, ecx
0x180006a84  shr     eax, 0Bh
0x180006a87  shr     ecx, 16h
0x180006a8a  and     al, 1
0x180006a8c  and     cl, 1
0x180006a8f  mov     [r12+271h], al
0x180006a97  mov     rax, [rbp+0E0h+var_140+8]
0x180006a9b  mov     [r12+272h], cl
0x180006aa3  mov     ecx, [r12+274h]
0x180006aab  mov     [rsp+1E0h+Source], rax
0x180006ab0  call    ?IsTrustLabelAceSupported@PackagedCreateProcess@@CA_NW4PackagePathType@@@Z; PackagedCreateProcess::IsTrustLabelAceSupported(PackagePathType)
0x180006ab5  test    al, al
0x180006ab7  jnz     loc_180006D3E
0x180006abd  mov     byte ptr [r12], 1
0x180006ac2  test    r15, r15
0x180006ac5  jz      loc_1800075F2
0x180006acb  mov     rax, r15
0x180006ace  cmp     [rax], r14w
0x180006ad2  jz      short loc_180006ADE
0x180006ad4  add     rax, 2
0x180006ad8  sub     r13, 1
0x180006adc  jnz     short loc_180006ACE
0x180006ade  sub     rax, r15
0x180006ae1  xor     ecx, ecx; uFlags
0x180006ae3  sar     rax, 1
0x180006ae6  lea     r14, [rax+rax]
0x180006aea  lea     rdx, [r14+2]; uBytes
0x180006aee  call    LocalAlloc
0x180006af3  mov     rdi, rax
0x180006af6  test    rax, rax
0x180006af9  jz      loc_180006DBF
0x180006aff  mov     r9, r14; SourceSize
0x180006b02  lea     rdx, [r14+2]; DestinationSize
0x180006b06  mov     r8, r15; Source
0x180006b09  mov     rcx, rax; Destination
0x180006b0c  call    cs:__imp_memcpy_s
0x180006b13  nop     dword ptr [rax+rax+00h]
0x180006b18  xor     r13d, r13d
0x180006b1b  mov     [rdi+r14], r13w
0x180006b20  cmp     dword ptr [r12+224h], 1
0x180006b29  jz      loc_180006E4F
0x180006b2f  mov     r9, [rsp+1E0h+Source]
0x180006b34  lea     r8, [r12+106h]
0x180006b3c  mov     eax, 7FFFFFFEh
0x180006b41  mov     edx, 80h
0x180006b46  test    rax, rax
0x180006b49  jz      short loc_180006B69
0x180006b4b  movzx   ecx, word ptr [r9]
0x180006b4f  test    cx, cx
0x180006b52  jz      short loc_180006B69
  ... truncated ...
```
