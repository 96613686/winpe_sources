# OpenTextFileByName

- ea: `0x180091064`
- end: `0x1800911d1`
- name: `OpenTextFileByName`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180090f94`

## callees

- `0x180090b78`
- `0x180091064`

## import_xrefs

- `KERNEL32!MapViewOfFile` at `0x180091195`
- `KERNEL32!MapViewOfFile` at `0x180091195`
- `KERNEL32!CreateFileMappingW` at `0x180091150`
- `KERNEL32!CreateFileMappingW` at `0x180091150`
- `KERNEL32!GetFileSize` at `0x1800910e6`
- `KERNEL32!GetFileSize` at `0x1800910e6`
- `KERNEL32!GetLastError` at `0x1800910b0`
- `KERNEL32!GetLastError` at `0x1800910fd`
- `KERNEL32!GetLastError` at `0x18009110d`
- `KERNEL32!GetLastError` at `0x180091168`
- `KERNEL32!GetLastError` at `0x1800911ad`
- `KERNEL32!GetLastError` at `0x1800910b0`
- `KERNEL32!GetLastError` at `0x1800910fd`
- `KERNEL32!GetLastError` at `0x18009110d`
- `KERNEL32!GetLastError` at `0x180091168`
- `KERNEL32!GetLastError` at `0x1800911ad`
- `KERNEL32!CreateFileW` at `0x180091090`
- `KERNEL32!CreateFileW` at `0x180091090`

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
0x180091064  push    rbx
0x180091066  sub     rsp, 40h
0x18009106a  xor     ebx, ebx
0x18009106c  mov     rcx, rdx; lpFileName
0x18009106f  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x180091074  xor     r9d, r9d; lpSecurityAttributes
0x180091077  mov     [rsp+48h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x18009107f  mov     edx, 0C0010000h; dwDesiredAccess
0x180091084  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18009108c  lea     r8d, [rbx+1]; dwShareMode
0x180091090  call    cs:__imp_CreateFileW
0x180091097  nop     dword ptr [rax+rax+00h]
0x18009109c  mov     cs:hTextFile, rax
0x1800910a3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800910a7  jnz     short loc_1800910DC
0x1800910a9  mov     cs:hTextFile, rbx
0x1800910b0  call    cs:__imp_GetLastError
0x1800910b7  nop     dword ptr [rax+rax+00h]
0x1800910bc  mov     ebx, eax
0x1800910be  cmp     eax, 2
0x1800910c1  jz      short loc_1800910D5
0x1800910c3  mov     r8d, eax
0x1800910c6  mov     edx, 29h ; ')'
0x1800910cb  mov     ecx, 1
0x1800910d0  call    DebugLog
0x1800910d5  mov     eax, ebx
0x1800910d7  jmp     loc_1800911CA
0x1800910dc  lea     rdx, HiSize; lpFileSizeHigh
0x1800910e3  mov     rcx, rax; hFile
0x1800910e6  call    cs:__imp_GetFileSize
0x1800910ed  nop     dword ptr [rax+rax+00h]
0x1800910f2  mov     cs:LoSize, eax
0x1800910f8  cmp     eax, 0FFFFFFFFh
0x1800910fb  jnz     short loc_180091124
0x1800910fd  call    cs:__imp_GetLastError
0x180091104  nop     dword ptr [rax+rax+00h]
0x180091109  test    eax, eax
0x18009110b  jz      short loc_18009111E
0x18009110d  call    cs:__imp_GetLastError
0x180091114  nop     dword ptr [rax+rax+00h]
0x180091119  jmp     loc_1800911CA
0x18009111e  mov     eax, cs:LoSize
0x180091124  mov     r9d, cs:HiSize; dwMaximumSizeHigh
0x18009112b  test    eax, eax
0x18009112d  jnz     short loc_180091138
0x18009112f  test    r9d, r9d
0x180091132  jz      loc_1800911C8
0x180091138  mov     rcx, cs:hTextFile; hFile
0x18009113f  xor     edx, edx; lpFileMappingAttributes
0x180091141  mov     qword ptr [rsp+48h+dwFlagsAndAttributes], rbx; lpName
0x180091146  mov     r8d, 8000002h; flProtect
0x18009114c  mov     [rsp+48h+dwCreationDisposition], eax; dwMaximumSizeLow
0x180091150  call    cs:__imp_CreateFileMappingW
0x180091157  nop     dword ptr [rax+rax+00h]
0x18009115c  mov     cs:hMapping, rax
0x180091163  test    rax, rax
0x180091166  jnz     short loc_180091183
0x180091168  call    cs:__imp_GetLastError
0x18009116f  nop     dword ptr [rax+rax+00h]
0x180091174  mov     ebx, eax
0x180091176  mov     r8d, eax
0x180091179  mov     edx, 30h ; '0'
0x18009117e  jmp     loc_1800910CB
0x180091183  xor     r9d, r9d; dwFileOffsetLow
0x180091186  mov     qword ptr [rsp+48h+dwCreationDisposition], rbx; dwNumberOfBytesToMap
0x18009118b  xor     r8d, r8d; dwFileOffsetHigh
0x18009118e  mov     rcx, rax; hFileMappingObject
0x180091191  lea     edx, [r9+4]; dwDesiredAccess
0x180091195  call    cs:__imp_MapViewOfFile
0x18009119c  nop     dword ptr [rax+rax+00h]
0x1800911a1  mov     cs:FileView, rax
0x1800911a8  test    rax, rax
0x1800911ab  jnz     short loc_1800911C8
0x1800911ad  call    cs:__imp_GetLastError
0x1800911b4  nop     dword ptr [rax+rax+00h]
0x1800911b9  mov     ebx, eax
0x1800911bb  mov     r8d, eax
0x1800911be  mov     edx, 31h ; '1'
0x1800911c3  jmp     loc_1800910CB
0x1800911c8  xor     eax, eax
0x1800911ca  add     rsp, 40h
0x1800911ce  pop     rbx
0x1800911cf  retn
```
