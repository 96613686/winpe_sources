# CreateSockets

- ea: `0x18004deec`
- end: `0x18004e937`
- name: `CreateSockets`
- size: `2635`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004d8d0`

## callees

- `0x180011790`
- `0x18004deec`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18004e0f6`
- `KERNEL32!HeapAlloc` at `0x18004e0f6`
- `WS2_32!WSAIoctl` at `0x18004e53c`
- `WS2_32!WSAIoctl` at `0x18004e612`
- `WS2_32!WSAIoctl` at `0x18004e53c`
- `WS2_32!WSAIoctl` at `0x18004e612`
- `WS2_32!WSAEventSelect` at `0x18004e3f2`
- `WS2_32!WSAEventSelect` at `0x18004e3f2`
- `WS2_32!WSASocketA` at `0x18004e265`
- `WS2_32!WSASocketA` at `0x18004e265`
- `WS2_32!__imp_bind` at `0x18004e483`
- `WS2_32!__imp_bind` at `0x18004e483`
- `WS2_32!__imp_closesocket` at `0x18004e897`
- `WS2_32!__imp_closesocket` at `0x18004e897`
- `WS2_32!__imp_setsockopt` at `0x18004e349`
- `WS2_32!__imp_setsockopt` at `0x18004e6dd`
- `WS2_32!__imp_setsockopt` at `0x18004e7ca`
- `WS2_32!__imp_setsockopt` at `0x18004e349`
- `WS2_32!__imp_setsockopt` at `0x18004e6dd`
- `WS2_32!__imp_setsockopt` at `0x18004e7ca`
- `WS2_32!__imp_WSAGetLastError` at `0x18004e288`
- `WS2_32!__imp_WSAGetLastError` at `0x18004e373`
- `WS2_32!__imp_WSAGetLastError` at `0x18004e420`
- `WS2_32!__imp_WSAGetLastError` at `0x18004e48e`
- `WS2_32!__imp_WSAGetLastError` at `0x18004e56a`
- `WS2_32!__imp_WSAGetLastError` at `0x18004e644`
- `WS2_32!__imp_WSAGetLastError` at `0x18004e7d9`
- `WS2_32!__imp_WSAGetLastError` at `0x18004e288`
- `WS2_32!__imp_WSAGetLastError` at `0x18004e373`
- `WS2_32!__imp_WSAGetLastError` at `0x18004e420`
- `WS2_32!__imp_WSAGetLastError` at `0x18004e48e`
- `WS2_32!__imp_WSAGetLastError` at `0x18004e56a`
- `WS2_32!__imp_WSAGetLastError` at `0x18004e644`
- `WS2_32!__imp_WSAGetLastError` at `0x18004e7d9`

## string_xrefs

- `0x18004dfbd`: `Entered: CreateSockets`
- `0x18004e010`: `CreateSockets: Can not activate router discovery on %ws as it has no addresses`
- `0x18004e097`: `Leaving: CreateSockets`
- `0x18004e8c9`: `Leaving: CreateSockets`
- `0x18004e11a`: `CreateSockets: Arithmetic overflow error allocating %d bytes for sockets`
- `0x18004e1a2`: `CreateSockets: Error allocating %d bytes for sockets`
- `0x18004e2a2`: `CreateSockets: Couldnt create socket number %d on %ws. Error %d`
- `0x18004e37c`: `CreateSockets: Couldnt set reuse option - continuing. Error %d`
- `0x18004e429`: `CreateSockets: WSAEventSelect() failed for socket on %ws.Error %d`
- `0x18004e4f0`: `CreateSockets: Couldnt bind to %d.%d.%d.%d on interface %ws. Error %d`
- `0x18004e573`: `CreateSockets: Error %d setting loopback to FALSE`
- `0x18004e64d`: `CreateSockets: Error %d setting multicast scope to 1`
- `0x18004e836`: `CreateSockets: Couldnt join multicast group on socket for %d.%d.%d.%d on %ws`
- `0x18004e740`: `CreateSockets: Joining ALL_ROUTERS on %d.%d.%d.%d over %ws`

## pseudocode

```c
__int64 __fastcall CreateSockets(__int64 a1)
{
  char v2; // al
  __int128 *v3; // r9
  __int64 v4; // rcx
  __int64 v5; // r8
  __int128 *v6; // r9
  __int128 *v7; // r9
  unsigned __int64 v9; // rcx
  unsigned int v10; // ebx
  LPVOID v11; // rax
  __int128 *v12; // r9
  __int128 *v13; // r9
  unsigned int v14; // r12d
  __int64 i; // rdx
  __int64 j; // r13
  __int64 v17; // rcx
  int Error; // eax
  __int64 v19; // r9
  __int128 *v20; // r9
  unsigned int v21; // eax
  __int128 *v22; // r9
  __int64 v23; // rbx
  unsigned int v24; // eax
  __int64 v25; // rax
  __int64 v26; // rbx
  __int64 v27; // rcx
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rcx
  unsigned int v31; // eax
  __int128 *v32; // r9
  __int64 v33; // rcx
  unsigned int v34; // eax
  __int128 *v35; // r9
  __int64 v36; // rax
  __int128 *v37; // r9
  __int64 v38; // rax
  __int64 v39; // rax
  __int128 *v40; // r9
  __int128 *v41; // r9
  GROUP g[2]; // [rsp+20h] [rbp-8D8h]
  GROUP ga[2]; // [rsp+20h] [rbp-8D8h]
  GROUP gb[2]; // [rsp+20h] [rbp-8D8h]
  DWORD dwFlags[2]; // [rsp+28h] [rbp-8D0h]
  DWORD dwFlagsa[2]; // [rsp+28h] [rbp-8D0h]
  LPWSAOVERLAPPED lpOverlapped; // [rsp+38h] [rbp-8C0h]
  char optval[4]; // [rsp+50h] [rbp-8A8h] BYREF
  int vInBuffer; // [rsp+54h] [rbp-8A4h] BYREF
  DWORD cbBytesReturned; // [rsp+58h] [rbp-8A0h] BYREF
  int v51[3]; // [rsp+5Ch] [rbp-89Ch] BYREF
  char v52[8]; // [rsp+68h] [rbp-890h] BYREF
  __int128 v53; // [rsp+70h] [rbp-888h] BYREF
  struct sockaddr name; // [rsp+80h] [rbp-878h] BYREF
  int v55; // [rsp+90h] [rbp-868h] BYREF
  __int128 v56; // [rsp+94h] [rbp-864h]
  __int128 v57; // [rsp+A4h] [rbp-854h]
  int v58; // [rsp+B4h] [rbp-844h]
  int v59; // [rsp+C0h] [rbp-838h] BYREF
  _BYTE v60[2044]; // [rsp+C4h] [rbp-834h] BYREF

  cbBytesReturned = 0;
  *(_DWORD *)optval = 0;
  vInBuffer = 0;
  v59 = 0;
  *(_QWORD *)v52 = 0;
  v51[0] = 0;
  name = 0;
  memset_0(v60, 0, sizeof(v60));
  v55 = 0;
  v58 = 0;
  v2 = Microsoft_Windows_RRASEnableBits;
  v56 = 0;
  v57 = 0;
  v53 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v3 = &v53;
    LOWORD(v55) = 0;
    if ( a1 != -688 )
      LODWORD(v3) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: CreateSockets",
      (_DWORD)v3,
      *(_QWORD *)(a1 + 72),
      (__int64)&v55);
    v2 = Microsoft_Windows_RRASEnableBits;
  }
  v4 = *(unsigned int *)(a1 + 668);
  if ( !(_DWORD)v4 )
  {
    if ( v2 < 0 )
    {
      v5 = *(_QWORD *)(a1 + 72);
      LOWORD(v59) = 0;
      LOWORD(v55) = 0;
      FormatRRASErrorString(&v59, L"CreateSockets: Can not activate router discovery on %ws as it has no addresses", v5);
      v2 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v6 = &v53;
        if ( a1 != -688 )
          LODWORD(v6) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v59,
          (_DWORD)v6,
          *(_QWORD *)(a1 + 72),
          (__int64)&v55);
        v2 = Microsoft_Windows_RRASEnableBits;
      }
    }
    if ( v2 < 0 )
    {
      v7 = &v53;
      LOWORD(v55) = 0;
      if ( a1 != -688 )
        LODWORD(v7) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)L"Leaving: CreateSockets",
        (_DWORD)v7,
        *(_QWORD *)(a1 + 72),
        (__int64)&v55);
    }
    return 1003;
  }
  v9 = 8 * v4;
  if ( v9 > 0xFFFFFFFF )
  {
    v10 = -1;
    if ( (v2 & 0x40) != 0 )
    {
      LOWORD(v59) = 0;
      LOWORD(v55) = 0;
      FormatRRASErrorString(
        &v59,
        L"CreateSockets: Arithmetic overflow error allocating %d bytes for sockets",
        0xFFFFFFFFLL);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v12 = &v53;
        if ( a1 != -688 )
          LODWORD(v12) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v59,
          (_DWORD)v12,
          *(_QWORD *)(a1 + 72),
          (__int64)&v55);
      }
    }
    v11 = 0;
  }
  else
  {
    v10 = v9;
    v11 = HeapAlloc(IPRouterHeap, 0, (unsigned int)v9);
  }
  *(_QWORD *)(a1 + 288) = v11;
  if ( !v11 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v59) = 0;
      LOWORD(v55) = 0;
      FormatRRASErrorString(&v59, L"CreateSockets: Error allocating %d bytes for sockets", v10);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v13 = &v53;
        if ( a1 != -688 )
          LODWORD(v13) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v59,
          (_DWORD)v13,
          *(_QWORD *)(a1 + 72),
          (__int64)&v55);
      }
    }
    return 8;
  }
  v14 = 0;
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 668); i = (unsigned int)(i + 1) )
    *(_QWORD *)(*(_QWORD *)(a1 + 288) + 8 * i) = -1;
  for ( j = 0; (unsigned int)j < *(_DWORD *)(a1 + 668); j = (unsigned int)(j + 1) )
  {
    *(_QWORD *)(*(_QWORD *)(a1 + 288) + 8 * j) = WSASocketA(2, 3, 1, 0, 0, 0x14u);
    v17 = *(_QWORD *)(a1 + 288);
    if ( *(_QWORD *)(v17 + 8 * j) == -1 )
    {
      Error = WSAGetLastError();
      v14 = Error;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v19 = *(_QWORD *)(a1 + 72);
        g[0] = Error;
        LOWORD(v59) = 0;
        LOWORD(v55) = 0;
        FormatRRASErrorString(
          &v59,
          L"CreateSockets: Couldnt create socket number %d on %ws. Error %d",
          (unsigned int)j,
          v19,
          *(_QWORD *)g);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v20 = &v53;
          if ( a1 != -688 )
            LODWORD(v20) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v59,
            (_DWORD)v20,
            *(_QWORD *)(a1 + 72),
            (__int64)&v55);
        }
      }
    }
    else
    {
      *(_DWORD *)optval = 1;
      if ( setsockopt(*(_QWORD *)(v17 + 8 * j), 0xFFFF, 4, optval, 4) == -1
        && (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v59) = 0;
        LOWORD(v55) = 0;
        v21 = WSAGetLastError();
        FormatRRASErrorString(&v59, L"CreateSockets: Couldnt set reuse option - continuing. Error %d", v21);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v22 = &v53;
          if ( a1 != -688 )
            LODWORD(v22) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v59,
            (_DWORD)v22,
            *(_QWORD *)(a1 + 72),
            (__int64)&v55);
        }
      }
      if ( WSAEventSelect(*(_QWORD *)(*(_QWORD *)(a1 + 288) + 8 * j), g_hRtrDiscSocketEvent, 1) == -1 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v23 = *(_QWORD *)(a1 + 72);
          LOWORD(v59) = 0;
          LOWORD(v55) = 0;
          v24 = WSAGetLastError();
          FormatRRASErrorString(&v59, L"CreateSockets: WSAEventSelect() failed for socket on %ws.Error %d", v23, v24);
LABEL_74:
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v40 = &v53;
            if ( a1 != -688 )
              LODWORD(v40) = a1 + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrmgrParamTraceInfo,
              (unsigned int)&v59,
              (_DWORD)v40,
              *(_QWORD *)(a1 + 72),
              (__int64)&v55);
          }
        }
        goto LABEL_78;
      }
      v25 = *(_QWORD *)(a1 + 712);
      name.sa_family = 2;
      v26 = 28LL * (unsigned int)j;
      *(_DWORD *)&name.sa_data[2] = *(_DWORD *)(v26 + v25);
      v27 = *(_QWORD *)(a1 + 288);
      *(_WORD *)name.sa_data = 0;
      if ( bind(*(_QWORD *)(v27 + 8 * j), &name, 16) == -1 )
      {
        v28 = WSAGetLastError();
        v14 = v28;
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LODWORD(lpOverlapped) = v28;
          LOWORD(v59) = 0;
          LOWORD(v55) = 0;
          v29 = *(_QWORD *)(a1 + 712);
          dwFlags[0] = *(unsigned __int8 *)(v26 + v29 + 3);
          ga[0] = *(unsigned __int8 *)(v26 + v29 + 2);
          FormatRRASErrorString(
            &v59,
            L"CreateSockets: Couldnt bind to %d.%d.%d.%d on interface %ws. Error %d",
            *(unsigned __int8 *)(v26 + v29),
            *(unsigned __int8 *)(v26 + v29 + 1),
            *(_QWORD *)ga,
            *(_QWORD *)dwFlags,
            *(_QWORD *)(a1 + 72),
            lpOverlapped);
          goto LABEL_74;
        }
LABEL_78:
        closesocket(*(_QWORD *)(*(_QWORD *)(a1 + 288) + 8 * j));
        *(_QWORD *)(*(_QWORD *)(a1 + 288) + 8 * j) = -1;
        continue;
      }
      v30 = *(_QWORD *)(a1 + 288);
      vInBuffer = 0;
      if ( WSAIoctl(*(_QWORD *)(v30 + 8 * j), 0x88000009, &vInBuffer, 4u, 0, 0, &cbBytesReturned, 0, 0) == -1
        && (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v59) = 0;
        LOWORD(v55) = 0;
        v31 = WSAGetLastError();
        FormatRRASErrorString(&v59, L"CreateSockets: Error %d setting loopback to FALSE", v31);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v32 = &v53;
          if ( a1 != -688 )
            LODWORD(v32) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v59,
            (_DWORD)v32,
            *(_QWORD *)(a1 + 72),
            (__int64)&v55);
        }
      }
      v33 = *(_QWORD *)(a1 + 288);
      v51[0] = 1;
      v14 = WSAIoctl(*(_QWORD *)(v33 + 8 * j), 0x8800000A, v51, 4u, 0, 0, &cbBytesReturned, 0, 0);
      if ( v14 == -1 && (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v59) = 0;
        LOWORD(v55) = 0;
        v34 = WSAGetLastError();
        FormatRRASErrorString(&v59, L"CreateSockets: Error %d setting multicast scope to 1", v34);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v35 = &v53;
          if ( a1 != -688 )
            LODWORD(v35) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v59,
            (_DWORD)v35,
            *(_QWORD *)(a1 + 72),
            (__int64)&v55);
        }
      }
      *(_DWORD *)&name.sa_data[2] = *(_DWORD *)(v26 + *(_QWORD *)(a1 + 712));
      if ( setsockopt(*(_QWORD *)(*(_QWORD *)(a1 + 288) + 8 * j), 0, 9, &name.sa_data[2], 4) == -1 )
        goto LABEL_72;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v59) = 0;
        LOWORD(v55) = 0;
        v36 = *(_QWORD *)(a1 + 712);
        dwFlagsa[0] = *(unsigned __int8 *)(v26 + v36 + 3);
        gb[0] = *(unsigned __int8 *)(v26 + v36 + 2);
        FormatRRASErrorString(
          &v59,
          L"CreateSockets: Joining ALL_ROUTERS on %d.%d.%d.%d over %ws",
          *(unsigned __int8 *)(v26 + v36),
          *(unsigned __int8 *)(v26 + v36 + 1),
          *(_QWORD *)gb,
          *(_QWORD *)dwFlagsa,
          *(_QWORD *)(a1 + 72));
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v37 = &v53;
          if ( a1 != -688 )
            LODWORD(v37) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v59,
            (_DWORD)v37,
            *(_QWORD *)(a1 + 72),
            (__int64)&v55);
        }
      }
      v38 = *(_QWORD *)(a1 + 712);
      *(_DWORD *)v52 = 33554656;
      *(_DWORD *)&v52[4] = *(_DWORD *)(v26 + v38);
      if ( setsockopt(*(_QWORD *)(*(_QWORD *)(a1 + 288) + 8 * j), 0, 12, v52, 8) == -1 )
      {
LABEL_72:
        v14 = WSAGetLastError();
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v59) = 0;
          LOWORD(v55) = 0;
          v39 = *(_QWORD *)(a1 + 712);
          dwFlagsa[0] = *(unsigned __int8 *)(v26 + v39 + 3);
          gb[0] = *(unsigned __int8 *)(v26 + v39 + 2);
          FormatRRASErrorString(
            &v59,
            L"CreateSockets: Couldnt join multicast group on socket for %d.%d.%d.%d on %ws",
            *(unsigned __int8 *)(v26 + v39),
            *(unsigned __int8 *)(v26 + v39 + 1),
            *(_QWORD *)gb,
            *(_QWORD *)dwFlagsa,
            *(_QWORD *)(a1 + 72));
          goto LABEL_74;
        }
        goto LABEL_78;
      }
    }
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v41 = &v53;
    LOWORD(v55) = 0;
    if ( a1 != -688 )
      LODWORD(v41) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Leaving: CreateSockets",
      (_DWORD)v41,
      *(_QWORD *)(a1 + 72),
      (__int64)&v55);
  }
  return v14;
}

```

## disassembly

```asm
0x18004deec  mov     [rsp+arg_8], rbx
0x18004def1  mov     [rsp+arg_10], rsi
0x18004def6  push    rdi
0x18004def7  push    r12
0x18004def9  push    r13
0x18004defb  push    r14
0x18004defd  push    r15
0x18004deff  sub     rsp, 8D0h
0x18004df06  mov     rax, cs:__security_cookie
0x18004df0d  xor     rax, rsp
0x18004df10  mov     [rsp+8F8h+var_38], rax
0x18004df18  mov     rdi, rcx
0x18004df1b  mov     [rsp+8F8h+cbBytesReturned], 0
0x18004df23  xorps   xmm0, xmm0
0x18004df26  mov     dword ptr [rsp+8F8h+optval], 0
0x18004df2e  xor     eax, eax
0x18004df30  mov     [rsp+8F8h+vInBuffer], 0
0x18004df38  lea     rcx, [rsp+8F8h+var_834]; void *
0x18004df40  mov     [rsp+8F8h+var_838], eax
0x18004df47  xor     edx, edx; Val
0x18004df49  mov     qword ptr [rsp+8F8h+var_890], 0
0x18004df52  mov     r8d, 7FCh; Size
0x18004df58  mov     [rsp+8F8h+var_89C], 0
0x18004df60  movups  xmmword ptr [rsp+8F8h+name.sa_family], xmm0
0x18004df68  call    memset_0
0x18004df6d  xor     eax, eax
0x18004df6f  lea     rbx, RasRtrmgrParamTraceInfo
0x18004df76  xorps   xmm0, xmm0
0x18004df79  mov     [rsp+8F8h+var_868], eax
0x18004df80  mov     [rsp+8F8h+var_844], eax
0x18004df87  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004df8e  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004df95  movups  [rsp+8F8h+var_864], xmm0
0x18004df9d  movups  [rsp+8F8h+var_854], xmm0
0x18004dfa5  movups  [rsp+8F8h+var_888], xmm0
0x18004dfaa  test    al, 80h
0x18004dfac  jz      short loc_18004DFFA
0x18004dfae  xor     eax, eax
0x18004dfb0  lea     r9, [rsp+8F8h+var_888]
0x18004dfb5  mov     word ptr [rsp+8F8h+var_868], ax
0x18004dfbd  lea     r8, aEnteredCreates; "Entered: CreateSockets"
0x18004dfc4  lea     rax, [rdi+2B0h]
0x18004dfcb  mov     rdx, rbx
0x18004dfce  test    rax, rax
0x18004dfd1  mov     rcx, r12
0x18004dfd4  cmovnz  r9, rax
0x18004dfd8  lea     rax, [rsp+8F8h+var_868]
0x18004dfe0  mov     qword ptr [rsp+8F8h+dwFlags], rax
0x18004dfe5  mov     rax, [rdi+48h]
0x18004dfe9  mov     qword ptr [rsp+8F8h+g], rax
0x18004dfee  call    McTemplateU0zjzz_EventWriteTransfer
0x18004dff3  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004dffa  mov     ecx, [rdi+29Ch]
0x18004e000  test    ecx, ecx
0x18004e002  jnz     loc_18004E0D7
0x18004e008  test    al, al
0x18004e00a  jns     short loc_18004E084
0x18004e00c  mov     r8, [rdi+48h]
0x18004e010  lea     rdx, aCreatesocketsC_3; "CreateSockets: Can not activate router "...
0x18004e017  xor     eax, eax
0x18004e019  lea     rcx, [rsp+8F8h+var_838]
0x18004e021  mov     word ptr [rsp+8F8h+var_838], ax
0x18004e029  mov     word ptr [rsp+8F8h+var_868], ax
0x18004e031  call    FormatRRASErrorString
0x18004e036  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004e03d  test    al, al
0x18004e03f  jns     short loc_18004E084
0x18004e041  lea     rax, [rdi+2B0h]
0x18004e048  mov     rdx, rbx
0x18004e04b  test    rax, rax
0x18004e04e  lea     r9, [rsp+8F8h+var_888]
0x18004e053  lea     r8, [rsp+8F8h+var_838]
0x18004e05b  mov     rcx, r12
0x18004e05e  cmovnz  r9, rax
0x18004e062  lea     rax, [rsp+8F8h+var_868]
0x18004e06a  mov     qword ptr [rsp+8F8h+dwFlags], rax
0x18004e06f  mov     rax, [rdi+48h]
0x18004e073  mov     qword ptr [rsp+8F8h+g], rax
0x18004e078  call    McTemplateU0zjzz_EventWriteTransfer
0x18004e07d  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18004e084  test    al, 80h
0x18004e086  jz      short loc_18004E0CD
0x18004e088  xor     eax, eax
0x18004e08a  lea     r9, [rsp+8F8h+var_888]
0x18004e08f  mov     word ptr [rsp+8F8h+var_868], ax
0x18004e097  lea     r8, aLeavingCreates; "Leaving: CreateSockets"
0x18004e09e  lea     rax, [rdi+2B0h]
0x18004e0a5  mov     rdx, rbx
0x18004e0a8  test    rax, rax
0x18004e0ab  mov     rcx, r12
0x18004e0ae  cmovnz  r9, rax
0x18004e0b2  lea     rax, [rsp+8F8h+var_868]
0x18004e0ba  mov     qword ptr [rsp+8F8h+dwFlags], rax
0x18004e0bf  mov     rax, [rdi+48h]
0x18004e0c3  mov     qword ptr [rsp+8F8h+g], rax
0x18004e0c8  call    McTemplateU0zjzz_EventWriteTransfer
0x18004e0cd  mov     eax, 3EBh
0x18004e0d2  jmp     loc_18004E90A
0x18004e0d7  shl     rcx, 3
0x18004e0db  mov     edx, 0FFFFFFFFh
0x18004e0e0  mov     r15b, 40h ; '@'
0x18004e0e3  cmp     rcx, rdx
0x18004e0e6  ja      short loc_18004E0FE
0x18004e0e8  mov     ebx, ecx
0x18004e0ea  xor     edx, edx; dwFlags
0x18004e0ec  mov     r8d, ecx; dwBytes
0x18004e0ef  mov     rcx, cs:IPRouterHeap; hHeap
0x18004e0f6  call    cs:__imp_HeapAlloc
0x18004e0fc  jmp     short loc_18004E179
0x18004e0fe  mov     ebx, edx
0x18004e100  test    r15b, al
0x18004e103  jz      short loc_18004E177
0x18004e105  xor     eax, eax
0x18004e107  lea     rcx, [rsp+8F8h+var_838]
0x18004e10f  mov     r8d, edx
0x18004e112  mov     word ptr [rsp+8F8h+var_838], ax
0x18004e11a  lea     rdx, aCreatesocketsA; "CreateSockets: Arithmetic overflow erro"...
0x18004e121  mov     word ptr [rsp+8F8h+var_868], ax
0x18004e129  call    FormatRRASErrorString
0x18004e12e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18004e135  jz      short loc_18004E177
0x18004e137  lea     rax, [rdi+2B0h]
0x18004e13e  mov     rcx, r12
0x18004e141  test    rax, rax
0x18004e144  lea     r9, [rsp+8F8h+var_888]
0x18004e149  lea     r8, [rsp+8F8h+var_838]
0x18004e151  cmovnz  r9, rax
0x18004e155  lea     rdx, RasRtrMgrParamTraceError
0x18004e15c  lea     rax, [rsp+8F8h+var_868]
0x18004e164  mov     qword ptr [rsp+8F8h+dwFlags], rax
0x18004e169  mov     rax, [rdi+48h]
0x18004e16d  mov     qword ptr [rsp+8F8h+g], rax
0x18004e172  call    McTemplateU0zjzz_EventWriteTransfer
0x18004e177  xor     eax, eax
0x18004e179  mov     esi, 120h
0x18004e17e  mov     r14, rdi
0x18004e181  mov     [rsi+rdi], rax
0x18004e185  test    rax, rax
0x18004e188  jnz     loc_18004E211
0x18004e18e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18004e195  jz      short loc_18004E207
0x18004e197  mov     r8d, ebx
0x18004e19a  mov     word ptr [rsp+8F8h+var_838], ax
0x18004e1a2  lea     rdx, aCreatesocketsE_1; "CreateSockets: Error allocating %d byte"...
0x18004e1a9  mov     word ptr [rsp+8F8h+var_868], ax
0x18004e1b1  lea     rcx, [rsp+8F8h+var_838]
0x18004e1b9  call    FormatRRASErrorString
0x18004e1be  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18004e1c5  jz      short loc_18004E207
0x18004e1c7  lea     rax, [rdi+2B0h]
0x18004e1ce  mov     rcx, r12
0x18004e1d1  test    rax, rax
0x18004e1d4  lea     r9, [rsp+8F8h+var_888]
0x18004e1d9  lea     r8, [rsp+8F8h+var_838]
0x18004e1e1  cmovnz  r9, rax
0x18004e1e5  lea     rdx, RasRtrMgrParamTraceError
0x18004e1ec  lea     rax, [rsp+8F8h+var_868]
0x18004e1f4  mov     qword ptr [rsp+8F8h+dwFlags], rax
0x18004e1f9  mov     rax, [rdi+48h]
0x18004e1fd  mov     qword ptr [rsp+8F8h+g], rax
0x18004e202  call    McTemplateU0zjzz_EventWriteTransfer
0x18004e207  mov     eax, 8
0x18004e20c  jmp     loc_18004E90A
0x18004e211  xor     r12d, r12d
0x18004e214  xor     edx, edx
0x18004e216  cmp     [rdi+29Ch], edx
0x18004e21c  jbe     short loc_18004E234
0x18004e21e  mov     rax, [rsi+r14]
0x18004e222  mov     qword ptr [rax+rdx*8], 0FFFFFFFFFFFFFFFFh
0x18004e22a  inc     edx
0x18004e22c  cmp     edx, [rdi+29Ch]
0x18004e232  jb      short loc_18004E21E
0x18004e234  xor     r13d, r13d
0x18004e237  mov     ebx, 2
0x18004e23c  cmp     r13d, [rdi+29Ch]
0x18004e243  jnb     loc_18004E8B1
0x18004e249  mov     [rsp+8F8h+dwFlags], 14h; dwFlags
0x18004e251  lea     edx, [rbx+1]; type
0x18004e254  xor     r9d, r9d; lpProtocolInfo
0x18004e257  mov     [rsp+8F8h+g], 0; g
0x18004e25f  lea     r8d, [rbx-1]; protocol
0x18004e263  mov     ecx, ebx; af
0x18004e265  call    cs:__imp_WSASocketA
0x18004e26b  mov     rcx, [rdi+120h]
0x18004e272  mov     r15d, r13d
0x18004e275  mov     [rcx+r13*8], rax
0x18004e279  mov     rcx, [rsi+r14]
0x18004e27d  cmp     qword ptr [rcx+r13*8], 0FFFFFFFFFFFFFFFFh
0x18004e282  jnz     loc_18004E325
0x18004e288  call    cs:__imp_WSAGetLastError
0x18004e28e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18004e295  mov     r12d, eax
0x18004e298  jge     loc_18004E8A9
0x18004e29e  mov     r9, [rdi+48h]
0x18004e2a2  lea     rdx, aCreatesocketsC_1; "CreateSockets: Couldnt create socket nu"...
0x18004e2a9  xor     ecx, ecx
0x18004e2ab  mov     [rsp+8F8h+g], eax
0x18004e2af  mov     word ptr [rsp+8F8h+var_838], cx
0x18004e2b7  mov     r8d, r13d
0x18004e2ba  mov     word ptr [rsp+8F8h+var_868], cx
0x18004e2c2  lea     rcx, [rsp+8F8h+var_838]
0x18004e2ca  call    FormatRRASErrorString
0x18004e2cf  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18004e2d6  jge     loc_18004E8A9
0x18004e2dc  lea     rax, [rdi+2B0h]
0x18004e2e3  test    rax, rax
0x18004e2e6  lea     r9, [rsp+8F8h+var_888]
0x18004e2eb  lea     r8, [rsp+8F8h+var_838]
0x18004e2f3  cmovnz  r9, rax
0x18004e2f7  lea     rdx, RasRtrmgrParamTraceInfo
0x18004e2fe  lea     rax, [rsp+8F8h+var_868]
0x18004e306  mov     qword ptr [rsp+8F8h+dwFlags], rax
0x18004e30b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004e312  mov     rax, [rdi+48h]
0x18004e316  mov     qword ptr [rsp+8F8h+g], rax
0x18004e31b  call    McTemplateU0zjzz_EventWriteTransfer
0x18004e320  jmp     loc_18004E8A9
0x18004e325  mov     dword ptr [rsp+8F8h+optval], 1
0x18004e32d  lea     r9, [rsp+8F8h+optval]; optval
0x18004e332  mov     rcx, [rcx+r13*8]; s
0x18004e336  mov     edx, 0FFFFh; level
0x18004e33b  mov     r8d, 4; optname
0x18004e341  mov     [rsp+8F8h+g], 4; optlen
0x18004e349  call    cs:__imp_setsockopt
0x18004e34f  cmp     eax, 0FFFFFFFFh
0x18004e352  jnz     loc_18004E3DD
0x18004e358  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18004e35f  jge     short loc_18004E3DD
0x18004e361  xor     eax, eax
0x18004e363  mov     word ptr [rsp+8F8h+var_838], ax
0x18004e36b  mov     word ptr [rsp+8F8h+var_868], ax
0x18004e373  call    cs:__imp_WSAGetLastError
0x18004e379  mov     r8d, eax
0x18004e37c  lea     rdx, aCreatesocketsC_0; "CreateSockets: Couldnt set reuse option"...
0x18004e383  lea     rcx, [rsp+8F8h+var_838]
0x18004e38b  call    FormatRRASErrorString
0x18004e390  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18004e397  jge     short loc_18004E3DD
0x18004e399  lea     rax, [rdi+2B0h]
0x18004e3a0  test    rax, rax
0x18004e3a3  lea     r9, [rsp+8F8h+var_888]
0x18004e3a8  lea     r8, [rsp+8F8h+var_838]
0x18004e3b0  cmovnz  r9, rax
0x18004e3b4  lea     rdx, RasRtrmgrParamTraceInfo
0x18004e3bb  lea     rax, [rsp+8F8h+var_868]
0x18004e3c3  mov     qword ptr [rsp+8F8h+dwFlags], rax
0x18004e3c8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004e3cf  mov     rax, [rdi+48h]
0x18004e3d3  mov     qword ptr [rsp+8F8h+g], rax
0x18004e3d8  call    McTemplateU0zjzz_EventWriteTransfer
0x18004e3dd  mov     rcx, [rsi+r14]
0x18004e3e1  mov     r8d, 1; lNetworkEvents
0x18004e3e7  mov     rdx, cs:g_hRtrDiscSocketEvent; hEventObject
0x18004e3ee  mov     rcx, [rcx+r13*8]; s
0x18004e3f2  call    cs:__imp_WSAEventSelect
0x18004e3f8  cmp     eax, 0FFFFFFFFh
0x18004e3fb  jnz     short loc_18004E445
0x18004e3fd  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18004e404  jge     loc_18004E88F
0x18004e40a  mov     rbx, [rdi+48h]
0x18004e40e  xor     eax, eax
0x18004e410  mov     word ptr [rsp+8F8h+var_838], ax
0x18004e418  mov     word ptr [rsp+8F8h+var_868], ax
0x18004e420  call    cs:__imp_WSAGetLastError
0x18004e426  mov     r8, rbx
0x18004e429  lea     rdx, aCreatesocketsW; "CreateSockets: WSAEventSelect() failed "...
0x18004e430  mov     r9d, eax
0x18004e433  lea     rcx, [rsp+8F8h+var_838]
0x18004e43b  call    FormatRRASErrorString
0x18004e440  jmp     loc_18004E842
0x18004e445  mov     rax, [rdi+2C8h]
0x18004e44c  lea     rdx, [rsp+8F8h+name]; name
0x18004e454  mov     [rsp+8F8h+name.sa_family], bx
0x18004e45c  xor     r12d, r12d
0x18004e45f  imul    rbx, r15, 1Ch
0x18004e463  lea     r8d, [r12+10h]; namelen
0x18004e468  mov     ecx, [rbx+rax]
0x18004e46b  mov     dword ptr [rsp+8F8h+name.sa_data+2], ecx
0x18004e472  mov     rcx, [rsi+r14]
0x18004e476  mov     word ptr [rsp+8F8h+name.sa_data], r12w
0x18004e47f  mov     rcx, [rcx+r13*8]; s
0x18004e483  call    cs:__imp_bind
0x18004e489  cmp     eax, 0FFFFFFFFh
0x18004e48c  jnz     short loc_18004E501
0x18004e48e  call    cs:__imp_WSAGetLastError
0x18004e494  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18004e49b  mov     r12d, eax
0x18004e49e  jge     loc_18004E88F
0x18004e4a4  xor     eax, eax
0x18004e4a6  mov     dword ptr [rsp+8F8h+lpOverlapped], r12d
0x18004e4ab  mov     word ptr [rsp+8F8h+var_838], ax
0x18004e4b3  mov     word ptr [rsp+8F8h+var_868], ax
0x18004e4bb  mov     rax, [rdi+2C8h]
0x18004e4c2  movzx   ecx, byte ptr [rbx+rax+3]
0x18004e4c7  movzx   edx, byte ptr [rbx+rax+2]
0x18004e4cc  movzx   r9d, byte ptr [rbx+rax+1]
0x18004e4d2  movzx   r8d, byte ptr [rbx+rax]
0x18004e4d7  mov     rax, [rdi+48h]
0x18004e4db  mov     [rsp+8F8h+lpcbBytesReturned], rax
0x18004e4e0  mov     [rsp+8F8h+dwFlags], ecx
  ... truncated ...
```
