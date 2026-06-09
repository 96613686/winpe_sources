# SendMessageToProtocolEngine

- ea: `0x180008d10`
- end: `0x1800096a6`
- name: `SendMessageToProtocolEngine`
- size: `2454`
- prototype: `DWORD __fastcall(__int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008c70`
- `0x180014880`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x180008d10`
- `0x18001246c`
- `0x180012948`
- `0x180018fcc`
- `0x18002b0dc`
- `0x180033a80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800094e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800094e5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008d59`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008ef0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008d59`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008ef0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f24`

## string_xrefs

- `0x18000933f`: `PROTOCOL_MSG_Start recvd, d=%hs, hPort=%d,flags=%d,mask=%x,IfType=%d`
- `0x1800093c8`: `PROTOCOL_MSG_Start: Encode password failed`
- `0x1800092cb`: `PROTOCOL_MSG_Stop recvd`
- `0x180009221`: `PROTOCOL_MSG_Callback recvd, hPort=%d`
- `0x1800090bb`: `PROTOCOL_MSG_ChangePw recvd, hPort=%d`
- `0x180008f64`: `PROTOCOL_MSG_Retry recvd hPort=%d,u=%hs`
- `0x180008e43`: `PROTOCOL_MSG_LineDown recvd, hPort=%d`
- `0x180009424`: `PROTOCOL_MSG_DdmCallbackDone recvd`
- `0x180009681`: `PROTOCOL_MSG_DdmInterfaceInfo recvd,IPif=%x,IPv6=%x,Type=%x`

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
  void *v35; // rax
  int v36; // eax
  __int64 v37; // rsi
  _BYTE *v38; // r14
  __int64 v39; // rcx
  __int64 v40; // rax
  _BYTE *v41; // rdi
  __int64 v42; // r8
  void (__fastcall *v43)(__int64); // rax
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
          dword_18004DA20 = *(_DWORD *)(a1 + 28);
          dword_18004DAD0 = *(_DWORD *)(a1 + 24);
          goto LABEL_121;
        case 14:
          v43 = ProcessProtocolEvent;
          break;
        case 15:
          v43 = (void (__fastcall *)(__int64))ProcessPostLineDown;
          break;
        case 16:
          *((_QWORD *)v3 + 1) = ProcessRemoveQuarantine;
          *((_QWORD *)v3 + 3) = *(_QWORD *)(a1 + 16);
          goto LABEL_121;
        case 17:
          *((_QWORD *)v3 + 1) = ProcessRenegotiation;
          if ( (byte_18004DF34 & 1) == 0 )
            goto LABEL_121;
          v42 = *(_QWORD *)(a1 + 8);
          LOWORD(v46) = 0;
          FormatRRASErrorString((wchar_t *)&v46, L"Starting PPP renegotiation on port %d", v42);
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
    if ( (byte_18004DF34 & 1) == 0 )
      goto LABEL_121;
    LOWORD(v46) = 0;
    FormatRRASErrorString(
      (wchar_t *)&v46,
      L"PROTOCOL_MSG_DdmInterfaceInfo recvd,IPif=%x,IPv6=%x,Type=%x",
      *((_QWORD *)v3 + 10),
      *((_QWORD *)v3 + 11),
      *((_DWORD *)v3 + 18));
LABEL_118:
    if ( (byte_18004DF34 & 1) == 0 )
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
      if ( (byte_18004DF34 & 1) != 0 )
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
      if ( (byte_18004DF34 & 1) != 0 )
      {
        v45 = *(_DWORD *)(a1 + 4104);
        v44 = *(_DWORD *)(a1 + 2504);
        v36 = *(_DWORD *)(a1 + 2516);
        LOWORD(v46) = 0;
        FormatRRASErrorString(
          (wchar_t *)&v46,
          L"PROTOCOL_MSG_Start recvd, d=%hs, hPort=%d,flags=%d,mask=%x,IfType=%d",
          a1 + 2480,
          *((_QWORD *)v3 + 2),
          v36,
          v44,
          v45);
        if ( (byte_18004DF34 & 1) != 0 )
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
      if ( byte_18004DF33 >= 0 )
      {
LABEL_121:
        InsertWorkItemInQ((__int64)v3);
        return 0;
      }
      v21 = L"PROTOCOL_MSG_Start: Encode password failed";
      goto LABEL_38;
    case 1:
      if ( (byte_18004DF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasPppTraceInfo,
          L"PROTOCOL_MSG_Stop recvd");
      *((_QWORD *)v3 + 1) = ProcessClose;
      *((_DWORD *)v3 + 18) = *(_DWORD *)(a1 + 24);
      goto LABEL_121;
    case 2:
      if ( (byte_18004DF34 & 1) != 0 )
      {
        LOWORD(v46) = 0;
        FormatRRASErrorString((wchar_t *)&v46, L"PROTOCOL_MSG_Callback recvd, hPort=%d", *((_QWORD *)v3 + 2));
        if ( (byte_18004DF34 & 1) != 0 )
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
      if ( (byte_18004DF34 & 1) != 0 )
      {
        LOWORD(v46) = 0;
        FormatRRASErrorString((wchar_t *)&v46, L"PROTOCOL_MSG_ChangePw recvd, hPort=%d", *((_QWORD *)v3 + 2));
        if ( (byte_18004DF34 & 1) != 0 )
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
        if ( (unsigned int)EncodePassword((unsigned int)(v29 + 1), v3 + 586, v3 + 1632) && byte_18004DF33 < 0 )
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
      if ( byte_18004DF33 >= 0 )
        goto LABEL_121;
      v21 = L"EncodePassword failed";
LABEL_38:
      v22 = RasPppTraceError;
      goto LABEL_120;
    case 4:
      if ( (byte_18004DF34 & 1) != 0 )
      {
        LOWORD(v46) = 0;
        FormatRRASErrorString(
          (wchar_t *)&v46,
          L"PROTOCOL_MSG_Retry recvd hPort=%d,u=%hs",
          *((_QWORD *)v3 + 2),
          a1 + 1966);
        if ( (byte_18004DF34 & 1) != 0 )
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
      if ( (byte_18004DF34 & 1) != 0 )
      {
        LOWORD(v46) = 0;
        FormatRRASErrorString(
          (wchar_t *)&v46,
          L"Packet received (%d bytes) for hPort %d",
          *((unsigned int *)v3 + 12),
          *((_QWORD *)v3 + 2));
        if ( (byte_18004DF34 & 1) != 0 )
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
      if ( (byte_18004DF34 & 1) != 0 )
      {
        LOWORD(v46) = 0;
        FormatRRASErrorString((wchar_t *)&v46, L"PROTOCOL_MSG_LineDown recvd, hPort=%d", *((_QWORD *)v3 + 2));
        if ( (byte_18004DF34 & 1) != 0 )
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
  if ( (byte_18004DF34 & 1) != 0 )
  {
    LOWORD(v46) = 0;
    FormatRRASErrorString((wchar_t *)&v46, L"Unknown IPC message %d received");
    if ( (byte_18004DF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v46);
  }
  HeapFree(hHeap, 0, v3);
  return 87;
}

```

## disassembly

```asm
0x180008d10  mov     [rsp-8+arg_8], rbx
0x180008d15  mov     [rsp-8+arg_10], rsi
0x180008d1a  push    rbp
0x180008d1b  push    rdi
0x180008d1c  push    r12
0x180008d1e  push    r14
0x180008d20  push    r15
0x180008d22  lea     rbp, [rsp-760h]
0x180008d2a  sub     rsp, 860h
0x180008d31  mov     rax, cs:__security_cookie
0x180008d38  xor     rax, rsp
0x180008d3b  mov     [rbp+780h+var_30], rax
0x180008d42  mov     rdi, rcx
0x180008d45  mov     esi, 8
0x180008d4a  mov     rcx, cs:hHeap; hHeap
0x180008d51  mov     edx, esi; dwFlags
0x180008d53  mov     r8d, 1C10h; dwBytes
0x180008d59  call    cs:__imp_HeapAlloc
0x180008d60  nop     dword ptr [rax+rax+00h]
0x180008d65  xor     r12d, r12d
0x180008d68  lea     rcx, [rsp+880h+var_82C]; void *
0x180008d6d  xor     edx, edx; Val
0x180008d6f  mov     [rsp+880h+var_830], r12d
0x180008d74  mov     r8d, 7FCh; Size
0x180008d7a  mov     rbx, rax
0x180008d7d  call    memset_0
0x180008d82  test    rbx, rbx
0x180008d85  jnz     short loc_180008DA3
0x180008d87  call    cs:__imp_GetLastError
0x180008d8e  nop     dword ptr [rax+rax+00h]
0x180008d93  xor     edx, edx
0x180008d95  mov     ebx, eax
0x180008d97  call    LogPPPEvent
0x180008d9c  mov     eax, ebx
0x180008d9e  jmp     loc_180009552
0x180008da3  mov     rax, [rdi+8]
0x180008da7  mov     [rbx+10h], rax
0x180008dab  mov     r8d, [rdi]
0x180008dae  cmp     r8d, 9
0x180008db2  jg      loc_180009451
0x180008db8  jz      loc_18000941B
0x180008dbe  mov     ecx, r8d
0x180008dc1  test    r8d, r8d
0x180008dc4  jz      loc_1800092FB
0x180008dca  sub     ecx, 1
0x180008dcd  jz      loc_1800092C2
0x180008dd3  sub     ecx, 1
0x180008dd6  jz      loc_180009212
0x180008ddc  sub     ecx, 1
0x180008ddf  jz      loc_1800090AC
0x180008de5  sub     ecx, 1
0x180008de8  jz      loc_180008F4A
0x180008dee  sub     ecx, 1
0x180008df1  jz      loc_180008E89
0x180008df7  sub     ecx, 1
0x180008dfa  jz      short loc_180008E34
0x180008dfc  sub     ecx, 1
0x180008dff  jz      short loc_180008E2B
0x180008e01  cmp     ecx, 1
0x180008e04  jnz     loc_180009498
0x180008e0a  lea     rax, ProcessLineUp
0x180008e11  mov     [rbx+20h], ecx
0x180008e14  mov     [rbx+8], rax
0x180008e18  lea     rcx, [rbx+48h]
0x180008e1c  lea     rdx, [rdi+18h]
0x180008e20  mov     r8d, 748h
0x180008e26  jmp     loc_180008F40
0x180008e2b  lea     rax, ProcessRasPortListenEvent
0x180008e32  jmp     short loc_180008E80
0x180008e34  test    cs:byte_18004DF34, 1
0x180008e3b  jz      short loc_180008E79
0x180008e3d  mov     word ptr [rsp+880h+var_830], r12w
0x180008e43  lea     rdx, aProtocolMsgLin; "PROTOCOL_MSG_LineDown recvd, hPort=%d"
0x180008e4a  mov     r8, [rbx+10h]
0x180008e4e  lea     rcx, [rsp+880h+var_830]
0x180008e53  call    FormatRRASErrorString
0x180008e58  test    cs:byte_18004DF34, 1
0x180008e5f  jz      short loc_180008E79
0x180008e61  lea     r8, [rsp+880h+var_830]
0x180008e66  lea     rdx, RasPppTraceInfo
0x180008e6d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008e74  call    McTemplateU0z_EventWriteTransfer
0x180008e79  lea     rax, ProcessLineDown
0x180008e80  mov     [rbx+8], rax
0x180008e84  jmp     loc_180009548
0x180008e89  lea     rax, ProcessReceive
0x180008e90  mov     [rbx+8], rax
0x180008e94  mov     eax, [rdi+18h]
0x180008e97  mov     [rbx+30h], eax
0x180008e9a  test    cs:byte_18004DF34, 1
0x180008ea1  jz      short loc_180008EE3
0x180008ea3  mov     word ptr [rsp+880h+var_830], r12w
0x180008ea9  lea     rdx, aPacketReceived; "Packet received (%d bytes) for hPort %d"
0x180008eb0  mov     r9, [rbx+10h]
0x180008eb4  lea     rcx, [rsp+880h+var_830]
0x180008eb9  mov     r8d, [rbx+30h]
0x180008ebd  call    FormatRRASErrorString
0x180008ec2  test    cs:byte_18004DF34, 1
0x180008ec9  jz      short loc_180008EE3
0x180008ecb  lea     r8, [rsp+880h+var_830]
0x180008ed0  lea     rdx, RasPppTraceInfo
0x180008ed7  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008ede  call    McTemplateU0z_EventWriteTransfer
0x180008ee3  mov     r8d, [rbx+30h]; dwBytes
0x180008ee7  mov     edx, esi; dwFlags
0x180008ee9  mov     rcx, cs:hHeap; hHeap
0x180008ef0  call    cs:__imp_HeapAlloc
0x180008ef7  nop     dword ptr [rax+rax+00h]
0x180008efc  mov     [rbx+28h], rax
0x180008f00  test    rax, rax
0x180008f03  jnz     short loc_180008F35
0x180008f05  xor     edx, edx
0x180008f07  call    LogPPPEvent
0x180008f0c  mov     rcx, cs:hHeap; hHeap
0x180008f13  mov     r8, rbx; lpMem
0x180008f16  xor     edx, edx; dwFlags
0x180008f18  call    cs:__imp_HeapFree
0x180008f1f  nop     dword ptr [rax+rax+00h]
0x180008f24  call    cs:__imp_GetLastError
0x180008f2b  nop     dword ptr [rax+rax+00h]
0x180008f30  jmp     loc_180009552
0x180008f35  mov     r8d, [rbx+30h]; Size
0x180008f39  mov     rcx, rax; void *
0x180008f3c  mov     rdx, [rdi+20h]; Src
0x180008f40  call    memcpy_0
0x180008f45  jmp     loc_180009548
0x180008f4a  test    cs:byte_18004DF34, 1
0x180008f51  jz      short loc_180008F96
0x180008f53  mov     word ptr [rsp+880h+var_830], r12w
0x180008f59  lea     r9, [rdi+7AEh]
0x180008f60  mov     r8, [rbx+10h]
0x180008f64  lea     rdx, aProtocolMsgRet; "PROTOCOL_MSG_Retry recvd hPort=%d,u=%hs"
0x180008f6b  lea     rcx, [rsp+880h+var_830]
0x180008f70  call    FormatRRASErrorString
0x180008f75  test    cs:byte_18004DF34, 1
0x180008f7c  jz      short loc_180008F96
0x180008f7e  lea     r8, [rsp+880h+var_830]
0x180008f83  lea     rdx, RasPppTraceInfo
0x180008f8a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008f91  call    McTemplateU0z_EventWriteTransfer
0x180008f96  lea     rax, ProcessRetryPassword
0x180008f9d  mov     [rbx+8], rax
0x180008fa1  lea     rcx, [rdi+18h]
0x180008fa5  lea     rax, [rbx+48h]
0x180008fa9  movups  xmm0, xmmword ptr [rcx]
0x180008fac  lea     rcx, [rcx+80h]
0x180008fb3  movups  xmmword ptr [rax], xmm0
0x180008fb6  lea     rax, [rax+80h]
0x180008fbd  movups  xmm1, xmmword ptr [rcx-70h]
0x180008fc1  movups  xmmword ptr [rax-70h], xmm1
0x180008fc5  movups  xmm0, xmmword ptr [rcx-60h]
0x180008fc9  movups  xmmword ptr [rax-60h], xmm0
0x180008fcd  movups  xmm1, xmmword ptr [rcx-50h]
0x180008fd1  movups  xmmword ptr [rax-50h], xmm1
0x180008fd5  movups  xmm0, xmmword ptr [rcx-40h]
0x180008fd9  movups  xmmword ptr [rax-40h], xmm0
0x180008fdd  movups  xmm1, xmmword ptr [rcx-30h]
0x180008fe1  movups  xmmword ptr [rax-30h], xmm1
0x180008fe5  movups  xmm0, xmmword ptr [rcx-20h]
0x180008fe9  movups  xmmword ptr [rax-20h], xmm0
0x180008fed  movups  xmm1, xmmword ptr [rcx-10h]
0x180008ff1  movups  xmmword ptr [rax-10h], xmm1
0x180008ff5  sub     rsi, 1
0x180008ff9  jnz     short loc_180008FA9
0x180008ffb  movups  xmm0, xmmword ptr [rcx]
0x180008ffe  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009002  lea     r14, [rbx+24Ah]
0x180009009  movups  xmmword ptr [rax], xmm0
0x18000900c  movups  xmm1, xmmword ptr [rcx+10h]
0x180009010  movups  xmmword ptr [rax+10h], xmm1
0x180009014  movups  xmm0, xmmword ptr [rcx+20h]
0x180009018  movups  xmmword ptr [rax+20h], xmm0
0x18000901c  movups  xmm1, xmmword ptr [rcx+30h]
0x180009020  mov     rcx, rsi
0x180009023  movups  xmmword ptr [rax+30h], xmm1
0x180009027  inc     rcx
0x18000902a  cmp     [r14+rcx], r12b
0x18000902e  jnz     short loc_180009027
0x180009030  lea     r8, [rbx+478h]
0x180009037  inc     ecx
0x180009039  mov     rdx, r14
0x18000903c  call    EncodePassword
0x180009041  test    eax, eax
0x180009043  jz      short loc_180009065
0x180009045  test    cs:byte_18004DF33, 80h
0x18000904c  jz      loc_180009548
0x180009052  lea     r8, aEncodepassword; "EncodePassword failed"
0x180009059  lea     rdx, RasPppTraceError
0x180009060  jmp     loc_18000953C
0x180009065  mov     rax, rsi
0x180009068  inc     rax
0x18000906b  cmp     [r14+rax], r12b
0x18000906f  jnz     short loc_180009068
0x180009071  test    rax, rax
0x180009074  jz      short loc_180009082
0x180009076  mov     [r14], r12b
0x180009079  inc     r14
0x18000907c  sub     rax, 1
0x180009080  jnz     short loc_180009076
0x180009082  add     rdi, 21Ah
0x180009089  inc     rsi
0x18000908c  cmp     [rdi+rsi], r12b
0x180009090  jnz     short loc_180009089
0x180009092  test    rsi, rsi
0x180009095  jz      loc_180009548
0x18000909b  mov     [rdi], r12b
0x18000909e  inc     rdi
0x1800090a1  sub     rsi, 1
0x1800090a5  jnz     short loc_18000909B
0x1800090a7  jmp     loc_180009548
0x1800090ac  test    cs:byte_18004DF34, 1
0x1800090b3  jz      short loc_1800090F1
0x1800090b5  mov     word ptr [rsp+880h+var_830], r12w
0x1800090bb  lea     rdx, aProtocolMsgCha; "PROTOCOL_MSG_ChangePw recvd, hPort=%d"
0x1800090c2  mov     r8, [rbx+10h]
0x1800090c6  lea     rcx, [rsp+880h+var_830]
0x1800090cb  call    FormatRRASErrorString
0x1800090d0  test    cs:byte_18004DF34, 1
0x1800090d7  jz      short loc_1800090F1
0x1800090d9  lea     r8, [rsp+880h+var_830]
0x1800090de  lea     rdx, RasPppTraceInfo
0x1800090e5  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800090ec  call    McTemplateU0z_EventWriteTransfer
0x1800090f1  lea     rax, ProcessChangePassword
0x1800090f8  mov     r8d, 628h; Size
0x1800090fe  lea     rcx, [rbx+48h]; void *
0x180009102  mov     [rbx+8], rax
0x180009106  lea     rdx, [rdi+18h]; Src
0x18000910a  call    memcpy_0
0x18000910f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009113  lea     r15, [rbx+44Ch]
0x18000911a  mov     rcx, rsi
0x18000911d  inc     rcx
0x180009120  cmp     [r15+rcx], r12b
0x180009124  jnz     short loc_18000911D
0x180009126  lea     r8, [rbx+650h]
0x18000912d  inc     ecx
0x18000912f  mov     rdx, r15
0x180009132  call    EncodePassword
0x180009137  test    eax, eax
0x180009139  jnz     loc_180009045
0x18000913f  lea     r14, [rbx+24Ah]
0x180009146  mov     rcx, rsi
0x180009149  inc     rcx
0x18000914c  cmp     [r14+rcx], r12b
0x180009150  jnz     short loc_180009149
0x180009152  lea     r8, [rbx+660h]
0x180009159  inc     ecx
0x18000915b  mov     rdx, r14
0x18000915e  call    EncodePassword
0x180009163  test    eax, eax
0x180009165  jz      short loc_18000918A
0x180009167  test    cs:byte_18004DF33, 80h
0x18000916e  jz      short loc_18000918A
0x180009170  lea     r8, aEncodepassword; "EncodePassword failed"
0x180009177  lea     rdx, RasPppTraceError
0x18000917e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009185  call    McTemplateU0z_EventWriteTransfer
0x18000918a  mov     rax, rsi
0x18000918d  inc     rax
0x180009190  cmp     [r14+rax], r12b
0x180009194  jnz     short loc_18000918D
0x180009196  test    rax, rax
0x180009199  jz      short loc_1800091A7
0x18000919b  mov     [r14], r12b
0x18000919e  inc     r14
0x1800091a1  sub     rax, 1
0x1800091a5  jnz     short loc_18000919B
0x1800091a7  mov     rax, rsi
0x1800091aa  inc     rax
0x1800091ad  cmp     [r15+rax], r12b
0x1800091b1  jnz     short loc_1800091AA
0x1800091b3  test    rax, rax
0x1800091b6  jz      short loc_1800091C4
0x1800091b8  mov     [r15], r12b
0x1800091bb  inc     r15
0x1800091be  sub     rax, 1
0x1800091c2  jnz     short loc_1800091B8
0x1800091c4  lea     rcx, [rdi+21Ah]
0x1800091cb  mov     rax, rsi
0x1800091ce  inc     rax
0x1800091d1  cmp     [rcx+rax], r12b
0x1800091d5  jnz     short loc_1800091CE
0x1800091d7  test    rax, rax
0x1800091da  jz      short loc_1800091E8
0x1800091dc  mov     [rcx], r12b
0x1800091df  inc     rcx
0x1800091e2  sub     rax, 1
0x1800091e6  jnz     short loc_1800091DC
0x1800091e8  add     rdi, 41Ch
0x1800091ef  inc     rsi
0x1800091f2  cmp     [rdi+rsi], r12b
0x1800091f6  jnz     short loc_1800091EF
0x1800091f8  test    rsi, rsi
0x1800091fb  jz      loc_180009548
0x180009201  mov     [rdi], r12b
0x180009204  inc     rdi
0x180009207  sub     rsi, 1
0x18000920b  jnz     short loc_180009201
0x18000920d  jmp     loc_180009548
  ... truncated ...
```
