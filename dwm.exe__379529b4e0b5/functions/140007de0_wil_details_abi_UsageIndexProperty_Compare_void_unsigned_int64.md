# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x140007de0`
- end: `0x140007e0c`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004ee0`
- `0x140008660`
- `0x1400097a4`

## callees

- `0x140006959`
- `0x140007de0`

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
0x140007de0  sub     rsp, 28h
0x140007de4  movzx   eax, word ptr [rcx+8]
0x140007de8  mov     r9, rdx
0x140007deb  cmp     r8, rax
0x140007dee  jnz     short loc_140007E01
0x140007df0  mov     rdx, [rcx+18h]; Buf2
0x140007df4  mov     rcx, r9; Buf1
0x140007df7  call    memcmp_0
0x140007dfc  mov     r8d, eax
0x140007dff  jmp     short loc_140007E04
0x140007e01  sub     r8d, eax
0x140007e04  mov     eax, r8d
0x140007e07  add     rsp, 28h
0x140007e0b  retn
```
