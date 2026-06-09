# KSecCreateContextList

- ea: `0x180029530`
- end: `0x180029560`
- name: `KSecCreateContextList`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180029530`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180029546`
- `ntoskrnl!ExAllocatePool2` at `0x180029546`

## pseudocode

```c
_DWORD *__fastcall KSecCreateContextList(int a1)
{
  _DWORD *result; // rax

  result = (_DWORD *)ExAllocatePool2(64, 4, 1279485267);
  if ( result )
    *result = a1;
  return result;
}

```

## disassembly

```asm
0x180029530  push    rbx
0x180029532  sub     rsp, 20h
0x180029536  mov     edx, 4
0x18002953b  mov     ebx, ecx
0x18002953d  mov     r8d, 4C436553h
0x180029543  lea     ecx, [rdx+3Ch]
0x180029546  call    cs:__imp_ExAllocatePool2
0x18002954d  nop     dword ptr [rax+rax+00h]
0x180029552  test    rax, rax
0x180029555  jz      short loc_180029559
0x180029557  mov     [rax], ebx
0x180029559  add     rsp, 20h
0x18002955d  pop     rbx
0x18002955e  retn
```
