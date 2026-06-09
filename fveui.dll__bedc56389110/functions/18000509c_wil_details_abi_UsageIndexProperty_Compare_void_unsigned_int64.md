# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x18000509c`
- end: `0x1800050c8`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800087e4`
- `0x180009d48`
- `0x18000ac18`

## callees

- `0x18000509c`
- `0x18002c230`

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
0x18000509c  sub     rsp, 28h
0x1800050a0  movzx   eax, word ptr [rcx+8]
0x1800050a4  mov     r9, rdx
0x1800050a7  cmp     r8, rax
0x1800050aa  jnz     short loc_1800050BD
0x1800050ac  mov     rdx, [rcx+18h]; Buf2
0x1800050b0  mov     rcx, r9; Buf1
0x1800050b3  call    memcmp_0
0x1800050b8  mov     r8d, eax
0x1800050bb  jmp     short loc_1800050C0
0x1800050bd  sub     r8d, eax
0x1800050c0  mov     eax, r8d
0x1800050c3  add     rsp, 28h
0x1800050c7  retn
```
