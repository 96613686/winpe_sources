# CAMCDocManager::DoPromptFileName(CString &,uint,ulong,int,CDocTemplate *)

- ea: `0x14005af30`
- end: `0x14005b1b2`
- name: `?DoPromptFileName@CAMCDocManager@@UEAAHAEAVCString@@IKHPEAVCDocTemplate@@@Z`
- size: `642`
- prototype: `__int64 __fastcall(CAMCDocManager *__hidden this, struct CString *, unsigned int, unsigned int, int, struct CDocTemplate *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x14005af30`
- `0x14005b1b8`
- `0x140081d14`
- `0x140081d4c`
- `0x140081e6c`
- `0x1400b5b84`
- `0x1400b5c10`
- `0x1400e9e10`

## import_xrefs

- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x14005af83`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x14005affc`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x14005b020`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x14005b02c`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x14005b099`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x14005af83`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x14005affc`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x14005b020`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x14005b02c`
- `MFC42u!__imp_??0CString@@QEAA@XZ` at `0x14005b099`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14005afa9`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14005afcf`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14005b15a`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14005b166`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14005b172`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14005b17e`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14005afa9`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14005afcf`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14005b15a`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14005b166`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14005b172`
- `MFC42u!__imp_??1CString@@QEAA@XZ` at `0x14005b17e`
- `MFC42u!__imp_??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x14005af9d`
- `MFC42u!__imp_??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x14005af9d`
- `MFC42u!__imp_??YCString@@QEAAAEBV0@AEBV0@@Z` at `0x14005b0ba`
- `MFC42u!__imp_??YCString@@QEAAAEBV0@AEBV0@@Z` at `0x14005b0ba`
- `MFC42u!__imp_??YCString@@QEAAAEBV0@G@Z` at `0x14005b0c7`
- `MFC42u!__imp_??YCString@@QEAAAEBV0@G@Z` at `0x14005b0e6`
- `MFC42u!__imp_??YCString@@QEAAAEBV0@G@Z` at `0x14005b0c7`
- `MFC42u!__imp_??YCString@@QEAAAEBV0@G@Z` at `0x14005b0e6`
- `MFC42u!__imp_??YCString@@QEAAAEBV0@PEBG@Z` at `0x14005b0d9`
- `MFC42u!__imp_??YCString@@QEAAAEBV0@PEBG@Z` at `0x14005b0d9`
- `MFC42u!__imp_?GetBuffer@CString@@QEAAPEAGH@Z` at `0x14005b10e`
- `MFC42u!__imp_?GetBuffer@CString@@QEAAPEAGH@Z` at `0x14005b10e`
- `MFC42u!__imp_?LoadStringW@CString@@QEAAHI@Z` at `0x14005b00b`
- `MFC42u!__imp_?LoadStringW@CString@@QEAAHI@Z` at `0x14005b0aa`
- `MFC42u!__imp_?LoadStringW@CString@@QEAAHI@Z` at `0x14005b00b`
- `MFC42u!__imp_?LoadStringW@CString@@QEAAHI@Z` at `0x14005b0aa`
- `MFC42u!__imp_?ReleaseBuffer@CString@@QEAAXH@Z` at `0x14005b14e`
- `MFC42u!__imp_?ReleaseBuffer@CString@@QEAAXH@Z` at `0x14005b14e`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x14005afbe`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x14005afbe`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x14005b121`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x14005b121`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_BOOL8 __fastcall CAMCDocManager::DoPromptFileName(
        CAMCDocManager *this,
        struct CString *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        int a5,
        struct CDocTemplate *a6)
{
  int v6; // ebx
  __int64 v10; // rcx
  __int64 DefaultDirectory; // rax
  BOOL v12; // eax
  CPtrList *v13; // rcx
  int i; // ebx
  struct CDocTemplate **Next; // rax
  BOOL v16; // ebx
  struct CWnd *v18; // [rsp+30h] [rbp-D0h]
  const WCHAR *v19; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpPathName; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v21[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[8]; // [rsp+58h] [rbp-A8h] BYREF
  const WCHAR *v23; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[8]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v25[192]; // [rsp+70h] [rbp-90h] BYREF
  tagOFN_NT4W v26; // [rsp+130h] [rbp+30h] BYREF
  WCHAR Buffer[264]; // [rsp+4F0h] [rbp+3F0h] BYREF

  v6 = (int)a4;
  if ( !HIDWORD(qword_1401620D8) )
  {
    CString::CString(&lpPathName);
    DefaultDirectory = CAMCApp::GetDefaultDirectory(v10, v24);
    CString::operator=(&lpPathName, DefaultDirectory);
    CString::~CString(v24);
    if ( *((_DWORD *)lpPathName - 2) )
      v12 = SetCurrentDirectoryW(lpPathName);
    else
      v12 = 0;
    HIDWORD(qword_1401620D8) = v12;
    CString::~CString(&lpPathName);
  }
  CFileDialogEx::CFileDialogEx((CFileDialogEx *)v25, a5, 0, a4, 6u, 0, v18);
  CString::CString(&v23);
  CString::LoadStringW((CString *)&v23, a3);
  v26.Flags |= v6 | 0x800000;
  CString::CString(&v19);
  CString::CString(v22);
  if ( a6 )
  {
    AppendFilterSuffix((struct CString *)&v19, &v26, a6, (struct CString *)v22);
  }
  else
  {
    lpPathName = (LPCWSTR)*((_QWORD *)this + 2);
    for ( i = 1; lpPathName; i = 0 )
    {
      Next = (struct CDocTemplate **)CPtrList::GetNext(v13, (struct __POSITION **)&lpPathName);
      AppendFilterSuffix(
        (struct CString *)&v19,
        &v26,
        *Next,
        (struct CString *)((unsigned __int64)v22 & -(__int64)(i != 0)));
    }
  }
  CString::CString(v21);
  CString::LoadStringW((CString *)v21, 0xF002u);
  CString::operator+=(&v19, v21);
  CString::operator+=(&v19, 0);
  CString::operator+=(&v19, L"*.*");
  CString::operator+=(&v19, 0);
  ++v26.nMaxCustFilter;
  v26.lpstrFilter = v19;
  v26.lpstrTitle = v23;
  v26.lpstrFile = CString::GetBuffer(a2, 260);
  GetCurrentDirectoryW(0x104u, Buffer);
  v26.lpstrInitialDir = Buffer;
  v16 = CFileDialogEx::DoModal((CFileDialogEx *)v25) == 1;
  CString::ReleaseBuffer(a2, -1);
  CString::~CString(v21);
  CString::~CString(v22);
  CString::~CString(&v19);
  CString::~CString(&v23);
  CFileDialog::~CFileDialog((CFileDialog *)v25);
  return v16;
}

```

## disassembly

```asm
0x14005af30  push    rbp
0x14005af32  push    rbx
0x14005af33  push    rsi
0x14005af34  push    rdi
0x14005af35  push    r12
0x14005af37  push    r14
0x14005af39  push    r15
0x14005af3b  lea     rbp, [rsp-610h]
0x14005af43  sub     rsp, 710h
0x14005af4a  mov     rax, cs:__security_cookie
0x14005af51  xor     rax, rsp
0x14005af54  mov     [rbp+640h+var_40], rax
0x14005af5b  mov     ebx, r9d
0x14005af5e  mov     r14d, r8d
0x14005af61  mov     r12, rdx
0x14005af64  mov     rsi, rcx
0x14005af67  mov     r15d, [rbp+640h+arg_20]
0x14005af6e  mov     rdi, [rbp+640h+arg_28]
0x14005af75  cmp     dword ptr cs:qword_1401620D8+4, 0
0x14005af7c  jnz     short loc_14005AFD5
0x14005af7e  lea     rcx, [rsp+740h+lpPathName]
0x14005af83  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x14005af89  nop
0x14005af8a  lea     rdx, [rsp+740h+var_6D8]
0x14005af8f  call    ?GetDefaultDirectory@CAMCApp@@QEAA?AVCString@@XZ; CAMCApp::GetDefaultDirectory(void)
0x14005af94  nop
0x14005af95  mov     rdx, rax
0x14005af98  lea     rcx, [rsp+740h+lpPathName]
0x14005af9d  call    cs:__imp_??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x14005afa3  nop
0x14005afa4  lea     rcx, [rsp+740h+var_6D8]
0x14005afa9  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x14005afaf  mov     rcx, [rsp+740h+lpPathName]; lpPathName
0x14005afb4  cmp     dword ptr [rcx-8], 0
0x14005afb8  jnz     short loc_14005AFBE
0x14005afba  xor     eax, eax
0x14005afbc  jmp     short loc_14005AFC4
0x14005afbe  call    cs:__imp_SetCurrentDirectoryW
0x14005afc4  mov     dword ptr cs:qword_1401620D8+4, eax
0x14005afca  lea     rcx, [rsp+740h+lpPathName]
0x14005afcf  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x14005afd5  mov     [rsp+740h+var_718], 0; unsigned __int16 *
0x14005afde  mov     [rsp+740h+var_720], 6; unsigned int
0x14005afe6  xor     r8d, r8d; unsigned __int16 *
0x14005afe9  mov     edx, r15d; int
0x14005afec  lea     rcx, [rsp+740h+var_6D0]; this
0x14005aff1  call    ??0CFileDialogEx@@QEAA@HPEBG0K0PEAVCWnd@@@Z; CFileDialogEx::CFileDialogEx(int,ushort const *,ushort const *,ulong,ushort const *,CWnd *)
0x14005aff6  nop
0x14005aff7  lea     rcx, [rsp+740h+var_6E0]
0x14005affc  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x14005b002  nop
0x14005b003  mov     edx, r14d
0x14005b006  lea     rcx, [rsp+740h+var_6E0]
0x14005b00b  call    cs:__imp_?LoadStringW@CString@@QEAAHI@Z; CString::LoadStringW(uint)
0x14005b011  bts     ebx, 17h
0x14005b015  or      [rbp+640h+var_610.Flags], ebx
0x14005b01b  lea     rcx, [rsp+740h+var_700]
0x14005b020  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x14005b026  nop
0x14005b027  lea     rcx, [rsp+740h+var_6E8]
0x14005b02c  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x14005b032  nop
0x14005b033  test    rdi, rdi
0x14005b036  jz      short loc_14005B050
0x14005b038  lea     r9, [rsp+740h+var_6E8]; struct CString *
0x14005b03d  mov     r8, rdi; struct CDocTemplate *
0x14005b040  lea     rdx, [rbp+640h+var_610]; struct tagOFN_NT4W *
0x14005b044  lea     rcx, [rsp+740h+var_700]; struct CString *
0x14005b049  call    ?AppendFilterSuffix@@YAXAEAVCString@@AEAUtagOFN_NT4W@@PEAVCDocTemplate@@PEAV1@@Z; AppendFilterSuffix(CString &,tagOFN_NT4W &,CDocTemplate *,CString *)
0x14005b04e  jmp     short loc_14005B094
0x14005b050  mov     rax, [rsi+10h]
0x14005b054  mov     [rsp+740h+lpPathName], rax
0x14005b059  mov     ebx, 1
0x14005b05e  test    rax, rax
0x14005b061  jz      short loc_14005B094
0x14005b063  lea     rdx, [rsp+740h+lpPathName]; struct __POSITION **
0x14005b068  call    ?GetNext@CPtrList@@QEAAAEAPEAXAEAPEAU__POSITION@@@Z; CPtrList::GetNext(__POSITION * &)
0x14005b06d  neg     ebx
0x14005b06f  sbb     r9, r9
0x14005b072  lea     rcx, [rsp+740h+var_6E8]
0x14005b077  and     r9, rcx; struct CString *
0x14005b07a  mov     r8, [rax]; struct CDocTemplate *
0x14005b07d  lea     rdx, [rbp+640h+var_610]; struct tagOFN_NT4W *
0x14005b081  lea     rcx, [rsp+740h+var_700]; struct CString *
0x14005b086  call    ?AppendFilterSuffix@@YAXAEAVCString@@AEAUtagOFN_NT4W@@PEAVCDocTemplate@@PEAV1@@Z; AppendFilterSuffix(CString &,tagOFN_NT4W &,CDocTemplate *,CString *)
0x14005b08b  xor     ebx, ebx
0x14005b08d  cmp     [rsp+740h+lpPathName], rbx
0x14005b092  jnz     short loc_14005B063
0x14005b094  lea     rcx, [rsp+740h+var_6F0]
0x14005b099  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x14005b09f  nop
0x14005b0a0  mov     edx, 0F002h
0x14005b0a5  lea     rcx, [rsp+740h+var_6F0]
0x14005b0aa  call    cs:__imp_?LoadStringW@CString@@QEAAHI@Z; CString::LoadStringW(uint)
0x14005b0b0  lea     rdx, [rsp+740h+var_6F0]
0x14005b0b5  lea     rcx, [rsp+740h+var_700]
0x14005b0ba  call    cs:__imp_??YCString@@QEAAAEBV0@AEBV0@@Z; CString::operator+=(CString const &)
0x14005b0c0  xor     edx, edx
0x14005b0c2  lea     rcx, [rsp+740h+var_700]
0x14005b0c7  call    cs:__imp_??YCString@@QEAAAEBV0@G@Z; CString::operator+=(ushort)
0x14005b0cd  lea     rdx, asc_1401123B8; "*.*"
0x14005b0d4  lea     rcx, [rsp+740h+var_700]
0x14005b0d9  call    cs:__imp_??YCString@@QEAAAEBV0@PEBG@Z; CString::operator+=(ushort const *)
0x14005b0df  xor     edx, edx
0x14005b0e1  lea     rcx, [rsp+740h+var_700]
0x14005b0e6  call    cs:__imp_??YCString@@QEAAAEBV0@G@Z; CString::operator+=(ushort)
0x14005b0ec  inc     [rbp+640h+var_610.nMaxCustFilter]
0x14005b0ef  mov     rax, [rsp+740h+var_700]
0x14005b0f4  mov     [rbp+640h+var_610.lpstrFilter], rax
0x14005b0f8  mov     rax, [rsp+740h+var_6E0]
0x14005b0fd  mov     [rbp+640h+var_610.lpstrTitle], rax
0x14005b104  mov     ebx, 104h
0x14005b109  mov     edx, ebx
0x14005b10b  mov     rcx, r12
0x14005b10e  call    cs:__imp_?GetBuffer@CString@@QEAAPEAGH@Z; CString::GetBuffer(int)
0x14005b114  mov     [rbp+640h+var_610.lpstrFile], rax
0x14005b118  lea     rdx, [rbp+640h+Buffer]; lpBuffer
0x14005b11f  mov     ecx, ebx; nBufferLength
0x14005b121  call    cs:__imp_GetCurrentDirectoryW
0x14005b127  lea     rax, [rbp+640h+Buffer]
0x14005b12e  mov     [rbp+640h+var_610.lpstrInitialDir], rax
0x14005b135  lea     rcx, [rsp+740h+var_6D0]; this
0x14005b13a  call    ?DoModal@CFileDialogEx@@UEAA_JXZ; CFileDialogEx::DoModal(void)
0x14005b13f  xor     ebx, ebx
0x14005b141  cmp     rax, 1
0x14005b145  setz    bl
0x14005b148  or      edx, 0FFFFFFFFh
0x14005b14b  mov     rcx, r12
0x14005b14e  call    cs:__imp_?ReleaseBuffer@CString@@QEAAXH@Z; CString::ReleaseBuffer(int)
0x14005b154  nop
0x14005b155  lea     rcx, [rsp+740h+var_6F0]
0x14005b15a  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x14005b160  nop
0x14005b161  lea     rcx, [rsp+740h+var_6E8]
0x14005b166  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x14005b16c  nop
0x14005b16d  lea     rcx, [rsp+740h+var_700]
0x14005b172  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x14005b178  nop
0x14005b179  lea     rcx, [rsp+740h+var_6E0]
0x14005b17e  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x14005b184  nop
0x14005b185  lea     rcx, [rsp+740h+var_6D0]; this
0x14005b18a  call    ??1CFileDialog@@UEAA@XZ; CFileDialog::~CFileDialog(void)
0x14005b18f  mov     eax, ebx
0x14005b191  mov     rcx, [rbp+640h+var_40]
0x14005b198  xor     rcx, rsp; StackCookie
0x14005b19b  call    __security_check_cookie
0x14005b1a0  add     rsp, 710h
0x14005b1a7  pop     r15
0x14005b1a9  pop     r14
0x14005b1ab  pop     r12
0x14005b1ad  pop     rdi
0x14005b1ae  pop     rsi
0x14005b1af  pop     rbx
0x14005b1b0  pop     rbp
0x14005b1b1  retn
```
