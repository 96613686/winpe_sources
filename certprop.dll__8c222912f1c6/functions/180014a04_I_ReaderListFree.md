# I_ReaderListFree

- ea: `0x180014a04`
- end: `0x180014a28`
- name: `I_ReaderListFree`
- size: `36`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800010c4`
- `0x180001274`
- `0x180003510`
- `0x180005830`
- `0x18000e47c`

## callees

- `0x180014a04`
- `0x18001f9a0`

## pseudocode

```c
__int64 __fastcall I_ReaderListFree(_QWORD *a1)
{
  _QWORD *v1; // rbx
  __int64 result; // rax

  if ( a1 )
  {
    do
    {
      v1 = (_QWORD *)a1[30];
      result = I_ReaderListFreeItem(a1);
      a1 = v1;
    }
    while ( v1 );
  }
  return result;
}

```

## disassembly

```asm
0x180014a04  test    rcx, rcx
0x180014a07  jz      short locret_180014A27
0x180014a09  push    rbx
0x180014a0a  sub     rsp, 20h
0x180014a0e  mov     rbx, [rcx+0F0h]
0x180014a15  call    I_ReaderListFreeItem
0x180014a1a  mov     rcx, rbx
0x180014a1d  test    rbx, rbx
0x180014a20  jnz     short loc_180014A0E
0x180014a22  add     rsp, 20h
0x180014a26  pop     rbx
0x180014a27  retn
```
