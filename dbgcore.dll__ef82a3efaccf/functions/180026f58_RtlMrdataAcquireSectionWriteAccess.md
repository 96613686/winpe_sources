# RtlMrdataAcquireSectionWriteAccess

- ea: `0x180026f58`
- end: `0x180026fef`
- name: `RtlMrdataAcquireSectionWriteAccess`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013d70`
- `0x180026dac`

## callees

- `0x180026f58`
- `0x18002708c`
- `0x180027110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026f71`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026f71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026fe1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026fe1`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180026fc7`
- `api-ms-win-core-memory-l1-1-0!VirtualProtect` at `0x180026fc7`

## pseudocode

```c
char __fastcall RtlMrdataAcquireSectionWriteAccess(__int64 a1)
{
  char v1; // bl
  void *v2; // rax
  unsigned int dwSize; // [rsp+30h] [rbp+8h] BYREF
  int dwSize_4; // [rsp+34h] [rbp+Ch]

  dwSize_4 = HIDWORD(a1);
  dwSize = 0;
  AcquireSRWLockExclusive(&RtlpMrdataProtectionLock);
  if ( RtlpMrdataSectionLockCount == -1 )
  {
    RtlpMrdataUnlock();
    __fastfail(0xEu);
  }
  v1 = 1;
  if ( ++RtlpMrdataSectionLockCount == 1 )
  {
    v2 = (void *)RtlpMrdataObtainSection(&g_RunOnceMrdataCommitObtained, &dwSize);
    if ( !VirtualProtect(v2, dwSize, 4u, &RtlpMrdataSectionOldProtection) )
    {
      --RtlpMrdataSectionLockCount;
      v1 = 0;
    }
  }
  ReleaseSRWLockExclusive(&RtlpMrdataProtectionLock);
  return v1;
}

```

## disassembly

```asm
0x180026f58  mov     [rsp+dwSize], rcx
0x180026f5d  push    rbx
0x180026f5e  sub     rsp, 20h
0x180026f62  lea     rcx, RtlpMrdataProtectionLock; SRWLock
0x180026f69  mov     dword ptr [rsp+28h+dwSize], 0
0x180026f71  call    cs:__imp_AcquireSRWLockExclusive
0x180026f77  mov     rax, cs:RtlpMrdataSectionLockCount
0x180026f7e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026f82  jnz     short loc_180026F90
0x180026f84  call    RtlpMrdataUnlock
0x180026f89  mov     ecx, 0Eh
0x180026f8e  int     29h; Win8: RtlFailFast(ecx)
0x180026f90  mov     ebx, 1
0x180026f95  add     rax, rbx
0x180026f98  mov     cs:RtlpMrdataSectionLockCount, rax
0x180026f9f  cmp     rax, rbx
0x180026fa2  jnz     short loc_180026FDA
0x180026fa4  lea     rdx, [rsp+28h+dwSize]
0x180026fa9  lea     rcx, ?g_RunOnceMrdataCommitObtained@@3T_RTL_RUN_ONCE@@C; _RTL_RUN_ONCE volatile g_RunOnceMrdataCommitObtained
0x180026fb0  call    RtlpMrdataObtainSection
0x180026fb5  mov     edx, dword ptr [rsp+28h+dwSize]; dwSize
0x180026fb9  lea     r9, RtlpMrdataSectionOldProtection; lpflOldProtect
0x180026fc0  lea     r8d, [rbx+3]; flNewProtect
0x180026fc4  mov     rcx, rax; lpAddress
0x180026fc7  call    cs:__imp_VirtualProtect
0x180026fcd  test    eax, eax
0x180026fcf  jnz     short loc_180026FDA
0x180026fd1  sub     cs:RtlpMrdataSectionLockCount, rbx
0x180026fd8  xor     bl, bl
0x180026fda  lea     rcx, RtlpMrdataProtectionLock; SRWLock
0x180026fe1  call    cs:__imp_ReleaseSRWLockExclusive
0x180026fe7  mov     al, bl
0x180026fe9  add     rsp, 20h
0x180026fed  pop     rbx
0x180026fee  retn
```
