# Microsoft::WRL::ComPtr<ID3D12CommandAllocator>::~ComPtr<ID3D12CommandAllocator>(void)

- ea: `0x18001ff00`
- end: `0x18001ff05`
- name: `??1?$ComPtr@UID3D12CommandAllocator@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `void(void *)`
- caller_count: `29`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18006f292`
- `0x18006f2a4`
- `0x18006f2ba`
- `0x18006f2d0`
- `0x18006f2e6`
- `0x18006f2fc`
- `0x18006f312`
- `0x18006f33e`
- `0x18006f354`
- `0x18006f392`
- `0x18006f3c8`
- `0x18006f3da`
- `0x18006f458`
- `0x18006f510`
- `0x18006f6d3`
- `0x18006f7ab`
- `0x18006f7c1`
- `0x18006f886`
- `0x18006f89f`
- `0x18006f8b8`
- `0x18006f987`
- `0x18006f9ab`
- `0x18006fa3b`
- `0x18006fa4d`
- `0x18006fa83`
- `0x18006fab9`
- `0x18006fce3`
- `0x18006fd07`
- `0x18006fd4f`

## callees

- `0x180020598`

## pseudocode

```c
// attributes: thunk
void __fastcall Microsoft::WRL::ComPtr<ID3D12CommandAllocator>::~ComPtr<ID3D12CommandAllocator>(__int64 *a1)
{
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
}

```

## disassembly

```asm
0x18001ff00  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
