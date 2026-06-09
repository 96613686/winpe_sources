# StringCopyWorkerW

- ea: `0x140006048`
- end: `0x140006099`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005f24`
- `0x140005fa0`

## callees

- `0x140006048`

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
0x140006048  xor     r10d, r10d
0x14000604b  mov     r8, rdx
0x14000604e  mov     eax, 7FFFFFFEh
0x140006053  test    rdx, rdx
0x140006056  jz      short loc_14000607A
0x140006058  test    rax, rax
0x14000605b  jz      short loc_14000607A
0x14000605d  movzx   edx, word ptr [r9]
0x140006061  test    dx, dx
0x140006064  jz      short loc_14000607A
0x140006066  mov     [rcx], dx
0x140006069  add     r9, 2
0x14000606d  add     rcx, 2
0x140006071  dec     rax
0x140006074  sub     r8, 1
0x140006078  jnz     short loc_140006058
0x14000607a  mov     rax, r8
0x14000607d  lea     rdx, [rcx-2]
0x140006081  neg     rax
0x140006084  sbb     eax, eax
0x140006086  not     eax
0x140006088  and     eax, 8007007Ah
0x14000608d  test    r8, r8
0x140006090  cmovnz  rdx, rcx
0x140006094  mov     [rdx], r10w
0x140006098  retn
```
