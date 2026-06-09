# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x140009ec0`
- end: `0x140009ee1`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `33`
- prototype: `int __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008d1c`
- `0x140014dfc`
- `0x1400168a4`

## callees

- `0x140009ec0`
- `0x14001e006`

## pseudocode

```c
int __fastcall wil::details_abi::UsageIndexProperty::Compare(const void **this, void *a2, size_t a3)
{
  __int64 v3; // rax

  v3 = *((unsigned __int16 *)this + 4);
  if ( a3 == v3 )
    return memcmp_0(a2, this[3], a3);
  else
    return a3 - v3;
}

```

## disassembly

```asm
0x140009ec0  movzx   eax, word ptr [rcx+8]
0x140009ec4  mov     r9, rdx
0x140009ec7  cmp     r8, rax
0x140009eca  jnz     short loc_140009ED9
0x140009ecc  mov     rdx, [rcx+18h]; Buf2
0x140009ed0  mov     rcx, r9; Buf1
0x140009ed3  jmp     memcmp_0
0x140009ed8  retn
0x140009ed9  sub     r8d, eax
0x140009edc  mov     eax, r8d
0x140009edf  jmp     short locret_140009ED8
```
