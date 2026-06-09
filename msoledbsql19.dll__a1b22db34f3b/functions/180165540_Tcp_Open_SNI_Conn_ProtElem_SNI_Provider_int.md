# Tcp::Open(SNI_Conn *,ProtElem *,SNI_Provider * *,int)

- ea: `0x180165540`
- end: `0x18016624f`
- name: `?Open@Tcp@@SAKPEAVSNI_Conn@@PEAVProtElem@@PEAPEAVSNI_Provider@@H@Z`
- size: `3343`
- prototype: `unsigned int __fastcall(struct SNI_Conn *, struct ProtElem *, struct SNI_Provider **, int)`
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180157780`

## callees

- `0x180001f70`
- `0x180002e50`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003150`
- `0x180003d80`
- `0x18013532c`
- `0x18015a6f0`
- `0x18015a880`
- `0x180162ff0`
- `0x180165540`
- `0x180166320`
- `0x180166550`
- `0x180166740`
- `0x180166b20`
- `0x180166fb0`
- `0x18017ec20`
- `0x18017ed20`
- `0x18017f0e0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1801655e4`
- `KERNEL32!GetTickCount` at `0x180165b02`
- `KERNEL32!GetTickCount` at `0x180165bd1`
- `KERNEL32!GetTickCount` at `0x180165c44`
- `KERNEL32!GetTickCount` at `0x1801655e4`
- `KERNEL32!GetTickCount` at `0x180165b02`
- `KERNEL32!GetTickCount` at `0x180165bd1`
- `KERNEL32!GetTickCount` at `0x180165c44`
- `WS2_32!GetAddrInfoW` at `0x18016587a`
- `WS2_32!GetAddrInfoW` at `0x1801658ba`
- `WS2_32!GetAddrInfoW` at `0x18016587a`
- `WS2_32!GetAddrInfoW` at `0x1801658ba`
- `WS2_32!FreeAddrInfoW` at `0x180165937`
- `WS2_32!FreeAddrInfoW` at `0x180165d25`
- `WS2_32!FreeAddrInfoW` at `0x180165937`
- `WS2_32!FreeAddrInfoW` at `0x180165d25`
- `WS2_32!__imp_closesocket` at `0x180165960`
- `WS2_32!__imp_closesocket` at `0x180165960`
- `WS2_32!__imp_getpeername` at `0x180165edc`
- `WS2_32!__imp_getpeername` at `0x180165edc`
- `WS2_32!__imp_getsockname` at `0x180165fe4`
- `WS2_32!__imp_getsockname` at `0x180165fe4`
- `WS2_32!__imp_ioctlsocket` at `0x180166144`
- `WS2_32!__imp_ioctlsocket` at `0x180166144`
- `WS2_32!__imp_setsockopt` at `0x180165e13`
- `WS2_32!__imp_setsockopt` at `0x180165e13`
- `WS2_32!__imp_shutdown` at `0x180165956`
- `WS2_32!__imp_shutdown` at `0x180165956`
- `WS2_32!__imp_WSAGetLastError` at `0x180165884`
- `WS2_32!__imp_WSAGetLastError` at `0x1801658c4`
- `WS2_32!__imp_WSAGetLastError` at `0x180165e1e`
- `WS2_32!__imp_WSAGetLastError` at `0x180165ee6`
- `WS2_32!__imp_WSAGetLastError` at `0x180165fee`
- `WS2_32!__imp_WSAGetLastError` at `0x18016614f`
- `WS2_32!__imp_WSAGetLastError` at `0x180165884`
- `WS2_32!__imp_WSAGetLastError` at `0x1801658c4`
- `WS2_32!__imp_WSAGetLastError` at `0x180165e1e`
- `WS2_32!__imp_WSAGetLastError` at `0x180165ee6`
- `WS2_32!__imp_WSAGetLastError` at `0x180165fee`
- `WS2_32!__imp_WSAGetLastError` at `0x18016614f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Tcp::Open(struct SNI_Conn *a1, WCHAR *a2, struct SNI_Provider **a3, signed int a4)
{
  signed int v7; // ebx
  SNI::detail::Transport *v8; // rax
  SNI::detail::Transport *v9; // r15
  __int64 v10; // rdi
  void (__fastcall ***v11)(_QWORD, __int64); // rcx
  unsigned int Error; // edi
  unsigned int v13; // ebx
  wchar_t *v14; // r8
  __int64 v15; // rdx
  char *v16; // rcx
  __int64 v17; // rdx
  SOCKET v18; // rcx
  char v20; // al
  unsigned int v21; // edx
  PADDRINFOW i; // rax
  int ai_family; // ecx
  unsigned int v24; // ecx
  int *v25; // rax
  unsigned int v26; // r12d
  PADDRINFOW v27; // rsi
  int v28; // eax
  __int64 v29; // r9
  const struct addrinfoW *v30; // rdi
  unsigned int v31; // ebx
  signed int v32; // eax
  DWORD TickCount; // eax
  unsigned int v34; // esi
  DWORD v35; // eax
  __int64 v36; // r9
  SOCKET v37; // rcx
  bool v38; // [rsp+30h] [rbp-D0h]
  int v39; // [rsp+38h] [rbp-C8h] BYREF
  int v40; // [rsp+3Ch] [rbp-C4h]
  struct SNI_Provider **v41; // [rsp+40h] [rbp-C0h]
  __int64 v42; // [rsp+48h] [rbp-B8h]
  struct SNI_Conn *v43; // [rsp+50h] [rbp-B0h]
  PADDRINFOW ppResult; // [rsp+58h] [rbp-A8h] BYREF
  char optval[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v46; // [rsp+64h] [rbp-9Ch] BYREF
  int namelen; // [rsp+68h] [rbp-98h] BYREF
  u_long argp[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v49; // [rsp+78h] [rbp-88h] BYREF
  ADDRINFOW pHints; // [rsp+80h] [rbp-80h] BYREF
  struct sockaddr name; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v52; // [rsp+C0h] [rbp-40h]
  __int128 v53; // [rsp+D0h] [rbp-30h]
  __int128 v54; // [rsp+E0h] [rbp-20h]
  __int128 v55; // [rsp+F0h] [rbp-10h]
  __int128 v56; // [rsp+100h] [rbp+0h]
  __int128 v57; // [rsp+110h] [rbp+10h]
  __int128 v58; // [rsp+120h] [rbp+20h]
  struct sockaddr v59; // [rsp+130h] [rbp+30h] BYREF
  __int128 v60; // [rsp+140h] [rbp+40h]
  __int128 v61; // [rsp+150h] [rbp+50h]
  __int128 v62; // [rsp+160h] [rbp+60h]
  __int128 v63; // [rsp+170h] [rbp+70h]
  __int128 v64; // [rsp+180h] [rbp+80h]
  __int128 v65; // [rsp+190h] [rbp+90h]
  __int128 v66; // [rsp+1A0h] [rbp+A0h]

  v41 = a3;
  v43 = a1;
  v49 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266A08[0] )
    bidScopeEnterW(&v49, off_180266A08[0], a1, a2);
  v42 = 0;
  ppResult = 0;
  memset(&pHints, 0, sizeof(pHints));
  *(_DWORD *)optval = GetTickCount();
  v7 = a4;
  v8 = (SNI::detail::Transport *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(
                                   gpmo,
                                   352);
  v9 = v8;
  *(_QWORD *)argp = v8;
  if ( v8 )
  {
    SNI::detail::Transport::Transport(v8, a1);
    *(_QWORD *)v9 = &Tcp::`vftable';
    *((_QWORD *)v9 + 8) = -1;
    *((_QWORD *)v9 + 9) = 0;
    *((_WORD *)v9 + 40) = 0;
    *(_OWORD *)((char *)v9 + 84) = 0;
    *(_OWORD *)((char *)v9 + 100) = 0;
    *(_OWORD *)((char *)v9 + 116) = 0;
    *(_OWORD *)((char *)v9 + 132) = 0;
    *(_OWORD *)((char *)v9 + 148) = 0;
    *(_OWORD *)((char *)v9 + 164) = 0;
    *(_QWORD *)((char *)v9 + 180) = 0;
    *(_OWORD *)((char *)v9 + 188) = 0;
    *(_OWORD *)((char *)v9 + 204) = 0;
    *(_OWORD *)((char *)v9 + 220) = 0;
    *(_OWORD *)((char *)v9 + 236) = 0;
    *(_OWORD *)((char *)v9 + 252) = 0;
    *(_OWORD *)((char *)v9 + 268) = 0;
    *(_QWORD *)((char *)v9 + 284) = 0;
    *((_DWORD *)v9 + 73) = 0;
    *((_QWORD *)v9 + 37) = 0;
    *((_DWORD *)v9 + 76) = 0;
    *((_QWORD *)v9 + 39) = 0;
    *((_QWORD *)v9 + 40) = 0;
    *((_QWORD *)v9 + 41) = 0;
    *((_DWORD *)v9 + 84) = 0;
    *((_QWORD *)v9 + 43) = 0;
    *((_DWORD *)v9 + 6) = 6;
    v10 = (*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 24);
    *(_QWORD *)argp = v10;
    if ( v10 )
    {
      *(_QWORD *)v10 = &CCriticalSectionNT_SNI::`vftable';
      *(_BYTE *)(v10 + 8) = 0;
      *(_QWORD *)(v10 + 16) = 0;
      *((_QWORD *)v9 + 9) = v10;
      if ( (unsigned int)MPInitializeCriticalSectionAndSpinCount((struct CCriticalSection **)(v10 + 16)) )
      {
        *(_BYTE *)(v10 + 8) = 1;
LABEL_11:
        *((_DWORD *)v9 + 11) = bidObtainItemIDA(off_180262B30[0], v9, *((int *)a1 + 12));
        *(_QWORD *)v9 = &TcpWSA::`vftable';
        goto LABEL_13;
      }
      v11 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v9 + 9);
      if ( v11 )
        (**v11)(v11, 1);
    }
    *((_QWORD *)v9 + 9) = 0;
    goto LABEL_11;
  }
  v9 = 0;
LABEL_13:
  if ( !v9 )
  {
    Error = 14;
    if ( (bidGblFlags & 2) != 0 && off_1802646E8[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(off_1802613A0[0], 2915328, off_1802646E8[0], 6);
    }
    SNISetLastError(6, 14, 50100);
    goto LABEL_36;
  }
  Error = (*(__int64 (__fastcall **)(SNI::detail::Transport *))(*(_QWORD *)v9 + 56LL))(v9);
  if ( Error )
  {
    if ( (bidGblFlags & 2) != 0 && off_1802646F0[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(off_1802613A8[0], 2923520, off_1802646F0[0], 6);
    }
    SNISetLastError(6, Error, 50100);
    goto LABEL_36;
  }
  pHints.ai_socktype = 1;
  Error = 0;
  if ( GetAddrInfoW(a2 + 4, a2 + 772, &pHints, &ppResult) )
    Error = WSAGetLastError();
  if ( Error )
  {
    if ( Error != 11001 )
    {
      v13 = 50100;
      if ( (bidGblFlags & 2) == 0 || !off_180264700[0] )
        goto LABEL_34;
      SniErrorIdFromStringId(0xC3B4u);
      v14 = off_180264700[0];
      v15 = 2953216;
      v16 = off_1802613B8[0];
      goto LABEL_33;
    }
    pHints.ai_flags |= 4u;
    Error = 0;
    if ( GetAddrInfoW(a2 + 4, a2 + 772, &pHints, &ppResult) )
      Error = WSAGetLastError();
    if ( Error )
    {
      v13 = 50100;
      if ( (bidGblFlags & 2) == 0 || !off_1802646F8[0] )
        goto LABEL_34;
      SniErrorIdFromStringId(0xC3B4u);
      v14 = off_1802646F8[0];
      v15 = 2947072;
      v16 = off_1802613B0[0];
LABEL_33:
      bidTraceW(v16, v15, v14, 6);
LABEL_34:
      v17 = Error;
LABEL_35:
      SNISetLastError(6, v17, v13);
LABEL_36:
      if ( ppResult )
      {
        FreeAddrInfoW(ppResult);
        ppResult = 0;
      }
      if ( v9 )
      {
        v18 = *((_QWORD *)v9 + 8);
        if ( v18 != -1 )
        {
          shutdown(v18, 1);
          closesocket(*((_QWORD *)v9 + 8));
        }
        (**(void (__fastcall ***)(SNI::detail::Transport *, __int64))v9)(v9, 1);
      }
      *v41 = 0;
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264770[0] )
        bidTraceW(off_180261428[0], 3232768, off_180264770[0], Error);
      LODWORD(v42) = Error;
      goto LABEL_46;
    }
  }
  if ( !*((_BYTE *)a2 + 2056) )
  {
    v20 = *((_BYTE *)a2 + 2057);
    if ( v20 == 1 )
    {
      v21 = 0;
      for ( i = ppResult; i; i = i->ai_next )
      {
        ai_family = i->ai_family;
        if ( ai_family == 2 || ai_family == 23 )
          ++v21;
      }
      v38 = v21 > 0x40;
      v39 = 2;
      v40 = 23;
      if ( v21 > 0x40 )
      {
        a4 = *((_DWORD *)a2 + 515);
        v38 = v21 > 0x40;
      }
LABEL_61:
      v24 = 0;
      namelen = 0;
      v25 = &v39;
      *(_QWORD *)argp = &v39;
      v26 = -1;
      while ( 1 )
      {
        v27 = ppResult;
        if ( ppResult )
          break;
LABEL_77:
        namelen = ++v24;
        *(_QWORD *)argp = ++v25;
        if ( v24 >= 2 )
          goto LABEL_104;
      }
      v28 = *v25;
      v46 = v28;
      while ( 1 )
      {
        if ( v27->ai_family == v28 )
        {
          if ( a4 != -1 )
          {
            v7 = a4 + *(_DWORD *)optval - GetTickCount();
            if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264708[0] )
              bidTraceW(off_1802613C0[0], 3010560, off_180264708[0], (unsigned int)v7);
            if ( v7 <= 0 || v7 > a4 )
            {
              if ( !Error )
                Error = 258;
              goto LABEL_104;
            }
          }
          Error = Tcp::SocketOpenSync(v9, v27, v7, (struct ProtElem *)a2);
          if ( !Error )
          {
            if ( a4 != -1 )
            {
              v29 = a4 + *(_DWORD *)optval - GetTickCount();
              if ( (bidGblFlags & 0x20002) == 0x20002 )
              {
                if ( off_180264710[0] )
                  bidTraceW(off_1802613C8[0], 3038208, off_180264710[0], v29);
              }
            }
            goto LABEL_104;
          }
          if ( *((_BYTE *)a2 + 2057) == 1 && !v38 )
            goto LABEL_104;
          v28 = v46;
        }
        v27 = v27->ai_next;
        if ( !v27 )
        {
          v25 = *(int **)argp;
          v24 = namelen;
          goto LABEL_77;
        }
      }
    }
    if ( v20 != 2 )
    {
      v39 = 2;
      v40 = 23;
      v38 = 0;
      goto LABEL_61;
    }
  }
  v30 = ppResult;
  v31 = a4;
  v26 = -1;
  if ( a4 == -1 )
  {
    v34 = *(_DWORD *)optval;
  }
  else
  {
    v32 = 0;
    if ( a4 >= 0 )
      v32 = a4;
    a4 = v32;
    TickCount = GetTickCount();
    v34 = *(_DWORD *)optval;
    v35 = TickCount - *(_DWORD *)optval;
    if ( a4 < v35 )
    {
      v31 = 1500;
    }
    else
    {
      v31 = a4 - v35;
      if ( a4 - v35 < 0x5DC )
        v31 = 1500;
    }
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1802646D8[0] )
      bidTraceW(off_180261390[0], 2865152, off_1802646D8[0], v31);
  }
  Error = Tcp::SocketOpenParallel(v9, v30, v31, (struct ProtElem *)a2);
  if ( Error )
    goto LABEL_36;
  if ( a4 != -1 && (bidGblFlags & 0x20002) == 0x20002 )
  {
    v36 = Tcp::ComputeNewTimeout(a4, v34);
    if ( (bidGblFlags & 0x20002) == 0x20002 )
    {
      if ( off_1802646E0[0] )
        bidTraceW(off_180261398[0], 2882560, off_1802646E0[0], v36);
    }
  }
  Error = 0;
LABEL_104:
  FreeAddrInfoW(ppResult);
  ppResult = 0;
  v37 = *((_QWORD *)v9 + 8);
  if ( v37 == -1 )
  {
    if ( Error )
    {
      v13 = 50100;
      if ( (bidGblFlags & 2) != 0 && off_180264720[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceW(off_1802613D8[0], 3080192, off_180264720[0], 6);
      }
      v26 = Error;
    }
    else
    {
      Error = -1;
      v13 = 50117;
      if ( (bidGblFlags & 2) != 0 && off_180264718[0] )
      {
        SniErrorIdFromStringId(0xC3C5u);
        bidTraceW(off_1802613D0[0], 3076096, off_180264718[0], 6);
        v17 = 0xFFFFFFFFLL;
        goto LABEL_35;
      }
    }
    v17 = v26;
    goto LABEL_35;
  }
  *(_DWORD *)optval = 1;
  if ( setsockopt(v37, 6, 1, optval, 4) == -1 )
  {
    Error = WSAGetLastError();
    v13 = 50100;
    if ( (bidGblFlags & 2) == 0 || !off_180264728[0] )
      goto LABEL_34;
    SniErrorIdFromStringId(0xC3B4u);
    v14 = off_180264728[0];
    v15 = 3094528;
    v16 = off_1802613E0[0];
    goto LABEL_33;
  }
  Error = Tcp::SetKeepAliveOption(v9);
  if ( Error )
    goto LABEL_36;
  Error = (*(__int64 (__fastcall **)(SNI::detail::Transport *))(*(_QWORD *)v9 + 176LL))(v9);
  if ( Error )
    goto LABEL_36;
  name = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  namelen = 128;
  if ( getpeername(*((_QWORD *)v9 + 8), &name, &namelen) )
  {
    Error = WSAGetLastError();
    v13 = 50100;
    if ( (bidGblFlags & 2) == 0 || !off_180264730[0] )
      goto LABEL_34;
    SniErrorIdFromStringId(0xC3B4u);
    v14 = off_180264730[0];
    v15 = 3122176;
    v16 = off_1802613E8[0];
    goto LABEL_33;
  }
  Error = Tcp::SetPeerAddrInfo(v9, &name, namelen);
  if ( Error )
  {
    v13 = 50100;
    if ( (bidGblFlags & 2) == 0 || !off_180264738[0] )
      goto LABEL_34;
    SniErrorIdFromStringId(0xC3B4u);
    v14 = off_180264738[0];
    v15 = 3129344;
    v16 = off_1802613F0[0];
    goto LABEL_33;
  }
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v46 = 128;
  if ( getsockname(*((_QWORD *)v9 + 8), &v59, &v46) )
  {
    Error = WSAGetLastError();
    v13 = 50100;
    if ( (bidGblFlags & 2) == 0 || !off_180264740[0] )
      goto LABEL_34;
    SniErrorIdFromStringId(0xC3B4u);
    v14 = off_180264740[0];
    v15 = 3142656;
    v16 = off_1802613F8[0];
    goto LABEL_33;
  }
  Error = Tcp::SetLocalAddrInfo(v9, &v59, v46);
  if ( Error )
  {
    v13 = 50100;
    if ( (bidGblFlags & 2) == 0 || !off_180264748[0] )
      goto LABEL_34;
    SniErrorIdFromStringId(0xC3B4u);
    v14 = off_180264748[0];
    v15 = 3149824;
    v16 = off_180261400[0];
    goto LABEL_33;
  }
  *((_QWORD *)v9 + 2) = *((_QWORD *)v9 + 8);
  Error = SNI::detail::Transport::DWSetSkipCompletionPortOnSuccess(v9);
  if ( Error )
  {
    v13 = 50100;
    if ( (bidGblFlags & 2) == 0 || !off_180264750[0] )
      goto LABEL_34;
    SniErrorIdFromStringId(0xC3B4u);
    v14 = off_180264750[0];
    v15 = 3162112;
    v16 = off_180261408[0];
    goto LABEL_33;
  }
  if ( !SNI::detail::Transport::FWillSkipCompletionPortOnSuccess(v9) )
  {
    argp[0] = 1;
    if ( (*((_BYTE *)v43 + 228) & 1) == 0 && ioctlsocket(*((_QWORD *)v9 + 8), -2147195266, argp) == -1 )
    {
      Error = WSAGetLastError();
      v13 = 50100;
      if ( (bidGblFlags & 2) == 0 || !off_180264758[0] )
        goto LABEL_34;
      SniErrorIdFromStringId(0xC3B4u);
      v14 = off_180264758[0];
      v15 = 3176448;
      v16 = off_180261410[0];
      goto LABEL_33;
    }
  }
  *((_DWORD *)v9 + 11) = bidUpdateItemIDA(*((unsigned int *)v9 + 11), off_180262B40[0], a2);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264760[0] )
    bidTraceW(off_180261418[0], 3189760, off_180264760[0], *((unsigned int *)v9 + 11));
  *v41 = v9;
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264768[0] )
    bidTraceW(off_180261420[0], 3201024, off_180264768[0], 0);
LABEL_46:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v49);
  return (unsigned int)v42;
}

```

## disassembly

```asm
0x180165540  push    rbp
0x180165542  push    rbx
0x180165543  push    rsi
0x180165544  push    rdi
0x180165545  push    r12
0x180165547  push    r13
0x180165549  push    r14
0x18016554b  push    r15
0x18016554d  lea     rbp, [rsp-0C8h]
0x180165555  sub     rsp, 1C8h
0x18016555c  mov     rax, cs:__security_cookie
0x180165563  xor     rax, rsp
0x180165566  mov     [rbp+100h+var_50], rax
0x18016556d  mov     r14d, r9d
0x180165570  mov     [rsp+200h+var_1C0], r8
0x180165575  mov     r13, rdx
0x180165578  mov     rsi, rcx
0x18016557b  mov     [rsp+200h+var_1B0], rcx
0x180165580  mov     [rsp+200h+var_188], 0FFFFFFFFFFFFFFFFh
0x180165589  mov     eax, cs:_bidGblFlags
0x18016558f  and     eax, 20004h
0x180165594  cmp     eax, 20004h
0x180165599  jnz     short loc_1801655C8
0x18016559b  mov     rax, cs:off_180266A08; "<Tcp::Open|API|SNI> pConn: %p{SNI_Conn*"...
0x1801655a2  test    rax, rax
0x1801655a5  jz      short loc_1801655C8
0x1801655a7  mov     [rsp+200h+var_1D8], r9d
0x1801655ac  mov     qword ptr [rsp+200h+optlen], r8
0x1801655b1  mov     r9, rdx
0x1801655b4  mov     r8, rcx
0x1801655b7  mov     rdx, cs:off_180266A08; "<Tcp::Open|API|SNI> pConn: %p{SNI_Conn*"...
0x1801655be  lea     rcx, [rsp+200h+var_188]
0x1801655c3  call    _bidScopeEnterW
0x1801655c8  xor     r12d, r12d
0x1801655cb  mov     [rsp+200h+var_1B8], r12
0x1801655d0  mov     [rsp+200h+ppResult], r12
0x1801655d5  xorps   xmm0, xmm0
0x1801655d8  movups  xmmword ptr [rbp+100h+pHints.ai_flags], xmm0
0x1801655dc  movups  xmmword ptr [rbp+100h+pHints.ai_addrlen], xmm0
0x1801655e0  movups  xmmword ptr [rbp+100h+pHints.ai_addr], xmm0
0x1801655e4  call    cs:__imp_GetTickCount
0x1801655ea  mov     dword ptr [rsp+200h+optval], eax
0x1801655ee  mov     ebx, r14d
0x1801655f1  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x1801655f8  mov     rax, [rcx]
0x1801655fb  mov     edx, 160h
0x180165600  mov     rax, [rax+58h]
0x180165604  call    cs:__guard_dispatch_icall_fptr
0x18016560a  mov     r15, rax
0x18016560d  mov     qword ptr [rsp+200h+argp], rax
0x180165612  test    rax, rax
0x180165615  jz      loc_180165783
0x18016561b  mov     rdx, rsi; struct SNI_Conn *
0x18016561e  mov     rcx, rax; this
0x180165621  call    ??0Transport@detail@SNI@@IEAA@QEAVSNI_Conn@@@Z; SNI::detail::Transport::Transport(SNI_Conn * const)
0x180165626  nop
0x180165627  lea     rax, ??_7Tcp@@6B@; const Tcp::`vftable'
0x18016562e  mov     [r15], rax
0x180165631  mov     qword ptr [r15+40h], 0FFFFFFFFFFFFFFFFh
0x180165639  mov     [r15+48h], r12
0x18016563d  mov     [r15+50h], r12w
0x180165642  xor     eax, eax
0x180165644  xorps   xmm0, xmm0
0x180165647  movups  xmmword ptr [r15+54h], xmm0
0x18016564c  movups  xmmword ptr [r15+64h], xmm0
0x180165651  movups  xmmword ptr [r15+74h], xmm0
0x180165656  movups  xmmword ptr [r15+84h], xmm0
0x18016565e  movups  xmmword ptr [r15+94h], xmm0
0x180165666  movups  xmmword ptr [r15+0A4h], xmm0
0x18016566e  mov     [r15+0B4h], rax
0x180165675  movups  xmmword ptr [r15+0BCh], xmm0
0x18016567d  movups  xmmword ptr [r15+0CCh], xmm0
0x180165685  movups  xmmword ptr [r15+0DCh], xmm0
0x18016568d  movups  xmmword ptr [r15+0ECh], xmm0
0x180165695  movups  xmmword ptr [r15+0FCh], xmm0
0x18016569d  movups  xmmword ptr [r15+10Ch], xmm0
0x1801656a5  mov     [r15+11Ch], rax
0x1801656ac  mov     [r15+124h], r12d
0x1801656b3  mov     [r15+128h], r12
0x1801656ba  mov     [r15+130h], r12d
0x1801656c1  mov     [r15+138h], r12
0x1801656c8  mov     [r15+140h], r12
0x1801656cf  mov     [r15+148h], r12
0x1801656d6  mov     [r15+150h], r12d
0x1801656dd  mov     [r15+158h], r12
0x1801656e4  mov     dword ptr [r15+18h], 6
0x1801656ec  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x1801656f3  mov     rax, [rcx]
0x1801656f6  mov     edx, 18h
0x1801656fb  mov     rax, [rax+58h]
0x1801656ff  call    cs:__guard_dispatch_icall_fptr
0x180165705  mov     rdi, rax
0x180165708  mov     qword ptr [rsp+200h+argp], rax
0x18016570d  test    rax, rax
0x180165710  jz      short loc_18016575C
0x180165712  lea     rax, ??_7CCriticalSectionNT_SNI@@6B@; const CCriticalSectionNT_SNI::`vftable'
0x180165719  mov     [rdi], rax
0x18016571c  mov     [rdi+8], r12b
0x180165720  mov     [rdi+10h], r12
0x180165724  mov     [r15+48h], rdi
0x180165728  test    rdi, rdi
0x18016572b  jz      short loc_180165760
0x18016572d  lea     rcx, [rdi+10h]; struct CCriticalSection **
0x180165731  xor     edx, edx
0x180165733  call    MPInitializeCriticalSectionAndSpinCount
0x180165738  test    eax, eax
0x18016573a  jz      short loc_180165742
0x18016573c  mov     byte ptr [rdi+8], 1
0x180165740  jmp     short loc_180165760
0x180165742  mov     rcx, [r15+48h]
0x180165746  test    rcx, rcx
0x180165749  jz      short loc_18016575C
0x18016574b  mov     rax, [rcx]
0x18016574e  mov     edx, 1
0x180165753  mov     rax, [rax]
0x180165756  call    cs:__guard_dispatch_icall_fptr
0x18016575c  mov     [r15+48h], r12
0x180165760  movsxd  r8, dword ptr [rsi+30h]
0x180165764  mov     rdx, r15
0x180165767  mov     rcx, cs:off_180262B30; "<Tcp::Tcp|ID|SNI> %p{.} created by %u#{"...
0x18016576e  call    _bidObtainItemIDA
0x180165773  mov     [r15+2Ch], eax
0x180165777  lea     rax, ??_7TcpWSA@@6B@; const TcpWSA::`vftable'
0x18016577e  mov     [r15], rax
0x180165781  jmp     short loc_180165786
0x180165783  mov     r15, r12
0x180165786  test    r15, r15
0x180165789  jnz     short loc_1801657EB
0x18016578b  mov     edi, 0Eh
0x180165790  mov     ebx, 0C3B4h
0x180165795  test    byte ptr cs:_bidGblFlags, 2
0x18016579c  jz      short loc_1801657D7
0x18016579e  mov     rax, cs:off_1802646E8; "<Tcp::Open|ERR|SNI> ProviderNum: %d{Pro"...
0x1801657a5  test    rax, rax
0x1801657a8  jz      short loc_1801657D7
0x1801657aa  mov     ecx, ebx; unsigned int
0x1801657ac  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1801657b1  mov     [rsp+200h+var_1D8], edi
0x1801657b5  mov     [rsp+200h+optlen], eax
0x1801657b9  mov     r9d, 6
0x1801657bf  mov     r8, cs:off_1802646E8; "<Tcp::Open|ERR|SNI> ProviderNum: %d{Pro"...
0x1801657c6  mov     edx, 2C7C00h
0x1801657cb  mov     rcx, cs:off_1802613A0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801657d2  call    _bidTraceW
0x1801657d7  mov     r8d, ebx
0x1801657da  mov     edx, edi
0x1801657dc  mov     ecx, 6
0x1801657e1  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1801657e6  jmp     loc_18016592D
0x1801657eb  mov     rax, [r15]
0x1801657ee  mov     rcx, r15
0x1801657f1  mov     rax, [rax+38h]
0x1801657f5  call    cs:__guard_dispatch_icall_fptr
0x1801657fb  mov     edi, eax
0x1801657fd  test    eax, eax
0x1801657ff  jz      short loc_18016585C
0x180165801  mov     ebx, 0C3B4h
0x180165806  test    byte ptr cs:_bidGblFlags, 2
0x18016580d  jz      short loc_180165848
0x18016580f  mov     rax, cs:off_1802646F0; "<Tcp::Open|ERR|SNI> ProviderNum: %d{Pro"...
0x180165816  test    rax, rax
0x180165819  jz      short loc_180165848
0x18016581b  mov     ecx, ebx; unsigned int
0x18016581d  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x180165822  mov     [rsp+200h+var_1D8], edi
0x180165826  mov     [rsp+200h+optlen], eax
0x18016582a  mov     r9d, 6
0x180165830  mov     r8, cs:off_1802646F0; "<Tcp::Open|ERR|SNI> ProviderNum: %d{Pro"...
0x180165837  mov     edx, 2C9C00h
0x18016583c  mov     rcx, cs:off_1802613A8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180165843  call    _bidTraceW
0x180165848  mov     r8d, ebx
0x18016584b  mov     edx, edi
0x18016584d  mov     ecx, 6
0x180165852  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x180165857  jmp     loc_18016592D
0x18016585c  mov     [rbp+100h+pHints.ai_socktype], 1
0x180165863  mov     edi, r12d
0x180165866  lea     r9, [rsp+200h+ppResult]; ppResult
0x18016586b  lea     r8, [rbp+100h+pHints]; pHints
0x18016586f  lea     rdx, [r13+608h]; pServiceName
0x180165876  lea     rcx, [r13+8]; pNodeName
0x18016587a  call    cs:__imp_GetAddrInfoW
0x180165880  test    eax, eax
0x180165882  jz      short loc_18016588C
0x180165884  call    cs:__imp_WSAGetLastError
0x18016588a  mov     edi, eax
0x18016588c  test    edi, edi
0x18016588e  jz      loc_180165A40
0x180165894  cmp     edi, 2AF9h
0x18016589a  jnz     loc_1801659F1
0x1801658a0  or      [rbp+100h+pHints.ai_flags], 4
0x1801658a4  xor     edi, edi
0x1801658a6  lea     r9, [rsp+200h+ppResult]; ppResult
0x1801658ab  lea     r8, [rbp+100h+pHints]; pHints
0x1801658af  lea     rdx, [r13+608h]; pServiceName
0x1801658b6  lea     rcx, [r13+8]; pNodeName
0x1801658ba  call    cs:__imp_GetAddrInfoW
0x1801658c0  test    eax, eax
0x1801658c2  jz      short loc_1801658CC
0x1801658c4  call    cs:__imp_WSAGetLastError
0x1801658ca  mov     edi, eax
0x1801658cc  test    edi, edi
0x1801658ce  jz      loc_180165A40
0x1801658d4  mov     ebx, 0C3B4h
0x1801658d9  test    byte ptr cs:_bidGblFlags, 2
0x1801658e0  jz      short loc_18016591B
0x1801658e2  mov     rax, cs:off_1802646F8; "<Tcp::Open|ERR|SNI> ProviderNum: %d{Pro"...
0x1801658e9  test    rax, rax
0x1801658ec  jz      short loc_18016591B
0x1801658ee  mov     ecx, ebx; unsigned int
0x1801658f0  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1801658f5  mov     [rsp+200h+var_1D8], edi
0x1801658f9  mov     [rsp+200h+optlen], eax
0x1801658fd  mov     r9d, 6
0x180165903  mov     r8, cs:off_1802646F8; "<Tcp::Open|ERR|SNI> ProviderNum: %d{Pro"...
0x18016590a  mov     edx, 2CF800h
0x18016590f  mov     rcx, cs:off_1802613B0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180165916  call    _bidTraceW
0x18016591b  mov     edx, edi
0x18016591d  mov     r8d, ebx
0x180165920  mov     ecx, 6
0x180165925  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18016592a  xor     r12d, r12d
0x18016592d  mov     rcx, [rsp+200h+ppResult]; pAddrInfo
0x180165932  test    rcx, rcx
0x180165935  jz      short loc_180165942
0x180165937  call    cs:__imp_FreeAddrInfoW
0x18016593d  mov     [rsp+200h+ppResult], r12
0x180165942  test    r15, r15
0x180165945  jz      short loc_18016597A
0x180165947  mov     rcx, [r15+40h]; s
0x18016594b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18016594f  jz      short loc_180165966
0x180165951  mov     edx, 1; how
0x180165956  call    cs:__imp_shutdown
0x18016595c  mov     rcx, [r15+40h]; s
0x180165960  call    cs:__imp_closesocket
0x180165966  mov     rax, [r15]
0x180165969  mov     edx, 1
0x18016596e  mov     rcx, r15
0x180165971  mov     rax, [rax]
0x180165974  call    cs:__guard_dispatch_icall_fptr
0x18016597a  mov     rax, [rsp+200h+var_1C0]
0x18016597f  mov     [rax], r12
0x180165982  mov     eax, cs:_bidGblFlags
0x180165988  and     eax, 20002h
0x18016598d  cmp     eax, 20002h
0x180165992  jnz     short loc_1801659BB
0x180165994  mov     rax, cs:off_180264770; "<Tcp::Open|RET|SNI> %d{WINERR}\n"
0x18016599b  test    rax, rax
0x18016599e  jz      short loc_1801659BB
0x1801659a0  mov     r9d, edi
0x1801659a3  mov     r8, cs:off_180264770; "<Tcp::Open|RET|SNI> %d{WINERR}\n"
0x1801659aa  mov     edx, 315400h
0x1801659af  mov     rcx, cs:off_180261428; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801659b6  call    _bidTraceW
0x1801659bb  mov     dword ptr [rsp+200h+var_1B8], edi
0x1801659bf  lea     rcx, [rsp+200h+var_188]; this
0x1801659c4  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x1801659c9  nop
0x1801659ca  mov     eax, dword ptr [rsp+200h+var_1B8]
0x1801659ce  mov     rcx, [rbp+100h+var_50]
0x1801659d5  xor     rcx, rsp; StackCookie
0x1801659d8  call    __security_check_cookie
0x1801659dd  add     rsp, 1C8h
0x1801659e4  pop     r15
0x1801659e6  pop     r14
0x1801659e8  pop     r13
0x1801659ea  pop     r12
0x1801659ec  pop     rdi
0x1801659ed  pop     rsi
0x1801659ee  pop     rbx
0x1801659ef  pop     rbp
0x1801659f0  retn
0x1801659f1  mov     ebx, 0C3B4h
0x1801659f6  test    byte ptr cs:_bidGblFlags, 2
0x1801659fd  jz      loc_18016591B
0x180165a03  mov     rax, cs:off_180264700; "<Tcp::Open|ERR|SNI> ProviderNum: %d{Pro"...
0x180165a0a  test    rax, rax
0x180165a0d  jz      loc_18016591B
0x180165a13  mov     ecx, ebx; unsigned int
0x180165a15  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x180165a1a  mov     [rsp+200h+var_1D8], edi
0x180165a1e  mov     [rsp+200h+optlen], eax
0x180165a22  mov     r9d, 6
0x180165a28  mov     r8, cs:off_180264700; "<Tcp::Open|ERR|SNI> ProviderNum: %d{Pro"...
0x180165a2f  mov     edx, 2D1000h
0x180165a34  mov     rcx, cs:off_1802613B8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180165a3b  jmp     loc_180165916
0x180165a40  cmp     byte ptr [r13+808h], 0
0x180165a48  jnz     loc_180165C25
0x180165a4e  movzx   eax, byte ptr [r13+809h]
0x180165a56  cmp     al, 1
0x180165a58  jnz     short loc_180165AA9
0x180165a5a  xor     edx, edx
0x180165a5c  mov     rax, [rsp+200h+ppResult]
0x180165a61  test    rax, rax
0x180165a64  jz      short loc_180165A7E
0x180165a66  mov     ecx, [rax+4]
  ... truncated ...
```
