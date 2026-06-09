# CheckDirForExecutable(_PROCESS_ENTRY *,ushort const *,ushort const *,ushort *,int (*)(ushort const *,void *),void *)

- ea: `0x1801a85f8`
- end: `0x1801a8956`
- name: `?CheckDirForExecutable@@YAHPEAU_PROCESS_ENTRY@@PEBG1PEAGP6AH1PEAX@Z3@Z`
- size: `862`
- prototype: `int(struct _PROCESS_ENTRY *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, int (*)(const unsigned __int16 *, void *), void *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1801a8ed0`

## callees

- `0x180012e28`
- `0x180012e6c`
- `0x180012ed4`
- `0x1800181c8`
- `0x180023244`
- `0x180027430`
- `0x180195d78`
- `0x1801a85f8`
- `0x1801a932c`
- `0x1801a93a0`
- `0x1801aef0c`
- `0x1801af030`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x1801a88eb`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x1801a88eb`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1801a8798`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1801a8798`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801a88b5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801a894c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801a88b5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801a894c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801a88a4`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801a88a4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1801a8718`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1801a8718`

## pseudocode

```c
__int64 __fastcall CheckDirForExecutable(
        struct _PROCESS_ENTRY *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        int (*a5)(const unsigned __int16 *, void *),
        PVOID CallerData)
{
  unsigned __int64 v10; // r8
  HANDLE FirstFileW; // rdi
  unsigned __int64 v12; // r8
  unsigned __int64 v13; // rdx
  unsigned int v15; // ebx
  struct _PROCESS_ENTRY *v16; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+58h] [rbp-A8h]
  int v18; // [rsp+5Ch] [rbp-A4h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v20[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR FileName[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  wchar_t Filename; // [rsp+6D0h] [rbp+5D0h] BYREF
  _BYTE v23[526]; // [rsp+6D2h] [rbp+5D2h] BYREF
  unsigned __int16 v24[264]; // [rsp+8E0h] [rbp+7E0h] BYREF
  wchar_t Ext[264]; // [rsp+AF0h] [rbp+9F0h] BYREF

  Filename = 0;
  memset_0(v23, 0, 0x200u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v16 = a1;
  v18 = 0;
  v17 = MarkOperationStart(a1, &v18);
  if ( (unsigned int)CancellationCheck::IsCancelled((CancellationCheck *)&v16) )
    return 0;
  if ( !(unsigned int)bldpath(v24, 0x105u, a2, a3, 0) )
    return 0;
  ShortFileName(v24, FileName, v10);
  if ( !(unsigned int)bldpath(FileName, 0x105u, v24, L"*", 0) )
    return 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
    return 0;
  if ( (unsigned int)bldpath(v24, 0x105u, a2, a3, 0) )
  {
    ShortFileName(v24, FileName, v12);
    _wsplitpath_s(FileName, 0, 0, 0, 0, &Filename, 0x101u, Ext, 0x101u);
    while ( !(unsigned int)CancellationCheck::IsCancelled((CancellationCheck *)&v16) )
    {
      if ( FindFileData.cFileName[0] == 46
        && !FindFileData.cFileName[1]
        && (unsigned int)bldpath(v20, 0x105u, FileName, FindFileData.cFileName, 0)
        && (!(unsigned int)isdir(v20)
         || (unsigned int)BackslashCat(v20, 261)
         && !wcscat_s_ex(v20, v13, &Filename)
         && !wcscat_s_ex(v20, 0x105u, Ext)
         && !(unsigned int)fileexists(v20)) )
      {
        if ( (unsigned int)wcscpy_s_ex(a4, 0x105u, v20) )
          break;
        if ( cbFindExeSrchTree(a4, CallerData) )
        {
          v15 = 1;
          goto LABEL_25;
        }
        *a4 = 0;
      }
      if ( !FindNextFileW(FirstFileW, &FindFileData) )
      {
        FindClose(FirstFileW);
        _o__wmakepath_s(v20, 261, &word_18022B134, FileName, &Filename, Ext);
        if ( (unsigned int)fileexists(v20) )
          wcscpy_s_ex(a4, 0x105u, v20);
        return 0;
      }
    }
  }
  v15 = 0;
LABEL_25:
  FindClose(FirstFileW);
  return v15;
}

```

## disassembly

```asm
0x1801a85f8  mov     [rsp-8+arg_0], rbx
0x1801a85fd  push    rbp
0x1801a85fe  push    rsi
0x1801a85ff  push    rdi
0x1801a8600  push    r12
0x1801a8602  push    r13
0x1801a8604  push    r14
0x1801a8606  push    r15
0x1801a8608  lea     rbp, [rsp-0C10h]
0x1801a8610  sub     rsp, 0D10h
0x1801a8617  mov     rax, cs:__security_cookie
0x1801a861e  xor     rax, rsp
0x1801a8621  mov     [rbp+0C40h+var_40], rax
0x1801a8628  mov     r12, [rbp+0C40h+CallerData]
0x1801a862f  mov     r15, r8
0x1801a8632  mov     r14, rdx
0x1801a8635  mov     rbx, rcx
0x1801a8638  xor     r13d, r13d
0x1801a863b  lea     rcx, [rbp+0C40h+var_66E]; void *
0x1801a8642  xor     edx, edx; Val
0x1801a8644  mov     [rbp+0C40h+var_670], r13w
0x1801a864c  mov     r8d, 200h; Size
0x1801a8652  mov     rsi, r9
0x1801a8655  call    memset_0
0x1801a865a  mov     edi, 250h
0x1801a865f  lea     rcx, [rsp+0D40h+FindFileData]; void *
0x1801a8664  mov     r8d, edi; Size
0x1801a8667  xor     edx, edx; Val
0x1801a8669  call    memset_0
0x1801a866e  lea     rdx, [rsp+0D40h+var_CE4]
0x1801a8673  mov     [rsp+0D40h+var_CF0], rbx
0x1801a8678  mov     rcx, rbx
0x1801a867b  mov     [rsp+58h], r13
0x1801a8680  call    MarkOperationStart
0x1801a8685  lea     rcx, [rsp+0D40h+var_CF0]; this
0x1801a868a  mov     [rsp+0D40h+var_CE8], eax
0x1801a868e  call    ?IsCancelled@CancellationCheck@@QEBAHXZ; CancellationCheck::IsCancelled(void)
0x1801a8693  test    eax, eax
0x1801a8695  jnz     loc_1801A8913
0x1801a869b  mov     ebx, 105h
0x1801a86a0  mov     [rsp+0D40h+DirCount], r13
0x1801a86a5  mov     edx, ebx; unsigned __int64
0x1801a86a7  lea     rcx, [rbp+0C40h+var_460]; unsigned __int16 *
0x1801a86ae  mov     r9, r15
0x1801a86b1  mov     r8, r14
0x1801a86b4  call    ?bldpath@@YAHPEAG_KZZ; bldpath(ushort *,unsigned __int64,...)
0x1801a86b9  test    eax, eax
0x1801a86bb  jz      loc_1801A8913
0x1801a86c1  lea     rdx, [rbp+0C40h+FileName]; unsigned __int16 *
0x1801a86c8  lea     rcx, [rbp+0C40h+var_460]; unsigned __int16 *
0x1801a86cf  call    ?ShortFileName@@YAHPEBGPEAG_K@Z; ShortFileName(ushort const *,ushort *,unsigned __int64)
0x1801a86d4  lea     r9, asc_18024F6FC; "*"
0x1801a86db  mov     [rsp+0D40h+DirCount], r13
0x1801a86e0  lea     r8, [rbp+0C40h+var_460]
0x1801a86e7  mov     edx, ebx; unsigned __int64
0x1801a86e9  lea     rcx, [rbp+0C40h+FileName]; unsigned __int16 *
0x1801a86f0  call    ?bldpath@@YAHPEAG_KZZ; bldpath(ushort *,unsigned __int64,...)
0x1801a86f5  test    eax, eax
0x1801a86f7  jz      loc_1801A8913
0x1801a86fd  mov     r8d, edi; Size
0x1801a8700  lea     rcx, [rsp+0D40h+FindFileData]; void *
0x1801a8705  xor     edx, edx; Val
0x1801a8707  call    memset_0
0x1801a870c  lea     rdx, [rsp+0D40h+FindFileData]; lpFindFileData
0x1801a8711  lea     rcx, [rbp+0C40h+FileName]; lpFileName
0x1801a8718  call    cs:__imp_FindFirstFileW
0x1801a871e  mov     rdi, rax
0x1801a8721  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a8725  jz      loc_1801A8913
0x1801a872b  mov     r9, r15
0x1801a872e  mov     [rsp+0D40h+DirCount], r13
0x1801a8733  mov     r8, r14
0x1801a8736  lea     rcx, [rbp+0C40h+var_460]; unsigned __int16 *
0x1801a873d  mov     edx, ebx; unsigned __int64
0x1801a873f  call    ?bldpath@@YAHPEAG_KZZ; bldpath(ushort *,unsigned __int64,...)
0x1801a8744  test    eax, eax
0x1801a8746  jz      loc_1801A8946
0x1801a874c  lea     rdx, [rbp+0C40h+FileName]; unsigned __int16 *
0x1801a8753  lea     rcx, [rbp+0C40h+var_460]; unsigned __int16 *
0x1801a875a  call    ?ShortFileName@@YAHPEBGPEAG_K@Z; ShortFileName(ushort const *,ushort *,unsigned __int64)
0x1801a875f  lea     ecx, [rbx-4]
0x1801a8762  xor     r9d, r9d; Dir
0x1801a8765  mov     [rsp+0D40h+ExtCount], rcx; ExtCount
0x1801a876a  lea     rax, [rbp+0C40h+var_250]
0x1801a8771  mov     [rsp+0D40h+Ext], rax; Ext
0x1801a8776  xor     r8d, r8d; DriveCount
0x1801a8779  mov     [rsp+0D40h+FilenameCount], rcx; FilenameCount
0x1801a877e  lea     rax, [rbp+0C40h+var_670]
0x1801a8785  mov     [rsp+0D40h+Filename], rax; Filename
0x1801a878a  lea     rcx, [rbp+0C40h+FileName]; FullPath
0x1801a8791  xor     edx, edx; Drive
0x1801a8793  mov     [rsp+0D40h+DirCount], r13; DirCount
0x1801a8798  call    cs:__imp__wsplitpath_s
0x1801a879e  lea     rcx, [rsp+0D40h+var_CF0]; this
0x1801a87a3  call    ?IsCancelled@CancellationCheck@@QEBAHXZ; CancellationCheck::IsCancelled(void)
0x1801a87a8  test    eax, eax
0x1801a87aa  jnz     loc_1801A8946
0x1801a87b0  cmp     [rbp+0C40h+FindFileData.cFileName], 2Eh ; '.'
0x1801a87b5  jnz     loc_1801A889C
0x1801a87bb  movzx   eax, [rbp+0C40h+FindFileData.cFileName+2]
0x1801a87bf  test    ax, ax
0x1801a87c2  jnz     loc_1801A889C
0x1801a87c8  cmp     [rbp+0C40h+FindFileData.cFileName], 2Eh ; '.'
0x1801a87cd  jnz     short loc_1801A87E0
0x1801a87cf  cmp     ax, 2Eh ; '.'
0x1801a87d3  jnz     short loc_1801A87E0
0x1801a87d5  cmp     [rbp+0C40h+FindFileData.cFileName+4], r13w
0x1801a87da  jz      loc_1801A889C
0x1801a87e0  lea     r9, [rbp+0C40h+FindFileData.cFileName]
0x1801a87e4  mov     [rsp+0D40h+DirCount], r13
0x1801a87e9  lea     r8, [rbp+0C40h+FileName]
0x1801a87f0  mov     rdx, rbx; unsigned __int64
0x1801a87f3  lea     rcx, [rbp+0C40h+var_A90]; unsigned __int16 *
0x1801a87fa  call    ?bldpath@@YAHPEAG_KZZ; bldpath(ushort *,unsigned __int64,...)
0x1801a87ff  test    eax, eax
0x1801a8801  jz      loc_1801A889C
0x1801a8807  lea     rcx, [rbp+0C40h+var_A90]; unsigned __int16 *
0x1801a880e  call    ?isdir@@YAHPEBG@Z; isdir(ushort const *)
0x1801a8813  test    eax, eax
0x1801a8815  jz      short loc_1801A886B
0x1801a8817  mov     rdx, rbx
0x1801a881a  lea     rcx, [rbp+0C40h+var_A90]
0x1801a8821  call    BackslashCat
0x1801a8826  test    eax, eax
0x1801a8828  jz      short loc_1801A889C
0x1801a882a  lea     r8, [rbp+0C40h+var_670]; unsigned __int16 *
0x1801a8831  lea     rcx, [rbp+0C40h+var_A90]; unsigned __int16 *
0x1801a8838  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a883d  test    eax, eax
0x1801a883f  jnz     short loc_1801A889C
0x1801a8841  lea     r8, [rbp+0C40h+var_250]; unsigned __int16 *
0x1801a8848  mov     rdx, rbx; unsigned __int64
0x1801a884b  lea     rcx, [rbp+0C40h+var_A90]; unsigned __int16 *
0x1801a8852  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a8857  test    eax, eax
0x1801a8859  jnz     short loc_1801A889C
0x1801a885b  lea     rcx, [rbp+0C40h+var_A90]; unsigned __int16 *
0x1801a8862  call    ?fileexists@@YAHPEBG@Z; fileexists(ushort const *)
0x1801a8867  test    eax, eax
0x1801a8869  jnz     short loc_1801A889C
0x1801a886b  lea     r8, [rbp+0C40h+var_A90]; unsigned __int16 *
0x1801a8872  mov     rdx, rbx; unsigned __int64
0x1801a8875  mov     rcx, rsi; unsigned __int16 *
0x1801a8878  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a887d  test    eax, eax
0x1801a887f  jnz     loc_1801A8946
0x1801a8885  mov     rdx, r12; CallerData
0x1801a8888  mov     rcx, rsi; FilePath
0x1801a888b  call    ?cbFindExeSrchTree@@YAHPEBGPEAX@Z; cbFindExeSrchTree(ushort const *,void *)
0x1801a8890  test    eax, eax
0x1801a8892  jnz     loc_1801A893F
0x1801a8898  mov     [rsi], r13w
0x1801a889c  lea     rdx, [rsp+0D40h+FindFileData]; lpFindFileData
0x1801a88a1  mov     rcx, rdi; hFindFile
0x1801a88a4  call    cs:__imp_FindNextFileW
0x1801a88aa  test    eax, eax
0x1801a88ac  jnz     loc_1801A879E
0x1801a88b2  mov     rcx, rdi; hFindFile
0x1801a88b5  call    cs:__imp_FindClose
0x1801a88bb  lea     rax, [rbp+0C40h+var_250]
0x1801a88c2  mov     rdx, rbx
0x1801a88c5  mov     [rsp+0D40h+Filename], rax
0x1801a88ca  lea     r9, [rbp+0C40h+FileName]
0x1801a88d1  lea     rax, [rbp+0C40h+var_670]
0x1801a88d8  lea     r8, word_18022B134
0x1801a88df  mov     [rsp+0D40h+DirCount], rax
0x1801a88e4  lea     rcx, [rbp+0C40h+var_A90]
0x1801a88eb  call    cs:__imp__o__wmakepath_s
0x1801a88f1  lea     rcx, [rbp+0C40h+var_A90]; unsigned __int16 *
0x1801a88f8  call    ?fileexists@@YAHPEBG@Z; fileexists(ushort const *)
0x1801a88fd  test    eax, eax
0x1801a88ff  jz      short loc_1801A8913
0x1801a8901  lea     r8, [rbp+0C40h+var_A90]; unsigned __int16 *
0x1801a8908  mov     rdx, rbx; unsigned __int64
0x1801a890b  mov     rcx, rsi; unsigned __int16 *
0x1801a890e  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a8913  xor     eax, eax
0x1801a8915  mov     rcx, [rbp+0C40h+var_40]
0x1801a891c  xor     rcx, rsp; StackCookie
0x1801a891f  call    __security_check_cookie
0x1801a8924  mov     rbx, [rsp+0D40h+arg_0]
0x1801a892c  add     rsp, 0D10h
0x1801a8933  pop     r15
0x1801a8935  pop     r14
0x1801a8937  pop     r13
0x1801a8939  pop     r12
0x1801a893b  pop     rdi
0x1801a893c  pop     rsi
0x1801a893d  pop     rbp
0x1801a893e  retn
0x1801a893f  mov     ebx, 1
0x1801a8944  jmp     short loc_1801A8949
0x1801a8946  mov     ebx, r13d
0x1801a8949  mov     rcx, rdi; hFindFile
0x1801a894c  call    cs:__imp_FindClose
0x1801a8952  mov     eax, ebx
0x1801a8954  jmp     short loc_1801A8915
```
