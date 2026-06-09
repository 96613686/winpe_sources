# LsaLookuprOpenPolicy2

- ea: `0x1400015d0`
- end: `0x1400015f9`
- name: `LsaLookuprOpenPolicy2`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x1400015d0`
- `0x140006010`

## pseudocode

```c
__int64 LsaLookuprOpenPolicy2()
{
  if ( gLsapLookupExtension && *(_QWORD *)gLsapLookupExtension )
    return (*(__int64 (**)(void))gLsapLookupExtension)();
  else
    return 3221225474LL;
}

```

## disassembly

```asm
0x1400015d0  sub     rsp, 38h
0x1400015d4  mov     rax, cs:gLsapLookupExtension
0x1400015db  test    rax, rax
0x1400015de  jz      short loc_1400015F2
0x1400015e0  mov     rax, [rax]
0x1400015e3  test    rax, rax
0x1400015e6  jz      short loc_1400015F2
0x1400015e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400015ed  add     rsp, 38h
0x1400015f1  retn
0x1400015f2  mov     eax, 0C0000002h
0x1400015f7  jmp     short loc_1400015ED
```
