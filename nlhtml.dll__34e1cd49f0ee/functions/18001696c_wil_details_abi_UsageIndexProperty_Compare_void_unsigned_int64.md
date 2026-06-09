# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x18001696c`
- end: `0x180016998`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016d78`
- `0x180017e0c`
- `0x180018cc8`

## callees

- `0x18001696c`
- `0x18002337c`

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
0x18001696c  sub     rsp, 28h
0x180016970  movzx   eax, word ptr [rcx+8]
0x180016974  mov     r9, rdx
0x180016977  cmp     r8, rax
0x18001697a  jnz     short loc_18001698D
0x18001697c  mov     rdx, [rcx+18h]; Buf2
0x180016980  mov     rcx, r9; Buf1
0x180016983  call    memcmp_0
0x180016988  mov     r8d, eax
0x18001698b  jmp     short loc_180016990
0x18001698d  sub     r8d, eax
0x180016990  mov     eax, r8d
0x180016993  add     rsp, 28h
0x180016997  retn
```
