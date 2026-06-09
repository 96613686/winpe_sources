# ClmProcessData::DetermineIfConsoleApplication(void)

- ea: `0x180061148`
- end: `0x180061310`
- name: `?DetermineIfConsoleApplication@ClmProcessData@@AEAAXXZ`
- size: `456`
- prototype: `void __fastcall(ClmProcessData *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180062a98`

## callees

- `0x1800210fc`
- `0x180061148`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006128c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800612a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006128c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800612a6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006119e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006119e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800611ea`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800611ea`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800612c0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18006122c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18006122c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ClmProcessData::DetermineIfConsoleApplication(ClmProcessData *this)
{
  char *v2; // rcx
  char *FileW; // rax
  const char *v4; // r9
  char *v5; // rdi
  char *FileMappingW; // rax
  const char *v7; // r9
  char *v8; // rbx
  unsigned int *v9; // rsi
  const char *v10; // r9
  __int64 v11; // rax
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = (char *)this + 96;
  if ( *((_QWORD *)v2 + 3) > 7u )
    v2 = *(char **)v2;
  FileW = (char *)CreateFileW((LPCWSTR)v2, 0x80000000, 1u, 0, 3u, 0, 0);
  v5 = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\clmdatastore.cpp",
      v4);
  FileMappingW = (char *)CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
  v8 = FileMappingW;
  if ( (unsigned __int64)(FileMappingW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x13A,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\clmdatastore.cpp",
      v7);
  v9 = (unsigned int *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
  if ( !v9 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x141,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\clmdatastore.cpp",
      v10);
  if ( *(_WORD *)v9 == 23117 )
  {
    v11 = v9[15];
    if ( *(unsigned int *)((char *)v9 + v11) == 17744
      && (*(_WORD *)((char *)v9 + v11 + 24) == 267 || *(_WORD *)((char *)v9 + v11 + 24) == 523)
      && *(_WORD *)((char *)v9 + v11 + 92) == 3 )
    {
      *((_DWORD *)this + 10) = 2;
    }
  }
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  UnmapViewOfFile(v9);
}

```

## disassembly

```asm
0x180061148  push    rbx
0x18006114a  push    rbp
0x18006114b  push    rsi
0x18006114c  push    rdi
0x18006114d  push    r15
0x18006114f  sub     rsp, 40h
0x180061153  mov     rbp, rcx
0x180061156  mov     [rsp+68h+arg_8], 0
0x18006115f  mov     [rsp+68h+arg_0], 0
0x180061168  add     rcx, 60h ; '`'
0x18006116c  cmp     qword ptr [rcx+18h], 7
0x180061171  jbe     short loc_180061176
0x180061173  mov     rcx, [rcx]; lpFileName
0x180061176  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18006117f  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180061187  mov     r15d, 3
0x18006118d  mov     [rsp+68h+dwCreationDisposition], r15d; dwCreationDisposition
0x180061192  xor     r9d, r9d; lpSecurityAttributes
0x180061195  mov     edx, 80000000h; dwDesiredAccess
0x18006119a  lea     r8d, [r15-2]; dwShareMode
0x18006119e  call    cs:__imp_CreateFileW
0x1800611a5  nop     dword ptr [rax+rax+00h]
0x1800611aa  mov     rdi, rax
0x1800611ad  mov     [rsp+68h+arg_10], rax
0x1800611b5  lea     rcx, [rax-1]
0x1800611b9  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800611bd  setbe   dl
0x1800611c0  mov     rcx, [rsp+68h]; this
0x1800611c5  test    dl, dl
0x1800611c7  jz      loc_1800612EC
0x1800611cd  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], 0; lpName
0x1800611d6  mov     [rsp+68h+dwCreationDisposition], 0; dwMaximumSizeLow
0x1800611de  xor     r9d, r9d; dwMaximumSizeHigh
0x1800611e1  xor     edx, edx; lpFileMappingAttributes
0x1800611e3  lea     r8d, [r15-1]; flProtect
0x1800611e7  mov     rcx, rax; hFile
0x1800611ea  call    cs:__imp_CreateFileMappingW
0x1800611f1  nop     dword ptr [rax+rax+00h]
0x1800611f6  mov     rbx, rax
0x1800611f9  mov     [rsp+68h+arg_0], rax
0x1800611fe  lea     rcx, [rax-1]
0x180061202  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180061206  setbe   dl
0x180061209  mov     rcx, [rsp+68h]; this
0x18006120e  test    dl, dl
0x180061210  jz      loc_1800612FE
0x180061216  mov     qword ptr [rsp+68h+dwCreationDisposition], 0; dwNumberOfBytesToMap
0x18006121f  xor     r9d, r9d; dwFileOffsetLow
0x180061222  xor     r8d, r8d; dwFileOffsetHigh
0x180061225  lea     edx, [r15+1]; dwDesiredAccess
0x180061229  mov     rcx, rax; hFileMappingObject
0x18006122c  call    cs:__imp_MapViewOfFile
0x180061233  nop     dword ptr [rax+rax+00h]
0x180061238  mov     rsi, rax
0x18006123b  mov     [rsp+68h+arg_8], rax
0x180061240  mov     rcx, [rsp+68h]; this
0x180061245  test    rax, rax
0x180061248  jz      loc_1800612DA
0x18006124e  mov     eax, 5A4Dh
0x180061253  cmp     [rsi], ax
0x180061256  jnz     short loc_18006127F
0x180061258  mov     eax, [rsi+3Ch]
0x18006125b  cmp     dword ptr [rax+rsi], 4550h
0x180061262  jnz     short loc_18006127F
0x180061264  mov     ecx, 10Bh
0x180061269  cmp     [rax+rsi+18h], cx
0x18006126e  jnz     short loc_1800612CC
0x180061270  cmp     [rax+rsi+5Ch], r15w
0x180061276  jnz     short loc_18006127F
0x180061278  mov     dword ptr [rbp+28h], 2
0x18006127f  lea     rax, [rdi-1]
0x180061283  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180061287  ja      short loc_180061299
0x180061289  mov     rcx, rdi; hObject
0x18006128c  call    cs:__imp_CloseHandle
0x180061293  nop     dword ptr [rax+rax+00h]
0x180061298  nop
0x180061299  lea     rax, [rbx-1]
0x18006129d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800612a1  ja      short loc_1800612B3
0x1800612a3  mov     rcx, rbx; hObject
0x1800612a6  call    cs:__imp_CloseHandle
0x1800612ad  nop     dword ptr [rax+rax+00h]
0x1800612b2  nop
0x1800612b3  mov     rcx, rsi
0x1800612b6  add     rsp, 40h
0x1800612ba  pop     r15
0x1800612bc  pop     rdi
0x1800612bd  pop     rsi
0x1800612be  pop     rbp
0x1800612bf  pop     rbx
0x1800612c0  jmp     cs:__imp_UnmapViewOfFile
0x1800612cc  mov     ecx, 20Bh
0x1800612d1  cmp     [rax+rsi+18h], cx
0x1800612d6  jnz     short loc_18006127F
0x1800612d8  jmp     short loc_180061270
0x1800612da  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800612e1  mov     edx, 141h; void *
0x1800612e6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800612ec  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800612f3  mov     edx, 132h; void *
0x1800612f8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800612fe  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\execmodel\\des"...
0x180061305  mov     edx, 13Ah; void *
0x18006130a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
