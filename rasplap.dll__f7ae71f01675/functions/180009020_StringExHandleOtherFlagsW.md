# StringExHandleOtherFlagsW

- ea: `0x180009020`
- end: `0x1800090bd`
- name: `StringExHandleOtherFlagsW`
- size: `157`
- prototype: `static HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cbDest, size_t cchOriginalDestLength, STRSAFE_LPWSTR *ppszDestEnd, size_t *pcchRemaining, DWORD dwFlags)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008c5c`
- `0x180008ddc`

## callees

- `0x180009020`
- `0x18000b0ce`

## pseudocode

```c
HRESULT __stdcall StringExHandleOtherFlagsW(
        STRSAFE_LPWSTR pszDest,
        size_t cbDest,
        size_t cchOriginalDestLength,
        STRSAFE_LPWSTR *ppszDestEnd,
        size_t *pcchRemaining,
        DWORD dwFlags)
{
  size_t v6; // rdi
  wchar_t *v10; // rcx

  v6 = cbDest >> 1;
  if ( cbDest >> 1 && (dwFlags & 0x1000) != 0 )
  {
    *ppszDestEnd = pszDest;
    *pszDest = 0;
    *pcchRemaining = v6;
  }
  if ( (dwFlags & 0x400) == 0 )
  {
LABEL_7:
    if ( !v6 )
      return 0;
    goto LABEL_8;
  }
  memset_0(pszDest, (unsigned __int8)dwFlags, cbDest);
  if ( !(_BYTE)dwFlags )
  {
    *ppszDestEnd = pszDest;
    *pcchRemaining = v6;
    goto LABEL_7;
  }
  if ( !v6 )
    return 0;
  *pcchRemaining = 1;
  v10 = &pszDest[v6 - 1];
  *ppszDestEnd = v10;
  *v10 = 0;
LABEL_8:
  if ( (dwFlags & 0x800) != 0 )
  {
    *ppszDestEnd = pszDest;
    *pszDest = 0;
    *pcchRemaining = v6;
  }
  return 0;
}

```

## disassembly

```asm
0x180009020  push    rbx
0x180009022  push    rsi
0x180009023  push    rdi
0x180009024  push    r14
0x180009026  push    r15
0x180009028  sub     rsp, 20h
0x18000902c  mov     r15, [rsp+48h+pcchRemaining]
0x180009031  mov     rdi, rdx
0x180009034  shr     rdi, 1
0x180009037  mov     r14, r9
0x18000903a  mov     rsi, rcx
0x18000903d  jz      short loc_180009054
0x18000903f  test    [rsp+48h+dwFlags], 1000h
0x180009047  jz      short loc_180009054
0x180009049  xor     eax, eax
0x18000904b  mov     [r9], rcx
0x18000904e  mov     [rcx], ax
0x180009051  mov     [r15], rdi
0x180009054  test    [rsp+48h+dwFlags], 400h
0x18000905c  jz      short loc_180009077
0x18000905e  movzx   ebx, byte ptr [rsp+48h+dwFlags]
0x180009063  mov     r8, rdx; Size
0x180009066  mov     edx, ebx; Val
0x180009068  call    memset_0
0x18000906d  test    ebx, ebx
0x18000906f  jnz     short loc_18000909F
0x180009071  mov     [r14], rsi
0x180009074  mov     [r15], rdi
0x180009077  test    rdi, rdi
0x18000907a  jz      short loc_180009091
0x18000907c  test    [rsp+48h+dwFlags], 800h
0x180009084  jz      short loc_180009091
0x180009086  xor     eax, eax
0x180009088  mov     [r14], rsi
0x18000908b  mov     [rsi], ax
0x18000908e  mov     [r15], rdi
0x180009091  xor     eax, eax
0x180009093  add     rsp, 20h
0x180009097  pop     r15
0x180009099  pop     r14
0x18000909b  pop     rdi
0x18000909c  pop     rsi
0x18000909d  pop     rbx
0x18000909e  retn
0x18000909f  test    rdi, rdi
0x1800090a2  jz      short loc_180009091
0x1800090a4  lea     rcx, [rsi-2]
0x1800090a8  mov     qword ptr [r15], 1
0x1800090af  lea     rcx, [rcx+rdi*2]
0x1800090b3  xor     eax, eax
0x1800090b5  mov     [r14], rcx
0x1800090b8  mov     [rcx], ax
0x1800090bb  jmp     short loc_18000907C
```
