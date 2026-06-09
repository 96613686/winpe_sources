# Staging::FindAllFiles(ID_UPDATE const &,int const volatile &,int &,FileId &,int &,int &,int &,_WIN32_FIND_DATAW &,_WIN32_FIND_DATAW &,std::list<GVSN,std::allocator<GVSN>> &)

- ea: `0x14014c814`
- end: `0x14014ce6d`
- name: `?FindAllFiles@Staging@@AEAAPEAVFrsStatus@@AEBVID_UPDATE@@AEDHAEAHAEAVFileId@@222AEAU_WIN32_FIND_DATAW@@4AEAV?$list@VGVSN@@V?$allocator@VGVSN@@@std@@@std@@@Z`
- size: `1625`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x14014fb04`

## callees

- `0x1400036a0`
- `0x1400046cc`
- `0x14000c870`
- `0x14000ee94`
- `0x140024868`
- `0x1400248f4`
- `0x140024be4`
- `0x140028fcc`
- `0x14009f544`
- `0x14011c03c`
- `0x14014c814`
- `0x14014da64`
- `0x14014e7e4`
- `0x14014f878`
- `0x14014f9cc`
- `0x140150340`
- `0x1401b9494`
- `0x1401bebec`

## import_xrefs

- `KERNEL32!FindFirstFileW` at `0x14014c964`
- `KERNEL32!FindFirstFileW` at `0x14014c964`
- `KERNEL32!FindClose` at `0x14014cc78`
- `KERNEL32!FindClose` at `0x14014cd2c`
- `KERNEL32!FindClose` at `0x14014cc78`
- `KERNEL32!FindClose` at `0x14014cd2c`
- `KERNEL32!FindNextFileW` at `0x14014cc52`
- `KERNEL32!FindNextFileW` at `0x14014cc52`
- `KERNEL32!GetLastError` at `0x14014cc62`
- `KERNEL32!GetLastError` at `0x14014cd43`
- `KERNEL32!GetLastError` at `0x14014cc62`
- `KERNEL32!GetLastError` at `0x14014cd43`
- `KERNEL32!GetCurrentThreadId` at `0x14014cc8c`
- `KERNEL32!GetCurrentThreadId` at `0x14014ccd7`
- `KERNEL32!GetCurrentThreadId` at `0x14014cd73`
- `KERNEL32!GetCurrentThreadId` at `0x14014cdbd`
- `KERNEL32!GetCurrentThreadId` at `0x14014cc8c`
- `KERNEL32!GetCurrentThreadId` at `0x14014ccd7`
- `KERNEL32!GetCurrentThreadId` at `0x14014cd73`
- `KERNEL32!GetCurrentThreadId` at `0x14014cdbd`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Staging::FindAllFiles(
        __int64 a1,
        const struct UID *a2,
        _DWORD *a3,
        _DWORD *a4,
        struct FileId *a5,
        _DWORD *a6,
        _DWORD *a7,
        _DWORD *a8,
        _OWORD *a9,
        _OWORD *a10,
        __int64 a11)
{
  __int64 v14; // rbx
  __int64 v15; // r14
  unsigned int *v16; // r15
  __int64 v17; // rcx
  const unsigned __int16 *v18; // rax
  HANDLE FirstFileW; // rax
  __int64 v20; // rcx
  int v21; // ecx
  int v22; // ecx
  _DWORD *v23; // r13
  __int64 v24; // rax
  WCHAR *cFileName; // rcx
  __int64 v26; // rax
  int v27; // r8d
  int v28; // edx
  __int64 v29; // rax
  WCHAR *v30; // rcx
  __int64 v31; // rax
  int v32; // r8d
  int v33; // edx
  _OWORD *v34; // rax
  struct _WIN32_FIND_DATAW *p_FindFileData; // rcx
  __int64 v36; // rdx
  __int64 v37; // rax
  WCHAR *v38; // rcx
  __int64 v39; // rax
  int v40; // r8d
  int v41; // edx
  __int64 v42; // rdx
  DWORD LastError; // edi
  DWORD CurrentThreadId; // eax
  __int64 v45; // rcx
  DWORD v46; // eax
  __int64 v47; // rcx
  DWORD v48; // ebx
  DWORD v49; // eax
  __int64 v50; // rcx
  DWORD v51; // eax
  __int64 v52; // rcx
  __int64 v54; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v55; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD *v56; // [rsp+60h] [rbp-A0h]
  _DWORD *v57; // [rsp+68h] [rbp-98h]
  _DWORD *v58; // [rsp+70h] [rbp-90h]
  void **v59; // [rsp+78h] [rbp-88h] BYREF
  __int64 v60; // [rsp+80h] [rbp-80h] BYREF
  _OWORD *v61; // [rsp+88h] [rbp-78h]
  _OWORD *v62; // [rsp+90h] [rbp-70h]
  __int64 v63; // [rsp+98h] [rbp-68h]
  const wchar_t *v64; // [rsp+A0h] [rbp-60h] BYREF
  int v65; // [rsp+A8h] [rbp-58h]
  int v66; // [rsp+ACh] [rbp-54h]
  const wchar_t *v67; // [rsp+B0h] [rbp-50h]
  __int128 v68; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v69; // [rsp+C8h] [rbp-38h]
  __int128 v70; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v71; // [rsp+E0h] [rbp-20h]
  _BYTE v72[32]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v73[32]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v74[32]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v75[40]; // [rsp+148h] [rbp+48h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+170h] [rbp+70h] BYREF

  v55 = a3;
  v58 = a6;
  v56 = a7;
  v57 = a8;
  v61 = a9;
  v62 = a10;
  v63 = a11;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FilePath::FilePath((FilePath *)&v59);
  std::wstring::wstring(v75);
  std::wstring::wstring(v74);
  std::wstring::wstring(v73);
  std::wstring::wstring(v72);
  v14 = -1;
  v54 = -1;
  v15 = 0;
  v16 = 0;
  *a6 = 0;
  *v56 = 0;
  *v57 = 0;
  if ( !(unsigned int)Staging::StageSubDirectory::GetFilePath(
                        (Staging::StageSubDirectory *)(a1 + 152),
                        a2,
                        (struct FilePath *)&v59,
                        a5) )
  {
    *a4 = 0;
    goto LABEL_46;
  }
  *a4 = 1;
  Staging::MakeStageNameFromUID(v17, a2, v75);
  v18 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v75);
  FilePath::Append((FilePath *)&v59, v18);
  FirstFileW = FindFirstFileW((LPCWSTR)(v60 + 18), &FindFileData);
  v20 = -1;
  if ( FirstFileW != (HANDLE)-1LL )
  {
    v14 = (__int64)FirstFileW;
    v54 = (__int64)FirstFileW;
    v20 = (__int64)FirstFileW;
  }
  if ( v20 && v20 != -1 )
  {
    Staging::MakeStageName(v20, (_DWORD)a2, (_DWORD)a2 + 24, 1, (__int64)v73);
    Staging::MakeStageName(v21, (_DWORD)a2, (_DWORD)a2 + 24, 2, (__int64)v74);
    Staging::MakeStageName(v22, (_DWORD)a2, (_DWORD)a2 + 24, 3, (__int64)v72);
    v23 = v55;
    while ( 1 )
    {
      if ( v16 )
        goto LABEL_45;
      if ( (unsigned __int64)(v14 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        goto LABEL_46;
      v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v74);
      cFileName = FindFileData.cFileName;
      v26 = v24 - (_QWORD)FindFileData.cFileName;
      do
      {
        v27 = *(WCHAR *)((char *)cFileName + v26);
        v28 = *cFileName - v27;
        if ( v28 )
          break;
        ++cFileName;
      }
      while ( v27 );
      if ( !v28 )
      {
        *v58 = 1;
        FindClose((HANDLE)v14);
        v54 = -1;
        goto LABEL_46;
      }
      v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v73);
      v30 = FindFileData.cFileName;
      v31 = v29 - (_QWORD)FindFileData.cFileName;
      do
      {
        v32 = *(WCHAR *)((char *)v30 + v31);
        v33 = *v30 - v32;
        if ( v33 )
          break;
        ++v30;
      }
      while ( v32 );
      if ( !v33 )
        break;
      v37 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v72);
      v38 = FindFileData.cFileName;
      v39 = v37 - (_QWORD)FindFileData.cFileName;
      do
      {
        v40 = *(WCHAR *)((char *)v38 + v39);
        v41 = *v38 - v40;
        if ( v41 )
          break;
        ++v38;
      }
      while ( v40 );
      if ( !v41 )
      {
        *v57 = 1;
        v34 = v62;
        p_FindFileData = &FindFileData;
        v42 = 4;
        do
        {
          *v34 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
          v34[1] = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
          v34[2] = *(_OWORD *)&p_FindFileData->nFileSizeLow;
          v34[3] = *(_OWORD *)&p_FindFileData->cFileName[2];
          v34[4] = *(_OWORD *)&p_FindFileData->cFileName[10];
          v34[5] = *(_OWORD *)&p_FindFileData->cFileName[18];
          v34[6] = *(_OWORD *)&p_FindFileData->cFileName[26];
          v34 += 8;
          *(v34 - 1) = *(_OWORD *)&p_FindFileData->cFileName[34];
          p_FindFileData = (struct _WIN32_FIND_DATAW *)((char *)p_FindFileData + 128);
          --v42;
        }
        while ( v42 );
        goto LABEL_27;
      }
      v70 = 0;
      v71 = 0;
      v68 = 0;
      v69 = 0;
      if ( Staging::ParseStageName(
             (Staging *)v38,
             FindFileData.cFileName,
             0,
             (struct UID *)&v70,
             (struct GVSN *)&v68,
             (enum Staging::FILE_STATE *)&v55,
             0) )
      {
        std::list<GVSN>::push_back(v63, &v68);
        if ( g_DebugLog )
        {
          if ( LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
          {
            v64 = L"Staging::FindAllFiles";
            v65 = 4456;
            v66 = 5;
            v67 = L"STAG";
            dbgobj::DbgPrint<unsigned short,unsigned short [39]>(
              &v64,
              L"Older version found:%s",
              FindFileData.cFileName);
          }
        }
      }
LABEL_33:
      if ( FindNextFileW((HANDLE)v14, &FindFileData) )
        goto LABEL_37;
      LastError = GetLastError();
      if ( LastError == 18 )
      {
        FindClose((HANDLE)v14);
        v54 = -1;
        goto LABEL_37;
      }
      CurrentThreadId = GetCurrentThreadId();
      v16 = (unsigned int *)FrsStatusList::PushNewError(
                              v45,
                              LastError,
                              0,
                              1,
                              "base\\fs\\remotefs\\frs\\src\\sync\\staging.cpp",
                              "Staging::FindAllFiles",
                              4468,
                              CurrentThreadId,
                              0);
      if ( !v16 )
      {
LABEL_37:
        if ( *v23 )
        {
          v46 = GetCurrentThreadId();
          v16 = (unsigned int *)FrsStatusList::PushNewError(
                                  v47,
                                  9033,
                                  0,
                                  3,
                                  "base\\fs\\remotefs\\frs\\src\\sync\\staging.cpp",
                                  "Staging::FindAllFiles",
                                  4473,
                                  v46,
                                  0);
        }
        v14 = v54;
      }
    }
    *v56 = 1;
    v34 = v61;
    p_FindFileData = &FindFileData;
    v36 = 4;
    do
    {
      *v34 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
      v34[1] = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
      v34[2] = *(_OWORD *)&p_FindFileData->nFileSizeLow;
      v34[3] = *(_OWORD *)&p_FindFileData->cFileName[2];
      v34[4] = *(_OWORD *)&p_FindFileData->cFileName[10];
      v34[5] = *(_OWORD *)&p_FindFileData->cFileName[18];
      v34[6] = *(_OWORD *)&p_FindFileData->cFileName[26];
      v34 += 8;
      *(v34 - 1) = *(_OWORD *)&p_FindFileData->cFileName[34];
      p_FindFileData = (struct _WIN32_FIND_DATAW *)((char *)p_FindFileData + 128);
      --v36;
    }
    while ( v36 );
LABEL_27:
    *v34 = *(_OWORD *)&p_FindFileData->dwFileAttributes;
    v34[1] = *(_OWORD *)&p_FindFileData->ftLastAccessTime.dwHighDateTime;
    v34[2] = *(_OWORD *)&p_FindFileData->nFileSizeLow;
    v34[3] = *(_OWORD *)&p_FindFileData->cFileName[2];
    v34[4] = *(_OWORD *)&p_FindFileData->cFileName[10];
    goto LABEL_33;
  }
  v48 = GetLastError();
  if ( v48 == 3 )
  {
    Staging::StageSubDirectory::InvalidatePath((Staging::StageSubDirectory *)(a1 + 152), a2);
  }
  else if ( v48 != 2 )
  {
    v49 = GetCurrentThreadId();
    v16 = (unsigned int *)FrsStatusList::PushNewError(
                            v50,
                            v48,
                            0,
                            1,
                            "base\\fs\\remotefs\\frs\\src\\sync\\staging.cpp",
                            "Staging::FindAllFiles",
                            4487,
                            v49,
                            0);
    if ( v16 )
    {
LABEL_45:
      v51 = GetCurrentThreadId();
      v15 = FrsStatusList::PushNewError(
              v52,
              v16[1],
              v16[2],
              *v16,
              "base\\fs\\remotefs\\frs\\src\\sync\\staging.cpp",
              "Staging::FindAllFiles",
              4491,
              v51,
              v16);
    }
  }
LABEL_46:
  scoped_any<void *,close_fun<int (*)(void *),&int FindClose(void *)>,value_const<void *,-1>,0>::~scoped_any<void *,close_fun<int (*)(void *),&int FindClose(void *)>,value_const<void *,-1>,0>(&v54);
  std::wstring::~wstring(v72);
  std::wstring::~wstring(v73);
  std::wstring::~wstring(v74);
  std::wstring::~wstring(v75);
  v59 = &FilePath::`vftable';
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v60);
  return v15;
}

```

## disassembly

```asm
0x14014c814  mov     [rsp-8+arg_10], rbx
0x14014c819  push    rbp
0x14014c81a  push    rsi
0x14014c81b  push    rdi
0x14014c81c  push    r12
0x14014c81e  push    r13
0x14014c820  push    r14
0x14014c822  push    r15
0x14014c824  lea     rbp, [rsp-2D0h]
0x14014c82c  sub     rsp, 3D0h
0x14014c833  mov     rax, cs:__security_cookie
0x14014c83a  xor     rax, rsp
0x14014c83d  mov     [rbp+300h+var_40], rax
0x14014c844  mov     r12, r9
0x14014c847  mov     [rsp+400h+var_3A8], r8
0x14014c84c  mov     r13, rdx
0x14014c84f  mov     rsi, rcx
0x14014c852  mov     rdi, [rbp+300h+arg_20]
0x14014c859  mov     rax, [rbp+300h+arg_28]
0x14014c860  mov     [rsp+400h+var_390], rax
0x14014c865  mov     rax, [rbp+300h+arg_30]
0x14014c86c  mov     [rsp+400h+var_3A0], rax
0x14014c871  mov     rax, [rbp+300h+arg_38]
0x14014c878  mov     [rsp+400h+var_398], rax
0x14014c87d  mov     rax, [rbp+300h+arg_40]
0x14014c884  mov     [rbp+300h+var_378], rax
0x14014c888  mov     rax, [rbp+300h+arg_48]
0x14014c88f  mov     [rbp+300h+var_370], rax
0x14014c893  mov     rax, [rbp+300h+arg_50]
0x14014c89a  mov     [rbp+300h+var_368], rax
0x14014c89e  xor     edx, edx; Val
0x14014c8a0  mov     r8d, 250h; Size
0x14014c8a6  lea     rcx, [rbp+300h+FindFileData]; void *
0x14014c8aa  call    memset_0
0x14014c8af  lea     rcx, [rsp+400h+var_388]; this
0x14014c8b4  call    ??0FilePath@@QEAA@XZ; FilePath::FilePath(void)
0x14014c8b9  nop
0x14014c8ba  lea     rcx, [rbp+300h+var_2B8]
0x14014c8be  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14014c8c3  nop
0x14014c8c4  lea     rcx, [rbp+300h+var_2D8]
0x14014c8c8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14014c8cd  nop
0x14014c8ce  lea     rcx, [rbp+300h+var_2F8]
0x14014c8d2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14014c8d7  nop
0x14014c8d8  lea     rcx, [rbp+300h+var_318]
0x14014c8dc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x14014c8e1  nop
0x14014c8e2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14014c8e6  mov     [rsp+400h+var_3B0], rbx
0x14014c8eb  xor     r14d, r14d
0x14014c8ee  mov     r15d, r14d
0x14014c8f1  mov     rax, [rsp+400h+var_390]
0x14014c8f6  mov     [rax], r14d
0x14014c8f9  mov     rax, [rsp+400h+var_3A0]
0x14014c8fe  mov     [rax], r14d
0x14014c901  mov     rax, [rsp+400h+var_398]
0x14014c906  mov     [rax], r14d
0x14014c909  mov     r9, rdi; struct FileId *
0x14014c90c  lea     r8, [rsp+400h+var_388]; struct FilePath *
0x14014c911  mov     rdx, r13; struct UID *
0x14014c914  lea     rcx, [rsi+98h]; this
0x14014c91b  call    ?GetFilePath@StageSubDirectory@Staging@@QEAAHAEBVUID@@AEAVFilePath@@AEAVFileId@@@Z; Staging::StageSubDirectory::GetFilePath(UID const &,FilePath &,FileId &)
0x14014c920  test    eax, eax
0x14014c922  jnz     short loc_14014C92D
0x14014c924  mov     [r12], r14d
0x14014c928  jmp     loc_14014CDF7
0x14014c92d  mov     edi, 1
0x14014c932  mov     [r12], edi
0x14014c936  lea     r8, [rbp+300h+var_2B8]
0x14014c93a  mov     rdx, r13
0x14014c93d  call    ?MakeStageNameFromUID@Staging@@AEAAXAEBVUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Staging::MakeStageNameFromUID(UID const &,std::wstring &)
0x14014c942  lea     rcx, [rbp+300h+var_2B8]
0x14014c946  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14014c94b  mov     rdx, rax; unsigned __int16 *
0x14014c94e  lea     rcx, [rsp+400h+var_388]; this
0x14014c953  call    ?Append@FilePath@@QEAAXPEBG@Z; FilePath::Append(ushort const *)
0x14014c958  mov     rcx, [rbp+300h+var_380]
0x14014c95c  add     rcx, 12h; lpFileName
0x14014c960  lea     rdx, [rbp+300h+FindFileData]; lpFindFileData
0x14014c964  call    cs:__imp_FindFirstFileW
0x14014c96b  nop     dword ptr [rax+rax+00h]
0x14014c970  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14014c974  cmp     rax, rcx
0x14014c977  jz      short loc_14014C984
0x14014c979  mov     rbx, rax
0x14014c97c  mov     [rsp+400h+var_3B0], rax
0x14014c981  mov     rcx, rax
0x14014c984  test    rcx, rcx
0x14014c987  jz      loc_14014CD43
0x14014c98d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14014c991  jz      loc_14014CD43
0x14014c997  lea     rdi, [r13+18h]
0x14014c99b  lea     rax, [rbp+300h+var_2F8]
0x14014c99f  mov     [rsp+400h+var_3E0], rax
0x14014c9a4  mov     r9d, 1
0x14014c9aa  mov     r8, rdi
0x14014c9ad  mov     rdx, r13
0x14014c9b0  call    ?MakeStageName@Staging@@AEAAXAEBVUID@@AEBVGVSN@@W4FILE_STATE@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Staging::MakeStageName(UID const &,GVSN const &,Staging::FILE_STATE,std::wstring &)
0x14014c9b5  lea     rax, [rbp+300h+var_2D8]
0x14014c9b9  mov     [rsp+400h+var_3E0], rax
0x14014c9be  mov     r9d, 2
0x14014c9c4  mov     r8, rdi
0x14014c9c7  mov     rdx, r13
0x14014c9ca  call    ?MakeStageName@Staging@@AEAAXAEBVUID@@AEBVGVSN@@W4FILE_STATE@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Staging::MakeStageName(UID const &,GVSN const &,Staging::FILE_STATE,std::wstring &)
0x14014c9cf  lea     rax, [rbp+300h+var_318]
0x14014c9d3  mov     [rsp+400h+var_3E0], rax
0x14014c9d8  mov     r9d, 3
0x14014c9de  mov     r8, rdi
0x14014c9e1  mov     rdx, r13
0x14014c9e4  call    ?MakeStageName@Staging@@AEAAXAEBVUID@@AEBVGVSN@@W4FILE_STATE@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Staging::MakeStageName(UID const &,GVSN const &,Staging::FILE_STATE,std::wstring &)
0x14014c9e9  lea     rsi, aStagingFindall; "Staging::FindAllFiles"
0x14014c9f0  lea     r12, aBaseFsRemotefs_61; "base\\fs\\remotefs\\frs\\src\\sync\\sta"...
0x14014c9f7  mov     r13, [rsp+400h+var_3A8]
0x14014c9fc  test    r15, r15
0x14014c9ff  jnz     loc_14014CDBD
0x14014ca05  lea     rax, [rbx-1]
0x14014ca09  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14014ca0d  ja      loc_14014CDF7
0x14014ca13  lea     rcx, [rbp+300h+var_2D8]
0x14014ca17  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14014ca1c  lea     rcx, [rbp+300h+FindFileData.cFileName]
0x14014ca23  sub     rax, rcx
0x14014ca26  movzx   edx, word ptr [rcx]
0x14014ca29  movzx   r8d, word ptr [rcx+rax]
0x14014ca2e  sub     edx, r8d
0x14014ca31  jnz     short loc_14014CA3C
0x14014ca33  add     rcx, 2
0x14014ca37  test    r8d, r8d
0x14014ca3a  jnz     short loc_14014CA26
0x14014ca3c  test    edx, edx
0x14014ca3e  jz      loc_14014CD1E
0x14014ca44  lea     rcx, [rbp+300h+var_2F8]
0x14014ca48  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14014ca4d  lea     rcx, [rbp+300h+FindFileData.cFileName]
0x14014ca54  sub     rax, rcx
0x14014ca57  movzx   edx, word ptr [rcx]
0x14014ca5a  movzx   r8d, word ptr [rcx+rax]
0x14014ca5f  sub     edx, r8d
0x14014ca62  jnz     short loc_14014CA6D
0x14014ca64  add     rcx, 2
0x14014ca68  test    r8d, r8d
0x14014ca6b  jnz     short loc_14014CA57
0x14014ca6d  test    edx, edx
0x14014ca6f  jnz     short loc_14014CAE0
0x14014ca71  mov     rax, [rsp+400h+var_3A0]
0x14014ca76  mov     dword ptr [rax], 1
0x14014ca7c  mov     rax, [rbp+300h+var_378]
0x14014ca80  lea     rcx, [rbp+300h+FindFileData]
0x14014ca84  mov     edx, 4
0x14014ca89  movups  xmm0, xmmword ptr [rcx]
0x14014ca8c  movups  xmmword ptr [rax], xmm0
0x14014ca8f  movups  xmm1, xmmword ptr [rcx+10h]
0x14014ca93  movups  xmmword ptr [rax+10h], xmm1
0x14014ca97  movups  xmm0, xmmword ptr [rcx+20h]
0x14014ca9b  movups  xmmword ptr [rax+20h], xmm0
0x14014ca9f  movups  xmm1, xmmword ptr [rcx+30h]
0x14014caa3  movups  xmmword ptr [rax+30h], xmm1
0x14014caa7  movups  xmm0, xmmword ptr [rcx+40h]
0x14014caab  movups  xmmword ptr [rax+40h], xmm0
0x14014caaf  movups  xmm1, xmmword ptr [rcx+50h]
0x14014cab3  movups  xmmword ptr [rax+50h], xmm1
0x14014cab7  movups  xmm0, xmmword ptr [rcx+60h]
0x14014cabb  movups  xmmword ptr [rax+60h], xmm0
0x14014cabf  lea     rax, [rax+80h]
0x14014cac6  movups  xmm1, xmmword ptr [rcx+70h]
0x14014caca  movups  xmmword ptr [rax-10h], xmm1
0x14014cace  lea     rcx, [rcx+80h]
0x14014cad5  sub     rdx, 1
0x14014cad9  jnz     short loc_14014CA89
0x14014cadb  jmp     loc_14014CB7B
0x14014cae0  lea     rcx, [rbp+300h+var_318]
0x14014cae4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14014cae9  lea     rcx, [rbp+300h+FindFileData.cFileName]
0x14014caf0  sub     rax, rcx
0x14014caf3  movzx   edx, word ptr [rcx]
0x14014caf6  movzx   r8d, word ptr [rcx+rax]
0x14014cafb  sub     edx, r8d
0x14014cafe  jnz     short loc_14014CB09
0x14014cb00  add     rcx, 2; this
0x14014cb04  test    r8d, r8d
0x14014cb07  jnz     short loc_14014CAF3
0x14014cb09  test    edx, edx
0x14014cb0b  jnz     loc_14014CBA6
0x14014cb11  mov     rax, [rsp+400h+var_398]
0x14014cb16  mov     dword ptr [rax], 1
0x14014cb1c  mov     rax, [rbp+300h+var_370]
0x14014cb20  lea     rcx, [rbp+300h+FindFileData]
0x14014cb24  mov     edx, 4
0x14014cb29  movups  xmm0, xmmword ptr [rcx]
0x14014cb2c  movups  xmmword ptr [rax], xmm0
0x14014cb2f  movups  xmm1, xmmword ptr [rcx+10h]
0x14014cb33  movups  xmmword ptr [rax+10h], xmm1
0x14014cb37  movups  xmm0, xmmword ptr [rcx+20h]
0x14014cb3b  movups  xmmword ptr [rax+20h], xmm0
0x14014cb3f  movups  xmm1, xmmword ptr [rcx+30h]
0x14014cb43  movups  xmmword ptr [rax+30h], xmm1
0x14014cb47  movups  xmm0, xmmword ptr [rcx+40h]
0x14014cb4b  movups  xmmword ptr [rax+40h], xmm0
0x14014cb4f  movups  xmm1, xmmword ptr [rcx+50h]
0x14014cb53  movups  xmmword ptr [rax+50h], xmm1
0x14014cb57  movups  xmm0, xmmword ptr [rcx+60h]
0x14014cb5b  movups  xmmword ptr [rax+60h], xmm0
0x14014cb5f  lea     rax, [rax+80h]
0x14014cb66  movups  xmm1, xmmword ptr [rcx+70h]
0x14014cb6a  movups  xmmword ptr [rax-10h], xmm1
0x14014cb6e  lea     rcx, [rcx+80h]
0x14014cb75  sub     rdx, 1
0x14014cb79  jnz     short loc_14014CB29
0x14014cb7b  movups  xmm0, xmmword ptr [rcx]
0x14014cb7e  movups  xmmword ptr [rax], xmm0
0x14014cb81  movups  xmm1, xmmword ptr [rcx+10h]
0x14014cb85  movups  xmmword ptr [rax+10h], xmm1
0x14014cb89  movups  xmm0, xmmword ptr [rcx+20h]
0x14014cb8d  movups  xmmword ptr [rax+20h], xmm0
0x14014cb91  movups  xmm1, xmmword ptr [rcx+30h]
0x14014cb95  movups  xmmword ptr [rax+30h], xmm1
0x14014cb99  movups  xmm0, xmmword ptr [rcx+40h]
0x14014cb9d  movups  xmmword ptr [rax+40h], xmm0
0x14014cba1  jmp     loc_14014CC4B
0x14014cba6  xorps   xmm0, xmm0
0x14014cba9  movups  [rbp+300h+var_330], xmm0
0x14014cbad  mov     [rbp+300h+var_320], r14
0x14014cbb1  xorps   xmm1, xmm1
0x14014cbb4  movups  [rbp+300h+var_348], xmm1
0x14014cbb8  mov     [rbp+300h+var_338], r14
0x14014cbbc  mov     [rsp+400h+var_3D0], r14; int *
0x14014cbc1  lea     rax, [rsp+400h+var_3A8]
0x14014cbc6  mov     [rsp+400h+var_3D8], rax; enum Staging::FILE_STATE *
0x14014cbcb  lea     rax, [rbp+300h+var_348]
0x14014cbcf  mov     [rsp+400h+var_3E0], rax; struct GVSN *
0x14014cbd4  lea     r9, [rbp+300h+var_330]; struct UID *
0x14014cbd8  xor     r8d, r8d; int
0x14014cbdb  lea     rdx, [rbp+300h+FindFileData.cFileName]; unsigned __int16 *
0x14014cbe2  call    ?ParseStageName@Staging@@AEAAHPEBGHAEAVUID@@AEAVGVSN@@AEAW4FILE_STATE@1@PEAH@Z; Staging::ParseStageName(ushort const *,int,UID &,GVSN &,Staging::FILE_STATE &,int *)
0x14014cbe7  test    eax, eax
0x14014cbe9  jz      short loc_14014CC4B
0x14014cbeb  lea     rdx, [rbp+300h+var_348]
0x14014cbef  mov     rcx, [rbp+300h+var_368]
0x14014cbf3  call    ?push_back@?$list@VGVSN@@V?$allocator@VGVSN@@@std@@@std@@QEAAXAEBVGVSN@@@Z; std::list<GVSN>::push_back(GVSN const &)
0x14014cbf8  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x14014cbff  test    rax, rax
0x14014cc02  jz      short loc_14014CC4B
0x14014cc04  cmp     [rax+40h], r14d
0x14014cc08  jz      short loc_14014CC4B
0x14014cc0a  cmp     dword ptr [rax+38h], 5
0x14014cc0e  jl      short loc_14014CC4B
0x14014cc10  lea     rax, aStagingFindall_0; "Staging::FindAllFiles"
0x14014cc17  mov     [rbp+300h+var_360], rax
0x14014cc1b  mov     [rbp+300h+var_358], 1168h
0x14014cc22  mov     [rbp+300h+var_354], 5
0x14014cc29  lea     rax, aStag; "STAG"
0x14014cc30  mov     [rbp+300h+var_350], rax
0x14014cc34  lea     r8, [rbp+300h+FindFileData.cFileName]
0x14014cc3b  lea     rdx, aOlderVersionFo; "Older version found:%s"
0x14014cc42  lea     rcx, [rbp+300h+var_360]
0x14014cc46  call    ??$DbgPrint@G$$BY0CH@G@dbgobj@@QEAA_KPEBGAEAY0CH@$$CBG@Z; dbgobj::DbgPrint<ushort,ushort [39]>(ushort const *,ushort const (&)[39])
0x14014cc4b  lea     rdx, [rbp+300h+FindFileData]; lpFindFileData
0x14014cc4f  mov     rcx, rbx; hFindFile
0x14014cc52  call    cs:__imp_FindNextFileW
0x14014cc59  nop     dword ptr [rax+rax+00h]
0x14014cc5e  test    eax, eax
0x14014cc60  jnz     short loc_14014CCCF
0x14014cc62  call    cs:__imp_GetLastError
0x14014cc69  nop     dword ptr [rax+rax+00h]
0x14014cc6e  mov     edi, eax
0x14014cc70  cmp     eax, 12h
0x14014cc73  jnz     short loc_14014CC8C
0x14014cc75  mov     rcx, rbx; hFindFile
0x14014cc78  call    cs:__imp_FindClose
0x14014cc7f  nop     dword ptr [rax+rax+00h]
0x14014cc84  or      [rsp+400h+var_3B0], 0FFFFFFFFFFFFFFFFh
0x14014cc8a  jmp     short loc_14014CCCF
0x14014cc8c  call    cs:__imp_GetCurrentThreadId
0x14014cc93  nop     dword ptr [rax+rax+00h]
0x14014cc98  mov     [rsp+400h+var_3C0], r14
0x14014cc9d  mov     [rsp+400h+var_3C8], eax
0x14014cca1  mov     dword ptr [rsp+400h+var_3D0], 1174h
0x14014cca9  mov     [rsp+400h+var_3D8], rsi
0x14014ccae  mov     [rsp+400h+var_3E0], r12
0x14014ccb3  mov     r9d, 1
0x14014ccb9  xor     r8d, r8d
0x14014ccbc  mov     edx, edi
0x14014ccbe  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14014ccc3  mov     r15, rax
0x14014ccc6  test    rax, rax
0x14014ccc9  jnz     loc_14014C9FC
0x14014cccf  mov     ecx, [r13+0]
0x14014ccd3  test    ecx, ecx
0x14014ccd5  jz      short loc_14014CD14
0x14014ccd7  call    cs:__imp_GetCurrentThreadId
0x14014ccde  nop     dword ptr [rax+rax+00h]
0x14014cce3  mov     [rsp+400h+var_3C0], r14
0x14014cce8  mov     [rsp+400h+var_3C8], eax
0x14014ccec  mov     dword ptr [rsp+400h+var_3D0], 1179h
0x14014ccf4  mov     [rsp+400h+var_3D8], rsi
0x14014ccf9  mov     [rsp+400h+var_3E0], r12
0x14014ccfe  mov     r9d, 3
0x14014cd04  xor     r8d, r8d
  ... truncated ...
```
