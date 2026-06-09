# _RPCClientDuplicateHandle

- ea: `0x18000f88c`
- end: `0x18000f9a7`
- name: `_RPCClientDuplicateHandle`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f5e8`

## callees

- `0x180003cf0`
- `0x18000f6c8`
- `0x18000f88c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f94b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f95f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f94b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f95f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f913`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f913`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000f941`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000f941`
- `ntdll!NtClose` at `0x18000f98f`
- `ntdll!NtClose` at `0x18000f98f`

## string_xrefs

- `0x18000f8bd`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000f905`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall RPCClientDuplicateHandle(__int64 a1, void *a2, HANDLE *a3)
{
  unsigned int LastError; // ebx
  int ClientProcessHandle; // eax
  __int64 v7; // r9
  __int64 v8; // rcx
  HANDLE CurrentProcess; // rax
  HANDLE hTargetProcessHandle; // [rsp+60h] [rbp+18h] BYREF
  HANDLE TargetHandle; // [rsp+68h] [rbp+20h] BYREF

  hTargetProcessHandle = 0;
  TargetHandle = 0;
  if ( !a3 )
  {
    LastError = -2146893785;
    DebugTraceError(2148073511LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 287);
    return LastError;
  }
  *a3 = (HANDLE)-1LL;
  ClientProcessHandle = GetClientProcessHandle(a1, &hTargetProcessHandle);
  LastError = ClientProcessHandle;
  if ( ClientProcessHandle < 0 )
  {
    v7 = 300;
    v8 = (unsigned int)ClientProcessHandle;
LABEL_5:
    DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v7);
    goto LABEL_12;
  }
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(CurrentProcess, a2, hTargetProcessHandle, &TargetHandle, 0, 0, 2u) )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0xC0070000;
    else
      LastError = GetLastError();
    v7 = 314;
    v8 = LastError;
    goto LABEL_5;
  }
  LastError = 0;
  *a3 = TargetHandle;
LABEL_12:
  if ( hTargetProcessHandle )
    NtClose(hTargetProcessHandle);
  return LastError;
}

```

## disassembly

```asm
0x18000f88c  mov     rax, rsp
0x18000f88f  mov     [rax+8], rbx
0x18000f893  mov     [rax+10h], rbp
0x18000f897  push    rdi
0x18000f898  sub     rsp, 40h
0x18000f89c  mov     qword ptr [rax+18h], 0
0x18000f8a4  mov     rdi, r8
0x18000f8a7  mov     qword ptr [rax+20h], 0
0x18000f8af  mov     rbp, rdx
0x18000f8b2  test    r8, r8
0x18000f8b5  jnz     short loc_18000F8DF
0x18000f8b7  mov     r9d, 11Fh
0x18000f8bd  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f8c4  lea     rdx, aStatus; "Status"
0x18000f8cb  mov     ecx, 80090027h
0x18000f8d0  mov     ebx, 80090027h
0x18000f8d5  call    DebugTraceError
0x18000f8da  jmp     loc_18000F995
0x18000f8df  lea     rdx, [rsp+48h+hTargetProcessHandle]
0x18000f8e4  mov     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x18000f8eb  call    _GetClientProcessHandle
0x18000f8f0  mov     ebx, eax
0x18000f8f2  test    eax, eax
0x18000f8f4  jns     short loc_18000F913
0x18000f8f6  mov     r9d, 12Ch
0x18000f8fc  mov     ecx, eax
0x18000f8fe  lea     rdx, aStatus; "Status"
0x18000f905  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f90c  call    DebugTraceError
0x18000f911  jmp     short loc_18000F982
0x18000f913  call    cs:__imp_GetCurrentProcess
0x18000f919  mov     r8, [rsp+48h+hTargetProcessHandle]; hTargetProcessHandle
0x18000f91e  lea     r9, [rsp+48h+TargetHandle]; lpTargetHandle
0x18000f923  mov     [rsp+48h+dwOptions], 2; dwOptions
0x18000f92b  mov     rcx, rax; hSourceProcessHandle
0x18000f92e  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x18000f936  mov     rdx, rbp; hSourceHandle
0x18000f939  mov     [rsp+48h+dwDesiredAccess], 0; dwDesiredAccess
0x18000f941  call    cs:__imp_DuplicateHandle
0x18000f947  test    eax, eax
0x18000f949  jnz     short loc_18000F978
0x18000f94b  call    cs:__imp_GetLastError
0x18000f951  test    eax, eax
0x18000f953  jg      short loc_18000F95F
0x18000f955  call    cs:__imp_GetLastError
0x18000f95b  mov     ebx, eax
0x18000f95d  jmp     short loc_18000F96E
0x18000f95f  call    cs:__imp_GetLastError
0x18000f965  movzx   ebx, ax
0x18000f968  or      ebx, 0C0070000h
0x18000f96e  mov     r9d, 13Ah
0x18000f974  mov     ecx, ebx
0x18000f976  jmp     short loc_18000F8FE
0x18000f978  mov     rax, [rsp+48h+TargetHandle]
0x18000f97d  xor     ebx, ebx
0x18000f97f  mov     [rdi], rax
0x18000f982  cmp     [rsp+48h+hTargetProcessHandle], 0
0x18000f988  jz      short loc_18000F995
0x18000f98a  mov     rcx, [rsp+48h+hTargetProcessHandle]; Handle
0x18000f98f  call    cs:__imp_NtClose
0x18000f995  mov     rbp, [rsp+48h+arg_8]
0x18000f99a  mov     eax, ebx
0x18000f99c  mov     rbx, [rsp+48h+arg_0]
0x18000f9a1  add     rsp, 40h
0x18000f9a5  pop     rdi
0x18000f9a6  retn
```
