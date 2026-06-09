# DeleteAllHiddenProfile

- ea: `0x1800caa9c`
- end: `0x1800cb0f2`
- name: `DeleteAllHiddenProfile`
- size: `1622`
- prototype: `__int64 __fastcall(wchar_t *Str, const wchar_t *)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180005af0`

## callees

- `0x180005af0`
- `0x1800079c0`
- `0x18000b0f4`
- `0x180020c78`
- `0x1800279c0`
- `0x18003b284`
- `0x18004e580`
- `0x18004e984`
- `0x180063d80`
- `0x18007e650`
- `0x18007e6c8`
- `0x18007ed3c`
- `0x1800c1ef4`
- `0x1800caa9c`
- `0x1800cb7dc`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cacb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cacfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cad80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cae00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cacb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cacfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cad80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cae00`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800cb08f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800cb08f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800caf7f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800cb05d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800caf7f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800cb05d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800cadf1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800cadf1`
- `rtutils!TracePrintfExA` at `0x1800cabfa`
- `rtutils!TracePrintfExA` at `0x1800cac31`
- `rtutils!TracePrintfExA` at `0x1800cacd0`
- `rtutils!TracePrintfExA` at `0x1800cad52`
- `rtutils!TracePrintfExA` at `0x1800cafb5`
- `rtutils!TracePrintfExA` at `0x1800cb006`
- `rtutils!TracePrintfExA` at `0x1800cabfa`
- `rtutils!TracePrintfExA` at `0x1800cac31`
- `rtutils!TracePrintfExA` at `0x1800cacd0`
- `rtutils!TracePrintfExA` at `0x1800cad52`
- `rtutils!TracePrintfExA` at `0x1800cafb5`
- `rtutils!TracePrintfExA` at `0x1800cb006`
- `USERENV!GetProfilesDirectoryW` at `0x1800cac9e`
- `USERENV!GetProfilesDirectoryW` at `0x1800cac9e`

## string_xrefs

- `0x1800cac78`: `\system32\`
- `0x1800cac25`: ` DeleteAllHiddenProfile: GetFileNameFromPath  for Entry %S failed. Error = %d`
- `0x1800cabf0`: ` DeleteAllHiddenProfile: ++`
- `0x1800cad46`: ` DeleteAllHiddenProfile: GetAppDataPath  for Entry %S failed. Error = %d`
- `0x1800cacbd`: ` DeleteAllHiddenProfile: GetProfilesDirectory  for Entry %S failed. Error = %d`
- `0x1800cafeb`: ` DeleteAllHiddenProfile: WritePhonebookFile  for Entry %S in the file %S failed. Error %d`
- `0x1800cafa9`: ` DeleteAllHiddenProfile: GetPbkAndEntryName for Entry %S in the file %S failed. Error %d`

## pseudocode

```c
__int64 __fastcall DeleteAllHiddenProfile(wchar_t *Str, const wchar_t *a2)
{
  DWORD v4; // edi
  __int64 FirstFileW; // r15
  DWORD FileNameFromPath; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  wchar_t *v10; // r12
  DWORD LastError; // eax
  __int64 v12; // rbx
  char v13; // al
  int v14; // edx
  DWORD AppDataFolderPathUnderUserProfile; // eax
  DWORD v16; // eax
  int v17; // edx
  int v18; // edx
  const wchar_t *v19; // rcx
  DWORD PbkAndEntryName; // eax
  BOOL NextFileW; // ebx
  DWORD v22; // eax
  DWORD cchSize; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v28[3]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+A0h] [rbp-60h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+B0h] [rbp-50h] BYREF
  char v31[44]; // [rsp+300h] [rbp+200h] BYREF
  wchar_t v32[274]; // [rsp+32Ch] [rbp+22Ch] BYREF
  WCHAR ProfileDir[264]; // [rsp+550h] [rbp+450h] BYREF
  WCHAR v34[264]; // [rsp+760h] [rbp+660h] BYREF
  WCHAR FileName[264]; // [rsp+970h] [rbp+870h] BYREF

  if ( Str && a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        778,
        (unsigned int)&WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
        (_DWORD)Str,
        (__int64)a2);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && *((char *)WPP_GLOBAL_Control + 28) < 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 779, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
  }
  v4 = 0;
  memset_0(FileName, 0, 0x20Au);
  memset_0(v34, 0, 0x20Au);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(v31, 0, 0x250u);
  v29 = 0;
  v27 = 0;
  v25 = 0;
  memset(v28, 0, sizeof(v28));
  v26 = 0;
  FirstFileW = -1;
  memset_0(ProfileDir, 0, 0x20Au);
  if ( !a2 )
    goto LABEL_77;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, " DeleteAllHiddenProfile: ++");
  FileNameFromPath = GetFileNameFromPath(Str, &v25);
  v4 = FileNameFromPath;
  if ( !FileNameFromPath )
  {
    cchSize = 261;
    v10 = wcsstr_0(Str, L"\\system32\\");
    if ( !GetProfilesDirectoryW(ProfileDir, &cchSize) )
    {
      if ( g_dwTraceId != -1 )
      {
        LastError = GetLastError();
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          " DeleteAllHiddenProfile: GetProfilesDirectory  for Entry %S failed. Error = %d",
          a2,
          LastError);
      }
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_77;
      }
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v13 = GetLastError();
      v14 = 781;
      goto LABEL_29;
    }
    AppDataFolderPathUnderUserProfile = GetAppDataFolderPathUnderUserProfile(&v26);
    v4 = AppDataFolderPathUnderUserProfile;
    if ( AppDataFolderPathUnderUserProfile )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          " DeleteAllHiddenProfile: GetAppDataPath  for Entry %S failed. Error = %d",
          a2,
          AppDataFolderPathUnderUserProfile);
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_77;
      }
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v13 = GetLastError();
      v14 = 782;
LABEL_29:
      WPP_SF_Sd(v12, v14, (unsigned int)&WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, (_DWORD)a2, v13);
      goto LABEL_77;
    }
    v16 = StringCchPrintfWrapW(FileName, 261, L"%s\\*", ProfileDir);
    v4 = v16;
    if ( v16 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_77;
      }
      v8 = 783;
      goto LABEL_42;
    }
    FirstFileW = (__int64)FindFirstFileW(FileName, &FindFileData);
    if ( FirstFileW == -1 )
    {
      v16 = GetLastError();
      v4 = v16;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || *((char *)WPP_GLOBAL_Control + 28) >= 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_77;
      }
      v8 = 784;
LABEL_42:
      v9 = v16;
      goto LABEL_21;
    }
    while ( 1 )
    {
      if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
      {
        v17 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
          v17 = FindFileData.cFileName[1];
        if ( v17 )
        {
          v18 = FindFileData.cFileName[0] - 46;
          if ( FindFileData.cFileName[0] == 46 )
          {
            v18 = FindFileData.cFileName[1] - 46;
            if ( FindFileData.cFileName[1] == 46 )
              v18 = FindFileData.cFileName[2];
          }
          if ( v18 )
          {
            v19 = L"_hiddenPBK\\System\\";
            if ( !v10 )
              v19 = L"_hiddenPbk\\";
            if ( !(unsigned int)StringCchPrintfWrapW(
                                  v34,
                                  261,
                                  L"%s\\%s\\%s\\%s\\%s%s",
                                  ProfileDir,
                                  FindFileData.cFileName,
                                  v26,
                                  L"Microsoft\\Network\\Connections\\Pbk",
                                  v19,
                                  v25)
              && (unsigned int)FFileExists(v34) )
            {
              PbkAndEntryName = GetPbkAndEntryName(v34, (__int64)&v27);
              v4 = PbkAndEntryName;
              if ( PbkAndEntryName )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && *((char *)WPP_GLOBAL_Control + 28) < 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_SSD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    785,
                    (unsigned int)&WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
                    (_DWORD)a2,
                    (__int64)v32,
                    PbkAndEntryName);
                }
                NextFileW = FindNextFileW((HANDLE)FirstFileW, &FindFileData);
                if ( g_dwTraceId != -1 )
                  TracePrintfExA(
                    g_dwTraceId,
                    0xCu,
                    " DeleteAllHiddenProfile: GetPbkAndEntryName for Entry %S in the file %S failed. Error %d",
                    a2,
                    v32,
                    v4);
                goto LABEL_76;
              }
              v27 = 0;
              v22 = WritePhonebookFile(v28, a2);
              v4 = v22;
              if ( v22 )
              {
                if ( g_dwTraceId != -1 )
                  TracePrintfExA(
                    g_dwTraceId,
                    0xCu,
                    " DeleteAllHiddenProfile: WritePhonebookFile  for Entry %S in the file %S failed. Error %d",
                    a2,
                    v32,
                    v22);
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && *((char *)WPP_GLOBAL_Control + 28) < 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_SSD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    786,
                    (unsigned int)&WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids,
                    (_DWORD)a2,
                    (__int64)v32,
                    v4);
                }
              }
              ClosePhonebookFile((__int64)v28);
            }
          }
        }
      }
      NextFileW = FindNextFileW((HANDLE)FirstFileW, &FindFileData);
LABEL_76:
      if ( !NextFileW )
        goto LABEL_77;
    }
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(
      g_dwTraceId,
      0xCu,
      " DeleteAllHiddenProfile: GetFileNameFromPath  for Entry %S failed. Error = %d",
      a2,
      FileNameFromPath);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = 780;
    v9 = v4;
LABEL_21:
    WPP_SF_d(v7[2], v8, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v9);
  }
LABEL_77:
  Free0(v25);
  Free0(v26);
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 787, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x1800caa9c  mov     [rsp-8+arg_10], rbx
0x1800caaa1  mov     [rsp-8+arg_18], rsi
0x1800caaa6  push    rbp
0x1800caaa7  push    rdi
0x1800caaa8  push    r12
0x1800caaaa  push    r14
0x1800caaac  push    r15
0x1800caaae  lea     rbp, [rsp-0A90h]
0x1800caab6  sub     rsp, 0B90h
0x1800caabd  mov     rax, cs:__security_cookie
0x1800caac4  xor     rax, rsp
0x1800caac7  mov     [rbp+0AB0h+var_30], rax
0x1800caace  mov     rsi, rdx
0x1800caad1  mov     rbx, rcx
0x1800caad4  test    rcx, rcx
0x1800caad7  jz      short loc_1800CAB1C
0x1800caad9  test    rdx, rdx
0x1800caadc  jz      short loc_1800CAB1C
0x1800caade  mov     rcx, cs:WPP_GLOBAL_Control
0x1800caae5  lea     r14, WPP_GLOBAL_Control
0x1800caaec  cmp     rcx, r14
0x1800caaef  jz      short loc_1800CAB50
0x1800caaf1  test    byte ptr [rcx+1Ch], 80h
0x1800caaf5  jz      short loc_1800CAB50
0x1800caaf7  cmp     byte ptr [rcx+19h], 6
0x1800caafb  jb      short loc_1800CAB50
0x1800caafd  mov     rcx, [rcx+10h]
0x1800cab01  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800cab08  mov     edx, 30Ah
0x1800cab0d  mov     [rsp+0BB0h+var_B90], rsi
0x1800cab12  mov     r9, rbx
0x1800cab15  call    WPP_SF_SS
0x1800cab1a  jmp     short loc_1800CAB50
0x1800cab1c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cab23  lea     r14, WPP_GLOBAL_Control
0x1800cab2a  cmp     rcx, r14
0x1800cab2d  jz      short loc_1800CAB50
0x1800cab2f  test    byte ptr [rcx+1Ch], 80h
0x1800cab33  jz      short loc_1800CAB50
0x1800cab35  cmp     byte ptr [rcx+19h], 6
0x1800cab39  jb      short loc_1800CAB50
0x1800cab3b  mov     rcx, [rcx+10h]
0x1800cab3f  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800cab46  mov     edx, 30Bh
0x1800cab4b  call    WPP_SF_
0x1800cab50  mov     r12d, 20Ah
0x1800cab56  lea     rcx, [rbp+0AB0h+FileName]; void *
0x1800cab5d  mov     r8d, r12d; Size
0x1800cab60  xor     edx, edx; Val
0x1800cab62  xor     edi, edi
0x1800cab64  call    memset_0
0x1800cab69  mov     r8d, r12d; Size
0x1800cab6c  lea     rcx, [rbp+0AB0h+var_450]; void *
0x1800cab73  xor     edx, edx; Val
0x1800cab75  call    memset_0
0x1800cab7a  lea     r15d, [r12+46h]
0x1800cab7f  xor     edx, edx; Val
0x1800cab81  mov     r8d, r15d; Size
0x1800cab84  lea     rcx, [rbp+0AB0h+FindFileData]; void *
0x1800cab88  call    memset_0
0x1800cab8d  mov     r8d, r15d; Size
0x1800cab90  lea     rcx, [rbp+0AB0h+var_8B0]; void *
0x1800cab97  xor     edx, edx; Val
0x1800cab99  call    memset_0
0x1800cab9e  xor     eax, eax
0x1800caba0  lea     rcx, [rbp+0AB0h+ProfileDir]; void *
0x1800caba7  xorps   xmm0, xmm0
0x1800cabaa  mov     [rbp+0AB0h+var_B10], rax
0x1800cabae  mov     r8d, r12d; Size
0x1800cabb1  mov     [rsp+0BB0h+var_B48], rax
0x1800cabb6  xor     edx, edx; Val
0x1800cabb8  mov     [rsp+0BB0h+var_B58], rax
0x1800cabbd  movups  [rsp+0BB0h+var_B40], xmm0
0x1800cabc2  mov     [rsp+0BB0h+var_B50], rax
0x1800cabc7  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800cabcb  movups  [rbp+0AB0h+var_B30], xmm0
0x1800cabcf  movups  [rbp+0AB0h+var_B20], xmm0
0x1800cabd3  call    memset_0
0x1800cabd8  test    rsi, rsi
0x1800cabdb  jz      loc_1800CB072
0x1800cabe1  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800cabe7  or      r12d, 0FFFFFFFFh
0x1800cabeb  cmp     ecx, r12d
0x1800cabee  jz      short loc_1800CAC00
0x1800cabf0  lea     r8, aDeleteallhidde; " DeleteAllHiddenProfile: ++"
0x1800cabf7  lea     edx, [rdi+0Ch]; dwFlags
0x1800cabfa  call    cs:__imp_TracePrintfExA
0x1800cac00  lea     rdx, [rsp+0BB0h+var_B58]
0x1800cac05  mov     rcx, rbx
0x1800cac08  call    GetFileNameFromPath
0x1800cac0d  mov     edi, eax
0x1800cac0f  test    eax, eax
0x1800cac11  jz      short loc_1800CAC78
0x1800cac13  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800cac19  cmp     ecx, r12d
0x1800cac1c  jz      short loc_1800CAC37
0x1800cac1e  mov     r9, rsi
0x1800cac21  mov     dword ptr [rsp+0BB0h+var_B90], eax
0x1800cac25  lea     r8, aDeleteallhidde_1; " DeleteAllHiddenProfile: GetFileNameFro"...
0x1800cac2c  mov     edx, 0Ch; dwFlags
0x1800cac31  call    cs:__imp_TracePrintfExA
0x1800cac37  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cac3e  cmp     rcx, r14
0x1800cac41  jz      loc_1800CB072
0x1800cac47  test    byte ptr [rcx+1Ch], 80h
0x1800cac4b  jz      loc_1800CB072
0x1800cac51  cmp     byte ptr [rcx+19h], 2
0x1800cac55  jb      loc_1800CB072
0x1800cac5b  mov     edx, 30Ch
0x1800cac60  mov     r9d, edi
0x1800cac63  mov     rcx, [rcx+10h]
0x1800cac67  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800cac6e  call    WPP_SF_d
0x1800cac73  jmp     loc_1800CB072
0x1800cac78  lea     rdx, aSystem32; "\\system32\\"
0x1800cac7f  mov     rcx, rbx; Str
0x1800cac82  call    wcsstr_0
0x1800cac87  lea     rdx, [rsp+0BB0h+cchSize]; lpcchSize
0x1800cac8c  mov     [rsp+0BB0h+cchSize], 105h
0x1800cac94  lea     rcx, [rbp+0AB0h+ProfileDir]; lpProfileDir
0x1800cac9b  mov     r12, rax
0x1800cac9e  call    cs:__imp_GetProfilesDirectoryW
0x1800caca4  test    eax, eax
0x1800caca6  jnz     short loc_1800CAD24
0x1800caca8  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x1800cacaf  jz      short loc_1800CACD6
0x1800cacb1  call    cs:__imp_GetLastError
0x1800cacb7  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800cacbd  lea     r8, aDeleteallhidde_4; " DeleteAllHiddenProfile: GetProfilesDir"...
0x1800cacc4  mov     r9, rsi
0x1800cacc7  mov     dword ptr [rsp+0BB0h+var_B90], eax
0x1800caccb  mov     edx, 0Ch; dwFlags
0x1800cacd0  call    cs:__imp_TracePrintfExA
0x1800cacd6  mov     rbx, cs:WPP_GLOBAL_Control
0x1800cacdd  cmp     rbx, r14
0x1800cace0  jz      loc_1800CB072
0x1800cace6  test    byte ptr [rbx+1Ch], 80h
0x1800cacea  jz      loc_1800CB072
0x1800cacf0  cmp     byte ptr [rbx+19h], 2
0x1800cacf4  jb      loc_1800CB072
0x1800cacfa  mov     rbx, [rbx+10h]
0x1800cacfe  call    cs:__imp_GetLastError
0x1800cad04  mov     edx, 30Dh
0x1800cad09  mov     r9, rsi
0x1800cad0c  mov     dword ptr [rsp+0BB0h+var_B90], eax
0x1800cad10  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800cad17  mov     rcx, rbx
0x1800cad1a  call    WPP_SF_Sd
0x1800cad1f  jmp     loc_1800CB072
0x1800cad24  lea     rcx, [rsp+0BB0h+var_B50]
0x1800cad29  call    GetAppDataFolderPathUnderUserProfile
0x1800cad2e  mov     edi, eax
0x1800cad30  test    eax, eax
0x1800cad32  jz      short loc_1800CAD90
0x1800cad34  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800cad3a  cmp     ecx, 0FFFFFFFFh
0x1800cad3d  jz      short loc_1800CAD58
0x1800cad3f  mov     r9, rsi
0x1800cad42  mov     dword ptr [rsp+0BB0h+var_B90], eax
0x1800cad46  lea     r8, aDeleteallhidde_2; " DeleteAllHiddenProfile: GetAppDataPath"...
0x1800cad4d  mov     edx, 0Ch; dwFlags
0x1800cad52  call    cs:__imp_TracePrintfExA
0x1800cad58  mov     rbx, cs:WPP_GLOBAL_Control
0x1800cad5f  cmp     rbx, r14
0x1800cad62  jz      loc_1800CB072
0x1800cad68  test    byte ptr [rbx+1Ch], 80h
0x1800cad6c  jz      loc_1800CB072
0x1800cad72  cmp     byte ptr [rbx+19h], 2
0x1800cad76  jb      loc_1800CB072
0x1800cad7c  mov     rbx, [rbx+10h]
0x1800cad80  call    cs:__imp_GetLastError
0x1800cad86  mov     edx, 30Eh
0x1800cad8b  jmp     loc_1800CAD09
0x1800cad90  lea     r9, [rbp+0AB0h+ProfileDir]
0x1800cad97  mov     edx, 105h
0x1800cad9c  lea     r8, aS_1; "%s\\*"
0x1800cada3  lea     rcx, [rbp+0AB0h+FileName]
0x1800cadaa  call    StringCchPrintfWrapW
0x1800cadaf  mov     edi, eax
0x1800cadb1  test    eax, eax
0x1800cadb3  jz      short loc_1800CADE6
0x1800cadb5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cadbc  cmp     rcx, r14
0x1800cadbf  jz      loc_1800CB072
0x1800cadc5  test    byte ptr [rcx+1Ch], 80h
0x1800cadc9  jz      loc_1800CB072
0x1800cadcf  cmp     byte ptr [rcx+19h], 2
0x1800cadd3  jb      loc_1800CB072
0x1800cadd9  mov     edx, 30Fh
0x1800cadde  mov     r9d, eax
0x1800cade1  jmp     loc_1800CAC63
0x1800cade6  lea     rdx, [rbp+0AB0h+FindFileData]; lpFindFileData
0x1800cadea  lea     rcx, [rbp+0AB0h+FileName]; lpFileName
0x1800cadf1  call    cs:__imp_FindFirstFileW
0x1800cadf7  mov     r15, rax
0x1800cadfa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800cadfe  jnz     short loc_1800CAE33
0x1800cae00  call    cs:__imp_GetLastError
0x1800cae06  mov     edi, eax
0x1800cae08  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cae0f  cmp     rcx, r14
0x1800cae12  jz      loc_1800CB072
0x1800cae18  test    byte ptr [rcx+1Ch], 80h
0x1800cae1c  jz      loc_1800CB072
0x1800cae22  cmp     byte ptr [rcx+19h], 2
0x1800cae26  jb      loc_1800CB072
0x1800cae2c  mov     edx, 310h
0x1800cae31  jmp     short loc_1800CADDE
0x1800cae33  mov     ecx, 2Eh ; '.'
0x1800cae38  test    byte ptr [rbp+0AB0h+FindFileData.dwFileAttributes], 10h
0x1800cae3c  jz      loc_1800CB056
0x1800cae42  movzx   edx, [rbp+0AB0h+FindFileData.cFileName]
0x1800cae46  movzx   eax, cx
0x1800cae49  sub     edx, eax
0x1800cae4b  jnz     short loc_1800CAE5B
0x1800cae4d  movzx   edx, [rbp+0AB0h+FindFileData.cFileName+2]
0x1800cae51  xor     eax, eax
0x1800cae53  movzx   ecx, ax
0x1800cae56  sub     edx, ecx
0x1800cae58  lea     ecx, [rax+2Eh]
0x1800cae5b  test    edx, edx
0x1800cae5d  jz      loc_1800CB056
0x1800cae63  movzx   edx, [rbp+0AB0h+FindFileData.cFileName]
0x1800cae67  movzx   eax, cx
0x1800cae6a  sub     edx, eax
0x1800cae6c  jnz     short loc_1800CAE84
0x1800cae6e  movzx   edx, [rbp+0AB0h+FindFileData.cFileName+2]
0x1800cae72  movzx   eax, cx
0x1800cae75  sub     edx, eax
0x1800cae77  jnz     short loc_1800CAE84
0x1800cae79  movzx   edx, [rbp+0AB0h+FindFileData.cFileName+4]
0x1800cae7d  xor     eax, eax
0x1800cae7f  movzx   ecx, ax
0x1800cae82  sub     edx, ecx
0x1800cae84  test    edx, edx
0x1800cae86  jz      loc_1800CB056
0x1800cae8c  lea     rax, aHiddenpbk; "_hiddenPbk\\"
0x1800cae93  test    r12, r12
0x1800cae96  lea     rcx, aHiddenpbkSyste; "_hiddenPBK\\System\\"
0x1800cae9d  mov     edx, 105h
0x1800caea2  cmovz   rcx, rax
0x1800caea6  lea     r9, [rbp+0AB0h+ProfileDir]
0x1800caead  mov     rax, [rsp+0BB0h+var_B58]
0x1800caeb2  lea     r8, aSSSSSS; "%s\\%s\\%s\\%s\\%s%s"
0x1800caeb9  mov     [rsp+0BB0h+var_B70], rax
0x1800caebe  lea     rax, aMicrosoftNetwo_0; "Microsoft\\Network\\Connections\\Pbk"
0x1800caec5  mov     [rsp+0BB0h+var_B78], rcx
0x1800caeca  lea     rcx, [rbp+0AB0h+var_450]
0x1800caed1  mov     [rsp+0BB0h+var_B80], rax
0x1800caed6  mov     rax, [rsp+0BB0h+var_B50]
0x1800caedb  mov     [rsp+0BB0h+var_B88], rax
0x1800caee0  lea     rax, [rbp+0AB0h+FindFileData.cFileName]
0x1800caee4  mov     [rsp+0BB0h+var_B90], rax
0x1800caee9  call    StringCchPrintfWrapW
0x1800caeee  test    eax, eax
0x1800caef0  jnz     loc_1800CB056
0x1800caef6  lea     rcx, [rbp+0AB0h+var_450]; lpFileName
0x1800caefd  call    FFileExists
0x1800caf02  test    eax, eax
0x1800caf04  jz      loc_1800CB056
0x1800caf0a  lea     rax, [rsp+0BB0h+var_B48]
0x1800caf0f  mov     r8d, 408h
0x1800caf15  lea     r9, [rsp+0BB0h+var_B40]
0x1800caf1a  mov     [rsp+0BB0h+var_B90], rax
0x1800caf1f  mov     rdx, rsi
0x1800caf22  lea     rcx, [rbp+0AB0h+var_450]
0x1800caf29  call    GetPbkAndEntryName
0x1800caf2e  mov     edi, eax
0x1800caf30  test    eax, eax
0x1800caf32  jz      loc_1800CAFC0
0x1800caf38  mov     rcx, cs:WPP_GLOBAL_Control
0x1800caf3f  cmp     rcx, r14
0x1800caf42  jz      short loc_1800CAF78
0x1800caf44  test    byte ptr [rcx+1Ch], 80h
0x1800caf48  jz      short loc_1800CAF78
0x1800caf4a  cmp     byte ptr [rcx+19h], 2
0x1800caf4e  jb      short loc_1800CAF78
0x1800caf50  mov     rcx, [rcx+10h]
0x1800caf54  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x1800caf5b  mov     dword ptr [rsp+0BB0h+var_B88], eax
0x1800caf5f  mov     edx, 311h
0x1800caf64  lea     rax, [rbp+0AB0h+var_884]
0x1800caf6b  mov     r9, rsi
0x1800caf6e  mov     [rsp+0BB0h+var_B90], rax
0x1800caf73  call    WPP_SF_SSD
0x1800caf78  lea     rdx, [rbp+0AB0h+FindFileData]; lpFindFileData
0x1800caf7c  mov     rcx, r15; hFindFile
0x1800caf7f  call    cs:__imp_FindNextFileW
0x1800caf85  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800caf8b  mov     ebx, eax
0x1800caf8d  cmp     ecx, 0FFFFFFFFh
0x1800caf90  jz      loc_1800CB065
0x1800caf96  lea     rax, [rbp+0AB0h+var_884]
0x1800caf9d  mov     dword ptr [rsp+0BB0h+var_B88], edi
0x1800cafa1  mov     r9, rsi
0x1800cafa4  mov     [rsp+0BB0h+var_B90], rax
0x1800cafa9  lea     r8, aDeleteallhidde_3; " DeleteAllHiddenProfile: GetPbkAndEntry"...
0x1800cafb0  mov     edx, 0Ch; dwFlags
0x1800cafb5  call    cs:__imp_TracePrintfExA
0x1800cafbb  jmp     loc_1800CB065
  ... truncated ...
```
