# FF_RemoveLegacyDump(ushort const *,ushort const *,ulong)

- ea: `0x180041c7c`
- end: `0x180041e66`
- name: `?FF_RemoveLegacyDump@@YAXPEBG0K@Z`
- size: `490`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18002c7ac`

## callees

- `0x180006194`
- `0x180018930`
- `0x18002ba34`
- `0x180041c7c`
- `0x1800434c6`
- `0x180043510`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180041d63`
- `msvcrt!_wcsicmp` at `0x180041d63`
- `msvcrt!wcsrchr` at `0x180041deb`
- `msvcrt!wcsrchr` at `0x180041deb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180041d36`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180041d36`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180041dce`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180041e19`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180041dce`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180041e19`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180041d89`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180041d89`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180041e35`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180041e35`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180041ddb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180041e26`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180041ddb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180041e26`

## pseudocode

```c
void __fastcall FF_RemoveLegacyDump(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned int a3)
{
  unsigned int v6; // edi
  HANDLE FirstFileW; // rbx
  wchar_t *v8; // rax
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Str[264]; // [rsp+280h] [rbp+180h] BYREF
  wchar_t String1[264]; // [rsp+490h] [rbp+390h] BYREF
  WCHAR FileName[264]; // [rsp+6A0h] [rbp+5A0h] BYREF

  memset_0(FileName, 0, 0x208u);
  memset_0(String1, 0, 0x20Au);
  memset_0(Str, 0, 0x20Au);
  v6 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  StringCchPrintfW(FileName, 0x104u, L"%s\\%s*.dmp", a2, a1);
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    do
    {
      ++v6;
      if ( !String1[0] || _wcsicmp(String1, FindFileData.cFileName) > 0 )
        StringCchCopyW(String1, 0x105u, FindFileData.cFileName);
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
  }
  if ( v6 >= a3 )
  {
    StringCchPrintfW(Str, 0x105u, L"%s\\%s", a2, String1);
    SetFileAttributesW(Str, 0x80u);
    DeleteFileW(Str);
    v8 = wcsrchr(Str, 0x2Eu);
    if ( v8 )
    {
      *v8 = 0;
      StringCchCatW(Str, 0x105u, L".txt");
      SetFileAttributesW(Str, 0x80u);
      DeleteFileW(Str);
    }
  }
  if ( FirstFileW != (HANDLE)-1LL )
    FindClose(FirstFileW);
}

```

## disassembly

```asm
0x180041c7c  mov     [rsp-8+arg_10], rbx
0x180041c81  mov     [rsp-8+arg_18], rsi
0x180041c86  push    rbp
0x180041c87  push    rdi
0x180041c88  push    r12
0x180041c8a  push    r14
0x180041c8c  push    r15
0x180041c8e  lea     rbp, [rsp-7C0h]
0x180041c96  sub     rsp, 8C0h
0x180041c9d  mov     rax, cs:__security_cookie
0x180041ca4  xor     rax, rsp
0x180041ca7  mov     [rbp+7E0h+var_30], rax
0x180041cae  mov     esi, r8d
0x180041cb1  mov     r14, rdx
0x180041cb4  mov     rbx, rcx
0x180041cb7  xor     edx, edx; Val
0x180041cb9  mov     r8d, 208h; Size
0x180041cbf  lea     rcx, [rbp+7E0h+FileName]; void *
0x180041cc6  call    memset_0
0x180041ccb  mov     edi, 20Ah
0x180041cd0  lea     rcx, [rbp+7E0h+String1]; void *
0x180041cd7  mov     r8d, edi; Size
0x180041cda  xor     edx, edx; Val
0x180041cdc  call    memset_0
0x180041ce1  mov     r8d, edi; Size
0x180041ce4  lea     rcx, [rbp+7E0h+Str]; void *
0x180041ceb  xor     edx, edx; Val
0x180041ced  call    memset_0
0x180041cf2  xor     r15d, r15d
0x180041cf5  lea     rcx, [rsp+8E0h+FindFileData]; void *
0x180041cfa  xor     edx, edx; Val
0x180041cfc  mov     r8d, 250h; Size
0x180041d02  mov     edi, r15d
0x180041d05  call    memset_0
0x180041d0a  mov     r9, r14
0x180041d0d  mov     [rsp+8E0h+var_8C0], rbx
0x180041d12  lea     r8, aSSDmp; "%s\\%s*.dmp"
0x180041d19  mov     edx, 104h; unsigned __int64
0x180041d1e  lea     rcx, [rbp+7E0h+FileName]; unsigned __int16 *
0x180041d25  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041d2a  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x180041d2f  lea     rcx, [rbp+7E0h+FileName]; lpFileName
0x180041d36  call    cs:__imp_FindFirstFileW
0x180041d3c  mov     rbx, rax
0x180041d3f  mov     r12d, 105h
0x180041d45  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180041d49  jz      short loc_180041D93
0x180041d4b  inc     edi
0x180041d4d  cmp     [rbp+7E0h+String1], r15w
0x180041d55  jz      short loc_180041D6D
0x180041d57  lea     rdx, [rsp+8E0h+FindFileData.cFileName]; String2
0x180041d5c  lea     rcx, [rbp+7E0h+String1]; String1
0x180041d63  call    cs:__imp__wcsicmp
0x180041d69  test    eax, eax
0x180041d6b  jle     short loc_180041D81
0x180041d6d  lea     r8, [rsp+8E0h+FindFileData.cFileName]; unsigned __int16 *
0x180041d72  mov     rdx, r12; unsigned __int64
0x180041d75  lea     rcx, [rbp+7E0h+String1]; unsigned __int16 *
0x180041d7c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180041d81  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x180041d86  mov     rcx, rbx; hFindFile
0x180041d89  call    cs:__imp_FindNextFileW
0x180041d8f  test    eax, eax
0x180041d91  jnz     short loc_180041D4B
0x180041d93  cmp     edi, esi
0x180041d95  jb      loc_180041E2C
0x180041d9b  lea     rax, [rbp+7E0h+String1]
0x180041da2  mov     r9, r14
0x180041da5  lea     r8, aSS; "%s\\%s"
0x180041dac  mov     [rsp+8E0h+var_8C0], rax
0x180041db1  mov     rdx, r12; unsigned __int64
0x180041db4  lea     rcx, [rbp+7E0h+Str]; unsigned __int16 *
0x180041dbb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180041dc0  mov     edi, 80h
0x180041dc5  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x180041dcc  mov     edx, edi; dwFileAttributes
0x180041dce  call    cs:__imp_SetFileAttributesW
0x180041dd4  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x180041ddb  call    cs:__imp_DeleteFileW
0x180041de1  lea     edx, [rdi-52h]; Ch
0x180041de4  lea     rcx, [rbp+7E0h+Str]; Str
0x180041deb  call    cs:__imp_wcsrchr
0x180041df1  test    rax, rax
0x180041df4  jz      short loc_180041E2C
0x180041df6  lea     r8, aTxt; ".txt"
0x180041dfd  mov     [rax], r15w
0x180041e01  mov     rdx, r12; unsigned __int64
0x180041e04  lea     rcx, [rbp+7E0h+Str]; unsigned __int16 *
0x180041e0b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180041e10  mov     edx, edi; dwFileAttributes
0x180041e12  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x180041e19  call    cs:__imp_SetFileAttributesW
0x180041e1f  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x180041e26  call    cs:__imp_DeleteFileW
0x180041e2c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180041e30  jz      short loc_180041E3B
0x180041e32  mov     rcx, rbx; hFindFile
0x180041e35  call    cs:__imp_FindClose
0x180041e3b  mov     rcx, [rbp+7E0h+var_30]
0x180041e42  xor     rcx, rsp; StackCookie
0x180041e45  call    __security_check_cookie
0x180041e4a  lea     r11, [rsp+8E0h+var_20]
0x180041e52  mov     rbx, [r11+40h]
0x180041e56  mov     rsi, [r11+48h]
0x180041e5a  mov     rsp, r11
0x180041e5d  pop     r15
0x180041e5f  pop     r14
0x180041e61  pop     r12
0x180041e63  pop     rdi
0x180041e64  pop     rbp
0x180041e65  retn
```
