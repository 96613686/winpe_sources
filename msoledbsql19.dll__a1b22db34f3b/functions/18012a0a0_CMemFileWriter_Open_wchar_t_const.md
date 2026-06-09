# CMemFileWriter::Open(wchar_t const *)

- ea: `0x18012a0a0`
- end: `0x18012a272`
- name: `?Open@CMemFileWriter@@UEAAJPEB_W@Z`
- size: `466`
- prototype: `int(CMemFileWriter *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180003030`
- `0x18012a0a0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18012a12a`
- `KERNEL32!GetLastError` at `0x18012a15e`
- `KERNEL32!GetLastError` at `0x18012a168`
- `KERNEL32!GetLastError` at `0x18012a12a`
- `KERNEL32!GetLastError` at `0x18012a15e`
- `KERNEL32!GetLastError` at `0x18012a168`
- `KERNEL32!MapViewOfFile` at `0x18012a219`
- `KERNEL32!MapViewOfFile` at `0x18012a219`
- `KERNEL32!CreateFileMappingW` at `0x18012a1ec`
- `KERNEL32!CreateFileMappingW` at `0x18012a1ec`
- `KERNEL32!GetFileSize` at `0x18012a14c`
- `KERNEL32!GetFileSize` at `0x18012a14c`
- `KERNEL32!CreateFileW` at `0x18012a11b`
- `KERNEL32!CreateFileW` at `0x18012a11b`
- `KERNEL32!CloseHandle` at `0x18012a248`
- `KERNEL32!CloseHandle` at `0x18012a248`

## pseudocode

```c
__int64 __fastcall CMemFileWriter::Open(CMemFileWriter *this, const wchar_t *a2)
{
  unsigned int v3; // ebx
  HANDLE *v4; // r14
  HANDLE FileW; // rax
  signed int LastError; // eax
  _QWORD *v7; // rsi
  DWORD FileSize; // eax
  signed int v9; // eax
  HANDLE FileMappingW; // rax
  LPVOID v12; // rax

  if ( !a2 )
  {
    v3 = -2147024809;
LABEL_16:
    (*(void (__fastcall **)(CMemFileWriter *))(*(_QWORD *)this + 48LL))(this);
    if ( (bidGblFlags & 2) != 0 )
    {
      _mm_lfence();
      bidTraceHR(off_180260618[0], 860169, v3);
      return v3;
    }
    return v3;
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
  FileW = CreateFileW(a2, 0xC0000000, 1u, 0, 2u, 0x8100080u, 0);
  *v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v7 = (_QWORD *)((char *)this + 16);
  }
  else
  {
    FileSize = GetFileSize(FileW, (LPDWORD)this + 5);
    *((_DWORD *)this + 4) = FileSize;
    v7 = (_QWORD *)((char *)this + 16);
    if ( FileSize != -1 || !GetLastError() )
    {
      *((_DWORD *)this + 6) = 1;
      v3 = 0;
      goto LABEL_20;
    }
    v9 = GetLastError();
    v3 = v9;
    if ( v9 > 0 )
      v3 = (unsigned __int16)v9 | 0x80070000;
  }
  if ( (v3 & 0x80000000) != 0 )
    goto LABEL_16;
LABEL_20:
  FileMappingW = CreateFileMappingW(*v4, 0, 4u, 0, 0x100000u, 0);
  *((_QWORD *)this + 5) = FileMappingW;
  if ( FileMappingW )
  {
    *((_DWORD *)this + 19) = 0x100000;
    v12 = MapViewOfFile(FileMappingW, 2u, 0, 0, 0x100000u);
    *((_QWORD *)this + 6) = v12;
    if ( v12 )
    {
      *v7 = *((unsigned int *)this + 19);
      *((_QWORD *)this + 7) = 0;
      *((_QWORD *)this + 8) = 0;
      *((_DWORD *)this + 18) = 0;
      *((_DWORD *)this + 8) = 1;
      return v3;
    }
    CloseHandle(*((HANDLE *)this + 5));
    *((_QWORD *)this + 5) = 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18012a0a0  mov     [rsp+arg_0], rbx
0x18012a0a5  mov     [rsp+arg_8], rbp
0x18012a0aa  mov     [rsp+arg_10], rsi
0x18012a0af  mov     [rsp+arg_18], rdi
0x18012a0b4  push    r14
0x18012a0b6  sub     rsp, 40h
0x18012a0ba  xor     ebp, ebp
0x18012a0bc  mov     rax, rdx
0x18012a0bf  mov     rdi, rcx
0x18012a0c2  test    rdx, rdx
0x18012a0c5  jnz     short loc_18012A0D1
0x18012a0c7  mov     ebx, 80070057h
0x18012a0cc  jmp     loc_18012A181
0x18012a0d1  cmp     [rdx], bp
0x18012a0d4  jnz     short loc_18012A0E0
0x18012a0d6  mov     ebx, 800400C9h
0x18012a0db  jmp     loc_18012A181
0x18012a0e0  cmp     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x18012a0e5  lea     r14, [rcx+8]
0x18012a0e9  jz      short loc_18012A0F5
0x18012a0eb  mov     ebx, 800400CAh
0x18012a0f0  jmp     loc_18012A181
0x18012a0f5  mov     [rsp+48h+hTemplateFile], rbp; hTemplateFile
0x18012a0fa  xor     r9d, r9d; lpSecurityAttributes
0x18012a0fd  mov     [rsp+48h+dwFlagsAndAttributes], 8100080h; dwFlagsAndAttributes
0x18012a105  mov     edx, 0C0000000h; dwDesiredAccess
0x18012a10a  mov     r8d, 1; dwShareMode
0x18012a110  mov     [rsp+48h+dwCreationDisposition], 2; dwCreationDisposition
0x18012a118  mov     rcx, rax; lpFileName
0x18012a11b  call    cs:__imp_CreateFileW
0x18012a121  mov     [r14], rax
0x18012a124  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18012a128  jnz     short loc_18012A145
0x18012a12a  call    cs:__imp_GetLastError
0x18012a130  mov     ebx, eax
0x18012a132  test    eax, eax
0x18012a134  jle     short loc_18012A13F
0x18012a136  movzx   ebx, ax
0x18012a139  or      ebx, 80070000h
0x18012a13f  lea     rsi, [rdi+10h]
0x18012a143  jmp     short loc_18012A17D
0x18012a145  lea     rdx, [rdi+14h]; lpFileSizeHigh
0x18012a149  mov     rcx, rax; hFile
0x18012a14c  call    cs:__imp_GetFileSize
0x18012a152  mov     [rdi+10h], eax
0x18012a155  lea     rsi, [rdi+10h]
0x18012a159  cmp     eax, 0FFFFFFFFh
0x18012a15c  jnz     short loc_18012A1C8
0x18012a15e  call    cs:__imp_GetLastError
0x18012a164  test    eax, eax
0x18012a166  jz      short loc_18012A1C8
0x18012a168  call    cs:__imp_GetLastError
0x18012a16e  mov     ebx, eax
0x18012a170  test    eax, eax
0x18012a172  jle     short loc_18012A17D
0x18012a174  movzx   ebx, ax
0x18012a177  or      ebx, 80070000h
0x18012a17d  test    ebx, ebx
0x18012a17f  jns     short loc_18012A1D1
0x18012a181  mov     rax, [rdi]
0x18012a184  mov     rcx, rdi
0x18012a187  mov     rax, [rax+30h]
0x18012a18b  call    cs:__guard_dispatch_icall_fptr
0x18012a191  lea     r14, [rdi+8]
0x18012a195  lea     rsi, [rdi+10h]
0x18012a199  test    ebx, ebx
0x18012a19b  jns     short loc_18012A1D1
0x18012a19d  test    byte ptr cs:_bidGblFlags, 2
0x18012a1a4  jz      loc_18012A240
0x18012a1aa  lfence
0x18012a1ad  mov     rcx, cs:off_180260618; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18012a1b4  mov     r8d, ebx
0x18012a1b7  mov     edx, 0D2009h
0x18012a1bc  call    _bidTraceHR
0x18012a1c1  mov     eax, ebx
0x18012a1c3  jmp     loc_18012A257
0x18012a1c8  mov     dword ptr [rdi+18h], 1
0x18012a1cf  mov     ebx, ebp
0x18012a1d1  mov     rcx, [r14]; hFile
0x18012a1d4  xor     r9d, r9d; dwMaximumSizeHigh
0x18012a1d7  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], rbp; lpName
0x18012a1dc  xor     edx, edx; lpFileMappingAttributes
0x18012a1de  mov     r8d, 4; flProtect
0x18012a1e4  mov     [rsp+48h+dwCreationDisposition], 100000h; dwMaximumSizeLow
0x18012a1ec  call    cs:__imp_CreateFileMappingW
0x18012a1f2  mov     [rdi+28h], rax
0x18012a1f6  test    rax, rax
0x18012a1f9  jz      short loc_18012A252
0x18012a1fb  xor     r9d, r9d; dwFileOffsetLow
0x18012a1fe  mov     dword ptr [rdi+4Ch], 100000h
0x18012a205  xor     r8d, r8d; dwFileOffsetHigh
0x18012a208  mov     qword ptr [rsp+48h+dwCreationDisposition], 100000h; dwNumberOfBytesToMap
0x18012a211  mov     edx, 2; dwDesiredAccess
0x18012a216  mov     rcx, rax; hFileMappingObject
0x18012a219  call    cs:__imp_MapViewOfFile
0x18012a21f  mov     [rdi+30h], rax
0x18012a223  test    rax, rax
0x18012a226  jz      short loc_18012A244
0x18012a228  mov     eax, [rdi+4Ch]
0x18012a22b  mov     [rsi], rax
0x18012a22e  mov     [rdi+38h], rbp
0x18012a232  mov     [rdi+40h], rbp
0x18012a236  mov     [rdi+48h], ebp
0x18012a239  mov     dword ptr [rdi+20h], 1
0x18012a240  mov     eax, ebx
0x18012a242  jmp     short loc_18012A257
0x18012a244  mov     rcx, [rdi+28h]; hObject
0x18012a248  call    cs:__imp_CloseHandle
0x18012a24e  mov     [rdi+28h], rbp
0x18012a252  mov     eax, 1
0x18012a257  mov     rbx, [rsp+48h+arg_0]
0x18012a25c  mov     rbp, [rsp+48h+arg_8]
0x18012a261  mov     rsi, [rsp+48h+arg_10]
0x18012a266  mov     rdi, [rsp+48h+arg_18]
0x18012a26b  add     rsp, 40h
0x18012a26f  pop     r14
0x18012a271  retn
```
