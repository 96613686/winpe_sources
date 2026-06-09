# CPacketIo::DisableProcessing(void)

- ea: `0x180012630`
- end: `0x18001266b`
- name: `?DisableProcessing@CPacketIo@@IEAAHXZ`
- size: `59`
- prototype: `__int64 __fastcall(CPacketIo *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180012720`
- `0x180015604`
- `0x180015900`

## callees

- `0x180029d20`
- `0x180029ee4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180012639`
- `KERNEL32!GetCurrentThreadId` at `0x180012650`
- `KERNEL32!GetCurrentThreadId` at `0x180012639`
- `KERNEL32!GetCurrentThreadId` at `0x180012650`

## pseudocode

```c
__int64 __fastcall CPacketIo::DisableProcessing(CPacketIo *this)
{
  DWORD CurrentThreadId; // eax
  DWORD v3; // eax

  CurrentThreadId = GetCurrentThreadId();
  Perimeter::LockExclusive(this, CurrentThreadId);
  *((_DWORD *)this + 24) = 0;
  v3 = GetCurrentThreadId();
  Perimeter::Unlock(this, v3);
  return 1;
}

```

## disassembly

```asm
0x180012630  push    rbx
0x180012632  sub     rsp, 20h
0x180012636  mov     rbx, rcx
0x180012639  call    cs:__imp_GetCurrentThreadId
0x18001263f  mov     edx, eax; unsigned int
0x180012641  mov     rcx, rbx; this
0x180012644  call    ?LockExclusive@Perimeter@@QEAAXK@Z; Perimeter::LockExclusive(ulong)
0x180012649  mov     dword ptr [rbx+60h], 0
0x180012650  call    cs:__imp_GetCurrentThreadId
0x180012656  mov     edx, eax; unsigned int
0x180012658  mov     rcx, rbx; this
0x18001265b  call    ?Unlock@Perimeter@@QEAAXK@Z; Perimeter::Unlock(ulong)
0x180012660  mov     eax, 1
0x180012665  add     rsp, 20h
0x180012669  pop     rbx
0x18001266a  retn
```
