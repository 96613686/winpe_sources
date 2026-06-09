# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18000a224`
- end: `0x18000a306`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800116a4`

## callees

- `0x180009c44`
- `0x18000a224`
- `0x18000a64c`
- `0x180010614`
- `0x180013360`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2b6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a2dd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a2dd`

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
0x18000a224  mov     [rsp+arg_0], rbx
0x18000a229  mov     [rsp+arg_8], rsi
0x18000a22e  push    rdi
0x18000a22f  sub     rsp, 0E0h
0x18000a236  mov     rbx, rcx
0x18000a239  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000a23e  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000a243  cmp     byte ptr [rbx+40h], 0
0x18000a247  jz      short loc_18000A257
0x18000a249  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000a24d  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000a252  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a257  cmp     byte ptr [rbx+80h], 0
0x18000a25e  jz      short loc_18000A26E
0x18000a260  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000a264  lea     rcx, [rsp+0E8h+var_88]; this
0x18000a269  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a26e  cmp     byte ptr [rbx+0C0h], 0
0x18000a275  jz      short loc_18000A28B
0x18000a277  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000a27e  lea     rcx, [rsp+0E8h+var_48]; this
0x18000a286  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000a28b  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000a290  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000a295  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000a29a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000a29f  mov     rsi, [rbx+108h]
0x18000a2a6  mov     qword ptr [rbx+108h], 0
0x18000a2b1  test    rsi, rsi
0x18000a2b4  jz      short loc_18000A2D6
0x18000a2b6  call    cs:__imp_GetProcessHeap
0x18000a2bd  nop     dword ptr [rax+rax+00h]
0x18000a2c2  mov     rcx, rax; hHeap
0x18000a2c5  mov     r8, rsi; lpMem
0x18000a2c8  xor     edx, edx; dwFlags
0x18000a2ca  call    cs:__imp_HeapFree
0x18000a2d1  nop     dword ptr [rax+rax+00h]
0x18000a2d6  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18000a2dd  call    cs:__imp_DeleteCriticalSection
0x18000a2e4  nop     dword ptr [rax+rax+00h]
0x18000a2e9  lea     rcx, [rbx+8]; this
0x18000a2ed  lea     r11, [rsp+0E8h+var_8]
0x18000a2f5  mov     rbx, [r11+10h]
0x18000a2f9  mov     rsi, [r11+18h]
0x18000a2fd  mov     rsp, r11
0x18000a300  pop     rdi
0x18000a301  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
