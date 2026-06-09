# StringCopyWorkerW

- ea: `0x180005b58`
- end: `0x180005ba9`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800059fc`
- `0x180005a48`

## callees

- `0x180005b58`

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
0x180005b58  xor     r10d, r10d
0x180005b5b  mov     r8, rdx
0x180005b5e  mov     eax, 7FFFFFFEh
0x180005b63  test    rdx, rdx
0x180005b66  jz      short loc_180005B8A
0x180005b68  test    rax, rax
0x180005b6b  jz      short loc_180005B8A
0x180005b6d  movzx   edx, word ptr [r9]
0x180005b71  test    dx, dx
0x180005b74  jz      short loc_180005B8A
0x180005b76  mov     [rcx], dx
0x180005b79  add     r9, 2
0x180005b7d  add     rcx, 2
0x180005b81  dec     rax
0x180005b84  sub     r8, 1
0x180005b88  jnz     short loc_180005B68
0x180005b8a  mov     rax, r8
0x180005b8d  lea     rdx, [rcx-2]
0x180005b91  neg     rax
0x180005b94  sbb     eax, eax
0x180005b96  not     eax
0x180005b98  and     eax, 8007007Ah
0x180005b9d  test    r8, r8
0x180005ba0  cmovnz  rdx, rcx
0x180005ba4  mov     [rdx], r10w
0x180005ba8  retn
```
