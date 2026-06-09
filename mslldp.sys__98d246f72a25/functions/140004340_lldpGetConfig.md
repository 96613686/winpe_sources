# lldpGetConfig

- ea: `0x140004340`
- end: `0x140004354`
- name: `lldpGetConfig`
- size: `20`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000e614`
- `0x140011a40`
- `0x140011cac`

## callees

- `0x140004340`

## pseudocode

```c
__int64 __fastcall lldpGetConfig(__int64 a1, unsigned int a2)
{
  if ( a2 > 6 )
    return 0;
  else
    return *(unsigned int *)(a1 + 4LL * (int)a2 + 248);
}

```

## disassembly

```asm
0x140004340  cmp     edx, 6
0x140004343  ja      short loc_140004351
0x140004345  movsxd  rax, edx
0x140004348  mov     eax, [rcx+rax*4+0F8h]
0x14000434f  retn
0x140004351  xor     eax, eax
0x140004353  retn
```
