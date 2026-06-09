# FdiCallbacks::CallbackFDINotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)

- ea: `0x18000c8e0`
- end: `0x18000ccad`
- name: `?CallbackFDINotify@FdiCallbacks@@SA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z`
- size: `973`
- prototype: `INT_PTR __fastcall(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops`

## callees

- `0x180001540`
- `0x180002e54`
- `0x180003648`
- `0x1800082b8`
- `0x1800084b4`
- `0x18000b2c0`
- `0x18000b34c`
- `0x18000b658`
- `0x18000c060`
- `0x18000c7a4`
- `0x18000c8e0`
- `0x18000ce80`
- `0x18000cee0`
- `0x18000e188`
- `0x18000e458`
- `0x18000e604`
- `0x18000e68c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc0e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000cb16`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000cbe5`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000cb16`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000cbe5`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18000caf7`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x18000caf7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x18000cadb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x18000cadb`

## pseudocode

```c
INT_PTR __fastcall FdiCallbacks::CallbackFDINotify(FDINOTIFICATIONTYPE fdint, PFDINOTIFICATION pfdin)
{
  size_t v3; // rbx
  int v4; // ecx
  int v5; // ecx
  char *psz1; // rdx
  size_t v7; // r8
  _DWORD *pv; // rdi
  int v9; // r14d
  int v11; // r14d
  _QWORD *v12; // rdi
  char *v13; // rdx
  __int64 v14; // r14
  _QWORD *v15; // rdx
  USHORT attribs; // r8
  int v17; // edx
  int v18; // ecx
  DWORD v19; // ebx
  const WCHAR *v20; // rcx
  signed int TargetPath; // eax
  const WCHAR *v22; // rcx
  CHAR *v23; // rcx
  INT_PTR v24; // rsi
  struct _FILETIME FileTime; // [rsp+30h] [rbp-71h] BYREF
  LPSTR pszFile[2]; // [rsp+38h] [rbp-69h] BYREF
  __m128i si128; // [rsp+48h] [rbp-59h]
  CHAR MultiByteStr[16]; // [rsp+58h] [rbp-49h] BYREF
  __m128i v29; // [rsp+68h] [rbp-39h]
  _OWORD v30[2]; // [rsp+78h] [rbp-29h] BYREF
  LPCWSTR v31[2]; // [rsp+98h] [rbp-9h] BYREF
  __m128i v32; // [rsp+A8h] [rbp+7h]
  LPCWSTR lpFileName[2]; // [rsp+B8h] [rbp+17h] BYREF
  __m128i v34; // [rsp+C8h] [rbp+27h]

  v3 = -1;
  v4 = fdint - 2;
  if ( v4 )
  {
    v5 = v4 - 1;
    if ( v5 )
    {
      if ( v5 != 1 )
        return 0;
      return v3;
    }
    goto LABEL_13;
  }
  psz1 = pfdin->psz1;
  *(_OWORD *)MultiByteStr = 0;
  v29 = 0;
  v7 = -1;
  do
    ++v7;
  while ( psz1[v7] );
  std::string::_Construct<1,char const *>(MultiByteStr, psz1, v7);
  v30[0] = 0;
  v30[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v30[0]) = 0;
  pv = pfdin->pv;
  v9 = pv[2];
  if ( (int)Utils::ConvertMultiByteToUnicode(MultiByteStr) < 0 )
  {
    std::wstring::~wstring((char **)v30);
    std::string::~string((char **)MultiByteStr);
    return 0;
  }
  v11 = v9 - 1;
  if ( !v11 )
  {
    if ( (unsigned int)CabContext::IsSelected(pv, v30) )
    {
      if ( (int)Utils::ValidateFilePath(v30, 1) >= 0 )
      {
        *(_OWORD *)pszFile = 0;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOBYTE(pszFile[0]) = 0;
        *(_OWORD *)v31 = 0;
        v32 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v31[0]) = 0;
        TargetPath = CabContext::GetTargetPath(pv, v30, v31);
        if ( TargetPath >= 0 )
        {
          TargetPath = Utils::ConvertUnicodeToMultiByte((LPCWCH)v31, pszFile);
          if ( TargetPath >= 0 )
          {
            v22 = (const WCHAR *)v31;
            if ( v32.m128i_i64[1] > 7uLL )
              v22 = v31[0];
            SetFileAttributesW(v22, 0x80u);
            v23 = (CHAR *)pszFile;
            if ( si128.m128i_i64[1] > 0xFuLL )
              v23 = pszFile[0];
            v24 = FdiCallbacks::CallbackFileOpen(v23, 33057, 0);
            if ( v24 != -1 )
            {
              CabContext::ToggleSelectedFile(pv, v30);
              std::wstring::~wstring((char **)v31);
              std::string::~string(pszFile);
              std::wstring::~wstring((char **)v30);
              std::string::~string((char **)MultiByteStr);
              return v24;
            }
            TargetPath = GetLastError();
            if ( TargetPath > 0 )
              TargetPath = (unsigned __int16)TargetPath | 0x80070000;
          }
        }
        pv[40] = TargetPath;
        std::wstring::~wstring((char **)v31);
        std::string::~string(pszFile);
      }
LABEL_49:
      std::wstring::~wstring((char **)v30);
      std::string::~string((char **)MultiByteStr);
      return v3;
    }
LABEL_36:
    v3 = 0;
    goto LABEL_49;
  }
  if ( v11 == 2 )
  {
    CabContext::AddSelectedFile(pv, v30, pfdin->cb);
    goto LABEL_36;
  }
  std::wstring::~wstring((char **)v30);
  std::string::~string((char **)MultiByteStr);
LABEL_13:
  FileTime = 0;
  v12 = pfdin->pv;
  v13 = pfdin->psz1;
  *(_OWORD *)pszFile = 0;
  si128 = 0;
  do
    ++v3;
  while ( v13[v3] );
  std::string::_Construct<1,char const *>(pszFile, v13, v3);
  *(_OWORD *)MultiByteStr = 0;
  v29 = _mm_load_si128((const __m128i *)&_xmm);
  *(_WORD *)MultiByteStr = 0;
  if ( (int)Utils::ConvertMultiByteToUnicode((LPCCH)pszFile) >= 0 )
  {
    *(_OWORD *)lpFileName = 0;
    v34 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(lpFileName[0]) = 0;
    v15 = v12 + 8;
    if ( lpFileName != v12 + 8 )
    {
      if ( v12[11] > 7u )
        v15 = (_QWORD *)*v15;
      std::wstring::_Assign<wchar_t>((void **)lpFileName, v15, v12[10]);
    }
    std::wstring::operator+=(lpFileName, L"\\");
    std::wstring::operator+=(lpFileName, MultiByteStr);
    attribs = pfdin->attribs;
    v14 = 1;
    v17 = attribs & 1 | 0x20;
    if ( (attribs & 0x20) == 0 )
      v17 = pfdin->attribs & 1;
    v18 = v17 | 2;
    if ( (attribs & 2) == 0 )
      v18 = v17;
    v19 = v18 | 4;
    if ( (attribs & 4) == 0 )
      v19 = v18;
    if ( !v19 )
      v19 = 128;
    if ( DosDateTimeToFileTime(pfdin->date, pfdin->time, &FileTime) )
      SetFileTime(*(HANDLE *)pfdin->hf, &FileTime, 0, &FileTime);
    FdiCallbacks::CallbackFileClose(pfdin->hf);
    v20 = (const WCHAR *)lpFileName;
    if ( v34.m128i_i64[1] > 7uLL )
      v20 = lpFileName[0];
    SetFileAttributesW(v20, v19);
    std::wstring::~wstring((char **)lpFileName);
  }
  else
  {
    v14 = 0;
  }
  std::wstring::~wstring((char **)MultiByteStr);
  std::string::~string(pszFile);
  return v14;
}

```

## disassembly

```asm
0x18000c8e0  mov     rax, rsp
0x18000c8e3  push    rbp
0x18000c8e4  push    rdi
0x18000c8e5  push    r14
0x18000c8e7  lea     rbp, [rax-5Fh]
0x18000c8eb  sub     rsp, 0E0h
0x18000c8f2  mov     [rbp+57h+var_D0], 0FFFFFFFFFFFFFFFEh
0x18000c8fa  mov     [rax+8], rbx
0x18000c8fe  mov     [rax+18h], rsi
0x18000c902  mov     rax, cs:__security_cookie
0x18000c909  xor     rax, rsp
0x18000c90c  mov     [rbp+57h+var_20], rax
0x18000c910  mov     rsi, rdx
0x18000c913  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000c917  sub     ecx, 2
0x18000c91a  jz      short loc_18000C930
0x18000c91c  sub     ecx, 1
0x18000c91f  jz      loc_18000C9CE
0x18000c925  cmp     ecx, 1
0x18000c928  jz      loc_18000CC4D
0x18000c92e  jmp     short loc_18000C9A0
0x18000c930  mov     rdx, [rdx+8]
0x18000c934  xorps   xmm0, xmm0
0x18000c937  movups  xmmword ptr [rbp+57h+MultiByteStr], xmm0
0x18000c93b  xorps   xmm1, xmm1
0x18000c93e  movdqu  [rbp+57h+var_90], xmm1
0x18000c943  mov     r8, rbx
0x18000c946  inc     r8
0x18000c949  cmp     byte ptr [rdx+r8], 0
0x18000c94e  jnz     short loc_18000C946
0x18000c950  lea     rcx, [rbp+57h+MultiByteStr]
0x18000c954  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000c959  nop
0x18000c95a  xorps   xmm0, xmm0
0x18000c95d  movups  [rbp+57h+var_80], xmm0
0x18000c961  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000c969  movdqu  [rbp+57h+var_70], xmm1
0x18000c96e  xor     eax, eax
0x18000c970  mov     word ptr [rbp+57h+var_80], ax
0x18000c974  mov     rdi, [rsi+20h]
0x18000c978  mov     r14d, [rdi+8]
0x18000c97c  lea     rdx, [rbp+57h+var_80]
0x18000c980  lea     rcx, [rbp+57h+MultiByteStr]; lpMultiByteStr
0x18000c984  call    ?ConvertMultiByteToUnicode@Utils@@SAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; Utils::ConvertMultiByteToUnicode(std::string const &,std::wstring *)
0x18000c989  test    eax, eax
0x18000c98b  jns     short loc_18000C9A7
0x18000c98d  lea     rcx, [rbp+57h+var_80]
0x18000c991  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c996  nop
0x18000c997  lea     rcx, [rbp+57h+MultiByteStr]
0x18000c99b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000c9a0  xor     eax, eax
0x18000c9a2  jmp     loc_18000CC89
0x18000c9a7  sub     r14d, 1
0x18000c9ab  jz      loc_18000CB58
0x18000c9b1  cmp     r14d, 2
0x18000c9b5  jz      loc_18000CB42
0x18000c9bb  lea     rcx, [rbp+57h+var_80]
0x18000c9bf  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c9c4  nop
0x18000c9c5  lea     rcx, [rbp+57h+MultiByteStr]
0x18000c9c9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000c9ce  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], 0
0x18000c9d6  mov     rdi, [rsi+20h]
0x18000c9da  mov     rdx, [rsi+8]
0x18000c9de  xorps   xmm0, xmm0
0x18000c9e1  movups  xmmword ptr [rbp+57h+pszFile], xmm0
0x18000c9e5  xorps   xmm1, xmm1
0x18000c9e8  movdqu  [rbp+57h+var_B0], xmm1
0x18000c9ed  inc     rbx
0x18000c9f0  cmp     byte ptr [rdx+rbx], 0
0x18000c9f4  jnz     short loc_18000C9ED
0x18000c9f6  mov     r8, rbx
0x18000c9f9  lea     rcx, [rbp+57h+pszFile]
0x18000c9fd  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000ca02  nop
0x18000ca03  xorps   xmm0, xmm0
0x18000ca06  movups  xmmword ptr [rbp+57h+MultiByteStr], xmm0
0x18000ca0a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000ca12  movdqu  [rbp+57h+var_90], xmm1
0x18000ca17  xor     eax, eax
0x18000ca19  mov     word ptr [rbp+57h+MultiByteStr], ax
0x18000ca1d  lea     rdx, [rbp+57h+MultiByteStr]
0x18000ca21  lea     rcx, [rbp+57h+pszFile]; lpMultiByteStr
0x18000ca25  call    ?ConvertMultiByteToUnicode@Utils@@SAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; Utils::ConvertMultiByteToUnicode(std::string const &,std::wstring *)
0x18000ca2a  test    eax, eax
0x18000ca2c  jns     short loc_18000CA36
0x18000ca2e  xor     r14d, r14d
0x18000ca31  jmp     loc_18000CB27
0x18000ca36  xorps   xmm0, xmm0
0x18000ca39  movups  xmmword ptr [rbp+57h+lpFileName], xmm0
0x18000ca3d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000ca45  movdqu  [rbp+57h+var_30], xmm1
0x18000ca4a  xor     eax, eax
0x18000ca4c  mov     word ptr [rbp+57h+lpFileName], ax
0x18000ca50  lea     rdx, [rdi+40h]
0x18000ca54  lea     rax, [rbp+57h+lpFileName]
0x18000ca58  cmp     rax, rdx
0x18000ca5b  jz      short loc_18000CA74
0x18000ca5d  mov     r8, [rdx+10h]
0x18000ca61  cmp     qword ptr [rdx+18h], 7
0x18000ca66  jbe     short loc_18000CA6B
0x18000ca68  mov     rdx, [rdx]
0x18000ca6b  lea     rcx, [rbp+57h+lpFileName]
0x18000ca6f  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18000ca74  lea     rdx, asc_180017CF4; "\\"
0x18000ca7b  lea     rcx, [rbp+57h+lpFileName]; Src
0x18000ca7f  call    ??Y?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator+=(wchar_t const * const)
0x18000ca84  lea     rdx, [rbp+57h+MultiByteStr]
0x18000ca88  lea     rcx, [rbp+57h+lpFileName]; Src
0x18000ca8c  call    ??Y?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x18000ca91  movzx   r8d, word ptr [rsi+34h]
0x18000ca96  mov     ecx, r8d
0x18000ca99  mov     r14d, 1
0x18000ca9f  and     ecx, r14d
0x18000caa2  mov     edx, ecx
0x18000caa4  or      edx, 20h
0x18000caa7  test    r8b, 20h
0x18000caab  cmovz   edx, ecx
0x18000caae  mov     ecx, edx
0x18000cab0  or      ecx, 2
0x18000cab3  test    r8b, 2
0x18000cab7  cmovz   ecx, edx
0x18000caba  mov     ebx, ecx
0x18000cabc  or      ebx, 4
0x18000cabf  test    r8b, 4
0x18000cac3  cmovz   ebx, ecx
0x18000cac6  lea     edx, [r14+7Fh]
0x18000caca  test    ebx, ebx
0x18000cacc  cmovz   ebx, edx
0x18000cacf  lea     r8, [rbp+57h+FileTime]; lpFileTime
0x18000cad3  movzx   edx, word ptr [rsi+32h]; wFatTime
0x18000cad7  movzx   ecx, word ptr [rsi+30h]; wFatDate
0x18000cadb  call    cs:__imp_DosDateTimeToFileTime
0x18000cae1  test    eax, eax
0x18000cae3  jz      short loc_18000CAFD
0x18000cae5  mov     rcx, [rsi+28h]
0x18000cae9  lea     r9, [rbp+57h+FileTime]; lpLastWriteTime
0x18000caed  xor     r8d, r8d; lpLastAccessTime
0x18000caf0  lea     rdx, [rbp+57h+FileTime]; lpCreationTime
0x18000caf4  mov     rcx, [rcx]; hFile
0x18000caf7  call    cs:__imp_SetFileTime
0x18000cafd  mov     rcx, [rsi+28h]; hf
0x18000cb01  call    ?CallbackFileClose@FdiCallbacks@@SAH_J@Z; FdiCallbacks::CallbackFileClose(__int64)
0x18000cb06  lea     rcx, [rbp+57h+lpFileName]
0x18000cb0a  cmp     qword ptr [rbp+57h+var_30+8], 7
0x18000cb0f  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18000cb14  mov     edx, ebx; dwFileAttributes
0x18000cb16  call    cs:__imp_SetFileAttributesW
0x18000cb1c  nop
0x18000cb1d  lea     rcx, [rbp+57h+lpFileName]
0x18000cb21  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cb26  nop
0x18000cb27  lea     rcx, [rbp+57h+MultiByteStr]
0x18000cb2b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cb30  nop
0x18000cb31  lea     rcx, [rbp+57h+pszFile]
0x18000cb35  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000cb3a  mov     rax, r14
0x18000cb3d  jmp     loc_18000CC89
0x18000cb42  movsxd  r8, dword ptr [rsi]
0x18000cb45  lea     rdx, [rbp+57h+var_80]
0x18000cb49  mov     rcx, rdi
0x18000cb4c  call    ?AddSelectedFile@CabContext@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@Z; CabContext::AddSelectedFile(std::wstring const &,unsigned __int64)
0x18000cb51  xor     ebx, ebx
0x18000cb53  jmp     loc_18000CC3A
0x18000cb58  lea     rdx, [rbp+57h+var_80]
0x18000cb5c  mov     rcx, rdi
0x18000cb5f  call    ?IsSelected@CabContext@@QEBAHAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; CabContext::IsSelected(std::wstring const &)
0x18000cb64  test    eax, eax
0x18000cb66  jz      short loc_18000CB51
0x18000cb68  mov     edx, 1
0x18000cb6d  lea     rcx, [rbp+57h+var_80]
0x18000cb71  call    ?ValidateFilePath@Utils@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z; Utils::ValidateFilePath(std::wstring const &,bool)
0x18000cb76  test    eax, eax
0x18000cb78  js      loc_18000CC3A
0x18000cb7e  xorps   xmm0, xmm0
0x18000cb81  movups  xmmword ptr [rbp+57h+pszFile], xmm0
0x18000cb85  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18000cb8d  movdqu  [rbp+57h+var_B0], xmm1
0x18000cb92  mov     byte ptr [rbp+57h+pszFile], 0
0x18000cb96  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18000cb9a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000cba2  movdqu  [rbp+57h+var_50], xmm1
0x18000cba7  xor     eax, eax
0x18000cba9  mov     word ptr [rbp+57h+var_60], ax
0x18000cbad  lea     r8, [rbp+57h+var_60]
0x18000cbb1  lea     rdx, [rbp+57h+var_80]
0x18000cbb5  mov     rcx, rdi
0x18000cbb8  call    ?GetTargetPath@CabContext@@QEBAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAV23@@Z; CabContext::GetTargetPath(std::wstring const &,std::wstring *)
0x18000cbbd  test    eax, eax
0x18000cbbf  js      short loc_18000CC20
0x18000cbc1  lea     rdx, [rbp+57h+pszFile]; void *
0x18000cbc5  lea     rcx, [rbp+57h+var_60]; lpWideCharStr
0x18000cbc9  call    ?ConvertUnicodeToMultiByte@Utils@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; Utils::ConvertUnicodeToMultiByte(std::wstring const &,std::string *)
0x18000cbce  test    eax, eax
0x18000cbd0  js      short loc_18000CC20
0x18000cbd2  lea     rcx, [rbp+57h+var_60]
0x18000cbd6  cmp     qword ptr [rbp+57h+var_50+8], 7
0x18000cbdb  cmova   rcx, [rbp+57h+var_60]; lpFileName
0x18000cbe0  mov     edx, 80h; dwFileAttributes
0x18000cbe5  call    cs:__imp_SetFileAttributesW
0x18000cbeb  lea     rcx, [rbp+57h+pszFile]
0x18000cbef  cmp     qword ptr [rbp+57h+var_B0+8], 0Fh
0x18000cbf4  cmova   rcx, [rbp+57h+pszFile]; pszFile
0x18000cbf9  xor     r8d, r8d; pmode
0x18000cbfc  mov     edx, 8121h; oflag
0x18000cc01  call    ?CallbackFileOpen@FdiCallbacks@@SA_JPEADHH@Z; FdiCallbacks::CallbackFileOpen(char *,int,int)
0x18000cc06  mov     rsi, rax
0x18000cc09  cmp     rax, rbx
0x18000cc0c  jnz     short loc_18000CC52
0x18000cc0e  call    cs:__imp_GetLastError
0x18000cc14  test    eax, eax
0x18000cc16  jle     short loc_18000CC20
0x18000cc18  movzx   eax, ax
0x18000cc1b  or      eax, 80070000h
0x18000cc20  mov     [rdi+0A0h], eax
0x18000cc26  lea     rcx, [rbp+57h+var_60]
0x18000cc2a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cc2f  nop
0x18000cc30  lea     rcx, [rbp+57h+pszFile]
0x18000cc34  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000cc39  nop
0x18000cc3a  lea     rcx, [rbp+57h+var_80]
0x18000cc3e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cc43  nop
0x18000cc44  lea     rcx, [rbp+57h+MultiByteStr]
0x18000cc48  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000cc4d  mov     rax, rbx
0x18000cc50  jmp     short loc_18000CC89
0x18000cc52  lea     rdx, [rbp+57h+var_80]
0x18000cc56  mov     rcx, rdi
0x18000cc59  call    ?ToggleSelectedFile@CabContext@@QEAAHAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; CabContext::ToggleSelectedFile(std::wstring const &)
0x18000cc5e  nop
0x18000cc5f  lea     rcx, [rbp+57h+var_60]
0x18000cc63  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cc68  nop
0x18000cc69  lea     rcx, [rbp+57h+pszFile]
0x18000cc6d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000cc72  nop
0x18000cc73  lea     rcx, [rbp+57h+var_80]
0x18000cc77  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cc7c  nop
0x18000cc7d  lea     rcx, [rbp+57h+MultiByteStr]
0x18000cc81  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000cc86  mov     rax, rsi
0x18000cc89  mov     rcx, [rbp+57h+var_20]
0x18000cc8d  xor     rcx, rsp; StackCookie
0x18000cc90  call    __security_check_cookie
0x18000cc95  lea     r11, [rsp+0F0h+var_10]
0x18000cc9d  mov     rbx, [r11+20h]
0x18000cca1  mov     rsi, [r11+30h]
0x18000cca5  mov     rsp, r11
0x18000cca8  pop     r14
0x18000ccaa  pop     rdi
0x18000ccab  pop     rbp
0x18000ccac  retn
```
