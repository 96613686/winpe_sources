# CoMarshalInterface

- ea: `0x18006ef60`
- end: `0x18006f8bd`
- name: `CoMarshalInterface`
- size: `2397`
- prototype: `HRESULT __stdcall(LPSTREAM pStm, const IID *const riid, LPUNKNOWN pUnk, DWORD dwDestContext, LPVOID pvDestContext, DWORD mshlflags)`
- caller_count: `20`
- callee_count: `27`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e3a0`
- `0x180022fb8`
- `0x180023900`
- `0x180024664`
- `0x18006e440`
- `0x18006f910`
- `0x1800935dc`
- `0x1800a1300`
- `0x1800a4ca8`
- `0x1800a67c0`
- `0x1800b4fb0`
- `0x1800db2c8`
- `0x1800e24b0`
- `0x18015c620`
- `0x18016349c`
- `0x180176ab8`
- `0x18017dbd0`
- `0x1801bd524`
- `0x1801d4e20`
- `0x1801d5a20`

## callees

- `0x180006570`
- `0x180008b90`
- `0x18000b408`
- `0x1800188a0`
- `0x18001d0e8`
- `0x18001f124`
- `0x180032c10`
- `0x180034270`
- `0x180036038`
- `0x18003a8bc`
- `0x18004768c`
- `0x18006ef60`
- `0x1800865b8`
- `0x18008db2c`
- `0x1800a09a0`
- `0x1800d0644`
- `0x1800d18f4`
- `0x1800ecaa8`
- `0x1800f56b8`
- `0x1800f5d04`
- `0x180114b74`
- `0x18014d5f4`
- `0x1801999b0`
- `0x18019a654`
- `0x1801a85d0`
- `0x1801ab028`
- `0x180255010`

## import_xrefs

- `ntdll!RtlApplicationVerifierStop` at `0x18006f049`
- `ntdll!RtlApplicationVerifierStop` at `0x18006f12d`
- `ntdll!RtlApplicationVerifierStop` at `0x18006f3a0`
- `ntdll!RtlApplicationVerifierStop` at `0x18006f566`
- `ntdll!RtlApplicationVerifierStop` at `0x18006f049`
- `ntdll!RtlApplicationVerifierStop` at `0x18006f12d`
- `ntdll!RtlApplicationVerifierStop` at `0x18006f3a0`
- `ntdll!RtlApplicationVerifierStop` at `0x18006f566`
- `ntdll!RtlDllShutdownInProgress` at `0x18006efbc`
- `ntdll!RtlDllShutdownInProgress` at `0x18006f14a`
- `ntdll!RtlDllShutdownInProgress` at `0x18006efbc`
- `ntdll!RtlDllShutdownInProgress` at `0x18006f14a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006f4a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006f4a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18006f48f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18006f48f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18006f4e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18006f4e4`

## string_xrefs

- `0x18006f865`: `onecore\com\combase\dcomrem\marshal.hxx`
- `0x18006f068`: `onecore\com\combase\dcomrem\coapi.cxx`
- `0x18006f784`: `onecore\com\combase\dcomrem\coapi.cxx`
- `0x18006efc6`: `COM API or Proxy called during ExitProcess`
- `0x18006f0db`: `Details on why this is unrecommended`
- `0x18006f0ff`: `Using this COM API or entry point from the context of a user APC is not recommended`
- `0x18006f0f3`: `CoMarshalInterface`
- `0x18006f772`: `CoMarshalInterface`
- `0x18006f768`: `CoMarshalInterface: QI for INoMarshal succeeded.`
- `0x18006f03b`: `COM API or Proxy called from DllMain`
- `0x18006f359`: `Pointer to the COM object being marshaled.`
- `0x18006f4a2`: `ServiceMain`
- `0x18006f4f1`: `The name of the DLL that contains the v-tbl (du to dump). Heuristically, this is the service DLL`
- `0x18006f4fd`: `The IUnknown of the agile COM object that is being marshaled from a disconnectable context.`
- `0x18006f602`: `onecore\com\combase\common\internal\carefulqi.cpp`
- `0x18006f6be`: `onecore\com\combase\common\internal\carefulqi.cpp`

## pseudocode

```c
HRESULT __stdcall CoMarshalInterface(
        LPSTREAM pStm,
        const IID *const riid,
        LPUNKNOWN pUnk,
        DWORD dwDestContext,
        LPVOID pvDestContext,
        DWORD mshlflags)
{
  ComVerifierSettings::ComVerifierSettingsState *pSettingsState; // rax
  char *v11; // rdx
  unsigned __int64 v12; // rcx
  tagSOleTlsData *ReservedForOle; // rax
  bool v15; // al
  ExitProcessDiagnostics::MarshalingApiContext *p_exitProcessDiagnosticsContext; // rax
  unsigned int v17; // edx
  tagSOleTlsData *pData; // rax
  unsigned int v19; // edx
  int v20; // edi
  bool fCheckClassicMarshalingToUntrustedProcess; // cl
  void **v22; // rax
  HRESULT inited; // edi
  void *v24; // rcx
  CObjectContext *v25; // rax
  void *v26; // rdx
  CObjectContext *v27; // rcx
  IUnknown_vtbl *v28; // rdi
  IUnknown_vtbl *v29; // rdx
  tagSOleTlsData *v30; // rcx
  IStream_vtbl *v31; // rax
  wchar_t *v32; // rax
  int v33; // ebx
  tagSOleTlsData *v34; // rcx
  int v35; // eax
  wchar_t *v36; // rax
  unsigned __int64 v37; // rbx
  IUnknown_vtbl *v38; // rax
  TraceLevel v39; // edx
  CObjectContext *CurrentContext; // rax
  COleTls v41; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int offset[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 ulReturnObjectContainerAttribute; // [rsp+70h] [rbp-90h] BYREF
  Microsoft::WRL::ComPtr<IMarshalingStream> spMarshalingStream; // [rsp+78h] [rbp-88h] BYREF
  ExitProcessDiagnostics::MarshalingApiContext exitProcessDiagnosticsContext; // [rsp+80h] [rbp-80h] BYREF
  IContextMarshaler *pICM; // [rsp+90h] [rbp-70h] BYREF
  INoMarshal *pNoMarshal; // [rsp+98h] [rbp-68h] BYREF
  void *v48; // [rsp+A0h] [rbp-60h]
  CDestObjectWrapper DOW; // [rsp+A8h] [rbp-58h] BYREF
  _GUID modulePdbSignature; // [rsp+C8h] [rbp-38h] BYREF
  CGuidStr v51; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t Filename[8]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v53[512]; // [rsp+140h] [rbp+40h] BYREF
  void *retaddr; // [rsp+398h] [rbp+298h]

  pSettingsState = ComVerifierSettings::s_singleton._pSettingsState;
  v48 = pvDestContext;
  if ( ComVerifierSettings::s_singleton._pSettingsState )
  {
    if ( ComVerifierSettings::s_singleton._pSettingsState->_fEnableExitProcessChecks )
    {
      if ( RtlDllShutdownInProgress() )
      {
        v11 = "COM API or Proxy called during ExitProcess";
        v12 = 268436527;
LABEL_5:
        if ( gMockApplicationVerifierStop )
          gMockApplicationVerifierStop(
            v12,
            v11,
            0,
            (char *)Description4,
            0,
            (char *)Description4,
            0,
            (char *)Description4,
            0,
            (char *)Description4);
        else
          RtlApplicationVerifierStop(v12, v11, 0, Description4, 0, Description4, 0, Description4, 0, Description4);
        return wil::details::in1diag3::Return_Win32Msg(
                 retaddr,
                 0x441u,
                 "onecore\\com\\combase\\dcomrem\\coapi.cxx",
                 0x46Bu,
                 "Preemptive failure return from dangerous API usage under AppVerifier");
      }
      pSettingsState = ComVerifierSettings::s_singleton._pSettingsState;
    }
    if ( pSettingsState && pSettingsState->_fEnableDllMainChecks && pSettingsState->_pfnVerifierIsDllEntryActive(0) )
    {
      v11 = "COM API or Proxy called from DllMain";
      v12 = 268436481;
      goto LABEL_5;
    }
  }
  ReservedForOle = (tagSOleTlsData *)NtCurrentTeb()->ReservedForOle;
  v41._pData = ReservedForOle;
  if ( !ReservedForOle )
  {
    if ( COleTls::TLSAllocData(&v41) < 0 )
      goto LABEL_24;
    ReservedForOle = v41._pData;
  }
  if ( ComVerifierSettings::s_singleton._pSettingsState
    && ComVerifierSettings::s_singleton._pSettingsState->_fCheckUnrecommendedUsageFromAPC
    && ReservedForOle
    && ReservedForOle->cReentrancyFromUserAPC )
  {
    if ( gMockApplicationVerifierStop )
      gMockApplicationVerifierStop(
        268436497u,
        "Using this COM API or entry point from the context of a user APC is not recommended",
        (unsigned __int64)"CoMarshalInterface",
        "API or entry point",
        (unsigned __int64)"Usage from APC can cause sporadic failure in some scenarios",
        "Details on why this is unrecommended",
        0,
        (char *)Description4,
        0,
        (char *)Description4);
    else
      RtlApplicationVerifierStop(
        0x10000411u,
        "Using this COM API or entry point from the context of a user APC is not recommended",
        (PVOID)"CoMarshalInterface",
        "API or entry point",
        "Usage from APC can cause sporadic failure in some scenarios",
        "Details on why this is unrecommended",
        0,
        Description4,
        0,
        Description4);
  }
LABEL_24:
  v15 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExitProcessDiagnostics>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ExitProcessDiagnostics>::GetImpl'::`2'::impl)
     && RtlDllShutdownInProgress();
  exitProcessDiagnosticsContext.m_isInExitProcess = v15;
  exitProcessDiagnosticsContext.m_category = Marshaling;
  exitProcessDiagnosticsContext.m_callerAddress = retaddr;
  if ( v15 )
  {
    p_exitProcessDiagnosticsContext = (ExitProcessDiagnostics::MarshalingApiContext *)ExitProcessDiagnostics::ApiContext::s_current;
    if ( !ExitProcessDiagnostics::ApiContext::s_current )
    {
      p_exitProcessDiagnosticsContext = &exitProcessDiagnosticsContext;
      ExitProcessDiagnostics::ApiContext::s_current = &exitProcessDiagnosticsContext;
    }
    if ( p_exitProcessDiagnosticsContext == &exitProcessDiagnosticsContext )
    {
      v17 = ExitProcessDiagnostics::ApiContext::s_countOfDangerousUsageReported++;
      if ( v17 < 0x64 )
      {
        pData = 0;
        v41._pData = 0;
        offset[0] = 0;
        modulePdbSignature = 0;
        if ( retaddr )
        {
          TryGetModuleTracingInfoFromAddress(
            retaddr,
            (wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&wil::details::FreeProcessHeap,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > *)&v41,
            &modulePdbSignature,
            offset);
          pData = v41._pData;
        }
        ulReturnObjectContainerAttribute = (unsigned __int64)pData;
        ComTrace::MarshalInExitProcess<unsigned short const *,_GUID const &,unsigned int,_GUID const &>(
          (const wchar_t **)&ulReturnObjectContainerAttribute,
          &modulePdbSignature,
          offset,
          riid);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(void *),&wil::details::FreeProcessHeap,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *)&v41);
      }
    }
  }
  if ( pStm && pUnk )
  {
    if ( dwDestContext > 5 )
    {
      v19 = 1067;
      goto LABEL_119;
    }
    if ( pvDestContext && dwDestContext != 5 && dwDestContext != 2 )
    {
      v19 = 1068;
      goto LABEL_119;
    }
    if ( (mshlflags & 0x7FF8FFC0) != 0 )
    {
      v19 = 1069;
      goto LABEL_119;
    }
    v41._pData = 0;
    if ( ComVerifierSettings::s_singleton._pSettingsState
      && ComVerifierSettings::s_singleton._pSettingsState->_fCheckMarshalingToUntrustedProcess
      && dwDestContext - 3 > 1 )
    {
      if ( pUnk->QueryInterface(pUnk, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, (void **)&v41) < 0 )
      {
        if ( ComVerifierSettings::s_singleton._pSettingsState )
          fCheckClassicMarshalingToUntrustedProcess = ComVerifierSettings::s_singleton._pSettingsState->_fCheckClassicMarshalingToUntrustedProcess;
        else
          fCheckClassicMarshalingToUntrustedProcess = 0;
        v20 = fCheckClassicMarshalingToUntrustedProcess;
      }
      else
      {
        offset[0] = 2;
        v20 = 1;
        if ( (*((int (__fastcall **)(tagSOleTlsData *, unsigned int *))v41._pData->pvThreadBase + 5))(
               v41._pData,
               offset) >= 0 )
          v20 = offset[0] == 2;
        (*((void (__fastcall **)(tagSOleTlsData *))v41._pData->pvThreadBase + 2))(v41._pData);
      }
      if ( v20 )
      {
        *(_QWORD *)offset = 0;
        v22 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IMarshalingStream>>((Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IActivationCatalogContext> >)offset);
        if ( CarefullyQueryNewInterface(pStm, &GUID_d8f2f5e6_6102_4863_9f26_389a4676efde, v22) >= 0 )
        {
          ulReturnObjectContainerAttribute = 0;
          if ( (*(int (__fastcall **)(_QWORD, __int64, unsigned __int64 *))(**(_QWORD **)offset + 112LL))(
                 *(_QWORD *)offset,
                 2147483655LL,
                 &ulReturnObjectContainerAttribute) >= 0 )
          {
            if ( ulReturnObjectContainerAttribute )
            {
              if ( gMockApplicationVerifierStop )
                gMockApplicationVerifierStop(
                  1057u,
                  "An object marked as requiring full trust should not be marshaled to an untrusted process.",
                  (unsigned __int64)riid,
                  "Pointer to IID of interface being marshaled.",
                  (unsigned __int64)pUnk,
                  "Pointer to the COM object being marshaled.",
                  0,
                  0,
                  0,
                  0);
              else
                RtlApplicationVerifierStop(
                  0x421u,
                  "An object marked as requiring full trust should not be marshaled to an untrusted process.",
                  (PVOID)riid,
                  "Pointer to IID of interface being marshaled.",
                  pUnk,
                  "Pointer to the COM object being marshaled.",
                  0,
                  0,
                  0,
                  0);
            }
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)offset);
      }
    }
    inited = InitChannelIfNecessary();
    if ( inited < 0 )
    {
LABEL_117:
      ExitProcessDiagnostics::ApiContext::~ApiContext(&exitProcessDiagnosticsContext);
      return inited;
    }
    v24 = NtCurrentTeb()->ReservedForOle;
    if ( v24 )
    {
      v25 = (CObjectContext *)*((_QWORD *)v24 + 13);
      if ( !v25 )
        v25 = g_pMTAEmptyCtx;
      *((_QWORD *)v24 + 12) = v25;
    }
    else
    {
      v25 = g_pMTAEmptyCtx;
    }
    if ( v25 )
    {
      v26 = NtCurrentTeb()->ReservedForOle;
      if ( v26 )
      {
        v27 = (CObjectContext *)*((_QWORD *)v26 + 13);
        if ( !v27 )
          v27 = g_pMTAEmptyCtx;
        *((_QWORD *)v26 + 12) = v27;
      }
      else
      {
        v27 = g_pMTAEmptyCtx;
      }
      if ( (CObjectContext::GetFlags(v27) & 0x100) != 0
        && ComVerifierSettings::s_singleton._pSettingsState
        && ComVerifierSettings::s_singleton._pSettingsState->_fEnableVerifyChannelState )
      {
        v41._pData = 0;
        if ( CarefullyQueryNewInterface(pUnk, &GUID_94ea2b94_e9cc_49e0_c0ff_ee64ca8f5b90, (void **)&v41._pData) >= 0 )
        {
          v28 = pUnk->__vftable;
          v29 = pUnk->__vftable;
          *(_QWORD *)offset = 0;
          if ( GetModuleHandleExW(4u, (LPCWSTR)v29, (HMODULE *)offset)
            && GetProcAddress(*(HMODULE *)offset, "ServiceMain") )
          {
            wcscpy(Filename, L"Unknown");
            memset_0(v53, 0, 0x1F8u);
            GetModuleFileNameW(*(HMODULE *)offset, Filename, 0x104u);
            if ( gMockApplicationVerifierStop )
              gMockApplicationVerifierStop(
                268436525u,
                "Marshaling an agile object from a disconnectable context.",
                (unsigned __int64)pUnk,
                "The IUnknown of the agile COM object that is being marshaled from a disconnectable context.",
                (unsigned __int64)v28,
                "The v-tbl address pointed to by the object",
                (unsigned __int64)Filename,
                "The name of the DLL that contains the v-tbl (du to dump). Heuristically, this is the service DLL",
                0,
                (char *)Description4);
            else
              RtlApplicationVerifierStop(
                0x1000042Du,
                "Marshaling an agile object from a disconnectable context.",
                pUnk,
                "The IUnknown of the agile COM object that is being marshaled from a disconnectable context.",
                v28,
                "The v-tbl address pointed to by the object",
                Filename,
                "The name of the DLL that contains the v-tbl (du to dump). Heuristically, this is the service DLL",
                0,
                Description4);
          }
          wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>((wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (__cdecl*)(HINSTANCE__ *),&FreeLibrary,wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t> > *)offset);
        }
        v30 = v41._pData;
        if ( v41._pData )
        {
          v41._pData = 0;
          (*((void (__fastcall **)(tagSOleTlsData *))v30->pvThreadBase + 2))(v30);
        }
      }
    }
    v31 = pStm->__vftable;
    spMarshalingStream.ptr_ = 0;
    v41._pData = 0;
    if ( v31->QueryInterface(pStm, &GUID_334d391f_0e79_3b15_c9ff_eac65dd07c42, (void **)&v41._pData) < 0 )
    {
      v33 = 2;
    }
    else
    {
      if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
        || gfEnableTracing && IsWppLevelEnabled((TraceLevel)(Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 + 1)) )
      {
        CGuidStr::CGuidStr(&v51, &GUID_d8f2f5e6_6102_4863_9f26_389a4676efde);
        ComTraceMessageT<void *>(
          "onecore\\com\\combase\\common\\internal\\carefulqi.cpp",
          "CarefullyQueryNewInterfaceContext::QueryInterface",
          26,
          WARNING,
          L"Found a buggy object when querying for %ws",
          v32);
      }
      v33 = 1;
    }
    v34 = v41._pData;
    if ( v41._pData )
    {
      v41._pData = 0;
      (*((void (__fastcall **)(tagSOleTlsData *))v34->pvThreadBase + 2))(v34);
    }
    if ( v33 != 1 )
    {
      v35 = pStm->QueryInterface(pStm, &GUID_d8f2f5e6_6102_4863_9f26_389a4676efde, (void **)&spMarshalingStream);
      if ( !v35 )
      {
        if ( !spMarshalingStream.ptr_ )
        {
          if ( Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
            || gfEnableTracing && IsWppLevelEnabled((TraceLevel)(Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 + 1)) )
          {
            CGuidStr::CGuidStr(&v51, &GUID_d8f2f5e6_6102_4863_9f26_389a4676efde);
            ComTraceMessageT<void *>(
              "onecore\\com\\combase\\common\\internal\\carefulqi.cpp",
              "CarefullyQueryNewInterfaceContext::QueryInterface",
              50,
              WARNING,
              L"Found a buggy object when querying for %ws, QI returns S_OK but *ppv is nullptr",
              v36);
          }
          goto LABEL_108;
        }
LABEL_106:
        ulReturnObjectContainerAttribute = 0;
        if ( spMarshalingStream.ptr_->GetMarshalingContextAttribute(
               spMarshalingStream.ptr_,
               CO_MARSHALING_CONTEXT_ATTRIBUTE_RESERVED_6,
               &ulReturnObjectContainerAttribute) >= 0 )
        {
          v37 = ulReturnObjectContainerAttribute;
          (*(void (__fastcall **)(unsigned __int64, const IID *const, LPUNKNOWN))(*(_QWORD *)ulReturnObjectContainerAttribute
                                                                                + 24LL))(
            ulReturnObjectContainerAttribute,
            riid,
            pUnk);
          (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v37 + 16LL))(v37);
        }
        goto LABEL_108;
      }
      if ( v35 >= 0 )
        goto LABEL_106;
    }
LABEL_108:
    v38 = pUnk->__vftable;
    pNoMarshal = 0;
    if ( v38->QueryInterface(pUnk, &GUID_ecc8691b_c1db_4dc0_855e_65f6c551af49, (void **)&pNoMarshal) < 0 )
    {
      pICM = 0;
      CurrentContext = GetCurrentContext();
      CurrentContext->GetContextMarshaler(CurrentContext, &pICM);
      CDestObjectWrapper::CDestObjectWrapper(&DOW, dwDestContext, v48);
      if ( pICM )
      {
        inited = pICM->MarshalInterface(pICM, pStm, riid, pUnk, dwDestContext, &DOW, mshlflags);
        pICM->Release(pICM);
      }
      else
      {
        inited = CDestObjectWrapper::MarshalInterface(
                   (CDestObjectWrapper *)&DOW.IContextMarshaler,
                   pStm,
                   riid,
                   pUnk,
                   dwDestContext,
                   &DOW,
                   mshlflags);
      }
      CoVrfAggressiveDllUnloadInSTA();
      CDestObjectWrapper::~CDestObjectWrapper(&DOW);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&spMarshalingStream);
    }
    else
    {
      pNoMarshal->Release(pNoMarshal);
      if ( gfEnableTracing && IsWppLevelEnabled(INFO) )
        ComTraceMessageT<>(
          "onecore\\com\\combase\\dcomrem\\coapi.cxx",
          "CoMarshalInterface",
          1143,
          v39,
          L"CoMarshalInterface: QI for INoMarshal succeeded.");
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<IMetaDataImport2> *)&spMarshalingStream);
      inited = -2147467231;
    }
    goto LABEL_117;
  }
  v19 = 1086;
LABEL_119:
  wil::details::in1diag3::Return_Hr(retaddr, v19, "onecore\\com\\combase\\dcomrem\\marshal.hxx", -2147024809);
  if ( exitProcessDiagnosticsContext.m_isInExitProcess
    && ExitProcessDiagnostics::ApiContext::s_current == &exitProcessDiagnosticsContext )
  {
    ExitProcessDiagnostics::ApiContext::s_current = 0;
  }
  return -2147024809;
}

```

## disassembly

```asm
0x18006ef60  push    rbp
0x18006ef62  push    rbx
0x18006ef63  push    rsi
0x18006ef64  push    rdi
0x18006ef65  push    r12
0x18006ef67  push    r13
0x18006ef69  push    r14
0x18006ef6b  push    r15
0x18006ef6d  lea     rbp, [rsp-258h]
0x18006ef75  sub     rsp, 358h
0x18006ef7c  mov     rax, cs:__security_cookie
0x18006ef83  xor     rax, rsp
0x18006ef86  mov     [rbp+290h+var_50], rax
0x18006ef8d  mov     rax, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18006ef94  xor     edi, edi
0x18006ef96  mov     r12, [rbp+290h+pvDestContext]
0x18006ef9d  mov     r14d, dwDestCtx
0x18006efa0  mov     [rbp+290h+var_2F0], r12
0x18006efa4  mov     rsi, pUnk
0x18006efa7  mov     r13, riid
0x18006efaa  mov     r15, pStm
0x18006efad  test    rax, rax
0x18006efb0  jz      loc_18006F07D
0x18006efb6  cmp     [rax+16h], dil
0x18006efba  jz      short loc_18006F017
0x18006efbc  call    cs:__imp_RtlDllShutdownInProgress
0x18006efc2  test    al, al
0x18006efc4  jz      short loc_18006F010
0x18006efc6  lea     riid, Message; "COM API or Proxy called during ExitProc"...
0x18006efcd  mov     ecx, 1000042Fh; Code
0x18006efd2  mov     rax, cs:?gMockApplicationVerifierStop@@3P6AX_KPEAD01010101@ZEA; void (*gMockApplicationVerifierStop)(unsigned __int64,char *,unsigned __int64,char *,unsigned __int64,char *,unsigned __int64,char *,unsigned __int64,char *)
0x18006efd9  lea     rbx, Description4
0x18006efe0  mov     [rsp+390h+Description4], rbx; Description4
0x18006efe5  xor     r8d, r8d; Value1
0x18006efe8  mov     [rsp+390h+Value4], rdi; Value4
0x18006efed  mov     r9, rbx; Description1
0x18006eff0  mov     [rsp+390h+Description3], rbx; Description3
0x18006eff5  mov     [rsp+390h+Value3], rdi; Value3
0x18006effa  mov     [rsp+390h+Description2], rbx; Description2
0x18006efff  mov     [rsp+390h+Value2], rdi; Value2
0x18006f004  test    rax, rax
0x18006f007  jz      short loc_18006F049
0x18006f009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f00e  jmp     short loc_18006F04F
0x18006f010  mov     rax, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18006f017  test    rax, rax
0x18006f01a  jz      short loc_18006F07D
0x18006f01c  cmp     [rax+1], dil
0x18006f020  jz      short loc_18006F07D
0x18006f022  test    rax, rax
0x18006f025  jz      short loc_18006F02D
0x18006f027  mov     rax, [rax+28h]
0x18006f02b  jmp     short loc_18006F030
0x18006f02d  mov     rax, rdi
0x18006f030  xor     ecx, ecx
0x18006f032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f037  test    eax, eax
0x18006f039  jz      short loc_18006F07D
0x18006f03b  lea     riid, aComApiOrProxyC_0; "COM API or Proxy called from DllMain"
0x18006f042  mov     ecx, 10000401h
0x18006f047  jmp     short loc_18006EFD2
0x18006f049  call    cs:__imp_RtlApplicationVerifierStop
0x18006f04f  mov     pStm, [rbp+298h]; callerReturnAddress
0x18006f056  lea     rax, formatString; "Preemptive failure return from dangerou"...
0x18006f05d  mov     dwDestCtx, 46Bh; err
0x18006f063  mov     [rsp+390h+Value2], rax; formatString
0x18006f068  lea     pUnk, aOnecoreComComb_67; "onecore\\com\\combase\\dcomrem\\coapi.c"...
0x18006f06f  lea     edx, [r9-2Ah]; lineNumber
0x18006f073  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18006f078  jmp     loc_18006F89A
0x18006f07d  mov     rax, gs:30h
0x18006f086  lea     rbx, Description4
0x18006f08d  mov     rax, [rax+1758h]
0x18006f094  mov     [rsp+390h+var_330._pData], rax
0x18006f099  test    rax, rax
0x18006f09c  jnz     short loc_18006F0B5
0x18006f09e  lea     pStm, [rsp+390h+var_330]; this
0x18006f0a3  call    ?TLSAllocData@COleTls@@QEAAJXZ; COleTls::TLSAllocData(void)
0x18006f0a8  test    eax, eax
0x18006f0aa  js      loc_18006F133
0x18006f0b0  mov     rax, [rsp+390h+var_330._pData]
0x18006f0b5  mov     pStm, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18006f0bc  test    pStm, pStm
0x18006f0bf  jz      short loc_18006F133
0x18006f0c1  cmp     [pStm+12h], dil
0x18006f0c5  jz      short loc_18006F133
0x18006f0c7  test    rax, rax
0x18006f0ca  jz      short loc_18006F133
0x18006f0cc  cmp     [rax+1C0h], edi
0x18006f0d2  jbe     short loc_18006F133
0x18006f0d4  mov     rax, cs:?gMockApplicationVerifierStop@@3P6AX_KPEAD01010101@ZEA; void (*gMockApplicationVerifierStop)(unsigned __int64,char *,unsigned __int64,char *,unsigned __int64,char *,unsigned __int64,char *,unsigned __int64,char *)
0x18006f0db  lea     pStm, Description2; "Details on why this is unrecommended"
0x18006f0e2  mov     [rsp+390h+Description4], rbx; Description4
0x18006f0e7  lea     r9, Description1; "API or entry point"
0x18006f0ee  mov     [rsp+390h+Value4], rdi; Value4
0x18006f0f3  lea     pUnk, Value1; "CoMarshalInterface"
0x18006f0fa  mov     [rsp+390h+Description3], rbx; Description3
0x18006f0ff  lea     riid, aUsingThisComAp; "Using this COM API or entry point from "...
0x18006f106  mov     [rsp+390h+Value3], rdi; Value3
0x18006f10b  mov     [rsp+390h+Description2], pStm; Description2
0x18006f110  lea     pStm, aUsageFromApcCa; "Usage from APC can cause sporadic failu"...
0x18006f117  mov     [rsp+390h+Value2], pStm; Value2
0x18006f11c  mov     ecx, 10000411h; Code
0x18006f121  test    rax, rax
0x18006f124  jz      short loc_18006F12D
0x18006f126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f12b  jmp     short loc_18006F133
0x18006f12d  call    cs:__imp_RtlApplicationVerifierStop
0x18006f133  mov     rdi, [rbp+298h]
0x18006f13a  lea     pStm, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ExitProcessDiagnostics@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ExitProcessDiagnostics@@@details@3@XZ@4V453@A; __annotation("WILSTG:|9211919|Feature_ExitProcessDiagnostics|EnabledByDefault")
0x18006f141  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ExitProcessDiagnostics@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExitProcessDiagnostics>::__private_IsEnabled(void)
0x18006f146  test    al, al
0x18006f148  jz      short loc_18006F158
0x18006f14a  call    cs:__imp_RtlDllShutdownInProgress
0x18006f150  test    al, al
0x18006f152  jz      short loc_18006F158
0x18006f154  mov     al, 1
0x18006f156  jmp     short loc_18006F15A
0x18006f158  xor     al, al
0x18006f15a  mov     [rbp+290h+exitProcessDiagnosticsContext.m_isInExitProcess], al
0x18006f15d  mov     [rbp+290h+exitProcessDiagnosticsContext.m_category], 4
0x18006f161  mov     [rbp+290h+exitProcessDiagnosticsContext.m_callerAddress], rdi
0x18006f165  test    al, al
0x18006f167  jz      loc_18006F1F9
0x18006f16d  mov     rax, cs:?s_current@ApiContext@ExitProcessDiagnostics@@0PEAV12@EA; ExitProcessDiagnostics::ApiContext * ExitProcessDiagnostics::ApiContext::s_current
0x18006f174  test    rax, rax
0x18006f177  jnz     short loc_18006F184
0x18006f179  lea     rax, [rbp+290h+exitProcessDiagnosticsContext]
0x18006f17d  mov     cs:?s_current@ApiContext@ExitProcessDiagnostics@@0PEAV12@EA, rax; ExitProcessDiagnostics::ApiContext * ExitProcessDiagnostics::ApiContext::s_current
0x18006f184  lea     pStm, [rbp+290h+exitProcessDiagnosticsContext]
0x18006f188  cmp     rax, pStm
0x18006f18b  jnz     short loc_18006F1F9
0x18006f18d  mov     eax, cs:?s_countOfDangerousUsageReported@ApiContext@ExitProcessDiagnostics@@0IA; uint ExitProcessDiagnostics::ApiContext::s_countOfDangerousUsageReported
0x18006f193  mov     edx, eax
0x18006f195  inc     eax
0x18006f197  mov     cs:?s_countOfDangerousUsageReported@ApiContext@ExitProcessDiagnostics@@0IA, eax; uint ExitProcessDiagnostics::ApiContext::s_countOfDangerousUsageReported
0x18006f19d  cmp     edx, 64h ; 'd'
0x18006f1a0  jnb     short loc_18006F1F9
0x18006f1a2  xor     eax, eax
0x18006f1a4  xorps   xmm0, xmm0
0x18006f1a7  mov     [rsp+390h+var_330._pData], rax
0x18006f1ac  mov     [rsp+390h+offset], eax
0x18006f1b0  movups  xmmword ptr [rbp+290h+modulePdbSignature.Data1], xmm0
0x18006f1b4  test    rdi, rdi
0x18006f1b7  jz      short loc_18006F1D4
0x18006f1b9  lea     r9, [rsp+390h+offset]; offset
0x18006f1be  mov     pStm, rdi; address
0x18006f1c1  lea     pUnk, [rbp+290h+modulePdbSignature]; modulePdbSignature
0x18006f1c5  lea     riid, [rsp+390h+var_330]; moduleFileName
0x18006f1ca  call    ?TryGetModuleTracingInfoFromAddress@@YA_NPEBXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAU_GUID@@AEAI@Z; TryGetModuleTracingInfoFromAddress(void const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,_GUID &,uint &)
0x18006f1cf  mov     rax, [rsp+390h+var_330._pData]
0x18006f1d4  mov     r9, r13; <args_3>
0x18006f1d7  mov     [rsp+390h+ulReturnObjectContainerAttribute], rax
0x18006f1dc  lea     pUnk, [rsp+390h+offset]; <args_2>
0x18006f1e1  lea     riid, [rbp+290h+modulePdbSignature]; <args_1>
0x18006f1e5  lea     pStm, [rsp+390h+ulReturnObjectContainerAttribute]; <args_0>
0x18006f1ea  call    ??$MarshalInExitProcess@PEBGAEBU_GUID@@IAEBU1@@ComTrace@@SAX$$QEAPEBGAEBU_GUID@@$$QEAI1@Z; ComTrace::MarshalInExitProcess<ushort const *,_GUID const &,uint,_GUID const &>(ushort const * &&,_GUID const &,uint &&,_GUID const &)
0x18006f1ef  lea     pStm, [rsp+390h+var_330]; this
0x18006f1f4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006f1f9  test    r15, r15
0x18006f1fc  jz      loc_18006F859
0x18006f202  test    rsi, rsi
0x18006f205  jz      loc_18006F859
0x18006f20b  cmp     r14d, 5
0x18006f20f  jbe     short loc_18006F21B
0x18006f211  mov     edx, 42Bh
0x18006f216  jmp     loc_18006F85E
0x18006f21b  test    r12, r12
0x18006f21e  jz      short loc_18006F236
0x18006f220  cmp     r14d, 5
0x18006f224  jz      short loc_18006F236
0x18006f226  cmp     r14d, 2
0x18006f22a  jz      short loc_18006F236
0x18006f22c  mov     edx, 42Ch
0x18006f231  jmp     loc_18006F85E
0x18006f236  mov     r12d, [rbp+290h+mshlflags]
0x18006f23d  test    r12d, 7FF8FFC0h
0x18006f244  jz      short loc_18006F250
0x18006f246  mov     edx, 42Dh
0x18006f24b  jmp     loc_18006F85E
0x18006f250  mov     rax, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18006f257  mov     [rsp+390h+var_330._pData], 0
0x18006f260  test    rax, rax
0x18006f263  jz      loc_18006F3B0
0x18006f269  cmp     byte ptr [rax+13h], 0
0x18006f26d  jz      loc_18006F3B0
0x18006f273  lea     eax, [r14-3]
0x18006f277  cmp     eax, 1
0x18006f27a  jbe     loc_18006F3B0
0x18006f280  mov     rax, [rsi]
0x18006f283  lea     pUnk, [rsp+390h+var_330]
0x18006f288  lea     riid, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18006f28f  mov     pStm, rsi
0x18006f292  mov     rax, [rax]
0x18006f295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f29a  test    eax, eax
0x18006f29c  js      short loc_18006F2E2
0x18006f29e  mov     pStm, [rsp+390h+var_330._pData]
0x18006f2a3  lea     riid, [rsp+390h+offset]
0x18006f2a8  mov     [rsp+390h+offset], 2
0x18006f2b0  mov     edi, 1
0x18006f2b5  mov     rax, [pStm]
0x18006f2b8  mov     rax, [rax+28h]
0x18006f2bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f2c1  test    eax, eax
0x18006f2c3  js      short loc_18006F2CF
0x18006f2c5  xor     eax, eax
0x18006f2c7  cmp     [rsp+390h+offset], 2
0x18006f2cc  cmovnz  edi, eax
0x18006f2cf  mov     pStm, [rsp+390h+var_330._pData]
0x18006f2d4  mov     rax, [pStm]
0x18006f2d7  mov     rax, [rax+10h]
0x18006f2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f2e0  jmp     short loc_18006F2F8
0x18006f2e2  mov     rax, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18006f2e9  test    rax, rax
0x18006f2ec  jz      short loc_18006F2F3
0x18006f2ee  mov     cl, [rax+14h]
0x18006f2f1  jmp     short loc_18006F2F5
0x18006f2f3  xor     cl, cl
0x18006f2f5  movzx   edi, cl
0x18006f2f8  test    edi, edi
0x18006f2fa  jz      loc_18006F3B0
0x18006f300  xor     edi, edi
0x18006f302  lea     pStm, [rsp+390h+offset]; pp
0x18006f307  mov     qword ptr [rsp+390h+offset], rdi
0x18006f30c  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIMarshalingStream@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIMarshalingStream@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IMarshalingStream>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IMarshalingStream>>)
0x18006f311  mov     pUnk, rax; ppv
0x18006f314  lea     riid, _GUID_d8f2f5e6_6102_4863_9f26_389a4676efde; iid
0x18006f31b  mov     pStm, r15; punk
0x18006f31e  call    ?CarefullyQueryNewInterface@@YAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CarefullyQueryNewInterface(IUnknown *,_GUID const &,void * *)
0x18006f323  test    eax, eax
0x18006f325  js      short loc_18006F3A6
0x18006f327  mov     pStm, qword ptr [rsp+390h+offset]
0x18006f32c  lea     pUnk, [rsp+390h+ulReturnObjectContainerAttribute]
0x18006f331  mov     [rsp+390h+ulReturnObjectContainerAttribute], rdi
0x18006f336  mov     edx, 80000007h
0x18006f33b  mov     rax, [pStm]
0x18006f33e  mov     rax, [rax+70h]
0x18006f342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f347  test    eax, eax
0x18006f349  js      short loc_18006F3A6
0x18006f34b  cmp     [rsp+390h+ulReturnObjectContainerAttribute], rdi
0x18006f350  jz      short loc_18006F3A6
0x18006f352  mov     rax, cs:?gMockApplicationVerifierStop@@3P6AX_KPEAD01010101@ZEA; void (*gMockApplicationVerifierStop)(unsigned __int64,char *,unsigned __int64,char *,unsigned __int64,char *,unsigned __int64,char *,unsigned __int64,char *)
0x18006f359  lea     pStm, aPointerToTheCo; "Pointer to the COM object being marshal"...
0x18006f360  mov     [rsp+390h+Description4], rdi; Description4
0x18006f365  lea     r9, aPointerToIidOf; "Pointer to IID of interface being marsh"...
0x18006f36c  mov     [rsp+390h+Value4], rdi; Value4
0x18006f371  mov     pUnk, r13; Value1
0x18006f374  mov     [rsp+390h+Description3], rdi; Description3
0x18006f379  lea     riid, aAnObjectMarked; "An object marked as requiring full trus"...
0x18006f380  mov     [rsp+390h+Value3], rdi; Value3
0x18006f385  mov     [rsp+390h+Description2], pStm; Description2
0x18006f38a  mov     ecx, 421h; Code
0x18006f38f  mov     [rsp+390h+Value2], rsi; Value2
0x18006f394  test    rax, rax
0x18006f397  jz      short loc_18006F3A0
0x18006f399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f39e  jmp     short loc_18006F3A6
0x18006f3a0  call    cs:__imp_RtlApplicationVerifierStop
0x18006f3a6  lea     pStm, [rsp+390h+offset]; this
0x18006f3ab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006f3b0  call    ?InitChannelIfNecessary@@YAJXZ; InitChannelIfNecessary(void)
0x18006f3b5  mov     edi, eax
0x18006f3b7  test    eax, eax
0x18006f3b9  js      loc_18006F84C
0x18006f3bf  mov     rax, gs:30h
0x18006f3c8  xor     edi, edi
0x18006f3ca  mov     pStm, [rax+1758h]
0x18006f3d1  test    pStm, pStm
0x18006f3d4  jnz     short loc_18006F3DF
0x18006f3d6  mov     rax, cs:?g_pMTAEmptyCtx@@3PEAVCObjectContext@@EA; CObjectContext * g_pMTAEmptyCtx
0x18006f3dd  jmp     short loc_18006F3F2
0x18006f3df  mov     rax, [pStm+68h]
0x18006f3e3  test    rax, rax
0x18006f3e6  cmovz   rax, cs:?g_pMTAEmptyCtx@@3PEAVCObjectContext@@EA; CObjectContext * g_pMTAEmptyCtx
0x18006f3ee  mov     [pStm+60h], rax
0x18006f3f2  test    rax, rax
0x18006f3f5  jz      loc_18006F593
0x18006f3fb  mov     rax, gs:30h
0x18006f404  mov     riid, [rax+1758h]
0x18006f40b  test    riid, riid
0x18006f40e  jnz     short loc_18006F419
0x18006f410  mov     pStm, cs:?g_pMTAEmptyCtx@@3PEAVCObjectContext@@EA; CObjectContext * g_pMTAEmptyCtx
0x18006f417  jmp     short loc_18006F42C
0x18006f419  mov     pStm, [riid+68h]
0x18006f41d  test    pStm, pStm
0x18006f420  cmovz   pStm, cs:?g_pMTAEmptyCtx@@3PEAVCObjectContext@@EA; this
0x18006f428  mov     [riid+60h], pStm
0x18006f42c  call    ?GetFlags@CObjectContext@@QEBAKXZ; CObjectContext::GetFlags(void)
0x18006f431  bt      eax, 8
0x18006f435  jnb     loc_18006F593
0x18006f43b  mov     rax, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18006f442  test    rax, rax
0x18006f445  jz      loc_18006F593
0x18006f44b  cmp     [rax+5], dil
0x18006f44f  jz      loc_18006F593
0x18006f455  lea     pUnk, [rsp+390h+var_330]; ppv
0x18006f45a  mov     [rsp+390h+var_330._pData], rdi
  ... truncated ...
```
