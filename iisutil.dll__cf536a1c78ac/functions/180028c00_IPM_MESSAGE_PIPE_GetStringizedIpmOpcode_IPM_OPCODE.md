# IPM_MESSAGE_PIPE::GetStringizedIpmOpcode(IPM_OPCODE)

- ea: `0x180028c00`
- end: `0x180028ea0`
- name: `?GetStringizedIpmOpcode@IPM_MESSAGE_PIPE@@SAPEBGW4IPM_OPCODE@@@Z`
- size: `672`
- prototype: `const wchar_t *__fastcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180028c00`

## string_xrefs

- `0x180028d38`: `IPM_OP_ANONYMOUS_TOKEN_HANDLE`
- `0x180028d98`: `IPM_OP_PROT_CREATE_POOL`
- `0x180028d8f`: `IPM_OP_PROT_DELETE_POOL`
- `0x180028dbc`: `IPM_OP_PROT_CREATE_APP`
- `0x180028df8`: `IPM_OP_PROT_DELETE_APP`
- `0x180028e3c`: `IPM_OP_PROT_UPDATE_POOL_ID`
- `0x180028e33`: `IPM_OP_PROT_SET_PROTOCOL_ACTIVE_STATE`
- `0x180028e57`: `IPM_OP_PROT_UPDATE_APP_APP_POOL`
- `0x180028e8f`: `IPM_OP_PROT_UPDATE_REQUESTS_BLOCKED`
- `0x180028e86`: `IPM_OP_PROT_POOL_ID_UPDATE_ACK`

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
0x180028c00  cmp     ecx, 1Ah
0x180028c03  jg      loc_180028D5C
0x180028c09  jz      loc_180028D53
0x180028c0f  cmp     ecx, 0Bh
0x180028c12  jg      loc_180028CBD
0x180028c18  jz      loc_180028CB4
0x180028c1e  cmp     ecx, 6
0x180028c21  jg      short loc_180028C78
0x180028c23  jz      short loc_180028C6F
0x180028c25  sub     ecx, 1
0x180028c28  jz      short loc_180028C66
0x180028c2a  sub     ecx, 1
0x180028c2d  jz      short loc_180028C5D
0x180028c2f  sub     ecx, 1
0x180028c32  jz      short loc_180028C54
0x180028c34  sub     ecx, 1
0x180028c37  jz      short loc_180028C4B
0x180028c39  cmp     ecx, 1
0x180028c3c  jnz     loc_180028E74
0x180028c42  lea     rax, aIpmOpRequestCo; "IPM_OP_REQUEST_COUNTERS"
0x180028c49  retn
0x180028c4b  lea     rax, aIpmOpShutdown; "IPM_OP_SHUTDOWN"
0x180028c52  retn
0x180028c54  lea     rax, aIpmOpWorkerReq; "IPM_OP_WORKER_REQUESTS_SHUTDOWN"
0x180028c5b  retn
0x180028c5d  lea     rax, aIpmOpPingReply; "IPM_OP_PING_REPLY"
0x180028c64  retn
0x180028c66  lea     rax, aIpmOpPing; "IPM_OP_PING"
0x180028c6d  retn
0x180028c6f  lea     rax, aIpmOpSendCount; "IPM_OP_SEND_COUNTERS"
0x180028c76  retn
0x180028c78  sub     ecx, 7
0x180028c7b  jz      short loc_180028CAB
0x180028c7d  sub     ecx, 1
0x180028c80  jz      short loc_180028CA2
0x180028c82  sub     ecx, 1
0x180028c85  jz      short loc_180028C99
0x180028c87  cmp     ecx, 1
0x180028c8a  jnz     loc_180028E74
0x180028c90  lea     rax, aIpmOpGetpid; "IPM_OP_GETPID"
0x180028c97  retn
0x180028c99  lea     rax, aIpmOpPeriodicP_0; "IPM_OP_PERIODIC_PROCESS_RESTART_SCHEDUL"...
0x180028ca0  retn
0x180028ca2  lea     rax, aIpmOpPeriodicP_1; "IPM_OP_PERIODIC_PROCESS_RESTART_MEMORY_"...
0x180028ca9  retn
0x180028cab  lea     rax, aIpmOpPeriodicP; "IPM_OP_PERIODIC_PROCESS_RESTART_PERIOD_"...
0x180028cb2  retn
0x180028cb4  lea     rax, aIpmOpHresult; "IPM_OP_HRESULT"
0x180028cbb  retn
0x180028cbd  cmp     ecx, 11h
0x180028cc0  jg      short loc_180028D17
0x180028cc2  jz      short loc_180028D0E
0x180028cc4  sub     ecx, 0Ch
0x180028cc7  jz      short loc_180028D05
0x180028cc9  sub     ecx, 1
0x180028ccc  jz      short loc_180028CFC
0x180028cce  sub     ecx, 1
0x180028cd1  jz      short loc_180028CF3
0x180028cd3  sub     ecx, 1
0x180028cd6  jz      short loc_180028CEA
0x180028cd8  cmp     ecx, 1
0x180028cdb  jnz     loc_180028E74
0x180028ce1  lea     rax, aIpmOpNotifyOfP; "IPM_OP_NOTIFY_OF_PENDING_SHUTDOWN"
0x180028ce8  retn
0x180028cea  lea     rax, aIpmOpReportQue; "IPM_OP_REPORT_QUEUE_STOPPED"
0x180028cf1  retn
0x180028cf3  lea     rax, aIpmOpReportQue_0; "IPM_OP_REPORT_QUEUE_STARTED"
0x180028cfa  retn
0x180028cfc  lea     rax, aIpmOpStopQueue; "IPM_OP_STOP_QUEUE"
0x180028d03  retn
0x180028d05  lea     rax, aIpmOpStartQueu; "IPM_OP_START_QUEUE"
0x180028d0c  retn
0x180028d0e  lea     rax, aIpmOpRequestCu; "IPM_OP_REQUEST_CUSTOM_ACTION"
0x180028d15  retn
0x180028d17  sub     ecx, 12h
0x180028d1a  jz      short loc_180028D4A
0x180028d1c  sub     ecx, 1
0x180028d1f  jz      short loc_180028D41
0x180028d21  sub     ecx, 1
0x180028d24  jz      short loc_180028D38
0x180028d26  cmp     ecx, 1
0x180028d29  jnz     loc_180028E74
0x180028d2f  lea     rax, aIpmOpIdleTime; "IPM_OP_IDLE_TIME"
0x180028d36  retn
0x180028d38  lea     rax, aIpmOpAnonymous; "IPM_OP_ANONYMOUS_TOKEN_HANDLE"
0x180028d3f  retn
0x180028d41  lea     rax, aIpmOpCentralLo; "IPM_OP_CENTRAL_LOGGING_ENABLED"
0x180028d48  retn
0x180028d4a  lea     rax, aIpmOpReportCus; "IPM_OP_REPORT_CUSTOM_ACTION_RESULT"
0x180028d51  retn
0x180028d53  lea     rax, aIpmOpProtRegis; "IPM_OP_PROT_REGISTER"
0x180028d5a  retn
0x180028d5c  cmp     ecx, 25h ; '%'
0x180028d5f  jg      loc_180028E0A
0x180028d65  jz      loc_180028E01
0x180028d6b  cmp     ecx, 20h ; ' '
0x180028d6e  jg      short loc_180028DC5
0x180028d70  jz      short loc_180028DBC
0x180028d72  sub     ecx, 1Bh
0x180028d75  jz      short loc_180028DB3
0x180028d77  sub     ecx, 1
0x180028d7a  jz      short loc_180028DAA
0x180028d7c  sub     ecx, 1
0x180028d7f  jz      short loc_180028DA1
0x180028d81  sub     ecx, 1
0x180028d84  jz      short loc_180028D98
0x180028d86  cmp     ecx, 1
0x180028d89  jnz     loc_180028E74
0x180028d8f  lea     rax, aIpmOpProtDelet_0; "IPM_OP_PROT_DELETE_POOL"
0x180028d96  retn
0x180028d98  lea     rax, aIpmOpProtCreat; "IPM_OP_PROT_CREATE_POOL"
0x180028d9f  retn
0x180028da1  lea     rax, aIpmOpProtStopQ; "IPM_OP_PROT_STOP_QUEUE"
0x180028da8  retn
0x180028daa  lea     rax, aIpmOpProtStart; "IPM_OP_PROT_START_QUEUE"
0x180028db1  retn
0x180028db3  lea     rax, aIpmOpProtDereg; "IPM_OP_PROT_DEREGISTER"
0x180028dba  retn
0x180028dbc  lea     rax, aIpmOpProtCreat_0; "IPM_OP_PROT_CREATE_APP"
0x180028dc3  retn
0x180028dc5  sub     ecx, 21h ; '!'
0x180028dc8  jz      short loc_180028DF8
0x180028dca  sub     ecx, 1
0x180028dcd  jz      short loc_180028DEF
0x180028dcf  sub     ecx, 1
0x180028dd2  jz      short loc_180028DE6
0x180028dd4  cmp     ecx, 1
0x180028dd7  jnz     loc_180028E74
0x180028ddd  lea     rax, aIpmOpProtCallO; "IPM_OP_PROT_CALL_ON_NEXT_REQUEST"
0x180028de4  retn
0x180028de6  lea     rax, aIpmOpProtDisab; "IPM_OP_PROT_DISABLE_POOL"
0x180028ded  retn
0x180028def  lea     rax, aIpmOpProtEnabl; "IPM_OP_PROT_ENABLE_POOL"
0x180028df6  retn
0x180028df8  lea     rax, aIpmOpProtDelet; "IPM_OP_PROT_DELETE_APP"
0x180028dff  retn
0x180028e01  lea     rax, aIpmOpProtServe; "IPM_OP_PROT_SERVER_CONNECTED"
0x180028e08  retn
0x180028e0a  cmp     ecx, 2Bh ; '+'
0x180028e0d  jg      short loc_180028E60
0x180028e0f  jz      short loc_180028E57
0x180028e11  sub     ecx, 26h ; '&'
0x180028e14  jz      short loc_180028E4E
0x180028e16  sub     ecx, 1
0x180028e19  jz      short loc_180028E45
0x180028e1b  sub     ecx, 1
0x180028e1e  jz      short loc_180028E3C
0x180028e20  sub     ecx, 1
0x180028e23  jz      short loc_180028E33
0x180028e25  cmp     ecx, 1
0x180028e28  jnz     short loc_180028E74
0x180028e2a  lea     rax, aIpmOpProtAllQu; "IPM_OP_PROT_ALL_QUEUE_INSTANCES_STOPPED"
0x180028e31  retn
0x180028e33  lea     rax, aIpmOpProtSetPr; "IPM_OP_PROT_SET_PROTOCOL_ACTIVE_STATE"
0x180028e3a  retn
0x180028e3c  lea     rax, aIpmOpProtUpdat; "IPM_OP_PROT_UPDATE_POOL_ID"
0x180028e43  retn
0x180028e45  lea     rax, aIpmOpProtOkToT; "IPM_OP_PROT_OK_TO_TERMINATE"
0x180028e4c  retn
0x180028e4e  lea     rax, aIpmOpProtReque; "IPM_OP_PROT_REQUEST_OK_TO_TERMINATE"
0x180028e55  retn
0x180028e57  lea     rax, aIpmOpProtUpdat_1; "IPM_OP_PROT_UPDATE_APP_APP_POOL"
0x180028e5e  retn
0x180028e60  sub     ecx, 2Ch ; ','
0x180028e63  jz      short loc_180028E98
0x180028e65  sub     ecx, 1
0x180028e68  jz      short loc_180028E8F
0x180028e6a  sub     ecx, 1
0x180028e6d  jz      short loc_180028E86
0x180028e6f  cmp     ecx, 1
0x180028e72  jz      short loc_180028E7D
0x180028e74  lea     rax, aInvalidOpcode; "INVALID_OPCODE"
0x180028e7b  retn
0x180028e7d  lea     rax, aIpmOpProtMaxBl; "IPM_OP_PROT_MAX_BLOB_SIZE"
0x180028e84  retn
0x180028e86  lea     rax, aIpmOpProtPoolI; "IPM_OP_PROT_POOL_ID_UPDATE_ACK"
0x180028e8d  retn
0x180028e8f  lea     rax, aIpmOpProtUpdat_0; "IPM_OP_PROT_UPDATE_REQUESTS_BLOCKED"
0x180028e96  retn
0x180028e98  lea     rax, aIpmOpProtNewAp; "IPM_OP_PROT_NEW_APP_BINDINGS"
0x180028e9f  retn
```
