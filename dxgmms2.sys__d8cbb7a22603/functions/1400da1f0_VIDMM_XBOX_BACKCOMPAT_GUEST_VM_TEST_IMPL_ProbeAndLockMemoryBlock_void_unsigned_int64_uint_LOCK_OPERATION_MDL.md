# VIDMM_XBOX_BACKCOMPAT_GUEST_VM_TEST_IMPL::ProbeAndLockMemoryBlock(void *,unsigned __int64,uint,_LOCK_OPERATION,_MDL * *)

- ea: `0x1400da1f0`
- end: `0x1400da6f5`
- name: `?ProbeAndLockMemoryBlock@VIDMM_XBOX_BACKCOMPAT_GUEST_VM_TEST_IMPL@@UEAAJPEAX_KIW4_LOCK_OPERATION@@PEAPEAU_MDL@@@Z`
- size: `1285`
- prototype: `__int64 __fastcall(VIDMM_XBOX_BACKCOMPAT_GUEST_VM_TEST_IMPL *this, __int64, __int64, int, LOCK_OPERATION Operation, PMDL)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140004268`
- `0x1400128c8`
- `0x14002eb80`
- `0x14002f2a8`
- `0x1400da1f0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400da36a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400da36a`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400da30e`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400da40b`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400da30e`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400da40b`
- `ntoskrnl!MmUnlockPages` at `0x1400da5e0`
- `ntoskrnl!MmUnlockPages` at `0x1400da5e0`
- `ntoskrnl!IoAllocateMdl` at `0x1400da23e`
- `ntoskrnl!IoAllocateMdl` at `0x1400da38f`
- `ntoskrnl!IoAllocateMdl` at `0x1400da23e`
- `ntoskrnl!IoAllocateMdl` at `0x1400da38f`
- `ntoskrnl!IoFreeMdl` at `0x1400da49c`
- `ntoskrnl!IoFreeMdl` at `0x1400da619`
- `ntoskrnl!IoFreeMdl` at `0x1400da6a6`
- `ntoskrnl!IoFreeMdl` at `0x1400da49c`
- `ntoskrnl!IoFreeMdl` at `0x1400da619`
- `ntoskrnl!IoFreeMdl` at `0x1400da6a6`
- `watchdog!WdLogSingleEntry2` at `0x1400da451`
- `watchdog!WdLogSingleEntry2` at `0x1400da54d`
- `watchdog!WdLogSingleEntry2` at `0x1400da65b`
- `watchdog!WdLogSingleEntry2` at `0x1400da451`
- `watchdog!WdLogSingleEntry2` at `0x1400da54d`
- `watchdog!WdLogSingleEntry2` at `0x1400da65b`
- `watchdog!WdLogSingleEntry1` at `0x1400da26e`
- `watchdog!WdLogSingleEntry1` at `0x1400da4ff`
- `watchdog!WdLogSingleEntry1` at `0x1400da26e`
- `watchdog!WdLogSingleEntry1` at `0x1400da4ff`

## pseudocode

```c
__int64 __fastcall VIDMM_XBOX_BACKCOMPAT_GUEST_VM_TEST_IMPL::ProbeAndLockMemoryBlock(
        VIDMM_XBOX_BACKCOMPAT_GUEST_VM_TEST_IMPL *this,
        __int64 a2,
        __int64 a3,
        int a4,
        LOCK_OPERATION Operation,
        PMDL a6)
{
  ULONG v7; // edi
  __int64 v8; // rcx
  __int64 v9; // r8
  PMDL Mdl; // r14
  unsigned int v11; // edi
  int v12; // ecx
  int v13; // r8d
  __int64 v15; // rcx
  __int64 v16; // r8
  PVOID MappedSystemVa; // rax
  __int64 v18; // r8
  struct _MDL *v19; // r15
  __int64 v20; // rcx
  __int64 v21; // r8
  int v22; // ecx
  int v23; // r8d
  int v24; // ecx
  int v25; // r8d
  __int64 v26; // rcx
  __int64 v27; // r8
  unsigned int v28; // [rsp+50h] [rbp-48h] BYREF
  __int64 v29; // [rsp+58h] [rbp-40h]
  char v30; // [rsp+60h] [rbp-38h]

  a6->Next = 0;
  v7 = a4 << 12;
  Mdl = IoAllocateMdl((PVOID)((a3 << 12) + (a2 ^ 0xAA5555AAA55AA55AuLL)), a4 << 12, 0, 0, 0);
  if ( Mdl )
  {
    v28 = -1;
    v29 = 0;
    if ( (qword_140087010 & 2) != 0 )
    {
      v30 = 1;
      v28 = 8000;
      if ( (byte_140087202 & 1) != 0 )
        McTemplateK0q_EtwWriteTransfer(v8, EventProfilerEnter, v9, 8000);
    }
    else
    {
      v30 = 0;
    }
    DXGETWPROFILER_BASE::PushProfilerEntry(&v28, 8000);
    MmProbeAndLockPages(Mdl, 0, Operation);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v28);
    if ( v30 && (byte_140087202 & 1) != 0 )
      McTemplateK0q_EtwWriteTransfer(v15, EventProfilerExit, v16, v28);
    if ( (Mdl->MdlFlags & 5) != 0 )
      MappedSystemVa = Mdl->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(Mdl, 0, MmCached, 0, 0, 0x10u);
    if ( MappedSystemVa )
    {
      v19 = IoAllocateMdl(MappedSystemVa, v7, 0, 0, 0);
      if ( v19 )
      {
        v11 = 0;
        v28 = -1;
        v29 = 0;
        if ( (qword_140087010 & 2) != 0 )
        {
          v30 = 1;
          v28 = 8000;
          if ( (byte_140087202 & 1) != 0 )
            McTemplateK0q_EtwWriteTransfer(qword_140087010, EventProfilerEnter, v18, 8000);
        }
        else
        {
          v30 = 0;
        }
        DXGETWPROFILER_BASE::PushProfilerEntry(&v28, 8000);
        MmProbeAndLockPages(v19, 0, Operation);
        a6->Next = v19;
        DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v28);
        if ( v30 && (byte_140087202 & 1) != 0 )
          McTemplateK0q_EtwWriteTransfer(v20, EventProfilerExit, v21, v28);
      }
      else
      {
        v11 = -1073741801;
        _InterlockedIncrement(&dword_14008770C);
        WdLogSingleEntry1(6, -1073741801);
        WdLogGlobalForLineNumber = 282;
        DxgkLogInternalTriageEvent(
          v22,
          262145,
          v23,
          (unsigned int)L"Failed to allocate MDL from the fence storage, returning 0x%I64x.",
          -1073741801,
          0,
          0,
          0);
      }
    }
    else
    {
      v11 = -1073741670;
      _InterlockedIncrement(&dword_14008770C);
      WdLogSingleEntry2(6, a2, -1073741670);
      WdLogGlobalForLineNumber = 291;
      DxgkLogInternalTriageEvent(
        v24,
        262145,
        v25,
        (unsigned int)L"Failed to get system address for the memory block 0x%I64x, returning 0x%I64x.",
        a2,
        -1073741670,
        0,
        0);
    }
    v28 = -1;
    v29 = 0;
    if ( (qword_140087010 & 2) != 0 )
    {
      v30 = 1;
      v28 = 8001;
      if ( (byte_140087202 & 1) != 0 )
        McTemplateK0q_EtwWriteTransfer(v20, EventProfilerEnter, v21, 8001);
    }
    else
    {
      v30 = 0;
    }
    DXGETWPROFILER_BASE::PushProfilerEntry(&v28, 8001);
    MmUnlockPages(Mdl);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v28);
    if ( v30 && (byte_140087202 & 1) != 0 )
      McTemplateK0q_EtwWriteTransfer(v26, EventProfilerExit, v27, v28);
    IoFreeMdl(Mdl);
  }
  else
  {
    _InterlockedIncrement(&dword_14008770C);
    v11 = -1073741801;
    WdLogSingleEntry1(6, -1073741801);
    WdLogGlobalForLineNumber = 222;
    DxgkLogInternalTriageEvent(
      v12,
      262145,
      v13,
      (unsigned int)L"Failed to allocate MDL from the fence storage, returning 0x%I64x.",
      -1073741801,
      0,
      0,
      0);
  }
  return v11;
}

```

## disassembly

```asm
0x1400da1f0  mov     [rsp+arg_0], rbx
0x1400da1f5  mov     [rsp+arg_8], rdx
0x1400da1fa  push    rsi
0x1400da1fb  push    rdi
0x1400da1fc  push    r12
0x1400da1fe  push    r14
0x1400da200  push    r15
0x1400da202  sub     rsp, 70h
0x1400da206  mov     edi, r9d
0x1400da209  mov     r15, rdx
0x1400da20c  xor     ebx, ebx
0x1400da20e  mov     r12, [rsp+98h+arg_28]
0x1400da216  mov     [r12], rbx
0x1400da21a  shl     edi, 0Ch
0x1400da21d  shl     r8, 0Ch
0x1400da221  mov     rcx, 0AA5555AAA55AA55Ah
0x1400da22b  xor     rcx, rdx
0x1400da22e  add     rcx, r8; VirtualAddress
0x1400da231  mov     [rsp+98h+Irp], rbx; Irp
0x1400da236  xor     r9d, r9d; ChargeQuota
0x1400da239  xor     r8d, r8d; SecondaryBuffer
0x1400da23c  mov     edx, edi; Length
0x1400da23e  call    cs:__imp_IoAllocateMdl
0x1400da245  nop     dword ptr [rax+rax+00h]
0x1400da24a  mov     r14, rax
0x1400da24d  mov     [rsp+98h+arg_28], rax
0x1400da255  test    rax, rax
0x1400da258  jnz     short loc_1400DA2B0
0x1400da25a  lock inc cs:dword_14008770C
0x1400da261  mov     rdi, 0FFFFFFFFC0000017h
0x1400da268  mov     rdx, rdi
0x1400da26b  lea     ecx, [rbx+6]
0x1400da26e  call    cs:__imp_WdLogSingleEntry1
0x1400da275  nop     dword ptr [rax+rax+00h]
0x1400da27a  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400da284  mov     [rsp+98h+var_60], rbx
0x1400da289  mov     [rsp+98h+var_68], rbx
0x1400da28e  mov     qword ptr [rsp+98h+Priority], rbx
0x1400da293  mov     [rsp+98h+Irp], rdi
0x1400da298  lea     r9, aFailedToAlloca_9; "Failed to allocate MDL from the fence s"...
0x1400da29f  mov     edx, 40001h
0x1400da2a4  call    DxgkLogInternalTriageEvent
0x1400da2a9  mov     eax, edi
0x1400da2ab  jmp     loc_1400DA6DF
0x1400da2b0  mov     [rsp+98h+var_48], 0FFFFFFFFh
0x1400da2b8  mov     [rsp+98h+var_40], rbx
0x1400da2bd  mov     rax, cs:qword_140087010
0x1400da2c4  mov     esi, 1F40h
0x1400da2c9  test    al, 2
0x1400da2cb  jz      short loc_1400DA2F0
0x1400da2cd  mov     [rsp+98h+var_38], 1
0x1400da2d2  mov     [rsp+98h+var_48], esi
0x1400da2d6  test    cs:byte_140087202, 1
0x1400da2dd  jz      short loc_1400DA2F4
0x1400da2df  mov     r9d, esi
0x1400da2e2  lea     rdx, EventProfilerEnter
0x1400da2e9  call    McTemplateK0q_EtwWriteTransfer
0x1400da2ee  jmp     short loc_1400DA2F4
0x1400da2f0  mov     [rsp+98h+var_38], bl
0x1400da2f4  mov     edx, esi
0x1400da2f6  lea     rcx, [rsp+98h+var_48]
0x1400da2fb  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1400da300  nop
0x1400da301  mov     r8d, [rsp+98h+Operation]; Operation
0x1400da309  xor     edx, edx; AccessMode
0x1400da30b  mov     rcx, r14; MemoryDescriptorList
0x1400da30e  call    cs:__imp_MmProbeAndLockPages
0x1400da315  nop     dword ptr [rax+rax+00h]
0x1400da31a  nop
0x1400da31b  lea     rcx, [rsp+98h+var_48]; this
0x1400da320  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1400da325  cmp     [rsp+98h+var_38], bl
0x1400da329  jz      short loc_1400DA345
0x1400da32b  test    cs:byte_140087202, 1
0x1400da332  jz      short loc_1400DA345
0x1400da334  mov     r9d, [rsp+98h+var_48]
0x1400da339  lea     rdx, EventProfilerExit
0x1400da340  call    McTemplateK0q_EtwWriteTransfer
0x1400da345  test    byte ptr [r14+0Ah], 5
0x1400da34a  jz      short loc_1400DA352
0x1400da34c  mov     rax, [r14+18h]
0x1400da350  jmp     short loc_1400DA376
0x1400da352  mov     [rsp+98h+Priority], 10h; Priority
0x1400da35a  mov     dword ptr [rsp+98h+Irp], ebx; BugCheckOnFailure
0x1400da35e  xor     r9d, r9d; RequestedAddress
0x1400da361  xor     edx, edx; AccessMode
0x1400da363  lea     r8d, [r9+1]; CacheType
0x1400da367  mov     rcx, r14; MemoryDescriptorList
0x1400da36a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400da371  nop     dword ptr [rax+rax+00h]
0x1400da376  test    rax, rax
0x1400da379  jz      loc_1400DA532
0x1400da37f  mov     [rsp+98h+Irp], rbx; Irp
0x1400da384  xor     r9d, r9d; ChargeQuota
0x1400da387  xor     r8d, r8d; SecondaryBuffer
0x1400da38a  mov     edx, edi; Length
0x1400da38c  mov     rcx, rax; VirtualAddress
0x1400da38f  call    cs:__imp_IoAllocateMdl
0x1400da396  nop     dword ptr [rax+rax+00h]
0x1400da39b  mov     r15, rax
0x1400da39e  mov     [rsp+98h+Mdl], rax
0x1400da3a6  test    rax, rax
0x1400da3a9  jz      loc_1400DA4E9
0x1400da3af  mov     edi, ebx
0x1400da3b1  mov     [rsp+98h+var_48], 0FFFFFFFFh
0x1400da3b9  mov     [rsp+98h+var_40], rbx
0x1400da3be  mov     rcx, cs:qword_140087010
0x1400da3c5  test    cl, 2
0x1400da3c8  jz      short loc_1400DA3ED
0x1400da3ca  mov     [rsp+98h+var_38], 1
0x1400da3cf  mov     [rsp+98h+var_48], esi
0x1400da3d3  test    cs:byte_140087202, 1
0x1400da3da  jz      short loc_1400DA3F1
0x1400da3dc  mov     r9d, esi
0x1400da3df  lea     rdx, EventProfilerEnter
0x1400da3e6  call    McTemplateK0q_EtwWriteTransfer
0x1400da3eb  jmp     short loc_1400DA3F1
0x1400da3ed  mov     [rsp+98h+var_38], bl
0x1400da3f1  mov     edx, esi
0x1400da3f3  lea     rcx, [rsp+98h+var_48]
0x1400da3f8  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1400da3fd  nop
0x1400da3fe  mov     r8d, [rsp+98h+Operation]; Operation
0x1400da406  xor     edx, edx; AccessMode
0x1400da408  mov     rcx, r15; MemoryDescriptorList
0x1400da40b  call    cs:__imp_MmProbeAndLockPages
0x1400da412  nop     dword ptr [rax+rax+00h]
0x1400da417  mov     [r12], r15
0x1400da41b  jmp     loc_1400DA4B2
0x1400da420  movsxd  rdi, eax
0x1400da423  test    cs:byte_140087201, 1
0x1400da42a  jz      short loc_1400DA43E
0x1400da42c  mov     r9d, 3
0x1400da432  lea     rdx, EventPerformanceWarning
0x1400da439  call    McTemplateK0q_EtwWriteTransfer
0x1400da43e  mov     r8, rdi
0x1400da441  mov     rbx, [rsp+98h+arg_8]
0x1400da449  mov     rdx, rbx
0x1400da44c  mov     ecx, 1
0x1400da451  call    cs:__imp_WdLogSingleEntry2
0x1400da458  nop     dword ptr [rax+rax+00h]
0x1400da45d  mov     cs:WdLogGlobalForLineNumber, 111h
0x1400da467  mov     [rsp+98h+var_60], 0
0x1400da470  mov     [rsp+98h+var_68], 0
0x1400da479  mov     qword ptr [rsp+98h+Priority], rdi
0x1400da47e  mov     [rsp+98h+Irp], rbx
0x1400da483  lea     r9, aFailedToProbea; "Failed to ProbeAndLock the memory block"...
0x1400da48a  mov     edx, 40000h
0x1400da48f  call    DxgkLogInternalTriageEvent
0x1400da494  mov     rcx, [rsp+98h+Mdl]; Mdl
0x1400da49c  call    cs:__imp_IoFreeMdl
0x1400da4a3  nop     dword ptr [rax+rax+00h]
0x1400da4a8  xor     ebx, ebx
0x1400da4aa  mov     r14, [rsp+98h+arg_28]
0x1400da4b2  lea     rcx, [rsp+98h+var_48]; this
0x1400da4b7  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1400da4bc  cmp     [rsp+98h+var_38], bl
0x1400da4c0  jz      loc_1400DA588
0x1400da4c6  test    cs:byte_140087202, 1
0x1400da4cd  jz      loc_1400DA588
0x1400da4d3  mov     r9d, [rsp+98h+var_48]
0x1400da4d8  lea     rdx, EventProfilerExit
0x1400da4df  call    McTemplateK0q_EtwWriteTransfer
0x1400da4e4  jmp     loc_1400DA588
0x1400da4e9  mov     rdi, 0FFFFFFFFC0000017h
0x1400da4f0  lock inc cs:dword_14008770C
0x1400da4f7  mov     rdx, rdi
0x1400da4fa  mov     ecx, 6
0x1400da4ff  call    cs:__imp_WdLogSingleEntry1
0x1400da506  nop     dword ptr [rax+rax+00h]
0x1400da50b  mov     cs:WdLogGlobalForLineNumber, 11Ah
0x1400da515  mov     [rsp+98h+var_60], rbx
0x1400da51a  mov     [rsp+98h+var_68], rbx
0x1400da51f  mov     qword ptr [rsp+98h+Priority], rbx
0x1400da524  mov     [rsp+98h+Irp], rdi
0x1400da529  lea     r9, aFailedToAlloca_9; "Failed to allocate MDL from the fence s"...
0x1400da530  jmp     short loc_1400DA57E
0x1400da532  mov     rsi, 0FFFFFFFFC000009Ah
0x1400da539  mov     edi, esi
0x1400da53b  lock inc cs:dword_14008770C
0x1400da542  mov     r8, rsi
0x1400da545  mov     rdx, r15
0x1400da548  mov     ecx, 6
0x1400da54d  call    cs:__imp_WdLogSingleEntry2
0x1400da554  nop     dword ptr [rax+rax+00h]
0x1400da559  mov     cs:WdLogGlobalForLineNumber, 123h
0x1400da563  mov     [rsp+98h+var_60], rbx
0x1400da568  mov     [rsp+98h+var_68], rbx
0x1400da56d  mov     qword ptr [rsp+98h+Priority], rsi
0x1400da572  mov     [rsp+98h+Irp], r15
0x1400da577  lea     r9, aFailedToGetSys_1; "Failed to get system address for the me"...
0x1400da57e  mov     edx, 40001h
0x1400da583  call    DxgkLogInternalTriageEvent
0x1400da588  mov     [rsp+98h+var_48], 0FFFFFFFFh
0x1400da590  mov     [rsp+98h+var_40], rbx
0x1400da595  mov     rax, cs:qword_140087010
0x1400da59c  test    al, 2
0x1400da59e  jz      short loc_1400DA5CA
0x1400da5a0  mov     [rsp+98h+var_38], 1
0x1400da5a5  mov     [rsp+98h+var_48], 1F41h
0x1400da5ad  test    cs:byte_140087202, 1
0x1400da5b4  jz      short loc_1400DA5CE
0x1400da5b6  mov     r9d, 1F41h
0x1400da5bc  lea     rdx, EventProfilerEnter
0x1400da5c3  call    McTemplateK0q_EtwWriteTransfer
0x1400da5c8  jmp     short loc_1400DA5CE
0x1400da5ca  mov     [rsp+98h+var_38], bl
0x1400da5ce  mov     edx, 1F41h
0x1400da5d3  lea     rcx, [rsp+98h+var_48]
0x1400da5d8  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1400da5dd  mov     rcx, r14; MemoryDescriptorList
0x1400da5e0  call    cs:__imp_MmUnlockPages
0x1400da5e7  nop     dword ptr [rax+rax+00h]
0x1400da5ec  lea     rcx, [rsp+98h+var_48]; this
0x1400da5f1  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1400da5f6  cmp     [rsp+98h+var_38], bl
0x1400da5fa  jz      short loc_1400DA616
0x1400da5fc  test    cs:byte_140087202, 1
0x1400da603  jz      short loc_1400DA616
0x1400da605  mov     r9d, [rsp+98h+var_48]
0x1400da60a  lea     rdx, EventProfilerExit
0x1400da611  call    McTemplateK0q_EtwWriteTransfer
0x1400da616  mov     rcx, r14; Mdl
0x1400da619  call    cs:__imp_IoFreeMdl
0x1400da620  nop     dword ptr [rax+rax+00h]
0x1400da625  jmp     loc_1400DA2A9
0x1400da62a  movsxd  rdi, eax
0x1400da62d  test    cs:byte_140087201, 1
0x1400da634  jz      short loc_1400DA648
0x1400da636  mov     r9d, 3
0x1400da63c  lea     rdx, EventPerformanceWarning
0x1400da643  call    McTemplateK0q_EtwWriteTransfer
0x1400da648  mov     r8, rdi
0x1400da64b  mov     rbx, [rsp+98h+arg_8]
0x1400da653  mov     rdx, rbx
0x1400da656  mov     ecx, 1
0x1400da65b  call    cs:__imp_WdLogSingleEntry2
0x1400da662  nop     dword ptr [rax+rax+00h]
0x1400da667  mov     cs:WdLogGlobalForLineNumber, 0F3h
0x1400da671  mov     [rsp+98h+var_60], 0
0x1400da67a  mov     [rsp+98h+var_68], 0
0x1400da683  mov     qword ptr [rsp+98h+Priority], rdi
0x1400da688  mov     [rsp+98h+Irp], rbx
0x1400da68d  lea     r9, aFailedToProbea; "Failed to ProbeAndLock the memory block"...
0x1400da694  mov     edx, 40000h
0x1400da699  call    DxgkLogInternalTriageEvent
0x1400da69e  mov     rcx, [rsp+98h+arg_28]; Mdl
0x1400da6a6  call    cs:__imp_IoFreeMdl
0x1400da6ad  nop     dword ptr [rax+rax+00h]
0x1400da6b2  lea     rcx, [rsp+98h+var_48]; this
0x1400da6b7  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1400da6bc  cmp     [rsp+98h+var_38], 0
0x1400da6c1  jz      short loc_1400DA6DD
0x1400da6c3  test    cs:byte_140087202, 1
0x1400da6ca  jz      short loc_1400DA6DD
0x1400da6cc  mov     r9d, [rsp+98h+var_48]
0x1400da6d1  lea     rdx, EventProfilerExit
0x1400da6d8  call    McTemplateK0q_EtwWriteTransfer
0x1400da6dd  mov     eax, edi
0x1400da6df  mov     rbx, [rsp+98h+arg_0]
0x1400da6e7  add     rsp, 70h
0x1400da6eb  pop     r15
0x1400da6ed  pop     r14
0x1400da6ef  pop     r12
0x1400da6f1  pop     rdi
0x1400da6f2  pop     rsi
0x1400da6f3  retn
```
