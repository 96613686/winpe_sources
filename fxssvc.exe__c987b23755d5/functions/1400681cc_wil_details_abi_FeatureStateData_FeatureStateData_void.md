# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1400681cc`
- end: `0x14006829c`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400680b4`

## callees

- `0x140067f20`
- `0x1400681cc`
- `0x140068638`
- `0x14006af5c`
- `0x14006ca78`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14006825e`
- `KERNEL32!GetProcessHeap` at `0x14006825e`
- `KERNEL32!HeapFree` at `0x14006826c`
- `KERNEL32!HeapFree` at `0x14006826c`
- `KERNEL32!DeleteCriticalSection` at `0x140068279`
- `KERNEL32!DeleteCriticalSection` at `0x140068279`

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
0x1400681cc  mov     [rsp+arg_0], rbx
0x1400681d1  mov     [rsp+arg_8], rsi
0x1400681d6  push    rdi
0x1400681d7  sub     rsp, 0E0h
0x1400681de  mov     rbx, rcx
0x1400681e1  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400681e6  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1400681eb  cmp     byte ptr [rbx+40h], 0
0x1400681ef  jz      short loc_1400681FF
0x1400681f1  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1400681f5  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400681fa  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1400681ff  cmp     byte ptr [rbx+80h], 0
0x140068206  jz      short loc_140068216
0x140068208  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x14006820c  lea     rcx, [rsp+0E8h+var_88]; this
0x140068211  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140068216  cmp     byte ptr [rbx+0C0h], 0
0x14006821d  jz      short loc_140068233
0x14006821f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140068226  lea     rcx, [rsp+0E8h+var_48]; this
0x14006822e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140068233  lea     rcx, [rsp+0E8h+var_C8]; this
0x140068238  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x14006823d  lea     rcx, [rsp+0E8h+var_C8]; this
0x140068242  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140068247  mov     rsi, [rbx+108h]
0x14006824e  mov     qword ptr [rbx+108h], 0
0x140068259  test    rsi, rsi
0x14006825c  jz      short loc_140068272
0x14006825e  call    cs:__imp_GetProcessHeap
0x140068264  mov     rcx, rax; hHeap
0x140068267  mov     r8, rsi; lpMem
0x14006826a  xor     edx, edx; dwFlags
0x14006826c  call    cs:__imp_HeapFree
0x140068272  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140068279  call    cs:__imp_DeleteCriticalSection
0x14006827f  lea     rcx, [rbx+8]; this
0x140068283  lea     r11, [rsp+0E8h+var_8]
0x14006828b  mov     rbx, [r11+10h]
0x14006828f  mov     rsi, [r11+18h]
0x140068293  mov     rsp, r11
0x140068296  pop     rdi
0x140068297  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
