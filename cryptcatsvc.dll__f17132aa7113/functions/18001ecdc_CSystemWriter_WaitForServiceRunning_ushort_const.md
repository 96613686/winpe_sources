# CSystemWriter::WaitForServiceRunning(ushort const *)

- ea: `0x18001ecdc`
- end: `0x18001ee63`
- name: `?WaitForServiceRunning@CSystemWriter@@CAHPEBG@Z`
- size: `391`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001e5e0`

## callees

- `0x180006e54`
- `0x18000be40`
- `0x18001ecdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001edc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001edc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee01`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ede1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ede1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001edd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ee25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001edd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ee25`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001edb1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001edb1`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001ed38`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001ed38`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ee33`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ee41`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ee33`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001ee41`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ed06`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001ed06`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18001ed92`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18001ed92`

## string_xrefs

- `0x18001ed1c`: `Could not open the Service Control Manager.`
- `0x18001ed5d`: `Could not open the EventSystem service for query.`
- `0x18001ee07`: `Could not query the status of the EventSystem service.`

## pseudocode

```c
__int64 __fastcall CSystemWriter::WaitForServiceRunning(const unsigned __int16 *a1)
{
  _DWORD *v1; // rbx
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  SC_HANDLE v4; // rdi
  DWORD LastError; // eax
  const unsigned __int16 *v6; // rdx
  DWORD v7; // r15d
  unsigned int v8; // ebp
  int v9; // r14d
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-48h] BYREF

  v1 = 0;
  pcbBytesNeeded = 0;
  v2 = OpenSCManagerW(0, 0, 5u);
  v3 = v2;
  if ( !v2 )
  {
    v4 = 0;
    LastError = GetLastError();
    v6 = L"Could not open the Service Control Manager.";
    goto LABEL_21;
  }
  v4 = OpenServiceW(v2, L"EventSystem", 4u);
  if ( !v4 )
  {
    if ( GetLastError() == 1060 )
    {
LABEL_22:
      v8 = 0;
      goto LABEL_23;
    }
    LastError = GetLastError();
    v6 = L"Could not open the EventSystem service for query.";
LABEL_21:
    CSystemWriter::LogSystemErrorEvent(0x200u, v6, LastError);
    goto LABEL_22;
  }
  v7 = 0;
  v8 = 1;
  v9 = 0;
  while ( !v9 )
  {
    if ( QueryServiceStatusEx(v4, SC_STATUS_PROCESS_INFO, (LPBYTE)v1, v7, &pcbBytesNeeded) )
    {
      if ( v1 && v1[1] == 4 )
      {
        v9 = 1;
      }
      else
      {
        Sleep(0x1F4u);
        if ( g_fShuttingDown )
          goto LABEL_22;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError != 122 )
        goto LABEL_20;
      if ( v1 )
        LocalFree(v1);
      v1 = LocalAlloc(0, pcbBytesNeeded);
      if ( !v1 )
      {
        LastError = GetLastError();
LABEL_20:
        v6 = L"Could not query the status of the EventSystem service.";
        goto LABEL_21;
      }
      v7 = pcbBytesNeeded;
      pcbBytesNeeded = 0;
    }
  }
LABEL_23:
  if ( v1 )
    LocalFree(v1);
  if ( v4 )
    CloseServiceHandle(v4);
  if ( v3 )
    CloseServiceHandle(v3);
  return v8;
}

```

## disassembly

```asm
0x18001ecdc  push    rbx
0x18001ecde  push    rbp
0x18001ecdf  push    rsi
0x18001ece0  push    rdi
0x18001ece1  push    r14
0x18001ece3  push    r15
0x18001ece5  sub     rsp, 48h
0x18001ece9  mov     rax, cs:__security_cookie
0x18001ecf0  xor     rax, rsp
0x18001ecf3  mov     [rsp+78h+var_40], rax
0x18001ecf8  xor     ebx, ebx
0x18001ecfa  xor     edx, edx; lpDatabaseName
0x18001ecfc  xor     ecx, ecx; lpMachineName
0x18001ecfe  mov     [rsp+78h+var_48], ebx
0x18001ed02  lea     r8d, [rbx+5]; dwDesiredAccess
0x18001ed06  call    cs:__imp_OpenSCManagerW
0x18001ed0c  mov     rsi, rax
0x18001ed0f  test    rax, rax
0x18001ed12  jnz     short loc_18001ED28
0x18001ed14  xor     edi, edi
0x18001ed16  call    cs:__imp_GetLastError
0x18001ed1c  lea     rdx, aCouldNotOpenTh; "Could not open the Service Control Mana"...
0x18001ed23  jmp     loc_18001EE0E
0x18001ed28  mov     r8d, 4; dwDesiredAccess
0x18001ed2e  lea     rdx, aEventsystem; "EventSystem"
0x18001ed35  mov     rcx, rsi; hSCManager
0x18001ed38  call    cs:__imp_OpenServiceW
0x18001ed3e  mov     rdi, rax
0x18001ed41  test    rax, rax
0x18001ed44  jnz     short loc_18001ED69
0x18001ed46  call    cs:__imp_GetLastError
0x18001ed4c  cmp     eax, 424h
0x18001ed51  jz      loc_18001EE1B
0x18001ed57  call    cs:__imp_GetLastError
0x18001ed5d  lea     rdx, aCouldNotOpenTh_0; "Could not open the EventSystem service "...
0x18001ed64  jmp     loc_18001EE0E
0x18001ed69  xor     r15d, r15d
0x18001ed6c  mov     ebp, 1
0x18001ed71  xor     r14d, r14d
0x18001ed74  test    r14d, r14d
0x18001ed77  jnz     loc_18001EE1D
0x18001ed7d  lea     rax, [rsp+78h+var_48]
0x18001ed82  mov     r9d, r15d; cbBufSize
0x18001ed85  mov     r8, rbx; lpBuffer
0x18001ed88  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18001ed8d  xor     edx, edx; InfoLevel
0x18001ed8f  mov     rcx, rdi; hService
0x18001ed92  call    cs:__imp_QueryServiceStatusEx
0x18001ed98  test    eax, eax
0x18001ed9a  jz      short loc_18001EDC2
0x18001ed9c  test    rbx, rbx
0x18001ed9f  jz      short loc_18001EDAC
0x18001eda1  cmp     dword ptr [rbx+4], 4
0x18001eda5  jnz     short loc_18001EDAC
0x18001eda7  mov     r14d, ebp
0x18001edaa  jmp     short loc_18001ED74
0x18001edac  mov     ecx, 1F4h; dwMilliseconds
0x18001edb1  call    cs:__imp_Sleep
0x18001edb7  cmp     cs:?g_fShuttingDown@@3HA, 0; int g_fShuttingDown
0x18001edbe  jz      short loc_18001ED74
0x18001edc0  jmp     short loc_18001EE1B
0x18001edc2  call    cs:__imp_GetLastError
0x18001edc8  cmp     eax, 7Ah ; 'z'
0x18001edcb  jnz     short loc_18001EE07
0x18001edcd  test    rbx, rbx
0x18001edd0  jz      short loc_18001EDDB
0x18001edd2  mov     rcx, rbx; hMem
0x18001edd5  call    cs:__imp_LocalFree
0x18001eddb  mov     edx, [rsp+78h+var_48]; uBytes
0x18001eddf  xor     ecx, ecx; uFlags
0x18001ede1  call    cs:__imp_LocalAlloc
0x18001ede7  mov     rbx, rax
0x18001edea  test    rax, rax
0x18001eded  jz      short loc_18001EE01
0x18001edef  mov     r15d, [rsp+78h+var_48]
0x18001edf4  mov     [rsp+78h+var_48], 0
0x18001edfc  jmp     loc_18001ED74
0x18001ee01  call    cs:__imp_GetLastError
0x18001ee07  lea     rdx, aCouldNotQueryT; "Could not query the status of the Event"...
0x18001ee0e  mov     r8d, eax; unsigned int
0x18001ee11  mov     ecx, 200h; unsigned int
0x18001ee16  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x18001ee1b  xor     ebp, ebp
0x18001ee1d  test    rbx, rbx
0x18001ee20  jz      short loc_18001EE2B
0x18001ee22  mov     rcx, rbx; hMem
0x18001ee25  call    cs:__imp_LocalFree
0x18001ee2b  test    rdi, rdi
0x18001ee2e  jz      short loc_18001EE39
0x18001ee30  mov     rcx, rdi; hSCObject
0x18001ee33  call    cs:__imp_CloseServiceHandle
0x18001ee39  test    rsi, rsi
0x18001ee3c  jz      short loc_18001EE47
0x18001ee3e  mov     rcx, rsi; hSCObject
0x18001ee41  call    cs:__imp_CloseServiceHandle
0x18001ee47  mov     eax, ebp
0x18001ee49  mov     rcx, [rsp+78h+var_40]
0x18001ee4e  xor     rcx, rsp; StackCookie
0x18001ee51  call    __security_check_cookie
0x18001ee56  add     rsp, 48h
0x18001ee5a  pop     r15
0x18001ee5c  pop     r14
0x18001ee5e  pop     rdi
0x18001ee5f  pop     rsi
0x18001ee60  pop     rbp
0x18001ee61  pop     rbx
0x18001ee62  retn
```
