# V2StartWinnat(void)

- ea: `0x18003f650`
- end: `0x18003f72c`
- name: `?V2StartWinnat@@YAKXZ`
- size: `220`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18004a6e0`

## callees

- `0x18003f650`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f67f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f6b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f6dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f67f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f6b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f6dd`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003f66b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003f66b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003f6f9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003f70d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003f6f9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003f70d`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18003f6cd`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18003f6cd`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003f69f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003f69f`

## pseudocode

```c
__int64 V2StartWinnat(void)
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  DWORD LastError; // ebx
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rdi

  v0 = OpenSCManagerW(0, 0, 0x10u);
  v1 = v0;
  if ( v0 )
  {
    v3 = OpenServiceW(v0, L"winnat", 0x10u);
    v4 = v3;
    if ( v3 )
    {
      LastError = 0;
      if ( !StartServiceW(v3, 0, 0) )
      {
        LastError = GetLastError();
        if ( LastError == 1056 )
          LastError = 0;
      }
    }
    else
    {
      LastError = GetLastError();
    }
    CloseServiceHandle(v1);
    if ( v4 )
      CloseServiceHandle(v4);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x18003f650  mov     [rsp+arg_0], rbx
0x18003f655  mov     [rsp+arg_8], rsi
0x18003f65a  push    rdi
0x18003f65b  sub     rsp, 20h
0x18003f65f  mov     ebx, 10h
0x18003f664  xor     edx, edx; lpDatabaseName
0x18003f666  mov     r8d, ebx; dwDesiredAccess
0x18003f669  xor     ecx, ecx; lpMachineName
0x18003f66b  call    cs:__imp_OpenSCManagerW
0x18003f672  nop     dword ptr [rax+rax+00h]
0x18003f677  mov     rsi, rax
0x18003f67a  test    rax, rax
0x18003f67d  jnz     short loc_18003F692
0x18003f67f  call    cs:__imp_GetLastError
0x18003f686  nop     dword ptr [rax+rax+00h]
0x18003f68b  mov     ebx, eax
0x18003f68d  jmp     loc_18003F719
0x18003f692  mov     r8d, ebx; dwDesiredAccess
0x18003f695  lea     rdx, ServiceName; "winnat"
0x18003f69c  mov     rcx, rsi; hSCManager
0x18003f69f  call    cs:__imp_OpenServiceW
0x18003f6a6  nop     dword ptr [rax+rax+00h]
0x18003f6ab  mov     rdi, rax
0x18003f6ae  test    rax, rax
0x18003f6b1  jnz     short loc_18003F6C3
0x18003f6b3  call    cs:__imp_GetLastError
0x18003f6ba  nop     dword ptr [rax+rax+00h]
0x18003f6bf  mov     ebx, eax
0x18003f6c1  jmp     short loc_18003F6F6
0x18003f6c3  xor     r8d, r8d; lpServiceArgVectors
0x18003f6c6  xor     edx, edx; dwNumServiceArgs
0x18003f6c8  mov     rcx, rdi; hService
0x18003f6cb  xor     ebx, ebx
0x18003f6cd  call    cs:__imp_StartServiceW
0x18003f6d4  nop     dword ptr [rax+rax+00h]
0x18003f6d9  test    eax, eax
0x18003f6db  jnz     short loc_18003F6F6
0x18003f6dd  call    cs:__imp_GetLastError
0x18003f6e4  nop     dword ptr [rax+rax+00h]
0x18003f6e9  mov     ebx, eax
0x18003f6eb  xor     eax, eax
0x18003f6ed  cmp     ebx, 420h
0x18003f6f3  cmovz   ebx, eax
0x18003f6f6  mov     rcx, rsi; hSCObject
0x18003f6f9  call    cs:__imp_CloseServiceHandle
0x18003f700  nop     dword ptr [rax+rax+00h]
0x18003f705  test    rdi, rdi
0x18003f708  jz      short loc_18003F719
0x18003f70a  mov     rcx, rdi; hSCObject
0x18003f70d  call    cs:__imp_CloseServiceHandle
0x18003f714  nop     dword ptr [rax+rax+00h]
0x18003f719  mov     rsi, [rsp+28h+arg_8]
0x18003f71e  mov     eax, ebx
0x18003f720  mov     rbx, [rsp+28h+arg_0]
0x18003f725  add     rsp, 20h
0x18003f729  pop     rdi
0x18003f72a  retn
```
