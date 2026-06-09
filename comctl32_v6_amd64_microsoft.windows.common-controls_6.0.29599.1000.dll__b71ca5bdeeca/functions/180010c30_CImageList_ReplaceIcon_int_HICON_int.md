# CImageList::_ReplaceIcon(int,HICON__ *,int *)

- ea: `0x180010c30`
- end: `0x180011562`
- name: `?_ReplaceIcon@CImageList@@IEAAJHPEAUHICON__@@PEAH@Z`
- size: `2354`
- prototype: `__int64 __fastcall(CImageList *__hidden this, int, HICON h, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800108d0`

## callees

- `0x180010c30`
- `0x180011570`
- `0x18001180c`
- `0x1800118a4`
- `0x1800a88c8`
- `0x180114520`
- `0x180114ebc`
- `0x1801d0c48`
- `0x1801d1010`

## import_xrefs

- `GDI32!DeleteObject` at `0x180010d18`
- `GDI32!DeleteObject` at `0x180010d27`
- `GDI32!DeleteObject` at `0x180011131`
- `GDI32!DeleteObject` at `0x18001113b`
- `GDI32!DeleteObject` at `0x180010d18`
- `GDI32!DeleteObject` at `0x180010d27`
- `GDI32!DeleteObject` at `0x180011131`
- `GDI32!DeleteObject` at `0x18001113b`
- `GDI32!GetObjectW` at `0x180010d01`
- `GDI32!GetObjectW` at `0x180010d01`
- `GDI32!SelectObject` at `0x1800112d9`
- `GDI32!SelectObject` at `0x180011324`
- `GDI32!SelectObject` at `0x1800112d9`
- `GDI32!SelectObject` at `0x180011324`
- `GDI32!DeleteDC` at `0x18001132d`
- `GDI32!DeleteDC` at `0x18001132d`
- `GDI32!CreateCompatibleDC` at `0x180010f6f`
- `GDI32!CreateCompatibleDC` at `0x180010f6f`
- `GDI32!BitBlt` at `0x180011318`
- `GDI32!BitBlt` at `0x180011318`
- `USER32!CopyImage` at `0x1800113c4`
- `USER32!CopyImage` at `0x1800114b0`
- `USER32!CopyImage` at `0x1800113c4`
- `USER32!CopyImage` at `0x1800114b0`
- `USER32!FillRect` at `0x18001143e`
- `USER32!FillRect` at `0x18001143e`
- `USER32!DestroyIcon` at `0x180011247`
- `USER32!DestroyIcon` at `0x180011247`
- `USER32!GetIconInfo` at `0x180010cc5`
- `USER32!GetIconInfo` at `0x180010f5a`
- `USER32!GetIconInfo` at `0x180010cc5`
- `USER32!GetIconInfo` at `0x180010f5a`
- `USER32!SetRect` at `0x180010f2a`
- `USER32!SetRect` at `0x180010fce`
- `USER32!SetRect` at `0x18001105e`
- `USER32!SetRect` at `0x180010f2a`
- `USER32!SetRect` at `0x180010fce`
- `USER32!SetRect` at `0x18001105e`
- `USER32!DrawIconEx` at `0x18001140a`
- `USER32!DrawIconEx` at `0x180011473`
- `USER32!DrawIconEx` at `0x18001140a`
- `USER32!DrawIconEx` at `0x180011473`

## pseudocode

```c
__int64 __fastcall CImageList::_ReplaceIcon(CImageList *this, int a2, HICON h, int *a4)
{
  HICON v4; // rbx
  int v5; // r15d
  int v7; // r14d
  int v8; // r12d
  signed int yHotspot; // ebx
  int v10; // r15d
  DWORD xHotspot; // esi
  bool v12; // cc
  int v13; // eax
  int v14; // ebx
  int v15; // ecx
  int v16; // r12d
  int v17; // r14d
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rsi
  int v20; // esi
  int v21; // r10d
  int i; // edx
  int v23; // r9d
  int v24; // r11d
  int v25; // edx
  int v26; // eax
  int v27; // ecx
  int v28; // r10d
  unsigned __int8 *v29; // r9
  int v30; // eax
  __int64 v31; // rbx
  int v32; // ecx
  unsigned int v33; // edx
  unsigned int v34; // ecx
  int *v35; // rbx
  int v36; // ecx
  HDC v37; // rcx
  HGDIOBJ v39; // rbx
  unsigned int v40; // esi
  unsigned int v41; // eax
  unsigned int v42; // esi
  int v43; // eax
  HICON v44; // rax
  unsigned int v45; // edx
  unsigned int v46; // r8d
  unsigned int v47; // esi
  unsigned int v48; // eax
  unsigned int v49; // esi
  HICON piconinfo[5]; // [rsp+70h] [rbp-98h] BYREF
  void *ppv; // [rsp+98h] [rbp-70h] BYREF
  struct tagRECT rc; // [rsp+A0h] [rbp-68h] BYREF
  int v56; // [rsp+B0h] [rbp-58h] BYREF
  ICONINFO pv; // [rsp+B8h] [rbp-50h] BYREF

  v4 = h;
  piconinfo[0] = h;
  v5 = a2;
  *a4 = -1;
  rc = 0;
  if ( a2 < -1 )
    return 2147942487LL;
  v7 = *((_DWORD *)this + 32);
  if ( *((_QWORD *)this + 16) == 0x1000000010LL )
  {
    v44 = (HICON)CopyImage(h, 1u, 16, 16, 0x4004u);
    goto LABEL_93;
  }
  v8 = *((_DWORD *)this + 33);
  memset(piconinfo, 0, sizeof(piconinfo));
  if ( GetIconInfo(h, (PICONINFO)&piconinfo[1]) )
  {
    yHotspot = 32;
    v10 = -2147467259;
    xHotspot = 32;
    if ( LODWORD(piconinfo[1]) )
    {
      memset(&pv, 0, sizeof(pv));
      if ( GetObjectW(piconinfo[4], 32, &pv) )
      {
        xHotspot = pv.xHotspot;
        v10 = 0;
        yHotspot = pv.yHotspot;
      }
    }
    DeleteObject(piconinfo[3]);
    if ( piconinfo[4] )
      DeleteObject(piconinfo[4]);
    if ( v10 >= 0 )
    {
      if ( xHotspot == v7 )
      {
        v12 = yHotspot < v8;
        if ( yHotspot == v8 )
        {
          v4 = h;
          piconinfo[0] = h;
LABEL_24:
          v5 = a2;
          goto LABEL_25;
        }
        goto LABEL_13;
      }
      if ( (int)xHotspot >= v7 )
      {
        v12 = yHotspot < v8;
LABEL_13:
        if ( !v12 )
        {
          piconinfo[1] = 0;
          if ( ImageList_CoCreateInstance(
                 &CLSID_ImageList,
                 0,
                 &GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1,
                 (void **)&piconinfo[1]) >= 0 )
          {
            v13 = (*(__int64 (__fastcall **)(HICON, _QWORD, _QWORD, __int64, int, int))(*(_QWORD *)piconinfo[1] + 328LL))(
                    piconinfo[1],
                    xHotspot,
                    (unsigned int)yHotspot,
                    131105,
                    1,
                    1);
            v4 = h;
            if ( v13 >= 0 )
            {
              v56 = -1;
              if ( (*(int (__fastcall **)(HICON, __int64, HICON, int *))(*(_QWORD *)piconinfo[1] + 32LL))(
                     piconinfo[1],
                     0xFFFFFFFFLL,
                     h,
                     &v56) >= 0 )
              {
                ppv = 0;
                if ( ImageList_CoCreateInstance(&CLSID_ImageList, 0, &GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1, &ppv) >= 0 )
                {
                  if ( (*(int (__fastcall **)(void *, _QWORD, _QWORD, __int64, int, int))(*(_QWORD *)ppv + 328LL))(
                         ppv,
                         (unsigned int)v7,
                         (unsigned int)v8,
                         131105,
                         1,
                         1) >= 0
                    && (*(int (__fastcall **)(void *, __int64))(*(_QWORD *)ppv + 152LL))(ppv, 1) >= 0
                    && (*(int (__fastcall **)(void *, _QWORD, HICON, _QWORD, _QWORD, _DWORD))(*(_QWORD *)ppv + 344LL))(
                         ppv,
                         0,
                         piconinfo[1],
                         0,
                         0,
                         0) >= 0 )
                  {
                    (*(void (__fastcall **)(void *, _QWORD, __int64, HICON *))(*(_QWORD *)ppv + 80LL))(
                      ppv,
                      0,
                      0x10000,
                      piconinfo);
                  }
                  (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
                }
              }
            }
            (*(void (__fastcall **)(HICON))(*(_QWORD *)piconinfo[1] + 16LL))(piconinfo[1]);
            goto LABEL_24;
          }
        }
      }
    }
    v4 = h;
    goto LABEL_24;
  }
LABEL_25:
  if ( piconinfo[0] )
    goto LABEL_26;
  v44 = (HICON)CopyImage(v4, 1u, v7, v8, 0x4000u);
LABEL_93:
  piconinfo[0] = v44;
  if ( !v44 )
    return 2147942414LL;
LABEL_26:
  if ( v5 == -1 )
  {
    v14 = 0;
    v15 = *((_DWORD *)this + 30);
    if ( *((_DWORD *)this + 29) + 2 > v15 )
    {
      v43 = *((_DWORD *)this + 31);
      if ( v43 < 1 )
        v43 = 1;
      v14 = CImageList::_ReAllocBitmaps(this, v43 + v15 + 1);
      if ( v14 < 0 )
        goto LABEL_72;
    }
    v5 = *((_DWORD *)this + 29);
    *((_DWORD *)this + 29) = v5 + 1;
    if ( v5 == -1 )
      goto LABEL_72;
  }
  if ( v5 >= 0 && v5 < *((_DWORD *)this + 29) )
  {
    SetRect(
      &rc,
      0,
      *((_DWORD *)this + 33) * v5,
      *((_DWORD *)this + 32),
      *((_DWORD *)this + 33) * v5 + *((_DWORD *)this + 33));
    v16 = 0;
    v17 = 0;
    if ( (*((_DWORD *)this + 34) & 0xFE) == 0x20 )
    {
      memset(&pv, 0, sizeof(pv));
      if ( GetIconInfo(piconinfo[0], &pv) )
      {
        CompatibleDC = CreateCompatibleDC(*((HDC *)this + 24));
        hdcSrc = CompatibleDC;
        if ( CompatibleDC )
        {
          v39 = SelectObject(CompatibleDC, pv.hbmColor);
          BitBlt(*((HDC *)this + 24), rc.left, rc.top, rc.right - rc.left, rc.bottom - rc.top, hdcSrc, 0, 0, 0xCC0020u);
          SelectObject(hdcSrc, v39);
          DeleteDC(hdcSrc);
        }
        if ( (*((_DWORD *)this + 34) & 0xFE) != 0x20 )
          goto LABEL_79;
        *(_OWORD *)&piconinfo[1] = 0;
        if ( v5 >= *((_DWORD *)this + 29) )
          goto LABEL_79;
        v20 = ~v5;
        SetRect(
          (LPRECT)&piconinfo[1],
          0,
          *((_DWORD *)this + 33) * (v20 + *((_DWORD *)this + 30)),
          *((_DWORD *)this + 32),
          *((_DWORD *)this + 33) * (v20 + *((_DWORD *)this + 30)) + *((_DWORD *)this + 33));
        v21 = HIDWORD(piconinfo[1]);
LABEL_38:
        if ( v21 < SHIDWORD(piconinfo[2]) )
        {
          for ( i = (int)piconinfo[1]; ; ++i )
          {
            if ( i >= SLODWORD(piconinfo[2]) )
            {
              ++v21;
              goto LABEL_38;
            }
            v23 = *((_DWORD *)this + 32);
            if ( *(_BYTE *)(*((_QWORD *)this + 23) + 4LL * (i + v23 * v21) + 3) )
              break;
          }
          if ( (*((_DWORD *)this + 34) & 0xFE) == 0x20 )
          {
            *(_OWORD *)&piconinfo[1] = 0;
            if ( v5 < *((_DWORD *)this + 29) )
              SetRect(
                (LPRECT)&piconinfo[1],
                0,
                *((_DWORD *)this + 33) * (v20 + *((_DWORD *)this + 30)),
                v23,
                *((_DWORD *)this + 33) * (v20 + *((_DWORD *)this + 30)) + *((_DWORD *)this + 33));
            v24 = HIDWORD(piconinfo[1]);
            v25 = HIDWORD(piconinfo[2]);
            if ( SHIDWORD(piconinfo[1]) < SHIDWORD(piconinfo[2]) )
            {
              v26 = (int)piconinfo[2];
              do
              {
                v27 = (int)piconinfo[1];
                v28 = *((_DWORD *)this + 32) * v24;
                if ( SLODWORD(piconinfo[1]) < v26 )
                {
                  do
                  {
                    v29 = (unsigned __int8 *)(*((_QWORD *)this + 23) + 4LL * (v27 + v28));
                    v30 = v29[3];
                    if ( (_BYTE)v30 )
                    {
                      v29[2] = (v30 * (unsigned int)v29[2] + 128) / 0xFF;
                      v29[1] = (v30 * (unsigned int)v29[1] + 128) / 0xFF;
                      *v29 = (v30 * (unsigned int)*v29 + 128) / 0xFF;
                    }
                    else
                    {
                      *(_DWORD *)v29 = 0;
                    }
                    v26 = (int)piconinfo[2];
                    ++v27;
                  }
                  while ( v27 < SLODWORD(piconinfo[2]) );
                  v25 = HIDWORD(piconinfo[2]);
                }
                ++v24;
              }
              while ( v24 < v25 );
            }
          }
          v17 = 1;
        }
        else
        {
LABEL_79:
          v16 = 1;
        }
        DeleteObject(pv.hbmColor);
        DeleteObject(pv.hbmMask);
      }
    }
    v31 = *((_QWORD *)this + 22);
    if ( v31 )
    {
      v32 = *(_DWORD *)v31;
      ppv = 0;
      if ( v5 < v32 )
      {
        memcpy_0(
          &ppv,
          (const void *)(*(_QWORD *)(v31 + 8) + (unsigned int)(v5 * *(_DWORD *)(v31 + 20))),
          *(unsigned int *)(v31 + 20));
        LODWORD(ppv) = v17 | (unsigned int)ppv & 0xFFFFFFFC;
        goto LABEL_63;
      }
      LODWORD(ppv) = v17;
      if ( v5 - v32 + 1 >= 0 )
      {
        v33 = v5 + 1;
        if ( v5 + 1 >= 0 )
        {
          v34 = *(_DWORD *)(v31 + 16);
          if ( v33 <= v34 )
          {
LABEL_62:
            memset_0(
              (void *)(*(_QWORD *)(v31 + 8) + (unsigned int)(*(_DWORD *)(v31 + 20) * *(_DWORD *)v31)),
              0,
              (unsigned int)(*(_DWORD *)(v31 + 20) * (v5 - *(_DWORD *)v31)));
            *(_DWORD *)v31 = v5 + 1;
LABEL_63:
            memcpy_0(
              (void *)(*(_QWORD *)(v31 + 8) + (unsigned int)(v5 * *(_DWORD *)(v31 + 20))),
              &ppv,
              *(unsigned int *)(v31 + 20));
            goto LABEL_64;
          }
          v40 = v34 + *(_DWORD *)(v31 + 24);
          if ( v33 > v40 )
            v40 = v5 + 1;
          if ( (int)v40 > 0 && v40 < 0x7FFFFFFFu / *(_DWORD *)(v31 + 20) && (unsigned int)DSA_ReAlloc(v31, v40) )
          {
            v41 = *(_DWORD *)(v31 + 24);
            v42 = v40 >> 2;
            if ( v41 <= v42 )
              v41 = v42;
            *(_DWORD *)(v31 + 24) = v41;
            goto LABEL_62;
          }
        }
      }
    }
LABEL_64:
    v35 = (int *)*((_QWORD *)this + 22);
    if ( v35 )
    {
      v36 = *v35;
      piconinfo[1] = 0;
      if ( v5 >= v36 )
      {
        if ( v5 - v36 + 1 < 0 )
          goto LABEL_68;
        v45 = v5 + 1;
        if ( v5 + 1 < 0 )
          goto LABEL_68;
        v46 = v35[4];
        if ( v45 > v46 )
        {
          v47 = v46 + v35[6];
          if ( v45 > v47 )
            v47 = v5 + 1;
          if ( (int)v47 <= 0 || v47 >= 0x7FFFFFFFu / v35[5] || !(unsigned int)DSA_ReAlloc(v35, v47) )
            goto LABEL_68;
          v48 = v35[6];
          v49 = v47 >> 2;
          if ( v48 <= v49 )
            v48 = v49;
          v35[6] = v48;
        }
        memset_0(
          (void *)(*((_QWORD *)v35 + 1) + (unsigned int)(v35[5] * *v35)),
          0,
          (unsigned int)(v35[5] * (v5 - *v35)));
        *v35 = v5 + 1;
      }
      else
      {
        memcpy_0(
          &piconinfo[1],
          (const void *)(*((_QWORD *)v35 + 1) + (unsigned int)(v5 * v35[5])),
          (unsigned int)v35[5]);
        HIDWORD(piconinfo[1]) = 0;
      }
      memcpy_0((void *)(*((_QWORD *)v35 + 1) + (unsigned int)(v5 * v35[5])), &piconinfo[1], (unsigned int)v35[5]);
    }
LABEL_68:
    if ( !v17 )
    {
      FillRect(*((HDC *)this + 24), &rc, *((HBRUSH *)this + 19));
      DrawIconEx(*((HDC *)this + 24), rc.left, rc.top, piconinfo[0], 0, 0, 0, 0, 3u);
    }
    v37 = (HDC)*((_QWORD *)this + 25);
    if ( v37 )
    {
      DrawIconEx(v37, rc.left, rc.top, piconinfo[0], 0, 0, 0, 0, 1u);
      if ( v16 )
        CImageList::_GenerateAlphaForImageUsingMask(this, v5, 0);
    }
    v14 = 0;
    *a4 = v5;
    goto LABEL_72;
  }
  v14 = -2147467259;
LABEL_72:
  if ( piconinfo[0] != h )
    DestroyIcon(piconinfo[0]);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180010c30  mov     r11, rsp
0x180010c33  push    rbp
0x180010c34  push    rbx
0x180010c35  push    rdi
0x180010c36  push    r15
0x180010c38  lea     rbp, [r11-28h]
0x180010c3c  sub     rsp, 108h
0x180010c43  mov     rax, cs:__security_cookie
0x180010c4a  xor     rax, rsp
0x180010c4d  mov     [rbp+20h+var_50], rax
0x180010c51  mov     [rsp+120h+var_C0], r9
0x180010c56  mov     rbx, r8
0x180010c59  mov     [rsp+120h+var_C8], rbx
0x180010c5e  xorps   xmm0, xmm0
0x180010c61  mov     qword ptr [rsp+120h+piconinfo], rbx
0x180010c66  mov     r15d, edx
0x180010c69  mov     dword ptr [rsp+120h+var_D0], edx
0x180010c6d  mov     rdi, rcx
0x180010c70  mov     dword ptr [r9], 0FFFFFFFFh
0x180010c77  movups  xmmword ptr [rbp+20h+rc.left], xmm0
0x180010c7b  cmp     edx, 0FFFFFFFFh
0x180010c7e  jl      loc_18001154E
0x180010c84  mov     [r11-28h], rsi
0x180010c88  mov     [r11-30h], r12
0x180010c8c  mov     [r11-38h], r13
0x180010c90  mov     [r11-40h], r14
0x180010c94  mov     r14d, [rcx+80h]
0x180010c9b  cmp     r14d, 10h
0x180010c9f  jz      loc_180011488
0x180010ca5  mov     r12d, [rcx+84h]
0x180010cac  lea     rdx, [rsp+120h+piconinfo+8]; piconinfo
0x180010cb1  xor     r13d, r13d
0x180010cb4  mov     rcx, rbx; hIcon
0x180010cb7  mov     qword ptr [rsp+120h+piconinfo], r13
0x180010cbc  movups  xmmword ptr [rsp+120h+piconinfo+8], xmm0
0x180010cc1  movups  xmmword ptr [rbp+20h+piconinfo+18h], xmm0
0x180010cc5  call    cs:__imp_GetIconInfo
0x180010ccb  mov     esi, 1
0x180010cd0  test    eax, eax
0x180010cd2  jz      loc_180010EBC
0x180010cd8  mov     ebx, 20h ; ' '
0x180010cdd  mov     r15d, 80004005h
0x180010ce3  mov     esi, ebx
0x180010ce5  cmp     dword ptr [rsp+120h+piconinfo+8], r13d
0x180010cea  jz      short loc_180010D14
0x180010cec  mov     rcx, qword ptr [rbp+20h+piconinfo+20h]; h
0x180010cf0  lea     r8, [rbp+20h+pv]; pv
0x180010cf4  xorps   xmm0, xmm0
0x180010cf7  mov     edx, ebx; c
0x180010cf9  movups  [rbp+20h+pv], xmm0
0x180010cfd  movups  xmmword ptr [rbp+20h+ho], xmm0
0x180010d01  call    cs:__imp_GetObjectW
0x180010d07  test    eax, eax
0x180010d09  jz      short loc_180010D14
0x180010d0b  mov     esi, dword ptr [rbp+20h+pv+4]
0x180010d0e  mov     r15d, r13d
0x180010d11  mov     ebx, dword ptr [rbp+20h+pv+8]
0x180010d14  mov     rcx, qword ptr [rbp+20h+piconinfo+18h]; ho
0x180010d18  call    cs:__imp_DeleteObject
0x180010d1e  mov     rcx, qword ptr [rbp+20h+piconinfo+20h]; ho
0x180010d22  test    rcx, rcx
0x180010d25  jz      short loc_180010D2D
0x180010d27  call    cs:__imp_DeleteObject
0x180010d2d  test    r15d, r15d
0x180010d30  js      loc_18001147E
0x180010d36  cmp     esi, r14d
0x180010d39  jz      loc_180011290
0x180010d3f  jl      loc_18001147E
0x180010d45  cmp     ebx, r12d
0x180010d48  jl      loc_18001147E
0x180010d4e  lea     r9, [rsp+120h+piconinfo+8]; ppv
0x180010d53  mov     qword ptr [rsp+120h+piconinfo+8], r13
0x180010d58  lea     r8, _GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1; riid
0x180010d5f  xor     edx, edx; punkOuter
0x180010d61  lea     rcx, CLSID_ImageList; rclsid
0x180010d68  call    ImageList_CoCreateInstance
0x180010d6d  test    eax, eax
0x180010d6f  js      loc_18001147E
0x180010d75  mov     rcx, qword ptr [rsp+120h+piconinfo+8]
0x180010d7a  mov     r15d, 1
0x180010d80  mov     dword ptr [rsp+120h+hdcSrc], r15d
0x180010d85  mov     r9d, 20021h
0x180010d8b  mov     r8d, ebx
0x180010d8e  mov     [rsp+120h+yBottom], r15d
0x180010d93  mov     edx, esi
0x180010d95  mov     rax, [rcx]
0x180010d98  mov     rax, [rax+148h]
0x180010d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010da4  mov     rbx, [rsp+120h+var_C8]
0x180010da9  test    eax, eax
0x180010dab  js      loc_180010EA1
0x180010db1  mov     rcx, qword ptr [rsp+120h+piconinfo+8]
0x180010db6  lea     r9, [rbp+20h+var_78]
0x180010dba  mov     [rbp+20h+var_78], 0FFFFFFFFh
0x180010dc1  mov     r8, rbx
0x180010dc4  mov     edx, 0FFFFFFFFh
0x180010dc9  mov     rax, [rcx]
0x180010dcc  mov     rax, [rax+20h]
0x180010dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dd5  test    eax, eax
0x180010dd7  js      loc_180010EA1
0x180010ddd  lea     r9, [rbp+20h+ppv]; ppv
0x180010de1  mov     [rbp+20h+ppv], r13
0x180010de5  lea     r8, _GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1; riid
0x180010dec  xor     edx, edx; punkOuter
0x180010dee  lea     rcx, CLSID_ImageList; rclsid
0x180010df5  call    ImageList_CoCreateInstance
0x180010dfa  test    eax, eax
0x180010dfc  js      loc_180010EA1
0x180010e02  mov     rcx, [rbp+20h+ppv]
0x180010e06  mov     r9d, 20021h
0x180010e0c  mov     dword ptr [rsp+120h+hdcSrc], r15d
0x180010e11  mov     r8d, r12d
0x180010e14  mov     edx, r14d
0x180010e17  mov     [rsp+120h+yBottom], r15d
0x180010e1c  mov     rax, [rcx]
0x180010e1f  mov     rax, [rax+148h]
0x180010e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e2b  test    eax, eax
0x180010e2d  js      short loc_180010E91
0x180010e2f  mov     rcx, [rbp+20h+ppv]
0x180010e33  mov     edx, r15d
0x180010e36  mov     rax, [rcx]
0x180010e39  mov     rax, [rax+98h]
0x180010e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e45  test    eax, eax
0x180010e47  js      short loc_180010E91
0x180010e49  mov     rcx, [rbp+20h+ppv]
0x180010e4d  xor     r9d, r9d
0x180010e50  mov     r8, qword ptr [rsp+120h+piconinfo+8]
0x180010e55  xor     edx, edx
0x180010e57  mov     dword ptr [rsp+120h+hdcSrc], r13d
0x180010e5c  mov     qword ptr [rsp+120h+yBottom], r13
0x180010e61  mov     rax, [rcx]
0x180010e64  mov     rax, [rax+158h]
0x180010e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e70  test    eax, eax
0x180010e72  js      short loc_180010E91
0x180010e74  mov     rcx, [rbp+20h+ppv]
0x180010e78  lea     r9, [rsp+120h+piconinfo]
0x180010e7d  xor     edx, edx
0x180010e7f  mov     r8d, 10000h
0x180010e85  mov     rax, [rcx]
0x180010e88  mov     rax, [rax+50h]
0x180010e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e91  mov     rcx, [rbp+20h+ppv]
0x180010e95  mov     rax, [rcx]
0x180010e98  mov     rax, [rax+10h]
0x180010e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ea1  mov     rcx, qword ptr [rsp+120h+piconinfo+8]
0x180010ea6  mov     rax, [rcx]
0x180010ea9  mov     rax, [rax+10h]
0x180010ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010eb2  mov     r15d, dword ptr [rsp+120h+var_D0]
0x180010eb7  mov     esi, 1
0x180010ebc  cmp     qword ptr [rsp+120h+piconinfo], r13
0x180010ec1  jz      loc_1800113B1
0x180010ec7  cmp     r15d, 0FFFFFFFFh
0x180010ecb  jnz     short loc_180010EF6
0x180010ecd  mov     eax, [rdi+74h]
0x180010ed0  mov     ebx, r13d
0x180010ed3  mov     ecx, [rdi+78h]
0x180010ed6  add     eax, 2
0x180010ed9  cmp     eax, ecx
0x180010edb  jg      loc_18001138C
0x180010ee1  mov     r15d, [rdi+74h]
0x180010ee5  lea     eax, [r15+1]
0x180010ee9  mov     [rdi+74h], eax
0x180010eec  cmp     r15d, 0FFFFFFFFh
0x180010ef0  jz      loc_180011238
0x180010ef6  test    r15d, r15d
0x180010ef9  js      loc_180011558
0x180010eff  cmp     r15d, [rdi+74h]
0x180010f03  jge     loc_180011558
0x180010f09  mov     eax, [rdi+84h]
0x180010f0f  lea     rcx, [rbp+20h+rc]; lprc
0x180010f13  mov     r9d, [rdi+80h]; xRight
0x180010f1a  mov     r8d, r15d
0x180010f1d  imul    r8d, eax; yTop
0x180010f21  xor     edx, edx; xLeft
0x180010f23  add     eax, r8d
0x180010f26  mov     [rsp+120h+yBottom], eax; yBottom
0x180010f2a  call    cs:__imp_SetRect
0x180010f30  mov     eax, [rdi+88h]
0x180010f36  mov     r12d, r13d
0x180010f39  and     al, 0FEh
0x180010f3b  mov     r14d, r13d
0x180010f3e  cmp     al, 20h ; ' '
0x180010f40  jnz     loc_180011141
0x180010f46  mov     rcx, qword ptr [rsp+120h+piconinfo]; hIcon
0x180010f4b  lea     rdx, [rbp+20h+pv]; piconinfo
0x180010f4f  xorps   xmm0, xmm0
0x180010f52  movups  [rbp+20h+pv], xmm0
0x180010f56  movups  xmmword ptr [rbp+20h+ho], xmm0
0x180010f5a  call    cs:__imp_GetIconInfo
0x180010f60  test    eax, eax
0x180010f62  jz      loc_180011141
0x180010f68  mov     rcx, [rdi+0C0h]; hdc
0x180010f6f  call    cs:__imp_CreateCompatibleDC
0x180010f75  mov     rsi, rax
0x180010f78  test    rax, rax
0x180010f7b  jnz     loc_1800112D2
0x180010f81  mov     eax, [rdi+88h]
0x180010f87  and     al, 0FEh
0x180010f89  cmp     al, 20h ; ' '
0x180010f8b  jnz     loc_180011338
0x180010f91  xorps   xmm0, xmm0
0x180010f94  movups  xmmword ptr [rsp+120h+piconinfo+8], xmm0
0x180010f99  cmp     r15d, [rdi+74h]
0x180010f9d  jge     loc_180011338
0x180010fa3  mov     eax, [rdi+84h]
0x180010fa9  lea     rcx, [rsp+120h+piconinfo+8]; lprc
0x180010fae  mov     r8d, [rdi+78h]
0x180010fb2  mov     esi, r15d
0x180010fb5  mov     r9d, [rdi+80h]; xRight
0x180010fbc  not     esi
0x180010fbe  add     r8d, esi
0x180010fc1  xor     edx, edx; xLeft
0x180010fc3  imul    r8d, eax; yTop
0x180010fc7  add     eax, r8d
0x180010fca  mov     [rsp+120h+yBottom], eax; yBottom
0x180010fce  call    cs:__imp_SetRect
0x180010fd4  mov     r10d, dword ptr [rsp+120h+piconinfo+0Ch]
0x180010fd9  mov     r11d, dword ptr [rsp+120h+piconinfo+14h]
0x180010fde  mov     r8d, dword ptr [rsp+120h+piconinfo+10h]
0x180010fe3  mov     ebx, dword ptr [rsp+120h+piconinfo+8]
0x180010fe7  cmp     r10d, r11d
0x180010fea  jge     loc_180011338
0x180010ff0  mov     edx, ebx
0x180010ff2  cmp     edx, r8d
0x180010ff5  jge     short loc_18001101C
0x180010ff7  mov     r9d, [rdi+80h]; xRight
0x180010ffe  mov     eax, r10d
0x180011001  imul    eax, r9d
0x180011005  add     eax, edx
0x180011007  movsxd  rcx, eax
0x18001100a  mov     rax, [rdi+0B8h]
0x180011011  cmp     byte ptr [rax+rcx*4+3], 0
0x180011016  jnz     short loc_180011021
0x180011018  inc     edx
0x18001101a  jmp     short loc_180010FF2
0x18001101c  inc     r10d
0x18001101f  jmp     short loc_180010FE7
0x180011021  mov     eax, [rdi+88h]
0x180011027  and     al, 0FEh
0x180011029  cmp     al, 20h ; ' '
0x18001102b  jnz     loc_180011127
0x180011031  xorps   xmm0, xmm0
0x180011034  movups  xmmword ptr [rsp+120h+piconinfo+8], xmm0
0x180011039  cmp     r15d, [rdi+74h]
0x18001103d  jge     short loc_180011064
0x18001103f  mov     eax, [rdi+84h]
0x180011045  lea     rcx, [rsp+120h+piconinfo+8]; lprc
0x18001104a  mov     r8d, [rdi+78h]
0x18001104e  xor     edx, edx; xLeft
0x180011050  add     r8d, esi
0x180011053  imul    r8d, eax; yTop
0x180011057  add     eax, r8d
0x18001105a  mov     [rsp+120h+yBottom], eax; yBottom
0x18001105e  call    cs:__imp_SetRect
0x180011064  mov     r11d, dword ptr [rsp+120h+piconinfo+0Ch]
0x180011069  mov     edx, dword ptr [rsp+120h+piconinfo+14h]
0x18001106d  cmp     r11d, edx
0x180011070  jge     loc_180011127
0x180011076  mov     eax, dword ptr [rsp+120h+piconinfo+10h]
0x18001107a  nop     word ptr [rax+rax+00h]
0x180011080  mov     ecx, dword ptr [rsp+120h+piconinfo+8]
0x180011084  mov     r10d, r11d
0x180011087  imul    r10d, [rdi+80h]
0x18001108f  cmp     ecx, eax
0x180011091  jge     loc_18001111B
0x180011097  nop     word ptr [rax+rax+00000000h]
0x1800110a0  lea     eax, [rcx+r10]
0x1800110a4  movsxd  rdx, eax
0x1800110a7  mov     rax, [rdi+0B8h]
0x1800110ae  lea     r9, [rax+rdx*4]
0x1800110b2  movzx   eax, byte ptr [rax+rdx*4+3]
0x1800110b7  test    al, al
0x1800110b9  jz      loc_180011288
0x1800110bf  movzx   edx, byte ptr [r9+2]
0x1800110c4  mov     r8d, eax
0x1800110c7  imul    edx, eax
0x1800110ca  mov     eax, 80808081h
0x1800110cf  sub     edx, 0FFFFFF80h
0x1800110d2  mul     edx
0x1800110d4  mov     eax, 80808081h
0x1800110d9  shr     edx, 7
0x1800110dc  mov     [r9+2], dl
0x1800110e0  movzx   edx, byte ptr [r9+1]
0x1800110e5  imul    edx, r8d
0x1800110e9  sub     edx, 0FFFFFF80h
0x1800110ec  mul     edx
0x1800110ee  mov     eax, 80808081h
0x1800110f3  shr     edx, 7
0x1800110f6  mov     [r9+1], dl
0x1800110fa  movzx   edx, byte ptr [r9]
0x1800110fe  imul    edx, r8d
0x180011102  sub     edx, 0FFFFFF80h
0x180011105  mul     edx
0x180011107  shr     edx, 7
  ... truncated ...
```
