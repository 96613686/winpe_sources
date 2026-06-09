# CreateDynamicArray

- ea: `0x14000f294`
- end: `0x14000f2be`
- name: `CreateDynamicArray`
- size: `42`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400056ec`
- `0x1400075ac`
- `0x140007cbc`
- `0x1400080a4`
- `0x140008838`
- `0x14000dab0`
- `0x14000f3b0`

## callees

- `0x14000ce50`
- `0x14000f294`

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
0x14000f294  sub     rsp, 28h
0x14000f298  mov     ecx, 18h; dwBytes
0x14000f29d  call    AllocateMemory
0x14000f2a2  xor     ecx, ecx
0x14000f2a4  test    rax, rax
0x14000f2a7  jz      short loc_14000F2B8
0x14000f2a9  mov     qword ptr [rax], 9
0x14000f2b0  mov     [rax+8], rcx
0x14000f2b4  mov     [rax+10h], rcx
0x14000f2b8  add     rsp, 28h
0x14000f2bc  retn
```
