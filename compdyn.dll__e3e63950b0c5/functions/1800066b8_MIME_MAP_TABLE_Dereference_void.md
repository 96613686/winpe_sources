# MIME_MAP_TABLE::Dereference(void)

- ea: `0x1800066b8`
- end: `0x1800066e0`
- name: `?Dereference@MIME_MAP_TABLE@@QEAAXXZ`
- size: `40`
- prototype: `void __fastcall(MIME_MAP_TABLE *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800019a0`
- `0x180003fb0`
- `0x180006e14`

## callees

- `0x1800066b8`
- `0x180008010`

## pseudocode

```c
void __fastcall MIME_MAP_TABLE::Dereference(MIME_MAP_TABLE *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 266, 0xFFFFFFFF) == 1 )
  {
    if ( this )
      (**(void (__fastcall ***)(MIME_MAP_TABLE *, __int64))this)(this, 1);
  }
}

```

## disassembly

```asm
0x1800066b8  mov     eax, 0FFFFFFFFh
0x1800066bd  lock xadd [rcx+428h], eax
0x1800066c5  cmp     eax, 1
0x1800066c8  jnz     short locret_1800066DF
0x1800066ca  test    rcx, rcx
0x1800066cd  jz      short locret_1800066DF
0x1800066cf  mov     rax, [rcx]
0x1800066d2  mov     edx, 1
0x1800066d7  mov     rax, [rax]
0x1800066da  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800066df  retn
```
