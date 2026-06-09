# wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)

- ea: `0x140002c08`
- end: `0x140002c7e`
- name: `?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ`
- size: `118`
- prototype: `unsigned __int16 *(wil::details *__hidden this, unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002374`

## callees

- `0x140001d24`
- `0x140002c08`

## pseudocode

```c
unsigned __int16 *wil::details::LogStringPrintf(
        wil::details *this,
        char *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        ...)
{
  unsigned __int64 v4; // rdi
  unsigned __int16 *v6; // rbx
  size_t v7; // rdi
  int v8; // eax
  __int64 v9; // rax
  const unsigned __int16 *Args; // [rsp+78h] [rbp+20h] BYREF

  Args = a4;
  v4 = (a2 - (char *)this) >> 1;
  v6 = (unsigned __int16 *)this;
  if ( v4 )
  {
    if ( v4 > 0x7FFFFFFF )
    {
      *(_WORD *)this = 0;
    }
    else
    {
      v7 = v4 - 1;
      v8 = vsnwprintf((wchar_t *)this, v7, a3, (va_list)&Args);
      if ( v8 < 0 || v8 >= v7 )
        v6[v7] = 0;
    }
  }
  if ( a2 != (char *)v6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v6[v9] );
    v6 += v9;
  }
  return v6;
}

```

## disassembly

```asm
0x140002c08  mov     [rsp+arg_10], r8
0x140002c0d  mov     [rsp+Args], r9
0x140002c12  push    rbx
0x140002c13  push    rbp
0x140002c14  push    rsi
0x140002c15  push    rdi
0x140002c16  sub     rsp, 38h
0x140002c1a  mov     rdi, rdx
0x140002c1d  lea     r9, [rsp+58h+Args]; Args
0x140002c22  sub     rdi, rcx
0x140002c25  xor     ebp, ebp
0x140002c27  sar     rdi, 1
0x140002c2a  mov     rsi, rdx
0x140002c2d  mov     rbx, rcx
0x140002c30  jz      short loc_140002C5C
0x140002c32  cmp     rdi, 7FFFFFFFh
0x140002c39  ja      short loc_140002C59
0x140002c3b  dec     rdi
0x140002c3e  mov     rdx, rdi; BufferCount
0x140002c41  call    _vsnwprintf
0x140002c46  test    eax, eax
0x140002c48  js      short loc_140002C53
0x140002c4a  cdqe
0x140002c4c  cmp     rax, rdi
0x140002c4f  ja      short loc_140002C53
0x140002c51  jnz     short loc_140002C5C
0x140002c53  mov     [rbx+rdi*2], bp
0x140002c57  jmp     short loc_140002C5C
0x140002c59  mov     [rcx], bp
0x140002c5c  cmp     rsi, rbx
0x140002c5f  jz      short loc_140002C72
0x140002c61  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002c65  inc     rax
0x140002c68  cmp     [rbx+rax*2], bp
0x140002c6c  jnz     short loc_140002C65
0x140002c6e  lea     rbx, [rbx+rax*2]
0x140002c72  mov     rax, rbx
0x140002c75  add     rsp, 38h
0x140002c79  pop     rdi
0x140002c7a  pop     rsi
0x140002c7b  pop     rbp
0x140002c7c  pop     rbx
0x140002c7d  retn
```
