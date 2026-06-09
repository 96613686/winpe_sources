# StringCopyWorkerW

- ea: `0x1800035b0`
- end: `0x1800035fd`
- name: `StringCopyWorkerW`
- size: `77`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003570`

## callees

- `0x1800035b0`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t i; // r10
  STRSAFE_LPWSTR v8; // rdx
  HRESULT result; // eax

  for ( i = cchDest; i; --i )
  {
    if ( !cchToCopy )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --cchToCopy;
  }
  v8 = pszDest - 1;
  result = -2147024774;
  if ( i )
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
0x1800035b0  mov     r10, rdx
0x1800035b3  mov     r11, rcx
0x1800035b6  test    rdx, rdx
0x1800035b9  jz      short loc_1800035E4
0x1800035bb  mov     rax, [rsp+cchToCopy]
0x1800035c0  test    rax, rax
0x1800035c3  jz      short loc_1800035E4
0x1800035c5  movzx   r8d, word ptr [r9]
0x1800035c9  test    r8w, r8w
0x1800035cd  jz      short loc_1800035E4
0x1800035cf  mov     [r11], r8w
0x1800035d3  add     r9, 2
0x1800035d7  add     r11, 2
0x1800035db  dec     rax
0x1800035de  sub     r10, 1
0x1800035e2  jnz     short loc_1800035C0
0x1800035e4  xor     ecx, ecx
0x1800035e6  lea     rdx, [r11-2]
0x1800035ea  test    r10, r10
0x1800035ed  mov     eax, 8007007Ah
0x1800035f2  cmovnz  rdx, r11
0x1800035f6  cmovnz  eax, ecx
0x1800035f9  mov     [rdx], cx
0x1800035fc  retn
```
