# DloadAcquireSectionWriteAccess

- ea: `0x18000a308`
- end: `0x18000a359`
- name: `DloadAcquireSectionWriteAccess`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800089e0`

## callees

- `0x18000a308`
- `0x180029bb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a34e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a34e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a31f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a31f`

## pseudocode

```c
void DloadAcquireSectionWriteAccess()
{
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( ++DloadSectionLockCount == 1 )
    DloadProtectSection(4u, &DloadSectionOldProtection);
  ReleaseSRWLockExclusive(&DloadSrwLock);
}

```

## disassembly

```asm
0x18000a308  sub     rsp, 28h
0x18000a30c  test    cs:dword_18002CA40, 1000h
0x18000a316  jz      short loc_18000A354
0x18000a318  lea     rcx, DloadSrwLock; SRWLock
0x18000a31f  call    cs:__imp_AcquireSRWLockExclusive
0x18000a325  mov     eax, cs:DloadSectionLockCount
0x18000a32b  inc     eax
0x18000a32d  mov     cs:DloadSectionLockCount, eax
0x18000a333  cmp     eax, 1
0x18000a336  jnz     short loc_18000A347
0x18000a338  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x18000a33f  lea     ecx, [rax+3]; flNewProtect
0x18000a342  call    DloadProtectSection
0x18000a347  lea     rcx, DloadSrwLock; SRWLock
0x18000a34e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a354  add     rsp, 28h
0x18000a358  retn
```
