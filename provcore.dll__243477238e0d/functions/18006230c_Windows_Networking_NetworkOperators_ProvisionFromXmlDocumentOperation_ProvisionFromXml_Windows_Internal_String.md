# Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentOperation::ProvisionFromXml(Windows::Internal::StringReference const &,uchar &,Windows::Internal::String &)

- ea: `0x18006230c`
- end: `0x180062ada`
- name: `?ProvisionFromXml@ProvisionFromXmlDocumentOperation@NetworkOperators@Networking@Windows@@AEAAJAEBVStringReference@Internal@4@AEAEAEAVString@64@@Z`
- size: `1998`
- prototype: `HRESULT __fastcall(Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentOperation *this, const Windows::Internal::StringReference *ProvisioningXml, unsigned __int8 *AllElementsProvisioned, Windows::Internal::String *ResultsXml)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180060e94`

## callees

- `0x18000106c`
- `0x180001430`
- `0x180002790`
- `0x18000af94`
- `0x180011844`
- `0x180011cfc`
- `0x180012748`
- `0x180012770`
- `0x1800127cc`
- `0x180012988`
- `0x18005b4a4`
- `0x180060a1c`
- `0x180060c28`
- `0x180060ec8`
- `0x18006155c`
- `0x180061770`
- `0x180061e10`
- `0x18006230c`
- `0x180062d70`
- `0x1800641cc`
- `0x1800678c8`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062694`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006286b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800629c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062694`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006286b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800629c8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180062421`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180062421`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180062371`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180062371`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180062ab2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180062ab2`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
HRESULT __fastcall Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentOperation::ProvisionFromXml(
        Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentOperation *this,
        const Windows::Internal::StringReference *ProvisioningXml,
        bool *AllElementsProvisioned,
        Windows::Internal::String *ResultsXml)
{
  HRESULT result; // eax
  const _EVENT_DESCRIPTOR *v9; // rdx
  int Instance; // edi
  IProvisioningEngine *ptr; // rdi
  HRESULT (__fastcall *CreateDocumentFromStream)(IProvisioningEngine *, IStream *, IProvisioningDocument **); // rbx
  HRESULT v13; // eax
  wchar_t *v14; // rcx
  WPP_PROJECT_CONTROL_BLOCK *v15; // r10
  const wchar_t *v16; // rax
  __int64 v17; // r10
  bool v18; // bl
  unsigned __int16 v19; // dx
  int UserConsent; // eax
  bool v21; // bl
  wchar_t *SignerDisplayName; // rax
  const wchar_t *v23; // rax
  __int64 v24; // r9
  int v25; // eax
  Windows::Internal::_StringDetail::dummy_t v26; // r8
  const wchar_t *v27; // rbx
  std::wstring *p_m_callerAppId; // rcx
  const wchar_t *v29; // rax
  const _GUID *v30; // r8
  const _GUID *v31; // r9
  std::wstring *v32; // rcx
  bool userAllowed; // [rsp+40h] [rbp-79h] BYREF
  wil::unique_call<void (__cdecl*)(void),&CoUninitialize,1> coUninit; // [rsp+41h] [rbp-78h]
  _tlgWrapSz<unsigned short> pEventMetadata; // [rsp+48h] [rbp-71h] BYREF
  _tlgWrapperByVal<8> v36; // [rsp+50h] [rbp-69h] BYREF
  std::wstring rhs; // [rsp+58h] [rbp-61h] BYREF
  wchar_t *errorOccured; // [rsp+78h] [rbp-41h] BYREF
  wchar_t *str; // [rsp+80h] [rbp-39h] BYREF
  Microsoft::WRL::ComPtr<IProvisioningDocument> spDocument; // [rsp+88h] [rbp-31h] BYREF
  Microsoft::WRL::ComPtr<IProvisioningEngine> spEngine; // [rsp+90h] [rbp-29h] BYREF
  Microsoft::WRL::ComPtr<IStream> spStream; // [rsp+98h] [rbp-21h] BYREF
  PROVISIONING_DOCUMENT_SIGNATURE_INFO signatureInfo; // [rsp+A0h] [rbp-19h] BYREF

  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x14u, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids);
  }
  result = CoInitializeEx(0, 0);
  if ( result >= 0 )
  {
    coUninit.m_call = 1;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x15u, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids);
    }
    spStream.ptr_ = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spStream);
    Instance = WcmProvisioningUtil::PrepareStreamFromString(ProvisioningXml, &spStream.ptr_);
    spEngine.ptr_ = 0;
    if ( Instance >= 0 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x16u, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spEngine);
      Instance = CoCreateInstance(
                   &CLSID_ProvisioningEngine,
                   0,
                   4u,
                   &GUID_217700e0_1001_11df_adb9_f4ce462d9137,
                   (LPVOID *)&spEngine.ptr_);
      if ( Instance >= 0 )
      {
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x17u, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids);
        }
        errorOccured = (wchar_t *)spEngine.ptr_;
        if ( spEngine.ptr_ )
          spEngine.ptr_->AddRef(spEngine.ptr_);
        Instance = AllowImpersonation<IProvisioningDocument>((const Microsoft::WRL::ComPtr<IProvisioningEngine>)&errorOccured);
      }
    }
    spDocument.ptr_ = 0;
    if ( Instance < 0 )
      goto LABEL_103;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x18u, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids);
    }
    ptr = spEngine.ptr_;
    CreateDocumentFromStream = spEngine.ptr_->CreateDocumentFromStream;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spDocument);
    v13 = CreateDocumentFromStream(ptr, spStream.ptr_, &spDocument.ptr_);
    Instance = v13;
    if ( v13 < 0 )
    {
      ProvisioningAgentOriginateError(v13);
      str = 0;
LABEL_112:
      v27 = &sourceString;
      if ( (Microsoft_Windows_NetworkProvisioningEnableBits[0] & 0x4000) != 0 )
      {
        p_m_callerAppId = &this->m_callerAppId;
        if ( this->m_callerAppId._Mypair._Myval2._Mysize )
          v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&p_m_callerAppId->_Mypair._Myval2);
        else
          v29 = &sourceString;
        McTemplateU0zd_EtwEventWriteTransfer((_MCGEN_TRACE_CONTEXT *)p_m_callerAppId, v9, v29, Instance);
      }
      if ( Tlgg_hWcmProvisioningLoggingProviderProv.LevelPlus1 > 5
        && tlgKeywordOn((const _tlgProvider_t *)v14, 0x200000000000uLL) )
      {
        v36.Value = 2048;
        v32 = &this->m_callerAppId;
        if ( this->m_callerAppId._Mypair._Myval2._Mysize )
          v27 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v32->_Mypair._Myval2);
        pEventMetadata.Psz = v27;
        LODWORD(errorOccured) = Instance;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
          (const _tlgProvider_t *)v32,
          &tlgEvent_6._tlgChannel,
          v30,
          v31,
          (const _tlgWrapperByVal<4> *)&errorOccured,
          &pEventMetadata,
          &v36);
      }
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x2Au, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids, Instance);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spDocument);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spEngine);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spStream);
      CoUninitialize();
      return Instance;
    }
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x19u, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids);
    }
    errorOccured = (wchar_t *)spDocument.ptr_;
    if ( spDocument.ptr_ )
      spDocument.ptr_->AddRef(spDocument.ptr_);
    Instance = AllowImpersonation<IProvisioningDocument>((const Microsoft::WRL::ComPtr<IProvisioningEngine>)&errorOccured);
    if ( Instance < 0 )
      goto LABEL_103;
    if ( this->m_isSourceTrusted )
    {
      MBAE::GetCarrierFromNetworkAccountId((std::wstring *)&signatureInfo, &this->m_mbaeNetworkAccountId);
      if ( signatureInfo.SignerDisplayName )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
          {
            v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((std::_String_val<std::_Simple_types<unsigned short> > *)&signatureInfo);
            WPP_SF_S(*(_QWORD *)(v17 + 16), 0x1Bu, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids, v16);
            v15 = WPP_GLOBAL_Control;
          }
          if ( v15 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v15->ReserveSpace[28] & 0x10) != 0 )
            WPP_SF_(v15->Control.Logger, 0x1Cu, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids);
        }
        errorOccured = 0;
        Instance = spDocument.ptr_->GetCarrierId(spDocument.ptr_, &errorOccured);
        if ( Instance >= 0 )
        {
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
          {
            WPP_SF_S(
              WPP_GLOBAL_Control->Control.Logger,
              0x1Du,
              WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids,
              errorOccured);
          }
          std::wstring::wstring(&rhs, errorOccured);
          v18 = WcmProvisioningUtil::AreEqualCaseInsensitive((const std::wstring *)&signatureInfo, &rhs);
          std::wstring::_Tidy_deallocate(&rhs);
          if ( !v18 )
          {
            if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x1Eu, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids);
            }
            Instance = -2147024891;
          }
          CoTaskMemFree(errorOccured);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x1Au, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids);
        }
        Instance = -2147024883;
      }
      std::wstring::_Tidy_deallocate((std::wstring *)&signatureInfo);
      if ( Instance < 0 )
        goto LABEL_103;
      if ( this->m_isSourceTrusted )
        goto LABEL_90;
    }
    if ( !CallingApp::IsDesktopApp(this->m_parentWindow) )
    {
LABEL_90:
      v14 = (wchar_t *)WPP_GLOBAL_Control;
LABEL_91:
      if ( v14 != (wchar_t *)&WPP_GLOBAL_Control && (v14[14] & 0x10) != 0 )
        WPP_SF_(*((_QWORD *)v14 + 2), 0x26u, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids);
      LODWORD(errorOccured) = 0;
      Instance = spDocument.ptr_->Provision(spDocument.ptr_, (int *)&errorOccured);
      *AllElementsProvisioned = (_DWORD)errorOccured == 0;
      if ( Instance >= 0 )
      {
        if ( this->m_callerAppId._Mypair._Myval2._Mysize )
        {
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x27u, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids);
          }
          v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this->m_callerAppId._Mypair._Myval2);
          v25 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v24 + 64LL))(v24, v23);
          v14 = (wchar_t *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) == 0 )
          {
            goto LABEL_104;
          }
          WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x28u, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids, v25);
        }
        str = 0;
        v14 = (wchar_t *)WPP_GLOBAL_Control;
        goto LABEL_105;
      }
LABEL_103:
      v14 = (wchar_t *)WPP_GLOBAL_Control;
      goto LABEL_104;
    }
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x1Fu, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids);
    }
    memset(&signatureInfo, 0, sizeof(signatureInfo));
    Instance = spDocument.ptr_->GetSignatureInformation(spDocument.ptr_, &signatureInfo);
    if ( Instance < 0 )
      goto LABEL_103;
    if ( signatureInfo.DocumentIsSigned )
    {
      if ( signatureInfo.SignerIsTrusted )
      {
LABEL_82:
        v14 = (wchar_t *)WPP_GLOBAL_Control;
        goto LABEL_83;
      }
      if ( signatureInfo.CertHasExtendedValidation )
      {
        userAllowed = 1;
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
        {
          WPP_SF_S(
            WPP_GLOBAL_Control->Control.Logger,
            0x21u,
            WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids,
            signatureInfo.SignerDisplayName);
        }
        UserConsent = Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentOperation::GetUserConsent(
                        this,
                        signatureInfo.SignerDisplayName,
                        &userAllowed);
        Instance = UserConsent;
        v21 = userAllowed;
        v14 = (wchar_t *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
        {
          WPP_SF_dd(
            WPP_GLOBAL_Control->Control.Logger,
            0x22u,
            WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids,
            userAllowed,
            UserConsent);
          v14 = (wchar_t *)WPP_GLOBAL_Control;
        }
        if ( Instance >= 0 && v21 )
        {
LABEL_83:
          SignerDisplayName = signatureInfo.SignerDisplayName;
          if ( signatureInfo.SignerDisplayName )
          {
            if ( v14 != (wchar_t *)&WPP_GLOBAL_Control && (v14[14] & 0x10) != 0 )
            {
              WPP_SF_S(
                *((_QWORD *)v14 + 2),
                0x25u,
                WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids,
                signatureInfo.SignerDisplayName);
              SignerDisplayName = signatureInfo.SignerDisplayName;
            }
            CoTaskMemFree(SignerDisplayName);
            v14 = (wchar_t *)WPP_GLOBAL_Control;
          }
          if ( Instance < 0 )
          {
LABEL_104:
            str = 0;
            if ( Instance < 0 )
              goto LABEL_112;
LABEL_105:
            if ( v14 != (wchar_t *)&WPP_GLOBAL_Control && (v14[14] & 0x10) != 0 )
              WPP_SF_(*((_QWORD *)v14 + 2), 0x29u, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids);
            Instance = spDocument.ptr_->GetProvisioningResults(spDocument.ptr_, &str);
            if ( Instance >= 0 )
              Instance = Windows::Internal::String::Initialize<unsigned short *>(
                           ResultsXml,
                           (const wchar_t **)&str,
                           v26);
            v14 = str;
            if ( str )
              CoTaskMemFree(str);
            goto LABEL_112;
          }
          goto LABEL_91;
        }
        Instance = -2112421882;
        if ( v14 == (wchar_t *)&WPP_GLOBAL_Control || (v14[14] & 2) == 0 )
          goto LABEL_81;
        v19 = 35;
      }
      else
      {
        Instance = -2112421875;
        v14 = (wchar_t *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control->ReserveSpace[28] & 2) == 0 )
        {
          goto LABEL_81;
        }
        v19 = 36;
      }
    }
    else
    {
      Instance = -2112421874;
      v14 = (wchar_t *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control->ReserveSpace[28] & 2) == 0 )
      {
        goto LABEL_81;
      }
      v19 = 32;
    }
    WPP_SF_d(*((_QWORD *)v14 + 2), v19, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids, Instance);
LABEL_81:
    ProvisioningAgentOriginateError(Instance);
    goto LABEL_82;
  }
  return result;
}

```

## disassembly

```asm
0x18006230c  push    rbp
0x18006230e  push    rbx
0x18006230f  push    rsi
0x180062310  push    rdi
0x180062311  push    r12
0x180062313  push    r13
0x180062315  push    r14
0x180062317  push    r15
0x180062319  lea     rbp, [rsp-1Fh]
0x18006231e  sub     rsp, 0D8h
0x180062325  mov     rax, cs:__security_cookie
0x18006232c  xor     rax, rsp
0x18006232f  mov     [rbp+57h+var_50], rax
0x180062333  mov     r15, ResultsXml
0x180062336  mov     r14, AllElementsProvisioned
0x180062339  mov     rbx, ProvisioningXml
0x18006233c  mov     rsi, this
0x18006233f  lea     r13, WPP_GLOBAL_Control; __annotation("TMF:",
0x180062346  mov     this, cs:WPP_GLOBAL_Control
0x18006234d  cmp     this, r13
0x180062350  jz      short loc_18006236D
0x180062352  test    byte ptr [this+1Ch], 10h
0x180062356  jz      short loc_18006236D
0x180062358  mov     edx, 14h; id
0x18006235d  lea     AllElementsProvisioned, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids; TraceGuid
0x180062364  mov     this, [this+10h]; Logger
0x180062368  call    WPP_SF_
0x18006236d  xor     edx, edx; dwCoInit
0x18006236f  xor     ecx, ecx; pvReserved
0x180062371  call    cs:__imp_CoInitializeEx
0x180062377  xor     r12d, r12d
0x18006237a  test    eax, eax
0x18006237c  js      loc_180062ABA
0x180062382  mov     [rbp+57h+coUninit.m_call], 1
0x180062386  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18006238d  cmp     this, r13
0x180062390  jz      short loc_1800623AD
0x180062392  test    byte ptr [this+1Ch], 10h
0x180062396  jz      short loc_1800623AD
0x180062398  lea     edx, [r12+15h]; id
0x18006239d  lea     AllElementsProvisioned, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids; TraceGuid
0x1800623a4  mov     this, [this+10h]; Logger
0x1800623a8  call    WPP_SF_
0x1800623ad  mov     [rbp+57h+spStream.ptr_], r12
0x1800623b1  lea     this, [rbp+57h+spStream]; this
0x1800623b5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800623ba  lea     ProvisioningXml, [rbp+57h+spStream]; ppStream
0x1800623be  mov     this, rbx; StringRef
0x1800623c1  call    ?PrepareStreamFromString@WcmProvisioningUtil@@YAJAEBVStringReference@Internal@Windows@@PEAPEAUIStream@@@Z; WcmProvisioningUtil::PrepareStreamFromString(Windows::Internal::StringReference const &,IStream * *)
0x1800623c6  mov     edi, eax
0x1800623c8  mov     [rbp+57h+spEngine.ptr_], r12
0x1800623cc  test    eax, eax
0x1800623ce  js      loc_180062479
0x1800623d4  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800623db  cmp     this, r13
0x1800623de  jz      short loc_1800623FB
0x1800623e0  test    byte ptr [this+1Ch], 10h
0x1800623e4  jz      short loc_1800623FB
0x1800623e6  mov     edx, 16h; id
0x1800623eb  lea     AllElementsProvisioned, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids; TraceGuid
0x1800623f2  mov     this, [this+10h]; Logger
0x1800623f6  call    WPP_SF_
0x1800623fb  lea     this, [rbp+57h+spEngine]; this
0x1800623ff  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180062404  lea     rax, [rbp+57h+spEngine]
0x180062408  mov     [rsp+110h+ppv], rax; ppv
0x18006240d  lea     ResultsXml, _GUID_217700e0_1001_11df_adb9_f4ce462d9137; riid
0x180062414  xor     edx, edx; pUnkOuter
0x180062416  lea     r8d, [ProvisioningXml+4]; dwClsContext
0x18006241a  lea     this, CLSID_ProvisioningEngine; rclsid
0x180062421  call    cs:__imp_CoCreateInstance
0x180062427  mov     edi, eax
0x180062429  test    eax, eax
0x18006242b  js      short loc_180062479
0x18006242d  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180062434  cmp     this, r13
0x180062437  jz      short loc_180062454
0x180062439  test    byte ptr [this+1Ch], 10h
0x18006243d  jz      short loc_180062454
0x18006243f  mov     edx, 17h; id
0x180062444  lea     AllElementsProvisioned, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids; TraceGuid
0x18006244b  mov     this, [this+10h]; Logger
0x18006244f  call    WPP_SF_
0x180062454  mov     this, [rbp+57h+spEngine.ptr_]
0x180062458  mov     [rbp+57h+errorOccured], this
0x18006245c  test    this, this
0x18006245f  jz      short loc_18006246E
0x180062461  mov     rax, [this]
0x180062464  mov     rax, [rax+8]
0x180062468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006246d  nop
0x18006246e  lea     this, [rbp+57h+errorOccured]; spObj
0x180062472  call    ??$AllowImpersonation@UIProvisioningDocument@@@@YAJV?$ComPtr@UIProvisioningDocument@@@WRL@Microsoft@@@Z; AllowImpersonation<IProvisioningDocument>(Microsoft::WRL::ComPtr<IProvisioningDocument>)
0x180062477  mov     edi, eax
0x180062479  mov     [rbp+57h+spDocument.ptr_], r12
0x18006247d  test    edi, edi
0x18006247f  js      loc_180062968
0x180062485  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18006248c  cmp     this, r13
0x18006248f  jz      short loc_1800624AC
0x180062491  test    byte ptr [this+1Ch], 10h
0x180062495  jz      short loc_1800624AC
0x180062497  mov     edx, 18h; id
0x18006249c  lea     AllElementsProvisioned, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids; TraceGuid
0x1800624a3  mov     this, [this+10h]; Logger
0x1800624a7  call    WPP_SF_
0x1800624ac  mov     rdi, [rbp+57h+spEngine.ptr_]
0x1800624b0  mov     rax, [rdi]
0x1800624b3  mov     rbx, [rax+18h]
0x1800624b7  lea     this, [rbp+57h+spDocument]; this
0x1800624bb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800624c0  lea     AllElementsProvisioned, [rbp+57h+spDocument]
0x1800624c4  mov     ProvisioningXml, [rbp+57h+spStream.ptr_]
0x1800624c8  mov     this, rdi
0x1800624cb  mov     rax, rbx
0x1800624ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800624d3  mov     edi, eax
0x1800624d5  test    eax, eax
0x1800624d7  jns     short loc_1800624E9
0x1800624d9  mov     ecx, eax; hr
0x1800624db  call    ?ProvisioningAgentOriginateError@@YAXJ@Z; ProvisioningAgentOriginateError(long)
0x1800624e0  mov     [rbp+57h+str], r12
0x1800624e4  jmp     loc_1800629CE
0x1800624e9  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800624f0  cmp     this, r13
0x1800624f3  jz      short loc_180062510
0x1800624f5  test    byte ptr [this+1Ch], 10h
0x1800624f9  jz      short loc_180062510
0x1800624fb  mov     edx, 19h; id
0x180062500  lea     AllElementsProvisioned, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids; TraceGuid
0x180062507  mov     this, [this+10h]; Logger
0x18006250b  call    WPP_SF_
0x180062510  mov     this, [rbp+57h+spDocument.ptr_]
0x180062514  mov     [rbp+57h+errorOccured], this
0x180062518  test    this, this
0x18006251b  jz      short loc_18006252A
0x18006251d  mov     rax, [this]
0x180062520  mov     rax, [rax+8]
0x180062524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062529  nop
0x18006252a  lea     this, [rbp+57h+errorOccured]; spObj
0x18006252e  call    ??$AllowImpersonation@UIProvisioningDocument@@@@YAJV?$ComPtr@UIProvisioningDocument@@@WRL@Microsoft@@@Z; AllowImpersonation<IProvisioningDocument>(Microsoft::WRL::ComPtr<IProvisioningDocument>)
0x180062533  mov     edi, eax
0x180062535  test    eax, eax
0x180062537  js      loc_180062968
0x18006253d  cmp     [rsi+80h], r12b
0x180062544  jz      loc_1800626B9
0x18006254a  lea     ProvisioningXml, [rsi+88h]; MbaeNetworkAccountId
0x180062551  lea     this, [rbp+57h+signatureInfo]; result
0x180062555  call    ?GetCarrierFromNetworkAccountId@MBAE@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; MBAE::GetCarrierFromNetworkAccountId(std::wstring const &)
0x18006255a  nop
0x18006255b  cmp     [rbp+57h+signatureInfo.SignerDisplayName], r12
0x18006255f  jnz     short loc_180062592
0x180062561  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180062568  cmp     this, r13
0x18006256b  jz      short loc_180062588
0x18006256d  test    byte ptr [this+1Ch], 2
0x180062571  jz      short loc_180062588
0x180062573  mov     edx, 1Ah; id
0x180062578  lea     AllElementsProvisioned, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids; TraceGuid
0x18006257f  mov     this, [this+10h]; Logger
0x180062583  call    WPP_SF_
0x180062588  mov     edi, 8007000Dh
0x18006258d  jmp     loc_18006269B
0x180062592  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180062599  cmp     r10, r13
0x18006259c  jz      short loc_1800625EE
0x18006259e  test    byte ptr [r10+1Ch], 10h
0x1800625a3  jz      short loc_1800625CD
0x1800625a5  lea     this, [rbp+57h+signatureInfo]; this
0x1800625a9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800625ae  mov     ResultsXml, rax; _a1
0x1800625b1  mov     edx, 1Bh; id
0x1800625b6  lea     AllElementsProvisioned, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids; TraceGuid
0x1800625bd  mov     this, [r10+10h]; Logger
0x1800625c1  call    WPP_SF_S
0x1800625c6  mov     r10, cs:WPP_GLOBAL_Control
0x1800625cd  cmp     r10, r13; __annotation("TMF:",
0x1800625d0  jz      short loc_1800625EE
0x1800625d2  test    byte ptr [r10+1Ch], 10h
0x1800625d7  jz      short loc_1800625EE
0x1800625d9  mov     edx, 1Ch; id
0x1800625de  lea     AllElementsProvisioned, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids; TraceGuid
0x1800625e5  mov     this, [r10+10h]; Logger
0x1800625e9  call    WPP_SF_
0x1800625ee  mov     [rbp+57h+errorOccured], r12
0x1800625f2  mov     this, [rbp+57h+spDocument.ptr_]
0x1800625f6  mov     rax, [this]
0x1800625f9  lea     ProvisioningXml, [rbp+57h+errorOccured]
0x1800625fd  mov     rax, [rax+20h]
0x180062601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062606  mov     edi, eax
0x180062608  test    eax, eax
0x18006260a  js      loc_18006269B
0x180062610  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180062617  cmp     this, r13
0x18006261a  jz      short loc_18006263B
0x18006261c  test    byte ptr [this+1Ch], 10h
0x180062620  jz      short loc_18006263B
0x180062622  mov     edx, 1Dh; id
0x180062627  mov     ResultsXml, [rbp+57h+errorOccured]; _a1
0x18006262b  lea     AllElementsProvisioned, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids; TraceGuid
0x180062632  mov     this, [this+10h]; Logger
0x180062636  call    WPP_SF_S
0x18006263b  mov     ProvisioningXml, [rbp+57h+errorOccured]; _Ptr
0x18006263f  lea     this, [rbp+57h+rhs]; this
0x180062643  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180062648  lea     ProvisioningXml, [rbp+57h+rhs]; rhs
0x18006264c  lea     this, [rbp+57h+signatureInfo]; lhs
0x180062650  call    ?AreEqualCaseInsensitive@WcmProvisioningUtil@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; WcmProvisioningUtil::AreEqualCaseInsensitive(std::wstring const &,std::wstring const &)
0x180062655  mov     bl, al
0x180062657  lea     this, [rbp+57h+rhs]; this
0x18006265b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180062660  test    bl, bl
0x180062662  jnz     short loc_180062690
0x180062664  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18006266b  cmp     this, r13
0x18006266e  jz      short loc_18006268B
0x180062670  test    byte ptr [this+1Ch], 2
0x180062674  jz      short loc_18006268B
0x180062676  mov     edx, 1Eh; id
0x18006267b  lea     AllElementsProvisioned, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids; TraceGuid
0x180062682  mov     this, [this+10h]; Logger
0x180062686  call    WPP_SF_
0x18006268b  mov     edi, 80070005h
0x180062690  mov     this, [rbp+57h+errorOccured]; pv
0x180062694  call    cs:__imp_CoTaskMemFree
0x18006269a  nop
0x18006269b  lea     this, [rbp+57h+signatureInfo]; this
0x18006269f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800626a4  test    edi, edi
0x1800626a6  js      loc_180062968
0x1800626ac  cmp     [rsi+80h], r12b
0x1800626b3  jnz     loc_180062881
0x1800626b9  mov     this, [rsi+0A8h]; hwnd
0x1800626c0  call    ?IsDesktopApp@CallingApp@@YA_NPEAUHWND__@@@Z; CallingApp::IsDesktopApp(HWND__ *)
0x1800626c5  test    al, al
0x1800626c7  jz      loc_180062881
0x1800626cd  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800626d4  cmp     this, r13
0x1800626d7  jz      short loc_1800626F4
0x1800626d9  test    byte ptr [this+1Ch], 10h
0x1800626dd  jz      short loc_1800626F4
0x1800626df  mov     edx, 1Fh; id
0x1800626e4  lea     AllElementsProvisioned, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids; TraceGuid
0x1800626eb  mov     this, [this+10h]; Logger
0x1800626ef  call    WPP_SF_
0x1800626f4  xorps   xmm0, xmm0
0x1800626f7  xor     eax, eax
0x1800626f9  movups  xmmword ptr [rbp+57h+signatureInfo.DocumentIsSigned], xmm0
0x1800626fd  mov     [rbp+57h+signatureInfo.SignerDisplayName], rax
0x180062701  mov     this, [rbp+57h+spDocument.ptr_]
0x180062705  mov     rax, [this]
0x180062708  lea     ProvisioningXml, [rbp+57h+signatureInfo]
0x18006270c  mov     rax, [rax+30h]
0x180062710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062715  mov     edi, eax
0x180062717  test    eax, eax
0x180062719  js      loc_180062968
0x18006271f  cmp     [rbp+57h+signatureInfo.DocumentIsSigned], r12d
0x180062723  jnz     short loc_18006274E
0x180062725  mov     edi, 8217000Eh
0x18006272a  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180062731  cmp     this, r13
0x180062734  jz      loc_18006282A
0x18006273a  test    byte ptr [this+1Ch], 2
0x18006273e  jz      loc_18006282A
0x180062744  mov     edx, 20h ; ' '
0x180062749  jmp     loc_180062817
0x18006274e  cmp     [rbp+57h+signatureInfo.SignerIsTrusted], r12d
0x180062752  jnz     loc_180062831
0x180062758  cmp     [rbp+57h+signatureInfo.CertHasExtendedValidation], r12d
0x18006275c  jz      loc_1800627FB
0x180062762  mov     [rbp+57h+userAllowed], 1
0x180062766  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18006276d  cmp     this, r13
0x180062770  jz      short loc_180062791
0x180062772  test    byte ptr [this+1Ch], 8
0x180062776  jz      short loc_180062791
0x180062778  mov     edx, 21h ; '!'; id
0x18006277d  mov     ResultsXml, [rbp+57h+signatureInfo.SignerDisplayName]; _a1
0x180062781  lea     AllElementsProvisioned, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids; TraceGuid
0x180062788  mov     this, [this+10h]; Logger
0x18006278c  call    WPP_SF_S
0x180062791  lea     AllElementsProvisioned, [rbp+57h+userAllowed]; UserHasAllowed
0x180062795  mov     ProvisioningXml, [rbp+57h+signatureInfo.SignerDisplayName]; SignerDisplayName
0x180062799  mov     this, rsi; this
0x18006279c  call    ?GetUserConsent@ProvisionFromXmlDocumentOperation@NetworkOperators@Networking@Windows@@AEAAJPEBGAEA_N@Z; Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentOperation::GetUserConsent(ushort const *,bool &)
0x1800627a1  mov     edi, eax
0x1800627a3  movzx   ebx, [rbp+57h+userAllowed]; __annotation("TMF:",
0x1800627a7  mov     this, cs:WPP_GLOBAL_Control
0x1800627ae  cmp     this, r13
0x1800627b1  jz      short loc_1800627DC
0x1800627b3  test    byte ptr [this+1Ch], 10h
0x1800627b7  jz      short loc_1800627DC
0x1800627b9  mov     r9d, ebx; _a1
0x1800627bc  mov     edx, 22h ; '"'; id
0x1800627c1  mov     dword ptr [rsp+110h+ppv], eax; _a2
0x1800627c5  lea     AllElementsProvisioned, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids; TraceGuid
0x1800627cc  mov     this, [this+10h]; Logger
  ... truncated ...
```
