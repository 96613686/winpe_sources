# StringCopyWorkerW

- ea: `0x18000231c`
- end: `0x18000236d`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002198`
- `0x18000222c`
- `0x180002280`

## callees

- `0x18000231c`

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
0x18000231c  xor     r10d, r10d
0x18000231f  mov     r8, rdx
0x180002322  test    rdx, rdx
0x180002325  jz      short loc_18000234E
0x180002327  mov     rax, [rsp+cchToCopy]
0x18000232c  test    rax, rax
0x18000232f  jz      short loc_18000234E
0x180002331  movzx   edx, word ptr [r9]
0x180002335  test    dx, dx
0x180002338  jz      short loc_18000234E
0x18000233a  mov     [rcx], dx
0x18000233d  add     r9, 2
0x180002341  add     rcx, 2
0x180002345  dec     rax
0x180002348  sub     r8, 1
0x18000234c  jnz     short loc_18000232C
0x18000234e  mov     rax, r8
0x180002351  lea     rdx, [rcx-2]
0x180002355  neg     rax
0x180002358  sbb     eax, eax
0x18000235a  not     eax
0x18000235c  and     eax, 8007007Ah
0x180002361  test    r8, r8
0x180002364  cmovnz  rdx, rcx
0x180002368  mov     [rdx], r10w
0x18000236c  retn
```
