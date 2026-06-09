# ClasspIsCommandDurationLimitSupported

- ea: `0x1400317b4`
- end: `0x1400317d8`
- name: `ClasspIsCommandDurationLimitSupported`
- size: `36`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140033924`
- `0x140033d94`
- `0x1400340b4`
- `0x140034e08`
- `0x140035128`
- `0x140035764`

## callees

- `0x1400317b4`

## pseudocode

```c
bool __fastcall ClasspIsCommandDurationLimitSupported(__int64 a1)
{
  __int64 v1; // rdx
  bool result; // al

  v1 = *(_QWORD *)(a1 + 1144);
  result = 0;
  if ( (*(_BYTE *)(v1 + 112) & 1) != 0 )
    return (*(_BYTE *)(v1 + 284) & 1) != 0;
  return result;
}

```

## disassembly

```asm
0x1400317b4  mov     rdx, [rcx+478h]
0x1400317bb  xor     al, al
0x1400317bd  mov     r8d, 1
0x1400317c3  test    [rdx+70h], r8b
0x1400317c7  jz      short locret_1400317D7
0x1400317c9  test    [rdx+11Ch], r8b
0x1400317d0  movzx   eax, al
0x1400317d3  cmovnz  eax, r8d
0x1400317d7  retn
```
