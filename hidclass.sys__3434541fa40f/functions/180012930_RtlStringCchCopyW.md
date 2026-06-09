# RtlStringCchCopyW

- ea: `0x180012930`
- end: `0x18001299c`
- name: `RtlStringCchCopyW`
- size: `108`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18003da1c`
- `0x18003dfcc`

## callees

- `0x180012930`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCchCopyW(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszSrc)
{
  NTSTRSAFE_PWSTR v3; // r9
  __int64 v4; // rax
  NTSTATUS result; // eax

  v3 = pszDest;
  if ( !cchDest )
    return -1073741811;
  if ( cchDest > 0x7FFFFFFF )
  {
    result = -1073741811;
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
    pszDest = v3 - 1;
    if ( cchDest )
      pszDest = v3;
    result = cchDest == 0 ? 0x80000005 : 0;
  }
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x180012930  xor     r10d, r10d
0x180012933  mov     r9, rcx
0x180012936  test    rdx, rdx
0x180012939  jz      short loc_180012990
0x18001293b  cmp     rdx, 7FFFFFFFh
0x180012942  ja      short loc_180012989
0x180012944  mov     eax, 7FFFFFFEh
0x180012949  test    rax, rax
0x18001294c  jz      short loc_18001296C
0x18001294e  movzx   ecx, word ptr [r8]
0x180012952  test    cx, cx
0x180012955  jz      short loc_18001296C
0x180012957  mov     [r9], cx
0x18001295b  add     r8, 2
0x18001295f  add     r9, 2
0x180012963  dec     rax
0x180012966  sub     rdx, 1
0x18001296a  jnz     short loc_180012949
0x18001296c  test    rdx, rdx
0x18001296f  lea     rcx, [r9-2]
0x180012973  cmovnz  rcx, r9
0x180012977  neg     rdx
0x18001297a  sbb     eax, eax
0x18001297c  not     eax
0x18001297e  and     eax, 80000005h
0x180012983  mov     [rcx], r10w
0x180012987  retn
0x180012989  mov     eax, 0C000000Dh
0x18001298e  jmp     short loc_180012983
0x180012990  mov     eax, 0C000000Dh
0x180012995  test    rdx, rdx
0x180012998  jz      short locret_180012987
0x18001299a  jmp     short loc_180012983
```
