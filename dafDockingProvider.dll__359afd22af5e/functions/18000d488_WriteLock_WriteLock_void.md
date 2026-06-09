# WriteLock::~WriteLock(void)

- ea: `0x18000d488`
- end: `0x18000d4aa`
- name: `??1WriteLock@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(PSRWLOCK *this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180013dc8`
- `0x180015ff8`
- `0x18001d959`

## callees

- `0x18000d488`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d49a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d49a`

## pseudocode

```c
void __fastcall WriteLock::~WriteLock(PSRWLOCK *this)
{
  if ( *((_BYTE *)this + 8) )
  {
    ReleaseSRWLockExclusive(*this);
    *((_BYTE *)this + 8) = 0;
  }
}

```

## disassembly

```asm
0x18000d488  push    rbx
0x18000d48a  sub     rsp, 20h
0x18000d48e  cmp     byte ptr [rcx+8], 0
0x18000d492  mov     rbx, rcx
0x18000d495  jz      short loc_18000D4A4
0x18000d497  mov     rcx, [rcx]; SRWLock
0x18000d49a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d4a0  mov     byte ptr [rbx+8], 0
0x18000d4a4  add     rsp, 20h
0x18000d4a8  pop     rbx
0x18000d4a9  retn
```
