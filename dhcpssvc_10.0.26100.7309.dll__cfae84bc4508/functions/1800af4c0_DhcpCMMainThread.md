# DhcpCMMainThread

- ea: `0x1800af4c0`
- end: `0x1800afc82`
- name: `DhcpCMMainThread`
- size: `1986`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180002854`
- `0x18001ceb4`
- `0x1800ae11c`
- `0x1800ae358`
- `0x1800ae730`
- `0x1800aec1c`
- `0x1800af4c0`
- `0x1800afc88`
- `0x1800afd9c`
- `0x1800b0d5c`
- `0x1800cc99a`
- `0x1800cc9e0`

## import_xrefs

- `WS2_32!WSAResetEvent` at `0x1800af689`
- `WS2_32!WSAResetEvent` at `0x1800af689`
- `WS2_32!WSAEnumNetworkEvents` at `0x1800af6f7`
- `WS2_32!WSAEnumNetworkEvents` at `0x1800af6f7`
- `WS2_32!WSASetEvent` at `0x1800af7cf`
- `WS2_32!WSASetEvent` at `0x1800af9ac`
- `WS2_32!WSASetEvent` at `0x1800afa38`
- `WS2_32!WSASetEvent` at `0x1800afafe`
- `WS2_32!WSASetEvent` at `0x1800afc1e`
- `WS2_32!WSASetEvent` at `0x1800af7cf`
- `WS2_32!WSASetEvent` at `0x1800af9ac`
- `WS2_32!WSASetEvent` at `0x1800afa38`
- `WS2_32!WSASetEvent` at `0x1800afafe`
- `WS2_32!WSASetEvent` at `0x1800afc1e`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800af55a`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800af60b`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800af55a`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800af60b`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af56d`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af699`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af7df`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af9bc`
- `WS2_32!__imp_WSAGetLastError` at `0x1800afa48`
- `WS2_32!__imp_WSAGetLastError` at `0x1800afb0e`
- `WS2_32!__imp_WSAGetLastError` at `0x1800afc2e`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af56d`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af699`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af7df`
- `WS2_32!__imp_WSAGetLastError` at `0x1800af9bc`
- `WS2_32!__imp_WSAGetLastError` at `0x1800afa48`
- `WS2_32!__imp_WSAGetLastError` at `0x1800afb0e`
- `WS2_32!__imp_WSAGetLastError` at `0x1800afc2e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800af84e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800af84e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800af822`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800af822`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800af80e`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800afb39`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800af80e`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800afb39`
- `KERNEL32!AcquireSRWLockShared` at `0x1800af7b3`
- `KERNEL32!AcquireSRWLockShared` at `0x1800afae6`
- `KERNEL32!AcquireSRWLockShared` at `0x1800af7b3`
- `KERNEL32!AcquireSRWLockShared` at `0x1800afae6`
- `KERNEL32!EnterCriticalSection` at `0x1800af63a`
- `KERNEL32!EnterCriticalSection` at `0x1800af63a`
- `KERNEL32!LeaveCriticalSection` at `0x1800af6c7`
- `KERNEL32!LeaveCriticalSection` at `0x1800af6c7`

## string_xrefs

- `0x1800af86b`: `DeleteSocketFromGArray`
- `0x1800af8d8`: `DhcpCMAcceptIncomingConnections`
- `0x1800af588`: `DhcpCMMainThread`
- `0x1800af6b4`: `DhcpCMMainThread`
- `0x1800af7fa`: `DhcpCMMainThread`
- `0x1800af872`: `DhcpCMMainThread`
- `0x1800af8df`: `DhcpCMMainThread`
- `0x1800af94a`: `DhcpCMMainThread`
- `0x1800af9d7`: `DhcpCMMainThread`
- `0x1800afa63`: `DhcpCMMainThread`
- `0x1800afad4`: `DhcpCMMainThread`
- `0x1800afb29`: `DhcpCMMainThread`
- `0x1800afbfd`: `DhcpCMMainThread`
- `0x1800afc49`: `DhcpCMMainThread`

## pseudocode

```c
ULONG __fastcall DhcpCMMainThread(PVOID Parameter)
{
  DWORD v1; // eax
  __int64 v2; // rsi
  unsigned int Error; // eax
  unsigned int v4; // r15d
  DWORD v5; // edx
  __int64 v6; // rcx
  _DWORD *v7; // rax
  __int64 v8; // r14
  ULONG result; // eax
  unsigned int v10; // eax
  HANDLE v11; // rcx
  unsigned int v12; // eax
  unsigned int *v13; // rbx
  int v14; // edi
  _QWORD *v15; // rcx
  unsigned int v16; // eax
  void *v17; // rcx
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  __int64 v23; // rdi
  void *v24; // rcx
  unsigned int v25; // eax
  int *v26; // rcx
  __int64 v27; // r8
  unsigned int v28; // eax
  void *v29; // rcx
  unsigned int v30; // eax
  unsigned int v31; // eax
  __int64 v32; // rbx
  unsigned int v33; // eax
  unsigned int v34; // eax
  _BYTE NetworkEvents[52]; // [rsp+30h] [rbp-D8h] BYREF
  HANDLE hEvent[64]; // [rsp+68h] [rbp-A0h] BYREF
  LPVOID lpMem[64]; // [rsp+268h] [rbp+160h] BYREF

  memset(&NetworkEvents[8], 0, 44);
  memset_0(hEvent, 0, sizeof(hEvent));
  memset_0(lpMem, 0, sizeof(lpMem));
  while ( 1 )
  {
    while ( 1 )
    {
      v1 = WSAWaitForMultipleEvents(gSocketEventTotal, gSocketEventArray, 0, 0xFFFFFFFF, 0);
      v2 = v1;
      if ( v1 != -1 )
        break;
      Error = WSAGetLastError();
      DhcpPrintFOErrorEx(Error, "DhcpCMMainThread", "WSAWaitForMultipleEvents", 1966);
    }
    v4 = gSocketEventTotal;
    v5 = v1;
    if ( v1 < gSocketEventTotal )
      break;
LABEL_92:
    memset_0(hEvent, 0, sizeof(hEvent));
    memset_0(lpMem, 0, sizeof(lpMem));
  }
  v6 = v1;
  do
  {
    hEvent[v6] = gSocketEventArray[v6];
    v7 = (_DWORD *)gSocketArray[v6];
    lpMem[v6] = v7;
    if ( v7 )
      v7[1] = v5;
    ++v5;
    ++v6;
  }
  while ( v5 < v4 );
  v8 = v2;
  while ( 1 )
  {
    if ( hEvent[v8] )
    {
      result = WSAWaitForMultipleEvents(1u, &hEvent[v2], 1, 0, 0);
      if ( result != -1 && result != 258 )
        break;
    }
LABEL_91:
    v2 = (unsigned int)(v2 + 1);
    ++v8;
    if ( (unsigned int)v2 >= v4 )
      goto LABEL_92;
  }
  if ( !(_DWORD)v2 )
  {
    EnterCriticalSection(&gReadySocketsCS);
    v10 = DhcpCMProcessNewConnectionRequests(hEvent);
    if ( v10
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids, v10);
    }
    v11 = hEvent[v8];
    if ( v11 )
    {
      if ( !WSAResetEvent(v11) )
      {
        v12 = WSAGetLastError();
        DhcpPrintFOErrorEx(v12, "DhcpCMMainThread", "WSAResetEvent", 1998);
      }
    }
    LeaveCriticalSection(&gReadySocketsCS);
    goto LABEL_91;
  }
  if ( (_DWORD)v2 != 1 )
  {
    v13 = (unsigned int *)lpMem[v8];
    WSAEnumNetworkEvents(*((_QWORD *)v13 + 1), hEvent[v8], (LPWSANETWORKEVENTS)&NetworkEvents[8]);
    if ( (NetworkEvents[8] & 0x10) != 0 )
    {
      v14 = *(_DWORD *)&NetworkEvents[28];
      if ( *(_DWORD *)&NetworkEvents[28] )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
        {
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids,
            *(unsigned int *)&NetworkEvents[28]);
          v15 = WPP_GLOBAL_Control;
        }
        if ( v14 )
          goto LABEL_34;
LABEL_40:
        if ( (NetworkEvents[8] & 8) != 0 )
        {
          if ( *(_DWORD *)&NetworkEvents[24] )
          {
            if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x800000) != 0 )
            {
              WPP_SF_D(
                v15[2],
                59,
                &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids,
                *(unsigned int *)&NetworkEvents[24]);
              goto LABEL_47;
            }
          }
          else
          {
            v20 = DhcpCMAcceptIncomingConnections(v13);
            if ( v20 )
              DhcpPrintFOErrorEx(v20, "DhcpCMMainThread", "DhcpCMAcceptIncomingConnections", 2067);
LABEL_47:
            v15 = WPP_GLOBAL_Control;
          }
        }
        if ( (NetworkEvents[8] & 1) != 0 )
        {
          if ( *(_DWORD *)&NetworkEvents[12] )
          {
            if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x800000) != 0 )
            {
              WPP_SF_D(
                v15[2],
                60,
                &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids,
                *(unsigned int *)&NetworkEvents[12]);
              goto LABEL_56;
            }
          }
          else
          {
            v21 = DhcpCMReceiveFailoverMessage(v13, *v13, (__int64)hEvent);
            if ( v21 )
              DhcpPrintFOErrorEx(v21, "DhcpCMMainThread", "DhcpCMReceiveFailoverMessage", 2086);
            if ( !hEvent[v8] )
              goto LABEL_91;
LABEL_56:
            v15 = WPP_GLOBAL_Control;
          }
        }
        if ( (NetworkEvents[8] & 2) != 0 )
        {
          if ( *(_DWORD *)&NetworkEvents[16] )
          {
            if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x800000) != 0 )
            {
              WPP_SF_D(
                v15[2],
                61,
                &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids,
                *(unsigned int *)&NetworkEvents[16]);
              goto LABEL_65;
            }
          }
          else if ( *((_QWORD *)v13 + 5) )
          {
            if ( !WSASetEvent(*((HANDLE *)v13 + 5)) )
            {
              v22 = WSAGetLastError();
              DhcpPrintFOErrorEx(v22, "DhcpCMMainThread", "WSASetEvent", 2103);
            }
LABEL_65:
            v15 = WPP_GLOBAL_Control;
          }
        }
        if ( (NetworkEvents[8] & 0x20) != 0 )
        {
          if ( *(_DWORD *)&NetworkEvents[32] && v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x800000) != 0 )
            WPP_SF_D(v15[2], 62, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids, *(unsigned int *)&NetworkEvents[32]);
          v23 = *((_QWORD *)v13 + 7);
          if ( v23 )
          {
            v24 = (void *)*((_QWORD *)v13 + 6);
            if ( v24 && !WSASetEvent(v24) )
            {
              v25 = WSAGetLastError();
              DhcpPrintFOErrorEx(v25, "DhcpCMMainThread", "WSASetEvent", 2117);
            }
            hEvent[v13[1]] = 0;
            if ( *(_DWORD *)(v23 + 8) == 1 && gNumListeningSockets )
            {
              v26 = dword_1800FB380;
              v27 = (unsigned int)gNumListeningSockets;
              do
              {
                if ( *(v26 - 4) == *(_DWORD *)(v23 + 16) && *v26 == 1 )
                  hEvent[*(unsigned int *)(*((_QWORD *)v26 - 1) + 4LL)] = 0;
                v26 += 6;
                --v27;
              }
              while ( v27 );
            }
            v28 = DhcpCMCloseConnection(v13, *v13, 0);
            if ( v28 )
              DhcpPrintFOErrorEx(v28, "DhcpCMMainThread", "DhcpCMCloseConnection", 2130);
            AcquireSRWLockShared((PSRWLOCK)(v23 + 72));
            v29 = *(void **)(v23 + 312);
            if ( v29 && !WSASetEvent(v29) )
            {
              v30 = WSAGetLastError();
              DhcpPrintFOErrorEx(v30, "DhcpCMMainThread", "WSASetEvent", 2134);
            }
            ReleaseSRWLockShared((PSRWLOCK)(v23 + 72));
          }
          else
          {
            hEvent[v13[1]] = 0;
            v31 = DhcpCMCloseConnectionUnclaimedSocket(v13);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids, v31);
            }
          }
        }
        goto LABEL_91;
      }
      v16 = DhcpCMProcessEstablishedConnections(v13, hEvent[v8]);
      if ( v16 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_5bd49953df5f3f59743b495ddca40749_Traceguids, v16);
        }
LABEL_34:
        AcquireSRWLockShared((PSRWLOCK)(*((_QWORD *)v13 + 7) + 72LL));
        v17 = *(void **)(*((_QWORD *)v13 + 7) + 312LL);
        if ( v17 && !WSASetEvent(v17) )
        {
          v18 = WSAGetLastError();
          DhcpPrintFOErrorEx(v18, "DhcpCMMainThread", "WSASetEvent", 2043);
        }
        ReleaseSRWLockShared((PSRWLOCK)(*((_QWORD *)v13 + 7) + 72LL));
        AcquireSRWLockExclusive((PSRWLOCK)(*((_QWORD *)v13 + 7) + 72LL));
        *(_QWORD *)(*((_QWORD *)v13 + 7) + 480LL) = 0;
        *(_QWORD *)(*((_QWORD *)v13 + 7) + 488LL) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)(*((_QWORD *)v13 + 7) + 72LL));
        v19 = DeleteSocketFromGArray(*v13);
        if ( v19 )
          DhcpPrintFOErrorEx(v19, "DhcpCMMainThread", "DeleteSocketFromGArray", 2052);
      }
    }
    v15 = WPP_GLOBAL_Control;
    goto LABEL_40;
  }
  v32 = gSocketEventTotal - 1;
  if ( gSocketEventTotal != 2 )
  {
    do
    {
      v33 = DhcpCMCloseConnectionUnclaimedSocket((_QWORD *)gSocketArray[v32]);
      result = DhcpPrintFOErrorEx(v33, "DhcpCMMainThread", "DhcpCMCloseConnectionUnclaimedSocket", 2009);
      v32 = (unsigned int)(v32 - 1);
    }
    while ( (_DWORD)v32 != 1 );
  }
  if ( gTerminateCMThreadCompleteEvent )
  {
    result = WSASetEvent(gTerminateCMThreadCompleteEvent);
    if ( !result )
    {
      v34 = WSAGetLastError();
      return DhcpPrintFOErrorEx(v34, "DhcpCMMainThread", "WSASetEvent", 2013);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800af4c0  mov     rax, rsp
0x1800af4c3  mov     [rax+8], rbx
0x1800af4c7  mov     [rax+10h], rsi
0x1800af4cb  mov     [rax+18h], rdi
0x1800af4cf  push    rbp
0x1800af4d0  push    r14
0x1800af4d2  push    r15
0x1800af4d4  lea     rbp, [rax-388h]
0x1800af4db  sub     rsp, 470h
0x1800af4e2  mov     rax, cs:__security_cookie
0x1800af4e9  xor     rax, rsp
0x1800af4ec  mov     [rbp+380h+var_20], rax
0x1800af4f3  xorps   xmm0, xmm0
0x1800af4f6  lea     rcx, [rsp+480h+hEvent]; void *
0x1800af4fb  xor     eax, eax
0x1800af4fd  mov     ebx, 200h
0x1800af502  mov     r8d, ebx; Size
0x1800af505  mov     qword ptr [rsp+480h+NetworkEvents.iErrorCode+24h], rax
0x1800af50a  xor     edx, edx; Val
0x1800af50c  mov     dword ptr [rsp+480h+var_428], eax
0x1800af510  movups  xmmword ptr [rsp+480h+NetworkEvents.iErrorCode+4], xmm0
0x1800af515  movups  xmmword ptr [rsp+480h+NetworkEvents.iErrorCode+14h], xmm0
0x1800af51a  call    memset_0
0x1800af51f  mov     r8d, ebx; Size
0x1800af522  lea     rcx, [rbp+380h+lpMem]; void *
0x1800af529  xor     edx, edx; Val
0x1800af52b  call    memset_0
0x1800af530  lea     r14, gSocketArray
0x1800af537  lea     rdi, WPP_GLOBAL_Control
0x1800af53e  mov     ecx, cs:gSocketEventTotal; cEvents
0x1800af544  lea     rax, gSocketEventArray
0x1800af54b  and     [rsp+480h+var_460], 0
0x1800af550  mov     rdx, rax; lphEvents
0x1800af553  or      r9d, 0FFFFFFFFh; dwTimeout
0x1800af557  xor     r8d, r8d; fWaitAll
0x1800af55a  call    cs:__imp_WSAWaitForMultipleEvents
0x1800af561  nop     dword ptr [rax+rax+00h]
0x1800af566  mov     esi, eax
0x1800af568  cmp     eax, 0FFFFFFFFh
0x1800af56b  jnz     short loc_1800AF596
0x1800af56d  call    cs:__imp_WSAGetLastError
0x1800af574  nop     dword ptr [rax+rax+00h]
0x1800af579  mov     r9d, 7AEh
0x1800af57f  lea     r8, aWsawaitformult; "WSAWaitForMultipleEvents"
0x1800af586  mov     ecx, eax
0x1800af588  lea     rdx, aDhcpcmmainthre; "DhcpCMMainThread"
0x1800af58f  call    DhcpPrintFOErrorEx
0x1800af594  jmp     short loc_1800AF53E
0x1800af596  mov     r15d, cs:gSocketEventTotal
0x1800af59d  mov     edx, esi
0x1800af59f  cmp     esi, r15d
0x1800af5a2  jnb     loc_1800AFBAE
0x1800af5a8  lea     rcx, ds:0[rsi*8]
0x1800af5b0  lea     r9, gSocketEventArray
0x1800af5b7  mov     rax, [rcx+r9]
0x1800af5bb  mov     [rsp+rcx+480h+hEvent], rax
0x1800af5c0  mov     rax, [rcx+r14]
0x1800af5c4  mov     [rbp+rcx+380h+lpMem], rax
0x1800af5cc  test    rax, rax
0x1800af5cf  jz      short loc_1800AF5D4
0x1800af5d1  mov     [rax+4], edx
0x1800af5d4  inc     edx
0x1800af5d6  add     rcx, 8
0x1800af5da  cmp     edx, r15d
0x1800af5dd  jb      short loc_1800AF5B7
0x1800af5df  lea     r14, ds:0[rsi*8]
0x1800af5e7  cmp     [rsp+r14+480h+hEvent], 0
0x1800af5ed  jz      loc_1800AFB93
0x1800af5f3  and     [rsp+480h+var_460], 0
0x1800af5f8  lea     rdx, [rsp+480h+hEvent]
0x1800af5fd  xor     r9d, r9d; dwTimeout
0x1800af600  lea     rdx, [rdx+rsi*8]; lphEvents
0x1800af604  lea     ecx, [r9+1]; cEvents
0x1800af608  mov     r8d, ecx; fWaitAll
0x1800af60b  call    cs:__imp_WSAWaitForMultipleEvents
0x1800af612  nop     dword ptr [rax+rax+00h]
0x1800af617  cmp     eax, 0FFFFFFFFh
0x1800af61a  jz      loc_1800AFB93
0x1800af620  cmp     eax, 102h
0x1800af625  jz      loc_1800AFB93
0x1800af62b  test    esi, esi
0x1800af62d  jnz     loc_1800AF6D8
0x1800af633  lea     rcx, gReadySocketsCS; lpCriticalSection
0x1800af63a  call    cs:__imp_EnterCriticalSection
0x1800af641  nop     dword ptr [rax+rax+00h]
0x1800af646  lea     rcx, [rsp+480h+hEvent]
0x1800af64b  call    DhcpCMProcessNewConnectionRequests
0x1800af650  test    eax, eax
0x1800af652  jz      short loc_1800AF67F
0x1800af654  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af65b  cmp     rcx, rdi
0x1800af65e  jz      short loc_1800AF67F
0x1800af660  test    dword ptr [rcx+1Ch], 800000h
0x1800af667  jz      short loc_1800AF67F
0x1800af669  mov     rcx, [rcx+10h]
0x1800af66d  lea     edx, [rsi+38h]
0x1800af670  mov     r9d, eax
0x1800af673  lea     r8, WPP_5bd49953df5f3f59743b495ddca40749_Traceguids
0x1800af67a  call    WPP_SF_D
0x1800af67f  mov     rcx, [rsp+r14+480h+hEvent]; hEvent
0x1800af684  test    rcx, rcx
0x1800af687  jz      short loc_1800AF6C0
0x1800af689  call    cs:__imp_WSAResetEvent
0x1800af690  nop     dword ptr [rax+rax+00h]
0x1800af695  test    eax, eax
0x1800af697  jnz     short loc_1800AF6C0
0x1800af699  call    cs:__imp_WSAGetLastError
0x1800af6a0  nop     dword ptr [rax+rax+00h]
0x1800af6a5  mov     r9d, 7CEh
0x1800af6ab  lea     r8, aWsaresetevent; "WSAResetEvent"
0x1800af6b2  mov     ecx, eax
0x1800af6b4  lea     rdx, aDhcpcmmainthre; "DhcpCMMainThread"
0x1800af6bb  call    DhcpPrintFOErrorEx
0x1800af6c0  lea     rcx, gReadySocketsCS; lpCriticalSection
0x1800af6c7  call    cs:__imp_LeaveCriticalSection
0x1800af6ce  nop     dword ptr [rax+rax+00h]
0x1800af6d3  jmp     loc_1800AFB93
0x1800af6d8  cmp     esi, 1
0x1800af6db  jz      loc_1800AFBD3
0x1800af6e1  mov     rbx, [rbp+r14+380h+lpMem]
0x1800af6e9  lea     r8, [rsp+480h+NetworkEvents.iErrorCode+4]; lpNetworkEvents
0x1800af6ee  mov     rdx, [rsp+r14+480h+hEvent]; hEventObject
0x1800af6f3  mov     rcx, [rbx+8]; s
0x1800af6f7  call    cs:__imp_WSAEnumNetworkEvents
0x1800af6fe  nop     dword ptr [rax+rax+00h]
0x1800af703  test    byte ptr [rsp+480h+NetworkEvents.iErrorCode+4], 10h
0x1800af708  jz      loc_1800AF889
0x1800af70e  mov     edi, [rsp+480h+NetworkEvents.iErrorCode+18h]
0x1800af712  test    edi, edi
0x1800af714  jz      short loc_1800AF762
0x1800af716  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af71d  lea     rax, WPP_GLOBAL_Control
0x1800af724  cmp     rcx, rax
0x1800af727  jz      short loc_1800AF751
0x1800af729  test    dword ptr [rcx+1Ch], 800000h
0x1800af730  jz      short loc_1800AF751
0x1800af732  mov     rcx, [rcx+10h]
0x1800af736  lea     r8, WPP_5bd49953df5f3f59743b495ddca40749_Traceguids
0x1800af73d  mov     edx, 39h ; '9'
0x1800af742  mov     r9d, edi
0x1800af745  call    WPP_SF_D
0x1800af74a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af751  test    edi, edi
0x1800af753  lea     rdi, WPP_GLOBAL_Control
0x1800af75a  jz      loc_1800AF890
0x1800af760  jmp     short loc_1800AF7AB
0x1800af762  mov     rdx, [rsp+r14+480h+hEvent]
0x1800af767  mov     rcx, rbx
0x1800af76a  call    DhcpCMProcessEstablishedConnections
0x1800af76f  test    eax, eax
0x1800af771  jz      loc_1800AF882
0x1800af777  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af77e  lea     rdi, WPP_GLOBAL_Control
0x1800af785  cmp     rcx, rdi
0x1800af788  jz      short loc_1800AF7AB
0x1800af78a  test    dword ptr [rcx+1Ch], 800000h
0x1800af791  jz      short loc_1800AF7AB
0x1800af793  mov     rcx, [rcx+10h]
0x1800af797  lea     r8, WPP_5bd49953df5f3f59743b495ddca40749_Traceguids
0x1800af79e  mov     edx, 3Ah ; ':'
0x1800af7a3  mov     r9d, eax
0x1800af7a6  call    WPP_SF_D
0x1800af7ab  mov     rcx, [rbx+38h]
0x1800af7af  add     rcx, 48h ; 'H'; SRWLock
0x1800af7b3  call    cs:__imp_AcquireSRWLockShared
0x1800af7ba  nop     dword ptr [rax+rax+00h]
0x1800af7bf  mov     rax, [rbx+38h]
0x1800af7c3  mov     rcx, [rax+138h]; hEvent
0x1800af7ca  test    rcx, rcx
0x1800af7cd  jz      short loc_1800AF806
0x1800af7cf  call    cs:__imp_WSASetEvent
0x1800af7d6  nop     dword ptr [rax+rax+00h]
0x1800af7db  test    eax, eax
0x1800af7dd  jnz     short loc_1800AF806
0x1800af7df  call    cs:__imp_WSAGetLastError
0x1800af7e6  nop     dword ptr [rax+rax+00h]
0x1800af7eb  mov     r9d, 7FBh
0x1800af7f1  lea     r8, aWsasetevent; "WSASetEvent"
0x1800af7f8  mov     ecx, eax
0x1800af7fa  lea     rdx, aDhcpcmmainthre; "DhcpCMMainThread"
0x1800af801  call    DhcpPrintFOErrorEx
0x1800af806  mov     rcx, [rbx+38h]
0x1800af80a  add     rcx, 48h ; 'H'; SRWLock
0x1800af80e  call    cs:__imp_ReleaseSRWLockShared
0x1800af815  nop     dword ptr [rax+rax+00h]
0x1800af81a  mov     rcx, [rbx+38h]
0x1800af81e  add     rcx, 48h ; 'H'; SRWLock
0x1800af822  call    cs:__imp_AcquireSRWLockExclusive
0x1800af829  nop     dword ptr [rax+rax+00h]
0x1800af82e  mov     rax, [rbx+38h]
0x1800af832  and     qword ptr [rax+1E0h], 0
0x1800af83a  mov     rax, [rbx+38h]
0x1800af83e  and     qword ptr [rax+1E8h], 0
0x1800af846  mov     rcx, [rbx+38h]
0x1800af84a  add     rcx, 48h ; 'H'; SRWLock
0x1800af84e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800af855  nop     dword ptr [rax+rax+00h]
0x1800af85a  mov     ecx, [rbx]
0x1800af85c  call    DeleteSocketFromGArray
0x1800af861  test    eax, eax
0x1800af863  jz      short loc_1800AF889
0x1800af865  mov     r9d, 804h
0x1800af86b  lea     r8, aDeletesocketfr; "DeleteSocketFromGArray"
0x1800af872  lea     rdx, aDhcpcmmainthre; "DhcpCMMainThread"
0x1800af879  mov     ecx, eax
0x1800af87b  call    DhcpPrintFOErrorEx
0x1800af880  jmp     short loc_1800AF889
0x1800af882  lea     rdi, WPP_GLOBAL_Control
0x1800af889  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af890  test    byte ptr [rsp+480h+NetworkEvents.iErrorCode+4], 8
0x1800af895  jz      short loc_1800AF8F4
0x1800af897  mov     r9d, [rsp+480h+NetworkEvents.iErrorCode+14h]
0x1800af89c  test    r9d, r9d
0x1800af89f  jz      short loc_1800AF8C6
0x1800af8a1  cmp     rcx, rdi
0x1800af8a4  jz      short loc_1800AF8F4
0x1800af8a6  test    dword ptr [rcx+1Ch], 800000h
0x1800af8ad  jz      short loc_1800AF8F4
0x1800af8af  mov     rcx, [rcx+10h]
0x1800af8b3  lea     r8, WPP_5bd49953df5f3f59743b495ddca40749_Traceguids
0x1800af8ba  mov     edx, 3Bh ; ';'
0x1800af8bf  call    WPP_SF_D
0x1800af8c4  jmp     short loc_1800AF8ED
0x1800af8c6  mov     rcx, rbx
0x1800af8c9  call    DhcpCMAcceptIncomingConnections
0x1800af8ce  test    eax, eax
0x1800af8d0  jz      short loc_1800AF8ED
0x1800af8d2  mov     r9d, 813h
0x1800af8d8  lea     r8, aDhcpcmacceptin; "DhcpCMAcceptIncomingConnections"
0x1800af8df  lea     rdx, aDhcpcmmainthre; "DhcpCMMainThread"
0x1800af8e6  mov     ecx, eax
0x1800af8e8  call    DhcpPrintFOErrorEx
0x1800af8ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af8f4  test    byte ptr [rsp+480h+NetworkEvents.iErrorCode+4], 1
0x1800af8f9  jz      short loc_1800AF96B
0x1800af8fb  mov     r9d, [rsp+480h+NetworkEvents.iErrorCode+8]
0x1800af900  test    r9d, r9d
0x1800af903  jz      short loc_1800AF92A
0x1800af905  cmp     rcx, rdi
0x1800af908  jz      short loc_1800AF96B
0x1800af90a  test    dword ptr [rcx+1Ch], 800000h
0x1800af911  jz      short loc_1800AF96B
0x1800af913  mov     rcx, [rcx+10h]
0x1800af917  lea     r8, WPP_5bd49953df5f3f59743b495ddca40749_Traceguids
0x1800af91e  mov     edx, 3Ch ; '<'
0x1800af923  call    WPP_SF_D
0x1800af928  jmp     short loc_1800AF964
0x1800af92a  mov     edx, [rbx]
0x1800af92c  lea     r8, [rsp+480h+hEvent]
0x1800af931  mov     rcx, rbx; lpMem
0x1800af934  call    DhcpCMReceiveFailoverMessage
0x1800af939  test    eax, eax
0x1800af93b  jz      short loc_1800AF958
0x1800af93d  mov     r9d, 826h
0x1800af943  lea     r8, aDhcpcmreceivef; "DhcpCMReceiveFailoverMessage"
0x1800af94a  lea     rdx, aDhcpcmmainthre; "DhcpCMMainThread"
0x1800af951  mov     ecx, eax
0x1800af953  call    DhcpPrintFOErrorEx
0x1800af958  cmp     [rsp+r14+480h+hEvent], 0
0x1800af95e  jz      loc_1800AFB93
0x1800af964  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af96b  test    byte ptr [rsp+480h+NetworkEvents.iErrorCode+4], 2
0x1800af970  jz      short loc_1800AF9EA
0x1800af972  mov     r9d, [rsp+480h+NetworkEvents.iErrorCode+0Ch]
0x1800af977  test    r9d, r9d
0x1800af97a  jz      short loc_1800AF9A1
0x1800af97c  cmp     rcx, rdi
0x1800af97f  jz      short loc_1800AF9EA
0x1800af981  test    dword ptr [rcx+1Ch], 800000h
0x1800af988  jz      short loc_1800AF9EA
0x1800af98a  mov     rcx, [rcx+10h]
0x1800af98e  lea     r8, WPP_5bd49953df5f3f59743b495ddca40749_Traceguids
0x1800af995  mov     edx, 3Dh ; '='
0x1800af99a  call    WPP_SF_D
0x1800af99f  jmp     short loc_1800AF9E3
0x1800af9a1  cmp     qword ptr [rbx+28h], 0
0x1800af9a6  jz      short loc_1800AF9EA
0x1800af9a8  mov     rcx, [rbx+28h]; hEvent
0x1800af9ac  call    cs:__imp_WSASetEvent
0x1800af9b3  nop     dword ptr [rax+rax+00h]
0x1800af9b8  test    eax, eax
0x1800af9ba  jnz     short loc_1800AF9E3
0x1800af9bc  call    cs:__imp_WSAGetLastError
0x1800af9c3  nop     dword ptr [rax+rax+00h]
0x1800af9c8  mov     r9d, 837h
0x1800af9ce  lea     r8, aWsasetevent; "WSASetEvent"
0x1800af9d5  mov     ecx, eax
0x1800af9d7  lea     rdx, aDhcpcmmainthre; "DhcpCMMainThread"
0x1800af9de  call    DhcpPrintFOErrorEx
0x1800af9e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af9ea  test    byte ptr [rsp+480h+NetworkEvents.iErrorCode+4], 20h
0x1800af9ef  jz      loc_1800AFB93
0x1800af9f5  mov     r9d, [rsp+480h+NetworkEvents.iErrorCode+1Ch]
0x1800af9fa  test    r9d, r9d
0x1800af9fd  jz      short loc_1800AFA22
0x1800af9ff  cmp     rcx, rdi
0x1800afa02  jz      short loc_1800AFA22
0x1800afa04  test    dword ptr [rcx+1Ch], 800000h
0x1800afa0b  jz      short loc_1800AFA22
0x1800afa0d  mov     rcx, [rcx+10h]
  ... truncated ...
```
