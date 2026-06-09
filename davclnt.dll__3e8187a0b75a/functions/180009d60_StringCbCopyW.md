# StringCbCopyW

- ea: `0x180009d60`
- end: `0x180009dcd`
- name: `StringCbCopyW`
- size: `109`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180004340`
- `0x18000d0ec`
- `0x18000ec54`
- `0x18000f7f0`
- `0x18000fd30`

## callees

- `0x180009d60`

## pseudocode

```c
HRESULT __stdcall StringCbCopyW(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)
{
  size_t v3; // rdx
  STRSAFE_LPWSTR v4; // r9
  HRESULT result; // eax
  __int64 v6; // rcx
  STRSAFE_LPWSTR v7; // rax

  v3 = cbDest >> 1;
  v4 = pszDest;
  if ( !v3 )
    return -2147024809;
  if ( v3 <= 0x7FFFFFFF )
  {
    v6 = 2147483646;
    do
    {
      if ( !v6 )
        break;
      if ( !*pszSrc )
        break;
      *v4++ = *pszSrc++;
      --v6;
      --v3;
    }
    while ( v3 );
    v7 = v4 - 1;
    if ( v3 )
      v7 = v4;
    *v7 = 0;
    result = -2147024774;
    if ( v3 )
      return 0;
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
0x180009d60  shr     rdx, 1
0x180009d63  mov     r9, rcx
0x180009d66  jz      short loc_180009DBC
0x180009d68  cmp     rdx, 7FFFFFFFh
0x180009d6f  jbe     short loc_180009D78
0x180009d71  mov     eax, 80070057h
0x180009d76  jmp     short loc_180009DC6
0x180009d78  mov     ecx, 7FFFFFFEh
0x180009d7d  test    rcx, rcx
0x180009d80  jz      short loc_180009DA0
0x180009d82  movzx   eax, word ptr [r8]
0x180009d86  test    ax, ax
0x180009d89  jz      short loc_180009DA0
0x180009d8b  mov     [r9], ax
0x180009d8f  add     r8, 2
0x180009d93  add     r9, 2
0x180009d97  dec     rcx
0x180009d9a  sub     rdx, 1
0x180009d9e  jnz     short loc_180009D7D
0x180009da0  test    rdx, rdx
0x180009da3  lea     rax, [r9-2]
0x180009da7  cmovnz  rax, r9
0x180009dab  xor     ecx, ecx
0x180009dad  test    rdx, rdx
0x180009db0  mov     [rax], cx
0x180009db3  mov     eax, 8007007Ah
0x180009db8  cmovnz  eax, ecx
0x180009dbb  retn
0x180009dbc  mov     eax, 80070057h
0x180009dc1  test    rdx, rdx
0x180009dc4  jz      short locret_180009DCC
0x180009dc6  xor     ecx, ecx
0x180009dc8  mov     [r9], cx
0x180009dcc  retn
```
