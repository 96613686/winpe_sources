# MIME_MAP_TABLE::Dereference(void)

- ea: `0x180008480`
- end: `0x1800084a8`
- name: `?Dereference@MIME_MAP_TABLE@@QEAAXXZ`
- size: `40`
- prototype: `void __fastcall(MIME_MAP_TABLE *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003de0`
- `0x180004ad0`
- `0x180008004`
- `0x180008904`

## callees

- `0x180008480`
- `0x180009010`

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
0x180008480  mov     eax, 0FFFFFFFFh
0x180008485  lock xadd [rcx+428h], eax
0x18000848d  cmp     eax, 1
0x180008490  jnz     short locret_1800084A7
0x180008492  test    rcx, rcx
0x180008495  jz      short locret_1800084A7
0x180008497  mov     rax, [rcx]
0x18000849a  mov     edx, 1
0x18000849f  mov     rax, [rax]
0x1800084a2  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800084a7  retn
```
