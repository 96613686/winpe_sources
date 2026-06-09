# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x1800051ac`
- end: `0x1800051d8`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005898`
- `0x180006d90`
- `0x180007ddc`

## callees

- `0x1800051ac`
- `0x180012a74`

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
0x1800051ac  sub     rsp, 28h
0x1800051b0  movzx   eax, word ptr [rcx+8]
0x1800051b4  mov     r9, rdx
0x1800051b7  cmp     r8, rax
0x1800051ba  jnz     short loc_1800051CD
0x1800051bc  mov     rdx, [rcx+18h]; Buf2
0x1800051c0  mov     rcx, r9; Buf1
0x1800051c3  call    memcmp_0
0x1800051c8  mov     r8d, eax
0x1800051cb  jmp     short loc_1800051D0
0x1800051cd  sub     r8d, eax
0x1800051d0  mov     eax, r8d
0x1800051d3  add     rsp, 28h
0x1800051d7  retn
```
