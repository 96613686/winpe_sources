# HevcEncoder::ConfigureMFTEncoder(int)

- ea: `0x180094120`
- end: `0x180094bcd`
- name: `?ConfigureMFTEncoder@HevcEncoder@@AEAAJH@Z`
- size: `2733`
- prototype: `__int64 __fastcall(HevcEncoder *__hidden this, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180097960`
- `0x180097b9c`

## callees

- `0x1800071c0`
- `0x180009628`
- `0x18002e600`
- `0x1800598d0`
- `0x180094120`
- `0x18014d010`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180094172`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009424a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180094290`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009431e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800943af`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180094439`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800944d1`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009455a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800945e3`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009466f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800946fb`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800947af`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009487b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180094901`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180094988`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800949ed`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180094a7b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180094af0`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180094b65`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180094172`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009424a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180094290`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009431e`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800943af`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180094439`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800944d1`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009455a`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800945e3`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009466f`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800946fb`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800947af`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18009487b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180094901`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180094988`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x1800949ed`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180094a7b`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180094af0`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180094b65`

## string_xrefs

- `0x180094565`: `spCodecApi->SetValue( CODECAPI_AVEncCommonRateControlMode ) failed`
- `0x1800945ee`: `spCodecApi->SetValue(CODECAPI_AVEncCommonQualityVsSpeed) failed`
- `0x180094706`: `spCodecApi->SetValue( CODECAPI_AVEncCommonQuality ) failed`
- `0x18009490c`: `spCodecApi->SetValue(CODECAPI_AVEncNoInputCopy) failed`
- `0x180094923`: `CODECAPI_AVEncNoInputCopy not supported`

## pseudocode

```c
__int64 __fastcall HevcEncoder::ConfigureMFTEncoder(HevcEncoder *this, __int64 a2, __int64 a3)
{
  __int64 (__fastcall ***v4)(_QWORD, GUID *, char *); // rcx
  int ActivityIdPrefix; // eax
  int v6; // edi
  __int64 v7; // rcx
  int v8; // r9d
  __int64 v9; // rcx
  int v10; // eax
  int v11; // edx
  const char *v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // r9d
  __int64 v22; // rcx
  int v23; // r9d
  bool v24; // cf
  __int64 v25; // rcx
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  _QWORD *v32; // rax
  __int64 v33; // rsi
  __int64 v34; // r14
  __int64 v35; // rcx
  int v36; // eax
  __int64 v37; // rcx
  int v38; // eax
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v42; // [rsp+28h] [rbp-28h]
  __int128 v43; // [rsp+30h] [rbp-20h] BYREF
  __int64 v44; // [rsp+40h] [rbp-10h]
  __int64 v45; // [rsp+80h] [rbp+30h] BYREF
  __int64 v46; // [rsp+90h] [rbp+40h] BYREF
  const char *v47; // [rsp+98h] [rbp+48h] BYREF

  v45 = 0;
  v44 = 0;
  v4 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*((_QWORD *)this + 7);
  v46 = 0;
  v43 = 0;
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(0);
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        (unsigned int)WPP_225ebdff2f7730fc004038fb7f46f5ea_Traceguids,
        ActivityIdPrefix,
        (__int64)"m_spEncoderMFT");
    }
    v6 = -2147467261;
    goto LABEL_130;
  }
  v6 = (**v4)(v4, &IID_IMFMediaEventGenerator, (char *)this + 96);
  if ( v6 == -2147467262 )
  {
    if ( (unsigned int)dword_1801B76C8 > 3 )
    {
      v47 = "The selected MF encoder does not support async encode. Switching to sync mode.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v7,
        (unsigned int)byte_1801A268D,
        a3,
        v8,
        (__int64)&v47);
    }
  }
  else if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_130;
    }
    v10 = RdpX_GetActivityIdPrefix(v7);
    v11 = 38;
    v12 = "m_spEncoderMFT->QueryInterface  IID_IMFMediaEventGenerator failed";
LABEL_129:
    LODWORD(v42) = v6;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)WPP_225ebdff2f7730fc004038fb7f46f5ea_Traceguids,
      v10,
      (__int64)v12,
      v42,
      v43,
      v44);
    goto LABEL_130;
  }
  v6 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 7))(
         *((_QWORD *)this + 7),
         &IID_ICodecAPI,
         &v45);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_130;
    }
    v10 = RdpX_GetActivityIdPrefix(v9);
    v11 = 39;
    v12 = "pEncoder->QueryInterface( IID_ICodecApi ) failed";
    goto LABEL_129;
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v45 + 24LL))(
          v45,
          &GUID_9c27891a_ed7a_40e1_88e8_b22727a024ee) )
  {
    LOWORD(v43) = 11;
    WORD4(v43) = -1;
    v6 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v45 + 72LL))(
           v45,
           &GUID_9c27891a_ed7a_40e1_88e8_b22727a024ee,
           &v43);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_130;
      }
      v10 = RdpX_GetActivityIdPrefix(v13);
      v11 = 40;
      v12 = "spCodecApi->SetValue( CODECAPI_AVLowLatencyMode ) failed";
      goto LABEL_129;
    }
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v45 + 24LL))(
          v45,
          &GUID_3daf6f66_a6a7_45e0_a8e5_f2743f46a3a2) )
  {
    DWORD2(v43) = *((unsigned __int8 *)this + 140);
    LOWORD(v43) = 19;
    v6 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v45 + 72LL))(
           v45,
           &GUID_3daf6f66_a6a7_45e0_a8e5_f2743f46a3a2,
           &v43);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_130;
      }
      v10 = RdpX_GetActivityIdPrefix(v14);
      v11 = 41;
      v12 = "spCodecApi->SetValue( CODECAPI_AVEncVideoMaxQP ) failed";
      goto LABEL_129;
    }
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v45 + 24LL))(
          v45,
          &GUID_0ee22c6a_a37c_4568_b5f1_9d4c2b3ab886) )
  {
    DWORD2(v43) = *((unsigned __int8 *)this + 141);
    LOWORD(v43) = 19;
    v6 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v45 + 72LL))(
           v45,
           &GUID_0ee22c6a_a37c_4568_b5f1_9d4c2b3ab886,
           &v43);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_130;
      }
      v10 = RdpX_GetActivityIdPrefix(v15);
      v11 = 42;
      v12 = "spCodecApi->SetValue( CODECAPI_AVEncVideoMinQP ) failed";
      goto LABEL_129;
    }
  }
  if ( *((_DWORD *)this + 54) )
  {
    if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v45 + 24LL))(
            v45,
            &GUID_95f31b26_95a4_41aa_9303_246a7fc6eef1) )
    {
      DWORD2(v43) = *((_DWORD *)this + 54);
      LOWORD(v43) = 19;
      v6 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v45 + 72LL))(
             v45,
             &GUID_95f31b26_95a4_41aa_9303_246a7fc6eef1,
             &v43);
      if ( v6 < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_130;
        }
        v10 = RdpX_GetActivityIdPrefix(v16);
        v11 = 43;
        v12 = "SetValue CODECAPI_AVEncMPVGOPSize failed";
        goto LABEL_129;
      }
    }
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v45 + 24LL))(
          v45,
          &GUID_1c0608e9_370c_4710_8a58_cb6181c42423) )
  {
    LOWORD(v43) = 19;
    DWORD2(v43) = 3;
    v6 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v45 + 72LL))(
           v45,
           &GUID_1c0608e9_370c_4710_8a58_cb6181c42423,
           &v43);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_130;
      }
      v10 = RdpX_GetActivityIdPrefix(v17);
      v11 = 44;
      v12 = "spCodecApi->SetValue( CODECAPI_AVEncCommonRateControlMode ) failed";
      goto LABEL_129;
    }
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v45 + 24LL))(
          v45,
          &GUID_98332df8_03cd_476b_89fa_3f9e442dec9f) )
  {
    LOWORD(v43) = 19;
    DWORD2(v43) = 30;
    v6 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v45 + 72LL))(
           v45,
           &GUID_98332df8_03cd_476b_89fa_3f9e442dec9f,
           &v43);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_130;
      }
      v10 = RdpX_GetActivityIdPrefix(v18);
      v11 = 45;
      v12 = "spCodecApi->SetValue(CODECAPI_AVEncCommonQualityVsSpeed) failed";
      goto LABEL_129;
    }
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v45 + 24LL))(
          v45,
          &GUID_8acb8fdd_5e0c_4c66_8729_b8f629ab04fb) )
  {
    LOWORD(v43) = 19;
    DWORD2(v43) = 1;
    v6 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v45 + 72LL))(
           v45,
           &GUID_8acb8fdd_5e0c_4c66_8729_b8f629ab04fb,
           &v43);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_130;
      }
      v10 = RdpX_GetActivityIdPrefix(v19);
      v11 = 47;
      v12 = "spCodecApi->SetValue( CODECAPI_AVEncVideoDirtyRectEnabled ) failed";
      goto LABEL_129;
    }
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v45 + 24LL))(
          v45,
          &GUID_fcbf57a3_7ea5_4b0c_9644_69b40c39c391) )
  {
    LOWORD(v43) = 19;
    DWORD2(v43) = 100;
    v6 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v45 + 72LL))(
           v45,
           &GUID_fcbf57a3_7ea5_4b0c_9644_69b40c39c391,
           &v43);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_130;
      }
      v10 = RdpX_GetActivityIdPrefix(v20);
      v11 = 48;
      v12 = "spCodecApi->SetValue( CODECAPI_AVEncCommonQuality ) failed";
      goto LABEL_129;
    }
    if ( (unsigned int)dword_1801B76C8 > 4 )
    {
      v47 = "Use constant quality 100 as rate control initialization";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v20,
        (unsigned int)byte_1801A2641,
        a3,
        v21,
        (__int64)&v47);
    }
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v45 + 24LL))(
          v45,
          &GUID_d2e8e399_0623_4bf3_92a8_4d1818529ded) )
  {
    DWORD2(v43) = 0;
    LOWORD(v43) = 19;
    v6 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v45 + 72LL))(
           v45,
           &GUID_d2e8e399_0623_4bf3_92a8_4d1818529ded,
           &v43);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_130;
      }
      v10 = RdpX_GetActivityIdPrefix(v22);
      v11 = 52;
      v12 = "spCodecApi->SetValue( CODECAPI_AVEnableInLoopDeblockFilter ) failed";
      goto LABEL_129;
    }
    if ( (unsigned int)dword_1801B76C8 > 4 )
    {
      v47 = "Able to disable in-loop deblocking in encoding";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v22,
        (unsigned int)&byte_1801A2667,
        a3,
        v23,
        (__int64)&v47);
    }
  }
  if ( *((_DWORD *)this + 58) )
  {
    if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v45 + 24LL))(
            v45,
            &GUID_8a47ab5a_4798_4c93_b5a5_554f9a3b9f50) )
    {
      v24 = *((_DWORD *)this + 58) != 0;
      LOWORD(v43) = 19;
      DWORD2(v43) = v24 + 1;
      v6 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v45 + 72LL))(
             v45,
             &GUID_8a47ab5a_4798_4c93_b5a5_554f9a3b9f50,
             &v43);
      if ( v6 < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_130;
        }
        v10 = RdpX_GetActivityIdPrefix(v25);
        v11 = 53;
        v12 = "spCodecApi->SetValue(CODECAPI_AVEncChromaEncodeMode) failed";
        goto LABEL_129;
      }
    }
  }
  if ( (*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v45 + 24LL))(
         v45,
         &GUID_d2b46a2a_e8ee_4ec5_869e_449b6c62c81a) )
  {
    if ( (unsigned int)dword_1801B76C8 > 5 )
    {
      v47 = "CODECAPI_AVEncNoInputCopy not supported";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v26,
        (unsigned int)byte_1801A261B,
        v27,
        v28,
        (__int64)&v47);
    }
  }
  else
  {
    LOWORD(v43) = 19;
    DWORD2(v43) = 1;
    v6 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v45 + 72LL))(
           v45,
           &GUID_d2b46a2a_e8ee_4ec5_869e_449b6c62c81a,
           &v43);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_130;
      }
      v10 = RdpX_GetActivityIdPrefix(v29);
      v11 = 54;
      v12 = "spCodecApi->SetValue(CODECAPI_AVEncNoInputCopy) failed";
      goto LABEL_129;
    }
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 7) + 64LL))(*((_QWORD *)this + 7), &v46);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_130;
    }
    v10 = RdpX_GetActivityIdPrefix(v30);
    v11 = 55;
    v12 = "pEncoder->GetAttributes() failed";
    goto LABEL_129;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v46 + 168LL))(
         v46,
         &MF_TRANSFORM_ASYNC_UNLOCK,
         1);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_130;
    }
    v10 = RdpX_GetActivityIdPrefix(v31);
    v11 = 56;
    v12 = "MF_TRANSFORM_ASYNC_UNLOCK failed";
    goto LABEL_129;
  }
  v32 = (_QWORD *)*((_QWORD *)this + 19);
  if ( v32 )
  {
    a3 = 0;
    if ( v32[8] )
      a3 = v32[8];
    v33 = 0;
    if ( v32[9] )
      v33 = v32[9];
    v34 = 0;
    if ( v32[10] )
      v34 = v32[10];
    if ( a3 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v46 + 200LL))(v46, qword_180173318);
      if ( v6 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v36 = RdpX_GetActivityIdPrefix(v35);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          57,
          (unsigned int)WPP_225ebdff2f7730fc004038fb7f46f5ea_Traceguids,
          v36,
          (__int64)"Failed to set IMFattribute H264ENC_DUMP_SOURCE",
          v6);
      }
    }
    if ( v33 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v46 + 200LL))(v46, qword_1801732F8, v33);
      if ( v6 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v38 = RdpX_GetActivityIdPrefix(v37);
        LODWORD(v42) = v6;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          58,
          (unsigned int)WPP_225ebdff2f7730fc004038fb7f46f5ea_Traceguids,
          v38,
          (__int64)"Failed to set IMFattribute H264ENC_DUMP_REFS",
          v42);
      }
    }
    if ( v34 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v46 + 200LL))(v46, qword_180173308, v34);
      if ( v6 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = RdpX_GetActivityIdPrefix(v39);
        v11 = 59;
        v12 = "Failed to set IMFattribute H264ENC_DUMP_RECON";
        goto LABEL_129;
      }
    }
  }
LABEL_130:
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v46, a2, a3);
  v40 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180094120  push    rbp
0x180094122  push    rbx
0x180094123  push    rsi
0x180094124  push    rdi
0x180094125  push    r14
0x180094127  mov     rbp, rsp
0x18009412a  sub     rsp, 50h
0x18009412e  xor     eax, eax
0x180094130  mov     [rbp+arg_0], 0
0x180094138  mov     rbx, rcx
0x18009413b  mov     [rbp+var_10], rax
0x18009413f  mov     rcx, [rcx+38h]
0x180094143  xorps   xmm0, xmm0
0x180094146  mov     [rbp+arg_10], rax
0x18009414a  movups  [rbp+var_20], xmm0
0x18009414e  test    rcx, rcx
0x180094151  jnz     short loc_1800941AD
0x180094153  mov     rax, cs:WPP_GLOBAL_Control
0x18009415a  lea     rbx, WPP_GLOBAL_Control
0x180094161  cmp     rax, rbx
0x180094164  jz      short loc_1800941A3
0x180094166  test    byte ptr [rax+1Ch], 8
0x18009416a  jz      short loc_1800941A3
0x18009416c  cmp     byte ptr [rax+19h], 2
0x180094170  jb      short loc_1800941A3
0x180094172  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180094178  lea     rcx, aMSpencodermft; "m_spEncoderMFT"
0x18009417f  mov     edx, 25h ; '%'
0x180094184  mov     [rsp+50h+var_30], rcx
0x180094189  lea     r8, WPP_225ebdff2f7730fc004038fb7f46f5ea_Traceguids
0x180094190  mov     rcx, cs:WPP_GLOBAL_Control
0x180094197  mov     r9d, eax
0x18009419a  mov     rcx, [rcx+10h]
0x18009419e  call    WPP_SF_Ds
0x1800941a3  mov     edi, 80004003h
0x1800941a8  jmp     loc_180094B9A
0x1800941ad  mov     rax, [rcx]
0x1800941b0  lea     r8, [rbx+60h]
0x1800941b4  lea     rdx, IID_IMFMediaEventGenerator
0x1800941bb  mov     rax, [rax]
0x1800941be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800941c3  mov     edi, eax
0x1800941c5  cmp     eax, 80004002h
0x1800941ca  jnz     loc_180094261
0x1800941d0  mov     eax, cs:dword_1801B76C8
0x1800941d6  cmp     eax, 3
0x1800941d9  jbe     short loc_1800941FB
0x1800941db  lea     rax, aTheSelectedMfE; "The selected MF encoder does not suppor"...
0x1800941e2  mov     [rbp+arg_18], rax
0x1800941e6  lea     rdx, byte_1801A268D
0x1800941ed  lea     rax, [rbp+arg_18]
0x1800941f1  mov     [rsp+50h+var_30], rax
0x1800941f6  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800941fb  mov     rcx, [rbx+38h]
0x1800941ff  lea     r8, [rbp+arg_0]
0x180094203  lea     rdx, IID_ICodecAPI
0x18009420a  mov     rax, [rcx]
0x18009420d  mov     rax, [rax]
0x180094210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094215  mov     edi, eax
0x180094217  test    eax, eax
0x180094219  jns     loc_1800942A7
0x18009421f  mov     rax, cs:WPP_GLOBAL_Control
0x180094226  lea     rbx, WPP_GLOBAL_Control
0x18009422d  cmp     rax, rbx
0x180094230  jz      loc_180094B9A
0x180094236  test    byte ptr [rax+1Ch], 8
0x18009423a  jz      loc_180094B9A
0x180094240  cmp     byte ptr [rax+19h], 2
0x180094244  jb      loc_180094B9A
0x18009424a  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180094250  mov     edx, 27h ; '''
0x180094255  lea     rcx, aPencoderQueryi_0; "pEncoder->QueryInterface( IID_ICodecApi"...
0x18009425c  jmp     loc_180094B77
0x180094261  test    edi, edi
0x180094263  jns     short loc_1800941FB
0x180094265  mov     rax, cs:WPP_GLOBAL_Control
0x18009426c  lea     rbx, WPP_GLOBAL_Control
0x180094273  cmp     rax, rbx
0x180094276  jz      loc_180094B9A
0x18009427c  test    byte ptr [rax+1Ch], 8
0x180094280  jz      loc_180094B9A
0x180094286  cmp     byte ptr [rax+19h], 2
0x18009428a  jb      loc_180094B9A
0x180094290  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180094296  mov     edx, 26h ; '&'
0x18009429b  lea     rcx, aMSpencodermftQ; "m_spEncoderMFT->QueryInterface  IID_IMF"...
0x1800942a2  jmp     loc_180094B77
0x1800942a7  mov     rcx, [rbp+arg_0]
0x1800942ab  lea     rdx, _GUID_9c27891a_ed7a_40e1_88e8_b22727a024ee
0x1800942b2  mov     rax, [rcx]
0x1800942b5  mov     rax, [rax+18h]
0x1800942b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800942be  test    eax, eax
0x1800942c0  jnz     short loc_180094335
0x1800942c2  mov     rcx, [rbp+arg_0]
0x1800942c6  lea     r8, [rbp+var_20]
0x1800942ca  mov     eax, 0Bh
0x1800942cf  lea     rdx, _GUID_9c27891a_ed7a_40e1_88e8_b22727a024ee
0x1800942d6  mov     word ptr [rbp+var_20], ax
0x1800942da  or      eax, 0FFFFFFFFh
0x1800942dd  mov     word ptr [rbp+var_20+8], ax
0x1800942e1  mov     rax, [rcx]
0x1800942e4  mov     rax, [rax+48h]
0x1800942e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800942ed  mov     edi, eax
0x1800942ef  test    eax, eax
0x1800942f1  jns     short loc_180094335
0x1800942f3  mov     rax, cs:WPP_GLOBAL_Control
0x1800942fa  lea     rbx, WPP_GLOBAL_Control
0x180094301  cmp     rax, rbx
0x180094304  jz      loc_180094B9A
0x18009430a  test    byte ptr [rax+1Ch], 8
0x18009430e  jz      loc_180094B9A
0x180094314  cmp     byte ptr [rax+19h], 2
0x180094318  jb      loc_180094B9A
0x18009431e  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180094324  mov     edx, 28h ; '('
0x180094329  lea     rcx, aSpcodecapiSetv_11; "spCodecApi->SetValue( CODECAPI_AVLowLat"...
0x180094330  jmp     loc_180094B77
0x180094335  mov     rcx, [rbp+arg_0]
0x180094339  lea     rdx, _GUID_3daf6f66_a6a7_45e0_a8e5_f2743f46a3a2
0x180094340  mov     rax, [rcx]
0x180094343  mov     rax, [rax+18h]
0x180094347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009434c  mov     esi, 13h
0x180094351  test    eax, eax
0x180094353  jnz     short loc_1800943C4
0x180094355  movzx   eax, byte ptr [rbx+8Ch]
0x18009435c  lea     r8, [rbp+var_20]
0x180094360  mov     rcx, [rbp+arg_0]
0x180094364  lea     rdx, _GUID_3daf6f66_a6a7_45e0_a8e5_f2743f46a3a2
0x18009436b  mov     dword ptr [rbp+var_20+8], eax
0x18009436e  mov     word ptr [rbp+var_20], si
0x180094372  mov     rax, [rcx]
0x180094375  mov     rax, [rax+48h]
0x180094379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009437e  mov     edi, eax
0x180094380  test    eax, eax
0x180094382  jns     short loc_1800943C4
0x180094384  mov     rax, cs:WPP_GLOBAL_Control
0x18009438b  lea     rbx, WPP_GLOBAL_Control
0x180094392  cmp     rax, rbx
0x180094395  jz      loc_180094B9A
0x18009439b  test    byte ptr [rax+1Ch], 8
0x18009439f  jz      loc_180094B9A
0x1800943a5  cmp     byte ptr [rax+19h], 2
0x1800943a9  jb      loc_180094B9A
0x1800943af  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800943b5  lea     edx, [rsi+16h]
0x1800943b8  lea     rcx, aSpcodecapiSetv_12; "spCodecApi->SetValue( CODECAPI_AVEncVid"...
0x1800943bf  jmp     loc_180094B77
0x1800943c4  mov     rcx, [rbp+arg_0]
0x1800943c8  lea     rdx, _GUID_0ee22c6a_a37c_4568_b5f1_9d4c2b3ab886
0x1800943cf  mov     rax, [rcx]
0x1800943d2  mov     rax, [rax+18h]
0x1800943d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800943db  test    eax, eax
0x1800943dd  jnz     short loc_180094450
0x1800943df  movzx   eax, byte ptr [rbx+8Dh]
0x1800943e6  lea     r8, [rbp+var_20]
0x1800943ea  mov     rcx, [rbp+arg_0]
0x1800943ee  lea     rdx, _GUID_0ee22c6a_a37c_4568_b5f1_9d4c2b3ab886
0x1800943f5  mov     dword ptr [rbp+var_20+8], eax
0x1800943f8  mov     word ptr [rbp+var_20], si
0x1800943fc  mov     rax, [rcx]
0x1800943ff  mov     rax, [rax+48h]
0x180094403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094408  mov     edi, eax
0x18009440a  test    eax, eax
0x18009440c  jns     short loc_180094450
0x18009440e  mov     rax, cs:WPP_GLOBAL_Control
0x180094415  lea     rbx, WPP_GLOBAL_Control
0x18009441c  cmp     rax, rbx
0x18009441f  jz      loc_180094B9A
0x180094425  test    byte ptr [rax+1Ch], 8
0x180094429  jz      loc_180094B9A
0x18009442f  cmp     byte ptr [rax+19h], 2
0x180094433  jb      loc_180094B9A
0x180094439  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18009443f  mov     edx, 2Ah ; '*'
0x180094444  lea     rcx, aSpcodecapiSetv_0; "spCodecApi->SetValue( CODECAPI_AVEncVid"...
0x18009444b  jmp     loc_180094B77
0x180094450  cmp     dword ptr [rbx+0D8h], 0
0x180094457  jz      loc_1800944E8
0x18009445d  mov     rcx, [rbp+arg_0]
0x180094461  lea     rdx, _GUID_95f31b26_95a4_41aa_9303_246a7fc6eef1
0x180094468  mov     rax, [rcx]
0x18009446b  mov     rax, [rax+18h]
0x18009446f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094474  test    eax, eax
0x180094476  jnz     short loc_1800944E8
0x180094478  mov     eax, [rbx+0D8h]
0x18009447e  lea     r8, [rbp+var_20]
0x180094482  mov     rcx, [rbp+arg_0]
0x180094486  lea     rdx, _GUID_95f31b26_95a4_41aa_9303_246a7fc6eef1
0x18009448d  mov     dword ptr [rbp+var_20+8], eax
0x180094490  mov     word ptr [rbp+var_20], si
0x180094494  mov     rax, [rcx]
0x180094497  mov     rax, [rax+48h]
0x18009449b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800944a0  mov     edi, eax
0x1800944a2  test    eax, eax
0x1800944a4  jns     short loc_1800944E8
0x1800944a6  mov     rax, cs:WPP_GLOBAL_Control
0x1800944ad  lea     rbx, WPP_GLOBAL_Control
0x1800944b4  cmp     rax, rbx
0x1800944b7  jz      loc_180094B9A
0x1800944bd  test    byte ptr [rax+1Ch], 8
0x1800944c1  jz      loc_180094B9A
0x1800944c7  cmp     byte ptr [rax+19h], 2
0x1800944cb  jb      loc_180094B9A
0x1800944d1  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800944d7  mov     edx, 2Bh ; '+'
0x1800944dc  lea     rcx, aSetvalueCodeca; "SetValue CODECAPI_AVEncMPVGOPSize faile"...
0x1800944e3  jmp     loc_180094B77
0x1800944e8  mov     rcx, [rbp+arg_0]
0x1800944ec  lea     rdx, _GUID_1c0608e9_370c_4710_8a58_cb6181c42423
0x1800944f3  mov     rax, [rcx]
0x1800944f6  mov     rax, [rax+18h]
0x1800944fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800944ff  test    eax, eax
0x180094501  jnz     short loc_180094571
0x180094503  mov     rcx, [rbp+arg_0]
0x180094507  lea     r8, [rbp+var_20]
0x18009450b  mov     word ptr [rbp+var_20], si
0x18009450f  lea     rdx, _GUID_1c0608e9_370c_4710_8a58_cb6181c42423
0x180094516  mov     dword ptr [rbp+var_20+8], 3
0x18009451d  mov     rax, [rcx]
0x180094520  mov     rax, [rax+48h]
0x180094524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094529  mov     edi, eax
0x18009452b  test    eax, eax
0x18009452d  jns     short loc_180094571
0x18009452f  mov     rax, cs:WPP_GLOBAL_Control
0x180094536  lea     rbx, WPP_GLOBAL_Control
0x18009453d  cmp     rax, rbx
0x180094540  jz      loc_180094B9A
0x180094546  test    byte ptr [rax+1Ch], 8
0x18009454a  jz      loc_180094B9A
0x180094550  cmp     byte ptr [rax+19h], 2
0x180094554  jb      loc_180094B9A
0x18009455a  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180094560  mov     edx, 2Ch ; ','
0x180094565  lea     rcx, aSpcodecapiSetv_19; "spCodecApi->SetValue( CODECAPI_AVEncCom"...
0x18009456c  jmp     loc_180094B77
0x180094571  mov     rcx, [rbp+arg_0]
0x180094575  lea     rdx, _GUID_98332df8_03cd_476b_89fa_3f9e442dec9f
0x18009457c  mov     rax, [rcx]
0x18009457f  mov     rax, [rax+18h]
0x180094583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094588  test    eax, eax
0x18009458a  jnz     short loc_1800945FA
0x18009458c  mov     rcx, [rbp+arg_0]
0x180094590  lea     r8, [rbp+var_20]
0x180094594  mov     word ptr [rbp+var_20], si
0x180094598  lea     rdx, _GUID_98332df8_03cd_476b_89fa_3f9e442dec9f
0x18009459f  mov     dword ptr [rbp+var_20+8], 1Eh
0x1800945a6  mov     rax, [rcx]
0x1800945a9  mov     rax, [rax+48h]
0x1800945ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800945b2  mov     edi, eax
0x1800945b4  test    eax, eax
0x1800945b6  jns     short loc_1800945FA
0x1800945b8  mov     rax, cs:WPP_GLOBAL_Control
0x1800945bf  lea     rbx, WPP_GLOBAL_Control
0x1800945c6  cmp     rax, rbx
0x1800945c9  jz      loc_180094B9A
0x1800945cf  test    byte ptr [rax+1Ch], 8
0x1800945d3  jz      loc_180094B9A
0x1800945d9  cmp     byte ptr [rax+19h], 2
0x1800945dd  jb      loc_180094B9A
0x1800945e3  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1800945e9  mov     edx, 2Dh ; '-'
0x1800945ee  lea     rcx, aSpcodecapiSetv_9; "spCodecApi->SetValue(CODECAPI_AVEncComm"...
0x1800945f5  jmp     loc_180094B77
0x1800945fa  mov     rcx, [rbp+arg_0]
0x1800945fe  lea     rdx, _GUID_8acb8fdd_5e0c_4c66_8729_b8f629ab04fb
0x180094605  mov     rax, [rcx]
0x180094608  mov     rax, [rax+18h]
0x18009460c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094611  mov     r14d, 1
0x180094617  test    eax, eax
0x180094619  jnz     short loc_180094685
0x18009461b  mov     rcx, [rbp+arg_0]
0x18009461f  lea     r8, [rbp+var_20]
0x180094623  mov     word ptr [rbp+var_20], si
0x180094627  lea     rdx, _GUID_8acb8fdd_5e0c_4c66_8729_b8f629ab04fb
0x18009462e  mov     dword ptr [rbp+var_20+8], r14d
0x180094632  mov     rax, [rcx]
0x180094635  mov     rax, [rax+48h]
0x180094639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009463e  mov     edi, eax
0x180094640  test    eax, eax
0x180094642  jns     short loc_180094685
0x180094644  mov     rax, cs:WPP_GLOBAL_Control
0x18009464b  lea     rbx, WPP_GLOBAL_Control
0x180094652  cmp     rax, rbx
0x180094655  jz      loc_180094B9A
0x18009465b  test    byte ptr [rax+1Ch], 8
  ... truncated ...
```
