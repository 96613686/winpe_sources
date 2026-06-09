# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180003fdc`
- end: `0x180004008`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800042a8`
- `0x18000551c`
- `0x18000635c`

## callees

- `0x180003fdc`
- `0x180023c42`

## pseudocode

```c
__int64 __fastcall wil::details_abi::UsageIndexProperty::Compare(const void **this, void *a2, size_t a3)
{
  __int64 v3; // rax

  v3 = *((unsigned __int16 *)this + 4);
  if ( a3 == v3 )
    return (unsigned int)memcmp_0(a2, this[3], a3);
  else
    return (unsigned int)(a3 - v3);
}

```

## disassembly

```asm
0x180003fdc  sub     rsp, 28h
0x180003fe0  movzx   eax, word ptr [rcx+8]
0x180003fe4  mov     r9, rdx
0x180003fe7  cmp     r8, rax
0x180003fea  jnz     short loc_180003FFD
0x180003fec  mov     rdx, [rcx+18h]; Buf2
0x180003ff0  mov     rcx, r9; Buf1
0x180003ff3  call    memcmp_0
0x180003ff8  mov     r8d, eax
0x180003ffb  jmp     short loc_180004000
0x180003ffd  sub     r8d, eax
0x180004000  mov     eax, r8d
0x180004003  add     rsp, 28h
0x180004007  retn
```
