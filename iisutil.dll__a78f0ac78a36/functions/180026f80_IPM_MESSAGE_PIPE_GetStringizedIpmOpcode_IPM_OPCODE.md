# IPM_MESSAGE_PIPE::GetStringizedIpmOpcode(IPM_OPCODE)

- ea: `0x180026f80`
- end: `0x1800271f5`
- name: `?GetStringizedIpmOpcode@IPM_MESSAGE_PIPE@@SAPEBGW4IPM_OPCODE@@@Z`
- size: `629`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180026f80`

## string_xrefs

- `0x1800270a6`: `IPM_OP_ANONYMOUS_TOKEN_HANDLE`
- `0x180027101`: `IPM_OP_PROT_CREATE_POOL`
- `0x1800270f9`: `IPM_OP_PROT_DELETE_POOL`
- `0x180027121`: `IPM_OP_PROT_CREATE_APP`
- `0x180027159`: `IPM_OP_PROT_DELETE_APP`
- `0x180027199`: `IPM_OP_PROT_UPDATE_POOL_ID`
- `0x180027191`: `IPM_OP_PROT_SET_PROTOCOL_ACTIVE_STATE`
- `0x1800271b1`: `IPM_OP_PROT_UPDATE_APP_APP_POOL`
- `0x1800271e5`: `IPM_OP_PROT_UPDATE_REQUESTS_BLOCKED`
- `0x1800271dd`: `IPM_OP_PROT_POOL_ID_UPDATE_ACK`

## pseudocode

```c
const wchar_t *__fastcall IPM_MESSAGE_PIPE::GetStringizedIpmOpcode(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx

  if ( a1 <= 26 )
  {
    if ( a1 == 26 )
      return L"IPM_OP_PROT_REGISTER";
    if ( a1 > 11 )
    {
      if ( a1 > 17 )
      {
        v13 = a1 - 18;
        if ( !v13 )
          return L"IPM_OP_REPORT_CUSTOM_ACTION_RESULT";
        v14 = v13 - 1;
        if ( !v14 )
          return L"IPM_OP_CENTRAL_LOGGING_ENABLED";
        v15 = v14 - 1;
        if ( !v15 )
          return L"IPM_OP_ANONYMOUS_TOKEN_HANDLE";
        if ( v15 == 1 )
          return L"IPM_OP_IDLE_TIME";
      }
      else
      {
        if ( a1 == 17 )
          return L"IPM_OP_REQUEST_CUSTOM_ACTION";
        v9 = a1 - 12;
        if ( !v9 )
          return L"IPM_OP_START_QUEUE";
        v10 = v9 - 1;
        if ( !v10 )
          return L"IPM_OP_STOP_QUEUE";
        v11 = v10 - 1;
        if ( !v11 )
          return L"IPM_OP_REPORT_QUEUE_STARTED";
        v12 = v11 - 1;
        if ( !v12 )
          return L"IPM_OP_REPORT_QUEUE_STOPPED";
        if ( v12 == 1 )
          return L"IPM_OP_NOTIFY_OF_PENDING_SHUTDOWN";
      }
    }
    else
    {
      if ( a1 == 11 )
        return L"IPM_OP_HRESULT";
      if ( a1 > 6 )
      {
        v6 = a1 - 7;
        if ( !v6 )
          return L"IPM_OP_PERIODIC_PROCESS_RESTART_PERIOD_IN_MINUTES";
        v7 = v6 - 1;
        if ( !v7 )
          return L"IPM_OP_PERIODIC_PROCESS_RESTART_MEMORY_USAGE_IN_BYTES";
        v8 = v7 - 1;
        if ( !v8 )
          return L"IPM_OP_PERIODIC_PROCESS_RESTART_SCHEDULE";
        if ( v8 == 1 )
          return L"IPM_OP_GETPID";
      }
      else
      {
        if ( a1 == 6 )
          return L"IPM_OP_SEND_COUNTERS";
        v1 = a1 - 1;
        if ( !v1 )
          return L"IPM_OP_PING";
        v2 = v1 - 1;
        if ( !v2 )
          return L"IPM_OP_PING_REPLY";
        v3 = v2 - 1;
        if ( !v3 )
          return L"IPM_OP_WORKER_REQUESTS_SHUTDOWN";
        v4 = v3 - 1;
        if ( !v4 )
          return L"IPM_OP_SHUTDOWN";
        if ( v4 == 1 )
          return L"IPM_OP_REQUEST_COUNTERS";
      }
    }
    return L"INVALID_OPCODE";
  }
  if ( a1 <= 37 )
  {
    if ( a1 == 37 )
      return L"IPM_OP_PROT_SERVER_CONNECTED";
    if ( a1 > 32 )
    {
      v20 = a1 - 33;
      if ( !v20 )
        return L"IPM_OP_PROT_DELETE_APP";
      v21 = v20 - 1;
      if ( !v21 )
        return L"IPM_OP_PROT_ENABLE_POOL";
      v22 = v21 - 1;
      if ( !v22 )
        return L"IPM_OP_PROT_DISABLE_POOL";
      if ( v22 == 1 )
        return L"IPM_OP_PROT_CALL_ON_NEXT_REQUEST";
    }
    else
    {
      if ( a1 == 32 )
        return L"IPM_OP_PROT_CREATE_APP";
      v16 = a1 - 27;
      if ( !v16 )
        return L"IPM_OP_PROT_DEREGISTER";
      v17 = v16 - 1;
      if ( !v17 )
        return L"IPM_OP_PROT_START_QUEUE";
      v18 = v17 - 1;
      if ( !v18 )
        return L"IPM_OP_PROT_STOP_QUEUE";
      v19 = v18 - 1;
      if ( !v19 )
        return L"IPM_OP_PROT_CREATE_POOL";
      if ( v19 == 1 )
        return L"IPM_OP_PROT_DELETE_POOL";
    }
    return L"INVALID_OPCODE";
  }
  if ( a1 <= 43 )
  {
    if ( a1 == 43 )
      return L"IPM_OP_PROT_UPDATE_APP_APP_POOL";
    v23 = a1 - 38;
    if ( !v23 )
      return L"IPM_OP_PROT_REQUEST_OK_TO_TERMINATE";
    v24 = v23 - 1;
    if ( !v24 )
      return L"IPM_OP_PROT_OK_TO_TERMINATE";
    v25 = v24 - 1;
    if ( !v25 )
      return L"IPM_OP_PROT_UPDATE_POOL_ID";
    v26 = v25 - 1;
    if ( !v26 )
      return L"IPM_OP_PROT_SET_PROTOCOL_ACTIVE_STATE";
    if ( v26 == 1 )
      return L"IPM_OP_PROT_ALL_QUEUE_INSTANCES_STOPPED";
    return L"INVALID_OPCODE";
  }
  v27 = a1 - 44;
  if ( !v27 )
    return L"IPM_OP_PROT_NEW_APP_BINDINGS";
  v28 = v27 - 1;
  if ( !v28 )
    return L"IPM_OP_PROT_UPDATE_REQUESTS_BLOCKED";
  v29 = v28 - 1;
  if ( !v29 )
    return L"IPM_OP_PROT_POOL_ID_UPDATE_ACK";
  if ( v29 != 1 )
    return L"INVALID_OPCODE";
  return L"IPM_OP_PROT_MAX_BLOB_SIZE";
}

```

## disassembly

```asm
0x180026f80  cmp     ecx, 1Ah
0x180026f83  jg      loc_1800270C6
0x180026f89  jz      loc_1800270BE
0x180026f8f  cmp     ecx, 0Bh
0x180026f92  jg      loc_180027032
0x180026f98  jz      loc_18002702A
0x180026f9e  cmp     ecx, 6
0x180026fa1  jg      short loc_180026FF2
0x180026fa3  jz      short loc_180026FEA
0x180026fa5  sub     ecx, 1
0x180026fa8  jz      short loc_180026FE2
0x180026faa  sub     ecx, 1
0x180026fad  jz      short loc_180026FDA
0x180026faf  sub     ecx, 1
0x180026fb2  jz      short loc_180026FD2
0x180026fb4  sub     ecx, 1
0x180026fb7  jz      short loc_180026FCA
0x180026fb9  cmp     ecx, 1
0x180026fbc  jnz     loc_1800271CD
0x180026fc2  lea     rax, aIpmOpRequestCo; "IPM_OP_REQUEST_COUNTERS"
0x180026fc9  retn
0x180026fca  lea     rax, aIpmOpShutdown; "IPM_OP_SHUTDOWN"
0x180026fd1  retn
0x180026fd2  lea     rax, aIpmOpWorkerReq; "IPM_OP_WORKER_REQUESTS_SHUTDOWN"
0x180026fd9  retn
0x180026fda  lea     rax, aIpmOpPingReply; "IPM_OP_PING_REPLY"
0x180026fe1  retn
0x180026fe2  lea     rax, aIpmOpPing; "IPM_OP_PING"
0x180026fe9  retn
0x180026fea  lea     rax, aIpmOpSendCount; "IPM_OP_SEND_COUNTERS"
0x180026ff1  retn
0x180026ff2  sub     ecx, 7
0x180026ff5  jz      short loc_180027022
0x180026ff7  sub     ecx, 1
0x180026ffa  jz      short loc_18002701A
0x180026ffc  sub     ecx, 1
0x180026fff  jz      short loc_180027012
0x180027001  cmp     ecx, 1
0x180027004  jnz     loc_1800271CD
0x18002700a  lea     rax, aIpmOpGetpid; "IPM_OP_GETPID"
0x180027011  retn
0x180027012  lea     rax, aIpmOpPeriodicP_0; "IPM_OP_PERIODIC_PROCESS_RESTART_SCHEDUL"...
0x180027019  retn
0x18002701a  lea     rax, aIpmOpPeriodicP_1; "IPM_OP_PERIODIC_PROCESS_RESTART_MEMORY_"...
0x180027021  retn
0x180027022  lea     rax, aIpmOpPeriodicP; "IPM_OP_PERIODIC_PROCESS_RESTART_PERIOD_"...
0x180027029  retn
0x18002702a  lea     rax, aIpmOpHresult; "IPM_OP_HRESULT"
0x180027031  retn
0x180027032  cmp     ecx, 11h
0x180027035  jg      short loc_180027086
0x180027037  jz      short loc_18002707E
0x180027039  sub     ecx, 0Ch
0x18002703c  jz      short loc_180027076
0x18002703e  sub     ecx, 1
0x180027041  jz      short loc_18002706E
0x180027043  sub     ecx, 1
0x180027046  jz      short loc_180027066
0x180027048  sub     ecx, 1
0x18002704b  jz      short loc_18002705E
0x18002704d  cmp     ecx, 1
0x180027050  jnz     loc_1800271CD
0x180027056  lea     rax, aIpmOpNotifyOfP; "IPM_OP_NOTIFY_OF_PENDING_SHUTDOWN"
0x18002705d  retn
0x18002705e  lea     rax, aIpmOpReportQue; "IPM_OP_REPORT_QUEUE_STOPPED"
0x180027065  retn
0x180027066  lea     rax, aIpmOpReportQue_0; "IPM_OP_REPORT_QUEUE_STARTED"
0x18002706d  retn
0x18002706e  lea     rax, aIpmOpStopQueue; "IPM_OP_STOP_QUEUE"
0x180027075  retn
0x180027076  lea     rax, aIpmOpStartQueu; "IPM_OP_START_QUEUE"
0x18002707d  retn
0x18002707e  lea     rax, aIpmOpRequestCu; "IPM_OP_REQUEST_CUSTOM_ACTION"
0x180027085  retn
0x180027086  sub     ecx, 12h
0x180027089  jz      short loc_1800270B6
0x18002708b  sub     ecx, 1
0x18002708e  jz      short loc_1800270AE
0x180027090  sub     ecx, 1
0x180027093  jz      short loc_1800270A6
0x180027095  cmp     ecx, 1
0x180027098  jnz     loc_1800271CD
0x18002709e  lea     rax, aIpmOpIdleTime; "IPM_OP_IDLE_TIME"
0x1800270a5  retn
0x1800270a6  lea     rax, aIpmOpAnonymous; "IPM_OP_ANONYMOUS_TOKEN_HANDLE"
0x1800270ad  retn
0x1800270ae  lea     rax, aIpmOpCentralLo; "IPM_OP_CENTRAL_LOGGING_ENABLED"
0x1800270b5  retn
0x1800270b6  lea     rax, aIpmOpReportCus; "IPM_OP_REPORT_CUSTOM_ACTION_RESULT"
0x1800270bd  retn
0x1800270be  lea     rax, aIpmOpProtRegis; "IPM_OP_PROT_REGISTER"
0x1800270c5  retn
0x1800270c6  cmp     ecx, 25h ; '%'
0x1800270c9  jg      loc_180027169
0x1800270cf  jz      loc_180027161
0x1800270d5  cmp     ecx, 20h ; ' '
0x1800270d8  jg      short loc_180027129
0x1800270da  jz      short loc_180027121
0x1800270dc  sub     ecx, 1Bh
0x1800270df  jz      short loc_180027119
0x1800270e1  sub     ecx, 1
0x1800270e4  jz      short loc_180027111
0x1800270e6  sub     ecx, 1
0x1800270e9  jz      short loc_180027109
0x1800270eb  sub     ecx, 1
0x1800270ee  jz      short loc_180027101
0x1800270f0  cmp     ecx, 1
0x1800270f3  jnz     loc_1800271CD
0x1800270f9  lea     rax, aIpmOpProtDelet_0; "IPM_OP_PROT_DELETE_POOL"
0x180027100  retn
0x180027101  lea     rax, aIpmOpProtCreat; "IPM_OP_PROT_CREATE_POOL"
0x180027108  retn
0x180027109  lea     rax, aIpmOpProtStopQ; "IPM_OP_PROT_STOP_QUEUE"
0x180027110  retn
0x180027111  lea     rax, aIpmOpProtStart; "IPM_OP_PROT_START_QUEUE"
0x180027118  retn
0x180027119  lea     rax, aIpmOpProtDereg; "IPM_OP_PROT_DEREGISTER"
0x180027120  retn
0x180027121  lea     rax, aIpmOpProtCreat_0; "IPM_OP_PROT_CREATE_APP"
0x180027128  retn
0x180027129  sub     ecx, 21h ; '!'
0x18002712c  jz      short loc_180027159
0x18002712e  sub     ecx, 1
0x180027131  jz      short loc_180027151
0x180027133  sub     ecx, 1
0x180027136  jz      short loc_180027149
0x180027138  cmp     ecx, 1
0x18002713b  jnz     loc_1800271CD
0x180027141  lea     rax, aIpmOpProtCallO; "IPM_OP_PROT_CALL_ON_NEXT_REQUEST"
0x180027148  retn
0x180027149  lea     rax, aIpmOpProtDisab; "IPM_OP_PROT_DISABLE_POOL"
0x180027150  retn
0x180027151  lea     rax, aIpmOpProtEnabl; "IPM_OP_PROT_ENABLE_POOL"
0x180027158  retn
0x180027159  lea     rax, aIpmOpProtDelet; "IPM_OP_PROT_DELETE_APP"
0x180027160  retn
0x180027161  lea     rax, aIpmOpProtServe; "IPM_OP_PROT_SERVER_CONNECTED"
0x180027168  retn
0x180027169  cmp     ecx, 2Bh ; '+'
0x18002716c  jg      short loc_1800271B9
0x18002716e  jz      short loc_1800271B1
0x180027170  sub     ecx, 26h ; '&'
0x180027173  jz      short loc_1800271A9
0x180027175  sub     ecx, 1
0x180027178  jz      short loc_1800271A1
0x18002717a  sub     ecx, 1
0x18002717d  jz      short loc_180027199
0x18002717f  sub     ecx, 1
0x180027182  jz      short loc_180027191
0x180027184  cmp     ecx, 1
0x180027187  jnz     short loc_1800271CD
0x180027189  lea     rax, aIpmOpProtAllQu; "IPM_OP_PROT_ALL_QUEUE_INSTANCES_STOPPED"
0x180027190  retn
0x180027191  lea     rax, aIpmOpProtSetPr; "IPM_OP_PROT_SET_PROTOCOL_ACTIVE_STATE"
0x180027198  retn
0x180027199  lea     rax, aIpmOpProtUpdat; "IPM_OP_PROT_UPDATE_POOL_ID"
0x1800271a0  retn
0x1800271a1  lea     rax, aIpmOpProtOkToT; "IPM_OP_PROT_OK_TO_TERMINATE"
0x1800271a8  retn
0x1800271a9  lea     rax, aIpmOpProtReque; "IPM_OP_PROT_REQUEST_OK_TO_TERMINATE"
0x1800271b0  retn
0x1800271b1  lea     rax, aIpmOpProtUpdat_1; "IPM_OP_PROT_UPDATE_APP_APP_POOL"
0x1800271b8  retn
0x1800271b9  sub     ecx, 2Ch ; ','
0x1800271bc  jz      short loc_1800271ED
0x1800271be  sub     ecx, 1
0x1800271c1  jz      short loc_1800271E5
0x1800271c3  sub     ecx, 1
0x1800271c6  jz      short loc_1800271DD
0x1800271c8  cmp     ecx, 1
0x1800271cb  jz      short loc_1800271D5
0x1800271cd  lea     rax, aInvalidOpcode; "INVALID_OPCODE"
0x1800271d4  retn
0x1800271d5  lea     rax, aIpmOpProtMaxBl; "IPM_OP_PROT_MAX_BLOB_SIZE"
0x1800271dc  retn
0x1800271dd  lea     rax, aIpmOpProtPoolI; "IPM_OP_PROT_POOL_ID_UPDATE_ACK"
0x1800271e4  retn
0x1800271e5  lea     rax, aIpmOpProtUpdat_0; "IPM_OP_PROT_UPDATE_REQUESTS_BLOCKED"
0x1800271ec  retn
0x1800271ed  lea     rax, aIpmOpProtNewAp; "IPM_OP_PROT_NEW_APP_BINDINGS"
0x1800271f4  retn
```
