# SpInitLsaModeContext(unsigned __int64,unsigned __int64,_UNICODE_STRING *,ulong,ulong,_SecBufferDesc *,unsigned __int64 *,_SecBufferDesc *,ulong *,_LARGE_INTEGER *,uchar *,_SecBuffer *)

- ea: `0x18001cc90`
- end: `0x18001e07b`
- name: `?SpInitLsaModeContext@@YAJ_K0PEAU_UNICODE_STRING@@KKPEAU_SecBufferDesc@@PEA_K2PEAKPEAT_LARGE_INTEGER@@PEAEPEAU_SecBuffer@@@Z`
- size: `5099`
- prototype: `__int64 __fastcall(struct _PKU2U_SECONDARY_CREDENTIAL *, struct _PKU2U_CONTEXT *, struct _UNICODE_STRING *, int, unsigned int, struct _SecBufferDesc *, unsigned __int64 *, struct _SecBufferDesc *, unsigned int *, union _LARGE_INTEGER *, unsigned __int8 *, struct _SecBuffer *)`
- caller_count: `0`
- callee_count: `33`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001910`
- `0x180005300`
- `0x180005a80`
- `0x180006250`
- `0x180007dc8`
- `0x18000a340`
- `0x18000afc0`
- `0x18000f100`
- `0x18000fc70`
- `0x180011ec0`
- `0x1800138c0`
- `0x180014e30`
- `0x180015190`
- `0x1800160e0`
- `0x180016ff0`
- `0x180018c00`
- `0x18001cc90`
- `0x18001e090`
- `0x1800210f0`
- `0x180023cb8`
- `0x180023ce0`
- `0x180023d9c`
- `0x180023e30`
- `0x180023e70`
- `0x18002adb0`
- `0x18002b158`
- `0x18002b454`
- `0x18002b744`
- `0x1800320e8`
- `0x1800355cc`
- `0x18003754c`
- `0x180044f8c`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001db1f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001db1f`
- `MSASN1!ASN1_CloseDecoder` at `0x18001d365`
- `MSASN1!ASN1_CloseDecoder` at `0x18001d68c`
- `MSASN1!ASN1_CloseDecoder` at `0x18001df95`
- `MSASN1!ASN1_CloseDecoder` at `0x18001dfd7`
- `MSASN1!ASN1_CloseDecoder` at `0x18001d365`
- `MSASN1!ASN1_CloseDecoder` at `0x18001d68c`
- `MSASN1!ASN1_CloseDecoder` at `0x18001df95`
- `MSASN1!ASN1_CloseDecoder` at `0x18001dfd7`
- `MSASN1!ASN1_FreeDecoded` at `0x18001d355`
- `MSASN1!ASN1_FreeDecoded` at `0x18001d67c`
- `MSASN1!ASN1_FreeDecoded` at `0x18001df85`
- `MSASN1!ASN1_FreeDecoded` at `0x18001dfc7`
- `MSASN1!ASN1_FreeDecoded` at `0x18001d355`
- `MSASN1!ASN1_FreeDecoded` at `0x18001d67c`
- `MSASN1!ASN1_FreeDecoded` at `0x18001df85`
- `MSASN1!ASN1_FreeDecoded` at `0x18001dfc7`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18001de8d`
- `ntdll!RtlSystemTimeToLocalTime` at `0x18001de8d`
- `ntdll!RtlTimeToTimeFields` at `0x18001db53`
- `ntdll!RtlTimeToTimeFields` at `0x18001db53`

## string_xrefs

- `0x18001d142`: `onecore\ds\security\protocols\pku2u\ctxtapi.cxx`
- `0x18001d219`: `onecore\ds\security\protocols\pku2u\ctxtapi.cxx`
- `0x18001d43e`: `onecore\ds\security\protocols\pku2u\ctxtapi.cxx`
- `0x18001d863`: `onecore\ds\security\protocols\pku2u\ctxtapi.cxx`
- `0x18001d88b`: `onecore\ds\security\protocols\pku2u\ctxtapi.cxx`
- `0x18001d984`: `onecore\ds\security\protocols\pku2u\ctxtapi.cxx`
- `0x18001da4c`: `onecore\ds\security\protocols\pku2u\ctxtapi.cxx`
- `0x18001dcd4`: `onecore\ds\security\protocols\pku2u\ctxtapi.cxx`
- `0x18001dc21`: `onecore\ds\security\protocols\pku2u\tick.cxx`

## pseudocode

```c
__int64 __fastcall SpInitLsaModeContext(
        struct _PKU2U_SECONDARY_CREDENTIAL *a1,
        struct _PKU2U_CONTEXT *a2,
        struct _UNICODE_STRING *a3,
        int a4,
        unsigned int a5,
        struct _SecBufferDesc *a6,
        unsigned __int64 *a7,
        struct _SecBufferDesc *a8,
        unsigned int *a9,
        union _LARGE_INTEGER *a10,
        unsigned __int8 *a11,
        struct _SecBuffer *a12)
{
  struct _FILETIME v14; // r15
  PLARGE_INTEGER v15; // rcx
  union _LARGE_INTEGER v16; // rax
  int v17; // ebx
  volatile signed __int32 *v18; // r12
  volatile signed __int32 *v19; // r14
  int v20; // eax
  unsigned int cBuffers; // edx
  PSecBuffer pBuffers; // r8
  int v23; // ecx
  struct _SecBuffer *v24; // rsi
  int v25; // eax
  struct _SecBuffer *v26; // r14
  unsigned int v27; // edx
  PSecBuffer v28; // r8
  int v29; // ecx
  struct _SecBuffer *v30; // rsi
  int v31; // eax
  _QWORD *v32; // rcx
  __int64 v33; // rdx
  struct _SEC_CHANNEL_BINDINGS *pvBuffer; // r12
  unsigned int v35; // edx
  unsigned int v36; // ecx
  PSecBuffer v37; // r9
  __int64 v38; // rsi
  PSecBuffer v39; // rax
  unsigned __int64 cbBuffer; // rdx
  __int64 cbInitiatorLength; // r8
  __int64 cbAcceptorLength; // r9
  __int64 cbApplicationDataLength; // r10
  unsigned __int64 v44; // rcx
  unsigned __int64 dwInitiatorOffset; // rax
  unsigned __int64 dwAcceptorOffset; // rax
  unsigned __int64 dwApplicationDataOffset; // rax
  struct _PKU2U_SECONDARY_CREDENTIAL *v48; // rcx
  __int64 v49; // r9
  __int64 v50; // r9
  __int64 v51; // r9
  int v52; // eax
  _QWORD *v53; // rcx
  int v54; // edx
  int v55; // eax
  struct gss_OID_desc_struct *v56; // rcx
  DWORD dwLowDateTime; // ebx
  struct ASN1decoding_s *v58; // rsi
  unsigned int v59; // edx
  unsigned __int8 *v60; // rcx
  struct KERB_ERROR *v61; // r10
  struct _FILETIME v62; // rbx
  int v63; // ecx
  struct KERB_ERROR *v64; // r10
  _QWORD *v65; // rcx
  __int64 v66; // rdx
  int v67; // eax
  struct gss_OID_desc_struct *v68; // rcx
  DWORD v69; // ebx
  struct ASN1decoding_s *v70; // rsi
  unsigned int v71; // edx
  unsigned __int8 *v72; // rcx
  struct _FILETIME v73; // rbx
  int v74; // ecx
  struct _PKU2U_TICKET_CACHE_ENTRY *v75; // r8
  __int64 v76; // rdx
  int v77; // ecx
  int v78; // r9d
  __int64 v79; // rcx
  __int64 v80; // r8
  int v81; // eax
  PVOID *v82; // rcx
  unsigned int v83; // ecx
  int v84; // eax
  unsigned int *v85; // r14
  struct ASN1decoding_s *v86; // rsi
  union _LARGE_INTEGER *v87; // rdx
  struct KERB_ERROR *v88; // rdi
  void (*v89)(void); // rax
  char v91; // [rsp+28h] [rbp-D8h]
  size_t Size; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-B8h] BYREF
  struct KERB_ERROR *v94; // [rsp+50h] [rbp-B0h] BYREF
  struct ASN1decoding_s *v95; // [rsp+58h] [rbp-A8h] BYREF
  void *Src; // [rsp+60h] [rbp-A0h] BYREF
  struct _SecBufferDesc *v97; // [rsp+68h] [rbp-98h] BYREF
  struct ASN1decoding_s *v98; // [rsp+70h] [rbp-90h] BYREF
  int v99; // [rsp+78h] [rbp-88h]
  struct _PKU2U_SECONDARY_CREDENTIAL *v100; // [rsp+80h] [rbp-80h]
  struct _SecBufferDesc *v101; // [rsp+88h] [rbp-78h]
  PLARGE_INTEGER LocalTime; // [rsp+90h] [rbp-70h]
  unsigned int *v103; // [rsp+98h] [rbp-68h]
  struct _SecBuffer *v104; // [rsp+A0h] [rbp-60h]
  unsigned __int8 *v105; // [rsp+A8h] [rbp-58h]
  unsigned __int64 *v106; // [rsp+B0h] [rbp-50h]
  _DWORD v107[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v108; // [rsp+C0h] [rbp-40h]
  __int128 v109; // [rsp+D0h] [rbp-30h]
  struct _TIME_FIELDS TimeFields; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v111; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v112; // [rsp+100h] [rbp+0h]
  __int128 v113; // [rsp+110h] [rbp+10h]
  __int64 v114; // [rsp+120h] [rbp+20h]

  *(_QWORD *)&TimeFields.Year = a3;
  v101 = a8;
  v97 = a6;
  v14 = 0;
  v94 = 0;
  Src = 0;
  LODWORD(Size) = 0;
  v100 = 0;
  v99 = a4;
  v104 = a12;
  v106 = a7;
  v103 = a9;
  LocalTime = a10;
  v105 = a11;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, a2);
  v15 = LocalTime;
  v16 = Pku2uGlobalHasNeverTime;
  *a9 = 0;
  *a7 = (unsigned __int64)a2;
  *v15 = v16;
  *a11 = 0;
  a12->pvBuffer = 0;
  a12->cbBuffer = 0;
  if ( !a2 )
  {
    v17 = -1073741816;
    goto LABEL_273;
  }
  v18 = (volatile signed __int32 *)((char *)a2 + 8);
  _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
  v19 = (volatile signed __int32 *)((char *)a2 + 320);
  if ( _InterlockedIncrement((volatile signed __int32 *)a2 + 80) > 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, a2, *v19);
    v17 = -2146893054;
    goto LABEL_273;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NegoLateFallback>::GetImpl'::`2'::impl) )
  {
    v20 = *((_DWORD *)a2 + 10);
    if ( (v20 & 4) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, a2);
      v17 = -2146893054;
      goto LABEL_273;
    }
    *((_DWORD *)a2 + 10) = v20 | 2;
  }
  v98 = 0;
  cBuffers = v101->cBuffers;
  if ( cBuffers )
  {
    pBuffers = v101->pBuffers;
    v23 = 0;
    while ( 1 )
    {
      v24 = &pBuffers[v23];
      if ( (v24->BufferType & 0xFFFFFFF) == 2 )
        break;
      if ( ++v23 >= cBuffers )
        goto LABEL_28;
    }
    v25 = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))Pku2uGlobalLsaFunctions->MapBuffer)(
            &pBuffers[v23],
            &pBuffers[v23]);
    v17 = v25;
    if ( v25 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
          (unsigned int)v25);
      goto LABEL_39;
    }
    v98 = (struct ASN1decoding_s *)v24;
  }
LABEL_28:
  v26 = 0;
  v27 = v97->cBuffers;
  if ( !v27 )
    goto LABEL_44;
  v28 = v97->pBuffers;
  v29 = 0;
  while ( 1 )
  {
    v30 = &v28[v29];
    if ( (v30->BufferType & 0xFFFFFFF) == 2 )
      break;
    if ( ++v29 >= v27 )
      goto LABEL_44;
  }
  v31 = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))Pku2uGlobalLsaFunctions->MapBuffer)(
          &v28[v29],
          &v28[v29]);
  v17 = v31;
  if ( v31 >= 0 )
  {
    v26 = v30;
    if ( v30 )
    {
      if ( v30->cbBuffer )
      {
        v17 = Pku2uSaveSSPIMessage((unsigned __int8 *)v30->pvBuffer, v30->cbBuffer, a2);
        if ( v17 < 0 )
        {
LABEL_263:
          if ( v17 != 280 )
          {
            v19 = (volatile signed __int32 *)((char *)a2 + 320);
            if ( v17 == 590610 )
              goto LABEL_274;
            goto LABEL_39;
          }
LABEL_272:
          v17 = -1073741715;
          goto LABEL_273;
        }
      }
    }
LABEL_44:
    pvBuffer = 0;
    v35 = v97->cBuffers;
    if ( v35 )
    {
      v36 = 0;
      v37 = v97->pBuffers;
      while ( 1 )
      {
        v38 = v36;
        if ( (v37[v36].BufferType & 0xFFFFFFF) == 0xE )
          break;
        if ( ++v36 >= v35 )
          goto LABEL_48;
      }
      v17 = ((__int64 (__fastcall *)(struct _SecBuffer *, struct _SecBuffer *))Pku2uGlobalLsaFunctions->MapBuffer)(
              &v37[v36],
              &v37[v36]);
      if ( v17 < 0 )
      {
LABEL_262:
        v18 = (volatile signed __int32 *)((char *)a2 + 8);
        goto LABEL_263;
      }
      v39 = v97->pBuffers;
      pvBuffer = (struct _SEC_CHANNEL_BINDINGS *)v39[v38].pvBuffer;
      if ( !pvBuffer )
        goto LABEL_60;
      cbBuffer = v39[v38].cbBuffer;
      if ( (unsigned int)cbBuffer < 0x20
        || (cbInitiatorLength = pvBuffer->cbInitiatorLength,
            cbAcceptorLength = pvBuffer->cbAcceptorLength,
            cbApplicationDataLength = pvBuffer->cbApplicationDataLength,
            v44 = cbApplicationDataLength + cbAcceptorLength + cbInitiatorLength + 32,
            v44 > cbBuffer)
        || (dwInitiatorOffset = pvBuffer->dwInitiatorOffset, dwInitiatorOffset + cbInitiatorLength > v44)
        || dwInitiatorOffset + cbInitiatorLength < dwInitiatorOffset
        || (dwAcceptorOffset = pvBuffer->dwAcceptorOffset, dwAcceptorOffset + cbAcceptorLength > v44)
        || dwAcceptorOffset + cbAcceptorLength < dwAcceptorOffset
        || (dwApplicationDataOffset = pvBuffer->dwApplicationDataOffset,
            dwApplicationDataOffset + cbApplicationDataLength > v44)
        || dwApplicationDataOffset + cbApplicationDataLength < dwApplicationDataOffset )
      {
LABEL_60:
        v17 = -1073741811;
        goto LABEL_273;
      }
    }
LABEL_48:
    if ( !*((_QWORD *)a2 + 10) )
    {
      v17 = -2146893053;
      goto LABEL_273;
    }
    if ( a1 )
    {
      v100 = a1;
      Pku2uReferenceSecondaryCredential(a1);
      v48 = (struct _PKU2U_SECONDARY_CREDENTIAL *)*((_QWORD *)a2 + 2);
      if ( v48 != a1 )
      {
        v49 = *((unsigned int *)a1 + 8);
        if ( (_DWORD)v49 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, v49);
          v17 = -2146893042;
          goto LABEL_273;
        }
        Pku2uDereferenceSecondaryCredential(v48);
        *((_QWORD *)a2 + 2) = a1;
        v100 = 0;
      }
    }
    v50 = *((unsigned int *)a2 + 17);
    if ( !(_DWORD)v50 )
    {
      if ( v26 )
      {
        v51 = v26->cbBuffer;
        if ( (_DWORD)v51 )
        {
          v17 = -2146893048;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, v51);
          goto LABEL_273;
        }
      }
      v17 = Pku2uLookupTicketCacheEntryFromCredentials(
              *((struct _PKU2U_SECONDARY_CREDENTIAL **)a2 + 2),
              *((struct _PKU2U_ASSOCIATED_CREDENTIAL **)a2 + 4),
              *((struct _KERB_INTERNAL_NAME **)a2 + 10),
              (struct _PKU2U_TICKET_CACHE_ENTRY **)a2 + 22);
      if ( v17 >= 0 )
      {
        if ( !*((_QWORD *)a2 + 22) )
        {
          v52 = Pku2uBuildPeer2PeerAsRequest(a2, v94, (unsigned __int8 **)&Src, (unsigned int *)&Size);
          v17 = v52;
          if ( v52 < 0 )
          {
            v53 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_38;
            v54 = 25;
            v91 = 122;
            goto LABEL_81;
          }
          goto LABEL_82;
        }
        goto LABEL_124;
      }
      goto LABEL_262;
    }
    if ( (_DWORD)v50 == 1 )
    {
      if ( v26 && v26->cbBuffer )
      {
        v55 = Pku2uHandlePeer2PeerAsReply(a2, v26->cbBuffer, (unsigned __int8 *)v26->pvBuffer);
        v17 = v55;
        if ( v55 != 280 )
        {
          if ( v55 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_dsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                29,
                (unsigned int)&WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
                v55,
                (__int64)"onecore\\ds\\security\\protocols\\pku2u\\ctxtapi.cxx",
                214);
            goto LABEL_38;
          }
LABEL_124:
          v64 = v94;
LABEL_125:
          v52 = Pku2uBuildApRequest(a2, v64, (unsigned __int8 **)&Src, (unsigned int *)&Size, pvBuffer);
          v17 = v52;
          if ( v52 < 0 )
          {
            v53 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_38;
            v54 = 42;
            v91 = -80;
            goto LABEL_81;
          }
          v76 = *((_QWORD *)a2 + 22);
          if ( v76 )
          {
            v77 = *((_DWORD *)a2 + 16);
            *((_DWORD *)a2 + 16) = v77 & 0xFFFFFFFD;
            *((_DWORD *)a2 + 16) = v77 ^ (*(_DWORD *)(v76 + 180) ^ v77) & 2;
LABEL_177:
            v17 = 590610;
            *((_DWORD *)a2 + 17) = 3;
            goto LABEL_232;
          }
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_177;
          WPP_SF_dsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            43,
            (unsigned int)&WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
            -1073741504,
            (__int64)"onecore\\ds\\security\\protocols\\pku2u\\ctxtapi.cxx",
            205);
          v17 = 590610;
          *((_DWORD *)a2 + 17) = 3;
LABEL_232:
          v83 = Size;
          if ( (_DWORD)Size )
          {
            v84 = Pku2uSaveSSPIMessage((unsigned __int8 *)Src, Size, a2);
            if ( v84 < 0 )
            {
              v17 = v84;
              goto LABEL_38;
            }
            v83 = Size;
          }
          v85 = v103;
          *v103 |= *((_DWORD *)a2 + 16);
          if ( v83 )
          {
            v86 = v98;
            if ( !v98 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  44,
                  (unsigned int)&WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
                  (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\ctxtapi.cxx",
                  240);
              v17 = -2146893048;
              goto LABEL_273;
            }
            if ( (v99 & 0x100) != 0 )
            {
              *((_QWORD *)v98 + 1) = Src;
              *v85 |= 0x100u;
              Src = 0;
              *(_DWORD *)v86 = Size;
            }
            else
            {
              if ( *(_DWORD *)v98 < v83 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_ddsd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    45,
                    (unsigned int)&WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
                    *(_DWORD *)v98,
                    v83,
                    (__int64)"onecore\\ds\\security\\protocols\\pku2u\\ctxtapi.cxx",
                    254);
                  v83 = Size;
                }
                *(_DWORD *)v86 = v83;
                v19 = (volatile signed __int32 *)((char *)a2 + 320);
                v17 = -1073741789;
                v18 = (volatile signed __int32 *)((char *)a2 + 8);
                goto LABEL_274;
              }
              memcpy_0(*((void **)v98 + 1), Src, v83);
              *v85 &= ~0x100u;
              *(_DWORD *)v86 = Size;
            }
          }
          else if ( v98 )
          {
            *(_DWORD *)v98 = 0;
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NegoLateFallback>::GetImpl'::`2'::impl) )
          {
            if ( v17 )
              goto LABEL_261;
            v31 = Pku2uGenerateOrVerifyMechlistMIC(a2, v97, v101);
            v17 = v31;
            if ( v31 < 0 )
            {
              v32 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                goto LABEL_38;
              v33 = 46;
              goto LABEL_37;
            }
          }
          if ( !v17 )
          {
            v17 = Pku2uMapContext(a2, v105, v104);
            if ( v17 >= 0 )
            {
              v17 = 0;
              goto LABEL_261;
            }
LABEL_185:
            v18 = (volatile signed __int32 *)((char *)a2 + 8);
            goto LABEL_263;
          }
LABEL_261:
          v87 = LocalTime;
          *v106 = (unsigned __int64)a2;
          RtlSystemTimeToLocalTime((PLARGE_INTEGER)a2 + 6, v87);
          v18 = (volatile signed __int32 *)((char *)a2 + 8);
          goto LABEL_263;
        }
        dwLowDateTime = v26->cbBuffer;
        v58 = (struct ASN1decoding_s *)v26->pvBuffer;
        v95 = v58;
        SystemTimeAsFileTime.dwLowDateTime = dwLowDateTime;
        if ( (unsigned int)g_verify_token_header(
                             v56,
                             (int *)&SystemTimeAsFileTime,
                             (unsigned __int8 **)&v95,
                             768,
                             dwLowDateTime) )
        {
          dwLowDateTime = SystemTimeAsFileTime.dwLowDateTime;
          v58 = v95;
        }
        if ( !(unsigned int)KerbUnpackData((unsigned __int8 *)v58, dwLowDateTime, 4u, (void **)&v94) )
        {
          if ( (*(_BYTE *)v94 & 4) == 0 )
          {
            v17 = KerbMapKerbError(0);
            if ( v17 < 0 )
              goto LABEL_38;
            goto LABEL_100;
          }
          v59 = *((_DWORD *)v94 + 30);
          v60 = (unsigned __int8 *)*((_QWORD *)v94 + 16);
          SystemTimeAsFileTime = 0;
          if ( (unsigned int)KerbUnpackData(v60, v59, 0x17u, (void **)&SystemTimeAsFileTime) )
          {
            v62 = SystemTimeAsFileTime;
            if ( SystemTimeAsFileTime )
            {
              v95 = 0;
              if ( !(unsigned int)KerbInitAsn(0, &v95) )
              {
                ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))ASN1_FreeDecoded)(v95, v62, 23);
                if ( v95 )
                {
                  ASN1_CloseDecoder();
                  v61 = v94;
LABEL_100:
                  if ( *((_DWORD *)a2 + 43) || *((_DWORD *)v61 + 13) != 37 )
                  {
                    v63 = *((_DWORD *)v61 + 13);
                    if ( v63 == 60
                      && *(_QWORD *)&v14
                      && *(_DWORD *)(*(_QWORD *)&v14 + 4LL) == 1
                      && *(char *)v14.dwLowDateTime < 0
                      && *(_QWORD *)(*(_QWORD *)&v14 + 16LL)
                      && *(_DWORD *)(*(_QWORD *)&v14 + 8LL) == 4 )
                    {
                      v17 = **((_DWORD **)v61 + 16);
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                        WPP_SF_dsd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          27,
                          (unsigned int)&WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
                          v17,
                          (__int64)"onecore\\ds\\security\\protocols\\pku2u\\ctxtapi.cxx",
                          177);
                    }
                    else
                    {
                      v17 = KerbMapKerbError(v63);
                    }
                    if ( v17 >= 0 )
                    {
                      v17 = -1073741595;
                      goto LABEL_273;
                    }
                    goto LABEL_38;
                  }
                  *((_DWORD *)a2 + 43) = 1;
                  v52 = Pku2uBuildPeer2PeerAsRequest(a2, v61, (unsigned __int8 **)&Src, (unsigned int *)&Size);
                  v17 = v52;
                  if ( v52 >= 0 )
                  {
LABEL_82:
                    *((_DWORD *)a2 + 17) = 1;
                    v17 = 590610;
                    goto LABEL_232;
                  }
                  v53 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                    goto LABEL_38;
                  v54 = 28;
                  v91 = -54;
                  goto LABEL_81;
                }
              }
            }
          }
          else if ( SystemTimeAsFileTime )
          {
            v14 = SystemTimeAsFileTime;
            SystemTimeAsFileTime = 0;
          }
          v61 = v94;
          goto LABEL_100;
        }
LABEL_118:
        v17 = -1073741811;
        goto LABEL_38;
      }
      v17 = -2146893048;
      v65 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_273;
      v66 = 26;
LABEL_132:
      WPP_SF_q(v65[2], v66, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, v26);
      goto LABEL_273;
    }
    if ( (_DWORD)v50 != 3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, v50);
      goto LABEL_272;
    }
    if ( !v26 || !v26->cbBuffer )
    {
      v17 = -2146893048;
      v65 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_273;
      v66 = 30;
      goto LABEL_132;
    }
    v67 = Pku2uVerifyApReply(a2, (unsigned __int8 *)v26->pvBuffer, v26->cbBuffer);
    v17 = v67;
    if ( v67 == 280 )
    {
      v69 = v26->cbBuffer;
      v70 = (struct ASN1decoding_s *)v26->pvBuffer;
      v95 = v70;
      SystemTimeAsFileTime.dwLowDateTime = v69;
      if ( (unsigned int)g_verify_token_header(v68, (int *)&SystemTimeAsFileTime, (unsigned __int8 **)&v95, 768, v69) )
      {
        v70 = v95;
        v69 = SystemTimeAsFileTime.dwLowDateTime;
      }
      if ( (unsigned int)KerbUnpackData((unsigned __int8 *)v70, v69, 4u, (void **)&v94) )
        goto LABEL_118;
      if ( (*(_BYTE *)v94 & 4) != 0 )
      {
        v71 = *((_DWORD *)v94 + 30);
        v72 = (unsigned __int8 *)*((_QWORD *)v94 + 16);
        SystemTimeAsFileTime = 0;
        if ( !(unsigned int)KerbUnpackData(v72, v71, 0x17u, (void **)&SystemTimeAsFileTime) )
        {
          if ( SystemTimeAsFileTime )
          {
            v14 = SystemTimeAsFileTime;
            SystemTimeAsFileTime = 0;
          }
          goto LABEL_144;
        }
        v73 = SystemTimeAsFileTime;
        if ( !*(_QWORD *)&SystemTimeAsFileTime
          || (v95 = 0, (unsigned int)KerbInitAsn(0, &v95))
          || (((void (__fastcall *)(_QWORD, _QWORD, _QWORD))ASN1_FreeDecoded)(v95, v73, 23), !v95) )
        {
LABEL_144:
          v64 = v94;
          goto LABEL_150;
        }
        ASN1_CloseDecoder();
        v64 = v94;
      }
      else
      {
        v17 = KerbMapKerbError(0);
        if ( v17 < 0 )
          goto LABEL_38;
      }
LABEL_150:
      if ( !*((_DWORD *)a2 + 43) )
      {
        v74 = *((_DWORD *)v64 + 13);
        if ( v74 == 37 )
        {
          if ( !*(_QWORD *)&v14 )
            goto LABEL_181;
          goto LABEL_156;
        }
        if ( ((v74 - 33) & 0xFFFFFFF7) == 0 )
        {
          if ( !*(_QWORD *)&v14 )
          {
LABEL_157:
            if ( v74 == 33 )
            {
              Pku2uPurgeTicketCacheEntry(
                *((struct _PKU2U_SECONDARY_CREDENTIAL **)a2 + 2),
                *((struct _PKU2U_ASSOCIATED_CREDENTIAL **)a2 + 4),
                *((struct _PKU2U_TICKET_CACHE_ENTRY **)a2 + 22));
              Pku2uDereferenceTicketCacheEntry(*((struct _PKU2U_TICKET_CACHE_ENTRY **)a2 + 22));
              *((_QWORD *)a2 + 22) = 0;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids);
              v64 = v94;
            }
            ++*((_DWORD *)a2 + 43);
            if ( *((_DWORD *)v64 + 13) == 41 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids);
              v75 = (struct _PKU2U_TICKET_CACHE_ENTRY *)*((_QWORD *)a2 + 22);
              if ( v75 )
              {
                Pku2uPurgeTicketCacheEntry(
                  *((struct _PKU2U_SECONDARY_CREDENTIAL **)a2 + 2),
                  *((struct _PKU2U_ASSOCIATED_CREDENTIAL **)a2 + 4),
                  v75);
                Pku2uDereferenceTicketCacheEntry(*((struct _PKU2U_TICKET_CACHE_ENTRY **)a2 + 22));
                *((_QWORD *)a2 + 22) = 0;
              }
              KerbFreeKey((struct _PKU2U_CONTEXT *)((char *)a2 + 224));
              KerbFreeKey((struct _PKU2U_CONTEXT *)((char *)a2 + 200));
              v64 = v94;
            }
            if ( *((_QWORD *)a2 + 22) )
              goto LABEL_125;
            v52 = Pku2uBuildPeer2PeerAsRequest(a2, v64, (unsigned __int8 **)&Src, (unsigned int *)&Size);
            v17 = v52;
            if ( v52 >= 0 )
            {
              *((_DWORD *)a2 + 17) = 1;
              v17 = 590610;
              goto LABEL_232;
            }
            v53 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_38;
            v54 = 38;
            v91 = 114;
LABEL_81:
            WPP_SF_dsd(
              v53[2],
              v54,
              (unsigned int)&WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
              v52,
              (__int64)"onecore\\ds\\security\\protocols\\pku2u\\ctxtapi.cxx",
              v91);
            goto LABEL_38;
          }
LABEL_156:
          if ( *(_DWORD *)(*(_QWORD *)&v14 + 4LL) == 2 )
            goto LABEL_157;
LABEL_181:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids);
            v64 = v94;
          }
          v17 = KerbMapKerbError(*((_DWORD *)v64 + 13));
          goto LABEL_185;
        }
      }
      v78 = *((_DWORD *)v64 + 13);
      switch ( v78 )
      {
        case '<':
          if ( *(_QWORD *)&v14
            && *(_DWORD *)(*(_QWORD *)&v14 + 4LL) == 1
            && *(char *)v14.dwLowDateTime < 0
            && *(_QWORD *)(*(_QWORD *)&v14 + 16LL)
            && *(_DWORD *)(*(_QWORD *)&v14 + 8LL) == 4 )
          {
            v17 = **((_DWORD **)v64 + 16);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_dsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                31,
                (unsigned int)&WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
                v17,
                (__int64)"onecore\\ds\\security\\protocols\\pku2u\\ctxtapi.cxx",
                11);
            goto LABEL_209;
          }
LABEL_205:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_dsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              34,
              (unsigned int)&WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
              v78,
              (__int64)"onecore\\ds\\security\\protocols\\pku2u\\ctxtapi.cxx",
              30);
            v64 = v94;
          }
          v17 = KerbMapKerbError(*((_DWORD *)v64 + 13));
LABEL_209:
          if ( v17 >= 0 )
          {
            v17 = -1073741595;
            break;
          }
          goto LABEL_38;
        case ')':
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2));
          v17 = -2146893022;
          break;
        case '!':
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids);
          v17 = -1073741517;
          break;
        default:
          goto LABEL_205;
      }
LABEL_273:
      Pku2uLogProvider::LogClientContext(a2, v17);
      v19 = (volatile signed __int32 *)((char *)a2 + 320);
      v18 = (volatile signed __int32 *)((char *)a2 + 8);
      if ( !a2 )
        goto LABEL_276;
      goto LABEL_274;
    }
    if ( v67 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          (unsigned int)&WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
          v67,
          (__int64)"onecore\\ds\\security\\protocols\\pku2u\\ctxtapi.cxx",
          128);
      goto LABEL_38;
    }
    if ( (*((_DWORD *)a2 + 16) & 0x200) != 0 )
    {
      SystemTimeAsFileTime = 0;
      v107[0] = 5;
      v114 = 0;
      Src = 0;
      v108 = 0;
      LODWORD(Size) = 0;
      v109 = 0;
      v107[1] = 15;
      v111 = 0;
      v112 = 0;
      v113 = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      TimeFields = 0;
      if ( SystemTimeAsFileTime )
      {
        RtlTimeToTimeFields((PLARGE_INTEGER)&SystemTimeAsFileTime, &TimeFields);
        WORD1(v111) = 9999;
        if ( TimeFields.Year <= 9999 )
          WORD1(v111) = TimeFields.Year;
        BYTE4(v111) = TimeFields.Month;
        BYTE5(v111) = TimeFields.Day;
        BYTE6(v111) = TimeFields.Hour;
        BYTE7(v111) = TimeFields.Minute;
        BYTE8(v111) = TimeFields.Second;
        WORD5(v111) = 0;
        v79 = *(__int64 *)&SystemTimeAsFileTime / 10 % 1000000;
      }
      else
      {
        LODWORD(v79) = 0;
        *(_QWORD *)((char *)&v111 + 2) = 16844722;
        *(_DWORD *)((char *)&v111 + 10) = 0;
      }
      LOWORD(v111) = v111 | 0x40;
      v80 = *((_QWORD *)a2 + 22);
      HIWORD(v111) = 0;
      v81 = *((_DWORD *)a2 + 74);
      BYTE12(v111) = 1;
      LODWORD(v112) = v79;
      LODWORD(v114) = v81;
      if ( !v80 )
      {
        v82 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            (unsigned int)&WPP_6bfba9c36965322fee57f4932fd116a9_Traceguids,
            (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\tick.cxx",
            73);
          v82 = (PVOID *)WPP_GLOBAL_Control;
        }
        v17 = -1073741715;
LABEL_228:
        if ( v82 != &WPP_GLOBAL_Control && (*((_BYTE *)v82 + 28) & 1) != 0 )
        {
          WPP_SF_dsd(
            (unsigned int)v82[2],
            40,
            (unsigned int)&WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
            v17,
            (__int64)"onecore\\ds\\security\\protocols\\pku2u\\ctxtapi.cxx",
            146);
          v18 = (volatile signed __int32 *)((char *)a2 + 8);
          goto LABEL_263;
        }
        goto LABEL_185;
      }
      v17 = Pku2uMarshallApReply(
              (struct KERB_AP_REPLY *)v107,
              (struct KERB_ENCRYPTED_AP_REPLY *)&v111,
              (struct KERB_ENCRYPTION_KEY *)(v80 + 56),
              (unsigned __int8 **)&Src,
              (unsigned int *)&Size);
      if ( v17 < 0 )
      {
        v82 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_228;
      }
    }
    *((_DWORD *)a2 + 17) = 6;
    v17 = 0;
    goto LABEL_232;
  }
  v32 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_38;
  v33 = 22;
LABEL_37:
  WPP_SF_d(v32[2], v33, &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids, (unsigned int)v31);
LABEL_38:
  v19 = (volatile signed __int32 *)((char *)a2 + 320);
LABEL_39:
  if ( v17 != -1073741789 )
    goto LABEL_273;
  v18 = (volatile signed __int32 *)((char *)a2 + 8);
LABEL_274:
  *((_DWORD *)a2 + 18) = v17;
  _InterlockedDecrement(v19);
  if ( _InterlockedExchangeAdd(v18, 0xFFFFFFFF) <= 1 )
    Pku2uFreeContext(a2);
LABEL_276:
  v88 = v94;
  if ( v94 )
  {
    v98 = 0;
    if ( !(unsigned int)KerbInitAsn(0, &v98) )
    {
      ASN1_FreeDecoded(v98, v88, 4);
      if ( v98 )
        ASN1_CloseDecoder();
    }
  }
  if ( v14 )
  {
    v97 = 0;
    if ( !(unsigned int)KerbInitAsn(0, (struct ASN1decoding_s **)&v97) )
    {
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))ASN1_FreeDecoded)(v97, v14, 23);
      if ( v97 )
        ASN1_CloseDecoder();
    }
  }
  if ( Src )
  {
    if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
      v89 = *(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 392LL);
    else
      v89 = *(void (**)(void))(*((_QWORD *)Pku2uGlobalBaseSSP + 31) + 8LL);
    v89();
  }
  if ( v100 )
    Pku2uDereferenceSecondaryCredential(v100);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      47,
      &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
      (unsigned int)v17);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18001cc90  mov     [rsp-8+arg_18], rbx
0x18001cc95  push    rbp
0x18001cc96  push    rsi
0x18001cc97  push    rdi
0x18001cc98  push    r12
0x18001cc9a  push    r13
0x18001cc9c  push    r14
0x18001cc9e  push    r15
0x18001cca0  lea     rbp, [rsp-30h]
0x18001cca5  sub     rsp, 130h
0x18001ccac  mov     rax, cs:__security_cookie
0x18001ccb3  xor     rax, rsp
0x18001ccb6  mov     [rbp+60h+var_38], rax
0x18001ccba  mov     rax, [rbp+60h+arg_28]
0x18001ccc1  mov     rdi, rdx
0x18001ccc4  mov     rsi, [rbp+60h+arg_58]
0x18001cccb  mov     r13, rcx
0x18001ccce  mov     r12, [rbp+60h+arg_30]
0x18001ccd5  mov     rbx, [rbp+60h+arg_40]
0x18001ccdc  mov     r14, [rbp+60h+arg_50]
0x18001cce3  mov     qword ptr [rbp+60h+TimeFields.Year], r8
0x18001cce7  mov     r8, [rbp+60h+arg_38]
0x18001ccee  mov     [rbp+60h+var_D8], r8
0x18001ccf2  xor     r8d, r8d
0x18001ccf5  mov     [rsp+160h+var_F8], rax
0x18001ccfa  mov     r15d, r8d
0x18001ccfd  mov     rax, [rbp+60h+arg_48]
0x18001cd04  mov     [rsp+160h+var_110], r8
0x18001cd09  mov     [rsp+160h+Src], r8
0x18001cd0e  mov     dword ptr [rsp+160h+Size], r8d
0x18001cd13  mov     [rbp+60h+var_E0], r8
0x18001cd17  mov     [rsp+160h+var_E8], r9d
0x18001cd1c  mov     [rbp+60h+var_C0], rsi
0x18001cd20  mov     [rbp+60h+var_B0], r12
0x18001cd24  mov     [rbp+60h+var_C8], rbx
0x18001cd28  mov     [rbp+60h+LocalTime], rax
0x18001cd2c  mov     [rbp+60h+var_B8], r14
0x18001cd30  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd37  lea     rdx, WPP_GLOBAL_Control
0x18001cd3e  cmp     rcx, rdx
0x18001cd41  jz      short loc_18001CD6B
0x18001cd43  test    byte ptr [rcx+1Ch], 8
0x18001cd47  jz      short loc_18001CD6B
0x18001cd49  mov     rcx, [rcx+10h]
0x18001cd4d  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18001cd54  mov     edx, 12h
0x18001cd59  mov     r9, rdi
0x18001cd5c  call    WPP_SF_q
0x18001cd61  lea     rdx, WPP_GLOBAL_Control
0x18001cd68  xor     r8d, r8d
0x18001cd6b  mov     rcx, [rbp+60h+LocalTime]
0x18001cd6f  mov     rax, cs:?Pku2uGlobalHasNeverTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER Pku2uGlobalHasNeverTime
0x18001cd76  mov     [rbx], r8d
0x18001cd79  mov     [r12], rdi
0x18001cd7d  mov     [rcx], rax
0x18001cd80  mov     [r14], r15b
0x18001cd83  mov     [rsi+8], r8
0x18001cd87  mov     [rsi], r8d
0x18001cd8a  test    rdi, rdi
0x18001cd8d  jnz     short loc_18001CDA0
0x18001cd8f  mov     ebx, 0C0000008h
0x18001cd94  lea     r13, WPP_GLOBAL_Control
0x18001cd9b  jmp     loc_18001DF1B
0x18001cda0  lea     r12, [rdi+8]
0x18001cda4  lock inc dword ptr [r12]
0x18001cda9  lea     r14, [rdi+140h]
0x18001cdb0  mov     eax, 1
0x18001cdb5  lock xadd [r14], eax
0x18001cdba  inc     eax
0x18001cdbc  cmp     eax, 1
0x18001cdbf  jle     short loc_18001CE03
0x18001cdc1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cdc8  cmp     rcx, rdx
0x18001cdcb  jz      short loc_18001CDF2
0x18001cdcd  test    byte ptr [rcx+1Ch], 1
0x18001cdd1  jz      short loc_18001CDF2
0x18001cdd3  mov     eax, [r14]
0x18001cdd6  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18001cddd  mov     rcx, [rcx+10h]
0x18001cde1  mov     edx, 13h
0x18001cde6  mov     r9, rdi
0x18001cde9  mov     dword ptr [rsp+160h+var_140], eax
0x18001cded  call    WPP_SF_qD
0x18001cdf2  mov     ebx, 80090302h
0x18001cdf7  lea     r13, WPP_GLOBAL_Control
0x18001cdfe  jmp     loc_18001DF1B
0x18001ce03  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NegoLateFallback@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NegoLateFallback@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback> `wil::Feature<__WilFeatureTraits_Feature_NegoLateFallback>::GetImpl(void)'::`2'::impl
0x18001ce0a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NegoLateFallback@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NegoLateFallback>::__private_IsEnabled(void)
0x18001ce0f  test    al, al
0x18001ce11  jz      short loc_18001CE5B
0x18001ce13  mov     eax, [rdi+28h]
0x18001ce16  test    al, 4
0x18001ce18  jz      short loc_18001CE55
0x18001ce1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce21  lea     r13, WPP_GLOBAL_Control
0x18001ce28  cmp     rcx, r13
0x18001ce2b  jz      short loc_18001CE4B
0x18001ce2d  test    byte ptr [rcx+1Ch], 1
0x18001ce31  jz      short loc_18001CE4B
0x18001ce33  mov     rcx, [rcx+10h]
0x18001ce37  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18001ce3e  mov     edx, 14h
0x18001ce43  mov     r9, rdi
0x18001ce46  call    WPP_SF_q
0x18001ce4b  mov     ebx, 80090302h
0x18001ce50  jmp     loc_18001DF1B
0x18001ce55  or      eax, 2
0x18001ce58  mov     [rdi+28h], eax
0x18001ce5b  mov     rax, [rbp+60h+var_D8]
0x18001ce5f  mov     [rsp+160h+var_F0], r15
0x18001ce64  mov     edx, [rax+4]
0x18001ce67  test    edx, edx
0x18001ce69  jz      loc_18001CF00
0x18001ce6f  mov     r8, [rax+8]
0x18001ce73  xor     ecx, ecx
0x18001ce75  nop     word ptr [rax+rax+00000000h]
0x18001ce80  mov     esi, ecx
0x18001ce82  shl     rsi, 4
0x18001ce86  add     rsi, r8
0x18001ce89  mov     eax, [rsi+4]
0x18001ce8c  and     eax, 0FFFFFFFh
0x18001ce91  cmp     eax, 2
0x18001ce94  jz      short loc_18001CE9E
0x18001ce96  inc     ecx
0x18001ce98  cmp     ecx, edx
0x18001ce9a  jb      short loc_18001CE80
0x18001ce9c  jmp     short loc_18001CF00
0x18001ce9e  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18001cea5  mov     rdx, rsi
0x18001cea8  mov     rcx, rsi
0x18001ceab  mov     rax, [rax+98h]
0x18001ceb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ceb7  mov     ebx, eax
0x18001ceb9  test    eax, eax
0x18001cebb  jns     short loc_18001CEFB
0x18001cebd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cec4  lea     r13, WPP_GLOBAL_Control
0x18001cecb  cmp     rcx, r13
0x18001cece  jz      loc_18001CF98
0x18001ced4  test    byte ptr [rcx+1Ch], 1
0x18001ced8  jz      loc_18001CF98
0x18001cede  mov     rcx, [rcx+10h]
0x18001cee2  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18001cee9  mov     edx, 15h
0x18001ceee  mov     r9d, eax
0x18001cef1  call    WPP_SF_d
0x18001cef6  jmp     loc_18001CF98
0x18001cefb  mov     [rsp+160h+var_F0], rsi
0x18001cf00  mov     r9, [rsp+160h+var_F8]
0x18001cf05  xor     r14d, r14d
0x18001cf08  mov     edx, [r9+4]
0x18001cf0c  test    edx, edx
0x18001cf0e  jz      loc_18001CFD1
0x18001cf14  mov     r8, [r9+8]
0x18001cf18  xor     ecx, ecx
0x18001cf1a  nop     word ptr [rax+rax+00h]
0x18001cf20  mov     esi, ecx
0x18001cf22  shl     rsi, 4
0x18001cf26  add     rsi, r8
0x18001cf29  mov     eax, [rsi+4]
0x18001cf2c  and     eax, 0FFFFFFFh
0x18001cf31  cmp     eax, 2
0x18001cf34  jz      short loc_18001CF41
0x18001cf36  inc     ecx
0x18001cf38  cmp     ecx, edx
0x18001cf3a  jb      short loc_18001CF20
0x18001cf3c  jmp     loc_18001CFD1
0x18001cf41  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18001cf48  mov     rdx, rsi
0x18001cf4b  mov     rcx, rsi
0x18001cf4e  mov     rax, [rax+98h]
0x18001cf55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf5a  mov     ebx, eax
0x18001cf5c  test    eax, eax
0x18001cf5e  jns     short loc_18001CFAD
0x18001cf60  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf67  lea     r13, WPP_GLOBAL_Control
0x18001cf6e  cmp     rcx, r13
0x18001cf71  jz      short loc_18001CF91
0x18001cf73  test    byte ptr [rcx+1Ch], 1
0x18001cf77  jz      short loc_18001CF91
0x18001cf79  mov     edx, 16h
0x18001cf7e  mov     rcx, [rcx+10h]
0x18001cf82  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18001cf89  mov     r9d, eax
0x18001cf8c  call    WPP_SF_d
0x18001cf91  lea     r14, [rdi+140h]
0x18001cf98  cmp     ebx, 0C0000023h
0x18001cf9e  jnz     loc_18001DF1B
0x18001cfa4  lea     r12, [rdi+8]
0x18001cfa8  jmp     loc_18001DF35
0x18001cfad  mov     r14, rsi
0x18001cfb0  test    rsi, rsi
0x18001cfb3  jz      short loc_18001CFD1
0x18001cfb5  mov     edx, [rsi]; unsigned int
0x18001cfb7  test    edx, edx
0x18001cfb9  jz      short loc_18001CFD1
0x18001cfbb  mov     rcx, [rsi+8]; Src
0x18001cfbf  mov     r8, rdi; struct _PKU2U_CONTEXT *
0x18001cfc2  call    ?Pku2uSaveSSPIMessage@@YAJPEAEKPEAU_PKU2U_CONTEXT@@@Z; Pku2uSaveSSPIMessage(uchar *,ulong,_PKU2U_CONTEXT *)
0x18001cfc7  mov     ebx, eax
0x18001cfc9  test    eax, eax
0x18001cfcb  js      loc_18001DE9D
0x18001cfd1  mov     rdx, [rsp+160h+var_F8]
0x18001cfd6  xor     r12d, r12d
0x18001cfd9  mov     edx, [rdx+4]
0x18001cfdc  test    edx, edx
0x18001cfde  jz      short loc_18001D00E
0x18001cfe0  mov     r9, [rsp+160h+var_F8]
0x18001cfe5  xor     ecx, ecx
0x18001cfe7  mov     r9, [r9+8]
0x18001cfeb  nop     dword ptr [rax+rax+00h]
0x18001cff0  mov     esi, ecx
0x18001cff2  add     rsi, rsi
0x18001cff5  mov     eax, [r9+rsi*8+4]
0x18001cffa  lea     r8, [r9+rsi*8]
0x18001cffe  and     eax, 0FFFFFFFh
0x18001d003  cmp     eax, 0Eh
0x18001d006  jz      short loc_18001D029
0x18001d008  inc     ecx
0x18001d00a  cmp     ecx, edx
0x18001d00c  jb      short loc_18001CFF0
0x18001d00e  cmp     [rdi+50h], r15
0x18001d012  jnz     loc_18001D0D4
0x18001d018  mov     ebx, 80090303h
0x18001d01d  lea     r13, WPP_GLOBAL_Control
0x18001d024  jmp     loc_18001DF1B
0x18001d029  mov     rax, cs:?Pku2uGlobalLsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * Pku2uGlobalLsaFunctions
0x18001d030  mov     rdx, r8
0x18001d033  mov     rcx, r8
0x18001d036  mov     rax, [rax+98h]
0x18001d03d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d042  mov     ebx, eax
0x18001d044  test    eax, eax
0x18001d046  js      loc_18001DE99
0x18001d04c  mov     rax, [rsp+160h+var_F8]
0x18001d051  mov     rax, [rax+8]
0x18001d055  mov     r12, [rax+rsi*8+8]
0x18001d05a  test    r12, r12
0x18001d05d  jz      short loc_18001D0C3
0x18001d05f  mov     edx, [rax+rsi*8]
0x18001d062  cmp     edx, 20h ; ' '
0x18001d065  jb      short loc_18001D0C3
0x18001d067  mov     r8d, [r12+4]
0x18001d06c  mov     r9d, [r12+10h]
0x18001d071  mov     r10d, [r12+18h]
0x18001d076  lea     rcx, [r8+20h]
0x18001d07a  lea     rax, [r10+r9]
0x18001d07e  add     rcx, rax
0x18001d081  cmp     rcx, rdx
0x18001d084  ja      short loc_18001D0C3
0x18001d086  mov     eax, [r12+8]
0x18001d08b  lea     rdx, [rax+r8]
0x18001d08f  cmp     rdx, rcx
0x18001d092  ja      short loc_18001D0C3
0x18001d094  cmp     rdx, rax
0x18001d097  jb      short loc_18001D0C3
0x18001d099  mov     eax, [r12+14h]
0x18001d09e  lea     rdx, [rax+r9]
0x18001d0a2  cmp     rdx, rcx
0x18001d0a5  ja      short loc_18001D0C3
0x18001d0a7  cmp     rdx, rax
0x18001d0aa  jb      short loc_18001D0C3
0x18001d0ac  mov     eax, [r12+1Ch]
0x18001d0b1  lea     rdx, [rax+r10]
0x18001d0b5  cmp     rdx, rcx
0x18001d0b8  ja      short loc_18001D0C3
0x18001d0ba  cmp     rdx, rax
0x18001d0bd  jnb     loc_18001D00E
0x18001d0c3  mov     ebx, 0C000000Dh
0x18001d0c8  lea     r13, WPP_GLOBAL_Control
0x18001d0cf  jmp     loc_18001DF1B
0x18001d0d4  test    r13, r13
0x18001d0d7  jz      short loc_18001D13E
0x18001d0d9  mov     rcx, r13; struct _PKU2U_SECONDARY_CREDENTIAL *
0x18001d0dc  mov     [rbp+60h+var_E0], r13
0x18001d0e0  call    ?Pku2uReferenceSecondaryCredential@@YAXPEAU_PKU2U_SECONDARY_CREDENTIAL@@@Z; Pku2uReferenceSecondaryCredential(_PKU2U_SECONDARY_CREDENTIAL *)
0x18001d0e5  mov     rcx, [rdi+10h]; struct _PKU2U_SECONDARY_CREDENTIAL *
0x18001d0e9  cmp     rcx, r13
0x18001d0ec  jz      short loc_18001D13E
0x18001d0ee  mov     r9d, [r13+20h]
0x18001d0f2  test    r9d, r9d
0x18001d0f5  jz      short loc_18001D12F
0x18001d0f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d0fe  lea     r13, WPP_GLOBAL_Control
0x18001d105  cmp     rcx, r13
0x18001d108  jz      short loc_18001D125
0x18001d10a  test    byte ptr [rcx+1Ch], 1
0x18001d10e  jz      short loc_18001D125
0x18001d110  mov     rcx, [rcx+10h]
0x18001d114  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids
0x18001d11b  mov     edx, 17h
0x18001d120  call    WPP_SF_d
0x18001d125  mov     ebx, 8009030Eh
0x18001d12a  jmp     loc_18001DF1B
0x18001d12f  call    ?Pku2uDereferenceSecondaryCredential@@YAXPEAU_PKU2U_SECONDARY_CREDENTIAL@@@Z; Pku2uDereferenceSecondaryCredential(_PKU2U_SECONDARY_CREDENTIAL *)
0x18001d134  xor     eax, eax
0x18001d136  mov     [rdi+10h], r13
0x18001d13a  mov     [rbp+60h+var_E0], rax
0x18001d13e  mov     r9d, [rdi+44h]
  ... truncated ...
```
