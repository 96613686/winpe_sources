# RasTapiCallback

- ea: `0x18000cb80`
- end: `0x18000d926`
- name: `RasTapiCallback`
- size: `3494`
- prototype: `void __stdcall(DWORD hDevice, DWORD dwMessage, DWORD_PTR dwInstance, DWORD_PTR dwParam1, DWORD_PTR dwParam2, DWORD_PTR dwParam3)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001b6c`
- `0x18000212c`
- `0x18000272c`
- `0x180002b20`
- `0x18000c8bc`
- `0x18000c918`
- `0x18000caac`
- `0x18000cb80`
- `0x18000d92c`
- `0x18000de88`
- `0x18000ff60`
- `0x180012340`
- `0x180012b00`
- `0x180023a14`
- `0x1800244ec`
- `0x180024b38`
- `0x18002619c`
- `0x18002927e`
- `0x1800292b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d233`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d5f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d233`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d5f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ccb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cd4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cde1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ce05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d661`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d6b3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ccb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cd4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cde1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ce05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d661`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d6b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d241`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d241`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d8f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000d8f3`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetCallStatus` at `0x18000d77e`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetCallStatus` at `0x18000d77e`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetCallInfoA` at `0x18000d1b4`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetCallInfoA` at `0x18000d5b3`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetCallInfoA` at `0x18000d61f`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetCallInfoA` at `0x18000d1b4`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetCallInfoA` at `0x18000d5b3`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetCallInfoA` at `0x18000d61f`
- `ext-ms-win-ras-tapi32-l1-1-1!lineDeallocateCall` at `0x18000cfce`
- `ext-ms-win-ras-tapi32-l1-1-1!lineDeallocateCall` at `0x18000d04c`
- `ext-ms-win-ras-tapi32-l1-1-1!lineDeallocateCall` at `0x18000d8bb`
- `ext-ms-win-ras-tapi32-l1-1-1!lineDeallocateCall` at `0x18000cfce`
- `ext-ms-win-ras-tapi32-l1-1-1!lineDeallocateCall` at `0x18000d04c`
- `ext-ms-win-ras-tapi32-l1-1-1!lineDeallocateCall` at `0x18000d8bb`
- `ext-ms-win-ras-tapi32-l1-1-1!lineDevSpecific` at `0x18000d285`
- `ext-ms-win-ras-tapi32-l1-1-1!lineDevSpecific` at `0x18000d285`
- `ext-ms-win-ras-tapi32-l1-1-1!lineSetStatusMessages` at `0x18000d41b`
- `ext-ms-win-ras-tapi32-l1-1-1!lineSetStatusMessages` at `0x18000d41b`
- `ext-ms-win-ras-tapi32-l1-1-1!lineOpenA` at `0x18000d3b6`
- `ext-ms-win-ras-tapi32-l1-1-1!lineOpenA` at `0x18000d3b6`

## string_xrefs

- `0x18000d54b`: `Some one else has already answered the call `
- `0x18000d6be`: `RasTapiCallback: Incoming Call`
- `0x18000ce77`: `**** Not posting completion for lineAnswer ***`
- `0x18000ceae`: `RasTapiCallback: Connect Attempt on %s failed. 0x%x`
- `0x18000cea0`: `RasTapiCallback: ConnectAttempt on %s failed. 0x%x`
- `0x18000d3d7`: `RasTapiCallback: LINECLOSE: lineOpen Failed. 0x%x`
- `0x18000d3e7`: `RasTapiCallback: Linestate changed from%d to PS_OPEN`
- `0x18000cc37`: `RasTapiaCallback: LINE_CREATE`
- `0x18000cc81`: `RasTapiCallback: dwCreateTapiPortsPerLine Failed. 0x%x`
- `0x18000cc1f`: `RasTapiCallback: LINE_REMOVE`
- `0x18000d209`: `RasTapiCallback: Port not found! line=0x%x, AddressID=0x%x`

## pseudocode

```c
void __fastcall RasTapiCallback(
        __int64 hDevice,
        __int64 dwMessage,
        DWORD_PTR dwInstance,
        DWORD_PTR dwParam1,
        DWORD_PTR dwParam2,
        DWORD_PTR dwParam3)
{
  int v8; // ebx
  HCALL v9; // r12d
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // edx
  const CHAR *v17; // rcx
  unsigned int *i; // rbx
  __int64 *v19; // rbx
  _DWORD *v20; // r8
  unsigned int v21; // r9d
  __int64 v22; // r10
  unsigned int v23; // r11d
  __int64 v24; // rax
  int v25; // ecx
  unsigned int v26; // ecx
  int v27; // edi
  const CHAR *v28; // rcx
  const CHAR *v29; // rcx
  const CHAR *v30; // rcx
  int v31; // eax
  unsigned int *v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 **v36; // rcx
  void *v37; // rcx
  _QWORD *v38; // rdi
  _QWORD *v39; // rbx
  int v40; // r8d
  __int64 v41; // rax
  HLOCAL j; // rbx
  _DWORD *v43; // rax
  _DWORD *v44; // rdi
  unsigned int v45; // eax
  _DWORD *v46; // r9
  unsigned int v47; // r10d
  unsigned int v48; // r11d
  __int64 v49; // rax
  int v50; // r8d
  _DWORD *v51; // rbx
  HLOCAL v52; // rdi
  unsigned int *dwCallbackInstance; // rcx
  unsigned int dwMediaModes; // r8d
  const CHAR *v56; // rcx
  __int64 v57; // rcx
  bool v58; // zf
  struct linecallinfo_tag *p_CallInfo; // r15
  unsigned int v60; // eax
  const CHAR *v61; // rcx
  unsigned int v62; // eax
  __int64 v63; // rcx
  unsigned int v64; // eax
  __int64 v65; // rcx
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int *v67; // [rsp+58h] [rbp-A8h] BYREF
  struct linecallstatus_tag CallStatus; // [rsp+60h] [rbp-A0h] BYREF
  struct linecallinfo_tag CallInfo; // [rsp+130h] [rbp+30h] BYREF

  v67 = 0;
  v8 = dwMessage;
  v9 = hDevice;
  GetMutex(hDevice, dwMessage, dwInstance, dwParam1);
  RasTapiTrace("RasTapicallback: msg=%ld , param1=%ul , param2=%ul");
  v10 = v8 - 2;
  if ( !v10 )
  {
    RasTapiTrace("RasTapicallback: linecallstate=0x%x");
    if ( !dwInstance )
    {
      v29 = "RasTapiCallback: LINE_CALLSTATE - line is NULL";
      goto LABEL_136;
    }
    if ( !*(_DWORD *)(dwInstance + 16) )
    {
      v29 = "RasTapiCallback: LINE_CALLSTATE - linestate = PS_CLOSED";
      goto LABEL_136;
    }
    if ( dwParam1 != 2 || !(unsigned int)DwProcessOfferEvent(v9) )
    {
      for ( i = (unsigned int *)RasPortsList; i; i = (unsigned int *)*((_QWORD *)i + 1) )
      {
        if ( i[58] == v9 && *((_QWORD *)i + 27) == dwInstance )
        {
          v67 = i;
          if ( dwParam1 != 256 )
            goto LABEL_178;
          if ( *((_QWORD *)i + 139) )
            goto LABEL_170;
          memset_0(&CallInfo.dwNeededSize, 0, 0x3E4u);
          v58 = *(_DWORD *)(dwInstance + 60) == 0;
          p_CallInfo = &CallInfo;
          CallInfo.dwTotalSize = 1000;
          if ( v58 )
            v60 = lineGetCallInfoA(v9, &CallInfo);
          else
            v60 = RasLineGetCallInfo(v9, &CallInfo);
          if ( *(_DWORD *)(dwInstance + 60) )
          {
            if ( !v60 )
              goto LABEL_166;
          }
          else if ( v60 <= 0x80000000 )
          {
            goto LABEL_166;
          }
          if ( v60 == -2147483571 || CallInfo.dwNeededSize > 0x3E8 )
          {
            hMem = (HLOCAL)CallInfo.dwNeededSize;
            p_CallInfo = (struct linecallinfo_tag *)LocalAlloc(0x40u, CallInfo.dwNeededSize);
            if ( !p_CallInfo )
            {
              GetLastError();
              goto LABEL_217;
            }
            p_CallInfo->dwTotalSize = (unsigned int)hMem;
            if ( *(_DWORD *)(dwInstance + 60) )
              v60 = RasLineGetCallInfo(v9, p_CallInfo);
            else
              v60 = lineGetCallInfoA(v9, p_CallInfo);
          }
LABEL_166:
          if ( *(_DWORD *)(dwInstance + 60) )
          {
            if ( !v60 )
              goto LABEL_168;
          }
          else if ( v60 <= 0x80000000 )
          {
LABEL_168:
            DwGetConnectInfo(i, v9, p_CallInfo);
            RasTapiTrace("RasTapiCallback: DwGetConnectInforeturned 0x%x");
            if ( &CallInfo != p_CallInfo )
              LocalFree(p_CallInfo);
LABEL_170:
            RasTapiTrace("RasTapiCallback: Connected on %s");
            if ( i[14] == 4 )
            {
              v61 = "RasTapiCallback: Outgoing call";
LABEL_172:
              RasTapiTrace(v61);
              goto LABEL_53;
            }
            i[15] = 4;
            RasTapiTrace("RasTapiCallback: Incoming Call");
            PostNotificationCompletion(i);
LABEL_178:
            if ( ((dwParam1 - 64) & 0xFFFFFFFFFFFFFFBFuLL) == 0 )
            {
              RasTapiTrace("RasTapiCallback: LINECALLSTATE. Failure. param1 = 0x%x");
              if ( i[14] == 4 )
                PostNotificationCompletion(i);
            }
            if ( dwParam1 == 0x4000 )
            {
              v62 = i[14];
              switch ( v62 )
              {
                case 4u:
                  i[64] = DwRasErrorFromDisconnectMode((unsigned int)dwParam2, i);
                  RasTapiTrace("RasTapiCallback: LINECALLSTATE_DISCONNECTED for port %s. AsyncErr = %d, param2=0x%x");
                  goto LABEL_53;
                case 0u:
                  goto LABEL_217;
                case 3u:
                  memset_0(&CallStatus.dwNeededSize, 0, 0xC4u);
                  CallStatus.dwTotalSize = 200;
                  v63 = i[58];
                  if ( *(_DWORD *)(dwInstance + 60) )
                    RasLineGetCallStatus(v63, &CallStatus);
                  else
                    lineGetCallStatus(v63, &CallStatus);
                  i[273] = (CallStatus.dwCallState == 0x4000) + 1;
                  RasTapiTrace("RasTapiCallback: lineGetCallStatus for %s returned 0x%x");
                  RasTapiTrace("RasTapiCallback: DisconnectReason mapped to %d");
                  break;
                default:
                  i[273] = 0;
                  break;
              }
              RasTapiTrace("RasTapiCallback: LINECALLSTATE - initiating Port Disconnect");
              if ( (unsigned int)InitiatePortDisconnection(i) == 600 )
                goto LABEL_217;
              RasTapiTrace("RasTapiCallback: PortDisconnected sync");
              goto LABEL_193;
            }
            if ( dwParam1 == 64 )
            {
              if ( i[14] != 4 )
                goto LABEL_217;
              i[64] = 676;
              v61 = "RasTapiCallback: Failed to initiate connection. LINECALLSTATE_BUSY";
              goto LABEL_172;
            }
            if ( dwParam1 != 1 )
              goto LABEL_217;
            v64 = i[14];
            if ( v64 != 5 || i[63] != -1 )
            {
              if ( v64 == 1 )
              {
                if ( i[15] != 1 )
                {
LABEL_206:
                  i[275] = 1;
                  goto LABEL_217;
                }
LABEL_208:
                RasTapiTrace("RasTapiCallback: Receied IDLE in LS_RINGING state!");
                i[273] = 1;
LABEL_209:
                if ( i[14] != 7 )
                  i[14] = 1;
                RasTapiTrace("RasTapiCallback: Received Idle. Deallocating for %s, callhandle = 0x%x");
                v65 = i[58];
                if ( *(_DWORD *)(dwInstance + 60) )
                  RasLineCloseCall(v65);
                else
                  lineDeallocateCall(v65);
                i[58] = -1;
                i[275] = 0;
                goto LABEL_193;
              }
              if ( v64 != 7 && (i[15] != 1 || v64 != 2) )
                goto LABEL_206;
            }
            if ( i[15] == 1 )
              goto LABEL_208;
            goto LABEL_209;
          }
          RasTapiTrace("RasTapiCallback: LINE_CALLSTATE - lineGetCallInfo Failed. %d");
          if ( &CallInfo == p_CallInfo )
            goto LABEL_217;
          v37 = p_CallInfo;
LABEL_176:
          LocalFree(v37);
          goto LABEL_217;
        }
      }
      v67 = 0;
      if ( dwParam1 != 256 )
      {
        v17 = "RasTapiCallback: FindPortByCallHandle, hcall = 0x%x failed";
        goto LABEL_216;
      }
      RasTapiTrace("Some one else has already answered the call ");
      DwProcessOfferEvent(v9);
    }
    v17 = "DwProcessOfferEvent failed. 0x%x";
    goto LABEL_216;
  }
  v11 = v10 - 1;
  if ( v11 )
  {
    v12 = v11 - 1;
    if ( v12 )
    {
      v13 = v12 - 4;
      if ( v13 )
      {
        v14 = v13 - 4;
        if ( v14 )
        {
          v15 = v14 - 7;
          if ( v15 )
          {
            if ( v15 == 6 )
            {
              RasTapiTrace("RasTapiCallback: LINE_REMOVE");
              PostNotificationRemoveLine((unsigned int)dwParam1);
            }
            goto LABEL_217;
          }
          LODWORD(v67) = 0;
          hMem = 0;
          RasTapiTrace("RasTapiaCallback: LINE_CREATE");
          if ( (_DWORD)dwParam3 )
          {
            ++g_dwNumNDProxyLines;
            v16 = 1;
          }
          else
          {
            ++g_dwNumTapiLines;
            v16 = 0;
          }
          if ( !(unsigned int)dwCreateTapiPortsPerLine(dwParam1, v16, &v67, &hMem) )
          {
            RasTapiTrace("RasTapiCallback: cNewPorts = %d");
            AddNewPortsPerLine(hMem, (unsigned int)v67);
            LocalFree(hMem);
            hMem = 0;
            goto LABEL_217;
          }
          v17 = "RasTapiCallback: dwCreateTapiPortsPerLine Failed. 0x%x";
LABEL_216:
          RasTapiTrace(v17);
          goto LABEL_217;
        }
        RasTapiTrace("LINE_REPLY. param1=0x%x");
        for ( i = (unsigned int *)RasPortsList; i; i = (unsigned int *)*((_QWORD *)i + 1) )
        {
          if ( i[63] == (_DWORD)dwParam1
            || i[298] && (i[280] == (_DWORD)dwParam1 || i[284] == (_DWORD)dwParam1 || i[294] == (_DWORD)dwParam1) )
          {
            if ( i[280] == dwParam1 )
            {
              i[280] = -1;
              LocalFree(*((HLOCAL *)i + 141));
              *((_QWORD *)i + 141) = 0;
              goto LABEL_217;
            }
            if ( i[284] == dwParam1 )
            {
              i[284] = -1;
              if ( i[14] == 3 )
              {
                v20 = (_DWORD *)*((_QWORD *)i + 146);
                v21 = 0;
                v22 = *((_QWORD *)i + 143);
                v23 = *(_DWORD *)(v22 + 8);
                if ( *v20 != v20[3] )
                {
                  do
                  {
                    if ( v21 >= v23 )
                      break;
                    v24 = v21++;
                    *((_BYTE *)v20 + (unsigned int)v20[1] + 16) = *(_BYTE *)(v24 + v22 + 12);
                    LODWORD(v24) = v20[1];
                    v25 = ++*v20;
                    v20[1] = (unsigned int)(v24 + 1) % v20[3];
                  }
                  while ( v25 != v20[3] );
                }
              }
              PostNotificationCompletion(i);
              LocalFree(*((HLOCAL *)i + 143));
              *((_QWORD *)i + 143) = 0;
              goto LABEL_217;
            }
            if ( i[294] == dwParam1 )
            {
              LocalFree(*((HLOCAL *)i + 148));
              *((_QWORD *)i + 148) = 0;
              goto LABEL_217;
            }
            i[63] = -1;
            v26 = i[14];
            if ( ((v26 - 5) & 0xFFFFFFFD) != 0 )
            {
              if ( !dwParam2 )
              {
                if ( v26 != 2 )
                  goto LABEL_217;
                v27 = 3;
                if ( i[15] == 2 )
                {
                  v28 = "RasTapiCallback: LINE_REPLY. Changing Listen state for %s from %d -> %d";
                  goto LABEL_50;
                }
                if ( i[15] != 3 )
                  goto LABEL_217;
                RasTapiTrace("RasTapiCallback: LINE_REPLY. Changing Listen state for %s from %d -> %d");
                v29 = "**** Not posting completion for lineAnswer ***";
                i[15] = 4;
LABEL_136:
                RasTapiTrace(v29);
                goto LABEL_217;
              }
              if ( v26 != 4 )
              {
                if ( v26 != 2 )
                  goto LABEL_217;
                if ( i[15] == 2 )
                {
                  v27 = 3;
                  v28 = "RasTapiCallback: Changing Listen State for %s from %d -> %d";
LABEL_50:
                  RasTapiTrace(v28);
                }
                else
                {
                  RasTapiTrace("RasTapiCallback: Changing Listen State for %s from %d -> %d.param2=0x%x");
                  v27 = 5;
                }
                i[15] = v27;
                goto LABEL_53;
              }
              if ( dwParam2 == 2147483663 || dwParam2 == 2147483653 )
              {
                v30 = "RasTapiCallback: Connect Attempt on %s failed. 0x%x";
                v31 = 676;
              }
              else
              {
                v30 = "RasTapiCallback: ConnectAttempt on %s failed. 0x%x";
                v31 = 692;
              }
              i[64] = v31;
              RasTapiTrace(v30);
              RasTapiTrace("RasTapiCallback: LINE_REPLY. AsyncErr = %d");
LABEL_53:
              v32 = i;
LABEL_54:
              PostNotificationCompletion(v32);
              goto LABEL_217;
            }
            RasTapiTrace("RasTapiCallback: lineDropped. port %s, id=0x%x");
            i[276] &= ~4u;
            if ( !i[275] )
              goto LABEL_217;
            i[275] = 0;
            RasTapiTrace("RasTapiCallback: Idle Received for port %s");
            if ( i[14] != 7 )
            {
              RasTapiTrace("RasTapiCallback: changing state of %s. %d -> %d");
              i[14] = 1;
            }
            RasTapiTrace("RasTapiCallback: lineDeallocateCall for %s,hcall = 0x%x");
            v33 = i[58];
            if ( *(_DWORD *)(*((_QWORD *)i + 27) + 60LL) )
              RasLineCloseCall(v33);
            else
              lineDeallocateCall(v33);
            i[58] = -1;
            if ( (i[276] & 8) != 0 )
            {
              RasTapiTrace("RasTapiCallback: Posting listen on rasman's behalf on port %s");
              i[276] &= ~8u;
              DeviceListen();
              v17 = "DeviceListen returned 0x%x";
              goto LABEL_216;
            }
LABEL_193:
            PostDisconnectCompletion(i);
            goto LABEL_217;
          }
        }
        v19 = (__int64 *)ZombieCallList;
        RasTapiTrace("PortByRequestId found");
        while ( v19 != &ZombieCallList )
        {
          if ( *((_DWORD *)v19 + 4) )
          {
            RasTapiTrace("RasTapiCallback: LINE_REPLY Deallocatingcall. hcall = 0x%x");
            v34 = *((unsigned int *)v19 + 5);
            if ( *((_DWORD *)v19 + 6) )
              RasLineCloseCall(v34);
            else
              lineDeallocateCall(v34);
            v35 = *v19;
            if ( *(__int64 **)(*v19 + 8) != v19 || (v36 = (__int64 **)v19[1], *v36 != v19) )
              __fastfail(3u);
            *v36 = (__int64 *)v35;
            *(_QWORD *)(v35 + 8) = v36;
            v37 = v19;
            goto LABEL_176;
          }
          v19 = (__int64 *)*v19;
        }
      }
      else
      {
        RasTapiTrace("LINE_LINEDEVSTATE. param1=0x%x, line=0x%x");
        if ( dwParam1 != 2 )
          goto LABEL_217;
        if ( !dwInstance )
          goto LABEL_217;
        if ( !*(_DWORD *)(dwInstance + 16) )
          goto LABEL_217;
        v38 = RasPortsList;
        if ( !RasPortsList )
          goto LABEL_217;
        v39 = RasPortsList;
        while ( *((_DWORD *)v39 + 14) == 6
             || v39[27] != dwInstance
             || *((_DWORD *)v39 + 14) != 2
             || *((_DWORD *)v39 + 15) != 1 )
        {
          v38 = (_QWORD *)v39[1];
          v39 = v38;
          if ( !v38 )
            goto LABEL_217;
        }
        v40 = *((_DWORD *)v39 + 274);
        if ( v40 )
          *((_DWORD *)v39 + 274) = v40 - 1;
        RasTapiTrace("RasTapiCallback: LINEDEVSTATE - Number of rings for %s = %d");
        if ( !*((_DWORD *)v39 + 274) )
        {
          RasTapiTrace("RasTapiCallback: Changing Listen State for %s from %d -> %d");
          v41 = *(_QWORD *)(dwInstance + 40);
          if ( v41 )
          {
            ++*(_DWORD *)(v41 + 16);
            RasTapiTrace("CurrentDialInClients=0x%x");
          }
          *((_DWORD *)v39 + 276) |= 2u;
          v32 = (unsigned int *)v38;
          *((_DWORD *)v39 + 15) = 2;
          goto LABEL_54;
        }
      }
    }
    else
    {
      if ( !dwInstance )
        goto LABEL_217;
      RasTapiTrace("RasTapiCallback:LINE_DEVSPECIFIC");
      if ( !*(_DWORD *)(dwInstance + 16) )
        goto LABEL_217;
      memset_0(&CallInfo.dwNeededSize, 0, 0x3E4u);
      CallInfo.dwTotalSize = 1000;
      if ( (unsigned int)lineGetCallInfoA(v9, &CallInfo) > 0x80000000 )
      {
        RasTapiTrace("RastapiCallback: lineGetCallInfo failed. 0x%x. hcall=0x%x, line=0x%x");
        goto LABEL_217;
      }
      for ( j = RasPortsList; ; j = (HLOCAL)*((_QWORD *)j + 1) )
      {
        if ( !j )
        {
          RasTapiTrace("RasTapiCallback: Port not found! line=0x%x, AddressID=0x%x");
          goto LABEL_217;
        }
        if ( *((_DWORD *)j + 56) == CallInfo.dwAddressID && *((_QWORD *)j + 27) == dwInstance )
          break;
      }
      if ( dwParam1 == 1 )
      {
        v43 = LocalAlloc(0x40u, 0x5ECu);
        v44 = v43;
        if ( !v43 )
        {
          GetLastError();
          v17 = "RasTapiCallback: RASTAPI_DEV_RECV. LocalAlloc failed. %d";
          goto LABEL_216;
        }
        *v43 = 1;
        v43[2] = 1500;
        *((_QWORD *)j + 143) = v43;
        v45 = lineDevSpecific(
                *(_DWORD *)(*((_QWORD *)j + 27) + 12LL),
                *((_DWORD *)j + 56),
                *((_DWORD *)j + 58),
                v43,
                0x5ECu);
        *((_DWORD *)j + 284) = v45;
        if ( v45 )
        {
          if ( v45 <= 0x80000000 )
            goto LABEL_217;
          RasTapiTrace("RasTapiCallback: lineDevSpecific failed. 0x%x");
          *((_QWORD *)j + 143) = 0;
          *((_DWORD *)j + 284) = -1;
        }
        else
        {
          v46 = (_DWORD *)*((_QWORD *)j + 146);
          v47 = 0;
          v48 = v44[2];
          if ( *v46 != v46[3] )
          {
            do
            {
              if ( v47 >= v48 )
                break;
              v49 = v47++;
              *((_BYTE *)v46 + (unsigned int)v46[1] + 16) = *((_BYTE *)v44 + v49 + 12);
              LODWORD(v49) = v46[1];
              v50 = ++*v46;
              v46[1] = (unsigned int)(v49 + 1) % v46[3];
            }
            while ( v50 != v46[3] );
          }
          *((_QWORD *)j + 143) = 0;
        }
        v37 = v44;
        goto LABEL_176;
      }
    }
  }
  else
  {
    RasTapiTrace("LINE_CLOSE. line=0x%x");
    if ( dwInstance )
    {
      if ( *(_DWORD *)(dwInstance + 16) )
      {
        v51 = RasPortsList;
        if ( RasPortsList )
        {
          v52 = RasPortsList;
          do
          {
            if ( *((_DWORD *)v52 + 14) == 6 )
            {
              v51 = (_DWORD *)*((_QWORD *)v52 + 1);
            }
            else
            {
              dwCallbackInstance = (unsigned int *)*((_QWORD *)v52 + 27);
              if ( dwCallbackInstance == (unsigned int *)dwInstance )
              {
                if ( dwCallbackInstance[4] != 1 )
                {
                  dwMediaModes = dwCallbackInstance[14];
                  if ( dwCallbackInstance[15]
                     ? RasLineOpen(
                         dwCallbackInstance[2],
                         4,
                         dwMediaModes,
                         (__int64)dwCallbackInstance,
                         (__int64)(dwCallbackInstance + 3))
                     : lineOpenA(
                         RasLine,
                         dwCallbackInstance[2],
                         dwCallbackInstance + 3,
                         dwCallbackInstance[6],
                         dwCallbackInstance[7],
                         (DWORD_PTR)dwCallbackInstance,
                         4u,
                         dwMediaModes,
                         0) )
                  {
                    v56 = "RasTapiCallback: LINECLOSE: lineOpen Failed. 0x%x";
                  }
                  else
                  {
                    v56 = "RasTapiCallback: Linestate changed from%d to PS_OPEN";
                    *(_DWORD *)(*((_QWORD *)v52 + 27) + 16LL) = 1;
                  }
                  RasTapiTrace(v56);
                  v57 = *((_QWORD *)v52 + 27);
                  if ( !*(_DWORD *)(v57 + 60) )
                    lineSetStatusMessages(*(_DWORD *)(v57 + 12), 2u, 0);
                }
                if ( !v51[64] )
                  v51[64] = 651;
                v51[273] = 1;
                v51[58] = -1;
                v51[15] = 5;
                RasTapiTrace("RasTapiCallback: LINECLOSE - Signalling HW Failure for %s");
                RasTapiTrace("RasTapiCallback: LINECLOSE - AsyncErr = %d");
                PostDisconnectCompletion(v51);
              }
              v51 = (_DWORD *)*((_QWORD *)v51 + 1);
            }
            v52 = v51;
          }
          while ( v51 );
        }
      }
    }
  }
LABEL_217:
  if ( !ReleaseMutex(RasTapiMutex) )
    GetLastError();
}

```

## disassembly

```asm
0x18000cb80  push    rbp
0x18000cb82  push    rbx
0x18000cb83  push    rsi
0x18000cb84  push    rdi
0x18000cb85  push    r12
0x18000cb87  push    r13
0x18000cb89  push    r14
0x18000cb8b  push    r15
0x18000cb8d  lea     rbp, [rsp-438h]
0x18000cb95  sub     rsp, 538h
0x18000cb9c  mov     rax, cs:__security_cookie
0x18000cba3  xor     rax, rsp
0x18000cba6  mov     [rbp+470h+var_50], rax
0x18000cbad  xor     r15d, r15d
0x18000cbb0  mov     rdi, r9
0x18000cbb3  mov     [rsp+570h+var_518], r15
0x18000cbb8  mov     rsi, r8
0x18000cbbb  mov     ebx, edx
0x18000cbbd  mov     r12, rcx
0x18000cbc0  call    GetMutex
0x18000cbc5  mov     r13, [rbp+470h+dwParam2]
0x18000cbcc  lea     rcx, aRastapicallbac_35; "RasTapicallback: msg=%ld , param1=%ul ,"...
0x18000cbd3  mov     r9, r13
0x18000cbd6  mov     r8, rdi
0x18000cbd9  mov     edx, ebx
0x18000cbdb  call    RasTapiTrace
0x18000cbe0  sub     ebx, 2
0x18000cbe3  jz      loc_18000D48E
0x18000cbe9  sub     ebx, 1
0x18000cbec  jz      loc_18000D319
0x18000cbf2  sub     ebx, 1
0x18000cbf5  jz      loc_18000D176
0x18000cbfb  lea     r14d, [r15+4]
0x18000cbff  sub     ebx, r14d
0x18000cc02  jz      loc_18000D081
0x18000cc08  sub     ebx, r14d
0x18000cc0b  jz      loc_18000CCC0
0x18000cc11  sub     ebx, 7
0x18000cc14  jz      short loc_18000CC37
0x18000cc16  cmp     ebx, 6
0x18000cc19  jnz     loc_18000D8EC
0x18000cc1f  lea     rcx, aRastapicallbac_29; "RasTapiCallback: LINE_REMOVE"
0x18000cc26  call    RasTapiTrace
0x18000cc2b  mov     ecx, edi
0x18000cc2d  call    PostNotificationRemoveLine
0x18000cc32  jmp     loc_18000D8EC
0x18000cc37  lea     rcx, aRastapiacallba; "RasTapiaCallback: LINE_CREATE"
0x18000cc3e  mov     dword ptr [rsp+570h+var_518], r15d
0x18000cc43  mov     [rsp+570h+hMem], r15
0x18000cc48  call    RasTapiTrace
0x18000cc4d  cmp     dword ptr [rbp+470h+dwParam3], r15d
0x18000cc54  jz      short loc_18000CC63
0x18000cc56  inc     cs:g_dwNumNDProxyLines
0x18000cc5c  mov     edx, 1
0x18000cc61  jmp     short loc_18000CC6C
0x18000cc63  inc     cs:g_dwNumTapiLines
0x18000cc69  mov     edx, r15d
0x18000cc6c  mov     ecx, edi
0x18000cc6e  lea     r9, [rsp+570h+hMem]
0x18000cc73  lea     r8, [rsp+570h+var_518]
0x18000cc78  call    dwCreateTapiPortsPerLine
0x18000cc7d  test    eax, eax
0x18000cc7f  jz      short loc_18000CC8D
0x18000cc81  lea     rcx, aRastapicallbac_12; "RasTapiCallback: dwCreateTapiPortsPerLi"...
0x18000cc88  jmp     loc_18000D8E5
0x18000cc8d  mov     edx, dword ptr [rsp+570h+var_518]
0x18000cc91  lea     rcx, aRastapicallbac_30; "RasTapiCallback: cNewPorts = %d"
0x18000cc98  call    RasTapiTrace
0x18000cc9d  mov     edx, dword ptr [rsp+570h+var_518]
0x18000cca1  mov     rcx, [rsp+570h+hMem]
0x18000cca6  call    AddNewPortsPerLine
0x18000ccab  mov     rcx, [rsp+570h+hMem]; hMem
0x18000ccb0  call    cs:__imp_LocalFree
0x18000ccb6  mov     [rsp+570h+hMem], r15
0x18000ccbb  jmp     loc_18000D8EC
0x18000ccc0  mov     rdx, rdi
0x18000ccc3  lea     rcx, aLineReplyParam; "LINE_REPLY. param1=0x%x"
0x18000ccca  call    RasTapiTrace
0x18000cccf  mov     rbx, cs:RasPortsList
0x18000ccd6  jmp     short loc_18000CD05
0x18000ccd8  cmp     [rbx+0FCh], edi
0x18000ccde  jz      short loc_18000CD29
0x18000cce0  cmp     [rbx+4A8h], r15d
0x18000cce7  jz      short loc_18000CD01
0x18000cce9  cmp     [rbx+460h], edi
0x18000ccef  jz      short loc_18000CD29
0x18000ccf1  cmp     [rbx+470h], edi
0x18000ccf7  jz      short loc_18000CD29
0x18000ccf9  cmp     [rbx+498h], edi
0x18000ccff  jz      short loc_18000CD29
0x18000cd01  mov     rbx, [rbx+8]
0x18000cd05  test    rbx, rbx
0x18000cd08  jnz     short loc_18000CCD8
0x18000cd0a  mov     rbx, cs:ZombieCallList
0x18000cd11  lea     rcx, aPortbyrequesti; "PortByRequestId found"
0x18000cd18  call    RasTapiTrace
0x18000cd1d  lea     rax, ZombieCallList
0x18000cd24  jmp     loc_18000D02A
0x18000cd29  test    rbx, rbx
0x18000cd2c  jz      short loc_18000CD0A
0x18000cd2e  mov     eax, [rbx+460h]
0x18000cd34  cmp     rax, rdi
0x18000cd37  jnz     short loc_18000CD5C
0x18000cd39  mov     dword ptr [rbx+460h], 0FFFFFFFFh
0x18000cd43  mov     rcx, [rbx+468h]; hMem
0x18000cd4a  call    cs:__imp_LocalFree
0x18000cd50  mov     [rbx+468h], r15
0x18000cd57  jmp     loc_18000D8EC
0x18000cd5c  mov     eax, [rbx+470h]
0x18000cd62  cmp     rax, rdi
0x18000cd65  jnz     loc_18000CDF3
0x18000cd6b  mov     edi, 3
0x18000cd70  mov     dword ptr [rbx+470h], 0FFFFFFFFh
0x18000cd7a  cmp     [rbx+38h], edi
0x18000cd7d  jnz     short loc_18000CDD2
0x18000cd7f  mov     r8, [rbx+490h]
0x18000cd86  mov     r9d, r15d
0x18000cd89  mov     r10, [rbx+478h]
0x18000cd90  mov     eax, [r8+0Ch]
0x18000cd94  mov     r11d, [r10+8]
0x18000cd98  cmp     [r8], eax
0x18000cd9b  jz      short loc_18000CDD2
0x18000cd9d  cmp     r9d, r11d
0x18000cda0  jnb     short loc_18000CDD2
0x18000cda2  mov     ecx, [r8+4]
0x18000cda6  xor     edx, edx
0x18000cda8  mov     eax, r9d
0x18000cdab  inc     r9d
0x18000cdae  mov     al, [rax+r10+0Ch]
0x18000cdb3  mov     [rcx+r8+10h], al
0x18000cdb8  mov     eax, [r8+4]
0x18000cdbc  inc     dword ptr [r8]
0x18000cdbf  inc     eax
0x18000cdc1  div     dword ptr [r8+0Ch]
0x18000cdc5  mov     ecx, [r8]
0x18000cdc8  mov     [r8+4], edx
0x18000cdcc  cmp     ecx, [r8+0Ch]
0x18000cdd0  jnz     short loc_18000CD9D
0x18000cdd2  mov     rcx, rbx
0x18000cdd5  call    PostNotificationCompletion
0x18000cdda  mov     rcx, [rbx+478h]; hMem
0x18000cde1  call    cs:__imp_LocalFree
0x18000cde7  mov     [rbx+478h], r15
0x18000cdee  jmp     loc_18000D8EC
0x18000cdf3  mov     eax, [rbx+498h]
0x18000cdf9  cmp     rax, rdi
0x18000cdfc  jnz     short loc_18000CE17
0x18000cdfe  mov     rcx, [rbx+4A0h]; hMem
0x18000ce05  call    cs:__imp_LocalFree
0x18000ce0b  mov     [rbx+4A0h], r15
0x18000ce12  jmp     loc_18000D8EC
0x18000ce17  mov     dword ptr [rbx+0FCh], 0FFFFFFFFh
0x18000ce21  mov     ecx, [rbx+38h]
0x18000ce24  lea     eax, [rcx-5]
0x18000ce27  test    eax, 0FFFFFFFDh
0x18000ce2c  jz      loc_18000CF3E
0x18000ce32  test    r13, r13
0x18000ce35  jnz     short loc_18000CE87
0x18000ce37  cmp     ecx, 2
0x18000ce3a  jnz     loc_18000D8EC
0x18000ce40  lea     edi, [rcx+1]
0x18000ce43  cmp     [rbx+3Ch], ecx
0x18000ce46  jnz     short loc_18000CE58
0x18000ce48  lea     rdx, [rbx+18h]
0x18000ce4c  lea     rcx, aRastapicallbac_40; "RasTapiCallback: LINE_REPLY. Changing L"...
0x18000ce53  jmp     loc_18000CF02
0x18000ce58  cmp     [rbx+3Ch], edi
0x18000ce5b  jnz     loc_18000D8EC
0x18000ce61  lea     rdx, [rbx+18h]
0x18000ce65  mov     r9d, r14d
0x18000ce68  mov     r8d, edi
0x18000ce6b  lea     rcx, aRastapicallbac_40; "RasTapiCallback: LINE_REPLY. Changing L"...
0x18000ce72  call    RasTapiTrace
0x18000ce77  lea     rcx, aNotPostingComp; "**** Not posting completion for lineAns"...
0x18000ce7e  mov     [rbx+3Ch], r14d
0x18000ce82  jmp     loc_18000D4A9
0x18000ce87  cmp     ecx, r14d
0x18000ce8a  jnz     short loc_18000CEE2
0x18000ce8c  mov     eax, 8000000Fh
0x18000ce91  cmp     r13, rax
0x18000ce94  jz      short loc_18000CEAE
0x18000ce96  mov     eax, 80000005h
0x18000ce9b  cmp     r13, rax
0x18000ce9e  jz      short loc_18000CEAE
0x18000cea0  lea     rcx, aRastapicallbac_15; "RasTapiCallback: ConnectAttempt on %s f"...
0x18000cea7  mov     eax, 2B4h
0x18000ceac  jmp     short loc_18000CEBA
0x18000ceae  lea     rcx, aRastapicallbac_36; "RasTapiCallback: Connect Attempt on %s "...
0x18000ceb5  mov     eax, 2A4h
0x18000ceba  lea     rdi, [rbx+100h]
0x18000cec1  mov     r8, rdi
0x18000cec4  mov     [rdi], eax
0x18000cec6  mov     r8, r13
0x18000cec9  lea     rdx, [rbx+18h]
0x18000cecd  call    RasTapiTrace
0x18000ced2  mov     edx, [rdi]
0x18000ced4  lea     rcx, aRastapicallbac_25; "RasTapiCallback: LINE_REPLY. AsyncErr ="...
0x18000cedb  call    RasTapiTrace
0x18000cee0  jmp     short loc_18000CF31
0x18000cee2  cmp     ecx, 2
0x18000cee5  jnz     loc_18000D8EC
0x18000ceeb  mov     r8d, [rbx+3Ch]
0x18000ceef  lea     rdx, [rbx+18h]
0x18000cef3  cmp     r8d, ecx
0x18000cef6  jnz     short loc_18000CF12
0x18000cef8  lea     edi, [rcx+1]
0x18000cefb  lea     rcx, aRastapicallbac_13; "RasTapiCallback: Changing Listen State "...
0x18000cf02  mov     r8d, 2
0x18000cf08  mov     r9d, edi
0x18000cf0b  call    RasTapiTrace
0x18000cf10  jmp     short loc_18000CF2E
0x18000cf12  mov     r9d, 5
0x18000cf18  mov     qword ptr [rsp+570h+dwSize], r13
0x18000cf1d  lea     rcx, aRastapicallbac_44; "RasTapiCallback: Changing Listen State "...
0x18000cf24  call    RasTapiTrace
0x18000cf29  mov     edi, 5
0x18000cf2e  mov     [rbx+3Ch], edi
0x18000cf31  mov     rcx, rbx
0x18000cf34  call    PostNotificationCompletion
0x18000cf39  jmp     loc_18000D8EC
0x18000cf3e  lea     rdi, [rbx+18h]
0x18000cf42  or      r8d, 0FFFFFFFFh
0x18000cf46  mov     rdx, rdi
0x18000cf49  lea     rcx, aRastapicallbac_41; "RasTapiCallback: lineDropped. port %s, "...
0x18000cf50  call    RasTapiTrace
0x18000cf55  and     dword ptr [rbx+450h], 0FFFFFFFBh
0x18000cf5c  cmp     [rbx+44Ch], r15d
0x18000cf63  jz      loc_18000D8EC
0x18000cf69  mov     rdx, rdi
0x18000cf6c  mov     [rbx+44Ch], r15d
0x18000cf73  lea     rcx, aRastapicallbac_20; "RasTapiCallback: Idle Received for port"...
0x18000cf7a  call    RasTapiTrace
0x18000cf7f  mov     r8d, [rbx+38h]
0x18000cf83  cmp     r8d, 7
0x18000cf87  jz      short loc_18000CFA5
0x18000cf89  mov     r9d, 1
0x18000cf8f  lea     rcx, aRastapicallbac_2; "RasTapiCallback: changing state of %s. "...
0x18000cf96  mov     rdx, rdi
0x18000cf99  call    RasTapiTrace
0x18000cf9e  mov     dword ptr [rbx+38h], 1
0x18000cfa5  mov     r8d, [rbx+0E8h]
0x18000cfac  lea     rcx, aRastapicallbac_26; "RasTapiCallback: lineDeallocateCall for"...
0x18000cfb3  mov     rdx, rdi
0x18000cfb6  call    RasTapiTrace
0x18000cfbb  mov     rax, [rbx+0D8h]
0x18000cfc2  mov     ecx, [rbx+0E8h]; hCall
0x18000cfc8  cmp     [rax+3Ch], r15d
0x18000cfcc  jnz     short loc_18000CFD6
0x18000cfce  call    cs:__imp_lineDeallocateCall
0x18000cfd4  jmp     short loc_18000CFDB
0x18000cfd6  call    RasLineCloseCall
0x18000cfdb  mov     dword ptr [rbx+0E8h], 0FFFFFFFFh
0x18000cfe5  test    byte ptr [rbx+450h], 8
0x18000cfec  jz      loc_18000D7F9
0x18000cff2  mov     rdx, rdi
0x18000cff5  lea     rcx, aRastapicallbac_1; "RasTapiCallback: Posting listen on rasm"...
0x18000cffc  call    RasTapiTrace
0x18000d001  and     dword ptr [rbx+450h], 0FFFFFFF7h
0x18000d008  xor     r8d, r8d
0x18000d00b  xor     edx, edx
0x18000d00d  mov     rcx, rbx
0x18000d010  call    DeviceListen
0x18000d015  lea     rcx, aDevicelistenRe; "DeviceListen returned 0x%x"
0x18000d01c  jmp     loc_18000D8E5
0x18000d021  cmp     [rbx+10h], r15d
0x18000d025  jnz     short loc_18000D034
0x18000d027  mov     rbx, [rbx]
0x18000d02a  cmp     rbx, rax
0x18000d02d  jnz     short loc_18000D021
0x18000d02f  jmp     loc_18000D8EC
0x18000d034  mov     edx, [rbx+14h]
0x18000d037  lea     rcx, aRastapicallbac_3; "RasTapiCallback: LINE_REPLY Deallocatin"...
0x18000d03e  call    RasTapiTrace
0x18000d043  mov     ecx, [rbx+14h]; hCall
0x18000d046  cmp     [rbx+18h], r15d
0x18000d04a  jnz     short loc_18000D054
0x18000d04c  call    cs:__imp_lineDeallocateCall
0x18000d052  jmp     short loc_18000D059
0x18000d054  call    RasLineCloseCall
0x18000d059  mov     rax, [rbx]
0x18000d05c  cmp     [rax+8], rbx
0x18000d060  jnz     short loc_18000D07A
0x18000d062  mov     rcx, [rbx+8]
0x18000d066  cmp     [rcx], rbx
0x18000d069  jnz     short loc_18000D07A
0x18000d06b  mov     [rcx], rax
0x18000d06e  mov     [rax+8], rcx
0x18000d072  mov     rcx, rbx
0x18000d075  jmp     loc_18000D6B3
0x18000d07a  mov     ecx, 3
0x18000d07f  int     29h; Win8: RtlFailFast(ecx)
0x18000d081  mov     r8, rsi
0x18000d084  lea     rcx, aLineLinedevsta; "LINE_LINEDEVSTATE. param1=0x%x, line=0x"...
0x18000d08b  mov     rdx, rdi
0x18000d08e  call    RasTapiTrace
0x18000d093  cmp     rdi, 2
0x18000d097  jnz     loc_18000D8EC
0x18000d09d  test    rsi, rsi
0x18000d0a0  jz      loc_18000D8EC
0x18000d0a6  cmp     [rsi+10h], r15d
  ... truncated ...
```
