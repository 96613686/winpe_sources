# PortOpenRequest

- ea: `0x180023670`
- end: `0x180023ef7`
- name: `PortOpenRequest`
- size: `2183`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180037520`

## callees

- `0x180005a20`
- `0x180005ad8`
- `0x180005bcc`
- `0x180005bfc`
- `0x180005c40`
- `0x180005cf8`
- `0x18000c37c`
- `0x18000c3c0`
- `0x18000c424`
- `0x180023670`
- `0x18003372c`
- `0x180035a08`
- `0x1800399a4`
- `0x180046fc4`
- `0x1800499f0`
- `0x18004aa34`
- `0x1800eb010`

## import_xrefs

- `msvcrt!_stricmp` at `0x180023a24`
- `msvcrt!_stricmp` at `0x180023a24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023888`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023888`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800236fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800236fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023770`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023770`

## string_xrefs

- `0x1800238ac`: `PortOpenRequest: Port is not available`
- `0x1800237fb`: `PortOpenRequest: Port is in process of being removed`
- `0x180023c4a`: `PortOpenRequest: Failed to open port`
- `0x180023937`: `PortOpenRequest: Port is already opened`

## pseudocode

```c
void __fastcall PortOpenRequest(__int64 a1, _DWORD *a2, __int64 a3)
{
  struct _LIST_ENTRY *v5; // rcx
  int v6; // edi
  unsigned int v7; // ecx
  _QWORD *v8; // rbx
  unsigned __int8 *v9; // rax
  int v10; // edx
  int v11; // r8d
  __int64 v12; // r9
  struct _LIST_ENTRY *v13; // rcx
  struct _LIST_ENTRY *v14; // rcx
  __int64 v15; // rdx
  DWORD v16; // r15d
  unsigned int v17; // esi
  struct _LIST_ENTRY *v18; // rcx
  __int64 v19; // rax
  unsigned int v20; // eax
  unsigned int v21; // eax
  int v22; // ecx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  char *v26; // rcx
  __int64 v27; // rax
  void *v28; // rbp

  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 128, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
      v5 = WPP_GLOBAL_Control;
    }
    if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v5[1].Blink) & 0x2000) != 0
      && BYTE1(v5[1].Blink) >= 6u )
    {
      WPP_SF_(v5[1].Flink, 191, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids);
    }
  }
  v6 = 0;
  EnterCriticalSection(&PcbLock);
  v7 = 0;
  if ( MaxPorts )
  {
    while ( 1 )
    {
      v8 = (_QWORD *)*((_QWORD *)Pcb + v7);
      if ( v8 && *((_DWORD *)v8 + 6) != 3 )
      {
        v9 = (unsigned __int8 *)(v8 + 1);
        do
        {
          v10 = v9[a3 + 32 - (_QWORD)(v8 + 1)];
          v11 = *v9 - v10;
          if ( v11 )
            break;
          ++v9;
        }
        while ( v10 );
        if ( !v11 )
          break;
      }
      if ( ++v7 >= MaxPorts )
        goto LABEL_20;
    }
    v6 = 1;
  }
  else
  {
    v8 = 0;
  }
LABEL_20:
  LeaveCriticalSection(&PcbLock);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    LOBYTE(v12) = v6;
    WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 192, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids, v12);
    v13 = WPP_GLOBAL_Control;
  }
  if ( !v6 || !v8 )
  {
    *(_DWORD *)a3 = 615;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_s(WPP_GLOBAL_Control[1].Flink, 129, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, a3 + 32);
        v14 = WPP_GLOBAL_Control;
      }
      if ( v14 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v14[1].Blink) & 0x2000) != 0
        && BYTE1(v14[1].Blink) >= 6u )
      {
        v15 = 130;
        goto LABEL_136;
      }
    }
    return;
  }
  if ( v13 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v13[1].Blink) & 0x2000) != 0
    && BYTE1(v13[1].Blink) >= 4u )
  {
    WPP_SF_qD(v13[1].Flink, 131, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, *v8, *((unsigned __int16 *)v8 + 22));
  }
  if ( *((_DWORD *)v8 + 6) == 2 )
  {
    TelemetryEventWriteStateChange(v8, 615, "PortOpenRequest: Port is in process of being removed");
    *(_DWORD *)a3 = 615;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 132, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, *v8);
        v14 = WPP_GLOBAL_Control;
      }
      if ( v14 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v14[1].Blink) & 0x2000) != 0
        && BYTE1(v14[1].Blink) >= 6u )
      {
        v15 = 133;
LABEL_136:
        WPP_SF_(v14[1].Flink, v15, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
        return;
      }
    }
    return;
  }
  if ( a2 && *a2 )
    v16 = a2[2];
  else
    v16 = *(_DWORD *)(a3 + 24);
  if ( v16 == GetCurrentProcessId() || (*((_BYTE *)v8 + 36) & 2) != 0 )
  {
    if ( (v8[153] & 8) != 0 )
    {
      TelemetryEventWriteStateChange(v8, 602, "PortOpenRequest: Port is already opened");
      *(_DWORD *)a3 = 602;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 136, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, *v8);
          v14 = WPP_GLOBAL_Control;
        }
        if ( v14 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v14[1].Blink) & 0x2000) != 0
          && BYTE1(v14[1].Blink) >= 6u )
        {
          v15 = 137;
          goto LABEL_136;
        }
      }
      return;
    }
    if ( *((_WORD *)v8 + 22) >= 2u )
    {
      v17 = 602;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
LABEL_106:
        TelemetryEventWriteStateChange(v8, v17, "PortOpenRequest: Failed to open port");
LABEL_124:
        *(_DWORD *)a3 = v17;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 147, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v17);
        }
        return;
      }
      if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_Dd(
          WPP_GLOBAL_Control[1].Flink,
          138,
          WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
          *((unsigned __int16 *)v8 + 22),
          602);
LABEL_101:
        v18 = WPP_GLOBAL_Control;
      }
LABEL_102:
      if ( v18 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v18[1].Blink) & 0x2000) != 0
        && BYTE1(v18[1].Blink) >= 2u )
      {
        WPP_SF_sd(v18[1].Flink, 146, (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, (_DWORD)v8 + 8, v17);
      }
      goto LABEL_106;
    }
    if ( *((_DWORD *)v8 + 6) != 1 )
    {
      v21 = *((_DWORD *)v8 + 7);
      v17 = 0;
      if ( v21 != 1 )
      {
        if ( v21 <= 5 )
        {
          v22 = 37;
          if ( _bittest(&v22, v21) )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
            {
              WPP_SF_sd(
                WPP_GLOBAL_Control[1].Flink,
                140,
                (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                (_DWORD)v8 + 8,
                *((_DWORD *)v8 + 8));
              v18 = WPP_GLOBAL_Control;
            }
            if ( *((_DWORD *)v8 + 8) == 2 && (*((_DWORD *)v8 + 7) & 0xFFFFFFFD) == 0 )
            {
              ++*((_WORD *)v8 + 22);
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
              {
                WPP_SF_qD(
                  WPP_GLOBAL_Control[1].Flink,
                  141,
                  WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
                  *v8,
                  *((unsigned __int16 *)v8 + 22));
              }
              *(_QWORD *)(a3 + 16) = *v8;
              *(_DWORD *)a3 = 0;
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
              {
                v15 = 142;
                goto LABEL_136;
              }
              return;
            }
            v17 = 602;
            if ( v18 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
              goto LABEL_106;
            if ( (HIDWORD(v18[1].Blink) & 0x2000) == 0 || BYTE1(v18[1].Blink) < 2u )
              goto LABEL_102;
            WPP_SF_d(v18[1].Flink, 143, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, 602);
            goto LABEL_101;
          }
        }
        FreeNotifierHandle((HANDLE)v8[58]);
        v8[58] = -1;
      }
      ReOpenBiplexPort(v8);
      goto LABEL_109;
    }
    if ( !_stricmp((const char *)v8[6], "rastapi") && (v19 = v8[133]) != 0 && !*(_BYTE *)(v19 + 445) )
    {
      v20 = ((__int64 (__fastcall *)(_QWORD *, _QWORD *, HANDLE, _QWORD, int))RastapiPortOpen)(
              v8 + 1,
              v8 + 27,
              hIoCompletionPort,
              *(unsigned int *)v8,
              2);
      v17 = v20;
      if ( !v20 )
        goto LABEL_109;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_78;
      }
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 139, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v20);
    }
    else
    {
      v17 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *, HANDLE, _QWORD))(v8[6] + 24LL))(
              v8 + 1,
              v8 + 27,
              hIoCompletionPort,
              *(unsigned int *)v8);
    }
    v18 = WPP_GLOBAL_Control;
LABEL_78:
    if ( v17 )
      goto LABEL_102;
LABEL_109:
    SetRasmanServiceStopControl(0);
    *((_DWORD *)v8 + 6) = 0;
    SetPortConnState(v24, v23, v8, 4);
    *((_DWORD *)v8 + 67) = 3;
    *((_DWORD *)v8 + 331) = 3;
    ++*((_WORD *)v8 + 22);
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control[1].Flink,
        144,
        WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
        *v8,
        *((unsigned __int16 *)v8 + 22));
    }
    v8[28] = v8[27];
    v25 = 0;
    *((_DWORD *)v8 + 68) = v16;
    v8[70] = 0;
    v8[71] = 0;
    v8[132] = 0;
    v8[131] = 0;
    v8[133] = 0;
    *((_DWORD *)v8 + 268) = 0;
    v8[150] = 0;
    v8[151] = 0;
    v8[152] = 0;
    v8[157] = 0;
    v8[159] = 0;
    *((_DWORD *)v8 + 66) = 0;
    v8[160] = -1;
    do
    {
      *((_DWORD *)v8 + v25 + 183) = 0;
      *((_DWORD *)v8 + v25 + 222) = 0;
      *((_DWORD *)v8 + v25++ + 144) = 0;
    }
    while ( v25 != 39 );
    *((_DWORD *)v8 + 8) = 0;
    v26 = *(char **)(a3 + 8);
    if ( (unsigned __int64)(v26 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v27 = ValidateHandleForRasman(v26, v16);
      v28 = (void *)v27;
      if ( (unsigned __int64)(v27 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        v17 = AddNotifierToList(v8 + 53, v27, 2, v16);
        if ( v17 )
        {
          FreeNotifierHandle(v28);
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 145, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v17);
          }
        }
      }
    }
    *(_QWORD *)(a3 + 16) = *v8;
    v8[136] = v8 + 135;
    v8[135] = v8 + 135;
    *((_DWORD *)v8 + 274) = 0;
    if ( !*(_DWORD *)(a3 + 28) )
      (*(void (__fastcall **)(_QWORD))(v8[6] + 32LL))(v8[27]);
    goto LABEL_124;
  }
  TelemetryEventWriteStateChange(v8, 633, "PortOpenRequest: Port is not available");
  *(_DWORD *)a3 = 633;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 134, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, *v8);
      v14 = WPP_GLOBAL_Control;
    }
    if ( v14 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v14[1].Blink) & 0x2000) != 0
      && BYTE1(v14[1].Blink) >= 6u )
    {
      v15 = 135;
      goto LABEL_136;
    }
  }
}

```

## disassembly

```asm
0x180023670  push    rbx
0x180023672  push    rbp
0x180023673  push    rsi
0x180023674  push    rdi
0x180023675  push    r12
0x180023677  push    r13
0x180023679  push    r14
0x18002367b  push    r15
0x18002367d  sub     rsp, 38h
0x180023681  mov     r14, r8
0x180023684  mov     r15, rdx
0x180023687  mov     rcx, cs:WPP_GLOBAL_Control
0x18002368e  lea     rbp, WPP_GLOBAL_Control
0x180023695  lea     rsi, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x18002369c  mov     r13d, 2000h
0x1800236a2  cmp     rcx, rbp
0x1800236a5  jz      short loc_1800236F1
0x1800236a7  test    [rcx+1Ch], r13d
0x1800236ab  jz      short loc_1800236CB
0x1800236ad  cmp     byte ptr [rcx+19h], 6
0x1800236b1  jb      short loc_1800236CB
0x1800236b3  mov     rcx, [rcx+10h]
0x1800236b7  mov     edx, 80h
0x1800236bc  mov     r8, rsi
0x1800236bf  call    WPP_SF_
0x1800236c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800236cb  cmp     rcx, rbp
0x1800236ce  jz      short loc_1800236F1
0x1800236d0  test    [rcx+1Ch], r13d
0x1800236d4  jz      short loc_1800236F1
0x1800236d6  cmp     byte ptr [rcx+19h], 6
0x1800236da  jb      short loc_1800236F1
0x1800236dc  mov     rcx, [rcx+10h]
0x1800236e0  lea     r8, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x1800236e7  mov     edx, 0BFh
0x1800236ec  call    WPP_SF_
0x1800236f1  xor     r12d, r12d
0x1800236f4  lea     rcx, PcbLock; lpCriticalSection
0x1800236fb  mov     edi, r12d
0x1800236fe  call    cs:__imp_EnterCriticalSection
0x180023705  nop     dword ptr [rax+rax+00h]
0x18002370a  mov     r10d, cs:MaxPorts
0x180023711  mov     ecx, r12d
0x180023714  test    r10d, r10d
0x180023717  jz      short loc_180023766
0x180023719  mov     r11, cs:Pcb
0x180023720  mov     eax, ecx
0x180023722  mov     rbx, [r11+rax*8]
0x180023726  test    rbx, rbx
0x180023729  jz      short loc_180023756
0x18002372b  cmp     dword ptr [rbx+18h], 3
0x18002372f  jz      short loc_180023756
0x180023731  lea     r9, [r14+20h]
0x180023735  lea     rax, [rbx+8]
0x180023739  sub     r9, rax
0x18002373c  movzx   r8d, byte ptr [rax]
0x180023740  movzx   edx, byte ptr [rax+r9]
0x180023745  sub     r8d, edx
0x180023748  jnz     short loc_180023751
0x18002374a  inc     rax
0x18002374d  test    edx, edx
0x18002374f  jnz     short loc_18002373C
0x180023751  test    r8d, r8d
0x180023754  jz      short loc_18002375F
0x180023756  inc     ecx
0x180023758  cmp     ecx, r10d
0x18002375b  jb      short loc_180023720
0x18002375d  jmp     short loc_180023769
0x18002375f  mov     edi, 1
0x180023764  jmp     short loc_180023769
0x180023766  mov     rbx, r12
0x180023769  lea     rcx, PcbLock; lpCriticalSection
0x180023770  call    cs:__imp_LeaveCriticalSection
0x180023777  nop     dword ptr [rax+rax+00h]
0x18002377c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023783  cmp     rcx, rbp
0x180023786  jz      short loc_1800237B3
0x180023788  test    [rcx+1Ch], r13d
0x18002378c  jz      short loc_1800237B3
0x18002378e  cmp     byte ptr [rcx+19h], 6
0x180023792  jb      short loc_1800237B3
0x180023794  mov     rcx, [rcx+10h]
0x180023798  lea     r8, WPP_ffb9b272f6a43a91c926496dbfc16f42_Traceguids
0x18002379f  mov     r9b, dil
0x1800237a2  mov     edx, 0C0h
0x1800237a7  call    WPP_SF_c
0x1800237ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800237b3  test    edi, edi
0x1800237b5  jz      loc_180023E85
0x1800237bb  test    rbx, rbx
0x1800237be  jz      loc_180023E85
0x1800237c4  cmp     rcx, rbp
0x1800237c7  jz      short loc_1800237F1
0x1800237c9  test    [rcx+1Ch], r13d
0x1800237cd  jz      short loc_1800237F1
0x1800237cf  cmp     byte ptr [rcx+19h], 4
0x1800237d3  jb      short loc_1800237F1
0x1800237d5  movzx   eax, word ptr [rbx+2Ch]
0x1800237d9  mov     edx, 83h
0x1800237de  mov     r9, [rbx]
0x1800237e1  mov     r8, rsi
0x1800237e4  mov     rcx, [rcx+10h]
0x1800237e8  mov     [rsp+78h+var_58], eax
0x1800237ec  call    WPP_SF_qD
0x1800237f1  mov     edi, 2
0x1800237f6  cmp     [rbx+18h], edi
0x1800237f9  jnz     short loc_180023874
0x1800237fb  lea     r8, aPortopenreques; "PortOpenRequest: Port is in process of "...
0x180023802  mov     edx, 267h
0x180023807  mov     rcx, rbx
0x18002380a  call    TelemetryEventWriteStateChange
0x18002380f  mov     dword ptr [r14], 267h
0x180023816  mov     rcx, cs:WPP_GLOBAL_Control
0x18002381d  cmp     rcx, rbp
0x180023820  jz      loc_180023EE5
0x180023826  test    [rcx+1Ch], r13d
0x18002382a  jz      short loc_18002384D
0x18002382c  cmp     [rcx+19h], dil
0x180023830  jb      short loc_18002384D
0x180023832  mov     r9, [rbx]
0x180023835  mov     edx, 84h
0x18002383a  mov     rcx, [rcx+10h]
0x18002383e  mov     r8, rsi
0x180023841  call    WPP_SF_q
0x180023846  mov     rcx, cs:WPP_GLOBAL_Control
0x18002384d  cmp     rcx, rbp
0x180023850  jz      loc_180023EE5
0x180023856  test    [rcx+1Ch], r13d
0x18002385a  jz      loc_180023EE5
0x180023860  cmp     byte ptr [rcx+19h], 6
0x180023864  jb      loc_180023EE5
0x18002386a  mov     edx, 85h
0x18002386f  jmp     loc_180023ED9
0x180023874  test    r15, r15
0x180023877  jz      short loc_180023884
0x180023879  cmp     [r15], r12d
0x18002387c  jz      short loc_180023884
0x18002387e  mov     r15d, [r15+8]
0x180023882  jmp     short loc_180023888
0x180023884  mov     r15d, [r14+18h]
0x180023888  call    cs:__imp_GetCurrentProcessId
0x18002388f  nop     dword ptr [rax+rax+00h]
0x180023894  cmp     r15d, eax
0x180023897  jz      loc_180023929
0x18002389d  test    [rbx+24h], dil
0x1800238a1  jnz     loc_180023929
0x1800238a7  mov     esi, 279h
0x1800238ac  lea     r8, aPortopenreques_2; "PortOpenRequest: Port is not available"
0x1800238b3  mov     edx, esi
0x1800238b5  mov     rcx, rbx
0x1800238b8  call    TelemetryEventWriteStateChange
0x1800238bd  mov     [r14], esi
0x1800238c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800238c7  cmp     rcx, rbp
0x1800238ca  jz      loc_180023EE5
0x1800238d0  test    [rcx+1Ch], r13d
0x1800238d4  jz      short loc_1800238FB
0x1800238d6  cmp     [rcx+19h], dil
0x1800238da  jb      short loc_1800238FB
0x1800238dc  mov     r9, [rbx]
0x1800238df  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800238e6  mov     rcx, [rcx+10h]
0x1800238ea  mov     edx, 86h
0x1800238ef  call    WPP_SF_q
0x1800238f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800238fb  cmp     rcx, rbp
0x1800238fe  jz      loc_180023EE5
0x180023904  test    [rcx+1Ch], r13d
0x180023908  jz      loc_180023EE5
0x18002390e  cmp     byte ptr [rcx+19h], 6
0x180023912  jb      loc_180023EE5
0x180023918  mov     edx, 87h
0x18002391d  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180023924  jmp     loc_180023EDC
0x180023929  test    byte ptr [rbx+4C8h], 8
0x180023930  jz      short loc_1800239B0
0x180023932  mov     ebp, 25Ah
0x180023937  lea     r8, aPortopenreques_0; "PortOpenRequest: Port is already opened"
0x18002393e  mov     edx, ebp
0x180023940  mov     rcx, rbx
0x180023943  call    TelemetryEventWriteStateChange
0x180023948  mov     [r14], ebp
0x18002394b  mov     rcx, cs:WPP_GLOBAL_Control
0x180023952  lea     r15, WPP_GLOBAL_Control
0x180023959  cmp     rcx, r15
0x18002395c  jz      loc_180023EE5
0x180023962  test    [rcx+1Ch], r13d
0x180023966  jz      short loc_180023989
0x180023968  cmp     [rcx+19h], dil
0x18002396c  jb      short loc_180023989
0x18002396e  mov     r9, [rbx]
0x180023971  mov     edx, 88h
0x180023976  mov     rcx, [rcx+10h]
0x18002397a  mov     r8, rsi
0x18002397d  call    WPP_SF_q
0x180023982  mov     rcx, cs:WPP_GLOBAL_Control
0x180023989  cmp     rcx, r15
0x18002398c  jz      loc_180023EE5
0x180023992  test    [rcx+1Ch], r13d
0x180023996  jz      loc_180023EE5
0x18002399c  cmp     byte ptr [rcx+19h], 6
0x1800239a0  jb      loc_180023EE5
0x1800239a6  mov     edx, 89h
0x1800239ab  jmp     loc_180023ED9
0x1800239b0  cmp     [rbx+2Ch], di
0x1800239b4  jb      short loc_180023A0B
0x1800239b6  mov     ebp, 25Ah
0x1800239bb  mov     esi, ebp
0x1800239bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800239c4  lea     r15, WPP_GLOBAL_Control
0x1800239cb  cmp     rcx, r15
0x1800239ce  jz      loc_180023C43
0x1800239d4  test    [rcx+1Ch], r13d
0x1800239d8  jz      loc_180023C0C
0x1800239de  cmp     [rcx+19h], dil
0x1800239e2  jb      loc_180023C0C
0x1800239e8  movzx   r9d, word ptr [rbx+2Ch]
0x1800239ed  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x1800239f4  mov     rcx, [rcx+10h]
0x1800239f8  mov     edx, 8Ah
0x1800239fd  mov     [rsp+78h+var_58], ebp
0x180023a01  call    WPP_SF_Dd
0x180023a06  jmp     loc_180023C05
0x180023a0b  mov     edx, 1
0x180023a10  cmp     [rbx+18h], edx
0x180023a13  jnz     loc_180023AE3
0x180023a19  mov     rcx, [rbx+30h]; String1
0x180023a1d  lea     rdx, String2; "rastapi"
0x180023a24  call    cs:__imp__stricmp
0x180023a2b  nop     dword ptr [rax+rax+00h]
0x180023a30  test    eax, eax
0x180023a32  jnz     short loc_180023AAB
0x180023a34  mov     rax, [rbx+428h]
0x180023a3b  test    rax, rax
0x180023a3e  jz      short loc_180023AAB
0x180023a40  cmp     [rax+1BDh], r12b
0x180023a47  jnz     short loc_180023AAB
0x180023a49  mov     r9d, [rbx]
0x180023a4c  lea     rdx, [rbx+0D8h]
0x180023a53  mov     r8, cs:hIoCompletionPort
0x180023a5a  lea     rcx, [rbx+8]
0x180023a5e  mov     rax, cs:RastapiPortOpen
0x180023a65  mov     [rsp+78h+var_58], edi
0x180023a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a6e  mov     rsi, rax
0x180023a71  test    eax, eax
0x180023a73  jz      loc_180023C7F
0x180023a79  mov     rcx, cs:WPP_GLOBAL_Control
0x180023a80  cmp     rcx, rbp
0x180023a83  jz      short loc_180023AD6
0x180023a85  test    [rcx+1Ch], r13d
0x180023a89  jz      short loc_180023AD6
0x180023a8b  cmp     [rcx+19h], dil
0x180023a8f  jb      short loc_180023AD6
0x180023a91  mov     rcx, [rcx+10h]
0x180023a95  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180023a9c  mov     edx, 8Bh
0x180023aa1  mov     r9d, eax
0x180023aa4  call    WPP_SF_d
0x180023aa9  jmp     short loc_180023ACF
0x180023aab  mov     rax, [rbx+30h]
0x180023aaf  lea     rdx, [rbx+0D8h]
0x180023ab6  mov     r9d, [rbx]
0x180023ab9  lea     rcx, [rbx+8]
0x180023abd  mov     r8, cs:hIoCompletionPort
0x180023ac4  mov     rax, [rax+18h]
0x180023ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023acd  mov     esi, eax
0x180023acf  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ad6  test    esi, esi
0x180023ad8  jnz     loc_180023C13
0x180023ade  jmp     loc_180023C7F
0x180023ae3  mov     eax, [rbx+1Ch]
0x180023ae6  mov     esi, r12d
0x180023ae9  cmp     eax, edx
0x180023aeb  jz      loc_180023C77
0x180023af1  cmp     eax, 5
0x180023af4  ja      loc_180023C60
0x180023afa  mov     ecx, 25h ; '%'
0x180023aff  bt      ecx, eax
0x180023b02  jnb     loc_180023C60
0x180023b08  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b0f  cmp     rcx, rbp
0x180023b12  jz      short loc_180023B4C
0x180023b14  test    [rcx+1Ch], r13d
0x180023b18  jz      short loc_180023B4C
0x180023b1a  cmp     byte ptr [rcx+19h], 4
0x180023b1e  jb      short loc_180023B4C
0x180023b20  mov     eax, [rbx+20h]
0x180023b23  lea     r9, [rbx+8]
0x180023b27  mov     rcx, [rcx+10h]
0x180023b2b  lea     r8, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180023b32  mov     edx, 8Ch
0x180023b37  mov     [rsp+78h+var_58], eax
0x180023b3b  call    WPP_SF_sd
0x180023b40  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b47  mov     edx, 1
0x180023b4c  cmp     [rbx+20h], edi
0x180023b4f  jnz     short loc_180023BCE
0x180023b51  test    dword ptr [rbx+1Ch], 0FFFFFFFDh
  ... truncated ...
```
