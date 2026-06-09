# ProcessLineUpWorker

- ea: `0x180016260`
- end: `0x180017166`
- name: `ProcessLineUpWorker`
- size: `3846`
- prototype: `unsigned int __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x1800152c0`
- `0x180016240`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x1800041d0`
- `0x18000bdd0`
- `0x18000c234`
- `0x18000cdc8`
- `0x18000cf3c`
- `0x18000f780`
- `0x18000fd3c`
- `0x180010114`
- `0x180010d3c`
- `0x18001148c`
- `0x1800115a0`
- `0x180011778`
- `0x180013b54`
- `0x180013b88`
- `0x180013fcc`
- `0x18001411c`
- `0x1800141bc`
- `0x180016260`
- `0x18002b0dc`
- `0x180033a80`
- `0x180034010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x180016cda`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x180016cda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016f96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016f96`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001634e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001634e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016f18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016f2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016f18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016f2b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800166f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016730`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016ba7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016c09`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016c6a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800166f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016730`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016ba7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016c09`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016c6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001670e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001670e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016f05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016f05`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800164f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800164f6`

## string_xrefs

- `0x180016de2`: `Starting PPP on link with IfType=0x%x,IPIf=0x%x,IPv6If=0x%x`

## pseudocode

```c
DWORD __fastcall ProcessLineUpWorker(__int64 a1, int a2)
{
  __int64 v4; // r8
  __int64 PCBPointerFromhPort; // rax
  _DWORD *v6; // rdi
  DWORD LastError; // eax
  _DWORD *v8; // r14
  __int64 v9; // rdx
  __int64 v10; // r8
  DWORD result; // eax
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
  if ( (byte_18004DF34 & 1) != 0 )
  {
    v4 = *(_QWORD *)(a1 + 16);
    LOWORD(v82) = 0;
    FormatRRASErrorString((wchar_t *)&v82, L"Line up event occurred on port %d", v4);
    if ( (byte_18004DF34 & 1) != 0 )
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
  v12 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _BYTE *))&xmmword_18004D470 + 1))(0, *(_QWORD *)(a1 + 16), v79);
  v13 = v12;
  if ( v12 )
  {
    if ( byte_18004DF33 < 0 )
    {
      LOWORD(v82) = 0;
      FormatRRASErrorString((wchar_t *)&v82, L"RasGetInfo failed and returned returned %d", v12);
      if ( byte_18004DF33 < 0 )
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
  v14 = dword_18004DACC;
  v76 = 0;
  ++dword_18004DACC;
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
    LastError = AllocateAndInitBcb((__int64)v6);
    if ( LastError )
      goto LABEL_7;
    v76 = 1;
  }
  LastError = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))xmmword_18004D410)(
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
      if ( (byte_18004DF34 & 1) != 0 )
      {
        LOWORD(v82) = 0;
        FormatRRASErrorString((wchar_t *)&v82, L"PortName: %hs", v20);
        if ( (byte_18004DF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v82);
      }
    }
    memset_0(v6 + 46, 0, 0x430u);
    v21 = &dword_18004DAD0;
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
        if ( (byte_18004DF34 & 1) != 0 )
        {
          LOWORD(v82) = 0;
          FormatRRASErrorString((wchar_t *)&v82, L"CorrelationGuidStr: %hs from ddm ", v6 + 428);
          if ( (byte_18004DF34 & 1) != 0 )
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
          if ( (byte_18004DF34 & 1) != 0 )
          {
            LOWORD(v82) = 0;
            FormatRRASErrorString(
              (wchar_t *)&v82,
              L" BypassAuth for  %hs\\%hs",
              *((_QWORD *)v6 + 1) + 746LL,
              *((_QWORD *)v6 + 1) + 489LL);
            if ( (byte_18004DF34 & 1) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v82);
          }
        }
LABEL_102:
        *((_QWORD *)v6 + 19) = GetUserAttributes((__int64)v6);
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
  v6[23] = dword_18004DA24;
  v6[24] = dword_18004DA28;
  v6[25] = dword_18004DA2C;
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
  if ( (byte_18004DF34 & 1) != 0 )
  {
    LOWORD(v82) = 0;
    FormatRRASErrorString((wchar_t *)&v82, L"PortName: %hs", v42);
    if ( (byte_18004DF34 & 1) != 0 )
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
  if ( (byte_18004DF34 & 1) != 0 )
  {
    LOWORD(v82) = 0;
    FormatRRASErrorString(
      (wchar_t *)&v82,
      L"Starting PPP on link with IfType=0x%x,IPIf=0x%x,IPv6If=0x%x",
      *(unsigned int *)(*((_QWORD *)v6 + 1) + 1320LL),
      *(_QWORD *)(*((_QWORD *)v6 + 1) + 1328LL),
      *(_QWORD *)(*((_QWORD *)v6 + 1) + 1336LL));
    if ( (byte_18004DF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v82);
  }
  v75 = 1500;
  v67 = ((__int64 (__fastcall *)(_DWORD *, int *))xmmword_18004D4B0)(v6 + 10, &v75);
  if ( v67 )
  {
    result = NotifyCallerOfFailure(v6, v67);
  }
  else
  {
    if ( (byte_18004DF34 & 1) != 0 )
    {
      LOWORD(v82) = 0;
      FormatRRASErrorString((wchar_t *)&v82, L"RasGetBuffer returned %x for SendBuf", *((_QWORD *)v6 + 5));
      if ( (byte_18004DF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v82);
    }
    v6[375] = 1;
    if ( (unsigned int)FsmInit((__int64)v6, 0) )
    {
      v69 = ((__int64 (__fastcall *)(_QWORD))xmmword_18004D420)(*((_QWORD *)v6 + 2));
      if ( !v69 )
      {
        v72 = *(_DWORD *)(a1 + 16) % (unsigned int)qword_18004D970;
        if ( (byte_18004DF34 & 1) != 0 )
        {
          LOWORD(v82) = 0;
          FormatRRASErrorString((wchar_t *)&v82, L"Inserting port in bucket # %d", (unsigned int)v72);
          if ( (byte_18004DF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v82);
        }
        v73 = v76 == 0;
        *(_QWORD *)v6 = *((_QWORD *)PcbTable + v72);
        *((_QWORD *)PcbTable + v72) = v6;
        if ( !v73 )
        {
          v74 = *(_DWORD *)(*((_QWORD *)v6 + 1) + 40LL) % (unsigned int)qword_18004D970;
          if ( (byte_18004DF34 & 1) != 0 )
          {
            LOWORD(v82) = 0;
            FormatRRASErrorString((wchar_t *)&v82, L"Inserting bundle in bucket # %d", (unsigned int)v74);
            if ( (byte_18004DF34 & 1) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v82);
          }
          **((_QWORD **)v6 + 1) = *((_QWORD *)*(&PcbTable + 1) + v74);
          *((_QWORD *)*(&PcbTable + 1) + v74) = *((_QWORD *)v6 + 1);
        }
        v6[374] = 721;
        FsmOpen((__int64)v6, 0);
        FsmUp(v6, 0);
        result = dword_18004DA04;
        if ( dword_18004DA04 )
          result = InsertInTimerQ(v6[16], *((_QWORD *)v6 + 2), 0, 0, 0, 3, dword_18004DA04);
        if ( (v6[14] & 4) != 0 && !v78 )
        {
          if ( v6[374] == 721 )
            v6[374] = 0;
          result = 49185;
          if ( (*(unsigned __int8 *)(a1 + 105) << 8) + *(unsigned __int8 *)(a1 + 106) == 0xC021 )
            return ReceiveViaParser(
                     (__int64)v6,
                     (unsigned __int8 *)(a1 + 105),
                     (unsigned int)(*(_DWORD *)(a1 + 1596) - 12));
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
    DeallocateAndRemoveBcbFromTable(*((char **)v6 + 1));
    if ( *((_QWORD *)v6 + 5) )
      ((void (*)(void))xmmword_18004D460)();
    return HeapFree(hHeap, 0, v6);
  }
  return result;
}

```

## disassembly

```asm
0x180016260  push    rbp
0x180016262  push    rbx
0x180016263  push    rsi
0x180016264  push    rdi
0x180016265  push    r12
0x180016267  push    r13
0x180016269  push    r14
0x18001626b  push    r15
0x18001626d  lea     rbp, [rsp-0B18h]
0x180016275  sub     rsp, 0C18h
0x18001627c  mov     rax, cs:__security_cookie
0x180016283  xor     rax, rsp
0x180016286  mov     [rbp+0B50h+var_50], rax
0x18001628d  mov     r12d, edx
0x180016290  mov     [rsp+0C50h+var_C00], edx
0x180016294  mov     rsi, rcx
0x180016297  xor     ebx, ebx
0x180016299  xor     edx, edx; Val
0x18001629b  mov     [rsp+0C50h+var_C10], ebx
0x18001629f  lea     rcx, [rsp+0C50h+var_BF0]; void *
0x1800162a4  mov     r8d, 398h; Size
0x1800162aa  call    memset_0
0x1800162af  mov     eax, dword ptr cs:aNa; "{NA}"
0x1800162b5  lea     rcx, [rbp+0B50h+var_84C]; void *
0x1800162bc  mov     dword ptr [rsp+0C50h+Src], eax
0x1800162c0  xor     edx, edx; Val
0x1800162c2  mov     al, byte ptr cs:aNa+4; ""
0x1800162c8  mov     r8d, 7FCh; Size
0x1800162ce  mov     byte ptr [rsp+0C50h+Src+4], al
0x1800162d2  mov     [rbp+0B50h+var_850], ebx
0x1800162d8  call    memset_0
0x1800162dd  test    cs:byte_18004DF34, 1
0x1800162e4  jz      short loc_180016327
0x1800162e6  mov     r8, [rsi+10h]
0x1800162ea  lea     rdx, aLineUpEventOcc; "Line up event occurred on port %d"
0x1800162f1  lea     rcx, [rbp+0B50h+var_850]
0x1800162f8  mov     word ptr [rbp+0B50h+var_850], bx
0x1800162ff  call    FormatRRASErrorString
0x180016304  test    cs:byte_18004DF34, 1
0x18001630b  jz      short loc_180016327
0x18001630d  lea     r8, [rbp+0B50h+var_850]
0x180016314  lea     rdx, RasPppTraceInfo
0x18001631b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016322  call    McTemplateU0z_EventWriteTransfer
0x180016327  mov     rcx, [rsi+10h]
0x18001632b  call    GetPCBPointerFromhPort
0x180016330  mov     rdi, rax
0x180016333  mov     r15d, 8
0x180016339  test    rax, rax
0x18001633c  jnz     short loc_180016386
0x18001633e  mov     rcx, cs:hHeap; hHeap
0x180016345  mov     r8d, 700h; dwBytes
0x18001634b  mov     edx, r15d; dwFlags
0x18001634e  call    cs:__imp_HeapAlloc
0x180016355  nop     dword ptr [rax+rax+00h]
0x18001635a  mov     rdi, rax
0x18001635d  test    rax, rax
0x180016360  jnz     short loc_18001638E
0x180016362  call    cs:__imp_GetLastError
0x180016369  nop     dword ptr [rax+rax+00h]
0x18001636e  lea     r14, [rsi+20h]
0x180016372  mov     edx, [r14]
0x180016375  mov     r8d, eax
0x180016378  mov     rcx, [rsi+10h]
0x18001637c  call    NotifyCallerOfFailureOnPort
0x180016381  jmp     loc_180016EF3
0x180016386  mov     rcx, rax
0x180016389  call    RemovePcbFromTable
0x18001638e  lea     r14, [rsi+20h]
0x180016392  cmp     [r14], ebx
0x180016395  jnz     short loc_1800163AD
0x180016397  test    dword ptr [rsi+9F8h], 8000008h
0x1800163a1  jnz     short loc_1800163AD
0x1800163a3  xor     edx, edx
0x1800163a5  mov     r8d, 2D0h
0x1800163ab  jmp     short loc_180016378
0x1800163ad  mov     rdx, [rsi+10h]
0x1800163b1  lea     r8, [rsp+0C50h+var_BF0]
0x1800163b6  mov     rax, qword ptr cs:xmmword_18004D470+8
0x1800163bd  xor     ecx, ecx
0x1800163bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163c4  mov     ebx, eax
0x1800163c6  test    eax, eax
0x1800163c8  jz      short loc_18001642B
0x1800163ca  cmp     cs:byte_18004DF33, 0
0x1800163d1  jge     short loc_180016415
0x1800163d3  xor     ecx, ecx
0x1800163d5  lea     rdx, aRasgetinfoFail; "RasGetInfo failed and returned returned"...
0x1800163dc  mov     word ptr [rbp+0B50h+var_850], cx
0x1800163e3  mov     r8d, eax
0x1800163e6  lea     rcx, [rbp+0B50h+var_850]
0x1800163ed  call    FormatRRASErrorString
0x1800163f2  cmp     cs:byte_18004DF33, 0
0x1800163f9  jge     short loc_180016415
0x1800163fb  lea     r8, [rbp+0B50h+var_850]
0x180016402  lea     rdx, RasPppTraceError
0x180016409  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016410  call    McTemplateU0z_EventWriteTransfer
0x180016415  mov     edx, [r14]
0x180016418  mov     r8d, ebx
0x18001641b  mov     rcx, [rsi+10h]
0x18001641f  call    NotifyCallerOfFailureOnPort
0x180016424  xor     ebx, ebx
0x180016426  jmp     loc_180016EF3
0x18001642b  xor     ebx, ebx
0x18001642d  mov     [rdi+28h], rbx
0x180016431  mov     rax, [rsi+10h]
0x180016435  mov     [rdi+10h], rax
0x180016439  mov     rax, [rsi+18h]
0x18001643d  mov     [rdi+18h], rax
0x180016441  mov     [rdi], rbx
0x180016444  mov     [rdi+20h], bl
0x180016447  mov     ecx, cs:dword_18004DACC
0x18001644d  mov     [rsp+0C50h+var_C0C], ebx
0x180016451  lea     eax, [rcx+1]
0x180016454  mov     cs:dword_18004DACC, eax
0x18001645a  mov     [rdi+40h], ecx
0x18001645d  mov     rcx, [rsi+10h]
0x180016461  call    CalculateRestartTimer
0x180016466  mov     [rdi+24h], eax
0x180016469  lea     r13, [rdi+6B0h]
0x180016470  mov     [rdi+30h], ebx
0x180016473  lea     r8, aNa; "{NA}"
0x18001647a  mov     eax, [r14]
0x18001647d  neg     eax
0x18001647f  mov     [rdi+98h], rbx
0x180016486  mov     eax, r12d
0x180016489  mov     [rdi+0A0h], rbx
0x180016490  sbb     edx, edx
0x180016492  mov     [rdi+0A8h], rbx
0x180016499  and     edx, 4
0x18001649c  mov     [rdi+0B0h], rbx
0x1800164a3  neg     eax
0x1800164a5  mov     dword ptr [rdi+74h], 0FFFFFFFFh
0x1800164ac  sbb     ecx, ecx
0x1800164ae  and     ecx, r15d
0x1800164b1  or      edx, ecx
0x1800164b3  mov     rcx, r13; pszDest
0x1800164b6  or      [rdi+38h], edx
0x1800164b9  lea     edx, [rbx+28h]; cchDest
0x1800164bc  mov     eax, [rbp+0B50h+var_884]
0x1800164c2  mov     [rdi+3Ch], eax
0x1800164c5  call    StringCchCopyA
0x1800164ca  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800164ce  lea     r10, [rsp+0C50h+Src]
0x1800164d3  mov     r8, r15
0x1800164d6  inc     r8
0x1800164d9  cmp     [r10+r8], bl
0x1800164dd  jnz     short loc_1800164D6
0x1800164df  inc     r8; Size
0x1800164e2  lea     rdx, [rsp+0C50h+Src]; Src
0x1800164e7  mov     rcx, r13; void *
0x1800164ea  call    memcpy_0
0x1800164ef  lea     rcx, [rdi+5F0h]; lpSystemTimeAsFileTime
0x1800164f6  call    cs:__imp_GetSystemTimeAsFileTime
0x1800164fd  nop     dword ptr [rax+rax+00h]
0x180016502  cmp     [rdi+8], rbx
0x180016506  jnz     short loc_180016520
0x180016508  mov     rcx, rdi
0x18001650b  call    AllocateAndInitBcb
0x180016510  test    eax, eax
0x180016512  jnz     loc_180016372
0x180016518  mov     [rsp+0C50h+var_C0C], 1
0x180016520  mov     r8, [rdi+8]
0x180016524  xor     ecx, ecx
0x180016526  mov     rdx, [rdi+10h]
0x18001652a  add     r8, 28h ; '('
0x18001652e  mov     rax, qword ptr cs:xmmword_18004D410
0x180016535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001653a  mov     edx, [r14]
0x18001653d  test    eax, eax
0x18001653f  jnz     loc_180016375
0x180016545  mov     rcx, [rdi+8]
0x180016549  neg     edx
0x18001654b  sbb     eax, eax
0x18001654d  and     eax, 200h
0x180016552  or      [rcx+34h], eax
0x180016555  mov     rax, [rdi+8]
0x180016559  mov     [rax+0D8h], bl
0x18001655f  mov     rax, [rdi+8]
0x180016563  mov     [rax+1D9h], bl
0x180016569  mov     rax, [rdi+8]
0x18001656d  mov     [rax+3FBh], bl
0x180016573  test    byte ptr [rdi+38h], 4
0x180016577  jz      loc_1800168DB
0x18001657d  mov     rax, [rdi+8]
0x180016581  lea     r8, [rsi+48h]; pszSrc
0x180016585  mov     dword ptr [rdi+80h], 0FFFFFFFFh
0x18001658f  mov     dword ptr [rdi+70h], 1
0x180016596  mov     [rax+40h], r15
0x18001659a  mov     eax, ebx
0x18001659c  test    r12d, r12d
0x18001659f  jnz     short loc_1800165A4
0x1800165a1  mov     eax, [r8]
0x1800165a4  mov     [rdi+34h], eax
0x1800165a7  test    r12d, r12d
0x1800165aa  jz      short loc_1800165BF
0x1800165ac  lea     rcx, [rdi+600h]; pszDest
0x1800165b3  mov     edx, 81h; cbDest
0x1800165b8  call    StringCbCopyA
0x1800165bd  jmp     short loc_180016620
0x1800165bf  lea     r10, [rdi+681h]
0x1800165c6  mov     edx, 11h; cbDest
0x1800165cb  mov     rcx, r10; pszDest
0x1800165ce  lea     r8, [rsi+4Ch]; pszSrc
0x1800165d2  call    StringCbCopyA
0x1800165d7  test    cs:byte_18004DF34, 1
0x1800165de  jz      short loc_180016620
0x1800165e0  mov     r8, r10
0x1800165e3  mov     word ptr [rbp+0B50h+var_850], bx
0x1800165ea  lea     rdx, aPortnameHs; "PortName: %hs"
0x1800165f1  lea     rcx, [rbp+0B50h+var_850]
0x1800165f8  call    FormatRRASErrorString
0x1800165fd  test    cs:byte_18004DF34, 1
0x180016604  jz      short loc_180016620
0x180016606  lea     r8, [rbp+0B50h+var_850]
0x18001660d  lea     rdx, RasPppTraceInfo
0x180016614  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001661b  call    McTemplateU0z_EventWriteTransfer
0x180016620  lea     r12, [rdi+0B8h]
0x180016627  xor     edx, edx; Val
0x180016629  mov     rcx, r12; void *
0x18001662c  mov     r8d, 430h; Size
0x180016632  call    memset_0
0x180016637  xor     eax, eax
0x180016639  lea     rcx, dword_18004DAD0
0x180016640  mov     [rdi+5F8h], rax
0x180016647  mov     edx, 8
0x18001664c  mov     rax, [rdi+8]
0x180016650  lea     r15d, [rdx+78h]
0x180016654  mov     [rax+4FCh], bl
0x18001665a  mov     rax, r12
0x18001665d  movups  xmm0, xmmword ptr [rcx]
0x180016660  movups  xmmword ptr [rax], xmm0
0x180016663  movups  xmm1, xmmword ptr [rcx+10h]
0x180016667  movups  xmmword ptr [rax+10h], xmm1
0x18001666b  movups  xmm0, xmmword ptr [rcx+20h]
0x18001666f  movups  xmmword ptr [rax+20h], xmm0
0x180016673  movups  xmm1, xmmword ptr [rcx+30h]
0x180016677  movups  xmmword ptr [rax+30h], xmm1
0x18001667b  movups  xmm0, xmmword ptr [rcx+40h]
0x18001667f  movups  xmmword ptr [rax+40h], xmm0
0x180016683  movups  xmm1, xmmword ptr [rcx+50h]
0x180016687  movups  xmmword ptr [rax+50h], xmm1
0x18001668b  movups  xmm0, xmmword ptr [rcx+60h]
0x18001668f  movups  xmmword ptr [rax+60h], xmm0
0x180016693  movups  xmm1, xmmword ptr [rcx+70h]
0x180016697  add     rcx, r15
0x18001669a  movups  xmmword ptr [rax+70h], xmm1
0x18001669e  add     rax, r15
0x1800166a1  sub     rdx, 1
0x1800166a5  jnz     short loc_18001665D
0x1800166a7  movups  xmm0, xmmword ptr [rcx]
0x1800166aa  mov     edx, 81h; uBytes
0x1800166af  movups  xmmword ptr [rax], xmm0
0x1800166b2  movups  xmm1, xmmword ptr [rcx+10h]
0x1800166b6  movups  xmmword ptr [rax+10h], xmm1
0x1800166ba  movups  xmm0, xmmword ptr [rcx+20h]
0x1800166be  mov     [rdi+58h], ebx
0x1800166c1  lea     ecx, [rdx-41h]; uFlags
0x1800166c4  movups  xmmword ptr [rax+20h], xmm0
0x1800166c8  mov     rax, [rdi+8]
0x1800166cc  mov     [rax+1E9h], bl
0x1800166d2  mov     rax, [rdi+8]
0x1800166d6  mov     [rax+2EAh], bl
0x1800166dc  mov     rax, [rdi+8]
0x1800166e0  mov     [rax+2FAh], bl
0x1800166e6  mov     rax, [rdi+8]
0x1800166ea  or      dword ptr [rax+34h], 4
0x1800166ee  mov     rbx, [rdi+8]
0x1800166f2  call    cs:__imp_LocalAlloc
0x1800166f9  nop     dword ptr [rax+rax+00h]
0x1800166fe  mov     [rbx+68h], rax
0x180016702  xor     ebx, ebx
0x180016704  mov     rax, [rdi+8]
0x180016708  cmp     [rax+68h], rbx
0x18001670c  jnz     short loc_180016724
0x18001670e  call    cs:__imp_GetLastError
0x180016715  nop     dword ptr [rax+rax+00h]
0x18001671a  mov     edx, 1
0x18001671f  jmp     loc_180016375
0x180016724  mov     rbx, [rdi+8]
0x180016728  mov     edx, 81h; uBytes
0x18001672d  lea     ecx, [rdx-41h]; uFlags
0x180016730  call    cs:__imp_LocalAlloc
0x180016737  nop     dword ptr [rax+rax+00h]
0x18001673c  mov     [rbx+70h], rax
0x180016740  xor     ebx, ebx
0x180016742  mov     rax, [rdi+8]
0x180016746  cmp     [rax+70h], rbx
0x18001674a  jz      short loc_18001670E
0x18001674c  movups  xmm0, xmmword ptr [rsi+668h]
0x180016753  lea     r8, [rdi+69Ch]
0x18001675a  mov     rcx, r13; pszDest
0x18001675d  movdqu  xmmword ptr [r8], xmm0
0x180016762  call    PrintGuid
0x180016767  test    cs:byte_18004DF34, 1
0x18001676e  jz      short loc_1800167B0
0x180016770  mov     r8, r13
0x180016773  mov     word ptr [rbp+0B50h+var_850], bx
  ... truncated ...
```
