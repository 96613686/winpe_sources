# CreateFileWithUnicodeBOM

- ea: `0x1800129e0`
- end: `0x180012a71`
- name: `CreateFileWithUnicodeBOM`
- size: `145`
- prototype: `HANDLE __fastcall(const WCHAR *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180013270`

## callees

- `0x1800129e0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180012a10`
- `KERNEL32!CreateFileW` at `0x180012a10`
- `KERNEL32!WriteFile` at `0x180012a44`
- `KERNEL32!WriteFile` at `0x180012a44`
- `KERNEL32!CloseHandle` at `0x180012a5d`
- `KERNEL32!CloseHandle` at `0x180012a5d`

## pseudocode

```c
HANDLE __fastcall CreateFileWithUnicodeBOM(const WCHAR *a1)
{
  unsigned __int16 v1; // bx
  HANDLE result; // rax
  void *v3; // rdi
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp+10h] BYREF

  v1 = 0;
  NumberOfBytesWritten = 0;
  result = CreateFileW(a1, 0x40000000u, 0, 0, 1u, 0x80u, 0);
  v3 = result;
  if ( result != (HANDLE)-1LL )
  {
    if ( !WriteFile(result, &qword_180018340, 2u, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 2 )
      v1 = -1;
    CloseHandle(v3);
    return (HANDLE)v1;
  }
  return result;
}

```

## disassembly

```asm
0x1800129e0  mov     [rsp+arg_0], rbx
0x1800129e5  push    rdi
0x1800129e6  sub     rsp, 40h
0x1800129ea  xor     ebx, ebx
0x1800129ec  xor     r9d, r9d; lpSecurityAttributes
0x1800129ef  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x1800129f4  xor     r8d, r8d; dwShareMode
0x1800129f7  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800129ff  mov     edx, 40000000h; dwDesiredAccess
0x180012a04  mov     [rsp+48h+dwCreationDisposition], 1; dwCreationDisposition
0x180012a0c  mov     [rsp+48h+NumberOfBytesWritten], ebx
0x180012a10  call    cs:__imp_CreateFileW
0x180012a16  mov     rdi, rax
0x180012a19  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012a1d  jnz     short loc_180012A2A
0x180012a1f  mov     rbx, [rsp+48h+arg_0]
0x180012a24  add     rsp, 40h
0x180012a28  pop     rdi
0x180012a29  retn
0x180012a2a  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180012a2f  mov     qword ptr [rsp+48h+dwCreationDisposition], rbx; lpOverlapped
0x180012a34  mov     r8d, 2; nNumberOfBytesToWrite
0x180012a3a  lea     rdx, qword_180018340; lpBuffer
0x180012a41  mov     rcx, rdi; hFile
0x180012a44  call    cs:__imp_WriteFile
0x180012a4a  test    eax, eax
0x180012a4c  jz      short loc_180012A55
0x180012a4e  cmp     [rsp+48h+NumberOfBytesWritten], 2
0x180012a53  jz      short loc_180012A5A
0x180012a55  mov     ebx, 0FFFFFFFFh
0x180012a5a  mov     rcx, rdi; hObject
0x180012a5d  call    cs:__imp_CloseHandle
0x180012a63  movzx   eax, bx
0x180012a66  mov     rbx, [rsp+48h+arg_0]
0x180012a6b  add     rsp, 40h
0x180012a6f  pop     rdi
0x180012a70  retn
```
