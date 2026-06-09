# APICharNext(ushort const *)

- ea: `0x140003c8c`
- end: `0x140003ca5`
- name: `?APICharNext@@YAPEBGPEBG@Z`
- size: `25`
- prototype: `const unsigned __int16 *__fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003ffc`
- `0x140007568`

## callees

- `0x140003c8c`

## pseudocode

```c
const unsigned __int16 *__fastcall APICharNext(const unsigned __int16 *a1)
{
  if ( !a1 )
    return 0;
  if ( *a1 )
    ++a1;
  return a1;
}

```

## disassembly

```asm
0x140003c8c  xor     edx, edx
0x140003c8e  test    rcx, rcx
0x140003c91  jnz     short loc_140003C96
0x140003c93  xor     eax, eax
0x140003c95  retn
0x140003c96  cmp     [rcx], dx
0x140003c99  lea     rax, [rcx+2]
0x140003c9d  cmovnz  rcx, rax
0x140003ca1  mov     rax, rcx
0x140003ca4  retn
```
