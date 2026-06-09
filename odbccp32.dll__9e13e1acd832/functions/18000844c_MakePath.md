# MakePath

- ea: `0x18000844c`
- end: `0x1800084b7`
- name: `MakePath`
- size: `107`
- prototype: `int __fastcall(STRSAFE_LPWSTR pszDest, STRSAFE_LPCWSTR pszSrc, STRSAFE_LPCWSTR)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180006184`
- `0x180007628`

## callees

- `0x180002e14`
- `0x180004afc`
- `0x18000844c`

## pseudocode

```c
int __fastcall MakePath(STRSAFE_LPWSTR pszDest, STRSAFE_LPCWSTR pszSrc, STRSAFE_LPCWSTR a3)
{
  wchar_t *v4; // r11
  __int64 v5; // rcx
  signed __int64 v6; // rax

  v4 = pszDest;
  if ( pszDest != pszSrc )
    StringCchCopyW(pszDest, 0x104u, pszSrc);
  v5 = -1;
  do
    ++v5;
  while ( v4[v5] );
  if ( v4[v5 - 1] == 92 )
    goto LABEL_8;
  v6 = (2 * v5 - 2) & 0xFFFFFFFFFFFFFFFEuLL;
  if ( v6 < 516 )
  {
    *(_DWORD *)&v4[v5] = 92;
LABEL_8:
    LODWORD(v6) = StringCchCatW(v4, 0x104u, a3);
  }
  return v6;
}

```

## disassembly

```asm
0x18000844c  push    rbx
0x18000844e  sub     rsp, 20h
0x180008452  mov     rbx, r8
0x180008455  mov     r11, rcx
0x180008458  cmp     rcx, rdx
0x18000845b  jz      short loc_18000846A
0x18000845d  mov     r8, rdx; pszSrc
0x180008460  mov     edx, 104h; cchDest
0x180008465  call    StringCchCopyW
0x18000846a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000846e  xor     edx, edx
0x180008470  inc     rcx
0x180008473  cmp     [r11+rcx*2], dx
0x180008478  jnz     short loc_180008470
0x18000847a  lea     rax, [r11-2]
0x18000847e  mov     r8d, 5Ch ; '\'
0x180008484  lea     rax, [rax+rcx*2]
0x180008488  cmp     [rax], r8w
0x18000848c  jz      short loc_1800084A1
0x18000848e  sub     rax, r11
0x180008491  and     rax, 0FFFFFFFFFFFFFFFEh
0x180008495  cmp     rax, 204h
0x18000849b  jge     short loc_1800084B1
0x18000849d  mov     [r11+rcx*2], r8d
0x1800084a1  mov     r8, rbx; pszSrc
0x1800084a4  mov     edx, 104h; cchDest
0x1800084a9  mov     rcx, r11; pszDest
0x1800084ac  call    StringCchCatW
0x1800084b1  add     rsp, 20h
0x1800084b5  pop     rbx
0x1800084b6  retn
```
