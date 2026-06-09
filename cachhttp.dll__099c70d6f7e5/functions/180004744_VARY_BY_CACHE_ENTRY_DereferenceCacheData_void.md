# VARY_BY_CACHE_ENTRY::DereferenceCacheData(void)

- ea: `0x180004744`
- end: `0x180004770`
- name: `?DereferenceCacheData@VARY_BY_CACHE_ENTRY@@QEAAXXZ`
- size: `44`
- prototype: `void __fastcall(VARY_BY_CACHE_ENTRY *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180002f20`
- `0x180004220`
- `0x180004778`
- `0x1800065b0`
- `0x1800076c0`

## callees

- `0x180004744`
- `0x180009010`

## pseudocode

```c
void __fastcall VARY_BY_CACHE_ENTRY::DereferenceCacheData(VARY_BY_CACHE_ENTRY *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 3, 0xFFFFFFFF) == 1 )
  {
    if ( this )
      (*(void (__fastcall **)(VARY_BY_CACHE_ENTRY *, __int64))(*(_QWORD *)this + 8LL))(this, 1);
  }
}

```

## disassembly

```asm
0x180004744  sub     rsp, 28h
0x180004748  or      eax, 0FFFFFFFFh
0x18000474b  lock xadd [rcx+0Ch], eax
0x180004750  cmp     eax, 1
0x180004753  jnz     short loc_18000476B
0x180004755  test    rcx, rcx
0x180004758  jz      short loc_18000476B
0x18000475a  mov     rax, [rcx]
0x18000475d  mov     edx, 1
0x180004762  mov     rax, [rax+8]
0x180004766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000476b  add     rsp, 28h
0x18000476f  retn
```
