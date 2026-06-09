# UL_RESPONSE_CACHE_ENTRY::DereferenceCacheData(void)

- ea: `0x1800025e4`
- end: `0x180002607`
- name: `?DereferenceCacheData@UL_RESPONSE_CACHE_ENTRY@@QEAAXXZ`
- size: `35`
- prototype: `void __fastcall(UL_RESPONSE_CACHE_ENTRY *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800011e0`
- `0x1800020d0`

## callees

- `0x1800025e4`
- `0x180009010`

## pseudocode

```c
void __fastcall UL_RESPONSE_CACHE_ENTRY::DereferenceCacheData(UL_RESPONSE_CACHE_ENTRY *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 3, 0xFFFFFFFF) == 1 )
  {
    if ( this )
      (**(void (__fastcall ***)(UL_RESPONSE_CACHE_ENTRY *, __int64))this)(this, 1);
  }
}

```

## disassembly

```asm
0x1800025e4  or      eax, 0FFFFFFFFh
0x1800025e7  lock xadd [rcx+0Ch], eax
0x1800025ec  cmp     eax, 1
0x1800025ef  jz      short loc_1800025F2
0x1800025f1  retn
0x1800025f2  test    rcx, rcx
0x1800025f5  jz      short locret_1800025F1
0x1800025f7  mov     rax, [rcx]
0x1800025fa  mov     edx, 1
0x1800025ff  mov     rax, [rax]
0x180002602  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
