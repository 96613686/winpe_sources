# HashStringNoCase(ushort const *,ulong)

- ea: `0x1800074f4`
- end: `0x18000751b`
- name: `?HashStringNoCase@@YAKPEBGK@Z`
- size: `39`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180007428`

## callees

- `0x1800074f4`

## pseudocode

```c
__int64 __fastcall HashStringNoCase(const unsigned __int16 *a1)
{
  unsigned int i; // r8d
  __int16 v2; // ax

  for ( i = 0; ; i = (v2 & 0xFFDF) + 101 * i )
  {
    v2 = *a1;
    if ( !*a1 )
      break;
    ++a1;
  }
  return i;
}

```

## disassembly

```asm
0x1800074f4  xor     r9d, r9d
0x1800074f7  mov     r8d, r9d
0x1800074fa  jmp     short loc_18000750F
0x1800074fc  imul    r8d, 65h ; 'e'
0x180007500  lea     rcx, [rcx+2]
0x180007504  movzx   eax, ax
0x180007507  and     eax, 0FFDFh
0x18000750c  add     r8d, eax
0x18000750f  movzx   eax, word ptr [rcx]
0x180007512  test    ax, ax
0x180007515  jnz     short loc_1800074FC
0x180007517  mov     eax, r8d
0x18000751a  retn
```
