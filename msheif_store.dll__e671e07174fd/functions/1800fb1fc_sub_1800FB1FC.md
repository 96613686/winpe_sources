# sub_1800FB1FC

- ea: `0x1800fb1fc`
- end: `0x1800fc00e`
- name: `sub_1800FB1FC`
- size: `3602`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: ``

## callers

- `0x1800f8c20`

## callees

- `0x180002d00`
- `0x180059ab4`
- `0x180059eac`
- `0x18005ae04`
- `0x18005bab0`
- `0x18007980c`
- `0x180079880`
- `0x180079b90`
- `0x1800f62fc`
- `0x1800f71b8`
- `0x1800f73e8`
- `0x1800f82e4`
- `0x1800fb1fc`
- `0x180105908`
- `0x180105968`
- `0x1801059dc`
- `0x180105a84`
- `0x18014aaa4`
- `0x180157a84`
- `0x18018b2a0`
- `0x180207168`
- `0x1802b9010`

## import_xrefs

- `MFPlat!MFCreateMediaBufferWrapper` at `0x1800fb94c`
- `MFPlat!MFCreateMediaBufferWrapper` at `0x1800fb94c`

## string_xrefs

- `0x1800fb281`: `CHEIFStreamReader::ParseStream`
- `0x1800fb2df`: `CHEIFStreamReader::ParseStream`
- `0x1800fb4e9`: `CHEIFStreamReader::ParseStream`
- `0x1800fb5e4`: `CHEIFStreamReader::ParseStream`
- `0x1800fb6af`: `CHEIFStreamReader::ParseStream`
- `0x1800fb77e`: `CHEIFStreamReader::ParseStream`
- `0x1800fb825`: `CHEIFStreamReader::ParseStream`
- `0x1800fb8cf`: `CHEIFStreamReader::ParseStream`
- `0x1800fb9f2`: `CHEIFStreamReader::ParseStream`
- `0x1800fba4d`: `CHEIFStreamReader::ParseStream`
- `0x1800fbbec`: `CHEIFStreamReader::ParseStream`
- `0x1800fbc47`: `CHEIFStreamReader::ParseStream`
- `0x1800fbca2`: `CHEIFStreamReader::ParseStream`
- `0x1800fbcfd`: `CHEIFStreamReader::ParseStream`
- `0x1800fbd58`: `CHEIFStreamReader::ParseStream`
- `0x1800fbdd6`: `CHEIFStreamReader::ParseStream`
- `0x1800fbe69`: `CHEIFStreamReader::ParseStream`
- `0x1800fbf40`: `CHEIFStreamReader::ParseStream`
- `0x1800fbf97`: `CHEIFStreamReader::ParseStream`

## pseudocode

```c
__int64 __fastcall sub_1800FB1FC(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v3; // rsi
  unsigned __int64 v4; // r13
  __int64 v5; // rdx
  int v6; // edi
  __int64 v7; // r8
  __int64 *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r12
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  char v18; // cl
  unsigned __int32 v19; // r12d
  unsigned __int64 v20; // r14
  __int64 v21; // rdx
  __int64 *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rdx
  unsigned __int64 v25; // r9
  bool v26; // al
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 *v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 *v43; // rcx
  __int64 v44; // rax
  __int64 *v45; // rcx
  __int64 v46; // rax
  int v47; // r12d
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 *v52; // rcx
  __int64 v53; // rax
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 *v58; // rcx
  __int64 v59; // rax
  __int64 *v60; // rcx
  __int64 v61; // rax
  __int64 v62; // rdx
  __int64 v63; // r8
  int v64; // r13d
  unsigned int v65; // r12d
  unsigned int v66; // r14d
  __int64 v67; // rsi
  int v68; // eax
  const char *v69; // r9
  __int64 *v70; // rcx
  __int64 v71; // rax
  __int64 *v72; // rcx
  __int64 v73; // rax
  __int64 *v74; // rcx
  __int64 v75; // rax
  __int64 *v76; // rcx
  __int64 v77; // rax
  __int64 *v78; // rcx
  __int64 v79; // rax
  __int64 *v80; // rcx
  __int64 v81; // rax
  __int64 *v82; // rcx
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 *v87; // rcx
  __int64 v88; // rax
  __int64 *v89; // rcx
  __int64 v90; // rax
  int v91; // [rsp+20h] [rbp-E0h]
  int v92; // [rsp+28h] [rbp-D8h]
  int v93; // [rsp+30h] [rbp-D0h]
  _BYTE v94[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v95; // [rsp+48h] [rbp-B8h]
  unsigned __int32 v96; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v97; // [rsp+58h] [rbp-A8h]
  __int64 v98; // [rsp+60h] [rbp-A0h]
  _QWORD *v99; // [rsp+68h] [rbp-98h]
  _QWORD *v100; // [rsp+70h] [rbp-90h]
  unsigned __int64 v101; // [rsp+78h] [rbp-88h] BYREF
  __int64 v102; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v103; // [rsp+88h] [rbp-78h] BYREF
  IMFMediaBuffer *pBuffer; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v105; // [rsp+98h] [rbp-68h] BYREF
  __int64 v106; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v107; // [rsp+A8h] [rbp-58h] BYREF
  IMFMediaBuffer *ppBuffer[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v109[272]; // [rsp+C0h] [rbp-40h] BYREF

  v100 = a3;
  v99 = a2;
  v3 = a1;
  v98 = a1;
  v4 = 0;
  pBuffer = 0;
  v106 = 0;
  v107 = 0;
  v97 = 0;
  if ( !a2 || !a3 )
  {
    sub_1800F62FC(&v107);
    sub_1800F62FC(&v106);
    sub_1800F62FC(&pBuffer);
    return 2147500035LL;
  }
  *a2 = 0;
  *a3 = 0;
  sub_1800F82E4();
  *(_QWORD *)(v3 + 40) = 0;
  *(_DWORD *)(v3 + 48) = 0;
  sub_180059AB4(v94, "CHEIFStreamReader::ParseStream", 157);
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(v3 + 56) + 40LL))(
         *(_QWORD *)(v3 + 56),
         0,
         0,
         0);
  if ( v6 < 0 )
  {
    v8 = (__int64 *)qword_180685260;
    if ( !qword_180685260 )
    {
      v8 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v9 = sub_18005AE04(v8, v5, v7);
      if ( *(_DWORD *)(v9 + 1996) != v6 )
        sub_180207168(v9, "CHEIFStreamReader::ParseStream", 157);
    }
    if ( byte_180685210 )
    {
      v10 = 16;
      goto LABEL_11;
    }
    goto LABEL_215;
  }
  LODWORD(v11) = 0x10000;
  v95 = 0x10000;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        if ( v4 + (unsigned int)v11 > *(_QWORD *)(v3 + 32) )
        {
          LODWORD(v11) = *(_DWORD *)(v3 + 32) - v4;
          v95 = (unsigned int)v11;
        }
        if ( !(_DWORD)v11 || !pBuffer && v4 + (unsigned int)v11 <= v97 )
          goto LABEL_210;
        v97 = v4 + (unsigned int)v11;
        v102 = 0;
        v105 = 0;
        v96 = 0;
        v103 = 0;
        v101 = 0;
        if ( !pBuffer )
        {
          v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD, IMFMediaBuffer **))(*(_QWORD *)(v3 + 24)
                                                                                               + 48LL))(
                 v3 + 24,
                 v4,
                 (unsigned int)v11,
                 &pBuffer);
          if ( v6 < 0 )
          {
            v58 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v58 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( *((_BYTE *)v58 + 8) )
            {
              v59 = sub_18005AE04(v58, v12, v13);
              if ( *(_DWORD *)(v59 + 1996) != v6 )
                sub_180207168(v59, "CHEIFStreamReader::ParseStream", 190);
            }
            if ( byte_180685210 )
            {
              v10 = 17;
              goto LABEL_11;
            }
            goto LABEL_215;
          }
        }
        v6 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64 *, _QWORD, unsigned int *))pBuffer->lpVtbl->Lock)(
               pBuffer,
               &v102,
               0,
               &v105);
        if ( v6 < 0 )
        {
          v89 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v89 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( *((_BYTE *)v89 + 8) )
          {
            v90 = sub_18005AE04(v89, v14, v15);
            if ( *(_DWORD *)(v90 + 1996) != v6 )
              sub_180207168(v90, "CHEIFStreamReader::ParseStream", 193);
          }
          if ( !byte_180685210 )
            goto LABEL_215;
          v10 = 18;
LABEL_11:
          sub_180105A84(*((_QWORD *)RequestContext + 2), v10, &stru_1805D9498, v3, v6);
          goto LABEL_215;
        }
        v6 = sub_18014AAA4(v105, v102, &v96, &v101, &v103);
        ((void (__fastcall *)(IMFMediaBuffer *))pBuffer->lpVtbl->Unlock)(pBuffer);
        if ( v6 != -1072863856 )
          break;
        if ( !v105 )
          *(_QWORD *)(v3 + 32) = v4;
        LODWORD(v11) = 0x10000;
        v95 = 0x10000;
        if ( pBuffer )
          sub_1800F73E8(&pBuffer, 0);
        v6 = 0;
      }
      if ( v6 < 0 )
      {
        v87 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v87 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v87 + 8) )
        {
          v88 = sub_18005AE04(v87, v16, v17);
          if ( *(_DWORD *)(v88 + 1996) != v6 )
            sub_180207168(v88, "CHEIFStreamReader::ParseStream", 425);
        }
        if ( !byte_180685210 )
          goto LABEL_215;
        v10 = 40;
        goto LABEL_11;
      }
      v18 = byte_180685211;
      v19 = v96;
      v20 = v101;
      if ( (unsigned __int8)byte_180685211 >= 0x10u )
      {
        LOBYTE(v92) = BYTE1(v96);
        LOBYTE(v93) = v96;
        LOBYTE(v91) = BYTE2(v96);
        sub_1801059DC(*((_QWORD *)RequestContext + 7), v16, v17, HIBYTE(v96), v91, v92, v93, v101);
        v18 = byte_180685211;
      }
      v21 = v103;
      if ( v20 )
      {
        v25 = v20 + v4;
        if ( v20 + v4 < v4 )
        {
          v25 = -1;
LABEL_198:
          if ( (unsigned __int8)v18 >= 4u )
          {
            sub_180105968(*((_QWORD *)RequestContext + 7), v103, v17, v25, *(_QWORD *)(v3 + 32));
            v18 = byte_180685211;
          }
          if ( v106 )
          {
            if ( (unsigned __int8)v18 >= 4u )
              sub_18007980C(*((_QWORD *)RequestContext + 7), 22, &stru_1805D9498);
LABEL_210:
            if ( !v106 )
              *(_QWORD *)(v3 + 40) = 0;
            if ( !v107 )
              *(_DWORD *)(v3 + 48) = 0;
            v84 = v106;
            v106 = 0;
            *v99 = v84;
            v85 = v107;
            v107 = 0;
            *v100 = v85;
            goto LABEL_215;
          }
          v82 = (__int64 *)qword_180685260;
          v6 = -1072875842;
          if ( !qword_180685260 )
          {
            v82 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( *((_BYTE *)v82 + 8) )
          {
            v83 = sub_18005AE04(v82, v21, v17);
            if ( *(_DWORD *)(v83 + 1996) != -1072875842 )
              sub_180207168(v83, "CHEIFStreamReader::ParseStream", 242);
          }
          if ( !byte_180685210 )
            goto LABEL_215;
          v24 = 23;
LABEL_40:
          sub_180105A84(*((_QWORD *)RequestContext + 2), v24, &stru_1805D9498, v3, -1072875842);
          goto LABEL_215;
        }
        if ( v25 > *(_QWORD *)(v3 + 32) )
          goto LABEL_198;
      }
      else
      {
        v20 = *(_QWORD *)(v3 + 32) - v4;
        if ( v20 < v103 )
        {
          v22 = (__int64 *)qword_180685260;
          v6 = -1072875842;
          if ( !qword_180685260 )
          {
            v22 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( *((_BYTE *)v22 + 8) )
          {
            v23 = sub_18005AE04(v22, v103, v17);
            if ( *(_DWORD *)(v23 + 1996) != -1072875842 )
              sub_180207168(v23, "CHEIFStreamReader::ParseStream", 223);
          }
          if ( !byte_180685210 )
            goto LABEL_215;
          v24 = 20;
          goto LABEL_40;
        }
      }
      v26 = v105 >= v20 || (v19 == 1835295092 || v19 == 1718773093) && v105 >= v103;
      if ( v19 != 1718183032 && v19 != 1718773093 )
        break;
      if ( !v26 )
      {
LABEL_118:
        v11 = 16;
        goto LABEL_119;
      }
      v6 = sub_1800F71B8(v3, 5, v4, v20);
      if ( v6 < 0 )
      {
        v80 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v80 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v80 + 8) )
        {
          v81 = sub_18005AE04(v80, v54, v55);
          if ( *(_DWORD *)(v81 + 1996) != v6 )
            sub_180207168(v81, "CHEIFStreamReader::ParseStream", 278);
        }
        if ( !byte_180685210 )
          goto LABEL_215;
        v10 = 26;
        goto LABEL_11;
      }
LABEL_111:
      if ( !v20 )
        goto LABEL_210;
      if ( v20 + v4 >= v105 + v4 )
      {
        v4 += v20;
        v11 = 0x10000;
LABEL_119:
        v95 = v11;
        goto LABEL_120;
      }
      ppBuffer[0] = 0;
      v6 = MFCreateMediaBufferWrapper(pBuffer, v20, v105 - v20, ppBuffer);
      if ( v6 < 0 )
      {
        v78 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v78 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v78 + 8) )
        {
          v79 = sub_18005AE04(v78, v56, v57);
          if ( *(_DWORD *)(v79 + 1996) != v6 )
            sub_180207168(v79, "CHEIFStreamReader::ParseStream", 406);
        }
        if ( byte_180685210 )
          sub_180105A84(*((_QWORD *)RequestContext + 2), 39, &stru_1805D9498, v3, v6);
        sub_1800F62FC(ppBuffer);
        goto LABEL_215;
      }
      if ( pBuffer != ppBuffer[0] )
        sub_1800F73E8(&pBuffer, ppBuffer[0]);
      v4 += v20;
      LODWORD(v11) = v95 - v20;
      v95 = (unsigned int)(v95 - v20);
      sub_1800F62FC(ppBuffer);
    }
    if ( v19 == 1835295092 )
    {
      if ( !v26 )
        goto LABEL_118;
      v47 = v20 - v103;
      v6 = sub_1800F71B8(v3, 3, v103, (unsigned int)v20 - v103);
      if ( v6 < 0 )
      {
        v76 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v76 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v76 + 8) )
        {
          v77 = sub_18005AE04(v76, v48, v49);
          if ( *(_DWORD *)(v77 + 1996) != v6 )
            sub_180207168(v77, "CHEIFStreamReader::ParseStream", 259);
        }
        if ( !byte_180685210 )
          goto LABEL_215;
        v10 = 24;
        goto LABEL_11;
      }
      v6 = sub_1800F71B8(v3, 4, (unsigned int)v4 + v103, v47);
      if ( v6 < 0 )
      {
        v52 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v52 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v52 + 8) )
        {
          v53 = sub_18005AE04(v52, v50, v51);
          if ( *(_DWORD *)(v53 + 1996) != v6 )
            sub_180207168(v53, "CHEIFStreamReader::ParseStream", 260);
        }
        if ( byte_180685210 )
        {
          v10 = 25;
          goto LABEL_11;
        }
        goto LABEL_215;
      }
      goto LABEL_111;
    }
    if ( v19 == 1835365473 && !v106 )
      break;
    if ( v19 != 1836019574 || v107 )
    {
      v6 = sub_1800F71B8(v3, 6, v4, v20);
      if ( v6 < 0 )
      {
        v29 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v29 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v29 + 8) )
        {
          v30 = sub_18005AE04(v29, v27, v28);
          if ( *(_DWORD *)(v30 + 1996) != v6 )
            sub_180207168(v30, "CHEIFStreamReader::ParseStream", 378);
        }
        if ( byte_180685210 )
        {
          v10 = 36;
          goto LABEL_11;
        }
        goto LABEL_215;
      }
      goto LABEL_111;
    }
    *(_DWORD *)(v3 + 48) = v20;
    if ( v26 )
    {
      v6 = sub_180157A84(pBuffer, &v107, 4);
      if ( v6 < 0 )
      {
        v74 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v74 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v74 + 8) )
        {
          v75 = sub_18005AE04(v74, v37, v38);
          if ( *(_DWORD *)(v75 + 1996) != v6 )
            sub_180207168(v75, "CHEIFStreamReader::ParseStream", 359);
        }
        if ( !byte_180685210 )
          goto LABEL_215;
        v10 = 33;
        goto LABEL_11;
      }
      if ( v106 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v106 + 24LL))(v106, v107);
        if ( v6 < 0 )
        {
          v72 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v72 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( *((_BYTE *)v72 + 8) )
          {
            v73 = sub_18005AE04(v72, v39, v40);
            if ( *(_DWORD *)(v73 + 1996) != v6 )
              sub_180207168(v73, "CHEIFStreamReader::ParseStream", 363);
          }
          if ( !byte_180685210 )
            goto LABEL_215;
          v10 = 34;
          goto LABEL_11;
        }
      }
      v6 = sub_1800F71B8(v3, 2, v4, *(_DWORD *)(v3 + 48));
      if ( v6 < 0 )
      {
        v43 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v43 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v43 + 8) )
        {
          v44 = sub_18005AE04(v43, v41, v42);
          if ( *(_DWORD *)(v44 + 1996) != v6 )
            sub_180207168(v44, "CHEIFStreamReader::ParseStream", 366);
        }
        if ( byte_180685210 )
        {
          v10 = 35;
          goto LABEL_11;
        }
        goto LABEL_215;
      }
      goto LABEL_111;
    }
LABEL_88:
    if ( !v20 )
      goto LABEL_111;
    v95 = v20;
    LODWORD(v11) = v20;
    if ( v20 > 0xC800000 )
    {
      if ( (unsigned __int8)v18 >= 4u )
        sub_180105908(*((_QWORD *)RequestContext + 7), 37, &stru_1805D9498, v20);
      v45 = (__int64 *)qword_180685260;
      v6 = -1072875842;
      if ( !qword_180685260 )
      {
        v45 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v45 + 8) )
      {
        v46 = sub_18005AE04(v45, v21, v17);
        if ( *(_DWORD *)(v46 + 1996) != -1072875842 )
          sub_180207168(v46, "CHEIFStreamReader::ParseStream", 391);
      }
      if ( !byte_180685210 )
        goto LABEL_215;
      v24 = 38;
      goto LABEL_40;
    }
LABEL_120:
    if ( pBuffer )
      sub_1800F73E8(&pBuffer, 0);
  }
  *(_QWORD *)(v3 + 40) = v20;
  if ( !v26 )
    goto LABEL_88;
  v6 = sub_18018B2A0(pBuffer, &v106, *(_QWORD *)(v3 + 64));
  if ( v6 < 0 )
  {
    v101 = 0;
    v103 = 0;
    if ( ((int (__fastcall *)(IMFMediaBuffer *, unsigned __int64 *, _QWORD, unsigned int *))pBuffer->lpVtbl->Lock)(
           pBuffer,
           &v101,
           0,
           &v103) >= 0 )
    {
      v64 = 0;
      if ( (unsigned __int8)byte_180685211 >= 0x10u )
        sub_180079880(*((_QWORD *)RequestContext + 7), 27, &stru_1805D9498, (unsigned int)v6, v103);
      v65 = 0;
      if ( v103 )
      {
        do
        {
          if ( v64 < 0 )
            break;
          v66 = 0;
          v67 = v101 + v65;
          do
          {
            if ( v66 + v65 >= v103 )
              break;
            if ( v64 < 0 )
              break;
            v68 = sub_18005BAB0(&v109[2 * v66], 257 - 2 * v66, "%02x", *(unsigned __int8 *)(v66 + v67));
            ++v66;
            v64 = v68;
          }
          while ( 2 * v66 < 0x100 );
          if ( (unsigned __int8)byte_180685211 >= 0x10u )
          {
            v69 = v109;
            if ( v64 < 0 )
              v69 = "failed!";
            sub_180079B90(*((_QWORD *)RequestContext + 7), 28, &stru_1805D9498, v69);
          }
          v65 += v66;
        }
        while ( v65 < v103 );
        v3 = v98;
      }
      if ( (unsigned __int8)byte_180685211 >= 0x10u )
        sub_18007980C(*((_QWORD *)RequestContext + 7), 29, &stru_1805D9498);
      ((void (__fastcall *)(IMFMediaBuffer *))pBuffer->lpVtbl->Unlock)(pBuffer);
    }
    v70 = (__int64 *)qword_180685260;
    if ( !qword_180685260 )
    {
      v70 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( *((_BYTE *)v70 + 8) )
    {
      v71 = sub_18005AE04(v70, v62, v63);
      if ( *(_DWORD *)(v71 + 1996) != v6 )
        sub_180207168(v71, "CHEIFStreamReader::ParseStream", 330);
    }
    if ( !byte_180685210 )
      goto LABEL_215;
    v10 = 30;
    goto LABEL_11;
  }
  if ( !v107 || (v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v106 + 24LL))(v106), v6 >= 0) )
  {
    v6 = sub_1800F71B8(v3, 1, v4, *(_QWORD *)(v3 + 40));
    if ( v6 < 0 )
    {
      v35 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v35 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v36 = sub_18005AE04(v35, v33, v34);
        if ( *(_DWORD *)(v36 + 1996) != v6 )
          sub_180207168(v36, "CHEIFStreamReader::ParseStream", 337);
      }
      if ( byte_180685210 )
      {
        v10 = 32;
        goto LABEL_11;
      }
      goto LABEL_215;
    }
    goto LABEL_111;
  }
  v60 = (__int64 *)qword_180685260;
  if ( !qword_180685260 )
  {
    v60 = &qword_180684620;
    qword_180685260 = (__int64)&qword_180684620;
  }
  if ( *((_BYTE *)v60 + 8) )
  {
    v61 = sub_18005AE04(v60, v31, v32);
    if ( *(_DWORD *)(v61 + 1996) != v6 )
      sub_180207168(v61, "CHEIFStreamReader::ParseStream", 334);
  }
  if ( byte_180685210 )
  {
    v10 = 31;
    goto LABEL_11;
  }
LABEL_215:
  sub_180059EAC(v94);
  sub_1800F62FC(&v107);
  sub_1800F62FC(&v106);
  sub_1800F62FC(&pBuffer);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800fb1fc  mov     [rsp-8+arg_18], rbx
0x1800fb201  push    rbp
0x1800fb202  push    rsi
0x1800fb203  push    rdi
0x1800fb204  push    r12
0x1800fb206  push    r13
0x1800fb208  push    r14
0x1800fb20a  push    r15
0x1800fb20c  lea     rbp, [rsp-0E0h]
0x1800fb214  sub     rsp, 1E0h
0x1800fb21b  mov     rax, cs:__security_cookie
0x1800fb222  xor     rax, rsp
0x1800fb225  mov     [rbp+110h+var_40], rax
0x1800fb22c  xor     ebx, ebx
0x1800fb22e  mov     [rsp+210h+var_1A0], r8
0x1800fb233  mov     [rsp+210h+var_1A8], rdx
0x1800fb238  mov     rsi, rcx
0x1800fb23b  mov     [rsp+210h+var_1B0], rcx
0x1800fb240  mov     r13d, ebx
0x1800fb243  mov     [rbp+110h+pBuffer], rbx
0x1800fb247  mov     [rbp+110h+var_170], rbx
0x1800fb24b  mov     [rbp+110h+var_168], rbx
0x1800fb24f  mov     [rsp+210h+var_1B8], rbx
0x1800fb254  test    rdx, rdx
0x1800fb257  jz      loc_1800FBFC3
0x1800fb25d  test    r8, r8
0x1800fb260  jz      loc_1800FBFC3
0x1800fb266  mov     [rdx], rbx
0x1800fb269  mov     [r8], rbx
0x1800fb26c  call    sub_1800F82E4
0x1800fb271  mov     r14d, 9Dh
0x1800fb277  mov     [rsi+28h], rbx
0x1800fb27b  mov     r8d, r14d
0x1800fb27e  mov     [rsi+30h], ebx
0x1800fb281  lea     rdx, aCheifstreamrea_20; "CHEIFStreamReader::ParseStream"
0x1800fb288  lea     rcx, [rsp+210h+var_1D0]
0x1800fb28d  call    sub_180059AB4
0x1800fb292  mov     rcx, [rsi+38h]
0x1800fb296  xor     r9d, r9d
0x1800fb299  xor     r8d, r8d
0x1800fb29c  mov     edx, ebx
0x1800fb29e  mov     rax, [rcx]
0x1800fb2a1  mov     rax, [rax+28h]
0x1800fb2a5  call    j__guard_dispatch_icall
0x1800fb2aa  mov     edi, eax
0x1800fb2ac  test    eax, eax
0x1800fb2ae  jns     short loc_1800FB32B
0x1800fb2b0  mov     rcx, cs:qword_180685260
0x1800fb2b7  test    rcx, rcx
0x1800fb2ba  jnz     short loc_1800FB2CA
0x1800fb2bc  lea     rcx, qword_180684620
0x1800fb2c3  mov     cs:qword_180685260, rcx
0x1800fb2ca  cmp     [rcx+8], bl
0x1800fb2cd  jz      short loc_1800FB2F1
0x1800fb2cf  call    sub_18005AE04
0x1800fb2d4  cmp     [rax+7CCh], edi
0x1800fb2da  jz      short loc_1800FB2F1
0x1800fb2dc  mov     r9d, edi
0x1800fb2df  lea     rdx, aCheifstreamrea_20; "CHEIFStreamReader::ParseStream"
0x1800fb2e6  mov     r8d, r14d
0x1800fb2e9  mov     rcx, rax
0x1800fb2ec  call    sub_180207168
0x1800fb2f1  mov     r15d, 1
0x1800fb2f7  cmp     cs:byte_180685210, r15b
0x1800fb2fe  jb      loc_1800FBEE5
0x1800fb304  lea     edx, [r15+0Fh]
0x1800fb308  mov     dword ptr [rsp+210h+var_1F0], edi
0x1800fb30c  mov     rcx, cs:RequestContext
0x1800fb313  lea     r8, stru_1805D9498
0x1800fb31a  mov     r9, rsi
0x1800fb31d  mov     rcx, [rcx+10h]
0x1800fb321  call    sub_180105A84
0x1800fb326  jmp     loc_1800FBEE5
0x1800fb32b  mov     r12d, 10000h
0x1800fb331  mov     r15d, 1
0x1800fb337  mov     [rsp+210h+var_1C8], r12
0x1800fb33c  mov     ecx, r12d
0x1800fb33f  add     rcx, r13
0x1800fb342  cmp     rcx, [rsi+20h]
0x1800fb346  jbe     short loc_1800FB354
0x1800fb348  mov     r12d, [rsi+20h]
0x1800fb34c  sub     r12d, r13d
0x1800fb34f  mov     [rsp+210h+var_1C8], r12
0x1800fb354  test    r12d, r12d
0x1800fb357  jz      loc_1800FBEB2
0x1800fb35d  mov     eax, r12d
0x1800fb360  add     rax, r13
0x1800fb363  cmp     [rbp+110h+pBuffer], rbx
0x1800fb367  jnz     short loc_1800FB374
0x1800fb369  cmp     rax, [rsp+210h+var_1B8]
0x1800fb36e  jbe     loc_1800FBEB2
0x1800fb374  mov     [rsp+210h+var_1B8], rax
0x1800fb379  mov     [rbp+110h+var_190], rbx
0x1800fb37d  mov     [rbp+110h+var_178], ebx
0x1800fb380  mov     [rsp+210h+var_1C0], ebx
0x1800fb384  mov     [rbp+110h+var_188], ebx
0x1800fb387  mov     [rsp+210h+var_198], rbx
0x1800fb38c  cmp     [rbp+110h+pBuffer], rbx
0x1800fb390  jnz     short loc_1800FB3B6
0x1800fb392  lea     rcx, [rsi+18h]
0x1800fb396  mov     r8d, r12d
0x1800fb399  mov     rax, [rcx]
0x1800fb39c  lea     r9, [rbp+110h+pBuffer]
0x1800fb3a0  mov     rdx, r13
0x1800fb3a3  mov     rax, [rax+30h]
0x1800fb3a7  call    j__guard_dispatch_icall
0x1800fb3ac  mov     edi, eax
0x1800fb3ae  test    eax, eax
0x1800fb3b0  js      loc_1800FB9C3
0x1800fb3b6  mov     rcx, [rbp+110h+pBuffer]
0x1800fb3ba  lea     r9, [rbp+110h+var_178]
0x1800fb3be  xor     r8d, r8d
0x1800fb3c1  lea     rdx, [rbp+110h+var_190]
0x1800fb3c5  mov     rax, [rcx]
0x1800fb3c8  mov     rax, [rax+18h]
0x1800fb3cc  call    j__guard_dispatch_icall
0x1800fb3d1  mov     edi, eax
0x1800fb3d3  test    eax, eax
0x1800fb3d5  js      loc_1800FBF68
0x1800fb3db  mov     rdx, [rbp+110h+var_190]
0x1800fb3df  lea     rax, [rbp+110h+var_188]
0x1800fb3e3  mov     ecx, [rbp+110h+var_178]
0x1800fb3e6  lea     r9, [rsp+210h+var_198]
0x1800fb3eb  lea     r8, [rsp+210h+var_1C0]
0x1800fb3f0  mov     [rsp+210h+var_1F0], rax
0x1800fb3f5  call    sub_18014AAA4
0x1800fb3fa  mov     rcx, [rbp+110h+pBuffer]
0x1800fb3fe  mov     edi, eax
0x1800fb400  mov     rax, [rcx]
0x1800fb403  mov     rax, [rax+20h]
0x1800fb407  call    j__guard_dispatch_icall
0x1800fb40c  cmp     edi, 0C00D6590h
0x1800fb412  jnz     short loc_1800FB440
0x1800fb414  cmp     [rbp+110h+var_178], ebx
0x1800fb417  jnz     short loc_1800FB41D
0x1800fb419  mov     [rsi+20h], r13
0x1800fb41d  mov     r12d, 10000h
0x1800fb423  mov     [rsp+210h+var_1C8], r12
0x1800fb428  cmp     [rbp+110h+pBuffer], rbx
0x1800fb42c  jz      short loc_1800FB439
0x1800fb42e  xor     edx, edx
0x1800fb430  lea     rcx, [rbp+110h+pBuffer]
0x1800fb434  call    sub_1800F73E8
0x1800fb439  mov     edi, ebx
0x1800fb43b  jmp     loc_1800FB33C
0x1800fb440  test    edi, edi
0x1800fb442  js      loc_1800FBF11
0x1800fb448  mov     cl, cs:byte_180685211
0x1800fb44e  mov     r12d, [rsp+210h+var_1C0]
0x1800fb453  mov     r14, [rsp+210h+var_198]
0x1800fb458  cmp     cl, 10h
0x1800fb45b  jb      short loc_1800FB498
0x1800fb45d  mov     [rsp+210h+var_1D8], r14
0x1800fb462  mov     ecx, r12d
0x1800fb465  shr     ecx, 8
0x1800fb468  mov     eax, r12d
0x1800fb46b  mov     [rsp+210h+var_1E0], r12b
0x1800fb470  mov     r9d, r12d
0x1800fb473  mov     [rsp+210h+var_1E8], cl
0x1800fb477  mov     rcx, cs:RequestContext
0x1800fb47e  shr     eax, 10h
0x1800fb481  shr     r9d, 18h
0x1800fb485  mov     byte ptr [rsp+210h+var_1F0], al
0x1800fb489  mov     rcx, [rcx+38h]
0x1800fb48d  call    sub_1801059DC
0x1800fb492  mov     cl, cs:byte_180685211
0x1800fb498  mov     edx, [rbp+110h+var_188]
0x1800fb49b  test    r14, r14
0x1800fb49e  jnz     short loc_1800FB51A
0x1800fb4a0  mov     r14, [rsi+20h]
0x1800fb4a4  sub     r14, r13
0x1800fb4a7  cmp     r14, rdx
0x1800fb4aa  jnb     loc_1800FB531
0x1800fb4b0  mov     rcx, cs:qword_180685260
0x1800fb4b7  mov     r14d, 0C00D36BEh
0x1800fb4bd  mov     edi, r14d
0x1800fb4c0  test    rcx, rcx
0x1800fb4c3  jnz     short loc_1800FB4D3
0x1800fb4c5  lea     rcx, qword_180684620
0x1800fb4cc  mov     cs:qword_180685260, rcx
0x1800fb4d3  cmp     [rcx+8], bl
0x1800fb4d6  jz      short loc_1800FB4FE
0x1800fb4d8  call    sub_18005AE04
0x1800fb4dd  cmp     [rax+7CCh], r14d
0x1800fb4e4  jz      short loc_1800FB4FE
0x1800fb4e6  mov     r9d, r14d
0x1800fb4e9  lea     rdx, aCheifstreamrea_20; "CHEIFStreamReader::ParseStream"
0x1800fb4f0  mov     r8d, 0DFh
0x1800fb4f6  mov     rcx, rax
0x1800fb4f9  call    sub_180207168
0x1800fb4fe  cmp     cs:byte_180685210, r15b
0x1800fb505  jb      loc_1800FBEE5
0x1800fb50b  mov     edx, 14h
0x1800fb510  mov     dword ptr [rsp+210h+var_1F0], r14d
0x1800fb515  jmp     loc_1800FB30C
0x1800fb51a  lea     r9, [r14+r13]
0x1800fb51e  cmp     r9, r13
0x1800fb521  jb      loc_1800FBE02
0x1800fb527  cmp     r9, [rsi+20h]
0x1800fb52b  ja      loc_1800FBE06
0x1800fb531  mov     eax, [rbp+110h+var_178]
0x1800fb534  cmp     rax, r14
0x1800fb537  jnb     short loc_1800FB550
0x1800fb539  cmp     r12d, 6D646174h
0x1800fb540  jz      short loc_1800FB54B
0x1800fb542  cmp     r12d, 66726565h
0x1800fb549  jnz     short loc_1800FB555
0x1800fb54b  cmp     [rbp+110h+var_178], edx
0x1800fb54e  jb      short loc_1800FB555
0x1800fb550  mov     al, r15b
0x1800fb553  jmp     short loc_1800FB557
0x1800fb555  mov     al, bl
0x1800fb557  cmp     r12d, 66696478h
0x1800fb55e  jz      loc_1800FB8FB
0x1800fb564  cmp     r12d, 66726565h
0x1800fb56b  jz      loc_1800FB8FB
0x1800fb571  cmp     r12d, 6D646174h
0x1800fb578  jz      loc_1800FB851
0x1800fb57e  cmp     r12d, 6D657461h
0x1800fb585  jz      loc_1800FB610
0x1800fb58b  cmp     r12d, 6D6F6F76h
0x1800fb592  jz      loc_1800FB6DB
0x1800fb598  mov     r9, r14
0x1800fb59b  mov     r8, r13
0x1800fb59e  mov     edx, 6
0x1800fb5a3  mov     rcx, rsi
0x1800fb5a6  call    sub_1800F71B8
0x1800fb5ab  mov     edi, eax
0x1800fb5ad  test    eax, eax
0x1800fb5af  jns     loc_1800FB920
0x1800fb5b5  mov     rcx, cs:qword_180685260
0x1800fb5bc  test    rcx, rcx
0x1800fb5bf  jnz     short loc_1800FB5CF
0x1800fb5c1  lea     rcx, qword_180684620
0x1800fb5c8  mov     cs:qword_180685260, rcx
0x1800fb5cf  cmp     [rcx+8], bl
0x1800fb5d2  jz      short loc_1800FB5F9
0x1800fb5d4  call    sub_18005AE04
0x1800fb5d9  cmp     [rax+7CCh], edi
0x1800fb5df  jz      short loc_1800FB5F9
0x1800fb5e1  mov     r9d, edi
0x1800fb5e4  lea     rdx, aCheifstreamrea_20; "CHEIFStreamReader::ParseStream"
0x1800fb5eb  mov     r8d, 17Ah
0x1800fb5f1  mov     rcx, rax
0x1800fb5f4  call    sub_180207168
0x1800fb5f9  cmp     cs:byte_180685210, r15b
0x1800fb600  jb      loc_1800FBEE5
0x1800fb606  mov     edx, 24h ; '$'
0x1800fb60b  jmp     loc_1800FB308
0x1800fb610  cmp     [rbp+110h+var_170], rbx
0x1800fb614  jnz     loc_1800FB58B
0x1800fb61a  mov     [rsi+28h], r14
0x1800fb61e  test    al, al
0x1800fb620  jz      loc_1800FB7AA
0x1800fb626  mov     r8, [rsi+40h]
0x1800fb62a  lea     rdx, [rbp+110h+var_170]
0x1800fb62e  mov     rcx, [rbp+110h+pBuffer]
0x1800fb632  call    sub_18018B2A0
0x1800fb637  mov     edi, eax
0x1800fb639  test    eax, eax
0x1800fb63b  js      loc_1800FBA79
0x1800fb641  mov     rdx, [rbp+110h+var_168]
0x1800fb645  test    rdx, rdx
0x1800fb648  jz      short loc_1800FB664
0x1800fb64a  mov     rcx, [rbp+110h+var_170]
0x1800fb64e  mov     rax, [rcx]
0x1800fb651  mov     rax, [rax+18h]
0x1800fb655  call    j__guard_dispatch_icall
0x1800fb65a  mov     edi, eax
0x1800fb65c  test    eax, eax
0x1800fb65e  js      loc_1800FBA1E
0x1800fb664  mov     r9, [rsi+28h]
0x1800fb668  mov     r8, r13
0x1800fb66b  mov     edx, r15d
0x1800fb66e  mov     rcx, rsi
0x1800fb671  call    sub_1800F71B8
0x1800fb676  mov     edi, eax
0x1800fb678  test    eax, eax
0x1800fb67a  jns     loc_1800FB920
0x1800fb680  mov     rcx, cs:qword_180685260
0x1800fb687  test    rcx, rcx
0x1800fb68a  jnz     short loc_1800FB69A
0x1800fb68c  lea     rcx, qword_180684620
0x1800fb693  mov     cs:qword_180685260, rcx
0x1800fb69a  cmp     [rcx+8], bl
0x1800fb69d  jz      short loc_1800FB6C4
0x1800fb69f  call    sub_18005AE04
0x1800fb6a4  cmp     [rax+7CCh], edi
0x1800fb6aa  jz      short loc_1800FB6C4
0x1800fb6ac  mov     r9d, edi
0x1800fb6af  lea     rdx, aCheifstreamrea_20; "CHEIFStreamReader::ParseStream"
0x1800fb6b6  mov     r8d, 151h
0x1800fb6bc  mov     rcx, rax
0x1800fb6bf  call    sub_180207168
0x1800fb6c4  cmp     cs:byte_180685210, r15b
0x1800fb6cb  jb      loc_1800FBEE5
0x1800fb6d1  mov     edx, 20h ; ' '
0x1800fb6d6  jmp     loc_1800FB308
0x1800fb6db  cmp     [rbp+110h+var_168], rbx
0x1800fb6df  jnz     loc_1800FB598
  ... truncated ...
```
