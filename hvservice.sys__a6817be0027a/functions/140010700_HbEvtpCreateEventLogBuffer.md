# HbEvtpCreateEventLogBuffer

- ea: `0x140010700`
- end: `0x14001090b`
- name: `HbEvtpCreateEventLogBuffer`
- size: `523`
- prototype: `__int64 __fastcall(PVOID DeferredContext, unsigned int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140014810`

## callees

- `0x140001600`
- `0x1400105d4`
- `0x140010700`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400108e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400108e7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140010854`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140010854`
- `ntoskrnl!KeInitializeDpc` at `0x1400107a5`
- `ntoskrnl!KeInitializeDpc` at `0x1400107a5`
- `ntoskrnl!HvlQueryHypervisorProcessorNodeNumber` at `0x140010777`
- `ntoskrnl!HvlQueryHypervisorProcessorNodeNumber` at `0x140010777`
- `ntoskrnl!MmFreePagesFromMdl` at `0x1400108cd`
- `ntoskrnl!MmFreePagesFromMdl` at `0x1400108cd`
- `winhvr!WinHvMapEventLogBuffer` at `0x1400107fe`
- `winhvr!WinHvMapEventLogBuffer` at `0x1400107fe`
- `winhvr!WinHvReleaseEventLogBuffer` at `0x14001088f`
- `winhvr!WinHvReleaseEventLogBuffer` at `0x14001088f`
- `winhvr!WinHvCreateEventLogBuffer` at `0x1400107b8`
- `winhvr!WinHvCreateEventLogBuffer` at `0x1400107b8`
- `winhvr!WinHvUnmapEventLogBuffer` at `0x14001089f`
- `winhvr!WinHvUnmapEventLogBuffer` at `0x14001089f`
- `winhvr!WinHvDeleteEventLogBuffer` at `0x1400108b4`
- `winhvr!WinHvDeleteEventLogBuffer` at `0x1400108b4`

## string_xrefs

- `0x140010753`: `HbEvtpCreateEventLogBuffer`
- `0x1400107df`: `HbEvtpCreateEventLogBuffer`
- `0x140010825`: `HbEvtpCreateEventLogBuffer`
- `0x14001087d`: `HbEvtpCreateEventLogBuffer`
- `0x1400107ce`: `WinHvCreateEventLogBuffer failed for %d - ntStatus: %X`
- `0x14001086c`: `MmMapLockedPagesSpecifyCache failed for %d`

## pseudocode

```c
__int64 __fastcall HbEvtpCreateEventLogBuffer(PVOID DeferredContext, unsigned int a2, unsigned int a3, __int64 a4)
{
  __int64 v7; // r14
  int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  int EventLogBuffer; // eax
  int v12; // eax
  PVOID v13; // rax
  void *v14; // rcx
  unsigned __int16 v16; // [rsp+78h] [rbp+10h] BYREF

  v16 = 0;
  v7 = *(_QWORD *)(a4 + 32) + 112LL * a3;
  *(_DWORD *)(v7 + 80) = a2;
  *(_DWORD *)(v7 + 84) = a3;
  v8 = HbEvtpAllocateAndInitializeEventLogMdl(*(_DWORD *)a4, v7 + 8);
  v9 = v8;
  if ( v8 >= 0 )
  {
    if ( (int)HvlQueryHypervisorProcessorNodeNumber(a3 % HbEvtpActiveProcessorCount, &v16) < 0 )
      v10 = -2147418113;
    else
      v10 = v16 | 0x80000000;
    KeInitializeDpc((PRKDPC)(v7 + 16), HbEvtpTraceCompletedDpcRoutine, DeferredContext);
    EventLogBuffer = WinHvCreateEventLogBuffer(a2, a3, v10);
    v9 = EventLogBuffer;
    if ( EventLogBuffer >= 0 )
    {
      v12 = WinHvMapEventLogBuffer(a2, a3, *(_QWORD *)(v7 + 8) + 48LL);
      v9 = v12;
      if ( v12 >= 0 )
      {
        v13 = MmMapLockedPagesSpecifyCache(*(PMDL *)(v7 + 8), 0, MmCached, 0, 0, 0x40000020u);
        *(_QWORD *)v7 = v13;
        if ( v13 )
          return v9;
        HbpTraceEvent(0, "HbEvtpCreateEventLogBuffer", 3039, "MmMapLockedPagesSpecifyCache failed for %d", a3);
        WinHvReleaseEventLogBuffer(a2, a3);
        WinHvUnmapEventLogBuffer(a2, a3);
        v9 = -1073741670;
      }
      else
      {
        HbpTraceEvent(
          0,
          "HbEvtpCreateEventLogBuffer",
          3020,
          "WinHvMapEventLogBuffer failed for %d - ntStatus: %X",
          a3,
          v12);
      }
      WinHvDeleteEventLogBuffer(a2, a3);
    }
    else
    {
      HbpTraceEvent(
        0,
        "HbEvtpCreateEventLogBuffer",
        3006,
        "WinHvCreateEventLogBuffer failed for %d - ntStatus: %X",
        a3,
        EventLogBuffer);
    }
  }
  else
  {
    HbpTraceEvent(
      0,
      "HbEvtpCreateEventLogBuffer",
      2981,
      "HbEvtpAllocateAndInitializeEventLogMdl failed for %d - ntStatus: %X",
      a3,
      v8);
  }
  if ( !byte_140009048 )
    MmFreePagesFromMdl(*(PMDL *)(v7 + 8));
  v14 = *(void **)(v7 + 8);
  if ( v14 )
  {
    ExFreePoolWithTag(v14, 0x75426248u);
    *(_QWORD *)(v7 + 8) = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x140010700  push    rbx
0x140010702  push    rbp
0x140010703  push    rsi
0x140010704  push    rdi
0x140010705  push    r14
0x140010707  push    r15
0x140010709  sub     rsp, 38h
0x14001070d  mov     edi, r8d
0x140010710  xor     eax, eax
0x140010712  mov     [rsp+68h+arg_8], ax
0x140010717  mov     ebp, edx
0x140010719  mov     r15, rcx
0x14001071c  imul    r14, rdi, 70h ; 'p'
0x140010720  add     r14, [r9+20h]
0x140010724  mov     [r14+50h], edx
0x140010728  lea     rdx, [r14+8]
0x14001072c  mov     [r14+54h], edi
0x140010730  mov     ecx, [r9]
0x140010733  call    HbEvtpAllocateAndInitializeEventLogMdl
0x140010738  mov     ebx, eax
0x14001073a  test    eax, eax
0x14001073c  jns     short loc_140010766
0x14001073e  mov     [rsp+68h+Priority], eax
0x140010742  lea     r9, aHbevtpallocate; "HbEvtpAllocateAndInitializeEventLogMdl "...
0x140010749  mov     r8d, 0BA5h
0x14001074f  mov     [rsp+68h+BugCheckOnFailure], edi
0x140010753  lea     rdx, aHbevtpcreateev; "HbEvtpCreateEventLogBuffer"
0x14001075a  xor     ecx, ecx
0x14001075c  call    HbpTraceEvent
0x140010761  jmp     loc_1400108C0
0x140010766  xor     edx, edx
0x140010768  mov     eax, edi
0x14001076a  div     cs:HbEvtpActiveProcessorCount
0x140010770  mov     ecx, edx
0x140010772  lea     rdx, [rsp+68h+arg_8]
0x140010777  call    cs:__imp_HvlQueryHypervisorProcessorNodeNumber
0x14001077e  nop     dword ptr [rax+rax+00h]
0x140010783  test    eax, eax
0x140010785  js      short loc_140010792
0x140010787  movzx   ebx, [rsp+68h+arg_8]
0x14001078c  bts     ebx, 1Fh
0x140010790  jmp     short loc_140010797
0x140010792  mov     ebx, 8000FFFFh
0x140010797  lea     rcx, [r14+10h]; Dpc
0x14001079b  mov     r8, r15; DeferredContext
0x14001079e  lea     rdx, HbEvtpTraceCompletedDpcRoutine; DeferredRoutine
0x1400107a5  call    cs:__imp_KeInitializeDpc
0x1400107ac  nop     dword ptr [rax+rax+00h]
0x1400107b1  mov     r8d, ebx
0x1400107b4  mov     edx, edi
0x1400107b6  mov     ecx, ebp
0x1400107b8  call    cs:__imp_WinHvCreateEventLogBuffer
0x1400107bf  nop     dword ptr [rax+rax+00h]
0x1400107c4  mov     ebx, eax
0x1400107c6  test    eax, eax
0x1400107c8  jns     short loc_1400107F2
0x1400107ca  mov     [rsp+68h+Priority], eax
0x1400107ce  lea     r9, aWinhvcreateeve; "WinHvCreateEventLogBuffer failed for %d"...
0x1400107d5  mov     r8d, 0BBEh
0x1400107db  mov     [rsp+68h+BugCheckOnFailure], edi
0x1400107df  lea     rdx, aHbevtpcreateev; "HbEvtpCreateEventLogBuffer"
0x1400107e6  xor     ecx, ecx
0x1400107e8  call    HbpTraceEvent
0x1400107ed  jmp     loc_1400108C0
0x1400107f2  mov     r8, [r14+8]
0x1400107f6  mov     edx, edi
0x1400107f8  add     r8, 30h ; '0'
0x1400107fc  mov     ecx, ebp
0x1400107fe  call    cs:__imp_WinHvMapEventLogBuffer
0x140010805  nop     dword ptr [rax+rax+00h]
0x14001080a  mov     ebx, eax
0x14001080c  test    eax, eax
0x14001080e  jns     short loc_140010835
0x140010810  mov     [rsp+68h+Priority], eax
0x140010814  lea     r9, aWinhvmapeventl; "WinHvMapEventLogBuffer failed for %d - "...
0x14001081b  mov     r8d, 0BCCh
0x140010821  mov     [rsp+68h+BugCheckOnFailure], edi
0x140010825  lea     rdx, aHbevtpcreateev; "HbEvtpCreateEventLogBuffer"
0x14001082c  xor     ecx, ecx
0x14001082e  call    HbpTraceEvent
0x140010833  jmp     short loc_1400108B0
0x140010835  mov     rcx, [r14+8]; MemoryDescriptorList
0x140010839  xor     r9d, r9d; RequestedAddress
0x14001083c  mov     [rsp+68h+Priority], 40000020h; Priority
0x140010844  xor     edx, edx; AccessMode
0x140010846  mov     r8d, 1; CacheType
0x14001084c  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140010854  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001085b  nop     dword ptr [rax+rax+00h]
0x140010860  mov     [r14], rax
0x140010863  test    rax, rax
0x140010866  jnz     loc_1400108FB
0x14001086c  lea     r9, aMmmaplockedpag_0; "MmMapLockedPagesSpecifyCache failed for"...
0x140010873  mov     [rsp+68h+BugCheckOnFailure], edi
0x140010877  mov     r8d, 0BDFh
0x14001087d  lea     rdx, aHbevtpcreateev; "HbEvtpCreateEventLogBuffer"
0x140010884  xor     ecx, ecx
0x140010886  call    HbpTraceEvent
0x14001088b  mov     edx, edi
0x14001088d  mov     ecx, ebp
0x14001088f  call    cs:__imp_WinHvReleaseEventLogBuffer
0x140010896  nop     dword ptr [rax+rax+00h]
0x14001089b  mov     edx, edi
0x14001089d  mov     ecx, ebp
0x14001089f  call    cs:__imp_WinHvUnmapEventLogBuffer
0x1400108a6  nop     dword ptr [rax+rax+00h]
0x1400108ab  mov     ebx, 0C000009Ah
0x1400108b0  mov     edx, edi
0x1400108b2  mov     ecx, ebp
0x1400108b4  call    cs:__imp_WinHvDeleteEventLogBuffer
0x1400108bb  nop     dword ptr [rax+rax+00h]
0x1400108c0  cmp     cs:byte_140009048, 0
0x1400108c7  jnz     short loc_1400108D9
0x1400108c9  mov     rcx, [r14+8]; MemoryDescriptorList
0x1400108cd  call    cs:__imp_MmFreePagesFromMdl
0x1400108d4  nop     dword ptr [rax+rax+00h]
0x1400108d9  mov     rcx, [r14+8]; P
0x1400108dd  test    rcx, rcx
0x1400108e0  jz      short loc_1400108FB
0x1400108e2  mov     edx, 75426248h; Tag
0x1400108e7  call    cs:__imp_ExFreePoolWithTag
0x1400108ee  nop     dword ptr [rax+rax+00h]
0x1400108f3  mov     qword ptr [r14+8], 0
0x1400108fb  mov     eax, ebx
0x1400108fd  add     rsp, 38h
0x140010901  pop     r15
0x140010903  pop     r14
0x140010905  pop     rdi
0x140010906  pop     rsi
0x140010907  pop     rbp
0x140010908  pop     rbx
0x140010909  retn
```
