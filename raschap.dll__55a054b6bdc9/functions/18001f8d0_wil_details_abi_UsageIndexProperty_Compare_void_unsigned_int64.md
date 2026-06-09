# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x18001f8d0`
- end: `0x18001f8fc`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011d74`
- `0x18001fc70`
- `0x180020ca8`

## callees

- `0x18001f8d0`
- `0x180025ef0`

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
0x18001f8d0  sub     rsp, 28h
0x18001f8d4  movzx   eax, word ptr [rcx+8]
0x18001f8d8  mov     r9, rdx
0x18001f8db  cmp     r8, rax
0x18001f8de  jnz     short loc_18001F8F1
0x18001f8e0  mov     rdx, [rcx+18h]; Buf2
0x18001f8e4  mov     rcx, r9; Buf1
0x18001f8e7  call    memcmp_0
0x18001f8ec  mov     r8d, eax
0x18001f8ef  jmp     short loc_18001F8F4
0x18001f8f1  sub     r8d, eax
0x18001f8f4  mov     eax, r8d
0x18001f8f7  add     rsp, 28h
0x18001f8fb  retn
```
