# wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)

- ea: `0x140004000`
- end: `0x140004077`
- name: `?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ`
- size: `119`
- prototype: `unsigned __int16 *(wil::details *__hidden this, unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400033a4`

## callees

- `0x140004000`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140004039`
- `msvcrt!_vsnwprintf` at `0x140004039`

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
      v8 = _vsnwprintf((wchar_t *)this, v7, a3, (va_list)&Args);
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
0x140004000  mov     [rsp+arg_10], r8
0x140004005  mov     [rsp+Args], r9
0x14000400a  push    rbx
0x14000400b  push    rbp
0x14000400c  push    rsi
0x14000400d  push    rdi
0x14000400e  sub     rsp, 38h
0x140004012  mov     rdi, rdx
0x140004015  lea     r9, [rsp+58h+Args]; Args
0x14000401a  sub     rdi, rcx
0x14000401d  xor     ebp, ebp
0x14000401f  sar     rdi, 1
0x140004022  mov     rsi, rdx
0x140004025  mov     rbx, rcx
0x140004028  jz      short loc_140004055
0x14000402a  cmp     rdi, 7FFFFFFFh
0x140004031  ja      short loc_140004052
0x140004033  dec     rdi
0x140004036  mov     rdx, rdi; BufferCount
0x140004039  call    cs:__imp__vsnwprintf
0x14000403f  test    eax, eax
0x140004041  js      short loc_14000404C
0x140004043  cdqe
0x140004045  cmp     rax, rdi
0x140004048  ja      short loc_14000404C
0x14000404a  jnz     short loc_140004055
0x14000404c  mov     [rbx+rdi*2], bp
0x140004050  jmp     short loc_140004055
0x140004052  mov     [rcx], bp
0x140004055  cmp     rsi, rbx
0x140004058  jz      short loc_14000406B
0x14000405a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000405e  inc     rax
0x140004061  cmp     [rbx+rax*2], bp
0x140004065  jnz     short loc_14000405E
0x140004067  lea     rbx, [rbx+rax*2]
0x14000406b  mov     rax, rbx
0x14000406e  add     rsp, 38h
0x140004072  pop     rdi
0x140004073  pop     rsi
0x140004074  pop     rbp
0x140004075  pop     rbx
0x140004076  retn
```
