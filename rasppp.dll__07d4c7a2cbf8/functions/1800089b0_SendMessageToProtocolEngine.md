# SendMessageToProtocolEngine

- ea: `0x1800089b0`
- end: `0x180009321`
- name: `SendMessageToProtocolEngine`
- size: `2417`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008910`
- `0x1800141b0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x1800089b0`
- `0x180011e70`
- `0x1800122bc`
- `0x18001873c`
- `0x18002a138`
- `0x180032460`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008ba6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009167`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008ba6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009167`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800089f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008b84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800089f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008b84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bac`

## string_xrefs

- `0x180008fc1`: `PROTOCOL_MSG_Start recvd, d=%hs, hPort=%d,flags=%d,mask=%x,IfType=%d`
- `0x18000904a`: `PROTOCOL_MSG_Start: Encode password failed`
- `0x180008f4d`: `PROTOCOL_MSG_Stop recvd`
- `0x180008ea3`: `PROTOCOL_MSG_Callback recvd, hPort=%d`
- `0x180008d3d`: `PROTOCOL_MSG_ChangePw recvd, hPort=%d`
- `0x180008be6`: `PROTOCOL_MSG_Retry recvd hPort=%d,u=%hs`
- `0x180008ad7`: `PROTOCOL_MSG_LineDown recvd, hPort=%d`
- `0x1800090a6`: `PROTOCOL_MSG_DdmCallbackDone recvd`
- `0x1800092fc`: `PROTOCOL_MSG_DdmInterfaceInfo recvd,IPif=%x,IPv6=%x,Type=%x`

## pseudocode

```c
DWORD __fastcall SendMessageToProtocolEngine(__int64 a1)
{
  __int64 v2; // rsi
  char *v3; // rbx
  DWORD LastError; // ebx
  __int64 v5; // rcx
  int v7; // r8d
  void *v8; // rcx
  const void *v9; // rdx
  size_t v10; // r8
  int (__fastcall *v11)(__int64); // rax
  LPVOID v12; // rax
  __int64 v13; // rcx
  __int128 *v14; // rcx
  __int128 *v15; // rax
  __int128 v16; // xmm0
  __int64 v17; // rsi
  _BYTE *v18; // r14
  __int128 v19; // xmm1
  __int64 v20; // rcx
  const wchar_t *v21; // r8
  __int64 *v22; // rdx
  __int64 v23; // rax
  _BYTE *v24; // rdi
  __int64 v25; // rsi
  _BYTE *v26; // r15
  __int64 v27; // rcx
  _BYTE *v28; // r14
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rax
  _BYTE *v32; // rcx
  __int64 v33; // rax
  _BYTE *v34; // rdi
  __int64 (__fastcall *v35)(); // rax
  int v36; // eax
  __int64 v37; // rsi
  _BYTE *v38; // r14
  __int64 v39; // rcx
  __int64 v40; // rax
  _BYTE *v41; // rdi
  __int64 v42; // r8
  __int64 (__fastcall *v43)(); // rax
  int v44; // [rsp+28h] [rbp-D8h]
  int v45; // [rsp+30h] [rbp-D0h]
  int v46; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v47[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v2 = 8;
  v46 = 0;
  v3 = (char *)HeapAlloc(hHeap, 8u, 0x1C10u);
  memset_0(v47, 0, sizeof(v47));
  if ( !v3 )
  {
    LastError = GetLastError();
    LogPPPEvent(v5, 0);
    return LastError;
  }
  *((_QWORD *)v3 + 2) = *(_QWORD *)(a1 + 8);
  v7 = *(_DWORD *)a1;
  if ( *(int *)a1 > 9 )
  {
    if ( v7 != 10 )
    {
      switch ( v7 )
      {
        case 11:
          *((_QWORD *)v3 + 1) = ProcessDhcpInform;
          *((_QWORD *)v3 + 3) = *(_QWORD *)(a1 + 16);
          *(_OWORD *)(v3 + 72) = *(_OWORD *)(a1 + 24);
          *(_OWORD *)(v3 + 88) = *(_OWORD *)(a1 + 40);
          *(_OWORD *)(v3 + 104) = *(_OWORD *)(a1 + 56);
          *(_OWORD *)(v3 + 120) = *(_OWORD *)(a1 + 72);
          *((_QWORD *)v3 + 17) = *(_QWORD *)(a1 + 88);
          goto LABEL_121;
        case 12:
          *((_QWORD *)v3 + 1) = ProcessEapUIData;
          *(_OWORD *)(v3 + 72) = *(_OWORD *)(a1 + 24);
          *((_QWORD *)v3 + 11) = *(_QWORD *)(a1 + 40);
          goto LABEL_121;
        case 13:
          _InterlockedIncrement((volatile signed __int32 *)&g_DdmMsgHandler);
          *((_QWORD *)v3 + 1) = ProcessChangeNotification;
          dword_18004CA20 = *(_DWORD *)(a1 + 28);
          dword_18004CAD0 = *(_DWORD *)(a1 + 24);
          goto LABEL_121;
        case 14:
          v43 = ProcessProtocolEvent;
          break;
        case 15:
          v43 = ProcessPostLineDown;
          break;
        case 16:
          *((_QWORD *)v3 + 1) = ProcessRemoveQuarantine;
          *((_QWORD *)v3 + 3) = *(_QWORD *)(a1 + 16);
          goto LABEL_121;
        case 17:
          *((_QWORD *)v3 + 1) = ProcessRenegotiation;
          if ( (byte_18004CF34 & 1) == 0 )
            goto LABEL_121;
          v42 = *(_QWORD *)(a1 + 8);
          LOWORD(v46) = 0;
          FormatRRASErrorString(&v46, L"Starting PPP renegotiation on port %d", v42);
          goto LABEL_118;
        default:
          goto LABEL_112;
      }
      *((_QWORD *)v3 + 1) = v43;
      *((_QWORD *)v3 + 9) = *(_QWORD *)(a1 + 24);
      goto LABEL_121;
    }
    *((_DWORD *)v3 + 8) = 1;
    *((_QWORD *)v3 + 1) = ProcessInterfaceInfo;
    *((_QWORD *)v3 + 3) = *(_QWORD *)(a1 + 16);
    memcpy_0(v3 + 72, (const void *)(a1 + 24), 0xAE8u);
    if ( (byte_18004CF34 & 1) == 0 )
      goto LABEL_121;
    LOWORD(v46) = 0;
    FormatRRASErrorString(
      &v46,
      L"PROTOCOL_MSG_DdmInterfaceInfo recvd,IPif=%x,IPv6=%x,Type=%x",
      *((_QWORD *)v3 + 10),
      *((_QWORD *)v3 + 11),
      *((_DWORD *)v3 + 18));
LABEL_118:
    if ( (byte_18004CF34 & 1) == 0 )
      goto LABEL_121;
    v21 = (const wchar_t *)&v46;
    v22 = RasPppTraceInfo;
LABEL_120:
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v22, v21);
    goto LABEL_121;
  }
  switch ( v7 )
  {
    case 9:
      if ( (byte_18004CF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasPppTraceInfo,
          L"PROTOCOL_MSG_DdmCallbackDone recvd");
      v35 = ProcessCallbackDone;
      *((_DWORD *)v3 + 8) = 1;
      goto LABEL_80;
    case 0:
      *((_DWORD *)v3 + 8) = 0;
      *((_QWORD *)v3 + 1) = ProcessLineUp;
      *((_QWORD *)v3 + 3) = *(_QWORD *)(a1 + 16);
      memcpy_0(v3 + 72, (const void *)(a1 + 24), 0x1BC8u);
      if ( (byte_18004CF34 & 1) != 0 )
      {
        v45 = *(_DWORD *)(a1 + 4104);
        v44 = *(_DWORD *)(a1 + 2504);
        v36 = *(_DWORD *)(a1 + 2516);
        LOWORD(v46) = 0;
        FormatRRASErrorString(
          &v46,
          L"PROTOCOL_MSG_Start recvd, d=%hs, hPort=%d,flags=%d,mask=%x,IfType=%d",
          a1 + 2480,
          *((_QWORD *)v3 + 2),
          v36,
          v44,
          v45);
        if ( (byte_18004CF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v46);
      }
      v37 = -1;
      v38 = v3 + 2271;
      v39 = -1;
      do
        ++v39;
      while ( v38[v39] );
      if ( !(unsigned int)EncodePassword((unsigned int)(v39 + 1), v3 + 2271, v3 + 6976) )
      {
        v40 = -1;
        do
          ++v40;
        while ( v38[v40] );
        for ( ; v40; --v40 )
          *v38++ = 0;
        v41 = (_BYTE *)(a1 + 2223);
        do
          ++v37;
        while ( v41[v37] );
        for ( ; v37; --v37 )
          *v41++ = 0;
        goto LABEL_121;
      }
      if ( byte_18004CF33 >= 0 )
      {
LABEL_121:
        InsertWorkItemInQ(v3);
        return 0;
      }
      v21 = L"PROTOCOL_MSG_Start: Encode password failed";
      goto LABEL_38;
    case 1:
      if ( (byte_18004CF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasPppTraceInfo,
          L"PROTOCOL_MSG_Stop recvd");
      *((_QWORD *)v3 + 1) = ProcessClose;
      *((_DWORD *)v3 + 18) = *(_DWORD *)(a1 + 24);
      goto LABEL_121;
    case 2:
      if ( (byte_18004CF34 & 1) != 0 )
      {
        LOWORD(v46) = 0;
        FormatRRASErrorString(&v46, L"PROTOCOL_MSG_Callback recvd, hPort=%d", *((_QWORD *)v3 + 2));
        if ( (byte_18004CF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v46);
      }
      v35 = ProcessGetCallbackNumberFromUser;
LABEL_80:
      *((_QWORD *)v3 + 1) = v35;
      *(_OWORD *)(v3 + 72) = *(_OWORD *)(a1 + 24);
      *(_OWORD *)(v3 + 88) = *(_OWORD *)(a1 + 40);
      *(_OWORD *)(v3 + 104) = *(_OWORD *)(a1 + 56);
      *(_OWORD *)(v3 + 120) = *(_OWORD *)(a1 + 72);
      *(_OWORD *)(v3 + 136) = *(_OWORD *)(a1 + 88);
      *(_OWORD *)(v3 + 152) = *(_OWORD *)(a1 + 104);
      *(_OWORD *)(v3 + 168) = *(_OWORD *)(a1 + 120);
      *(_OWORD *)(v3 + 184) = *(_OWORD *)(a1 + 136);
      v3[200] = *(_BYTE *)(a1 + 152);
      goto LABEL_121;
    case 3:
      if ( (byte_18004CF34 & 1) != 0 )
      {
        LOWORD(v46) = 0;
        FormatRRASErrorString(&v46, L"PROTOCOL_MSG_ChangePw recvd, hPort=%d", *((_QWORD *)v3 + 2));
        if ( (byte_18004CF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v46);
      }
      *((_QWORD *)v3 + 1) = ProcessChangePassword;
      memcpy_0(v3 + 72, (const void *)(a1 + 24), 0x628u);
      v25 = -1;
      v26 = v3 + 1100;
      v27 = -1;
      do
        ++v27;
      while ( v26[v27] );
      if ( !(unsigned int)EncodePassword((unsigned int)(v27 + 1), v3 + 1100, v3 + 1616) )
      {
        v28 = v3 + 586;
        v29 = -1;
        do
          ++v29;
        while ( v28[v29] );
        if ( (unsigned int)EncodePassword((unsigned int)(v29 + 1), v3 + 586, v3 + 1632) && byte_18004CF33 < 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            RasPppTraceError,
            L"EncodePassword failed");
        v30 = -1;
        do
          ++v30;
        while ( v28[v30] );
        for ( ; v30; --v30 )
          *v28++ = 0;
        v31 = -1;
        do
          ++v31;
        while ( v26[v31] );
        for ( ; v31; --v31 )
          *v26++ = 0;
        v32 = (_BYTE *)(a1 + 538);
        v33 = -1;
        do
          ++v33;
        while ( v32[v33] );
        for ( ; v33; --v33 )
          *v32++ = 0;
        v34 = (_BYTE *)(a1 + 1052);
        do
          ++v25;
        while ( v34[v25] );
        for ( ; v25; --v25 )
          *v34++ = 0;
        goto LABEL_121;
      }
LABEL_36:
      if ( byte_18004CF33 >= 0 )
        goto LABEL_121;
      v21 = L"EncodePassword failed";
LABEL_38:
      v22 = RasPppTraceError;
      goto LABEL_120;
    case 4:
      if ( (byte_18004CF34 & 1) != 0 )
      {
        LOWORD(v46) = 0;
        FormatRRASErrorString(&v46, L"PROTOCOL_MSG_Retry recvd hPort=%d,u=%hs", *((_QWORD *)v3 + 2), a1 + 1966);
        if ( (byte_18004CF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v46);
      }
      *((_QWORD *)v3 + 1) = ProcessRetryPassword;
      v14 = (__int128 *)(a1 + 24);
      v15 = (__int128 *)(v3 + 72);
      do
      {
        v16 = *v14;
        v14 += 8;
        *v15 = v16;
        v15 += 8;
        *(v15 - 7) = *(v14 - 7);
        *(v15 - 6) = *(v14 - 6);
        *(v15 - 5) = *(v14 - 5);
        *(v15 - 4) = *(v14 - 4);
        *(v15 - 3) = *(v14 - 3);
        *(v15 - 2) = *(v14 - 2);
        *(v15 - 1) = *(v14 - 1);
        --v2;
      }
      while ( v2 );
      v17 = -1;
      v18 = v3 + 586;
      *v15 = *v14;
      v15[1] = v14[1];
      v15[2] = v14[2];
      v19 = v14[3];
      v20 = -1;
      v15[3] = v19;
      do
        ++v20;
      while ( v18[v20] );
      if ( !(unsigned int)EncodePassword((unsigned int)(v20 + 1), v3 + 586, v3 + 1144) )
      {
        v23 = -1;
        do
          ++v23;
        while ( v18[v23] );
        for ( ; v23; --v23 )
          *v18++ = 0;
        v24 = (_BYTE *)(a1 + 538);
        do
          ++v17;
        while ( v24[v17] );
        for ( ; v17; --v17 )
          *v24++ = 0;
        goto LABEL_121;
      }
      goto LABEL_36;
    case 5:
      *((_QWORD *)v3 + 1) = ProcessReceive;
      *((_DWORD *)v3 + 12) = *(_DWORD *)(a1 + 24);
      if ( (byte_18004CF34 & 1) != 0 )
      {
        LOWORD(v46) = 0;
        FormatRRASErrorString(
          &v46,
          L"Packet received (%d bytes) for hPort %d",
          *((unsigned int *)v3 + 12),
          *((_QWORD *)v3 + 2));
        if ( (byte_18004CF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v46);
      }
      v12 = HeapAlloc(hHeap, 8u, *((unsigned int *)v3 + 12));
      *((_QWORD *)v3 + 5) = v12;
      if ( !v12 )
      {
        LogPPPEvent(v13, 0);
        HeapFree(hHeap, 0, v3);
        return GetLastError();
      }
      v10 = *((unsigned int *)v3 + 12);
      v8 = v12;
      v9 = *(const void **)(a1 + 32);
      goto LABEL_27;
    case 6:
      if ( (byte_18004CF34 & 1) != 0 )
      {
        LOWORD(v46) = 0;
        FormatRRASErrorString(&v46, L"PROTOCOL_MSG_LineDown recvd, hPort=%d", *((_QWORD *)v3 + 2));
        if ( (byte_18004CF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v46);
      }
      v11 = (int (__fastcall *)(__int64))ProcessLineDown;
      goto LABEL_20;
    case 7:
      v11 = ProcessRasPortListenEvent;
LABEL_20:
      *((_QWORD *)v3 + 1) = v11;
      goto LABEL_121;
    case 8:
      *((_DWORD *)v3 + 8) = 1;
      *((_QWORD *)v3 + 1) = ProcessLineUp;
      v8 = v3 + 72;
      v9 = (const void *)(a1 + 24);
      v10 = 1864;
LABEL_27:
      memcpy_0(v8, v9, v10);
      goto LABEL_121;
  }
LABEL_112:
  if ( (byte_18004CF34 & 1) != 0 )
  {
    LOWORD(v46) = 0;
    FormatRRASErrorString(&v46, L"Unknown IPC message %d received");
    if ( (byte_18004CF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v46);
  }
  HeapFree(hHeap, 0, v3);
  return 87;
}

```

## disassembly

```asm
0x1800089b0  mov     [rsp-8+arg_8], rbx
0x1800089b5  mov     [rsp-8+arg_10], rsi
0x1800089ba  push    rbp
0x1800089bb  push    rdi
0x1800089bc  push    r12
0x1800089be  push    r14
0x1800089c0  push    r15
0x1800089c2  lea     rbp, [rsp-760h]
0x1800089ca  sub     rsp, 860h
0x1800089d1  mov     rax, cs:__security_cookie
0x1800089d8  xor     rax, rsp
0x1800089db  mov     [rbp+780h+var_30], rax
0x1800089e2  mov     rdi, rcx
0x1800089e5  mov     esi, 8
0x1800089ea  mov     rcx, cs:hHeap; hHeap
0x1800089f1  mov     edx, esi; dwFlags
0x1800089f3  mov     r8d, 1C10h; dwBytes
0x1800089f9  call    cs:__imp_HeapAlloc
0x1800089ff  xor     r12d, r12d
0x180008a02  lea     rcx, [rsp+880h+var_82C]; void *
0x180008a07  xor     edx, edx; Val
0x180008a09  mov     [rsp+880h+var_830], r12d
0x180008a0e  mov     r8d, 7FCh; Size
0x180008a14  mov     rbx, rax
0x180008a17  call    memset_0
0x180008a1c  test    rbx, rbx
0x180008a1f  jnz     short loc_180008A37
0x180008a21  call    cs:__imp_GetLastError
0x180008a27  xor     edx, edx
0x180008a29  mov     ebx, eax
0x180008a2b  call    LogPPPEvent
0x180008a30  mov     eax, ebx
0x180008a32  jmp     loc_1800091CE
0x180008a37  mov     rax, [rdi+8]
0x180008a3b  mov     [rbx+10h], rax
0x180008a3f  mov     r8d, [rdi]
0x180008a42  cmp     r8d, 9
0x180008a46  jg      loc_1800090D3
0x180008a4c  jz      loc_18000909D
0x180008a52  mov     ecx, r8d
0x180008a55  test    r8d, r8d
0x180008a58  jz      loc_180008F7D
0x180008a5e  sub     ecx, 1
0x180008a61  jz      loc_180008F44
0x180008a67  sub     ecx, 1
0x180008a6a  jz      loc_180008E94
0x180008a70  sub     ecx, 1
0x180008a73  jz      loc_180008D2E
0x180008a79  sub     ecx, 1
0x180008a7c  jz      loc_180008BCC
0x180008a82  sub     ecx, 1
0x180008a85  jz      loc_180008B1D
0x180008a8b  sub     ecx, 1
0x180008a8e  jz      short loc_180008AC8
0x180008a90  sub     ecx, 1
0x180008a93  jz      short loc_180008ABF
0x180008a95  cmp     ecx, 1
0x180008a98  jnz     loc_18000911A
0x180008a9e  lea     rax, ProcessLineUp
0x180008aa5  mov     [rbx+20h], ecx
0x180008aa8  mov     [rbx+8], rax
0x180008aac  lea     rcx, [rbx+48h]
0x180008ab0  lea     rdx, [rdi+18h]
0x180008ab4  mov     r8d, 748h
0x180008aba  jmp     loc_180008BC2
0x180008abf  lea     rax, ProcessRasPortListenEvent
0x180008ac6  jmp     short loc_180008B14
0x180008ac8  test    cs:byte_18004CF34, 1
0x180008acf  jz      short loc_180008B0D
0x180008ad1  mov     word ptr [rsp+880h+var_830], r12w
0x180008ad7  lea     rdx, aProtocolMsgLin; "PROTOCOL_MSG_LineDown recvd, hPort=%d"
0x180008ade  mov     r8, [rbx+10h]
0x180008ae2  lea     rcx, [rsp+880h+var_830]
0x180008ae7  call    FormatRRASErrorString
0x180008aec  test    cs:byte_18004CF34, 1
0x180008af3  jz      short loc_180008B0D
0x180008af5  lea     r8, [rsp+880h+var_830]
0x180008afa  lea     rdx, RasPppTraceInfo
0x180008b01  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008b08  call    McTemplateU0z_EventWriteTransfer
0x180008b0d  lea     rax, ProcessLineDown
0x180008b14  mov     [rbx+8], rax
0x180008b18  jmp     loc_1800091C4
0x180008b1d  lea     rax, ProcessReceive
0x180008b24  mov     [rbx+8], rax
0x180008b28  mov     eax, [rdi+18h]
0x180008b2b  mov     [rbx+30h], eax
0x180008b2e  test    cs:byte_18004CF34, 1
0x180008b35  jz      short loc_180008B77
0x180008b37  mov     word ptr [rsp+880h+var_830], r12w
0x180008b3d  lea     rdx, aPacketReceived; "Packet received (%d bytes) for hPort %d"
0x180008b44  mov     r9, [rbx+10h]
0x180008b48  lea     rcx, [rsp+880h+var_830]
0x180008b4d  mov     r8d, [rbx+30h]
0x180008b51  call    FormatRRASErrorString
0x180008b56  test    cs:byte_18004CF34, 1
0x180008b5d  jz      short loc_180008B77
0x180008b5f  lea     r8, [rsp+880h+var_830]
0x180008b64  lea     rdx, RasPppTraceInfo
0x180008b6b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008b72  call    McTemplateU0z_EventWriteTransfer
0x180008b77  mov     r8d, [rbx+30h]; dwBytes
0x180008b7b  mov     edx, esi; dwFlags
0x180008b7d  mov     rcx, cs:hHeap; hHeap
0x180008b84  call    cs:__imp_HeapAlloc
0x180008b8a  mov     [rbx+28h], rax
0x180008b8e  test    rax, rax
0x180008b91  jnz     short loc_180008BB7
0x180008b93  xor     edx, edx
0x180008b95  call    LogPPPEvent
0x180008b9a  mov     rcx, cs:hHeap; hHeap
0x180008ba1  mov     r8, rbx; lpMem
0x180008ba4  xor     edx, edx; dwFlags
0x180008ba6  call    cs:__imp_HeapFree
0x180008bac  call    cs:__imp_GetLastError
0x180008bb2  jmp     loc_1800091CE
0x180008bb7  mov     r8d, [rbx+30h]; Size
0x180008bbb  mov     rcx, rax; void *
0x180008bbe  mov     rdx, [rdi+20h]; Src
0x180008bc2  call    memcpy_0
0x180008bc7  jmp     loc_1800091C4
0x180008bcc  test    cs:byte_18004CF34, 1
0x180008bd3  jz      short loc_180008C18
0x180008bd5  mov     word ptr [rsp+880h+var_830], r12w
0x180008bdb  lea     r9, [rdi+7AEh]
0x180008be2  mov     r8, [rbx+10h]
0x180008be6  lea     rdx, aProtocolMsgRet; "PROTOCOL_MSG_Retry recvd hPort=%d,u=%hs"
0x180008bed  lea     rcx, [rsp+880h+var_830]
0x180008bf2  call    FormatRRASErrorString
0x180008bf7  test    cs:byte_18004CF34, 1
0x180008bfe  jz      short loc_180008C18
0x180008c00  lea     r8, [rsp+880h+var_830]
0x180008c05  lea     rdx, RasPppTraceInfo
0x180008c0c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008c13  call    McTemplateU0z_EventWriteTransfer
0x180008c18  lea     rax, ProcessRetryPassword
0x180008c1f  mov     [rbx+8], rax
0x180008c23  lea     rcx, [rdi+18h]
0x180008c27  lea     rax, [rbx+48h]
0x180008c2b  movups  xmm0, xmmword ptr [rcx]
0x180008c2e  lea     rcx, [rcx+80h]
0x180008c35  movups  xmmword ptr [rax], xmm0
0x180008c38  lea     rax, [rax+80h]
0x180008c3f  movups  xmm1, xmmword ptr [rcx-70h]
0x180008c43  movups  xmmword ptr [rax-70h], xmm1
0x180008c47  movups  xmm0, xmmword ptr [rcx-60h]
0x180008c4b  movups  xmmword ptr [rax-60h], xmm0
0x180008c4f  movups  xmm1, xmmword ptr [rcx-50h]
0x180008c53  movups  xmmword ptr [rax-50h], xmm1
0x180008c57  movups  xmm0, xmmword ptr [rcx-40h]
0x180008c5b  movups  xmmword ptr [rax-40h], xmm0
0x180008c5f  movups  xmm1, xmmword ptr [rcx-30h]
0x180008c63  movups  xmmword ptr [rax-30h], xmm1
0x180008c67  movups  xmm0, xmmword ptr [rcx-20h]
0x180008c6b  movups  xmmword ptr [rax-20h], xmm0
0x180008c6f  movups  xmm1, xmmword ptr [rcx-10h]
0x180008c73  movups  xmmword ptr [rax-10h], xmm1
0x180008c77  sub     rsi, 1
0x180008c7b  jnz     short loc_180008C2B
0x180008c7d  movups  xmm0, xmmword ptr [rcx]
0x180008c80  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180008c84  lea     r14, [rbx+24Ah]
0x180008c8b  movups  xmmword ptr [rax], xmm0
0x180008c8e  movups  xmm1, xmmword ptr [rcx+10h]
0x180008c92  movups  xmmword ptr [rax+10h], xmm1
0x180008c96  movups  xmm0, xmmword ptr [rcx+20h]
0x180008c9a  movups  xmmword ptr [rax+20h], xmm0
0x180008c9e  movups  xmm1, xmmword ptr [rcx+30h]
0x180008ca2  mov     rcx, rsi
0x180008ca5  movups  xmmword ptr [rax+30h], xmm1
0x180008ca9  inc     rcx
0x180008cac  cmp     [r14+rcx], r12b
0x180008cb0  jnz     short loc_180008CA9
0x180008cb2  lea     r8, [rbx+478h]
0x180008cb9  inc     ecx
0x180008cbb  mov     rdx, r14
0x180008cbe  call    EncodePassword
0x180008cc3  test    eax, eax
0x180008cc5  jz      short loc_180008CE7
0x180008cc7  test    cs:byte_18004CF33, 80h
0x180008cce  jz      loc_1800091C4
0x180008cd4  lea     r8, aEncodepassword; "EncodePassword failed"
0x180008cdb  lea     rdx, RasPppTraceError
0x180008ce2  jmp     loc_1800091B8
0x180008ce7  mov     rax, rsi
0x180008cea  inc     rax
0x180008ced  cmp     [r14+rax], r12b
0x180008cf1  jnz     short loc_180008CEA
0x180008cf3  test    rax, rax
0x180008cf6  jz      short loc_180008D04
0x180008cf8  mov     [r14], r12b
0x180008cfb  inc     r14
0x180008cfe  sub     rax, 1
0x180008d02  jnz     short loc_180008CF8
0x180008d04  add     rdi, 21Ah
0x180008d0b  inc     rsi
0x180008d0e  cmp     [rdi+rsi], r12b
0x180008d12  jnz     short loc_180008D0B
0x180008d14  test    rsi, rsi
0x180008d17  jz      loc_1800091C4
0x180008d1d  mov     [rdi], r12b
0x180008d20  inc     rdi
0x180008d23  sub     rsi, 1
0x180008d27  jnz     short loc_180008D1D
0x180008d29  jmp     loc_1800091C4
0x180008d2e  test    cs:byte_18004CF34, 1
0x180008d35  jz      short loc_180008D73
0x180008d37  mov     word ptr [rsp+880h+var_830], r12w
0x180008d3d  lea     rdx, aProtocolMsgCha; "PROTOCOL_MSG_ChangePw recvd, hPort=%d"
0x180008d44  mov     r8, [rbx+10h]
0x180008d48  lea     rcx, [rsp+880h+var_830]
0x180008d4d  call    FormatRRASErrorString
0x180008d52  test    cs:byte_18004CF34, 1
0x180008d59  jz      short loc_180008D73
0x180008d5b  lea     r8, [rsp+880h+var_830]
0x180008d60  lea     rdx, RasPppTraceInfo
0x180008d67  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008d6e  call    McTemplateU0z_EventWriteTransfer
0x180008d73  lea     rax, ProcessChangePassword
0x180008d7a  mov     r8d, 628h; Size
0x180008d80  lea     rcx, [rbx+48h]; void *
0x180008d84  mov     [rbx+8], rax
0x180008d88  lea     rdx, [rdi+18h]; Src
0x180008d8c  call    memcpy_0
0x180008d91  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180008d95  lea     r15, [rbx+44Ch]
0x180008d9c  mov     rcx, rsi
0x180008d9f  inc     rcx
0x180008da2  cmp     [r15+rcx], r12b
0x180008da6  jnz     short loc_180008D9F
0x180008da8  lea     r8, [rbx+650h]
0x180008daf  inc     ecx
0x180008db1  mov     rdx, r15
0x180008db4  call    EncodePassword
0x180008db9  test    eax, eax
0x180008dbb  jnz     loc_180008CC7
0x180008dc1  lea     r14, [rbx+24Ah]
0x180008dc8  mov     rcx, rsi
0x180008dcb  inc     rcx
0x180008dce  cmp     [r14+rcx], r12b
0x180008dd2  jnz     short loc_180008DCB
0x180008dd4  lea     r8, [rbx+660h]
0x180008ddb  inc     ecx
0x180008ddd  mov     rdx, r14
0x180008de0  call    EncodePassword
0x180008de5  test    eax, eax
0x180008de7  jz      short loc_180008E0C
0x180008de9  test    cs:byte_18004CF33, 80h
0x180008df0  jz      short loc_180008E0C
0x180008df2  lea     r8, aEncodepassword; "EncodePassword failed"
0x180008df9  lea     rdx, RasPppTraceError
0x180008e00  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008e07  call    McTemplateU0z_EventWriteTransfer
0x180008e0c  mov     rax, rsi
0x180008e0f  inc     rax
0x180008e12  cmp     [r14+rax], r12b
0x180008e16  jnz     short loc_180008E0F
0x180008e18  test    rax, rax
0x180008e1b  jz      short loc_180008E29
0x180008e1d  mov     [r14], r12b
0x180008e20  inc     r14
0x180008e23  sub     rax, 1
0x180008e27  jnz     short loc_180008E1D
0x180008e29  mov     rax, rsi
0x180008e2c  inc     rax
0x180008e2f  cmp     [r15+rax], r12b
0x180008e33  jnz     short loc_180008E2C
0x180008e35  test    rax, rax
0x180008e38  jz      short loc_180008E46
0x180008e3a  mov     [r15], r12b
0x180008e3d  inc     r15
0x180008e40  sub     rax, 1
0x180008e44  jnz     short loc_180008E3A
0x180008e46  lea     rcx, [rdi+21Ah]
0x180008e4d  mov     rax, rsi
0x180008e50  inc     rax
0x180008e53  cmp     [rcx+rax], r12b
0x180008e57  jnz     short loc_180008E50
0x180008e59  test    rax, rax
0x180008e5c  jz      short loc_180008E6A
0x180008e5e  mov     [rcx], r12b
0x180008e61  inc     rcx
0x180008e64  sub     rax, 1
0x180008e68  jnz     short loc_180008E5E
0x180008e6a  add     rdi, 41Ch
0x180008e71  inc     rsi
0x180008e74  cmp     [rdi+rsi], r12b
0x180008e78  jnz     short loc_180008E71
0x180008e7a  test    rsi, rsi
0x180008e7d  jz      loc_1800091C4
0x180008e83  mov     [rdi], r12b
0x180008e86  inc     rdi
0x180008e89  sub     rsi, 1
0x180008e8d  jnz     short loc_180008E83
0x180008e8f  jmp     loc_1800091C4
0x180008e94  test    cs:byte_18004CF34, 1
0x180008e9b  jz      short loc_180008ED9
0x180008e9d  mov     word ptr [rsp+880h+var_830], r12w
0x180008ea3  lea     rdx, aProtocolMsgCal; "PROTOCOL_MSG_Callback recvd, hPort=%d"
0x180008eaa  mov     r8, [rbx+10h]
  ... truncated ...
```
