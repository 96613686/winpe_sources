# PortDisconnectRequestInternal

- ea: `0x180021e2c`
- end: `0x1800225b9`
- name: `PortDisconnectRequestInternal`
- size: `1933`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021d90`
- `0x18004f350`

## callees

- `0x180005ad8`
- `0x180005bcc`
- `0x180005bfc`
- `0x180005cf8`
- `0x18000c3c0`
- `0x18000c424`
- `0x180014734`
- `0x180021e2c`
- `0x180034190`
- `0x18003bba4`
- `0x18003e864`
- `0x180046b70`
- `0x18004aa34`
- `0x180080824`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180021e83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180021e83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022049`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022114`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002255a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022049`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022114`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002255a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180022105`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002254b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180022105`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002254b`

## string_xrefs

- `0x180022035`: `PortDisconnectRequestInternal: Access was denied`
- `0x1800220f1`: `PortDisconnectRequestInternal: Access was denied`
- `0x180022435`: `PortDisconnectRequestInternal: SendMessageToProtocolEngine: Failed`
- `0x180022532`: `PortDisconnectRequestInternal: port is already disconnecting`

## pseudocode

```c
int __fastcall PortDisconnectRequestInternal(__int64 a1, _DWORD *a2, __int64 a3, int a4)
{
  __int64 (*v8)(void); // rax
  int v9; // ebp
  DWORD v10; // esi
  struct _LIST_ENTRY *v11; // rcx
  __int64 v12; // rdx
  void *v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // rax
  unsigned int v16; // eax
  struct _LIST_ENTRY *v17; // rcx
  _QWORD *v18; // rcx
  unsigned int v19; // edi
  struct _LIST_ENTRY *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r9
  int v24; // [rsp+80h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 260, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
  }
  LODWORD(v8) = GetCurrentProcessId();
  v9 = (int)v8;
  if ( a2 && *a2 )
    v10 = a2[2];
  else
    v10 = *(_DWORD *)(a3 + 8);
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      LODWORD(v8) = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 261, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
    }
    *(_DWORD *)a3 = 615;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        LODWORD(v8) = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 262, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
        v11 = WPP_GLOBAL_Control;
      }
      if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v11[1].Blink) & 0x2000) != 0
        && BYTE1(v11[1].Blink) >= 6u )
      {
        v12 = 263;
LABEL_135:
        LODWORD(v8) = WPP_SF_(v11[1].Flink, v12, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
        return (int)v8;
      }
    }
    return (int)v8;
  }
  if ( a4 )
  {
    v13 = *(void **)a3;
    goto LABEL_43;
  }
  v13 = 0;
  if ( (unsigned __int64)(*(_QWORD *)a3 - 1LL) > 0xFFFFFFFFFFFFFFFDuLL
    || (v13 = (void *)ValidateHandleForRasman(*(HANDLE *)a3, v10),
        (((unsigned __int64)v13 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0) )
  {
    if ( *(_DWORD *)(a1 + 272) == v9 )
    {
      if ( v10 == v9 )
        goto LABEL_58;
      if ( (*(_BYTE *)(a1 + 40) & 8) == 0 )
      {
        v14 = *(_QWORD *)(a1 + 1064);
        if ( v14 )
        {
          if ( (unsigned int)IsRouterPhonebook((LPCWSTR)(v14 + 184)) )
          {
            *(_DWORD *)a3 = 5;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_sd(
                WPP_GLOBAL_Control[1].Flink,
                265,
                (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                a1 + 8,
                5);
            }
            TelemetryEventWriteStateChange(a1, 5, "PortDisconnectRequestInternal: Access was denied");
            LODWORD(v8) = CloseHandle(v13);
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
            {
              v12 = 266;
              goto LABEL_135;
            }
            return (int)v8;
          }
        }
      }
LABEL_44:
      if ( *(_QWORD *)(a1 + 1064) )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 267, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
        }
        if ( !(unsigned int)CheckIfAllowedToManageConnection(
                              *(PSID *)(*(_QWORD *)(a1 + 1064) + 96LL),
                              *(_DWORD *)(a1 + 40) & 8,
                              0) )
        {
          *(_DWORD *)a3 = 5;
          TelemetryEventWriteStateChange(a1, 5, "PortDisconnectRequestInternal: Access was denied");
          if ( a4 )
            SetEvent(v13);
          LODWORD(v8) = CloseHandle(v13);
          if ( v13 == *(void **)(a1 + 1280) )
            *(_QWORD *)(a1 + 1280) = -1;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
          {
            v12 = 268;
            goto LABEL_135;
          }
          return (int)v8;
        }
      }
LABEL_58:
      if ( *(_DWORD *)(a1 + 28) != 3 )
      {
        if ( a4 )
          goto LABEL_80;
        if ( ((*(_QWORD *)(a1 + 1280) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        {
          v15 = *(_QWORD *)(a1 + 1064);
          if ( v15 && *(_DWORD *)(v15 + 68) == 1 )
          {
            v24 = 0;
            *(_DWORD *)g_RasEvent = 64;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
            {
              WPP_SF_(WPP_GLOBAL_Control[1].Flink, 271, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
            }
            v16 = DwSendNotificationInternal(*(_QWORD *)(a1 + 1064), g_RasEvent);
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 272, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v16);
            }
            LODWORD(v8) = QueueCloseConnections(*(_QWORD *)(a1 + 1064), v13, &v24);
            if ( v24 )
            {
              *(_QWORD *)(a1 + 1280) = v13;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
              {
                LODWORD(v8) = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 273, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
              }
              *(_DWORD *)a3 = 600;
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
              {
                v12 = 274;
                goto LABEL_135;
              }
              return (int)v8;
            }
          }
LABEL_80:
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
          {
            WPP_SF_sqD(
              WPP_GLOBAL_Control[1].Flink,
              275,
              (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
              a1 + 8,
              *(_QWORD *)(a1 + 1064),
              *(_DWORD *)(a1 + 1224));
            v17 = WPP_GLOBAL_Control;
          }
          if ( !*(_QWORD *)(a1 + 1064) || (*(_DWORD *)(a1 + 1224) & 0x14) != 4 )
          {
            if ( v17 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(v17[1].Blink) & 0x2000) != 0
              && BYTE1(v17[1].Blink) >= 4u )
            {
              WPP_SF_s(v17[1].Flink, 280, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, a1 + 8);
            }
            *(_DWORD *)(a1 + 1324) = 0;
            LODWORD(v8) = DisconnectPort((_QWORD *)a1, v13, 0);
            v19 = (unsigned int)v8;
            goto LABEL_115;
          }
          if ( v17 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(v17[1].Blink) & 0x2000) != 0
            && BYTE1(v17[1].Blink) >= 4u )
          {
            WPP_SF_q(v17[1].Flink, 276, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v13);
          }
          v18 = g_ProtocolEngMsg;
          *(_QWORD *)(a1 + 1280) = v13;
          *(_DWORD *)v18 = 1;
          v18[1] = *(_QWORD *)a1;
          v18[2] = 0;
          *((_DWORD *)v18 + 6) = 0;
          v8 = (__int64 (*)(void))qword_18010B098[8 * (__int64)*(int *)(a1 + 1360)];
          if ( v8 )
          {
            LODWORD(v8) = v8();
            v19 = (unsigned int)v8;
            if ( !(_DWORD)v8 )
            {
LABEL_101:
              v20 = WPP_GLOBAL_Control;
              goto LABEL_102;
            }
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
              goto LABEL_107;
            if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
            {
LABEL_102:
              if ( v20 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(v20[1].Blink) & 0x2000) != 0
                && BYTE1(v20[1].Blink) >= 2u )
              {
                LODWORD(v8) = WPP_SF_sd(
                                v20[1].Flink,
                                279,
                                (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                                (int)a1 + 8,
                                v19);
              }
              if ( !v19 )
              {
                v19 = 600;
                goto LABEL_115;
              }
LABEL_107:
              if ( v19 != 600 )
                goto LABEL_108;
LABEL_115:
              *(_DWORD *)a3 = v19;
              v11 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
              {
                if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
                {
                  LODWORD(v8) = WPP_SF_s(
                                  WPP_GLOBAL_Control[1].Flink,
                                  281,
                                  WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                                  a1 + 8);
                  v11 = WPP_GLOBAL_Control;
                }
                if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && (HIDWORD(v11[1].Blink) & 0x2000) != 0
                  && BYTE1(v11[1].Blink) >= 6u )
                {
                  v12 = 282;
                  goto LABEL_135;
                }
              }
              return (int)v8;
            }
            v21 = 278;
            v22 = (unsigned int)v8;
          }
          else
          {
            v19 = 839;
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
            {
LABEL_108:
              LODWORD(v8) = TelemetryEventWriteStateChange(
                              a1,
                              v19,
                              "PortDisconnectRequestInternal: SendMessageToProtocolEngine: Failed");
              goto LABEL_115;
            }
            if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
              goto LABEL_102;
            v21 = 277;
            v22 = 839;
          }
          LODWORD(v8) = WPP_SF_d(v20[1].Flink, v21, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v22);
          goto LABEL_101;
        }
      }
      *(_DWORD *)a3 = 617;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
      {
        WPP_SF_s(WPP_GLOBAL_Control[1].Flink, 269, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, a1 + 8);
      }
      TelemetryEventWriteStateChange(a1, 617, "PortDisconnectRequestInternal: port is already disconnecting");
      if ( a4 )
        SetEvent(v13);
      LODWORD(v8) = CloseHandle(v13);
      if ( v13 == *(void **)(a1 + 1280) )
        *(_QWORD *)(a1 + 1280) = -1;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
      {
        v12 = 270;
        goto LABEL_135;
      }
      return (int)v8;
    }
LABEL_43:
    if ( v10 == v9 )
      goto LABEL_58;
    goto LABEL_44;
  }
  LODWORD(v8) = TelemetryEventWriteStateChange(a1, 2147942487LL, "PortDisconnectRequestInternal: Invalid Handle");
  *(_DWORD *)a3 = -2147024809;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    v12 = 264;
    goto LABEL_135;
  }
  return (int)v8;
}

```

## disassembly

```asm
0x180021e2c  push    rbx
0x180021e2e  push    rbp
0x180021e2f  push    rsi
0x180021e30  push    rdi
0x180021e31  push    r12
0x180021e33  push    r13
0x180021e35  push    r14
0x180021e37  push    r15
0x180021e39  sub     rsp, 38h
0x180021e3d  mov     r15d, r9d
0x180021e40  mov     r14, r8
0x180021e43  mov     rdi, rdx
0x180021e46  mov     rbx, rcx
0x180021e49  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e50  lea     r13, WPP_GLOBAL_Control
0x180021e57  mov     r12d, 2000h
0x180021e5d  cmp     rcx, r13
0x180021e60  jz      short loc_180021E83
0x180021e62  test    [rcx+1Ch], r12d
0x180021e66  jz      short loc_180021E83
0x180021e68  cmp     byte ptr [rcx+19h], 6
0x180021e6c  jb      short loc_180021E83
0x180021e6e  mov     rcx, [rcx+10h]
0x180021e72  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180021e79  mov     edx, 104h
0x180021e7e  call    WPP_SF_
0x180021e83  call    cs:__imp_GetCurrentProcessId
0x180021e8a  nop     dword ptr [rax+rax+00h]
0x180021e8f  mov     ebp, eax
0x180021e91  test    rdi, rdi
0x180021e94  jz      short loc_180021EA0
0x180021e96  cmp     dword ptr [rdi], 0
0x180021e99  jz      short loc_180021EA0
0x180021e9b  mov     esi, [rdi+8]
0x180021e9e  jmp     short loc_180021EA4
0x180021ea0  mov     esi, [r14+8]
0x180021ea4  test    rbx, rbx
0x180021ea7  jnz     loc_180021F40
0x180021ead  mov     rcx, cs:WPP_GLOBAL_Control
0x180021eb4  cmp     rcx, r13
0x180021eb7  jz      short loc_180021EDA
0x180021eb9  test    [rcx+1Ch], r12d
0x180021ebd  jz      short loc_180021EDA
0x180021ebf  cmp     byte ptr [rcx+19h], 2
0x180021ec3  jb      short loc_180021EDA
0x180021ec5  mov     rcx, [rcx+10h]
0x180021ec9  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180021ed0  mov     edx, 105h
0x180021ed5  call    WPP_SF_
0x180021eda  mov     dword ptr [r14], 267h
0x180021ee1  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ee8  cmp     rcx, r13
0x180021eeb  jz      loc_1800225A7
0x180021ef1  test    [rcx+1Ch], r12d
0x180021ef5  jz      short loc_180021F19
0x180021ef7  cmp     byte ptr [rcx+19h], 2
0x180021efb  jb      short loc_180021F19
0x180021efd  mov     rcx, [rcx+10h]
0x180021f01  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180021f08  mov     edx, 106h
0x180021f0d  call    WPP_SF_
0x180021f12  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f19  cmp     rcx, r13
0x180021f1c  jz      loc_1800225A7
0x180021f22  test    [rcx+1Ch], r12d
0x180021f26  jz      loc_1800225A7
0x180021f2c  cmp     byte ptr [rcx+19h], 6
0x180021f30  jb      loc_1800225A7
0x180021f36  mov     edx, 107h
0x180021f3b  jmp     loc_180022597
0x180021f40  test    r15d, r15d
0x180021f43  jnz     loc_180022083
0x180021f49  mov     rcx, [r14]; hSourceHandle
0x180021f4c  xor     edi, edi
0x180021f4e  lea     rax, [rcx-1]
0x180021f52  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180021f56  ja      short loc_180021FB6
0x180021f58  mov     edx, esi; dwProcessId
0x180021f5a  call    ValidateHandleForRasman
0x180021f5f  mov     rdi, rax
0x180021f62  lea     rcx, [rax+1]
0x180021f66  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180021f6d  jnz     short loc_180021FB6
0x180021f6f  mov     edi, 80070057h
0x180021f74  lea     r8, aPortdisconnect; "PortDisconnectRequestInternal: Invalid "...
0x180021f7b  mov     edx, edi
0x180021f7d  mov     rcx, rbx
0x180021f80  call    TelemetryEventWriteStateChange
0x180021f85  mov     [r14], edi
0x180021f88  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f8f  cmp     rcx, r13
0x180021f92  jz      loc_1800225A7
0x180021f98  test    [rcx+1Ch], r12d
0x180021f9c  jz      loc_1800225A7
0x180021fa2  cmp     byte ptr [rcx+19h], 6
0x180021fa6  jb      loc_1800225A7
0x180021fac  mov     edx, 108h
0x180021fb1  jmp     loc_180022597
0x180021fb6  cmp     [rbx+110h], ebp
0x180021fbc  jnz     loc_180022086
0x180021fc2  cmp     esi, ebp
0x180021fc4  jz      loc_180022162
0x180021fca  test    byte ptr [rbx+28h], 8
0x180021fce  jnz     loc_18002208E
0x180021fd4  mov     rcx, [rbx+428h]
0x180021fdb  test    rcx, rcx
0x180021fde  jz      loc_18002208E
0x180021fe4  add     rcx, 0B8h; lpString
0x180021feb  call    IsRouterPhonebook
0x180021ff0  test    eax, eax
0x180021ff2  jz      loc_18002208E
0x180021ff8  mov     esi, 5
0x180021ffd  mov     [r14], esi
0x180022000  mov     rcx, cs:WPP_GLOBAL_Control
0x180022007  cmp     rcx, r13
0x18002200a  jz      short loc_180022035
0x18002200c  test    [rcx+1Ch], r12d
0x180022010  jz      short loc_180022035
0x180022012  cmp     byte ptr [rcx+19h], 2
0x180022016  jb      short loc_180022035
0x180022018  mov     rcx, [rcx+10h]
0x18002201c  lea     r9, [rbx+8]
0x180022020  mov     edx, 109h
0x180022025  mov     dword ptr [rsp+78h+var_58], esi
0x180022029  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180022030  call    WPP_SF_sd
0x180022035  lea     r8, aPortdisconnect_1; "PortDisconnectRequestInternal: Access w"...
0x18002203c  mov     edx, esi
0x18002203e  mov     rcx, rbx
0x180022041  call    TelemetryEventWriteStateChange
0x180022046  mov     rcx, rdi; hObject
0x180022049  call    cs:__imp_CloseHandle
0x180022050  nop     dword ptr [rax+rax+00h]
0x180022055  mov     rcx, cs:WPP_GLOBAL_Control
0x18002205c  cmp     rcx, r13
0x18002205f  jz      loc_1800225A7
0x180022065  test    [rcx+1Ch], r12d
0x180022069  jz      loc_1800225A7
0x18002206f  cmp     byte ptr [rcx+19h], 6
0x180022073  jb      loc_1800225A7
0x180022079  mov     edx, 10Ah
0x18002207e  jmp     loc_180022597
0x180022083  mov     rdi, [r14]
0x180022086  cmp     esi, ebp
0x180022088  jz      loc_180022162
0x18002208e  cmp     qword ptr [rbx+428h], 0
0x180022096  jz      loc_180022162
0x18002209c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800220a3  cmp     rcx, r13
0x1800220a6  jz      short loc_1800220C9
0x1800220a8  test    [rcx+1Ch], r12d
0x1800220ac  jz      short loc_1800220C9
0x1800220ae  cmp     byte ptr [rcx+19h], 4
0x1800220b2  jb      short loc_1800220C9
0x1800220b4  mov     rcx, [rcx+10h]
0x1800220b8  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800220bf  mov     edx, 10Bh
0x1800220c4  call    WPP_SF_
0x1800220c9  mov     rcx, [rbx+428h]
0x1800220d0  xor     r8d, r8d
0x1800220d3  mov     edx, [rbx+28h]
0x1800220d6  and     edx, 8
0x1800220d9  mov     rcx, [rcx+60h]; pSid2
0x1800220dd  call    CheckIfAllowedToManageConnection
0x1800220e2  test    eax, eax
0x1800220e4  jnz     short loc_180022162
0x1800220e6  lea     esi, [rax+5]
0x1800220e9  mov     rcx, rbx
0x1800220ec  mov     edx, esi
0x1800220ee  mov     [r14], esi
0x1800220f1  lea     r8, aPortdisconnect_1; "PortDisconnectRequestInternal: Access w"...
0x1800220f8  call    TelemetryEventWriteStateChange
0x1800220fd  test    r15d, r15d
0x180022100  jz      short loc_180022111
0x180022102  mov     rcx, rdi; hEvent
0x180022105  call    cs:__imp_SetEvent
0x18002210c  nop     dword ptr [rax+rax+00h]
0x180022111  mov     rcx, rdi; hObject
0x180022114  call    cs:__imp_CloseHandle
0x18002211b  nop     dword ptr [rax+rax+00h]
0x180022120  cmp     rdi, [rbx+500h]
0x180022127  jnz     short loc_180022134
0x180022129  mov     qword ptr [rbx+500h], 0FFFFFFFFFFFFFFFFh
0x180022134  mov     rcx, cs:WPP_GLOBAL_Control
0x18002213b  cmp     rcx, r13
0x18002213e  jz      loc_1800225A7
0x180022144  test    [rcx+1Ch], r12d
0x180022148  jz      loc_1800225A7
0x18002214e  cmp     byte ptr [rcx+19h], 6
0x180022152  jb      loc_1800225A7
0x180022158  mov     edx, 10Ch
0x18002215d  jmp     loc_180022597
0x180022162  cmp     dword ptr [rbx+1Ch], 3
0x180022166  jz      loc_1800224F9
0x18002216c  test    r15d, r15d
0x18002216f  jnz     loc_1800222B5
0x180022175  mov     rax, [rbx+500h]
0x18002217c  inc     rax
0x18002217f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180022185  jnz     loc_1800224F9
0x18002218b  mov     rax, [rbx+428h]
0x180022192  test    rax, rax
0x180022195  jz      loc_1800222B5
0x18002219b  cmp     dword ptr [rax+44h], 1
0x18002219f  jnz     loc_1800222B5
0x1800221a5  mov     [rsp+78h+arg_0], r15d
0x1800221ad  mov     cs:g_RasEvent, 40h ; '@'
0x1800221b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800221be  cmp     rcx, r13
0x1800221c1  jz      short loc_1800221E8
0x1800221c3  test    [rcx+1Ch], r12d
0x1800221c7  jz      short loc_1800221E8
0x1800221c9  lea     esi, [r15+5]
0x1800221cd  cmp     [rcx+19h], sil
0x1800221d1  jb      short loc_1800221E8
0x1800221d3  mov     rcx, [rcx+10h]
0x1800221d7  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800221de  mov     edx, 10Fh
0x1800221e3  call    WPP_SF_
0x1800221e8  mov     rcx, [rbx+428h]
0x1800221ef  lea     rdx, g_RasEvent
0x1800221f6  call    DwSendNotificationInternal
0x1800221fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180022202  cmp     rcx, r13
0x180022205  jz      short loc_18002222B
0x180022207  test    [rcx+1Ch], r12d
0x18002220b  jz      short loc_18002222B
0x18002220d  cmp     byte ptr [rcx+19h], 4
0x180022211  jb      short loc_18002222B
0x180022213  mov     rcx, [rcx+10h]
0x180022217  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x18002221e  mov     edx, 110h
0x180022223  mov     r9d, eax
0x180022226  call    WPP_SF_d
0x18002222b  mov     rcx, [rbx+428h]
0x180022232  lea     r8, [rsp+78h+arg_0]
0x18002223a  mov     rdx, rdi
0x18002223d  call    QueueCloseConnections
0x180022242  cmp     [rsp+78h+arg_0], 0
0x18002224a  jz      short loc_1800222B5
0x18002224c  mov     [rbx+500h], rdi
0x180022253  mov     rcx, cs:WPP_GLOBAL_Control
0x18002225a  cmp     rcx, r13
0x18002225d  jz      short loc_180022280
0x18002225f  test    [rcx+1Ch], r12d
0x180022263  jz      short loc_180022280
0x180022265  cmp     byte ptr [rcx+19h], 4
0x180022269  jb      short loc_180022280
0x18002226b  mov     rcx, [rcx+10h]
0x18002226f  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180022276  mov     edx, 111h
0x18002227b  call    WPP_SF_
0x180022280  mov     dword ptr [r14], 258h
0x180022287  mov     rcx, cs:WPP_GLOBAL_Control
0x18002228e  cmp     rcx, r13
0x180022291  jz      loc_1800225A7
0x180022297  test    [rcx+1Ch], r12d
0x18002229b  jz      loc_1800225A7
0x1800222a1  cmp     byte ptr [rcx+19h], 6
0x1800222a5  jb      loc_1800225A7
0x1800222ab  mov     edx, 112h
0x1800222b0  jmp     loc_180022597
0x1800222b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800222bc  cmp     rcx, r13
0x1800222bf  jz      short loc_180022303
0x1800222c1  test    [rcx+1Ch], r12d
0x1800222c5  jz      short loc_180022303
0x1800222c7  cmp     byte ptr [rcx+19h], 4
0x1800222cb  jb      short loc_180022303
0x1800222cd  mov     eax, [rbx+4C8h]
0x1800222d3  lea     r9, [rbx+8]
0x1800222d7  mov     rcx, [rcx+10h]
0x1800222db  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800222e2  mov     [rsp+78h+var_50], eax
0x1800222e6  mov     edx, 113h
0x1800222eb  mov     rax, [rbx+428h]
0x1800222f2  mov     [rsp+78h+var_58], rax
0x1800222f7  call    WPP_SF_sqD
0x1800222fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180022303  cmp     qword ptr [rbx+428h], 0
0x18002230b  jz      loc_18002244F
0x180022311  mov     eax, [rbx+4C8h]
0x180022317  and     al, 14h
0x180022319  cmp     al, 4
0x18002231b  jnz     loc_18002244F
0x180022321  cmp     rcx, r13
0x180022324  jz      short loc_180022349
0x180022326  test    [rcx+1Ch], r12d
0x18002232a  jz      short loc_180022349
0x18002232c  cmp     [rcx+19h], al
0x18002232f  jb      short loc_180022349
0x180022331  mov     rcx, [rcx+10h]
0x180022335  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x18002233c  mov     edx, 114h
0x180022341  mov     r9, rdi
0x180022344  call    WPP_SF_q
0x180022349  mov     rcx, cs:g_ProtocolEngMsg
0x180022350  lea     rdx, qword_18010B098
0x180022357  mov     [rbx+500h], rdi
0x18002235e  mov     dword ptr [rcx], 1
  ... truncated ...
```
