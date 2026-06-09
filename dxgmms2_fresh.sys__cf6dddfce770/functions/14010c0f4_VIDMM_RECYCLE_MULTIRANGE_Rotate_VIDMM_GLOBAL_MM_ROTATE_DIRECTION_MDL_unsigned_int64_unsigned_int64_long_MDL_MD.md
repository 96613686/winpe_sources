# VIDMM_RECYCLE_MULTIRANGE::Rotate(VIDMM_GLOBAL *,_MM_ROTATE_DIRECTION,_MDL *,unsigned __int64,unsigned __int64,long (*)(_MDL *,_MDL *,void *),void *,VIDMM_ROTATE_FLAGS)

- ea: `0x14010c0f4`
- end: `0x14010c701`
- name: `?Rotate@VIDMM_RECYCLE_MULTIRANGE@@QEAAJPEAVVIDMM_GLOBAL@@W4_MM_ROTATE_DIRECTION@@PEAU_MDL@@_K3P6AJ22PEAX@Z4TVIDMM_ROTATE_FLAGS@@@Z`
- size: `1549`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400cac30`

## callees

- `0x140004268`
- `0x1400128c8`
- `0x1400f37f4`
- `0x1400f6ebc`
- `0x1400f7698`
- `0x14010c0f4`
- `0x14010c708`
- `0x140113db8`

## import_xrefs

- `ntoskrnl!MmSecureVirtualMemory` at `0x14010c24d`
- `ntoskrnl!MmSecureVirtualMemory` at `0x14010c24d`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x14010c64e`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x14010c64e`
- `ntoskrnl!KeDelayExecutionThread` at `0x14010c367`
- `ntoskrnl!KeDelayExecutionThread` at `0x14010c458`
- `ntoskrnl!KeDelayExecutionThread` at `0x14010c466`
- `ntoskrnl!KeDelayExecutionThread` at `0x14010c598`
- `ntoskrnl!KeDelayExecutionThread` at `0x14010c615`
- `ntoskrnl!KeDelayExecutionThread` at `0x14010c367`
- `ntoskrnl!KeDelayExecutionThread` at `0x14010c458`
- `ntoskrnl!KeDelayExecutionThread` at `0x14010c466`
- `ntoskrnl!KeDelayExecutionThread` at `0x14010c598`
- `ntoskrnl!KeDelayExecutionThread` at `0x14010c615`
- `ntoskrnl!MmRotatePhysicalView` at `0x14010c300`
- `ntoskrnl!MmRotatePhysicalView` at `0x14010c3bf`
- `ntoskrnl!MmRotatePhysicalView` at `0x14010c440`
- `ntoskrnl!MmRotatePhysicalView` at `0x14010c4c5`
- `ntoskrnl!MmRotatePhysicalView` at `0x14010c300`
- `ntoskrnl!MmRotatePhysicalView` at `0x14010c3bf`
- `ntoskrnl!MmRotatePhysicalView` at `0x14010c440`
- `ntoskrnl!MmRotatePhysicalView` at `0x14010c4c5`
- `ntoskrnl!MmIsIoSpaceActive` at `0x14010c574`
- `ntoskrnl!MmIsIoSpaceActive` at `0x14010c5aa`
- `ntoskrnl!MmIsIoSpaceActive` at `0x14010c5f1`
- `ntoskrnl!MmIsIoSpaceActive` at `0x14010c627`
- `ntoskrnl!MmIsIoSpaceActive` at `0x14010c574`
- `ntoskrnl!MmIsIoSpaceActive` at `0x14010c5aa`
- `ntoskrnl!MmIsIoSpaceActive` at `0x14010c5f1`
- `ntoskrnl!MmIsIoSpaceActive` at `0x14010c627`
- `ntoskrnl!PsGetCurrentProcess` at `0x14010c65e`
- `ntoskrnl!PsGetCurrentProcess` at `0x14010c6a0`
- `ntoskrnl!PsGetCurrentProcess` at `0x14010c65e`
- `ntoskrnl!PsGetCurrentProcess` at `0x14010c6a0`
- `watchdog!WdLogSingleEntry3` at `0x14010c1ef`
- `watchdog!WdLogSingleEntry3` at `0x14010c1ef`
- `watchdog!WdLogSingleEntry5` at `0x14010c155`
- `watchdog!WdLogSingleEntry5` at `0x14010c6cd`
- `watchdog!WdLogSingleEntry5` at `0x14010c155`
- `watchdog!WdLogSingleEntry5` at `0x14010c6cd`
- `watchdog!WdLogSingleEntry0` at `0x14010c26d`
- `watchdog!WdLogSingleEntry0` at `0x14010c322`
- `watchdog!WdLogSingleEntry0` at `0x14010c3e9`
- `watchdog!WdLogSingleEntry0` at `0x14010c26d`
- `watchdog!WdLogSingleEntry0` at `0x14010c322`
- `watchdog!WdLogSingleEntry0` at `0x14010c3e9`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14010c12d`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14010c6ac`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 __fastcall VIDMM_RECYCLE_MULTIRANGE::Rotate(
        union _LARGE_INTEGER a1,
        ULONG_PTR a2,
        int a3,
        struct _MDL *a4,
        __int64 a5,
        unsigned __int64 a6,
        PMM_ROTATE_COPY_CALLBACK_FUNCTION CopyFunction,
        PVOID Context,
        char a9)
{
  union _LARGE_INTEGER v9; // r14
  __int64 v10; // r13
  __int64 v11; // rbx
  int v12; // r12d
  char v13; // di
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rbx
  HANDLE v17; // rax
  int v18; // ecx
  int v19; // r8d
  char *v21; // rdi
  unsigned __int64 v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // r8
  int v25; // ebx
  NTSTATUS v26; // eax
  __int64 v27; // rcx
  __int64 v28; // r8
  PVOID v29; // r14
  NTSTATUS (__stdcall *v30)(PMDL, PMDL, PVOID); // r13
  struct _MDL *v31; // rbx
  PMDL v32; // rbx
  ULONG ByteCount; // eax
  __int64 v34; // rcx
  struct _MDL *Next; // rbx
  unsigned int v36; // eax
  struct _MDL *v37; // rdx
  PMDL v38; // r12
  unsigned int v39; // r13d
  unsigned int v40; // r14d
  struct _MDL *v41; // r8
  SIZE_T v42; // rdx
  PHYSICAL_ADDRESS v43; // rdi
  PHYSICAL_ADDRESS v44; // rcx
  union _LARGE_INTEGER v45; // r14
  PHYSICAL_ADDRESS v46; // rbx
  union _LARGE_INTEGER v47; // rdi
  void *v48; // rcx
  struct _EPROCESS *v49; // rax
  __int64 CurrentProcess; // rax
  int v51; // [rsp+58h] [rbp-41h]
  unsigned int v52; // [rsp+58h] [rbp-41h]
  union _LARGE_INTEGER v53; // [rsp+60h] [rbp-39h] BYREF
  ULONG_PTR NumberOfBytes[2]; // [rsp+68h] [rbp-31h] BYREF
  char *v55; // [rsp+78h] [rbp-21h]
  union _LARGE_INTEGER Interval; // [rsp+80h] [rbp-19h] BYREF
  union _LARGE_INTEGER v57; // [rsp+88h] [rbp-11h] BYREF
  union _LARGE_INTEGER v58; // [rsp+E8h] [rbp+4Fh] BYREF
  ULONG_PTR v59; // [rsp+F0h] [rbp+57h] BYREF
  int v60; // [rsp+F8h] [rbp+5Fh]
  PMDL NewMdl; // [rsp+100h] [rbp+67h]

  NewMdl = a4;
  v60 = a3;
  v59 = a2;
  v58 = a1;
  v9 = a1;
  v10 = a3;
  if ( *(_DWORD *)(a1.QuadPart + 144) == 4 )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 52, 11, a3, 0);
    WdLogGlobalForLineNumber = 227;
  }
  v11 = *(_QWORD *)(a1.QuadPart + 64);
  v12 = 0;
  v13 = 0;
  while ( !v13 )
  {
    if ( *(_DWORD *)(v11 + 64) == 3 )
    {
      VIDMM_RECYCLE_HEAP_MGR::RemoveFromDebounce(
        (VIDMM_RECYCLE_HEAP_MGR *)a1.QuadPart,
        (struct VIDMM_RECYCLE_RANGE *)v11);
      LOBYTE(v59) = 0;
      v12 = VIDMM_RECYCLE_RANGE::DebouncedUnlock((VIDMM_RECYCLE_RANGE *)v11, (bool *)&v59);
      if ( v12 < 0 )
      {
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WdLogSingleEntry3)(
          3,
          v11,
          (union _LARGE_INTEGER)v9.QuadPart,
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v9.QuadPart + 80) + 32LL) + 8LL) + 8LL) + 16LL));
        WdLogGlobalForLineNumber = 3382;
        VIDMM_RECYCLE_HEAP_MGR::AddToUnlockDebounce(
          *(VIDMM_RECYCLE_HEAP_MGR **)(*(_QWORD *)(*(_QWORD *)(v9.QuadPart + 80) + 32LL) + 8LL),
          (struct VIDMM_RECYCLE_RANGE *)v11);
        return (unsigned int)v12;
      }
    }
    if ( v11 == *(_QWORD *)(v9.QuadPart + 72) )
    {
      v13 = 1;
    }
    else
    {
      v14 = *(_QWORD *)(v11 + 120);
      v15 = *(_QWORD *)(v11 + 72);
      v11 = 0;
      a1.QuadPart = v15 + 72;
      if ( v14 != a1.QuadPart )
        v11 = v14 - 120;
    }
  }
  if ( !VIDMM_RECYCLE_MULTIRANGE::IsRotateVAD((VIDMM_RECYCLE_MULTIRANGE *)v9.QuadPart) )
  {
    if ( (unsigned int)v10 >= 2 )
    {
      if ( (unsigned int)(v10 - 2) > 1 )
        return (unsigned int)v12;
      CurrentProcess = PsGetCurrentProcess();
      g_DxgMmsBugcheckExportIndex = 1;
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WdLogSingleEntry5)(
        0,
        270,
        1,
        CurrentProcess,
        (union _LARGE_INTEGER)v9.QuadPart,
        v10);
      WdLogGlobalForLineNumber = 227;
    }
    return (unsigned int)-1073741823;
  }
  v16 = *(_QWORD *)(v9.QuadPart + 48);
  if ( (unsigned int)v10 <= 1 && !*(_QWORD *)(v9.QuadPart + 120) )
  {
    v17 = MmSecureVirtualMemory(*(PVOID *)(v9.QuadPart + 48), *(_QWORD *)(v9.QuadPart + 40) - v16, 4u);
    *(_QWORD *)(v9.QuadPart + 120) = v17;
    if ( !v17 )
    {
      _InterlockedAdd(&dword_140087788, 1u);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 3441;
      DxgkLogInternalTriageEvent(
        v18,
        262145,
        v19,
        (unsigned int)L"Couldn't secure the virtual memory range for the allocation.\n",
        3441,
        0,
        0,
        0);
      return 3221225495LL;
    }
  }
  v21 = (char *)(v16 + a5);
  v55 = (char *)(v16 + a5);
  if ( (_DWORD)v10 == 2 )
  {
    v22 = a6;
    Interval.QuadPart = -10000;
    while ( 1 )
    {
      NumberOfBytes[0] = v22;
      LODWORD(v59) = MmRotatePhysicalView(v21, NumberOfBytes, 0, MmToRegularMemory, CopyFunction, Context);
      v12 = v59;
      if ( (_DWORD)v59 != 1073741849 )
        break;
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 3496;
      if ( (byte_140087201 & 1) != 0 )
        McTemplateK0q_EtwWriteTransfer(v23, &EventPerformanceWarning, v24, 12);
      v21 += NumberOfBytes[0];
      v22 -= NumberOfBytes[0];
      v55 = v21;
      KeDelayExecutionThread(0, 0, &Interval);
    }
LABEL_37:
    v32 = NewMdl;
    goto LABEL_38;
  }
  if ( (_DWORD)v10 == 3 )
  {
    v53.QuadPart = -10000;
    v25 = a9 & 1;
    v51 = v25;
    NumberOfBytes[0] = a6;
    while ( 1 )
    {
      v26 = MmRotatePhysicalView(v21, NumberOfBytes, 0, MmToRegularMemoryNoCopy, CopyFunction, Context);
      LODWORD(v59) = v26;
      v12 = v26;
      if ( !v25 || v26 != 1073741849 )
        break;
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 3561;
      if ( (byte_140087201 & 1) != 0 )
        McTemplateK0q_EtwWriteTransfer(v27, &EventPerformanceWarning, v28, 12);
      v29 = Context;
      v30 = CopyFunction;
      v31 = NewMdl;
      while ( MmRotatePhysicalView(v21, NumberOfBytes, v31, MmToFrameBufferNoCopy, v30, v29) < 0 )
        KeDelayExecutionThread(0, 0, &v53);
      KeDelayExecutionThread(0, 0, &v53);
      v9 = v58;
      LODWORD(v10) = v60;
      v25 = v51;
    }
    goto LABEL_37;
  }
  v59 = a6;
  if ( g_bInjectRotateFailure )
  {
    v12 = -1073741823;
    goto LABEL_60;
  }
  v32 = NewMdl;
  v12 = MmRotatePhysicalView(v21, &v59, NewMdl, (MM_ROTATE_DIRECTION)v10, CopyFunction, Context);
  LODWORD(v59) = v12;
LABEL_38:
  if ( v12 < 0 )
  {
    if ( v12 == -1073741558 && (unsigned int)(v10 - 2) <= 1 )
    {
      ByteCount = v32->ByteCount;
      v34 = 1;
      Next = v32[1].Next;
      v36 = ByteCount >> 12;
      v37 = Next;
      v52 = v36;
      if ( v36 > 1 )
      {
        v38 = NewMdl;
        v39 = 1;
        v40 = v36;
        do
        {
          v41 = (struct _MDL *)*((_QWORD *)&v38[1].Next + v39);
          if ( v41 == (struct _MDL *)((char *)&v37->Next + 1) )
          {
            ++v34;
          }
          else
          {
            v42 = v34 << 12;
            v43.QuadPart = (_QWORD)Next << 12;
            v57.QuadPart = v34 << 12;
            v44.QuadPart = (_QWORD)Next << 12;
            Next = v41;
            if ( MmIsIoSpaceActive(v44, v42) )
            {
              v45 = v57;
              do
              {
                v57.QuadPart = -10000;
                KeDelayExecutionThread(0, 0, &v57);
              }
              while ( MmIsIoSpaceActive(v43, v45.QuadPart) );
              v40 = v52;
            }
            v41 = Next;
            v34 = 1;
          }
          ++v39;
          v37 = v41;
        }
        while ( v39 < v40 );
        v9 = v58;
        v12 = v59;
        LODWORD(v10) = v60;
      }
      v53.QuadPart = v34 << 12;
      v46.QuadPart = (_QWORD)Next << 12;
      if ( MmIsIoSpaceActive(v46, v34 << 12) )
      {
        v47 = v53;
        do
        {
          v58.QuadPart = -10000;
          KeDelayExecutionThread(0, 0, &v58);
        }
        while ( MmIsIoSpaceActive(v46, v47.QuadPart) );
      }
      --*(_DWORD *)(v9.QuadPart + 96);
      v21 = v55;
    }
    goto LABEL_60;
  }
  if ( (unsigned int)v10 > 1 )
  {
    --*(_DWORD *)(v9.QuadPart + 96);
    if ( (a9 & 2) != 0 )
      goto LABEL_63;
LABEL_60:
    v48 = *(void **)(v9.QuadPart + 120);
    if ( v48 && !*(_DWORD *)(v9.QuadPart + 96) )
    {
      MmUnsecureVirtualMemory(v48);
      *(_QWORD *)(v9.QuadPart + 120) = 0;
    }
    goto LABEL_63;
  }
  ++*(_DWORD *)(v9.QuadPart + 96);
LABEL_63:
  v49 = (struct _EPROCESS *)PsGetCurrentProcess();
  VIDMM_GLOBAL::RecordRotation(v49, v21, a6, NewMdl, (enum _MM_ROTATE_DIRECTION)v10, v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14010c0f4  mov     rax, rsp
0x14010c0f7  mov     [rax+20h], r9
0x14010c0fb  mov     [rax+18h], r8d
0x14010c0ff  mov     [rax+10h], rdx
0x14010c103  mov     [rax+8], rcx
0x14010c107  push    rbp
0x14010c108  push    rbx
0x14010c109  push    rsi
0x14010c10a  push    rdi
0x14010c10b  push    r12
0x14010c10d  push    r13
0x14010c10f  push    r14
0x14010c111  push    r15
0x14010c113  lea     rbp, [rax-47h]
0x14010c117  sub     rsp, 98h
0x14010c11e  cmp     dword ptr [rcx+90h], 4
0x14010c125  mov     r14, rcx
0x14010c128  movsxd  r13, r8d
0x14010c12b  jnz     short loc_14010C16B
0x14010c12d  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x14010c134  mov     dword ptr [rax], 1
0x14010c13a  xor     esi, esi
0x14010c13c  mov     edx, 10Eh
0x14010c141  mov     [rsp+0D0h+Context], rsi
0x14010c146  xor     ecx, ecx
0x14010c148  mov     [rsp+0D0h+CopyFunction], r13
0x14010c14d  lea     r9d, [rsi+0Bh]
0x14010c151  lea     r8d, [rsi+34h]
0x14010c155  call    cs:__imp_WdLogSingleEntry5
0x14010c15c  nop     dword ptr [rax+rax+00h]
0x14010c161  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x14010c16b  mov     rbx, [rcx+40h]
0x14010c16f  xor     esi, esi
0x14010c171  mov     r12d, esi
0x14010c174  mov     dil, sil
0x14010c177  lea     r15d, [rsi+1]
0x14010c17b  test    dil, dil
0x14010c17e  jnz     loc_14010C21E
0x14010c184  cmp     dword ptr [rbx+40h], 3
0x14010c188  jnz     short loc_14010C1A9
0x14010c18a  mov     rdx, rbx; struct VIDMM_RECYCLE_RANGE *
0x14010c18d  call    ?RemoveFromDebounce@VIDMM_RECYCLE_HEAP_MGR@@QEAAXPEAVVIDMM_RECYCLE_RANGE@@@Z; VIDMM_RECYCLE_HEAP_MGR::RemoveFromDebounce(VIDMM_RECYCLE_RANGE *)
0x14010c192  lea     rdx, [rbp+3Fh+arg_8]; bool *
0x14010c196  mov     byte ptr [rbp+3Fh+arg_8], sil
0x14010c19a  mov     rcx, rbx; this
0x14010c19d  call    ?DebouncedUnlock@VIDMM_RECYCLE_RANGE@@QEAAJAEA_N@Z; VIDMM_RECYCLE_RANGE::DebouncedUnlock(bool &)
0x14010c1a2  mov     r12d, eax
0x14010c1a5  test    eax, eax
0x14010c1a7  js      short loc_14010C1D0
0x14010c1a9  cmp     rbx, [r14+48h]
0x14010c1ad  jnz     short loc_14010C1B4
0x14010c1af  mov     dil, r15b
0x14010c1b2  jmp     short loc_14010C17B
0x14010c1b4  mov     rdx, [rbx+78h]
0x14010c1b8  mov     rcx, [rbx+48h]
0x14010c1bc  mov     rbx, rsi
0x14010c1bf  add     rcx, 48h ; 'H'
0x14010c1c3  cmp     rdx, rcx
0x14010c1c6  lea     rax, [rdx-78h]
0x14010c1ca  cmovnz  rbx, rax
0x14010c1ce  jmp     short loc_14010C17B
0x14010c1d0  mov     rax, [r14+50h]
0x14010c1d4  mov     rdx, rbx
0x14010c1d7  mov     ecx, 3
0x14010c1dc  mov     r8, [rax+20h]
0x14010c1e0  mov     rax, [r8+8]
0x14010c1e4  mov     r8, r14
0x14010c1e7  mov     r9, [rax+8]
0x14010c1eb  mov     r9, [r9+10h]
0x14010c1ef  call    cs:__imp_WdLogSingleEntry3
0x14010c1f6  nop     dword ptr [rax+rax+00h]
0x14010c1fb  mov     cs:WdLogGlobalForLineNumber, 0D36h
0x14010c205  mov     rdx, rbx; struct VIDMM_RECYCLE_RANGE *
0x14010c208  mov     rax, [r14+50h]
0x14010c20c  mov     rcx, [rax+20h]
0x14010c210  mov     rcx, [rcx+8]; this
0x14010c214  call    ?AddToUnlockDebounce@VIDMM_RECYCLE_HEAP_MGR@@QEAAXPEAVVIDMM_RECYCLE_RANGE@@@Z; VIDMM_RECYCLE_HEAP_MGR::AddToUnlockDebounce(VIDMM_RECYCLE_RANGE *)
0x14010c219  jmp     loc_14010C6E9
0x14010c21e  mov     rcx, r14; this
0x14010c221  call    ?IsRotateVAD@VIDMM_RECYCLE_MULTIRANGE@@QEAAEXZ; VIDMM_RECYCLE_MULTIRANGE::IsRotateVAD(void)
0x14010c226  test    al, al
0x14010c228  jz      loc_14010C689
0x14010c22e  mov     rbx, [r14+30h]
0x14010c232  cmp     r13d, r15d
0x14010c235  ja      short loc_14010C2B3
0x14010c237  cmp     [r14+78h], rsi
0x14010c23b  jnz     short loc_14010C2B3
0x14010c23d  mov     rdx, [r14+28h]
0x14010c241  mov     r8d, 4; ProbeMode
0x14010c247  sub     rdx, rbx; Size
0x14010c24a  mov     rcx, rbx; Address
0x14010c24d  call    cs:__imp_MmSecureVirtualMemory
0x14010c254  nop     dword ptr [rax+rax+00h]
0x14010c259  mov     [r14+78h], rax
0x14010c25d  test    rax, rax
0x14010c260  jnz     short loc_14010C2B3
0x14010c262  lock add cs:dword_140087788, r15d
0x14010c26a  lea     ecx, [rax+6]
0x14010c26d  call    cs:__imp_WdLogSingleEntry0
0x14010c274  nop     dword ptr [rax+rax+00h]
0x14010c279  mov     [rsp+38h], rsi
0x14010c27e  lea     r9, aCouldnTSecureT; "Couldn't secure the virtual memory rang"...
0x14010c285  mov     eax, 0D71h
0x14010c28a  mov     [rsp+0D0h+var_A0], rsi
0x14010c28f  mov     [rsp+0D0h+Context], rsi
0x14010c294  mov     edx, 40001h
0x14010c299  mov     cs:WdLogGlobalForLineNumber, eax
0x14010c29f  mov     [rsp+0D0h+CopyFunction], rax
0x14010c2a4  call    DxgkLogInternalTriageEvent
0x14010c2a9  mov     eax, 0C0000017h
0x14010c2ae  jmp     loc_14010C6EC
0x14010c2b3  mov     rdi, [rbp+3Fh+arg_20]
0x14010c2b7  mov     rax, 0FFFFFFFFFFFFD8F0h
0x14010c2be  add     rdi, rbx
0x14010c2c1  mov     [rbp+3Fh+var_60], rdi
0x14010c2c5  cmp     r13d, 2
0x14010c2c9  jnz     loc_14010C378
0x14010c2cf  mov     rbx, [rbp+3Fh+arg_28]
0x14010c2d3  mov     qword ptr [rbp+3Fh+Interval], rax
0x14010c2d7  mov     rax, [rbp+3Fh+arg_38]
0x14010c2de  lea     rdx, [rbp+3Fh+NumberOfBytes]; NumberOfBytes
0x14010c2e2  mov     [rsp+0D0h+Context], rax; Context
0x14010c2e7  mov     r9d, 2; Direction
0x14010c2ed  mov     rax, [rbp+3Fh+arg_30]
0x14010c2f1  xor     r8d, r8d; NewMdl
0x14010c2f4  mov     rcx, rdi; VirtualAddress
0x14010c2f7  mov     [rsp+0D0h+CopyFunction], rax; CopyFunction
0x14010c2fc  mov     [rbp+3Fh+NumberOfBytes], rbx
0x14010c300  call    cs:__imp_MmRotatePhysicalView
0x14010c307  nop     dword ptr [rax+rax+00h]
0x14010c30c  mov     dword ptr [rbp+3Fh+arg_8], eax
0x14010c30f  mov     r12d, eax
0x14010c312  cmp     eax, 40000019h
0x14010c317  jnz     loc_14010C4D9
0x14010c31d  mov     ecx, 3
0x14010c322  call    cs:__imp_WdLogSingleEntry0
0x14010c329  nop     dword ptr [rax+rax+00h]
0x14010c32e  test    cs:byte_140087201, r15b
0x14010c335  mov     cs:WdLogGlobalForLineNumber, 0DA8h
0x14010c33f  jz      short loc_14010C353
0x14010c341  mov     r9d, 0Ch
0x14010c347  lea     rdx, EventPerformanceWarning
0x14010c34e  call    McTemplateK0q_EtwWriteTransfer
0x14010c353  add     rdi, [rbp+3Fh+NumberOfBytes]
0x14010c357  lea     r8, [rbp+3Fh+Interval]; Interval
0x14010c35b  sub     rbx, [rbp+3Fh+NumberOfBytes]
0x14010c35f  xor     edx, edx; Alertable
0x14010c361  xor     ecx, ecx; WaitMode
0x14010c363  mov     [rbp+3Fh+var_60], rdi
0x14010c367  call    cs:__imp_KeDelayExecutionThread
0x14010c36e  nop     dword ptr [rax+rax+00h]
0x14010c373  jmp     loc_14010C2D7
0x14010c378  cmp     r13d, 3
0x14010c37c  jnz     loc_14010C482
0x14010c382  mov     ebx, [rbp+3Fh+arg_40]
0x14010c388  mov     qword ptr [rbp+3Fh+var_78], rax
0x14010c38c  and     ebx, r15d
0x14010c38f  mov     rax, [rbp+3Fh+arg_28]
0x14010c393  mov     [rbp+3Fh+var_80], ebx
0x14010c396  mov     [rbp+3Fh+NumberOfBytes], rax
0x14010c39a  mov     rax, [rbp+3Fh+arg_38]
0x14010c3a1  lea     rdx, [rbp+3Fh+NumberOfBytes]; NumberOfBytes
0x14010c3a5  mov     [rsp+0D0h+Context], rax; Context
0x14010c3aa  mov     r9d, 3; Direction
0x14010c3b0  mov     rax, [rbp+3Fh+arg_30]
0x14010c3b4  xor     r8d, r8d; NewMdl
0x14010c3b7  mov     rcx, rdi; VirtualAddress
0x14010c3ba  mov     [rsp+0D0h+CopyFunction], rax; CopyFunction
0x14010c3bf  call    cs:__imp_MmRotatePhysicalView
0x14010c3c6  nop     dword ptr [rax+rax+00h]
0x14010c3cb  mov     dword ptr [rbp+3Fh+arg_8], eax
0x14010c3ce  mov     r12d, eax
0x14010c3d1  test    ebx, ebx
0x14010c3d3  jz      loc_14010C4D9
0x14010c3d9  cmp     eax, 40000019h
0x14010c3de  jnz     loc_14010C4D9
0x14010c3e4  mov     ecx, 3
0x14010c3e9  call    cs:__imp_WdLogSingleEntry0
0x14010c3f0  nop     dword ptr [rax+rax+00h]
0x14010c3f5  test    cs:byte_140087201, r15b
0x14010c3fc  mov     cs:WdLogGlobalForLineNumber, 0DE9h
0x14010c406  jz      short loc_14010C41A
0x14010c408  mov     r9d, 0Ch
0x14010c40e  lea     rdx, EventPerformanceWarning
0x14010c415  call    McTemplateK0q_EtwWriteTransfer
0x14010c41a  mov     r14, [rbp+3Fh+arg_38]
0x14010c421  mov     r13, [rbp+3Fh+arg_30]
0x14010c425  mov     rbx, [rbp+3Fh+NewMdl]
0x14010c429  mov     [rsp+0D0h+Context], r14; Context
0x14010c42e  lea     rdx, [rbp+3Fh+NumberOfBytes]; NumberOfBytes
0x14010c432  mov     r9d, r15d; Direction
0x14010c435  mov     [rsp+0D0h+CopyFunction], r13; CopyFunction
0x14010c43a  mov     r8, rbx; NewMdl
0x14010c43d  mov     rcx, rdi; VirtualAddress
0x14010c440  call    cs:__imp_MmRotatePhysicalView
0x14010c447  nop     dword ptr [rax+rax+00h]
0x14010c44c  xor     edx, edx; Alertable
0x14010c44e  lea     r8, [rbp+3Fh+var_78]; Interval
0x14010c452  xor     ecx, ecx; WaitMode
0x14010c454  test    eax, eax
0x14010c456  jns     short loc_14010C466
0x14010c458  call    cs:__imp_KeDelayExecutionThread
0x14010c45f  nop     dword ptr [rax+rax+00h]
0x14010c464  jmp     short loc_14010C429
0x14010c466  call    cs:__imp_KeDelayExecutionThread
0x14010c46d  nop     dword ptr [rax+rax+00h]
0x14010c472  mov     r14, qword ptr [rbp+3Fh+arg_0]
0x14010c476  mov     r13d, [rbp+3Fh+arg_10]
0x14010c47a  mov     ebx, [rbp+3Fh+var_80]
0x14010c47d  jmp     loc_14010C39A
0x14010c482  mov     rax, [rbp+3Fh+arg_28]
0x14010c486  mov     [rbp+3Fh+arg_8], rax
0x14010c48a  mov     al, cs:?g_bInjectRotateFailure@@3_NC; bool volatile g_bInjectRotateFailure
0x14010c490  test    al, al
0x14010c492  jz      short loc_14010C49F
0x14010c494  mov     r12d, 0C0000001h
0x14010c49a  jmp     loc_14010C63F
0x14010c49f  mov     rax, [rbp+3Fh+arg_38]
0x14010c4a6  lea     rdx, [rbp+3Fh+arg_8]; NumberOfBytes
0x14010c4aa  mov     rbx, [rbp+3Fh+NewMdl]
0x14010c4ae  mov     r9d, r13d; Direction
0x14010c4b1  mov     [rsp+0D0h+Context], rax; Context
0x14010c4b6  mov     r8, rbx; NewMdl
0x14010c4b9  mov     rax, [rbp+3Fh+arg_30]
0x14010c4bd  mov     rcx, rdi; VirtualAddress
0x14010c4c0  mov     [rsp+0D0h+CopyFunction], rax; CopyFunction
0x14010c4c5  call    cs:__imp_MmRotatePhysicalView
0x14010c4cc  nop     dword ptr [rax+rax+00h]
0x14010c4d1  mov     r12d, eax
0x14010c4d4  mov     dword ptr [rbp+3Fh+arg_8], eax
0x14010c4d7  jmp     short loc_14010C4DD
0x14010c4d9  mov     rbx, [rbp+3Fh+NewMdl]
0x14010c4dd  test    r12d, r12d
0x14010c4e0  js      short loc_14010C506
0x14010c4e2  cmp     r13d, r15d
0x14010c4e5  jbe     short loc_14010C4FD
0x14010c4e7  dec     dword ptr [r14+60h]
0x14010c4eb  test    byte ptr [rbp+3Fh+arg_40], 2
0x14010c4f2  jz      loc_14010C63F
0x14010c4f8  jmp     loc_14010C65E
0x14010c4fd  add     [r14+60h], r15d
0x14010c501  jmp     loc_14010C65E
0x14010c506  cmp     r12d, 0C000010Ah
0x14010c50d  jnz     loc_14010C63F
0x14010c513  lea     eax, [r13-2]
0x14010c517  cmp     eax, r15d
0x14010c51a  ja      loc_14010C63F
0x14010c520  mov     eax, [rbx+28h]
0x14010c523  mov     rcx, r15
0x14010c526  mov     rbx, [rbx+30h]
0x14010c52a  shr     eax, 0Ch
0x14010c52d  mov     rdx, rbx
0x14010c530  mov     [rbp+3Fh+var_80], eax
0x14010c533  cmp     eax, r15d
0x14010c536  jbe     loc_14010C5DF
0x14010c53c  mov     r12, [rbp+3Fh+NewMdl]
0x14010c540  mov     r13d, ecx
0x14010c543  mov     r14d, eax
0x14010c546  mov     eax, r13d
0x14010c549  mov     r8, [r12+rax*8+30h]
0x14010c54e  lea     rax, [rdx+1]
0x14010c552  cmp     r8, rax
0x14010c555  jnz     short loc_14010C55C
0x14010c557  add     rcx, r15
0x14010c55a  jmp     short loc_14010C5C4
0x14010c55c  shl     rcx, 0Ch
0x14010c560  shl     rbx, 0Ch
0x14010c564  mov     rdx, rcx; NumberOfBytes
0x14010c567  mov     rdi, rbx
0x14010c56a  mov     qword ptr [rbp+3Fh+var_50], rcx
0x14010c56e  mov     rcx, rdi; StartAddress
0x14010c571  mov     rbx, r8
0x14010c574  call    cs:__imp_MmIsIoSpaceActive
0x14010c57b  nop     dword ptr [rax+rax+00h]
0x14010c580  test    eax, eax
0x14010c582  jz      short loc_14010C5BE
0x14010c584  mov     r14, qword ptr [rbp+3Fh+var_50]
0x14010c588  lea     r8, [rbp+3Fh+var_50]; Interval
0x14010c58c  mov     qword ptr [rbp+3Fh+var_50], 0FFFFFFFFFFFFD8F0h
0x14010c594  xor     edx, edx; Alertable
0x14010c596  xor     ecx, ecx; WaitMode
0x14010c598  call    cs:__imp_KeDelayExecutionThread
0x14010c59f  nop     dword ptr [rax+rax+00h]
0x14010c5a4  mov     rdx, r14; NumberOfBytes
0x14010c5a7  mov     rcx, rdi; StartAddress
0x14010c5aa  call    cs:__imp_MmIsIoSpaceActive
0x14010c5b1  nop     dword ptr [rax+rax+00h]
0x14010c5b6  test    eax, eax
0x14010c5b8  jnz     short loc_14010C588
0x14010c5ba  mov     r14d, [rbp+3Fh+var_80]
0x14010c5be  mov     r8, rbx
0x14010c5c1  mov     rcx, r15
0x14010c5c4  add     r13d, r15d
0x14010c5c7  mov     rdx, r8
0x14010c5ca  cmp     r13d, r14d
0x14010c5cd  jb      loc_14010C546
0x14010c5d3  mov     r14, qword ptr [rbp+3Fh+arg_0]
0x14010c5d7  mov     r12d, dword ptr [rbp+3Fh+arg_8]
0x14010c5db  mov     r13d, [rbp+3Fh+arg_10]
0x14010c5df  shl     rcx, 0Ch
  ... truncated ...
```
