# RetrieveBLOBFromFile

- ea: `0x18009db4c`
- end: `0x18009dcf5`
- name: `RetrieveBLOBFromFile`
- size: `425`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18002d430`

## callees

- `0x18009db4c`
- `0x1800bec20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dc7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dcc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dc7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dcc1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18009dbbc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18009dbbc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009dc14`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009dc14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009dc96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009dce6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009dc96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009dce6`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18009dc64`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18009dc64`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x18009dc44`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateFileMappingA` at `0x18009dc44`

## pseudocode

```c
__int64 __fastcall RetrieveBLOBFromFile(LPCWSTR lpFileName, _DWORD *a2, _QWORD *a3, _QWORD *a4)
{
  SIZE_T v8; // rbp
  HANDLE FileW; // rax
  void *v10; // rdi
  HANDLE FileMappingA; // rax
  void *v12; // rsi
  LPVOID v13; // rax
  unsigned int v14; // ebx
  signed int LastError; // eax
  signed int v17; // eax
  __int128 FileInformation; // [rsp+40h] [rbp-68h] BYREF
  __int128 v19; // [rsp+50h] [rbp-58h]
  SIZE_T dwNumberOfBytesToMap; // [rsp+60h] [rbp-48h]

  LODWORD(dwNumberOfBytesToMap) = 0;
  FileInformation = 0;
  v19 = 0;
  if ( a2 && a3 && lpFileName && a4 )
  {
    *a3 = 0;
    *a2 = 0;
    *a4 = 0;
    if ( GetFileAttributesExW(lpFileName, GetFileExInfoStandard, &FileInformation) )
    {
      if ( (FileInformation & 0x10) != 0 )
        return (unsigned int)-2147467259;
      if ( HIDWORD(v19) )
        return (unsigned int)-2147467259;
      v8 = (unsigned int)dwNumberOfBytesToMap;
      if ( !(_DWORD)dwNumberOfBytesToMap )
        return (unsigned int)-2147467259;
      FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
      v10 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        FileMappingA = CreateFileMappingA(FileW, 0, 2u, 0, 0, 0);
        v12 = FileMappingA;
        if ( FileMappingA && (v13 = MapViewOfFile(FileMappingA, 4u, 0, 0, v8)) != 0 )
        {
          *a2 = v8;
          v14 = 0;
          *a3 = v13;
          *a4 = v10;
        }
        else
        {
          LastError = GetLastError();
          v14 = LastError;
          if ( LastError > 0 )
            v14 = (unsigned __int16)LastError | 0x80070000;
          if ( v10 )
            CloseHandle(v10);
          if ( !v12 )
            return v14;
        }
        CloseHandle(v12);
        return v14;
      }
    }
    v17 = GetLastError();
    v14 = v17;
    if ( v17 > 0 )
      return (unsigned __int16)v17 | 0x80070000;
    return v14;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18009db4c  push    rbx
0x18009db4e  push    rbp
0x18009db4f  push    rsi
0x18009db50  push    rdi
0x18009db51  push    r12
0x18009db53  push    r14
0x18009db55  push    r15
0x18009db57  sub     rsp, 70h
0x18009db5b  mov     rax, cs:__security_cookie
0x18009db62  xor     rax, rsp
0x18009db65  mov     [rsp+0A8h+var_40], rax
0x18009db6a  xor     eax, eax
0x18009db6c  xorps   xmm0, xmm0
0x18009db6f  mov     dword ptr [rsp+0A8h+dwNumberOfBytesToMap], eax
0x18009db73  mov     r15, r9
0x18009db76  mov     r14, r8
0x18009db79  mov     r12, rdx
0x18009db7c  mov     rbx, rcx
0x18009db7f  movups  [rsp+0A8h+FileInformation], xmm0
0x18009db84  movups  [rsp+0A8h+var_58], xmm0
0x18009db89  test    rdx, rdx
0x18009db8c  jz      loc_18009DCBA
0x18009db92  test    r8, r8
0x18009db95  jz      loc_18009DCBA
0x18009db9b  test    rcx, rcx
0x18009db9e  jz      loc_18009DCBA
0x18009dba4  test    r9, r9
0x18009dba7  jz      loc_18009DCBA
0x18009dbad  mov     [r8], rax
0x18009dbb0  lea     r8, [rsp+0A8h+FileInformation]; lpFileInformation
0x18009dbb5  mov     [rdx], eax
0x18009dbb7  xor     edx, edx; fInfoLevelId
0x18009dbb9  mov     [r9], rax
0x18009dbbc  call    cs:__imp_GetFileAttributesExW
0x18009dbc2  test    eax, eax
0x18009dbc4  jz      loc_18009DCC1
0x18009dbca  test    byte ptr [rsp+0A8h+FileInformation], 10h
0x18009dbcf  jnz     loc_18009DCEE
0x18009dbd5  cmp     dword ptr [rsp+0A8h+var_58+0Ch], 0
0x18009dbda  jnz     loc_18009DCEE
0x18009dbe0  mov     ebp, dword ptr [rsp+0A8h+dwNumberOfBytesToMap]
0x18009dbe4  test    ebp, ebp
0x18009dbe6  jz      loc_18009DCEE
0x18009dbec  xor     r9d, r9d; lpSecurityAttributes
0x18009dbef  mov     [rsp+0A8h+hTemplateFile], 0; hTemplateFile
0x18009dbf8  mov     [rsp+0A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18009dc00  mov     edx, 80000000h; dwDesiredAccess
0x18009dc05  mov     rcx, rbx; lpFileName
0x18009dc08  mov     [rsp+0A8h+dwCreationDisposition], 3; dwCreationDisposition
0x18009dc10  lea     r8d, [r9+1]; dwShareMode
0x18009dc14  call    cs:__imp_CreateFileW
0x18009dc1a  mov     rdi, rax
0x18009dc1d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009dc21  jz      loc_18009DCC1
0x18009dc27  xor     r9d, r9d; dwMaximumSizeHigh
0x18009dc2a  mov     qword ptr [rsp+0A8h+dwFlagsAndAttributes], 0; lpName
0x18009dc33  xor     edx, edx; lpFileMappingAttributes
0x18009dc35  mov     [rsp+0A8h+dwCreationDisposition], 0; dwMaximumSizeLow
0x18009dc3d  mov     rcx, rax; hFile
0x18009dc40  lea     r8d, [r9+2]; flProtect
0x18009dc44  call    cs:__imp_CreateFileMappingA
0x18009dc4a  mov     rsi, rax
0x18009dc4d  test    rax, rax
0x18009dc50  jz      short loc_18009DC7D
0x18009dc52  xor     r9d, r9d; dwFileOffsetLow
0x18009dc55  mov     qword ptr [rsp+0A8h+dwCreationDisposition], rbp; dwNumberOfBytesToMap
0x18009dc5a  xor     r8d, r8d; dwFileOffsetHigh
0x18009dc5d  mov     rcx, rax; hFileMappingObject
0x18009dc60  lea     edx, [r9+4]; dwDesiredAccess
0x18009dc64  call    cs:__imp_MapViewOfFile
0x18009dc6a  test    rax, rax
0x18009dc6d  jz      short loc_18009DC7D
0x18009dc6f  mov     [r12], ebp
0x18009dc73  xor     ebx, ebx
0x18009dc75  mov     [r14], rax
0x18009dc78  mov     [r15], rdi
0x18009dc7b  jmp     short loc_18009DC93
0x18009dc7d  call    cs:__imp_GetLastError
0x18009dc83  mov     ebx, eax
0x18009dc85  test    eax, eax
0x18009dc87  jg      short loc_18009DCD8
0x18009dc89  test    rdi, rdi
0x18009dc8c  jnz     short loc_18009DCE3
0x18009dc8e  test    rsi, rsi
0x18009dc91  jz      short loc_18009DC9C
0x18009dc93  mov     rcx, rsi; hObject
0x18009dc96  call    cs:__imp_CloseHandle
0x18009dc9c  mov     eax, ebx
0x18009dc9e  mov     rcx, [rsp+0A8h+var_40]
0x18009dca3  xor     rcx, rsp; StackCookie
0x18009dca6  call    __security_check_cookie
0x18009dcab  add     rsp, 70h
0x18009dcaf  pop     r15
0x18009dcb1  pop     r14
0x18009dcb3  pop     r12
0x18009dcb5  pop     rdi
0x18009dcb6  pop     rsi
0x18009dcb7  pop     rbp
0x18009dcb8  pop     rbx
0x18009dcb9  retn
0x18009dcba  mov     eax, 80070057h
0x18009dcbf  jmp     short loc_18009DC9E
0x18009dcc1  call    cs:__imp_GetLastError
0x18009dcc7  mov     ebx, eax
0x18009dcc9  test    eax, eax
0x18009dccb  jle     short loc_18009DC9C
0x18009dccd  movzx   ebx, ax
0x18009dcd0  or      ebx, 80070000h
0x18009dcd6  jmp     short loc_18009DC9C
0x18009dcd8  movzx   ebx, ax
0x18009dcdb  or      ebx, 80070000h
0x18009dce1  jmp     short loc_18009DC89
0x18009dce3  mov     rcx, rdi; hObject
0x18009dce6  call    cs:__imp_CloseHandle
0x18009dcec  jmp     short loc_18009DC8E
0x18009dcee  mov     ebx, 80004005h
0x18009dcf3  jmp     short loc_18009DC9C
```
