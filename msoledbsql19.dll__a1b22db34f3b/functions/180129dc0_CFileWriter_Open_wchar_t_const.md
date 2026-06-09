# CFileWriter::Open(wchar_t const *)

- ea: `0x180129dc0`
- end: `0x180129ea0`
- name: `?Open@CFileWriter@@UEAAJPEB_W@Z`
- size: `224`
- prototype: `int(CFileWriter *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180129dc0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180129e4c`
- `KERNEL32!GetLastError` at `0x180129e56`
- `KERNEL32!GetLastError` at `0x180129e4c`
- `KERNEL32!GetLastError` at `0x180129e56`
- `KERNEL32!GetFileSize` at `0x180129e3e`
- `KERNEL32!GetFileSize` at `0x180129e3e`
- `KERNEL32!CreateFileW` at `0x180129e27`
- `KERNEL32!CreateFileW` at `0x180129e27`

## pseudocode

```c
__int64 __fastcall CFileWriter::Open(CFileWriter *this, const wchar_t *a2)
{
  unsigned int v3; // ebx
  HANDLE FileW; // rax
  DWORD FileSize; // eax
  signed int LastError; // eax
  __int64 result; // rax

  if ( !a2 )
  {
    v3 = -2147024809;
LABEL_13:
    (*(void (__fastcall **)(CFileWriter *))(*(_QWORD *)this + 48LL))(this);
    return v3;
  }
  if ( !*a2 )
  {
    v3 = -2147221303;
    goto LABEL_13;
  }
  if ( *((_QWORD *)this + 1) != -1 )
  {
    v3 = -2147221302;
    goto LABEL_13;
  }
  FileW = CreateFileW(a2, 0xC0000000, 1u, 0, 2u, 0x8100080u, 0);
  *((_QWORD *)this + 1) = FileW;
  if ( FileW == (HANDLE)-1LL
    || (FileSize = GetFileSize(FileW, (LPDWORD)this + 5), *((_DWORD *)this + 4) = FileSize, FileSize == -1)
    && GetLastError() )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( (v3 & 0x80000000) == 0 )
      return v3;
    goto LABEL_13;
  }
  result = 0;
  *((_DWORD *)this + 6) = 1;
  return result;
}

```

## disassembly

```asm
0x180129dc0  mov     [rsp+arg_0], rbx
0x180129dc5  push    rdi
0x180129dc6  sub     rsp, 40h
0x180129dca  mov     rax, rdx
0x180129dcd  mov     rdi, rcx
0x180129dd0  test    rdx, rdx
0x180129dd3  jnz     short loc_180129DDF
0x180129dd5  mov     ebx, 80070057h
0x180129dda  jmp     loc_180129E6F
0x180129ddf  cmp     word ptr [rdx], 0
0x180129de3  jnz     short loc_180129DEF
0x180129de5  mov     ebx, 800400C9h
0x180129dea  jmp     loc_180129E6F
0x180129def  cmp     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x180129df4  jz      short loc_180129DFD
0x180129df6  mov     ebx, 800400CAh
0x180129dfb  jmp     short loc_180129E6F
0x180129dfd  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180129e06  xor     r9d, r9d; lpSecurityAttributes
0x180129e09  mov     [rsp+48h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x180129e11  mov     edx, 0C0000000h; dwDesiredAccess
0x180129e16  mov     r8d, 1; dwShareMode
0x180129e1c  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x180129e24  mov     rcx, rax; lpFileName
0x180129e27  call    cs:__imp_CreateFileW
0x180129e2d  mov     [rdi+8], rax
0x180129e31  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180129e35  jz      short loc_180129E56
0x180129e37  lea     rdx, [rdi+14h]; lpFileSizeHigh
0x180129e3b  mov     rcx, rax; hFile
0x180129e3e  call    cs:__imp_GetFileSize
0x180129e44  mov     [rdi+10h], eax
0x180129e47  cmp     eax, 0FFFFFFFFh
0x180129e4a  jnz     short loc_180129E8C
0x180129e4c  call    cs:__imp_GetLastError
0x180129e52  test    eax, eax
0x180129e54  jz      short loc_180129E8C
0x180129e56  call    cs:__imp_GetLastError
0x180129e5c  mov     ebx, eax
0x180129e5e  test    eax, eax
0x180129e60  jle     short loc_180129E6B
0x180129e62  movzx   ebx, ax
0x180129e65  or      ebx, 80070000h
0x180129e6b  test    ebx, ebx
0x180129e6d  jns     short loc_180129E7F
0x180129e6f  mov     rax, [rdi]
0x180129e72  mov     rcx, rdi
0x180129e75  mov     rax, [rax+30h]
0x180129e79  call    cs:__guard_dispatch_icall_fptr
0x180129e7f  mov     eax, ebx
0x180129e81  mov     rbx, [rsp+48h+arg_0]
0x180129e86  add     rsp, 40h
0x180129e8a  pop     rdi
0x180129e8b  retn
0x180129e8c  mov     rbx, [rsp+48h+arg_0]
0x180129e91  xor     eax, eax
0x180129e93  mov     dword ptr [rdi+18h], 1
0x180129e9a  add     rsp, 40h
0x180129e9e  pop     rdi
0x180129e9f  retn
```
