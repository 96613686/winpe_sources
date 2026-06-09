# BwcNblAppendNblsMoveLast

- ea: `0x14000917c`
- end: `0x140009199`
- name: `BwcNblAppendNblsMoveLast`
- size: `29`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002974`
- `0x140011da8`
- `0x1400123e4`

## callees

- `0x14000917c`

## pseudocode

```c
_QWORD *__fastcall BwcNblAppendNblsMoveLast(_QWORD *a1, _QWORD *a2)
{
  _QWORD *result; // rax
  _QWORD *v3; // r8

  result = (_QWORD *)*a1;
  *(_QWORD *)*a1 = a2;
  if ( a2 )
  {
    do
    {
      result = (_QWORD *)*a2;
      v3 = a2;
      a2 = result;
    }
    while ( result );
    *a1 = v3;
  }
  return result;
}

```

## disassembly

```asm
0x14000917c  mov     rax, [rcx]
0x14000917f  mov     [rax], rdx
0x140009182  test    rdx, rdx
0x140009185  jz      short locret_140009198
0x140009187  mov     rax, [rdx]
0x14000918a  mov     r8, rdx
0x14000918d  mov     rdx, rax
0x140009190  test    rax, rax
0x140009193  jnz     short loc_140009187
0x140009195  mov     [rcx], r8
0x140009198  retn
```
