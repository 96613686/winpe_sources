# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x18000824c`
- end: `0x18000831c`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008134`

## callees

- `0x180007fa0`
- `0x18000824c`
- `0x1800086b8`
- `0x18000ac2c`
- `0x18000c60c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800082ec`
- `KERNEL32!HeapFree` at `0x1800082ec`
- `KERNEL32!GetProcessHeap` at `0x1800082de`
- `KERNEL32!GetProcessHeap` at `0x1800082de`
- `KERNEL32!DeleteCriticalSection` at `0x1800082f9`
- `KERNEL32!DeleteCriticalSection` at `0x1800082f9`

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
0x18000824c  mov     [rsp+arg_0], rbx
0x180008251  mov     [rsp+arg_8], rsi
0x180008256  push    rdi
0x180008257  sub     rsp, 0E0h
0x18000825e  mov     rbx, rcx
0x180008261  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008266  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000826b  cmp     byte ptr [rbx+40h], 0
0x18000826f  jz      short loc_18000827F
0x180008271  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180008275  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000827a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000827f  cmp     byte ptr [rbx+80h], 0
0x180008286  jz      short loc_180008296
0x180008288  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000828c  lea     rcx, [rsp+0E8h+var_88]; this
0x180008291  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008296  cmp     byte ptr [rbx+0C0h], 0
0x18000829d  jz      short loc_1800082B3
0x18000829f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1800082a6  lea     rcx, [rsp+0E8h+var_48]; this
0x1800082ae  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1800082b3  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800082b8  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1800082bd  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800082c2  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800082c7  mov     rsi, [rbx+108h]
0x1800082ce  mov     qword ptr [rbx+108h], 0
0x1800082d9  test    rsi, rsi
0x1800082dc  jz      short loc_1800082F2
0x1800082de  call    cs:__imp_GetProcessHeap
0x1800082e4  mov     rcx, rax; hHeap
0x1800082e7  mov     r8, rsi; lpMem
0x1800082ea  xor     edx, edx; dwFlags
0x1800082ec  call    cs:__imp_HeapFree
0x1800082f2  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800082f9  call    cs:__imp_DeleteCriticalSection
0x1800082ff  lea     rcx, [rbx+8]; this
0x180008303  lea     r11, [rsp+0E8h+var_8]
0x18000830b  mov     rbx, [r11+10h]
0x18000830f  mov     rsi, [r11+18h]
0x180008313  mov     rsp, r11
0x180008316  pop     rdi
0x180008317  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
