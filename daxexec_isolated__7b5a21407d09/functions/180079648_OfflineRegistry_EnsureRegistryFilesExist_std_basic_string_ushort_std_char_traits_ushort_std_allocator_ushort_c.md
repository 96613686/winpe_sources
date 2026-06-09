# OfflineRegistry::EnsureRegistryFilesExist(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::filesystem::path const &,void *,std::vector<std::unique_ptr<PackageInformation,std::default_delete<PackageInformation>>,std::allocator<std::unique_ptr<PackageInformation,std::default_delete<PackageInformation>>>> const &,bool)

- ea: `0x180079648`
- end: `0x180079fed`
- name: `?EnsureRegistryFilesExist@OfflineRegistry@@YA?AUHivePaths@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVpath@filesystem@4@PEAXAEBV?$vector@V?$unique_ptr@VPackageInformation@@U?$default_delete@VPackageInformation@@@std@@@std@@V?$allocator@V?$unique_ptr@VPackageInformation@@U?$default_delete@VPackageInformation@@@std@@@std@@@2@@4@_N@Z`
- size: `2469`
- prototype: `const wchar_t *__fastcall(const wchar_t *, unsigned __int16 *, void *, __int64, __int64 *, char)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007161c`

## callees

- `0x180004f70`
- `0x1800057fc`
- `0x180012fb8`
- `0x180013320`
- `0x180013490`
- `0x180013510`
- `0x1800136dc`
- `0x180014e74`
- `0x180014ebc`
- `0x18001544c`
- `0x1800164f8`
- `0x180016b98`
- `0x180016da0`
- `0x1800190e0`
- `0x18001f808`
- `0x180022044`
- `0x180024778`
- `0x180024924`
- `0x1800281a0`
- `0x18002bab4`
- `0x18002d978`
- `0x18005cf20`
- `0x18005d0b8`
- `0x180061318`
- `0x180079238`
- `0x180079648`
- `0x18007a650`
- `0x18007b3b0`
- `0x18007bcf8`
- `0x1800a3e44`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079ee3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180079ee3`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x18007977f`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x18007977f`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800797cf`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800797cf`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18007976d`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18007976d`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800797df`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800797df`

## string_xrefs

- `0x180079f99`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x180079fc6`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x180079fdb`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18007968d`: `\registry`
- `0x180079b61`: `BuildRegistryCache`
- `0x180079929`: `_COM15.dat`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
const wchar_t *__fastcall OfflineRegistry::EnsureRegistryFilesExist(
        const wchar_t *a1,
        unsigned __int16 *a2,
        void *a3,
        __int64 a4,
        __int64 *a5,
        char a6)
{
  __int64 v10; // rdi
  __int64 i; // r8
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  unsigned __int64 v14; // r9
  unsigned __int64 v15; // r10
  unsigned __int16 *v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  _QWORD *v22; // r9
  __int64 v23; // rdx
  __int64 v24; // r8
  _QWORD *v25; // r9
  __int64 v26; // rdx
  __int64 v27; // r8
  _QWORD *v28; // r9
  __int64 v29; // rdx
  __int64 v30; // r8
  _QWORD *v31; // r9
  __int64 v32; // rax
  __int64 v33; // rax
  const unsigned __int16 *v34; // rcx
  const unsigned __int16 *v35; // rcx
  char v36; // bl
  const unsigned __int16 *v37; // rcx
  char v38; // al
  const unsigned __int16 *v39; // rdi
  unsigned __int16 **v40; // rdx
  unsigned int v41; // eax
  unsigned __int16 **v42; // rdx
  unsigned int v43; // eax
  unsigned __int16 **v44; // rdx
  unsigned int v45; // eax
  const unsigned __int16 *v46; // rcx
  char v47; // bl
  const unsigned __int16 *v48; // rcx
  char v49; // al
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // r9
  void *v53; // rcx
  unsigned int v55; // [rsp+20h] [rbp-E0h]
  unsigned int v56; // [rsp+20h] [rbp-E0h]
  unsigned int v57; // [rsp+20h] [rbp-E0h]
  int v58; // [rsp+28h] [rbp-D8h]
  int v59; // [rsp+28h] [rbp-D8h]
  int v60; // [rsp+28h] [rbp-D8h]
  __int64 v61; // [rsp+58h] [rbp-A8h] BYREF
  int v62; // [rsp+60h] [rbp-A0h]
  HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  void *Block; // [rsp+78h] [rbp-88h]
  char v65[16]; // [rsp+88h] [rbp-78h] BYREF
  char v66[16]; // [rsp+98h] [rbp-68h] BYREF
  char v67; // [rsp+A8h] [rbp-58h]
  __int128 v68; // [rsp+B0h] [rbp-50h] BYREF
  int v69; // [rsp+C0h] [rbp-40h]
  int v70; // [rsp+CCh] [rbp-34h]
  _QWORD v71[2]; // [rsp+D0h] [rbp-30h] BYREF
  char v72[8]; // [rsp+E0h] [rbp-20h] BYREF
  char v73[8]; // [rsp+E8h] [rbp-18h] BYREF
  char v74[120]; // [rsp+F0h] [rbp-10h] BYREF
  char v75[104]; // [rsp+168h] [rbp+68h] BYREF
  _QWORD v76[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v77; // [rsp+1E0h] [rbp+E0h]
  unsigned __int64 v78; // [rsp+1E8h] [rbp+E8h]
  unsigned __int16 *v79[3]; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int64 v80; // [rsp+208h] [rbp+108h]
  unsigned __int16 *v81[3]; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int64 v82; // [rsp+228h] [rbp+128h]
  const wchar_t *v83; // [rsp+230h] [rbp+130h] BYREF
  __int64 v84; // [rsp+238h] [rbp+138h]
  unsigned __int16 *v85[3]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int64 v86; // [rsp+268h] [rbp+168h]
  _OWORD v87[2]; // [rsp+270h] [rbp+170h] BYREF
  _OWORD v88[2]; // [rsp+290h] [rbp+190h] BYREF
  __int128 v89; // [rsp+2B0h] [rbp+1B0h] BYREF
  __m128i si128; // [rsp+2C0h] [rbp+1C0h]
  _BYTE v91[32]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _BYTE v92[32]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE Src[32]; // [rsp+310h] [rbp+210h] BYREF
  _QWORD v94[2]; // [rsp+330h] [rbp+230h] BYREF
  char v95[32]; // [rsp+340h] [rbp+240h] BYREF
  unsigned int v96; // [rsp+360h] [rbp+260h]
  _QWORD v97[2]; // [rsp+368h] [rbp+268h] BYREF
  char v98[32]; // [rsp+378h] [rbp+278h] BYREF
  _QWORD v99[2]; // [rsp+398h] [rbp+298h] BYREF
  char v100[32]; // [rsp+3A8h] [rbp+2A8h] BYREF
  unsigned int v101; // [rsp+3C8h] [rbp+2C8h]
  _QWORD v102[2]; // [rsp+3D0h] [rbp+2D0h] BYREF
  char v103[32]; // [rsp+3E0h] [rbp+2E0h] BYREF
  unsigned int v104; // [rsp+400h] [rbp+300h]
  _QWORD v105[42]; // [rsp+410h] [rbp+310h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5A8h] [rbp+4A8h]

  v83 = a1;
  v68 = *(_OWORD *)L"\\registry";
  v69 = *(_DWORD *)L"y";
  v61 = *(_QWORD *)L"\\user";
  v62 = *(_DWORD *)L"r";
  v87[0] = *(_OWORD *)L"\\userclasses";
  *(_OWORD *)((char *)v87 + 10) = *(_OWORD *)L"classes";
  v10 = 0;
  for ( i = *a5; i != a5[1]; i += 8 )
  {
    v12 = (_QWORD *)(*(_QWORD *)i + 8LL);
    if ( *(_QWORD *)(*(_QWORD *)i + 32LL) > 7u )
      v12 = (_QWORD *)*v12;
    v13 = 0xCBF29CE484222325uLL;
    v14 = 0;
    v15 = 2LL * *(_QWORD *)(*(_QWORD *)i + 24LL);
    if ( v15 )
    {
      do
        v13 = 0x100000001B3LL * (*((unsigned __int8 *)v12 + v14++) ^ (unsigned __int64)v13);
      while ( v14 < v15 );
    }
    v10 ^= v13;
  }
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v71);
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v16 = a2;
  else
    v16 = *(unsigned __int16 **)a2;
  v17 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(
          v72,
          v16,
          *((_QWORD *)a2 + 2));
  v18 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v17, L"\\");
  v19 = std::basic_ostream<unsigned short>::operator<<(v18, std::hex);
  std::basic_ostream<unsigned short>::operator<<(v19, v10);
  std::basic_stringbuf<unsigned short>::str(v73, v76);
  *(_QWORD *)((char *)v71 + *(int *)(v71[0] + 4LL)) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
  *(int *)((char *)&v70 + *(int *)(v71[0] + 4LL)) = *(_DWORD *)(v71[0] + 4LL) - 152;
  std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v73);
  std::basic_iostream<unsigned short>::~basic_iostream<unsigned short,std::char_traits<unsigned short>>(v74);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v75);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v77) < 4 )
    std::_Xlen_string();
  v22 = v76;
  if ( v78 > 7 )
    v22 = (_QWORD *)v76[0];
  std::wstring::wstring(v85, v20, v21, v22, v77, L".dat", 4);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v77) < 9 )
    std::_Xlen_string();
  v25 = v76;
  if ( v78 > 7 )
    v25 = (_QWORD *)v76[0];
  std::wstring::wstring(v81, v23, v24, v25, v77, L"_user.dat", 9);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v77) < 0x10 )
    std::_Xlen_string();
  v28 = v76;
  if ( v78 > 7 )
    v28 = (_QWORD *)v76[0];
  std::wstring::wstring(v79, v26, v27, v28, v77, L"_userclasses.dat", 16);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v77) < 0xA )
    std::_Xlen_string();
  v31 = v76;
  if ( v78 > 7 )
    v31 = (_QWORD *)v76[0];
  std::wstring::wstring(v92, v29, v30, v31, v77, L"_COM15.dat", 10);
  v89 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v89) = 0;
  v88[0] = 0;
  v88[1] = si128;
  LOWORD(v88[0]) = 0;
  if ( a6 )
  {
    v83 = L"User.dat";
    v84 = 8;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v91, &v83);
    v32 = std::filesystem::operator/(Src, a3, (std::filesystem *)v91);
    std::wstring::wstring(&v83, v32);
    std::wstring::operator=(&v89, &v83);
    std::wstring::~wstring(&v83);
    std::wstring::~wstring(Src);
    std::wstring::~wstring(v91);
    v83 = L"UserClasses.dat";
    v84 = 15;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v91, &v83);
    v33 = std::filesystem::operator/(v97, a3, (std::filesystem *)v91);
    std::wstring::wstring(Src, v33);
    std::wstring::operator=(v88, Src);
    std::wstring::~wstring(Src);
    std::wstring::~wstring(v97);
    std::wstring::~wstring(v91);
  }
  v34 = (const unsigned __int16 *)v85;
  if ( v86 > 7 )
    v34 = v85[0];
  if ( FileExists(v34) )
  {
    v35 = (const unsigned __int16 *)v79;
    if ( v80 > 7 )
      v35 = v79[0];
    v36 = FileExists(v35);
    v37 = (const unsigned __int16 *)v81;
    if ( v82 > 7 )
      v37 = v81[0];
    v38 = FileExists(v37);
    OfflineRegistry::HivePaths::Create(
      (_DWORD)a1,
      (unsigned int)v85,
      (unsigned int)v92,
      (unsigned int)v81,
      (__int64)v79,
      v38,
      v36,
      (__int64)&v89,
      (__int64)v88);
  }
  else
  {
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v39 = a2;
    else
      v39 = *(const unsigned __int16 **)a2;
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v105,
      "BuildRegistryCache");
    v105[0] = &DesktopAppXProvider::BuildRegistryCache::`vftable';
    DesktopAppXProvider::BuildRegistryCache::StartActivity((DesktopAppXProvider::BuildRegistryCache *)v105, v39);
    OfflineRegistry::ClearCache((Common *)a2, (unsigned __int16 *)v85, (unsigned __int16 *)v81, (unsigned __int16 *)v79);
    v67 = 0;
    OfflineRegistry::Hive::Create(v102, 1);
    LOBYTE(v58) = 1;
    if ( (unsigned int)OfflineRegistry::MergeHives(&v61, a4, &hObject, a5, v102, v58) )
    {
      v40 = v81;
      if ( v82 > 7 )
        LODWORD(v40) = v81[0];
      v41 = ORSaveHiveEx(v102[0], (_DWORD)v40, 10, 0, v104);
      if ( v41 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x203,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
          (const char *)v41,
          v55);
    }
    OfflineRegistry::Hive::Create(v99, 1);
    LOBYTE(v59) = 1;
    if ( (unsigned int)OfflineRegistry::MergeHives(v87, a4, &hObject, a5, v99, v59) )
    {
      v42 = v79;
      if ( v80 > 7 )
        LODWORD(v42) = v79[0];
      v43 = ORSaveHiveEx(v99[0], (_DWORD)v42, 10, 0, v101);
      if ( v43 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x203,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
          (const char *)v43,
          v56);
    }
    OfflineRegistry::Hive::Create(v94, 1);
    memset(v87, 0, sizeof(v87));
    std::wstring::_Construct<1,unsigned short const *>(v87, L"Classes", 7);
    OfflineRegistry::Key::CreateSubKeys(v94, v97, v87);
    std::wstring::~wstring(v98);
    if ( v97[0] )
      ((void (*)(void))v97[1])();
    std::wstring::~wstring(v87);
    LOBYTE(v60) = 0;
    OfflineRegistry::MergeHives(&v68, a4, &hObject, a5, v94, v60);
    v44 = v85;
    if ( v86 > 7 )
      LODWORD(v44) = v85[0];
    v45 = ORSaveHiveEx(v94[0], (_DWORD)v44, 10, 0, v96);
    if ( v45 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x203,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
        (const char *)v45,
        v57);
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v105, 0);
    v46 = (const unsigned __int16 *)v79;
    if ( v80 > 7 )
      v46 = v79[0];
    v47 = FileExists(v46);
    v48 = (const unsigned __int16 *)v81;
    if ( v82 > 7 )
      v48 = v81[0];
    v49 = FileExists(v48);
    OfflineRegistry::HivePaths::Create(
      (_DWORD)a1,
      (unsigned int)v85,
      (unsigned int)v92,
      (unsigned int)v81,
      (__int64)v79,
      v49,
      v47,
      (__int64)&v89,
      (__int64)v88);
    std::wstring::~wstring(v95);
    if ( v94[0] )
      ((void (*)(void))v94[1])();
    std::wstring::~wstring(v100);
    if ( v99[0] )
      ((void (*)(void))v99[1])();
    std::wstring::~wstring(v103);
    if ( v102[0] )
      ((void (*)(void))v102[1])();
    if ( v67 )
    {
      std::_Tree<std::_Tmap_traits<std::wstring,TokenMap::TokenMapValue,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,TokenMap::TokenMapValue>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,TokenMap::TokenMapValue,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,TokenMap::TokenMapValue>>,0>>(v66);
      std::_Tree<std::_Tmap_traits<std::wstring,TokenMap::TokenMapValue,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,TokenMap::TokenMapValue>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,TokenMap::TokenMapValue,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,TokenMap::TokenMapValue>>,0>>(v65);
      v53 = Block;
      Block = 0;
      if ( v53 )
        operator delete(v53);
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
    }
    v105[0] = &DesktopAppXProvider::BuildRegistryCache::`vftable';
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v105, v50, v51, v52);
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v105);
  }
  std::wstring::~wstring(v88);
  std::wstring::~wstring(&v89);
  std::wstring::~wstring(v92);
  std::wstring::~wstring(v79);
  std::wstring::~wstring(v81);
  std::wstring::~wstring(v85);
  std::wstring::~wstring(v76);
  return a1;
}

```

## disassembly

```asm
0x180079648  push    rbp
0x18007964a  push    rbx
0x18007964b  push    rsi
0x18007964c  push    rdi
0x18007964d  push    r12
0x18007964f  push    r14
0x180079651  push    r15
0x180079653  lea     rbp, [rsp-470h]
0x18007965b  sub     rsp, 570h
0x180079662  mov     rax, cs:__security_cookie
0x180079669  xor     rax, rsp
0x18007966c  mov     [rbp+4A0h+var_40], rax
0x180079673  mov     r15, r9
0x180079676  mov     r12, r8
0x180079679  mov     rbx, rdx
0x18007967c  mov     rsi, rcx
0x18007967f  mov     [rbp+4A0h+var_370], rcx
0x180079686  mov     r14, [rbp+4A0h+arg_20]
0x18007968d  movups  xmm0, xmmword ptr cs:aRegistry_0; "\\registry"
0x180079694  movups  [rbp+4A0h+var_4F0], xmm0
0x180079698  mov     eax, dword ptr cs:aRegistry_0+10h; "y"
0x18007969e  mov     [rbp+4A0h+var_4E0], eax
0x1800796a1  movsd   xmm0, qword ptr cs:aUser_0; "\\user"
0x1800796a9  movsd   [rsp+5A0h+var_548], xmm0
0x1800796af  mov     eax, dword ptr cs:aUser_0+8; "r"
0x1800796b5  mov     [rsp+5A0h+var_540], eax
0x1800796b9  movups  xmm0, xmmword ptr cs:aUserclasses; "\\userclasses"
0x1800796c0  movups  [rbp+4A0h+var_330], xmm0
0x1800796c7  movups  xmm1, xmmword ptr cs:aUserclasses+0Ah; "classes"
0x1800796ce  movups  [rbp+4A0h+var_330+0Ah], xmm1
0x1800796d5  xor     edi, edi
0x1800796d7  mov     r8, [r14]
0x1800796da  jmp     short loc_180079728
0x1800796dc  mov     rcx, [r8]
0x1800796df  add     rcx, 8
0x1800796e3  mov     r10, [rcx+10h]
0x1800796e7  cmp     qword ptr [rcx+18h], 7
0x1800796ec  jbe     short loc_1800796F1
0x1800796ee  mov     rcx, [rcx]
0x1800796f1  mov     rdx, 0CBF29CE484222325h
0x1800796fb  xor     r9d, r9d
0x1800796fe  add     r10, r10
0x180079701  jz      short loc_180079721
0x180079703  movzx   eax, byte ptr [rcx+r9]
0x180079708  xor     rdx, rax
0x18007970b  mov     r11, 100000001B3h
0x180079715  imul    rdx, r11
0x180079719  inc     r9
0x18007971c  cmp     r9, r10
0x18007971f  jb      short loc_180079703
0x180079721  xor     rdi, rdx
0x180079724  add     r8, 8
0x180079728  cmp     r8, [r14+8]
0x18007972c  jnz     short loc_1800796DC
0x18007972e  lea     rcx, [rbp+4A0h+var_4D0]
0x180079732  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180079737  nop
0x180079738  cmp     qword ptr [rbx+18h], 7
0x18007973d  jbe     short loc_180079744
0x18007973f  mov     rdx, [rbx]
0x180079742  jmp     short loc_180079747
0x180079744  mov     rdx, rbx
0x180079747  mov     r8, [rbx+10h]
0x18007974b  lea     rcx, [rbp+4A0h+var_4C0]
0x18007974f  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x180079754  lea     rdx, S; "\\"
0x18007975b  mov     rcx, rax
0x18007975e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180079763  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18007976a  mov     rcx, rax
0x18007976d  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x180079774  nop     dword ptr [rax+rax+00h]
0x180079779  mov     rdx, rdi
0x18007977c  mov     rcx, rax
0x18007977f  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z; std::basic_ostream<ushort>::operator<<(unsigned __int64)
0x180079786  nop     dword ptr [rax+rax+00h]
0x18007978b  lea     rdx, [rbp+4A0h+var_3D0]
0x180079792  lea     rcx, [rbp+4A0h+var_4B8]
0x180079796  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18007979b  nop
0x18007979c  mov     rax, [rbp+4A0h+var_4D0]
0x1800797a0  movsxd  rcx, dword ptr [rax+4]
0x1800797a4  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x1800797ab  mov     [rbp+rcx+4A0h+var_4D0], rax
0x1800797b0  mov     rax, [rbp+4A0h+var_4D0]
0x1800797b4  movsxd  rcx, dword ptr [rax+4]
0x1800797b8  lea     edx, [rcx-98h]
0x1800797be  mov     [rbp+rcx+4A0h+var_4D4], edx
0x1800797c2  lea     rcx, [rbp+4A0h+var_4B8]
0x1800797c6  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x1800797cb  lea     rcx, [rbp+4A0h+var_4B0]
0x1800797cf  call    cs:__imp_??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_iostream<ushort>::~basic_iostream<ushort,std::char_traits<ushort>>(void)
0x1800797d6  nop     dword ptr [rax+rax+00h]
0x1800797db  lea     rcx, [rbp+4A0h+var_438]
0x1800797df  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x1800797e6  nop     dword ptr [rax+rax+00h]
0x1800797eb  nop
0x1800797ec  mov     rcx, [rbp+4A0h+var_3C0]
0x1800797f3  mov     rdi, 7FFFFFFFFFFFFFFEh
0x1800797fd  mov     rax, rdi
0x180079800  sub     rax, rcx
0x180079803  cmp     rax, 4
0x180079807  jb      loc_180079FAB
0x18007980d  lea     r9, [rbp+4A0h+var_3D0]
0x180079814  cmp     [rbp+4A0h+var_3B8], 7
0x18007981c  cmova   r9, [rbp+4A0h+var_3D0]
0x180079824  mov     [rsp+5A0h+var_570], 4
0x18007982d  lea     rax, aDat_0; ".dat"
0x180079834  mov     [rsp+5A0h+var_578], rax
0x180079839  mov     qword ptr [rsp+5A0h+var_580], rcx
0x18007983e  lea     rcx, [rbp+4A0h+var_350]
0x180079845  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18007984a  nop
0x18007984b  mov     rcx, [rbp+4A0h+var_3C0]
0x180079852  mov     rax, rdi
0x180079855  sub     rax, rcx
0x180079858  cmp     rax, 9
0x18007985c  jb      loc_180079FB1
0x180079862  lea     r9, [rbp+4A0h+var_3D0]
0x180079869  cmp     [rbp+4A0h+var_3B8], 7
0x180079871  cmova   r9, [rbp+4A0h+var_3D0]
0x180079879  mov     [rsp+5A0h+var_570], 9
0x180079882  lea     rax, aUserDat; "_user.dat"
0x180079889  mov     [rsp+5A0h+var_578], rax
0x18007988e  mov     qword ptr [rsp+5A0h+var_580], rcx
0x180079893  lea     rcx, [rbp+4A0h+var_390]
0x18007989a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18007989f  nop
0x1800798a0  mov     rcx, [rbp+4A0h+var_3C0]
0x1800798a7  mov     rax, rdi
0x1800798aa  sub     rax, rcx
0x1800798ad  cmp     rax, 10h
0x1800798b1  jb      loc_180079FB7
0x1800798b7  lea     r9, [rbp+4A0h+var_3D0]
0x1800798be  cmp     [rbp+4A0h+var_3B8], 7
0x1800798c6  cmova   r9, [rbp+4A0h+var_3D0]
0x1800798ce  mov     [rsp+5A0h+var_570], 10h
0x1800798d7  lea     rax, aUserclassesDat; "_userclasses.dat"
0x1800798de  mov     [rsp+5A0h+var_578], rax
0x1800798e3  mov     qword ptr [rsp+5A0h+var_580], rcx
0x1800798e8  lea     rcx, [rbp+4A0h+var_3B0]
0x1800798ef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800798f4  nop
0x1800798f5  mov     rax, [rbp+4A0h+var_3C0]
0x1800798fc  sub     rdi, rax
0x1800798ff  cmp     rdi, 0Ah
0x180079903  jb      loc_180079FBD
0x180079909  lea     r9, [rbp+4A0h+var_3D0]
0x180079910  cmp     [rbp+4A0h+var_3B8], 7
0x180079918  cmova   r9, [rbp+4A0h+var_3D0]
0x180079920  mov     [rsp+5A0h+var_570], 0Ah
0x180079929  lea     rcx, aCom15Dat; "_COM15.dat"
0x180079930  mov     [rsp+5A0h+var_578], rcx
0x180079935  mov     qword ptr [rsp+5A0h+var_580], rax
0x18007993a  lea     rcx, [rbp+4A0h+var_2B0]
0x180079941  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180079946  nop
0x180079947  xorps   xmm0, xmm0
0x18007994a  movups  [rbp+4A0h+var_2F0], xmm0
0x180079951  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180079959  movdqu  [rbp+4A0h+var_2E0], xmm1
0x180079961  xor     eax, eax
0x180079963  mov     word ptr [rbp+4A0h+var_2F0], ax
0x18007996a  movups  [rbp+4A0h+var_310], xmm0
0x180079971  movdqu  [rbp+4A0h+var_300], xmm1
0x180079979  mov     word ptr [rbp+4A0h+var_310], ax
0x180079980  cmp     [rbp+4A0h+arg_28], al
0x180079986  jz      loc_180079AA4
0x18007998c  lea     rax, aUserDat_0; "User.dat"
0x180079993  mov     [rbp+4A0h+var_370], rax
0x18007999a  mov     [rbp+4A0h+var_368], 8
0x1800799a5  lea     rdx, [rbp+4A0h+var_370]
0x1800799ac  lea     rcx, [rbp+4A0h+var_2D0]
0x1800799b3  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x1800799b8  nop
0x1800799b9  lea     r8, [rbp+4A0h+var_2D0]; this
0x1800799c0  mov     rdx, r12; void *
0x1800799c3  lea     rcx, [rbp+4A0h+Src]; Src
0x1800799ca  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x1800799cf  nop
0x1800799d0  mov     rdx, rax
0x1800799d3  lea     rcx, [rbp+4A0h+var_370]
0x1800799da  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800799df  lea     rdx, [rbp+4A0h+var_370]
0x1800799e6  lea     rcx, [rbp+4A0h+var_2F0]
0x1800799ed  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800799f2  lea     rcx, [rbp+4A0h+var_370]; void *
0x1800799f9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800799fe  nop
0x1800799ff  lea     rcx, [rbp+4A0h+Src]; void *
0x180079a06  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180079a0b  nop
0x180079a0c  lea     rcx, [rbp+4A0h+var_2D0]; void *
0x180079a13  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180079a18  lea     rax, aUserclassesDat_0; "UserClasses.dat"
0x180079a1f  mov     [rbp+4A0h+var_370], rax
0x180079a26  mov     [rbp+4A0h+var_368], 0Fh
0x180079a31  lea     rdx, [rbp+4A0h+var_370]
0x180079a38  lea     rcx, [rbp+4A0h+var_2D0]
0x180079a3f  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x180079a44  nop
0x180079a45  lea     r8, [rbp+4A0h+var_2D0]; this
0x180079a4c  mov     rdx, r12; void *
0x180079a4f  lea     rcx, [rbp+4A0h+var_238]; Src
0x180079a56  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180079a5b  nop
0x180079a5c  mov     rdx, rax
0x180079a5f  lea     rcx, [rbp+4A0h+Src]
0x180079a66  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180079a6b  lea     rdx, [rbp+4A0h+Src]
0x180079a72  lea     rcx, [rbp+4A0h+var_310]
0x180079a79  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180079a7e  lea     rcx, [rbp+4A0h+Src]; void *
0x180079a85  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180079a8a  nop
0x180079a8b  lea     rcx, [rbp+4A0h+var_238]; void *
0x180079a92  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180079a97  nop
0x180079a98  lea     rcx, [rbp+4A0h+var_2D0]; void *
0x180079a9f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180079aa4  lea     rcx, [rbp+4A0h+var_350]
0x180079aab  mov     r12d, 7
0x180079ab1  cmp     [rbp+4A0h+var_338], r12
0x180079ab8  cmova   rcx, [rbp+4A0h+var_350]; unsigned __int16 *
0x180079ac0  call    ?FileExists@@YA_NPEBG@Z; FileExists(ushort const *)
0x180079ac5  test    al, al
0x180079ac7  jz      loc_180079B53
0x180079acd  lea     rcx, [rbp+4A0h+var_3B0]
0x180079ad4  cmp     [rbp+4A0h+var_398], r12
0x180079adb  cmova   rcx, [rbp+4A0h+var_3B0]; unsigned __int16 *
0x180079ae3  call    ?FileExists@@YA_NPEBG@Z; FileExists(ushort const *)
0x180079ae8  mov     bl, al
0x180079aea  lea     rcx, [rbp+4A0h+var_390]
0x180079af1  cmp     [rbp+4A0h+var_378], r12
0x180079af8  cmova   rcx, [rbp+4A0h+var_390]; unsigned __int16 *
0x180079b00  call    ?FileExists@@YA_NPEBG@Z; FileExists(ushort const *)
0x180079b05  lea     rcx, [rbp+4A0h+var_310]
0x180079b0c  mov     [rsp+5A0h+var_560], rcx
0x180079b11  lea     rcx, [rbp+4A0h+var_2F0]
0x180079b18  mov     [rsp+5A0h+var_568], rcx
0x180079b1d  mov     byte ptr [rsp+5A0h+var_570], bl
0x180079b21  mov     byte ptr [rsp+5A0h+var_578], al
0x180079b25  lea     rax, [rbp+4A0h+var_3B0]
0x180079b2c  mov     qword ptr [rsp+5A0h+var_580], rax
0x180079b31  lea     r9, [rbp+4A0h+var_390]
0x180079b38  lea     r8, [rbp+4A0h+var_2B0]
0x180079b3f  lea     rdx, [rbp+4A0h+var_350]
0x180079b46  mov     rcx, rsi
0x180079b49  call    ?Create@HivePaths@OfflineRegistry@@SA?AU12@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000_N100@Z; OfflineRegistry::HivePaths::Create(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,bool,bool,std::wstring const &,std::wstring const &)
0x180079b4e  jmp     loc_180079F17
0x180079b53  cmp     [rbx+18h], r12
0x180079b57  jbe     short loc_180079B5E
0x180079b59  mov     rdi, [rbx]
0x180079b5c  jmp     short loc_180079B61
0x180079b5e  mov     rdi, rbx
0x180079b61  lea     rdx, aBuildregistryc; "BuildRegistryCache"
0x180079b68  lea     rcx, [rbp+4A0h+var_190]
0x180079b6f  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180079b74  lea     rax, ??_7BuildRegistryCache@DesktopAppXProvider@@6B@; const DesktopAppXProvider::BuildRegistryCache::`vftable'
0x180079b7b  mov     [rbp+4A0h+var_190], rax
0x180079b82  mov     rdx, rdi; unsigned __int16 *
0x180079b85  lea     rcx, [rbp+4A0h+var_190]; this
0x180079b8c  call    ?StartActivity@BuildRegistryCache@DesktopAppXProvider@@QEAAXPEBG@Z; DesktopAppXProvider::BuildRegistryCache::StartActivity(ushort const *)
0x180079b91  nop
0x180079b92  lea     r9, [rbp+4A0h+var_3B0]; unsigned __int16 *
0x180079b99  lea     r8, [rbp+4A0h+var_390]; unsigned __int16 *
0x180079ba0  lea     rdx, [rbp+4A0h+var_350]; unsigned __int16 *
0x180079ba7  mov     rcx, rbx; this
0x180079baa  call    ?ClearCache@OfflineRegistry@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000@Z; OfflineRegistry::ClearCache(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x180079baf  mov     [rbp+4A0h+var_4F8], 0
0x180079bb3  mov     edx, 1
0x180079bb8  lea     rcx, [rbp+4A0h+var_1D0]
0x180079bbf  call    ?Create@Hive@OfflineRegistry@@SA?AV12@K@Z; OfflineRegistry::Hive::Create(ulong)
0x180079bc4  nop
0x180079bc5  mov     byte ptr [rsp+5A0h+var_578], 1
0x180079bca  lea     rax, [rbp+4A0h+var_1D0]
0x180079bd1  mov     qword ptr [rsp+5A0h+var_580], rax
0x180079bd6  mov     r9, r14
0x180079bd9  lea     r8, [rsp+5A0h+hObject]
0x180079bde  mov     rdx, r15
0x180079be1  lea     rcx, [rsp+5A0h+var_548]
0x180079be6  call    ?MergeHives@OfflineRegistry@@YAHPEBGPEAXAEAV?$optional@VTokenMap@@@std@@AEBV?$vector@V?$unique_ptr@VPackageInformation@@U?$default_delete@VPackageInformation@@@std@@@std@@V?$allocator@V?$unique_ptr@VPackageInformation@@U?$default_delete@VPackageInformation@@@std@@@std@@@2@@3@AEAVHive@1@_N@Z; OfflineRegistry::MergeHives(ushort const *,void *,std::optional<TokenMap> &,std::vector<std::unique_ptr<PackageInformation>> const &,OfflineRegistry::Hive &,bool)
0x180079beb  test    eax, eax
0x180079bed  jz      short loc_180079C31
0x180079bef  lea     rdx, [rbp+4A0h+var_390]
0x180079bf6  cmp     [rbp+4A0h+var_378], r12
0x180079bfd  cmova   rdx, [rbp+4A0h+var_390]
0x180079c05  mov     eax, [rbp+4A0h+var_1A0]
0x180079c0b  mov     [rsp+5A0h+var_580], eax; unsigned int
0x180079c0f  xor     r9d, r9d
0x180079c12  lea     r8d, [r9+0Ah]
0x180079c16  mov     rcx, [rbp+4A0h+var_1D0]
0x180079c1d  call    ORSaveHiveEx
0x180079c22  mov     rcx, [rbp+4A8h]; this
0x180079c29  test    eax, eax
0x180079c2b  jnz     loc_180079FC3
0x180079c31  mov     edx, 1
0x180079c36  lea     rcx, [rbp+4A0h+var_208]
0x180079c3d  call    ?Create@Hive@OfflineRegistry@@SA?AV12@K@Z; OfflineRegistry::Hive::Create(ulong)
0x180079c42  nop
  ... truncated ...
```
