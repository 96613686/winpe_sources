# GetSchSvcState(ulong &)

- ea: `0x18001a868`
- end: `0x18001a913`
- name: `?GetSchSvcState@@YAJAEAK@Z`
- size: `171`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18001a7e0`

## callees

- `0x18001a868`
- `0x18001a91c`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8cc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001a8ee`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001a8ee`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001a8c2`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18001a8c2`

## pseudocode

```c
__int64 __fastcall GetSchSvcState(unsigned int *a1)
{
  struct SC_HANDLE__ *v2; // rax
  SC_HANDLE v3; // rdi
  signed int v4; // eax
  unsigned int v5; // ebx
  signed int LastError; // eax
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  v2 = OpenScheduleService();
  v3 = v2;
  if ( v2 )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( QueryServiceStatus(v2, &ServiceStatus) )
    {
      v5 = 0;
      *a1 = ServiceStatus.dwCurrentState;
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseServiceHandle(v3);
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
  }
  return v5;
}

```

## disassembly

```asm
0x18001a868  mov     [rsp+arg_8], rbx
0x18001a86d  mov     [rsp+arg_10], rsi
0x18001a872  push    rdi
0x18001a873  sub     rsp, 50h
0x18001a877  mov     rax, cs:__security_cookie
0x18001a87e  xor     rax, rsp
0x18001a881  mov     [rsp+58h+var_18], rax
0x18001a886  mov     rsi, rcx
0x18001a889  call    ?OpenScheduleService@@YAPEAUSC_HANDLE__@@K@Z; OpenScheduleService(ulong)
0x18001a88e  mov     rdi, rax
0x18001a891  test    rax, rax
0x18001a894  jnz     short loc_18001A8AD
0x18001a896  call    cs:__imp_GetLastError
0x18001a89c  mov     ebx, eax
0x18001a89e  test    eax, eax
0x18001a8a0  jle     short loc_18001A8F4
0x18001a8a2  movzx   ebx, ax
0x18001a8a5  or      ebx, 80070000h
0x18001a8ab  jmp     short loc_18001A8F4
0x18001a8ad  xorps   xmm0, xmm0
0x18001a8b0  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18001a8b5  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x18001a8ba  mov     rcx, rdi; hService
0x18001a8bd  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18001a8c2  call    cs:__imp_QueryServiceStatus
0x18001a8c8  test    eax, eax
0x18001a8ca  jnz     short loc_18001A8E3
0x18001a8cc  call    cs:__imp_GetLastError
0x18001a8d2  mov     ebx, eax
0x18001a8d4  test    eax, eax
0x18001a8d6  jle     short loc_18001A8EB
0x18001a8d8  movzx   ebx, ax
0x18001a8db  or      ebx, 80070000h
0x18001a8e1  jmp     short loc_18001A8EB
0x18001a8e3  mov     ecx, [rsp+58h+ServiceStatus.dwCurrentState]
0x18001a8e7  xor     ebx, ebx
0x18001a8e9  mov     [rsi], ecx
0x18001a8eb  mov     rcx, rdi; hSCObject
0x18001a8ee  call    cs:__imp_CloseServiceHandle
0x18001a8f4  mov     eax, ebx
0x18001a8f6  mov     rcx, [rsp+58h+var_18]
0x18001a8fb  xor     rcx, rsp; StackCookie
0x18001a8fe  call    __security_check_cookie
0x18001a903  mov     rbx, [rsp+58h+arg_8]
0x18001a908  mov     rsi, [rsp+58h+arg_10]
0x18001a90d  add     rsp, 50h
0x18001a911  pop     rdi
0x18001a912  retn
```
