# DhcpCMMainThread

- ea: `0x1800b02c0`
- end: `0x1800b0a98`
- name: `DhcpCMMainThread`
- size: `2008`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x18000282c`
- `0x18001c45c`
- `0x1800aeeb4`
- `0x1800af10c`
- `0x1800af4e4`
- `0x1800af9d8`
- `0x1800b02c0`
- `0x1800b0aa0`
- `0x1800b0bb4`
- `0x1800b1b78`
- `0x1800cda7a`
- `0x1800cdac0`

## import_xrefs

- `WS2_32!WSAEnumNetworkEvents` at `0x1800b04fd`
- `WS2_32!WSAEnumNetworkEvents` at `0x1800b04fd`
- `WS2_32!WSAResetEvent` at `0x1800b048f`
- `WS2_32!WSAResetEvent` at `0x1800b048f`
- `WS2_32!WSASetEvent` at `0x1800b05d5`
- `WS2_32!WSASetEvent` at `0x1800b07b8`
- `WS2_32!WSASetEvent` at `0x1800b0844`
- `WS2_32!WSASetEvent` at `0x1800b0911`
- `WS2_32!WSASetEvent` at `0x1800b0a34`
- `WS2_32!WSASetEvent` at `0x1800b05d5`
- `WS2_32!WSASetEvent` at `0x1800b07b8`
- `WS2_32!WSASetEvent` at `0x1800b0844`
- `WS2_32!WSASetEvent` at `0x1800b0911`
- `WS2_32!WSASetEvent` at `0x1800b0a34`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800b035d`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800b0411`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800b035d`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800b0411`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b0370`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b049f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b05e5`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b07c8`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b0854`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b0921`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b0a44`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b0370`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b049f`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b05e5`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b07c8`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b0854`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b0921`
- `WS2_32!__imp_WSAGetLastError` at `0x1800b0a44`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800b065a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800b065a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800b0628`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800b0628`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800b0614`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800b094c`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800b0614`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800b094c`
- `KERNEL32!AcquireSRWLockShared` at `0x1800b05b9`
- `KERNEL32!AcquireSRWLockShared` at `0x1800b08f9`
- `KERNEL32!AcquireSRWLockShared` at `0x1800b05b9`
- `KERNEL32!AcquireSRWLockShared` at `0x1800b08f9`
- `KERNEL32!EnterCriticalSection` at `0x1800b0440`
- `KERNEL32!EnterCriticalSection` at `0x1800b0440`
- `KERNEL32!LeaveCriticalSection` at `0x1800b04cd`
- `KERNEL32!LeaveCriticalSection` at `0x1800b04cd`

## string_xrefs

- `0x1800b0677`: `DeleteSocketFromGArray`
- `0x1800b06e4`: `DhcpCMAcceptIncomingConnections`
- `0x1800b038b`: `DhcpCMMainThread`
- `0x1800b04ba`: `DhcpCMMainThread`
- `0x1800b0600`: `DhcpCMMainThread`
- `0x1800b067e`: `DhcpCMMainThread`
- `0x1800b06eb`: `DhcpCMMainThread`
- `0x1800b0756`: `DhcpCMMainThread`
- `0x1800b07e3`: `DhcpCMMainThread`
- `0x1800b086f`: `DhcpCMMainThread`
- `0x1800b08e7`: `DhcpCMMainThread`
- `0x1800b093c`: `DhcpCMMainThread`
- `0x1800b0a13`: `DhcpCMMainThread`
- `0x1800b0a5f`: `DhcpCMMainThread`

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
  _DWORD *v13; // rbx
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
  __int64 *v26; // r8
  __int64 v27; // rcx
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
    v13 = lpMem[v8];
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
            v21 = DhcpCMReceiveFailoverMessage(v13);
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
              v26 = qword_1800FD360;
              v27 = (unsigned int)gNumListeningSockets;
              do
              {
                if ( *((_DWORD *)v26 - 4) == *(_DWORD *)(v23 + 16) && *(_DWORD *)v26 == 1 )
                  hEvent[*(unsigned int *)(*(v26 - 1) + 4)] = 0;
                v26 += 3;
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
0x1800b02c0  mov     rax, rsp
0x1800b02c3  mov     [rax+8], rbx
0x1800b02c7  mov     [rax+10h], rsi
0x1800b02cb  mov     [rax+18h], rdi
0x1800b02cf  push    rbp
0x1800b02d0  push    r14
0x1800b02d2  push    r15
0x1800b02d4  lea     rbp, [rax-388h]
0x1800b02db  sub     rsp, 470h
0x1800b02e2  mov     rax, cs:__security_cookie
0x1800b02e9  xor     rax, rsp
0x1800b02ec  mov     [rbp+380h+var_20], rax
0x1800b02f3  xorps   xmm0, xmm0
0x1800b02f6  lea     rcx, [rsp+480h+hEvent]; void *
0x1800b02fb  xor     eax, eax
0x1800b02fd  mov     ebx, 200h
0x1800b0302  mov     r8d, ebx; Size
0x1800b0305  mov     qword ptr [rsp+480h+NetworkEvents.iErrorCode+24h], rax
0x1800b030a  xor     edx, edx; Val
0x1800b030c  mov     dword ptr [rsp+480h+var_428], eax
0x1800b0310  movups  xmmword ptr [rsp+480h+NetworkEvents.iErrorCode+4], xmm0
0x1800b0315  movups  xmmword ptr [rsp+480h+NetworkEvents.iErrorCode+14h], xmm0
0x1800b031a  call    memset_0
0x1800b031f  mov     r8d, ebx; Size
0x1800b0322  lea     rcx, [rbp+380h+lpMem]; void *
0x1800b0329  xor     edx, edx; Val
0x1800b032b  call    memset_0
0x1800b0330  lea     r14, gSocketArray
0x1800b0337  lea     rdi, WPP_GLOBAL_Control
0x1800b033e  mov     ecx, cs:gSocketEventTotal; cEvents
0x1800b0344  lea     rax, gSocketEventArray
0x1800b034b  mov     rdx, rax; lphEvents
0x1800b034e  mov     [rsp+480h+fAlertable], 0; fAlertable
0x1800b0356  or      r9d, 0FFFFFFFFh; dwTimeout
0x1800b035a  xor     r8d, r8d; fWaitAll
0x1800b035d  call    cs:__imp_WSAWaitForMultipleEvents
0x1800b0364  nop     dword ptr [rax+rax+00h]
0x1800b0369  mov     esi, eax
0x1800b036b  cmp     eax, 0FFFFFFFFh
0x1800b036e  jnz     short loc_1800B0399
0x1800b0370  call    cs:__imp_WSAGetLastError
0x1800b0377  nop     dword ptr [rax+rax+00h]
0x1800b037c  mov     r9d, 7AEh
0x1800b0382  lea     r8, aWsawaitformult; "WSAWaitForMultipleEvents"
0x1800b0389  mov     ecx, eax
0x1800b038b  lea     rdx, aDhcpcmmainthre; "DhcpCMMainThread"
0x1800b0392  call    DhcpPrintFOErrorEx
0x1800b0397  jmp     short loc_1800B033E
0x1800b0399  mov     r15d, cs:gSocketEventTotal
0x1800b03a0  mov     edx, esi
0x1800b03a2  cmp     esi, r15d
0x1800b03a5  jnb     loc_1800B09C4
0x1800b03ab  lea     rcx, ds:0[rsi*8]
0x1800b03b3  lea     r9, gSocketEventArray
0x1800b03ba  mov     rax, [rcx+r9]
0x1800b03be  mov     [rsp+rcx+480h+hEvent], rax
0x1800b03c3  mov     rax, [rcx+r14]
0x1800b03c7  mov     [rbp+rcx+380h+lpMem], rax
0x1800b03cf  test    rax, rax
0x1800b03d2  jz      short loc_1800B03D7
0x1800b03d4  mov     [rax+4], edx
0x1800b03d7  inc     edx
0x1800b03d9  add     rcx, 8
0x1800b03dd  cmp     edx, r15d
0x1800b03e0  jb      short loc_1800B03BA
0x1800b03e2  lea     r14, ds:0[rsi*8]
0x1800b03ea  cmp     [rsp+r14+480h+hEvent], 0
0x1800b03f0  jz      loc_1800B09A9
0x1800b03f6  xor     r9d, r9d; dwTimeout
0x1800b03f9  mov     [rsp+480h+fAlertable], 0; fAlertable
0x1800b0401  lea     rdx, [rsp+480h+hEvent]
0x1800b0406  lea     rdx, [rdx+rsi*8]; lphEvents
0x1800b040a  lea     ecx, [r9+1]; cEvents
0x1800b040e  mov     r8d, ecx; fWaitAll
0x1800b0411  call    cs:__imp_WSAWaitForMultipleEvents
0x1800b0418  nop     dword ptr [rax+rax+00h]
0x1800b041d  cmp     eax, 0FFFFFFFFh
0x1800b0420  jz      loc_1800B09A9
0x1800b0426  cmp     eax, 102h
0x1800b042b  jz      loc_1800B09A9
0x1800b0431  test    esi, esi
0x1800b0433  jnz     loc_1800B04DE
0x1800b0439  lea     rcx, gReadySocketsCS; lpCriticalSection
0x1800b0440  call    cs:__imp_EnterCriticalSection
0x1800b0447  nop     dword ptr [rax+rax+00h]
0x1800b044c  lea     rcx, [rsp+480h+hEvent]
0x1800b0451  call    DhcpCMProcessNewConnectionRequests
0x1800b0456  test    eax, eax
0x1800b0458  jz      short loc_1800B0485
0x1800b045a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0461  cmp     rcx, rdi
0x1800b0464  jz      short loc_1800B0485
0x1800b0466  test    dword ptr [rcx+1Ch], 800000h
0x1800b046d  jz      short loc_1800B0485
0x1800b046f  mov     rcx, [rcx+10h]
0x1800b0473  lea     edx, [rsi+38h]
0x1800b0476  mov     r9d, eax
0x1800b0479  lea     r8, WPP_5bd49953df5f3f59743b495ddca40749_Traceguids
0x1800b0480  call    WPP_SF_D
0x1800b0485  mov     rcx, [rsp+r14+480h+hEvent]; hEvent
0x1800b048a  test    rcx, rcx
0x1800b048d  jz      short loc_1800B04C6
0x1800b048f  call    cs:__imp_WSAResetEvent
0x1800b0496  nop     dword ptr [rax+rax+00h]
0x1800b049b  test    eax, eax
0x1800b049d  jnz     short loc_1800B04C6
0x1800b049f  call    cs:__imp_WSAGetLastError
0x1800b04a6  nop     dword ptr [rax+rax+00h]
0x1800b04ab  mov     r9d, 7CEh
0x1800b04b1  lea     r8, aWsaresetevent; "WSAResetEvent"
0x1800b04b8  mov     ecx, eax
0x1800b04ba  lea     rdx, aDhcpcmmainthre; "DhcpCMMainThread"
0x1800b04c1  call    DhcpPrintFOErrorEx
0x1800b04c6  lea     rcx, gReadySocketsCS; lpCriticalSection
0x1800b04cd  call    cs:__imp_LeaveCriticalSection
0x1800b04d4  nop     dword ptr [rax+rax+00h]
0x1800b04d9  jmp     loc_1800B09A9
0x1800b04de  cmp     esi, 1
0x1800b04e1  jz      loc_1800B09E9
0x1800b04e7  mov     rbx, [rbp+r14+380h+lpMem]
0x1800b04ef  lea     r8, [rsp+480h+NetworkEvents.iErrorCode+4]; lpNetworkEvents
0x1800b04f4  mov     rdx, [rsp+r14+480h+hEvent]; hEventObject
0x1800b04f9  mov     rcx, [rbx+8]; s
0x1800b04fd  call    cs:__imp_WSAEnumNetworkEvents
0x1800b0504  nop     dword ptr [rax+rax+00h]
0x1800b0509  test    byte ptr [rsp+480h+NetworkEvents.iErrorCode+4], 10h
0x1800b050e  jz      loc_1800B0695
0x1800b0514  mov     edi, [rsp+480h+NetworkEvents.iErrorCode+18h]
0x1800b0518  test    edi, edi
0x1800b051a  jz      short loc_1800B0568
0x1800b051c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0523  lea     rax, WPP_GLOBAL_Control
0x1800b052a  cmp     rcx, rax
0x1800b052d  jz      short loc_1800B0557
0x1800b052f  test    dword ptr [rcx+1Ch], 800000h
0x1800b0536  jz      short loc_1800B0557
0x1800b0538  mov     rcx, [rcx+10h]
0x1800b053c  lea     r8, WPP_5bd49953df5f3f59743b495ddca40749_Traceguids
0x1800b0543  mov     edx, 39h ; '9'
0x1800b0548  mov     r9d, edi
0x1800b054b  call    WPP_SF_D
0x1800b0550  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0557  test    edi, edi
0x1800b0559  lea     rdi, WPP_GLOBAL_Control
0x1800b0560  jz      loc_1800B069C
0x1800b0566  jmp     short loc_1800B05B1
0x1800b0568  mov     rdx, [rsp+r14+480h+hEvent]
0x1800b056d  mov     rcx, rbx
0x1800b0570  call    DhcpCMProcessEstablishedConnections
0x1800b0575  test    eax, eax
0x1800b0577  jz      loc_1800B068E
0x1800b057d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0584  lea     rdi, WPP_GLOBAL_Control
0x1800b058b  cmp     rcx, rdi
0x1800b058e  jz      short loc_1800B05B1
0x1800b0590  test    dword ptr [rcx+1Ch], 800000h
0x1800b0597  jz      short loc_1800B05B1
0x1800b0599  mov     rcx, [rcx+10h]
0x1800b059d  lea     r8, WPP_5bd49953df5f3f59743b495ddca40749_Traceguids
0x1800b05a4  mov     edx, 3Ah ; ':'
0x1800b05a9  mov     r9d, eax
0x1800b05ac  call    WPP_SF_D
0x1800b05b1  mov     rcx, [rbx+38h]
0x1800b05b5  add     rcx, 48h ; 'H'; SRWLock
0x1800b05b9  call    cs:__imp_AcquireSRWLockShared
0x1800b05c0  nop     dword ptr [rax+rax+00h]
0x1800b05c5  mov     rax, [rbx+38h]
0x1800b05c9  mov     rcx, [rax+138h]; hEvent
0x1800b05d0  test    rcx, rcx
0x1800b05d3  jz      short loc_1800B060C
0x1800b05d5  call    cs:__imp_WSASetEvent
0x1800b05dc  nop     dword ptr [rax+rax+00h]
0x1800b05e1  test    eax, eax
0x1800b05e3  jnz     short loc_1800B060C
0x1800b05e5  call    cs:__imp_WSAGetLastError
0x1800b05ec  nop     dword ptr [rax+rax+00h]
0x1800b05f1  mov     r9d, 7FBh
0x1800b05f7  lea     r8, aWsasetevent; "WSASetEvent"
0x1800b05fe  mov     ecx, eax
0x1800b0600  lea     rdx, aDhcpcmmainthre; "DhcpCMMainThread"
0x1800b0607  call    DhcpPrintFOErrorEx
0x1800b060c  mov     rcx, [rbx+38h]
0x1800b0610  add     rcx, 48h ; 'H'; SRWLock
0x1800b0614  call    cs:__imp_ReleaseSRWLockShared
0x1800b061b  nop     dword ptr [rax+rax+00h]
0x1800b0620  mov     rcx, [rbx+38h]
0x1800b0624  add     rcx, 48h ; 'H'; SRWLock
0x1800b0628  call    cs:__imp_AcquireSRWLockExclusive
0x1800b062f  nop     dword ptr [rax+rax+00h]
0x1800b0634  mov     rax, [rbx+38h]
0x1800b0638  mov     qword ptr [rax+1E0h], 0
0x1800b0643  mov     rax, [rbx+38h]
0x1800b0647  mov     qword ptr [rax+1E8h], 0
0x1800b0652  mov     rcx, [rbx+38h]
0x1800b0656  add     rcx, 48h ; 'H'; SRWLock
0x1800b065a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b0661  nop     dword ptr [rax+rax+00h]
0x1800b0666  mov     ecx, [rbx]
0x1800b0668  call    DeleteSocketFromGArray
0x1800b066d  test    eax, eax
0x1800b066f  jz      short loc_1800B0695
0x1800b0671  mov     r9d, 804h
0x1800b0677  lea     r8, aDeletesocketfr; "DeleteSocketFromGArray"
0x1800b067e  lea     rdx, aDhcpcmmainthre; "DhcpCMMainThread"
0x1800b0685  mov     ecx, eax
0x1800b0687  call    DhcpPrintFOErrorEx
0x1800b068c  jmp     short loc_1800B0695
0x1800b068e  lea     rdi, WPP_GLOBAL_Control
0x1800b0695  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b069c  test    byte ptr [rsp+480h+NetworkEvents.iErrorCode+4], 8
0x1800b06a1  jz      short loc_1800B0700
0x1800b06a3  mov     r9d, [rsp+480h+NetworkEvents.iErrorCode+14h]
0x1800b06a8  test    r9d, r9d
0x1800b06ab  jz      short loc_1800B06D2
0x1800b06ad  cmp     rcx, rdi
0x1800b06b0  jz      short loc_1800B0700
0x1800b06b2  test    dword ptr [rcx+1Ch], 800000h
0x1800b06b9  jz      short loc_1800B0700
0x1800b06bb  mov     rcx, [rcx+10h]
0x1800b06bf  lea     r8, WPP_5bd49953df5f3f59743b495ddca40749_Traceguids
0x1800b06c6  mov     edx, 3Bh ; ';'
0x1800b06cb  call    WPP_SF_D
0x1800b06d0  jmp     short loc_1800B06F9
0x1800b06d2  mov     rcx, rbx
0x1800b06d5  call    DhcpCMAcceptIncomingConnections
0x1800b06da  test    eax, eax
0x1800b06dc  jz      short loc_1800B06F9
0x1800b06de  mov     r9d, 813h
0x1800b06e4  lea     r8, aDhcpcmacceptin; "DhcpCMAcceptIncomingConnections"
0x1800b06eb  lea     rdx, aDhcpcmmainthre; "DhcpCMMainThread"
0x1800b06f2  mov     ecx, eax
0x1800b06f4  call    DhcpPrintFOErrorEx
0x1800b06f9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0700  test    byte ptr [rsp+480h+NetworkEvents.iErrorCode+4], 1
0x1800b0705  jz      short loc_1800B0777
0x1800b0707  mov     r9d, [rsp+480h+NetworkEvents.iErrorCode+8]
0x1800b070c  test    r9d, r9d
0x1800b070f  jz      short loc_1800B0736
0x1800b0711  cmp     rcx, rdi
0x1800b0714  jz      short loc_1800B0777
0x1800b0716  test    dword ptr [rcx+1Ch], 800000h
0x1800b071d  jz      short loc_1800B0777
0x1800b071f  mov     rcx, [rcx+10h]
0x1800b0723  lea     r8, WPP_5bd49953df5f3f59743b495ddca40749_Traceguids
0x1800b072a  mov     edx, 3Ch ; '<'
0x1800b072f  call    WPP_SF_D
0x1800b0734  jmp     short loc_1800B0770
0x1800b0736  mov     edx, [rbx]
0x1800b0738  lea     r8, [rsp+480h+hEvent]
0x1800b073d  mov     rcx, rbx; lpMem
0x1800b0740  call    DhcpCMReceiveFailoverMessage
0x1800b0745  test    eax, eax
0x1800b0747  jz      short loc_1800B0764
0x1800b0749  mov     r9d, 826h
0x1800b074f  lea     r8, aDhcpcmreceivef; "DhcpCMReceiveFailoverMessage"
0x1800b0756  lea     rdx, aDhcpcmmainthre; "DhcpCMMainThread"
0x1800b075d  mov     ecx, eax
0x1800b075f  call    DhcpPrintFOErrorEx
0x1800b0764  cmp     [rsp+r14+480h+hEvent], 0
0x1800b076a  jz      loc_1800B09A9
0x1800b0770  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0777  test    byte ptr [rsp+480h+NetworkEvents.iErrorCode+4], 2
0x1800b077c  jz      short loc_1800B07F6
0x1800b077e  mov     r9d, [rsp+480h+NetworkEvents.iErrorCode+0Ch]
0x1800b0783  test    r9d, r9d
0x1800b0786  jz      short loc_1800B07AD
0x1800b0788  cmp     rcx, rdi
0x1800b078b  jz      short loc_1800B07F6
0x1800b078d  test    dword ptr [rcx+1Ch], 800000h
0x1800b0794  jz      short loc_1800B07F6
0x1800b0796  mov     rcx, [rcx+10h]
0x1800b079a  lea     r8, WPP_5bd49953df5f3f59743b495ddca40749_Traceguids
0x1800b07a1  mov     edx, 3Dh ; '='
0x1800b07a6  call    WPP_SF_D
0x1800b07ab  jmp     short loc_1800B07EF
0x1800b07ad  cmp     qword ptr [rbx+28h], 0
0x1800b07b2  jz      short loc_1800B07F6
0x1800b07b4  mov     rcx, [rbx+28h]; hEvent
0x1800b07b8  call    cs:__imp_WSASetEvent
0x1800b07bf  nop     dword ptr [rax+rax+00h]
0x1800b07c4  test    eax, eax
0x1800b07c6  jnz     short loc_1800B07EF
0x1800b07c8  call    cs:__imp_WSAGetLastError
0x1800b07cf  nop     dword ptr [rax+rax+00h]
0x1800b07d4  mov     r9d, 837h
0x1800b07da  lea     r8, aWsasetevent; "WSASetEvent"
0x1800b07e1  mov     ecx, eax
0x1800b07e3  lea     rdx, aDhcpcmmainthre; "DhcpCMMainThread"
0x1800b07ea  call    DhcpPrintFOErrorEx
0x1800b07ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b07f6  test    byte ptr [rsp+480h+NetworkEvents.iErrorCode+4], 20h
0x1800b07fb  jz      loc_1800B09A9
0x1800b0801  mov     r9d, [rsp+480h+NetworkEvents.iErrorCode+1Ch]
0x1800b0806  test    r9d, r9d
0x1800b0809  jz      short loc_1800B082E
0x1800b080b  cmp     rcx, rdi
0x1800b080e  jz      short loc_1800B082E
0x1800b0810  test    dword ptr [rcx+1Ch], 800000h
0x1800b0817  jz      short loc_1800B082E
0x1800b0819  mov     rcx, [rcx+10h]
  ... truncated ...
```
