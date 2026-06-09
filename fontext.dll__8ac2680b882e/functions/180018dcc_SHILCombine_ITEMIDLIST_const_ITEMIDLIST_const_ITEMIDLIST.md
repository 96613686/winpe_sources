# SHILCombine(_ITEMIDLIST const *,_ITEMIDLIST const *,_ITEMIDLIST * *)

- ea: `0x180018dcc`
- end: `0x180018df0`
- name: `?SHILCombine@@YAJPEFBU_ITEMIDLIST@@0PEAPEFAU1@@Z`
- size: `36`
- prototype: `__int64 __fastcall(const struct _ITEMIDLIST *, const struct _ITEMIDLIST *, struct _ITEMIDLIST **)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180017a70`
- `0x18001a8b4`
- `0x1800300b0`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x180018dd5`
- `SHELL32!__imp_ILCombine` at `0x180018dd5`

## pseudocode

```c
__int64 __fastcall SHILCombine(const struct _ITEMIDLIST *a1, const struct _ITEMIDLIST *a2, struct _ITEMIDLIST **a3)
{
  struct _ITEMIDLIST *v4; // rax

  v4 = ILCombine(a1, a2);
  *a3 = v4;
  return v4 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x180018dcc  push    rbx
0x180018dce  sub     rsp, 20h
0x180018dd2  mov     rbx, r8
0x180018dd5  call    cs:__imp_ILCombine
0x180018ddb  mov     [rbx], rax
0x180018dde  neg     rax
0x180018de1  sbb     eax, eax
0x180018de3  not     eax
0x180018de5  and     eax, 8007000Eh
0x180018dea  add     rsp, 20h
0x180018dee  pop     rbx
0x180018def  retn
```
