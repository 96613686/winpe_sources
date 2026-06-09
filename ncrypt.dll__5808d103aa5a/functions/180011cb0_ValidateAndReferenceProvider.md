# ValidateAndReferenceProvider

- ea: `0x180011cb0`
- end: `0x180011cc8`
- name: `ValidateAndReferenceProvider`
- size: `24`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d100`
- `0x180010c90`
- `0x180011310`
- `0x180011470`
- `0x180011950`
- `0x1800175f0`
- `0x180017990`
- `0x18001c2c0`

## callees

- `0x180011cb0`

## pseudocode

```c
__int64 __fastcall ValidateAndReferenceProvider(__int64 a1)
{
  if ( !a1 || *(_DWORD *)a1 != 1145307137 )
    return 0;
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 4));
  return a1;
}

```

## disassembly

```asm
0x180011cb0  test    rcx, rcx
0x180011cb3  jz      short loc_180011CBD
0x180011cb5  cmp     dword ptr [rcx], 44440001h
0x180011cbb  jz      short loc_180011CC0
0x180011cbd  xor     eax, eax
0x180011cbf  retn
0x180011cc0  lock inc dword ptr [rcx+4]
0x180011cc4  mov     rax, rcx
0x180011cc7  retn
```
