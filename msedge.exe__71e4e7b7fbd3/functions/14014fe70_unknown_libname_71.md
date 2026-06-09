# unknown_libname_71

- ea: `0x14014fe70`
- end: `0x14014ff2e`
- name: `unknown_libname_71`
- size: `190`
- prototype: `__int64 __fastcall(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14014af34`

## callees

- `0x14014fe70`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14014fec5`
- `KERNEL32!CloseHandle` at `0x14014fec5`
- `KERNEL32!CreateFileW` at `0x14014fef0`
- `KERNEL32!CreateFileW` at `0x14014fef0`
- `KERNEL32!GetLastError` at `0x14014fead`
- `KERNEL32!GetLastError` at `0x14014fead`
- `KERNEL32!WriteConsoleW` at `0x14014fea1`
- `KERNEL32!WriteConsoleW` at `0x14014ff0f`
- `KERNEL32!WriteConsoleW` at `0x14014fea1`
- `KERNEL32!WriteConsoleW` at `0x14014ff0f`

## pseudocode

```c
// Microsoft VisualC 64bit universal runtime
__int64 __fastcall unknown_libname_71(void *lpBuffer, DWORD nNumberOfCharsToWrite, LPDWORD lpNumberOfCharsWritten)
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
0x14014fe70  mov     rax, rsp
0x14014fe73  mov     [rax+8], rbx
0x14014fe77  mov     [rax+10h], rbp
0x14014fe7b  mov     [rax+18h], rsi
0x14014fe7f  push    rdi
0x14014fe80  sub     rsp, 40h
0x14014fe84  and     qword ptr [rax-28h], 0
0x14014fe89  mov     rdi, r8
0x14014fe8c  mov     r9, r8; lpNumberOfCharsWritten
0x14014fe8f  mov     esi, edx
0x14014fe91  mov     r8d, edx; nNumberOfCharsToWrite
0x14014fe94  mov     rbp, rcx
0x14014fe97  mov     rdx, rcx; lpBuffer
0x14014fe9a  mov     rcx, cs:hObject; hConsoleOutput
0x14014fea1  call    cs:WriteConsoleW
0x14014fea7  mov     ebx, eax
0x14014fea9  test    eax, eax
0x14014feab  jnz     short loc_14014FF17
0x14014fead  call    cs:__imp_GetLastError
0x14014feb3  cmp     eax, 6
0x14014feb6  jnz     short loc_14014FF17
0x14014feb8  mov     rcx, cs:hObject; hObject
0x14014febf  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14014fec3  ja      short loc_14014FECB
0x14014fec5  call    cs:__imp_CloseHandle
0x14014fecb  and     [rsp+48h+var_18], 0
0x14014fed1  lea     rcx, FileName
0x14014fed8  and     [rsp+48h+var_20], 0
0x14014fedd  mov     r8d, 3; dwShareMode
0x14014fee3  xor     r9d, r9d; lpSecurityAttributes
0x14014fee6  mov     [rsp+48h+dwCreationDisposition], r8d; lpReserved
0x14014feeb  mov     edx, 40000000h; dwDesiredAccess
0x14014fef0  call    cs:CreateFileW
0x14014fef6  and     qword ptr [rsp+48h+dwCreationDisposition], 0
0x14014fefc  mov     r9, rdi; lpNumberOfCharsWritten
0x14014feff  mov     rcx, rax; hConsoleOutput
0x14014ff02  mov     cs:hObject, rax
0x14014ff09  mov     r8d, esi; nNumberOfCharsToWrite
0x14014ff0c  mov     rdx, rbp; lpBuffer
0x14014ff0f  call    cs:WriteConsoleW
0x14014ff15  mov     ebx, eax
0x14014ff17  mov     rbp, [rsp+48h+arg_8]
0x14014ff1c  mov     eax, ebx
0x14014ff1e  mov     rbx, [rsp+48h+arg_0]
0x14014ff23  mov     rsi, [rsp+48h+arg_10]
0x14014ff28  add     rsp, 40h
0x14014ff2c  pop     rdi
0x14014ff2d  retn
```
