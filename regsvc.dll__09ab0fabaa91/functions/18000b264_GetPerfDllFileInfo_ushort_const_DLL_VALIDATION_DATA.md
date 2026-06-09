# GetPerfDllFileInfo(ushort const *,DLL_VALIDATION_DATA *)

- ea: `0x18000b264`
- end: `0x18000b34a`
- name: `?GetPerfDllFileInfo@@YAJPEBGPEAUDLL_VALIDATION_DATA@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(const unsigned __int16 *, FILETIME *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x1800136b0`

## callees

- `0x18000b264`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b335`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b335`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b32d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b32d`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18000b2bc`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18000b2bc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b29d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b29d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000b306`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18000b306`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x18000b2e1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x18000b2e1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x18000b2f8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x18000b2f8`

## pseudocode

```c
__int64 __fastcall GetPerfDllFileInfo(const unsigned __int16 *a1, FILETIME *a2)
{
  HANDLE FileW; // rax
  void *v4; // rdi
  DWORD LastError; // ebx
  FILETIME FileSizeHigh; // [rsp+40h] [rbp-18h] BYREF
  WORD FatTime; // [rsp+70h] [rbp+18h] BYREF
  WORD FatDate; // [rsp+78h] [rbp+20h] BYREF

  FileSizeHigh.dwHighDateTime = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    return GetLastError();
  }
  else
  {
    if ( !GetFileTime(FileW, a2, 0, 0) )
      goto LABEL_7;
    FatDate = 0;
    FatTime = 0;
    if ( FileTimeToDosDateTime(a2, &FatDate, &FatTime) )
      DosDateTimeToFileTime(FatDate, FatTime, a2);
    FileSizeHigh.dwLowDateTime = GetFileSize(v4, &FileSizeHigh.dwHighDateTime);
    if ( FileSizeHigh.dwLowDateTime == -1 )
    {
LABEL_7:
      LastError = GetLastError();
    }
    else
    {
      a2[1] = FileSizeHigh;
      LastError = 0;
    }
    CloseHandle(v4);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000b264  mov     rax, rsp
0x18000b267  mov     [rax+8], rbx
0x18000b26b  push    rdi
0x18000b26c  sub     rsp, 50h
0x18000b270  mov     qword ptr [rax-28h], 0
0x18000b278  xor     r9d, r9d; lpSecurityAttributes
0x18000b27b  mov     rbx, rdx
0x18000b27e  mov     dword ptr [rax-30h], 80h
0x18000b285  mov     edx, 80000000h; dwDesiredAccess
0x18000b28a  mov     qword ptr [rax-18h], 0
0x18000b292  mov     dword ptr [rax-38h], 3
0x18000b299  lea     r8d, [r9+1]; dwShareMode
0x18000b29d  call    cs:__imp_CreateFileW
0x18000b2a3  mov     rdi, rax
0x18000b2a6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b2aa  jz      loc_18000B335
0x18000b2b0  xor     r9d, r9d; lpLastWriteTime
0x18000b2b3  xor     r8d, r8d; lpLastAccessTime
0x18000b2b6  mov     rdx, rbx; lpCreationTime
0x18000b2b9  mov     rcx, rax; hFile
0x18000b2bc  call    cs:__imp_GetFileTime
0x18000b2c2  test    eax, eax
0x18000b2c4  jz      short loc_18000B322
0x18000b2c6  xor     ecx, ecx
0x18000b2c8  lea     r8, [rsp+58h+FatTime]; lpFatTime
0x18000b2cd  mov     [rsp+58h+FatDate], cx
0x18000b2d2  lea     rdx, [rsp+58h+FatDate]; lpFatDate
0x18000b2d7  xor     eax, eax
0x18000b2d9  mov     rcx, rbx; lpFileTime
0x18000b2dc  mov     [rsp+58h+FatTime], ax
0x18000b2e1  call    cs:__imp_FileTimeToDosDateTime
0x18000b2e7  test    eax, eax
0x18000b2e9  jz      short loc_18000B2FE
0x18000b2eb  movzx   edx, [rsp+58h+FatTime]; wFatTime
0x18000b2f0  mov     r8, rbx; lpFileTime
0x18000b2f3  movzx   ecx, [rsp+58h+FatDate]; wFatDate
0x18000b2f8  call    cs:__imp_DosDateTimeToFileTime
0x18000b2fe  lea     rdx, [rsp+58h+FileSizeHigh.dwHighDateTime]; lpFileSizeHigh
0x18000b303  mov     rcx, rdi; hFile
0x18000b306  call    cs:__imp_GetFileSize
0x18000b30c  mov     [rsp+58h+FileSizeHigh.dwLowDateTime], eax
0x18000b310  cmp     eax, 0FFFFFFFFh
0x18000b313  jz      short loc_18000B322
0x18000b315  mov     rax, qword ptr [rsp+58h+FileSizeHigh.dwLowDateTime]
0x18000b31a  mov     [rbx+8], rax
0x18000b31e  xor     ebx, ebx
0x18000b320  jmp     short loc_18000B32A
0x18000b322  call    cs:__imp_GetLastError
0x18000b328  mov     ebx, eax
0x18000b32a  mov     rcx, rdi; hObject
0x18000b32d  call    cs:__imp_CloseHandle
0x18000b333  jmp     short loc_18000B33D
0x18000b335  call    cs:__imp_GetLastError
0x18000b33b  mov     ebx, eax
0x18000b33d  mov     eax, ebx
0x18000b33f  mov     rbx, [rsp+58h+arg_0]
0x18000b344  add     rsp, 50h
0x18000b348  pop     rdi
0x18000b349  retn
```
