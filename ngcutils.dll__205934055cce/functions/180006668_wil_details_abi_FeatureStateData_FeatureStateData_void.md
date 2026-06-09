# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180006668`
- end: `0x180006738`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800063f0`

## callees

- `0x180006224`
- `0x180006668`
- `0x180006adc`
- `0x180009230`
- `0x18000b434`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006715`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006715`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006708`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006708`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066fa`

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
0x180006668  mov     [rsp+arg_0], rbx
0x18000666d  mov     [rsp+arg_8], rsi
0x180006672  push    rdi
0x180006673  sub     rsp, 0E0h
0x18000667a  mov     rbx, rcx
0x18000667d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006682  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180006687  cmp     byte ptr [rbx+40h], 0
0x18000668b  jz      short loc_18000669B
0x18000668d  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180006691  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006696  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000669b  cmp     byte ptr [rbx+80h], 0
0x1800066a2  jz      short loc_1800066B2
0x1800066a4  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1800066a8  lea     rcx, [rsp+0E8h+var_88]; this
0x1800066ad  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800066b2  cmp     byte ptr [rbx+0C0h], 0
0x1800066b9  jz      short loc_1800066CF
0x1800066bb  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800066c2  lea     rcx, [rsp+0E8h+var_48]; this
0x1800066ca  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800066cf  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800066d4  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800066d9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800066de  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800066e3  mov     rsi, [rbx+108h]
0x1800066ea  mov     qword ptr [rbx+108h], 0
0x1800066f5  test    rsi, rsi
0x1800066f8  jz      short loc_18000670E
0x1800066fa  call    cs:__imp_GetProcessHeap
0x180006700  mov     rcx, rax; hHeap
0x180006703  mov     r8, rsi; lpMem
0x180006706  xor     edx, edx; dwFlags
0x180006708  call    cs:__imp_HeapFree
0x18000670e  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180006715  call    cs:__imp_DeleteCriticalSection
0x18000671b  lea     rcx, [rbx+8]; this
0x18000671f  lea     r11, [rsp+0E8h+var_8]
0x180006727  mov     rbx, [r11+10h]
0x18000672b  mov     rsi, [r11+18h]
0x18000672f  mov     rsp, r11
0x180006732  pop     rdi
0x180006733  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
