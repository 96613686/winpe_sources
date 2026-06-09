# wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)

- ea: `0x180048580`
- end: `0x18004861b`
- name: `?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18004619c`

## callees

- `0x180048580`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800485b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800485fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800485b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800485fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180048589`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180048589`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800485e8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800485e8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800485a2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800485a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800485d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800485d1`

## pseudocode

```c
signed int __fastcall wil::open_current_access_token_nothrow(void **a1)
{
  HANDLE CurrentThread; // rax
  signed int result; // eax
  HANDLE CurrentProcess; // rax

  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x28u, 0, a1) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x28u, a1) )
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
0x180048580  push    rbx
0x180048582  sub     rsp, 20h
0x180048586  mov     rbx, rcx
0x180048589  call    cs:__imp_GetCurrentThread
0x180048590  nop     dword ptr [rax+rax+00h]
0x180048595  xor     r8d, r8d; OpenAsSelf
0x180048598  mov     r9, rbx; TokenHandle
0x18004859b  mov     rcx, rax; ThreadHandle
0x18004859e  lea     edx, [r8+28h]; DesiredAccess
0x1800485a2  call    cs:__imp_OpenThreadToken
0x1800485a9  nop     dword ptr [rax+rax+00h]
0x1800485ae  test    eax, eax
0x1800485b0  jnz     short loc_1800485F8
0x1800485b2  call    cs:__imp_GetLastError
0x1800485b9  nop     dword ptr [rax+rax+00h]
0x1800485be  test    eax, eax
0x1800485c0  jle     short loc_1800485CA
0x1800485c2  movzx   eax, ax
0x1800485c5  or      eax, 80070000h
0x1800485ca  cmp     eax, 800703F0h
0x1800485cf  jnz     short loc_180048614
0x1800485d1  call    cs:__imp_GetCurrentProcess
0x1800485d8  nop     dword ptr [rax+rax+00h]
0x1800485dd  mov     r8, rbx; TokenHandle
0x1800485e0  mov     edx, 28h ; '('; DesiredAccess
0x1800485e5  mov     rcx, rax; ProcessHandle
0x1800485e8  call    cs:__imp_OpenProcessToken
0x1800485ef  nop     dword ptr [rax+rax+00h]
0x1800485f4  test    eax, eax
0x1800485f6  jz      short loc_1800485FC
0x1800485f8  xor     eax, eax
0x1800485fa  jmp     short loc_180048614
0x1800485fc  call    cs:__imp_GetLastError
0x180048603  nop     dword ptr [rax+rax+00h]
0x180048608  test    eax, eax
0x18004860a  jle     short loc_180048614
0x18004860c  movzx   eax, ax
0x18004860f  or      eax, 80070000h
0x180048614  add     rsp, 20h
0x180048618  pop     rbx
0x180048619  retn
```
