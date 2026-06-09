# lldpNmrSetConfig

- ea: `0x14000f330`
- end: `0x14000f354`
- name: `lldpNmrSetConfig`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140005084`
- `0x14000f330`
- `0x1400114d0`

## pseudocode

```c
__int64 __fastcall lldpNmrSetConfig(_DWORD *a1)
{
  char **v1; // rax
  __int64 v2; // rdx

  v1 = (char **)lldpOpenPortFromHandle(a1);
  if ( v1 )
    return lldpSetPortAdminConfig(v1[3], v2);
  else
    return 3221225480LL;
}

```

## disassembly

```asm
0x14000f330  sub     rsp, 28h
0x14000f334  call    lldpOpenPortFromHandle
0x14000f339  test    rax, rax
0x14000f33c  jnz     short loc_14000F345
0x14000f33e  mov     eax, 0C0000008h
0x14000f343  jmp     short loc_14000F34E
0x14000f345  mov     rcx, [rax+18h]; Context
0x14000f349  call    lldpSetPortAdminConfig
0x14000f34e  add     rsp, 28h
0x14000f352  retn
```
