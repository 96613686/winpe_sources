# StringCopyWorkerW

- ea: `0x18002fbfc`
- end: `0x18002fc4d`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002ebd8`
- `0x18002fb70`

## callees

- `0x18002fbfc`

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
0x18002fbfc  xor     r10d, r10d
0x18002fbff  mov     r8, rdx
0x18002fc02  mov     eax, 7FFFFFFEh
0x18002fc07  test    rdx, rdx
0x18002fc0a  jz      short loc_18002FC2E
0x18002fc0c  test    rax, rax
0x18002fc0f  jz      short loc_18002FC2E
0x18002fc11  movzx   edx, word ptr [r9]
0x18002fc15  test    dx, dx
0x18002fc18  jz      short loc_18002FC2E
0x18002fc1a  mov     [rcx], dx
0x18002fc1d  add     r9, 2
0x18002fc21  add     rcx, 2
0x18002fc25  dec     rax
0x18002fc28  sub     r8, 1
0x18002fc2c  jnz     short loc_18002FC0C
0x18002fc2e  mov     rax, r8
0x18002fc31  lea     rdx, [rcx-2]
0x18002fc35  neg     rax
0x18002fc38  sbb     eax, eax
0x18002fc3a  not     eax
0x18002fc3c  and     eax, 8007007Ah
0x18002fc41  test    r8, r8
0x18002fc44  cmovnz  rdx, rcx
0x18002fc48  mov     [rdx], r10w
0x18002fc4c  retn
```
