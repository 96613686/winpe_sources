# MkvMfSourceLib::EnumerateCodecPacks

- ea: `0x18004ae44`
- end: `0x18004b7ab`
- name: `MkvMfSourceLib::EnumerateCodecPacks`
- size: `2407`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004aacc`

## callees

- `0x1800023e0`
- `0x1800036b9`
- `0x180005ab8`
- `0x180008ccc`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x18003c478`
- `0x18004a140`
- `0x18004a42c`
- `0x18004a554`
- `0x18004a778`
- `0x18004a7b4`
- `0x18004ae44`
- `0x18004c654`
- `0x18004c6a4`
- `0x18004c948`
- `0x18004c9cc`
- `0x180071330`
- `0x18007559c`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004b3d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004b3d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004af1a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b02f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b111`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b210`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b2cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b634`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b6f2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004af1a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b02f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b111`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b210`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b2cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b634`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004b6f2`
- `CompPkgSup!GetMediaComponentPackageInfo` at `0x18004aef6`
- `CompPkgSup!GetMediaComponentPackageInfo` at `0x18004aef6`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
char MkvMfSourceLib::EnumerateCodecPacks()
{
  int v0; // r14d
  char v1; // r15
  __int64 v2; // rdx
  int MediaComponentPackageInfo; // ebx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v9; // rdx
  char result; // al
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  unsigned int i; // esi
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD, _QWORD); // rbx
  __int64 v20; // rdx
  int CodecInfoFromMediaExtensionMap; // ebx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 *v24; // rcx
  CallStackTracing *v25; // rax
  struct CallStackContext *v26; // rax
  __int64 v27; // rdx
  __int64 (__fastcall ***v28)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v29)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 *v33; // rcx
  CallStackTracing *v34; // rax
  struct CallStackContext *v35; // rax
  _BYTE *k; // rdx
  unsigned __int64 v37; // r8
  __int16 *v38; // r9
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  unsigned int v42; // edi
  unsigned int j; // ebx
  unsigned int v44; // ecx
  HSTRING v45; // rcx
  PCWSTR StringRawBuffer; // rax
  __int64 v47; // rcx
  WCHAR *m; // r9
  _BYTE *n; // rdx
  __int64 v50; // rcx
  unsigned __int64 v51; // r8
  __int16 *v52; // r9
  __int128 v53; // xmm0
  __int64 v54; // rax
  __int64 v55; // rcx
  _QWORD *v56; // rcx
  __int128 v57; // xmm6
  __int64 v58; // rax
  __int64 v59; // r8
  __int64 v60; // r9
  __int64 *v61; // rcx
  CallStackTracing *v62; // rax
  struct CallStackContext *v63; // rax
  __int64 *v64; // rcx
  CallStackTracing *v65; // rax
  struct CallStackContext *v66; // rax
  __int64 *v67; // rcx
  CallStackTracing *v68; // rax
  struct CallStackContext *v69; // rax
  __int64 v70; // [rsp+0h] [rbp-698h] BYREF
  __int64 v71; // [rsp+20h] [rbp-678h]
  __int64 v72; // [rsp+28h] [rbp-670h]
  char v73; // [rsp+30h] [rbp-668h]
  _BYTE v74[7]; // [rsp+31h] [rbp-667h] BYREF
  __int64 v75; // [rsp+38h] [rbp-660h] BYREF
  __int64 (__fastcall ***v76)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-658h] BYREF
  unsigned int v77; // [rsp+48h] [rbp-650h] BYREF
  __int64 v78; // [rsp+50h] [rbp-648h] BYREF
  _BYTE v79[8]; // [rsp+58h] [rbp-640h] BYREF
  _BYTE v80[16]; // [rsp+60h] [rbp-638h] BYREF
  _BYTE v81[16]; // [rsp+70h] [rbp-628h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-618h] BYREF
  __int64 v83; // [rsp+98h] [rbp-600h]
  __int64 v84[2]; // [rsp+A0h] [rbp-5F8h] BYREF
  __int128 Buf1; // [rsp+B0h] [rbp-5E8h] BYREF
  _BYTE v86[128]; // [rsp+C0h] [rbp-5D8h] BYREF
  _BYTE v87[72]; // [rsp+140h] [rbp-558h] BYREF
  _BYTE v88[16]; // [rsp+188h] [rbp-510h] BYREF
  __int128 v89; // [rsp+198h] [rbp-500h]
  unsigned int v90; // [rsp+2F8h] [rbp-3A0h]
  _BYTE v91[16]; // [rsp+498h] [rbp-200h] BYREF
  HSTRING string; // [rsp+4A8h] [rbp-1F0h]
  unsigned int v93; // [rsp+560h] [rbp-138h]

  v0 = 0;
  v1 = 0;
  v73 = 0;
  v78 = 0;
  v77 = 0;
  std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v86);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v74, "MkvMfSourceLib::EnumerateCodecPacks", 108);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78);
  v83 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"windows.mediaCodec", 0x13u, 0x12u);
  MediaComponentPackageInfo = GetMediaComponentPackageInfo(0, v83, &v78);
  if ( MediaComponentPackageInfo < 0 )
  {
    v83 = 0;
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2, v4, v5);
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != MediaComponentPackageInfo )
        CallStackContext::TraceFailure(
          ThreadRelativeContext,
          "MkvMfSourceLib::EnumerateCodecPacks",
          108,
          MediaComponentPackageInfo);
    }
    if ( !g_wppLevels )
      goto LABEL_13;
    v9 = 11;
    goto LABEL_12;
  }
  MediaComponentPackageInfo = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v78 + 56LL))(v78, &v77);
  if ( MediaComponentPackageInfo < 0 )
  {
    v14 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11, v12, v13);
      CallStackTracing::s_wpInstance = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v14 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v14 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
      if ( *((_DWORD *)v16 + 499) != MediaComponentPackageInfo )
        CallStackContext::TraceFailure(v16, "MkvMfSourceLib::EnumerateCodecPacks", 109, MediaComponentPackageInfo);
    }
    if ( !g_wppLevels )
      goto LABEL_13;
    v9 = 12;
LABEL_12:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      &WPP_b0409c288d1f33103322a90ce1b6017f_Traceguids,
      0,
      MediaComponentPackageInfo);
    goto LABEL_13;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v77 )
      goto LABEL_13;
    v76 = 0;
    v75 = 0;
    CodecPackInfo::CodecPackInfo((CodecPackInfo *)v87);
    v18 = v78;
    v19 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v78 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76);
    CodecInfoFromMediaExtensionMap = v19(v18, i, &v76);
    if ( CodecInfoFromMediaExtensionMap < 0 )
      break;
    v28 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v76;
    v29 = **v76;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
    CodecInfoFromMediaExtensionMap = v29(v28, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v75);
    if ( CodecInfoFromMediaExtensionMap < 0 )
    {
      v33 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
        CallStackTracing::s_wpInstance = v34;
        if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
        {
          v33 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v33 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v33 + 8) )
      {
        v35 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
        if ( *((_DWORD *)v35 + 499) != CodecInfoFromMediaExtensionMap )
          CallStackContext::TraceFailure(
            v35,
            "MkvMfSourceLib::EnumerateCodecPacks",
            119,
            CodecInfoFromMediaExtensionMap);
      }
      if ( !g_wppLevels )
        goto LABEL_40;
      v27 = 14;
      goto LABEL_38;
    }
    v72 = 0;
    CodecInfoFromMediaExtensionMap = CreateCodecInfoFromMediaExtensionMap(
                                       (__int64)&GUID_00000000_0000_0000_0000_000000000000,
                                       0,
                                       0,
                                       v75,
                                       (__int64)v87);
    if ( CodecInfoFromMediaExtensionMap < 0 )
    {
      v39 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, k, v37, v38);
        CallStackTracing::s_wpInstance = v40;
        if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
        {
          v39 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v39 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
        }
      }
      if ( *((_BYTE *)v39 + 8) )
      {
        v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
        if ( *((_DWORD *)v41 + 499) != CodecInfoFromMediaExtensionMap )
          CallStackContext::TraceFailure(
            v41,
            "MkvMfSourceLib::EnumerateCodecPacks",
            121,
            CodecInfoFromMediaExtensionMap);
      }
      if ( !g_wppLevels )
        goto LABEL_40;
      v27 = 15;
      goto LABEL_38;
    }
    v42 = v90;
    for ( j = 0; j < v42; ++j )
    {
      if ( j >= v93 )
        goto LABEL_110;
      for ( k = v91; ; k = (_BYTE *)*((_QWORD *)k + 24) )
      {
        if ( !k )
          goto LABEL_73;
        v44 = *((_DWORD *)k + 2);
        if ( j >= v44 && j < v44 + 20 )
          break;
      }
      v37 = j - v44;
      v38 = &_ImageBase;
      if ( (*((_BYTE *)&CTSparseBlock<unsigned long,_tagpropertykey,20,0>::s_bSingleBitMasks + (v37 & 7))
          & k[(v37 >> 3) + 24]) != 0 )
      {
        v45 = *(HSTRING *)&k[8 * v37 + 32];
      }
      else
      {
LABEL_73:
        if ( (v91[12] & 1) == 0 )
        {
LABEL_110:
          v64 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v65 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, k, v37, v38);
            CallStackTracing::s_wpInstance = v65;
            if ( v65 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v65 + 8LL))(v65, 2032) )
            {
              v64 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v64 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v64 + 8) )
          {
            v66 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v64);
            if ( *((_DWORD *)v66 + 499) != -1072875845 )
              CallStackContext::TraceFailure(v66, "MkvMfSourceLib::EnumerateCodecPacks", 126, -1072875845);
          }
          if ( !g_wppLevels )
          {
LABEL_40:
            CodecPackInfo::~CodecPackInfo((CodecPackInfo *)v87);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76);
            goto LABEL_13;
          }
          v27 = 16;
          LODWORD(v71) = -1072875845;
LABEL_39:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, &WPP_b0409c288d1f33103322a90ce1b6017f_Traceguids, 0, v71);
          goto LABEL_40;
        }
        v45 = string;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(v45, 0);
      v47 = -1;
      do
        ++v47;
      while ( StringRawBuffer[v47] );
      if ( v47 )
      {
        for ( m = (WCHAR *)StringRawBuffer; *m; ++m )
          ;
        std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
          v86,
          &hstringHeader,
          StringRawBuffer,
          m);
        *(_OWORD *)v84 = 0;
        if ( j >= v90 )
        {
LABEL_99:
          v61 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v62 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, n, v51, v52);
            CallStackTracing::s_wpInstance = v62;
            if ( v62 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v62 + 8LL))(v62, 2032) )
            {
              v61 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v61 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
            }
          }
          if ( *((_BYTE *)v61 + 8) )
          {
            v63 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v61);
            if ( *((_DWORD *)v63 + 499) != -1072875845 )
              CallStackContext::TraceFailure(v63, "MkvMfSourceLib::EnumerateCodecPacks", 136, -1072875845);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              &WPP_b0409c288d1f33103322a90ce1b6017f_Traceguids,
              0,
              -1072875845);
          std::string::~string(&hstringHeader);
          goto LABEL_40;
        }
        for ( n = v88; ; n = (_BYTE *)*((_QWORD *)n + 45) )
        {
          if ( !n )
            goto LABEL_88;
          v50 = *((unsigned int *)n + 2);
          if ( j >= (unsigned int)v50 && j < (int)v50 + 20 )
            break;
        }
        v51 = j - (unsigned int)v50;
        v50 = ((_BYTE)j - (_BYTE)v50) & 7;
        v52 = &_ImageBase;
        if ( (n[(v51 >> 3) + 32]
            & *((_BYTE *)&CTSparseBlock<unsigned long,_tagpropertykey,20,0>::s_bSingleBitMasks + v50)) != 0 )
        {
          v53 = *(_OWORD *)&n[16 * v51 + 36];
        }
        else
        {
LABEL_88:
          if ( (v88[12] & 1) == 0 )
            goto LABEL_99;
          v53 = v89;
        }
        *(_OWORD *)v84 = v53;
        v54 = std::map<std::string,MkvMfSourceLib::MkvCodec>::_Try_emplace<std::string const &,>(
                v50,
                v80,
                &hstringHeader);
        v55 = *(_QWORD *)v54;
        Buf1 = *(_OWORD *)(*(_QWORD *)v54 + 68LL);
        v56 = (_QWORD *)std::_Tree<std::_Tmap_traits<std::string,MkvMfSourceLib::MkvCodec,std::less<std::string>,std::allocator<std::pair<std::string const,MkvMfSourceLib::MkvCodec>>,0>>::find(
                          v55,
                          v79,
                          &hstringHeader);
        if ( *v56 == qword_1800D6F58 || !memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
        {
          if ( (unsigned __int8)byte_1800D78D3 >= 4u )
            WPP_SF_s_guid_(*((_QWORD *)WPP_GLOBAL_Control + 17), (__int64)v84);
          try
          {
            v57 = *(_OWORD *)v84;
            v58 = *(_QWORD *)std::map<std::string,MkvMfSourceLib::MkvCodec>::_Try_emplace<std::string const &,>(
                               v56,
                               v81,
                               &hstringHeader);
            *(_DWORD *)(v58 + 64) = 1;
            *(_OWORD *)(v58 + 68) = v57;
          }
          catch ( ... )
          {
            v67 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v68 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, &v70, v59, v60);
              CallStackTracing::s_wpInstance = v68;
              if ( v68
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
              {
                v67 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v67 = &qword_1800D6F70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
              }
            }
            if ( *((_BYTE *)v67 + 8) )
            {
              v69 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v67);
              if ( *((_DWORD *)v69 + 499) != -2147024882 )
                CallStackContext::TraceFailure(v69, "MkvMfSourceLib::EnumerateCodecPacks", 152, -2147024882);
            }
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                20,
                &WPP_b0409c288d1f33103322a90ce1b6017f_Traceguids,
                0,
                -2147024882);
            std::string::~string(&hstringHeader);
            CodecPackInfo::~CodecPackInfo((CodecPackInfo *)v87);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76);
            v1 = v73;
LABEL_13:
            byte_1800D7970 = 1;
            CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v74);
            std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v86);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78);
            result = v1;
          }
          v1 = 1;
          v73 = 1;
        }
        else if ( (unsigned __int8)byte_1800D78D3 >= 4u )
        {
          WPP_SF_s_guid__guid_(*((_QWORD *)WPP_GLOBAL_Control + 17), (__int64)v84, (__int64)&Buf1);
        }
        v0 |= 1u;
        std::string::~string(&hstringHeader);
      }
    }
    CodecPackInfo::~CodecPackInfo((CodecPackInfo *)v87);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v75);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v76);
  }
  v24 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v22, v23);
    CallStackTracing::s_wpInstance = v25;
    if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
    {
      v24 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v24 = &qword_1800D6F70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
    }
  }
  if ( *((_BYTE *)v24 + 8) )
  {
    v26 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
    if ( *((_DWORD *)v26 + 499) != CodecInfoFromMediaExtensionMap )
      CallStackContext::TraceFailure(v26, "MkvMfSourceLib::EnumerateCodecPacks", 118, CodecInfoFromMediaExtensionMap);
  }
  if ( !g_wppLevels )
    goto LABEL_40;
  v27 = 13;
LABEL_38:
  LODWORD(v71) = CodecInfoFromMediaExtensionMap;
  goto LABEL_39;
}

```

## disassembly

```asm
0x18004ae44  mov     rax, rsp
0x18004ae47  push    rbx
0x18004ae48  push    rsi
0x18004ae49  push    rdi
0x18004ae4a  push    r12
0x18004ae4c  push    r13
0x18004ae4e  push    r14
0x18004ae50  push    r15
0x18004ae52  sub     rsp, 660h
0x18004ae59  movaps  xmmword ptr [rax-48h], xmm6
0x18004ae5d  mov     rax, cs:__security_cookie
0x18004ae64  xor     rax, rsp
0x18004ae67  mov     [rsp+698h+var_58], rax
0x18004ae6f  xor     r12d, r12d
0x18004ae72  mov     r14d, r12d
0x18004ae75  mov     [rsp+698h+var_650], r12d
0x18004ae7a  mov     r15b, r12b
0x18004ae7d  mov     [rsp+698h+var_668], r12b
0x18004ae82  mov     [rsp+698h+var_648], r12
0x18004ae87  mov     [rsp+698h+var_650], r12d
0x18004ae8c  lea     rcx, [rsp+698h+var_5D8]
0x18004ae94  call    ??0?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x18004ae99  nop
0x18004ae9a  lea     edi, [r12+6Ch]
0x18004ae9f  mov     r8d, edi; int
0x18004aea2  lea     r13, aMkvmfsourcelib_57; "MkvMfSourceLib::EnumerateCodecPacks"
0x18004aea9  mov     rdx, r13; char *
0x18004aeac  lea     rcx, [rsp+698h+var_667]; this
0x18004aeb1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004aeb6  nop
0x18004aeb7  lea     rcx, [rsp+698h+var_648]
0x18004aebc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004aec1  mov     [rsp+698h+var_600], r12
0x18004aec9  lea     r9d, [r12+12h]; unsigned int
0x18004aece  lea     r8d, [r12+13h]; unsigned int
0x18004aed3  lea     rdx, aWindowsMediaco; "windows.mediaCodec"
0x18004aeda  lea     rcx, [rsp+698h+hstringHeader]; hstringHeader
0x18004aee2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004aee7  lea     r8, [rsp+698h+var_648]
0x18004aeec  mov     rdx, [rsp+698h+var_600]
0x18004aef4  xor     ecx, ecx
0x18004aef6  call    cs:__imp_GetMediaComponentPackageInfo
0x18004aefc  mov     ebx, eax
0x18004aefe  test    eax, eax
0x18004af00  jns     loc_18004B003
0x18004af06  mov     [rsp+698h+var_600], r12
0x18004af0e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004af15  test    rcx, rcx
0x18004af18  jnz     short loc_18004AF5B
0x18004af1a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004af20  mov     rcx, rax
0x18004af23  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004af2a  test    rax, rax
0x18004af2d  jz      short loc_18004AF4D
0x18004af2f  mov     rax, [rax]
0x18004af32  mov     edx, 7F0h
0x18004af37  mov     rax, [rax+8]
0x18004af3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af40  test    eax, eax
0x18004af42  jz      short loc_18004AF4D
0x18004af44  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004af4b  jmp     short loc_18004AF5B
0x18004af4d  lea     rcx, qword_1800D6F70; this
0x18004af54  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004af5b  cmp     [rcx+8], r12b
0x18004af5f  jz      short loc_18004AF7F
0x18004af61  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004af66  cmp     [rax+7CCh], ebx
0x18004af6c  jz      short loc_18004AF7F
0x18004af6e  mov     r9d, ebx; int
0x18004af71  mov     r8d, edi; int
0x18004af74  mov     rdx, r13; char *
0x18004af77  mov     rcx, rax; this
0x18004af7a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004af7f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004af86  jb      short loc_18004AFAB
0x18004af88  mov     edx, 0Bh
0x18004af8d  mov     dword ptr [rsp+698h+var_678], ebx
0x18004af91  xor     r9d, r9d
0x18004af94  lea     r8, WPP_b0409c288d1f33103322a90ce1b6017f_Traceguids
0x18004af9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004afa2  mov     rcx, [rcx+10h]
0x18004afa6  call    WPP_SF_qD
0x18004afab  mov     cs:byte_1800D7970, 1
0x18004afb2  lea     rcx, [rsp+698h+var_667]; this
0x18004afb7  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004afbc  nop
0x18004afbd  lea     rcx, [rsp+698h+var_5D8]
0x18004afc5  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x18004afca  nop
0x18004afcb  lea     rcx, [rsp+698h+var_648]
0x18004afd0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004afd5  mov     al, r15b
0x18004afd8  mov     rcx, [rsp+698h+var_58]
0x18004afe0  xor     rcx, rsp; StackCookie
0x18004afe3  call    __security_check_cookie
0x18004afe8  movaps  xmm6, [rsp+698h+var_48]
0x18004aff0  add     rsp, 660h
0x18004aff7  pop     r15
0x18004aff9  pop     r14
0x18004affb  pop     r13
0x18004affd  pop     r12
0x18004afff  pop     rdi
0x18004b000  pop     rsi
0x18004b001  pop     rbx
0x18004b002  retn
0x18004b003  mov     rcx, [rsp+698h+var_648]
0x18004b008  mov     rax, [rcx]
0x18004b00b  lea     rdx, [rsp+698h+var_650]
0x18004b010  mov     rax, [rax+38h]
0x18004b014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b019  mov     ebx, eax
0x18004b01b  test    eax, eax
0x18004b01d  jns     loc_18004B0AE
0x18004b023  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b02a  test    rcx, rcx
0x18004b02d  jnz     short loc_18004B070
0x18004b02f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004b035  mov     rcx, rax
0x18004b038  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b03f  test    rax, rax
0x18004b042  jz      short loc_18004B062
0x18004b044  mov     rax, [rax]
0x18004b047  mov     edx, 7F0h
0x18004b04c  mov     rax, [rax+8]
0x18004b050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b055  test    eax, eax
0x18004b057  jz      short loc_18004B062
0x18004b059  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b060  jmp     short loc_18004B070
0x18004b062  lea     rcx, qword_1800D6F70; this
0x18004b069  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b070  cmp     [rcx+8], r12b
0x18004b074  jz      short loc_18004B097
0x18004b076  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b07b  cmp     [rax+7CCh], ebx
0x18004b081  jz      short loc_18004B097
0x18004b083  mov     r9d, ebx; int
0x18004b086  mov     r8d, 6Dh ; 'm'; int
0x18004b08c  mov     rdx, r13; char *
0x18004b08f  mov     rcx, rax; this
0x18004b092  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b097  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b09e  jb      loc_18004AFAB
0x18004b0a4  mov     edx, 0Ch
0x18004b0a9  jmp     loc_18004AF8D
0x18004b0ae  mov     esi, r12d
0x18004b0b1  cmp     esi, [rsp+698h+var_650]
0x18004b0b5  jnb     loc_18004AFAB
0x18004b0bb  mov     [rsp+698h+var_658], r12
0x18004b0c0  mov     [rsp+698h+var_660], r12
0x18004b0c5  lea     rcx, [rsp+698h+var_558]; this
0x18004b0cd  call    ??0CodecPackInfo@@QEAA@XZ; CodecPackInfo::CodecPackInfo(void)
0x18004b0d2  nop
0x18004b0d3  mov     rdi, [rsp+698h+var_648]
0x18004b0d8  mov     rax, [rdi]
0x18004b0db  mov     rbx, [rax+30h]
0x18004b0df  lea     rcx, [rsp+698h+var_658]
0x18004b0e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b0e9  lea     r8, [rsp+698h+var_658]
0x18004b0ee  mov     edx, esi
0x18004b0f0  mov     rcx, rdi
0x18004b0f3  mov     rax, rbx
0x18004b0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b0fb  mov     ebx, eax
0x18004b0fd  test    eax, eax
0x18004b0ff  jns     loc_18004B1CE
0x18004b105  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b10c  test    rcx, rcx
0x18004b10f  jnz     short loc_18004B152
0x18004b111  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004b117  mov     rcx, rax
0x18004b11a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b121  test    rax, rax
0x18004b124  jz      short loc_18004B144
0x18004b126  mov     rax, [rax]
0x18004b129  mov     edx, 7F0h
0x18004b12e  mov     rax, [rax+8]
0x18004b132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b137  test    eax, eax
0x18004b139  jz      short loc_18004B144
0x18004b13b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b142  jmp     short loc_18004B152
0x18004b144  lea     rcx, qword_1800D6F70; this
0x18004b14b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b152  cmp     [rcx+8], r12b
0x18004b156  jz      short loc_18004B179
0x18004b158  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b15d  cmp     [rax+7CCh], ebx
0x18004b163  jz      short loc_18004B179
0x18004b165  mov     r9d, ebx; int
0x18004b168  mov     r8d, 76h ; 'v'; int
0x18004b16e  mov     rdx, r13; char *
0x18004b171  mov     rcx, rax; this
0x18004b174  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b179  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b180  jb      short loc_18004B1A6
0x18004b182  mov     edx, 0Dh
0x18004b187  mov     dword ptr [rsp+698h+var_678], ebx
0x18004b18b  xor     r9d, r9d
0x18004b18e  lea     r8, WPP_b0409c288d1f33103322a90ce1b6017f_Traceguids
0x18004b195  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b19c  mov     rcx, [rcx+10h]
0x18004b1a0  call    WPP_SF_qD
0x18004b1a5  nop
0x18004b1a6  lea     rcx, [rsp+698h+var_558]; this
0x18004b1ae  call    ??1CodecPackInfo@@QEAA@XZ; CodecPackInfo::~CodecPackInfo(void)
0x18004b1b3  nop
0x18004b1b4  lea     rcx, [rsp+698h+var_660]
0x18004b1b9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b1be  nop
0x18004b1bf  lea     rcx, [rsp+698h+var_658]
0x18004b1c4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b1c9  jmp     loc_18004AFAB
0x18004b1ce  mov     rdi, [rsp+698h+var_658]
0x18004b1d3  mov     rax, [rdi]
0x18004b1d6  mov     rbx, [rax]
0x18004b1d9  lea     rcx, [rsp+698h+var_660]
0x18004b1de  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004b1e3  lea     r8, [rsp+698h+var_660]
0x18004b1e8  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18004b1ef  mov     rcx, rdi
0x18004b1f2  mov     rax, rbx
0x18004b1f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b1fa  mov     ebx, eax
0x18004b1fc  test    eax, eax
0x18004b1fe  jns     loc_18004B28F
0x18004b204  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b20b  test    rcx, rcx
0x18004b20e  jnz     short loc_18004B251
0x18004b210  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004b216  mov     rcx, rax
0x18004b219  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b220  test    rax, rax
0x18004b223  jz      short loc_18004B243
0x18004b225  mov     rax, [rax]
0x18004b228  mov     edx, 7F0h
0x18004b22d  mov     rax, [rax+8]
0x18004b231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b236  test    eax, eax
0x18004b238  jz      short loc_18004B243
0x18004b23a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b241  jmp     short loc_18004B251
0x18004b243  lea     rcx, qword_1800D6F70; this
0x18004b24a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b251  cmp     [rcx+8], r12b
0x18004b255  jz      short loc_18004B278
0x18004b257  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b25c  cmp     [rax+7CCh], ebx
0x18004b262  jz      short loc_18004B278
0x18004b264  mov     r9d, ebx; int
0x18004b267  mov     r8d, 77h ; 'w'; int
0x18004b26d  mov     rdx, r13; char *
0x18004b270  mov     rcx, rax; this
0x18004b273  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b278  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b27f  jb      loc_18004B1A6
0x18004b285  mov     edx, 0Eh
0x18004b28a  jmp     loc_18004B187
0x18004b28f  mov     [rsp+698h+var_670], r12
0x18004b294  lea     rax, [rsp+698h+var_558]
0x18004b29c  mov     [rsp+698h+var_678], rax
0x18004b2a1  mov     r9, [rsp+698h+var_660]
0x18004b2a6  xor     r8d, r8d
0x18004b2a9  xor     edx, edx
0x18004b2ab  lea     rcx, _GUID_00000000_0000_0000_0000_000000000000
0x18004b2b2  call    ?CreateCodecInfoFromMediaExtensionMap@@YAJAEBU_GUID@@PEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@1PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@AEAUCodecPackInfo@@PEA_N@Z; CreateCodecInfoFromMediaExtensionMap(_GUID const &,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,CodecPackInfo &,bool *)
0x18004b2b7  mov     ebx, eax
0x18004b2b9  test    eax, eax
0x18004b2bb  jns     loc_18004B34C
0x18004b2c1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b2c8  test    rcx, rcx
0x18004b2cb  jnz     short loc_18004B30E
0x18004b2cd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004b2d3  mov     rcx, rax
0x18004b2d6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b2dd  test    rax, rax
0x18004b2e0  jz      short loc_18004B300
0x18004b2e2  mov     rax, [rax]
0x18004b2e5  mov     edx, 7F0h
0x18004b2ea  mov     rax, [rax+8]
0x18004b2ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b2f3  test    eax, eax
0x18004b2f5  jz      short loc_18004B300
0x18004b2f7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b2fe  jmp     short loc_18004B30E
0x18004b300  lea     rcx, qword_1800D6F70; this
0x18004b307  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004b30e  cmp     [rcx+8], r12b
0x18004b312  jz      short loc_18004B335
0x18004b314  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004b319  cmp     [rax+7CCh], ebx
0x18004b31f  jz      short loc_18004B335
0x18004b321  mov     r9d, ebx; int
0x18004b324  mov     r8d, 79h ; 'y'; int
0x18004b32a  mov     rdx, r13; char *
0x18004b32d  mov     rcx, rax; this
0x18004b330  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004b335  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b33c  jb      loc_18004B1A6
  ... truncated ...
```
