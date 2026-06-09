# wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)

- ea: `0x180165b7c`
- end: `0x180165bf4`
- name: `?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z`
- size: `120`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180163630`
- `0x1801638e0`
- `0x180164780`
- `0x180164900`

## callees

- `0x180165b7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180165ba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180165bdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180165ba4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180165bdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180165bbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180165bbd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180165bce`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180165bce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180165b85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180165b85`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180165b9a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180165b9a`

## pseudocode

```c
signed int __fastcall wil::open_current_access_token_nothrow(void **a1)
{
  HANDLE CurrentThread; // rax
  signed int result; // eax
  HANDLE CurrentProcess; // rax

  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xEu, 1, a1) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0xEu, a1) )
      return 0;
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180165b7c  push    rbx
0x180165b7e  sub     rsp, 20h
0x180165b82  mov     rbx, rcx
0x180165b85  call    cs:__imp_GetCurrentThread
0x180165b8b  mov     edx, 0Eh; DesiredAccess
0x180165b90  mov     r9, rbx; TokenHandle
0x180165b93  mov     rcx, rax; ThreadHandle
0x180165b96  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x180165b9a  call    cs:__imp_OpenThreadToken
0x180165ba0  test    eax, eax
0x180165ba2  jnz     short loc_180165BD8
0x180165ba4  call    cs:__imp_GetLastError
0x180165baa  test    eax, eax
0x180165bac  jle     short loc_180165BB6
0x180165bae  movzx   eax, ax
0x180165bb1  or      eax, 80070000h
0x180165bb6  cmp     eax, 800703F0h
0x180165bbb  jnz     short loc_180165BEE
0x180165bbd  call    cs:__imp_GetCurrentProcess
0x180165bc3  mov     r8, rbx; TokenHandle
0x180165bc6  mov     edx, 0Eh; DesiredAccess
0x180165bcb  mov     rcx, rax; ProcessHandle
0x180165bce  call    cs:__imp_OpenProcessToken
0x180165bd4  test    eax, eax
0x180165bd6  jz      short loc_180165BDC
0x180165bd8  xor     eax, eax
0x180165bda  jmp     short loc_180165BEE
0x180165bdc  call    cs:__imp_GetLastError
0x180165be2  test    eax, eax
0x180165be4  jle     short loc_180165BEE
0x180165be6  movzx   eax, ax
0x180165be9  or      eax, 80070000h
0x180165bee  add     rsp, 20h
0x180165bf2  pop     rbx
0x180165bf3  retn
```
