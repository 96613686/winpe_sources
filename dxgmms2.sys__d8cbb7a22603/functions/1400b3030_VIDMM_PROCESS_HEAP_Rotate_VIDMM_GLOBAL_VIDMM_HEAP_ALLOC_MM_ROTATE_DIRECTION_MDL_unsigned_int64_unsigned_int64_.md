# VIDMM_PROCESS_HEAP::Rotate(VIDMM_GLOBAL *,VIDMM_HEAP_ALLOC *,_MM_ROTATE_DIRECTION,_MDL *,unsigned __int64,unsigned __int64,long (*)(_MDL *,_MDL *,void *),void *,VIDMM_ROTATE_FLAGS)

- ea: `0x1400b3030`
- end: `0x1400b353b`
- name: `?Rotate@VIDMM_PROCESS_HEAP@@UEAAJPEAVVIDMM_GLOBAL@@PEAUVIDMM_HEAP_ALLOC@@W4_MM_ROTATE_DIRECTION@@PEAU_MDL@@_K4P6AJ33PEAX@Z5TVIDMM_ROTATE_FLAGS@@@Z`
- size: `1291`
- prototype: `int __high(struct VIDMM_GLOBAL *, struct VIDMM_HEAP_ALLOC *, enum _MM_ROTATE_DIRECTION, struct _MDL *, unsigned __int64, unsigned __int64, int (__high *)(struct _MDL *, struct _MDL *, void *), void *, union VIDMM_ROTATE_FLAGS)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x140004268`
- `0x1400128c8`
- `0x14002eb80`
- `0x14002f2a8`
- `0x14004a9b8`
- `0x140059030`
- `0x1400b3030`
- `0x140113db8`

## import_xrefs

- `ntoskrnl!MmSecureVirtualMemory` at `0x1400b3196`
- `ntoskrnl!MmSecureVirtualMemory` at `0x1400b3196`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b32e1`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b33e2`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b33f0`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b32e1`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b33e2`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400b33f0`
- `ntoskrnl!MmRotatePhysicalView` at `0x1400b3286`
- `ntoskrnl!MmRotatePhysicalView` at `0x1400b334c`
- `ntoskrnl!MmRotatePhysicalView` at `0x1400b33ca`
- `ntoskrnl!MmRotatePhysicalView` at `0x1400b343d`
- `ntoskrnl!MmRotatePhysicalView` at `0x1400b3286`
- `ntoskrnl!MmRotatePhysicalView` at `0x1400b334c`
- `ntoskrnl!MmRotatePhysicalView` at `0x1400b33ca`
- `ntoskrnl!MmRotatePhysicalView` at `0x1400b343d`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b30b2`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b3468`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b34a6`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b30b2`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b3468`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b34a6`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b310a`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400b310a`
- `watchdog!WdLogSingleEntry5` at `0x1400b30e8`
- `watchdog!WdLogSingleEntry5` at `0x1400b34da`
- `watchdog!WdLogSingleEntry5` at `0x1400b30e8`
- `watchdog!WdLogSingleEntry5` at `0x1400b34da`
- `watchdog!WdLogSingleEntry0` at `0x1400b31b5`
- `watchdog!WdLogSingleEntry0` at `0x1400b32a0`
- `watchdog!WdLogSingleEntry0` at `0x1400b3373`
- `watchdog!WdLogSingleEntry0` at `0x1400b31b5`
- `watchdog!WdLogSingleEntry0` at `0x1400b32a0`
- `watchdog!WdLogSingleEntry0` at `0x1400b3373`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400b30c3`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400b34b2`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400b30fe`

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
  __int64 v15; // rcx
  __int64 v16; // rax
  int v17; // r14d
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
  __int64 v42; // rax
  __int64 v43; // rcx
  __int64 v44; // r8
  ULONG_PTR NumberOfBytes; // [rsp+50h] [rbp-30h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+58h] [rbp-28h] BYREF
  unsigned int v47; // [rsp+60h] [rbp-20h] BYREF
  __int64 v48; // [rsp+68h] [rbp-18h]
  char v49; // [rsp+70h] [rbp-10h]
  int v50; // [rsp+C0h] [rbp+40h]
  ULONG_PTR v51; // [rsp+D0h] [rbp+50h] BYREF

  v51 = a3;
  v10 = a4;
  v11 = a3;
  v47 = -1;
  v48 = 0;
  if ( (qword_140087010 & 2) != 0 )
  {
    v49 = 1;
    v47 = 8005;
    if ( (byte_140087202 & 1) != 0 )
      McTemplateK0q_EtwWriteTransfer(a1, EventProfilerEnter, a3, 8005);
  }
  else
  {
    v49 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v47, 8005);
  v14 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL);
  if ( ((__int64 (*)(void))PsGetCurrentProcess)() != v14 )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 30, 0, 0, 0);
    WdLogGlobalForLineNumber = 227;
  }
  if ( g_IsInternalReleaseOrDbg )
  {
    v16 = WdLogNewEntry5_WdTrace(v15);
    *(_QWORD *)(v16 + 24) = v11;
    *(_QWORD *)(v16 + 32) = v10;
    WdLogGlobalForLineNumber = 1512;
  }
  v17 = v10;
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
    if ( !(_DWORD)v10 || (v50 = 0, (_DWORD)v10 == 1) )
    {
      if ( (*(_DWORD *)v11 & 1) == 0 && !*(_QWORD *)(v18 + 56) && !*(_QWORD *)(v11 + 32) )
      {
        v21 = MmSecureVirtualMemory(v19, Size, 4u);
        *(_QWORD *)(v11 + 32) = v21;
        if ( !v21 )
        {
          _InterlockedIncrement(&dword_140087788);
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
          DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v47);
          if ( v49 )
          {
            if ( (byte_140087202 & 1) != 0 )
              McTemplateK0q_EtwWriteTransfer(v24, EventProfilerExit, v25, v47);
          }
          return 3221225495LL;
        }
      }
      if ( *(_DWORD *)(a2 + 36440) != -1 )
        (*(void (__fastcall **)(_QWORD))(a2 + 36168))(*(_QWORD *)(a2 + 36232));
      v50 = 1;
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
        if ( (byte_140087201 & 1) != 0 )
          McTemplateK0q_EtwWriteTransfer(v31, EventPerformanceWarning, v32, 12);
        v19 += NumberOfBytes;
        v28 -= NumberOfBytes;
        KeDelayExecutionThread(0, 0, &Interval);
      }
      VIDMM_GLOBAL::SetMemoryRefreshIdle((VIDMM_GLOBAL *)a2);
      v11 = v51;
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
        if ( (byte_140087201 & 1) != 0 )
          McTemplateK0q_EtwWriteTransfer(v36, EventPerformanceWarning, v37, 12);
        v38 = a9;
        v39 = a8;
        while ( MmRotatePhysicalView(v19, &NumberOfBytes, NewMdl, MmToFrameBufferNoCopy, v39, v38) < 0 )
          KeDelayExecutionThread(0, 0, &Interval);
        KeDelayExecutionThread(0, 0, &Interval);
        v11 = v51;
        v20 = Size;
      }
      VIDMM_GLOBAL::SetMemoryRefreshIdle((VIDMM_GLOBAL *)a2);
    }
    else
    {
      v51 = v20;
      v30 = MmRotatePhysicalView(v19, &v51, NewMdl, (MM_ROTATE_DIRECTION)v10, a8, a9);
    }
    if ( v30 < 0 )
    {
      if ( v50 )
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
      v42 = PsGetCurrentProcess(v18);
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(0, 270, 1, v42, v11, v17);
      WdLogGlobalForLineNumber = 227;
    }
  }
  v30 = -1073741823;
LABEL_56:
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v47);
  if ( v49 && (byte_140087202 & 1) != 0 )
    McTemplateK0q_EtwWriteTransfer(v43, EventProfilerExit, v44, v47);
  return (unsigned int)v30;
}

```

## disassembly

```asm
0x1400b3030  mov     [rsp-38h+arg_8], rbx
0x1400b3035  mov     [rsp-38h+arg_10], r8
0x1400b303a  push    rbp
0x1400b303b  push    rsi
0x1400b303c  push    rdi
0x1400b303d  push    r12
0x1400b303f  push    r13
0x1400b3041  push    r14
0x1400b3043  push    r15
0x1400b3045  mov     rbp, rsp
0x1400b3048  sub     rsp, 80h
0x1400b304f  xor     r12d, r12d
0x1400b3052  movsxd  rdi, r9d
0x1400b3055  test    byte ptr cs:qword_140087010, 2
0x1400b305c  mov     rsi, r8
0x1400b305f  mov     r15, rdx
0x1400b3062  mov     [rbp+var_20], 0FFFFFFFFh
0x1400b3069  mov     rbx, rcx
0x1400b306c  mov     [rbp+var_18], r12
0x1400b3070  mov     r14d, 1F45h
0x1400b3076  jz      short loc_1400B309A
0x1400b3078  test    cs:byte_140087202, 1
0x1400b307f  mov     [rbp+var_10], 1
0x1400b3083  mov     [rbp+var_20], r14d
0x1400b3087  jz      short loc_1400B309E
0x1400b3089  mov     r9d, r14d
0x1400b308c  lea     rdx, EventProfilerEnter
0x1400b3093  call    McTemplateK0q_EtwWriteTransfer
0x1400b3098  jmp     short loc_1400B309E
0x1400b309a  mov     [rbp+var_10], r12b
0x1400b309e  mov     edx, r14d
0x1400b30a1  lea     rcx, [rbp+var_20]
0x1400b30a5  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1400b30aa  mov     rax, [rbx+8]
0x1400b30ae  mov     rbx, [rax+10h]
0x1400b30b2  call    cs:__imp_PsGetCurrentProcess
0x1400b30b9  nop     dword ptr [rax+rax+00h]
0x1400b30be  cmp     rax, rbx
0x1400b30c1  jz      short loc_1400B30FE
0x1400b30c3  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400b30ca  mov     dword ptr [rax], 1
0x1400b30d0  xor     r9d, r9d
0x1400b30d3  mov     [rsp+80h+Context], r12
0x1400b30d8  mov     edx, 10Eh
0x1400b30dd  mov     [rsp+80h+CopyFunction], r12
0x1400b30e2  xor     ecx, ecx
0x1400b30e4  lea     r8d, [r9+1Eh]
0x1400b30e8  call    cs:__imp_WdLogSingleEntry5
0x1400b30ef  nop     dword ptr [rax+rax+00h]
0x1400b30f4  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x1400b30fe  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400b3105  cmp     [rax], r12b
0x1400b3108  jz      short loc_1400B3128
0x1400b310a  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400b3111  nop     dword ptr [rax+rax+00h]
0x1400b3116  mov     [rax+18h], rsi
0x1400b311a  mov     [rax+20h], rdi
0x1400b311e  mov     cs:WdLogGlobalForLineNumber, 5E8h
0x1400b3128  mov     edx, [rsi]
0x1400b312a  mov     r14d, edi
0x1400b312d  mov     rcx, [rsi+8]
0x1400b3131  and     edx, 1
0x1400b3134  jz      short loc_1400B3148
0x1400b3136  test    dword ptr [rsi+14h], 800000h
0x1400b313d  jz      loc_1400B3490
0x1400b3143  mov     r14, rcx
0x1400b3146  jmp     short loc_1400B315B
0x1400b3148  mov     eax, [rcx+40h]
0x1400b314b  test    al, 1
0x1400b314d  jz      loc_1400B3490
0x1400b3153  mov     r14, [rcx+20h]
0x1400b3157  add     r14, [rsi+10h]
0x1400b315b  mov     r13, [rbp+Size]
0x1400b315f  test    edi, edi
0x1400b3161  jz      short loc_1400B3170
0x1400b3163  mov     [rbp+arg_0], r12d
0x1400b3167  cmp     edi, 1
0x1400b316a  jnz     loc_1400B3249
0x1400b3170  test    edx, edx
0x1400b3172  jnz     loc_1400B3223
0x1400b3178  cmp     [rcx+38h], r12
0x1400b317c  jnz     loc_1400B3223
0x1400b3182  cmp     [rsi+20h], r12
0x1400b3186  jnz     loc_1400B3223
0x1400b318c  lea     r8d, [rdx+4]; ProbeMode
0x1400b3190  mov     rcx, r14; Address
0x1400b3193  mov     rdx, r13; Size
0x1400b3196  call    cs:__imp_MmSecureVirtualMemory
0x1400b319d  nop     dword ptr [rax+rax+00h]
0x1400b31a2  mov     [rsi+20h], rax
0x1400b31a6  test    rax, rax
0x1400b31a9  jnz     short loc_1400B3223
0x1400b31ab  lock inc cs:dword_140087788
0x1400b31b2  lea     ecx, [rax+6]
0x1400b31b5  call    cs:__imp_WdLogSingleEntry0
0x1400b31bc  nop     dword ptr [rax+rax+00h]
0x1400b31c1  mov     [rsp+80h+var_48], r12
0x1400b31c6  lea     r9, aCouldnTSecureT; "Couldn't secure the virtual memory rang"...
0x1400b31cd  mov     eax, 612h
0x1400b31d2  mov     [rsp+80h+var_50], r12
0x1400b31d7  mov     [rsp+80h+Context], r12
0x1400b31dc  mov     edx, 40001h
0x1400b31e1  mov     cs:WdLogGlobalForLineNumber, eax
0x1400b31e7  mov     [rsp+80h+CopyFunction], rax
0x1400b31ec  call    DxgkLogInternalTriageEvent
0x1400b31f1  lea     rcx, [rbp+var_20]; this
0x1400b31f5  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1400b31fa  cmp     [rbp+var_10], r12b
0x1400b31fe  jz      short loc_1400B3219
0x1400b3200  test    cs:byte_140087202, 1
0x1400b3207  jz      short loc_1400B3219
0x1400b3209  mov     r9d, [rbp+var_20]
0x1400b320d  lea     rdx, EventProfilerExit
0x1400b3214  call    McTemplateK0q_EtwWriteTransfer
0x1400b3219  mov     eax, 0C0000017h
0x1400b321e  jmp     loc_1400B351F
0x1400b3223  mov     edx, [r15+8E58h]
0x1400b322a  cmp     edx, 0FFFFFFFFh
0x1400b322d  jz      short loc_1400B3242
0x1400b322f  mov     rax, [r15+8D48h]
0x1400b3236  mov     rcx, [r15+8D88h]
0x1400b323d  call    _guard_dispatch_icall
0x1400b3242  mov     [rbp+arg_0], 1
0x1400b3249  cmp     edi, 2
0x1400b324c  jnz     loc_1400B3307
0x1400b3252  mov     rsi, [rbp+arg_38]
0x1400b3256  mov     r12, r13
0x1400b3259  mov     r13, [rbp+arg_40]
0x1400b3260  mov     qword ptr [rbp+Interval], 0FFFFFFFFFFFFD8F0h
0x1400b3268  mov     [rsp+80h+Context], r13; Context
0x1400b326d  lea     rdx, [rbp+NumberOfBytes]; NumberOfBytes
0x1400b3271  mov     r9d, 2; Direction
0x1400b3277  mov     [rsp+80h+CopyFunction], rsi; CopyFunction
0x1400b327c  xor     r8d, r8d; NewMdl
0x1400b327f  mov     [rbp+NumberOfBytes], r12
0x1400b3283  mov     rcx, r14; VirtualAddress
0x1400b3286  call    cs:__imp_MmRotatePhysicalView
0x1400b328d  nop     dword ptr [rax+rax+00h]
0x1400b3292  mov     ebx, eax
0x1400b3294  cmp     eax, 40000019h
0x1400b3299  jnz     short loc_1400B32F2
0x1400b329b  mov     ecx, 3
0x1400b32a0  call    cs:__imp_WdLogSingleEntry0
0x1400b32a7  nop     dword ptr [rax+rax+00h]
0x1400b32ac  test    cs:byte_140087201, 1
0x1400b32b3  mov     cs:WdLogGlobalForLineNumber, 654h
0x1400b32bd  jz      short loc_1400B32D1
0x1400b32bf  mov     r9d, 0Ch
0x1400b32c5  lea     rdx, EventPerformanceWarning
0x1400b32cc  call    McTemplateK0q_EtwWriteTransfer
0x1400b32d1  add     r14, [rbp+NumberOfBytes]
0x1400b32d5  lea     r8, [rbp+Interval]; Interval
0x1400b32d9  sub     r12, [rbp+NumberOfBytes]
0x1400b32dd  xor     edx, edx; Alertable
0x1400b32df  xor     ecx, ecx; WaitMode
0x1400b32e1  call    cs:__imp_KeDelayExecutionThread
0x1400b32e8  nop     dword ptr [rax+rax+00h]
0x1400b32ed  jmp     loc_1400B3268
0x1400b32f2  mov     rcx, r15; this
0x1400b32f5  call    ?SetMemoryRefreshIdle@VIDMM_GLOBAL@@QEAAXXZ; VIDMM_GLOBAL::SetMemoryRefreshIdle(void)
0x1400b32fa  mov     rsi, [rbp+arg_10]
0x1400b32fe  mov     r13, [rbp+Size]
0x1400b3302  jmp     loc_1400B3411
0x1400b3307  cmp     edi, 3
0x1400b330a  jnz     loc_1400B3416
0x1400b3310  mov     r12d, [rbp+arg_48]
0x1400b3317  and     r12d, 1
0x1400b331b  mov     qword ptr [rbp+Interval], 0FFFFFFFFFFFFD8F0h
0x1400b3323  mov     [rbp+NumberOfBytes], r13
0x1400b3327  mov     rax, [rbp+arg_40]
0x1400b332e  lea     rdx, [rbp+NumberOfBytes]; NumberOfBytes
0x1400b3332  mov     [rsp+80h+Context], rax; Context
0x1400b3337  mov     r9d, 3; Direction
0x1400b333d  mov     rax, [rbp+arg_38]
0x1400b3341  xor     r8d, r8d; NewMdl
0x1400b3344  mov     rcx, r14; VirtualAddress
0x1400b3347  mov     [rsp+80h+CopyFunction], rax; CopyFunction
0x1400b334c  call    cs:__imp_MmRotatePhysicalView
0x1400b3353  nop     dword ptr [rax+rax+00h]
0x1400b3358  mov     ebx, eax
0x1400b335a  test    r12d, r12d
0x1400b335d  jz      loc_1400B3409
0x1400b3363  cmp     eax, 40000019h
0x1400b3368  jnz     loc_1400B3409
0x1400b336e  mov     ecx, 3
0x1400b3373  call    cs:__imp_WdLogSingleEntry0
0x1400b337a  nop     dword ptr [rax+rax+00h]
0x1400b337f  test    cs:byte_140087201, 1
0x1400b3386  mov     cs:WdLogGlobalForLineNumber, 69Dh
0x1400b3390  jz      short loc_1400B33A4
0x1400b3392  mov     r9d, 0Ch
0x1400b3398  lea     rdx, EventPerformanceWarning
0x1400b339f  call    McTemplateK0q_EtwWriteTransfer
0x1400b33a4  mov     rsi, [rbp+arg_40]
0x1400b33ab  mov     r13, [rbp+arg_38]
0x1400b33af  mov     r8, [rbp+NewMdl]; NewMdl
0x1400b33b3  lea     rdx, [rbp+NumberOfBytes]; NumberOfBytes
0x1400b33b7  mov     [rsp+80h+Context], rsi; Context
0x1400b33bc  mov     r9d, 1; Direction
0x1400b33c2  mov     rcx, r14; VirtualAddress
0x1400b33c5  mov     [rsp+80h+CopyFunction], r13; CopyFunction
0x1400b33ca  call    cs:__imp_MmRotatePhysicalView
0x1400b33d1  nop     dword ptr [rax+rax+00h]
0x1400b33d6  xor     edx, edx; Alertable
0x1400b33d8  lea     r8, [rbp+Interval]; Interval
0x1400b33dc  xor     ecx, ecx; WaitMode
0x1400b33de  test    eax, eax
0x1400b33e0  jns     short loc_1400B33F0
0x1400b33e2  call    cs:__imp_KeDelayExecutionThread
0x1400b33e9  nop     dword ptr [rax+rax+00h]
0x1400b33ee  jmp     short loc_1400B33AF
0x1400b33f0  call    cs:__imp_KeDelayExecutionThread
0x1400b33f7  nop     dword ptr [rax+rax+00h]
0x1400b33fc  mov     rsi, [rbp+arg_10]
0x1400b3400  mov     r13, [rbp+Size]
0x1400b3404  jmp     loc_1400B3327
0x1400b3409  mov     rcx, r15; this
0x1400b340c  call    ?SetMemoryRefreshIdle@VIDMM_GLOBAL@@QEAAXXZ; VIDMM_GLOBAL::SetMemoryRefreshIdle(void)
0x1400b3411  xor     r12d, r12d
0x1400b3414  jmp     short loc_1400B344B
0x1400b3416  mov     rax, [rbp+arg_40]
0x1400b341d  lea     rdx, [rbp+arg_10]; NumberOfBytes
0x1400b3421  mov     r8, [rbp+NewMdl]; NewMdl
0x1400b3425  mov     r9d, edi; Direction
0x1400b3428  mov     [rsp+80h+Context], rax; Context
0x1400b342d  mov     rcx, r14; VirtualAddress
0x1400b3430  mov     rax, [rbp+arg_38]
0x1400b3434  mov     [rsp+80h+CopyFunction], rax; CopyFunction
0x1400b3439  mov     [rbp+arg_10], r13
0x1400b343d  call    cs:__imp_MmRotatePhysicalView
0x1400b3444  nop     dword ptr [rax+rax+00h]
0x1400b3449  mov     ebx, eax
0x1400b344b  test    ebx, ebx
0x1400b344d  js      short loc_1400B345A
0x1400b344f  cmp     edi, 1
0x1400b3452  setbe   al
0x1400b3455  mov     [rsi+40h], al
0x1400b3458  jmp     short loc_1400B3468
0x1400b345a  cmp     [rbp+arg_0], r12d
0x1400b345e  jz      short loc_1400B3468
0x1400b3460  mov     rcx, r15; this
0x1400b3463  call    ?SetMemoryRefreshIdle@VIDMM_GLOBAL@@QEAAXXZ; VIDMM_GLOBAL::SetMemoryRefreshIdle(void)
0x1400b3468  call    cs:__imp_PsGetCurrentProcess
0x1400b346f  nop     dword ptr [rax+rax+00h]
0x1400b3474  mov     r9, [rbp+NewMdl]; struct _MDL *
0x1400b3478  mov     r8, r13; unsigned __int64
0x1400b347b  mov     rcx, rax; struct _EPROCESS *
0x1400b347e  mov     dword ptr [rsp+80h+Context], ebx; int
0x1400b3482  mov     rdx, r14; void *
0x1400b3485  mov     dword ptr [rsp+80h+CopyFunction], edi; enum _MM_ROTATE_DIRECTION
0x1400b3489  call    ?RecordRotation@VIDMM_GLOBAL@@SAXPEAU_EPROCESS@@PEAX_KPEAU_MDL@@W4_MM_ROTATE_DIRECTION@@J@Z; VIDMM_GLOBAL::RecordRotation(_EPROCESS *,void *,unsigned __int64,_MDL *,_MM_ROTATE_DIRECTION,long)
0x1400b348e  jmp     short loc_1400B34F5
0x1400b3490  mov     ebx, r12d
0x1400b3493  test    edi, edi
0x1400b3495  jz      short loc_1400B34F0
0x1400b3497  sub     edi, 1
0x1400b349a  jz      short loc_1400B34F0
0x1400b349c  sub     edi, 1
0x1400b349f  jz      short loc_1400B34A6
0x1400b34a1  cmp     edi, 1
0x1400b34a4  jnz     short loc_1400B34F5
0x1400b34a6  call    cs:__imp_PsGetCurrentProcess
0x1400b34ad  nop     dword ptr [rax+rax+00h]
0x1400b34b2  mov     rcx, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400b34b9  mov     dword ptr [rcx], 1
0x1400b34bf  movsxd  rcx, r14d
0x1400b34c2  mov     r9, rax
0x1400b34c5  mov     [rsp+80h+Context], rcx
0x1400b34ca  mov     edx, 10Eh
0x1400b34cf  xor     ecx, ecx
0x1400b34d1  mov     [rsp+80h+CopyFunction], rsi
0x1400b34d6  lea     r8d, [rcx+1]
0x1400b34da  call    cs:__imp_WdLogSingleEntry5
0x1400b34e1  nop     dword ptr [rax+rax+00h]
0x1400b34e6  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x1400b34f0  mov     ebx, 0C0000001h
0x1400b34f5  lea     rcx, [rbp+var_20]; this
0x1400b34f9  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1400b34fe  cmp     [rbp+var_10], r12b
0x1400b3502  jz      short loc_1400B351D
0x1400b3504  test    cs:byte_140087202, 1
0x1400b350b  jz      short loc_1400B351D
0x1400b350d  mov     r9d, [rbp+var_20]
0x1400b3511  lea     rdx, EventProfilerExit
0x1400b3518  call    McTemplateK0q_EtwWriteTransfer
0x1400b351d  mov     eax, ebx
0x1400b351f  mov     rbx, [rsp+80h+arg_8]
0x1400b3527  add     rsp, 80h
0x1400b352e  pop     r15
0x1400b3530  pop     r14
0x1400b3532  pop     r13
0x1400b3534  pop     r12
0x1400b3536  pop     rdi
0x1400b3537  pop     rsi
0x1400b3538  pop     rbp
0x1400b3539  retn
```
