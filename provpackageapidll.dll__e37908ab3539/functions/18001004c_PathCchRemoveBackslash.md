# PathCchRemoveBackslash

- ea: `0x18001004c`
- end: `0x1800100a0`
- name: `PathCchRemoveBackslash`
- size: `84`
- prototype: `HRESULT __stdcall(PWSTR pszPath, size_t cchPath)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x180007f78`
- `0x1800100a8`

## callees

- `0x18000ff24`
- `0x18001004c`

## pseudocode

```c
HRESULT __stdcall PathCchRemoveBackslash(PWSTR pszPath, size_t cchPath)
{
  size_t v2; // rbx
  HRESULT v4; // edi

  v2 = -1;
  do
    ++v2;
  while ( pszPath[v2] );
  if ( v2 >= cchPath )
    return -2147024809;
  v4 = 1;
  if ( v2 && pszPath[v2 - 1] == 92 && !PathCchIsRoot(pszPath) )
  {
    pszPath[v2 - 1] = 0;
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18001004c  push    rbx
0x18001004e  push    rbp
0x18001004f  push    rsi
0x180010050  push    rdi
0x180010051  sub     rsp, 28h
0x180010055  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180010059  mov     rsi, rcx
0x18001005c  xor     ebp, ebp
0x18001005e  inc     rbx
0x180010061  cmp     [rcx+rbx*2], bp
0x180010065  jnz     short loc_18001005E
0x180010067  cmp     rbx, rdx
0x18001006a  jb      short loc_180010073
0x18001006c  mov     edi, 80070057h
0x180010071  jmp     short loc_180010095
0x180010073  mov     edi, 1
0x180010078  test    rbx, rbx
0x18001007b  jz      short loc_180010095
0x18001007d  cmp     word ptr [rcx+rbx*2-2], 5Ch ; '\'
0x180010083  jnz     short loc_180010095
0x180010085  call    PathCchIsRoot
0x18001008a  test    eax, eax
0x18001008c  jnz     short loc_180010095
0x18001008e  mov     [rsi+rbx*2-2], bp
0x180010093  mov     edi, ebp
0x180010095  mov     eax, edi
0x180010097  add     rsp, 28h
0x18001009b  pop     rdi
0x18001009c  pop     rsi
0x18001009d  pop     rbp
0x18001009e  pop     rbx
0x18001009f  retn
```
