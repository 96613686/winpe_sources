# GetLocalizedFontNames(wchar_t *,ushort)

- ea: `0x18003128c`
- end: `0x1800314da`
- name: `?GetLocalizedFontNames@@YAGPEA_WG@Z`
- size: `590`
- prototype: `unsigned __int16 __fastcall(wchar_t *, unsigned __int16)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180032b58`

## callees

- `0x18002f680`
- `0x18003128c`
- `0x18007f800`
- `0x1800805ec`

## import_xrefs

- `GDI32!SelectObject` at `0x18003138e`
- `GDI32!SelectObject` at `0x1800313f2`
- `GDI32!SelectObject` at `0x18003138e`
- `GDI32!SelectObject` at `0x1800313f2`
- `GDI32!DeleteObject` at `0x180031403`
- `GDI32!DeleteObject` at `0x180031403`
- `USER32!ReleaseDC` at `0x180031494`
- `USER32!ReleaseDC` at `0x180031494`
- `USER32!GetDC` at `0x1800312d2`
- `USER32!GetDC` at `0x1800312d2`
- `win32u!NtGdiGetTextFaceW` at `0x1800313b5`
- `win32u!NtGdiGetTextFaceW` at `0x180031439`
- `win32u!NtGdiGetTextFaceW` at `0x1800313b5`
- `win32u!NtGdiGetTextFaceW` at `0x180031439`

## pseudocode

```c
__int64 __fastcall GetLocalizedFontNames(wchar_t *a1, unsigned __int16 a2)
{
  int v2; // r15d
  unsigned __int16 v4; // r12
  HDC DC; // rdi
  unsigned __int16 v6; // si
  wchar_t *v7; // r14
  wchar_t *v8; // rbx
  HFONT FontIndirectWImpl; // rax
  unsigned __int16 *v10; // rax
  int v11; // ecx
  int v12; // edx
  unsigned __int16 *v13; // rax
  int v14; // ecx
  int v15; // edx
  int v17; // [rsp+20h] [rbp-B9h]
  HGDIOBJ h; // [rsp+28h] [rbp-B1h]
  HFONT ho; // [rsp+30h] [rbp-A9h]
  __m128i si128; // [rsp+40h] [rbp-99h] BYREF
  int v21; // [rsp+50h] [rbp-89h]
  int v22; // [rsp+54h] [rbp-85h]
  __int16 v23; // [rsp+58h] [rbp-81h]
  wchar_t Destination[2]; // [rsp+5Ah] [rbp-7Fh] BYREF
  __int128 v25; // [rsp+5Eh] [rbp-7Bh]
  __int128 v26; // [rsp+6Eh] [rbp-6Bh]
  _BYTE v27[30]; // [rsp+7Eh] [rbp-5Bh] BYREF
  _BYTE v28[64]; // [rsp+A0h] [rbp-39h] BYREF
  __int16 v29; // [rsp+E0h] [rbp+7h]

  v2 = a2;
  v4 = 0;
  if ( (unsigned __int16)(a2 - 1) <= 0x63u )
  {
    DC = GetDC(0);
    if ( DC )
    {
      v6 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      memset(v27, 0, sizeof(v27));
      v21 = 400;
      v22 = 0x1000000;
      v23 = 0;
      *(_DWORD *)Destination = 0;
      v25 = 0;
      v26 = 0;
      while ( v6 < (unsigned __int16)v2 )
      {
        v7 = &a1[64 * (unsigned __int64)v6 + 32];
        if ( !*v7 )
          break;
        wcscpy_s(&Destination[1], 0x20u, &a1[64 * (unsigned __int64)v6 + 32]);
        v29 = 0;
        v8 = &a1[64 * (unsigned __int64)v6];
        FontIndirectWImpl = CreateFontIndirectWImpl((__int64)&si128);
        ho = FontIndirectWImpl;
        if ( !FontIndirectWImpl )
          goto LABEL_15;
        v17 = 0;
        h = SelectObject(DC, FontIndirectWImpl);
        if ( h )
        {
          if ( (unsigned int)NtGdiGetTextFaceW(DC, 32, v28) )
          {
            v10 = (unsigned __int16 *)v28;
            do
            {
              v11 = *(unsigned __int16 *)((char *)v10 + (char *)v7 - v28);
              v12 = *v10 - v11;
              if ( v12 )
                break;
              ++v10;
            }
            while ( v11 );
            if ( !v12 )
            {
              if ( (unsigned int)NtGdiGetTextFaceW(DC, 32, v8) )
              {
                v8[31] = 0;
                if ( *v8 )
                {
                  v13 = (unsigned __int16 *)v28;
                  do
                  {
                    v14 = *(unsigned __int16 *)((char *)v13 + (char *)v8 - v28);
                    v15 = *v13 - v14;
                    if ( v15 )
                      break;
                    ++v13;
                  }
                  while ( v14 );
                  if ( v15 )
                  {
                    ++v4;
                    v17 = 1;
                  }
                }
              }
            }
          }
          SelectObject(DC, h);
        }
        DeleteObject(ho);
        if ( !v17 )
LABEL_15:
          wcscpy_s(v8, 0x20u, &a1[64 * (unsigned __int64)v6 + 32]);
        ++v6;
      }
      ReleaseDC(0, DC);
    }
    a1[v2 << 6] = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18003128c  mov     [rsp-8+arg_10], rbx
0x180031291  push    rbp
0x180031292  push    rsi
0x180031293  push    rdi
0x180031294  push    r12
0x180031296  push    r13
0x180031298  push    r14
0x18003129a  push    r15
0x18003129c  lea     rbp, [rsp-27h]
0x1800312a1  sub     rsp, 100h
0x1800312a8  mov     rax, cs:__security_cookie
0x1800312af  xor     rax, rsp
0x1800312b2  mov     [rbp+57h+var_40], rax
0x1800312b6  xor     ebx, ebx
0x1800312b8  movzx   r15d, dx
0x1800312bc  mov     r13, rcx
0x1800312bf  mov     r12d, ebx
0x1800312c2  lea     eax, [r15-1]
0x1800312c6  cmp     ax, 63h ; 'c'
0x1800312ca  ja      loc_1800314AE
0x1800312d0  xor     ecx, ecx; hWnd
0x1800312d2  call    cs:__imp_GetDC
0x1800312d9  nop     dword ptr [rax+rax+00h]
0x1800312de  mov     rdi, rax
0x1800312e1  test    rax, rax
0x1800312e4  jz      loc_1800314A2
0x1800312ea  movdqa  xmm0, cs:__xmm@000000000000000000000000fffffff4
0x1800312f2  mov     esi, ebx
0x1800312f4  movdqa  [rsp+130h+var_F0], xmm0
0x1800312fa  xorps   xmm0, xmm0
0x1800312fd  movups  xmmword ptr [rbp+57h+var_B2], xmm0
0x180031301  mov     [rsp+130h+var_E0], 190h
0x180031309  movups  xmmword ptr [rbp+57h+var_B2+0Eh], xmm0
0x18003130d  mov     [rsp+130h+var_DC], 1000000h
0x180031315  mov     [rsp+130h+var_D8], bx
0x18003131a  mov     dword ptr [rbp+57h+Destination], ebx
0x18003131d  movups  [rbp+57h+var_D2], xmm0
0x180031321  movups  [rbp+57h+var_C2], xmm0
0x180031325  cmp     si, r15w
0x180031329  jnb     loc_18003148F
0x18003132f  movzx   ebx, si
0x180031332  lea     r14, [r13+40h]
0x180031336  shl     rbx, 6
0x18003133a  xor     ecx, ecx
0x18003133c  lea     r14, [r14+rbx*2]
0x180031340  cmp     [r14], cx
0x180031344  jz      loc_18003148F
0x18003134a  lea     edx, [rcx+20h]; SizeInWords
0x18003134d  mov     r8, r14; Source
0x180031350  lea     rcx, [rbp+57h+Destination+2]; Destination
0x180031354  call    wcscpy_s
0x180031359  xor     eax, eax
0x18003135b  lea     rbx, ds:0[rbx*2]
0x180031363  lea     rcx, [rsp+130h+var_F0]
0x180031368  mov     [rbp+57h+var_50], ax
0x18003136c  add     rbx, r13
0x18003136f  call    CreateFontIndirectWImpl
0x180031374  xor     ecx, ecx
0x180031376  mov     [rsp+130h+ho], rax
0x18003137b  test    rax, rax
0x18003137e  jz      loc_180031416
0x180031384  mov     [rsp+130h+var_110], ecx
0x180031388  mov     rdx, rax; h
0x18003138b  mov     rcx, rdi; hdc
0x18003138e  call    cs:__imp_SelectObject
0x180031395  nop     dword ptr [rax+rax+00h]
0x18003139a  mov     [rsp+130h+h], rax
0x18003139f  test    rax, rax
0x1800313a2  jz      short loc_1800313FE
0x1800313a4  mov     r9d, 1
0x1800313aa  lea     r8, [rbp+57h+var_90]
0x1800313ae  mov     rcx, rdi
0x1800313b1  lea     edx, [r9+1Fh]
0x1800313b5  call    cs:__imp_NtGdiGetTextFaceW
0x1800313bc  nop     dword ptr [rax+rax+00h]
0x1800313c1  xor     r9d, r9d
0x1800313c4  test    eax, eax
0x1800313c6  jz      short loc_1800313EA
0x1800313c8  lea     rax, [rbp+57h+var_90]
0x1800313cc  mov     r8, r14
0x1800313cf  sub     r8, rax
0x1800313d2  movzx   edx, word ptr [rax]
0x1800313d5  movzx   ecx, word ptr [rax+r8]
0x1800313da  sub     edx, ecx
0x1800313dc  jnz     short loc_1800313E6
0x1800313de  add     rax, 2
0x1800313e2  test    ecx, ecx
0x1800313e4  jnz     short loc_1800313D2
0x1800313e6  test    edx, edx
0x1800313e8  jz      short loc_18003142E
0x1800313ea  mov     rdx, [rsp+130h+h]; h
0x1800313ef  mov     rcx, rdi; hdc
0x1800313f2  call    cs:__imp_SelectObject
0x1800313f9  nop     dword ptr [rax+rax+00h]
0x1800313fe  mov     rcx, [rsp+130h+ho]; ho
0x180031403  call    cs:__imp_DeleteObject
0x18003140a  nop     dword ptr [rax+rax+00h]
0x18003140f  cmp     [rsp+130h+var_110], 0
0x180031414  jnz     short loc_180031426
0x180031416  mov     r8, r14; Source
0x180031419  mov     edx, 20h ; ' '; SizeInWords
0x18003141e  mov     rcx, rbx; Destination
0x180031421  call    wcscpy_s
0x180031426  inc     si
0x180031429  jmp     loc_180031325
0x18003142e  mov     r8, rbx
0x180031431  mov     edx, 20h ; ' '
0x180031436  mov     rcx, rdi
0x180031439  call    cs:__imp_NtGdiGetTextFaceW
0x180031440  nop     dword ptr [rax+rax+00h]
0x180031445  xor     r9d, r9d
0x180031448  test    eax, eax
0x18003144a  jz      short loc_1800313EA
0x18003144c  mov     [rbx+3Eh], r9w
0x180031451  cmp     [rbx], r9w
0x180031455  jz      short loc_1800313EA
0x180031457  lea     rax, [rbp+57h+var_90]
0x18003145b  mov     r8, rbx
0x18003145e  sub     r8, rax
0x180031461  movzx   edx, word ptr [rax]
0x180031464  movzx   ecx, word ptr [rax+r8]
0x180031469  sub     edx, ecx
0x18003146b  jnz     short loc_180031475
0x18003146d  add     rax, 2
0x180031471  test    ecx, ecx
0x180031473  jnz     short loc_180031461
0x180031475  test    edx, edx
0x180031477  jz      loc_1800313EA
0x18003147d  mov     eax, 1
0x180031482  add     r12w, ax
0x180031486  mov     [rsp+130h+var_110], eax
0x18003148a  jmp     loc_1800313EA
0x18003148f  mov     rdx, rdi; hDC
0x180031492  xor     ecx, ecx; hWnd
0x180031494  call    cs:__imp_ReleaseDC
0x18003149b  nop     dword ptr [rax+rax+00h]
0x1800314a0  xor     ebx, ebx
0x1800314a2  mov     ecx, r15d
0x1800314a5  shl     ecx, 6
0x1800314a8  mov     [r13+rcx*2+0], bx
0x1800314ae  movzx   eax, r12w
0x1800314b2  mov     rcx, [rbp+57h+var_40]
0x1800314b6  xor     rcx, rsp; StackCookie
0x1800314b9  call    __security_check_cookie
0x1800314be  mov     rbx, [rsp+130h+arg_10]
0x1800314c6  add     rsp, 100h
0x1800314cd  pop     r15
0x1800314cf  pop     r14
0x1800314d1  pop     r13
0x1800314d3  pop     r12
0x1800314d5  pop     rdi
0x1800314d6  pop     rsi
0x1800314d7  pop     rbp
0x1800314d8  retn
```
