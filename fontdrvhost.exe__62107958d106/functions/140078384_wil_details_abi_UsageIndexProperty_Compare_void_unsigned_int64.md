# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x140078384`
- end: `0x1400783b0`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140075778`
- `0x14007863c`
- `0x140079914`

## callees

- `0x140076ede`
- `0x140078384`

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
0x140078384  sub     rsp, 28h
0x140078388  movzx   eax, word ptr [rcx+8]
0x14007838c  mov     r9, rdx
0x14007838f  cmp     r8, rax
0x140078392  jnz     short loc_1400783A5
0x140078394  mov     rdx, [rcx+18h]; Buf2
0x140078398  mov     rcx, r9; Buf1
0x14007839b  call    memcmp_0
0x1400783a0  mov     r8d, eax
0x1400783a3  jmp     short loc_1400783A8
0x1400783a5  sub     r8d, eax
0x1400783a8  mov     eax, r8d
0x1400783ab  add     rsp, 28h
0x1400783af  retn
```
