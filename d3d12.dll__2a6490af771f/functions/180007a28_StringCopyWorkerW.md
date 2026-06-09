# StringCopyWorkerW

- ea: `0x180007a28`
- end: `0x180007a79`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c9c8`

## callees

- `0x180007a28`

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
0x180007a28  xor     r10d, r10d
0x180007a2b  mov     r8, rdx
0x180007a2e  mov     eax, 7FFFFFFEh
0x180007a33  test    rdx, rdx
0x180007a36  jz      short loc_180007A5A
0x180007a38  test    rax, rax
0x180007a3b  jz      short loc_180007A5A
0x180007a3d  movzx   edx, word ptr [r9]
0x180007a41  test    dx, dx
0x180007a44  jz      short loc_180007A5A
0x180007a46  mov     [rcx], dx
0x180007a49  add     r9, 2
0x180007a4d  add     rcx, 2
0x180007a51  dec     rax
0x180007a54  sub     r8, 1
0x180007a58  jnz     short loc_180007A38
0x180007a5a  mov     rax, r8
0x180007a5d  lea     rdx, [rcx-2]
0x180007a61  neg     rax
0x180007a64  sbb     eax, eax
0x180007a66  not     eax
0x180007a68  and     eax, 8007007Ah
0x180007a6d  test    r8, r8
0x180007a70  cmovnz  rdx, rcx
0x180007a74  mov     [rdx], r10w
0x180007a78  retn
```
