# FileStream::open(ushort const *,bool)

- ea: `0x1005612b`
- end: `0x10056211`
- name: `?open@FileStream@@QAEJPBG_N@Z`
- size: `230`
- prototype: `HRESULT __thiscall(FileStream *this, const wchar_t *pwszFilename, bool fWrite)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10131880`
- `0x101318ca`

## callees

- `0x10040d5e`
- `0x1005612b`
- `0x10056217`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100561ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100561ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100561e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x100561e9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x10056178`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1005619f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x10056178`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1005619f`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x100561d5`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x100561d5`

## pseudocode

```c
unsigned int __thiscall FileStream::open(FileStream *this, wchar_t *pwszFilename, bool fWrite)
{
  int FilePath; // eax
  wchar_t *v5; // ecx
  unsigned int v6; // esi
  HANDLE FileW; // eax
  signed int LastError; // eax
  DWORD FileType; // eax
  int dwDesiredAccess; // [esp+8h] [ebp-8h]
  wchar_t *pwszFilePath; // [esp+Ch] [ebp-4h] BYREF
  const wchar_t *pwszFilenamea; // [esp+18h] [ebp+8h]

  pwszFilePath = 0;
  FilePath = URL::getFilePath(pwszFilename, &pwszFilePath);
  v5 = pwszFilename;
  v6 = FilePath;
  if ( FilePath >= 0 )
    v5 = pwszFilePath;
  this->_fWrite = fWrite;
  pwszFilenamea = v5;
  dwDesiredAccess = (!fWrite + 1) << 30;
  FileW = CreateFileW(v5, dwDesiredAccess, 1u, 0, 3u, 0x100080u, 0);
  this->_hFile = FileW;
  if ( FileW == (HANDLE)-1
    && (!fWrite
     || (FileW = CreateFileW(pwszFilenamea, dwDesiredAccess, 1u, 0, 2u, 0x100080u, 0),
         this->_hFile = FileW,
         FileW == (HANDLE)-1)) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( !LastError || LastError == 2 )
    {
      v6 = -2146697210;
    }
    else if ( LastError > 0 )
    {
      v6 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    FileType = GetFileType(FileW);
    if ( !FileType || FileType == 2 )
    {
      CloseHandle(this->_hFile);
      this->_hFile = (void *)-1;
      v6 = -2147024891;
    }
  }
  if ( pwszFilePath )
    MemFree(pwszFilePath);
  return v6;
}

```

## disassembly

```asm
0x1005612b  mov     edi, edi
0x1005612d  push    ebp
0x1005612e  mov     ebp, esp
0x10056130  push    this
0x10056131  push    this
0x10056132  push    esi
0x10056133  push    edi
0x10056134  mov     edi, this
0x10056136  mov     [ebp+pwszFilePath], 0
0x1005613d  mov     this, [ebp+pwszFilename]; pwszURL
0x10056140  lea     edx, [ebp+pwszFilePath]; pwszFilePath
0x10056143  call    ?getFilePath@URL@@SGJPBGPAPAG@Z; URL::getFilePath(ushort const *,ushort * *)
0x10056148  mov     this, [ebp+pwszFilename]
0x1005614b  mov     esi, eax
0x1005614d  mov     al, [ebp+fWrite]
0x10056150  test    esi, esi
0x10056152  push    0; hTemplateFile
0x10056154  cmovns  this, [ebp+pwszFilePath]
0x10056158  mov     [edi+58h], al
0x1005615b  push    100080h; dwFlagsAndAttributes
0x10056160  movzx   eax, al
0x10056163  push    3; dwCreationDisposition
0x10056165  xor     eax, 1
0x10056168  mov     [ebp+pwszFilename], this
0x1005616b  push    0; lpSecurityAttributes
0x1005616d  inc     eax
0x1005616e  shl     eax, 1Eh
0x10056171  push    1; dwShareMode
0x10056173  push    eax; dwDesiredAccess
0x10056174  push    this; lpFileName
0x10056175  mov     [ebp+dwDesiredAccess], eax
0x10056178  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x1005617e  mov     [edi+54h], eax
0x10056181  cmp     eax, 0FFFFFFFFh
0x10056184  jnz     short loc_100561D4
0x10056186  cmp     [ebp+fWrite], 0
0x1005618a  jz      short loc_100561AD
0x1005618c  push    0; hTemplateFile
0x1005618e  push    100080h; dwFlagsAndAttributes
0x10056193  push    2; dwCreationDisposition
0x10056195  push    0; lpSecurityAttributes
0x10056197  push    1; dwShareMode
0x10056199  push    [ebp+dwDesiredAccess]; dwDesiredAccess
0x1005619c  push    [ebp+pwszFilename]; lpFileName
0x1005619f  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x100561a5  mov     [edi+54h], eax
0x100561a8  cmp     eax, 0FFFFFFFFh
0x100561ab  jnz     short loc_100561D4
0x100561ad  call    ds:__imp__GetLastError@0; GetLastError()
0x100561b3  mov     esi, eax
0x100561b5  test    esi, esi
0x100561b7  jz      short loc_100561CD
0x100561b9  cmp     esi, 2
0x100561bc  jz      short loc_100561CD
0x100561be  test    esi, esi
0x100561c0  jle     short loc_100561FB
0x100561c2  movzx   esi, si
0x100561c5  or      esi, 80070000h
0x100561cb  jmp     short loc_100561FB
0x100561cd  mov     esi, 800C0006h
0x100561d2  jmp     short loc_100561FB
0x100561d4  push    eax; hFile
0x100561d5  call    ds:__imp__GetFileType@4; GetFileType(x)
0x100561db  sub     eax, 0
0x100561de  jz      short loc_100561E6
0x100561e0  dec     eax
0x100561e1  sub     eax, 1
0x100561e4  jnz     short loc_100561FB
0x100561e6  push    dword ptr [edi+54h]; hObject
0x100561e9  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x100561ef  mov     dword ptr [edi+54h], 0FFFFFFFFh
0x100561f6  mov     esi, 80070005h
0x100561fb  cmp     [ebp+pwszFilePath], 0
0x100561ff  jz      short loc_10056209
0x10056201  mov     this, [ebp+pwszFilePath]; pv
0x10056204  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10056209  pop     edi
0x1005620a  mov     eax, esi
0x1005620c  pop     esi
0x1005620d  leave
0x1005620e  retn    8
```
