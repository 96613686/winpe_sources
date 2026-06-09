# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x140003694`
- end: `0x140003776`
- name: `??1FeatureStateData@details_abi@wil@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400074a8`

## callees

- `0x1400033cc`
- `0x140003694`
- `0x140003b90`
- `0x14000645c`
- `0x140008548`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000373a`
- `KERNEL32!HeapFree` at `0x14000373a`
- `KERNEL32!GetProcessHeap` at `0x140003726`
- `KERNEL32!GetProcessHeap` at `0x140003726`
- `KERNEL32!DeleteCriticalSection` at `0x14000374d`
- `KERNEL32!DeleteCriticalSection` at `0x14000374d`

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
0x140003694  mov     [rsp+arg_0], rbx
0x140003699  mov     [rsp+arg_8], rsi
0x14000369e  push    rdi
0x14000369f  sub     rsp, 0E0h
0x1400036a6  mov     rbx, rcx
0x1400036a9  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400036ae  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1400036b3  cmp     byte ptr [rbx+40h], 0
0x1400036b7  jz      short loc_1400036C7
0x1400036b9  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x1400036bd  lea     rcx, [rsp+0E8h+var_C8]; this
0x1400036c2  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1400036c7  cmp     byte ptr [rbx+80h], 0
0x1400036ce  jz      short loc_1400036DE
0x1400036d0  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x1400036d4  lea     rcx, [rsp+0E8h+var_88]; this
0x1400036d9  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1400036de  cmp     byte ptr [rbx+0C0h], 0
0x1400036e5  jz      short loc_1400036FB
0x1400036e7  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x1400036ee  lea     rcx, [rsp+0E8h+var_48]; this
0x1400036f6  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1400036fb  lea     rcx, [rsp+0E8h+var_C8]; this
0x140003700  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140003705  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000370a  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000370f  mov     rsi, [rbx+108h]
0x140003716  mov     qword ptr [rbx+108h], 0
0x140003721  test    rsi, rsi
0x140003724  jz      short loc_140003746
0x140003726  call    cs:__imp_GetProcessHeap
0x14000372d  nop     dword ptr [rax+rax+00h]
0x140003732  mov     rcx, rax; hHeap
0x140003735  mov     r8, rsi; lpMem
0x140003738  xor     edx, edx; dwFlags
0x14000373a  call    cs:__imp_HeapFree
0x140003741  nop     dword ptr [rax+rax+00h]
0x140003746  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x14000374d  call    cs:__imp_DeleteCriticalSection
0x140003754  nop     dword ptr [rax+rax+00h]
0x140003759  lea     rcx, [rbx+8]; this
0x14000375d  lea     r11, [rsp+0E8h+var_8]
0x140003765  mov     rbx, [r11+10h]
0x140003769  mov     rsi, [r11+18h]
0x14000376d  mov     rsp, r11
0x140003770  pop     rdi
0x140003771  jmp     ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
```
