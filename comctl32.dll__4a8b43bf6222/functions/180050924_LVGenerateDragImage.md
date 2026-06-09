# LVGenerateDragImage

- ea: `0x180050924`
- end: `0x180050db4`
- name: `LVGenerateDragImage`
- size: `1168`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18005c0a0`

## callees

- `0x1800115f0`
- `0x180042570`
- `0x180050924`
- `0x1800526a8`
- `0x180052cf8`
- `0x18005643c`
- `0x18008ea60`
- `0x180090020`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x180050a32`
- `GDI32!CreateCompatibleDC` at `0x180050a32`
- `GDI32!SelectObject` at `0x180050bac`
- `GDI32!SelectObject` at `0x180050d75`
- `GDI32!SelectObject` at `0x180050bac`
- `GDI32!SelectObject` at `0x180050d75`
- `GDI32!GetDeviceCaps` at `0x180050b44`
- `GDI32!GetDeviceCaps` at `0x180050b54`
- `GDI32!GetDeviceCaps` at `0x180050b44`
- `GDI32!GetDeviceCaps` at `0x180050b54`
- `GDI32!SetLayout` at `0x180050a55`
- `GDI32!SetLayout` at `0x180050a55`
- `GDI32!DeleteDC` at `0x180050d7e`
- `GDI32!DeleteDC` at `0x180050d7e`
- `GDI32!CreateBitmap` at `0x180050b6a`
- `GDI32!CreateBitmap` at `0x180050b6a`
- `GDI32!GetPixel` at `0x180050bd4`
- `GDI32!GetPixel` at `0x180050bd4`
- `USER32!GetClientRect` at `0x1800509a6`
- `USER32!GetClientRect` at `0x1800509a6`
- `USER32!SendMessageW` at `0x1800509f2`
- `USER32!SendMessageW` at `0x1800509f2`
- `USER32!UnionRect` at `0x180050a25`
- `USER32!UnionRect` at `0x180050a25`
- `USER32!IntersectRect` at `0x180050a0f`
- `USER32!IntersectRect` at `0x180050d0c`
- `USER32!IntersectRect` at `0x180050a0f`
- `USER32!IntersectRect` at `0x180050d0c`

## pseudocode

```c
__int64 __fastcall LVGenerateDragImage(__int64 a1, __int64 a2)
{
  int v2; // eax
  bool v3; // zf
  int v6; // ebx
  int NextItem; // eax
  HWND v8; // rcx
  HDC CompatibleDC; // rax
  HDC v10; // r14
  LONG right; // r15d
  int left; // edx
  int v13; // r9d
  int v14; // r10d
  LONG v15; // ecx
  LONG v16; // eax
  int v17; // r8d
  LONG bottom; // esi
  int top; // ecx
  int v20; // r10d
  LONG v21; // r8d
  LONG v22; // eax
  int v23; // r15d
  int v24; // esi
  UINT DeviceCaps; // ebx
  UINT v26; // eax
  HBITMAP Bitmap; // rax
  HBITMAP v28; // rbx
  LONG v29; // eax
  HGDIOBJ v30; // rax
  void *v31; // r13
  int v32; // ecx
  int v33; // eax
  int v34; // r10d
  unsigned int v35; // esi
  __int64 v36; // rcx
  __int64 v37; // rax
  int v38; // r15d
  int v39; // ebx
  int v41; // [rsp+30h] [rbp-D0h] BYREF
  int v42; // [rsp+34h] [rbp-CCh] BYREF
  int v43; // [rsp+38h] [rbp-C8h] BYREF
  int v44; // [rsp+3Ch] [rbp-C4h]
  _QWORD v45[18]; // [rsp+40h] [rbp-C0h] BYREF
  RECT rcSrc1; // [rsp+D0h] [rbp-30h] BYREF
  struct tagRECT rcDst; // [rsp+E0h] [rbp-20h] BYREF
  LPARAM lParam[2]; // [rsp+F0h] [rbp-10h] BYREF
  RECT rect; // [rsp+100h] [rbp+0h] BYREF
  struct tagRECT Rect; // [rsp+110h] [rbp+10h] BYREF
  struct tagRECT v51; // [rsp+120h] [rbp+20h] BYREF

  v2 = *(_DWORD *)(a1 + 184);
  v3 = (*(_DWORD *)(a1 + 16) & 0x1000) == 0;
  v42 = v2;
  v41 = 0;
  rcSrc1 = 0;
  Rect = 0;
  if ( !v3 )
  {
    (*(void (__fastcall **)(_QWORD, int *))(**(_QWORD **)(a1 + 496) + 104LL))(*(_QWORD *)(a1 + 496), &v42);
    v2 = v42;
  }
  if ( !v2 )
    return 0;
  GetClientRect(*(HWND *)a1, &Rect);
  v6 = v42;
  v41 = -1;
  while ( --v6 >= 0 )
  {
    NextItem = ListView_OnGetNextItem(a1, (unsigned int)v41, 2);
    v41 = NextItem;
    if ( NextItem != -1 )
    {
      v8 = *(HWND *)a1;
      *(_OWORD *)lParam = 0;
      LODWORD(lParam[0]) = 3;
      if ( (unsigned int)SendMessageW(v8, 0x100Eu, NextItem, (LPARAM)lParam) )
      {
        rcDst = 0;
        if ( IntersectRect(&rcDst, &Rect, (const RECT *)lParam) )
          UnionRect(&rcSrc1, &rcSrc1, (const RECT *)lParam);
      }
    }
  }
  CompatibleDC = CreateCompatibleDC(0);
  v10 = CompatibleDC;
  if ( !CompatibleDC )
    return 0;
  if ( (*(_DWORD *)(a1 + 32) & 0x400000) != 0 )
    SetLayout(CompatibleDC, 1u);
  right = rcSrc1.right;
  left = rcSrc1.left;
  v13 = 150;
  if ( rcSrc1.right - rcSrc1.left > 300 )
  {
    v14 = *(_DWORD *)(a1 + 620);
    v15 = rcSrc1.left;
    v16 = v14 - 150;
    if ( rcSrc1.left >= v14 - 150 )
    {
      v17 = rcSrc1.left - v14 + 300;
    }
    else
    {
      v17 = 150;
      rcSrc1.left = v14 - 150;
      left = v14 - 150;
    }
    if ( v15 >= v16 )
      v16 = v15;
    if ( rcSrc1.right <= v14 + v17 )
    {
      if ( v16 > v15 )
      {
        left = v16 - v14 - v17 + rcSrc1.right;
        if ( left < v15 )
          left = v15;
        rcSrc1.left = left;
      }
    }
    else
    {
      right = v14 + v17;
      rcSrc1.right = v14 + v17;
    }
  }
  bottom = rcSrc1.bottom;
  top = rcSrc1.top;
  if ( rcSrc1.bottom - rcSrc1.top > 300 )
  {
    v20 = *(_DWORD *)(a1 + 624);
    v21 = rcSrc1.top;
    v22 = v20 - 150;
    if ( rcSrc1.top >= v20 - 150 )
    {
      v13 = rcSrc1.top - v20 + 300;
    }
    else
    {
      top = v20 - 150;
      rcSrc1.top = v20 - 150;
    }
    if ( v21 >= v22 )
      v22 = v21;
    if ( rcSrc1.bottom <= v20 + v13 )
    {
      if ( v22 > v21 )
      {
        top = v22 - v20 - v13 + rcSrc1.bottom;
        if ( top < v21 )
          top = v21;
        rcSrc1.top = top;
      }
    }
    else
    {
      bottom = v20 + v13;
      rcSrc1.bottom = v20 + v13;
    }
  }
  v23 = right - left;
  v24 = bottom - top;
  *(_DWORD *)a2 = v23;
  *(_DWORD *)(a2 + 4) = v24;
  DeviceCaps = GetDeviceCaps(v10, 12);
  v26 = GetDeviceCaps(v10, 14);
  Bitmap = CreateBitmap(v23, v24, v26, DeviceCaps, 0);
  *(_QWORD *)(a2 + 16) = Bitmap;
  v28 = Bitmap;
  if ( !Bitmap )
    return 0;
  memset(v45, 0, sizeof(v45));
  v29 = *(_DWORD *)(a2 + 4);
  rect.right = *(_DWORD *)a2;
  *(_QWORD *)&rect.left = 0;
  rect.bottom = v29;
  v30 = SelectObject(v10, v28);
  *(_DWORD *)(a2 + 24) = 5570815;
  v31 = v30;
  FillRectClr(v10, &rect, 0x5500FFu);
  *(_DWORD *)(a2 + 24) = GetPixel(v10, 0, 0);
  v32 = *(_DWORD *)(a1 + 620);
  if ( (*(_DWORD *)(a1 + 32) & 0x400000) != 0 )
    v33 = rcSrc1.right - v32;
  else
    v33 = v32 - rcSrc1.left;
  *(_DWORD *)(a2 + 8) = v33;
  v34 = -1;
  *(_DWORD *)(a2 + 12) = *(_DWORD *)(a1 + 624) - rcSrc1.top;
  v35 = *(_DWORD *)(a1 + 512);
  v41 = -1;
  v45[2] = 0;
  v45[0] = a1;
  v45[10] = v10;
  v45[4] = 0;
  while ( (--v35 & 0x80000000) == 0 )
  {
    if ( (*(_DWORD *)(a1 + 16) & 0x1000) != 0 )
    {
      v36 = *(_QWORD *)(a1 + 496);
      v41 = v34 + 1;
      (*(void (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v36 + 88LL))(v36, (unsigned int)(v34 + 1), &v41);
      v34 = v41;
    }
    else
    {
      v37 = *(_QWORD *)(a1 + 64);
      v41 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 288) + 8LL) + 8LL * v35);
      v34 = v41;
      if ( (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v37 + 8) + 8LL * v41) + 28LL) & 2) == 0 )
      {
        v34 = -1;
        v41 = -1;
      }
    }
    if ( v34 != -1 )
    {
      v38 = *(_DWORD *)(a1 + 152);
      v43 = -rcSrc1.left;
      v44 = -rcSrc1.top;
      v45[13] = v34;
      *(_DWORD *)(a1 + 152) = v34;
      rcDst = 0;
      v51 = 0;
      ListView_GetRects(a1, v34, 0, 0, &rcDst, 0);
      if ( IntersectRect(&v51, &Rect, &rcDst) )
      {
        v43 += rcDst.left;
        v44 += rcDst.top;
        v39 = *(_DWORD *)(a1 + 96);
        v45[1] = &v43;
        v45[16] = *(_QWORD *)(a1 + 104);
        *(_DWORD *)(a1 + 96) = *(_DWORD *)(a2 + 24);
        LODWORD(v45[3]) = 0;
        ListView_DrawItem(v45);
        *(_DWORD *)(a1 + 96) = v39;
      }
      v34 = v41;
      *(_DWORD *)(a1 + 152) = v38;
    }
  }
  SelectObject(v10, v31);
  DeleteDC(v10);
  return 1;
}

```

## disassembly

```asm
0x180050924  mov     [rsp-8+arg_10], rbx
0x180050929  push    rbp
0x18005092a  push    rsi
0x18005092b  push    rdi
0x18005092c  push    r12
0x18005092e  push    r13
0x180050930  push    r14
0x180050932  push    r15
0x180050934  lea     rbp, [rsp-40h]
0x180050939  sub     rsp, 140h
0x180050940  mov     rax, cs:__security_cookie
0x180050947  xor     rax, rsp
0x18005094a  mov     [rbp+70h+var_40], rax
0x18005094e  mov     eax, [rcx+0B8h]
0x180050954  xor     r13d, r13d
0x180050957  test    dword ptr [rcx+10h], 1000h
0x18005095e  xorps   xmm0, xmm0
0x180050961  mov     r12, rdx
0x180050964  mov     [rsp+170h+var_13C], eax
0x180050968  mov     rdi, rcx
0x18005096b  mov     [rsp+170h+var_140], r13d
0x180050970  movdqu  xmmword ptr [rbp+70h+rcSrc1.left], xmm0
0x180050975  movups  xmmword ptr [rbp+70h+Rect.left], xmm0
0x180050979  jz      short loc_180050997
0x18005097b  mov     rcx, [rcx+1F0h]
0x180050982  lea     rdx, [rsp+170h+var_13C]
0x180050987  mov     rax, [rcx]
0x18005098a  mov     rax, [rax+68h]
0x18005098e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050993  mov     eax, [rsp+170h+var_13C]
0x180050997  test    eax, eax
0x180050999  jz      loc_180050D8B
0x18005099f  mov     rcx, [rdi]; hWnd
0x1800509a2  lea     rdx, [rbp+70h+Rect]; lpRect
0x1800509a6  call    cs:__imp_GetClientRect
0x1800509ac  mov     ebx, [rsp+170h+var_13C]
0x1800509b0  mov     [rsp+170h+var_140], 0FFFFFFFFh
0x1800509b8  jmp     short loc_180050A2B
0x1800509ba  mov     edx, [rsp+170h+var_140]
0x1800509be  mov     r8d, 2
0x1800509c4  mov     rcx, rdi
0x1800509c7  call    ListView_OnGetNextItem
0x1800509cc  mov     [rsp+170h+var_140], eax
0x1800509d0  cmp     eax, 0FFFFFFFFh
0x1800509d3  jz      short loc_180050A2B
0x1800509d5  mov     rcx, [rdi]; hWnd
0x1800509d8  lea     r9, [rbp+70h+lParam]; lParam
0x1800509dc  xorps   xmm0, xmm0
0x1800509df  movsxd  r8, eax; wParam
0x1800509e2  movups  xmmword ptr [rbp+70h+lParam], xmm0
0x1800509e6  mov     edx, 100Eh; Msg
0x1800509eb  mov     dword ptr [rbp+70h+lParam], 3
0x1800509f2  call    cs:__imp_SendMessageW
0x1800509f8  test    eax, eax
0x1800509fa  jz      short loc_180050A2B
0x1800509fc  xorps   xmm0, xmm0
0x1800509ff  lea     r8, [rbp+70h+lParam]; lprcSrc2
0x180050a03  lea     rdx, [rbp+70h+Rect]; lprcSrc1
0x180050a07  lea     rcx, [rbp+70h+rcDst]; lprcDst
0x180050a0b  movups  xmmword ptr [rbp+70h+rcDst.left], xmm0
0x180050a0f  call    cs:__imp_IntersectRect
0x180050a15  test    eax, eax
0x180050a17  jz      short loc_180050A2B
0x180050a19  lea     r8, [rbp+70h+lParam]; lprcSrc2
0x180050a1d  lea     rdx, [rbp+70h+rcSrc1]; lprcSrc1
0x180050a21  lea     rcx, [rbp+70h+rcSrc1]; lprcDst
0x180050a25  call    cs:__imp_UnionRect
0x180050a2b  sub     ebx, 1
0x180050a2e  jns     short loc_1800509BA
0x180050a30  xor     ecx, ecx; hdc
0x180050a32  call    cs:__imp_CreateCompatibleDC
0x180050a38  mov     r14, rax
0x180050a3b  test    rax, rax
0x180050a3e  jz      loc_180050D8B
0x180050a44  test    dword ptr [rdi+20h], 400000h
0x180050a4b  jz      short loc_180050A5B
0x180050a4d  mov     edx, 1; l
0x180050a52  mov     rcx, rax; hdc
0x180050a55  call    cs:__imp_SetLayout
0x180050a5b  mov     r15d, [rbp+70h+rcSrc1.right]
0x180050a5f  mov     ebx, 12Ch
0x180050a64  mov     edx, [rbp+70h+rcSrc1.left]
0x180050a67  mov     eax, r15d
0x180050a6a  sub     eax, edx
0x180050a6c  mov     r9d, 96h
0x180050a72  cmp     eax, ebx
0x180050a74  jle     short loc_180050ACA
0x180050a76  mov     r10d, [rdi+26Ch]
0x180050a7d  mov     ecx, edx
0x180050a7f  lea     eax, [r10-96h]
0x180050a86  cmp     edx, eax
0x180050a88  jge     short loc_180050A94
0x180050a8a  mov     r8d, r9d
0x180050a8d  mov     [rbp+70h+rcSrc1.left], eax
0x180050a90  mov     edx, eax
0x180050a92  jmp     short loc_180050A9D
0x180050a94  mov     r8d, ecx
0x180050a97  sub     r8d, r10d
0x180050a9a  add     r8d, ebx
0x180050a9d  cmp     ecx, eax
0x180050a9f  lea     r11d, [r10+r8]
0x180050aa3  cmovge  eax, ecx
0x180050aa6  cmp     r15d, r11d
0x180050aa9  jle     short loc_180050AB4
0x180050aab  mov     r15d, r11d
0x180050aae  mov     [rbp+70h+rcSrc1.right], r11d
0x180050ab2  jmp     short loc_180050ACA
0x180050ab4  cmp     eax, ecx
0x180050ab6  jle     short loc_180050ACA
0x180050ab8  sub     eax, r10d
0x180050abb  sub     eax, r8d
0x180050abe  lea     edx, [rax+r15]
0x180050ac2  cmp     edx, ecx
0x180050ac4  cmovl   edx, ecx
0x180050ac7  mov     [rbp+70h+rcSrc1.left], edx
0x180050aca  mov     esi, [rbp+70h+rcSrc1.bottom]
0x180050acd  mov     eax, esi
0x180050acf  mov     ecx, [rbp+70h+rcSrc1.top]
0x180050ad2  sub     eax, ecx
0x180050ad4  cmp     eax, ebx
0x180050ad6  jle     short loc_180050B2E
0x180050ad8  mov     r10d, [rdi+270h]
0x180050adf  mov     r8d, ecx
0x180050ae2  lea     eax, [r10-96h]
0x180050ae9  cmp     ecx, eax
0x180050aeb  jge     short loc_180050AF4
0x180050aed  mov     ecx, eax
0x180050aef  mov     [rbp+70h+rcSrc1.top], eax
0x180050af2  jmp     short loc_180050AFD
0x180050af4  mov     r9d, r8d
0x180050af7  sub     r9d, r10d
0x180050afa  add     r9d, ebx
0x180050afd  cmp     r8d, eax
0x180050b00  lea     r11d, [r10+r9]
0x180050b04  cmovge  eax, r8d
0x180050b08  cmp     esi, r11d
0x180050b0b  jle     short loc_180050B16
0x180050b0d  mov     esi, r11d
0x180050b10  mov     [rbp+70h+rcSrc1.bottom], r11d
0x180050b14  jmp     short loc_180050B2E
0x180050b16  cmp     eax, r8d
0x180050b19  jle     short loc_180050B2E
0x180050b1b  sub     eax, r10d
0x180050b1e  sub     eax, r9d
0x180050b21  lea     ecx, [rax+rsi]
0x180050b24  cmp     ecx, r8d
0x180050b27  cmovl   ecx, r8d
0x180050b2b  mov     [rbp+70h+rcSrc1.top], ecx
0x180050b2e  sub     r15d, edx
0x180050b31  sub     esi, ecx
0x180050b33  mov     edx, 0Ch; index
0x180050b38  mov     [r12], r15d
0x180050b3c  mov     rcx, r14; hdc
0x180050b3f  mov     [r12+4], esi
0x180050b44  call    cs:__imp_GetDeviceCaps
0x180050b4a  mov     edx, 0Eh; index
0x180050b4f  mov     rcx, r14; hdc
0x180050b52  mov     ebx, eax
0x180050b54  call    cs:__imp_GetDeviceCaps
0x180050b5a  mov     r9d, ebx; nBitCount
0x180050b5d  mov     [rsp+170h+lpBits], r13; lpBits
0x180050b62  mov     r8d, eax; nPlanes
0x180050b65  mov     edx, esi; nHeight
0x180050b67  mov     ecx, r15d; nWidth
0x180050b6a  call    cs:__imp_CreateBitmap
0x180050b70  mov     [r12+10h], rax
0x180050b75  mov     rbx, rax
0x180050b78  test    rax, rax
0x180050b7b  jz      loc_180050D8B
0x180050b81  xor     edx, edx; Val
0x180050b83  lea     rcx, [rsp+170h+var_130]; void *
0x180050b88  mov     r8d, 90h; Size
0x180050b8e  call    memset
0x180050b93  mov     ecx, [r12]
0x180050b97  mov     rdx, rbx; h
0x180050b9a  mov     eax, [r12+4]
0x180050b9f  mov     [rbp+70h+rect.right], ecx
0x180050ba2  mov     rcx, r14; hdc
0x180050ba5  mov     qword ptr [rbp+70h+rect.left], r13
0x180050ba9  mov     [rbp+70h+rect.bottom], eax
0x180050bac  call    cs:__imp_SelectObject
0x180050bb2  mov     r8d, 5500FFh; color
0x180050bb8  lea     rdx, [rbp+70h+rect]; lprect
0x180050bbc  mov     rcx, r14; hdc
0x180050bbf  mov     [r12+18h], r8d
0x180050bc4  mov     r13, rax
0x180050bc7  call    FillRectClr
0x180050bcc  xor     r8d, r8d; y
0x180050bcf  xor     edx, edx; x
0x180050bd1  mov     rcx, r14; hdc
0x180050bd4  call    cs:__imp_GetPixel
0x180050bda  mov     [r12+18h], eax
0x180050bdf  test    dword ptr [rdi+20h], 400000h
0x180050be6  mov     ecx, [rdi+26Ch]
0x180050bec  jz      short loc_180050BF5
0x180050bee  mov     eax, [rbp+70h+rcSrc1.right]
0x180050bf1  sub     eax, ecx
0x180050bf3  jmp     short loc_180050BFA
0x180050bf5  mov     eax, ecx
0x180050bf7  sub     eax, [rbp+70h+rcSrc1.left]
0x180050bfa  mov     [r12+8], eax
0x180050bff  mov     eax, [rdi+270h]
0x180050c05  sub     eax, [rbp+70h+rcSrc1.top]
0x180050c08  or      r10d, 0FFFFFFFFh
0x180050c0c  mov     [r12+0Ch], eax
0x180050c11  mov     esi, [rdi+200h]
0x180050c17  mov     [rsp+170h+var_140], r10d
0x180050c1c  mov     [rsp+170h+var_120], 0
0x180050c25  mov     [rsp+170h+var_130], rdi
0x180050c2a  mov     [rbp+70h+var_E0], r14
0x180050c2e  mov     [rsp+170h+var_110], 0
0x180050c37  jmp     loc_180050D66
0x180050c3c  test    dword ptr [rdi+10h], 1000h
0x180050c43  jz      short loc_180050C6F
0x180050c45  mov     rcx, [rdi+1F0h]
0x180050c4c  lea     r8, [rsp+170h+var_140]
0x180050c51  inc     r10d
0x180050c54  mov     [rsp+170h+var_140], r10d
0x180050c59  mov     edx, r10d
0x180050c5c  mov     rax, [rcx]
0x180050c5f  mov     rax, [rax+58h]
0x180050c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c68  mov     r10d, [rsp+170h+var_140]
0x180050c6d  jmp     short loc_180050C9E
0x180050c6f  mov     rax, [rdi+120h]
0x180050c76  mov     rax, [rax+8]
0x180050c7a  movsxd  r10, dword ptr [rax+rsi*8]
0x180050c7e  mov     rax, [rdi+40h]
0x180050c82  mov     [rsp+170h+var_140], r10d
0x180050c87  mov     rcx, [rax+8]
0x180050c8b  mov     rax, [rcx+r10*8]
0x180050c8f  test    byte ptr [rax+1Ch], 2
0x180050c93  jnz     short loc_180050C9E
0x180050c95  or      r10d, 0FFFFFFFFh
0x180050c99  mov     [rsp+170h+var_140], r10d
0x180050c9e  cmp     r10d, 0FFFFFFFFh
0x180050ca2  jz      loc_180050D66
0x180050ca8  mov     eax, [rbp+70h+rcSrc1.left]
0x180050cab  xorps   xmm0, xmm0
0x180050cae  mov     r15d, [rdi+98h]
0x180050cb5  neg     eax
0x180050cb7  mov     [rsp+170h+var_138], eax
0x180050cbb  xorps   xmm1, xmm1
0x180050cbe  mov     eax, [rbp+70h+rcSrc1.top]
0x180050cc1  xor     r9d, r9d; int
0x180050cc4  neg     eax
0x180050cc6  mov     [rsp+170h+var_148], 0; LPRECT
0x180050ccf  mov     [rsp+170h+var_134], eax
0x180050cd3  xor     r8d, r8d; int
0x180050cd6  movsxd  rax, r10d
0x180050cd9  mov     edx, r10d; int
0x180050cdc  mov     [rbp+70h+var_C8], rax
0x180050ce0  mov     rcx, rdi; int
0x180050ce3  lea     rax, [rbp+70h+rcDst]
0x180050ce7  mov     [rdi+98h], r10d
0x180050cee  mov     [rsp+170h+lpBits], rax; lprcDst
0x180050cf3  movups  xmmword ptr [rbp+70h+rcDst.left], xmm0
0x180050cf7  movups  xmmword ptr [rbp+70h+var_50.left], xmm1
0x180050cfb  call    ListView_GetRects
0x180050d00  lea     r8, [rbp+70h+rcDst]; lprcSrc2
0x180050d04  lea     rdx, [rbp+70h+Rect]; lprcSrc1
0x180050d08  lea     rcx, [rbp+70h+var_50]; lprcDst
0x180050d0c  call    cs:__imp_IntersectRect
0x180050d12  test    eax, eax
0x180050d14  jz      short loc_180050D5A
0x180050d16  mov     eax, [rbp+70h+rcDst.left]
0x180050d19  lea     rcx, [rsp+170h+var_130]
0x180050d1e  add     [rsp+170h+var_138], eax
0x180050d22  mov     eax, [rbp+70h+rcDst.top]
0x180050d25  add     [rsp+170h+var_134], eax
0x180050d29  lea     rax, [rsp+170h+var_138]
0x180050d2e  mov     ebx, [rdi+60h]
0x180050d31  mov     [rsp+170h+var_128], rax
0x180050d36  mov     eax, [rdi+68h]
0x180050d39  mov     [rbp+70h+var_B0], eax
0x180050d3c  mov     eax, [rdi+6Ch]
0x180050d3f  mov     [rbp+70h+var_AC], eax
0x180050d42  mov     eax, [r12+18h]
0x180050d47  mov     [rdi+60h], eax
0x180050d4a  mov     [rsp+170h+var_118], 0
0x180050d52  call    ListView_DrawItem
0x180050d57  mov     [rdi+60h], ebx
0x180050d5a  mov     r10d, [rsp+170h+var_140]
0x180050d5f  mov     [rdi+98h], r15d
0x180050d66  sub     esi, 1
0x180050d69  jns     loc_180050C3C
0x180050d6f  mov     rdx, r13; h
0x180050d72  mov     rcx, r14; hdc
0x180050d75  call    cs:__imp_SelectObject
0x180050d7b  mov     rcx, r14; hdc
0x180050d7e  call    cs:__imp_DeleteDC
0x180050d84  mov     eax, 1
0x180050d89  jmp     short loc_180050D8D
0x180050d8b  xor     eax, eax
0x180050d8d  mov     rcx, [rbp+70h+var_40]
0x180050d91  xor     rcx, rsp; StackCookie
0x180050d94  call    __security_check_cookie
0x180050d99  mov     rbx, [rsp+170h+arg_10]
0x180050da1  add     rsp, 140h
0x180050da8  pop     r15
  ... truncated ...
```
