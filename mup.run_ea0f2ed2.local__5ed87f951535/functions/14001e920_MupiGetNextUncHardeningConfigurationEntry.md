# MupiGetNextUncHardeningConfigurationEntry

- ea: `0x14001e920`
- end: `0x14001e937`
- name: `MupiGetNextUncHardeningConfigurationEntry`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400157e8`

## callees

- `0x14001e920`

## pseudocode

```c
__int64 __fastcall MupiGetNextUncHardeningConfigurationEntry(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v3; // r8

  result = 0;
  if ( a2 )
  {
    v3 = *(_QWORD *)(a2 + 8);
    if ( v3 != a1 )
      return v3 - 8;
  }
  return result;
}

```

## disassembly

```asm
0x14001e920  xor     eax, eax
0x14001e922  test    rdx, rdx
0x14001e925  jz      short locret_14001E936
0x14001e927  mov     r8, [rdx+8]
0x14001e92b  cmp     r8, rcx
0x14001e92e  lea     rdx, [r8-8]
0x14001e932  cmovnz  rax, rdx
0x14001e936  retn
```
