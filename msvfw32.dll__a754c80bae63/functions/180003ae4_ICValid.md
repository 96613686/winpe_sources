# ICValid

- ea: `0x180003ae4`
- end: `0x180003b15`
- name: `ICValid`
- size: `49`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002640`
- `0x180002df0`
- `0x180003a60`

## callees

- `0x180003ae4`

## pseudocode

```c
_BOOL8 __fastcall ICValid(__int64 *a1)
{
  return a1 >= (__int64 *)paicConverters
      && a1 < &(*paicConverters)[6 * (unsigned int)g_max_converters]
      && *(_DWORD *)a1 == 1734438227;
}

```

## disassembly

```asm
0x180003ae4  mov     r8, cs:paicConverters
0x180003aeb  cmp     rcx, r8
0x180003aee  jb      short loc_180003B12
0x180003af0  mov     eax, cs:g_max_converters
0x180003af6  lea     rdx, [rax+rax*2]
0x180003afa  shl     rdx, 4
0x180003afe  add     rdx, r8
0x180003b01  cmp     rcx, rdx
0x180003b04  jnb     short loc_180003B12
0x180003b06  xor     eax, eax
0x180003b08  cmp     dword ptr [rcx], 67616D53h
0x180003b0e  setz    al
0x180003b11  retn
0x180003b12  xor     eax, eax
0x180003b14  retn
```
