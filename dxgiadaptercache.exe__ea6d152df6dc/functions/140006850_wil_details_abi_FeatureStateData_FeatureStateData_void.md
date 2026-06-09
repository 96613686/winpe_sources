# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140006850`
- end: `0x140006920`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140006110`

## callees

- `0x140005c9c`
- `0x140006850`
- `0x140006d54`
- `0x14000b1bc`
- `0x14000dd34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400068fd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400068fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400068e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400068e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400068f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400068f0`

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
0x140006850  mov     [rsp+arg_0], rbx
0x140006855  mov     [rsp+arg_8], rsi
0x14000685a  push    rdi
0x14000685b  sub     rsp, 0E0h
0x140006862  mov     rbx, rcx
0x140006865  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000686a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000686f  cmp     byte ptr [rbx+40h], 0
0x140006873  jz      short loc_140006883
0x140006875  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140006879  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000687e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140006883  cmp     byte ptr [rbx+80h], 0
0x14000688a  jz      short loc_14000689A
0x14000688c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140006890  lea     rcx, [rsp+0E8h+var_88]; this
0x140006895  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000689a  cmp     byte ptr [rbx+0C0h], 0
0x1400068a1  jz      short loc_1400068B7
0x1400068a3  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1400068aa  lea     rcx, [rsp+0E8h+var_48]; this
0x1400068b2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1400068b7  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400068bc  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1400068c1  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400068c6  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1400068cb  mov     rsi, [rbx+108h]
0x1400068d2  mov     qword ptr [rbx+108h], 0
0x1400068dd  test    rsi, rsi
0x1400068e0  jz      short loc_1400068F6
0x1400068e2  call    cs:__imp_GetProcessHeap
0x1400068e8  mov     rcx, rax; hHeap
0x1400068eb  mov     r8, rsi; lpMem
0x1400068ee  xor     edx, edx; dwFlags
0x1400068f0  call    cs:__imp_HeapFree
0x1400068f6  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1400068fd  call    cs:__imp_DeleteCriticalSection
0x140006903  lea     rcx, [rbx+8]; this
0x140006907  lea     r11, [rsp+0E8h+var_8]
0x14000690f  mov     rbx, [r11+10h]
0x140006913  mov     rsi, [r11+18h]
0x140006917  mov     rsp, r11
0x14000691a  pop     rdi
0x14000691b  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
