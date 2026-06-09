# CxCodeVideoProcMFTTypeHandler::OnInputTypeChanged(void)

- ea: `0x1800309c0`
- end: `0x18003102b`
- name: `?OnInputTypeChanged@CxCodeVideoProcMFTTypeHandler@@UEAAJXZ`
- size: `1643`
- prototype: `__int64 __fastcall(CxCodeVideoProcMFTTypeHandler *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x1800319b0`

## callees

- `0x180005f64`
- `0x180023cbc`
- `0x1800309c0`
- `0x180031034`
- `0x180032994`
- `0x180053bfc`
- `0x180054140`
- `0x1800c71f8`
- `0x1800c8548`
- `0x1800d1010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x180030cd2`
- `MFPlat!MFCreateMediaType` at `0x180030e11`
- `MFPlat!MFCreateMediaType` at `0x180030cd2`
- `MFPlat!MFCreateMediaType` at `0x180030e11`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFTTypeHandler::OnInputTypeChanged(CxCodeVideoProcMFTTypeHandler *this)
{
  __int64 v2; // rcx
  unsigned int inited; // ebx
  __int64 v4; // r10
  int v5; // r15d
  __m128i v6; // xmm5
  __m128i v7; // xmm4
  __m128i v8; // xmm6
  __m128i v9; // xmm2
  __m128i v10; // xmm1
  __int64 v11; // r8
  __m128i v12; // xmm3
  __int64 v13; // rax
  __m128i v14; // xmm0
  __m128i v15; // xmm4
  __m128i v16; // xmm4
  unsigned int i; // esi
  unsigned int v18; // eax
  unsigned int v19; // r13d
  _QWORD *v20; // rax
  struct IMFAttributes *v21; // rdx
  __int64 v22; // rcx
  BOOL v23; // r12d
  IMFMediaType *v24; // rcx
  unsigned int v25; // r9d
  CxCodeVideoProcMFTDataHandler *v26; // rcx
  IMFMediaType *v27; // rcx
  unsigned int v28; // edi
  IMFMediaType *v29; // rcx
  int v30; // r8d
  __int64 v31; // rax
  int v32; // eax
  unsigned int v33; // r9d
  IMFMediaType *v34; // rcx
  struct IMFAttributes *v35; // rcx
  IMFMediaType *v36; // rcx
  IMFMediaType *ppMFType; // [rsp+20h] [rbp-19h] BYREF
  struct IMFAttributes *v39; // [rsp+28h] [rbp-11h] BYREF
  __int128 v40; // [rsp+38h] [rbp-1h] BYREF
  __int128 v41; // [rsp+48h] [rbp+Fh] BYREF

  ppMFType = 0;
  v2 = *((_QWORD *)this + 46);
  v39 = 0;
  v41 = 0;
  if ( v2 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2) )
  {
    inited = 0;
    CxCodeVideoProcMFTTypeHandler::OnInputTypeChangedD3D(this);
    goto LABEL_65;
  }
  inited = (*(__int64 (__fastcall **)(_QWORD, const GUID *, __int128 *))(***((_QWORD ***)this + 8) + 80LL))(
             **((_QWORD **)this + 8),
             &MF_MT_SUBTYPE,
             &v41);
  if ( !inited )
  {
    v4 = 0;
    v5 = v41;
    v6 = 0;
    v7 = 0;
    v8 = _mm_shuffle_epi32(_mm_cvtsi32_si128(v41), 0);
    do
    {
      v9 = _mm_unpacklo_epi32(
             _mm_cvtsi32_si128(*((_DWORD *)&CtypeConversions::types + 6 * (unsigned int)(v4 + 2))),
             _mm_cvtsi32_si128(*((_DWORD *)&CtypeConversions::types + 6 * (unsigned int)(v4 + 3))));
      v10 = _mm_cvtsi32_si128(*((_DWORD *)&CtypeConversions::types + 6 * (unsigned int)(v4 + 7)));
      v11 = 3LL * (unsigned int)(v4 + 6);
      v12 = _mm_unpacklo_epi32(
              _mm_cvtsi32_si128(*((_DWORD *)&CtypeConversions::types + 6 * v4)),
              _mm_cvtsi32_si128(*((_DWORD *)&CtypeConversions::types + 6 * (unsigned int)(v4 + 1))));
      v13 = 3LL * (unsigned int)(v4 + 4);
      v14 = _mm_cvtsi32_si128(*((_DWORD *)&CtypeConversions::types + 6 * (unsigned int)(v4 + 5)));
      v4 = (unsigned int)(v4 + 8);
      v6 = _mm_sub_epi32(v6, _mm_cmpeq_epi32(_mm_unpacklo_epi64(v12, v9), v8));
      v7 = _mm_sub_epi32(
             v7,
             _mm_cmpeq_epi32(
               _mm_unpacklo_epi64(
                 _mm_unpacklo_epi32(_mm_cvtsi32_si128(*((_DWORD *)&CtypeConversions::types + 2 * v13)), v14),
                 _mm_unpacklo_epi32(_mm_cvtsi32_si128(*((_DWORD *)&CtypeConversions::types + 2 * v11)), v10)),
               v8));
    }
    while ( (unsigned int)v4 < 0x88 );
    v15 = _mm_add_epi32(v7, v6);
    v16 = _mm_add_epi32(v15, _mm_srli_si128(v15, 8));
    for ( i = _mm_cvtsi128_si32(_mm_add_epi32(v16, _mm_srli_si128(v16, 4))); (unsigned int)v4 < 0x8D; i = v18 )
    {
      v18 = i + 1;
      if ( *((_DWORD *)&CtypeConversions::types + 6 * v4) != (_DWORD)v41 )
        v18 = i;
      v4 = (unsigned int)(v4 + 1);
    }
    if ( *(_DWORD *)(*((_QWORD *)this + 47) + 1136LL) )
      v19 = 0;
    else
      v19 = i + (*(_BYTE *)(*((_QWORD *)this + 45) + 28LL) != 0 ? 0x10 : 0);
    if ( *(_BYTE *)(*((_QWORD *)this + 45) + 28LL) && !*((_QWORD *)this + 46) )
    {
      v20 = operator new(0x20u);
      if ( v20 )
      {
        v20[1] = 0;
        *v20 = &CxCodeVideoProcWARPTypeHandler::`vftable';
        v20[2] = 0;
        v20[3] = 0;
      }
      *((_QWORD *)this + 46) = v20;
      if ( !v20 )
      {
        inited = -2147024882;
        goto LABEL_65;
      }
    }
    v21 = v39;
    if ( v39 )
    {
      v39 = 0;
      ((void (__fastcall *)(struct IMFAttributes *))v21->lpVtbl->Release)(v21);
      v21 = 0;
    }
    v22 = *((_QWORD *)this + 1);
    if ( v22 )
    {
      (*(void (__fastcall **)(__int64, struct IMFAttributes **))(*(_QWORD *)v22 + 64LL))(v22, &v39);
      v21 = v39;
    }
    v23 = v21 && (unsigned int)IsS3DMultiView(**((struct IMFMediaType ***)this + 8), v21);
    inited = CMFTMultiStreamTypeHandler::InitAvailableOutputTypeArray(this, v19 + 1, v11);
    if ( !inited )
    {
      v24 = ppMFType;
      if ( ppMFType )
      {
        ppMFType = 0;
        ((void (__fastcall *)(IMFMediaType *))v24->lpVtbl->Release)(v24);
      }
      inited = MFCreateMediaType(&ppMFType);
      if ( !inited )
      {
        inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                   ppMFType,
                   &MF_MT_MAJOR_TYPE,
                   &MFMediaType_Video);
        if ( !inited )
        {
          inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int128 *))ppMFType->lpVtbl->SetGUID)(
                     ppMFType,
                     &MF_MT_SUBTYPE,
                     &v41);
          if ( !inited
            && (!v23
             || (inited = ((__int64 (__fastcall *)(IMFMediaType *, __int64 *, __int64))ppMFType->lpVtbl->SetUINT32)(
                            ppMFType,
                            MF_MT_VIDEO_3D,
                            1)) == 0
             && (inited = ((__int64 (__fastcall *)(IMFMediaType *, __int64 *, __int64))ppMFType->lpVtbl->SetUINT32)(
                            ppMFType,
                            MF_MT_VIDEO_3D_FORMAT,
                            1)) == 0) )
          {
            v26 = (CxCodeVideoProcMFTDataHandler *)*((_QWORD *)this + 47);
            if ( !*((_DWORD *)v26 + 284)
              || (inited = CxCodeVideoProcMFTDataHandler::GetNaturalOutputType(v26, ppMFType)) == 0 )
            {
              CMFTMultiStreamTypeHandler::SetAvailableOutputType(this, 0, ppMFType, v25);
              v27 = ppMFType;
              if ( ppMFType )
              {
                ppMFType = 0;
                ((void (__fastcall *)(IMFMediaType *))v27->lpVtbl->Release)(v27);
              }
              v28 = 0;
              if ( v19 )
              {
                while ( 1 )
                {
                  v29 = ppMFType;
                  if ( ppMFType )
                  {
                    ppMFType = 0;
                    ((void (__fastcall *)(IMFMediaType *))v29->lpVtbl->Release)(v29);
                  }
                  inited = MFCreateMediaType(&ppMFType);
                  if ( inited )
                    goto LABEL_65;
                  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
                             ppMFType,
                             &MF_MT_MAJOR_TYPE,
                             &MFMediaType_Video);
                  if ( inited )
                    goto LABEL_65;
                  LODWORD(v40) = 0;
                  *(_QWORD *)((char *)&v40 + 4) = 0xAA00008000100000uLL;
                  HIDWORD(v40) = 1905997824;
                  if ( v28 >= i && *(_BYTE *)(*((_QWORD *)this + 45) + 28LL) != (_BYTE)inited )
                  {
                    v40 = xmmword_1801547B0[v28 - i];
                    goto LABEL_56;
                  }
                  v30 = 0;
                  v31 = 0;
                  while ( *((_DWORD *)&CtypeConversions::types + 6 * v31) != v5 )
                  {
LABEL_53:
                    v31 = (unsigned int)(v31 + 1);
                    if ( (unsigned int)v31 >= 0x8D )
                    {
                      v32 = 0;
                      goto LABEL_55;
                    }
                  }
                  if ( v30 != v28 )
                    break;
                  v32 = dword_1800D3204[6 * v31];
LABEL_55:
                  LODWORD(v40) = v32;
LABEL_56:
                  inited = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int128 *))ppMFType->lpVtbl->SetGUID)(
                             ppMFType,
                             &MF_MT_SUBTYPE,
                             &v40);
                  if ( inited )
                    goto LABEL_65;
                  if ( v23 )
                  {
                    inited = ((__int64 (__fastcall *)(IMFMediaType *, __int64 *, __int64))ppMFType->lpVtbl->SetUINT32)(
                               ppMFType,
                               MF_MT_VIDEO_3D,
                               1);
                    if ( inited )
                      goto LABEL_65;
                    inited = ((__int64 (__fastcall *)(IMFMediaType *, __int64 *, __int64))ppMFType->lpVtbl->SetUINT32)(
                               ppMFType,
                               MF_MT_VIDEO_3D_FORMAT,
                               1);
                    if ( inited )
                      goto LABEL_65;
                  }
                  CMFTMultiStreamTypeHandler::SetAvailableOutputType(this, ++v28, ppMFType, v33);
                  v34 = ppMFType;
                  if ( ppMFType )
                  {
                    ppMFType = 0;
                    ((void (__fastcall *)(IMFMediaType *))v34->lpVtbl->Release)(v34);
                  }
                  if ( v28 >= v19 )
                    goto LABEL_63;
                }
                ++v30;
                goto LABEL_53;
              }
LABEL_63:
              if ( *(_BYTE *)(*((_QWORD *)this + 45) + 28LL) )
                inited = CxCodeVideoProcMFTTypeHandler::UpdateAvailableOutputTypesD3D(this, i + 1);
            }
          }
        }
      }
    }
  }
LABEL_65:
  v35 = v39;
  if ( v39 )
  {
    v39 = 0;
    ((void (__fastcall *)(struct IMFAttributes *))v35->lpVtbl->Release)(v35);
  }
  v36 = ppMFType;
  if ( ppMFType )
  {
    ppMFType = 0;
    ((void (__fastcall *)(IMFMediaType *))v36->lpVtbl->Release)(v36);
  }
  return inited;
}

```

## disassembly

```asm
0x1800309c0  push    rbp
0x1800309c2  push    rbx
0x1800309c3  lea     rbp, [rsp-4Fh]
0x1800309c8  sub     rsp, 88h
0x1800309cf  mov     rax, cs:__security_cookie
0x1800309d6  xor     rax, rsp
0x1800309d9  mov     [rbp+57h+var_38], rax
0x1800309dd  mov     [rsp+90h+var_18], r14
0x1800309e2  xorps   xmm0, xmm0
0x1800309e5  mov     r14, rcx
0x1800309e8  mov     [rbp+57h+ppMFType], 0
0x1800309f0  mov     rcx, [rcx+170h]
0x1800309f7  mov     [rbp+57h+var_68], 0
0x1800309ff  movups  [rbp+57h+var_48], xmm0
0x180030a03  test    rcx, rcx
0x180030a06  jz      short loc_180030A27
0x180030a08  mov     rax, [rcx]
0x180030a0b  mov     rax, [rax+18h]
0x180030a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a14  test    al, al
0x180030a16  jz      short loc_180030A27
0x180030a18  xor     ebx, ebx
0x180030a1a  mov     rcx, r14; this
0x180030a1d  call    ?OnInputTypeChangedD3D@CxCodeVideoProcMFTTypeHandler@@QEAAJXZ; CxCodeVideoProcMFTTypeHandler::OnInputTypeChangedD3D(void)
0x180030a22  jmp     loc_180030FC8
0x180030a27  mov     rax, [r14+40h]
0x180030a2b  lea     r8, [rbp+57h+var_48]
0x180030a2f  lea     rdx, MF_MT_SUBTYPE
0x180030a36  mov     rcx, [rax]
0x180030a39  mov     rax, [rcx]
0x180030a3c  mov     rax, [rax+50h]
0x180030a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a45  mov     ebx, eax
0x180030a47  test    eax, eax
0x180030a49  jnz     loc_180030FC8
0x180030a4f  mov     [rsp+90h+arg_8], rsi
0x180030a57  lea     r11, __ImageBase
0x180030a5e  mov     [rsp+90h+var_20], r15
0x180030a63  xor     r10d, r10d
0x180030a66  mov     r15d, dword ptr [rbp+57h+var_48]
0x180030a6a  xorps   xmm5, xmm5
0x180030a6d  movaps  [rsp+90h+var_30], xmm6
0x180030a72  xorps   xmm4, xmm4
0x180030a75  movd    xmm6, r15d
0x180030a7a  pshufd  xmm6, xmm6, 0
0x180030a7f  nop
0x180030a80  lea     eax, [r10+3]
0x180030a84  lea     r9, [rax+rax*2]
0x180030a88  movd    xmm1, ds:rva ?types@CtypeConversions@@0QBUTypeConversion@@B[r11+r9*8]; TypeConversion const near * const CtypeConversions::types ...
0x180030a92  lea     eax, [r10+2]
0x180030a96  lea     r8, [rax+rax*2]
0x180030a9a  movd    xmm2, ds:rva ?types@CtypeConversions@@0QBUTypeConversion@@B[r11+r8*8]; TypeConversion const near * const CtypeConversions::types ...
0x180030aa4  lea     eax, [r10+1]
0x180030aa8  lea     rdx, [rax+rax*2]
0x180030aac  punpckldq xmm2, xmm1
0x180030ab0  movd    xmm0, ds:rva ?types@CtypeConversions@@0QBUTypeConversion@@B[r11+rdx*8]; TypeConversion const near * const CtypeConversions::types ...
0x180030aba  lea     eax, [r10+7]
0x180030abe  lea     r9, [rax+rax*2]
0x180030ac2  movd    xmm1, ds:rva ?types@CtypeConversions@@0QBUTypeConversion@@B[r11+r9*8]; TypeConversion const near * const CtypeConversions::types ...
0x180030acc  lea     eax, [r10+6]
0x180030ad0  lea     r8, [rax+rax*2]
0x180030ad4  lea     eax, [r10+5]
0x180030ad8  lea     rdx, [rax+rax*2]
0x180030adc  lea     rcx, [r10+r10*2]
0x180030ae0  movd    xmm3, ds:rva ?types@CtypeConversions@@0QBUTypeConversion@@B[r11+rcx*8]; TypeConversion const near * const CtypeConversions::types ...
0x180030aea  lea     eax, [r10+4]
0x180030aee  punpckldq xmm3, xmm0
0x180030af2  lea     rax, [rax+rax*2]
0x180030af6  movd    xmm0, ds:rva ?types@CtypeConversions@@0QBUTypeConversion@@B[r11+rdx*8]; TypeConversion const near * const CtypeConversions::types ...
0x180030b00  add     r10d, 8
0x180030b04  punpcklqdq xmm3, xmm2
0x180030b08  movd    xmm2, ds:rva ?types@CtypeConversions@@0QBUTypeConversion@@B[r11+r8*8]; TypeConversion const near * const CtypeConversions::types ...
0x180030b12  pcmpeqd xmm3, xmm6
0x180030b16  punpckldq xmm2, xmm1
0x180030b1a  psubd   xmm5, xmm3
0x180030b1e  movd    xmm3, ds:rva ?types@CtypeConversions@@0QBUTypeConversion@@B[r11+rax*8]; TypeConversion const near * const CtypeConversions::types ...
0x180030b28  punpckldq xmm3, xmm0
0x180030b2c  punpcklqdq xmm3, xmm2
0x180030b30  pcmpeqd xmm3, xmm6
0x180030b34  psubd   xmm4, xmm3
0x180030b38  cmp     r10d, 88h
0x180030b3f  jb      loc_180030A80
0x180030b45  movaps  xmm6, [rsp+90h+var_30]
0x180030b4a  paddd   xmm4, xmm5
0x180030b4e  movdqa  xmm0, xmm4
0x180030b52  psrldq  xmm0, 8
0x180030b57  paddd   xmm4, xmm0
0x180030b5b  movdqa  xmm0, xmm4
0x180030b5f  psrldq  xmm0, 4
0x180030b64  paddd   xmm4, xmm0
0x180030b68  movd    esi, xmm4
0x180030b6c  cmp     r10d, 8Dh
0x180030b73  jnb     short loc_180030BA0
0x180030b75  nop     word ptr [rax+rax+00000000h]
0x180030b80  lea     rcx, [r10+r10*2]
0x180030b84  cmp     ds:rva ?types@CtypeConversions@@0QBUTypeConversion@@B[r11+rcx*8], r15d; TypeConversion const near * const CtypeConversions::types ...
0x180030b8c  lea     eax, [rsi+1]
0x180030b8f  cmovnz  eax, esi
0x180030b92  inc     r10d
0x180030b95  mov     esi, eax
0x180030b97  cmp     r10d, 8Dh
0x180030b9e  jb      short loc_180030B80
0x180030ba0  mov     rax, [r14+178h]
0x180030ba7  mov     [rsp+90h+var_10], r13
0x180030baf  cmp     dword ptr [rax+470h], 0
0x180030bb6  jz      short loc_180030BBD
0x180030bb8  xor     r13d, r13d
0x180030bbb  jmp     short loc_180030BD4
0x180030bbd  mov     rax, [r14+168h]
0x180030bc4  movzx   ecx, byte ptr [rax+1Ch]
0x180030bc8  neg     cl
0x180030bca  sbb     r13d, r13d
0x180030bcd  and     r13d, 10h
0x180030bd1  add     r13d, esi
0x180030bd4  mov     rax, [r14+168h]
0x180030bdb  cmp     byte ptr [rax+1Ch], 0
0x180030bdf  jz      short loc_180030C32
0x180030be1  cmp     qword ptr [r14+170h], 0
0x180030be9  jnz     short loc_180030C32
0x180030beb  mov     ecx, 20h ; ' '; Size
0x180030bf0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030bf5  test    rax, rax
0x180030bf8  jz      short loc_180030C1C
0x180030bfa  lea     rcx, ??_7CxCodeVideoProcWARPTypeHandler@@6B@; const CxCodeVideoProcWARPTypeHandler::`vftable'
0x180030c01  mov     qword ptr [rax+8], 0
0x180030c09  mov     [rax], rcx
0x180030c0c  mov     qword ptr [rax+10h], 0
0x180030c14  mov     qword ptr [rax+18h], 0
0x180030c1c  mov     [r14+170h], rax
0x180030c23  test    rax, rax
0x180030c26  jnz     short loc_180030C32
0x180030c28  mov     ebx, 8007000Eh
0x180030c2d  jmp     loc_180030FB3
0x180030c32  mov     rdx, [rbp+57h+var_68]
0x180030c36  test    rdx, rdx
0x180030c39  jz      short loc_180030C56
0x180030c3b  mov     [rbp+57h+var_68], 0
0x180030c43  mov     rcx, rdx
0x180030c46  mov     rax, [rdx]
0x180030c49  mov     rax, [rax+10h]
0x180030c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c52  mov     rdx, [rbp+57h+var_68]
0x180030c56  mov     rcx, [r14+8]
0x180030c5a  test    rcx, rcx
0x180030c5d  jz      short loc_180030C73
0x180030c5f  mov     rax, [rcx]
0x180030c62  lea     rdx, [rbp+57h+var_68]
0x180030c66  mov     rax, [rax+40h]
0x180030c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c6f  mov     rdx, [rbp+57h+var_68]; struct IMFAttributes *
0x180030c73  mov     [rsp+90h+arg_18], r12
0x180030c7b  test    rdx, rdx
0x180030c7e  jz      short loc_180030C98
0x180030c80  mov     rcx, [r14+40h]
0x180030c84  mov     rcx, [rcx]; struct IMFMediaType *
0x180030c87  call    ?IsS3DMultiView@@YAHPEAUIMFMediaType@@PEAUIMFAttributes@@@Z; IsS3DMultiView(IMFMediaType *,IMFAttributes *)
0x180030c8c  test    eax, eax
0x180030c8e  jz      short loc_180030C98
0x180030c90  mov     r12d, 1
0x180030c96  jmp     short loc_180030C9B
0x180030c98  xor     r12d, r12d
0x180030c9b  lea     edx, [r13+1]; unsigned int
0x180030c9f  mov     rcx, r14; this
0x180030ca2  call    ?InitAvailableOutputTypeArray@CMFTMultiStreamTypeHandler@@IEAAJKK@Z; CMFTMultiStreamTypeHandler::InitAvailableOutputTypeArray(ulong,ulong)
0x180030ca7  mov     ebx, eax
0x180030ca9  test    eax, eax
0x180030cab  jnz     loc_180030FAB
0x180030cb1  mov     rcx, [rbp+57h+ppMFType]
0x180030cb5  test    rcx, rcx
0x180030cb8  jz      short loc_180030CCE
0x180030cba  mov     [rbp+57h+ppMFType], 0
0x180030cc2  mov     rax, [rcx]
0x180030cc5  mov     rax, [rax+10h]
0x180030cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030cce  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x180030cd2  call    cs:__imp_MFCreateMediaType
0x180030cd8  mov     ebx, eax
0x180030cda  test    eax, eax
0x180030cdc  jnz     loc_180030FAB
0x180030ce2  mov     rcx, [rbp+57h+ppMFType]
0x180030ce6  lea     r8, MFMediaType_Video
0x180030ced  lea     rdx, MF_MT_MAJOR_TYPE
0x180030cf4  mov     rax, [rcx]
0x180030cf7  mov     rax, [rax+0C0h]
0x180030cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d03  mov     ebx, eax
0x180030d05  test    eax, eax
0x180030d07  jnz     loc_180030FAB
0x180030d0d  mov     rcx, [rbp+57h+ppMFType]
0x180030d11  lea     r8, [rbp+57h+var_48]
0x180030d15  lea     rdx, MF_MT_SUBTYPE
0x180030d1c  mov     rax, [rcx]
0x180030d1f  mov     rax, [rax+0C0h]
0x180030d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d2b  mov     ebx, eax
0x180030d2d  test    eax, eax
0x180030d2f  jnz     loc_180030FAB
0x180030d35  test    r12d, r12d
0x180030d38  jz      short loc_180030D8E
0x180030d3a  mov     rcx, [rbp+57h+ppMFType]
0x180030d3e  lea     rdx, MF_MT_VIDEO_3D
0x180030d45  mov     r8d, 1
0x180030d4b  mov     rax, [rcx]
0x180030d4e  mov     rax, [rax+0A8h]
0x180030d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d5a  mov     ebx, eax
0x180030d5c  test    eax, eax
0x180030d5e  jnz     loc_180030FAB
0x180030d64  mov     rcx, [rbp+57h+ppMFType]
0x180030d68  lea     rdx, MF_MT_VIDEO_3D_FORMAT
0x180030d6f  mov     r8d, 1
0x180030d75  mov     rax, [rcx]
0x180030d78  mov     rax, [rax+0A8h]
0x180030d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d84  mov     ebx, eax
0x180030d86  test    eax, eax
0x180030d88  jnz     loc_180030FAB
0x180030d8e  mov     rcx, [r14+178h]; this
0x180030d95  cmp     dword ptr [rcx+470h], 0
0x180030d9c  jz      short loc_180030DB1
0x180030d9e  mov     rdx, [rbp+57h+ppMFType]; struct IMFMediaType *
0x180030da2  call    ?GetNaturalOutputType@CxCodeVideoProcMFTDataHandler@@QEAAJPEAUIMFMediaType@@@Z; CxCodeVideoProcMFTDataHandler::GetNaturalOutputType(IMFMediaType *)
0x180030da7  mov     ebx, eax
0x180030da9  test    eax, eax
0x180030dab  jnz     loc_180030FAB
0x180030db1  mov     r8, [rbp+57h+ppMFType]; struct IMFMediaType *
0x180030db5  xor     edx, edx; unsigned int
0x180030db7  mov     rcx, r14; this
0x180030dba  mov     [rsp+90h+arg_10], rdi
0x180030dc2  call    ?SetAvailableOutputType@CMFTMultiStreamTypeHandler@@QEAAXKPEAUIMFMediaType@@K@Z; CMFTMultiStreamTypeHandler::SetAvailableOutputType(ulong,IMFMediaType *,ulong)
0x180030dc7  mov     rcx, [rbp+57h+ppMFType]
0x180030dcb  test    rcx, rcx
0x180030dce  jz      short loc_180030DE4
0x180030dd0  mov     [rbp+57h+ppMFType], 0
0x180030dd8  mov     rax, [rcx]
0x180030ddb  mov     rax, [rax+10h]
0x180030ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030de4  xor     edi, edi
0x180030de6  test    r13d, r13d
0x180030de9  jz      loc_180030F86
0x180030def  nop
0x180030df0  mov     rcx, [rbp+57h+ppMFType]
0x180030df4  test    rcx, rcx
0x180030df7  jz      short loc_180030E0D
0x180030df9  mov     [rbp+57h+ppMFType], 0
0x180030e01  mov     rax, [rcx]
0x180030e04  mov     rax, [rax+10h]
0x180030e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e0d  lea     rcx, [rbp+57h+ppMFType]; ppMFType
0x180030e11  call    cs:__imp_MFCreateMediaType
0x180030e17  mov     ebx, eax
0x180030e19  test    eax, eax
0x180030e1b  jnz     loc_180030FA3
0x180030e21  mov     rcx, [rbp+57h+ppMFType]
0x180030e25  lea     r8, MFMediaType_Video
0x180030e2c  lea     rdx, MF_MT_MAJOR_TYPE
0x180030e33  mov     rax, [rcx]
0x180030e36  mov     rax, [rax+0C0h]
0x180030e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e42  mov     ebx, eax
0x180030e44  test    eax, eax
0x180030e46  jnz     loc_180030FA3
0x180030e4c  mov     dword ptr [rbp+57h+var_58], eax
0x180030e4f  mov     dword ptr [rbp+57h+var_58+4], 100000h
0x180030e56  mov     dword ptr [rbp+57h+var_58+8], 0AA000080h
0x180030e5d  mov     dword ptr [rbp+57h+var_58+0Ch], 719B3800h
0x180030e64  cmp     edi, esi
0x180030e66  jb      short loc_180030E90
0x180030e68  mov     rax, [r14+168h]
0x180030e6f  cmp     [rax+1Ch], bl
0x180030e72  jz      short loc_180030E90
0x180030e74  mov     ecx, edi
0x180030e76  lea     rax, __ImageBase
0x180030e7d  sub     ecx, esi
0x180030e7f  add     rcx, rcx
0x180030e82  movups  xmm0, rva xmmword_1801547B0[rax+rcx*8]
0x180030e8a  movups  [rbp+57h+var_58], xmm0
0x180030e8e  jmp     short loc_180030ED7
0x180030e90  xor     r8d, r8d
0x180030e93  xor     eax, eax
0x180030e95  nop     word ptr [rax+rax+00000000h]
0x180030ea0  lea     rdx, [rax+rax*2]
0x180030ea4  lea     rdx, ds:0[rdx*8]
0x180030eac  lea     rcx, __ImageBase
0x180030eb3  cmp     [rdx+rcx+0D3200h], r15d
0x180030ebb  jnz     short loc_180030EC9
0x180030ebd  cmp     r8d, edi
0x180030ec0  jz      loc_18003101F
0x180030ec6  inc     r8d
0x180030ec9  inc     eax
0x180030ecb  cmp     eax, 8Dh
0x180030ed0  jb      short loc_180030EA0
0x180030ed2  xor     eax, eax
0x180030ed4  mov     dword ptr [rbp+57h+var_58], eax
0x180030ed7  mov     rcx, [rbp+57h+ppMFType]
0x180030edb  lea     r8, [rbp+57h+var_58]
0x180030edf  lea     rdx, MF_MT_SUBTYPE
0x180030ee6  mov     rax, [rcx]
0x180030ee9  mov     rax, [rax+0C0h]
0x180030ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
