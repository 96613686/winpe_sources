# ClmProcessData::DetermineIfConsoleApplication(void)

- ea: `0x18005f64c`
- end: `0x18005f7ff`
- name: `?DetermineIfConsoleApplication@ClmProcessData@@AEAAXXZ`
- size: `435`
- prototype: `void __fastcall(ClmProcessData *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180060fdc`

## callees

- `0x18002031c`
- `0x18005f64c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f789`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f7a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f789`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f7a3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005f697`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005f697`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18005f6de`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18005f6de`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18005f71e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18005f71e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18005f7bd`

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
  char *v9; // rsi
  const char *v10; // r9
  char *v11; // rax
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
  v9 = (char *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
  if ( !v9 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x141,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\clmdatastore.cpp",
      v10);
  if ( *(_WORD *)v9 == 23117 )
  {
    v11 = &v9[*((unsigned int *)v9 + 15)];
    if ( *(_DWORD *)v11 == 17744
      && (*((_WORD *)v11 + 12) == 267 || *((_WORD *)v11 + 12) == 523)
      && *((_WORD *)v11 + 46) == 3 )
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
0x18005f64c  push    rbx
0x18005f64e  push    rbp
0x18005f64f  push    rsi
0x18005f650  push    rdi
0x18005f651  push    r12
0x18005f653  sub     rsp, 40h
0x18005f657  mov     rbp, rcx
0x18005f65a  and     [rsp+68h+arg_8], 0
0x18005f660  and     [rsp+68h+arg_0], 0
0x18005f666  add     rcx, 60h ; '`'
0x18005f66a  cmp     qword ptr [rcx+18h], 7
0x18005f66f  jbe     short loc_18005F674
0x18005f671  mov     rcx, [rcx]; lpFileName
0x18005f674  and     [rsp+68h+var_38], 0
0x18005f67a  and     dword ptr [rsp+68h+var_40], 0
0x18005f67f  mov     r12d, 3
0x18005f685  mov     [rsp+68h+dwCreationDisposition], r12d; dwNumberOfBytesToMap
0x18005f68a  xor     r9d, r9d; lpSecurityAttributes
0x18005f68d  mov     edx, 80000000h; dwDesiredAccess
0x18005f692  lea     r8d, [r12-2]; dwShareMode
0x18005f697  call    cs:__imp_CreateFileW
0x18005f69e  nop     dword ptr [rax+rax+00h]
0x18005f6a3  mov     rdi, rax
0x18005f6a6  mov     [rsp+68h+arg_10], rax
0x18005f6ae  lea     rcx, [rax-1]
0x18005f6b2  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18005f6b6  setbe   dl
0x18005f6b9  mov     rcx, [rsp+68h]; this
0x18005f6be  test    dl, dl
0x18005f6c0  jz      loc_18005F7DB
0x18005f6c6  and     [rsp+68h+var_40], 0
0x18005f6cc  and     [rsp+68h+dwCreationDisposition], 0
0x18005f6d1  xor     r9d, r9d; dwMaximumSizeHigh
0x18005f6d4  xor     edx, edx; lpFileMappingAttributes
0x18005f6d6  lea     r8d, [r12-1]; flProtect
0x18005f6db  mov     rcx, rax; hFile
0x18005f6de  call    cs:__imp_CreateFileMappingW
0x18005f6e5  nop     dword ptr [rax+rax+00h]
0x18005f6ea  mov     rbx, rax
0x18005f6ed  mov     [rsp+68h+arg_0], rax
0x18005f6f2  lea     rcx, [rax-1]
0x18005f6f6  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18005f6fa  setbe   dl
0x18005f6fd  mov     rcx, [rsp+68h]; this
0x18005f702  test    dl, dl
0x18005f704  jz      loc_18005F7ED
0x18005f70a  and     qword ptr [rsp+68h+dwCreationDisposition], 0
0x18005f710  xor     r9d, r9d; dwFileOffsetLow
0x18005f713  xor     r8d, r8d; dwFileOffsetHigh
0x18005f716  lea     edx, [r12+1]; dwDesiredAccess
0x18005f71b  mov     rcx, rax; hFileMappingObject
0x18005f71e  call    cs:__imp_MapViewOfFile
0x18005f725  nop     dword ptr [rax+rax+00h]
0x18005f72a  mov     rsi, rax
0x18005f72d  mov     [rsp+68h+arg_8], rax
0x18005f732  mov     rcx, [rsp+68h]; this
0x18005f737  test    rax, rax
0x18005f73a  jz      loc_18005F7C9
0x18005f740  mov     eax, 5A4Dh
0x18005f745  cmp     [rsi], ax
0x18005f748  jnz     short loc_18005F77C
0x18005f74a  mov     eax, [rsi+3Ch]
0x18005f74d  add     rax, rsi
0x18005f750  cmp     dword ptr [rax], 4550h
0x18005f756  jnz     short loc_18005F77C
0x18005f758  mov     ecx, 10Bh
0x18005f75d  cmp     [rax+18h], cx
0x18005f761  jz      short loc_18005F76E
0x18005f763  mov     ecx, 20Bh
0x18005f768  cmp     [rax+18h], cx
0x18005f76c  jnz     short loc_18005F77C
0x18005f76e  cmp     [rax+5Ch], r12w
0x18005f773  jnz     short loc_18005F77C
0x18005f775  mov     dword ptr [rbp+28h], 2
0x18005f77c  lea     rax, [rdi-1]
0x18005f780  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005f784  ja      short loc_18005F796
0x18005f786  mov     rcx, rdi; hObject
0x18005f789  call    cs:__imp_CloseHandle
0x18005f790  nop     dword ptr [rax+rax+00h]
0x18005f795  nop
0x18005f796  lea     rax, [rbx-1]
0x18005f79a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005f79e  ja      short loc_18005F7B0
0x18005f7a0  mov     rcx, rbx; hObject
0x18005f7a3  call    cs:__imp_CloseHandle
0x18005f7aa  nop     dword ptr [rax+rax+00h]
0x18005f7af  nop
0x18005f7b0  mov     rcx, rsi
0x18005f7b3  add     rsp, 40h
0x18005f7b7  pop     r12
0x18005f7b9  pop     rdi
0x18005f7ba  pop     rsi
0x18005f7bb  pop     rbp
0x18005f7bc  pop     rbx
0x18005f7bd  jmp     cs:__imp_UnmapViewOfFile
0x18005f7c9  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005f7d0  mov     edx, 141h; void *
0x18005f7d5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005f7db  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005f7e2  mov     edx, 132h; void *
0x18005f7e7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005f7ed  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005f7f4  mov     edx, 13Ah; void *
0x18005f7f9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
