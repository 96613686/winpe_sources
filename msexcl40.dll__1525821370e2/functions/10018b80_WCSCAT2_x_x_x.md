# WCSCAT2(x,x,x)

- ea: `0x10018b80`
- end: `0x10018c01`
- name: `_WCSCAT2@12`
- size: `129`
- prototype: `_WORD *__fastcall(_WORD *, _WORD *, unsigned int)`
- caller_count: `23`
- callee_count: `1`
- tags: ``

## callers

- `0x10018cd0`
- `0x10019d40`
- `0x1001e2b0`
- `0x10020e70`
- `0x10022890`
- `0x10022920`
- `0x100232c9`
- `0x10023563`
- `0x10023815`
- `0x10024042`
- `0x100249dd`
- `0x10024d8e`
- `0x100252b0`
- `0x100269d4`
- `0x10026c60`
- `0x100278d3`
- `0x10028701`
- `0x10029068`
- `0x10029b60`
- `0x1002b580`
- `0x1002df60`
- `0x10034c1b`
- `0x10034c94`

## callees

- `0x10018b80`

## pseudocode

```c
_WORD *__fastcall WCSCAT2(_WORD *a1, _WORD *a2, unsigned int a3)
{
  _WORD *result; // eax
  unsigned int v6; // ecx
  int v7; // edx
  _WORD *v8; // ecx
  int v9; // eax
  unsigned int v10; // esi
  _WORD *v11; // eax

  if ( a3 )
  {
    result = a1;
    if ( a3 > 0x7FFFFFFF )
      return result;
    v6 = a3;
    do
    {
      if ( !*result )
        break;
      ++result;
      --v6;
    }
    while ( v6 );
    v7 = v6 != 0 ? a3 - v6 : 0;
    if ( v6 )
    {
      v8 = &a1[v7];
      v9 = 2147483646;
      v10 = a3 - v7;
      if ( a3 != v7 )
      {
        do
        {
          if ( !v9 )
            break;
          if ( !*a2 )
            break;
          *v8++ = *a2++;
          --v9;
          --v10;
        }
        while ( v10 );
      }
      v11 = v8 - 1;
      if ( v10 )
        v11 = v8;
      *v11 = 0;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x10018b80  mov     edi, edi
0x10018b82  push    ebp
0x10018b83  mov     ebp, esp
0x10018b85  push    ebx
0x10018b86  push    esi
0x10018b87  mov     esi, [ebp+arg_0]
0x10018b8a  mov     ebx, ecx
0x10018b8c  push    edi
0x10018b8d  mov     edi, edx
0x10018b8f  test    esi, esi
0x10018b91  jz      short loc_10018BF8
0x10018b93  mov     eax, ebx
0x10018b95  cmp     esi, 7FFFFFFFh
0x10018b9b  ja      short loc_10018BFA
0x10018b9d  mov     ecx, esi
0x10018b9f  nop
0x10018ba0  cmp     word ptr [eax], 0
0x10018ba4  jz      short loc_10018BAE
0x10018ba6  add     eax, 2
0x10018ba9  sub     ecx, 1
0x10018bac  jnz     short loc_10018BA0
0x10018bae  mov     eax, esi
0x10018bb0  mov     edx, ecx
0x10018bb2  sub     eax, ecx
0x10018bb4  neg     edx
0x10018bb6  sbb     edx, edx
0x10018bb8  and     edx, eax
0x10018bba  test    ecx, ecx
0x10018bbc  jz      short loc_10018BF8
0x10018bbe  lea     ecx, [ebx+edx*2]
0x10018bc1  mov     eax, 7FFFFFFEh
0x10018bc6  sub     esi, edx
0x10018bc8  jz      short loc_10018BEB
0x10018bca  nop     word ptr [eax+eax+00h]
0x10018bd0  test    eax, eax
0x10018bd2  jz      short loc_10018BEB
0x10018bd4  movzx   edx, word ptr [edi]
0x10018bd7  test    dx, dx
0x10018bda  jz      short loc_10018BEB
0x10018bdc  mov     [ecx], dx
0x10018bdf  add     edi, 2
0x10018be2  add     ecx, 2
0x10018be5  dec     eax
0x10018be6  sub     esi, 1
0x10018be9  jnz     short loc_10018BD0
0x10018beb  test    esi, esi
0x10018bed  lea     eax, [ecx-2]
0x10018bf0  cmovnz  eax, ecx
0x10018bf3  xor     ecx, ecx
0x10018bf5  mov     [eax], cx
0x10018bf8  mov     eax, ebx
0x10018bfa  pop     edi
0x10018bfb  pop     esi
0x10018bfc  pop     ebx
0x10018bfd  pop     ebp
0x10018bfe  retn    4
```
