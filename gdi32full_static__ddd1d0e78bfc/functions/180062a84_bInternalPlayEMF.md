# bInternalPlayEMF

- ea: `0x180062a84`
- end: `0x1800635b2`
- name: `bInternalPlayEMF`
- size: `2862`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x180062a40`
- `0x18006e760`

## callees

- `0x180016350`
- `0x180018720`
- `0x180018860`
- `0x180018a20`
- `0x180018c30`
- `0x180018f00`
- `0x180018fe0`
- `0x18002c2ec`
- `0x18002c5a0`
- `0x18002e040`
- `0x180032f20`
- `0x180056860`
- `0x180057410`
- `0x180057ba8`
- `0x18005d394`
- `0x180061404`
- `0x180062a84`
- `0x180063600`
- `0x18006c0e0`
- `0x18006eb5c`
- `0x1800756cc`
- `0x18007f800`
- `0x1800a8010`

## import_xrefs

- `GDI32!GetClipBox` at `0x180063041`
- `GDI32!GetClipBox` at `0x180063041`
- `GDI32!GetDeviceCaps` at `0x180063076`
- `GDI32!GetDeviceCaps` at `0x180063091`
- `GDI32!GetDeviceCaps` at `0x1800630b0`
- `GDI32!GetDeviceCaps` at `0x1800630cb`
- `GDI32!GetDeviceCaps` at `0x180063076`
- `GDI32!GetDeviceCaps` at `0x180063091`
- `GDI32!GetDeviceCaps` at `0x1800630b0`
- `GDI32!GetDeviceCaps` at `0x1800630cb`
- `GDI32!RestoreDC` at `0x18006353d`
- `GDI32!RestoreDC` at `0x18006353d`
- `GDI32!SaveDC` at `0x180062c26`
- `GDI32!SaveDC` at `0x180062c26`
- `GDI32!SetWorldTransform` at `0x180063023`
- `GDI32!SetWorldTransform` at `0x180063023`
- `GDI32!GdiGetEntry` at `0x180062b0d`
- `GDI32!GdiGetEntry` at `0x180062b0d`
- `GDI32!gW32PID` at `0x180062b3b`
- `GDI32!gCookie` at `0x180062b55`
- `GDI32!gMaxGdiHandleCount` at `0x180062ae4`
- `GDI32!pldcGet` at `0x1800632b4`
- `GDI32!pldcGet` at `0x1800632b4`
- `GDI32!GdiSetLastError` at `0x180063243`
- `GDI32!GdiSetLastError` at `0x180063259`
- `GDI32!GdiSetLastError` at `0x180063243`
- `GDI32!GdiSetLastError` at `0x180063259`
- `GDI32!DeleteObject` at `0x18006357a`
- `GDI32!DeleteObject` at `0x18006357a`
- `win32u!NtGdiGetTransform` at `0x180062e06`
- `win32u!NtGdiGetTransform` at `0x180062e06`
- `win32u!NtGdiSetSizeDevice` at `0x180063197`
- `win32u!NtGdiSetSizeDevice` at `0x180063197`
- `win32u!NtGdiSetVirtualResolution` at `0x180063165`
- `win32u!NtGdiSetVirtualResolution` at `0x180063165`

## pseudocode

```c
__int64 __fastcall bInternalPlayEMF(
        HDC hdc,
        __int64 a2,
        unsigned int (__fastcall *a3)(HDC, struct tagHANDLETABLE *, struct tagENHMETARECORD *, __int64, __int64),
        __int64 a4,
        int *a5)
{
  unsigned int v8; // eax
  __int64 v9; // r15
  __int64 v10; // rax
  __int64 v11; // r14
  struct tagENHMETAHEADER *v12; // rsi
  unsigned int nSize; // eax
  unsigned int v14; // r15d
  int v15; // r12d
  struct tagENHMETARECORD *v16; // r13
  void *v17; // rdx
  LONG left; // eax
  int v19; // ecx
  LONG v20; // r8d
  LONG right; // edx
  int v22; // eax
  float v23; // xmm7_4
  LONG top; // r8d
  LONG bottom; // edx
  int v26; // eax
  float v27; // xmm6_4
  float v28; // xmm3_4
  float v29; // xmm5_4
  float v30; // xmm4_4
  float v31; // xmm2_4
  float v32; // xmm1_4
  float v33; // xmm0_4
  float v34; // xmm4_4
  float v35; // xmm3_4
  float v36; // xmm0_4
  float v37; // xmm5_4
  float v38; // xmm4_4
  XFORM *v39; // rdx
  float v40; // xmm0_4
  int v41; // r8d
  float DeviceCaps; // xmm7_4
  float v43; // xmm7_4
  float v44; // xmm6_4
  float v45; // xmm6_4
  float v46; // xmm2_4
  float v47; // xmm1_4
  int v48; // ecx
  int v49; // eax
  BOOL v50; // eax
  struct tagHANDLETABLE *v51; // rdx
  __int64 nHandles; // r9
  unsigned int v53; // eax
  unsigned int v54; // ecx
  bool v55; // zf
  unsigned int (__fastcall *v56)(HDC, struct tagHANDLETABLE *, struct tagENHMETARECORD *, __int64, __int64); // rax
  unsigned int i; // edi
  void *v58; // rcx
  int cx; // [rsp+38h] [rbp-A1h]
  int v60; // [rsp+38h] [rbp-A1h]
  unsigned int v61; // [rsp+3Ch] [rbp-9Dh]
  unsigned int v62; // [rsp+3Ch] [rbp-9Dh]
  DWORD l; // [rsp+40h] [rbp-99h]
  int v64; // [rsp+44h] [rbp-95h]
  int v65; // [rsp+48h] [rbp-91h]
  int v67; // [rsp+58h] [rbp-81h]
  __int64 v68; // [rsp+60h] [rbp-79h]
  int v69; // [rsp+68h] [rbp-71h]
  int cy; // [rsp+6Ch] [rbp-6Dh]
  int v71; // [rsp+70h] [rbp-69h]
  int v72; // [rsp+74h] [rbp-65h]
  int v73; // [rsp+78h] [rbp-61h]
  int v74; // [rsp+7Ch] [rbp-5Dh]
  _DWORD *v76; // [rsp+88h] [rbp-51h]
  ENHMETARECORD point; // [rsp+90h] [rbp-49h] BYREF
  __int128 v78; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v79; // [rsp+B0h] [rbp-29h]

  if ( gbDisableMetaFiles )
    return 1;
  v8 = HANDLE_TO_INDEX(hdc);
  v9 = 0;
  v68 = 0;
  if ( v8 < gMaxGdiHandleCount )
  {
    v79 = 0;
    v78 = 0;
    if ( (int)GdiGetEntry(v8, &v78) >= 0
      && BYTE14(v78) == 1
      && WORD6(v78) == WORD1(hdc)
      && (DWORD2(v78) & 0xFFFFFFFE) == gW32PID
      && v79 )
    {
      v9 = gCookie ^ __ROR8__(v79, 64 - (gCookie & 0x3Fu));
      v68 = v9;
    }
  }
  v10 = pvClientObjGet(a2, 4587520);
  v11 = v10;
  if ( !v10 )
    return 0;
  v12 = *(struct tagENHMETAHEADER **)(v10 + 48);
  v76 = (_DWORD *)(v10 + 40);
  if ( !v12 )
    return 0;
  nSize = v12->nSize;
  if ( nSize < 0x58 )
    return 0;
  if ( v12->nBytes < nSize )
    return 0;
  **(_QWORD **)(v11 + 688) = a2;
  *(_DWORD *)(v11 + 700) = 1;
  *(_DWORD *)(v11 + 696) = 0;
  *(struct _RECTL *)(v11 + 140) = rclInfinity;
  v61 = ComputeBaseHeaderSize(v12);
  if ( v61 >= 0x64 && v12->bOpenGL && !(unsigned int)LoadOpenGL() )
    return 0;
  v64 = 0;
  if ( !hdc )
  {
    v65 = 0;
    l = -1;
LABEL_89:
    v60 = 0;
    v14 = 1;
    pldcGet(hdc);
    v62 = 0;
    v16 = EMFContainer::ObtainRecordPtr((EMFContainer *)(v11 + 40), 0);
    if ( v16 )
    {
      while ( 1 )
      {
        v17 = (void *)v16->nSize;
        if ( (unsigned int)v17 + v62 < v62
          || (unsigned int)v17 + v62 > v12->nBytes
          || (char *)v16 + (unsigned __int64)v17 < (char *)v16 )
        {
          break;
        }
        if ( v16->iType == 14 )
        {
          v15 = 0;
          goto LABEL_119;
        }
        if ( hdc && (*(_DWORD *)(v68 + 152) & 0x800) == 0 )
          break;
        if ( v64 )
        {
          if ( v16->iType - 102 <= 1 )
          {
            if ( !v60 )
            {
              v50 = *(&xmmword_1800FD800 + 1) && ((unsigned int (__fastcall *)(HDC))*(&xmmword_1800FD800 + 1))(hdc);
              v60 = 1;
              goto LABEL_110;
            }
          }
          else if ( v60 )
          {
            v50 = *((_QWORD *)&xmmword_1800FD810 + 1)
               && (*((unsigned int (__fastcall **)(HDC))&xmmword_1800FD810 + 1))(hdc);
            v60 = 0;
LABEL_110:
            v14 &= -v50;
          }
        }
        v51 = *(struct tagHANDLETABLE **)(v11 + 688);
        nHandles = v12->nHandles;
        if ( a3 )
        {
          if ( !a3(hdc, v51, v16, nHandles, a4) )
            break;
        }
        else
        {
          v14 &= -PlayEnhMetaFileRecord(hdc, v51, v16, nHandles);
        }
        if ( (*(_DWORD *)(v11 + 680) & 0x8000) == 0 )
        {
          if ( v16->nSize )
          {
            v53 = v16->nSize + v62;
            v62 = v53;
            if ( v53 < v12->nBytes )
            {
              --*(_DWORD *)(v11 + 40);
              v16 = EMFContainer::ObtainRecordPtr((EMFContainer *)(v11 + 40), v53);
              if ( v16 )
                continue;
            }
          }
        }
        break;
      }
    }
    v15 = 1;
    v14 = 0;
    goto LABEL_119;
  }
  if ( !a5 )
    goto LABEL_86;
  if ( !SaveDC(hdc) )
    return 0;
  if ( !v9 )
  {
LABEL_86:
    GdiSetLastError(87);
    return 0;
  }
  v14 = 0;
  v15 = 1;
  v16 = 0;
  v65 = *(_DWORD *)(v68 + 152) & 0x800;
  *(_DWORD *)(v68 + 152) |= 0x800u;
  l = SetLayout(hdc, 0);
  if ( SetGraphicsMode(hdc, 2) && SetMetaRgn(hdc) && (unsigned int)bMetaResetDC(hdc) )
  {
    if ( l != -1 && (l & 1) != 0 )
      GetAndSetDCDWord((_DWORD)hdc, 9, 2, 123, 123, 0);
    v79 = 0;
    *(_QWORD *)&point.iType = 0;
    left = v12->rclFrame.left;
    v78 = 0;
    if ( v12->rclFrame.right < left || v12->rclFrame.bottom < v12->rclFrame.top )
    {
      GdiSetLastError(13);
      goto LABEL_119;
    }
    if ( v61 < 0x64
      || !v12->bOpenGL
      || (v17 = EMFContainer::ObtainPtr((EMFContainer *)(v11 + 40), 0, v12->nBytes)) != 0
      && (!xmmword_1800FD800 || !(unsigned int)xmmword_1800FD800(hdc, v17, a5) ? (v19 = 0) : (v19 = 1),
          --*(_DWORD *)(v11 + 40),
          (v64 = v19) != 0) )
    {
      v20 = v12->rclFrame.left;
      right = v12->rclFrame.right;
      v73 = v20;
      v22 = a5[2] - *a5;
      v72 = *a5;
      v23 = right == v20 ? (float)(v22 + 1) : (float)v22 / (float)(right - v20);
      top = v12->rclFrame.top;
      bottom = v12->rclFrame.bottom;
      v26 = a5[3] - a5[1];
      v67 = top;
      v74 = a5[1];
      v27 = bottom == top ? (float)(v26 + 1) : (float)v26 / (float)(bottom - top);
      cx = v12->szlMillimeters.cx;
      v69 = v12->szlDevice.cx;
      cy = v12->szlMillimeters.cy;
      v71 = v12->szlDevice.cy;
      if ( (unsigned int)NtGdiGetTransform(hdc, 516, &v78) )
      {
        v28 = (float)((float)((float)cy * 100.0) / (float)v71) * v27;
        v29 = (float)v72 - (float)((float)v73 * v23);
        v30 = (float)v74 - (float)((float)v67 * v27);
        v31 = (float)((float)((float)((float)cx * 100.0) / (float)v69) * v23) * *((float *)&v78 + 1);
        *(float *)(v11 + 704) = (float)((float)((float)((float)cx * 100.0) / (float)v69) * v23) * *(float *)&v78;
        v32 = v30 * *((float *)&v78 + 2);
        v33 = v28 * *((float *)&v78 + 2);
        v34 = v30 * *((float *)&v78 + 3);
        v35 = v28 * *((float *)&v78 + 3);
        *(float *)(v11 + 712) = v33;
        v36 = v29 * *(float *)&v78;
        v37 = v29 * *((float *)&v78 + 1);
        *(float *)(v11 + 708) = v31;
        *(float *)(v11 + 716) = v35;
        v38 = (float)(v34 + v37) + *((float *)&v79 + 1);
        *(float *)(v11 + 720) = (float)(v32 + v36) + *(float *)&v79;
        *(float *)(v11 + 724) = v38;
        if ( (GetMapMode(hdc) == 1 || SetMapMode(hdc, 1))
          && GetWindowOrgEx(hdc, (LPPOINT)&point)
          && (!point.iType && !point.nSize || SetWindowOrgEx(hdc, 0, 0, 0))
          && GetViewportOrgEx(hdc, (LPPOINT)&point)
          && (!point.iType && !point.nSize || SetViewportOrgEx(hdc, 0, 0, 0)) )
        {
          if ( *((float *)&v78 + 1) == 0.0 && *((float *)&v78 + 2) == 0.0 )
          {
            v39 = (XFORM *)(v11 + 704);
            if ( *(float *)(v11 + 708) == 0.0
              && *(float *)(v11 + 712) == 0.0
              && v39->eM11 >= 0.99900001
              && v39->eM11 <= 1.001 )
            {
              v40 = *(float *)(v11 + 716);
              if ( v40 >= 0.99900001 && v40 <= 1.001 )
              {
                v39->eM11 = 1.0;
                *(_DWORD *)(v11 + 716) = 1065353216;
              }
            }
          }
          else
          {
            v39 = (XFORM *)(v11 + 704);
          }
          if ( SetWorldTransform(hdc, v39) )
          {
            GetClipBox(hdc, (LPRECT)(v11 + 140));
            ERECTL::vOrder((ERECTL *)(v11 + 140));
            if ( v41 )
            {
              if ( v41 == 1 )
              {
                v14 = 1;
                goto LABEL_119;
              }
              DeviceCaps = (float)GetDeviceCaps(hdc, 118);
              v43 = DeviceCaps / (float)GetDeviceCaps(hdc, 4);
              v44 = (float)GetDeviceCaps(hdc, 117);
              v45 = v44 / (float)GetDeviceCaps(hdc, 6);
              v46 = (float)v12->szlDevice.cx / (float)v12->szlMillimeters.cx;
              v47 = (float)v12->szlDevice.cy / (float)v12->szlMillimeters.cy;
              v48 = v43 < v46 ? (int)(float)(v46 / v43) + 1 : 1;
              v49 = v45 < v47 ? (int)(float)(v47 / v45) + 1 : 1;
              *(_DWORD *)(v11 + 140) -= v48;
              *(_DWORD *)(v11 + 148) += v48;
              *(_DWORD *)(v11 + 144) -= v49;
              *(_DWORD *)(v11 + 152) += v49;
              if ( (unsigned int)NtGdiSetVirtualResolution(
                                   *(_QWORD *)(v11 + 728),
                                   (unsigned int)v12->szlDevice.cx,
                                   (unsigned int)v12->szlDevice.cy,
                                   (unsigned int)v12->szlMillimeters.cx,
                                   v12->szlMillimeters.cy) )
              {
                if ( (v61 < 0x6C
                   || !v12->szlMicrometers.cx
                   || !v12->szlMicrometers.cy
                   || (unsigned int)NtGdiSetSizeDevice(*(_QWORD *)(v11 + 728)))
                  && SetMapMode(*(HDC *)(v11 + 728), 1)
                  && ModifyWorldTransform(*(HDC *)(v11 + 728), 0, 1u)
                  && SetWindowOrgEx(*(HDC *)(v11 + 728), 0, 0, 0)
                  && SetViewportOrgEx(*(HDC *)(v11 + 728), 0, 0, 0) )
                {
                  if ( l != -1 )
                  {
                    SetLayout(hdc, l);
                    l = -1;
                  }
                  goto LABEL_89;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_119:
  if ( l != -1 )
    SetLayout(hdc, l);
  v54 = *(_DWORD *)(v11 + 700);
  if ( v54 > 1 )
  {
    point.iType = 34;
    point.nSize = 12;
    point.dParm[0] = 1 - v54;
    if ( a3 && !v15 )
    {
      v55 = a3(hdc, *(struct tagHANDLETABLE **)(v11 + 688), &point, v12->nHandles, a4) == 0;
      v56 = a3;
      if ( v55 )
        v14 = 0;
      goto LABEL_130;
    }
    v14 &= -PlayEnhMetaFileRecord(hdc, *(LPHANDLETABLE *)(v11 + 688), &point, v12->nHandles);
  }
  if ( v15 )
    goto LABEL_132;
  v56 = a3;
  if ( a3 )
  {
LABEL_130:
    v14 &= -(v56(hdc, *(struct tagHANDLETABLE **)(v11 + 688), v16, v12->nHandles, a4) != 0);
    if ( !*(_DWORD *)(v11 + 696) )
      goto LABEL_132;
  }
  v14 &= -PlayEnhMetaFileRecord(hdc, *(LPHANDLETABLE *)(v11 + 688), v16, v12->nHandles);
LABEL_132:
  if ( v64 && xmmword_1800FD820 )
    xmmword_1800FD820(hdc, v17);
  if ( hdc )
  {
    RestoreDC(hdc, -1);
    *(_DWORD *)(v68 + 152) &= ~0x800u;
    *(_DWORD *)(v68 + 152) |= v65;
  }
  for ( i = 1; i < v12->nHandles; ++i )
  {
    v58 = *(void **)(*(_QWORD *)(v11 + 688) + 8LL * i);
    if ( v58 )
    {
      DeleteObject(v58);
      *(_QWORD *)(*(_QWORD *)(v11 + 688) + 8LL * i) = 0;
    }
  }
  if ( v16 )
    --*v76;
  return v14;
}

```

## disassembly

```asm
0x180062a84  mov     rax, rsp
0x180062a87  push    rbp
0x180062a88  push    rbx
0x180062a89  push    rsi
0x180062a8a  push    rdi
0x180062a8b  push    r12
0x180062a8d  push    r13
0x180062a8f  push    r14
0x180062a91  push    r15
0x180062a93  lea     rbp, [rax-57h]
0x180062a97  sub     rsp, 0E8h
0x180062a9e  movaps  xmmword ptr [rax-58h], xmm6
0x180062aa2  movaps  xmmword ptr [rax-68h], xmm7
0x180062aa6  mov     rax, cs:__security_cookie
0x180062aad  xor     rax, rsp
0x180062ab0  mov     [rbp+4Fh+var_70], rax
0x180062ab4  cmp     cs:gbDisableMetaFiles, 0
0x180062abb  mov     r13, rdx
0x180062abe  mov     r12, [rbp+4Fh+arg_20]
0x180062ac2  mov     rdi, rcx
0x180062ac5  mov     [rsp+120h+var_D0], r12
0x180062aca  mov     [rbp+4Fh+var_A8], r9
0x180062ace  mov     [rsp+120h+var_D8], r8
0x180062ad3  jz      short loc_180062ADF
0x180062ad5  mov     eax, 1
0x180062ada  jmp     loc_180063267
0x180062adf  call    HANDLE_TO_INDEX
0x180062ae4  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x180062aeb  xor     r15d, r15d
0x180062aee  mov     [rbp+4Fh+var_C8], r15
0x180062af2  lea     ebx, [r15+1]
0x180062af6  cmp     eax, [rcx]
0x180062af8  jnb     short loc_180062B76
0x180062afa  xor     ecx, ecx
0x180062afc  lea     rdx, [rbp+4Fh+var_88]
0x180062b00  mov     [rbp+4Fh+var_78], rcx
0x180062b04  xorps   xmm0, xmm0
0x180062b07  mov     ecx, eax
0x180062b09  movups  [rbp+4Fh+var_88], xmm0
0x180062b0d  call    cs:__imp_GdiGetEntry
0x180062b14  nop     dword ptr [rax+rax+00h]
0x180062b19  test    eax, eax
0x180062b1b  js      short loc_180062B76
0x180062b1d  cmp     byte ptr [rbp+4Fh+var_88+0Eh], bl
0x180062b20  jnz     short loc_180062B76
0x180062b22  movzx   eax, byte ptr [rbp+4Fh+var_88+0Ch]
0x180062b26  movzx   ecx, byte ptr [rbp+4Fh+var_88+0Dh]
0x180062b2a  shl     cx, 8
0x180062b2e  or      cx, ax
0x180062b31  mov     eax, edi
0x180062b33  shr     eax, 10h
0x180062b36  cmp     cx, ax
0x180062b39  jnz     short loc_180062B76
0x180062b3b  mov     rax, cs:__imp_gW32PID
0x180062b42  mov     ecx, dword ptr [rbp+4Fh+var_88+8]
0x180062b45  and     ecx, 0FFFFFFFEh
0x180062b48  cmp     ecx, [rax]
0x180062b4a  jnz     short loc_180062B76
0x180062b4c  mov     r8, [rbp+4Fh+var_78]
0x180062b50  test    r8, r8
0x180062b53  jz      short loc_180062B76
0x180062b55  mov     rax, cs:__imp_gCookie
0x180062b5c  lea     ecx, [rbx+3Fh]
0x180062b5f  mov     r15, r8
0x180062b62  mov     rdx, [rax]
0x180062b65  mov     eax, edx
0x180062b67  and     eax, 3Fh
0x180062b6a  sub     ecx, eax
0x180062b6c  ror     r15, cl
0x180062b6f  xor     r15, rdx
0x180062b72  mov     [rbp+4Fh+var_C8], r15
0x180062b76  mov     edx, 460000h
0x180062b7b  mov     rcx, r13
0x180062b7e  call    pvClientObjGet
0x180062b83  mov     r14, rax
0x180062b86  test    rax, rax
0x180062b89  jz      loc_180063265
0x180062b8f  mov     rsi, [rax+30h]
0x180062b93  add     rax, 28h ; '('
0x180062b97  mov     [rbp+4Fh+var_A0], rax
0x180062b9b  test    rsi, rsi
0x180062b9e  jz      loc_180063265
0x180062ba4  mov     eax, [rsi+4]
0x180062ba7  cmp     eax, 58h ; 'X'
0x180062baa  jb      loc_180063265
0x180062bb0  cmp     [rsi+30h], eax
0x180062bb3  jb      loc_180063265
0x180062bb9  mov     rax, [r14+2B0h]
0x180062bc0  mov     rcx, rsi; struct tagENHMETAHEADER *
0x180062bc3  mov     [rax], r13
0x180062bc6  mov     [r14+2BCh], ebx
0x180062bcd  mov     dword ptr [r14+2B8h], 0
0x180062bd8  movups  xmm0, cs:?rclInfinity@@3U_RECTL@@A; _RECTL rclInfinity
0x180062bdf  movdqu  xmmword ptr [r14+8Ch], xmm0
0x180062be8  call    ?ComputeBaseHeaderSize@@YAKQEAUtagENHMETAHEADER@@@Z; ComputeBaseHeaderSize(tagENHMETAHEADER * const)
0x180062bed  mov     [rsp+120h+var_EC], eax
0x180062bf1  cmp     eax, 64h ; 'd'
0x180062bf4  jb      short loc_180062C09
0x180062bf6  cmp     dword ptr [rsi+60h], 0
0x180062bfa  jz      short loc_180062C09
0x180062bfc  call    LoadOpenGL
0x180062c01  test    eax, eax
0x180062c03  jz      loc_180063265
0x180062c09  mov     [rsp+120h+var_E4], 0
0x180062c11  test    rdi, rdi
0x180062c14  jz      loc_180063296
0x180062c1a  test    r12, r12
0x180062c1d  jz      loc_180063254
0x180062c23  mov     rcx, rdi; hdc
0x180062c26  call    cs:__imp_SaveDC
0x180062c2d  nop     dword ptr [rax+rax+00h]
0x180062c32  test    eax, eax
0x180062c34  jz      loc_180063265
0x180062c3a  test    r15, r15
0x180062c3d  jz      loc_180063254
0x180062c43  mov     rcx, [rbp+4Fh+var_C8]
0x180062c47  mov     r8d, 800h
0x180062c4d  xor     r15d, r15d
0x180062c50  mov     r12d, ebx
0x180062c53  xor     r13d, r13d
0x180062c56  mov     eax, [rcx+98h]
0x180062c5c  mov     edx, eax
0x180062c5e  and     edx, r8d
0x180062c61  or      eax, r8d
0x180062c64  mov     dword ptr [rsp+120h+var_E0], edx
0x180062c68  xor     edx, edx; l
0x180062c6a  mov     [rcx+98h], eax
0x180062c70  mov     rcx, rdi; hdc
0x180062c73  call    SetLayout
0x180062c78  lea     edx, [r15+2]; iMode
0x180062c7c  mov     [rsp+120h+l], eax
0x180062c80  mov     rcx, rdi; hdc
0x180062c83  call    SetGraphicsMode
0x180062c88  test    eax, eax
0x180062c8a  jz      loc_180063420
0x180062c90  mov     rcx, rdi; hdc
0x180062c93  call    SetMetaRgn
0x180062c98  test    eax, eax
0x180062c9a  jz      loc_180063420
0x180062ca0  mov     rcx, rdi; hdc
0x180062ca3  call    bMetaResetDC
0x180062ca8  test    eax, eax
0x180062caa  jz      loc_180063420
0x180062cb0  mov     eax, [rsp+120h+l]
0x180062cb4  cmp     eax, 0FFFFFFFFh
0x180062cb7  jz      short loc_180062CDC
0x180062cb9  test    bl, al
0x180062cbb  jz      short loc_180062CDC
0x180062cbd  lea     r9d, [r15+7Bh]
0x180062cc1  mov     [rsp+120h+var_F8], r13d
0x180062cc6  lea     edx, [r15+9]
0x180062cca  mov     word ptr [rsp+120h+var_100], r9w
0x180062cd0  lea     r8d, [r15+2]
0x180062cd4  mov     rcx, rdi
0x180062cd7  call    GetAndSetDCDWord
0x180062cdc  xor     eax, eax
0x180062cde  xorps   xmm0, xmm0
0x180062ce1  mov     [rbp+4Fh+var_78], rax
0x180062ce5  mov     qword ptr [rbp+4Fh+point.x], rax
0x180062ce9  mov     eax, [rsi+18h]
0x180062cec  movups  [rbp+4Fh+var_88], xmm0
0x180062cf0  cmp     [rsi+20h], eax
0x180062cf3  jl      loc_18006323E
0x180062cf9  mov     eax, [rsi+1Ch]
0x180062cfc  cmp     [rsi+24h], eax
0x180062cff  jl      loc_18006323E
0x180062d05  cmp     [rsp+120h+var_EC], 64h ; 'd'
0x180062d0a  jb      short loc_180062D60
0x180062d0c  cmp     [rsi+60h], r13d
0x180062d10  jz      short loc_180062D60
0x180062d12  mov     r8d, [rsi+30h]; unsigned int
0x180062d16  lea     rcx, [r14+28h]; this
0x180062d1a  xor     edx, edx; unsigned int
0x180062d1c  call    ?ObtainPtr@EMFContainer@@QEAAPEAXII@Z; EMFContainer::ObtainPtr(uint,uint)
0x180062d21  mov     rdx, rax
0x180062d24  test    rax, rax
0x180062d27  jz      loc_180063420
0x180062d2d  mov     rax, qword ptr cs:xmmword_1800FD800
0x180062d34  test    rax, rax
0x180062d37  jz      short loc_180062D4E
0x180062d39  mov     r8, [rsp+120h+var_D0]
0x180062d3e  mov     rcx, rdi
0x180062d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d46  test    eax, eax
0x180062d48  jz      short loc_180062D4E
0x180062d4a  mov     ecx, ebx
0x180062d4c  jmp     short loc_180062D50
0x180062d4e  xor     ecx, ecx
0x180062d50  dec     dword ptr [r14+28h]
0x180062d54  mov     [rsp+120h+var_E4], ecx
0x180062d58  test    ecx, ecx
0x180062d5a  jz      loc_180063420
0x180062d60  mov     rcx, [rsp+120h+var_D0]
0x180062d65  mov     r8d, [rsi+18h]
0x180062d69  mov     edx, [rsi+20h]
0x180062d6c  mov     [rbp+4Fh+var_B0], r8d
0x180062d70  mov     r9d, [rcx]
0x180062d73  mov     eax, [rcx+8]
0x180062d76  sub     eax, r9d
0x180062d79  mov     [rbp+4Fh+var_B4], r9d
0x180062d7d  cmp     edx, r8d
0x180062d80  jnz     short loc_180062D8D
0x180062d82  inc     eax
0x180062d84  movd    xmm7, eax
0x180062d88  cvtdq2ps xmm7, xmm7
0x180062d8b  jmp     short loc_180062DA2
0x180062d8d  sub     edx, r8d
0x180062d90  movd    xmm7, eax
0x180062d94  cvtdq2ps xmm7, xmm7
0x180062d97  movd    xmm0, edx
0x180062d9b  cvtdq2ps xmm0, xmm0
0x180062d9e  divss   xmm7, xmm0
0x180062da2  mov     r9d, [rcx+4]
0x180062da6  mov     r8d, [rsi+1Ch]
0x180062daa  mov     eax, [rcx+0Ch]
0x180062dad  mov     edx, [rsi+24h]
0x180062db0  sub     eax, r9d
0x180062db3  mov     dword ptr [rsp+120h+var_D0], r8d
0x180062db8  mov     [rbp+4Fh+var_AC], r9d
0x180062dbc  cmp     edx, r8d
0x180062dbf  jnz     short loc_180062DCC
0x180062dc1  inc     eax
0x180062dc3  movd    xmm6, eax
0x180062dc7  cvtdq2ps xmm6, xmm6
0x180062dca  jmp     short loc_180062DE1
0x180062dcc  sub     edx, r8d
0x180062dcf  movd    xmm6, eax
0x180062dd3  cvtdq2ps xmm6, xmm6
0x180062dd6  movd    xmm0, edx
0x180062dda  cvtdq2ps xmm0, xmm0
0x180062ddd  divss   xmm6, xmm0
0x180062de1  mov     eax, [rsi+50h]
0x180062de4  lea     r8, [rbp+4Fh+var_88]
0x180062de8  mov     [rsp+120h+var_F0], eax
0x180062dec  mov     edx, 204h
0x180062df1  mov     eax, [rsi+48h]
0x180062df4  mov     rcx, rdi
0x180062df7  mov     [rbp+4Fh+var_C0], eax
0x180062dfa  mov     eax, [rsi+54h]
0x180062dfd  mov     [rbp+4Fh+var_BC], eax
0x180062e00  mov     eax, [rsi+4Ch]
0x180062e03  mov     [rbp+4Fh+var_B8], eax
0x180062e06  call    cs:__imp_NtGdiGetTransform
0x180062e0d  nop     dword ptr [rax+rax+00h]
0x180062e12  test    eax, eax
0x180062e14  jz      loc_180063420
0x180062e1a  xorps   xmm0, xmm0
0x180062e1d  xorps   xmm2, xmm2
0x180062e20  cvtsi2ss xmm0, [rbp+4Fh+var_C0]
0x180062e25  mov     rcx, rdi; hdc
0x180062e28  cvtsi2ss xmm2, [rsp+120h+var_F0]
0x180062e2e  xorps   xmm3, xmm3
0x180062e31  xorps   xmm4, xmm4
0x180062e34  cvtsi2ss xmm3, [rbp+4Fh+var_BC]
0x180062e39  mulss   xmm2, cs:__real@42c80000
0x180062e41  xorps   xmm5, xmm5
0x180062e44  cvtsi2ss xmm4, [rbp+4Fh+var_AC]
0x180062e49  mulss   xmm3, cs:__real@42c80000
0x180062e51  cvtsi2ss xmm5, [rbp+4Fh+var_B4]
0x180062e56  divss   xmm2, xmm0
0x180062e5a  xorps   xmm0, xmm0
0x180062e5d  cvtsi2ss xmm0, [rbp+4Fh+var_B8]
0x180062e62  mulss   xmm2, xmm7
0x180062e66  divss   xmm3, xmm0
0x180062e6a  xorps   xmm0, xmm0
0x180062e6d  cvtsi2ss xmm0, [rbp+4Fh+var_B0]
0x180062e72  mulss   xmm3, xmm6
0x180062e76  mulss   xmm0, xmm7
0x180062e7a  subss   xmm5, xmm0
0x180062e7e  xorps   xmm0, xmm0
0x180062e81  cvtsi2ss xmm0, dword ptr [rsp+120h+var_D0]
0x180062e87  mulss   xmm0, xmm6
0x180062e8b  subss   xmm4, xmm0
0x180062e8f  movaps  xmm0, xmm2
0x180062e92  mulss   xmm0, dword ptr [rbp+4Fh+var_88]
0x180062e97  mulss   xmm2, dword ptr [rbp+4Fh+var_88+4]
0x180062e9c  movss   dword ptr [r14+2C0h], xmm0
0x180062ea5  movaps  xmm1, xmm4
0x180062ea8  mulss   xmm1, dword ptr [rbp+4Fh+var_88+8]
0x180062ead  movaps  xmm0, xmm3
0x180062eb0  mulss   xmm0, dword ptr [rbp+4Fh+var_88+8]
0x180062eb5  mulss   xmm4, dword ptr [rbp+4Fh+var_88+0Ch]
0x180062eba  mulss   xmm3, dword ptr [rbp+4Fh+var_88+0Ch]
0x180062ebf  movss   dword ptr [r14+2C8h], xmm0
0x180062ec8  movaps  xmm0, xmm5
0x180062ecb  mulss   xmm0, dword ptr [rbp+4Fh+var_88]
0x180062ed0  mulss   xmm5, dword ptr [rbp+4Fh+var_88+4]
0x180062ed5  addss   xmm1, xmm0
0x180062ed9  movss   dword ptr [r14+2C4h], xmm2
0x180062ee2  movss   dword ptr [r14+2CCh], xmm3
0x180062eeb  addss   xmm4, xmm5
0x180062eef  addss   xmm1, dword ptr [rbp+4Fh+var_78]
0x180062ef4  addss   xmm4, dword ptr [rbp+4Fh+var_78+4]
0x180062ef9  movss   dword ptr [r14+2D0h], xmm1
0x180062f02  movss   dword ptr [r14+2D4h], xmm4
0x180062f0b  call    GetMapMode
0x180062f10  cmp     eax, ebx
0x180062f12  jz      short loc_180062F26
0x180062f14  mov     edx, ebx; iMode
0x180062f16  mov     rcx, rdi; hdc
  ... truncated ...
```
