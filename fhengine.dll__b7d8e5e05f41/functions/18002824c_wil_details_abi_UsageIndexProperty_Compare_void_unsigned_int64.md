# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x18002824c`
- end: `0x180028278`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180028d24`
- `0x18002b1ec`
- `0x18002c1e8`

## callees

- `0x18002824c`
- `0x180031636`

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
0x18002824c  sub     rsp, 28h
0x180028250  movzx   eax, word ptr [rcx+8]
0x180028254  mov     r9, rdx
0x180028257  cmp     r8, rax
0x18002825a  jnz     short loc_18002826D
0x18002825c  mov     rdx, [rcx+18h]; Buf2
0x180028260  mov     rcx, r9; Buf1
0x180028263  call    memcmp_0
0x180028268  mov     r8d, eax
0x18002826b  jmp     short loc_180028270
0x18002826d  sub     r8d, eax
0x180028270  mov     eax, r8d
0x180028273  add     rsp, 28h
0x180028277  retn
```
