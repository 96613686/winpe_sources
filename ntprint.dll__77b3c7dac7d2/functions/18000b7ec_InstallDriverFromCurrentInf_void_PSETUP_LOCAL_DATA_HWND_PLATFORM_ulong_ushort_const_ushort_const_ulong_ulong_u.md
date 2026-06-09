# InstallDriverFromCurrentInf(void *,_PSETUP_LOCAL_DATA *,HWND__ *,PLATFORM,ulong,ushort const *,ushort const *,ulong,ulong,ulong *)

- ea: `0x18000b7ec`
- end: `0x18000c24a`
- name: `?InstallDriverFromCurrentInf@@YAKPEAXPEAU_PSETUP_LOCAL_DATA@@PEAUHWND__@@W4PLATFORM@@KPEBG4KKPEAK@Z`
- size: `2654`
- prototype: `unsigned int __high(void *, struct _PSETUP_LOCAL_DATA *, HWND, enum PLATFORM, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `35`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000b498`
- `0x1800113c0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x1800078f0`
- `0x180007944`
- `0x1800093a4`
- `0x18000b200`
- `0x18000b7ec`
- `0x18000d314`
- `0x18000eb10`
- `0x18000f698`
- `0x180010ba0`
- `0x180012b28`
- `0x180018d18`
- `0x18001b648`
- `0x18001b9d8`
- `0x18001bc44`
- `0x18001c298`
- `0x18001c680`
- `0x18001d13c`
- `0x18001e07c`
- `0x18001e3c0`
- `0x18001e4f0`
- `0x18001e8b0`
- `0x180020384`
- `0x1800204e0`
- `0x180020998`
- `0x180023318`
- `0x18002354c`
- `0x180027570`
- `0x18002b2fc`
- `0x18002c3d0`
- `0x180034bec`
- `0x180036080`
- `0x180036248`
- `0x180036664`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c08e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c08e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000bab2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000be62`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000bab2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000be62`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000bd06`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000bf35`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000bd06`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000bf35`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000bd31`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000bfd5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000bd31`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000bfd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bfc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bfec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c024`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c036`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bfc4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bfec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c024`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c036`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18000bdc4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18000bdc4`
- `WINSPOOL!OpenPrinterW` at `0x18000c080`
- `WINSPOOL!OpenPrinterW` at `0x18000c080`
- `WINSPOOL!ClosePrinter` at `0x18000c136`
- `WINSPOOL!ClosePrinter` at `0x18000c136`

## string_xrefs

- `0x18000c1c9`: `InstallDriverFromCurrentInf`

## pseudocode

```c
__int64 __fastcall InstallDriverFromCurrentInf(
        FILETIME a1,
        DWORDLONG *a2,
        HWND a3,
        int a4,
        int a5,
        LPWSTR pPrinterName,
        const WCHAR *a7,
        unsigned int a8,
        int a9,
        __int64 a10)
{
  unsigned __int16 *v11; // r12
  __int64 v12; // r13
  int v13; // ecx
  void *v14; // r14
  signed int IsNullPrinterDriver; // ebx
  unsigned int v16; // esi
  __int64 v17; // rdx
  BOOL v18; // r15d
  int v19; // eax
  wchar_t *v20; // rcx
  void *v21; // r12
  int v22; // r14d
  int v23; // r15d
  int v24; // edx
  __int64 *v25; // rcx
  int v26; // r14d
  NCoreLibrary *v27; // rcx
  HANDLE v28; // r14
  signed int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  LONG v32; // eax
  HWND v33; // r15
  HANDLE FirstFileW; // r14
  DWORDLONG v35; // r9
  wchar_t *v36; // r8
  wchar_t *v37; // rcx
  bool v38; // sf
  int v39; // edx
  const unsigned __int16 *v40; // rcx
  DWORD LastError; // eax
  unsigned int v42; // eax
  int v43; // eax
  __int64 v45; // [rsp+64h] [rbp-9Ch] BYREF
  int v46[2]; // [rsp+70h] [rbp-90h]
  int v47; // [rsp+78h] [rbp-88h]
  HANDLE phPrinter; // [rsp+80h] [rbp-80h] BYREF
  int v49; // [rsp+88h] [rbp-78h]
  DWORDLONG v50; // [rsp+90h] [rbp-70h] BYREF
  __int64 v51; // [rsp+98h] [rbp-68h] BYREF
  FILETIME FileTime1; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL hMem; // [rsp+A8h] [rbp-58h] BYREF
  HWND Owner; // [rsp+B0h] [rbp-50h]
  int v55; // [rsp+B8h] [rbp-48h] BYREF
  DWORDLONG v56; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v57; // [rsp+C8h] [rbp-38h]
  FILETIME FileTime2; // [rsp+D0h] [rbp-30h]
  FILETIME v59; // [rsp+D8h] [rbp-28h] BYREF
  _PRINTER_DEFAULTSW pDefault; // [rsp+E0h] [rbp-20h] BYREF
  struct _WIN32_FIND_DATAW Buffer; // [rsp+100h] [rbp+0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+350h] [rbp+250h] BYREF
  OLECHAR sz[40]; // [rsp+5A0h] [rbp+4A0h] BYREF
  unsigned __int16 v64[264]; // [rsp+5F0h] [rbp+4F0h] BYREF

  v11 = pPrinterName;
  Owner = a3;
  FileTime2 = a1;
  phPrinter = pPrinterName;
  v57 = a10;
  v12 = a4;
  memset_0(v64, 0, 0x208u);
  v14 = 0;
  v49 = 0;
  v55 = 0;
  if ( a2 && (unsigned int)ValidPlatform((unsigned int)v12) )
  {
    IsNullPrinterDriver = 0;
  }
  else
  {
    IsNullPrinterDriver = -2147024809;
    if ( !a2 )
      return StatusFromHResult((unsigned int)IsNullPrinterDriver);
  }
  if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
    McTemplateU0zzz_EventWriteTransfer(
      v13,
      (unsigned int)DocPerf_Setup_InstallDriverFromCurrentInf_Start,
      *a2,
      (_DWORD)pPrinterName,
      a2[1]);
  if ( IsNullPrinterDriver >= 0 )
  {
    v16 = a8 & 0xFFFFFFF7;
    if ( (a8 & 0x20) == 0 )
      v16 = a8;
    if ( (v16 & 0x20) != 0 && (unsigned int)IsInfInDriverStore((wchar_t *)*a2) )
      v16 &= ~0x20u;
    IsNullPrinterDriver = InfFileIsNullPrinterDriver(a2, (unsigned int)v12, &v55);
    if ( IsNullPrinterDriver >= 0 )
    {
      if ( v55 )
      {
        IsNullPrinterDriver = -2147467259;
        goto LABEL_115;
      }
      IsNullPrinterDriver = InfFileIsPackageAware((unsigned __int16 *)*a2);
      if ( IsNullPrinterDriver >= 0 )
      {
        if ( (unsigned int)IsLonghornOrAbove(pPrinterName) && (v16 & 0x20) == 0 && !(unsigned int)IsNTPrintInf(*a2, v17) )
        {
          FileTime1 = 0;
          FileTime2 = 0;
          v18 = MyPlatform == v12;
          v50 = 0;
          v45 = __PAIR64__(v18, MyPlatform);
          hMem = 0;
          *(_QWORD *)v46 = 0;
          IsNullPrinterDriver = GetServerPlatform(pPrinterName, &v45);
          if ( IsNullPrinterDriver < 0 )
          {
LABEL_93:
            v13 = (int)hMem;
            if ( hMem )
            {
              LocalFree(hMem);
              hMem = 0;
            }
            if ( v14 )
              LocalFree(v14);
            goto LABEL_97;
          }
          if ( v49 )
          {
            v19 = ObtainPackageInfInfo((unsigned __int16 *)*a2, &FileTime1, &v50);
          }
          else
          {
            LOBYTE(v14) = (_DWORD)v45 == (_DWORD)v12;
            if ( (_DWORD)v14 )
              goto LABEL_29;
            IsNullPrinterDriver = DoesDriverUseIncludeNeeds(pPrinterName, (__int64)&hMem);
            if ( IsNullPrinterDriver < 0 )
              goto LABEL_92;
            if ( !hMem )
              goto LABEL_29;
            memset_0(sz, 0, sizeof(sz));
            IsNullPrinterDriver = StringCchCopyW(sz, 0x27u, L"{D20EA372-DD35-4950-9ED8-A6335AFE79F0}");
            if ( IsNullPrinterDriver < 0 )
            {
LABEL_92:
              v14 = *(void **)v46;
              goto LABEL_93;
            }
            v19 = CovertGuidMultiSzToArray(sz);
          }
          IsNullPrinterDriver = v19;
          if ( v19 >= 0 )
          {
LABEL_29:
            LODWORD(v45) = 0;
            if ( !hMem )
            {
              v14 = *(void **)v46;
LABEL_31:
              v20 = (wchar_t *)*a2;
              HIDWORD(v45) = 260;
              IsNullPrinterDriver = UploadPrinterDriverHelper(
                                      v20,
                                      v11,
                                      Owner,
                                      (unsigned int)v12,
                                      v16,
                                      v64,
                                      (char *)&v45 + 4);
              if ( IsNullPrinterDriver >= 0 )
                IsNullPrinterDriver = InstallPrinterDriverFromInfPackage(
                                        v11,
                                        v64,
                                        (unsigned __int16 *)a2[1],
                                        v16,
                                        a9,
                                        v57);
              goto LABEL_93;
            }
            v21 = 0;
            v51 = 0;
            v47 = IsLocalMachine((LPCWSTR)phPrinter);
            v45 = 0;
            v22 = 0;
            memset_0(&FindFileData, 0, sizeof(FindFileData));
            if ( !v18 && !a2[54] )
            {
              v23 = 1;
              if ( IsNullPrinterDriver < 0 )
                goto LABEL_87;
              goto LABEL_36;
            }
            memset_0(&Buffer, 0, 0x208u);
            v59 = 0;
            v56 = 0;
            if ( v18 )
            {
              if ( !GetSystemWindowsDirectoryW((LPWSTR)&Buffer, 0x104u) )
              {
                IsNullPrinterDriver = GetLastErrorAsHResult();
                if ( IsNullPrinterDriver < 0 )
                  goto LABEL_66;
              }
              v30 = -1;
              do
                ++v30;
              while ( *((_WORD *)&Buffer.dwFileAttributes + v30) );
              if ( *((_WORD *)&Buffer.dwFileAttributes + (unsigned int)(v30 - 1)) != 92 )
              {
                IsNullPrinterDriver = StringCchCatW((unsigned __int16 *)&Buffer, 0x104u, L"\\");
                if ( IsNullPrinterDriver < 0 )
                  goto LABEL_66;
              }
              v31 = StringCchCatW((unsigned __int16 *)&Buffer, 0x104u, gcszNtprintInfPath);
            }
            else
            {
              v31 = StringCchCopyW((unsigned __int16 *)&Buffer, 0x104u, (const unsigned __int16 *)a2[54]);
            }
            IsNullPrinterDriver = v31;
LABEL_66:
            if ( IsNullPrinterDriver >= 0 )
            {
              IsNullPrinterDriver = GetInfDriverVerInfo(&Buffer, &v59, &v56);
              if ( IsNullPrinterDriver >= 0 )
              {
                v32 = CompareFileTime(&FileTime1, &v59);
                if ( v32 == -1 || (v23 = 1, !v32) && v56 >= v50 )
                {
                  v24 = v47;
                  v22 = 1;
                  LODWORD(v45) = 1;
                  if ( !v47 || a2[54] )
                  {
                    v21 = (void *)AllocStr((unsigned __int16 *)&Buffer);
                    if ( !v21 )
                    {
                      IsNullPrinterDriver = -2147024882;
                      goto LABEL_87;
                    }
LABEL_77:
                    v33 = Owner;
                    LODWORD(v45) = 260;
                    IsNullPrinterDriver = UploadPrinterDriverHelper(
                                            v21,
                                            phPrinter,
                                            Owner,
                                            (unsigned int)v12,
                                            v16,
                                            v64,
                                            &v45);
                    if ( HIDWORD(v45) )
                    {
                      memset_0(&Buffer, 0, sizeof(Buffer));
                      FirstFileW = FindFirstFileW((LPCWSTR)*a2, &Buffer);
                      if ( FirstFileW != (HANDLE)-1LL
                        && Buffer.nFileSizeHigh == FindFileData.nFileSizeHigh
                        && Buffer.nFileSizeLow == FindFileData.nFileSizeLow )
                      {
                        goto LABEL_85;
                      }
                      v35 = a2[1];
                      v36 = (wchar_t *)*a2;
                      v56 = 0;
                      IsNullPrinterDriver = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))PromptForOriginalDriverMedia)(
                                              v33,
                                              (unsigned int)v12,
                                              v36,
                                              v35,
                                              0,
                                              *(_QWORD *)v46,
                                              FileTime1,
                                              v50,
                                              &FindFileData,
                                              &v56);
                      if ( IsNullPrinterDriver >= 0 && v56 )
                      {
                        v37 = (wchar_t *)*a2;
                        *a2 = v56;
                        LocalFree(v37);
                      }
                      if ( FirstFileW != (HANDLE)-1LL )
LABEL_85:
                        FindClose(FirstFileW);
                    }
                    goto LABEL_87;
                  }
                  v23 = 0;
LABEL_37:
                  if ( v22 )
                    goto LABEL_53;
                  v25 = &v51;
                  if ( v24 )
                    v25 = 0;
                  IsNullPrinterDriver = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))AllInboxCoreDriversInLocalDriverStore)(
                                          (unsigned int)v12,
                                          0,
                                          *(_QWORD *)v46,
                                          FileTime1,
                                          v50,
                                          hMem,
                                          &v45,
                                          v25);
                  if ( IsNullPrinterDriver >= 0 )
                  {
                    v26 = v45;
                    v21 = (void *)v51;
                    if ( (_DWORD)v45 )
                    {
                      if ( v47 )
                        v23 = 0;
LABEL_53:
                      if ( IsNullPrinterDriver < 0 || !v23 )
                        goto LABEL_87;
                      goto LABEL_77;
                    }
                    IsNullPrinterDriver = FindNtprintInfOnDisk(
                                            (unsigned __int16 *)*a2,
                                            v12,
                                            0,
                                            v46[0],
                                            FileTime1,
                                            v50,
                                            (__int64)&v51);
                    if ( IsNullPrinterDriver >= 0 )
                    {
                      v21 = (void *)v51;
                      if ( v51 )
                        v26 = 1;
                      if ( !v26 )
                      {
                        if ( (v16 & 8) != 0 )
                        {
                          IsNullPrinterDriver = -2147023673;
                          goto LABEL_87;
                        }
                        v28 = FindFirstFileW((LPCWSTR)*a2, &FindFileData);
                        if ( v28 == (HANDLE)-1LL )
                        {
                          IsNullPrinterDriver = NCoreLibrary::GetLastErrorAsFailHR(v27);
                          if ( IsNullPrinterDriver < 0 )
                          {
LABEL_87:
                            if ( v21 )
                              LocalFree(v21);
                            v11 = (unsigned __int16 *)phPrinter;
                            v14 = *(void **)v46;
                            if ( IsNullPrinterDriver < 0 )
                              goto LABEL_93;
                            goto LABEL_31;
                          }
                        }
                        HIDWORD(v45) = 1;
                        FindClose(v28);
                        v29 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))PromptAndRetrieveVerifyVerNtprintInfPath)(
                                Owner,
                                (unsigned int)v12,
                                0,
                                0,
                                *(_QWORD *)v46,
                                FileTime1,
                                v50,
                                hMem,
                                &v51);
                        v21 = (void *)v51;
                        IsNullPrinterDriver = v29;
                      }
                      goto LABEL_53;
                    }
                  }
                  v21 = (void *)v51;
                  goto LABEL_87;
                }
LABEL_36:
                v24 = v47;
                goto LABEL_37;
              }
            }
            v11 = (unsigned __int16 *)phPrinter;
            goto LABEL_92;
          }
          goto LABEL_92;
        }
        *(_QWORD *)&pDefault.DesiredAccess = 0x1000000;
        phPrinter = 0;
        *(_OWORD *)&pDefault.pDatatype = 0;
        if ( OpenPrinterW(pPrinterName, &phPrinter, &pDefault) )
        {
          ClosePrinter(phPrinter);
          phPrinter = 0;
        }
        else
        {
          LastError = GetLastError();
          v13 = 0;
          LOWORD(IsNullPrinterDriver) = 5;
          if ( LastError == 5 )
          {
            if ( (v16 & 0x28) == 0x20 && (unsigned int)IsLocalMachine(pPrinterName) )
            {
              HIDWORD(v45) = 0;
              v42 = RunningAsLUA((int *)&v45 + 1);
              v43 = StatusFromHResult(v42);
              if ( v43 )
                goto LABEL_111;
              if ( HIDWORD(v45) )
              {
                v43 = ElevateAndCallLegacyPrintDriverInstall(
                        *a2,
                        a2[1],
                        Owner,
                        (unsigned int)v12,
                        a5,
                        pPrinterName,
                        a7,
                        v16,
                        a9,
                        v57);
                goto LABEL_111;
              }
            }
            else
            {
              LOWORD(IsNullPrinterDriver) = 5;
            }
LABEL_112:
            IsNullPrinterDriver = (unsigned __int16)IsNullPrinterDriver | 0x80070000;
LABEL_97:
            v38 = IsNullPrinterDriver < 0;
            goto LABEL_98;
          }
        }
        v43 = LegacyPrintDriverInstall(
                *(HDEVINFO *)&FileTime2,
                (struct _PSETUP_LOCAL_DATA *)a2,
                (__int64)Owner,
                v12,
                a5,
                pPrinterName,
                a7,
                v16,
                a9,
                (unsigned int *)v57);
LABEL_111:
        IsNullPrinterDriver = v43;
        v38 = v43 < 0;
        if ( v43 <= 0 )
        {
LABEL_98:
          if ( !v38 )
          {
            v39 = *((_DWORD *)a2 + 43);
            if ( v39 )
              v40 = (const unsigned __int16 *)a2[28];
            else
              v40 = 0;
            SplLogPrinterSetupCoreDriverEvent(
              &SETUP_INSTALL_PRINTER_DRIVER_SUCCEEDED,
              L"InstallDriverFromCurrentInf",
              0,
              v11,
              (const unsigned __int16 *)*a2,
              (const unsigned __int16 *)a2[1],
              (const unsigned __int16 *)a2[23],
              (const unsigned __int16 *)PlatformEnv[v12],
              v39,
              v40,
              0,
              0);
          }
          goto LABEL_115;
        }
        goto LABEL_112;
      }
    }
  }
LABEL_115:
  if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
    McTemplateU0zzz_EventWriteTransfer(
      v13,
      (unsigned int)DocPerf_Setup_InstallDriverFromCurrentInf_Stop,
      *a2,
      (_DWORD)v11,
      a2[1]);
  return StatusFromHResult((unsigned int)IsNullPrinterDriver);
}

```

## disassembly

```asm
0x18000b7ec  push    rbp
0x18000b7ee  push    rbx
0x18000b7ef  push    rsi
0x18000b7f0  push    rdi
0x18000b7f1  push    r12
0x18000b7f3  push    r13
0x18000b7f5  push    r14
0x18000b7f7  push    r15
0x18000b7f9  lea     rbp, [rsp-718h]
0x18000b801  sub     rsp, 818h
0x18000b808  mov     rax, cs:__security_cookie
0x18000b80f  xor     rax, rsp
0x18000b812  mov     [rbp+750h+var_50], rax
0x18000b819  mov     rax, [rbp+750h+arg_48]
0x18000b820  mov     rdi, rdx
0x18000b823  mov     r12, [rbp+750h+pPrinterName]
0x18000b82a  xor     edx, edx; Val
0x18000b82c  mov     r15, [rbp+750h+arg_30]
0x18000b833  mov     [rbp+750h+Owner], r8
0x18000b837  mov     r8d, 208h; Size
0x18000b83d  mov     qword ptr [rbp+750h+FileTime2.dwLowDateTime], rcx
0x18000b841  lea     rcx, [rbp+750h+var_260]; void *
0x18000b848  mov     [rbp+750h+phPrinter], r12
0x18000b84c  mov     [rbp+750h+var_788], rax
0x18000b850  movsxd  r13, r9d
0x18000b853  call    memset_0
0x18000b858  xor     r14d, r14d
0x18000b85b  mov     [rbp+750h+var_7C8], r14d
0x18000b85f  mov     [rbp+750h+var_798], r14d
0x18000b863  test    rdi, rdi
0x18000b866  jz      short loc_18000B879
0x18000b868  mov     ecx, r13d
0x18000b86b  call    ValidPlatform
0x18000b870  test    eax, eax
0x18000b872  jz      short loc_18000B879
0x18000b874  mov     ebx, r14d
0x18000b877  jmp     short loc_18000B887
0x18000b879  mov     ebx, 80070057h
0x18000b87e  test    rdi, rdi
0x18000b881  jz      loc_18000C220
0x18000b887  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x18000b88e  jz      short loc_18000B8AB
0x18000b890  mov     rax, [rdi+8]
0x18000b894  lea     rdx, DocPerf_Setup_InstallDriverFromCurrentInf_Start
0x18000b89b  mov     r8, [rdi]
0x18000b89e  mov     r9, r12
0x18000b8a1  mov     qword ptr [rsp+850h+ftDriverDate.dwLowDateTime], rax
0x18000b8a6  call    McTemplateU0zzz_EventWriteTransfer
0x18000b8ab  test    ebx, ebx
0x18000b8ad  js      loc_18000C1F7
0x18000b8b3  mov     ecx, dword ptr [rbp+750h+arg_38]
0x18000b8b9  mov     esi, ecx
0x18000b8bb  and     esi, 0FFFFFFF7h
0x18000b8be  test    cl, 20h
0x18000b8c1  cmovz   esi, ecx
0x18000b8c4  test    sil, 20h
0x18000b8c8  jz      short loc_18000B8D9
0x18000b8ca  mov     rcx, [rdi]; Str
0x18000b8cd  call    IsInfInDriverStore
0x18000b8d2  test    eax, eax
0x18000b8d4  jz      short loc_18000B8D9
0x18000b8d6  and     esi, 0FFFFFFDFh
0x18000b8d9  lea     r8, [rbp+750h+var_798]
0x18000b8dd  mov     edx, r13d
0x18000b8e0  mov     rcx, rdi
0x18000b8e3  call    InfFileIsNullPrinterDriver
0x18000b8e8  mov     ebx, eax
0x18000b8ea  test    eax, eax
0x18000b8ec  js      loc_18000C1F7
0x18000b8f2  cmp     [rbp+750h+var_798], r14d
0x18000b8f6  jz      short loc_18000B902
0x18000b8f8  mov     ebx, 80004005h
0x18000b8fd  jmp     loc_18000C1F7
0x18000b902  mov     rcx, [rdi]; unsigned __int16 *
0x18000b905  lea     r8, [rbp+750h+var_7C8]
0x18000b909  mov     edx, r13d
0x18000b90c  call    InfFileIsPackageAware
0x18000b911  mov     ebx, eax
0x18000b913  test    eax, eax
0x18000b915  js      loc_18000C1F7
0x18000b91b  mov     rcx, r12; pPrinterName
0x18000b91e  call    IsLonghornOrAbove
0x18000b923  test    eax, eax
0x18000b925  jz      loc_18000C061
0x18000b92b  test    sil, 20h
0x18000b92f  jnz     loc_18000C061
0x18000b935  mov     rcx, [rdi]
0x18000b938  call    IsNTPrintInf
0x18000b93d  test    eax, eax
0x18000b93f  jnz     loc_18000C061
0x18000b945  mov     eax, cs:MyPlatform
0x18000b94b  lea     rdx, [rsp+850h+var_7EC]
0x18000b950  cmp     eax, r13d
0x18000b953  mov     qword ptr [rbp+750h+FileTime1.dwLowDateTime], r14
0x18000b957  mov     r15d, r14d
0x18000b95a  mov     qword ptr [rbp+750h+FileTime2.dwLowDateTime], r14
0x18000b95e  setz    r15b
0x18000b962  mov     [rbp+750h+var_7C0], r14
0x18000b966  mov     rcx, r12
0x18000b969  mov     dword ptr [rsp+850h+var_7EC+4], r15d
0x18000b96e  mov     dword ptr [rsp+850h+var_7EC], eax
0x18000b972  mov     [rbp+750h+hMem], r14
0x18000b976  mov     [rsp+850h+var_7F0], r14d
0x18000b97b  mov     qword ptr [rsp+850h+var_7E0], r14
0x18000b980  call    GetServerPlatform
0x18000b985  xor     ecx, ecx
0x18000b987  mov     ebx, eax
0x18000b989  test    eax, eax
0x18000b98b  js      loc_18000C019
0x18000b991  cmp     dword ptr [rsp+850h+var_7EC], r13d
0x18000b996  setz    r14b
0x18000b99a  cmp     [rbp+750h+var_7C8], ecx
0x18000b99d  jz      short loc_18000B9C8
0x18000b99f  mov     rcx, [rdi]; unsigned __int16 *
0x18000b9a2  lea     rax, [rbp+750h+var_7C0]
0x18000b9a6  mov     [rsp+850h+var_828], rax; unsigned __int64 *
0x18000b9ab  lea     r9, [rsp+850h+var_7E0]
0x18000b9b0  lea     rax, [rbp+750h+FileTime1]
0x18000b9b4  mov     edx, r13d
0x18000b9b7  lea     r8, [rsp+850h+var_7F0]
0x18000b9bc  mov     qword ptr [rsp+850h+ftDriverDate.dwLowDateTime], rax; struct _FILETIME *
0x18000b9c1  call    ObtainPackageInfInfo
0x18000b9c6  jmp     short loc_18000BA47
0x18000b9c8  test    r14d, r14d
0x18000b9cb  jnz     loc_18000BA53
0x18000b9d1  mov     r9, [rdi+10h]
0x18000b9d5  lea     rax, [rbp+750h+hMem]
0x18000b9d9  mov     r8, [rdi]
0x18000b9dc  mov     edx, r13d
0x18000b9df  mov     rcx, r12; lpString1
0x18000b9e2  mov     qword ptr [rsp+850h+ftDriverDate.dwLowDateTime], rax; __int64
0x18000b9e7  call    DoesDriverUseIncludeNeeds
0x18000b9ec  xor     ecx, ecx
0x18000b9ee  mov     ebx, eax
0x18000b9f0  test    eax, eax
0x18000b9f2  js      loc_18000C014
0x18000b9f8  cmp     [rbp+750h+hMem], rcx
0x18000b9fc  jz      short loc_18000BA53
0x18000b9fe  xor     edx, edx; Val
0x18000ba00  lea     r8d, [r14+50h]; Size
0x18000ba04  lea     rcx, [rbp+750h+sz]; void *
0x18000ba0b  call    memset_0
0x18000ba10  lea     r8, aD20ea372Dd3549_0; "{D20EA372-DD35-4950-9ED8-A6335AFE79F0}"
0x18000ba17  lea     edx, [r14+27h]; unsigned __int64
0x18000ba1b  lea     rcx, [rbp+750h+sz]; unsigned __int16 *
0x18000ba22  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ba27  mov     ebx, eax
0x18000ba29  test    eax, eax
0x18000ba2b  js      loc_18000C014
0x18000ba31  lea     r8, [rsp+850h+var_7E0]
0x18000ba36  lea     rdx, [rsp+850h+var_7F0]
0x18000ba3b  lea     rcx, [rbp+750h+sz]; lpsz
0x18000ba42  call    CovertGuidMultiSzToArray
0x18000ba47  xor     ecx, ecx
0x18000ba49  mov     ebx, eax
0x18000ba4b  test    eax, eax
0x18000ba4d  js      loc_18000C014
0x18000ba53  mov     dword ptr [rsp+850h+var_7EC], ecx
0x18000ba57  cmp     [rbp+750h+hMem], rcx
0x18000ba5b  jnz     loc_18000BBCB
0x18000ba61  mov     eax, [rsp+850h+var_7F0]
0x18000ba65  cmp     [rbp+750h+var_7C8], ecx
0x18000ba68  jz      loc_18000C006
0x18000ba6e  test    eax, eax
0x18000ba70  jz      loc_18000C006
0x18000ba76  mov     r15, qword ptr [rsp+850h+var_7E0]
0x18000ba7b  mov     ebx, ecx
0x18000ba7d  cmp     ebx, eax
0x18000ba7f  jnb     loc_18000C006
0x18000ba85  mov     ecx, ebx
0x18000ba87  shl     rcx, 4
0x18000ba8b  add     rcx, r15
0x18000ba8e  call    IsInboxCorePrinterDriverGUID
0x18000ba93  xor     ecx, ecx
0x18000ba95  test    eax, eax
0x18000ba97  jnz     short loc_18000BAA1
0x18000ba99  mov     eax, [rsp+850h+var_7F0]
0x18000ba9d  inc     ebx
0x18000ba9f  jmp     short loc_18000BA7D
0x18000baa1  test    r14d, r14d
0x18000baa4  jz      loc_18000BB7C
0x18000baaa  lea     rdx, [rbp+750h+FileTime2]; lpFileTime2
0x18000baae  lea     rcx, [rbp+750h+FileTime1]; lpFileTime1
0x18000bab2  call    cs:__imp_CompareFileTime
0x18000bab8  xor     ecx, ecx
0x18000baba  test    eax, eax
0x18000babc  mov     rax, [rbp+750h+var_7C0]
0x18000bac0  jnz     loc_18000BB80
0x18000bac6  test    rax, rax
0x18000bac9  jnz     loc_18000BB80
0x18000bacf  mov     r14, qword ptr [rsp+850h+var_7E0]
0x18000bad4  mov     eax, [rsp+850h+var_7F0]
0x18000bad8  cmp     [rbp+750h+var_7C8], ecx
0x18000badb  jz      short loc_18000BB0A
0x18000badd  test    eax, eax
0x18000badf  jz      short loc_18000BB0A
0x18000bae1  mov     r8, [rbp+750h+Owner]
0x18000bae5  mov     r9d, r13d
0x18000bae8  mov     rdx, [rdi]
0x18000baeb  mov     rcx, r12
0x18000baee  mov     [rsp+850h+var_820], r14
0x18000baf3  mov     dword ptr [rsp+850h+var_828], eax
0x18000baf7  mov     [rsp+850h+ftDriverDate.dwLowDateTime], esi
0x18000bafb  call    ?CheckAndUploadCommonDriverDependentPackages@@YAJPEBG0PEAUHWND__@@W4PLATFORM@@KKPEAU_GUID@@@Z; CheckAndUploadCommonDriverDependentPackages(ushort const *,ushort const *,HWND__ *,PLATFORM,ulong,ulong,_GUID *)
0x18000bb00  mov     ebx, eax
0x18000bb02  test    eax, eax
0x18000bb04  js      loc_18000C019
0x18000bb0a  mov     r8, [rbp+750h+Owner]
0x18000bb0e  lea     rax, [rsp+850h+var_7EC+4]
0x18000bb13  mov     rcx, [rdi]
0x18000bb16  mov     r9d, r13d
0x18000bb19  mov     [rsp+850h+var_820], rax
0x18000bb1e  mov     rdx, r12
0x18000bb21  lea     rax, [rbp+750h+var_260]
0x18000bb28  mov     dword ptr [rsp+850h+var_7EC+4], 104h
0x18000bb30  mov     [rsp+850h+var_828], rax
0x18000bb35  mov     [rsp+850h+ftDriverDate.dwLowDateTime], esi
0x18000bb39  call    ?UploadPrinterDriverHelper@@YAJPEAGPEBGPEAUHWND__@@W4PLATFORM@@K0PEAK@Z; UploadPrinterDriverHelper(ushort *,ushort const *,HWND__ *,PLATFORM,ulong,ushort *,ulong *)
0x18000bb3e  mov     ebx, eax
0x18000bb40  test    eax, eax
0x18000bb42  js      loc_18000C019
0x18000bb48  mov     rax, [rbp+750h+var_788]
0x18000bb4c  lea     rdx, [rbp+750h+var_260]; unsigned __int16 *
0x18000bb53  mov     r8, [rdi+8]; unsigned __int16 *
0x18000bb57  mov     r9d, r13d
0x18000bb5a  mov     [rsp+850h+var_820], rax; __int64
0x18000bb5f  mov     rcx, r12; unsigned __int16 *
0x18000bb62  mov     eax, [rbp+750h+arg_40]
0x18000bb68  mov     dword ptr [rsp+850h+var_828], eax; int
0x18000bb6c  mov     [rsp+850h+ftDriverDate.dwLowDateTime], esi; int
0x18000bb70  call    InstallPrinterDriverFromInfPackage
0x18000bb75  mov     ebx, eax
0x18000bb77  jmp     loc_18000C019
0x18000bb7c  mov     rax, [rbp+750h+var_7C0]
0x18000bb80  mov     r14, qword ptr [rsp+850h+var_7E0]
0x18000bb85  lea     rcx, [rsp+850h+var_7EC]
0x18000bb8a  mov     r8d, [rsp+850h+var_7F0]; int
0x18000bb8f  mov     r9, r14; int
0x18000bb92  mov     [rsp+850h+var_820], rcx; __int64
0x18000bb97  mov     edx, r13d; int
0x18000bb9a  mov     [rsp+850h+var_828], rax; DWORDLONG
0x18000bb9f  mov     rcx, r12; int
0x18000bba2  mov     rax, qword ptr [rbp+750h+FileTime1.dwLowDateTime]
0x18000bba6  mov     qword ptr [rsp+850h+ftDriverDate.dwLowDateTime], rax; ftDriverDate
0x18000bbab  call    AllInboxCoreDriversInstalled
0x18000bbb0  xor     ecx, ecx
0x18000bbb2  mov     ebx, eax
0x18000bbb4  test    eax, eax
0x18000bbb6  js      loc_18000C019
0x18000bbbc  cmp     dword ptr [rsp+850h+var_7EC], ecx
0x18000bbc0  jnz     loc_18000BAD4
0x18000bbc6  mov     r15d, dword ptr [rsp+850h+var_7EC+4]
0x18000bbcb  mov     r12, rcx
0x18000bbce  mov     [rbp+750h+var_7B8], rcx
0x18000bbd2  mov     rcx, [rbp+750h+phPrinter]; lpString1
0x18000bbd6  call    IsLocalMachine
0x18000bbdb  mov     [rsp+850h+var_7D8], eax
0x18000bbdf  lea     rcx, [rbp+750h+FindFileData]; void *
0x18000bbe6  xor     eax, eax
0x18000bbe8  xor     edx, edx; Val
0x18000bbea  mov     r8d, 250h; Size
0x18000bbf0  mov     dword ptr [rsp+850h+var_7EC], eax
0x18000bbf4  mov     r14d, eax
0x18000bbf7  mov     dword ptr [rsp+850h+var_7EC+4], eax
0x18000bbfb  call    memset_0
0x18000bc00  xor     ecx, ecx
0x18000bc02  test    r15d, r15d
0x18000bc05  jnz     loc_18000BD97
0x18000bc0b  cmp     [rdi+1B0h], rcx
0x18000bc12  jnz     loc_18000BD97
0x18000bc18  lea     r15d, [rcx+1]
0x18000bc1c  test    ebx, ebx
0x18000bc1e  js      loc_18000BFE4
0x18000bc24  mov     edx, [rsp+850h+var_7D8]
0x18000bc28  test    r14d, r14d
0x18000bc2b  jnz     loc_18000BD81
0x18000bc31  mov     r9, qword ptr [rbp+750h+FileTime1.dwLowDateTime]
0x18000bc35  lea     rax, [rsp+850h+var_7EC]
0x18000bc3a  xor     r8d, r8d
0x18000bc3d  lea     rcx, [rbp+750h+var_7B8]
0x18000bc41  test    edx, edx
0x18000bc43  mov     edx, [rsp+850h+var_7F0]
0x18000bc47  cmovnz  rcx, r8
0x18000bc4b  mov     r8, qword ptr [rsp+850h+var_7E0]
0x18000bc50  mov     [rsp+850h+var_818], rcx
0x18000bc55  mov     ecx, r13d
0x18000bc58  mov     [rsp+850h+var_820], rax
0x18000bc5d  mov     rax, [rbp+750h+hMem]
0x18000bc61  mov     [rsp+850h+var_828], rax
0x18000bc66  mov     rax, [rbp+750h+var_7C0]
0x18000bc6a  mov     qword ptr [rsp+850h+ftDriverDate.dwLowDateTime], rax
0x18000bc6f  call    AllInboxCoreDriversInLocalDriverStore
0x18000bc74  xor     ecx, ecx
0x18000bc76  mov     ebx, eax
0x18000bc78  test    eax, eax
0x18000bc7a  js      loc_18000BEAD
0x18000bc80  mov     r14d, dword ptr [rsp+850h+var_7EC]
0x18000bc85  mov     r12, [rbp+750h+var_7B8]
0x18000bc89  test    r14d, r14d
0x18000bc8c  jz      short loc_18000BC9F
  ... truncated ...
```
