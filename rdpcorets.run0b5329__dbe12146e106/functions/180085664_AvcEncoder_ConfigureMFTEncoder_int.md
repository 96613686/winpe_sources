# AvcEncoder::ConfigureMFTEncoder(int)

- ea: `0x180085664`
- end: `0x180086b6b`
- name: `?ConfigureMFTEncoder@AvcEncoder@@AEAAJH@Z`
- size: `5383`
- prototype: `__int64 __fastcall(AvcEncoder *__hidden this, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008a738`
- `0x18008a890`

## callees

- `0x1800015f0`
- `0x180002ea4`
- `0x1800071c0`
- `0x18001e49c`
- `0x18002e600`
- `0x180059838`
- `0x180059878`
- `0x1800598d0`
- `0x180085664`
- `0x1800891a4`
- `0x18014d010`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800856c2`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180085749`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180085ffb`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800861d9`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008638e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180086643`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180086a1e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180086a8f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180086b00`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800856c2`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180085749`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180085ffb`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800861d9`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18008638e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180086643`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180086a1e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180086a8f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180086b00`

## string_xrefs

- `0x1800857b6`: `ConfigureMFTEncoder`
- `0x18008583d`: `ConfigureMFTEncoder`
- `0x180085919`: `ConfigureMFTEncoder`
- `0x1800859eb`: `ConfigureMFTEncoder`
- `0x180085ab8`: `ConfigureMFTEncoder`
- `0x180085b91`: `ConfigureMFTEncoder`
- `0x180085c61`: `ConfigureMFTEncoder`
- `0x180085d2b`: `ConfigureMFTEncoder`
- `0x180085df5`: `ConfigureMFTEncoder`
- `0x180085ebf`: `ConfigureMFTEncoder`
- `0x180085f89`: `ConfigureMFTEncoder`
- `0x1800860ba`: `ConfigureMFTEncoder`
- `0x180086158`: `ConfigureMFTEncoder`
- `0x180086251`: `ConfigureMFTEncoder`
- `0x18008631c`: `ConfigureMFTEncoder`
- `0x180086422`: `ConfigureMFTEncoder`
- `0x180086503`: `ConfigureMFTEncoder`
- `0x1800865d1`: `ConfigureMFTEncoder`
- `0x1800866d0`: `ConfigureMFTEncoder`
- `0x18008681a`: `ConfigureMFTEncoder`
- `0x1800868b3`: `ConfigureMFTEncoder`
- `0x180086958`: `ConfigureMFTEncoder`
- `0x180085c48`: `spCodecApi->SetValue( CODECAPI_AVEncCommonRateControlMode ) failed`
- `0x180085d12`: `spCodecApi->SetValue(CODECAPI_AVEncCommonQualityVsSpeed) failed`
- `0x180085f70`: `spCodecApi->SetValue( CODECAPI_AVEncCommonQuality ) failed`
- `0x1800865b8`: `spCodecApi->SetValue(CODECAPI_AVEncNoInputCopy) failed`

## pseudocode

```c
__int64 __fastcall AvcEncoder::ConfigureMFTEncoder(AvcEncoder *this, __int64 a2, __int64 a3)
{
  __int64 (__fastcall ***v4)(_QWORD, GUID *, char *); // rcx
  int v5; // r12d
  int ActivityIdPrefix; // eax
  int v7; // ebx
  __int64 v8; // rcx
  int v9; // r9d
  unsigned int v10; // eax
  char *v11; // rdx
  const char **v12; // rax
  unsigned int v13; // eax
  int v14; // esi
  unsigned int EncoderSliceControlSize; // ebx
  unsigned int v16; // eax
  unsigned int v17; // eax
  bool v18; // cf
  __int64 v19; // rcx
  unsigned int v20; // eax
  _QWORD *v21; // rax
  __int64 v22; // rdi
  __int64 v23; // rsi
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rcx
  int v29; // eax
  __int64 v30; // rcx
  __int64 v32; // [rsp+28h] [rbp-61h]
  const char **v33; // [rsp+30h] [rbp-59h]
  const char **v34; // [rsp+40h] [rbp-49h]
  const char **v35; // [rsp+48h] [rbp-41h]
  const char *v36; // [rsp+50h] [rbp-39h] BYREF
  const char *v37; // [rsp+58h] [rbp-31h] BYREF
  const char *v38; // [rsp+60h] [rbp-29h] BYREF
  const char *v39; // [rsp+68h] [rbp-21h] BYREF
  __int128 v40; // [rsp+70h] [rbp-19h] BYREF
  __int64 v41; // [rsp+80h] [rbp-9h]
  __int64 v42; // [rsp+88h] [rbp-1h] BYREF
  __int128 v43; // [rsp+90h] [rbp+7h] BYREF
  __int64 v44; // [rsp+A0h] [rbp+17h]
  int v45; // [rsp+F0h] [rbp+67h] BYREF
  char *v46; // [rsp+100h] [rbp+77h] BYREF
  __int64 v47; // [rsp+108h] [rbp+7Fh] BYREF

  v47 = 0;
  v41 = 0;
  v4 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 8);
  v42 = 0;
  v5 = a2;
  v40 = 0;
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(0);
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        (unsigned int)&WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids,
        ActivityIdPrefix,
        (__int64)"m_spEncoderMFT");
    }
    v7 = -2147467261;
    goto LABEL_143;
  }
  v7 = (**v4)(v4, &IID_IMFMediaEventGenerator, (char *)this + 104);
  if ( v7 == -2147467262 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v10 = RdpX_GetActivityIdPrefix(v8);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids, v10);
    }
  }
  else if ( v7 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_143;
    v45 = 1020;
    v36 = "m_spEncoderMFT->QueryInterface  IID_IMFMediaEventGenerator failed";
    v11 = (char *)&word_1801A0E16;
    v37 = "ConfigureMFTEncoder";
    v38 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
    v39 = "Error HResult failed";
    v35 = &v36;
    v34 = &v37;
    v33 = &v38;
    v12 = &v39;
    goto LABEL_18;
  }
  v7 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 8))(
         *((_QWORD *)this + 8),
         &IID_ICodecAPI,
         &v47);
  if ( v7 < 0 )
  {
    LODWORD(v8) = dword_1801B76C8;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_143;
    v45 = 1023;
    v39 = "pEncoder->QueryInterface(IID_ICodecApi) failed";
    v11 = &byte_1801A0E67;
    v38 = "ConfigureMFTEncoder";
    v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
    v36 = "Error HResult failed";
    v35 = &v39;
    v34 = &v38;
    v33 = &v37;
    v12 = &v36;
    goto LABEL_18;
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v47 + 24LL))(
          v47,
          &GUID_9c27891a_ed7a_40e1_88e8_b22727a024ee) )
  {
    LOWORD(v40) = 11;
    WORD4(v40) = -1;
    v7 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v47 + 72LL))(
           v47,
           &GUID_9c27891a_ed7a_40e1_88e8_b22727a024ee,
           &v40);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_143;
      v45 = 1033;
      v39 = "spCodecApi->SetValue( CODECAPI_AVLowLatencyMode ) failed";
      v11 = byte_1801A0DC5;
      v38 = "ConfigureMFTEncoder";
      v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v36 = "Error HResult failed";
      v35 = &v39;
      v34 = &v38;
      v33 = &v37;
      v12 = &v36;
      goto LABEL_18;
    }
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v47 + 24LL))(
          v47,
          &GUID_3daf6f66_a6a7_45e0_a8e5_f2743f46a3a2) )
  {
    DWORD2(v40) = *((unsigned __int8 *)this + 148);
    LOWORD(v40) = 19;
    v7 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v47 + 72LL))(
           v47,
           &GUID_3daf6f66_a6a7_45e0_a8e5_f2743f46a3a2,
           &v40);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_143;
      v45 = 1044;
      v39 = "spCodecApi->SetValue( CODECAPI_AVEncVideoMaxQP ) failed";
      v11 = (char *)&dword_1801A0D74;
      v38 = "ConfigureMFTEncoder";
      v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v36 = "Error HResult failed";
      v35 = &v39;
      v34 = &v38;
      v33 = &v37;
      v12 = &v36;
      goto LABEL_18;
    }
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v47 + 24LL))(
          v47,
          &GUID_0ee22c6a_a37c_4568_b5f1_9d4c2b3ab886) )
  {
    DWORD2(v40) = *((unsigned __int8 *)this + 149);
    LOWORD(v40) = 19;
    v7 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v47 + 72LL))(
           v47,
           &GUID_0ee22c6a_a37c_4568_b5f1_9d4c2b3ab886,
           &v40);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_143;
      v45 = 1055;
      v39 = "spCodecApi->SetValue( CODECAPI_AVEncVideoMinQP ) failed";
      v11 = byte_1801A0D23;
      v38 = "ConfigureMFTEncoder";
      v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v36 = "Error HResult failed";
      v35 = &v39;
      v34 = &v38;
      v33 = &v37;
      v12 = &v36;
      goto LABEL_18;
    }
  }
  if ( *((_DWORD *)this + 66) )
  {
    if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v47 + 24LL))(
            v47,
            &GUID_95f31b26_95a4_41aa_9303_246a7fc6eef1) )
    {
      DWORD2(v40) = *((_DWORD *)this + 66);
      LOWORD(v40) = 19;
      v7 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v47 + 72LL))(
             v47,
             &GUID_95f31b26_95a4_41aa_9303_246a7fc6eef1,
             &v40);
      if ( v7 < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_143;
        v45 = 1063;
        v39 = "SetValue CODECAPI_AVEncMPVGOPSize failed";
        v11 = (char *)word_1801A0CD2;
        v38 = "ConfigureMFTEncoder";
        v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
        v36 = "Error HResult failed";
        v35 = &v39;
        v34 = &v38;
        v33 = &v37;
        v12 = &v36;
        goto LABEL_18;
      }
    }
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v47 + 24LL))(
          v47,
          &GUID_1c0608e9_370c_4710_8a58_cb6181c42423) )
  {
    LOWORD(v40) = 19;
    DWORD2(v40) = v5 != 0 ? 3 : 0;
    v7 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v47 + 72LL))(
           v47,
           &GUID_1c0608e9_370c_4710_8a58_cb6181c42423,
           &v40);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_143;
      v45 = 1083;
      v39 = "spCodecApi->SetValue( CODECAPI_AVEncCommonRateControlMode ) failed";
      v11 = byte_1801A0C81;
      v38 = "ConfigureMFTEncoder";
      v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v36 = "Error HResult failed";
      v35 = &v39;
      v34 = &v38;
      v33 = &v37;
      v12 = &v36;
      goto LABEL_18;
    }
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v47 + 24LL))(
          v47,
          &GUID_98332df8_03cd_476b_89fa_3f9e442dec9f) )
  {
    LOWORD(v40) = 19;
    DWORD2(v40) = 30;
    v7 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v47 + 72LL))(
           v47,
           &GUID_98332df8_03cd_476b_89fa_3f9e442dec9f,
           &v40);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_143;
      v45 = 1096;
      v39 = "spCodecApi->SetValue(CODECAPI_AVEncCommonQualityVsSpeed) failed";
      v11 = (char *)qword_1801A0C30;
      v38 = "ConfigureMFTEncoder";
      v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v36 = "Error HResult failed";
      v35 = &v39;
      v34 = &v38;
      v33 = &v37;
      v12 = &v36;
      goto LABEL_18;
    }
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v47 + 24LL))(
          v47,
          &GUID_d74f7f18_44dd_4b85_aba3_05d9f42a8280) )
  {
    LOWORD(v40) = 19;
    DWORD2(v40) = 1;
    v7 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v47 + 72LL))(
           v47,
           &GUID_d74f7f18_44dd_4b85_aba3_05d9f42a8280,
           &v40);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_143;
      v45 = 1105;
      v39 = "spCodecApi->SetValue( CODECAPI_AVEncVideoROIEnabled ) failed";
      v11 = &byte_1801A0BDF;
      v38 = "ConfigureMFTEncoder";
      v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v36 = "Error HResult failed";
      v35 = &v39;
      v34 = &v38;
      v33 = &v37;
      v12 = &v36;
      goto LABEL_18;
    }
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v47 + 24LL))(
          v47,
          &GUID_8acb8fdd_5e0c_4c66_8729_b8f629ab04fb) )
  {
    LOWORD(v40) = 19;
    DWORD2(v40) = 1;
    v7 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v47 + 72LL))(
           v47,
           &GUID_8acb8fdd_5e0c_4c66_8729_b8f629ab04fb,
           &v40);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_143;
      v45 = 1113;
      v39 = "spCodecApi->SetValue( CODECAPI_AVEncVideoDirtyRectEnabled ) failed";
      v11 = (char *)&word_1801A0B8E;
      v38 = "ConfigureMFTEncoder";
      v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v36 = "Error HResult failed";
      v35 = &v39;
      v34 = &v38;
      v33 = &v37;
      v12 = &v36;
      goto LABEL_18;
    }
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v47 + 24LL))(
          v47,
          &GUID_fcbf57a3_7ea5_4b0c_9644_69b40c39c391) )
  {
    LOWORD(v40) = 19;
    DWORD2(v40) = 100;
    v7 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v47 + 72LL))(
           v47,
           &GUID_fcbf57a3_7ea5_4b0c_9644_69b40c39c391,
           &v40);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_143;
      v45 = 1124;
      v39 = "spCodecApi->SetValue( CODECAPI_AVEncCommonQuality ) failed";
      v11 = byte_1801A0B3D;
      v38 = "ConfigureMFTEncoder";
      v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v36 = "Error HResult failed";
      v35 = &v39;
      v34 = &v38;
      v33 = &v37;
      v12 = &v36;
      goto LABEL_18;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v13 = RdpX_GetActivityIdPrefix(v8);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids, v13);
    }
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v47 + 24LL))(
          v47,
          &GUID_e9e782ef_5f18_44c9_a90b_e9c3c2c17b0b) )
  {
    v14 = 1;
    DWORD2(v40) = 2;
    LOWORD(v40) = 19;
    if ( (*(unsigned int (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v47 + 72LL))(
           v47,
           &GUID_e9e782ef_5f18_44c9_a90b_e9c3c2c17b0b,
           &v40) )
    {
      DWORD2(v40) = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v47 + 72LL))(
             v47,
             &GUID_e9e782ef_5f18_44c9_a90b_e9c3c2c17b0b,
             &v40);
      if ( v7 < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_143;
        v45 = 1140;
        v39 = "spCodecApi->SetValue(CODECAPI_AVEncSliceControlMode) failed both 0 and 2";
        v11 = (char *)&dword_1801A0AEC;
        v38 = "ConfigureMFTEncoder";
        v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
        v36 = "Error HResult failed";
        v35 = &v39;
        v34 = &v38;
        v33 = &v37;
        v12 = &v36;
        goto LABEL_18;
      }
      v14 = 0;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v47 + 24LL))(
           v47,
           &GUID_92f51df3_07a5_4172_aefe_c69ca3b60e35);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_143;
      v45 = 1146;
      v39 = "CODECAPI_AVEncSliceControlMode is supported but CODECAPI_AVEncSliceControlSize not supported";
      v11 = (char *)word_1801A0A4A;
      v38 = "ConfigureMFTEncoder";
      v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v36 = "Error HResult failed";
      v35 = &v39;
      v34 = &v38;
      v33 = &v37;
      v12 = &v36;
      goto LABEL_18;
    }
    EncoderSliceControlSize = AvcEncoder::GetEncoderSliceControlSize(this, v14, v5);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v16 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control);
      WPP_SF_DdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        &WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids,
        v16,
        2 * v14,
        EncoderSliceControlSize);
    }
    DWORD2(v40) = EncoderSliceControlSize;
    v7 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v47 + 72LL))(
           v47,
           &GUID_92f51df3_07a5_4172_aefe_c69ca3b60e35,
           &v40);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_143;
      v45 = 1154;
      v39 = "spCodecApi->SetValue(CODECAPI_AVEncSliceControlSize) failed";
      v11 = byte_1801A0A9B;
      v38 = "ConfigureMFTEncoder";
      v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v36 = "Error HResult failed";
      v35 = &v39;
      v34 = &v38;
      v33 = &v37;
      v12 = &v36;
      goto LABEL_18;
    }
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v47 + 24LL))(
          v47,
          &GUID_d2e8e399_0623_4bf3_92a8_4d1818529ded) )
  {
    DWORD2(v40) = 0;
    LOWORD(v40) = 19;
    v7 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v47 + 72LL))(
           v47,
           &GUID_d2e8e399_0623_4bf3_92a8_4d1818529ded,
           &v40);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_143;
      v45 = 1166;
      v39 = "spCodecApi->SetValue( CODECAPI_AVEnableInLoopDeblockFilter ) failed";
      v11 = byte_1801A09F9;
      v38 = "ConfigureMFTEncoder";
      v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v36 = "Error HResult failed";
      v35 = &v39;
      v34 = &v38;
      v33 = &v37;
      v12 = &v36;
      goto LABEL_18;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v17 = RdpX_GetActivityIdPrefix(v8);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids, v17);
    }
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v47 + 24LL))(
          v47,
          &GUID_b28a6e64_3ff9_446a_8a4b_0d7a53413236) )
  {
    LOWORD(v40) = 19;
    DWORD2(v40) = 6;
    v7 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v47 + 72LL))(
           v47,
           &GUID_b28a6e64_3ff9_446a_8a4b_0d7a53413236,
           &v40);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_143;
      v45 = 1177;
      v39 = "spCodecApi->SetValue(CODECAPI_AVScenarioInfo) failed";
      v11 = (char *)qword_1801A09A8;
      v38 = "ConfigureMFTEncoder";
      v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v36 = "Error HResult failed";
      v35 = &v39;
      v34 = &v38;
      v33 = &v37;
      v12 = &v36;
      goto LABEL_18;
    }
  }
  if ( *((_DWORD *)this + 70) )
  {
    if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v47 + 24LL))(
            v47,
            &GUID_8a47ab5a_4798_4c93_b5a5_554f9a3b9f50) )
    {
      v18 = *((_DWORD *)this + 71) != 0;
      LOWORD(v40) = 19;
      DWORD2(v40) = v18 + 1;
      v7 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v47 + 72LL))(
             v47,
             &GUID_8a47ab5a_4798_4c93_b5a5_554f9a3b9f50,
             &v40);
      if ( v7 < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_143;
        v45 = 1198;
        v39 = "spCodecApi->SetValue(CODECAPI_AVEncChromaEncodeMode) failed";
        v11 = &byte_1801A0957;
        v38 = "ConfigureMFTEncoder";
        v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
        v36 = "Error HResult failed";
        v35 = &v39;
        v34 = &v38;
        v33 = &v37;
        v12 = &v36;
        goto LABEL_18;
      }
    }
  }
  if ( (*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v47 + 24LL))(
         v47,
         &GUID_d2b46a2a_e8ee_4ec5_869e_449b6c62c81a) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v20 = RdpX_GetActivityIdPrefix(v19);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids, v20);
    }
  }
  else
  {
    LOWORD(v40) = 19;
    DWORD2(v40) = 1;
    v7 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v47 + 72LL))(
           v47,
           &GUID_d2b46a2a_e8ee_4ec5_869e_449b6c62c81a,
           &v40);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_143;
      v45 = 1209;
      v39 = "spCodecApi->SetValue(CODECAPI_AVEncNoInputCopy) failed";
      v11 = (char *)&word_1801A0906;
      v38 = "ConfigureMFTEncoder";
      v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v36 = "Error HResult failed";
      v35 = &v39;
      v34 = &v38;
      v33 = &v37;
      v12 = &v36;
      goto LABEL_18;
    }
  }
  if ( !v5 && *((_DWORD *)this + 51) == 1 )
  {
    v44 = 0;
    v43 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v47 + 64LL))(
           v47,
           &GUID_8bfda3b8_7387_4c07_924f_fe63006cf22b,
           &v43);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_143;
      v45 = 1223;
      v39 = "spCodecApi->GetValue(&CODECAPI_FeatureMapFlagsUsed, &capabilityHint) failed";
      v11 = byte_1801A08B5;
      v38 = "ConfigureMFTEncoder";
      v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v36 = "Error HResult failed";
      v35 = &v39;
      v34 = &v38;
      v33 = &v37;
      v12 = &v36;
      goto LABEL_18;
    }
    LOWORD(v43) = 19;
    DWORD2(v43) = -17;
    v7 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v47 + 72LL))(
           v47,
           &GUID_8bfda3b8_7387_4c07_924f_fe63006cf22b,
           &v43);
    if ( (unsigned int)dword_1801B76C8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1801B76C8, 0x470000000000LL) )
    {
      v45 = v7;
      v46 = (char *)this + 8;
      v37 = (const char *)0x1000000;
      v39 = "AVCEncoder";
      v38 = "Stack";
      v36 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned int)byte_1801A07D5,
        a3,
        v9,
        (__int64)&v36,
        (__int64)&v37,
        (__int64)&v38,
        (__int64)&v39,
        (__int64)&v46,
        (__int64)&v45);
    }
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_143;
      v45 = 1235;
      v39 = "spCodecApi->SetValue(&CODECAPI_FeatureMapFlagsUsed, &capabilityHint) failed";
      v11 = (char *)&dword_1801A0864;
      v38 = "ConfigureMFTEncoder";
      v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
      v36 = "Error HResult failed";
      v35 = &v39;
      v34 = &v38;
      v33 = &v37;
      v12 = &v36;
      goto LABEL_18;
    }
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 8) + 64LL))(*((_QWORD *)this + 8), &v42);
  if ( v7 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_143;
    v45 = 1240;
    v39 = "pEncoder->GetAttributes() failed";
    v11 = (char *)&dword_1801A0784;
    v38 = "ConfigureMFTEncoder";
    v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
    v36 = "Error HResult failed";
    v35 = &v39;
    v34 = &v38;
    v33 = &v37;
    v12 = &v36;
    goto LABEL_18;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v42 + 168LL))(
         v42,
         &MF_TRANSFORM_ASYNC_UNLOCK,
         1);
  if ( v7 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_143;
    v45 = 1243;
    v39 = "MF_TRANSFORM_ASYNC_UNLOCK failed";
    v11 = byte_1801A0733;
    v38 = "ConfigureMFTEncoder";
    v37 = "onecoreuap\\termsrv\\rdp\\win\\codecs\\h264codec\\avcencoder.cpp";
    v36 = "Error HResult failed";
    v35 = &v39;
    v34 = &v38;
    v33 = &v37;
    v12 = &v36;
LABEL_18:
    LODWORD(v46) = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v8,
      (_DWORD)v11,
      a3,
      v9,
      (__int64)v12,
      (__int64)&v46,
      (__int64)v33,
      (__int64)&v45,
      (__int64)v34,
      (__int64)v35);
    goto LABEL_143;
  }
  v21 = (_QWORD *)*((_QWORD *)this + 20);
  if ( v21 )
  {
    a3 = 0;
    if ( v21[8] )
      a3 = v21[8];
    v22 = 0;
    if ( v21[9] )
      v22 = v21[9];
    v23 = 0;
    if ( v21[10] )
      v23 = v21[10];
    if ( a3 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 200LL))(v42, qword_180171908);
      if ( v7 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v25 = RdpX_GetActivityIdPrefix(v24);
        LODWORD(v32) = v7;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          (unsigned int)&WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids,
          v25,
          (__int64)"Failed to set IMFattribute H264ENC_DUMP_SOURCE",
          v32);
      }
    }
    if ( v22 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v42 + 200LL))(v42, qword_180171928, v22);
      if ( v7 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v27 = RdpX_GetActivityIdPrefix(v26);
        LODWORD(v32) = v7;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)&WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids,
          v27,
          (__int64)"Failed to set IMFattribute H264ENC_DUMP_REFS",
          v32);
      }
    }
    if ( v23 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v42 + 200LL))(v42, qword_180171918, v23);
      if ( v7 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v29 = RdpX_GetActivityIdPrefix(v28);
        LODWORD(v32) = v7;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          (unsigned int)&WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids,
          v29,
          (__int64)"Failed to set IMFattribute H264ENC_DUMP_RECON",
          v32);
      }
    }
  }
LABEL_143:
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v42, a2, a3);
  v30 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180085664  push    rbp
0x180085666  push    rbx
0x180085667  push    rsi
0x180085668  push    rdi
0x180085669  push    r12
0x18008566b  push    r14
0x18008566d  push    r15
0x18008566f  lea     rbp, [rsp-27h]
0x180085674  sub     rsp, 0B0h
0x18008567b  xor     eax, eax
0x18008567d  mov     [rbp+57h+arg_18], 0
0x180085685  mov     rdi, rcx
0x180085688  mov     [rbp+57h+var_60], rax
0x18008568c  mov     rcx, [rcx+40h]
0x180085690  xorps   xmm0, xmm0
0x180085693  mov     [rbp+57h+var_58], rax
0x180085697  mov     r12d, edx
0x18008569a  movups  [rbp+57h+var_70], xmm0
0x18008569e  test    rcx, rcx
0x1800856a1  jnz     short loc_1800856FD
0x1800856a3  mov     rax, cs:WPP_GLOBAL_Control
0x1800856aa  lea     r14, WPP_GLOBAL_Control
0x1800856b1  cmp     rax, r14
0x1800856b4  jz      short loc_1800856F3
0x1800856b6  test    byte ptr [rax+1Ch], 8
0x1800856ba  jz      short loc_1800856F3
0x1800856bc  cmp     byte ptr [rax+19h], 2
0x1800856c0  jb      short loc_1800856F3
0x1800856c2  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800856c8  lea     rcx, aMSpencodermft; "m_spEncoderMFT"
0x1800856cf  mov     edx, 18h
0x1800856d4  mov     [rsp+0E0h+var_C0], rcx
0x1800856d9  lea     r8, WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids
0x1800856e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800856e7  mov     r9d, eax
0x1800856ea  mov     rcx, [rcx+10h]
0x1800856ee  call    WPP_SF_Ds
0x1800856f3  mov     ebx, 80004003h
0x1800856f8  jmp     loc_180086B31
0x1800856fd  mov     rax, [rcx]
0x180085700  lea     r8, [rdi+68h]
0x180085704  lea     rdx, IID_IMFMediaEventGenerator
0x18008570b  mov     rax, [rax]
0x18008570e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085713  lea     r14, WPP_GLOBAL_Control
0x18008571a  mov     ebx, eax
0x18008571c  lea     r15, WPP_1187df101f8d3e84b96b04ec6b6a0c86_Traceguids
0x180085723  cmp     eax, 80004002h
0x180085728  jnz     loc_18008580D
0x18008572e  mov     rax, cs:WPP_GLOBAL_Control
0x180085735  cmp     rax, r14
0x180085738  jz      short loc_18008576A
0x18008573a  test    dword ptr [rax+1Ch], 100h
0x180085741  jz      short loc_18008576A
0x180085743  cmp     byte ptr [rax+19h], 3
0x180085747  jb      short loc_18008576A
0x180085749  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18008574f  mov     rcx, cs:WPP_GLOBAL_Control
0x180085756  mov     edx, 19h
0x18008575b  mov     r9d, eax
0x18008575e  mov     r8, r15
0x180085761  mov     rcx, [rcx+10h]
0x180085765  call    WPP_SF_d
0x18008576a  mov     rcx, [rdi+40h]
0x18008576e  lea     r8, [rbp+57h+arg_18]
0x180085772  lea     rdx, IID_ICodecAPI
0x180085779  mov     rax, [rcx]
0x18008577c  mov     rax, [rax]
0x18008577f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085784  mov     ebx, eax
0x180085786  test    eax, eax
0x180085788  jns     loc_1800858A1
0x18008578e  mov     ecx, cs:dword_1801B76C8
0x180085794  cmp     ecx, 2
0x180085797  jbe     loc_180086B31
0x18008579d  lea     rax, aPencoderQueryi; "pEncoder->QueryInterface(IID_ICodecApi)"...
0x1800857a4  mov     [rbp+57h+arg_0], 3FFh
0x1800857ab  mov     [rbp+57h+var_78], rax
0x1800857af  lea     rdx, byte_1801A0E67
0x1800857b6  lea     rax, aConfiguremften; "ConfigureMFTEncoder"
0x1800857bd  mov     [rbp+57h+var_80], rax
0x1800857c1  lea     rax, aOnecoreuapTerm_2; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x1800857c8  mov     [rbp+57h+var_88], rax
0x1800857cc  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800857d3  mov     [rbp+57h+var_90], rax
0x1800857d7  lea     rax, [rbp+57h+var_78]
0x1800857db  mov     [rsp+0E0h+var_98], rax
0x1800857e0  lea     rax, [rbp+57h+var_80]
0x1800857e4  mov     [rsp+0E0h+var_A0], rax
0x1800857e9  lea     rax, [rbp+57h+arg_0]
0x1800857ed  mov     [rsp+0E0h+var_A8], rax
0x1800857f2  lea     rax, [rbp+57h+var_88]
0x1800857f6  mov     [rsp+0E0h+var_B0], rax
0x1800857fb  lea     rax, [rbp+57h+arg_10]
0x1800857ff  mov     [rsp+0E0h+var_B8], rax
0x180085804  lea     rax, [rbp+57h+var_90]
0x180085808  jmp     loc_18008588F
0x18008580d  test    ebx, ebx
0x18008580f  jns     loc_18008576A
0x180085815  mov     eax, cs:dword_1801B76C8
0x18008581b  cmp     eax, 2
0x18008581e  jbe     loc_180086B31
0x180085824  lea     rax, aMSpencodermftQ; "m_spEncoderMFT->QueryInterface  IID_IMF"...
0x18008582b  mov     [rbp+57h+arg_0], 3FCh
0x180085832  mov     [rbp+57h+var_90], rax
0x180085836  lea     rdx, word_1801A0E16
0x18008583d  lea     rax, aConfiguremften; "ConfigureMFTEncoder"
0x180085844  mov     [rbp+57h+var_88], rax
0x180085848  lea     rax, aOnecoreuapTerm_2; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18008584f  mov     [rbp+57h+var_80], rax
0x180085853  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008585a  mov     [rbp+57h+var_78], rax
0x18008585e  lea     rax, [rbp+57h+var_90]
0x180085862  mov     [rsp+0E0h+var_98], rax
0x180085867  lea     rax, [rbp+57h+var_88]
0x18008586b  mov     [rsp+0E0h+var_A0], rax
0x180085870  lea     rax, [rbp+57h+arg_0]
0x180085874  mov     [rsp+0E0h+var_A8], rax
0x180085879  lea     rax, [rbp+57h+var_80]
0x18008587d  mov     [rsp+0E0h+var_B0], rax
0x180085882  lea     rax, [rbp+57h+arg_10]
0x180085886  mov     [rsp+0E0h+var_B8], rax
0x18008588b  lea     rax, [rbp+57h+var_78]
0x18008588f  mov     [rsp+0E0h+var_C0], rax
0x180085894  mov     dword ptr [rbp+57h+arg_10], ebx
0x180085897  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18008589c  jmp     loc_180086B31
0x1800858a1  mov     rcx, [rbp+57h+arg_18]
0x1800858a5  lea     rdx, _GUID_9c27891a_ed7a_40e1_88e8_b22727a024ee
0x1800858ac  mov     rax, [rcx]
0x1800858af  mov     rax, [rax+18h]
0x1800858b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800858b8  test    eax, eax
0x1800858ba  jnz     loc_180085970
0x1800858c0  mov     rcx, [rbp+57h+arg_18]
0x1800858c4  lea     r8, [rbp+57h+var_70]
0x1800858c8  mov     eax, 0Bh
0x1800858cd  lea     rdx, _GUID_9c27891a_ed7a_40e1_88e8_b22727a024ee
0x1800858d4  mov     word ptr [rbp+57h+var_70], ax
0x1800858d8  or      eax, 0FFFFFFFFh
0x1800858db  mov     word ptr [rbp+57h+var_70+8], ax
0x1800858df  mov     rax, [rcx]
0x1800858e2  mov     rax, [rax+48h]
0x1800858e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800858eb  mov     ebx, eax
0x1800858ed  test    eax, eax
0x1800858ef  jns     short loc_180085970
0x1800858f1  mov     eax, cs:dword_1801B76C8
0x1800858f7  cmp     eax, 2
0x1800858fa  jbe     loc_180086B31
0x180085900  lea     rax, aSpcodecapiSetv_11; "spCodecApi->SetValue( CODECAPI_AVLowLat"...
0x180085907  mov     [rbp+57h+arg_0], 409h
0x18008590e  mov     [rbp+57h+var_78], rax
0x180085912  lea     rdx, byte_1801A0DC5
0x180085919  lea     rax, aConfiguremften; "ConfigureMFTEncoder"
0x180085920  mov     [rbp+57h+var_80], rax
0x180085924  lea     rax, aOnecoreuapTerm_2; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x18008592b  mov     [rbp+57h+var_88], rax
0x18008592f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180085936  mov     [rbp+57h+var_90], rax
0x18008593a  lea     rax, [rbp+57h+var_78]
0x18008593e  mov     [rsp+0E0h+var_98], rax
0x180085943  lea     rax, [rbp+57h+var_80]
0x180085947  mov     [rsp+0E0h+var_A0], rax
0x18008594c  lea     rax, [rbp+57h+arg_0]
0x180085950  mov     [rsp+0E0h+var_A8], rax
0x180085955  lea     rax, [rbp+57h+var_88]
0x180085959  mov     [rsp+0E0h+var_B0], rax
0x18008595e  lea     rax, [rbp+57h+arg_10]
0x180085962  mov     [rsp+0E0h+var_B8], rax
0x180085967  lea     rax, [rbp+57h+var_90]
0x18008596b  jmp     loc_18008588F
0x180085970  mov     rcx, [rbp+57h+arg_18]
0x180085974  lea     rdx, _GUID_3daf6f66_a6a7_45e0_a8e5_f2743f46a3a2
0x18008597b  mov     rax, [rcx]
0x18008597e  mov     rax, [rax+18h]
0x180085982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085987  mov     esi, 13h
0x18008598c  test    eax, eax
0x18008598e  jnz     loc_180085A42
0x180085994  movzx   eax, byte ptr [rdi+94h]
0x18008599b  lea     r8, [rbp+57h+var_70]
0x18008599f  mov     rcx, [rbp+57h+arg_18]
0x1800859a3  lea     rdx, _GUID_3daf6f66_a6a7_45e0_a8e5_f2743f46a3a2
0x1800859aa  mov     dword ptr [rbp+57h+var_70+8], eax
0x1800859ad  mov     word ptr [rbp+57h+var_70], si
0x1800859b1  mov     rax, [rcx]
0x1800859b4  mov     rax, [rax+48h]
0x1800859b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800859bd  mov     ebx, eax
0x1800859bf  test    eax, eax
0x1800859c1  jns     short loc_180085A42
0x1800859c3  mov     eax, cs:dword_1801B76C8
0x1800859c9  cmp     eax, 2
0x1800859cc  jbe     loc_180086B31
0x1800859d2  lea     rax, aSpcodecapiSetv_12; "spCodecApi->SetValue( CODECAPI_AVEncVid"...
0x1800859d9  mov     [rbp+57h+arg_0], 414h
0x1800859e0  mov     [rbp+57h+var_78], rax
0x1800859e4  lea     rdx, dword_1801A0D74
0x1800859eb  lea     rax, aConfiguremften; "ConfigureMFTEncoder"
0x1800859f2  mov     [rbp+57h+var_80], rax
0x1800859f6  lea     rax, aOnecoreuapTerm_2; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x1800859fd  mov     [rbp+57h+var_88], rax
0x180085a01  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180085a08  mov     [rbp+57h+var_90], rax
0x180085a0c  lea     rax, [rbp+57h+var_78]
0x180085a10  mov     [rsp+0E0h+var_98], rax
0x180085a15  lea     rax, [rbp+57h+var_80]
0x180085a19  mov     [rsp+0E0h+var_A0], rax
0x180085a1e  lea     rax, [rbp+57h+arg_0]
0x180085a22  mov     [rsp+0E0h+var_A8], rax
0x180085a27  lea     rax, [rbp+57h+var_88]
0x180085a2b  mov     [rsp+0E0h+var_B0], rax
0x180085a30  lea     rax, [rbp+57h+arg_10]
0x180085a34  mov     [rsp+0E0h+var_B8], rax
0x180085a39  lea     rax, [rbp+57h+var_90]
0x180085a3d  jmp     loc_18008588F
0x180085a42  mov     rcx, [rbp+57h+arg_18]
0x180085a46  lea     rdx, _GUID_0ee22c6a_a37c_4568_b5f1_9d4c2b3ab886
0x180085a4d  mov     rax, [rcx]
0x180085a50  mov     rax, [rax+18h]
0x180085a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085a59  test    eax, eax
0x180085a5b  jnz     loc_180085B0F
0x180085a61  movzx   eax, byte ptr [rdi+95h]
0x180085a68  lea     r8, [rbp+57h+var_70]
0x180085a6c  mov     rcx, [rbp+57h+arg_18]
0x180085a70  lea     rdx, _GUID_0ee22c6a_a37c_4568_b5f1_9d4c2b3ab886
0x180085a77  mov     dword ptr [rbp+57h+var_70+8], eax
0x180085a7a  mov     word ptr [rbp+57h+var_70], si
0x180085a7e  mov     rax, [rcx]
0x180085a81  mov     rax, [rax+48h]
0x180085a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085a8a  mov     ebx, eax
0x180085a8c  test    eax, eax
0x180085a8e  jns     short loc_180085B0F
0x180085a90  mov     eax, cs:dword_1801B76C8
0x180085a96  cmp     eax, 2
0x180085a99  jbe     loc_180086B31
0x180085a9f  lea     rax, aSpcodecapiSetv_0; "spCodecApi->SetValue( CODECAPI_AVEncVid"...
0x180085aa6  mov     [rbp+57h+arg_0], 41Fh
0x180085aad  mov     [rbp+57h+var_78], rax
0x180085ab1  lea     rdx, byte_1801A0D23
0x180085ab8  lea     rax, aConfiguremften; "ConfigureMFTEncoder"
0x180085abf  mov     [rbp+57h+var_80], rax
0x180085ac3  lea     rax, aOnecoreuapTerm_2; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x180085aca  mov     [rbp+57h+var_88], rax
0x180085ace  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180085ad5  mov     [rbp+57h+var_90], rax
0x180085ad9  lea     rax, [rbp+57h+var_78]
0x180085add  mov     [rsp+0E0h+var_98], rax
0x180085ae2  lea     rax, [rbp+57h+var_80]
0x180085ae6  mov     [rsp+0E0h+var_A0], rax
0x180085aeb  lea     rax, [rbp+57h+arg_0]
0x180085aef  mov     [rsp+0E0h+var_A8], rax
0x180085af4  lea     rax, [rbp+57h+var_88]
0x180085af8  mov     [rsp+0E0h+var_B0], rax
0x180085afd  lea     rax, [rbp+57h+arg_10]
0x180085b01  mov     [rsp+0E0h+var_B8], rax
0x180085b06  lea     rax, [rbp+57h+var_90]
0x180085b0a  jmp     loc_18008588F
0x180085b0f  cmp     dword ptr [rdi+108h], 0
0x180085b16  jz      loc_180085BE8
0x180085b1c  mov     rcx, [rbp+57h+arg_18]
0x180085b20  lea     rdx, _GUID_95f31b26_95a4_41aa_9303_246a7fc6eef1
0x180085b27  mov     rax, [rcx]
0x180085b2a  mov     rax, [rax+18h]
0x180085b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085b33  test    eax, eax
0x180085b35  jnz     loc_180085BE8
0x180085b3b  mov     eax, [rdi+108h]
0x180085b41  lea     r8, [rbp+57h+var_70]
0x180085b45  mov     rcx, [rbp+57h+arg_18]
0x180085b49  lea     rdx, _GUID_95f31b26_95a4_41aa_9303_246a7fc6eef1
0x180085b50  mov     dword ptr [rbp+57h+var_70+8], eax
0x180085b53  mov     word ptr [rbp+57h+var_70], si
0x180085b57  mov     rax, [rcx]
0x180085b5a  mov     rax, [rax+48h]
0x180085b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085b63  mov     ebx, eax
0x180085b65  test    eax, eax
0x180085b67  jns     short loc_180085BE8
0x180085b69  mov     eax, cs:dword_1801B76C8
0x180085b6f  cmp     eax, 2
0x180085b72  jbe     loc_180086B31
0x180085b78  lea     rax, aSetvalueCodeca; "SetValue CODECAPI_AVEncMPVGOPSize faile"...
0x180085b7f  mov     [rbp+57h+arg_0], 427h
0x180085b86  mov     [rbp+57h+var_78], rax
0x180085b8a  lea     rdx, word_1801A0CD2
0x180085b91  lea     rax, aConfiguremften; "ConfigureMFTEncoder"
0x180085b98  mov     [rbp+57h+var_80], rax
0x180085b9c  lea     rax, aOnecoreuapTerm_2; "onecoreuap\\termsrv\\rdp\\win\\codecs\\"...
0x180085ba3  mov     [rbp+57h+var_88], rax
0x180085ba7  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180085bae  mov     [rbp+57h+var_90], rax
0x180085bb2  lea     rax, [rbp+57h+var_78]
0x180085bb6  mov     [rsp+0E0h+var_98], rax
0x180085bbb  lea     rax, [rbp+57h+var_80]
0x180085bbf  mov     [rsp+0E0h+var_A0], rax
0x180085bc4  lea     rax, [rbp+57h+arg_0]
  ... truncated ...
```
