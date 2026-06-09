# CmpStartRMLog

- ea: `0x1408e5618`
- end: `0x1408e5bdb`
- name: `CmpStartRMLog`
- size: `1475`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1408e282c`
- `0x1408e5f54`

## callees

- `0x140216db0`
- `0x14036f270`
- `0x14051754c`
- `0x14073fcd0`
- `0x140805f74`
- `0x1408061b4`
- `0x140806390`
- `0x1408e4138`
- `0x1408e47f4`
- `0x1408e4bdc`
- `0x1408e5618`
- `0x1408e7248`
- `0x140923cd0`
- `0x14094b120`
- `0x140bb1410`
- `0x140bb19f0`

## import_xrefs

- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x1408e59ee`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadNextLogRecord` at `0x1408e59ee`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1408e5a1c`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1408e5a3b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1408e5aeb`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1408e5b4a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1408e5a1c`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1408e5a3b`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1408e5aeb`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsTerminateReadLog` at `0x1408e5b4a`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsWriteRestartArea` at `0x1408e5abd`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsWriteRestartArea` at `0x1408e5abd`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsDeleteLogByPointer` at `0x1408e5aff`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsDeleteLogByPointer` at `0x1408e5aff`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsDeleteMarshallingArea` at `0x1408e5b0e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsDeleteMarshallingArea` at `0x1408e5b0e`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnEqual` at `0x1408e5934`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnEqual` at `0x1408e5a53`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnEqual` at `0x1408e5934`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnEqual` at `0x1408e5a53`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadRestartArea` at `0x1408e5901`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadRestartArea` at `0x1408e5901`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1408e58a3`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1408e58cb`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1408e58a3`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsGetLogFileInformation` at `0x1408e58cb`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x1408e5b21`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsCloseLogFileObject` at `0x1408e5b21`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x1408e59aa`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsReadLogRecord` at `0x1408e59aa`

## pseudocode

```c
__int64 __fastcall CmpStartRMLog(char *a1, _OWORD *a2)
{
  PVOID v3; // r14
  int FileSecurityDescriptor; // ebx
  __int64 v6; // r8
  CLFS_INFORMATION *Pool2; // r13
  bool v8; // zf
  ULONGLONG *v9; // r15
  void *v10; // rsi
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v12; // r8
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // r8
  PVOID *v16; // rsi
  PLOG_FILE_OBJECT *v17; // r12
  unsigned int *v18; // rcx
  CLFS_INFORMATION *v19; // rax
  CLFS_INFORMATION *v20; // rbx
  FILE_OBJECT *v21; // rcx
  PVOID v22; // rcx
  NTSTATUS v23; // eax
  CLFS_LSN LastLsn; // rax
  CLFS_LSN v25; // rbx
  PVOID v26; // rcx
  NTSTATUS v27; // eax
  FILE_OBJECT *v28; // rcx
  int ppvReadContext; // [rsp+20h] [rbp-A9h]
  CLFS_LSN plsn2; // [rsp+50h] [rbp-79h] BYREF
  ULONG pcbWritten; // [rsp+58h] [rbp-71h] BYREF
  PVOID pvCursorContext; // [rsp+60h] [rbp-69h] BYREF
  PVOID pvReadContext; // [rsp+68h] [rbp-61h] BYREF
  ULONG pcbReadBuffer; // [rsp+70h] [rbp-59h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+78h] [rbp-51h] BYREF
  UNICODE_STRING v37; // [rsp+88h] [rbp-41h] BYREF
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
  char v48; // [rsp+130h] [rbp+67h]
  ULONG pcbInfoBuffer; // [rsp+140h] [rbp+77h] BYREF
  char v50; // [rsp+148h] [rbp+7Fh]

  *(_QWORD *)&UnicodeString.Length = 0;
  v3 = 0;
  UnicodeString.Buffer = 0;
  *(_QWORD *)&v37.Length = 0;
  v37.Buffer = 0;
  ppvRestartBuffer = 0;
  pcbRestartBuffer = 0;
  plsn.ullOffset = 0;
  pvCursorContext = 0;
  plsn2.ullOffset = 0;
  pcbWritten = 0;
  pvRestartBuffer.ullOffset = 0;
  pvReadContext = 0;
  v48 = 0;
  LOBYTE(pcbInfoBuffer) = 0;
  LockRMLog();
  if ( (*((_DWORD *)a1 + 26) & 1) != 0 )
  {
    FileSecurityDescriptor = 0;
LABEL_5:
    ExReleaseResourceLite(*((PERESOURCE *)a1 + 16));
    KeLeaveCriticalRegion();
    return (unsigned int)FileSecurityDescriptor;
  }
  Pool2 = (CLFS_INFORMATION *)ExAllocatePool2(256, 120, 0x20204D43u);
  if ( !Pool2 )
  {
    FileSecurityDescriptor = -1073741670;
    goto LABEL_5;
  }
  *((_DWORD *)a1 + 26) |= 2u;
  v8 = a1 == CmRmSystem;
  *((_QWORD *)a1 + 15) = CLFS_LSN_INVALID_EXT;
  if ( v8 )
  {
    if ( a2 )
      *(_OWORD *)(*(_QWORD *)(qword_140E0D200 + 64) + 128LL) = *a2;
    LOBYTE(v6) = 1;
    FileSecurityDescriptor = RtlStringFromGUIDEx(*(_QWORD *)(qword_140E0D200 + 64) + 128LL, &v37, v6);
    if ( FileSecurityDescriptor >= 0 )
    {
      v9 = (ULONGLONG *)(a1 + 72);
      *((_QWORD *)a1 + 9) = 5242880;
      Source = &CmpLogPath;
      v10 = *(void **)(qword_140E0D200 + 1552);
      if ( (Feature_CLFS_Signing__private_featureState & 0x10) != 0 )
        IsEnabledDeviceUsageNoInline = Feature_CLFS_Signing__private_featureState & 1;
      else
        IsEnabledDeviceUsageNoInline = Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline();
      if ( IsEnabledDeviceUsageNoInline )
        v48 = 1;
LABEL_25:
      FileSecurityDescriptor = CmpQueryFileSecurityDescriptor(v10);
      if ( FileSecurityDescriptor < 0 )
        goto LABEL_62;
      v3 = pvReadContext;
      v16 = (PVOID *)(a1 + 96);
      v50 = 1;
      v17 = (PLOG_FILE_OBJECT *)(a1 + 88);
      v18 = (unsigned int *)(a1 + 68);
      while ( 1 )
      {
        FileSecurityDescriptor = CmpStartCLFSLog(
                                   Source,
                                   &v37,
                                   v15,
                                   v3,
                                   ppvReadContext,
                                   v9,
                                   v48 == 0,
                                   v18,
                                   (FILE_OBJECT **)a1 + 11,
                                   (PVOID *)a1 + 12);
        if ( FileSecurityDescriptor < 0 )
          goto LABEL_56;
        pcbInfoBuffer = 120;
        v19 = (CLFS_INFORMATION *)ExAllocatePool2(256, 120, 0x20204D43u);
        v20 = v19;
        if ( v19 )
        {
          ClfsGetLogFileInformation(*v17, v19, &pcbInfoBuffer);
          ExFreePoolWithTag(v20, 0);
        }
        v21 = *v17;
        pcbWritten = 120;
        FileSecurityDescriptor = ClfsGetLogFileInformation(v21, Pool2, &pcbWritten);
        *((_QWORD *)a1 + 15) = Pool2->BaseLsn.ullOffset;
        if ( FileSecurityDescriptor < 0 )
        {
LABEL_56:
          if ( pvCursorContext )
            ClfsTerminateReadLog(pvCursorContext);
          if ( FileSecurityDescriptor >= 0 )
          {
            *((_DWORD *)a1 + 26) = *((_DWORD *)a1 + 26) & 0xFFFFFFFC | 1;
          }
          else if ( *v16 )
          {
            *v16 = 0;
          }
          break;
        }
        if ( ClfsReadRestartArea(*v16, &ppvRestartBuffer, &pcbRestartBuffer, &plsn, &pvCursorContext) == 1075445772
          || !ppvRestartBuffer )
        {
          plsn2 = Pool2->BaseLsn;
          goto LABEL_43;
        }
        plsn2 = *(CLFS_LSN *)ppvRestartBuffer;
        if ( !ClfsLsnEqual(&plsn, &plsn2) )
          goto LABEL_43;
        v22 = *v16;
        plsnFirst = plsn2;
        pvReadContext = 0;
        ppvReadBuffer = 0;
        pcbReadBuffer = 0;
        plsnUndoNext.ullOffset = 0;
        plsnPrevious.ullOffset = 0;
        plsnRecord.ullOffset = 0;
        LOBYTE(pcbInfoBuffer) = 0;
        if ( ClfsReadLogRecord(
               v22,
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
          v23 = ClfsReadNextLogRecord(
                  pvReadContext,
                  &ppvReadBuffer,
                  &pcbReadBuffer,
                  (PCLFS_RECORD_TYPE)&pcbInfoBuffer,
                  0,
                  &plsnUndoNext,
                  &plsnPrevious,
                  &plsnRecord);
          if ( v23 == -1073741807 )
          {
            LastLsn = Pool2->LastLsn;
          }
          else
          {
            if ( v23 < 0 )
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
        if ( !ClfsLsnEqual(&plsn2, &Pool2->LastLsn) && (*((_DWORD *)a1 + 26) & 4) != 0 )
        {
          v25 = plsn2;
          if ( (int)((__int64 (__fastcall *)(_QWORD, _QWORD))CmpRmAnalysisPhase)(a1, (CLFS_LSN)plsn2.ullOffset) >= 0 )
          {
            ((void (__fastcall *)(_QWORD, _QWORD))CmpRmReDoPhase)(a1, (CLFS_LSN)v25.ullOffset);
            CmpRmUnDoPhase(a1);
          }
          *((_DWORD *)a1 + 26) &= ~4u;
        }
        v26 = *v16;
        pvRestartBuffer = Pool2->LastLsn;
        v27 = ClfsWriteRestartArea(v26, &pvRestartBuffer, 8u, 0, 0, &pcbWritten, 0);
        FileSecurityDescriptor = v27;
        if ( !v50 || v27 != -1072037859 && *((_DWORD *)a1 + 17) <= 0xAu )
          goto LABEL_56;
        v50 = 0;
        if ( pvCursorContext )
        {
          ClfsTerminateReadLog(pvCursorContext);
          pvCursorContext = 0;
        }
        ClfsDeleteLogByPointer(*v17);
        ClfsDeleteMarshallingArea(*v16);
        v28 = *v17;
        *v16 = 0;
        ClfsCloseLogFileObject(v28);
        v18 = (unsigned int *)(a1 + 68);
        *v17 = 0;
        *((_DWORD *)a1 + 17) = 0;
        v9 = (ULONGLONG *)(a1 + 72);
      }
    }
  }
  else
  {
    FileSecurityDescriptor = CmpQueryNameString(*(_QWORD *)(*((_QWORD *)a1 + 10) + 1552LL), &UnicodeString);
    if ( FileSecurityDescriptor >= 0 )
    {
      if ( a2 )
        *(_OWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 10) + 64LL) + 128LL) = *a2;
      LOBYTE(v12) = 1;
      FileSecurityDescriptor = RtlStringFromGUIDEx(*(_QWORD *)(*((_QWORD *)a1 + 10) + 64LL) + 128LL, &v37, v12);
      if ( FileSecurityDescriptor >= 0 )
      {
        Source = &UnicodeString;
        v9 = (ULONGLONG *)(a1 + 72);
        v13 = *((_QWORD *)a1 + 10);
        *((_QWORD *)a1 + 9) = 0x100000;
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
          v48 = pcbInfoBuffer;
        }
        goto LABEL_25;
      }
    }
  }
LABEL_62:
  ExReleaseResourceLite(*((PERESOURCE *)a1 + 16));
  KeLeaveCriticalRegion();
  if ( UnicodeString.Buffer )
    RtlFreeAnsiString(&UnicodeString);
  if ( v37.Buffer )
    RtlFreeAnsiString(&v37);
  ExFreePoolWithTag(Pool2, 0);
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  return (unsigned int)FileSecurityDescriptor;
}

```

## disassembly

```asm
0x1408e5618  mov     [rsp-8+arg_8], rbx
0x1408e561d  push    rbp
0x1408e561e  push    rsi
0x1408e561f  push    rdi
0x1408e5620  push    r12
0x1408e5622  push    r13
0x1408e5624  push    r14
0x1408e5626  push    r15
0x1408e5628  lea     rbp, [rsp-27h]
0x1408e562d  sub     rsp, 0F0h
0x1408e5634  xor     r15d, r15d
0x1408e5637  mov     rsi, rdx
0x1408e563a  mov     qword ptr [rbp+57h+UnicodeString.Length], r15
0x1408e563e  mov     r14d, r15d
0x1408e5641  mov     [rbp+57h+UnicodeString.Buffer], r15
0x1408e5645  mov     rdi, rcx
0x1408e5648  mov     qword ptr [rbp+57h+var_98.Length], r15
0x1408e564c  mov     [rbp+57h+var_98.Buffer], r15
0x1408e5650  mov     [rbp+57h+ppvRestartBuffer], r15
0x1408e5654  mov     [rbp+57h+pcbRestartBuffer], r15d
0x1408e5658  mov     qword ptr [rbp+57h+plsn], r15
0x1408e565c  mov     [rbp+57h+pvCursorContext], r15
0x1408e5660  mov     qword ptr [rbp+57h+plsn2], r15
0x1408e5664  mov     [rbp+57h+pcbWritten], r15d
0x1408e5668  mov     [rbp+57h+pvRestartBuffer], r15
0x1408e566c  mov     [rbp+57h+pvReadContext], r15
0x1408e5670  mov     [rbp+57h+arg_0], r15b
0x1408e5674  mov     byte ptr [rbp+57h+pcbInfoBuffer], r15b
0x1408e5678  call    LockRMLog
0x1408e567d  mov     eax, [rdi+68h]
0x1408e5680  test    al, 1
0x1408e5682  jz      short loc_1408E5689
0x1408e5684  mov     ebx, r15d
0x1408e5687  jmp     short loc_1408E56AB
0x1408e5689  mov     edx, 78h ; 'x'
0x1408e568e  mov     ecx, 100h
0x1408e5693  mov     r8d, 20204D43h
0x1408e5699  call    ExAllocatePool2
0x1408e569e  mov     r13, rax
0x1408e56a1  test    rax, rax
0x1408e56a4  jnz     short loc_1408E56C1
0x1408e56a6  mov     ebx, 0C000009Ah
0x1408e56ab  mov     rcx, [rdi+80h]; Resource
0x1408e56b2  call    ExReleaseResourceLite
0x1408e56b7  call    KeLeaveCriticalRegion
0x1408e56bc  jmp     loc_1408E5BBD
0x1408e56c1  or      dword ptr [rdi+68h], 2
0x1408e56c5  cmp     rdi, cs:CmRmSystem
0x1408e56cc  mov     rax, cs:CLFS_LSN_INVALID_EXT
0x1408e56d3  mov     [rdi+78h], rax
0x1408e56d7  jnz     loc_1408E5766
0x1408e56dd  test    rsi, rsi
0x1408e56e0  jz      short loc_1408E56F8
0x1408e56e2  mov     rax, cs:qword_140E0D200
0x1408e56e9  movups  xmm0, xmmword ptr [rsi]
0x1408e56ec  mov     rcx, [rax+40h]
0x1408e56f0  movdqu  xmmword ptr [rcx+80h], xmm0
0x1408e56f8  mov     rax, cs:qword_140E0D200
0x1408e56ff  lea     rdx, [rbp+57h+var_98]
0x1408e5703  mov     r8b, 1
0x1408e5706  mov     rcx, [rax+40h]
0x1408e570a  sub     rcx, 0FFFFFFFFFFFFFF80h
0x1408e570e  call    RtlStringFromGUIDEx
0x1408e5713  mov     ebx, eax
0x1408e5715  test    eax, eax
0x1408e5717  js      loc_1408E5B75
0x1408e571d  lea     r15, [rdi+48h]
0x1408e5721  mov     qword ptr [r15], 500000h
0x1408e5728  lea     r12, CmpLogPath
0x1408e572f  mov     rax, cs:qword_140E0D200
0x1408e5736  mov     [rbp+57h+Source], r12
0x1408e573a  mov     rsi, [rax+610h]
0x1408e5741  mov     eax, cs:Feature_CLFS_Signing__private_featureState
0x1408e5747  test    al, 10h
0x1408e5749  jz      short loc_1408E5750
0x1408e574b  and     eax, 1
0x1408e574e  jmp     short loc_1408E5755
0x1408e5750  call    Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline
0x1408e5755  test    eax, eax
0x1408e5757  jz      loc_1408E5811
0x1408e575d  mov     [rbp+57h+arg_0], 1
0x1408e5761  jmp     loc_1408E5811
0x1408e5766  mov     rcx, [rdi+50h]
0x1408e576a  lea     rdx, [rbp+57h+UnicodeString]
0x1408e576e  mov     rcx, [rcx+610h]
0x1408e5775  call    CmpQueryNameString
0x1408e577a  mov     ebx, eax
0x1408e577c  test    eax, eax
0x1408e577e  js      loc_1408E5B75
0x1408e5784  test    rsi, rsi
0x1408e5787  jz      short loc_1408E579C
0x1408e5789  mov     rax, [rdi+50h]
0x1408e578d  movups  xmm0, xmmword ptr [rsi]
0x1408e5790  mov     rcx, [rax+40h]
0x1408e5794  movdqu  xmmword ptr [rcx+80h], xmm0
0x1408e579c  mov     rax, [rdi+50h]
0x1408e57a0  lea     rdx, [rbp+57h+var_98]
0x1408e57a4  mov     r8b, 1
0x1408e57a7  mov     rcx, [rax+40h]
0x1408e57ab  sub     rcx, 0FFFFFFFFFFFFFF80h
0x1408e57af  call    RtlStringFromGUIDEx
0x1408e57b4  mov     ebx, eax
0x1408e57b6  test    eax, eax
0x1408e57b8  js      loc_1408E5B75
0x1408e57be  lea     rax, [rbp+57h+UnicodeString]
0x1408e57c2  mov     [rbp+57h+Source], rax
0x1408e57c6  lea     r15, [rdi+48h]
0x1408e57ca  mov     rax, [rdi+50h]
0x1408e57ce  mov     qword ptr [r15], 100000h
0x1408e57d5  mov     rsi, [rax+610h]
0x1408e57dc  mov     eax, cs:Feature_CLFS_Signing__private_featureState
0x1408e57e2  test    al, 10h
0x1408e57e4  jz      short loc_1408E57EB
0x1408e57e6  and     eax, 1
0x1408e57e9  jmp     short loc_1408E57F0
0x1408e57eb  call    Feature_CLFS_Signing__private_IsEnabledDeviceUsageNoInline
0x1408e57f0  test    eax, eax
0x1408e57f2  jz      short loc_1408E5811
0x1408e57f4  lea     rdx, [rbp+57h+pcbInfoBuffer]
0x1408e57f8  lea     rcx, [rbp+57h+UnicodeString]; String2
0x1408e57fc  call    CmpIsFileInSystemConfig
0x1408e5801  mov     ebx, eax
0x1408e5803  test    eax, eax
0x1408e5805  js      loc_1408E5B72
0x1408e580b  mov     al, byte ptr [rbp+57h+pcbInfoBuffer]
0x1408e580e  mov     [rbp+57h+arg_0], al
0x1408e5811  lea     rdx, [rbp+57h+pvReadContext]
0x1408e5815  mov     rcx, rsi; Handle
0x1408e5818  call    CmpQueryFileSecurityDescriptor
0x1408e581d  mov     ebx, eax
0x1408e581f  test    eax, eax
0x1408e5821  js      loc_1408E5B72
0x1408e5827  mov     r14, [rbp+57h+pvReadContext]
0x1408e582b  lea     rsi, [rdi+60h]
0x1408e582f  mov     [rbp+57h+arg_18], 1
0x1408e5833  lea     r12, [rdi+58h]
0x1408e5837  lea     rcx, [rdi+44h]
0x1408e583b  cmp     [rbp+57h+arg_0], 0
0x1408e583f  lea     rdx, [rbp+57h+var_98]; PCUNICODE_STRING
0x1408e5843  mov     [rsp+120h+var_D8], rsi; __int64
0x1408e5848  mov     r9, r14
0x1408e584b  mov     [rsp+120h+var_E0], r12; __int64
0x1408e5850  setz    al
0x1408e5853  mov     [rsp+120h+plsnPrevious], rcx; __int64
0x1408e5858  mov     rcx, [rbp+57h+Source]; Source
0x1408e585c  mov     byte ptr [rsp+120h+plsnUndoNext], al; char
0x1408e5860  mov     [rsp+120h+peRecordType], r15; __int64
0x1408e5865  call    CmpStartCLFSLog
0x1408e586a  xor     r15d, r15d
0x1408e586d  mov     ebx, eax
0x1408e586f  test    eax, eax
0x1408e5871  js      loc_1408E5B41
0x1408e5877  lea     eax, [r15+78h]
0x1408e587b  mov     r8d, 20204D43h
0x1408e5881  mov     edx, eax
0x1408e5883  mov     [rbp+57h+pcbInfoBuffer], eax
0x1408e5886  mov     ecx, 100h
0x1408e588b  call    ExAllocatePool2
0x1408e5890  mov     rbx, rax
0x1408e5893  test    rax, rax
0x1408e5896  jz      short loc_1408E58B9
0x1408e5898  mov     rcx, [r12]; plfoLog
0x1408e589c  lea     r8, [rbp+57h+pcbInfoBuffer]; pcbInfoBuffer
0x1408e58a0  mov     rdx, rax; pinfoBuffer
0x1408e58a3  call    cs:__imp_ClfsGetLogFileInformation
0x1408e58aa  nop     dword ptr [rax+rax+00h]
0x1408e58af  xor     edx, edx; Tag
0x1408e58b1  mov     rcx, rbx; P
0x1408e58b4  call    ExFreePoolWithTag
0x1408e58b9  mov     rcx, [r12]; plfoLog
0x1408e58bd  lea     r8, [rbp+57h+pcbWritten]; pcbInfoBuffer
0x1408e58c1  mov     rdx, r13; pinfoBuffer
0x1408e58c4  mov     [rbp+57h+pcbWritten], 78h ; 'x'
0x1408e58cb  call    cs:__imp_ClfsGetLogFileInformation
0x1408e58d2  nop     dword ptr [rax+rax+00h]
0x1408e58d7  mov     ebx, eax
0x1408e58d9  mov     rax, [r13+48h]
0x1408e58dd  mov     [rdi+78h], rax
0x1408e58e1  test    ebx, ebx
0x1408e58e3  js      loc_1408E5B41
0x1408e58e9  mov     rcx, [rsi]; pvMarshalContext
0x1408e58ec  lea     rax, [rbp+57h+pvCursorContext]
0x1408e58f0  lea     r9, [rbp+57h+plsn]; plsn
0x1408e58f4  mov     [rsp+120h+ppvReadContext], rax; ppvReadContext
0x1408e58f9  lea     r8, [rbp+57h+pcbRestartBuffer]; pcbRestartBuffer
0x1408e58fd  lea     rdx, [rbp+57h+ppvRestartBuffer]; ppvRestartBuffer
0x1408e5901  call    cs:__imp_ClfsReadRestartArea
0x1408e5908  nop     dword ptr [rax+rax+00h]
0x1408e590d  cmp     eax, 401A000Ch
0x1408e5912  jz      loc_1408E5A2A
0x1408e5918  mov     rax, [rbp+57h+ppvRestartBuffer]
0x1408e591c  test    rax, rax
0x1408e591f  jz      loc_1408E5A2A
0x1408e5925  mov     rax, [rax]
0x1408e5928  lea     rdx, [rbp+57h+plsn2]; plsn2
0x1408e592c  lea     rcx, [rbp+57h+plsn]; plsn1
0x1408e5930  mov     qword ptr [rbp+57h+plsn2], rax
0x1408e5934  call    cs:__imp_ClfsLsnEqual
0x1408e593b  nop     dword ptr [rax+rax+00h]
0x1408e5940  test    al, al
0x1408e5942  jz      loc_1408E5A32
0x1408e5948  mov     rax, qword ptr [rbp+57h+plsn2]
0x1408e594c  lea     r9, [rbp+57h+ppvReadBuffer]; ppvReadBuffer
0x1408e5950  mov     rcx, [rsi]; pvMarshalContext
0x1408e5953  lea     rdx, [rbp+57h+plsnFirst]; plsnFirst
0x1408e5957  mov     qword ptr [rbp+57h+plsnFirst], rax
0x1408e595b  mov     r8d, 3; peContextMode
0x1408e5961  lea     rax, [rbp+57h+pvReadContext]
0x1408e5965  mov     [rbp+57h+pvReadContext], r15
0x1408e5969  mov     [rsp+120h+var_E0], rax; ppvReadContext
0x1408e596e  lea     rax, [rbp+57h+var_68]
0x1408e5972  mov     [rsp+120h+plsnPrevious], rax; plsnPrevious
0x1408e5977  lea     rax, [rbp+57h+var_60]
0x1408e597b  mov     [rsp+120h+plsnUndoNext], rax; plsnUndoNext
0x1408e5980  lea     rax, [rbp+57h+pcbInfoBuffer]
0x1408e5984  mov     [rsp+120h+peRecordType], rax; peRecordType
0x1408e5989  lea     rax, [rbp+57h+pcbReadBuffer]
0x1408e598d  mov     [rsp+120h+ppvReadContext], rax; pcbReadBuffer
0x1408e5992  mov     [rbp+57h+ppvReadBuffer], r15
0x1408e5996  mov     [rbp+57h+pcbReadBuffer], r15d
0x1408e599a  mov     qword ptr [rbp+57h+var_60], r15
0x1408e599e  mov     qword ptr [rbp+57h+var_68], r15
0x1408e59a2  mov     qword ptr [rbp+57h+plsnRecord], r15
0x1408e59a6  mov     byte ptr [rbp+57h+pcbInfoBuffer], r15b
0x1408e59aa  call    cs:__imp_ClfsReadLogRecord
0x1408e59b1  nop     dword ptr [rax+rax+00h]
0x1408e59b6  test    eax, eax
0x1408e59b8  js      short loc_1408E5A13
0x1408e59ba  mov     rcx, [rbp+57h+pvReadContext]; pvReadContext
0x1408e59be  lea     rax, [rbp+57h+plsnRecord]
0x1408e59c2  mov     [rsp+120h+plsnPrevious], rax; plsnRecord
0x1408e59c7  lea     r9, [rbp+57h+pcbInfoBuffer]; peRecordType
0x1408e59cb  lea     rax, [rbp+57h+var_68]
0x1408e59cf  mov     byte ptr [rbp+57h+pcbInfoBuffer], 1
0x1408e59d3  mov     [rsp+120h+plsnUndoNext], rax; plsnPrevious
0x1408e59d8  lea     r8, [rbp+57h+pcbReadBuffer]; pcbBuffer
0x1408e59dc  lea     rax, [rbp+57h+var_60]
0x1408e59e0  mov     [rsp+120h+peRecordType], rax; plsnUndoNext
0x1408e59e5  lea     rdx, [rbp+57h+ppvReadBuffer]; ppvBuffer
0x1408e59e9  mov     [rsp+120h+ppvReadContext], r15; plsnUser
0x1408e59ee  call    cs:__imp_ClfsReadNextLogRecord
0x1408e59f5  nop     dword ptr [rax+rax+00h]
0x1408e59fa  cmp     eax, 0C0000011h
0x1408e59ff  jnz     short loc_1408E5A07
0x1408e5a01  mov     rax, [r13+58h]
0x1408e5a05  jmp     short loc_1408E5A0F
0x1408e5a07  test    eax, eax
0x1408e5a09  js      short loc_1408E5A13
0x1408e5a0b  mov     rax, qword ptr [rbp+57h+plsnRecord]
0x1408e5a0f  mov     qword ptr [rbp+57h+plsn2], rax
0x1408e5a13  mov     rcx, [rbp+57h+pvReadContext]; pvCursorContext
0x1408e5a17  test    rcx, rcx
0x1408e5a1a  jz      short loc_1408E5A32
0x1408e5a1c  call    cs:__imp_ClfsTerminateReadLog
0x1408e5a23  nop     dword ptr [rax+rax+00h]
0x1408e5a28  jmp     short loc_1408E5A32
0x1408e5a2a  mov     rax, [r13+48h]
0x1408e5a2e  mov     qword ptr [rbp+57h+plsn2], rax
0x1408e5a32  mov     rcx, [rbp+57h+pvCursorContext]; pvCursorContext
0x1408e5a36  test    rcx, rcx
0x1408e5a39  jz      short loc_1408E5A4B
0x1408e5a3b  call    cs:__imp_ClfsTerminateReadLog
0x1408e5a42  nop     dword ptr [rax+rax+00h]
0x1408e5a47  mov     [rbp+57h+pvCursorContext], r15
0x1408e5a4b  lea     rdx, [r13+58h]; plsn2
0x1408e5a4f  lea     rcx, [rbp+57h+plsn2]; plsn1
0x1408e5a53  call    cs:__imp_ClfsLsnEqual
0x1408e5a5a  nop     dword ptr [rax+rax+00h]
0x1408e5a5f  test    al, al
0x1408e5a61  jnz     short loc_1408E5A94
0x1408e5a63  mov     eax, [rdi+68h]
0x1408e5a66  test    al, 4
0x1408e5a68  jz      short loc_1408E5A94
0x1408e5a6a  mov     rbx, qword ptr [rbp+57h+plsn2]
0x1408e5a6e  mov     rcx, rdi
0x1408e5a71  mov     rdx, rbx
0x1408e5a74  call    CmpRmAnalysisPhase
0x1408e5a79  test    eax, eax
0x1408e5a7b  js      short loc_1408E5A90
0x1408e5a7d  mov     rdx, rbx
0x1408e5a80  mov     rcx, rdi
0x1408e5a83  call    CmpRmReDoPhase
0x1408e5a88  mov     rcx, rdi
0x1408e5a8b  call    CmpRmUnDoPhase
0x1408e5a90  and     dword ptr [rdi+68h], 0FFFFFFFBh
0x1408e5a94  mov     rax, [r13+58h]
0x1408e5a98  lea     rdx, [rbp+57h+pvRestartBuffer]; pvRestartBuffer
0x1408e5a9c  mov     rcx, [rsi]; pvMarshalContext
0x1408e5a9f  xor     r9d, r9d; plsnBase
0x1408e5aa2  mov     [rbp+57h+pvRestartBuffer], rax
0x1408e5aa6  lea     rax, [rbp+57h+pcbWritten]
0x1408e5aaa  mov     [rsp+120h+plsnUndoNext], r15; plsnNext
0x1408e5aaf  mov     [rsp+120h+peRecordType], rax; pcbWritten
0x1408e5ab4  lea     r8d, [r9+8]; cbRestartBuffer
0x1408e5ab8  mov     dword ptr [rsp+120h+ppvReadContext], r15d; fFlags
0x1408e5abd  call    cs:__imp_ClfsWriteRestartArea
0x1408e5ac4  nop     dword ptr [rax+rax+00h]
0x1408e5ac9  mov     ebx, eax
0x1408e5acb  cmp     [rbp+57h+arg_18], r15b
0x1408e5acf  jz      short loc_1408E5B41
  ... truncated ...
```
