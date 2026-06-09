# FF_RemoveLegacyDump(ushort const *,ushort const *,ulong)

- ea: `0x180032554`
- end: `0x18003273e`
- name: `?FF_RemoveLegacyDump@@YAXPEBG0K@Z`
- size: `490`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800320ac`

## callees

- `0x180009ee0`
- `0x18000a01c`
- `0x18001ec1c`
- `0x180032554`
- `0x18005551a`
- `0x180055550`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1800326c3`
- `msvcrt!wcsrchr` at `0x1800326c3`
- `msvcrt!_wcsicmp` at `0x18003263b`
- `msvcrt!_wcsicmp` at `0x18003263b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003270d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003270d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180032661`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180032661`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003260e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003260e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800326b3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800326fe`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800326b3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800326fe`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800326a6`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800326f1`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800326a6`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800326f1`

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
0x180032554  mov     [rsp-8+arg_10], rbx
0x180032559  mov     [rsp-8+arg_18], rsi
0x18003255e  push    rbp
0x18003255f  push    rdi
0x180032560  push    r12
0x180032562  push    r14
0x180032564  push    r15
0x180032566  lea     rbp, [rsp-7C0h]
0x18003256e  sub     rsp, 8C0h
0x180032575  mov     rax, cs:__security_cookie
0x18003257c  xor     rax, rsp
0x18003257f  mov     [rbp+7E0h+var_30], rax
0x180032586  mov     esi, r8d
0x180032589  mov     r14, rdx
0x18003258c  mov     rbx, rcx
0x18003258f  xor     edx, edx; Val
0x180032591  mov     r8d, 208h; Size
0x180032597  lea     rcx, [rbp+7E0h+FileName]; void *
0x18003259e  call    memset_0
0x1800325a3  mov     edi, 20Ah
0x1800325a8  lea     rcx, [rbp+7E0h+String1]; void *
0x1800325af  mov     r8d, edi; Size
0x1800325b2  xor     edx, edx; Val
0x1800325b4  call    memset_0
0x1800325b9  mov     r8d, edi; Size
0x1800325bc  lea     rcx, [rbp+7E0h+Str]; void *
0x1800325c3  xor     edx, edx; Val
0x1800325c5  call    memset_0
0x1800325ca  xor     r15d, r15d
0x1800325cd  lea     rcx, [rsp+8E0h+FindFileData]; void *
0x1800325d2  xor     edx, edx; Val
0x1800325d4  mov     r8d, 250h; Size
0x1800325da  mov     edi, r15d
0x1800325dd  call    memset_0
0x1800325e2  mov     r9, r14
0x1800325e5  mov     [rsp+8E0h+var_8C0], rbx
0x1800325ea  lea     r8, aSSDmp; "%s\\%s*.dmp"
0x1800325f1  mov     edx, 104h; unsigned __int64
0x1800325f6  lea     rcx, [rbp+7E0h+FileName]; unsigned __int16 *
0x1800325fd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032602  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x180032607  lea     rcx, [rbp+7E0h+FileName]; lpFileName
0x18003260e  call    cs:__imp_FindFirstFileW
0x180032614  mov     rbx, rax
0x180032617  mov     r12d, 105h
0x18003261d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180032621  jz      short loc_18003266B
0x180032623  inc     edi
0x180032625  cmp     [rbp+7E0h+String1], r15w
0x18003262d  jz      short loc_180032645
0x18003262f  lea     rdx, [rsp+8E0h+FindFileData.cFileName]; String2
0x180032634  lea     rcx, [rbp+7E0h+String1]; String1
0x18003263b  call    cs:__imp__wcsicmp
0x180032641  test    eax, eax
0x180032643  jle     short loc_180032659
0x180032645  lea     r8, [rsp+8E0h+FindFileData.cFileName]; unsigned __int16 *
0x18003264a  mov     rdx, r12; unsigned __int64
0x18003264d  lea     rcx, [rbp+7E0h+String1]; unsigned __int16 *
0x180032654  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180032659  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x18003265e  mov     rcx, rbx; hFindFile
0x180032661  call    cs:__imp_FindNextFileW
0x180032667  test    eax, eax
0x180032669  jnz     short loc_180032623
0x18003266b  cmp     edi, esi
0x18003266d  jb      loc_180032704
0x180032673  lea     rax, [rbp+7E0h+String1]
0x18003267a  mov     r9, r14
0x18003267d  lea     r8, aSS; "%s\\%s"
0x180032684  mov     [rsp+8E0h+var_8C0], rax
0x180032689  mov     rdx, r12; unsigned __int64
0x18003268c  lea     rcx, [rbp+7E0h+Str]; unsigned __int16 *
0x180032693  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180032698  mov     edi, 80h
0x18003269d  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x1800326a4  mov     edx, edi; dwFileAttributes
0x1800326a6  call    cs:__imp_SetFileAttributesW
0x1800326ac  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x1800326b3  call    cs:__imp_DeleteFileW
0x1800326b9  lea     edx, [rdi-52h]; Ch
0x1800326bc  lea     rcx, [rbp+7E0h+Str]; Str
0x1800326c3  call    cs:__imp_wcsrchr
0x1800326c9  test    rax, rax
0x1800326cc  jz      short loc_180032704
0x1800326ce  lea     r8, aTxt; ".txt"
0x1800326d5  mov     [rax], r15w
0x1800326d9  mov     rdx, r12; unsigned __int64
0x1800326dc  lea     rcx, [rbp+7E0h+Str]; unsigned __int16 *
0x1800326e3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800326e8  mov     edx, edi; dwFileAttributes
0x1800326ea  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x1800326f1  call    cs:__imp_SetFileAttributesW
0x1800326f7  lea     rcx, [rbp+7E0h+Str]; lpFileName
0x1800326fe  call    cs:__imp_DeleteFileW
0x180032704  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180032708  jz      short loc_180032713
0x18003270a  mov     rcx, rbx; hFindFile
0x18003270d  call    cs:__imp_FindClose
0x180032713  mov     rcx, [rbp+7E0h+var_30]
0x18003271a  xor     rcx, rsp; StackCookie
0x18003271d  call    __security_check_cookie
0x180032722  lea     r11, [rsp+8E0h+var_20]
0x18003272a  mov     rbx, [r11+40h]
0x18003272e  mov     rsi, [r11+48h]
0x180032732  mov     rsp, r11
0x180032735  pop     r15
0x180032737  pop     r14
0x180032739  pop     r12
0x18003273b  pop     rdi
0x18003273c  pop     rbp
0x18003273d  retn
```
