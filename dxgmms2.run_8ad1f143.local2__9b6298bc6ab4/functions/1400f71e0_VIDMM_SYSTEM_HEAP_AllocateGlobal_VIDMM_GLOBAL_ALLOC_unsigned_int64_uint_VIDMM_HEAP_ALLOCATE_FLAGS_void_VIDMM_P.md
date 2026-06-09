# VIDMM_SYSTEM_HEAP::AllocateGlobal(VIDMM_GLOBAL_ALLOC *,unsigned __int64,uint,VIDMM_HEAP_ALLOCATE_FLAGS,void *,VIDMM_PROCESS_HEAP_MAPPING,VIDMM_HEAP_ALLOC * *,void * *,uchar *)

- ea: `0x1400f71e0`
- end: `0x1400f767b`
- name: `?AllocateGlobal@VIDMM_SYSTEM_HEAP@@UEAAJPEAUVIDMM_GLOBAL_ALLOC@@_KIW4VIDMM_HEAP_ALLOCATE_FLAGS@@PEAXW4VIDMM_PROCESS_HEAP_MAPPING@@PEAPEAUVIDMM_HEAP_ALLOC@@PEAPEAXPEAE@Z`
- size: `1179`
- prototype: `int __high(struct VIDMM_GLOBAL_ALLOC *, unsigned __int64, unsigned int, enum VIDMM_HEAP_ALLOCATE_FLAGS, void *, enum VIDMM_PROCESS_HEAP_MAPPING, struct VIDMM_HEAP_ALLOC **, void **, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x140058760`
- `0x1400c18bc`
- `0x1400f71e0`
- `0x1400f7684`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400f7286`
- `ntoskrnl!ObfReferenceObject` at `0x1400f73aa`
- `ntoskrnl!ObfReferenceObject` at `0x1400f7286`
- `ntoskrnl!ObfReferenceObject` at `0x1400f73aa`
- `ntoskrnl!MmCreateSection` at `0x1400f7309`
- `ntoskrnl!MmCreateSection` at `0x1400f7309`
- `ntoskrnl!ObCloseHandle` at `0x1400f7436`
- `ntoskrnl!ObCloseHandle` at `0x1400f7436`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x1400f7452`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x1400f7452`
- `ntoskrnl!ObInsertObject` at `0x1400f73d3`
- `ntoskrnl!ObInsertObject` at `0x1400f73d3`
- `watchdog!WdLogSingleEntry4` at `0x1400f7341`
- `watchdog!WdLogSingleEntry4` at `0x1400f7341`
- `watchdog!WdLogSingleEntry2` at `0x1400f73ee`
- `watchdog!WdLogSingleEntry2` at `0x1400f73ee`
- `watchdog!WdLogSingleEntry0` at `0x1400f7569`
- `watchdog!WdLogSingleEntry0` at `0x1400f7569`
- `watchdog!WdLogSingleEntry1` at `0x1400f7473`
- `watchdog!WdLogSingleEntry1` at `0x1400f74ea`
- `watchdog!WdLogSingleEntry1` at `0x1400f75ff`
- `watchdog!WdLogSingleEntry1` at `0x1400f7473`
- `watchdog!WdLogSingleEntry1` at `0x1400f74ea`
- `watchdog!WdLogSingleEntry1` at `0x1400f75ff`

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

  v10 = *(int **)(a2 + 384);
  ViewSize[0] = a3;
  v14 = *v10;
  v15 = operator new(56, 1680959830, 256);
  v16 = v15;
  if ( !v15 )
  {
    _InterlockedAdd(&dword_140086890, 1u);
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
  v20 = (**(_DWORD **)(a2 + 384) >> 2) & 1;
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
      _InterlockedAdd(&dword_140086898, 1u);
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
      _InterlockedAdd(&dword_140086894, 1u);
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
  _InterlockedAdd(&dword_140086830, 1u);
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
0x1400f71e0  mov     [rsp+arg_0], rbx
0x1400f71e5  push    rbp
0x1400f71e6  push    rsi
0x1400f71e7  push    rdi
0x1400f71e8  push    r12
0x1400f71ea  push    r13
0x1400f71ec  push    r14
0x1400f71ee  push    r15
0x1400f71f0  sub     rsp, 60h
0x1400f71f4  mov     rax, [rdx+180h]
0x1400f71fb  mov     rbx, r8
0x1400f71fe  mov     r14, rdx
0x1400f7201  mov     [rsp+98h+ViewSize], rbx
0x1400f7206  mov     r12, rcx
0x1400f7209  mov     edx, 64316956h
0x1400f720e  mov     ecx, 38h ; '8'
0x1400f7213  mov     r8d, 100h
0x1400f7219  mov     r13d, [rax]
0x1400f721c  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400f7221  xor     r15d, r15d
0x1400f7224  mov     rsi, rax
0x1400f7227  lea     edi, [r15+1]
0x1400f722b  test    rax, rax
0x1400f722e  jz      loc_1400F75F0
0x1400f7234  mov     ecx, [rax+30h]
0x1400f7237  and     r13d, 20000000h
0x1400f723e  mov     edx, [r14+1Ch]
0x1400f7242  shr     edx, 2
0x1400f7245  xor     edx, ecx
0x1400f7247  and     edx, 8
0x1400f724a  xor     edx, ecx
0x1400f724c  mov     rcx, [rsp+98h+Object]; Object
0x1400f7254  mov     [rax+30h], edx
0x1400f7257  and     edx, 0FFFFFFFEh
0x1400f725a  mov     rax, [r14+180h]
0x1400f7261  mov     r8d, [rax]
0x1400f7264  shr     r8d, 2
0x1400f7268  and     r8d, edi
0x1400f726b  mov     [rsi+10h], rbx
0x1400f726f  or      r8d, edx
0x1400f7272  mov     [rsi+30h], r8d
0x1400f7276  test    rcx, rcx
0x1400f7279  jz      short loc_1400F7297
0x1400f727b  or      r8d, 2
0x1400f727f  mov     [rsi], rcx
0x1400f7282  mov     [rsi+30h], r8d
0x1400f7286  call    cs:__imp_ObfReferenceObject
0x1400f728d  nop     dword ptr [rax+rax+00h]
0x1400f7292  jmp     loc_1400F7446
0x1400f7297  not     r8d
0x1400f729a  mov     [rsp+98h+arg_8], rbx
0x1400f72a2  and     r8d, edi
0x1400f72a5  shl     r8d, 1Eh
0x1400f72a9  lea     r15d, [r8+8040000h]
0x1400f72b0  test    [rsp+98h+arg_20], dil
0x1400f72b8  jz      short loc_1400F72D4
0x1400f72ba  bts     r15d, 13h
0x1400f72bf  lea     rax, [rbx+0FFFFh]
0x1400f72c6  and     rax, 0FFFFFFFFFFFF0000h
0x1400f72cc  mov     [rsp+98h+arg_8], rax
0x1400f72d4  or      r15d, [r12+14h]
0x1400f72d9  call    ?GetCurrentPartitionHandle@VIDMM_PROCESS@@SAPEAXXZ; VIDMM_PROCESS::GetCurrentPartitionHandle(void)
0x1400f72de  mov     [rsp+98h+var_60], 0
0x1400f72e7  lea     r9, [rsp+98h+arg_8]
0x1400f72ef  mov     [rsp+98h+var_68], rax
0x1400f72f4  xor     r8d, r8d
0x1400f72f7  mov     dword ptr [rsp+98h+Handle], r15d
0x1400f72fc  xor     edx, edx
0x1400f72fe  mov     rcx, rsi
0x1400f7301  mov     dword ptr [rsp+98h+NewObject], 4
0x1400f7309  call    cs:__imp_MmCreateSection
0x1400f7310  nop     dword ptr [rax+rax+00h]
0x1400f7315  movsxd  rbp, eax
0x1400f7318  test    eax, eax
0x1400f731a  jns     short loc_1400F738C
0x1400f731c  lock add cs:dword_140086830, edi
0x1400f7323  mov     r8, [rsp+98h+arg_8]
0x1400f732b  mov     rbx, rbp
0x1400f732e  mov     r9d, r15d
0x1400f7331  mov     rdx, r14
0x1400f7334  mov     ecx, 6
0x1400f7339  mov     [rsp+98h+NewObject], rbx
0x1400f733e  mov     edi, r15d
0x1400f7341  call    cs:__imp_WdLogSingleEntry4
0x1400f7348  nop     dword ptr [rax+rax+00h]
0x1400f734d  mov     rax, [rsp+98h+arg_8]
0x1400f7355  lea     r9, aFailedToAlloca_55; "Failed to allocate section object for g"...
0x1400f735c  mov     [rsp+98h+var_60], rbx
0x1400f7361  mov     edx, 40001h
0x1400f7366  mov     [rsp+98h+var_68], rdi
0x1400f736b  mov     [rsp+98h+Handle], rax
0x1400f7370  mov     [rsp+98h+NewObject], r14
0x1400f7375  mov     cs:WdLogGlobalForLineNumber, 339h
0x1400f737f  call    DxgkLogInternalTriageEvent
0x1400f7384  xor     r15d, r15d
0x1400f7387  jmp     loc_1400F75A8
0x1400f738c  xor     r15d, r15d
0x1400f738f  test    r13d, r13d
0x1400f7392  jnz     short loc_1400F739F
0x1400f7394  mov     eax, [rsi+30h]
0x1400f7397  test    al, 8
0x1400f7399  jz      loc_1400F7446
0x1400f739f  mov     rcx, [rsi]; Object
0x1400f73a2  mov     [rsp+98h+arg_10], r15
0x1400f73aa  call    cs:__imp_ObfReferenceObject
0x1400f73b1  nop     dword ptr [rax+rax+00h]
0x1400f73b6  mov     rcx, [rsi]; Object
0x1400f73b9  lea     rax, [rsp+98h+arg_10]
0x1400f73c1  mov     [rsp+98h+Handle], rax; Handle
0x1400f73c6  xor     r9d, r9d; ObjectPointerBias
0x1400f73c9  xor     r8d, r8d; DesiredAccess
0x1400f73cc  mov     [rsp+98h+NewObject], r15; NewObject
0x1400f73d1  xor     edx, edx; PassedAccessState
0x1400f73d3  call    cs:__imp_ObInsertObject
0x1400f73da  nop     dword ptr [rax+rax+00h]
0x1400f73df  movsxd  rbp, eax
0x1400f73e2  test    eax, eax
0x1400f73e4  jns     short loc_1400F7424
0x1400f73e6  mov     r8, rbp
0x1400f73e9  mov     rdx, r14
0x1400f73ec  mov     ecx, edi
0x1400f73ee  call    cs:__imp_WdLogSingleEntry2
0x1400f73f5  nop     dword ptr [rax+rax+00h]
0x1400f73fa  mov     [rsp+98h+var_60], r15
0x1400f73ff  lea     r9, aObinsertobject; "ObInsertObject for GlobalAlloc: 0x%I64p"...
0x1400f7406  mov     [rsp+98h+var_68], r15
0x1400f740b  mov     [rsp+98h+Handle], rbp
0x1400f7410  mov     [rsp+98h+NewObject], r14
0x1400f7415  mov     cs:WdLogGlobalForLineNumber, 35Ch
0x1400f741f  jmp     loc_1400F759E
0x1400f7424  mov     rcx, [rsp+98h+arg_10]; Handle
0x1400f742c  test    rcx, 0FFFFFFFF80000000h
0x1400f7433  setz    dl; PreviousMode
0x1400f7436  call    cs:__imp_ObCloseHandle
0x1400f743d  nop     dword ptr [rax+rax+00h]
0x1400f7442  or      dword ptr [rsi+30h], 4
0x1400f7446  mov     rcx, [rsi]; Section
0x1400f7449  lea     r8, [rsp+98h+ViewSize]; ViewSize
0x1400f744e  lea     rdx, [rsi+8]; MappedBase
0x1400f7452  call    cs:__imp_MmMapViewInSystemSpace
0x1400f7459  nop     dword ptr [rax+rax+00h]
0x1400f745e  mov     ebp, eax
0x1400f7460  test    eax, eax
0x1400f7462  jns     short loc_1400F74B1
0x1400f7464  lock add cs:dword_140086898, edi
0x1400f746b  mov     rdx, r14
0x1400f746e  mov     ecx, 6
0x1400f7473  call    cs:__imp_WdLogSingleEntry1
0x1400f747a  nop     dword ptr [rax+rax+00h]
0x1400f747f  xor     r15d, r15d
0x1400f7482  mov     cs:WdLogGlobalForLineNumber, 36Dh
0x1400f748c  mov     [rsp+98h+var_60], r15
0x1400f7491  lea     r9, aFailedToMapSys_0; "Failed to map system space view for sys"...
0x1400f7498  mov     [rsp+98h+var_68], r15
0x1400f749d  mov     edx, 40001h
0x1400f74a2  mov     [rsp+98h+Handle], r15
0x1400f74a7  mov     [rsp+98h+NewObject], r14
0x1400f74ac  jmp     loc_1400F75A3
0x1400f74b1  mov     eax, [rsi+30h]
0x1400f74b4  test    al, 8
0x1400f74b6  jz      loc_1400F75C7
0x1400f74bc  mov     edx, 63326956h
0x1400f74c1  mov     ecx, 18h
0x1400f74c6  mov     r8d, 100h
0x1400f74cc  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400f74d1  mov     [rsi+18h], rax
0x1400f74d5  mov     rdx, rax
0x1400f74d8  test    rax, rax
0x1400f74db  jnz     short loc_1400F752F
0x1400f74dd  lock add cs:dword_140086894, edi
0x1400f74e4  mov     rdx, r14
0x1400f74e7  lea     ecx, [rax+6]
0x1400f74ea  call    cs:__imp_WdLogSingleEntry1
0x1400f74f1  nop     dword ptr [rax+rax+00h]
0x1400f74f6  xor     r15d, r15d
0x1400f74f9  mov     cs:WdLogGlobalForLineNumber, 37Eh
0x1400f7503  mov     [rsp+98h+var_60], r15
0x1400f7508  lea     r9, aFailedToAlloca_51; "Failed to allocate VIDMM_SYSTEM_HEAP_AL"...
0x1400f750f  mov     [rsp+98h+var_68], r15
0x1400f7514  mov     edx, 40001h
0x1400f7519  mov     [rsp+98h+Handle], r15
0x1400f751e  mov     [rsp+98h+NewObject], r14
0x1400f7523  call    DxgkLogInternalTriageEvent
0x1400f7528  mov     ebp, 0C0000017h
0x1400f752d  jmp     short loc_1400F75A8
0x1400f752f  mov     [rsp+98h+var_60], rdx; void **
0x1400f7534  lea     rcx, [rdx+8]
0x1400f7538  mov     rdx, [rsi]; void *
0x1400f753b  add     rax, 10h
0x1400f753f  mov     [rsp+98h+var_68], rax; unsigned __int64 *
0x1400f7544  xor     r9d, r9d; unsigned int
0x1400f7547  mov     [rsp+98h+Handle], rcx; void **
0x1400f754c  mov     r8, rbx; unsigned __int64
0x1400f754f  mov     rcx, [r12+8]; this
0x1400f7554  mov     dword ptr [rsp+98h+NewObject], 4; unsigned int
0x1400f755c  call    ?MapHostVirtualAddressToGuest@VIDMM_PROCESS@@QEAAJPEAX_KKKPEAPEAXPEA_K2@Z; VIDMM_PROCESS::MapHostVirtualAddressToGuest(void *,unsigned __int64,ulong,ulong,void * *,unsigned __int64 *,void * *)
0x1400f7561  mov     ebp, eax
0x1400f7563  test    eax, eax
0x1400f7565  jns     short loc_1400F75C7
0x1400f7567  mov     ecx, edi
0x1400f7569  call    cs:__imp_WdLogSingleEntry0
0x1400f7570  nop     dword ptr [rax+rax+00h]
0x1400f7575  xor     r15d, r15d
0x1400f7578  lea     r9, aFailedToMapGue; "Failed to map guest physical address fo"...
0x1400f757f  mov     [rsp+98h+var_60], r15
0x1400f7584  mov     eax, 38Eh
0x1400f7589  mov     [rsp+98h+var_68], r15
0x1400f758e  mov     [rsp+98h+Handle], r15
0x1400f7593  mov     [rsp+98h+NewObject], rax
0x1400f7598  mov     cs:WdLogGlobalForLineNumber, eax
0x1400f759e  mov     edx, 40000h
0x1400f75a3  call    DxgkLogInternalTriageEvent
0x1400f75a8  mov     rax, [r12]
0x1400f75ac  xor     r9d, r9d
0x1400f75af  mov     r8, [rsi+8]
0x1400f75b3  mov     rdx, rsi
0x1400f75b6  mov     rcx, r12
0x1400f75b9  mov     rax, [rax+88h]
0x1400f75c0  call    _guard_dispatch_icall
0x1400f75c5  jmp     short loc_1400F763F
0x1400f75c7  mov     rax, [rsp+98h+arg_48]
0x1400f75cf  mov     [rax], dil
0x1400f75d2  mov     rax, [rsp+98h+arg_40]
0x1400f75da  mov     rcx, [rsi+8]
0x1400f75de  mov     [rax], rcx
0x1400f75e1  mov     rax, [rsp+98h+arg_38]
0x1400f75e9  mov     [rax], rsi
0x1400f75ec  xor     eax, eax
0x1400f75ee  jmp     short loc_1400F7662
0x1400f75f0  lock add cs:dword_140086890, edi
0x1400f75f7  mov     rdx, r14
0x1400f75fa  mov     ecx, 6
0x1400f75ff  call    cs:__imp_WdLogSingleEntry1
0x1400f7606  nop     dword ptr [rax+rax+00h]
0x1400f760b  mov     [rsp+98h+var_60], r15
0x1400f7610  lea     r9, aFailedToAlloca_78; "Failed to allocate VIDMM_SYSTEM_HEAP_AL"...
0x1400f7617  mov     [rsp+98h+var_68], r15
0x1400f761c  mov     edx, 40001h
0x1400f7621  mov     [rsp+98h+Handle], r15
0x1400f7626  mov     [rsp+98h+NewObject], r14
0x1400f762b  mov     cs:WdLogGlobalForLineNumber, 2F1h
0x1400f7635  call    DxgkLogInternalTriageEvent
0x1400f763a  mov     ebp, 0C0000017h
0x1400f763f  mov     rax, [rsp+98h+arg_48]
0x1400f7647  mov     [rax], r15b
0x1400f764a  mov     rax, [rsp+98h+arg_38]
0x1400f7652  mov     [rax], r15
0x1400f7655  mov     rax, [rsp+98h+arg_40]
0x1400f765d  mov     [rax], r15
0x1400f7660  mov     eax, ebp
0x1400f7662  mov     rbx, [rsp+98h+arg_0]
0x1400f766a  add     rsp, 60h
0x1400f766e  pop     r15
0x1400f7670  pop     r14
0x1400f7672  pop     r13
0x1400f7674  pop     r12
0x1400f7676  pop     rdi
0x1400f7677  pop     rsi
0x1400f7678  pop     rbp
0x1400f7679  retn
```
