# bInternalPlayEMF

- ea: `0x18005ec9c`
- end: `0x18005f765`
- name: `bInternalPlayEMF`
- size: `2761`
- prototype: `__int64 __usercall@<rax>(HDC hdc@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x180031b30`
- `0x18005ec60`

## callees

- `0x180010000`
- `0x180010140`
- `0x1800102f0`
- `0x1800104e0`
- `0x180010790`
- `0x180010870`
- `0x1800233ac`
- `0x180023650`
- `0x180024fb8`
- `0x180029790`
- `0x1800305e0`
- `0x180050e00`
- `0x1800518e0`
- `0x18005202c`
- `0x180058540`
- `0x18005e8f0`
- `0x18005e9b0`
- `0x18005ec9c`
- `0x180067b50`
- `0x18006a330`
- `0x1800710c4`
- `0x18007ac50`
- `0x1800a5010`

## import_xrefs

- `GDI32!GetClipBox` at `0x18005f241`
- `GDI32!GetClipBox` at `0x18005f241`
- `GDI32!GetDeviceCaps` at `0x18005f270`
- `GDI32!GetDeviceCaps` at `0x18005f285`
- `GDI32!GetDeviceCaps` at `0x18005f29e`
- `GDI32!GetDeviceCaps` at `0x18005f2b3`
- `GDI32!GetDeviceCaps` at `0x18005f270`
- `GDI32!GetDeviceCaps` at `0x18005f285`
- `GDI32!GetDeviceCaps` at `0x18005f29e`
- `GDI32!GetDeviceCaps` at `0x18005f2b3`
- `GDI32!RestoreDC` at `0x18005f6fc`
- `GDI32!RestoreDC` at `0x18005f6fc`
- `GDI32!SaveDC` at `0x18005ee38`
- `GDI32!SaveDC` at `0x18005ee38`
- `GDI32!SetWorldTransform` at `0x18005f229`
- `GDI32!SetWorldTransform` at `0x18005f229`
- `GDI32!GdiGetEntry` at `0x18005ed25`
- `GDI32!GdiGetEntry` at `0x18005ed25`
- `GDI32!gW32PID` at `0x18005ed4d`
- `GDI32!gCookie` at `0x18005ed67`
- `GDI32!gMaxGdiHandleCount` at `0x18005ecfc`
- `GDI32!pldcGet` at `0x18005f479`
- `GDI32!pldcGet` at `0x18005f479`
- `GDI32!GdiSetLastError` at `0x18005f415`
- `GDI32!GdiSetLastError` at `0x18005f425`
- `GDI32!GdiSetLastError` at `0x18005f415`
- `GDI32!GdiSetLastError` at `0x18005f425`
- `GDI32!DeleteObject` at `0x18005f733`
- `GDI32!DeleteObject` at `0x18005f733`
- `win32u!NtGdiGetTransform` at `0x18005f012`
- `win32u!NtGdiGetTransform` at `0x18005f012`
- `win32u!NtGdiSetSizeDevice` at `0x18005f373`
- `win32u!NtGdiSetSizeDevice` at `0x18005f373`
- `win32u!NtGdiSetVirtualResolution` at `0x18005f347`
- `win32u!NtGdiSetVirtualResolution` at `0x18005f347`

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
              v50 = *(&xmmword_1800FA710 + 1) && ((unsigned int (__fastcall *)(HDC))*(&xmmword_1800FA710 + 1))(hdc);
              v60 = 1;
              goto LABEL_110;
            }
          }
          else if ( v60 )
          {
            v50 = *((_QWORD *)&xmmword_1800FA720 + 1)
               && (*((unsigned int (__fastcall **)(HDC))&xmmword_1800FA720 + 1))(hdc);
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
      && (!xmmword_1800FA710 || !(unsigned int)xmmword_1800FA710(hdc, v17, a5) ? (v19 = 0) : (v19 = 1),
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
  if ( v64 && xmmword_1800FA730 )
    xmmword_1800FA730(hdc, v17);
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
0x18005ec9c  mov     rax, rsp
0x18005ec9f  push    rbp
0x18005eca0  push    rbx
0x18005eca1  push    rsi
0x18005eca2  push    rdi
0x18005eca3  push    r12
0x18005eca5  push    r13
0x18005eca7  push    r14
0x18005eca9  push    r15
0x18005ecab  lea     rbp, [rax-57h]
0x18005ecaf  sub     rsp, 0E8h
0x18005ecb6  movaps  xmmword ptr [rax-58h], xmm6
0x18005ecba  movaps  xmmword ptr [rax-68h], xmm7
0x18005ecbe  mov     rax, cs:__security_cookie
0x18005ecc5  xor     rax, rsp
0x18005ecc8  mov     [rbp+4Fh+var_70], rax
0x18005eccc  cmp     cs:gbDisableMetaFiles, 0
0x18005ecd3  mov     r13, rdx
0x18005ecd6  mov     r12, [rbp+4Fh+arg_20]
0x18005ecda  mov     rdi, rcx
0x18005ecdd  mov     [rsp+120h+var_D0], r12
0x18005ece2  mov     [rbp+4Fh+var_A8], r9
0x18005ece6  mov     [rsp+120h+var_D8], r8
0x18005eceb  jz      short loc_18005ECF7
0x18005eced  mov     eax, 1
0x18005ecf2  jmp     loc_18005F42D
0x18005ecf7  call    HANDLE_TO_INDEX
0x18005ecfc  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x18005ed03  xor     r15d, r15d
0x18005ed06  mov     [rbp+4Fh+var_C8], r15
0x18005ed0a  lea     ebx, [r15+1]
0x18005ed0e  cmp     eax, [rcx]
0x18005ed10  jnb     short loc_18005ED88
0x18005ed12  xor     ecx, ecx
0x18005ed14  lea     rdx, [rbp+4Fh+var_88]
0x18005ed18  mov     [rbp+4Fh+var_78], rcx
0x18005ed1c  xorps   xmm0, xmm0
0x18005ed1f  mov     ecx, eax
0x18005ed21  movups  [rbp+4Fh+var_88], xmm0
0x18005ed25  call    cs:__imp_GdiGetEntry
0x18005ed2b  test    eax, eax
0x18005ed2d  js      short loc_18005ED88
0x18005ed2f  cmp     byte ptr [rbp+4Fh+var_88+0Eh], bl
0x18005ed32  jnz     short loc_18005ED88
0x18005ed34  movzx   eax, byte ptr [rbp+4Fh+var_88+0Ch]
0x18005ed38  movzx   ecx, byte ptr [rbp+4Fh+var_88+0Dh]
0x18005ed3c  shl     cx, 8
0x18005ed40  or      cx, ax
0x18005ed43  mov     eax, edi
0x18005ed45  shr     eax, 10h
0x18005ed48  cmp     cx, ax
0x18005ed4b  jnz     short loc_18005ED88
0x18005ed4d  mov     rax, cs:__imp_gW32PID
0x18005ed54  mov     ecx, dword ptr [rbp+4Fh+var_88+8]
0x18005ed57  and     ecx, 0FFFFFFFEh
0x18005ed5a  cmp     ecx, [rax]
0x18005ed5c  jnz     short loc_18005ED88
0x18005ed5e  mov     r8, [rbp+4Fh+var_78]
0x18005ed62  test    r8, r8
0x18005ed65  jz      short loc_18005ED88
0x18005ed67  mov     rax, cs:__imp_gCookie
0x18005ed6e  lea     ecx, [rbx+3Fh]
0x18005ed71  mov     r15, r8
0x18005ed74  mov     rdx, [rax]
0x18005ed77  mov     eax, edx
0x18005ed79  and     eax, 3Fh
0x18005ed7c  sub     ecx, eax
0x18005ed7e  ror     r15, cl
0x18005ed81  xor     r15, rdx
0x18005ed84  mov     [rbp+4Fh+var_C8], r15
0x18005ed88  mov     edx, 460000h
0x18005ed8d  mov     rcx, r13
0x18005ed90  call    pvClientObjGet
0x18005ed95  mov     r14, rax
0x18005ed98  test    rax, rax
0x18005ed9b  jz      loc_18005F42B
0x18005eda1  mov     rsi, [rax+30h]
0x18005eda5  add     rax, 28h ; '('
0x18005eda9  mov     [rbp+4Fh+var_A0], rax
0x18005edad  test    rsi, rsi
0x18005edb0  jz      loc_18005F42B
0x18005edb6  mov     eax, [rsi+4]
0x18005edb9  cmp     eax, 58h ; 'X'
0x18005edbc  jb      loc_18005F42B
0x18005edc2  cmp     [rsi+30h], eax
0x18005edc5  jb      loc_18005F42B
0x18005edcb  mov     rax, [r14+2B0h]
0x18005edd2  mov     rcx, rsi; struct tagENHMETAHEADER *
0x18005edd5  mov     [rax], r13
0x18005edd8  mov     [r14+2BCh], ebx
0x18005eddf  mov     dword ptr [r14+2B8h], 0
0x18005edea  movups  xmm0, cs:?rclInfinity@@3U_RECTL@@A; _RECTL rclInfinity
0x18005edf1  movdqu  xmmword ptr [r14+8Ch], xmm0
0x18005edfa  call    ?ComputeBaseHeaderSize@@YAKQEAUtagENHMETAHEADER@@@Z; ComputeBaseHeaderSize(tagENHMETAHEADER * const)
0x18005edff  mov     [rsp+120h+var_EC], eax
0x18005ee03  cmp     eax, 64h ; 'd'
0x18005ee06  jb      short loc_18005EE1B
0x18005ee08  cmp     dword ptr [rsi+60h], 0
0x18005ee0c  jz      short loc_18005EE1B
0x18005ee0e  call    LoadOpenGL
0x18005ee13  test    eax, eax
0x18005ee15  jz      loc_18005F42B
0x18005ee1b  mov     [rsp+120h+var_E4], 0
0x18005ee23  test    rdi, rdi
0x18005ee26  jz      loc_18005F45B
0x18005ee2c  test    r12, r12
0x18005ee2f  jz      loc_18005F420
0x18005ee35  mov     rcx, rdi; hdc
0x18005ee38  call    cs:__imp_SaveDC
0x18005ee3e  test    eax, eax
0x18005ee40  jz      loc_18005F42B
0x18005ee46  test    r15, r15
0x18005ee49  jz      loc_18005F420
0x18005ee4f  mov     rcx, [rbp+4Fh+var_C8]
0x18005ee53  mov     r8d, 800h
0x18005ee59  xor     r15d, r15d
0x18005ee5c  mov     r12d, ebx
0x18005ee5f  xor     r13d, r13d
0x18005ee62  mov     eax, [rcx+98h]
0x18005ee68  mov     edx, eax
0x18005ee6a  and     edx, r8d
0x18005ee6d  or      eax, r8d
0x18005ee70  mov     dword ptr [rsp+120h+var_E0], edx
0x18005ee74  xor     edx, edx; l
0x18005ee76  mov     [rcx+98h], eax
0x18005ee7c  mov     rcx, rdi; hdc
0x18005ee7f  call    SetLayout
0x18005ee84  lea     edx, [r15+2]; iMode
0x18005ee88  mov     [rsp+120h+l], eax
0x18005ee8c  mov     rcx, rdi; hdc
0x18005ee8f  call    SetGraphicsMode
0x18005ee94  test    eax, eax
0x18005ee96  jz      loc_18005F5DF
0x18005ee9c  mov     rcx, rdi; hdc
0x18005ee9f  call    SetMetaRgn
0x18005eea4  test    eax, eax
0x18005eea6  jz      loc_18005F5DF
0x18005eeac  mov     rcx, rdi; hdc
0x18005eeaf  call    bMetaResetDC
0x18005eeb4  test    eax, eax
0x18005eeb6  jz      loc_18005F5DF
0x18005eebc  mov     eax, [rsp+120h+l]
0x18005eec0  cmp     eax, 0FFFFFFFFh
0x18005eec3  jz      short loc_18005EEE8
0x18005eec5  test    bl, al
0x18005eec7  jz      short loc_18005EEE8
0x18005eec9  lea     r9d, [r15+7Bh]
0x18005eecd  mov     [rsp+120h+var_F8], r13d
0x18005eed2  lea     edx, [r15+9]
0x18005eed6  mov     word ptr [rsp+120h+var_100], r9w
0x18005eedc  lea     r8d, [r15+2]
0x18005eee0  mov     rcx, rdi
0x18005eee3  call    GetAndSetDCDWord
0x18005eee8  xor     eax, eax
0x18005eeea  xorps   xmm0, xmm0
0x18005eeed  mov     [rbp+4Fh+var_78], rax
0x18005eef1  mov     qword ptr [rbp+4Fh+point.x], rax
0x18005eef5  mov     eax, [rsi+18h]
0x18005eef8  movups  [rbp+4Fh+var_88], xmm0
0x18005eefc  cmp     [rsi+20h], eax
0x18005eeff  jl      loc_18005F410
0x18005ef05  mov     eax, [rsi+1Ch]
0x18005ef08  cmp     [rsi+24h], eax
0x18005ef0b  jl      loc_18005F410
0x18005ef11  cmp     [rsp+120h+var_EC], 64h ; 'd'
0x18005ef16  jb      short loc_18005EF6C
0x18005ef18  cmp     [rsi+60h], r13d
0x18005ef1c  jz      short loc_18005EF6C
0x18005ef1e  mov     r8d, [rsi+30h]; unsigned int
0x18005ef22  lea     rcx, [r14+28h]; this
0x18005ef26  xor     edx, edx; unsigned int
0x18005ef28  call    ?ObtainPtr@EMFContainer@@QEAAPEAXII@Z; EMFContainer::ObtainPtr(uint,uint)
0x18005ef2d  mov     rdx, rax
0x18005ef30  test    rax, rax
0x18005ef33  jz      loc_18005F5DF
0x18005ef39  mov     rax, qword ptr cs:xmmword_1800FA710
0x18005ef40  test    rax, rax
0x18005ef43  jz      short loc_18005EF5A
0x18005ef45  mov     r8, [rsp+120h+var_D0]
0x18005ef4a  mov     rcx, rdi
0x18005ef4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ef52  test    eax, eax
0x18005ef54  jz      short loc_18005EF5A
0x18005ef56  mov     ecx, ebx
0x18005ef58  jmp     short loc_18005EF5C
0x18005ef5a  xor     ecx, ecx
0x18005ef5c  dec     dword ptr [r14+28h]
0x18005ef60  mov     [rsp+120h+var_E4], ecx
0x18005ef64  test    ecx, ecx
0x18005ef66  jz      loc_18005F5DF
0x18005ef6c  mov     rcx, [rsp+120h+var_D0]
0x18005ef71  mov     r8d, [rsi+18h]
0x18005ef75  mov     edx, [rsi+20h]
0x18005ef78  mov     [rbp+4Fh+var_B0], r8d
0x18005ef7c  mov     r9d, [rcx]
0x18005ef7f  mov     eax, [rcx+8]
0x18005ef82  sub     eax, r9d
0x18005ef85  mov     [rbp+4Fh+var_B4], r9d
0x18005ef89  cmp     edx, r8d
0x18005ef8c  jnz     short loc_18005EF99
0x18005ef8e  inc     eax
0x18005ef90  movd    xmm7, eax
0x18005ef94  cvtdq2ps xmm7, xmm7
0x18005ef97  jmp     short loc_18005EFAE
0x18005ef99  sub     edx, r8d
0x18005ef9c  movd    xmm7, eax
0x18005efa0  cvtdq2ps xmm7, xmm7
0x18005efa3  movd    xmm0, edx
0x18005efa7  cvtdq2ps xmm0, xmm0
0x18005efaa  divss   xmm7, xmm0
0x18005efae  mov     r9d, [rcx+4]
0x18005efb2  mov     r8d, [rsi+1Ch]
0x18005efb6  mov     eax, [rcx+0Ch]
0x18005efb9  mov     edx, [rsi+24h]
0x18005efbc  sub     eax, r9d
0x18005efbf  mov     dword ptr [rsp+120h+var_D0], r8d
0x18005efc4  mov     [rbp+4Fh+var_AC], r9d
0x18005efc8  cmp     edx, r8d
0x18005efcb  jnz     short loc_18005EFD8
0x18005efcd  inc     eax
0x18005efcf  movd    xmm6, eax
0x18005efd3  cvtdq2ps xmm6, xmm6
0x18005efd6  jmp     short loc_18005EFED
0x18005efd8  sub     edx, r8d
0x18005efdb  movd    xmm6, eax
0x18005efdf  cvtdq2ps xmm6, xmm6
0x18005efe2  movd    xmm0, edx
0x18005efe6  cvtdq2ps xmm0, xmm0
0x18005efe9  divss   xmm6, xmm0
0x18005efed  mov     eax, [rsi+50h]
0x18005eff0  lea     r8, [rbp+4Fh+var_88]
0x18005eff4  mov     [rsp+120h+var_F0], eax
0x18005eff8  mov     edx, 204h
0x18005effd  mov     eax, [rsi+48h]
0x18005f000  mov     rcx, rdi
0x18005f003  mov     [rbp+4Fh+var_C0], eax
0x18005f006  mov     eax, [rsi+54h]
0x18005f009  mov     [rbp+4Fh+var_BC], eax
0x18005f00c  mov     eax, [rsi+4Ch]
0x18005f00f  mov     [rbp+4Fh+var_B8], eax
0x18005f012  call    cs:__imp_NtGdiGetTransform
0x18005f018  test    eax, eax
0x18005f01a  jz      loc_18005F5DF
0x18005f020  xorps   xmm0, xmm0
0x18005f023  xorps   xmm2, xmm2
0x18005f026  cvtsi2ss xmm0, [rbp+4Fh+var_C0]
0x18005f02b  mov     rcx, rdi; hdc
0x18005f02e  cvtsi2ss xmm2, [rsp+120h+var_F0]
0x18005f034  xorps   xmm3, xmm3
0x18005f037  xorps   xmm4, xmm4
0x18005f03a  cvtsi2ss xmm3, [rbp+4Fh+var_BC]
0x18005f03f  mulss   xmm2, cs:__real@42c80000
0x18005f047  xorps   xmm5, xmm5
0x18005f04a  cvtsi2ss xmm4, [rbp+4Fh+var_AC]
0x18005f04f  mulss   xmm3, cs:__real@42c80000
0x18005f057  cvtsi2ss xmm5, [rbp+4Fh+var_B4]
0x18005f05c  divss   xmm2, xmm0
0x18005f060  xorps   xmm0, xmm0
0x18005f063  cvtsi2ss xmm0, [rbp+4Fh+var_B8]
0x18005f068  mulss   xmm2, xmm7
0x18005f06c  divss   xmm3, xmm0
0x18005f070  xorps   xmm0, xmm0
0x18005f073  cvtsi2ss xmm0, [rbp+4Fh+var_B0]
0x18005f078  mulss   xmm3, xmm6
0x18005f07c  mulss   xmm0, xmm7
0x18005f080  subss   xmm5, xmm0
0x18005f084  xorps   xmm0, xmm0
0x18005f087  cvtsi2ss xmm0, dword ptr [rsp+120h+var_D0]
0x18005f08d  mulss   xmm0, xmm6
0x18005f091  subss   xmm4, xmm0
0x18005f095  movaps  xmm0, xmm2
0x18005f098  mulss   xmm0, dword ptr [rbp+4Fh+var_88]
0x18005f09d  mulss   xmm2, dword ptr [rbp+4Fh+var_88+4]
0x18005f0a2  movss   dword ptr [r14+2C0h], xmm0
0x18005f0ab  movaps  xmm1, xmm4
0x18005f0ae  mulss   xmm1, dword ptr [rbp+4Fh+var_88+8]
0x18005f0b3  movaps  xmm0, xmm3
0x18005f0b6  mulss   xmm0, dword ptr [rbp+4Fh+var_88+8]
0x18005f0bb  mulss   xmm4, dword ptr [rbp+4Fh+var_88+0Ch]
0x18005f0c0  mulss   xmm3, dword ptr [rbp+4Fh+var_88+0Ch]
0x18005f0c5  movss   dword ptr [r14+2C8h], xmm0
0x18005f0ce  movaps  xmm0, xmm5
0x18005f0d1  mulss   xmm0, dword ptr [rbp+4Fh+var_88]
0x18005f0d6  mulss   xmm5, dword ptr [rbp+4Fh+var_88+4]
0x18005f0db  addss   xmm1, xmm0
0x18005f0df  movss   dword ptr [r14+2C4h], xmm2
0x18005f0e8  movss   dword ptr [r14+2CCh], xmm3
0x18005f0f1  addss   xmm4, xmm5
0x18005f0f5  addss   xmm1, dword ptr [rbp+4Fh+var_78]
0x18005f0fa  addss   xmm4, dword ptr [rbp+4Fh+var_78+4]
0x18005f0ff  movss   dword ptr [r14+2D0h], xmm1
0x18005f108  movss   dword ptr [r14+2D4h], xmm4
0x18005f111  call    GetMapMode
0x18005f116  cmp     eax, ebx
0x18005f118  jz      short loc_18005F12C
0x18005f11a  mov     edx, ebx; iMode
0x18005f11c  mov     rcx, rdi; hdc
0x18005f11f  call    SetMapMode
0x18005f124  test    eax, eax
0x18005f126  jz      loc_18005F5DF
  ... truncated ...
```
