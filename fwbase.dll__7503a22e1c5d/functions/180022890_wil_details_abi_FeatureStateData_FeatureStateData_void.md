# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180022890`
- end: `0x1800228f7`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `103`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180027550`

## callees

- `0x180022890`
- `0x180022a00`
- `0x180025e70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800228d9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800228d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800228cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800228cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800228be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800228be`

## pseudocode

```c
void __fastcall wil::details_abi::FeatureStateData::~FeatureStateData(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE LockSemaphore; // rsi
  HANDLE ProcessHeap; // rax

  wil::details_abi::FeatureStateData::ProcessShutdown((wil::details_abi::FeatureStateData *)this);
  LockSemaphore = this[6].LockSemaphore;
  this[6].LockSemaphore = 0;
  if ( LockSemaphore )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, LockSemaphore);
  }
  DeleteCriticalSection(this + 5);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)&this->LockCount);
}

```

## disassembly

```asm
0x180022890  mov     [rsp+arg_0], rbx
0x180022895  mov     [rsp+arg_8], rsi
0x18002289a  push    rdi
0x18002289b  sub     rsp, 20h
0x18002289f  mov     rbx, rcx
0x1800228a2  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x1800228a7  mov     rsi, [rbx+108h]
0x1800228ae  mov     qword ptr [rbx+108h], 0
0x1800228b9  test    rsi, rsi
0x1800228bc  jz      short loc_1800228D2
0x1800228be  call    cs:__imp_GetProcessHeap
0x1800228c4  mov     rcx, rax; hHeap
0x1800228c7  mov     r8, rsi; lpMem
0x1800228ca  xor     edx, edx; dwFlags
0x1800228cc  call    cs:__imp_HeapFree
0x1800228d2  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800228d9  call    cs:__imp_DeleteCriticalSection
0x1800228df  lea     rcx, [rbx+8]; this
0x1800228e3  mov     rbx, [rsp+28h+arg_0]
0x1800228e8  mov     rsi, [rsp+28h+arg_8]
0x1800228ed  add     rsp, 20h
0x1800228f1  pop     rdi
0x1800228f2  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
