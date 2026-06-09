# AddTempDriver(_INISPOOLER *,_INIENVIRONMENT *,_INIVERSION *,ulong,uchar *,ulong,_INTERNAL_DRV_FILE *,ulong,ulong,int,_INIDRIVER *)

- ea: `0x180069f64`
- end: `0x18006a413`
- name: `?AddTempDriver@@YAHPEAU_INISPOOLER@@PEAU_INIENVIRONMENT@@PEAU_INIVERSION@@KPEAEKPEAU_INTERNAL_DRV_FILE@@KKHPEAU_INIDRIVER@@@Z`
- size: `1199`
- prototype: `__int64 __fastcall(struct _INISPOOLER *, struct _INIENVIRONMENT *, struct _INIVERSION *, unsigned int, unsigned __int8 *, unsigned int, struct _INTERNAL_DRV_FILE *, unsigned int, unsigned int, unsigned int, struct _INIDRIVER *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800705a0`

## callees

- `0x18000bb60`
- `0x18000d944`
- `0x18000edc4`
- `0x18001fb10`
- `0x180030cdc`
- `0x180031388`
- `0x180034e78`
- `0x18003ea2c`
- `0x180046650`
- `0x180069f64`
- `0x18006ab60`
- `0x18006da74`
- `0x18009d704`
- `0x18009d81c`
- `0x1800ccbd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a15f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a19b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a22c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a3d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a15f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a19b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a22c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a3d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a20a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a20a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006a133`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006a133`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18006a151`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18006a21e`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18006a151`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18006a21e`
- `SPOOLSS!DllFreeSplMem` at `0x18006a3c8`
- `SPOOLSS!DllFreeSplMem` at `0x18006a3c8`
- `SPOOLSS!RevertToPrinterSelf` at `0x180069fd2`
- `SPOOLSS!RevertToPrinterSelf` at `0x180069fd2`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18006a3bf`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18006a3bf`

## string_xrefs

- `0x18006a174`: `Failed to copy '%ws' to '%ws'.  Error %d`
- `0x18006a241`: `Failed to copy '%ws' to '%ws'.  Error %d`
- `0x18006a3db`: `Failing AddTempDriver call.  Error %d`
- `0x18006a17b`: `AddTempDriver`
- `0x18006a248`: `AddTempDriver`
- `0x18006a3e2`: `AddTempDriver`

## pseudocode

```c
__int64 __fastcall AddTempDriver(
        struct _INISPOOLER *a1,
        struct _INIENVIRONMENT *a2,
        struct _INIVERSION *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        struct _INTERNAL_DRV_FILE *a7,
        unsigned int a8,
        unsigned int a9,
        unsigned int a10,
        struct _INIDRIVER *a11)
{
  struct _INIDRIVERTOUPDATE *v11; // rsi
  struct _INTERNAL_DRV_FILE *v12; // r14
  unsigned int v16; // edi
  HANDLE v17; // rax
  __int64 v18; // r8
  unsigned int v19; // ebx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  struct SplLogType *v22; // rax
  __int64 v23; // r10
  int *v24; // r9
  int *v25; // rcx
  DWORD v26; // eax
  unsigned __int8 *v27; // r15
  unsigned int v28; // r14d
  int v29; // eax
  struct _INIDRIVERTOUPDATE *v30; // rbx
  __int64 v31; // rcx
  DWORD v32; // eax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-E0h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-D0h]
  struct _INTERNAL_DRV_FILE *v37; // [rsp+38h] [rbp-C8h]
  unsigned int v38; // [rsp+48h] [rbp-B8h]
  struct _INIDRIVERTOUPDATE *MustForceUpdateDriverList; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v40; // [rsp+88h] [rbp-78h]
  unsigned int v41; // [rsp+8Ch] [rbp-74h]
  int v42; // [rsp+90h] [rbp-70h] BYREF
  __int64 v43; // [rsp+98h] [rbp-68h]
  int v44; // [rsp+A0h] [rbp-60h]
  DWORD v45; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v46; // [rsp+B0h] [rbp-50h]
  int v47; // [rsp+B8h] [rbp-48h]
  int v48; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v49; // [rsp+C8h] [rbp-38h]
  int v50; // [rsp+D0h] [rbp-30h]
  struct _INTERNAL_DRV_FILE *v51; // [rsp+D8h] [rbp-28h]
  struct _INIENVIRONMENT *v52; // [rsp+E0h] [rbp-20h]
  unsigned __int8 *v53; // [rsp+E8h] [rbp-18h]
  struct _INIDRIVER *v54; // [rsp+F0h] [rbp-10h]
  HANDLE hToken; // [rsp+F8h] [rbp-8h]
  _BYTE v56[24]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v57[24]; // [rsp+118h] [rbp+18h] BYREF
  WCHAR NewFileName[264]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR FileName[264]; // [rsp+340h] [rbp+240h] BYREF
  _BYTE v60[528]; // [rsp+550h] [rbp+450h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+760h] [rbp+660h] BYREF
  unsigned __int16 v62[272]; // [rsp+970h] [rbp+870h] BYREF

  v11 = 0;
  v12 = a7;
  v53 = a5;
  v16 = 0;
  v54 = a11;
  v41 = a4;
  v52 = a2;
  v51 = a7;
  MustForceUpdateDriverList = 0;
  v17 = RevertToPrinterSelf();
  v18 = *((_QWORD *)a1 + 4);
  hToken = v17;
  hTemplateFile = (HANDLE)*((_QWORD *)a3 + 3);
  *(_QWORD *)dwCreationDisposition = *((_QWORD *)a2 + 5);
  if ( !(unsigned int)StrNCatBuff(v60, 255, v18, L"\\drivers\\") )
  {
    v40 = CreateNumberedTempDirectory(v60, &MustForceUpdateDriverList);
    if ( v40 == -1 )
    {
      v11 = MustForceUpdateDriverList;
    }
    else
    {
      StringCchPrintfW(v62, 0x109u, L"%ws\\New", v60, *(_QWORD *)dwCreationDisposition, L"\\", hTemplateFile, 0);
      v11 = MustForceUpdateDriverList;
      v19 = 0;
      if ( a8 )
      {
        while ( 1 )
        {
          FindFileName(*((_QWORD *)v12 + 4 * v19));
          if ( (unsigned int)StrNCatBuff(FileName, 260, v62, L"\\")
            || (unsigned int)StrNCatBuff(ExistingFileName, 260, v60, L"\\")
            || (unsigned int)StrNCatBuff(NewFileName, 260, v11, L"\\") )
          {
            goto LABEL_22;
          }
          FileW = CreateFileW(FileName, 0x80000000, 0, 0, 3u, 0x80u, 0);
          if ( FileW != (HANDLE)-1LL )
            break;
          if ( !CopyFileW(ExistingFileName, NewFileName, 0) )
          {
            dwCreationDispositiona[0] = GetLastError();
            LocalSpoolerTelemetry::WriteDbgTraceError(
              "AddTempDriver",
              L"Failed to copy '%ws' to '%ws'.  Error %d",
              ExistingFileName,
              NewFileName,
              *(_QWORD *)dwCreationDispositiona);
            v42 = 106;
            v43 = 4;
            v44 = 0;
            LastError = GetLastError();
            v46 = 4;
            v45 = LastError;
            v47 = 0;
            v48 = 0;
            v49 = 4;
            v50 = 0;
            SplLogType::SplLogType((SplLogType *)v56, NewFileName);
            v22 = SplLogType::SplLogType((SplLogType *)v57, ExistingFileName);
            v24 = &v48;
            v25 = &v42;
LABEL_10:
            SplLogEvent2(&SPOOLER_COPY_FILE_FAILED, v22, v23, v24, &v45, v25, 0);
          }
LABEL_13:
          SplMoveFileEx(NewFileName, 0, 4u);
          v12 = v51;
          if ( ++v19 >= a8 )
            goto LABEL_14;
        }
        CloseHandle(FileW);
        if ( CopyFileW(FileName, NewFileName, 0) )
          goto LABEL_13;
        dwCreationDispositiona[0] = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "AddTempDriver",
          L"Failed to copy '%ws' to '%ws'.  Error %d",
          FileName,
          NewFileName,
          *(_QWORD *)dwCreationDispositiona);
        v48 = 106;
        v49 = 4;
        v50 = 0;
        v26 = GetLastError();
        v46 = 4;
        v45 = v26;
        v47 = 0;
        v42 = 0;
        v43 = 4;
        v44 = 0;
        SplLogType::SplLogType((SplLogType *)v57, NewFileName);
        v22 = SplLogType::SplLogType((SplLogType *)v56, FileName);
        v24 = &v42;
        v25 = &v48;
        goto LABEL_10;
      }
LABEL_14:
      SplMoveFileEx(v62, 0, 4u);
      MustForceUpdateDriverList = (struct _INIDRIVERTOUPDATE *)BuildTheMustForceUpdateDriverList(
                                                                 (_DWORD)a1,
                                                                 (_DWORD)v52,
                                                                 (_DWORD)a3,
                                                                 (_DWORD)v12,
                                                                 a8);
      v27 = v53;
      v37 = v12;
      v28 = v41;
      v29 = CompleteDriverUpgrade(
              a1,
              v52,
              a3,
              v54,
              v41,
              v53,
              a6,
              v37,
              a8,
              v38,
              v40,
              a10,
              1,
              1,
              &MustForceUpdateDriverList);
      v30 = MustForceUpdateDriverList;
      if ( v29 && (unsigned int)SaveParametersForUpgrade(*((unsigned __int16 **)a1 + 3), a10, v28, v27, a9) )
      {
        v16 = 1;
        if ( !v30 )
          goto LABEL_22;
        ForceDriverUpdateList(v31, a3, v30);
      }
      else
      {
        v16 = 0;
      }
      if ( v30 )
        FreeTheMustForceUpdateDriverList(v30);
    }
  }
LABEL_22:
  if ( hToken )
    ImpersonatePrinterClient(hToken);
  DllFreeSplMem(v11);
  if ( !v16 )
  {
    v32 = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError("AddTempDriver", L"Failing AddTempDriver call.  Error %d", v32);
  }
  return v16;
}

```

## disassembly

```asm
0x180069f64  push    rbp
0x180069f66  push    rbx
0x180069f67  push    rsi
0x180069f68  push    rdi
0x180069f69  push    r12
0x180069f6b  push    r13
0x180069f6d  push    r14
0x180069f6f  push    r15
0x180069f71  lea     rbp, [rsp-0AA8h]
0x180069f79  sub     rsp, 0BA8h
0x180069f80  mov     rax, cs:__security_cookie
0x180069f87  xor     rax, rsp
0x180069f8a  mov     [rbp+0AE0h+var_50], rax
0x180069f91  mov     rax, [rbp+0AE0h+arg_20]
0x180069f98  xor     esi, esi
0x180069f9a  mov     r14, [rbp+0AE0h+arg_30]
0x180069fa1  mov     r13, r8
0x180069fa4  mov     r15d, [rbp+0AE0h+arg_38]
0x180069fab  mov     rbx, rdx
0x180069fae  mov     [rbp+0AE0h+var_AF8], rax
0x180069fb2  mov     r12, rcx
0x180069fb5  mov     rax, [rbp+0AE0h+arg_50]
0x180069fbc  xor     edi, edi
0x180069fbe  mov     [rbp+0AE0h+var_AF0], rax
0x180069fc2  mov     [rbp+0AE0h+var_B54], r9d
0x180069fc6  mov     [rbp+0AE0h+var_B00], rdx
0x180069fca  mov     [rbp+0AE0h+var_B08], r14
0x180069fce  mov     [rbp+0AE0h+var_B60], rsi
0x180069fd2  call    cs:__imp_RevertToPrinterSelf
0x180069fd8  mov     r8, [r12+20h]
0x180069fdd  lea     r9, aDrivers; "\\drivers\\"
0x180069fe4  mov     [rbp+0AE0h+hToken], rax
0x180069fe8  lea     rcx, [rbp+0AE0h+var_690]
0x180069fef  mov     rax, [r13+18h]
0x180069ff3  mov     edx, 0FFh
0x180069ff8  mov     [rsp+0BE0h+var_BA8], rsi
0x180069ffd  mov     [rsp+0BE0h+hTemplateFile], rax
0x18006a002  lea     rax, SubBlock; "\\"
0x18006a009  mov     qword ptr [rsp+0BE0h+dwFlagsAndAttributes], rax
0x18006a00e  mov     rax, [rbx+28h]
0x18006a012  mov     qword ptr [rsp+0BE0h+dwCreationDisposition], rax
0x18006a017  call    StrNCatBuff
0x18006a01c  test    eax, eax
0x18006a01e  jnz     loc_18006A3B3
0x18006a024  lea     rdx, [rbp+0AE0h+var_B60]
0x18006a028  lea     rcx, [rbp+0AE0h+var_690]
0x18006a02f  call    CreateNumberedTempDirectory
0x18006a034  mov     [rbp+0AE0h+var_B58], eax
0x18006a037  cmp     eax, 0FFFFFFFFh
0x18006a03a  jz      loc_18006A3AF
0x18006a040  lea     r9, [rbp+0AE0h+var_690]
0x18006a047  mov     edx, 109h; unsigned __int64
0x18006a04c  lea     r8, aWsNew; "%ws\\New"
0x18006a053  lea     rcx, [rbp+0AE0h+var_270]; unsigned __int16 *
0x18006a05a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006a05f  mov     rsi, [rbp+0AE0h+var_B60]
0x18006a063  xor     ebx, ebx
0x18006a065  test    r15d, r15d
0x18006a068  jz      loc_18006A2D2
0x18006a06e  mov     ecx, ebx
0x18006a070  shl     rcx, 5
0x18006a074  mov     rcx, [rcx+r14]
0x18006a078  call    FindFileName
0x18006a07d  lea     r9, SubBlock; "\\"
0x18006a084  mov     qword ptr [rsp+0BE0h+dwFlagsAndAttributes], rdi
0x18006a089  lea     r8, [rbp+0AE0h+var_270]
0x18006a090  mov     qword ptr [rsp+0BE0h+dwCreationDisposition], rax
0x18006a095  mov     edx, 104h
0x18006a09a  lea     rcx, [rbp+0AE0h+FileName]
0x18006a0a1  mov     r14, rax
0x18006a0a4  call    StrNCatBuff
0x18006a0a9  test    eax, eax
0x18006a0ab  jnz     loc_18006A3B3
0x18006a0b1  mov     qword ptr [rsp+0BE0h+dwFlagsAndAttributes], rdi
0x18006a0b6  lea     r9, SubBlock; "\\"
0x18006a0bd  lea     r8, [rbp+0AE0h+var_690]
0x18006a0c4  mov     qword ptr [rsp+0BE0h+dwCreationDisposition], r14
0x18006a0c9  mov     edx, 104h
0x18006a0ce  lea     rcx, [rbp+0AE0h+ExistingFileName]
0x18006a0d5  call    StrNCatBuff
0x18006a0da  test    eax, eax
0x18006a0dc  jnz     loc_18006A3B3
0x18006a0e2  mov     qword ptr [rsp+0BE0h+dwFlagsAndAttributes], rdi
0x18006a0e7  lea     r9, SubBlock; "\\"
0x18006a0ee  mov     r8, rsi
0x18006a0f1  mov     qword ptr [rsp+0BE0h+dwCreationDisposition], r14
0x18006a0f6  mov     edx, 104h
0x18006a0fb  lea     rcx, [rbp+0AE0h+NewFileName]
0x18006a0ff  call    StrNCatBuff
0x18006a104  test    eax, eax
0x18006a106  jnz     loc_18006A3B3
0x18006a10c  mov     [rsp+0BE0h+hTemplateFile], rdi; hTemplateFile
0x18006a111  lea     rcx, [rbp+0AE0h+FileName]; lpFileName
0x18006a118  mov     [rsp+0BE0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18006a120  xor     r9d, r9d; lpSecurityAttributes
0x18006a123  xor     r8d, r8d; dwShareMode
0x18006a126  mov     [rsp+0BE0h+dwCreationDisposition], 3; dwCreationDisposition
0x18006a12e  mov     edx, 80000000h; dwDesiredAccess
0x18006a133  call    cs:__imp_CreateFileW
0x18006a139  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006a13d  jnz     loc_18006A207
0x18006a143  xor     r8d, r8d; bFailIfExists
0x18006a146  lea     rdx, [rbp+0AE0h+NewFileName]; lpNewFileName
0x18006a14a  lea     rcx, [rbp+0AE0h+ExistingFileName]; lpExistingFileName
0x18006a151  call    cs:__imp_CopyFileW
0x18006a157  test    eax, eax
0x18006a159  jnz     loc_18006A2AF
0x18006a15f  call    cs:__imp_GetLastError
0x18006a165  lea     r9, [rbp+0AE0h+NewFileName]
0x18006a169  mov     [rsp+0BE0h+dwCreationDisposition], eax
0x18006a16d  lea     r8, [rbp+0AE0h+ExistingFileName]
0x18006a174  lea     rdx, aFailedToCopyWs; "Failed to copy '%ws' to '%ws'.  Error %"...
0x18006a17b  lea     rcx, aAddtempdriver_0; "AddTempDriver"
0x18006a182  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18006a187  mov     r14d, 4
0x18006a18d  mov     [rbp+0AE0h+var_B50], 6Ah ; 'j'
0x18006a194  mov     [rbp+0AE0h+var_B48], r14
0x18006a198  mov     [rbp+0AE0h+var_B40], edi
0x18006a19b  call    cs:__imp_GetLastError
0x18006a1a1  lea     rdx, [rbp+0AE0h+NewFileName]; unsigned __int16 *
0x18006a1a5  mov     [rbp+0AE0h+var_B30], r14
0x18006a1a9  lea     rcx, [rbp+0AE0h+var_AE0]; this
0x18006a1ad  mov     [rbp+0AE0h+var_B38], eax
0x18006a1b0  mov     [rbp+0AE0h+var_B28], edi
0x18006a1b3  mov     [rbp+0AE0h+var_B20], edi
0x18006a1b6  mov     [rbp+0AE0h+var_B18], r14
0x18006a1ba  mov     [rbp+0AE0h+var_B10], edi
0x18006a1bd  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x18006a1c2  lea     rdx, [rbp+0AE0h+ExistingFileName]; unsigned __int16 *
0x18006a1c9  mov     r10, rax
0x18006a1cc  lea     rcx, [rbp+0AE0h+var_AC8]; this
0x18006a1d0  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x18006a1d5  lea     r9, [rbp+0AE0h+var_B20]
0x18006a1d9  lea     rcx, [rbp+0AE0h+var_B50]
0x18006a1dd  mov     [rsp+0BE0h+hTemplateFile], rdi
0x18006a1e2  mov     r8, r10
0x18006a1e5  mov     qword ptr [rsp+0BE0h+dwFlagsAndAttributes], rcx
0x18006a1ea  mov     rdx, rax; struct SplLogType *
0x18006a1ed  lea     rcx, [rbp+0AE0h+var_B38]
0x18006a1f1  mov     qword ptr [rsp+0BE0h+dwCreationDisposition], rcx
0x18006a1f6  lea     rcx, SPOOLER_COPY_FILE_FAILED; struct _EVENT_DESCRIPTOR *
0x18006a1fd  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x18006a202  jmp     loc_18006A2B5
0x18006a207  mov     rcx, rax; hObject
0x18006a20a  call    cs:__imp_CloseHandle
0x18006a210  xor     r8d, r8d; bFailIfExists
0x18006a213  lea     rdx, [rbp+0AE0h+NewFileName]; lpNewFileName
0x18006a217  lea     rcx, [rbp+0AE0h+FileName]; lpExistingFileName
0x18006a21e  call    cs:__imp_CopyFileW
0x18006a224  test    eax, eax
0x18006a226  jnz     loc_18006A2AF
0x18006a22c  call    cs:__imp_GetLastError
0x18006a232  lea     r9, [rbp+0AE0h+NewFileName]
0x18006a236  mov     [rsp+0BE0h+dwCreationDisposition], eax
0x18006a23a  lea     r8, [rbp+0AE0h+FileName]
0x18006a241  lea     rdx, aFailedToCopyWs; "Failed to copy '%ws' to '%ws'.  Error %"...
0x18006a248  lea     rcx, aAddtempdriver_0; "AddTempDriver"
0x18006a24f  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18006a254  mov     r14d, 4
0x18006a25a  mov     [rbp+0AE0h+var_B20], 6Ah ; 'j'
0x18006a261  mov     [rbp+0AE0h+var_B18], r14
0x18006a265  mov     [rbp+0AE0h+var_B10], edi
0x18006a268  call    cs:__imp_GetLastError
0x18006a26e  lea     rdx, [rbp+0AE0h+NewFileName]; unsigned __int16 *
0x18006a272  mov     [rbp+0AE0h+var_B30], r14
0x18006a276  lea     rcx, [rbp+0AE0h+var_AC8]; this
0x18006a27a  mov     [rbp+0AE0h+var_B38], eax
0x18006a27d  mov     [rbp+0AE0h+var_B28], edi
0x18006a280  mov     [rbp+0AE0h+var_B50], edi
0x18006a283  mov     [rbp+0AE0h+var_B48], r14
0x18006a287  mov     [rbp+0AE0h+var_B40], edi
0x18006a28a  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x18006a28f  lea     rdx, [rbp+0AE0h+FileName]; unsigned __int16 *
0x18006a296  mov     r10, rax
0x18006a299  lea     rcx, [rbp+0AE0h+var_AE0]; this
0x18006a29d  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x18006a2a2  lea     r9, [rbp+0AE0h+var_B50]
0x18006a2a6  lea     rcx, [rbp+0AE0h+var_B20]
0x18006a2aa  jmp     loc_18006A1DD
0x18006a2af  mov     r14d, 4
0x18006a2b5  mov     r8d, r14d; dwFlags
0x18006a2b8  lea     rcx, [rbp+0AE0h+NewFileName]; unsigned __int16 *
0x18006a2bc  xor     edx, edx; unsigned __int16 *
0x18006a2be  call    SplMoveFileEx
0x18006a2c3  mov     r14, [rbp+0AE0h+var_B08]
0x18006a2c7  inc     ebx
0x18006a2c9  cmp     ebx, r15d
0x18006a2cc  jb      loc_18006A06E
0x18006a2d2  xor     edx, edx; unsigned __int16 *
0x18006a2d4  lea     rcx, [rbp+0AE0h+var_270]; unsigned __int16 *
0x18006a2db  lea     r8d, [rdx+4]; dwFlags
0x18006a2df  call    SplMoveFileEx
0x18006a2e4  mov     rdx, [rbp+0AE0h+var_B00]
0x18006a2e8  mov     r9, r14
0x18006a2eb  mov     r8, r13
0x18006a2ee  mov     [rsp+0BE0h+dwCreationDisposition], r15d
0x18006a2f3  mov     rcx, r12
0x18006a2f6  call    BuildTheMustForceUpdateDriverList
0x18006a2fb  mov     edi, [rbp+0AE0h+arg_48]
0x18006a301  mov     r8, r13; struct _INIVERSION *
0x18006a304  mov     r9, [rbp+0AE0h+var_AF0]; struct _INIDRIVER *
0x18006a308  mov     rcx, r12; struct _INISPOOLER *
0x18006a30b  mov     rdx, [rbp+0AE0h+var_B00]; struct _INIENVIRONMENT *
0x18006a30f  mov     [rbp+0AE0h+var_B60], rax
0x18006a313  lea     rax, [rbp+0AE0h+var_B60]
0x18006a317  mov     [rsp+0BE0h+var_B70], rax; struct _INIDRIVERTOUPDATE **
0x18006a31c  mov     eax, 1
0x18006a321  mov     [rsp+0BE0h+var_B78], eax; int
0x18006a325  mov     [rsp+0BE0h+var_B80], eax; int
0x18006a329  mov     eax, [rbp+0AE0h+var_B58]
0x18006a32c  mov     [rsp+0BE0h+var_B88], edi; int
0x18006a330  mov     [rsp+0BE0h+var_B90], eax; unsigned int
0x18006a334  mov     eax, [rbp+0AE0h+arg_28]
0x18006a33a  mov     [rsp+0BE0h+var_BA0], r15d; unsigned int
0x18006a33f  mov     r15, [rbp+0AE0h+var_AF8]
0x18006a343  mov     [rsp+0BE0h+var_BA8], r14; struct _INTERNAL_DRV_FILE *
0x18006a348  mov     r14d, [rbp+0AE0h+var_B54]
0x18006a34c  mov     dword ptr [rsp+0BE0h+hTemplateFile], eax; unsigned int
0x18006a350  mov     qword ptr [rsp+0BE0h+dwFlagsAndAttributes], r15; unsigned __int8 *
0x18006a355  mov     [rsp+0BE0h+dwCreationDisposition], r14d; unsigned int
0x18006a35a  call    ?CompleteDriverUpgrade@@YAHPEAU_INISPOOLER@@PEAU_INIENVIRONMENT@@PEAU_INIVERSION@@PEAU_INIDRIVER@@KPEAEKPEAU_INTERNAL_DRV_FILE@@KKKHHHPEAPEAU_INIDRIVERTOUPDATE@@@Z; CompleteDriverUpgrade(_INISPOOLER *,_INIENVIRONMENT *,_INIVERSION *,_INIDRIVER *,ulong,uchar *,ulong,_INTERNAL_DRV_FILE *,ulong,ulong,ulong,int,int,int,_INIDRIVERTOUPDATE * *)
0x18006a35f  mov     rbx, [rbp+0AE0h+var_B60]
0x18006a363  test    eax, eax
0x18006a365  jz      short loc_18006A39E
0x18006a367  mov     eax, [rbp+0AE0h+arg_40]
0x18006a36d  mov     r9, r15; unsigned __int8 *
0x18006a370  mov     rcx, [r12+18h]; unsigned __int16 *
0x18006a375  mov     r8d, r14d; unsigned int
0x18006a378  mov     edx, edi; unsigned int
0x18006a37a  mov     [rsp+0BE0h+dwCreationDisposition], eax; unsigned int
0x18006a37e  call    ?SaveParametersForUpgrade@@YAHPEAGHKPEAEK@Z; SaveParametersForUpgrade(ushort *,int,ulong,uchar *,ulong)
0x18006a383  test    eax, eax
0x18006a385  jz      short loc_18006A39E
0x18006a387  mov     edi, 1
0x18006a38c  test    rbx, rbx
0x18006a38f  jz      short loc_18006A3B3
0x18006a391  mov     r8, rbx
0x18006a394  mov     rdx, r13
0x18006a397  call    ForceDriverUpdateList
0x18006a39c  jmp     short loc_18006A3A0
0x18006a39e  xor     edi, edi
0x18006a3a0  test    rbx, rbx
0x18006a3a3  jz      short loc_18006A3B3
0x18006a3a5  mov     rcx, rbx
0x18006a3a8  call    FreeTheMustForceUpdateDriverList
0x18006a3ad  jmp     short loc_18006A3B3
0x18006a3af  mov     rsi, [rbp+0AE0h+var_B60]
0x18006a3b3  mov     rax, [rbp+0AE0h+hToken]
0x18006a3b7  test    rax, rax
0x18006a3ba  jz      short loc_18006A3C5
0x18006a3bc  mov     rcx, rax; hToken
0x18006a3bf  call    cs:__imp_ImpersonatePrinterClient
0x18006a3c5  mov     rcx, rsi
0x18006a3c8  call    cs:__imp_DllFreeSplMem
0x18006a3ce  test    edi, edi
0x18006a3d0  jnz     short loc_18006A3EE
0x18006a3d2  call    cs:__imp_GetLastError
0x18006a3d8  mov     r8d, eax
0x18006a3db  lea     rdx, aFailingAddtemp; "Failing AddTempDriver call.  Error %d"
0x18006a3e2  lea     rcx, aAddtempdriver_0; "AddTempDriver"
0x18006a3e9  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18006a3ee  mov     eax, edi
0x18006a3f0  mov     rcx, [rbp+0AE0h+var_50]
0x18006a3f7  xor     rcx, rsp; StackCookie
0x18006a3fa  call    __security_check_cookie
0x18006a3ff  add     rsp, 0BA8h
0x18006a406  pop     r15
0x18006a408  pop     r14
0x18006a40a  pop     r13
0x18006a40c  pop     r12
0x18006a40e  pop     rdi
0x18006a40f  pop     rsi
0x18006a410  pop     rbx
0x18006a411  pop     rbp
0x18006a412  retn
```
