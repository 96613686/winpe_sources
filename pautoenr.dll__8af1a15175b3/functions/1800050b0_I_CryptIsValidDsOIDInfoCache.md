# I_CryptIsValidDsOIDInfoCache

- ea: `0x1800050b0`
- end: `0x1800051f7`
- name: `I_CryptIsValidDsOIDInfoCache`
- size: `327`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003d10`

## callees

- `0x180001100`
- `0x1800050b0`
- `0x180005200`
- `0x180005240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000511d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000511d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005155`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800051ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005155`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800051ec`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800051c6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800051c6`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180005199`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180005199`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000510e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000510e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000513e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000513e`

## pseudocode

```c
__int64 I_CryptIsValidDsOIDInfoCache()
{
  WCHAR *DsOIDInfoCacheFileName; // rsi
  unsigned int v1; // ebp
  unsigned int v2; // edi
  HANDLE FileW; // rbx
  DWORD LastError; // eax
  DWORD FileSize; // eax
  DWORD NumberOfBytesRead; // [rsp+70h] [rbp+8h] BYREF
  __int64 Buffer; // [rsp+78h] [rbp+10h] BYREF

  Buffer = 0;
  NumberOfBytesRead = 0;
  DsOIDInfoCacheFileName = GetDsOIDInfoCacheFileName(0);
  if ( !DsOIDInfoCacheFileName )
  {
LABEL_13:
    FileW = 0;
    PkiFree(DsOIDInfoCacheFileName);
    goto LABEL_14;
  }
  v1 = 0;
  v2 = 1;
  while ( 1 )
  {
    FileW = CreateFileW(DsOIDInfoCacheFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( FileW != (HANDLE)-1LL )
      break;
    LastError = GetLastError();
    if ( LastError == 32 )
    {
      if ( v1 >= 6 )
        goto LABEL_12;
    }
    else
    {
      if ( LastError != 5 )
      {
        if ( LastError == 3 )
          LastError = 2;
LABEL_12:
        SetLastError(LastError);
        goto LABEL_13;
      }
      if ( v1 )
        goto LABEL_12;
    }
    Sleep(*((_DWORD *)qword_18000B3E0 + v1++));
  }
  PkiFree(DsOIDInfoCacheFileName);
  if ( !FileW )
    goto LABEL_14;
  FileSize = GetFileSize(FileW, 0);
  if ( FileSize == -1 || FileSize - 8 > 0x632EA00 )
    goto LABEL_23;
  if ( !ReadFile(FileW, &Buffer, 8u, &NumberOfBytesRead, 0) )
  {
LABEL_14:
    v2 = 0;
    goto LABEL_15;
  }
  if ( NumberOfBytesRead != 8 || (_DWORD)Buffer != 1 || HIDWORD(Buffer) > 0xF4240 )
  {
LABEL_23:
    SetLastError(0xDu);
    goto LABEL_14;
  }
LABEL_15:
  CloseHandle(FileW);
  return v2;
}

```

## disassembly

```asm
0x1800050b0  mov     [rsp+arg_10], rbx
0x1800050b5  push    rbp
0x1800050b6  push    rsi
0x1800050b7  push    rdi
0x1800050b8  push    r14
0x1800050ba  push    r15
0x1800050bc  sub     rsp, 40h
0x1800050c0  xor     r14d, r14d
0x1800050c3  xor     ecx, ecx
0x1800050c5  mov     [rsp+68h+Buffer], r14
0x1800050ca  mov     [rsp+68h+NumberOfBytesRead], r14d
0x1800050cf  call    _GetDsOIDInfoCacheFileName
0x1800050d4  mov     rsi, rax
0x1800050d7  test    rax, rax
0x1800050da  jz      short loc_18000515B
0x1800050dc  mov     ebp, r14d
0x1800050df  mov     edi, 1
0x1800050e4  lea     r15, qword_18000B3E0
0x1800050eb  mov     [rsp+68h+hTemplateFile], r14; hTemplateFile
0x1800050f0  xor     r9d, r9d; lpSecurityAttributes
0x1800050f3  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800050fb  mov     r8d, edi; dwShareMode
0x1800050fe  mov     edx, 80000000h; dwDesiredAccess
0x180005103  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18000510b  mov     rcx, rsi; lpFileName
0x18000510e  call    cs:__imp_CreateFileW
0x180005114  mov     rbx, rax
0x180005117  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000511b  jnz     short loc_180005187
0x18000511d  call    cs:__imp_GetLastError
0x180005123  cmp     eax, 20h ; ' '
0x180005126  jnz     short loc_18000512F
0x180005128  cmp     ebp, 6
0x18000512b  jb      short loc_180005138
0x18000512d  jmp     short loc_180005153
0x18000512f  cmp     eax, 5
0x180005132  jnz     short loc_180005148
0x180005134  cmp     ebp, edi
0x180005136  jnb     short loc_180005153
0x180005138  mov     ecx, ebp
0x18000513a  mov     ecx, [r15+rcx*4]; dwMilliseconds
0x18000513e  call    cs:__imp_Sleep
0x180005144  inc     ebp
0x180005146  jmp     short loc_1800050EB
0x180005148  cmp     eax, 3
0x18000514b  mov     ecx, 2
0x180005150  cmovz   eax, ecx
0x180005153  mov     ecx, eax; dwErrCode
0x180005155  call    cs:__imp_SetLastError
0x18000515b  mov     rcx, rsi; hMem
0x18000515e  mov     rbx, r14
0x180005161  call    PkiFree
0x180005166  mov     edi, r14d
0x180005169  mov     rcx, rbx; hObject
0x18000516c  call    _CloseHandle
0x180005171  mov     rbx, [rsp+68h+arg_10]
0x180005179  mov     eax, edi
0x18000517b  add     rsp, 40h
0x18000517f  pop     r15
0x180005181  pop     r14
0x180005183  pop     rdi
0x180005184  pop     rsi
0x180005185  pop     rbp
0x180005186  retn
0x180005187  mov     rcx, rsi; hMem
0x18000518a  call    PkiFree
0x18000518f  test    rbx, rbx
0x180005192  jz      short loc_180005166
0x180005194  xor     edx, edx; lpFileSizeHigh
0x180005196  mov     rcx, rbx; hFile
0x180005199  call    cs:__imp_GetFileSize
0x18000519f  cmp     eax, 0FFFFFFFFh
0x1800051a2  jz      short loc_1800051E7
0x1800051a4  add     eax, 0FFFFFFF8h
0x1800051a7  cmp     eax, 632EA00h
0x1800051ac  ja      short loc_1800051E7
0x1800051ae  lea     r9, [rsp+68h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800051b3  mov     qword ptr [rsp+68h+dwCreationDisposition], r14; lpOverlapped
0x1800051b8  mov     r8d, 8; nNumberOfBytesToRead
0x1800051be  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x1800051c3  mov     rcx, rbx; hFile
0x1800051c6  call    cs:__imp_ReadFile
0x1800051cc  test    eax, eax
0x1800051ce  jz      short loc_180005166
0x1800051d0  cmp     [rsp+68h+NumberOfBytesRead], 8
0x1800051d5  jnz     short loc_1800051E7
0x1800051d7  cmp     dword ptr [rsp+68h+Buffer], edi
0x1800051db  jnz     short loc_1800051E7
0x1800051dd  cmp     dword ptr [rsp+68h+Buffer+4], 0F4240h
0x1800051e5  jbe     short loc_180005169
0x1800051e7  mov     ecx, 0Dh; dwErrCode
0x1800051ec  call    cs:__imp_SetLastError
0x1800051f2  jmp     loc_180005166
```
