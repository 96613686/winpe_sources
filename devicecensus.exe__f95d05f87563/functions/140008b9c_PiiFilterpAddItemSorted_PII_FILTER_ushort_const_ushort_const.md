# PiiFilterpAddItemSorted(_PII_FILTER *,ushort const *,ushort const *)

- ea: `0x140008b9c`
- end: `0x140008c3a`
- name: `?PiiFilterpAddItemSorted@@YAJPEAU_PII_FILTER@@PEBG1@Z`
- size: `158`
- prototype: `__int64 __fastcall(struct _PII_FILTER *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000899c`
- `0x140008c40`

## callees

- `0x1400088d4`
- `0x140008b9c`

## pseudocode

```c
__int64 __fastcall PiiFilterpAddItemSorted(
        struct _PII_FILTER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned __int64 v3; // r9
  const unsigned __int16 *v5; // rbx
  unsigned __int64 v7; // r11
  unsigned int i; // r8d
  __int64 v9; // rax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rax

  v3 = -1;
  v5 = a2;
  do
    ++v3;
  while ( a2[v3] );
  v7 = *((_QWORD *)this + 2);
  for ( i = 0; i < v7; ++i )
  {
    a2 = 0;
    if ( i < v7 )
    {
      v9 = *((_QWORD *)this + 1) * i;
      if ( !is_mul_ok(*((_QWORD *)this + 1), i)
        || (v10 = *((_QWORD *)this + 5), a2 = (const unsigned __int16 *)(v10 + v9), v10 + v9 < v10) )
      {
        a2 = 0;
      }
    }
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)(*(_QWORD *)a2 + 2 * v11) );
    if ( v3 > v11 )
      break;
  }
  return RtlNameValueArray::Insert((PVOID *)this, a2, v5, a3, i);
}

```

## disassembly

```asm
0x140008b9c  mov     [rsp+arg_8], rbx
0x140008ba1  mov     [rsp+arg_10], rsi
0x140008ba6  push    rdi
0x140008ba7  sub     rsp, 30h
0x140008bab  or      r9, 0FFFFFFFFFFFFFFFFh
0x140008baf  mov     rdi, r8
0x140008bb2  xor     esi, esi
0x140008bb4  mov     rbx, rdx
0x140008bb7  mov     r10, rcx
0x140008bba  inc     r9
0x140008bbd  cmp     [rdx+r9*2], si
0x140008bc2  jnz     short loc_140008BBA
0x140008bc4  mov     r11, [rcx+10h]
0x140008bc8  mov     r8d, esi
0x140008bcb  test    r11, r11
0x140008bce  jz      short loc_140008C14
0x140008bd0  mov     eax, r8d
0x140008bd3  mov     rdx, rsi
0x140008bd6  cmp     rax, r11
0x140008bd9  jnb     short loc_140008BF4
0x140008bdb  mul     qword ptr [r10+8]
0x140008bdf  test    rdx, rdx
0x140008be2  jnz     short loc_140008BF1
0x140008be4  mov     rcx, [r10+28h]
0x140008be8  lea     rdx, [rcx+rax]
0x140008bec  cmp     rdx, rcx
0x140008bef  jnb     short loc_140008BF4
0x140008bf1  mov     rdx, rsi; unsigned __int16 *
0x140008bf4  mov     rcx, [rdx]
0x140008bf7  or      rax, 0FFFFFFFFFFFFFFFFh
0x140008bfb  inc     rax
0x140008bfe  cmp     [rcx+rax*2], si
0x140008c02  jnz     short loc_140008BFB
0x140008c04  cmp     r9, rax
0x140008c07  ja      short loc_140008C14
0x140008c09  inc     r8d
0x140008c0c  mov     eax, r8d
0x140008c0f  cmp     rax, r11
0x140008c12  jb      short loc_140008BD0
0x140008c14  mov     eax, r8d
0x140008c17  mov     r9, rdi; unsigned __int16 *
0x140008c1a  mov     r8, rbx; unsigned __int16 *
0x140008c1d  mov     [rsp+38h+var_18], rax; unsigned __int64
0x140008c22  mov     rcx, r10; this
0x140008c25  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x140008c2a  mov     rbx, [rsp+38h+arg_8]
0x140008c2f  mov     rsi, [rsp+38h+arg_10]
0x140008c34  add     rsp, 30h
0x140008c38  pop     rdi
0x140008c39  retn
```
