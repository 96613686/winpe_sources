# ReadJsonFile(bool,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x1400122f8`
- end: `0x140012a8c`
- name: `?ReadJsonFile@@YAJ_NPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11@Z`
- size: `1940`
- prototype: `__int64 __fastcall(char, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140007ad8`
- `0x14000b0cc`

## callees

- `0x140002f40`
- `0x140003ab8`
- `0x140004e1c`
- `0x1400052fc`
- `0x140005cac`
- `0x14000a49c`
- `0x14000a4bc`
- `0x14000cc54`
- `0x14000dda4`
- `0x14000ddb4`
- `0x14000df28`
- `0x14000e280`
- `0x140011ba0`
- `0x140011d3c`
- `0x140011fe4`
- `0x140012214`
- `0x14001225c`
- `0x1400122f8`
- `0x140012d94`
- `0x14001a010`

## import_xrefs

- `msvcp_win!?read@?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@PEAG_J@Z` at `0x140012673`
- `msvcp_win!?read@?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@PEAG_J@Z` at `0x140012673`
- `msvcp_win!?seekg@?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@_JH@Z` at `0x1400125b8`
- `msvcp_win!?seekg@?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@_JH@Z` at `0x14001264e`
- `msvcp_win!?seekg@?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@_JH@Z` at `0x1400125b8`
- `msvcp_win!?seekg@?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@_JH@Z` at `0x14001264e`
- `msvcp_win!?tellg@?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x1400125c9`
- `msvcp_win!?tellg@?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x1400125c9`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x14001269b`
- `msvcp_win!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x14001269b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140012a85`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140012a85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400128e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14001296d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140012a40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400128e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14001296d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140012a40`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14001238a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400126de`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14001238a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400126de`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x140012503`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x140012503`

## string_xrefs

- `0x140012519`: `DirectXDbVersion.json`
- `0x14001292b`: `URLSUBPATH`
- `0x1400126b8`: `Windows.Data.Json.JsonObject`
- `0x140012416`: `onecore\windows\directx\database\updater\exe\onesettingshelper.cpp`
- `0x14001257c`: `onecore\windows\directx\database\updater\exe\onesettingshelper.cpp`
- `0x1400126f4`: `onecore\windows\directx\database\updater\exe\onesettingshelper.cpp`
- `0x1400127b1`: `onecore\windows\directx\database\updater\exe\onesettingshelper.cpp`
- `0x1400129ed`: `onecore\windows\directx\database\updater\exe\onesettingshelper.cpp`

## pseudocode

```c
__int64 __fastcall ReadJsonFile(char a1, __int64 a2, __int64 a3, __int64 a4)
{
  int JsonObjSize; // eax
  unsigned int LastError; // edi
  __int64 v9; // rdx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64, __int64 *); // rbx
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int BasicProfileFolderPath; // eax
  __int64 v14; // rdx
  const char *v15; // r9
  _QWORD *v16; // rax
  unsigned __int64 v17; // r9
  __int64 v18; // rax
  __int64 v19; // r9
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // r10
  __int64 v23; // rdx
  _WORD *v24; // rdi
  __int64 i; // rcx
  __int64 v26; // rax
  int ActivationFactory; // eax
  _QWORD *v28; // rdi
  __int64 v29; // rbx
  char v30; // al
  const WCHAR *p_hstringHeader; // rdx
  unsigned __int64 v32; // r9
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, __int64, __int64 *); // rbx
  __int64 v37; // rcx
  __int64 v38; // rbx
  __int64 (__fastcall *v39)(__int64, __int64, HSTRING *); // rdi
  PCWSTR StringRawBuffer; // rax
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rbx
  __int64 (__fastcall *v44)(__int64, __int64, HSTRING *); // rdi
  PCWSTR v45; // rax
  __int64 v46; // rax
  __int64 v47; // rcx
  __int64 v48; // rbx
  __int64 (__fastcall *v49)(__int64, __int64, HSTRING *); // rdi
  PCWSTR v51; // rax
  __int64 v52; // rax
  __int64 v53; // rcx
  const char *v54; // [rsp+20h] [rbp-E0h]
  __int64 v55; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v56; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v57; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v58; // [rsp+48h] [rbp-B8h] BYREF
  int v59; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v60; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v62; // [rsp+68h] [rbp-98h] BYREF
  HSTRING v63[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v64[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v65[128]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v66; // [rsp+110h] [rbp+10h]
  HSTRING_HEADER hstringHeader; // [rsp+190h] [rbp+90h] BYREF
  __int64 v68; // [rsp+1A8h] [rbp+A8h]
  HSTRING_HEADER v69; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v70; // [rsp+1C8h] [rbp+C8h]
  _BYTE v71[528]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int16 v72[264]; // [rsp+3E0h] [rbp+2E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+638h] [rbp+538h]

  v56 = 0;
  v55 = 0;
  if ( !a1 || g_bForceWeekly )
  {
    memset_0(v71, 0, 0x208u);
    BasicProfileFolderPath = GetBasicProfileFolderPath(4, 0, v71, 260);
    LastError = BasicProfileFolderPath;
    if ( BasicProfileFolderPath >= 0 )
    {
      v54 = L"Microsoft\\Windows\\OneSettings";
      BasicProfileFolderPath = StringCchPrintfW(v72, 0x104u, L"%ws\\%ws\\%ws", v71);
      LastError = BasicProfileFolderPath;
      if ( BasicProfileFolderPath >= 0 )
      {
        std::basic_ifstream<unsigned short>::basic_ifstream<unsigned short>(v64, v72);
        if ( v66 )
        {
          std::wstring::wstring(&hstringHeader);
          std::basic_istream<unsigned short>::seekg(v64, 0, 2);
          v16 = (_QWORD *)std::basic_istream<unsigned short>::tellg(v64, &v69);
          v17 = *v16 + v16[1];
          if ( v17 > *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] )
          {
            if ( v17 - *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] > v68
                                                                        - *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] )
            {
              std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(
                &hstringHeader,
                v17 - *(_QWORD *)&hstringHeader.Reserved.Reserved2[16],
                v17 - *(_QWORD *)&hstringHeader.Reserved.Reserved2[16],
                v17 - *(_QWORD *)&hstringHeader.Reserved.Reserved2[16]);
            }
            else
            {
              *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = *v16 + v16[1];
              v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
              v24 = (_WORD *)(v22 + 2 * v23);
              if ( v20 )
              {
                for ( i = v20; i; --i )
                  *v24++ = 0;
              }
              *(_WORD *)(v22 + 2 * v21) = 0;
            }
          }
          else
          {
            *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = *v16 + v16[1];
            v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
            *(_WORD *)(v18 + 2 * v19) = 0;
          }
          std::basic_istream<unsigned short>::seekg(v64, 0, 0);
          if ( *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] )
          {
            v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&hstringHeader);
            std::basic_istream<unsigned short>::read(v64, v26);
          }
          if ( !std::basic_filebuf<unsigned short>::close(v65) )
            std::basic_ios<unsigned short>::setstate((char *)v64 + *(int *)(v64[0] + 4LL), 2, 0);
          v58 = 0;
          v70 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(
            &v69,
            L"Windows.Data.Json.JsonObject",
            0x1Du,
            0x1Cu);
          ActivationFactory = RoGetActivationFactory(v70, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v58);
          LastError = ActivationFactory;
          if ( ActivationFactory >= 0 )
          {
            v57 = 0;
            v28 = v58;
            v29 = *v58;
            v57 = 0;
            v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Large_mode_engaged(&hstringHeader);
            p_hstringHeader = (const WCHAR *)&hstringHeader;
            if ( v30 )
              p_hstringHeader = (const WCHAR *)hstringHeader.Reserved.Reserved1;
            v70 = 0;
            v32 = -1;
            do
              ++v32;
            while ( p_hstringHeader[v32] );
            if ( v32 > 0xFFFFFFFF || (int)v32 + 1 < (unsigned int)v32 )
            {
              RaiseException(0x80070216, 1u, 0, 0);
              JUMPOUT(0x140012A8BLL);
            }
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v69, p_hstringHeader, v32 + 1, v32);
            v33 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *))(v29 + 48))(v28, v70, &v57);
            LastError = v33;
            if ( v33 >= 0 )
            {
              v35 = v57;
              v36 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v57 + 64LL);
              v37 = v55;
              v55 = 0;
              if ( v37 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
              v70 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v69, L"settings", 9u, 8u);
              v33 = v36(v35, v70, &v55);
              LastError = v33;
              if ( v33 >= 0 )
              {
                wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v57);
                wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v58);
                std::wstring::_Tidy_deallocate(&hstringHeader);
                std::basic_ifstream<unsigned short>::`vbase destructor'(v64);
                goto LABEL_55;
              }
              v34 = 107;
            }
            else
            {
              v34 = 106;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v34,
              (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\onesettingshelper.cpp",
              (const char *)(unsigned int)v33,
              (int)L"Microsoft\\Windows\\OneSettings");
            wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v57);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x67,
              (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\onesettingshelper.cpp",
              (const char *)(unsigned int)ActivationFactory,
              (int)L"Microsoft\\Windows\\OneSettings");
          }
          wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v58);
          std::wstring::_Tidy_deallocate(&hstringHeader);
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x59,
                        (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\onesettingshelper.cpp",
                        v15);
        }
        std::basic_ifstream<unsigned short>::`vbase destructor'(v64);
        goto LABEL_67;
      }
      v14 = 86;
    }
    else
    {
      v14 = 83;
    }
LABEL_66:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\onesettingshelper.cpp",
      (const char *)(unsigned int)BasicProfileFolderPath,
      (int)v54);
    goto LABEL_67;
  }
  v60 = 0;
  v68 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Flighting.OneSettings.OneSettingsPayload",
    0x3Au,
    0x39u);
  JsonObjSize = RoGetActivationFactory(v68, &GUID_d70cd0ed_0f1b_4bec_9bec_c230dc7996b0, &v60);
  LastError = JsonObjSize;
  if ( JsonObjSize < 0 )
  {
    v9 = 48;
    goto LABEL_7;
  }
  v10 = v60;
  v11 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v60 + 48LL);
  v56 = 0;
  v68 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"DXDB", 5u, 4u);
  JsonObjSize = v11(v10, v68, &v56);
  LastError = JsonObjSize;
  if ( JsonObjSize < 0 )
  {
    v9 = 50;
    goto LABEL_7;
  }
  v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v56 + 96LL);
  v55 = 0;
  JsonObjSize = v12(v56, &v55);
  LastError = JsonObjSize;
  if ( JsonObjSize < 0 )
  {
    v9 = 58;
    goto LABEL_7;
  }
  v59 = 0;
  JsonObjSize = GetJsonObjSize(&v55, &v59);
  LastError = JsonObjSize;
  if ( JsonObjSize < 0 )
  {
    v9 = 61;
    goto LABEL_7;
  }
  if ( !v59 )
  {
    JsonObjSize = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v56 + 112LL))(v56);
    LastError = JsonObjSize;
    if ( JsonObjSize >= 0 )
    {
      LastError = 1;
      goto LABEL_16;
    }
    v9 = 65;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\onesettingshelper.cpp",
      (const char *)(unsigned int)JsonObjSize,
      (int)v54);
LABEL_16:
    wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v60);
LABEL_67:
    wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v55);
    wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v56);
    return LastError;
  }
  wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v60);
LABEL_55:
  if ( a2 )
  {
    string = 0;
    v38 = v55;
    v39 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v55 + 80LL);
    v70 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v69, L"VERSION", 8u, 7u);
    BasicProfileFolderPath = v39(v38, v70, &string);
    LastError = BasicProfileFolderPath;
    if ( BasicProfileFolderPath < 0 )
    {
      v14 = 116;
      goto LABEL_66;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v41 = std::_WChar_traits<unsigned short>::length(StringRawBuffer);
    std::wstring::_Assign<unsigned short>(a2, v42, v41);
  }
  if ( a3 )
  {
    v62 = 0;
    v43 = v55;
    v44 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v55 + 80LL);
    v70 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v69, L"URLSUBPATH", 0xBu, 0xAu);
    BasicProfileFolderPath = v44(v43, v70, &v62);
    LastError = BasicProfileFolderPath;
    if ( BasicProfileFolderPath < 0 )
    {
      v14 = 125;
      goto LABEL_66;
    }
    v45 = WindowsGetStringRawBuffer(v62, 0);
    v46 = std::_WChar_traits<unsigned short>::length(v45);
    std::wstring::_Assign<unsigned short>(a3, v47, v46);
  }
  if ( a4 )
  {
    v63[0] = 0;
    v48 = v55;
    v49 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v55 + 80LL);
    v70 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v69, L"HASHSTRINGV2", 0xDu, 0xCu);
    BasicProfileFolderPath = v49(v48, v70, v63);
    LastError = BasicProfileFolderPath;
    if ( BasicProfileFolderPath < 0 )
    {
      v14 = 134;
      goto LABEL_66;
    }
    v51 = WindowsGetStringRawBuffer(v63[0], 0);
    v52 = std::_WChar_traits<unsigned short>::length(v51);
    std::wstring::_Assign<unsigned short>(a4, v53, v52);
  }
  wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v55);
  wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v56);
  return 0;
}

```

## disassembly

```asm
0x1400122f8  push    rbp
0x1400122fa  push    rbx
0x1400122fb  push    rsi
0x1400122fc  push    rdi
0x1400122fd  push    r12
0x1400122ff  push    r14
0x140012301  push    r15
0x140012303  lea     rbp, [rsp-500h]
0x14001230b  sub     rsp, 600h
0x140012312  mov     rax, cs:__security_cookie
0x140012319  xor     rax, rsp
0x14001231c  mov     [rbp+530h+var_40], rax
0x140012323  mov     r15, r9
0x140012326  mov     r14, r8
0x140012329  mov     rsi, rdx
0x14001232c  xor     r12d, r12d
0x14001232f  mov     [rsp+630h+var_5F8], r12
0x140012334  mov     [rsp+630h+var_600], r12
0x140012339  test    cl, cl
0x14001233b  jz      loc_1400124DB
0x140012341  cmp     cs:?g_bForceWeekly@@3_NA, r12b; bool g_bForceWeekly
0x140012348  jnz     loc_1400124DB
0x14001234e  mov     [rsp+630h+var_5D8], r12
0x140012353  mov     [rbp+530h+var_488], r12
0x14001235a  lea     r9d, [r12+39h]; unsigned int
0x14001235f  lea     r8d, [r12+3Ah]; unsigned int
0x140012364  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsPayload@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x14001236b  lea     rcx, [rbp+530h+hstringHeader]; hstringHeader
0x140012372  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140012377  lea     r8, [rsp+630h+var_5D8]
0x14001237c  lea     rdx, _GUID_d70cd0ed_0f1b_4bec_9bec_c230dc7996b0
0x140012383  mov     rcx, [rbp+530h+var_488]
0x14001238a  call    cs:__imp_RoGetActivationFactory
0x140012390  mov     edi, eax
0x140012392  test    eax, eax
0x140012394  jns     short loc_14001239D
0x140012396  lea     edx, [r12+30h]
0x14001239b  jmp     short loc_14001240C
0x14001239d  mov     rdi, [rsp+630h+var_5D8]
0x1400123a2  mov     rax, [rdi]
0x1400123a5  mov     rbx, [rax+30h]
0x1400123a9  mov     rcx, [rsp+630h+var_5F8]
0x1400123ae  mov     [rsp+630h+var_5F8], r12
0x1400123b3  test    rcx, rcx
0x1400123b6  jz      short loc_1400123C5
0x1400123b8  mov     rax, [rcx]
0x1400123bb  mov     rax, [rax+10h]
0x1400123bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400123c4  nop
0x1400123c5  mov     [rbp+530h+var_488], r12
0x1400123cc  mov     r9d, 4; unsigned int
0x1400123d2  lea     r8d, [r9+1]; unsigned int
0x1400123d6  lea     rdx, sourceString; "DXDB"
0x1400123dd  lea     rcx, [rbp+530h+hstringHeader]; hstringHeader
0x1400123e4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1400123e9  nop
0x1400123ea  lea     r8, [rsp+630h+var_5F8]
0x1400123ef  mov     rdx, [rbp+530h+var_488]
0x1400123f6  mov     rcx, rdi
0x1400123f9  mov     rax, rbx
0x1400123fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012401  mov     edi, eax
0x140012403  test    eax, eax
0x140012405  jns     short loc_140012427
0x140012407  mov     edx, 32h ; '2'; void *
0x14001240c  mov     rcx, [rbp+538h]; this
0x140012413  mov     r9d, eax; char *
0x140012416  lea     r8, aOnecoreWindows_4; "onecore\\windows\\directx\\database\\up"...
0x14001241d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012422  jmp     loc_1400124BD
0x140012427  mov     rdi, [rsp+630h+var_5F8]
0x14001242c  mov     rax, [rdi]
0x14001242f  mov     rbx, [rax+60h]
0x140012433  mov     rcx, [rsp+630h+var_600]
0x140012438  mov     [rsp+630h+var_600], r12
0x14001243d  test    rcx, rcx
0x140012440  jz      short loc_14001244F
0x140012442  mov     rdx, [rcx]
0x140012445  mov     rax, [rdx+10h]
0x140012449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001244e  nop
0x14001244f  lea     rdx, [rsp+630h+var_600]
0x140012454  mov     rcx, rdi
0x140012457  mov     rax, rbx
0x14001245a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001245f  mov     edi, eax
0x140012461  test    eax, eax
0x140012463  jns     short loc_14001246C
0x140012465  mov     edx, 3Ah ; ':'
0x14001246a  jmp     short loc_14001240C
0x14001246c  mov     [rsp+630h+var_5E0], r12d
0x140012471  lea     rdx, [rsp+630h+var_5E0]
0x140012476  lea     rcx, [rsp+630h+var_600]
0x14001247b  call    ?GetJsonObjSize@@YAJAEBV?$com_ptr_t@UIJsonObject@Json@Data@Windows@@Uerr_exception_policy@wil@@@wil@@PEAI@Z; GetJsonObjSize(wil::com_ptr_t<Windows::Data::Json::IJsonObject,wil::err_exception_policy> const &,uint *)
0x140012480  mov     edi, eax
0x140012482  test    eax, eax
0x140012484  jns     short loc_140012490
0x140012486  mov     edx, 3Dh ; '='
0x14001248b  jmp     loc_14001240C
0x140012490  cmp     [rsp+630h+var_5E0], r12d
0x140012495  jnz     short loc_1400124CC
0x140012497  mov     rcx, [rsp+630h+var_5F8]
0x14001249c  mov     rax, [rcx]
0x14001249f  mov     rax, [rax+70h]
0x1400124a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400124a8  mov     edi, eax
0x1400124aa  test    eax, eax
0x1400124ac  jns     short loc_1400124B8
0x1400124ae  mov     edx, 41h ; 'A'
0x1400124b3  jmp     loc_14001240C
0x1400124b8  mov     edi, 1
0x1400124bd  lea     rcx, [rsp+630h+var_5D8]
0x1400124c2  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x1400124c7  jmp     loc_140012A01
0x1400124cc  lea     rcx, [rsp+630h+var_5D8]
0x1400124d1  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x1400124d6  jmp     loc_140012877
0x1400124db  xor     edx, edx; Val
0x1400124dd  mov     r8d, 208h; Size
0x1400124e3  lea     rcx, [rbp+530h+var_460]; void *
0x1400124ea  call    memset_0
0x1400124ef  mov     ebx, 104h
0x1400124f4  mov     r9d, ebx
0x1400124f7  lea     r8, [rbp+530h+var_460]
0x1400124fe  xor     edx, edx
0x140012500  lea     ecx, [rdx+4]
0x140012503  call    cs:__imp_GetBasicProfileFolderPath
0x140012509  mov     edi, eax
0x14001250b  test    eax, eax
0x14001250d  jns     short loc_140012519
0x14001250f  mov     edx, 53h ; 'S'
0x140012514  jmp     loc_1400129EA
0x140012519  lea     rax, aDirectxdbversi; "DirectXDbVersion.json"
0x140012520  mov     [rsp+630h+var_608], rax
0x140012525  lea     rax, aMicrosoftWindo; "Microsoft\\Windows\\OneSettings"
0x14001252c  mov     qword ptr [rsp+630h+var_610], rax; int
0x140012531  lea     r9, [rbp+530h+var_460]
0x140012538  lea     r8, aWsWsWs_0; "%ws\\%ws\\%ws"
0x14001253f  mov     rdx, rbx; unsigned __int64
0x140012542  lea     rcx, [rbp+530h+var_250]; unsigned __int16 *
0x140012549  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001254e  mov     edi, eax
0x140012550  test    eax, eax
0x140012552  jns     short loc_14001255E
0x140012554  mov     edx, 56h ; 'V'
0x140012559  jmp     loc_1400129EA
0x14001255e  lea     rdx, [rbp+530h+var_250]
0x140012565  lea     rcx, [rbp+530h+var_5B0]
0x140012569  call    ??0?$basic_ifstream@GU?$char_traits@G@std@@@std@@QEAA@PEBGHH@Z; std::basic_ifstream<ushort>::basic_ifstream<ushort>(ushort const *,int,int)
0x14001256e  nop
0x14001256f  cmp     [rbp+530h+var_520], r12
0x140012573  jnz     short loc_14001259D
0x140012575  mov     rcx, [rbp+538h]; this
0x14001257c  lea     r8, aOnecoreWindows_4; "onecore\\windows\\directx\\database\\up"...
0x140012583  mov     edx, 59h ; 'Y'; void *
0x140012588  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001258d  mov     edi, eax
0x14001258f  lea     rcx, [rbp+530h+var_5B0]
0x140012593  call    ??_D?$basic_ifstream@GU?$char_traits@G@std@@@std@@QEAAXXZ; std::basic_ifstream<ushort>::`vbase destructor'(void)
0x140012598  jmp     loc_140012A01
0x14001259d  lea     rcx, [rbp+530h+hstringHeader]
0x1400125a4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400125a9  nop
0x1400125aa  mov     ebx, 2
0x1400125af  mov     r8d, ebx
0x1400125b2  xor     edx, edx
0x1400125b4  lea     rcx, [rbp+530h+var_5B0]
0x1400125b8  call    cs:__imp_?seekg@?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@_JH@Z; std::basic_istream<ushort>::seekg(__int64,int)
0x1400125be  lea     rdx, [rbp+530h+var_480]
0x1400125c5  lea     rcx, [rbp+530h+var_5B0]
0x1400125c9  call    cs:__imp_?tellg@?$basic_istream@GU?$char_traits@G@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ; std::basic_istream<ushort>::tellg(void)
0x1400125cf  mov     r9, [rax+8]
0x1400125d3  add     r9, [rax]
0x1400125d6  mov     rdx, qword ptr [rbp+530h+hstringHeader.Reserved+10h]
0x1400125dd  lea     rcx, [rbp+530h+hstringHeader]
0x1400125e4  cmp     r9, rdx
0x1400125e7  ja      short loc_1400125FC
0x1400125e9  mov     qword ptr [rbp+530h+hstringHeader.Reserved+10h], r9
0x1400125f0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEAAPEAGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400125f5  mov     [rax+r9*2], r12w
0x1400125fa  jmp     short loc_140012645
0x1400125fc  mov     r8, r9
0x1400125ff  sub     r8, rdx
0x140012602  mov     rax, [rbp+530h+var_488]
0x140012609  sub     rax, rdx
0x14001260c  cmp     r8, rax
0x14001260f  ja      short loc_14001263A
0x140012611  mov     qword ptr [rbp+530h+hstringHeader.Reserved+10h], r9
0x140012618  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEAAPEAGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14001261d  mov     r10, rax
0x140012620  lea     rdi, [rax+rdx*2]
0x140012624  test    r8, r8
0x140012627  jz      short loc_140012633
0x140012629  movzx   eax, r12w
0x14001262d  mov     rcx, r8
0x140012630  rep stosw
0x140012633  mov     [r10+r9*2], r12w
0x140012638  jmp     short loc_140012645
0x14001263a  mov     r9, r8
0x14001263d  mov     rdx, r8
0x140012640  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x140012645  xor     r8d, r8d
0x140012648  xor     edx, edx
0x14001264a  lea     rcx, [rbp+530h+var_5B0]
0x14001264e  call    cs:__imp_?seekg@?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@_JH@Z; std::basic_istream<ushort>::seekg(__int64,int)
0x140012654  mov     r8, qword ptr [rbp+530h+hstringHeader.Reserved+10h]
0x14001265b  test    r8, r8
0x14001265e  jz      short loc_140012679
0x140012660  lea     rcx, [rbp+530h+hstringHeader]
0x140012667  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEAAPEAGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14001266c  mov     rdx, rax
0x14001266f  lea     rcx, [rbp+530h+var_5B0]
0x140012673  call    cs:__imp_?read@?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@PEAG_J@Z; std::basic_istream<ushort>::read(ushort *,__int64)
0x140012679  lea     rcx, [rbp+530h+var_5A0]
0x14001267d  call    ?close@?$basic_filebuf@GU?$char_traits@G@std@@@std@@QEAAPEAV12@XZ; std::basic_filebuf<ushort>::close(void)
0x140012682  test    rax, rax
0x140012685  jnz     short loc_1400126A2
0x140012687  mov     rax, [rbp+530h+var_5B0]
0x14001268b  movsxd  rcx, dword ptr [rax+4]
0x14001268f  lea     rax, [rbp+530h+var_5B0]
0x140012693  add     rcx, rax
0x140012696  xor     r8d, r8d
0x140012699  mov     edx, ebx
0x14001269b  call    cs:__imp_?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::setstate(int,bool)
0x1400126a1  nop
0x1400126a2  mov     [rsp+630h+var_5E8], r12
0x1400126a7  mov     [rbp+530h+var_468], r12
0x1400126ae  mov     r9d, 1Ch; unsigned int
0x1400126b4  lea     r8d, [r9+1]; unsigned int
0x1400126b8  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1400126bf  lea     rcx, [rbp+530h+var_480]; hstringHeader
0x1400126c6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1400126cb  lea     r8, [rsp+630h+var_5E8]
0x1400126d0  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x1400126d7  mov     rcx, [rbp+530h+var_468]
0x1400126de  call    cs:__imp_RoGetActivationFactory
0x1400126e4  mov     edi, eax
0x1400126e6  test    eax, eax
0x1400126e8  jns     short loc_140012722
0x1400126ea  mov     rcx, [rbp+538h]; this
0x1400126f1  mov     r9d, eax; char *
0x1400126f4  lea     r8, aOnecoreWindows_4; "onecore\\windows\\directx\\database\\up"...
0x1400126fb  mov     edx, 67h ; 'g'; void *
0x140012700  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012705  nop
0x140012706  lea     rcx, [rsp+630h+var_5E8]
0x14001270b  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x140012710  nop
0x140012711  lea     rcx, [rbp+530h+hstringHeader]
0x140012718  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001271d  jmp     loc_14001258F
0x140012722  mov     [rsp+630h+var_5F0], r12
0x140012727  mov     rdi, [rsp+630h+var_5E8]
0x14001272c  mov     rbx, [rdi]
0x14001272f  mov     [rsp+630h+var_5F0], r12
0x140012734  lea     rcx, [rbp+530h+hstringHeader]
0x14001273b  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<ushort>>::_Large_mode_engaged(void)
0x140012740  lea     rdx, [rbp+530h+hstringHeader]
0x140012747  test    al, al
0x140012749  cmovnz  rdx, qword ptr [rbp+530h+hstringHeader.Reserved]; sourceString
0x140012751  mov     [rbp+530h+var_468], r12
0x140012758  or      r9, 0FFFFFFFFFFFFFFFFh
0x14001275c  inc     r9; unsigned int
0x14001275f  cmp     [rdx+r9*2], r12w
0x140012764  jnz     short loc_14001275C
0x140012766  mov     eax, 0FFFFFFFFh
0x14001276b  cmp     r9, rax
0x14001276e  ja      loc_140012A76
0x140012774  lea     r8d, [r9+1]; unsigned int
0x140012778  cmp     r8d, r9d
0x14001277b  jb      loc_140012A76
0x140012781  lea     rcx, [rbp+530h+var_480]; hstringHeader
0x140012788  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14001278d  nop
0x14001278e  lea     r8, [rsp+630h+var_5F0]
0x140012793  mov     rdx, [rbp+530h+var_468]
0x14001279a  mov     rcx, rdi
0x14001279d  mov     rax, [rbx+30h]
0x1400127a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400127a6  mov     edi, eax
0x1400127a8  test    eax, eax
0x1400127aa  jns     short loc_1400127D7
0x1400127ac  mov     edx, 6Ah ; 'j'; void *
0x1400127b1  lea     r8, aOnecoreWindows_4; "onecore\\windows\\directx\\database\\up"...
0x1400127b8  mov     r9d, eax; char *
0x1400127bb  mov     rcx, [rbp+538h]; this
0x1400127c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400127c7  nop
0x1400127c8  lea     rcx, [rsp+630h+var_5F0]
0x1400127cd  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x1400127d2  jmp     loc_140012706
0x1400127d7  mov     rdi, [rsp+630h+var_5F0]
0x1400127dc  mov     rax, [rdi]
0x1400127df  mov     rbx, [rax+40h]
0x1400127e3  mov     rcx, [rsp+630h+var_600]
0x1400127e8  mov     [rsp+630h+var_600], r12
0x1400127ed  test    rcx, rcx
0x1400127f0  jz      short loc_1400127FF
0x1400127f2  mov     rax, [rcx]
0x1400127f5  mov     rax, [rax+10h]
  ... truncated ...
```
