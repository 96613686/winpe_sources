# HashString(ushort const *,ulong)

- ea: `0x180002ee0`
- end: `0x180002f05`
- name: `?HashString@@YAKPEBGK@Z`
- size: `37`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180002eb0`
- `0x1800074a0`

## callees

- `0x180002ee0`

## pseudocode

```c
__int64 __fastcall HashString(unsigned __int16 *a1)
{
  unsigned __int16 v1; // dx
  __int64 result; // rax

  v1 = *a1;
  for ( result = 0; *a1; v1 = *a1 )
  {
    ++a1;
    result = (unsigned int)v1 + 101 * (_DWORD)result;
  }
  return result;
}

```

## disassembly

```asm
0x180002ee0  movzx   edx, word ptr [rcx]
0x180002ee3  xor     eax, eax
0x180002ee5  test    dx, dx
0x180002ee8  jz      short locret_180002F04
0x180002eea  nop     word ptr [rax+rax+00h]
0x180002ef0  imul    eax, 65h ; 'e'
0x180002ef3  lea     rcx, [rcx+2]
0x180002ef7  movzx   edx, dx
0x180002efa  add     eax, edx
0x180002efc  movzx   edx, word ptr [rcx]
0x180002eff  test    dx, dx
0x180002f02  jnz     short loc_180002EF0
0x180002f04  retn
```
