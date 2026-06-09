# LsaLookuprManageCache

- ea: `0x140001ce0`
- end: `0x140001d0a`
- name: `LsaLookuprManageCache`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140001ce0`
- `0x140006010`

## pseudocode

```c
__int64 LsaLookuprManageCache()
{
  __int64 (*v1)(void); // rax

  if ( gLsapLookupExtension && (v1 = *(__int64 (**)(void))(gLsapLookupExtension + 32)) != 0 )
    return v1();
  else
    return 3221225474LL;
}

```

## disassembly

```asm
0x140001ce0  sub     rsp, 38h
0x140001ce4  mov     rax, cs:gLsapLookupExtension
0x140001ceb  test    rax, rax
0x140001cee  jnz     short loc_140001CFA
0x140001cf0  mov     eax, 0C0000002h
0x140001cf5  add     rsp, 38h
0x140001cf9  retn
0x140001cfa  mov     rax, [rax+20h]
0x140001cfe  test    rax, rax
0x140001d01  jz      short loc_140001CF0
0x140001d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001d08  jmp     short loc_140001CF5
```
