# NPackageInstallLocalspl::TDriverStore::TMissingDriver::CheckForDriverInDriverStoreAndInPCC(ushort *,_DRIVER_INFO_8W *)

- ea: `0x1800ac384`
- end: `0x1800ac9cd`
- name: `?CheckForDriverInDriverStoreAndInPCC@TMissingDriver@TDriverStore@NPackageInstallLocalspl@@AEAAJPEAGPEAU_DRIVER_INFO_8W@@@Z`
- size: `1609`
- prototype: `int(NPackageInstallLocalspl::TDriverStore::TMissingDriver *__hidden this, unsigned __int16 *, struct _DRIVER_INFO_8W *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, installer_update`

## callers

- `0x1800b8fd8`

## callees

- `0x18000c380`
- `0x18000d944`
- `0x180011f00`
- `0x180015e28`
- `0x18002ff50`
- `0x1800306c4`
- `0x18003e984`
- `0x18003ea2c`
- `0x180046650`
- `0x180047330`
- `0x180071fb0`
- `0x1800ac384`
- `0x1800adb34`
- `0x1800b7b64`
- `0x1800ca284`
- `0x1800cb798`
- `0x1800cfd50`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800ac6b2`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800ac6cb`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800ac6b2`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800ac6cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac534`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac854`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac87b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac534`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac854`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac87b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ac981`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ac981`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800ac7b0`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800ac7b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800ac456`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800ac456`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800ac400`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800ac400`

## string_xrefs

- `0x1800ac3f9`: `ntprint.dll`
- `0x1800ac871`: `PSetupDriverStoreAddDriverPackage`
- `0x1800ac98e`: `Check for driver failed for path '%ws'`
- `0x1800ac4d4`: `NPackageInstallLocalspl::TDriverStore::TMissingDriver::CheckForDriverInDriverStoreAndInPCC`
- `0x1800ac50a`: `NPackageInstallLocalspl::TDriverStore::TMissingDriver::CheckForDriverInDriverStoreAndInPCC`
- `0x1800ac728`: `NPackageInstallLocalspl::TDriverStore::TMissingDriver::CheckForDriverInDriverStoreAndInPCC`
- `0x1800ac75a`: `NPackageInstallLocalspl::TDriverStore::TMissingDriver::CheckForDriverInDriverStoreAndInPCC`
- `0x1800ac995`: `NPackageInstallLocalspl::TDriverStore::TMissingDriver::CheckForDriverInDriverStoreAndInPCC`

## pseudocode

```c
__int64 __fastcall NPackageInstallLocalspl::TDriverStore::TMissingDriver::CheckForDriverInDriverStoreAndInPCC(
        NPackageInstallLocalspl::TDriverStore::TMissingDriver *this,
        unsigned __int16 *a2,
        struct _DRIVER_INFO_8W *a3)
{
  struct _DRIVER_INFO_8W *v3; // r15
  int LastErrorAsFailHRNoBreak; // ebx
  unsigned __int16 *v7; // rsi
  NCoreLibrary *v8; // rcx
  HMODULE v9; // r14
  NCoreLibrary *v10; // rcx
  UINT SystemWindowsDirectoryW; // edi
  int v12; // edi
  NCoreLibrary *v13; // rcx
  FARPROC ProcAddress; // rsi
  __int64 v15; // rax
  __int64 v16; // rcx
  NCoreLibrary *v17; // rcx
  __int64 v18; // rax
  wchar_t *v19; // rax
  NCoreLibrary *v20; // rcx
  wchar_t *v21; // rsi
  wchar_t *v22; // rax
  NCoreLibrary *v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  NCoreLibrary *v26; // rcx
  const unsigned __int16 *v27; // r8
  unsigned int v28; // r10d
  NCoreLibrary *v29; // rcx
  FARPROC v30; // rsi
  NCoreLibrary *v31; // rcx
  FARPROC v32; // r14
  unsigned int v33; // r15d
  unsigned __int16 *v34; // rdx
  struct _DRIVER_INFO_8W *v35; // r14
  unsigned __int16 *v37; // [rsp+20h] [rbp-E0h]
  _WORD v38[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v39; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 *FileName; // [rsp+48h] [rbp-B8h] BYREF
  HMODULE LibraryW; // [rsp+50h] [rbp-B0h]
  struct _DRIVER_INFO_8W *v42; // [rsp+58h] [rbp-A8h]
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v44[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR PathName[264]; // [rsp+480h] [rbp+380h] BYREF
  unsigned __int16 v46[264]; // [rsp+690h] [rbp+590h] BYREF

  v42 = a3;
  v38[0] = 0;
  v3 = a3;
  if ( !a2 || (unsigned int)FileExists(a2) || (FileName = (unsigned __int16 *)FindFileName(a2), (v7 = FileName) == 0) )
  {
    LastErrorAsFailHRNoBreak = -2147024809;
LABEL_69:
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "NPackageInstallLocalspl::TDriverStore::TMissingDriver::CheckForDriverInDriverStoreAndInPCC",
      L"Check for driver failed for path '%ws'",
      a2);
    return (unsigned int)LastErrorAsFailHRNoBreak;
  }
  LibraryW = LoadLibraryW(L"ntprint.dll");
  v9 = LibraryW;
  if ( !LibraryW )
  {
    LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v8);
    if ( LastErrorAsFailHRNoBreak < 0 )
      goto LABEL_69;
  }
  LastErrorAsFailHRNoBreak = GetProcessorArchitectureFromEnvironmentString(*((_QWORD *)this + 5), v38);
  if ( LastErrorAsFailHRNoBreak >= 0 )
  {
    memset_0(Buffer, 0, 0x208u);
    SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x104u);
    if ( SystemWindowsDirectoryW > 1
      || (LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v10), LastErrorAsFailHRNoBreak >= 0) )
    {
      if ( Buffer[SystemWindowsDirectoryW - 1] == 92
        || (LastErrorAsFailHRNoBreak = StringCchCatW(Buffer, 0x104u, L"\\"), LastErrorAsFailHRNoBreak >= 0) )
      {
        LastErrorAsFailHRNoBreak = StringCchCatW(Buffer, 0x104u, L"inf\\");
        if ( LastErrorAsFailHRNoBreak >= 0 )
          LastErrorAsFailHRNoBreak = StringCchCatW(Buffer, 0x104u, v7);
      }
    }
    LocalSpoolerTelemetry::WriteDbgTraceInfo(
      "NPackageInstallLocalspl::TDriverStore::TMissingDriver::CheckForDriverInDriverStoreAndInPCC",
      L"Looking for an INF in %ws",
      Buffer);
    if ( LastErrorAsFailHRNoBreak >= 0 )
    {
      v12 = 0;
      if ( (unsigned int)FileExists(Buffer) )
      {
        LocalSpoolerTelemetry::WriteDbgTraceInfo(
          "NPackageInstallLocalspl::TDriverStore::TMissingDriver::CheckForDriverInDriverStoreAndInPCC",
          L"Found an INF in %ws",
          Buffer);
        memset_0(v44, 0, 0x208u);
        ProcAddress = GetProcAddress(v9, "PSetupGetInfDriverStoreLocation");
        if ( !ProcAddress )
        {
          LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v13);
          if ( LastErrorAsFailHRNoBreak < 0 )
            goto LABEL_66;
        }
        LastErrorAsFailHRNoBreak = ((__int64 (__fastcall *)(_QWORD, WCHAR *, unsigned __int16 *, __int64))ProcAddress)(
                                     v38[0],
                                     Buffer,
                                     v44,
                                     260);
        if ( LastErrorAsFailHRNoBreak < 0 )
          goto LABEL_66;
        if ( v3 )
        {
          LODWORD(v37) = 0;
          LastErrorAsFailHRNoBreak = NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage(
                                       0,
                                       v44,
                                       v3->pName,
                                       *((unsigned __int16 **)this + 5),
                                       v37,
                                       *((struct _SETUP_CONTEXT **)this + 6));
          if ( LastErrorAsFailHRNoBreak < 0 )
            LastErrorAsFailHRNoBreak = 0;
          else
            v12 = 1;
        }
      }
      if ( v12 )
        goto LABEL_64;
      v39 = 0;
      memset_0(Buffer, 0, 0x208u);
      memset_0(v46, 0, 0x208u);
      v15 = *((_QWORD *)this + 6);
      LODWORD(v16) = 0;
      if ( (struct _INISPOOLER *)v15 != pLocalIniSpooler )
        v16 = *(_QWORD *)(v15 + 24);
      if ( (unsigned int)SplGetPrinterDriverDirectory(
                           v16,
                           *((_QWORD *)this + 5),
                           1,
                           (unsigned int)Buffer,
                           8,
                           (char)&v39,
                           *((_QWORD *)this + 6))
        || (LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v17), LastErrorAsFailHRNoBreak >= 0) )
      {
        v18 = -1;
        do
          ++v18;
        while ( Buffer[v18] );
        if ( Buffer[v18 - 1] == 92
          || (LastErrorAsFailHRNoBreak = StringCchCatW(Buffer, 0x104u, L"\\"), LastErrorAsFailHRNoBreak >= 0) )
        {
          LastErrorAsFailHRNoBreak = StringCchCatW(Buffer, 0x104u, L"PCC");
          if ( LastErrorAsFailHRNoBreak >= 0 )
          {
            LastErrorAsFailHRNoBreak = StringCchCatW(Buffer, 0x104u, L"\\");
            if ( LastErrorAsFailHRNoBreak >= 0 )
            {
              v19 = wcsrchr(a2, 0x5Cu);
              v21 = v19;
              if ( v19 )
              {
                *v19 = 0;
                v22 = wcsrchr(a2, 0x5Cu);
                v24 = v22 ? StringCchCatW(Buffer, 0x104u, v22 + 1) : NCoreLibrary::GetLastErrorAsFailHRNoBreak(v23);
                *v21 = 92;
              }
              else
              {
                v24 = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v20);
              }
              LastErrorAsFailHRNoBreak = v24;
              if ( v24 >= 0 )
                LastErrorAsFailHRNoBreak = StringCchCatW(Buffer, 0x104u, L".cab");
            }
          }
        }
      }
      LocalSpoolerTelemetry::WriteDbgTraceInfo(
        "NPackageInstallLocalspl::TDriverStore::TMissingDriver::CheckForDriverInDriverStoreAndInPCC",
        L"Looking for a CAB in %ws",
        Buffer);
      if ( LastErrorAsFailHRNoBreak >= 0 )
      {
        if ( !(unsigned int)FileExists(Buffer) )
          goto LABEL_64;
        LocalSpoolerTelemetry::WriteDbgTraceInfo(
          "NPackageInstallLocalspl::TDriverStore::TMissingDriver::CheckForDriverInDriverStoreAndInPCC",
          L"Found a CAB in %ws",
          Buffer);
        memset_0(PathName, 0, 0x208u);
        memset_0(v44, 0, 0x208u);
        LastErrorAsFailHRNoBreak = GetUniqueTempDirInPrintShare(v25, *((_QWORD *)this + 5), PathName);
        if ( LastErrorAsFailHRNoBreak >= 0 )
        {
          if ( CreateDirectoryW(PathName, 0)
            || (LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v26), LastErrorAsFailHRNoBreak >= 0) )
          {
            LastErrorAsFailHRNoBreak = NCabbingLibrary::LegacyCabUnpack((NCabbingLibrary *)Buffer, PathName, v27);
            if ( LastErrorAsFailHRNoBreak >= 0 )
            {
              LastErrorAsFailHRNoBreak = StringCchCopyW(v44, 0x104u, PathName);
              if ( LastErrorAsFailHRNoBreak >= 0 )
              {
                LastErrorAsFailHRNoBreak = StringCchCatW(v44, v28, L"\\");
                if ( LastErrorAsFailHRNoBreak >= 0 )
                {
                  LastErrorAsFailHRNoBreak = StringCchCatW(v44, 0x104u, FileName);
                  if ( LastErrorAsFailHRNoBreak >= 0 )
                  {
                    v30 = GetProcAddress(v9, "PSetupSetNonInteractiveMode");
                    if ( v30
                      || (LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v29),
                          LastErrorAsFailHRNoBreak >= 0) )
                    {
                      v32 = GetProcAddress(v9, "PSetupDriverStoreAddDriverPackage");
                      if ( v32
                        || (LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v31),
                            LastErrorAsFailHRNoBreak >= 0) )
                      {
                        v33 = ((__int64 (__fastcall *)(__int64))v30)(1);
                        LODWORD(FileName) = 260;
                        LastErrorAsFailHRNoBreak = ((__int64 (__fastcall *)(unsigned __int16 *, _QWORD, unsigned __int16 *, unsigned __int16 **))v32)(
                                                     v44,
                                                     v38[0],
                                                     v46,
                                                     &FileName);
                        if ( LastErrorAsFailHRNoBreak >= 0 )
                        {
                          v35 = v42;
                          if ( v42 )
                          {
                            LODWORD(v37) = (unsigned int)NPackageInstallLocalspl::IsClassDriverRemoved(
                                                           (NPackageInstallLocalspl *)a2,
                                                           v34) != 0
                                         ? 0x8000000
                                         : 0;
                            LastErrorAsFailHRNoBreak = NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage(
                                                         0,
                                                         v46,
                                                         v35->pName,
                                                         *((unsigned __int16 **)this + 5),
                                                         v37,
                                                         *((struct _SETUP_CONTEXT **)this + 6));
                            if ( LastErrorAsFailHRNoBreak < 0 )
                              LastErrorAsFailHRNoBreak = 0;
                            else
                              v12 = 1;
                          }
                        }
                        ((void (__fastcall *)(_QWORD))v30)(v33);
                        v3 = v42;
                      }
                      v9 = LibraryW;
                    }
                  }
                }
              }
            }
            RecursivelyDeleteDirectory(PathName, 5);
            if ( LastErrorAsFailHRNoBreak >= 0 )
            {
LABEL_64:
              if ( v3 && !v12 )
              {
                LODWORD(v37) = 0;
                LastErrorAsFailHRNoBreak = NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage(
                                             0,
                                             0,
                                             v3->pName,
                                             *((unsigned __int16 **)this + 5),
                                             v37,
                                             *((struct _SETUP_CONTEXT **)this + 6));
              }
            }
          }
        }
      }
    }
  }
LABEL_66:
  if ( v9 )
    FreeLibrary(v9);
  if ( LastErrorAsFailHRNoBreak < 0 )
    goto LABEL_69;
  return (unsigned int)LastErrorAsFailHRNoBreak;
}

```

## disassembly

```asm
0x1800ac384  mov     [rsp-8+arg_18], rbx
0x1800ac389  push    rbp
0x1800ac38a  push    rsi
0x1800ac38b  push    rdi
0x1800ac38c  push    r12
0x1800ac38e  push    r13
0x1800ac390  push    r14
0x1800ac392  push    r15
0x1800ac394  lea     rbp, [rsp-7B0h]
0x1800ac39c  sub     rsp, 8B0h
0x1800ac3a3  mov     rax, cs:__security_cookie
0x1800ac3aa  xor     rax, rsp
0x1800ac3ad  mov     [rbp+7E0h+var_40], rax
0x1800ac3b4  xor     edi, edi
0x1800ac3b6  mov     [rsp+8E0h+var_888], r8
0x1800ac3bb  mov     [rsp+8E0h+var_8A0], di
0x1800ac3c0  mov     r15, r8
0x1800ac3c3  mov     r12, rdx
0x1800ac3c6  mov     r13, rcx
0x1800ac3c9  test    rdx, rdx
0x1800ac3cc  jnz     short loc_1800AC3D8
0x1800ac3ce  mov     ebx, 80070057h
0x1800ac3d3  jmp     loc_1800AC98B
0x1800ac3d8  mov     rcx, r12
0x1800ac3db  call    FileExists
0x1800ac3e0  test    eax, eax
0x1800ac3e2  jnz     short loc_1800AC3CE
0x1800ac3e4  mov     rcx, r12
0x1800ac3e7  call    FindFileName
0x1800ac3ec  mov     [rsp+8E0h+var_898], rax
0x1800ac3f1  mov     rsi, rax
0x1800ac3f4  test    rax, rax
0x1800ac3f7  jz      short loc_1800AC3CE
0x1800ac3f9  lea     rcx, aNtprintDll; "ntprint.dll"
0x1800ac400  call    cs:__imp_LoadLibraryW
0x1800ac406  mov     [rsp+8E0h+var_890], rax
0x1800ac40b  mov     r14, rax
0x1800ac40e  test    rax, rax
0x1800ac411  jnz     short loc_1800AC422
0x1800ac413  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800ac418  mov     ebx, eax
0x1800ac41a  test    eax, eax
0x1800ac41c  js      loc_1800AC98B
0x1800ac422  mov     rcx, [r13+28h]
0x1800ac426  lea     rdx, [rsp+8E0h+var_8A0]
0x1800ac42b  call    GetProcessorArchitectureFromEnvironmentString
0x1800ac430  mov     ebx, eax
0x1800ac432  test    eax, eax
0x1800ac434  js      loc_1800AC979
0x1800ac43a  xor     edx, edx; Val
0x1800ac43c  lea     rcx, [rsp+8E0h+Buffer]; void *
0x1800ac441  mov     r8d, 208h; Size
0x1800ac447  call    memset_0
0x1800ac44c  mov     edx, 104h; uSize
0x1800ac451  lea     rcx, [rsp+8E0h+Buffer]; lpBuffer
0x1800ac456  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800ac45c  mov     edi, eax
0x1800ac45e  cmp     eax, 1
0x1800ac461  ja      short loc_1800AC46E
0x1800ac463  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800ac468  mov     ebx, eax
0x1800ac46a  test    eax, eax
0x1800ac46c  js      short loc_1800AC4C8
0x1800ac46e  lea     ecx, [rdi-1]
0x1800ac471  mov     eax, 5Ch ; '\'
0x1800ac476  cmp     [rsp+rcx*2+8E0h+Buffer], ax
0x1800ac47b  jz      short loc_1800AC499
0x1800ac47d  lea     r8, SubBlock; "\\"
0x1800ac484  mov     edx, 104h; unsigned __int64
0x1800ac489  lea     rcx, [rsp+8E0h+Buffer]; unsigned __int16 *
0x1800ac48e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ac493  mov     ebx, eax
0x1800ac495  test    eax, eax
0x1800ac497  js      short loc_1800AC4C8
0x1800ac499  mov     edi, 104h
0x1800ac49e  lea     r8, aInf; "inf\\"
0x1800ac4a5  mov     edx, edi; unsigned __int64
0x1800ac4a7  lea     rcx, [rsp+8E0h+Buffer]; unsigned __int16 *
0x1800ac4ac  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ac4b1  mov     ebx, eax
0x1800ac4b3  test    eax, eax
0x1800ac4b5  js      short loc_1800AC4C8
0x1800ac4b7  mov     r8, rsi; unsigned __int16 *
0x1800ac4ba  lea     rcx, [rsp+8E0h+Buffer]; unsigned __int16 *
0x1800ac4bf  mov     edx, edi; unsigned __int64
0x1800ac4c1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ac4c6  mov     ebx, eax
0x1800ac4c8  lea     r8, [rsp+8E0h+Buffer]
0x1800ac4cd  lea     rdx, aLookingForAnIn; "Looking for an INF in %ws"
0x1800ac4d4  lea     rcx, aNpackageinstal_20; "NPackageInstallLocalspl::TDriverStore::"...
0x1800ac4db  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800ac4e0  xor     esi, esi
0x1800ac4e2  test    ebx, ebx
0x1800ac4e4  js      loc_1800AC979
0x1800ac4ea  lea     rcx, [rsp+8E0h+Buffer]
0x1800ac4ef  mov     edi, esi
0x1800ac4f1  call    FileExists
0x1800ac4f6  test    eax, eax
0x1800ac4f8  jz      loc_1800AC5B1
0x1800ac4fe  lea     r8, [rsp+8E0h+Buffer]
0x1800ac503  lea     rdx, aFoundAnInfInWs; "Found an INF in %ws"
0x1800ac50a  lea     rcx, aNpackageinstal_20; "NPackageInstallLocalspl::TDriverStore::"...
0x1800ac511  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800ac516  xor     edx, edx; Val
0x1800ac518  lea     rcx, [rbp+7E0h+var_670]; void *
0x1800ac51f  mov     r8d, 208h; Size
0x1800ac525  call    memset_0
0x1800ac52a  lea     rdx, aPsetupgetinfdr; "PSetupGetInfDriverStoreLocation"
0x1800ac531  mov     rcx, r14; hModule
0x1800ac534  call    cs:__imp_GetProcAddress
0x1800ac53a  mov     rsi, rax
0x1800ac53d  test    rax, rax
0x1800ac540  jnz     short loc_1800AC551
0x1800ac542  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800ac547  mov     ebx, eax
0x1800ac549  test    eax, eax
0x1800ac54b  js      loc_1800AC979
0x1800ac551  movzx   ecx, [rsp+8E0h+var_8A0]
0x1800ac556  lea     r8, [rbp+7E0h+var_670]
0x1800ac55d  mov     r9d, 104h
0x1800ac563  lea     rdx, [rsp+8E0h+Buffer]
0x1800ac568  mov     rax, rsi
0x1800ac56b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac570  xor     esi, esi
0x1800ac572  mov     ebx, eax
0x1800ac574  test    eax, eax
0x1800ac576  js      loc_1800AC979
0x1800ac57c  test    r15, r15
0x1800ac57f  jz      short loc_1800AC5B1
0x1800ac581  mov     rax, [r13+30h]
0x1800ac585  lea     rdx, [rbp+7E0h+var_670]; unsigned __int16 *
0x1800ac58c  mov     r9, [r13+28h]; unsigned __int16 *
0x1800ac590  xor     ecx, ecx; this
0x1800ac592  mov     r8, [r15+8]; unsigned __int16 *
0x1800ac596  mov     qword ptr [rsp+8E0h+var_8B8], rax; unsigned int
0x1800ac59b  mov     dword ptr [rsp+8E0h+var_8C0], esi; unsigned __int16 *
0x1800ac59f  call    ?InternalInstallPrinterDriverFromPackage@NPackageInstallLocalspl@@YAJPEBG000KPEAU_INISPOOLER@@@Z; NPackageInstallLocalspl::InternalInstallPrinterDriverFromPackage(ushort const *,ushort const *,ushort const *,ushort const *,ulong,_INISPOOLER *)
0x1800ac5a4  mov     ebx, eax
0x1800ac5a6  test    eax, eax
0x1800ac5a8  js      short loc_1800AC5AF
0x1800ac5aa  lea     edi, [rsi+1]
0x1800ac5ad  jmp     short loc_1800AC5B1
0x1800ac5af  mov     ebx, esi
0x1800ac5b1  test    edi, edi
0x1800ac5b3  jnz     loc_1800AC950
0x1800ac5b9  mov     ebx, 208h
0x1800ac5be  mov     [rsp+8E0h+var_89C], esi
0x1800ac5c2  mov     r8d, ebx; Size
0x1800ac5c5  lea     rcx, [rsp+8E0h+Buffer]; void *
0x1800ac5ca  xor     edx, edx; Val
0x1800ac5cc  call    memset_0
0x1800ac5d1  mov     r8d, ebx; Size
0x1800ac5d4  lea     rcx, [rbp+7E0h+var_250]; void *
0x1800ac5db  xor     edx, edx; Val
0x1800ac5dd  call    memset_0
0x1800ac5e2  mov     rax, [r13+30h]
0x1800ac5e6  mov     rcx, rsi
0x1800ac5e9  cmp     rax, cs:pLocalIniSpooler
0x1800ac5f0  jz      short loc_1800AC5F6
0x1800ac5f2  mov     rcx, [rax+18h]
0x1800ac5f6  mov     rdx, [r13+28h]
0x1800ac5fa  lea     r9, [rsp+8E0h+Buffer]
0x1800ac5ff  mov     [rsp+8E0h+var_8B0], rax; struct _INISPOOLER *
0x1800ac604  mov     r8d, 1
0x1800ac60a  lea     rax, [rsp+8E0h+var_89C]
0x1800ac60f  mov     qword ptr [rsp+8E0h+var_8B8], rax
0x1800ac614  mov     dword ptr [rsp+8E0h+var_8C0], ebx
0x1800ac618  call    SplGetPrinterDriverDirectory
0x1800ac61d  test    eax, eax
0x1800ac61f  jnz     short loc_1800AC630
0x1800ac621  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800ac626  mov     ebx, eax
0x1800ac628  test    eax, eax
0x1800ac62a  js      loc_1800AC71C
0x1800ac630  lea     rcx, [rsp+8E0h+Buffer]
0x1800ac635  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ac639  inc     rax
0x1800ac63c  cmp     [rcx+rax*2], si
0x1800ac640  jnz     short loc_1800AC639
0x1800ac642  mov     ecx, 5Ch ; '\'
0x1800ac647  cmp     word ptr [rsp+rax*2+8E0h+var_888+6], cx
0x1800ac64c  jz      short loc_1800AC66E
0x1800ac64e  lea     r8, SubBlock; "\\"
0x1800ac655  mov     edx, 104h; unsigned __int64
0x1800ac65a  lea     rcx, [rsp+8E0h+Buffer]; unsigned __int16 *
0x1800ac65f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ac664  mov     ebx, eax
0x1800ac666  test    eax, eax
0x1800ac668  js      loc_1800AC71C
0x1800ac66e  lea     r8, aPcc; "PCC"
0x1800ac675  mov     edx, 104h; unsigned __int64
0x1800ac67a  lea     rcx, [rsp+8E0h+Buffer]; unsigned __int16 *
0x1800ac67f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ac684  mov     ebx, eax
0x1800ac686  test    eax, eax
0x1800ac688  js      loc_1800AC71C
0x1800ac68e  lea     r8, SubBlock; "\\"
0x1800ac695  mov     edx, 104h; unsigned __int64
0x1800ac69a  lea     rcx, [rsp+8E0h+Buffer]; unsigned __int16 *
0x1800ac69f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ac6a4  mov     ebx, eax
0x1800ac6a6  test    eax, eax
0x1800ac6a8  js      short loc_1800AC71C
0x1800ac6aa  mov     edx, 5Ch ; '\'; Ch
0x1800ac6af  mov     rcx, r12; Str
0x1800ac6b2  call    cs:__imp_wcsrchr
0x1800ac6b8  xor     ebx, ebx
0x1800ac6ba  mov     rsi, rax
0x1800ac6bd  test    rax, rax
0x1800ac6c0  jz      short loc_1800AC6F7
0x1800ac6c2  lea     edx, [rbx+5Ch]; Ch
0x1800ac6c5  mov     [rax], bx
0x1800ac6c8  mov     rcx, r12; Str
0x1800ac6cb  call    cs:__imp_wcsrchr
0x1800ac6d1  test    rax, rax
0x1800ac6d4  jz      short loc_1800AC6EB
0x1800ac6d6  lea     r8, [rax+2]; unsigned __int16 *
0x1800ac6da  mov     edx, 104h; unsigned __int64
0x1800ac6df  lea     rcx, [rsp+8E0h+Buffer]; unsigned __int16 *
0x1800ac6e4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ac6e9  jmp     short loc_1800AC6F0
0x1800ac6eb  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800ac6f0  mov     word ptr [rsi], 5Ch ; '\'
0x1800ac6f5  jmp     short loc_1800AC6FC
0x1800ac6f7  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800ac6fc  xor     esi, esi
0x1800ac6fe  mov     ebx, eax
0x1800ac700  test    eax, eax
0x1800ac702  js      short loc_1800AC71C
0x1800ac704  lea     r8, aCab; ".cab"
0x1800ac70b  mov     edx, 104h; unsigned __int64
0x1800ac710  lea     rcx, [rsp+8E0h+Buffer]; unsigned __int16 *
0x1800ac715  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ac71a  mov     ebx, eax
0x1800ac71c  lea     r8, [rsp+8E0h+Buffer]
0x1800ac721  lea     rdx, aLookingForACab; "Looking for a CAB in %ws"
0x1800ac728  lea     rcx, aNpackageinstal_20; "NPackageInstallLocalspl::TDriverStore::"...
0x1800ac72f  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800ac734  test    ebx, ebx
0x1800ac736  js      loc_1800AC979
0x1800ac73c  lea     rcx, [rsp+8E0h+Buffer]
0x1800ac741  call    FileExists
0x1800ac746  test    eax, eax
0x1800ac748  jz      loc_1800AC950
0x1800ac74e  lea     r8, [rsp+8E0h+Buffer]
0x1800ac753  lea     rdx, aFoundACabInWs; "Found a CAB in %ws"
0x1800ac75a  lea     rcx, aNpackageinstal_20; "NPackageInstallLocalspl::TDriverStore::"...
0x1800ac761  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800ac766  mov     ebx, 208h
0x1800ac76b  lea     rcx, [rbp+7E0h+PathName]; void *
0x1800ac772  mov     r8d, ebx; Size
0x1800ac775  xor     edx, edx; Val
0x1800ac777  call    memset_0
0x1800ac77c  mov     r8d, ebx; Size
0x1800ac77f  lea     rcx, [rbp+7E0h+var_670]; void *
0x1800ac786  xor     edx, edx; Val
0x1800ac788  call    memset_0
0x1800ac78d  mov     rdx, [r13+28h]
0x1800ac791  lea     r8, [rbp+7E0h+PathName]
0x1800ac798  call    GetUniqueTempDirInPrintShare
0x1800ac79d  mov     ebx, eax
0x1800ac79f  test    eax, eax
0x1800ac7a1  js      loc_1800AC979
0x1800ac7a7  xor     edx, edx; lpSecurityAttributes
0x1800ac7a9  lea     rcx, [rbp+7E0h+PathName]; lpPathName
0x1800ac7b0  call    cs:__imp_CreateDirectoryW
0x1800ac7b6  test    eax, eax
0x1800ac7b8  jnz     short loc_1800AC7C9
0x1800ac7ba  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800ac7bf  mov     ebx, eax
0x1800ac7c1  test    eax, eax
0x1800ac7c3  js      loc_1800AC979
0x1800ac7c9  lea     rdx, [rbp+7E0h+PathName]; unsigned __int16 *
0x1800ac7d0  lea     rcx, [rsp+8E0h+Buffer]; this
0x1800ac7d5  call    ?LegacyCabUnpack@NCabbingLibrary@@YAJPEBG0@Z; NCabbingLibrary::LegacyCabUnpack(ushort const *,ushort const *)
0x1800ac7da  mov     ebx, eax
0x1800ac7dc  test    eax, eax
0x1800ac7de  js      loc_1800AC93B
0x1800ac7e4  mov     r10d, 104h
0x1800ac7ea  lea     r8, [rbp+7E0h+PathName]; unsigned __int16 *
0x1800ac7f1  mov     edx, r10d; unsigned __int64
0x1800ac7f4  lea     rcx, [rbp+7E0h+var_670]; unsigned __int16 *
0x1800ac7fb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ac800  mov     ebx, eax
0x1800ac802  test    eax, eax
0x1800ac804  js      loc_1800AC93B
0x1800ac80a  lea     r8, SubBlock; "\\"
0x1800ac811  mov     edx, r10d; unsigned __int64
0x1800ac814  lea     rcx, [rbp+7E0h+var_670]; unsigned __int16 *
0x1800ac81b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ac820  mov     ebx, eax
0x1800ac822  test    eax, eax
0x1800ac824  js      loc_1800AC93B
0x1800ac82a  mov     r8, [rsp+8E0h+var_898]; unsigned __int16 *
0x1800ac82f  lea     rcx, [rbp+7E0h+var_670]; unsigned __int16 *
0x1800ac836  mov     edx, 104h; unsigned __int64
0x1800ac83b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ac840  mov     ebx, eax
0x1800ac842  test    eax, eax
0x1800ac844  js      loc_1800AC93B
  ... truncated ...
```
