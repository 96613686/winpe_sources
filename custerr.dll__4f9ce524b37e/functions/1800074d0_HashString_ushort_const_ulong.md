# HashString(ushort const *,ulong)

- ea: `0x1800074d0`
- end: `0x1800074ed`
- name: `?HashString@@YAKPEBGK@Z`
- size: `29`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180007428`

## callees

- `0x1800074d0`

## pseudocode

```c
__int64 __fastcall HashString(unsigned __int16 *a1)
{
  __int64 result; // rax
  unsigned __int16 v2; // dx

  for ( result = 0; ; result = (unsigned int)v2 + 101 * (_DWORD)result )
  {
    v2 = *a1;
    if ( !*a1 )
      break;
    ++a1;
  }
  return result;
}

```

## disassembly

```asm
0x1800074d0  xor     r8d, r8d
0x1800074d3  mov     eax, r8d
0x1800074d6  jmp     short loc_1800074E4
0x1800074d8  imul    eax, 65h ; 'e'
0x1800074db  lea     rcx, [rcx+2]
0x1800074df  movzx   edx, dx
0x1800074e2  add     eax, edx
0x1800074e4  movzx   edx, word ptr [rcx]
0x1800074e7  test    dx, dx
0x1800074ea  jnz     short loc_1800074D8
0x1800074ec  retn
```
