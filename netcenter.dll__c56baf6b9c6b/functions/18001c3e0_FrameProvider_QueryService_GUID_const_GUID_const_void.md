# FrameProvider::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x18001c3e0`
- end: `0x18001c3eb`
- name: `?QueryService@FrameProvider@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `11`
- prototype: `__int64 __fastcall(FrameProvider *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001c3e4`

## pseudocode

```c
HRESULT __fastcall FrameProvider::QueryService(
        IUnknown **this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  return IUnknown_QueryService(this[1], a2, a3, a4);
}

```

## disassembly

```asm
0x18001c3e0  mov     rcx, [rcx+8]
0x18001c3e4  jmp     cs:__imp_IUnknown_QueryService
```
