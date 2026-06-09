# CFileOwnerDialog::TakeOwnershipOfSelectedFiles(HWND__ *)

- ea: `0x180014e68`
- end: `0x180015106`
- name: `?TakeOwnershipOfSelectedFiles@CFileOwnerDialog@@AEAAJPEAUHWND__@@@Z`
- size: `670`
- prototype: `__int64 __fastcall(CFileOwnerDialog *__hidden this, HWND hWnd)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180013d44`

## callees

- `0x180011c9c`
- `0x180011dd0`
- `0x180011ed4`
- `0x180011f58`
- `0x180011fdc`
- `0x180012064`
- `0x18001270c`
- `0x180013468`
- `0x18001387c`
- `0x180014e68`
- `0x180019dd0`
- `0x180019ee0`
- `0x180019f38`
- `0x18001a274`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001506a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001506a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800150d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800150d5`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180014f9a`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180014f9a`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18001500c`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18001500c`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180015027`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180015027`
- `USER32!SendMessageW` at `0x180014f6f`
- `USER32!SendMessageW` at `0x180015040`
- `USER32!SendMessageW` at `0x180014f6f`
- `USER32!SendMessageW` at `0x180015040`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFileOwnerDialog::TakeOwnershipOfSelectedFiles(HWND *this, HWND hWnd)
{
  __int64 v4; // rcx
  int OwnershipSid; // edi
  PSID v6; // rcx
  int v7; // r15d
  unsigned int i; // r14d
  __int64 v9; // rbx
  unsigned int v10; // r13d
  __int64 v11; // rax
  __int64 v12; // rbx
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  CString *v15; // rax
  signed int LastError; // eax
  void **v18; // [rsp+20h] [rbp-B9h] BYREF
  int v19; // [rsp+28h] [rbp-B1h]
  PSID pOwner; // [rsp+30h] [rbp-A9h]
  _QWORD v21[2]; // [rsp+38h] [rbp-A1h] BYREF
  _BYTE lParam[12]; // [rsp+48h] [rbp-91h] BYREF
  int v23; // [rsp+54h] [rbp-85h]
  __int64 v24; // [rsp+58h] [rbp-81h]
  __int128 v25; // [rsp+60h] [rbp-79h]
  _OWORD pSecurityDescriptor[2]; // [rsp+70h] [rbp-69h] BYREF
  __int64 v27; // [rsp+90h] [rbp-49h]
  _BYTE v28[12]; // [rsp+A0h] [rbp-39h] BYREF
  int v29; // [rsp+ACh] [rbp-2Dh]
  int v30; // [rsp+150h] [rbp+77h]

  CArray<COwnerListItemHandle>::CArray<COwnerListItemHandle>(v28);
  CFileOwnerDialog::BuildListOfSelectedFiles(this, hWnd, 0, v28);
  if ( v29 )
  {
    v19 = 0;
    pOwner = 0;
    v18 = &array_autoptr<char>::`vftable';
    OwnershipSid = CFileOwnerDialog::GetOwnershipSid(v4, (__int64)&v18);
    if ( OwnershipSid >= 0 )
    {
      CString::CString((CString *)v21);
      v21[0] = &CPath::`vftable';
      v7 = v29;
      for ( i = 0; (int)i < v7; ++i )
      {
        v9 = *(_QWORD *)CArray<COwnerListItemHandle>::operator[](v28, i);
        *(_QWORD *)&lParam[4] = 0;
        v23 = 0;
        v25 = 0;
        *(_DWORD *)lParam = 1;
        v24 = v9;
        v30 = SendMessageW(hWnd, 0x1053u, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)lParam);
        if ( v30 != -1 )
        {
          memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
          v27 = 0;
          if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
            goto LABEL_14;
          v10 = v9 & 0x3FF;
          v11 = CArray<COwnerListEntry *>::operator[](this + 10, v9 & 0x3FF);
          v12 = v9 >> 10;
          v13 = (_QWORD *)CArray<COwnerListFile>::operator[](v11 + 24, lParam, (unsigned int)v12);
          if ( v21 != v13 )
            CString::operator=(v21, v13);
          *(_QWORD *)lParam = &CPath::`vftable';
          CString::~CString((CString *)lParam);
          if ( SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0)
            && SetFileSecurityW(*(LPCWSTR *)v21[1], 1u, pSecurityDescriptor) )
          {
            SendMessageW(hWnd, 0x1008u, v30, 0);
            v14 = (_QWORD *)CArray<COwnerListItemHandle>::operator[](this + 10, v10);
            v15 = (CString *)CArray<COwnerListFile>::operator[](*v14 + 24LL, (unsigned int)v12);
            CString::Empty(v15);
          }
          else
          {
LABEL_14:
            LastError = GetLastError();
            OwnershipSid = LastError;
            if ( LastError > 0 )
              OwnershipSid = (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
      CFileOwnerDialog::InitializeOwnerCombo((CFileOwnerDialog *)this, (const struct COwnerList *)(this + 10), this[4]);
      v21[0] = &CPath::`vftable';
      CString::~CString((CString *)v21);
      v18 = &array_autoptr<char>::`vftable';
      if ( !v19 )
        goto LABEL_21;
      v6 = pOwner;
      if ( !pOwner )
        goto LABEL_21;
    }
    else
    {
      v18 = &array_autoptr<char>::`vftable';
      if ( !v19 )
      {
LABEL_21:
        v18 = &a_ptr<IDiskQuotaUser>::`vftable';
        goto LABEL_22;
      }
      v6 = pOwner;
    }
    if ( v6 )
      LocalFree(v6);
    goto LABEL_21;
  }
  OwnershipSid = 0;
LABEL_22:
  CArray<COwnerListEntry *>::~CArray<COwnerListEntry *>(v28);
  return (unsigned int)OwnershipSid;
}

```

## disassembly

```asm
0x180014e68  push    rbp
0x180014e6a  push    rbx
0x180014e6b  push    rsi
0x180014e6c  push    rdi
0x180014e6d  push    r12
0x180014e6f  push    r13
0x180014e71  push    r14
0x180014e73  push    r15
0x180014e75  lea     rbp, [rsp-1Fh]
0x180014e7a  sub     rsp, 0F8h
0x180014e81  mov     r12, rdx
0x180014e84  mov     rsi, rcx
0x180014e87  lea     rcx, [rbp+57h+var_90]
0x180014e8b  call    ??0?$CArray@VCOwnerListItemHandle@@@@QEAA@XZ; CArray<COwnerListItemHandle>::CArray<COwnerListItemHandle>(void)
0x180014e90  nop
0x180014e91  lea     r9, [rbp+57h+var_90]
0x180014e95  xor     r8d, r8d
0x180014e98  mov     rdx, r12
0x180014e9b  mov     rcx, rsi
0x180014e9e  call    ?BuildListOfSelectedFiles@CFileOwnerDialog@@AEAAXPEAUHWND__@@PEAVDblNulTermList@@PEAV?$CArray@VCOwnerListItemHandle@@@@@Z; CFileOwnerDialog::BuildListOfSelectedFiles(HWND__ *,DblNulTermList *,CArray<COwnerListItemHandle> *)
0x180014ea3  cmp     [rbp+57h+var_84], 0
0x180014ea7  jnz     short loc_180014EB0
0x180014ea9  xor     edi, edi
0x180014eab  jmp     loc_1800150E7
0x180014eb0  mov     [rsp+130h+var_108], 0
0x180014eb8  mov     [rsp+130h+pOwner], 0
0x180014ec1  lea     rbx, ??_7?$array_autoptr@D@@6B@; const array_autoptr<char>::`vftable'
0x180014ec8  mov     [rsp+130h+var_110], rbx
0x180014ecd  lea     rdx, [rsp+130h+var_110]
0x180014ed2  call    ?GetOwnershipSid@CFileOwnerDialog@@AEAAJPEAV?$array_autoptr@E@@@Z; CFileOwnerDialog::GetOwnershipSid(array_autoptr<uchar> *)
0x180014ed7  mov     edi, eax
0x180014ed9  test    eax, eax
0x180014edb  jns     short loc_180014EF7
0x180014edd  mov     [rsp+130h+var_110], rbx
0x180014ee2  cmp     [rsp+130h+var_108], 0
0x180014ee7  jz      loc_1800150DB
0x180014eed  mov     rcx, [rsp+130h+pOwner]
0x180014ef2  jmp     loc_1800150D0
0x180014ef7  lea     rcx, [rsp+130h+var_F8]; this
0x180014efc  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x180014f01  lea     r13, ??_7CPath@@6B@; const CPath::`vftable'
0x180014f08  mov     [rsp+130h+var_F8], r13
0x180014f0d  mov     r15d, [rbp+57h+var_84]
0x180014f11  xor     r14d, r14d
0x180014f14  test    r15d, r15d
0x180014f17  jle     loc_180015099
0x180014f1d  mov     edx, r14d
0x180014f20  lea     rcx, [rbp+57h+var_90]
0x180014f24  call    ??A?$CArray@VCOwnerListItemHandle@@@@QEAAAEAVCOwnerListItemHandle@@H@Z; CArray<COwnerListItemHandle>::operator[](int)
0x180014f29  mov     rbx, [rax]
0x180014f2c  mov     rax, rbx
0x180014f2f  shr     rax, 20h
0x180014f33  mov     qword ptr [rsp+130h+lParam+4], 0
0x180014f3c  mov     [rsp+130h+var_DC], 0
0x180014f44  xorps   xmm0, xmm0
0x180014f47  movdqu  [rbp+57h+var_D0], xmm0
0x180014f4c  mov     r13d, 1
0x180014f52  mov     dword ptr [rsp+130h+lParam], r13d
0x180014f57  mov     dword ptr [rsp+130h+var_D8], ebx
0x180014f5b  mov     dword ptr [rbp+57h+var_D8+4], eax
0x180014f5e  lea     r9, [rsp+130h+lParam]; lParam
0x180014f63  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x180014f67  mov     edx, 1053h; Msg
0x180014f6c  mov     rcx, r12; hWnd
0x180014f6f  call    cs:__imp_SendMessageW
0x180014f75  mov     [rbp+57h+arg_10], rax
0x180014f79  cmp     eax, 0FFFFFFFFh
0x180014f7c  jz      loc_18001507F
0x180014f82  xorps   xmm0, xmm0
0x180014f85  xor     eax, eax
0x180014f87  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x180014f8b  movups  [rbp+57h+var_B0], xmm0
0x180014f8f  mov     [rbp+57h+var_A0], rax
0x180014f93  mov     edx, r13d; dwRevision
0x180014f96  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180014f9a  call    cs:__imp_InitializeSecurityDescriptor
0x180014fa0  test    eax, eax
0x180014fa2  jz      loc_18001506A
0x180014fa8  mov     r13d, ebx
0x180014fab  and     r13d, 3FFh
0x180014fb2  lea     rcx, [rsi+50h]
0x180014fb6  mov     edx, r13d
0x180014fb9  call    ??A?$CArray@PEAVCOwnerListEntry@@@@QEBAPEAVCOwnerListEntry@@H@Z; CArray<COwnerListEntry *>::operator[](int)
0x180014fbe  sar     rbx, 0Ah
0x180014fc2  lea     rcx, [rax+18h]
0x180014fc6  mov     r8d, ebx
0x180014fc9  lea     rdx, [rsp+130h+lParam]
0x180014fce  call    ??A?$CArray@VCOwnerListFile@@@@QEBA?AVCOwnerListFile@@H@Z; CArray<COwnerListFile>::operator[](int)
0x180014fd3  lea     rcx, [rsp+130h+var_F8]
0x180014fd8  cmp     rcx, rax
0x180014fdb  jz      short loc_180014FEA
0x180014fdd  mov     rdx, rax
0x180014fe0  lea     rcx, [rsp+130h+var_F8]
0x180014fe5  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x180014fea  lea     rax, ??_7CPath@@6B@; const CPath::`vftable'
0x180014ff1  mov     qword ptr [rsp+130h+lParam], rax
0x180014ff6  lea     rcx, [rsp+130h+lParam]; this
0x180014ffb  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180015000  xor     r8d, r8d; bOwnerDefaulted
0x180015003  mov     rdx, [rsp+130h+pOwner]; pOwner
0x180015008  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18001500c  call    cs:__imp_SetSecurityDescriptorOwner
0x180015012  test    eax, eax
0x180015014  jz      short loc_18001506A
0x180015016  lea     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18001501a  mov     edx, 1; SecurityInformation
0x18001501f  mov     rcx, [rsp+130h+var_F0]
0x180015024  mov     rcx, [rcx]; lpFileName
0x180015027  call    cs:__imp_SetFileSecurityW
0x18001502d  test    eax, eax
0x18001502f  jz      short loc_18001506A
0x180015031  movsxd  r8, dword ptr [rbp+57h+arg_10]; wParam
0x180015035  xor     r9d, r9d; lParam
0x180015038  mov     edx, 1008h; Msg
0x18001503d  mov     rcx, r12; hWnd
0x180015040  call    cs:__imp_SendMessageW
0x180015046  mov     edx, r13d
0x180015049  lea     rcx, [rsi+50h]
0x18001504d  call    ??A?$CArray@VCOwnerListItemHandle@@@@QEAAAEAVCOwnerListItemHandle@@H@Z; CArray<COwnerListItemHandle>::operator[](int)
0x180015052  mov     rcx, [rax]
0x180015055  add     rcx, 18h
0x180015059  mov     edx, ebx
0x18001505b  call    ??A?$CArray@VCOwnerListFile@@@@QEAAAEAVCOwnerListFile@@H@Z; CArray<COwnerListFile>::operator[](int)
0x180015060  mov     rcx, rax; this
0x180015063  call    ?Empty@CString@@QEAAXXZ; CString::Empty(void)
0x180015068  jmp     short loc_18001507F
0x18001506a  call    cs:__imp_GetLastError
0x180015070  mov     edi, eax
0x180015072  test    eax, eax
0x180015074  jle     short loc_18001507F
0x180015076  movzx   edi, ax
0x180015079  or      edi, 80070000h
0x18001507f  inc     r14d
0x180015082  cmp     r14d, r15d
0x180015085  jl      loc_180014F1D
0x18001508b  lea     rbx, ??_7?$array_autoptr@D@@6B@; const array_autoptr<char>::`vftable'
0x180015092  lea     r13, ??_7CPath@@6B@; const CPath::`vftable'
0x180015099  lea     rdx, [rsi+50h]; struct COwnerList *
0x18001509d  mov     r8, [rsi+20h]; HWND
0x1800150a1  mov     rcx, rsi; this
0x1800150a4  call    ?InitializeOwnerCombo@CFileOwnerDialog@@AEAAXAEBVCOwnerList@@PEAUHWND__@@@Z; CFileOwnerDialog::InitializeOwnerCombo(COwnerList const &,HWND__ *)
0x1800150a9  nop
0x1800150aa  mov     [rsp+130h+var_F8], r13
0x1800150af  lea     rcx, [rsp+130h+var_F8]; this
0x1800150b4  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x1800150b9  nop
0x1800150ba  mov     [rsp+130h+var_110], rbx
0x1800150bf  cmp     [rsp+130h+var_108], 0
0x1800150c4  jz      short loc_1800150DB
0x1800150c6  mov     rcx, [rsp+130h+pOwner]; hMem
0x1800150cb  test    rcx, rcx
0x1800150ce  jz      short loc_1800150DB
0x1800150d0  test    rcx, rcx
0x1800150d3  jz      short loc_1800150DB
0x1800150d5  call    cs:__imp_LocalFree
0x1800150db  lea     rax, ??_7?$a_ptr@UIDiskQuotaUser@@@@6B@; const a_ptr<IDiskQuotaUser>::`vftable'
0x1800150e2  mov     [rsp+130h+var_110], rax
0x1800150e7  lea     rcx, [rbp+57h+var_90]
0x1800150eb  call    ??1?$CArray@PEAVCOwnerListEntry@@@@UEAA@XZ; CArray<COwnerListEntry *>::~CArray<COwnerListEntry *>(void)
0x1800150f0  mov     eax, edi
0x1800150f2  add     rsp, 0F8h
0x1800150f9  pop     r15
0x1800150fb  pop     r14
0x1800150fd  pop     r13
0x1800150ff  pop     r12
0x180015101  pop     rdi
0x180015102  pop     rsi
0x180015103  pop     rbx
0x180015104  pop     rbp
0x180015105  retn
```
