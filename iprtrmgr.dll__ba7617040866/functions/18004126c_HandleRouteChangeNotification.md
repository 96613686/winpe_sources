# HandleRouteChangeNotification

- ea: `0x18004126c`
- end: `0x1800422bf`
- name: `HandleRouteChangeNotification`
- size: `4179`
- prototype: `__int64 __fastcall(NET_LUID *InterfaceLuid)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180042620`

## callees

- `0x180011790`
- `0x18001797c`
- `0x180017a34`
- `0x18002f000`
- `0x18003f1a4`
- `0x180040be4`
- `0x18004126c`
- `0x180042cac`
- `0x1800435b4`
- `0x18004a120`
- `0x180051c80`
- `0x180051e88`
- `0x1800583cc`
- `0x18005851e`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180042294`
- `ntdll!RtlReleaseResource` at `0x180042294`
- `ntdll!RtlAcquireResourceShared` at `0x180041398`
- `ntdll!RtlAcquireResourceShared` at `0x180041398`
- `IPHLPAPI!ConvertLengthToIpv4Mask` at `0x1800413b1`
- `IPHLPAPI!ConvertLengthToIpv4Mask` at `0x1800413b1`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180041684`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x180041684`

## string_xrefs

- `0x180041bb6`: `HandleRouteChangeNotification: Failed to delete route %d.%d.%d.%d, error %d`
- `0x180041c33`: `HandleRouteChangeNotification: Failed to delete route: \n`
- `0x180041c51`: `HandleRouteChangeNotification: Failed to delete route. Error %d`

## pseudocode

```c
__int64 __fastcall HandleRouteChangeNotification(NET_LUID *InterfaceLuid, int a2, int a3, __int64 a4)
{
  unsigned int v4; // ebx
  __int128 *v8; // r9
  int v9; // r14d
  __int64 v10; // rdi
  unsigned int v11; // esi
  __int64 Value_low; // r8
  __int128 *v13; // r9
  __int64 *v14; // rdx
  char v15; // al
  int v16; // edx
  __int64 v17; // r9
  __int64 v18; // r8
  __int128 *v19; // rbx
  ULONG64 Value; // r9
  __int64 v21; // r8
  __int64 v22; // r8
  __int128 *v23; // r9
  __int128 *v24; // r9
  ULONG64 v25; // r8
  __int64 v26; // r8
  ULONG64 v27; // r8
  __int128 *v28; // r9
  ULONG v29; // r15d
  __int64 v30; // rax
  int v31; // edx
  __int64 v32; // r9
  __int64 v33; // r8
  __int128 v34; // xmm0
  __int128 *v35; // r9
  void *RtmHandleForProtocol; // rax
  __int64 v37; // r8
  int v38; // ecx
  __int64 v39; // r9
  __int64 v40; // r8
  int v41; // r10d
  int v42; // edx
  int v43; // r15d
  int v44; // esi
  int v45; // eax
  int v46; // ecx
  int v47; // r9d
  int v48; // ecx
  unsigned int v49; // esi
  int v50; // r15d
  unsigned int v51; // r14d
  int v52; // edi
  unsigned int v53; // ebx
  unsigned __int8 BestNextHopMaskGivenICB; // al
  int v55; // esi
  __int128 *v56; // r9
  int BestNextHopIPv6PrefixLengthGivenICB; // eax
  int v58; // ecx
  int v59; // eax
  int v60; // ecx
  const char *v61; // rdx
  __int64 v62; // r9
  __int64 v63; // r8
  __int64 v64; // rax
  __int128 *v65; // r9
  int v67[2]; // [rsp+20h] [rbp-9A8h]
  __int64 v68; // [rsp+20h] [rbp-9A8h]
  int v69[2]; // [rsp+20h] [rbp-9A8h]
  int v70[2]; // [rsp+28h] [rbp-9A0h]
  int v71[2]; // [rsp+28h] [rbp-9A0h]
  int v72[2]; // [rsp+30h] [rbp-998h]
  int v73[2]; // [rsp+30h] [rbp-998h]
  __int64 v74; // [rsp+38h] [rbp-990h]
  struct _GUID *v75; // [rsp+40h] [rbp-988h]
  __int64 v76; // [rsp+48h] [rbp-980h]
  unsigned int v77; // [rsp+60h] [rbp-968h]
  int v78; // [rsp+60h] [rbp-968h]
  _BYTE v79[4]; // [rsp+64h] [rbp-964h] BYREF
  int v80; // [rsp+68h] [rbp-960h]
  int v81; // [rsp+6Ch] [rbp-95Ch]
  ULONG Mask; // [rsp+70h] [rbp-958h] BYREF
  int v83; // [rsp+74h] [rbp-954h]
  __int128 Buf2; // [rsp+80h] [rbp-948h] BYREF
  ULONG InterfaceIndex; // [rsp+90h] [rbp-938h] BYREF
  int v86; // [rsp+94h] [rbp-934h]
  __int64 v87; // [rsp+98h] [rbp-930h]
  int v88[4]; // [rsp+A0h] [rbp-928h] BYREF
  __m256i v89; // [rsp+B0h] [rbp-918h]
  int v90[4]; // [rsp+D0h] [rbp-8F8h]
  __int64 v91; // [rsp+E0h] [rbp-8E8h]
  int v92[4]; // [rsp+F0h] [rbp-8D8h] BYREF
  __m256i Buf1; // [rsp+100h] [rbp-8C8h] BYREF
  __int128 v94; // [rsp+120h] [rbp-8A8h]
  __int64 v95; // [rsp+130h] [rbp-898h]
  __int128 v96; // [rsp+140h] [rbp-888h] BYREF
  int v97; // [rsp+150h] [rbp-878h] BYREF
  __int128 v98; // [rsp+154h] [rbp-874h]
  __int128 v99; // [rsp+164h] [rbp-864h]
  int v100; // [rsp+174h] [rbp-854h]
  int v101; // [rsp+180h] [rbp-848h] BYREF
  _BYTE v102[2044]; // [rsp+184h] [rbp-844h] BYREF

  v4 = a3;
  v80 = a2;
  v81 = a3;
  memset_0(v88, 0, 0x48u);
  InterfaceIndex = 0;
  Mask = 0;
  v101 = 0;
  memset_0(v102, 0, sizeof(v102));
  v97 = 0;
  v98 = 0;
  v100 = 0;
  v99 = 0;
  v96 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v101) = 0;
    LOWORD(v97) = 0;
    FormatRRASErrorString(&v101, L"Entered: %ws", L"HandleRouteChangeNotification");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v8 = &v96;
      if ( a4 )
        LODWORD(v8) = a4;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v101,
        (_DWORD)v8,
        0,
        (__int64)&v97);
    }
  }
  v9 = 1;
  v10 = 0;
  RtlAcquireResourceShared(&Resource, 1u);
  if ( !v4 )
  {
    PrintIpv6Route("HandleRouteChangeNotification:", a4, InterfaceLuid);
    if ( a2 || (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_31;
    v26 = *((unsigned int *)&InterfaceLuid[10].Info + 1);
    v77 = *((_DWORD *)&InterfaceLuid[11].Info + 1);
    LOWORD(v101) = 0;
    LOWORD(v97) = 0;
    FormatRRASErrorString(&v101, L"Metric : %d, Change : 0x%x", v26, v77);
    goto LABEL_27;
  }
  v11 = ConvertLengthToIpv4Mask(LOBYTE(InterfaceLuid[5].Value), &Mask);
  if ( v11 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      goto LABEL_151;
    Value_low = LOBYTE(InterfaceLuid[5].Value);
    LOWORD(v101) = 0;
    LOWORD(v97) = 0;
    FormatRRASErrorString(
      &v101,
      L"ERROR:HandleRouteChangeNotification: Failed to convert Destination Prefix length %d to Mask. error %d",
      Value_low,
      v11);
    goto LABEL_10;
  }
  v15 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v16 = *((unsigned __int8 *)&InterfaceLuid[2].Info + 2);
    v17 = BYTE1(InterfaceLuid[2].Value);
    v18 = LOBYTE(InterfaceLuid[2].Value);
    LOWORD(v101) = 0;
    LOWORD(v97) = 0;
    v70[0] = *((unsigned __int8 *)&InterfaceLuid[2].Info + 3);
    v67[0] = v16;
    FormatRRASErrorString(
      &v101,
      L"Change for route to %d.%d.%d.%d/%d.%d.%d.%d",
      v18,
      v17,
      *(_QWORD *)v67,
      *(_QWORD *)v70,
      (unsigned __int8)Mask,
      BYTE1(Mask),
      BYTE2(Mask),
      HIBYTE(Mask));
    v15 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v19 = &v96;
      if ( a4 )
        LODWORD(v19) = a4;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v101,
        (_DWORD)v19,
        0,
        (__int64)&v97);
      v15 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        Value = InterfaceLuid->Value;
        LODWORD(v74) = *((unsigned __int8 *)&InterfaceLuid[6].Info + 3);
        v72[0] = *((unsigned __int8 *)&InterfaceLuid[6].Info + 2);
        v70[0] = BYTE1(InterfaceLuid[6].Value);
        v21 = LODWORD(InterfaceLuid[11].Value);
        LOWORD(v101) = 0;
        LOWORD(v97) = 0;
        v67[0] = LOBYTE(InterfaceLuid[6].Value);
        FormatRRASErrorString(
          &v101,
          L"Proto : %d, via i/f %lx, nexthop %d.%d.%d.%d",
          v21,
          Value,
          *(_QWORD *)v67,
          *(_QWORD *)v70,
          *(_QWORD *)v72,
          v74);
        v15 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v101,
            (_DWORD)v19,
            0,
            (__int64)&v97);
          v15 = Microsoft_Windows_RRASEnableBits;
        }
      }
    }
    v4 = v81;
  }
  if ( !a2 && v15 < 0 )
  {
    v22 = *((unsigned int *)&InterfaceLuid[10].Info + 1);
    LOWORD(v101) = 0;
    LOWORD(v97) = 0;
    FormatRRASErrorString(&v101, L"Metric : %d, Change : 0x%x", v22, *((unsigned int *)&InterfaceLuid[11].Info + 1));
LABEL_27:
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v23 = &v96;
      if ( a4 )
        LODWORD(v23) = a4;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v101,
        (_DWORD)v23,
        0,
        (__int64)&v97);
    }
  }
LABEL_31:
  v11 = ConvertInterfaceLuidToIndex(InterfaceLuid, &InterfaceIndex);
  if ( v11 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v101) = 0;
      LOWORD(v97) = 0;
      FormatRRASErrorString(
        &v101,
        L"ERROR:HandleRouteChangeNotification:Failed to convert interface Luid to Index. error %d",
        v11);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v24 = &v96;
        if ( a4 )
          LODWORD(v24) = a4;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v101,
          (_DWORD)v24,
          0,
          (__int64)&v97);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v25 = InterfaceLuid->Value;
          LOWORD(v101) = 0;
          LOWORD(v97) = 0;
          FormatRRASErrorString(&v101, L"ERROR:HandleRouteChangeNotification: Failed Convert(0x%I64x)", v25);
LABEL_10:
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
            goto LABEL_151;
          v68 = 0;
          goto LABEL_12;
        }
      }
    }
    goto LABEL_151;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v27 = InterfaceLuid->Value;
    LOWORD(v101) = 0;
    LOWORD(v97) = 0;
    FormatRRASErrorString(&v101, L"INFO: Converted interface Luid 0x%I64x to Index %d. ", v27, InterfaceIndex);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v28 = &v96;
      if ( a4 )
        LODWORD(v28) = a4;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v101,
        (_DWORD)v28,
        0,
        (__int64)&v97);
    }
  }
  v29 = InterfaceIndex;
  v30 = InterfaceLookupByIfIndex(InterfaceIndex, v4);
  v87 = v30;
  v10 = v30;
  if ( !v30 )
  {
    if ( !v4 )
    {
      PrintIpv6Route("HandleRouteChangeNotification: Failed to handle route: \n", a4, InterfaceLuid);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v101) = 0;
        LOWORD(v97) = 0;
        FormatRRASErrorString(
          &v101,
          L"HandleRouteChangeNotification: Failed to handle route as interface context doesn't exist. Error %d",
          0);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v68 = 0;
LABEL_12:
          v13 = &v96;
          if ( a4 )
            LODWORD(v13) = a4;
LABEL_14:
          v14 = RasRtrMgrParamTraceError;
LABEL_15:
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (_DWORD)v14,
            (unsigned int)&v101,
            (_DWORD)v13,
            v68,
            (__int64)&v97);
          goto LABEL_151;
        }
      }
      goto LABEL_151;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_151;
    v31 = *((unsigned __int8 *)&InterfaceLuid[2].Info + 2);
    v32 = BYTE1(InterfaceLuid[2].Value);
    v33 = LOBYTE(InterfaceLuid[2].Value);
    LOWORD(v101) = 0;
    LOWORD(v97) = 0;
    LODWORD(v76) = HIBYTE(Mask);
    LODWORD(v75) = BYTE2(Mask);
    LODWORD(v74) = BYTE1(Mask);
    v72[0] = (unsigned __int8)Mask;
    v70[0] = *((unsigned __int8 *)&InterfaceLuid[2].Info + 3);
    v67[0] = v31;
    FormatRRASErrorString(
      &v101,
      L"HandleRouteChangeNotification:Failed to handle route to %d.%d.%d.%d/%d.%d.%d.%d. Interface index %d not present wi"
       "th router manager",
      v33,
      v32,
      *(_QWORD *)v67,
      *(_QWORD *)v70,
      *(_QWORD *)v72,
      v74,
      v75,
      v76,
      v29);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_151;
    v13 = &v96;
    if ( a4 )
      LODWORD(v13) = a4;
    v68 = 0;
LABEL_77:
    v14 = RasRtrmgrParamTraceInfo;
    goto LABEL_15;
  }
  if ( (unsigned int)(*(_DWORD *)(v30 + 144) - 1) <= 1 )
  {
    if ( !v4 )
    {
      PrintIpv6Route("HandleRouteChangeNotification: Not handling DoD route: \n", a4, InterfaceLuid);
      goto LABEL_151;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_151;
    v60 = *((unsigned __int8 *)&InterfaceLuid[2].Info + 2);
    v61 = "deletion";
    v62 = BYTE1(InterfaceLuid[2].Value);
    v63 = LOBYTE(InterfaceLuid[2].Value);
    LOWORD(v101) = 0;
    LOWORD(v97) = 0;
    if ( !v80 )
      v61 = "addition";
    v70[0] = *((unsigned __int8 *)&InterfaceLuid[2].Info + 3);
    v67[0] = v60;
    FormatRRASErrorString(
      &v101,
      L"HandleRouteChangeNotification: Not handling DoD route %d.%d.%d.%d %hs",
      v63,
      v62,
      *(_QWORD *)v67,
      *(_QWORD *)v70,
      v61);
    goto LABEL_81;
  }
  if ( v80 )
  {
    HIDWORD(v91) = v4;
    v90[0] = v29;
    if ( v4 )
    {
      v88[0] = InterfaceLuid[2].Value;
      v88[1] = Mask;
      v88[3] = InterfaceLuid[6].Value;
      v90[2] = InterfaceLuid[11].Value;
    }
    else
    {
      v34 = *(_OWORD *)((char *)&InterfaceLuid[6].Info + 4);
      v88[0] = *((_DWORD *)&InterfaceLuid[2].Info + 1);
      v88[1] = InterfaceLuid[3].Value;
      v88[2] = *((_DWORD *)&InterfaceLuid[3].Info + 1);
      v88[3] = InterfaceLuid[4].Value;
      v89.m256i_i32[0] = LOBYTE(InterfaceLuid[5].Value);
      v90[2] = InterfaceLuid[11].Value;
      v79[0] = 0;
      *(_OWORD *)((char *)v89.m256i_i64 + 4) = v34;
      RowToRTMFlags(InterfaceLuid, v79);
      v89.m256i_i32[6] |= v79[0];
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v101) = 0;
        LOWORD(v97) = 0;
        FormatRRASErrorString(&v101, L"HandleRouteChangeNotification RtInfo.FlagsFlags1 (%d)  ");
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v35 = &v96;
          if ( v10 != -688 )
            LODWORD(v35) = v10 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v101,
            (_DWORD)v35,
            *(_QWORD *)(v10 + 72),
            (__int64)&v97);
        }
      }
    }
    *(_OWORD *)v92 = *(_OWORD *)v88;
    Buf1 = v89;
    v95 = v91;
    v94 = *(_OWORD *)v90;
    RtmHandleForProtocol = (void *)GetRtmHandleForProtocol((unsigned int)v90[2], v4, v10 + 688);
    v11 = DeleteSingleRoute((__int64)v92, RtmHandleForProtocol, v37, (struct _GUID *)(v10 + 688));
    if ( !v11 )
      goto LABEL_151;
    if ( v4 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v38 = *((unsigned __int8 *)&InterfaceLuid[2].Info + 2);
        v39 = BYTE1(InterfaceLuid[2].Value);
        v40 = LOBYTE(InterfaceLuid[2].Value);
        LOWORD(v101) = 0;
        LOWORD(v97) = 0;
        v72[0] = v11;
        v70[0] = *((unsigned __int8 *)&InterfaceLuid[2].Info + 3);
        v67[0] = v38;
        FormatRRASErrorString(
          &v101,
          L"HandleRouteChangeNotification: Failed to delete route %d.%d.%d.%d, error %d",
          v40,
          v39,
          *(_QWORD *)v67,
          *(_QWORD *)v70,
          *(_QWORD *)v72);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v13 = &v96;
          if ( v10 != -688 )
            LODWORD(v13) = v10 + 688;
          v68 = *(_QWORD *)(v10 + 72);
          goto LABEL_14;
        }
      }
      goto LABEL_151;
    }
    PrintIpv6Route("HandleRouteChangeNotification: Failed to delete route: \n", a4, InterfaceLuid);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_151;
    LOWORD(v101) = 0;
    LOWORD(v97) = 0;
    FormatRRASErrorString(&v101, L"HandleRouteChangeNotification: Failed to delete route. Error %d", v11);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_151;
    v13 = &v96;
    if ( v10 != -688 )
      LODWORD(v13) = v10 + 688;
    goto LABEL_76;
  }
  v11 = ConvertMib2RouteToRouteInfo(InterfaceLuid, v4, v88);
  if ( v11 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_151;
    LOWORD(v101) = 0;
    LOWORD(v97) = 0;
    FormatRRASErrorString(
      &v101,
      L"ERROR:HandleRouteChangeNotification:Failed to convert MIB_IPFORWARD_ROW2 route into route info. error %d",
      v11);
LABEL_81:
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_151;
    v13 = &v96;
    if ( v10 != -688 )
      LODWORD(v13) = v10 + 688;
    goto LABEL_76;
  }
  v86 = 1;
  LOWORD(v41) = 0;
  v78 = 0;
  v83 = 0;
  if ( v90[2] == 2 )
  {
    Buf1 = v89;
    v95 = v91;
    v42 = _mm_cvtsi128_si32(*(__m128i *)v89.m256i_i8);
    v43 = _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)v88, 4));
    *(_OWORD *)v92 = *(_OWORD *)v88;
    v94 = *(_OWORD *)v90;
    v80 = v42;
    v44 = _mm_cvtsi128_si32(*(__m128i *)v88);
    if ( HIDWORD(v91) )
    {
      if ( _mm_srli_si128(*(__m128i *)v88, 8).m128i_i32[1] == 16777343 )
        goto LABEL_90;
    }
    else
    {
      *(_QWORD *)&Buf2 = 0;
      *((_QWORD *)&Buf2 + 1) = 0x10000000000000LL;
      v45 = memcmp_0((char *)Buf1.m256i_i64 + 4, &Buf2, 0x10u);
      v42 = v80;
      if ( !v45 )
      {
LABEL_90:
        v4 = v81;
        v41 = 64;
        goto LABEL_98;
      }
      LOWORD(v41) = v83;
    }
    if ( v4 )
    {
      if ( v43 == -1 || (v44 & (unsigned int)v43) >= 0xE0 )
      {
LABEL_99:
        if ( HIDWORD(v91) )
        {
          if ( (v44 & 0x80u) != 0 )
          {
            if ( (v44 & 0xC0) == 0x80 )
            {
              v46 = -65536;
            }
            else
            {
              v46 = 0;
              if ( (v44 & 0xE0) == 0xC0 )
                v46 = -16777216;
            }
          }
          else
          {
            v46 = -256;
          }
          if ( (unsigned __int8)v44 < 0xE0u && v44 != (v46 | v44) )
            goto LABEL_108;
        }
        else if ( (_BYTE)v44 != 0xFF )
        {
LABEL_108:
          if ( v4 )
          {
            if ( v43 == -1 )
              goto LABEL_120;
          }
          else if ( v42 == 128 )
          {
            goto LABEL_131;
          }
          v78 = 1;
          goto LABEL_115;
        }
        v86 = 0;
        goto LABEL_119;
      }
    }
    else if ( v42 == 128 )
    {
      goto LABEL_99;
    }
    v41 = 16;
LABEL_98:
    v83 = v41;
    goto LABEL_99;
  }
LABEL_115:
  if ( v90[2] == 3 )
  {
    if ( !(unsigned int)IsDefaultRoute(v88, v4) )
      v47 = 1;
    v78 = v47;
  }
LABEL_119:
  if ( v4 )
  {
LABEL_120:
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
    {
      v55 = v78;
    }
    else
    {
      LOWORD(v101) = 0;
      LOWORD(v97) = 0;
      v48 = *(_DWORD *)(v10 + 144);
      if ( (unsigned int)(v48 - 1) <= 1 || (v80 = 0, v48 == 7) )
        v80 = 1;
      v49 = v88[3];
      v50 = (unsigned __int16)v41;
      v51 = (unsigned int)GetBestNextHopMaskGivenICB(v10, (unsigned int)v88[3]) >> 24;
      v52 = (unsigned __int8)((unsigned int)GetBestNextHopMaskGivenICB(v10, v49) >> 16);
      v53 = (unsigned __int8)((unsigned __int16)GetBestNextHopMaskGivenICB(v87, v49) >> 8);
      BestNextHopMaskGivenICB = GetBestNextHopMaskGivenICB(v87, v49);
      v55 = v78;
      LODWORD(v76) = v80;
      LODWORD(v75) = v78;
      LODWORD(v74) = v86;
      v72[0] = v50;
      v70[0] = v51;
      v67[0] = v52;
      FormatRRASErrorString(
        &v101,
        L"NHOP mask %d.%d.%d.%d, Flag 0x%x, Valid %d, Stack %d, P2P %d",
        BestNextHopMaskGivenICB,
        v53,
        *(_QWORD *)v67,
        *(_QWORD *)v70,
        *(_QWORD *)v72,
        v74,
        v75,
        v76);
      v10 = v87;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v56 = &v96;
        if ( v87 != -688 )
          LODWORD(v56) = v87 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v101,
          (_DWORD)v56,
          *(_QWORD *)(v87 + 72),
          (__int64)&v97);
      }
      v4 = v81;
      v9 = 1;
    }
    BestNextHopIPv6PrefixLengthGivenICB = GetBestNextHopMaskGivenICB(v10, (unsigned int)v88[3]);
    goto LABEL_132;
  }
LABEL_131:
  Buf2 = *(_OWORD *)((char *)v89.m256i_i64 + 4);
  BestNextHopIPv6PrefixLengthGivenICB = GetBestNextHopIPv6PrefixLengthGivenICB(v10, &Buf2);
  v55 = v78;
LABEL_132:
  v58 = *(_DWORD *)(v10 + 144);
  if ( (unsigned int)(v58 - 1) > 1 && v58 != 7 )
    v9 = 0;
  v59 = AddSingleRoute(
          v90[0],
          (int)v88,
          BestNextHopIPv6PrefixLengthGivenICB,
          (unsigned __int16)v83,
          v86,
          v55,
          v9,
          v4,
          (struct _GUID *)(v10 + 688),
          0);
  v11 = v59;
  if ( v59 )
  {
    if ( v4 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_151;
      LOWORD(v101) = 0;
      LOWORD(v97) = 0;
      v73[0] = v59;
      v71[0] = HIBYTE(v88[0]);
      v69[0] = BYTE2(v88[0]);
      FormatRRASErrorString(
        &v101,
        L"HandleRouteChangeNotification: Failed to add route %d.%d.%d.%d, error %d",
        LOBYTE(v88[0]),
        BYTE1(v88[0]),
        *(_QWORD *)v69,
        *(_QWORD *)v71,
        *(_QWORD *)v73);
    }
    else
    {
      PrintIpv6Route("HandleRouteChangeNotification: Failed to add ", a4, InterfaceLuid);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_151;
      LOWORD(v101) = 0;
      LOWORD(v97) = 0;
      FormatRRASErrorString(&v101, L"HandleRouteChangeNotification: Failed to error %d", v11);
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v13 = &v96;
      if ( v10 != -688 )
        LODWORD(v13) = v10 + 688;
LABEL_76:
      v68 = *(_QWORD *)(v10 + 72);
      goto LABEL_77;
    }
  }
LABEL_151:
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v64 = 0;
    LOWORD(v97) = 0;
    if ( v10 )
      v64 = *(_QWORD *)(v10 + 72);
    v65 = &v96;
    if ( a4 )
      LODWORD(v65) = a4;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Leaving: HandleRouteChangeNotification",
      (_DWORD)v65,
      v64,
      (__int64)&v97);
  }
  RtlReleaseResource(&Resource);
  return v11;
}

```

## disassembly

```asm
0x18004126c  push    rbx
0x18004126e  push    rsi
0x18004126f  push    rdi
0x180041270  push    r12
0x180041272  push    r13
0x180041274  push    r14
0x180041276  push    r15
0x180041278  sub     rsp, 990h
0x18004127f  mov     rax, cs:__security_cookie
0x180041286  xor     rax, rsp
0x180041289  mov     [rsp+9C8h+var_48], rax
0x180041291  mov     ebx, r8d
0x180041294  mov     [rsp+9C8h+var_960], edx
0x180041298  mov     r15d, edx
0x18004129b  mov     [rsp+9C8h+var_95C], ebx
0x18004129f  xor     edx, edx; Val
0x1800412a1  mov     r12, rcx
0x1800412a4  lea     rcx, [rsp+9C8h+var_928]; void *
0x1800412ac  mov     r13, r9
0x1800412af  lea     r8d, [rdx+48h]; Size
0x1800412b3  call    memset_0
0x1800412b8  xor     esi, esi
0x1800412ba  lea     rcx, [rsp+9C8h+var_844]; void *
0x1800412c2  xor     edx, edx; Val
0x1800412c4  mov     [rsp+9C8h+InterfaceIndex], esi
0x1800412cb  mov     r8d, 7FCh; Size
0x1800412d1  mov     [rsp+9C8h+Mask], esi
0x1800412d5  mov     [rsp+9C8h+var_848], esi
0x1800412dc  call    memset_0
0x1800412e1  xorps   xmm0, xmm0
0x1800412e4  mov     [rsp+9C8h+var_878], esi
0x1800412eb  xor     eax, eax
0x1800412ed  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x1800412f4  movups  [rsp+9C8h+var_874], xmm0
0x1800412fc  mov     [rsp+9C8h+var_854], eax
0x180041303  movups  [rsp+9C8h+var_864], xmm0
0x18004130b  movups  [rsp+9C8h+var_888], xmm0
0x180041313  jge     short loc_180041385
0x180041315  lea     r8, aHandleroutecha_4; "HandleRouteChangeNotification"
0x18004131c  mov     word ptr [rsp+9C8h+var_848], si
0x180041324  lea     rdx, aEnteredWs; "Entered: %ws"
0x18004132b  mov     word ptr [rsp+9C8h+var_878], si
0x180041333  lea     rcx, [rsp+9C8h+var_848]
0x18004133b  call    FormatRRASErrorString
0x180041340  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x180041347  jge     short loc_180041385
0x180041349  test    r13, r13
0x18004134c  lea     rax, [rsp+9C8h+var_878]
0x180041354  mov     qword ptr [rsp+9C8h+var_9A0], rax
0x180041359  lea     r9, [rsp+9C8h+var_888]
0x180041361  cmovnz  r9, r13
0x180041365  mov     qword ptr [rsp+9C8h+var_9A8], rsi
0x18004136a  lea     r8, [rsp+9C8h+var_848]
0x180041372  lea     rdx, RasRtrmgrParamTraceInfo
0x180041379  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180041380  call    McTemplateU0zjzz_EventWriteTransfer
0x180041385  mov     r14d, 1
0x18004138b  lea     rcx, Resource; Resource
0x180041392  mov     dl, r14b; Wait
0x180041395  mov     rdi, rsi
0x180041398  call    cs:__imp_RtlAcquireResourceShared
0x18004139e  test    ebx, ebx
0x1800413a0  jz      loc_180041751
0x1800413a6  movzx   ecx, byte ptr [r12+28h]; MaskLength
0x1800413ac  lea     rdx, [rsp+9C8h+Mask]; Mask
0x1800413b1  call    cs:__imp_ConvertLengthToIpv4Mask
0x1800413b7  mov     esi, eax
0x1800413b9  test    eax, eax
0x1800413bb  jz      loc_18004144D
0x1800413c1  lea     ebx, [r14+3Fh]
0x1800413c5  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x1800413cb  jz      loc_180042236
0x1800413d1  movzx   r8d, byte ptr [r12+28h]
0x1800413d7  lea     rdx, aErrorHandlerou_1; "ERROR:HandleRouteChangeNotification: Fa"...
0x1800413de  xor     eax, eax
0x1800413e0  lea     rcx, [rsp+9C8h+var_848]
0x1800413e8  mov     r9d, esi
0x1800413eb  mov     word ptr [rsp+9C8h+var_848], ax
0x1800413f3  mov     word ptr [rsp+9C8h+var_878], ax
0x1800413fb  call    FormatRRASErrorString
0x180041400  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180041406  jz      loc_180042236
0x18004140c  lea     rax, [rsp+9C8h+var_878]
0x180041414  mov     qword ptr [rsp+9C8h+var_9A0], rax
0x180041419  mov     qword ptr [rsp+9C8h+var_9A8], rdi
0x18004141e  test    r13, r13
0x180041421  lea     r9, [rsp+9C8h+var_888]
0x180041429  cmovnz  r9, r13
0x18004142d  lea     rdx, RasRtrMgrParamTraceError
0x180041434  lea     r8, [rsp+9C8h+var_848]
0x18004143c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180041443  call    McTemplateU0zjzz_EventWriteTransfer
0x180041448  jmp     loc_180042236
0x18004144d  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180041454  test    al, al
0x180041456  jns     loc_1800415CD
0x18004145c  mov     ecx, [rsp+9C8h+Mask]
0x180041460  xor     eax, eax
0x180041462  movzx   edx, byte ptr [r12+12h]
0x180041468  mov     ebx, ecx
0x18004146a  movzx   r9d, byte ptr [r12+11h]
0x180041470  movzx   r8d, byte ptr [r12+10h]
0x180041476  mov     word ptr [rsp+9C8h+var_848], ax
0x18004147e  mov     word ptr [rsp+9C8h+var_878], ax
0x180041486  mov     eax, ecx
0x180041488  shr     eax, 10h
0x18004148b  movzx   r11d, al
0x18004148f  mov     eax, ecx
0x180041491  shr     eax, 8
0x180041494  movzx   r10d, al
0x180041498  movzx   eax, cl
0x18004149b  movzx   ecx, byte ptr [r12+13h]
0x1800414a1  shr     ebx, 18h
0x1800414a4  mov     dword ptr [rsp+9C8h+var_980], ebx
0x1800414a8  mov     dword ptr [rsp+9C8h+var_988], r11d
0x1800414ad  mov     dword ptr [rsp+9C8h+var_990], r10d
0x1800414b2  mov     [rsp+9C8h+var_998], eax
0x1800414b6  mov     [rsp+9C8h+var_9A0], ecx
0x1800414ba  lea     rcx, [rsp+9C8h+var_848]
0x1800414c2  mov     [rsp+9C8h+var_9A8], edx
0x1800414c6  lea     rdx, aChangeForRoute; "Change for route to %d.%d.%d.%d/%d.%d.%"...
0x1800414cd  call    FormatRRASErrorString
0x1800414d2  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800414d9  test    al, al
0x1800414db  jns     loc_1800415C9
0x1800414e1  lea     rax, [rsp+9C8h+var_878]
0x1800414e9  test    r13, r13
0x1800414ec  mov     qword ptr [rsp+9C8h+var_9A0], rax
0x1800414f1  lea     rbx, [rsp+9C8h+var_888]
0x1800414f9  cmovnz  rbx, r13
0x1800414fd  mov     qword ptr [rsp+9C8h+var_9A8], rdi
0x180041502  mov     r9, rbx
0x180041505  lea     r8, [rsp+9C8h+var_848]
0x18004150d  lea     rdx, RasRtrmgrParamTraceInfo
0x180041514  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004151b  call    McTemplateU0zjzz_EventWriteTransfer
0x180041520  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180041527  test    al, al
0x180041529  jns     loc_1800415C9
0x18004152f  movzx   ecx, byte ptr [r12+33h]
0x180041535  xor     eax, eax
0x180041537  movzx   edx, byte ptr [r12+32h]
0x18004153d  movzx   r8d, byte ptr [r12+31h]
0x180041543  mov     r9, [r12]
0x180041547  mov     dword ptr [rsp+9C8h+var_990], ecx
0x18004154b  lea     rcx, [rsp+9C8h+var_848]
0x180041553  mov     [rsp+9C8h+var_998], edx
0x180041557  lea     rdx, aProtoDViaIFLxN; "Proto : %d, via i/f %lx, nexthop %d.%d."...
0x18004155e  mov     [rsp+9C8h+var_9A0], r8d
0x180041563  mov     r8d, [r12+58h]
0x180041568  mov     word ptr [rsp+9C8h+var_848], ax
0x180041570  mov     word ptr [rsp+9C8h+var_878], ax
0x180041578  movzx   eax, byte ptr [r12+30h]
0x18004157e  mov     [rsp+9C8h+var_9A8], eax
0x180041582  call    FormatRRASErrorString
0x180041587  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004158e  test    al, al
0x180041590  jns     short loc_1800415C9
0x180041592  lea     rax, [rsp+9C8h+var_878]
0x18004159a  mov     r9, rbx
0x18004159d  mov     qword ptr [rsp+9C8h+var_9A0], rax
0x1800415a2  lea     r8, [rsp+9C8h+var_848]
0x1800415aa  lea     rdx, RasRtrmgrParamTraceInfo
0x1800415b1  mov     qword ptr [rsp+9C8h+var_9A8], rdi
0x1800415b6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800415bd  call    McTemplateU0zjzz_EventWriteTransfer
0x1800415c2  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800415c9  mov     ebx, [rsp+9C8h+var_95C]
0x1800415cd  test    r15d, r15d
0x1800415d0  jnz     loc_180041679
0x1800415d6  test    al, al
0x1800415d8  jns     loc_180041679
0x1800415de  mov     r8d, [r12+54h]
0x1800415e3  lea     rdx, aMetricDChange0; "Metric : %d, Change : 0x%x"
0x1800415ea  xor     eax, eax
0x1800415ec  lea     rcx, [rsp+9C8h+var_848]
0x1800415f4  mov     word ptr [rsp+9C8h+var_848], ax
0x1800415fc  mov     word ptr [rsp+9C8h+var_878], ax
0x180041604  mov     al, [r12+5Ch]
0x180041609  mov     byte ptr [rsp+9C8h+var_968], al
0x18004160d  mov     al, [r12+5Dh]
0x180041612  mov     byte ptr [rsp+9C8h+var_968+1], al
0x180041616  mov     al, [r12+5Eh]
0x18004161b  mov     byte ptr [rsp+9C8h+var_968+2], al
0x18004161f  mov     al, [r12+5Fh]
0x180041624  mov     byte ptr [rsp+9C8h+var_968+3], al
0x180041628  mov     r9d, [rsp+9C8h+var_968]
0x18004162d  call    FormatRRASErrorString
0x180041632  xor     esi, esi
0x180041634  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x18004163b  jge     short loc_180041679
0x18004163d  test    r13, r13
0x180041640  lea     rax, [rsp+9C8h+var_878]
0x180041648  mov     qword ptr [rsp+9C8h+var_9A0], rax
0x18004164d  lea     r9, [rsp+9C8h+var_888]
0x180041655  cmovnz  r9, r13
0x180041659  mov     qword ptr [rsp+9C8h+var_9A8], rsi
0x18004165e  lea     r8, [rsp+9C8h+var_848]
0x180041666  lea     rdx, RasRtrmgrParamTraceInfo
0x18004166d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180041674  call    McTemplateU0zjzz_EventWriteTransfer
0x180041679  lea     rdx, [rsp+9C8h+InterfaceIndex]; InterfaceIndex
0x180041681  mov     rcx, r12; InterfaceLuid
0x180041684  call    cs:__imp_ConvertInterfaceLuidToIndex
0x18004168a  mov     esi, eax
0x18004168c  test    eax, eax
0x18004168e  jz      loc_1800417D0
0x180041694  mov     ebx, 40h ; '@'
0x180041699  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18004169f  jz      loc_180042236
0x1800416a5  xor     eax, eax
0x1800416a7  lea     rdx, aErrorHandlerou; "ERROR:HandleRouteChangeNotification:Fai"...
0x1800416ae  mov     r8d, esi
0x1800416b1  mov     word ptr [rsp+9C8h+var_848], ax
0x1800416b9  lea     rcx, [rsp+9C8h+var_848]
0x1800416c1  mov     word ptr [rsp+9C8h+var_878], ax
0x1800416c9  call    FormatRRASErrorString
0x1800416ce  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x1800416d4  jz      loc_180042236
0x1800416da  lea     rax, [rsp+9C8h+var_878]
0x1800416e2  test    r13, r13
0x1800416e5  mov     qword ptr [rsp+9C8h+var_9A0], rax
0x1800416ea  lea     r9, [rsp+9C8h+var_888]
0x1800416f2  cmovnz  r9, r13
0x1800416f6  mov     qword ptr [rsp+9C8h+var_9A8], rdi
0x1800416fb  lea     r8, [rsp+9C8h+var_848]
0x180041703  lea     rdx, RasRtrMgrParamTraceError
0x18004170a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180041711  call    McTemplateU0zjzz_EventWriteTransfer
0x180041716  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18004171c  jz      loc_180042236
0x180041722  mov     r8, [r12]
0x180041726  lea     rdx, aErrorHandlerou_0; "ERROR:HandleRouteChangeNotification: Fa"...
0x18004172d  xor     eax, eax
0x18004172f  lea     rcx, [rsp+9C8h+var_848]
0x180041737  mov     word ptr [rsp+9C8h+var_848], ax
0x18004173f  mov     word ptr [rsp+9C8h+var_878], ax
0x180041747  call    FormatRRASErrorString
0x18004174c  jmp     loc_180041400
0x180041751  mov     r8, r12
0x180041754  lea     rcx, aHandleroutecha; "HandleRouteChangeNotification:"
0x18004175b  mov     rdx, r13
0x18004175e  call    PrintIpv6Route
0x180041763  test    r15d, r15d
0x180041766  jnz     loc_180041679
0x18004176c  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x180041773  jge     loc_180041679
0x180041779  mov     al, [r12+5Ch]
0x18004177e  lea     rdx, aMetricDChange0; "Metric : %d, Change : 0x%x"
0x180041785  mov     r8d, [r12+54h]
0x18004178a  lea     rcx, [rsp+9C8h+var_848]
0x180041792  mov     byte ptr [rsp+9C8h+var_968], al
0x180041796  mov     al, [r12+5Dh]
0x18004179b  mov     byte ptr [rsp+9C8h+var_968+1], al
0x18004179f  mov     al, [r12+5Eh]
0x1800417a4  mov     byte ptr [rsp+9C8h+var_968+2], al
0x1800417a8  mov     al, [r12+5Fh]
0x1800417ad  mov     byte ptr [rsp+9C8h+var_968+3], al
0x1800417b1  mov     r9d, [rsp+9C8h+var_968]
0x1800417b6  mov     word ptr [rsp+9C8h+var_848], si
0x1800417be  mov     word ptr [rsp+9C8h+var_878], si
0x1800417c6  call    FormatRRASErrorString
0x1800417cb  jmp     loc_180041634
0x1800417d0  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x1800417d7  jge     short loc_180041850
0x1800417d9  mov     r9d, [rsp+9C8h+InterfaceIndex]
0x1800417e1  lea     rdx, aInfoConvertedI; "INFO: Converted interface Luid 0x%I64x "...
0x1800417e8  mov     r8, [r12]
0x1800417ec  lea     rcx, [rsp+9C8h+var_848]
0x1800417f4  xor     eax, eax
0x1800417f6  mov     word ptr [rsp+9C8h+var_848], ax
0x1800417fe  mov     word ptr [rsp+9C8h+var_878], ax
0x180041806  call    FormatRRASErrorString
0x18004180b  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180041812  jge     short loc_180041850
0x180041814  test    r13, r13
0x180041817  lea     rax, [rsp+9C8h+var_878]
0x18004181f  mov     qword ptr [rsp+9C8h+var_9A0], rax
0x180041824  lea     r9, [rsp+9C8h+var_888]
0x18004182c  cmovnz  r9, r13
0x180041830  mov     qword ptr [rsp+9C8h+var_9A8], rdi
0x180041835  lea     r8, [rsp+9C8h+var_848]
0x18004183d  lea     rdx, RasRtrmgrParamTraceInfo
0x180041844  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004184b  call    McTemplateU0zjzz_EventWriteTransfer
0x180041850  mov     r15d, [rsp+9C8h+InterfaceIndex]
0x180041858  mov     edx, ebx
0x18004185a  mov     ecx, r15d
0x18004185d  call    InterfaceLookupByIfIndex
0x180041862  mov     [rsp+9C8h+var_930], rax
0x18004186a  mov     rdi, rax
0x18004186d  test    rax, rax
0x180041870  jnz     loc_1800419AB
0x180041876  test    ebx, ebx
0x180041878  jz      loc_180041938
0x18004187e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, al
0x180041884  jge     loc_180042236
0x18004188a  movzx   edx, byte ptr [r12+12h]
0x180041890  xor     ecx, ecx
0x180041892  movzx   r9d, byte ptr [r12+11h]
  ... truncated ...
```
