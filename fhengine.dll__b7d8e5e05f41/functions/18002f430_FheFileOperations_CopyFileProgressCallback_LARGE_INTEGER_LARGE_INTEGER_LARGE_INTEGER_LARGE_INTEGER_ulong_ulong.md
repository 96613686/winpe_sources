# FheFileOperations::CopyFileProgressCallback(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *)

- ea: `0x18002f430`
- end: `0x18002f96a`
- name: `?CopyFileProgressCallback@FheFileOperations@@YAKT_LARGE_INTEGER@@000KKPEAX11@Z`
- size: `1338`
- prototype: `__int64 __fastcall(FheFileOperations *this, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, HANDLE hFile, void *, LPBY_HANDLE_FILE_INFORMATION lpFileInformation)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002c24`
- `0x180007818`
- `0x18002f430`
- `0x18003122c`
- `0x180031680`

## import_xrefs

- `KERNEL32!SetFileInformationByHandle` at `0x18002f6b6`
- `KERNEL32!SetFileInformationByHandle` at `0x18002f70e`
- `KERNEL32!SetFileInformationByHandle` at `0x18002f85f`
- `KERNEL32!SetFileInformationByHandle` at `0x18002f6b6`
- `KERNEL32!SetFileInformationByHandle` at `0x18002f70e`
- `KERNEL32!SetFileInformationByHandle` at `0x18002f85f`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18002f842`
- `KERNEL32!GetFileInformationByHandleEx` at `0x18002f842`
- `KERNEL32!GetLastError` at `0x18002f4c9`
- `KERNEL32!GetLastError` at `0x18002f67a`
- `KERNEL32!GetLastError` at `0x18002f6d2`
- `KERNEL32!GetLastError` at `0x18002f72a`
- `KERNEL32!GetLastError` at `0x18002f7ee`
- `KERNEL32!GetLastError` at `0x18002f87b`
- `KERNEL32!GetLastError` at `0x18002f8a6`
- `KERNEL32!GetLastError` at `0x18002f4c9`
- `KERNEL32!GetLastError` at `0x18002f67a`
- `KERNEL32!GetLastError` at `0x18002f6d2`
- `KERNEL32!GetLastError` at `0x18002f72a`
- `KERNEL32!GetLastError` at `0x18002f7ee`
- `KERNEL32!GetLastError` at `0x18002f87b`
- `KERNEL32!GetLastError` at `0x18002f8a6`
- `KERNEL32!GetCurrentThread` at `0x18002f652`
- `KERNEL32!GetCurrentThread` at `0x18002f652`
- `KERNEL32!SetThreadPriority` at `0x18002f65e`
- `KERNEL32!SetThreadPriority` at `0x18002f65e`
- `KERNEL32!GetFileInformationByHandle` at `0x18002f4aa`
- `KERNEL32!GetFileInformationByHandle` at `0x18002f7d0`
- `KERNEL32!GetFileInformationByHandle` at `0x18002f4aa`
- `KERNEL32!GetFileInformationByHandle` at `0x18002f7d0`
- `KERNEL32!Sleep` at `0x18002f929`
- `KERNEL32!Sleep` at `0x18002f929`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=3
__int64 __fastcall FheFileOperations::CopyFileProgressCallback(
        FheFileOperations *this,
        union _LARGE_INTEGER a2,
        union _LARGE_INTEGER a3,
        union _LARGE_INTEGER a4,
        union _LARGE_INTEGER a5,
        unsigned int a6,
        HANDLE hFile,
        void *a8,
        LPBY_HANDLE_FILE_INFORMATION lpFileInformation)
{
  unsigned int v11; // r15d
  BOOL FileInformationByHandle; // eax
  signed int LastError; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  __int64 v17; // rax
  __int64 v18; // rcx
  int v19; // eax
  void *ftCreationTime; // rdx
  void *v21; // rdx
  int v22; // eax
  bool v23; // cc
  HANDLE CurrentThread; // rax
  signed int v25; // eax
  signed int v26; // eax
  signed int v27; // eax
  HANDLE v28; // rsi
  int CurrentUsn; // eax
  BOOL v30; // eax
  signed int v31; // eax
  HANDLE v32; // rsi
  signed int v33; // eax
  __int64 v34; // rdx
  signed __int64 *ftLastWriteTime; // rdx
  signed __int64 v36; // r8
  signed __int64 v37; // rax
  signed __int64 v38; // rtt
  __int64 v39; // rax
  _DWORD *v40; // rax
  DWORD FileInformation; // [rsp+20h] [rbp-60h] BYREF
  int nPriority; // [rsp+28h] [rbp-58h] BYREF
  LONGLONG v44; // [rsp+30h] [rbp-50h]
  HANDLE hObject; // [rsp+38h] [rbp-48h]
  HANDLE v46; // [rsp+40h] [rbp-40h]
  _OWORD v47[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v48; // [rsp+68h] [rbp-18h]

  v11 = 1;
  hObject = hFile;
  v46 = a8;
  if ( hFile == (HANDLE)-1LL )
    return v11;
  if ( lpFileInformation[2].ftLastWriteTime.dwLowDateTime )
  {
    *(union _LARGE_INTEGER *)&lpFileInformation[2].ftLastWriteTime.dwHighDateTime = a4;
    *(union _LARGE_INTEGER *)&lpFileInformation[2].nFileSizeHigh = a4;
    lpFileInformation[2].ftLastWriteTime.dwLowDateTime = 0;
    FileInformationByHandle = GetFileInformationByHandle(hFile, lpFileInformation);
    lpFileInformation[1].dwFileAttributes = FileInformationByHandle;
    lpFileInformation[2].nFileIndexLow |= !FileInformationByHandle;
    if ( !FileInformationByHandle )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 43;
        v16 = (unsigned int)LastError;
LABEL_9:
        WPP_SF_d(v14[2], v15, &WPP_15a774469b7338d2f0041947fb32ba59_Traceguids, v16);
        return v11;
      }
      return v11;
    }
    v44 = 0;
  }
  else
  {
    v17 = *(_QWORD *)&lpFileInformation[2].nFileSizeHigh;
    if ( a4.QuadPart < v17 )
      v44 = 0;
    else
      v44 = a4.QuadPart - v17;
    v18 = *(_QWORD *)&lpFileInformation[2].ftLastWriteTime.dwHighDateTime;
    *(union _LARGE_INTEGER *)&lpFileInformation[2].nFileSizeHigh = a4;
    if ( a4.QuadPart < v18 )
      *(_QWORD *)&lpFileInformation[2].nNumberOfLinks = 0;
    else
      *(_QWORD *)&lpFileInformation[2].nNumberOfLinks = a4.QuadPart - v18;
  }
  if ( !*(_QWORD *)&lpFileInformation[1].nFileSizeLow )
  {
LABEL_25:
    ftCreationTime = (void *)lpFileInformation[1].ftCreationTime;
    if ( !ftCreationTime
      || (_m_prefetchw(ftCreationTime),
          _InterlockedOr((volatile signed __int32 *)ftCreationTime, 0) == lpFileInformation[1].ftLastAccessTime.dwLowDateTime) )
    {
LABEL_51:
      if ( a4.QuadPart == a3.QuadPart )
      {
        memset(v47, 0, sizeof(v47));
        v48 = 0;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&nPriority);
        v28 = hObject;
        CurrentUsn = FheFileOperations::ReadCurrentUsn(hObject);
        v16 = (unsigned int)CurrentUsn;
        lpFileInformation[2].nFileIndexLow |= (unsigned int)CurrentUsn >> 31;
        if ( CurrentUsn < 0 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v15 = 48;
            goto LABEL_9;
          }
          return v11;
        }
        v30 = GetFileInformationByHandle(v28, lpFileInformation);
        lpFileInformation[1].dwFileAttributes = v30;
        lpFileInformation[2].nFileIndexLow |= !v30;
        if ( !v30 )
        {
          v31 = GetLastError();
          if ( v31 > 0 )
            v31 = (unsigned __int16)v31 | 0x80070000;
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v15 = 49;
            v16 = (unsigned int)v31;
            goto LABEL_9;
          }
          return v11;
        }
        if ( lpFileInformation[2].ftLastAccessTime.dwHighDateTime )
        {
          v32 = v46;
          if ( GetFileInformationByHandleEx(v46, FileBasicInfo, v47, 0x28u) )
          {
            LODWORD(v48) = v48 | 1;
            if ( SetFileInformationByHandle(v32, FileBasicInfo, v47, 0x28u)
              || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_76;
            }
            v33 = GetLastError();
            if ( v33 > 0 )
              v33 = (unsigned __int16)v33 | 0x80070000;
            v34 = 50;
          }
          else
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_76;
            v33 = GetLastError();
            if ( v33 > 0 )
              v33 = (unsigned __int16)v33 | 0x80070000;
            v34 = 51;
          }
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v34,
            &WPP_15a774469b7338d2f0041947fb32ba59_Traceguids,
            (unsigned int)v33);
        }
      }
LABEL_76:
      ftLastWriteTime = (signed __int64 *)lpFileInformation[1].ftLastWriteTime;
      if ( !ftLastWriteTime )
        goto LABEL_92;
      v36 = *(_QWORD *)&lpFileInformation[2].nNumberOfLinks;
      _m_prefetchw(ftLastWriteTime);
      v37 = *ftLastWriteTime;
      do
      {
        v38 = v37;
        v37 = _InterlockedCompareExchange64(ftLastWriteTime, v37, v37);
      }
      while ( v38 != v37 );
      if ( v36 >= v37 && a4.QuadPart < a3.QuadPart )
      {
        lpFileInformation[1].dwVolumeSerialNumber = 1;
      }
      else
      {
LABEL_92:
        if ( (int)lpFileInformation[1].ftLastAccessTime.dwLowDateTime < 2 )
        {
          v39 = 4 * v44 / 0x40000;
          if ( v39 > 0 )
            Sleep(v39);
        }
        v40 = *(_DWORD **)&lpFileInformation[2].ftCreationTime.dwHighDateTime;
        if ( !v40 || !*v40 )
          return 0;
      }
      return 5;
    }
    v21 = (void *)lpFileInformation[1].ftCreationTime;
    FileInformation = 0;
    _m_prefetchw(v21);
    v22 = _InterlockedOr((volatile signed __int32 *)v21, 0);
    v23 = (signed int)lpFileInformation[1].ftLastAccessTime.dwLowDateTime < 2;
    FileInformation = v22;
    if ( v23 )
    {
      if ( v22 >= 2 )
      {
        nPriority = 0x20000;
LABEL_32:
        CurrentThread = GetCurrentThread();
        if ( !SetThreadPriority(CurrentThread, nPriority)
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v25 = GetLastError();
          if ( v25 > 0 )
            v25 = (unsigned __int16)v25 | 0x80070000;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            45,
            &WPP_15a774469b7338d2f0041947fb32ba59_Traceguids,
            (unsigned int)v25);
        }
      }
    }
    else if ( v22 < 2 )
    {
      nPriority = 0x10000;
      goto LABEL_32;
    }
    if ( !SetFileInformationByHandle(hObject, FileIoPriorityHintInfo, &FileInformation, 4u)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v26 = GetLastError();
      if ( v26 > 0 )
        v26 = (unsigned __int16)v26 | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        &WPP_15a774469b7338d2f0041947fb32ba59_Traceguids,
        (unsigned int)v26);
    }
    if ( !SetFileInformationByHandle(v46, FileIoPriorityHintInfo, &FileInformation, 4u)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v27 = GetLastError();
      if ( v27 > 0 )
        v27 = (unsigned __int16)v27 | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        &WPP_15a774469b7338d2f0041947fb32ba59_Traceguids,
        (unsigned int)v27);
    }
    lpFileInformation[1].ftLastAccessTime.dwLowDateTime = FileInformation;
    goto LABEL_51;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&nPriority);
  v19 = FheFileOperations::ReadCurrentUsn(hFile);
  v16 = (unsigned int)v19;
  lpFileInformation[2].nFileIndexLow |= (unsigned int)v19 >> 31;
  if ( v19 >= 0 )
  {
    if ( *(_QWORD *)&lpFileInformation[1].nFileIndexHigh != **(_QWORD **)&lpFileInformation[1].nFileSizeLow )
    {
      lpFileInformation[2].dwFileAttributes = 1;
      return v11;
    }
    *(_QWORD *)&lpFileInformation[1].nFileSizeLow = 0;
    goto LABEL_25;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v15 = 44;
    goto LABEL_9;
  }
  return v11;
}

```

## disassembly

```asm
0x18002f430  mov     [rsp-38h+arg_0], rbx
0x18002f435  push    rbp
0x18002f436  push    rsi
0x18002f437  push    rdi
0x18002f438  push    r12
0x18002f43a  push    r13
0x18002f43c  push    r14
0x18002f43e  push    r15
0x18002f440  mov     rbp, rsp
0x18002f443  sub     rsp, 80h
0x18002f44a  mov     rax, cs:__security_cookie
0x18002f451  xor     rax, rsp
0x18002f454  mov     [rbp+var_10], rax
0x18002f458  mov     r12, [rbp+hFile]
0x18002f45c  mov     rbx, r9
0x18002f45f  mov     rax, [rbp+arg_38]
0x18002f463  mov     rdi, r8
0x18002f466  mov     r14, [rbp+lpFileInformation]
0x18002f46d  mov     r15d, 1
0x18002f473  mov     [rbp+hObject], r12
0x18002f477  mov     [rbp+var_40], rax
0x18002f47b  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18002f47f  jz      loc_18002F940
0x18002f485  xor     r13d, r13d
0x18002f488  cmp     [r14+7Ch], r13d
0x18002f48c  jz      loc_18002F51F
0x18002f492  mov     rdx, r14; lpFileInformation
0x18002f495  mov     [r14+80h], rbx
0x18002f49c  mov     rcx, r12; hFile
0x18002f49f  mov     [r14+88h], rbx
0x18002f4a6  mov     [r14+7Ch], r13d
0x18002f4aa  call    cs:__imp_GetFileInformationByHandle
0x18002f4b0  mov     ecx, eax
0x18002f4b2  mov     eax, r13d
0x18002f4b5  test    ecx, ecx
0x18002f4b7  mov     [r14+34h], ecx
0x18002f4bb  setz    al
0x18002f4be  or      [r14+98h], eax
0x18002f4c5  test    ecx, ecx
0x18002f4c7  jnz     short loc_18002F519
0x18002f4c9  call    cs:__imp_GetLastError
0x18002f4cf  test    eax, eax
0x18002f4d1  jle     short loc_18002F4DB
0x18002f4d3  movzx   eax, ax
0x18002f4d6  or      eax, 80070000h
0x18002f4db  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f4e2  lea     r12, WPP_GLOBAL_Control
0x18002f4e9  cmp     rcx, r12
0x18002f4ec  jz      loc_18002F940
0x18002f4f2  test    [rcx+1Ch], r15b
0x18002f4f6  jz      loc_18002F940
0x18002f4fc  mov     edx, 2Bh ; '+'
0x18002f501  mov     r9d, eax
0x18002f504  lea     r8, WPP_15a774469b7338d2f0041947fb32ba59_Traceguids
0x18002f50b  mov     rcx, [rcx+10h]
0x18002f50f  call    WPP_SF_d
0x18002f514  jmp     loc_18002F940
0x18002f519  mov     [rbp+var_50], r13
0x18002f51d  jmp     short loc_18002F564
0x18002f51f  mov     rax, [r14+88h]
0x18002f526  cmp     rbx, rax
0x18002f529  jl      short loc_18002F537
0x18002f52b  mov     rdx, rbx
0x18002f52e  sub     rdx, rax
0x18002f531  mov     [rbp+var_50], rdx
0x18002f535  jmp     short loc_18002F53B
0x18002f537  mov     [rbp+var_50], r13
0x18002f53b  mov     rcx, [r14+80h]
0x18002f542  mov     [r14+88h], rbx
0x18002f549  cmp     rbx, rcx
0x18002f54c  jl      short loc_18002F55D
0x18002f54e  mov     rax, rbx
0x18002f551  sub     rax, rcx
0x18002f554  mov     [r14+90h], rax
0x18002f55b  jmp     short loc_18002F564
0x18002f55d  mov     [r14+90h], r13
0x18002f564  cmp     [r14+58h], r13
0x18002f568  jz      short loc_18002F5D9
0x18002f56a  lea     rcx, [rbp+nPriority]
0x18002f56e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002f573  mov     rdx, rax
0x18002f576  lea     r8, [r14+60h]
0x18002f57a  mov     rcx, r12; hObject
0x18002f57d  call    ?ReadCurrentUsn@FheFileOperations@@YAJPEAXV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEA_J@Z; FheFileOperations::ReadCurrentUsn(void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,__int64 &)
0x18002f582  mov     r9d, eax
0x18002f585  shr     eax, 1Fh
0x18002f588  or      [r14+98h], eax
0x18002f58f  test    r9d, r9d
0x18002f592  jns     short loc_18002F5BF
0x18002f594  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f59b  lea     r12, WPP_GLOBAL_Control
0x18002f5a2  cmp     rcx, r12
0x18002f5a5  jz      loc_18002F940
0x18002f5ab  test    [rcx+1Ch], r15b
0x18002f5af  jz      loc_18002F940
0x18002f5b5  mov     edx, 2Ch ; ','
0x18002f5ba  jmp     loc_18002F504
0x18002f5bf  mov     rax, [r14+58h]
0x18002f5c3  mov     rcx, [rax]
0x18002f5c6  cmp     [r14+60h], rcx
0x18002f5ca  jz      short loc_18002F5D5
0x18002f5cc  mov     [r14+68h], r15d
0x18002f5d0  jmp     loc_18002F940
0x18002f5d5  mov     [r14+58h], r13
0x18002f5d9  mov     rdx, [r14+38h]
0x18002f5dd  lea     r12, WPP_GLOBAL_Control
0x18002f5e4  xor     r8d, r8d
0x18002f5e7  lea     r13, WPP_15a774469b7338d2f0041947fb32ba59_Traceguids
0x18002f5ee  mov     esi, 80070000h
0x18002f5f3  test    rdx, rdx
0x18002f5f6  jz      loc_18002F75B
0x18002f5fc  prefetchw byte ptr [rdx]
0x18002f5ff  mov     eax, [rdx]
0x18002f601  mov     ecx, eax
0x18002f603  or      ecx, r8d
0x18002f606  lock cmpxchg [rdx], ecx
0x18002f60a  jnz     short loc_18002F601
0x18002f60c  cmp     eax, [r14+40h]
0x18002f610  jz      loc_18002F75B
0x18002f616  mov     rdx, [r14+38h]
0x18002f61a  mov     [rbp+FileInformation], r8d
0x18002f61e  prefetchw byte ptr [rdx]
0x18002f621  mov     eax, [rdx]
0x18002f623  mov     ecx, eax
0x18002f625  or      ecx, r8d
0x18002f628  lock cmpxchg [rdx], ecx
0x18002f62c  jnz     short loc_18002F623
0x18002f62e  cmp     dword ptr [r14+40h], 2
0x18002f633  mov     [rbp+FileInformation], eax
0x18002f636  jge     short loc_18002F646
0x18002f638  cmp     eax, 2
0x18002f63b  jl      short loc_18002F6A4
0x18002f63d  mov     [rbp+nPriority], 20000h
0x18002f644  jmp     short loc_18002F652
0x18002f646  cmp     eax, 2
0x18002f649  jge     short loc_18002F6A4
0x18002f64b  mov     [rbp+nPriority], 10000h
0x18002f652  call    cs:__imp_GetCurrentThread
0x18002f658  mov     edx, [rbp+nPriority]; nPriority
0x18002f65b  mov     rcx, rax; hThread
0x18002f65e  call    cs:__imp_SetThreadPriority
0x18002f664  test    eax, eax
0x18002f666  jnz     short loc_18002F6A4
0x18002f668  mov     rax, cs:WPP_GLOBAL_Control
0x18002f66f  cmp     rax, r12
0x18002f672  jz      short loc_18002F6A4
0x18002f674  test    [rax+1Ch], r15b
0x18002f678  jz      short loc_18002F6A4
0x18002f67a  call    cs:__imp_GetLastError
0x18002f680  test    eax, eax
0x18002f682  jle     short loc_18002F689
0x18002f684  movzx   eax, ax
0x18002f687  or      eax, esi
0x18002f689  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f690  mov     edx, 2Dh ; '-'
0x18002f695  mov     r9d, eax
0x18002f698  mov     r8, r13
0x18002f69b  mov     rcx, [rcx+10h]
0x18002f69f  call    WPP_SF_d
0x18002f6a4  mov     rcx, [rbp+hObject]; hFile
0x18002f6a8  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18002f6ac  mov     r9d, 4; dwBufferSize
0x18002f6b2  lea     edx, [r9+8]; FileInformationClass
0x18002f6b6  call    cs:__imp_SetFileInformationByHandle
0x18002f6bc  test    eax, eax
0x18002f6be  jnz     short loc_18002F6FC
0x18002f6c0  mov     rax, cs:WPP_GLOBAL_Control
0x18002f6c7  cmp     rax, r12
0x18002f6ca  jz      short loc_18002F6FC
0x18002f6cc  test    [rax+1Ch], r15b
0x18002f6d0  jz      short loc_18002F6FC
0x18002f6d2  call    cs:__imp_GetLastError
0x18002f6d8  test    eax, eax
0x18002f6da  jle     short loc_18002F6E1
0x18002f6dc  movzx   eax, ax
0x18002f6df  or      eax, esi
0x18002f6e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f6e8  mov     edx, 2Eh ; '.'
0x18002f6ed  mov     r9d, eax
0x18002f6f0  mov     r8, r13
0x18002f6f3  mov     rcx, [rcx+10h]
0x18002f6f7  call    WPP_SF_d
0x18002f6fc  mov     rcx, [rbp+var_40]; hFile
0x18002f700  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18002f704  mov     r9d, 4; dwBufferSize
0x18002f70a  lea     edx, [r9+8]; FileInformationClass
0x18002f70e  call    cs:__imp_SetFileInformationByHandle
0x18002f714  test    eax, eax
0x18002f716  jnz     short loc_18002F754
0x18002f718  mov     rax, cs:WPP_GLOBAL_Control
0x18002f71f  cmp     rax, r12
0x18002f722  jz      short loc_18002F754
0x18002f724  test    [rax+1Ch], r15b
0x18002f728  jz      short loc_18002F754
0x18002f72a  call    cs:__imp_GetLastError
0x18002f730  test    eax, eax
0x18002f732  jle     short loc_18002F739
0x18002f734  movzx   eax, ax
0x18002f737  or      eax, esi
0x18002f739  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f740  mov     edx, 2Fh ; '/'
0x18002f745  mov     r9d, eax
0x18002f748  mov     r8, r13
0x18002f74b  mov     rcx, [rcx+10h]
0x18002f74f  call    WPP_SF_d
0x18002f754  mov     eax, [rbp+FileInformation]
0x18002f757  mov     [r14+40h], eax
0x18002f75b  cmp     rbx, rdi
0x18002f75e  jnz     loc_18002F8D3
0x18002f764  xorps   xmm0, xmm0
0x18002f767  lea     rcx, [rbp+nPriority]
0x18002f76b  xor     eax, eax
0x18002f76d  movups  [rbp+var_38], xmm0
0x18002f771  mov     [rbp+var_18], rax
0x18002f775  movups  [rbp+var_28], xmm0
0x18002f779  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002f77e  mov     rsi, [rbp+hObject]
0x18002f782  lea     r8, [r14+60h]
0x18002f786  mov     rcx, rsi; hObject
0x18002f789  mov     rdx, rax
0x18002f78c  call    ?ReadCurrentUsn@FheFileOperations@@YAJPEAXV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEA_J@Z; FheFileOperations::ReadCurrentUsn(void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,__int64 &)
0x18002f791  mov     r9d, eax
0x18002f794  shr     eax, 1Fh
0x18002f797  or      [r14+98h], eax
0x18002f79e  test    r9d, r9d
0x18002f7a1  jns     short loc_18002F7CA
0x18002f7a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f7aa  cmp     rcx, r12
0x18002f7ad  jz      loc_18002F940
0x18002f7b3  test    [rcx+1Ch], r15b
0x18002f7b7  jz      loc_18002F940
0x18002f7bd  mov     edx, 30h ; '0'
0x18002f7c2  mov     r8, r13
0x18002f7c5  jmp     loc_18002F50B
0x18002f7ca  mov     rdx, r14; lpFileInformation
0x18002f7cd  mov     rcx, rsi; hFile
0x18002f7d0  call    cs:__imp_GetFileInformationByHandle
0x18002f7d6  mov     ecx, eax
0x18002f7d8  xor     eax, eax
0x18002f7da  test    ecx, ecx
0x18002f7dc  mov     [r14+34h], ecx
0x18002f7e0  setz    al
0x18002f7e3  or      [r14+98h], eax
0x18002f7ea  test    ecx, ecx
0x18002f7ec  jnz     short loc_18002F824
0x18002f7ee  call    cs:__imp_GetLastError
0x18002f7f4  test    eax, eax
0x18002f7f6  jle     short loc_18002F800
0x18002f7f8  movzx   eax, ax
0x18002f7fb  or      eax, 80070000h
0x18002f800  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f807  cmp     rcx, r12
0x18002f80a  jz      loc_18002F940
0x18002f810  test    [rcx+1Ch], r15b
0x18002f814  jz      loc_18002F940
0x18002f81a  mov     edx, 31h ; '1'
0x18002f81f  mov     r9d, eax
0x18002f822  jmp     short loc_18002F7C2
0x18002f824  cmp     dword ptr [r14+78h], 0
0x18002f829  jz      loc_18002F8D3
0x18002f82f  mov     rsi, [rbp+var_40]
0x18002f833  lea     r8, [rbp+var_38]; lpFileInformation
0x18002f837  mov     rcx, rsi; hFile
0x18002f83a  mov     r9d, 28h ; '('; dwBufferSize
0x18002f840  xor     edx, edx; FileInformationClass
0x18002f842  call    cs:__imp_GetFileInformationByHandleEx
0x18002f848  test    eax, eax
0x18002f84a  jz      short loc_18002F894
0x18002f84c  or      dword ptr [rbp+var_18], r15d
0x18002f850  lea     r8, [rbp+var_38]; lpFileInformation
0x18002f854  mov     r9d, 28h ; '('; dwBufferSize
0x18002f85a  xor     edx, edx; FileInformationClass
0x18002f85c  mov     rcx, rsi; hFile
0x18002f85f  call    cs:__imp_SetFileInformationByHandle
0x18002f865  test    eax, eax
0x18002f867  jnz     short loc_18002F8D3
0x18002f869  mov     rax, cs:WPP_GLOBAL_Control
0x18002f870  cmp     rax, r12
0x18002f873  jz      short loc_18002F8D3
0x18002f875  test    [rax+1Ch], r15b
0x18002f879  jz      short loc_18002F8D3
0x18002f87b  call    cs:__imp_GetLastError
0x18002f881  test    eax, eax
0x18002f883  jle     short loc_18002F88D
0x18002f885  movzx   eax, ax
0x18002f888  or      eax, 80070000h
0x18002f88d  mov     edx, 32h ; '2'
0x18002f892  jmp     short loc_18002F8BD
0x18002f894  mov     rax, cs:WPP_GLOBAL_Control
0x18002f89b  cmp     rax, r12
0x18002f89e  jz      short loc_18002F8D3
0x18002f8a0  test    [rax+1Ch], r15b
0x18002f8a4  jz      short loc_18002F8D3
0x18002f8a6  call    cs:__imp_GetLastError
0x18002f8ac  test    eax, eax
0x18002f8ae  jle     short loc_18002F8B8
0x18002f8b0  movzx   eax, ax
0x18002f8b3  or      eax, 80070000h
0x18002f8b8  mov     edx, 33h ; '3'
0x18002f8bd  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
