# RtlStringCchCopyW

- ea: `0x140001340`
- end: `0x1400013ae`
- name: `RtlStringCchCopyW`
- size: `110`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140010500`

## callees

- `0x140001340`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCchCopyW(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszSrc)
{
  NTSTRSAFE_PWSTR v3; // r9
  __int64 v4; // rax
  NTSTRSAFE_PWSTR v5; // rax
  NTSTATUS result; // eax

  v3 = pszDest;
  if ( !cchDest )
    return -1073741811;
  if ( cchDest > 0x7FFFFFFF )
  {
    result = -1073741811;
    *pszDest = 0;
  }
  else
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*pszSrc )
        break;
      *v3++ = *pszSrc++;
      --v4;
      --cchDest;
    }
    while ( cchDest );
    v5 = v3 - 1;
    if ( cchDest )
      v5 = v3;
    *v5 = 0;
    result = -2147483643;
    if ( cchDest )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140001340  mov     r9, rcx
0x140001343  test    rdx, rdx
0x140001346  jz      short loc_14000139D
0x140001348  cmp     rdx, 7FFFFFFFh
0x14000134f  ja      short loc_140001396
0x140001351  mov     eax, 7FFFFFFEh
0x140001356  test    rax, rax
0x140001359  jz      short loc_140001379
0x14000135b  movzx   ecx, word ptr [r8]
0x14000135f  test    cx, cx
0x140001362  jz      short loc_140001379
0x140001364  mov     [r9], cx
0x140001368  add     r8, 2
0x14000136c  add     r9, 2
0x140001370  dec     rax
0x140001373  sub     rdx, 1
0x140001377  jnz     short loc_140001356
0x140001379  test    rdx, rdx
0x14000137c  lea     rax, [r9-2]
0x140001380  cmovnz  rax, r9
0x140001384  xor     ecx, ecx
0x140001386  test    rdx, rdx
0x140001389  mov     [rax], cx
0x14000138c  mov     eax, 80000005h
0x140001391  cmovnz  eax, ecx
0x140001394  retn
0x140001396  mov     eax, 0C000000Dh
0x14000139b  jmp     short loc_1400013A7
0x14000139d  mov     eax, 0C000000Dh
0x1400013a2  test    rdx, rdx
0x1400013a5  jz      short locret_140001394
0x1400013a7  xor     ecx, ecx
0x1400013a9  mov     [r9], cx
0x1400013ad  retn
```
