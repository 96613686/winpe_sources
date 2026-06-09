# NbtCopyToStartOfIndicate

- ea: `0x14002f3d4`
- end: `0x14002f406`
- name: `NbtCopyToStartOfIndicate`
- size: `50`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14001e168`
- `0x14002f40c`
- `0x14002f880`

## callees

- `0x14002f3d4`
- `0x140031140`

## pseudocode

```c
void *__fastcall NbtCopyToStartOfIndicate(__int64 a1, unsigned int a2)
{
  void *result; // rax

  *(_DWORD *)(a1 + 280) -= a2;
  result = (void *)*(unsigned int *)(a1 + 280);
  if ( a2 )
  {
    if ( (_DWORD)result )
      return memmove(*(void **)(a1 + 232), (const void *)(*(_QWORD *)(a1 + 232) + a2), (unsigned int)result);
  }
  return result;
}

```

## disassembly

```asm
0x14002f3d4  sub     rsp, 28h
0x14002f3d8  sub     [rcx+118h], edx
0x14002f3de  mov     eax, [rcx+118h]
0x14002f3e4  test    edx, edx
0x14002f3e6  jz      short loc_14002F400
0x14002f3e8  test    eax, eax
0x14002f3ea  jz      short loc_14002F400
0x14002f3ec  mov     rcx, [rcx+0E8h]; void *
0x14002f3f3  mov     r8d, eax; Size
0x14002f3f6  mov     edx, edx
0x14002f3f8  add     rdx, rcx; Src
0x14002f3fb  call    memmove
0x14002f400  add     rsp, 28h
0x14002f404  retn
```
