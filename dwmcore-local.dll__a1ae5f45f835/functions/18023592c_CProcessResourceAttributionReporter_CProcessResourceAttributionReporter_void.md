# CProcessResourceAttributionReporter::~CProcessResourceAttributionReporter(void)

- ea: `0x18023592c`
- end: `0x1802359dd`
- name: `??1CProcessResourceAttributionReporter@@AEAA@XZ`
- size: `177`
- prototype: `void __fastcall(CProcessResourceAttributionReporter *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180216c30`

## callees

- `0x1800d32c0`
- `0x18016d100`
- `0x180213c80`
- `0x18023592c`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18023594c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18023594c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180235942`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180235942`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedFlushSList` at `0x180235956`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedFlushSList` at `0x180235956`

## pseudocode

```c
void __fastcall CProcessResourceAttributionReporter::~CProcessResourceAttributionReporter(
        CProcessResourceAttributionReporter *this)
{
  PSLIST_ENTRY v2; // rdi
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  __int64 v4; // rcx
  PSLIST_ENTRY v5; // [rsp+30h] [rbp+8h] BYREF

  WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 1), 1);
  CloseThreadpoolWork(*((PTP_WORK *)this + 1));
  v2 = InterlockedFlushSList((PSLIST_HEADER)this + 1);
  while ( v2 )
  {
    v5 = v2;
    v2 = v2->Next;
    std::unique_ptr<CProcessResourceAttributionReporter::HighResourceUsageReport>::~unique_ptr<CProcessResourceAttributionReporter::HighResourceUsageReport>(&v5);
  }
  v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 7);
  if ( v3 )
    (**v3)(v3, 1);
  v4 = *((_QWORD *)this + 4);
  if ( v4 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<CProcessResourceAttributionReporter::ResourceThresholdForProcessSequenceNumber>>>(
      v4,
      *((_QWORD *)this + 5));
    std::_Deallocate<16>(*((_QWORD *)this + 4), (*((_QWORD *)this + 6) - *((_QWORD *)this + 4)) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 4) = 0;
    *((_QWORD *)this + 5) = 0;
    *((_QWORD *)this + 6) = 0;
  }
}

```

## disassembly

```asm
0x18023592c  mov     [rsp+arg_8], rbx
0x180235931  push    rdi
0x180235932  sub     rsp, 20h
0x180235936  mov     rbx, rcx
0x180235939  mov     edx, 1; fCancelPendingCallbacks
0x18023593e  mov     rcx, [rcx+8]; pwk
0x180235942  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180235948  mov     rcx, [rbx+8]; pwk
0x18023594c  call    cs:__imp_CloseThreadpoolWork
0x180235952  lea     rcx, [rbx+10h]; ListHead
0x180235956  call    cs:__imp_InterlockedFlushSList
0x18023595c  mov     rdi, rax
0x18023595f  test    rax, rax
0x180235962  jz      short loc_18023597B
0x180235964  mov     [rsp+28h+arg_0], rdi
0x180235969  lea     rcx, [rsp+28h+arg_0]
0x18023596e  mov     rdi, [rdi]
0x180235971  call    ??1?$unique_ptr@UHighResourceUsageReport@CProcessResourceAttributionReporter@@U?$default_delete@UHighResourceUsageReport@CProcessResourceAttributionReporter@@@std@@@std@@QEAA@XZ; std::unique_ptr<CProcessResourceAttributionReporter::HighResourceUsageReport>::~unique_ptr<CProcessResourceAttributionReporter::HighResourceUsageReport>(void)
0x180235976  test    rdi, rdi
0x180235979  jnz     short loc_180235964
0x18023597b  mov     rcx, [rbx+38h]
0x18023597f  test    rcx, rcx
0x180235982  jz      short loc_180235994
0x180235984  mov     rax, [rcx]
0x180235987  mov     edx, 1
0x18023598c  mov     rax, [rax]
0x18023598f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180235994  mov     rcx, [rbx+20h]
0x180235998  test    rcx, rcx
0x18023599b  jz      short loc_1802359D2
0x18023599d  mov     rdx, [rbx+28h]
0x1802359a1  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UResourceThresholdForProcessSequenceNumber@CProcessResourceAttributionReporter@@U?$default_delete@UResourceThresholdForProcessSequenceNumber@CProcessResourceAttributionReporter@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UResourceThresholdForProcessSequenceNumber@CProcessResourceAttributionReporter@@U?$default_delete@UResourceThresholdForProcessSequenceNumber@CProcessResourceAttributionReporter@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UResourceThresholdForProcessSequenceNumber@CProcessResourceAttributionReporter@@U?$default_delete@UResourceThresholdForProcessSequenceNumber@CProcessResourceAttributionReporter@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<CProcessResourceAttributionReporter::ResourceThresholdForProcessSequenceNumber>>>(std::unique_ptr<CProcessResourceAttributionReporter::ResourceThresholdForProcessSequenceNumber> *,std::unique_ptr<CProcessResourceAttributionReporter::ResourceThresholdForProcessSequenceNumber> * const,std::allocator<std::unique_ptr<CProcessResourceAttributionReporter::ResourceThresholdForProcessSequenceNumber>> &)
0x1802359a6  mov     rcx, [rbx+20h]
0x1802359aa  mov     rdx, [rbx+30h]
0x1802359ae  sub     rdx, rcx
0x1802359b1  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1802359b5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1802359ba  mov     qword ptr [rbx+20h], 0
0x1802359c2  mov     qword ptr [rbx+28h], 0
0x1802359ca  mov     qword ptr [rbx+30h], 0
0x1802359d2  mov     rbx, [rsp+28h+arg_8]
0x1802359d7  add     rsp, 20h
0x1802359db  pop     rdi
0x1802359dc  retn
```
