# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180008310`
- end: `0x1800083e0`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800076a4`

## callees

- `0x18000726c`
- `0x180008310`
- `0x180008830`
- `0x18000ef90`
- `0x180013880`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800083a2`
- `KERNEL32!GetProcessHeap` at `0x1800083a2`
- `KERNEL32!DeleteCriticalSection` at `0x1800083bd`
- `KERNEL32!DeleteCriticalSection` at `0x1800083bd`
- `KERNEL32!HeapFree` at `0x1800083b0`
- `KERNEL32!HeapFree` at `0x1800083b0`

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
0x180008310  mov     [rsp+arg_0], rbx
0x180008315  mov     [rsp+arg_8], rsi
0x18000831a  push    rdi
0x18000831b  sub     rsp, 0E0h
0x180008322  mov     rbx, rcx
0x180008325  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000832a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000832f  cmp     byte ptr [rbx+40h], 0
0x180008333  jz      short loc_180008343
0x180008335  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180008339  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000833e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008343  cmp     byte ptr [rbx+80h], 0
0x18000834a  jz      short loc_18000835A
0x18000834c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180008350  lea     rcx, [rsp+0E8h+var_88]; this
0x180008355  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000835a  cmp     byte ptr [rbx+0C0h], 0
0x180008361  jz      short loc_180008377
0x180008363  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000836a  lea     rcx, [rsp+0E8h+var_48]; this
0x180008372  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008377  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000837c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180008381  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008386  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000838b  mov     rsi, [rbx+108h]
0x180008392  mov     qword ptr [rbx+108h], 0
0x18000839d  test    rsi, rsi
0x1800083a0  jz      short loc_1800083B6
0x1800083a2  call    cs:__imp_GetProcessHeap
0x1800083a8  mov     rcx, rax; hHeap
0x1800083ab  mov     r8, rsi; lpMem
0x1800083ae  xor     edx, edx; dwFlags
0x1800083b0  call    cs:__imp_HeapFree
0x1800083b6  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800083bd  call    cs:__imp_DeleteCriticalSection
0x1800083c3  lea     rcx, [rbx+8]; this
0x1800083c7  lea     r11, [rsp+0E8h+var_8]
0x1800083cf  mov     rbx, [r11+10h]
0x1800083d3  mov     rsi, [r11+18h]
0x1800083d7  mov     rsp, r11
0x1800083da  pop     rdi
0x1800083db  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
