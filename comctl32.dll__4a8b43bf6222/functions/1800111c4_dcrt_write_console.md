# __dcrt_write_console

- ea: `0x1800111c4`
- end: `0x180011278`
- name: `__dcrt_write_console`
- size: `180`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180010b00`

## callees

- `0x1800111c4`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180011212`
- `KERNEL32!CloseHandle` at `0x180011212`
- `KERNEL32!GetLastError` at `0x1800111fa`
- `KERNEL32!GetLastError` at `0x1800111fa`
- `KERNEL32!CreateFileW` at `0x180011243`
- `KERNEL32!CreateFileW` at `0x180011243`
- `KERNEL32!WriteConsoleW` at `0x1800111ee`
- `KERNEL32!WriteConsoleW` at `0x180011265`
- `KERNEL32!WriteConsoleW` at `0x1800111ee`
- `KERNEL32!WriteConsoleW` at `0x180011265`

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
0x1800111c4  push    rbx
0x1800111c6  push    rbp
0x1800111c7  push    rsi
0x1800111c8  push    rdi
0x1800111c9  sub     rsp, 48h
0x1800111cd  mov     rdi, r8
0x1800111d0  mov     [rsp+68h+lpReserved], 0; lpReserved
0x1800111d9  mov     r9, r8; lpNumberOfCharsWritten
0x1800111dc  mov     esi, edx
0x1800111de  mov     r8d, edx; nNumberOfCharsToWrite
0x1800111e1  mov     rbp, rcx
0x1800111e4  mov     rdx, rcx; lpBuffer
0x1800111e7  mov     rcx, cs:hObject; hConsoleOutput
0x1800111ee  call    cs:__imp_WriteConsoleW
0x1800111f4  mov     ebx, eax
0x1800111f6  test    eax, eax
0x1800111f8  jnz     short loc_18001126D
0x1800111fa  call    cs:__imp_GetLastError
0x180011200  cmp     eax, 6
0x180011203  jnz     short loc_18001126D
0x180011205  mov     rcx, cs:hObject; hObject
0x18001120c  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180011210  ja      short loc_180011218
0x180011212  call    cs:__imp_CloseHandle
0x180011218  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180011221  lea     rcx, FileName; "CONOUT$"
0x180011228  mov     r8d, 3; dwShareMode
0x18001122e  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180011236  xor     r9d, r9d; lpSecurityAttributes
0x180011239  mov     dword ptr [rsp+68h+lpReserved], r8d; dwCreationDisposition
0x18001123e  mov     edx, 40000000h; dwDesiredAccess
0x180011243  call    cs:__imp_CreateFileW
0x180011249  mov     r9, rdi; lpNumberOfCharsWritten
0x18001124c  mov     [rsp+68h+lpReserved], 0; lpReserved
0x180011255  mov     rcx, rax; hConsoleOutput
0x180011258  mov     cs:hObject, rax
0x18001125f  mov     r8d, esi; nNumberOfCharsToWrite
0x180011262  mov     rdx, rbp; lpBuffer
0x180011265  call    cs:__imp_WriteConsoleW
0x18001126b  mov     ebx, eax
0x18001126d  mov     eax, ebx
0x18001126f  add     rsp, 48h
0x180011273  pop     rdi
0x180011274  pop     rsi
0x180011275  pop     rbp
0x180011276  pop     rbx
0x180011277  retn
```
