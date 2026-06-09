# NcaCustomCommandEmpty

- ea: `0x180006d70`
- end: `0x180006d8d`
- name: `NcaCustomCommandEmpty`
- size: `29`
- prototype: `__int64 __fastcall(LPVOID *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005d04`
- `0x1800063f0`
- `0x18000a398`

## callees

- `0x180003770`

## pseudocode

```c
__int64 __fastcall NcaCustomCommandEmpty(LPVOID *a1)
{
  __int64 result; // rax

  NcaFree(*a1);
  result = 0;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180006d70  push    rbx
0x180006d72  sub     rsp, 20h
0x180006d76  mov     rbx, rcx
0x180006d79  mov     rcx, [rcx]; lpMem
0x180006d7c  call    NcaFree
0x180006d81  xor     eax, eax
0x180006d83  mov     [rbx], rax
0x180006d86  add     rsp, 20h
0x180006d8a  pop     rbx
0x180006d8b  retn
```
