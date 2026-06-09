# CDODownloadExt::SetProperty(_DODownloadProperty,tagVARIANT const *)

- ea: `0x18000fba0`
- end: `0x1800105ae`
- name: `?SetProperty@CDODownloadExt@@UEAAJW4_DODownloadProperty@@PEBUtagVARIANT@@@Z`
- size: `2574`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180008618`
- `0x18000933c`
- `0x1800095a0`
- `0x18000a4fc`
- `0x18000bd54`
- `0x18000e9a8`
- `0x18000ecf0`
- `0x18000ef98`
- `0x18000f2b4`
- `0x18000f54c`
- `0x18000fba0`
- `0x18001cc3c`
- `0x180089e64`
- `0x18008c458`
- `0x18008c634`
- `0x18008ce48`
- `0x18008cef0`
- `0x18008fbd4`
- `0x1800a1ea4`
- `0x1800a98f8`
- `0x1800f82f0`
- `0x1800f8320`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fc93`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ffe2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fc93`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ffe2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fc54`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ffa3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fc54`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ffa3`
- `CRYPT32!CertFreeCertificateContext` at `0x180010214`
- `CRYPT32!CertFreeCertificateContext` at `0x180010251`
- `CRYPT32!CertFreeCertificateContext` at `0x180010214`
- `CRYPT32!CertFreeCertificateContext` at `0x180010251`
- `CRYPT32!CertAddSerializedElementToStore` at `0x1800101e5`
- `CRYPT32!CertAddSerializedElementToStore` at `0x1800101e5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18001013a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18001013a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800100f1`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800100f1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800100ae`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800100ae`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001011d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180010166`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800101aa`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001021d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001025a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001011d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180010166`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800101aa`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001021d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001025a`

## string_xrefs

- `0x18000fbe5`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x18000fc2c`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x18000fd82`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x18000fe44`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x18000ff4d`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x180010025`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x1800100c5`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x180010109`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x180010152`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x180010196`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x1800101f7`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x1800102be`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x1800103d5`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x1800104e3`: `C:\__w\1\s\src\DeliveryOptimization\dll\ExternalJob.cpp`
- `0x18001007d`: `Job %s, SecurityContext set`
- `0x180010272`: `Job %s, SecurityContext cleared`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CDODownloadExt::SetProperty(__int64 a1, unsigned int a2, __int16 *a3)
{
  __int64 result; // rax
  const char *v7; // r9
  struct IUnknown *v8; // r14
  __int64 v9; // rcx
  const struct _GUID *v10; // r15
  volatile signed __int32 *v11; // rdi
  CBackgroundCopyJob *v12; // rcx
  int v13; // r12d
  IUnknown *v14; // r14
  __m128i si128; // xmm1
  volatile signed __int32 *v16; // rdi
  CBackgroundCopyJob *v17; // rcx
  int v18; // r12d
  __int64 v19; // rcx
  __int16 v20; // di
  SAFEARRAY *v21; // rdi
  HRESULT v22; // eax
  unsigned int v23; // ebx
  HRESULT LBound; // eax
  unsigned int v25; // r14d
  HRESULT UBound; // eax
  unsigned int v27; // r14d
  signed int v28; // r8d
  const char *v29; // r9
  unsigned int LastError; // ebx
  __int64 v31; // rdx
  __int64 v32; // r8
  __int128 *v33; // rax
  __int128 *v34; // r8
  unsigned __int64 v35; // r9
  __int64 v36; // r10
  __int128 *v37; // rax
  __int128 *v38; // rcx
  __int128 *v39; // rdx
  CBackgroundCopyJob *v40; // rdi
  unsigned int v41; // eax
  int v42; // eax
  unsigned int v43; // esi
  volatile signed __int32 *v44; // rdi
  volatile signed __int32 *v45; // rdi
  CBackgroundCopyJob *v46; // rbx
  unsigned int v47; // eax
  int v48; // eax
  unsigned int v49; // esi
  volatile signed __int32 *v50; // rdi
  int dwFlags; // [rsp+20h] [rbp-F8h]
  int dwFlagsa; // [rsp+20h] [rbp-F8h]
  LONG plLbound[4]; // [rsp+40h] [rbp-D8h] BYREF
  __m128i v54; // [rsp+50h] [rbp-C8h] BYREF
  LONG plUbound; // [rsp+60h] [rbp-B8h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+68h] [rbp-B0h] BYREF
  __int128 v57; // [rsp+70h] [rbp-A8h] BYREF
  __int64 v58; // [rsp+80h] [rbp-98h]
  unsigned __int64 v59; // [rsp+88h] [rbp-90h]
  void *ppvData[2]; // [rsp+90h] [rbp-88h] BYREF
  char v61[40]; // [rsp+B0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
      (const char *)0x80004003LL,
      dwFlags);
    return 2147500035LL;
  }
  try
  {
    if ( a2 != 13 )
    {
      switch ( a2 )
      {
        case 0xEu:
          if ( *a3 == 13 )
          {
            v14 = (IUnknown *)*((_QWORD *)a3 + 1);
          }
          else
          {
            if ( *a3 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xDA,
                (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
                (const char *)0x80070057LL,
                dwFlags);
              return 2147942487LL;
            }
            v14 = 0;
          }
          si128 = 0;
          *(_OWORD *)ppvData = 0;
          if ( v14 )
          {
            v16 = (volatile signed __int32 *)operator new(0x20u);
            v54.m128i_i64[0] = (__int64)v16;
            *((_DWORD *)v16 + 2) = 1;
            *((_DWORD *)v16 + 3) = 1;
            *(_QWORD *)v16 = &std::_Ref_count_obj2<CDownloadStream>::`vftable';
            CDownloadStream::CDownloadStream((CDownloadStream *)(v16 + 4), v14);
            ppvData[0] = (void *)(v16 + 4);
            ppvData[1] = (void *)v16;
            si128 = _mm_load_si128((const __m128i *)ppvData);
          }
          else
          {
            v16 = (volatile signed __int32 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
          }
          v17 = *(CBackgroundCopyJob **)(a1 + 32);
          if ( v16 )
            _InterlockedAdd(v16 + 2, 1u);
          v54 = si128;
          v18 = CBackgroundCopyJob::SetOutputStream(v17);
          if ( si128.m128i_i64[1] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v54.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(__int64))si128.m128i_i64[1])(si128.m128i_i64[1]);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(si128.m128i_i64[1] + 12), 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)si128.m128i_i64[1] + 8LL))(si128.m128i_i64[1]);
            }
          }
          if ( v18 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xE1,
              (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
              (const char *)(unsigned int)v18,
              dwFlags);
            if ( v16 )
            {
              if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
                if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
              }
            }
            return (unsigned int)v18;
          }
          AcquireSRWLockExclusive((PSRWLOCK)(a1 + 64));
          if ( *(IUnknown **)(a1 + 56) != v14 )
          {
            if ( v14 )
              ((void (__fastcall *)(IUnknown *))v14->lpVtbl->AddRef)(v14);
            v19 = *(_QWORD *)(a1 + 56);
            *(_QWORD *)(a1 + 56) = v14;
            if ( v19 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          }
          ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 64));
          if ( !v16 )
            return 0;
          break;
        case 0xFu:
          v20 = *a3;
          if ( *a3 != 8209 && v20 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xE8,
              (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
              (const char *)0x80070057LL,
              dwFlags);
            return 2147942487LL;
          }
          CGuidToString::CGuidToString(
            (CGuidToString *)v61,
            (const struct _GUID *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 248LL) + 16LL));
          if ( v20 == 8209 && (v21 = (SAFEARRAY *)*((_QWORD *)a3 + 1)) != 0 )
          {
            LogMessage(4u, "CDODownloadExt::SetProperty", 0xEDu, "Job %s, SecurityContext set", v61);
            ppvData[0] = 0;
            v22 = SafeArrayAccessData(v21, ppvData);
            v23 = v22;
            if ( v22 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xEF,
                (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
                (const char *)(unsigned int)v22,
                dwFlagsa);
              return v23;
            }
            plLbound[0] = 0;
            LBound = SafeArrayGetLBound(v21, 1u, plLbound);
            v25 = LBound;
            if ( LBound < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xF5,
                (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
                (const char *)(unsigned int)LBound,
                dwFlagsa);
              SafeArrayUnaccessData(v21);
              return v25;
            }
            plUbound = 0;
            UBound = SafeArrayGetUBound(v21, 1u, &plUbound);
            v27 = UBound;
            if ( UBound < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xF8,
                (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
                (const char *)(unsigned int)UBound,
                dwFlagsa);
              SafeArrayUnaccessData(v21);
              return v27;
            }
            v28 = plUbound - plLbound[0] + 1;
            if ( v28 <= 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xFB,
                (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
                (const char *)0x80070057LL,
                dwFlagsa);
              SafeArrayUnaccessData(v21);
              return 2147942487LL;
            }
            pCertContext = 0;
            if ( !CertAddSerializedElementToStore(
                    0,
                    (const BYTE *)ppvData[0],
                    v28,
                    1u,
                    0,
                    2u,
                    0,
                    (const void **)&pCertContext) )
            {
              LastError = wil::details::in1diag3::Return_GetLastError(
                            retaddr,
                            (void *)0x106,
                            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
                            v29);
              if ( pCertContext )
                CertFreeCertificateContext(pCertContext);
              SafeArrayUnaccessData(v21);
              return LastError;
            }
            v54.m128i_i64[0] = (__int64)pCertContext;
            pCertContext = 0;
            CBackgroundCopyJob::SetClientCertificate(*(_QWORD *)(a1 + 32), &v54);
            if ( pCertContext )
              CertFreeCertificateContext(pCertContext);
            SafeArrayUnaccessData(v21);
          }
          else
          {
            LogMessage(4u, "CDODownloadExt::SetProperty", 0x10Cu, "Job %s, SecurityContext cleared", v61);
            CBackgroundCopyJob::RemoveClientCertificate(*(CBackgroundCopyJob **)(a1 + 32));
          }
          return 0;
        case 4u:
          if ( *a3 != 8 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x112,
              (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
              (const char *)0x80070057LL,
              dwFlags);
            return 2147942487LL;
          }
          v31 = *((_QWORD *)a3 + 1);
          v32 = -1;
          do
            ++v32;
          while ( *(_WORD *)(v31 + 2 * v32) );
          v57 = 0;
          v58 = 0;
          v59 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v57);
          v33 = &v57;
          v34 = (__int128 *)v57;
          v35 = v59;
          if ( v59 > 7 )
            v33 = (__int128 *)v57;
          v36 = v58;
          v37 = (__int128 *)((char *)v33 + 2 * v58);
          v38 = &v57;
          if ( v59 > 7 )
            v38 = (__int128 *)v57;
          if ( v38 != v37 )
          {
            do
            {
              if ( *(_WORD *)v38 == 47 )
                *(_WORD *)v38 = 92;
              v38 = (__int128 *)((char *)v38 + 2);
            }
            while ( v38 != v37 );
            v35 = v59;
            v36 = v58;
            v34 = (__int128 *)v57;
          }
          v39 = &v57;
          if ( v35 > 7 )
            v39 = v34;
          WstrToUTF8(ppvData, v39, v36);
          v54 = 0;
          std::make_shared<CConfigValue,std::string const &>(&v54, ppvData);
          v40 = *(CBackgroundCopyJob **)(a1 + 32);
          v41 = CDODownloadExt::MapPropertyId(4);
          v42 = CBackgroundCopyJob::SetDownloadProperty(v40, (char *)v41, (unsigned __int8 **)&v54, 0);
          v43 = v42;
          if ( v42 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x118,
              (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
              (const char *)(unsigned int)v42,
              dwFlags);
            v44 = (volatile signed __int32 *)v54.m128i_i64[1];
            if ( v54.m128i_i64[1] )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v54.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
                if ( _InterlockedExchangeAdd(v44 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
              }
            }
            std::string::~string(ppvData);
            std::wstring::~wstring(&v57);
            return v43;
          }
          v45 = (volatile signed __int32 *)v54.m128i_i64[1];
          if ( v54.m128i_i64[1] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v54.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
              if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
            }
          }
          std::string::~string(ppvData);
          std::wstring::~wstring(&v57);
          return 0;
        default:
          v54 = 0;
          ConfigValueFromVariant(&v54, a3);
          v46 = *(CBackgroundCopyJob **)(a1 + 32);
          v47 = CDODownloadExt::MapPropertyId(a2);
          v48 = CBackgroundCopyJob::SetDownloadProperty(v46, (char *)v47, (unsigned __int8 **)&v54, 0);
          v49 = v48;
          if ( v48 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x11D,
              (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
              (const char *)(unsigned int)v48,
              dwFlags);
            v50 = (volatile signed __int32 *)v54.m128i_i64[1];
            if ( v54.m128i_i64[1] )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v54.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
                if ( _InterlockedExchangeAdd(v50 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
              }
            }
            return v49;
          }
          v16 = (volatile signed __int32 *)v54.m128i_i64[1];
          if ( !v54.m128i_i64[1] )
            return 0;
          break;
      }
      if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
      return 0;
    }
    if ( *a3 == 13 )
    {
      v8 = (struct IUnknown *)*((_QWORD *)a3 + 1);
      if ( v8 )
      {
        v10 = *(const struct _GUID **)(*(_QWORD *)(a1 + 32) + 248LL);
        v11 = (volatile signed __int32 *)operator new(0xA8u);
        v54.m128i_i64[0] = (__int64)v11;
        *((_DWORD *)v11 + 2) = 1;
        *((_DWORD *)v11 + 3) = 1;
        *(_QWORD *)v11 = &std::_Ref_count_obj2<CDODownloadCallback>::`vftable';
        CDODownloadCallback::CDODownloadCallback(
          (CDODownloadCallback *)(v11 + 4),
          (struct IDODownload *)a1,
          v10 + 1,
          v8);
        ppvData[0] = (void *)(v11 + 4);
        ppvData[1] = (void *)v11;
        v12 = *(CBackgroundCopyJob **)(a1 + 32);
        if ( v11 )
          _InterlockedAdd(v11 + 2, 1u);
        v54.m128i_i64[0] = (__int64)(v11 + 4);
        v54.m128i_i64[1] = (__int64)v11;
        v13 = CBackgroundCopyJob::SetStatusCallback(v12);
        if ( v11 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v54.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
            if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
          }
        }
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xCE,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
            (const char *)(unsigned int)v13,
            dwFlags);
          if ( v11 )
          {
            if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
              if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
            }
          }
          return (unsigned int)v13;
        }
        if ( v11 )
        {
          if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
            if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
          }
        }
        goto LABEL_9;
      }
    }
    else
    {
      if ( *a3 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
          (const char *)0x80070057LL,
          dwFlags);
        return 2147942487LL;
      }
      v8 = 0;
    }
    CBackgroundCopyJob::NoMoreCallbacks(*(CBackgroundCopyJob **)(a1 + 32));
LABEL_9:
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 64));
    if ( *(struct IUnknown **)(a1 + 48) != v8 )
    {
      if ( v8 )
        ((void (__fastcall *)(struct IUnknown *))v8->lpVtbl->AddRef)(v8);
      v9 = *(_QWORD *)(a1 + 48);
      *(_QWORD *)(a1 + 48) = v8;
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 64));
    return 0;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x122,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\ExternalJob.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x18000fba0  push    rbx
0x18000fba2  push    rsi
0x18000fba3  push    rdi
0x18000fba4  push    r12
0x18000fba6  push    r13
0x18000fba8  push    r14
0x18000fbaa  push    r15
0x18000fbac  sub     rsp, 0E0h
0x18000fbb3  mov     rax, cs:__security_cookie
0x18000fbba  xor     rax, rsp
0x18000fbbd  mov     [rsp+118h+var_40], rax
0x18000fbc5  mov     rbx, r8
0x18000fbc8  mov     edi, edx
0x18000fbca  mov     rsi, rcx
0x18000fbcd  xor     r13d, r13d
0x18000fbd0  test    rbx, rbx
0x18000fbd3  jnz     short loc_18000FBFD
0x18000fbd5  mov     rcx, [rsp+118h]; this
0x18000fbdd  mov     ebx, 80004003h
0x18000fbe2  mov     r9d, ebx; char *
0x18000fbe5  lea     r8, aCW1SSrcDeliver_81; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000fbec  mov     edx, 0C5h; void *
0x18000fbf1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fbf6  mov     eax, ebx
0x18000fbf8  jmp     loc_18001058A
0x18000fbfd  mov     ecx, 0Dh
0x18000fc02  cmp     edi, ecx
0x18000fc04  jnz     loc_18000FE1D
0x18000fc0a  movzx   eax, word ptr [r8]
0x18000fc0e  cmp     ax, cx
0x18000fc11  jz      loc_18000FC9E
0x18000fc17  test    ax, ax
0x18000fc1a  jz      short loc_18000FC44
0x18000fc1c  mov     rcx, [rsp+118h]; this
0x18000fc24  mov     ebx, 80070057h
0x18000fc29  mov     r9d, ebx; char *
0x18000fc2c  lea     r8, aCW1SSrcDeliver_81; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000fc33  mov     edx, 0C9h; void *
0x18000fc38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fc3d  mov     eax, ebx
0x18000fc3f  jmp     loc_18001058A
0x18000fc44  mov     r14, r13
0x18000fc47  mov     rcx, [rsi+20h]; this
0x18000fc4b  call    ?NoMoreCallbacks@CBackgroundCopyJob@@QEAAXXZ; CBackgroundCopyJob::NoMoreCallbacks(void)
0x18000fc50  lea     rcx, [rsi+40h]; SRWLock
0x18000fc54  call    cs:__imp_AcquireSRWLockExclusive
0x18000fc5a  cmp     [rsi+30h], r14
0x18000fc5e  jz      short loc_18000FC8F
0x18000fc60  test    r14, r14
0x18000fc63  jz      short loc_18000FC75
0x18000fc65  mov     rax, [r14]
0x18000fc68  mov     rcx, r14
0x18000fc6b  mov     rax, [rax+8]
0x18000fc6f  call    _guard_dispatch_icall
0x18000fc74  nop
0x18000fc75  mov     rcx, [rsi+30h]
0x18000fc79  mov     [rsi+30h], r14
0x18000fc7d  test    rcx, rcx
0x18000fc80  jz      short loc_18000FC8F
0x18000fc82  mov     rax, [rcx]
0x18000fc85  mov     rax, [rax+10h]
0x18000fc89  call    _guard_dispatch_icall
0x18000fc8e  nop
0x18000fc8f  lea     rcx, [rsi+40h]; SRWLock
0x18000fc93  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fc99  jmp     loc_18001057B
0x18000fc9e  mov     r14, [r8+8]
0x18000fca2  test    r14, r14
0x18000fca5  jz      short loc_18000FC47
0x18000fca7  mov     rax, [rsi+20h]
0x18000fcab  mov     r15, [rax+0F8h]
0x18000fcb2  mov     ecx, 0A8h; Size
0x18000fcb7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fcbc  mov     rdi, rax
0x18000fcbf  mov     qword ptr [rsp+118h+var_C8], rax
0x18000fcc4  mov     ebx, 1
0x18000fcc9  mov     [rax+8], ebx
0x18000fccc  mov     [rax+0Ch], ebx
0x18000fccf  lea     rax, ??_7?$_Ref_count_obj2@VCDODownloadCallback@@@std@@6B@; const std::_Ref_count_obj2<CDODownloadCallback>::`vftable'
0x18000fcd6  mov     [rdi], rax
0x18000fcd9  lea     r12, [rdi+10h]
0x18000fcdd  mov     r9, r14; struct IUnknown *
0x18000fce0  lea     r8, [r15+10h]; struct _GUID *
0x18000fce4  mov     rdx, rsi; struct IDODownload *
0x18000fce7  mov     rcx, r12; this
0x18000fcea  call    ??0CDODownloadCallback@@QEAA@PEAUIDODownload@@AEBU_GUID@@PEAUIUnknown@@@Z; CDODownloadCallback::CDODownloadCallback(IDODownload *,_GUID const &,IUnknown *)
0x18000fcef  nop
0x18000fcf0  xorps   xmm0, xmm0
0x18000fcf3  movups  xmmword ptr [rsp+118h+ppvData], xmm0
0x18000fcfb  mov     [rsp+118h+ppvData], r12
0x18000fd03  mov     [rsp+118h+ppvData+8], rdi
0x18000fd0b  mov     rcx, [rsi+20h]; this
0x18000fd0f  test    rdi, rdi
0x18000fd12  jz      short loc_18000FD18
0x18000fd14  lock add [rdi+8], ebx
0x18000fd18  mov     qword ptr [rsp+118h+var_C8], r12
0x18000fd1d  mov     qword ptr [rsp+118h+var_C8+8], rdi
0x18000fd22  lea     rdx, [rsp+118h+var_C8]
0x18000fd27  call    ?SetStatusCallback@CBackgroundCopyJob@@QEAAJAEBV?$shared_ptr@VIDownloadJobCallback@@@std@@@Z; CBackgroundCopyJob::SetStatusCallback(std::shared_ptr<IDownloadJobCallback> const &)
0x18000fd2c  mov     r12d, eax
0x18000fd2f  mov     r15, qword ptr [rsp+118h+var_C8+8]
0x18000fd34  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000fd38  test    r15, r15
0x18000fd3b  jz      short loc_18000FD72
0x18000fd3d  mov     eax, ebx
0x18000fd3f  lock xadd [r15+8], eax
0x18000fd45  add     eax, ebx
0x18000fd47  jnz     short loc_18000FD72
0x18000fd49  mov     rax, [r15]
0x18000fd4c  mov     rcx, r15
0x18000fd4f  mov     rax, [rax]
0x18000fd52  call    _guard_dispatch_icall
0x18000fd57  mov     eax, ebx
0x18000fd59  lock xadd [r15+0Ch], eax
0x18000fd5f  add     eax, ebx
0x18000fd61  jnz     short loc_18000FD72
0x18000fd63  mov     rax, [r15]
0x18000fd66  mov     rcx, r15
0x18000fd69  mov     rax, [rax+8]
0x18000fd6d  call    _guard_dispatch_icall
0x18000fd72  test    r12d, r12d
0x18000fd75  jns     short loc_18000FDD4
0x18000fd77  mov     rcx, [rsp+118h]; this
0x18000fd7f  mov     r9d, r12d; char *
0x18000fd82  lea     r8, aCW1SSrcDeliver_81; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000fd89  mov     edx, 0CEh; void *
0x18000fd8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fd93  nop
0x18000fd94  test    rdi, rdi
0x18000fd97  jz      short loc_18000FDCC
0x18000fd99  mov     eax, ebx
0x18000fd9b  lock xadd [rdi+8], eax
0x18000fda0  add     eax, ebx
0x18000fda2  jnz     short loc_18000FDCC
0x18000fda4  mov     rax, [rdi]
0x18000fda7  mov     rcx, rdi
0x18000fdaa  mov     rax, [rax]
0x18000fdad  call    _guard_dispatch_icall
0x18000fdb2  mov     edx, ebx
0x18000fdb4  lock xadd [rdi+0Ch], edx
0x18000fdb9  add     edx, ebx
0x18000fdbb  jnz     short loc_18000FDCC
0x18000fdbd  mov     rdx, [rdi]
0x18000fdc0  mov     rcx, rdi
0x18000fdc3  mov     rax, [rdx+8]
0x18000fdc7  call    _guard_dispatch_icall
0x18000fdcc  mov     eax, r12d
0x18000fdcf  jmp     loc_18001058A
0x18000fdd4  test    rdi, rdi
0x18000fdd7  jz      loc_18000FC50
0x18000fddd  mov     eax, ebx
0x18000fddf  lock xadd [rdi+8], eax
0x18000fde4  add     eax, ebx
0x18000fde6  jnz     loc_18000FC50
0x18000fdec  mov     rax, [rdi]
0x18000fdef  mov     rcx, rdi
0x18000fdf2  mov     rax, [rax]
0x18000fdf5  call    _guard_dispatch_icall
0x18000fdfa  mov     eax, ebx
0x18000fdfc  lock xadd [rdi+0Ch], eax
0x18000fe01  add     eax, ebx
0x18000fe03  jnz     loc_18000FC50
0x18000fe09  mov     rax, [rdi]
0x18000fe0c  mov     rcx, rdi
0x18000fe0f  mov     rax, [rax+8]
0x18000fe13  call    _guard_dispatch_icall
0x18000fe18  jmp     loc_18000FC50
0x18000fe1d  cmp     edi, 0Eh
0x18000fe20  jnz     loc_18000FFF7
0x18000fe26  movzx   eax, word ptr [r8]
0x18000fe2a  cmp     ax, cx
0x18000fe2d  jz      short loc_18000FE61
0x18000fe2f  test    ax, ax
0x18000fe32  jz      short loc_18000FE5C
0x18000fe34  mov     rcx, [rsp+118h]; this
0x18000fe3c  mov     ebx, 80070057h
0x18000fe41  mov     r9d, ebx; char *
0x18000fe44  lea     r8, aCW1SSrcDeliver_81; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000fe4b  mov     edx, 0DAh; void *
0x18000fe50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fe55  mov     eax, ebx
0x18000fe57  jmp     loc_18001058A
0x18000fe5c  mov     r14, r13
0x18000fe5f  jmp     short loc_18000FE65
0x18000fe61  mov     r14, [r8+8]
0x18000fe65  xorps   xmm0, xmm0
0x18000fe68  xorps   xmm1, xmm1
0x18000fe6b  movdqa  xmmword ptr [rsp+118h+ppvData], xmm1
0x18000fe74  test    r14, r14
0x18000fe77  jz      short loc_18000FECB
0x18000fe79  mov     ecx, 20h ; ' '; Size
0x18000fe7e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fe83  mov     rdi, rax
0x18000fe86  mov     qword ptr [rsp+118h+var_C8], rax
0x18000fe8b  mov     ebx, 1
0x18000fe90  mov     [rax+8], ebx
0x18000fe93  mov     [rax+0Ch], ebx
0x18000fe96  lea     rax, ??_7?$_Ref_count_obj2@VCDownloadStream@@@std@@6B@; const std::_Ref_count_obj2<CDownloadStream>::`vftable'
0x18000fe9d  mov     [rdi], rax
0x18000fea0  lea     r15, [rdi+10h]
0x18000fea4  mov     rdx, r14; pProxy
0x18000fea7  mov     rcx, r15; this
0x18000feaa  call    ??0CDownloadStream@@QEAA@PEAUIUnknown@@@Z; CDownloadStream::CDownloadStream(IUnknown *)
0x18000feaf  nop
0x18000feb0  mov     [rsp+118h+ppvData], r15
0x18000feb8  mov     [rsp+118h+ppvData+8], rdi
0x18000fec0  movdqa  xmm1, xmmword ptr [rsp+118h+ppvData]
0x18000fec9  jmp     short loc_18000FEDA
0x18000fecb  mov     ebx, 1
0x18000fed0  psrldq  xmm0, 8
0x18000fed5  movq    rdi, xmm0
0x18000feda  mov     rcx, [rsi+20h]; this
0x18000fede  test    rdi, rdi
0x18000fee1  jz      short loc_18000FEE7
0x18000fee3  lock add [rdi+8], ebx
0x18000fee7  movdqa  [rsp+118h+var_C8], xmm1
0x18000feed  lea     rdx, [rsp+118h+var_C8]
0x18000fef2  call    ?SetOutputStream@CBackgroundCopyJob@@QEAAJAEBV?$shared_ptr@VIDownloadStream@@@std@@@Z; CBackgroundCopyJob::SetOutputStream(std::shared_ptr<IDownloadStream> const &)
0x18000fef7  mov     r12d, eax
0x18000fefa  mov     r15, qword ptr [rsp+118h+var_C8+8]
0x18000feff  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ff03  test    r15, r15
0x18000ff06  jz      short loc_18000FF3D
0x18000ff08  mov     eax, ebx
0x18000ff0a  lock xadd [r15+8], eax
0x18000ff10  add     eax, ebx
0x18000ff12  jnz     short loc_18000FF3D
0x18000ff14  mov     rax, [r15]
0x18000ff17  mov     rcx, r15
0x18000ff1a  mov     rax, [rax]
0x18000ff1d  call    _guard_dispatch_icall
0x18000ff22  mov     eax, ebx
0x18000ff24  lock xadd [r15+0Ch], eax
0x18000ff2a  add     eax, ebx
0x18000ff2c  jnz     short loc_18000FF3D
0x18000ff2e  mov     rax, [r15]
0x18000ff31  mov     rcx, r15
0x18000ff34  mov     rax, [rax+8]
0x18000ff38  call    _guard_dispatch_icall
0x18000ff3d  test    r12d, r12d
0x18000ff40  jns     short loc_18000FF9F
0x18000ff42  mov     rcx, [rsp+118h]; this
0x18000ff4a  mov     r9d, r12d; char *
0x18000ff4d  lea     r8, aCW1SSrcDeliver_81; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000ff54  mov     edx, 0E1h; void *
0x18000ff59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ff5e  nop
0x18000ff5f  test    rdi, rdi
0x18000ff62  jz      short loc_18000FF97
0x18000ff64  mov     eax, ebx
0x18000ff66  lock xadd [rdi+8], eax
0x18000ff6b  add     eax, ebx
0x18000ff6d  jnz     short loc_18000FF97
0x18000ff6f  mov     rax, [rdi]
0x18000ff72  mov     rcx, rdi
0x18000ff75  mov     rax, [rax]
0x18000ff78  call    _guard_dispatch_icall
0x18000ff7d  mov     edx, ebx
0x18000ff7f  lock xadd [rdi+0Ch], edx
0x18000ff84  add     edx, ebx
0x18000ff86  jnz     short loc_18000FF97
0x18000ff88  mov     rdx, [rdi]
0x18000ff8b  mov     rcx, rdi
0x18000ff8e  mov     rax, [rdx+8]
0x18000ff92  call    _guard_dispatch_icall
0x18000ff97  mov     eax, r12d
0x18000ff9a  jmp     loc_18001058A
0x18000ff9f  lea     rcx, [rsi+40h]; SRWLock
0x18000ffa3  call    cs:__imp_AcquireSRWLockExclusive
0x18000ffa9  cmp     [rsi+38h], r14
0x18000ffad  jz      short loc_18000FFDE
0x18000ffaf  test    r14, r14
0x18000ffb2  jz      short loc_18000FFC4
0x18000ffb4  mov     rax, [r14]
0x18000ffb7  mov     rcx, r14
0x18000ffba  mov     rax, [rax+8]
0x18000ffbe  call    _guard_dispatch_icall
0x18000ffc3  nop
0x18000ffc4  mov     rcx, [rsi+38h]
0x18000ffc8  mov     [rsi+38h], r14
0x18000ffcc  test    rcx, rcx
0x18000ffcf  jz      short loc_18000FFDE
0x18000ffd1  mov     rax, [rcx]
0x18000ffd4  mov     rax, [rax+10h]
0x18000ffd8  call    _guard_dispatch_icall
0x18000ffdd  nop
0x18000ffde  lea     rcx, [rsi+40h]; SRWLock
0x18000ffe2  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ffe8  nop
0x18000ffe9  test    rdi, rdi
0x18000ffec  jz      loc_18001057B
0x18000fff2  jmp     loc_180010548
0x18000fff7  cmp     edi, 0Fh
0x18000fffa  jnz     loc_18001029E
0x180010000  movzx   edi, word ptr [r8]
0x180010004  mov     r14d, 2011h
0x18001000a  cmp     di, r14w
0x18001000e  jz      short loc_18001003D
0x180010010  test    di, di
0x180010013  jz      short loc_18001003D
  ... truncated ...
```
