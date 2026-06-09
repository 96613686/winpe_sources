# OpenTextFileByName

- ea: `0x180090ea0`
- end: `0x18009100d`
- name: `OpenTextFileByName`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180090dd0`

## callees

- `0x1800909c8`
- `0x180090ea0`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x180090fd1`
- `KERNEL32!MapViewOfFile` at `0x180090fd1`
- `KERNEL32!CreateFileMappingW` at `0x180090f8c`
- `KERNEL32!CreateFileMappingW` at `0x180090f8c`
- `KERNEL32!GetFileSize` at `0x180090f22`
- `KERNEL32!GetFileSize` at `0x180090f22`
- `KERNEL32!GetLastError` at `0x180090eec`
- `KERNEL32!GetLastError` at `0x180090f39`
- `KERNEL32!GetLastError` at `0x180090f49`
- `KERNEL32!GetLastError` at `0x180090fa4`
- `KERNEL32!GetLastError` at `0x180090fe9`
- `KERNEL32!GetLastError` at `0x180090eec`
- `KERNEL32!GetLastError` at `0x180090f39`
- `KERNEL32!GetLastError` at `0x180090f49`
- `KERNEL32!GetLastError` at `0x180090fa4`
- `KERNEL32!GetLastError` at `0x180090fe9`
- `KERNEL32!CreateFileW` at `0x180090ecc`
- `KERNEL32!CreateFileW` at `0x180090ecc`

## pseudocode

```c
DWORD __fastcall OpenTextFileByName(__int64 a1, const WCHAR *a2)
{
  HANDLE FileW; // rax
  DWORD LastError; // eax
  DWORD v4; // ebx
  __int64 v5; // r8
  __int64 v6; // rdx
  DWORD FileSize; // eax
  HANDLE FileMappingW; // rax

  FileW = CreateFileW(a2, 0xC0010000, 1u, 0, 3u, 0x8000080u, 0);
  hTextFile = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    hTextFile = 0;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError == 2 )
      return v4;
    v5 = LastError;
    v6 = 41;
LABEL_4:
    DebugLog(1, v6, v5);
    return v4;
  }
  FileSize = GetFileSize(FileW, &HiSize);
  LoSize = FileSize;
  if ( FileSize == -1 )
  {
    if ( GetLastError() )
      return GetLastError();
    FileSize = LoSize;
  }
  if ( FileSize || HiSize )
  {
    FileMappingW = CreateFileMappingW(hTextFile, 0, 0x8000002u, HiSize, FileSize, 0);
    hMapping = FileMappingW;
    if ( !FileMappingW )
    {
      v4 = GetLastError();
      v5 = v4;
      v6 = 48;
      goto LABEL_4;
    }
    FileView = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
    if ( !FileView )
    {
      v4 = GetLastError();
      v5 = v4;
      v6 = 49;
      goto LABEL_4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180090ea0  push    rbx
0x180090ea2  sub     rsp, 40h
0x180090ea6  xor     ebx, ebx
0x180090ea8  mov     rcx, rdx; lpFileName
0x180090eab  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x180090eb0  xor     r9d, r9d; lpSecurityAttributes
0x180090eb3  mov     [rsp+48h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x180090ebb  mov     edx, 0C0010000h; dwDesiredAccess
0x180090ec0  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180090ec8  lea     r8d, [rbx+1]; dwShareMode
0x180090ecc  call    cs:__imp_CreateFileW
0x180090ed3  nop     dword ptr [rax+rax+00h]
0x180090ed8  mov     cs:hTextFile, rax
0x180090edf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180090ee3  jnz     short loc_180090F18
0x180090ee5  mov     cs:hTextFile, rbx
0x180090eec  call    cs:__imp_GetLastError
0x180090ef3  nop     dword ptr [rax+rax+00h]
0x180090ef8  mov     ebx, eax
0x180090efa  cmp     eax, 2
0x180090efd  jz      short loc_180090F11
0x180090eff  mov     r8d, eax
0x180090f02  mov     edx, 29h ; ')'
0x180090f07  mov     ecx, 1
0x180090f0c  call    DebugLog
0x180090f11  mov     eax, ebx
0x180090f13  jmp     loc_180091006
0x180090f18  lea     rdx, HiSize; lpFileSizeHigh
0x180090f1f  mov     rcx, rax; hFile
0x180090f22  call    cs:__imp_GetFileSize
0x180090f29  nop     dword ptr [rax+rax+00h]
0x180090f2e  mov     cs:LoSize, eax
0x180090f34  cmp     eax, 0FFFFFFFFh
0x180090f37  jnz     short loc_180090F60
0x180090f39  call    cs:__imp_GetLastError
0x180090f40  nop     dword ptr [rax+rax+00h]
0x180090f45  test    eax, eax
0x180090f47  jz      short loc_180090F5A
0x180090f49  call    cs:__imp_GetLastError
0x180090f50  nop     dword ptr [rax+rax+00h]
0x180090f55  jmp     loc_180091006
0x180090f5a  mov     eax, cs:LoSize
0x180090f60  mov     r9d, cs:HiSize; dwMaximumSizeHigh
0x180090f67  test    eax, eax
0x180090f69  jnz     short loc_180090F74
0x180090f6b  test    r9d, r9d
0x180090f6e  jz      loc_180091004
0x180090f74  mov     rcx, cs:hTextFile; hFile
0x180090f7b  xor     edx, edx; lpFileMappingAttributes
0x180090f7d  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], rbx; lpName
0x180090f82  mov     r8d, 8000002h; flProtect
0x180090f88  mov     [rsp+48h+dwCreationDisposition], eax; dwMaximumSizeLow
0x180090f8c  call    cs:__imp_CreateFileMappingW
0x180090f93  nop     dword ptr [rax+rax+00h]
0x180090f98  mov     cs:hMapping, rax
0x180090f9f  test    rax, rax
0x180090fa2  jnz     short loc_180090FBF
0x180090fa4  call    cs:__imp_GetLastError
0x180090fab  nop     dword ptr [rax+rax+00h]
0x180090fb0  mov     ebx, eax
0x180090fb2  mov     r8d, eax
0x180090fb5  mov     edx, 30h ; '0'
0x180090fba  jmp     loc_180090F07
0x180090fbf  xor     r9d, r9d; dwFileOffsetLow
0x180090fc2  mov     qword ptr [rsp+48h+dwCreationDisposition], rbx; dwNumberOfBytesToMap
0x180090fc7  xor     r8d, r8d; dwFileOffsetHigh
0x180090fca  mov     rcx, rax; hFileMappingObject
0x180090fcd  lea     edx, [r9+4]; dwDesiredAccess
0x180090fd1  call    cs:__imp_MapViewOfFile
0x180090fd8  nop     dword ptr [rax+rax+00h]
0x180090fdd  mov     cs:FileView, rax
0x180090fe4  test    rax, rax
0x180090fe7  jnz     short loc_180091004
0x180090fe9  call    cs:__imp_GetLastError
0x180090ff0  nop     dword ptr [rax+rax+00h]
0x180090ff5  mov     ebx, eax
0x180090ff7  mov     r8d, eax
0x180090ffa  mov     edx, 31h ; '1'
0x180090fff  jmp     loc_180090F07
0x180091004  xor     eax, eax
0x180091006  add     rsp, 40h
0x18009100a  pop     rbx
0x18009100b  retn
```
