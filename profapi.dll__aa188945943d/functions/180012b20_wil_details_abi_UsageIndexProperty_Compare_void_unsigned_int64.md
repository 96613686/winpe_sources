# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180012b20`
- end: `0x180012b4c`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f2e4`
- `0x180012d18`
- `0x1800146fc`

## callees

- `0x180012b20`
- `0x1800170a0`

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
0x180012b20  sub     rsp, 28h
0x180012b24  movzx   eax, word ptr [rcx+8]
0x180012b28  mov     r9, rdx
0x180012b2b  cmp     r8, rax
0x180012b2e  jnz     short loc_180012B41
0x180012b30  mov     rdx, [rcx+18h]; Buf2
0x180012b34  mov     rcx, r9; Buf1
0x180012b37  call    memcmp_0
0x180012b3c  mov     r8d, eax
0x180012b3f  jmp     short loc_180012B44
0x180012b41  sub     r8d, eax
0x180012b44  mov     eax, r8d
0x180012b47  add     rsp, 28h
0x180012b4b  retn
```
