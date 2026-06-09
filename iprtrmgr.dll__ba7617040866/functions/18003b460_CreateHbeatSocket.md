# CreateHbeatSocket

- ea: `0x18003b460`
- end: `0x18003bb14`
- name: `CreateHbeatSocket`
- size: `1716`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003bc44`

## callees

- `0x180011790`
- `0x18003b460`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `WS2_32!WSAEventSelect` at `0x18003b800`
- `WS2_32!WSAEventSelect` at `0x18003b800`
- `WS2_32!WSASocketA` at `0x18003b652`
- `WS2_32!WSASocketA` at `0x18003b652`
- `WS2_32!__imp_bind` at `0x18003b8e4`
- `WS2_32!__imp_bind` at `0x18003b8e4`
- `WS2_32!__imp_closesocket` at `0x18003b895`
- `WS2_32!__imp_closesocket` at `0x18003b895`
- `WS2_32!__imp_inet_ntoa` at `0x18003b900`
- `WS2_32!__imp_inet_ntoa` at `0x18003b9a4`
- `WS2_32!__imp_inet_ntoa` at `0x18003ba3a`
- `WS2_32!__imp_inet_ntoa` at `0x18003b900`
- `WS2_32!__imp_inet_ntoa` at `0x18003b9a4`
- `WS2_32!__imp_inet_ntoa` at `0x18003ba3a`
- `WS2_32!__imp_setsockopt` at `0x18003b766`
- `WS2_32!__imp_setsockopt` at `0x18003b968`
- `WS2_32!__imp_setsockopt` at `0x18003b9fa`
- `WS2_32!__imp_setsockopt` at `0x18003b766`
- `WS2_32!__imp_setsockopt` at `0x18003b968`
- `WS2_32!__imp_setsockopt` at `0x18003b9fa`
- `WS2_32!__imp_WSAGetLastError` at `0x18003b668`
- `WS2_32!__imp_WSAGetLastError` at `0x18003b78a`
- `WS2_32!__imp_WSAGetLastError` at `0x18003b80f`
- `WS2_32!__imp_WSAGetLastError` at `0x18003b8ef`
- `WS2_32!__imp_WSAGetLastError` at `0x18003b973`
- `WS2_32!__imp_WSAGetLastError` at `0x18003ba09`
- `WS2_32!__imp_WSAGetLastError` at `0x18003b668`
- `WS2_32!__imp_WSAGetLastError` at `0x18003b78a`
- `WS2_32!__imp_WSAGetLastError` at `0x18003b80f`
- `WS2_32!__imp_WSAGetLastError` at `0x18003b8ef`
- `WS2_32!__imp_WSAGetLastError` at `0x18003b973`
- `WS2_32!__imp_WSAGetLastError` at `0x18003ba09`

## string_xrefs

- `0x18003b509`: `Entered: CreateHbeatSocket`
- `0x18003b558`: `CreateHbeatSocket: Can not activate heartbeat on %ws as it is not bound`
- `0x18003b5d6`: `Leaving: CreateHbeatSocket`
- `0x18003b707`: `Leaving: CreateHbeatSocket`
- `0x18003bab2`: `Leaving: CreateHbeatSocket`
- `0x18003b681`: `CreateHbeatSocket: Couldnt create socket on %ws. Error %d`
- `0x18003b793`: `CreateHbeatSocket: Couldnt set reuse option - continuing. Error %d`
- `0x18003b823`: `CreateHbeatSocket: WSAEventSelect() failed for socket on %ws.Error %d`
- `0x18003b912`: `CreateHbeatSocket: Couldnt bind to %hs on interface %ws. Error %d`
- `0x18003b9ad`: `CreateHbeatSocket: Couldnt enable mcast over %hs on %ws`
- `0x18003ba78`: `CreateHbeatSocket: Couldnt join %d.%d.%d.%d on socket over %hs on %ws`

## pseudocode

```c
__int64 __fastcall CreateHbeatSocket(__int64 a1)
{
  char v2; // al
  __int128 *v3; // r9
  __int64 v4; // r8
  __int128 *v5; // r9
  __int128 *v6; // r9
  int v8; // r8d
  int v9; // edx
  SOCKET v10; // rax
  unsigned int Error; // eax
  char v12; // cl
  unsigned int v13; // esi
  __int64 v14; // r8
  __int128 *v15; // r9
  __int128 *v16; // r9
  unsigned int v17; // eax
  __int128 *v18; // r9
  unsigned int v19; // eax
  __int64 v20; // r8
  __int64 *v21; // rdx
  __int128 *v22; // r9
  bool v23; // zf
  _DWORD *v24; // rax
  __int16 v25; // ax
  SOCKET v26; // rcx
  char *v27; // rax
  __int64 v28; // r9
  __int64 v29; // rbx
  char *v30; // rax
  __int64 v31; // rbx
  char *v32; // rax
  __int128 *v33; // r9
  GROUP g[2]; // [rsp+20h] [rbp-8A8h]
  GROUP ga[2]; // [rsp+20h] [rbp-8A8h]
  DWORD dwFlags[2]; // [rsp+28h] [rbp-8A0h]
  char optval[4]; // [rsp+44h] [rbp-884h] BYREF
  char v38[8]; // [rsp+48h] [rbp-880h] BYREF
  __int128 v39; // [rsp+50h] [rbp-878h] BYREF
  struct sockaddr name; // [rsp+60h] [rbp-868h] BYREF
  int v41; // [rsp+70h] [rbp-858h] BYREF
  __int128 v42; // [rsp+74h] [rbp-854h]
  __int128 v43; // [rsp+84h] [rbp-844h]
  int v44; // [rsp+94h] [rbp-834h]
  int v45; // [rsp+A0h] [rbp-828h] BYREF
  _BYTE v46[2044]; // [rsp+A4h] [rbp-824h] BYREF

  *(_DWORD *)optval = 0;
  *(_QWORD *)v38 = 0;
  v45 = 0;
  name = 0;
  memset_0(v46, 0, sizeof(v46));
  v41 = 0;
  v44 = 0;
  v2 = Microsoft_Windows_RRASEnableBits;
  v42 = 0;
  v43 = 0;
  v39 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v3 = &v39;
    LOWORD(v41) = 0;
    if ( a1 != -688 )
      LODWORD(v3) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: CreateHbeatSocket",
      (_DWORD)v3,
      *(_QWORD *)(a1 + 72),
      (__int64)&v41);
    v2 = Microsoft_Windows_RRASEnableBits;
  }
  if ( *(_DWORD *)(a1 + 512) )
  {
    if ( v2 < 0 )
    {
      v4 = *(_QWORD *)(a1 + 72);
      LOWORD(v45) = 0;
      LOWORD(v41) = 0;
      FormatRRASErrorString(&v45, L"CreateHbeatSocket: Can not activate heartbeat on %ws as it is not bound", v4);
      v2 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v5 = &v39;
        if ( a1 != -688 )
          LODWORD(v5) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v45,
          (_DWORD)v5,
          *(_QWORD *)(a1 + 72),
          (__int64)&v41);
        v2 = Microsoft_Windows_RRASEnableBits;
      }
    }
    if ( v2 < 0 )
    {
      v6 = &v39;
      LOWORD(v41) = 0;
      if ( a1 != -688 )
        LODWORD(v6) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)L"Leaving: CreateHbeatSocket",
        (_DWORD)v6,
        *(_QWORD *)(a1 + 72),
        (__int64)&v41);
    }
    return 1003;
  }
  *(_QWORD *)(a1 + 480) = -1;
  if ( *(_BYTE *)(a1 + 474) == 0xFF )
  {
    v8 = *(unsigned __int8 *)(a1 + 472);
    v9 = 3;
  }
  else
  {
    v8 = 17;
    v9 = 2;
  }
  v10 = WSASocketA(2, v9, v8, 0, 0, 0x14u);
  *(_QWORD *)(a1 + 480) = v10;
  if ( v10 == -1 )
  {
    Error = WSAGetLastError();
    v12 = Microsoft_Windows_RRASEnableBits;
    v13 = Error;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v14 = *(_QWORD *)(a1 + 72);
      LOWORD(v45) = 0;
      LOWORD(v41) = 0;
      FormatRRASErrorString(&v45, L"CreateHbeatSocket: Couldnt create socket on %ws. Error %d", v14, Error);
      v12 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v15 = &v39;
        if ( a1 != -688 )
          LODWORD(v15) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v45,
          (_DWORD)v15,
          *(_QWORD *)(a1 + 72),
          (__int64)&v41);
        v12 = Microsoft_Windows_RRASEnableBits;
      }
    }
    if ( v12 < 0 )
    {
      v16 = &v39;
      LOWORD(v41) = 0;
      if ( a1 != -688 )
        LODWORD(v16) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)L"Leaving: CreateHbeatSocket",
        (_DWORD)v16,
        *(_QWORD *)(a1 + 72),
        (__int64)&v41);
    }
    return v13;
  }
  *(_DWORD *)optval = 1;
  if ( setsockopt(v10, 0xFFFF, 4, optval, 4) == -1 && (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    LOWORD(v45) = 0;
    LOWORD(v41) = 0;
    v17 = WSAGetLastError();
    FormatRRASErrorString(&v45, L"CreateHbeatSocket: Couldnt set reuse option - continuing. Error %d", v17);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v18 = &v39;
      if ( a1 != -688 )
        LODWORD(v18) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrMgrParamTraceError,
        (unsigned int)&v45,
        (_DWORD)v18,
        *(_QWORD *)(a1 + 72),
        (__int64)&v41);
    }
  }
  if ( WSAEventSelect(*(_QWORD *)(a1 + 480), g_hMHbeatSocketEvent, 1) == -1 )
  {
    v19 = WSAGetLastError();
    v13 = v19;
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      goto LABEL_44;
    v20 = *(_QWORD *)(a1 + 72);
    LOWORD(v45) = 0;
    LOWORD(v41) = 0;
    FormatRRASErrorString(&v45, L"CreateHbeatSocket: WSAEventSelect() failed for socket on %ws.Error %d", v20, v19);
    goto LABEL_39;
  }
  v23 = *(_BYTE *)(a1 + 474) == 17;
  v24 = *(_DWORD **)(a1 + 712);
  name.sa_family = 2;
  *(_DWORD *)&name.sa_data[2] = *v24;
  if ( v23 )
    v25 = *(_WORD *)(a1 + 472);
  else
    v25 = 0;
  v26 = *(_QWORD *)(a1 + 480);
  *(_WORD *)name.sa_data = v25;
  if ( bind(v26, &name, 16) == -1 )
  {
    v13 = WSAGetLastError();
    v27 = inet_ntoa(**(struct in_addr **)(a1 + 712));
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
      goto LABEL_44;
    v28 = *(_QWORD *)(a1 + 72);
    g[0] = v13;
    LOWORD(v45) = 0;
    LOWORD(v41) = 0;
    FormatRRASErrorString(
      &v45,
      L"CreateHbeatSocket: Couldnt bind to %hs on interface %ws. Error %d",
      v27,
      v28,
      *(_QWORD *)g);
LABEL_39:
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v21 = RasRtrMgrParamTraceError;
LABEL_41:
      v22 = &v39;
      if ( a1 != -688 )
        LODWORD(v22) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (_DWORD)v21,
        (unsigned int)&v45,
        (_DWORD)v22,
        *(_QWORD *)(a1 + 72),
        (__int64)&v41);
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  *(_DWORD *)&name.sa_data[2] = **(_DWORD **)(a1 + 712);
  if ( setsockopt(*(_QWORD *)(a1 + 480), 0, 9, &name.sa_data[2], 4) == -1 )
  {
    v13 = WSAGetLastError();
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_44;
    v29 = *(_QWORD *)(a1 + 72);
    LOWORD(v45) = 0;
    LOWORD(v41) = 0;
    v30 = inet_ntoa(**(struct in_addr **)(a1 + 712));
    FormatRRASErrorString(&v45, L"CreateHbeatSocket: Couldnt enable mcast over %hs on %ws", v30, v29);
    goto LABEL_57;
  }
  *(_DWORD *)v38 = *(_DWORD *)(a1 + 468);
  *(_DWORD *)&v38[4] = **(_DWORD **)(a1 + 712);
  if ( setsockopt(*(_QWORD *)(a1 + 480), 0, 12, v38, 8) == -1 )
  {
    v13 = WSAGetLastError();
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_44;
    v31 = *(_QWORD *)(a1 + 72);
    LOWORD(v45) = 0;
    LOWORD(v41) = 0;
    v32 = inet_ntoa(**(struct in_addr **)(a1 + 712));
    dwFlags[0] = *(unsigned __int8 *)(a1 + 471);
    ga[0] = *(unsigned __int8 *)(a1 + 470);
    FormatRRASErrorString(
      &v45,
      L"CreateHbeatSocket: Couldnt join %d.%d.%d.%d on socket over %hs on %ws",
      *(unsigned __int8 *)(a1 + 468),
      *(unsigned __int8 *)(a1 + 469),
      *(_QWORD *)ga,
      *(_QWORD *)dwFlags,
      v32,
      v31);
LABEL_57:
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v21 = RasRtrmgrParamTraceInfo;
      goto LABEL_41;
    }
LABEL_44:
    closesocket(*(_QWORD *)(a1 + 480));
    *(_QWORD *)(a1 + 480) = -1;
    return v13;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v33 = &v39;
    LOWORD(v41) = 0;
    if ( a1 != -688 )
      LODWORD(v33) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Leaving: CreateHbeatSocket",
      (_DWORD)v33,
      *(_QWORD *)(a1 + 72),
      (__int64)&v41);
  }
  return 0;
}

```

## disassembly

```asm
0x18003b460  mov     [rsp+arg_8], rbx
0x18003b465  mov     [rsp+arg_10], rsi
0x18003b46a  push    rdi
0x18003b46b  push    r12
0x18003b46d  push    r15
0x18003b46f  sub     rsp, 8B0h
0x18003b476  mov     rax, cs:__security_cookie
0x18003b47d  xor     rax, rsp
0x18003b480  mov     [rsp+8C8h+var_28], rax
0x18003b488  mov     rdi, rcx
0x18003b48b  mov     dword ptr [rsp+8C8h+optval], 0
0x18003b493  xorps   xmm0, xmm0
0x18003b496  mov     qword ptr [rsp+8C8h+var_880], 0
0x18003b49f  xor     eax, eax
0x18003b4a1  lea     rcx, [rsp+8C8h+var_824]; void *
0x18003b4a9  xor     edx, edx; Val
0x18003b4ab  mov     [rsp+8C8h+var_828], eax
0x18003b4b2  mov     r8d, 7FCh; Size
0x18003b4b8  movups  xmmword ptr [rsp+8C8h+name.sa_family], xmm0
0x18003b4bd  call    memset_0
0x18003b4c2  xor     eax, eax
0x18003b4c4  lea     rbx, RasRtrmgrParamTraceInfo
0x18003b4cb  xorps   xmm0, xmm0
0x18003b4ce  mov     [rsp+8C8h+var_858], eax
0x18003b4d2  mov     [rsp+8C8h+var_834], eax
0x18003b4d9  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003b4e0  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18003b4e7  movups  [rsp+8C8h+var_854], xmm0
0x18003b4ec  movups  [rsp+8C8h+var_844], xmm0
0x18003b4f4  movups  [rsp+8C8h+var_878], xmm0
0x18003b4f9  test    al, 80h
0x18003b4fb  jz      short loc_18003B543
0x18003b4fd  xor     eax, eax
0x18003b4ff  lea     r9, [rsp+8C8h+var_878]
0x18003b504  mov     word ptr [rsp+8C8h+var_858], ax
0x18003b509  lea     r8, aEnteredCreateh; "Entered: CreateHbeatSocket"
0x18003b510  lea     rax, [rdi+2B0h]
0x18003b517  mov     rdx, rbx
0x18003b51a  test    rax, rax
0x18003b51d  mov     rcx, r12
0x18003b520  cmovnz  r9, rax
0x18003b524  lea     rax, [rsp+8C8h+var_858]
0x18003b529  mov     qword ptr [rsp+8C8h+dwFlags], rax
0x18003b52e  mov     rax, [rdi+48h]
0x18003b532  mov     qword ptr [rsp+8C8h+g], rax
0x18003b537  call    McTemplateU0zjzz_EventWriteTransfer
0x18003b53c  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18003b543  cmp     dword ptr [rdi+200h], 0
0x18003b54a  jz      loc_18003B613
0x18003b550  test    al, al
0x18003b552  jns     short loc_18003B5C6
0x18003b554  mov     r8, [rdi+48h]
0x18003b558  lea     rdx, aCreatehbeatsoc_4; "CreateHbeatSocket: Can not activate hea"...
0x18003b55f  xor     eax, eax
0x18003b561  lea     rcx, [rsp+8C8h+var_828]
0x18003b569  mov     word ptr [rsp+8C8h+var_828], ax
0x18003b571  mov     word ptr [rsp+8C8h+var_858], ax
0x18003b576  call    FormatRRASErrorString
0x18003b57b  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18003b582  test    al, al
0x18003b584  jns     short loc_18003B5C6
0x18003b586  lea     rax, [rdi+2B0h]
0x18003b58d  mov     rdx, rbx
0x18003b590  test    rax, rax
0x18003b593  lea     r9, [rsp+8C8h+var_878]
0x18003b598  lea     r8, [rsp+8C8h+var_828]
0x18003b5a0  mov     rcx, r12
0x18003b5a3  cmovnz  r9, rax
0x18003b5a7  lea     rax, [rsp+8C8h+var_858]
0x18003b5ac  mov     qword ptr [rsp+8C8h+dwFlags], rax
0x18003b5b1  mov     rax, [rdi+48h]
0x18003b5b5  mov     qword ptr [rsp+8C8h+g], rax
0x18003b5ba  call    McTemplateU0zjzz_EventWriteTransfer
0x18003b5bf  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18003b5c6  test    al, 80h
0x18003b5c8  jz      short loc_18003B609
0x18003b5ca  xor     eax, eax
0x18003b5cc  lea     r9, [rsp+8C8h+var_878]
0x18003b5d1  mov     word ptr [rsp+8C8h+var_858], ax
0x18003b5d6  lea     r8, aLeavingCreateh; "Leaving: CreateHbeatSocket"
0x18003b5dd  lea     rax, [rdi+2B0h]
0x18003b5e4  mov     rdx, rbx
0x18003b5e7  test    rax, rax
0x18003b5ea  mov     rcx, r12
0x18003b5ed  cmovnz  r9, rax
0x18003b5f1  lea     rax, [rsp+8C8h+var_858]
0x18003b5f6  mov     qword ptr [rsp+8C8h+dwFlags], rax
0x18003b5fb  mov     rax, [rdi+48h]
0x18003b5ff  mov     qword ptr [rsp+8C8h+g], rax
0x18003b604  call    McTemplateU0zjzz_EventWriteTransfer
0x18003b609  mov     eax, 3EBh
0x18003b60e  jmp     loc_18003BAEB
0x18003b613  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003b617  mov     [rsp+8C8h+dwFlags], 14h; dwFlags
0x18003b61f  xor     r9d, r9d; lpProtocolInfo
0x18003b622  mov     [rdi+1E0h], r15
0x18003b629  cmp     byte ptr [rdi+1DAh], 0FFh
0x18003b630  mov     [rsp+8C8h+g], r9d; g
0x18003b635  lea     esi, [r15+3]
0x18003b639  mov     ecx, esi; af
0x18003b63b  jnz     short loc_18003B64A
0x18003b63d  movzx   r8d, byte ptr [rdi+1D8h]
0x18003b645  lea     edx, [rsi+1]
0x18003b648  jmp     short loc_18003B652
0x18003b64a  mov     r8d, 11h; protocol
0x18003b650  mov     edx, esi; type
0x18003b652  call    cs:__imp_WSASocketA
0x18003b658  mov     [rdi+1E0h], rax
0x18003b65f  cmp     rax, r15
0x18003b662  jnz     loc_18003B745
0x18003b668  call    cs:__imp_WSAGetLastError
0x18003b66e  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18003b675  mov     bl, 40h ; '@'
0x18003b677  mov     esi, eax
0x18003b679  test    bl, cl
0x18003b67b  jz      short loc_18003B6F6
0x18003b67d  mov     r8, [rdi+48h]
0x18003b681  lea     rdx, aCreatehbeatsoc_3; "CreateHbeatSocket: Couldnt create socke"...
0x18003b688  xor     ecx, ecx
0x18003b68a  mov     r9d, eax
0x18003b68d  mov     word ptr [rsp+8C8h+var_828], cx
0x18003b695  mov     word ptr [rsp+8C8h+var_858], cx
0x18003b69a  lea     rcx, [rsp+8C8h+var_828]
0x18003b6a2  call    FormatRRASErrorString
0x18003b6a7  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18003b6ae  test    bl, cl
0x18003b6b0  jz      short loc_18003B6F6
0x18003b6b2  lea     rax, [rdi+2B0h]
0x18003b6b9  mov     rcx, r12
0x18003b6bc  test    rax, rax
0x18003b6bf  lea     r9, [rsp+8C8h+var_878]
0x18003b6c4  lea     r8, [rsp+8C8h+var_828]
0x18003b6cc  cmovnz  r9, rax
0x18003b6d0  lea     rdx, RasRtrMgrParamTraceError
0x18003b6d7  lea     rax, [rsp+8C8h+var_858]
0x18003b6dc  mov     qword ptr [rsp+8C8h+dwFlags], rax
0x18003b6e1  mov     rax, [rdi+48h]
0x18003b6e5  mov     qword ptr [rsp+8C8h+g], rax
0x18003b6ea  call    McTemplateU0zjzz_EventWriteTransfer
0x18003b6ef  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18003b6f6  test    cl, 80h
0x18003b6f9  jz      short loc_18003B73E
0x18003b6fb  xor     eax, eax
0x18003b6fd  lea     r9, [rsp+8C8h+var_878]
0x18003b702  mov     word ptr [rsp+8C8h+var_858], ax
0x18003b707  lea     r8, aLeavingCreateh; "Leaving: CreateHbeatSocket"
0x18003b70e  lea     rax, [rdi+2B0h]
0x18003b715  mov     rcx, r12
0x18003b718  test    rax, rax
0x18003b71b  lea     rdx, RasRtrmgrParamTraceInfo
0x18003b722  cmovnz  r9, rax
0x18003b726  lea     rax, [rsp+8C8h+var_858]
0x18003b72b  mov     qword ptr [rsp+8C8h+dwFlags], rax
0x18003b730  mov     rax, [rdi+48h]
0x18003b734  mov     qword ptr [rsp+8C8h+g], rax
0x18003b739  call    McTemplateU0zjzz_EventWriteTransfer
0x18003b73e  mov     eax, esi
0x18003b740  jmp     loc_18003BAEB
0x18003b745  mov     ecx, 4
0x18003b74a  mov     dword ptr [rsp+8C8h+optval], 1
0x18003b752  mov     [rsp+8C8h+g], ecx; optlen
0x18003b756  lea     r9, [rsp+8C8h+optval]; optval
0x18003b75b  mov     r8d, ecx; optname
0x18003b75e  mov     edx, 0FFFFh; level
0x18003b763  mov     rcx, rax; s
0x18003b766  call    cs:__imp_setsockopt
0x18003b76c  mov     bl, 40h ; '@'
0x18003b76e  cmp     eax, r15d
0x18003b771  jnz     short loc_18003B7EC
0x18003b773  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18003b779  jz      short loc_18003B7EC
0x18003b77b  xor     eax, eax
0x18003b77d  mov     word ptr [rsp+8C8h+var_828], ax
0x18003b785  mov     word ptr [rsp+8C8h+var_858], ax
0x18003b78a  call    cs:__imp_WSAGetLastError
0x18003b790  mov     r8d, eax
0x18003b793  lea     rdx, aCreatehbeatsoc_1; "CreateHbeatSocket: Couldnt set reuse op"...
0x18003b79a  lea     rcx, [rsp+8C8h+var_828]
0x18003b7a2  call    FormatRRASErrorString
0x18003b7a7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18003b7ad  jz      short loc_18003B7EC
0x18003b7af  lea     rax, [rdi+2B0h]
0x18003b7b6  mov     rcx, r12
0x18003b7b9  test    rax, rax
0x18003b7bc  lea     r9, [rsp+8C8h+var_878]
0x18003b7c1  lea     r8, [rsp+8C8h+var_828]
0x18003b7c9  cmovnz  r9, rax
0x18003b7cd  lea     rdx, RasRtrMgrParamTraceError
0x18003b7d4  lea     rax, [rsp+8C8h+var_858]
0x18003b7d9  mov     qword ptr [rsp+8C8h+dwFlags], rax
0x18003b7de  mov     rax, [rdi+48h]
0x18003b7e2  mov     qword ptr [rsp+8C8h+g], rax
0x18003b7e7  call    McTemplateU0zjzz_EventWriteTransfer
0x18003b7ec  mov     rdx, cs:g_hMHbeatSocketEvent; hEventObject
0x18003b7f3  mov     r8d, 1; lNetworkEvents
0x18003b7f9  mov     rcx, [rdi+1E0h]; s
0x18003b800  call    cs:__imp_WSAEventSelect
0x18003b806  cmp     eax, r15d
0x18003b809  jnz     loc_18003B8A7
0x18003b80f  call    cs:__imp_WSAGetLastError
0x18003b815  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18003b81b  mov     esi, eax
0x18003b81d  jz      short loc_18003B88E
0x18003b81f  mov     r8, [rdi+48h]
0x18003b823  lea     rdx, aCreatehbeatsoc_0; "CreateHbeatSocket: WSAEventSelect() fai"...
0x18003b82a  xor     ecx, ecx
0x18003b82c  mov     r9d, eax
0x18003b82f  mov     word ptr [rsp+8C8h+var_828], cx
0x18003b837  mov     word ptr [rsp+8C8h+var_858], cx
0x18003b83c  lea     rcx, [rsp+8C8h+var_828]
0x18003b844  call    FormatRRASErrorString
0x18003b849  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18003b84f  jz      short loc_18003B88E
0x18003b851  lea     rdx, RasRtrMgrParamTraceError
0x18003b858  lea     rax, [rdi+2B0h]
0x18003b85f  mov     rcx, r12
0x18003b862  test    rax, rax
0x18003b865  lea     r9, [rsp+8C8h+var_878]
0x18003b86a  lea     r8, [rsp+8C8h+var_828]
0x18003b872  cmovnz  r9, rax
0x18003b876  lea     rax, [rsp+8C8h+var_858]
0x18003b87b  mov     qword ptr [rsp+8C8h+dwFlags], rax
0x18003b880  mov     rax, [rdi+48h]
0x18003b884  mov     qword ptr [rsp+8C8h+g], rax
0x18003b889  call    McTemplateU0zjzz_EventWriteTransfer
0x18003b88e  mov     rcx, [rdi+1E0h]; s
0x18003b895  call    cs:__imp_closesocket
0x18003b89b  mov     [rdi+1E0h], r15
0x18003b8a2  jmp     loc_18003B73E
0x18003b8a7  cmp     byte ptr [rdi+1DAh], 11h
0x18003b8ae  mov     rax, [rdi+2C8h]
0x18003b8b5  mov     [rsp+8C8h+name.sa_family], si
0x18003b8ba  mov     ecx, [rax]
0x18003b8bc  mov     dword ptr [rsp+8C8h+name.sa_data+2], ecx
0x18003b8c0  jnz     short loc_18003B8CB
0x18003b8c2  movzx   eax, word ptr [rdi+1D8h]
0x18003b8c9  jmp     short loc_18003B8CD
0x18003b8cb  xor     eax, eax
0x18003b8cd  mov     rcx, [rdi+1E0h]; s
0x18003b8d4  lea     rdx, [rsp+8C8h+name]; name
0x18003b8d9  mov     r8d, 10h; namelen
0x18003b8df  mov     word ptr [rsp+8C8h+name.sa_data], ax
0x18003b8e4  call    cs:__imp_bind
0x18003b8ea  cmp     eax, r15d
0x18003b8ed  jnz     short loc_18003B941
0x18003b8ef  call    cs:__imp_WSAGetLastError
0x18003b8f5  mov     rcx, [rdi+2C8h]
0x18003b8fc  mov     esi, eax
0x18003b8fe  mov     ecx, [rcx]; in
0x18003b900  call    cs:__imp_inet_ntoa
0x18003b906  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18003b90c  jz      short loc_18003B88E
0x18003b90e  mov     r9, [rdi+48h]
0x18003b912  lea     rdx, aCreatehbeatsoc_5; "CreateHbeatSocket: Couldnt bind to %hs "...
0x18003b919  xor     ecx, ecx
0x18003b91b  mov     [rsp+8C8h+g], esi
0x18003b91f  mov     word ptr [rsp+8C8h+var_828], cx
0x18003b927  mov     r8, rax
0x18003b92a  mov     word ptr [rsp+8C8h+var_858], cx
0x18003b92f  lea     rcx, [rsp+8C8h+var_828]
0x18003b937  call    FormatRRASErrorString
0x18003b93c  jmp     loc_18003B849
0x18003b941  mov     rax, [rdi+2C8h]
0x18003b948  lea     r9, [rsp+8C8h+name.sa_data+2]; optval
0x18003b94d  xor     edx, edx; level
0x18003b94f  mov     [rsp+8C8h+g], 4; optlen
0x18003b957  mov     ecx, [rax]
0x18003b959  mov     dword ptr [rsp+8C8h+name.sa_data+2], ecx
0x18003b95d  lea     r8d, [rdx+9]; optname
0x18003b961  mov     rcx, [rdi+1E0h]; s
0x18003b968  call    cs:__imp_setsockopt
0x18003b96e  cmp     eax, r15d
0x18003b971  jnz     short loc_18003B9C9
0x18003b973  call    cs:__imp_WSAGetLastError
0x18003b979  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18003b980  mov     esi, eax
0x18003b982  jge     loc_18003B88E
0x18003b988  mov     rbx, [rdi+48h]
0x18003b98c  xor     ecx, ecx
0x18003b98e  mov     word ptr [rsp+8C8h+var_828], cx
0x18003b996  mov     word ptr [rsp+8C8h+var_858], cx
0x18003b99b  mov     rcx, [rdi+2C8h]
0x18003b9a2  mov     ecx, [rcx]; in
0x18003b9a4  call    cs:__imp_inet_ntoa
0x18003b9aa  mov     r9, rbx
0x18003b9ad  lea     rdx, aCreatehbeatsoc; "CreateHbeatSocket: Couldnt enable mcast"...
0x18003b9b4  mov     r8, rax
0x18003b9b7  lea     rcx, [rsp+8C8h+var_828]
0x18003b9bf  call    FormatRRASErrorString
0x18003b9c4  jmp     loc_18003BA84
0x18003b9c9  mov     eax, [rdi+1D4h]
0x18003b9cf  lea     r9, [rsp+8C8h+var_880]; optval
0x18003b9d4  mov     dword ptr [rsp+8C8h+var_880], eax
0x18003b9d8  xor     edx, edx; level
0x18003b9da  mov     rax, [rdi+2C8h]
0x18003b9e1  mov     [rsp+8C8h+g], 8; optlen
0x18003b9e9  lea     r8d, [rdx+0Ch]; optname
0x18003b9ed  mov     ecx, [rax]
0x18003b9ef  mov     dword ptr [rsp+8C8h+var_880+4], ecx
0x18003b9f3  mov     rcx, [rdi+1E0h]; s
  ... truncated ...
```
