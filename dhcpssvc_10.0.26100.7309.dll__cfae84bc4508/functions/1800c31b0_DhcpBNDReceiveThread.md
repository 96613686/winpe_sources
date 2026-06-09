# DhcpBNDReceiveThread

- ea: `0x1800c31b0`
- end: `0x1800c37dc`
- name: `DhcpBNDReceiveThread`
- size: `1580`
- prototype: `ULONG __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002854`
- `0x18000323c`
- `0x18001ceb4`
- `0x1800bf90c`
- `0x1800c0a64`
- `0x1800c0dc0`
- `0x1800c1540`
- `0x1800c31b0`
- `0x1800cb9dc`
- `0x1800cbc3c`

## import_xrefs

- `WS2_32!WSAResetEvent` at `0x1800c32a0`
- `WS2_32!WSAResetEvent` at `0x1800c32a0`
- `WS2_32!WSASetEvent` at `0x1800c3301`
- `WS2_32!WSASetEvent` at `0x1800c3331`
- `WS2_32!WSASetEvent` at `0x1800c359a`
- `WS2_32!WSASetEvent` at `0x1800c360a`
- `WS2_32!WSASetEvent` at `0x1800c364d`
- `WS2_32!WSASetEvent` at `0x1800c3787`
- `WS2_32!WSASetEvent` at `0x1800c3301`
- `WS2_32!WSASetEvent` at `0x1800c3331`
- `WS2_32!WSASetEvent` at `0x1800c359a`
- `WS2_32!WSASetEvent` at `0x1800c360a`
- `WS2_32!WSASetEvent` at `0x1800c364d`
- `WS2_32!WSASetEvent` at `0x1800c3787`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800c321e`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800c33d8`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800c321e`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800c33d8`
- `WS2_32!__imp_ntohl` at `0x1800c35e2`
- `WS2_32!__imp_ntohl` at `0x1800c35e2`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c32b0`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c3311`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c3341`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c35aa`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c361a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c365d`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c3797`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c32b0`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c3311`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c3341`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c35aa`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c361a`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c365d`
- `WS2_32!__imp_WSAGetLastError` at `0x1800c3797`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800c368e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800c36dd`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800c368e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800c36dd`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800c34ed`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800c34ed`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800c3463`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800c3463`
- `KERNEL32!AcquireSRWLockShared` at `0x1800c3448`
- `KERNEL32!AcquireSRWLockShared` at `0x1800c3448`
- `KERNEL32!EnterCriticalSection` at `0x1800c3272`
- `KERNEL32!EnterCriticalSection` at `0x1800c3504`
- `KERNEL32!EnterCriticalSection` at `0x1800c3272`
- `KERNEL32!EnterCriticalSection` at `0x1800c3504`
- `KERNEL32!LeaveCriticalSection` at `0x1800c3384`
- `KERNEL32!LeaveCriticalSection` at `0x1800c3577`
- `KERNEL32!LeaveCriticalSection` at `0x1800c3384`
- `KERNEL32!LeaveCriticalSection` at `0x1800c3577`

## string_xrefs

- `0x1800c35c5`: `DhcpBNDReceiveThread`
- `0x1800c3635`: `DhcpBNDReceiveThread`
- `0x1800c3678`: `DhcpBNDReceiveThread`
- `0x1800c32cb`: `BndRecvThread`
- `0x1800c335c`: `BndRecvThread`
- `0x1800c37b2`: `BndRecvThread`

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
      *(_QWORD *)v6 = 0;
      v6[2] = 0;
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
          v17 = DhcpBNDProcessIncomingBndUpdates((RTL_SRWLOCK *)v15, v16);
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
0x1800c31b0  mov     [rsp+arg_8], rbx
0x1800c31b5  mov     [rsp+arg_10], rbp
0x1800c31ba  mov     [rsp+arg_18], rsi
0x1800c31bf  push    rdi
0x1800c31c0  push    r12
0x1800c31c2  push    r13
0x1800c31c4  push    r14
0x1800c31c6  push    r15
0x1800c31c8  sub     rsp, 30h
0x1800c31cc  mov     edx, cs:gRecvThreadEventTotal
0x1800c31d2  lea     rbx, gRecvThreadEventArray
0x1800c31d9  mov     rax, cs:gStartBndRecvProcessingReqEvent
0x1800c31e0  lea     rdi, WPP_GLOBAL_Control
0x1800c31e7  xor     r14d, r14d
0x1800c31ea  mov     [rsp+58h+arg_0], r14
0x1800c31ef  mov     [rbx+rdx*8], rax
0x1800c31f3  inc     edx
0x1800c31f5  mov     rax, cs:gTerminateBndRecvThreadEvent
0x1800c31fc  mov     [rbx+rdx*8], rax
0x1800c3200  lea     eax, [rdx+1]
0x1800c3203  mov     cs:gRecvThreadEventTotal, eax
0x1800c3209  mov     ecx, cs:gRecvThreadEventTotal; cEvents
0x1800c320f  or      r9d, 0FFFFFFFFh; dwTimeout
0x1800c3213  xor     r8d, r8d; fWaitAll
0x1800c3216  mov     [rsp+58h+fAlertable], r14d; fAlertable
0x1800c321b  mov     rdx, rbx; lphEvents
0x1800c321e  call    cs:__imp_WSAWaitForMultipleEvents
0x1800c3225  nop     dword ptr [rax+rax+00h]
0x1800c322a  mov     r12d, eax
0x1800c322d  cmp     eax, 0FFFFFFFFh
0x1800c3230  jnz     short loc_1800C3262
0x1800c3232  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3239  cmp     rcx, rdi
0x1800c323c  jz      short loc_1800C3209
0x1800c323e  test    dword ptr [rcx+1Ch], 800000h
0x1800c3245  jz      short loc_1800C3209
0x1800c3247  mov     rcx, [rcx+10h]
0x1800c324b  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800c3252  mov     edx, 55h ; 'U'
0x1800c3257  or      r9d, 0FFFFFFFFh
0x1800c325b  call    WPP_SF_D
0x1800c3260  jmp     short loc_1800C3209
0x1800c3262  test    r12d, r12d
0x1800c3265  jnz     loc_1800C33A3
0x1800c326b  lea     rcx, gBndFailoverEndpointCS; lpCriticalSection
0x1800c3272  call    cs:__imp_EnterCriticalSection
0x1800c3279  nop     dword ptr [rax+rax+00h]
0x1800c327e  lea     edx, [r12+2]
0x1800c3283  mov     r9, rbx
0x1800c3286  lea     r8, gRecvThreadEventTotal
0x1800c328d  lea     ecx, [rdx-1]
0x1800c3290  call    DhcpBNDProcessNewFoReqs
0x1800c3295  mov     ecx, eax
0x1800c3297  mov     rcx, [rbx+rcx*8]; hEvent
0x1800c329b  test    rcx, rcx
0x1800c329e  jz      short loc_1800C32D7
0x1800c32a0  call    cs:__imp_WSAResetEvent
0x1800c32a7  nop     dword ptr [rax+rax+00h]
0x1800c32ac  test    eax, eax
0x1800c32ae  jnz     short loc_1800C32D7
0x1800c32b0  call    cs:__imp_WSAGetLastError
0x1800c32b7  nop     dword ptr [rax+rax+00h]
0x1800c32bc  mov     r9d, 0D27h
0x1800c32c2  lea     r8, aWsaresetevent; "WSAResetEvent"
0x1800c32c9  mov     ecx, eax
0x1800c32cb  lea     rdx, aBndrecvthread; "BndRecvThread"
0x1800c32d2  call    DhcpPrintFOErrorEx
0x1800c32d7  lea     rbx, gBndRecvInitCloseFailoverEndpoint
0x1800c32de  mov     edi, 40h ; '@'
0x1800c32e3  mov     rax, [rbx]
0x1800c32e6  test    rax, rax
0x1800c32e9  jz      loc_1800C336F
0x1800c32ef  cmp     dword ptr [rbx+0Ch], 1
0x1800c32f3  jnz     short loc_1800C3325
0x1800c32f5  mov     rcx, [rax+190h]; hEvent
0x1800c32fc  test    rcx, rcx
0x1800c32ff  jz      short loc_1800C3368
0x1800c3301  call    cs:__imp_WSASetEvent
0x1800c3308  nop     dword ptr [rax+rax+00h]
0x1800c330d  test    eax, eax
0x1800c330f  jnz     short loc_1800C3368
0x1800c3311  call    cs:__imp_WSAGetLastError
0x1800c3318  nop     dword ptr [rax+rax+00h]
0x1800c331d  mov     r9d, 0D30h
0x1800c3323  jmp     short loc_1800C3353
0x1800c3325  mov     rcx, [rax+1B8h]; hEvent
0x1800c332c  test    rcx, rcx
0x1800c332f  jz      short loc_1800C3368
0x1800c3331  call    cs:__imp_WSASetEvent
0x1800c3338  nop     dword ptr [rax+rax+00h]
0x1800c333d  test    eax, eax
0x1800c333f  jnz     short loc_1800C3368
0x1800c3341  call    cs:__imp_WSAGetLastError
0x1800c3348  nop     dword ptr [rax+rax+00h]
0x1800c334d  mov     r9d, 0D34h
0x1800c3353  lea     r8, aWsasetevent; "WSASetEvent"
0x1800c335a  mov     ecx, eax
0x1800c335c  lea     rdx, aBndrecvthread; "BndRecvThread"
0x1800c3363  call    DhcpPrintFOErrorEx
0x1800c3368  mov     [rbx], r14
0x1800c336b  mov     [rbx+8], r14d
0x1800c336f  add     rbx, 10h
0x1800c3373  sub     rdi, 1
0x1800c3377  jnz     loc_1800C32E3
0x1800c337d  lea     rcx, gBndFailoverEndpointCS; lpCriticalSection
0x1800c3384  call    cs:__imp_LeaveCriticalSection
0x1800c338b  nop     dword ptr [rax+rax+00h]
0x1800c3390  lea     rdi, WPP_GLOBAL_Control
0x1800c3397  lea     rbx, gRecvThreadEventArray
0x1800c339e  jmp     loc_1800C3209
0x1800c33a3  cmp     r12d, 1
0x1800c33a7  jz      loc_1800C3751
0x1800c33ad  cmp     r12d, cs:gRecvThreadEventTotal
0x1800c33b4  mov     r13d, r12d
0x1800c33b7  jnb     loc_1800C3209
0x1800c33bd  cmp     r13d, r12d
0x1800c33c0  jz      short loc_1800C33F8
0x1800c33c2  xor     r9d, r9d; dwTimeout
0x1800c33c5  mov     eax, r13d
0x1800c33c8  mov     [rsp+58h+fAlertable], r14d; fAlertable
0x1800c33cd  lea     ecx, [r9+1]; cEvents
0x1800c33d1  mov     r8d, ecx; fWaitAll
0x1800c33d4  lea     rdx, [rbx+rax*8]; lphEvents
0x1800c33d8  call    cs:__imp_WSAWaitForMultipleEvents
0x1800c33df  nop     dword ptr [rax+rax+00h]
0x1800c33e4  cmp     eax, 0FFFFFFFFh
0x1800c33e7  jz      loc_1800C372E
0x1800c33ed  cmp     eax, 102h
0x1800c33f2  jz      loc_1800C372E
0x1800c33f8  lea     eax, [r13-2]
0x1800c33fc  lea     rbx, gBndRecvFailoverEndpoints
0x1800c3403  mov     rbx, [rbx+rax*8]
0x1800c3407  test    rbx, rbx
0x1800c340a  jnz     short loc_1800C3441
0x1800c340c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c3413  cmp     rcx, rdi
0x1800c3416  jz      loc_1800C372E
0x1800c341c  test    dword ptr [rcx+1Ch], 800000h
0x1800c3423  jz      loc_1800C372E
0x1800c3429  mov     rcx, [rcx+10h]
0x1800c342d  lea     edx, [rbx+57h]
0x1800c3430  lea     r8, WPP_312e5744b13939c4b6095fd4c29e124f_Traceguids
0x1800c3437  call    WPP_SF_
0x1800c343c  jmp     loc_1800C372E
0x1800c3441  lea     r15, [rbx+48h]
0x1800c3445  mov     rcx, r15; SRWLock
0x1800c3448  call    cs:__imp_AcquireSRWLockShared
0x1800c344f  nop     dword ptr [rax+rax+00h]
0x1800c3454  mov     rcx, [rbx+58h]
0x1800c3458  call    MessageQGetElement
0x1800c345d  mov     rcx, r15; SRWLock
0x1800c3460  mov     rsi, rax
0x1800c3463  call    cs:__imp_ReleaseSRWLockShared
0x1800c346a  nop     dword ptr [rax+rax+00h]
0x1800c346f  test    rsi, rsi
0x1800c3472  jnz     short loc_1800C349D
0x1800c3474  mov     r8, rbx
0x1800c3477  lea     edx, [rsi+4]
0x1800c347a  lea     ecx, [rsi+8]
0x1800c347d  call    DhcpBNDHandleErrorConditions
0x1800c3482  cmp     eax, 4
0x1800c3485  jz      loc_1800C372E
0x1800c348b  cmp     eax, 5
0x1800c348e  jz      loc_1800C3397
0x1800c3494  cmp     eax, 6
0x1800c3497  jz      loc_1800C37BE
0x1800c349d  mov     rax, [rsi+10h]
0x1800c34a1  mov     rcx, [rax+10h]
0x1800c34a5  cmp     byte ptr [rcx+2], 3
0x1800c34a9  jnz     short loc_1800C34EA
0x1800c34ab  mov     rdx, rsi
0x1800c34ae  mov     rcx, rbx
0x1800c34b1  call    DhcpBNDProcessIncomingBndUpdates
0x1800c34b6  test    eax, eax
0x1800c34b8  jz      loc_1800C372E
0x1800c34be  mov     r8, rbx
0x1800c34c1  xor     edx, edx
0x1800c34c3  mov     ecx, eax
0x1800c34c5  call    DhcpBNDHandleErrorConditions
0x1800c34ca  cmp     eax, 4
0x1800c34cd  jz      loc_1800C372E
0x1800c34d3  cmp     eax, 5
0x1800c34d6  jz      loc_1800C3397
0x1800c34dc  cmp     eax, 6
0x1800c34df  jz      loc_1800C37BE
0x1800c34e5  jmp     loc_1800C372E
0x1800c34ea  mov     rcx, r15; SRWLock
0x1800c34ed  call    cs:__imp_AcquireSRWLockExclusive
0x1800c34f4  nop     dword ptr [rax+rax+00h]
0x1800c34f9  mov     rdi, [rbx+68h]
0x1800c34fd  mov     ebp, r14d
0x1800c3500  lea     rcx, [rdi+20h]; lpCriticalSection
0x1800c3504  call    cs:__imp_EnterCriticalSection
0x1800c350b  nop     dword ptr [rax+rax+00h]
0x1800c3510  mov     rdx, [rdi]
0x1800c3513  cmp     rdx, [rbx+68h]
0x1800c3517  jz      short loc_1800C3573
0x1800c3519  mov     rax, [rsi+10h]
0x1800c351d  mov     rcx, [rax+10h]
0x1800c3521  mov     r8d, [rcx+8]
0x1800c3525  mov     r9, rdx
0x1800c3528  mov     [rsp+58h+arg_0], rdx
0x1800c352d  mov     rdx, [rdx]
0x1800c3530  mov     rax, [r9+10h]
0x1800c3534  mov     rcx, [rax+10h]
0x1800c3538  cmp     r8d, [rcx+8]
0x1800c353c  jz      short loc_1800C3546
0x1800c353e  cmp     rdx, [rbx+68h]
0x1800c3542  jnz     short loc_1800C3525
0x1800c3544  jmp     short loc_1800C3573
0x1800c3546  mov     ebp, 1
0x1800c354b  cmp     [rdx+8], r9
0x1800c354f  jnz     loc_1800C374A
0x1800c3555  mov     rax, [r9+8]
0x1800c3559  cmp     [rax], r9
0x1800c355c  jnz     loc_1800C374A
0x1800c3562  mov     [rax], rdx
0x1800c3565  mov     [rdx+8], rax
0x1800c3569  dec     dword ptr [rdi+10h]
0x1800c356c  lock dec cs:DhcpGlobalFailoverBndUpdPending
0x1800c3573  lea     rcx, [rdi+20h]; lpCriticalSection
0x1800c3577  call    cs:__imp_LeaveCriticalSection
0x1800c357e  nop     dword ptr [rax+rax+00h]
0x1800c3583  xor     r14d, r14d
0x1800c3586  test    ebp, ebp
0x1800c3588  jz      loc_1800C36DA
0x1800c358e  dec     dword ptr [rbx+78h]
0x1800c3591  mov     rcx, [rbx+70h]; hEvent
0x1800c3595  test    rcx, rcx
0x1800c3598  jz      short loc_1800C35D1
0x1800c359a  call    cs:__imp_WSASetEvent
0x1800c35a1  nop     dword ptr [rax+rax+00h]
0x1800c35a6  test    eax, eax
0x1800c35a8  jnz     short loc_1800C35D1
0x1800c35aa  call    cs:__imp_WSAGetLastError
0x1800c35b1  nop     dword ptr [rax+rax+00h]
0x1800c35b6  mov     r9d, 0D99h
0x1800c35bc  lea     r8, aWsasetevent; "WSASetEvent"
0x1800c35c3  mov     ecx, eax
0x1800c35c5  lea     rdx, aDhcpbndreceive; "DhcpBNDReceiveThread"
0x1800c35cc  call    DhcpPrintFOErrorEx
0x1800c35d1  mov     rax, [rsi+10h]
0x1800c35d5  mov     edi, [rbx+220h]
0x1800c35db  mov     rcx, [rax+10h]
0x1800c35df  mov     ecx, [rcx+8]; netlong
0x1800c35e2  call    cs:__imp_ntohl
0x1800c35e9  nop     dword ptr [rax+rax+00h]
0x1800c35ee  cmp     edi, eax
0x1800c35f0  jnz     loc_1800C368B
0x1800c35f6  test    edi, edi
0x1800c35f8  jz      loc_1800C368B
0x1800c35fe  mov     rcx, [rbx+260h]; hEvent
0x1800c3605  test    rcx, rcx
0x1800c3608  jz      short loc_1800C3641
0x1800c360a  call    cs:__imp_WSASetEvent
0x1800c3611  nop     dword ptr [rax+rax+00h]
0x1800c3616  test    eax, eax
0x1800c3618  jnz     short loc_1800C3641
0x1800c361a  call    cs:__imp_WSAGetLastError
0x1800c3621  nop     dword ptr [rax+rax+00h]
0x1800c3626  mov     r9d, 0D9Dh
0x1800c362c  lea     r8, aWsasetevent; "WSASetEvent"
0x1800c3633  mov     ecx, eax
0x1800c3635  lea     rdx, aDhcpbndreceive; "DhcpBNDReceiveThread"
0x1800c363c  call    DhcpPrintFOErrorEx
0x1800c3641  mov     rcx, [rbx+110h]; hEvent
0x1800c3648  test    rcx, rcx
0x1800c364b  jz      short loc_1800C3684
0x1800c364d  call    cs:__imp_WSASetEvent
0x1800c3654  nop     dword ptr [rax+rax+00h]
0x1800c3659  test    eax, eax
0x1800c365b  jnz     short loc_1800C3684
0x1800c365d  call    cs:__imp_WSAGetLastError
0x1800c3664  nop     dword ptr [rax+rax+00h]
0x1800c3669  mov     r9d, 0D9Eh
0x1800c366f  lea     r8, aWsasetevent; "WSASetEvent"
0x1800c3676  mov     ecx, eax
0x1800c3678  lea     rdx, aDhcpbndreceive; "DhcpBNDReceiveThread"
0x1800c367f  call    DhcpPrintFOErrorEx
0x1800c3684  mov     [rbx+220h], r14d
0x1800c368b  mov     rcx, r15; SRWLock
0x1800c368e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c3695  nop     dword ptr [rax+rax+00h]
0x1800c369a  mov     rdx, [rsp+58h+arg_0]; LPVOID
0x1800c369f  mov     r8, rbx
0x1800c36a2  mov     rcx, rsi; lpMem
0x1800c36a5  call    DhcpBNDProcessIncomingBndAcks
0x1800c36aa  test    eax, eax
0x1800c36ac  jz      short loc_1800C36D1
0x1800c36ae  mov     r8, rbx
0x1800c36b1  xor     edx, edx
0x1800c36b3  mov     ecx, eax
0x1800c36b5  call    DhcpBNDHandleErrorConditions
0x1800c36ba  cmp     eax, 4
0x1800c36bd  jz      short loc_1800C36D1
0x1800c36bf  cmp     eax, 5
0x1800c36c2  jz      loc_1800C3390
0x1800c36c8  cmp     eax, 6
0x1800c36cb  jz      loc_1800C37BE
0x1800c36d1  lea     rdi, WPP_GLOBAL_Control
  ... truncated ...
```
