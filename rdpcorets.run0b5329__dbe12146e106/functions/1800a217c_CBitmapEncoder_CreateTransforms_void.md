# CBitmapEncoder::CreateTransforms(void)

- ea: `0x1800a217c`
- end: `0x1800a3487`
- name: `?CreateTransforms@CBitmapEncoder@@AEAAJXZ`
- size: `4875`
- prototype: `__int64 __fastcall(CBitmapEncoder *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a4a20`

## callees

- `0x1800071c0`
- `0x1800071f0`
- `0x1800091a8`
- `0x18001ac58`
- `0x18001bc38`
- `0x18002e600`
- `0x180059838`
- `0x1800598d0`
- `0x1800a217c`
- `0x1800a3490`
- `0x1800a3570`
- `0x1800a4ffc`
- `0x1800a5190`
- `0x1800a5390`
- `0x18013e7d0`
- `0x18013eab8`
- `0x18013ead8`
- `0x18013eb00`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a23dd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a249b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a25d4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a263c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a23dd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a249b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a25d4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a263c`

## string_xrefs

- `0x1800a22e3`: `Software\Policies\Microsoft\Windows NT\Terminal Services\H264Encoding`
- `0x1800a32e0`: `Software\Policies\Microsoft\Windows NT\Terminal Services\H264Encoding`
- `0x1800a2251`: `CTSMfWrapper::CreateInstance() failed`
- `0x1800a2298`: `Cannot create transforms.  MF is not installed.`
- `0x1800a24d6`: `CoCreateInstance( CLSID_VideoProcessorMFT ) failed`
- `0x1800a240c`: `CoCreateInstance( CLSID_CResizerDMO ) failed`
- `0x1800a2613`: `CoCreateInstance( CLSID_H264MFTEncoder ) failed`
- `0x1800a267b`: `CoCreateInstance( CLSID_CColorConvertDMO ) failed`
- `0x1800a2721`: `m_spMFWrapper->TS_MFCreateMediaType( RGB - Scaled ) failed`
- `0x1800a26c9`: `m_spMFWrapper->TS_MFCreateMediaType( RGB ) failed`
- `0x1800a27bd`: `m_spMFWrapper->TS_MFCreateMediaType( 264 ) failed`
- `0x1800a276f`: `m_spMFWrapper->TS_MFCreateMediaType( YUV ) failed`
- `0x1800a308e`: `m_spMFWrapper->TS_MFCreateSample() failed`
- `0x1800a30f2`: `m_spMFWrapper->TS_MFCreateMemoryBuffer() failed`

## pseudocode

```c
__int64 __fastcall CBitmapEncoder::CreateTransforms(CBitmapEncoder *this, __int64 a2, unsigned __int16 a3)
{
  struct CTSMfWrapper **v4; // r12
  BOOL v5; // ebx
  struct ITSPlatform *v6; // rcx
  HKEY v7; // rcx
  int Instance; // esi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v10; // edx
  const char *v11; // rcx
  unsigned int v12; // eax
  int v13; // esi
  PVOID *v14; // rax
  unsigned int v15; // eax
  __int64 v16; // rdx
  unsigned int v17; // eax
  HRESULT v18; // r13d
  unsigned int v19; // eax
  int v20; // edx
  const char *v21; // rcx
  unsigned int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  unsigned int v25; // eax
  int v26; // edx
  const char *v27; // rcx
  unsigned int v28; // eax
  int v29; // edx
  const char *v30; // rcx
  __int64 v31; // rcx
  unsigned int v32; // eax
  __int64 v33; // rcx
  CBitmapEncoder *v34; // rcx
  unsigned int v35; // r8d
  CBitmapEncoder *v36; // rcx
  int v37; // esi
  int v38; // r8d
  unsigned int v39; // eax
  int v40; // esi
  unsigned int v41; // eax
  HKEY v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // r8
  int v45; // r15d
  unsigned int v46; // eax
  CBitmapEncoder *v47; // rcx
  unsigned int v48; // eax
  int v49; // esi
  unsigned int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // rdx
  __int64 v54; // r8
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // rdx
  __int64 v66; // r8
  __int64 v68; // [rsp+28h] [rbp-51h]
  LPVOID v69; // [rsp+50h] [rbp-29h] BYREF
  struct IMFMediaType *v70; // [rsp+58h] [rbp-21h] BYREF
  struct IMFMediaType *v71; // [rsp+60h] [rbp-19h] BYREF
  struct IMFMediaType *v72; // [rsp+68h] [rbp-11h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-9h] BYREF
  struct IMFMediaBuffer *v74; // [rsp+78h] [rbp-1h] BYREF
  struct IMFMediaBuffer *v75[10]; // [rsp+80h] [rbp+7h] BYREF
  __int64 v76; // [rsp+E0h] [rbp+67h] BYREF
  unsigned int v77; // [rsp+E8h] [rbp+6Fh] BYREF
  struct IMFMediaType *v78; // [rsp+F0h] [rbp+77h] BYREF
  struct IMFTransform *v79; // [rsp+F8h] [rbp+7Fh] BYREF

  v77 = 0;
  ppv = 0;
  v69 = 0;
  v79 = 0;
  v72 = 0;
  v71 = 0;
  v70 = 0;
  v78 = 0;
  v75[0] = 0;
  v74 = 0;
  v4 = (struct CTSMfWrapper **)((char *)this + 128);
  v5 = IsWindowsVersionOrGreater(0xAu, 0, a3);
  LODWORD(v76) = 0;
  Instance = CTSMfWrapper::CreateInstance(v6, v4);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 57;
      v11 = "CTSMfWrapper::CreateInstance() failed";
LABEL_212:
      LODWORD(v68) = Instance;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        (unsigned int)WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v11,
        v68);
      goto LABEL_213;
    }
    goto LABEL_213;
  }
  if ( !*((_DWORD *)*v4 + 18) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        (unsigned int)WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids,
        v12,
        (__int64)"Cannot create transforms.  MF is not installed.",
        -2147467259);
    }
    Instance = -2147467259;
    goto LABEL_213;
  }
  v13 = v5;
  if ( TSMM_VIDEO_RegReadDWORD(
         v7,
         L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\H264Encoding",
         L"VOBRColorConvertApi",
         0,
         (unsigned int *)&v76) < 0 )
    goto LABEL_24;
  if ( (_DWORD)v76 == 2 )
  {
    v13 = 0;
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 59;
LABEL_23:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids, v15);
      goto LABEL_24;
    }
  }
  else
  {
    if ( (_DWORD)v76 != 1 )
    {
LABEL_24:
      v14 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_25;
    }
    v13 = 1;
    v14 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 60;
      goto LABEL_23;
    }
  }
LABEL_25:
  if ( *((_DWORD *)this + 47) )
  {
    if ( v14 != &WPP_GLOBAL_Control && (*((_DWORD *)v14 + 7) & 0x100) != 0 && *((_BYTE *)v14 + 25) >= 4u )
    {
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids, v17);
    }
    v18 = CoCreateInstance(&CLSID_CResizerDMO, 0, 1u, &GUID_bf94c121_5b05_4e6f_8000_ba598961414d, &ppv);
    if ( v18 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_36;
      }
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 62;
      v21 = "CoCreateInstance( CLSID_CResizerDMO ) failed";
      goto LABEL_35;
    }
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 )
  {
    if ( v14 != &WPP_GLOBAL_Control && (*((_DWORD *)v14 + 7) & 0x100) != 0 && *((_BYTE *)v14 + 25) >= 4u )
    {
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids, v22);
    }
    v18 = CoCreateInstance(&CLSID_VideoProcessorMFT, 0, 1u, &GUID_bf94c121_5b05_4e6f_8000_ba598961414d, &v69);
    if ( v18 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_36;
      }
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 64;
      v21 = "CoCreateInstance( CLSID_VideoProcessorMFT ) failed";
      goto LABEL_35;
    }
    v76 = 0;
    v18 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v69 + 64LL))(v69, &v76);
    if ( v18 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_54;
      }
      v25 = RdpWppGetCurrentThreadActivityIdPrefix();
      v26 = 65;
      v27 = "GetAttributes failed";
LABEL_53:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v26,
        (unsigned int)WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids,
        v25,
        (__int64)v27,
        v18);
LABEL_54:
      TCntPtr<IRdpSQMLogger>::SafeRelease(&v76, v23, v24);
      goto LABEL_36;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, const IID *, __int64))(*(_QWORD *)v76 + 168LL))(
            v76,
            &MF_XVP_DISABLE_FRC,
            1);
    if ( v18 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_54;
      }
      v25 = RdpWppGetCurrentThreadActivityIdPrefix();
      v26 = 66;
      v27 = "Set MF_XVP_DISABLE_FRC failed";
      goto LABEL_53;
    }
    TCntPtr<IRdpSQMLogger>::SafeRelease(&v76, v23, v24);
  }
  else
  {
    v18 = CoCreateInstance(&CLSID_CColorConvertDMO, 0, 1u, &GUID_bf94c121_5b05_4e6f_8000_ba598961414d, &v69);
    if ( v18 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_36;
      }
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 67;
      v21 = "CoCreateInstance( CLSID_CColorConvertDMO ) failed";
LABEL_35:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
        (unsigned int)WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids,
        v19,
        (__int64)v21,
        v18);
LABEL_36:
      Instance = v18;
      goto LABEL_213;
    }
  }
  v18 = CoCreateInstance(&CLSID_H264MFTEncoder, 0, 1u, &GUID_bf94c121_5b05_4e6f_8000_ba598961414d, (LPVOID *)&v79);
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_36;
    }
    v19 = RdpWppGetCurrentThreadActivityIdPrefix();
    v20 = 68;
    v21 = "CoCreateInstance( CLSID_H264MFTEncoder ) failed";
    goto LABEL_35;
  }
  v18 = CTSMfWrapper::TS_MFCreateMediaType(*v4, &v72);
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_36;
    }
    v19 = RdpWppGetCurrentThreadActivityIdPrefix();
    v20 = 69;
    v21 = "m_spMFWrapper->TS_MFCreateMediaType( RGB ) failed";
    goto LABEL_35;
  }
  if ( *((_DWORD *)this + 47) )
  {
    v18 = CTSMfWrapper::TS_MFCreateMediaType(*v4, &v71);
    if ( v18 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_36;
      }
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 70;
      v21 = "m_spMFWrapper->TS_MFCreateMediaType( RGB - Scaled ) failed";
      goto LABEL_35;
    }
  }
  v18 = CTSMfWrapper::TS_MFCreateMediaType(*v4, &v70);
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_36;
    }
    v19 = RdpWppGetCurrentThreadActivityIdPrefix();
    v20 = 71;
    v21 = "m_spMFWrapper->TS_MFCreateMediaType( YUV ) failed";
    goto LABEL_35;
  }
  v18 = CTSMfWrapper::TS_MFCreateMediaType(*v4, &v78);
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_36;
    }
    v19 = RdpWppGetCurrentThreadActivityIdPrefix();
    v20 = 72;
    v21 = "m_spMFWrapper->TS_MFCreateMediaType( 264 ) failed";
    goto LABEL_35;
  }
  ((void (__fastcall *)(struct IMFMediaType *, const GUID *, const GUID *))v72->lpVtbl->SetGUID)(
    v72,
    &MF_MT_MAJOR_TYPE,
    &MFMediaType_Video);
  ((void (__fastcall *)(struct IMFMediaType *, const GUID *, const GUID *))v72->lpVtbl->SetGUID)(
    v72,
    &MF_MT_SUBTYPE,
    &MFVideoFormat_RGB32);
  if ( v13 )
    ((void (__fastcall *)(struct IMFMediaType *, const GUID *, __int64))v72->lpVtbl->SetUINT32)(
      v72,
      &MF_MT_DEFAULT_STRIDE,
      1);
  ((void (__fastcall *)(struct IMFMediaType *, const GUID *, unsigned __int64))v72->lpVtbl->SetUINT64)(
    v72,
    &MF_MT_FRAME_SIZE,
    *((unsigned int *)this + 41) | ((unsigned __int64)*((unsigned int *)this + 40) << 32));
  if ( *((_DWORD *)this + 47) )
  {
    v76 = 0;
    ((void (__fastcall *)(struct IMFMediaType *, const GUID *, const GUID *))v71->lpVtbl->SetGUID)(
      v71,
      &MF_MT_MAJOR_TYPE,
      &MFMediaType_Video);
    ((void (__fastcall *)(struct IMFMediaType *, const GUID *, const GUID *))v71->lpVtbl->SetGUID)(
      v71,
      &MF_MT_SUBTYPE,
      &MFVideoFormat_RGB32);
    if ( v13 )
      ((void (__fastcall *)(struct IMFMediaType *, const GUID *, __int64))v71->lpVtbl->SetUINT32)(
        v71,
        &MF_MT_DEFAULT_STRIDE,
        1);
    ((void (__fastcall *)(struct IMFMediaType *, const GUID *, unsigned __int64))v71->lpVtbl->SetUINT64)(
      v71,
      &MF_MT_FRAME_SIZE,
      *((unsigned int *)this + 43) | ((unsigned __int64)*((unsigned int *)this + 42) << 32));
    Instance = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IWMResizerProps, &v76);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v28 = RdpWppGetCurrentThreadActivityIdPrefix();
        v29 = 73;
        v30 = "pResizer->QueryInterface( IID_IWMResizerProps ) failed";
LABEL_102:
        LODWORD(v68) = Instance;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v29,
          (unsigned int)WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids,
          v28,
          (__int64)v30,
          v68);
        goto LABEL_103;
      }
      goto LABEL_103;
    }
    Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD))(*(_QWORD *)v76 + 48LL))(
                 v76,
                 0,
                 0,
                 *((unsigned int *)this + 40),
                 *((_DWORD *)this + 41),
                 0,
                 0,
                 *((_DWORD *)this + 42),
                 *((_DWORD *)this + 43));
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v28 = RdpWppGetCurrentThreadActivityIdPrefix();
        v29 = 74;
        v30 = "spResizerProps->SetFullCropRegion() failed";
        goto LABEL_102;
      }
LABEL_103:
      v31 = v76;
      if ( v76 )
      {
        v76 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      }
      goto LABEL_213;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v32 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        (unsigned int)WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids,
        v32,
        (__int64)"Fast-Quality");
    }
    Instance = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v76 + 24LL))(v76, 0);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v28 = RdpWppGetCurrentThreadActivityIdPrefix();
        v29 = 76;
        v30 = "spResizerProps->SetResizerQuality() failed";
        goto LABEL_102;
      }
      goto LABEL_103;
    }
    v33 = v76;
    if ( v76 )
    {
      v76 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
  }
  Instance = CBitmapEncoder::SetMaxBitrate(this, v79, *((_DWORD *)this + 46), 0, &v77);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 77;
      v11 = "SetMaxBitrate() failed";
      goto LABEL_212;
    }
LABEL_213:
    v45 = CBitmapEncoder::DestroyTransforms(this);
    if ( v45 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v46 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v68) = v45;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        96,
        (unsigned int)WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids,
        v46,
        (__int64)"DestroyTransforms() failed",
        v68);
    }
    goto LABEL_238;
  }
  ((void (__fastcall *)(struct IMFMediaType *, const GUID *, const GUID *))v70->lpVtbl->SetGUID)(
    v70,
    &MF_MT_MAJOR_TYPE,
    &MFMediaType_Video);
  ((void (__fastcall *)(struct IMFMediaType *, const GUID *, const GUID *))v70->lpVtbl->SetGUID)(
    v70,
    &MF_MT_SUBTYPE,
    &MFVideoFormat_IYUV);
  ((void (__fastcall *)(struct IMFMediaType *, const GUID *, unsigned __int64))v70->lpVtbl->SetUINT64)(
    v70,
    &MF_MT_FRAME_SIZE,
    *((unsigned int *)this + 43) | ((unsigned __int64)*((unsigned int *)this + 42) << 32));
  ((void (__fastcall *)(struct IMFMediaType *, const GUID *, unsigned __int64))v70->lpVtbl->SetUINT64)(
    v70,
    &MF_MT_FRAME_RATE,
    ((unsigned __int64)*((unsigned int *)this + 45) << 32) | 1);
  ((void (__fastcall *)(struct IMFMediaType *, const GUID *, const GUID *))v78->lpVtbl->SetGUID)(
    v78,
    &MF_MT_MAJOR_TYPE,
    &MFMediaType_Video);
  ((void (__fastcall *)(struct IMFMediaType *, const GUID *, const GUID *))v78->lpVtbl->SetGUID)(
    v78,
    &MF_MT_SUBTYPE,
    &MFVideoFormat_H264);
  ((void (__fastcall *)(struct IMFMediaType *, const GUID *, _QWORD))v78->lpVtbl->SetUINT32)(
    v78,
    &MF_MT_AVG_BITRATE,
    v77);
  ((void (__fastcall *)(struct IMFMediaType *, const GUID *, __int64))v78->lpVtbl->SetUINT32)(
    v78,
    &MF_MT_INTERLACE_MODE,
    2);
  ((void (__fastcall *)(struct IMFMediaType *, const GUID *, __int64))v78->lpVtbl->SetUINT32)(
    v78,
    &MF_MT_MPEG2_PROFILE,
    66);
  ((void (__fastcall *)(struct IMFMediaType *, const GUID *, unsigned __int64))v78->lpVtbl->SetUINT64)(
    v78,
    &MF_MT_FRAME_RATE,
    ((unsigned __int64)*((unsigned int *)this + 45) << 32) | 1);
  ((void (__fastcall *)(struct IMFMediaType *, const GUID *, unsigned __int64))v78->lpVtbl->SetUINT64)(
    v78,
    &MF_MT_FRAME_SIZE,
    *((unsigned int *)this + 43) | ((unsigned __int64)*((unsigned int *)this + 42) << 32));
  if ( *((_DWORD *)this + 47) )
  {
    Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IMFMediaType *, _QWORD))(*(_QWORD *)ppv + 128LL))(
                 ppv,
                 0,
                 v71,
                 0);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 78;
        v11 = "spResizer->SetOutputType( Scaled RGB ) failed";
        goto LABEL_212;
      }
      goto LABEL_213;
    }
    Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IMFMediaType *, _QWORD))(*(_QWORD *)ppv + 120LL))(
                 ppv,
                 0,
                 v72,
                 0);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 79;
        v11 = "spResizer->SetInputType( RGB ) failed";
        goto LABEL_212;
      }
      goto LABEL_213;
    }
    Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IMFMediaType *, _QWORD))(*(_QWORD *)v69 + 128LL))(
                 v69,
                 0,
                 v70,
                 0);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_213;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 80;
      goto LABEL_142;
    }
    Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IMFMediaType *, _QWORD))(*(_QWORD *)v69 + 120LL))(
                 v69,
                 0,
                 v71,
                 0);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_213;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 81;
      goto LABEL_148;
    }
  }
  else
  {
    Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IMFMediaType *, _QWORD))(*(_QWORD *)v69 + 128LL))(
                 v69,
                 0,
                 v70,
                 0);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_213;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 82;
LABEL_142:
      v11 = "spConverter->SetOutputType( YUV ) failed";
      goto LABEL_212;
    }
    Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IMFMediaType *, _QWORD))(*(_QWORD *)v69 + 120LL))(
                 v69,
                 0,
                 v72,
                 0);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_213;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 83;
LABEL_148:
      v11 = "spConverter->SetInputType( RGB ) failed";
      goto LABEL_212;
    }
  }
  v37 = CBitmapEncoder::SetKeyframeInterval(v34, v79, v35);
  if ( v37 < 0 )
  {
    v36 = (CBitmapEncoder *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v39 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v68) = v37;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        84,
        (unsigned int)WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids,
        v39,
        (__int64)"SetKeyframeInterval() failed.  Non-Fatal.",
        v68);
    }
  }
  v40 = CBitmapEncoder::SetLowLatency(v36, v79, v38);
  if ( v40 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v41 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(v68) = v40;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      85,
      (unsigned int)WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids,
      v41,
      (__int64)"SetLowLatency() failed.  Non-Fatal.",
      v68);
  }
  Instance = ((__int64 (__fastcall *)(struct IMFTransform *, _QWORD, struct IMFMediaType *, _QWORD))v79->lpVtbl->SetOutputType)(
               v79,
               0,
               v78,
               0);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 86;
      v11 = "pEncoder->SetOutputType() failed";
      goto LABEL_212;
    }
    goto LABEL_213;
  }
  Instance = ((__int64 (__fastcall *)(struct IMFTransform *, _QWORD, struct IMFMediaType *, _QWORD))v79->lpVtbl->SetInputType)(
               v79,
               0,
               v70,
               0);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 87;
      v11 = "pEncoder->SetInputType() failed";
      goto LABEL_212;
    }
    goto LABEL_213;
  }
  if ( *((_DWORD *)this + 47) )
  {
    Instance = CTSMfWrapper::TS_MFCreateSample(*v4, (struct IMFSample **)this + 11);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_213;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 88;
      goto LABEL_185;
    }
    Instance = CTSMfWrapper::TS_MFCreateMemoryBuffer(
                 *v4,
                 *((_DWORD *)this + 42) * *((_DWORD *)this + 44) * *((_DWORD *)this + 43),
                 v75);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_213;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 89;
      goto LABEL_191;
    }
    Instance = (*(__int64 (__fastcall **)(_QWORD, struct IMFMediaBuffer *))(**((_QWORD **)this + 11) + 336LL))(
                 *((_QWORD *)this + 11),
                 v75[0]);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 90;
        v11 = "m_spRGBScaledSample->AddBuffer() failed";
        goto LABEL_212;
      }
      goto LABEL_213;
    }
  }
  Instance = CTSMfWrapper::TS_MFCreateSample(*v4, (struct IMFSample **)this + 12);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_213;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 91;
LABEL_185:
    v11 = "m_spMFWrapper->TS_MFCreateSample() failed";
    goto LABEL_212;
  }
  Instance = CTSMfWrapper::TS_MFCreateMemoryBuffer(
               *v4,
               *((_DWORD *)this + 44) * *((_DWORD *)this + 42) * *((_DWORD *)this + 43),
               &v74);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_213;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 92;
LABEL_191:
    v11 = "m_spMFWrapper->TS_MFCreateMemoryBuffer() failed";
    goto LABEL_212;
  }
  Instance = (*(__int64 (__fastcall **)(_QWORD, struct IMFMediaBuffer *))(**((_QWORD **)this + 12) + 336LL))(
               *((_QWORD *)this + 12),
               v74);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 93;
      v11 = "m_spConvertedSample->AddBuffer() failed";
      goto LABEL_212;
    }
    goto LABEL_213;
  }
  LODWORD(v76) = 0;
  if ( TSMM_VIDEO_RegReadDWORD(
         v42,
         L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\H264Encoding",
         L"DisableVOBRRC",
         0,
         (unsigned int *)&v76) >= 0
    && (_DWORD)v76 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v48 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids, v48);
    }
  }
  else
  {
    v49 = CBitmapEncoder::EnableVideoRateControl(v47, v79);
    if ( v49 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v50 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v68) = v49;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        95,
        (unsigned int)WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids,
        v50,
        (__int64)"EnableVideoRateControl() failed.  Non-Fatal.",
        v68);
    }
  }
  if ( ppv != *((LPVOID *)this + 8) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 64, v43, v44);
    *((_QWORD *)this + 8) = ppv;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 64);
  }
  if ( v69 != *((LPVOID *)this + 9) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 72, v43, v44);
    *((_QWORD *)this + 9) = v69;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 72);
  }
  if ( v79 != *((struct IMFTransform **)this + 10) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 80, v43, v44);
    *((_QWORD *)this + 10) = v79;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 80);
  }
  if ( v78 != *((struct IMFMediaType **)this + 14) )
  {
    TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 112, v43, v44);
    *((_QWORD *)this + 14) = v78;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 112);
  }
  Instance = 0;
LABEL_238:
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v74, v43, v44);
  TCntPtr<IRdpSQMLogger>::SafeRelease(v75, v51, v52);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v78, v53, v54);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v70, v55, v56);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v71, v57, v58);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v72, v59, v60);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v79, v61, v62);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v69, v63, v64);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&ppv, v65, v66);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800a217c  push    rbp
0x1800a217e  push    rbx
0x1800a217f  push    rsi
0x1800a2180  push    rdi
0x1800a2181  push    r12
0x1800a2183  push    r13
0x1800a2185  push    r14
0x1800a2187  push    r15
0x1800a2189  lea     rbp, [rsp-1Fh]
0x1800a218e  sub     rsp, 98h
0x1800a2195  xor     edx, edx; unsigned __int16
0x1800a2197  mov     [rbp+57h+arg_8], 0
0x1800a219e  mov     r15, rcx
0x1800a21a1  mov     [rbp+57h+var_60], 0
0x1800a21a9  mov     [rbp+57h+var_80], 0
0x1800a21b1  mov     [rbp+57h+arg_18], 0
0x1800a21b9  lea     ecx, [rdx+0Ah]; unsigned __int16
0x1800a21bc  mov     [rbp+57h+var_68], 0
0x1800a21c4  mov     [rbp+57h+var_70], 0
0x1800a21cc  mov     [rbp+57h+var_78], 0
0x1800a21d4  mov     [rbp+57h+arg_10], 0
0x1800a21dc  mov     [rbp+57h+var_50], 0
0x1800a21e4  mov     [rbp+57h+var_58], 0
0x1800a21ec  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x1800a21f1  lea     r12, [r15+80h]
0x1800a21f8  movzx   ebx, al
0x1800a21fb  mov     rdx, r12; struct CTSMfWrapper **
0x1800a21fe  mov     dword ptr [rbp+57h+arg_0], 0
0x1800a2205  call    ?CreateInstance@CTSMfWrapper@@SAJPEAVITSPlatform@@PEAPEAV1@@Z; CTSMfWrapper::CreateInstance(ITSPlatform *,CTSMfWrapper * *)
0x1800a220a  mov     esi, eax
0x1800a220c  test    eax, eax
0x1800a220e  jns     short loc_1800A225D
0x1800a2210  mov     rax, cs:WPP_GLOBAL_Control
0x1800a2217  lea     rbx, WPP_GLOBAL_Control
0x1800a221e  lea     rdi, WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids
0x1800a2225  mov     r14d, 2
0x1800a222b  cmp     rax, rbx
0x1800a222e  jz      loc_1800A3259
0x1800a2234  test    byte ptr [rax+1Ch], 8
0x1800a2238  jz      loc_1800A3259
0x1800a223e  cmp     [rax+19h], r14b
0x1800a2242  jb      loc_1800A3259
0x1800a2248  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a224d  lea     edx, [r14+37h]
0x1800a2251  lea     rcx, aCtsmfwrapperCr; "CTSMfWrapper::CreateInstance() failed"
0x1800a2258  jmp     loc_1800A323A
0x1800a225d  mov     rax, [r12]
0x1800a2261  cmp     dword ptr [rax+48h], 0
0x1800a2265  jnz     short loc_1800A22D0
0x1800a2267  mov     rax, cs:WPP_GLOBAL_Control
0x1800a226e  lea     rbx, WPP_GLOBAL_Control
0x1800a2275  lea     rdi, WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids
0x1800a227c  mov     r14d, 2
0x1800a2282  cmp     rax, rbx
0x1800a2285  jz      short loc_1800A22C6
0x1800a2287  test    byte ptr [rax+1Ch], 8
0x1800a228b  jz      short loc_1800A22C6
0x1800a228d  cmp     [rax+19h], r14b
0x1800a2291  jb      short loc_1800A22C6
0x1800a2293  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a2298  lea     rcx, aCannotCreateTr; "Cannot create transforms.  MF is not in"...
0x1800a229f  mov     dword ptr [rsp+0D0h+var_A8], 80004005h
0x1800a22a7  mov     [rsp+0D0h+ppv], rcx
0x1800a22ac  lea     edx, [r14+38h]
0x1800a22b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a22b7  mov     r9d, eax
0x1800a22ba  mov     r8, rdi
0x1800a22bd  mov     rcx, [rcx+10h]
0x1800a22c1  call    WPP_SF_DsD
0x1800a22c6  mov     esi, 80004005h
0x1800a22cb  jmp     loc_1800A3259
0x1800a22d0  lea     rax, [rbp+57h+arg_0]
0x1800a22d4  xor     r9d, r9d; unsigned int
0x1800a22d7  lea     r8, aVobrcolorconve; "VOBRColorConvertApi"
0x1800a22de  mov     [rsp+0D0h+ppv], rax; unsigned int *
0x1800a22e3  lea     rdx, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Windows "...
0x1800a22ea  mov     esi, ebx
0x1800a22ec  call    ?TSMM_VIDEO_RegReadDWORD@@YAJPEAUHKEY__@@PEBG1KPEAK@Z; TSMM_VIDEO_RegReadDWORD(HKEY__ *,ushort const *,ushort const *,ulong,ulong *)
0x1800a22f1  lea     rdi, WPP_d084f408a96c3b3368df51fe618a69e5_Traceguids
0x1800a22f8  mov     ecx, 200h
0x1800a22fd  lea     rbx, WPP_GLOBAL_Control
0x1800a2304  mov     r14d, 2
0x1800a230a  test    eax, eax
0x1800a230c  js      short loc_1800A2377
0x1800a230e  cmp     dword ptr [rbp+57h+arg_0], r14d
0x1800a2312  jnz     short loc_1800A2337
0x1800a2314  xor     esi, esi
0x1800a2316  mov     rax, cs:WPP_GLOBAL_Control
0x1800a231d  cmp     rax, rbx
0x1800a2320  jz      short loc_1800A237E
0x1800a2322  test    [rax+1Ch], ecx
0x1800a2325  jz      short loc_1800A237E
0x1800a2327  cmp     byte ptr [rax+19h], 3
0x1800a232b  jb      short loc_1800A237E
0x1800a232d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a2332  lea     edx, [rsi+3Bh]
0x1800a2335  jmp     short loc_1800A2361
0x1800a2337  cmp     dword ptr [rbp+57h+arg_0], 1
0x1800a233b  jnz     short loc_1800A2377
0x1800a233d  mov     esi, 1
0x1800a2342  mov     rax, cs:WPP_GLOBAL_Control
0x1800a2349  cmp     rax, rbx
0x1800a234c  jz      short loc_1800A237E
0x1800a234e  test    [rax+1Ch], ecx
0x1800a2351  jz      short loc_1800A237E
0x1800a2353  cmp     byte ptr [rax+19h], 3
0x1800a2357  jb      short loc_1800A237E
0x1800a2359  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a235e  lea     edx, [rsi+3Bh]
0x1800a2361  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2368  mov     r9d, eax
0x1800a236b  mov     r8, rdi
0x1800a236e  mov     rcx, [rcx+10h]
0x1800a2372  call    WPP_SF_d
0x1800a2377  mov     rax, cs:WPP_GLOBAL_Control
0x1800a237e  cmp     dword ptr [r15+0BCh], 0
0x1800a2386  jz      loc_1800A2442
0x1800a238c  cmp     rax, rbx
0x1800a238f  jz      short loc_1800A23C0
0x1800a2391  test    dword ptr [rax+1Ch], 100h
0x1800a2398  jz      short loc_1800A23C0
0x1800a239a  cmp     byte ptr [rax+19h], 4
0x1800a239e  jb      short loc_1800A23C0
0x1800a23a0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a23a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a23ac  mov     edx, 3Dh ; '='
0x1800a23b1  mov     r9d, eax
0x1800a23b4  mov     r8, rdi
0x1800a23b7  mov     rcx, [rcx+10h]
0x1800a23bb  call    WPP_SF_d
0x1800a23c0  xor     edx, edx; pUnkOuter
0x1800a23c2  lea     rax, [rbp+57h+var_60]
0x1800a23c6  lea     r9, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d; riid
0x1800a23cd  mov     [rsp+0D0h+ppv], rax; ppv
0x1800a23d2  lea     rcx, CLSID_CResizerDMO; rclsid
0x1800a23d9  lea     r8d, [rdx+1]; dwClsContext
0x1800a23dd  call    cs:__imp_CoCreateInstance
0x1800a23e3  mov     r13d, eax
0x1800a23e6  test    eax, eax
0x1800a23e8  jns     short loc_1800A243B
0x1800a23ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a23f1  cmp     rcx, rbx
0x1800a23f4  jz      short loc_1800A2433
0x1800a23f6  test    byte ptr [rcx+1Ch], 8
0x1800a23fa  jz      short loc_1800A2433
0x1800a23fc  cmp     [rcx+19h], r14b
0x1800a2400  jb      short loc_1800A2433
0x1800a2402  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a2407  mov     edx, 3Eh ; '>'
0x1800a240c  lea     rcx, aCocreateinstan_1; "CoCreateInstance( CLSID_CResizerDMO ) f"...
0x1800a2413  mov     dword ptr [rsp+0D0h+var_A8], r13d
0x1800a2418  mov     r9d, eax
0x1800a241b  mov     [rsp+0D0h+ppv], rcx
0x1800a2420  mov     r8, rdi
0x1800a2423  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a242a  mov     rcx, [rcx+10h]
0x1800a242e  call    WPP_SF_DsD
0x1800a2433  mov     esi, r13d
0x1800a2436  jmp     loc_1800A3259
0x1800a243b  mov     rax, cs:WPP_GLOBAL_Control
0x1800a2442  test    esi, esi
0x1800a2444  jz      loc_1800A261F
0x1800a244a  cmp     rax, rbx
0x1800a244d  jz      short loc_1800A247E
0x1800a244f  test    dword ptr [rax+1Ch], 100h
0x1800a2456  jz      short loc_1800A247E
0x1800a2458  cmp     byte ptr [rax+19h], 4
0x1800a245c  jb      short loc_1800A247E
0x1800a245e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a2463  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a246a  mov     edx, 3Fh ; '?'
0x1800a246f  mov     r9d, eax
0x1800a2472  mov     r8, rdi
0x1800a2475  mov     rcx, [rcx+10h]
0x1800a2479  call    WPP_SF_d
0x1800a247e  xor     edx, edx; pUnkOuter
0x1800a2480  lea     rax, [rbp+57h+var_80]
0x1800a2484  lea     r9, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d; riid
0x1800a248b  mov     [rsp+0D0h+ppv], rax; ppv
0x1800a2490  lea     rcx, CLSID_VideoProcessorMFT; rclsid
0x1800a2497  lea     r8d, [rdx+1]; dwClsContext
0x1800a249b  call    cs:__imp_CoCreateInstance
0x1800a24a1  mov     r13d, eax
0x1800a24a4  test    eax, eax
0x1800a24a6  jns     short loc_1800A24E2
0x1800a24a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a24af  cmp     rcx, rbx
0x1800a24b2  jz      loc_1800A2433
0x1800a24b8  test    byte ptr [rcx+1Ch], 8
0x1800a24bc  jz      loc_1800A2433
0x1800a24c2  cmp     [rcx+19h], r14b
0x1800a24c6  jb      loc_1800A2433
0x1800a24cc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a24d1  mov     edx, 40h ; '@'
0x1800a24d6  lea     rcx, aCocreateinstan_3; "CoCreateInstance( CLSID_VideoProcessorM"...
0x1800a24dd  jmp     loc_1800A2413
0x1800a24e2  mov     rcx, [rbp+57h+var_80]
0x1800a24e6  lea     rdx, [rbp+57h+arg_0]
0x1800a24ea  mov     [rbp+57h+arg_0], 0
0x1800a24f2  mov     rax, [rcx]
0x1800a24f5  mov     rax, [rax+40h]
0x1800a24f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a24fe  mov     r13d, eax
0x1800a2501  test    eax, eax
0x1800a2503  jns     short loc_1800A255C
0x1800a2505  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a250c  cmp     rcx, rbx
0x1800a250f  jz      short loc_1800A254E
0x1800a2511  test    byte ptr [rcx+1Ch], 8
0x1800a2515  jz      short loc_1800A254E
0x1800a2517  cmp     [rcx+19h], r14b
0x1800a251b  jb      short loc_1800A254E
0x1800a251d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a2522  mov     edx, 41h ; 'A'
0x1800a2527  lea     rcx, aGetattributesF; "GetAttributes failed"
0x1800a252e  mov     dword ptr [rsp+0D0h+var_A8], r13d
0x1800a2533  mov     r9d, eax
0x1800a2536  mov     [rsp+0D0h+ppv], rcx
0x1800a253b  mov     r8, rdi
0x1800a253e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2545  mov     rcx, [rcx+10h]
0x1800a2549  call    WPP_SF_DsD
0x1800a254e  lea     rcx, [rbp+57h+arg_0]
0x1800a2552  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800a2557  jmp     loc_1800A2433
0x1800a255c  mov     rcx, [rbp+57h+arg_0]
0x1800a2560  lea     rdx, MF_XVP_DISABLE_FRC
0x1800a2567  mov     r8d, 1
0x1800a256d  mov     rax, [rcx]
0x1800a2570  mov     rax, [rax+0A8h]
0x1800a2577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a257c  mov     r13d, eax
0x1800a257f  test    eax, eax
0x1800a2581  jns     short loc_1800A25AE
0x1800a2583  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a258a  cmp     rcx, rbx
0x1800a258d  jz      short loc_1800A254E
0x1800a258f  test    byte ptr [rcx+1Ch], 8
0x1800a2593  jz      short loc_1800A254E
0x1800a2595  cmp     [rcx+19h], r14b
0x1800a2599  jb      short loc_1800A254E
0x1800a259b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a25a0  mov     edx, 42h ; 'B'
0x1800a25a5  lea     rcx, aSetMfXvpDisabl; "Set MF_XVP_DISABLE_FRC failed"
0x1800a25ac  jmp     short loc_1800A252E
0x1800a25ae  lea     rcx, [rbp+57h+arg_0]
0x1800a25b2  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800a25b7  xor     edx, edx; pUnkOuter
0x1800a25b9  lea     rax, [rbp+57h+arg_18]
0x1800a25bd  lea     r9, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d; riid
0x1800a25c4  mov     [rsp+0D0h+ppv], rax; ppv
0x1800a25c9  lea     rcx, CLSID_H264MFTEncoder; rclsid
0x1800a25d0  lea     r8d, [rdx+1]; dwClsContext
0x1800a25d4  call    cs:__imp_CoCreateInstance
0x1800a25da  mov     r13d, eax
0x1800a25dd  test    eax, eax
0x1800a25df  jns     loc_1800A2687
0x1800a25e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a25ec  cmp     rcx, rbx
0x1800a25ef  jz      loc_1800A2433
0x1800a25f5  test    byte ptr [rcx+1Ch], 8
0x1800a25f9  jz      loc_1800A2433
0x1800a25ff  cmp     [rcx+19h], r14b
0x1800a2603  jb      loc_1800A2433
0x1800a2609  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a260e  mov     edx, 44h ; 'D'
0x1800a2613  lea     rcx, aCocreateinstan_0; "CoCreateInstance( CLSID_H264MFTEncoder "...
0x1800a261a  jmp     loc_1800A2413
0x1800a261f  xor     edx, edx; pUnkOuter
0x1800a2621  lea     rax, [rbp+57h+var_80]
0x1800a2625  lea     r9, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d; riid
0x1800a262c  mov     [rsp+0D0h+ppv], rax; ppv
0x1800a2631  lea     rcx, CLSID_CColorConvertDMO; rclsid
0x1800a2638  lea     r8d, [rdx+1]; dwClsContext
0x1800a263c  call    cs:__imp_CoCreateInstance
0x1800a2642  mov     r13d, eax
0x1800a2645  test    eax, eax
0x1800a2647  jns     loc_1800A25B7
0x1800a264d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a2654  cmp     rcx, rbx
0x1800a2657  jz      loc_1800A2433
0x1800a265d  test    byte ptr [rcx+1Ch], 8
0x1800a2661  jz      loc_1800A2433
0x1800a2667  cmp     [rcx+19h], r14b
0x1800a266b  jb      loc_1800A2433
0x1800a2671  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800a2676  mov     edx, 43h ; 'C'
0x1800a267b  lea     rcx, aCocreateinstan; "CoCreateInstance( CLSID_CColorConvertDM"...
0x1800a2682  jmp     loc_1800A2413
0x1800a2687  mov     rcx, [r12]; this
0x1800a268b  lea     rdx, [rbp+57h+var_68]; struct IMFMediaType **
0x1800a268f  call    ?TS_MFCreateMediaType@CTSMfWrapper@@QEAAJPEAPEAUIMFMediaType@@@Z; CTSMfWrapper::TS_MFCreateMediaType(IMFMediaType * *)
0x1800a2694  mov     r13d, eax
0x1800a2697  test    eax, eax
0x1800a2699  jns     short loc_1800A26D5
0x1800a269b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a26a2  cmp     rcx, rbx
0x1800a26a5  jz      loc_1800A2433
0x1800a26ab  test    byte ptr [rcx+1Ch], 8
0x1800a26af  jz      loc_1800A2433
  ... truncated ...
```
