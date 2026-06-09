# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x1800088e0`
- end: `0x18000896d`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180003ac0`
- `0x1800086f4`
- `0x18000a030`

## callees

- `0x1800044c0`
- `0x180004be4`
- `0x1800083f8`
- `0x1800088e0`
- `0x180009bf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800088f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800088f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000894a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000894a`

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
0x1800088e0  push    rbx
0x1800088e2  sub     rsp, 0E0h
0x1800088e9  mov     rbx, rcx
0x1800088ec  lea     rcx, [rsp+0E8h+var_C8]; this
0x1800088f1  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1800088f6  mov     rcx, rbx; SRWLock
0x1800088f9  call    cs:__imp_AcquireSRWLockExclusive
0x1800088ff  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x180008903  cmp     byte ptr [rdx+38h], 0
0x180008907  jz      short loc_180008913
0x180008909  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000890e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008913  cmp     byte ptr [rbx+80h], 0
0x18000891a  jz      short loc_18000892A
0x18000891c  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x180008920  lea     rcx, [rsp+0E8h+var_88]; this
0x180008925  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x18000892a  cmp     byte ptr [rbx+0C0h], 0
0x180008931  jz      short loc_180008947
0x180008933  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x18000893a  lea     rcx, [rsp+0E8h+var_48]; this
0x180008942  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x180008947  mov     rcx, rbx; SRWLock
0x18000894a  call    cs:__imp_ReleaseSRWLockExclusive
0x180008950  lea     rcx, [rsp+0E8h+var_C8]; this
0x180008955  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x18000895a  lea     rcx, [rsp+0E8h+var_C8]; this
0x18000895f  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x180008964  add     rsp, 0E0h
0x18000896b  pop     rbx
0x18000896c  retn
```
