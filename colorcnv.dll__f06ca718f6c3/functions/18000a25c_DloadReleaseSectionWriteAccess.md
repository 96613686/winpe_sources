# DloadReleaseSectionWriteAccess

- ea: `0x18000a25c`
- end: `0x18000a2ac`
- name: `DloadReleaseSectionWriteAccess`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800089e0`

## callees

- `0x18000a25c`
- `0x180029bb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a2a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a2a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a27b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a27b`

## pseudocode

```c
void DloadReleaseSectionWriteAccess()
{
  DWORD flOldProtect; // [rsp+30h] [rbp+8h] BYREF

  flOldProtect = 0;
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( !--DloadSectionLockCount )
    DloadProtectSection(DloadSectionOldProtection, &flOldProtect);
  ReleaseSRWLockExclusive(&DloadSrwLock);
}

```

## disassembly

```asm
0x18000a25c  sub     rsp, 28h
0x18000a260  test    cs:dword_18002CA40, 1000h
0x18000a26a  mov     [rsp+28h+flOldProtect], 0
0x18000a272  jz      short loc_18000A2A7
0x18000a274  lea     rcx, DloadSrwLock; SRWLock
0x18000a27b  call    cs:__imp_AcquireSRWLockExclusive
0x18000a281  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18000a288  jnz     short loc_18000A29A
0x18000a28a  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18000a290  lea     rdx, [rsp+28h+flOldProtect]; lpflOldProtect
0x18000a295  call    DloadProtectSection
0x18000a29a  lea     rcx, DloadSrwLock; SRWLock
0x18000a2a1  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a2a7  add     rsp, 28h
0x18000a2ab  retn
```
