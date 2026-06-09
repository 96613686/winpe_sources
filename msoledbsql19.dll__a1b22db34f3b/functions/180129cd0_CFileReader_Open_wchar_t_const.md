# CFileReader::Open(wchar_t const *)

- ea: `0x180129cd0`
- end: `0x180129db0`
- name: `?Open@CFileReader@@UEAAJPEB_W@Z`
- size: `224`
- prototype: `int(CFileReader *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180129cd0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180129d5c`
- `KERNEL32!GetLastError` at `0x180129d66`
- `KERNEL32!GetLastError` at `0x180129d5c`
- `KERNEL32!GetLastError` at `0x180129d66`
- `KERNEL32!GetFileSize` at `0x180129d4e`
- `KERNEL32!GetFileSize` at `0x180129d4e`
- `KERNEL32!CreateFileW` at `0x180129d37`
- `KERNEL32!CreateFileW` at `0x180129d37`

## pseudocode

```c
__int64 __fastcall CFileReader::Open(CFileReader *this, const wchar_t *a2)
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
    (*(void (__fastcall **)(CFileReader *))(*(_QWORD *)this + 56LL))(this);
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
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x8100080u, 0);
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
0x180129cd0  mov     [rsp+arg_0], rbx
0x180129cd5  push    rdi
0x180129cd6  sub     rsp, 40h
0x180129cda  mov     rax, rdx
0x180129cdd  mov     rdi, rcx
0x180129ce0  test    rdx, rdx
0x180129ce3  jnz     short loc_180129CEF
0x180129ce5  mov     ebx, 80070057h
0x180129cea  jmp     loc_180129D7F
0x180129cef  cmp     word ptr [rdx], 0
0x180129cf3  jnz     short loc_180129CFF
0x180129cf5  mov     ebx, 800400C9h
0x180129cfa  jmp     loc_180129D7F
0x180129cff  cmp     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x180129d04  jz      short loc_180129D0D
0x180129d06  mov     ebx, 800400CAh
0x180129d0b  jmp     short loc_180129D7F
0x180129d0d  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180129d16  xor     r9d, r9d; lpSecurityAttributes
0x180129d19  mov     [rsp+48h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x180129d21  mov     edx, 80000000h; dwDesiredAccess
0x180129d26  mov     r8d, 1; dwShareMode
0x180129d2c  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180129d34  mov     rcx, rax; lpFileName
0x180129d37  call    cs:__imp_CreateFileW
0x180129d3d  mov     [rdi+8], rax
0x180129d41  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180129d45  jz      short loc_180129D66
0x180129d47  lea     rdx, [rdi+14h]; lpFileSizeHigh
0x180129d4b  mov     rcx, rax; hFile
0x180129d4e  call    cs:__imp_GetFileSize
0x180129d54  mov     [rdi+10h], eax
0x180129d57  cmp     eax, 0FFFFFFFFh
0x180129d5a  jnz     short loc_180129D9C
0x180129d5c  call    cs:__imp_GetLastError
0x180129d62  test    eax, eax
0x180129d64  jz      short loc_180129D9C
0x180129d66  call    cs:__imp_GetLastError
0x180129d6c  mov     ebx, eax
0x180129d6e  test    eax, eax
0x180129d70  jle     short loc_180129D7B
0x180129d72  movzx   ebx, ax
0x180129d75  or      ebx, 80070000h
0x180129d7b  test    ebx, ebx
0x180129d7d  jns     short loc_180129D8F
0x180129d7f  mov     rax, [rdi]
0x180129d82  mov     rcx, rdi
0x180129d85  mov     rax, [rax+38h]
0x180129d89  call    cs:__guard_dispatch_icall_fptr
0x180129d8f  mov     eax, ebx
0x180129d91  mov     rbx, [rsp+48h+arg_0]
0x180129d96  add     rsp, 40h
0x180129d9a  pop     rdi
0x180129d9b  retn
0x180129d9c  mov     rbx, [rsp+48h+arg_0]
0x180129da1  xor     eax, eax
0x180129da3  mov     dword ptr [rdi+18h], 1
0x180129daa  add     rsp, 40h
0x180129dae  pop     rdi
0x180129daf  retn
```
