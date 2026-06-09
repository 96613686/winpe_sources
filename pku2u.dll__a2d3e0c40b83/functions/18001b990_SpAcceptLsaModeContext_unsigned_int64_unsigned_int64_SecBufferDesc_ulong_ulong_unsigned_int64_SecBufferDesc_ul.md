# SpAcceptLsaModeContext(unsigned __int64,unsigned __int64,_SecBufferDesc *,ulong,ulong,unsigned __int64 *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *,uchar *,_SecBuffer *)

- ea: `0x18001b990`
- end: `0x18001cc7e`
- name: `?SpAcceptLsaModeContext@@YAJ_K0PEAU_SecBufferDesc@@KKPEA_K1PEAKPEAT_LARGE_INTEGER@@PEAEPEAU_SecBuffer@@@Z`
- size: `4846`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, struct _SecBufferDesc *, int, unsigned int, struct ASN1decoding_s *, struct _SecBufferDesc *, unsigned int *Size, PLARGE_INTEGER LocalTime, unsigned __int8 *, struct _SecBuffer *Src)`
- caller_count: `0`
- callee_count: `26`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001910`
- `0x180001bf0`
- `0x180005300`
- `0x180005840`
- `0x18000d220`
- `0x18000f100`
- `0x180011ec0`
- `0x1800138c0`
- `0x180017a60`
- `0x18001b990`
- `0x18001e510`
- `0x180023cb8`
- `0x180023ce0`
- `0x180023d9c`
- `0x180023e30`
- `0x180023e70`
- `0x18002adb0`
- `0x18002b0d8`
- `0x18002b454`
- `0x18002b744`
- `0x18002e8b8`
- `0x180032830`
- `0x180035dc0`
- `0x18003754c`
- `0x180044f8c`
- `0x180046010`

## import_xrefs

- `MSASN1!ASN1_CloseDecoder` at `0x18001cb66`
- `MSASN1!ASN1_CloseDecoder` at `0x18001cba4`
- `MSASN1!ASN1_CloseDecoder` at `0x18001cbe2`
- `MSASN1!ASN1_CloseDecoder` at `0x18001cb66`
- `MSASN1!ASN1_CloseDecoder` at `0x18001cba4`
- `MSASN1!ASN1_CloseDecoder` at `0x18001cbe2`
- `MSASN1!ASN1_FreeDecoded` at `0x18001cb57`
- `MSASN1!ASN1_FreeDecoded` at `0x18001cb95`
- `MSASN1!ASN1_FreeDecoded` at `0x18001cbd3`
- `MSASN1!ASN1_FreeDecoded` at `0x18001cb57`
- `MSASN1!ASN1_FreeDecoded` at `0x18001cb95`
- `MSASN1!ASN1_FreeDecoded` at `0x18001cbd3`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18001c50a`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18001c96a`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18001c50a`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18001c96a`

## string_xrefs

- `0x18001bcf6`: `onecore\ds\security\protocols\pku2u\ctxtapi.cxx`
- `0x18001be77`: `onecore\ds\security\protocols\pku2u\ctxtapi.cxx`
- `0x18001c0e3`: `onecore\ds\security\protocols\pku2u\ctxtapi.cxx`
- `0x18001c745`: `onecore\ds\security\protocols\pku2u\ctxtapi.cxx`

## pseudocode

```c
__int64 __fastcall SpAcceptLsaModeContext(
        __int64 a1,
        unsigned __int64 a2,
        struct _SecBufferDesc *a3,
        int a4,
        unsigned int a5,
        struct ASN1decoding_s *a6,
        struct _SecBufferDesc *a7,
        unsigned int *Size,
        PLARGE_INTEGER LocalTime,
        unsigned __int8 *a10,
        struct _SecBuffer *Src)
{
  struct _SecBufferDesc *v11; // rbx
  union _LARGE_INTEGER *v13; // rcx
  struct _SecBuffer *v14; // rax
  int v15; // r10d
  int v16; // eax
  __int64 v17; // r13
  __int64 v18; // r15
  __int64 v19; // r12
  unsigned int *p_cBuffers; // r14
  unsigned int i; // esi
  __int64 v22; // rbx
  int v23; // eax
  int v24; // eax
  struct _SEC_CHANNEL_BINDINGS *pvBuffer; // r12
  PSecBuffer v26; // r9
  unsigned int v27; // ecx
  __int64 v28; // rbx
  struct _SecBuffer *v29; // r15
  struct _SecBufferDesc *v30; // r14
  unsigned int cBuffers; // edx
  PSecBuffer v32; // r8
  int v33; // ecx
  struct _SecBuffer *v34; // rbx
  _QWORD *v35; // rcx
  int v36; // edx
  int v37; // r9d
  _QWORD *v38; // rcx
  __int64 v39; // rdx
  PSecBuffer pBuffers; // r8
  int v41; // ecx
  struct _SecBuffer *v42; // rbx
  PSecBuffer v43; // rax
  unsigned __int64 cbBuffer; // rdx
  __int64 cbInitiatorLength; // r8
  __int64 cbAcceptorLength; // r9
  __int64 cbApplicationDataLength; // r10
  unsigned __int64 v48; // rcx
  unsigned __int64 dwInitiatorOffset; // rax
  unsigned __int64 dwAcceptorOffset; // rax
  unsigned __int64 dwApplicationDataOffset; // rax
  _DWORD *v52; // rbx
  _DWORD *v53; // rsi
  _QWORD *v54; // rcx
  __int64 v55; // rdx
  unsigned int v56; // eax
  int v57; // ecx
  void (*v58)(void); // rax
  struct KERB_KDC_REQUEST_BODY **v59; // rsi
  __int64 v60; // r8
  int v61; // eax
  int v62; // ecx
  unsigned int *v63; // r12
  __int64 v64; // rdx
  unsigned __int8 *v65; // rdx
  unsigned int v66; // eax
  int v67; // eax
  size_t v68; // r14
  struct _SecBuffer *v69; // rsi
  unsigned __int64 v70; // rsi
  unsigned __int64 v71; // rbx
  unsigned int v72; // eax
  union _LARGE_INTEGER *v73; // rdx
  int v74; // eax
  unsigned int v75; // ecx
  int v76; // eax
  unsigned int *v77; // rsi
  union _LARGE_INTEGER *v78; // rdx
  _DWORD *v79; // r9
  volatile signed __int32 *v80; // rax
  volatile signed __int32 *v81; // rcx
  void (*v82)(void); // rax
  struct KERB_AP_REQUEST *v83; // rbx
  struct KERB_AUTHENTICATOR *v84; // rbx
  struct KERB_ENCRYPTED_TICKET *v85; // rbx
  void (*v86)(void); // rax
  char v88; // [rsp+30h] [rbp-B9h]
  int v89; // [rsp+68h] [rbp-81h] BYREF
  int v90; // [rsp+6Ch] [rbp-7Dh] BYREF
  unsigned __int8 *v91; // [rsp+70h] [rbp-79h] BYREF
  volatile signed __int32 *v92; // [rsp+78h] [rbp-71h]
  volatile signed __int32 *v93; // [rsp+80h] [rbp-69h]
  _DWORD *v94; // [rsp+88h] [rbp-61h]
  _DWORD *v95; // [rsp+90h] [rbp-59h]
  struct KERB_AUTHENTICATOR *v96; // [rsp+98h] [rbp-51h] BYREF
  struct KERB_ENCRYPTED_TICKET *v97; // [rsp+A0h] [rbp-49h] BYREF
  struct KERB_AP_REQUEST *v98; // [rsp+A8h] [rbp-41h] BYREF
  __int128 v99; // [rsp+B0h] [rbp-39h] BYREF
  __int64 v100; // [rsp+C0h] [rbp-29h]
  union _LARGE_INTEGER v101; // [rsp+C8h] [rbp-21h] BYREF
  size_t v102; // [rsp+120h] [rbp+37h] BYREF
  struct _SecBufferDesc *v103; // [rsp+128h] [rbp+3Fh]
  int v104; // [rsp+130h] [rbp+47h]

  v104 = a4;
  v103 = a3;
  v11 = a3;
  v89 = 0;
  v100 = 0;
  v91 = 0;
  LODWORD(v102) = 0;
  v90 = 0;
  v98 = 0;
  v97 = 0;
  v96 = 0;
  v99 = 0;
  v101.QuadPart = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, a2);
  v13 = LocalTime;
  *Size = 0;
  *(_QWORD *)a6 = a2;
  *v13 = Pku2uGlobalHasNeverTime;
  *a10 = 0;
  v14 = Src;
  Src->pvBuffer = 0;
  v14->cbBuffer = 0;
  if ( !a2 )
  {
    v15 = -1073741816;
LABEL_155:
    v89 = v15;
LABEL_156:
    *(_DWORD *)(a2 + 68) = 7;
    goto LABEL_157;
  }
  v93 = (volatile signed __int32 *)(a2 + 8);
  _InterlockedIncrement((volatile signed __int32 *)(a2 + 8));
  v92 = (volatile signed __int32 *)(a2 + 320);
  if ( _InterlockedIncrement((volatile signed __int32 *)(a2 + 320)) > 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
        a2,
        *(_DWORD *)(a2 + 320));
      v15 = -2146893054;
      goto LABEL_155;
    }
LABEL_15:
    v15 = -2146893054;
    goto LABEL_155;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NegoLateFallback>::GetImpl'::`2'::impl) )
  {
    v16 = *(_DWORD *)(a2 + 40);
    if ( (v16 & 2) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, a2);
      goto LABEL_15;
    }
    *(_DWORD *)(a2 + 40) = v16 | 4;
  }
  v95 = 0;
  v17 = 0;
  v94 = 0;
  v18 = 0;
  v19 = 0;
  p_cBuffers = &v11->cBuffers;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NegoLateFallback>::GetImpl'::`2'::impl) )
  {
    for ( i = 0; i < *p_cBuffers; ++i )
    {
      v22 = (__int64)&v11->pBuffers[i];
      v23 = *(_DWORD *)(v22 + 4) & 0xFFFFFFF;
      switch ( v23 )
      {
        case 2:
          if ( v17 )
          {
            v38 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v39 = 54;
              goto LABEL_61;
            }
            goto LABEL_62;
          }
          v24 = ((__int64 (__fastcall *)(__int64, __int64))Pku2uGlobalLsaFunctions->MapBuffer)(v22, v22);
          v89 = v24;
          v15 = v24;
          if ( v24 < 0 )
          {
            v35 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v36 = 55;
              v88 = 38;
              goto LABEL_44;
            }
            goto LABEL_252;
          }
          v17 = v22;
          break;
        case 11:
          if ( v18 )
          {
            v38 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v39 = 56;
              goto LABEL_61;
            }
            goto LABEL_62;
          }
          v24 = ((__int64 (__fastcall *)(__int64, __int64))Pku2uGlobalLsaFunctions->MapBuffer)(v22, v22);
          v89 = v24;
          v15 = v24;
          if ( v24 < 0 )
          {
            v35 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v36 = 57;
              v88 = 60;
              goto LABEL_44;
            }
            goto LABEL_252;
          }
          v18 = v22;
          v95 = (_DWORD *)v22;
          break;
        case 12:
          if ( v19 )
          {
            v38 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v39 = 58;
LABEL_61:
              WPP_SF_(v38[2], v39, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids);
            }
LABEL_62:
            v15 = -2146893048;
            goto LABEL_155;
          }
          v24 = ((__int64 (__fastcall *)(__int64, __int64))Pku2uGlobalLsaFunctions->MapBuffer)(v22, v22);
          v89 = v24;
          v15 = v24;
          if ( v24 < 0 )
          {
            v35 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v36 = 59;
              v88 = 82;
              goto LABEL_44;
            }
            goto LABEL_252;
          }
          v19 = v22;
          v94 = (_DWORD *)v22;
          break;
      }
      v11 = v103;
    }
  }
  else
  {
    if ( !*p_cBuffers )
      goto LABEL_32;
    pBuffers = v11->pBuffers;
    v41 = 0;
    while ( 1 )
    {
      v42 = &pBuffers[v41];
      if ( (v42->BufferType & 0xFFFFFFF) == 2 )
        break;
      if ( ++v41 >= *p_cBuffers )
      {
        v11 = v103;
        goto LABEL_32;
      }
    }
    v89 = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))Pku2uGlobalLsaFunctions->MapBuffer)(
            &pBuffers[v41],
            &pBuffers[v41]);
    v15 = v89;
    if ( v89 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_252;
      WPP_SF_dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        (unsigned int)&WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
        v89,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\ctxtapi.cxx",
        102);
      goto LABEL_251;
    }
    v17 = (__int64)v42;
    v11 = v103;
  }
LABEL_32:
  pvBuffer = 0;
  if ( *p_cBuffers )
  {
    v26 = v11->pBuffers;
    v27 = 0;
    while ( 1 )
    {
      v28 = v27;
      if ( (v26[v27].BufferType & 0xFFFFFFF) == 0xE )
        break;
      if ( ++v27 >= *p_cBuffers )
        goto LABEL_36;
    }
    v89 = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))Pku2uGlobalLsaFunctions->MapBuffer)(
            &v26[v27],
            &v26[v27]);
    v15 = v89;
    if ( v89 < 0 )
      goto LABEL_252;
    v43 = v103->pBuffers;
    pvBuffer = (struct _SEC_CHANNEL_BINDINGS *)v43[v28].pvBuffer;
    if ( !pvBuffer )
      goto LABEL_84;
    cbBuffer = v43[v28].cbBuffer;
    if ( (unsigned int)cbBuffer < 0x20
      || (cbInitiatorLength = pvBuffer->cbInitiatorLength,
          cbAcceptorLength = pvBuffer->cbAcceptorLength,
          cbApplicationDataLength = pvBuffer->cbApplicationDataLength,
          v48 = cbApplicationDataLength + cbAcceptorLength + cbInitiatorLength + 32,
          v48 > cbBuffer)
      || (dwInitiatorOffset = pvBuffer->dwInitiatorOffset, dwInitiatorOffset + cbInitiatorLength > v48)
      || dwInitiatorOffset + cbInitiatorLength < dwInitiatorOffset
      || (dwAcceptorOffset = pvBuffer->dwAcceptorOffset, dwAcceptorOffset + cbAcceptorLength > v48)
      || dwAcceptorOffset + cbAcceptorLength < dwAcceptorOffset
      || (dwApplicationDataOffset = pvBuffer->dwApplicationDataOffset,
          dwApplicationDataOffset + cbApplicationDataLength > v48)
      || dwApplicationDataOffset + cbApplicationDataLength < dwApplicationDataOffset )
    {
LABEL_84:
      v15 = -1073741811;
      v89 = -1073741811;
      goto LABEL_252;
    }
    v89 = 0;
  }
LABEL_36:
  v29 = 0;
  v30 = a7;
  cBuffers = a7->cBuffers;
  if ( cBuffers )
  {
    v32 = a7->pBuffers;
    v33 = 0;
    while ( 1 )
    {
      v34 = &v32[v33];
      if ( (v34->BufferType & 0xFFFFFFF) == 2 )
        break;
      if ( ++v33 >= cBuffers )
        goto LABEL_90;
    }
    v24 = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))Pku2uGlobalLsaFunctions->MapBuffer)(
            &v32[v33],
            &v32[v33]);
    v89 = v24;
    v15 = v24;
    if ( v24 < 0 )
    {
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_252;
      v36 = 61;
      v88 = -98;
LABEL_44:
      v37 = v24;
      goto LABEL_45;
    }
    v29 = v34;
  }
LABEL_90:
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NegoLateFallback>::GetImpl'::`2'::impl) )
  {
    if ( !v17 || !*(_DWORD *)v17 )
    {
      v15 = -2146893048;
      v89 = -2146893048;
      v54 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_156;
      v55 = 63;
LABEL_249:
      v79 = (_DWORD *)v17;
LABEL_250:
      WPP_SF_q(v54[2], v55, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, v79);
      goto LABEL_251;
    }
    goto LABEL_102;
  }
  if ( v17 && *(_DWORD *)v17 )
  {
LABEL_102:
    v52 = v95;
LABEL_103:
    v53 = v94;
    goto LABEL_104;
  }
  v52 = v95;
  if ( v95 && *v95 )
    goto LABEL_103;
  v53 = v94;
  if ( !v94 || !*v94 )
  {
    v15 = -2146893048;
    v89 = -2146893048;
    v54 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_156;
    v55 = 62;
    goto LABEL_249;
  }
LABEL_104:
  v56 = *(_DWORD *)(a2 + 68);
  if ( v56 > 5 || (v57 = 37, !_bittest(&v57, v56)) )
  {
    if ( v56 == 4 )
    {
      v59 = (struct KERB_KDC_REQUEST_BODY **)(v17 + 8);
      v89 = Pku2uVerifyApReply((struct _PKU2U_CONTEXT *)a2, *(unsigned __int8 **)(v17 + 8), *(_DWORD *)v17);
      v15 = v89;
      if ( v89 == 280 )
      {
        v15 = -1073741670;
        v89 = -1073741670;
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_156;
        v36 = 69;
        v88 = 40;
        v37 = -1073741670;
        goto LABEL_45;
      }
      if ( v89 < 0 )
      {
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_252;
        v36 = 70;
        v88 = 45;
        v37 = v89;
        goto LABEL_45;
      }
      *(_DWORD *)(a2 + 68) = 6;
    }
    else
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NegoLateFallback>::GetImpl'::`2'::impl)
        || *(_DWORD *)(a2 + 68) != 6 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            73,
            &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
            *(unsigned int *)(a2 + 68));
        v15 = -1073741715;
        goto LABEL_155;
      }
      if ( !v52 || !*v52 )
      {
        v15 = -2146893048;
        v89 = -2146893048;
        v54 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_156;
        v55 = 71;
        v79 = v52;
        goto LABEL_250;
      }
      if ( !v53 || !*v53 )
      {
        v15 = -2146893048;
        v89 = -2146893048;
        v54 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_156;
        v55 = 72;
        v79 = v53;
        goto LABEL_250;
      }
      v59 = (struct KERB_KDC_REQUEST_BODY **)(v17 + 8);
    }
    goto LABEL_197;
  }
  if ( *(_QWORD *)(a2 + 264) )
  {
    if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
      v58 = *(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 392LL);
    else
      v58 = *(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 31) + 8LL);
    v58();
  }
  v59 = (struct KERB_KDC_REQUEST_BODY **)(v17 + 8);
  *(_OWORD *)(a2 + 248) = 0;
  *(_QWORD *)(a2 + 264) = 0;
  v89 = Pku2uVerifyApRequest(
          (struct _PKU2U_CONTEXT *)a2,
          *(unsigned __int8 **)(v17 + 8),
          *(_DWORD *)v17,
          &v98,
          &v97,
          &v96,
          (struct KERB_ENCRYPTION_KEY *)(a2 + 248),
          (struct KERB_ENCRYPTION_KEY *)&v99,
          &v90,
          pvBuffer);
  v15 = v89;
  if ( v89 == 280 )
  {
    v61 = Pku2uHandlePeer2PeerAsRequest(
            (struct _PKU2U_CONTEXT *)a2,
            *v59,
            *(_DWORD *)v17,
            &v90,
            &v91,
            (unsigned int *)&v102);
    v89 = v61;
    v15 = v61;
    if ( v61 == 280 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          64,
          (unsigned int)&WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
          280,
          (__int64)"onecore\\ds\\security\\protocols\\pku2u\\ctxtapi.cxx",
          216);
      v15 = -1073741670;
      goto LABEL_155;
    }
    if ( v61 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          65,
          (unsigned int)&WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
          v61,
          (__int64)"onecore\\ds\\security\\protocols\\pku2u\\ctxtapi.cxx",
          222);
LABEL_126:
        v15 = v89;
        goto LABEL_127;
      }
      goto LABEL_127;
    }
    v30 = a7;
    *(_DWORD *)(a2 + 68) = 2;
    v89 = 590610;
LABEL_198:
    if ( v97 && (*(_BYTE *)v97 & 0x20) != 0 )
      KerbGetClientNetbiosAddress((struct _UNICODE_STRING *)(a2 + 328), *((struct PKERB_HOST_ADDRESSES **)v97 + 19));
    if ( v17 )
    {
      if ( *(_DWORD *)v17 )
      {
        v74 = Pku2uSaveSSPIMessage((unsigned __int8 *)*v59, *(_DWORD *)v17, (struct _PKU2U_CONTEXT *)a2);
        v15 = v74;
        if ( v74 < 0 )
        {
          v89 = v74;
          goto LABEL_252;
        }
      }
    }
    v75 = v102;
    if ( (_DWORD)v102 )
    {
      v76 = Pku2uSaveSSPIMessage(v91, v102, (struct _PKU2U_CONTEXT *)a2);
      v15 = v76;
      if ( v76 < 0 )
      {
        v89 = v76;
        goto LABEL_252;
      }
      v75 = v102;
    }
    v77 = Size;
    *Size |= *(_DWORD *)(a2 + 64);
    if ( v75 )
    {
      if ( !v29 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            74,
            (unsigned int)&WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
            (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\ctxtapi.cxx",
            126);
        v15 = -1073741811;
        goto LABEL_155;
      }
      if ( (v104 & 0x100) != 0 )
      {
        v29->pvBuffer = v91;
        *v77 |= 0x100u;
        v91 = 0;
        v29->cbBuffer = v102;
      }
      else
      {
        if ( v29->cbBuffer < v75 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_ddsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              75,
              (unsigned int)&WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
              v29->cbBuffer,
              v75,
              (__int64)"onecore\\ds\\security\\protocols\\pku2u\\ctxtapi.cxx",
              140);
            v75 = v102;
          }
          v29->cbBuffer = v75;
          goto LABEL_154;
        }
        memcpy_0(v29->pvBuffer, v91, v75);
        *v77 &= ~0x100u;
        v29->cbBuffer = v102;
      }
    }
    else if ( v29 )
    {
      v29->cbBuffer = 0;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NegoLateFallback>::GetImpl'::`2'::impl) )
    {
      if ( v89 )
      {
LABEL_235:
        v78 = LocalTime;
        *(_QWORD *)a6 = a2;
        RtlSystemTimeToLocalTime((PLARGE_INTEGER)(a2 + 48), v78);
        goto LABEL_251;
      }
      v89 = Pku2uGenerateOrVerifyMechlistMIC((struct _PKU2U_CONTEXT *)a2, v103, v30);
      v15 = v89;
      if ( v89 < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_252;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          76,
          &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
          (unsigned int)v89);
        goto LABEL_251;
      }
    }
    else
    {
      v15 = v89;
    }
    if ( !v15 )
    {
      v89 = Pku2uMapContext((struct _PKU2U_CONTEXT *)a2, a10, Src);
      v15 = v89;
      if ( v89 < 0 )
        goto LABEL_252;
      v89 = 0;
    }
    goto LABEL_235;
  }
  if ( v89 >= 0 )
  {
    v89 = Pku2uCreateTokenFromTicket(
            v97,
            v96,
            *(_DWORD *)(a2 + 64),
            (struct KERB_ENCRYPTION_KEY *)(a2 + 248),
            (struct KERB_ENCRYPTION_KEY *)&v99,
            (struct _LUID *)(a2 + 352),
            (void **)(a2 + 344),
            (void **)(a2 + 272),
            (struct _UNICODE_STRING *)(a2 + 184),
            &v101);
    v15 = v89;
    if ( v89 < 0 )
    {
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_252;
      v36 = 67;
      v88 = -3;
      v37 = v89;
LABEL_45:
      WPP_SF_dsd(
        v35[2],
        v36,
        (unsigned int)&WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
        v37,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\ctxtapi.cxx",
        v88);
      goto LABEL_251;
    }
    v89 = Pku2uBuildApReply((struct _PKU2U_CONTEXT *)a2, v96, v98, &v91, (unsigned int *)&v102);
    v15 = v89;
    if ( v89 < 0 )
    {
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_252;
      v36 = 68;
      v88 = 10;
      v37 = v89;
      goto LABEL_45;
    }
    v30 = a7;
    if ( (*(_DWORD *)(a2 + 64) & 0x200) != 0 )
    {
      v89 = 590610;
      *(_DWORD *)(a2 + 68) = 4;
      goto LABEL_198;
    }
    *(_DWORD *)(a2 + 68) = 6;
LABEL_197:
    v89 = 0;
    goto LABEL_198;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_Ddsd(*((_QWORD *)WPP_GLOBAL_Control + 2), &WPP_GLOBAL_Control, v60, (unsigned int)v89, v90);
    goto LABEL_126;
  }
LABEL_127:
  if ( v15 >= 0 )
  {
    v15 = -1073741715;
    v89 = -1073741715;
  }
  if ( !v29 )
    goto LABEL_252;
  v62 = v90;
  v63 = Size;
  if ( !v90 && (v104 & 0x8000) == 0 && (*Size & 0x4000) == 0 )
    goto LABEL_252;
  Src = 0;
  LODWORD(Size) = 0;
  if ( (unsigned int)v90 > 0x29 )
    goto LABEL_252;
  v64 = 0x22300000000LL;
  if ( !_bittest64(&v64, (unsigned int)v90) )
    goto LABEL_252;
  if ( v90 )
  {
    v65 = 0;
    v66 = 0;
  }
  else
  {
    v62 = 60;
    v65 = (unsigned __int8 *)&v89;
    v90 = 60;
    v66 = 4;
  }
  if ( (int)Pku2uBuildGssErrorMessage(
              v62,
              v65,
              v66,
              (struct _PKU2U_CONTEXT *)a2,
              (unsigned int *)&Size,
              (unsigned __int8 **)&Src) < 0 )
  {
LABEL_251:
    v15 = v89;
    goto LABEL_252;
  }
  if ( *(_DWORD *)v17 )
  {
    v67 = Pku2uSaveSSPIMessage((unsigned __int8 *)*v59, *(_DWORD *)v17, (struct _PKU2U_CONTEXT *)a2);
    v15 = v67;
    if ( v67 < 0 )
    {
      v89 = v67;
      goto LABEL_252;
    }
  }
  v68 = (unsigned int)Size;
  v69 = Src;
  if ( !(_DWORD)Size
    || (v89 = Pku2uSaveSSPIMessage((unsigned __int8 *)Src, (unsigned int)Size, (struct _PKU2U_CONTEXT *)a2),
        v15 = v89,
        v89 >= 0) )
  {
    *v63 |= WSTMapContextAttributes(*(unsigned int *)(a2 + 64));
    if ( (v104 & 0x100) != 0 )
    {
      v29->cbBuffer = v68;
      v29->pvBuffer = v69;
      v72 = *v63 | 0x100;
      goto LABEL_168;
    }
    if ( v29->cbBuffer < (unsigned int)v68 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_ddsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          77,
          (unsigned int)&WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
          v29->cbBuffer,
          v68,
          (__int64)"onecore\\ds\\security\\protocols\\pku2u\\ctxtapi.cxx",
          51);
      if ( v69 )
      {
        if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
          (*(void (__fastcall **)(struct _SecBuffer *))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 392LL))(v69);
        else
          (*(void (__fastcall **)(struct _SecBuffer *))(*((_QWORD *)Pku2uGlobalBaseSSP + 31) + 8LL))(v69);
      }
      v29->cbBuffer = v68;
LABEL_154:
      v15 = -1073741789;
      goto LABEL_155;
    }
    memcpy_0(v29->pvBuffer, v69, v68);
    v29->cbBuffer = v68;
    if ( v69 )
    {
      if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
      {
        (*(void (__fastcall **)(struct _SecBuffer *))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 392LL))(v69);
        v72 = *v63 & 0xFFFFFEFF;
LABEL_168:
        v73 = LocalTime;
        *v63 = v72 | 0x8000;
        *(_QWORD *)a6 = a2;
        RtlSystemTimeToLocalTime((PLARGE_INTEGER)(a2 + 48), v73);
        v15 = 590610;
        *(_DWORD *)(a2 + 68) = 5;
        v89 = 590610;
        goto LABEL_259;
      }
      (*(void (__fastcall **)(struct _SecBuffer *))(*((_QWORD *)Pku2uGlobalBaseSSP + 31) + 8LL))(v69);
    }
    v72 = *v63 & 0xFFFFFEFF;
    goto LABEL_168;
  }
LABEL_252:
  if ( v15 == 280 )
  {
    v15 = -1073741715;
    goto LABEL_155;
  }
  if ( !v15 )
  {
    v70 = a2 + 8;
    v71 = a2 + 320;
    goto LABEL_158;
  }
  if ( v15 != 590610 )
    goto LABEL_156;
LABEL_157:
  v70 = a2 + 8;
  v93 = (volatile signed __int32 *)(a2 + 8);
  v71 = a2 + 320;
  v92 = (volatile signed __int32 *)(a2 + 320);
  if ( v15 < 0 )
  {
LABEL_158:
    Src = *(struct _SecBuffer **)(a2 + 352);
    ((void (__fastcall *)(_QWORD, _QWORD, unsigned __int64, _QWORD, unsigned __int64, _QWORD, int, int, struct _TOKEN_SOURCE *, struct _SecBuffer **))Pku2uGlobalLsaFunctions->AuditLogonEx)(
      (unsigned int)v15,
      (unsigned int)v15,
      a2 + 184,
      0,
      a2 + 328,
      *(_QWORD *)(a2 + 344),
      3,
      2 - ((*(_DWORD *)(a2 + 64) & 0x20000) != 0),
      &Pku2uGlobalSource,
      &Src);
    v15 = v89;
    v92 = (volatile signed __int32 *)v71;
    v93 = (volatile signed __int32 *)v70;
  }
  if ( v15 == 590610 || v15 == -1073741789 )
  {
    v92 = (volatile signed __int32 *)v71;
    v93 = (volatile signed __int32 *)v70;
  }
  else
  {
    Pku2uLogProvider::LogServerContext((struct _PKU2U_CONTEXT *)a2, v15);
    v15 = v89;
  }
LABEL_259:
  v80 = v92;
  v81 = v93;
  *(_DWORD *)(a2 + 72) = v15;
  _InterlockedDecrement(v80);
  if ( _InterlockedExchangeAdd(v81, 0xFFFFFFFF) <= 1 )
    Pku2uFreeContext((struct _PKU2U_CONTEXT *)a2);
  if ( v91 )
  {
    if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
      v82 = *(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 392LL);
    else
      v82 = *(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 31) + 8LL);
    v82();
  }
  v83 = v98;
  if ( v98 )
  {
    Size = 0;
    if ( !(unsigned int)KerbInitAsn(0, (struct ASN1decoding_s **)&Size) )
    {
      ASN1_FreeDecoded(Size, v83, 35);
      if ( Size )
        ASN1_CloseDecoder();
    }
  }
  v84 = v96;
  if ( v96 )
  {
    a6 = 0;
    if ( !(unsigned int)KerbInitAsn(0, &a6) )
    {
      ASN1_FreeDecoded(a6, v84, 34);
      if ( a6 )
        ASN1_CloseDecoder();
    }
  }
  v85 = v97;
  if ( v97 )
  {
    LocalTime = 0;
    if ( !(unsigned int)KerbInitAsn(0, (struct ASN1decoding_s **)&LocalTime) )
    {
      ASN1_FreeDecoded(LocalTime, v85, 33);
      if ( LocalTime )
        ASN1_CloseDecoder();
    }
  }
  if ( v100 )
  {
    if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
      v86 = *(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 392LL);
    else
      v86 = *(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 31) + 8LL);
    v86();
  }
  v99 = 0;
  v100 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      78,
      &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
      (unsigned int)v89);
  return (unsigned int)v89;
}

```

## disassembly

```asm
0x18001b990  mov     rax, rsp
0x18001b993  mov     [rax+20h], r9d
0x18001b997  mov     [rax+18h], r8
0x18001b99b  push    rbp
0x18001b99c  lea     rbp, [rax-27h]
0x18001b9a0  sub     rsp, 100h
0x18001b9a7  mov     [rax+8], rbx
0x18001b9ab  xorps   xmm0, xmm0
0x18001b9ae  mov     [rax-10h], rsi
0x18001b9b2  mov     rbx, r8
0x18001b9b5  mov     [rax-18h], rdi
0x18001b9b9  mov     rdi, rdx
0x18001b9bc  mov     [rax-30h], r14
0x18001b9c0  xor     r14d, r14d
0x18001b9c3  xor     eax, eax
0x18001b9c5  mov     [rsp+100h+var_A0], r14d
0x18001b9ca  mov     [rbp+1Fh+var_48], rax
0x18001b9ce  mov     [rbp+1Fh+var_98], r14
0x18001b9d2  mov     dword ptr [rbp+1Fh+arg_8], r14d
0x18001b9d6  mov     [rbp+1Fh+var_9C], r14d
0x18001b9da  mov     [rbp+1Fh+var_60], r14
0x18001b9de  mov     [rbp+1Fh+var_68], r14
0x18001b9e2  mov     [rbp+1Fh+var_70], r14
0x18001b9e6  movups  [rbp+1Fh+var_58], xmm0
0x18001b9ea  mov     qword ptr [rbp+1Fh+var_40], r14
0x18001b9ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9f5  lea     rsi, WPP_GLOBAL_Control
0x18001b9fc  cmp     rcx, rsi
0x18001b9ff  jz      short loc_18001BA1F
0x18001ba01  test    byte ptr [rcx+1Ch], 8
0x18001ba05  jz      short loc_18001BA1F
0x18001ba07  mov     rcx, [rcx+10h]
0x18001ba0b  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18001ba12  mov     edx, 33h ; '3'
0x18001ba17  mov     r9, rdi
0x18001ba1a  call    WPP_SF_q
0x18001ba1f  mov     rax, [rbp+1Fh+Size]
0x18001ba23  mov     rcx, [rbp+1Fh+LocalTime]
0x18001ba27  mov     [rsp+100h+var_18], r12
0x18001ba2f  mov     [rsp+100h+var_20], r13
0x18001ba37  mov     [rax], r14d
0x18001ba3a  mov     rax, [rbp+1Fh+arg_28]
0x18001ba3e  mov     [rsp+100h+var_30], r15
0x18001ba46  mov     [rax], rdi
0x18001ba49  mov     rax, cs:?Pku2uGlobalHasNeverTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER Pku2uGlobalHasNeverTime
0x18001ba50  mov     [rcx], rax
0x18001ba53  mov     rax, [rbp+1Fh+arg_48]
0x18001ba57  mov     [rax], r14b
0x18001ba5a  mov     rax, [rbp+1Fh+Src]
0x18001ba5e  mov     [rax+8], r14
0x18001ba62  mov     [rax], r14d
0x18001ba65  test    rdi, rdi
0x18001ba68  jnz     short loc_18001BA75
0x18001ba6a  mov     r10d, 0C0000008h
0x18001ba70  jmp     loc_18001C3A7
0x18001ba75  lea     rax, [rdi+8]
0x18001ba79  mov     [rbp+1Fh+var_88], rax
0x18001ba7d  lock inc dword ptr [rax]
0x18001ba80  lea     r8, [rdi+140h]
0x18001ba87  mov     eax, 1
0x18001ba8c  mov     [rbp+1Fh+var_90], r8
0x18001ba90  lock xadd [r8], eax
0x18001ba95  inc     eax
0x18001ba97  cmp     eax, 1
0x18001ba9a  jle     short loc_18001BAD8
0x18001ba9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001baa3  cmp     rcx, rsi
0x18001baa6  jz      short loc_18001BB19
0x18001baa8  test    byte ptr [rcx+1Ch], 1
0x18001baac  jz      short loc_18001BB19
0x18001baae  mov     eax, [r8]
0x18001bab1  mov     edx, 34h ; '4'
0x18001bab6  mov     rcx, [rcx+10h]
0x18001baba  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18001bac1  mov     r9, rdi
0x18001bac4  mov     dword ptr [rsp+100h+var_E0], eax
0x18001bac8  call    WPP_SF_qD
0x18001bacd  mov     r10d, 80090302h
0x18001bad3  jmp     loc_18001C3A7
0x18001bad8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NegoLateFallback@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NegoLateFallback@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback> `wil::Feature<__WilFeatureTraits_Feature_NegoLateFallback>::GetImpl(void)'::`2'::impl
0x18001badf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NegoLateFallback@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::__private_IsEnabled(void)
0x18001bae4  test    al, al
0x18001bae6  jz      short loc_18001BB2A
0x18001bae8  mov     eax, [rdi+28h]
0x18001baeb  test    al, 2
0x18001baed  jz      short loc_18001BB24
0x18001baef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001baf6  cmp     rcx, rsi
0x18001baf9  jz      short loc_18001BB19
0x18001bafb  test    byte ptr [rcx+1Ch], 1
0x18001baff  jz      short loc_18001BB19
0x18001bb01  mov     rcx, [rcx+10h]
0x18001bb05  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18001bb0c  mov     edx, 35h ; '5'
0x18001bb11  mov     r9, rdi
0x18001bb14  call    WPP_SF_q
0x18001bb19  mov     r10d, 80090302h
0x18001bb1f  jmp     loc_18001C3A7
0x18001bb24  or      eax, 4
0x18001bb27  mov     [rdi+28h], eax
0x18001bb2a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NegoLateFallback@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NegoLateFallback@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback> `wil::Feature<__WilFeatureTraits_Feature_NegoLateFallback>::GetImpl(void)'::`2'::impl
0x18001bb31  mov     [rbp+1Fh+var_78], r14
0x18001bb35  mov     r13, r14
0x18001bb38  mov     [rbp+1Fh+var_80], r14
0x18001bb3c  mov     r15, r14
0x18001bb3f  mov     r12, r14
0x18001bb42  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NegoLateFallback@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::__private_IsEnabled(void)
0x18001bb47  lea     r14, [rbx+4]
0x18001bb4b  test    al, al
0x18001bb4d  jz      loc_18001BDFE
0x18001bb53  xor     esi, esi
0x18001bb55  cmp     [r14], esi
0x18001bb58  jbe     loc_18001BC3B
0x18001bb5e  xchg    ax, ax
0x18001bb60  mov     rbx, [rbx+8]
0x18001bb64  mov     ecx, esi
0x18001bb66  shl     rcx, 4
0x18001bb6a  add     rbx, rcx
0x18001bb6d  mov     eax, [rbx+4]
0x18001bb70  and     eax, 0FFFFFFFh
0x18001bb75  cmp     eax, 2
0x18001bb78  jnz     short loc_18001BBB0
0x18001bb7a  test    r13, r13
0x18001bb7d  jnz     loc_18001BD17
0x18001bb83  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18001bb8a  mov     rdx, rbx
0x18001bb8d  mov     rcx, rbx
0x18001bb90  mov     rax, [rax+98h]
0x18001bb97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb9c  mov     [rsp+100h+var_A0], eax
0x18001bba0  mov     r10d, eax
0x18001bba3  test    eax, eax
0x18001bba5  js      loc_18001BCC5
0x18001bbab  mov     r13, rbx
0x18001bbae  jmp     short loc_18001BC2C
0x18001bbb0  cmp     eax, 0Bh
0x18001bbb3  jnz     short loc_18001BBEF
0x18001bbb5  test    r15, r15
0x18001bbb8  jnz     loc_18001BD72
0x18001bbbe  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18001bbc5  mov     rdx, rbx
0x18001bbc8  mov     rcx, rbx
0x18001bbcb  mov     rax, [rax+98h]
0x18001bbd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbd7  mov     [rsp+100h+var_A0], eax
0x18001bbdb  mov     r10d, eax
0x18001bbde  test    eax, eax
0x18001bbe0  js      loc_18001BD42
0x18001bbe6  mov     r15, rbx
0x18001bbe9  mov     [rbp+1Fh+var_78], rbx
0x18001bbed  jmp     short loc_18001BC2C
0x18001bbef  cmp     eax, 0Ch
0x18001bbf2  jnz     short loc_18001BC2C
0x18001bbf4  test    r12, r12
0x18001bbf7  jnz     loc_18001BDC5
0x18001bbfd  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18001bc04  mov     rdx, rbx
0x18001bc07  mov     rcx, rbx
0x18001bc0a  mov     rax, [rax+98h]
0x18001bc11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc16  mov     [rsp+100h+var_A0], eax
0x18001bc1a  mov     r10d, eax
0x18001bc1d  test    eax, eax
0x18001bc1f  js      loc_18001BD92
0x18001bc25  mov     r12, rbx
0x18001bc28  mov     [rbp+1Fh+var_80], rbx
0x18001bc2c  mov     rbx, [rbp+1Fh+arg_10]
0x18001bc30  inc     esi
0x18001bc32  cmp     esi, [r14]
0x18001bc35  jb      loc_18001BB60
0x18001bc3b  lea     rsi, WPP_GLOBAL_Control
0x18001bc42  mov     edx, [r14]
0x18001bc45  xor     r12d, r12d
0x18001bc48  xor     r14d, r14d
0x18001bc4b  test    edx, edx
0x18001bc4d  jz      short loc_18001BC82
0x18001bc4f  mov     r9, [rbx+8]
0x18001bc53  mov     ecx, r14d
0x18001bc56  nop     word ptr [rax+rax+00000000h]
0x18001bc60  mov     ebx, ecx
0x18001bc62  add     rbx, rbx
0x18001bc65  mov     eax, [r9+rbx*8+4]
0x18001bc6a  lea     r8, [r9+rbx*8]
0x18001bc6e  and     eax, 0FFFFFFFh
0x18001bc73  cmp     eax, 0Eh
0x18001bc76  jz      loc_18001BE9F
0x18001bc7c  inc     ecx
0x18001bc7e  cmp     ecx, edx
0x18001bc80  jb      short loc_18001BC60
0x18001bc82  mov     r15, r14
0x18001bc85  mov     r14, [rbp+1Fh+arg_30]
0x18001bc89  mov     edx, [r14+4]
0x18001bc8d  test    edx, edx
0x18001bc8f  jz      loc_18001BFA6
0x18001bc95  mov     r8, [r14+8]
0x18001bc99  xor     ecx, ecx
0x18001bc9b  nop     dword ptr [rax+rax+00h]
0x18001bca0  mov     ebx, ecx
0x18001bca2  shl     rbx, 4
0x18001bca6  add     rbx, r8
0x18001bca9  mov     eax, [rbx+4]
0x18001bcac  and     eax, 0FFFFFFFh
0x18001bcb1  cmp     eax, 2
0x18001bcb4  jz      loc_18001BF53
0x18001bcba  inc     ecx
0x18001bcbc  cmp     ecx, edx
0x18001bcbe  jb      short loc_18001BCA0
0x18001bcc0  jmp     loc_18001BFA6
0x18001bcc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bccc  lea     rdx, WPP_GLOBAL_Control
0x18001bcd3  cmp     rcx, rdx
0x18001bcd6  jz      loc_18001CA63
0x18001bcdc  test    byte ptr [rcx+1Ch], 1
0x18001bce0  jz      loc_18001CA63
0x18001bce6  mov     edx, 37h ; '7'
0x18001bceb  mov     dword ptr [rsp+100h+var_D8], 626h
0x18001bcf3  mov     r9d, eax
0x18001bcf6  lea     rbx, aOnecoreDsSecur_4; "onecore\\ds\\security\\protocols\\pku2u"...
0x18001bcfd  mov     rcx, [rcx+10h]
0x18001bd01  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18001bd08  mov     [rsp+100h+var_E0], rbx
0x18001bd0d  call    WPP_SF_dsd
0x18001bd12  jmp     loc_18001CA5E
0x18001bd17  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd1e  lea     rdx, WPP_GLOBAL_Control
0x18001bd25  cmp     rcx, rdx
0x18001bd28  jz      loc_18001BDF3
0x18001bd2e  test    byte ptr [rcx+1Ch], 1
0x18001bd32  jz      loc_18001BDF3
0x18001bd38  mov     edx, 36h ; '6'
0x18001bd3d  jmp     loc_18001BDE3
0x18001bd42  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd49  lea     rdx, WPP_GLOBAL_Control
0x18001bd50  cmp     rcx, rdx
0x18001bd53  jz      loc_18001CA63
0x18001bd59  test    byte ptr [rcx+1Ch], 1
0x18001bd5d  jz      loc_18001CA63
0x18001bd63  mov     edx, 39h ; '9'
0x18001bd68  mov     dword ptr [rsp+100h+var_D8], 63Ch
0x18001bd70  jmp     short loc_18001BCF3
0x18001bd72  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd79  lea     rdx, WPP_GLOBAL_Control
0x18001bd80  cmp     rcx, rdx
0x18001bd83  jz      short loc_18001BDF3
0x18001bd85  test    byte ptr [rcx+1Ch], 1
0x18001bd89  jz      short loc_18001BDF3
0x18001bd8b  mov     edx, 38h ; '8'
0x18001bd90  jmp     short loc_18001BDE3
0x18001bd92  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd99  lea     rdx, WPP_GLOBAL_Control
0x18001bda0  cmp     rcx, rdx
0x18001bda3  jz      loc_18001CA63
0x18001bda9  test    byte ptr [rcx+1Ch], 1
0x18001bdad  jz      loc_18001CA63
0x18001bdb3  mov     edx, 3Bh ; ';'
0x18001bdb8  mov     dword ptr [rsp+100h+var_D8], 652h
0x18001bdc0  jmp     loc_18001BCF3
0x18001bdc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bdcc  lea     rdx, WPP_GLOBAL_Control
0x18001bdd3  cmp     rcx, rdx
0x18001bdd6  jz      short loc_18001BDF3
0x18001bdd8  test    byte ptr [rcx+1Ch], 1
0x18001bddc  jz      short loc_18001BDF3
0x18001bdde  mov     edx, 3Ah ; ':'
0x18001bde3  mov     rcx, [rcx+10h]
0x18001bde7  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18001bdee  call    WPP_SF_
0x18001bdf3  mov     r10d, 80090308h
0x18001bdf9  jmp     loc_18001C3A7
0x18001bdfe  mov     edx, [r14]
0x18001be01  test    edx, edx
0x18001be03  jz      loc_18001BC42
0x18001be09  mov     r8, [rbx+8]
0x18001be0d  xor     ecx, ecx
0x18001be0f  nop
0x18001be10  mov     ebx, ecx
0x18001be12  shl     rbx, 4
0x18001be16  add     rbx, r8
0x18001be19  mov     eax, [rbx+4]
0x18001be1c  and     eax, 0FFFFFFFh
0x18001be21  cmp     eax, 2
0x18001be24  jz      short loc_18001BE35
0x18001be26  inc     ecx
0x18001be28  cmp     ecx, edx
0x18001be2a  jb      short loc_18001BE10
0x18001be2c  mov     rbx, [rbp+1Fh+arg_10]
0x18001be30  jmp     loc_18001BC42
0x18001be35  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18001be3c  mov     rdx, rbx
0x18001be3f  mov     rcx, rbx
0x18001be42  mov     rax, [rax+98h]
0x18001be49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be4e  mov     [rsp+100h+var_A0], eax
0x18001be52  mov     r10d, eax
0x18001be55  test    eax, eax
0x18001be57  jns     short loc_18001BE93
0x18001be59  mov     rax, cs:WPP_GLOBAL_Control
0x18001be60  cmp     rax, rsi
0x18001be63  jz      loc_18001CA63
0x18001be69  test    byte ptr [rax+1Ch], 1
  ... truncated ...
```
