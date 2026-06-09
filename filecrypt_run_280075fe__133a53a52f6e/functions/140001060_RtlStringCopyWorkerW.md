# RtlStringCopyWorkerW

- ea: `0x140001060`
- end: `0x1400010ad`
- name: `RtlStringCopyWorkerW`
- size: `77`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001010`
- `0x140003454`
- `0x140011150`

## callees

- `0x140001060`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCopyWorkerW(
        NTSTRSAFE_PWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  size_t i; // r10
  NTSTRSAFE_PWSTR v8; // rdx
  NTSTATUS result; // eax

  for ( i = cchDest; i; --i )
  {
    if ( !cchToCopy )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --cchToCopy;
  }
  v8 = pszDest - 1;
  result = -2147483643;
  if ( i )
  {
    v8 = pszDest;
    result = 0;
  }
  *v8 = 0;
  return result;
}

```

## disassembly

```asm
0x140001060  mov     r10, rdx
0x140001063  mov     r11, rcx
0x140001066  test    rdx, rdx
0x140001069  jz      short loc_140001094
0x14000106b  mov     rax, [rsp+cchToCopy]
0x140001070  test    rax, rax
0x140001073  jz      short loc_140001094
0x140001075  movzx   r8d, word ptr [r9]
0x140001079  test    r8w, r8w
0x14000107d  jz      short loc_140001094
0x14000107f  mov     [r11], r8w
0x140001083  add     r9, 2
0x140001087  add     r11, 2
0x14000108b  dec     rax
0x14000108e  sub     r10, 1
0x140001092  jnz     short loc_140001070
0x140001094  xor     ecx, ecx
0x140001096  lea     rdx, [r11-2]
0x14000109a  test    r10, r10
0x14000109d  mov     eax, 80000005h
0x1400010a2  cmovnz  rdx, r11
0x1400010a6  cmovnz  eax, ecx
0x1400010a9  mov     [rdx], cx
0x1400010ac  retn
```
