# ShortcutSerialization::s_SetLinkPropertyDwordValue(IPropertyStore *,_tagpropertykey const &,ulong)

- ea: `0x18001806c`
- end: `0x1800180b6`
- name: `?s_SetLinkPropertyDwordValue@ShortcutSerialization@@CAXPEAUIPropertyStore@@AEBU_tagpropertykey@@K@Z`
- size: `74`
- prototype: `void __fastcall(struct IPropertyStore *, const struct _tagpropertykey *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800180bc`

## callees

- `0x18001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800180a4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800180a4`

## pseudocode

```c
void __fastcall ShortcutSerialization::s_SetLinkPropertyDwordValue(
        struct IPropertyStore *a1,
        const struct _tagpropertykey *a2,
        LONG a3)
{
  struct IPropertyStoreVtbl *lpVtbl; // rax
  PROPVARIANT pvar; // [rsp+20h] [rbp-28h] BYREF

  memset(&pvar, 0, sizeof(pvar));
  pvar.vt = 19;
  lpVtbl = a1->lpVtbl;
  pvar.lVal = a3;
  ((void (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, PROPVARIANT *))lpVtbl->SetValue)(
    a1,
    a2,
    &pvar);
  PropVariantClear(&pvar);
}

```

## disassembly

```asm
0x18001806c  sub     rsp, 48h
0x180018070  xor     eax, eax
0x180018072  xorps   xmm0, xmm0
0x180018075  mov     qword ptr [rsp+48h+pvar+10h], rax
0x18001807a  mov     eax, 13h
0x18001807f  movups  xmmword ptr [rsp+48h+pvar], xmm0
0x180018084  mov     word ptr [rsp+48h+pvar], ax
0x180018089  mov     rax, [rcx]
0x18001808c  mov     dword ptr [rsp+48h+pvar+8], r8d
0x180018091  lea     r8, [rsp+48h+pvar]
0x180018096  mov     rax, [rax+30h]
0x18001809a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001809f  lea     rcx, [rsp+48h+pvar]; pvar
0x1800180a4  call    cs:__imp_PropVariantClear
0x1800180ab  nop     dword ptr [rax+rax+00h]
0x1800180b0  add     rsp, 48h
0x1800180b4  retn
```
