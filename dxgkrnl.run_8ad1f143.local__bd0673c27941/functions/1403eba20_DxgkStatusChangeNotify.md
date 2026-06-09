# DxgkStatusChangeNotify

- ea: `0x1403eba20`
- end: `0x1403ebed2`
- name: `DxgkStatusChangeNotify`
- size: `1202`
- prototype: ``
- caller_count: `12`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140051ce4`
- `0x140053308`
- `0x140189ee8`
- `0x14018b0a0`
- `0x1401b2cd8`
- `0x1401cfa1c`
- `0x1401d2ad8`
- `0x140218ebc`
- `0x1402c9504`
- `0x1402ca86c`
- `0x1402ce36c`
- `0x1402df910`

## callees

- `0x140012b14`
- `0x140013860`
- `0x14001b890`
- `0x14001d0e4`
- `0x140045aa4`
- `0x1403eba20`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ebb88`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ebbee`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ebcfb`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ebd62`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ebddf`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ebe63`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ebb88`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ebbee`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ebcfb`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ebd62`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ebddf`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ebe63`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403eba7d`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403eba7d`
- `ntoskrnl!PsGetProcessSessionId` at `0x1403eba8c`
- `ntoskrnl!PsGetProcessSessionId` at `0x1403eba8c`
- `ntoskrnl!RtlGetActiveConsoleId` at `0x1403ebab9`
- `ntoskrnl!RtlGetActiveConsoleId` at `0x1403ebab9`
- `ntoskrnl!PsGetServerSiloServiceSessionId` at `0x1403ebaaa`
- `ntoskrnl!PsGetServerSiloServiceSessionId` at `0x1403ebaaa`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1403eba9b`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1403eba9b`
- `watchdog!WdLogSingleEntry2` at `0x1403ebc10`
- `watchdog!WdLogSingleEntry2` at `0x1403ebd84`
- `watchdog!WdLogSingleEntry2` at `0x1403ebe85`
- `watchdog!WdLogSingleEntry2` at `0x1403ebc10`
- `watchdog!WdLogSingleEntry2` at `0x1403ebd84`
- `watchdog!WdLogSingleEntry2` at `0x1403ebe85`
- `watchdog!WdLogSingleEntry1` at `0x1403ebb50`
- `watchdog!WdLogSingleEntry1` at `0x1403ebbb6`
- `watchdog!WdLogSingleEntry1` at `0x1403ebc65`
- `watchdog!WdLogSingleEntry1` at `0x1403ebcc0`
- `watchdog!WdLogSingleEntry1` at `0x1403ebd27`
- `watchdog!WdLogSingleEntry1` at `0x1403ebda7`
- `watchdog!WdLogSingleEntry1` at `0x1403ebdff`
- `watchdog!WdLogSingleEntry1` at `0x1403ebb50`
- `watchdog!WdLogSingleEntry1` at `0x1403ebbb6`
- `watchdog!WdLogSingleEntry1` at `0x1403ebc65`
- `watchdog!WdLogSingleEntry1` at `0x1403ebcc0`
- `watchdog!WdLogSingleEntry1` at `0x1403ebd27`
- `watchdog!WdLogSingleEntry1` at `0x1403ebda7`
- `watchdog!WdLogSingleEntry1` at `0x1403ebdff`

## string_xrefs

- `0x1403ebe94`: `Failed to send MODE_CHANGE WNF notification to service session %u, status = 0x%I64x.`
- `0x1403ebe0e`: `Failed to get service session ID from server silo of current session %u.`

## pseudocode

```c
__int64 __fastcall DxgkStatusChangeNotify(int *a1, __int64 a2, __int64 a3)
{
  __int64 CurrentProcess; // rax
  __int64 CurrentServerSilo; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  int v9; // edx
  unsigned int updated; // esi
  __int64 v11; // rcx
  __int64 v12; // r8
  int v14; // eax
  __int64 v15; // rbx
  __int64 v16; // rax
  const wchar_t *v17; // r9
  int v18; // eax
  int v19; // eax
  unsigned int v20; // [rsp+50h] [rbp-20h] BYREF
  __int64 v21; // [rsp+58h] [rbp-18h]
  char v22; // [rsp+60h] [rbp-10h]
  unsigned int ProcessSessionId; // [rsp+A0h] [rbp+30h]
  unsigned int ActiveConsoleId; // [rsp+A8h] [rbp+38h]
  unsigned int ServerSiloServiceSessionId; // [rsp+B0h] [rbp+40h]

  v20 = -1;
  v21 = 0;
  if ( (qword_14015C500 & 2) != 0 )
  {
    v22 = 1;
    v20 = 2195;
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(a1, EventProfilerEnter, a3, 2195);
  }
  else
  {
    v22 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v20, 2195);
  CurrentProcess = PsGetCurrentProcess();
  ProcessSessionId = PsGetProcessSessionId(CurrentProcess);
  CurrentServerSilo = PsGetCurrentServerSilo();
  ServerSiloServiceSessionId = PsGetServerSiloServiceSessionId(CurrentServerSilo);
  ActiveConsoleId = RtlGetActiveConsoleId();
  if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10) != 0 )
    McTemplateK0qp_EtwWriteTransfer(v7, v6, v8, (unsigned int)*a1);
  v9 = *a1;
  if ( *a1 <= 7 )
  {
    if ( v9 != 7 )
    {
      if ( v9 != 1 )
      {
        if ( v9 == 2 || v9 == 3 || v9 == 4 || (unsigned int)(v9 - 5) <= 1 )
        {
LABEL_14:
          updated = 0;
          goto LABEL_15;
        }
LABEL_29:
        WdLogSingleEntry1(1);
        WdLogGlobalForLineNumber = 5073;
        DxgkLogInternalTriageEvent(
          0,
          262146,
          -1,
          (unsigned int)L"Unsupported state change notification type. (pNotification->Type = 0x%I64x)",
          *a1,
          0,
          0,
          0,
          0);
        updated = -1073741637;
        goto LABEL_15;
      }
      WdLogSingleEntry1(4);
      WdLogGlobalForLineNumber = 4990;
      updated = ZwUpdateWnfStateData(&WNF_DX_OCCLUSION_CHANGE_NOTIFICATION, 0, 0);
      if ( ProcessSessionId == ServerSiloServiceSessionId && ActiveConsoleId != -1 )
      {
        WdLogSingleEntry1(4);
        WdLogGlobalForLineNumber = 5006;
        v14 = ZwUpdateWnfStateData(&WNF_DX_OCCLUSION_CHANGE_NOTIFICATION, 0, 0);
        if ( v14 < 0 )
        {
          v15 = v14;
          WdLogSingleEntry2(2, ActiveConsoleId);
          WdLogGlobalForLineNumber = 5018;
LABEL_23:
          v16 = ActiveConsoleId;
          v17 = L"Failed to send OCCLUSION WNF notification to active session %u, status = 0x%I64x.";
LABEL_39:
          DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v17, v16, v15, 0, 0, 0);
          goto LABEL_15;
        }
      }
      goto LABEL_15;
    }
LABEL_34:
    WdLogSingleEntry1(4);
    WdLogGlobalForLineNumber = 4946;
    updated = ZwUpdateWnfStateData(&WNF_DX_MODE_CHANGE_NOTIFICATION, 0, 0);
    if ( ServerSiloServiceSessionId == -1 )
    {
      WdLogSingleEntry1(2);
      WdLogGlobalForLineNumber = 4959;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"Failed to get service session ID from server silo of current session %u.",
        ProcessSessionId,
        0,
        0,
        0,
        0);
      goto LABEL_15;
    }
    if ( ServerSiloServiceSessionId != ProcessSessionId )
    {
      v19 = ZwUpdateWnfStateData(&WNF_DX_MODE_CHANGE_NOTIFICATION, 0, 0);
      if ( v19 < 0 )
      {
        v15 = v19;
        WdLogSingleEntry2(2, ServerSiloServiceSessionId);
        v16 = ServerSiloServiceSessionId;
        v17 = L"Failed to send MODE_CHANGE WNF notification to service session %u, status = 0x%I64x.";
        WdLogGlobalForLineNumber = 4982;
        goto LABEL_39;
      }
    }
    goto LABEL_15;
  }
  if ( v9 == 8 || v9 == 9 || v9 == 10 )
    goto LABEL_14;
  if ( v9 == 11 )
    goto LABEL_34;
  if ( v9 != 12 )
    goto LABEL_29;
  WdLogSingleEntry1(4);
  WdLogGlobalForLineNumber = 5026;
  updated = ZwUpdateWnfStateData(&WNF_DX_MONITOR_CHANGE_NOTIFICATION, a1 + 4, 16);
  if ( ProcessSessionId != ActiveConsoleId && ActiveConsoleId != -1 )
  {
    WdLogSingleEntry1(4);
    WdLogGlobalForLineNumber = 5042;
    v18 = ZwUpdateWnfStateData(&WNF_DX_MONITOR_CHANGE_NOTIFICATION, a1 + 4, 16);
    if ( v18 < 0 )
    {
      v15 = v18;
      WdLogSingleEntry2(2, ActiveConsoleId);
      WdLogGlobalForLineNumber = 5054;
      goto LABEL_23;
    }
  }
LABEL_15:
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v20);
  if ( v22 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(v11, EventProfilerExit, v12, v20);
  return updated;
}

```

## disassembly

```asm
0x1403eba20  push    rbp
0x1403eba22  push    rbx
0x1403eba23  push    rsi
0x1403eba24  push    rdi
0x1403eba25  push    r14
0x1403eba27  mov     rbp, rsp
0x1403eba2a  sub     rsp, 70h
0x1403eba2e  xor     r14d, r14d
0x1403eba31  mov     [rbp+var_20], 0FFFFFFFFh
0x1403eba38  test    byte ptr cs:qword_14015C500, 2
0x1403eba3f  mov     rbx, rcx
0x1403eba42  mov     [rbp+var_18], r14
0x1403eba46  mov     edi, 893h
0x1403eba4b  jz      short loc_1403EBA6E
0x1403eba4d  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x1403eba54  mov     [rbp+var_10], 1
0x1403eba58  mov     [rbp+var_20], edi
0x1403eba5b  jz      short loc_1403EBA72
0x1403eba5d  mov     r9d, edi
0x1403eba60  lea     rdx, EventProfilerEnter
0x1403eba67  call    McTemplateK0q_EtwWriteTransfer
0x1403eba6c  jmp     short loc_1403EBA72
0x1403eba6e  mov     [rbp+var_10], r14b
0x1403eba72  mov     edx, edi
0x1403eba74  lea     rcx, [rbp+var_20]
0x1403eba78  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1403eba7d  call    cs:__imp_PsGetCurrentProcess
0x1403eba84  nop     dword ptr [rax+rax+00h]
0x1403eba89  mov     rcx, rax
0x1403eba8c  call    cs:__imp_PsGetProcessSessionId
0x1403eba93  nop     dword ptr [rax+rax+00h]
0x1403eba98  mov     [rbp+arg_0], eax
0x1403eba9b  call    cs:__imp_PsGetCurrentServerSilo
0x1403ebaa2  nop     dword ptr [rax+rax+00h]
0x1403ebaa7  mov     rcx, rax
0x1403ebaaa  call    cs:__imp_PsGetServerSiloServiceSessionId
0x1403ebab1  nop     dword ptr [rax+rax+00h]
0x1403ebab6  mov     [rbp+arg_10], eax
0x1403ebab9  call    cs:__imp_RtlGetActiveConsoleId
0x1403ebac0  nop     dword ptr [rax+rax+00h]
0x1403ebac5  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits, 10h
0x1403ebacc  mov     [rbp+arg_8], eax
0x1403ebacf  jz      short loc_1403EBAD9
0x1403ebad1  mov     r9d, [rbx]
0x1403ebad4  call    McTemplateK0qp_EtwWriteTransfer
0x1403ebad9  movsxd  rdx, dword ptr [rbx]
0x1403ebadc  cmp     edx, 7
0x1403ebadf  jg      loc_1403EBC35
0x1403ebae5  jz      loc_1403EBD9F
0x1403ebaeb  mov     ecx, edx
0x1403ebaed  sub     ecx, 1
0x1403ebaf0  jz      short loc_1403EBB48
0x1403ebaf2  sub     ecx, 1
0x1403ebaf5  jz      short loc_1403EBB0F
0x1403ebaf7  sub     ecx, 1
0x1403ebafa  jz      short loc_1403EBB0F
0x1403ebafc  sub     ecx, 1
0x1403ebaff  jz      short loc_1403EBB0F
0x1403ebb01  sub     ecx, 1
0x1403ebb04  jz      short loc_1403EBB0F
0x1403ebb06  cmp     ecx, 1
0x1403ebb09  jnz     loc_1403EBC60
0x1403ebb0f  mov     esi, r14d
0x1403ebb12  lea     rcx, [rbp+var_20]; this
0x1403ebb16  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1403ebb1b  cmp     [rbp+var_10], r14b
0x1403ebb1f  jz      short loc_1403EBB3A
0x1403ebb21  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x1403ebb28  jz      short loc_1403EBB3A
0x1403ebb2a  mov     r9d, [rbp+var_20]
0x1403ebb2e  lea     rdx, EventProfilerExit
0x1403ebb35  call    McTemplateK0q_EtwWriteTransfer
0x1403ebb3a  mov     eax, esi
0x1403ebb3c  add     rsp, 70h
0x1403ebb40  pop     r14
0x1403ebb42  pop     rdi
0x1403ebb43  pop     rsi
0x1403ebb44  pop     rbx
0x1403ebb45  pop     rbp
0x1403ebb46  retn
0x1403ebb48  mov     edx, [rbp+arg_0]
0x1403ebb4b  mov     ecx, 4
0x1403ebb50  call    cs:__imp_WdLogSingleEntry1
0x1403ebb57  nop     dword ptr [rax+rax+00h]
0x1403ebb5c  lea     rax, [rbp+arg_0]
0x1403ebb60  mov     dword ptr [rsp+70h+var_40], r14d
0x1403ebb65  mov     dword ptr [rsp+70h+var_48], r14d
0x1403ebb6a  lea     rcx, WNF_DX_OCCLUSION_CHANGE_NOTIFICATION
0x1403ebb71  xor     r9d, r9d
0x1403ebb74  mov     [rsp+70h+var_50], rax
0x1403ebb79  xor     r8d, r8d
0x1403ebb7c  mov     cs:WdLogGlobalForLineNumber, 137Eh
0x1403ebb86  xor     edx, edx
0x1403ebb88  call    cs:__imp_ZwUpdateWnfStateData
0x1403ebb8f  nop     dword ptr [rax+rax+00h]
0x1403ebb94  mov     edx, [rbp+arg_10]
0x1403ebb97  mov     esi, eax
0x1403ebb99  cmp     [rbp+arg_0], edx
0x1403ebb9c  jnz     loc_1403EBB12
0x1403ebba2  or      edi, 0FFFFFFFFh
0x1403ebba5  cmp     [rbp+arg_8], edi
0x1403ebba8  jz      loc_1403EBB12
0x1403ebbae  mov     edx, [rbp+arg_8]
0x1403ebbb1  mov     ecx, 4
0x1403ebbb6  call    cs:__imp_WdLogSingleEntry1
0x1403ebbbd  nop     dword ptr [rax+rax+00h]
0x1403ebbc2  lea     rax, [rbp+arg_8]
0x1403ebbc6  mov     dword ptr [rsp+70h+var_40], r14d
0x1403ebbcb  mov     dword ptr [rsp+70h+var_48], r14d
0x1403ebbd0  lea     rcx, WNF_DX_OCCLUSION_CHANGE_NOTIFICATION
0x1403ebbd7  xor     r9d, r9d
0x1403ebbda  mov     [rsp+70h+var_50], rax
0x1403ebbdf  xor     r8d, r8d
0x1403ebbe2  mov     cs:WdLogGlobalForLineNumber, 138Eh
0x1403ebbec  xor     edx, edx
0x1403ebbee  call    cs:__imp_ZwUpdateWnfStateData
0x1403ebbf5  nop     dword ptr [rax+rax+00h]
0x1403ebbfa  test    eax, eax
0x1403ebbfc  jns     loc_1403EBB12
0x1403ebc02  mov     edx, [rbp+arg_8]
0x1403ebc05  mov     ecx, 2
0x1403ebc0a  movsxd  rbx, eax
0x1403ebc0d  mov     r8, rbx
0x1403ebc10  call    cs:__imp_WdLogSingleEntry2
0x1403ebc17  nop     dword ptr [rax+rax+00h]
0x1403ebc1c  mov     cs:WdLogGlobalForLineNumber, 139Ah
0x1403ebc26  mov     eax, [rbp+arg_8]
0x1403ebc29  lea     r9, aFailedToSendOc; "Failed to send OCCLUSION WNF notificati"...
0x1403ebc30  jmp     loc_1403EBEA5
0x1403ebc35  mov     ecx, edx
0x1403ebc37  sub     ecx, 8
0x1403ebc3a  jz      loc_1403EBB0F
0x1403ebc40  sub     ecx, 1
0x1403ebc43  jz      loc_1403EBB0F
0x1403ebc49  sub     ecx, 1
0x1403ebc4c  jz      loc_1403EBB0F
0x1403ebc52  sub     ecx, 1
0x1403ebc55  jz      loc_1403EBD9F
0x1403ebc5b  cmp     ecx, 1
0x1403ebc5e  jz      short loc_1403EBCB8
0x1403ebc60  mov     ecx, 1
0x1403ebc65  call    cs:__imp_WdLogSingleEntry1
0x1403ebc6c  nop     dword ptr [rax+rax+00h]
0x1403ebc71  mov     [rsp+70h+var_30], r14
0x1403ebc76  lea     r9, aUnsupportedSta; "Unsupported state change notification t"...
0x1403ebc7d  mov     [rsp+70h+var_38], r14
0x1403ebc82  or      r8d, 0FFFFFFFFh
0x1403ebc86  mov     cs:WdLogGlobalForLineNumber, 13D1h
0x1403ebc90  mov     edx, 40002h
0x1403ebc95  movsxd  rax, dword ptr [rbx]
0x1403ebc98  xor     ecx, ecx
0x1403ebc9a  mov     [rsp+70h+var_40], r14
0x1403ebc9f  mov     [rsp+70h+var_48], r14
0x1403ebca4  mov     [rsp+70h+var_50], rax
0x1403ebca9  call    DxgkLogInternalTriageEvent
0x1403ebcae  mov     esi, 0C00000BBh
0x1403ebcb3  jmp     loc_1403EBB12
0x1403ebcb8  mov     edx, [rbp+arg_0]
0x1403ebcbb  mov     ecx, 4
0x1403ebcc0  call    cs:__imp_WdLogSingleEntry1
0x1403ebcc7  nop     dword ptr [rax+rax+00h]
0x1403ebccc  xor     r9d, r9d
0x1403ebccf  mov     dword ptr [rsp+70h+var_40], r14d
0x1403ebcd4  lea     rax, [rbp+arg_0]
0x1403ebcd8  mov     dword ptr [rsp+70h+var_48], r14d
0x1403ebcdd  lea     rdx, [rbx+10h]
0x1403ebce1  mov     cs:WdLogGlobalForLineNumber, 13A2h
0x1403ebceb  lea     rcx, WNF_DX_MONITOR_CHANGE_NOTIFICATION
0x1403ebcf2  mov     [rsp+70h+var_50], rax
0x1403ebcf7  lea     r8d, [r9+10h]
0x1403ebcfb  call    cs:__imp_ZwUpdateWnfStateData
0x1403ebd02  nop     dword ptr [rax+rax+00h]
0x1403ebd07  mov     esi, eax
0x1403ebd09  mov     eax, [rbp+arg_8]
0x1403ebd0c  cmp     [rbp+arg_0], eax
0x1403ebd0f  jz      loc_1403EBB12
0x1403ebd15  or      edi, 0FFFFFFFFh
0x1403ebd18  cmp     eax, edi
0x1403ebd1a  jz      loc_1403EBB12
0x1403ebd20  mov     edx, eax
0x1403ebd22  mov     ecx, 4
0x1403ebd27  call    cs:__imp_WdLogSingleEntry1
0x1403ebd2e  nop     dword ptr [rax+rax+00h]
0x1403ebd33  xor     r9d, r9d
0x1403ebd36  mov     dword ptr [rsp+70h+var_40], r14d
0x1403ebd3b  lea     rax, [rbp+arg_8]
0x1403ebd3f  mov     dword ptr [rsp+70h+var_48], r14d
0x1403ebd44  lea     rdx, [rbx+10h]
0x1403ebd48  mov     cs:WdLogGlobalForLineNumber, 13B2h
0x1403ebd52  lea     rcx, WNF_DX_MONITOR_CHANGE_NOTIFICATION
0x1403ebd59  mov     [rsp+70h+var_50], rax
0x1403ebd5e  lea     r8d, [r9+10h]
0x1403ebd62  call    cs:__imp_ZwUpdateWnfStateData
0x1403ebd69  nop     dword ptr [rax+rax+00h]
0x1403ebd6e  test    eax, eax
0x1403ebd70  jns     loc_1403EBB12
0x1403ebd76  mov     edx, [rbp+arg_8]
0x1403ebd79  mov     ecx, 2
0x1403ebd7e  movsxd  rbx, eax
0x1403ebd81  mov     r8, rbx
0x1403ebd84  call    cs:__imp_WdLogSingleEntry2
0x1403ebd8b  nop     dword ptr [rax+rax+00h]
0x1403ebd90  mov     cs:WdLogGlobalForLineNumber, 13BEh
0x1403ebd9a  jmp     loc_1403EBC26
0x1403ebd9f  mov     edx, [rbp+arg_0]
0x1403ebda2  mov     ecx, 4
0x1403ebda7  call    cs:__imp_WdLogSingleEntry1
0x1403ebdae  nop     dword ptr [rax+rax+00h]
0x1403ebdb3  lea     rax, [rbp+arg_0]
0x1403ebdb7  mov     dword ptr [rsp+70h+var_40], r14d
0x1403ebdbc  mov     dword ptr [rsp+70h+var_48], r14d
0x1403ebdc1  lea     rcx, WNF_DX_MODE_CHANGE_NOTIFICATION
0x1403ebdc8  xor     r9d, r9d
0x1403ebdcb  mov     [rsp+70h+var_50], rax
0x1403ebdd0  xor     r8d, r8d
0x1403ebdd3  mov     cs:WdLogGlobalForLineNumber, 1352h
0x1403ebddd  xor     edx, edx
0x1403ebddf  call    cs:__imp_ZwUpdateWnfStateData
0x1403ebde6  nop     dword ptr [rax+rax+00h]
0x1403ebdeb  mov     esi, eax
0x1403ebded  or      edi, 0FFFFFFFFh
0x1403ebdf0  mov     eax, [rbp+arg_10]
0x1403ebdf3  cmp     eax, edi
0x1403ebdf5  jnz     short loc_1403EBE38
0x1403ebdf7  mov     edx, [rbp+arg_0]
0x1403ebdfa  mov     ecx, 2
0x1403ebdff  call    cs:__imp_WdLogSingleEntry1
0x1403ebe06  nop     dword ptr [rax+rax+00h]
0x1403ebe0b  mov     eax, [rbp+arg_0]
0x1403ebe0e  lea     r9, aFailedToGetSer; "Failed to get service session ID from s"...
0x1403ebe15  mov     [rsp+70h+var_30], r14
0x1403ebe1a  mov     [rsp+70h+var_38], r14
0x1403ebe1f  mov     [rsp+70h+var_40], r14
0x1403ebe24  mov     [rsp+70h+var_48], r14
0x1403ebe29  mov     cs:WdLogGlobalForLineNumber, 135Fh
0x1403ebe33  jmp     loc_1403EBEB9
0x1403ebe38  cmp     eax, [rbp+arg_0]
0x1403ebe3b  jz      loc_1403EBB12
0x1403ebe41  mov     dword ptr [rsp+70h+var_40], r14d
0x1403ebe46  lea     rax, [rbp+arg_10]
0x1403ebe4a  mov     dword ptr [rsp+70h+var_48], r14d
0x1403ebe4f  lea     rcx, WNF_DX_MODE_CHANGE_NOTIFICATION
0x1403ebe56  xor     r9d, r9d
0x1403ebe59  mov     [rsp+70h+var_50], rax
0x1403ebe5e  xor     r8d, r8d
0x1403ebe61  xor     edx, edx
0x1403ebe63  call    cs:__imp_ZwUpdateWnfStateData
0x1403ebe6a  nop     dword ptr [rax+rax+00h]
0x1403ebe6f  test    eax, eax
0x1403ebe71  jns     loc_1403EBB12
0x1403ebe77  mov     edx, [rbp+arg_10]
0x1403ebe7a  mov     ecx, 2
0x1403ebe7f  movsxd  rbx, eax
0x1403ebe82  mov     r8, rbx
0x1403ebe85  call    cs:__imp_WdLogSingleEntry2
0x1403ebe8c  nop     dword ptr [rax+rax+00h]
0x1403ebe91  mov     eax, [rbp+arg_10]
0x1403ebe94  lea     r9, aFailedToSendMo; "Failed to send MODE_CHANGE WNF notifica"...
0x1403ebe9b  mov     cs:WdLogGlobalForLineNumber, 1376h
0x1403ebea5  mov     [rsp+70h+var_30], r14
0x1403ebeaa  mov     [rsp+70h+var_38], r14
0x1403ebeaf  mov     [rsp+70h+var_40], r14
0x1403ebeb4  mov     [rsp+70h+var_48], rbx
0x1403ebeb9  mov     r8d, edi
0x1403ebebc  mov     [rsp+70h+var_50], rax
0x1403ebec1  mov     edx, 40000h
0x1403ebec6  xor     ecx, ecx
0x1403ebec8  call    DxgkLogInternalTriageEvent
0x1403ebecd  jmp     loc_1403EBB12
```
