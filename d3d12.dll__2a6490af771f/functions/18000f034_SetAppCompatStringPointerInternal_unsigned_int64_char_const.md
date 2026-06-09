# SetAppCompatStringPointerInternal(unsigned __int64,char const *)

- ea: `0x18000f034`
- end: `0x18000f039`
- name: `?SetAppCompatStringPointerInternal@@YAX_KPEBD@Z`
- size: `5`
- prototype: `void __fastcall(unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000efc0`

## callees

- `0x180010fb4`

## pseudocode

```c
// attributes: thunk
void __fastcall SetAppCompatStringPointerInternal(DxgAppCompat *a1, const char *a2, const char *a3)
{
  DxgAppCompat::SetAppCompatStringPointerImpl(a1, (unsigned __int64)a2, a3);
}

```

## disassembly

```asm
0x18000f034  jmp     ?SetAppCompatStringPointerImpl@DxgAppCompat@@YAX_KPEBD@Z; DxgAppCompat::SetAppCompatStringPointerImpl(unsigned __int64,char const *)
```
