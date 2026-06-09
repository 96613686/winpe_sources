# CFileFind::FindFile(wchar_t const *,ulong)

- ea: `0x180233990`
- end: `0x180233c6b`
- name: `?FindFile@CFileFind@@UEAAHPEB_WK@Z`
- size: `731`
- prototype: `int __fastcall(CFileFind *this, const wchar_t *pstrName, unsigned int dwUnused)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x1800027e0`
- `0x180003230`
- `0x1800033dc`
- `0x180231d10`
- `0x180231d70`
- `0x180233920`
- `0x180233990`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180233af5`
- `KERNEL32!GetLastError` at `0x180233af5`
- `KERNEL32!SetLastError` at `0x180233aa1`
- `KERNEL32!SetLastError` at `0x180233aa1`
- `KERNEL32!GetProcAddress` at `0x180233a5a`
- `KERNEL32!GetProcAddress` at `0x180233a5a`
- `KERNEL32!GetModuleHandleW` at `0x180233a41`
- `KERNEL32!GetModuleHandleW` at `0x180233a41`
- `KERNEL32!FindFirstFileW` at `0x180233ae6`
- `KERNEL32!FindFirstFileW` at `0x180233ae6`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180233a8d`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180233a8d`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180233c16`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180233c16`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1802339f7`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x1802339f7`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x180233bf1`
- `api-ms-win-crt-filesystem-l1-1-0!_wmakepath_s` at `0x180233bf1`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x180233bbb`
- `api-ms-win-crt-filesystem-l1-1-0!_wsplitpath_s` at `0x180233bbb`
- `api-ms-win-crt-filesystem-l1-1-0!_wfullpath` at `0x180233b56`
- `api-ms-win-crt-filesystem-l1-1-0!_wfullpath` at `0x180233b56`

## string_xrefs

- `0x180233a3a`: `kernel32.dll`

## pseudocode

```c
__int64 __fastcall CFileFind::FindFile(CFileFind *this, const wchar_t *pstrName, unsigned int dwUnused)
{
  wchar_t *v5; // rax
  errno_t v6; // eax
  ATL::CAtlTransactionManager *m_pTM; // rbx
  void *m_pNextInfo; // rbp
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  __int64 FirstFileW; // rax
  DWORD v12; // ecx
  __int64 result; // rax
  DWORD LastError; // ebx
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *p_m_strRoot; // rbx
  wchar_t *m_pszData; // rbp
  errno_t v17; // eax
  errno_t v18; // eax
  int v19; // eax
  __int64 v20; // rdx
  wchar_t strDrive[8]; // [rsp+50h] [rbp-248h] BYREF
  wchar_t strDir[256]; // [rsp+60h] [rbp-238h] BYREF

  CFileFind::Close(this);
  if ( pstrName )
  {
    if ( wcslen(pstrName) >= 0x104 )
    {
      v12 = 160;
LABEL_14:
      SetLastError(v12);
      return 0;
    }
  }
  else
  {
    pstrName = L"*.*";
  }
  v5 = (wchar_t *)operator new(0x250u);
  this->m_pNextInfo = v5;
  v6 = wcscpy_s(v5 + 22, 0x104u, pstrName);
  if ( v6 )
  {
    if ( v6 == 12 )
      AfxThrowMemoryException();
    if ( v6 != 80 )
      AfxThrowInvalidArgException();
  }
  m_pTM = this->m_pTM;
  m_pNextInfo = this->m_pNextInfo;
  if ( m_pTM )
  {
    if ( !m_pNextInfo )
      goto LABEL_16;
    if ( m_pTM->m_hTransaction )
    {
      ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
      if ( ModuleHandleW )
      {
        ProcAddress = GetProcAddress(ModuleHandleW, "FindFirstFileTransactedW");
        if ( ProcAddress )
        {
          FirstFileW = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, void *, _QWORD, _QWORD, _DWORD, void *))ProcAddress)(
                         pstrName,
                         0,
                         m_pNextInfo,
                         0,
                         0,
                         0,
                         m_pTM->m_hTransaction);
          goto LABEL_18;
        }
      }
      goto LABEL_16;
    }
    if ( !m_pTM->m_bFallback )
    {
LABEL_16:
      FirstFileW = -1;
      goto LABEL_18;
    }
  }
  FirstFileW = (__int64)FindFirstFileW(pstrName, (LPWIN32_FIND_DATAW)this->m_pNextInfo);
LABEL_18:
  this->m_hContext = (void *)FirstFileW;
  if ( FirstFileW == -1 )
  {
    LastError = GetLastError();
    CFileFind::Close(this);
    v12 = LastError;
    goto LABEL_14;
  }
  p_m_strRoot = &this->m_strRoot;
  if ( ((*((_DWORD *)this->m_strRoot.m_pszData - 3) - 260) | (1 - *((_DWORD *)this->m_strRoot.m_pszData - 2))) < 0 )
    ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(&this->m_strRoot, 260);
  m_pszData = p_m_strRoot->m_pszData;
  if ( *((int *)p_m_strRoot->m_pszData - 3) < 260 )
LABEL_38:
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)m_pszData - 4) = 260;
  p_m_strRoot->m_pszData[260] = 0;
  if ( !_wfullpath(m_pszData, pstrName, 0x104u) )
  {
    if ( *((int *)p_m_strRoot->m_pszData - 3) >= 0 )
    {
      *((_DWORD *)p_m_strRoot->m_pszData - 4) = 0;
      *p_m_strRoot->m_pszData = 0;
      CFileFind::Close(this);
      v12 = 123;
      goto LABEL_14;
    }
    goto LABEL_38;
  }
  v17 = _wsplitpath_s(m_pszData, strDrive, 3u, strDir, 0x100u, 0, 0, 0, 0);
  if ( v17 )
  {
    if ( v17 == 12 )
      goto LABEL_42;
    if ( v17 != 80 )
      goto LABEL_41;
  }
  v18 = _wmakepath_s(m_pszData, 0x104u, strDrive, strDir, 0, 0);
  if ( !v18 )
    goto LABEL_32;
  if ( v18 == 12 )
LABEL_42:
    AfxThrowMemoryException();
  if ( v18 != 80 )
LABEL_41:
    AfxThrowInvalidArgException();
LABEL_32:
  if ( p_m_strRoot->m_pszData )
  {
    v19 = wcsnlen(p_m_strRoot->m_pszData, *((int *)p_m_strRoot->m_pszData - 3));
    if ( v19 < 0 )
      goto LABEL_37;
  }
  else
  {
    v19 = 0;
  }
  if ( v19 > *((_DWORD *)p_m_strRoot->m_pszData - 3) )
LABEL_37:
    ATL::AtlThrowImpl(-2147024809);
  *((_DWORD *)p_m_strRoot->m_pszData - 4) = v19;
  v20 = (unsigned int)v19;
  result = 1;
  p_m_strRoot->m_pszData[v20] = 0;
  return result;
}

```

## disassembly

```asm
0x180233990  mov     [rsp+arg_10], rbx
0x180233995  mov     [rsp+arg_18], rbp
0x18023399a  push    rsi
0x18023399b  push    rdi
0x18023399c  push    r12
0x18023399e  push    r14
0x1802339a0  push    r15
0x1802339a2  sub     rsp, 270h
0x1802339a9  mov     rax, cs:__security_cookie
0x1802339b0  xor     rax, rsp
0x1802339b3  mov     [rsp+298h+var_38], rax
0x1802339bb  mov     rsi, pstrName
0x1802339be  mov     rdi, this
0x1802339c1  call    ?Close@CFileFind@@QEAAXXZ; CFileFind::Close(void)
0x1802339c6  xor     r14d, r14d
0x1802339c9  mov     r15d, 104h
0x1802339cf  test    rsi, rsi
0x1802339d2  jnz     loc_180233A8A
0x1802339d8  lea     rsi, Path; "*.*"
0x1802339df  mov     ecx, 250h; nSize
0x1802339e4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802339e9  mov     r8, rsi; Source
0x1802339ec  mov     [rdi+10h], rax
0x1802339f0  mov     pstrName, r15; SizeInWords
0x1802339f3  lea     this, [rax+2Ch]; Destination
0x1802339f7  call    cs:__imp_wcscpy_s
0x1802339fd  test    eax, eax
0x1802339ff  jz      short loc_180233A13
0x180233a01  cmp     eax, 0Ch
0x180233a04  jz      loc_180233C59
0x180233a0a  cmp     eax, 50h ; 'P'
0x180233a0d  jnz     loc_180233C53
0x180233a13  mov     rbx, [rdi+30h]
0x180233a17  or      r12, 0FFFFFFFFFFFFFFFFh
0x180233a1b  mov     rbp, [rdi+10h]
0x180233a1f  test    rbx, rbx
0x180233a22  jz      loc_180233AE0
0x180233a28  test    rbp, rbp
0x180233a2b  jz      loc_180233ADB
0x180233a31  cmp     [rbx], r14
0x180233a34  jz      loc_180233AD5
0x180233a3a  lea     this, aKernel32Dll_0; "kernel32.dll"
0x180233a41  call    cs:__imp_GetModuleHandleW
0x180233a47  test    rax, rax
0x180233a4a  jz      loc_180233ADB
0x180233a50  lea     pstrName, aFindfirstfilet; "FindFirstFileTransactedW"
0x180233a57  mov     this, rax; hModule
0x180233a5a  call    cs:__imp_GetProcAddress
0x180233a60  test    rax, rax
0x180233a63  jz      short loc_180233ADB
0x180233a65  mov     this, [rbx]
0x180233a68  xor     r9d, r9d
0x180233a6b  mov     [rsp+298h+FilenameCount], this
0x180233a70  mov     r8, rbp
0x180233a73  mov     dword ptr [rsp+298h+Filename], r14d
0x180233a78  mov     this, rsi
0x180233a7b  xor     edx, edx
0x180233a7d  mov     [rsp+298h+DirCount], r14
0x180233a82  call    cs:__guard_dispatch_icall_fptr
0x180233a88  jmp     short loc_180233AEC
0x180233a8a  mov     this, rsi; String
0x180233a8d  call    cs:__imp_wcslen
0x180233a93  cmp     rax, r15
0x180233a96  jb      loc_1802339DF
0x180233a9c  mov     ecx, 0A0h; dwErrCode
0x180233aa1  call    cs:__imp_SetLastError
0x180233aa7  xor     eax, eax
0x180233aa9  mov     this, [rsp+298h+var_38]
0x180233ab1  xor     this, rsp; StackCookie
0x180233ab4  call    __security_check_cookie
0x180233ab9  lea     r11, [rsp+298h+var_28]
0x180233ac1  mov     rbx, [r11+40h]
0x180233ac5  mov     rbp, [r11+48h]
0x180233ac9  mov     rsp, r11
0x180233acc  pop     r15
0x180233ace  pop     r14
0x180233ad0  pop     r12
0x180233ad2  pop     rdi
0x180233ad3  pop     rsi
0x180233ad4  retn
0x180233ad5  cmp     [rbx+8], r14d
0x180233ad9  jnz     short loc_180233AE0
0x180233adb  mov     rax, r12
0x180233ade  jmp     short loc_180233AEC
0x180233ae0  mov     pstrName, rbp; lpFindFileData
0x180233ae3  mov     this, rsi; lpFileName
0x180233ae6  call    cs:__imp_FindFirstFileW
0x180233aec  mov     [rdi+18h], rax
0x180233af0  cmp     rax, r12
0x180233af3  jnz     short loc_180233B09
0x180233af5  call    cs:__imp_GetLastError
0x180233afb  mov     this, rdi; this
0x180233afe  mov     ebx, eax
0x180233b00  call    ?Close@CFileFind@@QEAAXXZ; CFileFind::Close(void)
0x180233b05  mov     ecx, ebx
0x180233b07  jmp     short loc_180233AA1
0x180233b09  lea     rbx, [rdi+20h]
0x180233b0d  mov     r12d, 1
0x180233b13  mov     rax, [rbx]
0x180233b16  mov     ecx, r12d
0x180233b19  sub     ecx, [rax-8]
0x180233b1c  mov     eax, [rax-0Ch]
0x180233b1f  sub     eax, r15d
0x180233b22  or      ecx, eax
0x180233b24  jge     short loc_180233B31
0x180233b26  mov     edx, r15d; nLength
0x180233b29  mov     this, rbx; this
0x180233b2c  call    ?PrepareWrite2@?$CSimpleStringT@_W$00@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(int)
0x180233b31  mov     rbp, [rbx]
0x180233b34  cmp     [rbp-0Ch], r15d
0x180233b38  jl      loc_180233C48
0x180233b3e  mov     [rbp-10h], r15d
0x180233b42  mov     r8, r15; BufferCount
0x180233b45  mov     rax, [rbx]
0x180233b48  mov     pstrName, rsi; Path
0x180233b4b  mov     this, rbp; Buffer
0x180233b4e  mov     [rax+208h], r14w
0x180233b56  call    cs:__imp__wfullpath
0x180233b5c  test    rax, rax
0x180233b5f  jnz     short loc_180233B8B
0x180233b61  mov     rax, [rbx]
0x180233b64  cmp     [rax-0Ch], r14d
0x180233b68  jl      loc_180233C48
0x180233b6e  mov     [rax-10h], r14d
0x180233b72  mov     this, rdi; this
0x180233b75  mov     rax, [rbx]
0x180233b78  mov     [rax], r14w
0x180233b7c  call    ?Close@CFileFind@@QEAAXXZ; CFileFind::Close(void)
0x180233b81  mov     ecx, 7Bh ; '{'
0x180233b86  jmp     loc_180233AA1
0x180233b8b  mov     [rsp+298h+ExtCount], r14; ExtCount
0x180233b90  lea     r9, [rsp+298h+strDir]; Dir
0x180233b95  mov     [rsp+298h+Ext], r14; Ext
0x180233b9a  lea     pstrName, [rsp+298h+strDrive]; Drive
0x180233b9f  mov     [rsp+298h+FilenameCount], r14; FilenameCount
0x180233ba4  mov     dwUnused, 3; DriveCount
0x180233baa  mov     [rsp+298h+Filename], r14; Filename
0x180233baf  mov     this, rbp; FullPath
0x180233bb2  mov     [rsp+298h+DirCount], 100h; DirCount
0x180233bbb  call    cs:__imp__wsplitpath_s
0x180233bc1  test    eax, eax
0x180233bc3  jz      short loc_180233BD7
0x180233bc5  cmp     eax, 0Ch
0x180233bc8  jz      loc_180233C65
0x180233bce  cmp     eax, 50h ; 'P'
0x180233bd1  jnz     loc_180233C5F
0x180233bd7  mov     [rsp+298h+Filename], r14; Ext
0x180233bdc  lea     r9, [rsp+298h+strDir]; Dir
0x180233be1  lea     r8, [rsp+298h+strDrive]; Drive
0x180233be6  mov     [rsp+298h+DirCount], r14; Filename
0x180233beb  mov     pstrName, r15; BufferCount
0x180233bee  mov     this, rbp; Buffer
0x180233bf1  call    cs:__imp__wmakepath_s
0x180233bf7  test    eax, eax
0x180233bf9  jz      short loc_180233C05
0x180233bfb  cmp     eax, 0Ch
0x180233bfe  jz      short loc_180233C65
0x180233c00  cmp     eax, 50h ; 'P'
0x180233c03  jnz     short loc_180233C5F
0x180233c05  mov     this, [rbx]; Source
0x180233c08  test    this, this
0x180233c0b  jnz     short loc_180233C12
0x180233c0d  mov     eax, r14d
0x180233c10  jmp     short loc_180233C20
0x180233c12  movsxd  pstrName, dword ptr [this-0Ch]; MaxCount
0x180233c16  call    cs:__imp_wcsnlen
0x180233c1c  test    eax, eax
0x180233c1e  js      short loc_180233C3D
0x180233c20  mov     this, [rbx]
0x180233c23  cmp     eax, [this-0Ch]
0x180233c26  jg      short loc_180233C3D
0x180233c28  mov     [this-10h], eax
0x180233c2b  mov     this, [rbx]
0x180233c2e  mov     edx, eax
0x180233c30  mov     eax, r12d
0x180233c33  mov     [this+pstrName*2], r14w
0x180233c38  jmp     loc_180233AA9
0x180233c3d  mov     ecx, 80070057h; hr
0x180233c42  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180233c48  mov     ecx, 80070057h; hr
0x180233c4d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180233c53  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
0x180233c59  call    ?AfxThrowMemoryException@@YAXXZ; AfxThrowMemoryException(void)
0x180233c5f  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
0x180233c65  call    ?AfxThrowMemoryException@@YAXXZ; AfxThrowMemoryException(void)
```
