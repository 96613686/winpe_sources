# __dcrt_write_console

- ea: `0x18013b00c`
- end: `0x18013b0ca`
- name: `__dcrt_write_console`
- size: `190`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180136078`

## callees

- `0x18013b00c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18013b049`
- `KERNEL32!GetLastError` at `0x18013b049`
- `KERNEL32!CreateFileW` at `0x18013b08c`
- `KERNEL32!CreateFileW` at `0x18013b08c`
- `KERNEL32!CloseHandle` at `0x18013b061`
- `KERNEL32!CloseHandle` at `0x18013b061`
- `KERNEL32!WriteConsoleW` at `0x18013b03d`
- `KERNEL32!WriteConsoleW` at `0x18013b0ab`
- `KERNEL32!WriteConsoleW` at `0x18013b03d`
- `KERNEL32!WriteConsoleW` at `0x18013b0ab`

## pseudocode

```c
__int64 __fastcall _dcrt_write_console(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)
{
  unsigned int v6; // ebx

  v6 = WriteConsoleW(hConsoleOutput, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, 0);
  if ( !v6 && GetLastError() == 6 )
  {
    if ( (unsigned __int64)hConsoleOutput <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(hConsoleOutput);
    hConsoleOutput = CreateFileW(L"CONOUT$", 0x40000000u, 3u, 0, 3u, 0, 0);
    return WriteConsoleW(hConsoleOutput, lpBuffer, nNumberOfCharsToWrite, lpNumberOfCharsWritten, 0);
  }
  return v6;
}

```

## disassembly

```asm
0x18013b00c  mov     rax, rsp
0x18013b00f  mov     [rax+8], rbx
0x18013b013  mov     [rax+10h], rbp
0x18013b017  mov     [rax+18h], rsi
0x18013b01b  push    rdi
0x18013b01c  sub     rsp, 40h
0x18013b020  and     qword ptr [rax-28h], 0
0x18013b025  mov     rdi, r8
0x18013b028  mov     r9, r8; lpNumberOfCharsWritten
0x18013b02b  mov     esi, edx
0x18013b02d  mov     r8d, edx; nNumberOfCharsToWrite
0x18013b030  mov     rbp, rcx
0x18013b033  mov     rdx, rcx; lpBuffer
0x18013b036  mov     rcx, cs:hConsoleOutput; hConsoleOutput
0x18013b03d  call    cs:__imp_WriteConsoleW
0x18013b043  mov     ebx, eax
0x18013b045  test    eax, eax
0x18013b047  jnz     short loc_18013B0B3
0x18013b049  call    cs:__imp_GetLastError
0x18013b04f  cmp     eax, 6
0x18013b052  jnz     short loc_18013B0B3
0x18013b054  mov     rcx, cs:hConsoleOutput; hObject
0x18013b05b  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18013b05f  ja      short loc_18013B067
0x18013b061  call    cs:__imp_CloseHandle
0x18013b067  and     [rsp+48h+var_18], 0
0x18013b06d  lea     rcx, aConout; "CONOUT$"
0x18013b074  and     [rsp+48h+var_20], 0
0x18013b079  mov     r8d, 3; dwShareMode
0x18013b07f  xor     r9d, r9d; lpSecurityAttributes
0x18013b082  mov     [rsp+48h+dwCreationDisposition], r8d; lpReserved
0x18013b087  mov     edx, 40000000h; dwDesiredAccess
0x18013b08c  call    cs:__imp_CreateFileW
0x18013b092  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x18013b098  mov     r9, rdi; lpNumberOfCharsWritten
0x18013b09b  mov     rcx, rax; hConsoleOutput
0x18013b09e  mov     cs:hConsoleOutput, rax
0x18013b0a5  mov     r8d, esi; nNumberOfCharsToWrite
0x18013b0a8  mov     rdx, rbp; lpBuffer
0x18013b0ab  call    cs:__imp_WriteConsoleW
0x18013b0b1  mov     ebx, eax
0x18013b0b3  mov     rbp, [rsp+48h+arg_8]
0x18013b0b8  mov     eax, ebx
0x18013b0ba  mov     rbx, [rsp+48h+arg_0]
0x18013b0bf  mov     rsi, [rsp+48h+arg_10]
0x18013b0c4  add     rsp, 40h
0x18013b0c8  pop     rdi
0x18013b0c9  retn
```
