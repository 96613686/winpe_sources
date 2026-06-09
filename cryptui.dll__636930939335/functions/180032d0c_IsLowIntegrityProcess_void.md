# IsLowIntegrityProcess(void)

- ea: `0x180032d0c`
- end: `0x180032e09`
- name: `?IsLowIntegrityProcess@@YA_NXZ`
- size: `253`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800323e0`

## callees

- `0x180032d0c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032d8b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032d8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032df3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032df3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d7a`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180032dc7`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180032dc7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180032d70`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180032db5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180032d70`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180032db5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180032d46`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180032d46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180032d35`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180032d35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032de5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032de5`

## pseudocode

```c
bool IsLowIntegrityProcess(void)
{
  bool v0; // zf
  PSID *v1; // rbx
  HANDLE CurrentProcess; // rax
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  if ( dword_1800502BC == -1 )
  {
    v1 = 0;
    TokenHandle = 0;
    dword_1800502BC = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x18u, &TokenHandle) )
    {
      TokenInformationLength = 0;
      if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength)
        && GetLastError() == 122 )
      {
        v1 = (PSID *)LocalAlloc(0, TokenInformationLength);
        if ( v1 )
        {
          if ( GetTokenInformation(
                 TokenHandle,
                 TokenIntegrityLevel,
                 v1,
                 TokenInformationLength,
                 &TokenInformationLength)
            && IsWellKnownSid(*v1, WinLowLabelSid) )
          {
            dword_1800502BC = 1;
          }
        }
      }
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    if ( v1 )
      LocalFree(v1);
    v0 = dword_1800502BC == 0;
  }
  else
  {
    v0 = dword_1800502BC == 0;
  }
  return !v0;
}

```

## disassembly

```asm
0x180032d0c  push    rbx
0x180032d0e  sub     rsp, 30h
0x180032d12  mov     eax, cs:dword_1800502BC
0x180032d18  cmp     eax, 0FFFFFFFFh
0x180032d1b  jz      short loc_180032D24
0x180032d1d  test    eax, eax
0x180032d1f  jmp     loc_180032E00
0x180032d24  xor     ebx, ebx
0x180032d26  mov     [rsp+38h+TokenHandle], 0
0x180032d2f  mov     cs:dword_1800502BC, ebx
0x180032d35  call    cs:__imp_GetCurrentProcess
0x180032d3b  mov     rcx, rax; ProcessHandle
0x180032d3e  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180032d43  lea     edx, [rbx+18h]; DesiredAccess
0x180032d46  call    cs:__imp_OpenProcessToken
0x180032d4c  test    eax, eax
0x180032d4e  jz      loc_180032DDB
0x180032d54  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180032d59  lea     rax, [rsp+38h+TokenInformationLength]
0x180032d5e  xor     r9d, r9d; TokenInformationLength
0x180032d61  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180032d66  xor     r8d, r8d; TokenInformation
0x180032d69  mov     [rsp+38h+TokenInformationLength], ebx
0x180032d6d  lea     edx, [rbx+19h]; TokenInformationClass
0x180032d70  call    cs:__imp_GetTokenInformation
0x180032d76  test    eax, eax
0x180032d78  jnz     short loc_180032DDB
0x180032d7a  call    cs:__imp_GetLastError
0x180032d80  cmp     eax, 7Ah ; 'z'
0x180032d83  jnz     short loc_180032DDB
0x180032d85  mov     edx, [rsp+38h+TokenInformationLength]; uBytes
0x180032d89  xor     ecx, ecx; uFlags
0x180032d8b  call    cs:__imp_LocalAlloc
0x180032d91  mov     rbx, rax
0x180032d94  test    rax, rax
0x180032d97  jz      short loc_180032DDB
0x180032d99  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180032d9e  lea     rax, [rsp+38h+TokenInformationLength]
0x180032da3  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180032da8  mov     r8, rbx; TokenInformation
0x180032dab  mov     edx, 19h; TokenInformationClass
0x180032db0  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180032db5  call    cs:__imp_GetTokenInformation
0x180032dbb  test    eax, eax
0x180032dbd  jz      short loc_180032DDB
0x180032dbf  mov     rcx, [rbx]; pSid
0x180032dc2  mov     edx, 42h ; 'B'; WellKnownSidType
0x180032dc7  call    cs:__imp_IsWellKnownSid
0x180032dcd  test    eax, eax
0x180032dcf  jz      short loc_180032DDB
0x180032dd1  mov     cs:dword_1800502BC, 1
0x180032ddb  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180032de0  test    rcx, rcx
0x180032de3  jz      short loc_180032DEB
0x180032de5  call    cs:__imp_CloseHandle
0x180032deb  test    rbx, rbx
0x180032dee  jz      short loc_180032DF9
0x180032df0  mov     rcx, rbx; hMem
0x180032df3  call    cs:__imp_LocalFree
0x180032df9  cmp     cs:dword_1800502BC, 0
0x180032e00  setnz   al
0x180032e03  add     rsp, 30h
0x180032e07  pop     rbx
0x180032e08  retn
```
