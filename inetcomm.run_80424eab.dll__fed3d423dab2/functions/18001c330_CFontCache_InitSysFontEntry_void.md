# CFontCache::InitSysFontEntry(void)

- ea: `0x18001c330`
- end: `0x18001c5f2`
- name: `?InitSysFontEntry@CFontCache@@AEAAJXZ`
- size: `706`
- prototype: `__int64 __fastcall(CFontCache *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18001c130`
- `0x1800c7bd4`
- `0x1800c7c40`

## callees

- `0x18001c330`
- `0x1800cc9ba`
- `0x1800cca00`

## import_xrefs

- `GDI32!SelectObject` at `0x18001c477`
- `GDI32!SelectObject` at `0x18001c49d`
- `GDI32!SelectObject` at `0x18001c477`
- `GDI32!SelectObject` at `0x18001c49d`
- `GDI32!DeleteObject` at `0x18001c4b1`
- `GDI32!DeleteObject` at `0x18001c4b1`
- `GDI32!GetTextMetricsA` at `0x18001c487`
- `GDI32!GetTextMetricsA` at `0x18001c487`
- `GDI32!TranslateCharsetInfo` at `0x18001c3b1`
- `GDI32!TranslateCharsetInfo` at `0x18001c3b1`
- `GDI32!CreateFontIndirectA` at `0x18001c43e`
- `GDI32!CreateFontIndirectA` at `0x18001c4c7`
- `GDI32!CreateFontIndirectA` at `0x18001c4fc`
- `GDI32!CreateFontIndirectA` at `0x18001c523`
- `GDI32!CreateFontIndirectA` at `0x18001c5bc`
- `GDI32!CreateFontIndirectA` at `0x18001c43e`
- `GDI32!CreateFontIndirectA` at `0x18001c4c7`
- `GDI32!CreateFontIndirectA` at `0x18001c4fc`
- `GDI32!CreateFontIndirectA` at `0x18001c523`
- `GDI32!CreateFontIndirectA` at `0x18001c5bc`
- `KERNEL32!GetACP` at `0x18001c391`
- `KERNEL32!GetACP` at `0x18001c391`
- `USER32!GetDC` at `0x18001c44e`
- `USER32!GetDC` at `0x18001c44e`
- `USER32!ReleaseDC` at `0x18001c4a8`
- `USER32!ReleaseDC` at `0x18001c4a8`
- `USER32!SystemParametersInfoA` at `0x18001c3c6`
- `USER32!SystemParametersInfoA` at `0x18001c557`
- `USER32!SystemParametersInfoA` at `0x18001c3c6`
- `USER32!SystemParametersInfoA` at `0x18001c557`

## pseudocode

```c
__int64 __fastcall CFontCache::InitSysFontEntry(CFontCache *this)
{
  UINT ACP; // eax
  CHAR *lfFaceName; // r8
  _BYTE *v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rdx
  _BYTE *v7; // rax
  unsigned int v8; // edi
  HFONT v9; // r15
  HDC DC; // r14
  HGDIOBJ v11; // rbx
  LONG lfWeight; // ebx
  LONG v13; // eax
  LOGFONTA pvParam; // [rsp+20h] [rbp-E0h] BYREF
  tagCHARSETINFO v16; // [rsp+60h] [rbp-A0h] BYREF
  tagTEXTMETRICA tm; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v18[40]; // [rsp+C0h] [rbp-40h] BYREF
  LOGFONTA v19; // [rsp+160h] [rbp+60h]

  memset_0(v18, 0, 0x158u);
  memset(&v16, 0, sizeof(v16));
  memset(&pvParam, 0, sizeof(pvParam));
  ACP = GetACP();
  **((_DWORD **)this + 8) = ACP;
  *((_DWORD *)this + 297) = ACP;
  TranslateCharsetInfo((DWORD *)(unsigned __int16)ACP, &v16, 2u);
  if ( !SystemParametersInfoA(0x1Fu, 0x3Cu, &pvParam, 0) )
    return (unsigned int)-2147467259;
  lfFaceName = pvParam.lfFaceName;
  v4 = (_BYTE *)(*((_QWORD *)this + 8) + 4LL);
  v5 = 2147483646;
  v6 = 32;
  do
  {
    if ( !v5 )
      break;
    if ( !*lfFaceName )
      break;
    *v4++ = *lfFaceName++;
    --v5;
    --v6;
  }
  while ( v6 );
  v7 = v4 - 1;
  if ( v6 )
    v7 = v4;
  *v7 = 0;
  v8 = v6 == 0 ? 0x8007007A : 0;
  if ( v6 )
  {
    pvParam.lfCharSet = v16.ciCharset;
    v9 = CreateFontIndirectA(&pvParam);
    if ( v9 )
    {
      DC = GetDC(0);
      if ( DC )
      {
        memset(&tm, 0, sizeof(tm));
        v11 = SelectObject(DC, v9);
        GetTextMetricsA(DC, &tm);
        pvParam.lfHeight = tm.tmInternalLeading - tm.tmHeight;
        SelectObject(DC, v11);
        ReleaseDC(0, DC);
      }
      DeleteObject(v9);
    }
    if ( !*(_QWORD *)(*((_QWORD *)this + 8) + 40LL) )
      *(_QWORD *)(*((_QWORD *)this + 8) + 40LL) = CreateFontIndirectA(&pvParam);
    if ( !*(_QWORD *)(*((_QWORD *)this + 8) + 48LL) )
    {
      lfWeight = pvParam.lfWeight;
      v13 = 1000;
      if ( pvParam.lfWeight < 700 )
        v13 = 700;
      pvParam.lfWeight = v13;
      *(_QWORD *)(*((_QWORD *)this + 8) + 48LL) = CreateFontIndirectA(&pvParam);
      pvParam.lfWeight = lfWeight;
    }
    if ( !*(_QWORD *)(*((_QWORD *)this + 8) + 64LL) )
    {
      pvParam.lfStrikeOut = 1;
      *(_QWORD *)(*((_QWORD *)this + 8) + 64LL) = CreateFontIndirectA(&pvParam);
    }
    if ( !*(_QWORD *)(*((_QWORD *)this + 8) + 56LL) )
    {
      v18[0] = 344;
      if ( SystemParametersInfoA(0x29u, 0x158u, v18, 0) )
      {
        pvParam = v19;
        *(_QWORD *)(*((_QWORD *)this + 8) + 56LL) = CreateFontIndirectA(&pvParam);
        return v8;
      }
      return (unsigned int)-2147467259;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18001c330  push    rbp
0x18001c332  push    rbx
0x18001c333  push    rsi
0x18001c334  push    rdi
0x18001c335  push    r14
0x18001c337  push    r15
0x18001c339  lea     rbp, [rsp-138h]
0x18001c341  sub     rsp, 238h
0x18001c348  mov     rax, cs:__security_cookie
0x18001c34f  xor     rax, rsp
0x18001c352  mov     [rbp+160h+var_40], rax
0x18001c359  mov     rsi, rcx
0x18001c35c  xor     edx, edx; Val
0x18001c35e  lea     rcx, [rbp+160h+var_1A0]; void *
0x18001c362  mov     r8d, 158h; Size
0x18001c368  call    memset_0
0x18001c36d  xorps   xmm1, xmm1
0x18001c370  xorps   xmm0, xmm0
0x18001c373  movups  [rsp+260h+var_220], xmm1
0x18001c378  movups  [rsp+260h+var_220+0Ch], xmm1
0x18001c37d  movups  xmmword ptr [rsp+260h+var_200.ciCharset], xmm0
0x18001c382  movups  xmmword ptr [rsp+260h+var_200.fs.fsUsb+8], xmm0
0x18001c387  movups  [rsp+260h+pvParam], xmm1
0x18001c38c  movups  [rsp+260h+var_230], xmm1
0x18001c391  call    cs:__imp_GetACP
0x18001c397  mov     rcx, [rsi+40h]
0x18001c39b  lea     rdx, [rsp+260h+var_200]; lpCs
0x18001c3a0  mov     r8d, 2; dwFlags
0x18001c3a6  mov     [rcx], eax
0x18001c3a8  movzx   ecx, ax; lpSrc
0x18001c3ab  mov     [rsi+4A4h], eax
0x18001c3b1  call    cs:__imp_TranslateCharsetInfo
0x18001c3b7  xor     r9d, r9d; fWinIni
0x18001c3ba  lea     r8, [rsp+260h+pvParam]; pvParam
0x18001c3bf  lea     edx, [r9+3Ch]; uiParam
0x18001c3c3  lea     ecx, [rdx-1Dh]; uiAction
0x18001c3c6  call    cs:__imp_SystemParametersInfoA
0x18001c3cc  test    eax, eax
0x18001c3ce  jz      loc_18001C5CC
0x18001c3d4  mov     rcx, [rsi+40h]
0x18001c3d8  lea     r8, [rsp+260h+var_230+0Ch]
0x18001c3dd  add     rcx, 4
0x18001c3e1  mov     eax, 7FFFFFFEh
0x18001c3e6  mov     edx, 20h ; ' '
0x18001c3eb  test    rax, rax
0x18001c3ee  jz      short loc_18001C40A
0x18001c3f0  mov     r9b, [r8]
0x18001c3f3  test    r9b, r9b
0x18001c3f6  jz      short loc_18001C40A
0x18001c3f8  mov     [rcx], r9b
0x18001c3fb  inc     r8
0x18001c3fe  inc     rcx
0x18001c401  dec     rax
0x18001c404  sub     rdx, 1
0x18001c408  jnz     short loc_18001C3EB
0x18001c40a  test    rdx, rdx
0x18001c40d  lea     rax, [rcx-1]
0x18001c411  cmovnz  rax, rcx
0x18001c415  mov     byte ptr [rax], 0
0x18001c418  mov     rax, rdx
0x18001c41b  neg     rax
0x18001c41e  sbb     edi, edi
0x18001c420  not     edi
0x18001c422  and     edi, 8007007Ah
0x18001c428  test    rdx, rdx
0x18001c42b  jz      loc_18001C5D1
0x18001c431  mov     al, byte ptr [rsp+260h+var_200.ciCharset]
0x18001c435  lea     rcx, [rsp+260h+pvParam]; lplf
0x18001c43a  mov     byte ptr [rsp+260h+var_230+7], al
0x18001c43e  call    cs:__imp_CreateFontIndirectA
0x18001c444  mov     r15, rax
0x18001c447  test    rax, rax
0x18001c44a  jz      short loc_18001C4B7
0x18001c44c  xor     ecx, ecx; hWnd
0x18001c44e  call    cs:__imp_GetDC
0x18001c454  mov     r14, rax
0x18001c457  test    rax, rax
0x18001c45a  jz      short loc_18001C4AE
0x18001c45c  xorps   xmm0, xmm0
0x18001c45f  xor     eax, eax
0x18001c461  mov     rdx, r15; h
0x18001c464  mov     qword ptr [rbp+160h+tm.tmItalic], rax
0x18001c468  mov     rcx, r14; hdc
0x18001c46b  movups  xmmword ptr [rbp+160h+tm.tmHeight], xmm0
0x18001c46f  movups  xmmword ptr [rbp+160h+tm.tmExternalLeading], xmm0
0x18001c473  movups  xmmword ptr [rbp+160h+tm.tmOverhang], xmm0
0x18001c477  call    cs:__imp_SelectObject
0x18001c47d  lea     rdx, [rbp+160h+tm]; lptm
0x18001c481  mov     rcx, r14; hdc
0x18001c484  mov     rbx, rax
0x18001c487  call    cs:__imp_GetTextMetricsA
0x18001c48d  mov     ecx, [rbp+160h+tm.tmInternalLeading]
0x18001c490  mov     rdx, rbx; h
0x18001c493  sub     ecx, [rbp+160h+tm.tmHeight]
0x18001c496  mov     dword ptr [rsp+260h+pvParam], ecx
0x18001c49a  mov     rcx, r14; hdc
0x18001c49d  call    cs:__imp_SelectObject
0x18001c4a3  mov     rdx, r14; hDC
0x18001c4a6  xor     ecx, ecx; hWnd
0x18001c4a8  call    cs:__imp_ReleaseDC
0x18001c4ae  mov     rcx, r15; ho
0x18001c4b1  call    cs:__imp_DeleteObject
0x18001c4b7  mov     rax, [rsi+40h]
0x18001c4bb  cmp     qword ptr [rax+28h], 0
0x18001c4c0  jnz     short loc_18001C4D5
0x18001c4c2  lea     rcx, [rsp+260h+pvParam]; lplf
0x18001c4c7  call    cs:__imp_CreateFontIndirectA
0x18001c4cd  mov     rcx, [rsi+40h]
0x18001c4d1  mov     [rcx+28h], rax
0x18001c4d5  mov     rax, [rsi+40h]
0x18001c4d9  cmp     qword ptr [rax+30h], 0
0x18001c4de  jnz     short loc_18001C50E
0x18001c4e0  mov     ebx, dword ptr [rsp+260h+var_230]
0x18001c4e4  mov     ecx, 2BCh
0x18001c4e9  cmp     ebx, ecx
0x18001c4eb  mov     eax, 3E8h
0x18001c4f0  cmovl   eax, ecx
0x18001c4f3  lea     rcx, [rsp+260h+pvParam]; lplf
0x18001c4f8  mov     dword ptr [rsp+260h+var_230], eax
0x18001c4fc  call    cs:__imp_CreateFontIndirectA
0x18001c502  mov     rcx, [rsi+40h]
0x18001c506  mov     [rcx+30h], rax
0x18001c50a  mov     dword ptr [rsp+260h+var_230], ebx
0x18001c50e  mov     rax, [rsi+40h]
0x18001c512  cmp     qword ptr [rax+40h], 0
0x18001c517  jnz     short loc_18001C531
0x18001c519  lea     rcx, [rsp+260h+pvParam]; lplf
0x18001c51e  mov     byte ptr [rsp+260h+var_230+6], 1
0x18001c523  call    cs:__imp_CreateFontIndirectA
0x18001c529  mov     rcx, [rsi+40h]
0x18001c52d  mov     [rcx+40h], rax
0x18001c531  mov     rax, [rsi+40h]
0x18001c535  cmp     qword ptr [rax+38h], 0
0x18001c53a  jnz     loc_18001C5D1
0x18001c540  xor     r9d, r9d; fWinIni
0x18001c543  mov     [rbp+160h+var_1A0], 158h
0x18001c54a  lea     r8, [rbp+160h+var_1A0]; pvParam
0x18001c54e  mov     edx, 158h; uiParam
0x18001c553  lea     ecx, [r9+29h]; uiAction
0x18001c557  call    cs:__imp_SystemParametersInfoA
0x18001c55d  test    eax, eax
0x18001c55f  jz      short loc_18001C5CC
0x18001c561  mov     eax, [rbp+160h+var_100]
0x18001c564  lea     rcx, [rsp+260h+pvParam]; lplf
0x18001c569  movsd   xmm0, [rbp+160h+var_FC]
0x18001c56e  movups  xmm1, [rbp+160h+var_D8]
0x18001c575  mov     dword ptr [rsp+260h+pvParam], eax
0x18001c579  mov     eax, [rbp+160h+var_F4]
0x18001c57c  mov     dword ptr [rsp+260h+pvParam+0Ch], eax
0x18001c580  mov     eax, dword ptr [rbp+160h+var_F0]
0x18001c583  mov     dword ptr [rsp+260h+var_230], eax
0x18001c587  movzx   eax, word ptr [rbp+160h+var_F0+4]
0x18001c58b  mov     word ptr [rsp+260h+var_230+4], ax
0x18001c590  mov     al, byte ptr [rbp+160h+var_F0+6]
0x18001c593  mov     byte ptr [rsp+260h+var_230+6], al
0x18001c597  mov     al, byte ptr [rbp+160h+var_F0+7]
0x18001c59a  movsd   qword ptr [rsp+260h+pvParam+4], xmm0
0x18001c5a0  movups  xmm0, [rbp+160h+var_E8]
0x18001c5a4  mov     byte ptr [rsp+260h+var_230+7], al
0x18001c5a8  mov     eax, [rbp+160h+var_C8]
0x18001c5ae  mov     [rsp+260h+var_208], eax
0x18001c5b2  movups  [rsp+260h+var_230+8], xmm0
0x18001c5b7  movups  [rsp+260h+var_220+8], xmm1
0x18001c5bc  call    cs:__imp_CreateFontIndirectA
0x18001c5c2  mov     rcx, [rsi+40h]
0x18001c5c6  mov     [rcx+38h], rax
0x18001c5ca  jmp     short loc_18001C5D1
0x18001c5cc  mov     edi, 80004005h
0x18001c5d1  mov     eax, edi
0x18001c5d3  mov     rcx, [rbp+160h+var_40]
0x18001c5da  xor     rcx, rsp; StackCookie
0x18001c5dd  call    __security_check_cookie
0x18001c5e2  add     rsp, 238h
0x18001c5e9  pop     r15
0x18001c5eb  pop     r14
0x18001c5ed  pop     rdi
0x18001c5ee  pop     rsi
0x18001c5ef  pop     rbx
0x18001c5f0  pop     rbp
0x18001c5f1  retn
```
