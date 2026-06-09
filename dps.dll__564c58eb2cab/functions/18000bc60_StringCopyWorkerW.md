# StringCopyWorkerW

- ea: `0x18000bc60`
- end: `0x18000bcb1`
- name: `StringCopyWorkerW`
- size: `81`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bbd4`
- `0x18000bc1c`

## callees

- `0x18000bc60`

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
0x18000bc60  xor     r10d, r10d
0x18000bc63  mov     r8, rdx
0x18000bc66  mov     eax, 7FFFFFFEh
0x18000bc6b  test    rdx, rdx
0x18000bc6e  jz      short loc_18000BC92
0x18000bc70  test    rax, rax
0x18000bc73  jz      short loc_18000BC92
0x18000bc75  movzx   edx, word ptr [r9]
0x18000bc79  test    dx, dx
0x18000bc7c  jz      short loc_18000BC92
0x18000bc7e  mov     [rcx], dx
0x18000bc81  add     r9, 2
0x18000bc85  add     rcx, 2
0x18000bc89  dec     rax
0x18000bc8c  sub     r8, 1
0x18000bc90  jnz     short loc_18000BC70
0x18000bc92  mov     rax, r8
0x18000bc95  lea     rdx, [rcx-2]
0x18000bc99  neg     rax
0x18000bc9c  sbb     eax, eax
0x18000bc9e  not     eax
0x18000bca0  and     eax, 8007007Ah
0x18000bca5  test    r8, r8
0x18000bca8  cmovnz  rdx, rcx
0x18000bcac  mov     [rdx], r10w
0x18000bcb0  retn
```
