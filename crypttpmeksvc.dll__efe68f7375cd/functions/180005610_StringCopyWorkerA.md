# StringCopyWorkerA

- ea: `0x180005610`
- end: `0x180005659`
- name: `StringCopyWorkerA`
- size: `73`
- prototype: `static HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007878`

## callees

- `0x180005610`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerA(
        STRSAFE_LPSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZCH pszSrc,
        size_t cchToCopy)
{
  __int64 i; // rax
  HRESULT result; // eax
  STRSAFE_LPSTR v8; // rcx

  for ( i = 2147483646; cchDest; --cchDest )
  {
    if ( !i )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --i;
  }
  result = -2147024774;
  if ( cchDest )
    result = 0;
  v8 = pszDest - 1;
  if ( cchDest )
    v8 = pszDest;
  *v8 = 0;
  return result;
}

```

## disassembly

```asm
0x180005610  mov     r10, rcx
0x180005613  mov     eax, 7FFFFFFEh
0x180005618  test    rdx, rdx
0x18000561b  jz      short loc_180005640
0x18000561d  nop     dword ptr [rax]
0x180005620  test    rax, rax
0x180005623  jz      short loc_180005640
0x180005625  movzx   r8d, byte ptr [r9]
0x180005629  test    r8b, r8b
0x18000562c  jz      short loc_180005640
0x18000562e  mov     [r10], r8b
0x180005631  inc     r9
0x180005634  inc     r10
0x180005637  dec     rax
0x18000563a  sub     rdx, 1
0x18000563e  jnz     short loc_180005620
0x180005640  xor     ecx, ecx
0x180005642  mov     eax, 8007007Ah
0x180005647  test    rdx, rdx
0x18000564a  cmovnz  eax, ecx
0x18000564d  lea     rcx, [r10-1]
0x180005651  cmovnz  rcx, r10
0x180005655  mov     byte ptr [rcx], 0
0x180005658  retn
```
