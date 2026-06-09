# __fullpath

- ea: `0x1002dffc`
- end: `0x1002e0f7`
- name: `__fullpath`
- size: `251`
- prototype: `char *__cdecl(char *Buffer, const char *Path, size_t BufferCount)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1002b500`

## callees

- `0x1002d6bb`
- `0x1002d6dc`
- `0x1002df32`
- `0x1002dffc`
- `0x10030870`
- `0x10034040`
- `0x100341ed`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1002e02e`
- `KERNEL32!GetLastError` at `0x1002e02e`
- `KERNEL32!GetFullPathNameA` at `0x1002e024`
- `KERNEL32!GetFullPathNameA` at `0x1002e0a5`
- `KERNEL32!GetFullPathNameA` at `0x1002e024`
- `KERNEL32!GetFullPathNameA` at `0x1002e0a5`

## pseudocode

```c
char *__cdecl _fullpath(char *Buffer, const char *Path, size_t BufferCount)
{
  const char *v3; // eax
  size_t FullPathNameA; // eax
  DWORD LastError; // eax
  size_t v7; // esi
  char *v8; // eax
  char *v9; // edi
  DWORD v10; // eax
  LPSTR FilePart; // [esp+Ch] [ebp-4h] BYREF

  v3 = Path;
  if ( !Path || !*Path )
    return _getcwd(Buffer, BufferCount);
  if ( Buffer )
  {
    v7 = BufferCount;
    if ( !BufferCount )
    {
      *_errno() = 22;
      _invalid_parameter_noinfo();
      return 0;
    }
    v9 = Buffer;
  }
  else
  {
    FullPathNameA = GetFullPathNameA(Path, 0, 0, 0);
    if ( !FullPathNameA )
    {
LABEL_5:
      LastError = GetLastError();
      _dosmaperr(LastError);
      return 0;
    }
    v7 = BufferCount;
    if ( BufferCount <= FullPathNameA )
      v7 = FullPathNameA;
    v8 = (char *)calloc(v7, 1u);
    v9 = v8;
    if ( !v8 )
    {
      *_errno() = 12;
      return 0;
    }
    v3 = Path;
  }
  v10 = GetFullPathNameA(v3, v7, v9, &FilePart);
  if ( v10 >= v7 )
  {
    if ( !Buffer )
      free(v9);
    *_errno() = 34;
    return 0;
  }
  if ( !v10 )
  {
    if ( !Buffer )
      free(v9);
    goto LABEL_5;
  }
  return v9;
}

```

## disassembly

```asm
0x1002dffc  push    ebp
0x1002dffd  mov     ebp, esp
0x1002dfff  push    ecx
0x1002e000  mov     eax, [ebp+Path]
0x1002e003  push    ebx
0x1002e004  push    esi
0x1002e005  push    edi
0x1002e006  test    eax, eax
0x1002e008  jz      loc_1002E0E3
0x1002e00e  cmp     byte ptr [eax], 0
0x1002e011  jz      loc_1002E0E3
0x1002e017  mov     ebx, [ebp+Buffer]
0x1002e01a  test    ebx, ebx
0x1002e01c  jnz     short loc_1002E07E
0x1002e01e  xor     ecx, ecx
0x1002e020  push    ecx; lpFilePart
0x1002e021  push    ecx; lpBuffer
0x1002e022  push    ecx; nBufferLength
0x1002e023  push    eax; lpFileName
0x1002e024  call    ds:__imp__GetFullPathNameA@16
0x1002e02a  test    eax, eax
0x1002e02c  jnz     short loc_1002E041
0x1002e02e  call    ds:__imp__GetLastError@0
0x1002e034  push    eax
0x1002e035  call    __dosmaperr
0x1002e03a  xor     eax, eax
0x1002e03c  jmp     loc_1002E0EF
0x1002e041  mov     esi, [ebp+BufferCount]
0x1002e044  cmp     esi, eax
0x1002e046  ja      short loc_1002E04A
0x1002e048  mov     esi, eax
0x1002e04a  cmp     esi, 0FFFFFFFFh
0x1002e04d  jbe     short loc_1002E061
0x1002e04f  call    __errno
0x1002e054  mov     dword ptr [eax], 16h
0x1002e05a  xor     eax, eax
0x1002e05c  jmp     loc_1002E0F0
0x1002e061  push    1; Size
0x1002e063  push    esi; Count
0x1002e064  call    _calloc
0x1002e069  mov     edi, eax
0x1002e06b  pop     ecx
0x1002e06c  pop     ecx
0x1002e06d  test    edi, edi
0x1002e06f  jnz     short loc_1002E09B
0x1002e071  call    __errno
0x1002e076  mov     dword ptr [eax], 0Ch
0x1002e07c  jmp     short loc_1002E05A
0x1002e07e  mov     esi, [ebp+BufferCount]
0x1002e081  test    esi, esi
0x1002e083  jnz     short loc_1002E097
0x1002e085  call    __errno
0x1002e08a  mov     dword ptr [eax], 16h
0x1002e090  call    __invalid_parameter_noinfo
0x1002e095  jmp     short loc_1002E05A
0x1002e097  mov     edi, ebx
0x1002e099  jmp     short loc_1002E09E
0x1002e09b  mov     eax, [ebp+Path]
0x1002e09e  lea     ecx, [ebp+FilePart]
0x1002e0a1  push    ecx; lpFilePart
0x1002e0a2  push    edi; lpBuffer
0x1002e0a3  push    esi; nBufferLength
0x1002e0a4  push    eax; lpFileName
0x1002e0a5  call    ds:__imp__GetFullPathNameA@16
0x1002e0ab  cmp     eax, esi
0x1002e0ad  jb      short loc_1002E0C7
0x1002e0af  test    ebx, ebx
0x1002e0b1  jnz     short loc_1002E0BA
0x1002e0b3  push    edi; Block
0x1002e0b4  call    _free
0x1002e0b9  pop     ecx
0x1002e0ba  call    __errno
0x1002e0bf  mov     dword ptr [eax], 22h ; '"'
0x1002e0c5  jmp     short loc_1002E05A
0x1002e0c7  test    eax, eax
0x1002e0c9  jnz     short loc_1002E0DF
0x1002e0cb  test    ebx, ebx
0x1002e0cd  jnz     loc_1002E02E
0x1002e0d3  push    edi; Block
0x1002e0d4  call    _free
0x1002e0d9  pop     ecx
0x1002e0da  jmp     loc_1002E02E
0x1002e0df  mov     eax, edi
0x1002e0e1  jmp     short loc_1002E0F0
0x1002e0e3  push    [ebp+BufferCount]; SizeInBytes
0x1002e0e6  push    [ebp+Buffer]; DstBuf
0x1002e0e9  call    __getcwd
0x1002e0ee  pop     ecx
0x1002e0ef  pop     ecx
0x1002e0f0  pop     edi
0x1002e0f1  pop     esi
0x1002e0f2  pop     ebx
0x1002e0f3  mov     esp, ebp
0x1002e0f5  pop     ebp
0x1002e0f6  retn
```
