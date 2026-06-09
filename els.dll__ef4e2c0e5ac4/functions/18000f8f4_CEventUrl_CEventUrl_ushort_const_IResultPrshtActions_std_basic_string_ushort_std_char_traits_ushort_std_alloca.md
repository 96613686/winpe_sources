# CEventUrl::CEventUrl(ushort const *,IResultPrshtActions *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000f8f4`
- end: `0x180010708`
- name: `??0CEventUrl@@QEAA@PEBGPEAUIResultPrshtActions@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `3604`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000af00`

## callees

- `0x180001620`
- `0x180001750`
- `0x180001910`
- `0x180001a70`
- `0x180001dd0`
- `0x180002314`
- `0x180002630`
- `0x180002680`
- `0x1800028e0`
- `0x180002bb8`
- `0x18000513c`
- `0x18000c6c0`
- `0x18000f854`
- `0x18000f8f4`
- `0x180010948`
- `0x180010d40`
- `0x180019a28`
- `0x180019ae4`
- `0x180019b68`
- `0x180019be8`
- `0x180022292`
- `0x1800222d0`
- `0x180024010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000fe7e`
- `msvcrt!wcsrchr` at `0x18000fe7e`
- `msvcrt!_snwprintf_s` at `0x180010676`
- `msvcrt!_snwprintf_s` at `0x180010676`
- `msvcrt!swprintf_s` at `0x18000fb7b`
- `msvcrt!swprintf_s` at `0x18000fc2b`
- `msvcrt!swprintf_s` at `0x18000fcad`
- `msvcrt!swprintf_s` at `0x18000fb7b`
- `msvcrt!swprintf_s` at `0x18000fc2b`
- `msvcrt!swprintf_s` at `0x18000fcad`
- `msvcrt!_itow` at `0x18000fdee`
- `msvcrt!_itow` at `0x18000fdee`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800101af`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800101af`
- `msvcrt!_ultow` at `0x18000fd7a`
- `msvcrt!_ultow` at `0x18000fd7a`
- `KERNEL32!HeapFree` at `0x1800106a7`
- `KERNEL32!HeapFree` at `0x1800106a7`
- `KERNEL32!GetProcessHeap` at `0x180010632`
- `KERNEL32!GetProcessHeap` at `0x180010699`
- `KERNEL32!GetProcessHeap` at `0x180010632`
- `KERNEL32!GetProcessHeap` at `0x180010699`
- `KERNEL32!HeapAlloc` at `0x180010643`
- `KERNEL32!HeapAlloc` at `0x180010643`
- `KERNEL32!GetTimeZoneInformation` at `0x18000fdc1`
- `KERNEL32!GetTimeZoneInformation` at `0x18000fdc1`
- `SHLWAPI!wnsprintfW` at `0x18000ff8f`
- `SHLWAPI!wnsprintfW` at `0x18000fff1`
- `SHLWAPI!wnsprintfW` at `0x18000ff8f`
- `SHLWAPI!wnsprintfW` at `0x18000fff1`
- `VERSION!GetFileVersionInfoW` at `0x18000ff16`
- `VERSION!GetFileVersionInfoW` at `0x18000ff16`
- `VERSION!VerQueryValueW` at `0x18000ff43`
- `VERSION!VerQueryValueW` at `0x180010082`
- `VERSION!VerQueryValueW` at `0x180010110`
- `VERSION!VerQueryValueW` at `0x18000ff43`
- `VERSION!VerQueryValueW` at `0x180010082`
- `VERSION!VerQueryValueW` at `0x180010110`
- `VERSION!GetFileVersionInfoSizeW` at `0x18000fedc`
- `VERSION!GetFileVersionInfoSizeW` at `0x18000fedc`

## string_xrefs

- `0x18001004c`: `CompanyName`

## pseudocode

```c
__int64 __fastcall CEventUrl::CEventUrl(__int64 a1, __int64 a2, __int64 a3)
{
  const WCHAR *v6; // rsi
  void *v7; // r15
  __int64 v8; // r10
  _QWORD *v9; // r12
  int v10; // r14d
  unsigned __int16 *TypeStr; // rax
  wchar_t *v12; // rax
  DWORD v13; // eax
  int v14; // ecx
  wchar_t *v15; // rax
  const wchar_t *v16; // rcx
  wchar_t *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r13
  const WCHAR *v20; // rcx
  DWORD FileVersionInfoSizeW; // eax
  DWORD v22; // ebx
  void *v23; // rax
  unsigned __int16 *v24; // rbx
  unsigned int v25; // edx
  __int64 v26; // rax
  __int64 v27; // rcx
  const WCHAR *v28; // rdx
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rcx
  const WCHAR *v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rsi
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 v49; // rax
  __int64 v50; // rdx
  int v51; // r15d
  __int64 v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // rdx
  int v57; // eax
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rdx
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rdx
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rdx
  __int64 v70; // rdx
  HANDLE ProcessHeap; // rax
  __int64 v72; // rdx
  wchar_t *v73; // rbx
  LPCWSTR *v74; // rax
  HANDLE v75; // rax
  int v76; // eax
  __int64 v78; // [rsp+20h] [rbp-E0h]
  __int64 v79; // [rsp+28h] [rbp-D8h]
  __int64 v80; // [rsp+30h] [rbp-D0h]
  unsigned int puLen; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENTLOGRECORD *v82; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpBuffer; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwHandle; // [rsp+58h] [rbp-A8h] BYREF
  int v85; // [rsp+5Ch] [rbp-A4h]
  struct CLogInfo *v86[4]; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpSubBlock[3]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v88; // [rsp+98h] [rbp-68h]
  _BYTE v89[32]; // [rsp+A0h] [rbp-60h] BYREF
  _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t Buffer[1024]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 v92[264]; // [rsp+970h] [rbp+870h] BYREF

  v86[2] = (struct CLogInfo *)a1;
  ((void (*)(void))std::wstring::wstring)();
  std::wstring::wstring(a1 + 32);
  std::wstring::wstring(a1 + 64);
  std::wstring::wstring(a1 + 96);
  std::wstring::wstring(a1 + 128);
  std::wstring::wstring(a1 + 160);
  std::wstring::wstring(a1 + 192);
  std::wstring::wstring(a1 + 224);
  std::wstring::wstring(a1 + 256);
  std::wstring::wstring(a1 + 288);
  std::wstring::wstring(a1 + 320);
  std::wstring::wstring(a1 + 352);
  std::wstring::wstring(a1 + 384);
  std::wstring::wstring(a1 + 416);
  std::wstring::wstring(a1 + 448);
  v6 = (const WCHAR *)(a1 + 480);
  v7 = 0;
  *(_QWORD *)(a1 + 496) = 0;
  *(_QWORD *)(a1 + 504) = 7;
  std::wstring::_Eos(a1 + 480, 0);
  std::wstring::assign(a1 + 480, v8, 0, -1);
  std::wstring::wstring(a1 + 512);
  std::wstring::wstring(a1 + 544);
  std::wstring::wstring(a1 + 576);
  std::wstring::wstring(a1 + 608);
  std::wstring::wstring(a1 + 640);
  std::wstring::wstring(a1 + 672);
  std::wstring::wstring(a1 + 704);
  std::wstring::wstring(a1 + 736);
  std::wstring::wstring(a1 + 768);
  std::wstring::wstring(a1 + 800);
  std::wstring::wstring(a1 + 832);
  std::wstring::wstring(a1 + 864);
  std::wstring::wstring(a1 + 896);
  std::wstring::wstring(a1 + 928);
  std::wstring::wstring(a1 + 960);
  v9 = (_QWORD *)(a1 + 992);
  std::wstring::wstring(a1 + 992, a2);
  *(_QWORD *)(a1 + 1024) = 0;
  std::wstring::wstring(a1 + 1032);
  v82 = 0;
  v10 = 0;
  v85 = 0;
  if ( !a3 )
    goto LABEL_53;
  (*(void (__fastcall **)(__int64, struct _EVENTLOGRECORD **))(*(_QWORD *)a3 + 48LL))(a3, &v82);
  if ( !v82 )
    goto LABEL_53;
  std::wstring::assign(a1, &v82[1]);
  std::wstring::operator=(a1 + 512, a1);
  EscapeUrlComponent((LPCWCH)(a1 + 512));
  swprintf_s(Buffer, 0x400u, L"%u", LOWORD(v82->EventID));
  std::wstring::assign(a1 + 32, Buffer);
  std::wstring::operator=(a1 + 544, a1 + 32);
  EscapeUrlComponent((LPCWCH)(a1 + 544));
  v86[0] = 0;
  (*(void (__fastcall **)(__int64, struct CLogInfo **))(*(_QWORD *)a3 + 40LL))(a3, v86);
  Buffer[0] = 0;
  if ( v86[0] )
    GetCategoryStr(v86[0], v82, Buffer, 0x400u);
  std::wstring::assign(a1 + 64, Buffer);
  std::wstring::operator=(a1 + 576, a1 + 64);
  EscapeUrlComponent((LPCWCH)(a1 + 576));
  swprintf_s(Buffer, 0x400u, L"%hu", v82->EventCategory);
  std::wstring::assign(a1 + 96, Buffer);
  std::wstring::operator=(a1 + 608, a1 + 96);
  EscapeUrlComponent((LPCWCH)(a1 + 608));
  TypeStr = GetTypeStr(v82->EventType);
  std::wstring::assign(a1 + 128, TypeStr);
  std::wstring::operator=(a1 + 640, a1 + 128);
  EscapeUrlComponent((LPCWCH)(a1 + 640));
  swprintf_s(Buffer, 0x400u, L"%hu", v82->EventType);
  std::wstring::assign(a1 + 160, Buffer);
  std::wstring::operator=(a1 + 672, a1 + 160);
  EscapeUrlComponent((LPCWCH)(a1 + 672));
  GetDateStr(v82->TimeGenerated, Buffer, 0x400u);
  std::wstring::assign(a1 + 192, Buffer);
  std::wstring::operator=(a1 + 704, a1 + 192);
  EscapeUrlComponent((LPCWCH)(a1 + 704));
  GetTimeStr(v82->TimeGenerated, Buffer, 0x400u);
  std::wstring::assign(a1 + 224, Buffer);
  std::wstring::operator=(a1 + 736, a1 + 224);
  EscapeUrlComponent((LPCWCH)(a1 + 736));
  v12 = _ultow(v82->TimeGenerated, Buffer, 10);
  std::wstring::assign(a1 + 256, v12);
  std::wstring::operator=(a1 + 768, a1 + 256);
  EscapeUrlComponent((LPCWCH)(a1 + 768));
  memset_0(&TimeZoneInformation, 0, sizeof(TimeZoneInformation));
  v13 = GetTimeZoneInformation(&TimeZoneInformation);
  if ( v13 == 1 )
  {
    v14 = TimeZoneInformation.StandardBias + TimeZoneInformation.Bias;
  }
  else if ( v13 == 2 )
  {
    v14 = TimeZoneInformation.DaylightBias + TimeZoneInformation.Bias;
  }
  else
  {
    v14 = 0;
  }
  v15 = _itow(v14, Buffer, 10);
  std::wstring::assign(a1 + 288, v15);
  std::wstring::operator=(a1 + 800, a1 + 288);
  EscapeUrlComponent((LPCWCH)(a1 + 800));
  if ( *(_QWORD *)(a1 + 528)
    && *(_QWORD *)(a1 + 560)
    && *(_QWORD *)(a1 + 592)
    && *(_QWORD *)(a1 + 624)
    && *(_QWORD *)(a1 + 656)
    && *(_QWORD *)(a1 + 688) )
  {
    v10 = 1;
  }
  if ( !*(_QWORD *)(a1 + 496) )
  {
LABEL_53:
    v19 = a1 + 832;
LABEL_54:
    v29 = a1 + 928;
    v34 = a1 + 960;
    goto LABEL_55;
  }
  if ( *(_QWORD *)(a1 + 504) < 8u )
    v16 = (const wchar_t *)(a1 + 480);
  else
    v16 = *(const wchar_t **)v6;
  v17 = wcsrchr(v16, 0x5Cu);
  v18 = a1 + 320;
  if ( v17 )
    std::wstring::assign(v18, v17 + 1);
  else
    std::wstring::operator=(v18, a1 + 480);
  v19 = a1 + 832;
  std::wstring::operator=(a1 + 832, a1 + 320);
  EscapeUrlComponent((LPCWCH)(a1 + 832));
  dwHandle = 0;
  if ( *(_QWORD *)(a1 + 504) < 8u )
    v20 = (const WCHAR *)(a1 + 480);
  else
    v20 = *(const WCHAR **)v6;
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(v20, &dwHandle);
  v22 = FileVersionInfoSizeW;
  if ( !FileVersionInfoSizeW )
    goto LABEL_54;
  v23 = operator new[](FileVersionInfoSizeW);
  v7 = v23;
  if ( !v23 )
    goto LABEL_54;
  if ( *(_QWORD *)(a1 + 504) >= 8u )
    v6 = *(const WCHAR **)v6;
  if ( !GetFileVersionInfoW(v6, dwHandle, v22, v23) )
    goto LABEL_54;
  lpBuffer = 0;
  puLen = 0;
  if ( !VerQueryValueW(v7, L"\\", &lpBuffer, &puLen) )
    goto LABEL_54;
  if ( !puLen )
    goto LABEL_54;
  v24 = (unsigned __int16 *)lpBuffer;
  wnsprintfW(
    Buffer,
    1024,
    L"%u.%u.%u.%u",
    *((unsigned __int16 *)lpBuffer + 5),
    *((unsigned __int16 *)lpBuffer + 4),
    *((unsigned __int16 *)lpBuffer + 7),
    *((unsigned __int16 *)lpBuffer + 6));
  std::wstring::assign(a1 + 352, Buffer);
  std::wstring::operator=(a1 + 864, a1 + 352);
  EscapeUrlComponent((LPCWCH)(a1 + 864));
  LODWORD(v80) = v24[10];
  LODWORD(v79) = v24[11];
  LODWORD(v78) = v24[8];
  wnsprintfW(Buffer, 1024, L"%u.%u.%u.%u", v24[9], v78, v79, v80);
  std::wstring::assign(a1 + 384, Buffer);
  std::wstring::operator=(a1 + 896, a1 + 384);
  EscapeUrlComponent((LPCWCH)(a1 + 896));
  if ( !(unsigned int)_DetermineSubBlockPrefix(v92, v25, v7) )
    goto LABEL_54;
  std::wstring::wstring(lpSubBlock, v92);
  v26 = std::char_traits<unsigned short>::length(L"CompanyName");
  std::wstring::append(lpSubBlock, v27, v26);
  v28 = (const WCHAR *)lpSubBlock;
  if ( v88 >= 8 )
    v28 = lpSubBlock[0];
  if ( VerQueryValueW(v7, v28, &lpBuffer, &puLen) && puLen )
  {
    std::wstring::assign(a1 + 416, lpBuffer);
    v29 = a1 + 928;
    std::wstring::operator=(a1 + 928, a1 + 416);
    EscapeUrlComponent((LPCWCH)(a1 + 928));
  }
  else
  {
    v29 = a1 + 928;
  }
  std::wstring::assign(lpSubBlock, v92);
  v30 = std::char_traits<unsigned short>::length(L"ProductName");
  std::wstring::append(lpSubBlock, v31, v30);
  v32 = (const WCHAR *)lpSubBlock;
  if ( v88 >= 8 )
    v32 = lpSubBlock[0];
  if ( VerQueryValueW(v7, v32, &lpBuffer, &puLen) && puLen )
  {
    std::wstring::assign(a1 + 448, lpBuffer);
    v34 = a1 + 960;
    std::wstring::operator=(a1 + 960, a1 + 448);
    EscapeUrlComponent((LPCWCH)(a1 + 960));
  }
  else
  {
    v34 = a1 + 960;
  }
  if ( *(_QWORD *)(a1 + 880) || *(_QWORD *)(a1 + 912) || *(_QWORD *)(a1 + 944) || *(_QWORD *)(a1 + 976) )
    v85 = 1;
  LOBYTE(v33) = 1;
  std::wstring::_Tidy(lpSubBlock, v33, 0);
LABEL_55:
  operator delete[](v7);
  std::wstring::wstring(v89);
  if ( v10 )
  {
    v35 = std::operator+<unsigned short>(lpSubBlock, L"?EvtSrc=", a1 + 512);
    std::wstring::append(v89, v35, 0, -1);
    LOBYTE(v36) = 1;
    std::wstring::_Tidy(lpSubBlock, v36, 0);
    v37 = std::operator+<unsigned short>(lpSubBlock, L"&EvtCat=", a1 + 576);
    std::wstring::append(v89, v37, 0, -1);
    LOBYTE(v38) = 1;
    std::wstring::_Tidy(lpSubBlock, v38, 0);
    v39 = std::operator+<unsigned short>(lpSubBlock, L"&EvtID=", a1 + 544);
    std::wstring::append(v89, v39, 0, -1);
    LOBYTE(v40) = 1;
    std::wstring::_Tidy(lpSubBlock, v40, 0);
    v41 = std::operator+<unsigned short>(lpSubBlock, L"&EvtCatID=", a1 + 608);
    std::wstring::append(v89, v41, 0, -1);
    LOBYTE(v42) = 1;
    std::wstring::_Tidy(lpSubBlock, v42, 0);
    v43 = std::operator+<unsigned short>(lpSubBlock, L"&EvtType=", a1 + 640);
    std::wstring::append(v89, v43, 0, -1);
    LOBYTE(v44) = 1;
    std::wstring::_Tidy(lpSubBlock, v44, 0);
    v45 = std::operator+<unsigned short>(lpSubBlock, L"&EvtTypeID=", a1 + 672);
    std::wstring::append(v89, v45, 0, -1);
    LOBYTE(v46) = 1;
    std::wstring::_Tidy(lpSubBlock, v46, 0);
    v47 = std::operator+<unsigned short>(lpSubBlock, L"&EvtRptTime=", a1 + 768);
    std::wstring::append(v89, v47, 0, -1);
    LOBYTE(v48) = 1;
    std::wstring::_Tidy(lpSubBlock, v48, 0);
    v49 = std::operator+<unsigned short>(lpSubBlock, L"&EvtTZBias=", a1 + 800);
    std::wstring::append(v89, v49, 0, -1);
    LOBYTE(v50) = 1;
    std::wstring::_Tidy(lpSubBlock, v50, 0);
  }
  v51 = v85;
  if ( v85 )
  {
    if ( !v10 )
    {
      v52 = std::char_traits<unsigned short>::length(L"?");
      std::wstring::append(v89, v53, v52);
    }
    if ( *(_QWORD *)(a1 + 944) )
    {
      if ( v10 )
      {
        v54 = std::char_traits<unsigned short>::length(L"&");
        std::wstring::append(v89, L"&", v54);
      }
      v55 = std::operator+<unsigned short>(lpSubBlock, L"CoName=", v29);
      std::wstring::append(v89, v55, 0, -1);
      LOBYTE(v56) = 1;
      std::wstring::_Tidy(lpSubBlock, v56, 0);
      v57 = 1;
    }
    else
    {
      v57 = v10;
    }
    if ( *(_QWORD *)(a1 + 976) )
    {
      if ( v57 )
      {
        v58 = std::char_traits<unsigned short>::length(L"&");
        std::wstring::append(v89, L"&", v58);
      }
      v59 = std::operator+<unsigned short>(lpSubBlock, L"ProdName=", v34);
      std::wstring::append(v89, v59, 0, -1);
      LOBYTE(v60) = 1;
      std::wstring::_Tidy(lpSubBlock, v60, 0);
      v57 = 1;
    }
    if ( *(_QWORD *)(a1 + 912) )
    {
      if ( v57 )
      {
        v61 = std::char_traits<unsigned short>::length(L"&");
        std::wstring::append(v89, L"&", v61);
      }
      v62 = std::operator+<unsigned short>(lpSubBlock, L"ProdVer=", a1 + 896);
      std::wstring::append(v89, v62, 0, -1);
      LOBYTE(v63) = 1;
      std::wstring::_Tidy(lpSubBlock, v63, 0);
      v57 = 1;
    }
    if ( *(_QWORD *)(a1 + 848) )
    {
      if ( v57 )
      {
        v64 = std::char_traits<unsigned short>::length(L"&");
        std::wstring::append(v89, L"&", v64);
      }
      v65 = std::operator+<unsigned short>(lpSubBlock, L"FileName=", v19);
      std::wstring::append(v89, v65, 0, -1);
      LOBYTE(v66) = 1;
      std::wstring::_Tidy(lpSubBlock, v66, 0);
      v57 = 1;
    }
    if ( *(_QWORD *)(a1 + 880) )
    {
      if ( v57 )
      {
        v67 = std::char_traits<unsigned short>::length(L"&");
        std::wstring::append(v89, L"&", v67);
      }
      v68 = std::operator+<unsigned short>(lpSubBlock, L"FileVer=", a1 + 864);
      std::wstring::append(v89, v68, 0, -1);
      LOBYTE(v69) = 1;
      std::wstring::_Tidy(lpSubBlock, v69, 0);
    }
  }
  std::wstring::append(a1 + 992, v89, 0, -1);
  if ( g_wszRedirectionProgram && g_wszRedirectionCmdLineParams )
  {
    std::wstring::wstring(lpSubBlock);
    if ( *(_QWORD *)(a1 + 1016) >= 8u )
      v9 = (_QWORD *)*v9;
    UrlEscapeW(lpSubBlock, v9);
    ProcessHeap = GetProcessHeap();
    v73 = (wchar_t *)HeapAlloc(ProcessHeap, 0, 0x2000u);
    if ( v73 )
    {
      v74 = lpSubBlock;
      if ( v88 >= 8 )
        v74 = (LPCWSTR *)lpSubBlock[0];
      if ( _snwprintf_s(v73, 0x1000u, 0x1000u, &g_wszRedirectionCmdLineParams, v74) > 0 )
      {
        *(_DWORD *)(a1 + 1028) = 1;
        std::wstring::assign(a1 + 1032, v73);
      }
      v75 = GetProcessHeap();
      HeapFree(v75, 0, v73);
    }
    LOBYTE(v72) = 1;
    std::wstring::_Tidy(lpSubBlock, v72, 0);
  }
  if ( v10 || (v76 = 0, v51) )
    v76 = 1;
  *(_DWORD *)(a1 + 1024) = v76;
  LOBYTE(v70) = 1;
  std::wstring::_Tidy(v89, v70, 0);
  return a1;
}

```

## disassembly

```asm
0x18000f8f4  push    rbp
0x18000f8f6  push    rbx
0x18000f8f7  push    rsi
0x18000f8f8  push    rdi
0x18000f8f9  push    r12
0x18000f8fb  push    r13
0x18000f8fd  push    r14
0x18000f8ff  push    r15
0x18000f901  lea     rbp, [rsp-0A98h]
0x18000f909  sub     rsp, 0B98h
0x18000f910  mov     rax, cs:__security_cookie
0x18000f917  xor     rax, rsp
0x18000f91a  mov     [rbp+0AD0h+var_50], rax
0x18000f921  mov     r10, r9
0x18000f924  mov     r13, r8
0x18000f927  mov     rbx, rdx
0x18000f92a  mov     rdi, rcx
0x18000f92d  mov     [rsp+0BD0h+var_B60], rcx
0x18000f932  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f937  nop
0x18000f938  lea     rcx, [rdi+20h]
0x18000f93c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f941  nop
0x18000f942  lea     rcx, [rdi+40h]
0x18000f946  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f94b  nop
0x18000f94c  lea     rcx, [rdi+60h]
0x18000f950  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f955  nop
0x18000f956  lea     rcx, [rdi+80h]
0x18000f95d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f962  nop
0x18000f963  lea     rcx, [rdi+0A0h]
0x18000f96a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f96f  nop
0x18000f970  lea     rcx, [rdi+0C0h]
0x18000f977  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f97c  nop
0x18000f97d  lea     rcx, [rdi+0E0h]
0x18000f984  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f989  nop
0x18000f98a  lea     rcx, [rdi+100h]
0x18000f991  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f996  nop
0x18000f997  lea     rcx, [rdi+120h]
0x18000f99e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f9a3  nop
0x18000f9a4  lea     rcx, [rdi+140h]
0x18000f9ab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f9b0  nop
0x18000f9b1  lea     rcx, [rdi+160h]
0x18000f9b8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f9bd  nop
0x18000f9be  lea     rcx, [rdi+180h]
0x18000f9c5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f9ca  nop
0x18000f9cb  lea     rcx, [rdi+1A0h]
0x18000f9d2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f9d7  nop
0x18000f9d8  lea     rcx, [rdi+1C0h]
0x18000f9df  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000f9e4  nop
0x18000f9e5  lea     rsi, [rdi+1E0h]
0x18000f9ec  xor     r15d, r15d
0x18000f9ef  mov     [rsi+10h], r15
0x18000f9f3  mov     qword ptr [rsi+18h], 7
0x18000f9fb  xor     edx, edx
0x18000f9fd  mov     rcx, rsi
0x18000fa00  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x18000fa05  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000fa09  xor     r8d, r8d
0x18000fa0c  mov     rdx, r10
0x18000fa0f  mov     rcx, rsi
0x18000fa12  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000fa17  nop
0x18000fa18  lea     rcx, [rdi+200h]
0x18000fa1f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000fa24  nop
0x18000fa25  lea     rcx, [rdi+220h]
0x18000fa2c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000fa31  nop
0x18000fa32  lea     rcx, [rdi+240h]
0x18000fa39  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000fa3e  nop
0x18000fa3f  lea     rcx, [rdi+260h]
0x18000fa46  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000fa4b  nop
0x18000fa4c  lea     rcx, [rdi+280h]
0x18000fa53  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000fa58  nop
0x18000fa59  lea     rcx, [rdi+2A0h]
0x18000fa60  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000fa65  nop
0x18000fa66  lea     rcx, [rdi+2C0h]
0x18000fa6d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000fa72  nop
0x18000fa73  lea     rcx, [rdi+2E0h]
0x18000fa7a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000fa7f  nop
0x18000fa80  lea     rcx, [rdi+300h]
0x18000fa87  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000fa8c  nop
0x18000fa8d  lea     rcx, [rdi+320h]
0x18000fa94  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000fa99  nop
0x18000fa9a  lea     rcx, [rdi+340h]
0x18000faa1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000faa6  nop
0x18000faa7  lea     rcx, [rdi+360h]
0x18000faae  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000fab3  nop
0x18000fab4  lea     rcx, [rdi+380h]
0x18000fabb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000fac0  nop
0x18000fac1  lea     rcx, [rdi+3A0h]
0x18000fac8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000facd  nop
0x18000face  lea     rcx, [rdi+3C0h]
0x18000fad5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000fada  nop
0x18000fadb  lea     r12, [rdi+3E0h]
0x18000fae2  mov     rdx, rbx
0x18000fae5  mov     rcx, r12
0x18000fae8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000faed  nop
0x18000faee  mov     [rdi+400h], r15
0x18000faf5  lea     rcx, [rdi+408h]
0x18000fafc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000fb01  nop
0x18000fb02  mov     [rsp+0BD0h+var_B88], r15
0x18000fb07  mov     r14d, r15d
0x18000fb0a  mov     [rsp+0BD0h+var_B74], r15d
0x18000fb0f  test    r13, r13
0x18000fb12  jz      loc_180010197
0x18000fb18  mov     rax, [r13+0]
0x18000fb1c  lea     rdx, [rsp+0BD0h+var_B88]
0x18000fb21  mov     rcx, r13
0x18000fb24  mov     rax, [rax+30h]
0x18000fb28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb2d  mov     rdx, [rsp+0BD0h+var_B88]
0x18000fb32  test    rdx, rdx
0x18000fb35  jz      loc_180010197
0x18000fb3b  add     rdx, 38h ; '8'
0x18000fb3f  mov     rcx, rdi
0x18000fb42  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000fb47  mov     rdx, rdi
0x18000fb4a  lea     rbx, [rdi+200h]
0x18000fb51  mov     rcx, rbx
0x18000fb54  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000fb59  mov     rcx, rbx; lpWideCharStr
0x18000fb5c  call    ?EscapeUrlComponent@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; EscapeUrlComponent(std::wstring *)
0x18000fb61  mov     rax, [rsp+0BD0h+var_B88]
0x18000fb66  movzx   r9d, word ptr [rax+14h]
0x18000fb6b  lea     r8, aU_0; "%u"
0x18000fb72  mov     edx, 400h; BufferCount
0x18000fb77  lea     rcx, [rbp+0AD0h+Buffer]; Buffer
0x18000fb7b  call    cs:__imp_swprintf_s
0x18000fb81  lea     rdx, [rbp+0AD0h+Buffer]
0x18000fb85  lea     rcx, [rdi+20h]
0x18000fb89  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000fb8e  lea     rdx, [rdi+20h]
0x18000fb92  lea     rbx, [rdi+220h]
0x18000fb99  mov     rcx, rbx
0x18000fb9c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000fba1  mov     rcx, rbx; lpWideCharStr
0x18000fba4  call    ?EscapeUrlComponent@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; EscapeUrlComponent(std::wstring *)
0x18000fba9  mov     [rsp+0BD0h+var_B70], r14
0x18000fbae  mov     rax, [r13+0]
0x18000fbb2  lea     rdx, [rsp+0BD0h+var_B70]
0x18000fbb7  mov     rcx, r13
0x18000fbba  mov     rax, [rax+28h]
0x18000fbbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbc3  xor     r13d, r13d
0x18000fbc6  mov     [rbp+0AD0h+Buffer], r13w
0x18000fbcb  mov     rcx, [rsp+0BD0h+var_B70]; struct CLogInfo *
0x18000fbd0  test    rcx, rcx
0x18000fbd3  jz      short loc_18000FBE9
0x18000fbd5  mov     r9d, 400h; unsigned int
0x18000fbdb  lea     r8, [rbp+0AD0h+Buffer]; unsigned __int16 *
0x18000fbdf  mov     rdx, [rsp+0BD0h+var_B88]; struct _EVENTLOGRECORD *
0x18000fbe4  call    ?GetCategoryStr@@YAPEAGPEAVCLogInfo@@PEAU_EVENTLOGRECORD@@PEAGK@Z; GetCategoryStr(CLogInfo *,_EVENTLOGRECORD *,ushort *,ulong)
0x18000fbe9  lea     rdx, [rbp+0AD0h+Buffer]
0x18000fbed  lea     rcx, [rdi+40h]
0x18000fbf1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000fbf6  lea     rdx, [rdi+40h]
0x18000fbfa  lea     rbx, [rdi+240h]
0x18000fc01  mov     rcx, rbx
0x18000fc04  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000fc09  mov     rcx, rbx; lpWideCharStr
0x18000fc0c  call    ?EscapeUrlComponent@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; EscapeUrlComponent(std::wstring *)
0x18000fc11  mov     rax, [rsp+0BD0h+var_B88]
0x18000fc16  movzx   r9d, word ptr [rax+1Ch]
0x18000fc1b  lea     r8, aHu; "%hu"
0x18000fc22  mov     edx, 400h; BufferCount
0x18000fc27  lea     rcx, [rbp+0AD0h+Buffer]; Buffer
0x18000fc2b  call    cs:__imp_swprintf_s
0x18000fc31  lea     rdx, [rbp+0AD0h+Buffer]
0x18000fc35  lea     rcx, [rdi+60h]
0x18000fc39  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000fc3e  lea     rdx, [rdi+60h]
0x18000fc42  lea     rbx, [rdi+260h]
0x18000fc49  mov     rcx, rbx
0x18000fc4c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000fc51  mov     rcx, rbx; lpWideCharStr
0x18000fc54  call    ?EscapeUrlComponent@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; EscapeUrlComponent(std::wstring *)
0x18000fc59  mov     rcx, [rsp+0BD0h+var_B88]
0x18000fc5e  movzx   ecx, word ptr [rcx+18h]; unsigned __int16
0x18000fc62  call    ?GetTypeStr@@YAPEAGG@Z; GetTypeStr(ushort)
0x18000fc67  mov     rdx, rax
0x18000fc6a  lea     rbx, [rdi+80h]
0x18000fc71  mov     rcx, rbx
0x18000fc74  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000fc79  mov     rdx, rbx
0x18000fc7c  lea     rbx, [rdi+280h]
0x18000fc83  mov     rcx, rbx
0x18000fc86  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000fc8b  mov     rcx, rbx; lpWideCharStr
0x18000fc8e  call    ?EscapeUrlComponent@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; EscapeUrlComponent(std::wstring *)
0x18000fc93  mov     rax, [rsp+0BD0h+var_B88]
0x18000fc98  movzx   r9d, word ptr [rax+18h]
0x18000fc9d  lea     r8, aHu; "%hu"
0x18000fca4  mov     edx, 400h; BufferCount
0x18000fca9  lea     rcx, [rbp+0AD0h+Buffer]; Buffer
0x18000fcad  call    cs:__imp_swprintf_s
0x18000fcb3  lea     rdx, [rbp+0AD0h+Buffer]
0x18000fcb7  lea     rbx, [rdi+0A0h]
0x18000fcbe  mov     rcx, rbx
0x18000fcc1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000fcc6  mov     rdx, rbx
0x18000fcc9  lea     rbx, [rdi+2A0h]
0x18000fcd0  mov     rcx, rbx
0x18000fcd3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000fcd8  mov     rcx, rbx; lpWideCharStr
0x18000fcdb  call    ?EscapeUrlComponent@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; EscapeUrlComponent(std::wstring *)
0x18000fce0  mov     r8d, 400h; unsigned int
0x18000fce6  lea     rdx, [rbp+0AD0h+Buffer]; unsigned __int16 *
0x18000fcea  mov     rcx, [rsp+0BD0h+var_B88]
0x18000fcef  mov     ecx, [rcx+0Ch]; unsigned int
0x18000fcf2  call    ?GetDateStr@@YAPEAGKPEAGK@Z; GetDateStr(ulong,ushort *,ulong)
0x18000fcf7  lea     rdx, [rbp+0AD0h+Buffer]
0x18000fcfb  lea     rbx, [rdi+0C0h]
0x18000fd02  mov     rcx, rbx
0x18000fd05  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000fd0a  mov     rdx, rbx
0x18000fd0d  lea     rbx, [rdi+2C0h]
0x18000fd14  mov     rcx, rbx
0x18000fd17  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000fd1c  mov     rcx, rbx; lpWideCharStr
0x18000fd1f  call    ?EscapeUrlComponent@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; EscapeUrlComponent(std::wstring *)
0x18000fd24  mov     r8d, 400h; unsigned int
0x18000fd2a  lea     rdx, [rbp+0AD0h+Buffer]; unsigned __int16 *
0x18000fd2e  mov     rcx, [rsp+0BD0h+var_B88]
0x18000fd33  mov     ecx, [rcx+0Ch]; unsigned int
0x18000fd36  call    ?GetTimeStr@@YAPEAGKPEAGK@Z; GetTimeStr(ulong,ushort *,ulong)
0x18000fd3b  lea     rdx, [rbp+0AD0h+Buffer]
0x18000fd3f  lea     rbx, [rdi+0E0h]
0x18000fd46  mov     rcx, rbx
0x18000fd49  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000fd4e  mov     rdx, rbx
0x18000fd51  lea     rbx, [rdi+2E0h]
0x18000fd58  mov     rcx, rbx
0x18000fd5b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000fd60  mov     rcx, rbx; lpWideCharStr
0x18000fd63  call    ?EscapeUrlComponent@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; EscapeUrlComponent(std::wstring *)
0x18000fd68  mov     r8d, 0Ah; Radix
0x18000fd6e  lea     rdx, [rbp+0AD0h+Buffer]; Buffer
0x18000fd72  mov     rcx, [rsp+0BD0h+var_B88]
0x18000fd77  mov     ecx, [rcx+0Ch]; Value
0x18000fd7a  call    cs:__imp__ultow
0x18000fd80  mov     rdx, rax
0x18000fd83  lea     rbx, [rdi+100h]
0x18000fd8a  mov     rcx, rbx
0x18000fd8d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18000fd92  mov     rdx, rbx
0x18000fd95  lea     rbx, [rdi+300h]
0x18000fd9c  mov     rcx, rbx
0x18000fd9f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000fda4  mov     rcx, rbx; lpWideCharStr
0x18000fda7  call    ?EscapeUrlComponent@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; EscapeUrlComponent(std::wstring *)
0x18000fdac  xor     edx, edx; Val
0x18000fdae  mov     r8d, 0ACh; Size
0x18000fdb4  lea     rcx, [rbp+0AD0h+TimeZoneInformation]; void *
0x18000fdb8  call    memset_0
0x18000fdbd  lea     rcx, [rbp+0AD0h+TimeZoneInformation]; lpTimeZoneInformation
0x18000fdc1  call    cs:__imp_GetTimeZoneInformation
0x18000fdc7  cmp     eax, 1
0x18000fdca  jnz     short loc_18000FDD4
0x18000fdcc  mov     ecx, [rbp+0AD0h+TimeZoneInformation.Bias]
0x18000fdcf  add     ecx, [rbp+0AD0h+TimeZoneInformation.StandardBias]
0x18000fdd2  jmp     short loc_18000FDE4
0x18000fdd4  cmp     eax, 2
0x18000fdd7  jnz     short loc_18000FDE1
0x18000fdd9  mov     ecx, [rbp+0AD0h+TimeZoneInformation.Bias]
0x18000fddc  add     ecx, [rbp+0AD0h+TimeZoneInformation.DaylightBias]
0x18000fddf  jmp     short loc_18000FDE4
0x18000fde1  mov     ecx, r13d; Value
0x18000fde4  mov     r8d, 0Ah; Radix
0x18000fdea  lea     rdx, [rbp+0AD0h+Buffer]; Buffer
0x18000fdee  call    cs:__imp__itow
0x18000fdf4  mov     rdx, rax
  ... truncated ...
```
