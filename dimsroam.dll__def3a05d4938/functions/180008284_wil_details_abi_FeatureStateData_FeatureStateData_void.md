# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180008284`
- end: `0x180008354`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008190`

## callees

- `0x180007ffc`
- `0x180008284`
- `0x1800085d4`
- `0x18000ab1c`
- `0x18000c1a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008331`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008331`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008324`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008324`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008316`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008316`

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
0x180008284  mov     [rsp+arg_0], rbx
0x180008289  mov     [rsp+arg_8], rsi
0x18000828e  push    rdi
0x18000828f  sub     rsp, 0E0h
0x180008296  mov     rbx, rcx
0x180008299  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000829e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800082a3  cmp     byte ptr [rbx+40h], 0
0x1800082a7  jz      short loc_1800082B7
0x1800082a9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1800082ad  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800082b2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800082b7  cmp     byte ptr [rbx+80h], 0
0x1800082be  jz      short loc_1800082CE
0x1800082c0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800082c4  lea     rcx, [rsp+0E8h+var_88]; this
0x1800082c9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800082ce  cmp     byte ptr [rbx+0C0h], 0
0x1800082d5  jz      short loc_1800082EB
0x1800082d7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800082de  lea     rcx, [rsp+0E8h+var_48]; this
0x1800082e6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800082eb  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800082f0  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800082f5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800082fa  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800082ff  mov     rsi, [rbx+108h]
0x180008306  mov     qword ptr [rbx+108h], 0
0x180008311  test    rsi, rsi
0x180008314  jz      short loc_18000832A
0x180008316  call    cs:__imp_GetProcessHeap
0x18000831c  mov     r8, rsi; lpMem
0x18000831f  xor     edx, edx; dwFlags
0x180008321  mov     rcx, rax; hHeap
0x180008324  call    cs:__imp_HeapFree
0x18000832a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180008331  call    cs:__imp_DeleteCriticalSection
0x180008337  lea     rcx, [rbx+8]; this
0x18000833b  lea     r11, [rsp+0E8h+var_8]
0x180008343  mov     rbx, [r11+10h]
0x180008347  mov     rsi, [r11+18h]
0x18000834b  mov     rsp, r11
0x18000834e  pop     rdi
0x18000834f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
