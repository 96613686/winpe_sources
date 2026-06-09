# RtlStringCchCopyW

- ea: `0x14000800c`
- end: `0x140008077`
- name: `RtlStringCchCopyW`
- size: `107`
- prototype: `__int64(_WORD *, unsigned __int64, _WORD *, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400097d4`
- `0x14000b6bc`

## callees

- `0x14000800c`

## pseudocode

```c
__int64 RtlStringCchCopyW(_WORD *a1, unsigned __int64 a2, _WORD *a3, ...)
{
  _WORD *v3; // r9
  __int64 result; // rax
  __int64 v5; // rax

  v3 = a1;
  if ( !a2 )
    return 3221225485LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*a3 )
        break;
      *v3++ = *a3++;
      --v5;
      --a2;
    }
    while ( a2 );
    a1 = v3 - 1;
    if ( a2 )
      a1 = v3;
    result = a2 == 0 ? 0x80000005 : 0;
  }
  else
  {
    result = 3221225485LL;
  }
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x14000800c  xor     r10d, r10d
0x14000800f  mov     r9, rcx
0x140008012  test    rdx, rdx
0x140008015  jz      short loc_140008068
0x140008017  cmp     rdx, 7FFFFFFFh
0x14000801e  jbe     short loc_140008027
0x140008020  mov     eax, 0C000000Dh
0x140008025  jmp     short loc_140008072
0x140008027  mov     eax, 7FFFFFFEh
0x14000802c  test    rax, rax
0x14000802f  jz      short loc_14000804F
0x140008031  movzx   ecx, word ptr [r8]
0x140008035  test    cx, cx
0x140008038  jz      short loc_14000804F
0x14000803a  mov     [r9], cx
0x14000803e  add     r8, 2
0x140008042  add     r9, 2
0x140008046  dec     rax
0x140008049  sub     rdx, 1
0x14000804d  jnz     short loc_14000802C
0x14000804f  test    rdx, rdx
0x140008052  lea     rcx, [r9-2]
0x140008056  cmovnz  rcx, r9
0x14000805a  neg     rdx
0x14000805d  sbb     eax, eax
0x14000805f  not     eax
0x140008061  and     eax, 80000005h
0x140008066  jmp     short loc_140008072
0x140008068  mov     eax, 0C000000Dh
0x14000806d  test    rdx, rdx
0x140008070  jz      short locret_140008076
0x140008072  mov     [rcx], r10w
0x140008076  retn
```
