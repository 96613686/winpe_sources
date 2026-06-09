# operator delete(void *)

- ea: `0x180003f50`
- end: `0x180003f6f`
- name: `??3@YAXPEAX@Z`
- size: `31`
- prototype: `void __fastcall(void *)`
- caller_count: `236`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180001920`
- `0x180004d50`
- `0x180007e80`
- `0x1800163cc`
- `0x18001720c`
- `0x18001abb4`
- `0x18001e0a0`
- `0x180023db0`
- `0x180023de0`
- `0x180023e20`
- `0x180023e58`
- `0x180023f58`
- `0x180024fe0`
- `0x180025964`
- `0x180025a60`
- `0x180025aa0`
- `0x180025b7c`
- `0x180026304`
- `0x180026c04`
- `0x180028cd0`
- `0x180028d10`
- `0x180028d50`
- `0x180028d90`
- `0x180028dc8`
- `0x180028e00`
- `0x180028e30`
- `0x180028e60`
- `0x180028ea0`
- `0x180028ee0`
- `0x180028f20`
- `0x180028f60`
- `0x180028fa0`
- `0x18002926c`
- `0x180029340`
- `0x18002986c`
- `0x18002a590`
- `0x18002b3c4`
- `0x18002b418`
- `0x18002b720`
- `0x18002b758`
- `0x18002b790`
- `0x18002b7d0`
- `0x18002b808`
- `0x18002b840`
- `0x18002b880`
- `0x18002cc2c`
- `0x18002da80`
- `0x18002dc8c`
- `0x18002dcbc`
- `0x18002de0c`

## callees

- `0x180003f50`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180003f67`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  if ( a1 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x180003f50  test    rcx, rcx
0x180003f53  jz      short locret_180003F6E
0x180003f55  mov     rax, gs:60h
0x180003f5e  mov     r8, rcx
0x180003f61  xor     edx, edx
0x180003f63  mov     rcx, [rax+30h]
0x180003f67  jmp     cs:__imp_RtlFreeHeap
0x180003f6e  retn
```
