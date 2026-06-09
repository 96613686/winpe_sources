# CReference::Release(void)

- ea: `0x140004538`
- end: `0x140004563`
- name: `?Release@CReference@@QEBAXXZ`
- size: `43`
- prototype: `void __fastcall(CReference *__hidden this)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x14000393c`
- `0x140006624`
- `0x140007af8`
- `0x14000ab78`
- `0x14000ac00`
- `0x14000ac9c`
- `0x14000b43c`
- `0x14000b5a0`
- `0x14000c0e0`
- `0x14000cbd8`
- `0x14001d552`

## callees

- `0x140004538`
- `0x140020010`

## pseudocode

```c
void __fastcall CReference::Release(CReference *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
  {
    if ( this )
      (**(void (__fastcall ***)(CReference *, __int64))this)(this, 1);
  }
}

```

## disassembly

```asm
0x140004538  sub     rsp, 28h
0x14000453c  or      eax, 0FFFFFFFFh
0x14000453f  lock xadd [rcx+8], eax
0x140004544  cmp     eax, 1
0x140004547  jnz     short loc_14000455E
0x140004549  test    rcx, rcx
0x14000454c  jz      short loc_14000455E
0x14000454e  mov     rax, [rcx]
0x140004551  mov     edx, 1
0x140004556  mov     rax, [rax]
0x140004559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000455e  add     rsp, 28h
0x140004562  retn
```
