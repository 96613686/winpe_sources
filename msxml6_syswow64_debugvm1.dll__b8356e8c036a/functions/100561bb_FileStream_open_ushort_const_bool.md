# FileStream::open(ushort const *,bool)

- ea: `0x100561bb`
- end: `0x100562a1`
- name: `?open@FileStream@@QAEJPBG_N@Z`
- size: `230`
- prototype: `HRESULT __thiscall(FileStream *this, const wchar_t *pwszFilename, bool fWrite)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10131770`
- `0x101317ba`

## callees

- `0x10040dee`
- `0x100561bb`
- `0x100562a7`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1005623d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1005623d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10056279`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10056279`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x10056208`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1005622f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x10056208`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1005622f`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x10056265`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x10056265`

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
0x100561bb  mov     edi, edi
0x100561bd  push    ebp
0x100561be  mov     ebp, esp
0x100561c0  push    this
0x100561c1  push    this
0x100561c2  push    esi
0x100561c3  push    edi
0x100561c4  mov     edi, this
0x100561c6  mov     [ebp+pwszFilePath], 0
0x100561cd  mov     this, [ebp+pwszFilename]; pwszURL
0x100561d0  lea     edx, [ebp+pwszFilePath]; pwszFilePath
0x100561d3  call    ?getFilePath@URL@@SGJPBGPAPAG@Z; URL::getFilePath(ushort const *,ushort * *)
0x100561d8  mov     this, [ebp+pwszFilename]
0x100561db  mov     esi, eax
0x100561dd  mov     al, [ebp+fWrite]
0x100561e0  test    esi, esi
0x100561e2  push    0; hTemplateFile
0x100561e4  cmovns  this, [ebp+pwszFilePath]
0x100561e8  mov     [edi+58h], al
0x100561eb  push    100080h; dwFlagsAndAttributes
0x100561f0  movzx   eax, al
0x100561f3  push    3; dwCreationDisposition
0x100561f5  xor     eax, 1
0x100561f8  mov     [ebp+pwszFilename], this
0x100561fb  push    0; lpSecurityAttributes
0x100561fd  inc     eax
0x100561fe  shl     eax, 1Eh
0x10056201  push    1; dwShareMode
0x10056203  push    eax; dwDesiredAccess
0x10056204  push    this; lpFileName
0x10056205  mov     [ebp+dwDesiredAccess], eax
0x10056208  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x1005620e  mov     [edi+54h], eax
0x10056211  cmp     eax, 0FFFFFFFFh
0x10056214  jnz     short loc_10056264
0x10056216  cmp     [ebp+fWrite], 0
0x1005621a  jz      short loc_1005623D
0x1005621c  push    0; hTemplateFile
0x1005621e  push    100080h; dwFlagsAndAttributes
0x10056223  push    2; dwCreationDisposition
0x10056225  push    0; lpSecurityAttributes
0x10056227  push    1; dwShareMode
0x10056229  push    [ebp+dwDesiredAccess]; dwDesiredAccess
0x1005622c  push    [ebp+pwszFilename]; lpFileName
0x1005622f  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x10056235  mov     [edi+54h], eax
0x10056238  cmp     eax, 0FFFFFFFFh
0x1005623b  jnz     short loc_10056264
0x1005623d  call    ds:__imp__GetLastError@0; GetLastError()
0x10056243  mov     esi, eax
0x10056245  test    esi, esi
0x10056247  jz      short loc_1005625D
0x10056249  cmp     esi, 2
0x1005624c  jz      short loc_1005625D
0x1005624e  test    esi, esi
0x10056250  jle     short loc_1005628B
0x10056252  movzx   esi, si
0x10056255  or      esi, 80070000h
0x1005625b  jmp     short loc_1005628B
0x1005625d  mov     esi, 800C0006h
0x10056262  jmp     short loc_1005628B
0x10056264  push    eax; hFile
0x10056265  call    ds:__imp__GetFileType@4; GetFileType(x)
0x1005626b  sub     eax, 0
0x1005626e  jz      short loc_10056276
0x10056270  dec     eax
0x10056271  sub     eax, 1
0x10056274  jnz     short loc_1005628B
0x10056276  push    dword ptr [edi+54h]; hObject
0x10056279  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1005627f  mov     dword ptr [edi+54h], 0FFFFFFFFh
0x10056286  mov     esi, 80070005h
0x1005628b  cmp     [ebp+pwszFilePath], 0
0x1005628f  jz      short loc_10056299
0x10056291  mov     this, [ebp+pwszFilePath]; pv
0x10056294  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x10056299  pop     edi
0x1005629a  mov     eax, esi
0x1005629c  pop     esi
0x1005629d  leave
0x1005629e  retn    8
```
