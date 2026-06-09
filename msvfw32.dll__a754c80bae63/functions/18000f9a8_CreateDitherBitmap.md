# CreateDitherBitmap

- ea: `0x18000f9a8`
- end: `0x18000faff`
- name: `CreateDitherBitmap`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800135a4`

## callees

- `0x1800014b0`
- `0x18000f9a8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fad9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fad9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f9ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f9ce`
- `GDI32!CreateDIBitmap` at `0x18000fac2`
- `GDI32!CreateDIBitmap` at `0x18000fac2`
- `USER32!GetDC` at `0x18000fa9f`
- `USER32!GetDC` at `0x18000fa9f`
- `USER32!ReleaseDC` at `0x18000fad0`
- `USER32!ReleaseDC` at `0x18000fad0`
- `USER32!GetSysColor` at `0x18000f9fe`
- `USER32!GetSysColor` at `0x18000fa1f`
- `USER32!GetSysColor` at `0x18000f9fe`
- `USER32!GetSysColor` at `0x18000fa1f`

## pseudocode

```c
HBITMAP CreateDitherBitmap()
{
  HBITMAP result; // rax
  HBITMAP pbmi; // rsi
  DWORD SysColor; // eax
  DWORD v3; // eax
  signed int v4; // ecx
  __int64 v5; // rax
  __m128i v6; // xmm3
  __m128 v7; // xmm3
  HDC DC; // rdi
  HBITMAP DIBitmap; // rbx
  _OWORD pjBits[2]; // [rsp+30h] [rbp-38h] BYREF

  result = (HBITMAP)LocalAlloc(0x40u, 0x68u);
  pbmi = result;
  if ( result )
  {
    *(_DWORD *)result = 40;
    *((_DWORD *)result + 1) = 8;
    *((_DWORD *)result + 2) = 8;
    *(_QWORD *)(result + 3) = 65537;
    SysColor = GetSysColor(15);
    *((_BYTE *)pbmi + 42) = SysColor;
    *((_BYTE *)pbmi + 40) = BYTE2(SysColor);
    *((_BYTE *)pbmi + 41) = BYTE1(SysColor);
    *((_BYTE *)pbmi + 43) = 0;
    v3 = GetSysColor(20);
    *((_BYTE *)pbmi + 46) = v3;
    *((_BYTE *)pbmi + 44) = BYTE2(v3);
    *((_BYTE *)pbmi + 45) = BYTE1(v3);
    v4 = 0;
    *((_BYTE *)pbmi + 47) = 0;
    do
    {
      v5 = (unsigned int)v4;
      v6 = _mm_cvtsi32_si128(v4);
      v4 += 4;
      v7 = _mm_andnot_ps(
             (__m128)_mm_cmpeq_epi32(
                       (__m128i)_mm_and_ps((__m128)_mm_add_epi32(_mm_shuffle_epi32(v6, 0), (__m128i)_xmm), (__m128)_xmm),
                       (__m128i)_xmm),
             (__m128)_xmm_ffffffffffffffffffffffffffffffff);
      *(__m128 *)((char *)pjBits + 4 * v5) = _mm_or_ps(
                                               _mm_and_ps(
                                                 _mm_or_ps(
                                                   _mm_and_ps(v7, (__m128)_xmm_aaaa5555aaaa5555aaaa5555aaaa5555),
                                                   _mm_andnot_ps(
                                                     v7,
                                                     (__m128)_mm_loadu_si128((const __m128i *)((char *)pjBits + 4 * v5)))),
                                                 v7),
                                               _mm_andnot_ps(v7, (__m128)_xmm));
    }
    while ( v4 < 8 );
    DC = GetDC(0);
    DIBitmap = CreateDIBitmap(DC, (const BITMAPINFOHEADER *)pbmi, 4u, pjBits, (const BITMAPINFO *)pbmi, 0);
    ReleaseDC(0, DC);
    LocalFree(pbmi);
    return DIBitmap;
  }
  return result;
}

```

## disassembly

```asm
0x18000f9a8  mov     [rsp+arg_0], rbx
0x18000f9ad  mov     [rsp+arg_8], rsi
0x18000f9b2  push    rdi
0x18000f9b3  sub     rsp, 60h
0x18000f9b7  mov     rax, cs:__security_cookie
0x18000f9be  xor     rax, rsp
0x18000f9c1  mov     [rsp+68h+var_18], rax
0x18000f9c6  mov     edx, 68h ; 'h'; uBytes
0x18000f9cb  lea     ecx, [rdx-28h]; uFlags
0x18000f9ce  call    cs:__imp_LocalAlloc
0x18000f9d4  xor     ebx, ebx
0x18000f9d6  mov     rsi, rax
0x18000f9d9  test    rax, rax
0x18000f9dc  jz      loc_18000FAE2
0x18000f9e2  mov     edi, 8
0x18000f9e7  mov     dword ptr [rax], 28h ; '('
0x18000f9ed  mov     [rax+4], edi
0x18000f9f0  mov     [rax+8], edi
0x18000f9f3  mov     qword ptr [rax+0Ch], 10001h
0x18000f9fb  lea     ecx, [rdi+7]; nIndex
0x18000f9fe  call    cs:__imp_GetSysColor
0x18000fa04  mov     ecx, eax
0x18000fa06  mov     [rsi+2Ah], al
0x18000fa09  shr     ecx, 10h
0x18000fa0c  mov     [rsi+28h], cl
0x18000fa0f  movzx   ecx, ax
0x18000fa12  shr     cx, 8
0x18000fa16  mov     [rsi+29h], cl
0x18000fa19  lea     ecx, [rdi+0Ch]; nIndex
0x18000fa1c  mov     [rsi+2Bh], bl
0x18000fa1f  call    cs:__imp_GetSysColor
0x18000fa25  mov     ecx, eax
0x18000fa27  mov     [rsi+2Eh], al
0x18000fa2a  shr     ecx, 10h
0x18000fa2d  mov     [rsi+2Ch], cl
0x18000fa30  movzx   ecx, ax
0x18000fa33  shr     cx, 8
0x18000fa37  mov     [rsi+2Dh], cl
0x18000fa3a  mov     ecx, ebx
0x18000fa3c  mov     [rsi+2Fh], bl
0x18000fa3f  mov     eax, ecx
0x18000fa41  movd    xmm3, ecx
0x18000fa45  add     ecx, 4
0x18000fa48  pshufd  xmm3, xmm3, 0
0x18000fa4d  paddd   xmm3, cs:__xmm@00000003000000020000000100000000
0x18000fa55  andps   xmm3, cs:__xmm@00000001000000010000000100000001
0x18000fa5c  pcmpeqd xmm3, cs:__xmm@00000000000000000000000000000000
0x18000fa64  andnps  xmm3, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000fa6b  movdqa  xmm2, xmm3
0x18000fa6f  movdqa  xmm1, xmm3
0x18000fa73  andps   xmm2, cs:__xmm@aaaa5555aaaa5555aaaa5555aaaa5555
0x18000fa7a  movdqu  xmm0, [rsp+rax*4+68h+pjBits]
0x18000fa80  andnps  xmm1, xmm0
0x18000fa83  orps    xmm2, xmm1
0x18000fa86  andps   xmm2, xmm3
0x18000fa89  andnps  xmm3, cs:__xmm@5555aaaa5555aaaa5555aaaa5555aaaa
0x18000fa90  orps    xmm2, xmm3
0x18000fa93  movdqu  [rsp+rax*4+68h+pjBits], xmm2
0x18000fa99  cmp     ecx, edi
0x18000fa9b  jl      short loc_18000FA3F
0x18000fa9d  xor     ecx, ecx; hWnd
0x18000fa9f  call    cs:__imp_GetDC
0x18000faa5  mov     [rsp+68h+iUsage], ebx; iUsage
0x18000faa9  lea     r9, [rsp+68h+pjBits]; pjBits
0x18000faae  mov     rcx, rax; hdc
0x18000fab1  mov     [rsp+68h+pbmi], rsi; pbmi
0x18000fab6  mov     r8d, 4; flInit
0x18000fabc  mov     rdx, rsi; pbmih
0x18000fabf  mov     rdi, rax
0x18000fac2  call    cs:__imp_CreateDIBitmap
0x18000fac8  mov     rdx, rdi; hDC
0x18000facb  xor     ecx, ecx; hWnd
0x18000facd  mov     rbx, rax
0x18000fad0  call    cs:__imp_ReleaseDC
0x18000fad6  mov     rcx, rsi; hMem
0x18000fad9  call    cs:__imp_LocalFree
0x18000fadf  mov     rax, rbx
0x18000fae2  mov     rcx, [rsp+68h+var_18]
0x18000fae7  xor     rcx, rsp; StackCookie
0x18000faea  call    __security_check_cookie
0x18000faef  mov     rbx, [rsp+68h+arg_0]
0x18000faf4  mov     rsi, [rsp+68h+arg_8]
0x18000faf9  add     rsp, 60h
0x18000fafd  pop     rdi
0x18000fafe  retn
```
