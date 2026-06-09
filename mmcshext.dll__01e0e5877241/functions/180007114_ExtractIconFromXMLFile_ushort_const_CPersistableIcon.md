# ExtractIconFromXMLFile(ushort const *,CPersistableIcon &)

- ea: `0x180007114`
- end: `0x180007250`
- name: `?ExtractIconFromXMLFile@@YAJPEBGAEAVCPersistableIcon@@@Z`
- size: `316`
- prototype: `signed int __fastcall(const unsigned __int16 *, struct CPersistableIcon *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180002160`

## callees

- `0x180007114`
- `0x1800074d4`

## import_xrefs

- `KERNEL32!UnmapViewOfFile` at `0x180007216`
- `KERNEL32!UnmapViewOfFile` at `0x180007216`
- `KERNEL32!MapViewOfFile` at `0x1800071f0`
- `KERNEL32!MapViewOfFile` at `0x1800071f0`
- `KERNEL32!CreateFileMappingW` at `0x1800071b5`
- `KERNEL32!CreateFileMappingW` at `0x1800071b5`
- `KERNEL32!CloseHandle` at `0x180007193`
- `KERNEL32!CloseHandle` at `0x180007236`
- `KERNEL32!CloseHandle` at `0x18000723f`
- `KERNEL32!CloseHandle` at `0x180007193`
- `KERNEL32!CloseHandle` at `0x180007236`
- `KERNEL32!CloseHandle` at `0x18000723f`
- `KERNEL32!GetFileSizeEx` at `0x180007186`
- `KERNEL32!GetFileSizeEx` at `0x180007186`
- `KERNEL32!CreateFileW` at `0x180007145`
- `KERNEL32!CreateFileW` at `0x180007145`
- `KERNEL32!GetLastError` at `0x180007154`
- `KERNEL32!GetLastError` at `0x1800071c3`
- `KERNEL32!GetLastError` at `0x18000721e`
- `KERNEL32!GetLastError` at `0x180007154`
- `KERNEL32!GetLastError` at `0x1800071c3`
- `KERNEL32!GetLastError` at `0x18000721e`

## pseudocode

```c
signed int __fastcall ExtractIconFromXMLFile(const unsigned __int16 *a1, struct CPersistableIcon *a2)
{
  HANDLE FileW; // rax
  void *v4; // rdi
  signed int result; // eax
  HANDLE FileMappingW; // rax
  void *v7; // rsi
  signed int v8; // eax
  unsigned int v9; // ebx
  const void *v10; // rax
  const void *v11; // rbp
  signed int LastError; // eax
  union _LARGE_INTEGER FileSize; // [rsp+80h] [rbp+18h] BYREF

  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_2;
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    CloseHandle(v4);
LABEL_2:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  FileMappingW = CreateFileMappingW(v4, 0, 2u, 0, 0, 0);
  v7 = FileMappingW;
  if ( FileMappingW )
  {
    v10 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
    v11 = v10;
    if ( v10 )
    {
      v9 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))LoadIconFromXMLData)(
             v10,
             (union _LARGE_INTEGER)FileSize.QuadPart,
             a2);
      UnmapViewOfFile(v11);
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(v7);
  }
  else
  {
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
  }
  CloseHandle(v4);
  return v9;
}

```

## disassembly

```asm
0x180007114  push    rbx
0x180007116  push    rbp
0x180007117  push    rsi
0x180007118  push    rdi
0x180007119  sub     rsp, 48h
0x18000711d  xor     r9d, r9d; lpSecurityAttributes
0x180007120  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180007129  mov     rbx, rdx
0x18000712c  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180007134  mov     edx, 80000000h; dwDesiredAccess
0x180007139  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180007141  lea     r8d, [r9+1]; dwShareMode
0x180007145  call    cs:__imp_CreateFileW
0x18000714b  mov     rdi, rax
0x18000714e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007152  jnz     short loc_18000716F
0x180007154  call    cs:__imp_GetLastError
0x18000715a  test    eax, eax
0x18000715c  jle     loc_180007247
0x180007162  movzx   eax, ax
0x180007165  or      eax, 80070000h
0x18000716a  jmp     loc_180007247
0x18000716f  lea     rdx, [rsp+68h+FileSize]; lpFileSize
0x180007177  mov     qword ptr [rsp+68h+FileSize], 0
0x180007183  mov     rcx, rdi; hFile
0x180007186  call    cs:__imp_GetFileSizeEx
0x18000718c  mov     rcx, rdi; hFile
0x18000718f  test    eax, eax
0x180007191  jnz     short loc_18000719B
0x180007193  call    cs:__imp_CloseHandle
0x180007199  jmp     short loc_180007154
0x18000719b  xor     r9d, r9d; dwMaximumSizeHigh
0x18000719e  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; lpName
0x1800071a7  xor     edx, edx; lpFileMappingAttributes
0x1800071a9  mov     [rsp+68h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1800071b1  lea     r8d, [r9+2]; flProtect
0x1800071b5  call    cs:__imp_CreateFileMappingW
0x1800071bb  mov     rsi, rax
0x1800071be  test    rax, rax
0x1800071c1  jnz     short loc_1800071DA
0x1800071c3  call    cs:__imp_GetLastError
0x1800071c9  mov     ebx, eax
0x1800071cb  test    eax, eax
0x1800071cd  jle     short loc_18000723C
0x1800071cf  movzx   ebx, ax
0x1800071d2  or      ebx, 80070000h
0x1800071d8  jmp     short loc_18000723C
0x1800071da  xor     r9d, r9d; dwFileOffsetLow
0x1800071dd  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1800071e6  xor     r8d, r8d; dwFileOffsetHigh
0x1800071e9  mov     rcx, rsi; hFileMappingObject
0x1800071ec  lea     edx, [r9+4]; dwDesiredAccess
0x1800071f0  call    cs:__imp_MapViewOfFile
0x1800071f6  mov     rbp, rax
0x1800071f9  test    rax, rax
0x1800071fc  jz      short loc_18000721E
0x1800071fe  mov     rdx, qword ptr [rsp+68h+FileSize]
0x180007206  mov     r8, rbx
0x180007209  mov     rcx, rax
0x18000720c  call    LoadIconFromXMLData
0x180007211  mov     rcx, rbp; lpBaseAddress
0x180007214  mov     ebx, eax
0x180007216  call    cs:__imp_UnmapViewOfFile
0x18000721c  jmp     short loc_180007233
0x18000721e  call    cs:__imp_GetLastError
0x180007224  mov     ebx, eax
0x180007226  test    eax, eax
0x180007228  jle     short loc_180007233
0x18000722a  movzx   ebx, ax
0x18000722d  or      ebx, 80070000h
0x180007233  mov     rcx, rsi; hObject
0x180007236  call    cs:__imp_CloseHandle
0x18000723c  mov     rcx, rdi; hObject
0x18000723f  call    cs:__imp_CloseHandle
0x180007245  mov     eax, ebx
0x180007247  add     rsp, 48h
0x18000724b  pop     rdi
0x18000724c  pop     rsi
0x18000724d  pop     rbp
0x18000724e  pop     rbx
0x18000724f  retn
```
