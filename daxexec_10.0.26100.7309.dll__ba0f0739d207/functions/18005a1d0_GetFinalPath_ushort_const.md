# GetFinalPath(ushort const *)

- ea: `0x18005a1d0`
- end: `0x18005a345`
- name: `?GetFinalPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z`
- size: `373`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x18002ece8`
- `0x18003cc84`
- `0x180060208`

## callees

- `0x1800149a4`
- `0x18002031c`
- `0x18005a1d0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a2ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a2ef`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18005a24a`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18005a268`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18005a2b4`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18005a24a`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18005a268`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18005a2b4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005a20f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005a20f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall GetFinalPath(__int64 *a1, const WCHAR *a2)
{
  char *FileW; // rbx
  const char *v4; // r9
  DWORD v5; // esi
  DWORD FinalPathNameByHandleW; // eax
  __int64 v7; // r8
  char v8; // cl
  WCHAR *v9; // rdx
  unsigned __int64 v10; // rdx
  const char *v11; // r9
  __int64 *v12; // rax
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  FileW = (char *)CreateFileW(a2, 8u, 7u, 0, 3u, 0x2000000u, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fileutils.cpp",
      v4);
  v5 = 0;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 0);
  if ( FinalPathNameByHandleW
    || (v5 = 1, FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 1u), v8 = 1, FinalPathNameByHandleW) )
  {
    v8 = 0;
  }
  if ( v8 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fileutils.cpp",
      (const char *)retaddr);
  std::wstring::wstring(a1, FinalPathNameByHandleW, v7, retaddr);
  v9 = (WCHAR *)a1;
  if ( (unsigned __int64)a1[3] > 7 )
    v9 = (WCHAR *)*a1;
  v10 = GetFinalPathNameByHandleW(FileW, v9, *((_DWORD *)a1 + 4), v5);
  if ( v10 > a1[2] )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fileutils.cpp",
      v11);
  v12 = a1;
  if ( (unsigned __int64)a1[3] > 7 )
    v12 = (__int64 *)*a1;
  a1[2] = v10;
  *((_WORD *)v12 + v10) = 0;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return a1;
}

```

## disassembly

```asm
0x18005a1d0  mov     [rsp+arg_8], rbx
0x18005a1d5  mov     [rsp+arg_0], rcx
0x18005a1da  push    rbp
0x18005a1db  push    rsi
0x18005a1dc  push    rdi
0x18005a1dd  sub     rsp, 50h
0x18005a1e1  mov     rax, rdx
0x18005a1e4  mov     rdi, rcx
0x18005a1e7  xor     ebp, ebp
0x18005a1e9  mov     [rsp+68h+var_28], ebp
0x18005a1ed  mov     [rsp+68h+hTemplateFile], rbp; hTemplateFile
0x18005a1f2  mov     [rsp+68h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18005a1fa  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18005a202  xor     r9d, r9d; lpSecurityAttributes
0x18005a205  lea     edx, [rbp+8]; dwDesiredAccess
0x18005a208  lea     r8d, [rbp+7]; dwShareMode
0x18005a20c  mov     rcx, rax; lpFileName
0x18005a20f  call    cs:__imp_CreateFileW
0x18005a216  nop     dword ptr [rax+rax+00h]
0x18005a21b  mov     rbx, rax
0x18005a21e  mov     [rsp+68h+arg_10], rax
0x18005a226  dec     rax
0x18005a229  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005a22d  setbe   al
0x18005a230  mov     rcx, [rsp+68h]; this
0x18005a235  test    al, al
0x18005a237  jz      loc_18005A31E
0x18005a23d  mov     esi, ebp
0x18005a23f  xor     r9d, r9d; dwFlags
0x18005a242  xor     r8d, r8d; cchFilePath
0x18005a245  xor     edx, edx; lpszFilePath
0x18005a247  mov     rcx, rbx; hFile
0x18005a24a  call    cs:__imp_GetFinalPathNameByHandleW
0x18005a251  nop     dword ptr [rax+rax+00h]
0x18005a256  test    eax, eax
0x18005a258  jnz     short loc_18005A27B
0x18005a25a  lea     esi, [rbp+1]
0x18005a25d  mov     r9d, esi; dwFlags
0x18005a260  xor     r8d, r8d; cchFilePath
0x18005a263  xor     edx, edx; lpszFilePath
0x18005a265  mov     rcx, rbx; hFile
0x18005a268  call    cs:__imp_GetFinalPathNameByHandleW
0x18005a26f  nop     dword ptr [rax+rax+00h]
0x18005a274  test    eax, eax
0x18005a276  mov     cl, sil
0x18005a279  jz      short loc_18005A27E
0x18005a27b  mov     cl, bpl
0x18005a27e  mov     r9, [rsp+68h]; char *
0x18005a283  test    cl, cl
0x18005a285  jnz     loc_18005A330
0x18005a28b  mov     edx, eax
0x18005a28d  mov     rcx, rdi
0x18005a290  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18005a295  mov     [rsp+68h+var_28], 1
0x18005a29d  mov     rdx, rdi
0x18005a2a0  cmp     qword ptr [rdi+18h], 7
0x18005a2a5  jbe     short loc_18005A2AA
0x18005a2a7  mov     rdx, [rdi]; lpszFilePath
0x18005a2aa  mov     r9d, esi; dwFlags
0x18005a2ad  mov     r8d, [rdi+10h]; cchFilePath
0x18005a2b1  mov     rcx, rbx; hFile
0x18005a2b4  call    cs:__imp_GetFinalPathNameByHandleW
0x18005a2bb  nop     dword ptr [rax+rax+00h]
0x18005a2c0  mov     edx, eax
0x18005a2c2  mov     rcx, [rsp+68h]; this
0x18005a2c7  cmp     rdx, [rdi+10h]
0x18005a2cb  ja      short loc_18005A30C
0x18005a2cd  mov     rax, rdi
0x18005a2d0  cmp     qword ptr [rdi+18h], 7
0x18005a2d5  jbe     short loc_18005A2DA
0x18005a2d7  mov     rax, [rdi]
0x18005a2da  mov     [rdi+10h], rdx
0x18005a2de  mov     [rax+rdx*2], bp
0x18005a2e2  lea     rax, [rbx-1]
0x18005a2e6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005a2ea  ja      short loc_18005A2FB
0x18005a2ec  mov     rcx, rbx; hObject
0x18005a2ef  call    cs:__imp_CloseHandle
0x18005a2f6  nop     dword ptr [rax+rax+00h]
0x18005a2fb  mov     rax, rdi
0x18005a2fe  mov     rbx, [rsp+68h+arg_8]
0x18005a303  add     rsp, 50h
0x18005a307  pop     rdi
0x18005a308  pop     rsi
0x18005a309  pop     rbp
0x18005a30a  retn
0x18005a30c  lea     r8, aOnecoreBaseApp_49; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005a313  mov     edx, 45h ; 'E'; void *
0x18005a318  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005a31e  lea     r8, aOnecoreBaseApp_49; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005a325  mov     edx, 33h ; '3'; void *
0x18005a32a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005a330  lea     r8, aOnecoreBaseApp_49; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005a337  mov     edx, 41h ; 'A'; void *
0x18005a33c  mov     rcx, r9; this
0x18005a33f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
