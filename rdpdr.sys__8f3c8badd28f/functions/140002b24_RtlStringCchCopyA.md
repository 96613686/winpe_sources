# RtlStringCchCopyA

- ea: `0x140002b24`
- end: `0x140002b87`
- name: `RtlStringCchCopyA`
- size: `99`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PSTR pszDest, size_t cchDest, NTSTRSAFE_PCSTR pszSrc)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400294a0`
- `0x14002a540`

## callees

- `0x140002b24`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCchCopyA(NTSTRSAFE_PSTR pszDest, size_t cchDest, NTSTRSAFE_PCSTR pszSrc)
{
  NTSTATUS result; // eax
  __int64 v4; // rax
  NTSTRSAFE_PSTR v5; // rax

  if ( !cchDest )
    return -1073741811;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v4 = 2147483646;
    do
    {
      if ( !v4 )
        break;
      if ( !*pszSrc )
        break;
      *pszDest++ = *pszSrc++;
      --v4;
      --cchDest;
    }
    while ( cchDest );
    v5 = pszDest - 1;
    if ( cchDest )
      v5 = pszDest;
    *v5 = 0;
    return cchDest == 0 ? 0x80000005 : 0;
  }
  else
  {
    result = -1073741811;
    *pszDest = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140002b24  test    rdx, rdx
0x140002b27  jz      short loc_140002B79
0x140002b29  cmp     rdx, 7FFFFFFFh
0x140002b30  jbe     short loc_140002B39
0x140002b32  mov     eax, 0C000000Dh
0x140002b37  jmp     short loc_140002B83
0x140002b39  mov     eax, 7FFFFFFEh
0x140002b3e  test    rax, rax
0x140002b41  jz      short loc_140002B5D
0x140002b43  mov     r9b, [r8]
0x140002b46  test    r9b, r9b
0x140002b49  jz      short loc_140002B5D
0x140002b4b  mov     [rcx], r9b
0x140002b4e  inc     r8
0x140002b51  inc     rcx
0x140002b54  dec     rax
0x140002b57  sub     rdx, 1
0x140002b5b  jnz     short loc_140002B3E
0x140002b5d  test    rdx, rdx
0x140002b60  lea     rax, [rcx-1]
0x140002b64  cmovnz  rax, rcx
0x140002b68  neg     rdx
0x140002b6b  mov     byte ptr [rax], 0
0x140002b6e  sbb     eax, eax
0x140002b70  not     eax
0x140002b72  and     eax, 80000005h
0x140002b77  retn
0x140002b79  mov     eax, 0C000000Dh
0x140002b7e  test    rdx, rdx
0x140002b81  jz      short locret_140002B86
0x140002b83  mov     byte ptr [rcx], 0
0x140002b86  retn
```
