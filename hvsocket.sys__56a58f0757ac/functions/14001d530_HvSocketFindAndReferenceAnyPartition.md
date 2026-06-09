# HvSocketFindAndReferenceAnyPartition

- ea: `0x14001d530`
- end: `0x14001d561`
- name: `HvSocketFindAndReferenceAnyPartition`
- size: `49`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x14001a9f0`
- `0x14001ac90`
- `0x14001ae50`
- `0x14001b200`
- `0x14001b3c0`
- `0x14001df1c`
- `0x14001e5ac`

## callees

- `0x14001d530`
- `0x14001d568`
- `0x14001f540`

## pseudocode

```c
__int64 __fastcall HvSocketFindAndReferenceAnyPartition(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = VmbusTlFindAndReferencePartition(a1, a2);
  if ( !result )
    return HvSocketFindAndReferenceUninitializedPartition(a1, a2);
  return result;
}

```

## disassembly

```asm
0x14001d530  mov     [rsp+arg_0], rbx
0x14001d535  push    rdi
0x14001d536  sub     rsp, 20h
0x14001d53a  mov     rbx, rdx
0x14001d53d  mov     rdi, rcx
0x14001d540  call    VmbusTlFindAndReferencePartition
0x14001d545  test    rax, rax
0x14001d548  jnz     short loc_14001D555
0x14001d54a  mov     rdx, rbx
0x14001d54d  mov     rcx, rdi
0x14001d550  call    HvSocketFindAndReferenceUninitializedPartition
0x14001d555  mov     rbx, [rsp+28h+arg_0]
0x14001d55a  add     rsp, 20h
0x14001d55e  pop     rdi
0x14001d55f  retn
```
