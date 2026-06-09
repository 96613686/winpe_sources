# WerpReportFaultInternal

- ea: `0x180046438`
- end: `0x180046ab8`
- name: `WerpReportFaultInternal`
- size: `1664`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006fa38`

## callees

- `0x180045c50`
- `0x180046438`
- `0x18004be98`
- `0x18004bffc`
- `0x18004e470`
- `0x18004ed20`
- `0x18007a840`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x180046540`
- `ntdll!DbgPrintEx` at `0x1800465a4`
- `ntdll!DbgPrintEx` at `0x1800466b1`
- `ntdll!DbgPrintEx` at `0x180046726`
- `ntdll!DbgPrintEx` at `0x180046821`
- `ntdll!DbgPrintEx` at `0x180046851`
- `ntdll!DbgPrintEx` at `0x1800469a5`
- `ntdll!DbgPrintEx` at `0x180046a1f`
- `ntdll!DbgPrintEx` at `0x180046540`
- `ntdll!DbgPrintEx` at `0x1800465a4`
- `ntdll!DbgPrintEx` at `0x1800466b1`
- `ntdll!DbgPrintEx` at `0x180046726`
- `ntdll!DbgPrintEx` at `0x180046821`
- `ntdll!DbgPrintEx` at `0x180046851`
- `ntdll!DbgPrintEx` at `0x1800469a5`
- `ntdll!DbgPrintEx` at `0x180046a1f`
- `ntdll!NtClose` at `0x1800469cc`
- `ntdll!NtClose` at `0x180046a30`
- `ntdll!NtClose` at `0x180046a40`
- `ntdll!NtClose` at `0x180046a4e`
- `ntdll!NtClose` at `0x180046a5c`
- `ntdll!NtClose` at `0x180046a78`
- `ntdll!NtClose` at `0x180046a88`
- `ntdll!NtClose` at `0x18007b51d`
- `ntdll!NtClose` at `0x18007b52d`
- `ntdll!NtClose` at `0x18007b53d`
- `ntdll!NtClose` at `0x18007b54d`
- `ntdll!NtClose` at `0x18007b570`
- `ntdll!NtClose` at `0x18007b580`
- `ntdll!NtClose` at `0x1800469cc`
- `ntdll!NtClose` at `0x180046a30`
- `ntdll!NtClose` at `0x180046a40`
- `ntdll!NtClose` at `0x180046a4e`
- `ntdll!NtClose` at `0x180046a5c`
- `ntdll!NtClose` at `0x180046a78`
- `ntdll!NtClose` at `0x180046a88`
- `ntdll!NtClose` at `0x18007b51d`
- `ntdll!NtClose` at `0x18007b52d`
- `ntdll!NtClose` at `0x18007b53d`
- `ntdll!NtClose` at `0x18007b54d`
- `ntdll!NtClose` at `0x18007b570`
- `ntdll!NtClose` at `0x18007b580`
- `ntdll!RtlWerpReportException` at `0x1800467ed`
- `ntdll!RtlWerpReportException` at `0x1800467ed`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800465ca`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800465ca`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18004660a`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18004660a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180046a6a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18007b55d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180046a6a`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18007b55d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004666a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800466df`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004666a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800466df`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800464ec`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046557`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800464ec`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046557`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18004695e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18004695e`

## string_xrefs

- `0x18004652f`: `WER/ReportFault/%u:%u: WARNING CreateEvent/hRecoveryEvent failed: %u.\n`
- `0x180046a0b`: `WER/ReportFault/%u:%u: ERROR CreateFileMapping failed: %u.\n`
- `0x180046596`: `WER/ReportFault/%u:%u: WARNING CreateEvent/hCompletionEvent failed: %u.\n`
- `0x180046718`: `WER/ReportFault/%u:%u: WARNING DuplicateHandle of current thread failed: %u.\n`
- `0x18004683d`: `WER/ReportFault/%u:%u: ERROR RtlWerpReportException failed: Service port busy\n`

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
0x180046438  mov     r11, rsp
0x18004643b  push    rbx
0x18004643c  push    rsi
0x18004643d  push    rdi
0x18004643e  push    r12
0x180046440  push    r13
0x180046442  push    r14
0x180046444  push    r15
0x180046446  sub     rsp, 0F0h
0x18004644d  mov     rax, cs:__security_cookie
0x180046454  xor     rax, rsp
0x180046457  mov     [rsp+128h+var_40], rax
0x18004645f  mov     r13, rcx
0x180046462  mov     [rsp+128h+var_88], rcx
0x18004646a  xorps   xmm0, xmm0
0x18004646d  xor     eax, eax
0x18004646f  movups  xmmword ptr [rsp+128h+EventAttributes.nLength], xmm0
0x180046477  mov     [r11-90h], rax
0x18004647e  xor     r12d, r12d
0x180046481  mov     r14d, r12d
0x180046484  mov     [rsp+128h+var_B0], r12
0x180046489  mov     [rsp+128h+var_C8], r12
0x18004648e  mov     [rsp+128h+var_B8], r12
0x180046493  mov     [r11-0A8h], r12
0x18004649a  mov     [rsp+128h+TargetHandle], r12
0x18004649f  mov     [rsp+128h+Handle], r12
0x1800464a4  movups  xmmword ptr [r11-68h], xmm0
0x1800464a9  movups  xmmword ptr [r11-58h], xmm0
0x1800464ae  mov     [r11-48h], rax
0x1800464b2  mov     ebx, r12d
0x1800464b5  mov     [rsp+128h+var_E0], r12
0x1800464ba  mov     [rsp+128h+var_C0], r12
0x1800464bf  mov     [rsp+128h+EventAttributes.nLength], 18h
0x1800464ca  mov     [r11-98h], r12
0x1800464d1  lea     r15d, [rax+1]
0x1800464d5  mov     [r11-90h], r15d
0x1800464dc  xor     r9d, r9d; lpName
0x1800464df  xor     r8d, r8d; bInitialState
0x1800464e2  mov     edx, r15d; bManualReset
0x1800464e5  lea     rcx, [r11-0A0h]; lpEventAttributes
0x1800464ec  call    cs:__imp_CreateEventW
0x1800464f2  mov     rdi, rax
0x1800464f5  mov     [rsp+128h+var_C8], rax
0x1800464fa  test    rax, rax
0x1800464fd  jz      short loc_180046515
0x1800464ff  mov     [rsp+128h+var_68], rax
0x180046507  mov     ebx, r15d
0x18004650a  mov     [rsp+128h+var_E8], ebx
0x18004650e  mov     esi, 96h
0x180046513  jmp     short loc_180046546
0x180046515  call    WerpGetLastError
0x18004651a  mov     r9, gs:40h
0x180046523  mov     dword ptr [rsp+128h+lpName], eax
0x180046527  mov     [rsp+128h+dwMaximumSizeLow], 351h
0x18004652f  lea     r8, aWerReportfault_13; "WER/ReportFault/%u:%u: WARNING CreateEv"...
0x180046536  mov     edx, r15d; Level
0x180046539  mov     esi, 96h
0x18004653e  mov     ecx, esi; ComponentId
0x180046540  call    cs:__imp_DbgPrintEx
0x180046546  xor     r9d, r9d; lpName
0x180046549  xor     r8d, r8d; bInitialState
0x18004654c  mov     edx, r15d; bManualReset
0x18004654f  lea     rcx, [rsp+128h+EventAttributes]; lpEventAttributes
0x180046557  call    cs:__imp_CreateEventW
0x18004655d  mov     r15, rax
0x180046560  mov     [rsp+128h+var_B8], rax
0x180046565  test    rax, rax
0x180046568  jz      short loc_18004657C
0x18004656a  mov     eax, ebx
0x18004656c  mov     [rsp+rax*8+128h+var_68], r15
0x180046574  inc     ebx
0x180046576  mov     [rsp+128h+var_E8], ebx
0x18004657a  jmp     short loc_1800465AA
0x18004657c  call    WerpGetLastError
0x180046581  mov     r9, gs:40h
0x18004658a  mov     dword ptr [rsp+128h+lpName], eax
0x18004658e  mov     [rsp+128h+dwMaximumSizeLow], 35Ch
0x180046596  lea     r8, aWerReportfault_2; "WER/ReportFault/%u:%u: WARNING CreateEv"...
0x18004659d  mov     edx, 1; Level
0x1800465a2  mov     ecx, esi; ComponentId
0x1800465a4  call    cs:__imp_DbgPrintEx
0x1800465aa  mov     [rsp+128h+lpName], r12; lpName
0x1800465af  mov     [rsp+128h+dwMaximumSizeLow], 0F8h; dwMaximumSizeLow
0x1800465b7  xor     r9d, r9d; dwMaximumSizeHigh
0x1800465ba  lea     r8d, [r9+4]; flProtect
0x1800465be  lea     rdx, [rsp+128h+EventAttributes]; lpFileMappingAttributes
0x1800465c6  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800465ca  call    cs:__imp_CreateFileMappingW
0x1800465d0  mov     r12, rax
0x1800465d3  mov     [rsp+128h+var_A8], rax
0x1800465db  test    rax, rax
0x1800465de  jz      loc_1800469F4
0x1800465e4  mov     eax, ebx
0x1800465e6  mov     [rsp+rax*8+128h+var_68], r12
0x1800465ee  inc     ebx
0x1800465f0  mov     [rsp+128h+var_E8], ebx
0x1800465f4  mov     qword ptr [rsp+128h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x1800465fd  xor     r9d, r9d; dwFileOffsetLow
0x180046600  xor     r8d, r8d; dwFileOffsetHigh
0x180046603  lea     edx, [r9+6]; dwDesiredAccess
0x180046607  mov     rcx, r12; hFileMappingObject
0x18004660a  call    cs:__imp_MapViewOfFile
0x180046610  mov     r14, rax
0x180046613  mov     [rsp+128h+var_B0], rax
0x180046618  test    rax, rax
0x18004661b  jnz     short loc_180046640
0x18004661d  call    WerpGetLastError
0x180046622  mov     ebx, eax
0x180046624  bts     ebx, 1Ch
0x180046628  mov     dword ptr [rsp+128h+lpName], ebx
0x18004662c  mov     [rsp+128h+dwMaximumSizeLow], 37Fh
0x180046634  lea     r8, aWerReportfault_19; "WER/ReportFault/%u:%u: ERROR MapViewOfF"...
0x18004663b  jmp     loc_180046A12
0x180046640  mov     [rsp+128h+dwOptions], 0; dwOptions
0x180046648  mov     dword ptr [rsp+128h+lpName], 1; bInheritHandle
0x180046650  mov     [rsp+128h+dwMaximumSizeLow], 1FFFFFh; dwDesiredAccess
0x180046658  lea     r9, [rsp+128h+TargetHandle]; lpTargetHandle
0x18004665d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180046661  mov     r8, rax; hTargetProcessHandle
0x180046664  mov     rdx, rax; hSourceHandle
0x180046667  mov     rcx, rax; hSourceProcessHandle
0x18004666a  call    cs:__imp_DuplicateHandle
0x180046670  test    eax, eax
0x180046672  jz      short loc_180046689
0x180046674  mov     rax, [rsp+128h+TargetHandle]
0x180046679  mov     [rsp+rbx*8+128h+var_68], rax
0x180046681  inc     ebx
0x180046683  mov     [rsp+128h+var_E8], ebx
0x180046687  jmp     short loc_1800466B7
0x180046689  call    WerpGetLastError
0x18004668e  mov     r9, gs:40h
0x180046697  mov     dword ptr [rsp+128h+lpName], eax
0x18004669b  mov     [rsp+128h+dwMaximumSizeLow], 399h
0x1800466a3  lea     r8, aWerReportfault_23; "WER/ReportFault/%u:%u: WARNING Duplicat"...
0x1800466aa  mov     edx, 1; Level
0x1800466af  mov     ecx, esi; ComponentId
0x1800466b1  call    cs:__imp_DbgPrintEx
0x1800466b7  mov     [rsp+128h+dwOptions], 0; dwOptions
0x1800466bf  mov     dword ptr [rsp+128h+lpName], 1; bInheritHandle
0x1800466c7  mov     [rsp+128h+dwMaximumSizeLow], 1FFFFFh; dwDesiredAccess
0x1800466cf  lea     r9, [rsp+128h+Handle]; lpTargetHandle
0x1800466d4  or      rcx, 0FFFFFFFFFFFFFFFFh; hSourceProcessHandle
0x1800466d8  mov     r8, rcx; hTargetProcessHandle
0x1800466db  lea     rdx, [rcx-1]; hSourceHandle
0x1800466df  call    cs:__imp_DuplicateHandle
0x1800466e5  test    eax, eax
0x1800466e7  jz      short loc_1800466FE
0x1800466e9  mov     rax, [rsp+128h+Handle]
0x1800466ee  mov     [rsp+rbx*8+128h+var_68], rax
0x1800466f6  inc     ebx
0x1800466f8  mov     [rsp+128h+var_E8], ebx
0x1800466fc  jmp     short loc_18004672C
0x1800466fe  call    WerpGetLastError
0x180046703  mov     r9, gs:40h
0x18004670c  mov     dword ptr [rsp+128h+lpName], eax
0x180046710  mov     [rsp+128h+dwMaximumSizeLow], 3AAh
0x180046718  lea     r8, aWerReportfault_11; "WER/ReportFault/%u:%u: WARNING Duplicat"...
0x18004671f  mov     edx, 1; Level
0x180046724  mov     ecx, esi; ComponentId
0x180046726  call    cs:__imp_DbgPrintEx
0x18004672c  mov     dword ptr [r14], 0F8h
0x180046733  mov     rax, gs:40h
0x18004673c  mov     [r14+4], eax
0x180046740  mov     rax, gs:48h
0x180046749  mov     [r14+8], eax
0x18004674d  mov     [r14+0A8h], r13
0x180046754  mov     dword ptr [r14+0B0h], 80004005h
0x18004675f  mov     rax, [rsp+128h+TargetHandle]
0x180046764  mov     [r14+0B8h], rax
0x18004676b  mov     rax, [rsp+128h+Handle]
0x180046770  mov     [r14+0C0h], rax
0x180046777  mov     [r14+0C8h], rdi
0x18004677e  mov     [r14+0D0h], r15
0x180046785  mov     qword ptr [r14+0E0h], 0
0x180046790  mov     dword ptr [r14+0E8h], 0C0000001h
0x18004679b  mov     dword ptr [r14+0ECh], 0
0x1800467a6  mov     eax, 7FFE0320h
0x1800467ab  mov     rax, [rax]
0x1800467ae  mov     ecx, ds:7FFE0004h
0x1800467b5  imul    rcx, rax
0x1800467b9  shr     rcx, 18h
0x1800467bd  mov     [r14+0F0h], ecx
0x1800467c4  mov     rcx, gs:40h
0x1800467cd  lea     rax, [rsp+128h+var_E0]
0x1800467d2  mov     [rsp+128h+lpName], rax
0x1800467d7  mov     [rsp+128h+dwMaximumSizeLow], 0
0x1800467df  mov     r9d, ebx
0x1800467e2  lea     r8, [rsp+128h+var_68]
0x1800467ea  mov     rdx, r12
0x1800467ed  call    cs:__imp_RtlWerpReportException
0x1800467f3  mov     r13d, eax
0x1800467f6  test    eax, eax
0x1800467f8  jns     loc_1800468AF
0x1800467fe  mov     r9, gs:40h
0x180046807  mov     dword ptr [rsp+128h+lpName], eax
0x18004680b  mov     [rsp+128h+dwMaximumSizeLow], 3D0h
0x180046813  lea     r8, aWerReportfault_12; "WER/ReportFault/%u:%u: WARNING RtlWerpR"...
0x18004681a  mov     edx, 1; Level
0x18004681f  mov     ecx, esi; ComponentId
0x180046821  call    cs:__imp_DbgPrintEx
0x180046827  cmp     r13d, 0C0000041h
0x18004682e  jnz     short loc_18004685C
0x180046830  mov     ebx, 1B000Bh
0x180046835  mov     [rsp+128h+dwMaximumSizeLow], 3DBh
0x18004683d  lea     r8, aWerReportfault_17; "WER/ReportFault/%u:%u: ERROR RtlWerpRep"...
0x180046844  mov     r9, gs:40h
0x18004684d  xor     edx, edx; Level
0x18004684f  mov     ecx, esi; ComponentId
0x180046851  call    cs:__imp_DbgPrintEx
0x180046857  jmp     loc_180046A26
0x18004685c  mov     rax, [rsp+128h+var_88]
0x180046864  mov     rax, [rax]
0x180046867  cmp     dword ptr [rax], 0C00000FDh
0x18004686d  jnz     short loc_180046879
0x18004686f  mov     ebx, 80070032h
0x180046874  jmp     loc_180046A26
0x180046879  lea     r9, [rsp+128h+var_E0]
0x18004687e  mov     r8d, ebx
0x180046881  lea     rdx, [rsp+128h+var_68]
0x180046889  mov     rcx, r12; void *
0x18004688c  call    StartCrashVertical
0x180046891  mov     ebx, eax
0x180046893  test    eax, eax
0x180046895  jns     short loc_1800468CD
0x180046897  mov     dword ptr [rsp+128h+lpName], eax
0x18004689b  mov     [rsp+128h+dwMaximumSizeLow], 3F3h
0x1800468a3  lea     r8, aWerReportfault; "WER/ReportFault/%u:%u: ERROR StartCrash"...
0x1800468aa  jmp     loc_180046A12
0x1800468af  mov     ebx, 1B000Bh
0x1800468b4  cmp     r13d, ebx
0x1800468b7  jnz     short loc_1800468CD
0x1800468b9  mov     [rsp+128h+dwMaximumSizeLow], 402h
0x1800468c1  lea     r8, aWerReportfault_9; "WER/ReportFault/%u:%u: ERROR RtlWerpRep"...
0x1800468c8  jmp     loc_180046844
0x1800468cd  cmp     [rsp+128h+var_E0], 0
0x1800468d3  jnz     short loc_1800468DF
0x1800468d5  mov     ebx, 1B0002h
0x1800468da  jmp     loc_180046A26
0x1800468df  xorps   xmm0, xmm0
0x1800468e2  xor     eax, eax
0x1800468e4  movups  xmmword ptr [rsp+128h+Handles], xmm0
0x1800468ec  mov     [rsp+128h+var_70], rax
0x1800468f4  mov     r13d, 0D000022Dh
0x1800468fa  mov     ebx, r13d
0x1800468fd  cmp     ebx, r13d
0x180046900  jnz     loc_1800469EB
0x180046906  mov     [rsp+128h+var_E4], 0
0x18004690e  mov     rax, [rsp+128h+var_E0]
0x180046913  mov     [rsp+128h+Handles], rax
0x18004691b  mov     ecx, 1
0x180046920  mov     [rsp+128h+var_E4], ecx
0x180046924  test    r15, r15
0x180046927  jz      short loc_18004693A
0x180046929  mov     [rsp+128h+Handles+8], r15
0x180046931  mov     ecx, 2
0x180046936  mov     [rsp+128h+var_E4], ecx
0x18004693a  test    rdi, rdi
0x18004693d  jz      short loc_18004694F
0x18004693f  mov     eax, ecx
0x180046941  mov     [rsp+rax*8+128h+Handles], rdi
0x180046949  inc     ecx; nCount
0x18004694b  mov     [rsp+128h+var_E4], ecx
0x18004694f  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180046953  xor     r8d, r8d; bWaitAll
0x180046956  lea     rdx, [rsp+128h+Handles]; lpHandles
0x18004695e  call    cs:__imp_WaitForMultipleObjects
0x180046964  mov     ecx, eax
0x180046966  test    eax, eax
0x180046968  jz      short loc_1800469B2
0x18004696a  sub     ecx, 1
0x18004696d  jz      short loc_1800469AD
0x18004696f  cmp     ecx, 1
0x180046972  jz      short loc_1800469B6
0x180046974  test    eax, eax
0x180046976  jg      short loc_18004697C
0x180046978  mov     ebx, eax
0x18004697a  jmp     short loc_180046985
0x18004697c  movzx   ebx, ax
0x18004697f  or      ebx, 80070000h
0x180046985  mov     r9, gs:40h
0x18004698e  mov     dword ptr [rsp+128h+lpName], eax
0x180046992  mov     [rsp+128h+dwMaximumSizeLow], 46Ah
0x18004699a  lea     r8, aWerReportfault_15; "WER/ReportFault/%u:%u: ERROR WaitForMul"...
0x1800469a1  xor     edx, edx; Level
0x1800469a3  mov     ecx, esi; ComponentId
0x1800469a5  call    cs:__imp_DbgPrintEx
0x1800469ab  jmp     short loc_1800469E6
0x1800469ad  test    r15, r15
0x1800469b0  jz      short loc_1800469B6
0x1800469b2  xor     ebx, ebx
0x1800469b4  jmp     short loc_1800469E6
0x1800469b6  test    rdi, rdi
0x1800469b9  jz      short loc_1800469B2
0x1800469bb  lea     rcx, [rsp+128h+var_C0]; struct WER_RECOVERY_INFO **
0x1800469c0  call    ?WerpGetRecoveryInfoForSelf@@YAJPEAPEAUWER_RECOVERY_INFO@@@Z; WerpGetRecoveryInfoForSelf(WER_RECOVERY_INFO * *)
0x1800469c5  test    eax, eax
0x1800469c7  js      short loc_1800469B2
0x1800469c9  mov     rcx, rdi; Handle
0x1800469cc  call    cs:__imp_NtClose
0x1800469d2  xor     edi, edi
  ... truncated ...
```
