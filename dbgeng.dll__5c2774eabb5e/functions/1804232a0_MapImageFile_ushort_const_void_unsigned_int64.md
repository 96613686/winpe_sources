# MapImageFile(ushort const *,void * *,unsigned __int64 *)

- ea: `0x1804232a0`
- end: `0x18042347a`
- name: `?MapImageFile@@YAJPEBGPEAPEAXPEA_K@Z`
- size: `474`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18041fac0`
- `0x180420d80`

## callees

- `0x1800f2560`
- `0x1804196ec`
- `0x1804232a0`
- `0x1804da4c0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1804232fe`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1804232fe`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1804232ea`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18042345e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1804232ea`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18042345e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18042343b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18042343b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18042341e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18042342d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18042341e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18042342d`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1804233a0`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1804233a0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180423367`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180423367`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1804233db`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1804233db`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180423405`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180423405`

## pseudocode

```c
__int64 __fastcall MapImageFile(const unsigned __int16 *a1, void **a2, unsigned __int64 *a3)
{
  char *FileW; // rax
  void *v7; // rsi
  unsigned int v8; // ebx
  HANDLE FileMappingW; // rax
  void *v10; // rbp
  void *v11; // rax
  signed int LastError; // eax
  unsigned __int64 FileSizeHigh; // [rsp+98h] [rbp+20h] BYREF

  wcschr(a1, 0x5Cu);
  FileW = (char *)CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v7 = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    HIDWORD(FileSizeHigh) = 0;
    v8 = -2147467259;
    FileSizeHigh = GetFileSize(FileW, (LPDWORD)&FileSizeHigh + 1);
    *a3 = FileSizeHigh;
    FileMappingW = CreateFileMappingW(v7, 0, 2u, 0, 0, 0);
    v10 = FileMappingW;
    if ( FileMappingW )
    {
      v11 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
      if ( v11 )
      {
        *a2 = v11;
        v8 = 0;
      }
      CloseHandle(v10);
    }
    CloseHandle(v7);
  }
  return v8;
}

```

## disassembly

```asm
0x1804232a0  push    rbx
0x1804232a2  push    rbp
0x1804232a3  push    rsi
0x1804232a4  push    rdi
0x1804232a5  push    r14
0x1804232a7  push    r15
0x1804232a9  sub     rsp, 48h
0x1804232ad  mov     r14, rdx
0x1804232b0  xor     edi, edi
0x1804232b2  mov     r15, r8
0x1804232b5  mov     rbx, rcx
0x1804232b8  lea     edx, [rdi+5Ch]; Ch
0x1804232bb  call    wcschr
0x1804232c0  test    rax, rax
0x1804232c3  jnz     short loc_18042333F
0x1804232c5  mov     rax, cs:qword_18082D958
0x1804232cc  test    rax, rax
0x1804232cf  jnz     short loc_1804232DD
0x1804232d1  mov     rax, cs:qword_18082D5A0
0x1804232d8  test    rax, rax
0x1804232db  jz      short loc_18042333F
0x1804232dd  mov     ebp, 104h
0x1804232e2  test    rdi, rdi
0x1804232e5  jz      short loc_1804232F6
0x1804232e7  mov     rcx, rdi; Block
0x1804232ea  call    cs:__imp_free
0x1804232f1  nop     dword ptr [rax+rax+00h]
0x1804232f6  mov     esi, ebp
0x1804232f8  add     rsi, rsi
0x1804232fb  mov     rcx, rsi; Size
0x1804232fe  call    cs:__imp_malloc
0x180423305  nop     dword ptr [rax+rax+00h]
0x18042330a  mov     rdi, rax
0x18042330d  test    rax, rax
0x180423310  jz      short loc_18042333F
0x180423312  mov     r8, rsi; Size
0x180423315  xor     edx, edx; Val
0x180423317  mov     rcx, rax; void *
0x18042331a  call    memset
0x18042331f  mov     r9d, ebp; unsigned int
0x180423322  mov     qword ptr [rsp+78h+dwCreationDisposition], rdi; unsigned __int16 *
0x180423327  mov     rdx, rbx; unsigned __int16 *
0x18042332a  call    ?DbgSearchPathW@@YAKPEBG00KPEAGPEAPEAG@Z; DbgSearchPathW(ushort const *,ushort const *,ushort const *,ulong,ushort *,ushort * *)
0x18042332f  cmp     eax, ebp
0x180423331  jbe     short loc_180423339
0x180423333  mov     ebp, eax
0x180423335  test    eax, eax
0x180423337  jnz     short loc_1804232E2
0x180423339  test    eax, eax
0x18042333b  cmovnz  rbx, rdi
0x18042333f  xor     r9d, r9d; lpSecurityAttributes
0x180423342  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18042334b  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180423353  mov     edx, 80000000h; dwDesiredAccess
0x180423358  mov     rcx, rbx; lpFileName
0x18042335b  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180423363  lea     r8d, [r9+1]; dwShareMode
0x180423367  call    cs:__imp_CreateFileW
0x18042336e  nop     dword ptr [rax+rax+00h]
0x180423373  mov     rsi, rax
0x180423376  lea     rcx, [rax-1]
0x18042337a  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18042337e  ja      loc_18042343B
0x180423384  lea     rdx, [rsp+78h+FileSizeHigh+4]; lpFileSizeHigh
0x18042338c  mov     qword ptr [rsp+98h], 0
0x180423398  mov     rcx, rax; hFile
0x18042339b  mov     ebx, 80004005h
0x1804233a0  call    cs:__imp_GetFileSize
0x1804233a7  nop     dword ptr [rax+rax+00h]
0x1804233ac  xor     r9d, r9d; dwMaximumSizeHigh
0x1804233af  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], 0; lpName
0x1804233b8  mov     dword ptr [rsp+78h+FileSizeHigh], eax
0x1804233bf  xor     edx, edx; lpFileMappingAttributes
0x1804233c1  mov     rcx, [rsp+78h+FileSizeHigh]
0x1804233c9  mov     [r15], rcx
0x1804233cc  mov     rcx, rsi; hFile
0x1804233cf  lea     r8d, [r9+2]; flProtect
0x1804233d3  mov     [rsp+78h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1804233db  call    cs:__imp_CreateFileMappingW
0x1804233e2  nop     dword ptr [rax+rax+00h]
0x1804233e7  mov     rbp, rax
0x1804233ea  test    rax, rax
0x1804233ed  jz      short loc_18042342A
0x1804233ef  xor     r9d, r9d; dwFileOffsetLow
0x1804233f2  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x1804233fb  xor     r8d, r8d; dwFileOffsetHigh
0x1804233fe  mov     rcx, rax; hFileMappingObject
0x180423401  lea     edx, [r9+4]; dwDesiredAccess
0x180423405  call    cs:__imp_MapViewOfFile
0x18042340c  nop     dword ptr [rax+rax+00h]
0x180423411  test    rax, rax
0x180423414  jz      short loc_18042341B
0x180423416  mov     [r14], rax
0x180423419  xor     ebx, ebx
0x18042341b  mov     rcx, rbp; hObject
0x18042341e  call    cs:__imp_CloseHandle
0x180423425  nop     dword ptr [rax+rax+00h]
0x18042342a  mov     rcx, rsi; hObject
0x18042342d  call    cs:__imp_CloseHandle
0x180423434  nop     dword ptr [rax+rax+00h]
0x180423439  jmp     short loc_180423456
0x18042343b  call    cs:__imp_GetLastError
0x180423442  nop     dword ptr [rax+rax+00h]
0x180423447  mov     ebx, eax
0x180423449  test    eax, eax
0x18042344b  jle     short loc_180423456
0x18042344d  movzx   ebx, ax
0x180423450  or      ebx, 80070000h
0x180423456  test    rdi, rdi
0x180423459  jz      short loc_18042346A
0x18042345b  mov     rcx, rdi; Block
0x18042345e  call    cs:__imp_free
0x180423465  nop     dword ptr [rax+rax+00h]
0x18042346a  mov     eax, ebx
0x18042346c  add     rsp, 48h
0x180423470  pop     r15
0x180423472  pop     r14
0x180423474  pop     rdi
0x180423475  pop     rsi
0x180423476  pop     rbp
0x180423477  pop     rbx
0x180423478  retn
```
