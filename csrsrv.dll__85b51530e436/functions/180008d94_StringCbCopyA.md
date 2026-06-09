# StringCbCopyA

- ea: `0x180008d94`
- end: `0x180008ddd`
- name: `StringCbCopyA`
- size: `73`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001140`
- `0x180001c50`
- `0x1800064b0`
- `0x180006820`
- `0x180008290`
- `0x180008ca4`

## callees

- `0x180008d94`

## pseudocode

```c
HRESULT __stdcall StringCbCopyA(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszSrc)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  STRSAFE_LPSTR v6; // rcx
  HRESULT result; // eax

  v4 = 2147483646;
  v5 = 64;
  do
  {
    if ( !v4 )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --v4;
    --v5;
  }
  while ( v5 );
  v6 = pszDest - 1;
  result = v5 == 0 ? 0x8007007A : 0;
  if ( v5 )
    v6 = pszDest;
  *v6 = 0;
  return result;
}

```

## disassembly

```asm
0x180008d94  mov     r9, rcx
0x180008d97  mov     eax, 7FFFFFFEh
0x180008d9c  mov     edx, 40h ; '@'
0x180008da1  test    rax, rax
0x180008da4  jz      short loc_180008DBF
0x180008da6  mov     cl, [r8]
0x180008da9  test    cl, cl
0x180008dab  jz      short loc_180008DBF
0x180008dad  mov     [r9], cl
0x180008db0  inc     r8
0x180008db3  inc     r9
0x180008db6  dec     rax
0x180008db9  sub     rdx, 1
0x180008dbd  jnz     short loc_180008DA1
0x180008dbf  mov     rax, rdx
0x180008dc2  lea     rcx, [r9-1]
0x180008dc6  neg     rax
0x180008dc9  sbb     eax, eax
0x180008dcb  not     eax
0x180008dcd  and     eax, 8007007Ah
0x180008dd2  test    rdx, rdx
0x180008dd5  cmovnz  rcx, r9
0x180008dd9  mov     byte ptr [rcx], 0
0x180008ddc  retn
```
