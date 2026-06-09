# CscSec_OpenToken(ulong,void * *)

- ea: `0x180033250`
- end: `0x1800332d2`
- name: `?CscSec_OpenToken@@YAJKPEAPEAX@Z`
- size: `130`
- prototype: `__int64 __fastcall(DWORD DesiredAccess, PHANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180032bd8`
- `0x18005cb84`

## callees

- `0x18002f10c`
- `0x180033250`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033285`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033285`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180033269`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180033269`
- `KERNEL32!GetCurrentProcess` at `0x180033292`
- `KERNEL32!GetCurrentProcess` at `0x180033292`
- `ADVAPI32!OpenProcessToken` at `0x1800332a0`
- `ADVAPI32!OpenProcessToken` at `0x1800332a0`
- `ADVAPI32!OpenThreadToken` at `0x18003327b`
- `ADVAPI32!OpenThreadToken` at `0x18003327b`

## pseudocode

```c
__int64 __fastcall CscSec_OpenToken(DWORD DesiredAccess, PHANDLE TokenHandle)
{
  unsigned int v2; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax

  v2 = 0;
  *TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, DesiredAccess, 1, TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
    {
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      return (unsigned int)LastError;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, DesiredAccess, TokenHandle) )
      return (unsigned int)ResultFromLastError();
  }
  return v2;
}

```

## disassembly

```asm
0x180033250  mov     [rsp+arg_0], rbx
0x180033255  mov     [rsp+arg_8], rsi
0x18003325a  push    rdi
0x18003325b  sub     rsp, 20h
0x18003325f  xor     ebx, ebx
0x180033261  mov     rdi, rdx
0x180033264  mov     [rdx], rbx
0x180033267  mov     esi, ecx
0x180033269  call    cs:__imp_GetCurrentThread
0x18003326f  mov     r9, rdi; TokenHandle
0x180033272  lea     r8d, [rbx+1]; OpenAsSelf
0x180033276  mov     rcx, rax; ThreadHandle
0x180033279  mov     edx, esi; DesiredAccess
0x18003327b  call    cs:__imp_OpenThreadToken
0x180033281  test    eax, eax
0x180033283  jnz     short loc_1800332C0
0x180033285  call    cs:__imp_GetLastError
0x18003328b  cmp     eax, 3F0h
0x180033290  jnz     short loc_1800332B3
0x180033292  call    cs:__imp_GetCurrentProcess
0x180033298  mov     r8, rdi; TokenHandle
0x18003329b  mov     edx, esi; DesiredAccess
0x18003329d  mov     rcx, rax; ProcessHandle
0x1800332a0  call    cs:__imp_OpenProcessToken
0x1800332a6  test    eax, eax
0x1800332a8  jnz     short loc_1800332C0
0x1800332aa  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800332af  mov     ebx, eax
0x1800332b1  jmp     short loc_1800332C0
0x1800332b3  test    eax, eax
0x1800332b5  jle     short loc_1800332AF
0x1800332b7  movzx   ebx, ax
0x1800332ba  or      ebx, 80070000h
0x1800332c0  mov     rsi, [rsp+28h+arg_8]
0x1800332c5  mov     eax, ebx
0x1800332c7  mov     rbx, [rsp+28h+arg_0]
0x1800332cc  add     rsp, 20h
0x1800332d0  pop     rdi
0x1800332d1  retn
```
