# CPacketIo::EnableProcessing(void)

- ea: `0x180012674`
- end: `0x1800126af`
- name: `?EnableProcessing@CPacketIo@@IEAAHXZ`
- size: `59`
- prototype: `__int64 __fastcall(CPacketIo *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180012700`
- `0x180015604`

## callees

- `0x180029d20`
- `0x180029ee4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001267d`
- `KERNEL32!GetCurrentThreadId` at `0x180012694`
- `KERNEL32!GetCurrentThreadId` at `0x18001267d`
- `KERNEL32!GetCurrentThreadId` at `0x180012694`

## pseudocode

```c
__int64 __fastcall CPacketIo::EnableProcessing(CPacketIo *this)
{
  DWORD CurrentThreadId; // eax
  DWORD v3; // eax

  CurrentThreadId = GetCurrentThreadId();
  Perimeter::LockExclusive(this, CurrentThreadId);
  *((_DWORD *)this + 24) = 1;
  v3 = GetCurrentThreadId();
  Perimeter::Unlock(this, v3);
  return 1;
}

```

## disassembly

```asm
0x180012674  push    rbx
0x180012676  sub     rsp, 20h
0x18001267a  mov     rbx, rcx
0x18001267d  call    cs:__imp_GetCurrentThreadId
0x180012683  mov     edx, eax; unsigned int
0x180012685  mov     rcx, rbx; this
0x180012688  call    ?LockExclusive@Perimeter@@QEAAXK@Z; Perimeter::LockExclusive(ulong)
0x18001268d  mov     dword ptr [rbx+60h], 1
0x180012694  call    cs:__imp_GetCurrentThreadId
0x18001269a  mov     edx, eax; unsigned int
0x18001269c  mov     rcx, rbx; this
0x18001269f  call    ?Unlock@Perimeter@@QEAAXK@Z; Perimeter::Unlock(ulong)
0x1800126a4  mov     eax, 1
0x1800126a9  add     rsp, 20h
0x1800126ad  pop     rbx
0x1800126ae  retn
```
