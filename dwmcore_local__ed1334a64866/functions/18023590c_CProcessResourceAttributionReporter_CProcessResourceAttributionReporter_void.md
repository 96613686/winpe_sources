# CProcessResourceAttributionReporter::~CProcessResourceAttributionReporter(void)

- ea: `0x18023590c`
- end: `0x1802359bd`
- name: `??1CProcessResourceAttributionReporter@@AEAA@XZ`
- size: `177`
- prototype: `void __fastcall(CProcessResourceAttributionReporter *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180216c10`

## callees

- `0x1800d5b30`
- `0x1801680e0`
- `0x180213c60`
- `0x18023590c`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18023592c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18023592c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180235922`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180235922`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedFlushSList` at `0x180235936`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedFlushSList` at `0x180235936`

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
0x18023590c  mov     [rsp+arg_8], rbx
0x180235911  push    rdi
0x180235912  sub     rsp, 20h
0x180235916  mov     rbx, rcx
0x180235919  mov     edx, 1; fCancelPendingCallbacks
0x18023591e  mov     rcx, [rcx+8]; pwk
0x180235922  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180235928  mov     rcx, [rbx+8]; pwk
0x18023592c  call    cs:__imp_CloseThreadpoolWork
0x180235932  lea     rcx, [rbx+10h]; ListHead
0x180235936  call    cs:__imp_InterlockedFlushSList
0x18023593c  mov     rdi, rax
0x18023593f  test    rax, rax
0x180235942  jz      short loc_18023595B
0x180235944  mov     [rsp+28h+arg_0], rdi
0x180235949  lea     rcx, [rsp+28h+arg_0]
0x18023594e  mov     rdi, [rdi]
0x180235951  call    ??1?$unique_ptr@UHighResourceUsageReport@CProcessResourceAttributionReporter@@U?$default_delete@UHighResourceUsageReport@CProcessResourceAttributionReporter@@@std@@@std@@QEAA@XZ; std::unique_ptr<CProcessResourceAttributionReporter::HighResourceUsageReport>::~unique_ptr<CProcessResourceAttributionReporter::HighResourceUsageReport>(void)
0x180235956  test    rdi, rdi
0x180235959  jnz     short loc_180235944
0x18023595b  mov     rcx, [rbx+38h]
0x18023595f  test    rcx, rcx
0x180235962  jz      short loc_180235974
0x180235964  mov     rax, [rcx]
0x180235967  mov     edx, 1
0x18023596c  mov     rax, [rax]
0x18023596f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180235974  mov     rcx, [rbx+20h]
0x180235978  test    rcx, rcx
0x18023597b  jz      short loc_1802359B2
0x18023597d  mov     rdx, [rbx+28h]
0x180235981  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UResourceThresholdForProcessSequenceNumber@CProcessResourceAttributionReporter@@U?$default_delete@UResourceThresholdForProcessSequenceNumber@CProcessResourceAttributionReporter@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UResourceThresholdForProcessSequenceNumber@CProcessResourceAttributionReporter@@U?$default_delete@UResourceThresholdForProcessSequenceNumber@CProcessResourceAttributionReporter@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UResourceThresholdForProcessSequenceNumber@CProcessResourceAttributionReporter@@U?$default_delete@UResourceThresholdForProcessSequenceNumber@CProcessResourceAttributionReporter@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<CProcessResourceAttributionReporter::ResourceThresholdForProcessSequenceNumber>>>(std::unique_ptr<CProcessResourceAttributionReporter::ResourceThresholdForProcessSequenceNumber> *,std::unique_ptr<CProcessResourceAttributionReporter::ResourceThresholdForProcessSequenceNumber> * const,std::allocator<std::unique_ptr<CProcessResourceAttributionReporter::ResourceThresholdForProcessSequenceNumber>> &)
0x180235986  mov     rcx, [rbx+20h]
0x18023598a  mov     rdx, [rbx+30h]
0x18023598e  sub     rdx, rcx
0x180235991  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180235995  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18023599a  mov     qword ptr [rbx+20h], 0
0x1802359a2  mov     qword ptr [rbx+28h], 0
0x1802359aa  mov     qword ptr [rbx+30h], 0
0x1802359b2  mov     rbx, [rsp+28h+arg_8]
0x1802359b7  add     rsp, 20h
0x1802359bb  pop     rdi
0x1802359bc  retn
```
