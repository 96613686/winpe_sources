# SyncActionReadFile

- ea: `0x18001f534`
- end: `0x18001fb39`
- name: `SyncActionReadFile`
- size: `1541`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, loader_planting`

## callers

- `0x180002540`
- `0x18007ab30`

## callees

- `0x1800053e0`
- `0x18001f534`
- `0x1800204c0`
- `0x180020f2c`
- `0x180020f58`
- `0x180030aec`
- `0x180034eb8`
- `0x1800360c0`
- `0x180036394`
- `0x180039610`
- `0x18003c460`
- `0x18004fef4`
- `0x18007291c`
- `0x18007523c`
- `0x180089010`

## import_xrefs

- `ntdll!NtReadFile` at `0x18001f898`
- `ntdll!NtReadFile` at `0x18001f898`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f5e3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f7f9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f907`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f996`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f5e3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f7f9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f907`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f996`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f8b0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f8b0`
- `KERNEL32!VirtualFree` at `0x18001fa74`
- `KERNEL32!VirtualFree` at `0x18001fa74`

## string_xrefs

- `0x18001f82d`: `SyncReadFileAtPos: Handle: 0x%p FilePos: %I64d Buffer: 0x%p BytesToRead: %d`
- `0x18001f8d8`: `SyncReadFileAtPos: 0x%x`
- `0x18001f5b5`: `SyncActionReadFile: SourceHandle: 0x%p`
- `0x18001f620`: `SyncActionReadFile: Bailing out with 0x%08x as fill will not succeed`
- `0x18001f67b`: `SyncActionReadFile: Failed to allocate %d byte buffer`
- `0x18001f6df`: `SyncActionReadFile: SyncQueryInformationLocal to find local File EOF failed with %x`
- `0x18001f748`: `SyncActionReadFile: SyncGetFileSize failed with %x`
- `0x18001f79a`: `SyncActionReadFile: Size < LocalEof Aborting!`
- `0x18001fb23`: `SyncActionReadFile: SyncReadFileAtPos failed with %x`
- `0x18001fa8e`: `SyncActionReadFile: 0x%x`

## pseudocode

```c
__int64 __fastcall SyncActionReadFile(__int64 a1, void *a2)
{
  ULONG Length; // esi
  void *Buffer; // r13
  CObjectMonitor *v6; // rax
  unsigned int FileSize; // ebx
  unsigned int InformationLocal; // ebx
  LARGE_INTEGER v9; // rdi
  __int64 v10; // rdx
  LARGE_INTEGER v11; // r8
  unsigned int Status; // r14d
  __int64 PerformanceFrequency; // rax
  struct CPerfCounterSetInstance *v14; // r10
  LONGLONG v15; // rbx
  __int64 (__fastcall *v16)(__int128 *, __int64); // rax
  __int64 v17; // rdx
  int v18; // eax
  PIO_STATUS_BLOCK IoStatusBlock; // [rsp+20h] [rbp-A9h]
  _BYTE v21[7]; // [rsp+51h] [rbp-78h] BYREF
  LARGE_INTEGER ByteOffset; // [rsp+58h] [rbp-71h] BYREF
  LARGE_INTEGER v23; // [rsp+60h] [rbp-69h]
  LARGE_INTEGER PerformanceCount; // [rsp+68h] [rbp-61h] BYREF
  LARGE_INTEGER v25; // [rsp+70h] [rbp-59h] BYREF
  LARGE_INTEGER v26; // [rsp+78h] [rbp-51h] BYREF
  __int128 v27; // [rsp+80h] [rbp-49h] BYREF
  __int128 v28; // [rsp+90h] [rbp-39h]
  struct _IO_STATUS_BLOCK v29; // [rsp+A0h] [rbp-29h] BYREF
  __int128 v30; // [rsp+B0h] [rbp-19h]
  __int128 v31; // [rsp+C0h] [rbp-9h]
  __int128 v32; // [rsp+D0h] [rbp+7h]
  __int64 v33; // [rsp+E0h] [rbp+17h]

  v23.QuadPart = 0;
  v21[0] = 0;
  v33 = 0;
  PerformanceCount.QuadPart = 0;
  v30 = 0;
  v26.QuadPart = 0;
  v31 = 0;
  v25.QuadPart = 0;
  v32 = 0;
  v27 = 0;
  v28 = 0;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
  {
    SyncTraceOutputInternal(L"SyncActionReadFile: SourceHandle: 0x%p");
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 31, WPP_6245c1b01f713a032f327efa2846a355_Traceguids, a2);
  }
  QueryPerformanceCounter(&PerformanceCount);
  SyncWillFillSucceed(a2);
  Length = 0x10000;
  Buffer = (void *)SyncLargeAlloc(0x10000);
  if ( Buffer )
  {
    InformationLocal = SyncQueryInformationLocal(a2);
    if ( InformationLocal )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        SyncTraceOutputInternal(
          L"SyncActionReadFile: SyncQueryInformationLocal to find local File EOF failed with %x",
          InformationLocal);
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          34,
          WPP_6245c1b01f713a032f327efa2846a355_Traceguids,
          InformationLocal);
      }
      v9.QuadPart = 0;
    }
    else
    {
      v9 = *(LARGE_INTEGER *)((char *)&v32 + 8);
    }
    FileSize = SyncGetFileSize(a2);
    if ( FileSize )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        SyncTraceOutputInternal(L"SyncActionReadFile: SyncGetFileSize failed with %x", FileSize);
        v10 = 35;
LABEL_19:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), v10, WPP_6245c1b01f713a032f327efa2846a355_Traceguids, FileSize);
      }
      goto LABEL_55;
    }
    v11 = v23;
    if ( v23.QuadPart < v9.QuadPart )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        SyncTraceOutputInternal(L"SyncActionReadFile: Size < LocalEof Aborting!");
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 36, WPP_6245c1b01f713a032f327efa2846a355_Traceguids);
      }
      FileSize = -1073740768;
LABEL_55:
      ++NumLargeFree;
      VirtualFree(Buffer, 0, 0x8000u);
      v6 = WPP_GLOBAL_Control;
      goto LABEL_56;
    }
    if ( v23.QuadPart > v9.QuadPart )
      v9.QuadPart -= v9.QuadPart % 0x10000;
    while ( 1 )
    {
      if ( v9.QuadPart >= v11.QuadPart )
        goto LABEL_55;
      if ( Length > v11.QuadPart - v9.QuadPart )
        Length = v11.LowPart - v9.LowPart;
      QueryPerformanceCounter(&v26);
      ByteOffset.QuadPart = 0;
      v29 = 0;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
      {
        LODWORD(IoStatusBlock) = Length;
        SyncTraceOutputInternal(
          L"SyncReadFileAtPos: Handle: 0x%p FilePos: %I64d Buffer: 0x%p BytesToRead: %d",
          a2,
          v9.QuadPart,
          Buffer,
          IoStatusBlock);
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_qqqD)(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          76,
          WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids,
          a2,
          (LARGE_INTEGER)v9.QuadPart,
          Buffer,
          Length);
      }
      ByteOffset = v9;
      Status = NtReadFile(a2, 0, 0, 0, &v29, Buffer, Length, &ByteOffset, 0);
      if ( Status == 259 )
      {
        Status = 258;
        if ( !WaitForSingleObject(a2, 0x3E8u) )
          Status = v29.Status;
      }
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
      {
        SyncTraceOutputInternal(L"SyncReadFileAtPos: 0x%x", Status);
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 77, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, Status);
      }
      QueryPerformanceCounter(&v25);
      FileSize = 0;
      if ( Status != -1073741807 )
        FileSize = Status;
      if ( FileSize )
      {
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          SyncTraceOutputInternal(L"SyncActionReadFile: SyncReadFileAtPos failed with %x", FileSize);
          v10 = 37;
          goto LABEL_19;
        }
        goto LABEL_55;
      }
      v9.QuadPart += Length;
      if ( g_pPerfCtrSetInst_OfflineFilesCounters )
        _InterlockedAdd64((volatile signed __int64 *)g_pPerfCtrSetInst_OfflineFilesCounters + 5, Length);
      PerformanceFrequency = SyncActionGetPerformanceFrequency();
      v14 = g_pPerfCtrSetInst_OfflineFilesCounters;
      if ( g_pPerfCtrSetInst_OfflineFilesCounters )
      {
        _InterlockedAdd(
          (volatile signed __int32 *)g_pPerfCtrSetInst_OfflineFilesCounters + 21,
          (v25.QuadPart - v26.QuadPart) / (PerformanceFrequency / 1000));
        _InterlockedAdd64((volatile signed __int64 *)v14 + 13, 1000LL * Length);
      }
      ByteOffset.QuadPart = 0;
      if ( QueryPerformanceCounter(&ByteOffset) )
      {
        v15 = ByteOffset.QuadPart - PerformanceCount.QuadPart;
        if ( v15 / (SyncActionGetPerformanceFrequency() / 1000) < 1000 )
        {
          FileSize = 0;
          goto LABEL_61;
        }
        PerformanceCount = ByteOffset;
      }
      FileSize = SyncActionQueueAborted(*(_QWORD *)(*(_QWORD *)a1 + 24LL), v21);
      if ( !FileSize && v21[0] )
        goto LABEL_54;
      v16 = *(__int64 (__fastcall **)(__int128 *, __int64))(a1 + 80);
      if ( v16 )
      {
        v17 = *(_QWORD *)(a1 + 96);
        *(_QWORD *)&v27 = *(_QWORD *)(a1 + 16);
        *((_QWORD *)&v27 + 1) = *(_QWORD *)(a1 + 8);
        LODWORD(v28) = *(_DWORD *)(a1 + 240);
        *((LARGE_INTEGER *)&v28 + 1) = v9;
        v18 = v16(&v27, v17);
        if ( v18 == 2 )
        {
          SyncActionQueueAbort(*(_QWORD *)(*(_QWORD *)a1 + 24LL));
LABEL_54:
          FileSize = -1073741248;
          goto LABEL_55;
        }
        if ( v18 == 1 )
          goto LABEL_54;
      }
LABEL_61:
      v11 = v23;
    }
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    SyncTraceOutputInternal(L"SyncActionReadFile: Failed to allocate %d byte buffer", 0x10000);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 33, WPP_6245c1b01f713a032f327efa2846a355_Traceguids, 0x10000);
    v6 = WPP_GLOBAL_Control;
  }
  FileSize = -1073741670;
LABEL_56:
  if ( v6 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncActionReadFile: 0x%x", FileSize);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 38, WPP_6245c1b01f713a032f327efa2846a355_Traceguids, FileSize);
  }
  return FileSize;
}

```

## disassembly

```asm
0x18001f534  mov     [rsp-8+arg_10], rbx
0x18001f539  push    rbp
0x18001f53a  push    rsi
0x18001f53b  push    rdi
0x18001f53c  push    r12
0x18001f53e  push    r13
0x18001f540  push    r14
0x18001f542  push    r15
0x18001f544  lea     rbp, [rsp-27h]
0x18001f549  sub     rsp, 0F0h
0x18001f550  mov     rax, cs:__security_cookie
0x18001f557  xor     rax, rsp
0x18001f55a  mov     [rbp+57h+var_38], rax
0x18001f55e  xor     r14d, r14d
0x18001f561  mov     [rbp+57h+var_D0], 1
0x18001f565  xorps   xmm0, xmm0
0x18001f568  mov     [rbp+57h+var_C0], r14
0x18001f56c  xor     eax, eax
0x18001f56e  mov     [rbp+57h+var_CF], r14b
0x18001f572  mov     [rbp+57h+var_40], rax
0x18001f576  mov     r15, rdx
0x18001f579  mov     r12, rcx
0x18001f57c  mov     qword ptr [rbp+57h+PerformanceCount], r14
0x18001f580  movups  [rbp+57h+var_70], xmm0
0x18001f584  mov     qword ptr [rbp+57h+var_A8], r14
0x18001f588  movups  [rbp+57h+var_60], xmm0
0x18001f58c  mov     qword ptr [rbp+57h+var_B0], r14
0x18001f590  movups  [rbp+57h+var_50], xmm0
0x18001f594  movups  [rbp+57h+var_A0], xmm0
0x18001f598  movups  [rbp+57h+var_90], xmm0
0x18001f59c  mov     rax, cs:WPP_GLOBAL_Control
0x18001f5a3  lea     rdi, WPP_GLOBAL_Control
0x18001f5aa  cmp     rax, rdi
0x18001f5ad  jz      short loc_18001F5DF
0x18001f5af  test    byte ptr [rax+6Ch], 4
0x18001f5b3  jz      short loc_18001F5DF
0x18001f5b5  lea     rcx, aSyncactionread_0; "SyncActionReadFile: SourceHandle: 0x%p"
0x18001f5bc  call    SyncTraceOutputInternal
0x18001f5c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f5c8  lea     edx, [r14+1Fh]
0x18001f5cc  mov     r9, r15
0x18001f5cf  lea     r8, WPP_6245c1b01f713a032f327efa2846a355_Traceguids
0x18001f5d6  mov     rcx, [rcx+60h]
0x18001f5da  call    WPP_SF_q
0x18001f5df  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x18001f5e3  call    cs:__imp_QueryPerformanceCounter
0x18001f5e9  lea     rdx, [rbp+57h+var_D0]
0x18001f5ed  mov     rcx, r15; FileHandle
0x18001f5f0  call    SyncWillFillSucceed
0x18001f5f5  test    eax, eax
0x18001f5f7  js      short loc_18001F653
0x18001f5f9  cmp     [rbp+57h+var_D0], r14b
0x18001f5fd  jnz     short loc_18001F653
0x18001f5ff  mov     ebx, 0C0000043h
0x18001f604  mov     rax, cs:WPP_GLOBAL_Control
0x18001f60b  cmp     rax, rdi
0x18001f60e  jz      loc_18001FAB9
0x18001f614  test    byte ptr [rax+6Ch], 1
0x18001f618  jz      loc_18001FA81
0x18001f61e  mov     edx, ebx
0x18001f620  lea     rcx, aSyncactionread_3; "SyncActionReadFile: Bailing out with 0x"...
0x18001f627  call    SyncTraceOutputInternal
0x18001f62c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f633  lea     r8, WPP_6245c1b01f713a032f327efa2846a355_Traceguids
0x18001f63a  mov     edx, 20h ; ' '
0x18001f63f  mov     r9d, 0C0000043h
0x18001f645  mov     rcx, [rcx+60h]
0x18001f649  call    WPP_SF_d
0x18001f64e  jmp     loc_18001FA7A
0x18001f653  mov     esi, 10000h
0x18001f658  mov     ecx, esi
0x18001f65a  call    SyncLargeAlloc
0x18001f65f  mov     r13, rax
0x18001f662  test    rax, rax
0x18001f665  jnz     short loc_18001F6B6
0x18001f667  mov     rax, cs:WPP_GLOBAL_Control
0x18001f66e  cmp     rax, rdi
0x18001f671  jz      short loc_18001F6AC
0x18001f673  test    byte ptr [rax+6Ch], 1
0x18001f677  jz      short loc_18001F6AC
0x18001f679  mov     edx, esi
0x18001f67b  lea     rcx, aSyncactionread_6; "SyncActionReadFile: Failed to allocate "...
0x18001f682  call    SyncTraceOutputInternal
0x18001f687  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f68e  lea     edx, [r13+21h]
0x18001f692  mov     r9d, esi
0x18001f695  lea     r8, WPP_6245c1b01f713a032f327efa2846a355_Traceguids
0x18001f69c  mov     rcx, [rcx+60h]
0x18001f6a0  call    WPP_SF_d
0x18001f6a5  mov     rax, cs:WPP_GLOBAL_Control
0x18001f6ac  mov     ebx, 0C000009Ah
0x18001f6b1  jmp     loc_18001FA81
0x18001f6b6  xor     r8d, r8d
0x18001f6b9  lea     rdx, [rbp+57h+var_70]
0x18001f6bd  mov     rcx, r15; FileHandle
0x18001f6c0  call    SyncQueryInformationLocal
0x18001f6c5  mov     ebx, eax
0x18001f6c7  test    eax, eax
0x18001f6c9  jz      short loc_18001F70F
0x18001f6cb  mov     rax, cs:WPP_GLOBAL_Control
0x18001f6d2  cmp     rax, rdi
0x18001f6d5  jz      short loc_18001F70A
0x18001f6d7  test    byte ptr [rax+6Ch], 1
0x18001f6db  jz      short loc_18001F70A
0x18001f6dd  mov     edx, ebx
0x18001f6df  lea     rcx, aSyncactionread_2; "SyncActionReadFile: SyncQueryInformatio"...
0x18001f6e6  call    SyncTraceOutputInternal
0x18001f6eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f6f2  lea     r8, WPP_6245c1b01f713a032f327efa2846a355_Traceguids
0x18001f6f9  mov     edx, 22h ; '"'
0x18001f6fe  mov     r9d, ebx
0x18001f701  mov     rcx, [rcx+60h]
0x18001f705  call    WPP_SF_d
0x18001f70a  mov     rdi, r14
0x18001f70d  jmp     short loc_18001F713
0x18001f70f  mov     rdi, qword ptr [rbp+57h+var_50+8]
0x18001f713  lea     rdx, [rbp+57h+var_C0]
0x18001f717  mov     rcx, r15; hHandle
0x18001f71a  call    SyncGetFileSize
0x18001f71f  mov     ebx, eax
0x18001f721  test    eax, eax
0x18001f723  jz      short loc_18001F778
0x18001f725  mov     rax, cs:WPP_GLOBAL_Control
0x18001f72c  lea     rdi, WPP_GLOBAL_Control
0x18001f733  cmp     rax, rdi
0x18001f736  jz      loc_18001FA62
0x18001f73c  test    byte ptr [rax+6Ch], 1
0x18001f740  jz      loc_18001FA62
0x18001f746  mov     edx, ebx
0x18001f748  lea     rcx, aSyncactionread; "SyncActionReadFile: SyncGetFileSize fai"...
0x18001f74f  call    SyncTraceOutputInternal
0x18001f754  mov     edx, 23h ; '#'
0x18001f759  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f760  lea     r8, WPP_6245c1b01f713a032f327efa2846a355_Traceguids
0x18001f767  mov     r9d, ebx
0x18001f76a  mov     rcx, [rcx+60h]
0x18001f76e  call    WPP_SF_d
0x18001f773  jmp     loc_18001FA62
0x18001f778  mov     r8, [rbp+57h+var_C0]
0x18001f77c  cmp     r8, rdi
0x18001f77f  jge     short loc_18001F7CC
0x18001f781  mov     rax, cs:WPP_GLOBAL_Control
0x18001f788  lea     rdi, WPP_GLOBAL_Control
0x18001f78f  cmp     rax, rdi
0x18001f792  jz      short loc_18001F7C2
0x18001f794  test    byte ptr [rax+6Ch], 1
0x18001f798  jz      short loc_18001F7C2
0x18001f79a  lea     rcx, aSyncactionread_4; "SyncActionReadFile: Size < LocalEof Abo"...
0x18001f7a1  call    SyncTraceOutputInternal
0x18001f7a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f7ad  lea     r8, WPP_6245c1b01f713a032f327efa2846a355_Traceguids
0x18001f7b4  mov     edx, 24h ; '$'
0x18001f7b9  mov     rcx, [rcx+60h]
0x18001f7bd  call    WPP_SF_
0x18001f7c2  mov     ebx, 0C0000420h
0x18001f7c7  jmp     loc_18001FA62
0x18001f7cc  jle     short loc_18001F7D9
0x18001f7ce  mov     rax, rdi
0x18001f7d1  cqo
0x18001f7d3  idiv    rsi
0x18001f7d6  sub     rdi, rdx
0x18001f7d9  cmp     rdi, r8
0x18001f7dc  jge     loc_18001FA5B
0x18001f7e2  mov     rcx, r8
0x18001f7e5  mov     eax, esi
0x18001f7e7  sub     rcx, rdi
0x18001f7ea  cmp     rax, rcx
0x18001f7ed  jle     short loc_18001F7F5
0x18001f7ef  sub     r8d, edi
0x18001f7f2  mov     esi, r8d
0x18001f7f5  lea     rcx, [rbp+57h+var_A8]; lpPerformanceCount
0x18001f7f9  call    cs:__imp_QueryPerformanceCounter
0x18001f7ff  xorps   xmm0, xmm0
0x18001f802  mov     qword ptr [rbp+57h+var_C8], r14
0x18001f806  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x18001f80a  mov     rax, cs:WPP_GLOBAL_Control
0x18001f811  lea     rbx, WPP_GLOBAL_Control
0x18001f818  cmp     rax, rbx
0x18001f81b  jz      short loc_18001F869
0x18001f81d  test    byte ptr [rax+6Ch], 4
0x18001f821  jz      short loc_18001F869
0x18001f823  mov     r9, r13
0x18001f826  mov     dword ptr [rsp+120h+IoStatusBlock], esi
0x18001f82a  mov     r8, rdi
0x18001f82d  lea     rcx, aSyncreadfileat; "SyncReadFileAtPos: Handle: 0x%p FilePos"...
0x18001f834  mov     rdx, r15
0x18001f837  call    SyncTraceOutputInternal
0x18001f83c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f843  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x18001f84a  mov     [rsp+120h+Length], esi
0x18001f84e  mov     edx, 4Ch ; 'L'
0x18001f853  mov     [rsp+120h+Buffer], r13
0x18001f858  mov     r9, r15
0x18001f85b  mov     [rsp+120h+IoStatusBlock], rdi
0x18001f860  mov     rcx, [rcx+60h]
0x18001f864  call    WPP_SF_qqqD
0x18001f869  mov     [rsp+120h+Key], r14; Key
0x18001f86e  lea     rax, [rbp+57h+var_C8]
0x18001f872  mov     [rsp+120h+ByteOffset], rax; ByteOffset
0x18001f877  xor     r9d, r9d; ApcContext
0x18001f87a  mov     [rsp+120h+Length], esi; Length
0x18001f87e  lea     rax, [rbp+57h+var_80]
0x18001f882  mov     [rsp+120h+Buffer], r13; Buffer
0x18001f887  xor     r8d, r8d; ApcRoutine
0x18001f88a  xor     edx, edx; Event
0x18001f88c  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x18001f891  mov     rcx, r15; FileHandle
0x18001f894  mov     qword ptr [rbp+57h+var_C8], rdi
0x18001f898  call    cs:__imp_NtReadFile
0x18001f89e  mov     r14d, eax
0x18001f8a1  cmp     eax, 103h
0x18001f8a6  jnz     short loc_18001F8C3
0x18001f8a8  mov     edx, 3E8h; dwMilliseconds
0x18001f8ad  mov     rcx, r15; hHandle
0x18001f8b0  call    cs:__imp_WaitForSingleObject
0x18001f8b6  test    eax, eax
0x18001f8b8  mov     r14d, 102h
0x18001f8be  cmovz   r14d, dword ptr [rbp+57h+var_80]
0x18001f8c3  mov     rax, cs:WPP_GLOBAL_Control
0x18001f8ca  cmp     rax, rbx
0x18001f8cd  jz      short loc_18001F903
0x18001f8cf  test    byte ptr [rax+6Ch], 8
0x18001f8d3  jz      short loc_18001F903
0x18001f8d5  mov     edx, r14d
0x18001f8d8  lea     rcx, aSyncreadfileat_0; "SyncReadFileAtPos: 0x%x"
0x18001f8df  call    SyncTraceOutputInternal
0x18001f8e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f8eb  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x18001f8f2  mov     edx, 4Dh ; 'M'
0x18001f8f7  mov     r9d, r14d
0x18001f8fa  mov     rcx, [rcx+60h]
0x18001f8fe  call    WPP_SF_d
0x18001f903  lea     rcx, [rbp+57h+var_B0]; lpPerformanceCount
0x18001f907  call    cs:__imp_QueryPerformanceCounter
0x18001f90d  xor     ebx, ebx
0x18001f90f  cmp     r14d, 0C0000011h
0x18001f916  cmovnz  ebx, r14d
0x18001f91a  xor     r14d, r14d
0x18001f91d  test    ebx, ebx
0x18001f91f  jnz     loc_18001FB00
0x18001f925  mov     rax, cs:?g_pPerfCtrSetInst_OfflineFilesCounters@@3PEAVCPerfCounterSetInstance_OfflineFilesCounters@@EA; CPerfCounterSetInstance_OfflineFilesCounters * g_pPerfCtrSetInst_OfflineFilesCounters
0x18001f92c  mov     ebx, esi
0x18001f92e  add     rdi, rbx
0x18001f931  test    rax, rax
0x18001f934  jz      short loc_18001F93B
0x18001f936  lock add [rax+28h], rbx
0x18001f93b  call    SyncActionGetPerformanceFrequency
0x18001f940  mov     r10, cs:?g_pPerfCtrSetInst_OfflineFilesCounters@@3PEAVCPerfCounterSetInstance_OfflineFilesCounters@@EA; CPerfCounterSetInstance_OfflineFilesCounters * g_pPerfCtrSetInst_OfflineFilesCounters
0x18001f947  mov     rcx, rax
0x18001f94a  test    r10, r10
0x18001f94d  jz      short loc_18001F98E
0x18001f94f  mov     r9, qword ptr [rbp+57h+var_B0]
0x18001f953  mov     rax, 20C49BA5E353F7CFh
0x18001f95d  sub     r9, qword ptr [rbp+57h+var_A8]
0x18001f961  imul    rcx
0x18001f964  mov     rax, r9
0x18001f967  mov     r8, rdx
0x18001f96a  cqo
0x18001f96c  sar     r8, 7
0x18001f970  mov     rcx, r8
0x18001f973  shr     rcx, 3Fh
0x18001f977  add     r8, rcx
0x18001f97a  idiv    r8
0x18001f97d  lock add [r10+54h], eax
0x18001f982  imul    rax, rbx, 3E8h
0x18001f989  lock add [r10+68h], rax
0x18001f98e  lea     rcx, [rbp+57h+var_C8]; lpPerformanceCount
0x18001f992  mov     qword ptr [rbp+57h+var_C8], r14
0x18001f996  call    cs:__imp_QueryPerformanceCounter
0x18001f99c  test    eax, eax
0x18001f99e  jz      short loc_18001F9EA
0x18001f9a0  mov     rbx, qword ptr [rbp+57h+var_C8]
0x18001f9a4  sub     rbx, qword ptr [rbp+57h+PerformanceCount]
0x18001f9a8  call    SyncActionGetPerformanceFrequency
0x18001f9ad  mov     rcx, rax
0x18001f9b0  mov     rax, 20C49BA5E353F7CFh
0x18001f9ba  imul    rcx
0x18001f9bd  mov     rax, rbx
0x18001f9c0  mov     r8, rdx
0x18001f9c3  cqo
0x18001f9c5  sar     r8, 7
0x18001f9c9  mov     rcx, r8
0x18001f9cc  shr     rcx, 3Fh
0x18001f9d0  add     r8, rcx
0x18001f9d3  idiv    r8
0x18001f9d6  cmp     rax, 3E8h
0x18001f9dc  jl      loc_18001FAE2
0x18001f9e2  mov     rax, qword ptr [rbp+57h+var_C8]
0x18001f9e6  mov     qword ptr [rbp+57h+PerformanceCount], rax
0x18001f9ea  mov     rcx, [r12]
0x18001f9ee  lea     rdx, [rbp+57h+var_CF]
0x18001f9f2  mov     rcx, [rcx+18h]
0x18001f9f6  call    SyncActionQueueAborted
0x18001f9fb  mov     ebx, eax
0x18001f9fd  test    eax, eax
0x18001f9ff  jnz     short loc_18001FA07
0x18001fa01  cmp     [rbp+57h+var_CF], r14b
0x18001fa05  jnz     short loc_18001FA56
0x18001fa07  mov     rax, [r12+50h]
0x18001fa0c  test    rax, rax
  ... truncated ...
```
