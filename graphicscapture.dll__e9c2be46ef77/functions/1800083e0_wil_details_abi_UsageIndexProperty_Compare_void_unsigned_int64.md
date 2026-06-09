# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x1800083e0`
- end: `0x18000840c`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008778`
- `0x180009b0c`
- `0x18000aa88`

## callees

- `0x1800022c2`
- `0x1800083e0`

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
0x1800083e0  sub     rsp, 28h
0x1800083e4  movzx   eax, word ptr [rcx+8]
0x1800083e8  mov     r9, rdx
0x1800083eb  cmp     r8, rax
0x1800083ee  jnz     short loc_180008401
0x1800083f0  mov     rdx, [rcx+18h]; Buf2
0x1800083f4  mov     rcx, r9; Buf1
0x1800083f7  call    memcmp_0
0x1800083fc  mov     r8d, eax
0x1800083ff  jmp     short loc_180008404
0x180008401  sub     r8d, eax
0x180008404  mov     eax, r8d
0x180008407  add     rsp, 28h
0x18000840b  retn
```
