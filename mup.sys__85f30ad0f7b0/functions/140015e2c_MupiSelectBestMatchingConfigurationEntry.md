# MupiSelectBestMatchingConfigurationEntry

- ea: `0x140015e2c`
- end: `0x140015e9e`
- name: `MupiSelectBestMatchingConfigurationEntry`
- size: `114`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140017f50`
- `0x140018570`
- `0x14001a920`

## callees

- `0x140015e2c`

## pseudocode

```c
__int64 __fastcall MupiSelectBestMatchingConfigurationEntry(__int64 a1, __int64 a2, __int64 a3)
{
  bool v3; // al
  int v4; // ecx

  if ( !a2 )
    return a3;
  if ( !a3 )
    return a2;
  v3 = *(_DWORD *)a1 == 1 && *(_WORD *)(a1 + 18) != *(_WORD *)(a1 + 16);
  v4 = *(_DWORD *)(a2 + 24);
  if ( !v3 )
  {
    if ( v4 != 1
      || *(_WORD *)(a2 + 42) == *(_WORD *)(a2 + 40)
      || *(_DWORD *)(a3 + 24) == 1 && *(_WORD *)(a3 + 42) != *(_WORD *)(a3 + 40) )
    {
      return a2;
    }
    return a3;
  }
  if ( (v4 != 1 || *(_WORD *)(a2 + 42) == *(_WORD *)(a2 + 40))
    && *(_DWORD *)(a3 + 24) == 1
    && *(_WORD *)(a3 + 42) != *(_WORD *)(a3 + 40) )
  {
    return a3;
  }
  return a2;
}

```

## disassembly

```asm
0x140015e2c  test    rdx, rdx
0x140015e2f  jz      short loc_140015E74
0x140015e31  test    r8, r8
0x140015e34  jz      short loc_140015E9A
0x140015e36  cmp     dword ptr [rcx], 1
0x140015e39  jnz     short loc_140015E49
0x140015e3b  movzx   eax, word ptr [rcx+10h]
0x140015e3f  cmp     [rcx+12h], ax
0x140015e43  jz      short loc_140015E49
0x140015e45  mov     al, 1
0x140015e47  jmp     short loc_140015E4B
0x140015e49  xor     al, al
0x140015e4b  mov     ecx, [rdx+18h]
0x140015e4e  test    al, al
0x140015e50  jz      short loc_140015E79
0x140015e52  cmp     ecx, 1
0x140015e55  jnz     short loc_140015E61
0x140015e57  movzx   eax, word ptr [rdx+28h]
0x140015e5b  cmp     [rdx+2Ah], ax
0x140015e5f  jnz     short loc_140015E9A
0x140015e61  cmp     dword ptr [r8+18h], 1
0x140015e66  jnz     short loc_140015E9A
0x140015e68  movzx   eax, word ptr [r8+28h]
0x140015e6d  cmp     [r8+2Ah], ax
0x140015e72  jz      short loc_140015E9A
0x140015e74  mov     rax, r8
0x140015e77  retn
0x140015e79  cmp     ecx, 1
0x140015e7c  jnz     short loc_140015E9A
0x140015e7e  movzx   eax, word ptr [rdx+28h]
0x140015e82  cmp     [rdx+2Ah], ax
0x140015e86  jz      short loc_140015E9A
0x140015e88  cmp     [r8+18h], ecx
0x140015e8c  jnz     short loc_140015E74
0x140015e8e  movzx   eax, word ptr [r8+28h]
0x140015e93  cmp     [r8+2Ah], ax
0x140015e98  jz      short loc_140015E74
0x140015e9a  mov     rax, rdx
0x140015e9d  retn
```
