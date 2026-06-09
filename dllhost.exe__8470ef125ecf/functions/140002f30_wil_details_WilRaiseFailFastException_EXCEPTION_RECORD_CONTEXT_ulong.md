# wil::details::WilRaiseFailFastException(_EXCEPTION_RECORD *,_CONTEXT *,ulong)

- ea: `0x140002f30`
- end: `0x140002f53`
- name: `?WilRaiseFailFastException@details@wil@@YAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(wil::details *__hidden this, struct _EXCEPTION_RECORD *, struct _CONTEXT *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002e80`

## callees

- `0x140002f30`
- `0x140004010`

## pseudocode

```c
void __fastcall __noreturn wil::details::WilRaiseFailFastException(
        struct _EXCEPTION_RECORD *this,
        struct _EXCEPTION_RECORD *a2,
        struct _CONTEXT *a3)
{
  if ( wil::details::g_pfnRaiseFailFastException )
    wil::details::g_pfnRaiseFailFastException(this, 0, (unsigned int)a3);
  __fastfail(7u);
}

```

## disassembly

```asm
0x140002f30  sub     rsp, 28h
0x140002f34  mov     rax, cs:?g_pfnRaiseFailFastException@details@wil@@3P6AXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@K@ZEA; void (*wil::details::g_pfnRaiseFailFastException)(_EXCEPTION_RECORD *,_CONTEXT *,ulong)
0x140002f3b  test    rax, rax
0x140002f3e  jz      short loc_140002F47
0x140002f40  xor     edx, edx
0x140002f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f47  mov     ecx, 7
0x140002f4c  int     29h; Win8: RtlFailFast(ecx)
0x140002f4e  add     rsp, 28h
0x140002f52  retn
```
