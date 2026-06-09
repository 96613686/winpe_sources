# ProcessLineUpWorker

- ea: `0x180015ae0`
- end: `0x180016991`
- name: `ProcessLineUpWorker`
- size: `3761`
- prototype: `unsigned int __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x180014ba0`
- `0x180015ac0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x180004134`
- `0x18000b9ac`
- `0x18000be0c`
- `0x18000c9a0`
- `0x18000cb10`
- `0x18000f334`
- `0x18000f8ac`
- `0x18000fc6c`
- `0x180010850`
- `0x180010f2c`
- `0x180011038`
- `0x1800111d8`
- `0x180013490`
- `0x1800134c4`
- `0x180013908`
- `0x180013a58`
- `0x180013af8`
- `0x180015ae0`
- `0x18002a138`
- `0x180032460`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x180016524`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x180016524`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800167c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800167c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015bce`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015bce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016756`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016763`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016756`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016763`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015f60`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015f92`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016403`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001645f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800164ba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015f60`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015f92`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016403`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001645f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800164ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015bdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015bdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015f76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016749`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016749`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180015d6a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180015d6a`

## string_xrefs

- `0x180016626`: `Starting PPP on link with IfType=0x%x,IPIf=0x%x,IPv6If=0x%x`

## pseudocode

```c
unsigned int __fastcall ProcessLineUpWorker(__int64 a1, int a2)
{
  __int64 v4; // r8
  __int64 PCBPointerFromhPort; // rax
  _DWORD *v6; // rdi
  DWORD LastError; // eax
  _DWORD *v8; // r14
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int result; // eax
  unsigned int v12; // eax
  unsigned int v13; // ebx
  int v14; // ecx
  bool v15; // cf
  __int64 v16; // r8
  __int64 v17; // rax
  const char *v18; // r8
  int v19; // eax
  __int64 v20; // r10
  int *v21; // rcx
  __int64 v22; // rdx
  _OWORD *v23; // rax
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int64 v26; // rbx
  __int64 v27; // rbx
  _OWORD *v28; // rax
  _OWORD *v29; // rcx
  __int64 v30; // rdx
  __int128 v31; // xmm1
  _OWORD *v32; // rbx
  __int64 v33; // rcx
  char *v34; // rcx
  _OWORD *v35; // rax
  __int64 v36; // rcx
  __int128 v37; // xmm1
  _OWORD *v38; // rcx
  __int64 v39; // rdx
  _OWORD *v40; // rax
  __int128 v41; // xmm1
  __int64 v42; // r10
  __int64 v43; // rdx
  __int64 v44; // rbx
  char *v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // r10
  __int64 v48; // rdx
  __int64 v49; // r15
  __int64 v50; // rbx
  char *v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // r10
  __int64 v54; // rdx
  __int64 v55; // r15
  __int64 v56; // rbx
  char *v57; // rcx
  __int64 v58; // rdx
  __int64 v59; // r11
  __int64 v60; // rax
  unsigned __int8 *v61; // rbx
  unsigned __int8 v62; // r15
  unsigned int v63; // r12d
  __int64 v64; // r13
  _DWORD *v65; // rcx
  __int64 v66; // r8
  unsigned int v67; // eax
  __int64 v68; // rdx
  unsigned int v69; // eax
  void *v70; // rcx
  __int64 v71; // rax
  __int64 v72; // rbx
  bool v73; // zf
  __int64 v74; // rbx
  int v75; // [rsp+40h] [rbp-C0h] BYREF
  int v76; // [rsp+44h] [rbp-BCh]
  __int64 Src; // [rsp+48h] [rbp-B8h] BYREF
  int v78; // [rsp+50h] [rbp-B0h]
  _BYTE v79[872]; // [rsp+60h] [rbp-A0h] BYREF
  int v80; // [rsp+3C8h] [rbp+2C8h]
  int v81; // [rsp+3CCh] [rbp+2CCh]
  int v82; // [rsp+400h] [rbp+300h] BYREF
  _BYTE v83[2044]; // [rsp+404h] [rbp+304h] BYREF

  v78 = a2;
  v75 = 0;
  memset_0(v79, 0, 0x398u);
  strcpy((char *)&Src, "{NA}");
  v82 = 0;
  memset_0(v83, 0, sizeof(v83));
  if ( (byte_18004CF34 & 1) != 0 )
  {
    v4 = *(_QWORD *)(a1 + 16);
    LOWORD(v82) = 0;
    FormatRRASErrorString(&v82, L"Line up event occurred on port %d", v4);
    if ( (byte_18004CF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v82);
  }
  PCBPointerFromhPort = GetPCBPointerFromhPort(*(_QWORD *)(a1 + 16));
  v6 = (_DWORD *)PCBPointerFromhPort;
  if ( PCBPointerFromhPort )
  {
    RemovePcbFromTable(PCBPointerFromhPort);
  }
  else
  {
    v6 = HeapAlloc(hHeap, 8u, 0x700u);
    if ( !v6 )
    {
      LastError = GetLastError();
      v8 = (_DWORD *)(a1 + 32);
LABEL_7:
      v9 = (unsigned int)*v8;
LABEL_8:
      v10 = LastError;
LABEL_9:
      result = NotifyCallerOfFailureOnPort(*(_QWORD *)(a1 + 16), v9, v10);
      goto LABEL_116;
    }
  }
  v8 = (_DWORD *)(a1 + 32);
  if ( !*(_DWORD *)(a1 + 32) && (*(_DWORD *)(a1 + 2552) & 0x8000008) == 0 )
  {
    v9 = 0;
    v10 = 720;
    goto LABEL_9;
  }
  v12 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _BYTE *))&xmmword_18004C470 + 1))(0, *(_QWORD *)(a1 + 16), v79);
  v13 = v12;
  if ( v12 )
  {
    if ( byte_18004CF33 < 0 )
    {
      LOWORD(v82) = 0;
      FormatRRASErrorString(&v82, L"RasGetInfo failed and returned returned %d", v12);
      if ( byte_18004CF33 < 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v82);
    }
    result = NotifyCallerOfFailureOnPort(*(_QWORD *)(a1 + 16), (unsigned int)*v8, v13);
    goto LABEL_116;
  }
  *((_QWORD *)v6 + 5) = 0;
  *((_QWORD *)v6 + 2) = *(_QWORD *)(a1 + 16);
  *((_QWORD *)v6 + 3) = *(_QWORD *)(a1 + 24);
  *(_QWORD *)v6 = 0;
  *((_BYTE *)v6 + 32) = 0;
  v14 = dword_18004CACC;
  v76 = 0;
  ++dword_18004CACC;
  v6[16] = v14;
  v6[9] = CalculateRestartTimer(*(_QWORD *)(a1 + 16));
  v6[12] = 0;
  v15 = *v8 != 0;
  *((_QWORD *)v6 + 19) = 0;
  *((_QWORD *)v6 + 20) = 0;
  *((_QWORD *)v6 + 21) = 0;
  *((_QWORD *)v6 + 22) = 0;
  v6[29] = -1;
  v6[14] |= (a2 != 0 ? 8 : 0) | (v15 ? 4 : 0);
  v6[15] = v81;
  StringCchCopyA((STRSAFE_LPSTR)v6 + 1712, 0x28u, "{NA}");
  v16 = -1;
  do
    ++v16;
  while ( *((_BYTE *)&Src + v16) );
  memcpy_0(v6 + 428, &Src, v16 + 1);
  GetSystemTimeAsFileTime((LPFILETIME)v6 + 190);
  if ( !*((_QWORD *)v6 + 1) )
  {
    LastError = AllocateAndInitBcb(v6);
    if ( LastError )
      goto LABEL_7;
    v76 = 1;
  }
  LastError = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))xmmword_18004C410)(
                0,
                *((_QWORD *)v6 + 2),
                *((_QWORD *)v6 + 1) + 40LL);
  v9 = (unsigned int)*v8;
  if ( LastError )
    goto LABEL_8;
  *(_DWORD *)(*((_QWORD *)v6 + 1) + 52LL) |= (_DWORD)v9 != 0 ? 0x200 : 0;
  *(_BYTE *)(*((_QWORD *)v6 + 1) + 216LL) = 0;
  *(_BYTE *)(*((_QWORD *)v6 + 1) + 473LL) = 0;
  *(_BYTE *)(*((_QWORD *)v6 + 1) + 1019LL) = 0;
  if ( (v6[14] & 4) != 0 )
  {
    v17 = *((_QWORD *)v6 + 1);
    v18 = (const char *)(a1 + 72);
    v6[32] = -1;
    v6[28] = 1;
    *(_QWORD *)(v17 + 64) = -1;
    v19 = 0;
    if ( !a2 )
      v19 = *(_DWORD *)v18;
    v6[13] = v19;
    if ( a2 )
    {
      StringCbCopyA((STRSAFE_LPSTR)v6 + 1536, 0x81u, v18);
    }
    else
    {
      StringCbCopyA((STRSAFE_LPSTR)v6 + 1665, 0x11u, (STRSAFE_LPCSTR)(a1 + 76));
      if ( (byte_18004CF34 & 1) != 0 )
      {
        LOWORD(v82) = 0;
        FormatRRASErrorString(&v82, L"PortName: %hs", v20);
        if ( (byte_18004CF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v82);
      }
    }
    memset_0(v6 + 46, 0, 0x430u);
    v21 = &dword_18004CAD0;
    *((_QWORD *)v6 + 191) = 0;
    v22 = 8;
    *(_BYTE *)(*((_QWORD *)v6 + 1) + 1276LL) = 0;
    v23 = v6 + 46;
    do
    {
      *v23 = *(_OWORD *)v21;
      v23[1] = *((_OWORD *)v21 + 1);
      v23[2] = *((_OWORD *)v21 + 2);
      v23[3] = *((_OWORD *)v21 + 3);
      v23[4] = *((_OWORD *)v21 + 4);
      v23[5] = *((_OWORD *)v21 + 5);
      v23[6] = *((_OWORD *)v21 + 6);
      v24 = *((_OWORD *)v21 + 7);
      v21 += 32;
      v23[7] = v24;
      v23 += 8;
      --v22;
    }
    while ( v22 );
    *v23 = *(_OWORD *)v21;
    v23[1] = *((_OWORD *)v21 + 1);
    v25 = *((_OWORD *)v21 + 2);
    v6[22] = 0;
    v23[2] = v25;
    *(_BYTE *)(*((_QWORD *)v6 + 1) + 489LL) = 0;
    *(_BYTE *)(*((_QWORD *)v6 + 1) + 746LL) = 0;
    *(_BYTE *)(*((_QWORD *)v6 + 1) + 762LL) = 0;
    *(_DWORD *)(*((_QWORD *)v6 + 1) + 52LL) |= 4u;
    v26 = *((_QWORD *)v6 + 1);
    *(_QWORD *)(v26 + 104) = LocalAlloc(0x40u, 0x81u);
    if ( *(_QWORD *)(*((_QWORD *)v6 + 1) + 104LL) )
    {
      v27 = *((_QWORD *)v6 + 1);
      *(_QWORD *)(v27 + 112) = LocalAlloc(0x40u, 0x81u);
      if ( *(_QWORD *)(*((_QWORD *)v6 + 1) + 112LL) )
      {
        *(_OWORD *)(v6 + 423) = *(_OWORD *)(a1 + 1640);
        PrintGuid((STRSAFE_LPSTR)v6 + 1712);
        if ( (byte_18004CF34 & 1) != 0 )
        {
          LOWORD(v82) = 0;
          FormatRRASErrorString(&v82, L"CorrelationGuidStr: %hs from ddm ", v6 + 428);
          if ( (byte_18004CF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v82);
        }
        *(_OWORD *)(v6 + 438) = *(_OWORD *)(a1 + 1600);
        v6[442] = *(_DWORD *)(a1 + 1616);
        *(_OWORD *)(v6 + 443) = *(_OWORD *)(a1 + 1620);
        v6[447] = *(_DWORD *)(a1 + 1636);
        if ( (*(_BYTE *)(a1 + 1656) & 0x40) != 0 )
        {
          v28 = (_OWORD *)(a1 + 1660);
          v29 = (_OWORD *)(*((_QWORD *)v6 + 1) + 489LL);
          v30 = 2;
          do
          {
            *v29 = *v28;
            v29[1] = v28[1];
            v29[2] = v28[2];
            v29[3] = v28[3];
            v29[4] = v28[4];
            v29[5] = v28[5];
            v29[6] = v28[6];
            v31 = v28[7];
            v28 += 8;
            v29[7] = v31;
            v29 += 8;
            --v30;
          }
          while ( v30 );
          *(_BYTE *)v29 = *(_BYTE *)v28;
          *(_OWORD *)(*((_QWORD *)v6 + 1) + 746LL) = *(_OWORD *)(a1 + 1917);
          v6[46] |= 0x4000u;
          if ( (byte_18004CF34 & 1) != 0 )
          {
            LOWORD(v82) = 0;
            FormatRRASErrorString(
              &v82,
              L" BypassAuth for  %hs\\%hs",
              *((_QWORD *)v6 + 1) + 746LL,
              *((_QWORD *)v6 + 1) + 489LL);
            if ( (byte_18004CF34 & 1) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v82);
          }
        }
LABEL_102:
        *((_QWORD *)v6 + 19) = GetUserAttributes(v6);
        goto LABEL_103;
      }
    }
LABEL_36:
    LastError = GetLastError();
    v9 = 1;
    goto LABEL_8;
  }
  v32 = (_OWORD *)(a1 + 2552);
  if ( (*(_DWORD *)(a1 + 2552) & 0x8000) != 0 )
    v6[32] = *(_DWORD *)(a1 + 6956);
  v33 = *((_QWORD *)v6 + 1);
  v6[33] = *(_DWORD *)(a1 + 2572);
  *(_QWORD *)(v33 + 64) = *(_QWORD *)(a1 + 6944);
  *(_QWORD *)(*((_QWORD *)v6 + 1) + 88LL) = *(_QWORD *)(a1 + 6960);
  *(_QWORD *)(*((_QWORD *)v6 + 1) + 96LL) = *(_QWORD *)(a1 + 6968);
  *(_OWORD *)(v6 + 423) = *(_OWORD *)(a1 + 6992);
  PrintGuid((STRSAFE_LPSTR)v6 + 1712);
  if ( (*(_BYTE *)(a1 + 2564) & 1) != 0 )
    *(_DWORD *)(*((_QWORD *)v6 + 1) + 52LL) |= 0x40u;
  if ( (*(_BYTE *)(a1 + 2564) & 4) != 0 )
    v6[14] |= 0x800u;
  if ( *(char *)(a1 + 2564) < 0 )
    v6[14] |= 0x800000u;
  if ( (*(_BYTE *)(a1 + 2564) & 2) != 0 )
    v6[14] |= 0x10000u;
  if ( (*(_BYTE *)(a1 + 2564) & 0x20) != 0 )
    v6[14] |= 0x200000u;
  if ( (*(_DWORD *)(a1 + 2564) & 0x100) != 0 )
    v6[14] |= 0x1000000u;
  v34 = (char *)(*((_QWORD *)v6 + 1) + 489LL);
  v6[314] = v80;
  v6[13] = 0;
  StringCbCopyA(v34, 0x101u, (STRSAFE_LPCSTR)(a1 + 2014));
  *(_OWORD *)(*((_QWORD *)v6 + 1) + 184LL) = *(_OWORD *)(a1 + 6976);
  *(_OWORD *)(a1 + 6976) = 0;
  StringCbCopyA((STRSAFE_LPSTR)(*((_QWORD *)v6 + 1) + 746LL), 0x10u, (STRSAFE_LPCSTR)(a1 + 2528));
  v35 = v6 + 46;
  *((_QWORD *)v6 + 191) = *(_QWORD *)(a1 + 2544);
  v36 = 8;
  do
  {
    *v35 = *v32;
    v35[1] = v32[1];
    v35[2] = v32[2];
    v35[3] = v32[3];
    v35[4] = v32[4];
    v35[5] = v32[5];
    v35[6] = v32[6];
    v37 = v32[7];
    v32 += 8;
    v35[7] = v37;
    v35 += 8;
    --v36;
  }
  while ( v36 );
  v38 = (_OWORD *)(a1 + 3624);
  v39 = 4;
  *v35 = *v32;
  v35[1] = v32[1];
  v35[2] = v32[2];
  v6[22] = *(_DWORD *)(a1 + 2560);
  v6[23] = dword_18004CA24;
  v6[24] = dword_18004CA28;
  v6[25] = dword_18004CA2C;
  v40 = (_OWORD *)(*((_QWORD *)v6 + 1) + 1344LL);
  do
  {
    *v40 = *v38;
    v40[1] = v38[1];
    v40[2] = v38[2];
    v40[3] = v38[3];
    v40[4] = v38[4];
    v40[5] = v38[5];
    v40[6] = v38[6];
    v41 = v38[7];
    v38 += 8;
    v40[7] = v41;
    v40 += 8;
    --v39;
  }
  while ( v39 );
  GetLocalComputerName((STRSAFE_LPSTR)(*((_QWORD *)v6 + 1) + 1276LL));
  StringCbCopyA((STRSAFE_LPSTR)v6 + 1665, 0x11u, (STRSAFE_LPCSTR)(a1 + 72));
  if ( (byte_18004CF34 & 1) != 0 )
  {
    LOWORD(v82) = 0;
    FormatRRASErrorString(&v82, L"PortName: %hs", v42);
    if ( (byte_18004CF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v82);
  }
  v43 = -1;
  do
    ++v43;
  while ( *(_BYTE *)(a1 + v43 + 89) );
  v44 = *((_QWORD *)v6 + 1);
  *(_QWORD *)(v44 + 152) = LocalAlloc(0x40u, v43 + 1);
  v45 = *(char **)(*((_QWORD *)v6 + 1) + 152LL);
  if ( !v45 )
    goto LABEL_36;
  v46 = -1;
  do
    ++v46;
  while ( *(_BYTE *)(a1 + v46 + 89) );
  StringCbCopyA(v45, v46 + 1, (STRSAFE_LPCSTR)(a1 + 89));
  v48 = v47;
  v49 = a1 + 349;
  do
    ++v48;
  while ( *(_BYTE *)(v49 + v48) );
  v50 = *((_QWORD *)v6 + 1);
  *(_QWORD *)(v50 + 160) = LocalAlloc(0x40u, v48 + 1);
  v51 = *(char **)(*((_QWORD *)v6 + 1) + 160LL);
  if ( !v51 )
    goto LABEL_36;
  v52 = -1;
  do
    ++v52;
  while ( *(_BYTE *)(v49 + v52) );
  StringCbCopyA(v51, v52 + 1, (STRSAFE_LPCSTR)(a1 + 349));
  v54 = v53;
  v55 = a1 + 1886;
  do
    ++v54;
  while ( *(_BYTE *)(v55 + v54) );
  v56 = *((_QWORD *)v6 + 1);
  *(_QWORD *)(v56 + 104) = LocalAlloc(0x40u, v54 + 1);
  v57 = *(char **)(*((_QWORD *)v6 + 1) + 104LL);
  if ( !v57 )
    goto LABEL_36;
  v58 = -1;
  do
    ++v58;
  while ( *(_BYTE *)(v55 + v58) );
  StringCbCopyA(v57, v58 + 1, (STRSAFE_LPCSTR)(a1 + 1886));
  v60 = v59;
  v61 = *(unsigned __int8 **)(*((_QWORD *)v6 + 1) + 104LL);
  do
    ++v60;
  while ( v61[v60] );
  Src = v60;
  if ( v61 )
  {
    v62 = *v61;
    v63 = 0;
    v64 = 0;
    while ( v62 && v63 < (unsigned int)v60 )
    {
      if ( (unsigned int)_o_isdigit(v62) )
      {
        v61[v64] = v62;
        v64 = (unsigned int)(v64 + 1);
      }
      LODWORD(v60) = Src;
      v62 = v61[++v63];
    }
    v61[v64] = 0;
  }
  *(_DWORD *)(*((_QWORD *)v6 + 1) + 52LL) |= 4u;
  *(_DWORD *)(*((_QWORD *)v6 + 1) + 52LL) |= 2u;
  if ( (v6[46] & 0x1000000) != 0 )
    *(_DWORD *)(*((_QWORD *)v6 + 1) + 52LL) &= ~4u;
  v65 = (_DWORD *)(*((_QWORD *)v6 + 1) + 1320LL);
  if ( *(_DWORD *)(a1 + 4152) == -1 )
  {
    *v65 = -1;
    *(_QWORD *)(*((_QWORD *)v6 + 1) + 1328LL) = -1;
    *(_QWORD *)(*((_QWORD *)v6 + 1) + 1336LL) = -1;
  }
  else
  {
    memcpy_0(v65, (const void *)(a1 + 4152), 0xAE8u);
    v66 = *((_QWORD *)v6 + 1);
    if ( *(_DWORD *)(v66 + 1320) == 2 )
    {
      if ( (*(_BYTE *)(a1 + 2564) & 8) != 0 )
        v6[22] = 0;
      StringCbCopyA((STRSAFE_LPSTR)(v66 + 216), 0x101u, *(STRSAFE_LPCSTR *)(v66 + 160));
      if ( (v6[46] & 0x800) != 0 )
        goto LABEL_102;
    }
  }
LABEL_103:
  if ( (byte_18004CF34 & 1) != 0 )
  {
    LOWORD(v82) = 0;
    FormatRRASErrorString(
      &v82,
      L"Starting PPP on link with IfType=0x%x,IPIf=0x%x,IPv6If=0x%x",
      *(unsigned int *)(*((_QWORD *)v6 + 1) + 1320LL),
      *(_QWORD *)(*((_QWORD *)v6 + 1) + 1328LL),
      *(_QWORD *)(*((_QWORD *)v6 + 1) + 1336LL));
    if ( (byte_18004CF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v82);
  }
  v75 = 1500;
  v67 = ((__int64 (__fastcall *)(_DWORD *, int *))xmmword_18004C4B0)(v6 + 10, &v75);
  if ( v67 )
  {
    result = NotifyCallerOfFailure(v6, v67);
  }
  else
  {
    if ( (byte_18004CF34 & 1) != 0 )
    {
      LOWORD(v82) = 0;
      FormatRRASErrorString(&v82, L"RasGetBuffer returned %x for SendBuf", *((_QWORD *)v6 + 5));
      if ( (byte_18004CF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v82);
    }
    v6[375] = 1;
    if ( (unsigned int)FsmInit(v6, 0) )
    {
      v69 = ((__int64 (__fastcall *)(_QWORD))xmmword_18004C420)(*((_QWORD *)v6 + 2));
      if ( !v69 )
      {
        v72 = *(_DWORD *)(a1 + 16) % (unsigned int)qword_18004C970;
        if ( (byte_18004CF34 & 1) != 0 )
        {
          LOWORD(v82) = 0;
          FormatRRASErrorString(&v82, L"Inserting port in bucket # %d", (unsigned int)v72);
          if ( (byte_18004CF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v82);
        }
        v73 = v76 == 0;
        *(_QWORD *)v6 = *((_QWORD *)PcbTable + v72);
        *((_QWORD *)PcbTable + v72) = v6;
        if ( !v73 )
        {
          v74 = *(_DWORD *)(*((_QWORD *)v6 + 1) + 40LL) % (unsigned int)qword_18004C970;
          if ( (byte_18004CF34 & 1) != 0 )
          {
            LOWORD(v82) = 0;
            FormatRRASErrorString(&v82, L"Inserting bundle in bucket # %d", (unsigned int)v74);
            if ( (byte_18004CF34 & 1) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v82);
          }
          **((_QWORD **)v6 + 1) = *((_QWORD *)*(&PcbTable + 1) + v74);
          *((_QWORD *)*(&PcbTable + 1) + v74) = *((_QWORD *)v6 + 1);
        }
        v6[374] = 721;
        FsmOpen(v6, 0);
        FsmUp(v6, 0);
        result = dword_18004CA04;
        if ( dword_18004CA04 )
          result = InsertInTimerQ(v6[16], *((_QWORD *)v6 + 2), 0, 0, 0, 3, dword_18004CA04);
        if ( (v6[14] & 4) != 0 && !v78 )
        {
          if ( v6[374] == 721 )
            v6[374] = 0;
          result = 49185;
          if ( (*(unsigned __int8 *)(a1 + 105) << 8) + *(unsigned __int8 *)(a1 + 106) == 0xC021 )
            return ReceiveViaParser(v6, a1 + 105, (unsigned int)(*(_DWORD *)(a1 + 1596) - 12));
        }
        return result;
      }
      v68 = v69;
    }
    else
    {
      v68 = (unsigned int)v6[374];
    }
    result = NotifyCallerOfFailure(v6, v68);
  }
LABEL_116:
  if ( *v8 )
  {
    if ( !v6 )
      return result;
    goto LABEL_123;
  }
  v70 = *(void **)(a1 + 6944);
  if ( v70 != (void *)-1LL )
    CloseHandle(v70);
  LocalFree(*(HLOCAL *)(a1 + 6960));
  result = (unsigned int)LocalFree(*(HLOCAL *)(a1 + 6968));
  if ( v6 )
  {
    v71 = *((_QWORD *)v6 + 1);
    if ( v71 )
    {
      *(_QWORD *)(v71 + 64) = -1;
      *(_QWORD *)(*((_QWORD *)v6 + 1) + 88LL) = 0;
      *(_QWORD *)(*((_QWORD *)v6 + 1) + 96LL) = 0;
    }
LABEL_123:
    DeallocateAndRemoveBcbFromTable(*((LPVOID *)v6 + 1));
    if ( *((_QWORD *)v6 + 5) )
      ((void (*)(void))xmmword_18004C460)();
    return HeapFree(hHeap, 0, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180015ae0  push    rbp
0x180015ae2  push    rbx
0x180015ae3  push    rsi
0x180015ae4  push    rdi
0x180015ae5  push    r12
0x180015ae7  push    r13
0x180015ae9  push    r14
0x180015aeb  push    r15
0x180015aed  lea     rbp, [rsp-0B18h]
0x180015af5  sub     rsp, 0C18h
0x180015afc  mov     rax, cs:__security_cookie
0x180015b03  xor     rax, rsp
0x180015b06  mov     [rbp+0B50h+var_50], rax
0x180015b0d  mov     r12d, edx
0x180015b10  mov     [rsp+0C50h+var_C00], edx
0x180015b14  mov     rsi, rcx
0x180015b17  xor     ebx, ebx
0x180015b19  xor     edx, edx; Val
0x180015b1b  mov     [rsp+0C50h+var_C10], ebx
0x180015b1f  lea     rcx, [rsp+0C50h+var_BF0]; void *
0x180015b24  mov     r8d, 398h; Size
0x180015b2a  call    memset_0
0x180015b2f  mov     eax, dword ptr cs:aNa; "{NA}"
0x180015b35  lea     rcx, [rbp+0B50h+var_84C]; void *
0x180015b3c  mov     dword ptr [rsp+0C50h+Src], eax
0x180015b40  xor     edx, edx; Val
0x180015b42  mov     al, byte ptr cs:aNa+4; ""
0x180015b48  mov     r8d, 7FCh; Size
0x180015b4e  mov     byte ptr [rsp+0C50h+Src+4], al
0x180015b52  mov     [rbp+0B50h+var_850], ebx
0x180015b58  call    memset_0
0x180015b5d  test    cs:byte_18004CF34, 1
0x180015b64  jz      short loc_180015BA7
0x180015b66  mov     r8, [rsi+10h]
0x180015b6a  lea     rdx, aLineUpEventOcc; "Line up event occurred on port %d"
0x180015b71  lea     rcx, [rbp+0B50h+var_850]
0x180015b78  mov     word ptr [rbp+0B50h+var_850], bx
0x180015b7f  call    FormatRRASErrorString
0x180015b84  test    cs:byte_18004CF34, 1
0x180015b8b  jz      short loc_180015BA7
0x180015b8d  lea     r8, [rbp+0B50h+var_850]
0x180015b94  lea     rdx, RasPppTraceInfo
0x180015b9b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015ba2  call    McTemplateU0z_EventWriteTransfer
0x180015ba7  mov     rcx, [rsi+10h]
0x180015bab  call    GetPCBPointerFromhPort
0x180015bb0  mov     rdi, rax
0x180015bb3  mov     r15d, 8
0x180015bb9  test    rax, rax
0x180015bbc  jnz     short loc_180015BFA
0x180015bbe  mov     rcx, cs:hHeap; hHeap
0x180015bc5  mov     r8d, 700h; dwBytes
0x180015bcb  mov     edx, r15d; dwFlags
0x180015bce  call    cs:__imp_HeapAlloc
0x180015bd4  mov     rdi, rax
0x180015bd7  test    rax, rax
0x180015bda  jnz     short loc_180015C02
0x180015bdc  call    cs:__imp_GetLastError
0x180015be2  lea     r14, [rsi+20h]
0x180015be6  mov     edx, [r14]
0x180015be9  mov     r8d, eax
0x180015bec  mov     rcx, [rsi+10h]
0x180015bf0  call    NotifyCallerOfFailureOnPort
0x180015bf5  jmp     loc_180016737
0x180015bfa  mov     rcx, rax
0x180015bfd  call    RemovePcbFromTable
0x180015c02  lea     r14, [rsi+20h]
0x180015c06  cmp     [r14], ebx
0x180015c09  jnz     short loc_180015C21
0x180015c0b  test    dword ptr [rsi+9F8h], 8000008h
0x180015c15  jnz     short loc_180015C21
0x180015c17  xor     edx, edx
0x180015c19  mov     r8d, 2D0h
0x180015c1f  jmp     short loc_180015BEC
0x180015c21  mov     rdx, [rsi+10h]
0x180015c25  lea     r8, [rsp+0C50h+var_BF0]
0x180015c2a  mov     rax, qword ptr cs:xmmword_18004C470+8
0x180015c31  xor     ecx, ecx
0x180015c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c38  mov     ebx, eax
0x180015c3a  test    eax, eax
0x180015c3c  jz      short loc_180015C9F
0x180015c3e  cmp     cs:byte_18004CF33, 0
0x180015c45  jge     short loc_180015C89
0x180015c47  xor     ecx, ecx
0x180015c49  lea     rdx, aRasgetinfoFail; "RasGetInfo failed and returned returned"...
0x180015c50  mov     word ptr [rbp+0B50h+var_850], cx
0x180015c57  mov     r8d, eax
0x180015c5a  lea     rcx, [rbp+0B50h+var_850]
0x180015c61  call    FormatRRASErrorString
0x180015c66  cmp     cs:byte_18004CF33, 0
0x180015c6d  jge     short loc_180015C89
0x180015c6f  lea     r8, [rbp+0B50h+var_850]
0x180015c76  lea     rdx, RasPppTraceError
0x180015c7d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015c84  call    McTemplateU0z_EventWriteTransfer
0x180015c89  mov     edx, [r14]
0x180015c8c  mov     r8d, ebx
0x180015c8f  mov     rcx, [rsi+10h]
0x180015c93  call    NotifyCallerOfFailureOnPort
0x180015c98  xor     ebx, ebx
0x180015c9a  jmp     loc_180016737
0x180015c9f  xor     ebx, ebx
0x180015ca1  mov     [rdi+28h], rbx
0x180015ca5  mov     rax, [rsi+10h]
0x180015ca9  mov     [rdi+10h], rax
0x180015cad  mov     rax, [rsi+18h]
0x180015cb1  mov     [rdi+18h], rax
0x180015cb5  mov     [rdi], rbx
0x180015cb8  mov     [rdi+20h], bl
0x180015cbb  mov     ecx, cs:dword_18004CACC
0x180015cc1  mov     [rsp+0C50h+var_C0C], ebx
0x180015cc5  lea     eax, [rcx+1]
0x180015cc8  mov     cs:dword_18004CACC, eax
0x180015cce  mov     [rdi+40h], ecx
0x180015cd1  mov     rcx, [rsi+10h]
0x180015cd5  call    CalculateRestartTimer
0x180015cda  mov     [rdi+24h], eax
0x180015cdd  lea     r13, [rdi+6B0h]
0x180015ce4  mov     [rdi+30h], ebx
0x180015ce7  lea     r8, aNa; "{NA}"
0x180015cee  mov     eax, [r14]
0x180015cf1  neg     eax
0x180015cf3  mov     [rdi+98h], rbx
0x180015cfa  mov     eax, r12d
0x180015cfd  mov     [rdi+0A0h], rbx
0x180015d04  sbb     edx, edx
0x180015d06  mov     [rdi+0A8h], rbx
0x180015d0d  and     edx, 4
0x180015d10  mov     [rdi+0B0h], rbx
0x180015d17  neg     eax
0x180015d19  mov     dword ptr [rdi+74h], 0FFFFFFFFh
0x180015d20  sbb     ecx, ecx
0x180015d22  and     ecx, r15d
0x180015d25  or      edx, ecx
0x180015d27  mov     rcx, r13; pszDest
0x180015d2a  or      [rdi+38h], edx
0x180015d2d  lea     edx, [rbx+28h]; cchDest
0x180015d30  mov     eax, [rbp+0B50h+var_884]
0x180015d36  mov     [rdi+3Ch], eax
0x180015d39  call    StringCchCopyA
0x180015d3e  or      r15, 0FFFFFFFFFFFFFFFFh
0x180015d42  lea     r10, [rsp+0C50h+Src]
0x180015d47  mov     r8, r15
0x180015d4a  inc     r8
0x180015d4d  cmp     [r10+r8], bl
0x180015d51  jnz     short loc_180015D4A
0x180015d53  inc     r8; Size
0x180015d56  lea     rdx, [rsp+0C50h+Src]; Src
0x180015d5b  mov     rcx, r13; void *
0x180015d5e  call    memcpy_0
0x180015d63  lea     rcx, [rdi+5F0h]; lpSystemTimeAsFileTime
0x180015d6a  call    cs:__imp_GetSystemTimeAsFileTime
0x180015d70  cmp     [rdi+8], rbx
0x180015d74  jnz     short loc_180015D8E
0x180015d76  mov     rcx, rdi
0x180015d79  call    AllocateAndInitBcb
0x180015d7e  test    eax, eax
0x180015d80  jnz     loc_180015BE6
0x180015d86  mov     [rsp+0C50h+var_C0C], 1
0x180015d8e  mov     r8, [rdi+8]
0x180015d92  xor     ecx, ecx
0x180015d94  mov     rdx, [rdi+10h]
0x180015d98  add     r8, 28h ; '('
0x180015d9c  mov     rax, qword ptr cs:xmmword_18004C410
0x180015da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015da8  mov     edx, [r14]
0x180015dab  test    eax, eax
0x180015dad  jnz     loc_180015BE9
0x180015db3  mov     rcx, [rdi+8]
0x180015db7  neg     edx
0x180015db9  sbb     eax, eax
0x180015dbb  and     eax, 200h
0x180015dc0  or      [rcx+34h], eax
0x180015dc3  mov     rax, [rdi+8]
0x180015dc7  mov     [rax+0D8h], bl
0x180015dcd  mov     rax, [rdi+8]
0x180015dd1  mov     [rax+1D9h], bl
0x180015dd7  mov     rax, [rdi+8]
0x180015ddb  mov     [rax+3FBh], bl
0x180015de1  test    byte ptr [rdi+38h], 4
0x180015de5  jz      loc_180016137
0x180015deb  mov     rax, [rdi+8]
0x180015def  lea     r8, [rsi+48h]; pszSrc
0x180015df3  mov     dword ptr [rdi+80h], 0FFFFFFFFh
0x180015dfd  mov     dword ptr [rdi+70h], 1
0x180015e04  mov     [rax+40h], r15
0x180015e08  mov     eax, ebx
0x180015e0a  test    r12d, r12d
0x180015e0d  jnz     short loc_180015E12
0x180015e0f  mov     eax, [r8]
0x180015e12  mov     [rdi+34h], eax
0x180015e15  test    r12d, r12d
0x180015e18  jz      short loc_180015E2D
0x180015e1a  lea     rcx, [rdi+600h]; pszDest
0x180015e21  mov     edx, 81h; cbDest
0x180015e26  call    StringCbCopyA
0x180015e2b  jmp     short loc_180015E8E
0x180015e2d  lea     r10, [rdi+681h]
0x180015e34  mov     edx, 11h; cbDest
0x180015e39  mov     rcx, r10; pszDest
0x180015e3c  lea     r8, [rsi+4Ch]; pszSrc
0x180015e40  call    StringCbCopyA
0x180015e45  test    cs:byte_18004CF34, 1
0x180015e4c  jz      short loc_180015E8E
0x180015e4e  mov     r8, r10
0x180015e51  mov     word ptr [rbp+0B50h+var_850], bx
0x180015e58  lea     rdx, aPortnameHs; "PortName: %hs"
0x180015e5f  lea     rcx, [rbp+0B50h+var_850]
0x180015e66  call    FormatRRASErrorString
0x180015e6b  test    cs:byte_18004CF34, 1
0x180015e72  jz      short loc_180015E8E
0x180015e74  lea     r8, [rbp+0B50h+var_850]
0x180015e7b  lea     rdx, RasPppTraceInfo
0x180015e82  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015e89  call    McTemplateU0z_EventWriteTransfer
0x180015e8e  lea     r12, [rdi+0B8h]
0x180015e95  xor     edx, edx; Val
0x180015e97  mov     rcx, r12; void *
0x180015e9a  mov     r8d, 430h; Size
0x180015ea0  call    memset_0
0x180015ea5  xor     eax, eax
0x180015ea7  lea     rcx, dword_18004CAD0
0x180015eae  mov     [rdi+5F8h], rax
0x180015eb5  mov     edx, 8
0x180015eba  mov     rax, [rdi+8]
0x180015ebe  lea     r15d, [rdx+78h]
0x180015ec2  mov     [rax+4FCh], bl
0x180015ec8  mov     rax, r12
0x180015ecb  movups  xmm0, xmmword ptr [rcx]
0x180015ece  movups  xmmword ptr [rax], xmm0
0x180015ed1  movups  xmm1, xmmword ptr [rcx+10h]
0x180015ed5  movups  xmmword ptr [rax+10h], xmm1
0x180015ed9  movups  xmm0, xmmword ptr [rcx+20h]
0x180015edd  movups  xmmword ptr [rax+20h], xmm0
0x180015ee1  movups  xmm1, xmmword ptr [rcx+30h]
0x180015ee5  movups  xmmword ptr [rax+30h], xmm1
0x180015ee9  movups  xmm0, xmmword ptr [rcx+40h]
0x180015eed  movups  xmmword ptr [rax+40h], xmm0
0x180015ef1  movups  xmm1, xmmword ptr [rcx+50h]
0x180015ef5  movups  xmmword ptr [rax+50h], xmm1
0x180015ef9  movups  xmm0, xmmword ptr [rcx+60h]
0x180015efd  movups  xmmword ptr [rax+60h], xmm0
0x180015f01  movups  xmm1, xmmword ptr [rcx+70h]
0x180015f05  add     rcx, r15
0x180015f08  movups  xmmword ptr [rax+70h], xmm1
0x180015f0c  add     rax, r15
0x180015f0f  sub     rdx, 1
0x180015f13  jnz     short loc_180015ECB
0x180015f15  movups  xmm0, xmmword ptr [rcx]
0x180015f18  mov     edx, 81h; uBytes
0x180015f1d  movups  xmmword ptr [rax], xmm0
0x180015f20  movups  xmm1, xmmword ptr [rcx+10h]
0x180015f24  movups  xmmword ptr [rax+10h], xmm1
0x180015f28  movups  xmm0, xmmword ptr [rcx+20h]
0x180015f2c  mov     [rdi+58h], ebx
0x180015f2f  lea     ecx, [rdx-41h]; uFlags
0x180015f32  movups  xmmword ptr [rax+20h], xmm0
0x180015f36  mov     rax, [rdi+8]
0x180015f3a  mov     [rax+1E9h], bl
0x180015f40  mov     rax, [rdi+8]
0x180015f44  mov     [rax+2EAh], bl
0x180015f4a  mov     rax, [rdi+8]
0x180015f4e  mov     [rax+2FAh], bl
0x180015f54  mov     rax, [rdi+8]
0x180015f58  or      dword ptr [rax+34h], 4
0x180015f5c  mov     rbx, [rdi+8]
0x180015f60  call    cs:__imp_LocalAlloc
0x180015f66  mov     [rbx+68h], rax
0x180015f6a  xor     ebx, ebx
0x180015f6c  mov     rax, [rdi+8]
0x180015f70  cmp     [rax+68h], rbx
0x180015f74  jnz     short loc_180015F86
0x180015f76  call    cs:__imp_GetLastError
0x180015f7c  mov     edx, 1
0x180015f81  jmp     loc_180015BE9
0x180015f86  mov     rbx, [rdi+8]
0x180015f8a  mov     edx, 81h; uBytes
0x180015f8f  lea     ecx, [rdx-41h]; uFlags
0x180015f92  call    cs:__imp_LocalAlloc
0x180015f98  mov     [rbx+70h], rax
0x180015f9c  xor     ebx, ebx
0x180015f9e  mov     rax, [rdi+8]
0x180015fa2  cmp     [rax+70h], rbx
0x180015fa6  jz      short loc_180015F76
0x180015fa8  movups  xmm0, xmmword ptr [rsi+668h]
0x180015faf  lea     r8, [rdi+69Ch]
0x180015fb6  mov     rcx, r13; pszDest
0x180015fb9  movdqu  xmmword ptr [r8], xmm0
0x180015fbe  call    PrintGuid
0x180015fc3  test    cs:byte_18004CF34, 1
0x180015fca  jz      short loc_18001600C
0x180015fcc  mov     r8, r13
0x180015fcf  mov     word ptr [rbp+0B50h+var_850], bx
0x180015fd6  lea     rdx, aCorrelationgui; "CorrelationGuidStr: %hs from ddm "
0x180015fdd  lea     rcx, [rbp+0B50h+var_850]
0x180015fe4  call    FormatRRASErrorString
0x180015fe9  test    cs:byte_18004CF34, 1
0x180015ff0  jz      short loc_18001600C
0x180015ff2  lea     r8, [rbp+0B50h+var_850]
  ... truncated ...
```
