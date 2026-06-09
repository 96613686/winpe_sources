# CsrLocateProcessByClientId

- ea: `0x180002850`
- end: `0x180002877`
- name: `CsrLocateProcessByClientId`
- size: `39`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800021f0`
- `0x180002540`
- `0x1800097f0`

## callees

- `0x180002850`

## pseudocode

```c
_QWORD *__fastcall CsrLocateProcessByClientId(__int64 a1)
{
  _QWORD *v1; // rax

  v1 = (_QWORD *)(CsrRootProcess + 16);
  while ( *(v1 - 2) != a1 )
  {
    v1 = (_QWORD *)*v1;
    if ( v1 == (_QWORD *)(CsrRootProcess + 16) )
      return 0;
  }
  return v1 - 2;
}

```

## disassembly

```asm
0x180002850  mov     r8, cs:CsrRootProcess
0x180002857  add     r8, 10h
0x18000285b  mov     rax, r8
0x18000285e  xchg    ax, ax
0x180002860  cmp     [rax-10h], rcx
0x180002864  jz      short loc_180002872
0x180002866  mov     rax, [rax]
0x180002869  cmp     rax, r8
0x18000286c  jnz     short loc_180002860
0x18000286e  xor     eax, eax
0x180002870  retn
0x180002872  add     rax, 0FFFFFFFFFFFFFFF0h
0x180002876  retn
```
