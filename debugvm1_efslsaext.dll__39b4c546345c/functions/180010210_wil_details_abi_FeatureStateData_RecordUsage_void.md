# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x180010210`
- end: `0x18001029d`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c8e0`
- `0x180010090`
- `0x1800111d0`

## callees

- `0x18000c968`
- `0x18000cdf0`
- `0x18000ff84`
- `0x180010210`
- `0x180011008`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010229`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010229`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001027a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001027a`

## pseudocode

```c
void __fastcall wil::details_abi::FeatureStateData::RecordUsage(PSRWLOCK SRWLock)
{
  _BYTE v2[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v3[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v4[72]; // [rsp+A0h] [rbp-48h] BYREF

  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v2);
  AcquireSRWLockExclusive(SRWLock);
  if ( LOBYTE(SRWLock[8].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v2,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[1]);
  if ( LOBYTE(SRWLock[16].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v3,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[9]);
  if ( LOBYTE(SRWLock[24].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v4,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[17]);
  ReleaseSRWLockExclusive(SRWLock);
  wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v2);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v2);
}

```

## disassembly

```asm
0x180010210  push    rbx
0x180010212  sub     rsp, 0E0h
0x180010219  mov     rbx, rcx
0x18001021c  lea     rcx, [rsp+0E8h+var_C8]; this
0x180010221  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180010226  mov     rcx, rbx; SRWLock
0x180010229  call    cs:__imp_AcquireSRWLockExclusive
0x18001022f  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180010233  cmp     byte ptr [rdx+38h], 0
0x180010237  jz      short loc_180010243
0x180010239  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001023e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180010243  cmp     byte ptr [rbx+80h], 0
0x18001024a  jz      short loc_18001025A
0x18001024c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180010250  lea     rcx, [rsp+0E8h+var_88]; this
0x180010255  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18001025a  cmp     byte ptr [rbx+0C0h], 0
0x180010261  jz      short loc_180010277
0x180010263  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18001026a  lea     rcx, [rsp+0E8h+var_48]; this
0x180010272  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180010277  mov     rcx, rbx; SRWLock
0x18001027a  call    cs:__imp_ReleaseSRWLockExclusive
0x180010280  lea     rcx, [rsp+0E8h+var_C8]; this
0x180010285  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18001028a  lea     rcx, [rsp+0E8h+var_C8]; this
0x18001028f  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180010294  add     rsp, 0E0h
0x18001029b  pop     rbx
0x18001029c  retn
```
