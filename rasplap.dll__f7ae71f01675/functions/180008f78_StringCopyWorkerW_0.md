# StringCopyWorkerW_0

- ea: `0x180008f78`
- end: `0x180008fee`
- name: `StringCopyWorkerW_0`
- size: `118`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008c5c`

## callees

- `0x180008f78`

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
0x180008f78  mov     [rsp+arg_0], rbx
0x180008f7d  mov     r10, rdx
0x180008f80  xor     ebx, ebx
0x180008f82  mov     r11, r8
0x180008f85  mov     eax, 7FFFFFFEh
0x180008f8a  mov     edx, ebx
0x180008f8c  test    r10, r10
0x180008f8f  jz      short loc_180008FB8
0x180008f91  test    rax, rax
0x180008f94  jz      short loc_180008FB8
0x180008f96  movzx   r8d, word ptr [r9]
0x180008f9a  test    r8w, r8w
0x180008f9e  jz      short loc_180008FB8
0x180008fa0  mov     [rcx], r8w
0x180008fa4  add     r9, 2
0x180008fa8  add     rcx, 2
0x180008fac  dec     rax
0x180008faf  inc     rdx
0x180008fb2  sub     r10, 1
0x180008fb6  jnz     short loc_180008F91
0x180008fb8  test    r10, r10
0x180008fbb  lea     r8, [rdx-1]
0x180008fbf  mov     rax, r10
0x180008fc2  cmovnz  r8, rdx
0x180008fc6  neg     rax
0x180008fc9  lea     rdx, [rcx-2]
0x180008fcd  sbb     eax, eax
0x180008fcf  not     eax
0x180008fd1  and     eax, 8007007Ah
0x180008fd6  test    r10, r10
0x180008fd9  cmovnz  rdx, rcx
0x180008fdd  mov     [rdx], bx
0x180008fe0  test    r11, r11
0x180008fe3  jz      short loc_180008FE8
0x180008fe5  mov     [r11], r8
0x180008fe8  mov     rbx, [rsp+arg_0]
0x180008fed  retn
```
