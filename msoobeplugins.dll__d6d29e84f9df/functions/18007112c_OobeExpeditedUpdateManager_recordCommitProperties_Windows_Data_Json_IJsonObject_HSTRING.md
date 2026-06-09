# OobeExpeditedUpdateManager::_recordCommitProperties(Windows::Data::Json::IJsonObject *,HSTRING__ *)

- ea: `0x18007112c`
- end: `0x180071621`
- name: `?_recordCommitProperties@OobeExpeditedUpdateManager@@AEAAJPEAUIJsonObject@Json@Data@Windows@@PEAUHSTRING__@@@Z`
- size: `1269`
- prototype: `int(OobeExpeditedUpdateManager *__hidden this, struct Windows::Data::Json::IJsonObject *, HSTRING)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180064990`

## callees

- `0x180003470`
- `0x180007bbc`
- `0x180008544`
- `0x18001ad08`
- `0x18001de58`
- `0x180040898`
- `0x1800418d8`
- `0x180043c58`
- `0x180046c9c`
- `0x1800616cc`
- `0x18007112c`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071372`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071381`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007138f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800713ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800713fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071460`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007146e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071372`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071381`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007138f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800713ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800713fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180071460`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007146e`

## string_xrefs

- `0x18007119c`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x1800711dd`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x180071423`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x1800714d3`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x180071550`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x18007156a`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`
- `0x1800715bf`: `shell\oobe\machine\plugins\adapters\com\oobeexpeditedupdatemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall OobeExpeditedUpdateManager::_recordCommitProperties(
        OobeExpeditedUpdateManager *this,
        struct Windows::Data::Json::IJsonObject *a2,
        HSTRING a3)
{
  __int64 (__fastcall *v5)(struct Windows::Data::Json::IJsonObject *, PVOID, _QWORD); // rbx
  HSTRING_HEADER *v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // eax
  char v15; // al
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64 **); // rbx
  int v18; // eax
  __int64 *v19; // rdi
  __int64 (__fastcall *v20)(__int64 *, HSTRING *); // rbx
  int v21; // eax
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rbx
  int v26; // eax
  const unsigned __int16 *v27; // rdi
  const unsigned __int16 *v28; // rbx
  const unsigned __int16 *v29; // rax
  unsigned int v30; // edi
  const unsigned __int16 *v31; // rbx
  const unsigned __int16 *v32; // rax
  __int64 v33; // rdx
  unsigned int v34; // edi
  const unsigned __int16 *StringRawBuffer; // rbx
  const unsigned __int16 *v36; // rax
  __int64 v37; // rdx
  HSTRING_HEADER v39; // [rsp+28h] [rbp-59h] BYREF
  char v40; // [rsp+48h] [rbp-39h] BYREF
  _BYTE v41[7]; // [rsp+49h] [rbp-38h] BYREF
  __int64 v42; // [rsp+50h] [rbp-31h] BYREF
  __int64 (__fastcall ***v43)(_QWORD, GUID *, _QWORD *); // [rsp+58h] [rbp-29h] BYREF
  __int64 v44; // [rsp+60h] [rbp-21h] BYREF
  HSTRING v45; // [rsp+68h] [rbp-19h] BYREF
  __int64 *v46; // [rsp+70h] [rbp-11h] BYREF
  __int64 *v47; // [rsp+78h] [rbp-9h] BYREF
  HSTRING string; // [rsp+80h] [rbp-1h] BYREF
  int v49; // [rsp+88h] [rbp+7h] BYREF
  __int64 (__fastcall ***v50)(_QWORD, GUID *, _QWORD); // [rsp+90h] [rbp+Fh] BYREF
  double v51; // [rsp+98h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]

  v5 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, _QWORD))(*(_QWORD *)a2 + 64LL);
  v50 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v39, (const WCHAR **)off_1800D1870, (char)a3);
  v7 = v5(a2, v6[1].Reserved.Reserved1, &v50);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x456,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
      (const char *)(unsigned int)v7,
      (int)v39.Reserved.Reserved1);
LABEL_47:
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v50);
    return v8;
  }
  v43 = 0;
  v9 = (**v50)(v50, &GUID_c9d9a725_786b_5113_b4b7_9b61764c220b, &v43);
  v8 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45A,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
      (const char *)(unsigned int)v9,
      (int)v39.Reserved.Reserved1);
LABEL_46:
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v43);
    goto LABEL_47;
  }
  wil::com_copy<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>,wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>,wil::err_returncode_policy> &>(
    &v47,
    &v43);
  v42 = 0;
  v10 = *v47;
  v42 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v10 + 48))(v47, &v42);
  v8 = v11;
  if ( v11 < 0 )
  {
    v12 = (unsigned int)v11;
    v13 = 1119;
    goto LABEL_44;
  }
  v40 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v42 + 56LL))(v42, &v40);
  v8 = v14;
  if ( v14 < 0 )
  {
    v12 = (unsigned int)v14;
    v13 = 1121;
    goto LABEL_44;
  }
  v15 = v40;
  if ( !v40 )
  {
    v8 = -2147024809;
    v12 = 2147942487LL;
    v13 = 1122;
LABEL_44:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
      (const char *)v12,
      (int)v39.Reserved.Reserved1);
LABEL_45:
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v42);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v47);
    goto LABEL_46;
  }
  while ( v15 )
  {
    v46 = 0;
    v16 = v42;
    v17 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v42 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    v18 = v17(v16, &v46);
    v8 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x468,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
        (const char *)(unsigned int)v18,
        (int)v39.Reserved.Reserved1);
      goto LABEL_41;
    }
    v45 = 0;
    v19 = v46;
    v20 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*v46 + 48);
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &v45,
      0);
    v21 = v20(v19, &v45);
    v8 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46A,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
        (const char *)(unsigned int)v21,
        (int)v39.Reserved.Reserved1);
      goto LABEL_31;
    }
    v44 = 0;
    v22 = *v46;
    v44 = 0;
    v23 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v22 + 56))(v46, &v44);
    v8 = v23;
    if ( v23 < 0 )
    {
      v33 = 1132;
      goto LABEL_23;
    }
    v49 = 0;
    v23 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v44 + 48LL))(v44, &v49);
    v8 = v23;
    if ( v23 < 0 )
    {
      v33 = 1135;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v33,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
        (const char *)(unsigned int)v23,
        (int)v39.Reserved.Reserved1);
      goto LABEL_30;
    }
    if ( v49 == 1 )
    {
      v41[0] = 0;
      v23 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v44 + 80LL))(v44, v41);
      v8 = v23;
      if ( v23 < 0 )
      {
        v33 = 1140;
        goto LABEL_23;
      }
      v34 = v41[0];
      StringRawBuffer = WindowsGetStringRawBuffer(v45, 0);
      v36 = WindowsGetStringRawBuffer(a3, 0);
      v23 = SHRegSetDWORD(HKEY_LOCAL_MACHINE, v36, StringRawBuffer, v34);
      v8 = v23;
      if ( v23 < 0 )
      {
        v33 = 1141;
        goto LABEL_23;
      }
    }
    else if ( v49 == 2 )
    {
      v51 = 0.0;
      v23 = (*(__int64 (__fastcall **)(__int64, double *))(*(_QWORD *)v44 + 72LL))(v44, &v51);
      v8 = v23;
      if ( v23 < 0 )
      {
        v33 = 1145;
        goto LABEL_23;
      }
      v30 = (int)v51;
      v31 = WindowsGetStringRawBuffer(v45, 0);
      v32 = WindowsGetStringRawBuffer(a3, 0);
      v23 = SHRegSetDWORD(HKEY_LOCAL_MACHINE, v32, v31, v30);
      v8 = v23;
      if ( v23 < 0 )
      {
        v33 = 1146;
        goto LABEL_23;
      }
    }
    else
    {
      string = 0;
      v24 = v44;
      v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v44 + 64LL);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      v26 = v25(v24, &string);
      v8 = v26;
      if ( v26 < 0 )
      {
        v37 = 1151;
LABEL_29:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v37,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\oobeexpeditedupdatemanager.cpp",
          (const char *)(unsigned int)v26,
          (int)v39.Reserved.Reserved1);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
LABEL_30:
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v44);
LABEL_31:
        Windows::Internal::String::~String((Windows::Internal::String *)&v45);
LABEL_41:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
        goto LABEL_45;
      }
      v27 = WindowsGetStringRawBuffer(string, 0);
      v28 = WindowsGetStringRawBuffer(v45, 0);
      v29 = WindowsGetStringRawBuffer(a3, 0);
      v26 = SHRegSetString(HKEY_LOCAL_MACHINE, v29, v28, v27);
      v8 = v26;
      if ( v26 < 0 )
      {
        v37 = 1152;
        goto LABEL_29;
      }
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
    }
    v23 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v42 + 64LL))(v42, &v40);
    v8 = v23;
    if ( v23 < 0 )
    {
      v33 = 1156;
      goto LABEL_23;
    }
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v44);
    Windows::Internal::String::~String((Windows::Internal::String *)&v45);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    v15 = v40;
  }
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v42);
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v47);
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v43);
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v50);
  return 0;
}

```

## disassembly

```asm
0x18007112c  mov     rax, rsp
0x18007112f  mov     [rax+8], rbx
0x180071133  push    rbp
0x180071134  push    rsi
0x180071135  push    rdi
0x180071136  push    r14
0x180071138  push    r15
0x18007113a  lea     rbp, [rax-5Fh]
0x18007113e  sub     rsp, 0B0h
0x180071145  movaps  xmmword ptr [rax-38h], xmm6
0x180071149  mov     rax, cs:__security_cookie
0x180071150  xor     rax, rsp
0x180071153  mov     [rbp+57h+var_38], rax
0x180071157  mov     rsi, r8
0x18007115a  mov     rdi, rdx
0x18007115d  mov     rax, [rdx]
0x180071160  mov     rbx, [rax+40h]
0x180071164  xor     r14d, r14d
0x180071167  mov     [rbp+57h+var_48], r14
0x18007116b  lea     rdx, off_1800D1870; "CommitProperties"
0x180071172  lea     rcx, [rbp+57h+var_B0]
0x180071176  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18007117b  nop
0x18007117c  lea     r8, [rbp+57h+var_48]
0x180071180  mov     rdx, [rax+18h]
0x180071184  mov     rcx, rdi
0x180071187  mov     rax, rbx
0x18007118a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007118f  mov     ebx, eax
0x180071191  test    eax, eax
0x180071193  jns     short loc_1800711B2
0x180071195  mov     rcx, [rbp+5Fh]; this
0x180071199  mov     r9d, eax; char *
0x18007119c  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800711a3  mov     edx, 456h; void *
0x1800711a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800711ad  jmp     loc_1800715EE
0x1800711b2  mov     [rbp+57h+var_80], r14
0x1800711b6  mov     rcx, [rbp+57h+var_48]
0x1800711ba  mov     rax, [rcx]
0x1800711bd  lea     r8, [rbp+57h+var_80]
0x1800711c1  lea     rdx, _GUID_c9d9a725_786b_5113_b4b7_9b61764c220b
0x1800711c8  mov     rax, [rax]
0x1800711cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800711d0  mov     ebx, eax
0x1800711d2  test    eax, eax
0x1800711d4  jns     short loc_1800711F3
0x1800711d6  mov     rcx, [rbp+5Fh]; this
0x1800711da  mov     r9d, eax; char *
0x1800711dd  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800711e4  mov     edx, 45Ah; void *
0x1800711e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800711ee  jmp     loc_1800715E4
0x1800711f3  lea     rdx, [rbp+57h+var_80]
0x1800711f7  lea     rcx, [rbp+57h+var_60]
0x1800711fb  call    ??$com_copy@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@AEAV?$com_ptr_t@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@@wil@@YA?AV?$com_ptr_t@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@0@AEAV?$com_ptr_t@U?$IMap@PEAUHSTRING__@@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@0@@Z; wil::com_copy<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,Windows::Data::Json::IJsonValue *> *>,wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>,wil::err_returncode_policy> &>(wil::com_ptr_t<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>,wil::err_returncode_policy> &)
0x180071200  nop
0x180071201  mov     [rbp+57h+var_88], r14
0x180071205  mov     rcx, [rbp+57h+var_60]
0x180071209  mov     rax, [rcx]
0x18007120c  mov     [rbp+57h+var_88], r14
0x180071210  lea     rdx, [rbp+57h+var_88]
0x180071214  mov     rax, [rax+30h]
0x180071218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007121d  mov     ebx, eax
0x18007121f  test    eax, eax
0x180071221  jns     short loc_180071230
0x180071223  mov     r9d, eax
0x180071226  mov     edx, 45Fh
0x18007122b  jmp     loc_1800715BF
0x180071230  mov     [rbp+57h+var_90], r14b
0x180071234  mov     rcx, [rbp+57h+var_88]
0x180071238  mov     rax, [rcx]
0x18007123b  lea     rdx, [rbp+57h+var_90]
0x18007123f  mov     rax, [rax+38h]
0x180071243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071248  mov     ebx, eax
0x18007124a  test    eax, eax
0x18007124c  jns     short loc_18007125B
0x18007124e  mov     r9d, eax
0x180071251  mov     edx, 461h
0x180071256  jmp     loc_1800715BF
0x18007125b  mov     al, [rbp+57h+var_90]
0x18007125e  test    al, al
0x180071260  jz      loc_1800715B2
0x180071266  mov     r15, 0FFFFFFFF80000002h
0x18007126d  xorps   xmm6, xmm6
0x180071270  test    al, al
0x180071272  jz      loc_180071587
0x180071278  mov     [rbp+57h+var_68], r14
0x18007127c  mov     rdi, [rbp+57h+var_88]
0x180071280  mov     rax, [rdi]
0x180071283  mov     rbx, [rax+30h]
0x180071287  lea     rcx, [rbp+57h+var_68]
0x18007128b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180071290  lea     rdx, [rbp+57h+var_68]
0x180071294  mov     rcx, rdi
0x180071297  mov     rax, rbx
0x18007129a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007129f  mov     ebx, eax
0x1800712a1  test    eax, eax
0x1800712a3  js      loc_180071563
0x1800712a9  mov     [rbp+57h+var_70], r14
0x1800712ad  mov     rdi, [rbp+57h+var_68]
0x1800712b1  mov     rax, [rdi]
0x1800712b4  mov     rbx, [rax+30h]
0x1800712b8  xor     edx, edx
0x1800712ba  lea     rcx, [rbp+57h+var_70]
0x1800712be  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800712c3  lea     rdx, [rbp+57h+var_70]
0x1800712c7  mov     rcx, rdi
0x1800712ca  mov     rax, rbx
0x1800712cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800712d2  mov     ebx, eax
0x1800712d4  test    eax, eax
0x1800712d6  js      loc_180071549
0x1800712dc  mov     [rbp+57h+var_78], r14
0x1800712e0  mov     rcx, [rbp+57h+var_68]
0x1800712e4  mov     rax, [rcx]
0x1800712e7  mov     [rbp+57h+var_78], r14
0x1800712eb  lea     rdx, [rbp+57h+var_78]
0x1800712ef  mov     rax, [rax+38h]
0x1800712f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800712f8  mov     ebx, eax
0x1800712fa  test    eax, eax
0x1800712fc  js      loc_18007153F
0x180071302  mov     [rbp+57h+var_50], r14d
0x180071306  mov     rcx, [rbp+57h+var_78]
0x18007130a  mov     rax, [rcx]
0x18007130d  lea     rdx, [rbp+57h+var_50]
0x180071311  mov     rax, [rax+30h]
0x180071315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007131a  mov     ebx, eax
0x18007131c  test    eax, eax
0x18007131e  js      loc_180071535
0x180071324  mov     ecx, [rbp+57h+var_50]
0x180071327  sub     ecx, 1
0x18007132a  jz      loc_180071434
0x180071330  cmp     ecx, 1
0x180071333  jz      loc_1800713BE
0x180071339  mov     [rbp+57h+string], r14
0x18007133d  mov     rdi, [rbp+57h+var_78]
0x180071341  mov     rax, [rdi]
0x180071344  mov     rbx, [rax+40h]
0x180071348  xor     edx, edx
0x18007134a  lea     rcx, [rbp+57h+string]
0x18007134e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180071353  lea     rdx, [rbp+57h+string]
0x180071357  mov     rcx, rdi
0x18007135a  mov     rax, rbx
0x18007135d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071362  mov     ebx, eax
0x180071364  test    eax, eax
0x180071366  js      loc_180071506
0x18007136c  xor     edx, edx; length
0x18007136e  mov     rcx, [rbp+57h+string]; string
0x180071372  call    cs:__imp_WindowsGetStringRawBuffer
0x180071378  mov     rdi, rax
0x18007137b  xor     edx, edx; length
0x18007137d  mov     rcx, [rbp+57h+var_70]; string
0x180071381  call    cs:__imp_WindowsGetStringRawBuffer
0x180071387  mov     rbx, rax
0x18007138a  xor     edx, edx; length
0x18007138c  mov     rcx, rsi; string
0x18007138f  call    cs:__imp_WindowsGetStringRawBuffer
0x180071395  mov     r9, rdi; unsigned __int16 *
0x180071398  mov     r8, rbx; unsigned __int16 *
0x18007139b  mov     rdx, rax; unsigned __int16 *
0x18007139e  mov     rcx, r15; HKEY
0x1800713a1  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1800713a6  mov     ebx, eax
0x1800713a8  test    eax, eax
0x1800713aa  js      loc_1800714CE
0x1800713b0  lea     rcx, [rbp+57h+string]; this
0x1800713b4  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800713b9  jmp     loc_18007148F
0x1800713be  movsd   [rbp+57h+var_40], xmm6
0x1800713c3  mov     rcx, [rbp+57h+var_78]
0x1800713c7  mov     rax, [rcx]
0x1800713ca  lea     rdx, [rbp+57h+var_40]
0x1800713ce  mov     rax, [rax+48h]
0x1800713d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800713d7  mov     ebx, eax
0x1800713d9  test    eax, eax
0x1800713db  js      loc_18007150D
0x1800713e1  cvttsd2si edi, [rbp+57h+var_40]
0x1800713e6  xor     edx, edx; length
0x1800713e8  mov     rcx, [rbp+57h+var_70]; string
0x1800713ec  call    cs:__imp_WindowsGetStringRawBuffer
0x1800713f2  mov     rbx, rax
0x1800713f5  xor     edx, edx; length
0x1800713f7  mov     rcx, rsi; string
0x1800713fa  call    cs:__imp_WindowsGetStringRawBuffer
0x180071400  mov     r9d, edi; unsigned int
0x180071403  mov     r8, rbx; unsigned __int16 *
0x180071406  mov     rdx, rax; unsigned __int16 *
0x180071409  mov     rcx, r15; HKEY
0x18007140c  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180071411  mov     ebx, eax
0x180071413  test    eax, eax
0x180071415  jns     short loc_18007148F
0x180071417  mov     edx, 47Ah; void *
0x18007141c  mov     rcx, [rbp+5Fh]; this
0x180071420  mov     r9d, eax; char *
0x180071423  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007142a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007142f  jmp     loc_1800714F1
0x180071434  mov     [rbp+57h+var_8F], r14b
0x180071438  mov     rcx, [rbp+57h+var_78]
0x18007143c  mov     rax, [rcx]
0x18007143f  lea     rdx, [rbp+57h+var_8F]
0x180071443  mov     rax, [rax+50h]
0x180071447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007144c  mov     ebx, eax
0x18007144e  test    eax, eax
0x180071450  js      loc_18007152B
0x180071456  movzx   edi, [rbp+57h+var_8F]
0x18007145a  xor     edx, edx; length
0x18007145c  mov     rcx, [rbp+57h+var_70]; string
0x180071460  call    cs:__imp_WindowsGetStringRawBuffer
0x180071466  mov     rbx, rax
0x180071469  xor     edx, edx; length
0x18007146b  mov     rcx, rsi; string
0x18007146e  call    cs:__imp_WindowsGetStringRawBuffer
0x180071474  mov     r9d, edi; unsigned int
0x180071477  mov     r8, rbx; unsigned __int16 *
0x18007147a  mov     rdx, rax; unsigned __int16 *
0x18007147d  mov     rcx, r15; HKEY
0x180071480  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180071485  mov     ebx, eax
0x180071487  test    eax, eax
0x180071489  js      loc_180071521
0x18007148f  mov     rcx, [rbp+57h+var_88]
0x180071493  mov     rax, [rcx]
0x180071496  lea     rdx, [rbp+57h+var_90]
0x18007149a  mov     rax, [rax+40h]
0x18007149e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800714a3  mov     ebx, eax
0x1800714a5  test    eax, eax
0x1800714a7  js      short loc_180071517
0x1800714a9  lea     rcx, [rbp+57h+var_78]
0x1800714ad  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800714b2  nop
0x1800714b3  lea     rcx, [rbp+57h+var_70]; this
0x1800714b7  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800714bc  nop
0x1800714bd  lea     rcx, [rbp+57h+var_68]
0x1800714c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800714c6  mov     al, [rbp+57h+var_90]
0x1800714c9  jmp     loc_180071270
0x1800714ce  mov     edx, 480h; void *
0x1800714d3  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x1800714da  mov     r9d, eax; char *
0x1800714dd  mov     rcx, [rbp+5Fh]; this
0x1800714e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800714e6  nop
0x1800714e7  lea     rcx, [rbp+57h+string]; this
0x1800714eb  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800714f0  nop
0x1800714f1  lea     rcx, [rbp+57h+var_78]
0x1800714f5  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800714fa  nop
0x1800714fb  lea     rcx, [rbp+57h+var_70]; this
0x1800714ff  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180071504  jmp     short loc_18007157C
0x180071506  mov     edx, 47Fh
0x18007150b  jmp     short loc_1800714D3
0x18007150d  mov     edx, 479h
0x180071512  jmp     loc_18007141C
0x180071517  mov     edx, 484h
0x18007151c  jmp     loc_18007141C
0x180071521  mov     edx, 475h
0x180071526  jmp     loc_18007141C
0x18007152b  mov     edx, 474h
0x180071530  jmp     loc_18007141C
0x180071535  mov     edx, 46Fh
0x18007153a  jmp     loc_18007141C
0x18007153f  mov     edx, 46Ch
0x180071544  jmp     loc_18007141C
0x180071549  mov     rcx, [rbp+5Fh]; this
0x18007154d  mov     r9d, eax; char *
0x180071550  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x180071557  mov     edx, 46Ah; void *
0x18007155c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071561  jmp     short loc_1800714FB
0x180071563  mov     rcx, [rbp+5Fh]; this
0x180071567  mov     r9d, eax; char *
0x18007156a  lea     r8, aShellOobeMachi_20; "shell\\oobe\\machine\\plugins\\adapters"...
0x180071571  mov     edx, 468h; void *
0x180071576  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007157b  nop
0x18007157c  lea     rcx, [rbp+57h+var_68]
0x180071580  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180071585  jmp     short loc_1800715D0
0x180071587  lea     rcx, [rbp+57h+var_88]
0x18007158b  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180071590  nop
0x180071591  lea     rcx, [rbp+57h+var_60]
0x180071595  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007159a  nop
  ... truncated ...
```
