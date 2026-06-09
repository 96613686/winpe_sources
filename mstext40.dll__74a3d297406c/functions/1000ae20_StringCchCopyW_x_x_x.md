# StringCchCopyW(x,x,x)

- ea: `0x1000ae20`
- end: `0x1000ae99`
- name: `_StringCchCopyW@12`
- size: `121`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `24`
- callee_count: `1`
- tags: ``

## callers

- `0x10009db0`
- `0x1000a3e0`
- `0x1000a8c0`
- `0x1000aa30`
- `0x1000b6d0`
- `0x1000b7a0`
- `0x1000bab0`
- `0x1000c370`
- `0x1000cbf0`
- `0x1000d130`
- `0x1000ff30`
- `0x10013cd0`
- `0x10013d50`
- `0x10013de0`
- `0x10019b40`
- `0x1001df30`
- `0x1001f730`
- `0x100232f0`
- `0x10023ac0`
- `0x10023bb0`
- `0x100260f0`
- `0x10026150`
- `0x100279a0`
- `0x10029110`

## callees

- `0x1000ae20`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  size_t v3; // edx
  HRESULT result; // eax
  STRSAFE_LPWSTR v5; // ecx
  HRESULT v6; // ebx
  wchar_t v7; // ax

  v3 = cchDest;
  result = 0;
  if ( (int)cchDest <= 0 )
    result = -2147024809;
  if ( result < 0 )
  {
    if ( cchDest )
      *pszDest = 0;
  }
  else
  {
    v5 = pszDest;
    v6 = 0;
    if ( !cchDest )
      goto LABEL_10;
    while ( 2147483646 - cchDest + v3 )
    {
      v7 = *(STRSAFE_LPWSTR)((char *)v5 + (char *)pszSrc - (char *)pszDest);
      if ( !v7 )
        break;
      *v5++ = v7;
      if ( !--v3 )
        goto LABEL_10;
    }
    if ( !v3 )
    {
LABEL_10:
      --v5;
      v6 = -2147024774;
    }
    *v5 = 0;
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x1000ae20  mov     edx, [esp+cchDest]
0x1000ae24  xor     eax, eax
0x1000ae26  test    edx, edx
0x1000ae28  jz      short loc_1000AE32
0x1000ae2a  cmp     edx, 7FFFFFFFh
0x1000ae30  jbe     short loc_1000AE37
0x1000ae32  mov     eax, 80070057h
0x1000ae37  test    eax, eax
0x1000ae39  js      short loc_1000AE89
0x1000ae3b  mov     ecx, [esp+pszDest]
0x1000ae3f  push    ebx
0x1000ae40  push    esi
0x1000ae41  xor     ebx, ebx
0x1000ae43  push    edi
0x1000ae44  test    edx, edx
0x1000ae46  jz      short loc_1000AE74
0x1000ae48  mov     edi, [esp+0Ch+pszSrc]
0x1000ae4c  mov     esi, 7FFFFFFEh
0x1000ae51  sub     esi, edx
0x1000ae53  sub     edi, ecx
0x1000ae55  lea     eax, [esi+edx]
0x1000ae58  test    eax, eax
0x1000ae5a  jz      short loc_1000AE70
0x1000ae5c  movzx   eax, word ptr [edi+ecx]
0x1000ae60  test    ax, ax
0x1000ae63  jz      short loc_1000AE70
0x1000ae65  mov     [ecx], ax
0x1000ae68  add     ecx, 2
0x1000ae6b  dec     edx
0x1000ae6c  jnz     short loc_1000AE55
0x1000ae6e  jmp     short loc_1000AE74
0x1000ae70  test    edx, edx
0x1000ae72  jnz     short loc_1000AE7C
0x1000ae74  sub     ecx, 2
0x1000ae77  mov     ebx, 8007007Ah
0x1000ae7c  xor     eax, eax
0x1000ae7e  pop     edi
0x1000ae7f  mov     [ecx], ax
0x1000ae82  mov     eax, ebx
0x1000ae84  pop     esi
0x1000ae85  pop     ebx
0x1000ae86  retn    0Ch
0x1000ae89  test    edx, edx
0x1000ae8b  jz      short locret_1000AE96
0x1000ae8d  mov     ecx, [esp+pszDest]
0x1000ae91  xor     edx, edx
0x1000ae93  mov     [ecx], dx
0x1000ae96  retn    0Ch
```
