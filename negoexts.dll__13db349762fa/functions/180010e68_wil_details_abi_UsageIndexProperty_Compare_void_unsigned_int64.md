# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180010e68`
- end: `0x180010e94`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e338`
- `0x180011258`
- `0x1800128f8`

## callees

- `0x180010e68`
- `0x18001ecd6`

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
0x180010e68  sub     rsp, 28h
0x180010e6c  movzx   eax, word ptr [rcx+8]
0x180010e70  mov     r9, rdx
0x180010e73  cmp     r8, rax
0x180010e76  jnz     short loc_180010E89
0x180010e78  mov     rdx, [rcx+18h]; Buf2
0x180010e7c  mov     rcx, r9; Buf1
0x180010e7f  call    memcmp_0
0x180010e84  mov     r8d, eax
0x180010e87  jmp     short loc_180010E8C
0x180010e89  sub     r8d, eax
0x180010e8c  mov     eax, r8d
0x180010e8f  add     rsp, 28h
0x180010e93  retn
```
