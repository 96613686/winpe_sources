# DsRolepWaitForService

- ea: `0x18000ba6c`
- end: `0x18000bbcd`
- name: `DsRolepWaitForService`
- size: `353`
- prototype: `__int64 __fastcall(SC_HANDLE hService)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000a364`

## callees

- `0x18000ba6c`
- `0x180020dbc`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000bb54`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000bb54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000baf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000baf9`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18000baed`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18000baed`

## string_xrefs

- `0x18000ba9f`: `DsRolepWaitForService: waiting for %ws to enter one of %lu states\n`
- `0x18000bb05`: `DsRolepWaitForService: QueryServiceStatus on %ws returned %lu (gle=%lu), SvcStatus.dwCS=%lu\n`
- `0x18000bba0`: `DsRolepWaitForService: exiting due to QueryServiceStatus failure\n`
- `0x18000bb8c`: `DsRolepWaitForService: exiting because %ws entered STOPPED state\n`
- `0x18000bb83`: `DsRolepWaitForService: exiting because %ws entered RUNNING state\n`
- `0x18000bb7a`: `DsRolepWaitForService: exiting because %ws entered PAUSED state\n`
- `0x18000bb61`: `DsRolepWaitForService: timed out after waiting %lu msec for %ws\n`

## pseudocode

```c
__int64 __fastcall DsRolepWaitForService(SC_HANDLE hService, __int64 a2, __int64 a3, unsigned int *a4)
{
  unsigned int *v7; // rsi
  unsigned int v8; // r14d
  DWORD LastError; // ebx
  unsigned int v10; // ebp
  DWORD dwWaitHint; // ebx
  __int64 v13; // [rsp+20h] [rbp-78h]
  __int64 v14; // [rsp+28h] [rbp-70h]
  int v15; // [rsp+30h] [rbp-68h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-60h] BYREF

  v15 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  DsRolepLogPrintRoutine(4, "DsRolepWaitForService: waiting for %ws to enter one of %lu states\n", a2, 7);
  v7 = (unsigned int *)&v15;
  v8 = a4 != 0 ? 180000 : 120000;
  if ( a4 )
    v7 = a4;
  while ( 1 )
  {
    LastError = 0;
    v10 = QueryServiceStatus(hService, &ServiceStatus);
    if ( !v10 )
      LastError = GetLastError();
    LODWORD(v14) = ServiceStatus.dwCurrentState;
    LODWORD(v13) = LastError;
    DsRolepLogPrintRoutine(
      4,
      "DsRolepWaitForService: QueryServiceStatus on %ws returned %lu (gle=%lu), SvcStatus.dwCS=%lu\n",
      a2,
      v10,
      v13,
      v14);
    if ( LastError )
      break;
    switch ( ServiceStatus.dwCurrentState )
    {
      case 1u:
        DsRolepLogPrintRoutine(4, "DsRolepWaitForService: exiting because %ws entered STOPPED state\n", a2);
        return LastError;
      case 4u:
        DsRolepLogPrintRoutine(4, "DsRolepWaitForService: exiting because %ws entered RUNNING state\n", a2);
        return LastError;
      case 7u:
        DsRolepLogPrintRoutine(4, "DsRolepWaitForService: exiting because %ws entered PAUSED state\n", a2);
        return LastError;
    }
    if ( *v7 >= v8 )
    {
      LastError = 258;
      DsRolepLogPrintRoutine(4, "DsRolepWaitForService: timed out after waiting %lu msec for %ws\n", v7, a2);
      return LastError;
    }
    dwWaitHint = ServiceStatus.dwWaitHint;
    if ( ServiceStatus.dwWaitHint - 1 > 0x3E7 )
      dwWaitHint = 1000;
    Sleep(dwWaitHint);
    *v7 += dwWaitHint;
  }
  DsRolepLogPrintRoutine(4, "DsRolepWaitForService: exiting due to QueryServiceStatus failure\n");
  return LastError;
}

```

## disassembly

```asm
0x18000ba6c  push    rbx
0x18000ba6e  push    rbp
0x18000ba6f  push    rsi
0x18000ba70  push    rdi
0x18000ba71  push    r12
0x18000ba73  push    r14
0x18000ba75  push    r15
0x18000ba77  sub     rsp, 60h
0x18000ba7b  mov     rax, cs:__security_cookie
0x18000ba82  xor     rax, rsp
0x18000ba85  mov     [rsp+98h+var_40], rax
0x18000ba8a  xor     eax, eax
0x18000ba8c  xorps   xmm0, xmm0
0x18000ba8f  mov     rbx, r9
0x18000ba92  mov     [rsp+98h+var_68], eax
0x18000ba96  mov     rdi, rdx
0x18000ba99  mov     r15, rcx
0x18000ba9c  mov     r8, rdx
0x18000ba9f  lea     rdx, aDsrolepwaitfor_0; "DsRolepWaitForService: waiting for %ws "...
0x18000baa6  lea     r12d, [rax+4]
0x18000baaa  movups  xmmword ptr [rsp+98h+ServiceStatus.dwServiceType], xmm0
0x18000baaf  mov     ecx, r12d
0x18000bab2  lea     r9d, [rax+7]
0x18000bab6  movups  xmmword ptr [rsp+98h+ServiceStatus.dwWin32ExitCode], xmm0
0x18000babb  call    DsRolepLogPrintRoutine
0x18000bac0  mov     rax, rbx
0x18000bac3  lea     rsi, [rsp+98h+var_68]
0x18000bac8  neg     rax
0x18000bacb  sbb     r14d, r14d
0x18000bace  and     r14d, 0EA60h
0x18000bad5  add     r14d, 1D4C0h
0x18000badc  test    rbx, rbx
0x18000badf  cmovnz  rsi, rbx
0x18000bae3  lea     rdx, [rsp+98h+ServiceStatus]; lpServiceStatus
0x18000bae8  mov     rcx, r15; hService
0x18000baeb  xor     ebx, ebx
0x18000baed  call    cs:__imp_QueryServiceStatus
0x18000baf3  mov     ebp, eax
0x18000baf5  test    eax, eax
0x18000baf7  jnz     short loc_18000BB01
0x18000baf9  call    cs:__imp_GetLastError
0x18000baff  mov     ebx, eax
0x18000bb01  mov     ecx, [rsp+98h+ServiceStatus.dwCurrentState]
0x18000bb05  lea     rdx, aDsrolepwaitfor_5; "DsRolepWaitForService: QueryServiceStat"...
0x18000bb0c  mov     dword ptr [rsp+98h+var_70], ecx
0x18000bb10  mov     r9d, ebp
0x18000bb13  mov     ecx, r12d
0x18000bb16  mov     dword ptr [rsp+98h+var_78], ebx
0x18000bb1a  mov     r8, rdi
0x18000bb1d  call    DsRolepLogPrintRoutine
0x18000bb22  test    ebx, ebx
0x18000bb24  jnz     short loc_18000BBA0
0x18000bb26  mov     ecx, [rsp+98h+ServiceStatus.dwCurrentState]
0x18000bb2a  cmp     ecx, 1
0x18000bb2d  jz      short loc_18000BB8C
0x18000bb2f  cmp     ecx, r12d
0x18000bb32  jz      short loc_18000BB83
0x18000bb34  cmp     ecx, 7
0x18000bb37  jz      short loc_18000BB7A
0x18000bb39  cmp     [rsi], r14d
0x18000bb3c  jnb     short loc_18000BB5E
0x18000bb3e  mov     ebx, [rsp+98h+ServiceStatus.dwWaitHint]
0x18000bb42  mov     ecx, 3E8h
0x18000bb47  lea     eax, [rbx-1]
0x18000bb4a  cmp     eax, 3E7h
0x18000bb4f  cmova   ebx, ecx
0x18000bb52  mov     ecx, ebx; dwMilliseconds
0x18000bb54  call    cs:__imp_Sleep
0x18000bb5a  add     [rsi], ebx
0x18000bb5c  jmp     short loc_18000BAE3
0x18000bb5e  mov     r9, rdi
0x18000bb61  lea     rdx, aDsrolepwaitfor; "DsRolepWaitForService: timed out after "...
0x18000bb68  mov     r8, rsi
0x18000bb6b  mov     ecx, r12d
0x18000bb6e  mov     ebx, 102h
0x18000bb73  call    DsRolepLogPrintRoutine
0x18000bb78  jmp     short loc_18000BBAF
0x18000bb7a  lea     rdx, aDsrolepwaitfor_3; "DsRolepWaitForService: exiting because "...
0x18000bb81  jmp     short loc_18000BB93
0x18000bb83  lea     rdx, aDsrolepwaitfor_1; "DsRolepWaitForService: exiting because "...
0x18000bb8a  jmp     short loc_18000BB93
0x18000bb8c  lea     rdx, aDsrolepwaitfor_2; "DsRolepWaitForService: exiting because "...
0x18000bb93  mov     r8, rdi
0x18000bb96  mov     ecx, r12d
0x18000bb99  call    DsRolepLogPrintRoutine
0x18000bb9e  jmp     short loc_18000BBAF
0x18000bba0  lea     rdx, aDsrolepwaitfor_4; "DsRolepWaitForService: exiting due to Q"...
0x18000bba7  mov     ecx, r12d
0x18000bbaa  call    DsRolepLogPrintRoutine
0x18000bbaf  mov     eax, ebx
0x18000bbb1  mov     rcx, [rsp+98h+var_40]
0x18000bbb6  xor     rcx, rsp; StackCookie
0x18000bbb9  call    __security_check_cookie
0x18000bbbe  add     rsp, 60h
0x18000bbc2  pop     r15
0x18000bbc4  pop     r14
0x18000bbc6  pop     r12
0x18000bbc8  pop     rdi
0x18000bbc9  pop     rsi
0x18000bbca  pop     rbp
0x18000bbcb  pop     rbx
0x18000bbcc  retn
```
