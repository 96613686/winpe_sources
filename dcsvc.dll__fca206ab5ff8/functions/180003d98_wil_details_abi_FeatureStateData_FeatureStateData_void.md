# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180003d98`
- end: `0x180003e68`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180003b20`

## callees

- `0x180003954`
- `0x180003d98`
- `0x18000420c`
- `0x180006c9c`
- `0x1800095a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e2a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e38`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e38`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003e45`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003e45`

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
0x180003d98  mov     [rsp+arg_0], rbx
0x180003d9d  mov     [rsp+arg_8], rsi
0x180003da2  push    rdi
0x180003da3  sub     rsp, 0E0h
0x180003daa  mov     rbx, rcx
0x180003dad  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003db2  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003db7  cmp     byte ptr [rbx+40h], 0
0x180003dbb  jz      short loc_180003DCB
0x180003dbd  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180003dc1  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003dc6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003dcb  cmp     byte ptr [rbx+80h], 0
0x180003dd2  jz      short loc_180003DE2
0x180003dd4  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180003dd8  lea     rcx, [rsp+0E8h+var_88]; this
0x180003ddd  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003de2  cmp     byte ptr [rbx+0C0h], 0
0x180003de9  jz      short loc_180003DFF
0x180003deb  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180003df2  lea     rcx, [rsp+0E8h+var_48]; this
0x180003dfa  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003dff  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003e04  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003e09  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003e0e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180003e13  mov     rsi, [rbx+108h]
0x180003e1a  mov     qword ptr [rbx+108h], 0
0x180003e25  test    rsi, rsi
0x180003e28  jz      short loc_180003E3E
0x180003e2a  call    cs:__imp_GetProcessHeap
0x180003e30  mov     rcx, rax; hHeap
0x180003e33  mov     r8, rsi; lpMem
0x180003e36  xor     edx, edx; dwFlags
0x180003e38  call    cs:__imp_HeapFree
0x180003e3e  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180003e45  call    cs:__imp_DeleteCriticalSection
0x180003e4b  lea     rcx, [rbx+8]; this
0x180003e4f  lea     r11, [rsp+0E8h+var_8]
0x180003e57  mov     rbx, [r11+10h]
0x180003e5b  mov     rsi, [r11+18h]
0x180003e5f  mov     rsp, r11
0x180003e62  pop     rdi
0x180003e63  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
