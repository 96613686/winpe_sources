# GenerateDirectoryNamesForCopyFilesKey(_SPOOL *,void *,ushort const *,ushort * *,ushort * *,ulong)

- ea: `0x18009aac4`
- end: `0x18009afda`
- name: `?GenerateDirectoryNamesForCopyFilesKey@@YAHPEAU_SPOOL@@PEAXPEBGPEAPEAG3K@Z`
- size: `1302`
- prototype: `__int64 __fastcall(struct _SPOOL *, void *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18008a1fc`

## callees

- `0x180008520`
- `0x180008560`
- `0x18000edc4`
- `0x180011f00`
- `0x1800170a0`
- `0x18003ea2c`
- `0x18004486c`
- `0x18009aac4`
- `0x18009afe0`
- `0x18009bb70`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009ab86`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009ad7e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009af01`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009ab86`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009ad7e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009af01`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18009ab66`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18009ab66`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009adca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009adca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009ad23`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009ad23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009ab3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009acc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009af26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009afbe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009ab3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009acc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009af26`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009afbe`
- `SPOOLSS!DllFreeSplStr` at `0x18009acf6`
- `SPOOLSS!DllFreeSplStr` at `0x18009ad00`
- `SPOOLSS!DllFreeSplStr` at `0x18009ad09`
- `SPOOLSS!DllFreeSplStr` at `0x18009ad13`
- `SPOOLSS!DllFreeSplStr` at `0x18009ad35`
- `SPOOLSS!DllFreeSplStr` at `0x18009ad47`
- `SPOOLSS!DllFreeSplStr` at `0x18009acf6`
- `SPOOLSS!DllFreeSplStr` at `0x18009ad00`
- `SPOOLSS!DllFreeSplStr` at `0x18009ad09`
- `SPOOLSS!DllFreeSplStr` at `0x18009ad13`
- `SPOOLSS!DllFreeSplStr` at `0x18009ad35`
- `SPOOLSS!DllFreeSplStr` at `0x18009ad47`
- `SPOOLSS!DllAllocSplMem` at `0x18009abc9`
- `SPOOLSS!DllAllocSplMem` at `0x18009abd4`
- `SPOOLSS!DllAllocSplMem` at `0x18009abe0`
- `SPOOLSS!DllAllocSplMem` at `0x18009adf4`
- `SPOOLSS!DllAllocSplMem` at `0x18009ae06`
- `SPOOLSS!DllAllocSplMem` at `0x18009abc9`
- `SPOOLSS!DllAllocSplMem` at `0x18009abd4`
- `SPOOLSS!DllAllocSplMem` at `0x18009abe0`
- `SPOOLSS!DllAllocSplMem` at `0x18009adf4`
- `SPOOLSS!DllAllocSplMem` at `0x18009ae06`
- `SPOOLSS!AllocSplStr` at `0x18009ae31`
- `SPOOLSS!AllocSplStr` at `0x18009ae31`

## string_xrefs

- `0x18009ab25`: `CopyFiles is not allowed when Windows Protected Print is enabled!`
- `0x18009ab93`: `CopyFiles specified registry key %ws for copy operations but only ICM is allowed!`
- `0x18009abac`: `CopyFiles is not allowed!`
- `0x18009ab2c`: `GenerateDirectoryNamesForCopyFilesKey`
- `0x18009ab9a`: `GenerateDirectoryNamesForCopyFilesKey`
- `0x18009ace5`: `GenerateDirectoryNamesForCopyFilesKey`
- `0x18009ad92`: `GenerateDirectoryNamesForCopyFilesKey`
- `0x18009af15`: `GenerateDirectoryNamesForCopyFilesKey`
- `0x18009afa8`: `GenerateDirectoryNamesForCopyFilesKey`
- `0x18009adc0`: `GenerateCopyFilePaths`
- `0x18009ac29`: `Directory`
- `0x18009ad8b`: `CopyFiles specified module %ws for copy operations but only mscms.dll is allowed!`
- `0x18009acdb`: `Failed to generate names for file copy for printer '%ws' path '%ws'.`
- `0x18009af0e`: `CopyFiles specified directory %ws for copy operations but only COLOR is allowed!`
- `0x18009af9a`: `GenerateCopyFilePaths for printer '%ws' path '%ws' failed with error code %d`
- `0x18009ad74`: `mscms.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GenerateDirectoryNamesForCopyFilesKey(
        struct _SPOOL *a1,
        void *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        unsigned int a6)
{
  unsigned __int8 *v6; // rsi
  unsigned __int8 *v7; // r14
  DWORD v11; // ecx
  unsigned __int16 **v12; // r15
  HMODULE v13; // r13
  int CopyFilesPolicy; // eax
  unsigned int v15; // ebx
  wchar_t *v16; // rax
  HMODULE LibraryTheCopyFileModule; // rax
  DWORD v18; // ecx
  FARPROC ProcAddress; // rdi
  unsigned __int16 *v21; // rax
  __int64 v22; // rcx
  unsigned __int16 *v23; // rax
  __int64 v24; // r8
  unsigned __int64 v25; // rcx
  __int64 v26; // rax
  __int128 v27; // xmm1
  __int64 v28; // xmm0_8
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  unsigned int *v32; // [rsp+20h] [rbp-89h]
  struct _INISPOOLER *v33; // [rsp+28h] [rbp-81h]
  struct _INISPOOLER *v34; // [rsp+28h] [rbp-81h]
  struct _INISPOOLER *v35; // [rsp+28h] [rbp-81h]
  HMODULE v36; // [rsp+50h] [rbp-59h]
  unsigned int v37; // [rsp+58h] [rbp-51h] BYREF
  unsigned int v38; // [rsp+5Ch] [rbp-4Dh] BYREF
  unsigned __int64 v39; // [rsp+60h] [rbp-49h] BYREF
  int v40; // [rsp+68h] [rbp-41h]
  __int64 v41; // [rsp+70h] [rbp-39h]
  unsigned __int8 *v42; // [rsp+78h] [rbp-31h]
  __int128 v43; // [rsp+80h] [rbp-29h] BYREF
  __int128 v44; // [rsp+90h] [rbp-19h]
  __int64 v45; // [rsp+A0h] [rbp-9h]

  v38 = 0;
  v6 = 0;
  v37 = 0;
  v7 = 0;
  v39 = 0;
  v42 = 0;
  v41 = 0;
  v36 = 0;
  v43 = 0;
  v45 = 0;
  v44 = 0;
  if ( (unsigned int)IsWindowsProtectedPrintEnabled() )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "GenerateDirectoryNamesForCopyFilesKey",
      L"CopyFiles is not allowed when Windows Protected Print is enabled!");
LABEL_3:
    v11 = 1260;
LABEL_4:
    SetLastError(v11);
    v12 = a4;
    v13 = 0;
LABEL_28:
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "GenerateDirectoryNamesForCopyFilesKey",
      L"Failed to generate names for file copy for printer '%ws' path '%ws'.",
      v41,
      v6);
    v15 = 0;
    goto LABEL_29;
  }
  CopyFilesPolicy = GetCopyFilesPolicy();
  v15 = 1;
  v40 = CopyFilesPolicy;
  if ( CopyFilesPolicy == 1 )
  {
    v16 = wcsrchr(a3, 0x5Cu);
    if ( v16 )
      a3 = v16 + 1;
    if ( !*a3 || (unsigned int)_o__wcsicmp(a3, L"ICM") )
    {
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "GenerateDirectoryNamesForCopyFilesKey",
        L"CopyFiles specified registry key %ws for copy operations but only ICM is allowed!",
        a3);
      goto LABEL_3;
    }
  }
  else if ( !CopyFilesPolicy )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError("GenerateDirectoryNamesForCopyFilesKey", L"CopyFiles is not allowed!");
    goto LABEL_3;
  }
  if ( !a6 )
  {
    v11 = 87;
    goto LABEL_4;
  }
  v6 = (unsigned __int8 *)DllAllocSplMem(a6);
  v42 = (unsigned __int8 *)DllAllocSplMem(a6);
  v7 = (unsigned __int8 *)DllAllocSplMem(a6);
  LibraryTheCopyFileModule = 0;
  if ( !v6 || !v42 || !v7 )
    goto LABEL_62;
  v33 = (struct _INISPOOLER *)*((_QWORD *)a1 + 21);
  v37 = a6;
  if ( !SplRegQueryValue(a2, L"Directory", &v38, v6, &v37, v33) && v38 == 1 )
  {
    v34 = (struct _INISPOOLER *)*((_QWORD *)a1 + 21);
    v37 = a6;
    if ( !SplRegQueryValue(a2, L"Files", &v38, v42, &v37, v34) && v38 == 7 )
    {
      v35 = (struct _INISPOOLER *)*((_QWORD *)a1 + 21);
      v37 = a6;
      if ( !SplRegQueryValue(a2, L"Module", &v38, v7, &v37, v35) && v38 != 1 )
      {
        v18 = 87;
LABEL_25:
        SetLastError(v18);
LABEL_26:
        v12 = a4;
LABEL_27:
        v13 = v36;
        goto LABEL_28;
      }
    }
  }
  if ( !*(_WORD *)v7 )
  {
    ProcAddress = 0;
    goto LABEL_45;
  }
  if ( v40 == 1 && (unsigned int)_o__wcsicmp(v7, L"mscms.dll") )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "GenerateDirectoryNamesForCopyFilesKey",
      L"CopyFiles specified module %ws for copy operations but only mscms.dll is allowed!",
      v7);
    v18 = 1260;
    goto LABEL_25;
  }
  LibraryTheCopyFileModule = (HMODULE)SplLoadLibraryTheCopyFileModule(a1, v7);
  v36 = LibraryTheCopyFileModule;
  if ( !LibraryTheCopyFileModule )
  {
LABEL_62:
    v12 = a4;
    v13 = LibraryTheCopyFileModule;
    goto LABEL_28;
  }
  ProcAddress = GetProcAddress(LibraryTheCopyFileModule, "GenerateCopyFilePaths");
  if ( !ProcAddress )
    goto LABEL_26;
LABEL_45:
  v39 = 0x20400000104LL;
  v21 = (unsigned __int16 *)DllAllocSplMem(1032);
  v12 = a4;
  v22 = (unsigned int)(2 * v39);
  *a4 = v21;
  v23 = (unsigned __int16 *)DllAllocSplMem(v22);
  *a5 = v23;
  if ( !*a4 || !v23 )
    goto LABEL_27;
  EnterSplSem(0);
  v41 = AllocSplStr(*(_QWORD *)(*((_QWORD *)a1 + 8) + 24LL));
  if ( !v41 )
    goto LABEL_61;
  v24 = -1;
  v25 = -1;
  do
    ++v25;
  while ( *(_WORD *)&v6[2 * v25] );
  if ( v25 >= (unsigned int)v39 )
    goto LABEL_61;
  v26 = -1;
  do
    ++v26;
  while ( *(_WORD *)(*((_QWORD *)a1 + 4) + 2 * v26) );
  do
    ++v24;
  while ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)a1 + 21) + 152LL) + 2 * v24) );
  if ( v24 + v26 + v25 + 2 >= HIDWORD(v39) )
  {
LABEL_61:
    SetLastError(0x57u);
    LeaveSplSem(v31);
    goto LABEL_27;
  }
  StringCchPrintfW(*a4, HIDWORD(v39), L"%ws\\%ws\\%ws");
  v27 = *((_OWORD *)a1 + 15);
  v43 = *((_OWORD *)a1 + 14);
  v28 = *((_QWORD *)a1 + 32);
  *((_QWORD *)&v44 + 1) = *((_QWORD *)&v27 + 1);
  *(_QWORD *)&v44 = 0;
  *((_QWORD *)&v43 + 1) = 0;
  v45 = v28;
  LeaveSplSem(v29);
  if ( v40 == 1 && (unsigned int)_o__wcsicmp(v6, L"COLOR") )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "GenerateDirectoryNamesForCopyFilesKey",
      L"CopyFiles specified directory %ws for copy operations but only COLOR is allowed!",
      v6);
    SetLastError(0x4ECu);
    goto LABEL_27;
  }
  StringCchCopyW(*a5, (unsigned int)v39, (const unsigned __int16 *)v6);
  v13 = v36;
  if ( v36 )
  {
    v30 = ((__int64 (__fastcall *)(__int64, unsigned __int8 *, __int128 *, __int64, _QWORD, char *, _QWORD, unsigned __int64 *, int))ProcAddress)(
            v41,
            v6,
            &v43,
            1,
            *a4,
            (char *)&v39 + 4,
            *a5,
            &v39,
            2);
    if ( v30 )
    {
      LODWORD(v32) = v30;
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "GenerateDirectoryNamesForCopyFilesKey",
        L"GenerateCopyFilePaths for printer '%ws' path '%ws' failed with error code %d",
        v41,
        v6,
        v32);
      goto LABEL_28;
    }
  }
LABEL_29:
  DllFreeSplStr(v6);
  DllFreeSplStr(v42);
  DllFreeSplStr(v7);
  DllFreeSplStr(v41);
  if ( v13 )
    FreeLibrary(v13);
  if ( !v15 )
  {
    if ( v12 )
    {
      DllFreeSplStr(*v12);
      *v12 = 0;
    }
    if ( a5 )
    {
      DllFreeSplStr(*a5);
      *a5 = 0;
    }
  }
  return v15;
}

```

## disassembly

```asm
0x18009aac4  mov     [rsp-8+arg_18], r9
0x18009aac9  push    rbp
0x18009aaca  push    rbx
0x18009aacb  push    rsi
0x18009aacc  push    rdi
0x18009aacd  push    r12
0x18009aacf  push    r13
0x18009aad1  push    r14
0x18009aad3  push    r15
0x18009aad5  lea     rbp, [rsp-0Fh]
0x18009aada  sub     rsp, 0B8h
0x18009aae1  xor     eax, eax
0x18009aae3  xorps   xmm0, xmm0
0x18009aae6  mov     [rbp+47h+var_94], eax
0x18009aae9  mov     esi, eax
0x18009aaeb  mov     [rbp+47h+var_98], eax
0x18009aaee  mov     r14d, eax
0x18009aaf1  mov     dword ptr [rbp+47h+var_90+4], eax
0x18009aaf4  mov     rdi, r8
0x18009aaf7  mov     dword ptr [rbp+47h+var_90], eax
0x18009aafa  mov     r15, rdx
0x18009aafd  mov     [rbp+47h+var_78], rax
0x18009ab01  mov     r13, rcx
0x18009ab04  mov     [rbp+47h+var_80], rax
0x18009ab08  mov     [rbp+47h+var_A0], rax
0x18009ab0c  movups  [rbp+47h+var_70], xmm0
0x18009ab10  mov     [rbp+47h+var_50], rax
0x18009ab14  movups  [rbp+47h+var_60], xmm0
0x18009ab18  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x18009ab1d  mov     r12, [rbp+47h+arg_20]
0x18009ab21  test    eax, eax
0x18009ab23  jz      short loc_18009AB4F
0x18009ab25  lea     rdx, aCopyfilesIsNot; "CopyFiles is not allowed when Windows P"...
0x18009ab2c  lea     rcx, aGeneratedirect; "GenerateDirectoryNamesForCopyFilesKey"
0x18009ab33  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009ab38  mov     ecx, 4ECh; dwErrCode
0x18009ab3d  call    cs:__imp_SetLastError
0x18009ab43  mov     r15, [rbp+47h+arg_18]
0x18009ab47  mov     r13, rsi
0x18009ab4a  jmp     loc_18009ACD7
0x18009ab4f  call    ?GetCopyFilesPolicy@@YA?AW4ECopyFilesPolicy@@XZ; GetCopyFilesPolicy(void)
0x18009ab54  mov     ebx, 1
0x18009ab59  mov     [rbp+47h+var_88], eax
0x18009ab5c  cmp     eax, ebx
0x18009ab5e  jnz     short loc_18009ABA8
0x18009ab60  lea     edx, [rbx+5Bh]; Ch
0x18009ab63  mov     rcx, rdi; Str
0x18009ab66  call    cs:__imp_wcsrchr
0x18009ab6c  xor     ecx, ecx
0x18009ab6e  test    rax, rax
0x18009ab71  jz      short loc_18009AB77
0x18009ab73  lea     rdi, [rax+2]
0x18009ab77  cmp     [rdi], cx
0x18009ab7a  jz      short loc_18009AB90
0x18009ab7c  lea     rdx, aIcm_0; "ICM"
0x18009ab83  mov     rcx, rdi
0x18009ab86  call    cs:__imp__o__wcsicmp
0x18009ab8c  test    eax, eax
0x18009ab8e  jz      short loc_18009ABB8
0x18009ab90  mov     r8, rdi
0x18009ab93  lea     rdx, aCopyfilesSpeci_0; "CopyFiles specified registry key %ws fo"...
0x18009ab9a  lea     rcx, aGeneratedirect; "GenerateDirectoryNamesForCopyFilesKey"
0x18009aba1  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009aba6  jmp     short loc_18009AB38
0x18009aba8  test    eax, eax
0x18009abaa  jnz     short loc_18009ABB8
0x18009abac  lea     rdx, aCopyfilesIsNot_0; "CopyFiles is not allowed!"
0x18009abb3  jmp     loc_18009AB2C
0x18009abb8  mov     edi, [rbp+47h+arg_28]
0x18009abbb  test    edi, edi
0x18009abbd  jnz     short loc_18009ABC7
0x18009abbf  lea     ecx, [rdi+57h]
0x18009abc2  jmp     loc_18009AB3D
0x18009abc7  mov     ecx, edi
0x18009abc9  call    cs:__imp_DllAllocSplMem
0x18009abcf  mov     ecx, edi
0x18009abd1  mov     rsi, rax
0x18009abd4  call    cs:__imp_DllAllocSplMem
0x18009abda  mov     ecx, edi
0x18009abdc  mov     [rbp+47h+var_78], rax
0x18009abe0  call    cs:__imp_DllAllocSplMem
0x18009abe6  mov     r14, rax
0x18009abe9  xor     eax, eax
0x18009abeb  test    rsi, rsi
0x18009abee  jz      loc_18009AFCE
0x18009abf4  cmp     [rbp+47h+var_78], rax
0x18009abf8  jz      loc_18009AFCE
0x18009abfe  test    r14, r14
0x18009ac01  jz      loc_18009AFCE
0x18009ac07  mov     rcx, [r13+0A8h]
0x18009ac0e  lea     rax, [rbp+47h+var_98]
0x18009ac12  mov     [rsp+0F0h+var_C8], rcx; struct _INISPOOLER *
0x18009ac17  lea     r8, [rbp+47h+var_94]; unsigned int *
0x18009ac1b  mov     rcx, r15; void *
0x18009ac1e  mov     [rbp+47h+var_98], edi
0x18009ac21  mov     r9, rsi; unsigned __int8 *
0x18009ac24  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x18009ac29  lea     rdx, aDirectory; "Directory"
0x18009ac30  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x18009ac35  test    eax, eax
0x18009ac37  jnz     loc_18009AD67
0x18009ac3d  cmp     [rbp+47h+var_94], ebx
0x18009ac40  jnz     loc_18009AD67
0x18009ac46  mov     rax, [r13+0A8h]
0x18009ac4d  lea     r8, [rbp+47h+var_94]; unsigned int *
0x18009ac51  mov     r9, [rbp+47h+var_78]; unsigned __int8 *
0x18009ac55  lea     rdx, aFiles; "Files"
0x18009ac5c  mov     [rsp+0F0h+var_C8], rax; struct _INISPOOLER *
0x18009ac61  mov     rcx, r15; void *
0x18009ac64  lea     rax, [rbp+47h+var_98]
0x18009ac68  mov     [rbp+47h+var_98], edi
0x18009ac6b  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x18009ac70  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x18009ac75  test    eax, eax
0x18009ac77  jnz     loc_18009AD67
0x18009ac7d  cmp     [rbp+47h+var_94], 7
0x18009ac81  jnz     loc_18009AD67
0x18009ac87  mov     rax, [r13+0A8h]
0x18009ac8e  lea     r8, [rbp+47h+var_94]; unsigned int *
0x18009ac92  mov     [rsp+0F0h+var_C8], rax; struct _INISPOOLER *
0x18009ac97  lea     rdx, aModule; "Module"
0x18009ac9e  lea     rax, [rbp+47h+var_98]
0x18009aca2  mov     [rbp+47h+var_98], edi
0x18009aca5  mov     r9, r14; unsigned __int8 *
0x18009aca8  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x18009acad  mov     rcx, r15; void *
0x18009acb0  call    ?SplRegQueryValue@@YAJPEAXPEBGPEAKPEAE2PEAU_INISPOOLER@@@Z; SplRegQueryValue(void *,ushort const *,ulong *,uchar *,ulong *,_INISPOOLER *)
0x18009acb5  test    eax, eax
0x18009acb7  jnz     loc_18009AD67
0x18009acbd  cmp     [rbp+47h+var_94], ebx
0x18009acc0  jz      loc_18009AD67
0x18009acc6  lea     ecx, [rax+57h]; dwErrCode
0x18009acc9  call    cs:__imp_SetLastError
0x18009accf  mov     r15, [rbp+47h+arg_18]
0x18009acd3  mov     r13, [rbp+47h+var_A0]
0x18009acd7  mov     r8, [rbp+47h+var_80]
0x18009acdb  lea     rdx, aFailedToGenera; "Failed to generate names for file copy "...
0x18009ace2  mov     r9, rsi
0x18009ace5  lea     rcx, aGeneratedirect; "GenerateDirectoryNamesForCopyFilesKey"
0x18009acec  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009acf1  xor     ebx, ebx
0x18009acf3  mov     rcx, rsi
0x18009acf6  call    cs:__imp_DllFreeSplStr
0x18009acfc  mov     rcx, [rbp+47h+var_78]
0x18009ad00  call    cs:__imp_DllFreeSplStr
0x18009ad06  mov     rcx, r14
0x18009ad09  call    cs:__imp_DllFreeSplStr
0x18009ad0f  mov     rcx, [rbp+47h+var_80]
0x18009ad13  call    cs:__imp_DllFreeSplStr
0x18009ad19  xor     esi, esi
0x18009ad1b  test    r13, r13
0x18009ad1e  jz      short loc_18009AD29
0x18009ad20  mov     rcx, r13; hLibModule
0x18009ad23  call    cs:__imp_FreeLibrary
0x18009ad29  test    ebx, ebx
0x18009ad2b  jnz     short loc_18009AD51
0x18009ad2d  test    r15, r15
0x18009ad30  jz      short loc_18009AD3E
0x18009ad32  mov     rcx, [r15]
0x18009ad35  call    cs:__imp_DllFreeSplStr
0x18009ad3b  mov     [r15], rsi
0x18009ad3e  test    r12, r12
0x18009ad41  jz      short loc_18009AD51
0x18009ad43  mov     rcx, [r12]
0x18009ad47  call    cs:__imp_DllFreeSplStr
0x18009ad4d  mov     [r12], rsi
0x18009ad51  mov     eax, ebx
0x18009ad53  add     rsp, 0B8h
0x18009ad5a  pop     r15
0x18009ad5c  pop     r14
0x18009ad5e  pop     r13
0x18009ad60  pop     r12
0x18009ad62  pop     rdi
0x18009ad63  pop     rsi
0x18009ad64  pop     rbx
0x18009ad65  pop     rbp
0x18009ad66  retn
0x18009ad67  xor     eax, eax
0x18009ad69  cmp     [r14], ax
0x18009ad6d  jz      short loc_18009ADDE
0x18009ad6f  cmp     [rbp+47h+var_88], ebx
0x18009ad72  jnz     short loc_18009ADA8
0x18009ad74  lea     rdx, aMscmsDll_0; "mscms.dll"
0x18009ad7b  mov     rcx, r14
0x18009ad7e  call    cs:__imp__o__wcsicmp
0x18009ad84  test    eax, eax
0x18009ad86  jz      short loc_18009ADA8
0x18009ad88  mov     r8, r14
0x18009ad8b  lea     rdx, aCopyfilesSpeci_1; "CopyFiles specified module %ws for copy"...
0x18009ad92  lea     rcx, aGeneratedirect; "GenerateDirectoryNamesForCopyFilesKey"
0x18009ad99  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009ad9e  mov     ecx, 4ECh
0x18009ada3  jmp     loc_18009ACC9
0x18009ada8  mov     rdx, r14
0x18009adab  mov     rcx, r13
0x18009adae  call    SplLoadLibraryTheCopyFileModule
0x18009adb3  mov     [rbp+47h+var_A0], rax
0x18009adb7  test    rax, rax
0x18009adba  jz      loc_18009AFCE
0x18009adc0  lea     rdx, aGeneratecopyfi_0; "GenerateCopyFilePaths"
0x18009adc7  mov     rcx, rax; hModule
0x18009adca  call    cs:__imp_GetProcAddress
0x18009add0  mov     rdi, rax
0x18009add3  test    rax, rax
0x18009add6  jz      loc_18009ACCF
0x18009addc  jmp     short loc_18009ADE1
0x18009adde  mov     rdi, rax
0x18009ade1  mov     ecx, 408h
0x18009ade6  mov     dword ptr [rbp+47h+var_90], 104h
0x18009aded  mov     dword ptr [rbp+47h+var_90+4], 204h
0x18009adf4  call    cs:__imp_DllAllocSplMem
0x18009adfa  mov     ecx, dword ptr [rbp+47h+var_90]
0x18009adfd  mov     r15, [rbp+47h+arg_18]
0x18009ae01  add     ecx, ecx
0x18009ae03  mov     [r15], rax
0x18009ae06  call    cs:__imp_DllAllocSplMem
0x18009ae0c  xor     ecx, ecx
0x18009ae0e  mov     [r12], rax
0x18009ae12  cmp     [r15], rcx
0x18009ae15  jz      loc_18009ACD3
0x18009ae1b  test    rax, rax
0x18009ae1e  jz      loc_18009ACD3
0x18009ae24  call    EnterSplSem
0x18009ae29  mov     rcx, [r13+40h]
0x18009ae2d  mov     rcx, [rcx+18h]
0x18009ae31  call    cs:__imp_AllocSplStr
0x18009ae37  xor     r11d, r11d
0x18009ae3a  mov     [rbp+47h+var_80], rax
0x18009ae3e  test    rax, rax
0x18009ae41  jz      loc_18009AFB9
0x18009ae47  or      r8, 0FFFFFFFFFFFFFFFFh
0x18009ae4b  mov     rcx, r8
0x18009ae4e  inc     rcx
0x18009ae51  cmp     [rsi+rcx*2], r11w
0x18009ae56  jnz     short loc_18009AE4E
0x18009ae58  mov     eax, dword ptr [rbp+47h+var_90]
0x18009ae5b  cmp     rcx, rax
0x18009ae5e  jnb     loc_18009AFB9
0x18009ae64  mov     rax, [r13+0A8h]
0x18009ae6b  mov     edx, dword ptr [rbp+47h+var_90+4]; unsigned __int64
0x18009ae6e  mov     r9, [r13+20h]
0x18009ae72  mov     r10, [rax+98h]
0x18009ae79  mov     rax, r8
0x18009ae7c  inc     rax
0x18009ae7f  cmp     [r9+rax*2], r11w
0x18009ae84  jnz     short loc_18009AE7C
0x18009ae86  inc     r8
0x18009ae89  cmp     [r10+r8*2], r11w
0x18009ae8e  jnz     short loc_18009AE86
0x18009ae90  add     rax, r8
0x18009ae93  add     rcx, 2
0x18009ae97  add     rcx, rax
0x18009ae9a  cmp     rcx, rdx
0x18009ae9d  jnb     loc_18009AFB9
0x18009aea3  mov     rcx, [r15]; unsigned __int16 *
0x18009aea6  lea     r8, aWsWsWs_1; "%ws\\%ws\\%ws"
0x18009aead  mov     [rsp+0F0h+var_C8], rsi
0x18009aeb2  mov     [rsp+0F0h+var_D0], r10
0x18009aeb7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009aebc  movups  xmm0, xmmword ptr [r13+0E0h]
0x18009aec4  movups  xmm1, xmmword ptr [r13+0F0h]
0x18009aecc  movups  [rbp+47h+var_70], xmm0
0x18009aed0  movsd   xmm0, qword ptr [r13+100h]
0x18009aed9  xor     r13d, r13d
0x18009aedc  movups  [rbp+47h+var_60], xmm1
0x18009aee0  mov     qword ptr [rbp+47h+var_60], r13
0x18009aee4  mov     qword ptr [rbp+47h+var_70+8], r13
0x18009aee8  movsd   [rbp+47h+var_50], xmm0
0x18009aeed  call    LeaveSplSem
0x18009aef2  cmp     [rbp+47h+var_88], ebx
0x18009aef5  jnz     short loc_18009AF31
0x18009aef7  lea     rdx, aColor_1; "COLOR"
0x18009aefe  mov     rcx, rsi
0x18009af01  call    cs:__imp__o__wcsicmp
0x18009af07  test    eax, eax
0x18009af09  jz      short loc_18009AF31
0x18009af0b  mov     r8, rsi
0x18009af0e  lea     rdx, aCopyfilesSpeci; "CopyFiles specified directory %ws for c"...
0x18009af15  lea     rcx, aGeneratedirect; "GenerateDirectoryNamesForCopyFilesKey"
0x18009af1c  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18009af21  mov     ecx, 4ECh; dwErrCode
0x18009af26  call    cs:__imp_SetLastError
0x18009af2c  jmp     loc_18009ACD3
0x18009af31  mov     edx, dword ptr [rbp+47h+var_90]; unsigned __int64
0x18009af34  mov     r8, rsi; unsigned __int16 *
0x18009af37  mov     rcx, [r12]; unsigned __int16 *
0x18009af3b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009af40  mov     r13, [rbp+47h+var_A0]
0x18009af44  test    r13, r13
0x18009af47  jz      loc_18009ACF3
0x18009af4d  mov     rcx, [rbp+47h+var_80]
0x18009af51  lea     rax, [rbp+47h+var_90]
0x18009af55  mov     [rsp+0F0h+var_B0], 2
0x18009af5d  lea     r8, [rbp+47h+var_70]
0x18009af61  mov     [rsp+0F0h+var_B8], rax
0x18009af66  mov     r9d, ebx
0x18009af69  mov     rax, [r12]
0x18009af6d  mov     rdx, rsi
0x18009af70  mov     [rsp+0F0h+var_C0], rax
0x18009af75  lea     rax, [rbp+47h+var_90+4]
  ... truncated ...
```
