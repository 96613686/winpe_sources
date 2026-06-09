# MMCUpdateRegistry(int,CObjectRegParams const *,CControlRegParams const *)

- ea: `0x180015ca0`
- end: `0x18001634a`
- name: `?MMCUpdateRegistry@@YAJHPEBVCObjectRegParams@@PEBVCControlRegParams@@@Z`
- size: `1706`
- prototype: `__int64 __fastcall(int, const IID *, const IID *)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180003b60`
- `0x180003c40`
- `0x180003f10`
- `0x1800041f0`
- `0x180008cdc`
- `0x18000cbfc`
- `0x18000ed64`
- `0x180012154`
- `0x1800121b4`
- `0x1800150e4`
- `0x180015198`
- `0x180015220`
- `0x18001549c`
- `0x180015c68`
- `0x180015ca0`
- `0x1800164b4`
- `0x1800169cc`
- `0x180016fc0`
- `0x180017024`
- `0x1800171b0`
- `0x18001b522`
- `0x18001b550`

## import_xrefs

- `msvcrt!malloc` at `0x180015dca`
- `msvcrt!malloc` at `0x180015dca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800162ce`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800162ce`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180016259`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180016259`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180015d59`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180015f70`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180015d59`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180015f70`

## string_xrefs

- `0x180015ce8`: `MMCUpdateRegistry`
- `0x180015e18`: `VCLSID`
- `0x180015ec8`: `ThreadingModel`
- `0x180016167`: `CLSID\`
- `0x1800160a3`: `            ForceRemove 'Programmable'\n            ForceRemove 'Control'\n            ForceRemove 'ToolboxBitmap32' = s '%VFileName%, %VBitmapID%'\n            'MiscStatus' = s '0'\n            {\n                '1' = s '131473'\n            }\n            'TypeLib' = s '%VLIBID%'\n            'Version' = s '%VVersion%'`
- `0x1800160b1`: `HKCR\n{\n    %%VProgID%% = s '%%VClassName%%'\n    {\n        CLSID = s '%%VCLSID%%'\n    }\n    %%VVersionIndependentProgID%% = s '%%VClassName%%'\n    {\n        CLSID = s '%%VCLSID%%'\n        CurVer = s '%%VProgID%%'\n    }\n    NoRemove CLSID\n    {\n        ForceRemove %%VCLSID%% = s '%%VClassName%%'\n        {\n            ProgID = s '%%VProgID%%'\n            VersionIndependentProgID = s '%%VVersionIndependentProgID%%'\n            %%ServerType%% = s '%%VFileName%%'\n            {\n     `

## pseudocode

```c
__int64 __fastcall MMCUpdateRegistry(int a1, const IID *a2, const IID *a3)
{
  int v6; // ecx
  unsigned int v7; // ebx
  HRESULT v8; // eax
  unsigned __int16 *v9; // rbx
  unsigned int i; // ecx
  int v11; // eax
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rax
  unsigned int j; // ebx
  const unsigned __int16 *v18; // r15
  const unsigned __int16 *v19; // r12
  int v20; // eax
  HRESULT v21; // eax
  unsigned __int16 *v22; // rax
  unsigned __int16 *v23; // rax
  unsigned int k; // ebx
  const unsigned __int16 *v25; // r15
  const unsigned __int16 *v26; // r12
  int v27; // eax
  const wchar_t *v28; // r9
  int v29; // eax
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rdx
  BOOL v36; // ebx
  const WCHAR *v37; // r8
  DWORD cbData; // eax
  const IID *v39; // rdi
  __int64 v40; // rdx
  unsigned int lpData; // [rsp+20h] [rbp-E0h]
  LPOLESTR lpsz; // [rsp+30h] [rbp-D0h] BYREF
  int v44; // [rsp+38h] [rbp-C8h] BYREF
  int v45; // [rsp+3Ch] [rbp-C4h]
  __int128 v46; // [rsp+40h] [rbp-C0h]
  LPOLESTR v47[2]; // [rsp+50h] [rbp-B0h] BYREF
  void *v48; // [rsp+60h] [rbp-A0h] BYREF
  int v49; // [rsp+68h] [rbp-98h]
  int v50; // [rsp+6Ch] [rbp-94h]
  _OWORD v51[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v52; // [rsp+90h] [rbp-70h]
  char v53; // [rsp+98h] [rbp-68h]
  unsigned __int16 *v54; // [rsp+A0h] [rbp-60h]
  unsigned __int16 *v55[13]; // [rsp+A8h] [rbp-58h]
  HKEY hKey; // [rsp+110h] [rbp+10h] BYREF
  __int128 v57; // [rsp+118h] [rbp+18h]
  LPCWSTR lpSubKey[3]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int64 v59; // [rsp+148h] [rbp+48h]
  unsigned __int16 *v60; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 *v61[5]; // [rsp+158h] [rbp+58h]
  _BYTE v62[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v63[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 v65[904]; // [rsp+2E0h] [rbp+1E0h] BYREF

  v46 = 0;
  ++mmcerror::SC::s_CallDepth;
  mmcerror::SC::SetFunctionName((mmcerror::SC *)&v44, L"MMCUpdateRegistry");
  v6 = -2147467259;
  if ( a2 )
    v6 = 0;
  v57 = 0;
  LODWORD(hKey) = 3;
  HIDWORD(hKey) = v6;
  v44 = 3;
  v45 = v6;
  mmcerror::SC::Trace_((mmcerror::SC *)&hKey);
  if ( !(unsigned __int8)mmcerror::SC::operator bool(&v44) )
  {
    lpsz = 0;
    v8 = StringFromCLSID(a2, &lpsz);
    v44 = 3;
    v45 = v8;
    if ( (unsigned __int8)mmcerror::SC::operator bool(&v44) )
    {
      v7 = mmcerror::SC::ToHr((mmcerror::SC *)&v44);
LABEL_66:
      CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&lpsz);
      goto LABEL_67;
    }
    v9 = off_18002B2B8;
    for ( i = 0; i < 4; ++i )
    {
      if ( LODWORD(qword_18002B2B0[2 * (int)i]) == a2[13].Data1 )
      {
        v9 = (unsigned __int16 *)qword_18002B2B0[2 * (int)i + 1];
        break;
      }
    }
    v49 = 0;
    v50 = 10;
    v48 = malloc(0x50u);
    memset(v51, 0, sizeof(v51));
    v52 = 0;
    v53 = 0;
    v11 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)v51);
    if ( v11 >= 0 )
      v53 = 1;
    v44 = 3;
    v45 = v11;
    if ( !(unsigned __int8)mmcerror::SC::operator bool(&v44) )
    {
      v54 = L"VCLSID";
      v55[0] = lpsz;
      v55[1] = L"VFileName";
      v12 = (unsigned __int16 *)&a2[1];
      if ( *(_QWORD *)a2[2].Data4 >= 8u )
        v12 = *(unsigned __int16 **)v12;
      v55[2] = v12;
      v55[3] = L"VClassName";
      v13 = (unsigned __int16 *)&a2[5];
      if ( *(_QWORD *)a2[6].Data4 >= 8u )
        v13 = *(unsigned __int16 **)v13;
      v55[4] = v13;
      v55[5] = L"VProgID";
      v14 = (unsigned __int16 *)&a2[7];
      if ( *(_QWORD *)a2[8].Data4 >= 8u )
        v14 = *(unsigned __int16 **)v14;
      v55[6] = v14;
      v55[7] = L"VVersionIndependentProgID";
      v15 = (unsigned __int16 *)&a2[9];
      if ( *(_QWORD *)a2[10].Data4 >= 8u )
        v15 = *(unsigned __int16 **)v15;
      v55[8] = v15;
      v55[9] = L"ServerType";
      if ( *(_QWORD *)a2[12].Data4 < 8u )
        v16 = (unsigned __int16 *)&a2[11];
      else
        v16 = *(unsigned __int16 **)&a2[11].Data1;
      v55[10] = v16;
      v55[11] = L"ThreadingModel";
      v55[12] = v9;
      for ( j = 0; j < 7; ++j )
      {
        v18 = v55[2 * (int)j];
        v19 = v55[2 * (int)j - 1];
        v20 = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v48, v19, v18);
        v44 = 3;
        v45 = v20;
        if ( (unsigned __int8)mmcerror::SC::operator bool(&v44) )
          goto LABEL_64;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
          WPP_SF_SS(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            10,
            (unsigned int)WPP_a680e13931b236967ab195d811b2f3db_Traceguids,
            (_DWORD)v19,
            (__int64)v18);
      }
      if ( a3 )
      {
        v47[0] = 0;
        v21 = StringFromCLSID(a3, v47);
        v44 = 3;
        v45 = v21;
        if ( (unsigned __int8)mmcerror::SC::operator bool(&v44) )
        {
LABEL_35:
          v7 = mmcerror::SC::ToHr((mmcerror::SC *)&v44);
          CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(v47);
LABEL_65:
          ATL::CRegObject::~CRegObject((ATL::CRegObject *)&v48);
          goto LABEL_66;
        }
        v60 = L"VLIBID";
        v61[0] = v47[0];
        v61[1] = L"VBitmapID";
        v22 = (unsigned __int16 *)&a3[1];
        if ( *(_QWORD *)a3[2].Data4 >= 8u )
          v22 = *(unsigned __int16 **)v22;
        v61[2] = v22;
        v61[3] = L"VVersion";
        v23 = (unsigned __int16 *)&a3[3];
        if ( *(_QWORD *)a3[4].Data4 >= 8u )
          v23 = *(unsigned __int16 **)v23;
        v61[4] = v23;
        for ( k = 0; k < 3; ++k )
        {
          v25 = v61[2 * (int)k];
          v26 = v61[2 * (int)k - 1];
          v27 = ATL::CRegObject::AddReplacement((ATL::CRegObject *)&v48, v26, v25);
          v44 = 3;
          v45 = v27;
          if ( (unsigned __int8)mmcerror::SC::operator bool(&v44) )
            goto LABEL_35;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
            WPP_SF_SS(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              11,
              (unsigned int)WPP_a680e13931b236967ab195d811b2f3db_Traceguids,
              (_DWORD)v26,
              (__int64)v25);
        }
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(v47);
      }
      v28 = L"            ForceRemove 'Programmable'\n"
             "            ForceRemove 'Control'\n"
             "            ForceRemove 'ToolboxBitmap32' = s '%VFileName%, %VBitmapID%'\n"
             "            'MiscStatus' = s '0'\n"
             "            {\n"
             "                '1' = s '131473'\n"
             "            }\n"
             "            'TypeLib' = s '%VLIBID%'\n"
             "            'Version' = s '%VVersion%'";
      if ( !a3 )
        v28 = &String;
      v29 = StringCchPrintfW(
              v65,
              0x383u,
              L"HKCR\n"
               "{\n"
               "    %%VProgID%% = s '%%VClassName%%'\n"
               "    {\n"
               "        CLSID = s '%%VCLSID%%'\n"
               "    }\n"
               "    %%VVersionIndependentProgID%% = s '%%VClassName%%'\n"
               "    {\n"
               "        CLSID = s '%%VCLSID%%'\n"
               "        CurVer = s '%%VProgID%%'\n"
               "    }\n"
               "    NoRemove CLSID\n"
               "    {\n"
               "        ForceRemove %%VCLSID%% = s '%%VClassName%%'\n"
               "        {\n"
               "            ProgID = s '%%VProgID%%'\n"
               "            VersionIndependentProgID = s '%%VVersionIndependentProgID%%'\n"
               "            %%ServerType%% = s '%%VFileName%%'\n"
               "            {\n"
               "                val ThreadingModel = s '%%ThreadingModel%%'\n"
               "            }\n"
               "            %s\n"
               "        }\n"
               "    }\n"
               "}",
              v28);
      v44 = 3;
      v45 = v29;
      if ( !(unsigned __int8)mmcerror::SC::operator bool(&v44) )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
          WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_a680e13931b236967ab195d811b2f3db_Traceguids, v65);
        v30 = ATL::CRegObject::RegisterWithString((ATL::CRegObject *)&v48, v65, a1 != 0);
        v44 = 3;
        v45 = v30;
        if ( !(unsigned __int8)mmcerror::SC::operator bool(&v44) && a1 && *(_QWORD *)&a2[4].Data1 )
        {
          tstring::tstring((tstring *)v62, L"CLSID\\");
          std::operator+<unsigned short>(&hKey);
          v59 = 7;
          lpSubKey[2] = 0;
          LOWORD(lpSubKey[0]) = 0;
          std::wstring::assign(lpSubKey);
          LOBYTE(v31) = 1;
          std::wstring::_Tidy(&hKey, v31, 0);
          LOBYTE(v32) = 1;
          std::wstring::_Tidy(v62, v32, 0);
          tstring::tstring((tstring *)&v60, L"\\");
          v33 = std::operator+<unsigned short>(v63);
          std::wstring::append(lpSubKey, v33, 0, -1);
          LOBYTE(v34) = 1;
          std::wstring::_Tidy(v63, v34, 0);
          LOBYTE(v35) = 1;
          std::wstring::_Tidy(&v60, v35, 0);
          memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
          VersionInformation.dwOSVersionInfoSize = 276;
          GetVersionExW(&VersionInformation);
          v36 = VersionInformation.dwPlatformId == 2;
          hKey = 0;
          v57 = 0u;
          v37 = (const WCHAR *)lpSubKey;
          if ( v59 >= 8 )
            v37 = lpSubKey[0];
          if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)&hKey, HKEY_CLASSES_ROOT, v37, 0x20006u, lpData) )
          {
            cbData = 2 * a2[4].Data1 + 2;
            v39 = a2 + 3;
            if ( *(_QWORD *)v39[1].Data4 >= 8u )
              v39 = *(const IID **)&v39->Data1;
            RegSetValueExW(hKey, 0, 0, v36 + 1, (const BYTE *)v39, cbData);
          }
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          LOBYTE(v40) = 1;
          std::wstring::_Tidy(lpSubKey, v40, 0);
        }
      }
    }
LABEL_64:
    v7 = mmcerror::SC::ToHr((mmcerror::SC *)&v44);
    goto LABEL_65;
  }
  v7 = mmcerror::SC::ToHr((mmcerror::SC *)&v44);
LABEL_67:
  --mmcerror::SC::s_CallDepth;
  mmcerror::SC::Trace_((mmcerror::SC *)&v44);
  return v7;
}

```

## disassembly

```asm
0x180015ca0  mov     [rsp-8+arg_0], rbx
0x180015ca5  push    rbp
0x180015ca6  push    rsi
0x180015ca7  push    rdi
0x180015ca8  push    r12
0x180015caa  push    r13
0x180015cac  push    r14
0x180015cae  push    r15
0x180015cb0  lea     rbp, [rsp-900h]
0x180015cb8  sub     rsp, 0A00h
0x180015cbf  mov     rax, cs:__security_cookie
0x180015cc6  xor     rax, rsp
0x180015cc9  mov     [rbp+930h+var_40], rax
0x180015cd0  mov     r14, r8
0x180015cd3  mov     rdi, rdx
0x180015cd6  mov     r13d, ecx
0x180015cd9  xorps   xmm0, xmm0
0x180015cdc  movdqu  [rsp+0A30h+var_9F0], xmm0
0x180015ce2  inc     cs:?s_CallDepth@SC@mmcerror@@0IA; uint mmcerror::SC::s_CallDepth
0x180015ce8  lea     rdx, aMmcupdateregis_0; "MMCUpdateRegistry"
0x180015cef  lea     rcx, [rsp+0A30h+var_9F8]; this
0x180015cf4  call    ?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x180015cf9  mov     ecx, 80004005h
0x180015cfe  xor     r15d, r15d
0x180015d01  test    rdi, rdi
0x180015d04  cmovnz  ecx, r15d
0x180015d08  xorps   xmm0, xmm0
0x180015d0b  movdqu  [rbp+930h+var_918], xmm0
0x180015d10  lea     r12d, [r15+3]
0x180015d14  mov     dword ptr [rbp+930h+hKey], r12d
0x180015d18  mov     dword ptr [rbp+930h+hKey+4], ecx
0x180015d1b  mov     [rsp+0A30h+var_9F8], r12d
0x180015d20  mov     [rsp+0A30h+var_9F4], ecx
0x180015d24  lea     rcx, [rbp+930h+hKey]; this
0x180015d28  call    ?Trace_@SC@mmcerror@@QEBAXXZ; mmcerror::SC::Trace_(void)
0x180015d2d  lea     rcx, [rsp+0A30h+var_9F8]
0x180015d32  call    ??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180015d37  test    al, al
0x180015d39  jz      short loc_180015D4C
0x180015d3b  lea     rcx, [rsp+0A30h+var_9F8]; this
0x180015d40  call    ?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x180015d45  mov     ebx, eax
0x180015d47  jmp     loc_18001630E
0x180015d4c  mov     [rsp+0A30h+lpsz], r15
0x180015d51  lea     rdx, [rsp+0A30h+lpsz]; lplpsz
0x180015d56  mov     rcx, rdi; rclsid
0x180015d59  call    cs:__imp_StringFromCLSID
0x180015d5f  mov     [rsp+0A30h+var_9F8], r12d
0x180015d64  mov     [rsp+0A30h+var_9F4], eax
0x180015d68  lea     rcx, [rsp+0A30h+var_9F8]
0x180015d6d  call    ??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180015d72  test    al, al
0x180015d74  jz      short loc_180015D87
0x180015d76  lea     rcx, [rsp+0A30h+var_9F8]; this
0x180015d7b  call    ?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x180015d80  mov     ebx, eax
0x180015d82  jmp     loc_180016303
0x180015d87  mov     rbx, cs:off_18002B2B8; "Apartment"
0x180015d8e  mov     ecx, r15d
0x180015d91  lea     r8, qword_18002B2B0
0x180015d98  cmp     ecx, 4
0x180015d9b  jnb     short loc_180015DB8
0x180015d9d  movsxd  rdx, ecx
0x180015da0  add     rdx, rdx
0x180015da3  mov     eax, [rdi+0D0h]
0x180015da9  cmp     [r8+rdx*8], eax
0x180015dad  jz      short loc_180015DB3
0x180015daf  inc     ecx
0x180015db1  jmp     short loc_180015D98
0x180015db3  mov     rbx, [r8+rdx*8+8]
0x180015db8  mov     [rsp+0A30h+var_9C8], r15d
0x180015dbd  mov     [rsp+0A30h+var_9C4], 0Ah
0x180015dc5  mov     ecx, 50h ; 'P'; Size
0x180015dca  call    cs:__imp_malloc
0x180015dd0  mov     [rsp+0A30h+var_9D0], rax
0x180015dd5  xorps   xmm0, xmm0
0x180015dd8  xor     eax, eax
0x180015dda  movups  [rsp+0A30h+var_9C0], xmm0
0x180015ddf  movups  [rbp+930h+var_9B0], xmm0
0x180015de3  mov     [rbp+930h+var_9A0], rax
0x180015de7  mov     [rbp+930h+var_998], r15b
0x180015deb  lea     rcx, [rsp+0A30h+var_9C0]; this
0x180015df0  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180015df5  test    eax, eax
0x180015df7  js      short loc_180015DFD
0x180015df9  mov     [rbp+930h+var_998], 1
0x180015dfd  mov     [rsp+0A30h+var_9F8], r12d
0x180015e02  mov     [rsp+0A30h+var_9F4], eax
0x180015e06  lea     rcx, [rsp+0A30h+var_9F8]
0x180015e0b  call    ??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180015e10  test    al, al
0x180015e12  jnz     loc_1800162EC
0x180015e18  lea     rax, aVclsid; "VCLSID"
0x180015e1f  mov     [rbp+930h+var_990], rax
0x180015e23  mov     rax, [rsp+0A30h+lpsz]
0x180015e28  mov     [rbp+930h+var_988], rax
0x180015e2c  lea     rax, aVfilename; "VFileName"
0x180015e33  mov     [rbp+930h+var_980], rax
0x180015e37  lea     rax, [rdi+10h]
0x180015e3b  cmp     qword ptr [rax+18h], 8
0x180015e40  jb      short loc_180015E45
0x180015e42  mov     rax, [rax]
0x180015e45  mov     [rbp+930h+var_978], rax
0x180015e49  lea     rax, aVclassname; "VClassName"
0x180015e50  mov     [rbp+930h+var_970], rax
0x180015e54  lea     rax, [rdi+50h]
0x180015e58  cmp     qword ptr [rax+18h], 8
0x180015e5d  jb      short loc_180015E62
0x180015e5f  mov     rax, [rax]
0x180015e62  mov     [rbp+930h+var_968], rax
0x180015e66  lea     rax, aVprogid; "VProgID"
0x180015e6d  mov     [rbp+930h+var_960], rax
0x180015e71  lea     rax, [rdi+70h]
0x180015e75  cmp     qword ptr [rax+18h], 8
0x180015e7a  jb      short loc_180015E7F
0x180015e7c  mov     rax, [rax]
0x180015e7f  mov     [rbp+930h+var_958], rax
0x180015e83  lea     rax, aVversionindepe; "VVersionIndependentProgID"
0x180015e8a  mov     [rbp+930h+var_950], rax
0x180015e8e  lea     rax, [rdi+90h]
0x180015e95  cmp     qword ptr [rax+18h], 8
0x180015e9a  jb      short loc_180015E9F
0x180015e9c  mov     rax, [rax]
0x180015e9f  mov     [rbp+930h+var_948], rax
0x180015ea3  lea     rax, aServertype; "ServerType"
0x180015eaa  mov     [rbp+930h+var_940], rax
0x180015eae  lea     rsi, [rdi+0B0h]
0x180015eb5  cmp     qword ptr [rsi+18h], 8
0x180015eba  jb      short loc_180015EC1
0x180015ebc  mov     rax, [rsi]
0x180015ebf  jmp     short loc_180015EC4
0x180015ec1  mov     rax, rsi
0x180015ec4  mov     [rbp+930h+var_938], rax
0x180015ec8  lea     rax, aThreadingmodel; "ThreadingModel"
0x180015ecf  mov     [rbp+930h+var_930], rax
0x180015ed3  mov     [rbp+930h+var_928], rbx
0x180015ed7  mov     ebx, r15d
0x180015eda  cmp     ebx, 7
0x180015edd  jnb     short loc_180015F57
0x180015edf  movsxd  rax, ebx
0x180015ee2  add     rax, rax
0x180015ee5  mov     r15, [rbp+rax*8+930h+var_988]
0x180015eea  mov     r12, [rbp+rax*8+930h+var_990]
0x180015eef  mov     r8, r15; unsigned __int16 *
0x180015ef2  mov     rdx, r12; unsigned __int16 *
0x180015ef5  lea     rcx, [rsp+0A30h+var_9D0]; this
0x180015efa  call    ?AddReplacement@CRegObject@ATL@@QEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180015eff  mov     [rsp+0A30h+var_9F8], 3
0x180015f07  mov     [rsp+0A30h+var_9F4], eax
0x180015f0b  lea     rcx, [rsp+0A30h+var_9F8]
0x180015f10  call    ??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180015f15  test    al, al
0x180015f17  jnz     loc_1800162EC
0x180015f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f24  lea     rax, WPP_GLOBAL_Control
0x180015f2b  cmp     rcx, rax
0x180015f2e  jz      short loc_180015F53
0x180015f30  cmp     byte ptr [rcx+19h], 4
0x180015f34  jb      short loc_180015F53
0x180015f36  mov     edx, 0Ah
0x180015f3b  mov     [rsp+0A30h+lpData], r15
0x180015f40  mov     r9, r12
0x180015f43  lea     r8, WPP_a680e13931b236967ab195d811b2f3db_Traceguids
0x180015f4a  mov     rcx, [rcx+10h]
0x180015f4e  call    WPP_SF_SS
0x180015f53  inc     ebx
0x180015f55  jmp     short loc_180015EDA
0x180015f57  xor     r15d, r15d
0x180015f5a  test    r14, r14
0x180015f5d  jz      loc_180016096
0x180015f63  mov     [rsp+0A30h+var_9E0], r15
0x180015f68  lea     rdx, [rsp+0A30h+var_9E0]; lplpsz
0x180015f6d  mov     rcx, r14; rclsid
0x180015f70  call    cs:__imp_StringFromCLSID
0x180015f76  lea     r12d, [r15+3]
0x180015f7a  mov     [rsp+0A30h+var_9F8], r12d
0x180015f7f  mov     [rsp+0A30h+var_9F4], eax
0x180015f83  lea     rcx, [rsp+0A30h+var_9F8]
0x180015f88  call    ??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180015f8d  test    al, al
0x180015f8f  jz      short loc_180015FAC
0x180015f91  lea     rcx, [rsp+0A30h+var_9F8]; this
0x180015f96  call    ?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x180015f9b  mov     ebx, eax
0x180015f9d  lea     rcx, [rsp+0A30h+var_9E0]
0x180015fa2  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180015fa7  jmp     loc_1800162F8
0x180015fac  lea     rax, aVlibid; "VLIBID"
0x180015fb3  mov     [rbp+930h+var_8E0], rax
0x180015fb7  mov     rax, [rsp+0A30h+var_9E0]
0x180015fbc  mov     [rbp+930h+var_8D8], rax
0x180015fc0  lea     rax, aVbitmapid; "VBitmapID"
0x180015fc7  mov     [rbp+930h+var_8D0], rax
0x180015fcb  lea     rax, [r14+10h]
0x180015fcf  cmp     qword ptr [rax+18h], 8
0x180015fd4  jb      short loc_180015FD9
0x180015fd6  mov     rax, [rax]
0x180015fd9  mov     [rbp+930h+var_8C8], rax
0x180015fdd  lea     rax, aVversion; "VVersion"
0x180015fe4  mov     [rbp+930h+var_8C0], rax
0x180015fe8  lea     rax, [r14+30h]
0x180015fec  cmp     qword ptr [rax+18h], 8
0x180015ff1  jb      short loc_180015FF6
0x180015ff3  mov     rax, [rax]
0x180015ff6  mov     [rbp+930h+var_8B8], rax
0x180015ffa  mov     ebx, r15d
0x180015ffd  cmp     ebx, r12d
0x180016000  jnb     loc_180016087
0x180016006  movsxd  rax, ebx
0x180016009  add     rax, rax
0x18001600c  mov     r15, [rbp+rax*8+930h+var_8D8]
0x180016011  mov     r12, [rbp+rax*8+930h+var_8E0]
0x180016016  mov     r8, r15; unsigned __int16 *
0x180016019  mov     rdx, r12; unsigned __int16 *
0x18001601c  lea     rcx, [rsp+0A30h+var_9D0]; this
0x180016021  call    ?AddReplacement@CRegObject@ATL@@QEAAJPEBG0@Z; ATL::CRegObject::AddReplacement(ushort const *,ushort const *)
0x180016026  mov     [rsp+0A30h+var_9F8], 3
0x18001602e  mov     [rsp+0A30h+var_9F4], eax
0x180016032  lea     rcx, [rsp+0A30h+var_9F8]
0x180016037  call    ??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18001603c  test    al, al
0x18001603e  jnz     loc_180015F91
0x180016044  mov     rcx, cs:WPP_GLOBAL_Control
0x18001604b  lea     rax, WPP_GLOBAL_Control
0x180016052  cmp     rcx, rax
0x180016055  jz      short loc_18001607A
0x180016057  cmp     byte ptr [rcx+19h], 4
0x18001605b  jb      short loc_18001607A
0x18001605d  mov     edx, 0Bh
0x180016062  mov     [rsp+0A30h+lpData], r15
0x180016067  mov     r9, r12
0x18001606a  lea     r8, WPP_a680e13931b236967ab195d811b2f3db_Traceguids
0x180016071  mov     rcx, [rcx+10h]
0x180016075  call    WPP_SF_SS
0x18001607a  inc     ebx
0x18001607c  mov     r12d, 3
0x180016082  jmp     loc_180015FFD
0x180016087  lea     rcx, [rsp+0A30h+var_9E0]
0x18001608c  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180016091  xor     r15d, r15d
0x180016094  jmp     short loc_18001609C
0x180016096  mov     r12d, 3
0x18001609c  lea     rax, String
0x1800160a3  lea     r9, aForceremovePro; "            ForceRemove 'Programmable'"...
0x1800160aa  test    r14, r14
0x1800160ad  cmovz   r9, rax
0x1800160b1  lea     r8, aHkcrVprogidSVc; "HKCR\n{\n    %%VProgID%% = s '%%VClassN"...
0x1800160b8  mov     edx, 383h; unsigned __int64
0x1800160bd  lea     rcx, [rbp+930h+var_750]; unsigned __int16 *
0x1800160c4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800160c9  mov     [rsp+0A30h+var_9F8], r12d
0x1800160ce  mov     [rsp+0A30h+var_9F4], eax
0x1800160d2  lea     rcx, [rsp+0A30h+var_9F8]
0x1800160d7  call    ??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1800160dc  test    al, al
0x1800160de  jnz     loc_1800162EC
0x1800160e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800160eb  lea     rax, WPP_GLOBAL_Control
0x1800160f2  cmp     rcx, rax
0x1800160f5  jz      short loc_180016119
0x1800160f7  cmp     byte ptr [rcx+19h], 4
0x1800160fb  jb      short loc_180016119
0x1800160fd  mov     edx, 0Ch
0x180016102  lea     r9, [rbp+930h+var_750]
0x180016109  lea     r8, WPP_a680e13931b236967ab195d811b2f3db_Traceguids
0x180016110  mov     rcx, [rcx+10h]
0x180016114  call    WPP_SF_S
0x180016119  mov     r8d, r15d
0x18001611c  test    r13d, r13d
0x18001611f  setnz   r8b; int
0x180016123  lea     rdx, [rbp+930h+var_750]; unsigned __int16 *
0x18001612a  lea     rcx, [rsp+0A30h+var_9D0]; this
0x18001612f  call    ?RegisterWithString@CRegObject@ATL@@IEAAJPEBGH@Z; ATL::CRegObject::RegisterWithString(ushort const *,int)
0x180016134  mov     [rsp+0A30h+var_9F8], r12d
0x180016139  mov     [rsp+0A30h+var_9F4], eax
0x18001613d  lea     rcx, [rsp+0A30h+var_9F8]
0x180016142  call    ??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180016147  test    al, al
0x180016149  jnz     loc_1800162EC
0x18001614f  test    r13d, r13d
0x180016152  jz      loc_1800162EC
0x180016158  cmp     [rdi+40h], r15
0x18001615c  jz      loc_1800162EC
0x180016162  mov     rbx, [rsp+0A30h+lpsz]
0x180016167  lea     rdx, aClsid; "CLSID\\"
0x18001616e  lea     rcx, [rbp+930h+var_8B0]; this
0x180016175  call    ??0tstring@@QEAA@PEBG@Z; tstring::tstring(ushort const *)
0x18001617a  nop
0x18001617b  mov     r8, rbx
0x18001617e  mov     rdx, rax
0x180016181  lea     rcx, [rbp+930h+hKey]; void *
0x180016185  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x18001618a  nop
0x18001618b  mov     [rbp+930h+var_8E8], 7
0x180016193  mov     [rbp+930h+var_8F0], r15
0x180016197  mov     word ptr [rbp+930h+lpSubKey], r15w
0x18001619c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800161a0  mov     r9, rbx
0x1800161a3  xor     r8d, r8d
0x1800161a6  mov     rdx, rax
  ... truncated ...
```
