# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x1400073c8`
- end: `0x1400073f4`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007778`
- `0x140007d0c`
- `0x140008dc8`

## callees

- `0x1400073c8`
- `0x1400176dc`

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
0x1400073c8  sub     rsp, 28h
0x1400073cc  movzx   eax, word ptr [rcx+8]
0x1400073d0  mov     r9, rdx
0x1400073d3  cmp     r8, rax
0x1400073d6  jnz     short loc_1400073E9
0x1400073d8  mov     rdx, [rcx+18h]; Buf2
0x1400073dc  mov     rcx, r9; Buf1
0x1400073df  call    memcmp_0
0x1400073e4  mov     r8d, eax
0x1400073e7  jmp     short loc_1400073EC
0x1400073e9  sub     r8d, eax
0x1400073ec  mov     eax, r8d
0x1400073ef  add     rsp, 28h
0x1400073f3  retn
```
