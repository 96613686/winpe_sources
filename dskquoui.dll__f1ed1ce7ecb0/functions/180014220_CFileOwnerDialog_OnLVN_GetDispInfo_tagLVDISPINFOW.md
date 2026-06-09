# CFileOwnerDialog::OnLVN_GetDispInfo(tagLVDISPINFOW *)

- ea: `0x180014220`
- end: `0x180014489`
- name: `?OnLVN_GetDispInfo@CFileOwnerDialog@@AEAAXPEAUtagLVDISPINFOW@@@Z`
- size: `617`
- prototype: `void __fastcall(CFileOwnerDialog *__hidden this, struct tagLVDISPINFOW *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180014490`

## callees

- `0x18000199c`
- `0x180001bcc`
- `0x180001c34`
- `0x180011f58`
- `0x180012064`
- `0x180014220`
- `0x180019dd0`
- `0x180019ee0`
- `0x180019f38`
- `0x180019fb0`
- `0x18001a468`
- `0x18001a708`
- `0x18001bfc8`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180014352`
- `SHLWAPI!PathFindFileNameW` at `0x180014352`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CFileOwnerDialog::OnLVN_GetDispInfo(HINSTANCE *this, struct tagLVDISPINFOW *a2)
{
  __int64 v4; // rbx
  LPARAM v5; // r14
  LPARAM v6; // rsi
  int iSubItem; // r8d
  int v8; // r8d
  __int64 v9; // rax
  LPWSTR *v10; // rax
  __int64 v11; // rax
  CPath *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  LPWSTR FileNameW; // rax
  __int64 v16; // rax
  char v17; // bl
  _QWORD v18[3]; // [rsp+20h] [rbp-30h] BYREF
  _QWORD v19[3]; // [rsp+38h] [rbp-18h] BYREF

  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_180028670 > *(_DWORD *)(v4 + 4) )
  {
    Init_thread_header(&dword_180028670);
    if ( dword_180028670 == -1 )
    {
      CString::CString((CString *)&qword_180028678);
      qword_180028678 = &CPath::`vftable';
      atexit(CFileOwnerDialog::OnLVN_GetDispInfo_::_2_::_dynamic_atexit_destructor_for__strPath__);
      Init_thread_footer(&dword_180028670);
    }
  }
  if ( dword_180028688 > *(_DWORD *)(v4 + 4) )
  {
    Init_thread_header(&dword_180028688);
    if ( dword_180028688 == -1 )
    {
      CString::CString((CString *)&qword_180028690);
      atexit(CFileOwnerDialog::OnLVN_GetDispInfo_::_2_::_dynamic_atexit_destructor_for__strOwner__);
      Init_thread_footer(&dword_180028688);
    }
  }
  if ( (a2->item.mask & 1) != 0 )
  {
    v5 = a2->item.lParam & 0x3FF;
    v6 = a2->item.lParam >> 10;
    iSubItem = a2->item.iSubItem;
    if ( iSubItem )
    {
      v8 = iSubItem - 1;
      if ( !v8 )
      {
        v11 = CArray<COwnerListEntry *>::operator[](this + 10, (unsigned int)v5);
        v12 = (CPath *)CArray<COwnerListFile>::operator[](v11 + 24, v18, (unsigned int)v6);
        CPath::GetPath(v12, (void ***)&qword_180028678);
        v18[0] = &CPath::`vftable';
        CString::~CString((CString *)v18);
        v10 = (LPWSTR *)qword_180028680;
        goto LABEL_9;
      }
      if ( v8 == 1 )
      {
        v9 = CArray<COwnerListEntry *>::operator[](this + 10, (unsigned int)v5);
        CString::operator=(&qword_180028690, v9 + 8);
        v10 = (LPWSTR *)qword_180028698;
LABEL_9:
        a2->item.pszText = *v10;
      }
    }
    else
    {
      CString::CString((CString *)v18);
      v18[0] = &CPath::`vftable';
      v13 = CArray<COwnerListEntry *>::operator[](this + 10, (unsigned int)v5);
      v14 = CArray<COwnerListFile>::operator[](v13 + 24, v19, (unsigned int)v6);
      FileNameW = PathFindFileNameW(**(LPCWSTR **)(v14 + 8));
      CString::operator=(v18, FileNameW);
      CString::Length((CString *)v18);
      v19[0] = &CPath::`vftable';
      CString::~CString((CString *)v19);
      v16 = CArray<COwnerListEntry *>::operator[](this + 10, (unsigned int)v5);
      v17 = *(_BYTE *)(CArray<COwnerListFile>::operator[](v16 + 24, v19, (unsigned int)v6) + 16);
      v19[0] = &CPath::`vftable';
      CString::~CString((CString *)v19);
      if ( v17 )
        CString::Format((CString *)&qword_180028678, *this, 0x9EC0u, *(_QWORD *)v18[1]);
      else
        CString::operator=(&qword_180028678, v18);
      a2->item.pszText = *(LPWSTR *)qword_180028680;
      v18[0] = &CPath::`vftable';
      CString::~CString((CString *)v18);
    }
  }
}

```

## disassembly

```asm
0x180014220  push    rbp
0x180014222  push    rbx
0x180014223  push    rsi
0x180014224  push    rdi
0x180014225  push    r13
0x180014227  push    r14
0x180014229  push    r15
0x18001422b  mov     rbp, rsp
0x18001422e  sub     rsp, 50h
0x180014232  mov     rdi, rdx
0x180014235  mov     r15, rcx
0x180014238  mov     r8d, cs:_tls_index
0x18001423f  mov     rax, gs:58h
0x180014248  mov     esi, 4
0x18001424d  mov     rbx, [rax+r8*8]
0x180014251  lea     r13, ??_7CPath@@6B@; const CPath::`vftable'
0x180014258  mov     eax, [rbx+rsi]
0x18001425b  cmp     cs:dword_180028670, eax
0x180014261  jg      loc_18001443F
0x180014267  mov     eax, [rbx+rsi]
0x18001426a  cmp     cs:dword_180028688, eax
0x180014270  jg      loc_1800143FC
0x180014276  test    byte ptr [rdi+18h], 1
0x18001427a  jz      loc_1800143ED
0x180014280  mov     rsi, [rdi+40h]
0x180014284  mov     r14d, esi
0x180014287  and     r14d, 3FFh
0x18001428e  sar     rsi, 0Ah
0x180014292  mov     r8d, [rdi+20h]
0x180014296  test    r8d, r8d
0x180014299  jz      loc_180014321
0x18001429f  sub     r8d, 1
0x1800142a3  jz      short loc_1800142D4
0x1800142a5  cmp     r8d, 1
0x1800142a9  jnz     loc_1800143ED
0x1800142af  lea     rcx, [r15+50h]
0x1800142b3  mov     edx, r14d
0x1800142b6  call    ??A?$CArray@PEAVCOwnerListEntry@@@@QEBAPEAVCOwnerListEntry@@H@Z; CArray<COwnerListEntry *>::operator[](int)
0x1800142bb  lea     rdx, [rax+8]
0x1800142bf  lea     rcx, qword_180028690
0x1800142c6  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x1800142cb  mov     rax, cs:qword_180028698
0x1800142d2  jmp     short loc_180014315
0x1800142d4  lea     rcx, [r15+50h]
0x1800142d8  mov     edx, r14d
0x1800142db  call    ??A?$CArray@PEAVCOwnerListEntry@@@@QEBAPEAVCOwnerListEntry@@H@Z; CArray<COwnerListEntry *>::operator[](int)
0x1800142e0  mov     r8d, esi
0x1800142e3  lea     rcx, [rax+18h]
0x1800142e7  lea     rdx, [rbp+var_30]
0x1800142eb  call    ??A?$CArray@VCOwnerListFile@@@@QEBA?AVCOwnerListFile@@H@Z; CArray<COwnerListFile>::operator[](int)
0x1800142f0  nop
0x1800142f1  lea     rdx, qword_180028678; struct CPath *
0x1800142f8  mov     rcx, rax; this
0x1800142fb  call    ?GetPath@CPath@@QEBA_NPEAV1@@Z; CPath::GetPath(CPath *)
0x180014300  nop
0x180014301  mov     [rbp+var_30], r13
0x180014305  lea     rcx, [rbp+var_30]; this
0x180014309  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x18001430e  mov     rax, cs:qword_180028680
0x180014315  mov     rcx, [rax]
0x180014318  mov     [rdi+30h], rcx
0x18001431c  jmp     loc_1800143ED
0x180014321  lea     rcx, [rbp+var_30]; this
0x180014325  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x18001432a  mov     [rbp+var_30], r13
0x18001432e  mov     edx, r14d
0x180014331  lea     rcx, [r15+50h]
0x180014335  call    ??A?$CArray@PEAVCOwnerListEntry@@@@QEBAPEAVCOwnerListEntry@@H@Z; CArray<COwnerListEntry *>::operator[](int)
0x18001433a  lea     rcx, [rax+18h]
0x18001433e  mov     r8d, esi
0x180014341  lea     rdx, [rbp+var_18]
0x180014345  call    ??A?$CArray@VCOwnerListFile@@@@QEBA?AVCOwnerListFile@@H@Z; CArray<COwnerListFile>::operator[](int)
0x18001434a  nop
0x18001434b  mov     rcx, [rax+8]
0x18001434f  mov     rcx, [rcx]; pszPath
0x180014352  call    cs:__imp_PathFindFileNameW
0x180014358  mov     rdx, rax
0x18001435b  lea     rcx, [rbp+var_30]
0x18001435f  call    ??4CString@@QEAAAEAV0@PEBG@Z; CString::operator=(ushort const *)
0x180014364  lea     rcx, [rbp+var_30]; this
0x180014368  call    ?Length@CString@@QEBAHXZ; CString::Length(void)
0x18001436d  nop
0x18001436e  mov     [rbp+var_18], r13
0x180014372  lea     rcx, [rbp+var_18]; this
0x180014376  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x18001437b  mov     edx, r14d
0x18001437e  lea     rcx, [r15+50h]
0x180014382  call    ??A?$CArray@PEAVCOwnerListEntry@@@@QEBAPEAVCOwnerListEntry@@H@Z; CArray<COwnerListEntry *>::operator[](int)
0x180014387  lea     rcx, [rax+18h]
0x18001438b  mov     r8d, esi
0x18001438e  lea     rdx, [rbp+var_18]
0x180014392  call    ??A?$CArray@VCOwnerListFile@@@@QEBA?AVCOwnerListFile@@H@Z; CArray<COwnerListFile>::operator[](int)
0x180014397  mov     bl, [rax+10h]
0x18001439a  mov     [rbp+var_18], r13
0x18001439e  lea     rcx, [rbp+var_18]; this
0x1800143a2  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x1800143a7  lea     rcx, qword_180028678; this
0x1800143ae  test    bl, bl
0x1800143b0  jz      short loc_1800143C9
0x1800143b2  mov     r9, [rbp+var_28]
0x1800143b6  mov     r9, [r9]
0x1800143b9  mov     r8d, 9EC0h; unsigned int
0x1800143bf  mov     rdx, [r15]; HINSTANCE
0x1800143c2  call    ?Format@CString@@QEAAHPEAUHINSTANCE__@@IZZ; CString::Format(HINSTANCE__ *,uint,...)
0x1800143c7  jmp     short loc_1800143D2
0x1800143c9  lea     rdx, [rbp+var_30]
0x1800143cd  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x1800143d2  mov     rax, cs:qword_180028680
0x1800143d9  mov     rcx, [rax]
0x1800143dc  mov     [rdi+30h], rcx
0x1800143e0  mov     [rbp+var_30], r13
0x1800143e4  lea     rcx, [rbp+var_30]; this
0x1800143e8  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x1800143ed  add     rsp, 50h
0x1800143f1  pop     r15
0x1800143f3  pop     r14
0x1800143f5  pop     r13
0x1800143f7  pop     rdi
0x1800143f8  pop     rsi
0x1800143f9  pop     rbx
0x1800143fa  pop     rbp
0x1800143fb  retn
0x1800143fc  lea     rcx, dword_180028688
0x180014403  call    _Init_thread_header
0x180014408  cmp     cs:dword_180028688, 0FFFFFFFFh
0x18001440f  jnz     loc_180014276
0x180014415  lea     rcx, qword_180028690; this
0x18001441c  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x180014421  lea     rcx, _CFileOwnerDialog__OnLVN_GetDispInfo____2____dynamic_atexit_destructor_for__strOwner__; void (__cdecl *)()
0x180014428  call    atexit
0x18001442d  nop
0x18001442e  lea     rcx, dword_180028688
0x180014435  call    _Init_thread_footer
0x18001443a  jmp     loc_180014276
0x18001443f  lea     rcx, dword_180028670
0x180014446  call    _Init_thread_header
0x18001444b  cmp     cs:dword_180028670, 0FFFFFFFFh
0x180014452  jnz     loc_180014267
0x180014458  lea     rcx, qword_180028678; this
0x18001445f  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x180014464  mov     cs:qword_180028678, r13
0x18001446b  lea     rcx, _CFileOwnerDialog__OnLVN_GetDispInfo____2____dynamic_atexit_destructor_for__strPath__; void (__cdecl *)()
0x180014472  call    atexit
0x180014477  nop
0x180014478  lea     rcx, dword_180028670
0x18001447f  call    _Init_thread_footer
0x180014484  jmp     loc_180014267
```
