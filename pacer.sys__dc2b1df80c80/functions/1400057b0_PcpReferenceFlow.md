# PcpReferenceFlow

- ea: `0x1400057b0`
- end: `0x1400057c5`
- name: `PcpReferenceFlow`
- size: `21`
- prototype: `char __fastcall(__int64)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140002e80`
- `0x14000570c`
- `0x140005c10`
- `0x14000a830`
- `0x14000bcb4`
- `0x14000c10c`
- `0x14000d284`
- `0x14000eaec`
- `0x14000fd20`
- `0x14000ff70`
- `0x140010b68`

## callees

- `0x1400057b0`

## pseudocode

```c
char __fastcall PcpReferenceFlow(__int64 a1)
{
  if ( (*(_DWORD *)(a1 + 616) & 8) != 0 )
    return 0;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 32));
  return 1;
}

```

## disassembly

```asm
0x1400057b0  mov     eax, [rcx+268h]
0x1400057b6  test    al, 8
0x1400057b8  jnz     short loc_1400057C2
0x1400057ba  lock inc dword ptr [rcx+20h]
0x1400057be  mov     al, 1
0x1400057c0  retn
0x1400057c2  xor     al, al
0x1400057c4  retn
```
