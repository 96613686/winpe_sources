# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180005fa4`
- end: `0x180005fd0`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003958`
- `0x180006250`
- `0x1800074e4`

## callees

- `0x180005fa4`
- `0x18000ac76`

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
0x180005fa4  sub     rsp, 28h
0x180005fa8  movzx   eax, word ptr [rcx+8]
0x180005fac  mov     r9, rdx
0x180005faf  cmp     r8, rax
0x180005fb2  jnz     short loc_180005FC5
0x180005fb4  mov     rdx, [rcx+18h]; Buf2
0x180005fb8  mov     rcx, r9; Buf1
0x180005fbb  call    memcmp_0
0x180005fc0  mov     r8d, eax
0x180005fc3  jmp     short loc_180005FC8
0x180005fc5  sub     r8d, eax
0x180005fc8  mov     eax, r8d
0x180005fcb  add     rsp, 28h
0x180005fcf  retn
```
