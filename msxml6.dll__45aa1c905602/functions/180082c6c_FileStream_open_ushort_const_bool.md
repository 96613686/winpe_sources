# FileStream::open(ushort const *,bool)

- ea: `0x180082c6c`
- end: `0x180082dca`
- name: `?open@FileStream@@QEAAJPEBG_N@Z`
- size: `350`
- prototype: `HRESULT __fastcall(FileStream *this, const wchar_t *pwszFilename, bool fWrite)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180082c20`
- `0x180156ebc`

## callees

- `0x180017480`
- `0x180082c6c`
- `0x180083164`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082d3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082d3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082d85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082d85`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180082cdf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180082d22`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180082cdf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180082d22`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180082d69`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180082d69`

## pseudocode

```c
__int64 __fastcall FileStream::open(FileStream *this, wchar_t *pwszFilename, bool fWrite)
{
  wchar_t *v3; // r14
  BOOL v4; // r15d
  int FilePath; // eax
  unsigned int v7; // ebx
  DWORD v8; // ebp
  HANDLE FileW; // rax
  signed int LastError; // eax
  DWORD FileType; // eax
  wchar_t *pwszFilePath; // [rsp+60h] [rbp+8h] BYREF

  v3 = pwszFilename;
  v4 = fWrite;
  pwszFilePath = 0;
  FilePath = URL::getFilePath(pwszFilename, &pwszFilePath);
  if ( FilePath >= 0 )
    v3 = pwszFilePath;
  v7 = FilePath;
  this->_fWrite = v4;
  v8 = (!v4 + 1) << 30;
  FileW = CreateFileW(v3, v8, 1u, 0, 3u, 0x100080u, 0);
  this->_hFile = FileW;
  if ( FileW == (HANDLE)-1LL
    && (!v4 || (FileW = CreateFileW(v3, v8, 1u, 0, 2u, 0x100080u, 0), this->_hFile = FileW, FileW == (HANDLE)-1LL)) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( (LastError & 0xFFFFFFFD) != 0 )
    {
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v7 = -2146697210;
    }
  }
  else
  {
    FileType = GetFileType(FileW);
    if ( !FileType || FileType == 2 )
    {
      CloseHandle(this->_hFile);
      this->_hFile = (void *)-1LL;
      v7 = -2147024891;
    }
  }
  if ( pwszFilePath )
    MemFree(pwszFilePath);
  return v7;
}

```

## disassembly

```asm
0x180082c6c  mov     rax, rsp
0x180082c6f  mov     [rax+10h], rbx
0x180082c73  mov     [rax+18h], rbp
0x180082c77  push    rdi
0x180082c78  push    r14
0x180082c7a  push    r15
0x180082c7c  sub     rsp, 40h
0x180082c80  mov     r14, pwszFilename
0x180082c83  movzx   r15d, fWrite
0x180082c87  mov     rdi, this
0x180082c8a  mov     qword ptr [rax+8], 0
0x180082c92  mov     this, r14; pwszURL
0x180082c95  lea     pwszFilename, [rax+8]; pwszFilePath
0x180082c99  call    ?getFilePath@URL@@SAJPEBGPEAPEAG@Z; URL::getFilePath(ushort const *,ushort * *)
0x180082c9e  test    eax, eax
0x180082ca0  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x180082ca9  mov     ebp, r15d
0x180082cac  mov     [rsp+58h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180082cb4  cmovns  r14, [rsp+58h+pwszFilePath]
0x180082cba  mov     ebx, eax
0x180082cbc  xor     ebp, 1
0x180082cbf  mov     [rdi+0A8h], r15b
0x180082cc6  xor     r9d, r9d; lpSecurityAttributes
0x180082cc9  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x180082cd1  inc     ebp
0x180082cd3  mov     this, r14; lpFileName
0x180082cd6  shl     ebp, 1Eh
0x180082cd9  mov     edx, ebp; dwDesiredAccess
0x180082cdb  lea     r8d, [r9+1]; dwShareMode
0x180082cdf  call    cs:__imp_CreateFileW
0x180082ce6  nop     dword ptr [rax+rax+00h]
0x180082ceb  mov     [rdi+0A0h], rax
0x180082cf2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180082cf6  jnz     short loc_180082D66
0x180082cf8  test    r15b, r15b
0x180082cfb  jz      short loc_180082D3B
0x180082cfd  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x180082d06  lea     r8d, [rax+2]; dwShareMode
0x180082d0a  mov     [rsp+58h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180082d12  xor     r9d, r9d; lpSecurityAttributes
0x180082d15  mov     edx, ebp; dwDesiredAccess
0x180082d17  mov     [rsp+58h+dwCreationDisposition], 2; dwCreationDisposition
0x180082d1f  mov     this, r14; lpFileName
0x180082d22  call    cs:__imp_CreateFileW
0x180082d29  nop     dword ptr [rax+rax+00h]
0x180082d2e  mov     [rdi+0A0h], rax
0x180082d35  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180082d39  jnz     short loc_180082D66
0x180082d3b  call    cs:__imp_GetLastError
0x180082d42  nop     dword ptr [rax+rax+00h]
0x180082d47  mov     ebx, eax
0x180082d49  test    eax, 0FFFFFFFDh
0x180082d4e  jz      short loc_180082D5F
0x180082d50  test    eax, eax
0x180082d52  jle     short loc_180082DA1
0x180082d54  movzx   ebx, ax
0x180082d57  or      ebx, 80070000h
0x180082d5d  jmp     short loc_180082DA1
0x180082d5f  mov     ebx, 800C0006h
0x180082d64  jmp     short loc_180082DA1
0x180082d66  mov     this, rax; hFile
0x180082d69  call    cs:__imp_GetFileType
0x180082d70  nop     dword ptr [rax+rax+00h]
0x180082d75  test    eax, eax
0x180082d77  jz      short loc_180082D7E
0x180082d79  cmp     eax, 2
0x180082d7c  jnz     short loc_180082DA1
0x180082d7e  mov     this, [rdi+0A0h]; hObject
0x180082d85  call    cs:__imp_CloseHandle
0x180082d8c  nop     dword ptr [rax+rax+00h]
0x180082d91  mov     qword ptr [rdi+0A0h], 0FFFFFFFFFFFFFFFFh
0x180082d9c  mov     ebx, 80070005h
0x180082da1  cmp     [rsp+58h+pwszFilePath], 0
0x180082da7  jz      short loc_180082DB3
0x180082da9  mov     this, [rsp+58h+pwszFilePath]; pv
0x180082dae  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180082db3  mov     rbp, [rsp+58h+arg_10]
0x180082db8  mov     eax, ebx
0x180082dba  mov     rbx, [rsp+58h+arg_8]
0x180082dbf  add     rsp, 40h
0x180082dc3  pop     r15
0x180082dc5  pop     r14
0x180082dc7  pop     rdi
0x180082dc8  retn
```
