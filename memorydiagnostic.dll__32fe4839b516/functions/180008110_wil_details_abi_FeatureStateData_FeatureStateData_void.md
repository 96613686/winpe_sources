# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180008110`
- end: `0x1800081ef`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `223`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180010918`

## callees

- `0x1800072e8`
- `0x180008110`
- `0x1800086d8`
- `0x18000f86c`
- `0x180014454`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000819f`
- `KERNEL32!GetProcessHeap` at `0x18000819f`
- `KERNEL32!DeleteCriticalSection` at `0x1800081c6`
- `KERNEL32!DeleteCriticalSection` at `0x1800081c6`
- `KERNEL32!HeapFree` at `0x1800081b3`
- `KERNEL32!HeapFree` at `0x1800081b3`

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
0x180008110  mov     [rsp+arg_0], rbx
0x180008115  mov     [rsp+arg_8], rsi
0x18000811a  push    rdi
0x18000811b  sub     rsp, 0E0h
0x180008122  mov     rbx, rcx
0x180008125  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000812a  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000812f  cmp     byte ptr [rbx+40h], 0
0x180008133  jz      short loc_180008143
0x180008135  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180008139  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000813e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008143  cmp     byte ptr [rbx+80h], 0
0x18000814a  jz      short loc_18000815A
0x18000814c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180008150  lea     rcx, [rsp+0E8h+var_88]; this
0x180008155  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000815a  cmp     byte ptr [rbx+0C0h], 0
0x180008161  jz      short loc_180008177
0x180008163  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000816a  lea     rcx, [rsp+0E8h+var_48]; this
0x180008172  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008177  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000817c  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180008181  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008186  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000818b  mov     rsi, [rbx+108h]
0x180008192  and     qword ptr [rbx+108h], 0
0x18000819a  test    rsi, rsi
0x18000819d  jz      short loc_1800081BF
0x18000819f  call    cs:__imp_GetProcessHeap
0x1800081a6  nop     dword ptr [rax+rax+00h]
0x1800081ab  mov     rcx, rax; hHeap
0x1800081ae  mov     r8, rsi; lpMem
0x1800081b1  xor     edx, edx; dwFlags
0x1800081b3  call    cs:__imp_HeapFree
0x1800081ba  nop     dword ptr [rax+rax+00h]
0x1800081bf  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800081c6  call    cs:__imp_DeleteCriticalSection
0x1800081cd  nop     dword ptr [rax+rax+00h]
0x1800081d2  lea     rcx, [rbx+8]; this
0x1800081d6  lea     r11, [rsp+0E8h+var_8]
0x1800081de  mov     rbx, [r11+10h]
0x1800081e2  mov     rsi, [r11+18h]
0x1800081e6  mov     rsp, r11
0x1800081e9  pop     rdi
0x1800081ea  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
