# StringCopyWorkerW

- ea: `0x180005720`
- end: `0x180005771`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005680`
- `0x1800056d4`

## callees

- `0x180005720`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t i; // r8
  STRSAFE_LPWSTR v7; // rdx
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
  v7 = pszDest - 1;
  result = i == 0 ? 0x8007007A : 0;
  if ( i )
    v7 = pszDest;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x180005720  xor     r10d, r10d
0x180005723  mov     r8, rdx
0x180005726  test    rdx, rdx
0x180005729  jz      short loc_180005752
0x18000572b  mov     rax, [rsp+cchToCopy]
0x180005730  test    rax, rax
0x180005733  jz      short loc_180005752
0x180005735  movzx   edx, word ptr [r9]
0x180005739  test    dx, dx
0x18000573c  jz      short loc_180005752
0x18000573e  mov     [rcx], dx
0x180005741  add     r9, 2
0x180005745  add     rcx, 2
0x180005749  dec     rax
0x18000574c  sub     r8, 1
0x180005750  jnz     short loc_180005730
0x180005752  mov     rax, r8
0x180005755  lea     rdx, [rcx-2]
0x180005759  neg     rax
0x18000575c  sbb     eax, eax
0x18000575e  not     eax
0x180005760  and     eax, 8007007Ah
0x180005765  test    r8, r8
0x180005768  cmovnz  rdx, rcx
0x18000576c  mov     [rdx], r10w
0x180005770  retn
```
