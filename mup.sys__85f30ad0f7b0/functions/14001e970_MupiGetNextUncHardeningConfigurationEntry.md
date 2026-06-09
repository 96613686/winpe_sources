# MupiGetNextUncHardeningConfigurationEntry

- ea: `0x14001e970`
- end: `0x14001e987`
- name: `MupiGetNextUncHardeningConfigurationEntry`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140015838`

## callees

- `0x14001e970`

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
0x14001e970  xor     eax, eax
0x14001e972  test    rdx, rdx
0x14001e975  jz      short locret_14001E986
0x14001e977  mov     r8, [rdx+8]
0x14001e97b  cmp     r8, rcx
0x14001e97e  lea     rdx, [r8-8]
0x14001e982  cmovnz  rax, rdx
0x14001e986  retn
```
