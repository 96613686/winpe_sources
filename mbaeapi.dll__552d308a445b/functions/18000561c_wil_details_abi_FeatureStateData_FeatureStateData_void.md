# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18000561c`
- end: `0x1800056ec`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180005300`

## callees

- `0x180005134`
- `0x18000561c`
- `0x180005a90`
- `0x180008124`
- `0x18000a368`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800056c9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800056c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800056bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800056bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18000561c  mov     [rsp+arg_0], rbx
0x180005621  mov     [rsp+arg_8], rsi
0x180005626  push    rdi
0x180005627  sub     rsp, 0E0h
0x18000562e  mov     rbx, rcx
0x180005631  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005636  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000563b  cmp     byte ptr [rbx+40h], 0
0x18000563f  jz      short loc_18000564F
0x180005641  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180005645  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000564a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000564f  cmp     byte ptr [rbx+80h], 0
0x180005656  jz      short loc_180005666
0x180005658  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000565c  lea     rcx, [rsp+0E8h+var_88]; this
0x180005661  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005666  cmp     byte ptr [rbx+0C0h], 0
0x18000566d  jz      short loc_180005683
0x18000566f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180005676  lea     rcx, [rsp+0E8h+var_48]; this
0x18000567e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180005683  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005688  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000568d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180005692  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180005697  mov     rsi, [rbx+108h]
0x18000569e  mov     qword ptr [rbx+108h], 0
0x1800056a9  test    rsi, rsi
0x1800056ac  jz      short loc_1800056C2
0x1800056ae  call    cs:__imp_GetProcessHeap
0x1800056b4  mov     rcx, rax; hHeap
0x1800056b7  mov     r8, rsi; lpMem
0x1800056ba  xor     edx, edx; dwFlags
0x1800056bc  call    cs:__imp_HeapFree
0x1800056c2  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800056c9  call    cs:__imp_DeleteCriticalSection
0x1800056cf  lea     rcx, [rbx+8]; this
0x1800056d3  lea     r11, [rsp+0E8h+var_8]
0x1800056db  mov     rbx, [r11+10h]
0x1800056df  mov     rsi, [r11+18h]
0x1800056e3  mov     rsp, r11
0x1800056e6  pop     rdi
0x1800056e7  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
