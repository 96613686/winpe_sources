# FF_RemoveLegacyDump(ushort const *,ushort const *,ulong)

- ea: `0x18004370c`
- end: `0x1800438f6`
- name: `?FF_RemoveLegacyDump@@YAXPEBG0K@Z`
- size: `490`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180043264`

## callees

- `0x180001e60`
- `0x18000717c`
- `0x180014ec8`
- `0x18004370c`
- `0x18005583a`
- `0x180055880`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800437f3`
- `msvcrt!_wcsicmp` at `0x1800437f3`
- `msvcrt!wcsrchr` at `0x18004387b`
- `msvcrt!wcsrchr` at `0x18004387b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004386b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800438b6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18004386b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800438b6`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800437c6`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800437c6`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180043819`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180043819`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800438c5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800438c5`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18004385e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800438a9`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18004385e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800438a9`

## pseudocode

```c
void __fastcall FF_RemoveLegacyDump(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned int a3)
{
  unsigned int v6; // edi
  HANDLE FirstFileW; // rbx
  wchar_t *v8; // rax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
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
0x18004370c  mov     [rsp-8+arg_10], rbx
0x180043711  mov     [rsp-8+arg_18], rsi
0x180043716  push    rbp
0x180043717  push    rdi
0x180043718  push    r12
0x18004371a  push    r14
0x18004371c  push    r15
0x18004371e  lea     rbp, [rsp-7C0h]
0x180043726  sub     rsp, 8C0h
0x18004372d  mov     rax, cs:__security_cookie
0x180043734  xor     rax, rsp
0x180043737  mov     [rbp+7E0h+var_30], rax
0x18004373e  mov     esi, r8d
0x180043741  mov     r14, rdx
0x180043744  mov     rbx, rcx
0x180043747  xor     edx, edx; Val
0x180043749  mov     r8d, 208h; Size
0x18004374f  lea     rcx, [rbp+7E0h+FileName]; void *
0x180043756  call    memset_0
0x18004375b  mov     edi, 20Ah
0x180043760  lea     rcx, [rbp+7E0h+String1]; void *
0x180043767  mov     r8d, edi; Size
0x18004376a  xor     edx, edx; Val
0x18004376c  call    memset_0
0x180043771  mov     r8d, edi; Size
0x180043774  lea     rcx, [rbp+7E0h+Str]; void *
0x18004377b  xor     edx, edx; Val
0x18004377d  call    memset_0
0x180043782  xor     r15d, r15d
0x180043785  lea     rcx, [rsp+8E0h+FindFileData]; void *
0x18004378a  xor     edx, edx; Val
0x18004378c  mov     r8d, 250h; Size
0x180043792  mov     edi, r15d
0x180043795  call    memset_0
0x18004379a  mov     r9, r14
0x18004379d  mov     [rsp+8E0h+var_8C0], rbx
0x1800437a2  lea     r8, aSSDmp; "%s\\%s*.dmp"
0x1800437a9  mov     edx, 104h; unsigned __int64
0x1800437ae  lea     rcx, [rbp+7E0h+FileName]; unsigned __int16 *
0x1800437b5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800437ba  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x1800437bf  lea     rcx, [rbp+7E0h+FileName]; lpFileName
0x1800437c6  call    cs:__imp_FindFirstFileW
0x1800437cc  mov     rbx, rax
0x1800437cf  mov     r12d, 105h
0x1800437d5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800437d9  jz      short loc_180043823
0x1800437db  inc     edi
0x1800437dd  cmp     [rbp+7E0h+String1], r15w
0x1800437e5  jz      short loc_1800437FD
0x1800437e7  lea     rdx, [rsp+8E0h+FindFileData.cFileName]; String2
0x1800437ec  lea     rcx, [rbp+7E0h+String1]; String1
0x1800437f3  call    cs:__imp__wcsicmp
0x1800437f9  test    eax, eax
0x1800437fb  jle     short loc_180043811
0x1800437fd  lea     r8, [rsp+8E0h+FindFileData.cFileName]; unsigned __int16 *
0x180043802  mov     rdx, r12; unsigned __int64
0x180043805  lea     rcx, [rbp+7E0h+String1]; unsigned __int16 *
0x18004380c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180043811  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x180043816  mov     rcx, rbx; hFindFile
0x180043819  call    cs:__imp_FindNextFileW
0x18004381f  test    eax, eax
0x180043821  jnz     short loc_1800437DB
0x180043823  cmp     edi, esi
0x180043825  jb      loc_1800438BC
0x18004382b  lea     rax, [rbp+7E0h+String1]
0x180043832  mov     r9, r14
0x180043835  lea     r8, aSS_0; "%s\\%s"
0x18004383c  mov     [rsp+8E0h+var_8C0], rax
0x180043841  mov     rdx, r12; unsigned __int64
0x180043844  lea     rcx, [rbp+7E0h+Str]; unsigned __int16 *
0x18004384b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180043850  mov     edi, 80h
0x180043855  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x18004385c  mov     edx, edi; dwFileAttributes
0x18004385e  call    cs:__imp_SetFileAttributesW
0x180043864  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x18004386b  call    cs:__imp_DeleteFileW
0x180043871  lea     edx, [rdi-52h]; Ch
0x180043874  lea     rcx, [rbp+7E0h+Str]; Str
0x18004387b  call    cs:__imp_wcsrchr
0x180043881  test    rax, rax
0x180043884  jz      short loc_1800438BC
0x180043886  lea     r8, aTxt; ".txt"
0x18004388d  mov     [rax], r15w
0x180043891  mov     rdx, r12; unsigned __int64
0x180043894  lea     rcx, [rbp+7E0h+Str]; unsigned __int16 *
0x18004389b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800438a0  mov     edx, edi; dwFileAttributes
0x1800438a2  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x1800438a9  call    cs:__imp_SetFileAttributesW
0x1800438af  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x1800438b6  call    cs:__imp_DeleteFileW
0x1800438bc  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800438c0  jz      short loc_1800438CB
0x1800438c2  mov     rcx, rbx; hFindFile
0x1800438c5  call    cs:__imp_FindClose
0x1800438cb  mov     rcx, [rbp+7E0h+var_30]
0x1800438d2  xor     rcx, rsp; StackCookie
0x1800438d5  call    __security_check_cookie
0x1800438da  lea     r11, [rsp+8E0h+var_20]
0x1800438e2  mov     rbx, [r11+40h]
0x1800438e6  mov     rsi, [r11+48h]
0x1800438ea  mov     rsp, r11
0x1800438ed  pop     r15
0x1800438ef  pop     r14
0x1800438f1  pop     r12
0x1800438f3  pop     rdi
0x1800438f4  pop     rbp
0x1800438f5  retn
```
