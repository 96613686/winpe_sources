# VIDMM_FENCE_STORAGE_PAGE::MapCpuVA(VIDMM_PROCESS *,VIDMM_DEVICE *,VIDMM_MONITORED_FENCE_STORAGE *,bool,bool,void * *,ulong)

- ea: `0x140115784`
- end: `0x140115c50`
- name: `?MapCpuVA@VIDMM_FENCE_STORAGE_PAGE@@QEAAJPEAVVIDMM_PROCESS@@PEAVVIDMM_DEVICE@@PEAUVIDMM_MONITORED_FENCE_STORAGE@@_N3PEAPEAXK@Z`
- size: `1228`
- prototype: `__int64 __fastcall(VIDMM_FENCE_STORAGE_PAGE *this, struct VIDMM_PROCESS *, struct VIDMM_DEVICE *, struct VIDMM_MONITORED_FENCE_STORAGE *, bool, bool, void **, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1401156fc`

## callees

- `0x140004268`
- `0x14002c5d0`
- `0x14002f7d0`
- `0x140031434`
- `0x14003196c`
- `0x140048860`
- `0x140058f50`
- `0x140059030`
- `0x1400c120c`
- `0x140115784`

## import_xrefs

- `ntoskrnl!PsGetProcessWow64Process` at `0x140115900`
- `ntoskrnl!PsGetProcessWow64Process` at `0x140115900`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140115997`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140115997`
- `ntoskrnl!MmUnmapLockedPages` at `0x140115c03`
- `ntoskrnl!MmUnmapLockedPages` at `0x140115c03`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14011583f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14011583f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140115850`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140115850`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140115b39`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140115b8c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140115b39`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140115b8c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140115b45`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140115b98`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140115b45`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140115b98`
- `ntoskrnl!ExFreePoolWithTag` at `0x140115c3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140115c3c`
- `ntoskrnl!ExAllocatePool2` at `0x1401158ab`
- `ntoskrnl!ExAllocatePool2` at `0x1401158ab`
- `watchdog!WdLogSingleEntry0` at `0x1401157eb`
- `watchdog!WdLogSingleEntry0` at `0x140115ae2`
- `watchdog!WdLogSingleEntry0` at `0x1401157eb`
- `watchdog!WdLogSingleEntry0` at `0x140115ae2`
- `watchdog!WdLogSingleEntry1` at `0x1401159d8`
- `watchdog!WdLogSingleEntry1` at `0x1401159d8`

## pseudocode

```c
__int64 __fastcall VIDMM_FENCE_STORAGE_PAGE::MapCpuVA(
        VIDMM_FENCE_STORAGE_PAGE *this,
        struct VIDMM_PROCESS *a2,
        struct VIDMM_DEVICE *a3,
        struct VIDMM_MONITORED_FENCE_STORAGE *a4,
        bool a5,
        bool a6,
        void **a7,
        unsigned int a8)
{
  void **v10; // rdi
  struct VIDMM_PROCESS *v11; // rsi
  int v12; // ecx
  int v13; // r8d
  char *v14; // rbx
  __int64 v15; // r14
  char *v16; // r12
  char *i; // rax
  __int64 Pool2; // rax
  unsigned int v19; // r12d
  void *v20; // rax
  __int64 v21; // rax
  struct VIDMM_PROCESS *v22; // rax
  PVOID v23; // rax
  int v24; // ecx
  int v25; // r8d
  char **v27; // rcx
  __int64 v28; // rdi
  const struct DXGK_VIRTUAL_MEMORY_INTERFACE *VirtualMemoryInterface; // rax
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rbx
  const struct DXGK_VIRTUAL_MEMORY_INTERFACE *v33; // rax
  int v34; // [rsp+60h] [rbp-C8h]
  unsigned __int64 v35; // [rsp+68h] [rbp-C0h] BYREF
  char *v36; // [rsp+70h] [rbp-B8h]
  void *v37; // [rsp+78h] [rbp-B0h]
  void **v38; // [rsp+80h] [rbp-A8h]
  PVOID v39; // [rsp+88h] [rbp-A0h]
  char *v40; // [rsp+90h] [rbp-98h]
  __int64 v41; // [rsp+98h] [rbp-90h] BYREF
  _BYTE v42[64]; // [rsp+A0h] [rbp-88h] BYREF

  v10 = a7;
  v38 = a7;
  v11 = 0;
  *a7 = 0;
  if ( a2 && (*(_DWORD *)(*((_QWORD *)a2 + 10) + 408LL) & 0x100) != 0 )
  {
    if ( !*((_QWORD *)this + 28) )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 1495;
      DxgkLogInternalTriageEvent(v12, 262146, v13, (unsigned int)L"_GuestPhysicalAddress", 1495, 0, 0, 0);
    }
    *a7 = (void *)*((_QWORD *)this + 28);
    return 0;
  }
  v14 = (char *)this + 72;
  v36 = (char *)this + 72;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx((char *)this + 72, 0);
  *((_QWORD *)this + 10) = KeGetCurrentThread();
  v15 = 0;
  v16 = (char *)this + 40;
  v40 = (char *)this + 40;
  for ( i = (char *)*((_QWORD *)this + 5); i != v16; i = *(char **)i )
  {
    if ( a2 == *((struct VIDMM_PROCESS **)i - 1) )
    {
      v15 = (__int64)(i - 16);
      ++*((_DWORD *)i + 4);
      break;
    }
  }
  if ( v15 )
  {
LABEL_35:
    *v10 = (void *)(*(_QWORD *)v15 + *((unsigned int *)a4 + 4));
    *((_QWORD *)v14 + 1) = 0;
    ExReleasePushLockExclusiveEx(v14, 0);
    KeLeaveCriticalRegion();
    return 0;
  }
  Pool2 = ExAllocatePool2(64, 40, 1700882774);
  v15 = Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)(Pool2 + 32) = 1;
    *(_QWORD *)(Pool2 + 8) = a2;
    v41 = 0;
    v35 = 4096;
    v20 = (void *)*((_QWORD *)a2 + 2);
    v37 = v20;
    if ( !a8 )
    {
      if ( PsGetProcessWow64Process(v20) || (a8 = 2, a5) )
        a8 = 4;
    }
    if ( VIDMM_FENCE_STORAGE_PAGE::IsGuestPresentFence(this) )
    {
      if ( DXGPROCESS::GetCurrent() && (v21 = *((_QWORD *)DXGPROCESS::GetCurrent() + 8)) != 0 )
        v22 = *(struct VIDMM_PROCESS **)(v21 + 8);
      else
        v22 = 0;
      VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)v42, a2, v22 != a2);
      v23 = MmMapLockedPagesSpecifyCache(*((PMDL *)this + 18), 1, MmCached, 0, 0, 0x40000010u);
      v39 = v23;
      if ( !v23 )
      {
        WdLogSingleEntry1(1, -1073741670);
        WdLogGlobalForLineNumber = 1616;
        DxgkLogInternalTriageEvent(
          v24,
          0x40000,
          v25,
          (unsigned int)L"Failed to map the fence storage page to user mode, returning 0x%I64x.",
          -1073741670,
          0,
          0,
          0);
        VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)v42);
        return 3221225626LL;
      }
      *(_QWORD *)v15 = v23;
      VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)v42);
      goto LABEL_27;
    }
    v28 = *((_QWORD *)this + 13);
    VirtualMemoryInterface = DxgkGetVirtualMemoryInterface();
    v30 = (*((__int64 (__fastcall **)(__int64, void *, __int64, _QWORD, unsigned __int64, __int64 *, unsigned __int64 *, int, _DWORD, unsigned int))VirtualMemoryInterface
           + 3))(
            v28,
            v37,
            v15,
            0,
            v35,
            &v41,
            &v35,
            2,
            0,
            a8);
    if ( v30 < 0 )
    {
      v19 = v30;
    }
    else
    {
      if ( !a5 || !a6 || (v34 = VidMmiEnsureVirtualAddressRangeValid(*(void **)v15, v35), v34 >= 0) )
      {
LABEL_27:
        v27 = (char **)*((_QWORD *)this + 6);
        if ( *v27 != v16 )
          __fastfail(3u);
        *(_QWORD *)(v15 + 16) = v16;
        *(_QWORD *)(v15 + 24) = v27;
        *v27 = (char *)(v15 + 16);
        *((_QWORD *)this + 6) = v15 + 16;
        v14 = v36;
        v10 = v38;
        goto LABEL_35;
      }
      WdLogSingleEntry0(3);
      WdLogGlobalForLineNumber = 1650;
      v19 = v34;
    }
    v14 = v36;
    goto LABEL_39;
  }
  v19 = -1073741801;
LABEL_39:
  *((_QWORD *)v14 + 1) = 0;
  ExReleasePushLockExclusiveEx(v14, 0);
  KeLeaveCriticalRegion();
  if ( v15 )
  {
    v37 = *(void **)v15;
    if ( v37 )
    {
      if ( VIDMM_FENCE_STORAGE_PAGE::IsGuestPresentFence(this) )
      {
        if ( DXGPROCESS::GetCurrent() )
        {
          v31 = *((_QWORD *)DXGPROCESS::GetCurrent() + 8);
          if ( v31 )
            v11 = *(struct VIDMM_PROCESS **)(v31 + 8);
        }
        VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)v42, a2, v11 != a2);
        MmUnmapLockedPages(*(PVOID *)v15, *((PMDL *)this + 18));
        VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH((VIDMM_PROCESS_AUTOATTACH *)v42);
      }
      else
      {
        v32 = *((_QWORD *)a2 + 2);
        v33 = DxgkGetVirtualMemoryInterface();
        (*((void (__fastcall **)(__int64, void *))v33 + 4))(v32, v37);
      }
    }
    ExFreePoolWithTag((PVOID)v15, 0);
  }
  return v19;
}

```

## disassembly

```asm
0x140115784  mov     [rsp+arg_18], r9
0x140115789  push    rbx
0x14011578a  push    rsi
0x14011578b  push    rdi
0x14011578c  push    r12
0x14011578e  push    r13
0x140115790  push    r14
0x140115792  push    r15
0x140115794  sub     rsp, 0F0h
0x14011579b  mov     rax, cs:__security_cookie
0x1401157a2  xor     rax, rsp
0x1401157a5  mov     [rsp+128h+var_48], rax
0x1401157ad  mov     r15, rdx
0x1401157b0  mov     r13, rcx
0x1401157b3  mov     rdi, [rsp+128h+arg_30]
0x1401157bb  mov     [rsp+128h+var_A8], rdi
0x1401157c3  xor     esi, esi
0x1401157c5  mov     [rdi], rsi
0x1401157c8  test    rdx, rdx
0x1401157cb  jz      short loc_140115836
0x1401157cd  mov     rax, [rdx+50h]
0x1401157d1  mov     ecx, [rax+198h]
0x1401157d7  shr     ecx, 8
0x1401157da  test    cl, 1
0x1401157dd  jz      short loc_140115836
0x1401157df  cmp     [r13+0E0h], rsi
0x1401157e6  jnz     short loc_140115827
0x1401157e8  lea     ecx, [rsi+1]
0x1401157eb  call    cs:__imp_WdLogSingleEntry0
0x1401157f2  nop     dword ptr [rax+rax+00h]
0x1401157f7  mov     eax, 5D7h
0x1401157fc  mov     cs:WdLogGlobalForLineNumber, eax
0x140115802  mov     [rsp+128h+var_F0], rsi
0x140115807  mov     [rsp+128h+var_F8], rsi
0x14011580c  mov     qword ptr [rsp+128h+Priority], rsi
0x140115811  mov     qword ptr [rsp+128h+BugCheckOnFailure], rax
0x140115816  lea     r9, aGuestphysicala; "_GuestPhysicalAddress"
0x14011581d  mov     edx, 40002h
0x140115822  call    DxgkLogInternalTriageEvent
0x140115827  mov     rax, [r13+0E0h]
0x14011582e  mov     [rdi], rax
0x140115831  jmp     loc_140115B51
0x140115836  lea     rbx, [r13+48h]
0x14011583a  mov     [rsp+128h+var_B8], rbx
0x14011583f  call    cs:__imp_KeEnterCriticalRegion
0x140115846  nop     dword ptr [rax+rax+00h]
0x14011584b  xor     edx, edx
0x14011584d  mov     rcx, rbx
0x140115850  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140115857  nop     dword ptr [rax+rax+00h]
0x14011585c  mov     rax, gs:188h
0x140115865  mov     [rbx+8], rax
0x140115869  mov     r14, rsi
0x14011586c  lea     r12, [r13+28h]
0x140115870  mov     [rsp+128h+var_98], r12
0x140115878  mov     rax, [r12]
0x14011587c  jmp     short loc_140115887
0x14011587e  cmp     r15, [rax-8]
0x140115882  jz      short loc_14011588E
0x140115884  mov     rax, [rax]
0x140115887  cmp     rax, r12
0x14011588a  jnz     short loc_14011587E
0x14011588c  jmp     short loc_140115895
0x14011588e  lea     r14, [rax-10h]
0x140115892  inc     dword ptr [rax+10h]
0x140115895  test    r14, r14
0x140115898  jnz     loc_140115B1F
0x14011589e  lea     edx, [r14+28h]
0x1401158a2  lea     ecx, [rdx+18h]
0x1401158a5  mov     r8d, 65616956h
0x1401158ab  call    cs:__imp_ExAllocatePool2
0x1401158b2  nop     dword ptr [rax+rax+00h]
0x1401158b7  mov     r14, rax
0x1401158ba  mov     [rsp+128h+var_C8], rax
0x1401158bf  test    rax, rax
0x1401158c2  jnz     short loc_1401158CF
0x1401158c4  mov     r12d, 0C0000017h
0x1401158ca  jmp     loc_140115B7F
0x1401158cf  mov     dword ptr [rax+20h], 1
0x1401158d6  mov     [rax+8], r15
0x1401158da  mov     [rsp+128h+var_90], rsi
0x1401158e2  mov     [rsp+128h+var_C0], 1000h
0x1401158eb  mov     rax, [r15+10h]
0x1401158ef  mov     [rsp+128h+var_B0], rax
0x1401158f4  cmp     [rsp+128h+arg_38], esi
0x1401158fb  jnz     short loc_140115931
0x1401158fd  mov     rcx, rax
0x140115900  call    cs:__imp_PsGetProcessWow64Process
0x140115907  nop     dword ptr [rax+rax+00h]
0x14011590c  test    rax, rax
0x14011590f  jnz     short loc_140115926
0x140115911  cmp     [rsp+128h+arg_20], sil
0x140115919  mov     [rsp+128h+arg_38], 2
0x140115924  jz      short loc_140115931
0x140115926  mov     [rsp+128h+arg_38], 4
0x140115931  mov     rcx, r13; this
0x140115934  call    ?IsGuestPresentFence@VIDMM_FENCE_STORAGE_PAGE@@QEAA_NXZ; VIDMM_FENCE_STORAGE_PAGE::IsGuestPresentFence(void)
0x140115939  test    al, al
0x14011593b  jz      loc_140115A4C
0x140115941  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x140115946  test    rax, rax
0x140115949  jz      short loc_14011595F
0x14011594b  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x140115950  mov     rax, [rax+40h]
0x140115954  test    rax, rax
0x140115957  jz      short loc_14011595F
0x140115959  mov     rax, [rax+8]
0x14011595d  jmp     short loc_140115962
0x14011595f  mov     rax, rsi
0x140115962  cmp     rax, r15
0x140115965  setnz   r8b; bool
0x140115969  mov     rdx, r15; struct VIDMM_PROCESS *
0x14011596c  lea     rcx, [rsp+128h+var_88]; this
0x140115974  call    ??0VIDMM_PROCESS_AUTOATTACH@@QEAA@PEAVVIDMM_PROCESS@@_N@Z; VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(VIDMM_PROCESS *,bool)
0x140115979  nop
0x14011597a  mov     [rsp+128h+Priority], 40000010h; Priority
0x140115982  mov     [rsp+128h+BugCheckOnFailure], esi; BugCheckOnFailure
0x140115986  xor     r9d, r9d; RequestedAddress
0x140115989  lea     r8d, [r9+1]; CacheType
0x14011598d  mov     dl, r8b; AccessMode
0x140115990  mov     rcx, [r13+90h]; MemoryDescriptorList
0x140115997  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14011599e  nop     dword ptr [rax+rax+00h]
0x1401159a3  mov     [rsp+128h+var_A0], rax
0x1401159ab  jmp     short loc_1401159C6
0x1401159ad  xor     eax, eax
0x1401159af  mov     [rsp+128h+var_A0], rax
0x1401159b7  xor     esi, esi
0x1401159b9  mov     r14, [rsp+128h+var_C8]
0x1401159be  mov     r12, [rsp+128h+var_98]
0x1401159c6  test    rax, rax
0x1401159c9  jnz     short loc_140115A27
0x1401159cb  mov     rbx, 0FFFFFFFFC000009Ah
0x1401159d2  mov     rdx, rbx
0x1401159d5  lea     ecx, [rax+1]
0x1401159d8  call    cs:__imp_WdLogSingleEntry1
0x1401159df  nop     dword ptr [rax+rax+00h]
0x1401159e4  mov     cs:WdLogGlobalForLineNumber, 650h
0x1401159ee  mov     [rsp+128h+var_F0], rsi
0x1401159f3  mov     [rsp+128h+var_F8], rsi
0x1401159f8  mov     qword ptr [rsp+128h+Priority], rsi
0x1401159fd  mov     qword ptr [rsp+128h+BugCheckOnFailure], rbx
0x140115a02  lea     r9, aFailedToMapThe; "Failed to map the fence storage page to"...
0x140115a09  mov     edx, 40000h
0x140115a0e  call    DxgkLogInternalTriageEvent
0x140115a13  lea     rcx, [rsp+128h+var_88]; this
0x140115a1b  call    ??1VIDMM_PROCESS_AUTOATTACH@@QEAA@XZ; VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH(void)
0x140115a20  mov     eax, ebx
0x140115a22  jmp     loc_140115B53
0x140115a27  mov     [r14], rax
0x140115a2a  lea     rcx, [rsp+128h+var_88]; this
0x140115a32  call    ??1VIDMM_PROCESS_AUTOATTACH@@QEAA@XZ; VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH(void)
0x140115a37  mov     rcx, [r12+8]
0x140115a3c  cmp     [rcx], r12
0x140115a3f  jz      loc_140115AFF
0x140115a45  mov     ecx, 3
0x140115a4a  int     29h; Win8: RtlFailFast(ecx)
0x140115a4c  mov     rbx, [rsp+128h+var_C0]
0x140115a51  mov     rdi, [r13+68h]
0x140115a55  call    ?DxgkGetVirtualMemoryInterface@@YAPEBUDXGK_VIRTUAL_MEMORY_INTERFACE@@XZ; DxgkGetVirtualMemoryInterface(void)
0x140115a5a  mov     rax, [rax+18h]
0x140115a5e  mov     ecx, [rsp+128h+arg_38]
0x140115a65  mov     [rsp+128h+var_E0], ecx
0x140115a69  mov     [rsp+128h+var_E8], esi
0x140115a6d  mov     dword ptr [rsp+128h+var_F0], 2
0x140115a75  lea     rcx, [rsp+128h+var_C0]
0x140115a7a  mov     [rsp+128h+var_F8], rcx
0x140115a7f  lea     rcx, [rsp+128h+var_90]
0x140115a87  mov     qword ptr [rsp+128h+Priority], rcx
0x140115a8c  mov     qword ptr [rsp+128h+BugCheckOnFailure], rbx
0x140115a91  xor     r9d, r9d
0x140115a94  mov     r8, r14
0x140115a97  mov     rdx, [rsp+128h+var_B0]
0x140115a9c  mov     rcx, rdi
0x140115a9f  call    _guard_dispatch_icall
0x140115aa4  test    eax, eax
0x140115aa6  js      loc_140115B77
0x140115aac  cmp     [rsp+128h+arg_20], sil
0x140115ab4  jz      short loc_140115A37
0x140115ab6  cmp     [rsp+128h+arg_28], sil
0x140115abe  jz      loc_140115A37
0x140115ac4  mov     rdx, [rsp+128h+var_C0]; unsigned __int64
0x140115ac9  mov     rcx, [r14]; void *
0x140115acc  call    ?VidMmiEnsureVirtualAddressRangeValid@@YAJPEAX_K@Z; VidMmiEnsureVirtualAddressRangeValid(void *,unsigned __int64)
0x140115ad1  mov     dword ptr [rsp+128h+var_C8], eax
0x140115ad5  test    eax, eax
0x140115ad7  jns     loc_140115A37
0x140115add  mov     ecx, 3
0x140115ae2  call    cs:__imp_WdLogSingleEntry0
0x140115ae9  nop     dword ptr [rax+rax+00h]
0x140115aee  mov     cs:WdLogGlobalForLineNumber, 672h
0x140115af8  mov     r12d, dword ptr [rsp+128h+var_C8]
0x140115afd  jmp     short loc_140115B7A
0x140115aff  lea     rax, [r14+10h]
0x140115b03  mov     [rax], r12
0x140115b06  mov     [rax+8], rcx
0x140115b0a  mov     [rcx], rax
0x140115b0d  mov     [r12+8], rax
0x140115b12  mov     rbx, [rsp+128h+var_B8]
0x140115b17  mov     rdi, [rsp+128h+var_A8]
0x140115b1f  mov     rax, [rsp+128h+arg_18]
0x140115b27  mov     eax, [rax+10h]
0x140115b2a  add     rax, [r14]
0x140115b2d  mov     [rdi], rax
0x140115b30  mov     [rbx+8], rsi
0x140115b34  xor     edx, edx
0x140115b36  mov     rcx, rbx
0x140115b39  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140115b40  nop     dword ptr [rax+rax+00h]
0x140115b45  call    cs:__imp_KeLeaveCriticalRegion
0x140115b4c  nop     dword ptr [rax+rax+00h]
0x140115b51  xor     eax, eax
0x140115b53  mov     rcx, [rsp+128h+var_48]
0x140115b5b  xor     rcx, rsp; StackCookie
0x140115b5e  call    __security_check_cookie
0x140115b63  add     rsp, 0F0h
0x140115b6a  pop     r15
0x140115b6c  pop     r14
0x140115b6e  pop     r13
0x140115b70  pop     r12
0x140115b72  pop     rdi
0x140115b73  pop     rsi
0x140115b74  pop     rbx
0x140115b75  retn
0x140115b77  mov     r12d, eax
0x140115b7a  mov     rbx, [rsp+128h+var_B8]
0x140115b7f  lea     rdi, [r15+10h]
0x140115b83  mov     [rbx+8], rsi
0x140115b87  xor     edx, edx
0x140115b89  mov     rcx, rbx
0x140115b8c  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140115b93  nop     dword ptr [rax+rax+00h]
0x140115b98  call    cs:__imp_KeLeaveCriticalRegion
0x140115b9f  nop     dword ptr [rax+rax+00h]
0x140115ba4  test    r14, r14
0x140115ba7  jz      loc_140115C48
0x140115bad  mov     rax, [r14]
0x140115bb0  mov     [rsp+128h+var_B0], rax
0x140115bb5  test    rax, rax
0x140115bb8  jz      short loc_140115C37
0x140115bba  mov     rcx, r13; this
0x140115bbd  call    ?IsGuestPresentFence@VIDMM_FENCE_STORAGE_PAGE@@QEAA_NXZ; VIDMM_FENCE_STORAGE_PAGE::IsGuestPresentFence(void)
0x140115bc2  test    al, al
0x140115bc4  jz      short loc_140115C1E
0x140115bc6  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x140115bcb  test    rax, rax
0x140115bce  jz      short loc_140115BE2
0x140115bd0  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x140115bd5  mov     rcx, [rax+40h]
0x140115bd9  test    rcx, rcx
0x140115bdc  jz      short loc_140115BE2
0x140115bde  mov     rsi, [rcx+8]
0x140115be2  cmp     rsi, r15
0x140115be5  setnz   r8b; bool
0x140115be9  mov     rdx, r15; struct VIDMM_PROCESS *
0x140115bec  lea     rcx, [rsp+128h+var_88]; this
0x140115bf4  call    ??0VIDMM_PROCESS_AUTOATTACH@@QEAA@PEAVVIDMM_PROCESS@@_N@Z; VIDMM_PROCESS_AUTOATTACH::VIDMM_PROCESS_AUTOATTACH(VIDMM_PROCESS *,bool)
0x140115bf9  mov     rdx, [r13+90h]; MemoryDescriptorList
0x140115c00  mov     rcx, [r14]; BaseAddress
0x140115c03  call    cs:__imp_MmUnmapLockedPages
0x140115c0a  nop     dword ptr [rax+rax+00h]
0x140115c0f  lea     rcx, [rsp+128h+var_88]; this
0x140115c17  call    ??1VIDMM_PROCESS_AUTOATTACH@@QEAA@XZ; VIDMM_PROCESS_AUTOATTACH::~VIDMM_PROCESS_AUTOATTACH(void)
0x140115c1c  jmp     short loc_140115C37
0x140115c1e  mov     rbx, [rdi]
0x140115c21  call    ?DxgkGetVirtualMemoryInterface@@YAPEBUDXGK_VIRTUAL_MEMORY_INTERFACE@@XZ; DxgkGetVirtualMemoryInterface(void)
0x140115c26  mov     rax, [rax+20h]
0x140115c2a  mov     rdx, [rsp+128h+var_B0]
0x140115c2f  mov     rcx, rbx
0x140115c32  call    _guard_dispatch_icall
0x140115c37  xor     edx, edx; Tag
0x140115c39  mov     rcx, r14; P
0x140115c3c  call    cs:__imp_ExFreePoolWithTag
0x140115c43  nop     dword ptr [rax+rax+00h]
0x140115c48  mov     eax, r12d
0x140115c4b  jmp     loc_140115B53
```
