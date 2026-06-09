# Vml::VmGuid::Assign(ushort const * const)

- ea: `0x18005d2dc`
- end: `0x18005e278`
- name: `?Assign@VmGuid@Vml@@QEAAXQEBG@Z`
- size: `3996`
- prototype: `void __fastcall(Vml::VmGuid *__hidden this, const unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18005e930`

## callees

- `0x18000995c`
- `0x18001587c`
- `0x18005d2dc`

## string_xrefs

- `0x18005dd54`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005dd77`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005dd9a`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005ddbd`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005dde0`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005de03`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005de26`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005de49`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005de6c`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005de8f`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005deb2`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005ded5`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005def8`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005df1b`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005df3e`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005df61`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005df84`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005dfa7`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005dfca`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005dfed`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005e010`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005e033`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005e056`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005e079`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005e09c`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005e0bf`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005e0e2`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005e105`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005e128`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005e14b`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005e16e`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005e191`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005e1b4`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005e1d7`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005e1fa`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005e21d`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005e240`: `onecore\vm\common\vml\VmGuid.h`
- `0x18005e263`: `onecore\vm\common\vml\VmGuid.h`

## pseudocode

```c
void __fastcall Vml::VmGuid::Assign(Vml::VmGuid *this, const unsigned __int16 *const a2)
{
  unsigned __int16 v4; // r14
  unsigned __int16 v5; // dx
  const unsigned __int16 *v6; // rcx
  int v7; // r9d
  int v8; // edx
  int v9; // esi
  unsigned __int16 v10; // dx
  unsigned __int8 v11; // di
  unsigned __int16 v12; // dx
  unsigned __int8 v13; // bl
  unsigned __int16 v14; // dx
  unsigned __int8 v15; // r11
  unsigned __int16 v16; // dx
  unsigned __int8 v17; // r10
  unsigned __int16 v18; // dx
  unsigned __int8 v19; // r8
  unsigned __int16 v20; // dx
  unsigned __int8 v21; // dl
  unsigned __int16 v22; // dx
  unsigned __int16 v23; // r8
  __int16 v24; // r9
  unsigned __int16 v25; // r10
  unsigned __int8 v26; // r8
  unsigned __int16 v27; // r10
  unsigned __int8 v28; // al
  unsigned __int16 v29; // dx
  unsigned __int16 v30; // r8
  __int16 v31; // r9
  unsigned __int16 v32; // r10
  unsigned __int8 v33; // r8
  unsigned __int16 v34; // r10
  unsigned __int8 v35; // al
  unsigned __int16 v36; // dx
  unsigned __int16 v37; // r8
  char v38; // r8
  unsigned __int16 v39; // dx
  unsigned __int16 v40; // r8
  char v41; // r8
  unsigned __int16 v42; // dx
  unsigned __int16 v43; // r8
  char v44; // r8
  unsigned __int16 v45; // dx
  unsigned __int16 v46; // r8
  char v47; // r8
  unsigned __int16 v48; // dx
  unsigned __int16 v49; // r8
  char v50; // r8
  unsigned __int16 v51; // dx
  unsigned __int16 v52; // r8
  char v53; // r8
  unsigned __int16 v54; // dx
  unsigned __int16 v55; // r8
  char v56; // r8
  unsigned __int16 v57; // dx
  unsigned __int16 v58; // r8
  char v59; // r8
  _WORD *v60; // rcx
  unsigned int v61; // eax
  unsigned int v62; // eax
  unsigned int v63; // eax
  unsigned int v64; // eax
  unsigned int v65; // eax
  unsigned int v66; // eax
  unsigned int v67; // eax
  unsigned int v68; // eax
  unsigned int v69; // eax
  unsigned int v70; // eax
  unsigned int v71; // eax
  unsigned int v72; // eax
  unsigned int v73; // eax
  unsigned int v74; // eax
  unsigned int v75; // eax
  unsigned int v76; // eax
  unsigned int v77; // eax
  unsigned int v78; // eax
  unsigned int v79; // eax
  unsigned int v80; // eax
  unsigned int v81; // eax
  unsigned int v82; // eax
  unsigned int v83; // eax
  unsigned int v84; // eax
  unsigned int v85; // eax
  unsigned int v86; // eax
  unsigned int v87; // eax
  unsigned int v88; // eax
  unsigned int v89; // eax
  unsigned int v90; // eax
  unsigned int v91; // eax
  unsigned int v92; // eax
  unsigned int v93; // eax
  unsigned int v94; // eax
  unsigned int v95; // eax
  unsigned int v96; // eax
  unsigned int v97; // eax
  unsigned int v98; // eax
  int v99; // [rsp+20h] [rbp-18h]
  __int128 v100; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+40h]

  if ( !a2 || (v4 = *a2) == 0 )
  {
    *(_OWORD *)this = 0;
    return;
  }
  if ( v4 == 123 )
    v5 = a2[1];
  else
    v5 = *a2;
  v6 = a2 + 1;
  if ( v4 != 123 )
    v6 = a2;
  if ( !v5 )
    goto LABEL_263;
  if ( (unsigned __int16)(v5 - 48) <= 9u )
  {
    v7 = v5;
    goto LABEL_15;
  }
  if ( (unsigned __int16)(v5 - 97) <= 5u )
  {
    v7 = v5 - 87;
    goto LABEL_15;
  }
  if ( (unsigned __int16)(v5 - 65) > 5u )
  {
LABEL_263:
    v98 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v98,
      v99);
  }
  v7 = v5 - 55;
LABEL_15:
  v8 = v6[1];
  if ( !(_WORD)v8 )
    goto LABEL_262;
  if ( (unsigned __int16)(v8 - 48) > 9u )
  {
    if ( (unsigned __int16)(v8 - 97) <= 5u )
    {
      v9 = v8 - 87;
      goto LABEL_22;
    }
    if ( (unsigned __int16)(v8 - 65) <= 5u )
    {
      v9 = v8 - 55;
      goto LABEL_22;
    }
LABEL_262:
    v97 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v97,
      v99);
  }
  v9 = v8 - 48;
LABEL_22:
  v10 = v6[2];
  if ( !v10 )
    goto LABEL_261;
  if ( (unsigned __int16)(v10 - 48) <= 9u )
  {
    v11 = v10 - 48;
    goto LABEL_29;
  }
  if ( (unsigned __int16)(v10 - 97) <= 5u )
  {
    v11 = v10 - 87;
    goto LABEL_29;
  }
  if ( (unsigned __int16)(v10 - 65) > 5u )
  {
LABEL_261:
    v96 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v96,
      v99);
  }
  v11 = v10 - 55;
LABEL_29:
  v12 = v6[3];
  if ( !v12 )
    goto LABEL_260;
  if ( (unsigned __int16)(v12 - 48) > 9u )
  {
    if ( (unsigned __int16)(v12 - 97) <= 5u )
    {
      v13 = v12 - 87;
      goto LABEL_36;
    }
    if ( (unsigned __int16)(v12 - 65) <= 5u )
    {
      v13 = v12 - 55;
      goto LABEL_36;
    }
LABEL_260:
    v95 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v95,
      v99);
  }
  v13 = v12 - 48;
LABEL_36:
  v14 = v6[4];
  if ( !v14 )
    goto LABEL_259;
  if ( (unsigned __int16)(v14 - 48) <= 9u )
  {
    v15 = v14 - 48;
    goto LABEL_43;
  }
  if ( (unsigned __int16)(v14 - 97) <= 5u )
  {
    v15 = v14 - 87;
    goto LABEL_43;
  }
  if ( (unsigned __int16)(v14 - 65) > 5u )
  {
LABEL_259:
    v94 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v94,
      v99);
  }
  v15 = v14 - 55;
LABEL_43:
  v16 = v6[5];
  if ( !v16 )
    goto LABEL_258;
  if ( (unsigned __int16)(v16 - 48) > 9u )
  {
    if ( (unsigned __int16)(v16 - 97) <= 5u )
    {
      v17 = v16 - 87;
      goto LABEL_50;
    }
    if ( (unsigned __int16)(v16 - 65) <= 5u )
    {
      v17 = v16 - 55;
      goto LABEL_50;
    }
LABEL_258:
    v93 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v93,
      v99);
  }
  v17 = v16 - 48;
LABEL_50:
  v18 = v6[6];
  if ( !v18 )
    goto LABEL_257;
  if ( (unsigned __int16)(v18 - 48) <= 9u )
  {
    v19 = v18 - 48;
    goto LABEL_57;
  }
  if ( (unsigned __int16)(v18 - 97) <= 5u )
  {
    v19 = v18 - 87;
    goto LABEL_57;
  }
  if ( (unsigned __int16)(v18 - 65) > 5u )
  {
LABEL_257:
    v92 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v92,
      v99);
  }
  v19 = v18 - 55;
LABEL_57:
  v20 = v6[7];
  if ( !v20 )
    goto LABEL_256;
  if ( (unsigned __int16)(v20 - 48) > 9u )
  {
    if ( (unsigned __int16)(v20 - 97) <= 5u )
    {
      v21 = v20 - 87;
      goto LABEL_64;
    }
    if ( (unsigned __int16)(v20 - 65) <= 5u )
    {
      v21 = v20 - 55;
      goto LABEL_64;
    }
LABEL_256:
    v91 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v91,
      v99);
  }
  v21 = v20 - 48;
LABEL_64:
  LODWORD(v100) = v21
                | (16 * (v19 | (16 * (v17 | (16 * (v15 | (16 * (v13 | (16 * (v11 | (16 * (v9 | (16 * v7)))))))))))));
  if ( v6[8] != 45 )
  {
    v61 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x44B,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v61,
      v100);
  }
  v22 = v6[9];
  if ( !v22 )
    goto LABEL_255;
  if ( (unsigned __int16)(v22 - 48) <= 9u )
    goto LABEL_71;
  if ( (unsigned __int16)(v22 - 97) <= 5u )
  {
    v22 -= 87;
    goto LABEL_71;
  }
  if ( (unsigned __int16)(v22 - 65) > 5u )
  {
LABEL_255:
    v90 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v90,
      v100);
  }
  v22 -= 55;
LABEL_71:
  v23 = v6[10];
  if ( !v23 )
    goto LABEL_254;
  v24 = v23 - 48;
  if ( (unsigned __int16)(v23 - 48) > 9u )
  {
    if ( (unsigned __int16)(v23 - 97) <= 5u )
    {
      v24 = v23 - 87;
      goto LABEL_77;
    }
    if ( (unsigned __int16)(v23 - 65) <= 5u )
    {
      v24 = v23 - 55;
      goto LABEL_77;
    }
LABEL_254:
    v89 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v89,
      v100);
  }
LABEL_77:
  v25 = v6[11];
  if ( !v25 )
    goto LABEL_253;
  v26 = v25 - 48;
  if ( (unsigned __int16)(v25 - 48) <= 9u )
    goto LABEL_83;
  if ( (unsigned __int16)(v25 - 97) <= 5u )
  {
    v26 = v25 - 87;
    goto LABEL_83;
  }
  if ( (unsigned __int16)(v25 - 65) > 5u )
  {
LABEL_253:
    v88 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v88,
      v100);
  }
  v26 = v25 - 55;
LABEL_83:
  v27 = v6[12];
  if ( !v27 )
    goto LABEL_252;
  v28 = v27 - 48;
  if ( (unsigned __int16)(v27 - 48) > 9u )
  {
    if ( (unsigned __int16)(v27 - 97) <= 5u )
    {
      v28 = v27 - 87;
      goto LABEL_89;
    }
    if ( (unsigned __int16)(v27 - 65) <= 5u )
    {
      v28 = v27 - 55;
      goto LABEL_89;
    }
LABEL_252:
    v87 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v87,
      v100);
  }
LABEL_89:
  WORD2(v100) = v28 | (unsigned __int16)(16 * (v26 | (unsigned __int16)(16 * (v24 | (16 * v22)))));
  if ( v6[13] != 45 )
  {
    v62 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x457,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v62,
      v100);
  }
  v29 = v6[14];
  if ( !v29 )
    goto LABEL_251;
  if ( (unsigned __int16)(v29 - 48) <= 9u )
    goto LABEL_96;
  if ( (unsigned __int16)(v29 - 97) <= 5u )
  {
    v29 -= 87;
    goto LABEL_96;
  }
  if ( (unsigned __int16)(v29 - 65) > 5u )
  {
LABEL_251:
    v86 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v86,
      v100);
  }
  v29 -= 55;
LABEL_96:
  v30 = v6[15];
  if ( !v30 )
    goto LABEL_250;
  v31 = v30 - 48;
  if ( (unsigned __int16)(v30 - 48) > 9u )
  {
    if ( (unsigned __int16)(v30 - 97) <= 5u )
    {
      v31 = v30 - 87;
      goto LABEL_102;
    }
    if ( (unsigned __int16)(v30 - 65) <= 5u )
    {
      v31 = v30 - 55;
      goto LABEL_102;
    }
LABEL_250:
    v85 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v85,
      v100);
  }
LABEL_102:
  v32 = v6[16];
  if ( !v32 )
    goto LABEL_249;
  v33 = v32 - 48;
  if ( (unsigned __int16)(v32 - 48) <= 9u )
    goto LABEL_108;
  if ( (unsigned __int16)(v32 - 97) <= 5u )
  {
    v33 = v32 - 87;
    goto LABEL_108;
  }
  if ( (unsigned __int16)(v32 - 65) > 5u )
  {
LABEL_249:
    v84 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v84,
      v100);
  }
  v33 = v32 - 55;
LABEL_108:
  v34 = v6[17];
  if ( !v34 )
    goto LABEL_248;
  v35 = v34 - 48;
  if ( (unsigned __int16)(v34 - 48) > 9u )
  {
    if ( (unsigned __int16)(v34 - 97) <= 5u )
    {
      v35 = v34 - 87;
      goto LABEL_114;
    }
    if ( (unsigned __int16)(v34 - 65) <= 5u )
    {
      v35 = v34 - 55;
      goto LABEL_114;
    }
LABEL_248:
    v83 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v83,
      v100);
  }
LABEL_114:
  WORD3(v100) = v35 | (unsigned __int16)(16 * (v33 | (unsigned __int16)(16 * (v31 | (16 * v29)))));
  if ( v6[18] != 45 )
  {
    v63 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x463,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v63,
      v100);
  }
  v36 = v6[19];
  if ( !v36 )
    goto LABEL_247;
  if ( (unsigned __int16)(v36 - 48) <= 9u )
    goto LABEL_121;
  if ( (unsigned __int16)(v36 - 97) <= 5u )
  {
    LOBYTE(v36) = v36 - 87;
    goto LABEL_121;
  }
  if ( (unsigned __int16)(v36 - 65) > 5u )
  {
LABEL_247:
    v82 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v82,
      v100);
  }
  LOBYTE(v36) = v36 - 55;
LABEL_121:
  v37 = v6[20];
  if ( !v37 )
    goto LABEL_246;
  if ( (unsigned __int16)(v37 - 48) > 9u )
  {
    if ( (unsigned __int16)(v37 - 97) <= 5u )
    {
      v38 = v37 - 87;
      goto LABEL_128;
    }
    if ( (unsigned __int16)(v37 - 65) <= 5u )
    {
      v38 = v37 - 55;
      goto LABEL_128;
    }
LABEL_246:
    v81 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v81,
      v100);
  }
  v38 = v37 - 48;
LABEL_128:
  BYTE8(v100) = v38 | (16 * v36);
  v39 = v6[21];
  if ( !v39 )
    goto LABEL_245;
  if ( (unsigned __int16)(v39 - 48) <= 9u )
    goto LABEL_134;
  if ( (unsigned __int16)(v39 - 97) <= 5u )
  {
    LOBYTE(v39) = v39 - 87;
    goto LABEL_134;
  }
  if ( (unsigned __int16)(v39 - 65) > 5u )
  {
LABEL_245:
    v80 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v80,
      v100);
  }
  LOBYTE(v39) = v39 - 55;
LABEL_134:
  v40 = v6[22];
  if ( !v40 )
    goto LABEL_244;
  if ( (unsigned __int16)(v40 - 48) > 9u )
  {
    if ( (unsigned __int16)(v40 - 97) <= 5u )
    {
      v41 = v40 - 87;
      goto LABEL_141;
    }
    if ( (unsigned __int16)(v40 - 65) <= 5u )
    {
      v41 = v40 - 55;
      goto LABEL_141;
    }
LABEL_244:
    v79 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v79,
      v100);
  }
  v41 = v40 - 48;
LABEL_141:
  BYTE9(v100) = v41 | (16 * v39);
  if ( v6[23] != 45 )
  {
    v64 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x472,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v64,
      v100);
  }
  v42 = v6[24];
  if ( !v42 )
    goto LABEL_243;
  if ( (unsigned __int16)(v42 - 48) <= 9u )
    goto LABEL_148;
  if ( (unsigned __int16)(v42 - 97) <= 5u )
  {
    LOBYTE(v42) = v42 - 87;
    goto LABEL_148;
  }
  if ( (unsigned __int16)(v42 - 65) > 5u )
  {
LABEL_243:
    v78 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v78,
      v100);
  }
  LOBYTE(v42) = v42 - 55;
LABEL_148:
  v43 = v6[25];
  if ( !v43 )
    goto LABEL_242;
  if ( (unsigned __int16)(v43 - 48) > 9u )
  {
    if ( (unsigned __int16)(v43 - 97) <= 5u )
    {
      v44 = v43 - 87;
      goto LABEL_155;
    }
    if ( (unsigned __int16)(v43 - 65) <= 5u )
    {
      v44 = v43 - 55;
      goto LABEL_155;
    }
LABEL_242:
    v77 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v77,
      v100);
  }
  v44 = v43 - 48;
LABEL_155:
  BYTE10(v100) = v44 | (16 * v42);
  v45 = v6[26];
  if ( !v45 )
    goto LABEL_241;
  if ( (unsigned __int16)(v45 - 48) <= 9u )
    goto LABEL_161;
  if ( (unsigned __int16)(v45 - 97) <= 5u )
  {
    LOBYTE(v45) = v45 - 87;
    goto LABEL_161;
  }
  if ( (unsigned __int16)(v45 - 65) > 5u )
  {
LABEL_241:
    v76 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v76,
      v100);
  }
  LOBYTE(v45) = v45 - 55;
LABEL_161:
  v46 = v6[27];
  if ( !v46 )
    goto LABEL_240;
  if ( (unsigned __int16)(v46 - 48) > 9u )
  {
    if ( (unsigned __int16)(v46 - 97) <= 5u )
    {
      v47 = v46 - 87;
      goto LABEL_168;
    }
    if ( (unsigned __int16)(v46 - 65) <= 5u )
    {
      v47 = v46 - 55;
      goto LABEL_168;
    }
LABEL_240:
    v75 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v75,
      v100);
  }
  v47 = v46 - 48;
LABEL_168:
  BYTE11(v100) = v47 | (16 * v45);
  v48 = v6[28];
  if ( !v48 )
    goto LABEL_239;
  if ( (unsigned __int16)(v48 - 48) <= 9u )
    goto LABEL_174;
  if ( (unsigned __int16)(v48 - 97) <= 5u )
  {
    LOBYTE(v48) = v48 - 87;
    goto LABEL_174;
  }
  if ( (unsigned __int16)(v48 - 65) > 5u )
  {
LABEL_239:
    v74 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v74,
      v100);
  }
  LOBYTE(v48) = v48 - 55;
LABEL_174:
  v49 = v6[29];
  if ( !v49 )
    goto LABEL_238;
  if ( (unsigned __int16)(v49 - 48) > 9u )
  {
    if ( (unsigned __int16)(v49 - 97) <= 5u )
    {
      v50 = v49 - 87;
      goto LABEL_181;
    }
    if ( (unsigned __int16)(v49 - 65) <= 5u )
    {
      v50 = v49 - 55;
      goto LABEL_181;
    }
LABEL_238:
    v73 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v73,
      v100);
  }
  v50 = v49 - 48;
LABEL_181:
  BYTE12(v100) = v50 | (16 * v48);
  v51 = v6[30];
  if ( !v51 )
    goto LABEL_237;
  if ( (unsigned __int16)(v51 - 48) <= 9u )
    goto LABEL_187;
  if ( (unsigned __int16)(v51 - 97) <= 5u )
  {
    LOBYTE(v51) = v51 - 87;
    goto LABEL_187;
  }
  if ( (unsigned __int16)(v51 - 65) > 5u )
  {
LABEL_237:
    v72 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v72,
      v100);
  }
  LOBYTE(v51) = v51 - 55;
LABEL_187:
  v52 = v6[31];
  if ( !v52 )
    goto LABEL_236;
  if ( (unsigned __int16)(v52 - 48) > 9u )
  {
    if ( (unsigned __int16)(v52 - 97) <= 5u )
    {
      v53 = v52 - 87;
      goto LABEL_194;
    }
    if ( (unsigned __int16)(v52 - 65) <= 5u )
    {
      v53 = v52 - 55;
      goto LABEL_194;
    }
LABEL_236:
    v71 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v71,
      v100);
  }
  v53 = v52 - 48;
LABEL_194:
  BYTE13(v100) = v53 | (16 * v51);
  v54 = v6[32];
  if ( !v54 )
    goto LABEL_235;
  if ( (unsigned __int16)(v54 - 48) <= 9u )
    goto LABEL_200;
  if ( (unsigned __int16)(v54 - 97) <= 5u )
  {
    LOBYTE(v54) = v54 - 87;
    goto LABEL_200;
  }
  if ( (unsigned __int16)(v54 - 65) > 5u )
  {
LABEL_235:
    v70 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v70,
      v100);
  }
  LOBYTE(v54) = v54 - 55;
LABEL_200:
  v55 = v6[33];
  if ( !v55 )
    goto LABEL_234;
  if ( (unsigned __int16)(v55 - 48) > 9u )
  {
    if ( (unsigned __int16)(v55 - 97) <= 5u )
    {
      v56 = v55 - 87;
      goto LABEL_207;
    }
    if ( (unsigned __int16)(v55 - 65) <= 5u )
    {
      v56 = v55 - 55;
      goto LABEL_207;
    }
LABEL_234:
    v69 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v69,
      v100);
  }
  v56 = v55 - 48;
LABEL_207:
  BYTE14(v100) = v56 | (16 * v54);
  v57 = v6[34];
  if ( !v57 )
    goto LABEL_233;
  if ( (unsigned __int16)(v57 - 48) <= 9u )
    goto LABEL_213;
  if ( (unsigned __int16)(v57 - 97) <= 5u )
  {
    LOBYTE(v57) = v57 - 87;
    goto LABEL_213;
  }
  if ( (unsigned __int16)(v57 - 65) > 5u )
  {
LABEL_233:
    v68 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v68,
      v100);
  }
  LOBYTE(v57) = v57 - 55;
LABEL_213:
  v58 = v6[35];
  if ( !v58 )
    goto LABEL_232;
  if ( (unsigned __int16)(v58 - 48) > 9u )
  {
    if ( (unsigned __int16)(v58 - 97) <= 5u )
    {
      v59 = v58 - 87;
      goto LABEL_220;
    }
    if ( (unsigned __int16)(v58 - 65) <= 5u )
    {
      v59 = v58 - 55;
      goto LABEL_220;
    }
LABEL_232:
    v67 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x410,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v67,
      v100);
  }
  v59 = v58 - 48;
LABEL_220:
  v60 = v6 + 36;
  if ( v4 == 123 )
  {
    if ( *v60 != 125 )
    {
      v65 = wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x497,
        (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
        (const char *)v65,
        v100);
    }
    ++v60;
  }
  if ( *v60 )
  {
    v66 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x49D,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)v66,
      v100);
  }
  HIBYTE(v100) = v59 | (16 * v57);
  *(_OWORD *)this = v100;
}

```

## disassembly

```asm
0x18005d2dc  push    rbp
0x18005d2de  push    rbx
0x18005d2df  push    rsi
0x18005d2e0  push    rdi
0x18005d2e1  push    r12
0x18005d2e3  push    r13
0x18005d2e5  push    r14
0x18005d2e7  push    r15
0x18005d2e9  mov     rbp, rsp
0x18005d2ec  sub     rsp, 38h
0x18005d2f0  mov     rax, rdx
0x18005d2f3  mov     r15, rcx
0x18005d2f6  test    rdx, rdx
0x18005d2f9  jz      loc_18005DD2F
0x18005d2ff  movzx   r14d, word ptr [rdx]
0x18005d303  test    r14w, r14w
0x18005d307  jz      loc_18005DD2F
0x18005d30d  cmp     r14w, 7Bh ; '{'
0x18005d312  jnz     short loc_18005D31A
0x18005d314  movzx   edx, word ptr [rdx+2]
0x18005d318  jmp     short loc_18005D31E
0x18005d31a  movzx   edx, r14w
0x18005d31e  lea     rcx, [rax+2]
0x18005d322  cmovnz  rcx, rax
0x18005d326  test    dx, dx
0x18005d329  jz      loc_18005E255
0x18005d32f  mov     r13d, 30h ; '0'
0x18005d335  movzx   eax, dx
0x18005d338  sub     ax, r13w
0x18005d33c  mov     bx, 9
0x18005d340  mov     r11w, 61h ; 'a'
0x18005d345  mov     r12w, 5
0x18005d34a  mov     r10w, 41h ; 'A'
0x18005d34f  lea     edi, [r13+27h]
0x18005d353  cmp     ax, bx
0x18005d356  ja      short loc_18005D35E
0x18005d358  movzx   r9d, dx
0x18005d35c  jmp     short loc_18005D38D
0x18005d35e  movzx   eax, dx
0x18005d361  sub     ax, r11w
0x18005d365  cmp     ax, r12w
0x18005d369  ja      short loc_18005D374
0x18005d36b  movzx   r9d, dx
0x18005d36f  sub     r9d, edi
0x18005d372  jmp     short loc_18005D38D
0x18005d374  movzx   eax, dx
0x18005d377  sub     ax, r10w
0x18005d37b  cmp     ax, r12w
0x18005d37f  ja      loc_18005E255
0x18005d385  movzx   r9d, dx
0x18005d389  sub     r9d, 37h ; '7'
0x18005d38d  movzx   edx, word ptr [rcx+2]
0x18005d391  test    dx, dx
0x18005d394  jz      loc_18005E232
0x18005d39a  movzx   eax, dx
0x18005d39d  sub     ax, r13w
0x18005d3a1  cmp     ax, bx
0x18005d3a4  ja      short loc_18005D3AD
0x18005d3a6  mov     esi, edx
0x18005d3a8  sub     esi, r13d
0x18005d3ab  jmp     short loc_18005D3D4
0x18005d3ad  movzx   eax, dx
0x18005d3b0  sub     ax, r11w
0x18005d3b4  cmp     ax, r12w
0x18005d3b8  ja      short loc_18005D3C0
0x18005d3ba  mov     esi, edx
0x18005d3bc  sub     esi, edi
0x18005d3be  jmp     short loc_18005D3D4
0x18005d3c0  movzx   eax, dx
0x18005d3c3  sub     ax, r10w
0x18005d3c7  cmp     ax, r12w
0x18005d3cb  ja      loc_18005E232
0x18005d3d1  lea     esi, [rdx-37h]
0x18005d3d4  movzx   edx, word ptr [rcx+4]
0x18005d3d8  test    dx, dx
0x18005d3db  jz      loc_18005E20F
0x18005d3e1  movzx   eax, dx
0x18005d3e4  sub     ax, r13w
0x18005d3e8  cmp     ax, bx
0x18005d3eb  ja      short loc_18005D3F4
0x18005d3ed  mov     edi, edx
0x18005d3ef  sub     edi, r13d
0x18005d3f2  jmp     short loc_18005D41A
0x18005d3f4  movzx   eax, dx
0x18005d3f7  sub     ax, r11w
0x18005d3fb  cmp     ax, r12w
0x18005d3ff  ja      short loc_18005D406
0x18005d401  lea     edi, [rdx-57h]
0x18005d404  jmp     short loc_18005D41A
0x18005d406  movzx   eax, dx
0x18005d409  sub     ax, r10w
0x18005d40d  cmp     ax, r12w
0x18005d411  ja      loc_18005E20F
0x18005d417  lea     edi, [rdx-37h]
0x18005d41a  movzx   edx, word ptr [rcx+6]
0x18005d41e  test    dx, dx
0x18005d421  jz      loc_18005E1EC
0x18005d427  movzx   eax, dx
0x18005d42a  sub     ax, r13w
0x18005d42e  cmp     ax, bx
0x18005d431  ja      short loc_18005D43A
0x18005d433  mov     ebx, edx
0x18005d435  sub     ebx, r13d
0x18005d438  jmp     short loc_18005D460
0x18005d43a  movzx   eax, dx
0x18005d43d  sub     ax, r11w
0x18005d441  cmp     ax, r12w
0x18005d445  ja      short loc_18005D44C
0x18005d447  lea     ebx, [rdx-57h]
0x18005d44a  jmp     short loc_18005D460
0x18005d44c  movzx   eax, dx
0x18005d44f  sub     ax, r10w
0x18005d453  cmp     ax, r12w
0x18005d457  ja      loc_18005E1EC
0x18005d45d  lea     ebx, [rdx-37h]
0x18005d460  movzx   edx, word ptr [rcx+8]
0x18005d464  test    dx, dx
0x18005d467  jz      loc_18005E1C9
0x18005d46d  movzx   eax, dx
0x18005d470  sub     ax, r13w
0x18005d474  cmp     ax, 9
0x18005d478  ja      short loc_18005D482
0x18005d47a  mov     r11d, edx
0x18005d47d  sub     r11d, r13d
0x18005d480  jmp     short loc_18005D4AA
0x18005d482  movzx   eax, dx
0x18005d485  sub     ax, r11w
0x18005d489  cmp     ax, r12w
0x18005d48d  ja      short loc_18005D495
0x18005d48f  lea     r11d, [rdx-57h]
0x18005d493  jmp     short loc_18005D4AA
0x18005d495  movzx   eax, dx
0x18005d498  sub     ax, r10w
0x18005d49c  cmp     ax, r12w
0x18005d4a0  ja      loc_18005E1C9
0x18005d4a6  lea     r11d, [rdx-37h]
0x18005d4aa  movzx   edx, word ptr [rcx+0Ah]
0x18005d4ae  test    dx, dx
0x18005d4b1  jz      loc_18005E1A6
0x18005d4b7  movzx   eax, dx
0x18005d4ba  sub     ax, r13w
0x18005d4be  cmp     ax, 9
0x18005d4c2  ja      short loc_18005D4CC
0x18005d4c4  mov     r10d, edx
0x18005d4c7  sub     r10d, r13d
0x18005d4ca  jmp     short loc_18005D4F0
0x18005d4cc  lea     eax, [rdx-61h]
0x18005d4cf  cmp     ax, r12w
0x18005d4d3  ja      short loc_18005D4DB
0x18005d4d5  lea     r10d, [rdx-57h]
0x18005d4d9  jmp     short loc_18005D4F0
0x18005d4db  movzx   eax, dx
0x18005d4de  sub     ax, r10w
0x18005d4e2  cmp     ax, r12w
0x18005d4e6  ja      loc_18005E1A6
0x18005d4ec  lea     r10d, [rdx-37h]
0x18005d4f0  movzx   edx, word ptr [rcx+0Ch]
0x18005d4f4  test    dx, dx
0x18005d4f7  jz      loc_18005E183
0x18005d4fd  movzx   eax, dx
0x18005d500  sub     ax, r13w
0x18005d504  cmp     ax, 9
0x18005d508  ja      short loc_18005D512
0x18005d50a  mov     r8d, edx
0x18005d50d  sub     r8d, r13d
0x18005d510  jmp     short loc_18005D532
0x18005d512  lea     eax, [rdx-61h]
0x18005d515  cmp     ax, r12w
0x18005d519  ja      short loc_18005D521
0x18005d51b  lea     r8d, [rdx-57h]
0x18005d51f  jmp     short loc_18005D532
0x18005d521  lea     eax, [rdx-41h]
0x18005d524  cmp     ax, r12w
0x18005d528  ja      loc_18005E183
0x18005d52e  lea     r8d, [rdx-37h]
0x18005d532  movzx   edx, word ptr [rcx+0Eh]
0x18005d536  test    dx, dx
0x18005d539  jz      loc_18005E160
0x18005d53f  movzx   eax, dx
0x18005d542  sub     ax, r13w
0x18005d546  cmp     ax, 9
0x18005d54a  ja      short loc_18005D551
0x18005d54c  sub     edx, r13d
0x18005d54f  jmp     short loc_18005D56F
0x18005d551  lea     eax, [rdx-61h]
0x18005d554  cmp     ax, r12w
0x18005d558  ja      short loc_18005D55F
0x18005d55a  sub     edx, 57h ; 'W'
0x18005d55d  jmp     short loc_18005D56F
0x18005d55f  lea     eax, [rdx-41h]
0x18005d562  cmp     ax, r12w
0x18005d566  ja      loc_18005E160
0x18005d56c  sub     edx, 37h ; '7'
0x18005d56f  shl     r9d, 4
0x18005d573  or      r9d, esi
0x18005d576  movzx   eax, dil
0x18005d57a  shl     r9d, 4
0x18005d57e  or      r9d, eax
0x18005d581  movzx   eax, bl
0x18005d584  shl     r9d, 4
0x18005d588  or      r9d, eax
0x18005d58b  movzx   eax, r11b
0x18005d58f  shl     r9d, 4
0x18005d593  or      r9d, eax
0x18005d596  movzx   eax, r10b
0x18005d59a  shl     r9d, 4
0x18005d59e  or      r9d, eax
0x18005d5a1  movzx   eax, r8b
0x18005d5a5  shl     r9d, 4
0x18005d5a9  or      r9d, eax
0x18005d5ac  movzx   eax, dl
0x18005d5af  shl     r9d, 4
0x18005d5b3  or      r9d, eax
0x18005d5b6  cmp     word ptr [rcx+10h], 2Dh ; '-'
0x18005d5bb  mov     dword ptr [rbp+var_18], r9d
0x18005d5bf  jnz     loc_18005DD46
0x18005d5c5  movzx   edx, word ptr [rcx+12h]
0x18005d5c9  xor     r11d, r11d
0x18005d5cc  test    dx, dx
0x18005d5cf  jz      loc_18005E13D
0x18005d5d5  movzx   eax, dx
0x18005d5d8  mov     si, 9
0x18005d5dc  sub     ax, r13w
0x18005d5e0  mov     di, 61h ; 'a'
0x18005d5e4  mov     bx, 41h ; 'A'
0x18005d5e8  cmp     ax, si
0x18005d5eb  jbe     short loc_18005D617
0x18005d5ed  movzx   eax, dx
0x18005d5f0  sub     ax, di
0x18005d5f3  cmp     ax, r12w
0x18005d5f7  ja      short loc_18005D603
0x18005d5f9  lea     r10d, [r11+57h]
0x18005d5fd  sub     dx, r10w
0x18005d601  jmp     short loc_18005D61D
0x18005d603  movzx   eax, dx
0x18005d606  sub     ax, bx
0x18005d609  cmp     ax, r12w
0x18005d60d  ja      loc_18005E13D
0x18005d613  sub     dx, 37h ; '7'
0x18005d617  mov     r10d, 57h ; 'W'
0x18005d61d  movzx   r8d, word ptr [rcx+14h]
0x18005d622  test    r8w, r8w
0x18005d626  jz      loc_18005E11A
0x18005d62c  movzx   r9d, r8w
0x18005d630  sub     r9w, r13w
0x18005d634  cmp     r9w, si
0x18005d638  jbe     short loc_18005D666
0x18005d63a  movzx   eax, r8w
0x18005d63e  sub     ax, di
0x18005d641  cmp     ax, r12w
0x18005d645  ja      short loc_18005D651
0x18005d647  movzx   r9d, r8w
0x18005d64b  sub     r9w, r10w
0x18005d64f  jmp     short loc_18005D666
0x18005d651  movzx   eax, r8w
0x18005d655  sub     ax, bx
0x18005d658  cmp     ax, r12w
0x18005d65c  ja      loc_18005E11A
0x18005d662  lea     r9d, [r8-37h]
0x18005d666  movzx   r10d, word ptr [rcx+16h]
0x18005d66b  test    r10w, r10w
0x18005d66f  jz      loc_18005E0F7
0x18005d675  movzx   r8d, r10w
0x18005d679  sub     r8w, r13w
0x18005d67d  cmp     r8w, si
0x18005d681  jbe     short loc_18005D6AB
0x18005d683  movzx   eax, r10w
0x18005d687  sub     ax, di
0x18005d68a  cmp     ax, r12w
0x18005d68e  ja      short loc_18005D696
0x18005d690  lea     r8d, [r10-57h]
0x18005d694  jmp     short loc_18005D6AB
0x18005d696  movzx   eax, r10w
0x18005d69a  sub     ax, bx
0x18005d69d  cmp     ax, r12w
0x18005d6a1  ja      loc_18005E0F7
0x18005d6a7  lea     r8d, [r10-37h]
0x18005d6ab  movzx   r10d, word ptr [rcx+18h]
0x18005d6b0  test    r10w, r10w
0x18005d6b4  jz      loc_18005E0D4
0x18005d6ba  movzx   eax, r10w
0x18005d6be  sub     ax, r13w
0x18005d6c2  cmp     ax, si
0x18005d6c5  jbe     short loc_18005D6F5
0x18005d6c7  movzx   eax, r10w
0x18005d6cb  sub     ax, di
0x18005d6ce  cmp     ax, r12w
0x18005d6d2  movzx   eax, r10w
0x18005d6d6  ja      short loc_18005D6E4
0x18005d6d8  mov     r10d, 57h ; 'W'
0x18005d6de  sub     ax, r10w
0x18005d6e2  jmp     short loc_18005D6FB
0x18005d6e4  sub     ax, bx
0x18005d6e7  cmp     ax, r12w
0x18005d6eb  ja      loc_18005E0D4
0x18005d6f1  lea     eax, [r10-37h]
0x18005d6f5  mov     r10d, 57h ; 'W'
0x18005d6fb  shl     dx, 4
0x18005d6ff  or      dx, r9w
0x18005d703  mov     r9d, 0FFh
  ... truncated ...
```
