# StringCopyWorkerW_0

- ea: `0x180015eb4`
- end: `0x180015f2a`
- name: `StringCopyWorkerW_0`
- size: `118`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180015c64`
- `0x180015d38`

## callees

- `0x180015eb4`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW_0(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  __int64 v7; // rax
  size_t i; // rdx
  size_t v9; // r8
  STRSAFE_LPWSTR v10; // rdx
  HRESULT result; // eax

  v7 = 2147483646;
  for ( i = 0; cchDest; --cchDest )
  {
    if ( !v7 )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --v7;
    ++i;
  }
  v9 = i - 1;
  if ( cchDest )
    v9 = i;
  v10 = pszDest - 1;
  result = cchDest == 0 ? 0x8007007A : 0;
  if ( cchDest )
    v10 = pszDest;
  *v10 = 0;
  if ( pcchNewDestLength )
    *pcchNewDestLength = v9;
  return result;
}

```

## disassembly

```asm
0x180015eb4  mov     [rsp+arg_0], rbx
0x180015eb9  mov     r10, rdx
0x180015ebc  xor     ebx, ebx
0x180015ebe  mov     r11, r8
0x180015ec1  mov     eax, 7FFFFFFEh
0x180015ec6  mov     edx, ebx
0x180015ec8  test    r10, r10
0x180015ecb  jz      short loc_180015EF4
0x180015ecd  test    rax, rax
0x180015ed0  jz      short loc_180015EF4
0x180015ed2  movzx   r8d, word ptr [r9]
0x180015ed6  test    r8w, r8w
0x180015eda  jz      short loc_180015EF4
0x180015edc  mov     [rcx], r8w
0x180015ee0  add     r9, 2
0x180015ee4  add     rcx, 2
0x180015ee8  dec     rax
0x180015eeb  inc     rdx
0x180015eee  sub     r10, 1
0x180015ef2  jnz     short loc_180015ECD
0x180015ef4  test    r10, r10
0x180015ef7  lea     r8, [rdx-1]
0x180015efb  mov     rax, r10
0x180015efe  cmovnz  r8, rdx
0x180015f02  neg     rax
0x180015f05  lea     rdx, [rcx-2]
0x180015f09  sbb     eax, eax
0x180015f0b  not     eax
0x180015f0d  and     eax, 8007007Ah
0x180015f12  test    r10, r10
0x180015f15  cmovnz  rdx, rcx
0x180015f19  mov     [rdx], bx
0x180015f1c  test    r11, r11
0x180015f1f  jz      short loc_180015F24
0x180015f21  mov     [r11], r8
0x180015f24  mov     rbx, [rsp+arg_0]
0x180015f29  retn
```
