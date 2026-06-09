# _ThumbnailClassFactory::CreateInstance_::_1_::dtor$2

- ea: `0x18000a453`
- end: `0x18000a45f`
- name: `_ThumbnailClassFactory::CreateInstance_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002b98`

## pseudocode

```c
__int64 __fastcall ThumbnailClassFactory::CreateInstance_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::Details::MakeAllocator<Ext3MFThumbnailProvider>::~MakeAllocator<Ext3MFThumbnailProvider>(a2 + 40);
}

```

## disassembly

```asm
0x18000a453  lea     rcx, [rdx+28h]
0x18000a45a  jmp     ??1?$MakeAllocator@VExt3MFThumbnailProvider@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Ext3MFThumbnailProvider>::~MakeAllocator<Ext3MFThumbnailProvider>(void)
```
