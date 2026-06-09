# FheFileOperations::CopyFileWithBackoff(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,_PRIORITY_HINT const *,int,int,int,__int64 const *,int *,__int64 *,ulong *,_FILETIME *,_FILETIME *,__int64 const *,__int64 *,int &,int &,long &,__int64 *,__int64 *,void *)

- ea: `0x18002f970`
- end: `0x18003049b`
- name: `?CopyFileWithBackoff@FheFileOperations@@YAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEBW4_PRIORITY_HINT@@HHHPEB_JPEAHPEA_JPEAKPEAU_FILETIME@@624AEAH7AEAJ44PEAX@Z`
- size: `2859`
- prototype: `__int64 __fastcall(LPCWSTR *, __int64 *, __int64, int, int, int, __int64, _DWORD *, _QWORD *, _DWORD *, _QWORD *, _QWORD *, _QWORD *, _QWORD *, unsigned int *, int *, int *, _QWORD *, _QWORD *, void *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x18000e078`
- `0x180013e14`

## callees

- `0x1800062d0`
- `0x1800077f0`
- `0x180007818`
- `0x180008fa0`
- `0x180009258`
- `0x180009404`
- `0x18000baa8`
- `0x1800126f0`
- `0x1800127b0`
- `0x18002f970`
- `0x1800304a4`
- `0x18003122c`
- `0x1800314ac`
- `0x180031642`
- `0x180031680`

## import_xrefs

- `KERNEL32!SetFileAttributesW` at `0x18002fd54`
- `KERNEL32!SetFileAttributesW` at `0x18002fd54`
- `KERNEL32!PowerSetRequest` at `0x18002fe1c`
- `KERNEL32!PowerSetRequest` at `0x18002fe66`
- `KERNEL32!PowerSetRequest` at `0x18002fe1c`
- `KERNEL32!PowerSetRequest` at `0x18002fe66`
- `KERNEL32!PrivCopyFileExW` at `0x18002ff73`
- `KERNEL32!PrivCopyFileExW` at `0x18002ff73`
- `KERNEL32!PowerClearRequest` at `0x18002ffec`
- `KERNEL32!PowerClearRequest` at `0x180030038`
- `KERNEL32!PowerClearRequest` at `0x18002ffec`
- `KERNEL32!PowerClearRequest` at `0x180030038`
- `KERNEL32!GetLastError` at `0x18002fbe8`
- `KERNEL32!GetLastError` at `0x18002ff7d`
- `KERNEL32!GetLastError` at `0x1800300b5`
- `KERNEL32!GetLastError` at `0x180030455`
- `KERNEL32!GetLastError` at `0x18003047b`
- `KERNEL32!GetLastError` at `0x18002fbe8`
- `KERNEL32!GetLastError` at `0x18002ff7d`
- `KERNEL32!GetLastError` at `0x1800300b5`
- `KERNEL32!GetLastError` at `0x180030455`
- `KERNEL32!GetLastError` at `0x18003047b`
- `KERNEL32!CloseHandle` at `0x180030151`
- `KERNEL32!CloseHandle` at `0x180030151`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002feb0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002ffab`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002feb0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002ffab`
- `KERNEL32!GetFileAttributesW` at `0x18002fbdd`
- `KERNEL32!GetFileAttributesW` at `0x18002fd36`
- `KERNEL32!GetFileAttributesW` at `0x18003046c`
- `KERNEL32!GetFileAttributesW` at `0x18002fbdd`
- `KERNEL32!GetFileAttributesW` at `0x18002fd36`
- `KERNEL32!GetFileAttributesW` at `0x18003046c`
- `KERNEL32!GetCurrentThread` at `0x18003008b`
- `KERNEL32!GetCurrentThread` at `0x18003008b`
- `KERNEL32!CreateFileW` at `0x180030130`
- `KERNEL32!CreateFileW` at `0x180030130`
- `KERNEL32!DeleteFileW` at `0x18003044b`
- `KERNEL32!DeleteFileW` at `0x18003044b`
- `KERNEL32!SetThreadPriority` at `0x180030099`
- `KERNEL32!SetThreadPriority` at `0x180030099`

## string_xrefs

- `0x18002fe47`: `tempRet`
- `0x18002fe91`: `tempRet`
- `0x180030017`: `tempRet`
- `0x180030063`: `tempRet`
- `0x18003027c`: `copyContext.FileInfoValid should be valid when CopyFile succeeds`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=3
__int64 __fastcall FheFileOperations::CopyFileWithBackoff(
        LPCWSTR *a1,
        __int64 *a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        __int64 a7,
        _DWORD *a8,
        _QWORD *a9,
        _DWORD *a10,
        _QWORD *a11,
        _QWORD *a12,
        _QWORD *a13,
        _QWORD *a14,
        unsigned int *a15,
        int *a16,
        int *a17,
        _QWORD *a18,
        _QWORD *a19,
        void *a20)
{
  __int64 *v20; // r13
  LPCWSTR *v21; // rbx
  int v22; // edx
  int v23; // r8d
  unsigned int v24; // r15d
  int v25; // r12d
  unsigned int CurrentUsn; // eax
  signed int v27; // ebx
  _QWORD *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r9
  signed int LastError; // eax
  unsigned int v32; // eax
  unsigned int v33; // r12d
  __int64 v34; // rax
  int DirectoryPath; // eax
  _QWORD *v36; // rax
  char v37; // r14
  DWORD FileAttributesW; // eax
  int v39; // ebx
  HANDLE v40; // r12
  signed int v41; // eax
  unsigned int v42; // r12d
  __int64 v43; // rax
  PVOID *v44; // rcx
  HANDLE CurrentThread; // rax
  signed int v46; // eax
  HANDLE FileW; // rax
  int v48; // r8d
  int v49; // r9d
  __int64 result; // rax
  __int64 v51; // rdx
  BOOL v52; // r9d
  BOOL v53; // r15d
  int v54; // [rsp+40h] [rbp-1C8h]
  int v55; // [rsp+44h] [rbp-1C4h]
  int v56; // [rsp+48h] [rbp-1C0h]
  unsigned int v57; // [rsp+4Ch] [rbp-1BCh]
  LPCWSTR *v58; // [rsp+58h] [rbp-1B0h]
  __int64 v59; // [rsp+60h] [rbp-1A8h] BYREF
  HANDLE PowerRequest; // [rsp+68h] [rbp-1A0h]
  unsigned int v61; // [rsp+70h] [rbp-198h] BYREF
  LPCWSTR *v62; // [rsp+78h] [rbp-190h]
  __int64 *v63; // [rsp+80h] [rbp-188h]
  _DWORD *v64; // [rsp+88h] [rbp-180h]
  _QWORD *v65; // [rsp+90h] [rbp-178h]
  __int64 v66; // [rsp+98h] [rbp-170h]
  __int64 v67; // [rsp+A0h] [rbp-168h]
  _QWORD *v68; // [rsp+A8h] [rbp-160h]
  struct _FILETIME v69; // [rsp+B0h] [rbp-158h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B8h] [rbp-150h] BYREF
  int v71; // [rsp+C0h] [rbp-148h] BYREF
  __int64 v72; // [rsp+C8h] [rbp-140h]
  _QWORD *v73; // [rsp+D0h] [rbp-138h]
  _DWORD *v74; // [rsp+D8h] [rbp-130h]
  _QWORD *v75; // [rsp+E0h] [rbp-128h]
  _QWORD *v76; // [rsp+E8h] [rbp-120h]
  _QWORD *v77; // [rsp+F0h] [rbp-118h]
  _QWORD *v78; // [rsp+F8h] [rbp-110h]
  unsigned int *v79; // [rsp+100h] [rbp-108h]
  int *v80; // [rsp+108h] [rbp-100h]
  int *v81; // [rsp+110h] [rbp-F8h]
  int v82; // [rsp+120h] [rbp-E8h] BYREF
  _QWORD v83[3]; // [rsp+124h] [rbp-E4h] BYREF
  unsigned int v84; // [rsp+140h] [rbp-C8h]
  unsigned int v85; // [rsp+144h] [rbp-C4h]
  int v86; // [rsp+154h] [rbp-B4h]
  __int64 v87; // [rsp+158h] [rbp-B0h]
  int v88; // [rsp+160h] [rbp-A8h]
  __int64 v89; // [rsp+168h] [rbp-A0h]
  int v90; // [rsp+170h] [rbp-98h]
  _QWORD *v91; // [rsp+178h] [rbp-90h]
  __int64 v92; // [rsp+180h] [rbp-88h]
  int v93; // [rsp+188h] [rbp-80h]
  _DWORD *v94; // [rsp+190h] [rbp-78h]
  int v95; // [rsp+198h] [rbp-70h]
  int v96; // [rsp+19Ch] [rbp-6Ch]
  __int128 v97; // [rsp+1A0h] [rbp-68h]
  __int64 v98; // [rsp+1B0h] [rbp-58h]
  __int64 v99; // [rsp+1B8h] [rbp-50h]

  v67 = a3;
  v20 = a2;
  v21 = a1;
  v58 = a1;
  v62 = a1;
  v63 = a2;
  v72 = a3;
  v66 = a7;
  v64 = a8;
  v73 = a9;
  v74 = a10;
  v75 = a11;
  v76 = a12;
  v65 = a13;
  v77 = a14;
  v79 = a15;
  v80 = a16;
  v81 = a17;
  v68 = a18;
  v78 = a19;
  PowerRequest = a20;
  v82 = 0;
  memset_0(v83, 0, 0x9Cu);
  SystemTimeAsFileTime = 0;
  v69 = 0;
  v24 = 0;
  v57 = 0;
  v55 = 0;
  v25 = 0;
  v54 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, v23, (int)*v21, *v20);
  if ( a13 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v61,
      v21);
    CurrentUsn = FheFileOperations::ReadCurrentUsn((HANDLE)0xFFFFFFFFFFFFFFFFLL);
    v27 = CurrentUsn;
    v24 = CurrentUsn >> 31;
    v57 = CurrentUsn >> 31;
    if ( (CurrentUsn & 0x80000000) != 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_133;
      v29 = 27;
      v30 = CurrentUsn;
      goto LABEL_9;
    }
    if ( v92 != *a13 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_ii(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_15a774469b7338d2f0041947fb32ba59_Traceguids, v92, *a13);
      v27 = -2147220476;
      goto LABEL_133;
    }
    v21 = v58;
  }
  if ( GetFileAttributesW(*v21) == -1 )
  {
    LastError = GetLastError();
    v27 = LastError;
    if ( LastError > 0 )
      v27 = (unsigned __int16)LastError | 0x80070000;
    v24 |= (unsigned int)v27 >> 31;
    v57 = v24;
    if ( v27 < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_133;
      v29 = 29;
      v30 = (unsigned int)v27;
LABEL_9:
      WPP_SF_d(v28[2], v29, &WPP_15a774469b7338d2f0041947fb32ba59_Traceguids, v30);
      goto LABEL_133;
    }
  }
  v61 = v24;
  v32 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::ReverseFind(
          v20,
          92);
  v33 = v32;
  if ( v32 == -1 )
  {
    v27 = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        (int)&WPP_15a774469b7338d2f0041947fb32ba59_Traceguids,
        *v20,
        87);
    v25 = 0;
    goto LABEL_133;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v34 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
            v20,
            &v59,
            v32);
    DirectoryPath = FheFileOperations::CreateDirectoryPath(v34);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v71) )
    {
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18002FD64);
      v27 = v71;
      if ( v71 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            32,
            &WPP_15a774469b7338d2f0041947fb32ba59_Traceguids,
            (unsigned int)v71);
        v24 = v57;
        v55 = 0;
        v25 = 0;
        v54 = 0;
        v58 = v62;
        v20 = v63;
        goto LABEL_133;
      }
      v24 = v57;
      v55 = 0;
      v39 = 0;
      v58 = v62;
      v20 = v63;
      v67 = v72;
LABEL_46:
      v40 = PowerRequest;
      if ( PowerRequest != (HANDLE)-1LL )
      {
        if ( !PowerSetRequest(PowerRequest, PowerRequestSystemRequired)
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_ss(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            (int)&WPP_15a774469b7338d2f0041947fb32ba59_Traceguids,
            (int)"tempRet",
            (__int64)"PowerSetRequest(PowerRequestSystemRequired) failed");
        }
        if ( !PowerSetRequest(v40, PowerRequestExecutionRequired)
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_ss(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            34,
            (int)&WPP_15a774469b7338d2f0041947fb32ba59_Traceguids,
            (int)"tempRet",
            (__int64)"PowerSetRequest(PowerRequestExecutionRequired) failed");
        }
      }
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v86 = 0;
      v89 = v66;
      v90 = 0;
      v87 = v67;
      v88 = 2;
      v91 = v65;
      v93 = 0;
      v94 = v64;
      v95 = a6;
      v96 = 1;
      v97 = 0;
      v98 = 0;
      v99 = 0;
      v56 = PrivCopyFileExW(*v58, *v20, FheFileOperations::CopyFileProgressCallback, &v82, 0, 245760);
      v41 = GetLastError();
      v42 = v41;
      if ( v41 > 0 )
        v42 = (unsigned __int16)v41 | 0x80070000;
      if ( v86 )
        v39 = 1;
      v54 = v39;
      GetSystemTimeAsFileTime(&v69);
      if ( v68 )
      {
        v43 = *(_QWORD *)&v69 - *(_QWORD *)&SystemTimeAsFileTime;
        if ( (__int64)(*(_QWORD *)&v69 - *(_QWORD *)&SystemTimeAsFileTime) <= 0 )
          v43 = 0;
        *v68 += v43;
      }
      if ( PowerRequest == (HANDLE)-1LL )
        goto LABEL_72;
      if ( !PowerClearRequest(PowerRequest, PowerRequestSystemRequired)
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          (int)&WPP_15a774469b7338d2f0041947fb32ba59_Traceguids,
          (int)"tempRet",
          (__int64)"PowerClearRequest(PowerRequestSystemRequired) failed");
      }
      if ( PowerClearRequest(PowerRequest, PowerRequestExecutionRequired) )
        goto LABEL_72;
      v44 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_ss(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          (int)&WPP_15a774469b7338d2f0041947fb32ba59_Traceguids,
          (int)"tempRet",
          (__int64)"PowerClearRequest(PowerRequestExecutionRequired) failed");
LABEL_72:
        v44 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v88 >= 2 )
        goto LABEL_82;
      CurrentThread = GetCurrentThread();
      if ( !SetThreadPriority(CurrentThread, 0x20000) )
      {
        v44 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_81;
        v46 = GetLastError();
        if ( v46 > 0 )
          v46 = (unsigned __int16)v46 | 0x80070000;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          37,
          &WPP_15a774469b7338d2f0041947fb32ba59_Traceguids,
          (unsigned int)v46);
      }
      v44 = (PVOID *)WPP_GLOBAL_Control;
LABEL_81:
      v88 = 2;
LABEL_82:
      if ( v56 )
      {
        if ( v86 )
        {
          FileW = CreateFileW((LPCWSTR)*v20, 0x80u, 7u, 0, 3u, 0x80u, 0);
          if ( FileW != (HANDLE)-1LL )
          {
            CloseHandle(FileW);
            v27 = 0;
            goto LABEL_87;
          }
          v27 = -2147220477;
          v25 = v54;
LABEL_133:
          if ( a5 && v27 == -2147024784 && (DeleteFileW((LPCWSTR)*v20) || GetLastError() == 2) )
          {
            v48 = -1;
            goto LABEL_88;
          }
          if ( GetFileAttributesW((LPCWSTR)*v20) == -1 )
          {
            if ( GetLastError() == 2 )
              v25 = -1;
            v48 = v25;
            goto LABEL_88;
          }
LABEL_87:
          v48 = v54;
LABEL_88:
          v49 = v55;
          goto LABEL_89;
        }
        if ( v44 != &WPP_GLOBAL_Control && (*((_BYTE *)v44 + 28) & 4) != 0 )
          WPP_SF_ss(
            (int)v44[2],
            38,
            (int)&WPP_15a774469b7338d2f0041947fb32ba59_Traceguids,
            (int)"FALSE",
            (__int64)"copyContext.FileInfoValid should be valid when CopyFile succeeds");
        v27 = -2147023661;
LABEL_132:
        v25 = v54;
        goto LABEL_133;
      }
      v54 = v39;
      if ( a4 && v42 == -2147023661 && v64 && *v64 != 1 )
      {
        v27 = -2147220477;
        if ( v44 == &WPP_GLOBAL_Control || (*((_BYTE *)v44 + 28) & 8) == 0 )
          goto LABEL_124;
        v51 = 39;
LABEL_123:
        WPP_SF_(v44[2], v51, &WPP_15a774469b7338d2f0041947fb32ba59_Traceguids);
LABEL_124:
        v52 = 0;
        goto LABEL_131;
      }
      if ( v65 && v93 )
      {
        v27 = -2147220476;
        if ( v44 != &WPP_GLOBAL_Control && (*((_BYTE *)v44 + 28) & 8) != 0 )
          WPP_SF_ii(v44[2], 40, &WPP_15a774469b7338d2f0041947fb32ba59_Traceguids, v92, *v65);
        goto LABEL_124;
      }
      if ( v90 )
      {
        v27 = -2147021846;
        if ( v44 == &WPP_GLOBAL_Control || (*((_BYTE *)v44 + 28) & 8) == 0 )
          goto LABEL_124;
        v51 = 41;
        goto LABEL_123;
      }
      v27 = v42;
      if ( v44 != &WPP_GLOBAL_Control && (*((_BYTE *)v44 + 28) & 8) != 0 )
        WPP_SF_d(v44[2], 42, &WPP_15a774469b7338d2f0041947fb32ba59_Traceguids, v42);
      v52 = v42 == -2147024784;
      v53 = v42 == -2147024891 || v42 == -2147024596;
      if ( v42 == -2147018896 )
        v53 = 1;
      v24 = v61 | (v42 == -2147024873 || v42 == -2147024864 || v42 == -2147018894 || v42 == -2147018895 || v53);
LABEL_131:
      v24 |= v99;
      v49 = HIDWORD(v99) | v52;
      v55 = v49;
      if ( v27 < 0 )
        goto LABEL_132;
      v48 = v54;
LABEL_89:
      if ( v86 )
      {
        if ( v73 )
          *v73 = v85 + ((unsigned __int64)v84 << 32);
        if ( v74 )
          *v74 = v82;
        if ( v75 )
          *v75 = v83[0];
        if ( v76 )
          *v76 = v83[2];
      }
      if ( v77 )
        *v77 = v92;
      if ( v78 )
        *v78 = v98;
      *v79 = v24;
      *v80 = v49;
      *v81 = v48;
      ATL::CStringData::Release((ATL::CStringData *)(*v58 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(*v20 - 24));
      result = (unsigned int)v27;
    }
  }
  v27 = DirectoryPath;
  if ( DirectoryPath < 0 )
  {
    v55 = 1;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    {
      v37 = 0;
    }
    else
    {
      v36 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                        v20,
                        &v59,
                        v33);
      v37 = 1;
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        (int)&WPP_15a774469b7338d2f0041947fb32ba59_Traceguids,
        *v36,
        v27);
    }
    if ( (v37 & 1) != 0 )
      ATL::CStringData::Release((ATL::CStringData *)(v59 - 24));
    v25 = 0;
    goto LABEL_133;
  }
  FileAttributesW = GetFileAttributesW((LPCWSTR)*v20);
  if ( FileAttributesW != -1 && (FileAttributesW & 1) != 0 )
    SetFileAttributesW((LPCWSTR)*v20, FileAttributesW & 0xFFFFFFFE);
  v39 = 0;
  goto LABEL_46;
}

```

## disassembly

```asm
0x18002f970  mov     [rsp+arg_18], r9d
0x18002f975  push    rbx
0x18002f976  push    rsi
0x18002f977  push    rdi
0x18002f978  push    r12
0x18002f97a  push    r13
0x18002f97c  push    r14
0x18002f97e  push    r15
0x18002f980  sub     rsp, 1D0h
0x18002f987  mov     rax, cs:__security_cookie
0x18002f98e  xor     rax, rsp
0x18002f991  mov     [rsp+208h+var_48], rax
0x18002f999  mov     rax, r8
0x18002f99c  mov     [rsp+208h+var_168], rax
0x18002f9a4  mov     r13, rdx
0x18002f9a7  mov     rbx, rcx
0x18002f9aa  mov     [rsp+208h+var_1B0], rcx
0x18002f9af  mov     [rsp+208h+var_190], rcx
0x18002f9b4  mov     [rsp+208h+var_188], rdx
0x18002f9bc  mov     [rsp+208h+var_140], rax
0x18002f9c4  mov     rax, [rsp+208h+arg_30]
0x18002f9cc  mov     [rsp+208h+var_170], rax
0x18002f9d4  mov     rax, [rsp+208h+arg_38]
0x18002f9dc  mov     [rsp+208h+var_180], rax
0x18002f9e4  mov     rax, [rsp+208h+arg_40]
0x18002f9ec  mov     [rsp+208h+var_138], rax
0x18002f9f4  mov     rax, [rsp+208h+arg_48]
0x18002f9fc  mov     [rsp+208h+var_130], rax
0x18002fa04  mov     rax, [rsp+208h+arg_50]
0x18002fa0c  mov     [rsp+208h+var_128], rax
0x18002fa14  mov     rax, [rsp+208h+arg_58]
0x18002fa1c  mov     [rsp+208h+var_120], rax
0x18002fa24  mov     rsi, [rsp+208h+arg_60]
0x18002fa2c  mov     [rsp+208h+var_178], rsi
0x18002fa34  mov     rax, [rsp+208h+arg_68]
0x18002fa3c  mov     [rsp+208h+var_118], rax
0x18002fa44  mov     rax, [rsp+208h+arg_70]
0x18002fa4c  mov     [rsp+208h+var_108], rax
0x18002fa54  mov     rax, [rsp+208h+arg_78]
0x18002fa5c  mov     [rsp+208h+var_100], rax
0x18002fa64  mov     rax, [rsp+208h+arg_80]
0x18002fa6c  mov     [rsp+208h+var_F8], rax
0x18002fa74  mov     rax, [rsp+208h+arg_88]
0x18002fa7c  mov     [rsp+208h+var_160], rax
0x18002fa84  mov     rax, [rsp+208h+arg_90]
0x18002fa8c  mov     [rsp+208h+var_110], rax
0x18002fa94  mov     rax, [rsp+208h+arg_98]
0x18002fa9c  mov     [rsp+208h+PowerRequest], rax
0x18002faa1  xor     edi, edi
0x18002faa3  mov     [rsp+208h+var_1C0], edi
0x18002faa7  mov     [rsp+208h+var_E8], edi
0x18002faae  xor     edx, edx; Val
0x18002fab0  mov     r8d, 9Ch; Size
0x18002fab6  lea     rcx, [rsp+208h+var_E4]; void *
0x18002fabe  call    memset_0
0x18002fac3  mov     qword ptr [rsp+208h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x18002facb  mov     qword ptr [rsp+208h+var_158.dwLowDateTime], rdi
0x18002fad3  mov     r15d, edi
0x18002fad6  mov     [rsp+208h+var_1BC], edi
0x18002fada  mov     eax, edi
0x18002fadc  mov     [rsp+208h+var_1C4], eax
0x18002fae0  mov     [rsp+208h+var_1B8], eax
0x18002fae4  mov     r12d, edi
0x18002fae7  mov     [rsp+208h+var_1C8], edi
0x18002faeb  lea     r14, WPP_GLOBAL_Control
0x18002faf2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002faf9  cmp     rcx, r14
0x18002fafc  jz      short loc_18002FB19
0x18002fafe  test    byte ptr [rcx+1Ch], 8
0x18002fb02  jz      short loc_18002FB19
0x18002fb04  mov     rax, [r13+0]
0x18002fb08  mov     qword ptr [rsp+208h+dwCreationDisposition], rax
0x18002fb0d  mov     r9, [rbx]
0x18002fb10  mov     rcx, [rcx+10h]
0x18002fb14  call    WPP_SF_SS
0x18002fb19  test    rsi, rsi
0x18002fb1c  jz      loc_18002FBDA
0x18002fb22  mov     rdx, rbx
0x18002fb25  lea     rcx, [rsp+208h+var_198]
0x18002fb2a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002fb2f  lea     r8, [rsp+208h+var_88]
0x18002fb37  mov     rdx, rax
0x18002fb3a  or      rcx, 0FFFFFFFFFFFFFFFFh; hObject
0x18002fb3e  call    ?ReadCurrentUsn@FheFileOperations@@YAJPEAXV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEA_J@Z; FheFileOperations::ReadCurrentUsn(void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,__int64 &)
0x18002fb43  mov     ebx, eax
0x18002fb45  mov     r15d, eax
0x18002fb48  shr     r15d, 1Fh
0x18002fb4c  mov     [rsp+208h+var_1BC], r15d
0x18002fb51  test    eax, eax
0x18002fb53  jns     short loc_18002FB8F
0x18002fb55  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb5c  cmp     rcx, r14
0x18002fb5f  jz      loc_180030432
0x18002fb65  mov     esi, 1
0x18002fb6a  test    [rcx+1Ch], sil
0x18002fb6e  jz      loc_180030432
0x18002fb74  lea     edx, [rsi+1Ah]
0x18002fb77  mov     r9d, eax
0x18002fb7a  lea     r8, WPP_15a774469b7338d2f0041947fb32ba59_Traceguids
0x18002fb81  mov     rcx, [rcx+10h]
0x18002fb85  call    WPP_SF_d
0x18002fb8a  jmp     loc_180030432
0x18002fb8f  mov     rax, [rsi]
0x18002fb92  mov     r9, [rsp+208h+var_88]
0x18002fb9a  cmp     r9, rax
0x18002fb9d  jz      short loc_18002FBD5
0x18002fb9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fba6  cmp     rcx, r14
0x18002fba9  jz      short loc_18002FBCB
0x18002fbab  test    byte ptr [rcx+1Ch], 8
0x18002fbaf  jz      short loc_18002FBCB
0x18002fbb1  mov     edx, 1Ch
0x18002fbb6  mov     qword ptr [rsp+208h+dwCreationDisposition], rax
0x18002fbbb  lea     r8, WPP_15a774469b7338d2f0041947fb32ba59_Traceguids
0x18002fbc2  mov     rcx, [rcx+10h]
0x18002fbc6  call    WPP_SF_ii
0x18002fbcb  mov     ebx, 80040404h
0x18002fbd0  jmp     loc_180030432
0x18002fbd5  mov     rbx, [rsp+208h+var_1B0]
0x18002fbda  mov     rcx, [rbx]; lpFileName
0x18002fbdd  call    cs:__imp_GetFileAttributesW
0x18002fbe3  cmp     eax, 0FFFFFFFFh
0x18002fbe6  jnz     short loc_18002FC38
0x18002fbe8  call    cs:__imp_GetLastError
0x18002fbee  mov     ebx, eax
0x18002fbf0  test    eax, eax
0x18002fbf2  jle     short loc_18002FBFD
0x18002fbf4  movzx   ebx, ax
0x18002fbf7  or      ebx, 80070000h
0x18002fbfd  mov     eax, ebx
0x18002fbff  shr     eax, 1Fh
0x18002fc02  or      r15d, eax
0x18002fc05  mov     [rsp+208h+var_1BC], r15d
0x18002fc0a  test    ebx, ebx
0x18002fc0c  jns     short loc_18002FC38
0x18002fc0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fc15  cmp     rcx, r14
0x18002fc18  jz      loc_180030432
0x18002fc1e  mov     esi, 1
0x18002fc23  test    [rcx+1Ch], sil
0x18002fc27  jz      loc_180030432
0x18002fc2d  lea     edx, [rsi+1Ch]
0x18002fc30  mov     r9d, ebx
0x18002fc33  jmp     loc_18002FB7A
0x18002fc38  mov     [rsp+208h+var_198], r15d
0x18002fc3d  mov     edx, 5Ch ; '\'
0x18002fc42  mov     rcx, r13
0x18002fc45  call    ?ReverseFind@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::ReverseFind(ushort)
0x18002fc4a  mov     r12d, eax
0x18002fc4d  cmp     eax, 0FFFFFFFFh
0x18002fc50  jnz     short loc_18002FC96
0x18002fc52  mov     ebx, 80070057h
0x18002fc57  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fc5e  cmp     rcx, r14
0x18002fc61  jz      short loc_18002FC88
0x18002fc63  lea     esi, [rax+2]
0x18002fc66  test    [rcx+1Ch], sil
0x18002fc6a  jz      short loc_18002FC88
0x18002fc6c  lea     edx, [rax+1Fh]
0x18002fc6f  mov     [rsp+208h+dwCreationDisposition], ebx
0x18002fc73  mov     r9, [r13+0]
0x18002fc77  lea     r8, WPP_15a774469b7338d2f0041947fb32ba59_Traceguids
0x18002fc7e  mov     rcx, [rcx+10h]
0x18002fc82  call    WPP_SF_Sd
0x18002fc87  nop
0x18002fc88  mov     r12d, [rsp+208h+var_1C8]
0x18002fc8d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002fc91  jmp     loc_180030436
0x18002fc96  mov     r8d, r12d
0x18002fc99  lea     rdx, [rsp+208h+var_1A8]
0x18002fc9e  mov     rcx, r13
0x18002fca1  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x18002fca6  mov     rcx, rax
0x18002fca9  call    ?CreateDirectoryPath@FheFileOperations@@YAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; FheFileOperations::CreateDirectoryPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x18002fcae  mov     ebx, eax
0x18002fcb0  test    eax, eax
0x18002fcb2  jns     short loc_18002FD32
0x18002fcb4  mov     esi, 1
0x18002fcb9  mov     eax, esi
0x18002fcbb  mov     [rsp+208h+var_1C4], eax
0x18002fcbf  mov     [rsp+208h+var_1B8], eax
0x18002fcc3  mov     rax, cs:WPP_GLOBAL_Control
0x18002fcca  cmp     rax, r14
0x18002fccd  jz      short loc_18002FD0B
0x18002fccf  test    byte ptr [rax+1Ch], 8
0x18002fcd3  jz      short loc_18002FD0B
0x18002fcd5  mov     r8d, r12d
0x18002fcd8  lea     rdx, [rsp+208h+var_1A8]
0x18002fcdd  mov     rcx, r13
0x18002fce0  call    ?Left@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@H@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Left(int)
0x18002fce5  mov     r14d, esi
0x18002fce8  lea     edx, [rsi+1Eh]
0x18002fceb  mov     [rsp+208h+dwCreationDisposition], ebx
0x18002fcef  mov     r9, [rax]
0x18002fcf2  lea     r8, WPP_15a774469b7338d2f0041947fb32ba59_Traceguids
0x18002fcf9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fd00  mov     rcx, [rcx+10h]
0x18002fd04  call    WPP_SF_Sd
0x18002fd09  jmp     short loc_18002FD10
0x18002fd0b  mov     r14d, [rsp+208h+var_1C0]
0x18002fd10  test    sil, r14b
0x18002fd13  jz      short loc_18002FD24
0x18002fd15  mov     rcx, [rsp+208h+var_1A8]
0x18002fd1a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002fd1e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002fd23  nop
0x18002fd24  mov     r12d, [rsp+208h+var_1C8]
0x18002fd29  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002fd2d  jmp     loc_180030436
0x18002fd32  mov     rcx, [r13+0]; lpFileName
0x18002fd36  call    cs:__imp_GetFileAttributesW
0x18002fd3c  mov     esi, 1
0x18002fd41  cmp     eax, 0FFFFFFFFh
0x18002fd44  jz      short loc_18002FD5B
0x18002fd46  test    sil, al
0x18002fd49  jz      short loc_18002FD5B
0x18002fd4b  and     eax, 0FFFFFFFEh
0x18002fd4e  mov     edx, eax; dwFileAttributes
0x18002fd50  mov     rcx, [r13+0]; lpFileName
0x18002fd54  call    cs:__imp_SetFileAttributesW
0x18002fd5a  nop
0x18002fd5b  mov     ebx, [rsp+208h+var_1C8]
0x18002fd5f  jmp     loc_18002FE08
0x18002fd64  mov     ebx, [rsp+208h+var_1C0]
0x18002fd68  xor     edi, edi
0x18002fd6a  test    ebx, ebx
0x18002fd6c  jns     short loc_18002FDCB
0x18002fd6e  lea     r14, WPP_GLOBAL_Control
0x18002fd75  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fd7c  cmp     rcx, r14
0x18002fd7f  jz      short loc_18002FDA0
0x18002fd81  lea     esi, [rdi+1]
0x18002fd84  test    [rcx+1Ch], sil
0x18002fd88  jz      short loc_18002FDA0
0x18002fd8a  lea     edx, [rdi+20h]
0x18002fd8d  mov     r9d, ebx
0x18002fd90  lea     r8, WPP_15a774469b7338d2f0041947fb32ba59_Traceguids
0x18002fd97  mov     rcx, [rcx+10h]
0x18002fd9b  call    WPP_SF_d
0x18002fda0  mov     r15d, [rsp+208h+var_1BC]
0x18002fda5  mov     eax, [rsp+208h+var_1B8]
0x18002fda9  mov     [rsp+208h+var_1C4], eax
0x18002fdad  mov     r12d, edi
0x18002fdb0  mov     [rsp+208h+var_1C8], edi
0x18002fdb4  mov     rax, [rsp+208h+var_190]
0x18002fdb9  mov     [rsp+208h+var_1B0], rax
0x18002fdbe  mov     r13, [rsp+208h+var_188]
0x18002fdc6  jmp     loc_180030432
0x18002fdcb  lea     r14, WPP_GLOBAL_Control
0x18002fdd2  mov     esi, 1
0x18002fdd7  mov     r15d, [rsp+208h+var_1BC]
0x18002fddc  mov     eax, [rsp+208h+var_1B8]
0x18002fde0  mov     [rsp+208h+var_1C4], eax
0x18002fde4  mov     ebx, edi
0x18002fde6  mov     rax, [rsp+208h+var_190]
0x18002fdeb  mov     [rsp+208h+var_1B0], rax
0x18002fdf0  mov     r13, [rsp+208h+var_188]
0x18002fdf8  mov     rax, [rsp+208h+var_140]
0x18002fe00  mov     [rsp+208h+var_168], rax
0x18002fe08  mov     r12, [rsp+208h+PowerRequest]
0x18002fe0d  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18002fe11  jz      loc_18002FEA8
0x18002fe17  mov     edx, esi; RequestType
0x18002fe19  mov     rcx, r12; PowerRequest
0x18002fe1c  call    cs:__imp_PowerSetRequest
0x18002fe22  test    eax, eax
0x18002fe24  jnz     short loc_18002FE5E
0x18002fe26  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe2d  cmp     rcx, r14
0x18002fe30  jz      short loc_18002FE5E
0x18002fe32  test    byte ptr [rcx+1Ch], 4
0x18002fe36  jz      short loc_18002FE5E
0x18002fe38  lea     edx, [rax+21h]
0x18002fe3b  lea     rax, aPowersetreques; "PowerSetRequest(PowerRequestSystemRequi"...
0x18002fe42  mov     qword ptr [rsp+208h+dwCreationDisposition], rax
0x18002fe47  lea     r9, aTempret; "tempRet"
0x18002fe4e  lea     r8, WPP_15a774469b7338d2f0041947fb32ba59_Traceguids
0x18002fe55  mov     rcx, [rcx+10h]
0x18002fe59  call    WPP_SF_ss
0x18002fe5e  mov     edx, 3; RequestType
0x18002fe63  mov     rcx, r12; PowerRequest
0x18002fe66  call    cs:__imp_PowerSetRequest
0x18002fe6c  test    eax, eax
0x18002fe6e  jnz     short loc_18002FEA8
0x18002fe70  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe77  cmp     rcx, r14
0x18002fe7a  jz      short loc_18002FEA8
0x18002fe7c  test    byte ptr [rcx+1Ch], 4
0x18002fe80  jz      short loc_18002FEA8
0x18002fe82  lea     edx, [rax+22h]
0x18002fe85  lea     rax, aPowersetreques_0; "PowerSetRequest(PowerRequestExecutionRe"...
0x18002fe8c  mov     qword ptr [rsp+208h+dwCreationDisposition], rax
0x18002fe91  lea     r9, aTempret; "tempRet"
0x18002fe98  lea     r8, WPP_15a774469b7338d2f0041947fb32ba59_Traceguids
0x18002fe9f  mov     rcx, [rcx+10h]
0x18002fea3  call    WPP_SF_ss
0x18002fea8  lea     rcx, [rsp+208h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002feb0  call    cs:__imp_GetSystemTimeAsFileTime
0x18002feb6  mov     [rsp+208h+var_B4], edi
0x18002febd  mov     rax, [rsp+208h+var_170]
  ... truncated ...
```
