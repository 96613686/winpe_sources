# VIDMM_PROCESS_HEAP::Rotate(VIDMM_GLOBAL *,VIDMM_HEAP_ALLOC *,_MM_ROTATE_DIRECTION,_MDL *,unsigned __int64,unsigned __int64,long (*)(_MDL *,_MDL *,void *),void *,VIDMM_ROTATE_FLAGS)

- ea: `0x1400b1a80`
- end: `0x1400b1f8b`
- name: `?Rotate@VIDMM_PROCESS_HEAP@@UEAAJPEAVVIDMM_GLOBAL@@PEAUVIDMM_HEAP_ALLOC@@W4_MM_ROTATE_DIRECTION@@PEAU_MDL@@_K4P6AJ33PEAX@Z5TVIDMM_ROTATE_FLAGS@@@Z`
- size: `1291`
- prototype: `__int64 __fastcall(__int64, __int64, ULONG_PTR, int, PMDL NewMdl, __int64, SIZE_T Size, PMM_ROTATE_COPY_CALLBACK_FUNCTION, PVOID, char)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1400045ec`
- `0x140012e28`
- `0x140030fa0`
- `0x14003142c`
- `0x14004a2a8`
- `0x140058760`
- `0x1400b1a80`
- `0x140111174`

## import_xrefs

- `ntoskrnl!MmSecureVirtualMemory` at `0x1400b1be6`
- `ntoskrnl!MmSecureVirtualMemory` at `0x1400b1be6`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b1d31`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b1e32`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b1e40`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b1d31`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b1e32`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b1e40`
- `ntoskrnl!MmRotatePhysicalView` at `0x1400b1cd6`
- `ntoskrnl!MmRotatePhysicalView` at `0x1400b1d9c`
- `ntoskrnl!MmRotatePhysicalView` at `0x1400b1e1a`
- `ntoskrnl!MmRotatePhysicalView` at `0x1400b1e8d`
- `ntoskrnl!MmRotatePhysicalView` at `0x1400b1cd6`
- `ntoskrnl!MmRotatePhysicalView` at `0x1400b1d9c`
- `ntoskrnl!MmRotatePhysicalView` at `0x1400b1e1a`
- `ntoskrnl!MmRotatePhysicalView` at `0x1400b1e8d`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b1b02`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b1eb8`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b1ef6`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b1b02`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b1eb8`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b1ef6`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b1b5a`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b1b5a`
- `watchdog!WdLogSingleEntry5` at `0x1400b1b38`
- `watchdog!WdLogSingleEntry5` at `0x1400b1f2a`
- `watchdog!WdLogSingleEntry5` at `0x1400b1b38`
- `watchdog!WdLogSingleEntry5` at `0x1400b1f2a`
- `watchdog!WdLogSingleEntry0` at `0x1400b1c05`
- `watchdog!WdLogSingleEntry0` at `0x1400b1cf0`
- `watchdog!WdLogSingleEntry0` at `0x1400b1dc3`
- `watchdog!WdLogSingleEntry0` at `0x1400b1c05`
- `watchdog!WdLogSingleEntry0` at `0x1400b1cf0`
- `watchdog!WdLogSingleEntry0` at `0x1400b1dc3`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400b1b13`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400b1f02`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b1b4e`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 __fastcall VIDMM_PROCESS_HEAP::Rotate(
        __int64 a1,
        __int64 a2,
        ULONG_PTR a3,
        int a4,
        PMDL NewMdl,
        __int64 a6,
        SIZE_T Size,
        PMM_ROTATE_COPY_CALLBACK_FUNCTION a8,
        PVOID a9,
        char a10)
{
  __int64 v10; // rdi
  ULONG_PTR v11; // rsi
  __int64 v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  char *v19; // r14
  SIZE_T v20; // r13
  HANDLE v21; // rax
  int v22; // ecx
  int v23; // r8d
  __int64 v24; // rcx
  __int64 v25; // r8
  NTSTATUS (__stdcall *CopyFunction)(PMDL, PMDL, PVOID); // rsi
  ULONG_PTR v28; // r12
  PVOID Context; // r13
  NTSTATUS v30; // ebx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // rcx
  int v34; // r12d
  NTSTATUS v35; // eax
  __int64 v36; // rcx
  __int64 v37; // r8
  PVOID v38; // rsi
  NTSTATUS (__stdcall *v39)(PMDL, PMDL, PVOID); // r13
  struct _EPROCESS *CurrentProcess; // rax
  int v41; // edi
  __int64 v42; // rcx
  __int64 v43; // r8
  ULONG_PTR NumberOfBytes; // [rsp+50h] [rbp-30h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+58h] [rbp-28h] BYREF
  unsigned int v46; // [rsp+60h] [rbp-20h] BYREF
  __int64 v47; // [rsp+68h] [rbp-18h]
  char v48; // [rsp+70h] [rbp-10h]
  int v49; // [rsp+C0h] [rbp+40h]
  ULONG_PTR v50; // [rsp+D0h] [rbp+50h] BYREF

  v50 = a3;
  v10 = a4;
  v11 = a3;
  v46 = -1;
  v47 = 0;
  if ( (qword_140086010 & 2) != 0 )
  {
    v48 = 1;
    v46 = 8005;
    if ( (byte_140086202 & 1) != 0 )
      McTemplateK0q_EtwWriteTransfer(a1, EventProfilerEnter, a3, 8005);
  }
  else
  {
    v48 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v46, 8005);
  v14 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL);
  if ( ((__int64 (*)(void))PsGetCurrentProcess)() != v14 )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 30);
    WdLogGlobalForLineNumber = 222;
  }
  if ( g_IsInternalReleaseOrDbg )
  {
    v17 = WdLogNewEntry5_WdTrace(v16, v15);
    *(_QWORD *)(v17 + 24) = v11;
    *(_QWORD *)(v17 + 32) = v10;
    WdLogGlobalForLineNumber = 1512;
  }
  v18 = *(_QWORD *)(v11 + 8);
  if ( (*(_DWORD *)v11 & 1) != 0 )
  {
    if ( (*(_DWORD *)(v11 + 20) & 0x800000) != 0 )
    {
      v19 = *(char **)(v11 + 8);
      goto LABEL_14;
    }
  }
  else if ( (*(_DWORD *)(v18 + 64) & 1) != 0 )
  {
    v19 = (char *)(*(_QWORD *)(v11 + 16) + *(_QWORD *)(v18 + 32));
LABEL_14:
    v20 = Size;
    if ( !(_DWORD)v10 || (v49 = 0, (_DWORD)v10 == 1) )
    {
      if ( (*(_DWORD *)v11 & 1) == 0 && !*(_QWORD *)(v18 + 56) && !*(_QWORD *)(v11 + 32) )
      {
        v21 = MmSecureVirtualMemory(v19, Size, 4u);
        *(_QWORD *)(v11 + 32) = v21;
        if ( !v21 )
        {
          _InterlockedIncrement(&dword_1400867A8);
          WdLogSingleEntry0(6);
          WdLogGlobalForLineNumber = 1554;
          DxgkLogInternalTriageEvent(
            v22,
            262145,
            v23,
            (unsigned int)L"Couldn't secure the virtual memory range for the allocation.\n",
            1554,
            0,
            0,
            0);
          DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v46);
          if ( v48 )
          {
            if ( (byte_140086202 & 1) != 0 )
              McTemplateK0q_EtwWriteTransfer(v24, EventProfilerExit, v25, v46);
          }
          return 3221225495LL;
        }
      }
      if ( *(_DWORD *)(a2 + 36440) != -1 )
        (*(void (__fastcall **)(_QWORD))(a2 + 36168))(*(_QWORD *)(a2 + 36232));
      v49 = 1;
    }
    if ( (_DWORD)v10 == 2 )
    {
      CopyFunction = a8;
      v28 = v20;
      Context = a9;
      Interval.QuadPart = -10000;
      while ( 1 )
      {
        NumberOfBytes = v28;
        v30 = MmRotatePhysicalView(v19, &NumberOfBytes, 0, MmToRegularMemory, CopyFunction, Context);
        if ( v30 != 1073741849 )
          break;
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 1620;
        if ( (byte_140086201 & 1) != 0 )
          McTemplateK0q_EtwWriteTransfer(v31, EventPerformanceWarning, v32, 12);
        v19 += NumberOfBytes;
        v28 -= NumberOfBytes;
        KeDelayExecutionThread(0, 0, &Interval);
      }
      VIDMM_GLOBAL::SetMemoryRefreshIdle((VIDMM_GLOBAL *)a2);
      v11 = v50;
      v20 = Size;
    }
    else if ( (_DWORD)v10 == 3 )
    {
      v34 = a10 & 1;
      Interval.QuadPart = -10000;
      NumberOfBytes = v20;
      while ( 1 )
      {
        v35 = MmRotatePhysicalView(v19, &NumberOfBytes, 0, MmToRegularMemoryNoCopy, a8, a9);
        v30 = v35;
        if ( !v34 || v35 != 1073741849 )
          break;
        WdLogSingleEntry0(3);
        WdLogGlobalForLineNumber = 1693;
        if ( (byte_140086201 & 1) != 0 )
          McTemplateK0q_EtwWriteTransfer(v36, EventPerformanceWarning, v37, 12);
        v38 = a9;
        v39 = a8;
        while ( MmRotatePhysicalView(v19, &NumberOfBytes, NewMdl, MmToFrameBufferNoCopy, v39, v38) < 0 )
          KeDelayExecutionThread(0, 0, &Interval);
        KeDelayExecutionThread(0, 0, &Interval);
        v11 = v50;
        v20 = Size;
      }
      VIDMM_GLOBAL::SetMemoryRefreshIdle((VIDMM_GLOBAL *)a2);
    }
    else
    {
      v50 = v20;
      v30 = MmRotatePhysicalView(v19, &v50, NewMdl, (MM_ROTATE_DIRECTION)v10, a8, a9);
    }
    if ( v30 < 0 )
    {
      if ( v49 )
        VIDMM_GLOBAL::SetMemoryRefreshIdle((VIDMM_GLOBAL *)a2);
    }
    else
    {
      *(_BYTE *)(v11 + 64) = (unsigned int)v10 <= 1;
    }
    CurrentProcess = (struct _EPROCESS *)PsGetCurrentProcess(v33);
    VIDMM_GLOBAL::RecordRotation(CurrentProcess, v19, v20, NewMdl, (enum _MM_ROTATE_DIRECTION)v10, v30);
    goto LABEL_56;
  }
  v30 = 0;
  if ( (_DWORD)v10 )
  {
    v41 = v10 - 1;
    if ( v41 )
    {
      if ( (unsigned int)(v41 - 1) > 1 )
        goto LABEL_56;
      PsGetCurrentProcess(v18);
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(0, 270, 1);
      WdLogGlobalForLineNumber = 222;
    }
  }
  v30 = -1073741823;
LABEL_56:
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v46);
  if ( v48 && (byte_140086202 & 1) != 0 )
    McTemplateK0q_EtwWriteTransfer(v42, EventProfilerExit, v43, v46);
  return (unsigned int)v30;
}

```

## disassembly

```asm
0x1400b1a80  mov     [rsp-38h+arg_8], rbx
0x1400b1a85  mov     [rsp-38h+arg_10], r8
0x1400b1a8a  push    rbp
0x1400b1a8b  push    rsi
0x1400b1a8c  push    rdi
0x1400b1a8d  push    r12
0x1400b1a8f  push    r13
0x1400b1a91  push    r14
0x1400b1a93  push    r15
0x1400b1a95  mov     rbp, rsp
0x1400b1a98  sub     rsp, 80h
0x1400b1a9f  xor     r12d, r12d
0x1400b1aa2  movsxd  rdi, r9d
0x1400b1aa5  test    byte ptr cs:qword_140086010, 2
0x1400b1aac  mov     rsi, r8
0x1400b1aaf  mov     r15, rdx
0x1400b1ab2  mov     [rbp+var_20], 0FFFFFFFFh
0x1400b1ab9  mov     rbx, rcx
0x1400b1abc  mov     [rbp+var_18], r12
0x1400b1ac0  mov     r14d, 1F45h
0x1400b1ac6  jz      short loc_1400B1AEA
0x1400b1ac8  test    cs:byte_140086202, 1
0x1400b1acf  mov     [rbp+var_10], 1
0x1400b1ad3  mov     [rbp+var_20], r14d
0x1400b1ad7  jz      short loc_1400B1AEE
0x1400b1ad9  mov     r9d, r14d
0x1400b1adc  lea     rdx, EventProfilerEnter
0x1400b1ae3  call    McTemplateK0q_EtwWriteTransfer
0x1400b1ae8  jmp     short loc_1400B1AEE
0x1400b1aea  mov     [rbp+var_10], r12b
0x1400b1aee  mov     edx, r14d
0x1400b1af1  lea     rcx, [rbp+var_20]
0x1400b1af5  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1400b1afa  mov     rax, [rbx+8]
0x1400b1afe  mov     rbx, [rax+10h]
0x1400b1b02  call    cs:__imp_PsGetCurrentProcess
0x1400b1b09  nop     dword ptr [rax+rax+00h]
0x1400b1b0e  cmp     rax, rbx
0x1400b1b11  jz      short loc_1400B1B4E
0x1400b1b13  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400b1b1a  mov     dword ptr [rax], 1
0x1400b1b20  xor     r9d, r9d
0x1400b1b23  mov     [rsp+80h+Context], r12
0x1400b1b28  mov     edx, 10Eh
0x1400b1b2d  mov     [rsp+80h+CopyFunction], r12
0x1400b1b32  xor     ecx, ecx
0x1400b1b34  lea     r8d, [r9+1Eh]
0x1400b1b38  call    cs:__imp_WdLogSingleEntry5
0x1400b1b3f  nop     dword ptr [rax+rax+00h]
0x1400b1b44  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400b1b4e  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400b1b55  cmp     [rax], r12b
0x1400b1b58  jz      short loc_1400B1B78
0x1400b1b5a  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400b1b61  nop     dword ptr [rax+rax+00h]
0x1400b1b66  mov     [rax+18h], rsi
0x1400b1b6a  mov     [rax+20h], rdi
0x1400b1b6e  mov     cs:WdLogGlobalForLineNumber, 5E8h
0x1400b1b78  mov     edx, [rsi]
0x1400b1b7a  mov     r14d, edi
0x1400b1b7d  mov     rcx, [rsi+8]
0x1400b1b81  and     edx, 1
0x1400b1b84  jz      short loc_1400B1B98
0x1400b1b86  test    dword ptr [rsi+14h], 800000h
0x1400b1b8d  jz      loc_1400B1EE0
0x1400b1b93  mov     r14, rcx
0x1400b1b96  jmp     short loc_1400B1BAB
0x1400b1b98  mov     eax, [rcx+40h]
0x1400b1b9b  test    al, 1
0x1400b1b9d  jz      loc_1400B1EE0
0x1400b1ba3  mov     r14, [rcx+20h]
0x1400b1ba7  add     r14, [rsi+10h]
0x1400b1bab  mov     r13, [rbp+Size]
0x1400b1baf  test    edi, edi
0x1400b1bb1  jz      short loc_1400B1BC0
0x1400b1bb3  mov     [rbp+arg_0], r12d
0x1400b1bb7  cmp     edi, 1
0x1400b1bba  jnz     loc_1400B1C99
0x1400b1bc0  test    edx, edx
0x1400b1bc2  jnz     loc_1400B1C73
0x1400b1bc8  cmp     [rcx+38h], r12
0x1400b1bcc  jnz     loc_1400B1C73
0x1400b1bd2  cmp     [rsi+20h], r12
0x1400b1bd6  jnz     loc_1400B1C73
0x1400b1bdc  lea     r8d, [rdx+4]; ProbeMode
0x1400b1be0  mov     rcx, r14; Address
0x1400b1be3  mov     rdx, r13; Size
0x1400b1be6  call    cs:__imp_MmSecureVirtualMemory
0x1400b1bed  nop     dword ptr [rax+rax+00h]
0x1400b1bf2  mov     [rsi+20h], rax
0x1400b1bf6  test    rax, rax
0x1400b1bf9  jnz     short loc_1400B1C73
0x1400b1bfb  lock inc cs:dword_1400867A8
0x1400b1c02  lea     ecx, [rax+6]
0x1400b1c05  call    cs:__imp_WdLogSingleEntry0
0x1400b1c0c  nop     dword ptr [rax+rax+00h]
0x1400b1c11  mov     [rsp+80h+var_48], r12
0x1400b1c16  lea     r9, aCouldnTSecureT; "Couldn't secure the virtual memory rang"...
0x1400b1c1d  mov     eax, 612h
0x1400b1c22  mov     [rsp+80h+var_50], r12
0x1400b1c27  mov     [rsp+80h+Context], r12
0x1400b1c2c  mov     edx, 40001h
0x1400b1c31  mov     cs:WdLogGlobalForLineNumber, eax
0x1400b1c37  mov     [rsp+80h+CopyFunction], rax
0x1400b1c3c  call    DxgkLogInternalTriageEvent
0x1400b1c41  lea     rcx, [rbp+var_20]; this
0x1400b1c45  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1400b1c4a  cmp     [rbp+var_10], r12b
0x1400b1c4e  jz      short loc_1400B1C69
0x1400b1c50  test    cs:byte_140086202, 1
0x1400b1c57  jz      short loc_1400B1C69
0x1400b1c59  mov     r9d, [rbp+var_20]
0x1400b1c5d  lea     rdx, EventProfilerExit
0x1400b1c64  call    McTemplateK0q_EtwWriteTransfer
0x1400b1c69  mov     eax, 0C0000017h
0x1400b1c6e  jmp     loc_1400B1F6F
0x1400b1c73  mov     edx, [r15+8E58h]
0x1400b1c7a  cmp     edx, 0FFFFFFFFh
0x1400b1c7d  jz      short loc_1400B1C92
0x1400b1c7f  mov     rax, [r15+8D48h]
0x1400b1c86  mov     rcx, [r15+8D88h]
0x1400b1c8d  call    _guard_dispatch_icall
0x1400b1c92  mov     [rbp+arg_0], 1
0x1400b1c99  cmp     edi, 2
0x1400b1c9c  jnz     loc_1400B1D57
0x1400b1ca2  mov     rsi, [rbp+arg_38]
0x1400b1ca6  mov     r12, r13
0x1400b1ca9  mov     r13, [rbp+arg_40]
0x1400b1cb0  mov     qword ptr [rbp+Interval], 0FFFFFFFFFFFFD8F0h
0x1400b1cb8  mov     [rsp+80h+Context], r13; Context
0x1400b1cbd  lea     rdx, [rbp+NumberOfBytes]; NumberOfBytes
0x1400b1cc1  mov     r9d, 2; Direction
0x1400b1cc7  mov     [rsp+80h+CopyFunction], rsi; CopyFunction
0x1400b1ccc  xor     r8d, r8d; NewMdl
0x1400b1ccf  mov     [rbp+NumberOfBytes], r12
0x1400b1cd3  mov     rcx, r14; VirtualAddress
0x1400b1cd6  call    cs:__imp_MmRotatePhysicalView
0x1400b1cdd  nop     dword ptr [rax+rax+00h]
0x1400b1ce2  mov     ebx, eax
0x1400b1ce4  cmp     eax, 40000019h
0x1400b1ce9  jnz     short loc_1400B1D42
0x1400b1ceb  mov     ecx, 3
0x1400b1cf0  call    cs:__imp_WdLogSingleEntry0
0x1400b1cf7  nop     dword ptr [rax+rax+00h]
0x1400b1cfc  test    cs:byte_140086201, 1
0x1400b1d03  mov     cs:WdLogGlobalForLineNumber, 654h
0x1400b1d0d  jz      short loc_1400B1D21
0x1400b1d0f  mov     r9d, 0Ch
0x1400b1d15  lea     rdx, EventPerformanceWarning
0x1400b1d1c  call    McTemplateK0q_EtwWriteTransfer
0x1400b1d21  add     r14, [rbp+NumberOfBytes]
0x1400b1d25  lea     r8, [rbp+Interval]; Interval
0x1400b1d29  sub     r12, [rbp+NumberOfBytes]
0x1400b1d2d  xor     edx, edx; Alertable
0x1400b1d2f  xor     ecx, ecx; WaitMode
0x1400b1d31  call    cs:__imp_KeDelayExecutionThread
0x1400b1d38  nop     dword ptr [rax+rax+00h]
0x1400b1d3d  jmp     loc_1400B1CB8
0x1400b1d42  mov     rcx, r15; this
0x1400b1d45  call    ?SetMemoryRefreshIdle@VIDMM_GLOBAL@@QEAAXXZ; VIDMM_GLOBAL::SetMemoryRefreshIdle(void)
0x1400b1d4a  mov     rsi, [rbp+arg_10]
0x1400b1d4e  mov     r13, [rbp+Size]
0x1400b1d52  jmp     loc_1400B1E61
0x1400b1d57  cmp     edi, 3
0x1400b1d5a  jnz     loc_1400B1E66
0x1400b1d60  mov     r12d, [rbp+arg_48]
0x1400b1d67  and     r12d, 1
0x1400b1d6b  mov     qword ptr [rbp+Interval], 0FFFFFFFFFFFFD8F0h
0x1400b1d73  mov     [rbp+NumberOfBytes], r13
0x1400b1d77  mov     rax, [rbp+arg_40]
0x1400b1d7e  lea     rdx, [rbp+NumberOfBytes]; NumberOfBytes
0x1400b1d82  mov     [rsp+80h+Context], rax; Context
0x1400b1d87  mov     r9d, 3; Direction
0x1400b1d8d  mov     rax, [rbp+arg_38]
0x1400b1d91  xor     r8d, r8d; NewMdl
0x1400b1d94  mov     rcx, r14; VirtualAddress
0x1400b1d97  mov     [rsp+80h+CopyFunction], rax; CopyFunction
0x1400b1d9c  call    cs:__imp_MmRotatePhysicalView
0x1400b1da3  nop     dword ptr [rax+rax+00h]
0x1400b1da8  mov     ebx, eax
0x1400b1daa  test    r12d, r12d
0x1400b1dad  jz      loc_1400B1E59
0x1400b1db3  cmp     eax, 40000019h
0x1400b1db8  jnz     loc_1400B1E59
0x1400b1dbe  mov     ecx, 3
0x1400b1dc3  call    cs:__imp_WdLogSingleEntry0
0x1400b1dca  nop     dword ptr [rax+rax+00h]
0x1400b1dcf  test    cs:byte_140086201, 1
0x1400b1dd6  mov     cs:WdLogGlobalForLineNumber, 69Dh
0x1400b1de0  jz      short loc_1400B1DF4
0x1400b1de2  mov     r9d, 0Ch
0x1400b1de8  lea     rdx, EventPerformanceWarning
0x1400b1def  call    McTemplateK0q_EtwWriteTransfer
0x1400b1df4  mov     rsi, [rbp+arg_40]
0x1400b1dfb  mov     r13, [rbp+arg_38]
0x1400b1dff  mov     r8, [rbp+NewMdl]; NewMdl
0x1400b1e03  lea     rdx, [rbp+NumberOfBytes]; NumberOfBytes
0x1400b1e07  mov     [rsp+80h+Context], rsi; Context
0x1400b1e0c  mov     r9d, 1; Direction
0x1400b1e12  mov     rcx, r14; VirtualAddress
0x1400b1e15  mov     [rsp+80h+CopyFunction], r13; CopyFunction
0x1400b1e1a  call    cs:__imp_MmRotatePhysicalView
0x1400b1e21  nop     dword ptr [rax+rax+00h]
0x1400b1e26  xor     edx, edx; Alertable
0x1400b1e28  lea     r8, [rbp+Interval]; Interval
0x1400b1e2c  xor     ecx, ecx; WaitMode
0x1400b1e2e  test    eax, eax
0x1400b1e30  jns     short loc_1400B1E40
0x1400b1e32  call    cs:__imp_KeDelayExecutionThread
0x1400b1e39  nop     dword ptr [rax+rax+00h]
0x1400b1e3e  jmp     short loc_1400B1DFF
0x1400b1e40  call    cs:__imp_KeDelayExecutionThread
0x1400b1e47  nop     dword ptr [rax+rax+00h]
0x1400b1e4c  mov     rsi, [rbp+arg_10]
0x1400b1e50  mov     r13, [rbp+Size]
0x1400b1e54  jmp     loc_1400B1D77
0x1400b1e59  mov     rcx, r15; this
0x1400b1e5c  call    ?SetMemoryRefreshIdle@VIDMM_GLOBAL@@QEAAXXZ; VIDMM_GLOBAL::SetMemoryRefreshIdle(void)
0x1400b1e61  xor     r12d, r12d
0x1400b1e64  jmp     short loc_1400B1E9B
0x1400b1e66  mov     rax, [rbp+arg_40]
0x1400b1e6d  lea     rdx, [rbp+arg_10]; NumberOfBytes
0x1400b1e71  mov     r8, [rbp+NewMdl]; NewMdl
0x1400b1e75  mov     r9d, edi; Direction
0x1400b1e78  mov     [rsp+80h+Context], rax; Context
0x1400b1e7d  mov     rcx, r14; VirtualAddress
0x1400b1e80  mov     rax, [rbp+arg_38]
0x1400b1e84  mov     [rsp+80h+CopyFunction], rax; CopyFunction
0x1400b1e89  mov     [rbp+arg_10], r13
0x1400b1e8d  call    cs:__imp_MmRotatePhysicalView
0x1400b1e94  nop     dword ptr [rax+rax+00h]
0x1400b1e99  mov     ebx, eax
0x1400b1e9b  test    ebx, ebx
0x1400b1e9d  js      short loc_1400B1EAA
0x1400b1e9f  cmp     edi, 1
0x1400b1ea2  setbe   al
0x1400b1ea5  mov     [rsi+40h], al
0x1400b1ea8  jmp     short loc_1400B1EB8
0x1400b1eaa  cmp     [rbp+arg_0], r12d
0x1400b1eae  jz      short loc_1400B1EB8
0x1400b1eb0  mov     rcx, r15; this
0x1400b1eb3  call    ?SetMemoryRefreshIdle@VIDMM_GLOBAL@@QEAAXXZ; VIDMM_GLOBAL::SetMemoryRefreshIdle(void)
0x1400b1eb8  call    cs:__imp_PsGetCurrentProcess
0x1400b1ebf  nop     dword ptr [rax+rax+00h]
0x1400b1ec4  mov     r9, [rbp+NewMdl]; struct _MDL *
0x1400b1ec8  mov     r8, r13; unsigned __int64
0x1400b1ecb  mov     rcx, rax; struct _EPROCESS *
0x1400b1ece  mov     dword ptr [rsp+80h+Context], ebx; int
0x1400b1ed2  mov     rdx, r14; void *
0x1400b1ed5  mov     dword ptr [rsp+80h+CopyFunction], edi; enum _MM_ROTATE_DIRECTION
0x1400b1ed9  call    ?RecordRotation@VIDMM_GLOBAL@@SAXPEAU_EPROCESS@@PEAX_KPEAU_MDL@@W4_MM_ROTATE_DIRECTION@@J@Z; VIDMM_GLOBAL::RecordRotation(_EPROCESS *,void *,unsigned __int64,_MDL *,_MM_ROTATE_DIRECTION,long)
0x1400b1ede  jmp     short loc_1400B1F45
0x1400b1ee0  mov     ebx, r12d
0x1400b1ee3  test    edi, edi
0x1400b1ee5  jz      short loc_1400B1F40
0x1400b1ee7  sub     edi, 1
0x1400b1eea  jz      short loc_1400B1F40
0x1400b1eec  sub     edi, 1
0x1400b1eef  jz      short loc_1400B1EF6
0x1400b1ef1  cmp     edi, 1
0x1400b1ef4  jnz     short loc_1400B1F45
0x1400b1ef6  call    cs:__imp_PsGetCurrentProcess
0x1400b1efd  nop     dword ptr [rax+rax+00h]
0x1400b1f02  mov     rcx, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400b1f09  mov     dword ptr [rcx], 1
0x1400b1f0f  movsxd  rcx, r14d
0x1400b1f12  mov     r9, rax
0x1400b1f15  mov     [rsp+80h+Context], rcx
0x1400b1f1a  mov     edx, 10Eh
0x1400b1f1f  xor     ecx, ecx
0x1400b1f21  mov     [rsp+80h+CopyFunction], rsi
0x1400b1f26  lea     r8d, [rcx+1]
0x1400b1f2a  call    cs:__imp_WdLogSingleEntry5
0x1400b1f31  nop     dword ptr [rax+rax+00h]
0x1400b1f36  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400b1f40  mov     ebx, 0C0000001h
0x1400b1f45  lea     rcx, [rbp+var_20]; this
0x1400b1f49  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1400b1f4e  cmp     [rbp+var_10], r12b
0x1400b1f52  jz      short loc_1400B1F6D
0x1400b1f54  test    cs:byte_140086202, 1
0x1400b1f5b  jz      short loc_1400B1F6D
0x1400b1f5d  mov     r9d, [rbp+var_20]
0x1400b1f61  lea     rdx, EventProfilerExit
0x1400b1f68  call    McTemplateK0q_EtwWriteTransfer
0x1400b1f6d  mov     eax, ebx
0x1400b1f6f  mov     rbx, [rsp+80h+arg_8]
0x1400b1f77  add     rsp, 80h
0x1400b1f7e  pop     r15
0x1400b1f80  pop     r14
0x1400b1f82  pop     r13
0x1400b1f84  pop     r12
0x1400b1f86  pop     rdi
0x1400b1f87  pop     rsi
0x1400b1f88  pop     rbp
0x1400b1f89  retn
```
