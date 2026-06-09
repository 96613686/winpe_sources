# Microsoft::WRL::Details::MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>::~MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>(void)

- ea: `0x18000a9f4`
- end: `0x18000aa0a`
- name: `??1?$MakeAllocator@VEmbeddedModeTaskHost@EmbeddedMode@IoT@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180009b28`
- `0x18000f440`
- `0x18000f4dc`
- `0x1800106fc`
- `0x180011e74`
- `0x18001953b`
- `0x1800199be`

## callees

- `0x180002f84`
- `0x18000a9f4`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>::~MakeAllocator<Microsoft::IoT::EmbeddedMode::EmbeddedModeTaskHost>(
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
0x18000a9f4  sub     rsp, 28h
0x18000a9f8  mov     rcx, [rcx]; Block
0x18000a9fb  test    rcx, rcx
0x18000a9fe  jz      short loc_18000AA05
0x18000aa00  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000aa05  add     rsp, 28h
0x18000aa09  retn
```
