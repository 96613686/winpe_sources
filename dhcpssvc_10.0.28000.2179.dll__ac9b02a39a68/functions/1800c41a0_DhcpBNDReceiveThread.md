# DhcpBNDReceiveThread

- ea: `0x1800c41a0`
- end: `0x1800c47cc`
- name: `DhcpBNDReceiveThread`
- size: `1580`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000282c`
- `0x180003228`
- `0x18001c45c`
- `0x1800c0928`
- `0x1800c1a80`
- `0x1800c1de4`
- `0x1800c2550`
- `0x1800c41a0`
- `0x1800cca94`
- `0x1800cccf4`

## import_xrefs

- `WS2_32!WSAResetEvent` at `0x1800c4290`
- `WS2_32!WSAResetEvent` at `0x1800c4290`
- `WS2_32!WSASetEvent` at `0x1800c42f1`
- `WS2_32!WSASetEvent` at `0x1800c4321`
- `WS2_32!WSASetEvent` at `0x1800c458a`
- `WS2_32!WSASetEvent` at `0x1800c45fa`
- `WS2_32!WSASetEvent` at `0x1800c463d`
- `WS2_32!WSASetEvent` at `0x1800c4777`
- `WS2_32!WSASetEvent` at `0x1800c42f1`
- `WS2_32!WSASetEvent` at `0x1800c4321`
- `WS2_32!WSASetEvent` at `0x1800c458a`
- `WS2_32!WSASetEvent` at `0x1800c45fa`
- `WS2_32!WSASetEvent` at `0x1800c463d`
- `WS2_32!WSASetEvent` at `0x1800c4777`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800c420e`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800c43c8`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800c420e`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800c43c8`
- `WS2_32!__imp_ntohl` at `0x1800c45d2`
- `WS2_32!__imp_ntohl` at `0x1800c45d2`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c42a0`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c4301`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c4331`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c459a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c460a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c464d`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c4787`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c42a0`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c4301`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c4331`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c459a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c460a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c464d`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c4787`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800c467e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800c46cd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800c467e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800c46cd`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800c44dd`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800c44dd`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800c4453`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800c4453`
- `KERNEL32!AcquireSRWLockShared` at `0x1800c4438`
- `KERNEL32!AcquireSRWLockShared` at `0x1800c4438`
- `KERNEL32!EnterCriticalSection` at `0x1800c4262`
- `KERNEL32!EnterCriticalSection` at `0x1800c44f4`
- `KERNEL32!EnterCriticalSection` at `0x1800c4262`
- `KERNEL32!EnterCriticalSection` at `0x1800c44f4`
- `KERNEL32!LeaveCriticalSection` at `0x1800c4374`
- `KERNEL32!LeaveCriticalSection` at `0x1800c4567`
- `KERNEL32!LeaveCriticalSection` at `0x1800c4374`
- `KERNEL32!LeaveCriticalSection` at `0x1800c4567`

## string_xrefs

- `0x1800c45b5`: `DhcpBNDReceiveThread`
- `0x1800c4625`: `DhcpBNDReceiveThread`
- `0x1800c4668`: `DhcpBNDReceiveThread`
- `0x1800c42bb`: `BndRecvThread`
- `0x1800c434c`: `BndRecvThread`
- `0x1800c47a2`: `BndRecvThread`

## pseudocode

```c
ULONG __fastcall DhcpBNDReceiveThread(PVOID Parameter)
{
  DWORD v1; // edx
  ULONG result; // eax
  ULONG v3; // r12d
  HANDLE v4; // rcx
  unsigned int Error; // eax
  _DWORD *v6; // rbx
  __int64 v7; // rdi
  __int64 v8; // rax
  void *v9; // rcx
  unsigned int v10; // eax
  __int64 v11; // r9
  void *v12; // rcx
  ULONG v13; // r13d
  DWORD v14; // eax
  __int64 v15; // rbx
  _QWORD *v16; // rsi
  unsigned int v17; // eax
  __int64 v18; // rdi
  int v19; // ebp
  _QWORD *v20; // rdx
  _QWORD *v21; // r9
  _QWORD *v22; // rax
  void *v23; // rcx
  unsigned int v24; // eax
  int v25; // edi
  void *v26; // rcx
  unsigned int v27; // eax
  void *v28; // rcx
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  void *v32; // [rsp+60h] [rbp+8h]

  v1 = gRecvThreadEventTotal;
  v32 = 0;
  gRecvThreadEventArray[gRecvThreadEventTotal] = gStartBndRecvProcessingReqEvent;
  gRecvThreadEventArray[++v1] = gTerminateBndRecvThreadEvent;
  gRecvThreadEventTotal = v1 + 1;
LABEL_2:
  while ( 2 )
  {
    while ( 1 )
    {
      result = WSAWaitForMultipleEvents(gRecvThreadEventTotal, gRecvThreadEventArray, 0, 0xFFFFFFFF, 0);
      v3 = result;
      if ( result != -1 )
        break;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
      {
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          &WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids,
          0xFFFFFFFFLL);
      }
    }
    if ( !result )
    {
      EnterCriticalSection(&gBndFailoverEndpointCS);
      v4 = gRecvThreadEventArray[(unsigned int)DhcpBNDProcessNewFoReqs(
                                                 1,
                                                 2,
                                                 &gRecvThreadEventTotal,
                                                 gRecvThreadEventArray)];
      if ( v4 && !WSAResetEvent(v4) )
      {
        Error = WSAGetLastError();
        DhcpPrintFOErrorEx(Error, "BndRecvThread", "WSAResetEvent", 3367);
      }
      v6 = &gBndRecvInitCloseFailoverEndpoint;
      v7 = 64;
      while ( 1 )
      {
        v8 = *(_QWORD *)v6;
        if ( *(_QWORD *)v6 )
          break;
LABEL_21:
        v6 += 4;
        if ( !--v7 )
        {
          LeaveCriticalSection(&gBndFailoverEndpointCS);
          goto LABEL_2;
        }
      }
      if ( v6[3] == 1 )
      {
        v9 = *(void **)(v8 + 400);
        if ( !v9 || WSASetEvent(v9) )
          goto LABEL_20;
        v10 = WSAGetLastError();
        v11 = 3376;
      }
      else
      {
        v12 = *(void **)(v8 + 440);
        if ( !v12 || WSASetEvent(v12) )
          goto LABEL_20;
        v10 = WSAGetLastError();
        v11 = 3380;
      }
      DhcpPrintFOErrorEx(v10, "BndRecvThread", "WSASetEvent", v11);
LABEL_20:
      v6[2] = 0;
      *(_QWORD *)v6 = 0;
      goto LABEL_21;
    }
    if ( result != 1 )
    {
      v13 = result;
      if ( result >= gRecvThreadEventTotal )
        continue;
      while ( 1 )
      {
        if ( v13 != v3 )
        {
          v14 = WSAWaitForMultipleEvents(1u, &gRecvThreadEventArray[v13], 1, 0, 0);
          if ( v14 == -1 || v14 == 258 )
            goto LABEL_72;
        }
        v15 = gBndRecvFailoverEndpoints[v13 - 2];
        if ( !v15 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids);
          }
          goto LABEL_72;
        }
        AcquireSRWLockShared((PSRWLOCK)(v15 + 72));
        v16 = (_QWORD *)MessageQGetElement(*(_QWORD *)(v15 + 88));
        ReleaseSRWLockShared((PSRWLOCK)(v15 + 72));
        if ( !v16 )
        {
          result = DhcpBNDHandleErrorConditions(8, 4, v15);
          switch ( result )
          {
            case 4u:
              goto LABEL_72;
            case 5u:
              goto LABEL_2;
            case 6u:
              return result;
          }
        }
        if ( *(_BYTE *)(*(_QWORD *)(v16[2] + 16LL) + 2LL) == 3 )
        {
          v17 = DhcpBNDProcessIncomingBndUpdates(v15, v16);
          if ( v17 )
          {
            result = DhcpBNDHandleErrorConditions(v17, 0, v15);
            if ( result != 4 )
            {
              if ( result == 5 )
                goto LABEL_2;
              if ( result == 6 )
                return result;
            }
          }
        }
        else
        {
          AcquireSRWLockExclusive((PSRWLOCK)(v15 + 72));
          v18 = *(_QWORD *)(v15 + 104);
          v19 = 0;
          EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 32));
          v20 = *(_QWORD **)v18;
          if ( *(_QWORD *)v18 != *(_QWORD *)(v15 + 104) )
          {
            while ( 1 )
            {
              v21 = v20;
              v32 = v20;
              v20 = (_QWORD *)*v20;
              if ( *(_DWORD *)(*(_QWORD *)(v16[2] + 16LL) + 8LL) == *(_DWORD *)(*(_QWORD *)(v21[2] + 16LL) + 8LL) )
                break;
              if ( v20 == *(_QWORD **)(v15 + 104) )
                goto LABEL_50;
            }
            v19 = 1;
            if ( (_QWORD *)v20[1] != v21 || (v22 = (_QWORD *)v21[1], (_QWORD *)*v22 != v21) )
              __fastfail(3u);
            *v22 = v20;
            v20[1] = v22;
            --*(_DWORD *)(v18 + 16);
            _InterlockedDecrement(&DhcpGlobalFailoverBndUpdPending);
          }
LABEL_50:
          LeaveCriticalSection((LPCRITICAL_SECTION)(v18 + 32));
          if ( v19 )
          {
            --*(_DWORD *)(v15 + 120);
            v23 = *(void **)(v15 + 112);
            if ( v23 && !WSASetEvent(v23) )
            {
              v24 = WSAGetLastError();
              DhcpPrintFOErrorEx(v24, "DhcpBNDReceiveThread", "WSASetEvent", 3481);
            }
            v25 = *(_DWORD *)(v15 + 544);
            if ( v25 == ntohl(*(_DWORD *)(*(_QWORD *)(v16[2] + 16LL) + 8LL)) && v25 )
            {
              v26 = *(void **)(v15 + 608);
              if ( v26 && !WSASetEvent(v26) )
              {
                v27 = WSAGetLastError();
                DhcpPrintFOErrorEx(v27, "DhcpBNDReceiveThread", "WSASetEvent", 3485);
              }
              v28 = *(void **)(v15 + 272);
              if ( v28 && !WSASetEvent(v28) )
              {
                v29 = WSAGetLastError();
                DhcpPrintFOErrorEx(v29, "DhcpBNDReceiveThread", "WSASetEvent", 3486);
              }
              *(_DWORD *)(v15 + 544) = 0;
            }
            ReleaseSRWLockExclusive((PSRWLOCK)(v15 + 72));
            v30 = DhcpBNDProcessIncomingBndAcks(v16, v32);
            if ( v30 )
            {
              result = DhcpBNDHandleErrorConditions(v30, 0, v15);
              if ( result != 4 )
              {
                if ( result == 5 )
                  goto LABEL_2;
                if ( result == 6 )
                  return result;
              }
            }
          }
          else
          {
            ReleaseSRWLockExclusive((PSRWLOCK)(v15 + 72));
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
            {
              WPP_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                88,
                &WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids,
                *(unsigned int *)(*(_QWORD *)(v16[2] + 16LL) + 8LL));
            }
            ResetAndRestoreInFreePacketPool(v16);
          }
        }
LABEL_72:
        if ( ++v13 >= gRecvThreadEventTotal )
          goto LABEL_2;
      }
    }
    break;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 )
    result = WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids);
  if ( gTerminateBndRecvThreadCompleteEvent )
  {
    result = WSASetEvent(gTerminateBndRecvThreadCompleteEvent);
    if ( !result )
    {
      v31 = WSAGetLastError();
      return DhcpPrintFOErrorEx(v31, "BndRecvThread", "WSASetEvent", 3395);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800c41a0  mov     [rsp+arg_8], rbx
0x1800c41a5  mov     [rsp+arg_10], rbp
0x1800c41aa  mov     [rsp+arg_18], rsi
0x1800c41af  push    rdi
0x1800c41b0  push    r12
0x1800c41b2  push    r13
0x1800c41b4  push    r14
0x1800c41b6  push    r15
0x1800c41b8  sub     rsp, 30h
0x1800c41bc  mov     edx, cs:gRecvThreadEventTotal
0x1800c41c2  lea     rbx, gRecvThreadEventArray
0x1800c41c9  mov     rax, cs:gStartBndRecvProcessingReqEvent
0x1800c41d0  lea     rdi, WPP_GLOBAL_Control
0x1800c41d7  xor     r14d, r14d
0x1800c41da  mov     [rsp+58h+arg_0], r14
0x1800c41df  mov     [rbx+rdx*8], rax
0x1800c41e3  inc     edx
0x1800c41e5  mov     rax, cs:gTerminateBndRecvThreadEvent
0x1800c41ec  mov     [rbx+rdx*8], rax
0x1800c41f0  lea     eax, [rdx+1]
0x1800c41f3  mov     cs:gRecvThreadEventTotal, eax
0x1800c41f9  mov     ecx, cs:gRecvThreadEventTotal; cEvents
0x1800c41ff  or      r9d, 0FFFFFFFFh; dwTimeout
0x1800c4203  xor     r8d, r8d; fWaitAll
0x1800c4206  mov     [rsp+58h+fAlertable], r14d; fAlertable
0x1800c420b  mov     rdx, rbx; lphEvents
0x1800c420e  call    cs:__imp_WSAWaitForMultipleEvents
0x1800c4215  nop     dword ptr [rax+rax+00h]
0x1800c421a  mov     r12d, eax
0x1800c421d  cmp     eax, 0FFFFFFFFh
0x1800c4220  jnz     short loc_1800C4252
0x1800c4222  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4229  cmp     rcx, rdi
0x1800c422c  jz      short loc_1800C41F9
0x1800c422e  test    dword ptr [rcx+1Ch], 800000h
0x1800c4235  jz      short loc_1800C41F9
0x1800c4237  mov     rcx, [rcx+10h]
0x1800c423b  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800c4242  mov     edx, 55h ; 'U'
0x1800c4247  or      r9d, 0FFFFFFFFh
0x1800c424b  call    WPP_SF_D
0x1800c4250  jmp     short loc_1800C41F9
0x1800c4252  test    r12d, r12d
0x1800c4255  jnz     loc_1800C4393
0x1800c425b  lea     rcx, gBndFailoverEndpointCS; lpCriticalSection
0x1800c4262  call    cs:__imp_EnterCriticalSection
0x1800c4269  nop     dword ptr [rax+rax+00h]
0x1800c426e  lea     edx, [r12+2]
0x1800c4273  mov     r9, rbx
0x1800c4276  lea     r8, gRecvThreadEventTotal
0x1800c427d  lea     ecx, [rdx-1]
0x1800c4280  call    DhcpBNDProcessNewFoReqs
0x1800c4285  mov     ecx, eax
0x1800c4287  mov     rcx, [rbx+rcx*8]; hEvent
0x1800c428b  test    rcx, rcx
0x1800c428e  jz      short loc_1800C42C7
0x1800c4290  call    cs:__imp_WSAResetEvent
0x1800c4297  nop     dword ptr [rax+rax+00h]
0x1800c429c  test    eax, eax
0x1800c429e  jnz     short loc_1800C42C7
0x1800c42a0  call    cs:__imp_WSAGetLastError
0x1800c42a7  nop     dword ptr [rax+rax+00h]
0x1800c42ac  mov     r9d, 0D27h
0x1800c42b2  lea     r8, aWsaresetevent; "WSAResetEvent"
0x1800c42b9  mov     ecx, eax
0x1800c42bb  lea     rdx, aBndrecvthread; "BndRecvThread"
0x1800c42c2  call    DhcpPrintFOErrorEx
0x1800c42c7  lea     rbx, gBndRecvInitCloseFailoverEndpoint
0x1800c42ce  mov     edi, 40h ; '@'
0x1800c42d3  mov     rax, [rbx]
0x1800c42d6  test    rax, rax
0x1800c42d9  jz      loc_1800C435F
0x1800c42df  cmp     dword ptr [rbx+0Ch], 1
0x1800c42e3  jnz     short loc_1800C4315
0x1800c42e5  mov     rcx, [rax+190h]; hEvent
0x1800c42ec  test    rcx, rcx
0x1800c42ef  jz      short loc_1800C4358
0x1800c42f1  call    cs:__imp_WSASetEvent
0x1800c42f8  nop     dword ptr [rax+rax+00h]
0x1800c42fd  test    eax, eax
0x1800c42ff  jnz     short loc_1800C4358
0x1800c4301  call    cs:__imp_WSAGetLastError
0x1800c4308  nop     dword ptr [rax+rax+00h]
0x1800c430d  mov     r9d, 0D30h
0x1800c4313  jmp     short loc_1800C4343
0x1800c4315  mov     rcx, [rax+1B8h]; hEvent
0x1800c431c  test    rcx, rcx
0x1800c431f  jz      short loc_1800C4358
0x1800c4321  call    cs:__imp_WSASetEvent
0x1800c4328  nop     dword ptr [rax+rax+00h]
0x1800c432d  test    eax, eax
0x1800c432f  jnz     short loc_1800C4358
0x1800c4331  call    cs:__imp_WSAGetLastError
0x1800c4338  nop     dword ptr [rax+rax+00h]
0x1800c433d  mov     r9d, 0D34h
0x1800c4343  lea     r8, aWsasetevent; "WSASetEvent"
0x1800c434a  mov     ecx, eax
0x1800c434c  lea     rdx, aBndrecvthread; "BndRecvThread"
0x1800c4353  call    DhcpPrintFOErrorEx
0x1800c4358  mov     [rbx+8], r14d
0x1800c435c  mov     [rbx], r14
0x1800c435f  add     rbx, 10h
0x1800c4363  sub     rdi, 1
0x1800c4367  jnz     loc_1800C42D3
0x1800c436d  lea     rcx, gBndFailoverEndpointCS; lpCriticalSection
0x1800c4374  call    cs:__imp_LeaveCriticalSection
0x1800c437b  nop     dword ptr [rax+rax+00h]
0x1800c4380  lea     rdi, WPP_GLOBAL_Control
0x1800c4387  lea     rbx, gRecvThreadEventArray
0x1800c438e  jmp     loc_1800C41F9
0x1800c4393  cmp     r12d, 1
0x1800c4397  jz      loc_1800C4741
0x1800c439d  cmp     r12d, cs:gRecvThreadEventTotal
0x1800c43a4  mov     r13d, r12d
0x1800c43a7  jnb     loc_1800C41F9
0x1800c43ad  cmp     r13d, r12d
0x1800c43b0  jz      short loc_1800C43E8
0x1800c43b2  xor     r9d, r9d; dwTimeout
0x1800c43b5  mov     eax, r13d
0x1800c43b8  mov     [rsp+58h+fAlertable], r14d; fAlertable
0x1800c43bd  lea     ecx, [r9+1]; cEvents
0x1800c43c1  mov     r8d, ecx; fWaitAll
0x1800c43c4  lea     rdx, [rbx+rax*8]; lphEvents
0x1800c43c8  call    cs:__imp_WSAWaitForMultipleEvents
0x1800c43cf  nop     dword ptr [rax+rax+00h]
0x1800c43d4  cmp     eax, 0FFFFFFFFh
0x1800c43d7  jz      loc_1800C471E
0x1800c43dd  cmp     eax, 102h
0x1800c43e2  jz      loc_1800C471E
0x1800c43e8  lea     eax, [r13-2]
0x1800c43ec  lea     rbx, gBndRecvFailoverEndpoints
0x1800c43f3  mov     rbx, [rbx+rax*8]
0x1800c43f7  test    rbx, rbx
0x1800c43fa  jnz     short loc_1800C4431
0x1800c43fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c4403  cmp     rcx, rdi
0x1800c4406  jz      loc_1800C471E
0x1800c440c  test    dword ptr [rcx+1Ch], 800000h
0x1800c4413  jz      loc_1800C471E
0x1800c4419  mov     rcx, [rcx+10h]
0x1800c441d  lea     edx, [rbx+57h]
0x1800c4420  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800c4427  call    WPP_SF_
0x1800c442c  jmp     loc_1800C471E
0x1800c4431  lea     r15, [rbx+48h]
0x1800c4435  mov     rcx, r15; SRWLock
0x1800c4438  call    cs:__imp_AcquireSRWLockShared
0x1800c443f  nop     dword ptr [rax+rax+00h]
0x1800c4444  mov     rcx, [rbx+58h]
0x1800c4448  call    MessageQGetElement
0x1800c444d  mov     rcx, r15; SRWLock
0x1800c4450  mov     rsi, rax
0x1800c4453  call    cs:__imp_ReleaseSRWLockShared
0x1800c445a  nop     dword ptr [rax+rax+00h]
0x1800c445f  test    rsi, rsi
0x1800c4462  jnz     short loc_1800C448D
0x1800c4464  mov     r8, rbx
0x1800c4467  lea     edx, [rsi+4]
0x1800c446a  lea     ecx, [rsi+8]
0x1800c446d  call    DhcpBNDHandleErrorConditions
0x1800c4472  cmp     eax, 4
0x1800c4475  jz      loc_1800C471E
0x1800c447b  cmp     eax, 5
0x1800c447e  jz      loc_1800C4387
0x1800c4484  cmp     eax, 6
0x1800c4487  jz      loc_1800C47AE
0x1800c448d  mov     rax, [rsi+10h]
0x1800c4491  mov     rcx, [rax+10h]
0x1800c4495  cmp     byte ptr [rcx+2], 3
0x1800c4499  jnz     short loc_1800C44DA
0x1800c449b  mov     rdx, rsi
0x1800c449e  mov     rcx, rbx
0x1800c44a1  call    DhcpBNDProcessIncomingBndUpdates
0x1800c44a6  test    eax, eax
0x1800c44a8  jz      loc_1800C471E
0x1800c44ae  mov     r8, rbx
0x1800c44b1  xor     edx, edx
0x1800c44b3  mov     ecx, eax
0x1800c44b5  call    DhcpBNDHandleErrorConditions
0x1800c44ba  cmp     eax, 4
0x1800c44bd  jz      loc_1800C471E
0x1800c44c3  cmp     eax, 5
0x1800c44c6  jz      loc_1800C4387
0x1800c44cc  cmp     eax, 6
0x1800c44cf  jz      loc_1800C47AE
0x1800c44d5  jmp     loc_1800C471E
0x1800c44da  mov     rcx, r15; SRWLock
0x1800c44dd  call    cs:__imp_AcquireSRWLockExclusive
0x1800c44e4  nop     dword ptr [rax+rax+00h]
0x1800c44e9  mov     rdi, [rbx+68h]
0x1800c44ed  mov     ebp, r14d
0x1800c44f0  lea     rcx, [rdi+20h]; lpCriticalSection
0x1800c44f4  call    cs:__imp_EnterCriticalSection
0x1800c44fb  nop     dword ptr [rax+rax+00h]
0x1800c4500  mov     rdx, [rdi]
0x1800c4503  cmp     rdx, [rbx+68h]
0x1800c4507  jz      short loc_1800C4563
0x1800c4509  mov     rax, [rsi+10h]
0x1800c450d  mov     rcx, [rax+10h]
0x1800c4511  mov     r8d, [rcx+8]
0x1800c4515  mov     r9, rdx
0x1800c4518  mov     [rsp+58h+arg_0], rdx
0x1800c451d  mov     rdx, [rdx]
0x1800c4520  mov     rax, [r9+10h]
0x1800c4524  mov     rcx, [rax+10h]
0x1800c4528  cmp     r8d, [rcx+8]
0x1800c452c  jz      short loc_1800C4536
0x1800c452e  cmp     rdx, [rbx+68h]
0x1800c4532  jnz     short loc_1800C4515
0x1800c4534  jmp     short loc_1800C4563
0x1800c4536  mov     ebp, 1
0x1800c453b  cmp     [rdx+8], r9
0x1800c453f  jnz     loc_1800C473A
0x1800c4545  mov     rax, [r9+8]
0x1800c4549  cmp     [rax], r9
0x1800c454c  jnz     loc_1800C473A
0x1800c4552  mov     [rax], rdx
0x1800c4555  mov     [rdx+8], rax
0x1800c4559  dec     dword ptr [rdi+10h]
0x1800c455c  lock dec cs:DhcpGlobalFailoverBndUpdPending
0x1800c4563  lea     rcx, [rdi+20h]; lpCriticalSection
0x1800c4567  call    cs:__imp_LeaveCriticalSection
0x1800c456e  nop     dword ptr [rax+rax+00h]
0x1800c4573  xor     r14d, r14d
0x1800c4576  test    ebp, ebp
0x1800c4578  jz      loc_1800C46CA
0x1800c457e  dec     dword ptr [rbx+78h]
0x1800c4581  mov     rcx, [rbx+70h]; hEvent
0x1800c4585  test    rcx, rcx
0x1800c4588  jz      short loc_1800C45C1
0x1800c458a  call    cs:__imp_WSASetEvent
0x1800c4591  nop     dword ptr [rax+rax+00h]
0x1800c4596  test    eax, eax
0x1800c4598  jnz     short loc_1800C45C1
0x1800c459a  call    cs:__imp_WSAGetLastError
0x1800c45a1  nop     dword ptr [rax+rax+00h]
0x1800c45a6  mov     r9d, 0D99h
0x1800c45ac  lea     r8, aWsasetevent; "WSASetEvent"
0x1800c45b3  mov     ecx, eax
0x1800c45b5  lea     rdx, aDhcpbndreceive; "DhcpBNDReceiveThread"
0x1800c45bc  call    DhcpPrintFOErrorEx
0x1800c45c1  mov     rax, [rsi+10h]
0x1800c45c5  mov     edi, [rbx+220h]
0x1800c45cb  mov     rcx, [rax+10h]
0x1800c45cf  mov     ecx, [rcx+8]; netlong
0x1800c45d2  call    cs:__imp_ntohl
0x1800c45d9  nop     dword ptr [rax+rax+00h]
0x1800c45de  cmp     edi, eax
0x1800c45e0  jnz     loc_1800C467B
0x1800c45e6  test    edi, edi
0x1800c45e8  jz      loc_1800C467B
0x1800c45ee  mov     rcx, [rbx+260h]; hEvent
0x1800c45f5  test    rcx, rcx
0x1800c45f8  jz      short loc_1800C4631
0x1800c45fa  call    cs:__imp_WSASetEvent
0x1800c4601  nop     dword ptr [rax+rax+00h]
0x1800c4606  test    eax, eax
0x1800c4608  jnz     short loc_1800C4631
0x1800c460a  call    cs:__imp_WSAGetLastError
0x1800c4611  nop     dword ptr [rax+rax+00h]
0x1800c4616  mov     r9d, 0D9Dh
0x1800c461c  lea     r8, aWsasetevent; "WSASetEvent"
0x1800c4623  mov     ecx, eax
0x1800c4625  lea     rdx, aDhcpbndreceive; "DhcpBNDReceiveThread"
0x1800c462c  call    DhcpPrintFOErrorEx
0x1800c4631  mov     rcx, [rbx+110h]; hEvent
0x1800c4638  test    rcx, rcx
0x1800c463b  jz      short loc_1800C4674
0x1800c463d  call    cs:__imp_WSASetEvent
0x1800c4644  nop     dword ptr [rax+rax+00h]
0x1800c4649  test    eax, eax
0x1800c464b  jnz     short loc_1800C4674
0x1800c464d  call    cs:__imp_WSAGetLastError
0x1800c4654  nop     dword ptr [rax+rax+00h]
0x1800c4659  mov     r9d, 0D9Eh
0x1800c465f  lea     r8, aWsasetevent; "WSASetEvent"
0x1800c4666  mov     ecx, eax
0x1800c4668  lea     rdx, aDhcpbndreceive; "DhcpBNDReceiveThread"
0x1800c466f  call    DhcpPrintFOErrorEx
0x1800c4674  mov     [rbx+220h], r14d
0x1800c467b  mov     rcx, r15; SRWLock
0x1800c467e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c4685  nop     dword ptr [rax+rax+00h]
0x1800c468a  mov     rdx, [rsp+58h+arg_0]; LPVOID
0x1800c468f  mov     r8, rbx
0x1800c4692  mov     rcx, rsi; lpMem
0x1800c4695  call    DhcpBNDProcessIncomingBndAcks
0x1800c469a  test    eax, eax
0x1800c469c  jz      short loc_1800C46C1
0x1800c469e  mov     r8, rbx
0x1800c46a1  xor     edx, edx
0x1800c46a3  mov     ecx, eax
0x1800c46a5  call    DhcpBNDHandleErrorConditions
0x1800c46aa  cmp     eax, 4
0x1800c46ad  jz      short loc_1800C46C1
0x1800c46af  cmp     eax, 5
0x1800c46b2  jz      loc_1800C4380
0x1800c46b8  cmp     eax, 6
0x1800c46bb  jz      loc_1800C47AE
0x1800c46c1  lea     rdi, WPP_GLOBAL_Control
  ... truncated ...
```
