# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1400052b4`
- end: `0x140005384`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140004f50`

## callees

- `0x140004bdc`
- `0x1400052b4`
- `0x1400058cc`
- `0x140009494`
- `0x14000bf2c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140005346`
- `KERNEL32!GetProcessHeap` at `0x140005346`
- `KERNEL32!HeapFree` at `0x140005354`
- `KERNEL32!HeapFree` at `0x140005354`
- `KERNEL32!DeleteCriticalSection` at `0x140005361`
- `KERNEL32!DeleteCriticalSection` at `0x140005361`

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
0x1400052b4  mov     [rsp+arg_0], rbx
0x1400052b9  mov     [rsp+arg_8], rsi
0x1400052be  push    rdi
0x1400052bf  sub     rsp, 0E0h
0x1400052c6  mov     rbx, rcx
0x1400052c9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400052ce  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1400052d3  cmp     byte ptr [rbx+40h], 0
0x1400052d7  jz      short loc_1400052E7
0x1400052d9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1400052dd  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400052e2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1400052e7  cmp     byte ptr [rbx+80h], 0
0x1400052ee  jz      short loc_1400052FE
0x1400052f0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1400052f4  lea     rcx, [rsp+0E8h+var_88]; this
0x1400052f9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1400052fe  cmp     byte ptr [rbx+0C0h], 0
0x140005305  jz      short loc_14000531B
0x140005307  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x14000530e  lea     rcx, [rsp+0E8h+var_48]; this
0x140005316  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000531b  lea     rcx, [rsp+0E8h+var_C8]; this
0x140005320  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140005325  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000532a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000532f  mov     rsi, [rbx+108h]
0x140005336  mov     qword ptr [rbx+108h], 0
0x140005341  test    rsi, rsi
0x140005344  jz      short loc_14000535A
0x140005346  call    cs:__imp_GetProcessHeap
0x14000534c  mov     rcx, rax; hHeap
0x14000534f  mov     r8, rsi; lpMem
0x140005352  xor     edx, edx; dwFlags
0x140005354  call    cs:__imp_HeapFree
0x14000535a  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x140005361  call    cs:__imp_DeleteCriticalSection
0x140005367  lea     rcx, [rbx+8]; this
0x14000536b  lea     r11, [rsp+0E8h+var_8]
0x140005373  mov     rbx, [r11+10h]
0x140005377  mov     rsi, [r11+18h]
0x14000537b  mov     rsp, r11
0x14000537e  pop     rdi
0x14000537f  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
