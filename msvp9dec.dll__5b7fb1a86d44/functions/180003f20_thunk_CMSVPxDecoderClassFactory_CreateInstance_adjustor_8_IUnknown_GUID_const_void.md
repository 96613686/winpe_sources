# [thunk]:CMSVPxDecoderClassFactory::CreateInstance`adjustor{8}' (IUnknown *,_GUID const &,void * *)

- ea: `0x180003f20`
- end: `0x180003f29`
- name: `?CreateInstance@CMSVPxDecoderClassFactory@@W7EAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180003ad0`

## pseudocode

```c
__int64 __fastcall CMSVPxDecoderClassFactory::CreateInstance(
        __int64 a1,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  return CMSVPxDecoderClassFactory::CreateInstance((CMSVPxDecoderClassFactory *)(a1 - 8), a2, a3, a4);
}

```

## disassembly

```asm
0x180003f20  sub     rcx, 8; this
0x180003f24  jmp     ?CreateInstance@CMSVPxDecoderClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CMSVPxDecoderClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)
```
