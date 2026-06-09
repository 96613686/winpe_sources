# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180003ea4`
- end: `0x180003f74`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180003c64`

## callees

- `0x180003ad0`
- `0x180003ea4`
- `0x1800041f4`
- `0x180007a10`
- `0x180009a30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003f51`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003f51`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003f44`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003f36`

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
0x180003ea4  mov     [rsp+arg_0], rbx
0x180003ea9  mov     [rsp+arg_8], rsi
0x180003eae  push    rdi
0x180003eaf  sub     rsp, 0E0h
0x180003eb6  mov     rbx, rcx
0x180003eb9  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003ebe  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003ec3  cmp     byte ptr [rbx+40h], 0
0x180003ec7  jz      short loc_180003ED7
0x180003ec9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180003ecd  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003ed2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003ed7  cmp     byte ptr [rbx+80h], 0
0x180003ede  jz      short loc_180003EEE
0x180003ee0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180003ee4  lea     rcx, [rsp+0E8h+var_88]; this
0x180003ee9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003eee  cmp     byte ptr [rbx+0C0h], 0
0x180003ef5  jz      short loc_180003F0B
0x180003ef7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180003efe  lea     rcx, [rsp+0E8h+var_48]; this
0x180003f06  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003f0b  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003f10  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003f15  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003f1a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180003f1f  mov     rsi, [rbx+108h]
0x180003f26  mov     qword ptr [rbx+108h], 0
0x180003f31  test    rsi, rsi
0x180003f34  jz      short loc_180003F4A
0x180003f36  call    cs:__imp_GetProcessHeap
0x180003f3c  mov     r8, rsi; lpMem
0x180003f3f  xor     edx, edx; dwFlags
0x180003f41  mov     rcx, rax; hHeap
0x180003f44  call    cs:__imp_HeapFree
0x180003f4a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180003f51  call    cs:__imp_DeleteCriticalSection
0x180003f57  lea     rcx, [rbx+8]; this
0x180003f5b  lea     r11, [rsp+0E8h+var_8]
0x180003f63  mov     rbx, [r11+10h]
0x180003f67  mov     rsi, [r11+18h]
0x180003f6b  mov     rsp, r11
0x180003f6e  pop     rdi
0x180003f6f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
