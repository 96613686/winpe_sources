# [thunk]:Shell3DPrintClassFactory::CreateInstance`adjustor{8}' (IUnknown *,_GUID const &,void * *)

- ea: `0x1800033f0`
- end: `0x1800033f9`
- name: `?CreateInstance@Shell3DPrintClassFactory@@W7EAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002df0`

## pseudocode

```c
__int64 __fastcall Shell3DPrintClassFactory::CreateInstance(
        __int64 a1,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  return Shell3DPrintClassFactory::CreateInstance((Shell3DPrintClassFactory *)(a1 - 8), a2, a3, a4);
}

```

## disassembly

```asm
0x1800033f0  sub     rcx, 8; this
0x1800033f4  jmp     ?CreateInstance@Shell3DPrintClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; Shell3DPrintClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)
```
