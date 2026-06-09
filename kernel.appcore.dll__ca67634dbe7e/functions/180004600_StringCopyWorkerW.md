# StringCopyWorkerW

- ea: `0x180004600`
- end: `0x180004678`
- name: `StringCopyWorkerW`
- size: `120`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005f54`

## callees

- `0x180004600`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t v7; // rcx
  size_t v8; // r10
  __int64 i; // rax
  size_t v10; // r8
  STRSAFE_LPWSTR v11; // rdx
  HRESULT result; // eax

  v7 = 0;
  v8 = cchDest;
  for ( i = 2147483646; v8; --v8 )
  {
    if ( !i )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --i;
    ++v7;
  }
  v10 = v7 - 1;
  v11 = pszDest - 1;
  result = -2147024774;
  if ( v8 )
  {
    v10 = v7;
    v11 = pszDest;
    result = 0;
  }
  *v11 = 0;
  if ( pcchNewDestLength )
    *pcchNewDestLength = v10;
  return result;
}

```

## disassembly

```asm
0x180004600  mov     [rsp+arg_0], rbx
0x180004605  mov     r11, rcx
0x180004608  mov     rbx, r8
0x18000460b  xor     ecx, ecx
0x18000460d  mov     r10, rdx
0x180004610  mov     eax, 7FFFFFFEh
0x180004615  test    rdx, rdx
0x180004618  jz      short loc_180004647
0x18000461a  nop     word ptr [rax+rax+00h]
0x180004620  test    rax, rax
0x180004623  jz      short loc_180004647
0x180004625  movzx   r8d, word ptr [r9]
0x180004629  test    r8w, r8w
0x18000462d  jz      short loc_180004647
0x18000462f  mov     [r11], r8w
0x180004633  add     r9, 2
0x180004637  add     r11, 2
0x18000463b  dec     rax
0x18000463e  inc     rcx
0x180004641  sub     r10, 1
0x180004645  jnz     short loc_180004620
0x180004647  test    r10, r10
0x18000464a  lea     r8, [rcx-1]
0x18000464e  lea     rdx, [r11-2]
0x180004652  mov     eax, 8007007Ah
0x180004657  cmovnz  r8, rcx
0x18000465b  xor     ecx, ecx
0x18000465d  test    r10, r10
0x180004660  cmovnz  rdx, r11
0x180004664  cmovnz  eax, ecx
0x180004667  mov     [rdx], cx
0x18000466a  test    rbx, rbx
0x18000466d  jz      short loc_180004672
0x18000466f  mov     [rbx], r8
0x180004672  mov     rbx, [rsp+arg_0]
0x180004677  retn
```
