# wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)

- ea: `0x1400636b0`
- end: `0x140063726`
- name: `?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140063080`

## callees

- `0x1400636b0`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x1400636b9`
- `KERNEL32!GetCurrentThread` at `0x1400636b9`
- `KERNEL32!GetCurrentProcess` at `0x1400636ef`
- `KERNEL32!GetCurrentProcess` at `0x1400636ef`
- `KERNEL32!GetLastError` at `0x1400636d6`
- `KERNEL32!GetLastError` at `0x14006370e`
- `KERNEL32!GetLastError` at `0x1400636d6`
- `KERNEL32!GetLastError` at `0x14006370e`
- `ADVAPI32!OpenProcessToken` at `0x140063700`
- `ADVAPI32!OpenProcessToken` at `0x140063700`
- `ADVAPI32!OpenThreadToken` at `0x1400636cc`
- `ADVAPI32!OpenThreadToken` at `0x1400636cc`

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
0x1400636b0  push    rbx
0x1400636b2  sub     rsp, 20h
0x1400636b6  mov     rbx, rcx
0x1400636b9  call    cs:__imp_GetCurrentThread
0x1400636bf  xor     r8d, r8d; OpenAsSelf
0x1400636c2  mov     r9, rbx; TokenHandle
0x1400636c5  mov     rcx, rax; ThreadHandle
0x1400636c8  lea     edx, [r8+20h]; DesiredAccess
0x1400636cc  call    cs:__imp_OpenThreadToken
0x1400636d2  test    eax, eax
0x1400636d4  jnz     short loc_14006370A
0x1400636d6  call    cs:__imp_GetLastError
0x1400636dc  test    eax, eax
0x1400636de  jle     short loc_1400636E8
0x1400636e0  movzx   eax, ax
0x1400636e3  or      eax, 80070000h
0x1400636e8  cmp     eax, 800703F0h
0x1400636ed  jnz     short loc_140063720
0x1400636ef  call    cs:__imp_GetCurrentProcess
0x1400636f5  mov     r8, rbx; TokenHandle
0x1400636f8  mov     edx, 20h ; ' '; DesiredAccess
0x1400636fd  mov     rcx, rax; ProcessHandle
0x140063700  call    cs:__imp_OpenProcessToken
0x140063706  test    eax, eax
0x140063708  jz      short loc_14006370E
0x14006370a  xor     eax, eax
0x14006370c  jmp     short loc_140063720
0x14006370e  call    cs:__imp_GetLastError
0x140063714  test    eax, eax
0x140063716  jle     short loc_140063720
0x140063718  movzx   eax, ax
0x14006371b  or      eax, 80070000h
0x140063720  add     rsp, 20h
0x140063724  pop     rbx
0x140063725  retn
```
