# HandleMtraceRequest

- ea: `0x180038e74`
- end: `0x180039e0b`
- name: `HandleMtraceRequest`
- size: `3991`
- prototype: `int __fastcall(__int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x180038540`

## callees

- `0x18000ac60`
- `0x18002f000`
- `0x180034c40`
- `0x1800368e0`
- `0x1800381d8`
- `0x1800382d4`
- `0x18003839c`
- `0x18003845c`
- `0x180038e74`
- `0x18003a114`
- `0x18003a1c4`
- `0x18003a35c`
- `0x18003a688`
- `0x18003a80c`
- `0x18003a9c0`
- `0x18003b0e4`
- `0x1800583cc`
- `0x18005852a`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180039278`
- `KERNEL32!HeapFree` at `0x180039d8f`
- `KERNEL32!HeapFree` at `0x180039da1`
- `KERNEL32!HeapFree` at `0x180039278`
- `KERNEL32!HeapFree` at `0x180039d8f`
- `KERNEL32!HeapFree` at `0x180039da1`
- `KERNEL32!HeapAlloc` at `0x18003908a`
- `KERNEL32!HeapAlloc` at `0x18003923b`
- `KERNEL32!HeapAlloc` at `0x18003908a`
- `KERNEL32!HeapAlloc` at `0x18003923b`
- `WS2_32!__imp_htonl` at `0x180039155`
- `WS2_32!__imp_htonl` at `0x18003954e`
- `WS2_32!__imp_htonl` at `0x180039568`
- `WS2_32!__imp_htonl` at `0x180039155`
- `WS2_32!__imp_htonl` at `0x18003954e`
- `WS2_32!__imp_htonl` at `0x180039568`
- `WS2_32!__imp_ntohl` at `0x180038f74`
- `WS2_32!__imp_ntohl` at `0x180038ff2`
- `WS2_32!__imp_ntohl` at `0x180038f74`
- `WS2_32!__imp_ntohl` at `0x180038ff2`
- `WS2_32!__imp_ntohs` at `0x180038f31`
- `WS2_32!__imp_ntohs` at `0x180038f31`
- `rtm!MgmGetMfeStats` at `0x180039212`
- `rtm!MgmGetMfeStats` at `0x180039262`
- `rtm!MgmGetMfeStats` at `0x180039212`
- `rtm!MgmGetMfeStats` at `0x180039262`

## string_xrefs

- `0x180039ae0`: ` IifProtocol      = %02x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall HandleMtraceRequest(__int64 a1)
{
  __int64 v2; // rdi
  u_short v3; // cx
  unsigned int v4; // ebx
  DWORD *v5; // r13
  unsigned __int64 v6; // rbx
  __int64 v7; // rcx
  _BYTE *v8; // rax
  const wchar_t *v9; // r8
  size_t v10; // rbx
  _BYTE *v11; // rsi
  int CurrentNTP32Time; // eax
  __int64 v13; // r12
  unsigned int v14; // eax
  u_long v15; // eax
  bool v16; // zf
  _DWORD *v17; // r12
  unsigned int v18; // r12d
  __int64 v19; // rcx
  char v20; // al
  DWORD v21; // ecx
  int v22; // eax
  int v23; // eax
  __int64 v24; // rax
  __int64 v25; // r13
  u_long v26; // eax
  DWORD *v27; // r12
  u_long v28; // ecx
  __int64 v29; // rdx
  u_long v30; // r12d
  unsigned __int8 v31; // di
  DWORD *v32; // rax
  u_long v33; // eax
  bool v34; // cf
  __int64 v35; // r11
  char v36; // al
  unsigned int v37; // edx
  unsigned int v38; // ecx
  __int64 v39; // r8
  char v40; // al
  void (__fastcall *v41)(_QWORD, _QWORD, _QWORD, _BYTE *); // rax
  unsigned __int8 v42; // cl
  void (__fastcall *v43)(_QWORD, _QWORD, _QWORD, _BYTE *); // rax
  unsigned __int8 v44; // cl
  char v45; // al
  int v46; // r11d
  DWORD *v47; // rdi
  __int64 v49; // [rsp+20h] [rbp-938h]
  __int64 v50; // [rsp+28h] [rbp-930h]
  __int64 v51; // [rsp+30h] [rbp-928h]
  __int64 v52; // [rsp+38h] [rbp-920h]
  __int64 v53; // [rsp+40h] [rbp-918h]
  __int64 v54; // [rsp+48h] [rbp-910h]
  char v55; // [rsp+50h] [rbp-908h] BYREF
  _BYTE v56[3]; // [rsp+51h] [rbp-907h] BYREF
  u_long v57; // [rsp+54h] [rbp-904h] BYREF
  u_long v58; // [rsp+58h] [rbp-900h]
  unsigned int v59; // [rsp+5Ch] [rbp-8FCh] BYREF
  int v60; // [rsp+60h] [rbp-8F8h]
  _DWORD v61[2]; // [rsp+64h] [rbp-8F4h] BYREF
  unsigned int v62; // [rsp+6Ch] [rbp-8ECh] BYREF
  DWORD pdwBufferSize; // [rsp+70h] [rbp-8E8h] BYREF
  __int64 v64; // [rsp+78h] [rbp-8E0h] BYREF
  DWORD *v65; // [rsp+80h] [rbp-8D8h]
  LPVOID lpMem; // [rsp+88h] [rbp-8D0h]
  __int64 v67; // [rsp+90h] [rbp-8C8h] BYREF
  __int64 v68; // [rsp+98h] [rbp-8C0h] BYREF
  __int128 v69; // [rsp+A0h] [rbp-8B8h] BYREF
  u_long hostlong[4]; // [rsp+B0h] [rbp-8A8h]
  unsigned __int64 v71; // [rsp+C0h] [rbp-898h]
  struct _MIB_IPMCAST_MFE pimm; // [rsp+D0h] [rbp-888h] BYREF
  int v73; // [rsp+120h] [rbp-838h] BYREF
  char v74[2044]; // [rsp+124h] [rbp-834h] BYREF

  pdwBufferSize = 0;
  v56[0] = 0;
  v64 = 0;
  v62 = 0;
  memset_0(&pimm, 0, sizeof(pimm));
  v2 = *(_QWORD *)(a1 + 8);
  v68 = 0;
  v67 = 0;
  v55 = 0;
  v57 = 0;
  v59 = 0;
  v61[0] = 0;
  v73 = 0;
  memset_0(v74, 0, sizeof(v74));
  v3 = *(_WORD *)(v2 + 2);
  v4 = 4 * (*(_BYTE *)v2 & 0xF);
  v5 = (DWORD *)(v2 + v4);
  v65 = v5;
  v6 = ((unsigned __int64)(ntohs(v3) - v4) - 24) >> 5;
  v71 = v6;
  if ( (_DWORD)v6 )
  {
    if ( (ntohl(*(_DWORD *)(v2 + 16)) & 0xF0000000) == 0xE0000000 )
    {
      LODWORD(v8) = *(_DWORD *)(v2 + 16) & 0xF0;
      if ( (*(_BYTE *)(v2 + 16) & 0xF0) != 0xE0 )
        return (int)v8;
    }
    LODWORD(v8) = FindBindingForPacket(v2, &v64, &v62);
    if ( (_DWORD)v8 )
    {
      if ( !g_mcastDebugLevel || (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        return (int)v8;
      v9 = L"Mtrace: no matching interface";
LABEL_164:
      LODWORD(v8) = McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, v9);
      return (int)v8;
    }
  }
  else if ( (unsigned int)FindBindingWithRemoteAddress(&v64, &v62, v5[3]) )
  {
    ntohl(*(_DWORD *)(v2 + 16));
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v73) = 0;
      FormatRRASErrorString(
        &v73,
        L"Mtrace: reinjecting packet to %d.%d.%d.%d",
        *(unsigned __int8 *)(v2 + 16),
        *(unsigned __int8 *)(v2 + 17),
        *(unsigned __int8 *)(v2 + 18),
        *(unsigned __int8 *)(v2 + 19));
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v73);
    }
    LODWORD(v8) = McSendPacketTo(v7, a1, v5[3]);
    return (int)v8;
  }
  v8 = (_BYTE *)(32LL * (unsigned int)v6);
  if ( (unsigned __int64)v8 > 0xFFFFFFFF )
    goto LABEL_162;
  v10 = (unsigned int)((_DWORD)v8 + 24);
  if ( (unsigned int)v10 < (unsigned int)v8 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return (int)v8;
    v9 = L"Arithmetic overflow - couldn't allocate memory for mtrace response";
    goto LABEL_164;
  }
  LODWORD(v8) = (_DWORD)v8 + 56;
  v61[1] = v10 + 32;
  if ( (int)v10 + 32 < (unsigned int)v10 )
  {
LABEL_162:
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return (int)v8;
    v9 = L"Arithmetic overflow - Couldn't allocate memory for mtrace response";
    goto LABEL_164;
  }
  v8 = HeapAlloc(IPRouterHeap, 0, (unsigned int)v8);
  v11 = v8;
  if ( !v8 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return (int)v8;
    v9 = L"Couldn't allocate memory for mtrace response";
    goto LABEL_164;
  }
  memcpy_0(v8, v5, v10);
  *(_OWORD *)&v11[v10] = 0;
  *(_OWORD *)&v11[v10 + 16] = 0;
  CurrentNTP32Time = GetCurrentNTP32Time();
  v13 = v64;
  *(_DWORD *)&v11[v10] = CurrentNTP32Time;
  v14 = v62;
  *(_DWORD *)&v11[v10 + 20] = 0;
  v11[v10 + 29] = 0;
  *(_DWORD *)&v11[v10 + 8] = v14;
  if ( v13 )
  {
    v69 = 0;
    *(_OWORD *)hostlong = 0;
    if ( (unsigned int)GetInterfaceMcastCounters(v13, &v69) )
    {
      LOBYTE(v58) = Microsoft_Windows_RRASEnableBits & 0x80;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"MTrace: GetInterfaceMcastCounters failed");
    }
    else
    {
      v15 = htonl(hostlong[2]);
      v16 = g_mcastDebugLevel == 0;
      *(_DWORD *)&v11[v10 + 20] = v15;
      if ( !v16 && (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v73) = 0;
        FormatRRASErrorString(&v73, L"dwOifPacketCount = %d", *(_QWORD *)&hostlong[2]);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v73);
      }
      v11[v10 + 29] = *(_BYTE *)(v13 + 324);
    }
  }
  memset_0(&pimm, 0, sizeof(pimm));
  pimm.dwGroup = v5[1];
  pimm.dwSource = v5[2];
  pdwBufferSize = 0;
  pimm.dwSrcMask = -1;
  if ( MgmGetMfeStats(&pimm, &pdwBufferSize, 0, 1u) )
  {
    lpMem = 0;
  }
  else
  {
    lpMem = HeapAlloc(IPRouterHeap, 0, pdwBufferSize);
    v17 = lpMem;
    if ( MgmGetMfeStats(&pimm, &pdwBufferSize, (PBYTE)lpMem, 1u) )
    {
      HeapFree(IPRouterHeap, 0, v17);
      lpMem = 0;
    }
    else
    {
      if ( v17 )
      {
        v18 = v17[4];
        v19 = *((unsigned int *)lpMem + 8);
        v58 = *((_DWORD *)lpMem + 3);
        v20 = MaskToMaskLen(v19);
        v60 = 1;
LABEL_42:
        v55 = v20;
        goto LABEL_43;
      }
      lpMem = 0;
    }
  }
  v21 = v5[2];
  if ( v21 != -1 )
  {
    v60 = McLookupRoute(v21, 0, (unsigned int)&v55, (unsigned int)&v57, (__int64)&v59, (__int64)v61);
    v58 = v57;
    if ( v57 == 16777343 )
    {
      v23 = McLookupRoute(v5[2], 1, (unsigned int)&v55, (unsigned int)&v57, (__int64)&v59, (__int64)v61);
      v58 = v57;
      v60 = v23;
    }
    v18 = v59;
    v20 = v55;
    goto LABEL_42;
  }
  v60 = McLookupRoute(v5[1], 0, (unsigned int)&v55, (unsigned int)&v57, (__int64)&v59, (__int64)v61);
  v58 = v57;
  if ( v57 == 16777343 )
  {
    v22 = McLookupRoute(v5[1], 1, (unsigned int)&v55, (unsigned int)&v57, (__int64)&v59, (__int64)v61);
    v58 = v57;
    v60 = v22;
  }
  v18 = v59;
  v55 = 0;
LABEL_43:
  if ( !v18 )
  {
    v25 = 0;
    goto LABEL_50;
  }
  v24 = InterfaceLookupByIfIndex(v18, 1);
  v25 = v24;
  if ( !v24 )
  {
LABEL_50:
    v27 = v65;
    v28 = 0;
    goto LABEL_51;
  }
  v26 = defaultSourceAddress(v24);
  v27 = v65;
  v28 = v26;
  v57 = v26;
  v29 = v65[2];
  if ( (_DWORD)v29 != -1 )
  {
    if ( (unsigned int)IsConnectedTo(v25, v29, 0, 0) )
    {
      v58 = v27[2];
      v28 = v57;
      goto LABEL_52;
    }
    v28 = v57;
  }
LABEL_51:
  v57 = v28;
LABEL_52:
  LODWORD(v8) = *(_DWORD *)(v2 + 16) & 0xF0;
  if ( (*(_BYTE *)(v2 + 16) & 0xF0) == 0xE0 && (!v25 || v25 == v64) )
    return (int)v8;
  v61[0] = v71 + 1;
  if ( v28 == 16777343 )
    v57 = v27[2];
  if ( v25 )
  {
    v31 = 0;
    MulticastOwner(v25, &v67, 0);
    *(_DWORD *)&v11[v10 + 4] = v57;
    if ( lpMem )
    {
      v30 = *((_DWORD *)lpMem + 3);
    }
    else if ( (*(_DWORD *)(v25 + 668) && *(_DWORD *)(*(_QWORD *)(v25 + 712) + 4LL) != -1
            || (v30 = *(_DWORD *)(v25 + 672)) == 0)
           && (!v60 || (v30 = v58) == 0) )
    {
      v30 = 0;
    }
    v32 = v65;
    *(_DWORD *)&v11[v10 + 12] = v30;
    if ( v30 == v32[2] )
      v30 = v32[4];
    *(_DWORD *)&v11[v10 + 16] = 0;
    v69 = 0;
    *(_OWORD *)hostlong = 0;
    if ( (unsigned int)GetInterfaceMcastCounters(v25, &v69) )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"MTrace: GetInterfaceMcastCounters failed");
    }
    else
    {
      *(_DWORD *)&v11[v10 + 16] = htonl(hostlong[0]);
    }
    v33 = (unsigned int)lpMem;
    if ( lpMem )
      v33 = htonl(*((_DWORD *)lpMem + 12));
    v34 = v60 != 0;
    v60 = -v60;
    *(_DWORD *)&v11[v10 + 24] = v33;
    v11[v10 + 28] = 0;
    v11[v10 + 30] = v34 ? v55 : 0;
  }
  else
  {
    v30 = v27[4];
    v31 = 9;
    v67 = 0;
  }
  if ( v64 )
  {
    MulticastOwner(v64, &v68, 0);
    if ( v68 )
    {
      if ( v64 == v25 && v31 < 8u )
        v31 = 8;
    }
    else if ( v31 < 7u )
    {
      v31 = 7;
    }
  }
  else
  {
    v68 = 0;
  }
  if ( v25 && (unsigned int)RmHasBoundary(*(unsigned int *)(v25 + 16), v65[1]) )
    goto LABEL_88;
  v35 = v64;
  if ( !v64 )
    goto LABEL_92;
  if ( (unsigned int)RmHasBoundary(*(unsigned int *)(v64 + 16), v65[1]) )
  {
LABEL_88:
    v36 = v31;
    if ( v31 < 6u )
      v36 = 6;
    v31 = v36;
  }
  v35 = v64;
LABEL_92:
  if ( lpMem && v35 )
  {
    v37 = *((_DWORD *)lpMem + 11);
    v38 = 0;
    if ( v37 )
    {
      while ( 1 )
      {
        v39 = 28LL * v38;
        if ( *(_DWORD *)(v35 + 16) == *(_DWORD *)((char *)lpMem + v39 + 64)
          && v62 == *(_DWORD *)((char *)lpMem + v39 + 68) )
        {
          break;
        }
        if ( ++v38 >= v37 )
          goto LABEL_98;
      }
    }
    else
    {
LABEL_98:
      if ( v38 >= v37 )
      {
        v40 = v31;
        if ( v31 < 2u )
          v40 = 2;
        v31 = v40;
      }
    }
  }
  if ( v68 )
  {
    v41 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _BYTE *))(v68 + 208);
    if ( v41 )
    {
      v41(*(unsigned int *)(v35 + 16), v65[1], v65[2], v56);
      v42 = v31;
      if ( v31 < v56[0] )
        v42 = v56[0];
      v31 = v42;
    }
  }
  if ( v67 )
  {
    v43 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _BYTE *))(v67 + 208);
    if ( v43 )
    {
      v43(*(unsigned int *)(v25 + 16), v65[1], v65[2], v56);
      v44 = v31;
      if ( v31 < v56[0] )
        v44 = v56[0];
      v31 = v44;
    }
  }
  v11[v10 + 31] = *((_BYTE *)qword_180076780 + 4 * v31);
  v45 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
  {
    v47 = v65;
  }
  else
  {
    LOWORD(v73) = 0;
    if ( v25 )
      v46 = *(_DWORD *)(v25 + 16);
    else
      v46 = 0;
    v47 = v65;
    LODWORD(v50) = v46;
    LODWORD(v49) = *((unsigned __int8 *)v65 + 1);
    FormatRRASErrorString(
      &v73,
      L"Mtrace: err %d blks %d maxhops %d iif %d prevhop %d.%d.%d.%d",
      (unsigned __int8)v11[v10 + 31],
      v61[0],
      v49,
      v50,
      (unsigned __int8)v11[v10 + 12],
      (unsigned __int8)v11[v10 + 13],
      (unsigned __int8)v11[v10 + 14],
      (unsigned __int8)v11[v10 + 15]);
    v45 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v73);
      v45 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( v61[0] == *((unsigned __int8 *)v47 + 1) )
    goto LABEL_123;
  if ( v30 )
    goto LABEL_124;
  if ( !v25 )
  {
LABEL_123:
    v30 = v47[4];
  }
  else
  {
    v30 = 33554656;
    *(_DWORD *)&v11[v10 + 12] = 33554656;
    v45 = Microsoft_Windows_RRASEnableBits;
  }
LABEL_124:
  if ( g_mcastDebugLevel )
  {
    if ( v45 < 0 )
    {
      LOWORD(v73) = 0;
      FormatRRASErrorString(&v73, L" QueryArrivalTime = %08x", *(unsigned int *)&v11[v10]);
      v45 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v73);
        v45 = Microsoft_Windows_RRASEnableBits;
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v73) = 0;
          LODWORD(v51) = (unsigned __int8)v11[v10 + 7];
          LODWORD(v50) = (unsigned __int8)v11[v10 + 6];
          LODWORD(v49) = (unsigned __int8)v11[v10 + 5];
          FormatRRASErrorString(
            &v73,
            L" IifAddr          = %08x (%d.%d.%d.%d)",
            *(unsigned int *)&v11[v10 + 4],
            (unsigned __int8)*(_DWORD *)&v11[v10 + 4],
            v49,
            v50,
            v51);
          v45 = Microsoft_Windows_RRASEnableBits;
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v73);
            v45 = Microsoft_Windows_RRASEnableBits;
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            {
              LOWORD(v73) = 0;
              LODWORD(v51) = (unsigned __int8)v11[v10 + 11];
              LODWORD(v50) = (unsigned __int8)v11[v10 + 10];
              LODWORD(v49) = (unsigned __int8)v11[v10 + 9];
              FormatRRASErrorString(
                &v73,
                L" OifAddr          = %08x (%d.%d.%d.%d)",
                *(unsigned int *)&v11[v10 + 8],
                (unsigned __int8)*(_DWORD *)&v11[v10 + 8],
                v49,
                v50,
                v51);
              v45 = Microsoft_Windows_RRASEnableBits;
              if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
              {
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v73);
                v45 = Microsoft_Windows_RRASEnableBits;
                if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                {
                  LOWORD(v73) = 0;
                  LODWORD(v51) = (unsigned __int8)v11[v10 + 15];
                  LODWORD(v50) = (unsigned __int8)v11[v10 + 14];
                  LODWORD(v49) = (unsigned __int8)v11[v10 + 13];
                  FormatRRASErrorString(
                    &v73,
                    L" PrevHopAddr      = %08x (%d.%d.%d.%d)",
                    *(unsigned int *)&v11[v10 + 12],
                    (unsigned __int8)*(_DWORD *)&v11[v10 + 12],
                    v49,
                    v50,
                    v51);
                  v45 = Microsoft_Windows_RRASEnableBits;
                  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                  {
                    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v73);
                    v45 = Microsoft_Windows_RRASEnableBits;
                    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                    {
                      LOWORD(v73) = 0;
                      FormatRRASErrorString(&v73, L" IifPacketCount   = %08x", *(unsigned int *)&v11[v10 + 16]);
                      v45 = Microsoft_Windows_RRASEnableBits;
                      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                      {
                        McTemplateU0z_EventWriteTransfer(
                          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                          RasRtrmgrTraceInfo,
                          &v73);
                        v45 = Microsoft_Windows_RRASEnableBits;
                        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                        {
                          LOWORD(v73) = 0;
                          FormatRRASErrorString(&v73, L" OifPacketCount   = %08x", *(unsigned int *)&v11[v10 + 20]);
                          v45 = Microsoft_Windows_RRASEnableBits;
                          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                          {
                            McTemplateU0z_EventWriteTransfer(
                              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                              RasRtrmgrTraceInfo,
                              &v73);
                            v45 = Microsoft_Windows_RRASEnableBits;
                            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                            {
                              LOWORD(v73) = 0;
                              FormatRRASErrorString(&v73, L" SGPacketCount    = %08x", *(unsigned int *)&v11[v10 + 24]);
                              v45 = Microsoft_Windows_RRASEnableBits;
                              if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                              {
                                McTemplateU0z_EventWriteTransfer(
                                  &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                  RasRtrmgrTraceInfo,
                                  &v73);
                                v45 = Microsoft_Windows_RRASEnableBits;
                                if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                                {
                                  LOWORD(v73) = 0;
                                  FormatRRASErrorString(
                                    &v73,
                                    L" IifProtocol      = %02x",
                                    (unsigned __int8)v11[v10 + 28]);
                                  v45 = Microsoft_Windows_RRASEnableBits;
                                  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                                  {
                                    McTemplateU0z_EventWriteTransfer(
                                      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                      RasRtrmgrTraceInfo,
                                      &v73);
                                    v45 = Microsoft_Windows_RRASEnableBits;
                                    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                                    {
                                      LOWORD(v73) = 0;
                                      FormatRRASErrorString(
                                        &v73,
                                        L" OifThreshold     = %02x",
                                        (unsigned __int8)v11[v10 + 29]);
                                      v45 = Microsoft_Windows_RRASEnableBits;
                                      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                                      {
                                        McTemplateU0z_EventWriteTransfer(
                                          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                          RasRtrmgrTraceInfo,
                                          &v73);
                                        v45 = Microsoft_Windows_RRASEnableBits;
                                        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                                        {
                                          LOWORD(v73) = 0;
                                          FormatRRASErrorString(
                                            &v73,
                                            L" SrcMaskLength    = %02x",
                                            (unsigned __int8)v11[v10 + 30]);
                                          v45 = Microsoft_Windows_RRASEnableBits;
                                          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                                          {
                                            McTemplateU0z_EventWriteTransfer(
                                              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                              RasRtrmgrTraceInfo,
                                              &v73);
                                            v45 = Microsoft_Windows_RRASEnableBits;
                                            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                                            {
                                              LOWORD(v73) = 0;
                                              FormatRRASErrorString(
                                                &v73,
                                                L" StatusCode       = %02x",
                                                (unsigned __int8)v11[v10 + 31]);
                                              v45 = Microsoft_Windows_RRASEnableBits;
                                              if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                                              {
                                                McTemplateU0z_EventWriteTransfer(
                                                  &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                                                  RasRtrmgrTraceInfo,
                                                  &v73);
                                                v45 = Microsoft_Windows_RRASEnableBits;
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v30 == v47[4] )
  {
    if ( v45 < 0 )
    {
      LODWORD(v54) = HIBYTE(v62);
      LODWORD(v53) = BYTE2(v62);
      LODWORD(v52) = BYTE1(v62);
      LODWORD(v51) = (unsigned __int8)v62;
      LODWORD(v50) = HIBYTE(v30);
      LODWORD(v49) = BYTE2(v30);
      LOWORD(v73) = 0;
      FormatRRASErrorString(
        &v73,
        L"Sending mtrace response to %d.%d.%d.%d from %d.%d.%d.%d",
        (unsigned __int8)v30,
        BYTE1(v30),
        v49,
        v50,
        v51,
        v52,
        v53,
        v54);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v73);
    }
    SendMtraceResponse(v30);
  }
  else
  {
    if ( v45 < 0 )
    {
      LODWORD(v54) = HIBYTE(v57);
      LODWORD(v53) = BYTE2(v57);
      LODWORD(v52) = BYTE1(v57);
      LODWORD(v51) = (unsigned __int8)v57;
      LODWORD(v50) = HIBYTE(v30);
      LODWORD(v49) = BYTE2(v30);
      LOWORD(v73) = 0;
      FormatRRASErrorString(
        &v73,
        L"Forwarding mtrace request to %d.%d.%d.%d from %d.%d.%d.%d",
        (unsigned __int8)v30,
        BYTE1(v30),
        v49,
        v50,
        v51,
        v52,
        v53,
        v54);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v73);
    }
    ForwardMtraceRequest(v30);
  }
  if ( lpMem )
    HeapFree(IPRouterHeap, 0, lpMem);
  LODWORD(v8) = HeapFree(IPRouterHeap, 0, v11);
  return (int)v8;
}

```

## disassembly

```asm
0x180038e74  mov     [rsp+arg_8], rbx
0x180038e79  mov     [rsp+arg_10], rsi
0x180038e7e  push    rdi
0x180038e7f  push    r12
0x180038e81  push    r13
0x180038e83  push    r14
0x180038e85  push    r15
0x180038e87  sub     rsp, 930h
0x180038e8e  mov     rax, cs:__security_cookie
0x180038e95  xor     rax, rsp
0x180038e98  mov     [rsp+958h+var_38], rax
0x180038ea0  xor     r14d, r14d
0x180038ea3  mov     rsi, rcx
0x180038ea6  xor     edx, edx; Val
0x180038ea8  mov     [rsp+958h+pdwBufferSize], r14d
0x180038ead  lea     rcx, [rsp+958h+pimm]; void *
0x180038eb5  mov     [rsp+958h+var_907], r14b
0x180038eba  mov     [rsp+958h+var_8E0], r14
0x180038ebf  lea     r8d, [r14+4Ch]; Size
0x180038ec3  mov     [rsp+958h+var_8EC], r14d
0x180038ec8  call    memset_0
0x180038ecd  mov     rdi, [rsi+8]
0x180038ed1  lea     rcx, [rsp+958h+var_834]; void *
0x180038ed9  xor     edx, edx; Val
0x180038edb  mov     [rsp+958h+var_8C0], r14
0x180038ee3  mov     r8d, 7FCh; Size
0x180038ee9  mov     [rsp+958h+var_8C8], r14
0x180038ef1  mov     [rsp+958h+var_908], r14b
0x180038ef6  mov     [rsp+958h+var_904], r14d
0x180038efb  mov     [rsp+958h+var_8FC], r14d
0x180038f00  mov     [rsp+958h+var_8F4], r14d
0x180038f05  mov     [rsp+958h+var_838], r14d
0x180038f0d  call    memset_0
0x180038f12  movzx   eax, byte ptr [rdi]
0x180038f15  movzx   ecx, word ptr [rdi+2]; netshort
0x180038f19  and     eax, 0Fh
0x180038f1c  lea     ebx, ds:0[rax*4]
0x180038f23  mov     r13d, ebx
0x180038f26  add     r13, rdi
0x180038f29  mov     [rsp+958h+var_8D8], r13
0x180038f31  call    cs:__imp_ntohs
0x180038f37  movzx   eax, ax
0x180038f3a  sub     eax, ebx
0x180038f3c  mov     ebx, eax
0x180038f3e  sub     rbx, 18h
0x180038f42  shr     rbx, 5
0x180038f46  mov     [rsp+958h+var_898], rbx
0x180038f4e  test    ebx, ebx
0x180038f50  jnz     loc_180038FEF
0x180038f56  mov     r8d, [r13+0Ch]
0x180038f5a  lea     rdx, [rsp+958h+var_8EC]
0x180038f5f  lea     rcx, [rsp+958h+var_8E0]
0x180038f64  call    FindBindingWithRemoteAddress
0x180038f69  test    eax, eax
0x180038f6b  jz      loc_180039050
0x180038f71  mov     ecx, [rdi+10h]; netlong
0x180038f74  call    cs:__imp_ntohl
0x180038f7a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180038f81  jge     short loc_180038FDE
0x180038f83  mov     word ptr [rsp+958h+var_838], r14w
0x180038f8c  lea     rdx, aMtraceReinject; "Mtrace: reinjecting packet to %d.%d.%d."...
0x180038f93  movzx   ecx, byte ptr [rdi+12h]
0x180038f97  movzx   eax, byte ptr [rdi+13h]
0x180038f9b  movzx   r9d, byte ptr [rdi+11h]
0x180038fa0  movzx   r8d, byte ptr [rdi+10h]
0x180038fa5  mov     dword ptr [rsp+958h+var_930], eax
0x180038fa9  mov     dword ptr [rsp+958h+var_938], ecx
0x180038fad  lea     rcx, [rsp+958h+var_838]
0x180038fb5  call    FormatRRASErrorString
0x180038fba  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180038fc1  jge     short loc_180038FDE
0x180038fc3  lea     r8, [rsp+958h+var_838]
0x180038fcb  lea     rdx, RasRtrmgrTraceInfo
0x180038fd2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180038fd9  call    McTemplateU0z_EventWriteTransfer
0x180038fde  mov     r8d, [r13+0Ch]
0x180038fe2  mov     rdx, rsi
0x180038fe5  call    McSendPacketTo
0x180038fea  jmp     loc_180039DDE
0x180038fef  mov     ecx, [rdi+10h]; netlong
0x180038ff2  call    cs:__imp_ntohl
0x180038ff8  and     eax, 0F0000000h
0x180038ffd  cmp     eax, 0E0000000h
0x180039002  jnz     short loc_180039014
0x180039004  mov     eax, [rdi+10h]
0x180039007  and     eax, 0F0h
0x18003900c  cmp     al, 0E0h
0x18003900e  jnz     loc_180039DDE
0x180039014  lea     r8, [rsp+958h+var_8EC]
0x180039019  mov     rcx, rdi
0x18003901c  lea     rdx, [rsp+958h+var_8E0]
0x180039021  call    FindBindingForPacket
0x180039026  test    eax, eax
0x180039028  jz      short loc_180039050
0x18003902a  cmp     cs:g_mcastDebugLevel, r14d
0x180039031  jbe     loc_180039DDE
0x180039037  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18003903e  jz      loc_180039DDE
0x180039044  lea     r8, aMtraceNoMatchi; "Mtrace: no matching interface"
0x18003904b  jmp     loc_180039DCB
0x180039050  mov     eax, ebx
0x180039052  mov     ecx, 0FFFFFFFFh
0x180039057  shl     rax, 5
0x18003905b  cmp     rax, rcx
0x18003905e  ja      loc_180039DBB
0x180039064  lea     ebx, [rax+18h]
0x180039067  cmp     ebx, eax
0x180039069  jb      loc_180039DA9
0x18003906f  lea     eax, [rbx+20h]
0x180039072  mov     [rsp+958h+var_8F0], eax
0x180039076  cmp     eax, ebx
0x180039078  jb      loc_180039DBB
0x18003907e  mov     rcx, cs:IPRouterHeap; hHeap
0x180039085  xor     edx, edx; dwFlags
0x180039087  mov     r8d, eax; dwBytes
0x18003908a  call    cs:__imp_HeapAlloc
0x180039090  mov     rsi, rax
0x180039093  test    rax, rax
0x180039096  jnz     short loc_1800390B1
0x180039098  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18003909f  jz      loc_180039DDE
0x1800390a5  lea     r8, aCouldnTAllocat; "Couldn't allocate memory for mtrace res"...
0x1800390ac  jmp     loc_180039DCB
0x1800390b1  mov     r8, rbx; Size
0x1800390b4  mov     rdx, r13; Src
0x1800390b7  mov     rcx, rsi; void *
0x1800390ba  call    memcpy_0
0x1800390bf  xorps   xmm0, xmm0
0x1800390c2  movups  xmmword ptr [rbx+rsi], xmm0
0x1800390c6  movups  xmmword ptr [rbx+rsi+10h], xmm0
0x1800390cb  call    GetCurrentNTP32Time
0x1800390d0  mov     r12, [rsp+958h+var_8E0]
0x1800390d5  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800390dc  mov     [rbx+rsi], eax
0x1800390df  mov     eax, [rsp+958h+var_8EC]
0x1800390e3  mov     [rbx+rsi+14h], r14d
0x1800390e8  mov     [rbx+rsi+1Dh], r14b
0x1800390ed  lea     r14, RasRtrmgrTraceInfo
0x1800390f4  mov     [rbx+rsi+8], eax
0x1800390f8  test    r12, r12
0x1800390fb  jz      loc_1800391BF
0x180039101  xorps   xmm0, xmm0
0x180039104  lea     rdx, [rsp+958h+var_8B8]
0x18003910c  mov     rcx, r12
0x18003910f  movups  [rsp+958h+var_8B8], xmm0
0x180039117  movups  xmmword ptr [rsp+958h+hostlong], xmm0
0x18003911f  call    GetInterfaceMcastCounters
0x180039124  test    eax, eax
0x180039126  jz      short loc_18003914E
0x180039128  mov     al, byte ptr cs:Microsoft_Windows_RRASEnableBits
0x18003912e  and     al, 80h
0x180039130  mov     byte ptr [rsp+958h+var_900], al
0x180039134  jz      loc_1800391BF
0x18003913a  lea     r8, aMtraceGetinter; "MTrace: GetInterfaceMcastCounters faile"...
0x180039141  mov     rdx, r14
0x180039144  mov     rcx, r15
0x180039147  call    McTemplateU0z_EventWriteTransfer
0x18003914c  jmp     short loc_1800391BF
0x18003914e  mov     ecx, [rsp+958h+hostlong+8]; hostlong
0x180039155  call    cs:__imp_htonl
0x18003915b  cmp     cs:g_mcastDebugLevel, 0
0x180039162  mov     [rbx+rsi+14h], eax
0x180039166  jbe     short loc_1800391B3
0x180039168  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18003916f  jge     short loc_1800391B3
0x180039171  mov     r8, qword ptr [rsp+958h+hostlong+8]
0x180039179  lea     rdx, aDwoifpacketcou; "dwOifPacketCount = %d"
0x180039180  xor     eax, eax
0x180039182  lea     rcx, [rsp+958h+var_838]
0x18003918a  mov     word ptr [rsp+958h+var_838], ax
0x180039192  call    FormatRRASErrorString
0x180039197  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18003919e  jge     short loc_1800391B3
0x1800391a0  lea     r8, [rsp+958h+var_838]
0x1800391a8  mov     rdx, r14
0x1800391ab  mov     rcx, r15
0x1800391ae  call    McTemplateU0z_EventWriteTransfer
0x1800391b3  mov     al, [r12+144h]
0x1800391bb  mov     [rbx+rsi+1Dh], al
0x1800391bf  xor     edx, edx; Val
0x1800391c1  lea     rcx, [rsp+958h+pimm]; void *
0x1800391c9  lea     r8d, [rdx+4Ch]; Size
0x1800391cd  call    memset_0
0x1800391d2  mov     eax, [r13+4]
0x1800391d6  lea     rdx, [rsp+958h+pdwBufferSize]; pdwBufferSize
0x1800391db  mov     [rsp+958h+pimm.dwGroup], eax
0x1800391e2  lea     rcx, [rsp+958h+pimm]; pimm
0x1800391ea  mov     eax, [r13+8]
0x1800391ee  mov     r9d, 1; dwFlags
0x1800391f4  mov     [rsp+958h+pimm.dwSource], eax
0x1800391fb  xor     r8d, r8d; pbBuffer
0x1800391fe  mov     eax, 0FFFFFFFFh
0x180039203  mov     [rsp+958h+pdwBufferSize], 0
0x18003920b  mov     [rsp+958h+pimm.dwSrcMask], eax
0x180039212  call    cs:__imp_MgmGetMfeStats
0x180039218  test    eax, eax
0x18003921a  jz      short loc_18003922D
0x18003921c  mov     [rsp+958h+lpMem], 0
0x180039228  jmp     loc_1800392C2
0x18003922d  mov     r8d, [rsp+958h+pdwBufferSize]; dwBytes
0x180039232  xor     edx, edx; dwFlags
0x180039234  mov     rcx, cs:IPRouterHeap; hHeap
0x18003923b  call    cs:__imp_HeapAlloc
0x180039241  mov     r9d, 1; dwFlags
0x180039247  lea     rdx, [rsp+958h+pdwBufferSize]; pdwBufferSize
0x18003924c  lea     rcx, [rsp+958h+pimm]; pimm
0x180039254  mov     [rsp+958h+lpMem], rax
0x18003925c  mov     r8, rax; pbBuffer
0x18003925f  mov     r12, rax
0x180039262  call    cs:__imp_MgmGetMfeStats
0x180039268  test    eax, eax
0x18003926a  jz      short loc_18003928A
0x18003926c  mov     rcx, cs:IPRouterHeap; hHeap
0x180039273  mov     r8, r12; lpMem
0x180039276  xor     edx, edx; dwFlags
0x180039278  call    cs:__imp_HeapFree
0x18003927e  xor     ecx, ecx
0x180039280  mov     [rsp+958h+lpMem], rcx
0x180039288  jmp     short loc_1800392C2
0x18003928a  test    r12, r12
0x18003928d  jz      short loc_1800392BA
0x18003928f  mov     rcx, [rsp+958h+lpMem]
0x180039297  mov     r12d, [r12+10h]
0x18003929c  mov     r13d, [rcx+0Ch]
0x1800392a0  mov     ecx, [rcx+20h]
0x1800392a3  mov     [rsp+958h+var_900], r13d
0x1800392a8  call    MaskToMaskLen
0x1800392ad  mov     [rsp+958h+var_8F8], 1
0x1800392b5  jmp     loc_1800393A8
0x1800392ba  mov     [rsp+958h+lpMem], r12
0x1800392c2  mov     ecx, [r13+8]
0x1800392c6  lea     r9, [rsp+958h+var_904]
0x1800392cb  mov     eax, 0FFFFFFFFh
0x1800392d0  lea     r8, [rsp+958h+var_908]
0x1800392d5  xor     edx, edx
0x1800392d7  cmp     ecx, eax
0x1800392d9  lea     rax, [rsp+958h+var_8F4]
0x1800392de  mov     [rsp+958h+var_930], rax
0x1800392e3  lea     rax, [rsp+958h+var_8FC]
0x1800392e8  mov     [rsp+958h+var_938], rax
0x1800392ed  jnz     short loc_18003934F
0x1800392ef  mov     ecx, [r13+4]
0x1800392f3  call    McLookupRoute
0x1800392f8  mov     [rsp+958h+var_8F8], eax
0x1800392fc  mov     eax, [rsp+958h+var_904]
0x180039300  mov     [rsp+958h+var_900], eax
0x180039304  cmp     eax, 100007Fh
0x180039309  jnz     short loc_180039343
0x18003930b  mov     ecx, [r13+4]
0x18003930f  lea     rax, [rsp+958h+var_8F4]
0x180039314  mov     [rsp+958h+var_930], rax
0x180039319  lea     r9, [rsp+958h+var_904]
0x18003931e  lea     rax, [rsp+958h+var_8FC]
0x180039323  mov     edx, 1
0x180039328  lea     r8, [rsp+958h+var_908]
0x18003932d  mov     [rsp+958h+var_938], rax
0x180039332  call    McLookupRoute
0x180039337  mov     ecx, [rsp+958h+var_904]
0x18003933b  mov     [rsp+958h+var_900], ecx
0x18003933f  mov     [rsp+958h+var_8F8], eax
0x180039343  mov     r12d, [rsp+958h+var_8FC]
0x180039348  mov     [rsp+958h+var_908], 0
0x18003934d  jmp     short loc_1800393AC
0x18003934f  call    McLookupRoute
0x180039354  mov     [rsp+958h+var_8F8], eax
0x180039358  mov     eax, [rsp+958h+var_904]
0x18003935c  mov     [rsp+958h+var_900], eax
0x180039360  cmp     eax, 100007Fh
0x180039365  jnz     short loc_18003939F
0x180039367  mov     ecx, [r13+8]
0x18003936b  lea     rax, [rsp+958h+var_8F4]
0x180039370  mov     [rsp+958h+var_930], rax
0x180039375  lea     r9, [rsp+958h+var_904]
0x18003937a  lea     rax, [rsp+958h+var_8FC]
0x18003937f  mov     edx, 1
0x180039384  lea     r8, [rsp+958h+var_908]
0x180039389  mov     [rsp+958h+var_938], rax
0x18003938e  call    McLookupRoute
0x180039393  mov     ecx, [rsp+958h+var_904]
0x180039397  mov     [rsp+958h+var_900], ecx
0x18003939b  mov     [rsp+958h+var_8F8], eax
0x18003939f  mov     r12d, [rsp+958h+var_8FC]
0x1800393a4  mov     al, [rsp+958h+var_908]
0x1800393a8  mov     [rsp+958h+var_908], al
0x1800393ac  test    r12d, r12d
0x1800393af  jz      short loc_180039411
0x1800393b1  mov     edx, 1
0x1800393b6  mov     ecx, r12d
0x1800393b9  call    InterfaceLookupByIfIndex
0x1800393be  mov     r13, rax
0x1800393c1  test    rax, rax
0x1800393c4  jz      short loc_180039414
0x1800393c6  mov     rcx, rax
0x1800393c9  call    defaultSourceAddress
0x1800393ce  mov     r12, [rsp+958h+var_8D8]
0x1800393d6  mov     ecx, eax
0x1800393d8  mov     [rsp+958h+var_904], eax
0x1800393dc  mov     eax, 0FFFFFFFFh
0x1800393e1  mov     edx, [r12+8]
0x1800393e6  cmp     edx, eax
  ... truncated ...
```
