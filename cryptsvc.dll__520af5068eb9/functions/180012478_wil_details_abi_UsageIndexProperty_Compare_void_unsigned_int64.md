# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180012478`
- end: `0x1800124a4`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dc00`
- `0x18001278c`
- `0x180013ed4`

## callees

- `0x180012478`
- `0x1800174f0`

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
0x180012478  sub     rsp, 28h
0x18001247c  movzx   eax, word ptr [rcx+8]
0x180012480  mov     r9, rdx
0x180012483  cmp     r8, rax
0x180012486  jnz     short loc_180012499
0x180012488  mov     rdx, [rcx+18h]; Buf2
0x18001248c  mov     rcx, r9; Buf1
0x18001248f  call    memcmp_0
0x180012494  mov     r8d, eax
0x180012497  jmp     short loc_18001249C
0x180012499  sub     r8d, eax
0x18001249c  mov     eax, r8d
0x18001249f  add     rsp, 28h
0x1800124a3  retn
```
