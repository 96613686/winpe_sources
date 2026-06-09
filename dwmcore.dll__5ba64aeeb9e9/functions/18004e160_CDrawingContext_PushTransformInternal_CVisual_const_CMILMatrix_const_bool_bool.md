# CDrawingContext::PushTransformInternal(CVisual const *,CMILMatrix const *,bool,bool)

- ea: `0x18004e160`
- end: `0x18004eaa3`
- name: `?PushTransformInternal@CDrawingContext@@IEAAJPEBVCVisual@@PEBVCMILMatrix@@_N2@Z`
- size: `2371`
- prototype: `int(CDrawingContext *__hidden this, const struct CVisual *, const struct CMILMatrix *, bool, bool)`
- caller_count: `22`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002291c`
- `0x18003de10`
- `0x18005d470`
- `0x18005f4d0`
- `0x180062b50`
- `0x180063748`
- `0x1800641c0`
- `0x18007cbc4`
- `0x18008d9d4`
- `0x18009c4d0`
- `0x1800ce430`
- `0x1800fd774`
- `0x1800fe908`
- `0x18010c00c`
- `0x18013e5a0`
- `0x1801402c8`
- `0x18014e6f0`
- `0x1801c7c00`
- `0x1802213cc`
- `0x180232a10`
- `0x180236e74`
- `0x18024b600`

## callees

- `0x18004e160`
- `0x18004fce4`
- `0x180050270`
- `0x180051680`
- `0x1800516b0`
- `0x18008c810`
- `0x1800b0ae0`
- `0x180229444`

## string_xrefs

- `0x18004e35a`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x18004e371`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x18004e4c0`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x18004e4d7`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x18004e68c`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x18004e6a3`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x18004e936`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x18004e98f`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x18004e9a6`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`

## pseudocode

```c
__int64 __fastcall CDrawingContext::PushTransformInternal(
        CDrawingContext *this,
        const struct CVisual *a2,
        const struct CMILMatrix *a3,
        char a4,
        unsigned int a5)
{
  char v5; // si
  __int64 v10; // r14
  __int64 v11; // rax
  __int64 v12; // r12
  unsigned __int64 v13; // rax
  unsigned int v14; // esi
  unsigned __int64 v15; // r12
  void *v16; // rax
  void *v17; // r13
  __int64 v18; // rax
  __int64 v19; // rcx
  int v20; // edx
  unsigned int v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rdx
  int v26; // eax
  unsigned int v27; // eax
  int v28; // eax
  _BYTE *v29; // rdx
  char v30; // cl
  char v31; // bp
  __int64 v32; // rdx
  unsigned int v33; // edi
  __int64 result; // rax
  __int64 v35; // rcx
  __int64 v36; // rax
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int64 v40; // rax
  __int128 v41; // xmm1
  __int128 v42; // xmm0
  __int128 v43; // xmm1
  __int64 v44; // rdx
  unsigned int v45; // eax
  char v46; // al
  unsigned int v47; // r9d
  unsigned int v48; // eax
  __int64 v49; // rax
  int v50; // edi
  __int64 v51; // rcx
  unsigned __int64 v52; // rax
  unsigned __int64 v53; // r12
  const void *v54; // r15
  void *v55; // rax
  void *v56; // rbp
  unsigned int v57; // ecx
  __int64 v58; // rdx
  int v59; // eax
  int v60; // eax
  int v61; // ecx
  unsigned int v62; // ebp
  const void *v63; // r13
  void *v64; // r12
  __int32 v65; // xmm2_4
  int v66; // eax
  __int64 v67; // rcx
  unsigned __int64 v68; // rax
  __int64 v69; // rdx
  unsigned int v70; // ebp
  unsigned int v71; // edi
  const void *v72; // r13
  void *v73; // rax
  void *v74; // r12
  int v75; // [rsp+20h] [rbp-118h]
  int v76; // [rsp+20h] [rbp-118h]
  int v77; // [rsp+20h] [rbp-118h]
  int v78; // [rsp+20h] [rbp-118h]
  int v79; // [rsp+20h] [rbp-118h]
  void *Src; // [rsp+40h] [rbp-F8h] BYREF
  size_t Size; // [rsp+48h] [rbp-F0h]
  _OWORD v82[4]; // [rsp+50h] [rbp-E8h] BYREF
  int v83; // [rsp+90h] [rbp-A8h]
  _OWORD v84[4]; // [rsp+A0h] [rbp-98h] BYREF
  int v85; // [rsp+E0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v5 = 0;
  v10 = 64;
  if ( !(_BYTE)a5 )
    goto LABEL_14;
  Size = 0;
  v11 = *((unsigned int *)this + 67);
  if ( *((_DWORD *)this + 66) == (_DWORD)v11 )
  {
    v12 = (unsigned int)v11;
    v13 = 2 * v11;
    if ( v13 > 0xFFFFFFFF )
    {
      v32 = 95;
    }
    else
    {
      v14 = 64;
      if ( (unsigned int)v13 > 0x40 )
        v14 = v13;
      v15 = 16 * v12;
      if ( v15 <= 0xFFFFFFFF )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / v14 <= 0x10 )
        {
          v33 = -2147024809;
        }
        else
        {
          Src = (void *)*((_QWORD *)this + 32);
          v16 = MIDL_user_allocate(16LL * v14);
          v17 = v16;
          if ( v16 )
          {
            if ( Src && (_DWORD)v15 )
              memcpy_0(v16, Src, (unsigned int)v15);
            operator delete(*((void **)this + 32));
            *((_QWORD *)this + 32) = v17;
            *((_DWORD *)this + 67) = v14;
            goto LABEL_11;
          }
          v33 = -2147024882;
        }
        v32 = 101;
LABEL_27:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v32,
          (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
          (const char *)v33,
          v75);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8B,
          (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
          (const char *)v33,
          v76);
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v33, 0xCF7u, 0);
        return v33;
      }
      v32 = 98;
    }
    v33 = -2147024362;
    goto LABEL_27;
  }
LABEL_11:
  v5 = 1;
  v18 = *((_QWORD *)this + 32);
  v19 = 2LL * *((unsigned int *)this + 66);
  v20 = Size;
  *(_DWORD *)(v18 + 8 * v19) = 5;
  *(_DWORD *)(v18 + 8 * v19 + 4) = v20;
  *(_QWORD *)(v18 + 8 * v19 + 8) = a2;
  v21 = *((_DWORD *)this + 69);
  if ( v21 <= ++*((_DWORD *)this + 66) )
    v21 = *((_DWORD *)this + 66);
  *((_DWORD *)this + 69) = v21;
LABEL_14:
  v22 = *((_DWORD *)this + 72);
  if ( v22 && a4 )
  {
    v83 = 0;
    v35 = (unsigned int)(v22 - 1);
    v36 = *((_QWORD *)this + 35);
    v37 = *(_OWORD *)(68 * v35 + v36 + 16);
    v84[0] = *(_OWORD *)(68 * v35 + v36);
    v38 = *(_OWORD *)(68 * v35 + v36 + 32);
    v84[1] = v37;
    v39 = *(_OWORD *)(68 * v35 + v36 + 48);
    LODWORD(v36) = *(_DWORD *)(68 * v35 + v36 + 64);
    v84[2] = v38;
    v84[3] = v39;
    v85 = v36;
    CMILMatrix::Multiply(a3, (const struct CMILMatrix *)v84, (struct CMILMatrix *)v82);
    v40 = *((unsigned int *)this + 73);
    if ( *((_DWORD *)this + 72) != (_DWORD)v40 )
    {
LABEL_34:
      v24 = *((_QWORD *)this + 35);
      v41 = v82[1];
      v25 = 68LL * *((unsigned int *)this + 72);
      v26 = v83;
      *(_OWORD *)(v25 + v24) = v82[0];
      v42 = v82[2];
      *(_OWORD *)(v25 + v24 + 16) = v41;
      v43 = v82[3];
      *(_OWORD *)(v25 + v24 + 32) = v42;
      *(_OWORD *)(v25 + v24 + 48) = v43;
      goto LABEL_18;
    }
    v67 = *((unsigned int *)this + 73);
    v68 = 2 * v40;
    if ( v68 <= 0xFFFFFFFF )
    {
      v70 = 8;
      if ( (unsigned int)v68 > 8 )
        v70 = v68;
      v71 = 68 * v67;
      if ( (unsigned __int64)(68 * v67) <= 0xFFFFFFFF )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / v70 <= 0x44 )
        {
          v33 = -2147024809;
        }
        else
        {
          v72 = (const void *)*((_QWORD *)this + 35);
          v73 = MIDL_user_allocate(68LL * v70);
          v74 = v73;
          if ( v73 )
          {
            if ( v72 && v71 )
              memcpy_0(v73, v72, v71);
            operator delete(*((void **)this + 35));
            *((_QWORD *)this + 35) = v74;
            *((_DWORD *)this + 73) = v70;
            goto LABEL_34;
          }
          v33 = -2147024882;
        }
        v69 = 101;
LABEL_97:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v69,
          (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
          (const char *)v33,
          v75);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8B,
          (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
          (const char *)v33,
          v79);
        v45 = 69;
        goto LABEL_39;
      }
      v69 = 98;
    }
    else
    {
      v69 = 95;
    }
    v33 = -2147024362;
    goto LABEL_97;
  }
  v23 = *((unsigned int *)this + 73);
  if ( v22 == (_DWORD)v23 )
  {
    if ( (unsigned __int64)(2 * v23) <= 0xFFFFFFFF )
    {
      v62 = 8;
      if ( (unsigned int)(2 * v23) > 8 )
        v62 = 2 * v23;
      Size = 68 * v23;
      if ( (unsigned __int64)(68 * v23) <= 0xFFFFFFFF )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / v62 <= 0x44 )
        {
          v33 = -2147024809;
        }
        else
        {
          v63 = (const void *)*((_QWORD *)this + 35);
          v64 = MIDL_user_allocate(68LL * v62);
          if ( v64 )
          {
            if ( v63 && (_DWORD)Size )
              memcpy_0(v64, v63, (unsigned int)Size);
            operator delete(*((void **)this + 35));
            *((_QWORD *)this + 35) = v64;
            *((_DWORD *)this + 73) = v62;
            goto LABEL_17;
          }
          v33 = -2147024882;
        }
        v44 = 101;
        goto LABEL_38;
      }
      v44 = 98;
    }
    else
    {
      v44 = 95;
    }
    v33 = -2147024362;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v44,
      (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
      (const char *)v33,
      v75);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
      (const char *)v33,
      v77);
    v45 = 54;
LABEL_39:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v33, v45, 0);
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v33, 0xCFCu, 0);
    goto LABEL_65;
  }
LABEL_17:
  v24 = *((_QWORD *)this + 35);
  v25 = 68LL * *((unsigned int *)this + 72);
  *(_OWORD *)(v25 + v24) = *(_OWORD *)a3;
  *(_OWORD *)(v25 + v24 + 16) = *((_OWORD *)a3 + 1);
  *(_OWORD *)(v25 + v24 + 32) = *((_OWORD *)a3 + 2);
  *(_OWORD *)(v25 + v24 + 48) = *((_OWORD *)a3 + 3);
  v26 = *((_DWORD *)a3 + 16);
LABEL_18:
  *(_DWORD *)(v25 + v24 + 64) = v26;
  ++*((_DWORD *)this + 72);
  v27 = *((_DWORD *)this + 75);
  if ( v27 <= *((_DWORD *)this + 72) )
    v27 = *((_DWORD *)this + 72);
  *((_DWORD *)this + 75) = v27;
  v28 = *((_DWORD *)this + 72);
  if ( v28 )
    v29 = (_BYTE *)(*((_QWORD *)this + 35) + 68LL * (unsigned int)(v28 - 1));
  else
    v29 = &CMILMatrix::Identity;
  v30 = v29[65];
  if ( (v30 & 0x20) == 0 && 4 * (v30 & 0xF0) != 0 )
    goto LABEL_69;
  if ( (v30 & 0x20) != 0 )
  {
    v31 = 1;
    goto LABEL_42;
  }
  COERCE_FLOAT(v65 = _mm_load_si128((const __m128i *)&_xmm).m128i_i32[0]);
  if ( COERCE_FLOAT(
         COERCE_UNSIGNED_INT(
           (float)((float)((float)(COERCE_FLOAT(*((_DWORD *)v29 + 7) & v65) * 61440.0)
                         + (float)(COERCE_FLOAT(*((_DWORD *)v29 + 3) & v65) * 61440.0))
                 + COERCE_FLOAT(*((_DWORD *)v29 + 15) & v65))
         - 1.0)
       & v65) < 0.000081380211 )
  {
    v31 = 1;
    v46 = -16;
  }
  else
  {
    v31 = 0;
    v46 = 16;
  }
  v29[65] = v46 ^ (v46 ^ v30) & 0xCF;
  if ( !v31 )
LABEL_69:
    v31 = 0;
LABEL_42:
  v47 = *((_DWORD *)this + 79);
  if ( *((_DWORD *)this + 78) != v47 )
    goto LABEL_43;
  a5 = 0;
  Src = 0;
  v66 = Grow(1u, 0x40u, (unsigned int)a3, v47, *((void **)this + 38), &a5, &Src);
  v33 = v66;
  if ( v66 >= 0 )
  {
    operator delete(*((void **)this + 38));
    *((_QWORD *)this + 38) = Src;
    *((_DWORD *)this + 79) = a5;
LABEL_43:
    *(_BYTE *)((unsigned int)(*((_DWORD *)this + 78))++ + *((_QWORD *)this + 38)) = v31 ^ 1;
    v48 = *((_DWORD *)this + 81);
    if ( v48 <= *((_DWORD *)this + 78) )
      v48 = *((_DWORD *)this + 78);
    *((_DWORD *)this + 81) = v48;
    if ( !a2 )
      return 0;
    v49 = *((unsigned int *)this + 85);
    v50 = *((_DWORD *)this + 72);
    if ( *((_DWORD *)this + 84) != (_DWORD)v49 )
    {
LABEL_55:
      *(_DWORD *)(*((_QWORD *)this + 41) + 4LL * *((unsigned int *)this + 84)) = v50;
      v57 = *((_DWORD *)this + 87);
      if ( v57 <= ++*((_DWORD *)this + 84) )
        v57 = *((_DWORD *)this + 84);
      *((_DWORD *)this + 87) = v57;
      return 0;
    }
    v51 = (unsigned int)v49;
    v52 = 2 * v49;
    if ( v52 > 0xFFFFFFFF )
    {
      v58 = 95;
    }
    else
    {
      v53 = 4 * v51;
      if ( (unsigned int)v52 > 0x40 )
        v10 = (unsigned int)v52;
      if ( v53 <= 0xFFFFFFFF )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / (unsigned int)v10 <= 4 )
        {
          v33 = -2147024809;
        }
        else
        {
          v54 = (const void *)*((_QWORD *)this + 41);
          v55 = MIDL_user_allocate(4 * v10);
          v56 = v55;
          if ( v55 )
          {
            if ( v54 && (_DWORD)v53 )
              memcpy_0(v55, v54, (unsigned int)v53);
            operator delete(*((void **)this + 41));
            *((_QWORD *)this + 41) = v56;
            *((_DWORD *)this + 85) = v10;
            goto LABEL_55;
          }
          v33 = -2147024882;
        }
        v58 = 101;
        goto LABEL_61;
      }
      v58 = 98;
    }
    v33 = -2147024362;
LABEL_61:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v58,
      (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
      (const char *)v33,
      v75);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
      (const char *)v33,
      v78);
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v33, 0xD06u, 0);
    v59 = *((_DWORD *)this + 78);
    if ( v59 )
      *((_DWORD *)this + 78) = v59 - 1;
    goto LABEL_63;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8B,
    (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
    (const char *)(unsigned int)v66,
    v75);
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v33, 0xD00u, 0);
LABEL_63:
  v60 = *((_DWORD *)this + 72);
  if ( v60 )
    *((_DWORD *)this + 72) = v60 - 1;
LABEL_65:
  if ( !v5 )
    return v33;
  v61 = *((_DWORD *)this + 66);
  result = v33;
  if ( v61 )
    *((_DWORD *)this + 66) = v61 - 1;
  return result;
}

```

## disassembly

```asm
0x18004e160  push    rbx
0x18004e162  push    rbp
0x18004e163  push    rsi
0x18004e164  push    rdi
0x18004e165  push    r12
0x18004e167  push    r13
0x18004e169  push    r14
0x18004e16b  push    r15
0x18004e16d  sub     rsp, 0F8h
0x18004e174  xor     sil, sil
0x18004e177  movzx   ebp, r9b
0x18004e17b  mov     rdi, r8
0x18004e17e  mov     r15, rdx
0x18004e181  mov     rbx, rcx
0x18004e184  mov     r13d, 0FFFFFFFFh
0x18004e18a  mov     r14d, 40h ; '@'
0x18004e190  cmp     byte ptr [rsp+138h+arg_20], sil
0x18004e198  jz      loc_18004E28F
0x18004e19e  xor     eax, eax
0x18004e1a0  mov     [rsp+138h+Size], rax
0x18004e1a5  mov     eax, [rcx+10Ch]
0x18004e1ab  cmp     [rcx+108h], eax
0x18004e1b1  jnz     loc_18004E24A
0x18004e1b7  mov     r12d, eax
0x18004e1ba  add     rax, rax
0x18004e1bd  cmp     rax, r13
0x18004e1c0  ja      loc_18004E348
0x18004e1c6  cmp     eax, r14d
0x18004e1c9  mov     esi, r14d
0x18004e1cc  cmova   esi, eax
0x18004e1cf  shl     r12, 4
0x18004e1d3  cmp     r12, r13
0x18004e1d6  ja      loc_18004E3BE
0x18004e1dc  test    esi, esi
0x18004e1de  jz      loc_18004E807
0x18004e1e4  xor     edx, edx
0x18004e1e6  mov     ecx, esi
0x18004e1e8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18004e1ef  div     rcx
0x18004e1f2  cmp     rax, 10h
0x18004e1f6  jbe     loc_18004E807
0x18004e1fc  mov     rax, [rbx+100h]
0x18004e203  shl     rcx, 4; size
0x18004e207  mov     [rsp+138h+Src], rax
0x18004e20c  call    MIDL_user_allocate
0x18004e211  mov     r13, rax
0x18004e214  test    rax, rax
0x18004e217  jz      loc_18004E3C5
0x18004e21d  mov     rdx, [rsp+138h+Src]; Src
0x18004e222  test    rdx, rdx
0x18004e225  jnz     loc_18004E7EE
0x18004e22b  mov     rcx, [rbx+100h]; void *
0x18004e232  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004e237  mov     [rbx+100h], r13
0x18004e23e  mov     r13d, 0FFFFFFFFh
0x18004e244  mov     [rbx+10Ch], esi
0x18004e24a  mov     ecx, [rbx+108h]
0x18004e250  mov     sil, 1
0x18004e253  mov     rax, [rbx+100h]
0x18004e25a  add     rcx, rcx
0x18004e25d  mov     rdx, [rsp+138h+Size]
0x18004e262  mov     dword ptr [rax+rcx*8], 5
0x18004e269  mov     [rax+rcx*8+4], edx
0x18004e26d  mov     [rax+rcx*8+8], r15
0x18004e272  mov     eax, [rbx+114h]
0x18004e278  inc     dword ptr [rbx+108h]
0x18004e27e  mov     ecx, [rbx+108h]
0x18004e284  cmp     eax, ecx
0x18004e286  cmovbe  eax, ecx
0x18004e289  mov     [rbx+114h], eax
0x18004e28f  mov     eax, [rbx+120h]
0x18004e295  test    eax, eax
0x18004e297  jz      short loc_18004E2A2
0x18004e299  test    bpl, bpl
0x18004e29c  jnz     loc_18004E3D1
0x18004e2a2  mov     ecx, [rbx+124h]
0x18004e2a8  cmp     eax, ecx
0x18004e2aa  jz      loc_18004E49E
0x18004e2b0  mov     eax, [rbx+120h]
0x18004e2b6  movups  xmm0, xmmword ptr [rdi]
0x18004e2b9  mov     rcx, [rbx+118h]
0x18004e2c0  imul    rdx, rax, 44h ; 'D'
0x18004e2c4  movups  xmmword ptr [rdx+rcx], xmm0
0x18004e2c8  movups  xmm1, xmmword ptr [rdi+10h]
0x18004e2cc  movups  xmmword ptr [rdx+rcx+10h], xmm1
0x18004e2d1  movups  xmm0, xmmword ptr [rdi+20h]
0x18004e2d5  movups  xmmword ptr [rdx+rcx+20h], xmm0
0x18004e2da  movups  xmm1, xmmword ptr [rdi+30h]
0x18004e2de  movups  xmmword ptr [rdx+rcx+30h], xmm1
0x18004e2e3  mov     eax, [rdi+40h]
0x18004e2e6  mov     [rdx+rcx+40h], eax
0x18004e2ea  inc     dword ptr [rbx+120h]
0x18004e2f0  mov     ecx, [rbx+120h]
0x18004e2f6  mov     eax, [rbx+12Ch]
0x18004e2fc  cmp     eax, ecx
0x18004e2fe  cmovbe  eax, ecx
0x18004e301  mov     [rbx+12Ch], eax
0x18004e307  mov     eax, [rbx+120h]
0x18004e30d  test    eax, eax
0x18004e30f  jz      loc_18004E81B
0x18004e315  lea     ecx, [rax-1]
0x18004e318  imul    rdx, rcx, 44h ; 'D'
0x18004e31c  add     rdx, [rbx+118h]
0x18004e323  movzx   ecx, byte ptr [rdx+41h]
0x18004e327  movzx   eax, cl
0x18004e32a  and     al, 0F0h
0x18004e32c  shl     al, 2
0x18004e32f  test    al, al
0x18004e331  jg      loc_18004E72E
0x18004e337  test    cl, 20h
0x18004e33a  jz      loc_18004E827
0x18004e340  mov     bpl, 1
0x18004e343  jmp     loc_18004E54F
0x18004e348  mov     edx, 5Fh ; '_'; void *
0x18004e34d  mov     edi, 80070216h
0x18004e352  mov     rcx, [rsp+138h]; this
0x18004e35a  lea     r8, aOnecoreuapWind_170; "onecoreuap\\windows\\DWM\\dwmcore\\comm"...
0x18004e361  mov     r9d, edi; char *
0x18004e364  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e369  mov     rcx, [rsp+138h]; this
0x18004e371  lea     r8, aOnecoreuapWind_170; "onecoreuap\\windows\\DWM\\dwmcore\\comm"...
0x18004e378  mov     r9d, edi; char *
0x18004e37b  mov     edx, 8Bh; void *
0x18004e380  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e385  mov     r9d, edi; int
0x18004e388  mov     [rsp+138h+var_110], 0; void *
0x18004e391  xor     r8d, r8d; unsigned int
0x18004e394  mov     dword ptr [rsp+138h+var_118], 0CF7h; unsigned int
0x18004e39c  xor     edx, edx; int *
0x18004e39e  mov     ecx, 14h; unsigned int
0x18004e3a3  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18004e3a8  mov     eax, edi
0x18004e3aa  add     rsp, 0F8h
0x18004e3b1  pop     r15
0x18004e3b3  pop     r14
0x18004e3b5  pop     r13
0x18004e3b7  pop     r12
0x18004e3b9  pop     rdi
0x18004e3ba  pop     rsi
0x18004e3bb  pop     rbp
0x18004e3bc  pop     rbx
0x18004e3bd  retn
0x18004e3be  mov     edx, 62h ; 'b'
0x18004e3c3  jmp     short loc_18004E34D
0x18004e3c5  mov     edi, 8007000Eh
0x18004e3ca  mov     edx, 65h ; 'e'
0x18004e3cf  jmp     short loc_18004E352
0x18004e3d1  mov     [rsp+138h+var_A8], 0
0x18004e3dc  test    eax, eax
0x18004e3de  jz      loc_18004EA94
0x18004e3e4  lea     ecx, [rax-1]
0x18004e3e7  mov     rax, [rbx+118h]
0x18004e3ee  imul    rdx, rcx, 44h ; 'D'
0x18004e3f2  lea     r8, [rsp+138h+var_E8]; struct CMILMatrix *
0x18004e3f7  mov     rcx, rdi; struct CMILMatrix *
0x18004e3fa  movups  xmm0, xmmword ptr [rdx+rax]
0x18004e3fe  movups  xmm1, xmmword ptr [rdx+rax+10h]
0x18004e403  movaps  [rsp+138h+var_98], xmm0
0x18004e40b  movups  xmm0, xmmword ptr [rdx+rax+20h]
0x18004e410  movaps  [rsp+138h+var_88], xmm1
0x18004e418  movups  xmm1, xmmword ptr [rdx+rax+30h]
0x18004e41d  mov     eax, [rdx+rax+40h]
0x18004e421  lea     rdx, [rsp+138h+var_98]; struct CMILMatrix *
0x18004e429  movaps  [rsp+138h+var_78], xmm0
0x18004e431  movaps  [rsp+138h+var_68], xmm1
0x18004e439  mov     [rsp+138h+var_58], eax
0x18004e440  call    ?Multiply@CMILMatrix@@SAXAEBV1@0PEAV1@@Z; CMILMatrix::Multiply(CMILMatrix const &,CMILMatrix const &,CMILMatrix *)
0x18004e445  mov     eax, [rbx+124h]
0x18004e44b  cmp     [rbx+120h], eax
0x18004e451  jz      loc_18004E972
0x18004e457  mov     eax, [rbx+120h]
0x18004e45d  mov     rcx, [rbx+118h]
0x18004e464  movaps  xmm0, [rsp+138h+var_E8]
0x18004e469  movaps  xmm1, [rsp+138h+var_D8]
0x18004e46e  imul    rdx, rax, 44h ; 'D'
0x18004e472  mov     eax, [rsp+138h+var_A8]
0x18004e479  movups  xmmword ptr [rdx+rcx], xmm0
0x18004e47d  movaps  xmm0, [rsp+138h+var_C8]
0x18004e482  movups  xmmword ptr [rdx+rcx+10h], xmm1
0x18004e487  movaps  xmm1, [rsp+138h+var_B8]
0x18004e48f  movups  xmmword ptr [rdx+rcx+20h], xmm0
0x18004e494  movups  xmmword ptr [rdx+rcx+30h], xmm1
0x18004e499  jmp     loc_18004E2E6
0x18004e49e  lea     rax, [rcx+rcx]
0x18004e4a2  mov     rdx, rcx
0x18004e4a5  cmp     rax, r13
0x18004e4a8  jbe     loc_18004E76F
0x18004e4ae  mov     edx, 5Fh ; '_'; void *
0x18004e4b3  mov     edi, 80070216h
0x18004e4b8  mov     rcx, [rsp+138h]; this
0x18004e4c0  lea     r8, aOnecoreuapWind_170; "onecoreuap\\windows\\DWM\\dwmcore\\comm"...
0x18004e4c7  mov     r9d, edi; char *
0x18004e4ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e4cf  mov     rcx, [rsp+138h]; this
0x18004e4d7  lea     r8, aOnecoreuapWind_170; "onecoreuap\\windows\\DWM\\dwmcore\\comm"...
0x18004e4de  mov     r9d, edi; char *
0x18004e4e1  mov     edx, 8Bh; void *
0x18004e4e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e4eb  mov     eax, 36h ; '6'
0x18004e4f0  mov     r9d, edi; int
0x18004e4f3  mov     [rsp+138h+var_110], 0; void *
0x18004e4fc  xor     r8d, r8d; unsigned int
0x18004e4ff  mov     dword ptr [rsp+138h+var_118], eax; unsigned int
0x18004e503  xor     edx, edx; int *
0x18004e505  mov     ecx, 14h; unsigned int
0x18004e50a  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18004e50f  mov     r9d, edi; int
0x18004e512  mov     [rsp+138h+var_110], 0; void *
0x18004e51b  xor     r8d, r8d; unsigned int
0x18004e51e  mov     dword ptr [rsp+138h+var_118], 0CFCh; unsigned int
0x18004e526  xor     edx, edx; int *
0x18004e528  mov     ecx, 14h; unsigned int
0x18004e52d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18004e532  jmp     loc_18004E6FE
0x18004e537  mov     bpl, 1
0x18004e53a  mov     al, 0F0h
0x18004e53c  xor     cl, al
0x18004e53e  and     cl, 0CFh
0x18004e541  xor     cl, al
0x18004e543  mov     [rdx+41h], cl
0x18004e546  test    bpl, bpl
0x18004e549  jz      loc_18004E72E
0x18004e54f  mov     r9d, [rbx+13Ch]; unsigned int
0x18004e556  cmp     [rbx+138h], r9d
0x18004e55d  jz      loc_18004E885
0x18004e563  mov     ecx, [rbx+138h]
0x18004e569  xor     bpl, 1
0x18004e56d  mov     rax, [rbx+130h]
0x18004e574  mov     [rcx+rax], bpl
0x18004e578  inc     dword ptr [rbx+138h]
0x18004e57e  mov     eax, [rbx+144h]
0x18004e584  mov     ecx, [rbx+138h]
0x18004e58a  cmp     eax, ecx
0x18004e58c  cmovbe  eax, ecx
0x18004e58f  mov     [rbx+144h], eax
0x18004e595  test    r15, r15
0x18004e598  jz      loc_18004E673
0x18004e59e  mov     eax, [rbx+154h]
0x18004e5a4  mov     edi, [rbx+120h]
0x18004e5aa  cmp     [rbx+150h], eax
0x18004e5b0  jnz     loc_18004E646
0x18004e5b6  mov     ecx, eax
0x18004e5b8  mov     edx, 0FFFFFFFFh
0x18004e5bd  add     rax, rax
0x18004e5c0  cmp     rax, rdx
0x18004e5c3  ja      loc_18004E67A
0x18004e5c9  cmp     eax, r14d
0x18004e5cc  lea     r12, ds:0[rcx*4]
0x18004e5d4  cmova   r14d, eax
0x18004e5d8  cmp     r12, rdx
0x18004e5db  ja      loc_18004E724
0x18004e5e1  test    r14d, r14d
0x18004e5e4  jz      loc_18004E915
0x18004e5ea  xor     edx, edx
0x18004e5ec  mov     ecx, r14d
0x18004e5ef  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18004e5f6  div     rcx
0x18004e5f9  cmp     rax, 4
0x18004e5fd  jbe     loc_18004E915
0x18004e603  mov     r15, [rbx+148h]
0x18004e60a  lea     rcx, ds:0[r14*4]; size
0x18004e612  call    MIDL_user_allocate
0x18004e617  mov     rbp, rax
0x18004e61a  test    rax, rax
0x18004e61d  jz      loc_18004E760
0x18004e623  test    r15, r15
0x18004e626  jnz     loc_18004E8F9
0x18004e62c  mov     rcx, [rbx+148h]; void *
0x18004e633  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004e638  mov     [rbx+148h], rbp
0x18004e63f  mov     [rbx+154h], r14d
0x18004e646  mov     edx, [rbx+150h]
0x18004e64c  mov     rcx, [rbx+148h]
0x18004e653  mov     [rcx+rdx*4], edi
0x18004e656  mov     ecx, [rbx+15Ch]
0x18004e65c  inc     dword ptr [rbx+150h]
0x18004e662  mov     edx, [rbx+150h]
0x18004e668  cmp     ecx, edx
0x18004e66a  cmovbe  ecx, edx
0x18004e66d  mov     [rbx+15Ch], ecx
0x18004e673  xor     eax, eax
0x18004e675  jmp     loc_18004E3AA
0x18004e67a  mov     edx, 5Fh ; '_'; void *
0x18004e67f  mov     edi, 80070216h
0x18004e684  mov     rcx, [rsp+138h]; this
0x18004e68c  lea     r8, aOnecoreuapWind_170; "onecoreuap\\windows\\DWM\\dwmcore\\comm"...
0x18004e693  mov     r9d, edi; char *
0x18004e696  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e69b  mov     rcx, [rsp+138h]; this
0x18004e6a3  lea     r8, aOnecoreuapWind_170; "onecoreuap\\windows\\DWM\\dwmcore\\comm"...
0x18004e6aa  mov     r9d, edi; char *
0x18004e6ad  mov     edx, 8Bh; void *
0x18004e6b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e6b7  mov     r9d, edi; int
0x18004e6ba  mov     [rsp+138h+var_110], 0; void *
0x18004e6c3  xor     r8d, r8d; unsigned int
0x18004e6c6  mov     dword ptr [rsp+138h+var_118], 0D06h; unsigned int
0x18004e6ce  xor     edx, edx; int *
0x18004e6d0  mov     ecx, 14h; unsigned int
0x18004e6d5  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
  ... truncated ...
```
