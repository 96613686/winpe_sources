# MIME_MAP_TABLE::Dereference(void)

- ea: `0x180002c28`
- end: `0x180002c56`
- name: `?Dereference@MIME_MAP_TABLE@@QEAAXXZ`
- size: `46`
- prototype: `void __fastcall(MIME_MAP_TABLE *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001f40`
- `0x180002aac`
- `0x180007524`
- `0x180007710`

## callees

- `0x180002c28`
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
0x180002c28  sub     rsp, 28h
0x180002c2c  or      eax, 0FFFFFFFFh
0x180002c2f  lock xadd [rcx+428h], eax
0x180002c37  cmp     eax, 1
0x180002c3a  jnz     short loc_180002C51
0x180002c3c  test    rcx, rcx
0x180002c3f  jz      short loc_180002C51
0x180002c41  mov     rax, [rcx]
0x180002c44  mov     edx, 1
0x180002c49  mov     rax, [rax]
0x180002c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c51  add     rsp, 28h
0x180002c55  retn
```
