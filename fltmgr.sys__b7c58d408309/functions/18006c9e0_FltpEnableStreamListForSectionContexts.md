# FltpEnableStreamListForSectionContexts

- ea: `0x18006c9e0`
- end: `0x18006cbd6`
- name: `FltpEnableStreamListForSectionContexts`
- size: `502`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006c900`

## callees

- `0x180009f20`
- `0x180024c00`
- `0x18006c9e0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x18006caf5`
- `ntoskrnl!KeInitializeEvent` at `0x18006cb4c`
- `ntoskrnl!KeInitializeEvent` at `0x18006caf5`
- `ntoskrnl!KeInitializeEvent` at `0x18006cb4c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18006ca07`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18006ca07`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18006cbc8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18006cbc8`
- `ntoskrnl!IoSizeofWorkItem` at `0x18006caa2`
- `ntoskrnl!IoSizeofWorkItem` at `0x18006cb15`
- `ntoskrnl!IoSizeofWorkItem` at `0x18006caa2`
- `ntoskrnl!IoSizeofWorkItem` at `0x18006cb15`
- `ntoskrnl!IoCsqInitialize` at `0x18006ca62`
- `ntoskrnl!IoCsqInitialize` at `0x18006ca62`
- `ntoskrnl!ExInitializeRundownProtectionCacheAware` at `0x18006cb34`
- `ntoskrnl!ExInitializeRundownProtectionCacheAware` at `0x18006cb34`

## pseudocode

```c
__int64 __fastcall FltpEnableStreamListForSectionContexts(__int64 a1)
{
  char *v2; // rax
  signed __int64 v3; // rsi
  unsigned int v4; // edi
  ULONG v5; // eax
  SIZE_T v6; // rdi
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v7; // rcx

  if ( *(_QWORD *)(a1 + 360) )
    return 0;
  v2 = (char *)ExAllocateFromNPagedLookasideList(&stru_18003F1C0);
  v3 = (signed __int64)v2;
  if ( !v2 )
    return 3221225626LL;
  *(_QWORD *)v2 = a1;
  v4 = IoCsqInitialize(
         (PIO_CSQ)(v2 + 176),
         (PIO_CSQ_INSERT_IRP)FltpDataScanCsqInsertIrp,
         (PIO_CSQ_REMOVE_IRP)FltpDataScanCsqRemoveIrp,
         (PIO_CSQ_PEEK_NEXT_IRP)FltpDataScanCsqPeekNextIrp,
         (PIO_CSQ_ACQUIRE_LOCK)FltpDataScanCsqAcquireLock,
         (PIO_CSQ_RELEASE_LOCK)FltpDataScanCsqReleaseLock,
         (PIO_CSQ_COMPLETE_CANCELED_IRP)FltpDataScanCsqCompleteCanceledIrp);
  if ( (int)FltpDbgStatus(v4) >= 0 )
  {
    *(_QWORD *)(v3 + 320) = v3 + 336;
    v5 = IoSizeofWorkItem();
    memset(*(void **)(v3 + 320), 0, v5);
    *(_QWORD *)(v3 + 248) = v3 + 240;
    *(_QWORD *)(v3 + 240) = v3 + 240;
    *(_DWORD *)(v3 + 256) = 1;
    *(_QWORD *)(v3 + 264) = 0;
    *(_DWORD *)(v3 + 272) = 0;
    KeInitializeEvent((PRKEVENT)(v3 + 280), SynchronizationEvent, 0);
    *(_DWORD *)(v3 + 312) = 0;
    *(_QWORD *)(v3 + 328) = v3;
    v6 = RunRefSize;
    v7 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)(v3 + IoSizeofWorkItem() + 336LL);
    *(_QWORD *)(v3 + 8) = v7;
    ExInitializeRundownProtectionCacheAware(v7, v6);
    KeInitializeEvent((PRKEVENT)(v3 + 16), SynchronizationEvent, 1u);
    memset((void *)(v3 + 40), 0, 0x80u);
    *(_QWORD *)(v3 + 168) = 0;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 360), v3, 0) )
      ExFreeToNPagedLookasideList(&stru_18003F1C0, (PVOID)v3);
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18006c9e0  mov     [rsp+arg_8], rbx
0x18006c9e5  mov     [rsp+arg_10], rsi
0x18006c9ea  push    rdi
0x18006c9eb  sub     rsp, 40h
0x18006c9ef  cmp     qword ptr [rcx+168h], 0
0x18006c9f7  mov     rbx, rcx
0x18006c9fa  jnz     loc_18006CB82
0x18006ca00  lea     rcx, stru_18003F1C0; Lookaside
0x18006ca07  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x18006ca0e  nop     dword ptr [rax+rax+00h]
0x18006ca13  mov     rsi, rax
0x18006ca16  test    rax, rax
0x18006ca19  jz      loc_18006CB95
0x18006ca1f  mov     [rax], rbx
0x18006ca22  lea     rcx, [rax+0B0h]; Csq
0x18006ca29  lea     rax, FltpDataScanCsqCompleteCanceledIrp
0x18006ca30  mov     [rsp+48h+CsqCompleteCanceledIrp], rax; CsqCompleteCanceledIrp
0x18006ca35  lea     r9, FltpDataScanCsqPeekNextIrp; CsqPeekNextIrp
0x18006ca3c  lea     rax, FltpDataScanCsqReleaseLock
0x18006ca43  mov     [rsp+48h+CsqReleaseLock], rax; CsqReleaseLock
0x18006ca48  lea     r8, FltpDataScanCsqRemoveIrp; CsqRemoveIrp
0x18006ca4f  lea     rax, FltpDataScanCsqAcquireLock
0x18006ca56  lea     rdx, FltpDataScanCsqInsertIrp; CsqInsertIrp
0x18006ca5d  mov     [rsp+48h+CsqAcquireLock], rax; CsqAcquireLock
0x18006ca62  call    cs:__imp_IoCsqInitialize
0x18006ca69  nop     dword ptr [rax+rax+00h]
0x18006ca6e  mov     r8d, 902h
0x18006ca74  lea     rdx, aMinkernelFsFil_11; "minkernel\\fs\\filtermgr\\filter\\secti"...
0x18006ca7b  mov     ecx, eax
0x18006ca7d  xor     r9d, r9d
0x18006ca80  mov     edi, eax
0x18006ca82  call    FltpDbgStatus
0x18006ca87  test    eax, eax
0x18006ca89  js      loc_18006CBAB
0x18006ca8f  lea     rax, [rsi+150h]
0x18006ca96  mov     [rsp+48h+arg_0], rbp
0x18006ca9b  mov     [rsi+140h], rax
0x18006caa2  call    cs:__imp_IoSizeofWorkItem
0x18006caa9  nop     dword ptr [rax+rax+00h]
0x18006caae  mov     rcx, [rsi+140h]; void *
0x18006cab5  xor     edx, edx; Val
0x18006cab7  mov     r8d, eax; Size
0x18006caba  call    memset
0x18006cabf  lea     rax, [rsi+0F0h]
0x18006cac6  xor     ebp, ebp
0x18006cac8  mov     [rax+8], rax
0x18006cacc  lea     rcx, [rsi+118h]; Event
0x18006cad3  mov     [rax], rax
0x18006cad6  xor     r8d, r8d; State
0x18006cad9  mov     edx, 1; Type
0x18006cade  mov     dword ptr [rsi+100h], 1
0x18006cae8  mov     [rsi+108h], rbp
0x18006caef  mov     [rsi+110h], ebp
0x18006caf5  call    cs:__imp_KeInitializeEvent
0x18006cafc  nop     dword ptr [rax+rax+00h]
0x18006cb01  mov     [rsi+138h], ebp
0x18006cb07  mov     [rsi+148h], rsi
0x18006cb0e  mov     rdi, cs:RunRefSize
0x18006cb15  call    cs:__imp_IoSizeofWorkItem
0x18006cb1c  nop     dword ptr [rax+rax+00h]
0x18006cb21  mov     ecx, eax
0x18006cb23  mov     rdx, rdi; RunRefSize
0x18006cb26  add     rcx, 150h
0x18006cb2d  add     rcx, rsi; RunRefCacheAware
0x18006cb30  mov     [rsi+8], rcx
0x18006cb34  call    cs:__imp_ExInitializeRundownProtectionCacheAware
0x18006cb3b  nop     dword ptr [rax+rax+00h]
0x18006cb40  lea     rcx, [rsi+10h]; Event
0x18006cb44  mov     r8b, 1; State
0x18006cb47  mov     edx, 1; Type
0x18006cb4c  call    cs:__imp_KeInitializeEvent
0x18006cb53  nop     dword ptr [rax+rax+00h]
0x18006cb58  xor     edx, edx; Val
0x18006cb5a  lea     rcx, [rsi+28h]; void *
0x18006cb5e  mov     r8d, 80h; Size
0x18006cb64  call    memset
0x18006cb69  mov     [rsi+0A8h], rbp
0x18006cb70  xor     eax, eax
0x18006cb72  mov     rbp, [rsp+48h+arg_0]
0x18006cb77  lock cmpxchg [rbx+168h], rsi
0x18006cb80  jnz     short loc_18006CBBE
0x18006cb82  xor     eax, eax
0x18006cb84  mov     rbx, [rsp+48h+arg_8]
0x18006cb89  mov     rsi, [rsp+48h+arg_10]
0x18006cb8e  add     rsp, 40h
0x18006cb92  pop     rdi
0x18006cb93  retn
0x18006cb95  mov     eax, 0C000009Ah
0x18006cb9a  mov     rbx, [rsp+48h+arg_8]
0x18006cb9f  mov     rsi, [rsp+48h+arg_10]
0x18006cba4  add     rsp, 40h
0x18006cba8  pop     rdi
0x18006cba9  retn
0x18006cbab  mov     rbx, [rsp+48h+arg_8]
0x18006cbb0  mov     eax, edi
0x18006cbb2  mov     rsi, [rsp+48h+arg_10]
0x18006cbb7  add     rsp, 40h
0x18006cbbb  pop     rdi
0x18006cbbc  retn
0x18006cbbe  mov     rdx, rsi; Entry
0x18006cbc1  lea     rcx, stru_18003F1C0; Lookaside
0x18006cbc8  call    cs:__imp_ExFreeToNPagedLookasideList
0x18006cbcf  nop     dword ptr [rax+rax+00h]
0x18006cbd4  jmp     short loc_18006CB82
```
