# xDrawTransparentBitmap(HDC__ *,HBITMAP__ *,short,short,ulong)

- ea: `0x180511250`
- end: `0x180511936`
- name: `?xDrawTransparentBitmap@@YAXPEAUHDC__@@PEAUHBITMAP__@@FFK@Z`
- size: `1766`
- prototype: `void __fastcall(HDC hdc, HBITMAP h, __int16, __int16, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18050f6cc`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x180511250`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180511411`
- `KERNEL32!GetLastError` at `0x1805114a7`
- `KERNEL32!GetLastError` at `0x180511538`
- `KERNEL32!GetLastError` at `0x1805115c6`
- `KERNEL32!GetLastError` at `0x18051164c`
- `KERNEL32!GetLastError` at `0x1805116d2`
- `KERNEL32!GetLastError` at `0x180511758`
- `KERNEL32!GetLastError` at `0x1805117de`
- `KERNEL32!GetLastError` at `0x180511869`
- `KERNEL32!GetLastError` at `0x180511411`
- `KERNEL32!GetLastError` at `0x1805114a7`
- `KERNEL32!GetLastError` at `0x180511538`
- `KERNEL32!GetLastError` at `0x1805115c6`
- `KERNEL32!GetLastError` at `0x18051164c`
- `KERNEL32!GetLastError` at `0x1805116d2`
- `KERNEL32!GetLastError` at `0x180511758`
- `KERNEL32!GetLastError` at `0x1805117de`
- `KERNEL32!GetLastError` at `0x180511869`
- `GDI32!SetMapMode` at `0x1805113b3`
- `GDI32!SetMapMode` at `0x1805113b3`
- `GDI32!DeleteObject` at `0x1805118aa`
- `GDI32!DeleteObject` at `0x1805118c1`
- `GDI32!DeleteObject` at `0x1805118d8`
- `GDI32!DeleteObject` at `0x1805118ef`
- `GDI32!DeleteObject` at `0x1805118aa`
- `GDI32!DeleteObject` at `0x1805118c1`
- `GDI32!DeleteObject` at `0x1805118d8`
- `GDI32!DeleteObject` at `0x1805118ef`
- `GDI32!DeleteDC` at `0x1805118f8`
- `GDI32!DeleteDC` at `0x180511901`
- `GDI32!DeleteDC` at `0x18051190a`
- `GDI32!DeleteDC` at `0x180511913`
- `GDI32!DeleteDC` at `0x18051191c`
- `GDI32!DeleteDC` at `0x1805118f8`
- `GDI32!DeleteDC` at `0x180511901`
- `GDI32!DeleteDC` at `0x18051190a`
- `GDI32!DeleteDC` at `0x180511913`
- `GDI32!DeleteDC` at `0x18051191c`
- `GDI32!SelectObject` at `0x18051128a`
- `GDI32!SelectObject` at `0x18051135b`
- `GDI32!SelectObject` at `0x180511371`
- `GDI32!SelectObject` at `0x180511382`
- `GDI32!SelectObject` at `0x180511395`
- `GDI32!SelectObject` at `0x1805118a1`
- `GDI32!SelectObject` at `0x1805118b8`
- `GDI32!SelectObject` at `0x1805118cf`
- `GDI32!SelectObject` at `0x1805118e6`
- `GDI32!SelectObject` at `0x18051128a`
- `GDI32!SelectObject` at `0x18051135b`
- `GDI32!SelectObject` at `0x180511371`
- `GDI32!SelectObject` at `0x180511382`
- `GDI32!SelectObject` at `0x180511395`
- `GDI32!SelectObject` at `0x1805118a1`
- `GDI32!SelectObject` at `0x1805118b8`
- `GDI32!SelectObject` at `0x1805118cf`
- `GDI32!SelectObject` at `0x1805118e6`
- `GDI32!CreateCompatibleDC` at `0x18051127b`
- `GDI32!CreateCompatibleDC` at `0x1805112b3`
- `GDI32!CreateCompatibleDC` at `0x1805112c1`
- `GDI32!CreateCompatibleDC` at `0x1805112cf`
- `GDI32!CreateCompatibleDC` at `0x1805112db`
- `GDI32!CreateCompatibleDC` at `0x18051127b`
- `GDI32!CreateCompatibleDC` at `0x1805112b3`
- `GDI32!CreateCompatibleDC` at `0x1805112c1`
- `GDI32!CreateCompatibleDC` at `0x1805112cf`
- `GDI32!CreateCompatibleDC` at `0x1805112db`
- `GDI32!SetBkColor` at `0x180511450`
- `GDI32!SetBkColor` at `0x1805114dc`
- `GDI32!SetBkColor` at `0x180511450`
- `GDI32!SetBkColor` at `0x1805114dc`
- `GDI32!BitBlt` at `0x1805113e8`
- `GDI32!BitBlt` at `0x180511485`
- `GDI32!BitBlt` at `0x18051150f`
- `GDI32!BitBlt` at `0x1805115a4`
- `GDI32!BitBlt` at `0x180511623`
- `GDI32!BitBlt` at `0x1805116b0`
- `GDI32!BitBlt` at `0x18051172f`
- `GDI32!BitBlt` at `0x1805117bc`
- `GDI32!BitBlt` at `0x180511840`
- `GDI32!BitBlt` at `0x1805113e8`
- `GDI32!BitBlt` at `0x180511485`
- `GDI32!BitBlt` at `0x18051150f`
- `GDI32!BitBlt` at `0x1805115a4`
- `GDI32!BitBlt` at `0x180511623`
- `GDI32!BitBlt` at `0x1805116b0`
- `GDI32!BitBlt` at `0x18051172f`
- `GDI32!BitBlt` at `0x1805117bc`
- `GDI32!BitBlt` at `0x180511840`
- `GDI32!GetObjectW` at `0x18051129d`
- `GDI32!GetObjectW` at `0x18051129d`
- `GDI32!CreateCompatibleBitmap` at `0x180511330`
- `GDI32!CreateCompatibleBitmap` at `0x180511347`
- `GDI32!CreateCompatibleBitmap` at `0x180511330`
- `GDI32!CreateCompatibleBitmap` at `0x180511347`
- `GDI32!CreateBitmap` at `0x180511300`
- `GDI32!CreateBitmap` at `0x18051131e`
- `GDI32!CreateBitmap` at `0x180511300`
- `GDI32!CreateBitmap` at `0x18051131e`
- `GDI32!GetMapMode` at `0x1805113a8`
- `GDI32!GetMapMode` at `0x1805113a8`

## pseudocode

```c
void __fastcall xDrawTransparentBitmap(HDC hdc, HBITMAP h)
{
  HDC hdcSrc; // r12
  int v5; // r14d
  int v6; // r15d
  HDC v7; // r13
  HBITMAP Bitmap; // rbp
  HBITMAP v9; // rsi
  HBITMAP CompatibleBitmap; // rdi
  HBITMAP v11; // rax
  HBITMAP v12; // rdx
  HDC v13; // rbp
  HBITMAP v14; // rbx
  HDC v15; // rax
  HBITMAP v16; // rdx
  HDC v17; // rsi
  int MapMode; // eax
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  COLORREF v21; // edi
  DWORD v22; // ebx
  unsigned int v23; // eax
  DWORD v24; // ebx
  unsigned int v25; // eax
  DWORD v26; // ebx
  unsigned int v27; // eax
  DWORD v28; // ebx
  unsigned int v29; // eax
  DWORD v30; // ebx
  unsigned int v31; // eax
  DWORD v32; // ebx
  unsigned int v33; // eax
  DWORD v34; // ebx
  unsigned int v35; // eax
  DWORD v36; // ebx
  unsigned int v37; // eax
  HGDIOBJ v38; // rax
  HGDIOBJ v39; // rax
  HGDIOBJ v40; // rax
  HGDIOBJ v41; // rax
  HDC v42; // [rsp+50h] [rbp-98h]
  HDC CompatibleDC; // [rsp+58h] [rbp-90h]
  HDC v44; // [rsp+58h] [rbp-90h]
  HDC v45; // [rsp+60h] [rbp-88h]
  HDC v46; // [rsp+60h] [rbp-88h]
  HGDIOBJ ha; // [rsp+68h] [rbp-80h]
  HGDIOBJ v48; // [rsp+70h] [rbp-78h]
  int pv[28]; // [rsp+78h] [rbp-70h] BYREF

  memset(pv, 0, 32);
  hdcSrc = CreateCompatibleDC(hdc);
  SelectObject(hdcSrc, h);
  GetObjectW(h, 32, pv);
  v5 = pv[1];
  v6 = pv[2];
  CompatibleDC = CreateCompatibleDC(hdc);
  v45 = CreateCompatibleDC(hdc);
  v7 = CreateCompatibleDC(hdc);
  v42 = CreateCompatibleDC(hdc);
  Bitmap = CreateBitmap(v5, v6, 1u, 1u, 0);
  v9 = CreateBitmap(v5, v6, 1u, 1u, 0);
  CompatibleBitmap = CreateCompatibleBitmap(hdc, v5, v6);
  v11 = CreateCompatibleBitmap(hdc, v5, v6);
  v12 = Bitmap;
  v13 = CompatibleDC;
  v14 = v11;
  v15 = (HDC)SelectObject(CompatibleDC, v12);
  v16 = v9;
  v17 = v45;
  v44 = v15;
  v46 = (HDC)SelectObject(v45, v16);
  ha = SelectObject(v7, CompatibleBitmap);
  v48 = SelectObject(v42, v14);
  MapMode = GetMapMode(hdc);
  SetMapMode(hdcSrc, MapMode);
  if ( !BitBlt(v42, 0, 0, v5, v6, hdcSrc, 0, 0, 0xCC0020u)
    && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      WPP_e1afb13c57b53ac3446f0b206a0ef6ae_Traceguids,
      CurrentThreadActivityIdPrefix,
      LastError);
  }
  v21 = SetBkColor(hdcSrc, 0xFF00FFu);
  if ( !BitBlt(v17, 0, 0, v5, v6, hdcSrc, 0, 0, 0xCC0020u)
    && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v22 = GetLastError();
    v23 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_e1afb13c57b53ac3446f0b206a0ef6ae_Traceguids, v23, v22);
  }
  SetBkColor(hdcSrc, v21);
  if ( !BitBlt(v13, 0, 0, v5, v6, v17, 0, 0, 0x330008u)
    && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v24 = GetLastError();
    v25 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_e1afb13c57b53ac3446f0b206a0ef6ae_Traceguids, v25, v24);
  }
  if ( !BitBlt(v7, 0, 0, v5, v6, hdc, 0, 0, 0xCC0020u)
    && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v26 = GetLastError();
    v27 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_e1afb13c57b53ac3446f0b206a0ef6ae_Traceguids, v27, v26);
  }
  if ( !BitBlt(v7, 0, 0, v5, v6, v17, 0, 0, 0x8800C6u)
    && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v28 = GetLastError();
    v29 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_e1afb13c57b53ac3446f0b206a0ef6ae_Traceguids, v29, v28);
  }
  if ( !BitBlt(hdcSrc, 0, 0, v5, v6, v13, 0, 0, 0x8800C6u)
    && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v30 = GetLastError();
    v31 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_e1afb13c57b53ac3446f0b206a0ef6ae_Traceguids, v31, v30);
  }
  if ( !BitBlt(v7, 0, 0, v5, v6, hdcSrc, 0, 0, 0xEE0086u)
    && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v32 = GetLastError();
    v33 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_e1afb13c57b53ac3446f0b206a0ef6ae_Traceguids, v33, v32);
  }
  if ( !BitBlt(hdc, 0, 0, v5, v6, v7, 0, 0, 0xCC0020u)
    && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v34 = GetLastError();
    v35 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_e1afb13c57b53ac3446f0b206a0ef6ae_Traceguids, v35, v34);
  }
  if ( !BitBlt(hdcSrc, 0, 0, v5, v6, v42, 0, 0, 0xCC0020u)
    && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v36 = GetLastError();
    v37 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_e1afb13c57b53ac3446f0b206a0ef6ae_Traceguids, v37, v36);
  }
  v38 = SelectObject(v13, v44);
  DeleteObject(v38);
  v39 = SelectObject(v17, v46);
  DeleteObject(v39);
  v40 = SelectObject(v7, ha);
  DeleteObject(v40);
  v41 = SelectObject(v42, v48);
  DeleteObject(v41);
  DeleteDC(v7);
  DeleteDC(v13);
  DeleteDC(v17);
  DeleteDC(v42);
  DeleteDC(hdcSrc);
}

```

## disassembly

```asm
0x180511250  mov     rax, rsp
0x180511253  mov     [rax+8], rcx
0x180511257  push    rbx
0x180511258  push    rbp
0x180511259  push    rsi
0x18051125a  push    rdi
0x18051125b  push    r12
0x18051125d  push    r13
0x18051125f  push    r14
0x180511261  push    r15
0x180511263  sub     rsp, 0A8h
0x18051126a  xorps   xmm0, xmm0
0x18051126d  mov     rbx, rdx
0x180511270  movups  xmmword ptr [rax-70h], xmm0
0x180511274  mov     rdi, rcx
0x180511277  movups  xmmword ptr [rax-60h], xmm0
0x18051127b  call    cs:__imp_CreateCompatibleDC
0x180511281  mov     rcx, rax; hdc
0x180511284  mov     rdx, rbx; h
0x180511287  mov     r12, rax
0x18051128a  call    cs:__imp_SelectObject
0x180511290  lea     r8, [rsp+0E8h+pv]; pv
0x180511295  mov     edx, 20h ; ' '; c
0x18051129a  mov     rcx, rbx; h
0x18051129d  call    cs:__imp_GetObjectW
0x1805112a3  mov     r14d, [rsp+0E8h+nWidth]
0x1805112a8  mov     rcx, rdi; hdc
0x1805112ab  mov     r15d, [rsp+0E8h+nHeight]
0x1805112b3  call    cs:__imp_CreateCompatibleDC
0x1805112b9  mov     rcx, rdi; hdc
0x1805112bc  mov     [rsp+0E8h+var_90], rax
0x1805112c1  call    cs:__imp_CreateCompatibleDC
0x1805112c7  mov     rcx, rdi; hdc
0x1805112ca  mov     [rsp+0E8h+var_88], rax
0x1805112cf  call    cs:__imp_CreateCompatibleDC
0x1805112d5  mov     rcx, rdi; hdc
0x1805112d8  mov     r13, rax
0x1805112db  call    cs:__imp_CreateCompatibleDC
0x1805112e1  mov     ebx, 1
0x1805112e6  mov     [rsp+0E8h+lpBits], 0; lpBits
0x1805112ef  mov     r9d, ebx; nBitCount
0x1805112f2  mov     [rsp+0E8h+var_98], rax
0x1805112f7  mov     r8d, ebx; nPlanes
0x1805112fa  mov     edx, r15d; nHeight
0x1805112fd  mov     ecx, r14d; nWidth
0x180511300  call    cs:__imp_CreateBitmap
0x180511306  mov     r9d, ebx; nBitCount
0x180511309  mov     [rsp+0E8h+lpBits], 0; lpBits
0x180511312  mov     r8d, ebx; nPlanes
0x180511315  mov     edx, r15d; nHeight
0x180511318  mov     ecx, r14d; nWidth
0x18051131b  mov     rbp, rax
0x18051131e  call    cs:__imp_CreateBitmap
0x180511324  mov     r8d, r15d; cy
0x180511327  mov     edx, r14d; cx
0x18051132a  mov     rcx, rdi; hdc
0x18051132d  mov     rsi, rax
0x180511330  call    cs:__imp_CreateCompatibleBitmap
0x180511336  mov     rcx, [rsp+0E8h+hdc]; hdc
0x18051133e  mov     r8d, r15d; cy
0x180511341  mov     edx, r14d; cx
0x180511344  mov     rdi, rax
0x180511347  call    cs:__imp_CreateCompatibleBitmap
0x18051134d  mov     rdx, rbp; h
0x180511350  mov     rbp, [rsp+0E8h+var_90]
0x180511355  mov     rcx, rbp; hdc
0x180511358  mov     rbx, rax
0x18051135b  call    cs:__imp_SelectObject
0x180511361  mov     rdx, rsi; h
0x180511364  mov     rsi, [rsp+0E8h+var_88]
0x180511369  mov     rcx, rsi; hdc
0x18051136c  mov     [rsp+0E8h+var_90], rax
0x180511371  call    cs:__imp_SelectObject
0x180511377  mov     rdx, rdi; h
0x18051137a  mov     rcx, r13; hdc
0x18051137d  mov     [rsp+0E8h+var_88], rax
0x180511382  call    cs:__imp_SelectObject
0x180511388  mov     rcx, [rsp+0E8h+var_98]; hdc
0x18051138d  mov     rdx, rbx; h
0x180511390  mov     [rsp+0E8h+h], rax
0x180511395  call    cs:__imp_SelectObject
0x18051139b  mov     rcx, [rsp+0E8h+hdc]; hdc
0x1805113a3  mov     [rsp+0E8h+var_78], rax
0x1805113a8  call    cs:__imp_GetMapMode
0x1805113ae  mov     edx, eax; iMode
0x1805113b0  mov     rcx, r12; hdc
0x1805113b3  call    cs:__imp_SetMapMode
0x1805113b9  mov     [rsp+0E8h+rop], 0CC0020h; rop
0x1805113c1  mov     [rsp+0E8h+y1], 0; y1
0x1805113c9  mov     [rsp+0E8h+x1], 0; x1
0x1805113d1  mov     [rsp+0E8h+hdcSrc], r12; hdcSrc
0x1805113d6  mov     dword ptr [rsp+0E8h+lpBits], r15d; cy
0x1805113db  mov     rcx, [rsp+0E8h+var_98]; hdc
0x1805113e0  mov     r9d, r14d; cx
0x1805113e3  xor     r8d, r8d; y
0x1805113e6  xor     edx, edx; x
0x1805113e8  call    cs:__imp_BitBlt
0x1805113ee  lea     rbx, WPP_GLOBAL_Control
0x1805113f5  test    eax, eax
0x1805113f7  jnz     short loc_180511448
0x1805113f9  mov     rax, cs:WPP_GLOBAL_Control
0x180511400  cmp     rax, rbx
0x180511403  jz      short loc_180511448
0x180511405  test    byte ptr [rax+1Ch], 1
0x180511409  jz      short loc_180511448
0x18051140b  cmp     byte ptr [rax+19h], 2
0x18051140f  jb      short loc_180511448
0x180511411  call    cs:__imp_GetLastError
0x180511417  mov     ebx, eax
0x180511419  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18051141e  mov     rcx, cs:WPP_GLOBAL_Control
0x180511425  lea     r8, WPP_e1afb13c57b53ac3446f0b206a0ef6ae_Traceguids
0x18051142c  mov     edx, 1Ah
0x180511431  mov     dword ptr [rsp+0E8h+lpBits], ebx
0x180511435  mov     r9d, eax
0x180511438  mov     rcx, [rcx+10h]
0x18051143c  call    WPP_SF_Dd
0x180511441  lea     rbx, WPP_GLOBAL_Control
0x180511448  mov     edx, 0FF00FFh; color
0x18051144d  mov     rcx, r12; hdc
0x180511450  call    cs:__imp_SetBkColor
0x180511456  mov     [rsp+0E8h+rop], 0CC0020h; rop
0x18051145e  mov     r9d, r14d; cx
0x180511461  mov     [rsp+0E8h+y1], 0; y1
0x180511469  xor     r8d, r8d; y
0x18051146c  mov     [rsp+0E8h+x1], 0; x1
0x180511474  xor     edx, edx; x
0x180511476  mov     [rsp+0E8h+hdcSrc], r12; hdcSrc
0x18051147b  mov     rcx, rsi; hdc
0x18051147e  mov     dword ptr [rsp+0E8h+lpBits], r15d; cy
0x180511483  mov     edi, eax
0x180511485  call    cs:__imp_BitBlt
0x18051148b  test    eax, eax
0x18051148d  jnz     short loc_1805114D7
0x18051148f  mov     rax, cs:WPP_GLOBAL_Control
0x180511496  cmp     rax, rbx
0x180511499  jz      short loc_1805114D7
0x18051149b  test    byte ptr [rax+1Ch], 1
0x18051149f  jz      short loc_1805114D7
0x1805114a1  cmp     byte ptr [rax+19h], 2
0x1805114a5  jb      short loc_1805114D7
0x1805114a7  call    cs:__imp_GetLastError
0x1805114ad  mov     ebx, eax
0x1805114af  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805114b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1805114bb  lea     r8, WPP_e1afb13c57b53ac3446f0b206a0ef6ae_Traceguids
0x1805114c2  mov     edx, 1Bh
0x1805114c7  mov     dword ptr [rsp+0E8h+lpBits], ebx
0x1805114cb  mov     r9d, eax
0x1805114ce  mov     rcx, [rcx+10h]
0x1805114d2  call    WPP_SF_Dd
0x1805114d7  mov     edx, edi; color
0x1805114d9  mov     rcx, r12; hdc
0x1805114dc  call    cs:__imp_SetBkColor
0x1805114e2  mov     [rsp+0E8h+rop], 330008h; rop
0x1805114ea  mov     r9d, r14d; cx
0x1805114ed  mov     [rsp+0E8h+y1], 0; y1
0x1805114f5  xor     r8d, r8d; y
0x1805114f8  mov     [rsp+0E8h+x1], 0; x1
0x180511500  xor     edx, edx; x
0x180511502  mov     [rsp+0E8h+hdcSrc], rsi; hdcSrc
0x180511507  mov     rcx, rbp; hdc
0x18051150a  mov     dword ptr [rsp+0E8h+lpBits], r15d; cy
0x18051150f  call    cs:__imp_BitBlt
0x180511515  test    eax, eax
0x180511517  jnz     short loc_180511568
0x180511519  mov     rax, cs:WPP_GLOBAL_Control
0x180511520  lea     rbx, WPP_GLOBAL_Control
0x180511527  cmp     rax, rbx
0x18051152a  jz      short loc_18051156F
0x18051152c  test    byte ptr [rax+1Ch], 1
0x180511530  jz      short loc_18051156F
0x180511532  cmp     byte ptr [rax+19h], 2
0x180511536  jb      short loc_18051156F
0x180511538  call    cs:__imp_GetLastError
0x18051153e  mov     ebx, eax
0x180511540  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180511545  mov     rcx, cs:WPP_GLOBAL_Control
0x18051154c  lea     r8, WPP_e1afb13c57b53ac3446f0b206a0ef6ae_Traceguids
0x180511553  mov     edx, 1Ch
0x180511558  mov     dword ptr [rsp+0E8h+lpBits], ebx
0x18051155c  mov     r9d, eax
0x18051155f  mov     rcx, [rcx+10h]
0x180511563  call    WPP_SF_Dd
0x180511568  lea     rbx, WPP_GLOBAL_Control
0x18051156f  mov     rdi, [rsp+0E8h+hdc]
0x180511577  mov     r9d, r14d; cx
0x18051157a  mov     [rsp+0E8h+rop], 0CC0020h; rop
0x180511582  xor     r8d, r8d; y
0x180511585  mov     [rsp+0E8h+y1], 0; y1
0x18051158d  xor     edx, edx; x
0x18051158f  mov     [rsp+0E8h+x1], 0; x1
0x180511597  mov     rcx, r13; hdc
0x18051159a  mov     [rsp+0E8h+hdcSrc], rdi; hdcSrc
0x18051159f  mov     dword ptr [rsp+0E8h+lpBits], r15d; cy
0x1805115a4  call    cs:__imp_BitBlt
0x1805115aa  test    eax, eax
0x1805115ac  jnz     short loc_1805115F6
0x1805115ae  mov     rax, cs:WPP_GLOBAL_Control
0x1805115b5  cmp     rax, rbx
0x1805115b8  jz      short loc_1805115F6
0x1805115ba  test    byte ptr [rax+1Ch], 1
0x1805115be  jz      short loc_1805115F6
0x1805115c0  cmp     byte ptr [rax+19h], 2
0x1805115c4  jb      short loc_1805115F6
0x1805115c6  call    cs:__imp_GetLastError
0x1805115cc  mov     ebx, eax
0x1805115ce  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805115d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1805115da  lea     r8, WPP_e1afb13c57b53ac3446f0b206a0ef6ae_Traceguids
0x1805115e1  mov     edx, 1Dh
0x1805115e6  mov     dword ptr [rsp+0E8h+lpBits], ebx
0x1805115ea  mov     r9d, eax
0x1805115ed  mov     rcx, [rcx+10h]
0x1805115f1  call    WPP_SF_Dd
0x1805115f6  mov     [rsp+0E8h+rop], 8800C6h; rop
0x1805115fe  mov     r9d, r14d; cx
0x180511601  mov     [rsp+0E8h+y1], 0; y1
0x180511609  xor     r8d, r8d; y
0x18051160c  mov     [rsp+0E8h+x1], 0; x1
0x180511614  xor     edx, edx; x
0x180511616  mov     [rsp+0E8h+hdcSrc], rsi; hdcSrc
0x18051161b  mov     rcx, r13; hdc
0x18051161e  mov     dword ptr [rsp+0E8h+lpBits], r15d; cy
0x180511623  call    cs:__imp_BitBlt
0x180511629  test    eax, eax
0x18051162b  jnz     short loc_18051167C
0x18051162d  mov     rax, cs:WPP_GLOBAL_Control
0x180511634  lea     rbx, WPP_GLOBAL_Control
0x18051163b  cmp     rax, rbx
0x18051163e  jz      short loc_180511683
0x180511640  test    byte ptr [rax+1Ch], 1
0x180511644  jz      short loc_180511683
0x180511646  cmp     byte ptr [rax+19h], 2
0x18051164a  jb      short loc_180511683
0x18051164c  call    cs:__imp_GetLastError
0x180511652  mov     ebx, eax
0x180511654  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180511659  mov     rcx, cs:WPP_GLOBAL_Control
0x180511660  lea     r8, WPP_e1afb13c57b53ac3446f0b206a0ef6ae_Traceguids
0x180511667  mov     edx, 1Eh
0x18051166c  mov     dword ptr [rsp+0E8h+lpBits], ebx
0x180511670  mov     r9d, eax
0x180511673  mov     rcx, [rcx+10h]
0x180511677  call    WPP_SF_Dd
0x18051167c  lea     rbx, WPP_GLOBAL_Control
0x180511683  mov     [rsp+0E8h+rop], 8800C6h; rop
0x18051168b  mov     r9d, r14d; cx
0x18051168e  mov     [rsp+0E8h+y1], 0; y1
0x180511696  xor     r8d, r8d; y
0x180511699  mov     [rsp+0E8h+x1], 0; x1
0x1805116a1  xor     edx, edx; x
0x1805116a3  mov     [rsp+0E8h+hdcSrc], rbp; hdcSrc
0x1805116a8  mov     rcx, r12; hdc
0x1805116ab  mov     dword ptr [rsp+0E8h+lpBits], r15d; cy
0x1805116b0  call    cs:__imp_BitBlt
0x1805116b6  test    eax, eax
0x1805116b8  jnz     short loc_180511702
0x1805116ba  mov     rax, cs:WPP_GLOBAL_Control
0x1805116c1  cmp     rax, rbx
0x1805116c4  jz      short loc_180511702
0x1805116c6  test    byte ptr [rax+1Ch], 1
0x1805116ca  jz      short loc_180511702
0x1805116cc  cmp     byte ptr [rax+19h], 2
0x1805116d0  jb      short loc_180511702
0x1805116d2  call    cs:__imp_GetLastError
0x1805116d8  mov     ebx, eax
0x1805116da  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805116df  mov     rcx, cs:WPP_GLOBAL_Control
0x1805116e6  lea     r8, WPP_e1afb13c57b53ac3446f0b206a0ef6ae_Traceguids
0x1805116ed  mov     edx, 1Fh
0x1805116f2  mov     dword ptr [rsp+0E8h+lpBits], ebx
0x1805116f6  mov     r9d, eax
0x1805116f9  mov     rcx, [rcx+10h]
0x1805116fd  call    WPP_SF_Dd
0x180511702  mov     [rsp+0E8h+rop], 0EE0086h; rop
0x18051170a  mov     r9d, r14d; cx
0x18051170d  mov     [rsp+0E8h+y1], 0; y1
0x180511715  xor     r8d, r8d; y
0x180511718  mov     [rsp+0E8h+x1], 0; x1
0x180511720  xor     edx, edx; x
0x180511722  mov     [rsp+0E8h+hdcSrc], r12; hdcSrc
0x180511727  mov     rcx, r13; hdc
0x18051172a  mov     dword ptr [rsp+0E8h+lpBits], r15d; cy
0x18051172f  call    cs:__imp_BitBlt
0x180511735  test    eax, eax
0x180511737  jnz     short loc_180511788
0x180511739  mov     rax, cs:WPP_GLOBAL_Control
0x180511740  lea     rbx, WPP_GLOBAL_Control
0x180511747  cmp     rax, rbx
0x18051174a  jz      short loc_18051178F
0x18051174c  test    byte ptr [rax+1Ch], 1
0x180511750  jz      short loc_18051178F
0x180511752  cmp     byte ptr [rax+19h], 2
0x180511756  jb      short loc_18051178F
0x180511758  call    cs:__imp_GetLastError
0x18051175e  mov     ebx, eax
0x180511760  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180511765  mov     rcx, cs:WPP_GLOBAL_Control
0x18051176c  lea     r8, WPP_e1afb13c57b53ac3446f0b206a0ef6ae_Traceguids
  ... truncated ...
```
