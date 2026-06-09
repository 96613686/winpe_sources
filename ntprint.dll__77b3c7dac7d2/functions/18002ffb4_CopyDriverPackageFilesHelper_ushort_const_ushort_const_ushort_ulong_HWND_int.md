# CopyDriverPackageFilesHelper(ushort const *,ushort const *,ushort,ulong,HWND__ *,int)

- ea: `0x18002ffb4`
- end: `0x180030911`
- name: `?CopyDriverPackageFilesHelper@@YAJPEBG0GKPEAUHWND__@@H@Z`
- size: `2397`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16, unsigned int, HWND OwnerWindow, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800310a0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x18000d7f0`
- `0x180020b60`
- `0x18002fe14`
- `0x18002fec8`
- `0x18002ffb4`
- `0x180030918`
- `0x180038fc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180030430`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180030430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800300c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003023b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003049f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030515`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800300c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003023b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003049f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030515`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030877`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800306f7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800306f7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180030709`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180030709`
- `SETUPAPI!SetupInitDefaultQueueCallbackEx` at `0x18003082c`
- `SETUPAPI!SetupInitDefaultQueueCallbackEx` at `0x18003082c`
- `SETUPAPI!SetupOpenFileQueue` at `0x1800300f8`
- `SETUPAPI!SetupOpenFileQueue` at `0x1800300f8`
- `SETUPAPI!SetupQueueCopyW` at `0x180030169`
- `SETUPAPI!SetupQueueCopyW` at `0x1800302ae`
- `SETUPAPI!SetupQueueCopyW` at `0x1800307b6`
- `SETUPAPI!SetupQueueCopyW` at `0x180030169`
- `SETUPAPI!SetupQueueCopyW` at `0x1800302ae`
- `SETUPAPI!SetupQueueCopyW` at `0x1800307b6`
- `SETUPAPI!SetupGetStringFieldW` at `0x180030267`
- `SETUPAPI!SetupGetStringFieldW` at `0x1800303f3`
- `SETUPAPI!SetupGetStringFieldW` at `0x180030468`
- `SETUPAPI!SetupGetStringFieldW` at `0x180030495`
- `SETUPAPI!SetupGetStringFieldW` at `0x180030545`
- `SETUPAPI!SetupGetStringFieldW` at `0x180030575`
- `SETUPAPI!SetupGetStringFieldW` at `0x1800305a8`
- `SETUPAPI!SetupGetStringFieldW` at `0x180030267`
- `SETUPAPI!SetupGetStringFieldW` at `0x1800303f3`
- `SETUPAPI!SetupGetStringFieldW` at `0x180030468`
- `SETUPAPI!SetupGetStringFieldW` at `0x180030495`
- `SETUPAPI!SetupGetStringFieldW` at `0x180030545`
- `SETUPAPI!SetupGetStringFieldW` at `0x180030575`
- `SETUPAPI!SetupGetStringFieldW` at `0x1800305a8`
- `SETUPAPI!SetupFindFirstLineW` at `0x180030231`
- `SETUPAPI!SetupFindFirstLineW` at `0x180030509`
- `SETUPAPI!SetupFindFirstLineW` at `0x180030231`
- `SETUPAPI!SetupFindFirstLineW` at `0x180030509`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x180030894`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x180030894`
- `SETUPAPI!SetupCommitFileQueueW` at `0x18003086d`
- `SETUPAPI!SetupCommitFileQueueW` at `0x18003086d`
- `SETUPAPI!SetupGetLineCountW` at `0x180030313`
- `SETUPAPI!SetupGetLineCountW` at `0x1800304e9`
- `SETUPAPI!SetupGetLineCountW` at `0x180030313`
- `SETUPAPI!SetupGetLineCountW` at `0x1800304e9`
- `SETUPAPI!SetupCloseFileQueue` at `0x1800308d8`
- `SETUPAPI!SetupCloseFileQueue` at `0x1800308d8`
- `SETUPAPI!SetupInitDefaultQueueCallback` at `0x180030837`
- `SETUPAPI!SetupInitDefaultQueueCallback` at `0x180030837`
- `SETUPAPI!SetupCloseInfFile` at `0x1800308c9`
- `SETUPAPI!SetupCloseInfFile` at `0x1800308c9`
- `SETUPAPI!SetupGetLineByIndexW` at `0x1800303cb`
- `SETUPAPI!SetupGetLineByIndexW` at `0x1800303cb`
- `SETUPAPI!SetupDefaultQueueCallbackW` at `0x18003084c`

## pseudocode

```c
__int64 __fastcall CopyDriverPackageFilesHelper(
        unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 a3,
        char a4,
        HWND OwnerWindow,
        int a6)
{
  const WCHAR *TargetDirectory; // r14
  unsigned int v7; // ebx
  int v10; // ecx
  int v11; // r13d
  signed int LastError; // ebx
  wchar_t *v13; // rax
  wchar_t *v14; // rsi
  HSPFILEQ v15; // rax
  void *v16; // r15
  signed int v17; // eax
  DWORD v18; // eax
  void *v19; // rsi
  unsigned int v20; // edi
  __int64 v21; // rdx
  unsigned int i; // edi
  void *v23; // rdi
  struct _STRING_LIST *v24; // r14
  unsigned int j; // esi
  unsigned int LineCountW; // eax
  DWORD k; // r13d
  BOOL LineByIndexW; // eax
  DWORD *TargetFilename; // rdi
  unsigned int m; // ebx
  const WCHAR *v31; // rdi
  BOOL FirstLineW; // eax
  unsigned int v33; // r8d
  unsigned int *v34; // r9
  __int64 v35; // rax
  __int64 v36; // rax
  unsigned int v37; // r8d
  unsigned int *v38; // r9
  HANDLE FirstFileW; // rax
  __int64 v40; // rax
  const WCHAR *SourceTagfile; // rdx
  __int64 v42; // rax
  const WCHAR *SourceDescription; // rcx
  __int64 v44; // rax
  PVOID inited; // rax
  void *v46; // rsi
  UINT (__stdcall *v47)(PVOID, UINT, UINT_PTR, UINT_PTR); // r8
  int v48; // edi
  DWORD v49; // eax
  unsigned int v51; // [rsp+50h] [rbp-B0h]
  HINF InfHandle; // [rsp+58h] [rbp-A8h]
  int v54; // [rsp+64h] [rbp-9Ch]
  __int64 v55; // [rsp+68h] [rbp-98h]
  unsigned int v57; // [rsp+74h] [rbp-8Ch]
  struct _INFCONTEXT Context; // [rsp+80h] [rbp-80h] BYREF
  struct _STRING_LIST *v60; // [rsp+98h] [rbp-68h] BYREF
  PCWSTR Section; // [rsp+A0h] [rbp-60h]
  __int64 v62; // [rsp+A8h] [rbp-58h]
  struct _INFCONTEXT v63; // [rsp+B0h] [rbp-50h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR v65[264]; // [rsp+320h] [rbp+220h] BYREF
  WCHAR ReturnBuffer[264]; // [rsp+530h] [rbp+430h] BYREF
  WCHAR v67[264]; // [rsp+740h] [rbp+640h] BYREF
  WCHAR v68[264]; // [rsp+950h] [rbp+850h] BYREF
  wchar_t Str[264]; // [rsp+B60h] [rbp+A60h] BYREF
  WCHAR v70[512]; // [rsp+D70h] [rbp+C70h] BYREF
  WCHAR FileName[264]; // [rsp+1170h] [rbp+1070h] BYREF
  WCHAR Key[512]; // [rsp+1380h] [rbp+1280h] BYREF

  TargetDirectory = a2;
  v7 = a3;
  memset_0(Str, 0, 0x208u);
  if ( !a1 )
    return (unsigned int)-2147024809;
  if ( !TargetDirectory )
    return (unsigned int)-2147024809;
  if ( v7 > 0xC )
    return (unsigned int)-2147024809;
  v10 = 4673;
  if ( !_bittest(&v10, v7) )
    return (unsigned int)-2147024809;
  if ( (a4 & 2) != 0 || (v11 = 1, v54 = 1, a6) )
  {
    v11 = 0;
    v54 = 0;
  }
  LastError = StringCchCopyW(Str, 0x104u, a1);
  if ( LastError >= 0 )
  {
    v13 = wcsrchr(Str, 0x5Cu);
    v14 = v13;
    if ( v13 )
    {
      *v13 = 0;
      InfHandle = (HINF)OpenPrinterInfFile(a1);
      if ( InfHandle == (HINF)-1LL )
      {
        LastError = GetLastError();
        if ( (LastError & 0xE0000000) == 0xE0000000 )
        {
          return (unsigned __int16)LastError | 0x800F0000;
        }
        else if ( LastError > 0 )
        {
          return (unsigned __int16)LastError | 0x80070000;
        }
        return (unsigned int)LastError;
      }
      v15 = SetupOpenFileQueue();
      v16 = v15;
      if ( v15 == (HSPFILEQ)-1LL )
      {
        v17 = GetLastError();
        LastError = v17;
        if ( (v17 & 0xE0000000) == 0xE0000000 )
        {
          LastError = (unsigned __int16)v17;
LABEL_18:
          LastError |= 0x800F0000;
          goto LABEL_119;
        }
        if ( v17 > 0 )
        {
          LastError = (unsigned __int16)v17;
LABEL_118:
          LastError |= 0x80070000;
        }
      }
      else
      {
        if ( !v11 || SetupQueueCopyW(v15, Str, 0, v14 + 1, 0, 0, TargetDirectory, 0, 0) )
        {
          v19 = InfHandle;
          v20 = 0;
          v51 = 0;
          while ( v20 < 4 )
          {
            v21 = v20;
            v55 = v20;
            if ( *((_WORD *)&InfSectionNames + 44 * v20) == a3 )
            {
              if ( v11 )
              {
                for ( i = 0; ; ++i )
                {
                  if ( i >= 3 )
                    goto LABEL_39;
                  memset(&Context, 0, sizeof(Context));
                  memset_0(ReturnBuffer, 0, 0x208u);
                  if ( SetupFindFirstLineW(v19, L"Version", (PCWSTR)*(&InfSectionNames + 11 * v55 + i + 5), &Context) )
                    break;
                  GetLastError();
                }
                ReturnBuffer[0] = 0;
                if ( SetupGetStringFieldW(&Context, 1u, ReturnBuffer, 0x104u, 0)
                  && ReturnBuffer[0]
                  && SetupQueueCopyW(v16, Str, 0, ReturnBuffer, 0, 0, TargetDirectory, 0, 0) )
                {
LABEL_39:
                  v21 = v55;
                  v20 = v51;
                  goto LABEL_40;
                }
                goto LABEL_23;
              }
LABEL_40:
              if ( (a4 & 1) == 0 )
              {
                v23 = InfHandle;
                v24 = 0;
                v60 = 0;
                for ( j = 0; j < 2; ++j )
                {
                  v62 = 11 * v21;
                  Section = (PCWSTR)*(&InfSectionNames + 11 * v21 + j + 1);
                  LineCountW = SetupGetLineCountW(v23, Section);
                  v57 = LineCountW;
                  if ( LineCountW - 1 <= 0xFFFFFFFD )
                  {
                    for ( k = 0; k < LineCountW; ++k )
                    {
                      memset(&v63, 0, sizeof(v63));
                      memset_0(ReturnBuffer, 0, 0x208u);
                      memset_0(v70, 0, sizeof(v70));
                      memset_0(Key, 0, sizeof(Key));
                      memset_0(v68, 0, 0x208u);
                      memset_0(v67, 0, 0x208u);
                      memset_0(v65, 0, 0x208u);
                      LineByIndexW = SetupGetLineByIndexW(v23, Section, k, &v63);
                      TargetFilename = 0;
                      if ( !LineByIndexW || !SetupGetStringFieldW(&v63, 0, ReturnBuffer, 0x104u, 0) )
                        goto LABEL_23;
                      if ( j )
                      {
                        for ( TargetFilename = (DWORD *)v24;
                              TargetFilename;
                              TargetFilename = (DWORD *)*((_QWORD *)TargetFilename + 1) )
                        {
                          if ( !(unsigned int)_o__wcsicmp(ReturnBuffer, *(_QWORD *)TargetFilename) )
                            goto LABEL_96;
                        }
                      }
                      else
                      {
                        AddStringToList(&v60, ReturnBuffer, 0);
                        v24 = v60;
                      }
                      Key[0] = (unsigned __int16)TargetFilename;
                      if ( !SetupGetStringFieldW(&v63, 1u, Key, 0x200u, TargetFilename) )
                        goto LABEL_23;
                      v70[0] = (unsigned __int16)TargetFilename;
                      if ( !SetupGetStringFieldW(&v63, 2u, v70, 0x200u, TargetFilename) )
                      {
                        v18 = GetLastError();
                        LastError = v18;
                        if ( v18 != 87 )
                          goto LABEL_24;
                        v70[0] = (unsigned __int16)TargetFilename;
                      }
                      for ( m = (unsigned int)TargetFilename; m < 2; ++m )
                      {
                        memset(&Context, 0, sizeof(Context));
                        v31 = (const WCHAR *)*(&InfSectionNames + v62 + m + 3);
                        if ( (unsigned int)(SetupGetLineCountW(InfHandle, v31) - 1) > 0xFFFFFFFD )
                        {
                          TargetFilename = 0;
                        }
                        else
                        {
                          FirstLineW = SetupFindFirstLineW(InfHandle, v31, Key, &Context);
                          TargetFilename = 0;
                          if ( FirstLineW )
                          {
                            Key[0] = 0;
                            if ( !SetupGetStringFieldW(&Context, 1u, Key, 0x200u, 0) )
                              goto LABEL_23;
                            v67[0] = 0;
                            if ( !SetupGetStringFieldW(&Context, 2u, v67, 0x104u, 0) )
                              v67[0] = 0;
                            v65[0] = 0;
                            if ( !SetupGetStringFieldW(&Context, 4u, v65, 0x104u, 0) )
                              v65[0] = 0;
                            break;
                          }
                          GetLastError();
                        }
                      }
                      LastError = StringCchCopyW(v68, 0x104u, a2);
                      if ( LastError )
                        goto LABEL_119;
                      v35 = -1;
                      do
                        ++v35;
                      while ( v65[v35] != (_WORD)TargetFilename );
                      if ( v35 )
                        ConcatenatePaths(v68, v65, v33, v34);
                      v36 = -1;
                      do
                        ++v36;
                      while ( v70[v36] != (_WORD)TargetFilename );
                      if ( v36 )
                        ConcatenatePaths(v68, v70, v33, v34);
                      if ( v65[0] == 48 )
                      {
                        if ( v70[0] != 48 )
                        {
                          LastError = StringCchCopyW(v65, 0x104u, v70);
                          if ( LastError )
                            goto LABEL_119;
                        }
                      }
                      else if ( v70[0] != 48 )
                      {
                        ConcatenatePaths(v65, v70, v33, v34);
                      }
                      if ( a6 == (_DWORD)TargetFilename )
                        goto LABEL_89;
                      memset_0(FileName, 0, 0x208u);
                      memset_0(&FindFileData, 0, sizeof(FindFileData));
                      LastError = StringCchCopyW(FileName, 0x104u, v68);
                      if ( LastError < 0 )
                        goto LABEL_119;
                      ConcatenatePaths(FileName, ReturnBuffer, v37, v38);
                      FirstFileW = FindFirstFileW(FileName, &FindFileData);
                      if ( FirstFileW == (HANDLE)-1LL )
                      {
LABEL_89:
                        v40 = -1;
                        do
                          ++v40;
                        while ( v67[v40] != (_WORD)TargetFilename );
                        SourceTagfile = (const WCHAR *)((unsigned __int64)v67 & -(__int64)(v40 != 0));
                        v42 = -1;
                        do
                          ++v42;
                        while ( Key[v42] != (_WORD)TargetFilename );
                        SourceDescription = (const WCHAR *)((unsigned __int64)Key & -(__int64)(v42 != 0));
                        v44 = -1;
                        do
                          ++v44;
                        while ( v65[v44] != (_WORD)TargetFilename );
                        if ( !SetupQueueCopyW(
                                v16,
                                Str,
                                (PCWSTR)((unsigned __int64)v65 & -(__int64)(v44 != 0)),
                                ReturnBuffer,
                                SourceDescription,
                                SourceTagfile,
                                v68,
                                (PCWSTR)TargetFilename,
                                0x408u) )
                          goto LABEL_23;
                      }
                      else
                      {
                        FindClose(FirstFileW);
                      }
LABEL_96:
                      v23 = InfHandle;
                      LineCountW = v57;
                    }
                  }
                  v21 = v55;
                }
                if ( v24 )
                  DestroyStringList(v24);
                v19 = InfHandle;
                v11 = v54;
                TargetDirectory = a2;
                v20 = v51;
              }
            }
            v51 = ++v20;
          }
          if ( OwnerWindow == HWND_MESSAGE|0x2LL )
            inited = SetupInitDefaultQueueCallbackEx(0, HWND_MESSAGE|0x2LL, 0, 0, 0);
          else
            inited = SetupInitDefaultQueueCallback(OwnerWindow);
          v46 = inited;
          if ( !inited )
            goto LABEL_23;
          v47 = SetupDefaultQueueCallbackW;
          v48 = 0;
          if ( OwnerWindow == HWND_MESSAGE|0x2LL )
            v47 = QueueCallback;
          if ( !SetupCommitFileQueueW(0, v16, v47, inited) )
          {
            v49 = GetLastError();
            v48 = v49;
            if ( OwnerWindow == HWND_MESSAGE|0x2LL && v49 == 995 )
              v48 = 2;
          }
          SetupTermDefaultQueueCallback(v46);
          if ( !v48 )
            goto LABEL_119;
          if ( (v48 & 0xE0000000) == 0xE0000000 )
          {
            LastError = (unsigned __int16)v48;
            goto LABEL_18;
          }
          if ( v48 <= 0 )
          {
            LastError = v48;
            goto LABEL_119;
          }
          LastError = (unsigned __int16)v48;
          goto LABEL_118;
        }
LABEL_23:
        v18 = GetLastError();
        LastError = v18;
LABEL_24:
        if ( (v18 & 0xE0000000) == 0xE0000000 )
        {
          LastError = (unsigned __int16)LastError;
          goto LABEL_18;
        }
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError;
          goto LABEL_118;
        }
      }
LABEL_119:
      SetupCloseInfFile(InfHandle);
      if ( v16 != (void *)-1LL )
        SetupCloseFileQueue(v16);
      return (unsigned int)LastError;
    }
    return (unsigned int)-2147024809;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002ffb4  mov     [rsp-8+arg_10], rbx
0x18002ffb9  push    rbp
0x18002ffba  push    rsi
0x18002ffbb  push    rdi
0x18002ffbc  push    r12
0x18002ffbe  push    r13
0x18002ffc0  push    r14
0x18002ffc2  push    r15
0x18002ffc4  lea     rbp, [rsp-1690h]
0x18002ffcc  mov     eax, 1790h
0x18002ffd1  call    _alloca_probe
0x18002ffd6  sub     rsp, rax
0x18002ffd9  mov     rax, cs:__security_cookie
0x18002ffe0  xor     rax, rsp
0x18002ffe3  mov     [rbp+16C0h+var_40], rax
0x18002ffea  mov     r12, [rbp+16C0h+OwnerWindow]
0x18002fff1  mov     r14, rdx
0x18002fff4  movzx   ebx, r8w
0x18002fff8  mov     rdi, rcx
0x18002fffb  mov     [rsp+17C0h+var_1748], rdx
0x180030000  lea     rcx, [rbp+16C0h+Str]; void *
0x180030007  xor     edx, edx; Val
0x180030009  mov     [rsp+17C0h+var_1760], bx
0x18003000e  mov     r8d, 208h; Size
0x180030014  mov     [rsp+17C0h+var_1750], r9d
0x180030019  mov     esi, r9d
0x18003001c  call    memset_0
0x180030021  xor     r15d, r15d
0x180030024  test    rdi, rdi
0x180030027  jz      loc_1800308E0
0x18003002d  test    r14, r14
0x180030030  jz      loc_1800308E0
0x180030036  cmp     ebx, 0Ch
0x180030039  ja      loc_1800308E0
0x18003003f  mov     ecx, 1241h
0x180030044  bt      ecx, ebx
0x180030047  jnb     loc_1800308E0
0x18003004d  test    sil, 2
0x180030051  jnz     short loc_180030065
0x180030053  lea     r13d, [r15+1]
0x180030057  mov     [rsp+17C0h+var_175C], r13d
0x18003005c  cmp     [rbp+16C0h+arg_28], r15d
0x180030063  jz      short loc_18003006D
0x180030065  mov     r13d, r15d
0x180030068  mov     [rsp+17C0h+var_175C], r15d
0x18003006d  mov     r8, rdi; unsigned __int16 *
0x180030070  lea     rcx, [rbp+16C0h+Str]; unsigned __int16 *
0x180030077  mov     edx, 104h; unsigned __int64
0x18003007c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030081  mov     ebx, eax
0x180030083  test    eax, eax
0x180030085  js      loc_1800308E5
0x18003008b  mov     edx, 5Ch ; '\'; Ch
0x180030090  lea     rcx, [rbp+16C0h+Str]; Str
0x180030097  call    ?wcsrchr@@YAPEAGPEAGG@Z; wcsrchr(ushort *,ushort)
0x18003009c  mov     rsi, rax
0x18003009f  test    rax, rax
0x1800300a2  jz      loc_1800308E0
0x1800300a8  xor     edx, edx
0x1800300aa  mov     [rax], r15w
0x1800300ae  mov     rcx, rdi; unsigned __int16 *
0x1800300b1  call    OpenPrinterInfFile
0x1800300b6  mov     [rsp+17C0h+InfHandle], rax
0x1800300bb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800300bf  jnz     short loc_1800300F8
0x1800300c1  call    cs:__imp_GetLastError
0x1800300c7  mov     edx, 0E0000000h
0x1800300cc  mov     ebx, eax
0x1800300ce  and     eax, edx
0x1800300d0  cmp     eax, edx
0x1800300d2  jnz     short loc_1800300E2
0x1800300d4  movzx   ebx, bx
0x1800300d7  or      ebx, 800F0000h
0x1800300dd  jmp     loc_1800308E5
0x1800300e2  test    ebx, ebx
0x1800300e4  jle     loc_1800308E5
0x1800300ea  movzx   ebx, bx
0x1800300ed  or      ebx, 80070000h
0x1800300f3  jmp     loc_1800308E5
0x1800300f8  call    cs:__imp_SetupOpenFileQueue
0x1800300fe  mov     r15, rax
0x180030101  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030105  jnz     short loc_18003013A
0x180030107  call    cs:__imp_GetLastError
0x18003010d  mov     edx, 0E0000000h
0x180030112  mov     ecx, eax
0x180030114  and     ecx, edx
0x180030116  mov     ebx, eax
0x180030118  cmp     ecx, edx
0x18003011a  jnz     short loc_18003012A
0x18003011c  movzx   ebx, ax
0x18003011f  or      ebx, 800F0000h
0x180030125  jmp     loc_1800308C4
0x18003012a  test    eax, eax
0x18003012c  jle     loc_1800308C4
0x180030132  movzx   ebx, ax
0x180030135  jmp     loc_1800308BE
0x18003013a  xor     r8d, r8d; SourcePath
0x18003013d  test    r13d, r13d
0x180030140  jz      short loc_18003019E
0x180030142  mov     [rsp+17C0h+CopyStyle], r8d; CopyStyle
0x180030147  lea     r9, [rsi+2]; SourceFilename
0x18003014b  mov     [rsp+17C0h+TargetFilename], r8; TargetFilename
0x180030150  lea     rdx, [rbp+16C0h+Str]; SourceRootPath
0x180030157  mov     [rsp+17C0h+TargetDirectory], r14; TargetDirectory
0x18003015c  mov     rcx, r15; QueueHandle
0x18003015f  mov     [rsp+17C0h+SourceTagfile], r8; SourceTagfile
0x180030164  mov     [rsp+17C0h+SourceDescription], r8; SourceDescription
0x180030169  call    cs:__imp_SetupQueueCopyW
0x18003016f  xor     r8d, r8d
0x180030172  test    eax, eax
0x180030174  jnz     short loc_18003019E
0x180030176  call    cs:__imp_GetLastError
0x18003017c  mov     ebx, eax
0x18003017e  mov     edx, 0E0000000h
0x180030183  and     eax, edx
0x180030185  cmp     eax, edx
0x180030187  jnz     short loc_18003018E
0x180030189  movzx   ebx, bx
0x18003018c  jmp     short loc_18003011F
0x18003018e  test    ebx, ebx
0x180030190  jle     loc_1800308C4
0x180030196  movzx   ebx, bx
0x180030199  jmp     loc_1800308BE
0x18003019e  mov     rsi, [rsp+17C0h+InfHandle]
0x1800301a3  mov     edi, r8d
0x1800301a6  mov     [rsp+17C0h+var_1770], r8d
0x1800301ab  lea     r9, ?InfSectionNames@@3PAU_INF_SECTION_NAMES@@A; _INF_SECTION_NAMES near * InfSectionNames
0x1800301b2  cmp     edi, 4
0x1800301b5  jnb     loc_180030816
0x1800301bb  movzx   ecx, [rsp+17C0h+var_1760]
0x1800301c0  mov     edx, edi
0x1800301c2  imul    rax, rdx, 58h ; 'X'
0x1800301c6  mov     [rsp+17C0h+var_1758], rdx
0x1800301cb  cmp     [rax+r9], cx
0x1800301d0  jnz     loc_180030808
0x1800301d6  test    r13d, r13d
0x1800301d9  jz      loc_1800302D4
0x1800301df  mov     edi, r8d
0x1800301e2  cmp     edi, 3
0x1800301e5  jnb     loc_1800302C1
0x1800301eb  xorps   xmm0, xmm0
0x1800301ee  lea     rcx, [rbp+16C0h+ReturnBuffer]; void *
0x1800301f5  xor     eax, eax
0x1800301f7  xor     edx, edx; Val
0x1800301f9  mov     r8d, 208h; Size
0x1800301ff  mov     qword ptr [rbp+16C0h+Context.Section], rax
0x180030203  movups  xmmword ptr [rbp+16C0h+Context.Inf], xmm0
0x180030207  call    memset_0
0x18003020c  imul    r8, [rsp+17C0h+var_1758], 0Bh
0x180030212  mov     eax, edi
0x180030214  lea     r9, [rbp+16C0h+Context]; Context
0x180030218  add     r8, rax
0x18003021b  lea     rdx, cszVersion; "Version"
0x180030222  lea     rax, ?InfSectionNames@@3PAU_INF_SECTION_NAMES@@A; _INF_SECTION_NAMES near * InfSectionNames
0x180030229  mov     rcx, rsi; InfHandle
0x18003022c  mov     r8, [rax+r8*8+28h]; Key
0x180030231  call    cs:__imp_SetupFindFirstLineW
0x180030237  test    eax, eax
0x180030239  jnz     short loc_180030245
0x18003023b  call    cs:__imp_GetLastError
0x180030241  inc     edi
0x180030243  jmp     short loc_1800301E2
0x180030245  xor     edi, edi
0x180030247  lea     r8, [rbp+16C0h+ReturnBuffer]; ReturnBuffer
0x18003024e  mov     r9d, 104h; ReturnBufferSize
0x180030254  mov     [rbp+16C0h+ReturnBuffer], di
0x18003025b  lea     rcx, [rbp+16C0h+Context]; Context
0x18003025f  mov     [rsp+17C0h+SourceDescription], rdi; RequiredSize
0x180030264  lea     edx, [rdi+1]; FieldIndex
0x180030267  call    cs:__imp_SetupGetStringFieldW
0x18003026d  test    eax, eax
0x18003026f  jz      loc_180030176
0x180030275  cmp     [rbp+16C0h+ReturnBuffer], di
0x18003027c  jz      loc_180030176
0x180030282  mov     [rsp+17C0h+CopyStyle], edi; CopyStyle
0x180030286  lea     r9, [rbp+16C0h+ReturnBuffer]; SourceFilename
0x18003028d  mov     [rsp+17C0h+TargetFilename], rdi; TargetFilename
0x180030292  lea     rdx, [rbp+16C0h+Str]; SourceRootPath
0x180030299  mov     [rsp+17C0h+TargetDirectory], r14; TargetDirectory
0x18003029e  xor     r8d, r8d; SourcePath
0x1800302a1  mov     [rsp+17C0h+SourceTagfile], rdi; SourceTagfile
0x1800302a6  mov     rcx, r15; QueueHandle
0x1800302a9  mov     [rsp+17C0h+SourceDescription], rdi; SourceDescription
0x1800302ae  call    cs:__imp_SetupQueueCopyW
0x1800302b4  xor     r8d, r8d
0x1800302b7  test    eax, eax
0x1800302b9  jz      loc_180030176
0x1800302bf  jmp     short loc_1800302C4
0x1800302c1  xor     r8d, r8d
0x1800302c4  mov     rdx, [rsp+17C0h+var_1758]
0x1800302c9  lea     r9, ?InfSectionNames@@3PAU_INF_SECTION_NAMES@@A; _INF_SECTION_NAMES near * InfSectionNames
0x1800302d0  mov     edi, [rsp+17C0h+var_1770]
0x1800302d4  test    byte ptr [rsp+17C0h+var_1750], 1
0x1800302d9  jnz     loc_180030808
0x1800302df  mov     rdi, [rsp+17C0h+InfHandle]
0x1800302e4  mov     r14, r8
0x1800302e7  mov     [rbp+16C0h+var_1728], r8
0x1800302eb  mov     esi, r8d
0x1800302ee  cmp     esi, 2
0x1800302f1  jnb     loc_1800307E8
0x1800302f7  imul    rcx, rdx, 0Bh
0x1800302fb  mov     eax, esi
0x1800302fd  add     rax, rcx
0x180030300  mov     [rbp+16C0h+var_1718], rcx
0x180030304  mov     rcx, rdi; InfHandle
0x180030307  mov     rax, [r9+rax*8+8]
0x18003030c  mov     rdx, rax; Section
0x18003030f  mov     [rbp+16C0h+Section], rax
0x180030313  call    cs:__imp_SetupGetLineCountW
0x180030319  mov     [rsp+17C0h+var_174C], eax
0x18003031d  lea     ecx, [rax-1]
0x180030320  cmp     ecx, 0FFFFFFFDh
0x180030323  ja      loc_1800307D5
0x180030329  xor     r8d, r8d
0x18003032c  mov     r13d, r8d
0x18003032f  cmp     r13d, eax
0x180030332  jnb     loc_1800307D5
0x180030338  xorps   xmm0, xmm0
0x18003033b  lea     rcx, [rbp+16C0h+ReturnBuffer]; void *
0x180030342  xor     eax, eax
0x180030344  xor     edx, edx; Val
0x180030346  mov     r8d, 208h; Size
0x18003034c  mov     qword ptr [rbp+16C0h+var_1710.Section], rax
0x180030350  movups  xmmword ptr [rbp+16C0h+var_1710.Inf], xmm0
0x180030354  call    memset_0
0x180030359  xor     edx, edx; Val
0x18003035b  lea     rcx, [rbp+16C0h+var_A50]; void *
0x180030362  mov     r8d, 400h; Size
0x180030368  call    memset_0
0x18003036d  xor     edx, edx; Val
0x18003036f  lea     rcx, [rbp+16C0h+Key]; void *
0x180030376  mov     r8d, 400h; Size
0x18003037c  call    memset_0
0x180030381  xor     edx, edx; Val
0x180030383  lea     rcx, [rbp+16C0h+var_E70]; void *
0x18003038a  mov     r8d, 208h; Size
0x180030390  call    memset_0
0x180030395  xor     edx, edx; Val
0x180030397  lea     rcx, [rbp+16C0h+var_1080]; void *
0x18003039e  mov     r8d, 208h; Size
0x1800303a4  call    memset_0
0x1800303a9  xor     edx, edx; Val
0x1800303ab  lea     rcx, [rbp+16C0h+var_14A0]; void *
0x1800303b2  mov     r8d, 208h; Size
0x1800303b8  call    memset_0
0x1800303bd  mov     rdx, [rbp+16C0h+Section]; Section
0x1800303c1  lea     r9, [rbp+16C0h+var_1710]; Context
0x1800303c5  mov     r8d, r13d; Index
0x1800303c8  mov     rcx, rdi; InfHandle
0x1800303cb  call    cs:__imp_SetupGetLineByIndexW
0x1800303d1  xor     edi, edi
0x1800303d3  test    eax, eax
0x1800303d5  jz      loc_180030176
0x1800303db  mov     r9d, 104h; ReturnBufferSize
0x1800303e1  mov     [rsp+17C0h+SourceDescription], rdi; RequiredSize
0x1800303e6  lea     r8, [rbp+16C0h+ReturnBuffer]; ReturnBuffer
0x1800303ed  xor     edx, edx; FieldIndex
0x1800303ef  lea     rcx, [rbp+16C0h+var_1710]; Context
0x1800303f3  call    cs:__imp_SetupGetStringFieldW
0x1800303f9  test    eax, eax
0x1800303fb  jz      loc_180030176
0x180030401  test    esi, esi
0x180030403  jnz     short loc_18003041E
0x180030405  xor     r8d, r8d; int
0x180030408  lea     rdx, [rbp+16C0h+ReturnBuffer]; unsigned __int16 *
0x18003040f  lea     rcx, [rbp+16C0h+var_1728]; struct _STRING_LIST **
0x180030413  call    ?AddStringToList@@YAXPEAPEAU_STRING_LIST@@PEAGH@Z; AddStringToList(_STRING_LIST * *,ushort *,int)
0x180030418  mov     r14, [rbp+16C0h+var_1728]
0x18003041c  jmp     short loc_180030444
0x18003041e  mov     rdi, r14
0x180030421  test    rdi, rdi
0x180030424  jz      short loc_180030444
0x180030426  mov     rdx, [rdi]
0x180030429  lea     rcx, [rbp+16C0h+ReturnBuffer]
0x180030430  call    cs:__imp__o__wcsicmp
0x180030436  test    eax, eax
0x180030438  jz      loc_1800307C4
0x18003043e  mov     rdi, [rdi+8]
0x180030442  jmp     short loc_180030421
0x180030444  mov     ebx, 200h
0x180030449  mov     [rbp+16C0h+Key], di
0x180030450  mov     r9d, ebx; ReturnBufferSize
0x180030453  mov     [rsp+17C0h+SourceDescription], rdi; RequiredSize
0x180030458  lea     r8, [rbp+16C0h+Key]; ReturnBuffer
0x18003045f  mov     edx, 1; FieldIndex
0x180030464  lea     rcx, [rbp+16C0h+var_1710]; Context
0x180030468  call    cs:__imp_SetupGetStringFieldW
0x18003046e  test    eax, eax
0x180030470  jz      loc_180030176
0x180030476  mov     r9d, ebx; ReturnBufferSize
0x180030479  mov     [rbp+16C0h+var_A50], di
0x180030480  lea     r8, [rbp+16C0h+var_A50]; ReturnBuffer
0x180030487  mov     [rsp+17C0h+SourceDescription], rdi; RequiredSize
0x18003048c  mov     edx, 2; FieldIndex
0x180030491  lea     rcx, [rbp+16C0h+var_1710]; Context
0x180030495  call    cs:__imp_SetupGetStringFieldW
0x18003049b  test    eax, eax
0x18003049d  jnz     short loc_1800304B7
0x18003049f  call    cs:__imp_GetLastError
  ... truncated ...
```
