# ProcessUpdateType(_XML_TOKENIZATION_STATE *,ParsingSession *,PACKAGE_TYPE *,UPDATE_TYPE *)

- ea: `0x18008b2f4`
- end: `0x18008c74d`
- name: `?ProcessUpdateType@@YAJPEAU_XML_TOKENIZATION_STATE@@PEAUParsingSession@@PEAUPACKAGE_TYPE@@PEAUUPDATE_TYPE@@@Z`
- size: `5209`
- prototype: `__int64 __fastcall(struct _XML_TOKENIZATION_STATE *, struct ParsingSession *, struct PACKAGE_TYPE *, struct UPDATE_TYPE *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180088054`

## callees

- `0x180028830`
- `0x1800348cc`
- `0x180075640`
- `0x18007c1e0`
- `0x18007c660`
- `0x18007d1e0`
- `0x18007f590`
- `0x18007fc50`
- `0x180080df0`
- `0x180081630`
- `0x180087e24`
- `0x180088274`
- `0x1800886dc`
- `0x180088ca8`
- `0x1800898b8`
- `0x18008a278`
- `0x18008abb8`
- `0x18008b2f4`
- `0x18008c754`
- `0x18008cbb0`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x18010c010`
- `0x18020b0a4`

## string_xrefs

- `0x18008b448`: `No update result specified`
- `0x18008b786`: `Failed to expect token`
- `0x18008bc26`: `Failed to process update group`
- `0x18008c6d8`: `Failed to peek next token.`
- `0x18008b3b2`: `onecore\base\cbs\parser\update.cpp`
- `0x18008b6b9`: `onecore\base\cbs\parser\update.cpp`
- `0x18008bb69`: `onecore\base\cbs\parser\update.cpp`
- `0x18008c71b`: `onecore\base\cbs\parser\update.cpp`
- `0x18008c2d5`: `cannot have more than one package in one update`
- `0x18008c371`: `Failed to process DriverUpdateType`
- `0x18008c51e`: `Failed to process ComponentUpdateType`
- `0x18008c27b`: `allocating UPDATE_TYPE`
- `0x18008c3c9`: `allocating UPDATE_TYPE`
- `0x18008c576`: `allocating UPDATE_TYPE`
- `0x18008c0d4`: `Failed to process CapabilityUpdateType`
- `0x18008c12c`: `allocating allocating UPDATE_TYPE`
- `0x18008c187`: `cannot have more than one capability in one update`
- `0x18008c223`: `Failed to process packageUpdateType`
- `0x18008ba2f`: `Validation on updateType failed.`
- `0x18008c473`: `Failed to get update root element.`
- `0x18008b72e`: `Invalid update attributes`
- `0x18008b83f`: `unexpected update attribute; found {}`
- `0x18008c1d0`: `cannot mix different types in one update`
- `0x18008c31e`: `cannot mix different types in one update`
- `0x18008c41f`: `cannot mix different types in one update`
- `0x18008c5cc`: `cannot mix different types in one update`
- `0x18008bd6f`: `Failed to get update root elment.`
- `0x18008bce7`: `Failed to save last token`

## pseudocode

```c
__int64 __fastcall ProcessUpdateType(
        struct _XML_TOKENIZATION_STATE *a1,
        struct ParsingSession *a2,
        struct PACKAGE_TYPE *a3,
        struct UPDATE_TYPE *a4)
{
  unsigned int v7; // edi
  int v8; // edx
  __int64 v9; // rdx
  int v11; // edx
  int v12; // edx
  int Token; // esi
  int Value; // eax
  int v15; // edx
  __int64 v16; // rdx
  int v17; // edx
  int v18; // r8d
  int UINTFromString; // eax
  int v20; // edx
  int v21; // ebx
  __int64 v22; // rdx
  int updated; // eax
  int v24; // edx
  int v25; // edx
  int v26; // edx
  int v27; // edx
  int v28; // edx
  int v29; // edx
  int v30; // edx
  int v31; // edx
  int v32; // eax
  int v33; // edx
  void *v34; // r12
  wchar_t **v35; // rax
  wchar_t **v36; // rsi
  int v37; // eax
  struct _XML_TOKENIZATION_STATE *v38; // rdx
  int v39; // r15d
  int v40; // edx
  __int64 v41; // rdx
  int v42; // eax
  int v43; // edx
  int v44; // eax
  int v45; // edx
  int v46; // edx
  int v47; // eax
  int v48; // edx
  int NextElementEnumValue; // eax
  int v50; // edx
  unsigned int v51; // esi
  _QWORD *v52; // rax
  _QWORD *v53; // r15
  _QWORD *v54; // rax
  _DWORD *v55; // rax
  _QWORD *v56; // rax
  char *v57; // rax
  __int64 *v58; // rcx
  __int64 v59; // rax
  int v60; // edx
  int v61; // edx
  int v62; // edx
  int v63; // edx
  int v64; // edx
  int v65; // edx
  int v66; // edx
  int v67; // edx
  int v68; // edx
  int v69; // edx
  int v70; // edx
  int v71; // edx
  int v72; // edx
  int v73; // edx
  int v74; // edx
  int v75; // edx
  int v76; // edx
  int v77; // edx
  int v78; // edx
  int v79; // [rsp+20h] [rbp-99h]
  bool v80; // [rsp+40h] [rbp-79h] BYREF
  bool v81; // [rsp+41h] [rbp-78h] BYREF
  int v82[2]; // [rsp+48h] [rbp-71h] BYREF
  int *v83; // [rsp+50h] [rbp-69h] BYREF
  int *v84; // [rsp+58h] [rbp-61h] BYREF
  int *v85; // [rsp+60h] [rbp-59h] BYREF
  void *v86[2]; // [rsp+68h] [rbp-51h] BYREF
  __int128 v87; // [rsp+78h] [rbp-41h]
  bool v88[4]; // [rsp+88h] [rbp-31h] BYREF
  int v89; // [rsp+8Ch] [rbp-2Dh] BYREF
  struct PACKAGE_TYPE *v90; // [rsp+90h] [rbp-29h] BYREF
  int v91; // [rsp+98h] [rbp-21h] BYREF
  unsigned __int16 v92[2]; // [rsp+9Ch] [rbp-1Dh] BYREF
  int v93; // [rsp+A0h] [rbp-19h] BYREF
  int v94; // [rsp+A4h] [rbp-15h] BYREF
  int v95[4]; // [rsp+A8h] [rbp-11h] BYREF
  __int128 v96; // [rsp+B8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v90 = a3;
  v92[0] = 0;
  v88[0] = 0;
  v81 = 0;
  v80 = 0;
  *(_OWORD *)v95 = 0;
  v96 = 0;
  *(_OWORD *)v86 = 0;
  v87 = 0;
  if ( !a1 )
  {
    v7 = -2147024809;
    v91 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No state specified");
      v90 = (struct PACKAGE_TYPE *)&v91;
      LOBYTE(v8) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v8,
        3,
        (unsigned int)": {}",
        (__int64)&v90);
    }
    v9 = 606;
    goto LABEL_5;
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    v91 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No parsing session specified");
      v90 = (struct PACKAGE_TYPE *)&v91;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v11,
        3,
        (unsigned int)": {}",
        (__int64)&v90);
    }
    v9 = 607;
    goto LABEL_5;
  }
  if ( !a4 )
  {
    v7 = -2147467261;
    v91 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No update result specified");
      v90 = (struct PACKAGE_TYPE *)&v91;
      LOBYTE(v12) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v12,
        3,
        (unsigned int)": {}",
        (__int64)&v90);
    }
    v9 = 608;
    goto LABEL_5;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        Token = PeekNextToken(a1, (struct _XML_TOKEN *)v95);
        if ( Token < 0 )
        {
          LODWORD(v90) = Token;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to peek next token.");
            *(_QWORD *)v82 = &v90;
            LOBYTE(v78) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v78,
              3,
              (unsigned int)": {}",
              (__int64)v82);
          }
          v16 = 618;
LABEL_207:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v16,
            (unsigned int)"onecore\\base\\cbs\\parser\\update.cpp",
            (const char *)(unsigned int)Token,
            v79);
          return (unsigned int)Token;
        }
        if ( DWORD2(v96) != 7 )
          break;
        Token = ExpectToken(a1, 7, v95);
        if ( Token < 0 )
        {
          v91 = Token;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
            v90 = (struct PACKAGE_TYPE *)&v91;
            LOBYTE(v25) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v25,
              3,
              (unsigned int)": {}",
              (__int64)&v90);
          }
          v16 = 621;
          goto LABEL_207;
        }
        Value = GetValue(a1, (const struct _XML_TOKEN *)v95, (struct _XML_TOKEN *)v86);
        Token = Value;
        if ( Value < 0 )
        {
          v91 = Value;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get value.");
            v90 = (struct PACKAGE_TYPE *)&v91;
            LOBYTE(v15) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v15,
              3,
              (unsigned int)": {}",
              (__int64)&v90);
          }
          v16 = 623;
          goto LABEL_207;
        }
      }
      if ( !(unsigned int)GetNextAttributeEnumValue(
                            a2,
                            a1,
                            (struct enumType *const)&UPDATE_TYPE_ATTRIBUTE_MAP,
                            v88,
                            (struct _XML_TOKEN *)v95,
                            v92,
                            0) )
        break;
      Token = GetValue(a1, (const struct _XML_TOKEN *)v95, (struct _XML_TOKEN *)v86);
      if ( Token < 0 )
      {
        LODWORD(v90) = Token;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "failed to get value");
          *(_QWORD *)v82 = &v90;
          LOBYTE(v77) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v77,
            3,
            (unsigned int)": {}",
            (__int64)v82);
        }
        v16 = 694;
        goto LABEL_207;
      }
      updated = ProcessCommonUpdateAttributesGroup(
                  a1,
                  a2,
                  (const struct _XML_TOKEN *)v95,
                  (const struct _XML_TOKEN *)v86,
                  &v81,
                  &v80,
                  a4);
      Token = updated;
      if ( updated < 0 )
      {
        LODWORD(v90) = updated;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid update attributes");
          *(_QWORD *)v82 = &v90;
          LOBYTE(v24) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v24,
            3,
            (unsigned int)": {}",
            (__int64)v82);
        }
        v16 = 702;
        goto LABEL_207;
      }
    }
    if ( v88[0] )
      break;
    Token = GetValue(a1, (const struct _XML_TOKEN *)v95, (struct _XML_TOKEN *)v86);
    if ( Token < 0 )
    {
      v89 = Token;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "failed to get value");
        v90 = (struct PACKAGE_TYPE *)&v89;
        LOBYTE(v31) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v31,
          3,
          (unsigned int)": {}",
          (__int64)&v90);
      }
      v16 = 643;
      goto LABEL_207;
    }
    switch ( v92[0] )
    {
      case 1u:
        if ( *((_QWORD *)a4 + 1) )
        {
          v7 = -2146498546;
          v91 = -2146498546;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Duplicate name.");
            v90 = (struct PACKAGE_TYPE *)&v91;
            LOBYTE(v30) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v30,
              3,
              (unsigned int)": {}",
              (__int64)&v90);
          }
          v9 = 647;
          goto LABEL_5;
        }
        v21 = DuplicateXmlString(
                (wchar_t **)a4 + 1,
                a1,
                (struct _XML_EXTENT *)v86,
                (struct ParsingSession *)((char *)a2 + 48));
        if ( v21 < 0 )
        {
          v22 = 653;
          goto LABEL_42;
        }
        break;
      case 2u:
        if ( *((_QWORD *)a4 + 2) )
        {
          v7 = -2146498546;
          v91 = -2146498546;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Duplicate displayName.");
            v90 = (struct PACKAGE_TYPE *)&v91;
            LOBYTE(v29) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v29,
              3,
              (unsigned int)": {}",
              (__int64)&v90);
          }
          v9 = 658;
LABEL_5:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v9,
            (unsigned int)"onecore\\base\\cbs\\parser\\update.cpp",
            (const char *)v7,
            v79);
          return v7;
        }
        v21 = DuplicateXmlString(
                (wchar_t **)a4 + 2,
                a1,
                (struct _XML_EXTENT *)v86,
                (struct ParsingSession *)((char *)a2 + 48));
        if ( v21 < 0 )
        {
          v22 = 664;
          goto LABEL_42;
        }
        break;
      case 3u:
        if ( *((_QWORD *)a4 + 3) )
        {
          v7 = -2146498546;
          v91 = -2146498546;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Duplicate description.");
            v90 = (struct PACKAGE_TYPE *)&v91;
            LOBYTE(v28) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v28,
              3,
              (unsigned int)": {}",
              (__int64)&v90);
          }
          v9 = 669;
          goto LABEL_5;
        }
        v21 = DuplicateXmlString(
                (wchar_t **)a4 + 3,
                a1,
                (struct _XML_EXTENT *)v86,
                (struct ParsingSession *)((char *)a2 + 48));
        if ( v21 < 0 )
        {
          v22 = 675;
LABEL_42:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v22,
            (unsigned int)"onecore\\base\\cbs\\parser\\update.cpp",
            (const char *)(unsigned int)v21,
            v79);
          return (unsigned int)v21;
        }
        break;
      case 4u:
        if ( *((_DWORD *)a4 + 8) )
        {
          v7 = -2146498546;
          v91 = -2146498546;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Duplicate downloadSize.");
            v90 = (struct PACKAGE_TYPE *)&v91;
            LOBYTE(v26) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v26,
              3,
              (unsigned int)": {}",
              (__int64)&v90);
          }
          v9 = 680;
          goto LABEL_5;
        }
        UINTFromString = GetUINTFromString(v86[0], (unsigned __int64)v86[1], (unsigned int *)a4 + 8);
        Token = UINTFromString;
        if ( UINTFromString < 0 )
        {
          v91 = UINTFromString;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get download size.");
            v90 = (struct PACKAGE_TYPE *)&v91;
            LOBYTE(v20) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v20,
              3,
              (unsigned int)": {}",
              (__int64)&v90);
          }
          v16 = 684;
          goto LABEL_207;
        }
        break;
      default:
        v7 = -2146498547;
        v91 = -2146498547;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<unsigned short>(
            (_DWORD)LogAdapter::g_Logger,
            v17,
            v18,
            (unsigned int)"unexpected update attribute; found {}",
            (__int64)v92);
          v90 = (struct PACKAGE_TYPE *)&v91;
          LOBYTE(v27) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v27,
            3,
            (unsigned int)": {}",
            (__int64)&v90);
        }
        v9 = 688;
        goto LABEL_5;
    }
  }
  if ( IsElementClosed(a1) )
  {
    ExpectNoElement(a2, a1);
    goto LABEL_71;
  }
  v34 = (void *)*((_QWORD *)a1 + 4);
  if ( GetNextElementEnumValue(
         1u,
         a2,
         a1,
         (struct enumType *const)&UPDATE_TYPE_ROOT_ELEMENT_MAP,
         v88,
         (struct _XML_TOKEN *)v95,
         v92) < 0
    || v88[0]
    || v92[0] != 4 )
  {
    v47 = SaveToken(a2, (const struct _XML_TOKEN *)v95, v88[0]);
    Token = v47;
    if ( v47 < 0 )
    {
      v89 = v47;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to save last token");
        v90 = (struct PACKAGE_TYPE *)&v89;
        LOBYTE(v48) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v48,
          3,
          (unsigned int)": {}",
          (__int64)&v90);
      }
      v16 = 763;
      goto LABEL_207;
    }
  }
  else
  {
    v35 = (wchar_t **)CMemoryAllocator::Alloc((struct ParsingSession *)((char *)a2 + 48), 0x30u);
    v36 = v35;
    if ( !v35 )
    {
      v7 = -2147024882;
      v89 = -2147024882;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate custom information");
        v90 = (struct PACKAGE_TYPE *)&v89;
        LOBYTE(v46) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v46,
          3,
          (unsigned int)": {}",
          (__int64)&v90);
      }
      v9 = 741;
      goto LABEL_5;
    }
    *v35 = 0;
    v35[1] = 0;
    v35[2] = 0;
    v35[3] = 0;
    v35[4] = 0;
    v35[5] = 0;
    v37 = ProcessCustomInformation(a1, a2, 0, 0, (struct CUSTOM_INFORMATION_TYPE *)v35);
    v39 = v37;
    if ( v37 < 0 )
    {
      v89 = v37;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to process custom information");
        v90 = (struct PACKAGE_TYPE *)&v89;
        LOBYTE(v40) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v40,
          3,
          (unsigned int)": {}",
          (__int64)&v90);
      }
      v41 = 749;
LABEL_83:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v41,
        (unsigned int)"onecore\\base\\cbs\\parser\\update.cpp",
        (const char *)(unsigned int)v39,
        v79);
      return (unsigned int)v39;
    }
    v42 = DuplicateXmlBlobToString(v36 + 5, v38, v34, *((void **)a1 + 4), (struct ParsingSession *)((char *)a2 + 48));
    v39 = v42;
    if ( v42 < 0 )
    {
      v89 = v42;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          LogAdapter::g_Logger,
          0,
          3,
          "Failed to convert custom information blob to string");
        v90 = (struct PACKAGE_TYPE *)&v89;
        LOBYTE(v43) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v43,
          3,
          (unsigned int)": {}",
          (__int64)&v90);
      }
      v41 = 755;
      goto LABEL_83;
    }
    *((_QWORD *)a4 + 12) = v36;
  }
  v44 = ProcessUpdateGroupType(a1, a2, (struct APPLICABLE_TYPE_NODE **)a4 + 5);
  Token = v44;
  if ( v44 < 0 )
  {
    v89 = v44;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to process update group");
      v90 = (struct PACKAGE_TYPE *)&v89;
      LOBYTE(v45) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v45,
        3,
        (unsigned int)": {}",
        (__int64)&v90);
    }
    v16 = 766;
    goto LABEL_207;
  }
  NextElementEnumValue = GetNextElementEnumValue(
                           0,
                           a2,
                           a1,
                           (struct enumType *const)&UPDATE_TYPE_ROOT_ELEMENT_MAP,
                           v88,
                           (struct _XML_TOKEN *)v95,
                           v92);
  Token = NextElementEnumValue;
  if ( NextElementEnumValue < 0 )
  {
    v89 = NextElementEnumValue;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get update root elment.");
      v90 = (struct PACKAGE_TYPE *)&v89;
      LOBYTE(v50) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v50,
        3,
        (unsigned int)": {}",
        (__int64)&v90);
    }
    v16 = 779;
    goto LABEL_207;
  }
  v51 = 0;
  while ( !v88[0] )
  {
    v52 = CMemoryAllocator::Alloc((struct ParsingSession *)((char *)a2 + 48), 0x18u);
    v53 = v52;
    if ( !v52 )
    {
      v7 = -2147024882;
      LODWORD(v90) = -2147024882;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "allocating deployment node");
        *(_QWORD *)v82 = &v90;
        LOBYTE(v76) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v76,
          3,
          (unsigned int)": {}",
          (__int64)v82);
      }
      v9 = 783;
      goto LABEL_5;
    }
    *(_DWORD *)v52 = 0;
    v52[1] = 0;
    v52[2] = 0;
    switch ( v92[0] )
    {
      case 1u:
        if ( v51 > 2 )
        {
          v7 = -2146498547;
          LODWORD(v90) = -2146498547;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "cannot mix different types in one update");
            *(_QWORD *)v82 = &v90;
            LOBYTE(v75) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v75,
              3,
              (unsigned int)": {}",
              (__int64)v82);
          }
          v9 = 790;
          goto LABEL_5;
        }
        v57 = (char *)CMemoryAllocator::Alloc((struct ParsingSession *)((char *)a2 + 48), 0x50u);
        if ( v57 )
        {
          *(_QWORD *)v57 = 0;
          *((_QWORD *)v57 + 1) = 0;
          *((_QWORD *)v57 + 2) = 0;
          *((_QWORD *)v57 + 3) = 0;
          *((_QWORD *)v57 + 4) = 0;
          *((_QWORD *)v57 + 5) = 0;
          *((_QWORD *)v57 + 6) = 0;
          *((_QWORD *)v57 + 7) = 0;
          *((_QWORD *)v57 + 8) = 0;
          *((_WORD *)v57 + 36) = 0;
          v57[74] = 0;
          *(_DWORD *)(v57 + 75) = 0;
          v57[79] = 0;
        }
        else
        {
          v57 = 0;
        }
        v53[1] = v57;
        if ( !v57 )
        {
          v7 = -2147024882;
          LODWORD(v90) = -2147024882;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "allocating UPDATE_TYPE");
            *(_QWORD *)v82 = &v90;
            LOBYTE(v74) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v74,
              3,
              (unsigned int)": {}",
              (__int64)v82);
          }
          v9 = 795;
          goto LABEL_5;
        }
        Token = ProcessComponentUpdateType(a1, a2, (struct COMPONENT_UPDATE_TYPE *)v57);
        if ( Token < 0 )
        {
          LODWORD(v90) = Token;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to process ComponentUpdateType");
            *(_QWORD *)v82 = &v90;
            LOBYTE(v73) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v73,
              3,
              (unsigned int)": {}",
              (__int64)v82);
          }
          v16 = 801;
          goto LABEL_207;
        }
        v51 = 1;
        break;
      case 2u:
        if ( v51 > 2 )
        {
          v7 = -2146498547;
          v93 = -2146498547;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "cannot mix different types in one update");
            v83 = &v93;
            LOBYTE(v70) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v70,
              3,
              (unsigned int)": {}",
              (__int64)&v83);
          }
          v9 = 807;
          goto LABEL_5;
        }
        v56 = CMemoryAllocator::Alloc((struct ParsingSession *)((char *)a2 + 48), 0x58u);
        if ( v56 )
        {
          *v56 = 0;
          v56[1] = 0;
          v56[2] = 0;
          v56[3] = 0;
          v56[4] = 0;
          v56[5] = 0;
          v56[6] = 0;
          v56[7] = 0;
          v56[8] = 0;
          v56[9] = 0;
          *((_DWORD *)v56 + 20) = 0;
          *((_WORD *)v56 + 42) = 256;
        }
        else
        {
          v56 = 0;
        }
        v53[1] = v56;
        if ( !v56 )
        {
          v7 = -2147024882;
          v93 = -2147024882;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "allocating UPDATE_TYPE");
            v83 = &v93;
            LOBYTE(v69) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v69,
              3,
              (unsigned int)": {}",
              (__int64)&v83);
          }
          v9 = 812;
          goto LABEL_5;
        }
        Token = ProcessDriverUpdateType(a1, a2, (struct DRIVER_UPDATE_TYPE *)v56);
        if ( Token < 0 )
        {
          v93 = Token;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to process DriverUpdateType");
            v83 = &v93;
            LOBYTE(v68) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v68,
              3,
              (unsigned int)": {}",
              (__int64)&v83);
          }
          v16 = 817;
          goto LABEL_207;
        }
        v51 = 2;
        break;
      case 3u:
        if ( v51 )
        {
          v7 = -2146498547;
          v89 = -2146498547;
          if ( v51 == 3 )
          {
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "cannot have more than one package in one update");
              v85 = &v89;
              LOBYTE(v66) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v66,
                3,
                (unsigned int)": {}",
                (__int64)&v85);
            }
            v9 = 825;
          }
          else
          {
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "cannot mix different types in one update");
              v85 = &v89;
              LOBYTE(v67) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v67,
                3,
                (unsigned int)": {}",
                (__int64)&v85);
            }
            v9 = 829;
          }
          goto LABEL_5;
        }
        v55 = CMemoryAllocator::Alloc((struct ParsingSession *)((char *)a2 + 48), 0x68u);
        if ( v55 )
        {
          *(_BYTE *)v55 = 0;
          v55[1] = 2;
          *((_QWORD *)v55 + 1) = 0;
          *((_QWORD *)v55 + 2) = 0;
          *((_QWORD *)v55 + 3) = 0;
          *((_QWORD *)v55 + 4) = 0;
          *((_QWORD *)v55 + 5) = 0;
          *((_QWORD *)v55 + 6) = 0;
          *((_QWORD *)v55 + 7) = 0;
          *((_QWORD *)v55 + 8) = 0;
          *((_QWORD *)v55 + 9) = 0;
          *((_WORD *)v55 + 40) = 0;
          *((_BYTE *)v55 + 82) = 0;
          *(_DWORD *)((char *)v55 + 83) = 0;
          *((_BYTE *)v55 + 87) = 0;
          *((_QWORD *)v55 + 11) = 0;
          v55[24] = 0;
        }
        else
        {
          v55 = 0;
        }
        v53[1] = v55;
        if ( !v55 )
        {
          v7 = -2147024882;
          v89 = -2147024882;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "allocating UPDATE_TYPE");
            v85 = &v89;
            LOBYTE(v65) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v65,
              3,
              (unsigned int)": {}",
              (__int64)&v85);
          }
          v9 = 835;
          goto LABEL_5;
        }
        Token = ProcessPackageUpdateType(a1, a2, v90, (struct PACKAGE_UPDATE_TYPE *)v55);
        if ( Token < 0 )
        {
          v91 = Token;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to process packageUpdateType");
            v85 = &v91;
            LOBYTE(v64) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v64,
              3,
              (unsigned int)": {}",
              (__int64)&v85);
          }
          v16 = 841;
          goto LABEL_207;
        }
        v51 = 3;
        break;
      case 5u:
        if ( v51 )
        {
          v7 = -2146498547;
          v89 = -2146498547;
          if ( v51 == 5 )
          {
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "cannot have more than one capability in one update");
              v84 = &v89;
              LOBYTE(v62) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v62,
                3,
                (unsigned int)": {}",
                (__int64)&v84);
            }
            v9 = 849;
          }
          else
          {
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                LogAdapter::g_Logger,
                0,
                3,
                "cannot mix different types in one update");
              v84 = &v89;
              LOBYTE(v63) = 1;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v63,
                3,
                (unsigned int)": {}",
                (__int64)&v84);
            }
            v9 = 853;
          }
          goto LABEL_5;
        }
        v54 = CMemoryAllocator::Alloc((struct ParsingSession *)((char *)a2 + 48), 0x68u);
        if ( v54 )
        {
          *v54 = 0;
          v54[1] = 0;
          v54[2] = 0;
          v54[3] = 0;
          v54[4] = 0;
          v54[5] = 0;
          v54[6] = 0;
          v54[7] = 0;
          v54[8] = 0;
          *((_DWORD *)v54 + 18) = 96;
          *((_DWORD *)v54 + 19) = 1;
          *((_DWORD *)v54 + 20) = 1;
          *((_DWORD *)v54 + 21) = 1;
          *((_DWORD *)v54 + 22) = 1;
          *((_DWORD *)v54 + 23) = 1;
          v54[12] = 1;
        }
        else
        {
          v54 = 0;
        }
        v53[1] = v54;
        if ( !v54 )
        {
          v7 = -2147024882;
          v89 = -2147024882;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "allocating allocating UPDATE_TYPE");
            v84 = &v89;
            LOBYTE(v61) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v61,
              3,
              (unsigned int)": {}",
              (__int64)&v84);
          }
          v9 = 859;
          goto LABEL_5;
        }
        Token = ProcessCapabilityUpdateType(a1, a2, (struct CAPABILITY_UPDATE_TYPE *)v54);
        if ( Token < 0 )
        {
          v89 = Token;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to process CapabilityUpdateType");
            v84 = &v89;
            LOBYTE(v60) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v60,
              3,
              (unsigned int)": {}",
              (__int64)&v84);
          }
          v16 = 864;
          goto LABEL_207;
        }
        v51 = 5;
        break;
    }
    v58 = (__int64 *)((char *)a4 + 80);
    *(_DWORD *)v53 = v92[0];
    if ( a4 == (struct UPDATE_TYPE *)-80LL )
    {
      v7 = -2147024809;
      v94 = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to add deployment node");
        v83 = &v94;
        LOBYTE(v72) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v72,
          3,
          (unsigned int)": {}",
          (__int64)&v83);
      }
      v9 = 873;
      goto LABEL_5;
    }
    v59 = *v58;
    if ( *v58 )
    {
      while ( *(_QWORD *)(v59 + 16) )
        v59 = *(_QWORD *)(v59 + 16);
      *(_QWORD *)(v59 + 16) = v53;
      v53[2] = 0;
    }
    else
    {
      *v58 = (__int64)v53;
    }
    ++*((_DWORD *)a4 + 22);
    v39 = GetNextElementEnumValue(
            0,
            a2,
            a1,
            (struct enumType *const)&UPDATE_TYPE_ROOT_ELEMENT_MAP,
            v88,
            (struct _XML_TOKEN *)v95,
            v92);
    if ( v39 < 0 )
    {
      v93 = v39;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get update root element.");
        v83 = &v93;
        LOBYTE(v71) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v71,
          3,
          (unsigned int)": {}",
          (__int64)&v83);
      }
      v41 = 885;
      goto LABEL_83;
    }
  }
LABEL_71:
  v32 = ValidateUpdateType(a4);
  v7 = v32;
  if ( v32 < 0 )
  {
    LODWORD(v90) = v32;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Validation on updateType failed.");
      *(_QWORD *)v82 = &v90;
      LOBYTE(v33) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v33,
        3,
        (unsigned int)": {}",
        (__int64)v82);
    }
    v9 = 891;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x18008b2f4  push    rbp
0x18008b2f6  push    rbx
0x18008b2f7  push    rsi
0x18008b2f8  push    rdi
0x18008b2f9  push    r12
0x18008b2fb  push    r13
0x18008b2fd  push    r14
0x18008b2ff  push    r15
0x18008b301  lea     rbp, [rsp-1Fh]
0x18008b306  sub     rsp, 0D8h
0x18008b30d  mov     rax, cs:__security_cookie
0x18008b314  xor     rax, rsp
0x18008b317  mov     [rbp+57h+var_48], rax
0x18008b31b  xor     r15d, r15d
0x18008b31e  mov     [rbp+57h+var_80], r8
0x18008b322  mov     [rbp+57h+var_74], r15w
0x18008b327  xorps   xmm0, xmm0
0x18008b32a  mov     [rbp+57h+var_88], r15b
0x18008b32e  xorps   xmm1, xmm1
0x18008b331  mov     [rbp+57h+var_CF], r15b
0x18008b335  mov     r13, r9
0x18008b338  mov     [rbp+57h+var_D0], r15b
0x18008b33c  mov     r14, rdx
0x18008b33f  mov     rdi, rcx
0x18008b342  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x18008b346  movups  [rbp+57h+var_58], xmm0
0x18008b34a  movups  xmmword ptr [rbp+57h+var_A8], xmm1
0x18008b34e  movups  [rbp+57h+var_98], xmm1
0x18008b352  test    rcx, rcx
0x18008b355  jnz     short loc_18008B3C8
0x18008b357  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b35e  mov     edi, 80070057h
0x18008b363  mov     [rbp+57h+var_78], edi
0x18008b366  test    rcx, rcx
0x18008b369  jz      short loc_18008B3A9
0x18008b36b  lea     ebx, [r15+3]
0x18008b36f  xor     edx, edx
0x18008b371  mov     r8d, ebx
0x18008b374  lea     r9, aNoStateSpecifi_0; "No state specified"
0x18008b37b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008b380  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b387  lea     rax, [rbp+57h+var_78]
0x18008b38b  mov     [rbp+57h+var_80], rax
0x18008b38f  lea     r9, asc_1802EE7AC; ": {}"
0x18008b396  lea     rax, [rbp+57h+var_80]
0x18008b39a  mov     r8d, ebx
0x18008b39d  mov     dl, 1
0x18008b39f  mov     [rsp+110h+var_F0], rax; int
0x18008b3a4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008b3a9  mov     edx, 25Eh; void *
0x18008b3ae  mov     rcx, [rbp+5Fh]; this
0x18008b3b2  lea     r8, aOnecoreBaseCbs_131; "onecore\\base\\cbs\\parser\\update.cpp"
0x18008b3b9  mov     r9d, edi; char *
0x18008b3bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b3c1  mov     eax, edi
0x18008b3c3  jmp     loc_18008C72C
0x18008b3c8  test    r14, r14
0x18008b3cb  jnz     short loc_18008B426
0x18008b3cd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b3d4  mov     edi, 80070057h
0x18008b3d9  mov     [rbp+57h+var_78], edi
0x18008b3dc  test    rcx, rcx
0x18008b3df  jz      short loc_18008B41F
0x18008b3e1  lea     ebx, [r14+3]
0x18008b3e5  xor     edx, edx
0x18008b3e7  mov     r8d, ebx
0x18008b3ea  lea     r9, aNoParsingSessi_0; "No parsing session specified"
0x18008b3f1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008b3f6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b3fd  lea     rax, [rbp+57h+var_78]
0x18008b401  mov     [rbp+57h+var_80], rax
0x18008b405  lea     r9, asc_1802EE7AC; ": {}"
0x18008b40c  lea     rax, [rbp+57h+var_80]
0x18008b410  mov     r8d, ebx
0x18008b413  mov     dl, 1
0x18008b415  mov     [rsp+110h+var_F0], rax
0x18008b41a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008b41f  mov     edx, 25Fh
0x18008b424  jmp     short loc_18008B3AE
0x18008b426  test    r13, r13
0x18008b429  jnz     short loc_18008B487
0x18008b42b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b432  mov     edi, 80004003h
0x18008b437  mov     [rbp+57h+var_78], edi
0x18008b43a  test    rcx, rcx
0x18008b43d  jz      short loc_18008B47D
0x18008b43f  lea     ebx, [r13+3]
0x18008b443  xor     edx, edx
0x18008b445  mov     r8d, ebx
0x18008b448  lea     r9, aNoUpdateResult; "No update result specified"
0x18008b44f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008b454  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b45b  lea     rax, [rbp+57h+var_78]
0x18008b45f  mov     [rbp+57h+var_80], rax
0x18008b463  lea     r9, asc_1802EE7AC; ": {}"
0x18008b46a  lea     rax, [rbp+57h+var_80]
0x18008b46e  mov     r8d, ebx
0x18008b471  mov     dl, 1
0x18008b473  mov     [rsp+110h+var_F0], rax
0x18008b478  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008b47d  mov     edx, 260h
0x18008b482  jmp     loc_18008B3AE
0x18008b487  lea     rdx, [rbp+57h+var_68]; struct _XML_TOKEN *
0x18008b48b  mov     rcx, rdi; struct _XML_TOKENIZATION_STATE *
0x18008b48e  call    ?PeekNextToken@@YAJPEAU_XML_TOKENIZATION_STATE@@PEAU_XML_TOKEN@@@Z; PeekNextToken(_XML_TOKENIZATION_STATE *,_XML_TOKEN *)
0x18008b493  mov     esi, eax
0x18008b495  test    eax, eax
0x18008b497  js      loc_18008C6C4
0x18008b49d  cmp     dword ptr [rbp+57h+var_58+8], 7
0x18008b4a1  jnz     loc_18008B530
0x18008b4a7  lea     r8, [rbp+57h+var_68]
0x18008b4ab  mov     edx, 7
0x18008b4b0  mov     rcx, rdi
0x18008b4b3  call    ?ExpectToken@@YAJPEAU_XML_TOKENIZATION_STATE@@W4XML_TOKENIZATION_SPECIFIC_STATE@@PEAU_XML_TOKEN@@@Z; ExpectToken(_XML_TOKENIZATION_STATE *,XML_TOKENIZATION_SPECIFIC_STATE,_XML_TOKEN *)
0x18008b4b8  mov     esi, eax
0x18008b4ba  test    eax, eax
0x18008b4bc  js      loc_18008B772
0x18008b4c2  lea     r8, [rbp+57h+var_A8]; struct _XML_TOKEN *
0x18008b4c6  mov     rcx, rdi; struct _XML_TOKENIZATION_STATE *
0x18008b4c9  lea     rdx, [rbp+57h+var_68]; struct _XML_TOKEN *
0x18008b4cd  call    ?GetValue@@YAJPEAU_XML_TOKENIZATION_STATE@@PEBU_XML_TOKEN@@PEAU2@@Z; GetValue(_XML_TOKENIZATION_STATE *,_XML_TOKEN const *,_XML_TOKEN *)
0x18008b4d2  mov     esi, eax
0x18008b4d4  test    eax, eax
0x18008b4d6  jns     short loc_18008B487
0x18008b4d8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b4df  mov     [rbp+57h+var_78], eax
0x18008b4e2  test    rcx, rcx
0x18008b4e5  jz      short loc_18008B526
0x18008b4e7  mov     ebx, 3
0x18008b4ec  lea     r9, aFailedToGetVal_0; "Failed to get value."
0x18008b4f3  mov     r8d, ebx
0x18008b4f6  xor     edx, edx
0x18008b4f8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008b4fd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b504  lea     rax, [rbp+57h+var_78]
0x18008b508  mov     [rbp+57h+var_80], rax
0x18008b50c  lea     r9, asc_1802EE7AC; ": {}"
0x18008b513  lea     rax, [rbp+57h+var_80]
0x18008b517  mov     r8d, ebx
0x18008b51a  mov     dl, 1
0x18008b51c  mov     [rsp+110h+var_F0], rax
0x18008b521  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008b526  mov     edx, 26Fh
0x18008b52b  jmp     loc_18008C717
0x18008b530  lea     rax, [rbp+57h+var_74]
0x18008b534  mov     byte ptr [rsp+110h+var_E0], r15b; bool
0x18008b539  mov     [rsp+110h+var_E8], rax; unsigned __int16 *
0x18008b53e  lea     r9, [rbp+57h+var_88]; bool *
0x18008b542  lea     rax, [rbp+57h+var_68]
0x18008b546  mov     rdx, rdi; struct _XML_TOKENIZATION_STATE *
0x18008b549  lea     r8, ?UPDATE_TYPE_ATTRIBUTE_MAP@@3PAUenumType@@A; struct enumType *
0x18008b550  mov     [rsp+110h+var_F0], rax; int
0x18008b555  mov     rcx, r14; struct ParsingSession *
0x18008b558  call    ?GetNextAttributeEnumValue@@YAJPEAUParsingSession@@PEAU_XML_TOKENIZATION_STATE@@QEAUenumType@@PEA_NPEAU_XML_TOKEN@@PEAG_N@Z; GetNextAttributeEnumValue(ParsingSession *,_XML_TOKENIZATION_STATE *,enumType * const,bool *,_XML_TOKEN *,ushort *,bool)
0x18008b55d  mov     rcx, rdi; struct _XML_TOKENIZATION_STATE *
0x18008b560  test    eax, eax
0x18008b562  jnz     loc_18008B6CF
0x18008b568  cmp     [rbp+57h+var_88], r15b
0x18008b56c  jnz     loc_18008B9F5
0x18008b572  lea     r8, [rbp+57h+var_A8]; struct _XML_TOKEN *
0x18008b576  lea     rdx, [rbp+57h+var_68]; struct _XML_TOKEN *
0x18008b57a  call    ?GetValue@@YAJPEAU_XML_TOKENIZATION_STATE@@PEBU_XML_TOKEN@@PEAU2@@Z; GetValue(_XML_TOKENIZATION_STATE *,_XML_TOKEN const *,_XML_TOKEN *)
0x18008b57f  mov     esi, eax
0x18008b581  test    eax, eax
0x18008b583  js      loc_18008B99D
0x18008b589  movzx   ecx, [rbp+57h+var_74]
0x18008b58d  sub     ecx, 1
0x18008b590  jz      loc_18008B689
0x18008b596  sub     ecx, 1
0x18008b599  jz      loc_18008B65B
0x18008b59f  sub     ecx, 1
0x18008b5a2  jz      loc_18008B62D
0x18008b5a8  cmp     ecx, 1
0x18008b5ab  jnz     loc_18008B827
0x18008b5b1  lea     r8, [r13+20h]; unsigned int *
0x18008b5b5  cmp     [r8], r15d
0x18008b5b8  jnz     loc_18008B7CA
0x18008b5be  mov     rdx, [rbp+57h+var_A8+8]; unsigned __int64
0x18008b5c2  mov     rcx, [rbp+57h+var_A8]; void *
0x18008b5c6  call    ?GetUINTFromString@@YAJQEAX_KPEAI@Z; GetUINTFromString(void * const,unsigned __int64,uint *)
0x18008b5cb  mov     esi, eax
0x18008b5cd  test    eax, eax
0x18008b5cf  jns     loc_18008B487
0x18008b5d5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b5dc  mov     [rbp+57h+var_78], eax
0x18008b5df  test    rcx, rcx
0x18008b5e2  jz      short loc_18008B623
0x18008b5e4  mov     ebx, 3
0x18008b5e9  lea     r9, aFailedToGetDow_0; "Failed to get download size."
0x18008b5f0  mov     r8d, ebx
0x18008b5f3  xor     edx, edx
0x18008b5f5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008b5fa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b601  lea     rax, [rbp+57h+var_78]
0x18008b605  mov     [rbp+57h+var_80], rax
0x18008b609  lea     r9, asc_1802EE7AC; ": {}"
0x18008b610  lea     rax, [rbp+57h+var_80]
0x18008b614  mov     r8d, ebx
0x18008b617  mov     dl, 1
0x18008b619  mov     [rsp+110h+var_F0], rax
0x18008b61e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008b623  mov     edx, 2ACh
0x18008b628  jmp     loc_18008C717
0x18008b62d  lea     rcx, [r13+18h]; wchar_t **
0x18008b631  cmp     [rcx], r15
0x18008b634  jnz     loc_18008B886
0x18008b63a  lea     r9, [r14+30h]; struct CMemoryAllocator *
0x18008b63e  mov     rdx, rdi; struct _XML_TOKENIZATION_STATE *
0x18008b641  lea     r8, [rbp+57h+var_A8]; struct _XML_EXTENT *
0x18008b645  call    ?DuplicateXmlString@@YAJPEAPEA_WPEAU_XML_TOKENIZATION_STATE@@PEAU_XML_EXTENT@@PEAVCMemoryAllocator@@@Z; DuplicateXmlString(wchar_t * *,_XML_TOKENIZATION_STATE *,_XML_EXTENT *,CMemoryAllocator *)
0x18008b64a  mov     ebx, eax
0x18008b64c  test    eax, eax
0x18008b64e  jns     loc_18008B487
0x18008b654  mov     edx, 2A3h
0x18008b659  jmp     short loc_18008B6B5
0x18008b65b  lea     rcx, [r13+10h]; wchar_t **
0x18008b65f  cmp     [rcx], r15
0x18008b662  jnz     loc_18008B8E3
0x18008b668  lea     r9, [r14+30h]; struct CMemoryAllocator *
0x18008b66c  mov     rdx, rdi; struct _XML_TOKENIZATION_STATE *
0x18008b66f  lea     r8, [rbp+57h+var_A8]; struct _XML_EXTENT *
0x18008b673  call    ?DuplicateXmlString@@YAJPEAPEA_WPEAU_XML_TOKENIZATION_STATE@@PEAU_XML_EXTENT@@PEAVCMemoryAllocator@@@Z; DuplicateXmlString(wchar_t * *,_XML_TOKENIZATION_STATE *,_XML_EXTENT *,CMemoryAllocator *)
0x18008b678  mov     ebx, eax
0x18008b67a  test    eax, eax
0x18008b67c  jns     loc_18008B487
0x18008b682  mov     edx, 298h
0x18008b687  jmp     short loc_18008B6B5
0x18008b689  lea     rcx, [r13+8]; wchar_t **
0x18008b68d  cmp     [rcx], r15
0x18008b690  jnz     loc_18008B940
0x18008b696  lea     r9, [r14+30h]; struct CMemoryAllocator *
0x18008b69a  mov     rdx, rdi; struct _XML_TOKENIZATION_STATE *
0x18008b69d  lea     r8, [rbp+57h+var_A8]; struct _XML_EXTENT *
0x18008b6a1  call    ?DuplicateXmlString@@YAJPEAPEA_WPEAU_XML_TOKENIZATION_STATE@@PEAU_XML_EXTENT@@PEAVCMemoryAllocator@@@Z; DuplicateXmlString(wchar_t * *,_XML_TOKENIZATION_STATE *,_XML_EXTENT *,CMemoryAllocator *)
0x18008b6a6  mov     ebx, eax
0x18008b6a8  test    eax, eax
0x18008b6aa  jns     loc_18008B487
0x18008b6b0  mov     edx, 28Dh; void *
0x18008b6b5  mov     rcx, [rbp+5Fh]; this
0x18008b6b9  lea     r8, aOnecoreBaseCbs_131; "onecore\\base\\cbs\\parser\\update.cpp"
0x18008b6c0  mov     r9d, ebx; char *
0x18008b6c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b6c8  mov     eax, ebx
0x18008b6ca  jmp     loc_18008C72C
0x18008b6cf  lea     r8, [rbp+57h+var_A8]; struct _XML_TOKEN *
0x18008b6d3  lea     rdx, [rbp+57h+var_68]; struct _XML_TOKEN *
0x18008b6d7  call    ?GetValue@@YAJPEAU_XML_TOKENIZATION_STATE@@PEBU_XML_TOKEN@@PEAU2@@Z; GetValue(_XML_TOKENIZATION_STATE *,_XML_TOKEN const *,_XML_TOKEN *)
0x18008b6dc  mov     esi, eax
0x18008b6de  test    eax, eax
0x18008b6e0  js      loc_18008C66F
0x18008b6e6  lea     rax, [rbp+57h+var_D0]
0x18008b6ea  mov     [rsp+110h+var_E0], r13; struct COMMON_UPDATE_ATTRIBUTES_GROUP *
0x18008b6ef  mov     [rsp+110h+var_E8], rax; bool *
0x18008b6f4  lea     r9, [rbp+57h+var_A8]; struct _XML_TOKEN *
0x18008b6f8  lea     rax, [rbp+57h+var_CF]
0x18008b6fc  mov     rdx, r14; struct ParsingSession *
0x18008b6ff  lea     r8, [rbp+57h+var_68]; struct _XML_TOKEN *
0x18008b703  mov     [rsp+110h+var_F0], rax; bool *
0x18008b708  mov     rcx, rdi; struct _XML_TOKENIZATION_STATE *
0x18008b70b  call    ?ProcessCommonUpdateAttributesGroup@@YAJPEAU_XML_TOKENIZATION_STATE@@PEAUParsingSession@@PEBU_XML_TOKEN@@2PEA_N3PEAUCOMMON_UPDATE_ATTRIBUTES_GROUP@@@Z; ProcessCommonUpdateAttributesGroup(_XML_TOKENIZATION_STATE *,ParsingSession *,_XML_TOKEN const *,_XML_TOKEN const *,bool *,bool *,COMMON_UPDATE_ATTRIBUTES_GROUP *)
0x18008b710  mov     esi, eax
0x18008b712  test    eax, eax
0x18008b714  jns     loc_18008B487
0x18008b71a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b721  mov     dword ptr [rbp+57h+var_80], eax
0x18008b724  test    rcx, rcx
0x18008b727  jz      short loc_18008B768
0x18008b729  mov     ebx, 3
0x18008b72e  lea     r9, aInvalidUpdateA_0; "Invalid update attributes"
0x18008b735  mov     r8d, ebx
0x18008b738  xor     edx, edx
0x18008b73a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008b73f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b746  lea     rax, [rbp+57h+var_80]
0x18008b74a  mov     qword ptr [rbp+57h+var_C8], rax
0x18008b74e  lea     r9, asc_1802EE7AC; ": {}"
0x18008b755  lea     rax, [rbp+57h+var_C8]
0x18008b759  mov     r8d, ebx
0x18008b75c  mov     dl, 1
0x18008b75e  mov     [rsp+110h+var_F0], rax
0x18008b763  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008b768  mov     edx, 2BEh
0x18008b76d  jmp     loc_18008C717
0x18008b772  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b779  mov     [rbp+57h+var_78], esi
0x18008b77c  test    rcx, rcx
0x18008b77f  jz      short loc_18008B7C0
0x18008b781  mov     ebx, 3
0x18008b786  lea     r9, aFailedToExpect_0; "Failed to expect token"
0x18008b78d  mov     r8d, ebx
0x18008b790  xor     edx, edx
0x18008b792  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008b797  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b79e  lea     rax, [rbp+57h+var_78]
0x18008b7a2  mov     [rbp+57h+var_80], rax
0x18008b7a6  lea     r9, asc_1802EE7AC; ": {}"
0x18008b7ad  lea     rax, [rbp+57h+var_80]
0x18008b7b1  mov     r8d, ebx
0x18008b7b4  mov     dl, 1
0x18008b7b6  mov     [rsp+110h+var_F0], rax
  ... truncated ...
```
