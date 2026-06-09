# WerpReportFaultInternal

- ea: `0x180042690`
- end: `0x180042dec`
- name: `WerpReportFaultInternal`
- size: `1884`
- prototype: `__int64 __fastcall(_DWORD **, char)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800425b0`

## callees

- `0x180002890`
- `0x1800035f3`
- `0x180003617`
- `0x180004e9f`
- `0x180004ec3`
- `0x180004ef9`
- `0x180004fa2`
- `0x18001bdb4`
- `0x18001dd7c`
- `0x180041bdc`
- `0x1800424dc`
- `0x180042690`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800428a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800428ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800428b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004292f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180042940`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800428a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800428ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800428b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004292f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180042940`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180042a39`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180042a39`
- `ntdll!DbgPrintEx` at `0x18004279d`
- `ntdll!DbgPrintEx` at `0x180042807`
- `ntdll!DbgPrintEx` at `0x180042929`
- `ntdll!DbgPrintEx` at `0x1800429b5`
- `ntdll!DbgPrintEx` at `0x180042aaa`
- `ntdll!DbgPrintEx` at `0x180042adb`
- `ntdll!DbgPrintEx` at `0x180042c39`
- `ntdll!DbgPrintEx` at `0x180042cbb`
- `ntdll!DbgPrintEx` at `0x18004279d`
- `ntdll!DbgPrintEx` at `0x180042807`
- `ntdll!DbgPrintEx` at `0x180042929`
- `ntdll!DbgPrintEx` at `0x1800429b5`
- `ntdll!DbgPrintEx` at `0x180042aaa`
- `ntdll!DbgPrintEx` at `0x180042adb`
- `ntdll!DbgPrintEx` at `0x180042c39`
- `ntdll!DbgPrintEx` at `0x180042cbb`
- `ntdll!NtClose` at `0x180042c63`
- `ntdll!NtClose` at `0x180042ccc`
- `ntdll!NtClose` at `0x180042cdc`
- `ntdll!NtClose` at `0x180042cea`
- `ntdll!NtClose` at `0x180042cf8`
- `ntdll!NtClose` at `0x180042d18`
- `ntdll!NtClose` at `0x180042d28`
- `ntdll!NtClose` at `0x18004a06f`
- `ntdll!NtClose` at `0x18004a07f`
- `ntdll!NtClose` at `0x18004a092`
- `ntdll!NtClose` at `0x18004a0a2`
- `ntdll!NtClose` at `0x18004a0c1`
- `ntdll!NtClose` at `0x18004a0d1`
- `ntdll!NtClose` at `0x180042c63`
- `ntdll!NtClose` at `0x180042ccc`
- `ntdll!NtClose` at `0x180042cdc`
- `ntdll!NtClose` at `0x180042cea`
- `ntdll!NtClose` at `0x180042cf8`
- `ntdll!NtClose` at `0x180042d18`
- `ntdll!NtClose` at `0x180042d28`
- `ntdll!NtClose` at `0x18004a06f`
- `ntdll!NtClose` at `0x18004a07f`
- `ntdll!NtClose` at `0x18004a092`
- `ntdll!NtClose` at `0x18004a0a2`
- `ntdll!NtClose` at `0x18004a0c1`
- `ntdll!NtClose` at `0x18004a0d1`
- `ntdll!RtlWerpReportException` at `0x180042a71`
- `ntdll!RtlWerpReportException` at `0x180042a71`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180042744`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800427b6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180042744`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800427b6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800428e0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004296c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800428e0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18004296c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180042bf0`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180042bf0`

## string_xrefs

- `0x18004278a`: `WER/ReportFault/%u:%u: WARNING CreateEvent/hRecoveryEvent failed: %u.\n`
- `0x1800427fa`: `WER/ReportFault/%u:%u: WARNING CreateEvent/hCompletionEvent failed: %u.\n`
- `0x180042cac`: `WER/ReportFault/%u:%u: ERROR CreateFileMapping failed: %u.\n`
- `0x1800429a6`: `WER/ReportFault/%u:%u: WARNING DuplicateHandle of current thread failed: %u.\n`
- `0x180042acc`: `WER/ReportFault/%u:%u: ERROR RtlWerpReportException failed: Service port busy\n`

## pseudocode

```c
__int64 __fastcall WerpReportFaultInternal(_DWORD **a1, char a2)
{
  int *v2; // rdi
  int v3; // esi
  HANDLE v4; // rax
  void *v5; // r14
  int LastError; // ebx
  DWORD CurrentProcessId_0; // eax
  HANDLE v8; // r13
  int v9; // ebx
  DWORD v10; // eax
  unsigned int v11; // r12d
  HANDLE v12; // rcx
  __int64 v13; // rsi
  int started; // ebx
  DWORD v15; // eax
  HANDLE CurrentProcess; // rdi
  HANDLE v17; // rbx
  HANDLE v18; // rax
  int v19; // ebx
  DWORD v20; // eax
  HANDLE v21; // rdi
  HANDLE CurrentThread_0; // rbx
  HANDLE v23; // rax
  int v24; // ebx
  DWORD v25; // eax
  DWORD v26; // eax
  HANDLE v27; // rbx
  int v28; // eax
  DWORD v29; // eax
  DWORD v30; // eax
  DWORD v31; // eax
  DWORD v32; // eax
  unsigned int v33; // ebx
  DWORD v34; // ecx
  signed int v35; // eax
  signed int v36; // esi
  DWORD v37; // eax
  DWORD v38; // eax
  DWORD dwMaximumSizeLow[2]; // [rsp+20h] [rbp-118h]
  DWORD dwMaximumSizeLowa[2]; // [rsp+20h] [rbp-118h]
  DWORD dwMaximumSizeLowb[2]; // [rsp+20h] [rbp-118h]
  DWORD dwMaximumSizeLowc[2]; // [rsp+20h] [rbp-118h]
  LPCWSTR lpName; // [rsp+28h] [rbp-110h]
  LPCWSTR lpNamea; // [rsp+28h] [rbp-110h]
  int v47; // [rsp+44h] [rbp-F4h]
  HANDLE v48; // [rsp+50h] [rbp-E8h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp-E0h] BYREF
  HANDLE TargetHandle; // [rsp+60h] [rbp-D8h] BYREF
  HANDLE v51; // [rsp+68h] [rbp-D0h]
  HANDLE v52; // [rsp+70h] [rbp-C8h]
  LPCVOID lpBaseAddress; // [rsp+78h] [rbp-C0h]
  _DWORD **v54; // [rsp+80h] [rbp-B8h]
  struct WER_RECOVERY_INFO *v55; // [rsp+88h] [rbp-B0h] BYREF
  HANDLE v56; // [rsp+90h] [rbp-A8h]
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+98h] [rbp-A0h] BYREF
  HANDLE Handles[2]; // [rsp+B0h] [rbp-88h] BYREF
  __int64 v59; // [rsp+C0h] [rbp-78h]
  _QWORD v60[5]; // [rsp+C8h] [rbp-70h] BYREF

  v54 = a1;
  *(&EventAttributes.nLength + 1) = 0;
  *(&EventAttributes.bInheritHandle + 1) = 0;
  v2 = 0;
  lpBaseAddress = 0;
  v56 = 0;
  v51 = 0;
  TargetHandle = 0;
  Handle = 0;
  memset(v60, 0, sizeof(v60));
  v3 = 0;
  v48 = 0;
  v55 = 0;
  EventAttributes.nLength = 24;
  EventAttributes.lpSecurityDescriptor = 0;
  EventAttributes.bInheritHandle = 1;
  v4 = CreateEventW(&EventAttributes, 1, 0, 0);
  v5 = v4;
  v52 = v4;
  if ( v4 )
  {
    v60[0] = v4;
    v3 = 1;
  }
  else
  {
    LastError = WerpGetLastError();
    CurrentProcessId_0 = GetCurrentProcessId_0();
    DbgPrintEx(
      0x96u,
      1u,
      "WER/ReportFault/%u:%u: WARNING CreateEvent/hRecoveryEvent failed: %u.\n",
      CurrentProcessId_0,
      849,
      LastError);
  }
  v8 = CreateEventW(&EventAttributes, 1, 0, 0);
  v56 = v8;
  if ( v8 )
  {
    v60[v3++] = v8;
  }
  else
  {
    v9 = WerpGetLastError();
    v10 = GetCurrentProcessId_0();
    DbgPrintEx(0x96u, 1u, "WER/ReportFault/%u:%u: WARNING CreateEvent/hCompletionEvent failed: %u.\n", v10, 860, v9);
  }
  v11 = 4;
  v12 = CreateFileMappingW_0((HANDLE)0xFFFFFFFFFFFFFFFFLL, &EventAttributes, 4u, 0, 0xF8u, 0);
  v51 = v12;
  if ( !v12 )
  {
    started = WerpGetLastError() | 0x10000000;
    v38 = GetCurrentProcessId_0();
    LODWORD(lpName) = started;
    dwMaximumSizeLow[0] = 883;
    DbgPrintEx(
      0x96u,
      0,
      "WER/ReportFault/%u:%u: ERROR CreateFileMapping failed: %u.\n",
      v38,
      *(_QWORD *)dwMaximumSizeLow,
      lpName);
    goto LABEL_48;
  }
  v60[v3] = v12;
  v13 = (unsigned int)(v3 + 1);
  v2 = (int *)MapViewOfFile_0(v12, 6u, 0, 0, 0);
  lpBaseAddress = v2;
  if ( !v2 )
  {
    started = WerpGetLastError() | 0x10000000;
    v15 = GetCurrentProcessId_0();
    LODWORD(lpName) = started;
    dwMaximumSizeLowa[0] = 895;
    DbgPrintEx(
      0x96u,
      0,
      "WER/ReportFault/%u:%u: ERROR MapViewOfFile failed: %u.\n",
      v15,
      *(_QWORD *)dwMaximumSizeLowa,
      lpName);
    goto LABEL_48;
  }
  CurrentProcess = GetCurrentProcess();
  v17 = GetCurrentProcess();
  v18 = GetCurrentProcess();
  if ( DuplicateHandle(v18, v17, CurrentProcess, &TargetHandle, 0x1FFFFFu, 1, 0) )
  {
    v60[v13] = TargetHandle;
    v13 = (unsigned int)(v13 + 1);
  }
  else
  {
    v19 = WerpGetLastError();
    v20 = GetCurrentProcessId_0();
    DbgPrintEx(
      0x96u,
      1u,
      "WER/ReportFault/%u:%u: WARNING DuplicateHandle of current process failed: %u.\n",
      v20,
      921,
      v19);
  }
  v21 = GetCurrentProcess();
  CurrentThread_0 = GetCurrentThread_0();
  v23 = GetCurrentProcess();
  if ( DuplicateHandle(v23, CurrentThread_0, v21, &Handle, 0x1FFFFFu, 1, 0) )
  {
    v60[v13] = Handle;
    LODWORD(v13) = v13 + 1;
  }
  else
  {
    v24 = WerpGetLastError();
    v25 = GetCurrentProcessId_0();
    DbgPrintEx(
      0x96u,
      1u,
      "WER/ReportFault/%u:%u: WARNING DuplicateHandle of current thread failed: %u.\n",
      v25,
      938,
      v24);
  }
  v2 = (int *)lpBaseAddress;
  *(_DWORD *)lpBaseAddress = 248;
  v2[1] = GetCurrentProcessId_0();
  v2[2] = GetCurrentThreadId_0();
  *((_QWORD *)v2 + 21) = v54;
  v2[44] = -2147467259;
  *((_QWORD *)v2 + 23) = TargetHandle;
  *((_QWORD *)v2 + 24) = Handle;
  *((_QWORD *)v2 + 25) = v5;
  *((_QWORD *)v2 + 26) = v8;
  *((_QWORD *)v2 + 28) = 0;
  v2[58] = -1073741823;
  v2[59] = 2 * (a2 & 2);
  v2[60] = GetTickCount();
  v26 = GetCurrentProcessId_0();
  v27 = v51;
  v28 = RtlWerpReportException(v26, v51, v60, (unsigned int)v13, 0, &v48);
  v47 = v28;
  if ( v28 >= 0 )
  {
    started = 1769483;
    if ( v28 == 1769483 )
    {
      v32 = GetCurrentProcessId_0();
      dwMaximumSizeLowb[0] = 1026;
      DbgPrintEx(
        0x96u,
        0,
        "WER/ReportFault/%u:%u: ERROR RtlWerpReportException failed: too many concurrent workers\n",
        v32,
        *(_QWORD *)dwMaximumSizeLowb);
      goto LABEL_48;
    }
    goto LABEL_26;
  }
  v29 = GetCurrentProcessId_0();
  DbgPrintEx(0x96u, 1u, "WER/ReportFault/%u:%u: WARNING RtlWerpReportException failed: NTSTATUS %08X.\n", v29, 976, v47);
  if ( v47 != -1073741759 )
  {
    if ( **v54 == -1073741571 )
    {
      started = -2147024846;
      goto LABEL_48;
    }
    started = StartCrashVertical(v27);
    if ( started < 0 )
    {
      v31 = GetCurrentProcessId_0();
      LODWORD(lpNamea) = started;
      dwMaximumSizeLowc[0] = 1011;
      DbgPrintEx(
        0x96u,
        0,
        "WER/ReportFault/%u:%u: ERROR StartCrashVertical failed: HRESULT %08X.\n",
        v31,
        *(_QWORD *)dwMaximumSizeLowc,
        lpNamea);
      goto LABEL_48;
    }
LABEL_26:
    if ( !v48 )
    {
      started = 1769474;
      goto LABEL_48;
    }
    *(_OWORD *)Handles = 0;
    v59 = 0;
    v33 = -805305811;
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          if ( v33 != -805305811 )
          {
            started = v2[44];
            goto LABEL_48;
          }
          Handles[0] = v48;
          v34 = 1;
          if ( v8 )
          {
            Handles[1] = v8;
            v34 = 2;
          }
          if ( v5 )
            Handles[v34++] = v5;
          v35 = WaitForMultipleObjects(v34, Handles, 0, 0xFFFFFFFF);
          v36 = v35;
          if ( v35 )
            break;
LABEL_42:
          v33 = 0;
        }
        if ( v35 != 1 )
          break;
        if ( v8 )
          goto LABEL_42;
LABEL_43:
        if ( !v5 || (int)WerpGetRecoveryInfoForSelf(&v55) < 0 )
          goto LABEL_42;
        NtClose(v5);
        v5 = 0;
        v52 = 0;
        WerpInitiateRecovery(v55);
        v33 = -805305811;
      }
      if ( v35 == 2 )
        goto LABEL_43;
      if ( v35 > 0 )
        v33 = (unsigned __int16)v35 | 0x80070000;
      else
        v33 = v35;
      v37 = GetCurrentProcessId_0();
      DbgPrintEx(0x96u, 0, "WER/ReportFault/%u:%u: ERROR WaitForMultipleObjects returned %08X.\n", v37, 1130, v36);
    }
  }
  started = 1769483;
  v30 = GetCurrentProcessId_0();
  dwMaximumSizeLowc[0] = 987;
  DbgPrintEx(
    0x96u,
    0,
    "WER/ReportFault/%u:%u: ERROR RtlWerpReportException failed: Service port busy\n",
    v30,
    *(_QWORD *)dwMaximumSizeLowc);
LABEL_48:
  if ( Handle )
    NtClose(Handle);
  if ( TargetHandle )
    NtClose(TargetHandle);
  if ( v8 )
    NtClose(v8);
  if ( v5 )
    NtClose(v5);
  if ( v2 )
    UnmapViewOfFile_0(v2);
  if ( v51 )
    NtClose(v51);
  if ( v48 )
    NtClose(v48);
  if ( started > -2145681408 )
  {
    switch ( started )
    {
      case -2145681407:
      case 0:
        return 0;
      case 1769472:
        return 6;
      case 1769473:
        return 0;
      case 1769474:
        return 2;
    }
    if ( (unsigned int)(started - 1769483) <= 1 )
      return 0;
  }
  else if ( started == -2145681408 || (unsigned int)(started + 2147024894) <= 1 )
  {
    return 3;
  }
  else if ( started == -2147024888
         || started == -2147024882
         || started == -2147023766
         || started == -2147023446
         || started == -2147023441
         || started == -2147023080 )
  {
    return 9;
  }
  return v11;
}

```

## disassembly

```asm
0x180042690  mov     r11, rsp
0x180042693  push    rbx
0x180042694  push    rsi
0x180042695  push    rdi
0x180042696  push    r12
0x180042698  push    r13
0x18004269a  push    r14
0x18004269c  push    r15
0x18004269e  sub     rsp, 100h
0x1800426a5  mov     rax, cs:__security_cookie
0x1800426ac  xor     rax, rsp
0x1800426af  mov     [rsp+138h+var_48], rax
0x1800426b7  mov     [rsp+138h+var_F4], edx
0x1800426bb  mov     [rsp+138h+var_B8], rcx
0x1800426c3  xorps   xmm0, xmm0
0x1800426c6  xor     eax, eax
0x1800426c8  movups  xmmword ptr [rsp+138h+EventAttributes.nLength], xmm0
0x1800426d0  mov     [r11-90h], rax
0x1800426d7  xor     ebx, ebx
0x1800426d9  mov     edi, ebx
0x1800426db  mov     [rsp+138h+lpBaseAddress], rbx
0x1800426e0  mov     [rsp+138h+var_C8], rbx
0x1800426e5  mov     [r11-0A8h], rbx
0x1800426ec  mov     [rsp+138h+var_D0], rbx
0x1800426f1  mov     [rsp+138h+TargetHandle], rbx
0x1800426f6  mov     [rsp+138h+Handle], rbx
0x1800426fb  movups  xmmword ptr [r11-70h], xmm0
0x180042700  movups  xmmword ptr [r11-60h], xmm0
0x180042705  mov     [r11-50h], rax
0x180042709  mov     esi, ebx
0x18004270b  mov     [rsp+138h+var_E8], rbx
0x180042710  mov     [r11-0B0h], rbx
0x180042717  mov     [rsp+138h+EventAttributes.nLength], 18h
0x180042722  mov     [r11-98h], rbx
0x180042729  lea     r12d, [rax+1]
0x18004272d  mov     [r11-90h], r12d
0x180042734  xor     r9d, r9d; lpName
0x180042737  xor     r8d, r8d; bInitialState
0x18004273a  mov     edx, r12d; bManualReset
0x18004273d  lea     rcx, [r11-0A0h]; lpEventAttributes
0x180042744  call    cs:__imp_CreateEventW
0x18004274a  mov     r14, rax
0x18004274d  mov     [rsp+138h+var_C8], rax
0x180042752  test    rax, rax
0x180042755  jz      short loc_18004276F
0x180042757  mov     [rsp+138h+var_70], rax
0x18004275f  mov     esi, r12d
0x180042762  mov     [rsp+138h+var_F8], r12d
0x180042767  mov     r15d, 96h
0x18004276d  jmp     short loc_1800427A5
0x18004276f  call    WerpGetLastError
0x180042774  mov     ebx, eax
0x180042776  call    GetCurrentProcessId_0
0x18004277b  mov     dword ptr [rsp+138h+lpName], ebx
0x18004277f  mov     [rsp+138h+dwMaximumSizeLow], 351h
0x180042787  mov     r9d, eax
0x18004278a  lea     r8, aWerReportfault_13; "WER/ReportFault/%u:%u: WARNING CreateEv"...
0x180042791  mov     edx, r12d; Level
0x180042794  mov     r15d, 96h
0x18004279a  mov     ecx, r15d; ComponentId
0x18004279d  call    cs:__imp_DbgPrintEx
0x1800427a3  xor     ebx, ebx
0x1800427a5  xor     r9d, r9d; lpName
0x1800427a8  xor     r8d, r8d; bInitialState
0x1800427ab  mov     edx, r12d; bManualReset
0x1800427ae  lea     rcx, [rsp+138h+EventAttributes]; lpEventAttributes
0x1800427b6  call    cs:__imp_CreateEventW
0x1800427bc  mov     r13, rax
0x1800427bf  mov     [rsp+138h+var_A8], rax
0x1800427c7  test    rax, rax
0x1800427ca  jz      short loc_1800427DF
0x1800427cc  mov     eax, esi
0x1800427ce  mov     [rsp+rax*8+138h+var_70], r13
0x1800427d6  add     esi, r12d
0x1800427d9  mov     [rsp+138h+var_F8], esi
0x1800427dd  jmp     short loc_18004280F
0x1800427df  call    WerpGetLastError
0x1800427e4  mov     ebx, eax
0x1800427e6  call    GetCurrentProcessId_0
0x1800427eb  mov     dword ptr [rsp+138h+lpName], ebx
0x1800427ef  mov     [rsp+138h+dwMaximumSizeLow], 35Ch
0x1800427f7  mov     r9d, eax
0x1800427fa  lea     r8, aWerReportfault_2; "WER/ReportFault/%u:%u: WARNING CreateEv"...
0x180042801  mov     edx, r12d; Level
0x180042804  mov     ecx, r15d; ComponentId
0x180042807  call    cs:__imp_DbgPrintEx
0x18004280d  xor     ebx, ebx
0x18004280f  mov     [rsp+138h+lpName], rbx; lpName
0x180042814  mov     [rsp+138h+dwMaximumSizeLow], 0F8h; dwMaximumSizeLow
0x18004281c  xor     r9d, r9d; dwMaximumSizeHigh
0x18004281f  lea     r12d, [r9+4]
0x180042823  mov     r8d, r12d; flProtect
0x180042826  lea     rdx, [rsp+138h+EventAttributes]; lpFileMappingAttributes
0x18004282e  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180042832  call    CreateFileMappingW_0
0x180042837  mov     rcx, rax; hFileMappingObject
0x18004283a  mov     [rsp+138h+var_D0], rax
0x18004283f  test    rax, rax
0x180042842  jz      loc_180042C90
0x180042848  mov     eax, esi
0x18004284a  mov     [rsp+rax*8+138h+var_70], rcx
0x180042852  inc     esi
0x180042854  mov     [rsp+138h+var_F8], esi
0x180042858  mov     qword ptr [rsp+138h+dwMaximumSizeLow], rbx; dwNumberOfBytesToMap
0x18004285d  xor     r9d, r9d; dwFileOffsetLow
0x180042860  xor     r8d, r8d; dwFileOffsetHigh
0x180042863  lea     edx, [r12+2]; dwDesiredAccess
0x180042868  call    MapViewOfFile_0
0x18004286d  mov     rdi, rax
0x180042870  mov     [rsp+138h+lpBaseAddress], rax
0x180042875  test    rax, rax
0x180042878  jnz     short loc_1800428A2
0x18004287a  call    WerpGetLastError
0x18004287f  mov     ebx, eax
0x180042881  bts     ebx, 1Ch
0x180042885  call    GetCurrentProcessId_0
0x18004288a  mov     dword ptr [rsp+138h+lpName], ebx
0x18004288e  mov     [rsp+138h+dwMaximumSizeLow], 37Fh
0x180042896  lea     r8, aWerReportfault_19; "WER/ReportFault/%u:%u: ERROR MapViewOfF"...
0x18004289d  jmp     loc_180042CB3
0x1800428a2  call    cs:__imp_GetCurrentProcess
0x1800428a8  mov     rdi, rax
0x1800428ab  call    cs:__imp_GetCurrentProcess
0x1800428b1  mov     rbx, rax
0x1800428b4  call    cs:__imp_GetCurrentProcess
0x1800428ba  mov     [rsp+138h+dwOptions], 0; dwOptions
0x1800428c2  mov     dword ptr [rsp+138h+lpName], 1; bInheritHandle
0x1800428ca  mov     [rsp+138h+dwMaximumSizeLow], 1FFFFFh; dwDesiredAccess
0x1800428d2  lea     r9, [rsp+138h+TargetHandle]; lpTargetHandle
0x1800428d7  mov     r8, rdi; hTargetProcessHandle
0x1800428da  mov     rdx, rbx; hSourceHandle
0x1800428dd  mov     rcx, rax; hSourceProcessHandle
0x1800428e0  call    cs:__imp_DuplicateHandle
0x1800428e6  test    eax, eax
0x1800428e8  jz      short loc_1800428FF
0x1800428ea  mov     rax, [rsp+138h+TargetHandle]
0x1800428ef  mov     [rsp+rsi*8+138h+var_70], rax
0x1800428f7  inc     esi
0x1800428f9  mov     [rsp+138h+var_F8], esi
0x1800428fd  jmp     short loc_18004292F
0x1800428ff  call    WerpGetLastError
0x180042904  mov     ebx, eax
0x180042906  call    GetCurrentProcessId_0
0x18004290b  mov     dword ptr [rsp+138h+lpName], ebx
0x18004290f  mov     [rsp+138h+dwMaximumSizeLow], 399h
0x180042917  mov     r9d, eax
0x18004291a  lea     r8, aWerReportfault_23; "WER/ReportFault/%u:%u: WARNING Duplicat"...
0x180042921  mov     edx, 1; Level
0x180042926  mov     ecx, r15d; ComponentId
0x180042929  call    cs:__imp_DbgPrintEx
0x18004292f  call    cs:__imp_GetCurrentProcess
0x180042935  mov     rdi, rax
0x180042938  call    GetCurrentThread_0
0x18004293d  mov     rbx, rax
0x180042940  call    cs:__imp_GetCurrentProcess
0x180042946  mov     [rsp+138h+dwOptions], 0; dwOptions
0x18004294e  mov     dword ptr [rsp+138h+lpName], 1; bInheritHandle
0x180042956  mov     [rsp+138h+dwMaximumSizeLow], 1FFFFFh; dwDesiredAccess
0x18004295e  lea     r9, [rsp+138h+Handle]; lpTargetHandle
0x180042963  mov     r8, rdi; hTargetProcessHandle
0x180042966  mov     rdx, rbx; hSourceHandle
0x180042969  mov     rcx, rax; hSourceProcessHandle
0x18004296c  call    cs:__imp_DuplicateHandle
0x180042972  test    eax, eax
0x180042974  jz      short loc_18004298B
0x180042976  mov     rax, [rsp+138h+Handle]
0x18004297b  mov     [rsp+rsi*8+138h+var_70], rax
0x180042983  inc     esi
0x180042985  mov     [rsp+138h+var_F8], esi
0x180042989  jmp     short loc_1800429BB
0x18004298b  call    WerpGetLastError
0x180042990  mov     ebx, eax
0x180042992  call    GetCurrentProcessId_0
0x180042997  mov     dword ptr [rsp+138h+lpName], ebx
0x18004299b  mov     [rsp+138h+dwMaximumSizeLow], 3AAh
0x1800429a3  mov     r9d, eax
0x1800429a6  lea     r8, aWerReportfault_11; "WER/ReportFault/%u:%u: WARNING Duplicat"...
0x1800429ad  mov     edx, 1; Level
0x1800429b2  mov     ecx, r15d; ComponentId
0x1800429b5  call    cs:__imp_DbgPrintEx
0x1800429bb  mov     rdi, [rsp+138h+lpBaseAddress]
0x1800429c0  mov     dword ptr [rdi], 0F8h
0x1800429c6  call    GetCurrentProcessId_0
0x1800429cb  mov     [rdi+4], eax
0x1800429ce  call    GetCurrentThreadId_0
0x1800429d3  mov     [rdi+8], eax
0x1800429d6  mov     rax, [rsp+138h+var_B8]
0x1800429de  mov     [rdi+0A8h], rax
0x1800429e5  mov     dword ptr [rdi+0B0h], 80004005h
0x1800429ef  mov     rax, [rsp+138h+TargetHandle]
0x1800429f4  mov     [rdi+0B8h], rax
0x1800429fb  mov     rax, [rsp+138h+Handle]
0x180042a00  mov     [rdi+0C0h], rax
0x180042a07  mov     [rdi+0C8h], r14
0x180042a0e  mov     [rdi+0D0h], r13
0x180042a15  mov     qword ptr [rdi+0E0h], 0
0x180042a20  mov     dword ptr [rdi+0E8h], 0C0000001h
0x180042a2a  mov     eax, [rsp+138h+var_F4]
0x180042a2e  and     eax, 2
0x180042a31  add     eax, eax
0x180042a33  mov     [rdi+0ECh], eax
0x180042a39  call    cs:__imp_GetTickCount
0x180042a3f  mov     [rdi+0F0h], eax
0x180042a45  call    GetCurrentProcessId_0
0x180042a4a  mov     ecx, eax
0x180042a4c  lea     rax, [rsp+138h+var_E8]
0x180042a51  mov     [rsp+138h+lpName], rax
0x180042a56  mov     [rsp+138h+dwMaximumSizeLow], 0
0x180042a5e  mov     r9d, esi
0x180042a61  lea     r8, [rsp+138h+var_70]
0x180042a69  mov     rbx, [rsp+138h+var_D0]
0x180042a6e  mov     rdx, rbx
0x180042a71  call    cs:__imp_RtlWerpReportException
0x180042a77  mov     [rsp+138h+var_F4], eax
0x180042a7b  test    eax, eax
0x180042a7d  jns     loc_180042B3E
0x180042a83  call    GetCurrentProcessId_0
0x180042a88  mov     r9d, eax
0x180042a8b  mov     eax, [rsp+138h+var_F4]
0x180042a8f  mov     dword ptr [rsp+138h+lpName], eax
0x180042a93  mov     [rsp+138h+dwMaximumSizeLow], 3D0h
0x180042a9b  lea     r8, aWerReportfault_12; "WER/ReportFault/%u:%u: WARNING RtlWerpR"...
0x180042aa2  mov     edx, 1; Level
0x180042aa7  mov     ecx, r15d; ComponentId
0x180042aaa  call    cs:__imp_DbgPrintEx
0x180042ab0  cmp     [rsp+138h+var_F4], 0C0000041h
0x180042ab8  jnz     short loc_180042AE6
0x180042aba  mov     ebx, 1B000Bh
0x180042abf  call    GetCurrentProcessId_0
0x180042ac4  mov     [rsp+138h+dwMaximumSizeLow], 3DBh
0x180042acc  lea     r8, aWerReportfault_17; "WER/ReportFault/%u:%u: ERROR RtlWerpRep"...
0x180042ad3  mov     r9d, eax
0x180042ad6  xor     edx, edx; Level
0x180042ad8  mov     ecx, r15d; ComponentId
0x180042adb  call    cs:__imp_DbgPrintEx
0x180042ae1  jmp     loc_180042CC2
0x180042ae6  mov     rax, [rsp+138h+var_B8]
0x180042aee  mov     rax, [rax]
0x180042af1  cmp     dword ptr [rax], 0C00000FDh
0x180042af7  jnz     short loc_180042B03
0x180042af9  mov     ebx, 80070032h
0x180042afe  jmp     loc_180042CC2
0x180042b03  lea     r9, [rsp+138h+var_E8]
0x180042b08  mov     r8d, esi
0x180042b0b  lea     rdx, [rsp+138h+var_70]
0x180042b13  mov     rcx, rbx; void *
0x180042b16  call    StartCrashVertical
0x180042b1b  mov     ebx, eax
0x180042b1d  test    eax, eax
0x180042b1f  jns     short loc_180042B60
0x180042b21  call    GetCurrentProcessId_0
0x180042b26  mov     dword ptr [rsp+138h+lpName], ebx
0x180042b2a  mov     [rsp+138h+dwMaximumSizeLow], 3F3h
0x180042b32  lea     r8, aWerReportfault; "WER/ReportFault/%u:%u: ERROR StartCrash"...
0x180042b39  jmp     loc_180042CB3
0x180042b3e  mov     ebx, 1B000Bh
0x180042b43  cmp     eax, ebx
0x180042b45  jnz     short loc_180042B60
0x180042b47  call    GetCurrentProcessId_0
0x180042b4c  mov     [rsp+138h+dwMaximumSizeLow], 402h
0x180042b54  lea     r8, aWerReportfault_9; "WER/ReportFault/%u:%u: ERROR RtlWerpRep"...
0x180042b5b  jmp     loc_180042AD3
0x180042b60  cmp     [rsp+138h+var_E8], 0
0x180042b66  jnz     short loc_180042B72
0x180042b68  mov     ebx, 1B0002h
0x180042b6d  jmp     loc_180042CC2
0x180042b72  xorps   xmm0, xmm0
0x180042b75  xor     eax, eax
0x180042b77  movups  xmmword ptr [rsp+138h+Handles], xmm0
0x180042b7f  mov     [rsp+138h+var_78], rax
0x180042b87  mov     ebx, 0D000022Dh
0x180042b8c  cmp     ebx, 0D000022Dh
0x180042b92  jnz     loc_180042C88
0x180042b98  mov     [rsp+138h+var_F0], 0
0x180042ba0  mov     rax, [rsp+138h+var_E8]
0x180042ba5  mov     [rsp+138h+Handles], rax
0x180042bad  mov     ecx, 1
0x180042bb2  mov     [rsp+138h+var_F0], ecx
0x180042bb6  test    r13, r13
0x180042bb9  jz      short loc_180042BCC
0x180042bbb  mov     [rsp+138h+Handles+8], r13
0x180042bc3  mov     ecx, 2
0x180042bc8  mov     [rsp+138h+var_F0], ecx
0x180042bcc  test    r14, r14
0x180042bcf  jz      short loc_180042BE1
0x180042bd1  mov     eax, ecx
0x180042bd3  mov     [rsp+rax*8+138h+Handles], r14
0x180042bdb  inc     ecx; nCount
0x180042bdd  mov     [rsp+138h+var_F0], ecx
0x180042be1  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180042be5  xor     r8d, r8d; bWaitAll
0x180042be8  lea     rdx, [rsp+138h+Handles]; lpHandles
0x180042bf0  call    cs:__imp_WaitForMultipleObjects
0x180042bf6  mov     esi, eax
0x180042bf8  mov     ecx, eax
0x180042bfa  test    eax, eax
0x180042bfc  jz      short loc_180042C46
0x180042bfe  sub     ecx, 1
0x180042c01  jz      short loc_180042C41
0x180042c03  cmp     ecx, 1
  ... truncated ...
```
