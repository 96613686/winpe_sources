# StringCbLengthW

- ea: `0x180003110`
- end: `0x180003165`
- name: `StringCbLengthW`
- size: `85`
- prototype: `HRESULT __stdcall(STRSAFE_PCNZWCH psz, size_t cbMax, size_t *pcbLength)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800042d4`
- `0x180006300`
- `0x180007200`
- `0x1800075d0`
- `0x180009060`
- `0x180009584`

## callees

- `0x180003110`

## pseudocode

```c
HRESULT __stdcall StringCbLengthW(STRSAFE_PCNZWCH psz, size_t cbMax, size_t *pcbLength)
{
  __int64 v3; // rax
  HRESULT v4; // edx
  __int64 v5; // r9
  HRESULT result; // eax

  if ( psz )
  {
    v3 = 0x7FFFFFFF;
    do
    {
      if ( !*psz )
        break;
      ++psz;
      --v3;
    }
    while ( v3 );
    psz = 0;
    v4 = -2147024809;
    if ( v3 )
      v4 = 0;
    v5 = 0x7FFFFFFF - v3;
    if ( !v3 )
      v5 = 0;
  }
  else
  {
    v5 = 0;
    v4 = -2147024809;
  }
  result = v4;
  if ( pcbLength )
  {
    if ( v4 >= 0 )
      psz = (STRSAFE_PCNZWCH)(2 * v5);
    *pcbLength = (size_t)psz;
  }
  return result;
}

```

## disassembly

```asm
0x180003110  test    rcx, rcx
0x180003113  jz      short loc_18000314F
0x180003115  mov     r9d, 7FFFFFFFh
0x18000311b  mov     eax, r9d
0x18000311e  xchg    ax, ax
0x180003120  cmp     word ptr [rcx], 0
0x180003124  jz      short loc_180003130
0x180003126  add     rcx, 2
0x18000312a  sub     rax, 1
0x18000312e  jnz     short loc_180003120
0x180003130  xor     ecx, ecx
0x180003132  mov     edx, 80070057h
0x180003137  test    rax, rax
0x18000313a  cmovnz  edx, ecx
0x18000313d  sub     r9, rax
0x180003140  test    rax, rax
0x180003143  cmovz   r9, rcx
0x180003147  mov     eax, edx
0x180003149  test    r8, r8
0x18000314c  jnz     short loc_180003159
0x18000314e  retn
0x18000314f  mov     r9, rcx
0x180003152  mov     edx, 80070057h
0x180003157  jmp     short loc_180003147
0x180003159  test    edx, edx
0x18000315b  js      short loc_180003161
0x18000315d  lea     rcx, [r9+r9]
0x180003161  mov     [r8], rcx
0x180003164  retn
```
