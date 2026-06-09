# VIDMM_RECYCLE_MULTIRANGE::Rotate(VIDMM_GLOBAL *,_MM_ROTATE_DIRECTION,_MDL *,unsigned __int64,unsigned __int64,long (*)(_MDL *,_MDL *,void *),void *,VIDMM_ROTATE_FLAGS)

- ea: `0x140107ba4`
- end: `0x1401081b1`
- name: `?Rotate@VIDMM_RECYCLE_MULTIRANGE@@QEAAJPEAVVIDMM_GLOBAL@@W4_MM_ROTATE_DIRECTION@@PEAU_MDL@@_K3P6AJ22PEAX@Z4TVIDMM_ROTATE_FLAGS@@@Z`
- size: `1549`
- prototype: `__int64 __fastcall(union _LARGE_INTEGER, ULONG_PTR, enum _MM_ROTATE_DIRECTION, struct _MDL *, __int64, unsigned __int64, PMM_ROTATE_COPY_CALLBACK_FUNCTION CopyFunction, PVOID Context, char)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400c5280`

## callees

- `0x1400045ec`
- `0x140012e28`
- `0x1400ee814`
- `0x1400f1edc`
- `0x1400f26b8`
- `0x140107ba4`
- `0x1401081b8`
- `0x140111174`

## import_xrefs

- `ntoskrnl!MmSecureVirtualMemory` at `0x140107cfd`
- `ntoskrnl!MmSecureVirtualMemory` at `0x140107cfd`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x1401080fe`
- `ntoskrnl!MmUnsecureVirtualMemory` at `0x1401080fe`
- `ntoskrnl!KeDelayExecutionThread` at `0x140107e17`
- `ntoskrnl!KeDelayExecutionThread` at `0x140107f08`
- `ntoskrnl!KeDelayExecutionThread` at `0x140107f16`
- `ntoskrnl!KeDelayExecutionThread` at `0x140108048`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401080c5`
- `ntoskrnl!KeDelayExecutionThread` at `0x140107e17`
- `ntoskrnl!KeDelayExecutionThread` at `0x140107f08`
- `ntoskrnl!KeDelayExecutionThread` at `0x140107f16`
- `ntoskrnl!KeDelayExecutionThread` at `0x140108048`
- `ntoskrnl!KeDelayExecutionThread` at `0x1401080c5`
- `ntoskrnl!MmRotatePhysicalView` at `0x140107db0`
- `ntoskrnl!MmRotatePhysicalView` at `0x140107e6f`
- `ntoskrnl!MmRotatePhysicalView` at `0x140107ef0`
- `ntoskrnl!MmRotatePhysicalView` at `0x140107f75`
- `ntoskrnl!MmRotatePhysicalView` at `0x140107db0`
- `ntoskrnl!MmRotatePhysicalView` at `0x140107e6f`
- `ntoskrnl!MmRotatePhysicalView` at `0x140107ef0`
- `ntoskrnl!MmRotatePhysicalView` at `0x140107f75`
- `ntoskrnl!MmIsIoSpaceActive` at `0x140108024`
- `ntoskrnl!MmIsIoSpaceActive` at `0x14010805a`
- `ntoskrnl!MmIsIoSpaceActive` at `0x1401080a1`
- `ntoskrnl!MmIsIoSpaceActive` at `0x1401080d7`
- `ntoskrnl!MmIsIoSpaceActive` at `0x140108024`
- `ntoskrnl!MmIsIoSpaceActive` at `0x14010805a`
- `ntoskrnl!MmIsIoSpaceActive` at `0x1401080a1`
- `ntoskrnl!MmIsIoSpaceActive` at `0x1401080d7`
- `ntoskrnl!PsGetCurrentProcess` at `0x14010810e`
- `ntoskrnl!PsGetCurrentProcess` at `0x140108150`
- `ntoskrnl!PsGetCurrentProcess` at `0x14010810e`
- `ntoskrnl!PsGetCurrentProcess` at `0x140108150`
- `watchdog!WdLogSingleEntry3` at `0x140107c9f`
- `watchdog!WdLogSingleEntry3` at `0x140107c9f`
- `watchdog!WdLogSingleEntry5` at `0x140107c05`
- `watchdog!WdLogSingleEntry5` at `0x14010817d`
- `watchdog!WdLogSingleEntry5` at `0x140107c05`
- `watchdog!WdLogSingleEntry5` at `0x14010817d`
- `watchdog!WdLogSingleEntry0` at `0x140107d1d`
- `watchdog!WdLogSingleEntry0` at `0x140107dd2`
- `watchdog!WdLogSingleEntry0` at `0x140107e99`
- `watchdog!WdLogSingleEntry0` at `0x140107d1d`
- `watchdog!WdLogSingleEntry0` at `0x140107dd2`
- `watchdog!WdLogSingleEntry0` at `0x140107e99`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x140107bdd`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14010815c`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 __fastcall VIDMM_RECYCLE_MULTIRANGE::Rotate(
        union _LARGE_INTEGER a1,
        ULONG_PTR a2,
        enum _MM_ROTATE_DIRECTION a3,
        struct _MDL *a4,
        __int64 a5,
        unsigned __int64 a6,
        PMM_ROTATE_COPY_CALLBACK_FUNCTION CopyFunction,
        PVOID Context,
        char a9)
{
  union _LARGE_INTEGER v9; // r14
  enum _MM_ROTATE_DIRECTION v10; // r13d
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
  void *v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // r8
  int v26; // ebx
  NTSTATUS v27; // eax
  __int64 v28; // rcx
  __int64 v29; // r8
  PVOID v30; // r14
  NTSTATUS (__stdcall *v31)(PMDL, PMDL, PVOID); // r13
  struct _MDL *v32; // rbx
  PMDL v33; // rbx
  ULONG ByteCount; // eax
  __int64 v35; // rcx
  struct _MDL *Next; // rbx
  unsigned int v37; // eax
  struct _MDL *v38; // rdx
  PMDL v39; // r12
  unsigned int v40; // r13d
  unsigned int v41; // r14d
  struct _MDL *v42; // r8
  SIZE_T v43; // rdx
  PHYSICAL_ADDRESS v44; // rdi
  PHYSICAL_ADDRESS v45; // rcx
  union _LARGE_INTEGER v46; // r14
  PHYSICAL_ADDRESS v47; // rbx
  union _LARGE_INTEGER v48; // rdi
  struct _EPROCESS *CurrentProcess; // rax
  __int64 v50; // rcx
  int v51; // [rsp+58h] [rbp-41h]
  unsigned int v52; // [rsp+58h] [rbp-41h]
  union _LARGE_INTEGER v53; // [rsp+60h] [rbp-39h] BYREF
  ULONG_PTR NumberOfBytes[2]; // [rsp+68h] [rbp-31h] BYREF
  char *v55; // [rsp+78h] [rbp-21h]
  union _LARGE_INTEGER Interval; // [rsp+80h] [rbp-19h] BYREF
  union _LARGE_INTEGER v57; // [rsp+88h] [rbp-11h] BYREF
  union _LARGE_INTEGER v58; // [rsp+E8h] [rbp+4Fh] BYREF
  ULONG_PTR v59; // [rsp+F0h] [rbp+57h] BYREF
  enum _MM_ROTATE_DIRECTION v60; // [rsp+F8h] [rbp+5Fh]
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
    WdLogSingleEntry5(0, 270, 52);
    WdLogGlobalForLineNumber = 222;
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
    if ( (unsigned int)v10 >= MmToRegularMemory )
    {
      v50 = (unsigned int)(v10 - 2);
      if ( (unsigned int)v50 > 1 )
        return (unsigned int)v12;
      PsGetCurrentProcess(v50);
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(0, 270, 1);
      WdLogGlobalForLineNumber = 222;
    }
    return (unsigned int)-1073741823;
  }
  v16 = *(_QWORD *)(v9.QuadPart + 48);
  if ( (unsigned int)v10 <= MmToFrameBufferNoCopy && !*(_QWORD *)(v9.QuadPart + 120) )
  {
    v17 = MmSecureVirtualMemory(*(PVOID *)(v9.QuadPart + 48), *(_QWORD *)(v9.QuadPart + 40) - v16, 4u);
    *(_QWORD *)(v9.QuadPart + 120) = v17;
    if ( !v17 )
    {
      _InterlockedAdd(&dword_1400867A8, 1u);
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
  if ( v10 == MmToRegularMemory )
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
      if ( (byte_140086201 & 1) != 0 )
        McTemplateK0q_EtwWriteTransfer(v24, EventPerformanceWarning, v25, 12);
      v21 += NumberOfBytes[0];
      v22 -= NumberOfBytes[0];
      v55 = v21;
      KeDelayExecutionThread(0, 0, &Interval);
    }
LABEL_37:
    v33 = NewMdl;
    goto LABEL_38;
  }
  if ( v10 == MmToRegularMemoryNoCopy )
  {
    v53.QuadPart = -10000;
    v26 = a9 & 1;
    v51 = v26;
    NumberOfBytes[0] = a6;
    while ( 1 )
    {
      v27 = MmRotatePhysicalView(v21, NumberOfBytes, 0, MmToRegularMemoryNoCopy, CopyFunction, Context);
      LODWORD(v59) = v27;
      v12 = v27;
      if ( !v26 || v27 != 1073741849 )
        break;
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 3561;
      if ( (byte_140086201 & 1) != 0 )
        McTemplateK0q_EtwWriteTransfer(v28, EventPerformanceWarning, v29, 12);
      v30 = Context;
      v31 = CopyFunction;
      v32 = NewMdl;
      while ( MmRotatePhysicalView(v21, NumberOfBytes, v32, MmToFrameBufferNoCopy, v31, v30) < 0 )
        KeDelayExecutionThread(0, 0, &v53);
      KeDelayExecutionThread(0, 0, &v53);
      v9 = v58;
      v10 = v60;
      v26 = v51;
    }
    goto LABEL_37;
  }
  v59 = a6;
  if ( g_bInjectRotateFailure )
  {
    v12 = -1073741823;
    goto LABEL_60;
  }
  v33 = NewMdl;
  v12 = MmRotatePhysicalView(v21, &v59, NewMdl, v10, CopyFunction, Context);
  LODWORD(v59) = v12;
LABEL_38:
  if ( v12 < 0 )
  {
    if ( v12 == -1073741558 && (unsigned int)(v10 - 2) <= 1 )
    {
      ByteCount = v33->ByteCount;
      v35 = 1;
      Next = v33[1].Next;
      v37 = ByteCount >> 12;
      v38 = Next;
      v52 = v37;
      if ( v37 > 1 )
      {
        v39 = NewMdl;
        v40 = 1;
        v41 = v37;
        do
        {
          v42 = (struct _MDL *)*((_QWORD *)&v39[1].Next + v40);
          if ( v42 == (struct _MDL *)((char *)&v38->Next + 1) )
          {
            ++v35;
          }
          else
          {
            v43 = v35 << 12;
            v44.QuadPart = (_QWORD)Next << 12;
            v57.QuadPart = v35 << 12;
            v45.QuadPart = (_QWORD)Next << 12;
            Next = v42;
            if ( MmIsIoSpaceActive(v45, v43) )
            {
              v46 = v57;
              do
              {
                v57.QuadPart = -10000;
                KeDelayExecutionThread(0, 0, &v57);
              }
              while ( MmIsIoSpaceActive(v44, v46.QuadPart) );
              v41 = v52;
            }
            v42 = Next;
            v35 = 1;
          }
          ++v40;
          v38 = v42;
        }
        while ( v40 < v41 );
        v9 = v58;
        v12 = v59;
        v10 = v60;
      }
      v53.QuadPart = v35 << 12;
      v47.QuadPart = (_QWORD)Next << 12;
      if ( MmIsIoSpaceActive(v47, v35 << 12) )
      {
        v48 = v53;
        do
        {
          v58.QuadPart = -10000;
          KeDelayExecutionThread(0, 0, &v58);
        }
        while ( MmIsIoSpaceActive(v47, v48.QuadPart) );
      }
      --*(_DWORD *)(v9.QuadPart + 96);
      v21 = v55;
    }
    goto LABEL_60;
  }
  if ( (unsigned int)v10 > MmToFrameBufferNoCopy )
  {
    --*(_DWORD *)(v9.QuadPart + 96);
    if ( (a9 & 2) != 0 )
      goto LABEL_63;
LABEL_60:
    v23 = *(void **)(v9.QuadPart + 120);
    if ( v23 && !*(_DWORD *)(v9.QuadPart + 96) )
    {
      MmUnsecureVirtualMemory(v23);
      *(_QWORD *)(v9.QuadPart + 120) = 0;
    }
    goto LABEL_63;
  }
  ++*(_DWORD *)(v9.QuadPart + 96);
LABEL_63:
  CurrentProcess = (struct _EPROCESS *)PsGetCurrentProcess(v23);
  VIDMM_GLOBAL::RecordRotation(CurrentProcess, v21, a6, NewMdl, v10, v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140107ba4  mov     rax, rsp
0x140107ba7  mov     [rax+20h], r9
0x140107bab  mov     [rax+18h], r8d
0x140107baf  mov     [rax+10h], rdx
0x140107bb3  mov     [rax+8], rcx
0x140107bb7  push    rbp
0x140107bb8  push    rbx
0x140107bb9  push    rsi
0x140107bba  push    rdi
0x140107bbb  push    r12
0x140107bbd  push    r13
0x140107bbf  push    r14
0x140107bc1  push    r15
0x140107bc3  lea     rbp, [rax-47h]
0x140107bc7  sub     rsp, 98h
0x140107bce  cmp     dword ptr [rcx+90h], 4
0x140107bd5  mov     r14, rcx
0x140107bd8  movsxd  r13, r8d
0x140107bdb  jnz     short loc_140107C1B
0x140107bdd  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x140107be4  mov     dword ptr [rax], 1
0x140107bea  xor     esi, esi
0x140107bec  mov     edx, 10Eh
0x140107bf1  mov     [rsp+0D0h+Context], rsi
0x140107bf6  xor     ecx, ecx
0x140107bf8  mov     [rsp+0D0h+CopyFunction], r13
0x140107bfd  lea     r9d, [rsi+0Bh]
0x140107c01  lea     r8d, [rsi+34h]
0x140107c05  call    cs:__imp_WdLogSingleEntry5
0x140107c0c  nop     dword ptr [rax+rax+00h]
0x140107c11  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x140107c1b  mov     rbx, [rcx+40h]
0x140107c1f  xor     esi, esi
0x140107c21  mov     r12d, esi
0x140107c24  mov     dil, sil
0x140107c27  lea     r15d, [rsi+1]
0x140107c2b  test    dil, dil
0x140107c2e  jnz     loc_140107CCE
0x140107c34  cmp     dword ptr [rbx+40h], 3
0x140107c38  jnz     short loc_140107C59
0x140107c3a  mov     rdx, rbx; struct VIDMM_RECYCLE_RANGE *
0x140107c3d  call    ?RemoveFromDebounce@VIDMM_RECYCLE_HEAP_MGR@@QEAAXPEAVVIDMM_RECYCLE_RANGE@@@Z; VIDMM_RECYCLE_HEAP_MGR::RemoveFromDebounce(VIDMM_RECYCLE_RANGE *)
0x140107c42  lea     rdx, [rbp+3Fh+arg_8]; bool *
0x140107c46  mov     byte ptr [rbp+3Fh+arg_8], sil
0x140107c4a  mov     rcx, rbx; this
0x140107c4d  call    ?DebouncedUnlock@VIDMM_RECYCLE_RANGE@@QEAAJAEA_N@Z; VIDMM_RECYCLE_RANGE::DebouncedUnlock(bool &)
0x140107c52  mov     r12d, eax
0x140107c55  test    eax, eax
0x140107c57  js      short loc_140107C80
0x140107c59  cmp     rbx, [r14+48h]
0x140107c5d  jnz     short loc_140107C64
0x140107c5f  mov     dil, r15b
0x140107c62  jmp     short loc_140107C2B
0x140107c64  mov     rdx, [rbx+78h]
0x140107c68  mov     rcx, [rbx+48h]
0x140107c6c  mov     rbx, rsi
0x140107c6f  add     rcx, 48h ; 'H'
0x140107c73  cmp     rdx, rcx
0x140107c76  lea     rax, [rdx-78h]
0x140107c7a  cmovnz  rbx, rax
0x140107c7e  jmp     short loc_140107C2B
0x140107c80  mov     rax, [r14+50h]
0x140107c84  mov     rdx, rbx
0x140107c87  mov     ecx, 3
0x140107c8c  mov     r8, [rax+20h]
0x140107c90  mov     rax, [r8+8]
0x140107c94  mov     r8, r14
0x140107c97  mov     r9, [rax+8]
0x140107c9b  mov     r9, [r9+10h]
0x140107c9f  call    cs:__imp_WdLogSingleEntry3
0x140107ca6  nop     dword ptr [rax+rax+00h]
0x140107cab  mov     cs:WdLogGlobalForLineNumber, 0D36h
0x140107cb5  mov     rdx, rbx; struct VIDMM_RECYCLE_RANGE *
0x140107cb8  mov     rax, [r14+50h]
0x140107cbc  mov     rcx, [rax+20h]
0x140107cc0  mov     rcx, [rcx+8]; this
0x140107cc4  call    ?AddToUnlockDebounce@VIDMM_RECYCLE_HEAP_MGR@@QEAAXPEAVVIDMM_RECYCLE_RANGE@@@Z; VIDMM_RECYCLE_HEAP_MGR::AddToUnlockDebounce(VIDMM_RECYCLE_RANGE *)
0x140107cc9  jmp     loc_140108199
0x140107cce  mov     rcx, r14; this
0x140107cd1  call    ?IsRotateVAD@VIDMM_RECYCLE_MULTIRANGE@@QEAAEXZ; VIDMM_RECYCLE_MULTIRANGE::IsRotateVAD(void)
0x140107cd6  test    al, al
0x140107cd8  jz      loc_140108139
0x140107cde  mov     rbx, [r14+30h]
0x140107ce2  cmp     r13d, r15d
0x140107ce5  ja      short loc_140107D63
0x140107ce7  cmp     [r14+78h], rsi
0x140107ceb  jnz     short loc_140107D63
0x140107ced  mov     rdx, [r14+28h]
0x140107cf1  mov     r8d, 4; ProbeMode
0x140107cf7  sub     rdx, rbx; Size
0x140107cfa  mov     rcx, rbx; Address
0x140107cfd  call    cs:__imp_MmSecureVirtualMemory
0x140107d04  nop     dword ptr [rax+rax+00h]
0x140107d09  mov     [r14+78h], rax
0x140107d0d  test    rax, rax
0x140107d10  jnz     short loc_140107D63
0x140107d12  lock add cs:dword_1400867A8, r15d
0x140107d1a  lea     ecx, [rax+6]
0x140107d1d  call    cs:__imp_WdLogSingleEntry0
0x140107d24  nop     dword ptr [rax+rax+00h]
0x140107d29  mov     [rsp+38h], rsi
0x140107d2e  lea     r9, aCouldnTSecureT; "Couldn't secure the virtual memory rang"...
0x140107d35  mov     eax, 0D71h
0x140107d3a  mov     [rsp+0D0h+var_A0], rsi
0x140107d3f  mov     [rsp+0D0h+Context], rsi
0x140107d44  mov     edx, 40001h
0x140107d49  mov     cs:WdLogGlobalForLineNumber, eax
0x140107d4f  mov     [rsp+0D0h+CopyFunction], rax
0x140107d54  call    DxgkLogInternalTriageEvent
0x140107d59  mov     eax, 0C0000017h
0x140107d5e  jmp     loc_14010819C
0x140107d63  mov     rdi, [rbp+3Fh+arg_20]
0x140107d67  mov     rax, 0FFFFFFFFFFFFD8F0h
0x140107d6e  add     rdi, rbx
0x140107d71  mov     [rbp+3Fh+var_60], rdi
0x140107d75  cmp     r13d, 2
0x140107d79  jnz     loc_140107E28
0x140107d7f  mov     rbx, [rbp+3Fh+arg_28]
0x140107d83  mov     qword ptr [rbp+3Fh+Interval], rax
0x140107d87  mov     rax, [rbp+3Fh+arg_38]
0x140107d8e  lea     rdx, [rbp+3Fh+NumberOfBytes]; NumberOfBytes
0x140107d92  mov     [rsp+0D0h+Context], rax; Context
0x140107d97  mov     r9d, 2; Direction
0x140107d9d  mov     rax, [rbp+3Fh+arg_30]
0x140107da1  xor     r8d, r8d; NewMdl
0x140107da4  mov     rcx, rdi; VirtualAddress
0x140107da7  mov     [rsp+0D0h+CopyFunction], rax; CopyFunction
0x140107dac  mov     [rbp+3Fh+NumberOfBytes], rbx
0x140107db0  call    cs:__imp_MmRotatePhysicalView
0x140107db7  nop     dword ptr [rax+rax+00h]
0x140107dbc  mov     dword ptr [rbp+3Fh+arg_8], eax
0x140107dbf  mov     r12d, eax
0x140107dc2  cmp     eax, 40000019h
0x140107dc7  jnz     loc_140107F89
0x140107dcd  mov     ecx, 3
0x140107dd2  call    cs:__imp_WdLogSingleEntry0
0x140107dd9  nop     dword ptr [rax+rax+00h]
0x140107dde  test    cs:byte_140086201, r15b
0x140107de5  mov     cs:WdLogGlobalForLineNumber, 0DA8h
0x140107def  jz      short loc_140107E03
0x140107df1  mov     r9d, 0Ch
0x140107df7  lea     rdx, EventPerformanceWarning
0x140107dfe  call    McTemplateK0q_EtwWriteTransfer
0x140107e03  add     rdi, [rbp+3Fh+NumberOfBytes]
0x140107e07  lea     r8, [rbp+3Fh+Interval]; Interval
0x140107e0b  sub     rbx, [rbp+3Fh+NumberOfBytes]
0x140107e0f  xor     edx, edx; Alertable
0x140107e11  xor     ecx, ecx; WaitMode
0x140107e13  mov     [rbp+3Fh+var_60], rdi
0x140107e17  call    cs:__imp_KeDelayExecutionThread
0x140107e1e  nop     dword ptr [rax+rax+00h]
0x140107e23  jmp     loc_140107D87
0x140107e28  cmp     r13d, 3
0x140107e2c  jnz     loc_140107F32
0x140107e32  mov     ebx, [rbp+3Fh+arg_40]
0x140107e38  mov     qword ptr [rbp+3Fh+var_78], rax
0x140107e3c  and     ebx, r15d
0x140107e3f  mov     rax, [rbp+3Fh+arg_28]
0x140107e43  mov     [rbp+3Fh+var_80], ebx
0x140107e46  mov     [rbp+3Fh+NumberOfBytes], rax
0x140107e4a  mov     rax, [rbp+3Fh+arg_38]
0x140107e51  lea     rdx, [rbp+3Fh+NumberOfBytes]; NumberOfBytes
0x140107e55  mov     [rsp+0D0h+Context], rax; Context
0x140107e5a  mov     r9d, 3; Direction
0x140107e60  mov     rax, [rbp+3Fh+arg_30]
0x140107e64  xor     r8d, r8d; NewMdl
0x140107e67  mov     rcx, rdi; VirtualAddress
0x140107e6a  mov     [rsp+0D0h+CopyFunction], rax; CopyFunction
0x140107e6f  call    cs:__imp_MmRotatePhysicalView
0x140107e76  nop     dword ptr [rax+rax+00h]
0x140107e7b  mov     dword ptr [rbp+3Fh+arg_8], eax
0x140107e7e  mov     r12d, eax
0x140107e81  test    ebx, ebx
0x140107e83  jz      loc_140107F89
0x140107e89  cmp     eax, 40000019h
0x140107e8e  jnz     loc_140107F89
0x140107e94  mov     ecx, 3
0x140107e99  call    cs:__imp_WdLogSingleEntry0
0x140107ea0  nop     dword ptr [rax+rax+00h]
0x140107ea5  test    cs:byte_140086201, r15b
0x140107eac  mov     cs:WdLogGlobalForLineNumber, 0DE9h
0x140107eb6  jz      short loc_140107ECA
0x140107eb8  mov     r9d, 0Ch
0x140107ebe  lea     rdx, EventPerformanceWarning
0x140107ec5  call    McTemplateK0q_EtwWriteTransfer
0x140107eca  mov     r14, [rbp+3Fh+arg_38]
0x140107ed1  mov     r13, [rbp+3Fh+arg_30]
0x140107ed5  mov     rbx, [rbp+3Fh+NewMdl]
0x140107ed9  mov     [rsp+0D0h+Context], r14; Context
0x140107ede  lea     rdx, [rbp+3Fh+NumberOfBytes]; NumberOfBytes
0x140107ee2  mov     r9d, r15d; Direction
0x140107ee5  mov     [rsp+0D0h+CopyFunction], r13; CopyFunction
0x140107eea  mov     r8, rbx; NewMdl
0x140107eed  mov     rcx, rdi; VirtualAddress
0x140107ef0  call    cs:__imp_MmRotatePhysicalView
0x140107ef7  nop     dword ptr [rax+rax+00h]
0x140107efc  xor     edx, edx; Alertable
0x140107efe  lea     r8, [rbp+3Fh+var_78]; Interval
0x140107f02  xor     ecx, ecx; WaitMode
0x140107f04  test    eax, eax
0x140107f06  jns     short loc_140107F16
0x140107f08  call    cs:__imp_KeDelayExecutionThread
0x140107f0f  nop     dword ptr [rax+rax+00h]
0x140107f14  jmp     short loc_140107ED9
0x140107f16  call    cs:__imp_KeDelayExecutionThread
0x140107f1d  nop     dword ptr [rax+rax+00h]
0x140107f22  mov     r14, qword ptr [rbp+3Fh+arg_0]
0x140107f26  mov     r13d, [rbp+3Fh+arg_10]
0x140107f2a  mov     ebx, [rbp+3Fh+var_80]
0x140107f2d  jmp     loc_140107E4A
0x140107f32  mov     rax, [rbp+3Fh+arg_28]
0x140107f36  mov     [rbp+3Fh+arg_8], rax
0x140107f3a  mov     al, cs:?g_bInjectRotateFailure@@3_NC; bool volatile g_bInjectRotateFailure
0x140107f40  test    al, al
0x140107f42  jz      short loc_140107F4F
0x140107f44  mov     r12d, 0C0000001h
0x140107f4a  jmp     loc_1401080EF
0x140107f4f  mov     rax, [rbp+3Fh+arg_38]
0x140107f56  lea     rdx, [rbp+3Fh+arg_8]; NumberOfBytes
0x140107f5a  mov     rbx, [rbp+3Fh+NewMdl]
0x140107f5e  mov     r9d, r13d; Direction
0x140107f61  mov     [rsp+0D0h+Context], rax; Context
0x140107f66  mov     r8, rbx; NewMdl
0x140107f69  mov     rax, [rbp+3Fh+arg_30]
0x140107f6d  mov     rcx, rdi; VirtualAddress
0x140107f70  mov     [rsp+0D0h+CopyFunction], rax; CopyFunction
0x140107f75  call    cs:__imp_MmRotatePhysicalView
0x140107f7c  nop     dword ptr [rax+rax+00h]
0x140107f81  mov     r12d, eax
0x140107f84  mov     dword ptr [rbp+3Fh+arg_8], eax
0x140107f87  jmp     short loc_140107F8D
0x140107f89  mov     rbx, [rbp+3Fh+NewMdl]
0x140107f8d  test    r12d, r12d
0x140107f90  js      short loc_140107FB6
0x140107f92  cmp     r13d, r15d
0x140107f95  jbe     short loc_140107FAD
0x140107f97  dec     dword ptr [r14+60h]
0x140107f9b  test    byte ptr [rbp+3Fh+arg_40], 2
0x140107fa2  jz      loc_1401080EF
0x140107fa8  jmp     loc_14010810E
0x140107fad  add     [r14+60h], r15d
0x140107fb1  jmp     loc_14010810E
0x140107fb6  cmp     r12d, 0C000010Ah
0x140107fbd  jnz     loc_1401080EF
0x140107fc3  lea     eax, [r13-2]
0x140107fc7  cmp     eax, r15d
0x140107fca  ja      loc_1401080EF
0x140107fd0  mov     eax, [rbx+28h]
0x140107fd3  mov     rcx, r15
0x140107fd6  mov     rbx, [rbx+30h]
0x140107fda  shr     eax, 0Ch
0x140107fdd  mov     rdx, rbx
0x140107fe0  mov     [rbp+3Fh+var_80], eax
0x140107fe3  cmp     eax, r15d
0x140107fe6  jbe     loc_14010808F
0x140107fec  mov     r12, [rbp+3Fh+NewMdl]
0x140107ff0  mov     r13d, ecx
0x140107ff3  mov     r14d, eax
0x140107ff6  mov     eax, r13d
0x140107ff9  mov     r8, [r12+rax*8+30h]
0x140107ffe  lea     rax, [rdx+1]
0x140108002  cmp     r8, rax
0x140108005  jnz     short loc_14010800C
0x140108007  add     rcx, r15
0x14010800a  jmp     short loc_140108074
0x14010800c  shl     rcx, 0Ch
0x140108010  shl     rbx, 0Ch
0x140108014  mov     rdx, rcx; NumberOfBytes
0x140108017  mov     rdi, rbx
0x14010801a  mov     qword ptr [rbp+3Fh+var_50], rcx
0x14010801e  mov     rcx, rdi; StartAddress
0x140108021  mov     rbx, r8
0x140108024  call    cs:__imp_MmIsIoSpaceActive
0x14010802b  nop     dword ptr [rax+rax+00h]
0x140108030  test    eax, eax
0x140108032  jz      short loc_14010806E
0x140108034  mov     r14, qword ptr [rbp+3Fh+var_50]
0x140108038  lea     r8, [rbp+3Fh+var_50]; Interval
0x14010803c  mov     qword ptr [rbp+3Fh+var_50], 0FFFFFFFFFFFFD8F0h
0x140108044  xor     edx, edx; Alertable
0x140108046  xor     ecx, ecx; WaitMode
0x140108048  call    cs:__imp_KeDelayExecutionThread
0x14010804f  nop     dword ptr [rax+rax+00h]
0x140108054  mov     rdx, r14; NumberOfBytes
0x140108057  mov     rcx, rdi; StartAddress
0x14010805a  call    cs:__imp_MmIsIoSpaceActive
0x140108061  nop     dword ptr [rax+rax+00h]
0x140108066  test    eax, eax
0x140108068  jnz     short loc_140108038
0x14010806a  mov     r14d, [rbp+3Fh+var_80]
0x14010806e  mov     r8, rbx
0x140108071  mov     rcx, r15
0x140108074  add     r13d, r15d
0x140108077  mov     rdx, r8
0x14010807a  cmp     r13d, r14d
0x14010807d  jb      loc_140107FF6
0x140108083  mov     r14, qword ptr [rbp+3Fh+arg_0]
0x140108087  mov     r12d, dword ptr [rbp+3Fh+arg_8]
0x14010808b  mov     r13d, [rbp+3Fh+arg_10]
0x14010808f  shl     rcx, 0Ch
  ... truncated ...
```
