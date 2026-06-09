# GetPCBPointerFromhPort

- ea: `0x1800115a0`
- end: `0x1800115c6`
- name: `GetPCBPointerFromhPort`
- size: `38`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x1800031f4`
- `0x180007bd0`
- `0x180009920`
- `0x180015100`
- `0x180015430`
- `0x180015660`
- `0x180015730`
- `0x180015920`
- `0x180015a00`
- `0x180015a80`
- `0x180015ce0`
- `0x180015d28`
- `0x180016260`
- `0x180017510`
- `0x180017ca0`
- `0x180017e60`
- `0x180017fa0`
- `0x1800181b0`
- `0x180025d40`

## callees

- `0x1800115a0`

## pseudocode

```c
_QWORD *__fastcall GetPCBPointerFromhPort(__int64 a1)
{
  _QWORD *result; // rax

  for ( result = (_QWORD *)*((_QWORD *)PcbTable + (unsigned int)a1 % (unsigned int)qword_18004D970);
        result && result[2] != a1;
        result = (_QWORD *)*result )
  {
    ;
  }
  return result;
}

```

## disassembly

```asm
0x1800115a0  mov     eax, ecx
0x1800115a2  xor     edx, edx
0x1800115a4  div     dword ptr cs:qword_18004D970
0x1800115aa  mov     rax, qword ptr cs:PcbTable
0x1800115b1  mov     rax, [rax+rdx*8]
0x1800115b5  test    rax, rax
0x1800115b8  jz      short locret_1800115C5
0x1800115ba  cmp     [rax+10h], rcx
0x1800115be  jz      short locret_1800115C5
0x1800115c0  mov     rax, [rax]
0x1800115c3  jmp     short loc_1800115B5
0x1800115c5  retn
```
