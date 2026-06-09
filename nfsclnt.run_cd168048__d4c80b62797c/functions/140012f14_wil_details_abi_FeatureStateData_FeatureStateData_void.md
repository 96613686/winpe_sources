# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140012f14`
- end: `0x140012fe4`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140012e20`

## callees

- `0x140012c8c`
- `0x140012f14`
- `0x140013264`
- `0x1400157ac`
- `0x140016e30`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140012fb4`
- `KERNEL32!HeapFree` at `0x140012fb4`
- `KERNEL32!GetProcessHeap` at `0x140012fa6`
- `KERNEL32!GetProcessHeap` at `0x140012fa6`
- `KERNEL32!DeleteCriticalSection` at `0x140012fc1`
- `KERNEL32!DeleteCriticalSection` at `0x140012fc1`

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
0x140012f14  mov     [rsp+arg_0], rbx
0x140012f19  mov     [rsp+arg_8], rsi
0x140012f1e  push    rdi
0x140012f1f  sub     rsp, 0E0h
0x140012f26  mov     rbx, rcx
0x140012f29  lea     rcx, [rsp+0E8h+var_C8]; this
0x140012f2e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140012f33  cmp     byte ptr [rbx+40h], 0
0x140012f37  jz      short loc_140012F47
0x140012f39  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140012f3d  lea     rcx, [rsp+0E8h+var_C8]; this
0x140012f42  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140012f47  cmp     byte ptr [rbx+80h], 0
0x140012f4e  jz      short loc_140012F5E
0x140012f50  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140012f54  lea     rcx, [rsp+0E8h+var_88]; this
0x140012f59  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140012f5e  cmp     byte ptr [rbx+0C0h], 0
0x140012f65  jz      short loc_140012F7B
0x140012f67  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140012f6e  lea     rcx, [rsp+0E8h+var_48]; this
0x140012f76  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140012f7b  lea     rcx, [rsp+0E8h+var_C8]; this
0x140012f80  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140012f85  lea     rcx, [rsp+0E8h+var_C8]; this
0x140012f8a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140012f8f  mov     rsi, [rbx+108h]
0x140012f96  mov     qword ptr [rbx+108h], 0
0x140012fa1  test    rsi, rsi
0x140012fa4  jz      short loc_140012FBA
0x140012fa6  call    cs:__imp_GetProcessHeap
0x140012fac  mov     r8, rsi; lpMem
0x140012faf  xor     edx, edx; dwFlags
0x140012fb1  mov     rcx, rax; hHeap
0x140012fb4  call    cs:__imp_HeapFree
0x140012fba  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140012fc1  call    cs:__imp_DeleteCriticalSection
0x140012fc7  lea     rcx, [rbx+8]; this
0x140012fcb  lea     r11, [rsp+0E8h+var_8]
0x140012fd3  mov     rbx, [r11+10h]
0x140012fd7  mov     rsi, [r11+18h]
0x140012fdb  mov     rsp, r11
0x140012fde  pop     rdi
0x140012fdf  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
