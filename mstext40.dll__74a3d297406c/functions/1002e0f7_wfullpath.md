# __wfullpath

- ea: `0x1002e0f7`
- end: `0x1002e1ef`
- name: `__wfullpath`
- size: `248`
- prototype: `wchar_t *__cdecl(wchar_t *Buffer, const wchar_t *Path, size_t BufferCount)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1002b500`

## callees

- `0x1002d6bb`
- `0x1002d6dc`
- `0x1002df32`
- `0x1002e0f7`
- `0x10030870`
- `0x100341ed`
- `0x1003422d`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1002e126`
- `KERNEL32!GetLastError` at `0x1002e126`
- `KERNEL32!GetFullPathNameW` at `0x1002e11c`
- `KERNEL32!GetFullPathNameW` at `0x1002e19c`
- `KERNEL32!GetFullPathNameW` at `0x1002e11c`
- `KERNEL32!GetFullPathNameW` at `0x1002e19c`

## pseudocode

```c
wchar_t *__cdecl _wfullpath(wchar_t *Buffer, const wchar_t *Path, size_t BufferCount)
{
  const WCHAR *v3; // ebx
  size_t FullPathNameW; // eax
  DWORD LastError; // eax
  size_t v7; // esi
  WCHAR *v8; // edi
  DWORD v9; // eax

  v3 = Path;
  if ( !Path || !*Path )
    return _wgetcwd(Buffer, BufferCount);
  if ( Buffer )
  {
    v7 = BufferCount;
    if ( !BufferCount )
    {
      *_errno() = 22;
      _invalid_parameter_noinfo();
      return 0;
    }
    v8 = Buffer;
  }
  else
  {
    FullPathNameW = GetFullPathNameW(Path, 0, 0, 0);
    if ( !FullPathNameW )
    {
LABEL_5:
      LastError = GetLastError();
      _dosmaperr(LastError);
      return 0;
    }
    v7 = BufferCount;
    if ( BufferCount <= FullPathNameW )
      v7 = FullPathNameW;
    if ( v7 > 0x7FFFFFFF )
    {
      *_errno() = 22;
      return 0;
    }
    v8 = (WCHAR *)calloc(v7, 2u);
    if ( !v8 )
    {
      *_errno() = 12;
      return 0;
    }
  }
  v9 = GetFullPathNameW(v3, v7, v8, (LPWSTR *)&Path);
  if ( v9 >= v7 )
  {
    if ( !Buffer )
      free(v8);
    *_errno() = 34;
    return 0;
  }
  if ( !v9 )
  {
    if ( !Buffer )
      free(v8);
    goto LABEL_5;
  }
  return v8;
}

```

## disassembly

```asm
0x1002e0f7  push    ebp
0x1002e0f8  mov     ebp, esp
0x1002e0fa  push    ebx
0x1002e0fb  mov     ebx, [ebp+Path]
0x1002e0fe  push    esi
0x1002e0ff  push    edi
0x1002e100  test    ebx, ebx
0x1002e102  jz      loc_1002E1DD
0x1002e108  xor     eax, eax
0x1002e10a  cmp     [ebx], ax
0x1002e10d  jz      loc_1002E1DD
0x1002e113  cmp     [ebp+Buffer], eax
0x1002e116  jnz     short loc_1002E179
0x1002e118  push    eax; lpFilePart
0x1002e119  push    eax; lpBuffer
0x1002e11a  push    eax; nBufferLength
0x1002e11b  push    ebx; lpFileName
0x1002e11c  call    ds:__imp__GetFullPathNameW@16
0x1002e122  test    eax, eax
0x1002e124  jnz     short loc_1002E139
0x1002e126  call    ds:__imp__GetLastError@0
0x1002e12c  push    eax
0x1002e12d  call    __dosmaperr
0x1002e132  xor     eax, eax
0x1002e134  jmp     loc_1002E1E9
0x1002e139  mov     esi, [ebp+BufferCount]
0x1002e13c  cmp     esi, eax
0x1002e13e  ja      short loc_1002E142
0x1002e140  mov     esi, eax
0x1002e142  cmp     esi, 7FFFFFFFh
0x1002e148  jbe     short loc_1002E15C
0x1002e14a  call    __errno
0x1002e14f  mov     dword ptr [eax], 16h
0x1002e155  xor     eax, eax
0x1002e157  jmp     loc_1002E1EA
0x1002e15c  push    2; Size
0x1002e15e  push    esi; Count
0x1002e15f  call    _calloc
0x1002e164  mov     edi, eax
0x1002e166  pop     ecx
0x1002e167  pop     ecx
0x1002e168  test    edi, edi
0x1002e16a  jnz     short loc_1002E195
0x1002e16c  call    __errno
0x1002e171  mov     dword ptr [eax], 0Ch
0x1002e177  jmp     short loc_1002E155
0x1002e179  mov     esi, [ebp+BufferCount]
0x1002e17c  test    esi, esi
0x1002e17e  jnz     short loc_1002E192
0x1002e180  call    __errno
0x1002e185  mov     dword ptr [eax], 16h
0x1002e18b  call    __invalid_parameter_noinfo
0x1002e190  jmp     short loc_1002E155
0x1002e192  mov     edi, [ebp+Buffer]
0x1002e195  lea     eax, [ebp+Path]
0x1002e198  push    eax; lpFilePart
0x1002e199  push    edi; lpBuffer
0x1002e19a  push    esi; nBufferLength
0x1002e19b  push    ebx; lpFileName
0x1002e19c  call    ds:__imp__GetFullPathNameW@16
0x1002e1a2  cmp     eax, esi
0x1002e1a4  jb      short loc_1002E1C0
0x1002e1a6  cmp     [ebp+Buffer], 0
0x1002e1aa  jnz     short loc_1002E1B3
0x1002e1ac  push    edi; Block
0x1002e1ad  call    _free
0x1002e1b2  pop     ecx
0x1002e1b3  call    __errno
0x1002e1b8  mov     dword ptr [eax], 22h ; '"'
0x1002e1be  jmp     short loc_1002E155
0x1002e1c0  test    eax, eax
0x1002e1c2  jnz     short loc_1002E1D9
0x1002e1c4  cmp     [ebp+Buffer], eax
0x1002e1c7  jnz     loc_1002E126
0x1002e1cd  push    edi; Block
0x1002e1ce  call    _free
0x1002e1d3  pop     ecx
0x1002e1d4  jmp     loc_1002E126
0x1002e1d9  mov     eax, edi
0x1002e1db  jmp     short loc_1002E1EA
0x1002e1dd  push    [ebp+BufferCount]; SizeInWords
0x1002e1e0  push    [ebp+Buffer]; DstBuf
0x1002e1e3  call    __wgetcwd
0x1002e1e8  pop     ecx
0x1002e1e9  pop     ecx
0x1002e1ea  pop     edi
0x1002e1eb  pop     esi
0x1002e1ec  pop     ebx
0x1002e1ed  pop     ebp
0x1002e1ee  retn
```
