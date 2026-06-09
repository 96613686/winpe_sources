# RtlMrdataReleaseSectionWriteAccess

- ea: `0x180026ff8`
- end: `0x180027085`
- name: `RtlMrdataReleaseSectionWriteAccess`
- size: `141`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180013d70`
- `0x180026dac`

## callees

- `0x180026ff8`
- `0x18002708c`
- `0x180027110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027018`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027018`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027079`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027079`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180027063`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180027063`

## pseudocode

```c
void __fastcall RtlMrdataReleaseSectionWriteAccess(__int64 a1)
{
  void *v2; // rax
  SIZE_T dwSize; // [rsp+38h] [rbp+10h] BYREF
  DWORD flOldProtect; // [rsp+40h] [rbp+18h] BYREF

  flOldProtect = 0;
  LODWORD(dwSize) = 0;
  AcquireSRWLockExclusive(&RtlpMrdataProtectionLock);
  if ( !RtlpMrdataSectionLockCount )
  {
    RtlpMrdataUnlock();
    __fastfail(0xEu);
  }
  if ( !--RtlpMrdataSectionLockCount )
  {
    v2 = (void *)RtlpMrdataObtainSection(a1, &dwSize);
    if ( !VirtualProtect(v2, (unsigned int)dwSize, RtlpMrdataSectionOldProtection, &flOldProtect) )
      __fastfail(0x22u);
  }
  ReleaseSRWLockExclusive(&RtlpMrdataProtectionLock);
}

```

## disassembly

```asm
0x180026ff8  push    rbx
0x180026ffa  sub     rsp, 20h
0x180026ffe  mov     rbx, rcx
0x180027001  mov     [rsp+28h+flOldProtect], 0
0x180027009  lea     rcx, RtlpMrdataProtectionLock; SRWLock
0x180027010  mov     dword ptr [rsp+28h+dwSize], 0
0x180027018  call    cs:__imp_AcquireSRWLockExclusive
0x18002701e  mov     rax, cs:RtlpMrdataSectionLockCount
0x180027025  test    rax, rax
0x180027028  jnz     short loc_180027036
0x18002702a  call    RtlpMrdataUnlock
0x18002702f  mov     ecx, 0Eh
0x180027034  int     29h; Win8: RtlFailFast(ecx)
0x180027036  sub     rax, 1
0x18002703a  mov     cs:RtlpMrdataSectionLockCount, rax
0x180027041  jnz     short loc_180027072
0x180027043  lea     rdx, [rsp+28h+dwSize]
0x180027048  mov     rcx, rbx
0x18002704b  call    RtlpMrdataObtainSection
0x180027050  mov     edx, dword ptr [rsp+28h+dwSize]; dwSize
0x180027054  lea     r9, [rsp+28h+flOldProtect]; lpflOldProtect
0x180027059  mov     r8d, cs:RtlpMrdataSectionOldProtection; flNewProtect
0x180027060  mov     rcx, rax; lpAddress
0x180027063  call    cs:__imp_VirtualProtect
0x180027069  test    eax, eax
0x18002706b  jnz     short loc_180027072
0x18002706d  lea     ecx, [rax+22h]
0x180027070  int     29h; Win8: RtlFailFast(ecx)
0x180027072  lea     rcx, RtlpMrdataProtectionLock; SRWLock
0x180027079  call    cs:__imp_ReleaseSRWLockExclusive
0x18002707f  add     rsp, 20h
0x180027083  pop     rbx
0x180027084  retn
```
