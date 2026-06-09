# CFileOwnerDialog::RemoveListViewItems(HWND__ *,CArray<COwnerListItemHandle> const &)

- ea: `0x180014980`
- end: `0x180014b79`
- name: `?RemoveListViewItems@CFileOwnerDialog@@AEAAXPEAUHWND__@@AEBV?$CArray@VCOwnerListItemHandle@@@@@Z`
- size: `505`
- prototype: `__int64 __fastcall(CFileOwnerDialog *this, HWND hWnd)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800130ac`
- `0x180013b8c`

## callees

- `0x180006eb4`
- `0x180011ed4`
- `0x180011f58`
- `0x180011fdc`
- `0x180012064`
- `0x18001387c`
- `0x180014980`
- `0x180019dd0`
- `0x180019ee0`
- `0x180019f38`
- `0x18001a274`
- `0x18001ce34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014a18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014a18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800149e8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180014abc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180014abc`
- `USER32!SendMessageW` at `0x1800149c5`
- `USER32!SendMessageW` at `0x180014a52`
- `USER32!SendMessageW` at `0x180014ad6`
- `USER32!SendMessageW` at `0x180014b27`
- `USER32!SendMessageW` at `0x1800149c5`
- `USER32!SendMessageW` at `0x180014a52`
- `USER32!SendMessageW` at `0x180014ad6`
- `USER32!SendMessageW` at `0x180014b27`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CFileOwnerDialog::RemoveListViewItems(HWND *this, HWND hWnd, __int64 a3)
{
  __int64 i; // rsi
  __int64 v7; // rbx
  unsigned int v8; // edi
  __int64 v9; // rax
  __int64 v10; // rbx
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  CString *v13; // rax
  _QWORD v14[3]; // [rsp+20h] [rbp-50h] BYREF
  int v15; // [rsp+38h] [rbp-38h]
  _BYTE lParam[12]; // [rsp+40h] [rbp-30h] BYREF
  int v17; // [rsp+4Ch] [rbp-24h]
  __int64 v18; // [rsp+50h] [rbp-20h]
  __int128 v19; // [rsp+58h] [rbp-18h]
  int pExceptionObject; // [rsp+B8h] [rbp+48h] BYREF
  LRESULT v21; // [rsp+C0h] [rbp+50h]
  HWND v22; // [rsp+C8h] [rbp+58h]

  CString::CString((CString *)v14);
  v14[0] = &CPath::`vftable';
  v22 = hWnd;
  SendMessageW(hWnd, 0xBu, 0, 0);
  pExceptionObject = *(_DWORD *)(a3 + 12);
  for ( i = 0; (int)i < pExceptionObject; i = (unsigned int)(i + 1) )
  {
    v14[2] = a3 + 32;
    EnterCriticalSection((LPCRITICAL_SECTION)(a3 + 32));
    v15 = 1;
    if ( (int)i >= *(_DWORD *)(a3 + 12) )
    {
      CMemoryException::CMemoryException(&pExceptionObject, 2);
      throw (CMemoryException *)&pExceptionObject;
    }
    v7 = *(_QWORD *)(*(_QWORD *)(a3 + 24) + 8 * i);
    v15 = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a3 + 32));
    *(_QWORD *)&lParam[4] = 0;
    v17 = 0;
    v19 = 0;
    *(_DWORD *)lParam = 1;
    v18 = v7;
    v21 = SendMessageW(hWnd, 0x1053u, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)lParam);
    if ( (_DWORD)v21 != -1 )
    {
      v8 = v7 & 0x3FF;
      v9 = CArray<COwnerListEntry *>::operator[](this + 10, v7 & 0x3FF);
      v10 = v7 >> 10;
      v11 = (_QWORD *)CArray<COwnerListFile>::operator[](v9 + 24, lParam, (unsigned int)v10);
      if ( v14 != v11 )
        CString::operator=(v14, v11);
      *(_QWORD *)lParam = &CPath::`vftable';
      CString::~CString((CString *)lParam);
      if ( GetFileAttributesW(*(LPCWSTR *)v14[1]) == -1 )
      {
        SendMessageW(hWnd, 0x1008u, (int)v21, 0);
        v12 = (_QWORD *)CArray<COwnerListItemHandle>::operator[](this + 10, v8);
        v13 = (CString *)CArray<COwnerListFile>::operator[](*v12 + 24LL, (unsigned int)v10);
        CString::Empty(v13);
      }
    }
  }
  CFileOwnerDialog::InitializeOwnerCombo((CFileOwnerDialog *)this, (const struct COwnerList *)(this + 10), this[4]);
  SendMessageW(hWnd, 0xBu, 1u, 0);
  v14[0] = &CPath::`vftable';
  CString::~CString((CString *)v14);
}

```

## disassembly

```asm
0x180014980  mov     [rsp-38h+arg_0], rbx
0x180014985  push    rbp
0x180014986  push    rsi
0x180014987  push    rdi
0x180014988  push    r12
0x18001498a  push    r13
0x18001498c  push    r14
0x18001498e  push    r15
0x180014990  mov     rbp, rsp
0x180014993  sub     rsp, 70h
0x180014997  mov     r15, r8
0x18001499a  mov     r12, rdx
0x18001499d  mov     r14, rcx
0x1800149a0  lea     rcx, [rbp+var_50]; this
0x1800149a4  call    ??0CString@@QEAA@XZ; CString::CString(void)
0x1800149a9  lea     rax, ??_7CPath@@6B@; const CPath::`vftable'
0x1800149b0  mov     [rbp+var_50], rax
0x1800149b4  mov     [rbp+arg_18], r12
0x1800149b8  xor     r9d, r9d; lParam
0x1800149bb  xor     r8d, r8d; wParam
0x1800149be  lea     edx, [r9+0Bh]; Msg
0x1800149c2  mov     rcx, r12; hWnd
0x1800149c5  call    cs:__imp_SendMessageW
0x1800149cb  nop
0x1800149cc  mov     eax, [r15+0Ch]
0x1800149d0  mov     [rbp+pExceptionObject], eax
0x1800149d3  xor     esi, esi
0x1800149d5  test    eax, eax
0x1800149d7  jle     loc_180014B08
0x1800149dd  lea     r13, [r15+20h]
0x1800149e1  mov     [rbp+var_40], r13
0x1800149e5  mov     rcx, r13; lpCriticalSection
0x1800149e8  call    cs:__imp_EnterCriticalSection
0x1800149ee  mov     [rbp+var_38], 1
0x1800149f5  cmp     esi, [r15+0Ch]
0x1800149f9  jge     loc_180014B5A
0x1800149ff  mov     rbx, [r15+18h]
0x180014a03  mov     rbx, [rbx+rsi*8]
0x180014a07  mov     rdi, rbx
0x180014a0a  shr     rdi, 20h
0x180014a0e  mov     [rbp+var_38], 0
0x180014a15  mov     rcx, r13; lpCriticalSection
0x180014a18  call    cs:__imp_LeaveCriticalSection
0x180014a1e  mov     qword ptr [rbp+lParam+4], 0
0x180014a26  mov     [rbp+var_24], 0
0x180014a2d  xorps   xmm0, xmm0
0x180014a30  movdqu  [rbp+var_18], xmm0
0x180014a35  mov     dword ptr [rbp+lParam], 1
0x180014a3c  mov     dword ptr [rbp+var_20], ebx
0x180014a3f  mov     dword ptr [rbp+var_20+4], edi
0x180014a42  lea     r9, [rbp+lParam]; lParam
0x180014a46  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x180014a4a  mov     edx, 1053h; Msg
0x180014a4f  mov     rcx, r12; hWnd
0x180014a52  call    cs:__imp_SendMessageW
0x180014a58  mov     [rbp+arg_10], rax
0x180014a5c  cmp     eax, 0FFFFFFFFh
0x180014a5f  jz      loc_180014AFD
0x180014a65  mov     edi, ebx
0x180014a67  and     edi, 3FFh
0x180014a6d  lea     rcx, [r14+50h]
0x180014a71  mov     edx, edi
0x180014a73  call    ??A?$CArray@PEAVCOwnerListEntry@@@@QEBAPEAVCOwnerListEntry@@H@Z; CArray<COwnerListEntry *>::operator[](int)
0x180014a78  sar     rbx, 0Ah
0x180014a7c  lea     rcx, [rax+18h]
0x180014a80  mov     r8d, ebx
0x180014a83  lea     rdx, [rbp+lParam]
0x180014a87  call    ??A?$CArray@VCOwnerListFile@@@@QEBA?AVCOwnerListFile@@H@Z; CArray<COwnerListFile>::operator[](int)
0x180014a8c  lea     rcx, [rbp+var_50]
0x180014a90  cmp     rcx, rax
0x180014a93  jz      short loc_180014AA1
0x180014a95  mov     rdx, rax
0x180014a98  lea     rcx, [rbp+var_50]
0x180014a9c  call    ??4CString@@QEAAAEAV0@AEBV0@@Z; CString::operator=(CString const &)
0x180014aa1  lea     rax, ??_7CPath@@6B@; const CPath::`vftable'
0x180014aa8  mov     qword ptr [rbp+lParam], rax
0x180014aac  lea     rcx, [rbp+lParam]; this
0x180014ab0  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180014ab5  mov     rcx, [rbp+var_48]
0x180014ab9  mov     rcx, [rcx]; lpFileName
0x180014abc  call    cs:__imp_GetFileAttributesW
0x180014ac2  cmp     eax, 0FFFFFFFFh
0x180014ac5  jnz     short loc_180014AFD
0x180014ac7  movsxd  r8, dword ptr [rbp+arg_10]; wParam
0x180014acb  xor     r9d, r9d; lParam
0x180014ace  mov     edx, 1008h; Msg
0x180014ad3  mov     rcx, r12; hWnd
0x180014ad6  call    cs:__imp_SendMessageW
0x180014adc  mov     edx, edi
0x180014ade  lea     rcx, [r14+50h]
0x180014ae2  call    ??A?$CArray@VCOwnerListItemHandle@@@@QEAAAEAVCOwnerListItemHandle@@H@Z; CArray<COwnerListItemHandle>::operator[](int)
0x180014ae7  mov     rcx, [rax]
0x180014aea  add     rcx, 18h
0x180014aee  mov     edx, ebx
0x180014af0  call    ??A?$CArray@VCOwnerListFile@@@@QEAAAEAVCOwnerListFile@@H@Z; CArray<COwnerListFile>::operator[](int)
0x180014af5  mov     rcx, rax; this
0x180014af8  call    ?Empty@CString@@QEAAXXZ; CString::Empty(void)
0x180014afd  inc     esi
0x180014aff  cmp     esi, [rbp+pExceptionObject]
0x180014b02  jl      loc_1800149E1
0x180014b08  lea     rdx, [r14+50h]; struct COwnerList *
0x180014b0c  mov     r8, [r14+20h]; HWND
0x180014b10  mov     rcx, r14; this
0x180014b13  call    ?InitializeOwnerCombo@CFileOwnerDialog@@AEAAXAEBVCOwnerList@@PEAUHWND__@@@Z; CFileOwnerDialog::InitializeOwnerCombo(COwnerList const &,HWND__ *)
0x180014b18  nop
0x180014b19  xor     r9d, r9d; lParam
0x180014b1c  lea     edx, [r9+0Bh]; Msg
0x180014b20  lea     r8d, [r9+1]; wParam
0x180014b24  mov     rcx, r12; hWnd
0x180014b27  call    cs:__imp_SendMessageW
0x180014b2d  nop
0x180014b2e  lea     rax, ??_7CPath@@6B@; const CPath::`vftable'
0x180014b35  mov     [rbp+var_50], rax
0x180014b39  lea     rcx, [rbp+var_50]; this
0x180014b3d  call    ??1CString@@UEAA@XZ; CString::~CString(void)
0x180014b42  mov     rbx, [rsp+70h+arg_0]
0x180014b4a  add     rsp, 70h
0x180014b4e  pop     r15
0x180014b50  pop     r14
0x180014b52  pop     r13
0x180014b54  pop     r12
0x180014b56  pop     rdi
0x180014b57  pop     rsi
0x180014b58  pop     rbp
0x180014b59  retn
0x180014b5a  mov     edx, 2
0x180014b5f  lea     rcx, [rbp+pExceptionObject]
0x180014b63  call    ??0CMemoryException@@QEAA@W4reason@0@@Z; CMemoryException::CMemoryException(CMemoryException::reason)
0x180014b68  lea     rdx, _TI2?AVCMemoryException@@; pThrowInfo
0x180014b6f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180014b73  call    _CxxThrowException_0
```
