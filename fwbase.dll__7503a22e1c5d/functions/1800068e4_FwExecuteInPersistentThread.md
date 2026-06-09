# FwExecuteInPersistentThread

- ea: `0x1800068e4`
- end: `0x180006a3c`
- name: `FwExecuteInPersistentThread`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800053c0`

## callees

- `0x180004750`
- `0x1800047e0`
- `0x1800068e4`
- `0x180007010`
- `0x18001e1d0`
- `0x18002f43c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006919`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180006919`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000699d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000699d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800069c4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800069cf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800069da`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800069e5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800069f0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800069c4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800069cf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800069da`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800069e5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800069f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069a7`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000697a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000697a`

## string_xrefs

- `0x180006924`: `FwExecuteInPersistentThread`
- `0x180006936`: `CreateEventW`

## pseudocode

```c
__int64 __fastcall FwExecuteInPersistentThread(__int64 a1, __int64 a2)
{
  DWORD LastError; // eax
  const char *v4; // rdx
  int v5; // ebx
  DWORD v6; // eax
  __int128 Context; // [rsp+20h] [rbp-38h] BYREF
  __int128 v9; // [rsp+30h] [rbp-28h]

  Context = 0;
  v9 = 0;
  *(_QWORD *)&Context = CreateEventW(0, 1, 0, 0);
  if ( !(_QWORD)Context )
  {
    LastError = GetLastError();
    v4 = "CreateEventW";
LABEL_3:
    v5 = FwReportErrorAsWinError("FwExecuteInPersistentThread", v4, LastError);
    goto LABEL_12;
  }
  *(_QWORD *)&v9 = a2;
  *((_QWORD *)&Context + 1) = FwRegNotifyRegisterForChanges;
  DWORD2(v9) = 0;
  if ( !QueueUserWorkItem(FwPersistentThreadStartRoutine, &Context, 0x80u) )
  {
    LastError = GetLastError();
    v4 = "QueueUserWorkItem";
    goto LABEL_3;
  }
  v6 = WaitForSingleObject((HANDLE)Context, 0xFFFFFFFF);
  if ( v6 == -1 )
  {
    LastError = GetLastError();
    v4 = "WaitForSingleObject";
    goto LABEL_3;
  }
  if ( v6 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  Sleep(1u);
  Sleep(1u);
  Sleep(2u);
  Sleep(3u);
  Sleep(4u);
  v5 = DWORD2(v9);
  if ( SDWORD2(v9) < 0 )
    FwReportReturnError("FwExecuteInPersistentThread", DWORD2(v9));
LABEL_12:
  FwCloseHandle(Context);
  if ( v5 < 0 )
    return (unsigned int)FwReportReturnError("FwExecuteInPersistentThread", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800068e4  mov     [rsp+arg_0], rbx
0x1800068e9  push    rdi
0x1800068ea  sub     rsp, 50h
0x1800068ee  mov     rax, cs:__security_cookie
0x1800068f5  xor     rax, rsp
0x1800068f8  mov     [rsp+58h+var_18], rax
0x1800068fd  xorps   xmm0, xmm0
0x180006900  xor     r9d, r9d; lpName
0x180006903  mov     rbx, rdx
0x180006906  xor     r8d, r8d; bInitialState
0x180006909  xor     ecx, ecx; lpEventAttributes
0x18000690b  movups  [rsp+58h+Context], xmm0
0x180006910  lea     edx, [r9+1]; bManualReset
0x180006914  movups  [rsp+58h+var_28], xmm0
0x180006919  call    cs:__imp_CreateEventW
0x18000691f  mov     qword ptr [rsp+58h+Context], rax
0x180006924  lea     rdi, aFwexecuteinper; "FwExecuteInPersistentThread"
0x18000692b  test    rax, rax
0x18000692e  jnz     short loc_18000694F
0x180006930  call    cs:__imp_GetLastError
0x180006936  lea     rdx, aCreateeventw; "CreateEventW"
0x18000693d  mov     r8d, eax
0x180006940  mov     rcx, rdi
0x180006943  call    FwReportErrorAsWinError
0x180006948  mov     ebx, eax
0x18000694a  jmp     loc_180006A08
0x18000694f  lea     rax, ?FwRegNotifyRegisterForChanges@@YAJPEAUFW_REG_NOTIFY_@@@Z; FwRegNotifyRegisterForChanges(FW_REG_NOTIFY_ *)
0x180006956  mov     qword ptr [rsp+58h+var_28], rbx
0x18000695b  mov     r8d, 80h; Flags
0x180006961  mov     qword ptr [rsp+58h+Context+8], rax
0x180006966  lea     rdx, [rsp+58h+Context]; Context
0x18000696b  mov     dword ptr [rsp+58h+var_28+8], 0
0x180006973  lea     rcx, FwPersistentThreadStartRoutine; Function
0x18000697a  call    cs:__imp_QueueUserWorkItem
0x180006980  test    eax, eax
0x180006982  jnz     short loc_180006993
0x180006984  call    cs:__imp_GetLastError
0x18000698a  lea     rdx, aQueueuserworki; "QueueUserWorkItem"
0x180006991  jmp     short loc_18000693D
0x180006993  mov     rcx, qword ptr [rsp+58h+Context]; hHandle
0x180006998  or      ebx, 0FFFFFFFFh
0x18000699b  mov     edx, ebx; dwMilliseconds
0x18000699d  call    cs:__imp_WaitForSingleObject
0x1800069a3  cmp     eax, ebx
0x1800069a5  jnz     short loc_1800069B6
0x1800069a7  call    cs:__imp_GetLastError
0x1800069ad  lea     rdx, aWaitforsingleo; "WaitForSingleObject"
0x1800069b4  jmp     short loc_18000693D
0x1800069b6  test    eax, eax
0x1800069b8  jz      short loc_1800069BF
0x1800069ba  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "waitResult == WAIT_OBJECT_0")
0x1800069bf  mov     ecx, 1; dwMilliseconds
0x1800069c4  call    cs:__imp_Sleep
0x1800069ca  mov     ecx, 1; dwMilliseconds
0x1800069cf  call    cs:__imp_Sleep
0x1800069d5  mov     ecx, 2; dwMilliseconds
0x1800069da  call    cs:__imp_Sleep
0x1800069e0  mov     ecx, 3; dwMilliseconds
0x1800069e5  call    cs:__imp_Sleep
0x1800069eb  mov     ecx, 4; dwMilliseconds
0x1800069f0  call    cs:__imp_Sleep
0x1800069f6  mov     ebx, dword ptr [rsp+58h+var_28+8]
0x1800069fa  test    ebx, ebx
0x1800069fc  jns     short loc_180006A08
0x1800069fe  mov     edx, ebx
0x180006a00  mov     rcx, rdi
0x180006a03  call    FwReportReturnError
0x180006a08  mov     rcx, qword ptr [rsp+58h+Context]
0x180006a0d  call    FwCloseHandle
0x180006a12  test    ebx, ebx
0x180006a14  jns     short loc_180006A22
0x180006a16  mov     edx, ebx
0x180006a18  mov     rcx, rdi
0x180006a1b  call    FwReportReturnError
0x180006a20  mov     ebx, eax
0x180006a22  mov     eax, ebx
0x180006a24  mov     rcx, [rsp+58h+var_18]
0x180006a29  xor     rcx, rsp; StackCookie
0x180006a2c  call    __security_check_cookie
0x180006a31  mov     rbx, [rsp+58h+arg_0]
0x180006a36  add     rsp, 50h
0x180006a3a  pop     rdi
0x180006a3b  retn
```
