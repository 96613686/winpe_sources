# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180012964`
- end: `0x180012990`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b164`
- `0x180012d60`
- `0x180014148`

## callees

- `0x180012964`
- `0x18001891c`

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
0x180012964  sub     rsp, 28h
0x180012968  movzx   eax, word ptr [rcx+8]
0x18001296c  mov     r9, rdx
0x18001296f  cmp     r8, rax
0x180012972  jnz     short loc_180012985
0x180012974  mov     rdx, [rcx+18h]; Buf2
0x180012978  mov     rcx, r9; Buf1
0x18001297b  call    memcmp_0
0x180012980  mov     r8d, eax
0x180012983  jmp     short loc_180012988
0x180012985  sub     r8d, eax
0x180012988  mov     eax, r8d
0x18001298b  add     rsp, 28h
0x18001298f  retn
```
