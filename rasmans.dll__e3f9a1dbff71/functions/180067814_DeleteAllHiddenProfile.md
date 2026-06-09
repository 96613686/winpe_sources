# DeleteAllHiddenProfile

- ea: `0x180067814`
- end: `0x180067d5d`
- name: `DeleteAllHiddenProfile`
- size: `1353`
- prototype: `__int64 __fastcall(wchar_t *Str)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18007b698`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000e650`
- `0x18005bfa4`
- `0x18005d488`
- `0x180065328`
- `0x180066c44`
- `0x180067814`
- `0x180069260`
- `0x1800697e0`
- `0x18007b46c`
- `0x18007b698`
- `0x18007c56c`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800679be`
- `msvcrt!wcsstr` at `0x1800679be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067a10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067a6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067ae6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067a10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067a6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067ae6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180067cce`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180067ce5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180067cce`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180067ce5`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180067caf`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180067caf`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180067ad7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180067ad7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180067cfb`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180067cfb`
- `USERENV!GetProfilesDirectoryW` at `0x1800679de`
- `USERENV!GetProfilesDirectoryW` at `0x1800679de`

## string_xrefs

- `0x1800679b4`: `\system32\`

## pseudocode

```c
__int64 __fastcall DeleteAllHiddenProfile(wchar_t *Str, _WORD *a2)
{
  struct _LIST_ENTRY *v4; // rbx
  unsigned int AppDataFolderPathUnderUserProfile; // edi
  __int64 FirstFileW; // r12
  DWORD FileNameFromPath; // eax
  __int64 v8; // rdx
  wchar_t *v9; // rax
  wchar_t *v10; // rbx
  struct _LIST_ENTRY *Flink; // rbx
  char LastError; // al
  int v13; // edx
  const wchar_t *v14; // rcx
  unsigned int PbkAndEntryName; // eax
  unsigned int v16; // eax
  DWORD cchSize; // [rsp+50h] [rbp-B0h] BYREF
  HGLOBAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  HGLOBAL v20; // [rsp+60h] [rbp-A0h] BYREF
  size_t v21; // [rsp+68h] [rbp-98h] BYREF
  __int128 v22[3]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v23; // [rsp+A0h] [rbp-60h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v25[44]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v26[548]; // [rsp+32Ch] [rbp+22Ch] BYREF
  WCHAR ProfileDir[264]; // [rsp+550h] [rbp+450h] BYREF
  WCHAR v28[264]; // [rsp+760h] [rbp+660h] BYREF
  WCHAR FileName[264]; // [rsp+970h] [rbp+870h] BYREF

  if ( Str && a2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      WPP_SF_SS(
        WPP_GLOBAL_Control[1].Flink,
        778,
        (unsigned int)&WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
        (_DWORD)Str,
        (__int64)a2);
LABEL_11:
      v4 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 779, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
      goto LABEL_11;
    }
  }
  AppDataFolderPathUnderUserProfile = 0;
  memset_0(FileName, 0, 0x20Au);
  memset_0(v28, 0, 0x20Au);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(v25, 0, 0x250u);
  v23 = 0;
  v21 = 0;
  hMem = 0;
  memset(v22, 0, sizeof(v22));
  v20 = 0;
  FirstFileW = -1;
  memset_0(ProfileDir, 0, 0x20Au);
  if ( !a2 )
    goto LABEL_62;
  FileNameFromPath = GetFileNameFromPath(Str, &hMem);
  AppDataFolderPathUnderUserProfile = FileNameFromPath;
  if ( FileNameFromPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v8 = 780;
LABEL_18:
      WPP_SF_d(v4[1].Flink, v8, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, FileNameFromPath);
LABEL_61:
      v4 = WPP_GLOBAL_Control;
      goto LABEL_62;
    }
    goto LABEL_62;
  }
  v9 = wcsstr(Str, L"\\system32\\");
  cchSize = 261;
  v10 = v9;
  if ( !GetProfilesDirectoryW(ProfileDir, &cchSize) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_62;
    }
    Flink = WPP_GLOBAL_Control[1].Flink;
    LastError = GetLastError();
    v13 = 781;
    goto LABEL_24;
  }
  AppDataFolderPathUnderUserProfile = GetAppDataFolderPathUnderUserProfile((__int64 *)&v20);
  if ( AppDataFolderPathUnderUserProfile )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_62;
    }
    Flink = WPP_GLOBAL_Control[1].Flink;
    LastError = GetLastError();
    v13 = 782;
LABEL_24:
    WPP_SF_Sd((_DWORD)Flink, v13, (unsigned int)&WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, (_DWORD)a2, LastError);
    goto LABEL_61;
  }
  FileNameFromPath = StringCchPrintfWrapW(FileName, 261, L"%s\\*", ProfileDir);
  AppDataFolderPathUnderUserProfile = FileNameFromPath;
  if ( FileNameFromPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v8 = 783;
      goto LABEL_18;
    }
  }
  else
  {
    FirstFileW = (__int64)FindFirstFileW(FileName, &FindFileData);
    if ( FirstFileW != -1 )
    {
      do
      {
        if ( (FindFileData.dwFileAttributes & 0x10) != 0
          && (FindFileData.cFileName[0] != 46
           || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2])) )
        {
          v14 = L"_hiddenPBK\\System\\";
          if ( !v10 )
            v14 = L"_hiddenPbk\\";
          if ( !(unsigned int)StringCchPrintfWrapW(
                                v28,
                                261,
                                L"%s\\%s\\%s\\%s\\%s%s",
                                ProfileDir,
                                FindFileData.cFileName,
                                v20,
                                L"Microsoft\\Network\\Connections\\Pbk",
                                v14,
                                hMem)
            && (unsigned int)FFileExists(v28) )
          {
            PbkAndEntryName = GetPbkAndEntryName(v28, (__int64)a2, 0x408u, v22, &v21);
            AppDataFolderPathUnderUserProfile = PbkAndEntryName;
            if ( PbkAndEntryName )
            {
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_SSD(
                  WPP_GLOBAL_Control[1].Flink,
                  785,
                  (unsigned int)&WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
                  (_DWORD)a2,
                  (__int64)v26,
                  PbkAndEntryName);
              }
            }
            else
            {
              v21 = 0;
              v16 = WritePhonebookFile(v22, a2);
              AppDataFolderPathUnderUserProfile = v16;
              if ( v16
                && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
                && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
              {
                WPP_SF_SSD(
                  WPP_GLOBAL_Control[1].Flink,
                  786,
                  (unsigned int)&WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
                  (_DWORD)a2,
                  (__int64)v26,
                  v16);
              }
              ClosePhonebookFile(v22);
            }
          }
        }
      }
      while ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) );
      goto LABEL_61;
    }
    FileNameFromPath = GetLastError();
    AppDataFolderPathUnderUserProfile = FileNameFromPath;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v8 = 784;
      goto LABEL_18;
    }
  }
LABEL_62:
  if ( hMem )
  {
    GlobalFree(hMem);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v20 )
  {
    GlobalFree(v20);
    v4 = WPP_GLOBAL_Control;
  }
  if ( FirstFileW != -1 )
  {
    FindClose((HANDLE)FirstFileW);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
    WPP_SF_d(v4[1].Flink, 787, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, AppDataFolderPathUnderUserProfile);
  return AppDataFolderPathUnderUserProfile;
}

```

## disassembly

```asm
0x180067814  mov     [rsp-8+arg_10], rbx
0x180067819  push    rbp
0x18006781a  push    rsi
0x18006781b  push    rdi
0x18006781c  push    r12
0x18006781e  push    r13
0x180067820  push    r14
0x180067822  push    r15
0x180067824  lea     rbp, [rsp-0A90h]
0x18006782c  sub     rsp, 0B90h
0x180067833  mov     rax, cs:__security_cookie
0x18006783a  xor     rax, rsp
0x18006783d  mov     [rbp+0AC0h+var_40], rax
0x180067844  mov     r14, rdx
0x180067847  mov     r15, rcx
0x18006784a  test    rcx, rcx
0x18006784d  jz      short loc_180067892
0x18006784f  test    rdx, rdx
0x180067852  jz      short loc_180067892
0x180067854  mov     rbx, cs:WPP_GLOBAL_Control
0x18006785b  lea     rsi, WPP_GLOBAL_Control
0x180067862  cmp     rbx, rsi
0x180067865  jz      short loc_1800678CD
0x180067867  test    byte ptr [rbx+1Ch], 80h
0x18006786b  jz      short loc_1800678CD
0x18006786d  cmp     byte ptr [rbx+19h], 6
0x180067871  jb      short loc_1800678CD
0x180067873  mov     r9, rcx
0x180067876  mov     [rsp+0BC0h+var_BA0], r14
0x18006787b  mov     rcx, [rbx+10h]
0x18006787f  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180067886  mov     edx, 30Ah
0x18006788b  call    WPP_SF_SS
0x180067890  jmp     short loc_1800678C6
0x180067892  mov     rbx, cs:WPP_GLOBAL_Control
0x180067899  lea     rsi, WPP_GLOBAL_Control
0x1800678a0  cmp     rbx, rsi
0x1800678a3  jz      short loc_1800678CD
0x1800678a5  test    byte ptr [rbx+1Ch], 80h
0x1800678a9  jz      short loc_1800678CD
0x1800678ab  cmp     byte ptr [rbx+19h], 6
0x1800678af  jb      short loc_1800678CD
0x1800678b1  mov     rcx, [rbx+10h]
0x1800678b5  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800678bc  mov     edx, 30Bh
0x1800678c1  call    WPP_SF_
0x1800678c6  mov     rbx, cs:WPP_GLOBAL_Control
0x1800678cd  mov     r13d, 20Ah
0x1800678d3  lea     rcx, [rbp+0AC0h+FileName]; void *
0x1800678da  mov     r8d, r13d; Size
0x1800678dd  xor     edx, edx; Val
0x1800678df  xor     edi, edi
0x1800678e1  call    memset_0
0x1800678e6  mov     r8d, r13d; Size
0x1800678e9  lea     rcx, [rbp+0AC0h+var_460]; void *
0x1800678f0  xor     edx, edx; Val
0x1800678f2  call    memset_0
0x1800678f7  lea     r12d, [r13+46h]
0x1800678fb  xor     edx, edx; Val
0x1800678fd  mov     r8d, r12d; Size
0x180067900  lea     rcx, [rbp+0AC0h+FindFileData]; void *
0x180067904  call    memset_0
0x180067909  mov     r8d, r12d; Size
0x18006790c  lea     rcx, [rbp+0AC0h+var_8C0]; void *
0x180067913  xor     edx, edx; Val
0x180067915  call    memset_0
0x18006791a  xor     eax, eax
0x18006791c  lea     rcx, [rbp+0AC0h+ProfileDir]; void *
0x180067923  xorps   xmm0, xmm0
0x180067926  mov     [rbp+0AC0h+var_B20], rax
0x18006792a  mov     r8d, r13d; Size
0x18006792d  mov     [rsp+0BC0h+var_B58], rax
0x180067932  xor     edx, edx; Val
0x180067934  mov     [rsp+0BC0h+hMem], rax
0x180067939  movups  [rsp+0BC0h+var_B50], xmm0
0x18006793e  mov     [rsp+0BC0h+var_B60], rax
0x180067943  or      r12, 0FFFFFFFFFFFFFFFFh
0x180067947  movups  [rbp+0AC0h+var_B40], xmm0
0x18006794b  movups  [rbp+0AC0h+var_B30], xmm0
0x18006794f  call    memset_0
0x180067954  xor     r13d, r13d
0x180067957  test    r14, r14
0x18006795a  jz      loc_180067CC4
0x180067960  lea     rdx, [rsp+0BC0h+hMem]
0x180067965  mov     rcx, r15
0x180067968  call    GetFileNameFromPath
0x18006796d  mov     edi, eax
0x18006796f  test    eax, eax
0x180067971  jz      short loc_1800679B4
0x180067973  mov     rbx, cs:WPP_GLOBAL_Control
0x18006797a  cmp     rbx, rsi
0x18006797d  jz      loc_180067CC4
0x180067983  test    byte ptr [rbx+1Ch], 80h
0x180067987  jz      loc_180067CC4
0x18006798d  cmp     byte ptr [rbx+19h], 2
0x180067991  jb      loc_180067CC4
0x180067997  mov     edx, 30Ch
0x18006799c  mov     rcx, [rbx+10h]
0x1800679a0  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800679a7  mov     r9d, eax
0x1800679aa  call    WPP_SF_d
0x1800679af  jmp     loc_180067CBD
0x1800679b4  lea     rdx, aSystem32; "\\system32\\"
0x1800679bb  mov     rcx, r15; Str
0x1800679be  call    cs:__imp_wcsstr
0x1800679c4  mov     r15d, 105h
0x1800679ca  lea     rdx, [rsp+0BC0h+cchSize]; lpcchSize
0x1800679cf  lea     rcx, [rbp+0AC0h+ProfileDir]; lpProfileDir
0x1800679d6  mov     [rsp+0BC0h+cchSize], r15d
0x1800679db  mov     rbx, rax
0x1800679de  call    cs:__imp_GetProfilesDirectoryW
0x1800679e4  test    eax, eax
0x1800679e6  jnz     short loc_180067A36
0x1800679e8  mov     rbx, cs:WPP_GLOBAL_Control
0x1800679ef  cmp     rbx, rsi
0x1800679f2  jz      loc_180067CC4
0x1800679f8  test    byte ptr [rbx+1Ch], 80h
0x1800679fc  jz      loc_180067CC4
0x180067a02  cmp     byte ptr [rbx+19h], 2
0x180067a06  jb      loc_180067CC4
0x180067a0c  mov     rbx, [rbx+10h]
0x180067a10  call    cs:__imp_GetLastError
0x180067a16  mov     edx, 30Dh
0x180067a1b  mov     r9, r14
0x180067a1e  mov     dword ptr [rsp+0BC0h+var_BA0], eax
0x180067a22  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180067a29  mov     rcx, rbx
0x180067a2c  call    WPP_SF_Sd
0x180067a31  jmp     loc_180067CBD
0x180067a36  lea     rcx, [rsp+0BC0h+var_B60]
0x180067a3b  call    GetAppDataFolderPathUnderUserProfile
0x180067a40  mov     edi, eax
0x180067a42  test    eax, eax
0x180067a44  jz      short loc_180067A7B
0x180067a46  mov     rbx, cs:WPP_GLOBAL_Control
0x180067a4d  cmp     rbx, rsi
0x180067a50  jz      loc_180067CC4
0x180067a56  test    byte ptr [rbx+1Ch], 80h
0x180067a5a  jz      loc_180067CC4
0x180067a60  cmp     byte ptr [rbx+19h], 2
0x180067a64  jb      loc_180067CC4
0x180067a6a  mov     rbx, [rbx+10h]
0x180067a6e  call    cs:__imp_GetLastError
0x180067a74  mov     edx, 30Eh
0x180067a79  jmp     short loc_180067A1B
0x180067a7b  lea     r9, [rbp+0AC0h+ProfileDir]
0x180067a82  mov     rdx, r15
0x180067a85  lea     r8, aS_0; "%s\\*"
0x180067a8c  lea     rcx, [rbp+0AC0h+FileName]
0x180067a93  call    StringCchPrintfWrapW
0x180067a98  mov     edi, eax
0x180067a9a  test    eax, eax
0x180067a9c  jz      short loc_180067ACC
0x180067a9e  mov     rbx, cs:WPP_GLOBAL_Control
0x180067aa5  cmp     rbx, rsi
0x180067aa8  jz      loc_180067CC4
0x180067aae  test    byte ptr [rbx+1Ch], 80h
0x180067ab2  jz      loc_180067CC4
0x180067ab8  cmp     byte ptr [rbx+19h], 2
0x180067abc  jb      loc_180067CC4
0x180067ac2  mov     edx, 30Fh
0x180067ac7  jmp     loc_18006799C
0x180067acc  lea     rdx, [rbp+0AC0h+FindFileData]; lpFindFileData
0x180067ad0  lea     rcx, [rbp+0AC0h+FileName]; lpFileName
0x180067ad7  call    cs:__imp_FindFirstFileW
0x180067add  mov     r12, rax
0x180067ae0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180067ae4  jnz     short loc_180067B1C
0x180067ae6  call    cs:__imp_GetLastError
0x180067aec  mov     edi, eax
0x180067aee  mov     rbx, cs:WPP_GLOBAL_Control
0x180067af5  cmp     rbx, rsi
0x180067af8  jz      loc_180067CC4
0x180067afe  test    byte ptr [rbx+1Ch], 80h
0x180067b02  jz      loc_180067CC4
0x180067b08  cmp     byte ptr [rbx+19h], 2
0x180067b0c  jb      loc_180067CC4
0x180067b12  mov     edx, 310h
0x180067b17  jmp     loc_18006799C
0x180067b1c  test    byte ptr [rbp+0AC0h+FindFileData.dwFileAttributes], 10h
0x180067b20  jz      loc_180067CA8
0x180067b26  cmp     [rbp+0AC0h+FindFileData.cFileName], 2Eh ; '.'
0x180067b2b  movzx   eax, [rbp+0AC0h+FindFileData.cFileName+2]
0x180067b2f  jnz     short loc_180067B52
0x180067b31  test    ax, ax
0x180067b34  jz      loc_180067CA8
0x180067b3a  cmp     [rbp+0AC0h+FindFileData.cFileName], 2Eh ; '.'
0x180067b3f  jnz     short loc_180067B52
0x180067b41  cmp     ax, 2Eh ; '.'
0x180067b45  jnz     short loc_180067B52
0x180067b47  cmp     [rbp+0AC0h+FindFileData.cFileName+4], r13w
0x180067b4c  jz      loc_180067CA8
0x180067b52  lea     rax, aHiddenpbk; "_hiddenPbk\\"
0x180067b59  test    rbx, rbx
0x180067b5c  lea     rcx, aHiddenpbkSyste; "_hiddenPBK\\System\\"
0x180067b63  mov     rdx, r15
0x180067b66  cmovz   rcx, rax
0x180067b6a  lea     r9, [rbp+0AC0h+ProfileDir]
0x180067b71  mov     rax, [rsp+0BC0h+hMem]
0x180067b76  lea     r8, aSSSSSS; "%s\\%s\\%s\\%s\\%s%s"
0x180067b7d  mov     [rsp+0BC0h+var_B80], rax
0x180067b82  lea     rax, aMicrosoftNetwo_0; "Microsoft\\Network\\Connections\\Pbk"
0x180067b89  mov     [rsp+0BC0h+var_B88], rcx
0x180067b8e  lea     rcx, [rbp+0AC0h+var_460]
0x180067b95  mov     [rsp+0BC0h+var_B90], rax
0x180067b9a  mov     rax, [rsp+0BC0h+var_B60]
0x180067b9f  mov     [rsp+0BC0h+var_B98], rax
0x180067ba4  lea     rax, [rbp+0AC0h+FindFileData.cFileName]
0x180067ba8  mov     [rsp+0BC0h+var_BA0], rax
0x180067bad  call    StringCchPrintfWrapW
0x180067bb2  test    eax, eax
0x180067bb4  jnz     loc_180067CA8
0x180067bba  lea     rcx, [rbp+0AC0h+var_460]; lpFileName
0x180067bc1  call    FFileExists
0x180067bc6  test    eax, eax
0x180067bc8  jz      loc_180067CA8
0x180067bce  lea     rax, [rsp+0BC0h+var_B58]
0x180067bd3  mov     r8d, 408h
0x180067bd9  lea     r9, [rsp+0BC0h+var_B50]
0x180067bde  mov     [rsp+0BC0h+var_BA0], rax
0x180067be3  mov     rdx, r14
0x180067be6  lea     rcx, [rbp+0AC0h+var_460]
0x180067bed  call    GetPbkAndEntryName
0x180067bf2  mov     edi, eax
0x180067bf4  test    eax, eax
0x180067bf6  jz      short loc_180067C46
0x180067bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x180067bff  cmp     rcx, rsi
0x180067c02  jz      loc_180067CA8
0x180067c08  test    byte ptr [rcx+1Ch], 80h
0x180067c0c  jz      loc_180067CA8
0x180067c12  cmp     byte ptr [rcx+19h], 2
0x180067c16  jb      loc_180067CA8
0x180067c1c  mov     rcx, [rcx+10h]
0x180067c20  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180067c27  mov     dword ptr [rsp+0BC0h+var_B98], eax
0x180067c2b  mov     edx, 311h
0x180067c30  lea     rax, [rbp+0AC0h+var_894]
0x180067c37  mov     r9, r14
0x180067c3a  mov     [rsp+0BC0h+var_BA0], rax
0x180067c3f  call    WPP_SF_SSD
0x180067c44  jmp     short loc_180067CA8
0x180067c46  mov     rdx, r14
0x180067c49  mov     [rsp+0BC0h+var_B58], r13
0x180067c4e  lea     rcx, [rsp+0BC0h+var_B50]
0x180067c53  call    WritePhonebookFile
0x180067c58  mov     edi, eax
0x180067c5a  test    eax, eax
0x180067c5c  jz      short loc_180067C9E
0x180067c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180067c65  cmp     rcx, rsi
0x180067c68  jz      short loc_180067C9E
0x180067c6a  test    byte ptr [rcx+1Ch], 80h
0x180067c6e  jz      short loc_180067C9E
0x180067c70  cmp     byte ptr [rcx+19h], 2
0x180067c74  jb      short loc_180067C9E
0x180067c76  mov     rcx, [rcx+10h]
0x180067c7a  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180067c81  mov     dword ptr [rsp+0BC0h+var_B98], eax
0x180067c85  mov     edx, 312h
0x180067c8a  lea     rax, [rbp+0AC0h+var_894]
0x180067c91  mov     r9, r14
0x180067c94  mov     [rsp+0BC0h+var_BA0], rax
0x180067c99  call    WPP_SF_SSD
0x180067c9e  lea     rcx, [rsp+0BC0h+var_B50]
0x180067ca3  call    ClosePhonebookFile
0x180067ca8  lea     rdx, [rbp+0AC0h+FindFileData]; lpFindFileData
0x180067cac  mov     rcx, r12; hFindFile
0x180067caf  call    cs:__imp_FindNextFileW
0x180067cb5  test    eax, eax
0x180067cb7  jnz     loc_180067B1C
0x180067cbd  mov     rbx, cs:WPP_GLOBAL_Control
0x180067cc4  mov     rcx, [rsp+0BC0h+hMem]; hMem
0x180067cc9  test    rcx, rcx
0x180067ccc  jz      short loc_180067CDB
0x180067cce  call    cs:__imp_GlobalFree
0x180067cd4  mov     rbx, cs:WPP_GLOBAL_Control
0x180067cdb  mov     rcx, [rsp+0BC0h+var_B60]; hMem
0x180067ce0  test    rcx, rcx
0x180067ce3  jz      short loc_180067CF2
0x180067ce5  call    cs:__imp_GlobalFree
0x180067ceb  mov     rbx, cs:WPP_GLOBAL_Control
0x180067cf2  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x180067cf6  jz      short loc_180067D08
0x180067cf8  mov     rcx, r12; hFindFile
0x180067cfb  call    cs:__imp_FindClose
0x180067d01  mov     rbx, cs:WPP_GLOBAL_Control
0x180067d08  cmp     rbx, rsi
0x180067d0b  jz      short loc_180067D31
0x180067d0d  test    byte ptr [rbx+1Ch], 80h
0x180067d11  jz      short loc_180067D31
0x180067d13  cmp     byte ptr [rbx+19h], 6
0x180067d17  jb      short loc_180067D31
0x180067d19  mov     rcx, [rbx+10h]
0x180067d1d  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180067d24  mov     edx, 313h
0x180067d29  mov     r9d, edi
0x180067d2c  call    WPP_SF_d
0x180067d31  mov     eax, edi
0x180067d33  mov     rcx, [rbp+0AC0h+var_40]
  ... truncated ...
```
