# SendProtocolResultToRasman

- ea: `0x1800482c0`
- end: `0x180049176`
- name: `SendProtocolResultToRasman`
- size: `3766`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002b200`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x180006f70`
- `0x18000c3c0`
- `0x18000c424`
- `0x18001975c`
- `0x180033654`
- `0x1800336a8`
- `0x18003a718`
- `0x18003d6b8`
- `0x18003e864`
- `0x18004037c`
- `0x180040ddc`
- `0x18004236c`
- `0x1800442f8`
- `0x1800444ec`
- `0x180045e80`
- `0x1800482c0`
- `0x180049a9c`
- `0x180049c18`
- `0x18004a634`
- `0x18004a7cc`
- `0x18004b8fc`
- `0x18004c2d8`
- `0x180068bec`
- `0x18009e8ac`
- `0x1800e8e7e`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180048d59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180048d59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048cf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048cf2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004876a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004876a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800487c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800487c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800487e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800487e5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180048800`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180048cde`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180048800`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180048cde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048e63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048e72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048e90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049078`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048e63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048e72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048e90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049078`

## string_xrefs

- `0x18004858f`: `RasUpdateVpnLuidStatus: Setting %I64X to %s`
- `0x180048679`: `RasUpdateVpnLuidStatus: Setting %I64X to %s`

## pseudocode

```c
__int64 __fastcall SendProtocolResultToRasman(_QWORD *Src)
{
  __int64 PortByHandle; // r14
  struct _LIST_ENTRY *v3; // rcx
  unsigned int v4; // ebp
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // r9
  unsigned int v8; // eax
  int v9; // eax
  unsigned int v10; // eax
  _QWORD *i; // rbx
  _BYTE *v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rdi
  int v15; // edx
  _DWORD *v16; // rax
  _DWORD *v17; // r15
  DWORD LastError; // eax
  struct _LIST_ENTRY *v19; // rsi
  __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // rbx
  __int64 v25; // r9
  void *v26; // r8
  const CHAR *v27; // rdx
  const CHAR *v28; // rcx
  unsigned int v29; // eax
  __int64 v30; // r13
  _BYTE *v31; // rdi
  DWORD v32; // eax
  DWORD CurrentProcessId; // eax
  unsigned int PasswordA; // eax
  HLOCAL *v35; // rbx
  __int64 v36; // rcx
  _BYTE *v37; // rax
  _BYTE *v38; // rax
  unsigned int v39; // eax
  struct _LIST_ENTRY *v40; // rcx
  _DWORD *v41; // rcx
  __int64 v42; // r9
  __int64 v43; // rcx
  _QWORD *v44; // rax
  HLOCAL hMem; // [rsp+60h] [rbp-58h] BYREF
  int v47; // [rsp+68h] [rbp-50h]
  __int128 v48; // [rsp+6Ch] [rbp-4Ch]

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 269, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
  }
  PortByHandle = GetPortByHandle(Src[2]);
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
  {
    WPP_SF_dq(
      WPP_GLOBAL_Control[1].Flink,
      270,
      WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids,
      *((unsigned int *)Src + 3),
      Src[2]);
    v3 = WPP_GLOBAL_Control;
  }
  if ( PortByHandle )
  {
    v4 = 0;
    if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v3[1].Blink) & 0x2000) != 0
      && BYTE1(v3[1].Blink) >= 5u )
    {
      WPP_SF_Ds(
        v3[1].Flink,
        272,
        (unsigned int)WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids,
        *(_DWORD *)(PortByHandle + 28),
        PortByHandle + 8);
      v3 = WPP_GLOBAL_Control;
    }
    if ( *(_DWORD *)(PortByHandle + 28) != 2 )
    {
      if ( *(_DWORD *)(PortByHandle + 28) == 1 )
      {
        v7 = *((unsigned int *)Src + 3);
        if ( (_DWORD)v7 != 1 )
        {
          if ( v3 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            return v4;
          if ( (HIDWORD(v3[1].Blink) & 0x2000) == 0 || BYTE1(v3[1].Blink) < 5u )
            goto LABEL_249;
          WPP_SF_dq(v3[1].Flink, 275, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v7, *(_QWORD *)PortByHandle);
          goto LABEL_248;
        }
      }
      if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v3[1].Blink) & 0x2000) != 0
        && BYTE1(v3[1].Blink) >= 5u )
      {
        WPP_SF_(v3[1].Flink, 273, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
      }
      *(_DWORD *)(PortByHandle + 1316) = 0;
      v8 = DwProcessProtocolFailureMessage(PortByHandle);
      v4 = v8;
      if ( !v8 )
      {
LABEL_248:
        v3 = WPP_GLOBAL_Control;
        goto LABEL_249;
      }
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v4;
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        goto LABEL_249;
      v5 = 274;
      goto LABEL_36;
    }
    if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v3[1].Blink) & 0x2000) != 0
      && BYTE1(v3[1].Blink) >= 5u )
    {
      WPP_SF_d(v3[1].Flink, 276, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, *((unsigned int *)Src + 3));
      v3 = WPP_GLOBAL_Control;
    }
    v9 = *((_DWORD *)Src + 3);
    switch ( v9 )
    {
      case 14:
        if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v3[1].Blink) & 0x2000) != 0
          && BYTE1(v3[1].Blink) >= 5u )
        {
          WPP_SF_(v3[1].Flink, 277, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
        }
        v10 = SignalNotifierAndNetman(PortByHandle, 512, 16);
        v4 = v10;
        if ( v10 )
        {
          v3 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
LABEL_52:
            for ( i = g_RasVpnLuids; i; i = (_QWORD *)i[2] )
            {
              if ( *i == (*(_DWORD *)(*(_QWORD *)(PortByHandle + 1064) + 160LL) & 0xFFFFFF | 0x17000000LL) << 24 )
              {
                TraceMsg("RasUpdateVpnLuidStatus: Setting %I64X to %s");
                *((_BYTE *)i + 8) = 1;
                goto LABEL_248;
              }
            }
            goto LABEL_249;
          }
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 278, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v10);
        }
        v3 = WPP_GLOBAL_Control;
        goto LABEL_52;
      case 16:
        if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v3[1].Blink) & 0x2000) != 0
          && BYTE1(v3[1].Blink) >= 5u )
        {
          WPP_SF_(v3[1].Flink, 279, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
        }
        v8 = SignalNotifierAndNetman(PortByHandle, 1024, 0);
        v4 = v8;
        if ( !v8 )
          goto LABEL_248;
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          return v4;
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          goto LABEL_249;
        v5 = 280;
        goto LABEL_36;
      case 15:
        if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v3[1].Blink) & 0x2000) != 0
          && BYTE1(v3[1].Blink) >= 5u )
        {
          WPP_SF_(v3[1].Flink, 281, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
        }
        v12 = g_RasVpnLuids;
        v13 = (*(_DWORD *)(*(_QWORD *)(PortByHandle + 1064) + 160LL) & 0xFFFFFF | 0x17000000LL) << 24;
        while ( v12 )
        {
          if ( *(_QWORD *)v12 == v13 )
          {
            TraceMsg("RasUpdateVpnLuidStatus: Setting %I64X to %s");
            v12[8] = 0;
            break;
          }
          v12 = (_BYTE *)*((_QWORD *)v12 + 2);
        }
        LogUpdateConnectionSuccessEvent(PortByHandle, v13);
        v8 = SignalNotifierAndNetman(PortByHandle, 2048, 32);
        v4 = v8;
        if ( !v8 )
          goto LABEL_248;
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          return v4;
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          goto LABEL_249;
        v5 = 282;
LABEL_36:
        v6 = v8;
        goto LABEL_15;
      case 17:
        if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v3[1].Blink) & 0x2000) != 0
          && BYTE1(v3[1].Blink) >= 5u )
        {
          WPP_SF_(v3[1].Flink, 283, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
          v3 = WPP_GLOBAL_Control;
        }
        v14 = *(_QWORD *)(PortByHandle + 1304);
        if ( v14 )
        {
          v15 = *((_DWORD *)Src + 16);
          *(_DWORD *)v14 = v15;
          if ( v15 )
          {
            LogUpdateConnectionFailureEvent(PortByHandle);
            SignalNotifierAndNetman(PortByHandle, 512, 0);
          }
          SetEvent(*(HANDLE *)(v14 + 8));
          goto LABEL_248;
        }
        v4 = 6;
        if ( v3 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          return v4;
        if ( (HIDWORD(v3[1].Blink) & 0x2000) == 0 || BYTE1(v3[1].Blink) < 2u )
          goto LABEL_249;
        v5 = 284;
        goto LABEL_14;
      case 18:
        if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v3[1].Blink) & 0x2000) != 0
          && BYTE1(v3[1].Blink) >= 5u )
        {
          WPP_SF_(v3[1].Flink, 285, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
        }
        SignalNotifiers(*(_QWORD *)(*(_QWORD *)(PortByHandle + 1064) + 48LL), 64, 0);
        EnterCriticalSection(&g_csConnectionNotifierList);
        SignalNotifiers(pConnectionNotifierList, 64, 0);
        LeaveCriticalSection(&g_csConnectionNotifierList);
        goto LABEL_248;
    }
    v16 = LocalAlloc(0x40u, 0x6D8u);
    v17 = v16;
    if ( !v16 )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( !LastError )
        goto LABEL_248;
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return v4;
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        goto LABEL_249;
      v5 = 286;
      v6 = LastError;
      goto LABEL_15;
    }
    memcpy_0(v16, Src, 0x6D8u);
    if ( v17[3] == 11 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 5u )
      {
LABEL_115:
        if ( v17[3] == 1 && v17[16] )
        {
          if ( v19 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v19[1].Blink) & 0x2000) != 0
            && BYTE1(v19[1].Blink) >= 5u )
          {
            WPP_SF_sd(
              v19[1].Flink,
              288,
              (unsigned int)WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids,
              PortByHandle + 8,
              v17[16]);
          }
          *(_DWORD *)(PortByHandle + 264) = v17[16];
          v19 = WPP_GLOBAL_Control;
        }
        if ( v17[3] == 12 )
        {
          if ( v19 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v19[1].Blink) & 0x2000) != 0
            && BYTE1(v19[1].Blink) >= 5u )
          {
            WPP_SF_(v19[1].Flink, 289, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
            v19 = WPP_GLOBAL_Control;
          }
          v20 = (unsigned int)v17[18];
          if ( (_DWORD)v20 )
          {
            v21 = *((_QWORD *)v17 + 8);
            if ( v21 )
            {
              SetUserData(PortByHandle + 1080, 6, v21, v20);
              v19 = WPP_GLOBAL_Control;
            }
          }
        }
        if ( v17[3] == 13 )
        {
          if ( v19 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v19[1].Blink) & 0x2000) != 0
            && BYTE1(v19[1].Blink) >= 5u )
          {
            WPP_SF_(v19[1].Flink, 290, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
          }
          SetUserData(PortByHandle + 1080, 15, v17 + 16, 8);
          v19 = WPP_GLOBAL_Control;
        }
        v22 = -1;
        if ( v17[3] != 4 )
        {
LABEL_173:
          if ( v17[3] != 7 )
            goto LABEL_205;
          if ( v19 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v19[1].Blink) & 0x2000) != 0
            && BYTE1(v19[1].Blink) >= 5u )
          {
            WPP_SF_(v19[1].Flink, 296, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
          }
          v30 = 257;
          v31 = LocalAlloc(0x40u, 0x101u);
          if ( !v31 )
          {
            v32 = GetLastError();
            v4 = v32;
            if ( v32 )
            {
              v3 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                return v4;
              if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 297, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v32);
                v3 = WPP_GLOBAL_Control;
              }
              goto LABEL_249;
            }
            goto LABEL_248;
          }
          CurrentProcessId = GetCurrentProcessId();
          PasswordA = DwGetPasswordA(PortByHandle, v31, CurrentProcessId);
          if ( PasswordA )
          {
            v19 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
LABEL_190:
              if ( !v4 )
              {
                hMem = 0;
                do
                  ++v22;
                while ( v31[v22] );
                v4 = EncodeData(v31, (unsigned int)(v22 + 1), &hMem);
                if ( v4 )
                {
                  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                  {
                    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 299, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v4);
                  }
                }
                else
                {
                  v35 = (HLOCAL *)hMem;
                  if ( hMem )
                  {
                    SetUserData(PortByHandle + 1080, 10, *((_QWORD *)hMem + 1), *(unsigned int *)hMem);
                    v36 = *(unsigned int *)v35;
                    v37 = v35[1];
                    if ( *(_DWORD *)v35 )
                    {
                      do
                      {
                        *v37++ = 0;
                        --v36;
                      }
                      while ( v36 );
                    }
                    LocalFree(v35[1]);
                    LocalFree(v35);
                  }
                }
                v38 = v31;
                do
                {
                  *v38++ = 0;
                  --v30;
                }
                while ( v30 );
                LocalFree(v31);
                v19 = WPP_GLOBAL_Control;
              }
LABEL_205:
              if ( v17[3] != 10 )
              {
                if ( !v17[3] )
                {
                  if ( v19 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (HIDWORD(v19[1].Blink) & 0x2000) != 0
                    && BYTE1(v19[1].Blink) >= 5u )
                  {
                    WPP_SF_(v19[1].Flink, 305, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
                  }
                  v43 = *(_QWORD *)(PortByHandle + 1064);
                  *(_DWORD *)(PortByHandle + 1320) = 1;
                  if ( v43 && (*(_BYTE *)(v43 + 112) & 0x10) != 0 )
                    CheckAndInitiateProtocolRenegotiation(v43, 0);
                }
                v44 = *(_QWORD **)(PortByHandle + 1120);
                if ( v44 )
                  *v44 = v17;
                else
                  *(_QWORD *)(PortByHandle + 1112) = v17;
                *(_QWORD *)(PortByHandle + 1120) = v17;
                *(_QWORD *)v17 = 0;
                SetProtocolResultAvailableEvent(PortByHandle);
                goto LABEL_248;
              }
              if ( *(_DWORD *)(PortByHandle + 1360) != 3 )
                goto LABEL_220;
              *(_DWORD *)g_RasEvent = 128;
              v39 = DwSendNotificationInternal(*(_QWORD *)(PortByHandle + 1064), g_RasEvent);
              if ( v39 )
              {
                v40 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
                {
LABEL_217:
                  *(_DWORD *)(*(_QWORD *)(PortByHandle + 1064) + 120LL) = *(_DWORD *)(PortByHandle + 1072);
                  v41 = *(_DWORD **)(PortByHandle + 1064);
                  if ( !v41[41] )
                  {
                    FreeConnection(v41);
                    *(_QWORD *)(PortByHandle + 1064) = 0;
                  }
                  v19 = WPP_GLOBAL_Control;
LABEL_220:
                  if ( v19 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (HIDWORD(v19[1].Blink) & 0x2000) != 0
                    && BYTE1(v19[1].Blink) >= 5u )
                  {
                    WPP_SF_d(v19[1].Flink, 302, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, (unsigned int)v17[2]);
                    v19 = WPP_GLOBAL_Control;
                  }
                  v42 = (unsigned int)v17[2];
                  if ( (_DWORD)v42 )
                  {
                    if ( v19 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                      && (HIDWORD(v19[1].Blink) & 0x2000) != 0
                      && BYTE1(v19[1].Blink) >= 5u )
                    {
                      WPP_SF_d(v19[1].Flink, 303, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v42);
                    }
                    *(_DWORD *)(PortByHandle + 264) = v17[2];
                  }
                  *(_DWORD *)(PortByHandle + 1316) = v17[16] & 1;
                  v4 = DwProcessProtocolFailureMessage(PortByHandle);
                  if ( v4
                    && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
                  {
                    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 304, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v4);
                  }
                  LocalFree(v17);
                  goto LABEL_248;
                }
                if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
                {
LABEL_213:
                  if ( v40 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                    && (HIDWORD(v40[1].Blink) & 0x2000) != 0
                    && BYTE1(v40[1].Blink) >= 5u )
                  {
                    WPP_SF_qqd(
                      v40[1].Flink,
                      301,
                      WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids,
                      *(_QWORD *)(*(_QWORD *)(PortByHandle + 1064) + 16LL),
                      *(_QWORD *)(PortByHandle + 1064),
                      *(_DWORD *)(PortByHandle + 1072));
                  }
                  goto LABEL_217;
                }
                WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 300, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v39);
              }
              v40 = WPP_GLOBAL_Control;
              goto LABEL_213;
            }
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 298, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, PasswordA);
          }
          v19 = WPP_GLOBAL_Control;
          goto LABEL_190;
        }
        if ( v19 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v19[1].Blink) & 0x2000) != 0
          && BYTE1(v19[1].Blink) >= 5u )
        {
          WPP_SF_(v19[1].Flink, 291, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
          v19 = WPP_GLOBAL_Control;
        }
        v23 = *(_QWORD *)(PortByHandle + 1064);
        if ( v23 )
        {
          v24 = *((_QWORD *)v17 + 35);
          if ( v24 )
          {
            if ( !GetUserData(v23 + 32, 4) )
            {
              v25 = -1;
              do
                ++v25;
              while ( *(_BYTE *)(v24 + v25) );
              SetUserData(*(_QWORD *)(PortByHandle + 1064) + 32LL, 4, v24, (unsigned int)(v25 + 1));
            }
            v19 = WPP_GLOBAL_Control;
          }
        }
        if ( !v17[31] && (*(_BYTE *)(PortByHandle + 40) & 4) == 0 )
        {
          v26 = *(void **)(PortByHandle + 1240);
          v27 = *(const CHAR **)(PortByHandle + 1208);
          v28 = *(const CHAR **)(PortByHandle + 1200);
          *(_QWORD *)((char *)&v48 + 1) = 0;
          *(_QWORD *)&v48 = *((_QWORD *)v17 + 16);
          *((_QWORD *)&v48 + 1) = *((_QWORD *)v17 + 18);
          v47 = 3;
          v29 = WriteSharedPbkOptions(v28, v27, v26);
          v4 = v29;
          if ( v29 )
          {
            v19 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
              || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
              goto LABEL_164;
            }
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 292, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v29);
          }
          else
          {
            v19 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
              goto LABEL_164;
            if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
            {
              WPP_SF_DDDDDDDD(
                WPP_GLOBAL_Control[1].Flink,
                293,
                *((unsigned __int8 *)v17 + 133),
                *((unsigned __int8 *)v17 + 128),
                *((unsigned __int8 *)v17 + 129),
                *((unsigned __int8 *)v17 + 130),
                *((unsigned __int8 *)v17 + 131),
                *((unsigned __int8 *)v17 + 132),
                *((unsigned __int8 *)v17 + 133),
                *((unsigned __int8 *)v17 + 134),
                *((unsigned __int8 *)v17 + 135));
              v19 = WPP_GLOBAL_Control;
            }
            if ( v19 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              || (HIDWORD(v19[1].Blink) & 0x2000) == 0
              || BYTE1(v19[1].Blink) < 5u )
            {
              goto LABEL_164;
            }
            WPP_SF_DDDDDDDD(
              v19[1].Flink,
              294,
              *((unsigned __int8 *)v17 + 149),
              *((unsigned __int8 *)v17 + 144),
              *((unsigned __int8 *)v17 + 145),
              *((unsigned __int8 *)v17 + 146),
              *((unsigned __int8 *)v17 + 147),
              *((unsigned __int8 *)v17 + 148),
              *((unsigned __int8 *)v17 + 149),
              *((unsigned __int8 *)v17 + 150),
              *((unsigned __int8 *)v17 + 151));
          }
          v19 = WPP_GLOBAL_Control;
        }
LABEL_164:
        if ( v17[16] == 1 )
        {
          v4 = PopulateTsRoutes(*(_QWORD *)(PortByHandle + 1064), v17 + 62);
          if ( v4 )
          {
            v19 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 295, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v4);
              v19 = WPP_GLOBAL_Control;
            }
            v4 = 0;
          }
          else
          {
            v19 = WPP_GLOBAL_Control;
          }
        }
        v22 = -1;
        goto LABEL_173;
      }
      WPP_SF_s(WPP_GLOBAL_Control[1].Flink, 287, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, PortByHandle + 8);
    }
    v19 = WPP_GLOBAL_Control;
    goto LABEL_115;
  }
  v4 = 6;
  if ( v3 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v4;
  if ( (HIDWORD(v3[1].Blink) & 0x2000) != 0 && BYTE1(v3[1].Blink) >= 2u )
  {
    v5 = 271;
LABEL_14:
    v6 = 6;
LABEL_15:
    WPP_SF_d(v3[1].Flink, v5, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v6);
    goto LABEL_248;
  }
LABEL_249:
  if ( v3 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v3[1].Blink) & 0x2000) != 0
    && BYTE1(v3[1].Blink) >= 6u )
  {
    WPP_SF_d(v3[1].Flink, 306, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x1800482c0  mov     [rsp+arg_8], rbx
0x1800482c5  mov     [rsp+arg_10], rbp
0x1800482ca  push    rsi
0x1800482cb  push    rdi
0x1800482cc  push    r13
0x1800482ce  push    r14
0x1800482d0  push    r15
0x1800482d2  sub     rsp, 90h
0x1800482d9  mov     rax, cs:__security_cookie
0x1800482e0  xor     rax, rsp
0x1800482e3  mov     [rsp+0B8h+var_38], rax
0x1800482eb  mov     rbx, rcx
0x1800482ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800482f5  lea     rsi, WPP_GLOBAL_Control
0x1800482fc  lea     r15, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x180048303  mov     edi, 2000h
0x180048308  cmp     rcx, rsi
0x18004830b  jz      short loc_180048329
0x18004830d  test    [rcx+1Ch], edi
0x180048310  jz      short loc_180048329
0x180048312  cmp     byte ptr [rcx+19h], 6
0x180048316  jb      short loc_180048329
0x180048318  mov     rcx, [rcx+10h]
0x18004831c  mov     edx, 10Dh
0x180048321  mov     r8, r15
0x180048324  call    WPP_SF_
0x180048329  mov     rcx, [rbx+10h]
0x18004832d  call    GetPortByHandle
0x180048332  mov     r14, rax
0x180048335  mov     rcx, cs:WPP_GLOBAL_Control
0x18004833c  cmp     rcx, rsi
0x18004833f  jz      short loc_180048371
0x180048341  test    [rcx+1Ch], edi
0x180048344  jz      short loc_180048371
0x180048346  cmp     byte ptr [rcx+19h], 5
0x18004834a  jb      short loc_180048371
0x18004834c  mov     rax, [rbx+10h]
0x180048350  mov     edx, 10Eh
0x180048355  mov     r9d, [rbx+0Ch]
0x180048359  mov     r8, r15
0x18004835c  mov     rcx, [rcx+10h]
0x180048360  mov     [rsp+0B8h+var_98], rax
0x180048365  call    WPP_SF_dq
0x18004836a  mov     rcx, cs:WPP_GLOBAL_Control
0x180048371  xor     r13d, r13d
0x180048374  test    r14, r14
0x180048377  jnz     short loc_1800483B2
0x180048379  lea     ebp, [r13+6]
0x18004837d  cmp     rcx, rsi
0x180048380  jz      loc_180049147
0x180048386  test    [rcx+1Ch], edi
0x180048389  jz      loc_180049114
0x18004838f  cmp     byte ptr [rcx+19h], 2
0x180048393  jb      loc_180049114
0x180048399  mov     edx, 10Fh
0x18004839e  mov     r9d, ebp
0x1800483a1  mov     r8, r15
0x1800483a4  mov     rcx, [rcx+10h]
0x1800483a8  call    WPP_SF_d
0x1800483ad  jmp     loc_18004910D
0x1800483b2  mov     ebp, r13d
0x1800483b5  cmp     rcx, rsi
0x1800483b8  jz      short loc_1800483EA
0x1800483ba  test    [rcx+1Ch], edi
0x1800483bd  jz      short loc_1800483EA
0x1800483bf  cmp     byte ptr [rcx+19h], 5
0x1800483c3  jb      short loc_1800483EA
0x1800483c5  mov     r9d, [r14+1Ch]
0x1800483c9  lea     rax, [r14+8]
0x1800483cd  mov     rcx, [rcx+10h]
0x1800483d1  mov     edx, 110h
0x1800483d6  mov     r8, r15
0x1800483d9  mov     [rsp+0B8h+var_98], rax
0x1800483de  call    WPP_SF_Ds
0x1800483e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800483ea  cmp     dword ptr [r14+1Ch], 2
0x1800483ef  jz      loc_1800484AA
0x1800483f5  cmp     dword ptr [r14+1Ch], 1
0x1800483fa  jnz     short loc_180048440
0x1800483fc  mov     r9d, [rbx+0Ch]
0x180048400  cmp     r9d, 1
0x180048404  jz      short loc_180048440
0x180048406  cmp     rcx, rsi
0x180048409  jz      loc_180049147
0x18004840f  test    [rcx+1Ch], edi
0x180048412  jz      loc_180049114
0x180048418  cmp     byte ptr [rcx+19h], 5
0x18004841c  jb      loc_180049114
0x180048422  mov     rax, [r14]
0x180048425  mov     edx, 113h
0x18004842a  mov     rcx, [rcx+10h]
0x18004842e  mov     r8, r15
0x180048431  mov     [rsp+0B8h+var_98], rax
0x180048436  call    WPP_SF_dq
0x18004843b  jmp     loc_18004910D
0x180048440  cmp     rcx, rsi
0x180048443  jz      short loc_180048461
0x180048445  test    [rcx+1Ch], edi
0x180048448  jz      short loc_180048461
0x18004844a  cmp     byte ptr [rcx+19h], 5
0x18004844e  jb      short loc_180048461
0x180048450  mov     rcx, [rcx+10h]
0x180048454  mov     edx, 111h
0x180048459  mov     r8, r15
0x18004845c  call    WPP_SF_
0x180048461  mov     rcx, r14
0x180048464  mov     [r14+524h], r13d
0x18004846b  call    DwProcessProtocolFailureMessage
0x180048470  mov     ebp, eax
0x180048472  test    eax, eax
0x180048474  jz      loc_18004910D
0x18004847a  mov     rcx, cs:WPP_GLOBAL_Control
0x180048481  cmp     rcx, rsi
0x180048484  jz      loc_180049147
0x18004848a  test    [rcx+1Ch], edi
0x18004848d  jz      loc_180049114
0x180048493  cmp     byte ptr [rcx+19h], 2
0x180048497  jb      loc_180049114
0x18004849d  mov     edx, 112h
0x1800484a2  mov     r9d, eax
0x1800484a5  jmp     loc_1800483A1
0x1800484aa  cmp     rcx, rsi
0x1800484ad  jz      short loc_1800484D6
0x1800484af  test    [rcx+1Ch], edi
0x1800484b2  jz      short loc_1800484D6
0x1800484b4  cmp     byte ptr [rcx+19h], 5
0x1800484b8  jb      short loc_1800484D6
0x1800484ba  mov     r9d, [rbx+0Ch]
0x1800484be  mov     edx, 114h
0x1800484c3  mov     rcx, [rcx+10h]
0x1800484c7  mov     r8, r15
0x1800484ca  call    WPP_SF_d
0x1800484cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800484d6  mov     eax, [rbx+0Ch]
0x1800484d9  cmp     eax, 0Eh
0x1800484dc  jnz     loc_1800485A4
0x1800484e2  cmp     rcx, rsi
0x1800484e5  jz      short loc_180048503
0x1800484e7  test    [rcx+1Ch], edi
0x1800484ea  jz      short loc_180048503
0x1800484ec  cmp     byte ptr [rcx+19h], 5
0x1800484f0  jb      short loc_180048503
0x1800484f2  mov     rcx, [rcx+10h]
0x1800484f6  mov     edx, 115h
0x1800484fb  mov     r8, r15
0x1800484fe  call    WPP_SF_
0x180048503  mov     edx, 200h
0x180048508  mov     r8d, 10h
0x18004850e  mov     rcx, r14
0x180048511  call    SignalNotifierAndNetman
0x180048516  mov     ebp, eax
0x180048518  test    eax, eax
0x18004851a  jz      short loc_180048547
0x18004851c  mov     rcx, cs:WPP_GLOBAL_Control
0x180048523  cmp     rcx, rsi
0x180048526  jz      short loc_18004854E
0x180048528  test    [rcx+1Ch], edi
0x18004852b  jz      short loc_18004854E
0x18004852d  cmp     byte ptr [rcx+19h], 2
0x180048531  jb      short loc_18004854E
0x180048533  mov     rcx, [rcx+10h]
0x180048537  mov     edx, 116h
0x18004853c  mov     r9d, eax
0x18004853f  mov     r8, r15
0x180048542  call    WPP_SF_d
0x180048547  mov     rcx, cs:WPP_GLOBAL_Control
0x18004854e  mov     rdx, [r14+428h]
0x180048555  mov     rbx, cs:g_RasVpnLuids
0x18004855c  mov     edx, [rdx+0A0h]
0x180048562  and     edx, 0FFFFFFh
0x180048568  or      rdx, 17000000h
0x18004856f  shl     rdx, 18h
0x180048573  jmp     short loc_18004857E
0x180048575  cmp     [rbx], rdx
0x180048578  jz      short loc_180048588
0x18004857a  mov     rbx, [rbx+10h]
0x18004857e  test    rbx, rbx
0x180048581  jnz     short loc_180048575
0x180048583  jmp     loc_180049114
0x180048588  lea     r8, aDormant; "Dormant"
0x18004858f  lea     rcx, szFormat; "RasUpdateVpnLuidStatus: Setting %I64X t"...
0x180048596  call    TraceMsg
0x18004859b  mov     byte ptr [rbx+8], 1
0x18004859f  jmp     loc_18004910D
0x1800485a4  cmp     eax, 10h
0x1800485a7  jnz     short loc_180048611
0x1800485a9  cmp     rcx, rsi
0x1800485ac  jz      short loc_1800485CA
0x1800485ae  test    [rcx+1Ch], edi
0x1800485b1  jz      short loc_1800485CA
0x1800485b3  cmp     byte ptr [rcx+19h], 5
0x1800485b7  jb      short loc_1800485CA
0x1800485b9  mov     rcx, [rcx+10h]
0x1800485bd  mov     edx, 117h
0x1800485c2  mov     r8, r15
0x1800485c5  call    WPP_SF_
0x1800485ca  xor     r8d, r8d
0x1800485cd  mov     edx, 400h
0x1800485d2  mov     rcx, r14
0x1800485d5  call    SignalNotifierAndNetman
0x1800485da  mov     ebp, eax
0x1800485dc  test    eax, eax
0x1800485de  jz      loc_18004910D
0x1800485e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800485eb  cmp     rcx, rsi
0x1800485ee  jz      loc_180049147
0x1800485f4  test    [rcx+1Ch], edi
0x1800485f7  jz      loc_180049114
0x1800485fd  cmp     byte ptr [rcx+19h], 2
0x180048601  jb      loc_180049114
0x180048607  mov     edx, 118h
0x18004860c  jmp     loc_1800484A2
0x180048611  cmp     eax, 0Fh
0x180048614  jnz     loc_1800486DB
0x18004861a  cmp     rcx, rsi
0x18004861d  jz      short loc_18004863B
0x18004861f  test    [rcx+1Ch], edi
0x180048622  jz      short loc_18004863B
0x180048624  cmp     byte ptr [rcx+19h], 5
0x180048628  jb      short loc_18004863B
0x18004862a  mov     rcx, [rcx+10h]
0x18004862e  mov     edx, 119h
0x180048633  mov     r8, r15
0x180048636  call    WPP_SF_
0x18004863b  mov     rdx, [r14+428h]
0x180048642  mov     rbx, cs:g_RasVpnLuids
0x180048649  mov     edx, [rdx+0A0h]
0x18004864f  and     edx, 0FFFFFFh
0x180048655  or      rdx, 17000000h
0x18004865c  shl     rdx, 18h
0x180048660  jmp     short loc_18004866B
0x180048662  cmp     [rbx], rdx
0x180048665  jz      short loc_180048672
0x180048667  mov     rbx, [rbx+10h]
0x18004866b  test    rbx, rbx
0x18004866e  jnz     short loc_180048662
0x180048670  jmp     short loc_180048689
0x180048672  lea     r8, aActive; "Active"
0x180048679  lea     rcx, szFormat; "RasUpdateVpnLuidStatus: Setting %I64X t"...
0x180048680  call    TraceMsg
0x180048685  mov     [rbx+8], r13b
0x180048689  mov     rcx, r14
0x18004868c  call    LogUpdateConnectionSuccessEvent
0x180048691  mov     edx, 800h
0x180048696  mov     r8d, 20h ; ' '
0x18004869c  mov     rcx, r14
0x18004869f  call    SignalNotifierAndNetman
0x1800486a4  mov     ebp, eax
0x1800486a6  test    eax, eax
0x1800486a8  jz      loc_18004910D
0x1800486ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800486b5  cmp     rcx, rsi
0x1800486b8  jz      loc_180049147
0x1800486be  test    [rcx+1Ch], edi
0x1800486c1  jz      loc_180049114
0x1800486c7  cmp     byte ptr [rcx+19h], 2
0x1800486cb  jb      loc_180049114
0x1800486d1  mov     edx, 11Ah
0x1800486d6  jmp     loc_1800484A2
0x1800486db  cmp     eax, 11h
0x1800486de  jnz     loc_18004877B
0x1800486e4  cmp     rcx, rsi
0x1800486e7  jz      short loc_18004870C
0x1800486e9  test    [rcx+1Ch], edi
0x1800486ec  jz      short loc_18004870C
0x1800486ee  cmp     byte ptr [rcx+19h], 5
0x1800486f2  jb      short loc_18004870C
0x1800486f4  mov     rcx, [rcx+10h]
0x1800486f8  mov     edx, 11Bh
0x1800486fd  mov     r8, r15
0x180048700  call    WPP_SF_
0x180048705  mov     rcx, cs:WPP_GLOBAL_Control
0x18004870c  mov     rdi, [r14+518h]
0x180048713  test    rdi, rdi
0x180048716  jnz     short loc_180048745
0x180048718  lea     ebp, [rdi+6]
0x18004871b  cmp     rcx, rsi
0x18004871e  jz      loc_180049147
0x180048724  test    dword ptr [rcx+1Ch], 2000h
0x18004872b  jz      loc_180049114
0x180048731  cmp     byte ptr [rcx+19h], 2
0x180048735  jb      loc_180049114
0x18004873b  mov     edx, 11Ch
0x180048740  jmp     loc_18004839E
0x180048745  mov     edx, [rbx+40h]
0x180048748  mov     [rdi], edx
0x18004874a  test    edx, edx
0x18004874c  jz      short loc_180048766
0x18004874e  mov     rcx, r14
0x180048751  call    LogUpdateConnectionFailureEvent
0x180048756  xor     r8d, r8d
0x180048759  mov     edx, 200h
0x18004875e  mov     rcx, r14
0x180048761  call    SignalNotifierAndNetman
0x180048766  mov     rcx, [rdi+8]; hEvent
0x18004876a  call    cs:__imp_SetEvent
0x180048771  nop     dword ptr [rax+rax+00h]
0x180048776  jmp     loc_18004910D
0x18004877b  cmp     eax, 12h
0x18004877e  jnz     short loc_1800487F6
  ... truncated ...
```
