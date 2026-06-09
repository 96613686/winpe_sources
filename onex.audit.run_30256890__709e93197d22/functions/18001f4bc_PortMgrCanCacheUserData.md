# PortMgrCanCacheUserData

- ea: `0x18001f4bc`
- end: `0x18001f4d7`
- name: `PortMgrCanCacheUserData`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a318`
- `0x18001b360`

## callees

- `0x18001f4bc`

## pseudocode

```c
_BOOL8 __fastcall PortMgrCanCacheUserData(__int64 a1)
{
  return (*(_DWORD *)(a1 + 24) & 0x100) == 0 && (*(_DWORD *)(a1 + 24) & 0x400) == 0;
}

```

## disassembly

```asm
0x18001f4bc  test    dword ptr [rcx+18h], 100h
0x18001f4c3  jnz     short loc_18001F4D4
0x18001f4c5  test    dword ptr [rcx+18h], 400h
0x18001f4cc  jnz     short loc_18001F4D4
0x18001f4ce  mov     eax, 1
0x18001f4d3  retn
0x18001f4d4  xor     eax, eax
0x18001f4d6  retn
```
