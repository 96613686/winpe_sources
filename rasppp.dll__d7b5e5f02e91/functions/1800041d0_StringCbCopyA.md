# StringCbCopyA

- ea: `0x1800041d0`
- end: `0x180004233`
- name: `StringCbCopyA`
- size: `99`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cbDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x1800023c0`
- `0x18000442c`
- `0x180015430`
- `0x180015a00`
- `0x180015a80`
- `0x180016260`
- `0x180017fa0`
- `0x18001c310`
- `0x18001e2c0`
- `0x180021b40`
- `0x180022f50`
- `0x180024340`
- `0x180024820`
- `0x1800248a4`
- `0x180024bb4`
- `0x1800260b0`
- `0x180026e30`
- `0x18002a350`
- `0x18002a9b0`
- `0x18002ab18`
- `0x18002aca4`

## callees

- `0x1800041d0`

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
0x1800041d0  test    rdx, rdx
0x1800041d3  jz      short loc_180004225
0x1800041d5  cmp     rdx, 7FFFFFFFh
0x1800041dc  jbe     short loc_1800041E5
0x1800041de  mov     eax, 80070057h
0x1800041e3  jmp     short loc_18000422F
0x1800041e5  mov     eax, 7FFFFFFEh
0x1800041ea  test    rax, rax
0x1800041ed  jz      short loc_180004209
0x1800041ef  mov     r9b, [r8]
0x1800041f2  test    r9b, r9b
0x1800041f5  jz      short loc_180004209
0x1800041f7  mov     [rcx], r9b
0x1800041fa  inc     r8
0x1800041fd  inc     rcx
0x180004200  dec     rax
0x180004203  sub     rdx, 1
0x180004207  jnz     short loc_1800041EA
0x180004209  test    rdx, rdx
0x18000420c  lea     rax, [rcx-1]
0x180004210  cmovnz  rax, rcx
0x180004214  neg     rdx
0x180004217  mov     byte ptr [rax], 0
0x18000421a  sbb     eax, eax
0x18000421c  not     eax
0x18000421e  and     eax, 8007007Ah
0x180004223  retn
0x180004225  mov     eax, 80070057h
0x18000422a  test    rdx, rdx
0x18000422d  jz      short locret_180004232
0x18000422f  mov     byte ptr [rcx], 0
0x180004232  retn
```
