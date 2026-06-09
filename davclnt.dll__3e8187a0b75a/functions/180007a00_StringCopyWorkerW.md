# StringCopyWorkerW

- ea: `0x180007a00`
- end: `0x180007a7c`
- name: `StringCopyWorkerW`
- size: `124`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180009bb0`
- `0x18000cb10`
- `0x18000f048`
- `0x18001068c`
- `0x1800109a4`

## callees

- `0x180007a00`

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
  size_t i; // r11
  size_t v10; // r8
  STRSAFE_LPWSTR v11; // rdx
  HRESULT result; // eax

  v7 = 0;
  for ( i = cchDest; i; --i )
  {
    if ( !cchToCopy )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --cchToCopy;
    ++v7;
  }
  v10 = v7 - 1;
  v11 = pszDest - 1;
  result = -2147024774;
  if ( i )
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
0x180007a00  mov     [rsp+arg_0], rbx
0x180007a05  mov     [rsp+arg_8], rdi
0x180007a0a  mov     rbx, rcx
0x180007a0d  mov     rdi, r8
0x180007a10  xor     ecx, ecx
0x180007a12  mov     r11, rdx
0x180007a15  test    rdx, rdx
0x180007a18  jz      short loc_180007A44
0x180007a1a  mov     r10, [rsp+arg_20]
0x180007a1f  test    r10, r10
0x180007a22  jz      short loc_180007A44
0x180007a24  movzx   eax, word ptr [r9]
0x180007a28  test    ax, ax
0x180007a2b  jz      short loc_180007A44
0x180007a2d  mov     [rbx], ax
0x180007a30  add     r9, 2
0x180007a34  add     rbx, 2
0x180007a38  dec     r10
0x180007a3b  inc     rcx
0x180007a3e  sub     r11, 1
0x180007a42  jnz     short loc_180007A1F
0x180007a44  test    r11, r11
0x180007a47  lea     r8, [rcx-1]
0x180007a4b  lea     rdx, [rbx-2]
0x180007a4f  mov     eax, 8007007Ah
0x180007a54  cmovnz  r8, rcx
0x180007a58  xor     ecx, ecx
0x180007a5a  test    r11, r11
0x180007a5d  cmovnz  rdx, rbx
0x180007a61  cmovnz  eax, ecx
0x180007a64  mov     [rdx], cx
0x180007a67  test    rdi, rdi
0x180007a6a  jnz     short loc_180007A77
0x180007a6c  mov     rbx, [rsp+arg_0]
0x180007a71  mov     rdi, [rsp+arg_8]
0x180007a76  retn
0x180007a77  mov     [rdi], r8
0x180007a7a  jmp     short loc_180007A6C
```
