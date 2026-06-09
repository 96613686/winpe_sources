# VIDMM_PROCESS_HEAP::AllocateGlobal(VIDMM_GLOBAL_ALLOC *,unsigned __int64,uint,VIDMM_HEAP_ALLOCATE_FLAGS,void *,VIDMM_PROCESS_HEAP_MAPPING,VIDMM_HEAP_ALLOC * *,void * *,uchar *)

- ea: `0x1400ae640`
- end: `0x1400aed8d`
- name: `?AllocateGlobal@VIDMM_PROCESS_HEAP@@UEAAJPEAUVIDMM_GLOBAL_ALLOC@@_KIW4VIDMM_HEAP_ALLOCATE_FLAGS@@PEAXW4VIDMM_PROCESS_HEAP_MAPPING@@PEAPEAUVIDMM_HEAP_ALLOC@@PEAPEAXPEAE@Z`
- size: `1869`
- prototype: `__int64 __fastcall(__int64, __int64, SIZE_T, unsigned int, int, __int64, int, _QWORD *, PVOID *, _BYTE *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1400045ec`
- `0x140012e28`
- `0x140013434`
- `0x140030fa0`
- `0x14003142c`
- `0x140031934`
- `0x14003bbcc`
- `0x140058760`
- `0x140058ac0`
- `0x1400ae640`
- `0x1400aed94`
- `0x1400f70b4`

## import_xrefs

- `ntoskrnl!MmSecureVirtualMemory` at `0x1400ae90a`
- `ntoskrnl!MmSecureVirtualMemory` at `0x1400ae90a`
- `ntoskrnl!ObfReferenceObject` at `0x1400aea17`
- `ntoskrnl!ObfReferenceObject` at `0x1400aea17`
- `ntoskrnl!ObfDereferenceObject` at `0x1400aeb92`
- `ntoskrnl!ObfDereferenceObject` at `0x1400aeb92`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x1400aeb58`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x1400aeb58`
- `ntoskrnl!MmCreateSection` at `0x1400ae9ba`
- `ntoskrnl!MmCreateSection` at `0x1400ae9ba`
- `ntoskrnl!ObCloseHandle` at `0x1400aeb82`
- `ntoskrnl!ObCloseHandle` at `0x1400aeb82`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400ae7d3`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400ae7d3`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400aeba9`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400aeba9`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x1400aeab0`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x1400aeab0`
- `ntoskrnl!ObInsertObject` at `0x1400aea3d`
- `ntoskrnl!ObInsertObject` at `0x1400aea3d`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400ae701`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400ae701`
- `watchdog!WdLogSingleEntry2` at `0x1400aea5c`
- `watchdog!WdLogSingleEntry2` at `0x1400aea5c`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400ae6d3`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400ae6d3`
- `watchdog!WdLogSingleEntry5` at `0x1400ae737`
- `watchdog!WdLogSingleEntry5` at `0x1400ae737`
- `watchdog!WdLogSingleEntry0` at `0x1400ae7f9`
- `watchdog!WdLogSingleEntry0` at `0x1400ae8e0`
- `watchdog!WdLogSingleEntry0` at `0x1400ae931`
- `watchdog!WdLogSingleEntry0` at `0x1400ae9dc`
- `watchdog!WdLogSingleEntry0` at `0x1400ae7f9`
- `watchdog!WdLogSingleEntry0` at `0x1400ae8e0`
- `watchdog!WdLogSingleEntry0` at `0x1400ae931`
- `watchdog!WdLogSingleEntry0` at `0x1400ae9dc`
- `watchdog!WdLogSingleEntry1` at `0x1400aead6`
- `watchdog!WdLogSingleEntry1` at `0x1400aead6`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400ae712`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400ae6b7`

## string_xrefs

- `0x1400ae8f1`: `Couldn't commit virtual memory\n`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 __fastcall VIDMM_PROCESS_HEAP::AllocateGlobal(
        __int64 a1,
        __int64 a2,
        SIZE_T a3,
        unsigned int a4,
        int a5,
        __int64 a6,
        int a7,
        _QWORD *a8,
        PVOID *a9,
        _BYTE *a10)
{
  __int64 v10; // rdi
  bool v12; // zf
  bool v13; // si
  _QWORD *v14; // rax
  __int64 v15; // rbx
  _QWORD *v16; // r8
  int v17; // ebx
  PVOID *v18; // rcx
  _BYTE *v19; // r9
  SIZE_T v20; // rdx
  unsigned int SmallAllocation; // ebx
  __int64 v22; // rcx
  __int64 v23; // r8
  struct _PAGED_LOOKASIDE_LIST *v25; // r13
  _DWORD *v26; // rax
  int v27; // esi
  _DWORD *v28; // r15
  __int64 v29; // rdi
  int v30; // ecx
  int v31; // r8d
  const wchar_t *v32; // r9
  unsigned int v33; // edi
  unsigned int v34; // r13d
  int v35; // eax
  int v36; // ecx
  int v37; // r8d
  __int64 v38; // rax
  const wchar_t *v39; // r9
  HANDLE v40; // rcx
  int v41; // r8d
  int v42; // ecx
  NTSTATUS inserted; // eax
  int v44; // ecx
  int v45; // r8d
  NTSTATUS v46; // eax
  const struct DXGK_VIRTUAL_MEMORY_INTERFACE *VirtualMemoryInterface; // rax
  PVOID v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // r8
  _QWORD *v51; // rax
  _QWORD *v52; // rcx
  int v53; // r9d
  int v54; // ecx
  __int64 v55; // rcx
  __int64 v56; // r8
  PVOID *NewObject; // [rsp+20h] [rbp-60h]
  __int64 NewObjecta; // [rsp+20h] [rbp-60h]
  int Handle; // [rsp+28h] [rbp-58h]
  _BYTE *v60; // [rsp+38h] [rbp-48h]
  PVOID Object; // [rsp+50h] [rbp-30h] BYREF
  HANDLE v62; // [rsp+58h] [rbp-28h] BYREF
  PPAGED_LOOKASIDE_LIST Lookaside; // [rsp+60h] [rbp-20h] BYREF
  unsigned int v64; // [rsp+68h] [rbp-18h] BYREF
  __int64 v65; // [rsp+70h] [rbp-10h]
  char v66; // [rsp+78h] [rbp-8h]
  PVOID Address; // [rsp+B0h] [rbp+30h] BYREF
  SIZE_T Size; // [rsp+C0h] [rbp+40h] BYREF

  Size = a3;
  v10 = a4;
  v64 = -1;
  v65 = 0;
  if ( (qword_140086010 & 2) != 0 )
  {
    v66 = 1;
    v64 = 8004;
    if ( (byte_140086202 & 1) != 0 )
      McTemplateK0q_EtwWriteTransfer(a1, EventProfilerEnter, a3, 8004);
  }
  else
  {
    v66 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v64, 8004);
  v12 = (a5 & 4) == 0;
  a5 &= 4u;
  Address = 0;
  v13 = !v12;
  Object = 0;
  v62 = 0;
  if ( g_IsInternalReleaseOrDbg )
  {
    v14 = (_QWORD *)WdLogNewEntry5_WdTrace();
    v14[3] = Size;
    v14[4] = v10;
    v14[5] = a1;
    WdLogGlobalForLineNumber = 295;
  }
  v15 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL);
  if ( PsGetCurrentProcess() != v15 )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    HIDWORD(NewObject) = 0;
    WdLogSingleEntry5(0, 270, 30);
    WdLogGlobalForLineNumber = 222;
  }
  v16 = a8;
  v17 = 0;
  v18 = a9;
  v19 = a10;
  v20 = Size;
  *a8 = 0;
  *v18 = 0;
  *v19 = 0;
  if ( v20 < (unsigned int)dword_140086458 )
  {
    v60 = v19;
    LOBYTE(v19) = v13;
    LODWORD(NewObject) = a7;
    SmallAllocation = VIDMM_PROCESS_HEAP::AllocateSmallAllocation(
                        a1,
                        v20,
                        (unsigned int)v10,
                        v19,
                        NewObject,
                        v16,
                        v18,
                        v60);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v64);
    if ( v66 )
    {
      if ( (byte_140086202 & 1) != 0 )
        McTemplateK0q_EtwWriteTransfer(v22, EventProfilerExit, v23, v64);
    }
    return SmallAllocation;
  }
  v25 = (struct _PAGED_LOOKASIDE_LIST *)(a1 + 64);
  Lookaside = (PPAGED_LOOKASIDE_LIST)(a1 + 64);
  v26 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 64));
  v27 = a7;
  v28 = v26;
  if ( !v26 )
  {
    LODWORD(v29) = -1073741801;
    _InterlockedIncrement(&dword_140086704);
    WdLogSingleEntry0(6);
    v32 = L"Couldn't allocate memory for VIDMM_PROCESS_HEAP_ALLOC structure.\n";
    WdLogGlobalForLineNumber = 332;
    NewObjecta = 332;
LABEL_42:
    DxgkLogInternalTriageEvent(v30, 262145, v31, (_DWORD)v32, NewObjecta, 0, 0, 0);
    goto LABEL_43;
  }
  memset(v26, 0, 0x60u);
  switch ( v27 )
  {
    case 3:
      goto LABEL_34;
    case 4:
LABEL_33:
      v42 = 134479872;
LABEL_35:
      Handle = *(_DWORD *)(a1 + 288) | v42;
      Lookaside = (PPAGED_LOOKASIDE_LIST)Size;
      LODWORD(v29) = MmCreateSection(&Object, 0, 0, &Lookaside, 4, Handle, -1, 0);
      if ( (int)v29 < 0 )
      {
        Object = 0;
        _InterlockedIncrement(&dword_1400867D0);
        WdLogSingleEntry0(6);
        v32 = L"Couldn't allocate a backing section for a large allocation";
        WdLogGlobalForLineNumber = 374;
        NewObjecta = 374;
        goto LABEL_42;
      }
      ObfReferenceObject(Object);
      inserted = ObInsertObject(Object, 0, 0, 0, 0, &v62);
      v29 = inserted;
      if ( inserted < 0 )
      {
        WdLogSingleEntry2(1, Object, inserted);
        WdLogGlobalForLineNumber = 394;
        DxgkLogInternalTriageEvent(
          v44,
          0x40000,
          v45,
          (unsigned int)L"Unable to insert section object 0x%I64p into handle table, Status = 0x%I64p",
          (__int64)Object,
          v29,
          0,
          0);
LABEL_43:
        if ( v27 != 3 && v27 != 4 )
        {
          if ( v27 != 5 && v27 != 6 )
          {
LABEL_47:
            if ( Address )
            {
              VirtualMemoryInterface = DxgkGetVirtualMemoryInterface();
              (*((void (__fastcall **)(__int64, PVOID *, SIZE_T *, __int64))VirtualMemoryInterface + 2))(
                -1,
                &Address,
                &Size,
                0x8000);
            }
LABEL_55:
            if ( v28 )
              ExFreeToPagedLookasideList(v25, v28);
            DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v64);
            if ( v66 && (byte_140086202 & 1) != 0 )
              McTemplateK0q_EtwWriteTransfer(v49, EventProfilerExit, v50, v64);
            return (unsigned int)v29;
          }
          if ( Address )
            MmUnmapViewInSystemSpace(Address);
        }
        v48 = Object;
        if ( Object )
        {
          if ( v62 )
          {
            ObCloseHandle(v62, ((unsigned __int64)v62 & 0xFFFFFFFF80000000uLL) == 0);
            v48 = Object;
          }
          ObfDereferenceObject(v48);
        }
        goto LABEL_55;
      }
      if ( (unsigned int)(v27 - 5) <= 1 )
      {
        v46 = MmMapViewInSystemSpace(Object, &Address, &Size);
        v29 = v46;
        if ( v46 < 0 )
        {
          _InterlockedIncrement(&dword_1400867CC);
          WdLogSingleEntry1(6, v46);
          WdLogGlobalForLineNumber = 407;
          v32 = L"Failed VA mapping. Status = 0x%I64x\n";
          NewObjecta = v29;
          goto LABEL_42;
        }
      }
      v40 = 0;
      v34 = 0;
      goto LABEL_62;
    case 5:
LABEL_34:
      v42 = 1208221696;
      goto LABEL_35;
    case 6:
      goto LABEL_33;
  }
  v33 = 8400896;
  v34 = 4;
  if ( v27 != 2 )
    v34 = 1028;
  v17 = 12288;
  v35 = 12288;
  if ( v27 != 2 )
    v35 = 8400896;
  if ( !a5 )
    v33 = v35;
  if ( (int)VidMmAllocateVirtualMemory(&Address, &Size, v33, v34, *(_DWORD *)(a1 + 288)) >= 0 )
  {
    v17 = v33;
  }
  else
  {
    LODWORD(v29) = VidMmAllocateVirtualMemory(&Address, &Size, 0x3000u, v34, *(_DWORD *)(a1 + 288));
    if ( (int)v29 < 0 )
    {
      Address = 0;
      _InterlockedIncrement(&dword_1400867A8);
      WdLogSingleEntry0(6);
      v38 = 454;
      v39 = L"Couldn't commit virtual memory\n";
LABEL_32:
      WdLogGlobalForLineNumber = v38;
      DxgkLogInternalTriageEvent(v36, 262145, v37, (_DWORD)v39, v38, 0, 0, 0);
      v25 = Lookaside;
      goto LABEL_47;
    }
  }
  v40 = MmSecureVirtualMemory(Address, Size, 4u);
  if ( !v40 )
  {
    LODWORD(v29) = -1073741801;
    _InterlockedIncrement(&dword_1400867A8);
    WdLogSingleEntry0(6);
    v38 = 472;
    v39 = L"Couldn't secure the virtual memory range for the allocation.\n";
    goto LABEL_32;
  }
LABEL_62:
  *v28 |= 1u;
  *((_QWORD *)v28 + 7) = Size;
  *((_BYTE *)v28 + 64) = 0;
  *((_QWORD *)v28 + 6) = v40;
  *((_QWORD *)v28 + 1) = Address;
  v28[4] = v34;
  v28[5] = v17;
  *((_QWORD *)v28 + 4) = Object;
  *((_QWORD *)v28 + 5) = v62;
  v51 = a8;
  v28[6] = v27;
  *v51 = v28;
  if ( (unsigned int)(v27 - 5) <= 1 )
    *a9 = Address;
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 176LL) += Size;
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 184LL) += Size;
  ++*(_DWORD *)(*(_QWORD *)(a1 + 8) + 196LL);
  v52 = *(_QWORD **)(a1 + 8);
  if ( v27 == 1 )
  {
    v52[25] += Size;
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 208LL) += Size;
  }
  else if ( v27 == 2 )
  {
    v52[27] += Size;
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 224LL) += Size;
  }
  else
  {
    v52[29] += Size;
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 240LL) += Size;
  }
  if ( (byte_140086202 & 4) != 0 )
  {
    v53 = (int)Address;
    if ( (unsigned int)(v27 - 3) <= 3 )
      v53 = (int)Object;
    McTemplateK0pxqqt_EtwWriteTransfer(
      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 24LL),
      (unsigned int)EventCreateProcessAllocation,
      v41,
      v53,
      Size,
      v27,
      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 24LL),
      0);
  }
  if ( (byte_140086201 & 0x10) != 0 )
  {
    v54 = (int)Address;
    if ( (unsigned int)(v27 - 3) <= 3 )
      v54 = (int)Object;
    McTemplateK0qxxx_EtwWriteTransfer(
      v54,
      (unsigned int)EventCreateProcessAllocationDetails,
      v41,
      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 24LL),
      (char)v28,
      Size,
      v54);
  }
  *a10 = 1;
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v64);
  if ( v66 && (byte_140086202 & 1) != 0 )
    McTemplateK0q_EtwWriteTransfer(v55, EventProfilerExit, v56, v64);
  return 0;
}

```

## disassembly

```asm
0x1400ae640  mov     [rsp-28h+arg_8], rbx
0x1400ae645  mov     [rsp-28h+arg_18], rsi
0x1400ae64a  mov     [rsp-28h+Size], r8
0x1400ae64f  push    rbp
0x1400ae650  push    rdi
0x1400ae651  push    r13
0x1400ae653  push    r14
0x1400ae655  push    r15
0x1400ae657  mov     rbp, rsp
0x1400ae65a  sub     rsp, 80h
0x1400ae661  xor     r15d, r15d
0x1400ae664  mov     edi, r9d
0x1400ae667  test    byte ptr cs:qword_140086010, 2
0x1400ae66e  mov     r14, rcx
0x1400ae671  mov     [rbp+var_18], 0FFFFFFFFh
0x1400ae678  mov     ebx, 1F44h
0x1400ae67d  mov     [rbp+var_10], r15
0x1400ae681  jz      short loc_1400AE6A4
0x1400ae683  test    cs:byte_140086202, 1
0x1400ae68a  mov     [rbp+var_8], 1
0x1400ae68e  mov     [rbp+var_18], ebx
0x1400ae691  jz      short loc_1400AE6A8
0x1400ae693  mov     r9d, ebx
0x1400ae696  lea     rdx, EventProfilerEnter
0x1400ae69d  call    McTemplateK0q_EtwWriteTransfer
0x1400ae6a2  jmp     short loc_1400AE6A8
0x1400ae6a4  mov     [rbp+var_8], r15b
0x1400ae6a8  mov     edx, ebx
0x1400ae6aa  lea     rcx, [rbp+var_18]
0x1400ae6ae  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1400ae6b3  and     [rbp+arg_20], 4
0x1400ae6b7  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400ae6be  mov     [rbp+Address], r15
0x1400ae6c2  setnz   sil
0x1400ae6c6  mov     [rbp+Object], r15
0x1400ae6ca  mov     [rbp+var_28], r15
0x1400ae6ce  cmp     [rax], r15b
0x1400ae6d1  jz      short loc_1400AE6F9
0x1400ae6d3  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400ae6da  nop     dword ptr [rax+rax+00h]
0x1400ae6df  mov     rcx, [rbp+Size]
0x1400ae6e3  mov     [rax+18h], rcx
0x1400ae6e7  mov     [rax+20h], rdi
0x1400ae6eb  mov     [rax+28h], r14
0x1400ae6ef  mov     cs:WdLogGlobalForLineNumber, 127h
0x1400ae6f9  mov     rax, [r14+8]
0x1400ae6fd  mov     rbx, [rax+10h]
0x1400ae701  call    cs:__imp_PsGetCurrentProcess
0x1400ae708  nop     dword ptr [rax+rax+00h]
0x1400ae70d  cmp     rax, rbx
0x1400ae710  jz      short loc_1400AE74D
0x1400ae712  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400ae719  mov     dword ptr [rax], 1
0x1400ae71f  xor     r9d, r9d
0x1400ae722  mov     [rsp+80h+Handle], r15
0x1400ae727  mov     edx, 10Eh
0x1400ae72c  mov     [rsp+80h+NewObject], r15
0x1400ae731  xor     ecx, ecx
0x1400ae733  lea     r8d, [r9+1Eh]
0x1400ae737  call    cs:__imp_WdLogSingleEntry5
0x1400ae73e  nop     dword ptr [rax+rax+00h]
0x1400ae743  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400ae74d  mov     r8, [rbp+arg_38]
0x1400ae751  xor     ebx, ebx
0x1400ae753  mov     rcx, [rbp+arg_40]
0x1400ae757  mov     r9, [rbp+arg_48]
0x1400ae75b  mov     rdx, [rbp+Size]
0x1400ae75f  mov     [r8], rbx
0x1400ae762  mov     [rcx], rbx
0x1400ae765  mov     [r9], bl
0x1400ae768  mov     eax, cs:dword_140086458
0x1400ae76e  cmp     rdx, rax
0x1400ae771  jnb     short loc_1400AE7C8
0x1400ae773  mov     eax, [rbp+arg_30]
0x1400ae776  mov     [rsp+80h+var_48], r9
0x1400ae77b  mov     r9b, sil
0x1400ae77e  mov     [rsp+80h+var_50], rcx
0x1400ae783  mov     rcx, r14
0x1400ae786  mov     [rsp+80h+Handle], r8
0x1400ae78b  mov     r8d, edi
0x1400ae78e  mov     dword ptr [rsp+80h+NewObject], eax
0x1400ae792  call    ?AllocateSmallAllocation@VIDMM_PROCESS_HEAP@@AEAAJ_KI_NW4VIDMM_PROCESS_HEAP_MAPPING@@PEAPEAUVIDMM_HEAP_ALLOC@@PEAPEAXPEAE@Z; VIDMM_PROCESS_HEAP::AllocateSmallAllocation(unsigned __int64,uint,bool,VIDMM_PROCESS_HEAP_MAPPING,VIDMM_HEAP_ALLOC * *,void * *,uchar *)
0x1400ae797  lea     rcx, [rbp+var_18]; this
0x1400ae79b  mov     ebx, eax
0x1400ae79d  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1400ae7a2  cmp     [rbp+var_8], r15b
0x1400ae7a6  jz      short loc_1400AE7C1
0x1400ae7a8  test    cs:byte_140086202, 1
0x1400ae7af  jz      short loc_1400AE7C1
0x1400ae7b1  mov     r9d, [rbp+var_18]
0x1400ae7b5  lea     rdx, EventProfilerExit
0x1400ae7bc  call    McTemplateK0q_EtwWriteTransfer
0x1400ae7c1  mov     eax, ebx
0x1400ae7c3  jmp     loc_1400AED70
0x1400ae7c8  lea     r13, [r14+40h]
0x1400ae7cc  mov     rcx, r13; Lookaside
0x1400ae7cf  mov     [rbp+Lookaside], r13
0x1400ae7d3  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400ae7da  nop     dword ptr [rax+rax+00h]
0x1400ae7df  mov     esi, [rbp+arg_30]
0x1400ae7e2  mov     r15, rax
0x1400ae7e5  test    rax, rax
0x1400ae7e8  jnz     short loc_1400AE830
0x1400ae7ea  mov     edi, 0C0000017h
0x1400ae7ef  lock inc cs:dword_140086704
0x1400ae7f6  lea     ecx, [rax+6]
0x1400ae7f9  call    cs:__imp_WdLogSingleEntry0
0x1400ae800  nop     dword ptr [rax+rax+00h]
0x1400ae805  mov     [rsp+80h+var_48], rbx
0x1400ae80a  lea     r9, aCouldnTAllocat_37; "Couldn't allocate memory for VIDMM_PROC"...
0x1400ae811  mov     eax, 14Ch
0x1400ae816  mov     [rsp+80h+var_50], rbx
0x1400ae81b  mov     [rsp+80h+Handle], rbx
0x1400ae820  mov     cs:WdLogGlobalForLineNumber, eax
0x1400ae826  mov     [rsp+80h+NewObject], rax
0x1400ae82b  jmp     loc_1400AEB09
0x1400ae830  xor     edx, edx; Val
0x1400ae832  mov     rcx, r15; void *
0x1400ae835  lea     r8d, [rdx+60h]; Size
0x1400ae839  call    memset
0x1400ae83e  cmp     esi, 3
0x1400ae841  jz      loc_1400AE97F
0x1400ae847  cmp     esi, 4
0x1400ae84a  jz      loc_1400AE978
0x1400ae850  cmp     esi, 5
0x1400ae853  jz      loc_1400AE97F
0x1400ae859  cmp     esi, 6
0x1400ae85c  jz      loc_1400AE978
0x1400ae862  cmp     esi, 2
0x1400ae865  lea     rdx, [rbp+Size]; unsigned __int64 *
0x1400ae869  mov     eax, 404h
0x1400ae86e  lea     rcx, [rbp+Address]; void **
0x1400ae872  mov     edi, 803000h
0x1400ae877  mov     r13d, 4
0x1400ae87d  cmovnz  r13d, eax
0x1400ae881  mov     ebx, 3000h
0x1400ae886  mov     eax, ebx
0x1400ae888  mov     r9d, r13d; unsigned int
0x1400ae88b  cmovnz  eax, edi
0x1400ae88e  cmp     [rbp+arg_20], 0
0x1400ae892  cmovz   edi, eax
0x1400ae895  mov     eax, [r14+120h]
0x1400ae89c  mov     r8d, edi; unsigned int
0x1400ae89f  mov     dword ptr [rsp+80h+NewObject], eax; unsigned int
0x1400ae8a3  call    ?VidMmAllocateVirtualMemory@@YAJPEAPEAXPEA_KKKK@Z; VidMmAllocateVirtualMemory(void * *,unsigned __int64 *,ulong,ulong,ulong)
0x1400ae8a8  test    eax, eax
0x1400ae8aa  jns     short loc_1400AE8FA
0x1400ae8ac  mov     eax, [r14+120h]
0x1400ae8b3  lea     rdx, [rbp+Size]; unsigned __int64 *
0x1400ae8b7  mov     r9d, r13d; unsigned int
0x1400ae8ba  mov     dword ptr [rsp+80h+NewObject], eax; unsigned int
0x1400ae8be  mov     r8d, ebx; unsigned int
0x1400ae8c1  lea     rcx, [rbp+Address]; void **
0x1400ae8c5  call    ?VidMmAllocateVirtualMemory@@YAJPEAPEAXPEA_KKKK@Z; VidMmAllocateVirtualMemory(void * *,unsigned __int64 *,ulong,ulong,ulong)
0x1400ae8ca  mov     edi, eax
0x1400ae8cc  test    eax, eax
0x1400ae8ce  jns     short loc_1400AE8FC
0x1400ae8d0  xor     ebx, ebx
0x1400ae8d2  mov     [rbp+Address], rbx
0x1400ae8d6  lock inc cs:dword_1400867A8
0x1400ae8dd  lea     ecx, [rbx+6]
0x1400ae8e0  call    cs:__imp_WdLogSingleEntry0
0x1400ae8e7  nop     dword ptr [rax+rax+00h]
0x1400ae8ec  mov     eax, 1C6h
0x1400ae8f1  lea     r9, aCouldnTCommitV; "Couldn't commit virtual memory\n"
0x1400ae8f8  jmp     short loc_1400AE94B
0x1400ae8fa  mov     ebx, edi
0x1400ae8fc  mov     rdx, [rbp+Size]; Size
0x1400ae900  mov     r8d, 4; ProbeMode
0x1400ae906  mov     rcx, [rbp+Address]; Address
0x1400ae90a  call    cs:__imp_MmSecureVirtualMemory
0x1400ae911  nop     dword ptr [rax+rax+00h]
0x1400ae916  mov     rcx, rax
0x1400ae919  test    rax, rax
0x1400ae91c  jnz     loc_1400AEBE9
0x1400ae922  mov     edi, 0C0000017h
0x1400ae927  lock inc cs:dword_1400867A8
0x1400ae92e  lea     ecx, [rax+6]
0x1400ae931  call    cs:__imp_WdLogSingleEntry0
0x1400ae938  nop     dword ptr [rax+rax+00h]
0x1400ae93d  mov     eax, 1D8h
0x1400ae942  lea     r9, aCouldnTSecureT; "Couldn't secure the virtual memory rang"...
0x1400ae949  xor     ebx, ebx
0x1400ae94b  mov     [rsp+80h+var_48], rbx
0x1400ae950  mov     edx, 40001h
0x1400ae955  mov     [rsp+80h+var_50], rbx
0x1400ae95a  mov     [rsp+80h+Handle], rbx
0x1400ae95f  mov     [rsp+80h+NewObject], rax
0x1400ae964  mov     cs:WdLogGlobalForLineNumber, eax
0x1400ae96a  call    DxgkLogInternalTriageEvent
0x1400ae96f  mov     r13, [rbp+Lookaside]
0x1400ae973  jmp     loc_1400AEB27
0x1400ae978  mov     ecx, 8040000h
0x1400ae97d  jmp     short loc_1400AE984
0x1400ae97f  mov     ecx, 48040000h
0x1400ae984  or      ecx, [r14+120h]
0x1400ae98b  lea     r9, [rbp+Lookaside]
0x1400ae98f  mov     rax, [rbp+Size]
0x1400ae993  xor     r8d, r8d
0x1400ae996  mov     [rsp+80h+var_48], rbx
0x1400ae99b  xor     edx, edx
0x1400ae99d  mov     [rsp+80h+var_50], 0FFFFFFFFFFFFFFFFh
0x1400ae9a6  mov     dword ptr [rsp+80h+Handle], ecx
0x1400ae9aa  lea     rcx, [rbp+Object]
0x1400ae9ae  mov     [rbp+Lookaside], rax
0x1400ae9b2  mov     dword ptr [rsp+80h+NewObject], 4
0x1400ae9ba  call    cs:__imp_MmCreateSection
0x1400ae9c1  nop     dword ptr [rax+rax+00h]
0x1400ae9c6  mov     edi, eax
0x1400ae9c8  test    eax, eax
0x1400ae9ca  jns     short loc_1400AEA13
0x1400ae9cc  mov     [rbp+Object], rbx
0x1400ae9d0  lock inc cs:dword_1400867D0
0x1400ae9d7  mov     ecx, 6
0x1400ae9dc  call    cs:__imp_WdLogSingleEntry0
0x1400ae9e3  nop     dword ptr [rax+rax+00h]
0x1400ae9e8  mov     [rsp+80h+var_48], rbx
0x1400ae9ed  lea     r9, aCouldnTAllocat_5; "Couldn't allocate a backing section for"...
0x1400ae9f4  mov     eax, 176h
0x1400ae9f9  mov     [rsp+80h+var_50], rbx
0x1400ae9fe  mov     [rsp+80h+Handle], rbx
0x1400aea03  mov     cs:WdLogGlobalForLineNumber, eax
0x1400aea09  mov     [rsp+80h+NewObject], rax
0x1400aea0e  jmp     loc_1400AEB09
0x1400aea13  mov     rcx, [rbp+Object]; Object
0x1400aea17  call    cs:__imp_ObfReferenceObject
0x1400aea1e  nop     dword ptr [rax+rax+00h]
0x1400aea23  mov     rcx, [rbp+Object]; Object
0x1400aea27  lea     rax, [rbp+var_28]
0x1400aea2b  mov     [rsp+80h+Handle], rax; Handle
0x1400aea30  xor     r9d, r9d; ObjectPointerBias
0x1400aea33  xor     r8d, r8d; DesiredAccess
0x1400aea36  mov     [rsp+80h+NewObject], rbx; NewObject
0x1400aea3b  xor     edx, edx; PassedAccessState
0x1400aea3d  call    cs:__imp_ObInsertObject
0x1400aea44  nop     dword ptr [rax+rax+00h]
0x1400aea49  movsxd  rdi, eax
0x1400aea4c  test    eax, eax
0x1400aea4e  jns     short loc_1400AEA98
0x1400aea50  mov     rdx, [rbp+Object]
0x1400aea54  mov     r8, rdi
0x1400aea57  mov     ecx, 1
0x1400aea5c  call    cs:__imp_WdLogSingleEntry2
0x1400aea63  nop     dword ptr [rax+rax+00h]
0x1400aea68  mov     rax, [rbp+Object]
0x1400aea6c  lea     r9, aUnableToInsert; "Unable to insert section object 0x%I64p"...
0x1400aea73  mov     [rsp+80h+var_48], rbx
0x1400aea78  mov     edx, 40000h
0x1400aea7d  mov     [rsp+80h+var_50], rbx
0x1400aea82  mov     [rsp+80h+Handle], rdi
0x1400aea87  mov     [rsp+80h+NewObject], rax
0x1400aea8c  mov     cs:WdLogGlobalForLineNumber, 18Ah
0x1400aea96  jmp     short loc_1400AEB0E
0x1400aea98  lea     eax, [rsi-5]
0x1400aea9b  cmp     eax, 1
0x1400aea9e  ja      loc_1400AEBE3
0x1400aeaa4  mov     rcx, [rbp+Object]; Section
0x1400aeaa8  lea     r8, [rbp+Size]; ViewSize
0x1400aeaac  lea     rdx, [rbp+Address]; MappedBase
0x1400aeab0  call    cs:__imp_MmMapViewInSystemSpace
0x1400aeab7  nop     dword ptr [rax+rax+00h]
0x1400aeabc  movsxd  rdi, eax
0x1400aeabf  test    eax, eax
0x1400aeac1  jns     loc_1400AEBE3
0x1400aeac7  lock inc cs:dword_1400867CC
0x1400aeace  mov     rdx, rdi
0x1400aead1  mov     ecx, 6
0x1400aead6  call    cs:__imp_WdLogSingleEntry1
0x1400aeadd  nop     dword ptr [rax+rax+00h]
0x1400aeae2  xor     eax, eax
0x1400aeae4  mov     cs:WdLogGlobalForLineNumber, 197h
0x1400aeaee  mov     [rsp+80h+var_48], rax
0x1400aeaf3  lea     r9, aFailedVaMappin; "Failed VA mapping. Status = 0x%I64x\n"
0x1400aeafa  mov     [rsp+80h+var_50], rax
0x1400aeaff  mov     [rsp+80h+Handle], rax
0x1400aeb04  mov     [rsp+80h+NewObject], rdi
0x1400aeb09  mov     edx, 40001h
0x1400aeb0e  call    DxgkLogInternalTriageEvent
0x1400aeb13  cmp     esi, 3
0x1400aeb16  jz      short loc_1400AEB64
0x1400aeb18  cmp     esi, 4
0x1400aeb1b  jz      short loc_1400AEB64
0x1400aeb1d  cmp     esi, 5
0x1400aeb20  jz      short loc_1400AEB4F
0x1400aeb22  cmp     esi, 6
0x1400aeb25  jz      short loc_1400AEB4F
0x1400aeb27  cmp     [rbp+Address], rbx
0x1400aeb2b  jz      short loc_1400AEB9E
0x1400aeb2d  call    ?DxgkGetVirtualMemoryInterface@@YAPEBUDXGK_VIRTUAL_MEMORY_INTERFACE@@XZ; DxgkGetVirtualMemoryInterface(void)
0x1400aeb32  mov     r9d, 8000h
0x1400aeb38  lea     r8, [rbp+Size]
0x1400aeb3c  lea     rdx, [rbp+Address]
0x1400aeb40  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400aeb44  mov     rax, [rax+10h]
0x1400aeb48  call    _guard_dispatch_icall
0x1400aeb4d  jmp     short loc_1400AEB9E
0x1400aeb4f  mov     rcx, [rbp+Address]; MappedBase
0x1400aeb53  test    rcx, rcx
0x1400aeb56  jz      short loc_1400AEB64
0x1400aeb58  call    cs:__imp_MmUnmapViewInSystemSpace
  ... truncated ...
```
