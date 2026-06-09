# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180010f08`
- end: `0x180010fd8`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000fe14`

## callees

- `0x18000fbfc`
- `0x180010f08`
- `0x18001150c`
- `0x18001b998`
- `0x1800200c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010f9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010f9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010fa8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010fa8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010fb5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010fb5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
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
0x180010f08  mov     [rsp+arg_0], rbx
0x180010f0d  mov     [rsp+arg_8], rsi
0x180010f12  push    rdi
0x180010f13  sub     rsp, 0E0h
0x180010f1a  mov     rbx, rcx
0x180010f1d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180010f22  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180010f27  cmp     byte ptr [rbx+40h], 0
0x180010f2b  jz      short loc_180010F3B
0x180010f2d  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180010f31  lea     rcx, [rsp+0E8h+var_C8]; this
0x180010f36  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180010f3b  cmp     byte ptr [rbx+80h], 0
0x180010f42  jz      short loc_180010F52
0x180010f44  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180010f48  lea     rcx, [rsp+0E8h+var_88]; this
0x180010f4d  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180010f52  cmp     byte ptr [rbx+0C0h], 0
0x180010f59  jz      short loc_180010F6F
0x180010f5b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180010f62  lea     rcx, [rsp+0E8h+var_48]; this
0x180010f6a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180010f6f  lea     rcx, [rsp+0E8h+var_C8]; this
0x180010f74  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180010f79  lea     rcx, [rsp+0E8h+var_C8]; this
0x180010f7e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180010f83  mov     rsi, [rbx+108h]
0x180010f8a  mov     qword ptr [rbx+108h], 0
0x180010f95  test    rsi, rsi
0x180010f98  jz      short loc_180010FAE
0x180010f9a  call    cs:__imp_GetProcessHeap
0x180010fa0  mov     rcx, rax; hHeap
0x180010fa3  mov     r8, rsi; lpMem
0x180010fa6  xor     edx, edx; dwFlags
0x180010fa8  call    cs:__imp_HeapFree
0x180010fae  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180010fb5  call    cs:__imp_DeleteCriticalSection
0x180010fbb  lea     rcx, [rbx+8]; this
0x180010fbf  lea     r11, [rsp+0E8h+var_8]
0x180010fc7  mov     rbx, [r11+10h]
0x180010fcb  mov     rsi, [r11+18h]
0x180010fcf  mov     rsp, r11
0x180010fd2  pop     rdi
0x180010fd3  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
