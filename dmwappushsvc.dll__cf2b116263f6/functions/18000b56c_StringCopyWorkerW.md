# StringCopyWorkerW

- ea: `0x18000b56c`
- end: `0x18000b5bd`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b4d8`

## callees

- `0x18000b56c`

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
0x18000b56c  xor     r10d, r10d
0x18000b56f  mov     r8, rdx
0x18000b572  mov     eax, 7FFFFFFEh
0x18000b577  test    rdx, rdx
0x18000b57a  jz      short loc_18000B59E
0x18000b57c  test    rax, rax
0x18000b57f  jz      short loc_18000B59E
0x18000b581  movzx   edx, word ptr [r9]
0x18000b585  test    dx, dx
0x18000b588  jz      short loc_18000B59E
0x18000b58a  mov     [rcx], dx
0x18000b58d  add     r9, 2
0x18000b591  add     rcx, 2
0x18000b595  dec     rax
0x18000b598  sub     r8, 1
0x18000b59c  jnz     short loc_18000B57C
0x18000b59e  mov     rax, r8
0x18000b5a1  lea     rdx, [rcx-2]
0x18000b5a5  neg     rax
0x18000b5a8  sbb     eax, eax
0x18000b5aa  not     eax
0x18000b5ac  and     eax, 8007007Ah
0x18000b5b1  test    r8, r8
0x18000b5b4  cmovnz  rdx, rcx
0x18000b5b8  mov     [rdx], r10w
0x18000b5bc  retn
```
