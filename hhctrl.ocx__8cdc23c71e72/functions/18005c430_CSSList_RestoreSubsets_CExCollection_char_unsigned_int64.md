# CSSList::RestoreSubsets(CExCollection *,char *,unsigned __int64)

- ea: `0x18005c430`
- end: `0x18005c755`
- name: `?RestoreSubsets@CSSList@@QEAAJPEAVCExCollection@@PEAD_K@Z`
- size: `805`
- prototype: `__int64 __fastcall(CSSList *__hidden this, struct CExCollection *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180063284`

## callees

- `0x180001728`
- `0x1800095c8`
- `0x180059ab8`
- `0x180059be4`
- `0x180059d28`
- `0x18005c430`
- `0x18005c9b0`
- `0x180060980`
- `0x1800629bc`
- `0x180062aa4`
- `0x180075c5a`
- `0x180075c90`

## import_xrefs

- `msvcrt!realloc` at `0x18005c5ec`
- `msvcrt!realloc` at `0x18005c5ec`
- `msvcrt!malloc` at `0x18005c482`
- `msvcrt!malloc` at `0x18005c482`
- `msvcrt!free` at `0x18005c562`
- `msvcrt!free` at `0x18005c6f6`
- `msvcrt!free` at `0x18005c71d`
- `msvcrt!free` at `0x18005c562`
- `msvcrt!free` at `0x18005c6f6`
- `msvcrt!free` at `0x18005c71d`
- `KERNEL32!CloseHandle` at `0x18005c726`
- `KERNEL32!CloseHandle` at `0x18005c726`
- `KERNEL32!lstrcmpiA` at `0x18005c6b2`
- `KERNEL32!lstrcmpiA` at `0x18005c6b2`
- `KERNEL32!CreateFileA` at `0x18005c4d7`
- `KERNEL32!CreateFileA` at `0x18005c512`
- `KERNEL32!CreateFileA` at `0x18005c550`
- `KERNEL32!CreateFileA` at `0x18005c4d7`
- `KERNEL32!CreateFileA` at `0x18005c512`
- `KERNEL32!CreateFileA` at `0x18005c550`
- `KERNEL32!ReadFile` at `0x18005c588`
- `KERNEL32!ReadFile` at `0x18005c5cb`
- `KERNEL32!ReadFile` at `0x18005c622`
- `KERNEL32!ReadFile` at `0x18005c588`
- `KERNEL32!ReadFile` at `0x18005c5cb`
- `KERNEL32!ReadFile` at `0x18005c622`

## pseudocode

```c
__int64 __fastcall CSSList::RestoreSubsets(struct CStructuralSubset **this, struct CExCollection *a2, char *a3)
{
  char *v6; // rbx
  const CHAR *UserCHSLocalStoragePathnameByLanguage; // rax
  HANDLE v9; // r14
  const CHAR *UserCHSLocalStoragePathname; // rax
  const CHAR *LocalStoragePathname; // rax
  unsigned int v12; // esi
  unsigned int v14; // eax
  char *v15; // rax
  CStructuralSubset *v16; // rax
  CStructuralSubset *v17; // rdi
  unsigned int v18; // r10d
  CSSList *v19; // rcx
  struct CStructuralSubset *v20; // rdx
  CSSList *v21; // rcx
  struct CStructuralSubset *v22; // rdx
  CSSList *v23; // rcx
  unsigned int v24; // [rsp+40h] [rbp-69h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-65h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+48h] [rbp-61h] BYREF
  CStructuralSubset *v27; // [rsp+60h] [rbp-49h]
  int Buffer; // [rsp+70h] [rbp-39h] BYREF
  int v29; // [rsp+78h] [rbp-31h]
  CHAR String1[64]; // [rsp+80h] [rbp-29h] BYREF

  memset_0(&Buffer, 0, 0x50u);
  v24 = 0;
  NumberOfBytesRead = 0;
  v6 = (char *)malloc(0x13Cu);
  if ( !v6 )
    return 2147500037LL;
  UserCHSLocalStoragePathnameByLanguage = CExCollection::GetUserCHSLocalStoragePathnameByLanguage(a2);
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = 0;
  v9 = CreateFileA(UserCHSLocalStoragePathnameByLanguage, 0x80000000, 0, &SecurityAttributes, 3u, 0x80u, 0);
  if ( v9 == (HANDLE)-1LL )
  {
    UserCHSLocalStoragePathname = CExCollection::GetUserCHSLocalStoragePathname(a2);
    v9 = CreateFileA(UserCHSLocalStoragePathname, 0x80000000, 0, &SecurityAttributes, 3u, 0x80u, 0);
    if ( v9 == (HANDLE)-1LL )
    {
      LocalStoragePathname = CExCollection::GetLocalStoragePathname(a2, ".chs");
      v9 = CreateFileA(LocalStoragePathname, 0x80000000, 0, &SecurityAttributes, 3u, 0x80u, 0);
      if ( v9 == (HANDLE)-1LL )
      {
        free(v6);
        return 2147500037LL;
      }
    }
  }
  v12 = -2147467259;
  if ( ReadFile(v9, &Buffer, 0x50u, &NumberOfBytesRead, 0) && Buffer == 305419897 )
  {
    while ( v29-- )
    {
      if ( !ReadFile(v9, &v24, 4u, &NumberOfBytesRead, 0) )
        goto LABEL_26;
      v14 = v24;
      if ( v24 > 0x33 )
      {
        v15 = (char *)realloc(v6, 4LL * v24 + 116);
        if ( !v15 )
        {
          free(v6);
          v6 = 0;
          goto LABEL_26;
        }
        v6 = v15;
        v14 = v24;
      }
      *(_DWORD *)v6 = v14;
      if ( !ReadFile(v9, v6 + 4, 4 * v24 + 108, &NumberOfBytesRead, 0) )
        goto LABEL_26;
      v16 = (CStructuralSubset *)operator new(0x88u);
      v27 = v16;
      if ( !v16 )
        goto LABEL_26;
      v17 = CStructuralSubset::CStructuralSubset(v16, v6 + 4);
      if ( !v17 )
        goto LABEL_26;
      *((_DWORD *)v17 + 32) = *((_DWORD *)v6 + 27) & 0xFFFFFFC7;
      StringCchCopyA((char *)v17 + 67, 0x33u, v6 + 55);
      while ( 1 )
      {
        v18 = v24;
        if ( !v24 )
          break;
        --v24;
        CStructuralSubset::AddHash(v17, *(_DWORD *)&v6[4 * v18 + 108]);
      }
      CSSList::AddSubset((CSSList *)this, v17, 0);
      if ( !lstrcmpiA(String1, (LPCSTR)v17 + 16) )
      {
        CSSList::Set(v19, v17, this + 2, 8u);
        CSSList::Set(v21, v20, this + 4, 0x10u);
        CSSList::Set(v23, v22, this + 3, 0x20u);
      }
    }
    if ( a3 )
      StringCchCopyA(a3, 0x32u, String1);
    v12 = 0;
  }
LABEL_26:
  free(v6);
  CloseHandle(v9);
  return v12;
}

```

## disassembly

```asm
0x18005c430  mov     [rsp-8+arg_18], rbx
0x18005c435  push    rbp
0x18005c436  push    rsi
0x18005c437  push    rdi
0x18005c438  push    r12
0x18005c43a  push    r13
0x18005c43c  push    r14
0x18005c43e  push    r15
0x18005c440  lea     rbp, [rsp-27h]
0x18005c445  sub     rsp, 0D0h
0x18005c44c  mov     rax, cs:__security_cookie
0x18005c453  xor     rax, rsp
0x18005c456  mov     [rbp+57h+var_40], rax
0x18005c45a  mov     rdi, rdx
0x18005c45d  mov     r15, r8
0x18005c460  xor     edx, edx; Val
0x18005c462  mov     r13, rcx
0x18005c465  lea     rcx, [rbp+57h+Buffer]; void *
0x18005c469  lea     r8d, [rdx+50h]; Size
0x18005c46d  call    memset_0
0x18005c472  xor     r12d, r12d
0x18005c475  mov     ecx, 13Ch; Size
0x18005c47a  mov     [rbp+57h+var_C0], r12d
0x18005c47e  mov     [rbp+57h+NumberOfBytesRead], r12d
0x18005c482  call    cs:__imp_malloc
0x18005c488  mov     rbx, rax
0x18005c48b  test    rax, rax
0x18005c48e  jnz     short loc_18005C49A
0x18005c490  mov     eax, 80004005h
0x18005c495  jmp     loc_18005C72E
0x18005c49a  mov     rcx, rdi; this
0x18005c49d  call    ?GetUserCHSLocalStoragePathnameByLanguage@CExCollection@@QEAAPEBDXZ; CExCollection::GetUserCHSLocalStoragePathnameByLanguage(void)
0x18005c4a2  mov     [rsp+100h+hTemplateFile], r12; hTemplateFile
0x18005c4a7  lea     r9, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18005c4ab  mov     esi, 80h
0x18005c4b0  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x18005c4b8  mov     [rsp+100h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18005c4bc  xor     r8d, r8d; dwShareMode
0x18005c4bf  mov     edx, 80000000h; dwDesiredAccess
0x18005c4c4  mov     [rsp+100h+dwCreationDisposition], 3; dwCreationDisposition
0x18005c4cc  mov     rcx, rax; lpFileName
0x18005c4cf  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], r12
0x18005c4d3  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], r12
0x18005c4d7  call    cs:__imp_CreateFileA
0x18005c4dd  mov     r14, rax
0x18005c4e0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005c4e4  jnz     loc_18005C56D
0x18005c4ea  mov     rcx, rdi; this
0x18005c4ed  call    ?GetUserCHSLocalStoragePathname@CExCollection@@QEAAPEBDXZ; CExCollection::GetUserCHSLocalStoragePathname(void)
0x18005c4f2  mov     [rsp+100h+hTemplateFile], r12; hTemplateFile
0x18005c4f7  lea     r9, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18005c4fb  mov     [rsp+100h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18005c4ff  xor     r8d, r8d; dwShareMode
0x18005c502  mov     edx, 80000000h; dwDesiredAccess
0x18005c507  mov     [rsp+100h+dwCreationDisposition], 3; dwCreationDisposition
0x18005c50f  mov     rcx, rax; lpFileName
0x18005c512  call    cs:__imp_CreateFileA
0x18005c518  mov     r14, rax
0x18005c51b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005c51f  jnz     short loc_18005C56D
0x18005c521  lea     rdx, aChs; ".chs"
0x18005c528  mov     rcx, rdi; this
0x18005c52b  call    ?GetLocalStoragePathname@CExCollection@@QEAAPEBDPEBD@Z; CExCollection::GetLocalStoragePathname(char const *)
0x18005c530  mov     [rsp+100h+hTemplateFile], r12; hTemplateFile
0x18005c535  lea     r9, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18005c539  mov     [rsp+100h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18005c53d  xor     r8d, r8d; dwShareMode
0x18005c540  mov     edx, 80000000h; dwDesiredAccess
0x18005c545  mov     [rsp+100h+dwCreationDisposition], 3; dwCreationDisposition
0x18005c54d  mov     rcx, rax; lpFileName
0x18005c550  call    cs:__imp_CreateFileA
0x18005c556  mov     r14, rax
0x18005c559  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005c55d  jnz     short loc_18005C56D
0x18005c55f  mov     rcx, rbx; Block
0x18005c562  call    cs:__imp_free
0x18005c568  jmp     loc_18005C490
0x18005c56d  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005c571  mov     qword ptr [rsp+100h+dwCreationDisposition], r12; lpOverlapped
0x18005c576  mov     r8d, 50h ; 'P'; nNumberOfBytesToRead
0x18005c57c  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x18005c580  mov     rcx, r14; hFile
0x18005c583  mov     esi, 80004005h
0x18005c588  call    cs:__imp_ReadFile
0x18005c58e  test    eax, eax
0x18005c590  jz      loc_18005C71A
0x18005c596  cmp     [rbp+57h+Buffer], 12345679h
0x18005c59d  jnz     loc_18005C71A
0x18005c5a3  mov     eax, [rbp+57h+var_88]
0x18005c5a6  mov     ecx, eax
0x18005c5a8  dec     eax
0x18005c5aa  mov     [rbp+57h+var_88], eax
0x18005c5ad  test    ecx, ecx
0x18005c5af  jz      loc_18005C701
0x18005c5b5  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005c5b9  mov     qword ptr [rsp+100h+dwCreationDisposition], r12; lpOverlapped
0x18005c5be  mov     r8d, 4; nNumberOfBytesToRead
0x18005c5c4  lea     rdx, [rbp+57h+var_C0]; lpBuffer
0x18005c5c8  mov     rcx, r14; hFile
0x18005c5cb  call    cs:__imp_ReadFile
0x18005c5d1  test    eax, eax
0x18005c5d3  jz      loc_18005C71A
0x18005c5d9  mov     eax, [rbp+57h+var_C0]
0x18005c5dc  cmp     eax, 33h ; '3'
0x18005c5df  jbe     short loc_18005C604
0x18005c5e1  lea     rdx, ds:74h[rax*4]; Size
0x18005c5e9  mov     rcx, rbx; Block
0x18005c5ec  call    cs:__imp_realloc
0x18005c5f2  mov     rdi, rax
0x18005c5f5  test    rax, rax
0x18005c5f8  jz      loc_18005C6F3
0x18005c5fe  mov     rbx, rax
0x18005c601  mov     eax, [rbp+57h+var_C0]
0x18005c604  mov     [rbx], eax
0x18005c606  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18005c60a  mov     r8d, [rbp+57h+var_C0]
0x18005c60e  lea     rdx, [rbx+4]; lpBuffer
0x18005c612  mov     rcx, r14; hFile
0x18005c615  mov     qword ptr [rsp+100h+dwCreationDisposition], r12; lpOverlapped
0x18005c61a  lea     r8d, ds:6Ch[r8*4]; nNumberOfBytesToRead
0x18005c622  call    cs:__imp_ReadFile
0x18005c628  test    eax, eax
0x18005c62a  jz      loc_18005C71A
0x18005c630  mov     ecx, 88h; Size
0x18005c635  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005c63a  mov     [rbp+57h+var_A0], rax
0x18005c63e  test    rax, rax
0x18005c641  jz      loc_18005C71A
0x18005c647  lea     rdx, [rbx+4]; char *
0x18005c64b  mov     rcx, rax; this
0x18005c64e  call    ??0CStructuralSubset@@QEAA@PEBD@Z; CStructuralSubset::CStructuralSubset(char const *)
0x18005c653  mov     rdi, rax
0x18005c656  test    rax, rax
0x18005c659  jz      loc_18005C71A
0x18005c65f  mov     eax, [rbx+6Ch]
0x18005c662  lea     r8, [rbx+37h]; char *
0x18005c666  and     eax, 0FFFFFFC7h
0x18005c669  lea     rcx, [rdi+43h]; char *
0x18005c66d  mov     edx, 33h ; '3'; unsigned __int64
0x18005c672  mov     [rdi+80h], eax
0x18005c678  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18005c67d  jmp     short loc_18005C693
0x18005c67f  dec     r10d
0x18005c682  mov     rcx, rdi; this
0x18005c685  mov     [rbp+57h+var_C0], r10d
0x18005c689  mov     edx, [rbx+r10*4+70h]; unsigned int
0x18005c68e  call    ?AddHash@CStructuralSubset@@QEAAXK@Z; CStructuralSubset::AddHash(ulong)
0x18005c693  mov     r10d, [rbp+57h+var_C0]
0x18005c697  test    r10d, r10d
0x18005c69a  jnz     short loc_18005C67F
0x18005c69c  xor     r8d, r8d; HWND
0x18005c69f  mov     rdx, rdi; struct CStructuralSubset *
0x18005c6a2  mov     rcx, r13; this
0x18005c6a5  call    ?AddSubset@CSSList@@QEAAJPEAVCStructuralSubset@@PEAUHWND__@@@Z; CSSList::AddSubset(CStructuralSubset *,HWND__ *)
0x18005c6aa  lea     rdx, [rdi+10h]; lpString2
0x18005c6ae  lea     rcx, [rbp+57h+String1]; lpString1
0x18005c6b2  call    cs:__imp_lstrcmpiA
0x18005c6b8  test    eax, eax
0x18005c6ba  jnz     loc_18005C5A3
0x18005c6c0  lea     r8, [r13+10h]; struct CStructuralSubset **
0x18005c6c4  mov     rdx, rdi; struct CStructuralSubset *
0x18005c6c7  lea     r9d, [rax+8]; unsigned int
0x18005c6cb  call    ?Set@CSSList@@AEAAXPEAVCStructuralSubset@@PEAPEAV2@K@Z; CSSList::Set(CStructuralSubset *,CStructuralSubset * *,ulong)
0x18005c6d0  mov     r9d, 10h; unsigned int
0x18005c6d6  lea     r8, [r13+20h]; struct CStructuralSubset **
0x18005c6da  call    ?Set@CSSList@@AEAAXPEAVCStructuralSubset@@PEAPEAV2@K@Z; CSSList::Set(CStructuralSubset *,CStructuralSubset * *,ulong)
0x18005c6df  mov     r9d, 20h ; ' '; unsigned int
0x18005c6e5  lea     r8, [r13+18h]; struct CStructuralSubset **
0x18005c6e9  call    ?Set@CSSList@@AEAAXPEAVCStructuralSubset@@PEAPEAV2@K@Z; CSSList::Set(CStructuralSubset *,CStructuralSubset * *,ulong)
0x18005c6ee  jmp     loc_18005C5A3
0x18005c6f3  mov     rcx, rbx; Block
0x18005c6f6  call    cs:__imp_free
0x18005c6fc  mov     rbx, rdi
0x18005c6ff  jmp     short loc_18005C71A
0x18005c701  test    r15, r15
0x18005c704  jz      short loc_18005C717
0x18005c706  lea     r8, [rbp+57h+String1]; char *
0x18005c70a  mov     edx, 32h ; '2'; unsigned __int64
0x18005c70f  mov     rcx, r15; char *
0x18005c712  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18005c717  mov     esi, r12d
0x18005c71a  mov     rcx, rbx; Block
0x18005c71d  call    cs:__imp_free
0x18005c723  mov     rcx, r14; hObject
0x18005c726  call    cs:__imp_CloseHandle
0x18005c72c  mov     eax, esi
0x18005c72e  mov     rcx, [rbp+57h+var_40]
0x18005c732  xor     rcx, rsp; StackCookie
0x18005c735  call    __security_check_cookie
0x18005c73a  mov     rbx, [rsp+100h+arg_18]
0x18005c742  add     rsp, 0D0h
0x18005c749  pop     r15
0x18005c74b  pop     r14
0x18005c74d  pop     r13
0x18005c74f  pop     r12
0x18005c751  pop     rdi
0x18005c752  pop     rsi
0x18005c753  pop     rbp
0x18005c754  retn
```
