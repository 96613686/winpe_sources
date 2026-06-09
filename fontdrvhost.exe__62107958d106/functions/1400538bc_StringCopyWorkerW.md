# StringCopyWorkerW

- ea: `0x1400538bc`
- end: `0x14005390d`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140052a4c`
- `0x1400537e8`
- `0x140053878`
- `0x1400783b8`
- `0x14007accc`
- `0x14007b05c`

## callees

- `0x1400538bc`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t v5; // r8
  __int64 i; // rax
  STRSAFE_LPWSTR v7; // rdx
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
  v7 = pszDest - 1;
  result = v5 == 0 ? 0x8007007A : 0;
  if ( v5 )
    v7 = pszDest;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x1400538bc  xor     r10d, r10d
0x1400538bf  mov     r8, rdx
0x1400538c2  mov     eax, 7FFFFFFEh
0x1400538c7  test    rdx, rdx
0x1400538ca  jz      short loc_1400538EE
0x1400538cc  test    rax, rax
0x1400538cf  jz      short loc_1400538EE
0x1400538d1  movzx   edx, word ptr [r9]
0x1400538d5  test    dx, dx
0x1400538d8  jz      short loc_1400538EE
0x1400538da  mov     [rcx], dx
0x1400538dd  add     r9, 2
0x1400538e1  add     rcx, 2
0x1400538e5  dec     rax
0x1400538e8  sub     r8, 1
0x1400538ec  jnz     short loc_1400538CC
0x1400538ee  mov     rax, r8
0x1400538f1  lea     rdx, [rcx-2]
0x1400538f5  neg     rax
0x1400538f8  sbb     eax, eax
0x1400538fa  not     eax
0x1400538fc  and     eax, 8007007Ah
0x140053901  test    r8, r8
0x140053904  cmovnz  rdx, rcx
0x140053908  mov     [rdx], r10w
0x14005390c  retn
```
