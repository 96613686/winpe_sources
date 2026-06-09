# HandleControlMessage

- ea: `0x1800485dc`
- end: `0x18004901c`
- name: `HandleControlMessage`
- size: `2624`
- prototype: `__int64 __fastcall(PVOID CompletionContext)`
- caller_count: `1`
- callee_count: `31`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003b760`

## callees

- `0x1800028b8`
- `0x180008250`
- `0x1800222f0`
- `0x180023f14`
- `0x180024674`
- `0x180038104`
- `0x180038118`
- `0x180038944`
- `0x180038988`
- `0x180038a20`
- `0x180038bdc`
- `0x18003ae8c`
- `0x18003cdc8`
- `0x18003dae8`
- `0x1800453ec`
- `0x180045e74`
- `0x180045f50`
- `0x1800475c0`
- `0x1800485dc`
- `0x180049024`
- `0x180049310`
- `0x18004958c`
- `0x18004a2dc`
- `0x18004c204`
- `0x18004c650`
- `0x18004f7cc`
- `0x18004fa0c`
- `0x18004fb58`
- `0x18004fd1c`
- `0x18004fe40`
- `0x180053010`

## import_xrefs

- `ntdll!NtSetIoCompletion` at `0x180048719`
- `ntdll!NtSetIoCompletion` at `0x180048719`
- `ntdll!RtlFreeHeap` at `0x180048fe1`
- `ntdll!RtlFreeHeap` at `0x180048fe1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800486e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800487c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800488ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048a30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048a9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048aef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048c56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048c97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048de4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048e19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048e77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048ee2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048f98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800486e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800487c7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800488ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048a30`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048a9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048aef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048c56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048c97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048de4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048e19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048e77`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048ee2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048f98`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800486c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048761`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800488bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800488d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048930`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048a79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048be2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048c21`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048c81`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048d9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048e52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048ec1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048f74`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800486c7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048761`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800488bf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800488d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048930`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048a79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048be2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048c21`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048c81`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048d9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048e52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048ec1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048f74`

## pseudocode

```c
__int64 __fastcall HandleControlMessage(char *CompletionContext, __int64 a2)
{
  char v4; // cl
  unsigned int *v5; // rbx
  __int64 v6; // r9
  struct _RTL_CRITICAL_SECTION *v8; // rcx
  NTSTATUS v9; // eax
  int v10; // r8d
  int v11; // edx
  _QWORD *v12; // r13
  __int64 v13; // r9
  struct _RTL_CRITICAL_SECTION *v14; // rcx
  _QWORD *v15; // rbx
  _DWORD *v16; // rax
  PVOID *v17; // r8
  _QWORD *v18; // rax
  __int64 v19; // rdx
  unsigned int v20; // edx
  char v21; // dl
  unsigned int v22; // eax
  __int64 v23; // rdx
  unsigned int v24; // ebx
  char *v25; // rax
  int v26; // ecx
  __int64 v27; // rax
  _BYTE *v28; // r15
  int v29; // ebx
  void *v30; // r8
  __int64 v31; // rax
  _BYTE *v32; // rsi
  int v33; // ebx
  char v34; // [rsp+40h] [rbp-58h]
  unsigned int v35; // [rsp+44h] [rbp-54h] BYREF
  int v36; // [rsp+48h] [rbp-50h] BYREF
  unsigned int v37; // [rsp+4Ch] [rbp-4Ch]
  _BYTE v38[24]; // [rsp+50h] [rbp-48h] BYREF

  v35 = 0;
  v36 = 0;
  v4 = xmmword_180063D60;
  v5 = (unsigned int *)(a2 + 8);
  if ( (xmmword_180063D60 & 0x80u) != 0LL )
  {
    WPP_SF_ddd(
      1031,
      161,
      WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids,
      *v5,
      *(_DWORD *)(a2 + 12),
      *(_DWORD *)(a2 + 16));
    v4 = xmmword_180063D60;
  }
  if ( *(_DWORD *)a2 != 305419896 )
  {
    if ( (v4 & 2) != 0 )
      WPP_SF_(1025, 163, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids);
    return 0;
  }
  v6 = *v5;
  if ( (_DWORD)v6 != *((_DWORD *)CompletionContext + 111) - 1 )
  {
    if ( (v4 & 2) != 0 )
      WPP_SF_dd(
        1025,
        164,
        WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids,
        v6,
        *((_DWORD *)CompletionContext + 111) - 1);
    return 0;
  }
  v8 = (struct _RTL_CRITICAL_SECTION *)(CompletionContext + 48);
  if ( *(_BYTE *)(a2 + 24) != 16 )
  {
    EnterCriticalSection(v8);
    v10 = *((_DWORD *)CompletionContext + 108);
    v37 = v10;
    if ( CompletionContext[800] >= 0 )
    {
      v11 = *(_DWORD *)(a2 + 12) + *(_DWORD *)(a2 + 16) - *((_DWORD *)CompletionContext + 110);
      if ( v10 > v11 )
        v11 = v10;
      *((_DWORD *)CompletionContext + 108) = v11;
    }
    v12 = CompletionContext + 400;
    if ( (_QWORD *)*v12 != v12 || (v34 = 1, *((char **)CompletionContext + 52) != CompletionContext + 416) )
      v34 = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
    if ( (*(_BYTE *)(*((_QWORD *)CompletionContext + 27) + 24LL) & 4) == 0
      && v37 <= 2
      && *((_DWORD *)CompletionContext + 108) > 2u )
    {
      if ( *(_QWORD *)CompletionContext )
      {
        DrainSendCompleteQueue(CompletionContext);
        if ( *((_DWORD *)CompletionContext + 32) < *(_DWORD *)(*(_QWORD *)CompletionContext + 64LL) || v34 )
          NotifyAfdOfSendAvail(CompletionContext);
      }
    }
    v13 = (unsigned int)*(char *)(a2 + 24);
    if ( (int)v13 <= 10 )
    {
      if ( (_DWORD)v13 == 10 )
      {
        _InterlockedExchange((volatile __int32 *)CompletionContext + 201, 1);
        HandleRemoteClose(CompletionContext);
        if ( (CompletionContext[800] & 1) == 0 )
          return 40;
        v22 = ContinueGracefulDisconnect(CompletionContext);
        v35 = v22;
        if ( !v22 || (xmmword_180063D60 & 2) == 0 )
          return 40;
        v23 = 169;
        v13 = v22;
LABEL_102:
        WPP_SF_d(1025, v23, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, v13);
        return 40;
      }
      if ( *(_BYTE *)(a2 + 24) )
      {
        if ( (_DWORD)v13 == 1 )
        {
          if ( *((_DWORD *)CompletionContext + 44) != 1 )
            *((_DWORD *)CompletionContext + 44) = 0;
          *((_DWORD *)CompletionContext + 220) = *(_DWORD *)(a2 + 28);
          EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
          if ( *(_DWORD *)(a2 + 28) && *(_BYTE *)(*((_QWORD *)CompletionContext + 2) + 364LL) )
            v21 = 8;
          else
            v21 = 0;
          CompletionContext[801] &= ~8u;
          CompletionContext[801] |= v21;
          LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
          if ( *((_DWORD *)CompletionContext + 38) == 4 )
            SockSanHandleConnectPostProcessing(CompletionContext);
          if ( *(_DWORD *)(a2 + 32) )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
            ++*((_DWORD *)CompletionContext + 113);
            LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
          }
          if ( CompletionContext[208] )
            CheckForSocketDuplicationProtocol(CompletionContext);
          return 40;
        }
        if ( (_DWORD)v13 == 2 )
        {
          if ( (BYTE1(xmmword_180063D60) & 0x10) != 0 )
            WPP_SF_dd(1036, 167, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, 2, *v5);
          EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
          ProcessRdmaReadCompletion(CompletionContext, *(unsigned int *)(a2 + 28), *(unsigned int *)(a2 + 32));
          return 40;
        }
        if ( (_DWORD)v13 != 4 )
        {
          switch ( (_DWORD)v13 )
          {
            case 5:
              if ( (BYTE1(xmmword_180063D60) & 0x10) != 0 )
                WPP_SF_dd(1036, 168, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, 5, *v5);
              ProcessRdmaRecvCompletion(CompletionContext);
              return 40;
            case 7:
              if ( (BYTE1(xmmword_180063D60) & 0x10) != 0 )
                WPP_SF_dd(1036, 171, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, 7, *v5);
              EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
              if ( (CompletionContext[801] & 8) != 0 && *((_DWORD *)CompletionContext + 117) <= 1u )
              {
                LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
                if ( (xmmword_180063D60 & 2) != 0 )
                  WPP_SF_(1025, 172, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids);
                CheckReadvertiseFirstSend(CompletionContext);
              }
              else
              {
                PushLargeRecvFCInfo(
                  (int)CompletionContext,
                  1,
                  *(_DWORD *)(a2 + 28),
                  *(_DWORD *)(a2 + 32),
                  (void *)(a2 + 40));
                LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
                if ( !*((_DWORD *)CompletionContext + 117) )
                {
                  v19 = 1;
                  if ( !*(_DWORD *)(a2 + 36) )
                    v19 = 2;
                  CheckRsMode(CompletionContext, v19);
                }
              }
              return (unsigned int)(*(_DWORD *)(*((_QWORD *)CompletionContext + 2) + 20LL) + 40);
            case 8:
              EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
              if ( *((_DWORD *)CompletionContext + 121) != 3 )
                PushLargeRecvFCInfo((int)CompletionContext, 3, 0, 0, 0);
              if ( (CompletionContext[801] & 8) != 0 )
              {
                v15 = (_QWORD *)*v12;
                if ( (_QWORD *)*v12 != v12 )
                {
                  *((_DWORD *)v15 + 19) &= ~0x800u;
                  if ( (*((_DWORD *)v15 + 19) & 0x80u) != 0 )
                  {
                    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned int *))(*((_QWORD *)CompletionContext + 2)
                                                                                   + 328LL))(
                      *((_QWORD *)CompletionContext + 13),
                      *(_QWORD *)(v15[13] + 96LL),
                      *(unsigned int *)(*((_QWORD *)CompletionContext + 2) + 20LL),
                      &v35);
                    if ( _InterlockedExchangeAdd(*((volatile signed __int32 **)CompletionContext + 1), 0xFFFFFFFF) == 1 )
                      SockDestroySocket(*((_QWORD *)CompletionContext + 1));
                    v16 = (_DWORD *)v15[13];
                    *v16 = 1145324612;
                    v17 = (PVOID *)*((_QWORD *)CompletionContext + 97);
                    if ( *v17 != CompletionContext + 768 )
                      __fastfail(3u);
                    v18 = v16 + 10;
                    v18[1] = v17;
                    *v18 = CompletionContext + 768;
                    *v17 = v18;
                    *((_QWORD *)CompletionContext + 97) = v18;
                    *((_DWORD *)v15 + 19) &= ~0x80u;
                    v15[13] = 0;
                  }
                  else if ( (xmmword_180063D60 & 0x80u) != 0LL )
                  {
                    WPP_SF_q(1031, 170, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, CompletionContext);
                  }
                }
              }
              LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
              CheckRsMode(CompletionContext, 3);
              return 40;
            case 9:
              if ( (BYTE1(xmmword_180063D60) & 0x10) != 0 )
                WPP_SF_dddd(
                  (unsigned int)(v13 - 8),
                  173,
                  WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids,
                  9,
                  *(_DWORD *)(a2 + 8),
                  *(_DWORD *)(a2 + 28),
                  *(_DWORD *)(a2 + 32));
              v14 = (struct _RTL_CRITICAL_SECTION *)(CompletionContext + 48);
              if ( *(_DWORD *)(a2 + 28) == 2 )
              {
                EnterCriticalSection(v14);
                *((_DWORD *)CompletionContext + 120) = *(_DWORD *)(a2 + 32);
              }
              else
              {
                EnterCriticalSection(v14);
                *((_DWORD *)CompletionContext + 117) = *(_DWORD *)(a2 + 32);
              }
              LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
              if ( *(_DWORD *)(a2 + 28) != 2 || *(_DWORD *)(a2 + 32) != 2 )
              {
                HandleModeChange(CompletionContext);
                return 40;
              }
              _InterlockedExchange((volatile __int32 *)CompletionContext + 65, 1);
              goto LABEL_49;
          }
LABEL_110:
          if ( (xmmword_180063D60 & 2) == 0 )
            return 40;
          v23 = 175;
          goto LABEL_102;
        }
        if ( (BYTE1(xmmword_180063D60) & 0x10) != 0 )
          WPP_SF_dd(1036, 166, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, 4, *v5);
        if ( (CompletionContext[801] & 8) != 0 )
        {
          v20 = *(_DWORD *)(*((_QWORD *)CompletionContext + 2) + 20LL) + 32;
          *((_DWORD *)CompletionContext + 221) = *(_DWORD *)(a2 + 4) - v20;
          return v20;
        }
      }
      return 40;
    }
    switch ( (_DWORD)v13 )
    {
      case 0xB:
        v31 = *((_QWORD *)CompletionContext + 2);
        if ( *(_DWORD *)(v31 + 20) <= 0x18u )
        {
          v32 = v38;
        }
        else
        {
          v32 = (_BYTE *)((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(
                           SockPrivateHeap,
                           0,
                           *(unsigned int *)(v31 + 20));
          if ( !v32 )
            return 40;
        }
        EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
        v33 = PopLargeSendFCInfoExt(CompletionContext, &v36, v32, 1);
        LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
        if ( v33 == 2 )
          SendControlMessage(CompletionContext, 0, 0);
        if ( v32 == v38 )
          return 40;
        v30 = v32;
        break;
      case 0xC:
        *((_DWORD *)CompletionContext + 201) = 0;
        return 40;
      case 0xD:
        v27 = *((_QWORD *)CompletionContext + 2);
        if ( *(_DWORD *)(v27 + 20) <= 0x18u )
        {
          v28 = v38;
        }
        else
        {
          v28 = (_BYTE *)((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(
                           SockPrivateHeap,
                           0,
                           *(unsigned int *)(v27 + 20));
          if ( !v28 )
            return 40;
        }
        EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
        v29 = PopLargeRecvFCInfo(CompletionContext, &v36, v28);
        LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
        if ( v29 == 1 )
          SendControlMessage(CompletionContext, 0, 0);
        if ( v28 == v38 )
          return 40;
        v30 = v28;
        break;
      case 0xE:
        EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
        if ( *((_DWORD *)CompletionContext + 114) == *(_DWORD *)(a2 + 28) )
          *(_BYTE *)(*((_QWORD *)CompletionContext + 40) + 80LL) = 1;
        LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
LABEL_49:
        CheckPendingAppRecvs(CompletionContext);
        return 40;
      case 0xF:
        HandleSuspendCommunicationRequest(CompletionContext);
        return 40;
      case 0x11:
        HandleEnlargeBuffersRequest(CompletionContext, *(unsigned int *)(a2 + 28));
        return 40;
      case 0x12:
        v24 = *(_DWORD *)(a2 + 28) - 40;
        if ( (BYTE3(xmmword_180063D60) & 1) != 0 )
          WPP_SF_qD(
            1048,
            174,
            WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids,
            CompletionContext,
            *(_DWORD *)(a2 + 28) - 40);
        EnterCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
        if ( v24 <= *((unsigned __int16 *)CompletionContext + 419) )
        {
          if ( v24 <= *((unsigned __int16 *)CompletionContext + 421) )
            CompletionContext[801] |= 0x10u;
          CompletionContext[801] &= ~2u;
        }
        else
        {
          *((_WORD *)CompletionContext + 422) = v24;
          v25 = (char *)*((_QWORD *)CompletionContext + 46);
          v26 = 0;
          while ( v25 != CompletionContext + 368 )
          {
            v25 = *(char **)v25;
            ++v26;
          }
          if ( v26 == *(_DWORD *)(*((_QWORD *)CompletionContext + 2) + 368LL) )
          {
            LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
            ResizeSendBuffers(CompletionContext);
            return 40;
          }
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
        DrainSendCompleteQueue(CompletionContext);
        return 40;
      default:
        goto LABEL_110;
    }
    RtlFreeHeap(SockPrivateHeap, 0, v30);
    return 40;
  }
  EnterCriticalSection(v8);
  CompletionContext[801] |= 1u;
  LeaveCriticalSection((LPCRITICAL_SECTION)(CompletionContext + 48));
  if ( SockCheckAndReferenceAsyncThread() )
  {
    _InterlockedAdd(*((volatile signed __int32 **)CompletionContext + 1), 1u);
    v9 = NtSetIoCompletion(SockAsyncQueuePort, SockSanResumeDuplicationStub, CompletionContext, 0, 0);
    if ( v9 < 0 )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_d(1025, 165, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids, (unsigned int)v9);
      _InterlockedDecrement(&SockAsyncThreadReferenceCount);
    }
  }
  return 40;
}

```

## disassembly

```asm
0x1800485dc  mov     r11, rsp
0x1800485df  mov     [r11+18h], rbx
0x1800485e3  mov     [r11+20h], rsi
0x1800485e7  push    rdi
0x1800485e8  push    r12
0x1800485ea  push    r13
0x1800485ec  push    r14
0x1800485ee  push    r15
0x1800485f0  sub     rsp, 70h
0x1800485f4  mov     rax, cs:__security_cookie
0x1800485fb  xor     rax, rsp
0x1800485fe  mov     [rsp+98h+var_30], rax
0x180048603  xor     r13d, r13d
0x180048606  mov     rsi, rdx
0x180048609  mov     [r11-54h], r13d
0x18004860d  mov     rdi, rcx
0x180048610  mov     [r11-50h], r13d
0x180048614  mov     cl, byte ptr cs:xmmword_180063D60
0x18004861a  lea     rbx, [rdx+8]
0x18004861e  test    cl, cl
0x180048620  jns     short loc_18004864F
0x180048622  mov     eax, [rsi+10h]
0x180048625  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18004862c  mov     r9d, [rbx]
0x18004862f  mov     edx, 0A1h
0x180048634  mov     dword ptr [rsp+98h+var_70], eax
0x180048638  mov     ecx, 407h
0x18004863d  mov     eax, [rsi+0Ch]
0x180048640  mov     [rsp+98h+CompletionInformation], eax
0x180048644  call    WPP_SF_ddd
0x180048649  mov     cl, byte ptr cs:xmmword_180063D60
0x18004864f  cmp     dword ptr [rsi], 12345678h
0x180048655  jz      short loc_18004867A
0x180048657  mov     r15d, 2
0x18004865d  test    r15b, cl
0x180048660  jz      short loc_1800486AF
0x180048662  mov     edx, 0A3h
0x180048667  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x18004866e  mov     ecx, 401h
0x180048673  call    WPP_SF_
0x180048678  jmp     short loc_1800486AF
0x18004867a  mov     eax, [rdi+1BCh]
0x180048680  mov     r9d, [rbx]
0x180048683  dec     eax
0x180048685  cmp     r9d, eax
0x180048688  jz      short loc_1800486B6
0x18004868a  mov     r15d, 2
0x180048690  test    r15b, cl
0x180048693  jz      short loc_1800486AF
0x180048695  mov     edx, 0A4h
0x18004869a  mov     [rsp+98h+CompletionInformation], eax
0x18004869e  mov     ecx, 401h
0x1800486a3  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x1800486aa  call    WPP_SF_dd
0x1800486af  xor     eax, eax
0x1800486b1  jmp     loc_180048FF4
0x1800486b6  cmp     byte ptr [rsi+18h], 10h
0x1800486ba  lea     r14, [rdi+30h]
0x1800486be  mov     rcx, r14; lpCriticalSection
0x1800486c1  jnz     loc_180048761
0x1800486c7  call    cs:__imp_EnterCriticalSection
0x1800486ce  nop     dword ptr [rax+rax+00h]
0x1800486d3  mov     r12d, 1
0x1800486d9  mov     rcx, r14; lpCriticalSection
0x1800486dc  or      [rdi+321h], r12b
0x1800486e3  call    cs:__imp_LeaveCriticalSection
0x1800486ea  nop     dword ptr [rax+rax+00h]
0x1800486ef  call    SockCheckAndReferenceAsyncThread
0x1800486f4  test    al, al
0x1800486f6  jz      short loc_180048757
0x1800486f8  mov     rax, [rdi+8]
0x1800486fc  lock add [rax], r12d
0x180048700  mov     rcx, cs:SockAsyncQueuePort; IoCompletionPortHandle
0x180048707  lea     rdx, SockSanResumeDuplicationStub; CompletionKey
0x18004870e  xor     r9d, r9d; CompletionStatus
0x180048711  mov     qword ptr [rsp+98h+CompletionInformation], r13; CompletionInformation
0x180048716  mov     r8, rdi; CompletionContext
0x180048719  call    cs:__imp_NtSetIoCompletion
0x180048720  nop     dword ptr [rax+rax+00h]
0x180048725  test    eax, eax
0x180048727  jns     short loc_180048757
0x180048729  lea     r15d, [r12+1]
0x18004872e  test    byte ptr cs:xmmword_180063D60, r15b
0x180048735  jz      short loc_180048750
0x180048737  mov     edx, 0A5h
0x18004873c  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x180048743  mov     ecx, 401h
0x180048748  mov     r9d, eax
0x18004874b  call    WPP_SF_d
0x180048750  lock dec cs:SockAsyncThreadReferenceCount
0x180048757  mov     eax, 28h ; '('
0x18004875c  jmp     loc_180048FF4
0x180048761  call    cs:__imp_EnterCriticalSection
0x180048768  nop     dword ptr [rax+rax+00h]
0x18004876d  mov     r8d, [rdi+1B0h]
0x180048774  mov     [rsp+98h+var_4C], r8d
0x180048779  cmp     [rdi+320h], r13b
0x180048780  jl      short loc_18004879B
0x180048782  mov     edx, [rsi+10h]
0x180048785  sub     edx, [rdi+1B8h]
0x18004878b  add     edx, [rsi+0Ch]
0x18004878e  cmp     r8d, edx
0x180048791  cmovg   edx, r8d
0x180048795  mov     [rdi+1B0h], edx
0x18004879b  lea     r13, [rdi+190h]
0x1800487a2  mov     r12d, 1
0x1800487a8  cmp     [r13+0], r13
0x1800487ac  jnz     short loc_1800487BF
0x1800487ae  lea     rax, [rdi+1A0h]
0x1800487b5  mov     [rsp+98h+var_58], r12b
0x1800487ba  cmp     [rax], rax
0x1800487bd  jz      short loc_1800487C4
0x1800487bf  mov     [rsp+98h+var_58], 0
0x1800487c4  mov     rcx, r14; lpCriticalSection
0x1800487c7  call    cs:__imp_LeaveCriticalSection
0x1800487ce  nop     dword ptr [rax+rax+00h]
0x1800487d3  mov     rax, [rdi+0D8h]
0x1800487da  mov     r15d, 2
0x1800487e0  test    byte ptr [rax+18h], 4
0x1800487e4  jnz     short loc_180048821
0x1800487e6  cmp     [rsp+98h+var_4C], r15d
0x1800487eb  ja      short loc_180048821
0x1800487ed  cmp     [rdi+1B0h], r15d
0x1800487f4  jbe     short loc_180048821
0x1800487f6  cmp     qword ptr [rdi], 0
0x1800487fa  jz      short loc_180048821
0x1800487fc  mov     rcx, rdi
0x1800487ff  call    DrainSendCompleteQueue
0x180048804  mov     rax, [rdi]
0x180048807  mov     ecx, [rax+40h]
0x18004880a  cmp     [rdi+80h], ecx
0x180048810  jb      short loc_180048819
0x180048812  cmp     [rsp+98h+var_58], 0
0x180048817  jz      short loc_180048821
0x180048819  mov     rcx, rdi
0x18004881c  call    NotifyAfdOfSendAvail
0x180048821  movsx   r9d, byte ptr [rsi+18h]
0x180048826  cmp     r9d, 0Ah
0x18004882a  jg      loc_180048D1D
0x180048830  jz      loc_180048CBD
0x180048836  mov     ecx, r9d
0x180048839  test    r9d, r9d
0x18004883c  jz      loc_180048FED
0x180048842  sub     ecx, r12d
0x180048845  jz      loc_180048C02
0x18004884b  sub     ecx, r12d
0x18004884e  jz      loc_180048BB7
0x180048854  sub     ecx, r15d
0x180048857  jz      loc_180048B64
0x18004885d  sub     ecx, r12d
0x180048860  jz      loc_180048B29
0x180048866  sub     ecx, r15d
0x180048869  jz      loc_180048A4B
0x18004886f  sub     ecx, r12d
0x180048872  jz      loc_18004892D
0x180048878  cmp     ecx, r12d
0x18004887b  jnz     loc_180048D5B
0x180048881  test    byte ptr cs:xmmword_180063D60+1, 10h
0x180048888  jz      short loc_1800488B6
0x18004888a  mov     eax, [rsi+20h]
0x18004888d  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x180048894  mov     [rsp+98h+var_68], eax
0x180048898  mov     edx, 0ADh
0x18004889d  mov     eax, [rsi+1Ch]
0x1800488a0  mov     r9d, 9
0x1800488a6  mov     dword ptr [rsp+98h+var_70], eax
0x1800488aa  mov     eax, [rsi+8]
0x1800488ad  mov     [rsp+98h+CompletionInformation], eax
0x1800488b1  call    WPP_SF_dddd
0x1800488b6  mov     rcx, r14; lpCriticalSection
0x1800488b9  cmp     [rsi+1Ch], r15d
0x1800488bd  jnz     short loc_1800488D6
0x1800488bf  call    cs:__imp_EnterCriticalSection
0x1800488c6  nop     dword ptr [rax+rax+00h]
0x1800488cb  mov     eax, [rsi+20h]
0x1800488ce  mov     [rdi+1E0h], eax
0x1800488d4  jmp     short loc_1800488EB
0x1800488d6  call    cs:__imp_EnterCriticalSection
0x1800488dd  nop     dword ptr [rax+rax+00h]
0x1800488e2  mov     eax, [rsi+20h]
0x1800488e5  mov     [rdi+1D4h], eax
0x1800488eb  mov     rcx, r14; lpCriticalSection
0x1800488ee  call    cs:__imp_LeaveCriticalSection
0x1800488f5  nop     dword ptr [rax+rax+00h]
0x1800488fa  mov     edx, [rsi+1Ch]
0x1800488fd  cmp     edx, r15d
0x180048900  jnz     short loc_18004891C
0x180048902  cmp     [rsi+20h], r15d
0x180048906  jnz     short loc_18004891C
0x180048908  xchg    r12d, [rdi+104h]
0x18004890f  mov     rcx, rdi; CompletionContext
0x180048912  call    CheckPendingAppRecvs
0x180048917  jmp     loc_180048FED
0x18004891c  mov     r8d, [rsi+20h]
0x180048920  mov     rcx, rdi
0x180048923  call    HandleModeChange
0x180048928  jmp     loc_180048FED
0x18004892d  mov     rcx, r14; lpCriticalSection
0x180048930  call    cs:__imp_EnterCriticalSection
0x180048937  nop     dword ptr [rax+rax+00h]
0x18004893c  mov     esi, 3
0x180048941  cmp     [rdi+1E4h], esi
0x180048947  jz      short loc_180048962
0x180048949  xor     r9d, r9d; int
0x18004894c  mov     qword ptr [rsp+98h+CompletionInformation], 0; Src
0x180048955  xor     r8d, r8d; int
0x180048958  mov     edx, esi; int
0x18004895a  mov     rcx, rdi; int
0x18004895d  call    PushLargeRecvFCInfo
0x180048962  mov     dl, 8
0x180048964  test    [rdi+321h], dl
0x18004896a  jz      loc_180048A2D
0x180048970  mov     rbx, [r13+0]
0x180048974  cmp     rbx, r13
0x180048977  jz      loc_180048A2D
0x18004897d  btr     dword ptr [rbx+4Ch], 0Bh
0x180048982  mov     eax, [rbx+4Ch]
0x180048985  test    al, 80h
0x180048987  jnz     short loc_1800489B1
0x180048989  cmp     byte ptr cs:xmmword_180063D60, 0
0x180048990  jge     loc_180048A2D
0x180048996  mov     edx, 0AAh
0x18004899b  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x1800489a2  mov     ecx, 407h
0x1800489a7  mov     r9, rdi
0x1800489aa  call    WPP_SF_q
0x1800489af  jmp     short loc_180048A2D
0x1800489b1  mov     r8, [rdi+10h]
0x1800489b5  lea     r9, [rsp+98h+var_54]
0x1800489ba  mov     rdx, [rbx+68h]
0x1800489be  mov     rcx, [rdi+68h]
0x1800489c2  mov     rax, [r8+148h]
0x1800489c9  mov     r8d, [r8+14h]
0x1800489cd  mov     rdx, [rdx+60h]
0x1800489d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800489d6  mov     rcx, [rdi+8]
0x1800489da  or      eax, 0FFFFFFFFh
0x1800489dd  lock xadd [rcx], eax
0x1800489e1  cmp     eax, r12d
0x1800489e4  jnz     short loc_1800489EF
0x1800489e6  mov     rcx, [rdi+8]
0x1800489ea  call    SockDestroySocket
0x1800489ef  mov     rax, [rbx+68h]
0x1800489f3  lea     rdx, [rdi+300h]
0x1800489fa  mov     dword ptr [rax], 44444444h
0x180048a00  mov     r8, [rdx+8]
0x180048a04  cmp     [r8], rdx
0x180048a07  jz      short loc_180048A0E
0x180048a09  mov     rcx, rsi
0x180048a0c  int     29h; Win8: RtlFailFast(ecx)
0x180048a0e  add     rax, 28h ; '('
0x180048a12  mov     [rax+8], r8
0x180048a16  mov     [rax], rdx
0x180048a19  mov     [r8], rax
0x180048a1c  mov     [rdx+8], rax
0x180048a20  btr     dword ptr [rbx+4Ch], 7
0x180048a25  mov     qword ptr [rbx+68h], 0
0x180048a2d  mov     rcx, r14; lpCriticalSection
0x180048a30  call    cs:__imp_LeaveCriticalSection
0x180048a37  nop     dword ptr [rax+rax+00h]
0x180048a3c  mov     edx, esi
0x180048a3e  mov     rcx, rdi
0x180048a41  call    CheckRsMode
0x180048a46  jmp     loc_180048FED
0x180048a4b  test    byte ptr cs:xmmword_180063D60+1, 10h
0x180048a52  jz      short loc_180048A76
0x180048a54  mov     eax, [rbx]
0x180048a56  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x180048a5d  mov     edx, 0ABh
0x180048a62  mov     [rsp+98h+CompletionInformation], eax
0x180048a66  mov     ecx, 40Ch
0x180048a6b  mov     r9d, 7
0x180048a71  call    WPP_SF_dd
0x180048a76  mov     rcx, r14; lpCriticalSection
0x180048a79  call    cs:__imp_EnterCriticalSection
0x180048a80  nop     dword ptr [rax+rax+00h]
0x180048a85  mov     dl, 8
0x180048a87  test    [rdi+321h], dl
0x180048a8d  jz      short loc_180048AD0
0x180048a8f  cmp     [rdi+1D4h], r12d
0x180048a96  ja      short loc_180048AD0
0x180048a98  mov     rcx, r14; lpCriticalSection
0x180048a9b  call    cs:__imp_LeaveCriticalSection
0x180048aa2  nop     dword ptr [rax+rax+00h]
0x180048aa7  test    byte ptr cs:xmmword_180063D60, r15b
0x180048aae  jz      short loc_180048AC6
0x180048ab0  mov     edx, 0ACh
0x180048ab5  lea     r8, WPP_2679dd42b9fd305c9ea36fa3bdae9428_Traceguids
0x180048abc  mov     ecx, 401h
0x180048ac1  call    WPP_SF_
0x180048ac6  mov     rcx, rdi
0x180048ac9  call    CheckReadvertiseFirstSend
0x180048ace  jmp     short loc_180048B18
0x180048ad0  mov     r9d, [rsi+20h]; int
0x180048ad4  lea     rax, [rsi+28h]
0x180048ad8  mov     r8d, [rsi+1Ch]; int
0x180048adc  mov     edx, r12d; int
0x180048adf  mov     rcx, rdi; int
0x180048ae2  mov     qword ptr [rsp+98h+CompletionInformation], rax; Src
0x180048ae7  call    PushLargeRecvFCInfo
  ... truncated ...
```
