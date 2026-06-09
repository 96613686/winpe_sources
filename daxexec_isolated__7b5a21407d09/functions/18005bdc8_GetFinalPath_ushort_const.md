# GetFinalPath(ushort const *)

- ea: `0x18005bdc8`
- end: `0x18005bf3d`
- name: `?GetFinalPath@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z`
- size: `373`
- prototype: `DWORD *__fastcall(DWORD *Src, LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, reparse_path`

## callers

- `0x18002fa64`
- `0x18003e974`
- `0x180061cbc`

## callees

- `0x1800165bc`
- `0x1800210fc`
- `0x1800371c8`
- `0x18005bdc8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005bee4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005bee4`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18005be48`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18005be66`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18005beb5`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18005be48`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18005be66`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18005beb5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005be10`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005be10`

## pseudocode

```c
DWORD *__fastcall GetFinalPath(DWORD *Src, LPCWSTR lpFileName)
{
  char *FileW; // rbx
  const char *v4; // r9
  DWORD v5; // esi
  DWORD FinalPathNameByHandleW; // eax
  __int64 v7; // r8
  WCHAR *v9; // rdx
  const char *v10; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  FileW = (char *)CreateFileW(lpFileName, 8u, 7u, 0, 3u, 0x2000000u, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fileutils.cpp",
      v4);
  v5 = 0;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 0);
  if ( !FinalPathNameByHandleW )
  {
    v5 = 1;
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 1u);
    if ( !FinalPathNameByHandleW )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x41,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fileutils.cpp",
        (const char *)retaddr);
  }
  std::wstring::wstring(Src, FinalPathNameByHandleW, v7, retaddr);
  if ( *((_QWORD *)Src + 3) <= 7u )
    v9 = (WCHAR *)Src;
  else
    v9 = *(WCHAR **)Src;
  if ( (unsigned __int64)GetFinalPathNameByHandleW(FileW, v9, Src[4], v5) > *((_QWORD *)Src + 2) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\fileutils.cpp",
      v10);
  std::wstring::resize(Src);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return Src;
}

```

## disassembly

```asm
0x18005bdc8  mov     r11, rsp
0x18005bdcb  mov     [r11+10h], rbx
0x18005bdcf  mov     [r11+20h], rsi
0x18005bdd3  mov     [r11+8], rcx
0x18005bdd7  push    rdi
0x18005bdd8  sub     rsp, 50h
0x18005bddc  mov     rax, rdx
0x18005bddf  mov     rdi, rcx
0x18005bde2  mov     [rsp+58h+var_18], 0
0x18005bdea  mov     qword ptr [r11-28h], 0
0x18005bdf2  mov     [rsp+58h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18005bdfa  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x18005be02  xor     r9d, r9d; lpSecurityAttributes
0x18005be05  lea     edx, [r9+8]; dwDesiredAccess
0x18005be09  lea     r8d, [r9+7]; dwShareMode
0x18005be0d  mov     rcx, rax; lpFileName
0x18005be10  call    cs:__imp_CreateFileW
0x18005be17  nop     dword ptr [rax+rax+00h]
0x18005be1c  mov     rbx, rax
0x18005be1f  mov     [rsp+58h+arg_10], rax
0x18005be24  dec     rax
0x18005be27  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005be2b  setbe   al
0x18005be2e  mov     rcx, [rsp+58h]; this
0x18005be33  test    al, al
0x18005be35  jz      loc_18005BF16
0x18005be3b  xor     esi, esi
0x18005be3d  xor     r9d, r9d; dwFlags
0x18005be40  xor     r8d, r8d; cchFilePath
0x18005be43  xor     edx, edx; lpszFilePath
0x18005be45  mov     rcx, rbx; hFile
0x18005be48  call    cs:__imp_GetFinalPathNameByHandleW
0x18005be4f  nop     dword ptr [rax+rax+00h]
0x18005be54  test    eax, eax
0x18005be56  jnz     short loc_18005BE7B
0x18005be58  lea     esi, [rax+1]
0x18005be5b  mov     r9d, esi; dwFlags
0x18005be5e  xor     r8d, r8d; cchFilePath
0x18005be61  xor     edx, edx; lpszFilePath
0x18005be63  mov     rcx, rbx; hFile
0x18005be66  call    cs:__imp_GetFinalPathNameByHandleW
0x18005be6d  nop     dword ptr [rax+rax+00h]
0x18005be72  test    eax, eax
0x18005be74  jnz     short loc_18005BE7B
0x18005be76  mov     cl, sil
0x18005be79  jmp     short loc_18005BE7D
0x18005be7b  xor     cl, cl
0x18005be7d  mov     r9, [rsp+58h]; char *
0x18005be82  test    cl, cl
0x18005be84  jnz     loc_18005BF28
0x18005be8a  mov     edx, eax
0x18005be8c  mov     rcx, rdi
0x18005be8f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18005be94  mov     [rsp+58h+var_18], 1
0x18005be9c  cmp     qword ptr [rdi+18h], 7
0x18005bea1  jbe     short loc_18005BEA8
0x18005bea3  mov     rdx, [rdi]
0x18005bea6  jmp     short loc_18005BEAB
0x18005bea8  mov     rdx, rdi; lpszFilePath
0x18005beab  mov     r9d, esi; dwFlags
0x18005beae  mov     r8d, [rdi+10h]; cchFilePath
0x18005beb2  mov     rcx, rbx; hFile
0x18005beb5  call    cs:__imp_GetFinalPathNameByHandleW
0x18005bebc  nop     dword ptr [rax+rax+00h]
0x18005bec1  mov     edx, eax
0x18005bec3  mov     rcx, [rsp+58h]; this
0x18005bec8  cmp     rdx, [rdi+10h]
0x18005becc  ja      short loc_18005BF04
0x18005bece  mov     rcx, rdi; Src
0x18005bed1  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18005bed6  nop
0x18005bed7  lea     rax, [rbx-1]
0x18005bedb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005bedf  ja      short loc_18005BEF0
0x18005bee1  mov     rcx, rbx; hObject
0x18005bee4  call    cs:__imp_CloseHandle
0x18005beeb  nop     dword ptr [rax+rax+00h]
0x18005bef0  mov     rax, rdi
0x18005bef3  mov     rbx, [rsp+58h+arg_8]
0x18005bef8  mov     rsi, [rsp+58h+arg_18]
0x18005befd  add     rsp, 50h
0x18005bf01  pop     rdi
0x18005bf02  retn
0x18005bf04  lea     r8, aOnecoreBaseApp_50; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005bf0b  mov     edx, 45h ; 'E'; void *
0x18005bf10  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005bf16  lea     r8, aOnecoreBaseApp_50; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005bf1d  mov     edx, 33h ; '3'; void *
0x18005bf22  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005bf28  lea     r8, aOnecoreBaseApp_50; "onecore\\base\\appmodel\\execmodel\\des"...
0x18005bf2f  mov     edx, 41h ; 'A'; void *
0x18005bf34  mov     rcx, r9; this
0x18005bf37  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
