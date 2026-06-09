# Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal(HSTRING__ *,HSTRING__ *)

- ea: `0x180110560`
- end: `0x180111080`
- name: `?InitializeInternal@EMEStoreObjectDllManager@Protection@Media@Windows@@AEAAJPEAUHSTRING__@@0@Z`
- size: `2848`
- prototype: `int(Windows::Media::Protection::EMEStoreObjectDllManager *__hidden this, HSTRING, HSTRING)`
- caller_count: `2`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800ea8f0`
- `0x18010fe20`

## callees

- `0x180004870`
- `0x1800144ac`
- `0x1800153c4`
- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x1800255b0`
- `0x180038bf0`
- `0x18003eef4`
- `0x1800d7768`
- `0x180110560`
- `0x18011c7b8`
- `0x1801200d0`
- `0x18012a700`
- `0x1801542e8`
- `0x180154b68`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011061d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011062b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011099a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011061d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011062b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18011099a`
- `CompPkgSup!GetMediaComponentPackageInfo` at `0x18011069a`
- `CompPkgSup!GetMediaComponentPackageInfo` at `0x18011069a`

## string_xrefs

- `0x180110599`: `Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal`
- `0x18011070e`: `Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal`
- `0x1801107be`: `Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal`
- `0x18011095f`: `Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal`
- `0x180110a16`: `Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal`
- `0x180110ac0`: `Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal`
- `0x180110b6b`: `Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal`
- `0x180110c16`: `Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal`
- `0x180110cc4`: `Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal`
- `0x180110de3`: `Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal`
- `0x180110e6f`: `Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal`
- `0x180110efb`: `Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal`
- `0x180110f87`: `Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal`
- `0x180111003`: `Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal`

## pseudocode

```c
__int64 __fastcall Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal(
        Windows::Media::Protection::EMEStoreObjectDllManager *this,
        HSTRING a2,
        HSTRING a3)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  unsigned int v7; // ebx
  _GUID v8; // xmm0
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v10; // rax
  int MediaComponentPackageInfo; // ebx
  CallStackTracing *v12; // rcx
  struct CallStackContext *v13; // rax
  __int64 v14; // rdx
  CallStackTracing *v15; // rcx
  struct CallStackContext *v16; // rax
  unsigned int i; // r14d
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD, _QWORD); // rbx
  __int64 (__fastcall ***v20)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v21)(_QWORD, GUID *, __int64 *); // rbx
  CallStackTracing *v22; // rcx
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  const unsigned __int16 *v25; // rax
  CGlobalInprocDllManager *v26; // rcx
  CallStackTracing *v27; // rcx
  struct CallStackContext *v28; // rax
  CallStackTracing *v29; // rcx
  struct CallStackContext *v30; // rax
  CallStackTracing *v31; // rcx
  struct CallStackContext *v32; // rax
  CallStackTracing *v33; // rcx
  struct CallStackContext *v34; // rax
  CallStackTracing *v35; // rcx
  struct CallStackContext *v36; // rax
  CallStackTracing *v37; // rcx
  CallStackTracing *v38; // rcx
  struct CallStackContext *v39; // rax
  CallStackTracing *v40; // rcx
  struct CallStackContext *v41; // rax
  CallStackTracing *v42; // rcx
  struct CallStackContext *v43; // rax
  CallStackTracing *v44; // rcx
  struct CallStackContext *v45; // rax
  struct CallStackContext *v46; // rax
  CallStackScopeTrace v48; // [rsp+30h] [rbp-89h] BYREF
  __int64 v49; // [rsp+38h] [rbp-81h] BYREF
  __int64 (__fastcall ***v50)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-79h] BYREF
  unsigned int v51; // [rsp+48h] [rbp-71h] BYREF
  __int64 v52[2]; // [rsp+50h] [rbp-69h] BYREF
  HSTRING v53[2]; // [rsp+60h] [rbp-59h] BYREF
  __int128 v54; // [rsp+70h] [rbp-49h]
  __int16 v55; // [rsp+80h] [rbp-39h]
  char v56; // [rsp+82h] [rbp-37h]
  HSTRING string[2]; // [rsp+90h] [rbp-29h]
  __int64 v58; // [rsp+A0h] [rbp-19h]
  Microsoft::WRL::Wrappers::HStringReference v59; // [rsp+B0h] [rbp-9h] BYREF

  v52[0] = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    &v48,
    "Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal",
    73);
  if ( CallStackTracing::s_wpInstance->m_fEnabled && *((_QWORD *)this + 10) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 296LL))(*((_QWORD *)this + 10));
    v8 = *(_GUID *)(*(__int64 (__fastcall **)(_QWORD, Microsoft::WRL::Wrappers::HStringReference *))(**((_QWORD **)this + 10) + 280LL))(
                     *((_QWORD *)this + 10),
                     &v59);
    ThreadRelativeContext->m_instanceId = v7;
    ThreadRelativeContext->m_sessionId = v8;
  }
  if ( (unsigned __int8)byte_1801FD289 >= 0x10u )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
    v10 = WindowsGetStringRawBuffer(a2, 0);
    WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 7), (__int64)v10, (__int64)StringRawBuffer);
  }
  if ( *((_QWORD *)this + 11) )
  {
    MediaComponentPackageInfo = -1072871856;
    goto LABEL_149;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v52);
  v59.hstr_ = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v59,
    L"windows.mediaContentDecryptionModule",
    0x25u,
    0x24u);
  MediaComponentPackageInfo = GetMediaComponentPackageInfo(0, v59.hstr_, v52);
  if ( MediaComponentPackageInfo < 0 )
  {
    v12 = CallStackTracing::s_wpInstance;
    v59.hstr_ = 0;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v12 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v12 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v12->m_fEnabled )
    {
      v13 = CallStackTracing::GetThreadRelativeContext(v12);
      if ( v13->m_result != MediaComponentPackageInfo )
        CallStackContext::TraceFailure(
          v13,
          "Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal",
          81,
          MediaComponentPackageInfo);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v14 = 14;
      goto LABEL_148;
    }
    goto LABEL_149;
  }
  v51 = 0;
  MediaComponentPackageInfo = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v52[0] + 56LL))(
                                v52[0],
                                &v51);
  if ( MediaComponentPackageInfo < 0 )
  {
    v15 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v15 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v15 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v15->m_fEnabled )
    {
      v16 = CallStackTracing::GetThreadRelativeContext(v15);
      if ( v16->m_result != MediaComponentPackageInfo )
        CallStackContext::TraceFailure(
          v16,
          "Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal",
          84,
          MediaComponentPackageInfo);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v14 = 15;
      goto LABEL_148;
    }
    goto LABEL_149;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v51 )
      goto LABEL_100;
    v50 = 0;
    v49 = 0;
    v56 = 0;
    v58 = 0;
    *(_OWORD *)v53 = 0;
    v54 = 0;
    v55 = 0;
    *(_OWORD *)string = 0;
    v48 = 0;
    v18 = v52[0];
    v19 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v52[0] + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v50);
    MediaComponentPackageInfo = v19(v18, i, &v50);
    if ( MediaComponentPackageInfo < 0 )
    {
      v44 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v44 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v44 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v44->m_fEnabled )
      {
        v45 = CallStackTracing::GetThreadRelativeContext(v44);
        if ( v45->m_result != MediaComponentPackageInfo )
          CallStackContext::TraceFailure(
            v45,
            "Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal",
            92,
            MediaComponentPackageInfo);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_141;
      v24 = 16;
LABEL_140:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v24,
        WPP_95e19eb2fcbc35395588268428fbcc11_Traceguids,
        this,
        MediaComponentPackageInfo);
      goto LABEL_141;
    }
    v20 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v50;
    v21 = **v50;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    MediaComponentPackageInfo = v21(v20, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v49);
    if ( MediaComponentPackageInfo < 0 )
    {
      v42 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v42 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v42 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v42->m_fEnabled )
      {
        v43 = CallStackTracing::GetThreadRelativeContext(v42);
        if ( v43->m_result != MediaComponentPackageInfo )
          CallStackContext::TraceFailure(
            v43,
            "Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal",
            94,
            MediaComponentPackageInfo);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_141;
      v24 = 17;
      goto LABEL_140;
    }
    MediaComponentPackageInfo = MatchAndGetContentDecryptionModuleInfo(v49, a2, a3, v53, &v48);
    if ( MediaComponentPackageInfo < 0 )
    {
      v40 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v40 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v40 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v40->m_fEnabled )
      {
        v41 = CallStackTracing::GetThreadRelativeContext(v40);
        if ( v41->m_result != MediaComponentPackageInfo )
          CallStackContext::TraceFailure(
            v41,
            "Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal",
            101,
            MediaComponentPackageInfo);
      }
      if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
        goto LABEL_141;
      v24 = 18;
      goto LABEL_140;
    }
    if ( v48 )
      break;
    MediaContentDecryptionModuleInfo::~MediaContentDecryptionModuleInfo((MediaContentDecryptionModuleInfo *)v53);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v50);
  }
  if ( (_BYTE)v55 )
  {
    MediaComponentPackageInfo = DeployPackage(v53[1]);
    if ( MediaComponentPackageInfo < 0 )
    {
      v22 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v22 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v22 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      if ( v22->m_fEnabled )
      {
        v23 = CallStackTracing::GetThreadRelativeContext(v22);
        if ( v23->m_result != MediaComponentPackageInfo )
          CallStackContext::TraceFailure(
            v23,
            "Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal",
            108,
            MediaComponentPackageInfo);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v24 = 19;
        goto LABEL_140;
      }
LABEL_141:
      MediaContentDecryptionModuleInfo::~MediaContentDecryptionModuleInfo((MediaContentDecryptionModuleInfo *)v53);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v50);
      goto LABEL_149;
    }
  }
  Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease((char *)this + 72);
  v25 = WindowsGetStringRawBuffer(string[1], 0);
  MediaComponentPackageInfo = CGlobalInprocDllManager::GetDllManager(v26, v25, (struct CMFInprocDllManager **)this + 9);
  if ( MediaComponentPackageInfo < 0 )
  {
    v27 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v27 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v27 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v27->m_fEnabled )
    {
      v28 = CallStackTracing::GetThreadRelativeContext(v27);
      if ( v28->m_result != MediaComponentPackageInfo )
        CallStackContext::TraceFailure(
          v28,
          "Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal",
          111,
          MediaComponentPackageInfo);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_141;
    v24 = 20;
    goto LABEL_140;
  }
  v59.header_.Reserved.Reserved1 = string[1];
  MediaComponentPackageInfo = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)this + 11, (HSTRING *)&v59);
  if ( MediaComponentPackageInfo < 0 )
  {
    v29 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v29 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v29 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v29->m_fEnabled )
    {
      v30 = CallStackTracing::GetThreadRelativeContext(v29);
      if ( v30->m_result != MediaComponentPackageInfo )
        CallStackContext::TraceFailure(
          v30,
          "Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal",
          112,
          MediaComponentPackageInfo);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_141;
    v24 = 21;
    goto LABEL_140;
  }
  v59.header_.Reserved.Reserved1 = v53[1];
  MediaComponentPackageInfo = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)this + 12, (HSTRING *)&v59);
  if ( MediaComponentPackageInfo < 0 )
  {
    v31 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v31 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v31 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v31->m_fEnabled )
    {
      v32 = CallStackTracing::GetThreadRelativeContext(v31);
      if ( v32->m_result != MediaComponentPackageInfo )
        CallStackContext::TraceFailure(
          v32,
          "Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal",
          113,
          MediaComponentPackageInfo);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_141;
    v24 = 22;
    goto LABEL_140;
  }
  v59.header_.Reserved.Reserved1 = v53[0];
  MediaComponentPackageInfo = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)this + 13, (HSTRING *)&v59);
  if ( MediaComponentPackageInfo < 0 )
  {
    v33 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v33 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v33 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v33->m_fEnabled )
    {
      v34 = CallStackTracing::GetThreadRelativeContext(v33);
      if ( v34->m_result != MediaComponentPackageInfo )
        CallStackContext::TraceFailure(
          v34,
          "Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal",
          114,
          MediaComponentPackageInfo);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_141;
    v24 = 23;
    goto LABEL_140;
  }
  v59.header_.Reserved.Reserved1 = string[0];
  MediaComponentPackageInfo = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)this + 14, (HSTRING *)&v59);
  if ( MediaComponentPackageInfo < 0 )
  {
    v35 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v35 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v35 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v35->m_fEnabled )
    {
      v36 = CallStackTracing::GetThreadRelativeContext(v35);
      if ( v36->m_result != MediaComponentPackageInfo )
        CallStackContext::TraceFailure(
          v36,
          "Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal",
          115,
          MediaComponentPackageInfo);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_141;
    v24 = 24;
    goto LABEL_140;
  }
  if ( !*((_QWORD *)this + 11) || !*((_QWORD *)this + 12) || !*((_QWORD *)this + 14) )
  {
    v38 = CallStackTracing::s_wpInstance;
    MediaComponentPackageInfo = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v38 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v38 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v38->m_fEnabled )
    {
      v39 = CallStackTracing::GetThreadRelativeContext(v38);
      if ( v39->m_result != -2147024882 )
        CallStackContext::TraceFailure(
          v39,
          "Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal",
          119,
          -2147024882);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_141;
    v24 = 25;
    goto LABEL_140;
  }
  MediaContentDecryptionModuleInfo::~MediaContentDecryptionModuleInfo((MediaContentDecryptionModuleInfo *)v53);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)&v50);
LABEL_100:
  if ( !*((_QWORD *)this + 9) )
  {
    v37 = CallStackTracing::s_wpInstance;
    MediaComponentPackageInfo = -2140143607;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      {
        v37 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v37 = &stru_1801F8A30;
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
    }
    if ( v37->m_fEnabled )
    {
      v46 = CallStackTracing::GetThreadRelativeContext(v37);
      if ( v46->m_result != -2140143607 )
        CallStackContext::TraceFailure(
          v46,
          "Windows::Media::Protection::EMEStoreObjectDllManager::InitializeInternal",
          127,
          -2140143607);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v14 = 26;
LABEL_148:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        WPP_95e19eb2fcbc35395588268428fbcc11_Traceguids,
        this,
        MediaComponentPackageInfo);
    }
  }
LABEL_149:
  CallStackScopeTrace::~CallStackScopeTrace(&v48);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v52);
  return (unsigned int)MediaComponentPackageInfo;
}

```

## disassembly

```asm
0x180110560  mov     [rsp-8+arg_18], rbx
0x180110565  push    rbp
0x180110566  push    rsi
0x180110567  push    rdi
0x180110568  push    r12
0x18011056a  push    r13
0x18011056c  push    r14
0x18011056e  push    r15
0x180110570  lea     rbp, [rsp-27h]
0x180110575  sub     rsp, 0E0h
0x18011057c  mov     rax, cs:__security_cookie
0x180110583  xor     rax, rsp
0x180110586  mov     [rbp+57h+var_40], rax
0x18011058a  xor     edi, edi
0x18011058c  mov     r13, r8
0x18011058f  mov     r12, rdx
0x180110592  mov     [rbp+57h+var_C0], rdi
0x180110596  mov     rsi, rcx
0x180110599  lea     rdx, aWindowsMediaPr_0; "Windows::Media::Protection::EMEStoreObj"...
0x1801105a0  lea     rcx, [rsp+110h+var_E0]; this
0x1801105a5  lea     r8d, [rdi+49h]; int
0x1801105a9  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801105ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801105b5  cmp     [rcx+8], dil
0x1801105b9  jz      short loc_180110608
0x1801105bb  cmp     [rsi+50h], rdi
0x1801105bf  jz      short loc_180110608
0x1801105c1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801105c6  mov     rcx, [rsi+50h]
0x1801105ca  mov     rdi, rax
0x1801105cd  mov     rdx, [rcx]
0x1801105d0  mov     rax, [rdx+128h]
0x1801105d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801105dc  mov     rcx, [rsi+50h]
0x1801105e0  mov     ebx, eax
0x1801105e2  mov     rdx, [rcx]
0x1801105e5  mov     rax, [rdx+118h]
0x1801105ec  lea     rdx, [rbp+57h+var_60]
0x1801105f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801105f5  movups  xmm0, xmmword ptr [rax]
0x1801105f8  mov     [rdi+7E0h], ebx
0x1801105fe  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180110606  xor     edi, edi
0x180110608  cmp     cs:byte_1801FD289, 10h
0x18011060f  lea     r14, WPP_95e19eb2fcbc35395588268428fbcc11_Traceguids
0x180110616  jb      short loc_180110656
0x180110618  xor     edx, edx; length
0x18011061a  mov     rcx, r13; string
0x18011061d  call    cs:__imp_WindowsGetStringRawBuffer
0x180110623  xor     edx, edx; length
0x180110625  mov     rcx, r12; string
0x180110628  mov     rbx, rax
0x18011062b  call    cs:__imp_WindowsGetStringRawBuffer
0x180110631  mov     rcx, cs:WPP_GLOBAL_Control
0x180110638  mov     edx, 0Dh
0x18011063d  mov     [rsp+110h+var_E8], rbx; __int64
0x180110642  mov     r9, rsi
0x180110645  mov     r8, r14
0x180110648  mov     [rsp+110h+var_F0], rax; __int64
0x18011064d  mov     rcx, [rcx+38h]; LoggerHandle
0x180110651  call    WPP_SF_qSS
0x180110656  lea     r15, [rsi+58h]
0x18011065a  cmp     [r15], rdi
0x18011065d  jz      short loc_180110669
0x18011065f  mov     ebx, 0C00D4650h
0x180110664  jmp     loc_180111044
0x180110669  lea     rcx, [rbp+57h+var_C0]
0x18011066d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180110672  mov     r9d, 24h ; '$'; unsigned int
0x180110678  mov     [rbp+57h+var_60.hstr_], rdi
0x18011067c  lea     rdx, aWindowsMediaco_9; "windows.mediaContentDecryptionModule"
0x180110683  lea     rcx, [rbp+57h+var_60]; this
0x180110687  lea     r8d, [r9+1]; unsigned int
0x18011068b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180110690  mov     rdx, [rbp+57h+var_60.hstr_]
0x180110694  lea     r8, [rbp+57h+var_C0]
0x180110698  xor     ecx, ecx
0x18011069a  call    cs:__imp_GetMediaComponentPackageInfo
0x1801106a0  mov     ebx, eax
0x1801106a2  test    eax, eax
0x1801106a4  jns     loc_18011073D
0x1801106aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801106b1  mov     [rbp+57h+var_60.hstr_], rdi
0x1801106b5  test    rcx, rcx
0x1801106b8  jnz     short loc_1801106F8
0x1801106ba  mov     rdx, cs:stru_1801FC290.__vftable
0x1801106c1  lea     rcx, stru_1801FC290
0x1801106c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801106cf  mov     rax, [rdx+8]
0x1801106d3  mov     edx, 7F0h
0x1801106d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801106dd  test    eax, eax
0x1801106df  jnz     short loc_1801106F1
0x1801106e1  lea     rcx, stru_1801F8A30
0x1801106e8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801106ef  jmp     short loc_1801106F8
0x1801106f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801106f8  cmp     [rcx+8], dil
0x1801106fc  jz      short loc_180110723
0x1801106fe  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180110703  cmp     [rax+7CCh], ebx
0x180110709  jz      short loc_180110723
0x18011070b  mov     r9d, ebx; int
0x18011070e  lea     rdx, aWindowsMediaPr_0; "Windows::Media::Protection::EMEStoreObj"...
0x180110715  mov     r8d, 51h ; 'Q'; int
0x18011071b  mov     rcx, rax; this
0x18011071e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180110723  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011072a  jb      loc_180111044
0x180110730  mov     edx, 0Eh
0x180110735  mov     r8, r14
0x180110738  jmp     loc_18011102D
0x18011073d  mov     rcx, [rbp+57h+var_C0]
0x180110741  lea     rdx, [rbp+57h+var_C8]
0x180110745  mov     [rbp+57h+var_C8], edi
0x180110748  mov     rax, [rcx]
0x18011074b  mov     rax, [rax+38h]
0x18011074f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110754  mov     ebx, eax
0x180110756  test    eax, eax
0x180110758  jns     loc_1801107EA
0x18011075e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180110765  test    rcx, rcx
0x180110768  jnz     short loc_1801107A8
0x18011076a  mov     rax, cs:stru_1801FC290.__vftable
0x180110771  lea     rcx, stru_1801FC290
0x180110778  mov     edx, 7F0h
0x18011077d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180110784  mov     rax, [rax+8]
0x180110788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011078d  test    eax, eax
0x18011078f  jnz     short loc_1801107A1
0x180110791  lea     rcx, stru_1801F8A30
0x180110798  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18011079f  jmp     short loc_1801107A8
0x1801107a1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801107a8  cmp     [rcx+8], dil
0x1801107ac  jz      short loc_1801107D3
0x1801107ae  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801107b3  cmp     [rax+7CCh], ebx
0x1801107b9  jz      short loc_1801107D3
0x1801107bb  mov     r9d, ebx; int
0x1801107be  lea     rdx, aWindowsMediaPr_0; "Windows::Media::Protection::EMEStoreObj"...
0x1801107c5  mov     r8d, 54h ; 'T'; int
0x1801107cb  mov     rcx, rax; this
0x1801107ce  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801107d3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1801107da  jb      loc_180111044
0x1801107e0  mov     edx, 0Fh
0x1801107e5  jmp     loc_180110735
0x1801107ea  mov     r14d, edi
0x1801107ed  cmp     r14d, [rbp+57h+var_C8]
0x1801107f1  jnb     loc_180110D21
0x1801107f7  mov     [rbp+57h+var_D0], rdi
0x1801107fb  lea     rcx, [rbp+57h+var_D0]
0x1801107ff  mov     [rsp+110h+var_D8], rdi
0x180110804  xorps   xmm0, xmm0
0x180110807  mov     [rbp+57h+var_8E], dil
0x18011080b  xorps   xmm1, xmm1
0x18011080e  mov     [rbp+57h+var_70], rdi
0x180110812  movdqa  xmmword ptr [rbp+57h+var_B0], xmm0
0x180110817  movdqa  [rbp+57h+var_A0], xmm1
0x18011081c  mov     [rbp+57h+var_90], 0
0x180110822  movdqa  xmmword ptr [rbp+57h+string], xmm0
0x180110827  mov     byte ptr [rsp+110h+var_E0], dil
0x18011082c  mov     rdi, [rbp+57h+var_C0]
0x180110830  mov     rax, [rdi]
0x180110833  mov     rbx, [rax+30h]
0x180110837  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18011083c  lea     r8, [rbp+57h+var_D0]
0x180110840  mov     edx, r14d
0x180110843  mov     rcx, rdi
0x180110846  mov     rax, rbx
0x180110849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011084e  mov     ebx, eax
0x180110850  test    eax, eax
0x180110852  js      loc_180110F27
0x180110858  mov     rdi, [rbp+57h+var_D0]
0x18011085c  lea     rcx, [rsp+110h+var_D8]
0x180110861  mov     rax, [rdi]
0x180110864  mov     rbx, [rax]
0x180110867  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18011086c  lea     r8, [rsp+110h+var_D8]
0x180110871  mov     rcx, rdi
0x180110874  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18011087b  mov     rax, rbx
0x18011087e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180110883  xor     edi, edi
0x180110885  mov     ebx, eax
0x180110887  test    eax, eax
0x180110889  js      loc_180110E9B
0x18011088f  mov     rcx, [rsp+110h+var_D8]
0x180110894  lea     rax, [rsp+110h+var_E0]
0x180110899  lea     r9, [rbp+57h+var_B0]
0x18011089d  mov     [rsp+110h+var_F0], rax
0x1801108a2  mov     r8, r13
0x1801108a5  mov     rdx, r12
0x1801108a8  call    ?MatchAndGetContentDecryptionModuleInfo@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEAUHSTRING__@@1AEAUMediaContentDecryptionModuleInfo@@PEA_N@Z; MatchAndGetContentDecryptionModuleInfo(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ *,MediaContentDecryptionModuleInfo &,bool *)
0x1801108ad  mov     ebx, eax
0x1801108af  test    eax, eax
0x1801108b1  js      loc_180110E0F
0x1801108b7  cmp     byte ptr [rsp+110h+var_E0], dil
0x1801108bc  jnz     short loc_1801108E2
0x1801108be  lea     rcx, [rbp+57h+var_B0]; this
0x1801108c2  call    ??1MediaContentDecryptionModuleInfo@@QEAA@XZ; MediaContentDecryptionModuleInfo::~MediaContentDecryptionModuleInfo(void)
0x1801108c7  lea     rcx, [rsp+110h+var_D8]
0x1801108cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801108d1  lea     rcx, [rbp+57h+var_D0]
0x1801108d5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801108da  inc     r14d
0x1801108dd  jmp     loc_1801107ED
0x1801108e2  cmp     byte ptr [rbp+57h+var_90], dil
0x1801108e6  jz      loc_18011098B
0x1801108ec  mov     rcx, [rbp+57h+var_B0+8]; HSTRING
0x1801108f0  call    ?DeployPackage@@YAJPEAUHSTRING__@@@Z; DeployPackage(HSTRING__ *)
0x1801108f5  mov     ebx, eax
0x1801108f7  test    eax, eax
0x1801108f9  jns     loc_18011098B
0x1801108ff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180110906  test    rcx, rcx
0x180110909  jnz     short loc_180110949
0x18011090b  mov     rax, cs:stru_1801FC290.__vftable
0x180110912  lea     rcx, stru_1801FC290
0x180110919  mov     edx, 7F0h
0x18011091e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180110925  mov     rax, [rax+8]
0x180110929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011092e  test    eax, eax
0x180110930  jnz     short loc_180110942
0x180110932  lea     rcx, stru_1801F8A30
0x180110939  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180110940  jmp     short loc_180110949
0x180110942  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180110949  cmp     [rcx+8], dil
0x18011094d  jz      short loc_180110974
0x18011094f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180110954  cmp     [rax+7CCh], ebx
0x18011095a  jz      short loc_180110974
0x18011095c  mov     r9d, ebx; int
0x18011095f  lea     rdx, aWindowsMediaPr_0; "Windows::Media::Protection::EMEStoreObj"...
0x180110966  mov     r8d, 6Ch ; 'l'; int
0x18011096c  mov     rcx, rax; this
0x18011096f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180110974  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18011097b  jb      loc_180110FC8
0x180110981  mov     edx, 13h
0x180110986  jmp     loc_180110FAA
0x18011098b  lea     rcx, [rsi+48h]
0x18011098f  call    ?InternalRelease@?$ComPtr@VCMFInprocLifetimeAssociation@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(void)
0x180110994  mov     rcx, [rbp+57h+string+8]; string
0x180110998  xor     edx, edx; length
0x18011099a  call    cs:__imp_WindowsGetStringRawBuffer
0x1801109a0  mov     rdx, rax; unsigned __int16 *
0x1801109a3  lea     r8, [rsi+48h]; struct CMFInprocDllManager **
0x1801109a7  call    ?GetDllManager@CGlobalInprocDllManager@@QEAAJPEBGPEAPEAVCMFInprocDllManager@@@Z; CGlobalInprocDllManager::GetDllManager(ushort const *,CMFInprocDllManager * *)
0x1801109ac  mov     ebx, eax
0x1801109ae  test    eax, eax
0x1801109b0  jns     loc_180110A42
0x1801109b6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801109bd  test    rcx, rcx
0x1801109c0  jnz     short loc_180110A00
0x1801109c2  mov     rax, cs:stru_1801FC290.__vftable
0x1801109c9  lea     rcx, stru_1801FC290
0x1801109d0  mov     edx, 7F0h
0x1801109d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801109dc  mov     rax, [rax+8]
0x1801109e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801109e5  test    eax, eax
0x1801109e7  jnz     short loc_1801109F9
0x1801109e9  lea     rcx, stru_1801F8A30
0x1801109f0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1801109f7  jmp     short loc_180110A00
0x1801109f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180110a00  cmp     [rcx+8], dil
0x180110a04  jz      short loc_180110A2B
0x180110a06  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180110a0b  cmp     [rax+7CCh], ebx
0x180110a11  jz      short loc_180110A2B
0x180110a13  mov     r9d, ebx; int
0x180110a16  lea     rdx, aWindowsMediaPr_0; "Windows::Media::Protection::EMEStoreObj"...
0x180110a1d  mov     r8d, 6Fh ; 'o'; int
0x180110a23  mov     rcx, rax; this
0x180110a26  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180110a2b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180110a32  jb      loc_180110FC8
0x180110a38  mov     edx, 14h
0x180110a3d  jmp     loc_180110FAA
0x180110a42  mov     rax, [rbp+57h+string+8]
0x180110a46  lea     rdx, [rbp+57h+var_60]; HSTRING *
0x180110a4a  mov     rcx, r15; newString
0x180110a4d  mov     qword ptr [rbp+57h+var_60.header_.Reserved], rax
0x180110a51  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180110a56  mov     ebx, eax
0x180110a58  test    eax, eax
0x180110a5a  jns     loc_180110AEC
0x180110a60  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180110a67  test    rcx, rcx
0x180110a6a  jnz     short loc_180110AAA
0x180110a6c  mov     rax, cs:stru_1801FC290.__vftable
0x180110a73  lea     rcx, stru_1801FC290
  ... truncated ...
```
