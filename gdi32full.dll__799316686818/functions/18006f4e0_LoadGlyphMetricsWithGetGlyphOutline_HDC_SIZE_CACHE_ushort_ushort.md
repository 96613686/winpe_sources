# LoadGlyphMetricsWithGetGlyphOutline(HDC__ *,SIZE_CACHE *,ushort,ushort)

- ea: `0x18006f4e0`
- end: `0x18006f810`
- name: `?LoadGlyphMetricsWithGetGlyphOutline@@YAJPEAUHDC__@@PEAUSIZE_CACHE@@GG@Z`
- size: `816`
- prototype: `__int64 __fastcall(HDC, struct SIZE_CACHE *, unsigned __int16, unsigned __int16)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180004d2c`

## callees

- `0x1800054a4`
- `0x18000d620`
- `0x18000d6c0`
- `0x18000e5a0`
- `0x180025fb0`
- `0x180058700`
- `0x180058dd0`
- `0x18006f4e0`
- `0x180078968`
- `0x18007ac50`

## import_xrefs

- `GDI32!SelectObject` at `0x18006f5b5`
- `GDI32!SelectObject` at `0x18006f608`
- `GDI32!SelectObject` at `0x18006f7ba`
- `GDI32!SelectObject` at `0x18006f7d8`
- `GDI32!SelectObject` at `0x18006f5b5`
- `GDI32!SelectObject` at `0x18006f608`
- `GDI32!SelectObject` at `0x18006f7ba`
- `GDI32!SelectObject` at `0x18006f7d8`
- `GDI32!DeleteObject` at `0x18006f611`
- `GDI32!DeleteObject` at `0x18006f7c3`
- `GDI32!DeleteObject` at `0x18006f7e1`
- `GDI32!DeleteObject` at `0x18006f611`
- `GDI32!DeleteObject` at `0x18006f7c3`
- `GDI32!DeleteObject` at `0x18006f7e1`
- `win32u!NtGdiGetTextCharsetInfo` at `0x18006f598`
- `win32u!NtGdiGetTextCharsetInfo` at `0x18006f598`

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
        if ( !(unsigned int)DPToLPInternal((__int64)a1, (__int64)&v28, 6, 0) )
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
0x18006f4e0  mov     [rsp-8+arg_18], rbx
0x18006f4e5  push    rbp
0x18006f4e6  push    rsi
0x18006f4e7  push    rdi
0x18006f4e8  push    r12
0x18006f4ea  push    r13
0x18006f4ec  push    r14
0x18006f4ee  push    r15
0x18006f4f0  lea     rbp, [rsp-27h]
0x18006f4f5  sub     rsp, 0E0h
0x18006f4fc  mov     rax, cs:__security_cookie
0x18006f503  xor     rax, rsp
0x18006f506  mov     [rbp+57h+var_38], rax
0x18006f50a  xorps   xmm1, xmm1
0x18006f50d  movzx   r12d, r9w
0x18006f511  xor     eax, eax
0x18006f513  movzx   r14d, r8w
0x18006f517  xorps   xmm0, xmm0
0x18006f51a  mov     dword ptr [rbp+57h+var_D0.gmCellIncX], eax
0x18006f51d  mov     eax, 1
0x18006f522  mov     r15, rdx
0x18006f525  movups  xmmword ptr [rbp+57h+var_B8.eM11.fract], xmm0
0x18006f529  mov     edx, 0A0000h
0x18006f52e  mov     [rbp+57h+var_B8.eM11.value], ax
0x18006f532  movups  [rbp+57h+var_88], xmm1
0x18006f536  mov     [rbp+57h+var_B8.eM22.value], ax
0x18006f53a  mov     rbx, rcx
0x18006f53d  movups  xmmword ptr [rbp+57h+var_D0.gmBlackBoxX], xmm0
0x18006f541  movups  [rbp+57h+pv], xmm1
0x18006f545  movups  xmmword ptr [rbp+57h+Name], xmm1
0x18006f549  movups  [rbp+57h+var_88+0Ch], xmm1
0x18006f54d  call    GetDCObject
0x18006f552  test    rax, rax
0x18006f555  jnz     short loc_18006F561
0x18006f557  call    HRESULT_FROM_LAST_WIN32_ERROR
0x18006f55c  jmp     loc_18006F7E9
0x18006f561  lea     r8, [rbp+57h+pv]; pv
0x18006f565  mov     edx, 3Ch ; '<'; c
0x18006f56a  mov     rcx, rax; h
0x18006f56d  call    GetObjectA
0x18006f572  test    eax, eax
0x18006f574  jz      short loc_18006F557
0x18006f576  xor     edi, edi
0x18006f578  cmp     dword ptr [rbp+57h+pv+0Ch], edi
0x18006f57b  jz      short loc_18006F5BE
0x18006f57d  lea     r8, [rbp+57h+Name+0Ch]; lpName
0x18006f581  mov     qword ptr [rbp+57h+pv+8], rdi
0x18006f585  lea     edx, [rdi+20h]; c
0x18006f588  mov     rcx, rbx; hdc
0x18006f58b  call    GetTextFaceA
0x18006f590  xor     r8d, r8d
0x18006f593  xor     edx, edx
0x18006f595  mov     rcx, rbx
0x18006f598  call    cs:__imp_NtGdiGetTextCharsetInfo
0x18006f59e  lea     rcx, [rbp+57h+pv]; lplf
0x18006f5a2  mov     [rbp+57h+Name+7], al
0x18006f5a5  call    CreateFontIndirectA
0x18006f5aa  test    rax, rax
0x18006f5ad  jz      short loc_18006F5BE
0x18006f5af  mov     rdx, rax; h
0x18006f5b2  mov     rcx, rbx; hdc
0x18006f5b5  call    cs:__imp_SelectObject
0x18006f5bb  mov     rdi, rax
0x18006f5be  mov     rcx, [r15+68h]
0x18006f5c2  mov     r8, r14
0x18006f5c5  shr     r8, 9
0x18006f5c9  mov     r10d, 1
0x18006f5cf  mov     esi, r14d
0x18006f5d2  mov     r9b, [r8+rcx]
0x18006f5d6  mov     ecx, r14d
0x18006f5d9  shr     ecx, 6
0x18006f5dc  mov     r8d, r10d
0x18006f5df  and     ecx, 7
0x18006f5e2  shl     r8d, cl
0x18006f5e5  test    r8b, r9b
0x18006f5e8  jnz     short loc_18006F625
0x18006f5ea  movzx   edx, r14w; unsigned __int16
0x18006f5ee  mov     rcx, r15; struct SIZE_CACHE *
0x18006f5f1  call    ?InitializeMetricBlock@@YAJPEAUSIZE_CACHE@@G@Z; InitializeMetricBlock(SIZE_CACHE *,ushort)
0x18006f5f6  mov     r14d, eax
0x18006f5f9  test    eax, eax
0x18006f5fb  jns     short loc_18006F61F
0x18006f5fd  test    rdi, rdi
0x18006f600  jz      short loc_18006F617
0x18006f602  mov     rdx, rdi; h
0x18006f605  mov     rcx, rbx; hdc
0x18006f608  call    cs:__imp_SelectObject
0x18006f60e  mov     rcx, rax; ho
0x18006f611  call    cs:__imp_DeleteObject
0x18006f617  mov     eax, r14d
0x18006f61a  jmp     loc_18006F7E9
0x18006f61f  mov     r10d, 1
0x18006f625  mov     r13d, r12d
0x18006f628  cmp     esi, r13d
0x18006f62b  jge     loc_18006F7CD
0x18006f631  mov     eax, esi
0x18006f633  movsxd  r14, esi
0x18006f636  cdq
0x18006f637  sar     r14, 8
0x18006f63b  mov     ecx, 100h
0x18006f640  idiv    ecx
0x18006f642  mov     rax, [r15+70h]
0x18006f646  movsxd  r12, edx
0x18006f649  mov     rcx, [rax+r14*8]
0x18006f64d  cmp     dword ptr [rcx+r12*8], 0FFFFFFFFh
0x18006f652  jnz     loc_18006F7A0
0x18006f658  mov     [rsp+110h+var_D8], 0; int
0x18006f660  lea     rax, [rbp+57h+var_B8]
0x18006f664  mov     [rsp+110h+var_E0], rax; struct _MAT2 *
0x18006f669  lea     r9, [rbp+57h+var_D0]; struct _GLYPHMETRICS *
0x18006f66d  mov     [rsp+110h+var_E8], 0; void *
0x18006f676  mov     r8d, 80h; unsigned int
0x18006f67c  mov     edx, esi; unsigned int
0x18006f67e  mov     [rsp+110h+var_F0], 0; unsigned int
0x18006f686  mov     rcx, rbx; HDC
0x18006f689  call    ?GetGlyphOutlineInternalA@@YAKPEAUHDC__@@IIPEAU_GLYPHMETRICS@@KPEAXPEBU_MAT2@@H@Z; GetGlyphOutlineInternalA(HDC__ *,uint,uint,_GLYPHMETRICS *,ulong,void *,_MAT2 const *,int)
0x18006f68e  cmp     eax, 0FFFFFFFFh
0x18006f691  jz      loc_18006F7A8
0x18006f697  movsx   ecx, [rbp+57h+var_D0.gmCellIncX]
0x18006f69b  xor     edx, edx
0x18006f69d  mov     eax, [rbp+57h+var_D0.gmptGlyphOrigin.x]
0x18006f6a0  xor     r9d, r9d
0x18006f6a3  mov     [rbp+57h+var_60], ecx
0x18006f6a6  sub     ecx, [rbp+57h+var_D0.gmBlackBoxX]
0x18006f6a9  sub     ecx, eax
0x18006f6ab  mov     [rbp+57h+var_58], eax
0x18006f6ae  mov     eax, [rbp+57h+var_D0.gmptGlyphOrigin.y]
0x18006f6b1  lea     r8d, [rdx+6]
0x18006f6b5  mov     [rbp+57h+var_44], eax
0x18006f6b8  sub     eax, [rbp+57h+var_D0.gmBlackBoxY]
0x18006f6bb  mov     [rbp+57h+var_68], rdx
0x18006f6bf  mov     [rbp+57h+var_5C], edx
0x18006f6c2  mov     [rbp+57h+var_54], edx
0x18006f6c5  mov     [rbp+57h+var_50], ecx
0x18006f6c8  mov     rcx, rbx
0x18006f6cb  mov     [rbp+57h+var_4C], rdx
0x18006f6cf  mov     [rbp+57h+var_40], edx
0x18006f6d2  lea     rdx, [rbp+57h+var_68]
0x18006f6d6  mov     [rbp+57h+var_3C], eax
0x18006f6d9  call    DPToLPInternal
0x18006f6de  test    eax, eax
0x18006f6e0  jz      loc_18006F557
0x18006f6e6  mov     r10d, 1
0x18006f6ec  mov     ecx, r10d
0x18006f6ef  mov     eax, dword ptr [rbp+57h+var_68]
0x18006f6f2  sub     dword ptr [rbp+rcx*8+57h+var_68], eax
0x18006f6f6  mov     eax, dword ptr [rbp+57h+var_68+4]
0x18006f6f9  sub     dword ptr [rbp+rcx*8+57h+var_68+4], eax
0x18006f6fd  add     rcx, r10
0x18006f700  cmp     rcx, 6
0x18006f704  jnz     short loc_18006F6EF
0x18006f706  mov     ecx, [rbp+57h+var_60]
0x18006f709  test    ecx, ecx
0x18006f70b  jns     short loc_18006F726
0x18006f70d  mov     rcx, r10
0x18006f710  mov     eax, dword ptr [rbp+rcx*8+57h+var_68]
0x18006f714  neg     eax
0x18006f716  mov     dword ptr [rbp+rcx*8+57h+var_68], eax
0x18006f71a  add     rcx, r10
0x18006f71d  cmp     rcx, 6
0x18006f721  jnz     short loc_18006F710
0x18006f723  mov     ecx, [rbp+57h+var_60]
0x18006f726  mov     rax, [r15+70h]
0x18006f72a  mov     r9d, 2
0x18006f730  mov     r8, [rax+r14*8]
0x18006f734  mov     [r8+r12*8], ecx
0x18006f738  mov     eax, [r15+10h]
0x18006f73c  mov     ecx, [rbp+57h+var_58]
0x18006f73f  cdq
0x18006f740  idiv    r9d
0x18006f743  shl     ecx, 7
0x18006f746  add     eax, ecx
0x18006f748  cdq
0x18006f749  idiv    dword ptr [r15+10h]
0x18006f74d  mov     [r8+r12*8+4], al
0x18006f752  mov     eax, [r15+10h]
0x18006f756  mov     ecx, [rbp+57h+var_50]
0x18006f759  cdq
0x18006f75a  idiv    r9d
0x18006f75d  shl     ecx, 7
0x18006f760  add     eax, ecx
0x18006f762  cdq
0x18006f763  idiv    dword ptr [r15+10h]
0x18006f767  mov     [r8+r12*8+5], al
0x18006f76c  mov     eax, [r15+10h]
0x18006f770  mov     ecx, [rbp+57h+var_44]
0x18006f773  cdq
0x18006f774  idiv    r9d
0x18006f777  shl     ecx, 7
0x18006f77a  add     eax, ecx
0x18006f77c  cdq
0x18006f77d  idiv    dword ptr [r15+10h]
0x18006f781  mov     [r8+r12*8+6], al
0x18006f786  mov     eax, [r15+10h]
0x18006f78a  mov     ecx, [rbp+57h+var_3C]
0x18006f78d  cdq
0x18006f78e  idiv    r9d
0x18006f791  shl     ecx, 7
0x18006f794  add     eax, ecx
0x18006f796  cdq
0x18006f797  idiv    dword ptr [r15+10h]
0x18006f79b  mov     [r8+r12*8+7], al
0x18006f7a0  add     esi, r10d
0x18006f7a3  jmp     loc_18006F628
0x18006f7a8  call    HRESULT_FROM_LAST_WIN32_ERROR
0x18006f7ad  mov     esi, eax
0x18006f7af  test    rdi, rdi
0x18006f7b2  jz      short loc_18006F7C9
0x18006f7b4  mov     rdx, rdi; h
0x18006f7b7  mov     rcx, rbx; hdc
0x18006f7ba  call    cs:__imp_SelectObject
0x18006f7c0  mov     rcx, rax; ho
0x18006f7c3  call    cs:__imp_DeleteObject
0x18006f7c9  mov     eax, esi
0x18006f7cb  jmp     short loc_18006F7E9
0x18006f7cd  test    rdi, rdi
0x18006f7d0  jz      short loc_18006F7E7
0x18006f7d2  mov     rdx, rdi; h
0x18006f7d5  mov     rcx, rbx; hdc
0x18006f7d8  call    cs:__imp_SelectObject
0x18006f7de  mov     rcx, rax; ho
0x18006f7e1  call    cs:__imp_DeleteObject
0x18006f7e7  xor     eax, eax
0x18006f7e9  mov     rcx, [rbp+57h+var_38]
0x18006f7ed  xor     rcx, rsp; StackCookie
0x18006f7f0  call    __security_check_cookie
0x18006f7f5  mov     rbx, [rsp+110h+arg_18]
0x18006f7fd  add     rsp, 0E0h
0x18006f804  pop     r15
0x18006f806  pop     r14
0x18006f808  pop     r13
0x18006f80a  pop     r12
0x18006f80c  pop     rdi
0x18006f80d  pop     rsi
0x18006f80e  pop     rbp
0x18006f80f  retn
```
