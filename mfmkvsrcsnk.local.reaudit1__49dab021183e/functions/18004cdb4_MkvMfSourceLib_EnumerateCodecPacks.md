# MkvMfSourceLib::EnumerateCodecPacks

- ea: `0x18004cdb4`
- end: `0x18004d752`
- name: `MkvMfSourceLib::EnumerateCodecPacks`
- size: `2462`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004ca2c`

## callees

- `0x180002400`
- `0x1800036f9`
- `0x180005c68`
- `0x180008ffc`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x18003dea8`
- `0x18004c0c8`
- `0x18004c358`
- `0x18004c48c`
- `0x18004c6b0`
- `0x18004c6ec`
- `0x18004cdb4`
- `0x18004e5f8`
- `0x18004e648`
- `0x18004e8f8`
- `0x18004e984`
- `0x1800744d8`
- `0x1800789cc`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d369`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004d369`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ce90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cfac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d094`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d199`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d25c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d5cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d693`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004ce90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004cfac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d094`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d199`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d25c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d5cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004d693`
- `CompPkgSup!GetMediaComponentPackageInfo` at `0x18004ce66`
- `CompPkgSup!GetMediaComponentPackageInfo` at `0x18004ce66`

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
        v6 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v14 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v33 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
          v39 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v64 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
              v61 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        if ( *v56 == qword_1800DBF58 || !memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
        {
          if ( (unsigned __int8)byte_1800DC8D3 >= 4u )
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
                v67 = &qword_1800DBF70;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
            byte_1800DC970 = 1;
            CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v74);
            std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v86);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v78);
            result = v1;
          }
          v1 = 1;
          v73 = 1;
        }
        else if ( (unsigned __int8)byte_1800DC8D3 >= 4u )
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
      v24 = &qword_1800DBF70;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x18004cdb4  mov     rax, rsp
0x18004cdb7  push    rbx
0x18004cdb8  push    rsi
0x18004cdb9  push    rdi
0x18004cdba  push    r12
0x18004cdbc  push    r13
0x18004cdbe  push    r14
0x18004cdc0  push    r15
0x18004cdc2  sub     rsp, 660h
0x18004cdc9  movaps  xmmword ptr [rax-48h], xmm6
0x18004cdcd  mov     rax, cs:__security_cookie
0x18004cdd4  xor     rax, rsp
0x18004cdd7  mov     [rsp+698h+var_58], rax
0x18004cddf  xor     r12d, r12d
0x18004cde2  mov     r14d, r12d
0x18004cde5  mov     [rsp+698h+var_650], r12d
0x18004cdea  mov     r15b, r12b
0x18004cded  mov     [rsp+698h+var_668], r12b
0x18004cdf2  mov     [rsp+698h+var_648], r12
0x18004cdf7  mov     [rsp+698h+var_650], r12d
0x18004cdfc  lea     rcx, [rsp+698h+var_5D8]
0x18004ce04  call    ??0?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x18004ce09  nop
0x18004ce0a  lea     edi, [r12+6Ch]
0x18004ce0f  mov     r8d, edi; int
0x18004ce12  lea     r13, aMkvmfsourcelib_57; "MkvMfSourceLib::EnumerateCodecPacks"
0x18004ce19  mov     rdx, r13; char *
0x18004ce1c  lea     rcx, [rsp+698h+var_667]; this
0x18004ce21  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004ce26  nop
0x18004ce27  lea     rcx, [rsp+698h+var_648]
0x18004ce2c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ce31  mov     [rsp+698h+var_600], r12
0x18004ce39  lea     r9d, [r12+12h]; unsigned int
0x18004ce3e  lea     r8d, [r12+13h]; unsigned int
0x18004ce43  lea     rdx, aWindowsMediaco; "windows.mediaCodec"
0x18004ce4a  lea     rcx, [rsp+698h+hstringHeader]; hstringHeader
0x18004ce52  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004ce57  lea     r8, [rsp+698h+var_648]
0x18004ce5c  mov     rdx, [rsp+698h+var_600]
0x18004ce64  xor     ecx, ecx
0x18004ce66  call    cs:__imp_GetMediaComponentPackageInfo
0x18004ce6d  nop     dword ptr [rax+rax+00h]
0x18004ce72  mov     ebx, eax
0x18004ce74  test    eax, eax
0x18004ce76  jns     loc_18004CF80
0x18004ce7c  mov     [rsp+698h+var_600], r12
0x18004ce84  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ce8b  test    rcx, rcx
0x18004ce8e  jnz     short loc_18004CED7
0x18004ce90  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004ce97  nop     dword ptr [rax+rax+00h]
0x18004ce9c  mov     rcx, rax
0x18004ce9f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cea6  test    rax, rax
0x18004cea9  jz      short loc_18004CEC9
0x18004ceab  mov     rax, [rax]
0x18004ceae  mov     edx, 7F0h
0x18004ceb3  mov     rax, [rax+8]
0x18004ceb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cebc  test    eax, eax
0x18004cebe  jz      short loc_18004CEC9
0x18004cec0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cec7  jmp     short loc_18004CED7
0x18004cec9  lea     rcx, qword_1800DBF70; this
0x18004ced0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004ced7  cmp     [rcx+8], r12b
0x18004cedb  jz      short loc_18004CEFB
0x18004cedd  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004cee2  cmp     [rax+7CCh], ebx
0x18004cee8  jz      short loc_18004CEFB
0x18004ceea  mov     r9d, ebx; int
0x18004ceed  mov     r8d, edi; int
0x18004cef0  mov     rdx, r13; char *
0x18004cef3  mov     rcx, rax; this
0x18004cef6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004cefb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004cf02  jb      short loc_18004CF27
0x18004cf04  mov     edx, 0Bh
0x18004cf09  mov     dword ptr [rsp+698h+var_678], ebx
0x18004cf0d  xor     r9d, r9d
0x18004cf10  lea     r8, WPP_b0409c288d1f33103322a90ce1b6017f_Traceguids
0x18004cf17  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cf1e  mov     rcx, [rcx+10h]
0x18004cf22  call    WPP_SF_qD
0x18004cf27  mov     cs:byte_1800DC970, 1
0x18004cf2e  lea     rcx, [rsp+698h+var_667]; this
0x18004cf33  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18004cf38  nop
0x18004cf39  lea     rcx, [rsp+698h+var_5D8]
0x18004cf41  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x18004cf46  nop
0x18004cf47  lea     rcx, [rsp+698h+var_648]
0x18004cf4c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004cf51  mov     al, r15b
0x18004cf54  mov     rcx, [rsp+698h+var_58]
0x18004cf5c  xor     rcx, rsp; StackCookie
0x18004cf5f  call    __security_check_cookie
0x18004cf64  movaps  xmm6, [rsp+698h+var_48]
0x18004cf6c  add     rsp, 660h
0x18004cf73  pop     r15
0x18004cf75  pop     r14
0x18004cf77  pop     r13
0x18004cf79  pop     r12
0x18004cf7b  pop     rdi
0x18004cf7c  pop     rsi
0x18004cf7d  pop     rbx
0x18004cf7e  retn
0x18004cf80  mov     rcx, [rsp+698h+var_648]
0x18004cf85  mov     rax, [rcx]
0x18004cf88  lea     rdx, [rsp+698h+var_650]
0x18004cf8d  mov     rax, [rax+38h]
0x18004cf91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cf96  mov     ebx, eax
0x18004cf98  test    eax, eax
0x18004cf9a  jns     loc_18004D031
0x18004cfa0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cfa7  test    rcx, rcx
0x18004cfaa  jnz     short loc_18004CFF3
0x18004cfac  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004cfb3  nop     dword ptr [rax+rax+00h]
0x18004cfb8  mov     rcx, rax
0x18004cfbb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cfc2  test    rax, rax
0x18004cfc5  jz      short loc_18004CFE5
0x18004cfc7  mov     rax, [rax]
0x18004cfca  mov     edx, 7F0h
0x18004cfcf  mov     rax, [rax+8]
0x18004cfd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cfd8  test    eax, eax
0x18004cfda  jz      short loc_18004CFE5
0x18004cfdc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cfe3  jmp     short loc_18004CFF3
0x18004cfe5  lea     rcx, qword_1800DBF70; this
0x18004cfec  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004cff3  cmp     [rcx+8], r12b
0x18004cff7  jz      short loc_18004D01A
0x18004cff9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004cffe  cmp     [rax+7CCh], ebx
0x18004d004  jz      short loc_18004D01A
0x18004d006  mov     r9d, ebx; int
0x18004d009  mov     r8d, 6Dh ; 'm'; int
0x18004d00f  mov     rdx, r13; char *
0x18004d012  mov     rcx, rax; this
0x18004d015  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d01a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d021  jb      loc_18004CF27
0x18004d027  mov     edx, 0Ch
0x18004d02c  jmp     loc_18004CF09
0x18004d031  mov     esi, r12d
0x18004d034  cmp     esi, [rsp+698h+var_650]
0x18004d038  jnb     loc_18004CF27
0x18004d03e  mov     [rsp+698h+var_658], r12
0x18004d043  mov     [rsp+698h+var_660], r12
0x18004d048  lea     rcx, [rsp+698h+var_558]; this
0x18004d050  call    ??0CodecPackInfo@@QEAA@XZ; CodecPackInfo::CodecPackInfo(void)
0x18004d055  nop
0x18004d056  mov     rdi, [rsp+698h+var_648]
0x18004d05b  mov     rax, [rdi]
0x18004d05e  mov     rbx, [rax+30h]
0x18004d062  lea     rcx, [rsp+698h+var_658]
0x18004d067  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d06c  lea     r8, [rsp+698h+var_658]
0x18004d071  mov     edx, esi
0x18004d073  mov     rcx, rdi
0x18004d076  mov     rax, rbx
0x18004d079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d07e  mov     ebx, eax
0x18004d080  test    eax, eax
0x18004d082  jns     loc_18004D157
0x18004d088  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d08f  test    rcx, rcx
0x18004d092  jnz     short loc_18004D0DB
0x18004d094  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d09b  nop     dword ptr [rax+rax+00h]
0x18004d0a0  mov     rcx, rax
0x18004d0a3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d0aa  test    rax, rax
0x18004d0ad  jz      short loc_18004D0CD
0x18004d0af  mov     rax, [rax]
0x18004d0b2  mov     edx, 7F0h
0x18004d0b7  mov     rax, [rax+8]
0x18004d0bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0c0  test    eax, eax
0x18004d0c2  jz      short loc_18004D0CD
0x18004d0c4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d0cb  jmp     short loc_18004D0DB
0x18004d0cd  lea     rcx, qword_1800DBF70; this
0x18004d0d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d0db  cmp     [rcx+8], r12b
0x18004d0df  jz      short loc_18004D102
0x18004d0e1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d0e6  cmp     [rax+7CCh], ebx
0x18004d0ec  jz      short loc_18004D102
0x18004d0ee  mov     r9d, ebx; int
0x18004d0f1  mov     r8d, 76h ; 'v'; int
0x18004d0f7  mov     rdx, r13; char *
0x18004d0fa  mov     rcx, rax; this
0x18004d0fd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d102  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d109  jb      short loc_18004D12F
0x18004d10b  mov     edx, 0Dh
0x18004d110  mov     dword ptr [rsp+698h+var_678], ebx
0x18004d114  xor     r9d, r9d
0x18004d117  lea     r8, WPP_b0409c288d1f33103322a90ce1b6017f_Traceguids
0x18004d11e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d125  mov     rcx, [rcx+10h]
0x18004d129  call    WPP_SF_qD
0x18004d12e  nop
0x18004d12f  lea     rcx, [rsp+698h+var_558]; this
0x18004d137  call    ??1CodecPackInfo@@QEAA@XZ; CodecPackInfo::~CodecPackInfo(void)
0x18004d13c  nop
0x18004d13d  lea     rcx, [rsp+698h+var_660]
0x18004d142  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d147  nop
0x18004d148  lea     rcx, [rsp+698h+var_658]
0x18004d14d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d152  jmp     loc_18004CF27
0x18004d157  mov     rdi, [rsp+698h+var_658]
0x18004d15c  mov     rax, [rdi]
0x18004d15f  mov     rbx, [rax]
0x18004d162  lea     rcx, [rsp+698h+var_660]
0x18004d167  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004d16c  lea     r8, [rsp+698h+var_660]
0x18004d171  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18004d178  mov     rcx, rdi
0x18004d17b  mov     rax, rbx
0x18004d17e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d183  mov     ebx, eax
0x18004d185  test    eax, eax
0x18004d187  jns     loc_18004D21E
0x18004d18d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d194  test    rcx, rcx
0x18004d197  jnz     short loc_18004D1E0
0x18004d199  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d1a0  nop     dword ptr [rax+rax+00h]
0x18004d1a5  mov     rcx, rax
0x18004d1a8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d1af  test    rax, rax
0x18004d1b2  jz      short loc_18004D1D2
0x18004d1b4  mov     rax, [rax]
0x18004d1b7  mov     edx, 7F0h
0x18004d1bc  mov     rax, [rax+8]
0x18004d1c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d1c5  test    eax, eax
0x18004d1c7  jz      short loc_18004D1D2
0x18004d1c9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d1d0  jmp     short loc_18004D1E0
0x18004d1d2  lea     rcx, qword_1800DBF70; this
0x18004d1d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d1e0  cmp     [rcx+8], r12b
0x18004d1e4  jz      short loc_18004D207
0x18004d1e6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d1eb  cmp     [rax+7CCh], ebx
0x18004d1f1  jz      short loc_18004D207
0x18004d1f3  mov     r9d, ebx; int
0x18004d1f6  mov     r8d, 77h ; 'w'; int
0x18004d1fc  mov     rdx, r13; char *
0x18004d1ff  mov     rcx, rax; this
0x18004d202  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004d207  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d20e  jb      loc_18004D12F
0x18004d214  mov     edx, 0Eh
0x18004d219  jmp     loc_18004D110
0x18004d21e  mov     [rsp+698h+var_670], r12
0x18004d223  lea     rax, [rsp+698h+var_558]
0x18004d22b  mov     [rsp+698h+var_678], rax
0x18004d230  mov     r9, [rsp+698h+var_660]
0x18004d235  xor     r8d, r8d
0x18004d238  xor     edx, edx
0x18004d23a  lea     rcx, _GUID_00000000_0000_0000_0000_000000000000
0x18004d241  call    ?CreateCodecInfoFromMediaExtensionMap@@YAJAEBU_GUID@@PEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@1PEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@AEAUCodecPackInfo@@PEA_N@Z; CreateCodecInfoFromMediaExtensionMap(_GUID const &,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,CodecPackInfo &,bool *)
0x18004d246  mov     ebx, eax
0x18004d248  test    eax, eax
0x18004d24a  jns     loc_18004D2E1
0x18004d250  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d257  test    rcx, rcx
0x18004d25a  jnz     short loc_18004D2A3
0x18004d25c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004d263  nop     dword ptr [rax+rax+00h]
0x18004d268  mov     rcx, rax
0x18004d26b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d272  test    rax, rax
0x18004d275  jz      short loc_18004D295
0x18004d277  mov     rax, [rax]
0x18004d27a  mov     edx, 7F0h
0x18004d27f  mov     rax, [rax+8]
0x18004d283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d288  test    eax, eax
0x18004d28a  jz      short loc_18004D295
0x18004d28c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d293  jmp     short loc_18004D2A3
0x18004d295  lea     rcx, qword_1800DBF70; this
0x18004d29c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004d2a3  cmp     [rcx+8], r12b
0x18004d2a7  jz      short loc_18004D2CA
0x18004d2a9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004d2ae  cmp     [rax+7CCh], ebx
0x18004d2b4  jz      short loc_18004D2CA
0x18004d2b6  mov     r9d, ebx; int
  ... truncated ...
```
