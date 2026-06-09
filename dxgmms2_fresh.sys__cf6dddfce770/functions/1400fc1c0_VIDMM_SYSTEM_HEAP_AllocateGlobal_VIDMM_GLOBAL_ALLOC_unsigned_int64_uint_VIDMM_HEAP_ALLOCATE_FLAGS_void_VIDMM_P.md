# VIDMM_SYSTEM_HEAP::AllocateGlobal(VIDMM_GLOBAL_ALLOC *,unsigned __int64,uint,VIDMM_HEAP_ALLOCATE_FLAGS,void *,VIDMM_PROCESS_HEAP_MAPPING,VIDMM_HEAP_ALLOC * *,void * *,uchar *)

- ea: `0x1400fc1c0`
- end: `0x1400fc65b`
- name: `?AllocateGlobal@VIDMM_SYSTEM_HEAP@@UEAAJPEAUVIDMM_GLOBAL_ALLOC@@_KIW4VIDMM_HEAP_ALLOCATE_FLAGS@@PEAXW4VIDMM_PROCESS_HEAP_MAPPING@@PEAPEAUVIDMM_HEAP_ALLOC@@PEAPEAXPEAE@Z`
- size: `1179`
- prototype: `int __high(struct VIDMM_GLOBAL_ALLOC *, unsigned __int64, unsigned int, enum VIDMM_HEAP_ALLOCATE_FLAGS, void *, enum VIDMM_PROCESS_HEAP_MAPPING, struct VIDMM_HEAP_ALLOC **, void **, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140003490`
- `0x140004268`
- `0x140059030`
- `0x1400c5a68`
- `0x1400fc1c0`
- `0x1400fc664`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400fc266`
- `ntoskrnl!ObfReferenceObject` at `0x1400fc38a`
- `ntoskrnl!ObfReferenceObject` at `0x1400fc266`
- `ntoskrnl!ObfReferenceObject` at `0x1400fc38a`
- `ntoskrnl!MmCreateSection` at `0x1400fc2e9`
- `ntoskrnl!MmCreateSection` at `0x1400fc2e9`
- `ntoskrnl!ObCloseHandle` at `0x1400fc416`
- `ntoskrnl!ObCloseHandle` at `0x1400fc416`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x1400fc432`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x1400fc432`
- `ntoskrnl!ObInsertObject` at `0x1400fc3b3`
- `ntoskrnl!ObInsertObject` at `0x1400fc3b3`
- `watchdog!WdLogSingleEntry4` at `0x1400fc321`
- `watchdog!WdLogSingleEntry4` at `0x1400fc321`
- `watchdog!WdLogSingleEntry2` at `0x1400fc3ce`
- `watchdog!WdLogSingleEntry2` at `0x1400fc3ce`
- `watchdog!WdLogSingleEntry0` at `0x1400fc549`
- `watchdog!WdLogSingleEntry0` at `0x1400fc549`
- `watchdog!WdLogSingleEntry1` at `0x1400fc453`
- `watchdog!WdLogSingleEntry1` at `0x1400fc4ca`
- `watchdog!WdLogSingleEntry1` at `0x1400fc5df`
- `watchdog!WdLogSingleEntry1` at `0x1400fc453`
- `watchdog!WdLogSingleEntry1` at `0x1400fc4ca`
- `watchdog!WdLogSingleEntry1` at `0x1400fc5df`

## pseudocode

```c
__int64 __fastcall VIDMM_SYSTEM_HEAP::AllocateGlobal(
        __int64 a1,
        __int64 a2,
        ULONG_PTR a3,
        __int64 a4,
        char a5,
        PVOID Object,
        __int64 a7,
        __int64 *a8,
        _QWORD *a9,
        _BYTE *a10)
{
  int *v10; // rax
  int v14; // r13d
  __int64 v15; // rax
  __int64 v16; // rsi
  int v17; // r13d
  int v18; // edx
  PVOID v19; // rcx
  int v20; // r8d
  unsigned int v21; // r8d
  int v22; // r15d
  unsigned int v23; // r15d
  void *CurrentPartitionHandle; // rax
  int v25; // eax
  __int64 v26; // rbp
  int v27; // ecx
  int v28; // r8d
  PVOID v29; // rcx
  NTSTATUS inserted; // eax
  int v31; // ecx
  int v32; // r8d
  const wchar_t *v33; // r9
  int v34; // ecx
  int v35; // r8d
  __int64 v36; // rax
  int v37; // ecx
  int v38; // r8d
  int v40; // ecx
  int v41; // r8d
  __int64 NewObject; // [rsp+20h] [rbp-78h]
  PHANDLE Handle; // [rsp+28h] [rbp-70h]
  ULONG_PTR ViewSize[9]; // [rsp+50h] [rbp-48h] BYREF
  unsigned __int64 v45; // [rsp+A8h] [rbp+10h] BYREF
  HANDLE v46; // [rsp+B0h] [rbp+18h] BYREF

  v10 = *(int **)(a2 + 392);
  ViewSize[0] = a3;
  v14 = *v10;
  v15 = operator new(56, 1680959830, 256);
  v16 = v15;
  if ( !v15 )
  {
    _InterlockedAdd(&dword_140087870, 1u);
    WdLogSingleEntry1(6, a2);
    WdLogGlobalForLineNumber = 753;
    DxgkLogInternalTriageEvent(
      v40,
      262145,
      v41,
      (unsigned int)L"Failed to allocate VIDMM_SYSTEM_HEAP_ALLOC for global alloc 0x%.16x",
      a2,
      0,
      0,
      0);
    LODWORD(v26) = -1073741801;
    goto LABEL_24;
  }
  v17 = v14 & 0x20000000;
  v18 = *(_DWORD *)(v15 + 48)
      ^ ((unsigned __int8)*(_DWORD *)(v15 + 48)
       ^ (unsigned __int8)(*(_DWORD *)(a2 + 28) >> 2))
      & 8;
  v19 = Object;
  *(_DWORD *)(v15 + 48) = v18;
  v20 = (**(_DWORD **)(a2 + 392) >> 2) & 1;
  *(_QWORD *)(v15 + 16) = a3;
  v21 = v18 & 0xFFFFFFFE | v20;
  *(_DWORD *)(v15 + 48) = v21;
  if ( v19 )
  {
    *(_QWORD *)v15 = v19;
    *(_DWORD *)(v15 + 48) = v21 | 2;
    ObfReferenceObject(v19);
    goto LABEL_13;
  }
  v45 = a3;
  v22 = (((v21 & 1) == 0) << 30) + 134479872;
  if ( (a5 & 1) != 0 )
  {
    v22 |= 0x80000u;
    v45 = (a3 + 0xFFFF) & 0xFFFFFFFFFFFF0000uLL;
  }
  v23 = *(_DWORD *)(a1 + 20) | v22;
  CurrentPartitionHandle = VIDMM_PROCESS::GetCurrentPartitionHandle();
  v25 = MmCreateSection(v16, 0, 0, &v45, 4, v23, CurrentPartitionHandle, 0);
  v26 = v25;
  if ( v25 >= 0 )
  {
    if ( v17 || (*(_DWORD *)(v16 + 48) & 8) != 0 )
    {
      v29 = *(PVOID *)v16;
      v46 = 0;
      ObfReferenceObject(v29);
      inserted = ObInsertObject(*(PVOID *)v16, 0, 0, 0, 0, &v46);
      v26 = inserted;
      if ( inserted < 0 )
      {
        WdLogSingleEntry2(1, a2, inserted);
        v33 = L"ObInsertObject for GlobalAlloc: 0x%I64p failed with: 0x%I64x";
        Handle = (PHANDLE)v26;
        NewObject = a2;
        WdLogGlobalForLineNumber = 860;
        goto LABEL_20;
      }
      ObCloseHandle(v46, ((unsigned __int64)v46 & 0xFFFFFFFF80000000uLL) == 0);
      *(_DWORD *)(v16 + 48) |= 4u;
    }
LABEL_13:
    LODWORD(v26) = MmMapViewInSystemSpace(*(PVOID *)v16, (PVOID *)(v16 + 8), ViewSize);
    if ( (int)v26 < 0 )
    {
      _InterlockedAdd(&dword_140087878, 1u);
      WdLogSingleEntry1(6, a2);
      WdLogGlobalForLineNumber = 877;
      DxgkLogInternalTriageEvent(
        v34,
        262145,
        v35,
        (unsigned int)L"Failed to map system space view for system heap allocation. GlobalAlloc=0x%.16x",
        a2,
        0,
        0,
        0);
      goto LABEL_21;
    }
    if ( (*(_DWORD *)(v16 + 48) & 8) == 0 )
      goto LABEL_22;
    v36 = operator new(24, 1664248150, 256);
    *(_QWORD *)(v16 + 24) = v36;
    if ( !v36 )
    {
      _InterlockedAdd(&dword_140087874, 1u);
      WdLogSingleEntry1(6, a2);
      WdLogGlobalForLineNumber = 894;
      DxgkLogInternalTriageEvent(
        v37,
        262145,
        v38,
        (unsigned int)L"Failed to allocate VIDMM_SYSTEM_HEAP_ALLOC_VGPU_DATA for global alloc 0x%.16x",
        a2,
        0,
        0,
        0);
      LODWORD(v26) = -1073741801;
      goto LABEL_21;
    }
    LODWORD(v26) = VIDMM_PROCESS::MapHostVirtualAddressToGuest(
                     *(VIDMM_PROCESS **)(a1 + 8),
                     *(void **)v16,
                     a3,
                     0,
                     4u,
                     (void **)(v36 + 8),
                     (unsigned __int64 *)(v36 + 16),
                     (void **)v36);
    if ( (int)v26 >= 0 )
    {
LABEL_22:
      *a10 = 1;
      *a9 = *(_QWORD *)(v16 + 8);
      *a8 = v16;
      return 0;
    }
    WdLogSingleEntry0(1);
    v33 = L"Failed to map guest physical address for parav allocation";
    Handle = 0;
    NewObject = 910;
    WdLogGlobalForLineNumber = 910;
LABEL_20:
    DxgkLogInternalTriageEvent(v31, 0x40000, v32, (_DWORD)v33, NewObject, (__int64)Handle, 0, 0);
    goto LABEL_21;
  }
  _InterlockedAdd(&dword_140087810, 1u);
  WdLogSingleEntry4(6, a2, v45, v23, v25);
  WdLogGlobalForLineNumber = 825;
  DxgkLogInternalTriageEvent(
    v27,
    262145,
    v28,
    (unsigned int)L"Failed to allocate section object for global backing store. GlobalAlloc=0x%I64x, Size=%I64u, Attr=0x%."
                   "8x, Status=0x%.8x",
    a2,
    v45,
    v23,
    v26);
LABEL_21:
  (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)a1 + 136LL))(a1, v16, *(_QWORD *)(v16 + 8), 0);
LABEL_24:
  *a10 = 0;
  *a8 = 0;
  *a9 = 0;
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x1400fc1c0  mov     [rsp+arg_0], rbx
0x1400fc1c5  push    rbp
0x1400fc1c6  push    rsi
0x1400fc1c7  push    rdi
0x1400fc1c8  push    r12
0x1400fc1ca  push    r13
0x1400fc1cc  push    r14
0x1400fc1ce  push    r15
0x1400fc1d0  sub     rsp, 60h
0x1400fc1d4  mov     rax, [rdx+188h]
0x1400fc1db  mov     rbx, r8
0x1400fc1de  mov     r14, rdx
0x1400fc1e1  mov     [rsp+98h+ViewSize], rbx
0x1400fc1e6  mov     r12, rcx
0x1400fc1e9  mov     edx, 64316956h
0x1400fc1ee  mov     ecx, 38h ; '8'
0x1400fc1f3  mov     r8d, 100h
0x1400fc1f9  mov     r13d, [rax]
0x1400fc1fc  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400fc201  xor     r15d, r15d
0x1400fc204  mov     rsi, rax
0x1400fc207  lea     edi, [r15+1]
0x1400fc20b  test    rax, rax
0x1400fc20e  jz      loc_1400FC5D0
0x1400fc214  mov     ecx, [rax+30h]
0x1400fc217  and     r13d, 20000000h
0x1400fc21e  mov     edx, [r14+1Ch]
0x1400fc222  shr     edx, 2
0x1400fc225  xor     edx, ecx
0x1400fc227  and     edx, 8
0x1400fc22a  xor     edx, ecx
0x1400fc22c  mov     rcx, [rsp+98h+Object]; Object
0x1400fc234  mov     [rax+30h], edx
0x1400fc237  and     edx, 0FFFFFFFEh
0x1400fc23a  mov     rax, [r14+188h]
0x1400fc241  mov     r8d, [rax]
0x1400fc244  shr     r8d, 2
0x1400fc248  and     r8d, edi
0x1400fc24b  mov     [rsi+10h], rbx
0x1400fc24f  or      r8d, edx
0x1400fc252  mov     [rsi+30h], r8d
0x1400fc256  test    rcx, rcx
0x1400fc259  jz      short loc_1400FC277
0x1400fc25b  or      r8d, 2
0x1400fc25f  mov     [rsi], rcx
0x1400fc262  mov     [rsi+30h], r8d
0x1400fc266  call    cs:__imp_ObfReferenceObject
0x1400fc26d  nop     dword ptr [rax+rax+00h]
0x1400fc272  jmp     loc_1400FC426
0x1400fc277  not     r8d
0x1400fc27a  mov     [rsp+98h+arg_8], rbx
0x1400fc282  and     r8d, edi
0x1400fc285  shl     r8d, 1Eh
0x1400fc289  lea     r15d, [r8+8040000h]
0x1400fc290  test    [rsp+98h+arg_20], dil
0x1400fc298  jz      short loc_1400FC2B4
0x1400fc29a  bts     r15d, 13h
0x1400fc29f  lea     rax, [rbx+0FFFFh]
0x1400fc2a6  and     rax, 0FFFFFFFFFFFF0000h
0x1400fc2ac  mov     [rsp+98h+arg_8], rax
0x1400fc2b4  or      r15d, [r12+14h]
0x1400fc2b9  call    ?GetCurrentPartitionHandle@VIDMM_PROCESS@@SAPEAXXZ; VIDMM_PROCESS::GetCurrentPartitionHandle(void)
0x1400fc2be  mov     [rsp+98h+var_60], 0
0x1400fc2c7  lea     r9, [rsp+98h+arg_8]
0x1400fc2cf  mov     [rsp+98h+var_68], rax
0x1400fc2d4  xor     r8d, r8d
0x1400fc2d7  mov     dword ptr [rsp+98h+Handle], r15d
0x1400fc2dc  xor     edx, edx
0x1400fc2de  mov     rcx, rsi
0x1400fc2e1  mov     dword ptr [rsp+98h+NewObject], 4
0x1400fc2e9  call    cs:__imp_MmCreateSection
0x1400fc2f0  nop     dword ptr [rax+rax+00h]
0x1400fc2f5  movsxd  rbp, eax
0x1400fc2f8  test    eax, eax
0x1400fc2fa  jns     short loc_1400FC36C
0x1400fc2fc  lock add cs:dword_140087810, edi
0x1400fc303  mov     r8, [rsp+98h+arg_8]
0x1400fc30b  mov     rbx, rbp
0x1400fc30e  mov     r9d, r15d
0x1400fc311  mov     rdx, r14
0x1400fc314  mov     ecx, 6
0x1400fc319  mov     [rsp+98h+NewObject], rbx
0x1400fc31e  mov     edi, r15d
0x1400fc321  call    cs:__imp_WdLogSingleEntry4
0x1400fc328  nop     dword ptr [rax+rax+00h]
0x1400fc32d  mov     rax, [rsp+98h+arg_8]
0x1400fc335  lea     r9, aFailedToAlloca_59; "Failed to allocate section object for g"...
0x1400fc33c  mov     [rsp+98h+var_60], rbx
0x1400fc341  mov     edx, 40001h
0x1400fc346  mov     [rsp+98h+var_68], rdi
0x1400fc34b  mov     [rsp+98h+Handle], rax
0x1400fc350  mov     [rsp+98h+NewObject], r14
0x1400fc355  mov     cs:WdLogGlobalForLineNumber, 339h
0x1400fc35f  call    DxgkLogInternalTriageEvent
0x1400fc364  xor     r15d, r15d
0x1400fc367  jmp     loc_1400FC588
0x1400fc36c  xor     r15d, r15d
0x1400fc36f  test    r13d, r13d
0x1400fc372  jnz     short loc_1400FC37F
0x1400fc374  mov     eax, [rsi+30h]
0x1400fc377  test    al, 8
0x1400fc379  jz      loc_1400FC426
0x1400fc37f  mov     rcx, [rsi]; Object
0x1400fc382  mov     [rsp+98h+arg_10], r15
0x1400fc38a  call    cs:__imp_ObfReferenceObject
0x1400fc391  nop     dword ptr [rax+rax+00h]
0x1400fc396  mov     rcx, [rsi]; Object
0x1400fc399  lea     rax, [rsp+98h+arg_10]
0x1400fc3a1  mov     [rsp+98h+Handle], rax; Handle
0x1400fc3a6  xor     r9d, r9d; ObjectPointerBias
0x1400fc3a9  xor     r8d, r8d; DesiredAccess
0x1400fc3ac  mov     [rsp+98h+NewObject], r15; NewObject
0x1400fc3b1  xor     edx, edx; PassedAccessState
0x1400fc3b3  call    cs:__imp_ObInsertObject
0x1400fc3ba  nop     dword ptr [rax+rax+00h]
0x1400fc3bf  movsxd  rbp, eax
0x1400fc3c2  test    eax, eax
0x1400fc3c4  jns     short loc_1400FC404
0x1400fc3c6  mov     r8, rbp
0x1400fc3c9  mov     rdx, r14
0x1400fc3cc  mov     ecx, edi
0x1400fc3ce  call    cs:__imp_WdLogSingleEntry2
0x1400fc3d5  nop     dword ptr [rax+rax+00h]
0x1400fc3da  mov     [rsp+98h+var_60], r15
0x1400fc3df  lea     r9, aObinsertobject; "ObInsertObject for GlobalAlloc: 0x%I64p"...
0x1400fc3e6  mov     [rsp+98h+var_68], r15
0x1400fc3eb  mov     [rsp+98h+Handle], rbp
0x1400fc3f0  mov     [rsp+98h+NewObject], r14
0x1400fc3f5  mov     cs:WdLogGlobalForLineNumber, 35Ch
0x1400fc3ff  jmp     loc_1400FC57E
0x1400fc404  mov     rcx, [rsp+98h+arg_10]; Handle
0x1400fc40c  test    rcx, 0FFFFFFFF80000000h
0x1400fc413  setz    dl; PreviousMode
0x1400fc416  call    cs:__imp_ObCloseHandle
0x1400fc41d  nop     dword ptr [rax+rax+00h]
0x1400fc422  or      dword ptr [rsi+30h], 4
0x1400fc426  mov     rcx, [rsi]; Section
0x1400fc429  lea     r8, [rsp+98h+ViewSize]; ViewSize
0x1400fc42e  lea     rdx, [rsi+8]; MappedBase
0x1400fc432  call    cs:__imp_MmMapViewInSystemSpace
0x1400fc439  nop     dword ptr [rax+rax+00h]
0x1400fc43e  mov     ebp, eax
0x1400fc440  test    eax, eax
0x1400fc442  jns     short loc_1400FC491
0x1400fc444  lock add cs:dword_140087878, edi
0x1400fc44b  mov     rdx, r14
0x1400fc44e  mov     ecx, 6
0x1400fc453  call    cs:__imp_WdLogSingleEntry1
0x1400fc45a  nop     dword ptr [rax+rax+00h]
0x1400fc45f  xor     r15d, r15d
0x1400fc462  mov     cs:WdLogGlobalForLineNumber, 36Dh
0x1400fc46c  mov     [rsp+98h+var_60], r15
0x1400fc471  lea     r9, aFailedToMapSys_0; "Failed to map system space view for sys"...
0x1400fc478  mov     [rsp+98h+var_68], r15
0x1400fc47d  mov     edx, 40001h
0x1400fc482  mov     [rsp+98h+Handle], r15
0x1400fc487  mov     [rsp+98h+NewObject], r14
0x1400fc48c  jmp     loc_1400FC583
0x1400fc491  mov     eax, [rsi+30h]
0x1400fc494  test    al, 8
0x1400fc496  jz      loc_1400FC5A7
0x1400fc49c  mov     edx, 63326956h
0x1400fc4a1  mov     ecx, 18h
0x1400fc4a6  mov     r8d, 100h
0x1400fc4ac  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400fc4b1  mov     [rsi+18h], rax
0x1400fc4b5  mov     rdx, rax
0x1400fc4b8  test    rax, rax
0x1400fc4bb  jnz     short loc_1400FC50F
0x1400fc4bd  lock add cs:dword_140087874, edi
0x1400fc4c4  mov     rdx, r14
0x1400fc4c7  lea     ecx, [rax+6]
0x1400fc4ca  call    cs:__imp_WdLogSingleEntry1
0x1400fc4d1  nop     dword ptr [rax+rax+00h]
0x1400fc4d6  xor     r15d, r15d
0x1400fc4d9  mov     cs:WdLogGlobalForLineNumber, 37Eh
0x1400fc4e3  mov     [rsp+98h+var_60], r15
0x1400fc4e8  lea     r9, aFailedToAlloca_55; "Failed to allocate VIDMM_SYSTEM_HEAP_AL"...
0x1400fc4ef  mov     [rsp+98h+var_68], r15
0x1400fc4f4  mov     edx, 40001h
0x1400fc4f9  mov     [rsp+98h+Handle], r15
0x1400fc4fe  mov     [rsp+98h+NewObject], r14
0x1400fc503  call    DxgkLogInternalTriageEvent
0x1400fc508  mov     ebp, 0C0000017h
0x1400fc50d  jmp     short loc_1400FC588
0x1400fc50f  mov     [rsp+98h+var_60], rdx; void **
0x1400fc514  lea     rcx, [rdx+8]
0x1400fc518  mov     rdx, [rsi]; void *
0x1400fc51b  add     rax, 10h
0x1400fc51f  mov     [rsp+98h+var_68], rax; unsigned __int64 *
0x1400fc524  xor     r9d, r9d; unsigned int
0x1400fc527  mov     [rsp+98h+Handle], rcx; void **
0x1400fc52c  mov     r8, rbx; unsigned __int64
0x1400fc52f  mov     rcx, [r12+8]; this
0x1400fc534  mov     dword ptr [rsp+98h+NewObject], 4; unsigned int
0x1400fc53c  call    ?MapHostVirtualAddressToGuest@VIDMM_PROCESS@@QEAAJPEAX_KKKPEAPEAXPEA_K2@Z; VIDMM_PROCESS::MapHostVirtualAddressToGuest(void *,unsigned __int64,ulong,ulong,void * *,unsigned __int64 *,void * *)
0x1400fc541  mov     ebp, eax
0x1400fc543  test    eax, eax
0x1400fc545  jns     short loc_1400FC5A7
0x1400fc547  mov     ecx, edi
0x1400fc549  call    cs:__imp_WdLogSingleEntry0
0x1400fc550  nop     dword ptr [rax+rax+00h]
0x1400fc555  xor     r15d, r15d
0x1400fc558  lea     r9, aFailedToMapGue; "Failed to map guest physical address fo"...
0x1400fc55f  mov     [rsp+98h+var_60], r15
0x1400fc564  mov     eax, 38Eh
0x1400fc569  mov     [rsp+98h+var_68], r15
0x1400fc56e  mov     [rsp+98h+Handle], r15
0x1400fc573  mov     [rsp+98h+NewObject], rax
0x1400fc578  mov     cs:WdLogGlobalForLineNumber, eax
0x1400fc57e  mov     edx, 40000h
0x1400fc583  call    DxgkLogInternalTriageEvent
0x1400fc588  mov     rax, [r12]
0x1400fc58c  xor     r9d, r9d
0x1400fc58f  mov     r8, [rsi+8]
0x1400fc593  mov     rdx, rsi
0x1400fc596  mov     rcx, r12
0x1400fc599  mov     rax, [rax+88h]
0x1400fc5a0  call    _guard_dispatch_icall
0x1400fc5a5  jmp     short loc_1400FC61F
0x1400fc5a7  mov     rax, [rsp+98h+arg_48]
0x1400fc5af  mov     [rax], dil
0x1400fc5b2  mov     rax, [rsp+98h+arg_40]
0x1400fc5ba  mov     rcx, [rsi+8]
0x1400fc5be  mov     [rax], rcx
0x1400fc5c1  mov     rax, [rsp+98h+arg_38]
0x1400fc5c9  mov     [rax], rsi
0x1400fc5cc  xor     eax, eax
0x1400fc5ce  jmp     short loc_1400FC642
0x1400fc5d0  lock add cs:dword_140087870, edi
0x1400fc5d7  mov     rdx, r14
0x1400fc5da  mov     ecx, 6
0x1400fc5df  call    cs:__imp_WdLogSingleEntry1
0x1400fc5e6  nop     dword ptr [rax+rax+00h]
0x1400fc5eb  mov     [rsp+98h+var_60], r15
0x1400fc5f0  lea     r9, aFailedToAlloca_82; "Failed to allocate VIDMM_SYSTEM_HEAP_AL"...
0x1400fc5f7  mov     [rsp+98h+var_68], r15
0x1400fc5fc  mov     edx, 40001h
0x1400fc601  mov     [rsp+98h+Handle], r15
0x1400fc606  mov     [rsp+98h+NewObject], r14
0x1400fc60b  mov     cs:WdLogGlobalForLineNumber, 2F1h
0x1400fc615  call    DxgkLogInternalTriageEvent
0x1400fc61a  mov     ebp, 0C0000017h
0x1400fc61f  mov     rax, [rsp+98h+arg_48]
0x1400fc627  mov     [rax], r15b
0x1400fc62a  mov     rax, [rsp+98h+arg_38]
0x1400fc632  mov     [rax], r15
0x1400fc635  mov     rax, [rsp+98h+arg_40]
0x1400fc63d  mov     [rax], r15
0x1400fc640  mov     eax, ebp
0x1400fc642  mov     rbx, [rsp+98h+arg_0]
0x1400fc64a  add     rsp, 60h
0x1400fc64e  pop     r15
0x1400fc650  pop     r14
0x1400fc652  pop     r13
0x1400fc654  pop     r12
0x1400fc656  pop     rdi
0x1400fc657  pop     rsi
0x1400fc658  pop     rbp
0x1400fc659  retn
```
