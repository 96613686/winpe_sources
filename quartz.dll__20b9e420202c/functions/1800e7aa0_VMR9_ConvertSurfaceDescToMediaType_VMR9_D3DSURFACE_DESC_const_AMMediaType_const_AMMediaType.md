# VMR9::ConvertSurfaceDescToMediaType(VMR9::_D3DSURFACE_DESC const *,_AMMediaType const *,_AMMediaType * *)

- ea: `0x1800e7aa0`
- end: `0x1800e7e4f`
- name: `?ConvertSurfaceDescToMediaType@VMR9@@YAJPEBU_D3DSURFACE_DESC@1@PEBU_AMMediaType@@PEAPEAU3@@Z`
- size: `943`
- prototype: `int(VMR9 *__hidden this, const struct _D3DSURFACE_DESC *, const struct _AMMediaType *, struct _AMMediaType **)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x1800d6808`
- `0x1800d7dec`
- `0x1800d9544`
- `0x1800de1cc`
- `0x1800de6a0`

## callees

- `0x180026424`
- `0x18002f03c`
- `0x1800c1fcc`
- `0x1800e7a28`
- `0x1800e7aa0`
- `0x1800e7e58`
- `0x180144134`

## import_xrefs

- `USER32!IsRectEmpty` at `0x1800e7d2a`
- `USER32!IsRectEmpty` at `0x1800e7d57`
- `USER32!IsRectEmpty` at `0x1800e7de1`
- `USER32!IsRectEmpty` at `0x1800e7e0e`
- `USER32!IsRectEmpty` at `0x1800e7d2a`
- `USER32!IsRectEmpty` at `0x1800e7d57`
- `USER32!IsRectEmpty` at `0x1800e7de1`
- `USER32!IsRectEmpty` at `0x1800e7e0e`

## pseudocode

```c
__int64 __fastcall VMR9::ConvertSurfaceDescToMediaType(
        VMR9 *this,
        struct _D3DSURFACE_DESC *a2,
        struct _AMMediaType *a3,
        struct _AMMediaType **a4)
{
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 result; // rax
  const struct _AMMediaType *v10; // rdx
  unsigned int v11; // ebp
  struct tagBITMAPINFOHEADER *v12; // rax
  enum _D3DFORMAT v13; // edx
  struct _AMMediaType *v14; // rcx
  struct tagBITMAPINFOHEADER *v15; // r10
  int v16; // eax
  __int16 v17; // ax
  __int64 v18; // r10
  enum _D3DFORMAT v19; // edx
  struct VMR9::MTLookUp *TableEntry; // rax
  const struct _AMMediaType *v21; // rdx
  unsigned __int16 v22; // r9
  __int64 v23; // r10
  int v24; // r11d
  int v25; // eax
  struct tagBITMAPINFOHEADER *v26; // rax
  __int64 *v27; // rcx
  unsigned int v28; // eax
  __int64 v29; // r10
  int v30; // r11d
  int v31; // ecx
  int v32; // ecx
  int v33; // ecx
  GUID v34; // xmm0
  unsigned int i; // ecx
  __int64 v36; // rdx
  _QWORD *v37; // rbx
  __int64 v38; // rax
  __int64 v39; // rsi
  const RECT *v40; // rbx
  int *v41; // rdi
  int right; // ecx
  int v43; // eax
  int top; // ecx
  int v45; // eax
  int v46; // eax
  int v47; // eax
  int v48; // eax
  int v49; // eax
  __int64 v50; // rax
  __int64 v51; // rsi
  int *v52; // rdi
  int left; // ecx
  int v54; // eax
  int bottom; // ecx
  int v56; // eax
  int v57; // eax
  int v58; // eax
  int v59; // eax
  _BYTE v60[72]; // [rsp+20h] [rbp-48h] BYREF

  *(_QWORD *)&a3->majortype.Data1 = 0;
  v7 = *(_QWORD *)&a2[1].Pool - *(_QWORD *)&FORMAT_VideoInfo.Data1;
  if ( !v7 )
    v7 = *(_QWORD *)&a2[1].MultiSampleQuality - *(_QWORD *)FORMAT_VideoInfo.Data4;
  if ( !v7 && a2[2].Usage >= 0x58 )
    goto LABEL_9;
  v8 = *(_QWORD *)&a2[1].Pool - *(_QWORD *)&FORMAT_VideoInfo2.Data1;
  if ( !v8 )
    v8 = *(_QWORD *)&a2[1].MultiSampleQuality - *(_QWORD *)FORMAT_VideoInfo2.Data4;
  if ( !v8 && a2[2].Usage >= 0x70 )
  {
LABEL_9:
    result = VMR9::AllocVideoMediaType((VMR9 *)a2, a3, (struct _AMMediaType **)a3);
    v11 = result;
    if ( (int)result < 0 )
      return result;
    v12 = VMR9::GetbmiHeader(*(VMR9 **)&a3->majortype.Data1, v10);
    v15 = v12;
    if ( !v12 )
    {
      FreeMediaType(v14);
      return 2147500037LL;
    }
    v12->biSize = 40;
    v12->biWidth = *((_DWORD *)this + 6);
    v16 = -*((_DWORD *)this + 7);
    v15->biPlanes = 1;
    v15->biHeight = v16;
    v17 = VMR9::BitCountFromFormat((VMR9 *)*(unsigned int *)this, v13);
    *(_WORD *)(v18 + 14) = v17;
    TableEntry = VMR9::FindTableEntry((VMR9 *)*(unsigned int *)this, v19);
    if ( !TableEntry || *((_DWORD *)TableEntry + 5) )
      v25 = 0;
    else
      v25 = *((_DWORD *)TableEntry + 6);
    *(_DWORD *)(v23 + 16) = v25;
    *(_QWORD *)(v23 + 32) = 0;
    if ( v25 )
      goto LABEL_27;
    v26 = VMR9::GetbmiHeader((VMR9 *)a2, v21);
    v27 = qword_1801A2488;
    if ( v26 )
      v27 = (__int64 *)v26;
    if ( ((v22 - 16) & 0xFFEF) != 0 )
      goto LABEL_27;
    if ( *((_DWORD *)v27 + 4) != 3 )
    {
      if ( v22 == 32 )
      {
        if ( *(_DWORD *)this == 22 )
          goto LABEL_29;
      }
      else
      {
        if ( v22 != 16 )
          goto LABEL_27;
        if ( *(_DWORD *)this == 24 )
          goto LABEL_29;
      }
    }
    *(_DWORD *)(v23 + 16) = 3;
LABEL_27:
    if ( v22 <= 8u )
      *(_DWORD *)(v23 + 32) = v24 << v22;
LABEL_29:
    v28 = -(*(_DWORD *)(v23 + 8) * (((*(_DWORD *)(v23 + 4) * (unsigned int)v22 + 31) >> 3) & 0x1FFFFFFC));
    if ( *(int *)(v23 + 8) >= 0 )
      v28 = *(_DWORD *)(v23 + 8) * (((*(_DWORD *)(v23 + 4) * (unsigned int)v22 + 31) >> 3) & 0x1FFFFFFC);
    *(_DWORD *)(v23 + 20) = v28;
    *(_OWORD *)(*(_QWORD *)&a3->majortype.Data1 + 16LL) = *(_OWORD *)GetBitmapSubtype(v60, v23);
    if ( ((unsigned __int8)v30 & *((_BYTE *)this + 8)) != 0 )
    {
      if ( *(_DWORD *)this == 21 )
      {
        v34 = MEDIASUBTYPE_ARGB32_D3D_DX9_RT;
      }
      else
      {
        v31 = *(_DWORD *)this - 21 - v30;
        if ( v31 )
        {
          v32 = v31 - v30;
          if ( v32 )
          {
            v33 = v32 - 2;
            if ( v33 )
            {
              if ( v33 != v30 )
                goto LABEL_48;
              v34 = MEDIASUBTYPE_ARGB4444_D3D_DX9_RT;
            }
            else
            {
              v34 = MEDIASUBTYPE_ARGB1555_D3D_DX9_RT;
            }
          }
          else
          {
            v34 = MEDIASUBTYPE_RGB16_D3D_DX7_RT;
          }
        }
        else
        {
          v34 = MEDIASUBTYPE_RGB32_D3D_DX7_RT;
        }
      }
      *(GUID *)(*(_QWORD *)&a3->majortype.Data1 + 16LL) = v34;
    }
    else
    {
      for ( i = 0; i < 0x1F; i += v30 )
      {
        v36 = 32LL * i;
        if ( *(_DWORD *)((char *)&VMR9::table + v36 + 24) == *(_DWORD *)this )
        {
          _mm_lfence();
          *(_OWORD *)(*(_QWORD *)&a3->majortype.Data1 + 16LL) = **(_OWORD **)((char *)&VMR9::table + v36);
          break;
        }
      }
    }
LABEL_48:
    *(_DWORD *)(*(_QWORD *)&a3->majortype.Data1 + 40LL) = *(_DWORD *)(v29 + 20);
    v37 = *(_QWORD **)&a3->majortype.Data1;
    v38 = *(_QWORD *)((char *)v37 + 44) - *(_QWORD *)&FORMAT_VideoInfo.Data1;
    if ( !v38 )
      v38 = *(_QWORD *)((char *)v37 + 52) - *(_QWORD *)FORMAT_VideoInfo.Data4;
    if ( v38 )
    {
      v50 = *(_QWORD *)((char *)v37 + 44) - *(_QWORD *)&FORMAT_VideoInfo2.Data1;
      if ( !v50 )
        v50 = *(_QWORD *)((char *)v37 + 52) - *(_QWORD *)FORMAT_VideoInfo2.Data4;
      if ( v50 )
        return v11;
      v51 = *(_QWORD *)&a2[2].MultiSampleType;
      v40 = (const RECT *)v37[10];
      v52 = (int *)(v51 + 76);
      left = -v40[5].left;
      if ( v40[5].left > 0 )
        left = v40[5].left;
      v54 = -*(_DWORD *)(v51 + 80);
      if ( *(int *)(v51 + 80) > 0 )
        v54 = *(_DWORD *)(v51 + 80);
      if ( left == v54 )
      {
        bottom = -v40[4].bottom;
        if ( v40[4].bottom > 0 )
          bottom = v40[4].bottom;
        v56 = -*v52;
        if ( *v52 > 0 )
          v56 = *v52;
        if ( bottom == v56 )
          return v11;
      }
      if ( IsRectEmpty(v40) )
      {
        *(_QWORD *)&v40->left = 0;
        v57 = -*v52;
        if ( *v52 > 0 )
          v57 = *v52;
        v40->right = v57;
        v58 = -*(_DWORD *)(v51 + 80);
        if ( *(int *)(v51 + 80) > 0 )
          v58 = *(_DWORD *)(v51 + 80);
        v40->bottom = v58;
      }
      if ( !IsRectEmpty(v40 + 1) )
        return v11;
      *(_QWORD *)&v40[1].left = 0;
      v59 = -*v52;
      if ( *v52 > 0 )
        v59 = *v52;
      v40[1].right = v59;
      v49 = -*(_DWORD *)(v51 + 80);
      if ( *(int *)(v51 + 80) > 0 )
        v49 = *(_DWORD *)(v51 + 80);
    }
    else
    {
      v39 = *(_QWORD *)&a2[2].MultiSampleType;
      v40 = (const RECT *)v37[10];
      v41 = (int *)(v39 + 52);
      right = -v40[3].right;
      if ( v40[3].right > 0 )
        right = v40[3].right;
      v43 = -*(_DWORD *)(v39 + 56);
      if ( *(int *)(v39 + 56) > 0 )
        v43 = *(_DWORD *)(v39 + 56);
      if ( right == v43 )
      {
        top = -v40[3].top;
        if ( v40[3].top > 0 )
          top = v40[3].top;
        v45 = -*v41;
        if ( *v41 > 0 )
          v45 = *v41;
        if ( top == v45 )
          return v11;
      }
      if ( IsRectEmpty(v40) )
      {
        *(_QWORD *)&v40->left = 0;
        v46 = -*v41;
        if ( *v41 > 0 )
          v46 = *v41;
        v40->right = v46;
        v47 = -*(_DWORD *)(v39 + 56);
        if ( *(int *)(v39 + 56) > 0 )
          v47 = *(_DWORD *)(v39 + 56);
        v40->bottom = v47;
      }
      if ( !IsRectEmpty(v40 + 1) )
        return v11;
      *(_QWORD *)&v40[1].left = 0;
      v48 = -*v41;
      if ( *v41 > 0 )
        v48 = *v41;
      v40[1].right = v48;
      v49 = -*(_DWORD *)(v39 + 56);
      if ( *(int *)(v39 + 56) > 0 )
        v49 = *(_DWORD *)(v39 + 56);
    }
    v40[1].bottom = v49;
    return v11;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800e7aa0  push    rbx
0x1800e7aa2  push    rbp
0x1800e7aa3  push    rsi
0x1800e7aa4  push    rdi
0x1800e7aa5  push    r14
0x1800e7aa7  push    r15
0x1800e7aa9  sub     rsp, 38h
0x1800e7aad  xor     r15d, r15d
0x1800e7ab0  mov     rbx, r8
0x1800e7ab3  mov     [r8], r15
0x1800e7ab6  mov     rdi, rdx
0x1800e7ab9  mov     rax, [rdx+2Ch]
0x1800e7abd  mov     rsi, rcx
0x1800e7ac0  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x1800e7ac7  jnz     short loc_1800E7AD4
0x1800e7ac9  mov     rax, [rdx+34h]
0x1800e7acd  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x1800e7ad4  test    rax, rax
0x1800e7ad7  jnz     short loc_1800E7ADF
0x1800e7ad9  cmp     dword ptr [rdx+48h], 58h ; 'X'
0x1800e7add  jnb     short loc_1800E7B0A
0x1800e7adf  mov     rax, [rdx+2Ch]
0x1800e7ae3  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x1800e7aea  jnz     short loc_1800E7AF7
0x1800e7aec  mov     rax, [rdx+34h]
0x1800e7af0  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x1800e7af7  test    rax, rax
0x1800e7afa  jnz     loc_1800E7E3C
0x1800e7b00  cmp     dword ptr [rdx+48h], 70h ; 'p'
0x1800e7b04  jb      loc_1800E7E3C
0x1800e7b0a  mov     rdx, rbx; struct _AMMediaType *
0x1800e7b0d  mov     rcx, rdi; this
0x1800e7b10  call    ?AllocVideoMediaType@VMR9@@YAJPEBU_AMMediaType@@PEAPEAU2@@Z; VMR9::AllocVideoMediaType(_AMMediaType const *,_AMMediaType * *)
0x1800e7b15  mov     ebp, eax
0x1800e7b17  test    eax, eax
0x1800e7b19  js      loc_1800E7E41
0x1800e7b1f  mov     rcx, [rbx]; this
0x1800e7b22  call    ?GetbmiHeader@VMR9@@YAPEAUtagBITMAPINFOHEADER@@PEBU_AMMediaType@@@Z; VMR9::GetbmiHeader(_AMMediaType const *)
0x1800e7b27  mov     r10, rax
0x1800e7b2a  test    rax, rax
0x1800e7b2d  jnz     short loc_1800E7B3E
0x1800e7b2f  call    ?FreeMediaType@@YAXAEAU_AMMediaType@@@Z; FreeMediaType(_AMMediaType &)
0x1800e7b34  mov     eax, 80004005h
0x1800e7b39  jmp     loc_1800E7E41
0x1800e7b3e  mov     dword ptr [rax], 28h ; '('
0x1800e7b44  mov     r11d, 1
0x1800e7b4a  mov     eax, [rsi+18h]
0x1800e7b4d  mov     [r10+4], eax
0x1800e7b51  mov     eax, [rsi+1Ch]
0x1800e7b54  neg     eax
0x1800e7b56  mov     [r10+0Ch], r11w
0x1800e7b5b  mov     [r10+8], eax
0x1800e7b5f  mov     ecx, [rsi]; this
0x1800e7b61  call    ?BitCountFromFormat@VMR9@@YAKW4_D3DFORMAT@1@@Z; VMR9::BitCountFromFormat(VMR9::_D3DFORMAT)
0x1800e7b66  mov     r9d, eax
0x1800e7b69  mov     [r10+0Eh], r9w
0x1800e7b6e  mov     ecx, [rsi]; this
0x1800e7b70  call    ?FindTableEntry@VMR9@@YAPEAUMTLookUp@1@W4_D3DFORMAT@1@@Z; VMR9::FindTableEntry(VMR9::_D3DFORMAT)
0x1800e7b75  test    rax, rax
0x1800e7b78  jz      short loc_1800E7B85
0x1800e7b7a  cmp     [rax+14h], r15d
0x1800e7b7e  jnz     short loc_1800E7B85
0x1800e7b80  mov     eax, [rax+18h]
0x1800e7b83  jmp     short loc_1800E7B88
0x1800e7b85  mov     eax, r15d
0x1800e7b88  mov     [r10+10h], eax
0x1800e7b8c  mov     [r10+20h], r15
0x1800e7b90  test    eax, eax
0x1800e7b92  jnz     short loc_1800E7BE0
0x1800e7b94  mov     rcx, rdi; this
0x1800e7b97  call    ?GetbmiHeader@VMR9@@YAPEAUtagBITMAPINFOHEADER@@PEBU_AMMediaType@@@Z; VMR9::GetbmiHeader(_AMMediaType const *)
0x1800e7b9c  test    rax, rax
0x1800e7b9f  lea     rcx, qword_1801A2488
0x1800e7ba6  mov     edx, 0FFEFh
0x1800e7bab  cmovnz  rcx, rax
0x1800e7baf  lea     eax, [r9-10h]
0x1800e7bb3  test    dx, ax
0x1800e7bb6  jnz     short loc_1800E7BE0
0x1800e7bb8  cmp     dword ptr [rcx+10h], 3
0x1800e7bbc  jz      short loc_1800E7BD8
0x1800e7bbe  cmp     r9w, 20h ; ' '
0x1800e7bc3  jnz     short loc_1800E7BCC
0x1800e7bc5  cmp     dword ptr [rsi], 16h
0x1800e7bc8  jnz     short loc_1800E7BD8
0x1800e7bca  jmp     short loc_1800E7BF3
0x1800e7bcc  cmp     r9w, 10h
0x1800e7bd1  jnz     short loc_1800E7BE0
0x1800e7bd3  cmp     dword ptr [rsi], 18h
0x1800e7bd6  jz      short loc_1800E7BF3
0x1800e7bd8  mov     dword ptr [r10+10h], 3
0x1800e7be0  cmp     r9w, 8
0x1800e7be5  ja      short loc_1800E7BF3
0x1800e7be7  mov     ecx, r9d
0x1800e7bea  mov     eax, r11d
0x1800e7bed  shl     eax, cl
0x1800e7bef  mov     [r10+20h], eax
0x1800e7bf3  movzx   ecx, r9w
0x1800e7bf7  mov     rdx, r10
0x1800e7bfa  imul    ecx, [r10+4]
0x1800e7bff  add     ecx, 1Fh
0x1800e7c02  shr     ecx, 3
0x1800e7c05  and     ecx, 1FFFFFFCh
0x1800e7c0b  imul    ecx, [r10+8]
0x1800e7c10  mov     eax, ecx
0x1800e7c12  neg     eax
0x1800e7c14  cmp     [r10+8], r15d
0x1800e7c18  cmovge  eax, ecx
0x1800e7c1b  lea     rcx, [rsp+68h+var_48]
0x1800e7c20  mov     [r10+14h], eax
0x1800e7c24  call    GetBitmapSubtype
0x1800e7c29  movups  xmm1, xmmword ptr [rax]
0x1800e7c2c  mov     rax, [rbx]
0x1800e7c2f  movdqu  xmmword ptr [rax+10h], xmm1
0x1800e7c34  test    [rsi+8], r11b
0x1800e7c38  jz      short loc_1800E7C8A
0x1800e7c3a  mov     ecx, [rsi]
0x1800e7c3c  sub     ecx, 15h
0x1800e7c3f  jz      short loc_1800E7C79
0x1800e7c41  sub     ecx, r11d
0x1800e7c44  jz      short loc_1800E7C70
0x1800e7c46  sub     ecx, r11d
0x1800e7c49  jz      short loc_1800E7C67
0x1800e7c4b  sub     ecx, 2
0x1800e7c4e  jz      short loc_1800E7C5E
0x1800e7c50  cmp     ecx, r11d
0x1800e7c53  jnz     short loc_1800E7CBF
0x1800e7c55  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_ARGB4444_D3D_DX9_RT.Data1
0x1800e7c5c  jmp     short loc_1800E7C80
0x1800e7c5e  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_ARGB1555_D3D_DX9_RT.Data1
0x1800e7c65  jmp     short loc_1800E7C80
0x1800e7c67  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_RGB16_D3D_DX7_RT.Data1
0x1800e7c6e  jmp     short loc_1800E7C80
0x1800e7c70  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_RGB32_D3D_DX7_RT.Data1
0x1800e7c77  jmp     short loc_1800E7C80
0x1800e7c79  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_ARGB32_D3D_DX9_RT.Data1
0x1800e7c80  mov     rax, [rbx]
0x1800e7c83  movdqu  xmmword ptr [rax+10h], xmm0
0x1800e7c88  jmp     short loc_1800E7CBF
0x1800e7c8a  mov     ecx, r15d
0x1800e7c8d  lea     r8, ?table@VMR9@@3PAUMTLookUp@1@A; VMR9::MTLookUp near * VMR9::table
0x1800e7c94  cmp     ecx, 1Fh
0x1800e7c97  jnb     short loc_1800E7CBF
0x1800e7c99  mov     eax, [rsi]
0x1800e7c9b  mov     edx, ecx
0x1800e7c9d  shl     rdx, 5
0x1800e7ca1  cmp     [rdx+r8+18h], eax
0x1800e7ca6  jz      short loc_1800E7CAD
0x1800e7ca8  add     ecx, r11d
0x1800e7cab  jmp     short loc_1800E7C94
0x1800e7cad  lfence
0x1800e7cb0  mov     rax, [rdx+r8]
0x1800e7cb4  mov     rcx, [rbx]
0x1800e7cb7  movups  xmm0, xmmword ptr [rax]
0x1800e7cba  movdqu  xmmword ptr [rcx+10h], xmm0
0x1800e7cbf  mov     rcx, [rbx]
0x1800e7cc2  mov     eax, [r10+14h]
0x1800e7cc6  mov     [rcx+28h], eax
0x1800e7cc9  mov     rbx, [rbx]
0x1800e7ccc  mov     rax, [rbx+2Ch]
0x1800e7cd0  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x1800e7cd7  jnz     short loc_1800E7CE4
0x1800e7cd9  mov     rax, [rbx+34h]
0x1800e7cdd  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x1800e7ce4  test    rax, rax
0x1800e7ce7  jnz     loc_1800E7D87
0x1800e7ced  mov     rsi, [rdi+50h]
0x1800e7cf1  mov     rbx, [rbx+50h]
0x1800e7cf5  mov     eax, [rsi+38h]
0x1800e7cf8  lea     rdi, [rsi+34h]
0x1800e7cfc  mov     ecx, [rbx+38h]
0x1800e7cff  neg     ecx
0x1800e7d01  cmovs   ecx, [rbx+38h]
0x1800e7d05  neg     eax
0x1800e7d07  cmovs   eax, [rsi+38h]
0x1800e7d0b  cmp     ecx, eax
0x1800e7d0d  jnz     short loc_1800E7D27
0x1800e7d0f  mov     ecx, [rbx+34h]
0x1800e7d12  mov     eax, [rdi]
0x1800e7d14  neg     ecx
0x1800e7d16  cmovs   ecx, [rbx+34h]
0x1800e7d1a  neg     eax
0x1800e7d1c  cmovs   eax, [rdi]
0x1800e7d1f  cmp     ecx, eax
0x1800e7d21  jz      loc_1800E7E38
0x1800e7d27  mov     rcx, rbx; lprc
0x1800e7d2a  call    cs:__imp_IsRectEmpty
0x1800e7d31  nop     dword ptr [rax+rax+00h]
0x1800e7d36  test    eax, eax
0x1800e7d38  jz      short loc_1800E7D53
0x1800e7d3a  mov     [rbx], r15
0x1800e7d3d  mov     eax, [rdi]
0x1800e7d3f  neg     eax
0x1800e7d41  cmovs   eax, [rdi]
0x1800e7d44  mov     [rbx+8], eax
0x1800e7d47  mov     eax, [rsi+38h]
0x1800e7d4a  neg     eax
0x1800e7d4c  cmovs   eax, [rsi+38h]
0x1800e7d50  mov     [rbx+0Ch], eax
0x1800e7d53  lea     rcx, [rbx+10h]; lprc
0x1800e7d57  call    cs:__imp_IsRectEmpty
0x1800e7d5e  nop     dword ptr [rax+rax+00h]
0x1800e7d63  test    eax, eax
0x1800e7d65  jz      loc_1800E7E38
0x1800e7d6b  mov     [rbx+10h], r15
0x1800e7d6f  mov     eax, [rdi]
0x1800e7d71  neg     eax
0x1800e7d73  cmovs   eax, [rdi]
0x1800e7d76  mov     [rbx+18h], eax
0x1800e7d79  mov     eax, [rsi+38h]
0x1800e7d7c  neg     eax
0x1800e7d7e  cmovs   eax, [rsi+38h]
0x1800e7d82  jmp     loc_1800E7E35
0x1800e7d87  mov     rax, [rbx+2Ch]
0x1800e7d8b  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x1800e7d92  jnz     short loc_1800E7D9F
0x1800e7d94  mov     rax, [rbx+34h]
0x1800e7d98  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x1800e7d9f  test    rax, rax
0x1800e7da2  jnz     loc_1800E7E38
0x1800e7da8  mov     rsi, [rdi+50h]
0x1800e7dac  mov     rbx, [rbx+50h]
0x1800e7db0  mov     eax, [rsi+50h]
0x1800e7db3  lea     rdi, [rsi+4Ch]
0x1800e7db7  mov     ecx, [rbx+50h]
0x1800e7dba  neg     ecx
0x1800e7dbc  cmovs   ecx, [rbx+50h]
0x1800e7dc0  neg     eax
0x1800e7dc2  cmovs   eax, [rsi+50h]
0x1800e7dc6  cmp     ecx, eax
0x1800e7dc8  jnz     short loc_1800E7DDE
0x1800e7dca  mov     ecx, [rbx+4Ch]
0x1800e7dcd  mov     eax, [rdi]
0x1800e7dcf  neg     ecx
0x1800e7dd1  cmovs   ecx, [rbx+4Ch]
0x1800e7dd5  neg     eax
0x1800e7dd7  cmovs   eax, [rdi]
0x1800e7dda  cmp     ecx, eax
0x1800e7ddc  jz      short loc_1800E7E38
0x1800e7dde  mov     rcx, rbx; lprc
0x1800e7de1  call    cs:__imp_IsRectEmpty
0x1800e7de8  nop     dword ptr [rax+rax+00h]
0x1800e7ded  test    eax, eax
0x1800e7def  jz      short loc_1800E7E0A
0x1800e7df1  mov     [rbx], r15
0x1800e7df4  mov     eax, [rdi]
0x1800e7df6  neg     eax
0x1800e7df8  cmovs   eax, [rdi]
0x1800e7dfb  mov     [rbx+8], eax
0x1800e7dfe  mov     eax, [rsi+50h]
0x1800e7e01  neg     eax
0x1800e7e03  cmovs   eax, [rsi+50h]
0x1800e7e07  mov     [rbx+0Ch], eax
0x1800e7e0a  lea     rcx, [rbx+10h]; lprc
0x1800e7e0e  call    cs:__imp_IsRectEmpty
0x1800e7e15  nop     dword ptr [rax+rax+00h]
0x1800e7e1a  test    eax, eax
0x1800e7e1c  jz      short loc_1800E7E38
0x1800e7e1e  mov     [rbx+10h], r15
0x1800e7e22  mov     eax, [rdi]
0x1800e7e24  neg     eax
0x1800e7e26  cmovs   eax, [rdi]
0x1800e7e29  mov     [rbx+18h], eax
0x1800e7e2c  mov     eax, [rsi+50h]
0x1800e7e2f  neg     eax
0x1800e7e31  cmovs   eax, [rsi+50h]
0x1800e7e35  mov     [rbx+1Ch], eax
0x1800e7e38  mov     eax, ebp
0x1800e7e3a  jmp     short loc_1800E7E41
0x1800e7e3c  mov     eax, 80070057h
0x1800e7e41  add     rsp, 38h
0x1800e7e45  pop     r15
0x1800e7e47  pop     r14
0x1800e7e49  pop     rdi
0x1800e7e4a  pop     rsi
0x1800e7e4b  pop     rbp
0x1800e7e4c  pop     rbx
0x1800e7e4d  retn
```
