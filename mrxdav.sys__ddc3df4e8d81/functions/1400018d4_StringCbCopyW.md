# StringCbCopyW

- ea: `0x1400018d4`
- end: `0x140001941`
- name: `StringCbCopyW`
- size: `109`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140004b00`
- `0x140010620`
- `0x1400130e0`
- `0x14001a480`
- `0x14001b360`
- `0x14001bc30`
- `0x14001e6a0`
- `0x1400220c0`
- `0x140023530`

## callees

- `0x1400018d4`

## pseudocode

```c
HRESULT __stdcall StringCbCopyW(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)
{
  size_t v3; // rdx
  HRESULT result; // eax
  __int64 v5; // rax
  STRSAFE_LPWSTR v6; // rax

  v3 = cbDest >> 1;
  if ( !v3 )
    return -2147024809;
  if ( v3 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*pszSrc )
        break;
      *pszDest++ = *pszSrc++;
      --v5;
      --v3;
    }
    while ( v3 );
    v6 = pszDest - 1;
    if ( v3 )
      v6 = pszDest;
    *v6 = 0;
    return v3 == 0 ? 0x8007007A : 0;
  }
  else
  {
    result = -2147024809;
    *pszDest = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400018d4  xor     r9d, r9d
0x1400018d7  shr     rdx, 1
0x1400018da  jz      short loc_140001932
0x1400018dc  cmp     rdx, 7FFFFFFFh
0x1400018e3  jbe     short loc_1400018EC
0x1400018e5  mov     eax, 80070057h
0x1400018ea  jmp     short loc_14000193C
0x1400018ec  mov     eax, 7FFFFFFEh
0x1400018f1  test    rax, rax
0x1400018f4  jz      short loc_140001915
0x1400018f6  movzx   r10d, word ptr [r8]
0x1400018fa  test    r10w, r10w
0x1400018fe  jz      short loc_140001915
0x140001900  mov     [rcx], r10w
0x140001904  add     r8, 2
0x140001908  add     rcx, 2
0x14000190c  dec     rax
0x14000190f  sub     rdx, 1
0x140001913  jnz     short loc_1400018F1
0x140001915  test    rdx, rdx
0x140001918  lea     rax, [rcx-2]
0x14000191c  cmovnz  rax, rcx
0x140001920  neg     rdx
0x140001923  mov     [rax], r9w
0x140001927  sbb     eax, eax
0x140001929  not     eax
0x14000192b  and     eax, 8007007Ah
0x140001930  retn
0x140001932  mov     eax, 80070057h
0x140001937  test    rdx, rdx
0x14000193a  jz      short locret_140001940
0x14000193c  mov     [rcx], r9w
0x140001940  retn
```
