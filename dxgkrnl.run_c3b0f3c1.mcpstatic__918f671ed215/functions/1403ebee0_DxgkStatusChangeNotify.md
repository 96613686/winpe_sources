# DxgkStatusChangeNotify

- ea: `0x1403ebee0`
- end: `0x1403ec392`
- name: `DxgkStatusChangeNotify`
- size: `1202`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140051ea4`
- `0x140053558`
- `0x14018dee8`
- `0x14018f0a0`
- `0x1401b58e8`
- `0x1401d261c`
- `0x1401d56d8`
- `0x14021b50c`
- `0x1402cffac`
- `0x1402d1314`
- `0x1402d4e14`
- `0x1402e63c0`

## callees

- `0x140012cd4`
- `0x140013a20`
- `0x14001b9c0`
- `0x14001d214`
- `0x140045d04`
- `0x1403ebee0`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ec048`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ec0ae`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ec1bb`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ec222`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ec29f`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ec323`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ec048`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ec0ae`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ec1bb`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ec222`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ec29f`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1403ec323`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403ebf3d`
- `ntoskrnl!PsGetCurrentProcess` at `0x1403ebf3d`
- `ntoskrnl!PsGetProcessSessionId` at `0x1403ebf4c`
- `ntoskrnl!PsGetProcessSessionId` at `0x1403ebf4c`
- `ntoskrnl!RtlGetActiveConsoleId` at `0x1403ebf79`
- `ntoskrnl!RtlGetActiveConsoleId` at `0x1403ebf79`
- `ntoskrnl!PsGetServerSiloServiceSessionId` at `0x1403ebf6a`
- `ntoskrnl!PsGetServerSiloServiceSessionId` at `0x1403ebf6a`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1403ebf5b`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1403ebf5b`
- `watchdog!WdLogSingleEntry2` at `0x1403ec0d0`
- `watchdog!WdLogSingleEntry2` at `0x1403ec244`
- `watchdog!WdLogSingleEntry2` at `0x1403ec345`
- `watchdog!WdLogSingleEntry2` at `0x1403ec0d0`
- `watchdog!WdLogSingleEntry2` at `0x1403ec244`
- `watchdog!WdLogSingleEntry2` at `0x1403ec345`
- `watchdog!WdLogSingleEntry1` at `0x1403ec010`
- `watchdog!WdLogSingleEntry1` at `0x1403ec076`
- `watchdog!WdLogSingleEntry1` at `0x1403ec125`
- `watchdog!WdLogSingleEntry1` at `0x1403ec180`
- `watchdog!WdLogSingleEntry1` at `0x1403ec1e7`
- `watchdog!WdLogSingleEntry1` at `0x1403ec267`
- `watchdog!WdLogSingleEntry1` at `0x1403ec2bf`
- `watchdog!WdLogSingleEntry1` at `0x1403ec010`
- `watchdog!WdLogSingleEntry1` at `0x1403ec076`
- `watchdog!WdLogSingleEntry1` at `0x1403ec125`
- `watchdog!WdLogSingleEntry1` at `0x1403ec180`
- `watchdog!WdLogSingleEntry1` at `0x1403ec1e7`
- `watchdog!WdLogSingleEntry1` at `0x1403ec267`
- `watchdog!WdLogSingleEntry1` at `0x1403ec2bf`

## string_xrefs

- `0x1403ec354`: `Failed to send MODE_CHANGE WNF notification to service session %u, status = 0x%I64x.`
- `0x1403ec2ce`: `Failed to get service session ID from server silo of current session %u.`

## pseudocode

```c
__int64 __fastcall DxgkStatusChangeNotify(int *a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  __int64 CurrentProcess; // rax
  __int64 CurrentServerSilo; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  unsigned int updated; // esi
  __int64 v12; // rcx
  __int64 v13; // r8
  int v15; // eax
  __int64 v16; // rbx
  __int64 v17; // rax
  const wchar_t *v18; // r9
  int v19; // eax
  int v20; // eax
  unsigned int v21; // [rsp+50h] [rbp-20h] BYREF
  __int64 v22; // [rsp+58h] [rbp-18h]
  char v23; // [rsp+60h] [rbp-10h]
  unsigned int ProcessSessionId; // [rsp+A0h] [rbp+30h]
  unsigned int ActiveConsoleId; // [rsp+A8h] [rbp+38h]
  unsigned int ServerSiloServiceSessionId; // [rsp+B0h] [rbp+40h]

  v21 = -1;
  v22 = 0;
  if ( (qword_1401604F0 & 2) != 0 )
  {
    v23 = 1;
    v21 = 2195;
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(a1, EventProfilerEnter, a3, 2195);
  }
  else
  {
    v23 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v21, 2195);
  CurrentProcess = PsGetCurrentProcess(v4);
  ProcessSessionId = PsGetProcessSessionId(CurrentProcess);
  CurrentServerSilo = PsGetCurrentServerSilo();
  ServerSiloServiceSessionId = PsGetServerSiloServiceSessionId(CurrentServerSilo);
  ActiveConsoleId = RtlGetActiveConsoleId();
  if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10) != 0 )
    McTemplateK0qp_EtwWriteTransfer(v8, v7, v9, (unsigned int)*a1);
  v10 = *a1;
  if ( (int)v10 <= 7 )
  {
    if ( (_DWORD)v10 != 7 )
    {
      if ( (_DWORD)v10 != 1 )
      {
        if ( (_DWORD)v10 == 2 || (_DWORD)v10 == 3 || (_DWORD)v10 == 4 || (unsigned int)(v10 - 5) <= 1 )
        {
LABEL_14:
          updated = 0;
          goto LABEL_15;
        }
LABEL_29:
        WdLogSingleEntry1(1, v10);
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
      WdLogSingleEntry1(4, ProcessSessionId);
      WdLogGlobalForLineNumber = 4990;
      updated = ZwUpdateWnfStateData(&WNF_DX_OCCLUSION_CHANGE_NOTIFICATION, 0, 0);
      if ( ProcessSessionId == ServerSiloServiceSessionId && ActiveConsoleId != -1 )
      {
        WdLogSingleEntry1(4, ActiveConsoleId);
        WdLogGlobalForLineNumber = 5006;
        v15 = ZwUpdateWnfStateData(&WNF_DX_OCCLUSION_CHANGE_NOTIFICATION, 0, 0);
        if ( v15 < 0 )
        {
          v16 = v15;
          WdLogSingleEntry2(2, ActiveConsoleId, v15);
          WdLogGlobalForLineNumber = 5018;
LABEL_23:
          v17 = ActiveConsoleId;
          v18 = L"Failed to send OCCLUSION WNF notification to active session %u, status = 0x%I64x.";
LABEL_39:
          DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v18, v17, v16, 0, 0, 0);
          goto LABEL_15;
        }
      }
      goto LABEL_15;
    }
LABEL_34:
    WdLogSingleEntry1(4, ProcessSessionId);
    WdLogGlobalForLineNumber = 4946;
    updated = ZwUpdateWnfStateData(&WNF_DX_MODE_CHANGE_NOTIFICATION, 0, 0);
    if ( ServerSiloServiceSessionId == -1 )
    {
      WdLogSingleEntry1(2, ProcessSessionId);
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
      v20 = ZwUpdateWnfStateData(&WNF_DX_MODE_CHANGE_NOTIFICATION, 0, 0);
      if ( v20 < 0 )
      {
        v16 = v20;
        WdLogSingleEntry2(2, ServerSiloServiceSessionId, v20);
        v17 = ServerSiloServiceSessionId;
        v18 = L"Failed to send MODE_CHANGE WNF notification to service session %u, status = 0x%I64x.";
        WdLogGlobalForLineNumber = 4982;
        goto LABEL_39;
      }
    }
    goto LABEL_15;
  }
  if ( (_DWORD)v10 == 8 || (_DWORD)v10 == 9 || (_DWORD)v10 == 10 )
    goto LABEL_14;
  if ( (_DWORD)v10 == 11 )
    goto LABEL_34;
  if ( (_DWORD)v10 != 12 )
    goto LABEL_29;
  WdLogSingleEntry1(4, ProcessSessionId);
  WdLogGlobalForLineNumber = 5026;
  updated = ZwUpdateWnfStateData(&WNF_DX_MONITOR_CHANGE_NOTIFICATION, a1 + 4, 16);
  if ( ProcessSessionId != ActiveConsoleId && ActiveConsoleId != -1 )
  {
    WdLogSingleEntry1(4, ActiveConsoleId);
    WdLogGlobalForLineNumber = 5042;
    v19 = ZwUpdateWnfStateData(&WNF_DX_MONITOR_CHANGE_NOTIFICATION, a1 + 4, 16);
    if ( v19 < 0 )
    {
      v16 = v19;
      WdLogSingleEntry2(2, ActiveConsoleId, v19);
      WdLogGlobalForLineNumber = 5054;
      goto LABEL_23;
    }
  }
LABEL_15:
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v21);
  if ( v23 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
    McTemplateK0q_EtwWriteTransfer(v12, EventProfilerExit, v13, v21);
  return updated;
}

```

## disassembly

```asm
0x1403ebee0  push    rbp
0x1403ebee2  push    rbx
0x1403ebee3  push    rsi
0x1403ebee4  push    rdi
0x1403ebee5  push    r14
0x1403ebee7  mov     rbp, rsp
0x1403ebeea  sub     rsp, 70h
0x1403ebeee  xor     r14d, r14d
0x1403ebef1  mov     [rbp+var_20], 0FFFFFFFFh
0x1403ebef8  test    byte ptr cs:qword_1401604F0, 2
0x1403ebeff  mov     rbx, rcx
0x1403ebf02  mov     [rbp+var_18], r14
0x1403ebf06  mov     edi, 893h
0x1403ebf0b  jz      short loc_1403EBF2E
0x1403ebf0d  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x1403ebf14  mov     [rbp+var_10], 1
0x1403ebf18  mov     [rbp+var_20], edi
0x1403ebf1b  jz      short loc_1403EBF32
0x1403ebf1d  mov     r9d, edi
0x1403ebf20  lea     rdx, EventProfilerEnter
0x1403ebf27  call    McTemplateK0q_EtwWriteTransfer
0x1403ebf2c  jmp     short loc_1403EBF32
0x1403ebf2e  mov     [rbp+var_10], r14b
0x1403ebf32  mov     edx, edi
0x1403ebf34  lea     rcx, [rbp+var_20]
0x1403ebf38  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1403ebf3d  call    cs:__imp_PsGetCurrentProcess
0x1403ebf44  nop     dword ptr [rax+rax+00h]
0x1403ebf49  mov     rcx, rax
0x1403ebf4c  call    cs:__imp_PsGetProcessSessionId
0x1403ebf53  nop     dword ptr [rax+rax+00h]
0x1403ebf58  mov     [rbp+arg_0], eax
0x1403ebf5b  call    cs:__imp_PsGetCurrentServerSilo
0x1403ebf62  nop     dword ptr [rax+rax+00h]
0x1403ebf67  mov     rcx, rax
0x1403ebf6a  call    cs:__imp_PsGetServerSiloServiceSessionId
0x1403ebf71  nop     dword ptr [rax+rax+00h]
0x1403ebf76  mov     [rbp+arg_10], eax
0x1403ebf79  call    cs:__imp_RtlGetActiveConsoleId
0x1403ebf80  nop     dword ptr [rax+rax+00h]
0x1403ebf85  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits, 10h
0x1403ebf8c  mov     [rbp+arg_8], eax
0x1403ebf8f  jz      short loc_1403EBF99
0x1403ebf91  mov     r9d, [rbx]
0x1403ebf94  call    McTemplateK0qp_EtwWriteTransfer
0x1403ebf99  movsxd  rdx, dword ptr [rbx]
0x1403ebf9c  cmp     edx, 7
0x1403ebf9f  jg      loc_1403EC0F5
0x1403ebfa5  jz      loc_1403EC25F
0x1403ebfab  mov     ecx, edx
0x1403ebfad  sub     ecx, 1
0x1403ebfb0  jz      short loc_1403EC008
0x1403ebfb2  sub     ecx, 1
0x1403ebfb5  jz      short loc_1403EBFCF
0x1403ebfb7  sub     ecx, 1
0x1403ebfba  jz      short loc_1403EBFCF
0x1403ebfbc  sub     ecx, 1
0x1403ebfbf  jz      short loc_1403EBFCF
0x1403ebfc1  sub     ecx, 1
0x1403ebfc4  jz      short loc_1403EBFCF
0x1403ebfc6  cmp     ecx, 1
0x1403ebfc9  jnz     loc_1403EC120
0x1403ebfcf  mov     esi, r14d
0x1403ebfd2  lea     rcx, [rbp+var_20]; this
0x1403ebfd6  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1403ebfdb  cmp     [rbp+var_10], r14b
0x1403ebfdf  jz      short loc_1403EBFFA
0x1403ebfe1  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x1403ebfe8  jz      short loc_1403EBFFA
0x1403ebfea  mov     r9d, [rbp+var_20]
0x1403ebfee  lea     rdx, EventProfilerExit
0x1403ebff5  call    McTemplateK0q_EtwWriteTransfer
0x1403ebffa  mov     eax, esi
0x1403ebffc  add     rsp, 70h
0x1403ec000  pop     r14
0x1403ec002  pop     rdi
0x1403ec003  pop     rsi
0x1403ec004  pop     rbx
0x1403ec005  pop     rbp
0x1403ec006  retn
0x1403ec008  mov     edx, [rbp+arg_0]
0x1403ec00b  mov     ecx, 4
0x1403ec010  call    cs:__imp_WdLogSingleEntry1
0x1403ec017  nop     dword ptr [rax+rax+00h]
0x1403ec01c  lea     rax, [rbp+arg_0]
0x1403ec020  mov     dword ptr [rsp+70h+var_40], r14d
0x1403ec025  mov     dword ptr [rsp+70h+var_48], r14d
0x1403ec02a  lea     rcx, WNF_DX_OCCLUSION_CHANGE_NOTIFICATION
0x1403ec031  xor     r9d, r9d
0x1403ec034  mov     [rsp+70h+var_50], rax
0x1403ec039  xor     r8d, r8d
0x1403ec03c  mov     cs:WdLogGlobalForLineNumber, 137Eh
0x1403ec046  xor     edx, edx
0x1403ec048  call    cs:__imp_ZwUpdateWnfStateData
0x1403ec04f  nop     dword ptr [rax+rax+00h]
0x1403ec054  mov     edx, [rbp+arg_10]
0x1403ec057  mov     esi, eax
0x1403ec059  cmp     [rbp+arg_0], edx
0x1403ec05c  jnz     loc_1403EBFD2
0x1403ec062  or      edi, 0FFFFFFFFh
0x1403ec065  cmp     [rbp+arg_8], edi
0x1403ec068  jz      loc_1403EBFD2
0x1403ec06e  mov     edx, [rbp+arg_8]
0x1403ec071  mov     ecx, 4
0x1403ec076  call    cs:__imp_WdLogSingleEntry1
0x1403ec07d  nop     dword ptr [rax+rax+00h]
0x1403ec082  lea     rax, [rbp+arg_8]
0x1403ec086  mov     dword ptr [rsp+70h+var_40], r14d
0x1403ec08b  mov     dword ptr [rsp+70h+var_48], r14d
0x1403ec090  lea     rcx, WNF_DX_OCCLUSION_CHANGE_NOTIFICATION
0x1403ec097  xor     r9d, r9d
0x1403ec09a  mov     [rsp+70h+var_50], rax
0x1403ec09f  xor     r8d, r8d
0x1403ec0a2  mov     cs:WdLogGlobalForLineNumber, 138Eh
0x1403ec0ac  xor     edx, edx
0x1403ec0ae  call    cs:__imp_ZwUpdateWnfStateData
0x1403ec0b5  nop     dword ptr [rax+rax+00h]
0x1403ec0ba  test    eax, eax
0x1403ec0bc  jns     loc_1403EBFD2
0x1403ec0c2  mov     edx, [rbp+arg_8]
0x1403ec0c5  mov     ecx, 2
0x1403ec0ca  movsxd  rbx, eax
0x1403ec0cd  mov     r8, rbx
0x1403ec0d0  call    cs:__imp_WdLogSingleEntry2
0x1403ec0d7  nop     dword ptr [rax+rax+00h]
0x1403ec0dc  mov     cs:WdLogGlobalForLineNumber, 139Ah
0x1403ec0e6  mov     eax, [rbp+arg_8]
0x1403ec0e9  lea     r9, aFailedToSendOc; "Failed to send OCCLUSION WNF notificati"...
0x1403ec0f0  jmp     loc_1403EC365
0x1403ec0f5  mov     ecx, edx
0x1403ec0f7  sub     ecx, 8
0x1403ec0fa  jz      loc_1403EBFCF
0x1403ec100  sub     ecx, 1
0x1403ec103  jz      loc_1403EBFCF
0x1403ec109  sub     ecx, 1
0x1403ec10c  jz      loc_1403EBFCF
0x1403ec112  sub     ecx, 1
0x1403ec115  jz      loc_1403EC25F
0x1403ec11b  cmp     ecx, 1
0x1403ec11e  jz      short loc_1403EC178
0x1403ec120  mov     ecx, 1
0x1403ec125  call    cs:__imp_WdLogSingleEntry1
0x1403ec12c  nop     dword ptr [rax+rax+00h]
0x1403ec131  mov     [rsp+70h+var_30], r14
0x1403ec136  lea     r9, aUnsupportedSta; "Unsupported state change notification t"...
0x1403ec13d  mov     [rsp+70h+var_38], r14
0x1403ec142  or      r8d, 0FFFFFFFFh
0x1403ec146  mov     cs:WdLogGlobalForLineNumber, 13D1h
0x1403ec150  mov     edx, 40002h
0x1403ec155  movsxd  rax, dword ptr [rbx]
0x1403ec158  xor     ecx, ecx
0x1403ec15a  mov     [rsp+70h+var_40], r14
0x1403ec15f  mov     [rsp+70h+var_48], r14
0x1403ec164  mov     [rsp+70h+var_50], rax
0x1403ec169  call    DxgkLogInternalTriageEvent
0x1403ec16e  mov     esi, 0C00000BBh
0x1403ec173  jmp     loc_1403EBFD2
0x1403ec178  mov     edx, [rbp+arg_0]
0x1403ec17b  mov     ecx, 4
0x1403ec180  call    cs:__imp_WdLogSingleEntry1
0x1403ec187  nop     dword ptr [rax+rax+00h]
0x1403ec18c  xor     r9d, r9d
0x1403ec18f  mov     dword ptr [rsp+70h+var_40], r14d
0x1403ec194  lea     rax, [rbp+arg_0]
0x1403ec198  mov     dword ptr [rsp+70h+var_48], r14d
0x1403ec19d  lea     rdx, [rbx+10h]
0x1403ec1a1  mov     cs:WdLogGlobalForLineNumber, 13A2h
0x1403ec1ab  lea     rcx, WNF_DX_MONITOR_CHANGE_NOTIFICATION
0x1403ec1b2  mov     [rsp+70h+var_50], rax
0x1403ec1b7  lea     r8d, [r9+10h]
0x1403ec1bb  call    cs:__imp_ZwUpdateWnfStateData
0x1403ec1c2  nop     dword ptr [rax+rax+00h]
0x1403ec1c7  mov     esi, eax
0x1403ec1c9  mov     eax, [rbp+arg_8]
0x1403ec1cc  cmp     [rbp+arg_0], eax
0x1403ec1cf  jz      loc_1403EBFD2
0x1403ec1d5  or      edi, 0FFFFFFFFh
0x1403ec1d8  cmp     eax, edi
0x1403ec1da  jz      loc_1403EBFD2
0x1403ec1e0  mov     edx, eax
0x1403ec1e2  mov     ecx, 4
0x1403ec1e7  call    cs:__imp_WdLogSingleEntry1
0x1403ec1ee  nop     dword ptr [rax+rax+00h]
0x1403ec1f3  xor     r9d, r9d
0x1403ec1f6  mov     dword ptr [rsp+70h+var_40], r14d
0x1403ec1fb  lea     rax, [rbp+arg_8]
0x1403ec1ff  mov     dword ptr [rsp+70h+var_48], r14d
0x1403ec204  lea     rdx, [rbx+10h]
0x1403ec208  mov     cs:WdLogGlobalForLineNumber, 13B2h
0x1403ec212  lea     rcx, WNF_DX_MONITOR_CHANGE_NOTIFICATION
0x1403ec219  mov     [rsp+70h+var_50], rax
0x1403ec21e  lea     r8d, [r9+10h]
0x1403ec222  call    cs:__imp_ZwUpdateWnfStateData
0x1403ec229  nop     dword ptr [rax+rax+00h]
0x1403ec22e  test    eax, eax
0x1403ec230  jns     loc_1403EBFD2
0x1403ec236  mov     edx, [rbp+arg_8]
0x1403ec239  mov     ecx, 2
0x1403ec23e  movsxd  rbx, eax
0x1403ec241  mov     r8, rbx
0x1403ec244  call    cs:__imp_WdLogSingleEntry2
0x1403ec24b  nop     dword ptr [rax+rax+00h]
0x1403ec250  mov     cs:WdLogGlobalForLineNumber, 13BEh
0x1403ec25a  jmp     loc_1403EC0E6
0x1403ec25f  mov     edx, [rbp+arg_0]
0x1403ec262  mov     ecx, 4
0x1403ec267  call    cs:__imp_WdLogSingleEntry1
0x1403ec26e  nop     dword ptr [rax+rax+00h]
0x1403ec273  lea     rax, [rbp+arg_0]
0x1403ec277  mov     dword ptr [rsp+70h+var_40], r14d
0x1403ec27c  mov     dword ptr [rsp+70h+var_48], r14d
0x1403ec281  lea     rcx, WNF_DX_MODE_CHANGE_NOTIFICATION
0x1403ec288  xor     r9d, r9d
0x1403ec28b  mov     [rsp+70h+var_50], rax
0x1403ec290  xor     r8d, r8d
0x1403ec293  mov     cs:WdLogGlobalForLineNumber, 1352h
0x1403ec29d  xor     edx, edx
0x1403ec29f  call    cs:__imp_ZwUpdateWnfStateData
0x1403ec2a6  nop     dword ptr [rax+rax+00h]
0x1403ec2ab  mov     esi, eax
0x1403ec2ad  or      edi, 0FFFFFFFFh
0x1403ec2b0  mov     eax, [rbp+arg_10]
0x1403ec2b3  cmp     eax, edi
0x1403ec2b5  jnz     short loc_1403EC2F8
0x1403ec2b7  mov     edx, [rbp+arg_0]
0x1403ec2ba  mov     ecx, 2
0x1403ec2bf  call    cs:__imp_WdLogSingleEntry1
0x1403ec2c6  nop     dword ptr [rax+rax+00h]
0x1403ec2cb  mov     eax, [rbp+arg_0]
0x1403ec2ce  lea     r9, aFailedToGetSer; "Failed to get service session ID from s"...
0x1403ec2d5  mov     [rsp+70h+var_30], r14
0x1403ec2da  mov     [rsp+70h+var_38], r14
0x1403ec2df  mov     [rsp+70h+var_40], r14
0x1403ec2e4  mov     [rsp+70h+var_48], r14
0x1403ec2e9  mov     cs:WdLogGlobalForLineNumber, 135Fh
0x1403ec2f3  jmp     loc_1403EC379
0x1403ec2f8  cmp     eax, [rbp+arg_0]
0x1403ec2fb  jz      loc_1403EBFD2
0x1403ec301  mov     dword ptr [rsp+70h+var_40], r14d
0x1403ec306  lea     rax, [rbp+arg_10]
0x1403ec30a  mov     dword ptr [rsp+70h+var_48], r14d
0x1403ec30f  lea     rcx, WNF_DX_MODE_CHANGE_NOTIFICATION
0x1403ec316  xor     r9d, r9d
0x1403ec319  mov     [rsp+70h+var_50], rax
0x1403ec31e  xor     r8d, r8d
0x1403ec321  xor     edx, edx
0x1403ec323  call    cs:__imp_ZwUpdateWnfStateData
0x1403ec32a  nop     dword ptr [rax+rax+00h]
0x1403ec32f  test    eax, eax
0x1403ec331  jns     loc_1403EBFD2
0x1403ec337  mov     edx, [rbp+arg_10]
0x1403ec33a  mov     ecx, 2
0x1403ec33f  movsxd  rbx, eax
0x1403ec342  mov     r8, rbx
0x1403ec345  call    cs:__imp_WdLogSingleEntry2
0x1403ec34c  nop     dword ptr [rax+rax+00h]
0x1403ec351  mov     eax, [rbp+arg_10]
0x1403ec354  lea     r9, aFailedToSendMo; "Failed to send MODE_CHANGE WNF notifica"...
0x1403ec35b  mov     cs:WdLogGlobalForLineNumber, 1376h
0x1403ec365  mov     [rsp+70h+var_30], r14
0x1403ec36a  mov     [rsp+70h+var_38], r14
0x1403ec36f  mov     [rsp+70h+var_40], r14
0x1403ec374  mov     [rsp+70h+var_48], rbx
0x1403ec379  mov     r8d, edi
0x1403ec37c  mov     [rsp+70h+var_50], rax
0x1403ec381  mov     edx, 40000h
0x1403ec386  xor     ecx, ecx
0x1403ec388  call    DxgkLogInternalTriageEvent
0x1403ec38d  jmp     loc_1403EBFD2
```
