# WerpReportFaultInternal

- ea: `0x18004ac44`
- end: `0x18004b355`
- name: `WerpReportFaultInternal`
- size: `1809`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180077590`

## callees

- `0x180049924`
- `0x18004ac44`
- `0x180050558`
- `0x1800506ec`
- `0x18005216c`
- `0x180052b0c`
- `0x1800827c0`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18004ad52`
- `ntdll!DbgPrintEx` at `0x18004adc2`
- `ntdll!DbgPrintEx` at `0x18004aee7`
- `ntdll!DbgPrintEx` at `0x18004af68`
- `ntdll!DbgPrintEx` at `0x18004b06f`
- `ntdll!DbgPrintEx` at `0x18004b0a5`
- `ntdll!DbgPrintEx` at `0x18004b205`
- `ntdll!DbgPrintEx` at `0x18004b28b`
- `ntdll!DbgPrintEx` at `0x18004ad52`
- `ntdll!DbgPrintEx` at `0x18004adc2`
- `ntdll!DbgPrintEx` at `0x18004aee7`
- `ntdll!DbgPrintEx` at `0x18004af68`
- `ntdll!DbgPrintEx` at `0x18004b06f`
- `ntdll!DbgPrintEx` at `0x18004b0a5`
- `ntdll!DbgPrintEx` at `0x18004b205`
- `ntdll!DbgPrintEx` at `0x18004b28b`
- `ntdll!NtClose` at `0x18004b232`
- `ntdll!NtClose` at `0x18004b2a2`
- `ntdll!NtClose` at `0x18004b2b8`
- `ntdll!NtClose` at `0x18004b2cc`
- `ntdll!NtClose` at `0x18004b2e0`
- `ntdll!NtClose` at `0x18004b308`
- `ntdll!NtClose` at `0x18004b31e`
- `ntdll!NtClose` at `0x1800835e8`
- `ntdll!NtClose` at `0x1800835fe`
- `ntdll!NtClose` at `0x180083614`
- `ntdll!NtClose` at `0x18008362a`
- `ntdll!NtClose` at `0x180083659`
- `ntdll!NtClose` at `0x18008366f`
- `ntdll!NtClose` at `0x18004b232`
- `ntdll!NtClose` at `0x18004b2a2`
- `ntdll!NtClose` at `0x18004b2b8`
- `ntdll!NtClose` at `0x18004b2cc`
- `ntdll!NtClose` at `0x18004b2e0`
- `ntdll!NtClose` at `0x18004b308`
- `ntdll!NtClose` at `0x18004b31e`
- `ntdll!NtClose` at `0x1800835e8`
- `ntdll!NtClose` at `0x1800835fe`
- `ntdll!NtClose` at `0x180083614`
- `ntdll!NtClose` at `0x18008362a`
- `ntdll!NtClose` at `0x180083659`
- `ntdll!NtClose` at `0x18008366f`
- `ntdll!RtlWerpReportException` at `0x18004b035`
- `ntdll!RtlWerpReportException` at `0x18004b035`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18004adee`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18004adee`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18004ae34`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18004ae34`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18004b2f4`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180083640`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18004b2f4`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180083640`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004ae9a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004af1b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004ae9a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004af1b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004acf8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004ad6f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004acf8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004ad6f`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18004b1b8`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18004b1b8`

## string_xrefs

- `0x18004adb4`: `WER/ReportFault/%u:%u: WARNING CreateEvent/hCompletionEvent failed: %u.\n`
- `0x18004ad41`: `WER/ReportFault/%u:%u: WARNING CreateEvent/hRecoveryEvent failed: %u.\n`
- `0x18004b277`: `WER/ReportFault/%u:%u: ERROR CreateFileMapping failed: %u.\n`
- `0x18004af5a`: `WER/ReportFault/%u:%u: WARNING DuplicateHandle of current thread failed: %u.\n`
- `0x18004b091`: `WER/ReportFault/%u:%u: ERROR RtlWerpReportException failed: Service port busy\n`

## pseudocode

```c
__int64 __fastcall WerpReportFaultInternal(_DWORD **a1)
{
  _DWORD *v2; // r14
  int v3; // ebx
  HANDLE v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  void *v9; // rdi
  int LastError; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  HANDLE v15; // r15
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  HANDLE v21; // r12
  __int64 v22; // rbx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r9
  unsigned int v27; // ebx
  const CHAR *v28; // r8
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  int v38; // eax
  int v39; // eax
  int v40; // r13d
  const CHAR *v41; // r8
  int started; // eax
  unsigned int v43; // ebx
  DWORD v44; // ecx
  signed int v45; // eax
  DWORD dwMaximumSizeLow[2]; // [rsp+20h] [rbp-108h]
  LPCWSTR lpName; // [rsp+28h] [rbp-100h]
  HANDLE v49; // [rsp+48h] [rbp-E0h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-D8h] BYREF
  HANDLE TargetHandle; // [rsp+58h] [rbp-D0h] BYREF
  HANDLE v52; // [rsp+60h] [rbp-C8h]
  struct WER_RECOVERY_INFO *v53; // [rsp+68h] [rbp-C0h] BYREF
  HANDLE v54; // [rsp+70h] [rbp-B8h]
  _DWORD *v55; // [rsp+78h] [rbp-B0h]
  HANDLE v56; // [rsp+80h] [rbp-A8h]
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+88h] [rbp-A0h] BYREF
  _DWORD **v58; // [rsp+A0h] [rbp-88h]
  HANDLE Handles[2]; // [rsp+A8h] [rbp-80h] BYREF
  __int64 v60; // [rsp+B8h] [rbp-70h]
  _QWORD v61[5]; // [rsp+C0h] [rbp-68h] BYREF

  v58 = a1;
  *(&EventAttributes.nLength + 1) = 0;
  *(&EventAttributes.bInheritHandle + 1) = 0;
  v2 = 0;
  v55 = 0;
  v54 = 0;
  v56 = 0;
  TargetHandle = 0;
  Handle = 0;
  memset(v61, 0, sizeof(v61));
  v3 = 0;
  v49 = 0;
  v53 = 0;
  EventAttributes.nLength = 24;
  EventAttributes.lpSecurityDescriptor = 0;
  EventAttributes.bInheritHandle = 1;
  v4 = CreateEventW(&EventAttributes, 1, 0, 0);
  v9 = v4;
  v52 = v4;
  if ( v4 )
  {
    v61[0] = v4;
    v3 = 1;
  }
  else
  {
    LastError = WerpGetLastError(v6, v5, v7, v8);
    DbgPrintEx(
      0x96u,
      1u,
      "WER/ReportFault/%u:%u: WARNING CreateEvent/hRecoveryEvent failed: %u.\n",
      NtCurrentTeb()->ClientId.UniqueProcess,
      849,
      LastError);
  }
  v15 = CreateEventW(&EventAttributes, 1, 0, 0);
  v54 = v15;
  if ( v15 )
  {
    v61[v3++] = v15;
  }
  else
  {
    v16 = WerpGetLastError(v12, v11, v13, v14);
    DbgPrintEx(
      0x96u,
      1u,
      "WER/ReportFault/%u:%u: WARNING CreateEvent/hCompletionEvent failed: %u.\n",
      NtCurrentTeb()->ClientId.UniqueProcess,
      860,
      v16);
  }
  v21 = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, &EventAttributes, 4u, 0, 0xF8u, 0);
  v56 = v21;
  if ( !v21 )
  {
    v27 = WerpGetLastError(v18, v17, v19, v20) | 0x10000000;
    LODWORD(lpName) = v27;
    dwMaximumSizeLow[0] = 883;
    v28 = "WER/ReportFault/%u:%u: ERROR CreateFileMapping failed: %u.\n";
    goto LABEL_48;
  }
  v61[v3] = v21;
  v22 = (unsigned int)(v3 + 1);
  v2 = MapViewOfFile(v21, 6u, 0, 0, 0);
  v55 = v2;
  if ( v2 )
  {
    if ( DuplicateHandle(
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           &TargetHandle,
           0x1FFFFFu,
           1,
           0) )
    {
      v61[v22] = TargetHandle;
      v22 = (unsigned int)(v22 + 1);
    }
    else
    {
      v33 = WerpGetLastError(v30, v29, v31, v32);
      DbgPrintEx(
        0x96u,
        1u,
        "WER/ReportFault/%u:%u: WARNING DuplicateHandle of current process failed: %u.\n",
        NtCurrentTeb()->ClientId.UniqueProcess,
        921,
        v33);
    }
    if ( DuplicateHandle(
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           (HANDLE)0xFFFFFFFFFFFFFFFELL,
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           &Handle,
           0x1FFFFFu,
           1,
           0) )
    {
      v61[v22] = Handle;
      LODWORD(v22) = v22 + 1;
    }
    else
    {
      v38 = WerpGetLastError(v35, v34, v36, v37);
      DbgPrintEx(
        0x96u,
        1u,
        "WER/ReportFault/%u:%u: WARNING DuplicateHandle of current thread failed: %u.\n",
        NtCurrentTeb()->ClientId.UniqueProcess,
        938,
        v38);
    }
    *v2 = 248;
    v2[1] = NtCurrentTeb()->ClientId.UniqueProcess;
    v2[2] = NtCurrentTeb()->ClientId.UniqueThread;
    *((_QWORD *)v2 + 21) = a1;
    v2[44] = -2147467259;
    *((_QWORD *)v2 + 23) = TargetHandle;
    *((_QWORD *)v2 + 24) = Handle;
    *((_QWORD *)v2 + 25) = v9;
    *((_QWORD *)v2 + 26) = v15;
    *((_QWORD *)v2 + 28) = 0;
    v2[58] = -1073741823;
    v2[59] = 0;
    v2[60] = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
    v39 = RtlWerpReportException(NtCurrentTeb()->ClientId.UniqueProcess, v21, v61, (unsigned int)v22, 0, &v49);
    v40 = v39;
    if ( v39 >= 0 )
    {
      v27 = 1769483;
      if ( v39 == 1769483 )
      {
        dwMaximumSizeLow[0] = 1026;
        v41 = "WER/ReportFault/%u:%u: ERROR RtlWerpReportException failed: too many concurrent workers\n";
        goto LABEL_19;
      }
    }
    else
    {
      DbgPrintEx(
        0x96u,
        1u,
        "WER/ReportFault/%u:%u: WARNING RtlWerpReportException failed: NTSTATUS %08X.\n",
        NtCurrentTeb()->ClientId.UniqueProcess,
        976,
        v39);
      if ( v40 == -1073741759 )
      {
        v27 = 1769483;
        dwMaximumSizeLow[0] = 987;
        v41 = "WER/ReportFault/%u:%u: ERROR RtlWerpReportException failed: Service port busy\n";
LABEL_19:
        DbgPrintEx(0x96u, 0, v41, NtCurrentTeb()->ClientId.UniqueProcess, *(_QWORD *)dwMaximumSizeLow);
        goto LABEL_49;
      }
      if ( **v58 == -1073741571 )
      {
        v27 = -2147024846;
        goto LABEL_49;
      }
      started = StartCrashVertical(v21);
      v27 = started;
      if ( started < 0 )
      {
        LODWORD(lpName) = started;
        dwMaximumSizeLow[0] = 1011;
        v28 = "WER/ReportFault/%u:%u: ERROR StartCrashVertical failed: HRESULT %08X.\n";
        goto LABEL_48;
      }
    }
    if ( !v49 )
    {
      v27 = 1769474;
      goto LABEL_49;
    }
    *(_OWORD *)Handles = 0;
    v60 = 0;
    v43 = -805305811;
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          if ( v43 != -805305811 )
          {
            v27 = v2[44];
            goto LABEL_49;
          }
          Handles[0] = v49;
          v44 = 1;
          if ( v15 )
          {
            Handles[1] = v15;
            v44 = 2;
          }
          if ( v9 )
            Handles[v44++] = v9;
          v45 = WaitForMultipleObjects(v44, Handles, 0, 0xFFFFFFFF);
          if ( v45 )
            break;
LABEL_42:
          v43 = 0;
        }
        if ( v45 != 1 )
          break;
        if ( v15 )
          goto LABEL_42;
LABEL_43:
        if ( !v9 || (int)WerpGetRecoveryInfoForSelf(&v53) < 0 )
          goto LABEL_42;
        NtClose(v9);
        v9 = 0;
        v52 = 0;
        WerpInitiateRecovery(v53);
        v43 = -805305811;
      }
      if ( v45 == 2 )
        goto LABEL_43;
      if ( v45 > 0 )
        v43 = (unsigned __int16)v45 | 0x80070000;
      else
        v43 = v45;
      DbgPrintEx(
        0x96u,
        0,
        "WER/ReportFault/%u:%u: ERROR WaitForMultipleObjects returned %08X.\n",
        NtCurrentTeb()->ClientId.UniqueProcess,
        1130,
        v45);
    }
  }
  v27 = WerpGetLastError(v24, v23, v25, v26) | 0x10000000;
  LODWORD(lpName) = v27;
  dwMaximumSizeLow[0] = 895;
  v28 = "WER/ReportFault/%u:%u: ERROR MapViewOfFile failed: %u.\n";
LABEL_48:
  DbgPrintEx(0x96u, 0, v28, NtCurrentTeb()->ClientId.UniqueProcess, *(_QWORD *)dwMaximumSizeLow, lpName);
LABEL_49:
  if ( Handle )
    NtClose(Handle);
  if ( TargetHandle )
    NtClose(TargetHandle);
  if ( v15 )
    NtClose(v15);
  if ( v9 )
    NtClose(v9);
  if ( v2 )
    UnmapViewOfFile(v2);
  if ( v21 )
    NtClose(v21);
  if ( v49 )
    NtClose(v49);
  return MapReturnCode(v27);
}

```

## disassembly

```asm
0x18004ac44  mov     r11, rsp
0x18004ac47  push    rbx
0x18004ac48  push    rsi
0x18004ac49  push    rdi
0x18004ac4a  push    r12
0x18004ac4c  push    r13
0x18004ac4e  push    r14
0x18004ac50  push    r15
0x18004ac52  sub     rsp, 0F0h
0x18004ac59  mov     rax, cs:__security_cookie
0x18004ac60  xor     rax, rsp
0x18004ac63  mov     [rsp+128h+var_40], rax
0x18004ac6b  mov     r13, rcx
0x18004ac6e  mov     [rsp+128h+var_88], rcx
0x18004ac76  xorps   xmm0, xmm0
0x18004ac79  xor     eax, eax
0x18004ac7b  movups  xmmword ptr [rsp+128h+EventAttributes.nLength], xmm0
0x18004ac83  mov     [r11-90h], rax
0x18004ac8a  xor     r12d, r12d
0x18004ac8d  mov     r14d, r12d
0x18004ac90  mov     [rsp+128h+var_B0], r12
0x18004ac95  mov     [rsp+128h+var_C8], r12
0x18004ac9a  mov     [rsp+128h+var_B8], r12
0x18004ac9f  mov     [r11-0A8h], r12
0x18004aca6  mov     [rsp+128h+TargetHandle], r12
0x18004acab  mov     [rsp+128h+Handle], r12
0x18004acb0  movups  xmmword ptr [r11-68h], xmm0
0x18004acb5  movups  xmmword ptr [r11-58h], xmm0
0x18004acba  mov     [r11-48h], rax
0x18004acbe  mov     ebx, r12d
0x18004acc1  mov     [rsp+128h+var_E0], r12
0x18004acc6  mov     [rsp+128h+var_C0], r12
0x18004accb  mov     [rsp+128h+EventAttributes.nLength], 18h
0x18004acd6  mov     [r11-98h], r12
0x18004acdd  lea     r15d, [rax+1]
0x18004ace1  mov     [r11-90h], r15d
0x18004ace8  xor     r9d, r9d; lpName
0x18004aceb  xor     r8d, r8d; bInitialState
0x18004acee  mov     edx, r15d; bManualReset
0x18004acf1  lea     rcx, [r11-0A0h]; lpEventAttributes
0x18004acf8  call    cs:__imp_CreateEventW
0x18004acff  nop     dword ptr [rax+rax+00h]
0x18004ad04  mov     rdi, rax
0x18004ad07  mov     [rsp+128h+var_C8], rax
0x18004ad0c  test    rax, rax
0x18004ad0f  jz      short loc_18004AD27
0x18004ad11  mov     [rsp+128h+var_68], rax
0x18004ad19  mov     ebx, r15d
0x18004ad1c  mov     [rsp+128h+var_E8], ebx
0x18004ad20  mov     esi, 96h
0x18004ad25  jmp     short loc_18004AD5E
0x18004ad27  call    WerpGetLastError
0x18004ad2c  mov     r9, gs:40h
0x18004ad35  mov     dword ptr [rsp+128h+lpName], eax
0x18004ad39  mov     [rsp+128h+dwMaximumSizeLow], 351h
0x18004ad41  lea     r8, aWerReportfault_13; "WER/ReportFault/%u:%u: WARNING CreateEv"...
0x18004ad48  mov     edx, r15d; Level
0x18004ad4b  mov     esi, 96h
0x18004ad50  mov     ecx, esi; ComponentId
0x18004ad52  call    cs:__imp_DbgPrintEx
0x18004ad59  nop     dword ptr [rax+rax+00h]
0x18004ad5e  xor     r9d, r9d; lpName
0x18004ad61  xor     r8d, r8d; bInitialState
0x18004ad64  mov     edx, r15d; bManualReset
0x18004ad67  lea     rcx, [rsp+128h+EventAttributes]; lpEventAttributes
0x18004ad6f  call    cs:__imp_CreateEventW
0x18004ad76  nop     dword ptr [rax+rax+00h]
0x18004ad7b  mov     r15, rax
0x18004ad7e  mov     [rsp+128h+var_B8], rax
0x18004ad83  test    rax, rax
0x18004ad86  jz      short loc_18004AD9A
0x18004ad88  mov     eax, ebx
0x18004ad8a  mov     [rsp+rax*8+128h+var_68], r15
0x18004ad92  inc     ebx
0x18004ad94  mov     [rsp+128h+var_E8], ebx
0x18004ad98  jmp     short loc_18004ADCE
0x18004ad9a  call    WerpGetLastError
0x18004ad9f  mov     r9, gs:40h
0x18004ada8  mov     dword ptr [rsp+128h+lpName], eax
0x18004adac  mov     [rsp+128h+dwMaximumSizeLow], 35Ch
0x18004adb4  lea     r8, aWerReportfault_2; "WER/ReportFault/%u:%u: WARNING CreateEv"...
0x18004adbb  mov     edx, 1; Level
0x18004adc0  mov     ecx, esi; ComponentId
0x18004adc2  call    cs:__imp_DbgPrintEx
0x18004adc9  nop     dword ptr [rax+rax+00h]
0x18004adce  mov     [rsp+128h+lpName], r12; lpName
0x18004add3  mov     [rsp+128h+dwMaximumSizeLow], 0F8h; dwMaximumSizeLow
0x18004addb  xor     r9d, r9d; dwMaximumSizeHigh
0x18004adde  lea     r8d, [r9+4]; flProtect
0x18004ade2  lea     rdx, [rsp+128h+EventAttributes]; lpFileMappingAttributes
0x18004adea  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18004adee  call    cs:__imp_CreateFileMappingW
0x18004adf5  nop     dword ptr [rax+rax+00h]
0x18004adfa  mov     r12, rax
0x18004adfd  mov     [rsp+128h+var_A8], rax
0x18004ae05  test    rax, rax
0x18004ae08  jz      loc_18004B260
0x18004ae0e  mov     eax, ebx
0x18004ae10  mov     [rsp+rax*8+128h+var_68], r12
0x18004ae18  inc     ebx
0x18004ae1a  mov     [rsp+128h+var_E8], ebx
0x18004ae1e  mov     qword ptr [rsp+128h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18004ae27  xor     r9d, r9d; dwFileOffsetLow
0x18004ae2a  xor     r8d, r8d; dwFileOffsetHigh
0x18004ae2d  lea     edx, [r9+6]; dwDesiredAccess
0x18004ae31  mov     rcx, r12; hFileMappingObject
0x18004ae34  call    cs:__imp_MapViewOfFile
0x18004ae3b  nop     dword ptr [rax+rax+00h]
0x18004ae40  mov     r14, rax
0x18004ae43  mov     [rsp+128h+var_B0], rax
0x18004ae48  test    rax, rax
0x18004ae4b  jnz     short loc_18004AE70
0x18004ae4d  call    WerpGetLastError
0x18004ae52  mov     ebx, eax
0x18004ae54  bts     ebx, 1Ch
0x18004ae58  mov     dword ptr [rsp+128h+lpName], ebx
0x18004ae5c  mov     [rsp+128h+dwMaximumSizeLow], 37Fh
0x18004ae64  lea     r8, aWerReportfault_19; "WER/ReportFault/%u:%u: ERROR MapViewOfF"...
0x18004ae6b  jmp     loc_18004B27E
0x18004ae70  mov     [rsp+128h+dwOptions], 0; dwOptions
0x18004ae78  mov     dword ptr [rsp+128h+lpName], 1; bInheritHandle
0x18004ae80  mov     [rsp+128h+dwMaximumSizeLow], 1FFFFFh; dwDesiredAccess
0x18004ae88  lea     r9, [rsp+128h+TargetHandle]; lpTargetHandle
0x18004ae8d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004ae91  mov     r8, rax; hTargetProcessHandle
0x18004ae94  mov     rdx, rax; hSourceHandle
0x18004ae97  mov     rcx, rax; hSourceProcessHandle
0x18004ae9a  call    cs:__imp_DuplicateHandle
0x18004aea1  nop     dword ptr [rax+rax+00h]
0x18004aea6  test    eax, eax
0x18004aea8  jz      short loc_18004AEBF
0x18004aeaa  mov     rax, [rsp+128h+TargetHandle]
0x18004aeaf  mov     [rsp+rbx*8+128h+var_68], rax
0x18004aeb7  inc     ebx
0x18004aeb9  mov     [rsp+128h+var_E8], ebx
0x18004aebd  jmp     short loc_18004AEF3
0x18004aebf  call    WerpGetLastError
0x18004aec4  mov     r9, gs:40h
0x18004aecd  mov     dword ptr [rsp+128h+lpName], eax
0x18004aed1  mov     [rsp+128h+dwMaximumSizeLow], 399h
0x18004aed9  lea     r8, aWerReportfault_23; "WER/ReportFault/%u:%u: WARNING Duplicat"...
0x18004aee0  mov     edx, 1; Level
0x18004aee5  mov     ecx, esi; ComponentId
0x18004aee7  call    cs:__imp_DbgPrintEx
0x18004aeee  nop     dword ptr [rax+rax+00h]
0x18004aef3  mov     [rsp+128h+dwOptions], 0; dwOptions
0x18004aefb  mov     dword ptr [rsp+128h+lpName], 1; bInheritHandle
0x18004af03  mov     [rsp+128h+dwMaximumSizeLow], 1FFFFFh; dwDesiredAccess
0x18004af0b  lea     r9, [rsp+128h+Handle]; lpTargetHandle
0x18004af10  or      rcx, 0FFFFFFFFFFFFFFFFh; hSourceProcessHandle
0x18004af14  mov     r8, rcx; hTargetProcessHandle
0x18004af17  lea     rdx, [rcx-1]; hSourceHandle
0x18004af1b  call    cs:__imp_DuplicateHandle
0x18004af22  nop     dword ptr [rax+rax+00h]
0x18004af27  test    eax, eax
0x18004af29  jz      short loc_18004AF40
0x18004af2b  mov     rax, [rsp+128h+Handle]
0x18004af30  mov     [rsp+rbx*8+128h+var_68], rax
0x18004af38  inc     ebx
0x18004af3a  mov     [rsp+128h+var_E8], ebx
0x18004af3e  jmp     short loc_18004AF74
0x18004af40  call    WerpGetLastError
0x18004af45  mov     r9, gs:40h
0x18004af4e  mov     dword ptr [rsp+128h+lpName], eax
0x18004af52  mov     [rsp+128h+dwMaximumSizeLow], 3AAh
0x18004af5a  lea     r8, aWerReportfault_11; "WER/ReportFault/%u:%u: WARNING Duplicat"...
0x18004af61  mov     edx, 1; Level
0x18004af66  mov     ecx, esi; ComponentId
0x18004af68  call    cs:__imp_DbgPrintEx
0x18004af6f  nop     dword ptr [rax+rax+00h]
0x18004af74  mov     dword ptr [r14], 0F8h
0x18004af7b  mov     rax, gs:40h
0x18004af84  mov     [r14+4], eax
0x18004af88  mov     rax, gs:48h
0x18004af91  mov     [r14+8], eax
0x18004af95  mov     [r14+0A8h], r13
0x18004af9c  mov     dword ptr [r14+0B0h], 80004005h
0x18004afa7  mov     rax, [rsp+128h+TargetHandle]
0x18004afac  mov     [r14+0B8h], rax
0x18004afb3  mov     rax, [rsp+128h+Handle]
0x18004afb8  mov     [r14+0C0h], rax
0x18004afbf  mov     [r14+0C8h], rdi
0x18004afc6  mov     [r14+0D0h], r15
0x18004afcd  mov     qword ptr [r14+0E0h], 0
0x18004afd8  mov     dword ptr [r14+0E8h], 0C0000001h
0x18004afe3  mov     dword ptr [r14+0ECh], 0
0x18004afee  mov     eax, 7FFE0320h
0x18004aff3  mov     rax, [rax]
0x18004aff6  mov     ecx, ds:7FFE0004h
0x18004affd  imul    rcx, rax
0x18004b001  shr     rcx, 18h
0x18004b005  mov     [r14+0F0h], ecx
0x18004b00c  mov     rcx, gs:40h
0x18004b015  lea     rax, [rsp+128h+var_E0]
0x18004b01a  mov     [rsp+128h+lpName], rax
0x18004b01f  mov     [rsp+128h+dwMaximumSizeLow], 0
0x18004b027  mov     r9d, ebx
0x18004b02a  lea     r8, [rsp+128h+var_68]
0x18004b032  mov     rdx, r12
0x18004b035  call    cs:__imp_RtlWerpReportException
0x18004b03c  nop     dword ptr [rax+rax+00h]
0x18004b041  mov     r13d, eax
0x18004b044  test    eax, eax
0x18004b046  jns     loc_18004B109
0x18004b04c  mov     r9, gs:40h
0x18004b055  mov     dword ptr [rsp+128h+lpName], eax
0x18004b059  mov     [rsp+128h+dwMaximumSizeLow], 3D0h
0x18004b061  lea     r8, aWerReportfault_12; "WER/ReportFault/%u:%u: WARNING RtlWerpR"...
0x18004b068  mov     edx, 1; Level
0x18004b06d  mov     ecx, esi; ComponentId
0x18004b06f  call    cs:__imp_DbgPrintEx
0x18004b076  nop     dword ptr [rax+rax+00h]
0x18004b07b  cmp     r13d, 0C0000041h
0x18004b082  jnz     short loc_18004B0B6
0x18004b084  mov     ebx, 1B000Bh
0x18004b089  mov     [rsp+128h+dwMaximumSizeLow], 3DBh
0x18004b091  lea     r8, aWerReportfault_17; "WER/ReportFault/%u:%u: ERROR RtlWerpRep"...
0x18004b098  mov     r9, gs:40h
0x18004b0a1  xor     edx, edx; Level
0x18004b0a3  mov     ecx, esi; ComponentId
0x18004b0a5  call    cs:__imp_DbgPrintEx
0x18004b0ac  nop     dword ptr [rax+rax+00h]
0x18004b0b1  jmp     loc_18004B298
0x18004b0b6  mov     rax, [rsp+128h+var_88]
0x18004b0be  mov     rax, [rax]
0x18004b0c1  cmp     dword ptr [rax], 0C00000FDh
0x18004b0c7  jnz     short loc_18004B0D3
0x18004b0c9  mov     ebx, 80070032h
0x18004b0ce  jmp     loc_18004B298
0x18004b0d3  lea     r9, [rsp+128h+var_E0]
0x18004b0d8  mov     r8d, ebx
0x18004b0db  lea     rdx, [rsp+128h+var_68]
0x18004b0e3  mov     rcx, r12; void *
0x18004b0e6  call    StartCrashVertical
0x18004b0eb  mov     ebx, eax
0x18004b0ed  test    eax, eax
0x18004b0ef  jns     short loc_18004B127
0x18004b0f1  mov     dword ptr [rsp+128h+lpName], eax
0x18004b0f5  mov     [rsp+128h+dwMaximumSizeLow], 3F3h
0x18004b0fd  lea     r8, aWerReportfault; "WER/ReportFault/%u:%u: ERROR StartCrash"...
0x18004b104  jmp     loc_18004B27E
0x18004b109  mov     ebx, 1B000Bh
0x18004b10e  cmp     r13d, ebx
0x18004b111  jnz     short loc_18004B127
0x18004b113  mov     [rsp+128h+dwMaximumSizeLow], 402h
0x18004b11b  lea     r8, aWerReportfault_9; "WER/ReportFault/%u:%u: ERROR RtlWerpRep"...
0x18004b122  jmp     loc_18004B098
0x18004b127  cmp     [rsp+128h+var_E0], 0
0x18004b12d  jnz     short loc_18004B139
0x18004b12f  mov     ebx, 1B0002h
0x18004b134  jmp     loc_18004B298
0x18004b139  xorps   xmm0, xmm0
0x18004b13c  xor     eax, eax
0x18004b13e  movups  xmmword ptr [rsp+128h+Handles], xmm0
0x18004b146  mov     [rsp+128h+var_70], rax
0x18004b14e  mov     r13d, 0D000022Dh
0x18004b154  mov     ebx, r13d
0x18004b157  cmp     ebx, r13d
0x18004b15a  jnz     loc_18004B257
0x18004b160  mov     [rsp+128h+var_E4], 0
0x18004b168  mov     rax, [rsp+128h+var_E0]
0x18004b16d  mov     [rsp+128h+Handles], rax
0x18004b175  mov     ecx, 1
0x18004b17a  mov     [rsp+128h+var_E4], ecx
0x18004b17e  test    r15, r15
0x18004b181  jz      short loc_18004B194
0x18004b183  mov     [rsp+128h+Handles+8], r15
0x18004b18b  mov     ecx, 2
0x18004b190  mov     [rsp+128h+var_E4], ecx
0x18004b194  test    rdi, rdi
0x18004b197  jz      short loc_18004B1A9
0x18004b199  mov     eax, ecx
0x18004b19b  mov     [rsp+rax*8+128h+Handles], rdi
0x18004b1a3  inc     ecx; nCount
0x18004b1a5  mov     [rsp+128h+var_E4], ecx
0x18004b1a9  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18004b1ad  xor     r8d, r8d; bWaitAll
0x18004b1b0  lea     rdx, [rsp+128h+Handles]; lpHandles
0x18004b1b8  call    cs:__imp_WaitForMultipleObjects
0x18004b1bf  nop     dword ptr [rax+rax+00h]
0x18004b1c4  mov     ecx, eax
0x18004b1c6  test    eax, eax
0x18004b1c8  jz      short loc_18004B218
0x18004b1ca  sub     ecx, 1
0x18004b1cd  jz      short loc_18004B213
0x18004b1cf  cmp     ecx, 1
0x18004b1d2  jz      short loc_18004B21C
0x18004b1d4  test    eax, eax
0x18004b1d6  jg      short loc_18004B1DC
0x18004b1d8  mov     ebx, eax
0x18004b1da  jmp     short loc_18004B1E5
0x18004b1dc  movzx   ebx, ax
0x18004b1df  or      ebx, 80070000h
0x18004b1e5  mov     r9, gs:40h
0x18004b1ee  mov     dword ptr [rsp+128h+lpName], eax
0x18004b1f2  mov     [rsp+128h+dwMaximumSizeLow], 46Ah
0x18004b1fa  lea     r8, aWerReportfault_15; "WER/ReportFault/%u:%u: ERROR WaitForMul"...
0x18004b201  xor     edx, edx; Level
0x18004b203  mov     ecx, esi; ComponentId
0x18004b205  call    cs:__imp_DbgPrintEx
  ... truncated ...
```
