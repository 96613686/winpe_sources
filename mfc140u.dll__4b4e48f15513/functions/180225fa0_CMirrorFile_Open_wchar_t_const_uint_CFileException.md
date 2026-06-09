# CMirrorFile::Open(wchar_t const *,uint,CFileException *)

- ea: `0x180225fa0`
- end: `0x1802262a3`
- name: `?Open@CMirrorFile@@UEAAHPEB_WIPEAVCFileException@@@Z`
- size: `771`
- prototype: `int __fastcall(CMirrorFile *this, const wchar_t *lpszFileName, unsigned int nOpenFlags, CFileException *pError)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800027e0`
- `0x180002e40`
- `0x180003230`
- `0x1800033dc`
- `0x180003450`
- `0x180224d98`
- `0x180225fa0`
- `0x1802322a0`
- `0x1802332d0`
- `0x180236150`
- `0x180236330`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `ADVAPI32!GetFileSecurityW` at `0x180226205`
- `ADVAPI32!GetFileSecurityW` at `0x180226233`
- `ADVAPI32!GetFileSecurityW` at `0x180226205`
- `ADVAPI32!GetFileSecurityW` at `0x180226233`
- `ADVAPI32!SetFileSecurityW` at `0x180226246`
- `ADVAPI32!SetFileSecurityW` at `0x180226246`
- `KERNEL32!SetFileTime` at `0x1802261e0`
- `KERNEL32!SetFileTime` at `0x1802261e0`
- `KERNEL32!GetFileTime` at `0x1802261b4`
- `KERNEL32!GetFileTime` at `0x1802261b4`
- `KERNEL32!GetFullPathNameW` at `0x1802260ac`
- `KERNEL32!GetFullPathNameW` at `0x1802260ac`
- `KERNEL32!GetDiskFreeSpaceW` at `0x180226068`
- `KERNEL32!GetDiskFreeSpaceW` at `0x180226068`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18022624f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18022624f`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18022618c`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18022618c`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18022610f`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18022610f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall CMirrorFile::Open(
        CMirrorFile *this,
        const wchar_t *lpszFileName,
        unsigned int nOpenFlags,
        CFileException *pError)
{
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *p_m_strMirrorName; // rdi
  signed int v9; // r14d
  _FILETIME v10; // rbx
  int v11; // eax
  int v12; // eax
  void *v13; // rbx
  unsigned int dwLength; // [rsp+30h] [rbp-D0h] BYREF
  _FILETIME ftCreate; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int dwBytesPerSec; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int dwFreeClus; // [rsp+44h] [rbp-BCh] BYREF
  _FILETIME ftModify; // [rsp+48h] [rbp-B8h] BYREF
  _FILETIME ftAccess; // [rsp+50h] [rbp-B0h] BYREF
  CFileStatus status; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t szPath[264]; // [rsp+290h] [rbp+190h] BYREF

  p_m_strMirrorName = &this->m_strMirrorName;
  ATL::CSimpleStringT<wchar_t,1>::Empty(&this->m_strMirrorName);
  memset(&status, 0, 24);
  v9 = 0;
  if ( (nOpenFlags & 0x1000) == 0 || !CFile::GetStatus(lpszFileName, &status, 0) )
    goto LABEL_15;
  ftCreate = (_FILETIME)&afxStringManager.GetNilString(&afxStringManager)[1];
  AfxGetRoot(lpszFileName, (ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > *)&ftCreate);
  v10 = ftCreate;
  if ( GetDiskFreeSpaceW(*(LPCWSTR *)&ftCreate, &dwLength, &dwBytesPerSec, &dwFreeClus, (LPDWORD)&ftAccess) )
    v9 = dwFreeClus * dwBytesPerSec * dwLength;
  if ( v9 > 2 * status.m_size )
  {
    GetFullPathNameW(lpszFileName, 0x104u, szPath, (LPWSTR *)&ftModify);
    *(_WORD *)ftModify.dwLowDateTime = 0;
    if ( ((1 - *((_DWORD *)p_m_strMirrorName->m_pszData - 2)) | (*((_DWORD *)p_m_strMirrorName->m_pszData - 3) - 261)) < 0 )
      ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(p_m_strMirrorName, 261);
    AfxGetTempFileName(szPath, L"MFC", p_m_strMirrorName->m_pszData, 0x105u);
    if ( p_m_strMirrorName->m_pszData )
    {
      v11 = wcsnlen(p_m_strMirrorName->m_pszData, *((int *)p_m_strMirrorName->m_pszData - 3));
      if ( v11 < 0 )
        goto LABEL_28;
    }
    else
    {
      v11 = 0;
    }
    if ( v11 <= *((_DWORD *)p_m_strMirrorName->m_pszData - 3) )
    {
      *((_DWORD *)p_m_strMirrorName->m_pszData - 4) = v11;
      p_m_strMirrorName->m_pszData[v11] = 0;
      goto LABEL_13;
    }
LABEL_28:
    ATL::AtlThrowImpl(-2147024809);
  }
LABEL_13:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v10 - 24LL + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)&v10 - 24LL) + 8LL))(*(_QWORD *)(*(_QWORD *)&v10 - 24LL));
LABEL_15:
  if ( *((_DWORD *)p_m_strMirrorName->m_pszData - 4)
    && CFile::Open(this, p_m_strMirrorName->m_pszData, nOpenFlags, pError) )
  {
    if ( lpszFileName )
      v12 = wcslen(lpszFileName);
    else
      v12 = 0;
    ATL::CSimpleStringT<wchar_t,1>::SetString(&this->m_strFileName, lpszFileName, v12);
    if ( GetFileTime(this->m_hFile, &ftCreate, &ftAccess, &ftModify) )
    {
      AfxTimeToFileTime(&status.m_ctime, &ftCreate);
      SetFileTime(this->m_hFile, &ftCreate, &ftAccess, &ftModify);
    }
    dwLength = 0;
    if ( GetFileSecurityW(lpszFileName, 4u, 0, 0, &dwLength) )
    {
      v13 = operator new(dwLength);
      if ( GetFileSecurityW(lpszFileName, 4u, v13, dwLength, &dwLength) )
        SetFileSecurityW(p_m_strMirrorName->m_pszData, 4u, v13);
      free(v13);
    }
    return 1;
  }
  else
  {
    ATL::CSimpleStringT<wchar_t,1>::Empty(p_m_strMirrorName);
    return CFile::Open(this, lpszFileName, nOpenFlags, pError);
  }
}

```

## disassembly

```asm
0x180225fa0  push    rbp
0x180225fa2  push    rbx
0x180225fa3  push    rsi
0x180225fa4  push    rdi
0x180225fa5  push    r12
0x180225fa7  push    r13
0x180225fa9  push    r14
0x180225fab  push    r15
0x180225fad  lea     rbp, [rsp-3B8h]
0x180225fb5  sub     rsp, 4B8h
0x180225fbc  mov     rax, cs:__security_cookie
0x180225fc3  xor     rax, rsp
0x180225fc6  mov     [rbp+3F0h+var_50], rax
0x180225fcd  mov     r13, pError
0x180225fd0  mov     r12d, nOpenFlags
0x180225fd3  mov     rsi, lpszFileName
0x180225fd6  mov     r15, this
0x180225fd9  lea     rdi, [this+28h]
0x180225fdd  mov     this, rdi; this
0x180225fe0  call    ?Empty@?$CSimpleStringT@_W$00@ATL@@QEAAXXZ; ATL::CSimpleStringT<wchar_t,1>::Empty(void)
0x180225fe5  xorps   xmm0, xmm0
0x180225fe8  movdqa  xmmword ptr [rsp+4F0h+status.m_ctime.m_time], xmm0
0x180225fee  xor     r14d, r14d
0x180225ff1  mov     [rsp+4F0h+status.m_atime.m_time], r14
0x180225ff6  bt      r12d, 0Ch
0x180225ffb  jnb     loc_18022615C
0x180226001  xor     nOpenFlags, nOpenFlags; pTM
0x180226004  lea     lpszFileName, [rsp+4F0h+status]; rStatus
0x180226009  mov     this, rsi; lpszFileName
0x18022600c  call    ?GetStatus@CFile@@SAHPEB_WAEAUCFileStatus@@PEAVCAtlTransactionManager@ATL@@@Z; CFile::GetStatus(wchar_t const *,CFileStatus &,ATL::CAtlTransactionManager *)
0x180226011  test    eax, eax
0x180226013  jz      loc_18022615C
0x180226019  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x180226020  lea     this, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x180226027  mov     rax, [rax+18h]
0x18022602b  call    cs:__guard_dispatch_icall_fptr
0x180226031  add     rax, 18h
0x180226035  mov     qword ptr [rsp+4F0h+ftCreate.dwLowDateTime], rax
0x18022603a  lea     lpszFileName, [rsp+4F0h+ftCreate]; strRoot
0x18022603f  mov     this, rsi; lpszPath
0x180226042  call    ?AfxGetRoot@@YAXPEB_WAEAV?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@@Z; AfxGetRoot(wchar_t const *,ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x180226047  lea     rax, [rsp+4F0h+ftAccess]
0x18022604c  mov     [rsp+4F0h+lpTotalNumberOfClusters], rax; lpTotalNumberOfClusters
0x180226051  lea     pError, [rsp+4F0h+dwFreeClus]; lpNumberOfFreeClusters
0x180226056  lea     r8, [rsp+4F0h+dwBytesPerSec]; lpBytesPerSector
0x18022605b  lea     lpszFileName, [rsp+4F0h+dwLength]; lpSectorsPerCluster
0x180226060  mov     rbx, qword ptr [rsp+4F0h+ftCreate.dwLowDateTime]
0x180226065  mov     this, rbx; lpRootPathName
0x180226068  call    cs:__imp_GetDiskFreeSpaceW
0x18022606e  test    eax, eax
0x180226070  jz      short loc_180226083
0x180226072  mov     r14d, [rsp+4F0h+dwLength]
0x180226077  imul    r14d, [rsp+4F0h+dwBytesPerSec]
0x18022607d  imul    r14d, [rsp+4F0h+dwFreeClus]
0x180226083  mov     rax, [rsp+4F0h+status.m_size]
0x180226088  lea     this, [rax+rax]
0x18022608c  movsxd  rax, r14d
0x18022608f  cmp     rax, this
0x180226092  jbe     loc_180226138
0x180226098  lea     pError, [rsp+4F0h+ftModify]; lpFilePart
0x18022609d  lea     r8, [rbp+3F0h+szPath]; lpBuffer
0x1802260a4  mov     edx, 104h; nBufferLength
0x1802260a9  mov     this, rsi; lpFileName
0x1802260ac  call    cs:__imp_GetFullPathNameW
0x1802260b2  mov     rax, qword ptr [rsp+4F0h+ftModify.dwLowDateTime]
0x1802260b7  xor     r14d, r14d
0x1802260ba  mov     [rax], r14w
0x1802260be  mov     rax, [rdi]
0x1802260c1  lea     edx, [r14+1]
0x1802260c5  sub     edx, [rax-8]
0x1802260c8  mov     ecx, [rax-0Ch]
0x1802260cb  sub     ecx, 105h
0x1802260d1  or      ecx, edx
0x1802260d3  jge     short loc_1802260E2
0x1802260d5  mov     edx, 105h; nLength
0x1802260da  mov     this, rdi; this
0x1802260dd  call    ?PrepareWrite2@?$CSimpleStringT@_W$00@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,1>::PrepareWrite2(int)
0x1802260e2  mov     r9d, 105h; sizeOfTempName
0x1802260e8  mov     r8, [rdi]; lpszTempName
0x1802260eb  lea     lpszFileName, aMfc; "MFC"
0x1802260f2  lea     this, [rbp+3F0h+szPath]; lpszPath
0x1802260f9  call    ?AfxGetTempFileName@@YAXPEB_W0PEA_W_K@Z; AfxGetTempFileName(wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64)
0x1802260fe  mov     this, [rdi]; Source
0x180226101  test    this, this
0x180226104  jnz     short loc_18022610B
0x180226106  mov     eax, r14d
0x180226109  jmp     short loc_18022611D
0x18022610b  movsxd  lpszFileName, dword ptr [this-0Ch]; MaxCount
0x18022610f  call    cs:__imp_wcsnlen
0x180226115  test    eax, eax
0x180226117  js      loc_180226298
0x18022611d  mov     this, [rdi]
0x180226120  cmp     eax, [this-0Ch]
0x180226123  jg      loc_180226298
0x180226129  mov     [this-10h], eax
0x18022612c  mov     ecx, eax
0x18022612e  mov     rax, [rdi]
0x180226131  mov     [rax+this*2], r14w
0x180226136  jmp     short loc_18022613B
0x180226138  xor     r14d, r14d
0x18022613b  lea     lpszFileName, [rbx-18h]
0x18022613f  or      eax, 0FFFFFFFFh
0x180226142  lock xadd [lpszFileName+10h], eax
0x180226147  sub     eax, 1
0x18022614a  jg      short loc_18022615C
0x18022614c  mov     this, [lpszFileName]
0x18022614f  mov     rax, [this]
0x180226152  mov     rax, [rax+8]
0x180226156  call    cs:__guard_dispatch_icall_fptr
0x18022615c  mov     lpszFileName, [rdi]; lpszFileName
0x18022615f  cmp     [lpszFileName-10h], r14d
0x180226163  jz      loc_18022625C
0x180226169  mov     pError, r13; pException
0x18022616c  mov     nOpenFlags, r12d; nOpenFlags
0x18022616f  mov     this, r15; this
0x180226172  call    ?Open@CFile@@UEAAHPEB_WIPEAVCFileException@@@Z; CFile::Open(wchar_t const *,uint,CFileException *)
0x180226177  test    eax, eax
0x180226179  jz      loc_18022625C
0x18022617f  test    rsi, rsi
0x180226182  jnz     short loc_180226189
0x180226184  mov     eax, r14d
0x180226187  jmp     short loc_180226192
0x180226189  mov     this, rsi; String
0x18022618c  call    cs:__imp_wcslen
0x180226192  mov     nOpenFlags, eax; nLength
0x180226195  mov     lpszFileName, rsi; pszSrc
0x180226198  lea     this, [r15+18h]; this
0x18022619c  call    ?SetString@?$CSimpleStringT@_W$00@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,1>::SetString(wchar_t const *,int)
0x1802261a1  lea     pError, [rsp+4F0h+ftModify]; lpLastWriteTime
0x1802261a6  lea     r8, [rsp+4F0h+ftAccess]; lpLastAccessTime
0x1802261ab  lea     lpszFileName, [rsp+4F0h+ftCreate]; lpCreationTime
0x1802261b0  mov     this, [r15+8]; hFile
0x1802261b4  call    cs:__imp_GetFileTime
0x1802261ba  test    eax, eax
0x1802261bc  jz      short loc_1802261E6
0x1802261be  lea     lpszFileName, [rsp+4F0h+ftCreate]; pFileTime
0x1802261c3  lea     this, [rsp+4F0h+status]; time
0x1802261c8  call    ?AfxTimeToFileTime@@YAXAEBVCTime@ATL@@PEAU_FILETIME@@@Z; AfxTimeToFileTime(ATL::CTime const &,_FILETIME *)
0x1802261cd  lea     pError, [rsp+4F0h+ftModify]; lpLastWriteTime
0x1802261d2  lea     r8, [rsp+4F0h+ftAccess]; lpLastAccessTime
0x1802261d7  lea     lpszFileName, [rsp+4F0h+ftCreate]; lpCreationTime
0x1802261dc  mov     this, [r15+8]; hFile
0x1802261e0  call    cs:__imp_SetFileTime
0x1802261e6  mov     [rsp+4F0h+dwLength], r14d
0x1802261eb  lea     rax, [rsp+4F0h+dwLength]
0x1802261f0  mov     [rsp+4F0h+lpTotalNumberOfClusters], rax; lpnLengthNeeded
0x1802261f5  xor     r9d, r9d; nLength
0x1802261f8  xor     nOpenFlags, nOpenFlags; pSecurityDescriptor
0x1802261fb  lea     r15d, [pError+4]
0x1802261ff  mov     edx, r15d; RequestedInformation
0x180226202  mov     this, rsi; lpFileName
0x180226205  call    cs:__imp_GetFileSecurityW
0x18022620b  test    eax, eax
0x18022620d  jz      short loc_180226255
0x18022620f  mov     ecx, [rsp+4F0h+dwLength]; nSize
0x180226213  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180226218  mov     rbx, rax
0x18022621b  lea     rax, [rsp+4F0h+dwLength]
0x180226220  mov     [rsp+4F0h+lpTotalNumberOfClusters], rax; lpnLengthNeeded
0x180226225  mov     r9d, [rsp+4F0h+dwLength]; nLength
0x18022622a  mov     r8, rbx; pSecurityDescriptor
0x18022622d  mov     edx, r15d; RequestedInformation
0x180226230  mov     this, rsi; lpFileName
0x180226233  call    cs:__imp_GetFileSecurityW
0x180226239  test    eax, eax
0x18022623b  jz      short loc_18022624C
0x18022623d  mov     r8, rbx; pSecurityDescriptor
0x180226240  mov     edx, r15d; SecurityInformation
0x180226243  mov     this, [rdi]; lpFileName
0x180226246  call    cs:__imp_SetFileSecurityW
0x18022624c  mov     this, rbx; Block
0x18022624f  call    cs:__imp_free
0x180226255  mov     eax, 1
0x18022625a  jmp     short loc_180226275
0x18022625c  mov     this, rdi; this
0x18022625f  call    ?Empty@?$CSimpleStringT@_W$00@ATL@@QEAAXXZ; ATL::CSimpleStringT<wchar_t,1>::Empty(void)
0x180226264  mov     pError, r13; pException
0x180226267  mov     nOpenFlags, r12d; nOpenFlags
0x18022626a  mov     lpszFileName, rsi; lpszFileName
0x18022626d  mov     this, r15; this
0x180226270  call    ?Open@CFile@@UEAAHPEB_WIPEAVCFileException@@@Z; CFile::Open(wchar_t const *,uint,CFileException *)
0x180226275  mov     this, [rbp+3F0h+var_50]
0x18022627c  xor     this, rsp; StackCookie
0x18022627f  call    __security_check_cookie
0x180226284  add     rsp, 4B8h
0x18022628b  pop     r15
0x18022628d  pop     r14
0x18022628f  pop     r13
0x180226291  pop     r12
0x180226293  pop     rdi
0x180226294  pop     rsi
0x180226295  pop     rbx
0x180226296  pop     rbp
0x180226297  retn
0x180226298  mov     ecx, 80070057h; hr
0x18022629d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
