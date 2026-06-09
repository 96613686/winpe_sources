# ICETransportContext_CreateInstance

- ea: `0x18011e610`
- end: `0x18011f4b2`
- name: `ICETransportContext_CreateInstance`
- size: `3746`
- prototype: `__int64 __fastcall(struct ICETransportContextCreationParams *)`
- caller_count: `0`
- callee_count: `33`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001508`
- `0x180001aa0`
- `0x180002550`
- `0x1800025dc`
- `0x180004564`
- `0x180018930`
- `0x180018974`
- `0x18001cc3c`
- `0x18001e99c`
- `0x180038984`
- `0x180051620`
- `0x18006ce24`
- `0x18007813c`
- `0x1800787d4`
- `0x180078820`
- `0x180078c20`
- `0x18007969c`
- `0x1800dd6a0`
- `0x1801088a0`
- `0x180108e04`
- `0x180116a64`
- `0x180116ab0`
- `0x180117190`
- `0x180117450`
- `0x180117ac0`
- `0x18011a2f0`
- `0x18011ca28`
- `0x18011caa0`
- `0x18011cc20`
- `0x18011cea0`
- `0x18011e610`
- `0x1801367d0`
- `0x180162010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18011e9fc`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18011e9fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18011e9dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18011e9dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18011e928`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18011e928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011e936`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011f386`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011e936`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011f386`

## string_xrefs

- `0x18011ea3c`: `StringCchCat of file path failed`
- `0x18011e770`: `rdpnanoTransport.dll`
- `0x18011ead9`: `StringCchCopy of file path failed`
- `0x18011e6ea`: `ICETransportContext_CreateInstance`
- `0x18011e974`: `ICETransportContext_CreateInstance`
- `0x18011ea57`: `ICETransportContext_CreateInstance`
- `0x18011eaf4`: `ICETransportContext_CreateInstance`
- `0x18011ebfe`: `ICETransportContext_CreateInstance`
- `0x18011ecb5`: `ICETransportContext_CreateInstance`
- `0x18011ed64`: `ICETransportContext_CreateInstance`
- `0x18011ef62`: `ICETransportContext_CreateInstance`
- `0x18011f018`: `ICETransportContext_CreateInstance`
- `0x18011f0c3`: `ICETransportContext_CreateInstance`
- `0x18011f16f`: `ICETransportContext_CreateInstance`
- `0x18011f1f2`: `ICETransportContext_CreateInstance`
- `0x18011f28e`: `ICETransportContext_CreateInstance`
- `0x18011f327`: `ICETransportContext_CreateInstance`
- `0x18011f3c0`: `ICETransportContext_CreateInstance`
- `0x18011e7a4`: `ICE:ReadRegistryValue read failed at HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Terminal Server Client\EnablePrivateRdpNanoDll`
- `0x18011e766`: `EnablePrivateRdpNanoDll`
- `0x18011e7f0`: `ICE:ReadRegistryValueWSZ read failed at HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Terminal Server Client\PrivateRdpNanoDllName`
- `0x18011e87a`: `CRDPIce::CreateInstance:  wRDPNANOAltFileName allocation`
- `0x18011ebe3`: `Failed to create RdpNanoTransport loader object`
- `0x18011eb6f`: `ICE: Loading dll`
- `0x18011ed4a`: `Failed to create ice wrapper`
- `0x18011eca6`: `Failed to load RdpNanoTransport dll`
- `0x18011eee8`: `ICE: create CRDPIce instance successfully`
- `0x18011effe`: `ICE: spRdpIce->SetSmilesConfig failed`

## pseudocode

```c
__int64 __fastcall ICETransportContext_CreateInstance(
        struct ICETransportContextCreationParams *a1,
        const char *a2,
        struct ITSCoreApi *a3)
{
  int v5; // ecx
  int v6; // r8d
  unsigned __int16 *v7; // r9
  signed int started; // ebx
  char *v10; // rax
  int *v11; // rdx
  const unsigned __int16 *v12; // rbx
  unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // r9
  int v15; // eax
  unsigned int v16; // eax
  void *v17; // rax
  unsigned __int16 *v18; // rcx
  const unsigned __int16 *v19; // r13
  _QWORD *v20; // rdi
  RdpNanoIceWrapperStateCallback *v21; // rsi
  _QWORD *v22; // r15
  signed int LastError; // eax
  unsigned int v24; // edx
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  DWORD ModuleFileNameW; // eax
  wchar_t *v29; // rax
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  __int64 v33; // rax
  unsigned int v34; // r8d
  int v35; // r9d
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  int v39; // ecx
  int v40; // r8d
  int v41; // r9d
  int v42; // r8d
  int v43; // r9d
  RdpNanoIceWrapperStateCallback *v44; // rax
  int v45; // r8d
  int v46; // r9d
  int v47; // r8d
  int v48; // r9d
  void *v49; // rax
  __int64 v50; // r13
  __int64 v51; // rcx
  int v52; // ecx
  int v53; // r8d
  int v54; // r9d
  int v55; // ecx
  int v56; // r8d
  int v57; // r9d
  int v58; // ecx
  int v59; // r8d
  int v60; // r9d
  int v61; // ecx
  int v62; // r8d
  int v63; // r9d
  int v64; // ecx
  char *v65; // rdx
  const char *v66; // rax
  const char *v67; // rax
  signed int v68; // eax
  int v69; // ecx
  int v70; // r8d
  int v71; // r9d
  HKEY v72; // [rsp+20h] [rbp-E0h]
  const char *v73; // [rsp+60h] [rbp-A0h] BYREF
  int v74; // [rsp+68h] [rbp-98h] BYREF
  const char *v75; // [rsp+70h] [rbp-90h] BYREF
  const char *v76; // [rsp+78h] [rbp-88h] BYREF
  struct SMILES_CONFIG *v77; // [rsp+80h] [rbp-80h] BYREF
  struct ITSCoreApi *v78; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v79[2]; // [rsp+90h] [rbp-70h] BYREF
  const char *v80; // [rsp+98h] [rbp-68h] BYREF
  const char *v81; // [rsp+A0h] [rbp-60h] BYREF
  utl::_RefCountBase *v82; // [rsp+A8h] [rbp-58h]
  unsigned int v83; // [rsp+B0h] [rbp-50h] BYREF
  BYTE Data[4]; // [rsp+B4h] [rbp-4Ch] BYREF
  void *Block; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v86; // [rsp+C0h] [rbp-40h] BYREF
  DWORD cbData; // [rsp+C8h] [rbp-38h] BYREF
  Microsoft::RdpNano::Dll *v88[2]; // [rsp+D0h] [rbp-30h] BYREF
  HMODULE phModule; // [rsp+E0h] [rbp-20h] BYREF
  utl::_RefCountBase *v90[2]; // [rsp+E8h] [rbp-18h] BYREF
  WCHAR Filename[264]; // [rsp+100h] [rbp+0h] BYREF

  v78 = a3;
  v80 = a2;
  phModule = 0;
  memset_0(Filename, 0, 0x20Au);
  *(_DWORD *)Data = 0;
  cbData = 4;
  v86 = 0;
  *(_OWORD *)v88 = 0;
  *(_OWORD *)v90 = 0;
  if ( !a1 )
  {
    TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v86);
    return 2147942487LL;
  }
  LODWORD(v75) = *((_DWORD *)a1 + 6);
  if ( a2 )
  {
    v77 = (struct SMILES_CONFIG *)*((_QWORD *)a1 + 2);
    v79[0] = *((_DWORD *)a1 + 3);
    v12 = L"rdpnanoTransport.dll";
    v74 = *((_DWORD *)a1 + 7);
    Block = 0;
    if ( (unsigned int)ReadRegistryValue(L"EnablePrivateRdpNanoDll", Data, &cbData, v7, v72) == 1 )
    {
      v15 = *(_DWORD *)Data;
    }
    else
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        v73 = "ICE:ReadRegistryValue read failed at HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Terminal Server Client\\Enab"
              "lePrivateRdpNanoDll";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)byte_1801CCC83,
          0,
          (_DWORD)v14,
          (__int64)&v73);
      }
      v15 = 0;
      *(_DWORD *)Data = 0;
    }
    if ( v15 )
    {
      v83 = 0;
      if ( ReadRegistryValueWSZ(v13, 0, &v83, v14) == 1 )
      {
        v16 = v83;
      }
      else
      {
        if ( (unsigned int)CallbackContext > 3 )
        {
          v73 = "ICE:ReadRegistryValueWSZ read failed at HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Terminal Server Client\\"
                "PrivateRdpNanoDllName";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&CallbackContext,
            (unsigned int)byte_1801CD343,
            0,
            (_DWORD)v14,
            (__int64)&v73);
        }
        v16 = 0;
        v83 = 0;
      }
      if ( v16 )
      {
        v17 = operator new(saturated_mul(v16 + 1, 2u));
        Block = v17;
        v19 = (const unsigned __int16 *)v17;
        if ( !v17 )
        {
          v5 = -2147024882;
          started = -2147024882;
          if ( (unsigned int)CallbackContext <= 2 )
            goto LABEL_102;
          v10 = "CRDPIce::CreateInstance:  wRDPNANOAltFileName allocation";
          v74 = 1987;
          v79[0] = -2147024882;
          v11 = &dword_1801CD6EC;
          goto LABEL_6;
        }
        if ( ReadRegistryValueWSZ(v18, (unsigned __int8 *)v17, &v83, v7) == 1 )
        {
          v12 = v19;
        }
        else if ( (unsigned int)CallbackContext > 3 )
        {
          v73 = "ICE:ReadRegistryValueWSZ read failed at HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Terminal Server Client\\"
                "PrivateRdpNanoDllName";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&CallbackContext,
            (unsigned int)qword_1801CC810,
            0,
            (_DWORD)v14,
            (__int64)&v73);
        }
      }
    }
    v20 = 0;
    v21 = 0;
    v22 = 0;
    if ( (unsigned int)CallbackContext > 4 )
    {
      v73 = "ICE Process called";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&CallbackContext,
        (unsigned int)byte_1801CD131,
        0,
        (_DWORD)v14,
        (__int64)&v73);
    }
    if ( !GetModuleHandleExW(6u, (LPCWSTR)PipeETWEvents::OnFeatureMap, &phModule) )
    {
      LastError = GetLastError();
      started = LastError;
      if ( LastError > 0 )
        started = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v74 = 2011;
        v77 = (struct SMILES_CONFIG *)"Failed to get module handle to itself.";
        v79[0] = started;
        v73 = "ICETransportContext_CreateInstance";
        v75 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\ice.cpp";
        v76 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v25,
          (unsigned int)byte_1801CC655,
          v26,
          v27,
          (__int64)&v76,
          (__int64)v79,
          (__int64)&v75,
          (__int64)&v74,
          (__int64)&v73,
          (__int64)&v77);
      }
      goto LABEL_93;
    }
    ModuleFileNameW = GetModuleFileNameW(phModule, Filename, 0x105u);
    if ( !ModuleFileNameW || ModuleFileNameW == 261 )
    {
      v68 = GetLastError();
      started = v68;
      if ( v68 > 0 )
        started = (unsigned __int16)v68 | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v73) = 2019;
        v80 = "Failed to get the module file name";
        LODWORD(v75) = started;
        v78 = (struct ITSCoreApi *)"ICETransportContext_CreateInstance";
        v81 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\ice.cpp";
        v76 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v69,
          (unsigned int)word_1801CD65A,
          v70,
          v71,
          (__int64)&v76,
          (__int64)&v75,
          (__int64)&v81,
          (__int64)&v73,
          (__int64)&v78,
          (__int64)&v80);
      }
LABEL_93:
      if ( !started )
      {
LABEL_100:
        if ( Block )
          operator delete(Block);
        goto LABEL_102;
      }
      if ( !v20 )
      {
LABEL_96:
        if ( v21 )
          RdpNanoIceWrapperStateCallback::`scalar deleting destructor'(v21, v24);
        if ( v22 )
          operator delete(v22);
        goto LABEL_100;
      }
LABEL_95:
      operator delete(v20);
      goto LABEL_96;
    }
    v29 = wcsrchr(Filename, 0x5Cu);
    if ( v29 )
    {
      v29[1] = 0;
      started = StringCchCatW(Filename, 0x105u, v12);
      if ( started < 0 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v74 = 2027;
          v76 = "StringCchCat of file path failed";
          v79[0] = started;
          v77 = (struct SMILES_CONFIG *)"ICETransportContext_CreateInstance";
          v73 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\ice.cpp";
          v75 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (_DWORD)CallbackContext,
            (unsigned int)byte_1801CCB89,
            v31,
            v32,
            (__int64)&v75,
            (__int64)v79,
            (__int64)&v73,
            (__int64)&v74,
            (__int64)&v77,
            (__int64)&v76);
        }
        goto LABEL_100;
      }
    }
    else
    {
      started = StringCchCopyW(Filename, 0x105u, v12);
      if ( started < 0 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          v74 = 2032;
          v76 = "StringCchCopy of file path failed";
          v79[0] = started;
          v77 = (struct SMILES_CONFIG *)"ICETransportContext_CreateInstance";
          v73 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\ice.cpp";
          v75 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v30,
            (unsigned int)word_1801CD4CA,
            v31,
            v32,
            (__int64)&v75,
            (__int64)v79,
            (__int64)&v73,
            (__int64)&v74,
            (__int64)&v77,
            (__int64)&v76);
        }
        goto LABEL_100;
      }
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      v76 = (const char *)Filename;
      v73 = "ICE: Loading dll";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v30,
        (unsigned int)qword_1801CD2D8,
        v31,
        v32,
        (__int64)&v73,
        (__int64)&v76);
    }
    v33 = utl::make_shared<Microsoft::RdpNano::Dll,int &>(&v81, &v75);
    utl::shared_ptr<Microsoft::RdpNano::Dll>::operator=(v88, v33);
    if ( v82 )
      utl::_RefCountBase::_DecStrong(v82);
    if ( !(unsigned __int8)utl::operator!=<Microsoft::RdpNano::Dll>(v88) )
    {
      started = -2147024882;
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v75) = 2043;
        v76 = "Failed to create RdpNanoTransport loader object";
        v74 = -2147024882;
        v77 = (struct SMILES_CONFIG *)"ICETransportContext_CreateInstance";
        v73 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\ice.cpp";
        *(_QWORD *)v79 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          -2147024882,
          (unsigned int)byte_1801CC363,
          v34,
          v35,
          (__int64)v79,
          (__int64)&v74,
          (__int64)&v73,
          (__int64)&v75,
          (__int64)&v77,
          (__int64)&v76);
      }
      goto LABEL_100;
    }
    started = Microsoft::RdpNano::Dll::Load(v88[0], Filename, v34);
    if ( started < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v75) = 2051;
        v76 = (const char *)Filename;
        v74 = started;
        v77 = (struct SMILES_CONFIG *)"Failed to load RdpNanoTransport dll";
        v73 = "ICETransportContext_CreateInstance";
        *(_QWORD *)v79 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\ice.cpp";
        v81 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v36,
          (unsigned int)byte_1801CD733,
          v37,
          v38,
          (__int64)&v81,
          (__int64)&v74,
          (__int64)v79,
          (__int64)&v75,
          (__int64)&v73,
          (__int64)&v77,
          (__int64)&v76);
      }
      goto LABEL_100;
    }
    started = Microsoft::RdpNano::Dll::CreateIceWrapper<utl::shared_ptr>(v88[0], v90);
    if ( started < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v75) = 2058;
        v81 = "Failed to create ice wrapper";
        v74 = started;
        v76 = "ICETransportContext_CreateInstance";
        v77 = (struct SMILES_CONFIG *)"onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\ice.cpp";
        v73 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v39,
          (unsigned int)qword_1801CCFC0,
          v40,
          v41,
          (__int64)&v73,
          (__int64)&v74,
          (__int64)&v77,
          (__int64)&v75,
          (__int64)&v76,
          (__int64)&v81);
      }
      goto LABEL_100;
    }
    v20 = operator new(0x28u);
    if ( !v20 )
    {
      started = -2147024882;
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v73) = 2066;
        v80 = "Failed to allocate pRdpNanoIceWrapperDataCallback";
        LODWORD(v75) = -2147024882;
        v78 = (struct ITSCoreApi *)"ICETransportContext_CreateInstance";
        v81 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\ice.cpp";
        v76 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          -2147024882,
          (unsigned int)byte_1801CCE09,
          v42,
          v43,
          (__int64)&v76,
          (__int64)&v75,
          (__int64)&v81,
          (__int64)&v73,
          (__int64)&v78,
          (__int64)&v80);
      }
      goto LABEL_100;
    }
    v20[1] = 0;
    *v20 = &RdpNanoIceWrapperDataCallback::`vftable';
    v20[2] = 0;
    CTSReaderWriterLock::CTSReaderWriterLock((CTSReaderWriterLock *)(v20 + 3));
    v44 = (RdpNanoIceWrapperStateCallback *)operator new(0x28u);
    if ( v44 && (v21 = RdpNanoIceWrapperStateCallback::RdpNanoIceWrapperStateCallback(v44)) != 0 )
    {
      v22 = operator new(8u);
      if ( !v22 )
      {
        started = -2147024882;
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v73) = 2081;
          v80 = "Failed to allocate pRdpNanoIceWrapperInstrumentationCallback";
          LODWORD(v75) = -2147024882;
          v78 = (struct ITSCoreApi *)"ICETransportContext_CreateInstance";
          v81 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\ice.cpp";
          v76 = "Error condition failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            -2147024882,
            (unsigned int)byte_1801CD8BD,
            v47,
            v48,
            (__int64)&v76,
            (__int64)&v75,
            (__int64)&v81,
            (__int64)&v73,
            (__int64)&v78,
            (__int64)&v80);
        }
        v22 = 0;
        goto LABEL_95;
      }
      *v22 = &RdpNanoIceWrapperInstrumentationCallback::`vftable';
      v49 = operator new(0x1C0u);
      if ( v49 )
      {
        v50 = CRDPIce::CRDPIce((_DWORD)v49, (_DWORD)v21, (unsigned int)v90, (_DWORD)v20, (__int64)v22);
        if ( v50 )
        {
          TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v86);
          v51 = *(_QWORD *)(v50 + 32);
          v86 = v50;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 8LL))(v51);
          RdpNanoIceWrapperStateCallback::SetIRdpIceStateCallback(v21, (struct IRdpIceStateCallback *)(v50 + 56));
          CTSReaderWriterLock::WriteLock((CTSReaderWriterLock *)(v20 + 3));
          v20[2] = v50 + 64;
          CTSReaderWriterLock::WriteUnlock((CTSReaderWriterLock *)(v20 + 3));
          CRDPIce::SetNanoIceModule(v50, v88);
          if ( (unsigned int)CallbackContext > 4 )
          {
            LODWORD(v75) = v74;
            v81 = (const char *)v77;
            LODWORD(v73) = v79[0];
            v76 = "ICE: create CRDPIce instance successfully";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
              v52,
              (unsigned int)&dword_1801CC69C,
              v53,
              v54,
              (__int64)&v76,
              (__int64)&v73,
              (__int64)&v81,
              (__int64)&v75);
          }
          started = CRDPIce::InitializeInstance((CRDPIce *)v50, a1, v78);
          if ( started < 0 )
          {
            if ( (unsigned int)CallbackContext > 2 )
            {
              LODWORD(v73) = 2106;
              v78 = (struct ITSCoreApi *)"ICE: spRdpIce->InitializeInstance failed";
              LODWORD(v75) = started;
              v81 = "ICETransportContext_CreateInstance";
              v76 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\ice.cpp";
              v77 = (struct SMILES_CONFIG *)"Error HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v55,
                (unsigned int)&byte_1801CC287,
                v56,
                v57,
                (__int64)&v77,
                (__int64)&v75,
                (__int64)&v76,
                (__int64)&v73,
                (__int64)&v81,
                (__int64)&v78);
            }
            goto LABEL_95;
          }
          if ( started == 1 )
            goto LABEL_93;
          if ( v77 )
          {
            started = CRDPIce::SetSmilesConfig((CRDPIce *)v50, v79[0], v77);
            if ( started < 0 )
            {
              if ( (unsigned int)CallbackContext > 2 )
              {
                LODWORD(v73) = 2116;
                v78 = (struct ITSCoreApi *)"ICE: spRdpIce->SetSmilesConfig failed";
                LODWORD(v75) = started;
                v81 = "ICETransportContext_CreateInstance";
                v76 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\ice.cpp";
                v77 = (struct SMILES_CONFIG *)"Error HResult failed";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                  v58,
                  (unsigned int)byte_1801CC1F9,
                  v59,
                  v60,
                  (__int64)&v77,
                  (__int64)&v75,
                  (__int64)&v76,
                  (__int64)&v73,
                  (__int64)&v81,
                  (__int64)&v78);
              }
              goto LABEL_95;
            }
          }
          if ( v74 == 1 )
          {
            started = CRDPIce::StartNanoIceInitialization((CRDPIce *)(v50 + 72), 0, 0);
            if ( started < 0 )
            {
              if ( (unsigned int)CallbackContext > 2 )
              {
                LODWORD(v73) = 2122;
                v78 = (struct ITSCoreApi *)"ICE: spRdpIce->StartNanoIceInitialization failed";
                LODWORD(v75) = started;
                v81 = "ICETransportContext_CreateInstance";
                v76 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\ice.cpp";
                v77 = (struct SMILES_CONFIG *)"Error HResult failed";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                  v61,
                  (unsigned int)qword_1801CC240,
                  v62,
                  v63,
                  (__int64)&v77,
                  (__int64)&v75,
                  (__int64)&v76,
                  (__int64)&v73,
                  (__int64)&v81,
                  (__int64)&v78);
              }
              goto LABEL_95;
            }
          }
          started = (***(__int64 (__fastcall ****)(_QWORD, GUID *, const char *))(v50 + 32))(
                      *(_QWORD *)(v50 + 32),
                      &IID_IUnknown,
                      v80);
          if ( started >= 0 )
            goto LABEL_93;
          if ( (unsigned int)CallbackContext <= 2 )
            goto LABEL_95;
          LODWORD(v73) = 2126;
          v80 = "ICE: QI IID_IUnknown failed";
          v65 = byte_1801CCD8D;
          LODWORD(v75) = started;
          v78 = (struct ITSCoreApi *)"ICETransportContext_CreateInstance";
          v81 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\ice.cpp";
          v66 = "Error HResult failed";
LABEL_86:
          v76 = v66;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v64,
            (_DWORD)v65,
            v45,
            v46,
            (__int64)&v76,
            (__int64)&v75,
            (__int64)&v81,
            (__int64)&v73,
            (__int64)&v78,
            (__int64)&v80);
          goto LABEL_95;
        }
      }
      v64 = -2147024882;
      started = -2147024882;
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_95;
      v67 = "Failed to allocate spRdpIce";
      LODWORD(v73) = 2089;
      v65 = byte_1801CC7C9;
    }
    else
    {
      v64 = -2147024882;
      started = -2147024882;
      if ( (unsigned int)CallbackContext <= 2 )
        goto LABEL_95;
      v67 = "Failed to allocate pRdpNanoIceWrapperDataCallback";
      LODWORD(v73) = 2074;
      v65 = (char *)qword_1801CCE50;
    }
    v80 = v67;
    v78 = (struct ITSCoreApi *)"ICETransportContext_CreateInstance";
    v81 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\ice.cpp";
    v66 = "Error condition failed";
    LODWORD(v75) = -2147024882;
    goto LABEL_86;
  }
  started = -2147467261;
  if ( (unsigned int)CallbackContext > 2 )
  {
    v10 = "NULL ppICETransport";
    v74 = 1961;
    v79[0] = -2147467261;
    v11 = (int *)byte_1801CD291;
LABEL_6:
    Block = v10;
    v77 = (struct SMILES_CONFIG *)"ICETransportContext_CreateInstance";
    v73 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\ice.cpp";
    v75 = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v5,
      (_DWORD)v11,
      v6,
      (_DWORD)v7,
      (__int64)&v75,
      (__int64)v79,
      (__int64)&v73,
      (__int64)&v74,
      (__int64)&v77,
      (__int64)&Block);
  }
LABEL_102:
  TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v86);
  if ( v90[1] )
    utl::_RefCountBase::_DecStrong(v90[1]);
  if ( v88[1] )
    utl::_RefCountBase::_DecStrong(v88[1]);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18011e610  mov     [rsp-8+arg_10], rbx
0x18011e615  mov     [rsp-8+arg_18], rsi
0x18011e61a  push    rbp
0x18011e61b  push    rdi
0x18011e61c  push    r12
0x18011e61e  push    r13
0x18011e620  push    r15
0x18011e622  lea     rbp, [rsp-220h]
0x18011e62a  sub     rsp, 320h
0x18011e631  mov     rax, cs:__security_cookie
0x18011e638  xor     rax, rsp
0x18011e63b  mov     [rbp+240h+var_30], rax
0x18011e642  mov     [rbp+240h+var_2B8], r8
0x18011e646  mov     rbx, rdx
0x18011e649  mov     [rbp+240h+var_2A8], rdx
0x18011e64d  mov     r12, rcx
0x18011e650  xor     edx, edx; Val
0x18011e652  mov     [rbp+240h+phModule], 0
0x18011e65a  mov     r8d, 20Ah; Size
0x18011e660  lea     rcx, [rbp+240h+Filename]; void *
0x18011e664  call    memset_0
0x18011e669  mov     dword ptr [rbp+240h+Data], 0
0x18011e670  xorps   xmm0, xmm0
0x18011e673  mov     [rbp+240h+cbData], 4
0x18011e67a  xorps   xmm1, xmm1
0x18011e67d  mov     [rbp+240h+var_280], 0
0x18011e685  movdqu  xmmword ptr [rbp+240h+var_270], xmm0
0x18011e68a  movdqu  xmmword ptr [rbp+240h+var_258], xmm1
0x18011e68f  test    r12, r12
0x18011e692  jnz     short loc_18011E6A7
0x18011e694  lea     rcx, [rbp+240h+var_280]
0x18011e698  call    ?SafeRelease@?$TCntPtr@V?$SlidingStats@N$04$00@@@@AEAAXXZ; TCntPtr<SlidingStats<double,5,1>>::SafeRelease(void)
0x18011e69d  mov     eax, 80070057h
0x18011e6a2  jmp     loc_18011F487
0x18011e6a7  mov     eax, [r12+18h]
0x18011e6ac  mov     dword ptr [rsp+340h+var_2D0], eax
0x18011e6b0  test    rbx, rbx
0x18011e6b3  jnz     loc_18011E750
0x18011e6b9  mov     eax, cs:CallbackContext
0x18011e6bf  mov     ebx, 80004003h
0x18011e6c4  cmp     eax, 2
0x18011e6c7  jbe     loc_18011F460
0x18011e6cd  lea     rax, aNullPpicetrans; "NULL ppICETransport"
0x18011e6d4  mov     [rsp+340h+var_2D8], 7A9h
0x18011e6dc  mov     [rbp+240h+var_2B0], ebx
0x18011e6df  lea     rdx, byte_1801CD291
0x18011e6e6  mov     [rbp+240h+Block], rax
0x18011e6ea  lea     rax, aIcetransportco_0; "ICETransportContext_CreateInstance"
0x18011e6f1  mov     [rbp+240h+var_2C0], rax
0x18011e6f5  lea     rax, aOnecoreTermsrv_59; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18011e6fc  mov     [rsp+340h+var_2E0], rax
0x18011e701  lea     rax, aErrorCondition; "Error condition failed"
0x18011e708  mov     [rsp+340h+var_2D0], rax
0x18011e70d  lea     rax, [rbp+240h+Block]
0x18011e711  mov     [rsp+340h+var_2F8], rax
0x18011e716  lea     rax, [rbp+240h+var_2C0]
0x18011e71a  mov     [rsp+340h+var_300], rax
0x18011e71f  lea     rax, [rsp+340h+var_2D8]
0x18011e724  mov     [rsp+340h+var_308], rax
0x18011e729  lea     rax, [rsp+340h+var_2E0]
0x18011e72e  mov     [rsp+340h+var_310], rax
0x18011e733  lea     rax, [rbp+240h+var_2B0]
0x18011e737  mov     [rsp+340h+var_318], rax
0x18011e73c  lea     rax, [rsp+340h+var_2D0]
0x18011e741  mov     [rsp+340h+var_320], rax
0x18011e746  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18011e74b  jmp     loc_18011F460
0x18011e750  mov     rax, [r12+10h]
0x18011e755  lea     r8, [rbp+240h+cbData]; lpcbData
0x18011e759  mov     [rbp+240h+var_2C0], rax
0x18011e75d  lea     rdx, [rbp+240h+Data]; lpData
0x18011e761  mov     eax, [r12+0Ch]
0x18011e766  lea     rcx, aEnableprivater; "EnablePrivateRdpNanoDll"
0x18011e76d  mov     [rbp+240h+var_2B0], eax
0x18011e770  lea     rbx, aRdpnanotranspo; "rdpnanoTransport.dll"
0x18011e777  mov     eax, [r12+1Ch]
0x18011e77c  mov     [rsp+340h+var_2D8], eax
0x18011e780  mov     [rbp+240h+Block], 0
0x18011e788  call    ?ReadRegistryValue@@YAHPEAGPEAEPEAK0PEAUHKEY__@@@Z; ReadRegistryValue(ushort *,uchar *,ulong *,ushort *,HKEY__ *)
0x18011e78d  lea     rdi, CallbackContext
0x18011e794  cmp     eax, 1
0x18011e797  jz      short loc_18011E7D3
0x18011e799  mov     eax, cs:CallbackContext
0x18011e79f  cmp     eax, 3
0x18011e7a2  jbe     short loc_18011E7CC
0x18011e7a4  lea     rax, aIceReadregistr_0; "ICE:ReadRegistryValue read failed at HK"...
0x18011e7ab  xor     r8d, r8d
0x18011e7ae  mov     [rsp+340h+var_2E0], rax
0x18011e7b3  lea     rdx, byte_1801CCC83
0x18011e7ba  lea     rax, [rsp+340h+var_2E0]
0x18011e7bf  mov     rcx, rdi
0x18011e7c2  mov     [rsp+340h+var_320], rax
0x18011e7c7  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18011e7cc  xor     eax, eax
0x18011e7ce  mov     dword ptr [rbp+240h+Data], eax
0x18011e7d1  jmp     short loc_18011E7D6
0x18011e7d3  mov     eax, dword ptr [rbp+240h+Data]
0x18011e7d6  test    eax, eax
0x18011e7d8  jz      loc_18011E8DA
0x18011e7de  lea     r8, [rbp+240h+var_290]; unsigned int *
0x18011e7e2  mov     [rbp+240h+var_290], 0
0x18011e7e9  xor     edx, edx; unsigned __int8 *
0x18011e7eb  call    ?ReadRegistryValueWSZ@@YAHPEAGPEAEPEAK0@Z; ReadRegistryValueWSZ(ushort *,uchar *,ulong *,ushort *)
0x18011e7f0  lea     rsi, aIceReadregistr_2; "ICE:ReadRegistryValueWSZ read failed at"...
0x18011e7f7  cmp     eax, 1
0x18011e7fa  jz      short loc_18011E82F
0x18011e7fc  mov     eax, cs:CallbackContext
0x18011e802  cmp     eax, 3
0x18011e805  jbe     short loc_18011E828
0x18011e807  lea     rax, [rsp+340h+var_2E0]
0x18011e80c  mov     [rsp+340h+var_2E0], rsi
0x18011e811  xor     r8d, r8d
0x18011e814  mov     [rsp+340h+var_320], rax
0x18011e819  lea     rdx, byte_1801CD343
0x18011e820  mov     rcx, rdi
0x18011e823  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18011e828  xor     eax, eax
0x18011e82a  mov     [rbp+240h+var_290], eax
0x18011e82d  jmp     short loc_18011E832
0x18011e82f  mov     eax, [rbp+240h+var_290]
0x18011e832  test    eax, eax
0x18011e834  jz      loc_18011E8DA
0x18011e83a  lea     ecx, [rax+1]
0x18011e83d  mov     eax, 2
0x18011e842  mul     rcx
0x18011e845  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18011e84c  cmovb   rax, rcx
0x18011e850  mov     rcx, rax; Size
0x18011e853  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18011e858  mov     [rbp+240h+Block], rax
0x18011e85c  mov     r13, rax
0x18011e85f  test    rax, rax
0x18011e862  jnz     short loc_18011E898
0x18011e864  mov     eax, cs:CallbackContext
0x18011e86a  mov     ecx, 8007000Eh
0x18011e86f  mov     ebx, ecx
0x18011e871  cmp     eax, 2
0x18011e874  jbe     loc_18011F460
0x18011e87a  lea     rax, aCrdpiceCreatei; "CRDPIce::CreateInstance:  wRDPNANOAltFi"...
0x18011e881  mov     [rsp+340h+var_2D8], 7C3h
0x18011e889  mov     [rbp+240h+var_2B0], ecx
0x18011e88c  lea     rdx, dword_1801CD6EC
0x18011e893  jmp     loc_18011E6E6
0x18011e898  lea     r8, [rbp+240h+var_290]; unsigned int *
0x18011e89c  mov     rdx, r13; unsigned __int8 *
0x18011e89f  call    ?ReadRegistryValueWSZ@@YAHPEAGPEAEPEAK0@Z; ReadRegistryValueWSZ(ushort *,uchar *,ulong *,ushort *)
0x18011e8a4  cmp     eax, 1
0x18011e8a7  jz      short loc_18011E8D7
0x18011e8a9  mov     eax, cs:CallbackContext
0x18011e8af  cmp     eax, 3
0x18011e8b2  jbe     short loc_18011E8DA
0x18011e8b4  lea     rax, [rsp+340h+var_2E0]
0x18011e8b9  mov     [rsp+340h+var_2E0], rsi
0x18011e8be  xor     r8d, r8d
0x18011e8c1  mov     [rsp+340h+var_320], rax
0x18011e8c6  lea     rdx, qword_1801CC810
0x18011e8cd  mov     rcx, rdi
0x18011e8d0  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18011e8d5  jmp     short loc_18011E8DA
0x18011e8d7  mov     rbx, r13
0x18011e8da  mov     eax, cs:CallbackContext
0x18011e8e0  xor     edi, edi
0x18011e8e2  xor     esi, esi
0x18011e8e4  xor     r15d, r15d
0x18011e8e7  cmp     eax, 4
0x18011e8ea  jbe     short loc_18011E918
0x18011e8ec  lea     rax, aIceProcessCall; "ICE Process called"
0x18011e8f3  xor     r8d, r8d
0x18011e8f6  mov     [rsp+340h+var_2E0], rax
0x18011e8fb  lea     rdx, byte_1801CD131
0x18011e902  lea     rax, [rsp+340h+var_2E0]
0x18011e907  lea     rcx, CallbackContext
0x18011e90e  mov     [rsp+340h+var_320], rax
0x18011e913  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18011e918  lea     r8, [rbp+240h+phModule]; phModule
0x18011e91c  mov     ecx, 6; dwFlags
0x18011e921  lea     rdx, ?OnFeatureMap@PipeETWEvents@@UEAAJIPEAVAdvanceFeatureMap@@@Z; lpModuleName
0x18011e928  call    cs:__imp_GetModuleHandleExW
0x18011e92e  test    eax, eax
0x18011e930  jnz     loc_18011E9CB
0x18011e936  call    cs:__imp_GetLastError
0x18011e93c  mov     ebx, eax
0x18011e93e  test    eax, eax
0x18011e940  jle     short loc_18011E94B
0x18011e942  movzx   ebx, ax
0x18011e945  or      ebx, 80070000h
0x18011e94b  mov     eax, cs:CallbackContext
0x18011e951  cmp     eax, 2
0x18011e954  jbe     loc_18011F424
0x18011e95a  lea     rax, aFailedToGetMod_0; "Failed to get module handle to itself."
0x18011e961  mov     [rsp+340h+var_2D8], 7DBh
0x18011e969  mov     [rbp+240h+var_2C0], rax
0x18011e96d  lea     rdx, byte_1801CC655
0x18011e974  lea     rax, aIcetransportco_0; "ICETransportContext_CreateInstance"
0x18011e97b  mov     [rbp+240h+var_2B0], ebx
0x18011e97e  mov     [rsp+340h+var_2E0], rax
0x18011e983  lea     rax, aOnecoreTermsrv_59; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18011e98a  mov     [rsp+340h+var_2D0], rax
0x18011e98f  lea     rax, aErrorCondition; "Error condition failed"
0x18011e996  mov     [rsp+340h+var_2C8], rax
0x18011e99b  lea     rax, [rbp+240h+var_2C0]
0x18011e99f  mov     [rsp+340h+var_2F8], rax
0x18011e9a4  lea     rax, [rsp+340h+var_2E0]
0x18011e9a9  mov     [rsp+340h+var_300], rax
0x18011e9ae  lea     rax, [rsp+340h+var_2D8]
0x18011e9b3  mov     [rsp+340h+var_308], rax
0x18011e9b8  lea     rax, [rsp+340h+var_2D0]
0x18011e9bd  mov     [rsp+340h+var_310], rax
0x18011e9c2  lea     rax, [rbp+240h+var_2B0]
0x18011e9c6  jmp     loc_18011F410
0x18011e9cb  mov     rcx, [rbp+240h+phModule]; hModule
0x18011e9cf  lea     rdx, [rbp+240h+Filename]; lpFilename
0x18011e9d3  mov     r13d, 105h
0x18011e9d9  mov     r8d, r13d; nSize
0x18011e9dc  call    cs:__imp_GetModuleFileNameW
0x18011e9e2  test    eax, eax
0x18011e9e4  jz      loc_18011F386
0x18011e9ea  cmp     eax, r13d
0x18011e9ed  jz      loc_18011F386
0x18011e9f3  mov     edx, 5Ch ; '\'; Ch
0x18011e9f8  lea     rcx, [rbp+240h+Filename]; Str
0x18011e9fc  call    cs:__imp_wcsrchr
0x18011ea02  mov     r8, rbx; unsigned __int16 *
0x18011ea05  mov     edx, r13d; unsigned __int64
0x18011ea08  mov     rcx, rax
0x18011ea0b  test    rax, rax
0x18011ea0e  jz      loc_18011EAB7
0x18011ea14  xor     eax, eax
0x18011ea16  mov     [rcx+2], ax
0x18011ea1a  lea     rcx, [rbp+240h+Filename]; unsigned __int16 *
0x18011ea1e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18011ea23  mov     ebx, eax
0x18011ea25  test    eax, eax
0x18011ea27  jns     loc_18011EB54
0x18011ea2d  mov     ecx, cs:CallbackContext
0x18011ea33  cmp     ecx, 2
0x18011ea36  jbe     loc_18011F44F
0x18011ea3c  lea     rax, aStringcchcatOf; "StringCchCat of file path failed"
0x18011ea43  mov     [rsp+340h+var_2D8], 7EBh
0x18011ea4b  mov     [rsp+340h+var_2C8], rax
0x18011ea50  lea     rdx, byte_1801CCB89
0x18011ea57  lea     rax, aIcetransportco_0; "ICETransportContext_CreateInstance"
0x18011ea5e  mov     [rbp+240h+var_2B0], ebx
0x18011ea61  mov     [rbp+240h+var_2C0], rax
0x18011ea65  lea     rax, aOnecoreTermsrv_59; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18011ea6c  mov     [rsp+340h+var_2E0], rax
0x18011ea71  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18011ea78  mov     [rsp+340h+var_2D0], rax
0x18011ea7d  lea     rax, [rsp+340h+var_2C8]
0x18011ea82  mov     [rsp+340h+var_2F8], rax
0x18011ea87  lea     rax, [rbp+240h+var_2C0]
0x18011ea8b  mov     [rsp+340h+var_300], rax
0x18011ea90  lea     rax, [rsp+340h+var_2D8]
0x18011ea95  mov     [rsp+340h+var_308], rax
0x18011ea9a  lea     rax, [rsp+340h+var_2E0]
0x18011ea9f  mov     [rsp+340h+var_310], rax
0x18011eaa4  lea     rax, [rbp+240h+var_2B0]
0x18011eaa8  mov     [rsp+340h+var_318], rax
0x18011eaad  lea     rax, [rsp+340h+var_2D0]
0x18011eab2  jmp     loc_18011EC59
0x18011eab7  lea     rcx, [rbp+240h+Filename]; unsigned __int16 *
0x18011eabb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18011eac0  mov     ebx, eax
0x18011eac2  test    eax, eax
0x18011eac4  jns     loc_18011EB54
0x18011eaca  mov     eax, cs:CallbackContext
0x18011ead0  cmp     eax, 2
0x18011ead3  jbe     loc_18011F44F
0x18011ead9  lea     rax, aStringcchcopyO_2; "StringCchCopy of file path failed"
0x18011eae0  mov     [rsp+340h+var_2D8], 7F0h
0x18011eae8  mov     [rsp+340h+var_2C8], rax
0x18011eaed  lea     rdx, word_1801CD4CA
0x18011eaf4  lea     rax, aIcetransportco_0; "ICETransportContext_CreateInstance"
0x18011eafb  mov     [rbp+240h+var_2B0], ebx
0x18011eafe  mov     [rbp+240h+var_2C0], rax
0x18011eb02  lea     rax, aOnecoreTermsrv_59; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18011eb09  mov     [rsp+340h+var_2E0], rax
0x18011eb0e  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18011eb15  mov     [rsp+340h+var_2D0], rax
0x18011eb1a  lea     rax, [rsp+340h+var_2C8]
0x18011eb1f  mov     [rsp+340h+var_2F8], rax
0x18011eb24  lea     rax, [rbp+240h+var_2C0]
0x18011eb28  mov     [rsp+340h+var_300], rax
0x18011eb2d  lea     rax, [rsp+340h+var_2D8]
0x18011eb32  mov     [rsp+340h+var_308], rax
0x18011eb37  lea     rax, [rsp+340h+var_2E0]
0x18011eb3c  mov     [rsp+340h+var_310], rax
0x18011eb41  lea     rax, [rbp+240h+var_2B0]
0x18011eb45  mov     [rsp+340h+var_318], rax
0x18011eb4a  lea     rax, [rsp+340h+var_2D0]
0x18011eb4f  jmp     loc_18011EC59
0x18011eb54  mov     eax, cs:CallbackContext
0x18011eb5a  cmp     eax, 4
0x18011eb5d  jbe     short loc_18011EB94
0x18011eb5f  lea     rax, [rbp+240h+Filename]
0x18011eb63  mov     [rsp+340h+var_2C8], rax
0x18011eb68  lea     rdx, qword_1801CD2D8
0x18011eb6f  lea     rax, aIceLoadingDll; "ICE: Loading dll"
0x18011eb76  mov     [rsp+340h+var_2E0], rax
0x18011eb7b  lea     rax, [rsp+340h+var_2C8]
  ... truncated ...
```
