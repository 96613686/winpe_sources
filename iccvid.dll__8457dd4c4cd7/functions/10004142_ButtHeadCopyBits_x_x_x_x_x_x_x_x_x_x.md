# ButtHeadCopyBits(x,x,x,x,x,x,x,x,x,x)

- ea: `0x10004142`
- end: `0x100041ba`
- name: `_ButtHeadCopyBits@40`
- size: `120`
- prototype: `int __thiscall(void *Src, int, int, void *, int, int, int, __int16, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10010520`

## callees

- `0x10004100`
- `0x10004142`
- `0x10013599`

## pseudocode

```c
int __fastcall ButtHeadCopyBits(
        char *Src,
        unsigned int a2,
        int a3,
        int a4,
        char *a5,
        unsigned int a6,
        int a7,
        int a8,
        unsigned __int16 a9,
        __int16 a10)
{
  int result; // eax
  __int16 v11; // si

  result = a9;
  v11 = a10;
  if ( a10 )
  {
    result = a9 - 1;
    do
    {
      --v11;
      result = IsWriteRangeInBuffer(a2, (int)Src, a3, 0, result);
      if ( !result )
        break;
      result = IsWriteRangeInBuffer(a6, (int)a5, a7, 0, a9 - 1);
      if ( !result )
        break;
      memmove(a5, Src, a9);
      a5 += a8;
      Src += a4;
      result = a9 - 1;
    }
    while ( v11 );
  }
  return result;
}

```

## disassembly

```asm
0x10004142  mov     edi, edi
0x10004144  push    ebp
0x10004145  mov     ebp, esp
0x10004147  sub     esp, 0Ch
0x1000414a  movzx   eax, [ebp+arg_18]
0x1000414e  push    esi
0x1000414f  mov     esi, [ebp+arg_1C]
0x10004152  mov     [ebp+var_8], edx
0x10004155  push    edi
0x10004156  mov     edi, ecx
0x10004158  test    si, si
0x1000415b  jz      short loc_100041B4
0x1000415d  mov     [ebp+Size], eax
0x10004160  dec     eax
0x10004161  push    ebx
0x10004162  mov     ebx, [ebp+arg_8]
0x10004165  mov     [ebp+var_4], eax
0x10004168  mov     ecx, [ebp+var_8]
0x1000416b  mov     edx, edi
0x1000416d  push    eax
0x1000416e  push    0
0x10004170  push    [ebp+arg_0]
0x10004173  add     esi, 0FFFFh
0x10004179  call    _IsWriteRangeInBuffer@20; IsWriteRangeInBuffer(x,x,x,x,x)
0x1000417e  test    eax, eax
0x10004180  jz      short loc_100041B3
0x10004182  push    [ebp+var_4]
0x10004185  mov     ecx, [ebp+arg_C]
0x10004188  mov     edx, ebx
0x1000418a  push    0
0x1000418c  push    [ebp+arg_10]
0x1000418f  call    _IsWriteRangeInBuffer@20; IsWriteRangeInBuffer(x,x,x,x,x)
0x10004194  test    eax, eax
0x10004196  jz      short loc_100041B3
0x10004198  push    [ebp+Size]; Size
0x1000419b  push    edi; Src
0x1000419c  push    ebx; void *
0x1000419d  call    _memmove
0x100041a2  add     ebx, [ebp+arg_14]
0x100041a5  add     esp, 0Ch
0x100041a8  add     edi, [ebp+arg_4]
0x100041ab  mov     eax, [ebp+var_4]
0x100041ae  test    si, si
0x100041b1  jnz     short loc_10004168
0x100041b3  pop     ebx
0x100041b4  pop     edi
0x100041b5  pop     esi
0x100041b6  leave
0x100041b7  retn    20h ; ' '
```
