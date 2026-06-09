# XMLScrServProv::~XMLScrServProv(void)

- ea: `0x1400111a0`
- end: `0x1400111c8`
- name: `??1XMLScrServProv@@AEAA@XZ`
- size: `40`
- prototype: `void __fastcall(XMLScrServProv *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400118f0`

## callees

- `0x1400111a0`
- `0x140017010`

## pseudocode

```c
void __fastcall XMLScrServProv::~XMLScrServProv(XMLScrServProv *this)
{
  __int64 v1; // rcx

  *(_QWORD *)this = &XMLScrServProv::`vftable';
  v1 = *((_QWORD *)this + 1);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x1400111a0  sub     rsp, 28h
0x1400111a4  lea     rax, ??_7XMLScrServProv@@6B@; const XMLScrServProv::`vftable'
0x1400111ab  mov     [rcx], rax
0x1400111ae  mov     rcx, [rcx+8]
0x1400111b2  test    rcx, rcx
0x1400111b5  jz      short loc_1400111C3
0x1400111b7  mov     rax, [rcx]
0x1400111ba  mov     rax, [rax+10h]
0x1400111be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400111c3  add     rsp, 28h
0x1400111c7  retn
```
