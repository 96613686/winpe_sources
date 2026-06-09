# ArgumentsFromActivationArgs(ActivationProperties const &,Windows::ApplicationModel::Activation::IActivatedEventArgs *)

- ea: `0x1800b3a78`
- end: `0x1800b41f9`
- name: `?ArgumentsFromActivationArgs@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUActivationProperties@@PEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@@Z`
- size: `1921`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b5fb8`

## callees

- `0x180004f70`
- `0x1800125f4`
- `0x180012fb8`
- `0x180013510`
- `0x18001544c`
- `0x180016da0`
- `0x180022044`
- `0x180024778`
- `0x180024924`
- `0x1800b3a78`
- `0x1800b556c`
- `0x1800b9030`
- `0x1800ba878`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b3fe1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b3fe1`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800b410b`
- `msvcp_win!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800b410b`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800b411b`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x1800b411b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3bab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3c5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3d42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3e16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3ea2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3f76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4086`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b409c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3bab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3c5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3d42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3e16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3ea2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3f76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4086`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b409c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b3bea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b3d79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b3eea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b3fb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b4018`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b3bea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b3d79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b3eea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b3fb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b4018`

## string_xrefs

- `0x1800b4154`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b4169`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b417e`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b4193`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b41a8`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b41bd`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b41d2`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b41e7`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall ArgumentsFromActivationArgs(__int64 a1, _QWORD *a2, __int64 a3)
{
  int v6; // eax
  __int64 v7; // r8
  _QWORD *v8; // rdx
  _QWORD *v9; // rdx
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  PCWSTR v15; // rax
  __int128 *v16; // rdx
  _QWORD *v17; // rdx
  _QWORD *v18; // rax
  __int64 v19; // r8
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rbx
  int v23; // eax
  PCWSTR v24; // rax
  _QWORD *v25; // rdx
  _QWORD *v26; // rax
  __int64 v27; // r8
  __int64 v28; // r8
  _QWORD *v29; // rdx
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, HSTRING *); // rbx
  int v34; // eax
  PCWSTR StringRawBuffer; // rax
  __int128 *v36; // rdx
  __int64 v37; // rax
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, HSTRING *); // rbx
  int v40; // eax
  HSTRING v41; // rcx
  const WCHAR *v42; // rax
  const WCHAR *v43; // rcx
  __int64 v44; // rbx
  PCWSTR v45; // rax
  __int128 *v46; // rdx
  __int64 v47; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 length; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v52; // [rsp+40h] [rbp-C0h] BYREF
  int v53; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v54[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v55[32]; // [rsp+60h] [rbp-A0h] BYREF
  char v56; // [rsp+80h] [rbp-80h]
  int v57; // [rsp+8Ch] [rbp-74h]
  _QWORD v58[2]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v59[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v60[8]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v61[120]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v62[104]; // [rsp+128h] [rbp+28h] BYREF
  __int128 v63; // [rsp+190h] [rbp+90h] BYREF
  __int128 v64; // [rsp+1A0h] [rbp+A0h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v52 = a1;
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v58);
  v53 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a3 + 48LL))(a3, &v53);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
  if ( !v53 )
  {
    v28 = a2[26];
    if ( v28 )
    {
      v29 = a2 + 24;
      if ( a2[27] > 7u )
        v29 = (_QWORD *)*v29;
      v30 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v59, v29, v28);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v30, L" ");
    }
    v52 = 0;
    v31 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a3)(
            a3,
            &GUID_fbc93e26_a14a_4b4f_82b0_33bed920af52,
            &v52);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAA,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v31,
        bIgnoreCase);
    v54[0] = 0;
    v32 = v52;
    v33 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v52 + 48LL);
    WindowsDeleteString(0);
    v54[0] = 0;
    v34 = v33(v32, v54);
    if ( v34 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAD,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v34,
        bIgnoreCase);
    if ( v54[0] )
    {
      length = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(v54[0], &length);
      v63 = 0;
      v64 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v63, StringRawBuffer, length);
      v36 = &v63;
      if ( *((_QWORD *)&v64 + 1) > 7u )
        v36 = (__int128 *)v63;
      v37 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v59, v36, v64);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v37, L" ");
      std::wstring::~wstring(&v63);
    }
    string = 0;
    v38 = v52;
    v39 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v52 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v40 = v39(v38, &string);
    if ( v40 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB5,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v40,
        bIgnoreCase);
    v41 = string;
    if ( string )
    {
      v42 = WindowsGetStringRawBuffer(string, 0);
      v43 = (const WCHAR *)(a2 + 12);
      if ( a2[15] > 7u )
        v43 = *(const WCHAR **)v43;
      if ( CompareStringOrdinal(v43, -1, v42, -1, 1) != 2 )
      {
        v44 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v59, L"/tileid ");
        length = 0;
        v45 = WindowsGetStringRawBuffer(string, &length);
        v63 = 0;
        v64 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v63, v45, length);
        v46 = &v63;
        if ( *((_QWORD *)&v64 + 1) > 7u )
          v46 = (__int128 *)v63;
        std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v44, v46, v64);
        std::wstring::~wstring(&v63);
      }
      v41 = string;
    }
    WindowsDeleteString(v41);
    string = 0;
    WindowsDeleteString(v54[0]);
    v54[0] = 0;
    goto LABEL_64;
  }
  if ( v53 == 3 )
  {
    v52 = 0;
    v20 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a3)(
            a3,
            &GUID_bb2afc33_93b1_42ed_8b26_236dd9c78496,
            &v52);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v20,
        bIgnoreCase);
    string = 0;
    v21 = v52;
    v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v52 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v23 = v22(v21, &string);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD8,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v23,
        bIgnoreCase);
    v24 = WindowsGetStringRawBuffer(string, 0);
    GetFileTypeParameterList(v55, a2, v24);
    v25 = a2 + 45;
    if ( v56 )
    {
      if ( a2[48] > 7u )
        v25 = (_QWORD *)*v25;
      v26 = (_QWORD *)GenerateArgList(&v63, v25, v55);
      v27 = v26[2];
      if ( v26[3] > 7u )
        v26 = (_QWORD *)*v26;
      std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v59, v26, v27);
      std::wstring::~wstring(&v63);
    }
    else
    {
      if ( a2[48] > 7u )
        v25 = (_QWORD *)*v25;
      std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v59, v25, a2[47]);
    }
    if ( v56 )
      std::wstring::~wstring(v55);
    WindowsDeleteString(string);
    string = 0;
LABEL_64:
    v47 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    }
    goto LABEL_66;
  }
  if ( v53 != 4 )
  {
    v7 = a2[26];
    if ( v53 != 1010 )
    {
      if ( v7 )
      {
        v8 = a2 + 24;
        if ( a2[27] > 7u )
          v8 = (_QWORD *)*v8;
        std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v59, v8, v7);
      }
      goto LABEL_66;
    }
    if ( v7 )
    {
      v9 = a2 + 24;
      if ( a2[27] > 7u )
        v9 = (_QWORD *)*v9;
      v10 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v59, v9, v7);
      std::operator<<<unsigned short,std::char_traits<unsigned short>>(v10, L" ");
    }
    v52 = 0;
    v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a3)(
            a3,
            &GUID_92a86f82_5290_431d_be85_c4aaeeb8685f,
            &v52);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC9,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v11,
        bIgnoreCase);
    string = 0;
    v12 = v52;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v52 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v14 = v13(v12, &string);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCC,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v14,
        bIgnoreCase);
    length = 0;
    v15 = WindowsGetStringRawBuffer(string, &length);
    v63 = 0;
    v64 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v63, v15, length);
    v16 = &v63;
    if ( *((_QWORD *)&v64 + 1) > 7u )
      v16 = (__int128 *)v63;
    std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v59, v16, v64);
    std::wstring::~wstring(&v63);
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_64;
  }
  GetProtocolParameterList(v55, a2);
  v17 = a2 + 45;
  if ( v56 )
  {
    if ( a2[48] > 7u )
      v17 = (_QWORD *)*v17;
    v18 = (_QWORD *)GenerateArgList(&v63, v17, v55);
    v19 = v18[2];
    if ( v18[3] > 7u )
      v18 = (_QWORD *)*v18;
    std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v59, v18, v19);
    std::wstring::~wstring(&v63);
  }
  else
  {
    if ( a2[48] > 7u )
      v17 = (_QWORD *)*v17;
    std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(v59, v17, a2[47]);
  }
  if ( v56 )
    std::wstring::~wstring(v55);
LABEL_66:
  std::basic_stringbuf<unsigned short>::str(v60, a1);
  *(_QWORD *)((char *)v58 + *(int *)(v58[0] + 4LL)) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
  *(int *)((char *)&v57 + *(int *)(v58[0] + 4LL)) = *(_DWORD *)(v58[0] + 4LL) - 152;
  std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v60);
  std::basic_iostream<unsigned short>::~basic_iostream<unsigned short,std::char_traits<unsigned short>>(v61);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v62);
  return a1;
}

```

## disassembly

```asm
0x1800b3a78  mov     [rsp-8+arg_18], rbx
0x1800b3a7d  push    rbp
0x1800b3a7e  push    rsi
0x1800b3a7f  push    rdi
0x1800b3a80  push    r14
0x1800b3a82  push    r15
0x1800b3a84  lea     rbp, [rsp-0C0h]
0x1800b3a8c  sub     rsp, 1C0h
0x1800b3a93  mov     rax, cs:__security_cookie
0x1800b3a9a  xor     rax, rsp
0x1800b3a9d  mov     [rbp+0E0h+var_30], rax
0x1800b3aa4  mov     rbx, r8
0x1800b3aa7  mov     rsi, rdx
0x1800b3aaa  mov     r14, rcx
0x1800b3aad  mov     [rsp+1E0h+var_1A0], rcx
0x1800b3ab2  xor     r15d, r15d
0x1800b3ab5  lea     rcx, [rbp+0E0h+var_150]
0x1800b3ab9  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x1800b3abe  nop
0x1800b3abf  mov     [rsp+1E0h+var_198], r15d
0x1800b3ac4  mov     rax, [rbx]
0x1800b3ac7  lea     rdx, [rsp+1E0h+var_198]
0x1800b3acc  mov     rcx, rbx
0x1800b3acf  mov     rax, [rax+30h]
0x1800b3ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3ad8  mov     rcx, [rbp+0E8h]; this
0x1800b3adf  test    eax, eax
0x1800b3ae1  js      loc_1800B4166
0x1800b3ae7  mov     ecx, [rsp+1E0h+var_198]
0x1800b3aeb  test    ecx, ecx
0x1800b3aed  jz      loc_1800B3E2C
0x1800b3af3  sub     ecx, 3
0x1800b3af6  jz      loc_1800B3D01
0x1800b3afc  sub     ecx, 1
0x1800b3aff  jz      loc_1800B3C70
0x1800b3b05  mov     r8, [rsi+0D0h]
0x1800b3b0c  cmp     ecx, 3EEh
0x1800b3b12  jz      short loc_1800B3B3C
0x1800b3b14  test    r8, r8
0x1800b3b17  jz      loc_1800B40C9
0x1800b3b1d  lea     rdx, [rsi+0C0h]
0x1800b3b24  cmp     qword ptr [rdx+18h], 7
0x1800b3b29  jbe     short loc_1800B3B2E
0x1800b3b2b  mov     rdx, [rdx]
0x1800b3b2e  lea     rcx, [rbp+0E0h+var_140]
0x1800b3b32  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x1800b3b37  jmp     loc_1800B40C9
0x1800b3b3c  test    r8, r8
0x1800b3b3f  jz      short loc_1800B3B6A
0x1800b3b41  lea     rdx, [rsi+0C0h]
0x1800b3b48  cmp     qword ptr [rdx+18h], 7
0x1800b3b4d  jbe     short loc_1800B3B52
0x1800b3b4f  mov     rdx, [rdx]
0x1800b3b52  lea     rcx, [rbp+0E0h+var_140]
0x1800b3b56  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x1800b3b5b  lea     rdx, asc_1800D7C84; " "
0x1800b3b62  mov     rcx, rax
0x1800b3b65  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800b3b6a  mov     [rsp+1E0h+var_1A0], r15
0x1800b3b6f  mov     rax, [rbx]
0x1800b3b72  lea     r8, [rsp+1E0h+var_1A0]
0x1800b3b77  lea     rdx, _GUID_92a86f82_5290_431d_be85_c4aaeeb8685f
0x1800b3b7e  mov     rcx, rbx
0x1800b3b81  mov     rax, [rax]
0x1800b3b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3b89  mov     rcx, [rbp+0E8h]; this
0x1800b3b90  test    eax, eax
0x1800b3b92  js      loc_1800B417B
0x1800b3b98  mov     [rsp+1E0h+string], r15
0x1800b3b9d  mov     rdi, [rsp+1E0h+var_1A0]
0x1800b3ba2  mov     rax, [rdi]
0x1800b3ba5  mov     rbx, [rax+30h]
0x1800b3ba9  xor     ecx, ecx; string
0x1800b3bab  call    cs:__imp_WindowsDeleteString
0x1800b3bb2  nop     dword ptr [rax+rax+00h]
0x1800b3bb7  mov     [rsp+1E0h+string], r15
0x1800b3bbc  lea     rdx, [rsp+1E0h+string]
0x1800b3bc1  mov     rcx, rdi
0x1800b3bc4  mov     rax, rbx
0x1800b3bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3bcc  mov     rcx, [rbp+0E8h]; this
0x1800b3bd3  test    eax, eax
0x1800b3bd5  js      loc_1800B4190
0x1800b3bdb  mov     [rsp+1E0h+length], r15d
0x1800b3be0  lea     rdx, [rsp+1E0h+length]; length
0x1800b3be5  mov     rcx, [rsp+1E0h+string]; string
0x1800b3bea  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b3bf1  nop     dword ptr [rax+rax+00h]
0x1800b3bf6  xorps   xmm0, xmm0
0x1800b3bf9  movups  [rbp+0E0h+var_50], xmm0
0x1800b3c00  xorps   xmm1, xmm1
0x1800b3c03  movdqu  [rbp+0E0h+var_40], xmm1
0x1800b3c0b  mov     r8d, [rsp+1E0h+length]
0x1800b3c10  mov     rdx, rax
0x1800b3c13  lea     rcx, [rbp+0E0h+var_50]
0x1800b3c1a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800b3c1f  nop
0x1800b3c20  lea     rdx, [rbp+0E0h+var_50]
0x1800b3c27  cmp     qword ptr [rbp+0E0h+var_40+8], 7
0x1800b3c2f  cmova   rdx, qword ptr [rbp+0E0h+var_50]
0x1800b3c37  mov     r8, qword ptr [rbp+0E0h+var_40]
0x1800b3c3e  lea     rcx, [rbp+0E0h+var_140]
0x1800b3c42  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x1800b3c47  nop
0x1800b3c48  lea     rcx, [rbp+0E0h+var_50]; void *
0x1800b3c4f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b3c54  nop
0x1800b3c55  mov     rcx, [rsp+1E0h+string]; string
0x1800b3c5a  call    cs:__imp_WindowsDeleteString
0x1800b3c61  nop     dword ptr [rax+rax+00h]
0x1800b3c66  mov     [rsp+1E0h+string], r15
0x1800b3c6b  jmp     loc_1800B40AD
0x1800b3c70  mov     rdx, rsi
0x1800b3c73  lea     rcx, [rsp+1E0h+var_180]
0x1800b3c78  call    ?GetProtocolParameterList@@YA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBUActivationProperties@@@Z; GetProtocolParameterList(ActivationProperties const &)
0x1800b3c7d  nop
0x1800b3c7e  lea     rdx, [rsi+168h]
0x1800b3c85  cmp     [rbp+0E0h+var_160], r15b
0x1800b3c89  jz      short loc_1800B3CD0
0x1800b3c8b  cmp     qword ptr [rdx+18h], 7
0x1800b3c90  jbe     short loc_1800B3C95
0x1800b3c92  mov     rdx, [rdx]
0x1800b3c95  lea     r8, [rsp+1E0h+var_180]
0x1800b3c9a  lea     rcx, [rbp+0E0h+var_50]
0x1800b3ca1  call    ?GenerateArgList@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGAEAV12@@Z; GenerateArgList(ushort const *,std::wstring &)
0x1800b3ca6  nop
0x1800b3ca7  mov     r8, [rax+10h]
0x1800b3cab  cmp     qword ptr [rax+18h], 7
0x1800b3cb0  jbe     short loc_1800B3CB5
0x1800b3cb2  mov     rax, [rax]
0x1800b3cb5  mov     rdx, rax
0x1800b3cb8  lea     rcx, [rbp+0E0h+var_140]
0x1800b3cbc  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x1800b3cc1  nop
0x1800b3cc2  lea     rcx, [rbp+0E0h+var_50]; void *
0x1800b3cc9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b3cce  jmp     short loc_1800B3CE8
0x1800b3cd0  mov     r8, [rdx+10h]
0x1800b3cd4  cmp     qword ptr [rdx+18h], 7
0x1800b3cd9  jbe     short loc_1800B3CDE
0x1800b3cdb  mov     rdx, [rdx]
0x1800b3cde  lea     rcx, [rbp+0E0h+var_140]
0x1800b3ce2  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x1800b3ce7  nop
0x1800b3ce8  cmp     [rbp+0E0h+var_160], r15b
0x1800b3cec  jz      loc_1800B40C9
0x1800b3cf2  lea     rcx, [rsp+1E0h+var_180]; void *
0x1800b3cf7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b3cfc  jmp     loc_1800B40C9
0x1800b3d01  mov     [rsp+1E0h+var_1A0], r15
0x1800b3d06  mov     rax, [rbx]
0x1800b3d09  lea     r8, [rsp+1E0h+var_1A0]
0x1800b3d0e  lea     rdx, _GUID_bb2afc33_93b1_42ed_8b26_236dd9c78496
0x1800b3d15  mov     rcx, rbx
0x1800b3d18  mov     rax, [rax]
0x1800b3d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3d20  mov     rcx, [rbp+0E8h]; this
0x1800b3d27  test    eax, eax
0x1800b3d29  js      loc_1800B41A5
0x1800b3d2f  mov     [rsp+1E0h+string], r15
0x1800b3d34  mov     rdi, [rsp+1E0h+var_1A0]
0x1800b3d39  mov     rax, [rdi]
0x1800b3d3c  mov     rbx, [rax+38h]
0x1800b3d40  xor     ecx, ecx; string
0x1800b3d42  call    cs:__imp_WindowsDeleteString
0x1800b3d49  nop     dword ptr [rax+rax+00h]
0x1800b3d4e  mov     [rsp+1E0h+string], r15
0x1800b3d53  lea     rdx, [rsp+1E0h+string]
0x1800b3d58  mov     rcx, rdi
0x1800b3d5b  mov     rax, rbx
0x1800b3d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3d63  mov     rcx, [rbp+0E8h]; this
0x1800b3d6a  test    eax, eax
0x1800b3d6c  js      loc_1800B41BA
0x1800b3d72  xor     edx, edx; length
0x1800b3d74  mov     rcx, [rsp+1E0h+string]; string
0x1800b3d79  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b3d80  nop     dword ptr [rax+rax+00h]
0x1800b3d85  mov     r8, rax
0x1800b3d88  mov     rdx, rsi
0x1800b3d8b  lea     rcx, [rsp+1E0h+var_180]
0x1800b3d90  call    ?GetFileTypeParameterList@@YA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBUActivationProperties@@PEBG@Z; GetFileTypeParameterList(ActivationProperties const &,ushort const *)
0x1800b3d95  nop
0x1800b3d96  lea     rdx, [rsi+168h]
0x1800b3d9d  cmp     [rbp+0E0h+var_160], r15b
0x1800b3da1  jz      short loc_1800B3DE8
0x1800b3da3  cmp     qword ptr [rdx+18h], 7
0x1800b3da8  jbe     short loc_1800B3DAD
0x1800b3daa  mov     rdx, [rdx]
0x1800b3dad  lea     r8, [rsp+1E0h+var_180]
0x1800b3db2  lea     rcx, [rbp+0E0h+var_50]
0x1800b3db9  call    ?GenerateArgList@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGAEAV12@@Z; GenerateArgList(ushort const *,std::wstring &)
0x1800b3dbe  nop
0x1800b3dbf  mov     r8, [rax+10h]
0x1800b3dc3  cmp     qword ptr [rax+18h], 7
0x1800b3dc8  jbe     short loc_1800B3DCD
0x1800b3dca  mov     rax, [rax]
0x1800b3dcd  mov     rdx, rax
0x1800b3dd0  lea     rcx, [rbp+0E0h+var_140]
0x1800b3dd4  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x1800b3dd9  nop
0x1800b3dda  lea     rcx, [rbp+0E0h+var_50]; void *
0x1800b3de1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b3de6  jmp     short loc_1800B3E00
0x1800b3de8  mov     r8, [rdx+10h]
0x1800b3dec  cmp     qword ptr [rdx+18h], 7
0x1800b3df1  jbe     short loc_1800B3DF6
0x1800b3df3  mov     rdx, [rdx]
0x1800b3df6  lea     rcx, [rbp+0E0h+var_140]
0x1800b3dfa  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x1800b3dff  nop
0x1800b3e00  cmp     [rbp+0E0h+var_160], r15b
0x1800b3e04  jz      short loc_1800B3E11
0x1800b3e06  lea     rcx, [rsp+1E0h+var_180]; void *
0x1800b3e0b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b3e10  nop
0x1800b3e11  mov     rcx, [rsp+1E0h+string]; string
0x1800b3e16  call    cs:__imp_WindowsDeleteString
0x1800b3e1d  nop     dword ptr [rax+rax+00h]
0x1800b3e22  mov     [rsp+1E0h+string], r15
0x1800b3e27  jmp     loc_1800B40AD
0x1800b3e2c  mov     r8, [rsi+0D0h]
0x1800b3e33  test    r8, r8
0x1800b3e36  jz      short loc_1800B3E61
0x1800b3e38  lea     rdx, [rsi+0C0h]
0x1800b3e3f  cmp     qword ptr [rdx+18h], 7
0x1800b3e44  jbe     short loc_1800B3E49
0x1800b3e46  mov     rdx, [rdx]
0x1800b3e49  lea     rcx, [rbp+0E0h+var_140]
0x1800b3e4d  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x1800b3e52  lea     rdx, asc_1800D7C84; " "
0x1800b3e59  mov     rcx, rax
0x1800b3e5c  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800b3e61  mov     [rsp+1E0h+var_1A0], r15
0x1800b3e66  mov     rax, [rbx]
0x1800b3e69  lea     r8, [rsp+1E0h+var_1A0]
0x1800b3e6e  lea     rdx, _GUID_fbc93e26_a14a_4b4f_82b0_33bed920af52
0x1800b3e75  mov     rcx, rbx
0x1800b3e78  mov     rax, [rax]
0x1800b3e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3e80  mov     rcx, [rbp+0E8h]; this
0x1800b3e87  test    eax, eax
0x1800b3e89  js      loc_1800B41CF
0x1800b3e8f  mov     [rsp+1E0h+var_190], r15
0x1800b3e94  mov     rdi, [rsp+1E0h+var_1A0]
0x1800b3e99  mov     rax, [rdi]
0x1800b3e9c  mov     rbx, [rax+30h]
0x1800b3ea0  xor     ecx, ecx; string
0x1800b3ea2  call    cs:__imp_WindowsDeleteString
0x1800b3ea9  nop     dword ptr [rax+rax+00h]
0x1800b3eae  mov     [rsp+1E0h+var_190], r15
0x1800b3eb3  lea     rdx, [rsp+1E0h+var_190]
0x1800b3eb8  mov     rcx, rdi
0x1800b3ebb  mov     rax, rbx
0x1800b3ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3ec3  mov     rcx, [rbp+0E8h]; this
0x1800b3eca  test    eax, eax
0x1800b3ecc  js      loc_1800B41E4
0x1800b3ed2  mov     rcx, [rsp+1E0h+var_190]; string
0x1800b3ed7  test    rcx, rcx
0x1800b3eda  jz      loc_1800B3F63
0x1800b3ee0  mov     [rsp+1E0h+length], r15d
0x1800b3ee5  lea     rdx, [rsp+1E0h+length]; length
0x1800b3eea  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b3ef1  nop     dword ptr [rax+rax+00h]
0x1800b3ef6  xorps   xmm0, xmm0
0x1800b3ef9  movups  [rbp+0E0h+var_50], xmm0
0x1800b3f00  xorps   xmm1, xmm1
0x1800b3f03  movdqu  [rbp+0E0h+var_40], xmm1
0x1800b3f0b  mov     r8d, [rsp+1E0h+length]
0x1800b3f10  mov     rdx, rax
0x1800b3f13  lea     rcx, [rbp+0E0h+var_50]
0x1800b3f1a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800b3f1f  nop
0x1800b3f20  lea     rdx, [rbp+0E0h+var_50]
0x1800b3f27  cmp     qword ptr [rbp+0E0h+var_40+8], 7
0x1800b3f2f  cmova   rdx, qword ptr [rbp+0E0h+var_50]
0x1800b3f37  mov     r8, qword ptr [rbp+0E0h+var_40]
0x1800b3f3e  lea     rcx, [rbp+0E0h+var_140]
0x1800b3f42  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x1800b3f47  lea     rdx, asc_1800D7C84; " "
0x1800b3f4e  mov     rcx, rax
0x1800b3f51  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800b3f56  nop
0x1800b3f57  lea     rcx, [rbp+0E0h+var_50]; void *
0x1800b3f5e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b3f63  mov     [rsp+1E0h+string], r15
0x1800b3f68  mov     rdi, [rsp+1E0h+var_1A0]
0x1800b3f6d  mov     rax, [rdi]
0x1800b3f70  mov     rbx, [rax+38h]
0x1800b3f74  xor     ecx, ecx; string
0x1800b3f76  call    cs:__imp_WindowsDeleteString
0x1800b3f7d  nop     dword ptr [rax+rax+00h]
0x1800b3f82  mov     [rsp+1E0h+string], r15
0x1800b3f87  lea     rdx, [rsp+1E0h+string]
0x1800b3f8c  mov     rcx, rdi
0x1800b3f8f  mov     rax, rbx
0x1800b3f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3f97  mov     rcx, [rbp+0E8h]; this
0x1800b3f9e  test    eax, eax
  ... truncated ...
```
