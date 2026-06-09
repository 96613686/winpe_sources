# wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)

- ea: `0x140065820`
- end: `0x140065896`
- name: `?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400651f0`

## callees

- `0x140065820`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x140065829`
- `KERNEL32!GetCurrentThread` at `0x140065829`
- `KERNEL32!GetCurrentProcess` at `0x14006585f`
- `KERNEL32!GetCurrentProcess` at `0x14006585f`
- `KERNEL32!GetLastError` at `0x140065846`
- `KERNEL32!GetLastError` at `0x14006587e`
- `KERNEL32!GetLastError` at `0x140065846`
- `KERNEL32!GetLastError` at `0x14006587e`
- `ADVAPI32!OpenProcessToken` at `0x140065870`
- `ADVAPI32!OpenProcessToken` at `0x140065870`
- `ADVAPI32!OpenThreadToken` at `0x14006583c`
- `ADVAPI32!OpenThreadToken` at `0x14006583c`

## pseudocode

```c
signed int __fastcall wil::open_current_access_token_nothrow(void **a1)
{
  HANDLE CurrentThread; // rax
  signed int result; // eax
  HANDLE CurrentProcess; // rax

  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x20u, 0, a1) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x20u, a1) )
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
0x140065820  push    rbx
0x140065822  sub     rsp, 20h
0x140065826  mov     rbx, rcx
0x140065829  call    cs:__imp_GetCurrentThread
0x14006582f  xor     r8d, r8d; OpenAsSelf
0x140065832  mov     r9, rbx; TokenHandle
0x140065835  mov     rcx, rax; ThreadHandle
0x140065838  lea     edx, [r8+20h]; DesiredAccess
0x14006583c  call    cs:__imp_OpenThreadToken
0x140065842  test    eax, eax
0x140065844  jnz     short loc_14006587A
0x140065846  call    cs:__imp_GetLastError
0x14006584c  test    eax, eax
0x14006584e  jle     short loc_140065858
0x140065850  movzx   eax, ax
0x140065853  or      eax, 80070000h
0x140065858  cmp     eax, 800703F0h
0x14006585d  jnz     short loc_140065890
0x14006585f  call    cs:__imp_GetCurrentProcess
0x140065865  mov     r8, rbx; TokenHandle
0x140065868  mov     edx, 20h ; ' '; DesiredAccess
0x14006586d  mov     rcx, rax; ProcessHandle
0x140065870  call    cs:__imp_OpenProcessToken
0x140065876  test    eax, eax
0x140065878  jz      short loc_14006587E
0x14006587a  xor     eax, eax
0x14006587c  jmp     short loc_140065890
0x14006587e  call    cs:__imp_GetLastError
0x140065884  test    eax, eax
0x140065886  jle     short loc_140065890
0x140065888  movzx   eax, ax
0x14006588b  or      eax, 80070000h
0x140065890  add     rsp, 20h
0x140065894  pop     rbx
0x140065895  retn
```
