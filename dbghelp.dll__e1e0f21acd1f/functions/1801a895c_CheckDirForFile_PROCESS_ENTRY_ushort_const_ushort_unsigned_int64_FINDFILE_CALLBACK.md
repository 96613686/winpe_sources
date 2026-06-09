# CheckDirForFile(_PROCESS_ENTRY *,ushort const *,ushort *,unsigned __int64,_FINDFILE_CALLBACK *)

- ea: `0x1801a895c`
- end: `0x1801a8c8f`
- name: `?CheckDirForFile@@YAHPEAU_PROCESS_ENTRY@@PEBGPEAG_KPEAU_FINDFILE_CALLBACK@@@Z`
- size: `819`
- prototype: `int(struct _PROCESS_ENTRY *, const unsigned __int16 *, unsigned __int16 *, unsigned __int64, struct _FINDFILE_CALLBACK *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18001a5fc`

## callees

- `0x180012e28`
- `0x180012e6c`
- `0x180012ed4`
- `0x1800181c8`
- `0x180023244`
- `0x180027430`
- `0x180195d78`
- `0x1801a895c`
- `0x1801a92b0`
- `0x1801aef0c`
- `0x1801af030`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1801a8ab1`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1801a8ab1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801a8bd5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801a8c85`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801a8bd5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801a8c85`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801a8bc4`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801a8bc4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1801a8a56`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1801a8a56`

## pseudocode

```c
__int64 __fastcall CheckDirForFile(
        struct _PROCESS_ENTRY *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4,
        struct _FINDFILE_CALLBACK *a5)
{
  unsigned __int64 v8; // r8
  unsigned __int64 v9; // rdx
  HANDLE FirstFileW; // rdi
  unsigned __int64 v11; // r8
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rdx
  unsigned int v16; // ebx
  struct _PROCESS_ENTRY *v17; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+58h] [rbp-A8h]
  int v19; // [rsp+5Ch] [rbp-A4h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v21[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR FileName[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  wchar_t Filename; // [rsp+6D0h] [rbp+5D0h] BYREF
  _BYTE v24[526]; // [rsp+6D2h] [rbp+5D2h] BYREF
  wchar_t Ext[264]; // [rsp+8E0h] [rbp+7E0h] BYREF

  Filename = 0;
  memset_0(v24, 0, 0x200u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v17 = a1;
  v19 = 0;
  v18 = MarkOperationStart(a1, &v19);
  if ( !(unsigned int)CancellationCheck::IsCancelled((CancellationCheck *)&v17) )
  {
    ShortFileName(a2, FileName, v8);
    if ( (unsigned int)BackslashCat(FileName, 261) )
    {
      wcscat_s_ex(FileName, v9, L"*");
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      FirstFileW = FindFirstFileW(FileName, &FindFileData);
      if ( FirstFileW != (HANDLE)-1LL )
      {
        ShortFileName(a2, FileName, v11);
        _wsplitpath_s(FileName, 0, 0, 0, 0, &Filename, 0x101u, Ext, 0x101u);
        do
        {
          if ( (unsigned int)CancellationCheck::IsCancelled((CancellationCheck *)&v17) )
          {
            v16 = 0;
            goto LABEL_24;
          }
          if ( FindFileData.cFileName[0] != 46
            || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
          {
            wcscpy_s_ex(v21, 0x105u, FileName);
            if ( (unsigned int)BackslashCat(v21, 261) )
            {
              wcscat_s_ex(v21, v12, FindFileData.cFileName);
              if ( !(unsigned int)isdir(v21)
                || (unsigned int)BackslashCat(v21, 261)
                && (wcscat_s_ex(v21, v13, &Filename), wcscat_s_ex(v21, 0x105u, Ext), (unsigned int)fileexists(v21)) )
              {
                wcscpy_s_ex(a3, 0x105u, v21);
                if ( !a5 )
                  break;
                if ( !FindFileCallback(a5, a3) )
                {
                  v16 = 1;
LABEL_24:
                  FindClose(FirstFileW);
                  return v16;
                }
                *a3 = 0;
              }
            }
          }
        }
        while ( FindNextFileW(FirstFileW, &FindFileData) );
        FindClose(FirstFileW);
        wcscpy_s_ex(v21, 0x105u, a2);
        if ( (unsigned int)BackslashCat(v21, 261) )
        {
          wcscat_s_ex(v21, v14, &Filename);
          wcscat_s_ex(v21, 0x105u, Ext);
          if ( (unsigned int)fileexists(v21) )
            wcscpy_s_ex(a3, 0x105u, v21);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1801a895c  mov     [rsp-8+arg_0], rbx
0x1801a8961  mov     [rsp-8+arg_18], rsi
0x1801a8966  push    rbp
0x1801a8967  push    rdi
0x1801a8968  push    r12
0x1801a896a  push    r14
0x1801a896c  push    r15
0x1801a896e  lea     rbp, [rsp-0A00h]
0x1801a8976  sub     rsp, 0B00h
0x1801a897d  mov     rax, cs:__security_cookie
0x1801a8984  xor     rax, rsp
0x1801a8987  mov     [rbp+0A20h+var_30], rax
0x1801a898e  mov     r15, [rbp+0A20h+arg_20]
0x1801a8995  mov     rsi, r8
0x1801a8998  mov     r14, rdx
0x1801a899b  mov     rbx, rcx
0x1801a899e  xor     r12d, r12d
0x1801a89a1  lea     rcx, [rbp+0A20h+var_44E]; void *
0x1801a89a8  xor     edx, edx; Val
0x1801a89aa  mov     [rbp+0A20h+var_450], r12w
0x1801a89b2  mov     r8d, 200h; Size
0x1801a89b8  call    memset_0
0x1801a89bd  mov     edi, 250h
0x1801a89c2  lea     rcx, [rsp+0B20h+FindFileData]; void *
0x1801a89c7  mov     r8d, edi; Size
0x1801a89ca  xor     edx, edx; Val
0x1801a89cc  call    memset_0
0x1801a89d1  lea     rdx, [rsp+0B20h+var_AC8+4]
0x1801a89d6  mov     [rsp+0B20h+var_AD0], rbx
0x1801a89db  mov     rcx, rbx
0x1801a89de  mov     [rsp+0B20h+var_AC8], r12
0x1801a89e3  call    MarkOperationStart
0x1801a89e8  lea     rcx, [rsp+0B20h+var_AD0]; this
0x1801a89ed  mov     dword ptr [rsp+0B20h+var_AC8], eax
0x1801a89f1  call    ?IsCancelled@CancellationCheck@@QEBAHXZ; CancellationCheck::IsCancelled(void)
0x1801a89f6  test    eax, eax
0x1801a89f8  jnz     loc_1801A8C4B
0x1801a89fe  lea     rdx, [rbp+0A20h+FileName]; unsigned __int16 *
0x1801a8a05  mov     rcx, r14; unsigned __int16 *
0x1801a8a08  call    ?ShortFileName@@YAHPEBGPEAG_K@Z; ShortFileName(ushort const *,ushort *,unsigned __int64)
0x1801a8a0d  mov     ebx, 105h
0x1801a8a12  lea     rcx, [rbp+0A20h+FileName]
0x1801a8a19  mov     edx, ebx
0x1801a8a1b  call    BackslashCat
0x1801a8a20  test    eax, eax
0x1801a8a22  jz      loc_1801A8C4B
0x1801a8a28  lea     r8, asc_18024F6FC; "*"
0x1801a8a2f  lea     rcx, [rbp+0A20h+FileName]; unsigned __int16 *
0x1801a8a36  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a8a3b  mov     r8d, edi; Size
0x1801a8a3e  lea     rcx, [rsp+0B20h+FindFileData]; void *
0x1801a8a43  xor     edx, edx; Val
0x1801a8a45  call    memset_0
0x1801a8a4a  lea     rdx, [rsp+0B20h+FindFileData]; lpFindFileData
0x1801a8a4f  lea     rcx, [rbp+0A20h+FileName]; lpFileName
0x1801a8a56  call    cs:__imp_FindFirstFileW
0x1801a8a5c  mov     rdi, rax
0x1801a8a5f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a8a63  jz      loc_1801A8C4B
0x1801a8a69  lea     rdx, [rbp+0A20h+FileName]; unsigned __int16 *
0x1801a8a70  mov     rcx, r14; unsigned __int16 *
0x1801a8a73  call    ?ShortFileName@@YAHPEBGPEAG_K@Z; ShortFileName(ushort const *,ushort *,unsigned __int64)
0x1801a8a78  lea     ecx, [rbx-4]
0x1801a8a7b  xor     r9d, r9d; Dir
0x1801a8a7e  mov     [rsp+0B20h+ExtCount], rcx; ExtCount
0x1801a8a83  lea     rax, [rbp+0A20h+var_240]
0x1801a8a8a  mov     [rsp+0B20h+Ext], rax; Ext
0x1801a8a8f  xor     r8d, r8d; DriveCount
0x1801a8a92  mov     [rsp+0B20h+FilenameCount], rcx; FilenameCount
0x1801a8a97  lea     rax, [rbp+0A20h+var_450]
0x1801a8a9e  mov     [rsp+0B20h+Filename], rax; Filename
0x1801a8aa3  lea     rcx, [rbp+0A20h+FileName]; FullPath
0x1801a8aaa  xor     edx, edx; Drive
0x1801a8aac  mov     [rsp+0B20h+DirCount], r12; DirCount
0x1801a8ab1  call    cs:__imp__wsplitpath_s
0x1801a8ab7  lea     rcx, [rsp+0B20h+var_AD0]; this
0x1801a8abc  call    ?IsCancelled@CancellationCheck@@QEBAHXZ; CancellationCheck::IsCancelled(void)
0x1801a8ac1  test    eax, eax
0x1801a8ac3  jnz     loc_1801A8C7F
0x1801a8ac9  cmp     [rbp+0A20h+FindFileData.cFileName], 2Eh ; '.'
0x1801a8ace  movzx   eax, [rbp+0A20h+FindFileData.cFileName+2]
0x1801a8ad2  jnz     short loc_1801A8AF5
0x1801a8ad4  test    ax, ax
0x1801a8ad7  jz      loc_1801A8BBC
0x1801a8add  cmp     [rbp+0A20h+FindFileData.cFileName], 2Eh ; '.'
0x1801a8ae2  jnz     short loc_1801A8AF5
0x1801a8ae4  cmp     ax, 2Eh ; '.'
0x1801a8ae8  jnz     short loc_1801A8AF5
0x1801a8aea  cmp     [rbp+0A20h+FindFileData.cFileName+4], r12w
0x1801a8aef  jz      loc_1801A8BBC
0x1801a8af5  lea     r8, [rbp+0A20h+FileName]; unsigned __int16 *
0x1801a8afc  mov     rdx, rbx; unsigned __int64
0x1801a8aff  lea     rcx, [rbp+0A20h+var_870]; unsigned __int16 *
0x1801a8b06  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a8b0b  mov     rdx, rbx
0x1801a8b0e  lea     rcx, [rbp+0A20h+var_870]
0x1801a8b15  call    BackslashCat
0x1801a8b1a  test    eax, eax
0x1801a8b1c  jz      loc_1801A8BBC
0x1801a8b22  lea     r8, [rbp+0A20h+FindFileData.cFileName]; unsigned __int16 *
0x1801a8b26  lea     rcx, [rbp+0A20h+var_870]; unsigned __int16 *
0x1801a8b2d  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a8b32  lea     rcx, [rbp+0A20h+var_870]; unsigned __int16 *
0x1801a8b39  call    ?isdir@@YAHPEBG@Z; isdir(ushort const *)
0x1801a8b3e  test    eax, eax
0x1801a8b40  jz      short loc_1801A8B8E
0x1801a8b42  mov     rdx, rbx
0x1801a8b45  lea     rcx, [rbp+0A20h+var_870]
0x1801a8b4c  call    BackslashCat
0x1801a8b51  test    eax, eax
0x1801a8b53  jz      short loc_1801A8BBC
0x1801a8b55  lea     r8, [rbp+0A20h+var_450]; unsigned __int16 *
0x1801a8b5c  lea     rcx, [rbp+0A20h+var_870]; unsigned __int16 *
0x1801a8b63  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a8b68  lea     r8, [rbp+0A20h+var_240]; unsigned __int16 *
0x1801a8b6f  mov     rdx, rbx; unsigned __int64
0x1801a8b72  lea     rcx, [rbp+0A20h+var_870]; unsigned __int16 *
0x1801a8b79  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a8b7e  lea     rcx, [rbp+0A20h+var_870]; unsigned __int16 *
0x1801a8b85  call    ?fileexists@@YAHPEBG@Z; fileexists(ushort const *)
0x1801a8b8a  test    eax, eax
0x1801a8b8c  jz      short loc_1801A8BBC
0x1801a8b8e  lea     r8, [rbp+0A20h+var_870]; unsigned __int16 *
0x1801a8b95  mov     rdx, rbx; unsigned __int64
0x1801a8b98  mov     rcx, rsi; unsigned __int16 *
0x1801a8b9b  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a8ba0  test    r15, r15
0x1801a8ba3  jz      short loc_1801A8BD2
0x1801a8ba5  mov     rdx, rsi; unsigned __int16 *
0x1801a8ba8  mov     rcx, r15; struct _FINDFILE_CALLBACK *
0x1801a8bab  call    ?FindFileCallback@@YAHPEAU_FINDFILE_CALLBACK@@PEBG@Z; FindFileCallback(_FINDFILE_CALLBACK *,ushort const *)
0x1801a8bb0  test    eax, eax
0x1801a8bb2  jz      loc_1801A8C78
0x1801a8bb8  mov     [rsi], r12w
0x1801a8bbc  lea     rdx, [rsp+0B20h+FindFileData]; lpFindFileData
0x1801a8bc1  mov     rcx, rdi; hFindFile
0x1801a8bc4  call    cs:__imp_FindNextFileW
0x1801a8bca  test    eax, eax
0x1801a8bcc  jnz     loc_1801A8AB7
0x1801a8bd2  mov     rcx, rdi; hFindFile
0x1801a8bd5  call    cs:__imp_FindClose
0x1801a8bdb  mov     r8, r14; unsigned __int16 *
0x1801a8bde  lea     rcx, [rbp+0A20h+var_870]; unsigned __int16 *
0x1801a8be5  mov     rdx, rbx; unsigned __int64
0x1801a8be8  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a8bed  mov     rdx, rbx
0x1801a8bf0  lea     rcx, [rbp+0A20h+var_870]
0x1801a8bf7  call    BackslashCat
0x1801a8bfc  test    eax, eax
0x1801a8bfe  jz      short loc_1801A8C4B
0x1801a8c00  lea     r8, [rbp+0A20h+var_450]; unsigned __int16 *
0x1801a8c07  lea     rcx, [rbp+0A20h+var_870]; unsigned __int16 *
0x1801a8c0e  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a8c13  lea     r8, [rbp+0A20h+var_240]; unsigned __int16 *
0x1801a8c1a  mov     rdx, rbx; unsigned __int64
0x1801a8c1d  lea     rcx, [rbp+0A20h+var_870]; unsigned __int16 *
0x1801a8c24  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a8c29  lea     rcx, [rbp+0A20h+var_870]; unsigned __int16 *
0x1801a8c30  call    ?fileexists@@YAHPEBG@Z; fileexists(ushort const *)
0x1801a8c35  test    eax, eax
0x1801a8c37  jz      short loc_1801A8C4B
0x1801a8c39  lea     r8, [rbp+0A20h+var_870]; unsigned __int16 *
0x1801a8c40  mov     rdx, rbx; unsigned __int64
0x1801a8c43  mov     rcx, rsi; unsigned __int16 *
0x1801a8c46  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a8c4b  xor     eax, eax
0x1801a8c4d  mov     rcx, [rbp+0A20h+var_30]
0x1801a8c54  xor     rcx, rsp; StackCookie
0x1801a8c57  call    __security_check_cookie
0x1801a8c5c  lea     r11, [rsp+0B20h+var_20]
0x1801a8c64  mov     rbx, [r11+30h]
0x1801a8c68  mov     rsi, [r11+48h]
0x1801a8c6c  mov     rsp, r11
0x1801a8c6f  pop     r15
0x1801a8c71  pop     r14
0x1801a8c73  pop     r12
0x1801a8c75  pop     rdi
0x1801a8c76  pop     rbp
0x1801a8c77  retn
0x1801a8c78  mov     ebx, 1
0x1801a8c7d  jmp     short loc_1801A8C82
0x1801a8c7f  mov     ebx, r12d
0x1801a8c82  mov     rcx, rdi; hFindFile
0x1801a8c85  call    cs:__imp_FindClose
0x1801a8c8b  mov     eax, ebx
0x1801a8c8d  jmp     short loc_1801A8C4D
```
