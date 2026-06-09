# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x180003208`
- end: `0x1800032d8`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `208`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002f24`

## callees

- `0x180002c40`
- `0x180003208`
- `0x180003558`
- `0x180007a98`
- `0x18000a308`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800032b5`
- `KERNEL32!DeleteCriticalSection` at `0x1800032b5`
- `KERNEL32!GetProcessHeap` at `0x18000329a`
- `KERNEL32!GetProcessHeap` at `0x18000329a`
- `KERNEL32!HeapFree` at `0x1800032a8`
- `KERNEL32!HeapFree` at `0x1800032a8`

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
0x180003208  mov     [rsp+arg_0], rbx
0x18000320d  mov     [rsp+arg_8], rsi
0x180003212  push    rdi
0x180003213  sub     rsp, 0E0h
0x18000321a  mov     rbx, rcx
0x18000321d  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003222  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180003227  cmp     byte ptr [rbx+40h], 0
0x18000322b  jz      short loc_18000323B
0x18000322d  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180003231  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003236  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000323b  cmp     byte ptr [rbx+80h], 0
0x180003242  jz      short loc_180003252
0x180003244  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180003248  lea     rcx, [rsp+0E8h+var_88]; this
0x18000324d  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180003252  cmp     byte ptr [rbx+0C0h], 0
0x180003259  jz      short loc_18000326F
0x18000325b  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180003262  lea     rcx, [rsp+0E8h+var_48]; this
0x18000326a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000326f  lea     rcx, [rsp+0E8h+var_C8]; this
0x180003274  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180003279  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000327e  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180003283  mov     rsi, [rbx+108h]
0x18000328a  mov     qword ptr [rbx+108h], 0
0x180003295  test    rsi, rsi
0x180003298  jz      short loc_1800032AE
0x18000329a  call    cs:__imp_GetProcessHeap
0x1800032a0  mov     r8, rsi; lpMem
0x1800032a3  xor     edx, edx; dwFlags
0x1800032a5  mov     rcx, rax; hHeap
0x1800032a8  call    cs:__imp_HeapFree
0x1800032ae  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800032b5  call    cs:__imp_DeleteCriticalSection
0x1800032bb  lea     rcx, [rbx+8]; this
0x1800032bf  lea     r11, [rsp+0E8h+var_8]
0x1800032c7  mov     rbx, [r11+10h]
0x1800032cb  mov     rsi, [r11+18h]
0x1800032cf  mov     rsp, r11
0x1800032d2  pop     rdi
0x1800032d3  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
