# StringCbCopyW

- ea: `0x18000d3cc`
- end: `0x18000d438`
- name: `StringCbCopyW`
- size: `108`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180006300`
- `0x180009060`
- `0x180009584`
- `0x18000f528`

## callees

- `0x18000d3cc`

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
0x18000d3cc  xor     r9d, r9d
0x18000d3cf  shr     rdx, 1
0x18000d3d2  jz      short loc_18000D429
0x18000d3d4  cmp     rdx, 7FFFFFFFh
0x18000d3db  jbe     short loc_18000D3E4
0x18000d3dd  mov     eax, 80070057h
0x18000d3e2  jmp     short loc_18000D433
0x18000d3e4  mov     eax, 7FFFFFFEh
0x18000d3e9  test    rax, rax
0x18000d3ec  jz      short loc_18000D40D
0x18000d3ee  movzx   r10d, word ptr [r8]
0x18000d3f2  test    r10w, r10w
0x18000d3f6  jz      short loc_18000D40D
0x18000d3f8  mov     [rcx], r10w
0x18000d3fc  add     r8, 2
0x18000d400  add     rcx, 2
0x18000d404  dec     rax
0x18000d407  sub     rdx, 1
0x18000d40b  jnz     short loc_18000D3E9
0x18000d40d  test    rdx, rdx
0x18000d410  lea     rax, [rcx-2]
0x18000d414  cmovnz  rax, rcx
0x18000d418  neg     rdx
0x18000d41b  mov     [rax], r9w
0x18000d41f  sbb     eax, eax
0x18000d421  not     eax
0x18000d423  and     eax, 8007007Ah
0x18000d428  retn
0x18000d429  mov     eax, 80070057h
0x18000d42e  test    rdx, rdx
0x18000d431  jz      short locret_18000D437
0x18000d433  mov     [rcx], r9w
0x18000d437  retn
```
