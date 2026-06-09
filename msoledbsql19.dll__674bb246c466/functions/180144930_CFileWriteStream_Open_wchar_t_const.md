# CFileWriteStream::Open(wchar_t const *)

- ea: `0x180144930`
- end: `0x180144a12`
- name: `?Open@CFileWriteStream@@UEAAJPEB_W@Z`
- size: `226`
- prototype: `int(CFileWriteStream *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180144930`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801449b3`
- `KERNEL32!GetLastError` at `0x1801449bd`
- `KERNEL32!GetLastError` at `0x1801449b3`
- `KERNEL32!GetLastError` at `0x1801449bd`
- `KERNEL32!GetFileSize` at `0x1801449a5`
- `KERNEL32!GetFileSize` at `0x1801449a5`
- `KERNEL32!CreateFileW` at `0x18014498e`
- `KERNEL32!CreateFileW` at `0x18014498e`

## pseudocode

```c
__int64 __fastcall CFileWriteStream::Open(CFileWriteStream *this, const wchar_t *a2)
{
  unsigned int v3; // ebx
  HANDLE FileW; // rax
  DWORD FileSize; // eax
  signed int LastError; // eax

  if ( a2 && *a2 )
  {
    if ( *((_QWORD *)this + 2) == -1 )
    {
      FileW = CreateFileW(a2, 0xC0000000, 1u, 0, 2u, 0x8100080u, 0);
      *((_QWORD *)this + 2) = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        FileSize = GetFileSize(FileW, (LPDWORD)this + 7);
        *((_DWORD *)this + 6) = FileSize;
        if ( FileSize != -1 || !GetLastError() )
          return 0;
      }
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( (v3 & 0x80000000) == 0 )
        return v3;
    }
    else
    {
      v3 = -2147221302;
    }
  }
  else
  {
    v3 = -2147221303;
  }
  (*(void (__fastcall **)(CFileWriteStream *))(*(_QWORD *)this + 56LL))(this);
  return v3;
}

```

## disassembly

```asm
0x180144930  mov     [rsp+arg_0], rbx
0x180144935  push    rdi
0x180144936  sub     rsp, 40h
0x18014493a  mov     rax, rdx
0x18014493d  mov     rdi, rcx
0x180144940  test    rdx, rdx
0x180144943  jz      loc_1801449F0
0x180144949  cmp     word ptr [rdx], 0
0x18014494d  jz      loc_1801449F0
0x180144953  cmp     qword ptr [rcx+10h], 0FFFFFFFFFFFFFFFFh
0x180144958  jz      short loc_180144964
0x18014495a  mov     ebx, 800400CAh
0x18014495f  jmp     loc_1801449F5
0x180144964  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18014496d  xor     r9d, r9d; lpSecurityAttributes
0x180144970  mov     [rsp+48h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x180144978  mov     edx, 0C0000000h; dwDesiredAccess
0x18014497d  mov     r8d, 1; dwShareMode
0x180144983  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x18014498b  mov     rcx, rax; lpFileName
0x18014498e  call    cs:__imp_CreateFileW
0x180144994  mov     [rdi+10h], rax
0x180144998  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18014499c  jz      short loc_1801449BD
0x18014499e  lea     rdx, [rdi+1Ch]; lpFileSizeHigh
0x1801449a2  mov     rcx, rax; hFile
0x1801449a5  call    cs:__imp_GetFileSize
0x1801449ab  mov     [rdi+18h], eax
0x1801449ae  cmp     eax, 0FFFFFFFFh
0x1801449b1  jnz     short loc_1801449E3
0x1801449b3  call    cs:__imp_GetLastError
0x1801449b9  test    eax, eax
0x1801449bb  jz      short loc_1801449E3
0x1801449bd  call    cs:__imp_GetLastError
0x1801449c3  mov     ebx, eax
0x1801449c5  test    eax, eax
0x1801449c7  jle     short loc_1801449D2
0x1801449c9  movzx   ebx, ax
0x1801449cc  or      ebx, 80070000h
0x1801449d2  test    ebx, ebx
0x1801449d4  js      short loc_1801449F5
0x1801449d6  mov     eax, ebx
0x1801449d8  mov     rbx, [rsp+48h+arg_0]
0x1801449dd  add     rsp, 40h
0x1801449e1  pop     rdi
0x1801449e2  retn
0x1801449e3  xor     eax, eax
0x1801449e5  mov     rbx, [rsp+48h+arg_0]
0x1801449ea  add     rsp, 40h
0x1801449ee  pop     rdi
0x1801449ef  retn
0x1801449f0  mov     ebx, 800400C9h
0x1801449f5  mov     rax, [rdi]
0x1801449f8  mov     rcx, rdi
0x1801449fb  mov     rax, [rax+38h]
0x1801449ff  call    cs:__guard_dispatch_icall_fptr
0x180144a05  mov     eax, ebx
0x180144a07  mov     rbx, [rsp+48h+arg_0]
0x180144a0c  add     rsp, 40h
0x180144a10  pop     rdi
0x180144a11  retn
```
