# _lambda_128d4af0a342142bcd51ecbc6f3bae9e_::operator()

- ea: `0x180075f58`
- end: `0x1800767a8`
- name: `_lambda_128d4af0a342142bcd51ecbc6f3bae9e_::operator()`
- size: `2128`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18007579c`

## callees

- `0x1800073fc`
- `0x180008520`
- `0x180008560`
- `0x1800085ac`
- `0x1800086e0`
- `0x180008730`
- `0x18000d988`
- `0x18000edc4`
- `0x18000ef18`
- `0x180011f00`
- `0x18001224c`
- `0x180013c90`
- `0x180019404`
- `0x180029dd8`
- `0x18002d680`
- `0x18002f6a0`
- `0x1800345c0`
- `0x180034b98`
- `0x1800353b0`
- `0x180035ae4`
- `0x18003e984`
- `0x18003ea2c`
- `0x180041878`
- `0x180041e0c`
- `0x1800430b8`
- `0x180046650`
- `0x180047330`
- `0x18004d8d0`
- `0x180075f58`
- `0x180078b74`
- `0x18007b3d4`
- `0x18007b890`
- `0x18007bd7c`
- `0x180095a40`
- `0x180097b48`
- `0x1800a4f0c`
- `0x1800c03e4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800763c7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800763c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007670f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076777`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007670f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076777`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180075fd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180075fd0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007614c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180076195`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007614c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180076195`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180076279`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180076279`
- `SPOOLSS!DllAllocSplMem` at `0x180076088`
- `SPOOLSS!DllAllocSplMem` at `0x1800762b9`
- `SPOOLSS!DllAllocSplMem` at `0x180076088`
- `SPOOLSS!DllAllocSplMem` at `0x1800762b9`
- `SPOOLSS!RevertToPrinterSelf` at `0x180075fa4`
- `SPOOLSS!RevertToPrinterSelf` at `0x180075fa4`
- `SPOOLSS!AllocSplStr` at `0x180076212`
- `SPOOLSS!AllocSplStr` at `0x180076245`
- `SPOOLSS!AllocSplStr` at `0x180076381`
- `SPOOLSS!AllocSplStr` at `0x1800763d2`
- `SPOOLSS!AllocSplStr` at `0x180076436`
- `SPOOLSS!AllocSplStr` at `0x180076454`
- `SPOOLSS!AllocSplStr` at `0x18007647b`
- `SPOOLSS!AllocSplStr` at `0x180076490`
- `SPOOLSS!AllocSplStr` at `0x1800764a5`
- `SPOOLSS!AllocSplStr` at `0x1800764bd`
- `SPOOLSS!AllocSplStr` at `0x1800764f2`
- `SPOOLSS!AllocSplStr` at `0x180076212`
- `SPOOLSS!AllocSplStr` at `0x180076245`
- `SPOOLSS!AllocSplStr` at `0x180076381`
- `SPOOLSS!AllocSplStr` at `0x1800763d2`
- `SPOOLSS!AllocSplStr` at `0x180076436`
- `SPOOLSS!AllocSplStr` at `0x180076454`
- `SPOOLSS!AllocSplStr` at `0x18007647b`
- `SPOOLSS!AllocSplStr` at `0x180076490`
- `SPOOLSS!AllocSplStr` at `0x1800764a5`
- `SPOOLSS!AllocSplStr` at `0x1800764bd`
- `SPOOLSS!AllocSplStr` at `0x1800764f2`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180076731`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180076731`

## string_xrefs

- `0x180075f88`: `SplCreateSpooler::<lambda_128d4af0a342142bcd51ecbc6f3bae9e>::operator ()`
- `0x18007661e`: `pThisEnvironment is not set after initial BuildEnvironmentInfo attempt!`
- `0x180076685`: `Failed to create INISPOOOLER strings`

## pseudocode

```c
_QWORD *__fastcall lambda_128d4af0a342142bcd51ecbc6f3bae9e_::operator()(const unsigned __int16 ***a1)
{
  HANDLE v2; // r15
  __int64 v3; // rbx
  DWORD v4; // ecx
  struct _INISPOOLER *v5; // rcx
  const unsigned __int16 **v6; // rax
  __int64 Spooler; // rax
  __int64 v8; // rax
  const unsigned __int16 **v9; // rax
  LSTATUS Key; // eax
  __int64 v11; // rdx
  signed __int32 v12; // eax
  __int64 v13; // rax
  const unsigned __int16 **v14; // r14
  __int64 v15; // rcx
  const unsigned __int16 *v16; // rax
  UINT SystemDirectoryW; // eax
  __int64 v18; // r9
  _QWORD *v19; // rax
  __int64 DriversShareSecurityDescriptor; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  _QWORD *v23; // rax
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r9
  __int64 v29; // rax
  bool v30; // zf
  int v31; // eax
  unsigned __int8 v32; // al
  _QWORD *v33; // rsi
  __int64 v34; // rcx
  const unsigned __int16 *v35; // rbx
  DWORD LastError; // eax
  _QWORD *result; // rax
  DWORD v38; // eax
  const char *v39; // r9
  DWORD dwDisposition[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v42[256]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  LocalSpoolerTelemetry::WriteDbgTraceInfo(
    "SplCreateSpooler::<lambda_128d4af0a342142bcd51ecbc6f3bae9e>::operator ()",
    L"Entering %ws",
    **a1);
  v2 = RevertToPrinterSelf();
  if ( !v2 )
  {
    v33 = a1 + 2;
    goto LABEL_74;
  }
  v3 = 0;
  EnterSplSem(0);
  if ( !**a1 )
  {
    v4 = 123;
LABEL_4:
    SetLastError(v4);
    goto LABEL_65;
  }
  v6 = a1[1];
  if ( (*((_DWORD *)*v6 + 22) & 0x1020000) != 0 && BackupPrintersToSystemHive(*((LPCWSTR *)*v6 + 3)) )
  {
    StringCchPrintfW(v42, 0x100u, L"%x", 1);
    SplLogEvent(&MSG_BACKUP_SPOOLER_REGISTRY, 1u, v42, 0);
  }
  if ( pLocalIniSpooler )
  {
    Spooler = FindSpooler(**a1);
    v3 = Spooler;
    if ( (*((_DWORD *)*a1[1] + 22) & 0x80000) != 0 && !Spooler )
    {
      v4 = 2;
      goto LABEL_4;
    }
  }
  *((_DWORD *)*a1[1] + 22) &= ~0x80000u;
  if ( v3 )
  {
    SafeIncrementReference((unsigned int *)(v3 + 16));
LABEL_62:
    if ( (*(_DWORD *)(v3 + 168) & 0x20000) != 0 )
      InitializeDS((struct _INISPOOLER *)v3);
    *a1[2] = (const unsigned __int16 *)v3;
    goto LABEL_65;
  }
  v8 = DllAllocSplMem(65936);
  v3 = v8;
  if ( !v8 )
    goto LABEL_65;
  memset_0((void *)(v8 + 392), 0, 0x8000u);
  memset_0((void *)(v3 + 33160), 0, 0x8000u);
  *(_DWORD *)v3 = 1230196812;
  SafeIncrementReference((unsigned int *)(v3 + 16));
  *(_QWORD *)(v3 + 336) = 0;
  *(_QWORD *)(v3 + 344) = 0;
  *(_QWORD *)(v3 + 352) = 0;
  *(_QWORD *)(v3 + 360) = 0;
  *(_QWORD *)(v3 + 368) = 0;
  *(_DWORD *)(v3 + 168) = *((_DWORD *)*a1[1] + 22);
  v9 = a1[1];
  dwDisposition[0] = 0;
  Key = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          *((LPCWSTR *)*v9 + 2),
          0,
          0,
          0,
          0x3001Fu,
          0,
          (PHKEY)(v3 + 232),
          dwDisposition);
  if ( Key
    || (Key = RegCreateKeyExW(
                HKEY_LOCAL_MACHINE,
                *((LPCWSTR *)*a1[1] + 3),
                0,
                0,
                0,
                0x3001Fu,
                0,
                (PHKEY)(v3 + 240),
                dwDisposition)) != 0 )
  {
    v4 = Key;
    goto LABEL_4;
  }
  if ( (*((_DWORD *)*a1[1] + 22) & 0x4000000) != 0 )
  {
    v11 = *((_QWORD *)pLocalIniSpooler + 46);
    *(_QWORD *)(v3 + 368) = v11;
    do
      v12 = *(_DWORD *)(v11 + 8);
    while ( v12 != 0x7FFFFFFF && v12 != _InterlockedCompareExchange((volatile signed __int32 *)(v11 + 8), v12 + 1, v12) );
  }
  else if ( !(unsigned int)CreateSpoolerSandboxManager((struct _INISPOOLER *)v3) )
  {
    goto LABEL_65;
  }
  if ( (int)BindIniSpoolerWrapper((struct _INISPOOLER *)v3) >= 0 )
  {
    *(_QWORD *)(v3 + 264) = hCreateJobIdMap((unsigned int)v5);
    v13 = AllocSplStr(**a1);
    *(_QWORD *)(v3 + 24) = v13;
    if ( v13 )
    {
      if ( *(_QWORD *)(v3 + 264) )
      {
        v14 = (const unsigned __int16 **)(v3 + 32);
        v15 = *(_QWORD *)*a1[1];
        if ( v15 )
        {
          v16 = (const unsigned __int16 *)AllocSplStr(v15);
          *v14 = v16;
          if ( !v16 )
            goto LABEL_65;
          StringCchCopyW(Buffer, 0x104u, v16);
        }
        else
        {
          SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
          StringCchCopyW(&Buffer[SystemDirectoryW], 260LL - SystemDirectoryW, L"\\spool");
          StrCatAlloc(v3 + 32, Buffer, 0, v18);
          if ( !*v14 )
            goto LABEL_65;
        }
        v19 = (_QWORD *)DllAllocSplMem(80);
        *(_QWORD *)(v3 + 144) = v19;
        if ( v19 )
        {
          *v19 = 0;
          *(_DWORD *)(*(_QWORD *)(v3 + 144) + 8LL) = 0;
          *(_QWORD *)(*(_QWORD *)(v3 + 144) + 16LL) = 0;
          *(_DWORD *)(*(_QWORD *)(v3 + 144) + 24LL) = 0;
          *(_DWORD *)(*(_QWORD *)(v3 + 144) + 28LL) = -1;
          *(_DWORD *)(*(_QWORD *)(v3 + 144) + 32LL) = -1;
          *(_QWORD *)(*(_QWORD *)(v3 + 144) + 40LL) = 0;
          *(_QWORD *)(*(_QWORD *)(v3 + 144) + 48LL) = 0;
          DriversShareSecurityDescriptor = CreateDriversShareSecurityDescriptor();
          v5 = *(struct _INISPOOLER **)(v3 + 144);
          *((_QWORD *)v5 + 9) = DriversShareSecurityDescriptor;
          *(_QWORD *)(*(_QWORD *)(v3 + 144) + 56LL) = 0;
          if ( *(_QWORD *)(*(_QWORD *)(v3 + 144) + 72LL) )
          {
            v21 = -1;
            do
              ++v21;
            while ( Buffer[v21] );
            StringCchCopyW(&Buffer[(unsigned int)v21], 260LL - (unsigned int)v21, L"\\drivers");
            v22 = AllocSplStr(Buffer);
            v5 = *(struct _INISPOOLER **)(v3 + 144);
            *((_QWORD *)v5 + 5) = v22;
            v23 = *(_QWORD **)(v3 + 144);
            if ( v23[5] )
            {
              *v23 = L"print$";
              Buffer[0] = 0;
              LoadStringW(hInst, 0x68u, Buffer, 260);
              v24 = AllocSplStr(Buffer);
              v5 = *(struct _INISPOOLER **)(v3 + 144);
              *((_QWORD *)v5 + 2) = v24;
              if ( *(_QWORD *)(*(_QWORD *)(v3 + 144) + 16LL) )
              {
                *(_QWORD *)(v3 + 40) = 0;
                *(_DWORD *)(v3 + 288) = 1;
                *(_QWORD *)(v3 + 48) = 0;
                *(_QWORD *)(v3 + 80) = 0;
                *(_DWORD *)(v3 + 312) = 0;
                *(_QWORD *)(v3 + 88) = 0;
                *(_QWORD *)(v3 + 96) = 0;
                *(_DWORD *)(v3 + 284) = 600;
                v25 = *((_QWORD *)*a1[1] + 1);
                if ( !v25 || (v26 = AllocSplStr(v25), (*(_QWORD *)(v3 + 96) = v26) != 0) )
                {
                  *(_QWORD *)(v3 + 104) = AllocSplStr(*((_QWORD *)*a1[1] + 4));
                  if ( pLocalIniSpooler )
                    v27 = *((_QWORD *)pLocalIniSpooler + 14);
                  else
                    v27 = *((_QWORD *)*a1[1] + 5);
                  *(_QWORD *)(v3 + 112) = AllocSplStr(v27);
                  *(_QWORD *)(v3 + 120) = AllocSplStr(*((_QWORD *)*a1[1] + 6));
                  *(_QWORD *)(v3 + 128) = AllocSplStr(*((_QWORD *)*a1[1] + 7));
                  *(_QWORD *)(v3 + 136) = AllocSplStr(*((_QWORD *)*a1[1] + 8));
                  StrCatAlloc(v3 + 152, *((_QWORD *)*a1[1] + 9), 0, v28);
                  v29 = AllocSplStr(*((_QWORD *)*a1[1] + 10));
                  *(_QWORD *)(v3 + 160) = v29;
                  *(_QWORD *)(v3 + 304) = -1;
                  if ( !*(_QWORD *)(v3 + 104)
                    || !*(_QWORD *)(v3 + 112)
                    || !*(_QWORD *)(v3 + 120)
                    || !*(_QWORD *)(v3 + 128)
                    || !*(_QWORD *)(v3 + 136)
                    || !*(_QWORD *)(v3 + 152)
                    || !v29 )
                  {
                    LocalSpoolerTelemetry::WriteDbgTraceError(
                      "SplCreateSpooler::<lambda_128d4af0a342142bcd51ecbc6f3bae9e>::operator ()",
                      L"Failed to create INISPOOOLER strings");
                    goto LABEL_65;
                  }
                  v30 = pLocalIniSpooler == 0;
                  *(_QWORD *)(v3 + 72) = 0;
                  *(_QWORD *)(v3 + 176) = *((_QWORD *)*a1[1] + 12);
                  *(_QWORD *)(v3 + 184) = *((_QWORD *)*a1[1] + 13);
                  *(_QWORD *)(v3 + 192) = *((_QWORD *)*a1[1] + 14);
                  if ( v30 )
                  {
                    pLocalIniSpooler = (struct _INISPOOLER *)v3;
                    *(_QWORD *)(v3 + 8) = 0;
                  }
                  QueryServicePackUpgradeFlag();
                  QueryGMTAdjustedForDSTFlag(v3);
                  if ( (unsigned int)InitializeSpoolerSecurityDescriptor((struct _INISPOOLER *)v3) )
                  {
                    v31 = ServerSku();
                    CreateAndUpdateFormValidatorInstance(v3, 1, v31 == 0 ? 0x3E8 : 0);
                    BuildAllPorts((struct _INISPOOLER *)v3);
                    InitializeSpoolerSettings((struct _INISPOOLER *)v3);
                    g_hrCommonPathInitErrorCode = InitCommonPaths();
                    if ( (struct _INISPOOLER *)v3 == pLocalIniSpooler )
                    {
                      GetPrintSystemVersion((struct _INISPOOLER *)v3);
                      BuildEnvironmentInfo((struct _INISPOOLER *)v3);
                      if ( !pThisEnvironment )
                      {
                        LocalSpoolerTelemetry::WriteDbgTraceError(
                          "SplCreateSpooler::<lambda_128d4af0a342142bcd51ecbc6f3bae9e>::operator ()",
                          L"pThisEnvironment is not set after initial BuildEnvironmentInfo attempt!");
                        LocalSpoolerTelemetry::LogEnvironmentError(0);
                      }
                      if ( (unsigned __int8)IsSystemCurrentlyUpgrading() )
                      {
                        InitializeForms((struct _INISPOOLER *)v3);
                        UpgradeForms((struct _INISPOOLER *)v3);
                      }
                    }
                    else
                    {
                      *(_QWORD *)(v3 + 48) = *((_QWORD *)pLocalIniSpooler + 6);
                    }
                    v32 = IsSystemCurrentlyUpgrading();
                    if ( (unsigned int)BuildPrinterInfo((struct _INISPOOLER *)v3, v32) )
                    {
                      v5 = pLocalIniSpooler;
                      if ( pLocalIniSpooler != (struct _INISPOOLER *)v3 )
                      {
                        *(_QWORD *)(v3 + 8) = *((_QWORD *)pLocalIniSpooler + 1);
                        *((_QWORD *)v5 + 1) = v3;
                      }
                      goto LABEL_62;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_65:
  v33 = a1 + 2;
  if ( *a1[2] == (const unsigned __int16 *)-1LL && v3 )
  {
    if ( *(_DWORD *)(v3 + 16) )
      SafeDecrementReference((unsigned int *)(v3 + 16));
    DeleteSpoolerCheck(v3);
    LeaveSplSem(v34);
    goto LABEL_75;
  }
  LeaveSplSem(v5);
  if ( !v3 && (*((_DWORD *)*a1[1] + 22) & 0x80000) == 0 )
  {
LABEL_74:
    v35 = **a1;
    LastError = GetLastError();
    SplLogEvent(&MSG_SPOOLER_CREATION_FAILED, LastError, v35, 0);
    if ( !v2 )
      goto LABEL_76;
  }
LABEL_75:
  ImpersonatePrinterClient(v2);
LABEL_76:
  LocalSpoolerTelemetry::WriteDbgTraceInfo(
    "SplCreateSpooler::<lambda_128d4af0a342142bcd51ecbc6f3bae9e>::operator ()",
    L"Leaving %ws",
    **a1);
  result = (_QWORD *)*v33;
  if ( !*(_QWORD *)*v33 )
  {
    v38 = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "SplCreateSpooler::<lambda_128d4af0a342142bcd51ecbc6f3bae9e>::operator ()",
      L"Failed with error code %d",
      v38);
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x8CE,
      (unsigned int)"printscan\\print\\spooler\\localspl\\init.c",
      v39);
  }
  return result;
}

```

## disassembly

```asm
0x180075f58  push    rbp
0x180075f5a  push    rbx
0x180075f5b  push    rsi
0x180075f5c  push    rdi
0x180075f5d  push    r12
0x180075f5f  push    r13
0x180075f61  push    r14
0x180075f63  push    r15
0x180075f65  lea     rbp, [rsp-388h]
0x180075f6d  sub     rsp, 488h
0x180075f74  mov     rax, cs:__security_cookie
0x180075f7b  xor     rax, rsp
0x180075f7e  mov     [rbp+3C0h+var_50], rax
0x180075f85  mov     r8, [rcx]
0x180075f88  lea     r13, aSplcreatespool_1; "SplCreateSpooler::<lambda_128d4af0a3421"...
0x180075f8f  mov     rdi, rcx
0x180075f92  lea     rdx, aEnteringWs; "Entering %ws"
0x180075f99  mov     rcx, r13; char *
0x180075f9c  mov     r8, [r8]
0x180075f9f  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180075fa4  call    cs:__imp_RevertToPrinterSelf
0x180075faa  xor     r12d, r12d
0x180075fad  mov     r15, rax
0x180075fb0  test    rax, rax
0x180075fb3  jz      loc_180076705
0x180075fb9  xor     ecx, ecx
0x180075fbb  mov     ebx, r12d
0x180075fbe  call    EnterSplSem
0x180075fc3  mov     rcx, [rdi]
0x180075fc6  cmp     [rcx], r12
0x180075fc9  jnz     short loc_180075FDB
0x180075fcb  lea     ecx, [r12+7Bh]; dwErrCode
0x180075fd0  call    cs:__imp_SetLastError
0x180075fd6  jmp     loc_1800766BA
0x180075fdb  mov     rax, [rdi+8]
0x180075fdf  mov     esi, 1
0x180075fe4  mov     rcx, [rax]
0x180075fe7  test    dword ptr [rcx+58h], 1020000h
0x180075fee  jz      short loc_180076030
0x180075ff0  mov     rcx, [rcx+18h]; lpSubKey
0x180075ff4  call    ?BackupPrintersToSystemHive@@YAKPEAG@Z; BackupPrintersToSystemHive(ushort *)
0x180075ff9  test    eax, eax
0x180075ffb  jz      short loc_180076030
0x180075ffd  mov     r9d, esi
0x180076000  lea     r8, Format; "%x"
0x180076007  mov     edx, 100h; unsigned __int64
0x18007600c  lea     rcx, [rbp+3C0h+var_250]; unsigned __int16 *
0x180076013  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180076018  xor     r9d, r9d
0x18007601b  lea     r8, [rbp+3C0h+var_250]; unsigned __int16 *
0x180076022  mov     edx, esi; unsigned int
0x180076024  lea     rcx, MSG_BACKUP_SPOOLER_REGISTRY; struct _EVENT_DESCRIPTOR *
0x18007602b  call    ?SplLogEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBGZZ; SplLogEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *,...)
0x180076030  cmp     cs:pLocalIniSpooler, r12
0x180076037  jz      short loc_18007606E
0x180076039  mov     rax, [rdi+8]
0x18007603d  mov     rcx, [rdi]
0x180076040  mov     rdx, [rax]
0x180076043  mov     rcx, [rcx]; lpString1
0x180076046  mov     edx, [rdx+58h]
0x180076049  call    FindSpooler
0x18007604e  mov     rcx, [rdi+8]
0x180076052  mov     rbx, rax
0x180076055  mov     rdx, [rcx]
0x180076058  test    dword ptr [rdx+58h], 80000h
0x18007605f  jz      short loc_18007606E
0x180076061  test    rax, rax
0x180076064  jnz     short loc_18007606E
0x180076066  lea     ecx, [rax+2]
0x180076069  jmp     loc_180075FD0
0x18007606e  mov     rax, [rdi+8]
0x180076072  mov     rcx, [rax]
0x180076075  btr     dword ptr [rcx+58h], 13h
0x18007607a  test    rbx, rbx
0x18007607d  jnz     loc_180076696
0x180076083  mov     ecx, 10190h
0x180076088  call    cs:__imp_DllAllocSplMem
0x18007608e  mov     rbx, rax
0x180076091  test    rax, rax
0x180076094  jz      loc_1800766BA
0x18007609a  mov     esi, 8000h
0x18007609f  lea     rcx, [rax+188h]; void *
0x1800760a6  mov     r8d, esi; Size
0x1800760a9  xor     edx, edx; Val
0x1800760ab  call    memset_0
0x1800760b0  lea     rcx, [rbx+8188h]; void *
0x1800760b7  mov     r8d, esi; Size
0x1800760ba  xor     edx, edx; Val
0x1800760bc  call    memset_0
0x1800760c1  lea     rcx, [rbx+10h]; unsigned int *
0x1800760c5  mov     dword ptr [rbx], 4953504Ch
0x1800760cb  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x1800760d0  mov     [rbx+150h], r12
0x1800760d7  mov     esi, 3001Fh
0x1800760dc  mov     [rbx+158h], r12
0x1800760e3  mov     r14, 0FFFFFFFF80000002h
0x1800760ea  mov     [rbx+160h], r12
0x1800760f1  xor     r9d, r9d; lpClass
0x1800760f4  mov     [rbx+168h], r12
0x1800760fb  xor     r8d, r8d; Reserved
0x1800760fe  mov     [rbx+170h], r12
0x180076105  mov     rax, [rdi+8]
0x180076109  mov     rcx, [rax]
0x18007610c  mov     eax, [rcx+58h]
0x18007610f  lea     rcx, [rbx+0E8h]
0x180076116  mov     [rbx+0A8h], eax
0x18007611c  mov     rax, [rdi+8]
0x180076120  mov     [rsp+4C0h+dwDisposition], r12d
0x180076125  mov     rdx, [rax]
0x180076128  lea     rax, [rsp+4C0h+dwDisposition]
0x18007612d  mov     [rsp+4C0h+lpdwDisposition], rax; lpdwDisposition
0x180076132  mov     [rsp+4C0h+phkResult], rcx; phkResult
0x180076137  mov     rcx, r14; hKey
0x18007613a  mov     [rsp+4C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18007613f  mov     rdx, [rdx+10h]; lpSubKey
0x180076143  mov     [rsp+4C0h+samDesired], esi; samDesired
0x180076147  mov     [rsp+4C0h+dwOptions], r12d; dwOptions
0x18007614c  call    cs:__imp_RegCreateKeyExW
0x180076152  test    eax, eax
0x180076154  jz      short loc_18007615D
0x180076156  mov     ecx, eax
0x180076158  jmp     loc_180075FD0
0x18007615d  mov     rax, [rdi+8]
0x180076161  lea     r8, [rbx+0F0h]
0x180076168  xor     r9d, r9d; lpClass
0x18007616b  mov     rcx, r14; hKey
0x18007616e  mov     rdx, [rax]
0x180076171  lea     rax, [rsp+4C0h+dwDisposition]
0x180076176  mov     [rsp+4C0h+lpdwDisposition], rax; lpdwDisposition
0x18007617b  mov     [rsp+4C0h+phkResult], r8; phkResult
0x180076180  xor     r8d, r8d; Reserved
0x180076183  mov     [rsp+4C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180076188  mov     rdx, [rdx+18h]; lpSubKey
0x18007618c  mov     [rsp+4C0h+samDesired], esi; samDesired
0x180076190  mov     [rsp+4C0h+dwOptions], r12d; dwOptions
0x180076195  call    cs:__imp_RegCreateKeyExW
0x18007619b  test    eax, eax
0x18007619d  jnz     short loc_180076156
0x18007619f  mov     rax, [rdi+8]
0x1800761a3  mov     rcx, [rax]
0x1800761a6  test    dword ptr [rcx+58h], 4000000h
0x1800761ad  jz      short loc_1800761E0
0x1800761af  mov     rax, cs:pLocalIniSpooler
0x1800761b6  mov     r8d, 7FFFFFFFh
0x1800761bc  mov     rdx, [rax+170h]
0x1800761c3  mov     [rbx+170h], rdx
0x1800761ca  jmp     short loc_1800761D6
0x1800761cc  lea     ecx, [rax+1]
0x1800761cf  lock cmpxchg [rdx+8], ecx
0x1800761d4  jz      short loc_1800761F0
0x1800761d6  mov     eax, [rdx+8]
0x1800761d9  cmp     eax, r8d
0x1800761dc  jnz     short loc_1800761CC
0x1800761de  jmp     short loc_1800761F0
0x1800761e0  mov     rcx, rbx; struct _INISPOOLER *
0x1800761e3  call    ?CreateSpoolerSandboxManager@@YAHPEAU_INISPOOLER@@@Z; CreateSpoolerSandboxManager(_INISPOOLER *)
0x1800761e8  test    eax, eax
0x1800761ea  jz      loc_1800766BA
0x1800761f0  mov     rcx, rbx; struct _INISPOOLER *
0x1800761f3  call    BindIniSpoolerWrapper
0x1800761f8  test    eax, eax
0x1800761fa  js      loc_1800766BA
0x180076200  call    ?hCreateJobIdMap@@YAPEAXK@Z; hCreateJobIdMap(ulong)
0x180076205  mov     [rbx+108h], rax
0x18007620c  mov     rcx, [rdi]
0x18007620f  mov     rcx, [rcx]
0x180076212  call    cs:__imp_AllocSplStr
0x180076218  mov     [rbx+18h], rax
0x18007621c  test    rax, rax
0x18007621f  jz      loc_1800766BA
0x180076225  cmp     [rbx+108h], r12
0x18007622c  jz      loc_1800766BA
0x180076232  mov     rax, [rdi+8]
0x180076236  lea     r14, [rbx+20h]
0x18007623a  mov     rcx, [rax]
0x18007623d  mov     rcx, [rcx]
0x180076240  test    rcx, rcx
0x180076243  jz      short loc_18007626D
0x180076245  call    cs:__imp_AllocSplStr
0x18007624b  mov     [r14], rax
0x18007624e  test    rax, rax
0x180076251  jz      loc_1800766BA
0x180076257  mov     esi, 104h
0x18007625c  lea     rcx, [rsp+4C0h+Buffer]; unsigned __int16 *
0x180076261  mov     edx, esi; unsigned __int64
0x180076263  mov     r8, rax; unsigned __int16 *
0x180076266  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007626b  jmp     short loc_1800762B4
0x18007626d  mov     esi, 104h
0x180076272  lea     rcx, [rsp+4C0h+Buffer]; lpBuffer
0x180076277  mov     edx, esi; uSize
0x180076279  call    cs:__imp_GetSystemDirectoryW
0x18007627f  mov     eax, eax
0x180076281  mov     edx, esi
0x180076283  lea     rcx, [rsp+4C0h+Buffer]
0x180076288  sub     rdx, rax; unsigned __int64
0x18007628b  lea     r8, aSpool; "\\spool"
0x180076292  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x180076296  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007629b  xor     r8d, r8d
0x18007629e  lea     rdx, [rsp+4C0h+Buffer]
0x1800762a3  mov     rcx, r14
0x1800762a6  call    StrCatAlloc
0x1800762ab  cmp     [r14], r12
0x1800762ae  jz      loc_1800766BA
0x1800762b4  mov     ecx, 50h ; 'P'
0x1800762b9  call    cs:__imp_DllAllocSplMem
0x1800762bf  mov     [rbx+90h], rax
0x1800762c6  test    rax, rax
0x1800762c9  jz      loc_1800766BA
0x1800762cf  mov     [rax], r12
0x1800762d2  or      ecx, 0FFFFFFFFh
0x1800762d5  mov     rax, [rbx+90h]
0x1800762dc  mov     [rax+8], r12d
0x1800762e0  mov     rax, [rbx+90h]
0x1800762e7  mov     [rax+10h], r12
0x1800762eb  mov     rax, [rbx+90h]
0x1800762f2  mov     [rax+18h], r12d
0x1800762f6  mov     rax, [rbx+90h]
0x1800762fd  mov     [rax+1Ch], ecx
0x180076300  mov     rax, [rbx+90h]
0x180076307  mov     [rax+20h], ecx
0x18007630a  mov     rax, [rbx+90h]
0x180076311  mov     [rax+28h], r12
0x180076315  mov     rax, [rbx+90h]
0x18007631c  mov     [rax+30h], r12
0x180076320  call    ?CreateDriversShareSecurityDescriptor@@YAPEAXXZ; CreateDriversShareSecurityDescriptor(void)
0x180076325  mov     rcx, [rbx+90h]
0x18007632c  mov     [rcx+48h], rax
0x180076330  mov     rax, [rbx+90h]
0x180076337  mov     [rax+38h], r12
0x18007633b  mov     rax, [rbx+90h]
0x180076342  cmp     [rax+48h], r12
0x180076346  jz      loc_1800766BA
0x18007634c  lea     rcx, [rsp+4C0h+Buffer]
0x180076351  or      rax, 0FFFFFFFFFFFFFFFFh
0x180076355  inc     rax
0x180076358  cmp     [rcx+rax*2], r12w
0x18007635d  jnz     short loc_180076355
0x18007635f  mov     eax, eax
0x180076361  lea     rcx, [rsp+4C0h+Buffer]
0x180076366  mov     rdx, rsi
0x180076369  lea     r8, szDriversDirectory; "\\drivers"
0x180076370  sub     rdx, rax; unsigned __int64
0x180076373  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x180076377  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007637c  lea     rcx, [rsp+4C0h+Buffer]
0x180076381  call    cs:__imp_AllocSplStr
0x180076387  mov     rcx, [rbx+90h]
0x18007638e  mov     [rcx+28h], rax
0x180076392  mov     rax, [rbx+90h]
0x180076399  cmp     [rax+28h], r12
0x18007639d  jz      loc_1800766BA
0x1800763a3  lea     rcx, ipszDriversShareName; "print$"
0x1800763aa  mov     r9d, esi; cchBufferMax
0x1800763ad  mov     [rax], rcx
0x1800763b0  lea     r8, [rsp+4C0h+Buffer]; lpBuffer
0x1800763b5  mov     rcx, cs:hInst; hInstance
0x1800763bc  mov     edx, 68h ; 'h'; uID
0x1800763c1  mov     [rsp+4C0h+Buffer], r12w
0x1800763c7  call    cs:__imp_LoadStringW
0x1800763cd  lea     rcx, [rsp+4C0h+Buffer]
0x1800763d2  call    cs:__imp_AllocSplStr
0x1800763d8  mov     rcx, [rbx+90h]
0x1800763df  mov     [rcx+10h], rax
0x1800763e3  mov     rax, [rbx+90h]
0x1800763ea  cmp     [rax+10h], r12
0x1800763ee  jz      loc_1800766BA
0x1800763f4  mov     [rbx+28h], r12
0x1800763f8  mov     r14d, 1
0x1800763fe  mov     [rbx+120h], r14d
0x180076405  mov     [rbx+30h], r12
0x180076409  mov     [rbx+50h], r12
0x18007640d  mov     [rbx+138h], r12d
0x180076414  mov     [rbx+58h], r12
0x180076418  mov     [rbx+60h], r12
0x18007641c  mov     dword ptr [rbx+11Ch], 258h
0x180076426  mov     rax, [rdi+8]
0x18007642a  mov     rcx, [rax]
0x18007642d  mov     rcx, [rcx+8]
0x180076431  test    rcx, rcx
0x180076434  jz      short loc_180076449
0x180076436  call    cs:__imp_AllocSplStr
0x18007643c  mov     [rbx+60h], rax
0x180076440  test    rax, rax
0x180076443  jz      loc_1800766BA
0x180076449  mov     rax, [rdi+8]
0x18007644d  mov     rcx, [rax]
0x180076450  mov     rcx, [rcx+20h]
0x180076454  call    cs:__imp_AllocSplStr
0x18007645a  mov     [rbx+68h], rax
0x18007645e  mov     rax, cs:pLocalIniSpooler
0x180076465  test    rax, rax
0x180076468  jnz     short loc_180076477
0x18007646a  mov     rax, [rdi+8]
0x18007646e  mov     rcx, [rax]
0x180076471  mov     rcx, [rcx+28h]
0x180076475  jmp     short loc_18007647B
0x180076477  mov     rcx, [rax+70h]
0x18007647b  call    cs:__imp_AllocSplStr
  ... truncated ...
```
