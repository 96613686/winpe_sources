# DsRolepSpinWorkerThread

- ea: `0x18000ffa8`
- end: `0x1800100b8`
- name: `DsRolepSpinWorkerThread`
- size: `272`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180003a80`
- `0x1800058a0`
- `0x180005e40`
- `0x1800065a0`
- `0x180006c30`

## callees

- `0x18000ffa8`
- `0x180020dbc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ffe5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000ffe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001004e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010070`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001004e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010070`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010066`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010066`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001003c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001003c`
- `ntdll!NtResetEvent` at `0x18000ffcd`
- `ntdll!NtResetEvent` at `0x180010083`
- `ntdll!NtResetEvent` at `0x18000ffcd`
- `ntdll!NtResetEvent` at `0x180010083`
- `ntdll!RtlNtStatusToDosError` at `0x18000ffd5`
- `ntdll!RtlNtStatusToDosError` at `0x18000ffd5`

## string_xrefs

- `0x180010092`: `Thread %lu unsuccessfully started: %lu\n`

## pseudocode

```c
__int64 __fastcall DsRolepSpinWorkerThread(int a1, void *a2)
{
  NTSTATUS v4; // eax
  ULONG LastError; // ebx
  int v6; // edi
  ULONG (__stdcall *v7)(PVOID); // r8
  DWORD ThreadId; // [rsp+50h] [rbp+18h] BYREF

  ThreadId = 0;
  v4 = NtResetEvent(Handle, 0);
  LastError = RtlNtStatusToDosError(v4);
  if ( LastError )
    goto LABEL_15;
  DsRoleServiceLastActivity = GetTickCount64();
  if ( a1 )
  {
    v6 = a1 - 1;
    if ( v6 )
    {
      if ( v6 != 1 )
      {
        LastError = 87;
LABEL_15:
        DsRolepLogPrintRoutine(1, "Thread %lu unsuccessfully started: %lu\n", ThreadId, LastError);
        return LastError;
      }
      v7 = (ULONG (__stdcall *)(PVOID))DsRolepThreadDemote;
    }
    else
    {
      v7 = (ULONG (__stdcall *)(PVOID))DsRolepThreadPromoteReplica;
    }
  }
  else
  {
    v7 = (ULONG (__stdcall *)(PVOID))DsRolepThreadPromoteDc;
  }
  qword_18004E1B0 = CreateThread(0, 0, v7, a2, 0, &ThreadId);
  if ( !qword_18004E1B0 )
  {
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_15;
  }
  if ( WaitForSingleObject(Handle, 0xFFFFFFFF) == -1 )
    LastError = GetLastError();
  else
    NtResetEvent(Handle, 0);
  if ( LastError )
    goto LABEL_15;
  return LastError;
}

```

## disassembly

```asm
0x18000ffa8  mov     [rsp+arg_0], rbx
0x18000ffad  mov     [rsp+arg_8], rsi
0x18000ffb2  push    rdi
0x18000ffb3  sub     rsp, 30h
0x18000ffb7  mov     rsi, rdx
0x18000ffba  mov     [rsp+38h+ThreadId], 0
0x18000ffc2  mov     edi, ecx
0x18000ffc4  xor     edx, edx; NumberOfWaitingThreads
0x18000ffc6  mov     rcx, cs:Handle; EventHandle
0x18000ffcd  call    cs:__imp_NtResetEvent
0x18000ffd3  mov     ecx, eax; Status
0x18000ffd5  call    cs:__imp_RtlNtStatusToDosError
0x18000ffdb  mov     ebx, eax
0x18000ffdd  test    eax, eax
0x18000ffdf  jnz     loc_18001008D
0x18000ffe5  call    cs:__imp_GetTickCount64
0x18000ffeb  mov     cs:DsRoleServiceLastActivity, rax
0x18000fff2  test    edi, edi
0x18000fff4  jz      short loc_18001001C
0x18000fff6  sub     edi, 1
0x18000fff9  jz      short loc_180010013
0x18000fffb  cmp     edi, 1
0x18000fffe  jz      short loc_18001000A
0x180010000  mov     ebx, 57h ; 'W'
0x180010005  jmp     loc_18001008D
0x18001000a  lea     r8, DsRolepThreadDemote
0x180010011  jmp     short loc_180010023
0x180010013  lea     r8, DsRolepThreadPromoteReplica
0x18001001a  jmp     short loc_180010023
0x18001001c  lea     r8, DsRolepThreadPromoteDc; lpStartAddress
0x180010023  lea     rax, [rsp+38h+ThreadId]
0x180010028  mov     r9, rsi; lpParameter
0x18001002b  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180010030  xor     edx, edx; dwStackSize
0x180010032  xor     ecx, ecx; lpThreadAttributes
0x180010034  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18001003c  call    cs:__imp_CreateThread
0x180010042  mov     cs:qword_18004E1B0, rax
0x180010049  test    rax, rax
0x18001004c  jnz     short loc_18001005A
0x18001004e  call    cs:__imp_GetLastError
0x180010054  mov     ebx, eax
0x180010056  test    eax, eax
0x180010058  jnz     short loc_18001008D
0x18001005a  mov     rcx, cs:Handle; hHandle
0x180010061  or      edi, 0FFFFFFFFh
0x180010064  mov     edx, edi; dwMilliseconds
0x180010066  call    cs:__imp_WaitForSingleObject
0x18001006c  cmp     eax, edi
0x18001006e  jnz     short loc_18001007A
0x180010070  call    cs:__imp_GetLastError
0x180010076  mov     ebx, eax
0x180010078  jmp     short loc_180010089
0x18001007a  mov     rcx, cs:Handle; EventHandle
0x180010081  xor     edx, edx; NumberOfWaitingThreads
0x180010083  call    cs:__imp_NtResetEvent
0x180010089  test    ebx, ebx
0x18001008b  jz      short loc_1800100A6
0x18001008d  mov     r8d, [rsp+38h+ThreadId]
0x180010092  lea     rdx, aThreadLuUnsucc; "Thread %lu unsuccessfully started: %lu"...
0x180010099  mov     r9d, ebx
0x18001009c  mov     ecx, 1
0x1800100a1  call    DsRolepLogPrintRoutine
0x1800100a6  mov     rsi, [rsp+38h+arg_8]
0x1800100ab  mov     eax, ebx
0x1800100ad  mov     rbx, [rsp+38h+arg_0]
0x1800100b2  add     rsp, 30h
0x1800100b6  pop     rdi
0x1800100b7  retn
```
