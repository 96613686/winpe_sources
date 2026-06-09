# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180010454`
- end: `0x180010480`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010ad0`
- `0x180010e40`
- `0x180011788`

## callees

- `0x180010454`
- `0x180018a46`

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
0x180010454  sub     rsp, 28h
0x180010458  movzx   eax, word ptr [rcx+8]
0x18001045c  mov     r9, rdx
0x18001045f  cmp     r8, rax
0x180010462  jnz     short loc_180010475
0x180010464  mov     rdx, [rcx+18h]; Buf2
0x180010468  mov     rcx, r9; Buf1
0x18001046b  call    memcmp_0
0x180010470  mov     r8d, eax
0x180010473  jmp     short loc_180010478
0x180010475  sub     r8d, eax
0x180010478  mov     eax, r8d
0x18001047b  add     rsp, 28h
0x18001047f  retn
```
