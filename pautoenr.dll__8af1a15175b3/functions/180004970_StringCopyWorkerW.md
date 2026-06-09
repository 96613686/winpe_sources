# StringCopyWorkerW

- ea: `0x180004970`
- end: `0x1800049bd`
- name: `StringCopyWorkerW`
- size: `77`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005040`

## callees

- `0x180004970`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t v5; // r10
  __int64 i; // r8
  STRSAFE_LPWSTR v8; // rdx
  HRESULT result; // eax

  v5 = cchDest;
  for ( i = 2147483646; v5; --v5 )
  {
    if ( !i )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --i;
  }
  v8 = pszDest - 1;
  result = -2147024774;
  if ( v5 )
  {
    v8 = pszDest;
    result = 0;
  }
  *v8 = 0;
  return result;
}

```

## disassembly

```asm
0x180004970  mov     r10, rdx
0x180004973  mov     r11, rcx
0x180004976  mov     r8d, 7FFFFFFEh
0x18000497c  test    rdx, rdx
0x18000497f  jz      short loc_1800049A4
0x180004981  test    r8, r8
0x180004984  jz      short loc_1800049A4
0x180004986  movzx   eax, word ptr [r9]
0x18000498a  test    ax, ax
0x18000498d  jz      short loc_1800049A4
0x18000498f  mov     [r11], ax
0x180004993  add     r9, 2
0x180004997  add     r11, 2
0x18000499b  dec     r8
0x18000499e  sub     r10, 1
0x1800049a2  jnz     short loc_180004981
0x1800049a4  xor     ecx, ecx
0x1800049a6  lea     rdx, [r11-2]
0x1800049aa  test    r10, r10
0x1800049ad  mov     eax, 8007007Ah
0x1800049b2  cmovnz  rdx, r11
0x1800049b6  cmovnz  eax, ecx
0x1800049b9  mov     [rdx], cx
0x1800049bc  retn
```
