# GetValue(_XML_TOKENIZATION_STATE *,_XML_TOKEN const *,_XML_TOKEN *)

- ea: `0x18007fc50`
- end: `0x180080a03`
- name: `?GetValue@@YAJPEAU_XML_TOKENIZATION_STATE@@PEBU_XML_TOKEN@@PEAU2@@Z`
- size: `3507`
- prototype: `__int64 __fastcall(struct _XML_TOKENIZATION_STATE *, const struct _XML_TOKEN *, struct _XML_TOKEN *)`
- caller_count: `39`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180054588`
- `0x180071fd8`
- `0x18007442c`
- `0x180074a70`
- `0x180075f50`
- `0x180076c74`
- `0x180078464`
- `0x180078c9c`
- `0x180079abc`
- `0x18007ace4`
- `0x18007b33c`
- `0x18007b6ac`
- `0x1800810fc`
- `0x180081aa4`
- `0x180082dc8`
- `0x180083264`
- `0x180083c88`
- `0x1800846f4`
- `0x180084eac`
- `0x180088ca8`
- `0x180089214`
- `0x1800898b8`
- `0x18008a278`
- `0x18008b2f4`
- `0x18008dd30`
- `0x1801fffb0`
- `0x180201154`
- `0x180201630`
- `0x180201f44`
- `0x180203adc`
- `0x1802047c4`
- `0x180204ec4`
- `0x1802059e0`
- `0x180206e40`
- `0x1802076dc`
- `0x1802084a0`
- `0x180208910`
- `0x180209e18`
- `0x18020a3ac`

## callees

- `0x18007c660`
- `0x18007fc50`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`

## string_xrefs

- `0x18007fe4d`: `Failed to expect token`
- `0x18007fed2`: `Failed to expect token`
- `0x18007ff56`: `Failed to expect token`
- `0x18007ffdf`: `Failed to expect token`
- `0x180080064`: `Failed to expect token`
- `0x1800800e9`: `Failed to expect token`
- `0x18008016d`: `Failed to expect token`
- `0x1800801f6`: `Failed to expect token`
- `0x18008027b`: `Failed to expect token`
- `0x180080300`: `Failed to expect token`
- `0x180080385`: `Failed to expect token`
- `0x18008040a`: `Failed to expect token`
- `0x18008048e`: `Failed to expect token`
- `0x180080517`: `Failed to expect token`
- `0x18008059c`: `Failed to expect token`
- `0x180080621`: `Failed to expect token`
- `0x1800806a5`: `Failed to expect token`
- `0x18008072e`: `Failed to expect token`
- `0x1800807b3`: `Failed to expect token`
- `0x180080838`: `Failed to expect token`
- `0x1800808bc`: `Failed to expect token`
- `0x180080941`: `Failed to expect token`
- `0x18007fcd6`: `onecore\base\cbs\parser\token.cpp`
- `0x18007fd51`: `onecore\base\cbs\parser\token.cpp`
- `0x18007fdce`: `onecore\base\cbs\parser\token.cpp`
- `0x18007fe91`: `onecore\base\cbs\parser\token.cpp`
- `0x18007ff16`: `onecore\base\cbs\parser\token.cpp`
- `0x18007ff9a`: `onecore\base\cbs\parser\token.cpp`
- `0x180080023`: `onecore\base\cbs\parser\token.cpp`
- `0x1800800a8`: `onecore\base\cbs\parser\token.cpp`
- `0x18008012d`: `onecore\base\cbs\parser\token.cpp`
- `0x1800801b1`: `onecore\base\cbs\parser\token.cpp`
- `0x18008023a`: `onecore\base\cbs\parser\token.cpp`
- `0x1800802bf`: `onecore\base\cbs\parser\token.cpp`
- `0x180080344`: `onecore\base\cbs\parser\token.cpp`
- `0x1800803c9`: `onecore\base\cbs\parser\token.cpp`
- `0x18008044e`: `onecore\base\cbs\parser\token.cpp`
- `0x1800804d2`: `onecore\base\cbs\parser\token.cpp`
- `0x18008055b`: `onecore\base\cbs\parser\token.cpp`
- `0x1800805e0`: `onecore\base\cbs\parser\token.cpp`
- `0x180080665`: `onecore\base\cbs\parser\token.cpp`
- `0x1800806e9`: `onecore\base\cbs\parser\token.cpp`
- `0x180080772`: `onecore\base\cbs\parser\token.cpp`
- `0x1800807f7`: `onecore\base\cbs\parser\token.cpp`
- `0x18008087c`: `onecore\base\cbs\parser\token.cpp`
- `0x180080900`: `onecore\base\cbs\parser\token.cpp`
- `0x180080985`: `onecore\base\cbs\parser\token.cpp`
- `0x18007fd0f`: `No current token specified`
- `0x18007fd8a`: `No value token result specified`

## pseudocode

```c
__int64 __fastcall GetValue(struct _XML_TOKENIZATION_STATE *a1, const struct _XML_TOKEN *a2, struct _XML_TOKEN *a3)
{
  int v5; // edx
  __int64 result; // rax
  int v7; // edx
  int v8; // edx
  int v9; // eax
  unsigned int v10; // esi
  int v11; // edx
  int v12; // eax
  unsigned int v13; // esi
  int v14; // edx
  int v15; // eax
  unsigned int v16; // edi
  int v17; // edx
  int v18; // eax
  unsigned int v19; // ebx
  int v20; // edx
  int v21; // eax
  unsigned int v22; // esi
  int v23; // edx
  int v24; // eax
  unsigned int v25; // esi
  int v26; // edx
  int v27; // eax
  unsigned int v28; // edi
  int v29; // edx
  int v30; // eax
  unsigned int v31; // ebx
  int v32; // edx
  int v33; // eax
  unsigned int v34; // esi
  int v35; // edx
  int v36; // eax
  unsigned int v37; // esi
  int v38; // edx
  int v39; // eax
  unsigned int v40; // esi
  int v41; // edx
  int v42; // eax
  unsigned int v43; // esi
  int v44; // edx
  int v45; // eax
  unsigned int v46; // edi
  int v47; // edx
  int v48; // eax
  unsigned int v49; // ebx
  int v50; // edx
  int v51; // eax
  unsigned int v52; // esi
  int v53; // edx
  int v54; // eax
  unsigned int v55; // esi
  int v56; // edx
  int v57; // eax
  unsigned int v58; // edi
  int v59; // edx
  int v60; // eax
  unsigned int v61; // ebx
  int v62; // edx
  int v63; // eax
  unsigned int v64; // esi
  int v65; // edx
  int v66; // eax
  unsigned int v67; // esi
  int v68; // edx
  int v69; // eax
  unsigned int v70; // edi
  int v71; // edx
  int v72; // eax
  unsigned int v73; // ebx
  int v74; // edx
  int v75; // [rsp+20h] [rbp-50h]
  int v76[2]; // [rsp+30h] [rbp-40h] BYREF
  int v77; // [rsp+38h] [rbp-38h] BYREF
  _OWORD v78[2]; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  memset(v78, 0, sizeof(v78));
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a3 )
      {
        switch ( *((_DWORD *)a2 + 6) )
        {
          case 7:
            v33 = ExpectToken(a1, 10, v78);
            v34 = v33;
            if ( v33 >= 0 )
            {
              v36 = ExpectToken(a1, 9, v78);
              v37 = v36;
              if ( v36 >= 0 )
              {
                v39 = ExpectToken(a1, 11, v78);
                v40 = v39;
                if ( v39 >= 0 )
                {
                  v42 = ExpectToken(a1, 12, v78);
                  v43 = v42;
                  if ( v42 >= 0 )
                  {
                    v45 = ExpectToken(a1, 14, a3);
                    v46 = v45;
                    if ( v45 >= 0 )
                    {
                      v48 = ExpectToken(a1, 13, v78);
                      v49 = v48;
                      if ( v48 >= 0 )
                        goto LABEL_102;
                      v77 = v48;
                      if ( LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                        *(_QWORD *)v76 = &v77;
                        LOBYTE(v50) = 1;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          (_DWORD)LogAdapter::g_Logger,
                          v50,
                          3,
                          (unsigned int)": {}",
                          (__int64)v76);
                      }
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x2E7,
                        (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                        (const char *)v49,
                        v75);
                      result = v49;
                    }
                    else
                    {
                      v77 = v45;
                      if ( LogAdapter::g_Logger )
                      {
                        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                        *(_QWORD *)v76 = &v77;
                        LOBYTE(v47) = 1;
                        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                          (_DWORD)LogAdapter::g_Logger,
                          v47,
                          3,
                          (unsigned int)": {}",
                          (__int64)v76);
                      }
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x2E6,
                        (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                        (const char *)v46,
                        v75);
                      result = v46;
                    }
                  }
                  else
                  {
                    v77 = v42;
                    if ( LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                      *(_QWORD *)v76 = &v77;
                      LOBYTE(v44) = 1;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        (_DWORD)LogAdapter::g_Logger,
                        v44,
                        3,
                        (unsigned int)": {}",
                        (__int64)v76);
                    }
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x2E5,
                      (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                      (const char *)v43,
                      v75);
                    result = v43;
                  }
                }
                else
                {
                  v77 = v39;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                    *(_QWORD *)v76 = &v77;
                    LOBYTE(v41) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v41,
                      3,
                      (unsigned int)": {}",
                      (__int64)v76);
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2E4,
                    (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                    (const char *)v40,
                    v75);
                  result = v40;
                }
              }
              else
              {
                v77 = v36;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                  *(_QWORD *)v76 = &v77;
                  LOBYTE(v38) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v38,
                    3,
                    (unsigned int)": {}",
                    (__int64)v76);
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2E3,
                  (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                  (const char *)v37,
                  v75);
                result = v37;
              }
            }
            else
            {
              v77 = v33;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                *(_QWORD *)v76 = &v77;
                LOBYTE(v35) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v35,
                  3,
                  (unsigned int)": {}",
                  (__int64)v76);
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2E2,
                (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                (const char *)v34,
                v75);
              result = v34;
            }
            break;
          case 8:
            v21 = ExpectToken(a1, 11, v78);
            v22 = v21;
            if ( v21 >= 0 )
            {
              v24 = ExpectToken(a1, 12, v78);
              v25 = v24;
              if ( v24 >= 0 )
              {
                v27 = ExpectToken(a1, 14, a3);
                v28 = v27;
                if ( v27 >= 0 )
                {
                  v30 = ExpectToken(a1, 13, v78);
                  v31 = v30;
                  if ( v30 >= 0 )
                    goto LABEL_102;
                  v77 = v30;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                    *(_QWORD *)v76 = &v77;
                    LOBYTE(v32) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v32,
                      3,
                      (unsigned int)": {}",
                      (__int64)v76);
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2DD,
                    (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                    (const char *)v31,
                    v75);
                  result = v31;
                }
                else
                {
                  v77 = v27;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                    *(_QWORD *)v76 = &v77;
                    LOBYTE(v29) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v29,
                      3,
                      (unsigned int)": {}",
                      (__int64)v76);
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2DC,
                    (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                    (const char *)v28,
                    v75);
                  result = v28;
                }
              }
              else
              {
                v77 = v24;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                  *(_QWORD *)v76 = &v77;
                  LOBYTE(v26) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v26,
                    3,
                    (unsigned int)": {}",
                    (__int64)v76);
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2DB,
                  (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                  (const char *)v25,
                  v75);
                result = v25;
              }
            }
            else
            {
              v77 = v21;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                *(_QWORD *)v76 = &v77;
                LOBYTE(v23) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v23,
                  3,
                  (unsigned int)": {}",
                  (__int64)v76);
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2DA,
                (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                (const char *)v22,
                v75);
              result = v22;
            }
            break;
          case 0x1C:
            v51 = ExpectToken(a1, 29, v78);
            v52 = v51;
            if ( v51 >= 0 )
            {
              v54 = ExpectToken(a1, 31, v78);
              v55 = v54;
              if ( v54 >= 0 )
              {
                v57 = ExpectToken(a1, 30, a3);
                v58 = v57;
                if ( v57 >= 0 )
                {
                  v60 = ExpectToken(a1, 32, v78);
                  v61 = v60;
                  if ( v60 >= 0 )
                    goto LABEL_102;
                  v77 = v60;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                    *(_QWORD *)v76 = &v77;
                    LOBYTE(v62) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v62,
                      3,
                      (unsigned int)": {}",
                      (__int64)v76);
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2EE,
                    (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                    (const char *)v61,
                    v75);
                  result = v61;
                }
                else
                {
                  v77 = v57;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                    *(_QWORD *)v76 = &v77;
                    LOBYTE(v59) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v59,
                      3,
                      (unsigned int)": {}",
                      (__int64)v76);
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2ED,
                    (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                    (const char *)v58,
                    v75);
                  result = v58;
                }
              }
              else
              {
                v77 = v54;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                  *(_QWORD *)v76 = &v77;
                  LOBYTE(v56) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v56,
                    3,
                    (unsigned int)": {}",
                    (__int64)v76);
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2EC,
                  (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                  (const char *)v55,
                  v75);
                result = v55;
              }
            }
            else
            {
              v77 = v51;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                *(_QWORD *)v76 = &v77;
                LOBYTE(v53) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v53,
                  3,
                  (unsigned int)": {}",
                  (__int64)v76);
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2EB,
                (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                (const char *)v52,
                v75);
              result = v52;
            }
            break;
          case 0x37:
          case 0x38:
          case 0x39:
            v9 = ExpectToken(a1, 54, v78);
            v10 = v9;
            if ( v9 >= 0 )
            {
              v12 = ExpectToken(a1, 58, v78);
              v13 = v12;
              if ( v12 >= 0 )
              {
                v15 = ExpectToken(a1, 59, a3);
                v16 = v15;
                if ( v15 >= 0 )
                {
                  v18 = ExpectToken(a1, 60, v78);
                  v19 = v18;
                  if ( v18 >= 0 )
                    goto LABEL_102;
                  v77 = v18;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                    *(_QWORD *)v76 = &v77;
                    LOBYTE(v20) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v20,
                      3,
                      (unsigned int)": {}",
                      (__int64)v76);
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2D6,
                    (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                    (const char *)v19,
                    v75);
                  result = v19;
                }
                else
                {
                  v77 = v15;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                    *(_QWORD *)v76 = &v77;
                    LOBYTE(v17) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v17,
                      3,
                      (unsigned int)": {}",
                      (__int64)v76);
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2D5,
                    (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                    (const char *)v16,
                    v75);
                  result = v16;
                }
              }
              else
              {
                v77 = v12;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                  *(_QWORD *)v76 = &v77;
                  LOBYTE(v14) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v14,
                    3,
                    (unsigned int)": {}",
                    (__int64)v76);
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2D4,
                  (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                  (const char *)v13,
                  v75);
                result = v13;
              }
            }
            else
            {
              v77 = v9;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                *(_QWORD *)v76 = &v77;
                LOBYTE(v11) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v11,
                  3,
                  (unsigned int)": {}",
                  (__int64)v76);
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2D3,
                (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                (const char *)v10,
                v75);
              result = v10;
            }
            break;
          default:
            v63 = ExpectToken(a1, 54, v78);
            v64 = v63;
            if ( v63 >= 0 )
            {
              v66 = ExpectToken(a1, 58, v78);
              v67 = v66;
              if ( v66 >= 0 )
              {
                v69 = ExpectToken(a1, 59, a3);
                v70 = v69;
                if ( v69 >= 0 )
                {
                  v72 = ExpectToken(a1, 60, v78);
                  v73 = v72;
                  if ( v72 >= 0 )
                  {
LABEL_102:
                    result = 0;
                  }
                  else
                  {
                    v77 = v72;
                    if ( LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                      *(_QWORD *)v76 = &v77;
                      LOBYTE(v74) = 1;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                        (_DWORD)LogAdapter::g_Logger,
                        v74,
                        3,
                        (unsigned int)": {}",
                        (__int64)v76);
                    }
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x2F5,
                      (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                      (const char *)v73,
                      v75);
                    result = v73;
                  }
                }
                else
                {
                  v77 = v69;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                    *(_QWORD *)v76 = &v77;
                    LOBYTE(v71) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v71,
                      3,
                      (unsigned int)": {}",
                      (__int64)v76);
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2F4,
                    (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                    (const char *)v70,
                    v75);
                  result = v70;
                }
              }
              else
              {
                v77 = v66;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                  *(_QWORD *)v76 = &v77;
                  LOBYTE(v68) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v68,
                    3,
                    (unsigned int)": {}",
                    (__int64)v76);
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2F3,
                  (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                  (const char *)v67,
                  v75);
                result = v67;
              }
            }
            else
            {
              v77 = v63;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to expect token");
                *(_QWORD *)v76 = &v77;
                LOBYTE(v65) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v65,
                  3,
                  (unsigned int)": {}",
                  (__int64)v76);
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2F2,
                (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                (const char *)v64,
                v75);
              result = v64;
            }
            break;
        }
      }
      else
      {
        v77 = -2147467261;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No value token result specified");
          *(_QWORD *)v76 = &v77;
          LOBYTE(v8) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v8,
            3,
            (unsigned int)": {}",
            (__int64)v76);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2CC,
          (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
          (const char *)0x80004003LL,
          v75);
        return 2147500035LL;
      }
    }
    else
    {
      v77 = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No current token specified");
        *(_QWORD *)v76 = &v77;
        LOBYTE(v7) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v7,
          3,
          (unsigned int)": {}",
          (__int64)v76);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2CB,
        (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
        (const char *)0x80070057LL,
        v75);
      return 2147942487LL;
    }
  }
  else
  {
    v77 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No state specified");
      *(_QWORD *)v76 = &v77;
      LOBYTE(v5) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v5,
        3,
        (unsigned int)": {}",
        (__int64)v76);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CA,
      (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
      (const char *)0x80070057LL,
      v75);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x18007fc50  push    rbp
0x18007fc52  push    rbx
0x18007fc53  push    rdi
0x18007fc54  mov     rbp, rsp
0x18007fc57  sub     rsp, 70h
0x18007fc5b  mov     rax, cs:__security_cookie
0x18007fc62  xor     rax, rsp
0x18007fc65  mov     [rbp+var_10], rax
0x18007fc69  xorps   xmm0, xmm0
0x18007fc6c  mov     rdi, r8
0x18007fc6f  mov     rbx, rcx
0x18007fc72  movups  [rbp+var_30], xmm0
0x18007fc76  movups  [rbp+var_20], xmm0
0x18007fc7a  test    rcx, rcx
0x18007fc7d  jnz     short loc_18007FCF7
0x18007fc7f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007fc86  mov     [rbp+var_38], 80070057h
0x18007fc8d  test    rcx, rcx
0x18007fc90  jz      short loc_18007FCD2
0x18007fc92  lea     r9, aNoStateSpecifi_0; "No state specified"
0x18007fc99  xor     edx, edx
0x18007fc9b  mov     r8d, 3
0x18007fca1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007fca6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007fcad  lea     rax, [rbp+var_38]
0x18007fcb1  mov     qword ptr [rbp+var_40], rax
0x18007fcb5  lea     r9, asc_1802EE7AC; ": {}"
0x18007fcbc  lea     rax, [rbp+var_40]
0x18007fcc0  mov     r8d, 3
0x18007fcc6  mov     dl, 1
0x18007fcc8  mov     qword ptr [rsp+70h+var_50], rax; int
0x18007fccd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18007fcd2  mov     rcx, [rbp+18h]; this
0x18007fcd6  lea     r8, aOnecoreBaseCbs_62; "onecore\\base\\cbs\\parser\\token.cpp"
0x18007fcdd  mov     r9d, 80070057h; char *
0x18007fce3  mov     edx, 2CAh; void *
0x18007fce8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007fced  mov     eax, 80070057h
0x18007fcf2  jmp     loc_1800809A7
0x18007fcf7  test    rdx, rdx
0x18007fcfa  jnz     short loc_18007FD72
0x18007fcfc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007fd03  mov     [rbp+var_38], 80070057h
0x18007fd0a  test    rcx, rcx
0x18007fd0d  jz      short loc_18007FD4D
0x18007fd0f  lea     r9, aNoCurrentToken; "No current token specified"
0x18007fd16  mov     r8d, 3
0x18007fd1c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007fd21  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007fd28  lea     rax, [rbp+var_38]
0x18007fd2c  mov     qword ptr [rbp+var_40], rax
0x18007fd30  lea     r9, asc_1802EE7AC; ": {}"
0x18007fd37  lea     rax, [rbp+var_40]
0x18007fd3b  mov     r8d, 3
0x18007fd41  mov     dl, 1
0x18007fd43  mov     qword ptr [rsp+70h+var_50], rax; int
0x18007fd48  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18007fd4d  mov     rcx, [rbp+18h]; this
0x18007fd51  lea     r8, aOnecoreBaseCbs_62; "onecore\\base\\cbs\\parser\\token.cpp"
0x18007fd58  mov     r9d, 80070057h; char *
0x18007fd5e  mov     edx, 2CBh; void *
0x18007fd63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007fd68  mov     eax, 80070057h
0x18007fd6d  jmp     loc_1800809A7
0x18007fd72  test    rdi, rdi
0x18007fd75  jnz     short loc_18007FDEF
0x18007fd77  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007fd7e  mov     [rbp+var_38], 80004003h
0x18007fd85  test    rcx, rcx
0x18007fd88  jz      short loc_18007FDCA
0x18007fd8a  lea     r9, aNoValueTokenRe; "No value token result specified"
0x18007fd91  xor     edx, edx
0x18007fd93  mov     r8d, 3
0x18007fd99  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007fd9e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007fda5  lea     rax, [rbp+var_38]
0x18007fda9  mov     qword ptr [rbp+var_40], rax
0x18007fdad  lea     r9, asc_1802EE7AC; ": {}"
0x18007fdb4  lea     rax, [rbp+var_40]
0x18007fdb8  mov     r8d, 3
0x18007fdbe  mov     dl, 1
0x18007fdc0  mov     qword ptr [rsp+70h+var_50], rax; int
0x18007fdc5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18007fdca  mov     rcx, [rbp+18h]; this
0x18007fdce  lea     r8, aOnecoreBaseCbs_62; "onecore\\base\\cbs\\parser\\token.cpp"
0x18007fdd5  mov     r9d, 80004003h; char *
0x18007fddb  mov     edx, 2CCh; void *
0x18007fde0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007fde5  mov     eax, 80004003h
0x18007fdea  jmp     loc_1800809A7
0x18007fdef  mov     eax, [rdx+18h]
0x18007fdf2  add     eax, 0FFFFFFF9h; switch 51 cases
0x18007fdf5  mov     [rsp+70h+arg_8], rsi
0x18007fdfd  cmp     eax, 32h
0x18007fe00  ja      def_18007FE21; jumptable 000000018007FE21 default case, cases 9-27,29-54
0x18007fe06  lea     rdx, __ImageBase
0x18007fe0d  cdqe
0x18007fe0f  movzx   eax, ds:(byte_1800809D0 - 180000000h)[rdx+rax]
0x18007fe17  mov     ecx, ds:(jpt_18007FE21 - 180000000h)[rdx+rax*4]
0x18007fe1e  add     rcx, rdx
0x18007fe21  jmp     rcx; switch jump
0x18007fe27  lea     r8, [rbp+var_30]; jumptable 000000018007FE21 cases 55-57
0x18007fe2b  mov     edx, 36h ; '6'
0x18007fe30  mov     rcx, rbx
0x18007fe33  call    ?ExpectToken@@YAJPEAU_XML_TOKENIZATION_STATE@@W4XML_TOKENIZATION_SPECIFIC_STATE@@PEAU_XML_TOKEN@@@Z; ExpectToken(_XML_TOKENIZATION_STATE *,XML_TOKENIZATION_SPECIFIC_STATE,_XML_TOKEN *)
0x18007fe38  mov     esi, eax
0x18007fe3a  test    eax, eax
0x18007fe3c  jns     short loc_18007FEAC
0x18007fe3e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007fe45  mov     [rbp+var_38], eax
0x18007fe48  test    rcx, rcx
0x18007fe4b  jz      short loc_18007FE8D
0x18007fe4d  lea     r9, aFailedToExpect_0; "Failed to expect token"
0x18007fe54  xor     edx, edx
0x18007fe56  mov     r8d, 3
0x18007fe5c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007fe61  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007fe68  lea     rax, [rbp+var_38]
0x18007fe6c  mov     qword ptr [rbp+var_40], rax
0x18007fe70  lea     r9, asc_1802EE7AC; ": {}"
0x18007fe77  lea     rax, [rbp+var_40]
0x18007fe7b  mov     r8d, 3
0x18007fe81  mov     dl, 1
0x18007fe83  mov     qword ptr [rsp+70h+var_50], rax; int
0x18007fe88  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18007fe8d  mov     rcx, [rbp+18h]; this
0x18007fe91  lea     r8, aOnecoreBaseCbs_62; "onecore\\base\\cbs\\parser\\token.cpp"
0x18007fe98  mov     r9d, esi; char *
0x18007fe9b  mov     edx, 2D3h; void *
0x18007fea0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007fea5  mov     eax, esi
0x18007fea7  jmp     loc_18008099F
0x18007feac  lea     r8, [rbp+var_30]
0x18007feb0  mov     edx, 3Ah ; ':'
0x18007feb5  mov     rcx, rbx
0x18007feb8  call    ?ExpectToken@@YAJPEAU_XML_TOKENIZATION_STATE@@W4XML_TOKENIZATION_SPECIFIC_STATE@@PEAU_XML_TOKEN@@@Z; ExpectToken(_XML_TOKENIZATION_STATE *,XML_TOKENIZATION_SPECIFIC_STATE,_XML_TOKEN *)
0x18007febd  mov     esi, eax
0x18007febf  test    eax, eax
0x18007fec1  jns     short loc_18007FF31
0x18007fec3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007feca  mov     [rbp+var_38], eax
0x18007fecd  test    rcx, rcx
0x18007fed0  jz      short loc_18007FF12
0x18007fed2  lea     r9, aFailedToExpect_0; "Failed to expect token"
0x18007fed9  xor     edx, edx
0x18007fedb  mov     r8d, 3
0x18007fee1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007fee6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007feed  lea     rax, [rbp+var_38]
0x18007fef1  mov     qword ptr [rbp+var_40], rax
0x18007fef5  lea     r9, asc_1802EE7AC; ": {}"
0x18007fefc  lea     rax, [rbp+var_40]
0x18007ff00  mov     r8d, 3
0x18007ff06  mov     dl, 1
0x18007ff08  mov     qword ptr [rsp+70h+var_50], rax; int
0x18007ff0d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18007ff12  mov     rcx, [rbp+18h]; this
0x18007ff16  lea     r8, aOnecoreBaseCbs_62; "onecore\\base\\cbs\\parser\\token.cpp"
0x18007ff1d  mov     r9d, esi; char *
0x18007ff20  mov     edx, 2D4h; void *
0x18007ff25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ff2a  mov     eax, esi
0x18007ff2c  jmp     loc_18008099F
0x18007ff31  mov     r8, rdi
0x18007ff34  mov     edx, 3Bh ; ';'
0x18007ff39  mov     rcx, rbx
0x18007ff3c  call    ?ExpectToken@@YAJPEAU_XML_TOKENIZATION_STATE@@W4XML_TOKENIZATION_SPECIFIC_STATE@@PEAU_XML_TOKEN@@@Z; ExpectToken(_XML_TOKENIZATION_STATE *,XML_TOKENIZATION_SPECIFIC_STATE,_XML_TOKEN *)
0x18007ff41  mov     edi, eax
0x18007ff43  test    eax, eax
0x18007ff45  jns     short loc_18007FFB5
0x18007ff47  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007ff4e  mov     [rbp+var_38], eax
0x18007ff51  test    rcx, rcx
0x18007ff54  jz      short loc_18007FF96
0x18007ff56  lea     r9, aFailedToExpect_0; "Failed to expect token"
0x18007ff5d  xor     edx, edx
0x18007ff5f  mov     r8d, 3
0x18007ff65  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007ff6a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007ff71  lea     rax, [rbp+var_38]
0x18007ff75  mov     qword ptr [rbp+var_40], rax
0x18007ff79  lea     r9, asc_1802EE7AC; ": {}"
0x18007ff80  lea     rax, [rbp+var_40]
0x18007ff84  mov     r8d, 3
0x18007ff8a  mov     dl, 1
0x18007ff8c  mov     qword ptr [rsp+70h+var_50], rax; int
0x18007ff91  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18007ff96  mov     rcx, [rbp+18h]; this
0x18007ff9a  lea     r8, aOnecoreBaseCbs_62; "onecore\\base\\cbs\\parser\\token.cpp"
0x18007ffa1  mov     r9d, edi; char *
0x18007ffa4  mov     edx, 2D5h; void *
0x18007ffa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ffae  mov     eax, edi
0x18007ffb0  jmp     loc_18008099F
0x18007ffb5  lea     r8, [rbp+var_30]
0x18007ffb9  mov     edx, 3Ch ; '<'
0x18007ffbe  mov     rcx, rbx
0x18007ffc1  call    ?ExpectToken@@YAJPEAU_XML_TOKENIZATION_STATE@@W4XML_TOKENIZATION_SPECIFIC_STATE@@PEAU_XML_TOKEN@@@Z; ExpectToken(_XML_TOKENIZATION_STATE *,XML_TOKENIZATION_SPECIFIC_STATE,_XML_TOKEN *)
0x18007ffc6  mov     ebx, eax
0x18007ffc8  test    eax, eax
0x18007ffca  jns     loc_18008099D
0x18007ffd0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007ffd7  mov     [rbp+var_38], eax
0x18007ffda  test    rcx, rcx
0x18007ffdd  jz      short loc_18008001F
0x18007ffdf  lea     r9, aFailedToExpect_0; "Failed to expect token"
0x18007ffe6  xor     edx, edx
0x18007ffe8  mov     r8d, 3
0x18007ffee  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007fff3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007fffa  lea     rax, [rbp+var_38]
0x18007fffe  mov     qword ptr [rbp+var_40], rax
0x180080002  lea     r9, asc_1802EE7AC; ": {}"
0x180080009  lea     rax, [rbp+var_40]
0x18008000d  mov     r8d, 3
0x180080013  mov     dl, 1
0x180080015  mov     qword ptr [rsp+70h+var_50], rax; int
0x18008001a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008001f  mov     rcx, [rbp+18h]; this
0x180080023  lea     r8, aOnecoreBaseCbs_62; "onecore\\base\\cbs\\parser\\token.cpp"
0x18008002a  mov     r9d, ebx; char *
0x18008002d  mov     edx, 2D6h; void *
0x180080032  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080037  mov     eax, ebx
0x180080039  jmp     loc_18008099F
0x18008003e  lea     r8, [rbp+var_30]; jumptable 000000018007FE21 case 8
0x180080042  mov     edx, 0Bh
0x180080047  mov     rcx, rbx
0x18008004a  call    ?ExpectToken@@YAJPEAU_XML_TOKENIZATION_STATE@@W4XML_TOKENIZATION_SPECIFIC_STATE@@PEAU_XML_TOKEN@@@Z; ExpectToken(_XML_TOKENIZATION_STATE *,XML_TOKENIZATION_SPECIFIC_STATE,_XML_TOKEN *)
0x18008004f  mov     esi, eax
0x180080051  test    eax, eax
0x180080053  jns     short loc_1800800C3
0x180080055  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008005c  mov     [rbp+var_38], eax
0x18008005f  test    rcx, rcx
0x180080062  jz      short loc_1800800A4
0x180080064  lea     r9, aFailedToExpect_0; "Failed to expect token"
0x18008006b  xor     edx, edx
0x18008006d  mov     r8d, 3
0x180080073  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180080078  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008007f  lea     rax, [rbp+var_38]
0x180080083  mov     qword ptr [rbp+var_40], rax
0x180080087  lea     r9, asc_1802EE7AC; ": {}"
0x18008008e  lea     rax, [rbp+var_40]
0x180080092  mov     r8d, 3
0x180080098  mov     dl, 1
0x18008009a  mov     qword ptr [rsp+70h+var_50], rax; int
0x18008009f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800800a4  mov     rcx, [rbp+18h]; this
0x1800800a8  lea     r8, aOnecoreBaseCbs_62; "onecore\\base\\cbs\\parser\\token.cpp"
0x1800800af  mov     r9d, esi; char *
0x1800800b2  mov     edx, 2DAh; void *
0x1800800b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800800bc  mov     eax, esi
0x1800800be  jmp     loc_18008099F
0x1800800c3  lea     r8, [rbp+var_30]
0x1800800c7  mov     edx, 0Ch
0x1800800cc  mov     rcx, rbx
0x1800800cf  call    ?ExpectToken@@YAJPEAU_XML_TOKENIZATION_STATE@@W4XML_TOKENIZATION_SPECIFIC_STATE@@PEAU_XML_TOKEN@@@Z; ExpectToken(_XML_TOKENIZATION_STATE *,XML_TOKENIZATION_SPECIFIC_STATE,_XML_TOKEN *)
0x1800800d4  mov     esi, eax
0x1800800d6  test    eax, eax
0x1800800d8  jns     short loc_180080148
0x1800800da  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800800e1  mov     [rbp+var_38], eax
0x1800800e4  test    rcx, rcx
0x1800800e7  jz      short loc_180080129
0x1800800e9  lea     r9, aFailedToExpect_0; "Failed to expect token"
0x1800800f0  xor     edx, edx
0x1800800f2  mov     r8d, 3
0x1800800f8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800800fd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180080104  lea     rax, [rbp+var_38]
0x180080108  mov     qword ptr [rbp+var_40], rax
0x18008010c  lea     r9, asc_1802EE7AC; ": {}"
0x180080113  lea     rax, [rbp+var_40]
0x180080117  mov     r8d, 3
0x18008011d  mov     dl, 1
0x18008011f  mov     qword ptr [rsp+70h+var_50], rax; int
0x180080124  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180080129  mov     rcx, [rbp+18h]; this
0x18008012d  lea     r8, aOnecoreBaseCbs_62; "onecore\\base\\cbs\\parser\\token.cpp"
0x180080134  mov     r9d, esi; char *
0x180080137  mov     edx, 2DBh; void *
0x18008013c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080141  mov     eax, esi
0x180080143  jmp     loc_18008099F
0x180080148  mov     r8, rdi
0x18008014b  mov     edx, 0Eh
0x180080150  mov     rcx, rbx
0x180080153  call    ?ExpectToken@@YAJPEAU_XML_TOKENIZATION_STATE@@W4XML_TOKENIZATION_SPECIFIC_STATE@@PEAU_XML_TOKEN@@@Z; ExpectToken(_XML_TOKENIZATION_STATE *,XML_TOKENIZATION_SPECIFIC_STATE,_XML_TOKEN *)
0x180080158  mov     edi, eax
0x18008015a  test    eax, eax
0x18008015c  jns     short loc_1800801CC
0x18008015e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180080165  mov     [rbp+var_38], eax
0x180080168  test    rcx, rcx
0x18008016b  jz      short loc_1800801AD
0x18008016d  lea     r9, aFailedToExpect_0; "Failed to expect token"
0x180080174  xor     edx, edx
  ... truncated ...
```
