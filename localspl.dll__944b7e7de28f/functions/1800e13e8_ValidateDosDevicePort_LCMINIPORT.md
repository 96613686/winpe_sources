# ValidateDosDevicePort(_LCMINIPORT *)

- ea: `0x1800e13e8`
- end: `0x1800e183b`
- name: `?ValidateDosDevicePort@@YAHPEAU_LCMINIPORT@@@Z`
- size: `1107`
- prototype: `__int64 __fastcall(struct _LCMINIPORT *)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800de700`
- `0x1800e0fbc`
- `0x1800e1124`

## callees

- `0x180046650`
- `0x1800df3e0`
- `0x1800df488`
- `0x1800dfcdc`
- `0x1800dfef0`
- `0x1800e005c`
- `0x1800e0120`
- `0x1800e045c`
- `0x1800e081c`
- `0x1800e1338`
- `0x1800e13e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e16e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e16e3`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800e14d4`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x1800e14d4`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1800e1660`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1800e1672`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1800e1660`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1800e1672`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e16d3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e16d3`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800e1716`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800e1716`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800e15d9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800e1600`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800e15d9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800e1600`
- `SPOOLSS!DllFreeSplStr` at `0x1800e1511`
- `SPOOLSS!DllFreeSplStr` at `0x1800e1827`
- `SPOOLSS!DllFreeSplStr` at `0x1800e1511`
- `SPOOLSS!DllFreeSplStr` at `0x1800e1827`
- `SPOOLSS!DllFreeSplMem` at `0x1800e151f`
- `SPOOLSS!DllFreeSplMem` at `0x1800e152d`
- `SPOOLSS!DllFreeSplMem` at `0x1800e153b`
- `SPOOLSS!DllFreeSplMem` at `0x1800e1549`
- `SPOOLSS!DllFreeSplMem` at `0x1800e151f`
- `SPOOLSS!DllFreeSplMem` at `0x1800e152d`
- `SPOOLSS!DllFreeSplMem` at `0x1800e153b`
- `SPOOLSS!DllFreeSplMem` at `0x1800e1549`
- `SPOOLSS!DllAllocSplMem` at `0x1800e1487`
- `SPOOLSS!DllAllocSplMem` at `0x1800e14ba`
- `SPOOLSS!DllAllocSplMem` at `0x1800e158b`
- `SPOOLSS!DllAllocSplMem` at `0x1800e1615`
- `SPOOLSS!DllAllocSplMem` at `0x1800e1487`
- `SPOOLSS!DllAllocSplMem` at `0x1800e14ba`
- `SPOOLSS!DllAllocSplMem` at `0x1800e158b`
- `SPOOLSS!DllAllocSplMem` at `0x1800e1615`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800e1466`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800e17dc`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800e1466`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800e17dc`
- `SPOOLSS!AllocSplStr` at `0x1800e1574`
- `SPOOLSS!AllocSplStr` at `0x1800e1574`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800e14ff`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800e167c`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800e1800`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800e14ff`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800e167c`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800e1800`
- `SPOOLSS!SplRegisterForDeviceEvents` at `0x1800e17f3`
- `SPOOLSS!SplRegisterForDeviceEvents` at `0x1800e17f3`
- `KERNEL32!SetCommState` at `0x1800e1765`
- `KERNEL32!SetCommState` at `0x1800e1765`
- `KERNEL32!GetCommState` at `0x1800e1731`
- `KERNEL32!GetCommState` at `0x1800e1731`
- `KERNEL32!SetCommTimeouts` at `0x1800e178b`
- `KERNEL32!SetCommTimeouts` at `0x1800e17d6`
- `KERNEL32!SetCommTimeouts` at `0x1800e178b`
- `KERNEL32!SetCommTimeouts` at `0x1800e17d6`
- `KERNEL32!GetCommTimeouts` at `0x1800e1746`
- `KERNEL32!GetCommTimeouts` at `0x1800e17b1`
- `KERNEL32!GetCommTimeouts` at `0x1800e1746`
- `KERNEL32!GetCommTimeouts` at `0x1800e17b1`

## string_xrefs

- `0x1800e16ec`: `CreateFile() failed!!!  GLE[%d]  portname: %ws`
- `0x1800e1810`: `GetCommTimeouts failed for pIniPort->hFile %p`
- `0x1800e1793`: `GetCommState failed for pIniPort->hFile %p`

## pseudocode

```c
__int64 __fastcall ValidateDosDevicePort(struct _LCMINIPORT *a1)
{
  __int64 v1; // r8
  __int64 v3; // r14
  unsigned int v4; // ebx
  unsigned __int16 *v5; // rsi
  const WCHAR *v6; // r15
  unsigned __int16 *v7; // r12
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // r13
  WCHAR *v10; // rax
  const WCHAR *v12; // rsi
  __int64 v13; // rax
  HANDLE FileW; // rax
  DWORD LastError; // eax
  void *v16; // rcx
  void *v17; // rcx
  HANDLE v18; // rbx
  const WCHAR *lpTargetPath; // [rsp+40h] [rbp-39h]
  HANDLE hToken; // [rsp+48h] [rbp-31h]
  struct _COMMTIMEOUTS CommTimeouts; // [rsp+50h] [rbp-29h] BYREF
  _DCB DCB; // [rsp+68h] [rbp-11h] BYREF

  v1 = *((_QWORD *)a1 + 3);
  memset(&DCB, 0, sizeof(DCB));
  memset(&CommTimeouts, 0, sizeof(CommTimeouts));
  LocalMonTelemetry::WriteDbgTraceInfo("ValidateDosDevicePort", L"Port: %ws", v1);
  v3 = 0;
  if ( (unsigned int)IsCOMPort(*((unsigned __int16 **)a1 + 3))
    && (unsigned __int64)(*((_QWORD *)a1 + 4) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    return 1;
  }
  v4 = 0;
  hToken = RevertToPrinterSelf();
  if ( !hToken )
    return v4;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v8 = (unsigned __int16 *)DllAllocSplMem(520);
  v9 = v8;
  if ( v8 )
  {
    if ( !StrNCatBuffW(v8, 0x104u, *((_QWORD *)a1 + 3), 0) )
    {
      LcmRemoveColon(v9);
      v10 = (WCHAR *)DllAllocSplMem(520);
      v6 = v10;
      if ( v10 )
      {
        if ( !QueryDosDeviceW(v9, v10, 0x104u) )
        {
          v4 = 1;
          LocalMonTelemetry::WriteDbgTraceInfo("ValidateDosDevicePort", L"Unable to find port: %ws", v9);
          goto LABEL_10;
        }
        v3 = AllocSplStr(v6);
        if ( v3 )
        {
          v7 = (unsigned __int16 *)DllAllocSplMem(520);
          if ( v7 )
          {
            if ( !StrNCatBuffW(v7, 0x104u, &szLcmDeviceNameHeader, *((_QWORD *)a1 + 3), 0) )
            {
              lpTargetPath = v6;
              v12 = v6;
              LcmRemoveColon(v7);
              if ( !lstrcmpiW(v6, v7) )
              {
                do
                {
                  v13 = -1;
                  do
                    ++v13;
                  while ( v12[v13] );
                  v12 += v13 + 1;
                }
                while ( !lstrcmpiW(v12, v7) );
                lpTargetPath = v12;
              }
              v5 = (unsigned __int16 *)DllAllocSplMem(520);
              if ( v5 )
              {
                if ( !StrNCatBuffW(v5, 0x104u, L"NONSPOOLED_", *((_QWORD *)a1 + 3), 0) )
                {
                  LcmRemoveColon(v5);
                  DefineDosDeviceW(2u, v5, 0);
                  DefineDosDeviceW(1u, v5, lpTargetPath);
                  ImpersonatePrinterClient(hToken);
                  if ( StrNCatBuffW(v5, 0x104u, L"\\\\.\\NONSPOOLED_", *((_QWORD *)a1 + 3), 0) )
                  {
LABEL_12:
                    DllFreeSplStr(v3);
                    goto LABEL_13;
                  }
                  LcmRemoveColon(v5);
                  FileW = CreateFileW(v5, 0xC0000000, 1u, 0, 4u, 0x8000080u, 0);
                  *((_QWORD *)a1 + 4) = FileW;
                  if ( FileW == (HANDLE)-1LL )
                  {
                    LastError = GetLastError();
                    LocalMonTelemetry::WriteDbgTraceError(
                      "ValidateDosDevicePort",
                      L"CreateFile() failed!!!  GLE[%d]  portname: %ws",
                      LastError,
                      v5);
                    RemoveDosDeviceDefinition(a1);
                    goto LABEL_12;
                  }
                  *((_DWORD *)a1 + 11) |= 1u;
                  SetEndOfFile(FileW);
                  if ( (unsigned int)IsCOMPort(*((unsigned __int16 **)a1 + 3)) )
                  {
                    if ( GetCommState(*((HANDLE *)a1 + 4), &DCB) )
                    {
                      GetCommTimeouts(*((HANDLE *)a1 + 4), &CommTimeouts);
                      GetIniCommValues(*((LPCWSTR *)a1 + 3), &DCB, &CommTimeouts);
                      SetCommState(*((HANDLE *)a1 + 4), &DCB);
                      v16 = (void *)*((_QWORD *)a1 + 4);
                      CommTimeouts.WriteTotalTimeoutConstant = g_COMWriteTimeoutConstant_ms;
                      *(_QWORD *)&CommTimeouts.ReadTotalTimeoutConstant = 5000;
                      CommTimeouts.ReadIntervalTimeout = 200;
                      SetCommTimeouts(v16, &CommTimeouts);
LABEL_42:
                      *((_DWORD *)a1 + 11) |= 2u;
                      goto LABEL_44;
                    }
                    LocalMonTelemetry::WriteDbgTraceInfo(
                      "ValidateDosDevicePort",
                      L"GetCommState failed for pIniPort->hFile %p",
                      *((_QWORD *)a1 + 4));
                  }
                  else if ( (unsigned int)IsLPTPort(*((unsigned __int16 **)a1 + 3)) )
                  {
                    if ( !GetCommTimeouts(*((HANDLE *)a1 + 4), &CommTimeouts) )
                    {
                      LocalMonTelemetry::WriteDbgTraceInfo(
                        "ValidateDosDevicePort",
                        L"GetCommTimeouts failed for pIniPort->hFile %p",
                        *((_QWORD *)a1 + 4));
                      goto LABEL_44;
                    }
                    GetTransmissionRetryTimeoutFromRegistry(&CommTimeouts.WriteTotalTimeoutConstant);
                    v17 = (void *)*((_QWORD *)a1 + 4);
                    CommTimeouts.WriteTotalTimeoutConstant *= 1000;
                    SetCommTimeouts(v17, &CommTimeouts);
                    v18 = RevertToPrinterSelf();
                    *((_QWORD *)a1 + 12) = SplRegisterForDeviceEvents(*((_QWORD *)a1 + 4), a1, HandleLptQueryRemove);
                    ImpersonatePrinterClient(v18);
                    goto LABEL_42;
                  }
LABEL_44:
                  DllFreeSplStr(*((_QWORD *)a1 + 7));
                  *((_QWORD *)a1 + 7) = v3;
                  v4 = 1;
                  goto LABEL_14;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_10:
  ImpersonatePrinterClient(hToken);
  if ( !v4 && v3 )
    goto LABEL_12;
LABEL_13:
  if ( v5 )
LABEL_14:
    DllFreeSplMem(v5);
  if ( v6 )
    DllFreeSplMem(v6);
  if ( v9 )
    DllFreeSplMem(v9);
  if ( v7 )
    DllFreeSplMem(v7);
  return v4;
}

```

## disassembly

```asm
0x1800e13e8  push    rbp
0x1800e13ea  push    rbx
0x1800e13eb  push    rsi
0x1800e13ec  push    rdi
0x1800e13ed  push    r12
0x1800e13ef  push    r13
0x1800e13f1  push    r14
0x1800e13f3  push    r15
0x1800e13f5  lea     rbp, [rsp-1Fh]
0x1800e13fa  sub     rsp, 98h
0x1800e1401  mov     rax, cs:__security_cookie
0x1800e1408  xor     rax, rsp
0x1800e140b  mov     [rbp+57h+var_48], rax
0x1800e140f  mov     r8, [rcx+18h]
0x1800e1413  lea     rdx, aPortWs_0; "Port: %ws"
0x1800e141a  xorps   xmm0, xmm0
0x1800e141d  mov     rdi, rcx
0x1800e1420  xor     eax, eax
0x1800e1422  lea     rcx, aValidatedosdev_0; "ValidateDosDevicePort"
0x1800e1429  movups  xmmword ptr [rbp+57h+DCB.DCBlength], xmm0
0x1800e142d  mov     [rbp+57h+CommTimeouts.WriteTotalTimeoutConstant], eax
0x1800e1430  movups  xmmword ptr [rbp+57h+DCB.wReserved], xmm0
0x1800e1434  movups  xmmword ptr [rbp+57h+CommTimeouts.ReadIntervalTimeout], xmm0
0x1800e1438  call    ?WriteDbgTraceInfo@LocalMonTelemetry@@SAXPEADPEAGZZ; LocalMonTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800e143d  mov     rcx, [rdi+18h]; unsigned __int16 *
0x1800e1441  call    ?IsCOMPort@@YAHPEAG@Z; IsCOMPort(ushort *)
0x1800e1446  xor     r14d, r14d
0x1800e1449  test    eax, eax
0x1800e144b  jz      short loc_1800E1463
0x1800e144d  mov     rax, [rdi+20h]
0x1800e1451  dec     rax
0x1800e1454  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800e1458  ja      short loc_1800E1463
0x1800e145a  lea     ebx, [r14+1]
0x1800e145e  jmp     loc_1800E154F
0x1800e1463  mov     ebx, r14d
0x1800e1466  call    cs:__imp_RevertToPrinterSelf
0x1800e146c  mov     [rbp+57h+hToken], rax
0x1800e1470  test    rax, rax
0x1800e1473  jz      loc_1800E154F
0x1800e1479  mov     ecx, 208h
0x1800e147e  mov     rsi, r14
0x1800e1481  mov     r15, r14
0x1800e1484  mov     r12, r14
0x1800e1487  call    cs:__imp_DllAllocSplMem
0x1800e148d  mov     r13, rax
0x1800e1490  test    rax, rax
0x1800e1493  jz      short loc_1800E14FB
0x1800e1495  mov     r8, [rdi+18h]
0x1800e1499  xor     r9d, r9d
0x1800e149c  mov     edx, 104h; unsigned int
0x1800e14a1  mov     rcx, rax; unsigned __int16 *
0x1800e14a4  call    ?StrNCatBuffW@@YAKPEAGIZZ; StrNCatBuffW(ushort *,uint,...)
0x1800e14a9  test    eax, eax
0x1800e14ab  jnz     short loc_1800E14FB
0x1800e14ad  mov     rcx, r13; unsigned __int16 *
0x1800e14b0  call    ?LcmRemoveColon@@YAXPEAG@Z; LcmRemoveColon(ushort *)
0x1800e14b5  mov     ecx, 208h
0x1800e14ba  call    cs:__imp_DllAllocSplMem
0x1800e14c0  mov     r15, rax
0x1800e14c3  test    rax, rax
0x1800e14c6  jz      short loc_1800E14FB
0x1800e14c8  mov     r8d, 104h; ucchMax
0x1800e14ce  mov     rdx, rax; lpTargetPath
0x1800e14d1  mov     rcx, r13; lpDeviceName
0x1800e14d4  call    cs:__imp_QueryDosDeviceW
0x1800e14da  test    eax, eax
0x1800e14dc  jnz     loc_1800E1571
0x1800e14e2  mov     r8, r13
0x1800e14e5  lea     rdx, aUnableToFindPo; "Unable to find port: %ws"
0x1800e14ec  lea     rcx, aValidatedosdev_0; "ValidateDosDevicePort"
0x1800e14f3  lea     ebx, [rax+1]
0x1800e14f6  call    ?WriteDbgTraceInfo@LocalMonTelemetry@@SAXPEADPEAGZZ; LocalMonTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800e14fb  mov     rcx, [rbp+57h+hToken]; hToken
0x1800e14ff  call    cs:__imp_ImpersonatePrinterClient
0x1800e1505  test    ebx, ebx
0x1800e1507  jnz     short loc_1800E1517
0x1800e1509  test    r14, r14
0x1800e150c  jz      short loc_1800E1517
0x1800e150e  mov     rcx, r14
0x1800e1511  call    cs:__imp_DllFreeSplStr
0x1800e1517  test    rsi, rsi
0x1800e151a  jz      short loc_1800E1525
0x1800e151c  mov     rcx, rsi
0x1800e151f  call    cs:__imp_DllFreeSplMem
0x1800e1525  test    r15, r15
0x1800e1528  jz      short loc_1800E1533
0x1800e152a  mov     rcx, r15
0x1800e152d  call    cs:__imp_DllFreeSplMem
0x1800e1533  test    r13, r13
0x1800e1536  jz      short loc_1800E1541
0x1800e1538  mov     rcx, r13
0x1800e153b  call    cs:__imp_DllFreeSplMem
0x1800e1541  test    r12, r12
0x1800e1544  jz      short loc_1800E154F
0x1800e1546  mov     rcx, r12
0x1800e1549  call    cs:__imp_DllFreeSplMem
0x1800e154f  mov     eax, ebx
0x1800e1551  mov     rcx, [rbp+57h+var_48]
0x1800e1555  xor     rcx, rsp; StackCookie
0x1800e1558  call    __security_check_cookie
0x1800e155d  add     rsp, 98h
0x1800e1564  pop     r15
0x1800e1566  pop     r14
0x1800e1568  pop     r13
0x1800e156a  pop     r12
0x1800e156c  pop     rdi
0x1800e156d  pop     rsi
0x1800e156e  pop     rbx
0x1800e156f  pop     rbp
0x1800e1570  retn
0x1800e1571  mov     rcx, r15
0x1800e1574  call    cs:__imp_AllocSplStr
0x1800e157a  mov     r14, rax
0x1800e157d  test    rax, rax
0x1800e1580  jz      loc_1800E14FB
0x1800e1586  mov     ecx, 208h
0x1800e158b  call    cs:__imp_DllAllocSplMem
0x1800e1591  mov     r12, rax
0x1800e1594  xor     eax, eax
0x1800e1596  test    r12, r12
0x1800e1599  jz      loc_1800E14FB
0x1800e159f  mov     r9, [rdi+18h]
0x1800e15a3  lea     r8, ?szLcmDeviceNameHeader@@3PAGA; "\\Device\\NamedPipe\\Spooler\\"
0x1800e15aa  mov     edx, 104h; unsigned int
0x1800e15af  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax
0x1800e15b4  mov     rcx, r12; unsigned __int16 *
0x1800e15b7  call    ?StrNCatBuffW@@YAKPEAGIZZ; StrNCatBuffW(ushort *,uint,...)
0x1800e15bc  test    eax, eax
0x1800e15be  jnz     loc_1800E14FB
0x1800e15c4  mov     rcx, r12; unsigned __int16 *
0x1800e15c7  mov     [rbp+57h+lpTargetPath], r15
0x1800e15cb  mov     rsi, r15
0x1800e15ce  call    ?LcmRemoveColon@@YAXPEAG@Z; LcmRemoveColon(ushort *)
0x1800e15d3  mov     rdx, r12; lpString2
0x1800e15d6  mov     rcx, r15; lpString1
0x1800e15d9  call    cs:__imp_lstrcmpiW
0x1800e15df  xor     ecx, ecx
0x1800e15e1  test    eax, eax
0x1800e15e3  jnz     short loc_1800E1610
0x1800e15e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800e15e9  inc     rax
0x1800e15ec  cmp     [rsi+rax*2], cx
0x1800e15f0  jnz     short loc_1800E15E9
0x1800e15f2  lea     rsi, [rsi+rax*2]
0x1800e15f6  mov     rdx, r12; lpString2
0x1800e15f9  add     rsi, 2
0x1800e15fd  mov     rcx, rsi; lpString1
0x1800e1600  call    cs:__imp_lstrcmpiW
0x1800e1606  xor     ecx, ecx
0x1800e1608  test    eax, eax
0x1800e160a  jz      short loc_1800E15E5
0x1800e160c  mov     [rbp+57h+lpTargetPath], rsi
0x1800e1610  mov     ecx, 208h
0x1800e1615  call    cs:__imp_DllAllocSplMem
0x1800e161b  mov     rsi, rax
0x1800e161e  xor     eax, eax
0x1800e1620  test    rsi, rsi
0x1800e1623  jz      loc_1800E14FB
0x1800e1629  mov     r9, [rdi+18h]
0x1800e162d  lea     r8, aNonspooled; "NONSPOOLED_"
0x1800e1634  mov     edx, 104h; unsigned int
0x1800e1639  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rax
0x1800e163e  mov     rcx, rsi; unsigned __int16 *
0x1800e1641  call    ?StrNCatBuffW@@YAKPEAGIZZ; StrNCatBuffW(ushort *,uint,...)
0x1800e1646  test    eax, eax
0x1800e1648  jnz     loc_1800E14FB
0x1800e164e  mov     rcx, rsi; unsigned __int16 *
0x1800e1651  call    ?LcmRemoveColon@@YAXPEAG@Z; LcmRemoveColon(ushort *)
0x1800e1656  xor     r8d, r8d; lpTargetPath
0x1800e1659  mov     rdx, rsi; lpDeviceName
0x1800e165c  lea     ecx, [r8+2]; dwFlags
0x1800e1660  call    cs:__imp_DefineDosDeviceW
0x1800e1666  mov     r8, [rbp+57h+lpTargetPath]; lpTargetPath
0x1800e166a  mov     rdx, rsi; lpDeviceName
0x1800e166d  mov     ecx, 1; dwFlags
0x1800e1672  call    cs:__imp_DefineDosDeviceW
0x1800e1678  mov     rcx, [rbp+57h+hToken]; hToken
0x1800e167c  call    cs:__imp_ImpersonatePrinterClient
0x1800e1682  mov     r9, [rdi+18h]
0x1800e1686  lea     r8, aNonspooled_0; "\\\\.\\NONSPOOLED_"
0x1800e168d  mov     edx, 104h; unsigned int
0x1800e1692  mov     qword ptr [rsp+0D0h+dwCreationDisposition], rbx
0x1800e1697  mov     rcx, rsi; unsigned __int16 *
0x1800e169a  call    ?StrNCatBuffW@@YAKPEAGIZZ; StrNCatBuffW(ushort *,uint,...)
0x1800e169f  test    eax, eax
0x1800e16a1  jnz     loc_1800E150E
0x1800e16a7  mov     rcx, rsi; unsigned __int16 *
0x1800e16aa  call    ?LcmRemoveColon@@YAXPEAG@Z; LcmRemoveColon(ushort *)
0x1800e16af  xor     r9d, r9d; lpSecurityAttributes
0x1800e16b2  mov     [rsp+0D0h+hTemplateFile], rbx; hTemplateFile
0x1800e16b7  mov     [rsp+0D0h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x1800e16bf  mov     edx, 0C0000000h; dwDesiredAccess
0x1800e16c4  mov     rcx, rsi; lpFileName
0x1800e16c7  mov     [rsp+0D0h+dwCreationDisposition], 4; dwCreationDisposition
0x1800e16cf  lea     r8d, [r9+1]; dwShareMode
0x1800e16d3  call    cs:__imp_CreateFileW
0x1800e16d9  mov     [rdi+20h], rax
0x1800e16dd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800e16e1  jnz     short loc_1800E170F
0x1800e16e3  call    cs:__imp_GetLastError
0x1800e16e9  mov     r9, rsi
0x1800e16ec  lea     rdx, aCreatefileFail_0; "CreateFile() failed!!!  GLE[%d]  portna"...
0x1800e16f3  mov     r8d, eax
0x1800e16f6  lea     rcx, aValidatedosdev_0; "ValidateDosDevicePort"
0x1800e16fd  call    ?WriteDbgTraceError@LocalMonTelemetry@@SAXPEADPEAGZZ; LocalMonTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800e1702  mov     rcx, rdi; struct _LCMINIPORT *
0x1800e1705  call    ?RemoveDosDeviceDefinition@@YAHPEAU_LCMINIPORT@@@Z; RemoveDosDeviceDefinition(_LCMINIPORT *)
0x1800e170a  jmp     loc_1800E150E
0x1800e170f  or      dword ptr [rdi+2Ch], 1
0x1800e1713  mov     rcx, rax; hFile
0x1800e1716  call    cs:__imp_SetEndOfFile
0x1800e171c  mov     rcx, [rdi+18h]; unsigned __int16 *
0x1800e1720  call    ?IsCOMPort@@YAHPEAG@Z; IsCOMPort(ushort *)
0x1800e1725  test    eax, eax
0x1800e1727  jz      short loc_1800E179C
0x1800e1729  mov     rcx, [rdi+20h]; hFile
0x1800e172d  lea     rdx, [rbp+57h+DCB]; lpDCB
0x1800e1731  call    cs:__imp_GetCommState
0x1800e1737  mov     r8, [rdi+20h]
0x1800e173b  test    eax, eax
0x1800e173d  jz      short loc_1800E1793
0x1800e173f  lea     rdx, [rbp+57h+CommTimeouts]; lpCommTimeouts
0x1800e1743  mov     rcx, r8; hFile
0x1800e1746  call    cs:__imp_GetCommTimeouts
0x1800e174c  mov     rcx, [rdi+18h]; lpValueName
0x1800e1750  lea     r8, [rbp+57h+CommTimeouts]; struct _COMMTIMEOUTS *
0x1800e1754  lea     rdx, [rbp+57h+DCB]; lpDCB
0x1800e1758  call    ?GetIniCommValues@@YAHPEAGPEAU_DCB@@PEAU_COMMTIMEOUTS@@@Z; GetIniCommValues(ushort *,_DCB *,_COMMTIMEOUTS *)
0x1800e175d  mov     rcx, [rdi+20h]; hFile
0x1800e1761  lea     rdx, [rbp+57h+DCB]; lpDCB
0x1800e1765  call    cs:__imp_SetCommState
0x1800e176b  mov     eax, cs:?g_COMWriteTimeoutConstant_ms@@3KA; ulong g_COMWriteTimeoutConstant_ms
0x1800e1771  lea     rdx, [rbp+57h+CommTimeouts]; lpCommTimeouts
0x1800e1775  mov     rcx, [rdi+20h]; hFile
0x1800e1779  mov     [rbp+57h+CommTimeouts.WriteTotalTimeoutConstant], eax
0x1800e177c  mov     qword ptr [rbp+57h+CommTimeouts.ReadTotalTimeoutConstant], 1388h
0x1800e1784  mov     [rbp+57h+CommTimeouts.ReadIntervalTimeout], 0C8h
0x1800e178b  call    cs:__imp_SetCommTimeouts
0x1800e1791  jmp     short loc_1800E1806
0x1800e1793  lea     rdx, aGetcommstateFa; "GetCommState failed for pIniPort->hFile"...
0x1800e179a  jmp     short loc_1800E1817
0x1800e179c  mov     rcx, [rdi+18h]; unsigned __int16 *
0x1800e17a0  call    ?IsLPTPort@@YAHPEAG@Z; IsLPTPort(ushort *)
0x1800e17a5  test    eax, eax
0x1800e17a7  jz      short loc_1800E1823
0x1800e17a9  mov     rcx, [rdi+20h]; hFile
0x1800e17ad  lea     rdx, [rbp+57h+CommTimeouts]; lpCommTimeouts
0x1800e17b1  call    cs:__imp_GetCommTimeouts
0x1800e17b7  test    eax, eax
0x1800e17b9  jz      short loc_1800E180C
0x1800e17bb  lea     rcx, [rbp+57h+CommTimeouts.WriteTotalTimeoutConstant]; unsigned int *
0x1800e17bf  call    ?GetTransmissionRetryTimeoutFromRegistry@@YAXPEAK@Z; GetTransmissionRetryTimeoutFromRegistry(ulong *)
0x1800e17c4  imul    eax, [rbp+57h+CommTimeouts.WriteTotalTimeoutConstant], 3E8h
0x1800e17cb  lea     rdx, [rbp+57h+CommTimeouts]; lpCommTimeouts
0x1800e17cf  mov     rcx, [rdi+20h]; hFile
0x1800e17d3  mov     [rbp+57h+CommTimeouts.WriteTotalTimeoutConstant], eax
0x1800e17d6  call    cs:__imp_SetCommTimeouts
0x1800e17dc  call    cs:__imp_RevertToPrinterSelf
0x1800e17e2  mov     rcx, [rdi+20h]
0x1800e17e6  lea     r8, ?HandleLptQueryRemove@@YAKPEAX@Z; HandleLptQueryRemove(void *)
0x1800e17ed  mov     rdx, rdi
0x1800e17f0  mov     rbx, rax
0x1800e17f3  call    cs:__imp_SplRegisterForDeviceEvents
0x1800e17f9  mov     rcx, rbx; hToken
0x1800e17fc  mov     [rdi+60h], rax
0x1800e1800  call    cs:__imp_ImpersonatePrinterClient
0x1800e1806  or      dword ptr [rdi+2Ch], 2
0x1800e180a  jmp     short loc_1800E1823
0x1800e180c  mov     r8, [rdi+20h]
0x1800e1810  lea     rdx, aGetcommtimeout; "GetCommTimeouts failed for pIniPort->hF"...
0x1800e1817  lea     rcx, aValidatedosdev_0; "ValidateDosDevicePort"
0x1800e181e  call    ?WriteDbgTraceInfo@LocalMonTelemetry@@SAXPEADPEAGZZ; LocalMonTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800e1823  mov     rcx, [rdi+38h]
0x1800e1827  call    cs:__imp_DllFreeSplStr
0x1800e182d  mov     [rdi+38h], r14
0x1800e1831  mov     ebx, 1
0x1800e1836  jmp     loc_1800E151C
```
