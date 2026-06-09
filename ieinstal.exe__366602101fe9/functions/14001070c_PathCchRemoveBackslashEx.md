# PathCchRemoveBackslashEx

- ea: `0x14001070c`
- end: `0x140010761`
- name: `PathCchRemoveBackslashEx`
- size: `85`
- prototype: `HRESULT __stdcall(PWSTR pszPath, size_t cchPath, PWSTR *ppszEnd, size_t *pcchRemaining)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x140010768`

## callees

- `0x1400105d8`
- `0x14001070c`

## pseudocode

```c
HRESULT __stdcall PathCchRemoveBackslashEx(PWSTR pszPath, size_t cchPath, PWSTR *ppszEnd, size_t *pcchRemaining)
{
  size_t v4; // rbx
  HRESULT v7; // esi

  v4 = -1;
  do
    ++v4;
  while ( pszPath[v4] );
  if ( v4 >= cchPath )
    return -2147024809;
  v7 = 1;
  if ( v4 && pszPath[v4 - 1] == 92 && !PathCchIsRoot(pszPath) )
  {
    pszPath[v4 - 1] = 0;
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x14001070c  push    rbx
0x14001070e  push    rbp
0x14001070f  push    rsi
0x140010710  push    rdi
0x140010711  sub     rsp, 28h
0x140010715  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140010719  mov     rdi, rcx
0x14001071c  xor     ebp, ebp
0x14001071e  inc     rbx
0x140010721  cmp     [rcx+rbx*2], bp
0x140010725  jnz     short loc_14001071E
0x140010727  cmp     rbx, rdx
0x14001072a  jb      short loc_140010733
0x14001072c  mov     eax, 80070057h
0x140010731  jmp     short loc_140010757
0x140010733  mov     esi, 1
0x140010738  test    rbx, rbx
0x14001073b  jz      short loc_140010755
0x14001073d  cmp     word ptr [rcx+rbx*2-2], 5Ch ; '\'
0x140010743  jnz     short loc_140010755
0x140010745  call    PathCchIsRoot
0x14001074a  test    eax, eax
0x14001074c  jnz     short loc_140010755
0x14001074e  mov     [rdi+rbx*2-2], bp
0x140010753  mov     esi, ebp
0x140010755  mov     eax, esi
0x140010757  add     rsp, 28h
0x14001075b  pop     rdi
0x14001075c  pop     rsi
0x14001075d  pop     rbp
0x14001075e  pop     rbx
0x14001075f  retn
```
