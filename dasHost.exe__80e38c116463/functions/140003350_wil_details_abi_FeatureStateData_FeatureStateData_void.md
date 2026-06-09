# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140003350`
- end: `0x140003420`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400031f8`

## callees

- `0x14000302c`
- `0x140003350`
- `0x1400037c4`
- `0x140005bc8`
- `0x140007aac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400033fd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400033fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400033f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400033f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400033e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400033e2`

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
0x140003350  mov     [rsp+arg_0], rbx
0x140003355  mov     [rsp+arg_8], rsi
0x14000335a  push    rdi
0x14000335b  sub     rsp, 0E0h
0x140003362  mov     rbx, rcx
0x140003365  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000336a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000336f  cmp     byte ptr [rbx+40h], 0
0x140003373  jz      short loc_140003383
0x140003375  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140003379  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000337e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140003383  cmp     byte ptr [rbx+80h], 0
0x14000338a  jz      short loc_14000339A
0x14000338c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140003390  lea     rcx, [rsp+0E8h+var_88]; this
0x140003395  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000339a  cmp     byte ptr [rbx+0C0h], 0
0x1400033a1  jz      short loc_1400033B7
0x1400033a3  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1400033aa  lea     rcx, [rsp+0E8h+var_48]; this
0x1400033b2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1400033b7  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400033bc  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1400033c1  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400033c6  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1400033cb  mov     rsi, [rbx+108h]
0x1400033d2  mov     qword ptr [rbx+108h], 0
0x1400033dd  test    rsi, rsi
0x1400033e0  jz      short loc_1400033F6
0x1400033e2  call    cs:__imp_GetProcessHeap
0x1400033e8  mov     rcx, rax; hHeap
0x1400033eb  mov     r8, rsi; lpMem
0x1400033ee  xor     edx, edx; dwFlags
0x1400033f0  call    cs:__imp_HeapFree
0x1400033f6  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1400033fd  call    cs:__imp_DeleteCriticalSection
0x140003403  lea     rcx, [rbx+8]; this
0x140003407  lea     r11, [rsp+0E8h+var_8]
0x14000340f  mov     rbx, [r11+10h]
0x140003413  mov     rsi, [r11+18h]
0x140003417  mov     rsp, r11
0x14000341a  pop     rdi
0x14000341b  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
