# RtlStringLengthWorkerW

- ea: `0x180008b50`
- end: `0x180008b8f`
- name: `RtlStringLengthWorkerW`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008ab0`
- `0x180008b18`

## callees

- `0x180008b50`

## pseudocode

```c
__int64 __fastcall RtlStringLengthWorkerW(_WORD *a1, __int64 a2, _QWORD *a3)
{
  __int64 i; // r9
  __int64 result; // rax

  for ( i = a2; a2; --a2 )
  {
    if ( !*a1 )
      break;
    ++a1;
  }
  result = a2 == 0 ? 0xC000000D : 0;
  if ( a3 )
  {
    if ( a2 )
      *a3 = i - a2;
    else
      *a3 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180008b50  xor     r10d, r10d
0x180008b53  mov     r9, rdx
0x180008b56  test    rdx, rdx
0x180008b59  jz      short loc_180008B6B
0x180008b5b  cmp     [rcx], r10w
0x180008b5f  jz      short loc_180008B6B
0x180008b61  add     rcx, 2
0x180008b65  sub     rdx, 1
0x180008b69  jnz     short loc_180008B5B
0x180008b6b  mov     rax, rdx
0x180008b6e  neg     rax
0x180008b71  sbb     eax, eax
0x180008b73  not     eax
0x180008b75  and     eax, 0C000000Dh
0x180008b7a  test    r8, r8
0x180008b7d  jz      short locret_180008B8E
0x180008b7f  test    rdx, rdx
0x180008b82  jz      short loc_180008B8B
0x180008b84  sub     r9, rdx
0x180008b87  mov     [r8], r9
0x180008b8a  retn
0x180008b8b  mov     [r8], r10
0x180008b8e  retn
```
