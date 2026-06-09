# CombineIDLists(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x180015994`
- end: `0x1800159b8`
- name: `?CombineIDLists@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z`
- size: `36`
- prototype: `__int64 __fastcall(const struct _ITEMIDLIST_ABSOLUTE *, const struct _ITEMIDLIST_RELATIVE *, struct _ITEMIDLIST_ABSOLUTE **)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001c70`
- `0x180008010`
- `0x180016af0`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x18001599d`
- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x18001599d`

## pseudocode

```c
__int64 __fastcall CombineIDLists(const ITEMIDLIST *a1, const ITEMIDLIST *a2, struct _ITEMIDLIST_ABSOLUTE **a3)
{
  struct _ITEMIDLIST_ABSOLUTE *v4; // rax

  v4 = (struct _ITEMIDLIST_ABSOLUTE *)ILCombine(a1, a2);
  *a3 = v4;
  return v4 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x180015994  push    rbx
0x180015996  sub     rsp, 20h
0x18001599a  mov     rbx, r8
0x18001599d  call    cs:__imp_ILCombine
0x1800159a3  mov     [rbx], rax
0x1800159a6  neg     rax
0x1800159a9  sbb     eax, eax
0x1800159ab  not     eax
0x1800159ad  and     eax, 8007000Eh
0x1800159b2  add     rsp, 20h
0x1800159b6  pop     rbx
0x1800159b7  retn
```
