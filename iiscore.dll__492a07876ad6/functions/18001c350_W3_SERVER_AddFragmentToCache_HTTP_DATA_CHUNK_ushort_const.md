# W3_SERVER::AddFragmentToCache(_HTTP_DATA_CHUNK *,ushort const *)

- ea: `0x18001c350`
- end: `0x18001c35d`
- name: `?AddFragmentToCache@W3_SERVER@@UEAAJPEAU_HTTP_DATA_CHUNK@@PEBG@Z`
- size: `13`
- prototype: `__int64 __fastcall(W3_SERVER *__hidden this, struct _HTTP_DATA_CHUNK *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `w3dt!UlAtqAddFragmentToCache` at `0x18001c356`

## pseudocode

```c
int __fastcall W3_SERVER::AddFragmentToCache(W3_SERVER *this, struct _HTTP_DATA_CHUNK *a2, const unsigned __int16 *a3)
{
  return UlAtqAddFragmentToCache(a2, a3);
}

```

## disassembly

```asm
0x18001c350  mov     rcx, rdx
0x18001c353  mov     rdx, r8
0x18001c356  jmp     cs:__imp_?UlAtqAddFragmentToCache@@YAJPEAU_HTTP_DATA_CHUNK@@PEBG@Z; UlAtqAddFragmentToCache(_HTTP_DATA_CHUNK *,ushort const *)
```
