# CLVImageListManager::DrawImageEx2(CLVDrawState *,tagLVITEMW const *,HDC__ *,int,int,ulong,uint,int,int,int)

- ea: `0x180019bfc`
- end: `0x18001a621`
- name: `?DrawImageEx2@CLVImageListManager@@QEAAIPEAVCLVDrawState@@PEBUtagLVITEMW@@PEAUHDC__@@HHKIHHH@Z`
- size: `2597`
- prototype: `unsigned int __usercall@<eax>(CLVImageListManager *__hidden this@<rcx>, struct CLVDrawState *@<rdx>, const struct tagLVITEMW *@<r8>, HDC@<r9>, int, int, unsigned int, unsigned int, int, int, int)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x180033630`
- `0x180040910`
- `0x1800f7b30`
- `0x1801c8cb0`

## callees

- `0x180019bfc`
- `0x18001a628`
- `0x18001aab0`
- `0x18002becc`
- `0x180036850`
- `0x180114520`
- `0x180114ebc`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18001a28a`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18001a2a1`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18001a28a`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18001a2a1`
- `GDI32!IntersectClipRect` at `0x18001a37f`
- `GDI32!IntersectClipRect` at `0x18001a37f`
- `GDI32!DeleteObject` at `0x18001a313`
- `GDI32!DeleteObject` at `0x18001a3cd`
- `GDI32!DeleteObject` at `0x18001a313`
- `GDI32!DeleteObject` at `0x18001a3cd`
- `GDI32!SelectClipRgn` at `0x18001a2fb`
- `GDI32!SelectClipRgn` at `0x18001a2fb`
- `GDI32!GetClipBox` at `0x18001a33a`
- `GDI32!GetClipBox` at `0x18001a33a`
- `GDI32!GetClipRgn` at `0x18001a35a`
- `GDI32!GetClipRgn` at `0x18001a35a`
- `GDI32!CreateRectRgnIndirect` at `0x18001a344`
- `GDI32!CreateRectRgnIndirect` at `0x18001a344`
- `UxTheme!__imp_DrawThemeIconEx` at `0x18001a58b`
- `UxTheme!__imp_DrawThemeIconEx` at `0x18001a58b`

## pseudocode

```c
__int64 __fastcall CLVImageListManager::DrawImageEx2(
        CLVImageListManager *this,
        struct CLVDrawState *a2,
        const struct tagLVITEMW *a3,
        HDC a4,
        int a5,
        int a6,
        unsigned int a7,
        unsigned int a8,
        int right,
        int a10,
        int a11)
{
  UINT state; // r8d
  __int64 v14; // r9
  unsigned int v15; // r15d
  __int64 v16; // rdx
  int v17; // esi
  int v18; // ebx
  char *v19; // rax
  int v20; // r14d
  int v21; // eax
  LPARAM lParam; // rax
  int v23; // r12d
  int (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // rax
  struct CLVDrawState *v25; // rdi
  HRGN v26; // rsi
  __int64 v27; // rcx
  __int64 v28; // rax
  HRESULT v29; // edi
  int (__fastcall ***v30)(_QWORD, GUID *, __int64 *); // rbx
  int v31; // ecx
  __int64 v32; // rax
  __int64 (__fastcall ***v33)(_QWORD, GUID *, __int64 *); // rbx
  HDC v34; // rbx
  int v36; // r9d
  __int64 v37; // rcx
  int v38; // r10d
  __int64 v39; // r8
  int v40; // r8d
  int v41; // r14d
  int v42; // edx
  int (__fastcall ***v43)(_QWORD, GUID *, __int64 *); // rbx
  int v44; // ebx
  int v45; // ecx
  int v46; // eax
  HRGN v47; // rax
  __int64 v48; // rcx
  __int16 v49; // ax
  int v50; // edx
  int v51; // eax
  __int64 v52; // rcx
  void *v53; // rcx
  int v54; // eax
  int v55; // r12d
  int (__fastcall ***v56)(_QWORD, GUID *, _QWORD *); // [rsp+28h] [rbp-D8h]
  unsigned int v57; // [rsp+30h] [rbp-D0h]
  __int64 *v58; // [rsp+38h] [rbp-C8h]
  char v59; // [rsp+40h] [rbp-C0h]
  unsigned int v60; // [rsp+44h] [rbp-BCh]
  int v61; // [rsp+48h] [rbp-B8h]
  int v63; // [rsp+58h] [rbp-A8h]
  int v65; // [rsp+68h] [rbp-98h]
  int (__fastcall ***v66)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-90h]
  int (__fastcall ***v68)(_QWORD, GUID *, __int64 *); // [rsp+80h] [rbp-80h]
  __int64 v69; // [rsp+88h] [rbp-78h] BYREF
  __int64 v70; // [rsp+90h] [rbp-70h] BYREF
  int (__fastcall ***v71)(_QWORD, GUID *, __int64 *); // [rsp+98h] [rbp-68h] BYREF
  unsigned int iImage; // [rsp+A0h] [rbp-60h]
  int iPartId[2]; // [rsp+A8h] [rbp-58h]
  int v74; // [rsp+B0h] [rbp-50h]
  int v75; // [rsp+B4h] [rbp-4Ch]
  int v76; // [rsp+B8h] [rbp-48h]
  _BYTE v77[12]; // [rsp+BCh] [rbp-44h] BYREF
  unsigned int v78; // [rsp+C8h] [rbp-38h]
  int v79; // [rsp+CCh] [rbp-34h]
  int v80; // [rsp+D0h] [rbp-30h]
  int v81; // [rsp+D8h] [rbp-28h]
  int v82; // [rsp+DCh] [rbp-24h]
  struct CLVDrawState *v83; // [rsp+E8h] [rbp-18h]
  char v84[24]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 *v85; // [rsp+108h] [rbp+8h]
  HRESULT v86; // [rsp+110h] [rbp+10h]
  int v87; // [rsp+114h] [rbp+14h]
  int iItem; // [rsp+118h] [rbp+18h]
  int iSubItem; // [rsp+11Ch] [rbp+1Ch]
  LPARAM v90; // [rsp+120h] [rbp+20h]
  int v91; // [rsp+128h] [rbp+28h]
  int v92; // [rsp+12Ch] [rbp+2Ch]
  int v93; // [rsp+130h] [rbp+30h]
  int v94; // [rsp+134h] [rbp+34h]
  int v95; // [rsp+138h] [rbp+38h]
  unsigned int v96; // [rsp+13Ch] [rbp+3Ch]
  __int64 v97; // [rsp+140h] [rbp+40h] BYREF
  int nNumber; // [rsp+148h] [rbp+48h] BYREF
  int v99; // [rsp+14Ch] [rbp+4Ch] BYREF
  int nDenominator; // [rsp+150h] [rbp+50h] BYREF
  int v101; // [rsp+154h] [rbp+54h] BYREF
  struct tagRECT rect; // [rsp+158h] [rbp+58h] BYREF

  state = a3->state;
  v14 = *((_QWORD *)this + 1);
  if ( (state & 8) != 0 || (v15 = 16, (state & 2) != 0 && (a8 & 0x10) != 0) )
    v15 = 8;
  if ( (a8 & 0x20) != 0 && (state & 2) != 0 )
    v15 = 256;
  if ( (*(_DWORD *)(v14 + 168) & 0x20000) != 0 )
    v15 |= 0x200000u;
  v16 = *(_QWORD *)(v14 + 472);
  if ( *(_DWORD *)v16 && (*(_DWORD *)(*(_QWORD *)(v16 + 48) + 168LL) & 0x20000) == 0 )
    v15 |= 0x10000u;
  if ( (a8 & 1) != 0 )
    return v15;
  v17 = *(_DWORD *)(v14 + 176);
  v18 = state & 0xF00;
  v61 = 0;
  if ( (v17 & 0x4000000) != 0 )
    v18 |= 0x8000u;
  v65 = v18;
  v63 = *((_DWORD *)a2 + 2);
  if ( (*(_WORD *)(v14 + 164) & 0xFFFB) != 0 )
    v19 = (char *)a2 + 56;
  else
    v19 = (char *)a2 + 64;
  v20 = *((_DWORD *)a2 + 2);
  v66 = *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))v19;
  if ( (*(_DWORD *)(v14 + 168) & 0x20000) != 0 )
    goto LABEL_28;
  if ( (v17 & 0x8000) == 0 && (!*(_DWORD *)v16 || (*(_DWORD *)(*(_QWORD *)(v16 + 48) + 168LL) & 0x20000) != 0) )
  {
    if ( (state & 8) != 0 || (a8 & 0x10) != 0 && (state & 2) != 0 )
    {
      v18 |= 4u;
      v61 = -16777216;
    }
    if ( (a8 & 0x20) != 0 && (state & 2) != 0 )
    {
      v18 |= 2u;
      v61 = -16777216;
    }
  }
  if ( (a3->state & 4) != 0 )
  {
    v18 |= 4u;
    v61 = *(_DWORD *)(*((_QWORD *)this + 1) + 180LL);
  }
  if ( (v17 & 0x10000) != 0 || *(_DWORD *)(*((_QWORD *)this + 1) + 48LL) )
  {
    if ( ((state & 0x10) != 0 || (a8 & 0x200) != 0) && (a8 & 0x800) == 0 )
    {
      v21 = a10 | 1;
      v60 = -1;
      a10 |= 1u;
    }
    else
    {
      v60 = a7;
      v21 = a10;
    }
    if ( (a8 & 0x400) != 0 && (a8 & 0x800) == 0 )
    {
      v60 = -1;
      a10 = v21 | 2;
    }
  }
  else
  {
LABEL_28:
    v60 = a7;
  }
  v70 = 0;
  memset_0(&v71, 0, 0xA8u);
  iItem = a3->iItem;
  iSubItem = a3->iSubItem;
  lParam = a3->lParam;
  v23 = right;
  v90 = lParam;
  v93 = a5;
  v94 = a6;
  v24 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)a2 + 9);
  v96 = a8;
  v25 = a2;
  v68 = v24;
  v83 = a2;
  v87 = 0;
  v95 = right;
  if ( right >= 0 )
  {
    if ( !v66 && !v24 )
      return v15;
    rect = 0;
    GetClipBox(a4, &rect);
    v47 = CreateRectRgnIndirect(&rect);
    v26 = v47;
    if ( v47 && GetClipRgn(a4, v47) <= 0 )
    {
      DeleteObject(v26);
      v26 = 0;
    }
    v59 = 1;
    IntersectClipRect(a4, rect.left, rect.top, right, rect.bottom);
  }
  else
  {
    v26 = 0;
    v59 = 0;
  }
  if ( !v66 )
    goto LABEL_56;
  v27 = *((_QWORD *)this + 1);
  v28 = *(_QWORD *)(v27 + 344);
  if ( *(_QWORD *)(v28 + 8) || *(_QWORD *)(v28 + 56) )
    v60 = -1;
  LODWORD(v70) = 88;
  v71 = v66;
  *(_QWORD *)&v77[4] = 0;
  iImage = a3->iImage;
  *(_QWORD *)iPartId = a4;
  v78 = v60;
  v79 = v61;
  v81 = a10;
  v82 = a11;
  v80 = v18;
  if ( (*(_DWORD *)(v27 + 176) & 0x4000000) != 0 )
    v80 = v18 | 0x8000;
  while ( 1 )
  {
    while ( 1 )
    {
      v29 = 0;
      v30 = v71;
      v74 = v93;
      v75 = v94;
      v31 = *((_DWORD *)v83 + 2);
      v76 = v31;
      *(_DWORD *)v77 = *((_DWORD *)v83 + 3);
      v97 = 0;
      if ( v71 )
      {
        if ( (unsigned int)CImageListBase::IsValid((CImageListBase *)((unsigned __int64)(v71 - 2)
                                                                    & -(__int64)(v71 != (int (__fastcall ***)(_QWORD, GUID *, __int64 *))8)))
          && (**v30)(v30, &GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1, &v97) >= 0 )
        {
          v32 = *((_QWORD *)this + 1);
          nNumber = 0;
          v99 = 0;
          v29 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, int *, int *, int (__fastcall ***)(_QWORD, GUID *, _QWORD *), unsigned int, __int64 *))(*(_QWORD *)v97 + 264LL))(
                  v97,
                  iImage,
                  (*(_DWORD *)(v32 + 176) >> 26) & 1,
                  &nNumber,
                  &v99,
                  v56,
                  v57,
                  v58);
          if ( v29 >= 0 )
          {
            v43 = v71;
            nDenominator = 0;
            v101 = 0;
            v69 = 0;
            if ( v71
              && (unsigned int)CImageListBase::IsValid((CImageListBase *)((unsigned __int64)(v71 - 2)
                                                                        & -(__int64)(v71 != (int (__fastcall ***)(_QWORD, GUID *, __int64 *))8)))
              && (**v43)(v43, &GUID_46eb5926_582e_4017_9fdf_e8998daa0950, &v69) >= 0 )
            {
              v44 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v69 + 128LL))(
                      v69,
                      &nDenominator,
                      &v101);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
              if ( !v44 )
              {
                nNumber = MulDiv(nNumber, *((_DWORD *)v83 + 2), nDenominator);
                v45 = MulDiv(v99, *((_DWORD *)v83 + 3), v101);
                v99 = v45;
                v74 += (*((_DWORD *)v83 + 2) - nNumber) / 2;
                v46 = *((_DWORD *)v83 + 3) - v45;
                if ( (v96 & 0x1000) == 0 )
                  v46 /= 2;
                v75 += v46;
                v76 = nNumber;
                *(_DWORD *)v77 = v45;
              }
            }
            else
            {
              nDenominator = 0;
              v101 = 0;
            }
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v97 + 16LL))(v97);
        }
        v31 = v76;
      }
      if ( v29 != -2147483638 )
        v29 = 0;
      if ( v31 <= v95 - v74 && (*(_DWORD *)this || (*(_BYTE *)(*((_QWORD *)this + 1) + 156LL) & 1) != 0) )
        v80 |= 0x2000u;
      if ( v29 >= 0 )
      {
        if ( v31 <= 0 )
          goto LABEL_54;
        if ( (v81 & 1) != 0
          && CListView::IsExtendedTileView(*((CListView **)this + 1))
          && (v53 = *(void **)(*(_QWORD *)(v52 + 472) + 24LL)) != 0 )
        {
          v58 = &v70;
          v57 = iImage;
          v56 = v71;
          v29 = DrawThemeIconEx(v53, iPartId[0], 0, 0, 0);
        }
        else
        {
          v33 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v71;
          v69 = 0;
          if ( v71
            && (unsigned int)CImageListBase::IsValid((CImageListBase *)((unsigned __int64)(v71 - 2)
                                                                      & -(__int64)(v71 != (int (__fastcall ***)(_QWORD, GUID *, __int64 *))8))) )
          {
            v29 = (**v33)(v33, &GUID_46eb5926_582e_4017_9fdf_e8998daa0950, &v69);
            if ( v29 >= 0 )
            {
              v29 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v69 + 64LL))(v69, &v70);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
            }
          }
          else
          {
            v29 = -2147467261;
          }
        }
      }
      if ( v29 == -2147483638 )
        goto LABEL_102;
      if ( v29 < 0 )
        goto LABEL_55;
LABEL_54:
      if ( !v29 )
        goto LABEL_55;
LABEL_102:
      v48 = *((_QWORD *)this + 1);
      v85 = &v70;
      v92 = iImage;
      v86 = v29;
      v91 = 0;
      CCSendNotify(v48 + 96, 4294967110LL, v84);
      if ( v91 )
        break;
      if ( v86 != -2147483638 )
        goto LABEL_55;
      v80 &= ~0x8000u;
    }
    if ( v91 != 2 || v92 < 0 )
      break;
    iImage = v92;
  }
LABEL_55:
  v20 = v63;
  v23 = right;
  v25 = a2;
LABEL_56:
  if ( v68
    && (v36 = (unsigned __int8)HIBYTE(LOWORD(a3->state)) >> 4) != 0
    && (!a3->iSubItem || (*(_BYTE *)(*((_QWORD *)this + 1) + 176LL) & 2) != 0)
    && ((v37 = *((_QWORD *)this + 1), v38 = *(_DWORD *)(v37 + 176), (v38 & 0x8000000) == 0)
     || (a3->state & 2) != 0
     || (v39 = *(_QWORD *)(v37 + 384), *(_DWORD *)(v39 + 16) == a3->iItem)
     && ((*(_DWORD *)(v37 + 160) & 2) == 0
      || *(_WORD *)(v37 + 164) == 3
      || !*(_QWORD *)(v37 + 744)
      || *(_DWORD *)(v39 + 20) == a3->iGroup)) )
  {
    v40 = *((_DWORD *)v25 + 6);
    if ( (v38 & 0x100000) != 0 && (*(_WORD *)(v37 + 164) & 0xFFFB) == 0 )
    {
      v41 = a5 + v20 - v40;
LABEL_78:
      v42 = 0;
      goto LABEL_79;
    }
    if ( (*(_DWORD *)(v37 + 176) & 0x8000000) != 0 && (*(_WORD *)(v37 + 164) & 0xFFFB) == 0 )
    {
      v41 = a5;
      goto LABEL_78;
    }
    v42 = 0;
    v41 = a5 - v40 - 3;
    if ( v66 )
    {
      v49 = *(_WORD *)(v37 + 164);
      if ( v49 == 4 )
      {
        v54 = *(_DWORD *)(*(_QWORD *)(v37 + 648) + 32LL);
        if ( v54 >= *((_DWORD *)v25 + 3) )
          v54 = *((_DWORD *)v25 + 3);
      }
      else
      {
        v50 = *((_DWORD *)v25 + 3);
        if ( v49 != 1 )
        {
          v51 = v50 - *((_DWORD *)v25 + 7);
LABEL_118:
          v42 = v51 / 2;
          goto LABEL_79;
        }
        v54 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v37 + 640) + 16LL) + 64LL);
        if ( v54 >= v50 )
          v54 = *((_DWORD *)v25 + 3);
      }
      v51 = v54 - *((_DWORD *)v25 + 7);
      goto LABEL_118;
    }
LABEL_79:
    if ( v23 >= 0 )
    {
      v55 = v23 - v41;
      if ( v40 >= v55 )
        v40 = v55;
    }
    v71 = v68;
    v34 = a4;
    iImage = v36 - 1;
    v76 = v40;
    v75 = v42 + a6;
    v78 = v60;
    v79 = v61;
    v80 = v65;
    memset(v77, 0, sizeof(v77));
    v82 = 0;
    v81 = a10;
    LODWORD(v70) = 88;
    *(_QWORD *)iPartId = a4;
    v74 = v41;
    CLVImageListManager::DrawAsync(this, (struct LVDRAWASYNCPARAMS *)&v70, 0);
  }
  else
  {
    v34 = a4;
  }
  if ( v59 )
    SelectClipRgn(v34, v26);
  if ( v26 )
    DeleteObject(v26);
  return v15;
}

```

## disassembly

```asm
0x180019bfc  push    rbp
0x180019bfe  push    rbx
0x180019bff  push    rsi
0x180019c00  push    rdi
0x180019c01  push    r12
0x180019c03  push    r13
0x180019c05  push    r14
0x180019c07  push    r15
0x180019c09  lea     rbp, [rsp-78h]
0x180019c0e  sub     rsp, 178h
0x180019c15  mov     rax, cs:__security_cookie
0x180019c1c  xor     rax, rsp
0x180019c1f  mov     [rbp+0B0h+var_48], rax
0x180019c23  mov     edi, [rbp+0B0h+arg_38]
0x180019c29  mov     r12, r8
0x180019c2c  mov     [rsp+1B0h+var_138], r8
0x180019c31  mov     r13, rcx
0x180019c34  mov     r8d, [r8+0Ch]
0x180019c38  mov     r11d, r8d
0x180019c3b  mov     [rsp+1B0h+hdc], r9
0x180019c40  mov     r9, [rcx+8]
0x180019c44  mov     [rsp+1B0h+var_150], rdx
0x180019c49  mov     edx, 2
0x180019c4e  and     r11d, 8
0x180019c52  jnz     loc_18001A3AC
0x180019c58  test    dl, r8b
0x180019c5b  lea     r15d, [rdx+0Eh]
0x180019c5f  setnz   cl
0x180019c62  test    r15b, dil
0x180019c65  setnz   al
0x180019c68  test    al, cl
0x180019c6a  jnz     loc_18001A3AC
0x180019c70  mov     r10d, edi
0x180019c73  and     r10d, 20h
0x180019c77  jnz     loc_18001A2E4
0x180019c7d  mov     ecx, [r9+0A8h]
0x180019c84  mov     ebx, 20000h
0x180019c89  and     ecx, ebx
0x180019c8b  jz      short loc_180019C92
0x180019c8d  bts     r15d, 15h
0x180019c92  mov     rdx, [r9+1D8h]
0x180019c99  cmp     dword ptr [rdx], 0
0x180019c9c  jz      short loc_180019CAF
0x180019c9e  mov     rax, [rdx+30h]
0x180019ca2  test    [rax+0A8h], ebx
0x180019ca8  jnz     short loc_180019CAF
0x180019caa  bts     r15d, 10h
0x180019caf  test    dil, 1
0x180019cb3  jnz     loc_18001A074
0x180019cb9  mov     esi, [r9+0B0h]
0x180019cc0  mov     ebx, r8d
0x180019cc3  and     ebx, 0F00h
0x180019cc9  mov     [rsp+1B0h+var_168], 0
0x180019cd1  bt      esi, 1Ah
0x180019cd5  jnb     short loc_180019CDB
0x180019cd7  bts     ebx, 0Fh
0x180019cdb  mov     rax, [rsp+1B0h+var_150]
0x180019ce0  mov     [rsp+1B0h+var_148], ebx
0x180019ce4  mov     r14d, [rax+8]
0x180019ce8  mov     [rsp+1B0h+var_158], r14d
0x180019ced  mov     r14d, 0FFFBh
0x180019cf3  test    [r9+0A4h], r14w
0x180019cfb  jnz     loc_18001A4F1
0x180019d01  add     rax, 40h ; '@'
0x180019d05  mov     rax, [rax]
0x180019d08  xor     r9d, r9d
0x180019d0b  mov     r14d, [rsp+1B0h+var_158]
0x180019d10  mov     [rsp+1B0h+var_140], rax
0x180019d15  test    ecx, ecx
0x180019d17  jnz     loc_180019DA3
0x180019d1d  bt      esi, 0Fh
0x180019d21  jb      short loc_180019D40
0x180019d23  cmp     [rdx], r9d
0x180019d26  jz      loc_18001A097
0x180019d2c  mov     rax, [rdx+30h]
0x180019d30  test    dword ptr [rax+0A8h], 20000h
0x180019d3a  jnz     loc_18001A097
0x180019d40  mov     ecx, 4
0x180019d45  test    [r12+0Ch], cl
0x180019d4a  jnz     loc_18001A442
0x180019d50  bt      esi, 10h
0x180019d54  jnb     short loc_180019D99
0x180019d56  test    r8b, 10h
0x180019d5a  jnz     loc_18001A514
0x180019d60  bt      edi, 9
0x180019d64  jb      loc_18001A514
0x180019d6a  mov     eax, [rbp+0B0h+arg_30]
0x180019d70  mov     [rsp+1B0h+var_16C], eax
0x180019d74  mov     eax, [rbp+0B0h+arg_48]
0x180019d7a  bt      edi, 0Ah
0x180019d7e  jnb     short loc_180019DAD
0x180019d80  bt      edi, 0Bh
0x180019d84  jb      short loc_180019DAD
0x180019d86  or      eax, 2
0x180019d89  mov     [rsp+1B0h+var_16C], 0FFFFFFFFh
0x180019d91  mov     [rbp+0B0h+arg_48], eax
0x180019d97  jmp     short loc_180019DAD
0x180019d99  mov     rax, [r13+8]
0x180019d9d  cmp     [rax+30h], r9d
0x180019da1  jnz     short loc_180019D56
0x180019da3  mov     eax, [rbp+0B0h+arg_30]
0x180019da9  mov     [rsp+1B0h+var_16C], eax
0x180019dad  xor     edx, edx; Val
0x180019daf  mov     [rbp+0B0h+var_120], r9
0x180019db3  mov     r8d, 0A8h; Size
0x180019db9  lea     rcx, [rbp+0B0h+var_118]; void *
0x180019dbd  call    memset_0
0x180019dc2  mov     eax, [r12+4]
0x180019dc7  mov     rdx, [rsp+1B0h+var_150]
0x180019dcc  mov     [rbp+0B0h+var_98], eax
0x180019dcf  mov     eax, [r12+8]
0x180019dd4  mov     [rbp+0B0h+var_94], eax
0x180019dd7  mov     rax, [r12+28h]
0x180019ddc  mov     r12d, [rbp+0B0h+right]
0x180019de3  mov     [rbp+0B0h+var_90], rax
0x180019de7  mov     eax, [rbp+0B0h+arg_20]
0x180019ded  mov     [rbp+0B0h+var_80], eax
0x180019df0  mov     eax, [rbp+0B0h+arg_28]
0x180019df6  mov     [rbp+0B0h+var_7C], eax
0x180019df9  mov     rax, [rdx+48h]
0x180019dfd  mov     [rbp+0B0h+var_74], edi
0x180019e00  mov     rdi, rdx
0x180019e03  mov     [rbp+0B0h+var_130], rax
0x180019e07  mov     [rbp+0B0h+var_C8], rdx
0x180019e0b  mov     [rbp+0B0h+var_9C], 0
0x180019e12  mov     [rbp+0B0h+var_78], r12d
0x180019e16  test    r12d, r12d
0x180019e19  jns     loc_18001A31E
0x180019e1f  xor     esi, esi
0x180019e21  mov     [rsp+1B0h+var_170], sil
0x180019e26  mov     rdx, [rsp+1B0h+var_140]
0x180019e2b  test    rdx, rdx
0x180019e2e  jz      loc_18001A052
0x180019e34  mov     rcx, [r13+8]
0x180019e38  mov     rax, [rcx+158h]
0x180019e3f  cmp     qword ptr [rax+8], 0
0x180019e44  jnz     loc_18001A435
0x180019e4a  cmp     qword ptr [rax+38h], 0
0x180019e4f  jnz     loc_18001A435
0x180019e55  mov     rax, [rsp+1B0h+var_138]
0x180019e5a  mov     dword ptr [rbp+0B0h+var_120], 58h ; 'X'
0x180019e61  mov     [rbp+0B0h+var_118], rdx
0x180019e65  mov     [rbp+0B0h+var_F4+4], 0
0x180019e6d  mov     eax, [rax+24h]
0x180019e70  mov     [rbp+0B0h+var_110], eax
0x180019e73  mov     rax, [rsp+1B0h+hdc]
0x180019e78  mov     qword ptr [rbp+0B0h+iPartId], rax
0x180019e7c  mov     eax, [rsp+1B0h+var_16C]
0x180019e80  mov     [rbp+0B0h+var_E8], eax
0x180019e83  mov     eax, [rsp+1B0h+var_168]
0x180019e87  mov     [rbp+0B0h+var_E4], eax
0x180019e8a  mov     eax, [rbp+0B0h+arg_48]
0x180019e90  mov     [rbp+0B0h+var_D8], eax
0x180019e93  mov     eax, [rbp+0B0h+arg_50]
0x180019e99  mov     [rbp+0B0h+var_D4], eax
0x180019e9c  mov     [rbp+0B0h+var_E0], ebx
0x180019e9f  test    dword ptr [rcx+0B0h], 4000000h
0x180019ea9  jz      short loc_180019EB2
0x180019eab  bts     ebx, 0Fh
0x180019eaf  mov     [rbp+0B0h+var_E0], ebx
0x180019eb2  mov     r12d, 2
0x180019eb8  lea     r14d, [r12-1]
0x180019ebd  mov     eax, [rbp+0B0h+var_80]
0x180019ec0  xor     edi, edi
0x180019ec2  mov     rbx, [rbp+0B0h+var_118]
0x180019ec6  mov     [rbp+0B0h+var_100], eax
0x180019ec9  mov     eax, [rbp+0B0h+var_7C]
0x180019ecc  mov     [rbp+0B0h+var_FC], eax
0x180019ecf  mov     rax, [rbp+0B0h+var_C8]
0x180019ed3  mov     ecx, [rax+8]
0x180019ed6  mov     [rbp+0B0h+var_F8], ecx
0x180019ed9  mov     eax, [rax+0Ch]
0x180019edc  mov     dword ptr [rbp+0B0h+var_F4], eax
0x180019edf  mov     [rbp+0B0h+var_70], rdi
0x180019ee3  test    rbx, rbx
0x180019ee6  jz      loc_180019F7E
0x180019eec  lea     rdx, [rbx-10h]
0x180019ef0  lea     rax, [rbx-8]
0x180019ef4  neg     rax
0x180019ef7  sbb     rcx, rcx
0x180019efa  and     rcx, rdx; this
0x180019efd  call    ?IsValid@CImageListBase@@QEAAHXZ; CImageListBase::IsValid(void)
0x180019f02  test    eax, eax
0x180019f04  jz      short loc_180019F7B
0x180019f06  mov     rax, [rbx]
0x180019f09  lea     r8, [rbp+0B0h+var_70]
0x180019f0d  lea     rdx, _GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1
0x180019f14  mov     rcx, rbx
0x180019f17  mov     rax, [rax]
0x180019f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f1f  test    eax, eax
0x180019f21  js      short loc_180019F7B
0x180019f23  mov     r10, [rbp+0B0h+var_70]
0x180019f27  lea     r9, [rbp+0B0h+nNumber]
0x180019f2b  mov     rax, [r13+8]
0x180019f2f  mov     edx, [rbp+0B0h+var_110]
0x180019f32  mov     [rbp+0B0h+nNumber], edi
0x180019f35  mov     [rbp+0B0h+var_64], edi
0x180019f38  mov     rcx, [r10]
0x180019f3b  mov     r8d, [rax+0B0h]
0x180019f42  shr     r8d, 1Ah
0x180019f46  and     r8d, r14d
0x180019f49  mov     rax, [rcx+108h]
0x180019f50  lea     rcx, [rbp+0B0h+var_64]
0x180019f54  mov     qword ptr [rsp+1B0h+bottom], rcx
0x180019f59  mov     rcx, r10
0x180019f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f61  mov     edi, eax
0x180019f63  test    eax, eax
0x180019f65  jns     loc_18001A1E5
0x180019f6b  mov     rcx, [rbp+0B0h+var_70]
0x180019f6f  mov     rax, [rcx]
0x180019f72  mov     rax, [rax+10h]
0x180019f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f7b  mov     ecx, [rbp+0B0h+var_F8]
0x180019f7e  xor     eax, eax
0x180019f80  cmp     edi, 8000000Ah
0x180019f86  cmovnz  edi, eax
0x180019f89  mov     eax, [rbp+0B0h+var_78]
0x180019f8c  sub     eax, [rbp+0B0h+var_100]
0x180019f8f  cmp     ecx, eax
0x180019f91  jle     loc_18001A38A
0x180019f97  test    edi, edi
0x180019f99  js      loc_18001A029
0x180019f9f  test    ecx, ecx
0x180019fa1  jle     loc_18001A039
0x180019fa7  test    byte ptr [rbp+0B0h+var_D8], r14b
0x180019fab  jnz     loc_18001A53A
0x180019fb1  mov     rbx, [rbp+0B0h+var_118]
0x180019fb5  mov     [rbp+0B0h+var_128], 0
0x180019fbd  test    rbx, rbx
0x180019fc0  jz      loc_18001A306
0x180019fc6  lea     rdx, [rbx-10h]
0x180019fca  lea     rax, [rbx-8]
0x180019fce  neg     rax
0x180019fd1  sbb     rcx, rcx
0x180019fd4  and     rcx, rdx; this
0x180019fd7  call    ?IsValid@CImageListBase@@QEAAHXZ; CImageListBase::IsValid(void)
0x180019fdc  test    eax, eax
0x180019fde  jz      loc_18001A306
0x180019fe4  mov     rax, [rbx]
0x180019fe7  lea     r8, [rbp+0B0h+var_128]
0x180019feb  lea     rdx, _GUID_46eb5926_582e_4017_9fdf_e8998daa0950
0x180019ff2  mov     rcx, rbx
0x180019ff5  mov     rax, [rax]
0x180019ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ffd  mov     edi, eax
0x180019fff  test    eax, eax
0x18001a001  js      short loc_18001A029
0x18001a003  mov     rcx, [rbp+0B0h+var_128]
0x18001a007  lea     rdx, [rbp+0B0h+var_120]
0x18001a00b  mov     rax, [rcx]
0x18001a00e  mov     rax, [rax+40h]
0x18001a012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a017  mov     rcx, [rbp+0B0h+var_128]
0x18001a01b  mov     edi, eax
0x18001a01d  mov     rax, [rcx]
0x18001a020  mov     rax, [rax+10h]
0x18001a024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a029  cmp     edi, 8000000Ah
0x18001a02f  jz      loc_18001A3D7
0x18001a035  test    edi, edi
0x18001a037  js      short loc_18001A041
0x18001a039  test    edi, edi
0x18001a03b  jnz     loc_18001A3D7
0x18001a041  mov     r14d, [rsp+1B0h+var_158]
0x18001a046  mov     r12d, [rbp+0B0h+right]
0x18001a04d  mov     rdi, [rsp+1B0h+var_150]
0x18001a052  mov     rbx, [rbp+0B0h+var_130]
0x18001a056  test    rbx, rbx
0x18001a059  jnz     short loc_18001A0CE
0x18001a05b  mov     rbx, [rsp+1B0h+hdc]
0x18001a060  cmp     [rsp+1B0h+var_170], 0
0x18001a065  jnz     loc_18001A2F5
0x18001a06b  test    rsi, rsi
0x18001a06e  jnz     loc_18001A310
0x18001a074  mov     eax, r15d
0x18001a077  mov     rcx, [rbp+0B0h+var_48]
0x18001a07b  xor     rcx, rsp; StackCookie
0x18001a07e  call    __security_check_cookie
0x18001a083  add     rsp, 178h
0x18001a08a  pop     r15
0x18001a08c  pop     r14
0x18001a08e  pop     r13
0x18001a090  pop     r12
0x18001a092  pop     rdi
0x18001a093  pop     rsi
0x18001a094  pop     rbx
0x18001a095  pop     rbp
0x18001a096  retn
0x18001a097  mov     eax, 0FF000000h
0x18001a09c  test    r11d, r11d
0x18001a09f  jnz     loc_18001A508
0x18001a0a5  test    dil, 10h
0x18001a0a9  jnz     loc_18001A4FA
0x18001a0af  test    r10d, r10d
0x18001a0b2  jz      loc_180019D40
0x18001a0b8  test    r8b, 2
0x18001a0bc  jz      loc_180019D40
0x18001a0c2  or      ebx, 2
  ... truncated ...
```
