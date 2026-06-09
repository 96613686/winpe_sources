# SharingTokenDatabase::CheckAndSetRecoveryState(long)

- ea: `0x180016340`
- end: `0x180016382`
- name: `?CheckAndSetRecoveryState@SharingTokenDatabase@@AEAAXJ@Z`
- size: `66`
- prototype: `void __fastcall(RTL_SRWLOCK *this, int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800163ec`
- `0x18001669c`
- `0x18001686c`
- `0x180017140`
- `0x180017318`
- `0x180017518`
- `0x180017c90`

## callees

- `0x180016340`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016371`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016371`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001635c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001635c`

## pseudocode

```c
void __fastcall SharingTokenDatabase::CheckAndSetRecoveryState(RTL_SRWLOCK *this, int a2)
{
  RTL_SRWLOCK *v2; // rbx

  if ( a2 == -1055719420 )
  {
    v2 = this + 13;
    AcquireSRWLockExclusive(this + 13);
    LODWORD(this[5].Ptr) = 2;
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
  }
}

```

## disassembly

```asm
0x180016340  cmp     edx, 0C1130004h
0x180016346  jnz     short locret_180016381
0x180016348  mov     [rsp+arg_0], rbx
0x18001634d  push    rdi
0x18001634e  sub     rsp, 20h
0x180016352  lea     rbx, [rcx+68h]
0x180016356  mov     rdi, rcx
0x180016359  mov     rcx, rbx; SRWLock
0x18001635c  call    cs:__imp_AcquireSRWLockExclusive
0x180016362  mov     dword ptr [rdi+28h], 2
0x180016369  test    rbx, rbx
0x18001636c  jz      short loc_180016377
0x18001636e  mov     rcx, rbx; SRWLock
0x180016371  call    cs:__imp_ReleaseSRWLockExclusive
0x180016377  mov     rbx, [rsp+28h+arg_0]
0x18001637c  add     rsp, 20h
0x180016380  pop     rdi
0x180016381  retn
```
