# CDelegatingUseCountedObject<NOutermost::CDeviceChild>::LUCCompleteLayerConstruction(void)

- ea: `0x1800029f0`
- end: `0x1800029f5`
- name: `?LUCCompleteLayerConstruction@?$CDelegatingUseCountedObject@VCDeviceChild@NOutermost@@@@UEAAJXZ`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002a00`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CDelegatingUseCountedObject<NOutermost::CDeviceChild>::LUCCompleteLayerConstruction(
        NOutermost::CDeviceChild *a1)
{
  return NOutermost::CDeviceChild::LUCCompleteLayerConstruction(a1);
}

```

## disassembly

```asm
0x1800029f0  jmp     ?LUCCompleteLayerConstruction@CDeviceChild@NOutermost@@UEAAJXZ; NOutermost::CDeviceChild::LUCCompleteLayerConstruction(void)
```
