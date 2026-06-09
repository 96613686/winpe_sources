# FF_RemoveLegacyDump(ushort const *,ushort const *,ulong)

- ea: `0x140003c50`
- end: `0x140003e6d`
- name: `?FF_RemoveLegacyDump@@YAXPEBG0K@Z`
- size: `541`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1400037ac`

## callees

- `0x1400019cf`
- `0x140002830`
- `0x1400028f4`
- `0x140003c50`
- `0x140006f10`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140003d37`
- `msvcrt!_wcsicmp` at `0x140003d37`
- `msvcrt!wcsrchr` at `0x140003df2`
- `msvcrt!wcsrchr` at `0x140003df2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140003de2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140003e2d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140003de2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140003e2d`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x140003dd5`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x140003e20`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x140003dd5`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x140003e20`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x140003e3c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x140003e3c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x140003d90`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x140003d90`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140003d0a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x140003d0a`

## pseudocode

```c
void __fastcall FF_RemoveLegacyDump(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned int a3)
{
  unsigned int v6; // edi
  HANDLE FirstFileW; // rbx
  __int64 v8; // rcx
  WCHAR *cFileName; // r8
  __int64 v10; // rdx
  wchar_t *v11; // rax
  wchar_t *v12; // rcx
  wchar_t *v13; // rax
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
      {
        v8 = 2147483646;
        cFileName = FindFileData.cFileName;
        v10 = 261;
        v11 = String1;
        do
        {
          if ( !v8 )
            break;
          if ( !*cFileName )
            break;
          *v11++ = *cFileName++;
          --v8;
          --v10;
        }
        while ( v10 );
        v12 = v11 - 1;
        if ( v10 )
          v12 = v11;
        *v12 = 0;
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
  }
  if ( v6 >= a3 )
  {
    StringCchPrintfW(Str, 0x105u, L"%s\\%s", a2, String1);
    SetFileAttributesW(Str, 0x80u);
    DeleteFileW(Str);
    v13 = wcsrchr(Str, 0x2Eu);
    if ( v13 )
    {
      *v13 = 0;
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
0x140003c50  mov     [rsp-8+arg_10], rbx
0x140003c55  mov     [rsp-8+arg_18], rsi
0x140003c5a  push    rbp
0x140003c5b  push    rdi
0x140003c5c  push    r12
0x140003c5e  push    r14
0x140003c60  push    r15
0x140003c62  lea     rbp, [rsp-7C0h]
0x140003c6a  sub     rsp, 8C0h
0x140003c71  mov     rax, cs:__security_cookie
0x140003c78  xor     rax, rsp
0x140003c7b  mov     [rbp+7E0h+var_30], rax
0x140003c82  mov     esi, r8d
0x140003c85  mov     r14, rdx
0x140003c88  mov     rbx, rcx
0x140003c8b  xor     edx, edx; Val
0x140003c8d  mov     r8d, 208h; Size
0x140003c93  lea     rcx, [rbp+7E0h+FileName]; void *
0x140003c9a  call    memset_0
0x140003c9f  mov     edi, 20Ah
0x140003ca4  lea     rcx, [rbp+7E0h+String1]; void *
0x140003cab  mov     r8d, edi; Size
0x140003cae  xor     edx, edx; Val
0x140003cb0  call    memset_0
0x140003cb5  mov     r8d, edi; Size
0x140003cb8  lea     rcx, [rbp+7E0h+Str]; void *
0x140003cbf  xor     edx, edx; Val
0x140003cc1  call    memset_0
0x140003cc6  xor     r15d, r15d
0x140003cc9  lea     rcx, [rsp+8E0h+FindFileData]; void *
0x140003cce  xor     edx, edx; Val
0x140003cd0  mov     r8d, 250h; Size
0x140003cd6  mov     edi, r15d
0x140003cd9  call    memset_0
0x140003cde  mov     r9, r14
0x140003ce1  mov     [rsp+8E0h+var_8C0], rbx
0x140003ce6  lea     r8, aSSDmp_0; "%s\\%s*.dmp"
0x140003ced  mov     edx, 104h; unsigned __int64
0x140003cf2  lea     rcx, [rbp+7E0h+FileName]; unsigned __int16 *
0x140003cf9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003cfe  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x140003d03  lea     rcx, [rbp+7E0h+FileName]; lpFileName
0x140003d0a  call    cs:__imp_FindFirstFileW
0x140003d10  mov     rbx, rax
0x140003d13  mov     r12d, 105h
0x140003d19  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140003d1d  jz      short loc_140003D9A
0x140003d1f  inc     edi
0x140003d21  cmp     [rbp+7E0h+String1], r15w
0x140003d29  jz      short loc_140003D41
0x140003d2b  lea     rdx, [rsp+8E0h+FindFileData.cFileName]; String2
0x140003d30  lea     rcx, [rbp+7E0h+String1]; String1
0x140003d37  call    cs:__imp__wcsicmp
0x140003d3d  test    eax, eax
0x140003d3f  jle     short loc_140003D88
0x140003d41  mov     ecx, 7FFFFFFEh
0x140003d46  lea     r8, [rsp+8E0h+FindFileData.cFileName]
0x140003d4b  mov     rdx, r12
0x140003d4e  lea     rax, [rbp+7E0h+String1]
0x140003d55  test    rcx, rcx
0x140003d58  jz      short loc_140003D79
0x140003d5a  movzx   r9d, word ptr [r8]
0x140003d5e  test    r9w, r9w
0x140003d62  jz      short loc_140003D79
0x140003d64  mov     [rax], r9w
0x140003d68  add     r8, 2
0x140003d6c  add     rax, 2
0x140003d70  dec     rcx
0x140003d73  sub     rdx, 1
0x140003d77  jnz     short loc_140003D55
0x140003d79  test    rdx, rdx
0x140003d7c  lea     rcx, [rax-2]
0x140003d80  cmovnz  rcx, rax
0x140003d84  mov     [rcx], r15w
0x140003d88  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x140003d8d  mov     rcx, rbx; hFindFile
0x140003d90  call    cs:__imp_FindNextFileW
0x140003d96  test    eax, eax
0x140003d98  jnz     short loc_140003D1F
0x140003d9a  cmp     edi, esi
0x140003d9c  jb      loc_140003E33
0x140003da2  lea     rax, [rbp+7E0h+String1]
0x140003da9  mov     r9, r14
0x140003dac  lea     r8, aSS_0; "%s\\%s"
0x140003db3  mov     [rsp+8E0h+var_8C0], rax
0x140003db8  mov     rdx, r12; unsigned __int64
0x140003dbb  lea     rcx, [rbp+7E0h+Str]; unsigned __int16 *
0x140003dc2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140003dc7  mov     edi, 80h
0x140003dcc  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x140003dd3  mov     edx, edi; dwFileAttributes
0x140003dd5  call    cs:__imp_SetFileAttributesW
0x140003ddb  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x140003de2  call    cs:__imp_DeleteFileW
0x140003de8  lea     edx, [rdi-52h]; Ch
0x140003deb  lea     rcx, [rbp+7E0h+Str]; Str
0x140003df2  call    cs:__imp_wcsrchr
0x140003df8  test    rax, rax
0x140003dfb  jz      short loc_140003E33
0x140003dfd  lea     r8, aTxt; ".txt"
0x140003e04  mov     [rax], r15w
0x140003e08  mov     rdx, r12; unsigned __int64
0x140003e0b  lea     rcx, [rbp+7E0h+Str]; unsigned __int16 *
0x140003e12  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140003e17  mov     edx, edi; dwFileAttributes
0x140003e19  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x140003e20  call    cs:__imp_SetFileAttributesW
0x140003e26  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x140003e2d  call    cs:__imp_DeleteFileW
0x140003e33  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140003e37  jz      short loc_140003E42
0x140003e39  mov     rcx, rbx; hFindFile
0x140003e3c  call    cs:__imp_FindClose
0x140003e42  mov     rcx, [rbp+7E0h+var_30]
0x140003e49  xor     rcx, rsp; StackCookie
0x140003e4c  call    __security_check_cookie
0x140003e51  lea     r11, [rsp+8E0h+var_20]
0x140003e59  mov     rbx, [r11+40h]
0x140003e5d  mov     rsi, [r11+48h]
0x140003e61  mov     rsp, r11
0x140003e64  pop     r15
0x140003e66  pop     r14
0x140003e68  pop     r12
0x140003e6a  pop     rdi
0x140003e6b  pop     rbp
0x140003e6c  retn
```
