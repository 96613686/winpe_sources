# MupiSelectBestMatchingConfigurationEntry

- ea: `0x140015ddc`
- end: `0x140015e4e`
- name: `MupiSelectBestMatchingConfigurationEntry`
- size: `114`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140017f00`
- `0x140018520`
- `0x14001a8d0`

## callees

- `0x140015ddc`

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
0x140015ddc  test    rdx, rdx
0x140015ddf  jz      short loc_140015E24
0x140015de1  test    r8, r8
0x140015de4  jz      short loc_140015E4A
0x140015de6  cmp     dword ptr [rcx], 1
0x140015de9  jnz     short loc_140015DF9
0x140015deb  movzx   eax, word ptr [rcx+10h]
0x140015def  cmp     [rcx+12h], ax
0x140015df3  jz      short loc_140015DF9
0x140015df5  mov     al, 1
0x140015df7  jmp     short loc_140015DFB
0x140015df9  xor     al, al
0x140015dfb  mov     ecx, [rdx+18h]
0x140015dfe  test    al, al
0x140015e00  jz      short loc_140015E29
0x140015e02  cmp     ecx, 1
0x140015e05  jnz     short loc_140015E11
0x140015e07  movzx   eax, word ptr [rdx+28h]
0x140015e0b  cmp     [rdx+2Ah], ax
0x140015e0f  jnz     short loc_140015E4A
0x140015e11  cmp     dword ptr [r8+18h], 1
0x140015e16  jnz     short loc_140015E4A
0x140015e18  movzx   eax, word ptr [r8+28h]
0x140015e1d  cmp     [r8+2Ah], ax
0x140015e22  jz      short loc_140015E4A
0x140015e24  mov     rax, r8
0x140015e27  retn
0x140015e29  cmp     ecx, 1
0x140015e2c  jnz     short loc_140015E4A
0x140015e2e  movzx   eax, word ptr [rdx+28h]
0x140015e32  cmp     [rdx+2Ah], ax
0x140015e36  jz      short loc_140015E4A
0x140015e38  cmp     [r8+18h], ecx
0x140015e3c  jnz     short loc_140015E24
0x140015e3e  movzx   eax, word ptr [r8+28h]
0x140015e43  cmp     [r8+2Ah], ax
0x140015e48  jz      short loc_140015E24
0x140015e4a  mov     rax, rdx
0x140015e4d  retn
```
