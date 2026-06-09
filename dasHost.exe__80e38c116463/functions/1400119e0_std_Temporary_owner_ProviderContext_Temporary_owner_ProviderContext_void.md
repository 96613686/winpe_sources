# std::_Temporary_owner<ProviderContext>::~_Temporary_owner<ProviderContext>(void)

- ea: `0x1400119e0`
- end: `0x140011a09`
- name: `??1?$_Temporary_owner@VProviderContext@@@std@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(ProviderContext **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14001af46`

## callees

- `0x1400018d4`
- `0x1400119e0`
- `0x140014b60`

## pseudocode

```c
void __fastcall std::_Temporary_owner<ProviderContext>::~_Temporary_owner<ProviderContext>(ProviderContext **a1)
{
  ProviderContext *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    ProviderContext::~ProviderContext(*a1);
    operator delete(v1, 0xA0u);
  }
}

```

## disassembly

```asm
0x1400119e0  push    rbx
0x1400119e2  sub     rsp, 20h
0x1400119e6  mov     rbx, [rcx]
0x1400119e9  test    rbx, rbx
0x1400119ec  jz      short loc_140011A03
0x1400119ee  mov     rcx, rbx; this
0x1400119f1  call    ??1ProviderContext@@QEAA@XZ; ProviderContext::~ProviderContext(void)
0x1400119f6  mov     edx, 0A0h; unsigned __int64
0x1400119fb  mov     rcx, rbx; void *
0x1400119fe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011a03  add     rsp, 20h
0x140011a07  pop     rbx
0x140011a08  retn
```
