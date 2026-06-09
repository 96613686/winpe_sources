# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18000cb24`
- end: `0x18000cbf4`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ca30`

## callees

- `0x18000c968`
- `0x18000cb24`
- `0x18000cdf0`
- `0x18000ff84`
- `0x180011008`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cbd1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cbd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cbb6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cbb6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cbc4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cbc4`

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
0x18000cb24  mov     [rsp+arg_0], rbx
0x18000cb29  mov     [rsp+arg_8], rsi
0x18000cb2e  push    rdi
0x18000cb2f  sub     rsp, 0E0h
0x18000cb36  mov     rbx, rcx
0x18000cb39  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000cb3e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000cb43  cmp     byte ptr [rbx+40h], 0
0x18000cb47  jz      short loc_18000CB57
0x18000cb49  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000cb4d  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000cb52  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000cb57  cmp     byte ptr [rbx+80h], 0
0x18000cb5e  jz      short loc_18000CB6E
0x18000cb60  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000cb64  lea     rcx, [rsp+0E8h+var_88]; this
0x18000cb69  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000cb6e  cmp     byte ptr [rbx+0C0h], 0
0x18000cb75  jz      short loc_18000CB8B
0x18000cb77  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000cb7e  lea     rcx, [rsp+0E8h+var_48]; this
0x18000cb86  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000cb8b  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000cb90  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000cb95  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000cb9a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000cb9f  mov     rsi, [rbx+108h]
0x18000cba6  mov     qword ptr [rbx+108h], 0
0x18000cbb1  test    rsi, rsi
0x18000cbb4  jz      short loc_18000CBCA
0x18000cbb6  call    cs:__imp_GetProcessHeap
0x18000cbbc  mov     r8, rsi; lpMem
0x18000cbbf  xor     edx, edx; dwFlags
0x18000cbc1  mov     rcx, rax; hHeap
0x18000cbc4  call    cs:__imp_HeapFree
0x18000cbca  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000cbd1  call    cs:__imp_DeleteCriticalSection
0x18000cbd7  lea     rcx, [rbx+8]; this
0x18000cbdb  lea     r11, [rsp+0E8h+var_8]
0x18000cbe3  mov     rbx, [r11+10h]
0x18000cbe7  mov     rsi, [r11+18h]
0x18000cbeb  mov     rsp, r11
0x18000cbee  pop     rdi
0x18000cbef  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
