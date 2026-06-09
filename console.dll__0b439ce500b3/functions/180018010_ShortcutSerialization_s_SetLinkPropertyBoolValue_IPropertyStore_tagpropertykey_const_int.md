# ShortcutSerialization::s_SetLinkPropertyBoolValue(IPropertyStore *,_tagpropertykey const &,int)

- ea: `0x180018010`
- end: `0x180018066`
- name: `?s_SetLinkPropertyBoolValue@ShortcutSerialization@@CAXPEAUIPropertyStore@@AEBU_tagpropertykey@@H@Z`
- size: `86`
- prototype: `void __fastcall(struct IPropertyStore *, const struct _tagpropertykey *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800180bc`

## callees

- `0x180018010`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180018054`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180018054`

## pseudocode

```c
void __fastcall ShortcutSerialization::s_SetLinkPropertyBoolValue(
        struct IPropertyStore *a1,
        const struct _tagpropertykey *a2,
        int a3)
{
  SHORT v3; // ax
  PROPVARIANT pvar; // [rsp+20h] [rbp-28h] BYREF

  memset(&pvar, 0, sizeof(pvar));
  pvar.vt = 11;
  if ( a3 )
    v3 = -1;
  else
    v3 = 0;
  pvar.iVal = v3;
  ((void (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, PROPVARIANT *))a1->lpVtbl->SetValue)(
    a1,
    a2,
    &pvar);
  PropVariantClear(&pvar);
}

```

## disassembly

```asm
0x180018010  sub     rsp, 48h
0x180018014  xor     eax, eax
0x180018016  xorps   xmm0, xmm0
0x180018019  mov     qword ptr [rsp+48h+pvar+10h], rax
0x18001801e  mov     eax, 0Bh
0x180018023  movups  xmmword ptr [rsp+48h+pvar], xmm0
0x180018028  mov     word ptr [rsp+48h+pvar], ax
0x18001802d  test    r8d, r8d
0x180018030  jz      short loc_180018037
0x180018032  or      eax, 0FFFFFFFFh
0x180018035  jmp     short loc_180018039
0x180018037  xor     eax, eax
0x180018039  mov     word ptr [rsp+48h+pvar+8], ax
0x18001803e  lea     r8, [rsp+48h+pvar]
0x180018043  mov     rax, [rcx]
0x180018046  mov     rax, [rax+30h]
0x18001804a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001804f  lea     rcx, [rsp+48h+pvar]; pvar
0x180018054  call    cs:__imp_PropVariantClear
0x18001805b  nop     dword ptr [rax+rax+00h]
0x180018060  add     rsp, 48h
0x180018064  retn
```
