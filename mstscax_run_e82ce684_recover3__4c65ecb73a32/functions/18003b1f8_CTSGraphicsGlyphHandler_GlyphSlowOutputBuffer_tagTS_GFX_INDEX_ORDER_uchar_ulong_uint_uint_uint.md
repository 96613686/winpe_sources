# CTSGraphicsGlyphHandler::GlyphSlowOutputBuffer(tagTS_GFX_INDEX_ORDER *,uchar *,ulong,uint,uint,uint)

- ea: `0x18003b1f8`
- end: `0x18003b6a4`
- name: `?GlyphSlowOutputBuffer@CTSGraphicsGlyphHandler@@IEAAXPEAUtagTS_GFX_INDEX_ORDER@@PEAEKIII@Z`
- size: `1196`
- prototype: `void __fastcall(CTSGraphicsGlyphHandler *this, struct tagTS_GFX_INDEX_ORDER *, unsigned __int8 *, int, unsigned int, COLORREF color, COLORREF)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003a484`

## callees

- `0x18002a334`
- `0x180039ce4`
- `0x18003b1f8`
- `0x18003b6b0`
- `0x1800e9b1c`
- `0x18068c010`

## import_xrefs

- `GDI32!DeleteObject` at `0x18003b2a4`
- `GDI32!DeleteObject` at `0x18003b2a4`
- `GDI32!SelectObject` at `0x18003b2f6`
- `GDI32!SelectObject` at `0x18003b3b6`
- `GDI32!SelectObject` at `0x18003b2f6`
- `GDI32!SelectObject` at `0x18003b3b6`
- `GDI32!CreateCompatibleDC` at `0x18003b4cf`
- `GDI32!CreateCompatibleDC` at `0x18003b4cf`
- `GDI32!BitBlt` at `0x18003b39e`
- `GDI32!BitBlt` at `0x18003b39e`
- `GDI32!CreateBitmap` at `0x18003b2c4`
- `GDI32!CreateBitmap` at `0x18003b2c4`
- `GDI32!SetBitmapBits` at `0x18003b4c2`
- `GDI32!SetBitmapBits` at `0x18003b4c2`
- `GDI32!GetNearestColor` at `0x18003b55c`
- `GDI32!GetNearestColor` at `0x18003b58d`
- `GDI32!GetNearestColor` at `0x18003b55c`
- `GDI32!GetNearestColor` at `0x18003b58d`

## string_xrefs

- `0x18003b5c8`: `Failed to create brush`

## pseudocode

```c
void __fastcall CTSGraphicsGlyphHandler::GlyphSlowOutputBuffer(
        CTSGraphicsGlyphHandler *this,
        struct tagTS_GFX_INDEX_ORDER *a2,
        unsigned __int8 *a3,
        int a4,
        unsigned int a5,
        COLORREF color,
        COLORREF a7)
{
  __int64 v8; // rcx
  HDC v11; // r13
  unsigned int *v12; // r14
  unsigned int v13; // esi
  int v14; // r15d
  HBITMAP *v15; // rdi
  void *v16; // rcx
  HBITMAP Bitmap; // rax
  HDC CompatibleDC; // rax
  HGDIOBJ v19; // rsi
  DWORD rop; // eax
  __int64 v21; // rcx
  int v22; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v24; // rdx
  unsigned int v25; // eax
  unsigned int v26; // eax
  __int64 v27; // [rsp+50h] [rbp-68h] BYREF
  _DWORD v28[24]; // [rsp+58h] [rbp-60h] BYREF
  unsigned int v29; // [rsp+C0h] [rbp+8h]

  v27 = 0;
  v8 = *((_QWORD *)this + 54);
  memset(v28, 0, 32);
  v11 = (HDC)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v8 + 56) + 24LL))(v8 + 56);
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_14;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v24 = 22;
LABEL_45:
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v24,
      &WPP_c50f5e74c25e3036c795d57fb324c23c_Traceguids,
      CurrentThreadActivityIdPrefix);
    goto LABEL_14;
  }
  v12 = (unsigned int *)((char *)this + 396);
  v13 = *((_DWORD *)a2 + 7) - *((_DWORD *)a2 + 5);
  v29 = *(_DWORD *)(*((_QWORD *)this + 55) + 836LL);
  v14 = 8 * a5;
  if ( 8 * a5 == *((_DWORD *)this + 98) && v13 <= *v12 )
  {
    v15 = (HBITMAP *)((char *)this + 400);
  }
  else
  {
    v15 = (HBITMAP *)((char *)this + 400);
    v16 = (void *)*((_QWORD *)this + 50);
    if ( v16 )
    {
      DeleteObject(v16);
      *v15 = 0;
      goto LABEL_5;
    }
  }
  if ( *v15 )
  {
    SetBitmapBits(*v15, (v14 * v13) >> 3, a3);
    goto LABEL_7;
  }
LABEL_5:
  Bitmap = CreateBitmap(v14, v13, 1u, 1u, a3);
  *v15 = Bitmap;
  if ( !Bitmap )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_14;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v24 = 23;
    goto LABEL_45;
  }
  *((_DWORD *)this + 98) = v14;
  *v12 = v13;
LABEL_7:
  CompatibleDC = (HDC)*((_QWORD *)this + 51);
  if ( !CompatibleDC )
  {
    CompatibleDC = CreateCompatibleDC(0);
    *((_QWORD *)this + 51) = CompatibleDC;
    if ( !CompatibleDC )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        goto LABEL_14;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v24 = 24;
      goto LABEL_45;
    }
  }
  v19 = SelectObject(CompatibleDC, *v15);
  if ( *((_DWORD *)a2 + 9) < *((_DWORD *)a2 + 11) )
  {
    if ( v29 <= 8 )
    {
      GetNearestColor(v11, color);
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 54) + 48LL) + 184LL))(
        *((_QWORD *)this + 54) + 48LL,
        color);
      GetNearestColor(v11, a7);
    }
    else
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 54) + 48LL) + 184LL))(
        *((_QWORD *)this + 54) + 48LL,
        color);
    }
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 54) + 48LL) + 176LL))(
      *((_QWORD *)this + 54) + 48LL,
      a7);
    rop = 13369376;
    goto LABEL_12;
  }
  (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 54) + 48LL) + 136LL))(
    *((_QWORD *)this + 54) + 48LL,
    0,
    0);
  v21 = *((_QWORD *)this + 53);
  v28[0] = a7;
  v22 = CTSGraphics::BrushCreate(v21, 0, v28, &v27);
  if ( v22 >= 0 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(*((_QWORD *)this + 54) + 48LL) + 120LL))(
      *((_QWORD *)this + 54) + 48LL,
      v27);
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(*((_QWORD *)this + 54) + 48LL) + 184LL))(
      *((_QWORD *)this + 54) + 48LL,
      0);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(*((_QWORD *)this + 54) + 48LL) + 176LL))(
      *((_QWORD *)this + 54) + 48LL,
      0xFFFFFF);
    rop = 14812998;
LABEL_12:
    if ( !BitBlt(
            v11,
            *((_DWORD *)a2 + 4),
            *((_DWORD *)a2 + 5),
            *((_DWORD *)a2 + 6) - *((_DWORD *)a2 + 4),
            *((_DWORD *)a2 + 7) - *((_DWORD *)a2 + 5),
            *((HDC *)this + 51),
            a4,
            0,
            rop)
      && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_c50f5e74c25e3036c795d57fb324c23c_Traceguids, v26);
    }
    SelectObject(*((HDC *)this + 51), v19);
    goto LABEL_14;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v25 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      (unsigned int)&WPP_c50f5e74c25e3036c795d57fb324c23c_Traceguids,
      v25,
      (__int64)"Failed to create brush",
      v22);
  }
LABEL_14:
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
}

```

## disassembly

```asm
0x18003b1f8  mov     rax, rsp
0x18003b1fb  mov     [rax+10h], rbx
0x18003b1ff  mov     [rax+20h], r9d
0x18003b203  push    rbp
0x18003b204  push    rsi
0x18003b205  push    rdi
0x18003b206  push    r12
0x18003b208  push    r13
0x18003b20a  push    r14
0x18003b20c  push    r15
0x18003b20e  sub     rsp, 80h
0x18003b215  mov     rbx, rcx
0x18003b218  mov     qword ptr [rax-68h], 0
0x18003b220  mov     rcx, [rcx+1B0h]
0x18003b227  xorps   xmm0, xmm0
0x18003b22a  movups  xmmword ptr [rax-60h], xmm0
0x18003b22e  add     rcx, 38h ; '8'
0x18003b232  mov     r12, r8
0x18003b235  movups  xmmword ptr [rax-50h], xmm0
0x18003b239  mov     rbp, rdx
0x18003b23c  mov     rax, [rcx]
0x18003b23f  mov     rax, [rax+18h]
0x18003b243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b248  mov     r13, rax
0x18003b24b  test    rax, rax
0x18003b24e  jz      loc_18003B51F
0x18003b254  mov     rax, [rbx+1B8h]
0x18003b25b  lea     r14, [rbx+18Ch]
0x18003b262  mov     esi, [rbp+1Ch]
0x18003b265  sub     esi, [rbp+14h]
0x18003b268  mov     eax, [rax+344h]
0x18003b26e  mov     [rsp+0B8h+arg_0], eax
0x18003b275  mov     eax, [rsp+0B8h+arg_20]
0x18003b27c  lea     r15d, ds:0[rax*8]
0x18003b284  cmp     r15d, [rbx+188h]
0x18003b28b  jz      loc_18003B49A
0x18003b291  lea     rdi, [rbx+190h]
0x18003b298  mov     rcx, [rdi]; ho
0x18003b29b  test    rcx, rcx
0x18003b29e  jz      loc_18003B4AA
0x18003b2a4  call    cs:__imp_DeleteObject
0x18003b2aa  mov     qword ptr [rdi], 0
0x18003b2b1  mov     r9d, 1; nBitCount
0x18003b2b7  mov     [rsp+0B8h+lpBits], r12; lpBits
0x18003b2bc  mov     r8d, r9d; nPlanes
0x18003b2bf  mov     edx, esi; nHeight
0x18003b2c1  mov     ecx, r15d; nWidth
0x18003b2c4  call    cs:__imp_CreateBitmap
0x18003b2ca  mov     [rdi], rax
0x18003b2cd  test    rax, rax
0x18003b2d0  jz      loc_18003B650
0x18003b2d6  mov     [rbx+188h], r15d
0x18003b2dd  mov     [r14], esi
0x18003b2e0  mov     rax, [rbx+198h]
0x18003b2e7  test    rax, rax
0x18003b2ea  jz      loc_18003B4CD
0x18003b2f0  mov     rdx, [rdi]; h
0x18003b2f3  mov     rcx, rax; hdc
0x18003b2f6  call    cs:__imp_SelectObject
0x18003b2fc  mov     ecx, [rbp+2Ch]
0x18003b2ff  mov     rsi, rax
0x18003b302  cmp     [rbp+24h], ecx
0x18003b305  jge     loc_18003B3ED
0x18003b30b  cmp     [rsp+0B8h+arg_0], 8
0x18003b313  mov     edx, [rsp+0B8h+color]; color
0x18003b31a  jbe     loc_18003B559
0x18003b320  mov     rcx, [rbx+1B0h]
0x18003b327  add     rcx, 30h ; '0'
0x18003b32b  mov     rax, [rcx]
0x18003b32e  mov     rax, [rax+0B8h]
0x18003b335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b33a  mov     rcx, [rbx+1B0h]
0x18003b341  mov     edx, [rsp+0B8h+arg_30]
0x18003b348  add     rcx, 30h ; '0'
0x18003b34c  mov     rax, [rcx]
0x18003b34f  mov     rax, [rax+0B0h]
0x18003b356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b35b  mov     eax, 0CC0020h
0x18003b360  mov     ecx, [rbp+1Ch]
0x18003b363  mov     r8d, [rbp+14h]; y
0x18003b367  sub     ecx, r8d
0x18003b36a  mov     r9d, [rbp+18h]
0x18003b36e  mov     edx, [rbp+10h]; x
0x18003b371  sub     r9d, edx; cx
0x18003b374  mov     [rsp+0B8h+rop], eax; rop
0x18003b378  mov     eax, [rsp+0B8h+arg_18]
0x18003b37f  mov     [rsp+0B8h+y1], 0; y1
0x18003b387  mov     [rsp+0B8h+x1], eax; x1
0x18003b38b  mov     rax, [rbx+198h]
0x18003b392  mov     [rsp+0B8h+hdcSrc], rax; hdcSrc
0x18003b397  mov     dword ptr [rsp+0B8h+lpBits], ecx; cy
0x18003b39b  mov     rcx, r13; hdc
0x18003b39e  call    cs:__imp_BitBlt
0x18003b3a4  test    eax, eax
0x18003b3a6  jz      loc_18003B5FC
0x18003b3ac  mov     rcx, [rbx+198h]; hdc
0x18003b3b3  mov     rdx, rsi; h
0x18003b3b6  call    cs:__imp_SelectObject
0x18003b3bc  mov     rcx, [rsp+0B8h+var_68]
0x18003b3c1  test    rcx, rcx
0x18003b3c4  jz      short loc_18003B3D2
0x18003b3c6  mov     rax, [rcx]
0x18003b3c9  mov     rax, [rax+10h]
0x18003b3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3d2  mov     rbx, [rsp+0B8h+arg_8]
0x18003b3da  add     rsp, 80h
0x18003b3e1  pop     r15
0x18003b3e3  pop     r14
0x18003b3e5  pop     r13
0x18003b3e7  pop     r12
0x18003b3e9  pop     rdi
0x18003b3ea  pop     rsi
0x18003b3eb  pop     rbp
0x18003b3ec  retn
0x18003b3ed  mov     rcx, [rbx+1B0h]
0x18003b3f4  xor     r8d, r8d
0x18003b3f7  add     rcx, 30h ; '0'
0x18003b3fb  xor     edx, edx
0x18003b3fd  mov     rax, [rcx]
0x18003b400  mov     rax, [rax+88h]
0x18003b407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b40c  mov     eax, [rsp+0B8h+arg_30]
0x18003b413  lea     r9, [rsp+0B8h+var_68]
0x18003b418  mov     rcx, [rbx+1A8h]
0x18003b41f  lea     r8, [rsp+0B8h+var_60]
0x18003b424  xor     edx, edx
0x18003b426  mov     [rsp+0B8h+var_60], eax
0x18003b42a  call    ?BrushCreate@CTSGraphics@@UEAAJW4TS_GFX_BRUSH_TYPE@@PEATtagTS_GFX_BRUSH_DATA@@PEAPEAVITSGraphicsBrush@@@Z; CTSGraphics::BrushCreate(TS_GFX_BRUSH_TYPE,tagTS_GFX_BRUSH_DATA *,ITSGraphicsBrush * *)
0x18003b42f  mov     edi, eax
0x18003b431  test    eax, eax
0x18003b433  js      loc_18003B598
0x18003b439  mov     rcx, [rbx+1B0h]
0x18003b440  mov     rdx, [rsp+0B8h+var_68]
0x18003b445  add     rcx, 30h ; '0'
0x18003b449  mov     rax, [rcx]
0x18003b44c  mov     rax, [rax+78h]
0x18003b450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b455  mov     rcx, [rbx+1B0h]
0x18003b45c  xor     edx, edx
0x18003b45e  add     rcx, 30h ; '0'
0x18003b462  mov     rax, [rcx]
0x18003b465  mov     rax, [rax+0B8h]
0x18003b46c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b471  mov     rcx, [rbx+1B0h]
0x18003b478  mov     edx, 0FFFFFFh
0x18003b47d  add     rcx, 30h ; '0'
0x18003b481  mov     rax, [rcx]
0x18003b484  mov     rax, [rax+0B0h]
0x18003b48b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b490  mov     eax, 0E20746h
0x18003b495  jmp     loc_18003B360
0x18003b49a  cmp     esi, [r14]
0x18003b49d  ja      loc_18003B291
0x18003b4a3  lea     rdi, [rbx+190h]
0x18003b4aa  mov     rcx, [rdi]; hbm
0x18003b4ad  test    rcx, rcx
0x18003b4b0  jz      loc_18003B2B1
0x18003b4b6  imul    esi, r15d
0x18003b4ba  mov     r8, r12; pvBits
0x18003b4bd  shr     esi, 3
0x18003b4c0  mov     edx, esi; cb
0x18003b4c2  call    cs:__imp_SetBitmapBits
0x18003b4c8  jmp     loc_18003B2E0
0x18003b4cd  xor     ecx, ecx; hdc
0x18003b4cf  call    cs:__imp_CreateCompatibleDC
0x18003b4d5  mov     [rbx+198h], rax
0x18003b4dc  test    rax, rax
0x18003b4df  jnz     loc_18003B2F0
0x18003b4e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b4ec  lea     rax, WPP_GLOBAL_Control
0x18003b4f3  cmp     rcx, rax
0x18003b4f6  jz      loc_18003B3BC
0x18003b4fc  test    byte ptr [rcx+1Ch], 1
0x18003b500  jz      loc_18003B3BC
0x18003b506  cmp     byte ptr [rcx+19h], 4
0x18003b50a  jb      loc_18003B3BC
0x18003b510  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003b515  mov     edx, 18h
0x18003b51a  jmp     loc_18003B685
0x18003b51f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b526  lea     rax, WPP_GLOBAL_Control
0x18003b52d  cmp     rcx, rax
0x18003b530  jz      loc_18003B3BC
0x18003b536  test    byte ptr [rcx+1Ch], 1
0x18003b53a  jz      loc_18003B3BC
0x18003b540  cmp     byte ptr [rcx+19h], 2
0x18003b544  jb      loc_18003B3BC
0x18003b54a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003b54f  mov     edx, 16h
0x18003b554  jmp     loc_18003B685
0x18003b559  mov     rcx, r13; hdc
0x18003b55c  call    cs:__imp_GetNearestColor
0x18003b562  mov     rcx, [rbx+1B0h]
0x18003b569  mov     edx, [rsp+0B8h+color]
0x18003b570  add     rcx, 30h ; '0'
0x18003b574  mov     rax, [rcx]
0x18003b577  mov     rax, [rax+0B8h]
0x18003b57e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b583  mov     edx, [rsp+0B8h+arg_30]; color
0x18003b58a  mov     rcx, r13; hdc
0x18003b58d  call    cs:__imp_GetNearestColor
0x18003b593  jmp     loc_18003B33A
0x18003b598  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b59f  lea     rax, WPP_GLOBAL_Control
0x18003b5a6  cmp     rcx, rax
0x18003b5a9  jz      loc_18003B3BC
0x18003b5af  test    byte ptr [rcx+1Ch], 8
0x18003b5b3  jz      loc_18003B3BC
0x18003b5b9  cmp     byte ptr [rcx+19h], 2
0x18003b5bd  jb      loc_18003B3BC
0x18003b5c3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003b5c8  lea     rcx, aFailedToCreate_92; "Failed to create brush"
0x18003b5cf  mov     dword ptr [rsp+0B8h+hdcSrc], edi
0x18003b5d3  mov     [rsp+0B8h+lpBits], rcx
0x18003b5d8  lea     r8, WPP_c50f5e74c25e3036c795d57fb324c23c_Traceguids
0x18003b5df  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b5e6  mov     edx, 19h
0x18003b5eb  mov     r9d, eax
0x18003b5ee  mov     rcx, [rcx+10h]
0x18003b5f2  call    WPP_SF_DsD
0x18003b5f7  jmp     loc_18003B3BC
0x18003b5fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b603  lea     rax, WPP_GLOBAL_Control
0x18003b60a  cmp     rcx, rax
0x18003b60d  jz      loc_18003B3AC
0x18003b613  test    byte ptr [rcx+1Ch], 1
0x18003b617  jz      loc_18003B3AC
0x18003b61d  cmp     byte ptr [rcx+19h], 2
0x18003b621  jb      loc_18003B3AC
0x18003b627  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003b62c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b633  lea     r8, WPP_c50f5e74c25e3036c795d57fb324c23c_Traceguids
0x18003b63a  mov     edx, 1Bh
0x18003b63f  mov     r9d, eax
0x18003b642  mov     rcx, [rcx+10h]
0x18003b646  call    WPP_SF_d
0x18003b64b  jmp     loc_18003B3AC
0x18003b650  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b657  lea     rax, WPP_GLOBAL_Control
0x18003b65e  cmp     rcx, rax
0x18003b661  jz      loc_18003B3BC
0x18003b667  test    byte ptr [rcx+1Ch], 1
0x18003b66b  jz      loc_18003B3BC
0x18003b671  cmp     byte ptr [rcx+19h], 4
0x18003b675  jb      loc_18003B3BC
0x18003b67b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18003b680  mov     edx, 17h
0x18003b685  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b68c  lea     r8, WPP_c50f5e74c25e3036c795d57fb324c23c_Traceguids
0x18003b693  mov     r9d, eax
0x18003b696  mov     rcx, [rcx+10h]
0x18003b69a  call    WPP_SF_d
0x18003b69f  jmp     loc_18003B3BC
```
