# CFileOwnerDialog::MoveSelectedFiles(HWND__ *,ushort const *)

- ea: `0x180013b8c`
- end: `0x180013d3c`
- name: `?MoveSelectedFiles@CFileOwnerDialog@@AEAAXPEAUHWND__@@PEBG@Z`
- size: `432`
- prototype: `void __fastcall(CFileOwnerDialog *__hidden this, HWND hWnd, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180013d44`

## callees

- `0x180006ec0`
- `0x180011c9c`
- `0x180011dd0`
- `0x18001270c`
- `0x180013b8c`
- `0x180014980`
- `0x180019dd0`
- `0x180019ee0`
- `0x180019fb0`
- `0x18001a708`
- `0x18001bec8`
- `0x18001bf58`

## import_xrefs

- `SHELL32!SHFileOperationW` at `0x180013ced`
- `SHELL32!SHFileOperationW` at `0x180013ced`
- `SHLWAPI!PathFindFileNameW` at `0x180013c5d`
- `SHLWAPI!PathFindFileNameW` at `0x180013c5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013d25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013d25`
- `KERNEL32!lstrlenW` at `0x180013c32`
- `KERNEL32!lstrlenW` at `0x180013c32`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CFileOwnerDialog::MoveSelectedFiles(HWND *this, HWND hWnd, const unsigned __int16 *a3)
{
  const unsigned __int16 *v6; // r8
  const unsigned __int16 *v7; // r9
  WCHAR *v8; // rbx
  const unsigned __int16 *v9; // r8
  const unsigned __int16 *v10; // r9
  LPWSTR FileNameW; // rax
  const unsigned __int16 *v12; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v13; // [rsp+20h] [rbp-E0h]
  _QWORD v14[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v15[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v16[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpString[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v18; // [rsp+80h] [rbp-80h]
  struct _SHFILEOPSTRUCTW FileOp; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v20[128]; // [rsp+C0h] [rbp-40h] BYREF

  lpString[0] = (LPCWSTR)operator new(2u);
  lpString[1] = (LPCWSTR)1;
  lpString[2] = 0;
  lpString[3] = (LPCWSTR)1024;
  v18 = 0;
  *lpString[0] = 0;
  CArray<COwnerListItemHandle>::CArray<COwnerListItemHandle>(v20);
  CFileOwnerDialog::BuildListOfSelectedFiles(this, hWnd, lpString, v20);
  v8 = (WCHAR *)lpString[0];
  if ( v18 )
  {
    CPath::CPath((CPath *)v15, a3, v6, v7, v12);
    if ( v18 == 1 && *v8 )
    {
      lstrlenW(v8);
      CPath::CPath((CPath *)v16, v8, v9, v10, v13);
      CString::CString((CString *)v14);
      v14[0] = &CPath::`vftable';
      FileNameW = PathFindFileNameW(*(LPCWSTR *)v16[1]);
      CString::operator=(v14, FileNameW);
      CString::Length((CString *)v14);
      CPath::Append((CPath *)v15, *(LPCWSTR *)v14[1]);
      v14[0] = &CPath::`vftable';
      CString::~CString((CString *)v14);
      v16[0] = &CPath::`vftable';
      CString::~CString((CString *)v16);
    }
    memset(&FileOp, 0, sizeof(FileOp));
    FileOp.hwnd = this[2];
    FileOp.wFunc = 1;
    FileOp.pFrom = v8;
    FileOp.pTo = *(PCZZWSTR *)v15[1];
    FileOp.fFlags = 8;
    SHFileOperationW(&FileOp);
    CFileOwnerDialog::RemoveListViewItems((CFileOwnerDialog *)this, hWnd);
    v15[0] = &CPath::`vftable';
    CString::~CString((CString *)v15);
  }
  CArray<COwnerListEntry *>::~CArray<COwnerListEntry *>(v20);
  if ( v8 )
    LocalFree(v8);
}

```

## disassembly

```asm
0x180013b8c  push    rbp
0x180013b8e  push    rbx
0x180013b8f  push    rsi
0x180013b90  push    r12
0x180013b92  push    r14
0x180013b94  push    r15
0x180013b96  lea     rbp, [rsp-18h]
0x180013b9b  sub     rsp, 118h
0x180013ba2  mov     r14, r8
0x180013ba5  mov     r15, rdx
0x180013ba8  mov     rsi, rcx
0x180013bab  mov     ecx, 2; uBytes
0x180013bb0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013bb5  mov     [rsp+140h+lpString], rax
0x180013bba  mov     [rsp+140h+var_D8], 1
0x180013bc3  xor     r12d, r12d
0x180013bc6  mov     [rsp+140h+var_D0], r12
0x180013bcb  mov     [rsp+140h+var_C8], 400h
0x180013bd4  mov     [rbp+40h+var_C0], r12
0x180013bd8  mov     [rax], r12w
0x180013bdc  lea     rcx, [rbp+40h+var_80]
0x180013be0  call    ??0?$CArray@VCOwnerListItemHandle@@@@QEAA@XZ; CArray<COwnerListItemHandle>::CArray<COwnerListItemHandle>(void)
0x180013be5  nop
0x180013be6  lea     r9, [rbp+40h+var_80]
0x180013bea  lea     r8, [rsp+140h+lpString]
0x180013bef  mov     rdx, r15
0x180013bf2  mov     rcx, rsi
0x180013bf5  call    ?BuildListOfSelectedFiles@CFileOwnerDialog@@AEAAXPEAUHWND__@@PEAVDblNulTermList@@PEAV?$CArray@VCOwnerListItemHandle@@@@@Z; CFileOwnerDialog::BuildListOfSelectedFiles(HWND__ *,DblNulTermList *,CArray<COwnerListItemHandle> *)
0x180013bfa  mov     rbx, [rsp+140h+lpString]
0x180013bff  cmp     [rbp+40h+var_C0], r12
0x180013c03  jbe     loc_180013D13
0x180013c09  mov     rdx, r14; unsigned __int16 *
0x180013c0c  lea     rcx, [rsp+140h+var_100]; this
0x180013c11  call    ??0CPath@@QEAA@PEBG000@Z; CPath::CPath(ushort const *,ushort const *,ushort const *,ushort const *)
0x180013c16  nop
0x180013c17  lea     r14, ??_7CPath@@6B@; const CPath::`vftable'
0x180013c1e  cmp     [rbp+40h+var_C0], 1
0x180013c23  jnz     loc_180013CAC
0x180013c29  cmp     [rbx], r12w
0x180013c2d  jz      short loc_180013CAC
0x180013c2f  mov     rcx, rbx; lpString
0x180013c32  call    cs:__imp_lstrlenW
0x180013c38  mov     rdx, rbx; unsigned __int16 *
0x180013c3b  lea     rcx, [rsp+140h+var_F0]; this
0x180013c40  call    ??0CPath@@QEAA@PEBG000@Z; CPath::CPath(ushort const *,ushort const *,ushort const *,ushort const *)
0x180013c45  nop
0x180013c46  lea     rcx, [rsp+140h+var_110]; this
0x180013c4b  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x180013c50  mov     [rsp+140h+var_110], r14
0x180013c55  mov     rcx, [rsp+140h+var_E8]
0x180013c5a  mov     rcx, [rcx]; pszPath
0x180013c5d  call    cs:__imp_PathFindFileNameW
0x180013c63  mov     rdx, rax
0x180013c66  lea     rcx, [rsp+140h+var_110]
0x180013c6b  call    ??4CString@@QEAAAEAV0@PEBG@Z; CString::operator=(ushort const *)
0x180013c70  lea     rcx, [rsp+140h+var_110]; this
0x180013c75  call    ?Length@CString@@QEBAHXZ; CString::Length(void)
0x180013c7a  mov     rdx, [rsp+140h+var_108]
0x180013c7f  mov     rdx, [rdx]; pszMore
0x180013c82  lea     rcx, [rsp+140h+var_100]; this
0x180013c87  call    ?Append@CPath@@QEAA_NPEBG@Z; CPath::Append(ushort const *)
0x180013c8c  nop
0x180013c8d  mov     [rsp+140h+var_110], r14
0x180013c92  lea     rcx, [rsp+140h+var_110]; this
0x180013c97  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180013c9c  nop
0x180013c9d  mov     [rsp+140h+var_F0], r14
0x180013ca2  lea     rcx, [rsp+140h+var_F0]; this
0x180013ca7  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180013cac  xorps   xmm0, xmm0
0x180013caf  xor     eax, eax
0x180013cb1  movups  xmmword ptr [rbp+40h+FileOp.hwnd], xmm0
0x180013cb5  movups  xmmword ptr [rbp+40h+FileOp.pFrom], xmm0
0x180013cb9  movups  xmmword ptr [rbp+40h+FileOp.fFlags], xmm0
0x180013cbd  mov     [rbp+40h+FileOp.lpszProgressTitle], rax
0x180013cc1  mov     rax, [rsi+10h]
0x180013cc5  mov     [rbp+40h+FileOp.hwnd], rax
0x180013cc9  mov     [rbp+40h+FileOp.wFunc], 1
0x180013cd0  mov     [rbp+40h+FileOp.pFrom], rbx
0x180013cd4  mov     rax, [rsp+140h+var_F8]
0x180013cd9  mov     rcx, [rax]
0x180013cdc  mov     [rbp+40h+FileOp.pTo], rcx
0x180013ce0  mov     eax, 8
0x180013ce5  mov     [rbp+40h+FileOp.fFlags], ax
0x180013ce9  lea     rcx, [rbp+40h+FileOp]; lpFileOp
0x180013ced  call    cs:__imp_SHFileOperationW
0x180013cf3  lea     r8, [rbp+40h+var_80]
0x180013cf7  mov     rdx, r15; hWnd
0x180013cfa  mov     rcx, rsi; this
0x180013cfd  call    ?RemoveListViewItems@CFileOwnerDialog@@AEAAXPEAUHWND__@@AEBV?$CArray@VCOwnerListItemHandle@@@@@Z; CFileOwnerDialog::RemoveListViewItems(HWND__ *,CArray<COwnerListItemHandle> const &)
0x180013d02  nop
0x180013d03  mov     [rsp+140h+var_100], r14
0x180013d08  lea     rcx, [rsp+140h+var_100]; this
0x180013d0d  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180013d12  nop
0x180013d13  lea     rcx, [rbp+40h+var_80]
0x180013d17  call    ??1?$CArray@PEAVCOwnerListEntry@@@@UEAA@XZ; CArray<COwnerListEntry *>::~CArray<COwnerListEntry *>(void)
0x180013d1c  nop
0x180013d1d  test    rbx, rbx
0x180013d20  jz      short loc_180013D2B
0x180013d22  mov     rcx, rbx; hMem
0x180013d25  call    cs:__imp_LocalFree
0x180013d2b  add     rsp, 118h
0x180013d32  pop     r15
0x180013d34  pop     r14
0x180013d36  pop     r12
0x180013d38  pop     rsi
0x180013d39  pop     rbx
0x180013d3a  pop     rbp
0x180013d3b  retn
```
