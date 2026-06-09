# CheckDirForDbgs(_PROCESS_ENTRY *,ushort *,ushort *,ulong,_FINDDBG_CALLBACK *)

- ea: `0x1800130f4`
- end: `0x1800133d2`
- name: `?CheckDirForDbgs@@YAPEAXPEAU_PROCESS_ENTRY@@PEAG1KPEAU_FINDDBG_CALLBACK@@@Z`
- size: `734`
- prototype: `void *__usercall@<rax>(struct _PROCESS_ENTRY *@<rcx>, unsigned __int16 *@<rdx>, unsigned __int16 *@<r8>, unsigned int@<r9d>, struct _FINDDBG_CALLBACK *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800120f0`

## callees

- `0x180009790`
- `0x18000e378`
- `0x180012e28`
- `0x180012e6c`
- `0x180012ed4`
- `0x1800130f4`
- `0x1800181c8`
- `0x180027430`
- `0x1801aef0c`
- `0x1801af030`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800132e3`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800132e3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001337c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800133c7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001337c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800133c7`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001336b`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18001336b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180013203`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180013203`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180013294`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180013294`

## pseudocode

```c
__int64 __fastcall CheckDirForDbgs(
        struct _PROCESS_ENTRY *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        __int64 a4,
        struct _FINDDBG_CALLBACK *a5)
{
  unsigned __int64 v8; // r8
  unsigned __int64 v9; // rdx
  HANDLE FirstFileW; // rbx
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rdi
  struct _PROCESS_ENTRY *v16; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+58h] [rbp-A8h]
  int v18; // [rsp+5Ch] [rbp-A4h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v20[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wchar_t Filename; // [rsp+4C0h] [rbp+3C0h] BYREF
  _BYTE v22[526]; // [rsp+4C2h] [rbp+3C2h] BYREF
  WCHAR FileName[264]; // [rsp+6D0h] [rbp+5D0h] BYREF
  wchar_t Ext[264]; // [rsp+8E0h] [rbp+7E0h] BYREF

  Filename = 0;
  memset_0(v22, 0, 0x200u);
  memset_0(Ext, 0, 0x202u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v16 = a1;
  v18 = 0;
  v17 = MarkOperationStart(a1, &v18);
  if ( (unsigned int)CancellationCheck::IsCancelled((CancellationCheck *)&v16) )
    return -1;
  ShortFileName(a2, FileName, v8);
  if ( !(unsigned int)BackslashCat(FileName, 261) )
    return 0;
  wcscat_s_ex(FileName, v9, L"*");
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
    return -1;
  while ( 1 )
  {
    if ( (unsigned int)CancellationCheck::IsCancelled((CancellationCheck *)&v16) )
    {
LABEL_19:
      FindClose(FirstFileW);
      return -1;
    }
    if ( FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
    {
      goto LABEL_18;
    }
    wcscpy_s_ex(v20, 0x105u, a2);
    if ( !(unsigned int)BackslashCat(v20, 261) )
      goto LABEL_18;
    wcscat_s_ex(v20, v12, FindFileData.cFileName);
    if ( (GetFileAttributesW(v20) & 0x10) != 0 )
      break;
    if ( (unsigned int)extmatch(v20, L".dbg") )
      goto LABEL_17;
LABEL_18:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_19;
  }
  if ( !Filename )
    _wsplitpath_s(a2, 0, 0, 0, 0, &Filename, 0x101u, Ext, 0x101u);
  if ( !(unsigned int)BackslashCat(v20, 261) )
    goto LABEL_18;
  wcscat_s_ex(v20, v13, &Filename);
  wcscat_s_ex(v20, 0x105u, Ext);
LABEL_17:
  v15 = OpenDbg(a1, v20, a3, v14, a5);
  if ( v15 == -1 )
    goto LABEL_18;
  wcscpy_s_ex(a2, 0x105u, v20);
  FindClose(FirstFileW);
  return v15;
}

```

## disassembly

```asm
0x1800130f4  mov     [rsp-8+arg_18], rbx
0x1800130f9  push    rbp
0x1800130fa  push    rsi
0x1800130fb  push    rdi
0x1800130fc  push    r12
0x1800130fe  push    r13
0x180013100  push    r14
0x180013102  push    r15
0x180013104  lea     rbp, [rsp-0A00h]
0x18001310c  sub     rsp, 0B00h
0x180013113  mov     rax, cs:__security_cookie
0x18001311a  xor     rax, rsp
0x18001311d  mov     [rbp+0A30h+var_40], rax
0x180013124  mov     r12, [rbp+0A30h+arg_20]
0x18001312b  mov     r15, r8
0x18001312e  mov     rsi, rdx
0x180013131  mov     r14, rcx
0x180013134  xor     r13d, r13d
0x180013137  lea     rcx, [rbp+0A30h+var_66E]; void *
0x18001313e  xor     edx, edx; Val
0x180013140  mov     [rbp+0A30h+var_670], r13w
0x180013148  mov     r8d, 200h; Size
0x18001314e  call    memset_0
0x180013153  xor     edx, edx; Val
0x180013155  lea     rcx, [rbp+0A30h+var_250]; void *
0x18001315c  mov     r8d, 202h; Size
0x180013162  call    memset_0
0x180013167  mov     ebx, 250h
0x18001316c  lea     rcx, [rsp+0B30h+FindFileData]; void *
0x180013171  mov     r8d, ebx; Size
0x180013174  xor     edx, edx; Val
0x180013176  call    memset_0
0x18001317b  lea     rdx, [rsp+0B30h+var_AD4]
0x180013180  mov     [rsp+0B30h+var_AE0], r14
0x180013185  mov     rcx, r14
0x180013188  mov     [rsp+58h], r13
0x18001318d  call    MarkOperationStart
0x180013192  lea     rcx, [rsp+0B30h+var_AE0]; this
0x180013197  mov     [rsp+0B30h+var_AD8], eax
0x18001319b  call    ?IsCancelled@CancellationCheck@@QEBAHXZ; CancellationCheck::IsCancelled(void)
0x1800131a0  test    eax, eax
0x1800131a2  jnz     loc_180013382
0x1800131a8  lea     rdx, [rbp+0A30h+FileName]; unsigned __int16 *
0x1800131af  mov     rcx, rsi; unsigned __int16 *
0x1800131b2  call    ?ShortFileName@@YAHPEBGPEAG_K@Z; ShortFileName(ushort const *,ushort *,unsigned __int64)
0x1800131b7  mov     edi, 105h
0x1800131bc  lea     rcx, [rbp+0A30h+FileName]
0x1800131c3  mov     edx, edi
0x1800131c5  call    BackslashCat
0x1800131ca  test    eax, eax
0x1800131cc  jnz     short loc_1800131D5
0x1800131ce  xor     eax, eax
0x1800131d0  jmp     loc_180013386
0x1800131d5  lea     r8, asc_18024F6FC; "*"
0x1800131dc  lea     rcx, [rbp+0A30h+FileName]; unsigned __int16 *
0x1800131e3  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1800131e8  mov     r8, rbx; Size
0x1800131eb  lea     rcx, [rsp+0B30h+FindFileData]; void *
0x1800131f0  xor     edx, edx; Val
0x1800131f2  call    memset_0
0x1800131f7  lea     rdx, [rsp+0B30h+FindFileData]; lpFindFileData
0x1800131fc  lea     rcx, [rbp+0A30h+FileName]; lpFileName
0x180013203  call    cs:__imp_FindFirstFileW
0x180013209  mov     rbx, rax
0x18001320c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013210  jz      loc_180013382
0x180013216  lea     rcx, [rsp+0B30h+var_AE0]; this
0x18001321b  call    ?IsCancelled@CancellationCheck@@QEBAHXZ; CancellationCheck::IsCancelled(void)
0x180013220  test    eax, eax
0x180013222  jnz     loc_180013379
0x180013228  cmp     [rbp+0A30h+FindFileData.cFileName], 2Eh ; '.'
0x18001322d  movzx   eax, [rbp+0A30h+FindFileData.cFileName+2]
0x180013231  jnz     short loc_180013254
0x180013233  test    ax, ax
0x180013236  jz      loc_180013363
0x18001323c  cmp     [rbp+0A30h+FindFileData.cFileName], 2Eh ; '.'
0x180013241  jnz     short loc_180013254
0x180013243  cmp     ax, 2Eh ; '.'
0x180013247  jnz     short loc_180013254
0x180013249  cmp     [rbp+0A30h+FindFileData.cFileName+4], r13w
0x18001324e  jz      loc_180013363
0x180013254  mov     r8, rsi; unsigned __int16 *
0x180013257  lea     rcx, [rbp+0A30h+var_880]; unsigned __int16 *
0x18001325e  mov     rdx, rdi; unsigned __int64
0x180013261  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x180013266  mov     rdx, rdi
0x180013269  lea     rcx, [rbp+0A30h+var_880]
0x180013270  call    BackslashCat
0x180013275  test    eax, eax
0x180013277  jz      loc_180013363
0x18001327d  lea     r8, [rbp+0A30h+FindFileData.cFileName]; unsigned __int16 *
0x180013281  lea     rcx, [rbp+0A30h+var_880]; unsigned __int16 *
0x180013288  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x18001328d  lea     rcx, [rbp+0A30h+var_880]; lpFileName
0x180013294  call    cs:__imp_GetFileAttributesW
0x18001329a  test    al, 10h
0x18001329c  jz      loc_180013327
0x1800132a2  cmp     [rbp+0A30h+var_670], r13w
0x1800132aa  jnz     short loc_1800132E9
0x1800132ac  mov     ecx, 101h
0x1800132b1  lea     rax, [rbp+0A30h+var_250]
0x1800132b8  mov     [rsp+0B30h+ExtCount], rcx; ExtCount
0x1800132bd  xor     r9d, r9d; Dir
0x1800132c0  mov     [rsp+0B30h+Ext], rax; Ext
0x1800132c5  xor     r8d, r8d; DriveCount
0x1800132c8  mov     [rsp+0B30h+FilenameCount], rcx; FilenameCount
0x1800132cd  lea     rax, [rbp+0A30h+var_670]
0x1800132d4  mov     [rsp+0B30h+Filename], rax; Filename
0x1800132d9  xor     edx, edx; Drive
0x1800132db  mov     rcx, rsi; FullPath
0x1800132de  mov     [rsp+0B30h+DirCount], r13; DirCount
0x1800132e3  call    cs:__imp__wsplitpath_s
0x1800132e9  mov     rdx, rdi
0x1800132ec  lea     rcx, [rbp+0A30h+var_880]
0x1800132f3  call    BackslashCat
0x1800132f8  test    eax, eax
0x1800132fa  jz      short loc_180013363
0x1800132fc  lea     r8, [rbp+0A30h+var_670]; unsigned __int16 *
0x180013303  lea     rcx, [rbp+0A30h+var_880]; unsigned __int16 *
0x18001330a  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x18001330f  lea     r8, [rbp+0A30h+var_250]; unsigned __int16 *
0x180013316  mov     rdx, rdi; unsigned __int64
0x180013319  lea     rcx, [rbp+0A30h+var_880]; unsigned __int16 *
0x180013320  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x180013325  jmp     short loc_18001333E
0x180013327  lea     rdx, aDbg_0; ".dbg"
0x18001332e  lea     rcx, [rbp+0A30h+var_880]; unsigned __int16 *
0x180013335  call    ?extmatch@@YAHPEBG0@Z; extmatch(ushort const *,ushort const *)
0x18001333a  test    eax, eax
0x18001333c  jz      short loc_180013363
0x18001333e  mov     r8, r15; unsigned __int16 *
0x180013341  mov     [rsp+0B30h+DirCount], r12; struct _FINDDBG_CALLBACK *
0x180013346  lea     rdx, [rbp+0A30h+var_880]; unsigned __int16 *
0x18001334d  mov     rcx, r14; struct _PROCESS_ENTRY *
0x180013350  call    ?OpenDbg@@YAPEAXPEAU_PROCESS_ENTRY@@PEBGPEAGKPEAU_FINDDBG_CALLBACK@@@Z; OpenDbg(_PROCESS_ENTRY *,ushort const *,ushort *,ulong,_FINDDBG_CALLBACK *)
0x180013355  mov     rdi, rax
0x180013358  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001335c  jnz     short loc_1800133B0
0x18001335e  mov     edi, 105h
0x180013363  lea     rdx, [rsp+0B30h+FindFileData]; lpFindFileData
0x180013368  mov     rcx, rbx; hFindFile
0x18001336b  call    cs:__imp_FindNextFileW
0x180013371  test    eax, eax
0x180013373  jnz     loc_180013216
0x180013379  mov     rcx, rbx; hFindFile
0x18001337c  call    cs:__imp_FindClose
0x180013382  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013386  mov     rcx, [rbp+0A30h+var_40]
0x18001338d  xor     rcx, rsp; StackCookie
0x180013390  call    __security_check_cookie
0x180013395  mov     rbx, [rsp+0B30h+arg_18]
0x18001339d  add     rsp, 0B00h
0x1800133a4  pop     r15
0x1800133a6  pop     r14
0x1800133a8  pop     r13
0x1800133aa  pop     r12
0x1800133ac  pop     rdi
0x1800133ad  pop     rsi
0x1800133ae  pop     rbp
0x1800133af  retn
0x1800133b0  lea     r8, [rbp+0A30h+var_880]; unsigned __int16 *
0x1800133b7  mov     edx, 105h; unsigned __int64
0x1800133bc  mov     rcx, rsi; unsigned __int16 *
0x1800133bf  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1800133c4  mov     rcx, rbx; hFindFile
0x1800133c7  call    cs:__imp_FindClose
0x1800133cd  mov     rax, rdi
0x1800133d0  jmp     short loc_180013386
```
