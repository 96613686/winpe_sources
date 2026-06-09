# QuicConfigurationRelease

- ea: `0x1400207e0`
- end: `0x140020804`
- name: `QuicConfigurationRelease`
- size: `36`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140014d80`
- `0x14001ffc0`
- `0x140020010`
- `0x1400200d8`
- `0x140020b24`
- `0x140026b30`

## callees

- `0x1400207e0`
- `0x140020a04`
- `0x140029720`

## pseudocode

```c
__int64 __fastcall QuicConfigurationRelease(__int64 a1)
{
  __int64 result; // rax
  void *v2; // rdx

  result = CxPlatRefDecrement(a1 + 40);
  if ( (_BYTE)result )
    return QuicConfigurationUninitialize(v2);
  return result;
}

```

## disassembly

```asm
0x1400207e0  sub     rsp, 28h
0x1400207e4  mov     rdx, rcx
0x1400207e7  add     rcx, 28h ; '('
0x1400207eb  call    CxPlatRefDecrement
0x1400207f0  test    al, al
0x1400207f2  jnz     short loc_1400207FA
0x1400207f4  add     rsp, 28h
0x1400207f8  retn
0x1400207fa  mov     rcx, rdx; P
0x1400207fd  call    QuicConfigurationUninitialize
0x140020802  jmp     short loc_1400207F4
```
