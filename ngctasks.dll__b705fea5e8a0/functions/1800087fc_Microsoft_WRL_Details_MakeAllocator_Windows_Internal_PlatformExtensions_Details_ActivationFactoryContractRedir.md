# Microsoft::WRL::Details::MakeAllocator<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext>::~MakeAllocator<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext>(void)

- ea: `0x1800087fc`
- end: `0x180008812`
- name: `??1?$MakeAllocator@VActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800075d0`
- `0x1800076a4`
- `0x18001eb86`
- `0x18001ebd2`

## callees

- `0x180006314`
- `0x1800087fc`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::MakeAllocator<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext>::~MakeAllocator<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext>(
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
0x1800087fc  sub     rsp, 28h
0x180008800  mov     rcx, [rcx]; Block
0x180008803  test    rcx, rcx
0x180008806  jz      short loc_18000880D
0x180008808  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000880d  add     rsp, 28h
0x180008811  retn
```
