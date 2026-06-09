# RtlStringCchCopyW

- ea: `0x180013fc8`
- end: `0x180014033`
- name: `RtlStringCchCopyW`
- size: `107`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eef4`
- `0x18000f39c`

## callees

- `0x180013fc8`

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
0x180013fc8  xor     r10d, r10d
0x180013fcb  mov     r9, rcx
0x180013fce  test    rdx, rdx
0x180013fd1  jz      short loc_180014024
0x180013fd3  cmp     rdx, 7FFFFFFFh
0x180013fda  jbe     short loc_180013FE3
0x180013fdc  mov     eax, 0C000000Dh
0x180013fe1  jmp     short loc_18001402E
0x180013fe3  mov     eax, 7FFFFFFEh
0x180013fe8  test    rax, rax
0x180013feb  jz      short loc_18001400B
0x180013fed  movzx   ecx, word ptr [r8]
0x180013ff1  test    cx, cx
0x180013ff4  jz      short loc_18001400B
0x180013ff6  mov     [r9], cx
0x180013ffa  add     r8, 2
0x180013ffe  add     r9, 2
0x180014002  dec     rax
0x180014005  sub     rdx, 1
0x180014009  jnz     short loc_180013FE8
0x18001400b  test    rdx, rdx
0x18001400e  lea     rcx, [r9-2]
0x180014012  cmovnz  rcx, r9
0x180014016  neg     rdx
0x180014019  sbb     eax, eax
0x18001401b  not     eax
0x18001401d  and     eax, 80000005h
0x180014022  jmp     short loc_18001402E
0x180014024  mov     eax, 0C000000Dh
0x180014029  test    rdx, rdx
0x18001402c  jz      short locret_180014032
0x18001402e  mov     [rcx], r10w
0x180014032  retn
```
