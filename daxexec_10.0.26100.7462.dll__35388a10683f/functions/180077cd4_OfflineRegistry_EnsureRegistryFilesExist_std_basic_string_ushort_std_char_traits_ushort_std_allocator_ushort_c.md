# OfflineRegistry::EnsureRegistryFilesExist(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::filesystem::path const &,void *,std::vector<std::unique_ptr<PackageInformation,std::default_delete<PackageInformation>>,std::allocator<std::unique_ptr<PackageInformation,std::default_delete<PackageInformation>>>> const &,bool)

- ea: `0x180077cd4`
- end: `0x180078682`
- name: `?EnsureRegistryFilesExist@OfflineRegistry@@YA?AUHivePaths@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVpath@filesystem@4@PEAXAEBV?$vector@V?$unique_ptr@VPackageInformation@@U?$default_delete@VPackageInformation@@@std@@@std@@V?$allocator@V?$unique_ptr@VPackageInformation@@U?$default_delete@VPackageInformation@@@std@@@std@@@2@@4@_N@Z`
- size: `2478`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006fabc`

## callees

- `0x1800053a0`
- `0x180011300`
- `0x1800116b0`
- `0x180011820`
- `0x1800119a8`
- `0x180011a64`
- `0x180013100`
- `0x180013148`
- `0x18001366c`
- `0x1800148e8`
- `0x180014f4c`
- `0x18001513c`
- `0x18001748c`
- `0x18001ec94`
- `0x1800217f0`
- `0x180023e90`
- `0x180024030`
- `0x1800279fc`
- `0x18002b240`
- `0x18002d454`
- `0x18005b4cc`
- `0x18005b634`
- `0x18005f808`
- `0x1800778a0`
- `0x180077cd4`
- `0x180078cc4`
- `0x18007998c`
- `0x18007a2b8`
- `0x1800a268c`
- `0x1800cc010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x180077e22`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z` at `0x180077e22`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180077e72`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180077e72`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180077e10`
- `msvcp_win!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180077e10`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180077e82`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180077e82`

## string_xrefs

- `0x18007862e`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x18007865b`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x180078670`: `onecore\base\appmodel\execmodel\desktopappx\lib\offlineregistry.cpp`
- `0x180077d21`: `\registry`
- `0x180078233`: `BuildRegistryCache`
- `0x180077fcc`: `_COM15.dat`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
const wchar_t *__fastcall OfflineRegistry::EnsureRegistryFilesExist(
        const wchar_t *a1,
        unsigned __int16 *a2,
        __int64 a3,
        void *a4,
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
  const unsigned __int16 *v20; // rcx
  const unsigned __int16 *v21; // rcx
  char v22; // bl
  const unsigned __int16 *v23; // rcx
  char v24; // al
  const unsigned __int16 *v25; // rdi
  unsigned __int16 **v26; // rdx
  unsigned int v27; // eax
  unsigned __int16 **v28; // rdx
  unsigned int v29; // eax
  unsigned __int16 **v30; // rdx
  unsigned int v31; // eax
  const unsigned __int16 *v32; // rcx
  char v33; // bl
  const unsigned __int16 *v34; // rcx
  char v35; // al
  unsigned int v37; // [rsp+20h] [rbp-E0h]
  unsigned int v38; // [rsp+20h] [rbp-E0h]
  unsigned int v39; // [rsp+20h] [rbp-E0h]
  const wchar_t *v40; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h]
  __int64 v42; // [rsp+70h] [rbp-90h] BYREF
  int v43; // [rsp+78h] [rbp-88h]
  __int128 v44; // [rsp+80h] [rbp-80h] BYREF
  int v45; // [rsp+90h] [rbp-70h]
  _BYTE v46[56]; // [rsp+A0h] [rbp-60h] BYREF
  char v47; // [rsp+D8h] [rbp-28h]
  int v48; // [rsp+DCh] [rbp-24h]
  _QWORD v49[2]; // [rsp+E0h] [rbp-20h] BYREF
  char v50[8]; // [rsp+F0h] [rbp-10h] BYREF
  char v51[8]; // [rsp+F8h] [rbp-8h] BYREF
  char v52[120]; // [rsp+100h] [rbp+0h] BYREF
  char v53[104]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v54[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v55; // [rsp+1F0h] [rbp+F0h]
  unsigned __int16 *v56[3]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int64 v57; // [rsp+218h] [rbp+118h]
  unsigned __int16 *v58[3]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int64 v59; // [rsp+238h] [rbp+138h]
  unsigned __int16 *v60[3]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int64 v61; // [rsp+258h] [rbp+158h]
  __int128 v62; // [rsp+260h] [rbp+160h] BYREF
  __int128 v63; // [rsp+270h] [rbp+170h]
  _OWORD v64[2]; // [rsp+280h] [rbp+180h] BYREF
  __int128 v65; // [rsp+2A0h] [rbp+1A0h] BYREF
  __m128i si128; // [rsp+2B0h] [rbp+1B0h]
  _BYTE v67[32]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v68[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _QWORD v69[2]; // [rsp+300h] [rbp+200h] BYREF
  char v70[32]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v71[32]; // [rsp+330h] [rbp+230h] BYREF
  __int64 v72[2]; // [rsp+350h] [rbp+250h] BYREF
  char v73[32]; // [rsp+360h] [rbp+260h] BYREF
  unsigned int v74; // [rsp+380h] [rbp+280h]
  _QWORD v75[2]; // [rsp+388h] [rbp+288h] BYREF
  char v76[32]; // [rsp+398h] [rbp+298h] BYREF
  unsigned int v77; // [rsp+3B8h] [rbp+2B8h]
  _QWORD v78[2]; // [rsp+3C0h] [rbp+2C0h] BYREF
  char v79[32]; // [rsp+3D0h] [rbp+2D0h] BYREF
  unsigned int v80; // [rsp+3F0h] [rbp+2F0h]
  _QWORD v81[42]; // [rsp+400h] [rbp+300h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5A8h] [rbp+4A8h]

  v40 = a1;
  v44 = *(_OWORD *)L"\\registry";
  v45 = *(_DWORD *)L"y";
  v42 = *(_QWORD *)L"\\user";
  v43 = *(_DWORD *)L"r";
  v62 = *(_OWORD *)L"\\userclasses";
  *(_QWORD *)&v63 = *(_QWORD *)L"sses";
  WORD4(v63) = aUserclasses[12];
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
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v49);
  v16 = a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v16 = *(unsigned __int16 **)a2;
  v17 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(
          v50,
          v16,
          *((_QWORD *)a2 + 2));
  v18 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v17, L"\\");
  v19 = std::basic_ostream<unsigned short>::operator<<(v18, std::hex);
  std::basic_ostream<unsigned short>::operator<<(v19, v10);
  std::basic_stringbuf<unsigned short>::str(v51, v54);
  *(_QWORD *)((char *)v49 + *(int *)(v49[0] + 4LL)) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
  *(int *)((char *)&v48 + *(int *)(v49[0] + 4LL)) = *(_DWORD *)(v49[0] + 4LL) - 152;
  std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v51);
  std::basic_iostream<unsigned short>::~basic_iostream<unsigned short,std::char_traits<unsigned short>>(v52);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v53);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v55) < 4 )
    std::_Xlen_string();
  std::wstring::wstring(v60, v55, L".dat", 4);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v55) < 9 )
    std::_Xlen_string();
  std::wstring::wstring(v58, v55, L"_user.dat", 9);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v55) < 0x10 )
    std::_Xlen_string();
  std::wstring::wstring(v56, v55, L"_userclasses.dat", 16);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v55) < 0xA )
    std::_Xlen_string();
  std::wstring::wstring(v71, v55, L"_COM15.dat", 10);
  v65 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v65) = 0;
  v64[0] = 0;
  v64[1] = si128;
  LOWORD(v64[0]) = 0;
  if ( a6 )
  {
    v40 = L"User.dat";
    v41 = 8;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v68, &v40);
    std::wstring::wstring(v67, a3);
    std::filesystem::path::operator/=(v67, (std::filesystem *)v68);
    std::wstring::wstring(v69, v67);
    std::wstring::operator=(&v65, v69);
    std::wstring::~wstring(v69);
    std::wstring::~wstring(v67);
    std::wstring::~wstring(v68);
    v40 = L"UserClasses.dat";
    v41 = 15;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v67, &v40);
    std::wstring::wstring(v68, a3);
    std::filesystem::path::operator/=(v68, (std::filesystem *)v67);
    std::wstring::wstring(v69, v68);
    std::wstring::operator=(v64, v69);
    std::wstring::~wstring(v69);
    std::wstring::~wstring(v68);
    std::wstring::~wstring(v67);
  }
  v20 = (const unsigned __int16 *)v60;
  if ( v61 > 7 )
    v20 = v60[0];
  if ( FileExists(v20) )
  {
    v21 = (const unsigned __int16 *)v56;
    if ( v57 > 7 )
      v21 = v56[0];
    v22 = FileExists(v21);
    v23 = (const unsigned __int16 *)v58;
    if ( v59 > 7 )
      v23 = v58[0];
    v24 = FileExists(v23);
    OfflineRegistry::HivePaths::Create(
      (_DWORD)a1,
      (unsigned int)v60,
      (unsigned int)v71,
      (unsigned int)v58,
      (__int64)v56,
      v24,
      v22,
      (__int64)&v65,
      (__int64)v64);
  }
  else
  {
    v25 = a2;
    if ( *((_QWORD *)a2 + 3) > 7u )
      v25 = *(const unsigned __int16 **)a2;
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v81,
      "BuildRegistryCache");
    v81[0] = &DesktopAppXProvider::BuildRegistryCache::`vftable';
    DesktopAppXProvider::BuildRegistryCache::StartActivity((DesktopAppXProvider::BuildRegistryCache *)v81, v25);
    OfflineRegistry::ClearCache((char *)a2, (unsigned __int16 *)v60, (unsigned __int16 *)v58, (unsigned __int16 *)v56);
    v47 = 0;
    OfflineRegistry::Hive::Create(v78, 1);
    if ( (unsigned int)OfflineRegistry::MergeHives((__int64)&v42, a4, (__int64)v46, (__int64)a5, (__int64)v78, 1) )
    {
      v26 = v58;
      if ( v59 > 7 )
        LODWORD(v26) = v58[0];
      v27 = ORSaveHiveEx(v78[0], (_DWORD)v26, 10, 0, v80);
      if ( v27 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x203,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
          (const char *)v27,
          v37);
    }
    OfflineRegistry::Hive::Create(v75, 1);
    if ( (unsigned int)OfflineRegistry::MergeHives((__int64)&v62, a4, (__int64)v46, (__int64)a5, (__int64)v75, 1) )
    {
      v28 = v56;
      if ( v57 > 7 )
        LODWORD(v28) = v56[0];
      v29 = ORSaveHiveEx(v75[0], (_DWORD)v28, 10, 0, v77);
      if ( v29 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x203,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
          (const char *)v29,
          v38);
    }
    OfflineRegistry::Hive::Create(v72, 1);
    v62 = 0;
    v63 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v62, L"Classes", 7);
    OfflineRegistry::Key::CreateSubKeys(v72, v69, (__int64)&v62);
    std::wstring::~wstring(v70);
    if ( v69[0] )
      ((void (*)(void))v69[1])();
    std::wstring::~wstring(&v62);
    OfflineRegistry::MergeHives((__int64)&v44, a4, (__int64)v46, (__int64)a5, (__int64)v72, 0);
    v30 = v60;
    if ( v61 > 7 )
      LODWORD(v30) = v60[0];
    v31 = ORSaveHiveEx(v72[0], (_DWORD)v30, 10, 0, v74);
    if ( v31 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x203,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\offlineregistry.cpp",
        (const char *)v31,
        v39);
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v81, 0);
    v32 = (const unsigned __int16 *)v56;
    if ( v57 > 7 )
      v32 = v56[0];
    v33 = FileExists(v32);
    v34 = (const unsigned __int16 *)v58;
    if ( v59 > 7 )
      v34 = v58[0];
    v35 = FileExists(v34);
    OfflineRegistry::HivePaths::Create(
      (_DWORD)a1,
      (unsigned int)v60,
      (unsigned int)v71,
      (unsigned int)v58,
      (__int64)v56,
      v35,
      v33,
      (__int64)&v65,
      (__int64)v64);
    std::wstring::~wstring(v73);
    if ( v72[0] )
      ((void (*)(void))v72[1])();
    std::wstring::~wstring(v76);
    if ( v75[0] )
      ((void (*)(void))v75[1])();
    std::wstring::~wstring(v79);
    if ( v78[0] )
      ((void (*)(void))v78[1])();
    if ( v47 )
      TokenMap::~TokenMap((TokenMap *)v46);
    v81[0] = &DesktopAppXProvider::BuildRegistryCache::`vftable';
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v81);
    wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v81);
  }
  std::wstring::~wstring(v64);
  std::wstring::~wstring(&v65);
  std::wstring::~wstring(v71);
  std::wstring::~wstring(v56);
  std::wstring::~wstring(v58);
  std::wstring::~wstring(v60);
  std::wstring::~wstring(v54);
  return a1;
}

```

## disassembly

```asm
0x180077cd4  push    rbp
0x180077cd6  push    rbx
0x180077cd7  push    rsi
0x180077cd8  push    rdi
0x180077cd9  push    r12
0x180077cdb  push    r13
0x180077cdd  push    r14
0x180077cdf  push    r15
0x180077ce1  lea     rbp, [rsp-468h]
0x180077ce9  sub     rsp, 568h
0x180077cf0  mov     rax, cs:__security_cookie
0x180077cf7  xor     rax, rsp
0x180077cfa  mov     [rbp+4A0h+var_50], rax
0x180077d01  mov     r15, r9
0x180077d04  mov     r12, r8
0x180077d07  mov     rbx, rdx
0x180077d0a  mov     rsi, rcx
0x180077d0d  mov     [rsp+5A0h+var_540], rcx
0x180077d12  mov     r14, [rbp+4A0h+arg_20]
0x180077d19  xor     r13d, r13d
0x180077d1c  mov     [rsp+5A0h+var_550], r13d
0x180077d21  movups  xmm0, xmmword ptr cs:aRegistry_0; "\\registry"
0x180077d28  movups  [rbp+4A0h+var_520], xmm0
0x180077d2c  mov     eax, dword ptr cs:aRegistry_0+10h; "y"
0x180077d32  mov     [rbp+4A0h+var_510], eax
0x180077d35  movsd   xmm0, qword ptr cs:aUser_0; "\\user"
0x180077d3d  movsd   [rsp+5A0h+var_530], xmm0
0x180077d43  mov     eax, dword ptr cs:aUser_0+8; "r"
0x180077d49  mov     [rsp+5A0h+var_528], eax
0x180077d4d  movups  xmm0, xmmword ptr cs:aUserclasses; "\\userclasses"
0x180077d54  movups  [rbp+4A0h+var_340], xmm0
0x180077d5b  movsd   xmm0, qword ptr cs:aUserclasses+10h; "sses"
0x180077d63  movsd   qword ptr [rbp+4A0h+var_330], xmm0
0x180077d6b  movzx   eax, word ptr cs:aUserclasses+18h; ""
0x180077d72  mov     word ptr [rbp+4A0h+var_330+8], ax
0x180077d79  mov     edi, r13d
0x180077d7c  mov     r8, [r14]
0x180077d7f  jmp     short loc_180077DCD
0x180077d81  mov     rcx, [r8]
0x180077d84  add     rcx, 8
0x180077d88  mov     r10, [rcx+10h]
0x180077d8c  cmp     qword ptr [rcx+18h], 7
0x180077d91  jbe     short loc_180077D96
0x180077d93  mov     rcx, [rcx]
0x180077d96  mov     rdx, 0CBF29CE484222325h
0x180077da0  mov     r9, r13
0x180077da3  add     r10, r10
0x180077da6  jz      short loc_180077DC6
0x180077da8  movzx   eax, byte ptr [r9+rcx]
0x180077dad  xor     rdx, rax
0x180077db0  mov     r11, 100000001B3h
0x180077dba  imul    rdx, r11
0x180077dbe  inc     r9
0x180077dc1  cmp     r9, r10
0x180077dc4  jb      short loc_180077DA8
0x180077dc6  xor     rdi, rdx
0x180077dc9  add     r8, 8
0x180077dcd  cmp     r8, [r14+8]
0x180077dd1  jnz     short loc_180077D81
0x180077dd3  lea     rcx, [rbp+4A0h+var_4C0]
0x180077dd7  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180077ddc  nop
0x180077ddd  mov     rdx, rbx
0x180077de0  cmp     qword ptr [rbx+18h], 7
0x180077de5  jbe     short loc_180077DEA
0x180077de7  mov     rdx, [rbx]
0x180077dea  mov     r8, [rbx+10h]
0x180077dee  lea     rcx, [rbp+4A0h+var_4B0]
0x180077df2  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x180077df7  lea     rdx, asc_1800D5864; "\\"
0x180077dfe  mov     rcx, rax
0x180077e01  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x180077e06  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x180077e0d  mov     rcx, rax
0x180077e10  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::basic_ostream<ushort>::operator<<(std::ios_base & (*)(std::ios_base &))
0x180077e17  nop     dword ptr [rax+rax+00h]
0x180077e1c  mov     rdx, rdi
0x180077e1f  mov     rcx, rax
0x180077e22  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@_K@Z; std::basic_ostream<ushort>::operator<<(unsigned __int64)
0x180077e29  nop     dword ptr [rax+rax+00h]
0x180077e2e  lea     rdx, [rbp+4A0h+var_3C0]
0x180077e35  lea     rcx, [rbp+4A0h+var_4A8]
0x180077e39  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x180077e3e  nop
0x180077e3f  mov     rax, [rbp+4A0h+var_4C0]
0x180077e43  movsxd  rcx, dword ptr [rax+4]
0x180077e47  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x180077e4e  mov     [rbp+rcx+4A0h+var_4C0], rax
0x180077e53  mov     rax, [rbp+4A0h+var_4C0]
0x180077e57  movsxd  rcx, dword ptr [rax+4]
0x180077e5b  lea     edx, [rcx-98h]
0x180077e61  mov     [rbp+rcx+4A0h+var_4C4], edx
0x180077e65  lea     rcx, [rbp+4A0h+var_4A8]
0x180077e69  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x180077e6e  lea     rcx, [rbp+4A0h+var_4A0]
0x180077e72  call    cs:__imp_??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_iostream<ushort>::~basic_iostream<ushort,std::char_traits<ushort>>(void)
0x180077e79  nop     dword ptr [rax+rax+00h]
0x180077e7e  lea     rcx, [rbp+4A0h+var_428]
0x180077e82  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180077e89  nop     dword ptr [rax+rax+00h]
0x180077e8e  nop
0x180077e8f  mov     rdi, 7FFFFFFFFFFFFFFEh
0x180077e99  mov     rax, rdi
0x180077e9c  mov     rcx, [rbp+4A0h+var_3B0]
0x180077ea3  sub     rax, rcx
0x180077ea6  cmp     rax, 4
0x180077eaa  jb      loc_180078640
0x180077eb0  lea     r9, [rbp+4A0h+var_3C0]
0x180077eb7  cmp     [rbp+4A0h+var_3A8], 7
0x180077ebf  cmova   r9, [rbp+4A0h+var_3C0]
0x180077ec7  mov     [rsp+5A0h+var_570], 4; __int64
0x180077ed0  lea     rax, aDat_0; ".dat"
0x180077ed7  mov     [rsp+5A0h+Src], rax; Src
0x180077edc  mov     qword ptr [rsp+5A0h+var_580], rcx; __int64
0x180077ee1  lea     rcx, [rbp+4A0h+var_360]; void *
0x180077ee8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180077eed  nop
0x180077eee  mov     rax, rdi
0x180077ef1  mov     rcx, [rbp+4A0h+var_3B0]
0x180077ef8  sub     rax, rcx
0x180077efb  cmp     rax, 9
0x180077eff  jb      loc_180078646
0x180077f05  lea     r9, [rbp+4A0h+var_3C0]
0x180077f0c  cmp     [rbp+4A0h+var_3A8], 7
0x180077f14  cmova   r9, [rbp+4A0h+var_3C0]
0x180077f1c  mov     [rsp+5A0h+var_570], 9; __int64
0x180077f25  lea     rax, aUserDat; "_user.dat"
0x180077f2c  mov     [rsp+5A0h+Src], rax; Src
0x180077f31  mov     qword ptr [rsp+5A0h+var_580], rcx; __int64
0x180077f36  lea     rcx, [rbp+4A0h+var_380]; void *
0x180077f3d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180077f42  nop
0x180077f43  mov     rax, rdi
0x180077f46  mov     rcx, [rbp+4A0h+var_3B0]
0x180077f4d  sub     rax, rcx
0x180077f50  cmp     rax, 10h
0x180077f54  jb      loc_18007864C
0x180077f5a  lea     r9, [rbp+4A0h+var_3C0]
0x180077f61  cmp     [rbp+4A0h+var_3A8], 7
0x180077f69  cmova   r9, [rbp+4A0h+var_3C0]
0x180077f71  mov     [rsp+5A0h+var_570], 10h; __int64
0x180077f7a  lea     rax, aUserclassesDat; "_userclasses.dat"
0x180077f81  mov     [rsp+5A0h+Src], rax; Src
0x180077f86  mov     qword ptr [rsp+5A0h+var_580], rcx; __int64
0x180077f8b  lea     rcx, [rbp+4A0h+var_3A0]; void *
0x180077f92  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180077f97  nop
0x180077f98  mov     rax, [rbp+4A0h+var_3B0]
0x180077f9f  sub     rdi, rax
0x180077fa2  cmp     rdi, 0Ah
0x180077fa6  jb      loc_180078652
0x180077fac  lea     r9, [rbp+4A0h+var_3C0]
0x180077fb3  cmp     [rbp+4A0h+var_3A8], 7
0x180077fbb  cmova   r9, [rbp+4A0h+var_3C0]
0x180077fc3  mov     [rsp+5A0h+var_570], 0Ah; __int64
0x180077fcc  lea     rcx, aCom15Dat; "_COM15.dat"
0x180077fd3  mov     [rsp+5A0h+Src], rcx; Src
0x180077fd8  mov     qword ptr [rsp+5A0h+var_580], rax; __int64
0x180077fdd  lea     rcx, [rbp+4A0h+var_270]; void *
0x180077fe4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180077fe9  nop
0x180077fea  xorps   xmm0, xmm0
0x180077fed  movups  [rbp+4A0h+var_300], xmm0
0x180077ff4  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180077ffc  movdqu  [rbp+4A0h+var_2F0], xmm1
0x180078004  mov     word ptr [rbp+4A0h+var_300], r13w
0x18007800c  movups  [rbp+4A0h+var_320], xmm0
0x180078013  movdqu  [rbp+4A0h+var_310], xmm1
0x18007801b  mov     word ptr [rbp+4A0h+var_320], r13w
0x180078023  cmp     [rbp+4A0h+arg_28], r13b
0x18007802a  jz      loc_180078178
0x180078030  lea     rax, aUserDat_0; "User.dat"
0x180078037  mov     [rsp+5A0h+var_540], rax
0x18007803c  mov     [rsp+5A0h+var_538], 8
0x180078045  lea     rdx, [rsp+5A0h+var_540]
0x18007804a  lea     rcx, [rbp+4A0h+var_2C0]
0x180078051  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x180078056  mov     [rsp+5A0h+var_550], 0FEh
0x18007805e  mov     rdx, r12
0x180078061  lea     rcx, [rbp+4A0h+var_2E0]
0x180078068  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18007806d  mov     [rsp+5A0h+var_550], 1FEh
0x180078075  lea     rdx, [rbp+4A0h+var_2C0]; this
0x18007807c  lea     rcx, [rbp+4A0h+var_2E0]; void *
0x180078083  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x180078088  lea     rdx, [rbp+4A0h+var_2E0]
0x18007808f  lea     rcx, [rbp+4A0h+var_2A0]
0x180078096  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18007809b  lea     rdx, [rbp+4A0h+var_2A0]
0x1800780a2  lea     rcx, [rbp+4A0h+var_300]
0x1800780a9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800780ae  lea     rcx, [rbp+4A0h+var_2A0]; void *
0x1800780b5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800780ba  nop
0x1800780bb  lea     rcx, [rbp+4A0h+var_2E0]; void *
0x1800780c2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800780c7  nop
0x1800780c8  lea     rcx, [rbp+4A0h+var_2C0]; void *
0x1800780cf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800780d4  lea     rax, aUserclassesDat_0; "UserClasses.dat"
0x1800780db  mov     [rsp+5A0h+var_540], rax
0x1800780e0  mov     [rsp+5A0h+var_538], 0Fh
0x1800780e9  lea     rdx, [rsp+5A0h+var_540]
0x1800780ee  lea     rcx, [rbp+4A0h+var_2E0]
0x1800780f5  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x1800780fa  mov     [rsp+5A0h+var_550], 6FEh
0x180078102  mov     rdx, r12
0x180078105  lea     rcx, [rbp+4A0h+var_2C0]
0x18007810c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180078111  mov     [rsp+5A0h+var_550], 0EFEh
0x180078119  lea     rdx, [rbp+4A0h+var_2E0]; this
0x180078120  lea     rcx, [rbp+4A0h+var_2C0]; void *
0x180078127  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x18007812c  lea     rdx, [rbp+4A0h+var_2C0]
0x180078133  lea     rcx, [rbp+4A0h+var_2A0]
0x18007813a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18007813f  lea     rdx, [rbp+4A0h+var_2A0]
0x180078146  lea     rcx, [rbp+4A0h+var_320]
0x18007814d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180078152  lea     rcx, [rbp+4A0h+var_2A0]; void *
0x180078159  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007815e  nop
0x18007815f  lea     rcx, [rbp+4A0h+var_2C0]; void *
0x180078166  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007816b  nop
0x18007816c  lea     rcx, [rbp+4A0h+var_2E0]; void *
0x180078173  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180078178  lea     rcx, [rbp+4A0h+var_360]
0x18007817f  mov     r12d, 7
0x180078185  cmp     [rbp+4A0h+var_348], r12
0x18007818c  cmova   rcx, [rbp+4A0h+var_360]; unsigned __int16 *
0x180078194  call    ?FileExists@@YA_NPEBG@Z; FileExists(ushort const *)
0x180078199  test    al, al
0x18007819b  jz      loc_180078227
0x1800781a1  lea     rcx, [rbp+4A0h+var_3A0]
0x1800781a8  cmp     [rbp+4A0h+var_388], r12
0x1800781af  cmova   rcx, [rbp+4A0h+var_3A0]; unsigned __int16 *
0x1800781b7  call    ?FileExists@@YA_NPEBG@Z; FileExists(ushort const *)
0x1800781bc  mov     bl, al
0x1800781be  lea     rcx, [rbp+4A0h+var_380]
0x1800781c5  cmp     [rbp+4A0h+var_368], r12
0x1800781cc  cmova   rcx, [rbp+4A0h+var_380]; unsigned __int16 *
0x1800781d4  call    ?FileExists@@YA_NPEBG@Z; FileExists(ushort const *)
0x1800781d9  lea     rcx, [rbp+4A0h+var_320]
0x1800781e0  mov     [rsp+5A0h+var_560], rcx
0x1800781e5  lea     rcx, [rbp+4A0h+var_300]
0x1800781ec  mov     [rsp+5A0h+var_568], rcx
0x1800781f1  mov     byte ptr [rsp+5A0h+var_570], bl
0x1800781f5  mov     byte ptr [rsp+5A0h+Src], al
0x1800781f9  lea     rax, [rbp+4A0h+var_3A0]
0x180078200  mov     qword ptr [rsp+5A0h+var_580], rax
0x180078205  lea     r9, [rbp+4A0h+var_380]
0x18007820c  lea     r8, [rbp+4A0h+var_270]
0x180078213  lea     rdx, [rbp+4A0h+var_360]
0x18007821a  mov     rcx, rsi
0x18007821d  call    ?Create@HivePaths@OfflineRegistry@@SA?AU12@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000_N100@Z; OfflineRegistry::HivePaths::Create(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,bool,bool,std::wstring const &,std::wstring const &)
0x180078222  jmp     loc_1800785AA
0x180078227  mov     rdi, rbx
0x18007822a  cmp     [rbx+18h], r12
0x18007822e  jbe     short loc_180078233
0x180078230  mov     rdi, [rbx]
0x180078233  lea     rdx, aBuildregistryc; "BuildRegistryCache"
0x18007823a  lea     rcx, [rbp+4A0h+var_1A0]
0x180078241  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180078246  lea     rax, ??_7BuildRegistryCache@DesktopAppXProvider@@6B@; const DesktopAppXProvider::BuildRegistryCache::`vftable'
0x18007824d  mov     [rbp+4A0h+var_1A0], rax
0x180078254  mov     rdx, rdi; unsigned __int16 *
0x180078257  lea     rcx, [rbp+4A0h+var_1A0]; this
0x18007825e  call    ?StartActivity@BuildRegistryCache@DesktopAppXProvider@@QEAAXPEBG@Z; DesktopAppXProvider::BuildRegistryCache::StartActivity(ushort const *)
0x180078263  nop
0x180078264  lea     r9, [rbp+4A0h+var_3A0]; unsigned __int16 *
0x18007826b  lea     r8, [rbp+4A0h+var_380]; unsigned __int16 *
0x180078272  lea     rdx, [rbp+4A0h+var_360]; unsigned __int16 *
0x180078279  mov     rcx, rbx; char *
0x18007827c  call    ?ClearCache@OfflineRegistry@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000@Z; OfflineRegistry::ClearCache(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x180078281  mov     [rbp+4A0h+var_4C8], r13b
0x180078285  mov     edx, 1
0x18007828a  lea     rcx, [rbp+4A0h+var_1E0]
0x180078291  call    ?Create@Hive@OfflineRegistry@@SA?AV12@K@Z; OfflineRegistry::Hive::Create(ulong)
0x180078296  nop
0x180078297  mov     byte ptr [rsp+5A0h+Src], 1
0x18007829c  lea     rax, [rbp+4A0h+var_1E0]
0x1800782a3  mov     qword ptr [rsp+5A0h+var_580], rax
0x1800782a8  mov     r9, r14
0x1800782ab  lea     r8, [rbp+4A0h+var_500]
0x1800782af  mov     rdx, r15
0x1800782b2  lea     rcx, [rsp+5A0h+var_530]
0x1800782b7  call    ?MergeHives@OfflineRegistry@@YAHPEBGPEAXAEAV?$optional@VTokenMap@@@std@@AEBV?$vector@V?$unique_ptr@VPackageInformation@@U?$default_delete@VPackageInformation@@@std@@@std@@V?$allocator@V?$unique_ptr@VPackageInformation@@U?$default_delete@VPackageInformation@@@std@@@std@@@2@@3@AEAVHive@1@_N@Z; OfflineRegistry::MergeHives(ushort const *,void *,std::optional<TokenMap> &,std::vector<std::unique_ptr<PackageInformation>> const &,OfflineRegistry::Hive &,bool)
0x1800782bc  test    eax, eax
0x1800782be  jz      short loc_180078302
0x1800782c0  lea     rdx, [rbp+4A0h+var_380]
0x1800782c7  cmp     [rbp+4A0h+var_368], r12
0x1800782ce  cmova   rdx, [rbp+4A0h+var_380]
0x1800782d6  mov     eax, [rbp+4A0h+var_1B0]
0x1800782dc  mov     [rsp+5A0h+var_580], eax; unsigned int
0x1800782e0  xor     r9d, r9d
0x1800782e3  lea     r8d, [r9+0Ah]
0x1800782e7  mov     rcx, [rbp+4A0h+var_1E0]
0x1800782ee  call    ORSaveHiveEx
0x1800782f3  mov     rcx, [rbp+4A8h]; this
  ... truncated ...
```
