# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1800032d8`
- end: `0x1800033ba`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006a90`

## callees

- `0x1800031a4`
- `0x1800032d8`
- `0x18000368c`
- `0x180005c48`
- `0x180007524`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000336a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000336a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000337e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000337e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003391`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003391`

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
0x1800032d8  mov     [rsp+arg_0], rbx
0x1800032dd  mov     [rsp+arg_8], rsi
0x1800032e2  push    rdi
0x1800032e3  sub     rsp, 0E0h
0x1800032ea  mov     rbx, rcx
0x1800032ed  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800032f2  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800032f7  cmp     byte ptr [rbx+40h], 0
0x1800032fb  jz      short loc_18000330B
0x1800032fd  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180003301  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003306  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000330b  cmp     byte ptr [rbx+80h], 0
0x180003312  jz      short loc_180003322
0x180003314  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180003318  lea     rcx, [rsp+0E8h+var_88]; this
0x18000331d  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003322  cmp     byte ptr [rbx+0C0h], 0
0x180003329  jz      short loc_18000333F
0x18000332b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180003332  lea     rcx, [rsp+0E8h+var_48]; this
0x18000333a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000333f  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003344  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003349  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000334e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180003353  mov     rsi, [rbx+108h]
0x18000335a  mov     qword ptr [rbx+108h], 0
0x180003365  test    rsi, rsi
0x180003368  jz      short loc_18000338A
0x18000336a  call    cs:__imp_GetProcessHeap
0x180003371  nop     dword ptr [rax+rax+00h]
0x180003376  mov     r8, rsi; lpMem
0x180003379  xor     edx, edx; dwFlags
0x18000337b  mov     rcx, rax; hHeap
0x18000337e  call    cs:__imp_HeapFree
0x180003385  nop     dword ptr [rax+rax+00h]
0x18000338a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180003391  call    cs:__imp_DeleteCriticalSection
0x180003398  nop     dword ptr [rax+rax+00h]
0x18000339d  lea     rcx, [rbx+8]; this
0x1800033a1  lea     r11, [rsp+0E8h+var_8]
0x1800033a9  mov     rbx, [r11+10h]
0x1800033ad  mov     rsi, [r11+18h]
0x1800033b1  mov     rsp, r11
0x1800033b4  pop     rdi
0x1800033b5  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
