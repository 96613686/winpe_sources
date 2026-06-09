# StringCopyWorkerW_0

- ea: `0x140011f54`
- end: `0x140011fca`
- name: `StringCopyWorkerW_0`
- size: `118`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140011db8`
- `0x140011e0c`

## callees

- `0x140011f54`

## pseudocode

```c
HRESULT __stdcall StringCopyWorkerW_0(
        STRSAFE_LPWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t i; // rdx
  size_t v9; // r8
  STRSAFE_LPWSTR v10; // rdx
  HRESULT result; // eax

  for ( i = 0; cchDest; --cchDest )
  {
    if ( !cchToCopy )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --cchToCopy;
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
0x140011f54  mov     [rsp+arg_0], rbx
0x140011f59  mov     r10, rdx
0x140011f5c  xor     ebx, ebx
0x140011f5e  mov     r11, r8
0x140011f61  mov     edx, ebx
0x140011f63  test    r10, r10
0x140011f66  jz      short loc_140011F94
0x140011f68  mov     rax, [rsp+arg_20]
0x140011f6d  test    rax, rax
0x140011f70  jz      short loc_140011F94
0x140011f72  movzx   r8d, word ptr [r9]
0x140011f76  test    r8w, r8w
0x140011f7a  jz      short loc_140011F94
0x140011f7c  mov     [rcx], r8w
0x140011f80  add     r9, 2
0x140011f84  add     rcx, 2
0x140011f88  dec     rax
0x140011f8b  inc     rdx
0x140011f8e  sub     r10, 1
0x140011f92  jnz     short loc_140011F6D
0x140011f94  test    r10, r10
0x140011f97  lea     r8, [rdx-1]
0x140011f9b  mov     rax, r10
0x140011f9e  cmovnz  r8, rdx
0x140011fa2  neg     rax
0x140011fa5  lea     rdx, [rcx-2]
0x140011fa9  sbb     eax, eax
0x140011fab  not     eax
0x140011fad  and     eax, 8007007Ah
0x140011fb2  test    r10, r10
0x140011fb5  cmovnz  rdx, rcx
0x140011fb9  mov     [rdx], bx
0x140011fbc  test    r11, r11
0x140011fbf  jz      short loc_140011FC4
0x140011fc1  mov     [r11], r8
0x140011fc4  mov     rbx, [rsp+arg_0]
0x140011fc9  retn
```
