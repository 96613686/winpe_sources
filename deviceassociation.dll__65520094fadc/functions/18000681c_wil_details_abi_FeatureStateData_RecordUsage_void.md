# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x18000681c`
- end: `0x1800068a9`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180003090`
- `0x180006664`
- `0x180007f60`

## callees

- `0x1800039fc`
- `0x180003fd4`
- `0x18000651c`
- `0x18000681c`
- `0x180007ba0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006886`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006886`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006835`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006835`

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
0x18000681c  push    rbx
0x18000681e  sub     rsp, 0E0h
0x180006825  mov     rbx, rcx
0x180006828  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000682d  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x180006832  mov     rcx, rbx; SRWLock
0x180006835  call    cs:__imp_AcquireSRWLockExclusive
0x18000683b  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000683f  cmp     byte ptr [rdx+38h], 0
0x180006843  jz      short loc_18000684F
0x180006845  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000684a  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000684f  cmp     byte ptr [rbx+80h], 0
0x180006856  jz      short loc_180006866
0x180006858  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000685c  lea     rcx, [rsp+0E8h+var_88]; this
0x180006861  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006866  cmp     byte ptr [rbx+0C0h], 0
0x18000686d  jz      short loc_180006883
0x18000686f  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x180006876  lea     rcx, [rsp+0E8h+var_48]; this
0x18000687e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180006883  mov     rcx, rbx; SRWLock
0x180006886  call    cs:__imp_ReleaseSRWLockExclusive
0x18000688c  lea     rcx, [rsp+0E8h+var_C8]; this
0x180006891  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x180006896  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000689b  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1800068a0  add     rsp, 0E0h
0x1800068a7  pop     rbx
0x1800068a8  retn
```
