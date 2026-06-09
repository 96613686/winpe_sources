# StringCopyWorkerW

- ea: `0x14000c374`
- end: `0x14000c3c5`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c22c`
- `0x14000c2a8`

## callees

- `0x14000c374`

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
0x14000c374  xor     r10d, r10d
0x14000c377  mov     r8, rdx
0x14000c37a  mov     eax, 7FFFFFFEh
0x14000c37f  test    rdx, rdx
0x14000c382  jz      short loc_14000C3A6
0x14000c384  test    rax, rax
0x14000c387  jz      short loc_14000C3A6
0x14000c389  movzx   edx, word ptr [r9]
0x14000c38d  test    dx, dx
0x14000c390  jz      short loc_14000C3A6
0x14000c392  mov     [rcx], dx
0x14000c395  add     r9, 2
0x14000c399  add     rcx, 2
0x14000c39d  dec     rax
0x14000c3a0  sub     r8, 1
0x14000c3a4  jnz     short loc_14000C384
0x14000c3a6  mov     rax, r8
0x14000c3a9  lea     rdx, [rcx-2]
0x14000c3ad  neg     rax
0x14000c3b0  sbb     eax, eax
0x14000c3b2  not     eax
0x14000c3b4  and     eax, 8007007Ah
0x14000c3b9  test    r8, r8
0x14000c3bc  cmovnz  rdx, rcx
0x14000c3c0  mov     [rdx], r10w
0x14000c3c4  retn
```
