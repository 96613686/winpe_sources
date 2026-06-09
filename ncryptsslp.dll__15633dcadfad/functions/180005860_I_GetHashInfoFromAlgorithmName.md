# I_GetHashInfoFromAlgorithmName

- ea: `0x180005860`
- end: `0x1800058d1`
- name: `I_GetHashInfoFromAlgorithmName`
- size: `113`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180003f10`
- `0x180004570`
- `0x180005240`
- `0x1800058e0`
- `0x18000dea0`
- `0x18001d8e8`

## callees

- `0x180005860`
- `0x1800183d0`

## pseudocode

```c
__int64 __fastcall I_GetHashInfoFromAlgorithmName(wchar_t *String1)
{
  __int64 i; // rbx
  const wchar_t **v3; // rax

  for ( i = 0; (unsigned int)i < g_dwHashInfoTotalCount; i = (unsigned int)(i + 1) )
  {
    v3 = (const wchar_t **)g_pHashInfo[i];
    if ( v3 && *v3 && !wcsnicmp(String1, *v3, 0x40u) )
      return g_pHashInfo[i];
  }
  return 0;
}

```

## disassembly

```asm
0x180005860  mov     [rsp+arg_8], rbx
0x180005865  mov     [rsp+arg_10], rsi
0x18000586a  push    r14
0x18000586c  sub     rsp, 20h
0x180005870  mov     rsi, rcx
0x180005873  mov     [rsp+28h+arg_0], rdi
0x180005878  xor     ebx, ebx
0x18000587a  lea     r14, g_pHashInfo
0x180005881  cmp     ebx, cs:g_dwHashInfoTotalCount
0x180005887  jnb     short loc_1800058CD
0x180005889  mov     rax, [r14+rbx*8]
0x18000588d  lea     rdi, [r14+rbx*8]
0x180005891  test    rax, rax
0x180005894  jz      short loc_1800058B0
0x180005896  mov     rdx, [rax]; String2
0x180005899  test    rdx, rdx
0x18000589c  jz      short loc_1800058B0
0x18000589e  mov     r8d, 40h ; '@'; MaxCount
0x1800058a4  mov     rcx, rsi; String1
0x1800058a7  call    _wcsnicmp
0x1800058ac  test    eax, eax
0x1800058ae  jz      short loc_1800058B4
0x1800058b0  inc     ebx
0x1800058b2  jmp     short loc_180005881
0x1800058b4  mov     rax, [rdi]
0x1800058b7  mov     rdi, [rsp+28h+arg_0]
0x1800058bc  mov     rbx, [rsp+28h+arg_8]
0x1800058c1  mov     rsi, [rsp+28h+arg_10]
0x1800058c6  add     rsp, 20h
0x1800058ca  pop     r14
0x1800058cc  retn
0x1800058cd  xor     eax, eax
0x1800058cf  jmp     short loc_1800058B7
```
