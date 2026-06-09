# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180020d2c`
- end: `0x180020dfc`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180020c14`

## callees

- `0x180020a80`
- `0x180020d2c`
- `0x1800210b4`
- `0x180022b98`
- `0x180023ff0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020dbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020dbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020dcc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020dcc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020dd9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020dd9`

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
0x180020d2c  mov     [rsp+arg_0], rbx
0x180020d31  mov     [rsp+arg_8], rsi
0x180020d36  push    rdi
0x180020d37  sub     rsp, 0E0h
0x180020d3e  mov     rbx, rcx
0x180020d41  lea     rcx, [rsp+0E8h+var_C8]; this
0x180020d46  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180020d4b  cmp     byte ptr [rbx+40h], 0
0x180020d4f  jz      short loc_180020D5F
0x180020d51  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180020d55  lea     rcx, [rsp+0E8h+var_C8]; this
0x180020d5a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180020d5f  cmp     byte ptr [rbx+80h], 0
0x180020d66  jz      short loc_180020D76
0x180020d68  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180020d6c  lea     rcx, [rsp+0E8h+var_88]; this
0x180020d71  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180020d76  cmp     byte ptr [rbx+0C0h], 0
0x180020d7d  jz      short loc_180020D93
0x180020d7f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180020d86  lea     rcx, [rsp+0E8h+var_48]; this
0x180020d8e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180020d93  lea     rcx, [rsp+0E8h+var_C8]; this
0x180020d98  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180020d9d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180020da2  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180020da7  mov     rsi, [rbx+108h]
0x180020dae  mov     qword ptr [rbx+108h], 0
0x180020db9  test    rsi, rsi
0x180020dbc  jz      short loc_180020DD2
0x180020dbe  call    cs:__imp_GetProcessHeap
0x180020dc4  mov     rcx, rax; hHeap
0x180020dc7  mov     r8, rsi; lpMem
0x180020dca  xor     edx, edx; dwFlags
0x180020dcc  call    cs:__imp_HeapFree
0x180020dd2  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180020dd9  call    cs:__imp_DeleteCriticalSection
0x180020ddf  lea     rcx, [rbx+8]; this
0x180020de3  lea     r11, [rsp+0E8h+var_8]
0x180020deb  mov     rbx, [r11+10h]
0x180020def  mov     rsi, [r11+18h]
0x180020df3  mov     rsp, r11
0x180020df6  pop     rdi
0x180020df7  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
