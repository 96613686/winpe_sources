# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140004fd0`
- end: `0x1400050a0`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140004da8`

## callees

- `0x140004a98`
- `0x140004fd0`
- `0x140005490`
- `0x140008740`
- `0x14000a56c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000507d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000507d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005062`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005062`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005070`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005070`

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
0x140004fd0  mov     [rsp+arg_0], rbx
0x140004fd5  mov     [rsp+arg_8], rsi
0x140004fda  push    rdi
0x140004fdb  sub     rsp, 0E0h
0x140004fe2  mov     rbx, rcx
0x140004fe5  lea     rcx, [rsp+0E8h+var_C8]; this
0x140004fea  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140004fef  cmp     byte ptr [rbx+40h], 0
0x140004ff3  jz      short loc_140005003
0x140004ff5  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140004ff9  lea     rcx, [rsp+0E8h+var_C8]; this
0x140004ffe  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140005003  cmp     byte ptr [rbx+80h], 0
0x14000500a  jz      short loc_14000501A
0x14000500c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140005010  lea     rcx, [rsp+0E8h+var_88]; this
0x140005015  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000501a  cmp     byte ptr [rbx+0C0h], 0
0x140005021  jz      short loc_140005037
0x140005023  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14000502a  lea     rcx, [rsp+0E8h+var_48]; this
0x140005032  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140005037  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000503c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140005041  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005046  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000504b  mov     rsi, [rbx+108h]
0x140005052  mov     qword ptr [rbx+108h], 0
0x14000505d  test    rsi, rsi
0x140005060  jz      short loc_140005076
0x140005062  call    cs:__imp_GetProcessHeap
0x140005068  mov     rcx, rax; hHeap
0x14000506b  mov     r8, rsi; lpMem
0x14000506e  xor     edx, edx; dwFlags
0x140005070  call    cs:__imp_HeapFree
0x140005076  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x14000507d  call    cs:__imp_DeleteCriticalSection
0x140005083  lea     rcx, [rbx+8]; this
0x140005087  lea     r11, [rsp+0E8h+var_8]
0x14000508f  mov     rbx, [r11+10h]
0x140005093  mov     rsi, [r11+18h]
0x140005097  mov     rsp, r11
0x14000509a  pop     rdi
0x14000509b  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
