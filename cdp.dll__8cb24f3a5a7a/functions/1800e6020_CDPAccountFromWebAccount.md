# CDPAccountFromWebAccount

- ea: `0x1800e6020`
- end: `0x1800e6785`
- name: `CDPAccountFromWebAccount`
- size: `1893`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x18000aec4`
- `0x18000b724`
- `0x18000d02c`
- `0x18000d098`
- `0x18001ce80`
- `0x180030190`
- `0x18003dd60`
- `0x1800aeb14`
- `0x1800e6020`
- `0x180158c08`
- `0x1801f6fb0`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e64d2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e6505`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e64d2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e6505`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e618f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e61db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e62f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e63a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e63df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e642f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6463`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e65bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6621`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6677`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e66fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e672f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e618f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e61db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e62f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e63a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e63df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e642f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6463`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6588`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e65bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6621`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e6677`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e66fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e672f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e622e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e6493`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e622e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e6493`

## pseudocode

```c
// Hidden C++ exception states: #wind=16 #try_helpers=1
__int64 __fastcall CDPAccountFromWebAccount(__int64 (__fastcall ***a1)(_QWORD, GUID *, cdp **), _QWORD *a2)
{
  __int64 (__fastcall *v5)(_QWORD, GUID *, cdp **); // rbx
  int v6; // eax
  int v7; // edx
  int v8; // ecx
  cdp *v9; // rbx
  __int64 (__fastcall *v10)(cdp *, GUID *, __int64 *); // rdi
  int v11; // eax
  int v12; // edx
  int v13; // ecx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rbx
  int v16; // eax
  int v17; // edx
  int v18; // ecx
  __int64 v19; // rcx
  cdp *v20; // rcx
  PCWSTR StringRawBuffer; // rdx
  cdp *v22; // rdi
  __int64 (__fastcall *v23)(cdp *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v24; // eax
  int v25; // edx
  int v26; // ecx
  __int64 (__fastcall ***v27)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v28)(_QWORD, GUID *, __int64 *); // rdi
  int v29; // eax
  int v30; // edx
  int v31; // ecx
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, HSTRING *); // rbx
  int v34; // eax
  int v35; // edx
  int v36; // ecx
  PCWSTR v37; // rdx
  const WCHAR *v38; // rcx
  unsigned __int16 v39; // bx
  struct Windows::Security::Credentials::IWebAccount *v40; // rdx
  const WCHAR *v41; // rcx
  int v42; // ecx
  unsigned __int64 UserContextTokenFromWebAccount; // rax
  _QWORD *v44; // rcx
  int v45; // eax
  int v46; // edx
  int v47; // ecx
  __int64 v48; // rcx
  __int64 (__fastcall ***v49)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v50; // rcx
  cdp *v51; // rcx
  unsigned int v52; // [rsp+30h] [rbp-C8h] BYREF
  int v53; // [rsp+34h] [rbp-C4h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C0h] BYREF
  cdp *v55; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v56; // [rsp+48h] [rbp-B0h] BYREF
  HSTRING v57; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v58; // [rsp+58h] [rbp-A0h] BYREF
  __int64 (__fastcall ***v59)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-98h] BYREF
  int v60; // [rsp+68h] [rbp-90h] BYREF
  LPCWCH lpString1[2]; // [rsp+70h] [rbp-88h] BYREF
  __m128i si128; // [rsp+80h] [rbp-78h]
  _QWORD v63[4]; // [rsp+90h] [rbp-68h] BYREF
  _QWORD v64[3]; // [rsp+B0h] [rbp-48h] BYREF
  unsigned __int64 v65; // [rsp+C8h] [rbp-30h]

  if ( !a1 )
  {
    v52 = -2147024809;
    v60 = 17;
    Log<long &,char const (&)[15],int>(
      0,
      (_DWORD)a2,
      (unsigned int)&v52,
      (unsigned int)".\\accountlet.cpp",
      (__int64)&v60);
    return v52;
  }
  *a2 = 0;
  v60 = 0;
  v55 = 0;
  v5 = **a1;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
  v6 = v5(a1, &GUID_69473eb2_8031_49be_80bb_96cb46d99aba, &v55);
  if ( v6 < 0 )
  {
    v52 = v6;
    v53 = 25;
    Log<long &,char const (&)[15],int>(v8, v7, (unsigned int)&v52, (unsigned int)".\\accountlet.cpp", (__int64)&v53);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
    return v52;
  }
  v56 = 0;
  v9 = v55;
  v10 = **(__int64 (__fastcall ***)(cdp *, GUID *, __int64 *))v55;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
  v11 = v10(v9, &GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824, &v56);
  if ( v11 < 0 )
  {
    v52 = v11;
    v53 = 28;
    Log<long &,char const (&)[15],int>(v13, v12, (unsigned int)&v52, (unsigned int)".\\accountlet.cpp", (__int64)&v53);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
    return v52;
  }
  string = 0;
  v14 = v56;
  v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v56 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v16 = v15(v14, &string);
  if ( v16 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    std::wstring::wstring(v64, StringRawBuffer);
    cdp::ToUtf8(v63, v64);
    if ( v65 > 7 )
      std::_Deallocate<16>(v64[0], 2 * v65 + 2);
    v59 = 0;
    v22 = v55;
    v23 = *(__int64 (__fastcall **)(cdp *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v55 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
    v24 = v23(v22, &v59);
    if ( v24 < 0 )
    {
      v52 = v24;
      v53 = 35;
      Log<long &,char const (&)[15],int>(v26, v25, (unsigned int)&v52, (unsigned int)".\\accountlet.cpp", (__int64)&v53);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v63);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
      return v52;
    }
    v58 = 0;
    v27 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
    v28 = **v59;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
    v29 = v28(v27, &GUID_4a01eb05_4e42_41d4_b518_e008a5163614, &v58);
    if ( v29 < 0 )
    {
      v52 = v29;
      v53 = 38;
      Log<long &,char const (&)[15],int>(v31, v30, (unsigned int)&v52, (unsigned int)".\\accountlet.cpp", (__int64)&v53);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v63);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
      return v52;
    }
    v57 = 0;
    v32 = v58;
    v33 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v58 + 56LL);
    WindowsDeleteString(0);
    v57 = 0;
    v34 = v33(v32, &v57);
    if ( v34 < 0 )
    {
      v52 = v34;
      v53 = 41;
      Log<long &,char const (&)[15],int>(v36, v35, (unsigned int)&v52, (unsigned int)".\\accountlet.cpp", (__int64)&v53);
      WindowsDeleteString(v57);
      v57 = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v63);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
      return v52;
    }
    v37 = WindowsGetStringRawBuffer(v57, 0);
    std::wstring::wstring(lpString1, v37);
    v38 = (const WCHAR *)lpString1;
    if ( si128.m128i_i64[1] > 7uLL )
      v38 = lpString1[0];
    v39 = 1;
    if ( CompareStringOrdinal(v38, -1, L"consumers", -1, 1) != 2 )
    {
      v41 = (const WCHAR *)lpString1;
      if ( si128.m128i_i64[1] > 7uLL )
        v41 = lpString1[0];
      if ( CompareStringOrdinal(v41, -1, L"organizations", -1, 1) != 2 )
      {
        v52 = -2147221246;
        v53 = 55;
        Log<long &,char const (&)[15],int>(
          v42,
          (_DWORD)v40,
          (unsigned int)&v52,
          (unsigned int)".\\accountlet.cpp",
          (__int64)&v53);
        std::wstring::_Tidy_deallocate(lpString1);
        WindowsDeleteString(v57);
        v57 = 0;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
        std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v63);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
        return v52;
      }
      v39 = 2;
    }
    UserContextTokenFromWebAccount = cdp::GetUserContextTokenFromWebAccount(v55, v40);
    v44 = v63;
    if ( v63[3] > 0xFu )
      v44 = (_QWORD *)v63[0];
    v45 = CDPCreateAccountInternalForUser(v44, v39, UserContextTokenFromWebAccount, a2);
    if ( v45 >= 0 )
    {
      if ( si128.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(lpString1[0], 2 * si128.m128i_i64[1] + 2);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(lpString1[0]) = 0;
      WindowsDeleteString(v57);
      v57 = 0;
      v48 = v58;
      if ( v58 )
      {
        v58 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      }
      v49 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
      if ( v59 )
      {
        v59 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v49)[2])(v49);
      }
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v63);
      WindowsDeleteString(string);
      string = 0;
      v50 = v56;
      if ( v56 )
      {
        v56 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
      }
      v51 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(cdp *))(*(_QWORD *)v51 + 16LL))(v51);
      }
      return 0;
    }
    else
    {
      v52 = v45;
      v53 = 59;
      Log<long &,char const (&)[15],int>(v47, v46, (unsigned int)&v52, (unsigned int)".\\accountlet.cpp", (__int64)&v53);
      std::wstring::_Tidy_deallocate(lpString1);
      WindowsDeleteString(v57);
      v57 = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v59);
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v63);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
      return v52;
    }
  }
  else
  {
    v52 = v16;
    v53 = 31;
    Log<long &,char const (&)[15],int>(v18, v17, (unsigned int)&v52, (unsigned int)".\\accountlet.cpp", (__int64)&v53);
    WindowsDeleteString(string);
    string = 0;
    v19 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(cdp *))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return v52;
  }
}

```

## disassembly

```asm
0x1800e6020  mov     [rsp+arg_10], rbx
0x1800e6025  mov     [rsp+arg_18], rsi
0x1800e602a  push    rdi
0x1800e602b  push    r14
0x1800e602d  push    r15
0x1800e602f  sub     rsp, 0E0h
0x1800e6036  mov     rax, cs:__security_cookie
0x1800e603d  xor     rax, rsp
0x1800e6040  mov     [rsp+0F8h+var_28], rax
0x1800e6048  mov     r14, rdx
0x1800e604b  mov     rdi, rcx
0x1800e604e  xor     r15d, r15d
0x1800e6051  test    rcx, rcx
0x1800e6054  jnz     short loc_1800E608A
0x1800e6056  mov     [rsp+0F8h+var_C8], 80070057h
0x1800e605e  mov     [rsp+0F8h+var_90], 11h
0x1800e6066  lea     rax, [rsp+0F8h+var_90]
0x1800e606b  mov     qword ptr [rsp+0F8h+bIgnoreCase], rax
0x1800e6070  lea     r9, aAccountletCpp; ".\\accountlet.cpp"
0x1800e6077  lea     r8, [rsp+0F8h+var_C8]
0x1800e607c  call    ??$Log@AEAJAEAY0P@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0P@$$CBD$$QEAH@Z; Log<long &,char const (&)[15],int>(CDPLogLevel,char const *,long &,char const (&)[15],int &&)
0x1800e6081  mov     eax, [rsp+0F8h+var_C8]
0x1800e6085  jmp     loc_1800E675B
0x1800e608a  mov     [rdx], r15
0x1800e608d  mov     esi, r15d
0x1800e6090  mov     [rsp+0F8h+var_90], r15d
0x1800e6095  mov     [rsp+0F8h+var_B8], r15
0x1800e609a  mov     rax, [rcx]
0x1800e609d  mov     rbx, [rax]
0x1800e60a0  lea     rcx, [rsp+0F8h+var_B8]
0x1800e60a5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800e60aa  lea     r8, [rsp+0F8h+var_B8]
0x1800e60af  lea     rdx, _GUID_69473eb2_8031_49be_80bb_96cb46d99aba
0x1800e60b6  mov     rcx, rdi
0x1800e60b9  mov     rax, rbx
0x1800e60bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e60c1  test    eax, eax
0x1800e60c3  jns     short loc_1800E6100
0x1800e60c5  mov     [rsp+0F8h+var_C8], eax
0x1800e60c9  mov     [rsp+0F8h+var_C4], 19h
0x1800e60d1  lea     rax, [rsp+0F8h+var_C4]
0x1800e60d6  mov     qword ptr [rsp+0F8h+bIgnoreCase], rax
0x1800e60db  lea     r9, aAccountletCpp; ".\\accountlet.cpp"
0x1800e60e2  lea     r8, [rsp+0F8h+var_C8]
0x1800e60e7  call    ??$Log@AEAJAEAY0P@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0P@$$CBD$$QEAH@Z; Log<long &,char const (&)[15],int>(CDPLogLevel,char const *,long &,char const (&)[15],int &&)
0x1800e60ec  nop
0x1800e60ed  lea     rcx, [rsp+0F8h+var_B8]
0x1800e60f2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800e60f7  mov     eax, [rsp+0F8h+var_C8]
0x1800e60fb  jmp     loc_1800E675B
0x1800e6100  mov     [rsp+0F8h+var_B0], r15
0x1800e6105  mov     rbx, [rsp+0F8h+var_B8]
0x1800e610a  mov     rax, [rbx]
0x1800e610d  mov     rdi, [rax]
0x1800e6110  lea     rcx, [rsp+0F8h+var_B0]
0x1800e6115  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800e611a  lea     r8, [rsp+0F8h+var_B0]
0x1800e611f  lea     rdx, _GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824
0x1800e6126  mov     rcx, rbx
0x1800e6129  mov     rax, rdi
0x1800e612c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6131  nop
0x1800e6132  test    eax, eax
0x1800e6134  jns     short loc_1800E617C
0x1800e6136  mov     [rsp+0F8h+var_C8], eax
0x1800e613a  mov     [rsp+0F8h+var_C4], 1Ch
0x1800e6142  lea     rax, [rsp+0F8h+var_C4]
0x1800e6147  mov     qword ptr [rsp+0F8h+bIgnoreCase], rax
0x1800e614c  lea     r9, aAccountletCpp; ".\\accountlet.cpp"
0x1800e6153  lea     r8, [rsp+0F8h+var_C8]
0x1800e6158  call    ??$Log@AEAJAEAY0P@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0P@$$CBD$$QEAH@Z; Log<long &,char const (&)[15],int>(CDPLogLevel,char const *,long &,char const (&)[15],int &&)
0x1800e615d  nop
0x1800e615e  lea     rcx, [rsp+0F8h+var_B0]
0x1800e6163  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800e6168  nop
0x1800e6169  lea     rcx, [rsp+0F8h+var_B8]
0x1800e616e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800e6173  mov     eax, [rsp+0F8h+var_C8]
0x1800e6177  jmp     loc_1800E675B
0x1800e617c  mov     [rsp+0F8h+string], r15
0x1800e6181  mov     rdi, [rsp+0F8h+var_B0]
0x1800e6186  mov     rax, [rdi]
0x1800e6189  mov     rbx, [rax+30h]
0x1800e618d  xor     ecx, ecx; string
0x1800e618f  call    cs:__imp_WindowsDeleteString
0x1800e6195  mov     [rsp+0F8h+string], r15
0x1800e619a  lea     rdx, [rsp+0F8h+string]
0x1800e619f  mov     rcx, rdi
0x1800e61a2  mov     rax, rbx
0x1800e61a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e61aa  test    eax, eax
0x1800e61ac  jns     short loc_1800E6227
0x1800e61ae  mov     [rsp+0F8h+var_C8], eax
0x1800e61b2  mov     [rsp+0F8h+var_C4], 1Fh
0x1800e61ba  lea     rax, [rsp+0F8h+var_C4]
0x1800e61bf  mov     qword ptr [rsp+0F8h+bIgnoreCase], rax
0x1800e61c4  lea     r9, aAccountletCpp; ".\\accountlet.cpp"
0x1800e61cb  lea     r8, [rsp+0F8h+var_C8]
0x1800e61d0  call    ??$Log@AEAJAEAY0P@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0P@$$CBD$$QEAH@Z; Log<long &,char const (&)[15],int>(CDPLogLevel,char const *,long &,char const (&)[15],int &&)
0x1800e61d5  nop
0x1800e61d6  mov     rcx, [rsp+0F8h+string]; string
0x1800e61db  call    cs:__imp_WindowsDeleteString
0x1800e61e1  mov     [rsp+0F8h+string], r15
0x1800e61e6  mov     rcx, [rsp+0F8h+var_B0]
0x1800e61eb  test    rcx, rcx
0x1800e61ee  jz      short loc_1800E6202
0x1800e61f0  mov     [rsp+0F8h+var_B0], r15
0x1800e61f5  mov     rax, [rcx]
0x1800e61f8  mov     rax, [rax+10h]
0x1800e61fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6201  nop
0x1800e6202  mov     rcx, [rsp+0F8h+var_B8]
0x1800e6207  test    rcx, rcx
0x1800e620a  jz      short loc_1800E621E
0x1800e620c  mov     [rsp+0F8h+var_B8], r15
0x1800e6211  mov     rax, [rcx]
0x1800e6214  mov     rax, [rax+10h]
0x1800e6218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e621d  nop
0x1800e621e  mov     eax, [rsp+0F8h+var_C8]
0x1800e6222  jmp     loc_1800E675B
0x1800e6227  xor     edx, edx; length
0x1800e6229  mov     rcx, [rsp+0F8h+string]; string
0x1800e622e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e6234  mov     rdx, rax
0x1800e6237  lea     rcx, [rsp+0F8h+var_48]
0x1800e623f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800e6244  nop
0x1800e6245  lea     rdx, [rsp+0F8h+var_48]
0x1800e624d  lea     rcx, [rsp+0F8h+var_68]
0x1800e6255  call    ?ToUtf8@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; cdp::ToUtf8(std::wstring const &)
0x1800e625a  nop
0x1800e625b  mov     rdx, [rsp+0F8h+var_30]
0x1800e6263  cmp     rdx, 7
0x1800e6267  jbe     short loc_1800E627E
0x1800e6269  lea     rdx, ds:2[rdx*2]
0x1800e6271  mov     rcx, [rsp+0F8h+var_48]
0x1800e6279  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800e627e  mov     [rsp+0F8h+var_98], r15
0x1800e6283  mov     rdi, [rsp+0F8h+var_B8]
0x1800e6288  mov     rax, [rdi]
0x1800e628b  mov     rbx, [rax+30h]
0x1800e628f  lea     rcx, [rsp+0F8h+var_98]
0x1800e6294  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800e6299  lea     rdx, [rsp+0F8h+var_98]
0x1800e629e  mov     rcx, rdi
0x1800e62a1  mov     rax, rbx
0x1800e62a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e62a9  test    eax, eax
0x1800e62ab  jns     short loc_1800E631C
0x1800e62ad  mov     [rsp+0F8h+var_C8], eax
0x1800e62b1  mov     [rsp+0F8h+var_C4], 23h ; '#'
0x1800e62b9  lea     rax, [rsp+0F8h+var_C4]
0x1800e62be  mov     qword ptr [rsp+0F8h+bIgnoreCase], rax
0x1800e62c3  lea     r9, aAccountletCpp; ".\\accountlet.cpp"
0x1800e62ca  lea     r8, [rsp+0F8h+var_C8]
0x1800e62cf  call    ??$Log@AEAJAEAY0P@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0P@$$CBD$$QEAH@Z; Log<long &,char const (&)[15],int>(CDPLogLevel,char const *,long &,char const (&)[15],int &&)
0x1800e62d4  nop
0x1800e62d5  lea     rcx, [rsp+0F8h+var_98]
0x1800e62da  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800e62df  nop
0x1800e62e0  lea     rcx, [rsp+0F8h+var_68]; void *
0x1800e62e8  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800e62ed  nop
0x1800e62ee  mov     rcx, [rsp+0F8h+string]; string
0x1800e62f3  call    cs:__imp_WindowsDeleteString
0x1800e62f9  mov     [rsp+0F8h+string], r15
0x1800e62fe  lea     rcx, [rsp+0F8h+var_B0]
0x1800e6303  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800e6308  nop
0x1800e6309  lea     rcx, [rsp+0F8h+var_B8]
0x1800e630e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800e6313  mov     eax, [rsp+0F8h+var_C8]
0x1800e6317  jmp     loc_1800E675B
0x1800e631c  mov     [rsp+0F8h+var_A0], r15
0x1800e6321  mov     rbx, [rsp+0F8h+var_98]
0x1800e6326  mov     rax, [rbx]
0x1800e6329  mov     rdi, [rax]
0x1800e632c  lea     rcx, [rsp+0F8h+var_A0]
0x1800e6331  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800e6336  lea     r8, [rsp+0F8h+var_A0]
0x1800e633b  lea     rdx, _GUID_4a01eb05_4e42_41d4_b518_e008a5163614
0x1800e6342  mov     rcx, rbx
0x1800e6345  mov     rax, rdi
0x1800e6348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e634d  nop
0x1800e634e  test    eax, eax
0x1800e6350  jns     short loc_1800E63CC
0x1800e6352  mov     [rsp+0F8h+var_C8], eax
0x1800e6356  mov     [rsp+0F8h+var_C4], 26h ; '&'
0x1800e635e  lea     rax, [rsp+0F8h+var_C4]
0x1800e6363  mov     qword ptr [rsp+0F8h+bIgnoreCase], rax
0x1800e6368  lea     r9, aAccountletCpp; ".\\accountlet.cpp"
0x1800e636f  lea     r8, [rsp+0F8h+var_C8]
0x1800e6374  call    ??$Log@AEAJAEAY0P@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0P@$$CBD$$QEAH@Z; Log<long &,char const (&)[15],int>(CDPLogLevel,char const *,long &,char const (&)[15],int &&)
0x1800e6379  nop
0x1800e637a  lea     rcx, [rsp+0F8h+var_A0]
0x1800e637f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800e6384  nop
0x1800e6385  lea     rcx, [rsp+0F8h+var_98]
0x1800e638a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800e638f  nop
0x1800e6390  lea     rcx, [rsp+0F8h+var_68]; void *
0x1800e6398  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800e639d  nop
0x1800e639e  mov     rcx, [rsp+0F8h+string]; string
0x1800e63a3  call    cs:__imp_WindowsDeleteString
0x1800e63a9  mov     [rsp+0F8h+string], r15
0x1800e63ae  lea     rcx, [rsp+0F8h+var_B0]
0x1800e63b3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800e63b8  nop
0x1800e63b9  lea     rcx, [rsp+0F8h+var_B8]
0x1800e63be  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800e63c3  mov     eax, [rsp+0F8h+var_C8]
0x1800e63c7  jmp     loc_1800E675B
0x1800e63cc  mov     [rsp+0F8h+var_A8], r15
0x1800e63d1  mov     rdi, [rsp+0F8h+var_A0]
0x1800e63d6  mov     rax, [rdi]
0x1800e63d9  mov     rbx, [rax+38h]
0x1800e63dd  xor     ecx, ecx; string
0x1800e63df  call    cs:__imp_WindowsDeleteString
0x1800e63e5  mov     [rsp+0F8h+var_A8], r15
0x1800e63ea  lea     rdx, [rsp+0F8h+var_A8]
0x1800e63ef  mov     rcx, rdi
0x1800e63f2  mov     rax, rbx
0x1800e63f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e63fa  test    eax, eax
0x1800e63fc  jns     loc_1800E648C
0x1800e6402  mov     [rsp+0F8h+var_C8], eax
0x1800e6406  mov     [rsp+0F8h+var_C4], 29h ; ')'
0x1800e640e  lea     rax, [rsp+0F8h+var_C4]
0x1800e6413  mov     qword ptr [rsp+0F8h+bIgnoreCase], rax
0x1800e6418  lea     r9, aAccountletCpp; ".\\accountlet.cpp"
0x1800e641f  lea     r8, [rsp+0F8h+var_C8]
0x1800e6424  call    ??$Log@AEAJAEAY0P@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0P@$$CBD$$QEAH@Z; Log<long &,char const (&)[15],int>(CDPLogLevel,char const *,long &,char const (&)[15],int &&)
0x1800e6429  nop
0x1800e642a  mov     rcx, [rsp+0F8h+var_A8]; string
0x1800e642f  call    cs:__imp_WindowsDeleteString
0x1800e6435  mov     [rsp+0F8h+var_A8], r15
0x1800e643a  lea     rcx, [rsp+0F8h+var_A0]
0x1800e643f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800e6444  nop
0x1800e6445  lea     rcx, [rsp+0F8h+var_98]
0x1800e644a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800e644f  nop
0x1800e6450  lea     rcx, [rsp+0F8h+var_68]; void *
0x1800e6458  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800e645d  nop
0x1800e645e  mov     rcx, [rsp+0F8h+string]; string
0x1800e6463  call    cs:__imp_WindowsDeleteString
0x1800e6469  mov     [rsp+0F8h+string], r15
0x1800e646e  lea     rcx, [rsp+0F8h+var_B0]
0x1800e6473  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800e6478  nop
0x1800e6479  lea     rcx, [rsp+0F8h+var_B8]
0x1800e647e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800e6483  mov     eax, [rsp+0F8h+var_C8]
0x1800e6487  jmp     loc_1800E675B
0x1800e648c  xor     edx, edx; length
0x1800e648e  mov     rcx, [rsp+0F8h+var_A8]; string
0x1800e6493  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e6499  mov     rdx, rax
0x1800e649c  lea     rcx, [rsp+0F8h+lpString1]
0x1800e64a1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800e64a6  nop
0x1800e64a7  lea     rcx, [rsp+0F8h+lpString1]
0x1800e64ac  cmp     [rsp+0F8h+var_70], 7
0x1800e64b5  cmova   rcx, [rsp+0F8h+lpString1]; lpString1
0x1800e64bb  mov     ebx, 1
0x1800e64c0  mov     [rsp+0F8h+bIgnoreCase], ebx; bIgnoreCase
0x1800e64c4  or      r9d, 0FFFFFFFFh; cchCount2
0x1800e64c8  lea     r8, aConsumers; "consumers"
0x1800e64cf  or      edx, r9d; cchCount1
0x1800e64d2  call    cs:__imp_CompareStringOrdinal
0x1800e64d8  lea     edi, [rbx+1]
0x1800e64db  cmp     eax, edi
0x1800e64dd  jz      short loc_1800E6516
0x1800e64df  lea     rcx, [rsp+0F8h+lpString1]
0x1800e64e4  cmp     [rsp+0F8h+var_70], 7
0x1800e64ed  cmova   rcx, [rsp+0F8h+lpString1]; lpString1
0x1800e64f3  mov     [rsp+0F8h+bIgnoreCase], ebx; bIgnoreCase
0x1800e64f7  or      r9d, 0FFFFFFFFh; cchCount2
0x1800e64fb  lea     r8, aOrganizations; "organizations"
0x1800e6502  or      edx, r9d; cchCount1
0x1800e6505  call    cs:__imp_CompareStringOrdinal
0x1800e650b  cmp     eax, edi
0x1800e650d  jnz     loc_1800E66BF
0x1800e6513  movzx   ebx, di
0x1800e6516  mov     rcx, [rsp+0F8h+var_B8]; this
0x1800e651b  call    ?GetUserContextTokenFromWebAccount@cdp@@YA_KPEAUIWebAccount@Credentials@Security@Windows@@@Z; cdp::GetUserContextTokenFromWebAccount(Windows::Security::Credentials::IWebAccount *)
0x1800e6520  lea     rcx, [rsp+0F8h+var_68]
0x1800e6528  cmp     [rsp+0F8h+var_50], 0Fh
0x1800e6531  cmova   rcx, [rsp+0F8h+var_68]
0x1800e653a  mov     r9, r14
0x1800e653d  mov     r8, rax
0x1800e6540  movzx   edx, bx
0x1800e6543  call    CDPCreateAccountInternalForUser
0x1800e6548  test    eax, eax
0x1800e654a  jns     loc_1800E65E5
0x1800e6550  mov     [rsp+0F8h+var_C8], eax
  ... truncated ...
```
