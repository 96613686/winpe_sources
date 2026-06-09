# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180003bd4`
- end: `0x180003c00`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003f14`
- `0x18000517c`
- `0x180005dd4`

## callees

- `0x180003bd4`
- `0x18001a596`

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
0x180003bd4  sub     rsp, 28h
0x180003bd8  movzx   eax, word ptr [rcx+8]
0x180003bdc  mov     r9, rdx
0x180003bdf  cmp     r8, rax
0x180003be2  jnz     short loc_180003BF5
0x180003be4  mov     rdx, [rcx+18h]; Buf2
0x180003be8  mov     rcx, r9; Buf1
0x180003beb  call    memcmp_0
0x180003bf0  mov     r8d, eax
0x180003bf3  jmp     short loc_180003BF8
0x180003bf5  sub     r8d, eax
0x180003bf8  mov     eax, r8d
0x180003bfb  add     rsp, 28h
0x180003bff  retn
```
