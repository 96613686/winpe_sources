# wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)

- ea: `0x180099ce8`
- end: `0x180099d60`
- name: `?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z`
- size: `120`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18001249c`
- `0x1800f5088`

## callees

- `0x180099ce8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180099d29`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180099d29`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180099d3a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180099d3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180099cf1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180099cf1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180099d06`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180099d06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099d10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099d48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099d10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099d48`

## pseudocode

```c
signed int __fastcall wil::open_current_access_token_nothrow(void **a1)
{
  HANDLE CurrentThread; // rax
  signed int result; // eax
  HANDLE CurrentProcess; // rax

  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, a1) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, a1) )
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
0x180099ce8  push    rbx
0x180099cea  sub     rsp, 20h
0x180099cee  mov     rbx, rcx
0x180099cf1  call    cs:__imp_GetCurrentThread
0x180099cf7  mov     edx, 8; DesiredAccess
0x180099cfc  mov     r9, rbx; TokenHandle
0x180099cff  mov     rcx, rax; ThreadHandle
0x180099d02  lea     r8d, [rdx-7]; OpenAsSelf
0x180099d06  call    cs:__imp_OpenThreadToken
0x180099d0c  test    eax, eax
0x180099d0e  jnz     short loc_180099D44
0x180099d10  call    cs:__imp_GetLastError
0x180099d16  test    eax, eax
0x180099d18  jle     short loc_180099D22
0x180099d1a  movzx   eax, ax
0x180099d1d  or      eax, 80070000h
0x180099d22  cmp     eax, 800703F0h
0x180099d27  jnz     short loc_180099D5A
0x180099d29  call    cs:__imp_GetCurrentProcess
0x180099d2f  mov     r8, rbx; TokenHandle
0x180099d32  mov     edx, 8; DesiredAccess
0x180099d37  mov     rcx, rax; ProcessHandle
0x180099d3a  call    cs:__imp_OpenProcessToken
0x180099d40  test    eax, eax
0x180099d42  jz      short loc_180099D48
0x180099d44  xor     eax, eax
0x180099d46  jmp     short loc_180099D5A
0x180099d48  call    cs:__imp_GetLastError
0x180099d4e  test    eax, eax
0x180099d50  jle     short loc_180099D5A
0x180099d52  movzx   eax, ax
0x180099d55  or      eax, 80070000h
0x180099d5a  add     rsp, 20h
0x180099d5e  pop     rbx
0x180099d5f  retn
```
