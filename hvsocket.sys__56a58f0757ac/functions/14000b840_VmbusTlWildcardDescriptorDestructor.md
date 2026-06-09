# VmbusTlWildcardDescriptorDestructor

- ea: `0x14000b840`
- end: `0x14000b864`
- name: `VmbusTlWildcardDescriptorDestructor`
- size: `36`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000b840`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b852`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b852`

## pseudocode

```c
void __fastcall VmbusTlWildcardDescriptorDestructor(__int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 128);
  if ( v1 )
    ExFreePoolWithTag(v1, 0);
}

```

## disassembly

```asm
0x14000b840  sub     rsp, 28h
0x14000b844  mov     rcx, [rcx+80h]; P
0x14000b84b  test    rcx, rcx
0x14000b84e  jz      short loc_14000B85E
0x14000b850  xor     edx, edx; Tag
0x14000b852  call    cs:__imp_ExFreePoolWithTag
0x14000b859  nop     dword ptr [rax+rax+00h]
0x14000b85e  add     rsp, 28h
0x14000b862  retn
```
