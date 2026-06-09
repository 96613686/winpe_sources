# sub_1800CEC0C

- ea: `0x1800cec0c`
- end: `0x1800cf5d2`
- name: `sub_1800CEC0C`
- size: `2502`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1800d5198`

## callees

- `0x180002d00`
- `0x180059ab4`
- `0x180059eac`
- `0x18005ae04`
- `0x18005b17c`
- `0x18005e330`
- `0x18005ef34`
- `0x180070474`
- `0x18007980c`
- `0x180079880`
- `0x1800c7ee8`
- `0x1800cc294`
- `0x1800cc448`
- `0x1800cec0c`
- `0x180207168`
- `0x1802b9010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800ced3f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800ced3f`

## string_xrefs

- `0x1800cec5a`: `CWICHeifDecoderFrame::CreateGainMapMetadataReader`
- `0x1800cecd2`: `CWICHeifDecoderFrame::CreateGainMapMetadataReader`
- `0x1800cedc5`: `CWICHeifDecoderFrame::CreateGainMapMetadataReader`
- `0x1800cf04b`: `CWICHeifDecoderFrame::CreateGainMapMetadataReader`
- `0x1800cf29f`: `CWICHeifDecoderFrame::CreateGainMapMetadataReader`
- `0x1800cf374`: `CWICHeifDecoderFrame::CreateGainMapMetadataReader`
- `0x1800cf542`: `CWICHeifDecoderFrame::CreateGainMapMetadataReader`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall sub_1800CEC0C(unsigned __int64 a1, char a2)
{
  char v4; // r13
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rsi
  int v9; // edi
  unsigned int *v10; // r14
  HRESULT v11; // edi
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 *v22; // rcx
  __int64 *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 *v31; // rcx
  __int64 v32; // rax
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 *v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 *v39; // rcx
  __int64 *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 *v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rsi
  __int64 (__fastcall *v47)(__int64, __int64 *, _QWORD, _QWORD, __int64 *); // rdi
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  __int64 *v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rdx
  __int64 v54; // r8
  __int64 v55; // r9
  __int64 *v56; // rcx
  __int64 v57; // rax
  __int64 v58; // r8
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 *v62; // rcx
  __int64 v63; // rdx
  __int64 v64; // r8
  __int64 v65; // r9
  __int64 *v66; // rcx
  LPSTREAM ppstm; // [rsp+38h] [rbp-39h] BYREF
  char v69; // [rsp+40h] [rbp-31h] BYREF
  _BYTE v70[3]; // [rsp+41h] [rbp-30h] BYREF
  int v71; // [rsp+44h] [rbp-2Dh] BYREF
  unsigned int v72; // [rsp+48h] [rbp-29h] BYREF
  __int64 v73; // [rsp+50h] [rbp-21h] BYREF
  __int64 v74; // [rsp+58h] [rbp-19h] BYREF
  _QWORD v75[2]; // [rsp+60h] [rbp-11h] BYREF
  _BYTE v76[32]; // [rsp+70h] [rbp-1h] BYREF
  _QWORD v77[2]; // [rsp+90h] [rbp+1Fh] BYREF

  v75[1] = -2;
  v75[0] = 0;
  v4 = 0;
  sub_180059AB4(v70, "CWICHeifDecoderFrame::CreateGainMapMetadataReader", 301);
  if ( *(_BYTE *)(qword_180685260 + 8) && *(_QWORD *)(a1 + 112) )
  {
    v8 = sub_18005AE04(qword_180685260, v5, v6, v7);
    v9 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 112) + 296LL))(*(_QWORD *)(a1 + 112));
    *(_OWORD *)(v8 + 2000) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)(a1 + 112) + 280LL))(
                                          *(_QWORD *)(a1 + 112),
                                          v77);
    *(_DWORD *)(v8 + 2016) = v9;
  }
  v10 = (unsigned int *)(a1 + 48);
  sub_18005E330(
    v76,
    (a1 + 48) & ((unsigned __int128)-(__int128)a1 >> 64),
    "CWICHeifDecoderFrame::CreateGainMapMetadataReader");
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 96) + 24LL))(*(_QWORD *)(a1 + 96)) == 4 || !a2 )
  {
    sub_180070474(v75);
    sub_1800C7EE8(a1, v75);
  }
  if ( v75[0] )
  {
    ppstm = 0;
    sub_18005B17C(&ppstm);
    v11 = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( v11 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 36, &unk_1805D65D8, *v10, v11);
      }
      v15 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v15 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v15 + 8) )
        goto LABEL_21;
      v16 = sub_18005AE04(v15, v12, v13, v14);
      if ( *(_DWORD *)(v16 + 1996) == v11 )
        goto LABEL_21;
      v17 = 319;
      goto LABEL_19;
    }
    v69 = 49;
    v71 = 0;
    v11 = ((__int64 (__fastcall *)(LPSTREAM, char *, __int64, int *))ppstm->lpVtbl->Write)(ppstm, &v69, 1, &v71);
    if ( v11 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 37, &unk_1805D65D8, *v10, v11);
      }
      v22 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v22 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v22 + 8) )
        goto LABEL_21;
      v16 = sub_18005AE04(v22, v19, v20, v21);
      if ( *(_DWORD *)(v16 + 1996) == v11 )
        goto LABEL_21;
      v17 = 324;
      goto LABEL_19;
    }
    if ( v71 != 1 )
    {
      v11 = -2147418113;
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_18007980C(*((_QWORD *)RequestContext + 2), 38, &unk_1805D65D8);
      }
      v23 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v23 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v23 + 8) )
        goto LABEL_21;
      v16 = sub_18005AE04(v23, v19, v20, v21);
      if ( *(_DWORD *)(v16 + 1996) == -2147418113 )
        goto LABEL_21;
      v18 = 2147549183LL;
      v17 = 325;
      goto LABEL_20;
    }
    if ( v75[0] )
    {
      v77[0] = 0;
      v72 = 0;
      v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD, unsigned int *))(*(_QWORD *)v75[0] + 24LL))(
              v75[0],
              v77,
              0,
              &v72);
      if ( v11 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 39, &unk_1805D65D8, *v10, v11);
        }
        v27 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v27 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v27 + 8) )
          goto LABEL_21;
        v16 = sub_18005AE04(v27, v24, v25, v26);
        if ( *(_DWORD *)(v16 + 1996) == v11 )
          goto LABEL_21;
        v17 = 331;
LABEL_19:
        v18 = (unsigned int)v11;
LABEL_20:
        sub_180207168(v16, "CWICHeifDecoderFrame::CreateGainMapMetadataReader", v17, v18);
LABEL_21:
        sub_18005B17C(&ppstm);
        goto LABEL_151;
      }
      v4 = 1;
      v11 = ((__int64 (__fastcall *)(LPSTREAM, unsigned int *, __int64, int *))ppstm->lpVtbl->Write)(
              ppstm,
              &v72,
              4,
              &v71);
      if ( v11 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 40, &unk_1805D65D8, *v10, v11);
        }
        v31 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v31 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v31 + 8) )
          goto LABEL_65;
        v32 = sub_18005AE04(v31, v28, v29, v30);
        if ( *(_DWORD *)(v32 + 1996) == v11 )
          goto LABEL_65;
        v33 = 334;
        goto LABEL_63;
      }
      if ( v71 != 4 )
      {
        v11 = -2147418113;
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_18007980C(*((_QWORD *)RequestContext + 2), 41, &unk_1805D65D8);
        }
        v35 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v35 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v35 + 8) )
          goto LABEL_65;
        v32 = sub_18005AE04(v35, v28, v29, v30);
        if ( *(_DWORD *)(v32 + 1996) == -2147418113 )
          goto LABEL_65;
        v34 = 2147549183LL;
        v33 = 335;
        goto LABEL_64;
      }
      v11 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, int *))ppstm->lpVtbl->Write)(ppstm, v77[0], v72, &v71);
      if ( v11 < 0 )
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 42, &unk_1805D65D8, *v10, v11);
        }
        v39 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v39 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v39 + 8) )
          goto LABEL_65;
        v32 = sub_18005AE04(v39, v36, v37, v38);
        if ( *(_DWORD *)(v32 + 1996) == v11 )
          goto LABEL_65;
        v33 = 337;
LABEL_63:
        v34 = (unsigned int)v11;
LABEL_64:
        sub_180207168(v32, "CWICHeifDecoderFrame::CreateGainMapMetadataReader", v33, v34);
LABEL_65:
        sub_18005B17C(&ppstm);
        goto LABEL_150;
      }
      if ( v71 != v72 )
      {
        v11 = -2147418113;
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_18007980C(*((_QWORD *)RequestContext + 2), 43, &unk_1805D65D8);
        }
        v40 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v40 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v40 + 8) )
          goto LABEL_65;
        v32 = sub_18005AE04(v40, v36, v37, v38);
        if ( *(_DWORD *)(v32 + 1996) == -2147418113 )
          goto LABEL_65;
        v34 = 2147549183LL;
        v33 = 338;
        goto LABEL_64;
      }
    }
    v11 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, 0, 0, 0);
    if ( v11 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 44, &unk_1805D65D8, *v10, v11);
      }
      v44 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v44 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v44 + 8) )
      {
        v45 = sub_18005AE04(v44, v41, v42, v43);
        if ( *(_DWORD *)(v45 + 1996) != v11 )
          sub_180207168(v45, "CWICHeifDecoderFrame::CreateGainMapMetadataReader", 341, (unsigned int)v11);
      }
LABEL_149:
      sub_18005B17C(&ppstm);
      if ( !v4 )
        goto LABEL_151;
LABEL_150:
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v75[0] + 32LL))(v75[0]);
      goto LABEL_151;
    }
    v73 = 0;
    v46 = *(_QWORD *)(a1 + 552);
    v47 = *(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v46 + 240LL);
    sub_180070474(&v73);
    v11 = v47(v46, &qword_1805D0AC0, 0, 0, &v73);
    if ( v11 < 0 )
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 45, &unk_1805D65D8, *v10, v11);
      }
      v51 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v51 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v51 + 8) )
      {
        v52 = sub_18005AE04(v51, v48, v49, v50);
        if ( *(_DWORD *)(v52 + 1996) != v11 )
          sub_180207168(v52, "CWICHeifDecoderFrame::CreateGainMapMetadataReader", 348, (unsigned int)v11);
      }
      goto LABEL_148;
    }
    v74 = 0;
    v11 = sub_1800CC294(&v73, &v74);
    if ( v11 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, LPSTREAM, _QWORD, _QWORD))(*(_QWORD *)v74 + 64LL))(v74, ppstm, 0, 0);
      if ( v11 >= 0 )
      {
        v77[0] = a1;
        v77[1] = &v73;
        v11 = sub_1800CC448(v77);
        if ( v11 >= 0 )
          goto LABEL_147;
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 48, &unk_1805D65D8, *v10, v11);
        }
        v66 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v66 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v66 + 8) )
          goto LABEL_147;
        v57 = sub_18005AE04(v66, v63, v64, v65);
        if ( *(_DWORD *)(v57 + 1996) == v11 )
          goto LABEL_147;
        v58 = 358;
      }
      else
      {
        if ( RequestContext != &RequestContext
          && (*((_BYTE *)RequestContext + 28) & 1) != 0
          && *((_BYTE *)RequestContext + 25) >= 4u )
        {
          sub_180079880(*((_QWORD *)RequestContext + 2), 47, &unk_1805D65D8, *v10, v11);
        }
        v62 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v62 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( !*((_BYTE *)v62 + 8) )
          goto LABEL_147;
        v57 = sub_18005AE04(v62, v59, v60, v61);
        if ( *(_DWORD *)(v57 + 1996) == v11 )
          goto LABEL_147;
        v58 = 352;
      }
    }
    else
    {
      if ( RequestContext != &RequestContext
        && (*((_BYTE *)RequestContext + 28) & 1) != 0
        && *((_BYTE *)RequestContext + 25) >= 4u )
      {
        sub_180079880(*((_QWORD *)RequestContext + 2), 46, &unk_1805D65D8, *v10, v11);
      }
      v56 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v56 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( !*((_BYTE *)v56 + 8) )
        goto LABEL_147;
      v57 = sub_18005AE04(v56, v53, v54, v55);
      if ( *(_DWORD *)(v57 + 1996) == v11 )
        goto LABEL_147;
      v58 = 351;
    }
    sub_180207168(v57, "CWICHeifDecoderFrame::CreateGainMapMetadataReader", v58, (unsigned int)v11);
LABEL_147:
    sub_180070474(&v74);
LABEL_148:
    sub_180070474(&v73);
    goto LABEL_149;
  }
  v11 = 0;
LABEL_151:
  sub_18005EF34(v76);
  sub_180059EAC(v70);
  sub_180070474(v75);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800cec0c  mov     rax, rsp
0x1800cec0f  push    rbp
0x1800cec10  push    r12
0x1800cec12  push    r13
0x1800cec14  push    r14
0x1800cec16  push    r15
0x1800cec18  lea     rbp, [rax-5Fh]
0x1800cec1c  sub     rsp, 0A0h
0x1800cec23  mov     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFEh
0x1800cec2b  mov     [rax+10h], rbx
0x1800cec2f  mov     [rax+18h], rsi
0x1800cec33  mov     [rax+20h], rdi
0x1800cec37  mov     rax, cs:__security_cookie
0x1800cec3e  xor     rax, rsp
0x1800cec41  mov     [rbp+57h+var_28], rax
0x1800cec45  mov     r12b, dl
0x1800cec48  mov     r15, rcx
0x1800cec4b  xor     ebx, ebx
0x1800cec4d  mov     [rbp+57h+var_68], rbx
0x1800cec51  mov     r13b, bl
0x1800cec54  mov     r8d, 12Dh
0x1800cec5a  lea     rdx, aCwicheifdecode_13; "CWICHeifDecoderFrame::CreateGainMapMeta"...
0x1800cec61  lea     rcx, [rbp+57h+var_87]
0x1800cec65  call    sub_180059AB4
0x1800cec6a  nop
0x1800cec6b  mov     rcx, cs:qword_180685260
0x1800cec72  cmp     [rcx+8], bl
0x1800cec75  jz      short loc_1800CECC2
0x1800cec77  cmp     [r15+70h], rbx
0x1800cec7b  jz      short loc_1800CECC2
0x1800cec7d  call    sub_18005AE04
0x1800cec82  mov     rsi, rax
0x1800cec85  mov     rcx, [r15+70h]
0x1800cec89  mov     rdx, [rcx]
0x1800cec8c  mov     rax, [rdx+128h]
0x1800cec93  call    j__guard_dispatch_icall
0x1800cec98  mov     edi, eax
0x1800cec9a  mov     rcx, [r15+70h]
0x1800cec9e  mov     rdx, [rcx]
0x1800ceca1  mov     rax, [rdx+118h]
0x1800ceca8  lea     rdx, [rbp+57h+var_38]
0x1800cecac  call    j__guard_dispatch_icall
0x1800cecb1  movups  xmm0, xmmword ptr [rax]
0x1800cecb4  movdqu  xmmword ptr [rsi+7D0h], xmm0
0x1800cecbc  mov     [rsi+7E0h], edi
0x1800cecc2  lea     r14, [r15+30h]
0x1800cecc6  mov     rax, r15
0x1800cecc9  neg     rax
0x1800ceccc  sbb     rdx, rdx
0x1800ceccf  and     rdx, r14
0x1800cecd2  lea     r8, aCwicheifdecode_13; "CWICHeifDecoderFrame::CreateGainMapMeta"...
0x1800cecd9  lea     rcx, [rbp+57h+var_58]
0x1800cecdd  call    sub_18005E330
0x1800cece2  nop
0x1800cece3  mov     rcx, [r15+60h]
0x1800cece7  mov     rax, [rcx]
0x1800cecea  mov     rax, [rax+18h]
0x1800cecee  call    j__guard_dispatch_icall
0x1800cecf3  mov     esi, 4
0x1800cecf8  cmp     eax, esi
0x1800cecfa  jz      short loc_1800CED01
0x1800cecfc  test    r12b, r12b
0x1800cecff  jnz     short loc_1800CED16
0x1800ced01  lea     rcx, [rbp+57h+var_68]
0x1800ced05  call    sub_180070474
0x1800ced0a  lea     rdx, [rbp+57h+var_68]
0x1800ced0e  mov     rcx, r15
0x1800ced11  call    sub_1800C7EE8
0x1800ced16  cmp     [rbp+57h+var_68], rbx
0x1800ced1a  jnz     short loc_1800CED23
0x1800ced1c  mov     edi, ebx
0x1800ced1e  jmp     loc_1800CF585
0x1800ced23  mov     [rbp+57h+ppstm], rbx
0x1800ced27  lea     rcx, [rbp+57h+ppstm]
0x1800ced2b  call    sub_18005B17C
0x1800ced30  lea     r8, [rbp+57h+ppstm]; ppstm
0x1800ced34  mov     r12d, 1
0x1800ced3a  mov     edx, r12d; fDeleteOnRelease
0x1800ced3d  xor     ecx, ecx; hGlobal
0x1800ced3f  call    cs:CreateStreamOnHGlobal
0x1800ced46  nop     dword ptr [rax+rax+00h]
0x1800ced4b  mov     edi, eax
0x1800ced4d  test    eax, eax
0x1800ced4f  jns     loc_1800CEDE3
0x1800ced55  lea     rax, RequestContext
0x1800ced5c  mov     rcx, cs:RequestContext
0x1800ced63  cmp     rcx, rax
0x1800ced66  jz      short loc_1800CED90
0x1800ced68  test    [rcx+1Ch], r12b
0x1800ced6c  jz      short loc_1800CED90
0x1800ced6e  cmp     [rcx+19h], sil
0x1800ced72  jb      short loc_1800CED90
0x1800ced74  lea     edx, [r12+23h]
0x1800ced79  mov     dword ptr [rsp+0C0h+var_A0], edi
0x1800ced7d  mov     r9d, [r14]
0x1800ced80  lea     r8, unk_1805D65D8
0x1800ced87  mov     rcx, [rcx+10h]
0x1800ced8b  call    sub_180079880
0x1800ced90  mov     rcx, cs:qword_180685260
0x1800ced97  test    rcx, rcx
0x1800ced9a  jnz     short loc_1800CEDAA
0x1800ced9c  lea     rcx, qword_180684620
0x1800ceda3  mov     cs:qword_180685260, rcx
0x1800cedaa  cmp     [rcx+8], bl
0x1800cedad  jz      short loc_1800CEDD5
0x1800cedaf  call    sub_18005AE04
0x1800cedb4  cmp     [rax+7CCh], edi
0x1800cedba  jz      short loc_1800CEDD5
0x1800cedbc  mov     r8d, 13Fh
0x1800cedc2  mov     r9d, edi
0x1800cedc5  lea     rdx, aCwicheifdecode_13; "CWICHeifDecoderFrame::CreateGainMapMeta"...
0x1800cedcc  mov     rcx, rax
0x1800cedcf  call    sub_180207168
0x1800cedd4  nop
0x1800cedd5  lea     rcx, [rbp+57h+ppstm]
0x1800cedd9  call    sub_18005B17C
0x1800cedde  jmp     loc_1800CF585
0x1800cede3  mov     [rbp+57h+var_88], 31h ; '1'
0x1800cede7  mov     [rbp+57h+var_84], ebx
0x1800cedea  mov     rcx, [rbp+57h+ppstm]
0x1800cedee  mov     rax, [rcx]
0x1800cedf1  lea     r9, [rbp+57h+var_84]
0x1800cedf5  mov     r8d, r12d
0x1800cedf8  lea     rdx, [rbp+57h+var_88]
0x1800cedfc  mov     rax, [rax+20h]
0x1800cee00  call    j__guard_dispatch_icall
0x1800cee05  mov     edi, eax
0x1800cee07  test    eax, eax
0x1800cee09  jns     short loc_1800CEE85
0x1800cee0b  lea     rax, RequestContext
0x1800cee12  mov     rcx, cs:RequestContext
0x1800cee19  cmp     rcx, rax
0x1800cee1c  jz      short loc_1800CEE46
0x1800cee1e  test    [rcx+1Ch], r12b
0x1800cee22  jz      short loc_1800CEE46
0x1800cee24  cmp     [rcx+19h], sil
0x1800cee28  jb      short loc_1800CEE46
0x1800cee2a  mov     edx, 25h ; '%'
0x1800cee2f  mov     dword ptr [rsp+0C0h+var_A0], edi
0x1800cee33  mov     r9d, [r14]
0x1800cee36  lea     r8, unk_1805D65D8
0x1800cee3d  mov     rcx, [rcx+10h]
0x1800cee41  call    sub_180079880
0x1800cee46  mov     rcx, cs:qword_180685260
0x1800cee4d  test    rcx, rcx
0x1800cee50  jnz     short loc_1800CEE60
0x1800cee52  lea     rcx, qword_180684620
0x1800cee59  mov     cs:qword_180685260, rcx
0x1800cee60  cmp     [rcx+8], bl
0x1800cee63  jz      loc_1800CEDD5
0x1800cee69  call    sub_18005AE04
0x1800cee6e  cmp     [rax+7CCh], edi
0x1800cee74  jz      loc_1800CEDD5
0x1800cee7a  mov     r8d, 144h
0x1800cee80  jmp     loc_1800CEDC2
0x1800cee85  cmp     [rbp+57h+var_84], r12d
0x1800cee89  jz      short loc_1800CEF08
0x1800cee8b  mov     esi, 8000FFFFh
0x1800cee90  mov     edi, esi
0x1800cee92  lea     rax, RequestContext
0x1800cee99  mov     rcx, cs:RequestContext
0x1800ceea0  cmp     rcx, rax
0x1800ceea3  jz      short loc_1800CEEC6
0x1800ceea5  test    [rcx+1Ch], r12b
0x1800ceea9  jz      short loc_1800CEEC6
0x1800ceeab  cmp     byte ptr [rcx+19h], 4
0x1800ceeaf  jb      short loc_1800CEEC6
0x1800ceeb1  mov     edx, 26h ; '&'
0x1800ceeb6  lea     r8, unk_1805D65D8
0x1800ceebd  mov     rcx, [rcx+10h]
0x1800ceec1  call    sub_18007980C
0x1800ceec6  mov     rcx, cs:qword_180685260
0x1800ceecd  test    rcx, rcx
0x1800ceed0  jnz     short loc_1800CEEE0
0x1800ceed2  lea     rcx, qword_180684620
0x1800ceed9  mov     cs:qword_180685260, rcx
0x1800ceee0  cmp     [rcx+8], bl
0x1800ceee3  jz      loc_1800CEDD5
0x1800ceee9  call    sub_18005AE04
0x1800ceeee  cmp     [rax+7CCh], esi
0x1800ceef4  jz      loc_1800CEDD5
0x1800ceefa  mov     r9d, esi
0x1800ceefd  mov     r8d, 145h
0x1800cef03  jmp     loc_1800CEDC5
0x1800cef08  mov     rcx, [rbp+57h+var_68]
0x1800cef0c  test    rcx, rcx
0x1800cef0f  jz      loc_1800CF204
0x1800cef15  mov     [rbp+57h+var_38], rbx
0x1800cef19  mov     [rbp+57h+var_80], ebx
0x1800cef1c  mov     rax, [rcx]
0x1800cef1f  lea     r9, [rbp+57h+var_80]
0x1800cef23  xor     r8d, r8d
0x1800cef26  lea     rdx, [rbp+57h+var_38]
0x1800cef2a  mov     rax, [rax+18h]
0x1800cef2e  call    j__guard_dispatch_icall
0x1800cef33  mov     edi, eax
0x1800cef35  test    eax, eax
0x1800cef37  jns     short loc_1800CEFB3
0x1800cef39  lea     rax, RequestContext
0x1800cef40  mov     rcx, cs:RequestContext
0x1800cef47  cmp     rcx, rax
0x1800cef4a  jz      short loc_1800CEF74
0x1800cef4c  test    [rcx+1Ch], r12b
0x1800cef50  jz      short loc_1800CEF74
0x1800cef52  cmp     [rcx+19h], sil
0x1800cef56  jb      short loc_1800CEF74
0x1800cef58  mov     edx, 27h ; '''
0x1800cef5d  mov     dword ptr [rsp+0C0h+var_A0], edi
0x1800cef61  mov     r9d, [r14]
0x1800cef64  lea     r8, unk_1805D65D8
0x1800cef6b  mov     rcx, [rcx+10h]
0x1800cef6f  call    sub_180079880
0x1800cef74  mov     rcx, cs:qword_180685260
0x1800cef7b  test    rcx, rcx
0x1800cef7e  jnz     short loc_1800CEF8E
0x1800cef80  lea     rcx, qword_180684620
0x1800cef87  mov     cs:qword_180685260, rcx
0x1800cef8e  cmp     [rcx+8], bl
0x1800cef91  jz      loc_1800CEDD5
0x1800cef97  call    sub_18005AE04
0x1800cef9c  cmp     [rax+7CCh], edi
0x1800cefa2  jz      loc_1800CEDD5
0x1800cefa8  mov     r8d, 14Bh
0x1800cefae  jmp     loc_1800CEDC2
0x1800cefb3  mov     r13b, r12b
0x1800cefb6  mov     rcx, [rbp+57h+ppstm]
0x1800cefba  mov     rax, [rcx]
0x1800cefbd  lea     r9, [rbp+57h+var_84]
0x1800cefc1  mov     r8d, esi
0x1800cefc4  lea     rdx, [rbp+57h+var_80]
0x1800cefc8  mov     rax, [rax+20h]
0x1800cefcc  call    j__guard_dispatch_icall
0x1800cefd1  mov     edi, eax
0x1800cefd3  test    eax, eax
0x1800cefd5  jns     loc_1800CF069
0x1800cefdb  lea     rax, RequestContext
0x1800cefe2  mov     rcx, cs:RequestContext
0x1800cefe9  cmp     rcx, rax
0x1800cefec  jz      short loc_1800CF016
0x1800cefee  test    [rcx+1Ch], r12b
0x1800ceff2  jz      short loc_1800CF016
0x1800ceff4  cmp     [rcx+19h], sil
0x1800ceff8  jb      short loc_1800CF016
0x1800ceffa  mov     edx, 28h ; '('
0x1800cefff  mov     dword ptr [rsp+0C0h+var_A0], edi
0x1800cf003  mov     r9d, [r14]
0x1800cf006  lea     r8, unk_1805D65D8
0x1800cf00d  mov     rcx, [rcx+10h]
0x1800cf011  call    sub_180079880
0x1800cf016  mov     rcx, cs:qword_180685260
0x1800cf01d  test    rcx, rcx
0x1800cf020  jnz     short loc_1800CF030
0x1800cf022  lea     rcx, qword_180684620
0x1800cf029  mov     cs:qword_180685260, rcx
0x1800cf030  cmp     [rcx+8], bl
0x1800cf033  jz      short loc_1800CF05B
0x1800cf035  call    sub_18005AE04
0x1800cf03a  cmp     [rax+7CCh], edi
0x1800cf040  jz      short loc_1800CF05B
0x1800cf042  mov     r8d, 14Eh
0x1800cf048  mov     r9d, edi
0x1800cf04b  lea     rdx, aCwicheifdecode_13; "CWICHeifDecoderFrame::CreateGainMapMeta"...
0x1800cf052  mov     rcx, rax
0x1800cf055  call    sub_180207168
0x1800cf05a  nop
0x1800cf05b  lea     rcx, [rbp+57h+ppstm]
0x1800cf05f  call    sub_18005B17C
0x1800cf064  jmp     loc_1800CF574
0x1800cf069  cmp     [rbp+57h+var_84], esi
0x1800cf06c  jz      short loc_1800CF0E3
0x1800cf06e  mov     esi, 8000FFFFh
0x1800cf073  mov     edi, esi
0x1800cf075  lea     rax, RequestContext
0x1800cf07c  mov     rcx, cs:RequestContext
0x1800cf083  cmp     rcx, rax
0x1800cf086  jz      short loc_1800CF0A9
0x1800cf088  test    [rcx+1Ch], r12b
0x1800cf08c  jz      short loc_1800CF0A9
0x1800cf08e  cmp     byte ptr [rcx+19h], 4
0x1800cf092  jb      short loc_1800CF0A9
0x1800cf094  mov     edx, 29h ; ')'
0x1800cf099  lea     r8, unk_1805D65D8
0x1800cf0a0  mov     rcx, [rcx+10h]
0x1800cf0a4  call    sub_18007980C
0x1800cf0a9  mov     rcx, cs:qword_180685260
0x1800cf0b0  test    rcx, rcx
0x1800cf0b3  jnz     short loc_1800CF0C3
0x1800cf0b5  lea     rcx, qword_180684620
0x1800cf0bc  mov     cs:qword_180685260, rcx
0x1800cf0c3  cmp     [rcx+8], bl
0x1800cf0c6  jz      short loc_1800CF05B
0x1800cf0c8  call    sub_18005AE04
0x1800cf0cd  cmp     [rax+7CCh], esi
0x1800cf0d3  jz      short loc_1800CF05B
0x1800cf0d5  mov     r9d, esi
0x1800cf0d8  mov     r8d, 14Fh
0x1800cf0de  jmp     loc_1800CF04B
0x1800cf0e3  mov     rcx, [rbp+57h+ppstm]
0x1800cf0e7  mov     rax, [rcx]
0x1800cf0ea  lea     r9, [rbp+57h+var_84]
  ... truncated ...
```
