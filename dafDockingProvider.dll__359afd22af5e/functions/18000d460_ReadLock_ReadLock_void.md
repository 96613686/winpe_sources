# ReadLock::~ReadLock(void)

- ea: `0x18000d460`
- end: `0x18000d482`
- name: `??1ReadLock@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(PSRWLOCK *this)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ce20`
- `0x18000e5a4`
- `0x18000f3ec`
- `0x180014030`
- `0x1800145cc`
- `0x18001496c`
- `0x180014be4`
- `0x180014e20`
- `0x180015094`
- `0x180015a0c`
- `0x180015ff8`
- `0x180016374`
- `0x180016420`
- `0x1800165a4`
- `0x180016f0c`
- `0x18001d121`
- `0x18001d7bd`
- `0x18001d829`
- `0x18001d97d`

## callees

- `0x18000d460`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d472`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000d472`

## pseudocode

```c
void __fastcall ReadLock::~ReadLock(PSRWLOCK *this)
{
  if ( *((_BYTE *)this + 8) )
  {
    ReleaseSRWLockShared(*this);
    *((_BYTE *)this + 8) = 0;
  }
}

```

## disassembly

```asm
0x18000d460  push    rbx
0x18000d462  sub     rsp, 20h
0x18000d466  cmp     byte ptr [rcx+8], 0
0x18000d46a  mov     rbx, rcx
0x18000d46d  jz      short loc_18000D47C
0x18000d46f  mov     rcx, [rcx]; SRWLock
0x18000d472  call    cs:__imp_ReleaseSRWLockShared
0x18000d478  mov     byte ptr [rbx+8], 0
0x18000d47c  add     rsp, 20h
0x18000d480  pop     rbx
0x18000d481  retn
```
