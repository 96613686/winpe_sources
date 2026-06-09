# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180005200`
- end: `0x1800052e2`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009600`

## callees

- `0x180004ed8`
- `0x180005200`
- `0x180005700`
- `0x180008518`
- `0x18000aaac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800052b9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800052b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005292`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005292`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180005200  mov     [rsp+arg_0], rbx
0x180005205  mov     [rsp+arg_8], rsi
0x18000520a  push    rdi
0x18000520b  sub     rsp, 0E0h
0x180005212  mov     rbx, rcx
0x180005215  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000521a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000521f  cmp     byte ptr [rbx+40h], 0
0x180005223  jz      short loc_180005233
0x180005225  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180005229  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000522e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005233  cmp     byte ptr [rbx+80h], 0
0x18000523a  jz      short loc_18000524A
0x18000523c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180005240  lea     rcx, [rsp+0E8h+var_88]; this
0x180005245  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000524a  cmp     byte ptr [rbx+0C0h], 0
0x180005251  jz      short loc_180005267
0x180005253  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000525a  lea     rcx, [rsp+0E8h+var_48]; this
0x180005262  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005267  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000526c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180005271  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005276  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000527b  mov     rsi, [rbx+108h]
0x180005282  mov     qword ptr [rbx+108h], 0
0x18000528d  test    rsi, rsi
0x180005290  jz      short loc_1800052B2
0x180005292  call    cs:__imp_GetProcessHeap
0x180005299  nop     dword ptr [rax+rax+00h]
0x18000529e  mov     rcx, rax; hHeap
0x1800052a1  mov     r8, rsi; lpMem
0x1800052a4  xor     edx, edx; dwFlags
0x1800052a6  call    cs:__imp_HeapFree
0x1800052ad  nop     dword ptr [rax+rax+00h]
0x1800052b2  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800052b9  call    cs:__imp_DeleteCriticalSection
0x1800052c0  nop     dword ptr [rax+rax+00h]
0x1800052c5  lea     rcx, [rbx+8]; this
0x1800052c9  lea     r11, [rsp+0E8h+var_8]
0x1800052d1  mov     rbx, [r11+10h]
0x1800052d5  mov     rsi, [r11+18h]
0x1800052d9  mov     rsp, r11
0x1800052dc  pop     rdi
0x1800052dd  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
