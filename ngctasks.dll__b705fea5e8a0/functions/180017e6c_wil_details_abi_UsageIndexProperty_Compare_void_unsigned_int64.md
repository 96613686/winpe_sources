# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180017e6c`
- end: `0x180017e98`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018460`
- `0x180018d4c`
- `0x180019938`

## callees

- `0x180007345`
- `0x180017e6c`

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
0x180017e6c  sub     rsp, 28h
0x180017e70  movzx   eax, word ptr [rcx+8]
0x180017e74  mov     r9, rdx
0x180017e77  cmp     r8, rax
0x180017e7a  jnz     short loc_180017E8D
0x180017e7c  mov     rdx, [rcx+18h]; Buf2
0x180017e80  mov     rcx, r9; Buf1
0x180017e83  call    memcmp_0
0x180017e88  mov     r8d, eax
0x180017e8b  jmp     short loc_180017E90
0x180017e8d  sub     r8d, eax
0x180017e90  mov     eax, r8d
0x180017e93  add     rsp, 28h
0x180017e97  retn
```
