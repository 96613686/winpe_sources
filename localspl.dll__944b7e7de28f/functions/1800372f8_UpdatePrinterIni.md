# UpdatePrinterIni

- ea: `0x1800372f8`
- end: `0x180037e7f`
- name: `UpdatePrinterIni`
- size: `2951`
- prototype: `__int64 __fastcall(_INIPRINTER *this, int)`
- caller_count: `18`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800062fc`
- `0x180008cb8`
- `0x180038d84`
- `0x18003ce20`
- `0x180042588`
- `0x18004fe9c`
- `0x1800552ac`
- `0x180057b58`
- `0x180058cc4`
- `0x18005974c`
- `0x18006eb10`
- `0x18007acf8`
- `0x18007bd7c`
- `0x18008aabc`
- `0x18009cdac`
- `0x1800a2628`
- `0x1800a4c70`
- `0x1800c27d8`

## callees

- `0x180004fb8`
- `0x180005cc0`
- `0x180005d40`
- `0x180008520`
- `0x180008560`
- `0x1800085ac`
- `0x1800086e0`
- `0x180008730`
- `0x18000b600`
- `0x180012dc0`
- `0x1800170a0`
- `0x180025938`
- `0x18002595c`
- `0x180025a08`
- `0x180027fb0`
- `0x18002e35c`
- `0x1800372f8`
- `0x18003ea2c`
- `0x180040904`
- `0x180054638`
- `0x18005591c`
- `0x18009fd60`
- `0x1800e6010`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180037b7d`
- `ntdll!RtlLengthSid` at `0x180037b7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800373b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800373b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037d99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180037d99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800374e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037cf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800374e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037cf0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037d89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037d89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037d5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e4573`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037d5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e4573`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800374b1`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800374b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180037597`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180037597`
- `SPOOLSS!DllFreeSplStr` at `0x180037d74`
- `SPOOLSS!DllFreeSplStr` at `0x180037da4`
- `SPOOLSS!DllFreeSplStr` at `0x180037daf`
- `SPOOLSS!DllFreeSplStr` at `0x180037dc2`
- `SPOOLSS!DllFreeSplStr` at `0x180037d74`
- `SPOOLSS!DllFreeSplStr` at `0x180037da4`
- `SPOOLSS!DllFreeSplStr` at `0x180037daf`
- `SPOOLSS!DllFreeSplStr` at `0x180037dc2`
- `SPOOLSS!DllFreeSplMem` at `0x180037cc5`
- `SPOOLSS!DllFreeSplMem` at `0x180037de0`
- `SPOOLSS!DllFreeSplMem` at `0x180037cc5`
- `SPOOLSS!DllFreeSplMem` at `0x180037de0`
- `SPOOLSS!DllAllocSplMem` at `0x180037c74`
- `SPOOLSS!DllAllocSplMem` at `0x180037c74`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800374cc`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800374cc`
- `SPOOLSS!AllocSplStr` at `0x1800373cb`
- `SPOOLSS!AllocSplStr` at `0x1800373f7`
- `SPOOLSS!AllocSplStr` at `0x18003741f`
- `SPOOLSS!AllocSplStr` at `0x1800373cb`
- `SPOOLSS!AllocSplStr` at `0x1800373f7`
- `SPOOLSS!AllocSplStr` at `0x18003741f`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180037d69`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800e4586`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180037d69`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800e4586`

## string_xrefs

- `0x1800374f2`: `UpdatePrinterIni`
- `0x180037e50`: `UpdatePrinterIni`
- `0x180037e49`: `Failed to update iniPrinter %p.`
- `0x180037c32`: `SpoolDirectory`
- `0x180037b9f`: `CreatorSid`
- `0x180037586`: `DsKeyUpdateForeground`
- `0x1800377f3`: `DsKeyUpdateForeground`
- `0x180037b53`: `Security`
- `0x18003756e`: `DsKeyUpdate`
- `0x1800377ce`: `DsKeyUpdate`
- `0x1800378ea`: `IppInstalledDevMode`
- `0x18003791f`: `IppInstalledDevMode`

## pseudocode

```c
__int64 __fastcall UpdatePrinterIni(_INIPRINTER *this, int a2)
{
  unsigned int *v3; // r13
  __int64 v4; // rdi
  __int64 v5; // rsi
  unsigned int v6; // eax
  unsigned int v7; // r14d
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  _QWORD *v11; // rcx
  int v12; // eax
  __int64 v13; // rdx
  HANDLE v14; // r13
  DWORD LastError; // eax
  __int64 v16; // rax
  int v17; // r8d
  const unsigned __int16 *v18; // rdx
  DWORD TickCount; // eax
  __int64 v20; // r8
  unsigned int v21; // eax
  __int64 v22; // r8
  int v23; // r8d
  ULONG v24; // eax
  __int64 v25; // rax
  __int64 v26; // r14
  unsigned int (__fastcall *v27)(_QWORD, HKEY, _QWORD); // rax
  __int64 v28; // rax
  HKEY hKey; // [rsp+38h] [rbp-90h] BYREF
  char v31; // [rsp+40h] [rbp-88h]
  __int64 v32; // [rsp+48h] [rbp-80h] BYREF
  DWORD v33; // [rsp+50h] [rbp-78h]
  __int64 v34; // [rsp+58h] [rbp-70h]
  unsigned int v35; // [rsp+60h] [rbp-68h]
  unsigned int v36; // [rsp+64h] [rbp-64h]
  __int64 v37; // [rsp+68h] [rbp-60h]
  __int64 v38; // [rsp+70h] [rbp-58h]
  unsigned __int16 *v39; // [rsp+78h] [rbp-50h]
  HANDLE v40; // [rsp+80h] [rbp-48h]
  char v41; // [rsp+D0h] [rbp+8h]
  DWORD dwErrCode; // [rsp+E0h] [rbp+18h] BYREF
  DWORD SecurityDescriptorLength; // [rsp+E8h] [rbp+20h] BYREF

  v3 = (unsigned int *)*((_QWORD *)this + 35);
  dwErrCode = 0;
  hKey = 0;
  v4 = 0;
  v32 = 0;
  v5 = 0;
  v34 = 0;
  v6 = v3[42];
  if ( (v6 & 0x800) != 0 || (v6 & 0x4000000) != 0 && (unsigned int)(a2 - 2) <= 1 )
    return 1;
  v40 = 0;
  v7 = 1;
  v35 = 0;
  SecurityDescriptorLength = 0;
  v8 = 0;
  v41 = 0;
  if ( v3 )
    SafeIncrementReference(v3 + 4);
  if ( SafeIncrementReference((unsigned int *)this + 4) > *((_DWORD *)this + 62) )
    *((_DWORD *)this + 62) = *((_DWORD *)this + 4);
  v36 = LeaveSplSemAndResetCount();
  EnterCriticalSection(&RegistryLock);
  EnterSplSem(0);
  v9 = *((_QWORD *)this + 7);
  if ( v9 )
  {
    v37 = AllocSplStr(*(_QWORD *)(v9 + 24));
    if ( !v37 )
      v7 = 0;
  }
  else
  {
    v37 = 0;
  }
  v38 = 0;
  v10 = *((_QWORD *)this + 11);
  if ( v10 )
  {
    v38 = AllocSplStr(*(_QWORD *)(v10 + 24));
    v7 &= -(v38 != 0);
  }
  v39 = 0;
  v11 = (_QWORD *)*((_QWORD *)this + 11);
  if ( v11 )
    v39 = (unsigned __int16 *)AllocSplStr(v11[18]);
  if ( v7 )
  {
    if ( (unsigned int)CloneIniPrinter(this, &v32, a2 != 3, *((_DWORD *)this + 100) & 0xFFFEFFFE) )
    {
      v12 = CloneIniSpooler(v3);
      v4 = v32;
      v5 = v34;
      if ( v12 && v32 && v34 )
      {
        v7 = 1;
        goto LABEL_24;
      }
    }
    else
    {
      v4 = v32;
    }
    v7 = 0;
LABEL_24:
    v8 = *((_DWORD *)this + 100);
    *((_DWORD *)this + 100) = -1;
    v11 = (_QWORD *)*((_QWORD *)this + 24);
    if ( v11 )
      SecurityDescriptorLength = GetSecurityDescriptorLength(v11);
  }
  LeaveSplSem(v11);
  if ( v7 )
  {
    v14 = RevertToPrinterSelf();
    v40 = v14;
    if ( !v14 )
    {
      LastError = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceWarning("UpdatePrinterIni", L"Failed to revert to self.  Error %d", LastError);
    }
    v16 = SubChar(*(_QWORD *)(v4 + 24), v13);
    v32 = v16;
    if ( !v16 )
      goto LABEL_30;
    if ( !(unsigned int)PrinterCreateKey(*(_QWORD *)(v5 + 240), v16, (unsigned int)&hKey, (unsigned int)&dwErrCode, v5) )
      goto LABEL_102;
    if ( a2 == 3 )
    {
      RegSetDWord((_DWORD)hKey, (unsigned int)L"DsKeyUpdate", *(_DWORD *)(v4 + 344), (unsigned int)&dwErrCode, v5);
      v17 = *(_DWORD *)(v4 + 388);
      v18 = L"DsKeyUpdateForeground";
    }
    else
    {
      if ( a2 )
      {
        TickCount = GetTickCount();
        v33 = TickCount;
        if ( !TickCount )
          TickCount = 1;
        v33 = TickCount;
        if ( *(_DWORD *)(v4 + 304) == TickCount )
          v33 = ++TickCount;
        *(_DWORD *)(v4 + 304) = TickCount;
        _InterlockedExchange((volatile __int32 *)this + 76, TickCount);
        RegSetDWord((_DWORD)hKey, (unsigned int)L"ChangeID", *(_DWORD *)(v4 + 304), (unsigned int)&dwErrCode, v5);
      }
      if ( a2 == 2 )
        goto LABEL_102;
      RegSetDWord((_DWORD)hKey, (unsigned int)L"StatusExt", *(_DWORD *)(v4 + 140), (unsigned int)&dwErrCode, v5);
      RegSetDWord((_DWORD)hKey, (unsigned int)L"Status", *(_DWORD *)(v4 + 136), (unsigned int)&dwErrCode, v5);
      if ( (v8 & 1) == 0 )
      {
        RegSetString(hKey, (struct _INISPOOLER *)v5);
        v8 |= 1u;
      }
      if ( (v8 & 0x10000) == 0 )
      {
        RegSetString(hKey, (struct _INISPOOLER *)v5);
        v8 |= 0x10000u;
      }
      if ( (v8 & 2) == 0 )
      {
        RegSetString(hKey, (struct _INISPOOLER *)v5);
        v8 |= 2u;
      }
      if ( (v8 & 0x800) == 0 )
      {
        RegSetString(hKey, (struct _INISPOOLER *)v5);
        v8 |= 0x800u;
      }
      if ( (v8 & 4) == 0 )
      {
        RegSetString(hKey, (struct _INISPOOLER *)v5);
        v8 |= 4u;
      }
      if ( (v8 & 8) == 0 )
      {
        RegSetString(hKey, (struct _INISPOOLER *)v5);
        v8 |= 8u;
      }
      RegSetDWord((_DWORD)hKey, (unsigned int)L"Action", *(_DWORD *)(v4 + 372), (unsigned int)&dwErrCode, v5);
      if ( (v8 & 0x10) == 0 )
      {
        RegSetString(hKey, (struct _INISPOOLER *)v5);
        v8 |= 0x10u;
      }
      RegSetDWord((_DWORD)hKey, (unsigned int)L"DsKeyUpdate", *(_DWORD *)(v4 + 344), (unsigned int)&dwErrCode, v5);
      RegSetDWord(
        (_DWORD)hKey,
        (unsigned int)L"DsKeyUpdateForeground",
        *(_DWORD *)(v4 + 388),
        (unsigned int)&dwErrCode,
        v5);
      if ( (v8 & 0x20) == 0 )
      {
        RegSetString(hKey, (struct _INISPOOLER *)v5);
        v8 |= 0x20u;
      }
      if ( (v8 & 0x1000) == 0 )
      {
        RegSetString(hKey, (struct _INISPOOLER *)v5);
        v8 |= 0x1000u;
      }
      if ( (v8 & 0x200) == 0 )
      {
        v20 = *(_QWORD *)(v4 + 104);
        if ( v20 )
          v21 = *(_DWORD *)(v4 + 96);
        else
          v21 = v35;
        RegSetBinaryData(hKey, L"Default DevMode", v20, v21, &dwErrCode, v5);
        v8 |= 0x200u;
      }
      if ( v39 )
      {
        if ( PrintCore::IppSelection::IsIppOrMpsPrinter(v39)
          && (v8 & 0x20000) == 0
          && SplRegQueryValue(hKey, L"IppInstalledDevMode", 0, 0, 0, 0) == 2 )
        {
          v22 = *(_QWORD *)(v4 + 104);
          if ( v22 )
          {
            RegSetBinaryData(hKey, L"IppInstalledDevMode", v22, *(unsigned int *)(v4 + 96), &dwErrCode, v5);
            v8 |= 0x20000u;
          }
        }
      }
      if ( (v8 & 0x40000000) == 0 )
      {
        RegSetDWord((_DWORD)hKey, (unsigned int)L"Priority", *(_DWORD *)(v4 + 112), (unsigned int)&dwErrCode, v5);
        v8 |= 0x40000000u;
      }
      if ( v8 >= 0 )
      {
        RegSetDWord(
          (_DWORD)hKey,
          (unsigned int)L"Default Priority",
          *(_DWORD *)(v4 + 116),
          (unsigned int)&dwErrCode,
          v5);
        v8 |= 0x80000000;
      }
      if ( (v8 & 0x8000000) == 0 )
      {
        RegSetDWord((_DWORD)hKey, (unsigned int)L"StartTime", *(_DWORD *)(v4 + 120), (unsigned int)&dwErrCode, v5);
        v8 |= 0x8000000u;
      }
      if ( (v8 & 0x2000000) == 0 )
      {
        RegSetDWord((_DWORD)hKey, (unsigned int)L"UntilTime", *(_DWORD *)(v4 + 124), (unsigned int)&dwErrCode, v5);
        v8 |= 0x2000000u;
      }
      if ( (v8 & 0x40) == 0 )
      {
        RegSetString(hKey, (struct _INISPOOLER *)v5);
        v8 |= 0x40u;
      }
      if ( (v8 & 0x80u) == 0 )
      {
        RegSetString(hKey, (struct _INISPOOLER *)v5);
        v8 |= 0x80u;
      }
      RegSetDWord((_DWORD)hKey, (unsigned int)L"Attributes", *(_DWORD *)(v4 + 152), (unsigned int)&dwErrCode, v5);
      RegSetDWord((_DWORD)hKey, (unsigned int)L"txTimeout", *(_DWORD *)(v4 + 328), (unsigned int)&dwErrCode, v5);
      RegSetDWord((_DWORD)hKey, (unsigned int)L"dnsTimeout", *(_DWORD *)(v4 + 324), (unsigned int)&dwErrCode, v5);
      RegSetDWord((_DWORD)hKey, (unsigned int)L"Redirected", *(_DWORD *)(v4 + 536), (unsigned int)&dwErrCode, v5);
      v23 = *(_DWORD *)(v4 + 532);
      if ( v23 )
        RegSetDWord((_DWORD)hKey, (unsigned int)L"ContainerTsSessionId", v23, (unsigned int)&dwErrCode, v5);
      if ( (v8 & 0x400) == 0 )
      {
        RegSetBinaryData(hKey, L"Security", *(_QWORD *)(v4 + 192), SecurityDescriptorLength, &dwErrCode, v5);
        v8 |= 0x400u;
      }
      if ( (v8 & 0x4000) == 0 )
      {
        v24 = RtlLengthSid(*(PSID *)(v4 + 472));
        RegSetBinaryData(hKey, L"CreatorSid", *(_QWORD *)(v4 + 472), v24, &dwErrCode, v5);
        v8 |= 0x4000u;
      }
      if ( (v8 & 0x8000) == 0 )
      {
        RegSetString(hKey, (struct _INISPOOLER *)v5);
        RegSetString(hKey, (struct _INISPOOLER *)v5);
        v8 |= 0x8000u;
      }
      if ( (v8 & 0x100) == 0 )
      {
        RegSetString(hKey, (struct _INISPOOLER *)v5);
        v8 |= 0x100u;
      }
      if ( (v8 & 0x2000) == 0 )
      {
        SecurityDescriptorLength = 0;
        GetPrinterPorts(v4, 0, &SecurityDescriptorLength);
        v25 = DllAllocSplMem(SecurityDescriptorLength);
        v26 = v25;
        if ( !v25 )
        {
LABEL_30:
          dwErrCode = GetLastError();
LABEL_102:
          if ( hKey )
            RegCloseKey(hKey);
          if ( v14 )
            ImpersonatePrinterClient(v14);
          DllFreeSplStr(v32);
          if ( dwErrCode )
          {
            SetLastError(dwErrCode);
            v7 = 0;
          }
          else
          {
            v7 = 1;
          }
          goto LABEL_108;
        }
        GetPrinterPorts(v4, v25, &SecurityDescriptorLength);
        RegSetString(hKey, (struct _INISPOOLER *)v5);
        v8 |= 0x2000u;
        DllFreeSplMem(v26);
      }
      v27 = *(unsigned int (__fastcall **)(_QWORD, HKEY, _QWORD))(v5 + 184);
      if ( v27 && !v27(*(_QWORD *)(v4 + 24), hKey, *(_QWORD *)(v4 + 296)) )
        dwErrCode = GetLastError();
      if ( (*(_BYTE *)(v4 + 136) & 0x40) == 0 || dwErrCode )
        goto LABEL_102;
      _INIPRINTER::ClearPrinterStatusFlags((_INIPRINTER *)v4, 0x40u);
      v41 = 1;
      v31 = 1;
      v17 = *(_DWORD *)(v4 + 136);
      v18 = L"Status";
    }
    RegSetDWord((_DWORD)hKey, (_DWORD)v18, v17, (unsigned int)&dwErrCode, v5);
    goto LABEL_102;
  }
LABEL_108:
  LeaveCriticalSection(&RegistryLock);
  DllFreeSplStr(v37);
  DllFreeSplStr(v38);
  if ( v39 )
    DllFreeSplStr(v39);
  FreeClonedIniPrinter(v4, a2 != 3);
  DllFreeSplMem(v5);
  EnterSplSemAndRestoreCount(v36);
  if ( v41 )
    _INIPRINTER::ClearPrinterStatusFlags(this, 0x40u);
  v28 = *((_QWORD *)this + 35);
  if ( v28 )
  {
    if ( *(_DWORD *)(v28 + 16) )
      SafeDecrementReference((unsigned int *)(v28 + 16));
    DeleteSpoolerCheck(*((_QWORD *)this + 35));
  }
  if ( *((_DWORD *)this + 4) )
    SafeDecrementReference((unsigned int *)this + 4);
  *((_DWORD *)this + 100) &= v8;
  if ( !v7 )
    LocalSpoolerTelemetry::WriteDbgTraceError("UpdatePrinterIni", L"Failed to update iniPrinter %p.", this);
  return v7;
}

```

## disassembly

```asm
0x1800372f8  mov     rax, rsp
0x1800372fb  mov     [rax+10h], edx
0x1800372fe  push    rbx
0x1800372ff  push    rsi
0x180037300  push    rdi
0x180037301  push    r12
0x180037303  push    r13
0x180037305  push    r14
0x180037307  push    r15
0x180037309  sub     rsp, 90h
0x180037310  mov     r15, rcx
0x180037313  mov     r13, [rcx+118h]
0x18003731a  xor     ecx, ecx
0x18003731c  mov     [rax+18h], ecx
0x18003731f  mov     [rsp+0C8h+hKey], rcx
0x180037324  mov     edi, ecx
0x180037326  mov     [rax-80h], rcx
0x18003732a  mov     esi, ecx
0x18003732c  mov     [rax-70h], rcx
0x180037330  mov     eax, [r13+0A8h]
0x180037337  lea     r12d, [rcx+1]
0x18003733b  bt      eax, 0Bh
0x18003733f  jb      loc_180037E69
0x180037345  bt      eax, 1Ah
0x180037349  jnb     short loc_180037357
0x18003734b  lea     eax, [rdx-2]
0x18003734e  cmp     eax, r12d
0x180037351  jbe     loc_180037E69
0x180037357  mov     [rsp+0C8h+var_48], rcx
0x18003735f  mov     r14d, r12d
0x180037362  mov     [rsp+0C8h+var_68], ecx
0x180037366  mov     [rsp+0C8h+arg_18], ecx
0x18003736d  mov     ebx, ecx
0x18003736f  mov     [rsp+0C8h+arg_0], cl
0x180037376  test    r13, r13
0x180037379  jz      short loc_180037384
0x18003737b  lea     rcx, [r13+10h]; unsigned int *
0x18003737f  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x180037384  lea     rcx, [r15+10h]; unsigned int *
0x180037388  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x18003738d  cmp     eax, [r15+0F8h]
0x180037394  jbe     short loc_1800373A1
0x180037396  mov     eax, [r15+10h]
0x18003739a  mov     [r15+0F8h], eax
0x1800373a1  call    LeaveSplSemAndResetCount
0x1800373a6  mov     [rsp+0C8h+var_64], eax
0x1800373aa  lea     rcx, RegistryLock; lpCriticalSection
0x1800373b1  call    cs:__imp_EnterCriticalSection
0x1800373b7  xor     ecx, ecx
0x1800373b9  call    EnterSplSem
0x1800373be  mov     rcx, [r15+38h]
0x1800373c2  test    rcx, rcx
0x1800373c5  jz      short loc_1800373E0
0x1800373c7  mov     rcx, [rcx+18h]
0x1800373cb  call    cs:__imp_AllocSplStr
0x1800373d1  mov     [rsp+0C8h+var_60], rax
0x1800373d6  test    rax, rax
0x1800373d9  jnz     short loc_1800373E5
0x1800373db  xor     r14d, r14d
0x1800373de  jmp     short loc_1800373E5
0x1800373e0  mov     [rsp+0C8h+var_60], rbx
0x1800373e5  mov     [rsp+0C8h+var_58], rbx
0x1800373ea  mov     rcx, [r15+58h]
0x1800373ee  test    rcx, rcx
0x1800373f1  jz      short loc_18003740A
0x1800373f3  mov     rcx, [rcx+18h]
0x1800373f7  call    cs:__imp_AllocSplStr
0x1800373fd  mov     [rsp+0C8h+var_58], rax
0x180037402  neg     rax
0x180037405  sbb     ecx, ecx
0x180037407  and     r14d, ecx
0x18003740a  mov     [rsp+0C8h+var_50], rbx
0x18003740f  mov     rcx, [r15+58h]
0x180037413  test    rcx, rcx
0x180037416  jz      short loc_18003742A
0x180037418  mov     rcx, [rcx+90h]
0x18003741f  call    cs:__imp_AllocSplStr
0x180037425  mov     [rsp+0C8h+var_50], rax
0x18003742a  test    r14d, r14d
0x18003742d  jz      loc_1800374BE
0x180037433  mov     r9d, [r15+190h]
0x18003743a  and     r9d, 0FFFEFFFEh
0x180037441  xor     r8d, r8d
0x180037444  cmp     [rsp+0C8h+arg_8], 3
0x18003744c  setnz   r8b
0x180037450  lea     rdx, [rsp+0C8h+var_80]
0x180037455  mov     rcx, r15
0x180037458  call    CloneIniPrinter
0x18003745d  test    eax, eax
0x18003745f  jz      short loc_18003748B
0x180037461  lea     rdx, [rsp+0C8h+var_70]
0x180037466  mov     rcx, r13; Src
0x180037469  call    CloneIniSpooler
0x18003746e  mov     rdi, [rsp+0C8h+var_80]
0x180037473  mov     rsi, [rsp+0C8h+var_70]
0x180037478  test    eax, eax
0x18003747a  jz      short loc_180037490
0x18003747c  test    rdi, rdi
0x18003747f  jz      short loc_180037490
0x180037481  test    rsi, rsi
0x180037484  jz      short loc_180037490
0x180037486  mov     r14d, r12d
0x180037489  jmp     short loc_180037493
0x18003748b  mov     rdi, [rsp+0C8h+var_80]
0x180037490  xor     r14d, r14d
0x180037493  mov     ebx, [r15+190h]
0x18003749a  mov     dword ptr [r15+190h], 0FFFFFFFFh
0x1800374a5  mov     rcx, [r15+0C0h]; pSecurityDescriptor
0x1800374ac  test    rcx, rcx
0x1800374af  jz      short loc_1800374BE
0x1800374b1  call    cs:__imp_GetSecurityDescriptorLength
0x1800374b7  mov     [rsp+0C8h+arg_18], eax
0x1800374be  call    LeaveSplSem
0x1800374c3  test    r14d, r14d
0x1800374c6  jz      loc_180037D92
0x1800374cc  call    cs:__imp_RevertToPrinterSelf
0x1800374d2  mov     r13, rax
0x1800374d5  mov     [rsp+0C8h+var_48], rax
0x1800374dd  test    rax, rax
0x1800374e0  jnz     short loc_1800374FE
0x1800374e2  call    cs:__imp_GetLastError
0x1800374e8  mov     r8d, eax
0x1800374eb  lea     rdx, aFailedToRevert_1; "Failed to revert to self.  Error %d"
0x1800374f2  lea     rcx, aUpdateprinteri_1; "UpdatePrinterIni"
0x1800374f9  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800374fe  mov     rcx, [rdi+18h]
0x180037502  call    SubChar
0x180037507  mov     [rsp+0C8h+var_80], rax
0x18003750c  test    rax, rax
0x18003750f  jnz     short loc_180037523
0x180037511  call    cs:__imp_GetLastError
0x180037517  mov     [rsp+0C8h+dwErrCode], eax
0x18003751e  jmp     loc_180037D51
0x180037523  mov     [rsp+0C8h+var_A8], rsi
0x180037528  lea     r9, [rsp+0C8h+dwErrCode]
0x180037530  lea     r8, [rsp+0C8h+hKey]
0x180037535  mov     rdx, rax
0x180037538  mov     rcx, [rsi+0F0h]
0x18003753f  call    PrinterCreateKey
0x180037544  test    eax, eax
0x180037546  jz      loc_180037D51
0x18003754c  mov     r14d, [rsp+0C8h+arg_8]
0x180037554  cmp     r14d, 3
0x180037558  jnz     short loc_180037592
0x18003755a  mov     [rsp+0C8h+var_A8], rsi
0x18003755f  lea     r9, [rsp+0C8h+dwErrCode]
0x180037567  mov     r8d, [rdi+158h]
0x18003756e  lea     rdx, szDsKeyUpdate; "DsKeyUpdate"
0x180037575  mov     rcx, [rsp+0C8h+hKey]
0x18003757a  call    RegSetDWord
0x18003757f  mov     r8d, [rdi+184h]
0x180037586  lea     rdx, szDsKeyUpdateForeground; "DsKeyUpdateForeground"
0x18003758d  jmp     loc_180037D39
0x180037592  test    r14d, r14d
0x180037595  jz      short loc_1800375EC
0x180037597  call    cs:__imp_GetTickCount
0x18003759d  mov     [rsp+0C8h+var_78], eax
0x1800375a1  test    eax, eax
0x1800375a3  cmovz   eax, r12d
0x1800375a7  mov     [rsp+0C8h+var_78], eax
0x1800375ab  cmp     [rdi+130h], eax
0x1800375b1  jnz     short loc_1800375BA
0x1800375b3  add     eax, r12d
0x1800375b6  mov     [rsp+0C8h+var_78], eax
0x1800375ba  mov     [rdi+130h], eax
0x1800375c0  xchg    eax, [r15+130h]
0x1800375c7  mov     [rsp+0C8h+var_A8], rsi
0x1800375cc  lea     r9, [rsp+0C8h+dwErrCode]
0x1800375d4  mov     r8d, [rdi+130h]
0x1800375db  lea     rdx, szTimeLastChange; "ChangeID"
0x1800375e2  mov     rcx, [rsp+0C8h+hKey]
0x1800375e7  call    RegSetDWord
0x1800375ec  cmp     r14d, 2
0x1800375f0  jz      loc_180037D51
0x1800375f6  mov     [rsp+0C8h+var_A8], rsi
0x1800375fb  lea     r9, [rsp+0C8h+dwErrCode]
0x180037603  mov     r8d, [rdi+8Ch]
0x18003760a  lea     rdx, szStatusExt; "StatusExt"
0x180037611  mov     rcx, [rsp+0C8h+hKey]
0x180037616  call    RegSetDWord
0x18003761b  mov     [rsp+0C8h+var_A8], rsi
0x180037620  lea     r9, [rsp+0C8h+dwErrCode]
0x180037628  mov     r8d, [rdi+88h]
0x18003762f  lea     rdx, szStatus; "Status"
0x180037636  mov     rcx, [rsp+0C8h+hKey]
0x18003763b  call    RegSetDWord
0x180037640  test    r12b, bl
0x180037643  jnz     short loc_18003766E
0x180037645  mov     [rsp+0C8h+var_A8], rsi; struct _INISPOOLER *
0x18003764a  lea     r9, [rsp+0C8h+dwErrCode]
0x180037652  mov     r8, [rdi+18h]
0x180037656  lea     rdx, szName
0x18003765d  mov     rcx, [rsp+0C8h+hKey]; void *
0x180037662  call    RegSetString
0x180037667  or      ebx, r12d
0x18003766a  mov     [rsp+0C8h+var_98], ebx
0x18003766e  mov     r14d, 10000h
0x180037674  test    r14d, ebx
0x180037677  jnz     short loc_1800376A5
0x180037679  mov     [rsp+0C8h+var_A8], rsi; struct _INISPOOLER *
0x18003767e  lea     r9, [rsp+0C8h+dwErrCode]
0x180037686  mov     r8, [rdi+220h]
0x18003768d  lea     rdx, szPerUserName; "PerUserName"
0x180037694  mov     rcx, [rsp+0C8h+hKey]; void *
0x180037699  call    RegSetString
0x18003769e  or      ebx, r14d
0x1800376a1  mov     [rsp+0C8h+var_98], ebx
0x1800376a5  test    bl, 2
0x1800376a8  jnz     short loc_1800376D3
0x1800376aa  mov     [rsp+0C8h+var_A8], rsi; struct _INISPOOLER *
0x1800376af  lea     r9, [rsp+0C8h+dwErrCode]
0x1800376b7  mov     r8, [rdi+28h]
0x1800376bb  lea     rdx, szShare; "Share Name"
0x1800376c2  mov     rcx, [rsp+0C8h+hKey]; void *
0x1800376c7  call    RegSetString
0x1800376cc  or      ebx, 2
0x1800376cf  mov     [rsp+0C8h+var_98], ebx
0x1800376d3  mov     r14d, 800h
0x1800376d9  test    r14d, ebx
0x1800376dc  jnz     short loc_180037708
0x1800376de  mov     [rsp+0C8h+var_A8], rsi; struct _INISPOOLER *
0x1800376e3  lea     r9, [rsp+0C8h+dwErrCode]
0x1800376eb  mov     r8, [rsp+0C8h+var_60]
0x1800376f0  lea     rdx, szPrintProcessor; "Print Processor"
0x1800376f7  mov     rcx, [rsp+0C8h+hKey]; void *
0x1800376fc  call    RegSetString
0x180037701  or      ebx, r14d
0x180037704  mov     [rsp+0C8h+var_98], ebx
0x180037708  test    bl, 4
0x18003770b  jnz     short loc_180037736
0x18003770d  mov     [rsp+0C8h+var_A8], rsi; struct _INISPOOLER *
0x180037712  lea     r9, [rsp+0C8h+dwErrCode]
0x18003771a  mov     r8, [rdi+40h]
0x18003771e  lea     rdx, szDatatype; "Datatype"
0x180037725  mov     rcx, [rsp+0C8h+hKey]; void *
0x18003772a  call    RegSetString
0x18003772f  or      ebx, 4
0x180037732  mov     [rsp+0C8h+var_98], ebx
0x180037736  test    bl, 8
0x180037739  jnz     short loc_180037764
0x18003773b  mov     [rsp+0C8h+var_A8], rsi; struct _INISPOOLER *
0x180037740  lea     r9, [rsp+0C8h+dwErrCode]
0x180037748  mov     r8, [rdi+48h]
0x18003774c  lea     rdx, szParameters; "Parameters"
0x180037753  mov     rcx, [rsp+0C8h+hKey]; void *
0x180037758  call    RegSetString
0x18003775d  or      ebx, 8
0x180037760  mov     [rsp+0C8h+var_98], ebx
0x180037764  mov     [rsp+0C8h+var_A8], rsi
0x180037769  lea     r9, [rsp+0C8h+dwErrCode]
0x180037771  mov     r8d, [rdi+174h]
0x180037778  lea     rdx, szAction; "Action"
0x18003777f  mov     rcx, [rsp+0C8h+hKey]
0x180037784  call    RegSetDWord
0x180037789  test    bl, 10h
0x18003778c  jnz     short loc_1800377BA
0x18003778e  mov     [rsp+0C8h+var_A8], rsi; struct _INISPOOLER *
0x180037793  lea     r9, [rsp+0C8h+dwErrCode]
0x18003779b  mov     r8, [rdi+150h]
0x1800377a2  lea     rdx, szObjectGUID; "ObjectGUID"
0x1800377a9  mov     rcx, [rsp+0C8h+hKey]; void *
0x1800377ae  call    RegSetString
0x1800377b3  or      ebx, 10h
0x1800377b6  mov     [rsp+0C8h+var_98], ebx
0x1800377ba  mov     [rsp+0C8h+var_A8], rsi
0x1800377bf  lea     r9, [rsp+0C8h+dwErrCode]
0x1800377c7  mov     r8d, [rdi+158h]
0x1800377ce  lea     rdx, szDsKeyUpdate; "DsKeyUpdate"
0x1800377d5  mov     rcx, [rsp+0C8h+hKey]
0x1800377da  call    RegSetDWord
0x1800377df  mov     [rsp+0C8h+var_A8], rsi
0x1800377e4  lea     r9, [rsp+0C8h+dwErrCode]
0x1800377ec  mov     r8d, [rdi+184h]
0x1800377f3  lea     rdx, szDsKeyUpdateForeground; "DsKeyUpdateForeground"
0x1800377fa  mov     rcx, [rsp+0C8h+hKey]
0x1800377ff  call    RegSetDWord
0x180037804  test    bl, 20h
0x180037807  jnz     short loc_180037832
0x180037809  mov     [rsp+0C8h+var_A8], rsi; struct _INISPOOLER *
0x18003780e  lea     r9, [rsp+0C8h+dwErrCode]
0x180037816  mov     r8, [rdi+50h]
0x18003781a  lea     rdx, szName+10h
0x180037821  mov     rcx, [rsp+0C8h+hKey]; void *
0x180037826  call    RegSetString
0x18003782b  or      ebx, 20h
0x18003782e  mov     [rsp+0C8h+var_98], ebx
0x180037832  mov     r14d, 1000h
0x180037838  test    r14d, ebx
0x18003783b  jnz     short loc_180037867
0x18003783d  mov     [rsp+0C8h+var_A8], rsi; struct _INISPOOLER *
0x180037842  lea     r9, [rsp+0C8h+dwErrCode]
0x18003784a  mov     r8, [rsp+0C8h+var_58]
0x18003784f  lea     rdx, szDriver; "Printer Driver"
0x180037856  mov     rcx, [rsp+0C8h+hKey]; void *
0x18003785b  call    RegSetString
0x180037860  or      ebx, r14d
0x180037863  mov     [rsp+0C8h+var_98], ebx
0x180037867  mov     r14d, 200h
0x18003786d  test    r14d, ebx
0x180037870  jnz     short loc_1800378B1
  ... truncated ...
```
