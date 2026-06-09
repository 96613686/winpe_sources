# CheckDirForPdbsEx(ushort *,_GUID *,ulong,ulong,void *,_PROCESS_ENTRY *,int *,ushort *)

- ea: `0x1800186b0`
- end: `0x180018a46`
- name: `?CheckDirForPdbsEx@@YAJPEAGPEAU_GUID@@KKPEAXPEAU_PROCESS_ENTRY@@PEAH0@Z`
- size: `918`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _GUID *, unsigned int, unsigned int, void *, struct _PROCESS_ENTRY *, int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18001b03c`

## callees

- `0x1800051cc`
- `0x180009790`
- `0x180012c28`
- `0x180012e28`
- `0x180012e6c`
- `0x180012ed4`
- `0x1800186b0`
- `0x180021340`
- `0x180023244`
- `0x180027430`
- `0x180195d78`
- `0x1801aef0c`
- `0x1801af030`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800187a2`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800187a2`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180018970`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180018a3c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180018970`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180018a3c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001895f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001895f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001881c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001881c`

## pseudocode

```c
__int64 __fastcall CheckDirForPdbsEx(
        unsigned __int16 *a1,
        struct _GUID *a2,
        unsigned int a3,
        unsigned int a4,
        struct DIA *a5,
        struct _PROCESS_ENTRY *a6,
        int *a7,
        unsigned __int16 *a8)
{
  unsigned __int64 v13; // r8
  HANDLE FirstFileW; // rdi
  unsigned __int64 v15; // rdx
  unsigned int v16; // ebx
  int DirCount; // [rsp+20h] [rbp-E0h]
  struct _PROCESS_ENTRY *v18; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+58h] [rbp-A8h]
  int v20; // [rsp+5Ch] [rbp-A4h] BYREF
  int *v21; // [rsp+60h] [rbp-A0h]
  struct DIA *v22; // [rsp+68h] [rbp-98h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+70h] [rbp-90h] BYREF
  wchar_t Drive[8]; // [rsp+2C0h] [rbp+1C0h] BYREF
  wchar_t Buffer[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  wchar_t Ext[264]; // [rsp+4E0h] [rbp+3E0h] BYREF
  unsigned __int16 v27[264]; // [rsp+6F0h] [rbp+5F0h] BYREF
  wchar_t Dir[264]; // [rsp+900h] [rbp+800h] BYREF
  wchar_t Filename[264]; // [rsp+B10h] [rbp+A10h] BYREF

  v22 = a5;
  v21 = a7;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( *a1 )
  {
    v18 = a6;
    v20 = 0;
    v19 = MarkOperationStart(a6, &v20);
    if ( (unsigned int)CancellationCheck::IsCancelled((CancellationCheck *)&v18) )
      return 2147500036LL;
    _wsplitpath_s(a1, Drive, 4u, Dir, 0x101u, Filename, 0x101u, Ext, 0x101u);
    ShortNodeName(Filename, v27, v13);
    swprintf_s(Buffer, 0x105u, L"%s%s%s%s\\*", Drive, Dir, v27, Ext);
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileW = FindFirstFileW(Buffer, &FindFileData);
    if ( FirstFileW == (HANDLE)-1LL )
      return 2154627077LL;
    while ( 1 )
    {
      if ( (unsigned int)CancellationCheck::IsCancelled((CancellationCheck *)&v18) )
      {
        v16 = -2147467260;
        goto LABEL_21;
      }
      if ( FindFileData.cFileName[0] != 46
        || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
      {
        swprintf_s(Buffer, 0x105u, L"%s%s%s%s\\%s", Drive, Dir, v27, Ext, FindFileData.cFileName);
        if ( (unsigned int)isdir(Buffer) )
        {
          if ( !(unsigned int)BackslashCat(Buffer, 261) )
            goto LABEL_15;
          wcscat_s_ex(Buffer, v15, v27);
          wcscat_s_ex(Buffer, 0x105u, Ext);
        }
        else if ( !(unsigned int)extmatch(Buffer, L".pdb") )
        {
          goto LABEL_15;
        }
        if ( !(unsigned int)DiaOpenPdbEx(Buffer, a2, a3, a4, DirCount, v22, a6, v21, a8) )
        {
          wcscpy_s_ex(a1, 0x105u, Buffer);
          v16 = 0;
LABEL_21:
          FindClose(FirstFileW);
          return v16;
        }
      }
LABEL_15:
      if ( !FindNextFileW(FirstFileW, &FindFileData) )
      {
        FindClose(FirstFileW);
        swprintf_s(Buffer, 0x105u, L"%s%s%s%s\\%s%s", Drive, Dir, v27, Ext, v27, Ext);
        if ( (unsigned int)fileexists(Buffer) )
          wcscpy_s_ex(a8, 0x105u, Buffer);
        return 2154627077LL;
      }
    }
  }
  return 2154627077LL;
}

```

## disassembly

```asm
0x1800186b0  push    rbp
0x1800186b2  push    rbx
0x1800186b3  push    rsi
0x1800186b4  push    rdi
0x1800186b5  push    r12
0x1800186b7  push    r13
0x1800186b9  push    r14
0x1800186bb  push    r15
0x1800186bd  lea     rbp, [rsp-0C38h]
0x1800186c5  sub     rsp, 0D38h
0x1800186cc  mov     rax, cs:__security_cookie
0x1800186d3  xor     rax, rsp
0x1800186d6  mov     [rbp+0C70h+var_50], rax
0x1800186dd  mov     rax, [rbp+0C70h+arg_20]
0x1800186e4  mov     r12d, r8d
0x1800186e7  mov     rbx, [rbp+0C70h+arg_28]
0x1800186ee  mov     r15, rdx
0x1800186f1  mov     r14, [rbp+0C70h+arg_38]
0x1800186f8  mov     rsi, rcx
0x1800186fb  mov     [rsp+0D70h+var_D08], rax
0x180018700  lea     rcx, [rsp+0D70h+FindFileData]; void *
0x180018705  mov     rax, [rbp+0C70h+arg_30]
0x18001870c  xor     edx, edx; Val
0x18001870e  mov     r8d, 250h; Size
0x180018714  mov     [rsp+0D70h+var_D10], rax
0x180018719  mov     r13d, r9d
0x18001871c  call    memset_0
0x180018721  xor     edi, edi
0x180018723  cmp     [rsi], di
0x180018726  jz      loc_1800189F4
0x18001872c  lea     rdx, [rsp+0D70h+var_D14]
0x180018731  mov     [rsp+0D70h+var_D20], rbx
0x180018736  mov     rcx, rbx
0x180018739  mov     [rsp+58h], rdi
0x18001873e  call    MarkOperationStart
0x180018743  lea     rcx, [rsp+0D70h+var_D20]; this
0x180018748  mov     [rsp+0D70h+var_D18], eax
0x18001874c  call    ?IsCancelled@CancellationCheck@@QEBAHXZ; CancellationCheck::IsCancelled(void)
0x180018751  test    eax, eax
0x180018753  jz      short loc_18001875F
0x180018755  mov     eax, 80004004h
0x18001875a  jmp     loc_1800189F9
0x18001875f  mov     ecx, 101h
0x180018764  lea     rax, [rbp+0C70h+var_890]
0x18001876b  mov     [rsp+0D70h+ExtCount], rcx; ExtCount
0x180018770  lea     r9, [rbp+0C70h+Dir]; Dir
0x180018777  mov     [rsp+0D70h+Ext], rax; Ext
0x18001877c  lea     rdx, [rbp+0C70h+Drive]; Drive
0x180018783  mov     [rsp+0D70h+FilenameCount], rcx; FilenameCount
0x180018788  lea     rax, [rbp+0C70h+var_260]
0x18001878f  mov     [rsp+0D70h+Filename], rax; Filename
0x180018794  mov     r8d, 4; DriveCount
0x18001879a  mov     [rsp+0D70h+DirCount], rcx; DirCount
0x18001879f  mov     rcx, rsi; FullPath
0x1800187a2  call    cs:__imp__wsplitpath_s
0x1800187a8  lea     rdx, [rbp+0C70h+var_680]; unsigned __int16 *
0x1800187af  lea     rcx, [rbp+0C70h+var_260]; unsigned __int16 *
0x1800187b6  call    ?ShortNodeName@@YAHPEBGPEAG_K@Z; ShortNodeName(ushort const *,ushort *,unsigned __int64)
0x1800187bb  lea     rax, [rbp+0C70h+var_890]
0x1800187c2  mov     edx, 105h; BufferCount
0x1800187c7  mov     [rsp+0D70h+FilenameCount], rax
0x1800187cc  lea     r9, [rbp+0C70h+Drive]
0x1800187d3  lea     rax, [rbp+0C70h+var_680]
0x1800187da  mov     [rsp+0D70h+Filename], rax
0x1800187df  lea     r8, aSSSS; "%s%s%s%s\\*"
0x1800187e6  lea     rax, [rbp+0C70h+Dir]
0x1800187ed  lea     rcx, [rbp+0C70h+Buffer]; Buffer
0x1800187f4  mov     [rsp+0D70h+DirCount], rax
0x1800187f9  call    swprintf_s
0x1800187fe  xor     edx, edx; Val
0x180018800  lea     rcx, [rsp+0D70h+FindFileData]; void *
0x180018805  mov     r8d, 250h; Size
0x18001880b  call    memset_0
0x180018810  lea     rdx, [rsp+0D70h+FindFileData]; lpFindFileData
0x180018815  lea     rcx, [rbp+0C70h+Buffer]; lpFileName
0x18001881c  call    cs:__imp_FindFirstFileW
0x180018822  mov     rdi, rax
0x180018825  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180018829  jz      loc_1800189F4
0x18001882f  lea     rcx, [rsp+0D70h+var_D20]; this
0x180018834  call    ?IsCancelled@CancellationCheck@@QEBAHXZ; CancellationCheck::IsCancelled(void)
0x180018839  xor     ecx, ecx
0x18001883b  test    eax, eax
0x18001883d  jnz     loc_180018A34
0x180018843  cmp     [rbp+0C70h+FindFileData.cFileName], 2Eh ; '.'
0x180018848  movzx   eax, [rbp+0C70h+FindFileData.cFileName+2]
0x18001884c  jnz     short loc_18001886E
0x18001884e  test    ax, ax
0x180018851  jz      loc_180018957
0x180018857  cmp     [rbp+0C70h+FindFileData.cFileName], 2Eh ; '.'
0x18001885c  jnz     short loc_18001886E
0x18001885e  cmp     ax, 2Eh ; '.'
0x180018862  jnz     short loc_18001886E
0x180018864  cmp     [rbp+0C70h+FindFileData.cFileName+4], cx
0x180018868  jz      loc_180018957
0x18001886e  lea     rax, [rbp+0C70h+FindFileData.cFileName]
0x180018872  mov     edx, 105h; BufferCount
0x180018877  mov     [rsp+0D70h+Ext], rax
0x18001887c  lea     r9, [rbp+0C70h+Drive]
0x180018883  lea     rax, [rbp+0C70h+var_890]
0x18001888a  mov     [rsp+0D70h+FilenameCount], rax
0x18001888f  lea     r8, aSSSSS; "%s%s%s%s\\%s"
0x180018896  lea     rax, [rbp+0C70h+var_680]
0x18001889d  mov     [rsp+0D70h+Filename], rax
0x1800188a2  lea     rcx, [rbp+0C70h+Buffer]; Buffer
0x1800188a9  lea     rax, [rbp+0C70h+Dir]
0x1800188b0  mov     [rsp+0D70h+DirCount], rax; int
0x1800188b5  call    swprintf_s
0x1800188ba  lea     rcx, [rbp+0C70h+Buffer]; unsigned __int16 *
0x1800188c1  call    ?isdir@@YAHPEBG@Z; isdir(ushort const *)
0x1800188c6  lea     rcx, [rbp+0C70h+Buffer]; unsigned __int16 *
0x1800188cd  test    eax, eax
0x1800188cf  jz      short loc_18001890C
0x1800188d1  mov     edx, 105h
0x1800188d6  call    BackslashCat
0x1800188db  test    eax, eax
0x1800188dd  jz      short loc_180018957
0x1800188df  lea     r8, [rbp+0C70h+var_680]; unsigned __int16 *
0x1800188e6  lea     rcx, [rbp+0C70h+Buffer]; unsigned __int16 *
0x1800188ed  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1800188f2  lea     r8, [rbp+0C70h+var_890]; unsigned __int16 *
0x1800188f9  mov     edx, 105h; unsigned __int64
0x1800188fe  lea     rcx, [rbp+0C70h+Buffer]; unsigned __int16 *
0x180018905  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x18001890a  jmp     short loc_18001891C
0x18001890c  lea     rdx, aPdb_3; ".pdb"
0x180018913  call    ?extmatch@@YAHPEBG0@Z; extmatch(ushort const *,ushort const *)
0x180018918  test    eax, eax
0x18001891a  jz      short loc_180018957
0x18001891c  mov     rax, [rsp+0D70h+var_D10]
0x180018921  lea     rcx, [rbp+0C70h+Buffer]; unsigned __int16 *
0x180018928  mov     [rsp+0D70h+ExtCount], r14; unsigned __int16 *
0x18001892d  mov     r9d, r13d; unsigned int
0x180018930  mov     [rsp+0D70h+Ext], rax; int *
0x180018935  mov     r8d, r12d; unsigned int
0x180018938  mov     rax, [rsp+0D70h+var_D08]
0x18001893d  mov     rdx, r15; struct _GUID *
0x180018940  mov     [rsp+0D70h+FilenameCount], rbx; struct _PROCESS_ENTRY *
0x180018945  mov     [rsp+0D70h+Filename], rax; struct DIA *
0x18001894a  call    ?DiaOpenPdbEx@@YAJPEBGPEAU_GUID@@KKHPEAXPEAU_PROCESS_ENTRY@@PEAHPEAG@Z; DiaOpenPdbEx(ushort const *,_GUID *,ulong,ulong,int,void *,_PROCESS_ENTRY *,int *,ushort *)
0x18001894f  test    eax, eax
0x180018951  jz      loc_180018A1C
0x180018957  lea     rdx, [rsp+0D70h+FindFileData]; lpFindFileData
0x18001895c  mov     rcx, rdi; hFindFile
0x18001895f  call    cs:__imp_FindNextFileW
0x180018965  test    eax, eax
0x180018967  jnz     loc_18001882F
0x18001896d  mov     rcx, rdi; hFindFile
0x180018970  call    cs:__imp_FindClose
0x180018976  lea     rax, [rbp+0C70h+var_890]
0x18001897d  mov     ebx, 105h
0x180018982  mov     [rsp+0D70h+ExtCount], rax
0x180018987  lea     r9, [rbp+0C70h+Drive]
0x18001898e  lea     rax, [rbp+0C70h+var_680]
0x180018995  mov     edx, ebx; BufferCount
0x180018997  mov     [rsp+0D70h+Ext], rax
0x18001899c  lea     r8, aSSSSSS; "%s%s%s%s\\%s%s"
0x1800189a3  lea     rax, [rbp+0C70h+var_890]
0x1800189aa  mov     [rsp+0D70h+FilenameCount], rax
0x1800189af  lea     rcx, [rbp+0C70h+Buffer]; Buffer
0x1800189b6  lea     rax, [rbp+0C70h+var_680]
0x1800189bd  mov     [rsp+0D70h+Filename], rax
0x1800189c2  lea     rax, [rbp+0C70h+Dir]
0x1800189c9  mov     [rsp+0D70h+DirCount], rax
0x1800189ce  call    swprintf_s
0x1800189d3  lea     rcx, [rbp+0C70h+Buffer]; unsigned __int16 *
0x1800189da  call    ?fileexists@@YAHPEBG@Z; fileexists(ushort const *)
0x1800189df  test    eax, eax
0x1800189e1  jz      short loc_1800189F4
0x1800189e3  lea     r8, [rbp+0C70h+Buffer]; unsigned __int16 *
0x1800189ea  mov     edx, ebx; unsigned __int64
0x1800189ec  mov     rcx, r14; unsigned __int16 *
0x1800189ef  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1800189f4  mov     eax, 806D0005h
0x1800189f9  mov     rcx, [rbp+0C70h+var_50]
0x180018a00  xor     rcx, rsp; StackCookie
0x180018a03  call    __security_check_cookie
0x180018a08  add     rsp, 0D38h
0x180018a0f  pop     r15
0x180018a11  pop     r14
0x180018a13  pop     r13
0x180018a15  pop     r12
0x180018a17  pop     rdi
0x180018a18  pop     rsi
0x180018a19  pop     rbx
0x180018a1a  pop     rbp
0x180018a1b  retn
0x180018a1c  lea     r8, [rbp+0C70h+Buffer]; unsigned __int16 *
0x180018a23  mov     edx, 105h; unsigned __int64
0x180018a28  mov     rcx, rsi; unsigned __int16 *
0x180018a2b  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x180018a30  xor     ebx, ebx
0x180018a32  jmp     short loc_180018A39
0x180018a34  mov     ebx, 80004004h
0x180018a39  mov     rcx, rdi; hFindFile
0x180018a3c  call    cs:__imp_FindClose
0x180018a42  mov     eax, ebx
0x180018a44  jmp     short loc_1800189F9
```
