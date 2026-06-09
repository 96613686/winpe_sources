# FileStream::open(ushort const *,bool)

- ea: `0x18008366c`
- end: `0x1800837ab`
- name: `?open@FileStream@@QEAAJPEBG_N@Z`
- size: `319`
- prototype: `HRESULT __fastcall(FileStream *this, const wchar_t *pwszFilename, bool fWrite)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180083620`
- `0x18015396c`

## callees

- `0x18000ae54`
- `0x18008366c`
- `0x180083b3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008372f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008372f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008376d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008376d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800836df`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008371c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800836df`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008371c`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180083757`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180083757`

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
0x18008366c  mov     rax, rsp
0x18008366f  mov     [rax+10h], rbx
0x180083673  mov     [rax+18h], rbp
0x180083677  push    rdi
0x180083678  push    r14
0x18008367a  push    r15
0x18008367c  sub     rsp, 40h
0x180083680  mov     r14, pwszFilename
0x180083683  movzx   r15d, fWrite
0x180083687  mov     rdi, this
0x18008368a  mov     qword ptr [rax+8], 0
0x180083692  mov     this, r14; pwszURL
0x180083695  lea     pwszFilename, [rax+8]; pwszFilePath
0x180083699  call    ?getFilePath@URL@@SAJPEBGPEAPEAG@Z; URL::getFilePath(ushort const *,ushort * *)
0x18008369e  test    eax, eax
0x1800836a0  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x1800836a9  mov     ebp, r15d
0x1800836ac  mov     [rsp+58h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x1800836b4  cmovns  r14, [rsp+58h+pwszFilePath]
0x1800836ba  mov     ebx, eax
0x1800836bc  xor     ebp, 1
0x1800836bf  mov     [rdi+0A8h], r15b
0x1800836c6  xor     r9d, r9d; lpSecurityAttributes
0x1800836c9  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x1800836d1  inc     ebp
0x1800836d3  mov     this, r14; lpFileName
0x1800836d6  shl     ebp, 1Eh
0x1800836d9  mov     edx, ebp; dwDesiredAccess
0x1800836db  lea     r8d, [r9+1]; dwShareMode
0x1800836df  call    cs:__imp_CreateFileW
0x1800836e5  mov     [rdi+0A0h], rax
0x1800836ec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800836f0  jnz     short loc_180083754
0x1800836f2  test    r15b, r15b
0x1800836f5  jz      short loc_18008372F
0x1800836f7  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x180083700  lea     r8d, [rax+2]; dwShareMode
0x180083704  mov     [rsp+58h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x18008370c  xor     r9d, r9d; lpSecurityAttributes
0x18008370f  mov     edx, ebp; dwDesiredAccess
0x180083711  mov     [rsp+58h+dwCreationDisposition], 2; dwCreationDisposition
0x180083719  mov     this, r14; lpFileName
0x18008371c  call    cs:__imp_CreateFileW
0x180083722  mov     [rdi+0A0h], rax
0x180083729  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18008372d  jnz     short loc_180083754
0x18008372f  call    cs:__imp_GetLastError
0x180083735  mov     ebx, eax
0x180083737  test    eax, 0FFFFFFFDh
0x18008373c  jz      short loc_18008374D
0x18008373e  test    eax, eax
0x180083740  jle     short loc_180083783
0x180083742  movzx   ebx, ax
0x180083745  or      ebx, 80070000h
0x18008374b  jmp     short loc_180083783
0x18008374d  mov     ebx, 800C0006h
0x180083752  jmp     short loc_180083783
0x180083754  mov     this, rax; hFile
0x180083757  call    cs:__imp_GetFileType
0x18008375d  test    eax, eax
0x18008375f  jz      short loc_180083766
0x180083761  cmp     eax, 2
0x180083764  jnz     short loc_180083783
0x180083766  mov     this, [rdi+0A0h]; hObject
0x18008376d  call    cs:__imp_CloseHandle
0x180083773  mov     qword ptr [rdi+0A0h], 0FFFFFFFFFFFFFFFFh
0x18008377e  mov     ebx, 80070005h
0x180083783  cmp     [rsp+58h+pwszFilePath], 0
0x180083789  jz      short loc_180083795
0x18008378b  mov     this, [rsp+58h+pwszFilePath]; pv
0x180083790  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180083795  mov     rbp, [rsp+58h+arg_10]
0x18008379a  mov     eax, ebx
0x18008379c  mov     rbx, [rsp+58h+arg_8]
0x1800837a1  add     rsp, 40h
0x1800837a5  pop     r15
0x1800837a7  pop     r14
0x1800837a9  pop     rdi
0x1800837aa  retn
```
