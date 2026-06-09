# Microsoft::WRL::Details::MakeAllocator<CapabilityAccessHelper>::~MakeAllocator<CapabilityAccessHelper>(void)

- ea: `0x18001cb94`
- end: `0x18001cbab`
- name: `??1?$MakeAllocator@VCapabilityAccessHelper@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001222c`
- `0x180042a8c`
- `0x180042b4c`

## callees

- `0x18001cb94`
- `0x18001f21c`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::MakeAllocator<CapabilityAccessHelper>::~MakeAllocator<CapabilityAccessHelper>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18001cb94  sub     rsp, 28h
0x18001cb98  mov     rcx, [rcx]; void *
0x18001cb9b  test    rcx, rcx
0x18001cb9e  jz      short loc_18001CBA5
0x18001cba0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cba5  add     rsp, 28h
0x18001cba9  retn
```
