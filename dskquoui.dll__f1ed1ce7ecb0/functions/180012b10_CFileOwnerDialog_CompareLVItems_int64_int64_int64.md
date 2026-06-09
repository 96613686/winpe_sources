# CFileOwnerDialog::CompareLVItems(__int64,__int64,__int64)

- ea: `0x180012b10`
- end: `0x180012e8d`
- name: `?CompareLVItems@CFileOwnerDialog@@CAH_J00@Z`
- size: `893`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x18000199c`
- `0x180001bcc`
- `0x180001c34`
- `0x180011f58`
- `0x180012064`
- `0x180012b10`
- `0x180019dd0`
- `0x180019e80`
- `0x180019ee0`
- `0x180019f38`
- `0x180019fb0`
- `0x18001a274`
- `0x18001a708`
- `0x18001bfc8`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180012cd5`
- `SHLWAPI!PathFindFileNameW` at `0x180012d30`
- `SHLWAPI!PathFindFileNameW` at `0x180012cd5`
- `SHLWAPI!PathFindFileNameW` at `0x180012d30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012d8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012d8f`
- `KERNEL32!lstrcmpW` at `0x180012d7f`
- `KERNEL32!lstrcmpW` at `0x180012d7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall CFileOwnerDialog::CompareLVItems(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdi
  unsigned int v7; // r13d
  unsigned int v8; // r15d
  unsigned int i; // r12d
  int v10; // edx
  int v11; // edx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  CPath *v15; // rax
  __int64 v16; // rax
  CPath *v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  LPWSTR FileNameW; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  LPWSTR v23; // rax
  WCHAR *v24; // r15
  LPCWSTR lpString2[10]; // [rsp+28h] [rbp-50h] BYREF
  __int64 v28; // [rsp+80h] [rbp+8h]
  __int64 v29; // [rsp+88h] [rbp+10h]
  unsigned int v30; // [rsp+98h] [rbp+20h]

  v5 = 0;
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_1800286A0 > *(_DWORD *)(v6 + 4) )
  {
    Init_thread_header(&dword_1800286A0);
    if ( dword_1800286A0 == -1 )
    {
      CString::CString((CString *)&qword_1800286A8);
      qword_1800286A8 = &CPath::`vftable';
      atexit(CFileOwnerDialog::CompareLVItems_::_3_::_dynamic_atexit_destructor_for__s1__);
      Init_thread_footer(&dword_1800286A0);
    }
  }
  if ( dword_1800286B8 > *(_DWORD *)(v6 + 4) )
  {
    Init_thread_header(&dword_1800286B8);
    if ( dword_1800286B8 == -1 )
    {
      CString::CString((CString *)&qword_1800286C0);
      qword_1800286C0 = &CPath::`vftable';
      atexit(CFileOwnerDialog::CompareLVItems_::_3_::_dynamic_atexit_destructor_for__s2__);
      Init_thread_footer(&dword_1800286B8);
    }
  }
  v7 = a1 & 0x3FF;
  v8 = a2 & 0x3FF;
  v30 = v8;
  v28 = a1 >> 10;
  v29 = a2 >> 10;
  for ( i = 0; !v5 && i < 3; ++i )
  {
    v10 = *((_DWORD *)qword_180022008 + 3 * *(int *)(a3 + 48) + (int)i);
    if ( !v10 )
    {
      v18 = CArray<COwnerListEntry *>::operator[](a3 + 80, v7);
      v19 = CArray<COwnerListFile>::operator[](v18 + 24, lpString2, (unsigned int)v28);
      FileNameW = PathFindFileNameW(**(LPCWSTR **)(v19 + 8));
      CString::operator=(&qword_1800286A8, FileNameW);
      CString::Length((CString *)&qword_1800286A8);
      lpString2[0] = (LPCWSTR)&CPath::`vftable';
      CString::~CString((CString *)lpString2);
      v21 = CArray<COwnerListEntry *>::operator[](a3 + 80, v8);
      v22 = CArray<COwnerListFile>::operator[](v21 + 24, lpString2, (unsigned int)v29);
      v23 = PathFindFileNameW(**(LPCWSTR **)(v22 + 8));
      CString::operator=(&qword_1800286C0, v23);
      CString::Length((CString *)&qword_1800286C0);
      goto LABEL_12;
    }
    v11 = v10 - 1;
    if ( !v11 )
    {
      v14 = CArray<COwnerListEntry *>::operator[](a3 + 80, v7);
      v15 = (CPath *)CArray<COwnerListFile>::operator[](v14 + 24, lpString2, (unsigned int)v28);
      CPath::GetPath(v15, (struct CPath *)&qword_1800286A8);
      lpString2[0] = (LPCWSTR)&CPath::`vftable';
      CString::~CString((CString *)lpString2);
      v16 = CArray<COwnerListEntry *>::operator[](a3 + 80, v8);
      v17 = (CPath *)CArray<COwnerListFile>::operator[](v16 + 24, lpString2, (unsigned int)v29);
      CPath::GetPath(v17, (struct CPath *)&qword_1800286C0);
LABEL_12:
      lpString2[0] = (LPCWSTR)&CPath::`vftable';
      CString::~CString((CString *)lpString2);
      goto LABEL_13;
    }
    if ( v11 == 1 )
    {
      v12 = CArray<COwnerListEntry *>::operator[](a3 + 80, v7);
      CString::operator=(&qword_1800286A8, v12 + 8);
      v13 = CArray<COwnerListEntry *>::operator[](a3 + 80, v8);
      CString::operator=(&qword_1800286C0, v13 + 8);
    }
LABEL_13:
    CString::StringValue::StringValue((CString::StringValue *)lpString2, *(const unsigned __int16 **)qword_1800286C8);
    v24 = (WCHAR *)lpString2[0];
    v5 = lstrcmpW(*(LPCWSTR *)qword_1800286B0, lpString2[0]);
    if ( v24 )
      LocalFree(v24);
    v8 = v30;
  }
  CString::Empty((CString *)&qword_1800286A8);
  CString::Empty((CString *)&qword_1800286C0);
  if ( !*(_BYTE *)(a3 + 152) )
    return -v5;
  return v5;
}

```

## disassembly

```asm
0x180012b10  mov     [rsp+arg_0], rcx
0x180012b15  push    rbx
0x180012b16  push    rsi
0x180012b17  push    rdi
0x180012b18  push    r12
0x180012b1a  push    r13
0x180012b1c  push    r14
0x180012b1e  push    r15
0x180012b20  sub     rsp, 40h
0x180012b24  mov     r14, r8
0x180012b27  mov     r12, rdx
0x180012b2a  mov     [rsp+78h+var_58], r8
0x180012b2f  xor     ebx, ebx
0x180012b31  mov     [rsp+78h+arg_10], ebx
0x180012b38  mov     r9d, cs:_tls_index
0x180012b3f  mov     rax, gs:58h
0x180012b48  mov     r15d, 4
0x180012b4e  mov     rdi, [rax+r9*8]
0x180012b52  mov     eax, [rdi+r15]
0x180012b56  cmp     cs:dword_1800286A0, eax
0x180012b5c  jg      loc_180012DED
0x180012b62  lea     rsi, ??_7CPath@@6B@; const CPath::`vftable'
0x180012b69  mov     eax, [rdi+r15]
0x180012b6d  cmp     cs:dword_1800286B8, eax
0x180012b73  jg      loc_180012E3E
0x180012b79  lea     rdi, qword_1800286C0
0x180012b80  mov     rax, [rsp+78h+arg_0]
0x180012b88  mov     r13d, eax
0x180012b8b  mov     ecx, 3FFh
0x180012b90  and     r13d, ecx
0x180012b93  mov     r15d, r12d
0x180012b96  and     r15d, ecx
0x180012b99  mov     [rsp+78h+arg_18], r15d
0x180012ba1  sar     rax, 0Ah
0x180012ba5  mov     [rsp+78h+arg_0], rax
0x180012bad  sar     r12, 0Ah
0x180012bb1  mov     [rsp+78h+arg_8], r12
0x180012bb9  xor     r12d, r12d
0x180012bbc  test    ebx, ebx
0x180012bbe  jnz     loc_180012DAC
0x180012bc4  cmp     r12d, 3
0x180012bc8  jnb     loc_180012DAC
0x180012bce  movsxd  rax, dword ptr [r14+30h]
0x180012bd2  lea     rcx, [rax+rax*2]
0x180012bd6  movsxd  rax, r12d
0x180012bd9  add     rcx, rax
0x180012bdc  lea     rdx, qword_180022008
0x180012be3  mov     edx, [rdx+rcx*4]
0x180012be6  test    edx, edx
0x180012be8  jz      loc_180012CAB
0x180012bee  sub     edx, 1
0x180012bf1  jz      short loc_180012C35
0x180012bf3  cmp     edx, 1
0x180012bf6  jnz     loc_180012D59
0x180012bfc  mov     edx, r13d
0x180012bff  lea     rcx, [r14+50h]
0x180012c03  call    ??A?$CArray@PEAVCOwnerListEntry@@@@QEBAPEAVCOwnerListEntry@@H@Z; CArray<COwnerListEntry *>::operator[](int)
0x180012c08  lea     rdx, [rax+8]
0x180012c0c  lea     rcx, qword_1800286A8
0x180012c13  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x180012c18  mov     edx, r15d
0x180012c1b  lea     rcx, [r14+50h]
0x180012c1f  call    ??A?$CArray@PEAVCOwnerListEntry@@@@QEBAPEAVCOwnerListEntry@@H@Z; CArray<COwnerListEntry *>::operator[](int)
0x180012c24  lea     rdx, [rax+8]
0x180012c28  mov     rcx, rdi
0x180012c2b  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x180012c30  jmp     loc_180012D59
0x180012c35  mov     edx, r13d
0x180012c38  lea     rcx, [r14+50h]
0x180012c3c  call    ??A?$CArray@PEAVCOwnerListEntry@@@@QEBAPEAVCOwnerListEntry@@H@Z; CArray<COwnerListEntry *>::operator[](int)
0x180012c41  lea     rcx, [rax+18h]
0x180012c45  mov     r8d, dword ptr [rsp+78h+arg_0]
0x180012c4d  lea     rdx, [rsp+78h+lpString2]
0x180012c52  call    ??A?$CArray@VCOwnerListFile@@@@QEBA?AVCOwnerListFile@@H@Z; CArray<COwnerListFile>::operator[](int)
0x180012c57  nop
0x180012c58  lea     rdx, qword_1800286A8; struct CPath *
0x180012c5f  mov     rcx, rax; this
0x180012c62  call    ?GetPath@CPath@@QEBA_NPEAV1@@Z; CPath::GetPath(CPath *)
0x180012c67  nop
0x180012c68  mov     [rsp+78h+lpString2], rsi
0x180012c6d  lea     rcx, [rsp+78h+lpString2]; this
0x180012c72  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180012c77  mov     edx, r15d
0x180012c7a  lea     rcx, [r14+50h]
0x180012c7e  call    ??A?$CArray@PEAVCOwnerListEntry@@@@QEBAPEAVCOwnerListEntry@@H@Z; CArray<COwnerListEntry *>::operator[](int)
0x180012c83  lea     rcx, [rax+18h]
0x180012c87  mov     r8d, dword ptr [rsp+78h+arg_8]
0x180012c8f  lea     rdx, [rsp+78h+lpString2]
0x180012c94  call    ??A?$CArray@VCOwnerListFile@@@@QEBA?AVCOwnerListFile@@H@Z; CArray<COwnerListFile>::operator[](int)
0x180012c99  nop
0x180012c9a  mov     rdx, rdi; struct CPath *
0x180012c9d  mov     rcx, rax; this
0x180012ca0  call    ?GetPath@CPath@@QEBA_NPEAV1@@Z; CPath::GetPath(CPath *)
0x180012ca5  nop
0x180012ca6  jmp     loc_180012D4A
0x180012cab  mov     edx, r13d
0x180012cae  lea     rcx, [r14+50h]
0x180012cb2  call    ??A?$CArray@PEAVCOwnerListEntry@@@@QEBAPEAVCOwnerListEntry@@H@Z; CArray<COwnerListEntry *>::operator[](int)
0x180012cb7  lea     rcx, [rax+18h]
0x180012cbb  mov     r8d, dword ptr [rsp+78h+arg_0]
0x180012cc3  lea     rdx, [rsp+78h+lpString2]
0x180012cc8  call    ??A?$CArray@VCOwnerListFile@@@@QEBA?AVCOwnerListFile@@H@Z; CArray<COwnerListFile>::operator[](int)
0x180012ccd  nop
0x180012cce  mov     rcx, [rax+8]
0x180012cd2  mov     rcx, [rcx]; pszPath
0x180012cd5  call    cs:__imp_PathFindFileNameW
0x180012cdb  mov     rdx, rax
0x180012cde  lea     rcx, qword_1800286A8
0x180012ce5  call    ??4CString@@QEAAAEAV0@PEBG@Z; CString::operator=(ushort const *)
0x180012cea  lea     rcx, qword_1800286A8; this
0x180012cf1  call    ?Length@CString@@QEBAHXZ; CString::Length(void)
0x180012cf6  nop
0x180012cf7  mov     [rsp+78h+lpString2], rsi
0x180012cfc  lea     rcx, [rsp+78h+lpString2]; this
0x180012d01  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180012d06  mov     edx, r15d
0x180012d09  lea     rcx, [r14+50h]
0x180012d0d  call    ??A?$CArray@PEAVCOwnerListEntry@@@@QEBAPEAVCOwnerListEntry@@H@Z; CArray<COwnerListEntry *>::operator[](int)
0x180012d12  lea     rcx, [rax+18h]
0x180012d16  mov     r8d, dword ptr [rsp+78h+arg_8]
0x180012d1e  lea     rdx, [rsp+78h+lpString2]
0x180012d23  call    ??A?$CArray@VCOwnerListFile@@@@QEBA?AVCOwnerListFile@@H@Z; CArray<COwnerListFile>::operator[](int)
0x180012d28  nop
0x180012d29  mov     rcx, [rax+8]
0x180012d2d  mov     rcx, [rcx]; pszPath
0x180012d30  call    cs:__imp_PathFindFileNameW
0x180012d36  mov     rdx, rax
0x180012d39  mov     rcx, rdi
0x180012d3c  call    ??4CString@@QEAAAEAV0@PEBG@Z; CString::operator=(ushort const *)
0x180012d41  mov     rcx, rdi; this
0x180012d44  call    ?Length@CString@@QEBAHXZ; CString::Length(void)
0x180012d49  nop
0x180012d4a  mov     [rsp+78h+lpString2], rsi
0x180012d4f  lea     rcx, [rsp+78h+lpString2]; this
0x180012d54  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180012d59  mov     rdx, cs:qword_1800286C8
0x180012d60  mov     rdx, [rdx]; unsigned __int16 *
0x180012d63  lea     rcx, [rsp+78h+lpString2]; this
0x180012d68  call    ??0StringValue@CString@@QEAA@PEBG@Z; CString::StringValue::StringValue(ushort const *)
0x180012d6d  mov     r15, [rsp+78h+lpString2]
0x180012d72  mov     rdx, r15; lpString2
0x180012d75  mov     rcx, cs:qword_1800286B0
0x180012d7c  mov     rcx, [rcx]; lpString1
0x180012d7f  call    cs:__imp_lstrcmpW
0x180012d85  mov     ebx, eax
0x180012d87  test    r15, r15
0x180012d8a  jz      short loc_180012D95
0x180012d8c  mov     rcx, r15; hMem
0x180012d8f  call    cs:__imp_LocalFree
0x180012d95  inc     r12d
0x180012d98  mov     [rsp+78h+arg_10], ebx
0x180012d9f  mov     r15d, [rsp+78h+arg_18]
0x180012da7  jmp     loc_180012BBC
0x180012dac  lea     rcx, qword_1800286A8; this
0x180012db3  call    ?Empty@CString@@QEAAXXZ; CString::Empty(void)
0x180012db8  mov     rcx, rdi; this
0x180012dbb  call    ?Empty@CString@@QEAAXXZ; CString::Empty(void)
0x180012dc0  nop
0x180012dc1  jmp     short loc_180012DCF
0x180012dc3  mov     r14, [rsp+78h+var_58]
0x180012dc8  mov     ebx, [rsp+78h+arg_10]
0x180012dcf  cmp     byte ptr [r14+98h], 0
0x180012dd7  jnz     short loc_180012DDB
0x180012dd9  neg     ebx
0x180012ddb  mov     eax, ebx
0x180012ddd  add     rsp, 40h
0x180012de1  pop     r15
0x180012de3  pop     r14
0x180012de5  pop     r13
0x180012de7  pop     r12
0x180012de9  pop     rdi
0x180012dea  pop     rsi
0x180012deb  pop     rbx
0x180012dec  retn
0x180012ded  lea     rcx, dword_1800286A0
0x180012df4  call    _Init_thread_header
0x180012df9  cmp     cs:dword_1800286A0, 0FFFFFFFFh
0x180012e00  jnz     loc_180012B62
0x180012e06  lea     rcx, qword_1800286A8; this
0x180012e0d  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x180012e12  lea     rsi, ??_7CPath@@6B@; const CPath::`vftable'
0x180012e19  mov     cs:qword_1800286A8, rsi
0x180012e20  lea     rcx, _CFileOwnerDialog__CompareLVItems____3____dynamic_atexit_destructor_for__s1__; void (__cdecl *)()
0x180012e27  call    atexit
0x180012e2c  nop
0x180012e2d  lea     rcx, dword_1800286A0
0x180012e34  call    _Init_thread_footer
0x180012e39  jmp     loc_180012B69
0x180012e3e  lea     rcx, dword_1800286B8
0x180012e45  call    _Init_thread_header
0x180012e4a  cmp     cs:dword_1800286B8, 0FFFFFFFFh
0x180012e51  jnz     loc_180012B79
0x180012e57  lea     rdi, qword_1800286C0
0x180012e5e  mov     rcx, rdi; this
0x180012e61  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x180012e66  mov     cs:qword_1800286C0, rsi
0x180012e6d  lea     rcx, _CFileOwnerDialog__CompareLVItems____3____dynamic_atexit_destructor_for__s2__; void (__cdecl *)()
0x180012e74  call    atexit
0x180012e79  nop
0x180012e7a  lea     rcx, dword_1800286B8
0x180012e81  call    _Init_thread_footer
0x180012e86  jmp     loc_180012B80
```
