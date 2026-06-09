# RtlStringCbCopyW

- ea: `0x140001110`
- end: `0x14000117e`
- name: `RtlStringCbCopyW`
- size: `110`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszSrc)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e340`
- `0x140011d50`
- `0x140012a40`
- `0x140013160`

## callees

- `0x140001110`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCbCopyW(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszSrc)
{
  size_t v3; // rdx
  NTSTRSAFE_PWSTR v4; // r9
  __int64 v5; // rax
  NTSTRSAFE_PWSTR v6; // rax
  NTSTATUS result; // eax

  v3 = cbDest >> 1;
  v4 = pszDest;
  if ( !v3 )
    return -1073741811;
  if ( v3 > 0x7FFFFFFF )
  {
    result = -1073741811;
    *pszDest = 0;
  }
  else
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*pszSrc )
        break;
      *v4++ = *pszSrc++;
      --v5;
      --v3;
    }
    while ( v3 );
    v6 = v4 - 1;
    if ( v3 )
      v6 = v4;
    *v6 = 0;
    result = -2147483643;
    if ( v3 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140001110  shr     rdx, 1
0x140001113  mov     r9, rcx
0x140001116  jz      short loc_14000116D
0x140001118  cmp     rdx, 7FFFFFFFh
0x14000111f  ja      short loc_140001166
0x140001121  mov     eax, 7FFFFFFEh
0x140001126  test    rax, rax
0x140001129  jz      short loc_140001149
0x14000112b  movzx   ecx, word ptr [r8]
0x14000112f  test    cx, cx
0x140001132  jz      short loc_140001149
0x140001134  mov     [r9], cx
0x140001138  add     r8, 2
0x14000113c  add     r9, 2
0x140001140  dec     rax
0x140001143  sub     rdx, 1
0x140001147  jnz     short loc_140001126
0x140001149  test    rdx, rdx
0x14000114c  lea     rax, [r9-2]
0x140001150  cmovnz  rax, r9
0x140001154  xor     ecx, ecx
0x140001156  test    rdx, rdx
0x140001159  mov     [rax], cx
0x14000115c  mov     eax, 80000005h
0x140001161  cmovnz  eax, ecx
0x140001164  retn
0x140001166  mov     eax, 0C000000Dh
0x14000116b  jmp     short loc_140001177
0x14000116d  mov     eax, 0C000000Dh
0x140001172  test    rdx, rdx
0x140001175  jz      short locret_140001164
0x140001177  xor     ecx, ecx
0x140001179  mov     [r9], cx
0x14000117d  retn
```
