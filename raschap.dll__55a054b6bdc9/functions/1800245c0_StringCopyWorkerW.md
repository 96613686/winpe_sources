# StringCopyWorkerW

- ea: `0x1800245c0`
- end: `0x180024611`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180024520`

## callees

- `0x1800245c0`

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
0x1800245c0  xor     r10d, r10d
0x1800245c3  mov     r8, rdx
0x1800245c6  mov     eax, 7FFFFFFEh
0x1800245cb  test    rdx, rdx
0x1800245ce  jz      short loc_1800245F2
0x1800245d0  test    rax, rax
0x1800245d3  jz      short loc_1800245F2
0x1800245d5  movzx   edx, word ptr [r9]
0x1800245d9  test    dx, dx
0x1800245dc  jz      short loc_1800245F2
0x1800245de  mov     [rcx], dx
0x1800245e1  add     r9, 2
0x1800245e5  add     rcx, 2
0x1800245e9  dec     rax
0x1800245ec  sub     r8, 1
0x1800245f0  jnz     short loc_1800245D0
0x1800245f2  mov     rax, r8
0x1800245f5  lea     rdx, [rcx-2]
0x1800245f9  neg     rax
0x1800245fc  sbb     eax, eax
0x1800245fe  not     eax
0x180024600  and     eax, 8007007Ah
0x180024605  test    r8, r8
0x180024608  cmovnz  rdx, rcx
0x18002460c  mov     [rdx], r10w
0x180024610  retn
```
