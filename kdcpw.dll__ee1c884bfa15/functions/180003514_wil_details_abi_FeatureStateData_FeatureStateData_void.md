# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180003514`
- end: `0x1800035e4`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800032d4`

## callees

- `0x180003140`
- `0x180003514`
- `0x180003864`
- `0x180006744`
- `0x180008530`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800035c1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800035c1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035a6`

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
0x180003514  mov     [rsp+arg_0], rbx
0x180003519  mov     [rsp+arg_8], rsi
0x18000351e  push    rdi
0x18000351f  sub     rsp, 0E0h
0x180003526  mov     rbx, rcx
0x180003529  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000352e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003533  cmp     byte ptr [rbx+40h], 0
0x180003537  jz      short loc_180003547
0x180003539  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000353d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003542  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003547  cmp     byte ptr [rbx+80h], 0
0x18000354e  jz      short loc_18000355E
0x180003550  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180003554  lea     rcx, [rsp+0E8h+var_88]; this
0x180003559  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000355e  cmp     byte ptr [rbx+0C0h], 0
0x180003565  jz      short loc_18000357B
0x180003567  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000356e  lea     rcx, [rsp+0E8h+var_48]; this
0x180003576  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000357b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003580  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003585  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000358a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000358f  mov     rsi, [rbx+108h]
0x180003596  mov     qword ptr [rbx+108h], 0
0x1800035a1  test    rsi, rsi
0x1800035a4  jz      short loc_1800035BA
0x1800035a6  call    cs:__imp_GetProcessHeap
0x1800035ac  mov     r8, rsi; lpMem
0x1800035af  xor     edx, edx; dwFlags
0x1800035b1  mov     rcx, rax; hHeap
0x1800035b4  call    cs:__imp_HeapFree
0x1800035ba  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800035c1  call    cs:__imp_DeleteCriticalSection
0x1800035c7  lea     rcx, [rbx+8]; this
0x1800035cb  lea     r11, [rsp+0E8h+var_8]
0x1800035d3  mov     rbx, [r11+10h]
0x1800035d7  mov     rsi, [r11+18h]
0x1800035db  mov     rsp, r11
0x1800035de  pop     rdi
0x1800035df  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
