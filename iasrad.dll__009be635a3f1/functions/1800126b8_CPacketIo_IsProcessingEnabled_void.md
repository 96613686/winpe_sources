# CPacketIo::IsProcessingEnabled(void)

- ea: `0x1800126b8`
- end: `0x1800126f5`
- name: `?IsProcessingEnabled@CPacketIo@@IEAAHXZ`
- size: `61`
- prototype: `__int64 __fastcall(CPacketIo *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800157dc`
- `0x180015938`
- `0x1800162d8`

## callees

- `0x180029cb4`
- `0x180029ee4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800126c5`
- `KERNEL32!GetCurrentThreadId` at `0x1800126d8`
- `KERNEL32!GetCurrentThreadId` at `0x1800126c5`
- `KERNEL32!GetCurrentThreadId` at `0x1800126d8`

## pseudocode

```c
__int64 __fastcall CPacketIo::IsProcessingEnabled(CPacketIo *this)
{
  DWORD CurrentThreadId; // eax
  unsigned int v3; // ebx
  DWORD v4; // eax

  CurrentThreadId = GetCurrentThreadId();
  Perimeter::Lock(this, CurrentThreadId);
  v3 = *((_DWORD *)this + 24);
  v4 = GetCurrentThreadId();
  Perimeter::Unlock(this, v4);
  return v3;
}

```

## disassembly

```asm
0x1800126b8  mov     [rsp+arg_0], rbx
0x1800126bd  push    rdi
0x1800126be  sub     rsp, 20h
0x1800126c2  mov     rdi, rcx
0x1800126c5  call    cs:__imp_GetCurrentThreadId
0x1800126cb  mov     edx, eax; unsigned int
0x1800126cd  mov     rcx, rdi; this
0x1800126d0  call    ?Lock@Perimeter@@QEAAXK@Z; Perimeter::Lock(ulong)
0x1800126d5  mov     ebx, [rdi+60h]
0x1800126d8  call    cs:__imp_GetCurrentThreadId
0x1800126de  mov     edx, eax; unsigned int
0x1800126e0  mov     rcx, rdi; this
0x1800126e3  call    ?Unlock@Perimeter@@QEAAXK@Z; Perimeter::Unlock(ulong)
0x1800126e8  mov     eax, ebx
0x1800126ea  mov     rbx, [rsp+28h+arg_0]
0x1800126ef  add     rsp, 20h
0x1800126f3  pop     rdi
0x1800126f4  retn
```
