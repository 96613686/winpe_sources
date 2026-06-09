# PlaiGetOffloadInfo(IXMLDOMDocument *,IXMLDOMElement *,_IP_ADAPTER_ADDRESSES_LH *)

- ea: `0x18005e3a8`
- end: `0x18005f49a`
- name: `?PlaiGetOffloadInfo@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEAU_IP_ADAPTER_ADDRESSES_LH@@@Z`
- size: `4338`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument *, struct IXMLDOMElement *, struct _IP_ADAPTER_ADDRESSES_LH *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180102ae8`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18001cbe0`
- `0x18002b3a0`
- `0x18005e3a8`
- `0x18013aee0`

## import_xrefs

- `NSI!NsiFreeTable` at `0x18005ec31`
- `NSI!NsiFreeTable` at `0x18005f468`
- `NSI!NsiFreeTable` at `0x18005ec31`
- `NSI!NsiFreeTable` at `0x18005f468`
- `NSI!NsiAllocateAndGetTable` at `0x18005e452`
- `NSI!NsiAllocateAndGetTable` at `0x18005ec8b`
- `NSI!NsiAllocateAndGetTable` at `0x18005e452`
- `NSI!NsiAllocateAndGetTable` at `0x18005ec8b`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18005e3f0`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18005e3f0`

## pseudocode

```c
__int64 __fastcall PlaiGetOffloadInfo(
        struct IXMLDOMDocument *a1,
        struct IXMLDOMElement *a2,
        struct _IP_ADAPTER_ADDRESSES_LH *a3)
{
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // r12d
  unsigned int Table; // eax
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rax
  int *v11; // r9
  unsigned int i; // ecx
  __int64 v13; // rdi
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  unsigned int v34; // eax
  int v35; // eax
  __int64 v36; // rax
  unsigned int j; // ecx
  __int64 v38; // rdi
  int v39; // eax
  __int64 v40; // rax
  int v41; // eax
  __int64 v42; // rax
  int v43; // eax
  __int64 v44; // rax
  int v45; // eax
  __int64 v46; // rax
  int v47; // eax
  __int64 v48; // rax
  int v49; // eax
  __int64 v50; // rax
  int v51; // eax
  __int64 v52; // rax
  int v53; // eax
  __int64 v54; // rax
  int v55; // eax
  __int64 v56; // rax
  int v57; // eax
  __int64 v58; // rax
  int *v60; // [rsp+38h] [rbp-C8h]
  int v61; // [rsp+60h] [rbp-A0h]
  char v62; // [rsp+60h] [rbp-A0h]
  int v63; // [rsp+70h] [rbp-90h] BYREF
  int v64; // [rsp+78h] [rbp-88h] BYREF
  __int64 v65; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v66; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v67[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v68[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v69[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v70[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v71[64]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v72[64]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v73[64]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v74[64]; // [rsp+3A0h] [rbp+2A0h] BYREF
  unsigned __int16 v75[64]; // [rsp+420h] [rbp+320h] BYREF
  unsigned __int16 v76[64]; // [rsp+4A0h] [rbp+3A0h] BYREF
  unsigned __int16 v77[64]; // [rsp+520h] [rbp+420h] BYREF
  unsigned __int16 v78[64]; // [rsp+5A0h] [rbp+4A0h] BYREF
  unsigned __int16 v79[64]; // [rsp+620h] [rbp+520h] BYREF
  unsigned __int16 v80[64]; // [rsp+6A0h] [rbp+5A0h] BYREF
  unsigned __int16 v81[64]; // [rsp+720h] [rbp+620h] BYREF
  unsigned __int16 v82[64]; // [rsp+7A0h] [rbp+6A0h] BYREF
  unsigned __int16 v83[64]; // [rsp+820h] [rbp+720h] BYREF
  unsigned __int16 v84[64]; // [rsp+8A0h] [rbp+7A0h] BYREF
  unsigned __int16 v85[64]; // [rsp+920h] [rbp+820h] BYREF
  unsigned __int16 v86[64]; // [rsp+9A0h] [rbp+8A0h] BYREF
  unsigned __int16 v87[64]; // [rsp+A20h] [rbp+920h] BYREF
  unsigned __int16 v88[64]; // [rsp+AA0h] [rbp+9A0h] BYREF
  unsigned __int16 v89[64]; // [rsp+B20h] [rbp+A20h] BYREF

  v66 = 0;
  v67[0] = 0;
  v65 = 0;
  CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
  if ( SLOBYTE(a3->Flags) >= 0 )
    goto LABEL_96;
  v62 = 0;
  Table = NsiAllocateAndGetTable(1, &NPI_MS_IPV4_MODULEID, 7, v67, 8, 0, 0, &v65, 88, 0, 0, &v66, v62);
  v8 = PlaiHResultFromWin32(Table);
  v9 = v8;
  if ( v8 >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= v66 )
        goto LABEL_96;
      v13 = 88LL * i;
      if ( CurrentThreadCompartmentId == *(_DWORD *)(v13 + v65 + 4) && a3->IfIndex == *(_DWORD *)(v13 + v65) )
        break;
    }
    if ( (*(_BYTE *)(v13 + v65 + 32) & 2) != 0 )
    {
      v14 = PlaiAddDataToReportItem(a1, a2, L"networkInformationOffloadCapability", L"IPv4 Tx Options");
      v9 = v14;
      if ( v14 < 0 )
      {
        v64 = 0;
        v63 = v14;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_192;
        }
        PlaiWhoAmI(v69, 0x4000000000000800uLL);
        v15 = -1;
        do
          ++v15;
        while ( v69[v15] );
LABEL_22:
        v60 = &v64;
        goto LABEL_23;
      }
    }
    if ( (*(_BYTE *)(v13 + v65 + 32) & 1) != 0 )
    {
      v16 = PlaiAddDataToReportItem(a1, a2, L"networkInformationOffloadCapability", L"IPv4 Tx Checksum");
      v9 = v16;
      if ( v16 < 0 )
      {
        v64 = 0;
        v63 = v16;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_192;
        }
        PlaiWhoAmI(v70, 0x4000000000000800uLL);
        v17 = -1;
        do
          ++v17;
        while ( v70[v17] );
        goto LABEL_22;
      }
    }
    if ( (*(_BYTE *)(v13 + v65 + 32) & 8) != 0 )
    {
      v18 = PlaiAddDataToReportItem(a1, a2, L"networkInformationOffloadCapability", L"TCPv4 Tx Checksum");
      v9 = v18;
      if ( v18 < 0 )
      {
        v64 = 0;
        v63 = v18;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_192;
        }
        PlaiWhoAmI(v71, 0x4000000000000800uLL);
        v19 = -1;
        do
          ++v19;
        while ( v71[v19] );
        goto LABEL_22;
      }
    }
    if ( (*(_BYTE *)(v13 + v65 + 32) & 4) != 0 )
    {
      v20 = PlaiAddDataToReportItem(a1, a2, L"networkInformationOffloadCapability", L"UDPv4 Tx Checksum");
      v9 = v20;
      if ( v20 < 0 )
      {
        v64 = 0;
        v63 = v20;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_192;
        }
        PlaiWhoAmI(v72, 0x4000000000000800uLL);
        v21 = -1;
        do
          ++v21;
        while ( v72[v21] );
        goto LABEL_22;
      }
    }
    if ( (*(_BYTE *)(v13 + v65 + 32) & 0x40) != 0 )
    {
      v22 = PlaiAddDataToReportItem(a1, a2, L"networkInformationOffloadCapability", L"TCPv4 Tx LargeSend");
      v9 = v22;
      if ( v22 < 0 )
      {
        v64 = 0;
        v63 = v22;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_192;
        }
        PlaiWhoAmI(v73, 0x4000000000000800uLL);
        v23 = -1;
        do
          ++v23;
        while ( v73[v23] );
        goto LABEL_22;
      }
    }
    if ( *(char *)(v13 + v65 + 32) < 0 )
    {
      v24 = PlaiAddDataToReportItem(a1, a2, L"networkInformationOffloadCapability", L"TCPv4 Tx GiantSend");
      v9 = v24;
      if ( v24 < 0 )
      {
        v64 = 0;
        v63 = v24;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_192;
        }
        PlaiWhoAmI(v74, 0x4000000000000800uLL);
        v25 = -1;
        do
          ++v25;
        while ( v74[v25] );
        goto LABEL_22;
      }
    }
    if ( (*(_BYTE *)(v13 + v65 + 33) & 2) != 0 )
    {
      v26 = PlaiAddDataToReportItem(a1, a2, L"networkInformationOffloadCapability", L"IPv4 Rx Options");
      v9 = v26;
      if ( v26 < 0 )
      {
        v64 = 0;
        v63 = v26;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_192;
        }
        PlaiWhoAmI(v75, 0x4000000000000800uLL);
        v27 = -1;
        do
          ++v27;
        while ( v75[v27] );
        goto LABEL_22;
      }
    }
    if ( (*(_BYTE *)(v13 + v65 + 33) & 1) != 0 )
    {
      v28 = PlaiAddDataToReportItem(a1, a2, L"networkInformationOffloadCapability", L"IPv4 Rx Checksum");
      v9 = v28;
      if ( v28 < 0 )
      {
        v64 = 0;
        v63 = v28;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_192;
        }
        PlaiWhoAmI(v76, 0x4000000000000800uLL);
        v29 = -1;
        do
          ++v29;
        while ( v76[v29] );
        goto LABEL_22;
      }
    }
    if ( (*(_BYTE *)(v13 + v65 + 33) & 8) != 0 )
    {
      v30 = PlaiAddDataToReportItem(a1, a2, L"networkInformationOffloadCapability", L"TCPv4 Rx Checksum");
      v9 = v30;
      if ( v30 < 0 )
      {
        v64 = 0;
        v63 = v30;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_192;
        }
        PlaiWhoAmI(v77, 0x4000000000000800uLL);
        v31 = -1;
        do
          ++v31;
        while ( v77[v31] );
        goto LABEL_22;
      }
    }
    if ( (*(_BYTE *)(v13 + v65 + 33) & 4) != 0 )
    {
      v32 = PlaiAddDataToReportItem(a1, a2, L"networkInformationOffloadCapability", L"UDPv4 Rx Checksum");
      v9 = v32;
      if ( v32 < 0 )
      {
        v64 = 0;
        v63 = v32;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_192;
        }
        PlaiWhoAmI(v78, 0x4000000000000800uLL);
        v33 = -1;
        do
          ++v33;
        while ( v78[v33] );
        goto LABEL_22;
      }
    }
LABEL_96:
    if ( (a3->Flags & 0x100) != 0 )
    {
      if ( v65 )
      {
        NsiFreeTable(v67[0], 0, v65, 0);
        v65 = 0;
      }
      LOBYTE(v61) = 0;
      v34 = NsiAllocateAndGetTable(1, &NPI_MS_IPV6_MODULEID, 7, v67, 8, 0, 0, &v65, 88, 0, 0, &v66, v61);
      v35 = PlaiHResultFromWin32(v34);
      v9 = v35;
      if ( v35 < 0 )
      {
        v64 = 0;
        v63 = v35;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_192;
        }
        PlaiWhoAmI(v79, 0x4000000000000800uLL);
        v36 = -1;
        do
          ++v36;
        while ( v79[v36] );
        v60 = &v64;
LABEL_23:
        v11 = &v63;
LABEL_9:
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v11, 4, byte_180147320, 1, v60, 4);
        goto LABEL_192;
      }
      for ( j = 0; ; ++j )
      {
        if ( j >= v66 )
          goto LABEL_191;
        v38 = 88LL * j;
        if ( CurrentThreadCompartmentId == *(_DWORD *)(v38 + v65 + 4) && a3->Ipv6IfIndex == *(_DWORD *)(v38 + v65) )
          break;
      }
      if ( (*(_BYTE *)(v38 + v65 + 32) & 2) != 0 )
      {
        v39 = PlaiAddDataToReportItem(a1, a2, L"networkInformationOffloadCapability", L"IPv6 Tx Options");
        v9 = v39;
        if ( v39 < 0 )
        {
          v64 = 0;
          v63 = v39;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_192;
          }
          PlaiWhoAmI(v80, 0x4000000000000800uLL);
          v40 = -1;
          do
            ++v40;
          while ( v80[v40] );
          goto LABEL_22;
        }
      }
      if ( (*(_BYTE *)(v38 + v65 + 32) & 1) != 0 )
      {
        v41 = PlaiAddDataToReportItem(a1, a2, L"networkInformationOffloadCapability", L"IPv6 Tx Checksum");
        v9 = v41;
        if ( v41 < 0 )
        {
          v64 = 0;
          v63 = v41;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_192;
          }
          PlaiWhoAmI(v81, 0x4000000000000800uLL);
          v42 = -1;
          do
            ++v42;
          while ( v81[v42] );
          goto LABEL_22;
        }
      }
      if ( (*(_BYTE *)(v38 + v65 + 32) & 8) != 0 )
      {
        v43 = PlaiAddDataToReportItem(a1, a2, L"networkInformationOffloadCapability", L"TCPv6 Tx Checksum");
        v9 = v43;
        if ( v43 < 0 )
        {
          v64 = 0;
          v63 = v43;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_192;
          }
          PlaiWhoAmI(v82, 0x4000000000000800uLL);
          v44 = -1;
          do
            ++v44;
          while ( v82[v44] );
          goto LABEL_22;
        }
      }
      if ( (*(_BYTE *)(v38 + v65 + 32) & 4) != 0 )
      {
        v45 = PlaiAddDataToReportItem(a1, a2, L"networkInformationOffloadCapability", L"UDPv6 Tx Checksum");
        v9 = v45;
        if ( v45 < 0 )
        {
          v64 = 0;
          v63 = v45;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_192;
          }
          PlaiWhoAmI(v83, 0x4000000000000800uLL);
          v46 = -1;
          do
            ++v46;
          while ( v83[v46] );
          goto LABEL_142;
        }
      }
      if ( (*(_BYTE *)(v38 + v65 + 32) & 0x40) != 0 )
      {
        v47 = PlaiAddDataToReportItem(a1, a2, L"networkInformationOffloadCapability", L"TCPv6 Tx LargeSend");
        v9 = v47;
        if ( v47 < 0 )
        {
          v64 = 0;
          v63 = v47;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_192;
          }
          PlaiWhoAmI(v84, 0x4000000000000800uLL);
          v48 = -1;
          do
            ++v48;
          while ( v84[v48] );
          goto LABEL_142;
        }
      }
      if ( *(char *)(v38 + v65 + 32) < 0 )
      {
        v49 = PlaiAddDataToReportItem(a1, a2, L"networkInformationOffloadCapability", L"TCPv6 Tx GiantSend");
        v9 = v49;
        if ( v49 < 0 )
        {
          v64 = 0;
          v63 = v49;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_192;
          }
          PlaiWhoAmI(v85, 0x4000000000000800uLL);
          v50 = -1;
          do
            ++v50;
          while ( v85[v50] );
          goto LABEL_142;
        }
      }
      if ( (*(_BYTE *)(v38 + v65 + 33) & 2) != 0 )
      {
        v51 = PlaiAddDataToReportItem(a1, a2, L"networkInformationOffloadCapability", L"IPv6 Rx Options");
        v9 = v51;
        if ( v51 < 0 )
        {
          v64 = 0;
          v63 = v51;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_192;
          }
          PlaiWhoAmI(v86, 0x4000000000000800uLL);
          v52 = -1;
          do
            ++v52;
          while ( v86[v52] );
          goto LABEL_142;
        }
      }
      if ( (*(_BYTE *)(v38 + v65 + 33) & 1) != 0 )
      {
        v53 = PlaiAddDataToReportItem(a1, a2, L"networkInformationOffloadCapability", L"IPv6 Rx Checksum");
        v9 = v53;
        if ( v53 < 0 )
        {
          v64 = 0;
          v63 = v53;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_192;
          }
          PlaiWhoAmI(v87, 0x4000000000000800uLL);
          v54 = -1;
          do
            ++v54;
          while ( v87[v54] );
          goto LABEL_142;
        }
      }
      if ( (*(_BYTE *)(v38 + v65 + 33) & 8) != 0 )
      {
        v55 = PlaiAddDataToReportItem(a1, a2, L"networkInformationOffloadCapability", L"TCPv6 Rx Checksum");
        v9 = v55;
        if ( v55 < 0 )
        {
          v64 = 0;
          v63 = v55;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_192;
          }
          PlaiWhoAmI(v88, 0x4000000000000800uLL);
          v56 = -1;
          do
            ++v56;
          while ( v88[v56] );
          goto LABEL_142;
        }
      }
      if ( (*(_BYTE *)(v38 + v65 + 33) & 4) != 0 )
      {
        v57 = PlaiAddDataToReportItem(a1, a2, L"networkInformationOffloadCapability", L"UDPv6 Rx Checksum");
        v9 = v57;
        if ( v57 < 0 )
        {
          v64 = 0;
          v63 = v57;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_192;
          }
          PlaiWhoAmI(v89, 0x4000000000000800uLL);
          v58 = -1;
          do
            ++v58;
          while ( v89[v58] );
LABEL_142:
          v60 = &v64;
          goto LABEL_23;
        }
      }
    }
LABEL_191:
    v9 = 0;
    goto LABEL_192;
  }
  v63 = 0;
  v64 = v8;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v68, 0x4000000000000800uLL);
    v10 = -1;
    do
      ++v10;
    while ( v68[v10] );
    v11 = &v64;
    v60 = &v63;
    goto LABEL_9;
  }
LABEL_192:
  if ( v65 )
    NsiFreeTable(v67[0], 0, v65, 0);
  return v9;
}

```

## disassembly

```asm
0x18005e3a8  mov     [rsp-8+arg_10], rbx
0x18005e3ad  push    rbp
0x18005e3ae  push    rsi
0x18005e3af  push    rdi
0x18005e3b0  push    r12
0x18005e3b2  push    r13
0x18005e3b4  push    r14
0x18005e3b6  push    r15
0x18005e3b8  lea     rbp, [rsp-0AB0h]
0x18005e3c0  sub     rsp, 0BB0h
0x18005e3c7  mov     rax, cs:__security_cookie
0x18005e3ce  xor     rax, rsp
0x18005e3d1  mov     [rbp+0AE0h+var_40], rax
0x18005e3d8  xor     r13d, r13d
0x18005e3db  mov     r15, r8
0x18005e3de  mov     [rbp+0AE0h+var_B58], r13d
0x18005e3e2  mov     r14, rdx
0x18005e3e5  mov     [rbp+0AE0h+var_B50], r13
0x18005e3e9  mov     rsi, rcx
0x18005e3ec  mov     [rbp+0AE0h+var_B60], r13
0x18005e3f0  call    cs:__imp_GetCurrentThreadCompartmentId
0x18005e3f6  test    byte ptr [r15+5Ch], 80h
0x18005e3fb  mov     r12d, eax
0x18005e3fe  jz      loc_18005EC11
0x18005e404  mov     byte ptr [rsp+0BE0h+var_B80], r13b
0x18005e409  lea     rax, [rbp+0AE0h+var_B58]
0x18005e40d  mov     [rsp+0BE0h+var_B88], rax
0x18005e412  lea     r9, [rbp+0AE0h+var_B50]
0x18005e416  mov     dword ptr [rsp+0BE0h+var_B90], r13d
0x18005e41b  lea     rax, [rbp+0AE0h+var_B60]
0x18005e41f  mov     [rsp+0BE0h+var_B98], r13
0x18005e424  lea     r8d, [r13+7]
0x18005e428  mov     dword ptr [rsp+0BE0h+var_BA0], 58h ; 'X'
0x18005e430  lea     rdx, NPI_MS_IPV4_MODULEID
0x18005e437  mov     [rsp+0BE0h+var_BA8], rax
0x18005e43c  lea     ecx, [r13+1]
0x18005e440  mov     dword ptr [rsp+0BE0h+var_BB0], r13d
0x18005e445  mov     [rsp+0BE0h+var_BB8], r13
0x18005e44a  mov     dword ptr [rsp+0BE0h+var_BC0], 8
0x18005e452  call    cs:__imp_NsiAllocateAndGetTable
0x18005e458  mov     ecx, eax; unsigned int
0x18005e45a  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18005e45f  mov     ebx, eax
0x18005e461  test    eax, eax
0x18005e463  jns     loc_18005E546
0x18005e469  cmp     dword ptr cs:xmmword_180169738, r13d
0x18005e470  mov     [rsp+0BE0h+var_B70], r13d
0x18005e475  mov     [rsp+0BE0h+var_B68], eax
0x18005e479  jz      loc_18005F456
0x18005e47f  mov     rdx, 4000000000000800h; unsigned __int64
0x18005e489  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005e490  jz      loc_18005F456
0x18005e496  mov     rax, cs:qword_180169748
0x18005e49d  and     rax, rdx
0x18005e4a0  cmp     cs:qword_180169748, rax
0x18005e4a7  jnz     loc_18005F456
0x18005e4ad  lea     rcx, [rbp+0AE0h+var_B40]; unsigned __int16 *
0x18005e4b1  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005e4b6  lea     rcx, [rbp+0AE0h+var_B40]
0x18005e4ba  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005e4be  inc     rax
0x18005e4c1  cmp     [rcx+rax*2], r13w
0x18005e4c6  jnz     short loc_18005E4BE
0x18005e4c8  lea     ecx, [rax+rax]
0x18005e4cb  lea     rax, [rbp+0AE0h+var_B40]
0x18005e4cf  add     rcx, 2
0x18005e4d3  mov     qword ptr [rsp+0BE0h+var_B80], rcx
0x18005e4d8  lea     r9, [rsp+0BE0h+var_B68]
0x18005e4dd  mov     [rsp+0BE0h+var_B88], rax
0x18005e4e2  lea     rax, aPlaigetoffload; "PlaiGetOffloadInfo"
0x18005e4e9  mov     [rsp+0BE0h+var_B90], 13h
0x18005e4f2  mov     [rsp+0BE0h+var_B98], rax
0x18005e4f7  lea     rax, [rsp+0BE0h+var_B70]
0x18005e4fc  mov     [rsp+0BE0h+var_BA0], 4
0x18005e505  mov     [rsp+0BE0h+var_BA8], rax
0x18005e50a  lea     rax, byte_180147320
0x18005e511  mov     [rsp+0BE0h+var_BB0], 1
0x18005e51a  mov     [rsp+0BE0h+var_BB8], rax
0x18005e51f  mov     [rsp+0BE0h+var_BC0], 4
0x18005e528  mov     r8d, 5
0x18005e52e  lea     rdx, PLA_EVENT_ERROR
0x18005e535  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18005e53c  call    EventingWriteEvent
0x18005e541  jmp     loc_18005F456
0x18005e546  mov     ecx, r13d
0x18005e549  cmp     ecx, [rbp+0AE0h+var_B58]
0x18005e54c  jnb     loc_18005EC11
0x18005e552  mov     rdx, [rbp+0AE0h+var_B60]
0x18005e556  mov     eax, ecx
0x18005e558  imul    rdi, rax, 58h ; 'X'
0x18005e55c  cmp     r12d, [rdi+rdx+4]
0x18005e561  jnz     short loc_18005E56C
0x18005e563  mov     eax, [rdi+rdx]
0x18005e566  cmp     [r15+4], eax
0x18005e56a  jz      short loc_18005E570
0x18005e56c  inc     ecx
0x18005e56e  jmp     short loc_18005E549
0x18005e570  test    byte ptr [rdi+rdx+20h], 2
0x18005e575  jz      loc_18005E65F
0x18005e57b  lea     r9, aIpv4TxOptions; "IPv4 Tx Options"
0x18005e582  mov     rdx, r14; struct IXMLDOMElement *
0x18005e585  lea     r8, aNetworkinforma_2; "networkInformationOffloadCapability"
0x18005e58c  mov     rcx, rsi; struct IXMLDOMDocument *
0x18005e58f  call    ?PlaiAddDataToReportItem@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG2@Z; PlaiAddDataToReportItem(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *)
0x18005e594  mov     ebx, eax
0x18005e596  test    eax, eax
0x18005e598  jns     loc_18005E65F
0x18005e59e  cmp     dword ptr cs:xmmword_180169738, r13d
0x18005e5a5  mov     [rsp+0BE0h+var_B68], r13d
0x18005e5aa  mov     [rsp+0BE0h+var_B70], eax
0x18005e5ae  jz      loc_18005F456
0x18005e5b4  mov     rdx, 4000000000000800h; unsigned __int64
0x18005e5be  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005e5c5  jz      loc_18005F456
0x18005e5cb  mov     rax, cs:qword_180169748
0x18005e5d2  and     rax, rdx
0x18005e5d5  cmp     cs:qword_180169748, rax
0x18005e5dc  jnz     loc_18005F456
0x18005e5e2  lea     rcx, [rbp+0AE0h+var_AC0]; unsigned __int16 *
0x18005e5e6  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005e5eb  lea     rcx, [rbp+0AE0h+var_AC0]
0x18005e5ef  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005e5f3  inc     rax
0x18005e5f6  cmp     [rcx+rax*2], r13w
0x18005e5fb  jnz     short loc_18005E5F3
0x18005e5fd  lea     ecx, [rax+rax]
0x18005e600  lea     rax, [rbp+0AE0h+var_AC0]
0x18005e604  add     rcx, 2
0x18005e608  mov     qword ptr [rsp+0BE0h+var_B80], rcx
0x18005e60d  mov     ecx, 4
0x18005e612  mov     [rsp+0BE0h+var_B88], rax
0x18005e617  lea     rax, aPlaigetoffload; "PlaiGetOffloadInfo"
0x18005e61e  mov     [rsp+0BE0h+var_B90], 13h
0x18005e627  mov     [rsp+0BE0h+var_B98], rax
0x18005e62c  lea     rax, [rsp+0BE0h+var_B68]
0x18005e631  mov     [rsp+0BE0h+var_BA0], rcx
0x18005e636  mov     [rsp+0BE0h+var_BA8], rax
0x18005e63b  mov     [rsp+0BE0h+var_BB0], 1
0x18005e644  lea     rax, byte_180147320
0x18005e64b  mov     [rsp+0BE0h+var_BB8], rax
0x18005e650  mov     [rsp+0BE0h+var_BC0], rcx
0x18005e655  lea     r9, [rsp+0BE0h+var_B70]
0x18005e65a  jmp     loc_18005E528
0x18005e65f  mov     rax, [rbp+0AE0h+var_B60]
0x18005e663  test    byte ptr [rdi+rax+20h], 1
0x18005e668  jz      loc_18005E701
0x18005e66e  lea     r9, aIpv4TxChecksum; "IPv4 Tx Checksum"
0x18005e675  mov     rdx, r14; struct IXMLDOMElement *
0x18005e678  lea     r8, aNetworkinforma_2; "networkInformationOffloadCapability"
0x18005e67f  mov     rcx, rsi; struct IXMLDOMDocument *
0x18005e682  call    ?PlaiAddDataToReportItem@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG2@Z; PlaiAddDataToReportItem(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *)
0x18005e687  mov     ebx, eax
0x18005e689  test    eax, eax
0x18005e68b  jns     short loc_18005E701
0x18005e68d  cmp     dword ptr cs:xmmword_180169738, r13d
0x18005e694  mov     [rsp+0BE0h+var_B68], r13d
0x18005e699  mov     [rsp+0BE0h+var_B70], eax
0x18005e69d  jz      loc_18005F456
0x18005e6a3  mov     rdx, 4000000000000800h; unsigned __int64
0x18005e6ad  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005e6b4  jz      loc_18005F456
0x18005e6ba  mov     rax, cs:qword_180169748
0x18005e6c1  and     rax, rdx
0x18005e6c4  cmp     cs:qword_180169748, rax
0x18005e6cb  jnz     loc_18005F456
0x18005e6d1  lea     rcx, [rbp+0AE0h+var_A40]; unsigned __int16 *
0x18005e6d8  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005e6dd  lea     rcx, [rbp+0AE0h+var_A40]
0x18005e6e4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005e6e8  inc     rax
0x18005e6eb  cmp     [rcx+rax*2], r13w
0x18005e6f0  jnz     short loc_18005E6E8
0x18005e6f2  lea     ecx, [rax+rax]
0x18005e6f5  lea     rax, [rbp+0AE0h+var_A40]
0x18005e6fc  jmp     loc_18005E604
0x18005e701  mov     rax, [rbp+0AE0h+var_B60]
0x18005e705  test    byte ptr [rdi+rax+20h], 8
0x18005e70a  jz      loc_18005E7A3
0x18005e710  lea     r9, aTcpv4TxChecksu; "TCPv4 Tx Checksum"
0x18005e717  mov     rdx, r14; struct IXMLDOMElement *
0x18005e71a  lea     r8, aNetworkinforma_2; "networkInformationOffloadCapability"
0x18005e721  mov     rcx, rsi; struct IXMLDOMDocument *
0x18005e724  call    ?PlaiAddDataToReportItem@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG2@Z; PlaiAddDataToReportItem(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *)
0x18005e729  mov     ebx, eax
0x18005e72b  test    eax, eax
0x18005e72d  jns     short loc_18005E7A3
0x18005e72f  cmp     dword ptr cs:xmmword_180169738, r13d
0x18005e736  mov     [rsp+0BE0h+var_B68], r13d
0x18005e73b  mov     [rsp+0BE0h+var_B70], eax
0x18005e73f  jz      loc_18005F456
0x18005e745  mov     rdx, 4000000000000800h; unsigned __int64
0x18005e74f  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005e756  jz      loc_18005F456
0x18005e75c  mov     rax, cs:qword_180169748
0x18005e763  and     rax, rdx
0x18005e766  cmp     cs:qword_180169748, rax
0x18005e76d  jnz     loc_18005F456
0x18005e773  lea     rcx, [rbp+0AE0h+var_9C0]; unsigned __int16 *
0x18005e77a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005e77f  lea     rcx, [rbp+0AE0h+var_9C0]
0x18005e786  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005e78a  inc     rax
0x18005e78d  cmp     [rcx+rax*2], r13w
0x18005e792  jnz     short loc_18005E78A
0x18005e794  lea     ecx, [rax+rax]
0x18005e797  lea     rax, [rbp+0AE0h+var_9C0]
0x18005e79e  jmp     loc_18005E604
0x18005e7a3  mov     rax, [rbp+0AE0h+var_B60]
0x18005e7a7  test    byte ptr [rdi+rax+20h], 4
0x18005e7ac  jz      loc_18005E845
0x18005e7b2  lea     r9, aUdpv4TxChecksu; "UDPv4 Tx Checksum"
0x18005e7b9  mov     rdx, r14; struct IXMLDOMElement *
0x18005e7bc  lea     r8, aNetworkinforma_2; "networkInformationOffloadCapability"
0x18005e7c3  mov     rcx, rsi; struct IXMLDOMDocument *
0x18005e7c6  call    ?PlaiAddDataToReportItem@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG2@Z; PlaiAddDataToReportItem(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *)
0x18005e7cb  mov     ebx, eax
0x18005e7cd  test    eax, eax
0x18005e7cf  jns     short loc_18005E845
0x18005e7d1  cmp     dword ptr cs:xmmword_180169738, r13d
0x18005e7d8  mov     [rsp+0BE0h+var_B68], r13d
0x18005e7dd  mov     [rsp+0BE0h+var_B70], eax
0x18005e7e1  jz      loc_18005F456
0x18005e7e7  mov     rdx, 4000000000000800h; unsigned __int64
0x18005e7f1  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005e7f8  jz      loc_18005F456
0x18005e7fe  mov     rax, cs:qword_180169748
0x18005e805  and     rax, rdx
0x18005e808  cmp     cs:qword_180169748, rax
0x18005e80f  jnz     loc_18005F456
0x18005e815  lea     rcx, [rbp+0AE0h+var_940]; unsigned __int16 *
0x18005e81c  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005e821  lea     rcx, [rbp+0AE0h+var_940]
0x18005e828  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005e82c  inc     rax
0x18005e82f  cmp     [rcx+rax*2], r13w
0x18005e834  jnz     short loc_18005E82C
0x18005e836  lea     ecx, [rax+rax]
0x18005e839  lea     rax, [rbp+0AE0h+var_940]
0x18005e840  jmp     loc_18005E604
0x18005e845  mov     rax, [rbp+0AE0h+var_B60]
0x18005e849  test    byte ptr [rdi+rax+20h], 40h
0x18005e84e  jz      loc_18005E8E7
0x18005e854  lea     r9, aTcpv4TxLargese; "TCPv4 Tx LargeSend"
0x18005e85b  mov     rdx, r14; struct IXMLDOMElement *
0x18005e85e  lea     r8, aNetworkinforma_2; "networkInformationOffloadCapability"
0x18005e865  mov     rcx, rsi; struct IXMLDOMDocument *
0x18005e868  call    ?PlaiAddDataToReportItem@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG2@Z; PlaiAddDataToReportItem(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *)
0x18005e86d  mov     ebx, eax
0x18005e86f  test    eax, eax
0x18005e871  jns     short loc_18005E8E7
0x18005e873  cmp     dword ptr cs:xmmword_180169738, r13d
0x18005e87a  mov     [rsp+0BE0h+var_B68], r13d
0x18005e87f  mov     [rsp+0BE0h+var_B70], eax
0x18005e883  jz      loc_18005F456
0x18005e889  mov     rdx, 4000000000000800h; unsigned __int64
0x18005e893  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005e89a  jz      loc_18005F456
0x18005e8a0  mov     rax, cs:qword_180169748
0x18005e8a7  and     rax, rdx
0x18005e8aa  cmp     cs:qword_180169748, rax
0x18005e8b1  jnz     loc_18005F456
0x18005e8b7  lea     rcx, [rbp+0AE0h+var_8C0]; unsigned __int16 *
0x18005e8be  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005e8c3  lea     rcx, [rbp+0AE0h+var_8C0]
0x18005e8ca  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005e8ce  inc     rax
0x18005e8d1  cmp     [rcx+rax*2], r13w
0x18005e8d6  jnz     short loc_18005E8CE
0x18005e8d8  lea     ecx, [rax+rax]
0x18005e8db  lea     rax, [rbp+0AE0h+var_8C0]
0x18005e8e2  jmp     loc_18005E604
0x18005e8e7  mov     rax, [rbp+0AE0h+var_B60]
0x18005e8eb  cmp     [rdi+rax+20h], r13b
0x18005e8f0  jge     loc_18005E989
0x18005e8f6  lea     r9, aTcpv4TxGiantse; "TCPv4 Tx GiantSend"
0x18005e8fd  mov     rdx, r14; struct IXMLDOMElement *
0x18005e900  lea     r8, aNetworkinforma_2; "networkInformationOffloadCapability"
0x18005e907  mov     rcx, rsi; struct IXMLDOMDocument *
0x18005e90a  call    ?PlaiAddDataToReportItem@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG2@Z; PlaiAddDataToReportItem(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *)
0x18005e90f  mov     ebx, eax
0x18005e911  test    eax, eax
0x18005e913  jns     short loc_18005E989
0x18005e915  cmp     dword ptr cs:xmmword_180169738, r13d
0x18005e91c  mov     [rsp+0BE0h+var_B68], r13d
0x18005e921  mov     [rsp+0BE0h+var_B70], eax
0x18005e925  jz      loc_18005F456
0x18005e92b  mov     rdx, 4000000000000800h; unsigned __int64
0x18005e935  test    qword ptr cs:xmmword_180169738+8, rdx
0x18005e93c  jz      loc_18005F456
0x18005e942  mov     rax, cs:qword_180169748
0x18005e949  and     rax, rdx
0x18005e94c  cmp     cs:qword_180169748, rax
0x18005e953  jnz     loc_18005F456
0x18005e959  lea     rcx, [rbp+0AE0h+var_840]; unsigned __int16 *
0x18005e960  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005e965  lea     rcx, [rbp+0AE0h+var_840]
0x18005e96c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005e970  inc     rax
0x18005e973  cmp     [rcx+rax*2], r13w
0x18005e978  jnz     short loc_18005E970
  ... truncated ...
```
