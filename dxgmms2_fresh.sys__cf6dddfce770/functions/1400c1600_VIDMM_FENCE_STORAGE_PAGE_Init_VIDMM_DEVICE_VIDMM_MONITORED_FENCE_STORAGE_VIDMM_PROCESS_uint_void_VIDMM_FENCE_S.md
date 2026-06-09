# VIDMM_FENCE_STORAGE_PAGE::Init(VIDMM_DEVICE *,VIDMM_MONITORED_FENCE_STORAGE *,VIDMM_PROCESS *,uint,void *,VIDMM_FENCE_STORAGE_PLACMENT *)

- ea: `0x1400c1600`
- end: `0x1400c1c2e`
- name: `?Init@VIDMM_FENCE_STORAGE_PAGE@@QEAAJPEAVVIDMM_DEVICE@@PEAUVIDMM_MONITORED_FENCE_STORAGE@@PEAVVIDMM_PROCESS@@IPEAXPEAUVIDMM_FENCE_STORAGE_PLACMENT@@@Z`
- size: `1582`
- prototype: `__int64 __fastcall(VIDMM_FENCE_STORAGE_PAGE *this, struct VIDMM_DEVICE *, struct VIDMM_MONITORED_FENCE_STORAGE *, struct VIDMM_PROCESS *, unsigned int, __int64, __int64 MemoryDescriptorList)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14000288c`
- `0x14003d484`
- `0x140048514`

## callees

- `0x140004268`
- `0x14002bcc0`
- `0x14002bddc`
- `0x140059030`
- `0x1400c1600`
- `0x1400c58e4`
- `0x1400fc664`
- `0x140110c04`
- `0x14011c100`
- `0x140127f70`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400c1875`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400c1875`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400c1a1e`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400c1a1e`
- `ntoskrnl!MmCreateSection` at `0x1400c18fd`
- `ntoskrnl!MmCreateSection` at `0x1400c18fd`
- `ntoskrnl!MmMapViewInSystemSpaceEx` at `0x1400c1946`
- `ntoskrnl!MmMapViewInSystemSpaceEx` at `0x1400c1946`
- `watchdog!WdLogSingleEntry3` at `0x1400c1772`
- `watchdog!WdLogSingleEntry3` at `0x1400c1772`
- `watchdog!WdLogSingleEntry2` at `0x1400c1700`
- `watchdog!WdLogSingleEntry2` at `0x1400c1801`
- `watchdog!WdLogSingleEntry2` at `0x1400c1700`
- `watchdog!WdLogSingleEntry2` at `0x1400c1801`
- `watchdog!WdLogSingleEntry0` at `0x1400c19cf`
- `watchdog!WdLogSingleEntry0` at `0x1400c1a8a`
- `watchdog!WdLogSingleEntry0` at `0x1400c1ae4`
- `watchdog!WdLogSingleEntry0` at `0x1400c19cf`
- `watchdog!WdLogSingleEntry0` at `0x1400c1a8a`
- `watchdog!WdLogSingleEntry0` at `0x1400c1ae4`
- `watchdog!WdLogSingleEntry1` at `0x1400c164f`
- `watchdog!WdLogSingleEntry1` at `0x1400c16b0`
- `watchdog!WdLogSingleEntry1` at `0x1400c196a`
- `watchdog!WdLogSingleEntry1` at `0x1400c1bba`
- `watchdog!WdLogSingleEntry1` at `0x1400c164f`
- `watchdog!WdLogSingleEntry1` at `0x1400c16b0`
- `watchdog!WdLogSingleEntry1` at `0x1400c196a`
- `watchdog!WdLogSingleEntry1` at `0x1400c1bba`

## string_xrefs

- `0x1400c16c6`: `Allocating guest present fence storage page from non-Xbox Back Compat process, returning 0x%I64x.`

## pseudocode

```c
__int64 __fastcall VIDMM_FENCE_STORAGE_PAGE::Init(
        VIDMM_FENCE_STORAGE_PAGE *this,
        struct VIDMM_DEVICE *a2,
        struct VIDMM_MONITORED_FENCE_STORAGE *a3,
        struct VIDMM_PROCESS *a4,
        unsigned int a5,
        __int64 a6,
        __int64 MemoryDescriptorList)
{
  __int64 *v11; // rsi
  int v12; // ecx
  int v13; // r8d
  const wchar_t *v14; // r9
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // r14
  int v19; // ecx
  int v20; // r8d
  unsigned int v21; // ecx
  int v22; // ecx
  int v23; // r8d
  unsigned int v24; // ebx
  int v25; // eax
  int v26; // r8d
  __int64 v27; // rcx
  PVOID v28; // rax
  unsigned __int64 *v29; // r14
  int v30; // esi
  void *CurrentPartitionHandle; // rax
  _QWORD *v32; // r15
  __int64 v33; // rsi
  int v34; // eax
  int v35; // ecx
  int v36; // r8d
  struct _MDL *Mdl; // rax
  int v38; // ecx
  int v39; // r8d
  __int64 v40; // rcx
  VIDMM_PROCESS *VmwpProcess; // rcx
  int v42; // ecx
  int v43; // r8d
  __int64 v44; // rax
  int v45; // ecx
  int v46; // r8d
  struct VIDMM_PROCESS *v47; // rbx
  char *v48; // rbx
  __int64 v49; // rcx
  __int64 v50; // [rsp+50h] [rbp-48h] BYREF
  _BYTE v51[24]; // [rsp+58h] [rbp-40h] BYREF

  v11 = (__int64 *)MemoryDescriptorList;
  if ( MemoryDescriptorList )
  {
    if ( !*(_QWORD *)MemoryDescriptorList )
    {
      WdLogSingleEntry1(1, -1073741811);
      WdLogGlobalForLineNumber = 728;
      v14 = L"Caller sending nullptr hMemoryBlock, returning 0x%I64x.";
LABEL_4:
      DxgkLogInternalTriageEvent(v12, 0x40000, v13, (_DWORD)v14, -1073741811, 0, 0, 0);
      return 3221225485LL;
    }
    v16 = *((_QWORD *)a4 + 9);
    *((_QWORD *)this + 16) = v16;
    if ( !v16 )
    {
      WdLogSingleEntry1(1, -1073741811);
      WdLogGlobalForLineNumber = 736;
      v14 = L"Allocating guest present fence storage page from non-Xbox Back Compat process, returning 0x%I64x.";
      goto LABEL_4;
    }
    a5 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v16 + 16LL))(v16, *v11, &a5);
    v18 = v17;
    if ( v17 < 0 )
    {
      WdLogSingleEntry2(1, *v11, v17);
      WdLogGlobalForLineNumber = 749;
      DxgkLogInternalTriageEvent(
        v19,
        0x40000,
        v20,
        (unsigned int)L"Failed to get the size of the memory block 0x%I64x, returning 0x%I64x.",
        *v11,
        v18,
        0,
        0);
      return (unsigned int)v18;
    }
    v21 = *((_DWORD *)v11 + 2);
    if ( a5 < ((v21 + 4095) & 0xFFFFF000) )
    {
      WdLogSingleEntry3(1, *v11, v21, -1073741811);
      WdLogGlobalForLineNumber = 758;
      DxgkLogInternalTriageEvent(
        v22,
        0x40000,
        v23,
        (unsigned int)L"Memory block  0x%I64x is not large enough for the offset 0x%I64x, returning 0x%I64x.",
        *v11,
        *((unsigned int *)v11 + 2),
        -1073741811,
        0);
      return 3221225485LL;
    }
    v24 = v21 >> 12;
    MemoryDescriptorList = 0;
    v25 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, int, __int64 *))(**((_QWORD **)this + 16) + 24LL))(
            *((_QWORD *)this + 16),
            *v11,
            v21 >> 12,
            1,
            1,
            &MemoryDescriptorList);
    v18 = v25;
    if ( v25 < 0 )
    {
      WdLogSingleEntry2(1, *v11, v25);
      WdLogGlobalForLineNumber = 778;
      DxgkLogInternalTriageEvent(
        *v11,
        0x40000,
        v26,
        (unsigned int)L"Failed to probe and lock the memory block 0x%I64x, returning 0x%I64x.",
        *v11,
        v18,
        0,
        0);
      return (unsigned int)v18;
    }
    *((_QWORD *)this + 14) = *v11;
    *((_DWORD *)this + 30) = v24;
    v27 = MemoryDescriptorList;
    *((_QWORD *)this + 18) = MemoryDescriptorList;
    if ( (*(_BYTE *)(v27 + 10) & 5) != 0 )
      v28 = *(PVOID *)(v27 + 24);
    else
      v28 = MmMapLockedPagesSpecifyCache((PMDL)v27, 0, MmCached, 0, 0, 0x10u);
    v29 = (unsigned __int64 *)((char *)this + 136);
    *((_QWORD *)this + 17) = v28;
    goto LABEL_42;
  }
  v50 = 0;
  a6 = 4096;
  MemoryDescriptorList = 0;
  if ( *((VIDMM_PROCESS_FENCE_STORAGE **)this + 31) == VIDMM_PROCESS_FENCE_STORAGE::_GlobalFenceStorage )
  {
    v30 = 0x8000000;
    CurrentPartitionHandle = 0;
  }
  else
  {
    v30 = 134479872;
    CurrentPartitionHandle = VIDMM_PROCESS::GetCurrentPartitionHandle();
  }
  v32 = (_QWORD *)((char *)this + 104);
  LODWORD(v33) = MmCreateSection((char *)this + 104, 0, 0, &a6, 4, v30, CurrentPartitionHandle, 0);
  if ( (int)v33 >= 0 )
  {
    MemoryDescriptorList = 4096;
    v29 = (unsigned __int64 *)((char *)this + 136);
    v34 = MmMapViewInSystemSpaceEx(*v32, (char *)this + 136, &MemoryDescriptorList, &v50, 0);
    v33 = v34;
    if ( v34 < 0 )
    {
      _InterlockedIncrement(&dword_1400877AC);
      WdLogSingleEntry1(6, v34);
      WdLogGlobalForLineNumber = 850;
      DxgkLogInternalTriageEvent(
        v35,
        262145,
        v36,
        (unsigned int)L"Failed to map system space view of fence storage page. Status=0x%.8x",
        v33,
        0,
        0,
        0);
      goto LABEL_43;
    }
    Mdl = VidMmiAllocateMdl(*v29, 0x1000u);
    *((_QWORD *)this + 18) = Mdl;
    if ( Mdl )
    {
      MmProbeAndLockPages(Mdl, 0, IoModifyAccess);
      v40 = *((_QWORD *)this + 31);
      if ( *(_BYTE *)(v40 + 144) || a4 )
      {
        if ( a4 )
          VmwpProcess = VIDMM_PROCESS::GetVmwpProcess(a4);
        else
          VmwpProcess = *(VIDMM_PROCESS **)v40;
        *((_QWORD *)this + 4) = VmwpProcess;
        LODWORD(v33) = VIDMM_PROCESS::MapHostAddressesToGuest(
                         VmwpProcess,
                         *((struct _MDL **)this + 18),
                         0x1000u,
                         (void **)this + 29,
                         (unsigned __int64 *)this + 28);
        if ( (int)v33 < 0 )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 936;
          DxgkLogInternalTriageEvent(
            v42,
            0x40000,
            v43,
            (unsigned int)L"Failed to allocate fence storage page for paravirtualization",
            936,
            0,
            0,
            0);
          goto LABEL_43;
        }
        v44 = *((_QWORD *)this + 31);
        if ( !*(_BYTE *)(v44 + 144) )
        {
          if ( *(_QWORD *)v44 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 953;
            DxgkLogInternalTriageEvent(
              v45,
              262146,
              v46,
              (unsigned int)L"_ProcessFenceStorage.GetVidMmProcess() == nullptr",
              953,
              0,
              0,
              0);
          }
          *(_BYTE *)(*((_QWORD *)this + 31) + 145LL) = 1;
          *((_BYTE *)this + 240) = 1;
          v47 = VIDMM_PROCESS::GetVmwpProcess(*((VIDMM_PROCESS **)this + 4));
          DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
            (DXGAUTOPUSHLOCKEXCLUSIVE *)v51,
            (struct VIDMM_PROCESS *)((char *)v47 + 112));
          v48 = (char *)v47 + 96;
          v49 = *(_QWORD *)v48;
          if ( *(char **)(*(_QWORD *)v48 + 8LL) != v48 )
            __fastfail(3u);
          *((_QWORD *)this + 2) = v49;
          *((_QWORD *)this + 3) = v48;
          *(_QWORD *)(v49 + 8) = (char *)this + 16;
          *(_QWORD *)v48 = (char *)this + 16;
          DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v51);
        }
      }
LABEL_42:
      *((_QWORD *)this + 26) = *v29;
      *((_QWORD *)this + 20) = a2;
      *((_DWORD *)this + 44) = *((_DWORD *)a3 + 13);
      *((_DWORD *)this + 45) = *((_DWORD *)a3 + 14);
      return 0;
    }
    _InterlockedIncrement((volatile signed __int32 *)&gVidMmLowResourceAccumulated);
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 862;
    DxgkLogInternalTriageEvent(
      v38,
      262145,
      v39,
      (unsigned int)L"Failed to allocate memory for fence storage page MDL",
      862,
      0,
      0,
      0);
    LODWORD(v33) = -1073741801;
  }
  else
  {
    *v32 = 0;
  }
LABEL_43:
  VIDMM_FENCE_STORAGE_PAGE::FreeStorage(this);
  return (unsigned int)v33;
}

```

## disassembly

```asm
0x1400c1600  mov     [rsp+arg_8], rbx
0x1400c1605  mov     [rsp+arg_10], rsi
0x1400c160a  mov     [rsp+arg_0], rcx
0x1400c160f  push    rdi
0x1400c1610  push    r12
0x1400c1612  push    r13
0x1400c1614  push    r14
0x1400c1616  push    r15
0x1400c1618  sub     rsp, 70h
0x1400c161c  mov     rbx, r9
0x1400c161f  mov     r13, r8
0x1400c1622  mov     r12, rdx
0x1400c1625  mov     rdi, rcx
0x1400c1628  mov     rsi, [rsp+98h+MemoryDescriptorList]
0x1400c1630  xor     r15d, r15d
0x1400c1633  test    rsi, rsi
0x1400c1636  jz      loc_1400C1890
0x1400c163c  cmp     [rsi], r15
0x1400c163f  jnz     short loc_1400C1691
0x1400c1641  mov     rbx, 0FFFFFFFFC000000Dh
0x1400c1648  mov     rdx, rbx
0x1400c164b  lea     ecx, [r15+1]
0x1400c164f  call    cs:__imp_WdLogSingleEntry1
0x1400c1656  nop     dword ptr [rax+rax+00h]
0x1400c165b  mov     cs:WdLogGlobalForLineNumber, 2D8h
0x1400c1665  lea     r9, aCallerSendingN; "Caller sending nullptr hMemoryBlock, re"...
0x1400c166c  mov     [rsp+98h+var_60], r15
0x1400c1671  mov     [rsp+98h+var_68], r15
0x1400c1676  mov     qword ptr [rsp+98h+Priority], r15
0x1400c167b  mov     qword ptr [rsp+98h+BugCheckOnFailure], rbx
0x1400c1680  mov     edx, 40000h
0x1400c1685  call    DxgkLogInternalTriageEvent
0x1400c168a  mov     eax, ebx
0x1400c168c  jmp     loc_1400C1C13
0x1400c1691  mov     rcx, [r9+48h]
0x1400c1695  mov     [rdi+80h], rcx
0x1400c169c  test    rcx, rcx
0x1400c169f  jnz     short loc_1400C16CF
0x1400c16a1  mov     rbx, 0FFFFFFFFC000000Dh
0x1400c16a8  mov     rdx, rbx
0x1400c16ab  mov     ecx, 1
0x1400c16b0  call    cs:__imp_WdLogSingleEntry1
0x1400c16b7  nop     dword ptr [rax+rax+00h]
0x1400c16bc  mov     cs:WdLogGlobalForLineNumber, 2E0h
0x1400c16c6  lea     r9, aAllocatingGues; "Allocating guest present fence storage "...
0x1400c16cd  jmp     short loc_1400C166C
0x1400c16cf  mov     [rsp+98h+arg_20], r15d
0x1400c16d7  mov     rax, [rcx]
0x1400c16da  mov     rax, [rax+10h]
0x1400c16de  lea     r8, [rsp+98h+arg_20]
0x1400c16e6  mov     rdx, [rsi]
0x1400c16e9  call    _guard_dispatch_icall
0x1400c16ee  movsxd  r14, eax
0x1400c16f1  test    eax, eax
0x1400c16f3  jns     short loc_1400C1746
0x1400c16f5  mov     r8, r14
0x1400c16f8  mov     rdx, [rsi]
0x1400c16fb  mov     ecx, 1
0x1400c1700  call    cs:__imp_WdLogSingleEntry2
0x1400c1707  nop     dword ptr [rax+rax+00h]
0x1400c170c  mov     cs:WdLogGlobalForLineNumber, 2EDh
0x1400c1716  mov     [rsp+98h+var_60], r15
0x1400c171b  mov     [rsp+98h+var_68], r15
0x1400c1720  mov     qword ptr [rsp+98h+Priority], r14
0x1400c1725  mov     rax, [rsi]
0x1400c1728  mov     qword ptr [rsp+98h+BugCheckOnFailure], rax
0x1400c172d  lea     r9, aFailedToGetThe; "Failed to get the size of the memory bl"...
0x1400c1734  mov     edx, 40000h
0x1400c1739  call    DxgkLogInternalTriageEvent
0x1400c173e  mov     eax, r14d
0x1400c1741  jmp     loc_1400C1C13
0x1400c1746  mov     ecx, [rsi+8]
0x1400c1749  lea     eax, [rcx+0FFFh]
0x1400c174f  and     eax, 0FFFFF000h
0x1400c1754  cmp     [rsp+98h+arg_20], eax
0x1400c175b  jnb     short loc_1400C17AE
0x1400c175d  mov     r8d, ecx
0x1400c1760  mov     rbx, 0FFFFFFFFC000000Dh
0x1400c1767  mov     r9, rbx
0x1400c176a  mov     rdx, [rsi]
0x1400c176d  mov     ecx, 1
0x1400c1772  call    cs:__imp_WdLogSingleEntry3
0x1400c1779  nop     dword ptr [rax+rax+00h]
0x1400c177e  mov     cs:WdLogGlobalForLineNumber, 2F6h
0x1400c1788  mov     eax, [rsi+8]
0x1400c178b  mov     [rsp+98h+var_60], r15
0x1400c1790  mov     [rsp+98h+var_68], rbx
0x1400c1795  mov     qword ptr [rsp+98h+Priority], rax
0x1400c179a  mov     rax, [rsi]
0x1400c179d  mov     qword ptr [rsp+98h+BugCheckOnFailure], rax
0x1400c17a2  lea     r9, aMemoryBlock0xI_1; "Memory block  0x%I64x is not large enou"...
0x1400c17a9  jmp     loc_1400C1680
0x1400c17ae  shr     ecx, 0Ch
0x1400c17b1  mov     ebx, ecx
0x1400c17b3  mov     [rsp+98h+MemoryDescriptorList], r15
0x1400c17bb  mov     rcx, [rdi+80h]
0x1400c17c2  mov     rax, [rcx]
0x1400c17c5  mov     r8d, ebx
0x1400c17c8  mov     rax, [rax+18h]
0x1400c17cc  lea     rdx, [rsp+98h+MemoryDescriptorList]
0x1400c17d4  mov     qword ptr [rsp+98h+Priority], rdx
0x1400c17d9  mov     [rsp+98h+BugCheckOnFailure], 1
0x1400c17e1  mov     r9d, 1
0x1400c17e7  mov     rdx, [rsi]
0x1400c17ea  call    _guard_dispatch_icall
0x1400c17ef  movsxd  r14, eax
0x1400c17f2  test    eax, eax
0x1400c17f4  jns     short loc_1400C183A
0x1400c17f6  mov     r8, r14
0x1400c17f9  mov     rdx, [rsi]
0x1400c17fc  mov     ecx, 1
0x1400c1801  call    cs:__imp_WdLogSingleEntry2
0x1400c1808  nop     dword ptr [rax+rax+00h]
0x1400c180d  mov     cs:WdLogGlobalForLineNumber, 30Ah
0x1400c1817  mov     [rsp+98h+var_60], r15
0x1400c181c  mov     [rsp+98h+var_68], r15
0x1400c1821  mov     qword ptr [rsp+98h+Priority], r14
0x1400c1826  mov     rcx, [rsi]
0x1400c1829  mov     qword ptr [rsp+98h+BugCheckOnFailure], rcx
0x1400c182e  lea     r9, aFailedToProbeA_2; "Failed to probe and lock the memory blo"...
0x1400c1835  jmp     loc_1400C1734
0x1400c183a  mov     rax, [rsi]
0x1400c183d  mov     [rdi+70h], rax
0x1400c1841  mov     [rdi+78h], ebx
0x1400c1844  mov     rcx, [rsp+98h+MemoryDescriptorList]; MemoryDescriptorList
0x1400c184c  mov     [rdi+90h], rcx
0x1400c1853  test    byte ptr [rcx+0Ah], 5
0x1400c1857  jz      short loc_1400C185F
0x1400c1859  mov     rax, [rcx+18h]
0x1400c185d  jmp     short loc_1400C1881
0x1400c185f  mov     [rsp+98h+Priority], 10h; Priority
0x1400c1867  mov     [rsp+98h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x1400c186c  xor     r9d, r9d; RequestedAddress
0x1400c186f  xor     edx, edx; AccessMode
0x1400c1871  lea     r8d, [r9+1]; CacheType
0x1400c1875  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400c187c  nop     dword ptr [rax+rax+00h]
0x1400c1881  lea     r14, [rdi+88h]
0x1400c1888  mov     [r14], rax
0x1400c188b  jmp     loc_1400C1B7F
0x1400c1890  mov     [rsp+98h+var_48], r15
0x1400c1895  mov     r14d, 1000h
0x1400c189b  mov     [rsp+98h+arg_28], r14
0x1400c18a3  mov     [rsp+98h+MemoryDescriptorList], r15
0x1400c18ab  mov     rax, cs:?_GlobalFenceStorage@VIDMM_PROCESS_FENCE_STORAGE@@0PEAV1@EA; VIDMM_PROCESS_FENCE_STORAGE * VIDMM_PROCESS_FENCE_STORAGE::_GlobalFenceStorage
0x1400c18b2  cmp     [rcx+0F8h], rax
0x1400c18b9  jz      short loc_1400C18C7
0x1400c18bb  mov     esi, 8040000h
0x1400c18c0  call    ?GetCurrentPartitionHandle@VIDMM_PROCESS@@SAPEAXXZ; VIDMM_PROCESS::GetCurrentPartitionHandle(void)
0x1400c18c5  jmp     short loc_1400C18CF
0x1400c18c7  mov     esi, 8000000h
0x1400c18cc  mov     rax, r15
0x1400c18cf  lea     r15, [rdi+68h]
0x1400c18d3  mov     [rsp+98h+var_60], 0
0x1400c18dc  mov     [rsp+98h+var_68], rax
0x1400c18e1  mov     [rsp+98h+Priority], esi
0x1400c18e5  mov     [rsp+98h+BugCheckOnFailure], 4
0x1400c18ed  lea     r9, [rsp+98h+arg_28]
0x1400c18f5  xor     r8d, r8d
0x1400c18f8  xor     edx, edx
0x1400c18fa  mov     rcx, r15
0x1400c18fd  call    cs:__imp_MmCreateSection
0x1400c1904  nop     dword ptr [rax+rax+00h]
0x1400c1909  mov     esi, eax
0x1400c190b  test    eax, eax
0x1400c190d  jns     short loc_1400C191B
0x1400c190f  mov     qword ptr [r15], 0
0x1400c1916  jmp     loc_1400C1C09
0x1400c191b  mov     [rsp+98h+MemoryDescriptorList], r14
0x1400c1923  lea     r14, [rdi+88h]
0x1400c192a  mov     qword ptr [rsp+98h+BugCheckOnFailure], 0
0x1400c1933  lea     r9, [rsp+98h+var_48]
0x1400c1938  lea     r8, [rsp+98h+MemoryDescriptorList]
0x1400c1940  mov     rdx, r14
0x1400c1943  mov     rcx, [r15]
0x1400c1946  call    cs:__imp_MmMapViewInSystemSpaceEx
0x1400c194d  nop     dword ptr [rax+rax+00h]
0x1400c1952  movsxd  rsi, eax
0x1400c1955  xor     r15d, r15d
0x1400c1958  test    eax, eax
0x1400c195a  jns     short loc_1400C19AA
0x1400c195c  lock inc cs:dword_1400877AC
0x1400c1963  mov     rdx, rsi
0x1400c1966  lea     ecx, [r15+6]
0x1400c196a  call    cs:__imp_WdLogSingleEntry1
0x1400c1971  nop     dword ptr [rax+rax+00h]
0x1400c1976  mov     cs:WdLogGlobalForLineNumber, 352h
0x1400c1980  mov     [rsp+98h+var_60], r15
0x1400c1985  mov     [rsp+98h+var_68], r15
0x1400c198a  mov     qword ptr [rsp+98h+Priority], r15
0x1400c198f  mov     qword ptr [rsp+98h+BugCheckOnFailure], rsi
0x1400c1994  lea     r9, aFailedToMapSys; "Failed to map system space view of fenc"...
0x1400c199b  mov     edx, 40001h
0x1400c19a0  call    DxgkLogInternalTriageEvent
0x1400c19a5  jmp     loc_1400C1C09
0x1400c19aa  mov     esi, 1000h
0x1400c19af  mov     edx, esi; Length
0x1400c19b1  mov     rcx, [r14]; Base
0x1400c19b4  call    ?VidMmiAllocateMdl@@YAPEAU_MDL@@PEAX_K@Z; VidMmiAllocateMdl(void *,unsigned __int64)
0x1400c19b9  mov     [rdi+90h], rax
0x1400c19c0  test    rax, rax
0x1400c19c3  jnz     short loc_1400C1A15
0x1400c19c5  lock inc cs:?gVidMmLowResourceAccumulated@@3U_VIDMM_LOW_RESOURCE@@A; _VIDMM_LOW_RESOURCE gVidMmLowResourceAccumulated
0x1400c19cc  lea     ecx, [rax+6]
0x1400c19cf  call    cs:__imp_WdLogSingleEntry0
0x1400c19d6  nop     dword ptr [rax+rax+00h]
0x1400c19db  mov     eax, 35Eh
0x1400c19e0  mov     cs:WdLogGlobalForLineNumber, eax
0x1400c19e6  mov     [rsp+98h+var_60], r15
0x1400c19eb  mov     [rsp+98h+var_68], r15
0x1400c19f0  mov     qword ptr [rsp+98h+Priority], r15
0x1400c19f5  mov     qword ptr [rsp+98h+BugCheckOnFailure], rax
0x1400c19fa  lea     r9, aFailedToAlloca_63; "Failed to allocate memory for fence sto"...
0x1400c1a01  mov     edx, 40001h
0x1400c1a06  call    DxgkLogInternalTriageEvent
0x1400c1a0b  mov     esi, 0C0000017h
0x1400c1a10  jmp     loc_1400C1C09
0x1400c1a15  xor     edx, edx; AccessMode
0x1400c1a17  lea     r8d, [rdx+2]; Operation
0x1400c1a1b  mov     rcx, rax; MemoryDescriptorList
0x1400c1a1e  call    cs:__imp_MmProbeAndLockPages
0x1400c1a25  nop     dword ptr [rax+rax+00h]
0x1400c1a2a  nop
0x1400c1a2b  mov     rcx, [rdi+0F8h]
0x1400c1a32  cmp     [rcx+90h], r15b
0x1400c1a39  jnz     short loc_1400C1A44
0x1400c1a3b  test    rbx, rbx
0x1400c1a3e  jz      loc_1400C1B7F
0x1400c1a44  test    rbx, rbx
0x1400c1a47  jz      short loc_1400C1A56
0x1400c1a49  mov     rcx, rbx; this
0x1400c1a4c  call    ?GetVmwpProcess@VIDMM_PROCESS@@QEAAPEAV1@XZ; VIDMM_PROCESS::GetVmwpProcess(void)
0x1400c1a51  mov     rcx, rax
0x1400c1a54  jmp     short loc_1400C1A59
0x1400c1a56  mov     rcx, [rcx]; this
0x1400c1a59  mov     [rdi+20h], rcx
0x1400c1a5d  lea     rax, [rdi+0E0h]
0x1400c1a64  lea     r9, [rdi+0E8h]; void **
0x1400c1a6b  mov     qword ptr [rsp+98h+BugCheckOnFailure], rax; unsigned __int64 *
0x1400c1a70  mov     r8, rsi; unsigned __int64
0x1400c1a73  mov     rdx, [rdi+90h]; struct _MDL *
0x1400c1a7a  call    ?MapHostAddressesToGuest@VIDMM_PROCESS@@QEAAJPEAU_MDL@@_KPEAPEAXPEA_K@Z; VIDMM_PROCESS::MapHostAddressesToGuest(_MDL *,unsigned __int64,void * *,unsigned __int64 *)
0x1400c1a7f  mov     esi, eax
0x1400c1a81  test    eax, eax
0x1400c1a83  jns     short loc_1400C1AC6
0x1400c1a85  mov     ecx, 1
0x1400c1a8a  call    cs:__imp_WdLogSingleEntry0
0x1400c1a91  nop     dword ptr [rax+rax+00h]
0x1400c1a96  mov     eax, 3A8h
0x1400c1a9b  mov     cs:WdLogGlobalForLineNumber, eax
0x1400c1aa1  mov     [rsp+98h+var_60], r15
0x1400c1aa6  mov     [rsp+98h+var_68], r15
0x1400c1aab  mov     qword ptr [rsp+98h+Priority], r15
0x1400c1ab0  mov     qword ptr [rsp+98h+BugCheckOnFailure], rax
0x1400c1ab5  lea     r9, aFailedToAlloca_6; "Failed to allocate fence storage page f"...
0x1400c1abc  mov     edx, 40000h
0x1400c1ac1  jmp     loc_1400C19A0
0x1400c1ac6  mov     rax, [rdi+0F8h]
0x1400c1acd  cmp     [rax+90h], r15b
0x1400c1ad4  jnz     loc_1400C1B7F
0x1400c1ada  cmp     [rax], r15
0x1400c1add  jz      short loc_1400C1B20
0x1400c1adf  mov     ecx, 1
0x1400c1ae4  call    cs:__imp_WdLogSingleEntry0
0x1400c1aeb  nop     dword ptr [rax+rax+00h]
0x1400c1af0  mov     eax, 3B9h
0x1400c1af5  mov     cs:WdLogGlobalForLineNumber, eax
0x1400c1afb  mov     [rsp+98h+var_60], r15
0x1400c1b00  mov     [rsp+98h+var_68], r15
0x1400c1b05  mov     qword ptr [rsp+98h+Priority], r15
0x1400c1b0a  mov     qword ptr [rsp+98h+BugCheckOnFailure], rax
0x1400c1b0f  lea     r9, aProcessfencest; "_ProcessFenceStorage.GetVidMmProcess() "...
0x1400c1b16  mov     edx, 40002h
0x1400c1b1b  call    DxgkLogInternalTriageEvent
0x1400c1b20  mov     rax, [rdi+0F8h]
0x1400c1b27  mov     byte ptr [rax+91h], 1
0x1400c1b2e  mov     byte ptr [rdi+0F0h], 1
0x1400c1b35  mov     rcx, [rdi+20h]; this
0x1400c1b39  call    ?GetVmwpProcess@VIDMM_PROCESS@@QEAAPEAV1@XZ; VIDMM_PROCESS::GetVmwpProcess(void)
0x1400c1b3e  mov     rbx, rax
0x1400c1b41  lea     rdx, [rax+70h]; struct DXGPUSHLOCK *
0x1400c1b45  lea     rcx, [rsp+98h+var_40]; this
0x1400c1b4a  call    ??0DXGAUTOPUSHLOCKEXCLUSIVE@@QEAA@QEAVDXGPUSHLOCK@@@Z; DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(DXGPUSHLOCK * const)
0x1400c1b4f  add     rbx, 60h ; '`'
0x1400c1b53  mov     rcx, [rbx]
0x1400c1b56  cmp     [rcx+8], rbx
0x1400c1b5a  jz      short loc_1400C1B63
0x1400c1b5c  mov     ecx, 3
0x1400c1b61  int     29h; Win8: RtlFailFast(ecx)
0x1400c1b63  lea     rax, [rdi+10h]
0x1400c1b67  mov     [rax], rcx
0x1400c1b6a  mov     [rax+8], rbx
0x1400c1b6e  mov     [rcx+8], rax
0x1400c1b72  mov     [rbx], rax
0x1400c1b75  lea     rcx, [rsp+98h+var_40]; this
0x1400c1b7a  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1400c1b7f  mov     rax, [r14]
0x1400c1b82  mov     [rdi+0D0h], rax
0x1400c1b89  mov     [rdi+0A0h], r12
0x1400c1b90  mov     eax, [r13+34h]
  ... truncated ...
```
