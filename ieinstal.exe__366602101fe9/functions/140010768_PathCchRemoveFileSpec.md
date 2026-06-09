# PathCchRemoveFileSpec

- ea: `0x140010768`
- end: `0x140010817`
- name: `PathCchRemoveFileSpec`
- size: `175`
- prototype: `HRESULT __stdcall(PWSTR pszPath, size_t cchPath)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path`

## callers

- `0x140008f78`

## callees

- `0x14001070c`
- `0x140010768`
- `0x140010820`

## import_xrefs

- `msvcrt!wcschr` at `0x1400107cc`
- `msvcrt!wcschr` at `0x1400107cc`

## pseudocode

```c
HRESULT __stdcall PathCchRemoveFileSpec(PWSTR pszPath, size_t cchPath)
{
  HRESULT v4; // eax
  PWSTR v5; // rbx
  WCHAR *v6; // rbp
  const wchar_t *i; // rcx
  wchar_t *v8; // rax
  PWSTR *v9; // r8
  size_t *v10; // r9
  WCHAR *v12; // [rsp+40h] [rbp+8h] BYREF

  v12 = 0;
  if ( !pszPath || cchPath - 1 > 0x7FFF )
    return -2147024809;
  v4 = PathCchSkipRoot(pszPath, (PCWSTR *)&v12);
  v5 = v12;
  v6 = &pszPath[cchPath];
  if ( v4 < 0 )
    v5 = pszPath;
  if ( v5 >= v6 )
    return -2147024809;
  for ( i = v5; ; i = v8 + 1 )
  {
    v8 = wcschr(i, 0x5Cu);
    if ( !v8 )
      break;
    v5 = v8;
    if ( v8 >= v6 )
      return -2147024809;
  }
  if ( !*v5 )
    return PathCchRemoveBackslashEx(pszPath, cchPath, v9, v10);
  *v5 = 0;
  PathCchRemoveBackslashEx(pszPath, cchPath, v9, v10);
  return 0;
}

```

## disassembly

```asm
0x140010768  mov     r11, rsp
0x14001076b  mov     [r11+10h], rbx
0x14001076f  mov     [r11+18h], rbp
0x140010773  push    rsi
0x140010774  push    rdi
0x140010775  push    r14
0x140010777  sub     rsp, 20h
0x14001077b  xor     r14d, r14d
0x14001077e  mov     rsi, rdx
0x140010781  mov     [r11+8], r14
0x140010785  mov     rdi, rcx
0x140010788  test    rcx, rcx
0x14001078b  jz      short loc_1400107FE
0x14001078d  lea     rax, [rdx-1]
0x140010791  cmp     rax, 7FFFh
0x140010797  ja      short loc_1400107FE
0x140010799  lea     rdx, [r11+8]; ppszRootEnd
0x14001079d  call    PathCchSkipRoot
0x1400107a2  mov     rbx, [rsp+38h+arg_0]
0x1400107a7  lea     rbp, [rdi+rsi*2]
0x1400107ab  test    eax, eax
0x1400107ad  cmovs   rbx, rdi
0x1400107b1  cmp     rbx, rbp
0x1400107b4  jnb     short loc_1400107FE
0x1400107b6  mov     rcx, rbx
0x1400107b9  jmp     short loc_1400107C7
0x1400107bb  mov     rbx, rax
0x1400107be  cmp     rax, rbp
0x1400107c1  jnb     short loc_1400107FE
0x1400107c3  lea     rcx, [rax+2]; Str
0x1400107c7  mov     edx, 5Ch ; '\'; Ch
0x1400107cc  call    cs:__imp_wcschr
0x1400107d3  nop     dword ptr [rax+rax+00h]
0x1400107d8  test    rax, rax
0x1400107db  jnz     short loc_1400107BB
0x1400107dd  mov     rdx, rsi; cchPath
0x1400107e0  mov     rcx, rdi; pszPath
0x1400107e3  cmp     [rbx], r14w
0x1400107e7  jnz     short loc_1400107F0
0x1400107e9  call    PathCchRemoveBackslashEx
0x1400107ee  jmp     short loc_140010803
0x1400107f0  mov     [rbx], r14w
0x1400107f4  call    PathCchRemoveBackslashEx
0x1400107f9  mov     eax, r14d
0x1400107fc  jmp     short loc_140010803
0x1400107fe  mov     eax, 80070057h
0x140010803  mov     rbx, [rsp+38h+arg_8]
0x140010808  mov     rbp, [rsp+38h+arg_10]
0x14001080d  add     rsp, 20h
0x140010811  pop     r14
0x140010813  pop     rdi
0x140010814  pop     rsi
0x140010815  retn
```
