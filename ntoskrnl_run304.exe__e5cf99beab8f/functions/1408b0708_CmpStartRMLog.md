# CmpStartRMLog

- ea: `0x1408b0708`
- end: `0x1408b0ccb`
- name: `CmpStartRMLog`
- size: `1475`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1408ad910`
- `0x1408b1044`

## callees

- `0x140227210`
- `0x1402f8270`
- `0x14051136c`
- `0x14073b510`
- `0x1408031c4`
- `0x140803404`
- `0x1408035e0`
- `0x1408af21c`
- `0x1408af8e4`
- `0x1408afccc`
- `0x1408b0708`
- `0x1408b2338`
- `0x1408eeff0`
- `0x14092bbb0`
- `0x140bae410`
- `0x140bae8e0`

## import_xrefs

- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x1408b0ade`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x1408b0ade`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1408b0b0c`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1408b0b2b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1408b0bdb`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1408b0c3a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1408b0b0c`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1408b0b2b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1408b0bdb`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1408b0c3a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsWriteRestartArea` at `0x1408b0bad`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsWriteRestartArea` at `0x1408b0bad`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsDeleteLogByPointer` at `0x1408b0bef`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsDeleteLogByPointer` at `0x1408b0bef`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsDeleteMarshallingArea` at `0x1408b0bfe`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsDeleteMarshallingArea` at `0x1408b0bfe`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnEqual` at `0x1408b0a24`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnEqual` at `0x1408b0b43`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnEqual` at `0x1408b0a24`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnEqual` at `0x1408b0b43`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadRestartArea` at `0x1408b09f1`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadRestartArea` at `0x1408b09f1`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1408b0993`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1408b09bb`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1408b0993`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1408b09bb`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x1408b0c11`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x1408b0c11`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x1408b0a9a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x1408b0a9a`

## pseudocode

```c
__int64 __fastcall CmpStartRMLog(__int64 a1, _OWORD *a2)
{
  PVOID v3; // r14
  NTSTATUS FileSecurityDescriptor; // ebx
  __int64 v6; // r8
  CLFS_INFORMATION *Pool2; // r13
  bool v8; // zf
  __int64 v9; // r15
  void *v10; // rsi
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v12; // r8
  __int64 v13; // rax
  int v14; // eax
  PVOID *v15; // rsi
  PLOG_FILE_OBJECT *v16; // r12
  __int64 v17; // rcx
  CLFS_INFORMATION *v18; // rax
  CLFS_INFORMATION *v19; // rbx
  FILE_OBJECT *v20; // rcx
  PVOID v21; // rcx
  NTSTATUS v22; // eax
  CLFS_LSN LastLsn; // rax
  CLFS_LSN v24; // rbx
  PVOID v25; // rcx
  NTSTATUS v26; // eax
  FILE_OBJECT *v27; // rcx
  int ppvReadContext; // [rsp+20h] [rbp-A9h]
  CLFS_LSN plsn2; // [rsp+50h] [rbp-79h] BYREF
  ULONG pcbWritten; // [rsp+58h] [rbp-71h] BYREF
  PVOID pvCursorContext; // [rsp+60h] [rbp-69h] BYREF
  PVOID pvReadContext; // [rsp+68h] [rbp-61h] BYREF
  ULONG pcbReadBuffer; // [rsp+70h] [rbp-59h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+78h] [rbp-51h] BYREF
  UNICODE_STRING v36; // [rsp+88h] [rbp-41h] BYREF
  ULONG pcbRestartBuffer; // [rsp+98h] [rbp-31h] BYREF
  PCUNICODE_STRING Source; // [rsp+A0h] [rbp-29h]
  PVOID ppvRestartBuffer; // [rsp+A8h] [rbp-21h] BYREF
  CLFS_LSN plsn; // [rsp+B0h] [rbp-19h] BYREF
  CLFS_LSN plsnPrevious; // [rsp+B8h] [rbp-11h] BYREF
  CLFS_LSN plsnUndoNext; // [rsp+C0h] [rbp-9h] BYREF
  PVOID ppvReadBuffer; // [rsp+C8h] [rbp-1h] BYREF
  CLFS_LSN plsnRecord; // [rsp+D0h] [rbp+7h] BYREF
  CLS_LSN pvRestartBuffer; // [rsp+D8h] [rbp+Fh] BYREF
  CLFS_LSN plsnFirst; // [rsp+E0h] [rbp+17h] BYREF
  char v47; // [rsp+130h] [rbp+67h]
  ULONG pcbInfoBuffer; // [rsp+140h] [rbp+77h] BYREF
  char v49; // [rsp+148h] [rbp+7Fh]

  *(_QWORD *)&UnicodeString.Length = 0;
  v3 = 0;
  UnicodeString.Buffer = 0;
  *(_QWORD *)&v36.Length = 0;
  v36.Buffer = 0;
  ppvRestartBuffer = 0;
  pcbRestartBuffer = 0;
  plsn.ullOffset = 0;
  pvCursorContext = 0;
  plsn2.ullOffset = 0;
  pcbWritten = 0;
  pvRestartBuffer.ullOffset = 0;
  pvReadContext = 0;
  v47 = 0;
  LOBYTE(pcbInfoBuffer) = 0;
  LockRMLog();
  if ( (*(_DWORD *)(a1 + 104) & 1) != 0 )
  {
    FileSecurityDescriptor = 0;
LABEL_5:
    ExReleaseResourceLite(*(PERESOURCE *)(a1 + 128));
    KeLeaveCriticalRegion();
    return (unsigned int)FileSecurityDescriptor;
  }
  Pool2 = (CLFS_INFORMATION *)ExAllocatePool2(256, 120, 538987843);
  if ( !Pool2 )
  {
    FileSecurityDescriptor = -1073741670;
    goto LABEL_5;
  }
  *(_DWORD *)(a1 + 104) |= 2u;
  v8 = (struct _LIST_ENTRY *)a1 == WheapPfaLock.Timer.TimerListEntry.Blink;
  *(_QWORD *)(a1 + 120) = CLFS_LSN_INVALID_EXT;
  if ( v8 )
  {
    if ( a2 )
      *(_OWORD *)(*(_QWORD *)(qword_140E0D200 + 64) + 128LL) = *a2;
    LOBYTE(v6) = 1;
    FileSecurityDescriptor = RtlStringFromGUIDEx(*(_QWORD *)(qword_140E0D200 + 64) + 128LL, &v36, v6);
    if ( FileSecurityDescriptor >= 0 )
    {
      v9 = a1 + 72;
      *(_QWORD *)(a1 + 72) = 5242880;
      Source = &CmpLogPath;
      v10 = *(void **)(qword_140E0D200 + 1552);
      if ( (Feature_CLFS_Signing__private_featureState & 0x10) != 0 )
        IsEnabledDeviceUsageNoInline = Feature_CLFS_Signing__private_featureState & 1;
      else
        IsEnabledDeviceUsageNoInline = Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline();
      if ( IsEnabledDeviceUsageNoInline )
        v47 = 1;
LABEL_25:
      FileSecurityDescriptor = CmpQueryFileSecurityDescriptor(v10);
      if ( FileSecurityDescriptor < 0 )
        goto LABEL_62;
      v3 = pvReadContext;
      v15 = (PVOID *)(a1 + 96);
      v49 = 1;
      v16 = (PLOG_FILE_OBJECT *)(a1 + 88);
      v17 = a1 + 68;
      while ( 1 )
      {
        FileSecurityDescriptor = CmpStartCLFSLog(Source, &v36, ppvReadContext, v9, v47 == 0, v17, a1 + 88, a1 + 96);
        if ( FileSecurityDescriptor < 0 )
          goto LABEL_56;
        pcbInfoBuffer = 120;
        v18 = (CLFS_INFORMATION *)ExAllocatePool2(256, 120, 538987843);
        v19 = v18;
        if ( v18 )
        {
          ClfsGetLogFileInformation(*v16, v18, &pcbInfoBuffer);
          ExFreePoolWithTag(v19, 0);
        }
        v20 = *v16;
        pcbWritten = 120;
        FileSecurityDescriptor = ClfsGetLogFileInformation(v20, Pool2, &pcbWritten);
        *(_QWORD *)(a1 + 120) = Pool2->BaseLsn.ullOffset;
        if ( FileSecurityDescriptor < 0 )
        {
LABEL_56:
          if ( pvCursorContext )
            ClfsTerminateReadLog(pvCursorContext);
          if ( FileSecurityDescriptor >= 0 )
          {
            *(_DWORD *)(a1 + 104) = *(_DWORD *)(a1 + 104) & 0xFFFFFFFC | 1;
          }
          else if ( *v15 )
          {
            *v15 = 0;
          }
          break;
        }
        if ( ClfsReadRestartArea(*v15, &ppvRestartBuffer, &pcbRestartBuffer, &plsn, &pvCursorContext) == 1075445772
          || !ppvRestartBuffer )
        {
          plsn2 = Pool2->BaseLsn;
          goto LABEL_43;
        }
        plsn2 = *(CLFS_LSN *)ppvRestartBuffer;
        if ( !ClfsLsnEqual(&plsn, &plsn2) )
          goto LABEL_43;
        v21 = *v15;
        plsnFirst = plsn2;
        pvReadContext = 0;
        ppvReadBuffer = 0;
        pcbReadBuffer = 0;
        plsnUndoNext.ullOffset = 0;
        plsnPrevious.ullOffset = 0;
        plsnRecord.ullOffset = 0;
        LOBYTE(pcbInfoBuffer) = 0;
        if ( ClfsReadLogRecord(
               v21,
               &plsnFirst,
               ClfsContextForward,
               &ppvReadBuffer,
               &pcbReadBuffer,
               (PCLFS_RECORD_TYPE)&pcbInfoBuffer,
               &plsnUndoNext,
               &plsnPrevious,
               &pvReadContext) >= 0 )
        {
          LOBYTE(pcbInfoBuffer) = 1;
          v22 = ClfsReadNextLogRecord(
                  pvReadContext,
                  &ppvReadBuffer,
                  &pcbReadBuffer,
                  (PCLFS_RECORD_TYPE)&pcbInfoBuffer,
                  0,
                  &plsnUndoNext,
                  &plsnPrevious,
                  &plsnRecord);
          if ( v22 == -1073741807 )
          {
            LastLsn = Pool2->LastLsn;
          }
          else
          {
            if ( v22 < 0 )
              goto LABEL_40;
            LastLsn = plsnRecord;
          }
          plsn2 = LastLsn;
        }
LABEL_40:
        if ( pvReadContext )
          ClfsTerminateReadLog(pvReadContext);
LABEL_43:
        if ( pvCursorContext )
        {
          ClfsTerminateReadLog(pvCursorContext);
          pvCursorContext = 0;
        }
        if ( !ClfsLsnEqual(&plsn2, &Pool2->LastLsn) && (*(_DWORD *)(a1 + 104) & 4) != 0 )
        {
          v24 = plsn2;
          if ( (int)((__int64 (__fastcall *)(_QWORD, _QWORD))CmpRmAnalysisPhase)(a1, (CLFS_LSN)plsn2.ullOffset) >= 0 )
          {
            ((void (__fastcall *)(_QWORD, _QWORD))CmpRmReDoPhase)(a1, (CLFS_LSN)v24.ullOffset);
            CmpRmUnDoPhase(a1);
          }
          *(_DWORD *)(a1 + 104) &= ~4u;
        }
        v25 = *v15;
        pvRestartBuffer = Pool2->LastLsn;
        v26 = ClfsWriteRestartArea(v25, &pvRestartBuffer, 8u, 0, 0, &pcbWritten, 0);
        FileSecurityDescriptor = v26;
        if ( !v49 || v26 != -1072037859 && *(_DWORD *)(a1 + 68) <= 0xAu )
          goto LABEL_56;
        v49 = 0;
        if ( pvCursorContext )
        {
          ClfsTerminateReadLog(pvCursorContext);
          pvCursorContext = 0;
        }
        ClfsDeleteLogByPointer(*v16);
        ClfsDeleteMarshallingArea(*v15);
        v27 = *v16;
        *v15 = 0;
        ClfsCloseLogFileObject(v27);
        v17 = a1 + 68;
        *v16 = 0;
        *(_DWORD *)(a1 + 68) = 0;
        v9 = a1 + 72;
      }
    }
  }
  else
  {
    FileSecurityDescriptor = CmpQueryNameString(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 1552LL), &UnicodeString);
    if ( FileSecurityDescriptor >= 0 )
    {
      if ( a2 )
        *(_OWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 64LL) + 128LL) = *a2;
      LOBYTE(v12) = 1;
      FileSecurityDescriptor = RtlStringFromGUIDEx(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 64LL) + 128LL, &v36, v12);
      if ( FileSecurityDescriptor >= 0 )
      {
        Source = &UnicodeString;
        v9 = a1 + 72;
        v13 = *(_QWORD *)(a1 + 80);
        *(_QWORD *)(a1 + 72) = 0x100000;
        v10 = *(void **)(v13 + 1552);
        if ( (Feature_CLFS_Signing__private_featureState & 0x10) != 0 )
          v14 = Feature_CLFS_Signing__private_featureState & 1;
        else
          v14 = Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline();
        if ( v14 )
        {
          FileSecurityDescriptor = CmpIsFileInSystemConfig(&UnicodeString);
          if ( FileSecurityDescriptor < 0 )
            goto LABEL_62;
          v47 = pcbInfoBuffer;
        }
        goto LABEL_25;
      }
    }
  }
LABEL_62:
  ExReleaseResourceLite(*(PERESOURCE *)(a1 + 128));
  KeLeaveCriticalRegion();
  if ( UnicodeString.Buffer )
    RtlFreeAnsiString(&UnicodeString);
  if ( v36.Buffer )
    RtlFreeAnsiString(&v36);
  ExFreePoolWithTag(Pool2, 0);
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  return (unsigned int)FileSecurityDescriptor;
}

```

## disassembly

```asm
0x1408b0708  mov     [rsp-8+arg_8], rbx
0x1408b070d  push    rbp
0x1408b070e  push    rsi
0x1408b070f  push    rdi
0x1408b0710  push    r12
0x1408b0712  push    r13
0x1408b0714  push    r14
0x1408b0716  push    r15
0x1408b0718  lea     rbp, [rsp-27h]
0x1408b071d  sub     rsp, 0F0h
0x1408b0724  xor     r15d, r15d
0x1408b0727  mov     rsi, rdx
0x1408b072a  mov     qword ptr [rbp+57h+UnicodeString.Length], r15
0x1408b072e  mov     r14d, r15d
0x1408b0731  mov     [rbp+57h+UnicodeString.Buffer], r15
0x1408b0735  mov     rdi, rcx
0x1408b0738  mov     qword ptr [rbp+57h+var_98.Length], r15
0x1408b073c  mov     [rbp+57h+var_98.Buffer], r15
0x1408b0740  mov     [rbp+57h+ppvRestartBuffer], r15
0x1408b0744  mov     [rbp+57h+pcbRestartBuffer], r15d
0x1408b0748  mov     qword ptr [rbp+57h+plsn], r15
0x1408b074c  mov     [rbp+57h+pvCursorContext], r15
0x1408b0750  mov     qword ptr [rbp+57h+plsn2], r15
0x1408b0754  mov     [rbp+57h+pcbWritten], r15d
0x1408b0758  mov     [rbp+57h+pvRestartBuffer], r15
0x1408b075c  mov     [rbp+57h+pvReadContext], r15
0x1408b0760  mov     [rbp+57h+arg_0], r15b
0x1408b0764  mov     byte ptr [rbp+57h+pcbInfoBuffer], r15b
0x1408b0768  call    LockRMLog
0x1408b076d  mov     eax, [rdi+68h]
0x1408b0770  test    al, 1
0x1408b0772  jz      short loc_1408B0779
0x1408b0774  mov     ebx, r15d
0x1408b0777  jmp     short loc_1408B079B
0x1408b0779  mov     edx, 78h ; 'x'
0x1408b077e  mov     ecx, 100h
0x1408b0783  mov     r8d, 20204D43h
0x1408b0789  call    ExAllocatePool2
0x1408b078e  mov     r13, rax
0x1408b0791  test    rax, rax
0x1408b0794  jnz     short loc_1408B07B1
0x1408b0796  mov     ebx, 0C000009Ah
0x1408b079b  mov     rcx, [rdi+80h]; Resource
0x1408b07a2  call    ExReleaseResourceLite
0x1408b07a7  call    KeLeaveCriticalRegion
0x1408b07ac  jmp     loc_1408B0CAD
0x1408b07b1  or      dword ptr [rdi+68h], 2
0x1408b07b5  cmp     rdi, cs:WheapPfaLock.Timer.TimerListEntry.Blink
0x1408b07bc  mov     rax, cs:CLFS_LSN_INVALID_EXT
0x1408b07c3  mov     [rdi+78h], rax
0x1408b07c7  jnz     loc_1408B0856
0x1408b07cd  test    rsi, rsi
0x1408b07d0  jz      short loc_1408B07E8
0x1408b07d2  mov     rax, cs:qword_140E0D200
0x1408b07d9  movups  xmm0, xmmword ptr [rsi]
0x1408b07dc  mov     rcx, [rax+40h]
0x1408b07e0  movdqu  xmmword ptr [rcx+80h], xmm0
0x1408b07e8  mov     rax, cs:qword_140E0D200
0x1408b07ef  lea     rdx, [rbp+57h+var_98]
0x1408b07f3  mov     r8b, 1
0x1408b07f6  mov     rcx, [rax+40h]
0x1408b07fa  sub     rcx, 0FFFFFFFFFFFFFF80h
0x1408b07fe  call    RtlStringFromGUIDEx
0x1408b0803  mov     ebx, eax
0x1408b0805  test    eax, eax
0x1408b0807  js      loc_1408B0C65
0x1408b080d  lea     r15, [rdi+48h]
0x1408b0811  mov     qword ptr [r15], 500000h
0x1408b0818  lea     r12, CmpLogPath
0x1408b081f  mov     rax, cs:qword_140E0D200
0x1408b0826  mov     [rbp+57h+Source], r12
0x1408b082a  mov     rsi, [rax+610h]
0x1408b0831  mov     eax, cs:Feature_CLFS_Signing__private_featureState
0x1408b0837  test    al, 10h
0x1408b0839  jz      short loc_1408B0840
0x1408b083b  and     eax, 1
0x1408b083e  jmp     short loc_1408B0845
0x1408b0840  call    Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline
0x1408b0845  test    eax, eax
0x1408b0847  jz      loc_1408B0901
0x1408b084d  mov     [rbp+57h+arg_0], 1
0x1408b0851  jmp     loc_1408B0901
0x1408b0856  mov     rcx, [rdi+50h]
0x1408b085a  lea     rdx, [rbp+57h+UnicodeString]
0x1408b085e  mov     rcx, [rcx+610h]
0x1408b0865  call    CmpQueryNameString
0x1408b086a  mov     ebx, eax
0x1408b086c  test    eax, eax
0x1408b086e  js      loc_1408B0C65
0x1408b0874  test    rsi, rsi
0x1408b0877  jz      short loc_1408B088C
0x1408b0879  mov     rax, [rdi+50h]
0x1408b087d  movups  xmm0, xmmword ptr [rsi]
0x1408b0880  mov     rcx, [rax+40h]
0x1408b0884  movdqu  xmmword ptr [rcx+80h], xmm0
0x1408b088c  mov     rax, [rdi+50h]
0x1408b0890  lea     rdx, [rbp+57h+var_98]
0x1408b0894  mov     r8b, 1
0x1408b0897  mov     rcx, [rax+40h]
0x1408b089b  sub     rcx, 0FFFFFFFFFFFFFF80h
0x1408b089f  call    RtlStringFromGUIDEx
0x1408b08a4  mov     ebx, eax
0x1408b08a6  test    eax, eax
0x1408b08a8  js      loc_1408B0C65
0x1408b08ae  lea     rax, [rbp+57h+UnicodeString]
0x1408b08b2  mov     [rbp+57h+Source], rax
0x1408b08b6  lea     r15, [rdi+48h]
0x1408b08ba  mov     rax, [rdi+50h]
0x1408b08be  mov     qword ptr [r15], 100000h
0x1408b08c5  mov     rsi, [rax+610h]
0x1408b08cc  mov     eax, cs:Feature_CLFS_Signing__private_featureState
0x1408b08d2  test    al, 10h
0x1408b08d4  jz      short loc_1408B08DB
0x1408b08d6  and     eax, 1
0x1408b08d9  jmp     short loc_1408B08E0
0x1408b08db  call    Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline
0x1408b08e0  test    eax, eax
0x1408b08e2  jz      short loc_1408B0901
0x1408b08e4  lea     rdx, [rbp+57h+pcbInfoBuffer]
0x1408b08e8  lea     rcx, [rbp+57h+UnicodeString]; String2
0x1408b08ec  call    CmpIsFileInSystemConfig
0x1408b08f1  mov     ebx, eax
0x1408b08f3  test    eax, eax
0x1408b08f5  js      loc_1408B0C62
0x1408b08fb  mov     al, byte ptr [rbp+57h+pcbInfoBuffer]
0x1408b08fe  mov     [rbp+57h+arg_0], al
0x1408b0901  lea     rdx, [rbp+57h+pvReadContext]
0x1408b0905  mov     rcx, rsi; Handle
0x1408b0908  call    CmpQueryFileSecurityDescriptor
0x1408b090d  mov     ebx, eax
0x1408b090f  test    eax, eax
0x1408b0911  js      loc_1408B0C62
0x1408b0917  mov     r14, [rbp+57h+pvReadContext]
0x1408b091b  lea     rsi, [rdi+60h]
0x1408b091f  mov     [rbp+57h+arg_18], 1
0x1408b0923  lea     r12, [rdi+58h]
0x1408b0927  lea     rcx, [rdi+44h]
0x1408b092b  cmp     [rbp+57h+arg_0], 0
0x1408b092f  lea     rdx, [rbp+57h+var_98]; PCUNICODE_STRING
0x1408b0933  mov     [rsp+120h+var_D8], rsi; __int64
0x1408b0938  mov     r9, r14
0x1408b093b  mov     [rsp+120h+var_E0], r12; __int64
0x1408b0940  setz    al
0x1408b0943  mov     [rsp+120h+plsnPrevious], rcx; __int64
0x1408b0948  mov     rcx, [rbp+57h+Source]; Source
0x1408b094c  mov     byte ptr [rsp+120h+plsnUndoNext], al; char
0x1408b0950  mov     [rsp+120h+peRecordType], r15; __int64
0x1408b0955  call    CmpStartCLFSLog
0x1408b095a  xor     r15d, r15d
0x1408b095d  mov     ebx, eax
0x1408b095f  test    eax, eax
0x1408b0961  js      loc_1408B0C31
0x1408b0967  lea     eax, [r15+78h]
0x1408b096b  mov     r8d, 20204D43h
0x1408b0971  mov     edx, eax
0x1408b0973  mov     [rbp+57h+pcbInfoBuffer], eax
0x1408b0976  mov     ecx, 100h
0x1408b097b  call    ExAllocatePool2
0x1408b0980  mov     rbx, rax
0x1408b0983  test    rax, rax
0x1408b0986  jz      short loc_1408B09A9
0x1408b0988  mov     rcx, [r12]; plfoLog
0x1408b098c  lea     r8, [rbp+57h+pcbInfoBuffer]; pcbInfoBuffer
0x1408b0990  mov     rdx, rax; pinfoBuffer
0x1408b0993  call    cs:__imp_ClfsGetLogFileInformation
0x1408b099a  nop     dword ptr [rax+rax+00h]
0x1408b099f  xor     edx, edx; Tag
0x1408b09a1  mov     rcx, rbx; P
0x1408b09a4  call    ExFreePoolWithTag
0x1408b09a9  mov     rcx, [r12]; plfoLog
0x1408b09ad  lea     r8, [rbp+57h+pcbWritten]; pcbInfoBuffer
0x1408b09b1  mov     rdx, r13; pinfoBuffer
0x1408b09b4  mov     [rbp+57h+pcbWritten], 78h ; 'x'
0x1408b09bb  call    cs:__imp_ClfsGetLogFileInformation
0x1408b09c2  nop     dword ptr [rax+rax+00h]
0x1408b09c7  mov     ebx, eax
0x1408b09c9  mov     rax, [r13+48h]
0x1408b09cd  mov     [rdi+78h], rax
0x1408b09d1  test    ebx, ebx
0x1408b09d3  js      loc_1408B0C31
0x1408b09d9  mov     rcx, [rsi]; pvMarshalContext
0x1408b09dc  lea     rax, [rbp+57h+pvCursorContext]
0x1408b09e0  lea     r9, [rbp+57h+plsn]; plsn
0x1408b09e4  mov     [rsp+120h+ppvReadContext], rax; ppvReadContext
0x1408b09e9  lea     r8, [rbp+57h+pcbRestartBuffer]; pcbRestartBuffer
0x1408b09ed  lea     rdx, [rbp+57h+ppvRestartBuffer]; ppvRestartBuffer
0x1408b09f1  call    cs:__imp_ClfsReadRestartArea
0x1408b09f8  nop     dword ptr [rax+rax+00h]
0x1408b09fd  cmp     eax, 401A000Ch
0x1408b0a02  jz      loc_1408B0B1A
0x1408b0a08  mov     rax, [rbp+57h+ppvRestartBuffer]
0x1408b0a0c  test    rax, rax
0x1408b0a0f  jz      loc_1408B0B1A
0x1408b0a15  mov     rax, [rax]
0x1408b0a18  lea     rdx, [rbp+57h+plsn2]; plsn2
0x1408b0a1c  lea     rcx, [rbp+57h+plsn]; plsn1
0x1408b0a20  mov     qword ptr [rbp+57h+plsn2], rax
0x1408b0a24  call    cs:__imp_ClfsLsnEqual
0x1408b0a2b  nop     dword ptr [rax+rax+00h]
0x1408b0a30  test    al, al
0x1408b0a32  jz      loc_1408B0B22
0x1408b0a38  mov     rax, qword ptr [rbp+57h+plsn2]
0x1408b0a3c  lea     r9, [rbp+57h+ppvReadBuffer]; ppvReadBuffer
0x1408b0a40  mov     rcx, [rsi]; pvMarshalContext
0x1408b0a43  lea     rdx, [rbp+57h+plsnFirst]; plsnFirst
0x1408b0a47  mov     qword ptr [rbp+57h+plsnFirst], rax
0x1408b0a4b  mov     r8d, 3; peContextMode
0x1408b0a51  lea     rax, [rbp+57h+pvReadContext]
0x1408b0a55  mov     [rbp+57h+pvReadContext], r15
0x1408b0a59  mov     [rsp+120h+var_E0], rax; ppvReadContext
0x1408b0a5e  lea     rax, [rbp+57h+var_68]
0x1408b0a62  mov     [rsp+120h+plsnPrevious], rax; plsnPrevious
0x1408b0a67  lea     rax, [rbp+57h+var_60]
0x1408b0a6b  mov     [rsp+120h+plsnUndoNext], rax; plsnUndoNext
0x1408b0a70  lea     rax, [rbp+57h+pcbInfoBuffer]
0x1408b0a74  mov     [rsp+120h+peRecordType], rax; peRecordType
0x1408b0a79  lea     rax, [rbp+57h+pcbReadBuffer]
0x1408b0a7d  mov     [rsp+120h+ppvReadContext], rax; pcbReadBuffer
0x1408b0a82  mov     [rbp+57h+ppvReadBuffer], r15
0x1408b0a86  mov     [rbp+57h+pcbReadBuffer], r15d
0x1408b0a8a  mov     qword ptr [rbp+57h+var_60], r15
0x1408b0a8e  mov     qword ptr [rbp+57h+var_68], r15
0x1408b0a92  mov     qword ptr [rbp+57h+plsnRecord], r15
0x1408b0a96  mov     byte ptr [rbp+57h+pcbInfoBuffer], r15b
0x1408b0a9a  call    cs:__imp_ClfsReadLogRecord
0x1408b0aa1  nop     dword ptr [rax+rax+00h]
0x1408b0aa6  test    eax, eax
0x1408b0aa8  js      short loc_1408B0B03
0x1408b0aaa  mov     rcx, [rbp+57h+pvReadContext]; pvReadContext
0x1408b0aae  lea     rax, [rbp+57h+plsnRecord]
0x1408b0ab2  mov     [rsp+120h+plsnPrevious], rax; plsnRecord
0x1408b0ab7  lea     r9, [rbp+57h+pcbInfoBuffer]; peRecordType
0x1408b0abb  lea     rax, [rbp+57h+var_68]
0x1408b0abf  mov     byte ptr [rbp+57h+pcbInfoBuffer], 1
0x1408b0ac3  mov     [rsp+120h+plsnUndoNext], rax; plsnPrevious
0x1408b0ac8  lea     r8, [rbp+57h+pcbReadBuffer]; pcbBuffer
0x1408b0acc  lea     rax, [rbp+57h+var_60]
0x1408b0ad0  mov     [rsp+120h+peRecordType], rax; plsnUndoNext
0x1408b0ad5  lea     rdx, [rbp+57h+ppvReadBuffer]; ppvBuffer
0x1408b0ad9  mov     [rsp+120h+ppvReadContext], r15; plsnUser
0x1408b0ade  call    cs:__imp_ClfsReadNextLogRecord
0x1408b0ae5  nop     dword ptr [rax+rax+00h]
0x1408b0aea  cmp     eax, 0C0000011h
0x1408b0aef  jnz     short loc_1408B0AF7
0x1408b0af1  mov     rax, [r13+58h]
0x1408b0af5  jmp     short loc_1408B0AFF
0x1408b0af7  test    eax, eax
0x1408b0af9  js      short loc_1408B0B03
0x1408b0afb  mov     rax, qword ptr [rbp+57h+plsnRecord]
0x1408b0aff  mov     qword ptr [rbp+57h+plsn2], rax
0x1408b0b03  mov     rcx, [rbp+57h+pvReadContext]; pvCursorContext
0x1408b0b07  test    rcx, rcx
0x1408b0b0a  jz      short loc_1408B0B22
0x1408b0b0c  call    cs:__imp_ClfsTerminateReadLog
0x1408b0b13  nop     dword ptr [rax+rax+00h]
0x1408b0b18  jmp     short loc_1408B0B22
0x1408b0b1a  mov     rax, [r13+48h]
0x1408b0b1e  mov     qword ptr [rbp+57h+plsn2], rax
0x1408b0b22  mov     rcx, [rbp+57h+pvCursorContext]; pvCursorContext
0x1408b0b26  test    rcx, rcx
0x1408b0b29  jz      short loc_1408B0B3B
0x1408b0b2b  call    cs:__imp_ClfsTerminateReadLog
0x1408b0b32  nop     dword ptr [rax+rax+00h]
0x1408b0b37  mov     [rbp+57h+pvCursorContext], r15
0x1408b0b3b  lea     rdx, [r13+58h]; plsn2
0x1408b0b3f  lea     rcx, [rbp+57h+plsn2]; plsn1
0x1408b0b43  call    cs:__imp_ClfsLsnEqual
0x1408b0b4a  nop     dword ptr [rax+rax+00h]
0x1408b0b4f  test    al, al
0x1408b0b51  jnz     short loc_1408B0B84
0x1408b0b53  mov     eax, [rdi+68h]
0x1408b0b56  test    al, 4
0x1408b0b58  jz      short loc_1408B0B84
0x1408b0b5a  mov     rbx, qword ptr [rbp+57h+plsn2]
0x1408b0b5e  mov     rcx, rdi
0x1408b0b61  mov     rdx, rbx
0x1408b0b64  call    CmpRmAnalysisPhase
0x1408b0b69  test    eax, eax
0x1408b0b6b  js      short loc_1408B0B80
0x1408b0b6d  mov     rdx, rbx
0x1408b0b70  mov     rcx, rdi
0x1408b0b73  call    CmpRmReDoPhase
0x1408b0b78  mov     rcx, rdi
0x1408b0b7b  call    CmpRmUnDoPhase
0x1408b0b80  and     dword ptr [rdi+68h], 0FFFFFFFBh
0x1408b0b84  mov     rax, [r13+58h]
0x1408b0b88  lea     rdx, [rbp+57h+pvRestartBuffer]; pvRestartBuffer
0x1408b0b8c  mov     rcx, [rsi]; pvMarshalContext
0x1408b0b8f  xor     r9d, r9d; plsnBase
0x1408b0b92  mov     [rbp+57h+pvRestartBuffer], rax
0x1408b0b96  lea     rax, [rbp+57h+pcbWritten]
0x1408b0b9a  mov     [rsp+120h+plsnUndoNext], r15; plsnNext
0x1408b0b9f  mov     [rsp+120h+peRecordType], rax; pcbWritten
0x1408b0ba4  lea     r8d, [r9+8]; cbRestartBuffer
0x1408b0ba8  mov     dword ptr [rsp+120h+ppvReadContext], r15d; fFlags
0x1408b0bad  call    cs:__imp_ClfsWriteRestartArea
0x1408b0bb4  nop     dword ptr [rax+rax+00h]
0x1408b0bb9  mov     ebx, eax
0x1408b0bbb  cmp     [rbp+57h+arg_18], r15b
0x1408b0bbf  jz      short loc_1408B0C31
  ... truncated ...
```
