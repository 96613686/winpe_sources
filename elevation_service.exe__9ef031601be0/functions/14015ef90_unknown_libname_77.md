# unknown_libname_77

- ea: `0x14015ef90`
- end: `0x14015f04e`
- name: `unknown_libname_77`
- size: `190`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14015a5a0`

## callees

- `0x14015ef90`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14015efe5`
- `KERNEL32!CloseHandle` at `0x14015efe5`
- `KERNEL32!CreateFileW` at `0x14015f010`
- `KERNEL32!CreateFileW` at `0x14015f010`
- `KERNEL32!GetLastError` at `0x14015efcd`
- `KERNEL32!GetLastError` at `0x14015efcd`
- `KERNEL32!WriteConsoleW` at `0x14015efc1`
- `KERNEL32!WriteConsoleW` at `0x14015f02f`
- `KERNEL32!WriteConsoleW` at `0x14015efc1`
- `KERNEL32!WriteConsoleW` at `0x14015f02f`

## pseudocode

```c
// Microsoft VisualC 64bit universal runtime
__int64 __fastcall unknown_libname_77(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)
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
0x14015ef90  mov     rax, rsp
0x14015ef93  mov     [rax+8], rbx
0x14015ef97  mov     [rax+10h], rbp
0x14015ef9b  mov     [rax+18h], rsi
0x14015ef9f  push    rdi
0x14015efa0  sub     rsp, 40h
0x14015efa4  and     qword ptr [rax-28h], 0
0x14015efa9  mov     rdi, r8
0x14015efac  mov     r9, r8; lpNumberOfCharsWritten
0x14015efaf  mov     esi, edx
0x14015efb1  mov     r8d, edx; nNumberOfCharsToWrite
0x14015efb4  mov     rbp, rcx
0x14015efb7  mov     rdx, rcx; lpBuffer
0x14015efba  mov     rcx, cs:hObject; hConsoleOutput
0x14015efc1  call    cs:WriteConsoleW
0x14015efc7  mov     ebx, eax
0x14015efc9  test    eax, eax
0x14015efcb  jnz     short loc_14015F037
0x14015efcd  call    cs:__imp_GetLastError
0x14015efd3  cmp     eax, 6
0x14015efd6  jnz     short loc_14015F037
0x14015efd8  mov     rcx, cs:hObject; hObject
0x14015efdf  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14015efe3  ja      short loc_14015EFEB
0x14015efe5  call    cs:__imp_CloseHandle
0x14015efeb  and     [rsp+48h+var_18], 0
0x14015eff1  lea     rcx, FileName
0x14015eff8  and     [rsp+48h+var_20], 0
0x14015effd  mov     r8d, 3; dwShareMode
0x14015f003  xor     r9d, r9d; lpSecurityAttributes
0x14015f006  mov     [rsp+48h+dwCreationDisposition], r8d; lpReserved
0x14015f00b  mov     edx, 40000000h; dwDesiredAccess
0x14015f010  call    cs:CreateFileW
0x14015f016  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x14015f01c  mov     r9, rdi; lpNumberOfCharsWritten
0x14015f01f  mov     rcx, rax; hConsoleOutput
0x14015f022  mov     cs:hObject, rax
0x14015f029  mov     r8d, esi; nNumberOfCharsToWrite
0x14015f02c  mov     rdx, rbp; lpBuffer
0x14015f02f  call    cs:WriteConsoleW
0x14015f035  mov     ebx, eax
0x14015f037  mov     rbp, [rsp+48h+arg_8]
0x14015f03c  mov     eax, ebx
0x14015f03e  mov     rbx, [rsp+48h+arg_0]
0x14015f043  mov     rsi, [rsp+48h+arg_10]
0x14015f048  add     rsp, 40h
0x14015f04c  pop     rdi
0x14015f04d  retn
```
