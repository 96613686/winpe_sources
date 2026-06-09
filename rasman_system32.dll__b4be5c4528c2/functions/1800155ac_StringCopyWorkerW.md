# StringCopyWorkerW

- ea: `0x1800155ac`
- end: `0x180015623`
- name: `StringCopyWorkerW`
- size: `119`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180025fa8`
- `0x180026058`

## callees

- `0x1800155ac`

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
0x1800155ac  mov     [rsp+arg_0], rbx
0x1800155b1  mov     r10, rdx
0x1800155b4  xor     ebx, ebx
0x1800155b6  mov     r11, r8
0x1800155b9  mov     eax, 7FFFFFFEh
0x1800155be  mov     edx, ebx
0x1800155c0  test    r10, r10
0x1800155c3  jz      short loc_1800155EC
0x1800155c5  test    rax, rax
0x1800155c8  jz      short loc_1800155EC
0x1800155ca  movzx   r8d, word ptr [r9]
0x1800155ce  test    r8w, r8w
0x1800155d2  jz      short loc_1800155EC
0x1800155d4  mov     [rcx], r8w
0x1800155d8  add     r9, 2
0x1800155dc  add     rcx, 2
0x1800155e0  dec     rax
0x1800155e3  inc     rdx
0x1800155e6  sub     r10, 1
0x1800155ea  jnz     short loc_1800155C5
0x1800155ec  test    r10, r10
0x1800155ef  lea     r8, [rdx-1]
0x1800155f3  mov     rax, r10
0x1800155f6  cmovnz  r8, rdx
0x1800155fa  neg     rax
0x1800155fd  lea     rdx, [rcx-2]
0x180015601  sbb     eax, eax
0x180015603  not     eax
0x180015605  and     eax, 8007007Ah
0x18001560a  test    r10, r10
0x18001560d  cmovnz  rdx, rcx
0x180015611  mov     [rdx], bx
0x180015614  test    r11, r11
0x180015617  jz      short loc_18001561C
0x180015619  mov     [r11], r8
0x18001561c  mov     rbx, [rsp+arg_0]
0x180015621  retn
```
