# GetLocalizedFontNames(wchar_t *,ushort)

- ea: `0x180027f80`
- end: `0x18002819b`
- name: `?GetLocalizedFontNames@@YAGPEA_WG@Z`
- size: `539`
- prototype: `unsigned __int16 __fastcall(wchar_t *, unsigned __int16)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800293e0`

## callees

- `0x180026640`
- `0x180027f80`
- `0x18007ac50`
- `0x18007ba0c`

## import_xrefs

- `GDI32!SelectObject` at `0x180028078`
- `GDI32!SelectObject` at `0x1800280d0`
- `GDI32!SelectObject` at `0x180028078`
- `GDI32!SelectObject` at `0x1800280d0`
- `GDI32!DeleteObject` at `0x1800280db`
- `GDI32!DeleteObject` at `0x1800280db`
- `USER32!ReleaseDC` at `0x18002815c`
- `USER32!ReleaseDC` at `0x18002815c`
- `USER32!GetDC` at `0x180027fc6`
- `USER32!GetDC` at `0x180027fc6`
- `win32u!NtGdiGetTextFaceW` at `0x180028099`
- `win32u!NtGdiGetTextFaceW` at `0x18002810b`
- `win32u!NtGdiGetTextFaceW` at `0x180028099`
- `win32u!NtGdiGetTextFaceW` at `0x18002810b`

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
          if ( (unsigned int)NtGdiGetTextFaceW(DC, 32, v28, 1) )
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
              if ( (unsigned int)NtGdiGetTextFaceW(DC, 32, v8, 0) )
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
0x180027f80  mov     [rsp-8+arg_10], rbx
0x180027f85  push    rbp
0x180027f86  push    rsi
0x180027f87  push    rdi
0x180027f88  push    r12
0x180027f8a  push    r13
0x180027f8c  push    r14
0x180027f8e  push    r15
0x180027f90  lea     rbp, [rsp-27h]
0x180027f95  sub     rsp, 100h
0x180027f9c  mov     rax, cs:__security_cookie
0x180027fa3  xor     rax, rsp
0x180027fa6  mov     [rbp+57h+var_40], rax
0x180027faa  xor     ebx, ebx
0x180027fac  movzx   r15d, dx
0x180027fb0  mov     r13, rcx
0x180027fb3  mov     r12d, ebx
0x180027fb6  lea     eax, [r15-1]
0x180027fba  cmp     ax, 63h ; 'c'
0x180027fbe  ja      loc_180028170
0x180027fc4  xor     ecx, ecx; hWnd
0x180027fc6  call    cs:__imp_GetDC
0x180027fcc  mov     rdi, rax
0x180027fcf  test    rax, rax
0x180027fd2  jz      loc_180028164
0x180027fd8  movdqa  xmm0, cs:__xmm@000000000000000000000000fffffff4
0x180027fe0  mov     esi, ebx
0x180027fe2  movdqa  [rsp+130h+var_F0], xmm0
0x180027fe8  xorps   xmm0, xmm0
0x180027feb  movups  xmmword ptr [rbp+57h+var_B2], xmm0
0x180027fef  mov     [rsp+130h+var_E0], 190h
0x180027ff7  movups  xmmword ptr [rbp+57h+var_B2+0Eh], xmm0
0x180027ffb  mov     [rsp+130h+var_DC], 1000000h
0x180028003  mov     [rsp+130h+var_D8], bx
0x180028008  mov     dword ptr [rbp+57h+Destination], ebx
0x18002800b  movups  [rbp+57h+var_D2], xmm0
0x18002800f  movups  [rbp+57h+var_C2], xmm0
0x180028013  cmp     si, r15w
0x180028017  jnb     loc_180028157
0x18002801d  movzx   ebx, si
0x180028020  lea     r14, [r13+40h]
0x180028024  shl     rbx, 6
0x180028028  xor     ecx, ecx
0x18002802a  lea     r14, [r14+rbx*2]
0x18002802e  cmp     [r14], cx
0x180028032  jz      loc_180028157
0x180028038  lea     edx, [rcx+20h]; SizeInWords
0x18002803b  mov     r8, r14; Source
0x18002803e  lea     rcx, [rbp+57h+Destination+2]; Destination
0x180028042  call    wcscpy_s
0x180028047  xor     eax, eax
0x180028049  lea     rbx, ds:0[rbx*2]
0x180028051  lea     rcx, [rsp+130h+var_F0]
0x180028056  mov     [rbp+57h+var_50], ax
0x18002805a  add     rbx, r13
0x18002805d  call    CreateFontIndirectWImpl
0x180028062  xor     ecx, ecx
0x180028064  mov     [rsp+130h+ho], rax
0x180028069  test    rax, rax
0x18002806c  jz      short loc_1800280E8
0x18002806e  mov     [rsp+130h+var_110], ecx
0x180028072  mov     rdx, rax; h
0x180028075  mov     rcx, rdi; hdc
0x180028078  call    cs:__imp_SelectObject
0x18002807e  mov     [rsp+130h+h], rax
0x180028083  test    rax, rax
0x180028086  jz      short loc_1800280D6
0x180028088  mov     r9d, 1
0x18002808e  lea     r8, [rbp+57h+var_90]
0x180028092  mov     rcx, rdi
0x180028095  lea     edx, [r9+1Fh]
0x180028099  call    cs:__imp_NtGdiGetTextFaceW
0x18002809f  xor     r9d, r9d
0x1800280a2  test    eax, eax
0x1800280a4  jz      short loc_1800280C8
0x1800280a6  lea     rax, [rbp+57h+var_90]
0x1800280aa  mov     r8, r14
0x1800280ad  sub     r8, rax
0x1800280b0  movzx   edx, word ptr [rax]
0x1800280b3  movzx   ecx, word ptr [rax+r8]
0x1800280b8  sub     edx, ecx
0x1800280ba  jnz     short loc_1800280C4
0x1800280bc  add     rax, 2
0x1800280c0  test    ecx, ecx
0x1800280c2  jnz     short loc_1800280B0
0x1800280c4  test    edx, edx
0x1800280c6  jz      short loc_180028100
0x1800280c8  mov     rdx, [rsp+130h+h]; h
0x1800280cd  mov     rcx, rdi; hdc
0x1800280d0  call    cs:__imp_SelectObject
0x1800280d6  mov     rcx, [rsp+130h+ho]; ho
0x1800280db  call    cs:__imp_DeleteObject
0x1800280e1  cmp     [rsp+130h+var_110], 0
0x1800280e6  jnz     short loc_1800280F8
0x1800280e8  mov     r8, r14; Source
0x1800280eb  mov     edx, 20h ; ' '; SizeInWords
0x1800280f0  mov     rcx, rbx; Destination
0x1800280f3  call    wcscpy_s
0x1800280f8  inc     si
0x1800280fb  jmp     loc_180028013
0x180028100  mov     r8, rbx
0x180028103  mov     edx, 20h ; ' '
0x180028108  mov     rcx, rdi
0x18002810b  call    cs:__imp_NtGdiGetTextFaceW
0x180028111  xor     r9d, r9d
0x180028114  test    eax, eax
0x180028116  jz      short loc_1800280C8
0x180028118  mov     [rbx+3Eh], r9w
0x18002811d  cmp     [rbx], r9w
0x180028121  jz      short loc_1800280C8
0x180028123  lea     rax, [rbp+57h+var_90]
0x180028127  mov     r8, rbx
0x18002812a  sub     r8, rax
0x18002812d  movzx   edx, word ptr [rax]
0x180028130  movzx   ecx, word ptr [rax+r8]
0x180028135  sub     edx, ecx
0x180028137  jnz     short loc_180028141
0x180028139  add     rax, 2
0x18002813d  test    ecx, ecx
0x18002813f  jnz     short loc_18002812D
0x180028141  test    edx, edx
0x180028143  jz      short loc_1800280C8
0x180028145  mov     eax, 1
0x18002814a  add     r12w, ax
0x18002814e  mov     [rsp+130h+var_110], eax
0x180028152  jmp     loc_1800280C8
0x180028157  mov     rdx, rdi; hDC
0x18002815a  xor     ecx, ecx; hWnd
0x18002815c  call    cs:__imp_ReleaseDC
0x180028162  xor     ebx, ebx
0x180028164  mov     ecx, r15d
0x180028167  shl     ecx, 6
0x18002816a  mov     [r13+rcx*2+0], bx
0x180028170  movzx   eax, r12w
0x180028174  mov     rcx, [rbp+57h+var_40]
0x180028178  xor     rcx, rsp; StackCookie
0x18002817b  call    __security_check_cookie
0x180028180  mov     rbx, [rsp+130h+arg_10]
0x180028188  add     rsp, 100h
0x18002818f  pop     r15
0x180028191  pop     r14
0x180028193  pop     r13
0x180028195  pop     r12
0x180028197  pop     rdi
0x180028198  pop     rsi
0x180028199  pop     rbp
0x18002819a  retn
```
