# AdjustFileTime

- ea: `0x180015880`
- end: `0x1800158f8`
- name: `AdjustFileTime`
- size: `120`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180012a40`

## callees

- `0x180015880`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x1800158df`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x1800158df`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x1800158c3`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x1800158c3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x1800158af`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x1800158af`

## pseudocode

```c
_BOOL8 __fastcall AdjustFileTime(HANDLE hFile, WORD a2, WORD a3)
{
  struct _FILETIME FileTime; // [rsp+20h] [rbp-18h] BYREF
  FILETIME CreationTime; // [rsp+58h] [rbp+20h] BYREF

  FileTime = 0;
  CreationTime = 0;
  return DosDateTimeToFileTime(a2, a3, &FileTime)
      && LocalFileTimeToFileTime(&FileTime, &CreationTime)
      && SetFileTime(hFile, &CreationTime, &CreationTime, &CreationTime);
}

```

## disassembly

```asm
0x180015880  push    rbx
0x180015882  sub     rsp, 30h
0x180015886  movzx   eax, r8w
0x18001588a  mov     qword ptr [rsp+38h+FileTime.dwLowDateTime], 0
0x180015893  movzx   r9d, dx
0x180015897  mov     qword ptr [rsp+38h+CreationTime.dwLowDateTime], 0
0x1800158a0  mov     rbx, rcx
0x1800158a3  lea     r8, [rsp+38h+FileTime]; lpFileTime
0x1800158a8  movzx   edx, ax; wFatTime
0x1800158ab  movzx   ecx, r9w; wFatDate
0x1800158af  call    cs:__imp_DosDateTimeToFileTime
0x1800158b5  test    eax, eax
0x1800158b7  jz      short loc_1800158F0
0x1800158b9  lea     rdx, [rsp+38h+CreationTime]; lpFileTime
0x1800158be  lea     rcx, [rsp+38h+FileTime]; lpLocalFileTime
0x1800158c3  call    cs:__imp_LocalFileTimeToFileTime
0x1800158c9  test    eax, eax
0x1800158cb  jz      short loc_1800158F0
0x1800158cd  lea     r9, [rsp+38h+CreationTime]; lpLastWriteTime
0x1800158d2  mov     rcx, rbx; hFile
0x1800158d5  lea     r8, [rsp+38h+CreationTime]; lpLastAccessTime
0x1800158da  lea     rdx, [rsp+38h+CreationTime]; lpCreationTime
0x1800158df  call    cs:__imp_SetFileTime
0x1800158e5  xor     ecx, ecx
0x1800158e7  test    eax, eax
0x1800158e9  setnz   cl
0x1800158ec  mov     eax, ecx
0x1800158ee  jmp     short loc_1800158F2
0x1800158f0  xor     eax, eax
0x1800158f2  add     rsp, 30h
0x1800158f6  pop     rbx
0x1800158f7  retn
```
