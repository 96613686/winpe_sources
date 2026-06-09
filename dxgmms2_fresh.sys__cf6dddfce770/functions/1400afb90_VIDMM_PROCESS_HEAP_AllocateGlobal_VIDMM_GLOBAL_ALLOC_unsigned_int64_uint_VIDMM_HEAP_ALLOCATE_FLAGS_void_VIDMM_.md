# VIDMM_PROCESS_HEAP::AllocateGlobal(VIDMM_GLOBAL_ALLOC *,unsigned __int64,uint,VIDMM_HEAP_ALLOCATE_FLAGS,void *,VIDMM_PROCESS_HEAP_MAPPING,VIDMM_HEAP_ALLOC * *,void * *,uchar *)

- ea: `0x1400afb90`
- end: `0x1400b02dd`
- name: `?AllocateGlobal@VIDMM_PROCESS_HEAP@@UEAAJPEAUVIDMM_GLOBAL_ALLOC@@_KIW4VIDMM_HEAP_ALLOCATE_FLAGS@@PEAXW4VIDMM_PROCESS_HEAP_MAPPING@@PEAPEAUVIDMM_HEAP_ALLOC@@PEAPEAXPEAE@Z`
- size: `1869`
- prototype: `__int64 __fastcall(__int64, __int64, SIZE_T, unsigned int, int, __int64, unsigned int, _QWORD *, PVOID *, _BYTE *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140004268`
- `0x1400128c8`
- `0x140012ed4`
- `0x14002eb80`
- `0x14002f2a8`
- `0x14002f7d0`
- `0x14003a8dc`
- `0x140059030`
- `0x140059380`
- `0x1400afb90`
- `0x1400b02e4`
- `0x1400fc094`

## import_xrefs

- `ntoskrnl!MmSecureVirtualMemory` at `0x1400afe5a`
- `ntoskrnl!MmSecureVirtualMemory` at `0x1400afe5a`
- `ntoskrnl!ObfReferenceObject` at `0x1400aff67`
- `ntoskrnl!ObfReferenceObject` at `0x1400aff67`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b00e2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b00e2`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x1400b00a8`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x1400b00a8`
- `ntoskrnl!MmCreateSection` at `0x1400aff0a`
- `ntoskrnl!MmCreateSection` at `0x1400aff0a`
- `ntoskrnl!ObCloseHandle` at `0x1400b00d2`
- `ntoskrnl!ObCloseHandle` at `0x1400b00d2`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400afd23`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400afd23`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400b00f9`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400b00f9`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x1400b0000`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x1400b0000`
- `ntoskrnl!ObInsertObject` at `0x1400aff8d`
- `ntoskrnl!ObInsertObject` at `0x1400aff8d`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400afc51`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400afc51`
- `watchdog!WdLogSingleEntry2` at `0x1400affac`
- `watchdog!WdLogSingleEntry2` at `0x1400affac`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400afc23`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400afc23`
- `watchdog!WdLogSingleEntry5` at `0x1400afc87`
- `watchdog!WdLogSingleEntry5` at `0x1400afc87`
- `watchdog!WdLogSingleEntry0` at `0x1400afd49`
- `watchdog!WdLogSingleEntry0` at `0x1400afe30`
- `watchdog!WdLogSingleEntry0` at `0x1400afe81`
- `watchdog!WdLogSingleEntry0` at `0x1400aff2c`
- `watchdog!WdLogSingleEntry0` at `0x1400afd49`
- `watchdog!WdLogSingleEntry0` at `0x1400afe30`
- `watchdog!WdLogSingleEntry0` at `0x1400afe81`
- `watchdog!WdLogSingleEntry0` at `0x1400aff2c`
- `watchdog!WdLogSingleEntry1` at `0x1400b0026`
- `watchdog!WdLogSingleEntry1` at `0x1400b0026`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400afc62`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x1400afc07`

## string_xrefs

- `0x1400afe41`: `Couldn't commit virtual memory\n`

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
        unsigned int a7,
        _QWORD *a8,
        PVOID *a9,
        _BYTE *a10)
{
  __int64 v10; // rdi
  __int64 v12; // rdx
  __int64 v13; // rcx
  bool v14; // zf
  char v15; // si
  _QWORD *v16; // rax
  __int64 v17; // rbx
  _QWORD *v18; // r8
  int v19; // ebx
  PVOID *v20; // rcx
  _BYTE *v21; // r9
  SIZE_T v22; // rdx
  unsigned int SmallAllocation; // ebx
  __int64 v24; // rcx
  __int64 v25; // r8
  struct _PAGED_LOOKASIDE_LIST *v27; // r13
  _DWORD *v28; // rax
  unsigned int v29; // esi
  _DWORD *v30; // r15
  __int64 v31; // rdi
  int v32; // ecx
  int v33; // r8d
  const wchar_t *v34; // r9
  unsigned int v35; // edi
  unsigned int v36; // r13d
  int v37; // eax
  int v38; // ecx
  int v39; // r8d
  __int64 v40; // rax
  const wchar_t *v41; // r9
  HANDLE v42; // rcx
  int v43; // r8d
  int v44; // ecx
  NTSTATUS inserted; // eax
  int v46; // ecx
  int v47; // r8d
  NTSTATUS v48; // eax
  const struct DXGK_VIRTUAL_MEMORY_INTERFACE *VirtualMemoryInterface; // rax
  PVOID v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // r8
  _QWORD *v53; // rax
  _QWORD *v54; // rcx
  int v55; // r9d
  int v56; // ecx
  __int64 v57; // rcx
  __int64 v58; // r8
  __int64 NewObject; // [rsp+20h] [rbp-60h]
  int Handle; // [rsp+28h] [rbp-58h]
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
  if ( (qword_140087010 & 2) != 0 )
  {
    v66 = 1;
    v64 = 8004;
    if ( (byte_140087202 & 1) != 0 )
      McTemplateK0q_EtwWriteTransfer(a1, &EventProfilerEnter, a3, 8004);
  }
  else
  {
    v66 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v64, 8004);
  v14 = (a5 & 4) == 0;
  a5 &= 4u;
  Address = 0;
  v15 = !v14;
  Object = 0;
  v62 = 0;
  if ( g_IsInternalReleaseOrDbg )
  {
    v16 = (_QWORD *)WdLogNewEntry5_WdTrace(v13, v12);
    v16[3] = Size;
    v16[4] = v10;
    v16[5] = a1;
    WdLogGlobalForLineNumber = 295;
  }
  v17 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL);
  if ( PsGetCurrentProcess() != v17 )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 30, 0, 0, 0);
    WdLogGlobalForLineNumber = 227;
  }
  v18 = a8;
  v19 = 0;
  v20 = a9;
  v21 = a10;
  v22 = Size;
  *a8 = 0;
  *v20 = 0;
  *v21 = 0;
  if ( v22 < (unsigned int)dword_140087428 )
  {
    SmallAllocation = VIDMM_PROCESS_HEAP::AllocateSmallAllocation(a1, v22, v10, v15, a7, v18, v20, v21);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v64);
    if ( v66 )
    {
      if ( (byte_140087202 & 1) != 0 )
        McTemplateK0q_EtwWriteTransfer(v24, &EventProfilerExit, v25, v64);
    }
    return SmallAllocation;
  }
  v27 = (struct _PAGED_LOOKASIDE_LIST *)(a1 + 64);
  Lookaside = (PPAGED_LOOKASIDE_LIST)(a1 + 64);
  v28 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)(a1 + 64));
  v29 = a7;
  v30 = v28;
  if ( !v28 )
  {
    LODWORD(v31) = -1073741801;
    _InterlockedIncrement(&dword_1400876E4);
    WdLogSingleEntry0(6);
    v34 = L"Couldn't allocate memory for VIDMM_PROCESS_HEAP_ALLOC structure.\n";
    WdLogGlobalForLineNumber = 332;
    NewObject = 332;
LABEL_42:
    DxgkLogInternalTriageEvent(v32, 262145, v33, (_DWORD)v34, NewObject, 0, 0, 0);
    goto LABEL_43;
  }
  memset(v28, 0, 0x60u);
  switch ( v29 )
  {
    case 3u:
      goto LABEL_34;
    case 4u:
LABEL_33:
      v44 = 134479872;
LABEL_35:
      Handle = *(_DWORD *)(a1 + 288) | v44;
      Lookaside = (PPAGED_LOOKASIDE_LIST)Size;
      LODWORD(v31) = MmCreateSection(&Object, 0, 0, &Lookaside, 4, Handle, -1, 0);
      if ( (int)v31 < 0 )
      {
        Object = 0;
        _InterlockedIncrement(&dword_1400877B0);
        WdLogSingleEntry0(6);
        v34 = L"Couldn't allocate a backing section for a large allocation";
        WdLogGlobalForLineNumber = 374;
        NewObject = 374;
        goto LABEL_42;
      }
      ObfReferenceObject(Object);
      inserted = ObInsertObject(Object, 0, 0, 0, 0, &v62);
      v31 = inserted;
      if ( inserted < 0 )
      {
        WdLogSingleEntry2(1, Object, inserted);
        WdLogGlobalForLineNumber = 394;
        DxgkLogInternalTriageEvent(
          v46,
          0x40000,
          v47,
          (unsigned int)L"Unable to insert section object 0x%I64p into handle table, Status = 0x%I64p",
          (__int64)Object,
          v31,
          0,
          0);
LABEL_43:
        if ( v29 != 3 && v29 != 4 )
        {
          if ( v29 != 5 && v29 != 6 )
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
            if ( v30 )
              ExFreeToPagedLookasideList(v27, v30);
            DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v64);
            if ( v66 && (byte_140087202 & 1) != 0 )
              McTemplateK0q_EtwWriteTransfer(v51, &EventProfilerExit, v52, v64);
            return (unsigned int)v31;
          }
          if ( Address )
            MmUnmapViewInSystemSpace(Address);
        }
        v50 = Object;
        if ( Object )
        {
          if ( v62 )
          {
            ObCloseHandle(v62, ((unsigned __int64)v62 & 0xFFFFFFFF80000000uLL) == 0);
            v50 = Object;
          }
          ObfDereferenceObject(v50);
        }
        goto LABEL_55;
      }
      if ( v29 - 5 <= 1 )
      {
        v48 = MmMapViewInSystemSpace(Object, &Address, &Size);
        v31 = v48;
        if ( v48 < 0 )
        {
          _InterlockedIncrement(&dword_1400877AC);
          WdLogSingleEntry1(6, v48);
          WdLogGlobalForLineNumber = 407;
          v34 = L"Failed VA mapping. Status = 0x%I64x\n";
          NewObject = v31;
          goto LABEL_42;
        }
      }
      v42 = 0;
      v36 = 0;
      goto LABEL_62;
    case 5u:
LABEL_34:
      v44 = 1208221696;
      goto LABEL_35;
    case 6u:
      goto LABEL_33;
  }
  v35 = 8400896;
  v36 = 4;
  if ( v29 != 2 )
    v36 = 1028;
  v19 = 12288;
  v37 = 12288;
  if ( v29 != 2 )
    v37 = 8400896;
  if ( !a5 )
    v35 = v37;
  if ( (int)VidMmAllocateVirtualMemory(&Address, &Size, v35, v36, *(_DWORD *)(a1 + 288)) >= 0 )
  {
    v19 = v35;
  }
  else
  {
    LODWORD(v31) = VidMmAllocateVirtualMemory(&Address, &Size, 0x3000u, v36, *(_DWORD *)(a1 + 288));
    if ( (int)v31 < 0 )
    {
      Address = 0;
      _InterlockedIncrement(&dword_140087788);
      WdLogSingleEntry0(6);
      v40 = 454;
      v41 = L"Couldn't commit virtual memory\n";
LABEL_32:
      WdLogGlobalForLineNumber = v40;
      DxgkLogInternalTriageEvent(v38, 262145, v39, (_DWORD)v41, v40, 0, 0, 0);
      v27 = Lookaside;
      goto LABEL_47;
    }
  }
  v42 = MmSecureVirtualMemory(Address, Size, 4u);
  if ( !v42 )
  {
    LODWORD(v31) = -1073741801;
    _InterlockedIncrement(&dword_140087788);
    WdLogSingleEntry0(6);
    v40 = 472;
    v41 = L"Couldn't secure the virtual memory range for the allocation.\n";
    goto LABEL_32;
  }
LABEL_62:
  *v30 |= 1u;
  *((_QWORD *)v30 + 7) = Size;
  *((_BYTE *)v30 + 64) = 0;
  *((_QWORD *)v30 + 6) = v42;
  *((_QWORD *)v30 + 1) = Address;
  v30[4] = v36;
  v30[5] = v19;
  *((_QWORD *)v30 + 4) = Object;
  *((_QWORD *)v30 + 5) = v62;
  v53 = a8;
  v30[6] = v29;
  *v53 = v30;
  if ( v29 - 5 <= 1 )
    *a9 = Address;
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 184LL) += Size;
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 192LL) += Size;
  ++*(_DWORD *)(*(_QWORD *)(a1 + 8) + 204LL);
  v54 = *(_QWORD **)(a1 + 8);
  if ( v29 == 1 )
  {
    v54[26] += Size;
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 216LL) += Size;
  }
  else if ( v29 == 2 )
  {
    v54[28] += Size;
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 232LL) += Size;
  }
  else
  {
    v54[30] += Size;
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 248LL) += Size;
  }
  if ( (byte_140087202 & 4) != 0 )
  {
    v55 = (int)Address;
    if ( v29 - 3 <= 3 )
      v55 = (int)Object;
    McTemplateK0pxqqt_EtwWriteTransfer(
      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 24LL),
      (unsigned int)&EventCreateProcessAllocation,
      v43,
      v55,
      Size,
      v29,
      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 24LL),
      0);
  }
  if ( (byte_140087201 & 0x10) != 0 )
  {
    v56 = (int)Address;
    if ( v29 - 3 <= 3 )
      v56 = (int)Object;
    McTemplateK0qxxx_EtwWriteTransfer(
      v56,
      (unsigned int)&EventCreateProcessAllocationDetails,
      v43,
      *(_DWORD *)(*(_QWORD *)(a1 + 8) + 24LL),
      (char)v30,
      Size,
      v56);
  }
  *a10 = 1;
  DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v64);
  if ( v66 && (byte_140087202 & 1) != 0 )
    McTemplateK0q_EtwWriteTransfer(v57, &EventProfilerExit, v58, v64);
  return 0;
}

```

## disassembly

```asm
0x1400afb90  mov     [rsp-28h+arg_8], rbx
0x1400afb95  mov     [rsp-28h+arg_18], rsi
0x1400afb9a  mov     [rsp-28h+Size], r8
0x1400afb9f  push    rbp
0x1400afba0  push    rdi
0x1400afba1  push    r13
0x1400afba3  push    r14
0x1400afba5  push    r15
0x1400afba7  mov     rbp, rsp
0x1400afbaa  sub     rsp, 80h
0x1400afbb1  xor     r15d, r15d
0x1400afbb4  mov     edi, r9d
0x1400afbb7  test    byte ptr cs:qword_140087010, 2
0x1400afbbe  mov     r14, rcx
0x1400afbc1  mov     [rbp+var_18], 0FFFFFFFFh
0x1400afbc8  mov     ebx, 1F44h
0x1400afbcd  mov     [rbp+var_10], r15
0x1400afbd1  jz      short loc_1400AFBF4
0x1400afbd3  test    cs:byte_140087202, 1
0x1400afbda  mov     [rbp+var_8], 1
0x1400afbde  mov     [rbp+var_18], ebx
0x1400afbe1  jz      short loc_1400AFBF8
0x1400afbe3  mov     r9d, ebx
0x1400afbe6  lea     rdx, EventProfilerEnter
0x1400afbed  call    McTemplateK0q_EtwWriteTransfer
0x1400afbf2  jmp     short loc_1400AFBF8
0x1400afbf4  mov     [rbp+var_8], r15b
0x1400afbf8  mov     edx, ebx
0x1400afbfa  lea     rcx, [rbp+var_18]
0x1400afbfe  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1400afc03  and     [rbp+arg_20], 4
0x1400afc07  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x1400afc0e  mov     [rbp+Address], r15
0x1400afc12  setnz   sil
0x1400afc16  mov     [rbp+Object], r15
0x1400afc1a  mov     [rbp+var_28], r15
0x1400afc1e  cmp     [rax], r15b
0x1400afc21  jz      short loc_1400AFC49
0x1400afc23  call    cs:__imp_WdLogNewEntry5_WdTrace
0x1400afc2a  nop     dword ptr [rax+rax+00h]
0x1400afc2f  mov     rcx, [rbp+Size]
0x1400afc33  mov     [rax+18h], rcx
0x1400afc37  mov     [rax+20h], rdi
0x1400afc3b  mov     [rax+28h], r14
0x1400afc3f  mov     cs:WdLogGlobalForLineNumber, 127h
0x1400afc49  mov     rax, [r14+8]
0x1400afc4d  mov     rbx, [rax+10h]
0x1400afc51  call    cs:__imp_PsGetCurrentProcess
0x1400afc58  nop     dword ptr [rax+rax+00h]
0x1400afc5d  cmp     rax, rbx
0x1400afc60  jz      short loc_1400AFC9D
0x1400afc62  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400afc69  mov     dword ptr [rax], 1
0x1400afc6f  xor     r9d, r9d
0x1400afc72  mov     [rsp+80h+Handle], r15
0x1400afc77  mov     edx, 10Eh
0x1400afc7c  mov     [rsp+80h+NewObject], r15
0x1400afc81  xor     ecx, ecx
0x1400afc83  lea     r8d, [r9+1Eh]
0x1400afc87  call    cs:__imp_WdLogSingleEntry5
0x1400afc8e  nop     dword ptr [rax+rax+00h]
0x1400afc93  mov     cs:WdLogGlobalForLineNumber, 0E3h
0x1400afc9d  mov     r8, [rbp+arg_38]
0x1400afca1  xor     ebx, ebx
0x1400afca3  mov     rcx, [rbp+arg_40]
0x1400afca7  mov     r9, [rbp+arg_48]
0x1400afcab  mov     rdx, [rbp+Size]
0x1400afcaf  mov     [r8], rbx
0x1400afcb2  mov     [rcx], rbx
0x1400afcb5  mov     [r9], bl
0x1400afcb8  mov     eax, cs:dword_140087428
0x1400afcbe  cmp     rdx, rax
0x1400afcc1  jnb     short loc_1400AFD18
0x1400afcc3  mov     eax, [rbp+arg_30]
0x1400afcc6  mov     [rsp+80h+var_48], r9
0x1400afccb  mov     r9b, sil
0x1400afcce  mov     [rsp+80h+var_50], rcx
0x1400afcd3  mov     rcx, r14
0x1400afcd6  mov     [rsp+80h+Handle], r8
0x1400afcdb  mov     r8d, edi
0x1400afcde  mov     dword ptr [rsp+80h+NewObject], eax
0x1400afce2  call    ?AllocateSmallAllocation@VIDMM_PROCESS_HEAP@@AEAAJ_KI_NW4VIDMM_PROCESS_HEAP_MAPPING@@PEAPEAUVIDMM_HEAP_ALLOC@@PEAPEAXPEAE@Z; VIDMM_PROCESS_HEAP::AllocateSmallAllocation(unsigned __int64,uint,bool,VIDMM_PROCESS_HEAP_MAPPING,VIDMM_HEAP_ALLOC * *,void * *,uchar *)
0x1400afce7  lea     rcx, [rbp+var_18]; this
0x1400afceb  mov     ebx, eax
0x1400afced  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1400afcf2  cmp     [rbp+var_8], r15b
0x1400afcf6  jz      short loc_1400AFD11
0x1400afcf8  test    cs:byte_140087202, 1
0x1400afcff  jz      short loc_1400AFD11
0x1400afd01  mov     r9d, [rbp+var_18]
0x1400afd05  lea     rdx, EventProfilerExit
0x1400afd0c  call    McTemplateK0q_EtwWriteTransfer
0x1400afd11  mov     eax, ebx
0x1400afd13  jmp     loc_1400B02C0
0x1400afd18  lea     r13, [r14+40h]
0x1400afd1c  mov     rcx, r13; Lookaside
0x1400afd1f  mov     [rbp+Lookaside], r13
0x1400afd23  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400afd2a  nop     dword ptr [rax+rax+00h]
0x1400afd2f  mov     esi, [rbp+arg_30]
0x1400afd32  mov     r15, rax
0x1400afd35  test    rax, rax
0x1400afd38  jnz     short loc_1400AFD80
0x1400afd3a  mov     edi, 0C0000017h
0x1400afd3f  lock inc cs:dword_1400876E4
0x1400afd46  lea     ecx, [rax+6]
0x1400afd49  call    cs:__imp_WdLogSingleEntry0
0x1400afd50  nop     dword ptr [rax+rax+00h]
0x1400afd55  mov     [rsp+80h+var_48], rbx
0x1400afd5a  lea     r9, aCouldnTAllocat_39; "Couldn't allocate memory for VIDMM_PROC"...
0x1400afd61  mov     eax, 14Ch
0x1400afd66  mov     [rsp+80h+var_50], rbx
0x1400afd6b  mov     [rsp+80h+Handle], rbx
0x1400afd70  mov     cs:WdLogGlobalForLineNumber, eax
0x1400afd76  mov     [rsp+80h+NewObject], rax
0x1400afd7b  jmp     loc_1400B0059
0x1400afd80  xor     edx, edx; Val
0x1400afd82  mov     rcx, r15; void *
0x1400afd85  lea     r8d, [rdx+60h]; Size
0x1400afd89  call    memset
0x1400afd8e  cmp     esi, 3
0x1400afd91  jz      loc_1400AFECF
0x1400afd97  cmp     esi, 4
0x1400afd9a  jz      loc_1400AFEC8
0x1400afda0  cmp     esi, 5
0x1400afda3  jz      loc_1400AFECF
0x1400afda9  cmp     esi, 6
0x1400afdac  jz      loc_1400AFEC8
0x1400afdb2  cmp     esi, 2
0x1400afdb5  lea     rdx, [rbp+Size]; unsigned __int64 *
0x1400afdb9  mov     eax, 404h
0x1400afdbe  lea     rcx, [rbp+Address]; void **
0x1400afdc2  mov     edi, 803000h
0x1400afdc7  mov     r13d, 4
0x1400afdcd  cmovnz  r13d, eax
0x1400afdd1  mov     ebx, 3000h
0x1400afdd6  mov     eax, ebx
0x1400afdd8  mov     r9d, r13d; unsigned int
0x1400afddb  cmovnz  eax, edi
0x1400afdde  cmp     [rbp+arg_20], 0
0x1400afde2  cmovz   edi, eax
0x1400afde5  mov     eax, [r14+120h]
0x1400afdec  mov     r8d, edi; unsigned int
0x1400afdef  mov     dword ptr [rsp+80h+NewObject], eax; unsigned int
0x1400afdf3  call    ?VidMmAllocateVirtualMemory@@YAJPEAPEAXPEA_KKKK@Z; VidMmAllocateVirtualMemory(void * *,unsigned __int64 *,ulong,ulong,ulong)
0x1400afdf8  test    eax, eax
0x1400afdfa  jns     short loc_1400AFE4A
0x1400afdfc  mov     eax, [r14+120h]
0x1400afe03  lea     rdx, [rbp+Size]; unsigned __int64 *
0x1400afe07  mov     r9d, r13d; unsigned int
0x1400afe0a  mov     dword ptr [rsp+80h+NewObject], eax; unsigned int
0x1400afe0e  mov     r8d, ebx; unsigned int
0x1400afe11  lea     rcx, [rbp+Address]; void **
0x1400afe15  call    ?VidMmAllocateVirtualMemory@@YAJPEAPEAXPEA_KKKK@Z; VidMmAllocateVirtualMemory(void * *,unsigned __int64 *,ulong,ulong,ulong)
0x1400afe1a  mov     edi, eax
0x1400afe1c  test    eax, eax
0x1400afe1e  jns     short loc_1400AFE4C
0x1400afe20  xor     ebx, ebx
0x1400afe22  mov     [rbp+Address], rbx
0x1400afe26  lock inc cs:dword_140087788
0x1400afe2d  lea     ecx, [rbx+6]
0x1400afe30  call    cs:__imp_WdLogSingleEntry0
0x1400afe37  nop     dword ptr [rax+rax+00h]
0x1400afe3c  mov     eax, 1C6h
0x1400afe41  lea     r9, aCouldnTCommitV; "Couldn't commit virtual memory\n"
0x1400afe48  jmp     short loc_1400AFE9B
0x1400afe4a  mov     ebx, edi
0x1400afe4c  mov     rdx, [rbp+Size]; Size
0x1400afe50  mov     r8d, 4; ProbeMode
0x1400afe56  mov     rcx, [rbp+Address]; Address
0x1400afe5a  call    cs:__imp_MmSecureVirtualMemory
0x1400afe61  nop     dword ptr [rax+rax+00h]
0x1400afe66  mov     rcx, rax
0x1400afe69  test    rax, rax
0x1400afe6c  jnz     loc_1400B0139
0x1400afe72  mov     edi, 0C0000017h
0x1400afe77  lock inc cs:dword_140087788
0x1400afe7e  lea     ecx, [rax+6]
0x1400afe81  call    cs:__imp_WdLogSingleEntry0
0x1400afe88  nop     dword ptr [rax+rax+00h]
0x1400afe8d  mov     eax, 1D8h
0x1400afe92  lea     r9, aCouldnTSecureT; "Couldn't secure the virtual memory rang"...
0x1400afe99  xor     ebx, ebx
0x1400afe9b  mov     [rsp+80h+var_48], rbx
0x1400afea0  mov     edx, 40001h
0x1400afea5  mov     [rsp+80h+var_50], rbx
0x1400afeaa  mov     [rsp+80h+Handle], rbx
0x1400afeaf  mov     [rsp+80h+NewObject], rax
0x1400afeb4  mov     cs:WdLogGlobalForLineNumber, eax
0x1400afeba  call    DxgkLogInternalTriageEvent
0x1400afebf  mov     r13, [rbp+Lookaside]
0x1400afec3  jmp     loc_1400B0077
0x1400afec8  mov     ecx, 8040000h
0x1400afecd  jmp     short loc_1400AFED4
0x1400afecf  mov     ecx, 48040000h
0x1400afed4  or      ecx, [r14+120h]
0x1400afedb  lea     r9, [rbp+Lookaside]
0x1400afedf  mov     rax, [rbp+Size]
0x1400afee3  xor     r8d, r8d
0x1400afee6  mov     [rsp+80h+var_48], rbx
0x1400afeeb  xor     edx, edx
0x1400afeed  mov     [rsp+80h+var_50], 0FFFFFFFFFFFFFFFFh
0x1400afef6  mov     dword ptr [rsp+80h+Handle], ecx
0x1400afefa  lea     rcx, [rbp+Object]
0x1400afefe  mov     [rbp+Lookaside], rax
0x1400aff02  mov     dword ptr [rsp+80h+NewObject], 4
0x1400aff0a  call    cs:__imp_MmCreateSection
0x1400aff11  nop     dword ptr [rax+rax+00h]
0x1400aff16  mov     edi, eax
0x1400aff18  test    eax, eax
0x1400aff1a  jns     short loc_1400AFF63
0x1400aff1c  mov     [rbp+Object], rbx
0x1400aff20  lock inc cs:dword_1400877B0
0x1400aff27  mov     ecx, 6
0x1400aff2c  call    cs:__imp_WdLogSingleEntry0
0x1400aff33  nop     dword ptr [rax+rax+00h]
0x1400aff38  mov     [rsp+80h+var_48], rbx
0x1400aff3d  lea     r9, aCouldnTAllocat_5; "Couldn't allocate a backing section for"...
0x1400aff44  mov     eax, 176h
0x1400aff49  mov     [rsp+80h+var_50], rbx
0x1400aff4e  mov     [rsp+80h+Handle], rbx
0x1400aff53  mov     cs:WdLogGlobalForLineNumber, eax
0x1400aff59  mov     [rsp+80h+NewObject], rax
0x1400aff5e  jmp     loc_1400B0059
0x1400aff63  mov     rcx, [rbp+Object]; Object
0x1400aff67  call    cs:__imp_ObfReferenceObject
0x1400aff6e  nop     dword ptr [rax+rax+00h]
0x1400aff73  mov     rcx, [rbp+Object]; Object
0x1400aff77  lea     rax, [rbp+var_28]
0x1400aff7b  mov     [rsp+80h+Handle], rax; Handle
0x1400aff80  xor     r9d, r9d; ObjectPointerBias
0x1400aff83  xor     r8d, r8d; DesiredAccess
0x1400aff86  mov     [rsp+80h+NewObject], rbx; NewObject
0x1400aff8b  xor     edx, edx; PassedAccessState
0x1400aff8d  call    cs:__imp_ObInsertObject
0x1400aff94  nop     dword ptr [rax+rax+00h]
0x1400aff99  movsxd  rdi, eax
0x1400aff9c  test    eax, eax
0x1400aff9e  jns     short loc_1400AFFE8
0x1400affa0  mov     rdx, [rbp+Object]
0x1400affa4  mov     r8, rdi
0x1400affa7  mov     ecx, 1
0x1400affac  call    cs:__imp_WdLogSingleEntry2
0x1400affb3  nop     dword ptr [rax+rax+00h]
0x1400affb8  mov     rax, [rbp+Object]
0x1400affbc  lea     r9, aUnableToInsert; "Unable to insert section object 0x%I64p"...
0x1400affc3  mov     [rsp+80h+var_48], rbx
0x1400affc8  mov     edx, 40000h
0x1400affcd  mov     [rsp+80h+var_50], rbx
0x1400affd2  mov     [rsp+80h+Handle], rdi
0x1400affd7  mov     [rsp+80h+NewObject], rax
0x1400affdc  mov     cs:WdLogGlobalForLineNumber, 18Ah
0x1400affe6  jmp     short loc_1400B005E
0x1400affe8  lea     eax, [rsi-5]
0x1400affeb  cmp     eax, 1
0x1400affee  ja      loc_1400B0133
0x1400afff4  mov     rcx, [rbp+Object]; Section
0x1400afff8  lea     r8, [rbp+Size]; ViewSize
0x1400afffc  lea     rdx, [rbp+Address]; MappedBase
0x1400b0000  call    cs:__imp_MmMapViewInSystemSpace
0x1400b0007  nop     dword ptr [rax+rax+00h]
0x1400b000c  movsxd  rdi, eax
0x1400b000f  test    eax, eax
0x1400b0011  jns     loc_1400B0133
0x1400b0017  lock inc cs:dword_1400877AC
0x1400b001e  mov     rdx, rdi
0x1400b0021  mov     ecx, 6
0x1400b0026  call    cs:__imp_WdLogSingleEntry1
0x1400b002d  nop     dword ptr [rax+rax+00h]
0x1400b0032  xor     eax, eax
0x1400b0034  mov     cs:WdLogGlobalForLineNumber, 197h
0x1400b003e  mov     [rsp+80h+var_48], rax
0x1400b0043  lea     r9, aFailedVaMappin; "Failed VA mapping. Status = 0x%I64x\n"
0x1400b004a  mov     [rsp+80h+var_50], rax
0x1400b004f  mov     [rsp+80h+Handle], rax
0x1400b0054  mov     [rsp+80h+NewObject], rdi
0x1400b0059  mov     edx, 40001h
0x1400b005e  call    DxgkLogInternalTriageEvent
0x1400b0063  cmp     esi, 3
0x1400b0066  jz      short loc_1400B00B4
0x1400b0068  cmp     esi, 4
0x1400b006b  jz      short loc_1400B00B4
0x1400b006d  cmp     esi, 5
0x1400b0070  jz      short loc_1400B009F
0x1400b0072  cmp     esi, 6
0x1400b0075  jz      short loc_1400B009F
0x1400b0077  cmp     [rbp+Address], rbx
0x1400b007b  jz      short loc_1400B00EE
0x1400b007d  call    ?DxgkGetVirtualMemoryInterface@@YAPEBUDXGK_VIRTUAL_MEMORY_INTERFACE@@XZ; DxgkGetVirtualMemoryInterface(void)
0x1400b0082  mov     r9d, 8000h
0x1400b0088  lea     r8, [rbp+Size]
0x1400b008c  lea     rdx, [rbp+Address]
0x1400b0090  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400b0094  mov     rax, [rax+10h]
0x1400b0098  call    _guard_dispatch_icall
0x1400b009d  jmp     short loc_1400B00EE
0x1400b009f  mov     rcx, [rbp+Address]; MappedBase
0x1400b00a3  test    rcx, rcx
0x1400b00a6  jz      short loc_1400B00B4
0x1400b00a8  call    cs:__imp_MmUnmapViewInSystemSpace
  ... truncated ...
```
