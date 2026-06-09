# RtlStringCchCopyW

- ea: `0x1400024f0`
- end: `0x14000255b`
- name: `RtlStringCchCopyW`
- size: `107`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszSrc)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140011ef0`
- `0x140018b88`
- `0x140018c98`
- `0x14001e694`

## callees

- `0x1400024f0`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCchCopyW(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszSrc)
{
  NTSTRSAFE_PWSTR v3; // r9
  NTSTATUS result; // eax
  __int64 v5; // rax

  v3 = pszDest;
  if ( !cchDest )
    return -1073741811;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*pszSrc )
        break;
      *v3++ = *pszSrc++;
      --v5;
      --cchDest;
    }
    while ( cchDest );
    pszDest = v3 - 1;
    if ( cchDest )
      pszDest = v3;
    result = cchDest == 0 ? 0x80000005 : 0;
  }
  else
  {
    result = -1073741811;
  }
  *pszDest = 0;
  return result;
}

```

## disassembly

```asm
0x1400024f0  xor     r10d, r10d
0x1400024f3  mov     r9, rcx
0x1400024f6  test    rdx, rdx
0x1400024f9  jz      short loc_14000254C
0x1400024fb  cmp     rdx, 7FFFFFFFh
0x140002502  jbe     short loc_14000250B
0x140002504  mov     eax, 0C000000Dh
0x140002509  jmp     short loc_140002556
0x14000250b  mov     eax, 7FFFFFFEh
0x140002510  test    rax, rax
0x140002513  jz      short loc_140002533
0x140002515  movzx   ecx, word ptr [r8]
0x140002519  test    cx, cx
0x14000251c  jz      short loc_140002533
0x14000251e  mov     [r9], cx
0x140002522  add     r8, 2
0x140002526  add     r9, 2
0x14000252a  dec     rax
0x14000252d  sub     rdx, 1
0x140002531  jnz     short loc_140002510
0x140002533  test    rdx, rdx
0x140002536  lea     rcx, [r9-2]
0x14000253a  cmovnz  rcx, r9
0x14000253e  neg     rdx
0x140002541  sbb     eax, eax
0x140002543  not     eax
0x140002545  and     eax, 80000005h
0x14000254a  jmp     short loc_140002556
0x14000254c  mov     eax, 0C000000Dh
0x140002551  test    rdx, rdx
0x140002554  jz      short locret_14000255A
0x140002556  mov     [rcx], r10w
0x14000255a  retn
```
