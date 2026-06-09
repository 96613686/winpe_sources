# wil::details_abi::FeatureStateData::RecordUsage(void)

- ea: `0x140015aac`
- end: `0x140015b39`
- name: `?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ`
- size: `141`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140012320`
- `0x1400158f4`
- `0x1400171f0`

## callees

- `0x140012c8c`
- `0x140013264`
- `0x1400157ac`
- `0x140015aac`
- `0x140016e30`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x140015b16`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140015b16`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140015ac5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140015ac5`

## pseudocode

```c
void __fastcall wil::details_abi::FeatureStateData::RecordUsage(PSRWLOCK SRWLock)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  const struct wil::details_abi::RawUsageIndex *v4; // r9
  _BYTE v5[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v6[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v7[72]; // [rsp+A0h] [rbp-48h] BYREF

  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v5);
  AcquireSRWLockExclusive(SRWLock);
  if ( LOBYTE(SRWLock[8].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v5,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[1]);
  if ( LOBYTE(SRWLock[16].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v6,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[9]);
  if ( LOBYTE(SRWLock[24].Ptr) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v7,
      (struct wil::details_abi::RawUsageIndex *)&SRWLock[17]);
  ReleaseSRWLockExclusive(SRWLock);
  wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v5, v2, v3, v4);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v5);
}

```

## disassembly

```asm
0x140015aac  push    rbx
0x140015aae  sub     rsp, 0E0h
0x140015ab5  mov     rbx, rcx
0x140015ab8  lea     rcx, [rsp+0E8h+var_C8]; this
0x140015abd  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x140015ac2  mov     rcx, rbx; SRWLock
0x140015ac5  call    cs:__imp_AcquireSRWLockExclusive
0x140015acb  lea     rdx, [rbx+8]; struct wil::details_abi::RawUsageIndex *
0x140015acf  cmp     byte ptr [rdx+38h], 0
0x140015ad3  jz      short loc_140015ADF
0x140015ad5  lea     rcx, [rsp+0E8h+var_C8]; this
0x140015ada  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140015adf  cmp     byte ptr [rbx+80h], 0
0x140015ae6  jz      short loc_140015AF6
0x140015ae8  lea     rdx, [rbx+48h]; struct wil::details_abi::RawUsageIndex *
0x140015aec  lea     rcx, [rsp+0E8h+var_88]; this
0x140015af1  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140015af6  cmp     byte ptr [rbx+0C0h], 0
0x140015afd  jz      short loc_140015B13
0x140015aff  lea     rdx, [rbx+88h]; struct wil::details_abi::RawUsageIndex *
0x140015b06  lea     rcx, [rsp+0E8h+var_48]; this
0x140015b0e  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x140015b13  mov     rcx, rbx; SRWLock
0x140015b16  call    cs:__imp_ReleaseSRWLockExclusive
0x140015b1c  lea     rcx, [rsp+0E8h+var_C8]; this
0x140015b21  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x140015b26  lea     rcx, [rsp+0E8h+var_C8]; this
0x140015b2b  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x140015b30  add     rsp, 0E0h
0x140015b37  pop     rbx
0x140015b38  retn
```
