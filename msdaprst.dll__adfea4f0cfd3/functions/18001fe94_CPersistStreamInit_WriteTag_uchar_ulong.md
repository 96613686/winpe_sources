# CPersistStreamInit::WriteTag(uchar,ulong *)

- ea: `0x18001fe94`
- end: `0x18001febf`
- name: `?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z`
- size: `43`
- prototype: `int(CPersistStreamInit *__hidden this, unsigned __int8, unsigned int *)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c0a0`
- `0x18001c400`
- `0x18001d054`
- `0x18001d1c8`
- `0x18001d42c`
- `0x18001d828`
- `0x18001db24`
- `0x18001dd70`
- `0x18001e3c0`
- `0x18001ea04`
- `0x18001ed5c`
- `0x18001ed98`
- `0x18001f1bc`
- `0x18001f520`
- `0x18001f680`
- `0x18001f7c8`
- `0x18001fbc8`
- `0x18001fcec`
- `0x18001fd90`

## callees

- `0x18001d054`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::WriteTag(CPersistStreamInit *this, unsigned __int8 a2, unsigned int *a3)
{
  return CPersistStreamInit::Write(
           this,
           *(_BYTE **)(*((_QWORD *)this + 9) + 16LL * a2),
           *(unsigned __int8 *)(*((_QWORD *)this + 9) + 16LL * a2 + 8),
           a3,
           0);
}

```

## disassembly

```asm
0x18001fe94  sub     rsp, 38h
0x18001fe98  movzx   eax, dl
0x18001fe9b  mov     r9, r8; unsigned int *
0x18001fe9e  mov     rdx, [rcx+48h]
0x18001fea2  add     rax, rax
0x18001fea5  mov     [rsp+38h+var_18], 0; bool
0x18001feaa  movzx   r8d, byte ptr [rdx+rax*8+8]; Size
0x18001feb0  mov     rdx, [rdx+rax*8]; Src
0x18001feb4  call    ?Write@CPersistStreamInit@@AEAAJPEAXKPEAK_N@Z; CPersistStreamInit::Write(void *,ulong,ulong *,bool)
0x18001feb9  add     rsp, 38h
0x18001febd  retn
```
