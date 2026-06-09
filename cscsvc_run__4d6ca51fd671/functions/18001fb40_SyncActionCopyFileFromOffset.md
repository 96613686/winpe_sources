# SyncActionCopyFileFromOffset

- ea: `0x18001fb40`
- end: `0x1800204b7`
- name: `SyncActionCopyFileFromOffset`
- size: `2423`
- prototype: ``
- caller_count: `3`
- callee_count: `21`
- tags: `file_ops, loader_planting`

## callers

- `0x18007b5fc`
- `0x18007d1a0`
- `0x18007d6d8`

## callees

- `0x180005270`
- `0x18001fb40`
- `0x1800204c0`
- `0x180020f2c`
- `0x180020f58`
- `0x180025050`
- `0x180029f70`
- `0x18002c8e8`
- `0x180030a0c`
- `0x1800339b4`
- `0x1800360c0`
- `0x180036394`
- `0x18003670c`
- `0x180036724`
- `0x180039610`
- `0x18003c460`
- `0x18005fa04`
- `0x18007291c`
- `0x18007523c`
- `0x18007e4dc`
- `0x180089010`

## import_xrefs

- `ntdll!NtWriteFile` at `0x18001fff2`
- `ntdll!NtWriteFile` at `0x1800200e5`
- `ntdll!NtWriteFile` at `0x18001fff2`
- `ntdll!NtWriteFile` at `0x1800200e5`
- `ntdll!NtReadFile` at `0x18001febc`
- `ntdll!NtReadFile` at `0x18001febc`
- `ntdll!NtQueryVolumeInformationFile` at `0x18001fc8c`
- `ntdll!NtQueryVolumeInformationFile` at `0x18001fc8c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001fc0f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001ff3d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180020158`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180020244`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180020363`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180020394`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001fc0f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001ff3d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180020158`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180020244`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180020363`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180020394`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001fed4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020009`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800200fc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001fed4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020009`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800200fc`
- `KERNEL32!VirtualFree` at `0x180020449`
- `KERNEL32!VirtualFree` at `0x180020449`

## string_xrefs

- `0x18001fe3a`: `SyncReadFileAtPos: Handle: 0x%p FilePos: %I64d Buffer: 0x%p BytesToRead: %d`
- `0x18001fef9`: `SyncReadFileAtPos: 0x%x`
- `0x18001ff7f`: `SyncWriteFileAtPos: Handle: 0x%p FilePos: %I64d Buffer: 0x%p BytesToWrite: %d`
- `0x18002003d`: `SyncWriteFileAtPos: 0x%x`
- `0x18002007c`: `SyncWriteFile: Handle: 0x%p Buffer: 0x%p BytesToWrite: %d`
- `0x180020128`: `SyncWriteFile: 0x%x`
- `0x18001fbbd`: `SyncActionCopyFileFromOffset: OpArgs 0x%p SourceHandle 0x%p TargetHandle: 0x%p Offset: %I64d Size: %I64d`
- `0x18001fcbb`: `SyncActionCopyFileFromOffset: Failed to get BytesPerSector status=%#x`
- `0x18001fd16`: `SyncActionCopyFileFromOffset: SYNC_COPY_BLOCK_SIZE is not a multiple of BytesPerSector, Abort!`
- `0x18002046a`: `SyncActionCopyFileFromOffset: 0x%x`

## pseudocode

```c
__int64 __fastcall SyncActionCopyFileFromOffset(
        __int64 a1,
        void *a2,
        void *a3,
        LARGE_INTEGER a4,
        __int64 a5,
        __int64 a6,
        char a7)
{
  LARGE_INTEGER v7; // rsi
  HANDLE v9; // rbx
  __int64 v11; // r14
  __int64 v12; // rdx
  __int64 v13; // r8
  char *Buffer; // r15
  NTSTATUS v15; // edi
  __int64 v16; // rdx
  int v17; // ebx
  NTSTATUS FileAtPos; // eax
  __int64 v19; // rcx
  ULONG v20; // ebx
  int v21; // eax
  __int64 v22; // rax
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rax
  __int64 v25; // r14
  unsigned int Status; // ebx
  __int64 v27; // rdx
  __int64 v28; // rax
  struct CPerfCounterSetInstance *v29; // r10
  __int64 v30; // rax
  struct CPerfCounterSetInstance *v31; // r10
  LONGLONG v32; // rbx
  __int64 (__fastcall *v33)(__int128 *, __int64); // rax
  __int64 v34; // rdx
  int v35; // eax
  NTSTATUS v36; // eax
  NTSTATUS v37; // eax
  __int64 PerformanceFrequency; // rax
  __int64 v39; // rax
  FS_INFORMATION_CLASS FsInformationClass[2]; // [rsp+20h] [rbp-C1h]
  FS_INFORMATION_CLASS FsInformationClassa[2]; // [rsp+20h] [rbp-C1h]
  char v43; // [rsp+50h] [rbp-91h] BYREF
  char v44; // [rsp+51h] [rbp-90h]
  LARGE_INTEGER ByteOffset; // [rsp+58h] [rbp-89h] BYREF
  LARGE_INTEGER v46; // [rsp+60h] [rbp-81h] BYREF
  LARGE_INTEGER v47; // [rsp+68h] [rbp-79h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-71h] BYREF
  HANDLE hHandle; // [rsp+80h] [rbp-61h]
  LARGE_INTEGER PerformanceCount; // [rsp+88h] [rbp-59h] BYREF
  unsigned __int64 v51; // [rsp+90h] [rbp-51h]
  __int64 v52; // [rsp+98h] [rbp-49h]
  __int128 v53; // [rsp+A0h] [rbp-41h] BYREF
  __int128 v54; // [rsp+B0h] [rbp-31h]
  __int128 FsInformation; // [rsp+C0h] [rbp-21h] BYREF
  __int64 v56; // [rsp+D0h] [rbp-11h]

  hHandle = a2;
  v43 = 0;
  v53 = 0;
  PerformanceCount.QuadPart = 0;
  v7 = a4;
  v54 = 0;
  v47.QuadPart = 0;
  v46.QuadPart = 0;
  v9 = a2;
  v44 = 0;
  v11 = a5;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    SyncTraceOutputInternal(
      L"SyncActionCopyFileFromOffset: OpArgs 0x%p SourceHandle 0x%p TargetHandle: 0x%p Offset: %I64d Size: %I64d",
      a1,
      a2,
      a3,
      a4.QuadPart,
      a5);
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qqqii)(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      v12,
      v13,
      a1,
      v9,
      a3,
      (LARGE_INTEGER)v7.QuadPart,
      a5);
  }
  SyncIsStoreHandle(v9);
  QueryPerformanceCounter(&PerformanceCount);
  Buffer = (char *)SyncLargeAlloc(0x10000);
  if ( Buffer )
  {
    v15 = SyncActionQueueAborted(*(_QWORD *)(*(_QWORD *)a1 + 24LL), &v43);
    if ( !v15 && v43 )
    {
LABEL_8:
      v15 = -1073741248;
      goto LABEL_98;
    }
    if ( (*(_BYTE *)(a1 + 32) & 4) != 0 )
    {
      v56 = 0;
      FsInformation = 0;
      IoStatusBlock = 0;
      v15 = NtQueryVolumeInformationFile(v9, &IoStatusBlock, &FsInformation, 0x18u, FileFsSizeInformation);
      if ( v15 < 0 )
      {
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          SyncTraceOutputInternal(
            L"SyncActionCopyFileFromOffset: Failed to get BytesPerSector status=%#x",
            (unsigned int)v15);
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            26,
            WPP_6245c1b01f713a032f327efa2846a355_Traceguids,
            (unsigned int)v15);
        }
        goto LABEL_98;
      }
      if ( 0x10000u % HIDWORD(v56) )
      {
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          SyncTraceOutputInternal(L"SyncActionCopyFileFromOffset: SYNC_COPY_BLOCK_SIZE is not a multiple of BytesPerSector, Abort!");
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 27, WPP_6245c1b01f713a032f327efa2846a355_Traceguids);
        }
        v15 = -1073741823;
        goto LABEL_98;
      }
      v16 = v7.QuadPart % HIDWORD(v56);
      if ( v16 )
      {
        v17 = v7.LowPart - v16;
        FileAtPos = SyncReadFileAtPos(hHandle);
        v15 = 0;
        if ( FileAtPos != -1073741807 )
          v15 = FileAtPos;
        if ( v15 < 0 )
          goto LABEL_98;
        v19 = v7.LowPart - v17;
        if ( a5 + v19 > 0x10000 )
        {
          if ( (unsigned int)v19 > 0x10000 )
          {
            v15 = -1073741675;
            goto LABEL_98;
          }
          v20 = 0x10000 - v19;
        }
        else
        {
          v20 = a5;
        }
        v21 = a7 ? SyncWriteFileAtPos(a3) : SyncWriteFile(a3, &Buffer[v19], v20);
        v15 = v21;
        if ( v21 < 0 )
        {
LABEL_98:
          ++NumLargeFree;
          VirtualFree(Buffer, 0, 0x8000u);
          goto LABEL_99;
        }
        v22 = v20;
        v9 = hHandle;
        v7.QuadPart += v22;
        v11 = a5 - v22;
      }
    }
    v23 = v11 / 0x10000;
    v52 = v11 / 0x10000;
    v24 = 0;
    v25 = v11 % 0x10000;
    while ( 1 )
    {
      v51 = v24;
      if ( v24 >= v23 )
      {
        if ( (_DWORD)v25 )
        {
          v36 = SyncReadFileAtPos(v9);
          v15 = 0;
          if ( v36 != -1073741807 )
            v15 = v36;
          if ( v15 >= 0 )
          {
            QueryPerformanceCounter(&v47);
            v37 = a7 ? SyncWriteFileAtPos(a3) : SyncWriteFile(a3, Buffer, v25);
            v15 = v37;
            QueryPerformanceCounter(&v46);
            if ( v15 >= 0 )
            {
              if ( v44 )
              {
                PerfCtr_IncrClientToServerBytes((unsigned int)v25);
                PerformanceFrequency = SyncActionGetPerformanceFrequency();
                PerfCtr_IncrClientToServerByteRate(
                  (unsigned int)v25,
                  (v46.QuadPart - v47.QuadPart) / (PerformanceFrequency / 1000));
              }
              else
              {
                PerfCtr_IncrServerToClientBytes((unsigned int)v25);
                v39 = SyncActionGetPerformanceFrequency();
                PerfCtr_IncrServerToClientByteRate((unsigned int)v25, (v46.QuadPart - v47.QuadPart) / (v39 / 1000));
              }
            }
          }
        }
        goto LABEL_98;
      }
      ByteOffset.QuadPart = 0;
      IoStatusBlock = 0;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
      {
        FsInformationClass[0] = 0x10000;
        SyncTraceOutputInternal(
          L"SyncReadFileAtPos: Handle: 0x%p FilePos: %I64d Buffer: 0x%p BytesToRead: %d",
          v9,
          v7.QuadPart,
          Buffer,
          *(_QWORD *)FsInformationClass);
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_qqqD)(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          76,
          WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids,
          v9,
          (LARGE_INTEGER)v7.QuadPart,
          Buffer,
          0x10000);
      }
      ByteOffset = v7;
      Status = NtReadFile(v9, 0, 0, 0, &IoStatusBlock, Buffer, 0x10000u, &ByteOffset, 0);
      if ( Status == 259 )
      {
        Status = 258;
        if ( !WaitForSingleObject(hHandle, 0x3E8u) )
          Status = IoStatusBlock.Status;
      }
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
      {
        SyncTraceOutputInternal(L"SyncReadFileAtPos: 0x%x", Status);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 77, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, Status);
      }
      v15 = 0;
      if ( Status != -1073741807 )
        v15 = Status;
      if ( v15 < 0 )
        goto LABEL_98;
      QueryPerformanceCounter(&v47);
      IoStatusBlock = 0;
      if ( a7 )
      {
        ByteOffset.QuadPart = 0;
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
        {
          FsInformationClassa[0] = 0x10000;
          SyncTraceOutputInternal(
            L"SyncWriteFileAtPos: Handle: 0x%p FilePos: %I64d Buffer: 0x%p BytesToWrite: %d",
            a3,
            v7.QuadPart,
            Buffer,
            *(_QWORD *)FsInformationClassa);
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_qqqD)(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            78,
            WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids,
            a3,
            (LARGE_INTEGER)v7.QuadPart,
            Buffer,
            0x10000);
        }
        ByteOffset = v7;
        v15 = NtWriteFile(a3, 0, 0, 0, &IoStatusBlock, Buffer, 0x10000u, &ByteOffset, 0);
        if ( v15 == 259 )
        {
          v15 = 258;
          if ( !WaitForSingleObject(a3, 0x3E8u) )
            v15 = IoStatusBlock.Status;
        }
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
        {
          SyncTraceOutputInternal(L"SyncWriteFileAtPos: 0x%x", (unsigned int)v15);
          v27 = 79;
LABEL_66:
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            v27,
            WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids,
            (unsigned int)v15);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
        {
          SyncTraceOutputInternal(L"SyncWriteFile: Handle: 0x%p Buffer: 0x%p BytesToWrite: %d", a3, Buffer, 0x10000);
          WPP_SF_qqD(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            82,
            WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids,
            a3,
            Buffer,
            0x10000);
        }
        v15 = NtWriteFile(a3, 0, 0, 0, &IoStatusBlock, Buffer, 0x10000u, 0, 0);
        if ( v15 == 259 )
        {
          v15 = 258;
          if ( !WaitForSingleObject(a3, 0x3E8u) )
            v15 = IoStatusBlock.Status;
        }
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
        {
          SyncTraceOutputInternal(L"SyncWriteFile: 0x%x", (unsigned int)v15);
          v27 = 83;
          goto LABEL_66;
        }
      }
      QueryPerformanceCounter(&v46);
      if ( v15 < 0 )
        goto LABEL_98;
      if ( v44 )
      {
        if ( g_pPerfCtrSetInst_OfflineFilesCounters )
          _InterlockedAdd64((volatile signed __int64 *)g_pPerfCtrSetInst_OfflineFilesCounters + 8, 0x10000u);
        v28 = SyncActionGetPerformanceFrequency();
        v29 = g_pPerfCtrSetInst_OfflineFilesCounters;
        if ( g_pPerfCtrSetInst_OfflineFilesCounters )
        {
          _InterlockedAdd(
            (volatile signed __int32 *)g_pPerfCtrSetInst_OfflineFilesCounters + 31,
            (v46.QuadPart - v47.QuadPart) / (v28 / 1000));
          _InterlockedAdd64((volatile signed __int64 *)v29 + 18, 0x3E80000u);
        }
      }
      else
      {
        if ( g_pPerfCtrSetInst_OfflineFilesCounters )
          _InterlockedAdd64((volatile signed __int64 *)g_pPerfCtrSetInst_OfflineFilesCounters + 5, 0x10000u);
        v30 = SyncActionGetPerformanceFrequency();
        v31 = g_pPerfCtrSetInst_OfflineFilesCounters;
        if ( g_pPerfCtrSetInst_OfflineFilesCounters )
        {
          _InterlockedAdd(
            (volatile signed __int32 *)g_pPerfCtrSetInst_OfflineFilesCounters + 21,
            (v46.QuadPart - v47.QuadPart) / (v30 / 1000));
          _InterlockedAdd64((volatile signed __int64 *)v31 + 13, 0x3E80000u);
        }
      }
      ByteOffset.QuadPart = 0;
      if ( QueryPerformanceCounter(&ByteOffset) )
      {
        v32 = ByteOffset.QuadPart - PerformanceCount.QuadPart;
        if ( v32 / (SyncActionGetPerformanceFrequency() / 1000) < 1000 )
          goto LABEL_85;
        PerformanceCount = ByteOffset;
      }
      v15 = SyncActionQueueAborted(*(_QWORD *)(*(_QWORD *)a1 + 24LL), &v43);
      if ( !v15 && v43 )
        goto LABEL_8;
      v33 = *(__int64 (__fastcall **)(__int128 *, __int64))(a1 + 80);
      if ( v33 )
      {
        v34 = *(_QWORD *)(a1 + 96);
        *(_QWORD *)&v53 = *(_QWORD *)(a1 + 16);
        *((_QWORD *)&v53 + 1) = *(_QWORD *)(a1 + 8);
        LODWORD(v54) = *(_DWORD *)(a1 + 240);
        *((_QWORD *)&v54 + 1) = v51 << 16;
        v35 = v33(&v53, v34);
        if ( v35 == 2 )
        {
          SyncActionQueueAbort(*(_QWORD *)(*(_QWORD *)a1 + 24LL));
          goto LABEL_8;
        }
        if ( v35 == 1 )
          goto LABEL_8;
      }
LABEL_85:
      v9 = hHandle;
      v24 = v51 + 1;
      v23 = v52;
      v7.QuadPart += 0x10000LL;
    }
  }
  v15 = -1073741670;
LABEL_99:
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncActionCopyFileFromOffset: 0x%x", (unsigned int)v15);
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      28,
      WPP_6245c1b01f713a032f327efa2846a355_Traceguids,
      (unsigned int)v15);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001fb40  push    rbp
0x18001fb42  push    rbx
0x18001fb43  push    rsi
0x18001fb44  push    rdi
0x18001fb45  push    r12
0x18001fb47  push    r13
0x18001fb49  push    r14
0x18001fb4b  push    r15
0x18001fb4d  lea     rbp, [rsp-7]
0x18001fb52  sub     rsp, 0E8h
0x18001fb59  mov     rax, cs:__security_cookie
0x18001fb60  xor     rax, rsp
0x18001fb63  mov     [rbp+3Fh+var_48], rax
0x18001fb67  xor     edi, edi
0x18001fb69  mov     [rbp+3Fh+hHandle], rdx
0x18001fb6d  xorps   xmm0, xmm0
0x18001fb70  mov     [rsp+120h+var_D0], dil
0x18001fb75  movups  [rbp+3Fh+var_80], xmm0
0x18001fb79  mov     qword ptr [rbp+3Fh+PerformanceCount], rdi
0x18001fb7d  mov     rsi, r9
0x18001fb80  movups  [rbp+3Fh+var_70], xmm0
0x18001fb84  mov     qword ptr [rbp+3Fh+var_B8], rdi
0x18001fb88  mov     r12, r8
0x18001fb8b  mov     qword ptr [rsp+120h+var_C0], rdi
0x18001fb90  mov     rbx, rdx
0x18001fb93  mov     [rsp+120h+var_CF], dil
0x18001fb98  mov     r13, rcx
0x18001fb9b  mov     rax, cs:WPP_GLOBAL_Control
0x18001fba2  lea     rcx, WPP_GLOBAL_Control
0x18001fba9  mov     r14, [rbp+3Fh+arg_20]
0x18001fbad  cmp     rax, rcx
0x18001fbb0  jz      short loc_18001FBFE
0x18001fbb2  test    byte ptr [rax+6Ch], 4
0x18001fbb6  jz      short loc_18001FBFE
0x18001fbb8  mov     [rsp+120h+Buffer], r14
0x18001fbbd  lea     rcx, aSyncactioncopy_8; "SyncActionCopyFileFromOffset: OpArgs 0x"...
0x18001fbc4  mov     qword ptr [rsp+120h+FsInformationClass], r9
0x18001fbc9  mov     r9, r8
0x18001fbcc  mov     r8, rdx
0x18001fbcf  mov     rdx, r13
0x18001fbd2  call    SyncTraceOutputInternal
0x18001fbd7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fbde  mov     r9, r13
0x18001fbe1  mov     [rsp+120h+ByteOffset], r14
0x18001fbe6  mov     qword ptr [rsp+120h+Length], rsi
0x18001fbeb  mov     [rsp+120h+Buffer], r12
0x18001fbf0  mov     rcx, [rcx+60h]
0x18001fbf4  mov     qword ptr [rsp+120h+FsInformationClass], rbx
0x18001fbf9  call    WPP_SF_qqqii
0x18001fbfe  lea     rdx, [rsp+120h+var_CF]
0x18001fc03  mov     rcx, rbx; FileHandle
0x18001fc06  call    SyncIsStoreHandle
0x18001fc0b  lea     rcx, [rbp+3Fh+PerformanceCount]; lpPerformanceCount
0x18001fc0f  call    cs:__imp_QueryPerformanceCounter
0x18001fc15  mov     ecx, 10000h
0x18001fc1a  call    SyncLargeAlloc
0x18001fc1f  mov     r15, rax
0x18001fc22  test    rax, rax
0x18001fc25  jnz     short loc_18001FC31
0x18001fc27  mov     edi, 0C000009Ah
0x18001fc2c  jmp     loc_18002044F
0x18001fc31  mov     rcx, [r13+0]
0x18001fc35  lea     rdx, [rsp+120h+var_D0]
0x18001fc3a  mov     rcx, [rcx+18h]
0x18001fc3e  call    SyncActionQueueAborted
0x18001fc43  mov     edi, eax
0x18001fc45  test    eax, eax
0x18001fc47  jnz     short loc_18001FC59
0x18001fc49  cmp     [rsp+120h+var_D0], al
0x18001fc4d  jz      short loc_18001FC59
0x18001fc4f  mov     edi, 0C0000240h
0x18001fc54  jmp     loc_180020437
0x18001fc59  test    byte ptr [r13+20h], 4
0x18001fc5e  jz      loc_18001FDE5
0x18001fc64  xor     eax, eax
0x18001fc66  mov     [rsp+120h+FsInformationClass], 3; FsInformationClass
0x18001fc6e  xorps   xmm0, xmm0
0x18001fc71  mov     [rbp+3Fh+var_50], rax
0x18001fc75  lea     r8, [rbp+3Fh+FsInformation]; FsInformation
0x18001fc79  mov     rcx, rbx; FileHandle
0x18001fc7c  lea     rdx, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x18001fc80  lea     r9d, [rax+18h]; Length
0x18001fc84  movups  [rbp+3Fh+FsInformation], xmm0
0x18001fc88  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x18001fc8c  call    cs:__imp_NtQueryVolumeInformationFile
0x18001fc92  mov     edi, eax
0x18001fc94  test    eax, eax
0x18001fc96  jns     short loc_18001FCEB
0x18001fc98  mov     rax, cs:WPP_GLOBAL_Control
0x18001fc9f  lea     rcx, WPP_GLOBAL_Control
0x18001fca6  cmp     rax, rcx
0x18001fca9  jz      loc_180020437
0x18001fcaf  test    byte ptr [rax+6Ch], 1
0x18001fcb3  jz      loc_180020437
0x18001fcb9  mov     edx, edi
0x18001fcbb  lea     rcx, aSyncactioncopy_18; "SyncActionCopyFileFromOffset: Failed to"...
0x18001fcc2  call    SyncTraceOutputInternal
0x18001fcc7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fcce  lea     r8, WPP_6245c1b01f713a032f327efa2846a355_Traceguids
0x18001fcd5  mov     edx, 1Ah
0x18001fcda  mov     r9d, edi
0x18001fcdd  mov     rcx, [rcx+60h]
0x18001fce1  call    WPP_SF_d
0x18001fce6  jmp     loc_180020437
0x18001fceb  xor     edx, edx
0x18001fced  mov     r8d, 10000h
0x18001fcf3  mov     eax, r8d
0x18001fcf6  div     dword ptr [rbp+3Fh+var_50+4]
0x18001fcf9  test    edx, edx
0x18001fcfb  jz      short loc_18001FD48
0x18001fcfd  mov     rax, cs:WPP_GLOBAL_Control
0x18001fd04  lea     rcx, WPP_GLOBAL_Control
0x18001fd0b  cmp     rax, rcx
0x18001fd0e  jz      short loc_18001FD3E
0x18001fd10  test    byte ptr [rax+6Ch], 1
0x18001fd14  jz      short loc_18001FD3E
0x18001fd16  lea     rcx, aSyncactioncopy_42; "SyncActionCopyFileFromOffset: SYNC_COPY"...
0x18001fd1d  call    SyncTraceOutputInternal
0x18001fd22  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd29  lea     r8, WPP_6245c1b01f713a032f327efa2846a355_Traceguids
0x18001fd30  mov     edx, 1Bh
0x18001fd35  mov     rcx, [rcx+60h]
0x18001fd39  call    WPP_SF_
0x18001fd3e  mov     edi, 0C0000001h
0x18001fd43  jmp     loc_180020437
0x18001fd48  mov     ecx, dword ptr [rbp+3Fh+var_50+4]
0x18001fd4b  mov     rax, rsi
0x18001fd4e  cqo
0x18001fd50  idiv    rcx
0x18001fd53  test    rdx, rdx
0x18001fd56  jz      loc_18001FDEB
0x18001fd5c  mov     rcx, [rbp+3Fh+hHandle]; hHandle
0x18001fd60  mov     r9d, r8d
0x18001fd63  mov     rbx, rsi
0x18001fd66  mov     r8, r15
0x18001fd69  sub     rbx, rdx
0x18001fd6c  mov     rdx, rbx
0x18001fd6f  call    SyncReadFileAtPos
0x18001fd74  xor     edi, edi
0x18001fd76  cmp     eax, 0C0000011h
0x18001fd7b  cmovnz  edi, eax
0x18001fd7e  test    edi, edi
0x18001fd80  js      loc_180020437
0x18001fd86  mov     eax, esi
0x18001fd88  mov     edx, 10000h
0x18001fd8d  sub     eax, ebx
0x18001fd8f  mov     ecx, eax
0x18001fd91  add     rax, r14
0x18001fd94  cmp     rax, rdx
0x18001fd97  jg      short loc_18001FD9E
0x18001fd99  mov     ebx, r14d
0x18001fd9c  jmp     short loc_18001FDAA
0x18001fd9e  cmp     ecx, edx
0x18001fda0  ja      loc_180020053
0x18001fda6  mov     ebx, edx
0x18001fda8  sub     ebx, ecx
0x18001fdaa  cmp     [rbp+3Fh+arg_30], 0
0x18001fdae  lea     rdx, [rcx+r15]; Buffer
0x18001fdb2  mov     rcx, r12; hHandle
0x18001fdb5  jz      short loc_18001FDC7
0x18001fdb7  mov     r8, rdx
0x18001fdba  mov     r9d, ebx
0x18001fdbd  mov     rdx, rsi
0x18001fdc0  call    SyncWriteFileAtPos
0x18001fdc5  jmp     short loc_18001FDCF
0x18001fdc7  mov     r8d, ebx; Length
0x18001fdca  call    SyncWriteFile
0x18001fdcf  mov     edi, eax
0x18001fdd1  test    eax, eax
0x18001fdd3  js      loc_180020437
0x18001fdd9  mov     eax, ebx
0x18001fddb  mov     rbx, [rbp+3Fh+hHandle]
0x18001fddf  add     rsi, rax
0x18001fde2  sub     r14, rax
0x18001fde5  mov     r8d, 10000h
0x18001fdeb  mov     rax, r14
0x18001fdee  cqo
0x18001fdf0  idiv    r8
0x18001fdf3  mov     rcx, rax
0x18001fdf6  mov     [rbp+3Fh+var_88], rax
0x18001fdfa  xor     eax, eax
0x18001fdfc  mov     r14, rdx
0x18001fdff  mov     [rbp+3Fh+var_90], rax
0x18001fe03  cmp     rax, rcx
0x18001fe06  jnb     loc_180020333
0x18001fe0c  xorps   xmm0, xmm0
0x18001fe0f  mov     qword ptr [rsp+120h+var_C8], 0
0x18001fe18  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x18001fe1c  mov     rax, cs:WPP_GLOBAL_Control
0x18001fe23  lea     rdi, WPP_GLOBAL_Control
0x18001fe2a  cmp     rax, rdi
0x18001fe2d  jz      short loc_18001FE86
0x18001fe2f  test    byte ptr [rax+6Ch], 4
0x18001fe33  jz      short loc_18001FE86
0x18001fe35  mov     [rsp+120h+FsInformationClass], r8d
0x18001fe3a  lea     rcx, aSyncreadfileat; "SyncReadFileAtPos: Handle: 0x%p FilePos"...
0x18001fe41  mov     r8, rsi
0x18001fe44  mov     r9, r15
0x18001fe47  mov     rdx, rbx
0x18001fe4a  call    SyncTraceOutputInternal
0x18001fe4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe56  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x18001fe5d  mov     [rsp+120h+Length], 10000h
0x18001fe65  mov     edx, 4Ch ; 'L'
0x18001fe6a  mov     [rsp+120h+Buffer], r15
0x18001fe6f  mov     r9, rbx
0x18001fe72  mov     qword ptr [rsp+120h+FsInformationClass], rsi
0x18001fe77  mov     rcx, [rcx+60h]
0x18001fe7b  call    WPP_SF_qqqD
0x18001fe80  mov     r8d, 10000h
0x18001fe86  mov     [rsp+120h+Key], 0; Key
0x18001fe8f  lea     rax, [rsp+120h+var_C8]
0x18001fe94  mov     [rsp+120h+ByteOffset], rax; ByteOffset
0x18001fe99  xor     r9d, r9d; ApcContext
0x18001fe9c  mov     [rsp+120h+Length], r8d; Length
0x18001fea1  lea     rax, [rbp+3Fh+IoStatusBlock]
0x18001fea5  mov     [rsp+120h+Buffer], r15; Buffer
0x18001feaa  xor     r8d, r8d; ApcRoutine
0x18001fead  xor     edx, edx; Event
0x18001feaf  mov     qword ptr [rsp+120h+FsInformationClass], rax; IoStatusBlock
0x18001feb4  mov     rcx, rbx; FileHandle
0x18001feb7  mov     qword ptr [rsp+120h+var_C8], rsi
0x18001febc  call    cs:__imp_NtReadFile
0x18001fec2  mov     ebx, eax
0x18001fec4  cmp     eax, 103h
0x18001fec9  jnz     short loc_18001FEE5
0x18001fecb  mov     rcx, [rbp+3Fh+hHandle]; hHandle
0x18001fecf  mov     edx, 3E8h; dwMilliseconds
0x18001fed4  call    cs:__imp_WaitForSingleObject
0x18001feda  test    eax, eax
0x18001fedc  mov     ebx, 102h
0x18001fee1  cmovz   ebx, dword ptr [rbp+3Fh+IoStatusBlock]
0x18001fee5  mov     rax, cs:WPP_GLOBAL_Control
0x18001feec  cmp     rax, rdi
0x18001feef  jz      short loc_18001FF24
0x18001fef1  test    byte ptr [rax+6Ch], 8
0x18001fef5  jz      short loc_18001FF24
0x18001fef7  mov     edx, ebx
0x18001fef9  lea     rcx, aSyncreadfileat_0; "SyncReadFileAtPos: 0x%x"
0x18001ff00  call    SyncTraceOutputInternal
0x18001ff05  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff0c  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x18001ff13  mov     edx, 4Dh ; 'M'
0x18001ff18  mov     r9d, ebx
0x18001ff1b  mov     rcx, [rcx+60h]
0x18001ff1f  call    WPP_SF_d
0x18001ff24  xor     edi, edi
0x18001ff26  cmp     ebx, 0C0000011h
0x18001ff2c  cmovnz  edi, ebx
0x18001ff2f  xor     ebx, ebx
0x18001ff31  test    edi, edi
0x18001ff33  js      loc_180020437
0x18001ff39  lea     rcx, [rbp+3Fh+var_B8]; lpPerformanceCount
0x18001ff3d  call    cs:__imp_QueryPerformanceCounter
0x18001ff43  xorps   xmm0, xmm0
0x18001ff46  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x18001ff4a  cmp     [rbp+3Fh+arg_30], bl
0x18001ff4d  jz      loc_18002005D
0x18001ff53  mov     qword ptr [rsp+120h+var_C8], rbx
0x18001ff58  mov     rax, cs:WPP_GLOBAL_Control
0x18001ff5f  lea     rcx, WPP_GLOBAL_Control
0x18001ff66  cmp     rax, rcx
0x18001ff69  jz      short loc_18001FFBD
0x18001ff6b  test    byte ptr [rax+6Ch], 4
0x18001ff6f  jz      short loc_18001FFBD
0x18001ff71  mov     r9, r15
0x18001ff74  mov     [rsp+120h+FsInformationClass], 10000h
0x18001ff7c  mov     r8, rsi
0x18001ff7f  lea     rcx, aSyncwritefilea; "SyncWriteFileAtPos: Handle: 0x%p FilePo"...
0x18001ff86  mov     rdx, r12
0x18001ff89  call    SyncTraceOutputInternal
0x18001ff8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff95  lea     edx, [rbx+4Eh]
0x18001ff98  mov     [rsp+120h+Length], 10000h
0x18001ffa0  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x18001ffa7  mov     [rsp+120h+Buffer], r15
0x18001ffac  mov     r9, r12
0x18001ffaf  mov     qword ptr [rsp+120h+FsInformationClass], rsi
0x18001ffb4  mov     rcx, [rcx+60h]
0x18001ffb8  call    WPP_SF_qqqD
0x18001ffbd  mov     [rsp+120h+Key], rbx; Key
0x18001ffc2  lea     rax, [rsp+120h+var_C8]
0x18001ffc7  mov     [rsp+120h+ByteOffset], rax; ByteOffset
0x18001ffcc  xor     r9d, r9d; ApcContext
0x18001ffcf  mov     [rsp+120h+Length], 10000h; Length
0x18001ffd7  lea     rax, [rbp+3Fh+IoStatusBlock]
0x18001ffdb  mov     [rsp+120h+Buffer], r15; Buffer
0x18001ffe0  xor     r8d, r8d; ApcRoutine
0x18001ffe3  xor     edx, edx; Event
0x18001ffe5  mov     qword ptr [rsp+120h+FsInformationClass], rax; IoStatusBlock
0x18001ffea  mov     rcx, r12; FileHandle
0x18001ffed  mov     qword ptr [rsp+120h+var_C8], rsi
0x18001fff2  call    cs:__imp_NtWriteFile
0x18001fff8  mov     edi, eax
0x18001fffa  cmp     eax, 103h
0x18001ffff  jnz     short loc_18002001A
0x180020001  mov     edx, 3E8h; dwMilliseconds
0x180020006  mov     rcx, r12; hHandle
0x180020009  call    cs:__imp_WaitForSingleObject
0x18002000f  test    eax, eax
  ... truncated ...
```
