# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140012ef8`
- end: `0x140012fc8`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140012dc0`

## callees

- `0x140012cf8`
- `0x140012ef8`
- `0x1400131fc`
- `0x140014d0c`
- `0x140016684`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140012fa5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140012fa5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012f8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012f8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012f98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012f98`

## pseudocode

```c
void __fastcall wil::details_abi::FeatureStateData::~FeatureStateData(wil::details_abi::FeatureStateData *this)
{
  void *v2; // rsi
  HANDLE ProcessHeap; // rax
  _BYTE v4[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v5[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v6[64]; // [rsp+A0h] [rbp-48h] BYREF

  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v4);
  if ( *((_BYTE *)this + 64) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v4,
      (wil::details_abi::FeatureStateData *)((char *)this + 8));
  if ( *((_BYTE *)this + 128) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v5,
      (wil::details_abi::FeatureStateData *)((char *)this + 72));
  if ( *((_BYTE *)this + 192) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v6,
      (wil::details_abi::FeatureStateData *)((char *)this + 136));
  wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v4);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v4);
  v2 = (void *)*((_QWORD *)this + 33);
  *((_QWORD *)this + 33) = 0;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 5);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::FeatureStateData *)((char *)this + 8));
}

```

## disassembly

```asm
0x140012ef8  mov     [rsp+arg_0], rbx
0x140012efd  mov     [rsp+arg_8], rsi
0x140012f02  push    rdi
0x140012f03  sub     rsp, 0E0h
0x140012f0a  mov     rbx, rcx
0x140012f0d  lea     rcx, [rsp+0E8h+var_C8]; this
0x140012f12  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140012f17  cmp     byte ptr [rbx+40h], 0
0x140012f1b  jz      short loc_140012F2B
0x140012f1d  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140012f21  lea     rcx, [rsp+0E8h+var_C8]; this
0x140012f26  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140012f2b  cmp     byte ptr [rbx+80h], 0
0x140012f32  jz      short loc_140012F42
0x140012f34  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140012f38  lea     rcx, [rsp+0E8h+var_88]; this
0x140012f3d  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140012f42  cmp     byte ptr [rbx+0C0h], 0
0x140012f49  jz      short loc_140012F5F
0x140012f4b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140012f52  lea     rcx, [rsp+0E8h+var_48]; this
0x140012f5a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140012f5f  lea     rcx, [rsp+0E8h+var_C8]; this
0x140012f64  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140012f69  lea     rcx, [rsp+0E8h+var_C8]; this
0x140012f6e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140012f73  mov     rsi, [rbx+108h]
0x140012f7a  mov     qword ptr [rbx+108h], 0
0x140012f85  test    rsi, rsi
0x140012f88  jz      short loc_140012F9E
0x140012f8a  call    cs:__imp_GetProcessHeap
0x140012f90  mov     rcx, rax; hHeap
0x140012f93  mov     r8, rsi; lpMem
0x140012f96  xor     edx, edx; dwFlags
0x140012f98  call    cs:__imp_HeapFree
0x140012f9e  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140012fa5  call    cs:__imp_DeleteCriticalSection
0x140012fab  lea     rcx, [rbx+8]; this
0x140012faf  lea     r11, [rsp+0E8h+var_8]
0x140012fb7  mov     rbx, [r11+10h]
0x140012fbb  mov     rsi, [r11+18h]
0x140012fbf  mov     rsp, r11
0x140012fc2  pop     rdi
0x140012fc3  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
