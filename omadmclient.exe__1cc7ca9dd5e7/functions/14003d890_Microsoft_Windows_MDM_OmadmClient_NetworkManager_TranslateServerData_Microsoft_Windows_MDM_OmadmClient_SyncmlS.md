# Microsoft::Windows::MDM::OmadmClient::NetworkManager::TranslateServerData(Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState &,IStream *,ushort * *)

- ea: `0x14003d890`
- end: `0x14003e259`
- name: `?TranslateServerData@NetworkManager@OmadmClient@MDM@Windows@Microsoft@@UEAAJAEAVSyncmlSessionState@2345@PEAUIStream@@PEAPEAG@Z`
- size: `2505`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::NetworkManager *__hidden this, struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *, struct IStream *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140003450`
- `0x14000597e`
- `0x14000b0f4`
- `0x14000d71c`
- `0x14000e610`
- `0x140013404`
- `0x1400134a4`
- `0x14001391c`
- `0x140039f9c`
- `0x14003d890`
- `0x1400552f8`
- `0x140069010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x14003e082`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x14003e09f`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x14003e082`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x14003e09f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003dcb4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003dcb4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003dcfe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003dcfe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003e124`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003e205`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003e124`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003e205`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003e138`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003e219`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003e138`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14003e219`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d9e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dace`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dfa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dff6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003d9e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dace`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dce3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dfa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dff6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003d9ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003e015`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003d9ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003e015`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x14003db83`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x14003dc37`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x14003db83`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x14003dc37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003d9f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003e007`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003d9f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003e007`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14003dfdb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14003dfdb`
- `DMCmnUtils!MBToUnicode` at `0x14003e0ef`
- `DMCmnUtils!MBToUnicode` at `0x14003e0ef`
- `DMCmnUtils!InvStrCmpIW` at `0x14003dc11`
- `DMCmnUtils!InvStrCmpIW` at `0x14003dc11`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14003dc96`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x14003dc96`

## string_xrefs

- `0x14003dc03`: `application/vnd.syncml.dm+wbxml`
- `0x14003e1a6`: `XML from server =`
- `0x14003dc8f`: `dmxmlhelputils.dll`
- `0x14003dcaa`: `ConvertWBXmlToTextXmlEx`
- `0x14003e095`: `<?xml version='1.0' encoding='UTF-8'?>`
- `0x14003e078`: `<?xml version="1.0" encoding="utf-8"?>`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::NetworkManager::TranslateServerData(
        Microsoft::Windows::MDM::OmadmClient::NetworkManager *this,
        struct Microsoft::Windows::MDM::OmadmClient::SyncmlSessionState *a2,
        struct IStream *a3,
        unsigned __int16 **a4)
{
  struct COmaDmLogger *Logger; // rax
  __int64 v8; // r8
  void *v9; // rdi
  DWORD LastError; // ebx
  HRESULT v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  signed int v16; // ebx
  __int64 v17; // rdx
  __int64 v18; // r9
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rax
  signed int v23; // eax
  int v24; // eax
  LPSTREAM v25; // rdi
  __int64 v26; // r8
  LPSTREAM v27; // rbx
  unsigned int v28; // r15d
  HMODULE LibraryW; // rax
  __int64 v30; // r8
  HMODULE v31; // rdi
  FARPROC ProcAddress; // rax
  signed int v33; // eax
  char v34; // al
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  char *v42; // rdi
  signed int v43; // eax
  HLOCAL v44; // r14
  void *v45; // r15
  DWORD v46; // ebx
  unsigned int v47; // eax
  __int64 v48; // r8
  void *v49; // rbx
  HANDLE ProcessHeap; // rax
  struct COmaDmLogger *v51; // rax
  unsigned __int16 *v52; // rax
  void *v53; // rdi
  HANDLE v54; // rax
  int *v56; // [rsp+20h] [rbp-178h]
  int v57; // [rsp+40h] [rbp-158h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-150h] BYREF
  char v59[4]; // [rsp+50h] [rbp-148h] BYREF
  unsigned int uBytes; // [rsp+54h] [rbp-144h] BYREF
  int uBytes_4; // [rsp+58h] [rbp-140h] BYREF
  int v62; // [rsp+60h] [rbp-138h] BYREF
  int v63; // [rsp+64h] [rbp-134h] BYREF
  __int64 v64; // [rsp+68h] [rbp-130h] BYREF
  LPSTREAM ppstm; // [rsp+70h] [rbp-128h] BYREF
  LPSTREAM v66; // [rsp+78h] [rbp-120h] BYREF
  __int64 v67; // [rsp+80h] [rbp-118h] BYREF
  _QWORD v68[5]; // [rsp+88h] [rbp-110h] BYREF
  char v69; // [rsp+B0h] [rbp-E8h]
  unsigned int v70; // [rsp+B8h] [rbp-E0h] BYREF
  _QWORD v71[3]; // [rsp+C0h] [rbp-D8h] BYREF
  int v72; // [rsp+D8h] [rbp-C0h]
  int *v73; // [rsp+E0h] [rbp-B8h]
  __int128 v74; // [rsp+E8h] [rbp-B0h]
  LPVOID *p_lpMem; // [rsp+F8h] [rbp-A0h] BYREF
  unsigned __int16 *v76; // [rsp+100h] [rbp-98h] BYREF
  char v77; // [rsp+108h] [rbp-90h]
  unsigned __int16 **v78; // [rsp+110h] [rbp-88h]
  LPVOID **v79; // [rsp+120h] [rbp-78h]
  __int64 v80; // [rsp+128h] [rbp-70h]
  int v81[2]; // [rsp+130h] [rbp-68h] BYREF
  __int64 v82; // [rsp+138h] [rbp-60h]
  int *p_uBytes_4; // [rsp+140h] [rbp-58h]
  __int64 v84; // [rsp+148h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  v78 = a4;
  v57 = 0;
  Logger = COmaDmLogger::GetLogger();
  Microsoft::Windows::TelemetryLogger::LogFunctionEntryMeasure(Logger, 2, "TranslateServerData", 0);
  v71[0] = 0;
  v71[1] = "TranslateServerData";
  v71[2] = COmaDmLogger::GetLogger();
  v72 = 2;
  v73 = &v57;
  v67 = 0;
  v64 = 0;
  v66 = 0;
  lpMem = 0;
  ppstm = 0;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    uBytes_4 = 25;
    p_uBytes_4 = &uBytes_4;
    v84 = 4;
    v56 = v81;
    McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, OmaDmClientFunctionEntryPointEvent, v8, 2);
  }
  v68[0] = &v57;
  v68[1] = &v66;
  v68[2] = &ppstm;
  v68[3] = &v67;
  v68[4] = &v64;
  v69 = 1;
  v9 = (void *)*((_QWORD *)a2 + 247);
  if ( v9 )
  {
    LastError = GetLastError();
    LocalFree(v9);
    SetLastError(LastError);
  }
  *((_QWORD *)a2 + 247) = 0;
  if ( *((_DWORD *)a2 + 113) )
  {
    v62 = 0;
    v11 = (*(__int64 (__fastcall **)(_QWORD, struct IStream *, int *))(**((_QWORD **)this + 10) + 376LL))(
            *((_QWORD *)this + 10),
            a3,
            &v62);
    v16 = v11;
    v57 = v11;
    if ( v11 < 0 )
    {
      v17 = 1386;
LABEL_8:
      v18 = (unsigned int)v11;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\networkmanager.cpp",
        (const char *)v18,
        (int)v56);
      goto LABEL_94;
    }
    if ( !v62 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v13, v12, v14, v15, v56);
    v11 = (*(__int64 (__fastcall **)(_QWORD, struct IStream *, __int64 *))(**((_QWORD **)this + 10) + 392LL))(
            *((_QWORD *)this + 10),
            a3,
            &v64);
    v16 = v11;
    v57 = v11;
    if ( v11 < 0 )
    {
      v17 = 1391;
      goto LABEL_8;
    }
    if ( !v64 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v19, 0, v20, v21, v56);
    v22 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 400LL))(*((_QWORD *)this + 10));
    if ( !v22 )
    {
      v23 = GetLastError();
      v16 = v23;
      if ( v23 > 0 )
        v16 = (unsigned __int16)v23 | 0x80070000;
      goto LABEL_19;
    }
    v81[1] = 0;
    v82 = v22;
    v81[0] = v62;
    v74 = 0;
    v56 = v81;
    v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 9) + 16LL))(
            *((_QWORD *)this + 9),
            *((unsigned int *)a2 + 113),
            *((_QWORD *)a2 + 264),
            *((_QWORD *)a2 + 263));
    v16 = v24;
    v57 = v24;
    if ( v24 < 0 )
    {
      LODWORD(v71[0]) = 12081;
      HIDWORD(v71[0]) = v24;
      goto LABEL_94;
    }
    v11 = CreateStreamOnHGlobal(0, 1, &ppstm);
    v16 = v11;
    v57 = v11;
    if ( v11 < 0 )
    {
      v17 = 1417;
      goto LABEL_8;
    }
    uBytes_4 = 0;
    v11 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, int *))(*(_QWORD *)ppstm + 32LL))(
            ppstm,
            *((_QWORD *)&v74 + 1),
            (unsigned int)v74,
            &uBytes_4);
    v16 = v11;
    v57 = v11;
    if ( v11 < 0 )
    {
      v17 = 1422;
      goto LABEL_8;
    }
    if ( (_DWORD)v74 != uBytes_4 )
    {
      v16 = -2147467259;
LABEL_19:
      v57 = v16;
      goto LABEL_94;
    }
    v25 = ppstm;
  }
  else
  {
    v25 = a3;
  }
  if ( !InvStrCmpIW(*((const unsigned __int16 **)a2 + 94), L"application/vnd.syncml.dm+wbxml") )
  {
    v11 = CreateStreamOnHGlobal(0, 1, &v66);
    v16 = v11;
    v57 = v11;
    if ( v11 < 0 )
    {
      v17 = 1437;
      goto LABEL_8;
    }
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 0x10) != 0 )
    {
      v56 = (int *)&p_lpMem;
      McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, TIME_WBXML_DECODE_MARKER_START, v26, 1);
    }
    v27 = v66;
    v28 = *((_DWORD *)a2 + 199);
    LibraryW = LoadLibraryW(L"dmxmlhelputils.dll");
    v31 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "ConvertWBXmlToTextXmlEx");
      if ( ProcAddress )
      {
        LODWORD(v56) = 1;
        v16 = ((__int64 (__fastcall *)(char *, struct IStream *, _QWORD, LPSTREAM))ProcAddress)(
                (char *)a2 + 8,
                a3,
                v28,
                v27);
      }
      else
      {
        v33 = GetLastError();
        v16 = v33;
        if ( v33 > 0 )
          v16 = (unsigned __int16)v33 | 0x80070000;
      }
      FreeLibrary(v31);
    }
    else
    {
      v16 = -2147467263;
    }
    v57 = v16;
    v34 = Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits;
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 0x10) != 0 )
    {
      v56 = (int *)&p_lpMem;
      McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, TIME_WBXML_DECODE_MARKER_STOP, v30, 1);
      v16 = v57;
      v34 = Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits;
    }
    if ( v16 < 0 )
    {
      if ( (v34 & 2) != 0 )
      {
        LODWORD(p_lpMem) = v16;
        v79 = &p_lpMem;
        v80 = 4;
        McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, FailedWbxmlToXmlConversionEvent, v30, 2);
        v16 = v57;
        v34 = Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits;
      }
      if ( (v34 & 8) == 0 )
        goto LABEL_50;
      McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, ServerWbxmlResponseEvent, v30, 1);
      (*(void (__fastcall **)(_QWORD, struct IStream *))(**((_QWORD **)this + 1) + 32LL))(*((_QWORD *)this + 1), a3);
LABEL_49:
      v16 = v57;
LABEL_50:
      LODWORD(v71[0]) = 3016;
LABEL_51:
      HIDWORD(v71[0]) = v16;
      goto LABEL_94;
    }
    if ( (v34 & 1) != 0 )
    {
      v56 = (int *)&p_lpMem;
      McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, SuccessfulWbxmlToXmlConversionEvent, v30, 1);
    }
    v25 = v66;
  }
  uBytes = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD, LPSTREAM, unsigned int *))(**((_QWORD **)this + 10) + 376LL))(
          *((_QWORD *)this + 10),
          v25,
          &uBytes);
  v16 = v11;
  v57 = v11;
  if ( v11 < 0 )
  {
    v17 = 1476;
    goto LABEL_8;
  }
  if ( !uBytes )
    MicrosoftTelemetryAssertTriggeredNoArgs(v36, v35, v37, v38, v56);
  p_lpMem = 0;
  v11 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, __int64))(*(_QWORD *)v25 + 40LL))(v25, 0, 2);
  v16 = v11;
  v57 = v11;
  if ( v11 < 0 )
  {
    v17 = 1483;
    goto LABEL_8;
  }
  v59[0] = 0;
  v63 = 0;
  v11 = (*(__int64 (__fastcall **)(LPSTREAM, char *, __int64, int *))(*(_QWORD *)v25 + 32LL))(v25, v59, 1, &v63);
  v16 = v11;
  v57 = v11;
  if ( v11 < 0 )
  {
    v17 = 1489;
    goto LABEL_8;
  }
  if ( v63 != 1 )
  {
    LODWORD(v71[0]) = 18062;
    v16 = -2147467259;
    goto LABEL_51;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, LPSTREAM))(**((_QWORD **)this + 10) + 384LL))(*((_QWORD *)this + 10), v25);
  v16 = v11;
  v57 = v11;
  if ( v11 < 0 )
  {
    v17 = 1498;
    goto LABEL_8;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, LPSTREAM, __int64 *))(**((_QWORD **)this + 10) + 392LL))(
          *((_QWORD *)this + 10),
          v25,
          &v67);
  v16 = v11;
  v57 = v11;
  if ( v11 < 0 )
  {
    v17 = 1502;
    goto LABEL_8;
  }
  if ( !v67 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v39, 0, v40, v41, v56);
  v42 = (char *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 400LL))(*((_QWORD *)this + 10));
  if ( !v42 )
  {
    v43 = GetLastError();
    v16 = v43;
    if ( v43 > 0 )
      v16 = (unsigned __int16)v43 | 0x80070000;
    goto LABEL_19;
  }
  if ( *((_DWORD *)a2 + 158) == 2 )
  {
    v44 = LocalAlloc(0, uBytes);
    v45 = (void *)*((_QWORD *)a2 + 247);
    if ( v45 )
    {
      v46 = GetLastError();
      LocalFree(v45);
      SetLastError(v46);
    }
    *((_QWORD *)a2 + 247) = v44;
    if ( !v44 )
    {
      v16 = -2147024882;
      v57 = -2147024882;
      v18 = 2147942414LL;
      v17 = 1527;
      goto LABEL_9;
    }
    v57 = 0;
    memcpy_0(v44, v42, uBytes);
    v47 = uBytes;
    *((_DWORD *)a2 + 496) = uBytes;
  }
  else
  {
    v47 = uBytes;
  }
  if ( v47 > 0x27
    && (!_strnicmp(v42, "<?xml version=\"1.0\" encoding=\"utf-8\"?>", 0x26u)
     || !_strnicmp(v42, "<?xml version='1.0' encoding='UTF-8'?>", 0x26u)) )
  {
    v42 += 38;
  }
  v70 = 0;
  p_lpMem = &lpMem;
  v76 = 0;
  v77 = 1;
  v57 = MBToUnicode(v42, 0xFDE9u, &v76, &v70);
  if ( v77 )
  {
    v49 = *p_lpMem;
    *p_lpMem = v76;
    if ( v49 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v49);
    }
  }
  if ( v57 < 0 )
  {
    if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
    {
      McGenEventWrite_EventWriteTransfer(WP_OMADM_CLIENT_PROVIDER_Context, ServerRawDataResponseEvent, v48, 1);
      (*(void (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)this + 1) + 24LL))(
        *((_QWORD *)this + 1),
        v42,
        uBytes);
    }
    goto LABEL_49;
  }
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    v51 = COmaDmLogger::GetLogger();
    Microsoft::Windows::TelemetryLogger::LogMeasure(v51, 2, 0, L"XML from server =");
    (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 1) + 8LL))(*((_QWORD *)this + 1), v42);
  }
  v52 = (unsigned __int16 *)lpMem;
  lpMem = 0;
  *v78 = v52;
  v16 = v57;
LABEL_94:
  wil::details::ScopeExitFn__lambda_a3df9c5fcff703ac03853df8b7626e8a___::_ScopeExitFn__lambda_a3df9c5fcff703ac03853df8b7626e8a___(v68);
  v53 = lpMem;
  lpMem = 0;
  if ( v53 )
  {
    v54 = GetProcessHeap();
    HeapFree(v54, 0, v53);
  }
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v71);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14003d890  push    rbx
0x14003d892  push    rsi
0x14003d893  push    rdi
0x14003d894  push    r12
0x14003d896  push    r13
0x14003d898  push    r14
0x14003d89a  push    r15
0x14003d89c  sub     rsp, 160h
0x14003d8a3  mov     rax, cs:__security_cookie
0x14003d8aa  xor     rax, rsp
0x14003d8ad  mov     [rsp+198h+var_48], rax
0x14003d8b5  mov     [rsp+198h+var_88], r9
0x14003d8bd  mov     r12, r8
0x14003d8c0  mov     rsi, rdx
0x14003d8c3  mov     r13, rcx
0x14003d8c6  xor     r15d, r15d
0x14003d8c9  mov     [rsp+198h+var_158], r15d
0x14003d8ce  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14003d8d3  xor     r9d, r9d
0x14003d8d6  lea     rbx, aTranslateserve; "TranslateServerData"
0x14003d8dd  mov     r8, rbx
0x14003d8e0  lea     edi, [r15+2]
0x14003d8e4  mov     edx, edi
0x14003d8e6  mov     rcx, rax
0x14003d8e9  call    ?LogFunctionEntryMeasure@TelemetryLogger@Windows@Microsoft@@QEAAXW4TracingLevel@23@PEBDPEBGZZ; Microsoft::Windows::TelemetryLogger::LogFunctionEntryMeasure(Microsoft::Windows::TracingLevel,char const *,ushort const *,...)
0x14003d8ee  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14003d8f3  mov     [rsp+198h+var_D8], r15
0x14003d8fb  mov     [rsp+198h+var_D0], rbx
0x14003d903  mov     [rsp+198h+var_C8], rax
0x14003d90b  mov     [rsp+198h+var_C0], edi
0x14003d912  lea     rax, [rsp+198h+var_158]
0x14003d917  mov     [rsp+198h+var_B8], rax
0x14003d91f  mov     [rsp+198h+var_118], r15
0x14003d927  mov     [rsp+198h+var_130], r15
0x14003d92c  mov     [rsp+198h+var_120], r15
0x14003d931  mov     [rsp+198h+lpMem], r15
0x14003d936  mov     [rsp+198h+ppstm], r15
0x14003d93b  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 8
0x14003d942  jz      short loc_14003D988
0x14003d944  mov     dword ptr [rsp+198h+uBytes+4], 19h
0x14003d94c  lea     rax, [rsp+198h+uBytes+4]
0x14003d951  mov     [rsp+198h+var_58], rax
0x14003d959  mov     [rsp+198h+var_50], 4
0x14003d965  lea     rax, [rsp+198h+var_68]
0x14003d96d  mov     qword ptr [rsp+198h+var_178], rax; int
0x14003d972  mov     r9d, edi
0x14003d975  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x14003d97c  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14003d983  call    McGenEventWrite_EventWriteTransfer
0x14003d988  lea     rax, [rsp+198h+var_158]
0x14003d98d  mov     [rsp+198h+var_110], rax
0x14003d995  lea     rax, [rsp+198h+var_120]
0x14003d99a  mov     [rsp+198h+var_108], rax
0x14003d9a2  lea     rax, [rsp+198h+ppstm]
0x14003d9a7  mov     [rsp+198h+var_100], rax
0x14003d9af  lea     rax, [rsp+198h+var_118]
0x14003d9b7  mov     [rsp+198h+var_F8], rax
0x14003d9bf  lea     rax, [rsp+198h+var_130]
0x14003d9c4  mov     [rsp+198h+var_F0], rax
0x14003d9cc  mov     [rsp+198h+var_E8], 1
0x14003d9d4  mov     rdi, [rsi+7B8h]
0x14003d9db  test    rdi, rdi
0x14003d9de  jz      short loc_14003DA0B
0x14003d9e0  call    cs:__imp_GetLastError
0x14003d9e7  nop     dword ptr [rax+rax+00h]
0x14003d9ec  mov     ebx, eax
0x14003d9ee  mov     rcx, rdi; hMem
0x14003d9f1  call    cs:__imp_LocalFree
0x14003d9f8  nop     dword ptr [rax+rax+00h]
0x14003d9fd  mov     ecx, ebx; dwErrCode
0x14003d9ff  call    cs:__imp_SetLastError
0x14003da06  nop     dword ptr [rax+rax+00h]
0x14003da0b  mov     [rsi+7B8h], r15
0x14003da12  cmp     [rsi+1C4h], r15d
0x14003da19  jz      loc_14003DC00
0x14003da1f  mov     [rsp+198h+var_138], r15d
0x14003da24  mov     rcx, [r13+50h]
0x14003da28  mov     rax, [rcx]
0x14003da2b  lea     r8, [rsp+198h+var_138]
0x14003da30  mov     rdx, r12
0x14003da33  mov     rax, [rax+178h]
0x14003da3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003da3f  mov     ebx, eax
0x14003da41  mov     [rsp+198h+var_158], eax
0x14003da45  test    eax, eax
0x14003da47  jns     short loc_14003DA6A
0x14003da49  mov     edx, 56Ah; void *
0x14003da4e  mov     r9d, eax; char *
0x14003da51  mov     rcx, [rsp+198h]; this
0x14003da59  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14003da60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003da65  jmp     loc_14003E1E8
0x14003da6a  cmp     [rsp+198h+var_138], r15d
0x14003da6f  jnz     short loc_14003DA76
0x14003da71  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "0 != cbPackageData")
0x14003da76  mov     rcx, [r13+50h]
0x14003da7a  mov     rax, [rcx]
0x14003da7d  lea     r8, [rsp+198h+var_130]
0x14003da82  mov     rdx, r12
0x14003da85  mov     rax, [rax+188h]
0x14003da8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003da91  mov     ebx, eax
0x14003da93  mov     [rsp+198h+var_158], eax
0x14003da97  test    eax, eax
0x14003da99  jns     short loc_14003DAA2
0x14003da9b  mov     edx, 56Fh
0x14003daa0  jmp     short loc_14003DA4E
0x14003daa2  mov     rdx, [rsp+198h+var_130]
0x14003daa7  test    rdx, rdx
0x14003daaa  jnz     short loc_14003DAB6
0x14003daac  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "nullptr != hGlob2")
0x14003dab1  mov     rdx, [rsp+198h+var_130]
0x14003dab6  mov     rcx, [r13+50h]
0x14003daba  mov     rax, [rcx]
0x14003dabd  mov     rax, [rax+190h]
0x14003dac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dac9  test    rax, rax
0x14003dacc  jnz     short loc_14003DAF2
0x14003dace  call    cs:__imp_GetLastError
0x14003dad5  nop     dword ptr [rax+rax+00h]
0x14003dada  mov     ebx, eax
0x14003dadc  test    eax, eax
0x14003dade  jle     short loc_14003DAE9
0x14003dae0  movzx   ebx, ax
0x14003dae3  or      ebx, 80070000h
0x14003dae9  mov     [rsp+198h+var_158], ebx
0x14003daed  jmp     loc_14003E1E8
0x14003daf2  mov     [rsp+198h+var_64], r15d
0x14003dafa  mov     [rsp+198h+var_60], rax
0x14003db02  mov     eax, [rsp+198h+var_138]
0x14003db06  mov     [rsp+198h+var_68], eax
0x14003db0d  xorps   xmm0, xmm0
0x14003db10  movups  [rsp+198h+var_B0], xmm0
0x14003db18  mov     rcx, [r13+48h]
0x14003db1c  mov     rax, [rcx]
0x14003db1f  lea     rdx, [rsp+198h+var_B0]
0x14003db27  mov     [rsp+198h+var_170], rdx
0x14003db2c  lea     rdx, [rsp+198h+var_68]
0x14003db34  mov     qword ptr [rsp+198h+var_178], rdx
0x14003db39  mov     r9, [rsi+838h]
0x14003db40  mov     r8, [rsi+840h]
0x14003db47  mov     edx, [rsi+1C4h]
0x14003db4d  mov     rax, [rax+10h]
0x14003db51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003db56  mov     ebx, eax
0x14003db58  mov     [rsp+198h+var_158], eax
0x14003db5c  test    eax, eax
0x14003db5e  jns     short loc_14003DB77
0x14003db60  mov     dword ptr [rsp+198h+var_D8], 2F31h
0x14003db6b  mov     dword ptr [rsp+198h+var_D8+4], eax
0x14003db72  jmp     loc_14003E1E8
0x14003db77  lea     r8, [rsp+198h+ppstm]; ppstm
0x14003db7c  mov     edx, 1; fDeleteOnRelease
0x14003db81  xor     ecx, ecx; hGlobal
0x14003db83  call    cs:__imp_CreateStreamOnHGlobal
0x14003db8a  nop     dword ptr [rax+rax+00h]
0x14003db8f  mov     ebx, eax
0x14003db91  mov     [rsp+198h+var_158], eax
0x14003db95  test    eax, eax
0x14003db97  jns     short loc_14003DBA3
0x14003db99  mov     edx, 589h
0x14003db9e  jmp     loc_14003DA4E
0x14003dba3  mov     dword ptr [rsp+198h+uBytes+4], r15d
0x14003dba8  mov     rcx, [rsp+198h+ppstm]
0x14003dbad  mov     rax, [rcx]
0x14003dbb0  lea     r9, [rsp+198h+uBytes+4]
0x14003dbb5  mov     r8d, dword ptr [rsp+198h+var_B0]
0x14003dbbd  mov     rdx, qword ptr [rsp+198h+var_B0+8]
0x14003dbc5  mov     rax, [rax+20h]
0x14003dbc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dbce  mov     ebx, eax
0x14003dbd0  mov     [rsp+198h+var_158], eax
0x14003dbd4  test    eax, eax
0x14003dbd6  jns     short loc_14003DBE2
0x14003dbd8  mov     edx, 58Eh
0x14003dbdd  jmp     loc_14003DA4E
0x14003dbe2  mov     eax, dword ptr [rsp+198h+uBytes+4]
0x14003dbe6  cmp     dword ptr [rsp+198h+var_B0], eax
0x14003dbed  jz      short loc_14003DBF9
0x14003dbef  mov     ebx, 80004005h
0x14003dbf4  jmp     loc_14003DAE9
0x14003dbf9  mov     rdi, [rsp+198h+ppstm]
0x14003dbfe  jmp     short loc_14003DC03
0x14003dc00  mov     rdi, r12
0x14003dc03  lea     rdx, aApplicationVnd; "application/vnd.syncml.dm+wbxml"
0x14003dc0a  mov     rcx, [rsi+2F0h]
0x14003dc11  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x14003dc18  nop     dword ptr [rax+rax+00h]
0x14003dc1d  mov     r14d, 80070000h
0x14003dc23  test    eax, eax
0x14003dc25  jnz     loc_14003DE3C
0x14003dc2b  lea     r8, [rsp+198h+var_120]; ppstm
0x14003dc30  lea     edi, [rax+1]
0x14003dc33  mov     edx, edi; fDeleteOnRelease
0x14003dc35  xor     ecx, ecx; hGlobal
0x14003dc37  call    cs:__imp_CreateStreamOnHGlobal
0x14003dc3e  nop     dword ptr [rax+rax+00h]
0x14003dc43  mov     ebx, eax
0x14003dc45  mov     [rsp+198h+var_158], eax
0x14003dc49  test    eax, eax
0x14003dc4b  jns     short loc_14003DC57
0x14003dc4d  mov     edx, 59Dh
0x14003dc52  jmp     loc_14003DA4E
0x14003dc57  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, 10h
0x14003dc5e  jz      short loc_14003DC83
0x14003dc60  lea     rax, [rsp+198h+var_A0]
0x14003dc68  mov     qword ptr [rsp+198h+var_178], rax
0x14003dc6d  mov     r9d, edi
0x14003dc70  lea     rdx, TIME_WBXML_DECODE_MARKER_START
0x14003dc77  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14003dc7e  call    McGenEventWrite_EventWriteTransfer
0x14003dc83  mov     rbx, [rsp+198h+var_120]
0x14003dc88  mov     r15d, [rsi+31Ch]
0x14003dc8f  lea     rcx, aDmxmlhelputils; "dmxmlhelputils.dll"
0x14003dc96  call    cs:__imp_LoadLibraryW
0x14003dc9d  nop     dword ptr [rax+rax+00h]
0x14003dca2  mov     rdi, rax
0x14003dca5  test    rax, rax
0x14003dca8  jz      short loc_14003DD0C
0x14003dcaa  lea     rdx, aConvertwbxmlto; "ConvertWBXmlToTextXmlEx"
0x14003dcb1  mov     rcx, rax; hModule
0x14003dcb4  call    cs:__imp_GetProcAddress
0x14003dcbb  nop     dword ptr [rax+rax+00h]
0x14003dcc0  test    rax, rax
0x14003dcc3  jz      short loc_14003DCE3
0x14003dcc5  lea     rcx, [rsi+8]
0x14003dcc9  mov     [rsp+198h+var_178], 1
0x14003dcd1  mov     r9, rbx
0x14003dcd4  mov     r8d, r15d
0x14003dcd7  mov     rdx, r12
0x14003dcda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dcdf  mov     ebx, eax
0x14003dce1  jmp     short loc_14003DCFB
0x14003dce3  call    cs:__imp_GetLastError
0x14003dcea  nop     dword ptr [rax+rax+00h]
0x14003dcef  mov     ebx, eax
0x14003dcf1  test    eax, eax
0x14003dcf3  jle     short loc_14003DCFB
0x14003dcf5  movzx   ebx, ax
0x14003dcf8  or      ebx, r14d
0x14003dcfb  mov     rcx, rdi; hLibModule
0x14003dcfe  call    cs:__imp_FreeLibrary
0x14003dd05  nop     dword ptr [rax+rax+00h]
0x14003dd0a  jmp     short loc_14003DD11
0x14003dd0c  mov     ebx, 80004001h
0x14003dd11  mov     [rsp+198h+var_158], ebx
0x14003dd15  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x14003dd1b  test    al, 10h
0x14003dd1d  jz      short loc_14003DD4F
0x14003dd1f  lea     rax, [rsp+198h+var_A0]
0x14003dd27  mov     qword ptr [rsp+198h+var_178], rax
0x14003dd2c  mov     r9d, 1
0x14003dd32  lea     rdx, TIME_WBXML_DECODE_MARKER_STOP
0x14003dd39  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14003dd40  call    McGenEventWrite_EventWriteTransfer
0x14003dd45  mov     ebx, [rsp+198h+var_158]
0x14003dd49  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x14003dd4f  xor     r15d, r15d
0x14003dd52  test    ebx, ebx
0x14003dd54  jns     loc_14003DE07
0x14003dd5a  test    al, 2
0x14003dd5c  jz      short loc_14003DDAF
0x14003dd5e  mov     dword ptr [rsp+198h+var_A0], ebx
0x14003dd65  lea     rax, [rsp+198h+var_A0]
0x14003dd6d  mov     [rsp+198h+var_78], rax
0x14003dd75  mov     [rsp+198h+var_70], 4
0x14003dd81  lea     rax, [rsp+198h+var_88]
0x14003dd89  mov     qword ptr [rsp+198h+var_178], rax
0x14003dd8e  lea     r9d, [r15+2]
0x14003dd92  lea     rdx, FailedWbxmlToXmlConversionEvent
0x14003dd99  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14003dda0  call    McGenEventWrite_EventWriteTransfer
0x14003dda5  mov     ebx, [rsp+198h+var_158]
0x14003dda9  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x14003ddaf  test    al, 8
0x14003ddb1  jz      short loc_14003DDF0
0x14003ddb3  lea     rax, [rsp+198h+var_88]
0x14003ddbb  mov     qword ptr [rsp+198h+var_178], rax
0x14003ddc0  mov     r9d, 1
0x14003ddc6  lea     rdx, ServerWbxmlResponseEvent
0x14003ddcd  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14003ddd4  call    McGenEventWrite_EventWriteTransfer
0x14003ddd9  mov     rcx, [r13+8]
0x14003dddd  mov     rax, [rcx]
0x14003dde0  mov     rdx, r12
0x14003dde3  mov     rax, [rax+20h]
0x14003dde7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ddec  mov     ebx, [rsp+198h+var_158]
0x14003ddf0  mov     dword ptr [rsp+198h+var_D8], 0BC8h
0x14003ddfb  mov     dword ptr [rsp+198h+var_D8+4], ebx
0x14003de02  jmp     loc_14003E1E8
0x14003de07  mov     r12d, 1
0x14003de0d  test    r12b, al
0x14003de10  jz      short loc_14003DE35
0x14003de12  lea     rax, [rsp+198h+var_A0]
0x14003de1a  mov     qword ptr [rsp+198h+var_178], rax
0x14003de1f  mov     r9d, r12d
0x14003de22  lea     rdx, SuccessfulWbxmlToXmlConversionEvent
0x14003de29  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14003de30  call    McGenEventWrite_EventWriteTransfer
  ... truncated ...
```
