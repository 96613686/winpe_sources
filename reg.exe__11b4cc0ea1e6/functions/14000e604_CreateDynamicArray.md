# CreateDynamicArray

- ea: `0x14000e604`
- end: `0x14000e62d`
- name: `CreateDynamicArray`
- size: `41`
- prototype: `_QWORD *()`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400053e0`
- `0x140007170`
- `0x140007834`
- `0x140007be0`
- `0x140008320`
- `0x14000d114`
- `0x14000e718`

## callees

- `0x14000c62c`
- `0x14000e604`

## pseudocode

```c
_QWORD *CreateDynamicArray()
{
  _QWORD *result; // rax

  result = AllocateMemory(0x18u);
  if ( result )
  {
    *result = 9;
    result[1] = 0;
    result[2] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000e604  sub     rsp, 28h
0x14000e608  mov     ecx, 18h; dwBytes
0x14000e60d  call    AllocateMemory
0x14000e612  xor     ecx, ecx
0x14000e614  test    rax, rax
0x14000e617  jz      short loc_14000E628
0x14000e619  mov     qword ptr [rax], 9
0x14000e620  mov     [rax+8], rcx
0x14000e624  mov     [rax+10h], rcx
0x14000e628  add     rsp, 28h
0x14000e62c  retn
```
