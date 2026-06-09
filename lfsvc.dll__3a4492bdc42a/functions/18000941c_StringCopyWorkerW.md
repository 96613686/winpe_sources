# StringCopyWorkerW

- ea: `0x18000941c`
- end: `0x18000946d`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180006698`
- `0x1800092e0`
- `0x1800097f4`

## callees

- `0x18000941c`

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
0x18000941c  xor     r10d, r10d
0x18000941f  mov     r8, rdx
0x180009422  mov     eax, 7FFFFFFEh
0x180009427  test    rdx, rdx
0x18000942a  jz      short loc_18000944E
0x18000942c  test    rax, rax
0x18000942f  jz      short loc_18000944E
0x180009431  movzx   edx, word ptr [r9]
0x180009435  test    dx, dx
0x180009438  jz      short loc_18000944E
0x18000943a  mov     [rcx], dx
0x18000943d  add     r9, 2
0x180009441  add     rcx, 2
0x180009445  dec     rax
0x180009448  sub     r8, 1
0x18000944c  jnz     short loc_18000942C
0x18000944e  mov     rax, r8
0x180009451  lea     rdx, [rcx-2]
0x180009455  neg     rax
0x180009458  sbb     eax, eax
0x18000945a  not     eax
0x18000945c  and     eax, 8007007Ah
0x180009461  test    r8, r8
0x180009464  cmovnz  rdx, rcx
0x180009468  mov     [rdx], r10w
0x18000946c  retn
```
