# DeleteAllHiddenProfile

- ea: `0x18006b0b4`
- end: `0x18006b63a`
- name: `DeleteAllHiddenProfile`
- size: `1414`
- prototype: `__int64 __fastcall(wchar_t *Str)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18007f488`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000ec50`
- `0x18005eed8`
- `0x180060554`
- `0x180068a80`
- `0x18006a4bc`
- `0x18006b0b4`
- `0x18006cc28`
- `0x18006d1f0`
- `0x18007f248`
- `0x18007f488`
- `0x1800803c0`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `msvcrt!wcsstr` at `0x18006b25e`
- `msvcrt!wcsstr` at `0x18006b25e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b2bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b3a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b2bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b3a4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006b598`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006b5b5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006b598`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006b5b5`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18006b573`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18006b573`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18006b5d1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18006b5d1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18006b38f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18006b38f`
- `USERENV!GetProfilesDirectoryW` at `0x18006b284`
- `USERENV!GetProfilesDirectoryW` at `0x18006b284`

## string_xrefs

- `0x18006b254`: `\system32\`

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
  __int64 v21; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v22[3]; // [rsp+70h] [rbp-90h] BYREF
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
            PbkAndEntryName = GetPbkAndEntryName(v28, (__int64)&v21);
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
0x18006b0b4  mov     [rsp-8+arg_10], rbx
0x18006b0b9  push    rbp
0x18006b0ba  push    rsi
0x18006b0bb  push    rdi
0x18006b0bc  push    r12
0x18006b0be  push    r13
0x18006b0c0  push    r14
0x18006b0c2  push    r15
0x18006b0c4  lea     rbp, [rsp-0A90h]
0x18006b0cc  sub     rsp, 0B90h
0x18006b0d3  mov     rax, cs:__security_cookie
0x18006b0da  xor     rax, rsp
0x18006b0dd  mov     [rbp+0AC0h+var_40], rax
0x18006b0e4  mov     r14, rdx
0x18006b0e7  mov     r15, rcx
0x18006b0ea  test    rcx, rcx
0x18006b0ed  jz      short loc_18006B132
0x18006b0ef  test    rdx, rdx
0x18006b0f2  jz      short loc_18006B132
0x18006b0f4  mov     rbx, cs:WPP_GLOBAL_Control
0x18006b0fb  lea     rsi, WPP_GLOBAL_Control
0x18006b102  cmp     rbx, rsi
0x18006b105  jz      short loc_18006B16D
0x18006b107  test    byte ptr [rbx+1Ch], 80h
0x18006b10b  jz      short loc_18006B16D
0x18006b10d  cmp     byte ptr [rbx+19h], 6
0x18006b111  jb      short loc_18006B16D
0x18006b113  mov     r9, rcx
0x18006b116  mov     [rsp+0BC0h+var_BA0], r14
0x18006b11b  mov     rcx, [rbx+10h]
0x18006b11f  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006b126  mov     edx, 30Ah
0x18006b12b  call    WPP_SF_SS
0x18006b130  jmp     short loc_18006B166
0x18006b132  mov     rbx, cs:WPP_GLOBAL_Control
0x18006b139  lea     rsi, WPP_GLOBAL_Control
0x18006b140  cmp     rbx, rsi
0x18006b143  jz      short loc_18006B16D
0x18006b145  test    byte ptr [rbx+1Ch], 80h
0x18006b149  jz      short loc_18006B16D
0x18006b14b  cmp     byte ptr [rbx+19h], 6
0x18006b14f  jb      short loc_18006B16D
0x18006b151  mov     rcx, [rbx+10h]
0x18006b155  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006b15c  mov     edx, 30Bh
0x18006b161  call    WPP_SF_
0x18006b166  mov     rbx, cs:WPP_GLOBAL_Control
0x18006b16d  mov     r13d, 20Ah
0x18006b173  lea     rcx, [rbp+0AC0h+FileName]; void *
0x18006b17a  mov     r8d, r13d; Size
0x18006b17d  xor     edx, edx; Val
0x18006b17f  xor     edi, edi
0x18006b181  call    memset_0
0x18006b186  mov     r8d, r13d; Size
0x18006b189  lea     rcx, [rbp+0AC0h+var_460]; void *
0x18006b190  xor     edx, edx; Val
0x18006b192  call    memset_0
0x18006b197  lea     r12d, [r13+46h]
0x18006b19b  xor     edx, edx; Val
0x18006b19d  mov     r8d, r12d; Size
0x18006b1a0  lea     rcx, [rbp+0AC0h+FindFileData]; void *
0x18006b1a4  call    memset_0
0x18006b1a9  mov     r8d, r12d; Size
0x18006b1ac  lea     rcx, [rbp+0AC0h+var_8C0]; void *
0x18006b1b3  xor     edx, edx; Val
0x18006b1b5  call    memset_0
0x18006b1ba  xor     eax, eax
0x18006b1bc  lea     rcx, [rbp+0AC0h+ProfileDir]; void *
0x18006b1c3  xorps   xmm0, xmm0
0x18006b1c6  mov     [rbp+0AC0h+var_B20], rax
0x18006b1ca  mov     r8d, r13d; Size
0x18006b1cd  mov     [rsp+0BC0h+var_B58], rax
0x18006b1d2  xor     edx, edx; Val
0x18006b1d4  mov     [rsp+0BC0h+hMem], rax
0x18006b1d9  movups  [rsp+0BC0h+var_B50], xmm0
0x18006b1de  mov     [rsp+0BC0h+var_B60], rax
0x18006b1e3  or      r12, 0FFFFFFFFFFFFFFFFh
0x18006b1e7  movups  [rbp+0AC0h+var_B40], xmm0
0x18006b1eb  movups  [rbp+0AC0h+var_B30], xmm0
0x18006b1ef  call    memset_0
0x18006b1f4  xor     r13d, r13d
0x18006b1f7  test    r14, r14
0x18006b1fa  jz      loc_18006B58E
0x18006b200  lea     rdx, [rsp+0BC0h+hMem]
0x18006b205  mov     rcx, r15
0x18006b208  call    GetFileNameFromPath
0x18006b20d  mov     edi, eax
0x18006b20f  test    eax, eax
0x18006b211  jz      short loc_18006B254
0x18006b213  mov     rbx, cs:WPP_GLOBAL_Control
0x18006b21a  cmp     rbx, rsi
0x18006b21d  jz      loc_18006B58E
0x18006b223  test    byte ptr [rbx+1Ch], 80h
0x18006b227  jz      loc_18006B58E
0x18006b22d  cmp     byte ptr [rbx+19h], 2
0x18006b231  jb      loc_18006B58E
0x18006b237  mov     edx, 30Ch
0x18006b23c  mov     rcx, [rbx+10h]
0x18006b240  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006b247  mov     r9d, eax
0x18006b24a  call    WPP_SF_d
0x18006b24f  jmp     loc_18006B587
0x18006b254  lea     rdx, aSystem32; "\\system32\\"
0x18006b25b  mov     rcx, r15; Str
0x18006b25e  call    cs:__imp_wcsstr
0x18006b265  nop     dword ptr [rax+rax+00h]
0x18006b26a  mov     r15d, 105h
0x18006b270  lea     rdx, [rsp+0BC0h+cchSize]; lpcchSize
0x18006b275  lea     rcx, [rbp+0AC0h+ProfileDir]; lpProfileDir
0x18006b27c  mov     [rsp+0BC0h+cchSize], r15d
0x18006b281  mov     rbx, rax
0x18006b284  call    cs:__imp_GetProfilesDirectoryW
0x18006b28b  nop     dword ptr [rax+rax+00h]
0x18006b290  test    eax, eax
0x18006b292  jnz     short loc_18006B2E8
0x18006b294  mov     rbx, cs:WPP_GLOBAL_Control
0x18006b29b  cmp     rbx, rsi
0x18006b29e  jz      loc_18006B58E
0x18006b2a4  test    byte ptr [rbx+1Ch], 80h
0x18006b2a8  jz      loc_18006B58E
0x18006b2ae  cmp     byte ptr [rbx+19h], 2
0x18006b2b2  jb      loc_18006B58E
0x18006b2b8  mov     rbx, [rbx+10h]
0x18006b2bc  call    cs:__imp_GetLastError
0x18006b2c3  nop     dword ptr [rax+rax+00h]
0x18006b2c8  mov     edx, 30Dh
0x18006b2cd  mov     r9, r14
0x18006b2d0  mov     dword ptr [rsp+0BC0h+var_BA0], eax
0x18006b2d4  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006b2db  mov     rcx, rbx
0x18006b2de  call    WPP_SF_Sd
0x18006b2e3  jmp     loc_18006B587
0x18006b2e8  lea     rcx, [rsp+0BC0h+var_B60]
0x18006b2ed  call    GetAppDataFolderPathUnderUserProfile
0x18006b2f2  mov     edi, eax
0x18006b2f4  test    eax, eax
0x18006b2f6  jz      short loc_18006B333
0x18006b2f8  mov     rbx, cs:WPP_GLOBAL_Control
0x18006b2ff  cmp     rbx, rsi
0x18006b302  jz      loc_18006B58E
0x18006b308  test    byte ptr [rbx+1Ch], 80h
0x18006b30c  jz      loc_18006B58E
0x18006b312  cmp     byte ptr [rbx+19h], 2
0x18006b316  jb      loc_18006B58E
0x18006b31c  mov     rbx, [rbx+10h]
0x18006b320  call    cs:__imp_GetLastError
0x18006b327  nop     dword ptr [rax+rax+00h]
0x18006b32c  mov     edx, 30Eh
0x18006b331  jmp     short loc_18006B2CD
0x18006b333  lea     r9, [rbp+0AC0h+ProfileDir]
0x18006b33a  mov     rdx, r15
0x18006b33d  lea     r8, aS_0; "%s\\*"
0x18006b344  lea     rcx, [rbp+0AC0h+FileName]
0x18006b34b  call    StringCchPrintfWrapW
0x18006b350  mov     edi, eax
0x18006b352  test    eax, eax
0x18006b354  jz      short loc_18006B384
0x18006b356  mov     rbx, cs:WPP_GLOBAL_Control
0x18006b35d  cmp     rbx, rsi
0x18006b360  jz      loc_18006B58E
0x18006b366  test    byte ptr [rbx+1Ch], 80h
0x18006b36a  jz      loc_18006B58E
0x18006b370  cmp     byte ptr [rbx+19h], 2
0x18006b374  jb      loc_18006B58E
0x18006b37a  mov     edx, 30Fh
0x18006b37f  jmp     loc_18006B23C
0x18006b384  lea     rdx, [rbp+0AC0h+FindFileData]; lpFindFileData
0x18006b388  lea     rcx, [rbp+0AC0h+FileName]; lpFileName
0x18006b38f  call    cs:__imp_FindFirstFileW
0x18006b396  nop     dword ptr [rax+rax+00h]
0x18006b39b  mov     r12, rax
0x18006b39e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006b3a2  jnz     short loc_18006B3E0
0x18006b3a4  call    cs:__imp_GetLastError
0x18006b3ab  nop     dword ptr [rax+rax+00h]
0x18006b3b0  mov     edi, eax
0x18006b3b2  mov     rbx, cs:WPP_GLOBAL_Control
0x18006b3b9  cmp     rbx, rsi
0x18006b3bc  jz      loc_18006B58E
0x18006b3c2  test    byte ptr [rbx+1Ch], 80h
0x18006b3c6  jz      loc_18006B58E
0x18006b3cc  cmp     byte ptr [rbx+19h], 2
0x18006b3d0  jb      loc_18006B58E
0x18006b3d6  mov     edx, 310h
0x18006b3db  jmp     loc_18006B23C
0x18006b3e0  test    byte ptr [rbp+0AC0h+FindFileData.dwFileAttributes], 10h
0x18006b3e4  jz      loc_18006B56C
0x18006b3ea  cmp     [rbp+0AC0h+FindFileData.cFileName], 2Eh ; '.'
0x18006b3ef  movzx   eax, [rbp+0AC0h+FindFileData.cFileName+2]
0x18006b3f3  jnz     short loc_18006B416
0x18006b3f5  test    ax, ax
0x18006b3f8  jz      loc_18006B56C
0x18006b3fe  cmp     [rbp+0AC0h+FindFileData.cFileName], 2Eh ; '.'
0x18006b403  jnz     short loc_18006B416
0x18006b405  cmp     ax, 2Eh ; '.'
0x18006b409  jnz     short loc_18006B416
0x18006b40b  cmp     [rbp+0AC0h+FindFileData.cFileName+4], r13w
0x18006b410  jz      loc_18006B56C
0x18006b416  lea     rax, aHiddenpbk; "_hiddenPbk\\"
0x18006b41d  test    rbx, rbx
0x18006b420  lea     rcx, aHiddenpbkSyste; "_hiddenPBK\\System\\"
0x18006b427  mov     rdx, r15
0x18006b42a  cmovz   rcx, rax
0x18006b42e  lea     r9, [rbp+0AC0h+ProfileDir]
0x18006b435  mov     rax, [rsp+0BC0h+hMem]
0x18006b43a  lea     r8, aSSSSSS; "%s\\%s\\%s\\%s\\%s%s"
0x18006b441  mov     [rsp+0BC0h+var_B80], rax
0x18006b446  lea     rax, aMicrosoftNetwo_0; "Microsoft\\Network\\Connections\\Pbk"
0x18006b44d  mov     [rsp+0BC0h+var_B88], rcx
0x18006b452  lea     rcx, [rbp+0AC0h+var_460]
0x18006b459  mov     [rsp+0BC0h+var_B90], rax
0x18006b45e  mov     rax, [rsp+0BC0h+var_B60]
0x18006b463  mov     [rsp+0BC0h+var_B98], rax
0x18006b468  lea     rax, [rbp+0AC0h+FindFileData.cFileName]
0x18006b46c  mov     [rsp+0BC0h+var_BA0], rax
0x18006b471  call    StringCchPrintfWrapW
0x18006b476  test    eax, eax
0x18006b478  jnz     loc_18006B56C
0x18006b47e  lea     rcx, [rbp+0AC0h+var_460]; lpFileName
0x18006b485  call    FFileExists
0x18006b48a  test    eax, eax
0x18006b48c  jz      loc_18006B56C
0x18006b492  lea     rax, [rsp+0BC0h+var_B58]
0x18006b497  mov     r8d, 408h
0x18006b49d  lea     r9, [rsp+0BC0h+var_B50]
0x18006b4a2  mov     [rsp+0BC0h+var_BA0], rax
0x18006b4a7  mov     rdx, r14
0x18006b4aa  lea     rcx, [rbp+0AC0h+var_460]
0x18006b4b1  call    GetPbkAndEntryName
0x18006b4b6  mov     edi, eax
0x18006b4b8  test    eax, eax
0x18006b4ba  jz      short loc_18006B50A
0x18006b4bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b4c3  cmp     rcx, rsi
0x18006b4c6  jz      loc_18006B56C
0x18006b4cc  test    byte ptr [rcx+1Ch], 80h
0x18006b4d0  jz      loc_18006B56C
0x18006b4d6  cmp     byte ptr [rcx+19h], 2
0x18006b4da  jb      loc_18006B56C
0x18006b4e0  mov     rcx, [rcx+10h]
0x18006b4e4  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006b4eb  mov     dword ptr [rsp+0BC0h+var_B98], eax
0x18006b4ef  mov     edx, 311h
0x18006b4f4  lea     rax, [rbp+0AC0h+var_894]
0x18006b4fb  mov     r9, r14
0x18006b4fe  mov     [rsp+0BC0h+var_BA0], rax
0x18006b503  call    WPP_SF_SSD
0x18006b508  jmp     short loc_18006B56C
0x18006b50a  mov     rdx, r14
0x18006b50d  mov     [rsp+0BC0h+var_B58], r13
0x18006b512  lea     rcx, [rsp+0BC0h+var_B50]
0x18006b517  call    WritePhonebookFile
0x18006b51c  mov     edi, eax
0x18006b51e  test    eax, eax
0x18006b520  jz      short loc_18006B562
0x18006b522  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b529  cmp     rcx, rsi
0x18006b52c  jz      short loc_18006B562
0x18006b52e  test    byte ptr [rcx+1Ch], 80h
0x18006b532  jz      short loc_18006B562
0x18006b534  cmp     byte ptr [rcx+19h], 2
0x18006b538  jb      short loc_18006B562
0x18006b53a  mov     rcx, [rcx+10h]
0x18006b53e  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006b545  mov     dword ptr [rsp+0BC0h+var_B98], eax
0x18006b549  mov     edx, 312h
0x18006b54e  lea     rax, [rbp+0AC0h+var_894]
0x18006b555  mov     r9, r14
0x18006b558  mov     [rsp+0BC0h+var_BA0], rax
0x18006b55d  call    WPP_SF_SSD
0x18006b562  lea     rcx, [rsp+0BC0h+var_B50]
0x18006b567  call    ClosePhonebookFile
0x18006b56c  lea     rdx, [rbp+0AC0h+FindFileData]; lpFindFileData
0x18006b570  mov     rcx, r12; hFindFile
0x18006b573  call    cs:__imp_FindNextFileW
0x18006b57a  nop     dword ptr [rax+rax+00h]
0x18006b57f  test    eax, eax
0x18006b581  jnz     loc_18006B3E0
0x18006b587  mov     rbx, cs:WPP_GLOBAL_Control
0x18006b58e  mov     rcx, [rsp+0BC0h+hMem]; hMem
0x18006b593  test    rcx, rcx
0x18006b596  jz      short loc_18006B5AB
0x18006b598  call    cs:__imp_GlobalFree
0x18006b59f  nop     dword ptr [rax+rax+00h]
0x18006b5a4  mov     rbx, cs:WPP_GLOBAL_Control
0x18006b5ab  mov     rcx, [rsp+0BC0h+var_B60]; hMem
0x18006b5b0  test    rcx, rcx
0x18006b5b3  jz      short loc_18006B5C8
0x18006b5b5  call    cs:__imp_GlobalFree
0x18006b5bc  nop     dword ptr [rax+rax+00h]
0x18006b5c1  mov     rbx, cs:WPP_GLOBAL_Control
0x18006b5c8  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x18006b5cc  jz      short loc_18006B5E4
0x18006b5ce  mov     rcx, r12; hFindFile
0x18006b5d1  call    cs:__imp_FindClose
0x18006b5d8  nop     dword ptr [rax+rax+00h]
0x18006b5dd  mov     rbx, cs:WPP_GLOBAL_Control
0x18006b5e4  cmp     rbx, rsi
0x18006b5e7  jz      short loc_18006B60D
0x18006b5e9  test    byte ptr [rbx+1Ch], 80h
  ... truncated ...
```
