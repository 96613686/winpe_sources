# RtlStringCopyWorkerA

- ea: `0x140003fc8`
- end: `0x140004011`
- name: `RtlStringCopyWorkerA`
- size: `73`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003f54`
- `0x140018678`

## callees

- `0x140003fc8`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCopyWorkerA(
        NTSTRSAFE_PSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZCH pszSrc,
        size_t cchToCopy)
{
  __int64 i; // rax
  NTSTRSAFE_PSTR v7; // rcx
  NTSTATUS result; // eax

  for ( i = 2147483646; cchDest; --cchDest )
  {
    if ( !i )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --i;
  }
  v7 = pszDest - 1;
  result = cchDest == 0 ? 0x80000005 : 0;
  if ( cchDest )
    v7 = pszDest;
  *v7 = 0;
  return result;
}

```

## disassembly

```asm
0x140003fc8  mov     r8, rcx
0x140003fcb  mov     eax, 7FFFFFFEh
0x140003fd0  test    rdx, rdx
0x140003fd3  jz      short loc_140003FF3
0x140003fd5  test    rax, rax
0x140003fd8  jz      short loc_140003FF3
0x140003fda  mov     cl, [r9]
0x140003fdd  test    cl, cl
0x140003fdf  jz      short loc_140003FF3
0x140003fe1  mov     [r8], cl
0x140003fe4  inc     r9
0x140003fe7  inc     r8
0x140003fea  dec     rax
0x140003fed  sub     rdx, 1
0x140003ff1  jnz     short loc_140003FD5
0x140003ff3  mov     rax, rdx
0x140003ff6  lea     rcx, [r8-1]
0x140003ffa  neg     rax
0x140003ffd  sbb     eax, eax
0x140003fff  not     eax
0x140004001  and     eax, 80000005h
0x140004006  test    rdx, rdx
0x140004009  cmovnz  rcx, r8
0x14000400d  mov     byte ptr [rcx], 0
0x140004010  retn
```
