# CMapViewOfFile::CMapViewOfFile(ushort const *,bool)

- ea: `0x1801b40f0`
- end: `0x1801b41df`
- name: `??0CMapViewOfFile@@QEAA@PEBG_N@Z`
- size: `239`
- prototype: `CMapViewOfFile *(CMapViewOfFile *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1801b4324`

## callees

- `0x180022f7c`
- `0x1801b40f0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801b4184`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801b4184`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1801b41a4`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1801b41a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b41bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b41bc`

## pseudocode

```c
CMapViewOfFile *__fastcall CMapViewOfFile::CMapViewOfFile(CMapViewOfFile *this, const unsigned __int16 *a2)
{
  int v3; // eax
  const WCHAR *v4; // r11
  HANDLE FileW; // rax
  signed int LastError; // eax
  union _LARGE_INTEGER FileSize; // [rsp+50h] [rbp+8h] BYREF

  *((_DWORD *)this + 2) = 1;
  *((_DWORD *)this + 3) = -2147024809;
  *(_QWORD *)this = &CMapViewOfFile::`vftable';
  *((_QWORD *)this + 67) = -1;
  *((_QWORD *)this + 68) = 0;
  *((_QWORD *)this + 69) = 0;
  *((_QWORD *)this + 70) = 0;
  if ( a2 )
  {
    if ( *a2 )
    {
      v3 = StringCchCopyW((unsigned __int16 *)this + 8, 0x104u, a2);
      *((_DWORD *)this + 3) = v3;
      if ( v3 >= 0 )
      {
        FileW = CreateFileW(v4, 0x80000000, 5u, 0, 3u, 0, 0);
        *((_QWORD *)this + 67) = FileW;
        if ( FileW == (HANDLE)-1LL || (FileSize.QuadPart = 0, !GetFileSizeEx(FileW, &FileSize)) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          *((_DWORD *)this + 3) = LastError;
        }
        else
        {
          *((union _LARGE_INTEGER *)this + 68) = FileSize;
        }
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x1801b40f0  mov     [rsp+arg_8], rbx
0x1801b40f5  push    rdi
0x1801b40f6  sub     rsp, 40h
0x1801b40fa  xor     edi, edi
0x1801b40fc  mov     dword ptr [rcx+8], 1
0x1801b4103  mov     dword ptr [rcx+0Ch], 80070057h
0x1801b410a  lea     rax, ??_7CMapViewOfFile@@6B@; const CMapViewOfFile::`vftable'
0x1801b4111  mov     [rcx], rax
0x1801b4114  mov     r11, rdx
0x1801b4117  mov     qword ptr [rcx+218h], 0FFFFFFFFFFFFFFFFh
0x1801b4122  mov     rbx, rcx
0x1801b4125  mov     [rcx+220h], rdi
0x1801b412c  mov     [rcx+228h], rdi
0x1801b4133  mov     [rcx+230h], rdi
0x1801b413a  test    rdx, rdx
0x1801b413d  jz      loc_1801B41D1
0x1801b4143  cmp     [rdx], di
0x1801b4146  jz      loc_1801B41D1
0x1801b414c  mov     r8, rdx; unsigned __int16 *
0x1801b414f  add     rcx, 10h; unsigned __int16 *
0x1801b4153  mov     edx, 104h; unsigned __int64
0x1801b4158  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801b415d  mov     [rbx+0Ch], eax
0x1801b4160  test    eax, eax
0x1801b4162  js      short loc_1801B41D1
0x1801b4164  mov     [rsp+48h+hTemplateFile], rdi; hTemplateFile
0x1801b4169  lea     r8d, [rdi+5]; dwShareMode
0x1801b416d  mov     [rsp+48h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x1801b4171  xor     r9d, r9d; lpSecurityAttributes
0x1801b4174  mov     edx, 80000000h; dwDesiredAccess
0x1801b4179  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1801b4181  mov     rcx, r11; lpFileName
0x1801b4184  call    cs:__imp_CreateFileW
0x1801b418a  mov     [rbx+218h], rax
0x1801b4191  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801b4195  jz      short loc_1801B41BC
0x1801b4197  lea     rdx, [rsp+48h+FileSize]; lpFileSize
0x1801b419c  mov     qword ptr [rsp+48h+FileSize], rdi
0x1801b41a1  mov     rcx, rax; hFile
0x1801b41a4  call    cs:__imp_GetFileSizeEx
0x1801b41aa  test    eax, eax
0x1801b41ac  jz      short loc_1801B41BC
0x1801b41ae  mov     rax, qword ptr [rsp+48h+FileSize]
0x1801b41b3  mov     [rbx+220h], rax
0x1801b41ba  jmp     short loc_1801B41D1
0x1801b41bc  call    cs:__imp_GetLastError
0x1801b41c2  test    eax, eax
0x1801b41c4  jle     short loc_1801B41CE
0x1801b41c6  movzx   eax, ax
0x1801b41c9  or      eax, 80070000h
0x1801b41ce  mov     [rbx+0Ch], eax
0x1801b41d1  mov     rax, rbx
0x1801b41d4  mov     rbx, [rsp+48h+arg_8]
0x1801b41d9  add     rsp, 40h
0x1801b41dd  pop     rdi
0x1801b41de  retn
```
