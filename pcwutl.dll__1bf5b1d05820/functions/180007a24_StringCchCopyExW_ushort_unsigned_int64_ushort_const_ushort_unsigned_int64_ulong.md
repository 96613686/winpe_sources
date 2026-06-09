# StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)

- ea: `0x180007a24`
- end: `0x180007ad9`
- name: `?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z`
- size: `181`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int64, const unsigned __int16 *, unsigned __int16 **, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800039c8`

## callees

- `0x180007a24`
- `0x180007be0`

## pseudocode

```c
__int64 __fastcall StringCchCopyExW(
        STRSAFE_LPWSTR pszDest,
        __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  unsigned int v6; // ebx
  const wchar_t *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rdx
  STRSAFE_LPWSTR v10; // rax
  STRSAFE_LPWSTR v11; // rcx
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+48h] [rbp+10h] BYREF
  size_t pcchRemaining; // [rsp+58h] [rbp+20h] BYREF

  if ( pszDest )
  {
    v7 = &word_18001DAC4;
    v8 = 2147483646;
    v9 = 260;
    if ( a3 )
      v7 = a3;
    v10 = pszDest;
    do
    {
      if ( !v8 )
        break;
      if ( !*v7 )
        break;
      *v10++ = *v7++;
      --v8;
      --v9;
    }
    while ( v9 );
    v11 = v10 - 1;
    if ( v9 )
      v11 = v10;
    *v11 = 0;
    v6 = v9 == 0 ? 0x8007007A : 0;
    if ( !v9 )
      StringExHandleOtherFlagsW(pszDest, 0x208u, 0, &ppszDestEnd, &pcchRemaining, 0x900u);
  }
  else
  {
    v6 = -2147024809;
    MEMORY[0] = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180007a24  push    rbx
0x180007a26  sub     rsp, 30h
0x180007a2a  xor     r11d, r11d
0x180007a2d  mov     rax, r8
0x180007a30  mov     r10, rcx
0x180007a33  test    rcx, rcx
0x180007a36  jnz     short loc_180007A46
0x180007a38  mov     ebx, 80070057h
0x180007a3d  mov     [rcx], r11w
0x180007a41  jmp     loc_180007AD1
0x180007a46  test    rax, rax
0x180007a49  lea     rcx, word_18001DAC4
0x180007a50  mov     r8d, 7FFFFFFEh
0x180007a56  mov     edx, 104h
0x180007a5b  cmovnz  rcx, rax
0x180007a5f  mov     rax, r10
0x180007a62  test    r8, r8
0x180007a65  jz      short loc_180007A86
0x180007a67  movzx   r9d, word ptr [rcx]
0x180007a6b  test    r9w, r9w
0x180007a6f  jz      short loc_180007A86
0x180007a71  mov     [rax], r9w
0x180007a75  add     rcx, 2
0x180007a79  add     rax, 2
0x180007a7d  dec     r8
0x180007a80  sub     rdx, 1
0x180007a84  jnz     short loc_180007A62
0x180007a86  test    rdx, rdx
0x180007a89  lea     rcx, [rax-2]
0x180007a8d  cmovnz  rcx, rax
0x180007a91  mov     rax, rdx
0x180007a94  neg     rax
0x180007a97  sbb     ebx, ebx
0x180007a99  not     ebx
0x180007a9b  mov     [rcx], r11w
0x180007a9f  and     ebx, 8007007Ah
0x180007aa5  test    rdx, rdx
0x180007aa8  jnz     short loc_180007AD1
0x180007aaa  lea     rax, [rsp+38h+arg_18]
0x180007aaf  mov     [rsp+38h+dwFlags], 900h; dwFlags
0x180007ab7  lea     r9, [rsp+38h+ppszDestEnd]; ppszDestEnd
0x180007abc  mov     [rsp+38h+pcchRemaining], rax; pcchRemaining
0x180007ac1  xor     r8d, r8d; cchOriginalDestLength
0x180007ac4  mov     edx, 208h; cbDest
0x180007ac9  mov     rcx, r10; pszDest
0x180007acc  call    StringExHandleOtherFlagsW
0x180007ad1  mov     eax, ebx
0x180007ad3  add     rsp, 30h
0x180007ad7  pop     rbx
0x180007ad8  retn
```
