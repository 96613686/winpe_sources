# StringCopyWorkerW

- ea: `0x180014c0c`
- end: `0x180014c82`
- name: `StringCopyWorkerW`
- size: `118`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800250fc`
- `0x1800251ac`

## callees

- `0x180014c0c`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  __int64 v7; // rax
  size_t i; // rdx
  size_t v9; // r8
  STRSAFE_LPWSTR v10; // rdx
  HRESULT result; // eax

  v7 = 2147483646;
  for ( i = 0; cchDest; --cchDest )
  {
    if ( !v7 )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --v7;
    ++i;
  }
  v9 = i - 1;
  if ( cchDest )
    v9 = i;
  v10 = pszDest - 1;
  result = cchDest == 0 ? 0x8007007A : 0;
  if ( cchDest )
    v10 = pszDest;
  *v10 = 0;
  if ( pcchNewDestLength )
    *pcchNewDestLength = v9;
  return result;
}

```

## disassembly

```asm
0x180014c0c  mov     [rsp+arg_0], rbx
0x180014c11  mov     r10, rdx
0x180014c14  xor     ebx, ebx
0x180014c16  mov     r11, r8
0x180014c19  mov     eax, 7FFFFFFEh
0x180014c1e  mov     edx, ebx
0x180014c20  test    r10, r10
0x180014c23  jz      short loc_180014C4C
0x180014c25  test    rax, rax
0x180014c28  jz      short loc_180014C4C
0x180014c2a  movzx   r8d, word ptr [r9]
0x180014c2e  test    r8w, r8w
0x180014c32  jz      short loc_180014C4C
0x180014c34  mov     [rcx], r8w
0x180014c38  add     r9, 2
0x180014c3c  add     rcx, 2
0x180014c40  dec     rax
0x180014c43  inc     rdx
0x180014c46  sub     r10, 1
0x180014c4a  jnz     short loc_180014C25
0x180014c4c  test    r10, r10
0x180014c4f  lea     r8, [rdx-1]
0x180014c53  mov     rax, r10
0x180014c56  cmovnz  r8, rdx
0x180014c5a  neg     rax
0x180014c5d  lea     rdx, [rcx-2]
0x180014c61  sbb     eax, eax
0x180014c63  not     eax
0x180014c65  and     eax, 8007007Ah
0x180014c6a  test    r10, r10
0x180014c6d  cmovnz  rdx, rcx
0x180014c71  mov     [rdx], bx
0x180014c74  test    r11, r11
0x180014c77  jz      short loc_180014C7C
0x180014c79  mov     [r11], r8
0x180014c7c  mov     rbx, [rsp+arg_0]
0x180014c81  retn
```
