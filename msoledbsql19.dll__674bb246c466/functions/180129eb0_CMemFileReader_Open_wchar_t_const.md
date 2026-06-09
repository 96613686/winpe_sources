# CMemFileReader::Open(wchar_t const *)

- ea: `0x180129eb0`
- end: `0x18012a092`
- name: `?Open@CMemFileReader@@UEAAJPEB_W@Z`
- size: `482`
- prototype: `int(CMemFileReader *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180003030`
- `0x180129eb0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180129f3a`
- `KERNEL32!GetLastError` at `0x180129f6e`
- `KERNEL32!GetLastError` at `0x180129f78`
- `KERNEL32!GetLastError` at `0x180129f3a`
- `KERNEL32!GetLastError` at `0x180129f6e`
- `KERNEL32!GetLastError` at `0x180129f78`
- `KERNEL32!MapViewOfFile` at `0x18012a038`
- `KERNEL32!MapViewOfFile` at `0x18012a038`
- `KERNEL32!CreateFileMappingW` at `0x18012a005`
- `KERNEL32!CreateFileMappingW` at `0x18012a005`
- `KERNEL32!GetFileSize` at `0x180129f5c`
- `KERNEL32!GetFileSize` at `0x180129f5c`
- `KERNEL32!CreateFileW` at `0x180129f2b`
- `KERNEL32!CreateFileW` at `0x180129f2b`
- `KERNEL32!CloseHandle` at `0x18012a05f`
- `KERNEL32!CloseHandle` at `0x18012a05f`

## pseudocode

```c
__int64 __fastcall CMemFileReader::Open(CMemFileReader *this, const wchar_t *a2)
{
  signed int v3; // ebx
  HANDLE *v4; // r14
  HANDLE FileW; // rax
  signed int LastError; // eax
  SIZE_T *v7; // rsi
  DWORD FileSize; // eax
  signed int v9; // eax
  __int64 *v10; // rax
  HANDLE FileMappingW; // rax
  SIZE_T v12; // rcx
  LPVOID v13; // rax
  __int64 result; // rax

  if ( !a2 )
  {
    v3 = -2147024809;
LABEL_16:
    (*(void (__fastcall **)(CMemFileReader *))(*(_QWORD *)this + 56LL))(this);
    v7 = (SIZE_T *)((char *)this + 16);
    v4 = (HANDLE *)((char *)this + 8);
    goto LABEL_17;
  }
  if ( !*a2 )
  {
    v3 = -2147221303;
    goto LABEL_16;
  }
  v4 = (HANDLE *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) != -1 )
  {
    v3 = -2147221302;
    goto LABEL_16;
  }
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x8100080u, 0);
  *v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v7 = (SIZE_T *)((char *)this + 16);
  }
  else
  {
    FileSize = GetFileSize(FileW, (LPDWORD)this + 5);
    *((_DWORD *)this + 4) = FileSize;
    v7 = (SIZE_T *)((char *)this + 16);
    if ( FileSize != -1 || !GetLastError() )
    {
      *((_DWORD *)this + 6) = 1;
      v10 = (__int64 *)((char *)this + 16);
      v3 = 0;
      goto LABEL_21;
    }
    v9 = GetLastError();
    v3 = v9;
    if ( v9 > 0 )
      v3 = (unsigned __int16)v9 | 0x80070000;
  }
  if ( v3 < 0 )
    goto LABEL_16;
LABEL_17:
  v10 = (__int64 *)v7;
  if ( v3 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_180260618[0], 496649, (unsigned int)v3);
    }
    return (unsigned int)v3;
  }
LABEL_21:
  if ( *v10 > 0 )
  {
    FileMappingW = CreateFileMappingW(*v4, 0, 2u, 0, 0, 0);
    *((_QWORD *)this + 5) = FileMappingW;
    if ( FileMappingW )
    {
      v12 = *v7;
      if ( (__int64)*v7 > 0x100000 )
        v12 = 0x100000;
      *((_DWORD *)this + 19) = v12;
      v13 = MapViewOfFile(FileMappingW, 4u, 0, 0, v12);
      *((_QWORD *)this + 6) = v13;
      if ( !v13 )
      {
        CloseHandle(*((HANDLE *)this + 5));
        result = 1;
        *((_QWORD *)this + 5) = 0;
        return result;
      }
      *((_QWORD *)this + 7) = 0;
      *((_QWORD *)this + 8) = 0;
      *((_DWORD *)this + 18) = 0;
      *((_DWORD *)this + 8) = 1;
    }
    else
    {
      return 1;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180129eb0  mov     [rsp+arg_0], rbx
0x180129eb5  mov     [rsp+arg_8], rbp
0x180129eba  mov     [rsp+arg_10], rsi
0x180129ebf  mov     [rsp+arg_18], rdi
0x180129ec4  push    r14
0x180129ec6  sub     rsp, 40h
0x180129eca  xor     ebp, ebp
0x180129ecc  mov     rax, rdx
0x180129ecf  mov     rdi, rcx
0x180129ed2  test    rdx, rdx
0x180129ed5  jnz     short loc_180129EE1
0x180129ed7  mov     ebx, 80070057h
0x180129edc  jmp     loc_180129F91
0x180129ee1  cmp     [rdx], bp
0x180129ee4  jnz     short loc_180129EF0
0x180129ee6  mov     ebx, 800400C9h
0x180129eeb  jmp     loc_180129F91
0x180129ef0  cmp     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x180129ef5  lea     r14, [rcx+8]
0x180129ef9  jz      short loc_180129F05
0x180129efb  mov     ebx, 800400CAh
0x180129f00  jmp     loc_180129F91
0x180129f05  mov     [rsp+48h+hTemplateFile], rbp; hTemplateFile
0x180129f0a  xor     r9d, r9d; lpSecurityAttributes
0x180129f0d  mov     [rsp+48h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x180129f15  mov     edx, 80000000h; dwDesiredAccess
0x180129f1a  mov     r8d, 1; dwShareMode
0x180129f20  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180129f28  mov     rcx, rax; lpFileName
0x180129f2b  call    cs:__imp_CreateFileW
0x180129f31  mov     [r14], rax
0x180129f34  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180129f38  jnz     short loc_180129F55
0x180129f3a  call    cs:__imp_GetLastError
0x180129f40  mov     ebx, eax
0x180129f42  test    eax, eax
0x180129f44  jle     short loc_180129F4F
0x180129f46  movzx   ebx, ax
0x180129f49  or      ebx, 80070000h
0x180129f4f  lea     rsi, [rdi+10h]
0x180129f53  jmp     short loc_180129F8D
0x180129f55  lea     rdx, [rdi+14h]; lpFileSizeHigh
0x180129f59  mov     rcx, rax; hFile
0x180129f5c  call    cs:__imp_GetFileSize
0x180129f62  mov     [rdi+10h], eax
0x180129f65  lea     rsi, [rdi+10h]
0x180129f69  cmp     eax, 0FFFFFFFFh
0x180129f6c  jnz     short loc_180129FD9
0x180129f6e  call    cs:__imp_GetLastError
0x180129f74  test    eax, eax
0x180129f76  jz      short loc_180129FD9
0x180129f78  call    cs:__imp_GetLastError
0x180129f7e  mov     ebx, eax
0x180129f80  test    eax, eax
0x180129f82  jle     short loc_180129F8D
0x180129f84  movzx   ebx, ax
0x180129f87  or      ebx, 80070000h
0x180129f8d  test    ebx, ebx
0x180129f8f  jns     short loc_180129FA9
0x180129f91  mov     rax, [rdi]
0x180129f94  mov     rcx, rdi
0x180129f97  mov     rax, [rax+38h]
0x180129f9b  call    cs:__guard_dispatch_icall_fptr
0x180129fa1  lea     rsi, [rdi+10h]
0x180129fa5  lea     r14, [rdi+8]
0x180129fa9  mov     rax, rsi
0x180129fac  test    ebx, ebx
0x180129fae  jns     short loc_180129FE5
0x180129fb0  test    byte ptr cs:_bidGblFlags, 2
0x180129fb7  jz      loc_18012A075
0x180129fbd  lfence
0x180129fc0  mov     rcx, cs:off_180260618; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x180129fc7  mov     r8d, ebx
0x180129fca  mov     edx, 79409h
0x180129fcf  call    _bidTraceHR
0x180129fd4  jmp     loc_18012A075
0x180129fd9  mov     dword ptr [rdi+18h], 1
0x180129fe0  mov     rax, rsi
0x180129fe3  mov     ebx, ebp
0x180129fe5  cmp     [rax], rbp
0x180129fe8  jle     loc_18012A075
0x180129fee  mov     rcx, [r14]; hFile
0x180129ff1  xor     r9d, r9d; dwMaximumSizeHigh
0x180129ff4  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], rbp; lpName
0x180129ff9  xor     edx, edx; lpFileMappingAttributes
0x180129ffb  mov     r8d, 2; flProtect
0x18012a001  mov     [rsp+48h+dwCreationDisposition], ebp; dwMaximumSizeLow
0x18012a005  call    cs:__imp_CreateFileMappingW
0x18012a00b  mov     [rdi+28h], rax
0x18012a00f  test    rax, rax
0x18012a012  jz      short loc_18012A070
0x18012a014  mov     rcx, [rsi]
0x18012a017  mov     edx, 100000h
0x18012a01c  cmp     rcx, rdx
0x18012a01f  cmovg   ecx, edx
0x18012a022  xor     r9d, r9d; dwFileOffsetLow
0x18012a025  mov     [rdi+4Ch], ecx
0x18012a028  xor     r8d, r8d; dwFileOffsetHigh
0x18012a02b  mov     qword ptr [rsp+48h+dwCreationDisposition], rcx; dwNumberOfBytesToMap
0x18012a030  mov     edx, 4; dwDesiredAccess
0x18012a035  mov     rcx, rax; hFileMappingObject
0x18012a038  call    cs:__imp_MapViewOfFile
0x18012a03e  mov     [rdi+30h], rax
0x18012a042  test    rax, rax
0x18012a045  jz      short loc_18012A05B
0x18012a047  mov     [rdi+38h], rbp
0x18012a04b  mov     [rdi+40h], rbp
0x18012a04f  mov     [rdi+48h], ebp
0x18012a052  mov     dword ptr [rdi+20h], 1
0x18012a059  jmp     short loc_18012A075
0x18012a05b  mov     rcx, [rdi+28h]; hObject
0x18012a05f  call    cs:__imp_CloseHandle
0x18012a065  mov     eax, 1
0x18012a06a  mov     [rdi+28h], rbp
0x18012a06e  jmp     short loc_18012A077
0x18012a070  mov     ebx, 1
0x18012a075  mov     eax, ebx
0x18012a077  mov     rbx, [rsp+48h+arg_0]
0x18012a07c  mov     rbp, [rsp+48h+arg_8]
0x18012a081  mov     rsi, [rsp+48h+arg_10]
0x18012a086  mov     rdi, [rsp+48h+arg_18]
0x18012a08b  add     rsp, 40h
0x18012a08f  pop     r14
0x18012a091  retn
```
