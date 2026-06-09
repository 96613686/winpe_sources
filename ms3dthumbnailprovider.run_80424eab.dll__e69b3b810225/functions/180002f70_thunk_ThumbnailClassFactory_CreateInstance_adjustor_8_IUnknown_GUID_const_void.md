# [thunk]:ThumbnailClassFactory::CreateInstance`adjustor{8}' (IUnknown *,_GUID const &,void * *)

- ea: `0x180002f70`
- end: `0x180002f79`
- name: `?CreateInstance@ThumbnailClassFactory@@W7EAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002e80`

## pseudocode

```c
__int64 __fastcall ThumbnailClassFactory::CreateInstance(
        __int64 a1,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  return ThumbnailClassFactory::CreateInstance((ThumbnailClassFactory *)(a1 - 8), a2, a3, a4);
}

```

## disassembly

```asm
0x180002f70  sub     rcx, 8; this
0x180002f74  jmp     ?CreateInstance@ThumbnailClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; ThumbnailClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)
```
