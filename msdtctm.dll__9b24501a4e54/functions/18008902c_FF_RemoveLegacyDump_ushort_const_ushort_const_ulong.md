# FF_RemoveLegacyDump(ushort const *,ushort const *,ulong)

- ea: `0x18008902c`
- end: `0x180089216`
- name: `?FF_RemoveLegacyDump@@YAXPEBG0K@Z`
- size: `490`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180088b84`

## callees

- `0x180008a50`
- `0x180016f3c`
- `0x180084e88`
- `0x18008902c`
- `0x1800b83ee`
- `0x1800b8420`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18008919b`
- `msvcrt!wcsrchr` at `0x18008919b`
- `msvcrt!_wcsicmp` at `0x180089113`
- `msvcrt!_wcsicmp` at `0x180089113`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800891e5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800891e5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18008918b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800891d6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18008918b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800891d6`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18008917e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800891c9`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18008917e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800891c9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800890e6`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800890e6`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180089139`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180089139`

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
0x18008902c  mov     [rsp-8+arg_10], rbx
0x180089031  mov     [rsp-8+arg_18], rsi
0x180089036  push    rbp
0x180089037  push    rdi
0x180089038  push    r12
0x18008903a  push    r14
0x18008903c  push    r15
0x18008903e  lea     rbp, [rsp-7C0h]
0x180089046  sub     rsp, 8C0h
0x18008904d  mov     rax, cs:__security_cookie
0x180089054  xor     rax, rsp
0x180089057  mov     [rbp+7E0h+var_30], rax
0x18008905e  mov     esi, r8d
0x180089061  mov     r14, rdx
0x180089064  mov     rbx, rcx
0x180089067  xor     edx, edx; Val
0x180089069  mov     r8d, 208h; Size
0x18008906f  lea     rcx, [rbp+7E0h+FileName]; void *
0x180089076  call    memset_0
0x18008907b  mov     edi, 20Ah
0x180089080  lea     rcx, [rbp+7E0h+String1]; void *
0x180089087  mov     r8d, edi; Size
0x18008908a  xor     edx, edx; Val
0x18008908c  call    memset_0
0x180089091  mov     r8d, edi; Size
0x180089094  lea     rcx, [rbp+7E0h+Str]; void *
0x18008909b  xor     edx, edx; Val
0x18008909d  call    memset_0
0x1800890a2  xor     r15d, r15d
0x1800890a5  lea     rcx, [rsp+8E0h+FindFileData]; void *
0x1800890aa  xor     edx, edx; Val
0x1800890ac  mov     r8d, 250h; Size
0x1800890b2  mov     edi, r15d
0x1800890b5  call    memset_0
0x1800890ba  mov     r9, r14
0x1800890bd  mov     [rsp+8E0h+var_8C0], rbx
0x1800890c2  lea     r8, aSSDmp_0; "%s\\%s*.dmp"
0x1800890c9  mov     edx, 104h; unsigned __int64
0x1800890ce  lea     rcx, [rbp+7E0h+FileName]; unsigned __int16 *
0x1800890d5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800890da  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x1800890df  lea     rcx, [rbp+7E0h+FileName]; lpFileName
0x1800890e6  call    cs:__imp_FindFirstFileW
0x1800890ec  mov     rbx, rax
0x1800890ef  mov     r12d, 105h
0x1800890f5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800890f9  jz      short loc_180089143
0x1800890fb  inc     edi
0x1800890fd  cmp     [rbp+7E0h+String1], r15w
0x180089105  jz      short loc_18008911D
0x180089107  lea     rdx, [rsp+8E0h+FindFileData.cFileName]; String2
0x18008910c  lea     rcx, [rbp+7E0h+String1]; String1
0x180089113  call    cs:__imp__wcsicmp
0x180089119  test    eax, eax
0x18008911b  jle     short loc_180089131
0x18008911d  lea     r8, [rsp+8E0h+FindFileData.cFileName]; unsigned __int16 *
0x180089122  mov     rdx, r12; unsigned __int64
0x180089125  lea     rcx, [rbp+7E0h+String1]; unsigned __int16 *
0x18008912c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180089131  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x180089136  mov     rcx, rbx; hFindFile
0x180089139  call    cs:__imp_FindNextFileW
0x18008913f  test    eax, eax
0x180089141  jnz     short loc_1800890FB
0x180089143  cmp     edi, esi
0x180089145  jb      loc_1800891DC
0x18008914b  lea     rax, [rbp+7E0h+String1]
0x180089152  mov     r9, r14
0x180089155  lea     r8, aSS_1; "%s\\%s"
0x18008915c  mov     [rsp+8E0h+var_8C0], rax
0x180089161  mov     rdx, r12; unsigned __int64
0x180089164  lea     rcx, [rbp+7E0h+Str]; unsigned __int16 *
0x18008916b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180089170  mov     edi, 80h
0x180089175  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x18008917c  mov     edx, edi; dwFileAttributes
0x18008917e  call    cs:__imp_SetFileAttributesW
0x180089184  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x18008918b  call    cs:__imp_DeleteFileW
0x180089191  lea     edx, [rdi-52h]; Ch
0x180089194  lea     rcx, [rbp+7E0h+Str]; Str
0x18008919b  call    cs:__imp_wcsrchr
0x1800891a1  test    rax, rax
0x1800891a4  jz      short loc_1800891DC
0x1800891a6  lea     r8, aTxt; ".txt"
0x1800891ad  mov     [rax], r15w
0x1800891b1  mov     rdx, r12; unsigned __int64
0x1800891b4  lea     rcx, [rbp+7E0h+Str]; unsigned __int16 *
0x1800891bb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800891c0  mov     edx, edi; dwFileAttributes
0x1800891c2  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x1800891c9  call    cs:__imp_SetFileAttributesW
0x1800891cf  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x1800891d6  call    cs:__imp_DeleteFileW
0x1800891dc  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800891e0  jz      short loc_1800891EB
0x1800891e2  mov     rcx, rbx; hFindFile
0x1800891e5  call    cs:__imp_FindClose
0x1800891eb  mov     rcx, [rbp+7E0h+var_30]
0x1800891f2  xor     rcx, rsp; StackCookie
0x1800891f5  call    __security_check_cookie
0x1800891fa  lea     r11, [rsp+8E0h+var_20]
0x180089202  mov     rbx, [r11+40h]
0x180089206  mov     rsi, [r11+48h]
0x18008920a  mov     rsp, r11
0x18008920d  pop     r15
0x18008920f  pop     r14
0x180089211  pop     r12
0x180089213  pop     rdi
0x180089214  pop     rbp
0x180089215  retn
```
