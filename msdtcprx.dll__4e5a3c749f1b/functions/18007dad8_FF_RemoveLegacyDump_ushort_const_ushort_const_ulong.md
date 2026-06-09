# FF_RemoveLegacyDump(ushort const *,ushort const *,ulong)

- ea: `0x18007dad8`
- end: `0x18007dcc2`
- name: `?FF_RemoveLegacyDump@@YAXPEBG0K@Z`
- size: `490`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18007d630`

## callees

- `0x180006054`
- `0x18000c6bc`
- `0x180062658`
- `0x18007dad8`
- `0x180081d9e`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18007dc2a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18007dc75`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18007dc2a`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18007dc75`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18007dbe5`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18007dbe5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007dc37`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007dc82`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007dc37`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007dc82`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18007dc91`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18007dc91`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18007db92`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18007db92`
- `msvcrt!wcsrchr` at `0x18007dc47`
- `msvcrt!wcsrchr` at `0x18007dc47`
- `msvcrt!_wcsicmp` at `0x18007dbbf`
- `msvcrt!_wcsicmp` at `0x18007dbbf`

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
0x18007dad8  mov     [rsp-8+arg_10], rbx
0x18007dadd  mov     [rsp-8+arg_18], rsi
0x18007dae2  push    rbp
0x18007dae3  push    rdi
0x18007dae4  push    r12
0x18007dae6  push    r14
0x18007dae8  push    r15
0x18007daea  lea     rbp, [rsp-7C0h]
0x18007daf2  sub     rsp, 8C0h
0x18007daf9  mov     rax, cs:__security_cookie
0x18007db00  xor     rax, rsp
0x18007db03  mov     [rbp+7E0h+var_30], rax
0x18007db0a  mov     esi, r8d
0x18007db0d  mov     r14, rdx
0x18007db10  mov     rbx, rcx
0x18007db13  xor     edx, edx; Val
0x18007db15  mov     r8d, 208h; Size
0x18007db1b  lea     rcx, [rbp+7E0h+FileName]; void *
0x18007db22  call    memset_0
0x18007db27  mov     edi, 20Ah
0x18007db2c  lea     rcx, [rbp+7E0h+String1]; void *
0x18007db33  mov     r8d, edi; Size
0x18007db36  xor     edx, edx; Val
0x18007db38  call    memset_0
0x18007db3d  mov     r8d, edi; Size
0x18007db40  lea     rcx, [rbp+7E0h+Str]; void *
0x18007db47  xor     edx, edx; Val
0x18007db49  call    memset_0
0x18007db4e  xor     r15d, r15d
0x18007db51  lea     rcx, [rsp+8E0h+FindFileData]; void *
0x18007db56  xor     edx, edx; Val
0x18007db58  mov     r8d, 250h; Size
0x18007db5e  mov     edi, r15d
0x18007db61  call    memset_0
0x18007db66  mov     r9, r14
0x18007db69  mov     [rsp+8E0h+var_8C0], rbx
0x18007db6e  lea     r8, aSSDmp_0; "%s\\%s*.dmp"
0x18007db75  mov     edx, 104h; unsigned __int64
0x18007db7a  lea     rcx, [rbp+7E0h+FileName]; unsigned __int16 *
0x18007db81  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007db86  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x18007db8b  lea     rcx, [rbp+7E0h+FileName]; lpFileName
0x18007db92  call    cs:__imp_FindFirstFileW
0x18007db98  mov     rbx, rax
0x18007db9b  mov     r12d, 105h
0x18007dba1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007dba5  jz      short loc_18007DBEF
0x18007dba7  inc     edi
0x18007dba9  cmp     [rbp+7E0h+String1], r15w
0x18007dbb1  jz      short loc_18007DBC9
0x18007dbb3  lea     rdx, [rsp+8E0h+FindFileData.cFileName]; String2
0x18007dbb8  lea     rcx, [rbp+7E0h+String1]; String1
0x18007dbbf  call    cs:__imp__wcsicmp
0x18007dbc5  test    eax, eax
0x18007dbc7  jle     short loc_18007DBDD
0x18007dbc9  lea     r8, [rsp+8E0h+FindFileData.cFileName]; unsigned __int16 *
0x18007dbce  mov     rdx, r12; unsigned __int64
0x18007dbd1  lea     rcx, [rbp+7E0h+String1]; unsigned __int16 *
0x18007dbd8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007dbdd  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x18007dbe2  mov     rcx, rbx; hFindFile
0x18007dbe5  call    cs:__imp_FindNextFileW
0x18007dbeb  test    eax, eax
0x18007dbed  jnz     short loc_18007DBA7
0x18007dbef  cmp     edi, esi
0x18007dbf1  jb      loc_18007DC88
0x18007dbf7  lea     rax, [rbp+7E0h+String1]
0x18007dbfe  mov     r9, r14
0x18007dc01  lea     r8, aSS_1; "%s\\%s"
0x18007dc08  mov     [rsp+8E0h+var_8C0], rax
0x18007dc0d  mov     rdx, r12; unsigned __int64
0x18007dc10  lea     rcx, [rbp+7E0h+Str]; unsigned __int16 *
0x18007dc17  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007dc1c  mov     edi, 80h
0x18007dc21  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x18007dc28  mov     edx, edi; dwFileAttributes
0x18007dc2a  call    cs:__imp_SetFileAttributesW
0x18007dc30  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x18007dc37  call    cs:__imp_DeleteFileW
0x18007dc3d  lea     edx, [rdi-52h]; Ch
0x18007dc40  lea     rcx, [rbp+7E0h+Str]; Str
0x18007dc47  call    cs:__imp_wcsrchr
0x18007dc4d  test    rax, rax
0x18007dc50  jz      short loc_18007DC88
0x18007dc52  lea     r8, aTxt; ".txt"
0x18007dc59  mov     [rax], r15w
0x18007dc5d  mov     rdx, r12; unsigned __int64
0x18007dc60  lea     rcx, [rbp+7E0h+Str]; unsigned __int16 *
0x18007dc67  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18007dc6c  mov     edx, edi; dwFileAttributes
0x18007dc6e  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x18007dc75  call    cs:__imp_SetFileAttributesW
0x18007dc7b  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x18007dc82  call    cs:__imp_DeleteFileW
0x18007dc88  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18007dc8c  jz      short loc_18007DC97
0x18007dc8e  mov     rcx, rbx; hFindFile
0x18007dc91  call    cs:__imp_FindClose
0x18007dc97  mov     rcx, [rbp+7E0h+var_30]
0x18007dc9e  xor     rcx, rsp; StackCookie
0x18007dca1  call    __security_check_cookie
0x18007dca6  lea     r11, [rsp+8E0h+var_20]
0x18007dcae  mov     rbx, [r11+40h]
0x18007dcb2  mov     rsi, [r11+48h]
0x18007dcb6  mov     rsp, r11
0x18007dcb9  pop     r15
0x18007dcbb  pop     r14
0x18007dcbd  pop     r12
0x18007dcbf  pop     rdi
0x18007dcc0  pop     rbp
0x18007dcc1  retn
```
