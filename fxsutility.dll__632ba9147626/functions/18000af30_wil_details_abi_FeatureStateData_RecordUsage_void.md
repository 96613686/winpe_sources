# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x18000af30`
- end: `0x18000afbf`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `143`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180007450`
- `0x18000ad74`
- `0x18000ca10`

## callees

- `0x180007fa0`
- `0x1800086b8`
- `0x18000ac2c`
- `0x18000af30`
- `0x18000c60c`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000af9b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000af9b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000af4a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000af4a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000af30  push    rbx
0x18000af32  sub     rsp, 0E0h
0x18000af39  mov     rbx, rcx
0x18000af3c  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000af41  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x18000af46  nop
0x18000af47  mov     rcx, rbx; SRWLock
0x18000af4a  call    cs:__imp_AcquireSRWLockExclusive
0x18000af50  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x18000af54  cmp     byte ptr [rdx+38h], 0
0x18000af58  jz      short loc_18000AF64
0x18000af5a  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000af5f  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000af64  cmp     byte ptr [rbx+80h], 0
0x18000af6b  jz      short loc_18000AF7B
0x18000af6d  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x18000af71  lea     rcx, [rsp+0E8h+var_88]; this
0x18000af76  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000af7b  cmp     byte ptr [rbx+0C0h], 0
0x18000af82  jz      short loc_18000AF98
0x18000af84  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000af8b  lea     rcx, [rsp+0E8h+var_48]; this
0x18000af93  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000af98  mov     rcx, rbx; SRWLock
0x18000af9b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000afa1  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000afa6  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000afab  nop
0x18000afac  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000afb1  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x18000afb6  add     rsp, 0E0h
0x18000afbd  pop     rbx
0x18000afbe  retn
```
