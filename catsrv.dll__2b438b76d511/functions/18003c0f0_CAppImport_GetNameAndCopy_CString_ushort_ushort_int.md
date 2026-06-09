# CAppImport::GetNameAndCopy(CString &,ushort *,ushort *,int)

- ea: `0x18003c0f0`
- end: `0x18003c2c1`
- name: `?GetNameAndCopy@CAppImport@@QEAAJAEAVCString@@PEAG1H@Z`
- size: `465`
- prototype: `__int64 __fastcall(CAppImport *__hidden this, struct CString *, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18003ac0c`
- `0x1800474b0`

## callees

- `0x18003c0f0`

## import_xrefs

- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003c192`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003c19d`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003c1a8`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003c1b3`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003c21f`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003c22a`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003c235`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003c240`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003c27b`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003c2a1`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003c192`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003c19d`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003c1a8`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003c1b3`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003c21f`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003c22a`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003c235`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003c240`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003c27b`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18003c2a1`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x18003c12a`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x18003c12a`
- `MfcSubs!??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x18003c187`
- `MfcSubs!??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x18003c1c2`
- `MfcSubs!??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x18003c214`
- `MfcSubs!??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x18003c187`
- `MfcSubs!??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x18003c1c2`
- `MfcSubs!??4CString@@QEAAAEBV0@AEBV0@@Z` at `0x18003c214`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x18003c157`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x18003c1e5`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x18003c157`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x18003c1e5`
- `MfcSubs!??0CString@@QEAA@GH@Z` at `0x18003c147`
- `MfcSubs!??0CString@@QEAA@GH@Z` at `0x18003c1d5`
- `MfcSubs!??0CString@@QEAA@GH@Z` at `0x18003c147`
- `MfcSubs!??0CString@@QEAA@GH@Z` at `0x18003c1d5`
- `MfcSubs!??H@YA?AVCString@@AEBV0@0@Z` at `0x18003c168`
- `MfcSubs!??H@YA?AVCString@@AEBV0@0@Z` at `0x18003c179`
- `MfcSubs!??H@YA?AVCString@@AEBV0@0@Z` at `0x18003c1f6`
- `MfcSubs!??H@YA?AVCString@@AEBV0@0@Z` at `0x18003c207`
- `MfcSubs!??H@YA?AVCString@@AEBV0@0@Z` at `0x18003c168`
- `MfcSubs!??H@YA?AVCString@@AEBV0@0@Z` at `0x18003c179`
- `MfcSubs!??H@YA?AVCString@@AEBV0@0@Z` at `0x18003c1f6`
- `MfcSubs!??H@YA?AVCString@@AEBV0@0@Z` at `0x18003c207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c262`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18003c258`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18003c258`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003c296`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18003c296`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003c288`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003c288`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CAppImport::GetNameAndCopy(
        const WCHAR *this,
        LPCWSTR *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        int a5)
{
  CString *v8; // rbx
  CString *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  CString *v12; // rbx
  CString *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int v16; // ebx
  DWORD FileAttributesW; // eax
  _BYTE v19[8]; // [rsp+20h] [rbp-20h] BYREF
  _BYTE v20[8]; // [rsp+28h] [rbp-18h] BYREF
  _BYTE v21[16]; // [rsp+30h] [rbp-10h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+70h] [rbp+30h] BYREF
  char v23; // [rsp+80h] [rbp+40h] BYREF

  lpExistingFileName = this;
  if ( !a3 || !a4 )
    return 2147942487LL;
  CString::CString((CString *)&lpExistingFileName);
  if ( *a3 )
  {
    v8 = CString::CString((CString *)v21, 0x5Cu, 1);
    v9 = CString::CString((CString *)v20, a3);
    v10 = operator+(v19, v9, v8);
    v11 = operator+(&v23, v10, a2);
    CString::operator=(&lpExistingFileName, v11);
    CString::~CString((CString *)&v23);
    CString::~CString((CString *)v19);
    CString::~CString((CString *)v20);
    CString::~CString((CString *)v21);
  }
  else
  {
    CString::operator=(&lpExistingFileName, a2);
  }
  v12 = CString::CString((CString *)v19, 0x5Cu, 1);
  v13 = CString::CString((CString *)v20, a4);
  v14 = operator+(v21, v13, v12);
  v15 = operator+(&v23, v14, a2);
  CString::operator=(a2, v15);
  CString::~CString((CString *)&v23);
  CString::~CString((CString *)v21);
  CString::~CString((CString *)v20);
  CString::~CString((CString *)v19);
  if ( CopyFileW(lpExistingFileName, *a2, a5 == 0) )
  {
    FileAttributesW = GetFileAttributesW(*a2);
    SetFileAttributesW(*a2, FileAttributesW & 0xFFFFFFFE);
    CString::~CString((CString *)&lpExistingFileName);
    return 0;
  }
  else
  {
    v16 = -2146368499;
    if ( GetLastError() == 5 )
      v16 = -2146368485;
    CString::~CString((CString *)&lpExistingFileName);
    return v16;
  }
}

```

## disassembly

```asm
0x18003c0f0  mov     [rsp-28h+arg_8], rbx
0x18003c0f5  mov     [rsp-28h+lpExistingFileName], rcx
0x18003c0fa  push    rbp
0x18003c0fb  push    rsi
0x18003c0fc  push    rdi
0x18003c0fd  push    r14
0x18003c0ff  push    r15
0x18003c101  mov     rbp, rsp
0x18003c104  sub     rsp, 40h
0x18003c108  mov     r14, r9
0x18003c10b  mov     rsi, r8
0x18003c10e  mov     rdi, rdx
0x18003c111  xor     r15d, r15d
0x18003c114  test    r8, r8
0x18003c117  jz      loc_18003C2AB
0x18003c11d  test    r9, r9
0x18003c120  jz      loc_18003C2AB
0x18003c126  lea     rcx, [rbp+lpExistingFileName]
0x18003c12a  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x18003c130  nop
0x18003c131  cmp     [rsi], r15w
0x18003c135  jz      loc_18003C1BB
0x18003c13b  lea     edx, [r15+5Ch]
0x18003c13f  lea     r8d, [r15+1]
0x18003c143  lea     rcx, [rbp+var_10]
0x18003c147  call    cs:__imp_??0CString@@QEAA@GH@Z; CString::CString(ushort,int)
0x18003c14d  mov     rbx, rax
0x18003c150  mov     rdx, rsi
0x18003c153  lea     rcx, [rbp+var_18]
0x18003c157  call    cs:__imp_??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x18003c15d  nop
0x18003c15e  mov     r8, rbx
0x18003c161  mov     rdx, rax
0x18003c164  lea     rcx, [rbp+var_20]
0x18003c168  call    cs:__imp_??H@YA?AVCString@@AEBV0@0@Z; operator+(CString const &,CString const &)
0x18003c16e  nop
0x18003c16f  mov     r8, rdi
0x18003c172  mov     rdx, rax
0x18003c175  lea     rcx, [rbp+arg_10]
0x18003c179  call    cs:__imp_??H@YA?AVCString@@AEBV0@0@Z; operator+(CString const &,CString const &)
0x18003c17f  nop
0x18003c180  mov     rdx, rax
0x18003c183  lea     rcx, [rbp+lpExistingFileName]
0x18003c187  call    cs:__imp_??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x18003c18d  nop
0x18003c18e  lea     rcx, [rbp+arg_10]
0x18003c192  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18003c198  nop
0x18003c199  lea     rcx, [rbp+var_20]
0x18003c19d  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18003c1a3  nop
0x18003c1a4  lea     rcx, [rbp+var_18]
0x18003c1a8  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18003c1ae  nop
0x18003c1af  lea     rcx, [rbp+var_10]
0x18003c1b3  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18003c1b9  jmp     short loc_18003C1C8
0x18003c1bb  mov     rdx, rdi
0x18003c1be  lea     rcx, [rbp+lpExistingFileName]
0x18003c1c2  call    cs:__imp_??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x18003c1c8  mov     edx, 5Ch ; '\'
0x18003c1cd  lea     r8d, [rdx-5Bh]
0x18003c1d1  lea     rcx, [rbp+var_20]
0x18003c1d5  call    cs:__imp_??0CString@@QEAA@GH@Z; CString::CString(ushort,int)
0x18003c1db  mov     rbx, rax
0x18003c1de  mov     rdx, r14
0x18003c1e1  lea     rcx, [rbp+var_18]
0x18003c1e5  call    cs:__imp_??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x18003c1eb  nop
0x18003c1ec  mov     r8, rbx
0x18003c1ef  mov     rdx, rax
0x18003c1f2  lea     rcx, [rbp+var_10]
0x18003c1f6  call    cs:__imp_??H@YA?AVCString@@AEBV0@0@Z; operator+(CString const &,CString const &)
0x18003c1fc  nop
0x18003c1fd  mov     r8, rdi
0x18003c200  mov     rdx, rax
0x18003c203  lea     rcx, [rbp+arg_10]
0x18003c207  call    cs:__imp_??H@YA?AVCString@@AEBV0@0@Z; operator+(CString const &,CString const &)
0x18003c20d  nop
0x18003c20e  mov     rdx, rax
0x18003c211  mov     rcx, rdi
0x18003c214  call    cs:__imp_??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x18003c21a  nop
0x18003c21b  lea     rcx, [rbp+arg_10]
0x18003c21f  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18003c225  nop
0x18003c226  lea     rcx, [rbp+var_10]
0x18003c22a  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18003c230  nop
0x18003c231  lea     rcx, [rbp+var_18]
0x18003c235  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18003c23b  nop
0x18003c23c  lea     rcx, [rbp+var_20]
0x18003c240  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18003c246  mov     r8d, r15d
0x18003c249  cmp     [rbp+arg_20], r15d
0x18003c24d  setz    r8b; bFailIfExists
0x18003c251  mov     rdx, [rdi]; lpNewFileName
0x18003c254  mov     rcx, [rbp+lpExistingFileName]; lpExistingFileName
0x18003c258  call    cs:__imp_CopyFileW
0x18003c25e  test    eax, eax
0x18003c260  jnz     short loc_18003C285
0x18003c262  call    cs:__imp_GetLastError
0x18003c268  nop
0x18003c269  mov     ebx, 8011040Dh
0x18003c26e  lea     ecx, [rbx+0Eh]
0x18003c271  cmp     eax, 5
0x18003c274  cmovz   ebx, ecx
0x18003c277  lea     rcx, [rbp+lpExistingFileName]
0x18003c27b  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18003c281  mov     eax, ebx
0x18003c283  jmp     short loc_18003C2B0
0x18003c285  mov     rcx, [rdi]; lpFileName
0x18003c288  call    cs:__imp_GetFileAttributesW
0x18003c28e  and     eax, 0FFFFFFFEh
0x18003c291  mov     edx, eax; dwFileAttributes
0x18003c293  mov     rcx, [rdi]; lpFileName
0x18003c296  call    cs:__imp_SetFileAttributesW
0x18003c29c  nop
0x18003c29d  lea     rcx, [rbp+lpExistingFileName]
0x18003c2a1  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18003c2a7  xor     eax, eax
0x18003c2a9  jmp     short loc_18003C2B0
0x18003c2ab  mov     eax, 80070057h
0x18003c2b0  mov     rbx, [rsp+40h+arg_8]
0x18003c2b5  add     rsp, 40h
0x18003c2b9  pop     r15
0x18003c2bb  pop     r14
0x18003c2bd  pop     rdi
0x18003c2be  pop     rsi
0x18003c2bf  pop     rbp
0x18003c2c0  retn
```
