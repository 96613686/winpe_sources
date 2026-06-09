# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x18000e8bc`
- end: `0x18000e8e8`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000cbec`
- `0x18000ec44`
- `0x18000f48c`

## callees

- `0x18000dda0`
- `0x18000e8bc`

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
0x18000e8bc  sub     rsp, 28h
0x18000e8c0  movzx   eax, word ptr [rcx+8]
0x18000e8c4  mov     r9, rdx
0x18000e8c7  cmp     r8, rax
0x18000e8ca  jnz     short loc_18000E8DD
0x18000e8cc  mov     rdx, [rcx+18h]; Buf2
0x18000e8d0  mov     rcx, r9; Buf1
0x18000e8d3  call    memcmp_0
0x18000e8d8  mov     r8d, eax
0x18000e8db  jmp     short loc_18000E8E0
0x18000e8dd  sub     r8d, eax
0x18000e8e0  mov     eax, r8d
0x18000e8e3  add     rsp, 28h
0x18000e8e7  retn
```
