# V2StartWinnat(void)

- ea: `0x18003c44c`
- end: `0x18003c4f4`
- name: `?V2StartWinnat@@YAKXZ`
- size: `168`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180046c40`

## callees

- `0x18003c44c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c49a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c4b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c49a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c4b8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003c467`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003c467`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003c4ce`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003c4dc`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003c4ce`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003c4dc`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18003c4ae`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18003c4ae`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003c48c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003c48c`

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
0x18003c44c  mov     [rsp+arg_0], rbx
0x18003c451  mov     [rsp+arg_8], rsi
0x18003c456  push    rdi
0x18003c457  sub     rsp, 20h
0x18003c45b  mov     ebx, 10h
0x18003c460  xor     edx, edx; lpDatabaseName
0x18003c462  mov     r8d, ebx; dwDesiredAccess
0x18003c465  xor     ecx, ecx; lpMachineName
0x18003c467  call    cs:__imp_OpenSCManagerW
0x18003c46d  mov     rsi, rax
0x18003c470  test    rax, rax
0x18003c473  jnz     short loc_18003C47F
0x18003c475  call    cs:__imp_GetLastError
0x18003c47b  mov     ebx, eax
0x18003c47d  jmp     short loc_18003C4E2
0x18003c47f  mov     r8d, ebx; dwDesiredAccess
0x18003c482  lea     rdx, ServiceName; "winnat"
0x18003c489  mov     rcx, rsi; hSCManager
0x18003c48c  call    cs:__imp_OpenServiceW
0x18003c492  mov     rdi, rax
0x18003c495  test    rax, rax
0x18003c498  jnz     short loc_18003C4A4
0x18003c49a  call    cs:__imp_GetLastError
0x18003c4a0  mov     ebx, eax
0x18003c4a2  jmp     short loc_18003C4CB
0x18003c4a4  xor     r8d, r8d; lpServiceArgVectors
0x18003c4a7  xor     edx, edx; dwNumServiceArgs
0x18003c4a9  mov     rcx, rdi; hService
0x18003c4ac  xor     ebx, ebx
0x18003c4ae  call    cs:__imp_StartServiceW
0x18003c4b4  test    eax, eax
0x18003c4b6  jnz     short loc_18003C4CB
0x18003c4b8  call    cs:__imp_GetLastError
0x18003c4be  mov     ebx, eax
0x18003c4c0  xor     eax, eax
0x18003c4c2  cmp     ebx, 420h
0x18003c4c8  cmovz   ebx, eax
0x18003c4cb  mov     rcx, rsi; hSCObject
0x18003c4ce  call    cs:__imp_CloseServiceHandle
0x18003c4d4  test    rdi, rdi
0x18003c4d7  jz      short loc_18003C4E2
0x18003c4d9  mov     rcx, rdi; hSCObject
0x18003c4dc  call    cs:__imp_CloseServiceHandle
0x18003c4e2  mov     rsi, [rsp+28h+arg_8]
0x18003c4e7  mov     eax, ebx
0x18003c4e9  mov     rbx, [rsp+28h+arg_0]
0x18003c4ee  add     rsp, 20h
0x18003c4f2  pop     rdi
0x18003c4f3  retn
```
