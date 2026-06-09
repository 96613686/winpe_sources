# FheFileOperations::PerformDirectoryTreeOperation(FheFileOperations::DirectoryTreeOp,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int,int *,long *,__int64 *,IFhEngineCleanupProgressEvent *)

- ea: `0x180030b88`
- end: `0x180031224`
- name: `?PerformDirectoryTreeOperation@FheFileOperations@@YAJW4DirectoryTreeOp@1@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@HPEAHPEAJPEA_JPEAUIFhEngineCleanupProgressEvent@@@Z`
- size: `1692`
- prototype: `__int64 __fastcall(__int64, _QWORD *, int, _DWORD *, _DWORD *, _QWORD *, __int64)`
- caller_count: `3`
- callee_count: `19`
- tags: `file_ops`

## callers

- `0x180012b44`
- `0x18001b4e0`
- `0x1800228b0`

## callees

- `0x180002c24`
- `0x1800062d0`
- `0x1800077f0`
- `0x1800091a4`
- `0x180009258`
- `0x18000970c`
- `0x180009920`
- `0x18000bbb8`
- `0x18000bca8`
- `0x180012278`
- `0x180012b0c`
- `0x18001fbf0`
- `0x18001fc5c`
- `0x1800309ac`
- `0x180030b88`
- `0x180031424`
- `0x180031642`
- `0x180031680`
- `0x180034010`

## import_xrefs

- `KERNEL32!RemoveDirectoryW` at `0x180030dbe`
- `KERNEL32!RemoveDirectoryW` at `0x180030dbe`
- `KERNEL32!FindFirstFileExW` at `0x180030e69`
- `KERNEL32!FindFirstFileExW` at `0x180030e69`
- `KERNEL32!FindNextFileW` at `0x18003113e`
- `KERNEL32!FindNextFileW` at `0x18003113e`
- `KERNEL32!FindClose` at `0x1800311b4`
- `KERNEL32!FindClose` at `0x1800311e1`
- `KERNEL32!FindClose` at `0x1800311b4`
- `KERNEL32!FindClose` at `0x1800311e1`
- `KERNEL32!GetLastError` at `0x180030dd4`
- `KERNEL32!GetLastError` at `0x180030de3`
- `KERNEL32!GetLastError` at `0x180030df2`
- `KERNEL32!GetLastError` at `0x180030e96`
- `KERNEL32!GetLastError` at `0x180030ea5`
- `KERNEL32!GetLastError` at `0x180031061`
- `KERNEL32!GetLastError` at `0x18003114c`
- `KERNEL32!GetLastError` at `0x18003115b`
- `KERNEL32!GetLastError` at `0x180030dd4`
- `KERNEL32!GetLastError` at `0x180030de3`
- `KERNEL32!GetLastError` at `0x180030df2`
- `KERNEL32!GetLastError` at `0x180030e96`
- `KERNEL32!GetLastError` at `0x180030ea5`
- `KERNEL32!GetLastError` at `0x180031061`
- `KERNEL32!GetLastError` at `0x18003114c`
- `KERNEL32!GetLastError` at `0x18003115b`
- `KERNEL32!DeleteFileW` at `0x180031055`
- `KERNEL32!DeleteFileW` at `0x180031055`

## pseudocode

```c
__int64 __fastcall FheFileOperations::PerformDirectoryTreeOperation(
        __int64 a1,
        _QWORD *a2,
        int a3,
        _DWORD *a4,
        _DWORD *a5,
        _QWORD *a6,
        __int64 a7)
{
  int v10; // r14d
  signed int v11; // edi
  _QWORD *v12; // rax
  const WCHAR *v13; // rbx
  __int64 v14; // rdx
  volatile signed __int32 *v15; // rcx
  int *v16; // rsi
  volatile signed __int32 *v17; // rbx
  _QWORD *v18; // rcx
  bool v19; // si
  signed int LastError; // eax
  _QWORD *v21; // rcx
  int v22; // edx
  HANDLE FirstFile; // r15
  signed int v24; // eax
  int v25; // edx
  int v26; // edx
  const unsigned __int16 *v27; // rdx
  _QWORD *v28; // rax
  unsigned __int64 v29; // r14
  BOOL v30; // esi
  int v31; // ebx
  signed int v32; // eax
  signed int v33; // eax
  int v35; // [rsp+30h] [rbp-318h]
  LPCWSTR lpPathName; // [rsp+38h] [rbp-310h] BYREF
  LPCWSTR lpFileName; // [rsp+40h] [rbp-308h] BYREF
  __int64 v38; // [rsp+48h] [rbp-300h]
  _QWORD *v39; // [rsp+50h] [rbp-2F8h]
  __int64 v40; // [rsp+60h] [rbp-2E8h] BYREF
  __int64 v41; // [rsp+68h] [rbp-2E0h] BYREF
  __int64 v42; // [rsp+70h] [rbp-2D8h] BYREF
  _DWORD *v43; // [rsp+78h] [rbp-2D0h]
  _QWORD *v44; // [rsp+80h] [rbp-2C8h]
  __int64 v45; // [rsp+88h] [rbp-2C0h]
  __int128 v46; // [rsp+90h] [rbp-2B8h] BYREF
  __int64 v47; // [rsp+A0h] [rbp-2A8h]
  __int128 v48; // [rsp+A8h] [rbp-2A0h]
  int v49; // [rsp+B8h] [rbp-290h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+C0h] [rbp-288h] BYREF

  v39 = a2;
  v43 = a5;
  v44 = a6;
  v45 = a7;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v38 = -1;
  v10 = 0;
  v35 = 0;
  v11 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_15a774469b7338d2f0041947fb32ba59_Traceguids, *a2);
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 10;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpPathName);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::TrimRight(a2, L"\\*");
  if ( a3 )
    ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddHead(
      &v46,
      *a2);
  v12 = (_QWORD *)ATL::operator+(&lpFileName, a2, L"\\*");
  ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddHead(
    &v46,
    *v12);
  ATL::CStringData::Release((ATL::CStringData *)(lpFileName - 12));
LABEL_7:
  v13 = lpPathName;
LABEL_8:
  while ( 2 )
  {
    if ( v47 )
    {
      v14 = *(_QWORD *)ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveHead(
                         &v46,
                         &v40);
      v15 = (volatile signed __int32 *)(v14 - 24);
      v16 = (int *)(v13 - 12);
      if ( (const WCHAR *)(v14 - 24) != v13 - 12 )
      {
        if ( v16[4] >= 0 && *(_QWORD *)v15 == *(_QWORD *)v16 )
        {
          v17 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v15);
          ATL::CStringData::Release((ATL::CStringData *)v16);
          v13 = (const WCHAR *)(v17 + 6);
          lpPathName = v13;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&lpPathName, v14, *(unsigned int *)(v14 - 16));
          v13 = lpPathName;
        }
      }
      ATL::CStringData::Release((ATL::CStringData *)(v40 - 24));
      v18 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Right(
                        &lpPathName,
                        &v41);
      v19 = *(_DWORD *)(*v18 - 16LL) != 1
         || (unsigned __int16)ATL::CSimpleStringT<unsigned short,0>::operator[](v18, 0) != 42;
      ATL::CStringData::Release((ATL::CStringData *)(v41 - 24));
      if ( v19 )
      {
        if ( RemoveDirectoryW(v13) || v11 < 0 || GetLastError() == 3 || GetLastError() == 2 )
          continue;
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          continue;
        v22 = 20;
LABEL_29:
        WPP_SF_Sd(v21[2], v22, (unsigned int)&WPP_15a774469b7338d2f0041947fb32ba59_Traceguids, (_DWORD)v13, v11);
        continue;
      }
      FirstFile = FindFirstFileExW(v13, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 2u);
      v38 = (__int64)FirstFile;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::TrimRight(
        &lpPathName,
        L"*");
      if ( FirstFile == (HANDLE)-1LL )
      {
        if ( v11 < 0 || GetLastError() == 3 )
          goto LABEL_7;
        v24 = GetLastError();
        v11 = v24;
        if ( v24 > 0 )
          v11 = (unsigned __int16)v24 | 0x80070000;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_7;
        v22 = 21;
        v13 = lpPathName;
        goto LABEL_29;
      }
      while ( 1 )
      {
        if ( a4 && *a4 || v10 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_15a774469b7338d2f0041947fb32ba59_Traceguids);
          v11 = -2147023661;
          ATL::CStringData::Release((ATL::CStringData *)(lpPathName - 12));
          ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(&v46);
          FindClose(FirstFile);
          goto LABEL_87;
        }
        v25 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
          v25 = FindFileData.cFileName[1];
        if ( !v25 )
          goto LABEL_77;
        v26 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
        {
          v26 = FindFileData.cFileName[1] - 46;
          if ( FindFileData.cFileName[1] == 46 )
            v26 = FindFileData.cFileName[2];
        }
        if ( !v26 )
          goto LABEL_77;
        ATL::operator+(&lpFileName, &lpPathName, FindFileData.cFileName);
        if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
          break;
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddHead(
          &v46,
          lpFileName);
        v28 = (_QWORD *)ATL::operator+(&v42, &lpFileName, L"\\*");
        ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::AddHead(
          &v46,
          *v28);
        ATL::CStringData::Release((ATL::CStringData *)(v42 - 24));
LABEL_76:
        ATL::CStringData::Release((ATL::CStringData *)(lpFileName - 12));
LABEL_77:
        if ( !FindNextFileW(FirstFile, &FindFileData) )
        {
          if ( GetLastError() == 18 || v11 < 0 )
            goto LABEL_85;
          v33 = GetLastError();
          v11 = v33;
          if ( v33 > 0 )
            v11 = (unsigned __int16)v33 | 0x80070000;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          {
LABEL_85:
            v13 = lpPathName;
          }
          else
          {
            v13 = lpPathName;
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              24,
              (unsigned int)&WPP_15a774469b7338d2f0041947fb32ba59_Traceguids,
              (_DWORD)lpPathName,
              v11);
          }
          FindClose(FirstFile);
          v38 = -1;
          goto LABEL_8;
        }
      }
      v29 = FindFileData.nFileSizeLow + ((unsigned __int64)FindFileData.nFileSizeHigh << 32);
      if ( (FindFileData.dwFileAttributes & 1) != 0 )
      {
        v30 = 1;
        v31 = FheFileOperations::DeleteReadOnlyFile(lpFileName, v27);
      }
      else
      {
        v30 = DeleteFileW(lpFileName);
        if ( v30 )
        {
LABEL_66:
          if ( v43 )
            ++*v43;
          if ( v44 )
            *v44 += v29;
          if ( v30
            && v45
            && (*(unsigned int (__fastcall **)(__int64, unsigned __int64))(*(_QWORD *)v45 + 40LL))(v45, v29) == -2147467260 )
          {
            v10 = 1;
            v35 = 1;
            if ( a4 )
              *a4 = 1;
          }
          else
          {
            v10 = v35;
          }
          goto LABEL_76;
        }
        v32 = GetLastError();
        v31 = v32;
        if ( v32 > 0 )
          v31 = (unsigned __int16)v32 | 0x80070000;
      }
      if ( v31 <= -2147024895 || (unsigned int)(v31 + 2147024892) <= 0x7FF8FFFB )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            (unsigned int)&WPP_15a774469b7338d2f0041947fb32ba59_Traceguids,
            (_DWORD)lpFileName,
            v31);
        if ( v11 >= 0 )
          v11 = v31;
      }
      goto LABEL_66;
    }
    break;
  }
  ATL::CStringData::Release((ATL::CStringData *)(v13 - 12));
  ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(&v46);
LABEL_87:
  ATL::CStringData::Release((ATL::CStringData *)(*a2 - 24LL));
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180030b88  mov     [rsp+arg_0], rbx
0x180030b8d  mov     [rsp+arg_10], rsi
0x180030b92  push    rdi
0x180030b93  push    r12
0x180030b95  push    r13
0x180030b97  push    r14
0x180030b99  push    r15
0x180030b9b  sub     rsp, 320h
0x180030ba2  mov     rax, cs:__security_cookie
0x180030ba9  xor     rax, rsp
0x180030bac  mov     [rsp+348h+var_38], rax
0x180030bb4  mov     r13, r9
0x180030bb7  mov     ebx, r8d
0x180030bba  mov     r12, rdx
0x180030bbd  mov     [rsp+348h+var_2F8], rdx
0x180030bc2  mov     rax, [rsp+348h+arg_20]
0x180030bca  mov     [rsp+348h+var_2D0], rax
0x180030bcf  mov     rcx, [rsp+348h+arg_28]
0x180030bd7  mov     [rsp+348h+var_2C8], rcx
0x180030bdf  mov     rax, [rsp+348h+arg_30]
0x180030be7  mov     [rsp+348h+var_2C0], rax
0x180030bef  xor     edx, edx; Val
0x180030bf1  mov     r8d, 250h; Size
0x180030bf7  lea     rcx, [rsp+348h+FindFileData]; void *
0x180030bff  call    memset_0
0x180030c04  or      r15, 0FFFFFFFFFFFFFFFFh
0x180030c08  mov     [rsp+348h+var_300], r15
0x180030c0d  xor     r14d, r14d
0x180030c10  mov     [rsp+348h+var_318], r14d
0x180030c15  xor     edi, edi
0x180030c17  lea     rax, WPP_GLOBAL_Control
0x180030c1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180030c25  cmp     rcx, rax
0x180030c28  jz      short loc_180030C48
0x180030c2a  test    byte ptr [rcx+1Ch], 8
0x180030c2e  jz      short loc_180030C48
0x180030c30  lea     edx, [rdi+13h]
0x180030c33  mov     r9, [r12]
0x180030c37  lea     r8, WPP_15a774469b7338d2f0041947fb32ba59_Traceguids
0x180030c3e  mov     rcx, [rcx+10h]
0x180030c42  call    WPP_SF_S
0x180030c47  nop
0x180030c48  xorps   xmm0, xmm0
0x180030c4b  movdqu  [rsp+348h+var_2B8], xmm0
0x180030c54  mov     [rsp+348h+var_2A8], 0
0x180030c60  xorps   xmm1, xmm1
0x180030c63  movdqu  [rsp+348h+var_2A0], xmm1
0x180030c6c  mov     [rsp+348h+var_290], 0Ah
0x180030c77  lea     rcx, [rsp+348h+lpPathName]
0x180030c7c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180030c81  nop
0x180030c82  lea     rdx, asc_1800391AC; "\\*"
0x180030c89  mov     rcx, r12
0x180030c8c  call    ?TrimRight@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::TrimRight(ushort const *)
0x180030c91  test    ebx, ebx
0x180030c93  jz      short loc_180030CA6
0x180030c95  mov     rdx, [r12]
0x180030c99  lea     rcx, [rsp+348h+var_2B8]
0x180030ca1  call    ?AddHead@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddHead(ushort const *)
0x180030ca6  lea     r8, asc_1800391AC; "\\*"
0x180030cad  mov     rdx, r12
0x180030cb0  lea     rcx, [rsp+348h+lpFileName]
0x180030cb5  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x180030cba  nop
0x180030cbb  mov     rdx, [rax]
0x180030cbe  lea     rcx, [rsp+348h+var_2B8]
0x180030cc6  call    ?AddHead@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddHead(ushort const *)
0x180030ccb  nop
0x180030ccc  mov     rcx, [rsp+348h+lpFileName]
0x180030cd1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030cd5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030cda  mov     rbx, [rsp+348h+lpPathName]
0x180030cdf  cmp     [rsp+348h+var_2A8], 0
0x180030ce8  jnz     short loc_180030D07
0x180030cea  lea     rcx, [rbx-18h]; this
0x180030cee  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030cf3  nop
0x180030cf4  lea     rcx, [rsp+348h+var_2B8]
0x180030cfc  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x180030d01  nop
0x180030d02  jmp     loc_1800311D8
0x180030d07  lea     rdx, [rsp+348h+var_2E8]
0x180030d0c  lea     rcx, [rsp+348h+var_2B8]
0x180030d14  call    ?RemoveHead@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@XZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveHead(void)
0x180030d19  nop
0x180030d1a  mov     rdx, [rax]
0x180030d1d  lea     rcx, [rdx-18h]
0x180030d21  lea     rsi, [rbx-18h]
0x180030d25  cmp     rcx, rsi
0x180030d28  jz      short loc_180030D66
0x180030d2a  cmp     dword ptr [rsi+10h], 0
0x180030d2e  jl      short loc_180030D53
0x180030d30  mov     rax, [rsi]
0x180030d33  cmp     [rcx], rax
0x180030d36  jnz     short loc_180030D53
0x180030d38  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180030d3d  mov     rbx, rax
0x180030d40  mov     rcx, rsi; this
0x180030d43  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030d48  add     rbx, 18h
0x180030d4c  mov     [rsp+348h+lpPathName], rbx
0x180030d51  jmp     short loc_180030D66
0x180030d53  mov     r8d, [rdx-10h]
0x180030d57  lea     rcx, [rsp+348h+lpPathName]
0x180030d5c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180030d61  mov     rbx, [rsp+348h+lpPathName]
0x180030d66  mov     rcx, [rsp+348h+var_2E8]
0x180030d6b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030d6f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030d74  lea     rdx, [rsp+348h+var_2E0]
0x180030d79  lea     rcx, [rsp+348h+lpPathName]
0x180030d7e  call    ?Right@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Right(int)
0x180030d83  mov     rcx, rax
0x180030d86  mov     rax, [rax]
0x180030d89  cmp     dword ptr [rax-10h], 1
0x180030d8d  jnz     short loc_180030DA1
0x180030d8f  xor     edx, edx
0x180030d91  call    ??A?$CSimpleStringT@G$0A@@ATL@@QEBAGH@Z; ATL::CSimpleStringT<ushort,0>::operator[](int)
0x180030d96  cmp     ax, 2Ah ; '*'
0x180030d9a  jnz     short loc_180030DA1
0x180030d9c  xor     sil, sil
0x180030d9f  jmp     short loc_180030DA4
0x180030da1  mov     sil, 1
0x180030da4  mov     rcx, [rsp+348h+var_2E0]
0x180030da9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030dad  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030db2  mov     rcx, rbx; lpFileName
0x180030db5  test    sil, sil
0x180030db8  jz      loc_180030E49
0x180030dbe  call    cs:__imp_RemoveDirectoryW
0x180030dc4  test    eax, eax
0x180030dc6  jnz     loc_180030CDF
0x180030dcc  test    edi, edi
0x180030dce  js      loc_180030CDF
0x180030dd4  call    cs:__imp_GetLastError
0x180030dda  cmp     eax, 3
0x180030ddd  jz      loc_180030CDF
0x180030de3  call    cs:__imp_GetLastError
0x180030de9  cmp     eax, 2
0x180030dec  jz      loc_180030CDF
0x180030df2  call    cs:__imp_GetLastError
0x180030df8  mov     edi, eax
0x180030dfa  test    eax, eax
0x180030dfc  jle     short loc_180030E07
0x180030dfe  movzx   edi, ax
0x180030e01  or      edi, 80070000h
0x180030e07  mov     rcx, cs:WPP_GLOBAL_Control
0x180030e0e  lea     rax, WPP_GLOBAL_Control
0x180030e15  cmp     rcx, rax
0x180030e18  jz      loc_180030CDF
0x180030e1e  test    byte ptr [rcx+1Ch], 2
0x180030e22  jz      loc_180030CDF
0x180030e28  mov     edx, 14h
0x180030e2d  mov     dword ptr [rsp+348h+lpSearchFilter], edi
0x180030e31  mov     r9, rbx
0x180030e34  lea     r8, WPP_15a774469b7338d2f0041947fb32ba59_Traceguids
0x180030e3b  mov     rcx, [rcx+10h]
0x180030e3f  call    WPP_SF_Sd
0x180030e44  jmp     loc_180030CDF
0x180030e49  mov     [rsp+348h+dwAdditionalFlags], 2; dwAdditionalFlags
0x180030e51  mov     [rsp+348h+lpSearchFilter], 0; lpSearchFilter
0x180030e5a  xor     r9d, r9d; fSearchOp
0x180030e5d  lea     r8, [rsp+348h+FindFileData]; lpFindFileData
0x180030e65  lea     edx, [r9+1]; fInfoLevelId
0x180030e69  call    cs:__imp_FindFirstFileExW
0x180030e6f  mov     r15, rax
0x180030e72  mov     [rsp+348h+var_300], rax
0x180030e77  lea     rdx, asc_180038B98; "*"
0x180030e7e  lea     rcx, [rsp+348h+lpPathName]
0x180030e83  call    ?TrimRight@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::TrimRight(ushort const *)
0x180030e88  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180030e8c  jnz     short loc_180030EEA
0x180030e8e  test    edi, edi
0x180030e90  js      loc_180030CDA
0x180030e96  call    cs:__imp_GetLastError
0x180030e9c  cmp     eax, 3
0x180030e9f  jz      loc_180030CDA
0x180030ea5  call    cs:__imp_GetLastError
0x180030eab  mov     edi, eax
0x180030ead  test    eax, eax
0x180030eaf  jle     short loc_180030EBA
0x180030eb1  movzx   edi, ax
0x180030eb4  or      edi, 80070000h
0x180030eba  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ec1  lea     rax, WPP_GLOBAL_Control
0x180030ec8  cmp     rcx, rax
0x180030ecb  jz      loc_180030CDA
0x180030ed1  test    byte ptr [rcx+1Ch], 2
0x180030ed5  jz      loc_180030CDA
0x180030edb  mov     edx, 15h
0x180030ee0  mov     rbx, [rsp+348h+lpPathName]
0x180030ee5  jmp     loc_180030E2D
0x180030eea  test    r13, r13
0x180030eed  jz      short loc_180030EF7
0x180030eef  mov     eax, [r13+0]
0x180030ef3  test    eax, eax
0x180030ef5  jnz     short loc_180030EFC
0x180030ef7  test    r14d, r14d
0x180030efa  jz      short loc_180030F51
0x180030efc  mov     rcx, cs:WPP_GLOBAL_Control
0x180030f03  lea     rax, WPP_GLOBAL_Control
0x180030f0a  cmp     rcx, rax
0x180030f0d  jz      short loc_180030F2A
0x180030f0f  test    byte ptr [rcx+1Ch], 8
0x180030f13  jz      short loc_180030F2A
0x180030f15  mov     edx, 16h
0x180030f1a  lea     r8, WPP_15a774469b7338d2f0041947fb32ba59_Traceguids
0x180030f21  mov     rcx, [rcx+10h]
0x180030f25  call    WPP_SF_
0x180030f2a  mov     edi, 800704D3h
0x180030f2f  mov     rcx, [rsp+348h+lpPathName]
0x180030f34  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030f38  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030f3d  nop
0x180030f3e  lea     rcx, [rsp+348h+var_2B8]
0x180030f46  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x180030f4b  nop
0x180030f4c  jmp     loc_1800311DE
0x180030f51  movzx   edx, [rsp+348h+var_25C]
0x180030f59  mov     esi, 2Eh ; '.'
0x180030f5e  sub     edx, esi
0x180030f60  jnz     short loc_180030F77
0x180030f62  movzx   r8d, [rsp+348h+var_25A]
0x180030f6b  mov     edx, r8d
0x180030f6e  xor     eax, eax
0x180030f70  movzx   ecx, ax
0x180030f73  sub     edx, ecx
0x180030f75  jmp     short loc_180030F80
0x180030f77  movzx   r8d, [rsp+348h+var_25A]
0x180030f80  test    edx, edx
0x180030f82  jz      loc_180031133
0x180030f88  movzx   edx, [rsp+348h+var_25C]
0x180030f90  sub     edx, esi
0x180030f92  jnz     short loc_180030FAB
0x180030f94  movzx   edx, r8w
0x180030f98  sub     edx, esi
0x180030f9a  jnz     short loc_180030FAB
0x180030f9c  movzx   edx, [rsp+348h+var_258]
0x180030fa4  xor     eax, eax
0x180030fa6  movzx   ecx, ax
0x180030fa9  sub     edx, ecx
0x180030fab  test    edx, edx
0x180030fad  jz      loc_180031133
0x180030fb3  lea     r8, [rsp+348h+var_25C]
0x180030fbb  lea     rdx, [rsp+348h+lpPathName]
0x180030fc0  lea     rcx, [rsp+348h+lpFileName]
0x180030fc5  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x180030fca  nop
0x180030fcb  test    [rsp+348h+FindFileData], 10h
0x180030fd3  jz      short loc_180031022
0x180030fd5  mov     rdx, [rsp+348h+lpFileName]
0x180030fda  lea     rcx, [rsp+348h+var_2B8]
0x180030fe2  call    ?AddHead@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddHead(ushort const *)
0x180030fe7  lea     r8, asc_1800391AC; "\\*"
0x180030fee  lea     rdx, [rsp+348h+lpFileName]
0x180030ff3  lea     rcx, [rsp+348h+var_2D8]
0x180030ff8  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x180030ffd  nop
0x180030ffe  mov     rdx, [rax]
0x180031001  lea     rcx, [rsp+348h+var_2B8]
0x180031009  call    ?AddHead@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::AddHead(ushort const *)
0x18003100e  nop
0x18003100f  mov     rcx, [rsp+348h+var_2D8]
0x180031014  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031018  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003101d  jmp     loc_180031125
0x180031022  mov     r14d, [rsp+348h+var_26C]
0x18003102a  shl     r14, 20h
0x18003102e  mov     eax, [rsp+348h+var_268]
0x180031035  add     r14, rax
0x180031038  mov     rcx, [rsp+348h+lpFileName]; this
0x18003103d  test    [rsp+348h+FindFileData], 1
0x180031045  jz      short loc_180031055
0x180031047  mov     esi, 1
0x18003104c  call    ?DeleteReadOnlyFile@FheFileOperations@@YAJPEBG@Z; FheFileOperations::DeleteReadOnlyFile(ushort const *)
0x180031051  mov     ebx, eax
0x180031053  jmp     short loc_180031076
0x180031055  call    cs:__imp_DeleteFileW
0x18003105b  mov     esi, eax
0x18003105d  test    eax, eax
0x18003105f  jnz     short loc_1800310C7
0x180031061  call    cs:__imp_GetLastError
0x180031067  mov     ebx, eax
0x180031069  test    eax, eax
0x18003106b  jle     short loc_180031076
0x18003106d  movzx   ebx, ax
0x180031070  or      ebx, 80070000h
0x180031076  cmp     ebx, 80070001h
0x18003107c  jle     short loc_18003108B
0x18003107e  lea     eax, [rbx+7FF8FFFCh]
0x180031084  cmp     eax, 7FF8FFFBh
0x180031089  ja      short loc_1800310C7
0x18003108b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031092  lea     rax, WPP_GLOBAL_Control
0x180031099  cmp     rcx, rax
0x18003109c  jz      short loc_1800310C2
0x18003109e  test    byte ptr [rcx+1Ch], 2
0x1800310a2  jz      short loc_1800310C2
0x1800310a4  mov     edx, 17h
0x1800310a9  mov     dword ptr [rsp+348h+lpSearchFilter], ebx
  ... truncated ...
```
