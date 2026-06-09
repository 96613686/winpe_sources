# __dcrt_write_console

- ea: `0x180365ffc`
- end: `0x1803660ba`
- name: `__dcrt_write_console`
- size: `190`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18036484c`

## callees

- `0x180365ffc`

## import_xrefs

- `KERNEL32!WriteConsoleW` at `0x18036602d`
- `KERNEL32!WriteConsoleW` at `0x18036609b`
- `KERNEL32!WriteConsoleW` at `0x18036602d`
- `KERNEL32!WriteConsoleW` at `0x18036609b`
- `KERNEL32!CloseHandle` at `0x180366051`
- `KERNEL32!CloseHandle` at `0x180366051`
- `KERNEL32!GetLastError` at `0x180366039`
- `KERNEL32!GetLastError` at `0x180366039`
- `KERNEL32!CreateFileW` at `0x18036607c`
- `KERNEL32!CreateFileW` at `0x18036607c`

## pseudocode

```c
__int64 __fastcall _dcrt_write_console(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)
{
  unsigned int v6; // ebx

  v6 = WriteConsoleW(hObject, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, 0);
  if ( !v6 && GetLastError() == 6 )
  {
    if ( (unsigned __int64)hObject <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hObject);
    hObject = CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
    return WriteConsoleW(hObject, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, 0);
  }
  return v6;
}

```

## disassembly

```asm
0x180365ffc  mov     rax, rsp
0x180365fff  mov     [rax+8], rbx
0x180366003  mov     [rax+10h], rbp
0x180366007  mov     [rax+18h], rsi
0x18036600b  push    rdi
0x18036600c  sub     rsp, 40h
0x180366010  and     qword ptr [rax-28h], 0
0x180366015  mov     rdi, r8
0x180366018  mov     r9, r8; lpNumberOfCharsWritten
0x18036601b  mov     esi, edx
0x18036601d  mov     r8d, edx; nNumberOfCharsToWrite
0x180366020  mov     rbp, rcx
0x180366023  mov     rdx, rcx; lpBuffer
0x180366026  mov     rcx, cs:hObject; hConsoleOutput
0x18036602d  call    cs:__imp_WriteConsoleW
0x180366033  mov     ebx, eax
0x180366035  test    eax, eax
0x180366037  jnz     short loc_1803660A3
0x180366039  call    cs:__imp_GetLastError
0x18036603f  cmp     eax, 6
0x180366042  jnz     short loc_1803660A3
0x180366044  mov     rcx, cs:hObject; hObject
0x18036604b  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18036604f  ja      short loc_180366057
0x180366051  call    cs:__imp_CloseHandle
0x180366057  and     [rsp+48h+var_18], 0
0x18036605d  lea     rcx, aConout; "CONOUT$"
0x180366064  and     [rsp+48h+var_20], 0
0x180366069  mov     r8d, 3; dwShareMode
0x18036606f  xor     r9d, r9d; lpSecurityAttributes
0x180366072  mov     [rsp+48h+dwCreationDisposition], r8d; lpReserved
0x180366077  mov     edx, 40000000h; dwDesiredAccess
0x18036607c  call    cs:__imp_CreateFileW
0x180366082  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x180366088  mov     r9, rdi; lpNumberOfCharsWritten
0x18036608b  mov     rcx, rax; hConsoleOutput
0x18036608e  mov     cs:hObject, rax
0x180366095  mov     r8d, esi; nNumberOfCharsToWrite
0x180366098  mov     rdx, rbp; lpBuffer
0x18036609b  call    cs:__imp_WriteConsoleW
0x1803660a1  mov     ebx, eax
0x1803660a3  mov     rbp, [rsp+48h+arg_8]
0x1803660a8  mov     eax, ebx
0x1803660aa  mov     rbx, [rsp+48h+arg_0]
0x1803660af  mov     rsi, [rsp+48h+arg_10]
0x1803660b4  add     rsp, 40h
0x1803660b8  pop     rdi
0x1803660b9  retn
```
