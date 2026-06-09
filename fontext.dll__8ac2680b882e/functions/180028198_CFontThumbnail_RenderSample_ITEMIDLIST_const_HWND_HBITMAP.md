# CFontThumbnail::_RenderSample(_ITEMIDLIST const *,HWND__ *,HBITMAP__ * *)

- ea: `0x180028198`
- end: `0x1800283a0`
- name: `?_RenderSample@CFontThumbnail@@AEAAJPEFBU_ITEMIDLIST@@PEAUHWND__@@PEAPEAUHBITMAP__@@@Z`
- size: `520`
- prototype: `__int64 __fastcall(CFontThumbnail *__hidden this, const struct _ITEMIDLIST *, HWND hWnd, HBITMAP *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026dd0`

## callees

- `0x18001c0d0`
- `0x18001c0fc`
- `0x180022810`
- `0x180027070`
- `0x180027140`
- `0x180028198`
- `0x180031070`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800282f0`
- `GDI32!DeleteObject` at `0x1800282f0`
- `GDI32!CreateCompatibleDC` at `0x180028211`
- `GDI32!CreateCompatibleDC` at `0x180028211`
- `GDI32!DeleteDC` at `0x18002830a`
- `GDI32!DeleteDC` at `0x18002830a`
- `GDI32!SetTextColor` at `0x1800282a9`
- `GDI32!SetTextColor` at `0x1800282a9`
- `GDI32!SelectObject` at `0x180028283`
- `GDI32!SelectObject` at `0x1800282fd`
- `GDI32!SelectObject` at `0x180028283`
- `GDI32!SelectObject` at `0x1800282fd`
- `GDI32!CreateDIBSection` at `0x18002826b`
- `GDI32!CreateDIBSection` at `0x18002826b`
- `GDI32!SetBkMode` at `0x1800282b7`
- `GDI32!SetBkMode` at `0x1800282b7`
- `USER32!ReleaseDC` at `0x180028316`
- `USER32!ReleaseDC` at `0x180028316`
- `USER32!GetDC` at `0x1800281dc`
- `USER32!GetDC` at `0x1800281dc`

## pseudocode

```c
__int64 __fastcall CFontThumbnail::_RenderSample(CFontThumbnail *this, struct _ITEMIDLIST *a2, HWND hWnd, HBITMAP *a4)
{
  HWND v4; // rbx
  int j; // esi
  HDC DC; // r13
  int v9; // ecx
  int v10; // eax
  bool v11; // zf
  HDC CompatibleDC; // r14
  LONG v13; // eax
  HBITMAP v14; // rax
  HBITMAP v15; // r12
  unsigned int ActivationStatus; // eax
  COLORREF v17; // edx
  unsigned __int64 v18; // rdx
  int v19; // ebx
  _BYTE *v20; // r15
  __int64 i; // rcx
  int v23; // eax
  __int64 v24; // r8
  void *ppvBits; // [rsp+30h] [rbp-49h] BYREF
  struct _ITEMIDLIST *v26; // [rsp+38h] [rbp-41h]
  HBITMAP *v27; // [rsp+40h] [rbp-39h]
  HGDIOBJ h; // [rsp+48h] [rbp-31h]
  HWND v29; // [rsp+50h] [rbp-29h]
  BITMAPINFO pbmi; // [rsp+58h] [rbp-21h] BYREF

  v4 = hWnd;
  v27 = a4;
  v29 = hWnd;
  v26 = a2;
  j = -2147467259;
  DC = GetDC(hWnd);
  if ( DC )
  {
    v9 = 256;
    v10 = 256;
    if ( *((_DWORD *)this + 11) )
      v10 = *((_DWORD *)this + 11);
    v11 = *((_DWORD *)this + 10) == 0;
    *((_DWORD *)this + 11) = v10;
    if ( !v11 )
      v9 = *((_DWORD *)this + 10);
    *((_DWORD *)this + 10) = v9;
    CompatibleDC = CreateCompatibleDC(DC);
    if ( !CompatibleDC )
      goto LABEL_16;
    v13 = *((_DWORD *)this + 10);
    memset(&pbmi.bmiHeader.biWidth, 0, 40);
    pbmi.bmiHeader.biWidth = v13;
    pbmi.bmiHeader.biHeight = *((_DWORD *)this + 11);
    ppvBits = 0;
    pbmi.bmiHeader.biSize = 40;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    v14 = CreateDIBSection(DC, &pbmi, 0, &ppvBits, 0, 0);
    v15 = v14;
    if ( !v14 )
    {
LABEL_15:
      DeleteDC(CompatibleDC);
LABEL_16:
      ReleaseDC(v4, DC);
      return (unsigned int)j;
    }
    h = SelectObject(CompatibleDC, v14);
    ActivationStatus = FID_GetActivationStatus(a2);
    v17 = 8421504;
    if ( ActivationStatus != 1 )
      v17 = 0;
    SetTextColor(CompatibleDC, v17);
    SetBkMode(CompatibleDC, 1);
    j = CFontThumbnail::_DrawBackgroundIcon(this, CompatibleDC, a2);
    if ( j >= 0 )
    {
      v19 = *((_DWORD *)this + 10) * *((_DWORD *)this + 11);
      v20 = DirectUI::HAllocAndZero((DirectUI *)v19, v18);
      if ( v20 )
      {
        for ( i = 0; (int)i < v19; i = (unsigned int)(i + 1) )
          v20[i] = *((_BYTE *)ppvBits + 4 * i + 3);
        v23 = CFontThumbnail::_DrawSampleText(this, v26, CompatibleDC);
        v24 = 0;
        for ( j = v23; (int)v24 < v19; v24 = (unsigned int)(v24 + 1) )
          *((_BYTE *)ppvBits + 4 * v24 + 3) = v20[v24];
        operator delete(v20);
        if ( j >= 0 )
        {
          *v27 = v15;
          goto LABEL_14;
        }
      }
      else
      {
        j = -2147467259;
      }
    }
    DeleteObject(v15);
LABEL_14:
    SelectObject(CompatibleDC, h);
    v4 = v29;
    goto LABEL_15;
  }
  return (unsigned int)j;
}

```

## disassembly

```asm
0x180028198  push    rbp
0x18002819a  push    rbx
0x18002819b  push    rsi
0x18002819c  push    rdi
0x18002819d  push    r12
0x18002819f  push    r13
0x1800281a1  push    r14
0x1800281a3  push    r15
0x1800281a5  lea     rbp, [rsp-1Fh]
0x1800281aa  sub     rsp, 98h
0x1800281b1  mov     rax, cs:__security_cookie
0x1800281b8  xor     rax, rsp
0x1800281bb  mov     [rbp+57h+var_48], rax
0x1800281bf  mov     rbx, r8
0x1800281c2  mov     [rbp+57h+var_90], r9
0x1800281c6  mov     rdi, rcx
0x1800281c9  mov     [rbp+57h+var_80], rbx
0x1800281cd  mov     rcx, r8; hWnd
0x1800281d0  mov     [rbp+57h+var_98], rdx
0x1800281d4  mov     r15, rdx
0x1800281d7  mov     esi, 80004005h
0x1800281dc  call    cs:__imp_GetDC
0x1800281e2  xor     r12d, r12d
0x1800281e5  mov     r13, rax
0x1800281e8  test    rax, rax
0x1800281eb  jz      loc_18002831C
0x1800281f1  cmp     [rdi+2Ch], r12d
0x1800281f5  mov     ecx, 100h
0x1800281fa  mov     eax, ecx
0x1800281fc  cmovnz  eax, [rdi+2Ch]
0x180028200  cmp     [rdi+28h], r12d
0x180028204  mov     [rdi+2Ch], eax
0x180028207  cmovnz  ecx, [rdi+28h]
0x18002820b  mov     [rdi+28h], ecx
0x18002820e  mov     rcx, r13; hdc
0x180028211  call    cs:__imp_CreateCompatibleDC
0x180028217  mov     r14, rax
0x18002821a  test    rax, rax
0x18002821d  jz      loc_180028310
0x180028223  xor     eax, eax
0x180028225  mov     [rsp+0D0h+offset], r12d; offset
0x18002822a  xorps   xmm0, xmm0
0x18002822d  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rax
0x180028231  mov     eax, [rdi+28h]
0x180028234  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x180028238  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biWidth], xmm0
0x18002823c  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x18002823f  lea     rdx, [rbp+57h+pbmi]; pbmi
0x180028243  mov     eax, [rdi+2Ch]
0x180028246  xor     r8d, r8d; usage
0x180028249  mov     rcx, r13; hdc
0x18002824c  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x18002824f  mov     [rbp+57h+ppvBits], r12
0x180028253  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x180028257  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x18002825e  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x180028266  mov     [rsp+0D0h+hSection], r12; hSection
0x18002826b  call    cs:__imp_CreateDIBSection
0x180028271  mov     r12, rax
0x180028274  test    rax, rax
0x180028277  jz      loc_180028307
0x18002827d  mov     rdx, rax; h
0x180028280  mov     rcx, r14; hdc
0x180028283  call    cs:__imp_SelectObject
0x180028289  mov     rcx, r15; struct _ITEMIDLIST *
0x18002828c  mov     [rbp+57h+h], rax
0x180028290  call    ?FID_GetActivationStatus@@YAKPEFBU_ITEMIDLIST@@@Z; FID_GetActivationStatus(_ITEMIDLIST const *)
0x180028295  mov     r9d, eax
0x180028298  mov     edx, 808080h
0x18002829d  xor     eax, eax
0x18002829f  mov     rcx, r14; hdc
0x1800282a2  cmp     r9d, 1
0x1800282a6  cmovnz  edx, eax; color
0x1800282a9  call    cs:__imp_SetTextColor
0x1800282af  mov     edx, 1; mode
0x1800282b4  mov     rcx, r14; hdc
0x1800282b7  call    cs:__imp_SetBkMode
0x1800282bd  mov     r8, r15; struct _ITEMIDLIST *
0x1800282c0  mov     rdx, r14; HDC
0x1800282c3  mov     rcx, rdi; this
0x1800282c6  call    ?_DrawBackgroundIcon@CFontThumbnail@@AEAAJPEAUHDC__@@PEFBU_ITEMIDLIST@@@Z; CFontThumbnail::_DrawBackgroundIcon(HDC__ *,_ITEMIDLIST const *)
0x1800282cb  mov     esi, eax
0x1800282cd  test    eax, eax
0x1800282cf  js      short loc_1800282ED
0x1800282d1  mov     ebx, [rdi+2Ch]
0x1800282d4  imul    ebx, [rdi+28h]
0x1800282d8  movsxd  rcx, ebx; this
0x1800282db  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x1800282e0  mov     r15, rax
0x1800282e3  test    rax, rax
0x1800282e6  jnz     short loc_18002833E
0x1800282e8  mov     esi, 80004005h
0x1800282ed  mov     rcx, r12; ho
0x1800282f0  call    cs:__imp_DeleteObject
0x1800282f6  mov     rdx, [rbp+57h+h]; h
0x1800282fa  mov     rcx, r14; hdc
0x1800282fd  call    cs:__imp_SelectObject
0x180028303  mov     rbx, [rbp+57h+var_80]
0x180028307  mov     rcx, r14; hdc
0x18002830a  call    cs:__imp_DeleteDC
0x180028310  mov     rdx, r13; hDC
0x180028313  mov     rcx, rbx; hWnd
0x180028316  call    cs:__imp_ReleaseDC
0x18002831c  mov     eax, esi
0x18002831e  mov     rcx, [rbp+57h+var_48]
0x180028322  xor     rcx, rsp; StackCookie
0x180028325  call    __security_check_cookie
0x18002832a  add     rsp, 98h
0x180028331  pop     r15
0x180028333  pop     r14
0x180028335  pop     r13
0x180028337  pop     r12
0x180028339  pop     rdi
0x18002833a  pop     rsi
0x18002833b  pop     rbx
0x18002833c  pop     rbp
0x18002833d  retn
0x18002833e  xor     ecx, ecx
0x180028340  test    ebx, ebx
0x180028342  jle     short loc_180028357
0x180028344  mov     rax, [rbp+57h+ppvBits]
0x180028348  mov     r8b, [rax+rcx*4+3]
0x18002834d  mov     [r15+rcx], r8b
0x180028351  inc     ecx
0x180028353  cmp     ecx, ebx
0x180028355  jl      short loc_180028344
0x180028357  mov     rdx, [rbp+57h+var_98]; struct _ITEMIDLIST *
0x18002835b  mov     r8, r14; hdc
0x18002835e  mov     rcx, rdi; this
0x180028361  call    ?_DrawSampleText@CFontThumbnail@@AEAAJPEFBU_ITEMIDLIST@@PEAUHDC__@@@Z; CFontThumbnail::_DrawSampleText(_ITEMIDLIST const *,HDC__ *)
0x180028366  xor     r8d, r8d
0x180028369  mov     esi, eax
0x18002836b  test    ebx, ebx
0x18002836d  jle     short loc_180028384
0x18002836f  mov     cl, [r8+r15]
0x180028373  mov     rax, [rbp+57h+ppvBits]
0x180028377  mov     [rax+r8*4+3], cl
0x18002837c  inc     r8d
0x18002837f  cmp     r8d, ebx
0x180028382  jl      short loc_18002836F
0x180028384  mov     rcx, r15; lpMem
0x180028387  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002838c  test    esi, esi
0x18002838e  js      loc_1800282ED
0x180028394  mov     rax, [rbp+57h+var_90]
0x180028398  mov     [rax], r12
0x18002839b  jmp     loc_1800282F6
```
