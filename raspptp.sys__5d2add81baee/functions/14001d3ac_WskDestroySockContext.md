# WskDestroySockContext

- ea: `0x14001d3ac`
- end: `0x14001d3d2`
- name: `WskDestroySockContext`
- size: `38`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140011d04`
- `0x140012da4`
- `0x140014fd8`

## callees

- `0x140007710`
- `0x14001d3ac`

## pseudocode

```c
__int64 __fastcall WskDestroySockContext(__int64 a1)
{
  __int64 result; // rax

  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 512), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
    return (*(__int64 (**)(void))(a1 + 520))();
  return result;
}

```

## disassembly

```asm
0x14001d3ac  sub     rsp, 28h
0x14001d3b0  or      eax, 0FFFFFFFFh
0x14001d3b3  lock xadd [rcx+200h], eax
0x14001d3bb  cmp     eax, 1
0x14001d3be  jnz     short loc_14001D3CC
0x14001d3c0  mov     rax, [rcx+208h]
0x14001d3c7  call    _guard_dispatch_icall
0x14001d3cc  add     rsp, 28h
0x14001d3d0  retn
```
