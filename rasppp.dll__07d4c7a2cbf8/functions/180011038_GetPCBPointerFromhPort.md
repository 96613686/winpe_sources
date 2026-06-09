# GetPCBPointerFromhPort

- ea: `0x180011038`
- end: `0x18001105e`
- name: `GetPCBPointerFromhPort`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x180003190`
- `0x1800078e0`
- `0x180009560`
- `0x1800149e0`
- `0x180014d00`
- `0x180014f20`
- `0x180014ff0`
- `0x1800151d0`
- `0x1800152a0`
- `0x180015320`
- `0x180015570`
- `0x1800155b8`
- `0x180015ae0`
- `0x180016d40`
- `0x180017490`
- `0x180017650`
- `0x180017790`
- `0x180017990`
- `0x180024fa0`

## callees

- `0x180011038`

## pseudocode

```c
_QWORD *__fastcall GetPCBPointerFromhPort(__int64 a1)
{
  _QWORD *result; // rax

  for ( result = (_QWORD *)*((_QWORD *)PcbTable + (unsigned int)a1 % (unsigned int)qword_18004C970);
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
0x180011038  mov     eax, ecx
0x18001103a  xor     edx, edx
0x18001103c  div     dword ptr cs:qword_18004C970
0x180011042  mov     rax, qword ptr cs:PcbTable
0x180011049  mov     rax, [rax+rdx*8]
0x18001104d  test    rax, rax
0x180011050  jz      short locret_18001105D
0x180011052  cmp     [rax+10h], rcx
0x180011056  jz      short locret_18001105D
0x180011058  mov     rax, [rax]
0x18001105b  jmp     short loc_18001104D
0x18001105d  retn
```
