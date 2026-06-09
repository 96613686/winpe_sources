# CFileOwnerDialog::DeleteSelectedFiles(HWND__ *)

- ea: `0x1800130ac`
- end: `0x180013194`
- name: `?DeleteSelectedFiles@CFileOwnerDialog@@AEAAXPEAUHWND__@@@Z`
- size: `232`
- prototype: `void __fastcall(CFileOwnerDialog *__hidden this, HWND hWnd)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180013d44`
- `0x180014490`

## callees

- `0x180006ec0`
- `0x180011c9c`
- `0x180011dd0`
- `0x18001270c`
- `0x1800130ac`
- `0x180014980`

## import_xrefs

- `SHELL32!SHFileOperationW` at `0x18001315a`
- `SHELL32!SHFileOperationW` at `0x18001315a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013182`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013182`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CFileOwnerDialog::DeleteSelectedFiles(HWND *this, HWND hWnd)
{
  HLOCAL v4; // rbx
  HLOCAL hMem[4]; // [rsp+20h] [rbp-79h] BYREF
  __int64 v6; // [rsp+40h] [rbp-59h]
  _SHFILEOPSTRUCTW FileOp; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v8[112]; // [rsp+80h] [rbp-19h] BYREF

  hMem[0] = operator new(2u);
  hMem[1] = (HLOCAL)1;
  hMem[2] = 0;
  hMem[3] = (HLOCAL)1024;
  v6 = 0;
  *(_WORD *)hMem[0] = 0;
  CArray<COwnerListItemHandle>::CArray<COwnerListItemHandle>(v8);
  CFileOwnerDialog::BuildListOfSelectedFiles(this, hWnd, hMem, v8);
  v4 = hMem[0];
  if ( v6 )
  {
    memset(&FileOp, 0, sizeof(FileOp));
    FileOp.hwnd = this[2];
    FileOp.wFunc = 3;
    FileOp.pFrom = (PCZZWSTR)hMem[0];
    FileOp.pTo = 0;
    FileOp.fFlags = 0;
    SHFileOperationW(&FileOp);
    CFileOwnerDialog::RemoveListViewItems(this, hWnd, (__int64)v8);
  }
  CArray<COwnerListEntry *>::~CArray<COwnerListEntry *>((__int64)v8);
  if ( v4 )
    LocalFree(v4);
}

```

## disassembly

```asm
0x1800130ac  push    rbp
0x1800130ae  push    rbx
0x1800130af  push    rsi
0x1800130b0  push    rdi
0x1800130b1  lea     rbp, [rsp-3Fh]
0x1800130b6  sub     rsp, 0D8h
0x1800130bd  mov     rsi, rdx
0x1800130c0  mov     rdi, rcx
0x1800130c3  mov     ecx, 2; uBytes
0x1800130c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800130cd  mov     [rbp+57h+hMem], rax
0x1800130d1  mov     [rbp+57h+var_C8], 1
0x1800130d9  mov     [rbp+57h+var_C0], 0
0x1800130e1  mov     [rbp+57h+var_B8], 400h
0x1800130e9  mov     [rbp+57h+var_B0], 0
0x1800130f1  xor     r8d, r8d
0x1800130f4  mov     [rax], r8w
0x1800130f8  lea     rcx, [rbp+57h+var_70]
0x1800130fc  call    ??0?$CArray@VCOwnerListItemHandle@@@@QEAA@XZ; CArray<COwnerListItemHandle>::CArray<COwnerListItemHandle>(void)
0x180013101  nop
0x180013102  lea     r9, [rbp+57h+var_70]
0x180013106  lea     r8, [rbp+57h+hMem]
0x18001310a  mov     rdx, rsi
0x18001310d  mov     rcx, rdi
0x180013110  call    ?BuildListOfSelectedFiles@CFileOwnerDialog@@AEAAXPEAUHWND__@@PEAVDblNulTermList@@PEAV?$CArray@VCOwnerListItemHandle@@@@@Z; CFileOwnerDialog::BuildListOfSelectedFiles(HWND__ *,DblNulTermList *,CArray<COwnerListItemHandle> *)
0x180013115  mov     rbx, [rbp+57h+hMem]
0x180013119  cmp     [rbp+57h+var_B0], 0
0x18001311e  jbe     short loc_180013170
0x180013120  xorps   xmm0, xmm0
0x180013123  xor     eax, eax
0x180013125  movups  xmmword ptr [rbp+57h+FileOp.hwnd], xmm0
0x180013129  movups  xmmword ptr [rbp+57h+FileOp.pFrom], xmm0
0x18001312d  movups  xmmword ptr [rbp+57h+FileOp.fFlags], xmm0
0x180013131  mov     [rbp+57h+FileOp.lpszProgressTitle], rax
0x180013135  mov     rax, [rdi+10h]
0x180013139  mov     [rbp+57h+FileOp.hwnd], rax
0x18001313d  mov     [rbp+57h+FileOp.wFunc], 3
0x180013144  mov     [rbp+57h+FileOp.pFrom], rbx
0x180013148  mov     [rbp+57h+FileOp.pTo], 0
0x180013150  xor     eax, eax
0x180013152  mov     [rbp+57h+FileOp.fFlags], ax
0x180013156  lea     rcx, [rbp+57h+FileOp]; lpFileOp
0x18001315a  call    cs:__imp_SHFileOperationW
0x180013160  lea     r8, [rbp+57h+var_70]
0x180013164  mov     rdx, rsi; hWnd
0x180013167  mov     rcx, rdi; this
0x18001316a  call    ?RemoveListViewItems@CFileOwnerDialog@@AEAAXPEAUHWND__@@AEBV?$CArray@VCOwnerListItemHandle@@@@@Z; CFileOwnerDialog::RemoveListViewItems(HWND__ *,CArray<COwnerListItemHandle> const &)
0x18001316f  nop
0x180013170  lea     rcx, [rbp+57h+var_70]
0x180013174  call    ??1?$CArray@PEAVCOwnerListEntry@@@@UEAA@XZ; CArray<COwnerListEntry *>::~CArray<COwnerListEntry *>(void)
0x180013179  nop
0x18001317a  test    rbx, rbx
0x18001317d  jz      short loc_180013188
0x18001317f  mov     rcx, rbx; hMem
0x180013182  call    cs:__imp_LocalFree
0x180013188  add     rsp, 0D8h
0x18001318f  pop     rdi
0x180013190  pop     rsi
0x180013191  pop     rbx
0x180013192  pop     rbp
0x180013193  retn
```
