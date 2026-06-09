# CIndex::ResizeWindow(void)

- ea: `0x18003d420`
- end: `0x18003d682`
- name: `?ResizeWindow@CIndex@@UEAAXXZ`
- size: `610`
- prototype: `void __fastcall(CIndex *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800128a8`
- `0x18003b8a8`
- `0x180066c20`
- `0x180066f80`
- `0x1800673f0`
- `0x1800674e0`
- `0x180067798`
- `0x180075c90`

## import_xrefs

- `USER32!MoveWindow` at `0x18003d515`
- `USER32!MoveWindow` at `0x18003d5a5`
- `USER32!MoveWindow` at `0x18003d61a`
- `USER32!MoveWindow` at `0x18003d658`
- `USER32!MoveWindow` at `0x18003d515`
- `USER32!MoveWindow` at `0x18003d5a5`
- `USER32!MoveWindow` at `0x18003d61a`
- `USER32!MoveWindow` at `0x18003d658`
- `USER32!CopyRect` at `0x18003d493`
- `USER32!CopyRect` at `0x18003d4a8`
- `USER32!CopyRect` at `0x18003d52a`
- `USER32!CopyRect` at `0x18003d5ba`
- `USER32!CopyRect` at `0x18003d493`
- `USER32!CopyRect` at `0x18003d4a8`
- `USER32!CopyRect` at `0x18003d52a`
- `USER32!CopyRect` at `0x18003d5ba`
- `USER32!GetSystemMetrics` at `0x18003d47c`
- `USER32!GetSystemMetrics` at `0x18003d567`
- `USER32!GetSystemMetrics` at `0x18003d47c`
- `USER32!GetSystemMetrics` at `0x18003d567`

## pseudocode

```c
void __fastcall CIndex::ResizeWindow(CIndex *this)
{
  int v1; // r9d
  int v3; // r8d
  HWND v4; // rdx
  LONG left; // edi
  LONG right; // esi
  const WCHAR *StringResourceW; // rbx
  CResourceCache *v8; // rcx
  HFONT UIFont; // rax
  unsigned int StaticDimensionsW; // eax
  HWND v11; // rcx
  LONG v12; // edi
  HFONT ContentFont; // rax
  int SystemMetrics; // eax
  const WCHAR *v15; // rbx
  CResourceCache *v16; // rcx
  HFONT v17; // rax
  unsigned int ButtonDimensionsW; // eax
  HWND v19; // rcx
  struct tagRECT rcDst; // [rsp+30h] [rbp-19h] BYREF
  struct tagRECT v21; // [rsp+40h] [rbp-9h] BYREF
  struct tagRECT v22; // [rsp+50h] [rbp+7h] BYREF
  RECT rcSrc; // [rsp+60h] [rbp+17h] BYREF
  struct tagRECT v24; // [rsp+70h] [rbp+27h] BYREF

  v1 = *((_DWORD *)this + 120);
  v3 = *((_DWORD *)this + 117);
  v4 = (HWND)*((_QWORD *)this + 62);
  rcSrc = 0;
  rcDst = 0;
  GetParentSize(&rcSrc, v4, v3, v1);
  rcSrc.top += 2 * GetSystemMetrics(33);
  CopyRect(&rcDst, &rcSrc);
  v22 = 0;
  CopyRect(&v22, &rcDst);
  left = rcDst.left;
  right = rcDst.right;
  StringResourceW = GetStringResourceW(0x425u);
  UIFont = CResourceCache::GetUIFont(v8);
  StaticDimensionsW = GetStaticDimensionsW(*((HWND *)this + 57), UIFont, StringResourceW, right - left);
  v11 = (HWND)*((_QWORD *)this + 57);
  v22.bottom = HIWORD(StaticDimensionsW) + rcDst.top;
  MoveWindow(v11, v22.left, v22.top, v22.right - v22.left, v22.bottom - v22.top + 20, 1);
  v21 = 0;
  CopyRect(&v21, &rcDst);
  LODWORD(StringResourceW) = v21.left;
  v12 = v21.right;
  v21.top = v22.bottom + 10;
  ContentFont = CIndex::GetContentFont(this);
  LODWORD(StringResourceW) = GetStaticDimensions(
                               *((HWND *)this + 54),
                               ContentFont,
                               "Test",
                               v12 - (_DWORD)StringResourceW);
  SystemMetrics = GetSystemMetrics(33);
  LODWORD(StringResourceW) = (unsigned int)StringResourceW >> 16;
  v21.bottom = v21.top + (_DWORD)StringResourceW + 2 * SystemMetrics;
  MoveWindow(
    *((HWND *)this + 54),
    v21.left,
    v21.top + 10,
    v21.right - v21.left,
    (_DWORD)StringResourceW + 2 * SystemMetrics + 15,
    1);
  v24 = 0;
  CopyRect(&v24, &rcDst);
  v15 = GetStringResourceW(0x1020u);
  v17 = CResourceCache::GetUIFont(v16);
  ButtonDimensionsW = GetButtonDimensionsW(*((HWND *)this + 56), v17, v15);
  v24.bottom = rcSrc.bottom;
  v24.top = rcSrc.bottom - 24;
  MoveWindow(
    *((HWND *)this + 56),
    v24.right - (unsigned __int16)ButtonDimensionsW - 30,
    rcSrc.bottom - 29,
    (unsigned __int16)ButtonDimensionsW + 25,
    HIWORD(ButtonDimensionsW) + 15,
    1);
  v19 = (HWND)*((_QWORD *)this + 55);
  rcDst.bottom = v24.top - 8;
  rcDst.top = v21.bottom + 8;
  MoveWindow(v19, rcDst.left, v21.bottom + 28, rcDst.right - rcDst.left, v24.top - 8 - (v21.bottom + 8) - 20, 1);
}

```

## disassembly

```asm
0x18003d420  mov     [rsp-8+arg_8], rbx
0x18003d425  mov     [rsp-8+arg_10], rsi
0x18003d42a  push    rbp
0x18003d42b  push    rdi
0x18003d42c  push    r14
0x18003d42e  lea     rbp, [rsp-47h]
0x18003d433  sub     rsp, 90h
0x18003d43a  mov     rax, cs:__security_cookie
0x18003d441  xor     rax, rsp
0x18003d444  mov     [rbp+57h+var_20], rax
0x18003d448  mov     r9d, [rcx+1E0h]; int
0x18003d44f  mov     r14, rcx
0x18003d452  mov     r8d, [rcx+1D4h]; int
0x18003d459  xorps   xmm0, xmm0
0x18003d45c  mov     rdx, [rcx+1F0h]; hWnd
0x18003d463  xorps   xmm1, xmm1
0x18003d466  lea     rcx, [rbp+57h+rcSrc]; lprc
0x18003d46a  movups  xmmword ptr [rbp+57h+rcSrc.left], xmm0
0x18003d46e  movups  xmmword ptr [rbp+57h+rcDst.left], xmm1
0x18003d472  call    ?GetParentSize@@YAPEAUHWND__@@PEAUtagRECT@@PEAU1@HH@Z; GetParentSize(tagRECT *,HWND__ *,int,int)
0x18003d477  mov     ecx, 21h ; '!'; nIndex
0x18003d47c  call    cs:__imp_GetSystemMetrics
0x18003d482  mov     ecx, [rbp+57h+rcSrc.top]
0x18003d485  lea     rdx, [rbp+57h+rcSrc]; lprcSrc
0x18003d489  lea     eax, [rcx+rax*2]
0x18003d48c  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x18003d490  mov     [rbp+57h+rcSrc.top], eax
0x18003d493  call    cs:__imp_CopyRect
0x18003d499  xorps   xmm0, xmm0
0x18003d49c  lea     rdx, [rbp+57h+rcDst]; lprcSrc
0x18003d4a0  lea     rcx, [rbp+57h+var_50]; lprcDst
0x18003d4a4  movups  xmmword ptr [rbp+57h+var_50.left], xmm0
0x18003d4a8  call    cs:__imp_CopyRect
0x18003d4ae  mov     edi, [rbp+57h+rcDst.left]
0x18003d4b1  mov     ecx, 425h; uID
0x18003d4b6  mov     esi, [rbp+57h+rcDst.right]
0x18003d4b9  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18003d4be  mov     rbx, rax
0x18003d4c1  call    ?GetUIFont@CResourceCache@@QEAAPEAUHFONT__@@XZ; CResourceCache::GetUIFont(void)
0x18003d4c6  mov     rcx, [r14+1C8h]; hWnd
0x18003d4cd  sub     esi, edi
0x18003d4cf  mov     r9d, esi; int
0x18003d4d2  mov     r8, rbx; lpString
0x18003d4d5  mov     rdx, rax; h
0x18003d4d8  call    ?GetStaticDimensionsW@@YAKPEAUHWND__@@PEAUHFONT__@@PEBGH@Z; GetStaticDimensionsW(HWND__ *,HFONT__ *,ushort const *,int)
0x18003d4dd  mov     r10d, [rbp+57h+rcDst.top]
0x18003d4e1  mov     esi, 1
0x18003d4e6  mov     r8d, [rbp+57h+var_50.top]; Y
0x18003d4ea  mov     r9d, [rbp+57h+var_50.right]
0x18003d4ee  mov     edx, [rbp+57h+var_50.left]; X
0x18003d4f1  sub     r9d, edx; nWidth
0x18003d4f4  mov     rcx, [r14+1C8h]; hWnd
0x18003d4fb  shr     eax, 10h
0x18003d4fe  add     r10d, eax
0x18003d501  mov     [rsp+0A0h+bRepaint], esi; bRepaint
0x18003d505  mov     [rbp+57h+var_50.bottom], r10d
0x18003d509  sub     r10d, r8d
0x18003d50c  add     r10d, 14h
0x18003d510  mov     [rsp+0A0h+nHeight], r10d; nHeight
0x18003d515  call    cs:__imp_MoveWindow
0x18003d51b  xorps   xmm0, xmm0
0x18003d51e  lea     rdx, [rbp+57h+rcDst]; lprcSrc
0x18003d522  lea     rcx, [rbp+57h+var_60]; lprcDst
0x18003d526  movups  xmmword ptr [rbp+57h+var_60.left], xmm0
0x18003d52a  call    cs:__imp_CopyRect
0x18003d530  mov     eax, [rbp+57h+var_50.bottom]
0x18003d533  mov     rcx, r14; this
0x18003d536  mov     ebx, [rbp+57h+var_60.left]
0x18003d539  add     eax, 0Ah
0x18003d53c  mov     edi, [rbp+57h+var_60.right]
0x18003d53f  mov     [rbp+57h+var_60.top], eax
0x18003d542  call    ?GetContentFont@CIndex@@QEAAPEAUHFONT__@@XZ; CIndex::GetContentFont(void)
0x18003d547  mov     rcx, [r14+1B0h]; hWnd
0x18003d54e  lea     r8, aTest_0; "Test"
0x18003d555  sub     edi, ebx
0x18003d557  mov     rdx, rax; h
0x18003d55a  mov     r9d, edi; int
0x18003d55d  call    ?GetStaticDimensions@@YAKPEAUHWND__@@PEAUHFONT__@@PEBDH@Z; GetStaticDimensions(HWND__ *,HFONT__ *,char const *,int)
0x18003d562  lea     ecx, [rsi+20h]; nIndex
0x18003d565  mov     ebx, eax
0x18003d567  call    cs:__imp_GetSystemMetrics
0x18003d56d  mov     r8d, [rbp+57h+var_60.top]
0x18003d571  mov     r9d, [rbp+57h+var_60.right]
0x18003d575  mov     edx, [rbp+57h+var_60.left]; X
0x18003d578  shr     ebx, 10h
0x18003d57b  lea     ecx, [r8+rbx]
0x18003d57f  lea     r10d, [rcx+rax*2]
0x18003d583  mov     [rbp+57h+var_60.bottom], r10d
0x18003d587  sub     r10d, r8d
0x18003d58a  add     r10d, 0Fh
0x18003d58e  sub     r9d, edx; nWidth
0x18003d591  mov     rcx, [r14+1B0h]; hWnd
0x18003d598  add     r8d, 0Ah; Y
0x18003d59c  mov     [rsp+0A0h+bRepaint], esi; bRepaint
0x18003d5a0  mov     [rsp+0A0h+nHeight], r10d; nHeight
0x18003d5a5  call    cs:__imp_MoveWindow
0x18003d5ab  xorps   xmm0, xmm0
0x18003d5ae  lea     rdx, [rbp+57h+rcDst]; lprcSrc
0x18003d5b2  lea     rcx, [rbp+57h+var_30]; lprcDst
0x18003d5b6  movups  xmmword ptr [rbp+57h+var_30.left], xmm0
0x18003d5ba  call    cs:__imp_CopyRect
0x18003d5c0  mov     ecx, 1020h; uID
0x18003d5c5  call    ?GetStringResourceW@@YAPEBGH@Z; GetStringResourceW(int)
0x18003d5ca  mov     rbx, rax
0x18003d5cd  call    ?GetUIFont@CResourceCache@@QEAAPEAUHFONT__@@XZ; CResourceCache::GetUIFont(void)
0x18003d5d2  mov     rcx, [r14+1C0h]; hWnd
0x18003d5d9  mov     r8, rbx; lpString
0x18003d5dc  mov     rdx, rax; h
0x18003d5df  call    ?GetButtonDimensionsW@@YAKPEAUHWND__@@PEAUHFONT__@@PEBG@Z; GetButtonDimensionsW(HWND__ *,HFONT__ *,ushort const *)
0x18003d5e4  mov     ecx, [rbp+57h+rcSrc.bottom]
0x18003d5e7  mov     edx, [rbp+57h+var_30.right]
0x18003d5ea  mov     [rbp+57h+var_30.bottom], ecx
0x18003d5ed  mov     [rsp+0A0h+bRepaint], esi; bRepaint
0x18003d5f1  lea     r8d, [rcx-18h]
0x18003d5f5  movzx   ecx, ax
0x18003d5f8  sub     edx, ecx
0x18003d5fa  shr     eax, 10h
0x18003d5fd  mov     [rbp+57h+var_30.top], r8d
0x18003d601  add     eax, 0Fh
0x18003d604  add     r8d, 0FFFFFFFBh; Y
0x18003d608  mov     [rsp+0A0h+nHeight], eax; nHeight
0x18003d60c  lea     r9d, [rcx+19h]; nWidth
0x18003d610  sub     edx, 1Eh; X
0x18003d613  mov     rcx, [r14+1C0h]; hWnd
0x18003d61a  call    cs:__imp_MoveWindow
0x18003d620  mov     eax, [rbp+57h+var_30.top]
0x18003d623  mov     r8d, [rbp+57h+var_60.bottom]
0x18003d627  add     eax, 0FFFFFFF8h
0x18003d62a  mov     r9d, [rbp+57h+rcDst.right]
0x18003d62e  add     r8d, 8
0x18003d632  mov     edx, [rbp+57h+rcDst.left]; X
0x18003d635  sub     r9d, edx; nWidth
0x18003d638  mov     rcx, [r14+1B8h]; hWnd
0x18003d63f  mov     [rbp+57h+rcDst.bottom], eax
0x18003d642  sub     eax, r8d
0x18003d645  sub     eax, 14h
0x18003d648  mov     [rbp+57h+rcDst.top], r8d
0x18003d64c  add     r8d, 14h; Y
0x18003d650  mov     [rsp+0A0h+bRepaint], esi; bRepaint
0x18003d654  mov     [rsp+0A0h+nHeight], eax; nHeight
0x18003d658  call    cs:__imp_MoveWindow
0x18003d65e  mov     rcx, [rbp+57h+var_20]
0x18003d662  xor     rcx, rsp; StackCookie
0x18003d665  call    __security_check_cookie
0x18003d66a  lea     r11, [rsp+0A0h+var_10]
0x18003d672  mov     rbx, [r11+28h]
0x18003d676  mov     rsi, [r11+30h]
0x18003d67a  mov     rsp, r11
0x18003d67d  pop     r14
0x18003d67f  pop     rdi
0x18003d680  pop     rbp
0x18003d681  retn
```
