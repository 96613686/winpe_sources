# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180003c84`
- end: `0x180003d54`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180003b90`

## callees

- `0x1800039fc`
- `0x180003c84`
- `0x180003fd4`
- `0x18000651c`
- `0x180007ba0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003d31`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003d31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003d16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d24`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003d24`

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
0x180003c84  mov     [rsp+arg_0], rbx
0x180003c89  mov     [rsp+arg_8], rsi
0x180003c8e  push    rdi
0x180003c8f  sub     rsp, 0E0h
0x180003c96  mov     rbx, rcx
0x180003c99  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003c9e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003ca3  cmp     byte ptr [rbx+40h], 0
0x180003ca7  jz      short loc_180003CB7
0x180003ca9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180003cad  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003cb2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003cb7  cmp     byte ptr [rbx+80h], 0
0x180003cbe  jz      short loc_180003CCE
0x180003cc0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180003cc4  lea     rcx, [rsp+0E8h+var_88]; this
0x180003cc9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003cce  cmp     byte ptr [rbx+0C0h], 0
0x180003cd5  jz      short loc_180003CEB
0x180003cd7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180003cde  lea     rcx, [rsp+0E8h+var_48]; this
0x180003ce6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003ceb  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003cf0  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003cf5  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003cfa  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180003cff  mov     rsi, [rbx+108h]
0x180003d06  mov     qword ptr [rbx+108h], 0
0x180003d11  test    rsi, rsi
0x180003d14  jz      short loc_180003D2A
0x180003d16  call    cs:__imp_GetProcessHeap
0x180003d1c  mov     r8, rsi; lpMem
0x180003d1f  xor     edx, edx; dwFlags
0x180003d21  mov     rcx, rax; hHeap
0x180003d24  call    cs:__imp_HeapFree
0x180003d2a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180003d31  call    cs:__imp_DeleteCriticalSection
0x180003d37  lea     rcx, [rbx+8]; this
0x180003d3b  lea     r11, [rsp+0E8h+var_8]
0x180003d43  mov     rbx, [r11+10h]
0x180003d47  mov     rsi, [r11+18h]
0x180003d4b  mov     rsp, r11
0x180003d4e  pop     rdi
0x180003d4f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
