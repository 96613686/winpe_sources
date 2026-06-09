# HashString(ushort const *,ulong)

- ea: `0x180008c68`
- end: `0x180008c87`
- name: `?HashString@@YAKPEBGK@Z`
- size: `31`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a50`
- `0x180004b30`

## callees

- `0x180008c68`

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
0x180008c68  movzx   edx, word ptr [rcx]
0x180008c6b  xor     eax, eax
0x180008c6d  test    dx, dx
0x180008c70  jz      short locret_180008C86
0x180008c72  imul    eax, 65h ; 'e'
0x180008c75  lea     rcx, [rcx+2]
0x180008c79  movzx   edx, dx
0x180008c7c  add     eax, edx
0x180008c7e  movzx   edx, word ptr [rcx]
0x180008c81  test    dx, dx
0x180008c84  jnz     short loc_180008C72
0x180008c86  retn
```
