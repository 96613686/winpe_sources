# _bstr_t::_Compare(_bstr_t const &)

- ea: `0x140006ac8`
- end: `0x140006aed`
- name: `?_Compare@_bstr_t@@AEBAHAEBV1@@Z`
- size: `37`
- prototype: `__int64 __fastcall(_bstr_t::Data_t **this, const struct _bstr_t::Data_t **)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000741c`
- `0x140009550`
- `0x14000a434`
- `0x14000a4d4`
- `0x14000fbcc`
- `0x14000fe40`

## callees

- `0x140006138`
- `0x140006ac8`

## pseudocode

```c
__int64 __fastcall _bstr_t::_Compare(_bstr_t::Data_t **this, const struct _bstr_t::Data_t **a2)
{
  const struct _bstr_t::Data_t *v2; // rdx
  _bstr_t::Data_t *v3; // rcx

  v2 = *a2;
  v3 = *this;
  if ( v3 == v2 )
    return 0;
  if ( !v3 )
    return 0xFFFFFFFFLL;
  if ( v2 )
    return _bstr_t::Data_t::Compare(v3, v2);
  return 1;
}

```

## disassembly

```asm
0x140006ac8  mov     rdx, [rdx]; struct _bstr_t::Data_t *
0x140006acb  mov     rcx, [rcx]; this
0x140006ace  cmp     rcx, rdx
0x140006ad1  jnz     short loc_140006AD6
0x140006ad3  xor     eax, eax
0x140006ad5  retn
0x140006ad6  test    rcx, rcx
0x140006ad9  jnz     short loc_140006ADF
0x140006adb  or      eax, 0FFFFFFFFh
0x140006ade  retn
0x140006adf  test    rdx, rdx
0x140006ae2  jnz     short loc_140006AE8
0x140006ae4  lea     eax, [rdx+1]
0x140006ae7  retn
0x140006ae8  jmp     ?Compare@Data_t@_bstr_t@@QEBAHAEBV12@@Z; _bstr_t::Data_t::Compare(_bstr_t::Data_t const &)
```
