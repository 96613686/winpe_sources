# VMR9::CVideoMixer::SetAlphaBitmap(VMR9::_VMR9AlphaBitmap const *)

- ea: `0x1800df7d0`
- end: `0x1800dfe93`
- name: `?SetAlphaBitmap@CVideoMixer@VMR9@@UEAAJPEBU_VMR9AlphaBitmap@2@@Z`
- size: `1731`
- prototype: `int(VMR9::CVideoMixer *__hidden this, const struct _VMR9AlphaBitmap *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18002d864`
- `0x180038498`
- `0x1800384a4`
- `0x1800388a0`
- `0x1800df7d0`
- `0x1800dfe9c`
- `0x1800e1788`
- `0x1800e1838`
- `0x1800e9128`
- `0x18015bb98`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800df83a`
- `KERNEL32!LeaveCriticalSection` at `0x1800df8a9`
- `KERNEL32!LeaveCriticalSection` at `0x1800df83a`
- `KERNEL32!LeaveCriticalSection` at `0x1800df8a9`
- `KERNEL32!EnterCriticalSection` at `0x1800df819`
- `KERNEL32!EnterCriticalSection` at `0x1800df819`
- `GDI32!DeleteObject` at `0x1800dfda9`
- `GDI32!DeleteObject` at `0x18015cfde`
- `GDI32!DeleteObject` at `0x1800dfda9`
- `GDI32!DeleteObject` at `0x18015cfde`
- `GDI32!DeleteDC` at `0x1800dfde8`
- `GDI32!DeleteDC` at `0x18015d024`
- `GDI32!DeleteDC` at `0x1800dfde8`
- `GDI32!DeleteDC` at `0x18015d024`
- `GDI32!CreateCompatibleDC` at `0x1800dfc24`
- `GDI32!CreateCompatibleDC` at `0x1800dfc24`
- `GDI32!SelectObject` at `0x1800dfcd8`
- `GDI32!SelectObject` at `0x1800dfd48`
- `GDI32!SelectObject` at `0x1800dfcd8`
- `GDI32!SelectObject` at `0x1800dfd48`
- `GDI32!BitBlt` at `0x1800dfd26`
- `GDI32!BitBlt` at `0x1800dfd26`
- `GDI32!CreateDIBSection` at `0x1800dfcac`
- `GDI32!CreateDIBSection` at `0x1800dfcac`
- `USER32!IsRectEmpty` at `0x1800dfa3e`
- `USER32!IsRectEmpty` at `0x1800dfa3e`

## pseudocode

```c
__int64 __fastcall VMR9::CVideoMixer::SetAlphaBitmap(VMR9::CVideoMixer *this, struct _VMR9AlphaBitmap *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  const struct _VMR9AlphaBitmap *v5; // rdx
  int v6; // esi
  DWORD dwFlags; // r11d
  unsigned int v9; // edx
  unsigned int v10; // r12d
  int v11; // r13d
  IDirect3DSurface9 *pDDS; // rcx
  int v13; // r9d
  RECT *v14; // rcx
  RECT rSrc; // xmm0
  LONG v16; // edi
  char *v17; // rcx
  unsigned int *v18; // r9
  unsigned int i; // edi
  HDC CompatibleDC; // rax
  HBITMAP v21; // rax
  HGDIOBJ v22; // rdi
  COLORREF clrSrcKey; // edi
  unsigned int *hSection; // [rsp+20h] [rbp-148h]
  unsigned int offset; // [rsp+28h] [rbp-140h]
  HBITMAP ho; // [rsp+58h] [rbp-110h]
  unsigned int v27; // [rsp+60h] [rbp-108h]
  unsigned int *Block; // [rsp+68h] [rbp-100h]
  HDC hdc; // [rsp+70h] [rbp-F8h]
  DWORD dwFilterMode; // [rsp+78h] [rbp-F0h]
  void *ppvBits; // [rsp+88h] [rbp-E0h] BYREF
  HDC hdcSrc; // [rsp+90h] [rbp-D8h] BYREF
  unsigned int v33; // [rsp+98h] [rbp-D0h]
  char *v34; // [rsp+A0h] [rbp-C8h]
  struct _VMR9AlphaBitmap *v35; // [rsp+A8h] [rbp-C0h]
  unsigned int *v36; // [rsp+B0h] [rbp-B8h]
  __int128 v37; // [rsp+B8h] [rbp-B0h] BYREF
  VMR9::CVideoMixer *v38; // [rsp+C8h] [rbp-A0h]
  RECT rc; // [rsp+D0h] [rbp-98h] BYREF
  __int128 v40; // [rsp+E0h] [rbp-88h] BYREF
  struct tagRECT *v41[2]; // [rsp+F0h] [rbp-78h]
  BITMAPINFO pbmi; // [rsp+100h] [rbp-68h] BYREF

  v38 = this;
  v35 = a2;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v6 = VMR9::ValidateAlphaBitmapParam((VMR9 *)a2, v5);
  if ( v6 )
  {
LABEL_2:
    LeaveCriticalSection(v4);
    return (unsigned int)v6;
  }
  dwFlags = a2->dwFlags;
  v9 = 1;
  if ( (a2->dwFlags & 1) == 0 )
  {
    hdcSrc = 0;
    hdc = 0;
    ho = 0;
    v27 = 0;
    v10 = 0;
    Block = 0;
    v11 = 0;
    rc = 0;
    dwFilterMode = *((_DWORD *)this + 1634);
    v40 = 0;
    *(_OWORD *)v41 = 0;
    pDDS = a2->pDDS;
    if ( pDDS )
    {
      v6 = ((__int64 (__fastcall *)(IDirect3DSurface9 *, __int128 *))pDDS->lpVtbl->GetDesc)(pDDS, &v40);
      if ( v6 < 0 )
        goto LABEL_46;
      if ( HIDWORD(v40) != 2 )
        goto LABEL_8;
      v9 = 1;
      if ( (unsigned int)(v40 - 21) > 1 )
        goto LABEL_8;
      if ( (_DWORD)v40 == 21 )
      {
        if ( (a2->dwFlags & 8) != 0 )
          goto LABEL_8;
        v11 = 1;
      }
      else
      {
        v11 = 2;
      }
      dwFlags = a2->dwFlags;
      if ( (a2->dwFlags & 4) != 0 )
      {
        *(_QWORD *)&rc.left = 0;
        *(struct tagRECT **)&rc.right = v41[1];
LABEL_20:
        if ( (dwFlags & 0x20) != 0 )
        {
          if ( (unsigned int)VMR9::ValidateFilterMode((VMR9 *)a2->dwFilterMode, v9) )
            goto LABEL_8;
          dwFilterMode = a2->dwFilterMode;
        }
        if ( !IsRectEmpty(&rc) )
        {
          v16 = rc.right - rc.left;
          v27 = rc.right - rc.left;
          v10 = rc.bottom - rc.top;
          if ( (unsigned int)(rc.right - rc.left) <= *((_DWORD *)this + 56) && v10 <= *((_DWORD *)this + 57) )
          {
            Block = (unsigned int *)operator new[](saturated_mul(v16 * v10, 4u));
            if ( !Block )
              goto LABEL_27;
            if ( ((v11 - 2) & 0xFFFFFFFD) != 0 )
            {
              v37 = 0;
              v6 = ((__int64 (__fastcall *)(IDirect3DSurface9 *, __int128 *, _QWORD, __int64))a2->pDDS->lpVtbl->LockRect)(
                     a2->pDDS,
                     &v37,
                     0,
                     2048);
              if ( v6 >= 0 )
              {
                v17 = (char *)(*((_QWORD *)&v37 + 1) + rc.top * (int)v37 + 4 * rc.left);
                v34 = v17;
                v18 = &Block[v16 * (v10 - 1)];
                v36 = v18;
                LODWORD(ppvBits) = -v16;
                for ( i = 0; ; ++i )
                {
                  v33 = i;
                  if ( i >= v10 )
                    break;
                  memcpy_0(v18, v17, 4LL * v27);
                  v18 = &v36[(int)ppvBits];
                  v36 = v18;
                  v17 = &v34[(int)v37];
                  v34 = v17;
                }
                ((void (__fastcall *)(IDirect3DSurface9 *))a2->pDDS->lpVtbl->UnlockRect)(a2->pDDS);
              }
              goto LABEL_46;
            }
            if ( v11 == 4 )
            {
              hdcSrc = a2->hdc;
            }
            else
            {
              v6 = ((__int64 (__fastcall *)(IDirect3DSurface9 *, HDC *))a2->pDDS->lpVtbl->GetDC)(a2->pDDS, &hdcSrc);
              if ( v6 < 0 )
                goto LABEL_46;
            }
            CompatibleDC = CreateCompatibleDC(0);
            hdc = CompatibleDC;
            if ( CompatibleDC )
            {
              ppvBits = 0;
              memset(&pbmi.bmiHeader.biCompression, 0, 28);
              pbmi.bmiHeader.biSize = 40;
              pbmi.bmiHeader.biWidth = v16;
              pbmi.bmiHeader.biHeight = v10;
              *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
              v21 = CreateDIBSection(CompatibleDC, &pbmi, 0, &ppvBits, 0, 0);
              ho = v21;
              if ( !v21 )
              {
                v6 = -2147024882;
LABEL_47:
                clrSrcKey = -1;
                goto LABEL_48;
              }
              v22 = SelectObject(hdc, v21);
              if ( !BitBlt(hdc, 0, 0, v27, v10, hdcSrc, *((_DWORD *)this + 1640), *((_DWORD *)this + 1641), 0xCC0020u) )
                v6 = -2147467259;
              SelectObject(hdc, v22);
              if ( v6 >= 0 )
              {
                if ( (a2->dwFlags & 8) == 0 )
                {
                  clrSrcKey = -1;
                  LODWORD(hSection) = -1;
                  VMR9::SetAppImageColorKey((VMR9 *)v27, v10, (unsigned int)ppvBits, Block, hSection, offset);
                  v21 = ho;
LABEL_48:
                  if ( v21 )
                    DeleteObject(v21);
                  if ( hdcSrc && v11 == 2 )
                    ((void (__fastcall *)(IDirect3DSurface9 *))a2->pDDS->lpVtbl->ReleaseDC)(a2->pDDS);
                  if ( hdc )
                    DeleteDC(hdc);
                  if ( v6 < 0 )
                  {
                    operator delete(Block);
                  }
                  else
                  {
                    operator delete(*((void **)this + 822));
                    *((_QWORD *)this + 822) = Block;
                    RELEASE<IDDVideoAcceleratorContainer>((char *)this + 6544);
                    if ( (a2->dwFlags & 8) != 0 )
                      clrSrcKey = a2->clrSrcKey;
                    *((_DWORD *)this + 1633) = clrSrcKey;
                    *((RECT *)this + 410) = rc;
                    *((_OWORD *)this + 407) = a2->rDest;
                    *((_DWORD *)this + 1632) = LODWORD(a2->fAlpha);
                    *((_DWORD *)this + 1646) = v27;
                    *((_DWORD *)this + 1647) = v10;
                    *((_DWORD *)this + 1634) = dwFilterMode;
                    *((_DWORD *)this + 1648) = v11;
                  }
                  goto LABEL_2;
                }
                LODWORD(hSection) = a2->clrSrcKey & 0xFFFFFF;
                VMR9::SetAppImageColorKey((VMR9 *)v27, v10, (unsigned int)ppvBits, Block, hSection, offset);
              }
            }
            else
            {
LABEL_27:
              v6 = -2147024882;
            }
LABEL_46:
            v21 = ho;
            goto LABEL_47;
          }
        }
LABEL_8:
        v6 = -2147024809;
        goto LABEL_46;
      }
      if ( !VMR9::ValidRect((VMR9 *)&a2->rSrc, (const struct tagRECT *)LODWORD(v41[1]), SHIDWORD(v41[1]), v13) )
        goto LABEL_8;
      rSrc = *v14;
    }
    else
    {
      v11 = 4;
      rSrc = a2->rSrc;
    }
    rc = rSrc;
    goto LABEL_20;
  }
  RELEASE<IDDVideoAcceleratorContainer>((char *)this + 6544);
  operator delete(*((void **)this + 822));
  *((_QWORD *)this + 822) = 0;
  LeaveCriticalSection(v4);
  return 0;
}

```

## disassembly

```asm
0x1800df7d0  mov     [rsp+arg_10], rbx
0x1800df7d5  mov     [rsp+arg_18], rsi
0x1800df7da  push    rdi
0x1800df7db  push    r12
0x1800df7dd  push    r13
0x1800df7df  push    r14
0x1800df7e1  push    r15
0x1800df7e3  sub     rsp, 140h
0x1800df7ea  mov     rax, cs:__security_cookie
0x1800df7f1  xor     rax, rsp
0x1800df7f4  mov     [rsp+168h+var_38], rax
0x1800df7fc  mov     r15, rdx
0x1800df7ff  mov     r14, rcx
0x1800df802  mov     [rsp+168h+var_A0], rcx
0x1800df80a  mov     [rsp+168h+var_C0], rdx
0x1800df812  lea     rbx, [rcx+8]
0x1800df816  mov     rcx, rbx; lpCriticalSection
0x1800df819  call    cs:__imp_EnterCriticalSection
0x1800df820  nop     dword ptr [rax+rax+00h]
0x1800df825  mov     rcx, r15; this
0x1800df828  call    ?ValidateAlphaBitmapParam@VMR9@@YAJPEBU_VMR9AlphaBitmap@1@@Z; VMR9::ValidateAlphaBitmapParam(VMR9::_VMR9AlphaBitmap const *)
0x1800df82d  mov     esi, eax
0x1800df82f  mov     [rsp+168h+var_118], eax
0x1800df833  test    eax, eax
0x1800df835  jz      short loc_1800DF876
0x1800df837  mov     rcx, rbx; lpCriticalSection
0x1800df83a  call    cs:__imp_LeaveCriticalSection
0x1800df841  nop     dword ptr [rax+rax+00h]
0x1800df846  mov     eax, esi
0x1800df848  mov     rcx, [rsp+168h+var_38]
0x1800df850  xor     rcx, rsp; StackCookie
0x1800df853  call    __security_check_cookie
0x1800df858  lea     r11, [rsp+168h+var_28]
0x1800df860  mov     rbx, [r11+40h]
0x1800df864  mov     rsi, [r11+48h]
0x1800df868  mov     rsp, r11
0x1800df86b  pop     r15
0x1800df86d  pop     r14
0x1800df86f  pop     r13
0x1800df871  pop     r12
0x1800df873  pop     rdi
0x1800df874  retn
0x1800df876  mov     r11d, [r15]
0x1800df879  mov     edx, 1; unsigned int
0x1800df87e  test    dl, r11b
0x1800df881  jz      short loc_1800DF8B9
0x1800df883  lea     rcx, [r14+1990h]
0x1800df88a  call    ??$RELEASE@UIDDVideoAcceleratorContainer@@@@YAXAEAPEAUIDDVideoAcceleratorContainer@@@Z; RELEASE<IDDVideoAcceleratorContainer>(IDDVideoAcceleratorContainer * &)
0x1800df88f  mov     rcx, [r14+19B0h]; Block
0x1800df896  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800df89b  mov     qword ptr [r14+19B0h], 0
0x1800df8a6  mov     rcx, rbx; lpCriticalSection
0x1800df8a9  call    cs:__imp_LeaveCriticalSection
0x1800df8b0  nop     dword ptr [rax+rax+00h]
0x1800df8b5  xor     eax, eax
0x1800df8b7  jmp     short loc_1800DF848
0x1800df8b9  mov     [rsp+168h+hdcSrc], 0
0x1800df8c5  mov     [rsp+168h+hdc], 0
0x1800df8ce  mov     [rsp+168h+ho], 0
0x1800df8d7  xor     eax, eax
0x1800df8d9  mov     dword ptr [rsp+168h+var_108], eax
0x1800df8dd  mov     [rsp+168h+var_EC], eax
0x1800df8e1  xor     r12d, r12d
0x1800df8e4  mov     [rsp+168h+var_E8], r12d
0x1800df8ec  mov     [rsp+168h+Block], rax
0x1800df8f1  xor     r13d, r13d
0x1800df8f4  mov     dword ptr [rsp+168h+var_108+4], r13d
0x1800df8f9  xorps   xmm0, xmm0
0x1800df8fc  movups  xmmword ptr [rsp+168h+rc.left], xmm0
0x1800df904  mov     edi, [r14+1988h]
0x1800df90b  mov     [rsp+168h+var_F0], edi
0x1800df90f  mov     [rsp+168h+var_E4], edi
0x1800df916  movups  [rsp+168h+var_88], xmm0
0x1800df91e  movups  xmmword ptr [rsp+168h+var_78], xmm0
0x1800df926  mov     rcx, [r15+10h]
0x1800df92a  test    rcx, rcx
0x1800df92d  jz      loc_1800DF9F7
0x1800df933  mov     rax, [rcx]
0x1800df936  lea     rdx, [rsp+168h+var_88]
0x1800df93e  mov     rax, [rax+60h]
0x1800df942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df947  mov     esi, eax
0x1800df949  mov     [rsp+168h+var_118], eax
0x1800df94d  test    eax, eax
0x1800df94f  js      loc_1800DFD99
0x1800df955  cmp     dword ptr [rsp+168h+var_88+0Ch], 2
0x1800df95d  jz      short loc_1800DF96D
0x1800df95f  mov     esi, 80070057h
0x1800df964  mov     [rsp+168h+var_118], esi
0x1800df968  jmp     loc_1800DFD99
0x1800df96d  mov     ecx, dword ptr [rsp+168h+var_88]
0x1800df974  lea     eax, [rcx-15h]
0x1800df977  mov     edx, 1
0x1800df97c  cmp     eax, edx
0x1800df97e  ja      short loc_1800DF95F
0x1800df980  cmp     ecx, 15h
0x1800df983  jnz     short loc_1800DF994
0x1800df985  test    byte ptr [r15], 8
0x1800df989  jnz     short loc_1800DF95F
0x1800df98b  mov     r13d, edx
0x1800df98e  mov     dword ptr [rsp+168h+var_108+4], edx
0x1800df992  jmp     short loc_1800DF99F
0x1800df994  mov     r13d, 2
0x1800df99a  mov     dword ptr [rsp+168h+var_108+4], r13d
0x1800df99f  mov     r11d, [r15]
0x1800df9a2  test    r11b, 4
0x1800df9a6  jz      short loc_1800DF9D2
0x1800df9a8  mov     qword ptr [rsp+168h+rc.left], 0
0x1800df9b4  mov     eax, dword ptr [rsp+168h+var_78+8]
0x1800df9bb  mov     [rsp+168h+rc.right], eax
0x1800df9c2  mov     eax, dword ptr [rsp+168h+var_78+0Ch]
0x1800df9c9  mov     [rsp+168h+rc.bottom], eax
0x1800df9d0  jmp     short loc_1800DFA10
0x1800df9d2  lea     rcx, [r15+18h]; this
0x1800df9d6  mov     r8d, dword ptr [rsp+168h+var_78+0Ch]; int
0x1800df9de  mov     edx, dword ptr [rsp+168h+var_78+8]; struct tagRECT *
0x1800df9e5  call    ?ValidRect@VMR9@@YA_NPEBUtagRECT@@HH@Z; VMR9::ValidRect(tagRECT const *,int,int)
0x1800df9ea  test    al, al
0x1800df9ec  jz      loc_1800DF95F
0x1800df9f2  movups  xmm0, xmmword ptr [rcx]
0x1800df9f5  jmp     short loc_1800DFA07
0x1800df9f7  mov     r13d, 4
0x1800df9fd  mov     dword ptr [rsp+168h+var_108+4], r13d
0x1800dfa02  movups  xmm0, xmmword ptr [r15+18h]
0x1800dfa07  movdqu  xmmword ptr [rsp+168h+rc.left], xmm0
0x1800dfa10  test    r11b, 20h
0x1800dfa14  jz      short loc_1800DFA36
0x1800dfa16  mov     ecx, [r15+40h]; this
0x1800dfa1a  call    ?ValidateFilterMode@VMR9@@YAJK@Z; VMR9::ValidateFilterMode(ulong)
0x1800dfa1f  test    eax, eax
0x1800dfa21  jnz     loc_1800DF95F
0x1800dfa27  mov     eax, [r15+40h]
0x1800dfa2b  mov     [rsp+168h+var_F0], eax
0x1800dfa2f  mov     [rsp+168h+var_E4], eax
0x1800dfa36  lea     rcx, [rsp+168h+rc]; lprc
0x1800dfa3e  call    cs:__imp_IsRectEmpty
0x1800dfa45  nop     dword ptr [rax+rax+00h]
0x1800dfa4a  test    eax, eax
0x1800dfa4c  jnz     loc_1800DF95F
0x1800dfa52  mov     edi, [rsp+168h+rc.right]
0x1800dfa59  sub     edi, [rsp+168h+rc.left]
0x1800dfa60  mov     dword ptr [rsp+168h+var_108], edi
0x1800dfa64  mov     [rsp+168h+var_EC], edi
0x1800dfa68  mov     r12d, [rsp+168h+rc.bottom]
0x1800dfa70  sub     r12d, [rsp+168h+rc.top]
0x1800dfa78  mov     [rsp+168h+var_E8], r12d
0x1800dfa80  cmp     edi, [r14+0E0h]
0x1800dfa87  ja      loc_1800DF95F
0x1800dfa8d  cmp     r12d, [r14+0E4h]
0x1800dfa94  ja      loc_1800DF95F
0x1800dfa9a  mov     ecx, r12d
0x1800dfa9d  imul    ecx, edi
0x1800dfaa0  mov     eax, 4
0x1800dfaa5  mul     rcx
0x1800dfaa8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800dfaaf  cmovb   rax, rcx
0x1800dfab3  mov     rcx, rax; unsigned __int64
0x1800dfab6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800dfabb  mov     [rsp+168h+Block], rax
0x1800dfac0  test    rax, rax
0x1800dfac3  jnz     short loc_1800DFACF
0x1800dfac5  mov     esi, 8007000Eh
0x1800dfaca  jmp     loc_1800DF964
0x1800dfacf  lea     eax, [r13-2]
0x1800dfad3  test    eax, 0FFFFFFFDh
0x1800dfad8  jz      loc_1800DFBE8
0x1800dfade  xorps   xmm0, xmm0
0x1800dfae1  movups  [rsp+168h+var_B0], xmm0
0x1800dfae9  mov     rcx, [r15+10h]
0x1800dfaed  mov     rax, [rcx]
0x1800dfaf0  mov     r9d, 800h
0x1800dfaf6  xor     r8d, r8d
0x1800dfaf9  lea     rdx, [rsp+168h+var_B0]
0x1800dfb01  mov     rax, [rax+68h]
0x1800dfb05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfb0a  mov     esi, eax
0x1800dfb0c  mov     [rsp+168h+var_118], eax
0x1800dfb10  test    eax, eax
0x1800dfb12  js      loc_1800DFD99
0x1800dfb18  mov     eax, dword ptr [rsp+168h+var_B0]
0x1800dfb1f  imul    eax, [rsp+168h+rc.top]
0x1800dfb27  movsxd  rdx, eax
0x1800dfb2a  add     rdx, qword ptr [rsp+168h+var_B0+8]
0x1800dfb32  mov     [rsp+168h+var_C8], rdx
0x1800dfb3a  mov     eax, [rsp+168h+rc.left]
0x1800dfb41  shl     eax, 2
0x1800dfb44  movsxd  rcx, eax
0x1800dfb47  add     rcx, rdx
0x1800dfb4a  mov     [rsp+168h+var_C8], rcx
0x1800dfb52  lea     eax, [r12-1]
0x1800dfb57  imul    eax, edi
0x1800dfb5a  mov     r9, [rsp+168h+Block]
0x1800dfb5f  lea     r9, [r9+rax*4]
0x1800dfb63  mov     [rsp+168h+var_B8], r9
0x1800dfb6b  mov     eax, edi
0x1800dfb6d  neg     eax
0x1800dfb6f  mov     dword ptr [rsp+168h+ppvBits], eax
0x1800dfb76  xor     edi, edi
0x1800dfb78  mov     [rsp+168h+var_D0], edi
0x1800dfb7f  cmp     edi, r12d
0x1800dfb82  jnb     short loc_1800DFBD3
0x1800dfb84  mov     r8d, dword ptr [rsp+168h+var_108]
0x1800dfb89  shl     r8, 2; Size
0x1800dfb8d  mov     rdx, rcx; Src
0x1800dfb90  mov     rcx, r9; void *
0x1800dfb93  call    memcpy_0
0x1800dfb98  movsxd  rax, dword ptr [rsp+168h+ppvBits]
0x1800dfba0  mov     r9, [rsp+168h+var_B8]
0x1800dfba8  lea     r9, [r9+rax*4]
0x1800dfbac  mov     [rsp+168h+var_B8], r9
0x1800dfbb4  movsxd  rax, dword ptr [rsp+168h+var_B0]
0x1800dfbbc  mov     rcx, [rsp+168h+var_C8]
0x1800dfbc4  add     rcx, rax
0x1800dfbc7  mov     [rsp+168h+var_C8], rcx
0x1800dfbcf  inc     edi
0x1800dfbd1  jmp     short loc_1800DFB78
0x1800dfbd3  mov     rcx, [r15+10h]
0x1800dfbd7  mov     rax, [rcx]
0x1800dfbda  mov     rax, [rax+70h]
0x1800dfbde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfbe3  jmp     loc_1800DFD99
0x1800dfbe8  cmp     r13d, 4
0x1800dfbec  jnz     short loc_1800DFBFC
0x1800dfbee  mov     rax, [r15+8]
0x1800dfbf2  mov     [rsp+168h+hdcSrc], rax
0x1800dfbfa  jmp     short loc_1800DFC22
0x1800dfbfc  mov     rcx, [r15+10h]
0x1800dfc00  mov     rax, [rcx]
0x1800dfc03  lea     rdx, [rsp+168h+hdcSrc]
0x1800dfc0b  mov     rax, [rax+78h]
0x1800dfc0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfc14  mov     esi, eax
0x1800dfc16  mov     [rsp+168h+var_118], eax
0x1800dfc1a  test    eax, eax
0x1800dfc1c  js      loc_1800DFD99
0x1800dfc22  xor     ecx, ecx; hdc
0x1800dfc24  call    cs:__imp_CreateCompatibleDC
0x1800dfc2b  nop     dword ptr [rax+rax+00h]
0x1800dfc30  mov     [rsp+168h+hdc], rax
0x1800dfc35  test    rax, rax
0x1800dfc38  jz      loc_1800DFAC5
0x1800dfc3e  mov     [rsp+168h+ppvBits], 0
0x1800dfc4a  xorps   xmm0, xmm0
0x1800dfc4d  xor     ecx, ecx
0x1800dfc4f  movups  xmmword ptr [rsp+168h+pbmi.bmiHeader.biSize], xmm0
0x1800dfc57  movups  xmmword ptr [rsp+168h+pbmi.bmiHeader.biCompression], xmm0
0x1800dfc5f  movups  xmmword ptr [rsp+168h+pbmi.bmiHeader.biYPelsPerMeter], xmm0
0x1800dfc67  mov     [rsp+168h+pbmi.bmiHeader.biSize], 28h ; '('
0x1800dfc72  mov     [rsp+168h+pbmi.bmiHeader.biWidth], edi
0x1800dfc79  mov     [rsp+168h+pbmi.bmiHeader.biHeight], r12d
0x1800dfc81  mov     qword ptr [rsp+168h+pbmi.bmiHeader.biPlanes], 200001h
0x1800dfc8d  mov     [rsp+168h+offset], ecx; offset
0x1800dfc91  mov     [rsp+168h+hSection], rcx; hSection
0x1800dfc96  lea     r9, [rsp+168h+ppvBits]; ppvBits
0x1800dfc9e  xor     r8d, r8d; usage
0x1800dfca1  lea     rdx, [rsp+168h+pbmi]; pbmi
0x1800dfca9  mov     rcx, rax; hdc
0x1800dfcac  call    cs:__imp_CreateDIBSection
0x1800dfcb3  nop     dword ptr [rax+rax+00h]
0x1800dfcb8  mov     [rsp+168h+ho], rax
0x1800dfcbd  test    rax, rax
0x1800dfcc0  jnz     short loc_1800DFCD0
0x1800dfcc2  mov     esi, 8007000Eh
0x1800dfcc7  mov     [rsp+168h+var_118], esi
0x1800dfccb  jmp     loc_1800DFD9E
0x1800dfcd0  mov     rdx, rax; h
0x1800dfcd3  mov     rcx, [rsp+168h+hdc]; hdc
0x1800dfcd8  call    cs:__imp_SelectObject
0x1800dfcdf  nop     dword ptr [rax+rax+00h]
0x1800dfce4  mov     rdi, rax
0x1800dfce7  mov     [rsp+168h+rop], 0CC0020h; rop
0x1800dfcef  mov     ecx, [r14+19A4h]
0x1800dfcf6  mov     [rsp+168h+y1], ecx; y1
0x1800dfcfa  mov     ecx, [r14+19A0h]
0x1800dfd01  mov     [rsp+168h+x1], ecx; x1
0x1800dfd05  mov     rcx, [rsp+168h+hdcSrc]
0x1800dfd0d  mov     qword ptr [rsp+168h+offset], rcx; unsigned int
0x1800dfd12  mov     dword ptr [rsp+168h+hSection], r12d; cy
0x1800dfd17  mov     r9d, dword ptr [rsp+168h+var_108]; cx
0x1800dfd1c  xor     r8d, r8d; y
0x1800dfd1f  xor     edx, edx; x
0x1800dfd21  mov     rcx, [rsp+168h+hdc]; hdc
0x1800dfd26  call    cs:__imp_BitBlt
0x1800dfd2d  nop     dword ptr [rax+rax+00h]
0x1800dfd32  mov     ecx, 80004005h
0x1800dfd37  test    eax, eax
0x1800dfd39  cmovz   esi, ecx
0x1800dfd3c  mov     [rsp+168h+var_118], esi
0x1800dfd40  mov     rdx, rdi; h
0x1800dfd43  mov     rcx, [rsp+168h+hdc]; hdc
0x1800dfd48  call    cs:__imp_SelectObject
0x1800dfd4f  nop     dword ptr [rax+rax+00h]
0x1800dfd54  test    esi, esi
0x1800dfd56  js      short loc_1800DFD99
0x1800dfd58  mov     r9, [rsp+168h+Block]; unsigned int *
0x1800dfd5d  mov     r8, [rsp+168h+ppvBits]; unsigned int
0x1800dfd65  mov     edx, r12d; unsigned int
0x1800dfd68  mov     ecx, dword ptr [rsp+168h+var_108]; this
0x1800dfd6c  test    byte ptr [r15], 8
0x1800dfd70  jz      short loc_1800DFD86
  ... truncated ...
```
