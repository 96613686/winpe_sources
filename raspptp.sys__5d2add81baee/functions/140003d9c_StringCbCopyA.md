# StringCbCopyA

- ea: `0x140003d9c`
- end: `0x140003dff`
- name: `StringCbCopyA`
- size: `99`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f588`
- `0x1400102fc`

## callees

- `0x140003d9c`

## pseudocode

```c
HRESULT __stdcall StringCbCopyA(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszSrc)
{
  HRESULT result; // eax
  __int64 v4; // rax
  STRSAFE_LPSTR v5; // rax

  if ( !cbDest )
    return -2147024809;
  if ( cbDest <= 0x7FFFFFFF )
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*pszSrc )
        break;
      *pszDest++ = *pszSrc++;
      --v4;
      --cbDest;
    }
    while ( cbDest );
    v5 = pszDest - 1;
    if ( cbDest )
      v5 = pszDest;
    *v5 = 0;
    return cbDest == 0 ? 0x8007007A : 0;
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
0x140003d9c  test    rdx, rdx
0x140003d9f  jz      short loc_140003DF1
0x140003da1  cmp     rdx, 7FFFFFFFh
0x140003da8  jbe     short loc_140003DB1
0x140003daa  mov     eax, 80070057h
0x140003daf  jmp     short loc_140003DFB
0x140003db1  mov     eax, 7FFFFFFEh
0x140003db6  test    rax, rax
0x140003db9  jz      short loc_140003DD5
0x140003dbb  mov     r9b, [r8]
0x140003dbe  test    r9b, r9b
0x140003dc1  jz      short loc_140003DD5
0x140003dc3  mov     [rcx], r9b
0x140003dc6  inc     r8
0x140003dc9  inc     rcx
0x140003dcc  dec     rax
0x140003dcf  sub     rdx, 1
0x140003dd3  jnz     short loc_140003DB6
0x140003dd5  test    rdx, rdx
0x140003dd8  lea     rax, [rcx-1]
0x140003ddc  cmovnz  rax, rcx
0x140003de0  neg     rdx
0x140003de3  mov     byte ptr [rax], 0
0x140003de6  sbb     eax, eax
0x140003de8  not     eax
0x140003dea  and     eax, 8007007Ah
0x140003def  retn
0x140003df1  mov     eax, 80070057h
0x140003df6  test    rdx, rdx
0x140003df9  jz      short locret_140003DFE
0x140003dfb  mov     byte ptr [rcx], 0
0x140003dfe  retn
```
