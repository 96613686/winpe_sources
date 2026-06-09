# LoadGlyphMetricsWithGetGlyphOutline(HDC__ *,SIZE_CACHE *,ushort,ushort)

- ea: `0x1800741cc`
- end: `0x18007452d`
- name: `?LoadGlyphMetricsWithGetGlyphOutline@@YAJPEAUHDC__@@PEAUSIZE_CACHE@@GG@Z`
- size: `865`
- prototype: `__int64 __fastcall(HDC, struct SIZE_CACHE *, unsigned __int16, unsigned __int16)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001a384`

## callees

- `0x180004c00`
- `0x180006978`
- `0x180006a28`
- `0x18001ab0c`
- `0x18002ef90`
- `0x18005d5a0`
- `0x18005d7f0`
- `0x1800741cc`
- `0x18007d480`
- `0x18007f800`

## import_xrefs

- `GDI32!SelectObject` at `0x1800742a7`
- `GDI32!SelectObject` at `0x180074300`
- `GDI32!SelectObject` at `0x1800744be`
- `GDI32!SelectObject` at `0x1800744e8`
- `GDI32!SelectObject` at `0x1800742a7`
- `GDI32!SelectObject` at `0x180074300`
- `GDI32!SelectObject` at `0x1800744be`
- `GDI32!SelectObject` at `0x1800744e8`
- `GDI32!DeleteObject` at `0x18007430f`
- `GDI32!DeleteObject` at `0x1800744cd`
- `GDI32!DeleteObject` at `0x1800744f7`
- `GDI32!DeleteObject` at `0x18007430f`
- `GDI32!DeleteObject` at `0x1800744cd`
- `GDI32!DeleteObject` at `0x1800744f7`
- `win32u!NtGdiGetTextCharsetInfo` at `0x180074284`
- `win32u!NtGdiGetTextCharsetInfo` at `0x180074284`

## pseudocode

```c
__int64 __fastcall LoadGlyphMetricsWithGetGlyphOutline(
        HDC a1,
        struct SIZE_CACHE *a2,
        unsigned __int16 a3,
        unsigned __int16 a4)
{
  signed int v4; // r12d
  unsigned __int64 v5; // r14
  void *DCObject; // rax
  HGDIOBJ v10; // rdi
  HFONT v11; // rax
  signed int v12; // esi
  int v13; // r14d
  HGDIOBJ v14; // rax
  signed int v15; // r13d
  __int64 v16; // r14
  __int64 v17; // r12
  __int64 i; // rcx
  int v19; // ecx
  __int64 j; // rcx
  __int64 v21; // r8
  unsigned int v22; // esi
  HGDIOBJ v23; // rax
  HGDIOBJ v24; // rax
  _GLYPHMETRICS v25; // [rsp+40h] [rbp-79h] BYREF
  _MAT2 v26; // [rsp+58h] [rbp-61h] BYREF
  LOGFONTA pv; // [rsp+68h] [rbp-51h] BYREF
  __int64 v28; // [rsp+A8h] [rbp-11h] BYREF
  int gmCellIncX; // [rsp+B0h] [rbp-9h]
  int v30; // [rsp+B4h] [rbp-5h]
  LONG x; // [rsp+B8h] [rbp-1h]
  int v32; // [rsp+BCh] [rbp+3h]
  UINT v33; // [rsp+C0h] [rbp+7h]
  __int64 v34; // [rsp+C4h] [rbp+Bh]
  LONG y; // [rsp+CCh] [rbp+13h]
  int v36; // [rsp+D0h] [rbp+17h]
  UINT v37; // [rsp+D4h] [rbp+1Bh]

  v4 = a4;
  v5 = a3;
  v26 = 0;
  v26.eM11.value = 1;
  v26.eM22.value = 1;
  memset(&v25, 0, sizeof(v25));
  memset(&pv, 0, sizeof(pv));
  DCObject = (void *)GetDCObject(a1, 655360);
  if ( !DCObject || !GetObjectA(DCObject, 60, &pv) )
    return HRESULT_FROM_LAST_WIN32_ERROR();
  v10 = 0;
  if ( pv.lfOrientation )
  {
    *(_QWORD *)&pv.lfEscapement = 0;
    GetTextFaceA(a1, 32, pv.lfFaceName);
    pv.lfCharSet = NtGdiGetTextCharsetInfo(a1, 0, 0);
    v11 = CreateFontIndirectA(&pv);
    if ( v11 )
      v10 = SelectObject(a1, v11);
  }
  v12 = v5;
  if ( (*(_BYTE *)((v5 >> 9) + *((_QWORD *)a2 + 13)) & (unsigned __int8)(1 << (((unsigned int)v5 >> 6) & 7))) != 0
    || (v13 = InitializeMetricBlock(a2, v5), v13 >= 0) )
  {
    v15 = v4;
    while ( v12 < v15 )
    {
      v16 = (__int64)v12 >> 8;
      v17 = v12 % 256;
      if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a2 + 14) + 8 * v16) + 8 * v17) == -1 )
      {
        if ( GetGlyphOutlineInternalA(a1, v12, 0x80u, &v25, 0, 0, &v26, 0) == -1 )
        {
          v22 = HRESULT_FROM_LAST_WIN32_ERROR();
          if ( v10 )
          {
            v23 = SelectObject(a1, v10);
            DeleteObject(v23);
          }
          return v22;
        }
        gmCellIncX = v25.gmCellIncX;
        x = v25.gmptGlyphOrigin.x;
        y = v25.gmptGlyphOrigin.y;
        v28 = 0;
        v30 = 0;
        v32 = 0;
        v33 = v25.gmCellIncX - v25.gmBlackBoxX - v25.gmptGlyphOrigin.x;
        v34 = 0;
        v36 = 0;
        v37 = v25.gmptGlyphOrigin.y - v25.gmBlackBoxY;
        if ( !(unsigned int)DPToLPInternal(a1, &v28, 6, 0) )
          return HRESULT_FROM_LAST_WIN32_ERROR();
        for ( i = 1; i != 6; ++i )
        {
          *((_DWORD *)&v28 + 2 * i) -= v28;
          *((_DWORD *)&v28 + 2 * i + 1) -= HIDWORD(v28);
        }
        v19 = gmCellIncX;
        if ( gmCellIncX < 0 )
        {
          for ( j = 1; j != 6; ++j )
            *((_DWORD *)&v28 + 2 * j) = -*((_DWORD *)&v28 + 2 * j);
          v19 = gmCellIncX;
        }
        v21 = *(_QWORD *)(*((_QWORD *)a2 + 14) + 8 * v16);
        *(_DWORD *)(v21 + 8 * v17) = v19;
        *(_BYTE *)(v21 + 8 * v17 + 4) = ((x << 7) + *((_DWORD *)a2 + 4) / 2) / *((_DWORD *)a2 + 4);
        *(_BYTE *)(v21 + 8 * v17 + 5) = (int)((v33 << 7) + *((_DWORD *)a2 + 4) / 2) / *((_DWORD *)a2 + 4);
        *(_BYTE *)(v21 + 8 * v17 + 6) = ((y << 7) + *((_DWORD *)a2 + 4) / 2) / *((_DWORD *)a2 + 4);
        *(_BYTE *)(v21 + 8 * v17 + 7) = (int)((v37 << 7) + *((_DWORD *)a2 + 4) / 2) / *((_DWORD *)a2 + 4);
      }
      ++v12;
    }
    if ( v10 )
    {
      v24 = SelectObject(a1, v10);
      DeleteObject(v24);
    }
    return 0;
  }
  else
  {
    if ( v10 )
    {
      v14 = SelectObject(a1, v10);
      DeleteObject(v14);
    }
    return (unsigned int)v13;
  }
}

```

## disassembly

```asm
0x1800741cc  mov     [rsp-8+arg_18], rbx
0x1800741d1  push    rbp
0x1800741d2  push    rsi
0x1800741d3  push    rdi
0x1800741d4  push    r12
0x1800741d6  push    r13
0x1800741d8  push    r14
0x1800741da  push    r15
0x1800741dc  lea     rbp, [rsp-27h]
0x1800741e1  sub     rsp, 0E0h
0x1800741e8  mov     rax, cs:__security_cookie
0x1800741ef  xor     rax, rsp
0x1800741f2  mov     [rbp+57h+var_38], rax
0x1800741f6  xorps   xmm1, xmm1
0x1800741f9  movzx   r12d, r9w
0x1800741fd  xor     eax, eax
0x1800741ff  movzx   r14d, r8w
0x180074203  xorps   xmm0, xmm0
0x180074206  mov     dword ptr [rbp+57h+var_D0.gmCellIncX], eax
0x180074209  mov     eax, 1
0x18007420e  mov     r15, rdx
0x180074211  movups  xmmword ptr [rbp+57h+var_B8.eM11.fract], xmm0
0x180074215  mov     edx, 0A0000h
0x18007421a  mov     [rbp+57h+var_B8.eM11.value], ax
0x18007421e  movups  [rbp+57h+var_88], xmm1
0x180074222  mov     [rbp+57h+var_B8.eM22.value], ax
0x180074226  mov     rbx, rcx
0x180074229  movups  xmmword ptr [rbp+57h+var_D0.gmBlackBoxX], xmm0
0x18007422d  movups  [rbp+57h+pv], xmm1
0x180074231  movups  xmmword ptr [rbp+57h+Name], xmm1
0x180074235  movups  [rbp+57h+var_88+0Ch], xmm1
0x180074239  call    GetDCObject
0x18007423e  test    rax, rax
0x180074241  jnz     short loc_18007424D
0x180074243  call    HRESULT_FROM_LAST_WIN32_ERROR
0x180074248  jmp     loc_180074505
0x18007424d  lea     r8, [rbp+57h+pv]; pv
0x180074251  mov     edx, 3Ch ; '<'; c
0x180074256  mov     rcx, rax; h
0x180074259  call    GetObjectA
0x18007425e  test    eax, eax
0x180074260  jz      short loc_180074243
0x180074262  xor     edi, edi
0x180074264  cmp     dword ptr [rbp+57h+pv+0Ch], edi
0x180074267  jz      short loc_1800742B6
0x180074269  lea     r8, [rbp+57h+Name+0Ch]; lpName
0x18007426d  mov     qword ptr [rbp+57h+pv+8], rdi
0x180074271  lea     edx, [rdi+20h]; c
0x180074274  mov     rcx, rbx; hdc
0x180074277  call    GetTextFaceA
0x18007427c  xor     r8d, r8d
0x18007427f  xor     edx, edx
0x180074281  mov     rcx, rbx
0x180074284  call    cs:__imp_NtGdiGetTextCharsetInfo
0x18007428b  nop     dword ptr [rax+rax+00h]
0x180074290  lea     rcx, [rbp+57h+pv]; lplf
0x180074294  mov     [rbp+57h+Name+7], al
0x180074297  call    CreateFontIndirectA
0x18007429c  test    rax, rax
0x18007429f  jz      short loc_1800742B6
0x1800742a1  mov     rdx, rax; h
0x1800742a4  mov     rcx, rbx; hdc
0x1800742a7  call    cs:__imp_SelectObject
0x1800742ae  nop     dword ptr [rax+rax+00h]
0x1800742b3  mov     rdi, rax
0x1800742b6  mov     rcx, [r15+68h]
0x1800742ba  mov     r8, r14
0x1800742bd  shr     r8, 9
0x1800742c1  mov     r10d, 1
0x1800742c7  mov     esi, r14d
0x1800742ca  mov     r9b, [r8+rcx]
0x1800742ce  mov     ecx, r14d
0x1800742d1  shr     ecx, 6
0x1800742d4  mov     r8d, r10d
0x1800742d7  and     ecx, 7
0x1800742da  shl     r8d, cl
0x1800742dd  test    r8b, r9b
0x1800742e0  jnz     short loc_180074329
0x1800742e2  movzx   edx, r14w; unsigned __int16
0x1800742e6  mov     rcx, r15; struct SIZE_CACHE *
0x1800742e9  call    ?InitializeMetricBlock@@YAJPEAUSIZE_CACHE@@G@Z; InitializeMetricBlock(SIZE_CACHE *,ushort)
0x1800742ee  mov     r14d, eax
0x1800742f1  test    eax, eax
0x1800742f3  jns     short loc_180074323
0x1800742f5  test    rdi, rdi
0x1800742f8  jz      short loc_18007431B
0x1800742fa  mov     rdx, rdi; h
0x1800742fd  mov     rcx, rbx; hdc
0x180074300  call    cs:__imp_SelectObject
0x180074307  nop     dword ptr [rax+rax+00h]
0x18007430c  mov     rcx, rax; ho
0x18007430f  call    cs:__imp_DeleteObject
0x180074316  nop     dword ptr [rax+rax+00h]
0x18007431b  mov     eax, r14d
0x18007431e  jmp     loc_180074505
0x180074323  mov     r10d, 1
0x180074329  mov     r13d, r12d
0x18007432c  cmp     esi, r13d
0x18007432f  jge     loc_1800744DD
0x180074335  mov     eax, esi
0x180074337  movsxd  r14, esi
0x18007433a  cdq
0x18007433b  sar     r14, 8
0x18007433f  mov     ecx, 100h
0x180074344  idiv    ecx
0x180074346  mov     rax, [r15+70h]
0x18007434a  movsxd  r12, edx
0x18007434d  mov     rcx, [rax+r14*8]
0x180074351  cmp     dword ptr [rcx+r12*8], 0FFFFFFFFh
0x180074356  jnz     loc_1800744A4
0x18007435c  mov     [rsp+110h+var_D8], 0; int
0x180074364  lea     rax, [rbp+57h+var_B8]
0x180074368  mov     [rsp+110h+var_E0], rax; struct _MAT2 *
0x18007436d  lea     r9, [rbp+57h+var_D0]; struct _GLYPHMETRICS *
0x180074371  mov     [rsp+110h+var_E8], 0; void *
0x18007437a  mov     r8d, 80h; unsigned int
0x180074380  mov     edx, esi; unsigned int
0x180074382  mov     [rsp+110h+var_F0], 0; unsigned int
0x18007438a  mov     rcx, rbx; HDC
0x18007438d  call    ?GetGlyphOutlineInternalA@@YAKPEAUHDC__@@IIPEAU_GLYPHMETRICS@@KPEAXPEBU_MAT2@@H@Z; GetGlyphOutlineInternalA(HDC__ *,uint,uint,_GLYPHMETRICS *,ulong,void *,_MAT2 const *,int)
0x180074392  cmp     eax, 0FFFFFFFFh
0x180074395  jz      loc_1800744AC
0x18007439b  movsx   ecx, [rbp+57h+var_D0.gmCellIncX]
0x18007439f  xor     edx, edx
0x1800743a1  mov     eax, [rbp+57h+var_D0.gmptGlyphOrigin.x]
0x1800743a4  xor     r9d, r9d
0x1800743a7  mov     [rbp+57h+var_60], ecx
0x1800743aa  sub     ecx, [rbp+57h+var_D0.gmBlackBoxX]
0x1800743ad  sub     ecx, eax
0x1800743af  mov     [rbp+57h+var_58], eax
0x1800743b2  mov     eax, [rbp+57h+var_D0.gmptGlyphOrigin.y]
0x1800743b5  lea     r8d, [rdx+6]
0x1800743b9  mov     [rbp+57h+var_44], eax
0x1800743bc  sub     eax, [rbp+57h+var_D0.gmBlackBoxY]
0x1800743bf  mov     [rbp+57h+var_68], rdx
0x1800743c3  mov     [rbp+57h+var_5C], edx
0x1800743c6  mov     [rbp+57h+var_54], edx
0x1800743c9  mov     [rbp+57h+var_50], ecx
0x1800743cc  mov     rcx, rbx
0x1800743cf  mov     [rbp+57h+var_4C], rdx
0x1800743d3  mov     [rbp+57h+var_40], edx
0x1800743d6  lea     rdx, [rbp+57h+var_68]
0x1800743da  mov     [rbp+57h+var_3C], eax
0x1800743dd  call    DPToLPInternal
0x1800743e2  test    eax, eax
0x1800743e4  jz      loc_180074243
0x1800743ea  mov     r10d, 1
0x1800743f0  mov     ecx, r10d
0x1800743f3  mov     eax, dword ptr [rbp+57h+var_68]
0x1800743f6  sub     dword ptr [rbp+rcx*8+57h+var_68], eax
0x1800743fa  mov     eax, dword ptr [rbp+57h+var_68+4]
0x1800743fd  sub     dword ptr [rbp+rcx*8+57h+var_68+4], eax
0x180074401  add     rcx, r10
0x180074404  cmp     rcx, 6
0x180074408  jnz     short loc_1800743F3
0x18007440a  mov     ecx, [rbp+57h+var_60]
0x18007440d  test    ecx, ecx
0x18007440f  jns     short loc_18007442A
0x180074411  mov     rcx, r10
0x180074414  mov     eax, dword ptr [rbp+rcx*8+57h+var_68]
0x180074418  neg     eax
0x18007441a  mov     dword ptr [rbp+rcx*8+57h+var_68], eax
0x18007441e  add     rcx, r10
0x180074421  cmp     rcx, 6
0x180074425  jnz     short loc_180074414
0x180074427  mov     ecx, [rbp+57h+var_60]
0x18007442a  mov     rax, [r15+70h]
0x18007442e  mov     r9d, 2
0x180074434  mov     r8, [rax+r14*8]
0x180074438  mov     [r8+r12*8], ecx
0x18007443c  mov     eax, [r15+10h]
0x180074440  mov     ecx, [rbp+57h+var_58]
0x180074443  cdq
0x180074444  idiv    r9d
0x180074447  shl     ecx, 7
0x18007444a  add     eax, ecx
0x18007444c  cdq
0x18007444d  idiv    dword ptr [r15+10h]
0x180074451  mov     [r8+r12*8+4], al
0x180074456  mov     eax, [r15+10h]
0x18007445a  mov     ecx, [rbp+57h+var_50]
0x18007445d  cdq
0x18007445e  idiv    r9d
0x180074461  shl     ecx, 7
0x180074464  add     eax, ecx
0x180074466  cdq
0x180074467  idiv    dword ptr [r15+10h]
0x18007446b  mov     [r8+r12*8+5], al
0x180074470  mov     eax, [r15+10h]
0x180074474  mov     ecx, [rbp+57h+var_44]
0x180074477  cdq
0x180074478  idiv    r9d
0x18007447b  shl     ecx, 7
0x18007447e  add     eax, ecx
0x180074480  cdq
0x180074481  idiv    dword ptr [r15+10h]
0x180074485  mov     [r8+r12*8+6], al
0x18007448a  mov     eax, [r15+10h]
0x18007448e  mov     ecx, [rbp+57h+var_3C]
0x180074491  cdq
0x180074492  idiv    r9d
0x180074495  shl     ecx, 7
0x180074498  add     eax, ecx
0x18007449a  cdq
0x18007449b  idiv    dword ptr [r15+10h]
0x18007449f  mov     [r8+r12*8+7], al
0x1800744a4  add     esi, r10d
0x1800744a7  jmp     loc_18007432C
0x1800744ac  call    HRESULT_FROM_LAST_WIN32_ERROR
0x1800744b1  mov     esi, eax
0x1800744b3  test    rdi, rdi
0x1800744b6  jz      short loc_1800744D9
0x1800744b8  mov     rdx, rdi; h
0x1800744bb  mov     rcx, rbx; hdc
0x1800744be  call    cs:__imp_SelectObject
0x1800744c5  nop     dword ptr [rax+rax+00h]
0x1800744ca  mov     rcx, rax; ho
0x1800744cd  call    cs:__imp_DeleteObject
0x1800744d4  nop     dword ptr [rax+rax+00h]
0x1800744d9  mov     eax, esi
0x1800744db  jmp     short loc_180074505
0x1800744dd  test    rdi, rdi
0x1800744e0  jz      short loc_180074503
0x1800744e2  mov     rdx, rdi; h
0x1800744e5  mov     rcx, rbx; hdc
0x1800744e8  call    cs:__imp_SelectObject
0x1800744ef  nop     dword ptr [rax+rax+00h]
0x1800744f4  mov     rcx, rax; ho
0x1800744f7  call    cs:__imp_DeleteObject
0x1800744fe  nop     dword ptr [rax+rax+00h]
0x180074503  xor     eax, eax
0x180074505  mov     rcx, [rbp+57h+var_38]
0x180074509  xor     rcx, rsp; StackCookie
0x18007450c  call    __security_check_cookie
0x180074511  mov     rbx, [rsp+110h+arg_18]
0x180074519  add     rsp, 0E0h
0x180074520  pop     r15
0x180074522  pop     r14
0x180074524  pop     r13
0x180074526  pop     r12
0x180074528  pop     rdi
0x180074529  pop     rsi
0x18007452a  pop     rbp
0x18007452b  retn
```
