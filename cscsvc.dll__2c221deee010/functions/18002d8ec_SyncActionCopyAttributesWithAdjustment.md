# SyncActionCopyAttributesWithAdjustment

- ea: `0x18002d8ec`
- end: `0x18002e1d5`
- name: `SyncActionCopyAttributesWithAdjustment`
- size: `2281`
- prototype: `__int64 __usercall@<rax>(HANDLE hHandle@<rcx>, HANDLE FileHandle@<rdx>, char, int, __int64, __int64)`
- caller_count: `6`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180077bc0`
- `0x180078390`
- `0x180078900`
- `0x180079250`
- `0x18007d2b0`
- `0x18007d6d8`

## callees

- `0x18002d8ec`
- `0x180030634`
- `0x1800360c0`
- `0x180039610`
- `0x18003c460`
- `0x18003e928`
- `0x1800769e0`
- `0x18007dd7c`
- `0x18007e294`
- `0x18007e450`

## import_xrefs

- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x18002db37`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x18002dc3b`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x18002dd38`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x18002de43`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x18002df47`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x18002e044`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x18002db37`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x18002dc3b`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x18002dd38`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x18002de43`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x18002df47`
- `KERNEL32!SystemTimeToTzSpecificLocalTime` at `0x18002e044`
- `KERNEL32!FileTimeToSystemTime` at `0x18002db21`
- `KERNEL32!FileTimeToSystemTime` at `0x18002dc25`
- `KERNEL32!FileTimeToSystemTime` at `0x18002dd22`
- `KERNEL32!FileTimeToSystemTime` at `0x18002de2d`
- `KERNEL32!FileTimeToSystemTime` at `0x18002df31`
- `KERNEL32!FileTimeToSystemTime` at `0x18002e02e`
- `KERNEL32!FileTimeToSystemTime` at `0x18002db21`
- `KERNEL32!FileTimeToSystemTime` at `0x18002dc25`
- `KERNEL32!FileTimeToSystemTime` at `0x18002dd22`
- `KERNEL32!FileTimeToSystemTime` at `0x18002de2d`
- `KERNEL32!FileTimeToSystemTime` at `0x18002df31`
- `KERNEL32!FileTimeToSystemTime` at `0x18002e02e`

## string_xrefs

- `0x18002db99`: `SyncActionCompareChangeDesc [%ws]: LAST KNOWN : %02d/%02d/%d  %02d:%02d:%02d.%d`
- `0x18002de7b`: `SyncActionCompareChangeDesc [%ws]: LAST KNOWN : %02d/%02d/%d  %02d:%02d:%02d.%d`
- `0x18002dc96`: `SyncActionCompareChangeDesc [%ws]:    CURRENT : %02d/%02d/%d  %02d:%02d:%02d.%d`
- `0x18002df78`: `SyncActionCompareChangeDesc [%ws]:    CURRENT : %02d/%02d/%d  %02d:%02d:%02d.%d`
- `0x18002dd93`: `SyncActionCompareChangeDesc [%ws]: ENUM START : %02d/%02d/%d  %02d:%02d:%02d.%d`
- `0x18002e075`: `SyncActionCompareChangeDesc [%ws]: ENUM START : %02d/%02d/%d  %02d:%02d:%02d.%d`
- `0x18002d977`: `SyncActionCopyAttributesWithAdjustment: SourceHandle: 0x%p TargetHandle: 0x%p  ChangeDesc: 0x%p  RoundWriteTimeToSeconds: %d  TimeAdjustment: %d  pAdjustedLastWriteTime: 0x%p`
- `0x18002dae0`: `SyncActionCopyAttributesWithAdjustment: ChangeDesc time different from local time!!`
- `0x18002db50`: `SyncActionCopyAttributesWithAdjustment: ChangeTime: `
- `0x18002de5c`: `SyncActionCopyAttributesWithAdjustment: LastWriteTime: `
- `0x18002e182`: `SyncActionCopyAttributesWithAdjustment: 0x%08x ( EE = %u )`

## pseudocode

```c
__int64 __fastcall SyncActionCopyAttributesWithAdjustment(
        HANDLE hHandle,
        HANDLE FileHandle,
        FILETIME *a3,
        int a4,
        char a5,
        unsigned int a6,
        _BYTE *a7,
        _QWORD *a8)
{
  __int64 v12; // rdx
  __int64 v13; // r8
  int BasicInformation; // ebx
  unsigned int v15; // edi
  FILETIME v16; // rax
  int v17; // ecx
  __int64 v19; // [rsp+20h] [rbp-E0h]
  __int64 v21; // [rsp+28h] [rbp-D8h]
  __int64 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  __int64 v25; // [rsp+40h] [rbp-C0h]
  struct _SYSTEMTIME LocalTime; // [rsp+68h] [rbp-98h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+78h] [rbp-88h] BYREF
  __int128 v28; // [rsp+88h] [rbp-78h] BYREF
  FILETIME FileTime[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v30; // [rsp+A8h] [rbp-58h]
  __int128 v31; // [rsp+B0h] [rbp-50h] BYREF
  FILETIME v32[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v33; // [rsp+D0h] [rbp-30h]
  _QWORD FileInformation[5]; // [rsp+D8h] [rbp-28h] BYREF

  v30 = 0;
  v33 = 0;
  v28 = 0;
  *(_OWORD *)&FileTime[0].dwLowDateTime = 0;
  v31 = 0;
  *(_OWORD *)&v32[0].dwLowDateTime = 0;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    SyncTraceOutputInternal(
      L"SyncActionCopyAttributesWithAdjustment: SourceHandle: 0x%p TargetHandle: 0x%p  ChangeDesc: 0x%p  RoundWriteTimeToS"
       "econds: %d  TimeAdjustment: %d  pAdjustedLastWriteTime: 0x%p",
      hHandle,
      FileHandle,
      a3,
      a4,
      a6,
      a8);
    WPP_SF_qqqddq(*((_QWORD *)WPP_GLOBAL_Control + 12), v12, v13, hHandle, FileHandle, a3, a4, a6, a8);
  }
  if ( a8 )
    *a8 = 0;
  BasicInformation = SyncGetBasicInformation(hHandle, &v31);
  if ( BasicInformation >= 0 )
  {
    FileTime[1] = v32[1];
    v16 = v32[0];
    FileTime[0] = v32[0];
    v28 = (unsigned __int64)v31;
    v30 = (unsigned int)v33;
    if ( a3 )
    {
      v16 = a3[2];
      FileTime[1] = a3[1];
      v17 = (a3[3].dwLowDateTime ^ v33) & 0x4017;
      FileTime[0] = v16;
      LODWORD(v30) = v33 ^ v17;
    }
    if ( a4 )
    {
      SyncActionRoundUpValue(FileTime, (unsigned int)(10000000 * a4));
      SyncActionRoundUpValue(&v28, (unsigned int)(10000000 * a4));
      v16 = FileTime[0];
      if ( *(_QWORD *)&a3[2] != *(_QWORD *)FileTime || (_QWORD)v31 != (_QWORD)v28 )
      {
        FileInformation[0] = v28;
        FileInformation[1] = -1;
        FileInformation[3] = -1;
        FileInformation[4] = 0;
        a3[2] = FileTime[0];
        FileInformation[2] = v16;
        BasicInformation = SyncSetBasicInformation(hHandle, FileInformation);
        if ( BasicInformation < 0 )
        {
          v15 = 1139;
          goto LABEL_65;
        }
        v16 = FileTime[0];
      }
    }
    if ( *(_QWORD *)&FileTime[1] != *(_QWORD *)&v32[1] || v16 != *(_QWORD *)v32 )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
      {
        SyncTraceOutputInternal(L"SyncActionCopyAttributesWithAdjustment: ChangeDesc time different from local time!!");
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 42, WPP_6245c1b01f713a032f327efa2846a355_Traceguids);
      }
      LocalTime = 0;
      SystemTime = 0;
      if ( !FileTimeToSystemTime(&FileTime[1], &SystemTime)
        || !SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime) )
      {
        LocalTime = 0;
      }
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        LODWORD(v25) = LocalTime.wMilliseconds;
        LODWORD(v24) = LocalTime.wSecond;
        LODWORD(v23) = LocalTime.wMinute;
        LODWORD(v21) = LocalTime.wHour;
        LODWORD(v19) = LocalTime.wYear;
        SyncTraceOutputInternal(
          L"SyncActionCompareChangeDesc [%ws]: LAST KNOWN : %02d/%02d/%d  %02d:%02d:%02d.%d",
          L"SyncActionCopyAttributesWithAdjustment: ChangeTime: ",
          LocalTime.wMonth,
          LocalTime.wDay,
          v19,
          v21,
          v23,
          v24,
          v25);
        WPP_SF_Sddddddd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          10,
          LocalTime.wMinute,
          (unsigned int)L"SyncActionCopyAttributesWithAdjustment: ChangeTime: ",
          LocalTime.wMonth,
          LocalTime.wDay,
          LocalTime.wYear,
          LocalTime.wHour,
          LocalTime.wMinute,
          LocalTime.wSecond,
          LocalTime.wMilliseconds);
      }
      if ( !FileTimeToSystemTime(&v32[1], &SystemTime) || !SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime) )
        LocalTime = 0;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        LODWORD(v25) = LocalTime.wMilliseconds;
        LODWORD(v24) = LocalTime.wSecond;
        LODWORD(v23) = LocalTime.wMinute;
        LODWORD(v21) = LocalTime.wHour;
        LODWORD(v19) = LocalTime.wYear;
        SyncTraceOutputInternal(
          L"SyncActionCompareChangeDesc [%ws]:    CURRENT : %02d/%02d/%d  %02d:%02d:%02d.%d",
          L"SyncActionCopyAttributesWithAdjustment: ChangeTime: ",
          LocalTime.wMonth,
          LocalTime.wDay,
          v19,
          v21,
          v23,
          v24,
          v25);
        WPP_SF_Sddddddd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          11,
          LocalTime.wMinute,
          (unsigned int)L"SyncActionCopyAttributesWithAdjustment: ChangeTime: ",
          LocalTime.wMonth,
          LocalTime.wDay,
          LocalTime.wYear,
          LocalTime.wHour,
          LocalTime.wMinute,
          LocalTime.wSecond,
          LocalTime.wMilliseconds);
      }
      if ( !FileTimeToSystemTime(&v32[1], &SystemTime) || !SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime) )
        LocalTime = 0;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        LODWORD(v25) = LocalTime.wMilliseconds;
        LODWORD(v24) = LocalTime.wSecond;
        LODWORD(v23) = LocalTime.wMinute;
        LODWORD(v21) = LocalTime.wHour;
        LODWORD(v19) = LocalTime.wYear;
        SyncTraceOutputInternal(
          L"SyncActionCompareChangeDesc [%ws]: ENUM START : %02d/%02d/%d  %02d:%02d:%02d.%d",
          L"SyncActionCopyAttributesWithAdjustment: ChangeTime: ",
          LocalTime.wMonth,
          LocalTime.wDay,
          v19,
          v21,
          v23,
          v24,
          v25);
        WPP_SF_Sddddddd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          12,
          LocalTime.wMinute,
          (unsigned int)L"SyncActionCopyAttributesWithAdjustment: ChangeTime: ",
          LocalTime.wMonth,
          LocalTime.wDay,
          LocalTime.wYear,
          LocalTime.wHour,
          LocalTime.wMinute,
          LocalTime.wSecond,
          LocalTime.wMilliseconds);
      }
      LocalTime = 0;
      SystemTime = 0;
      if ( !FileTimeToSystemTime(FileTime, &SystemTime) || !SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime) )
        LocalTime = 0;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        LODWORD(v25) = LocalTime.wMilliseconds;
        LODWORD(v24) = LocalTime.wSecond;
        LODWORD(v23) = LocalTime.wMinute;
        LODWORD(v21) = LocalTime.wHour;
        LODWORD(v19) = LocalTime.wYear;
        SyncTraceOutputInternal(
          L"SyncActionCompareChangeDesc [%ws]: LAST KNOWN : %02d/%02d/%d  %02d:%02d:%02d.%d",
          L"SyncActionCopyAttributesWithAdjustment: LastWriteTime: ",
          LocalTime.wMonth,
          LocalTime.wDay,
          v19,
          v21,
          v23,
          v24,
          v25);
        WPP_SF_Sddddddd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          10,
          LocalTime.wMinute,
          (unsigned int)L"SyncActionCopyAttributesWithAdjustment: LastWriteTime: ",
          LocalTime.wMonth,
          LocalTime.wDay,
          LocalTime.wYear,
          LocalTime.wHour,
          LocalTime.wMinute,
          LocalTime.wSecond,
          LocalTime.wMilliseconds);
      }
      if ( !FileTimeToSystemTime(v32, &SystemTime) || !SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime) )
        LocalTime = 0;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        LODWORD(v25) = LocalTime.wMilliseconds;
        LODWORD(v24) = LocalTime.wSecond;
        LODWORD(v23) = LocalTime.wMinute;
        LODWORD(v21) = LocalTime.wHour;
        LODWORD(v19) = LocalTime.wYear;
        SyncTraceOutputInternal(
          L"SyncActionCompareChangeDesc [%ws]:    CURRENT : %02d/%02d/%d  %02d:%02d:%02d.%d",
          L"SyncActionCopyAttributesWithAdjustment: LastWriteTime: ",
          LocalTime.wMonth,
          LocalTime.wDay,
          v19,
          v21,
          v23,
          v24,
          v25);
        WPP_SF_Sddddddd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          11,
          LocalTime.wMinute,
          (unsigned int)L"SyncActionCopyAttributesWithAdjustment: LastWriteTime: ",
          LocalTime.wMonth,
          LocalTime.wDay,
          LocalTime.wYear,
          LocalTime.wHour,
          LocalTime.wMinute,
          LocalTime.wSecond,
          LocalTime.wMilliseconds);
      }
      if ( !FileTimeToSystemTime(v32, &SystemTime) || !SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime) )
        LocalTime = 0;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        LODWORD(v25) = LocalTime.wMilliseconds;
        LODWORD(v24) = LocalTime.wSecond;
        LODWORD(v23) = LocalTime.wMinute;
        LODWORD(v21) = LocalTime.wHour;
        LODWORD(v19) = LocalTime.wYear;
        SyncTraceOutputInternal(
          L"SyncActionCompareChangeDesc [%ws]: ENUM START : %02d/%02d/%d  %02d:%02d:%02d.%d",
          L"SyncActionCopyAttributesWithAdjustment: LastWriteTime: ",
          LocalTime.wMonth,
          LocalTime.wDay,
          v19,
          v21,
          v23,
          v24,
          v25);
        WPP_SF_Sddddddd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          12,
          LocalTime.wMinute,
          (unsigned int)L"SyncActionCopyAttributesWithAdjustment: LastWriteTime: ",
          LocalTime.wMonth,
          LocalTime.wDay,
          LocalTime.wYear,
          LocalTime.wHour,
          LocalTime.wMinute,
          LocalTime.wSecond,
          LocalTime.wMilliseconds);
      }
      v16 = FileTime[0];
    }
    FileTime[0] = (FILETIME)(*(_QWORD *)&v16 - a6);
    if ( a5 && (v30 & 1) != 0 )
    {
      LODWORD(v30) = v30 & 0xFFFFFFFE;
      *a7 = 1;
    }
    BasicInformation = SyncSetBasicInformation(FileHandle, &v28);
    if ( BasicInformation >= 0 )
    {
      v15 = 0;
      if ( a8 )
        *a8 = FileTime[0];
    }
    else
    {
      v15 = 1179;
    }
  }
  else
  {
    v15 = 1085;
  }
LABEL_65:
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(
      L"SyncActionCopyAttributesWithAdjustment: 0x%08x ( EE = %u )",
      (unsigned int)BasicInformation,
      v15);
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      43,
      WPP_6245c1b01f713a032f327efa2846a355_Traceguids,
      (unsigned int)BasicInformation,
      v15);
  }
  return (unsigned int)BasicInformation;
}

```

## disassembly

```asm
0x18002d8ec  push    rbp
0x18002d8ee  push    rbx
0x18002d8ef  push    rsi
0x18002d8f0  push    rdi
0x18002d8f1  push    r12
0x18002d8f3  push    r13
0x18002d8f5  push    r14
0x18002d8f7  push    r15
0x18002d8f9  lea     rbp, [rsp-18h]
0x18002d8fe  sub     rsp, 118h
0x18002d905  mov     rax, cs:__security_cookie
0x18002d90c  xor     rax, rsp
0x18002d90f  mov     [rbp+50h+var_50], rax
0x18002d913  mov     rax, [rbp+50h+arg_30]
0x18002d91a  xorps   xmm0, xmm0
0x18002d91d  mov     r15, [rbp+50h+arg_38]
0x18002d924  xorps   xmm1, xmm1
0x18002d927  mov     [rsp+150h+var_F0], rax
0x18002d92c  mov     esi, r9d
0x18002d92f  xor     eax, eax
0x18002d931  mov     rdi, r8
0x18002d934  mov     [rbp+50h+var_A8], rax
0x18002d938  mov     r13, rdx
0x18002d93b  mov     [rbp+50h+var_80], rax
0x18002d93f  mov     r14, rcx
0x18002d942  movups  [rbp+50h+var_C8], xmm0
0x18002d946  movups  xmmword ptr [rbp+50h+FileTime.dwLowDateTime], xmm0
0x18002d94a  movups  [rbp+50h+var_A0], xmm1
0x18002d94e  movups  xmmword ptr [rbp+50h+var_90.dwLowDateTime], xmm1
0x18002d952  mov     rax, cs:WPP_GLOBAL_Control
0x18002d959  lea     rcx, WPP_GLOBAL_Control
0x18002d960  mov     r12d, [rbp+50h+arg_28]
0x18002d967  cmp     rax, rcx
0x18002d96a  jz      short loc_18002D9C1
0x18002d96c  test    byte ptr [rax+6Ch], 4
0x18002d970  jz      short loc_18002D9C1
0x18002d972  mov     [rsp+150h+var_120], r15
0x18002d977  lea     rcx, aSyncactioncopy_9; "SyncActionCopyAttributesWithAdjustment:"...
0x18002d97e  mov     dword ptr [rsp+150h+var_128], r12d
0x18002d983  mov     dword ptr [rsp+150h+var_130], r9d
0x18002d988  mov     r9, r8
0x18002d98b  mov     r8, rdx
0x18002d98e  mov     rdx, r14
0x18002d991  call    SyncTraceOutputInternal
0x18002d996  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d99d  mov     r9, r14
0x18002d9a0  mov     [rsp+150h+var_110], r15
0x18002d9a5  mov     dword ptr [rsp+150h+var_118], r12d
0x18002d9aa  mov     dword ptr [rsp+150h+var_120], esi
0x18002d9ae  mov     rcx, [rcx+60h]
0x18002d9b2  mov     [rsp+150h+var_128], rdi
0x18002d9b7  mov     [rsp+150h+var_130], r13
0x18002d9bc  call    WPP_SF_qqqddq
0x18002d9c1  test    r15, r15
0x18002d9c4  jz      short loc_18002D9CD
0x18002d9c6  mov     qword ptr [r15], 0
0x18002d9cd  lea     rdx, [rbp+50h+var_A0]; FileInformation
0x18002d9d1  mov     rcx, r14; hHandle
0x18002d9d4  call    SyncGetBasicInformation
0x18002d9d9  mov     ebx, eax
0x18002d9db  test    eax, eax
0x18002d9dd  jns     short loc_18002D9E9
0x18002d9df  mov     edi, 43Dh
0x18002d9e4  jmp     loc_18002E166
0x18002d9e9  mov     rax, qword ptr [rbp+50h+var_90.dwLowDateTime+8]
0x18002d9ed  mov     rcx, qword ptr [rbp+50h+var_A0]
0x18002d9f1  mov     rdx, [rbp+50h+var_80]
0x18002d9f5  mov     qword ptr [rbp+50h+FileTime.dwLowDateTime+8], rax
0x18002d9f9  mov     rax, qword ptr [rbp+50h+var_90.dwLowDateTime]
0x18002d9fd  mov     qword ptr [rbp+50h+FileTime.dwLowDateTime], rax
0x18002da01  mov     qword ptr [rbp+50h+var_C8+8], 0
0x18002da09  mov     dword ptr [rbp+50h+var_A8+4], 0
0x18002da10  mov     qword ptr [rbp+50h+var_C8], rcx
0x18002da14  mov     dword ptr [rbp+50h+var_A8], edx
0x18002da17  test    rdi, rdi
0x18002da1a  jz      short loc_18002DA3C
0x18002da1c  mov     rcx, [rdi+8]
0x18002da20  mov     rax, [rdi+10h]
0x18002da24  mov     qword ptr [rbp+50h+FileTime.dwLowDateTime+8], rcx
0x18002da28  mov     ecx, edx
0x18002da2a  xor     ecx, [rdi+18h]
0x18002da2d  and     ecx, 4017h
0x18002da33  mov     qword ptr [rbp+50h+FileTime.dwLowDateTime], rax
0x18002da37  xor     ecx, edx
0x18002da39  mov     dword ptr [rbp+50h+var_A8], ecx
0x18002da3c  test    esi, esi
0x18002da3e  jz      short loc_18002DAB0
0x18002da40  imul    ebx, esi, 989680h
0x18002da46  lea     rcx, [rbp+50h+FileTime]
0x18002da4a  mov     edx, ebx
0x18002da4c  call    SyncActionRoundUpValue
0x18002da51  mov     edx, ebx
0x18002da53  lea     rcx, [rbp+50h+var_C8]
0x18002da57  call    SyncActionRoundUpValue
0x18002da5c  mov     rax, qword ptr [rbp+50h+FileTime.dwLowDateTime]
0x18002da60  mov     rdx, qword ptr [rbp+50h+var_C8]
0x18002da64  cmp     [rdi+10h], rax
0x18002da68  jnz     short loc_18002DA70
0x18002da6a  cmp     qword ptr [rbp+50h+var_A0], rdx
0x18002da6e  jz      short loc_18002DAB0
0x18002da70  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002da74  mov     [rbp+50h+FileInformation], rdx
0x18002da78  mov     [rbp+50h+var_70], rcx
0x18002da7c  lea     rdx, [rbp+50h+FileInformation]; FileInformation
0x18002da80  mov     [rbp+50h+var_60], rcx
0x18002da84  mov     rcx, r14; FileHandle
0x18002da87  mov     [rbp+50h+var_58], 0
0x18002da8f  mov     [rdi+10h], rax
0x18002da93  mov     [rbp+50h+var_68], rax
0x18002da97  call    SyncSetBasicInformation
0x18002da9c  mov     ebx, eax
0x18002da9e  test    eax, eax
0x18002daa0  jns     short loc_18002DAAC
0x18002daa2  mov     edi, 473h
0x18002daa7  jmp     loc_18002E166
0x18002daac  mov     rax, qword ptr [rbp+50h+FileTime.dwLowDateTime]
0x18002dab0  mov     rcx, qword ptr [rbp+50h+var_90.dwLowDateTime+8]
0x18002dab4  mov     sil, 1
0x18002dab7  cmp     qword ptr [rbp+50h+FileTime.dwLowDateTime+8], rcx
0x18002dabb  jnz     short loc_18002DAC7
0x18002dabd  cmp     rax, qword ptr [rbp+50h+var_90.dwLowDateTime]
0x18002dac1  jz      loc_18002E11D
0x18002dac7  mov     rax, cs:WPP_GLOBAL_Control
0x18002dace  lea     rbx, WPP_GLOBAL_Control
0x18002dad5  cmp     rax, rbx
0x18002dad8  jz      short loc_18002DB08
0x18002dada  test    byte ptr [rax+6Ch], 2
0x18002dade  jz      short loc_18002DB08
0x18002dae0  lea     rcx, aSyncactioncopy_7; "SyncActionCopyAttributesWithAdjustment:"...
0x18002dae7  call    SyncTraceOutputInternal
0x18002daec  mov     rcx, cs:WPP_GLOBAL_Control
0x18002daf3  lea     r8, WPP_6245c1b01f713a032f327efa2846a355_Traceguids
0x18002dafa  mov     edx, 2Ah ; '*'
0x18002daff  mov     rcx, [rcx+60h]
0x18002db03  call    WPP_SF_
0x18002db08  xorps   xmm0, xmm0
0x18002db0b  lea     rdx, [rsp+150h+SystemTime]; lpSystemTime
0x18002db10  xorps   xmm1, xmm1
0x18002db13  lea     rcx, [rbp+50h+FileTime.dwLowDateTime+8]; lpFileTime
0x18002db17  movups  xmmword ptr [rsp+150h+LocalTime.wYear], xmm0
0x18002db1c  movups  xmmword ptr [rsp+150h+SystemTime.wYear], xmm1
0x18002db21  call    cs:__imp_FileTimeToSystemTime
0x18002db27  test    eax, eax
0x18002db29  jz      short loc_18002DB41
0x18002db2b  lea     r8, [rsp+150h+LocalTime]; lpLocalTime
0x18002db30  xor     ecx, ecx; lpTimeZoneInformation
0x18002db32  lea     rdx, [rsp+150h+SystemTime]; lpUniversalTime
0x18002db37  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x18002db3d  test    eax, eax
0x18002db3f  jnz     short loc_18002DB49
0x18002db41  xorps   xmm0, xmm0
0x18002db44  movups  xmmword ptr [rsp+150h+LocalTime.wYear], xmm0
0x18002db49  mov     rax, cs:WPP_GLOBAL_Control
0x18002db50  lea     r14, aSyncactioncopy_43; "SyncActionCopyAttributesWithAdjustment:"...
0x18002db57  cmp     rax, rbx
0x18002db5a  jz      loc_18002DC1C
0x18002db60  test    [rax+6Ch], sil
0x18002db64  jz      loc_18002DC1C
0x18002db6a  movzx   ecx, [rsp+150h+LocalTime.wSecond]
0x18002db6f  movzx   edx, [rsp+150h+LocalTime.wMinute]
0x18002db74  movzx   eax, [rsp+150h+LocalTime.wMilliseconds]
0x18002db79  movzx   r10d, [rsp+150h+LocalTime.wHour]
0x18002db7f  movzx   r11d, [rsp+150h+LocalTime.wYear]
0x18002db85  movzx   r9d, [rsp+150h+LocalTime.wDay]
0x18002db8b  movzx   r8d, [rsp+150h+LocalTime.wMonth]
0x18002db91  mov     dword ptr [rsp+150h+var_110], eax
0x18002db95  mov     dword ptr [rsp+150h+var_118], ecx
0x18002db99  lea     rcx, aSyncactioncomp_0; "SyncActionCompareChangeDesc [%ws]: LAST"...
0x18002dba0  mov     dword ptr [rsp+150h+var_120], edx
0x18002dba4  mov     rdx, r14
0x18002dba7  mov     dword ptr [rsp+150h+var_128], r10d
0x18002dbac  mov     dword ptr [rsp+150h+var_130], r11d
0x18002dbb1  call    SyncTraceOutputInternal
0x18002dbb6  movzx   ecx, [rsp+150h+LocalTime.wSecond]
0x18002dbbb  mov     edx, 0Ah
0x18002dbc0  movzx   r9d, [rsp+150h+LocalTime.wHour]
0x18002dbc6  movzx   eax, [rsp+150h+LocalTime.wMilliseconds]
0x18002dbcb  movzx   r8d, [rsp+150h+LocalTime.wMinute]
0x18002dbd1  movzx   r10d, [rsp+150h+LocalTime.wYear]
0x18002dbd7  movzx   r11d, [rsp+150h+LocalTime.wDay]
0x18002dbdd  movzx   ebx, [rsp+150h+LocalTime.wMonth]
0x18002dbe2  mov     [rsp+150h+var_100], eax
0x18002dbe6  mov     [rsp+150h+var_108], ecx
0x18002dbea  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dbf1  mov     dword ptr [rsp+150h+var_110], r8d
0x18002dbf6  mov     dword ptr [rsp+150h+var_118], r9d
0x18002dbfb  mov     r9, r14
0x18002dbfe  mov     dword ptr [rsp+150h+var_120], r10d
0x18002dc03  mov     rcx, [rcx+60h]
0x18002dc07  mov     dword ptr [rsp+150h+var_128], r11d
0x18002dc0c  mov     dword ptr [rsp+150h+var_130], ebx
0x18002dc10  call    WPP_SF_Sddddddd
0x18002dc15  lea     rbx, WPP_GLOBAL_Control
0x18002dc1c  lea     rdx, [rsp+150h+SystemTime]; lpSystemTime
0x18002dc21  lea     rcx, [rbp+50h+var_90.dwLowDateTime+8]; lpFileTime
0x18002dc25  call    cs:__imp_FileTimeToSystemTime
0x18002dc2b  test    eax, eax
0x18002dc2d  jz      short loc_18002DC45
0x18002dc2f  lea     r8, [rsp+150h+LocalTime]; lpLocalTime
0x18002dc34  xor     ecx, ecx; lpTimeZoneInformation
0x18002dc36  lea     rdx, [rsp+150h+SystemTime]; lpUniversalTime
0x18002dc3b  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x18002dc41  test    eax, eax
0x18002dc43  jnz     short loc_18002DC4D
0x18002dc45  xorps   xmm0, xmm0
0x18002dc48  movups  xmmword ptr [rsp+150h+LocalTime.wYear], xmm0
0x18002dc4d  mov     rax, cs:WPP_GLOBAL_Control
0x18002dc54  cmp     rax, rbx
0x18002dc57  jz      loc_18002DD19
0x18002dc5d  test    [rax+6Ch], sil
0x18002dc61  jz      loc_18002DD19
0x18002dc67  movzx   ecx, [rsp+150h+LocalTime.wSecond]
0x18002dc6c  movzx   edx, [rsp+150h+LocalTime.wMinute]
0x18002dc71  movzx   eax, [rsp+150h+LocalTime.wMilliseconds]
0x18002dc76  movzx   r10d, [rsp+150h+LocalTime.wHour]
0x18002dc7c  movzx   r11d, [rsp+150h+LocalTime.wYear]
0x18002dc82  movzx   r9d, [rsp+150h+LocalTime.wDay]
0x18002dc88  movzx   r8d, [rsp+150h+LocalTime.wMonth]
0x18002dc8e  mov     dword ptr [rsp+150h+var_110], eax
0x18002dc92  mov     dword ptr [rsp+150h+var_118], ecx
0x18002dc96  lea     rcx, aSyncactioncomp_5; "SyncActionCompareChangeDesc [%ws]:    C"...
0x18002dc9d  mov     dword ptr [rsp+150h+var_120], edx
0x18002dca1  mov     rdx, r14
0x18002dca4  mov     dword ptr [rsp+150h+var_128], r10d
0x18002dca9  mov     dword ptr [rsp+150h+var_130], r11d
0x18002dcae  call    SyncTraceOutputInternal
0x18002dcb3  movzx   ecx, [rsp+150h+LocalTime.wSecond]
0x18002dcb8  mov     edx, 0Bh
0x18002dcbd  movzx   r9d, [rsp+150h+LocalTime.wHour]
0x18002dcc3  movzx   eax, [rsp+150h+LocalTime.wMilliseconds]
0x18002dcc8  movzx   r8d, [rsp+150h+LocalTime.wMinute]
0x18002dcce  movzx   r10d, [rsp+150h+LocalTime.wYear]
0x18002dcd4  movzx   r11d, [rsp+150h+LocalTime.wDay]
0x18002dcda  movzx   ebx, [rsp+150h+LocalTime.wMonth]
0x18002dcdf  mov     [rsp+150h+var_100], eax
0x18002dce3  mov     [rsp+150h+var_108], ecx
0x18002dce7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dcee  mov     dword ptr [rsp+150h+var_110], r8d
0x18002dcf3  mov     dword ptr [rsp+150h+var_118], r9d
0x18002dcf8  mov     r9, r14
0x18002dcfb  mov     dword ptr [rsp+150h+var_120], r10d
0x18002dd00  mov     rcx, [rcx+60h]
0x18002dd04  mov     dword ptr [rsp+150h+var_128], r11d
0x18002dd09  mov     dword ptr [rsp+150h+var_130], ebx
0x18002dd0d  call    WPP_SF_Sddddddd
0x18002dd12  lea     rbx, WPP_GLOBAL_Control
0x18002dd19  lea     rdx, [rsp+150h+SystemTime]; lpSystemTime
0x18002dd1e  lea     rcx, [rbp+50h+var_90.dwLowDateTime+8]; lpFileTime
0x18002dd22  call    cs:__imp_FileTimeToSystemTime
0x18002dd28  test    eax, eax
0x18002dd2a  jz      short loc_18002DD42
0x18002dd2c  lea     r8, [rsp+150h+LocalTime]; lpLocalTime
0x18002dd31  xor     ecx, ecx; lpTimeZoneInformation
0x18002dd33  lea     rdx, [rsp+150h+SystemTime]; lpUniversalTime
0x18002dd38  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x18002dd3e  test    eax, eax
0x18002dd40  jnz     short loc_18002DD4A
0x18002dd42  xorps   xmm0, xmm0
0x18002dd45  movups  xmmword ptr [rsp+150h+LocalTime.wYear], xmm0
0x18002dd4a  mov     rax, cs:WPP_GLOBAL_Control
0x18002dd51  cmp     rax, rbx
0x18002dd54  jz      loc_18002DE14
0x18002dd5a  test    [rax+6Ch], sil
0x18002dd5e  jz      loc_18002DE14
0x18002dd64  movzx   ecx, [rsp+150h+LocalTime.wSecond]
0x18002dd69  movzx   edx, [rsp+150h+LocalTime.wMinute]
0x18002dd6e  movzx   eax, [rsp+150h+LocalTime.wMilliseconds]
0x18002dd73  movzx   r10d, [rsp+150h+LocalTime.wHour]
0x18002dd79  movzx   r11d, [rsp+150h+LocalTime.wYear]
0x18002dd7f  movzx   r9d, [rsp+150h+LocalTime.wDay]
0x18002dd85  movzx   r8d, [rsp+150h+LocalTime.wMonth]
0x18002dd8b  mov     dword ptr [rsp+150h+var_110], eax
0x18002dd8f  mov     dword ptr [rsp+150h+var_118], ecx
0x18002dd93  lea     rcx, aSyncactioncomp_6; "SyncActionCompareChangeDesc [%ws]: ENUM"...
0x18002dd9a  mov     dword ptr [rsp+150h+var_120], edx
0x18002dd9e  mov     rdx, r14
0x18002dda1  mov     dword ptr [rsp+150h+var_128], r10d
0x18002dda6  mov     dword ptr [rsp+150h+var_130], r11d
0x18002ddab  call    SyncTraceOutputInternal
0x18002ddb0  movzx   ecx, [rsp+150h+LocalTime.wSecond]
0x18002ddb5  mov     edx, 0Ch
0x18002ddba  movzx   eax, [rsp+150h+LocalTime.wMilliseconds]
0x18002ddbf  mov     r9, r14
0x18002ddc2  movzx   r8d, [rsp+150h+LocalTime.wMinute]
0x18002ddc8  movzx   r10d, [rsp+150h+LocalTime.wHour]
0x18002ddce  movzx   r11d, [rsp+150h+LocalTime.wYear]
0x18002ddd4  movzx   ebx, [rsp+150h+LocalTime.wDay]
0x18002ddd9  movzx   edi, [rsp+150h+LocalTime.wMonth]
0x18002ddde  mov     [rsp+150h+var_100], eax
0x18002dde2  mov     [rsp+150h+var_108], ecx
0x18002dde6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dded  mov     dword ptr [rsp+150h+var_110], r8d
0x18002ddf2  mov     dword ptr [rsp+150h+var_118], r10d
0x18002ddf7  mov     dword ptr [rsp+150h+var_120], r11d
0x18002ddfc  mov     rcx, [rcx+60h]
0x18002de00  mov     dword ptr [rsp+150h+var_128], ebx
0x18002de04  mov     dword ptr [rsp+150h+var_130], edi
0x18002de08  call    WPP_SF_Sddddddd
0x18002de0d  lea     rbx, WPP_GLOBAL_Control
0x18002de14  xorps   xmm0, xmm0
  ... truncated ...
```
