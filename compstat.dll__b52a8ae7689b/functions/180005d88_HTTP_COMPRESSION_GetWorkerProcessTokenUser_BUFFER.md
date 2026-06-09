# HTTP_COMPRESSION::GetWorkerProcessTokenUser(BUFFER *)

- ea: `0x180005d88`
- end: `0x180005ea6`
- name: `?GetWorkerProcessTokenUser@HTTP_COMPRESSION@@CAJPEAVBUFFER@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(struct BUFFER *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004180`

## callees

- `0x180005d88`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180005dbd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180005dbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005daa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005daa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005dc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e32`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180005e28`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180005e28`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005de3`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005e67`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005de3`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180005e67`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180005dee`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180005e72`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180005dee`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180005e72`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005e0c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005e92`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005e0c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180005e92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e4c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e4c`

## pseudocode

```c
__int64 __fastcall HTTP_COMPRESSION::GetWorkerProcessTokenUser(struct BUFFER *a1)
{
  HANDLE CurrentProcess; // rax
  signed int v3; // eax
  unsigned int v4; // edi
  DWORD Size; // ebx
  void *Ptr; // rax
  signed int LastError; // eax
  DWORD v9; // ebx
  void *v10; // rax
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  ReturnLength = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    v4 = 0;
    Size = BUFFER::QuerySize(a1);
    Ptr = BUFFER::QueryPtr(a1);
    if ( !GetTokenInformation(TokenHandle, TokenUser, Ptr, Size, &ReturnLength) )
    {
      LastError = GetLastError();
      if ( LastError == 122 )
      {
        if ( BUFFER::Resize(a1, ReturnLength) )
        {
          v9 = BUFFER::QuerySize(a1);
          v10 = BUFFER::QueryPtr(a1);
          if ( GetTokenInformation(TokenHandle, TokenUser, v10, v9, &ReturnLength) )
            goto LABEL_9;
        }
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError <= 0 )
          goto LABEL_9;
      }
      else if ( LastError <= 0 )
      {
        v4 = LastError;
        goto LABEL_9;
      }
      v4 = (unsigned __int16)LastError | 0x80070000;
    }
LABEL_9:
    CloseHandle(TokenHandle);
    return v4;
  }
  v3 = GetLastError();
  v4 = v3;
  if ( v3 > 0 )
    return (unsigned __int16)v3 | 0x80070000;
  return v4;
}

```

## disassembly

```asm
0x180005d88  mov     rax, rsp
0x180005d8b  mov     [rax+8], rbx
0x180005d8f  mov     [rax+20h], rsi
0x180005d93  push    rdi
0x180005d94  sub     rsp, 30h
0x180005d98  mov     rsi, rcx
0x180005d9b  mov     dword ptr [rax+10h], 0
0x180005da2  mov     qword ptr [rax+18h], 0
0x180005daa  call    cs:__imp_GetCurrentProcess
0x180005db0  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180005db5  mov     edx, 8; DesiredAccess
0x180005dba  mov     rcx, rax; ProcessHandle
0x180005dbd  call    cs:__imp_OpenProcessToken
0x180005dc3  test    eax, eax
0x180005dc5  jnz     short loc_180005DDE
0x180005dc7  call    cs:__imp_GetLastError
0x180005dcd  mov     edi, eax
0x180005dcf  test    eax, eax
0x180005dd1  jle     short loc_180005E52
0x180005dd3  movzx   edi, ax
0x180005dd6  or      edi, 80070000h
0x180005ddc  jmp     short loc_180005E52
0x180005dde  mov     rcx, rsi
0x180005de1  xor     edi, edi
0x180005de3  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180005de9  mov     rcx, rsi
0x180005dec  mov     ebx, eax
0x180005dee  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180005df4  lea     rcx, [rsp+38h+arg_8]
0x180005df9  mov     r9d, ebx; TokenInformationLength
0x180005dfc  mov     [rsp+38h+ReturnLength], rcx; ReturnLength
0x180005e01  lea     edx, [rdi+1]; TokenInformationClass
0x180005e04  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180005e09  mov     r8, rax; TokenInformation
0x180005e0c  call    cs:__imp_GetTokenInformation
0x180005e12  test    eax, eax
0x180005e14  jnz     short loc_180005E47
0x180005e16  call    cs:__imp_GetLastError
0x180005e1c  cmp     eax, 7Ah ; 'z'
0x180005e1f  jnz     short loc_180005E9E
0x180005e21  mov     edx, [rsp+38h+arg_8]
0x180005e25  mov     rcx, rsi
0x180005e28  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180005e2e  test    al, al
0x180005e30  jnz     short loc_180005E64
0x180005e32  call    cs:__imp_GetLastError
0x180005e38  mov     edi, eax
0x180005e3a  test    eax, eax
0x180005e3c  jle     short loc_180005E47
0x180005e3e  movzx   edi, ax
0x180005e41  or      edi, 80070000h
0x180005e47  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180005e4c  call    cs:__imp_CloseHandle
0x180005e52  mov     rbx, [rsp+38h+arg_0]
0x180005e57  mov     eax, edi
0x180005e59  mov     rsi, [rsp+38h+arg_18]
0x180005e5e  add     rsp, 30h
0x180005e62  pop     rdi
0x180005e63  retn
0x180005e64  mov     rcx, rsi
0x180005e67  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180005e6d  mov     rcx, rsi
0x180005e70  mov     ebx, eax
0x180005e72  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180005e78  lea     rcx, [rsp+38h+arg_8]
0x180005e7d  mov     r9d, ebx; TokenInformationLength
0x180005e80  mov     [rsp+38h+ReturnLength], rcx; ReturnLength
0x180005e85  mov     r8, rax; TokenInformation
0x180005e88  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180005e8d  mov     edx, 1; TokenInformationClass
0x180005e92  call    cs:__imp_GetTokenInformation
0x180005e98  test    eax, eax
0x180005e9a  jnz     short loc_180005E47
0x180005e9c  jmp     short loc_180005E32
0x180005e9e  test    eax, eax
0x180005ea0  jg      short loc_180005E3E
0x180005ea2  mov     edi, eax
0x180005ea4  jmp     short loc_180005E47
```
