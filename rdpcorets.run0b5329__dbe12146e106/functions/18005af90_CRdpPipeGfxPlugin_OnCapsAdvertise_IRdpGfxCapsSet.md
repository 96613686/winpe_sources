# CRdpPipeGfxPlugin::OnCapsAdvertise(IRdpGfxCapsSet *)

- ea: `0x18005af90`
- end: `0x18005bdb5`
- name: `?OnCapsAdvertise@CRdpPipeGfxPlugin@@UEAAJPEAUIRdpGfxCapsSet@@@Z`
- size: `3621`
- prototype: `__int64 __fastcall(CRdpPipeGfxPlugin *__hidden this, struct IRdpGfxCapsSet *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800015f0`
- `0x1800071c0`
- `0x1800071f0`
- `0x18000f784`
- `0x180012200`
- `0x180033da0`
- `0x18005aa94`
- `0x18005af90`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005b24a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005b24a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b25c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b25c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005b60a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005b73f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005b60a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005b73f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18005b6c4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18005b6c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005b706`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005b706`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18005b044`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18005bca7`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18005b044`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18005bca7`
- `OLEAUT32!__imp_VariantInit` at `0x18005b020`
- `OLEAUT32!__imp_VariantInit` at `0x18005b02a`
- `OLEAUT32!__imp_VariantInit` at `0x18005b020`
- `OLEAUT32!__imp_VariantInit` at `0x18005b02a`
- `OLEAUT32!__imp_VariantClear` at `0x18005bcdb`
- `OLEAUT32!__imp_VariantClear` at `0x18005bce5`
- `OLEAUT32!__imp_VariantClear` at `0x18005bcdb`
- `OLEAUT32!__imp_VariantClear` at `0x18005bce5`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18005b31d`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18005b31d`

## string_xrefs

- `0x18005b195`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18005b29b`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18005b504`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18005b699`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18005bbe3`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umrdppipegfxplugin.cpp`
- `0x18005b21a`: `Failed to load Rdplite.dll`
- `0x18005b338`: `Failed to create property store`
- `0x18005b5b0`: `Failed to remove DirectStreamMediaControl property from platform context`
- `0x18005b6df`: `Failed to convert encoding profile GUID string to CLSID`
- `0x18005b787`: `Failed to allocate memory for CLSID`
- `0x18005b814`: `Failed to get pipe protocol`

## pseudocode

```c
__int64 __fastcall CRdpPipeGfxPlugin::OnCapsAdvertise(CRdpPipeGfxPlugin *this, struct IRdpGfxCapsSet *a2)
{
  __int64 v3; // rbx
  __int64 v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rsi
  char *v8; // r15
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // r9d
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rcx
  __int64 v23; // rcx
  int RdpLite; // esi
  int v25; // r9d
  int v26; // ecx
  const char *v27; // rax
  char *v28; // rdx
  FARPROC ProcAddress; // r12
  signed int LastError; // eax
  int v31; // ecx
  int v32; // r9d
  __int64 v33; // rcx
  int v34; // eax
  int v35; // r8d
  int v36; // r9d
  const char *v37; // rax
  GUID *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rdx
  __int64 v42; // r8
  void *v43; // rcx
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // rdx
  __int64 v57; // r8
  int v59; // [rsp+50h] [rbp-B0h] BYREF
  int v60; // [rsp+54h] [rbp-ACh] BYREF
  const char *v61; // [rsp+58h] [rbp-A8h] BYREF
  const char *v62; // [rsp+60h] [rbp-A0h] BYREF
  const char *v63; // [rsp+68h] [rbp-98h] BYREF
  const char *v64; // [rsp+70h] [rbp-90h] BYREF
  void *ppv; // [rsp+78h] [rbp-88h] BYREF
  __int64 (__fastcall ***v66)(_QWORD, GUID *, __int64 *); // [rsp+80h] [rbp-80h] BYREF
  __int64 v67; // [rsp+88h] [rbp-78h] BYREF
  PROPVARIANT pvar[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v69; // [rsp+A0h] [rbp-60h]
  __int64 v70; // [rsp+A8h] [rbp-58h] BYREF
  int v71; // [rsp+B0h] [rbp-50h] BYREF
  int v72; // [rsp+B4h] [rbp-4Ch] BYREF
  __int64 v73; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v74; // [rsp+C0h] [rbp-40h] BYREF
  void *v75; // [rsp+C8h] [rbp-38h] BYREF
  void *v76; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v77; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v78; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v79; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v80; // [rsp+F0h] [rbp-10h] BYREF
  const char *v81; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v82; // [rsp+100h] [rbp+0h] BYREF
  VARIANTARG pvarg; // [rsp+108h] [rbp+8h] BYREF
  VARIANTARG v84; // [rsp+120h] [rbp+20h] BYREF
  GUID pclsid; // [rsp+138h] [rbp+38h] BYREF

  v62 = (const char *)a2;
  v77 = 0;
  v79 = 0;
  v66 = 0;
  v70 = 0;
  v3 = 0;
  v67 = 0;
  v78 = 0;
  v4 = 0;
  v76 = 0;
  v75 = 0;
  v73 = 0;
  v74 = 0;
  ppv = 0;
  v82 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v84, 0, sizeof(v84));
  *(_OWORD *)pvar = 0;
  v69 = 0;
  VariantInit(&pvarg);
  VariantInit(&v84);
  v81 = (char *)this + 152;
  if ( *((_DWORD *)this + 40) )
    PAL_System_CritSecEnter(*((_QWORD *)this + 19), v5, v6);
  if ( *((_QWORD *)this + 13) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v77, v5, v6);
    v4 = *((_QWORD *)this + 13);
    v77 = v4;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v77);
  }
  v7 = 0;
  if ( *((_QWORD *)this + 9) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v78, v5, v6);
    v3 = *((_QWORD *)this + 9);
    v78 = v3;
    if ( v3 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
      v7 = v3;
    }
  }
  v8 = (char *)this + 128;
  if ( *((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 16) != v66 )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v66, v5, v6);
    v66 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v8;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v66);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v81);
  if ( v66 )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v82, v9, v10);
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v74, v12, v13);
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v73, v14, v15);
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v75, v16, v17);
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v76, v18, v19);
    v22 = v67;
    if ( v67 )
    {
      v67 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = v70;
    if ( v70 )
    {
      v70 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    RdpLite = 0;
    goto LABEL_122;
  }
  if ( !v7 )
  {
    RdpLite = -2147418113;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v60 = 724;
      v62 = "Called in bad state";
      v63 = "OnCapsAdvertise";
      v64 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
      v59 = -2147418113;
      v61 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147418113,
        (unsigned int)&word_18019AC06,
        v10,
        v11,
        (__int64)&v61,
        (__int64)&v59,
        (__int64)&v64,
        (__int64)&v60,
        (__int64)&v63,
        (__int64)&v62);
    }
    goto LABEL_108;
  }
  RdpLite = CRdpPipeGfxPlugin::LoadRdpLite((CRdpPipeGfxPlugin *)((char *)this - 8));
  if ( RdpLite < 0 )
  {
    v26 = dword_1801B76C8;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v27 = "Failed to load Rdplite.dll";
      v59 = 730;
      v28 = (char *)&word_18019ABB6;
LABEL_106:
      v61 = v27;
      v63 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
      v37 = "Error HResult failed";
      v60 = RdpLite;
      goto LABEL_107;
    }
    goto LABEL_108;
  }
  ProcAddress = GetProcAddress(*((HMODULE *)this + 17), "RdpLite_ClassFactory");
  if ( !ProcAddress )
  {
    LastError = GetLastError();
    RdpLite = LastError;
    if ( LastError > 0 )
      RdpLite = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v59 = 741;
      v61 = "Failed to load address of ClassFactory";
      v64 = "OnCapsAdvertise";
      v63 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
      v60 = RdpLite;
      v62 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v31,
        (unsigned int)&word_18019AB66,
        v10,
        v32,
        (__int64)&v62,
        (__int64)&v60,
        (__int64)&v63,
        (__int64)&v59,
        (__int64)&v64,
        (__int64)&v61);
    }
    if ( RdpLite >= 0 )
      goto LABEL_112;
    goto LABEL_108;
  }
  RdpLite = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  if ( RdpLite < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v27 = "Failed to create property store";
      v59 = 750;
      v28 = (char *)&word_18019AB16;
      goto LABEL_106;
    }
LABEL_108:
    if ( v67 )
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v67 + 296LL))(v67, 0);
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v67 + 304LL))(v67, 0);
    }
    if ( v66 )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease(&v66, v9, v10);
      v66 = 0;
      TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v66);
    }
    goto LABEL_112;
  }
  LOWORD(pvar[0]) = 72;
  pvar[1] = (char *)this + 196;
  RdpLite = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
              ppv,
              PKEY_Activity_Id,
              pvar);
  if ( RdpLite < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v27 = "Failed to set PKEY_Activity_Id property";
      v59 = 762;
      v28 = (char *)&word_18019AAC6;
      goto LABEL_106;
    }
    goto LABEL_108;
  }
  if ( v4 )
  {
    LODWORD(pvar[1]) = 0;
    LOWORD(pvar[0]) = 19;
    if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, PROPVARIANT *))(*(_QWORD *)v4 + 40LL))(
           v4,
           L"GfxPipeline::ImageQualityPolicy",
           &pvar[1]) >= 0 )
      (*(void (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
        ppv,
        PKEY_GrfxPipelineImageQuality,
        pvar);
  }
  v33 = *((_QWORD *)this + 12);
  v71 = 0;
  v34 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v33 + 32LL))(
          v33,
          L"EnableDirectStreamMediaApiServer",
          &v71);
  if ( v34 >= 0 )
  {
    LOWORD(pvar[0]) = 11;
    LOWORD(pvar[1]) = v71;
    RdpLite = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                ppv,
                PKEY_EnableDirectStreamMediaApiServer,
                pvar);
    if ( RdpLite < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v27 = "Failed to set PKEY_EnableDirectStreamMediaApiServer property";
        v59 = 799;
        v28 = (char *)&word_18019AA36;
        goto LABEL_106;
      }
      goto LABEL_108;
    }
  }
  else if ( (unsigned int)dword_1801B76C8 > 3 )
  {
    v59 = v34;
    v61 = "OnCapsAdvertise";
    v64 = "Failed to get CONN_PROPERTY_ENABLE_DIRECT_STREAM_MEDIA_API_SERVER property";
    v63 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      dword_1801B76C8,
      (unsigned int)&byte_18019AA87,
      v35,
      v36,
      (__int64)&v63,
      (__int64)&v64,
      (__int64)&v59,
      (__int64)&v61);
  }
  if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 12) + 24LL))(
         *((_QWORD *)this + 12),
         L"DirectStreamMediaControl",
         &pvarg) >= 0 )
  {
    if ( pvarg.vt != 13 )
    {
      v26 = -2147418113;
      RdpLite = -2147418113;
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_108;
      v59 = 813;
      v61 = "DirectStreamMediaControl is not set properly";
      v28 = byte_18019A9E5;
      v60 = -2147418113;
      v63 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
      v37 = "Error condition failed";
LABEL_107:
      v62 = v37;
      v64 = "OnCapsAdvertise";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v26,
        (_DWORD)v28,
        v10,
        v25,
        (__int64)&v62,
        (__int64)&v60,
        (__int64)&v63,
        (__int64)&v59,
        (__int64)&v64,
        (__int64)&v61);
      goto LABEL_108;
    }
    RdpLite = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD))(**((_QWORD **)this + 12) + 56LL))(
                *((_QWORD *)this + 12),
                L"DirectStreamMediaControl",
                0);
    if ( RdpLite < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v27 = "Failed to remove DirectStreamMediaControl property from platform context";
        v59 = 817;
        v28 = (char *)&dword_18019A994;
        goto LABEL_106;
      }
      goto LABEL_108;
    }
    LOWORD(pvar[0]) = 13;
    pvar[1] = pvarg.bstrVal;
    (*(void (__fastcall **)(LONGLONG))(*pvarg.pllVal + 8))(pvarg.llVal);
    RdpLite = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                ppv,
                PKEY_DirectStreamMediaControl,
                pvar);
    PropVariantClear(pvar);
    if ( RdpLite < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v27 = "Failed to set PKEY_DirectStreamMediaControl property";
        v59 = 829;
        v28 = byte_18019A943;
        goto LABEL_106;
      }
      goto LABEL_108;
    }
  }
  if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 12) + 24LL))(
         *((_QWORD *)this + 12),
         L"InDriverEncodingSelectedProfile",
         &v84) >= 0 )
  {
    if ( v84.vt != 8 )
    {
      v26 = -2147418113;
      RdpLite = -2147418113;
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_108;
      v59 = 843;
      v61 = "CONN_PROPERTY_INDRIVER_ENCODING_SELECTED_PROFILE is not set properly";
      v28 = (char *)word_18019A8F2;
      v60 = -2147418113;
      v63 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdppipegfxplugin.cpp";
      v37 = "Error condition failed";
      goto LABEL_107;
    }
    pclsid = 0;
    RdpLite = CLSIDFromString(v84.bstrVal, &pclsid);
    if ( RdpLite < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v27 = "Failed to convert encoding profile GUID string to CLSID";
        v59 = 848;
        v28 = byte_18019A8A1;
        goto LABEL_106;
      }
      goto LABEL_108;
    }
    LOWORD(pvar[0]) = 72;
    v38 = (GUID *)CoTaskMemAlloc(0x10u);
    pvar[1] = v38;
    if ( !v38 )
    {
      RdpLite = -2147024882;
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v27 = "Failed to allocate memory for CLSID";
        v59 = 867;
        v28 = &byte_18019A7FF;
        goto LABEL_106;
      }
      goto LABEL_108;
    }
    *v38 = pclsid;
    RdpLite = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                ppv,
                PKEY_EncodingScenarioGuid,
                pvar);
    PropVariantClear(pvar);
    if ( RdpLite < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v27 = "Failed to set PKEY_EncodingScenarioGuid property";
        v59 = 862;
        v28 = (char *)qword_18019A850;
        goto LABEL_106;
      }
      goto LABEL_108;
    }
  }
  RdpLite = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v3)(v3, &IID_IRdpPipeManager, &v79);
  if ( RdpLite < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v27 = "Failed to QI IRdpPipeManager";
      v59 = 875;
      v28 = &byte_18019A7AF;
      goto LABEL_106;
    }
    goto LABEL_108;
  }
  RdpLite = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v79 + 32LL))(v79, &v67);
  if ( RdpLite < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v27 = "Failed to get pipe protocol";
      v59 = 878;
      v28 = &byte_18019A75F;
      goto LABEL_106;
    }
    goto LABEL_108;
  }
  RdpLite = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v67 + 280LL))(v67, &v76);
  if ( RdpLite < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v27 = "Failed to get Grfx channel";
      v59 = 881;
      v28 = &byte_18019A70F;
      goto LABEL_106;
    }
    goto LABEL_108;
  }
  pvar[1] = v76;
  LOWORD(pvar[0]) = 13;
  RdpLite = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
              ppv,
              PKEY_GrfxChannel,
              pvar);
  if ( RdpLite < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v27 = "Failed to set PKEY_GrfxChannel property";
      v59 = 889;
      v28 = &byte_18019A6BF;
      goto LABEL_106;
    }
    goto LABEL_108;
  }
  RdpLite = (*(__int64 (__fastcall **)(__int64, void **))(*(_QWORD *)v67 + 288LL))(v67, &v75);
  if ( RdpLite < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v27 = "Failed to get Mouse channel";
      v59 = 895;
      v28 = &byte_18019A66F;
      goto LABEL_106;
    }
    goto LABEL_108;
  }
  pvar[1] = v75;
  LOWORD(pvar[0]) = 13;
  RdpLite = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
              ppv,
              PKEY_MouseChannel,
              pvar);
  if ( RdpLite < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v27 = "Failed to set PKEY_MouseChannel property";
      v59 = 903;
      v28 = &byte_18019A61F;
      goto LABEL_106;
    }
    goto LABEL_108;
  }
  pvar[1] = *((PROPVARIANT *)this + 15);
  LOWORD(pvar[0]) = 13;
  RdpLite = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
              ppv,
              PKEY_DynamicVcManager,
              pvar);
  if ( RdpLite < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v27 = "Failed to set PKEY_DynamicVcManager property";
      v59 = 914;
      v28 = &byte_18019A5CF;
      goto LABEL_106;
    }
    goto LABEL_108;
  }
  LOWORD(pvar[0]) = 13;
  pvar[1] = (char *)this - 8;
  RdpLite = (*(__int64 (__fastcall **)(void *, __int64 *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
              ppv,
              PKEY_GrfxPipelineEvents,
              pvar);
  if ( RdpLite < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v27 = "Failed to set PKEY_GrfxPipelineEvents property";
      v59 = 925;
      v28 = &byte_18019A57F;
      goto LABEL_106;
    }
    goto LABEL_108;
  }
  RdpLite = ((__int64 (__fastcall *)(GUID *, GUID *, void *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))ProcAddress)(
              &CLSID_GrfxPipeline,
              &GUID_b9ad6e4c_9b94_481d_b995_2f1702f837e1,
              ppv,
              &v66);
  if ( RdpLite < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v27 = "Failed to instantiate light Rdp graphics pipeline";
      v59 = 936;
      v28 = &byte_18019A52F;
      goto LABEL_106;
    }
    goto LABEL_108;
  }
  RdpLite = (**v66)(v66, &GUID_c79e35a3_3bfe_4703_9d29_02db98bb0518, &v70);
  if ( RdpLite < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v27 = "Failed to QI IGrfxPipelinePrivate";
      v59 = 942;
      v28 = &byte_18019A4DF;
      goto LABEL_106;
    }
    goto LABEL_108;
  }
  RdpLite = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v70 + 24LL))(v70, &v73);
  if ( RdpLite < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v27 = "Failed to QueryGraphicsVChannelSink";
      v59 = 945;
      v28 = &byte_18019A48F;
      goto LABEL_106;
    }
    goto LABEL_108;
  }
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v67 + 296LL))(v67, v73);
  RdpLite = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v70 + 32LL))(v70, &v74);
  if ( RdpLite < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v27 = "Failed to QueryMouseVChannelSink";
      v59 = 953;
      v28 = &byte_18019A43F;
      goto LABEL_106;
    }
    goto LABEL_108;
  }
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v67 + 304LL))(v67, v74);
  v80 = 0;
  v72 = 0;
  (*(void (__fastcall **)(const char *, __int64 *, int *))(*(_QWORD *)v62 + 48LL))(v62, &v80, &v72);
  RdpLite = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v73 + 24LL))(
              v73,
              (unsigned int)(v72 + 8),
              v80 - 8);
  if ( RdpLite < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v27 = "Failed to pass caps payload";
      v59 = 969;
      v28 = &byte_18019A3EF;
      goto LABEL_106;
    }
    goto LABEL_108;
  }
LABEL_112:
  v61 = v81;
  if ( *((_DWORD *)v81 + 2) )
    PAL_System_CritSecEnter(*(_QWORD *)v81, v9, v10);
  if ( v66 != *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v8 )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 128, v9, v10);
    *(_QWORD *)v8 = v66;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 128);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v61);
  VariantClear(&pvarg);
  VariantClear(&v84);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v82, v39, v40);
  v43 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v43 + 16LL))(v43);
  }
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v74, v41, v42);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v73, v44, v45);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v75, v46, v47);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v76, v48, v49);
  v50 = v67;
  if ( v67 )
  {
    v67 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  }
  v51 = v70;
  if ( v70 )
  {
    v70 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  }
LABEL_122:
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v66, v20, v21);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v78, v52, v53);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v79, v54, v55);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v77, v56, v57);
  return (unsigned int)RdpLite;
}

```

## disassembly

```asm
0x18005af90  mov     [rsp-8+arg_10], rbx
0x18005af95  push    rbp
0x18005af96  push    rsi
0x18005af97  push    rdi
0x18005af98  push    r12
0x18005af9a  push    r13
0x18005af9c  push    r14
0x18005af9e  push    r15
0x18005afa0  lea     rbp, [rsp-50h]
0x18005afa5  sub     rsp, 150h
0x18005afac  mov     rax, cs:__security_cookie
0x18005afb3  xor     rax, rsp
0x18005afb6  mov     [rbp+80h+var_38], rax
0x18005afba  xor     r15d, r15d
0x18005afbd  mov     [rsp+180h+var_120], rdx
0x18005afc2  xor     eax, eax
0x18005afc4  mov     [rbp+80h+var_A8], r15
0x18005afc8  xorps   xmm0, xmm0
0x18005afcb  mov     [rbp+80h+var_98], r15
0x18005afcf  mov     r14, rcx
0x18005afd2  mov     [rbp+80h+var_100], r15
0x18005afd6  xorps   xmm1, xmm1
0x18005afd9  mov     [rbp+80h+var_D8], r15
0x18005afdd  mov     ebx, r15d
0x18005afe0  mov     [rbp+80h+var_F8], r15
0x18005afe4  lea     rcx, [rbp+80h+pvarg]; pvarg
0x18005afe8  mov     [rbp+80h+var_A0], rbx
0x18005afec  mov     edi, r15d
0x18005afef  mov     [rbp+80h+var_B0], r15
0x18005aff3  mov     [rbp+80h+var_B8], r15
0x18005aff7  mov     [rbp+80h+var_C8], r15
0x18005affb  mov     [rbp+80h+var_C0], r15
0x18005afff  mov     [rsp+180h+ppv], r15
0x18005b004  mov     [rbp+80h+var_80], r15
0x18005b008  movups  xmmword ptr [rbp+80h+pvarg], xmm0
0x18005b00c  mov     qword ptr [rbp+80h+pvarg+10h], rax
0x18005b010  movups  xmmword ptr [rbp+80h+var_60], xmm1
0x18005b014  mov     qword ptr [rbp+80h+var_60+10h], rax
0x18005b018  movups  xmmword ptr [rbp+80h+pvar], xmm0
0x18005b01c  mov     [rbp+80h+var_E0], rax
0x18005b020  call    cs:__imp_VariantInit
0x18005b026  lea     rcx, [rbp+80h+var_60]; pvarg
0x18005b02a  call    cs:__imp_VariantInit
0x18005b030  lea     rax, [r14+98h]
0x18005b037  mov     [rbp+80h+var_88], rax
0x18005b03b  cmp     [rax+8], r15d
0x18005b03f  jz      short loc_18005B04A
0x18005b041  mov     rcx, [rax]
0x18005b044  call    cs:__imp_PAL_System_CritSecEnter
0x18005b04a  cmp     [r14+68h], r15
0x18005b04e  jz      short loc_18005B06A
0x18005b050  lea     rcx, [rbp+80h+var_A8]
0x18005b054  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18005b059  mov     rdi, [r14+68h]
0x18005b05d  lea     rcx, [rbp+80h+var_A8]
0x18005b061  mov     [rbp+80h+var_A8], rdi
0x18005b065  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18005b06a  mov     rsi, r15
0x18005b06d  cmp     [r14+48h], r15
0x18005b071  jz      short loc_18005B09B
0x18005b073  lea     rcx, [rbp+80h+var_A0]
0x18005b077  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18005b07c  mov     rbx, [r14+48h]
0x18005b080  mov     [rbp+80h+var_A0], rbx
0x18005b084  test    rbx, rbx
0x18005b087  jz      short loc_18005B09B
0x18005b089  mov     rax, [rbx]
0x18005b08c  mov     rcx, rbx
0x18005b08f  mov     rax, [rax+8]
0x18005b093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b098  mov     rsi, rbx
0x18005b09b  mov     rax, [rbp+80h+var_100]
0x18005b09f  lea     r15, [r14+80h]
0x18005b0a6  cmp     [r15], rax
0x18005b0a9  jz      short loc_18005B0C4
0x18005b0ab  lea     rcx, [rbp+80h+var_100]
0x18005b0af  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18005b0b4  mov     rax, [r15]
0x18005b0b7  lea     rcx, [rbp+80h+var_100]
0x18005b0bb  mov     [rbp+80h+var_100], rax
0x18005b0bf  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18005b0c4  lea     rcx, [rbp+80h+var_88]; this
0x18005b0c8  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18005b0cd  cmp     [rbp+80h+var_100], 0
0x18005b0d2  jz      loc_18005B15B
0x18005b0d8  lea     rcx, [rbp+80h+var_80]
0x18005b0dc  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18005b0e1  mov     rcx, [rsp+180h+ppv]
0x18005b0e6  xor     ebx, ebx
0x18005b0e8  test    rcx, rcx
0x18005b0eb  jz      short loc_18005B0FE
0x18005b0ed  mov     [rsp+180h+ppv], rbx
0x18005b0f2  mov     rax, [rcx]
0x18005b0f5  mov     rax, [rax+10h]
0x18005b0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b0fe  lea     rcx, [rbp+80h+var_C0]
0x18005b102  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18005b107  lea     rcx, [rbp+80h+var_C8]
0x18005b10b  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18005b110  lea     rcx, [rbp+80h+var_B8]
0x18005b114  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18005b119  lea     rcx, [rbp+80h+var_B0]
0x18005b11d  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18005b122  mov     rcx, [rbp+80h+var_F8]
0x18005b126  test    rcx, rcx
0x18005b129  jz      short loc_18005B13B
0x18005b12b  mov     [rbp+80h+var_F8], rbx
0x18005b12f  mov     rax, [rcx]
0x18005b132  mov     rax, [rax+10h]
0x18005b136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b13b  mov     rcx, [rbp+80h+var_D8]
0x18005b13f  test    rcx, rcx
0x18005b142  jz      short loc_18005B154
0x18005b144  mov     [rbp+80h+var_D8], rbx
0x18005b148  mov     rax, [rcx]
0x18005b14b  mov     rax, [rax+10h]
0x18005b14f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b154  mov     esi, ebx
0x18005b156  jmp     loc_18005BD68
0x18005b15b  test    rsi, rsi
0x18005b15e  jnz     loc_18005B1F9
0x18005b164  mov     eax, cs:dword_1801B76C8
0x18005b16a  mov     ecx, 8000FFFFh
0x18005b16f  mov     esi, ecx
0x18005b171  cmp     eax, 2
0x18005b174  jbe     loc_18005BC45
0x18005b17a  lea     rax, aCalledInBadSta; "Called in bad state"
0x18005b181  mov     [rsp+180h+var_12C], 2D4h
0x18005b189  mov     [rsp+180h+var_120], rax
0x18005b18e  lea     rdi, aOncapsadvertis; "OnCapsAdvertise"
0x18005b195  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18005b19c  mov     [rsp+180h+var_118], rdi
0x18005b1a1  mov     [rsp+180h+var_110], rax
0x18005b1a6  lea     rdx, word_18019AC06
0x18005b1ad  lea     rax, aErrorCondition; "Error condition failed"
0x18005b1b4  mov     [rsp+180h+var_130], ecx
0x18005b1b8  mov     [rsp+180h+var_128], rax
0x18005b1bd  lea     rax, [rsp+180h+var_120]
0x18005b1c2  mov     [rsp+180h+var_138], rax
0x18005b1c7  lea     rax, [rsp+180h+var_118]
0x18005b1cc  mov     [rsp+180h+var_140], rax
0x18005b1d1  lea     rax, [rsp+180h+var_12C]
0x18005b1d6  mov     [rsp+180h+var_148], rax
0x18005b1db  lea     rax, [rsp+180h+var_110]
0x18005b1e0  mov     [rsp+180h+var_150], rax
0x18005b1e5  lea     rax, [rsp+180h+var_130]
0x18005b1ea  mov     [rsp+180h+var_158], rax
0x18005b1ef  lea     rax, [rsp+180h+var_128]
0x18005b1f4  jmp     loc_18005BC3B
0x18005b1f9  lea     r13, [r14-8]
0x18005b1fd  mov     rcx, r13; this
0x18005b200  call    ?LoadRdpLite@CRdpPipeGfxPlugin@@AEAAJXZ; CRdpPipeGfxPlugin::LoadRdpLite(void)
0x18005b205  mov     esi, eax
0x18005b207  test    eax, eax
0x18005b209  jns     short loc_18005B23C
0x18005b20b  mov     ecx, cs:dword_1801B76C8
0x18005b211  cmp     ecx, 2
0x18005b214  jbe     loc_18005BC45
0x18005b21a  lea     rax, aFailedToLoadRd; "Failed to load Rdplite.dll"
0x18005b221  mov     [rsp+180h+var_130], 2DAh
0x18005b229  lea     rdi, aOncapsadvertis; "OnCapsAdvertise"
0x18005b230  lea     rdx, word_18019ABB6
0x18005b237  jmp     loc_18005BBDE
0x18005b23c  mov     rcx, [r14+88h]; hModule
0x18005b243  lea     rdx, aRdpliteClassfa; "RdpLite_ClassFactory"
0x18005b24a  call    cs:__imp_GetProcAddress
0x18005b250  mov     r12, rax
0x18005b253  test    rax, rax
0x18005b256  jnz     loc_18005B311
0x18005b25c  call    cs:__imp_GetLastError
0x18005b262  mov     esi, eax
0x18005b264  test    eax, eax
0x18005b266  jle     short loc_18005B271
0x18005b268  movzx   esi, ax
0x18005b26b  or      esi, 80070000h
0x18005b271  mov     eax, cs:dword_1801B76C8
0x18005b277  cmp     eax, 2
0x18005b27a  jbe     loc_18005B304
0x18005b280  lea     rax, aFailedToLoadAd; "Failed to load address of ClassFactory"
0x18005b287  mov     [rsp+180h+var_130], 2E5h
0x18005b28f  mov     [rsp+180h+var_128], rax
0x18005b294  lea     rdi, aOncapsadvertis; "OnCapsAdvertise"
0x18005b29b  lea     rax, aClientcoreTerm_7; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18005b2a2  mov     [rsp+180h+var_110], rdi
0x18005b2a7  mov     [rsp+180h+var_118], rax
0x18005b2ac  lea     rdx, word_18019AB66
0x18005b2b3  lea     rax, aErrorCondition; "Error condition failed"
0x18005b2ba  mov     [rsp+180h+var_12C], esi
0x18005b2be  mov     [rsp+180h+var_120], rax
0x18005b2c3  lea     rax, [rsp+180h+var_128]
0x18005b2c8  mov     [rsp+180h+var_138], rax
0x18005b2cd  lea     rax, [rsp+180h+var_110]
0x18005b2d2  mov     [rsp+180h+var_140], rax
0x18005b2d7  lea     rax, [rsp+180h+var_130]
0x18005b2dc  mov     [rsp+180h+var_148], rax
0x18005b2e1  lea     rax, [rsp+180h+var_118]
0x18005b2e6  mov     [rsp+180h+var_150], rax
0x18005b2eb  lea     rax, [rsp+180h+var_12C]
0x18005b2f0  mov     [rsp+180h+var_158], rax
0x18005b2f5  lea     rax, [rsp+180h+var_120]
0x18005b2fa  mov     [rsp+180h+var_160], rax
0x18005b2ff  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18005b304  test    esi, esi
0x18005b306  jns     loc_18005BC95
0x18005b30c  jmp     loc_18005BC45
0x18005b311  lea     rdx, [rsp+180h+ppv]; ppv
0x18005b316  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18005b31d  call    cs:__imp_PSCreateMemoryPropertyStore
0x18005b323  mov     esi, eax
0x18005b325  test    eax, eax
0x18005b327  jns     short loc_18005B35A
0x18005b329  mov     eax, cs:dword_1801B76C8
0x18005b32f  cmp     eax, 2
0x18005b332  jbe     loc_18005BC45
0x18005b338  lea     rax, aFailedToCreate_75; "Failed to create property store"
0x18005b33f  mov     [rsp+180h+var_130], 2EEh
0x18005b347  lea     rdi, aOncapsadvertis; "OnCapsAdvertise"
0x18005b34e  lea     rdx, word_18019AB16
0x18005b355  jmp     loc_18005BBDE
0x18005b35a  mov     rcx, [rsp+180h+ppv]
0x18005b35f  lea     r8, [rbp+80h+pvar]
0x18005b363  mov     eax, 48h ; 'H'
0x18005b368  lea     rdx, PKEY_Activity_Id
0x18005b36f  mov     word ptr [rbp+80h+pvar], ax
0x18005b373  lea     rax, [r14+0C4h]
0x18005b37a  mov     [rbp+80h+pvar+8], rax
0x18005b37e  mov     rax, [rcx]
0x18005b381  mov     rax, [rax+30h]
0x18005b385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b38a  mov     esi, eax
0x18005b38c  test    eax, eax
0x18005b38e  jns     short loc_18005B3C1
0x18005b390  mov     eax, cs:dword_1801B76C8
0x18005b396  cmp     eax, 2
0x18005b399  jbe     loc_18005BC45
0x18005b39f  lea     rax, aFailedToSetPke_11; "Failed to set PKEY_Activity_Id property"
0x18005b3a6  mov     [rsp+180h+var_130], 2FAh
0x18005b3ae  lea     rdi, aOncapsadvertis; "OnCapsAdvertise"
0x18005b3b5  lea     rdx, word_18019AAC6
0x18005b3bc  jmp     loc_18005BBDE
0x18005b3c1  test    rdi, rdi
0x18005b3c4  jz      short loc_18005B410
0x18005b3c6  mov     eax, 13h
0x18005b3cb  mov     dword ptr [rbp+80h+pvar+8], 0
0x18005b3d2  mov     word ptr [rbp+80h+pvar], ax
0x18005b3d6  lea     r8, [rbp+80h+pvar+8]
0x18005b3da  mov     rax, [rdi]
0x18005b3dd  lea     rdx, aGfxpipelineIma; "GfxPipeline::ImageQualityPolicy"
0x18005b3e4  mov     rcx, rdi
0x18005b3e7  mov     rax, [rax+28h]
0x18005b3eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b3f0  test    eax, eax
0x18005b3f2  js      short loc_18005B410
0x18005b3f4  mov     rcx, [rsp+180h+ppv]
0x18005b3f9  lea     r8, [rbp+80h+pvar]
0x18005b3fd  lea     rdx, PKEY_GrfxPipelineImageQuality
0x18005b404  mov     rax, [rcx]
0x18005b407  mov     rax, [rax+30h]
0x18005b40b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b410  mov     rcx, [r14+60h]
0x18005b414  lea     r8, [rbp+80h+var_D0]
0x18005b418  mov     [rbp+80h+var_D0], 0
0x18005b41f  lea     rdx, aEnabledirectst; "EnableDirectStreamMediaApiServer"
0x18005b426  mov     rax, [rcx]
0x18005b429  mov     rax, [rax+20h]
0x18005b42d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b432  lea     rdi, aOncapsadvertis; "OnCapsAdvertise"
0x18005b439  test    eax, eax
0x18005b43b  jns     loc_18005B520
0x18005b441  mov     ecx, cs:dword_1801B76C8
0x18005b447  cmp     ecx, 3
0x18005b44a  jbe     short loc_18005B4A1
0x18005b44c  mov     [rsp+180h+var_130], eax
0x18005b450  lea     rdx, byte_18019AA87
0x18005b457  lea     rax, aFailedToGetCon_2; "Failed to get CONN_PROPERTY_ENABLE_DIRE"...
0x18005b45e  mov     [rsp+180h+var_128], rdi
0x18005b463  mov     [rsp+180h+var_110], rax
0x18005b468  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18005b46f  mov     [rsp+180h+var_118], rax
0x18005b474  lea     rax, [rsp+180h+var_128]
0x18005b479  mov     [rsp+180h+var_148], rax
0x18005b47e  lea     rax, [rsp+180h+var_130]
0x18005b483  mov     [rsp+180h+var_150], rax
0x18005b488  lea     rax, [rsp+180h+var_110]
0x18005b48d  mov     [rsp+180h+var_158], rax
0x18005b492  lea     rax, [rsp+180h+var_118]
0x18005b497  mov     [rsp+180h+var_160], rax
0x18005b49c  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18005b4a1  mov     rcx, [r14+60h]
0x18005b4a5  lea     r8, [rbp+80h+pvarg]
0x18005b4a9  lea     rdx, aDirectstreamme_0; "DirectStreamMediaControl"
0x18005b4b0  mov     rax, [rcx]
0x18005b4b3  mov     rax, [rax+18h]
0x18005b4b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b4bc  mov     ecx, 0Dh
0x18005b4c1  test    eax, eax
0x18005b4c3  js      loc_18005B63E
0x18005b4c9  cmp     word ptr [rbp+80h+pvarg], cx
0x18005b4cd  jz      loc_18005B581
0x18005b4d3  mov     eax, cs:dword_1801B76C8
  ... truncated ...
```
