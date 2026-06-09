# IsAChmOrColFileOnDisk(char const *)

- ea: `0x180068330`
- end: `0x1800683fc`
- name: `?IsAChmOrColFileOnDisk@@YAHPEBD@Z`
- size: `204`
- prototype: `__int64 __fastcall(LPCSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180068410`

## callees

- `0x180068330`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800683df`
- `KERNEL32!CloseHandle` at `0x1800683df`
- `KERNEL32!lstrcmpiA` at `0x180068367`
- `KERNEL32!lstrcmpiA` at `0x18006837c`
- `KERNEL32!lstrcmpiA` at `0x180068367`
- `KERNEL32!lstrcmpiA` at `0x18006837c`
- `KERNEL32!CreateFileA` at `0x1800683ad`
- `KERNEL32!CreateFileA` at `0x1800683ad`
- `KERNEL32!GetFileType` at `0x1800683d4`
- `KERNEL32!GetFileType` at `0x1800683d4`
- `KERNEL32!GetLastError` at `0x1800683bc`
- `KERNEL32!GetLastError` at `0x1800683bc`

## pseudocode

```c
_BOOL8 __fastcall IsAChmOrColFileOnDisk(LPCSTR lpFileName)
{
  unsigned __int64 v2; // rax
  const CHAR *v3; // rdi
  HANDLE FileA; // rax
  void *v5; // rdi
  DWORD FileType; // ebx

  v2 = -1;
  do
    ++v2;
  while ( lpFileName[v2] );
  if ( v2 > 4 )
  {
    v3 = &lpFileName[v2];
    if ( !lstrcmpiA(&lpFileName[v2 - 4], ".chm") || !lstrcmpiA(v3 - 4, ".col") )
    {
      FileA = CreateFileA(lpFileName, 0, 1u, 0, 3u, 0x80u, 0);
      v5 = FileA;
      if ( FileA != (HANDLE)-1LL )
      {
        FileType = GetFileType(FileA);
        CloseHandle(v5);
        return FileType == 1;
      }
      if ( GetLastError() - 32 <= 1 )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180068330  push    rbx
0x180068332  sub     rsp, 40h
0x180068336  mov     rbx, rcx
0x180068339  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180068340  inc     rax
0x180068343  cmp     byte ptr [rcx+rax], 0
0x180068347  jnz     short loc_180068340
0x180068349  mov     [rsp+48h+arg_0], rdi
0x18006834e  cmp     rax, 4
0x180068352  jbe     loc_1800683EF
0x180068358  lea     rdi, [rax+rcx]
0x18006835c  lea     rcx, [rdi-4]; lpString1
0x180068360  lea     rdx, ?txtDefExtension@@3QBDB; ".chm"
0x180068367  call    cs:__imp_lstrcmpiA
0x18006836d  test    eax, eax
0x18006836f  jz      short loc_180068386
0x180068371  lea     rdx, ?txtCollectionExtension@@3QBDB; ".col"
0x180068378  lea     rcx, [rdi-4]; lpString1
0x18006837c  call    cs:__imp_lstrcmpiA
0x180068382  test    eax, eax
0x180068384  jnz     short loc_1800683EF
0x180068386  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18006838f  xor     r9d, r9d; lpSecurityAttributes
0x180068392  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18006839a  xor     edx, edx; dwDesiredAccess
0x18006839c  mov     r8d, 1; dwShareMode
0x1800683a2  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x1800683aa  mov     rcx, rbx; lpFileName
0x1800683ad  call    cs:__imp_CreateFileA
0x1800683b3  mov     rdi, rax
0x1800683b6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800683ba  jnz     short loc_1800683D1
0x1800683bc  call    cs:__imp_GetLastError
0x1800683c2  add     eax, 0FFFFFFE0h
0x1800683c5  cmp     eax, 1
0x1800683c8  ja      short loc_1800683EF
0x1800683ca  mov     eax, 1
0x1800683cf  jmp     short loc_1800683F1
0x1800683d1  mov     rcx, rdi; hFile
0x1800683d4  call    cs:__imp_GetFileType
0x1800683da  mov     rcx, rdi; hObject
0x1800683dd  mov     ebx, eax
0x1800683df  call    cs:__imp_CloseHandle
0x1800683e5  xor     eax, eax
0x1800683e7  cmp     ebx, 1
0x1800683ea  setz    al
0x1800683ed  jmp     short loc_1800683F1
0x1800683ef  xor     eax, eax
0x1800683f1  mov     rdi, [rsp+48h+arg_0]
0x1800683f6  add     rsp, 40h
0x1800683fa  pop     rbx
0x1800683fb  retn
```
