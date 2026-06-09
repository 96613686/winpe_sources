# CPersistStreamInit::WriteNamespace(uchar)

- ea: `0x18001ed5c`
- end: `0x18001ed91`
- name: `?WriteNamespace@CPersistStreamInit@@AEAAJE@Z`
- size: `53`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, unsigned __int8)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d1c8`
- `0x18001d42c`
- `0x18001d828`
- `0x18001dd70`
- `0x18001e3c0`
- `0x18001ea04`
- `0x18001f1bc`
- `0x18001f520`
- `0x18001f680`
- `0x18001f7c8`
- `0x18001fbc8`
- `0x18001fcec`
- `0x18001fd90`

## callees

- `0x18001ed5c`
- `0x18001fe94`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::WriteNamespace(CPersistStreamInit *this, unsigned __int8 a2)
{
  __int64 result; // rax
  unsigned int v4; // [rsp+40h] [rbp+18h] BYREF

  v4 = 0;
  result = CPersistStreamInit::WriteTag(this, a2, &v4);
  if ( (int)result >= 0 )
    return CPersistStreamInit::WriteTag(this, 0x2Au, &v4);
  return result;
}

```

## disassembly

```asm
0x18001ed5c  push    rbx
0x18001ed5e  sub     rsp, 20h
0x18001ed62  lea     r8, [rsp+28h+arg_10]; unsigned int *
0x18001ed67  mov     [rsp+28h+arg_10], 0
0x18001ed6f  mov     rbx, rcx
0x18001ed72  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001ed77  test    eax, eax
0x18001ed79  js      short loc_18001ED8A
0x18001ed7b  lea     r8, [rsp+28h+arg_10]; unsigned int *
0x18001ed80  mov     dl, 2Ah ; '*'; unsigned __int8
0x18001ed82  mov     rcx, rbx; this
0x18001ed85  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001ed8a  add     rsp, 20h
0x18001ed8e  pop     rbx
0x18001ed8f  retn
```
