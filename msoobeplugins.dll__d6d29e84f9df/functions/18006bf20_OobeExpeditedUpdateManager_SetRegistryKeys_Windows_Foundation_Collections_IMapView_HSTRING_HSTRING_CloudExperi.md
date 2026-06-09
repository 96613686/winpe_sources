# OobeExpeditedUpdateManager::SetRegistryKeys(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *,CloudExperienceHostAPI::OobeExpeditedUpdateCommitOption)

- ea: `0x18006bf20`
- end: `0x18006c42c`
- name: `?SetRegistryKeys@OobeExpeditedUpdateManager@@QEAAJPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@W4OobeExpeditedUpdateCommitOption@CloudExperienceHostAPI@@@Z`
- size: `1292`
- prototype: `__int64 __fastcall(__int64, HSTRING, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800658f0`

## callees

- `0x180003470`
- `0x180007bbc`
- `0x180008544`
- `0x18001ad08`
- `0x18001de58`
- `0x18002d0e0`
- `0x1800418d8`
- `0x180043c58`
- `0x180061670`
- `0x18006bf20`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006c1c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006c1d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006c1c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006c1d9`

## string_xrefs

- `0x18006c1e5`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\OOBE\NDUP\Updates`
- `0x18006c304`: `EnableExpeditedUpdateDeferred`
- `0x18006c357`: `EnableExpeditedUpdateAsync`
- `0x18006c3a3`: `EnableExpeditedUpdateSync`
- `0x18006bf8a`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006bfe1`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006c069`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006c0ee`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006c173`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006c206`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006c279`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006c329`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006c378`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18006c3c4`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`

## pseudocode

```c
__int64 __fastcall OobeExpeditedUpdateManager::SetRegistryKeys(__int64 a1, HSTRING a2, int a3)
{
  __int64 v4; // rax
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // eax
  HKEY v9; // rcx
  int v10; // r9d
  unsigned int v11; // ebx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64 *); // rbx
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  int v18; // eax
  unsigned int v19; // ebx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, HSTRING *); // rbx
  int v22; // eax
  unsigned int v23; // ebx
  const unsigned __int16 *StringRawBuffer; // rbx
  const unsigned __int16 *v25; // rax
  int v26; // eax
  unsigned int v27; // ebx
  int v28; // eax
  unsigned int v29; // ebx
  int v30; // esi
  int v31; // esi
  int v32; // eax
  unsigned int v33; // ebx
  int v34; // eax
  unsigned int v35; // ebx
  int v36; // eax
  unsigned int v37; // ebx
  HSTRING v38; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v39[8]; // [rsp+28h] [rbp-40h] BYREF
  __int64 v40; // [rsp+30h] [rbp-38h] BYREF
  __int64 *v41; // [rsp+38h] [rbp-30h] BYREF
  __int64 v42; // [rsp+40h] [rbp-28h] BYREF
  HSTRING string; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v38 = a2;
  wil::com_copy<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>,Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> * &>(
    &v41,
    (__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))&v38);
  v40 = 0;
  v4 = *v41;
  v40 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v4 + 48))(v41, &v40);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x252,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
      (const char *)(unsigned int)v5,
      (int)v38);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v40);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v41);
    return v6;
  }
  v39[0] = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v40 + 56LL))(v40, v39);
  v11 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x254,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
      (const char *)(unsigned int)v8,
      (int)v38);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v40);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v41);
    return v11;
  }
  while ( v39[0] )
  {
    v38 = 0;
    string = 0;
    v42 = 0;
    v12 = v40;
    v13 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    v14 = v13(v12, &v42);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25B,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
        (const char *)(unsigned int)v14,
        (int)v38);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      Windows::Internal::String::~String((Windows::Internal::String *)&v38);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v40);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v41);
      return v15;
    }
    v16 = v42;
    v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v42 + 48LL);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &v38,
      0);
    v18 = v17(v16, &v38);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25C,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
        (const char *)(unsigned int)v18,
        (int)v38);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      Windows::Internal::String::~String((Windows::Internal::String *)&v38);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v40);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v41);
      return v19;
    }
    v20 = v42;
    v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v42 + 56LL);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &string,
      0);
    v22 = v21(v20, &string);
    v23 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25D,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
        (const char *)(unsigned int)v22,
        (int)v38);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      Windows::Internal::String::~String((Windows::Internal::String *)&v38);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v40);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v41);
      return v23;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v25 = WindowsGetStringRawBuffer(v38, 0);
    v26 = SHRegSetString(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE\\NDUP\\Updates",
            v25,
            StringRawBuffer);
    v27 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25E,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
        (const char *)(unsigned int)v26,
        (int)v38);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      Windows::Internal::String::~String((Windows::Internal::String *)&v38);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v40);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v41);
      return v27;
    }
    v28 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v40 + 64LL))(v40, v39);
    v29 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25F,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
        (const char *)(unsigned int)v28,
        (int)v38);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      Windows::Internal::String::~String((Windows::Internal::String *)&v38);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v40);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v41);
      return v29;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Windows::Internal::String::~String((Windows::Internal::String *)&v38);
  }
  v30 = a3 - 1;
  if ( v30 )
  {
    v31 = v30 - 1;
    if ( v31 )
    {
      if ( v31 == 1 )
      {
        v32 = SHRegSetBOOL(
                v9,
                L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE\\NDUP",
                L"EnableExpeditedUpdateDeferred",
                v10);
        v33 = v32;
        if ( v32 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x26B,
            (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
            (const char *)(unsigned int)v32,
            (int)v38);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v40);
          wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v41);
          return v33;
        }
      }
    }
    else
    {
      v34 = SHRegSetBOOL(
              v9,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE\\NDUP",
              L"EnableExpeditedUpdateAsync",
              v10);
      v35 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x268,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
          (const char *)(unsigned int)v34,
          (int)v38);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v40);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v41);
        return v35;
      }
    }
  }
  else
  {
    v36 = SHRegSetBOOL(
            v9,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\OOBE\\NDUP",
            L"EnableExpeditedUpdateSync",
            v10);
    v37 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x265,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
        (const char *)(unsigned int)v36,
        (int)v38);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v40);
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v41);
      return v37;
    }
  }
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v40);
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v41);
  return 0;
}

```

## disassembly

```asm
0x18006bf20  mov     r11, rsp
0x18006bf23  mov     [r11+8], rbx
0x18006bf27  mov     [r11+18h], rsi
0x18006bf2b  push    rdi
0x18006bf2c  sub     rsp, 60h
0x18006bf30  mov     rax, cs:__security_cookie
0x18006bf37  xor     rax, rsp
0x18006bf3a  mov     [rsp+68h+var_18], rax
0x18006bf3f  mov     esi, r8d
0x18006bf42  mov     [r11-48h], rdx
0x18006bf46  lea     rdx, [r11-48h]
0x18006bf4a  lea     rcx, [r11-30h]
0x18006bf4e  call    ??$com_copy@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@AEAPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@234@@wil@@YA?AV?$com_ptr_t@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@0@AEAPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Z; wil::com_copy<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>,Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> * &>(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> * &)
0x18006bf53  nop
0x18006bf54  mov     [rsp+68h+var_38], 0
0x18006bf5d  mov     rcx, [rsp+68h+var_30]
0x18006bf62  mov     rax, [rcx]
0x18006bf65  mov     [rsp+68h+var_38], 0
0x18006bf6e  lea     rdx, [rsp+68h+var_38]
0x18006bf73  mov     rax, [rax+30h]
0x18006bf77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bf7c  mov     ebx, eax
0x18006bf7e  test    eax, eax
0x18006bf80  jns     short loc_18006BFB8
0x18006bf82  mov     rcx, [rsp+68h]; this
0x18006bf87  mov     r9d, eax; char *
0x18006bf8a  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006bf91  mov     edx, 252h; void *
0x18006bf96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bf9b  nop
0x18006bf9c  lea     rcx, [rsp+68h+var_38]
0x18006bfa1  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006bfa6  nop
0x18006bfa7  lea     rcx, [rsp+68h+var_30]
0x18006bfac  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006bfb1  mov     eax, ebx
0x18006bfb3  jmp     loc_18006C40C
0x18006bfb8  mov     [rsp+68h+var_40], 0
0x18006bfbd  mov     rcx, [rsp+68h+var_38]
0x18006bfc2  mov     rax, [rcx]
0x18006bfc5  lea     rdx, [rsp+68h+var_40]
0x18006bfca  mov     rax, [rax+38h]
0x18006bfce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bfd3  mov     ebx, eax
0x18006bfd5  test    eax, eax
0x18006bfd7  jns     short loc_18006C00F
0x18006bfd9  mov     rcx, [rsp+68h]; this
0x18006bfde  mov     r9d, eax; char *
0x18006bfe1  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006bfe8  mov     edx, 254h; void *
0x18006bfed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bff2  nop
0x18006bff3  lea     rcx, [rsp+68h+var_38]
0x18006bff8  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006bffd  nop
0x18006bffe  lea     rcx, [rsp+68h+var_30]
0x18006c003  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c008  mov     eax, ebx
0x18006c00a  jmp     loc_18006C40C
0x18006c00f  cmp     [rsp+68h+var_40], 0
0x18006c014  jz      loc_18006C2ED
0x18006c01a  mov     [rsp+68h+var_48], 0; int
0x18006c023  mov     [rsp+68h+string], 0
0x18006c02c  mov     [rsp+68h+var_28], 0
0x18006c035  mov     rdi, [rsp+68h+var_38]
0x18006c03a  mov     rax, [rdi]
0x18006c03d  mov     rbx, [rax+30h]
0x18006c041  lea     rcx, [rsp+68h+var_28]
0x18006c046  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006c04b  lea     rdx, [rsp+68h+var_28]
0x18006c050  mov     rcx, rdi
0x18006c053  mov     rax, rbx
0x18006c056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c05b  mov     ebx, eax
0x18006c05d  test    eax, eax
0x18006c05f  jns     short loc_18006C0B8
0x18006c061  mov     rcx, [rsp+68h]; this
0x18006c066  mov     r9d, eax; char *
0x18006c069  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006c070  mov     edx, 25Bh; void *
0x18006c075  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c07a  nop
0x18006c07b  lea     rcx, [rsp+68h+var_28]
0x18006c080  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006c085  nop
0x18006c086  lea     rcx, [rsp+68h+string]; this
0x18006c08b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006c090  nop
0x18006c091  lea     rcx, [rsp+68h+var_48]; this
0x18006c096  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006c09b  nop
0x18006c09c  lea     rcx, [rsp+68h+var_38]
0x18006c0a1  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c0a6  nop
0x18006c0a7  lea     rcx, [rsp+68h+var_30]
0x18006c0ac  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c0b1  mov     eax, ebx
0x18006c0b3  jmp     loc_18006C40C
0x18006c0b8  mov     rdi, [rsp+68h+var_28]
0x18006c0bd  mov     rax, [rdi]
0x18006c0c0  mov     rbx, [rax+30h]
0x18006c0c4  xor     edx, edx
0x18006c0c6  lea     rcx, [rsp+68h+var_48]
0x18006c0cb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18006c0d0  lea     rdx, [rsp+68h+var_48]
0x18006c0d5  mov     rcx, rdi
0x18006c0d8  mov     rax, rbx
0x18006c0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c0e0  mov     ebx, eax
0x18006c0e2  test    eax, eax
0x18006c0e4  jns     short loc_18006C13D
0x18006c0e6  mov     rcx, [rsp+68h]; this
0x18006c0eb  mov     r9d, eax; char *
0x18006c0ee  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006c0f5  mov     edx, 25Ch; void *
0x18006c0fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c0ff  nop
0x18006c100  lea     rcx, [rsp+68h+var_28]
0x18006c105  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006c10a  nop
0x18006c10b  lea     rcx, [rsp+68h+string]; this
0x18006c110  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006c115  nop
0x18006c116  lea     rcx, [rsp+68h+var_48]; this
0x18006c11b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006c120  nop
0x18006c121  lea     rcx, [rsp+68h+var_38]
0x18006c126  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c12b  nop
0x18006c12c  lea     rcx, [rsp+68h+var_30]
0x18006c131  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c136  mov     eax, ebx
0x18006c138  jmp     loc_18006C40C
0x18006c13d  mov     rdi, [rsp+68h+var_28]
0x18006c142  mov     rax, [rdi]
0x18006c145  mov     rbx, [rax+38h]
0x18006c149  xor     edx, edx
0x18006c14b  lea     rcx, [rsp+68h+string]
0x18006c150  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18006c155  lea     rdx, [rsp+68h+string]
0x18006c15a  mov     rcx, rdi
0x18006c15d  mov     rax, rbx
0x18006c160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c165  mov     ebx, eax
0x18006c167  test    eax, eax
0x18006c169  jns     short loc_18006C1C2
0x18006c16b  mov     rcx, [rsp+68h]; this
0x18006c170  mov     r9d, eax; char *
0x18006c173  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006c17a  mov     edx, 25Dh; void *
0x18006c17f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c184  nop
0x18006c185  lea     rcx, [rsp+68h+var_28]
0x18006c18a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006c18f  nop
0x18006c190  lea     rcx, [rsp+68h+string]; this
0x18006c195  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006c19a  nop
0x18006c19b  lea     rcx, [rsp+68h+var_48]; this
0x18006c1a0  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006c1a5  nop
0x18006c1a6  lea     rcx, [rsp+68h+var_38]
0x18006c1ab  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c1b0  nop
0x18006c1b1  lea     rcx, [rsp+68h+var_30]
0x18006c1b6  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c1bb  mov     eax, ebx
0x18006c1bd  jmp     loc_18006C40C
0x18006c1c2  xor     edx, edx; length
0x18006c1c4  mov     rcx, [rsp+68h+string]; string
0x18006c1c9  call    cs:__imp_WindowsGetStringRawBuffer
0x18006c1cf  mov     rbx, rax
0x18006c1d2  xor     edx, edx; length
0x18006c1d4  mov     rcx, [rsp+68h+var_48]; string
0x18006c1d9  call    cs:__imp_WindowsGetStringRawBuffer
0x18006c1df  mov     r9, rbx; unsigned __int16 *
0x18006c1e2  mov     r8, rax; unsigned __int16 *
0x18006c1e5  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18006c1ec  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18006c1f3  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18006c1f8  mov     ebx, eax
0x18006c1fa  test    eax, eax
0x18006c1fc  jns     short loc_18006C255
0x18006c1fe  mov     rcx, [rsp+68h]; this
0x18006c203  mov     r9d, eax; char *
0x18006c206  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006c20d  mov     edx, 25Eh; void *
0x18006c212  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c217  nop
0x18006c218  lea     rcx, [rsp+68h+var_28]
0x18006c21d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006c222  nop
0x18006c223  lea     rcx, [rsp+68h+string]; this
0x18006c228  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006c22d  nop
0x18006c22e  lea     rcx, [rsp+68h+var_48]; this
0x18006c233  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006c238  nop
0x18006c239  lea     rcx, [rsp+68h+var_38]
0x18006c23e  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c243  nop
0x18006c244  lea     rcx, [rsp+68h+var_30]
0x18006c249  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c24e  mov     eax, ebx
0x18006c250  jmp     loc_18006C40C
0x18006c255  mov     rcx, [rsp+68h+var_38]
0x18006c25a  mov     rax, [rcx]
0x18006c25d  lea     rdx, [rsp+68h+var_40]
0x18006c262  mov     rax, [rax+40h]
0x18006c266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c26b  mov     ebx, eax
0x18006c26d  test    eax, eax
0x18006c26f  jns     short loc_18006C2C8
0x18006c271  mov     rcx, [rsp+68h]; this
0x18006c276  mov     r9d, eax; char *
0x18006c279  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006c280  mov     edx, 25Fh; void *
0x18006c285  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c28a  nop
0x18006c28b  lea     rcx, [rsp+68h+var_28]
0x18006c290  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006c295  nop
0x18006c296  lea     rcx, [rsp+68h+string]; this
0x18006c29b  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006c2a0  nop
0x18006c2a1  lea     rcx, [rsp+68h+var_48]; this
0x18006c2a6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006c2ab  nop
0x18006c2ac  lea     rcx, [rsp+68h+var_38]
0x18006c2b1  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c2b6  nop
0x18006c2b7  lea     rcx, [rsp+68h+var_30]
0x18006c2bc  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c2c1  mov     eax, ebx
0x18006c2c3  jmp     loc_18006C40C
0x18006c2c8  lea     rcx, [rsp+68h+var_28]
0x18006c2cd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006c2d2  nop
0x18006c2d3  lea     rcx, [rsp+68h+string]; this
0x18006c2d8  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006c2dd  nop
0x18006c2de  lea     rcx, [rsp+68h+var_48]; this
0x18006c2e3  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18006c2e8  jmp     loc_18006C00F
0x18006c2ed  sub     esi, 1
0x18006c2f0  jz      loc_18006C3A3
0x18006c2f6  sub     esi, 1
0x18006c2f9  jz      short loc_18006C357
0x18006c2fb  cmp     esi, 1
0x18006c2fe  jnz     loc_18006C3EF
0x18006c304  lea     r8, aEnableexpedite_2; "EnableExpeditedUpdateDeferred"
0x18006c30b  lea     rdx, aSoftwareMicros_14; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18006c312  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x18006c317  mov     ebx, eax
0x18006c319  test    eax, eax
0x18006c31b  jns     loc_18006C3EF
0x18006c321  mov     rcx, [rsp+68h]; this
0x18006c326  mov     r9d, eax; char *
0x18006c329  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006c330  mov     edx, 26Bh; void *
0x18006c335  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c33a  nop
0x18006c33b  lea     rcx, [rsp+68h+var_38]
0x18006c340  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c345  nop
0x18006c346  lea     rcx, [rsp+68h+var_30]
0x18006c34b  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c350  mov     eax, ebx
0x18006c352  jmp     loc_18006C40C
0x18006c357  lea     r8, aEnableexpedite_1; "EnableExpeditedUpdateAsync"
0x18006c35e  lea     rdx, aSoftwareMicros_14; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18006c365  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x18006c36a  mov     ebx, eax
0x18006c36c  test    eax, eax
0x18006c36e  jns     short loc_18006C3EF
0x18006c370  mov     rcx, [rsp+68h]; this
0x18006c375  mov     r9d, eax; char *
0x18006c378  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006c37f  mov     edx, 268h; void *
0x18006c384  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c389  nop
0x18006c38a  lea     rcx, [rsp+68h+var_38]
0x18006c38f  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c394  nop
0x18006c395  lea     rcx, [rsp+68h+var_30]
0x18006c39a  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18006c39f  mov     eax, ebx
0x18006c3a1  jmp     short loc_18006C40C
0x18006c3a3  lea     r8, aEnableexpedite; "EnableExpeditedUpdateSync"
0x18006c3aa  lea     rdx, aSoftwareMicros_14; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18006c3b1  call    ?SHRegSetBOOL@@YAJPEAUHKEY__@@PEBG1H@Z; SHRegSetBOOL(HKEY__ *,ushort const *,ushort const *,int)
0x18006c3b6  mov     ebx, eax
0x18006c3b8  test    eax, eax
0x18006c3ba  jns     short loc_18006C3EF
0x18006c3bc  mov     rcx, [rsp+68h]; this
0x18006c3c1  mov     r9d, eax; char *
0x18006c3c4  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18006c3cb  mov     edx, 265h; void *
0x18006c3d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c3d5  nop
  ... truncated ...
```
