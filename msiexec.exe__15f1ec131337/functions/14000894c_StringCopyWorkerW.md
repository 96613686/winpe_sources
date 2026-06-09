# StringCopyWorkerW

- ea: `0x14000894c`
- end: `0x14000899d`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1400011e4`
- `0x140006350`
- `0x140006e10`
- `0x1400080c4`
- `0x1400086f8`
- `0x140008768`
- `0x1400087bc`

## callees

- `0x14000894c`

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
0x14000894c  xor     r10d, r10d
0x14000894f  mov     r8, rdx
0x140008952  test    rdx, rdx
0x140008955  jz      short loc_14000897E
0x140008957  mov     rax, [rsp+cchToCopy]
0x14000895c  test    rax, rax
0x14000895f  jz      short loc_14000897E
0x140008961  movzx   edx, word ptr [r9]
0x140008965  test    dx, dx
0x140008968  jz      short loc_14000897E
0x14000896a  mov     [rcx], dx
0x14000896d  add     r9, 2
0x140008971  add     rcx, 2
0x140008975  dec     rax
0x140008978  sub     r8, 1
0x14000897c  jnz     short loc_14000895C
0x14000897e  mov     rax, r8
0x140008981  lea     rdx, [rcx-2]
0x140008985  neg     rax
0x140008988  sbb     eax, eax
0x14000898a  not     eax
0x14000898c  and     eax, 8007007Ah
0x140008991  test    r8, r8
0x140008994  cmovnz  rdx, rcx
0x140008998  mov     [rdx], r10w
0x14000899c  retn
```
