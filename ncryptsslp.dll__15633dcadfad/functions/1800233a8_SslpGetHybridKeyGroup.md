# SslpGetHybridKeyGroup

- ea: `0x1800233a8`
- end: `0x1800233c7`
- name: `SslpGetHybridKeyGroup`
- size: `31`
- prototype: `__int64 *__fastcall(__int16)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180022608`
- `0x1800233d0`
- `0x1800238b4`
- `0x18002392c`

## callees

- `0x1800233a8`

## pseudocode

```c
__int64 *__fastcall SslpGetHybridKeyGroup(__int16 a1)
{
  __int64 *result; // rax

  result = qword_18002ADF0;
  while ( *(_WORD *)result != a1 )
  {
    result += 8;
    if ( result >= qword_18002AEB0 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800233a8  lea     rax, qword_18002ADF0
0x1800233af  cmp     [rax], cx
0x1800233b2  jz      short locret_1800233C6
0x1800233b4  add     rax, 40h ; '@'
0x1800233b8  lea     rdx, qword_18002AEB0
0x1800233bf  cmp     rax, rdx
0x1800233c2  jb      short loc_1800233AF
0x1800233c4  xor     eax, eax
0x1800233c6  retn
```
