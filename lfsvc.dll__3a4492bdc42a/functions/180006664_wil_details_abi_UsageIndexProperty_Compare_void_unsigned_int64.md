# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180006664`
- end: `0x180006690`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800035a4`
- `0x180006954`
- `0x180007bcc`

## callees

- `0x180006664`
- `0x18000b3b4`

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
0x180006664  sub     rsp, 28h
0x180006668  movzx   eax, word ptr [rcx+8]
0x18000666c  mov     r9, rdx
0x18000666f  cmp     r8, rax
0x180006672  jnz     short loc_180006685
0x180006674  mov     rdx, [rcx+18h]; Buf2
0x180006678  mov     rcx, r9; Buf1
0x18000667b  call    memcmp_0
0x180006680  mov     r8d, eax
0x180006683  jmp     short loc_180006688
0x180006685  sub     r8d, eax
0x180006688  mov     eax, r8d
0x18000668b  add     rsp, 28h
0x18000668f  retn
```
