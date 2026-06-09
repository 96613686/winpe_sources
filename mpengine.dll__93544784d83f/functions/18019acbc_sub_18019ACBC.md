# sub_18019ACBC

- ea: `0x18019acbc`
- end: `0x18019ad7a`
- name: `sub_18019ACBC`
- size: `190`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180199d04`

## callees

- `0x18019acbc`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18019ad3c`
- `KERNEL32!CreateFileW` at `0x18019ad3c`
- `KERNEL32!CloseHandle` at `0x18019ad11`
- `KERNEL32!CloseHandle` at `0x18019ad11`
- `KERNEL32!GetLastError` at `0x18019acf9`
- `KERNEL32!GetLastError` at `0x18019acf9`
- `KERNEL32!WriteConsoleW` at `0x18019aced`
- `KERNEL32!WriteConsoleW` at `0x18019ad5b`
- `KERNEL32!WriteConsoleW` at `0x18019aced`
- `KERNEL32!WriteConsoleW` at `0x18019ad5b`

## pseudocode

```c
__int64 __fastcall sub_18019ACBC(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)
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
0x18019acbc  mov     rax, rsp
0x18019acbf  mov     [rax+8], rbx
0x18019acc3  mov     [rax+10h], rbp
0x18019acc7  mov     [rax+18h], rsi
0x18019accb  push    rdi
0x18019accc  sub     rsp, 40h
0x18019acd0  and     qword ptr [rax-28h], 0
0x18019acd5  mov     rdi, r8
0x18019acd8  mov     r9, r8; lpNumberOfCharsWritten
0x18019acdb  mov     esi, edx
0x18019acdd  mov     r8d, edx; nNumberOfCharsToWrite
0x18019ace0  mov     rbp, rcx
0x18019ace3  mov     rdx, rcx; lpBuffer
0x18019ace6  mov     rcx, cs:hObject; hConsoleOutput
0x18019aced  call    cs:WriteConsoleW
0x18019acf3  mov     ebx, eax
0x18019acf5  test    eax, eax
0x18019acf7  jnz     short loc_18019AD63
0x18019acf9  call    cs:__imp_GetLastError
0x18019acff  cmp     eax, 6
0x18019ad02  jnz     short loc_18019AD63
0x18019ad04  mov     rcx, cs:hObject; hObject
0x18019ad0b  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18019ad0f  ja      short loc_18019AD17
0x18019ad11  call    cs:__imp_CloseHandle
0x18019ad17  and     [rsp+48h+var_18], 0
0x18019ad1d  lea     rcx, FileName; "CONOUT$"
0x18019ad24  and     [rsp+48h+var_20], 0
0x18019ad29  mov     r8d, 3; dwShareMode
0x18019ad2f  xor     r9d, r9d; lpSecurityAttributes
0x18019ad32  mov     [rsp+48h+dwCreationDisposition], r8d; lpReserved
0x18019ad37  mov     edx, 40000000h; dwDesiredAccess
0x18019ad3c  call    cs:__imp_CreateFileW
0x18019ad42  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x18019ad48  mov     r9, rdi; lpNumberOfCharsWritten
0x18019ad4b  mov     rcx, rax; hConsoleOutput
0x18019ad4e  mov     cs:hObject, rax
0x18019ad55  mov     r8d, esi; nNumberOfCharsToWrite
0x18019ad58  mov     rdx, rbp; lpBuffer
0x18019ad5b  call    cs:WriteConsoleW
0x18019ad61  mov     ebx, eax
0x18019ad63  mov     rbp, [rsp+48h+arg_8]
0x18019ad68  mov     eax, ebx
0x18019ad6a  mov     rbx, [rsp+48h+arg_0]
0x18019ad6f  mov     rsi, [rsp+48h+arg_10]
0x18019ad74  add     rsp, 40h
0x18019ad78  pop     rdi
0x18019ad79  retn
```
