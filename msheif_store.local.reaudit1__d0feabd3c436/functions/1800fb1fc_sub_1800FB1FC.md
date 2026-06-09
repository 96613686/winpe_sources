# sub_1800FB1FC

- ea: `0x1800fb1fc`
- end: `0x1800fc00e`
- name: `sub_1800FB1FC`
- size: `3602`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
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
  HRESULT v6; // edi
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r12
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  char v22; // cl
  unsigned int v23; // r12d
  unsigned __int64 v24; // r14
  __int64 v25; // rdx
  __int64 *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rdx
  unsigned __int64 v29; // r9
  bool v30; // al
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 *v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 *v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // r9
  __int64 *v53; // rcx
  __int64 v54; // rax
  unsigned __int64 v55; // r9
  __int64 *v56; // rcx
  __int64 v57; // rax
  int v58; // r12d
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // r9
  __int64 *v65; // rcx
  __int64 v66; // rax
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // r9
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 v72; // r9
  __int64 *v73; // rcx
  __int64 v74; // rax
  __int64 *v75; // rcx
  __int64 v76; // rax
  __int64 v77; // rdx
  __int64 v78; // r8
  __int64 v79; // r9
  int v80; // r13d
  unsigned int v81; // r12d
  unsigned int v82; // r14d
  unsigned __int64 v83; // rsi
  int v84; // eax
  const char *v85; // r9
  __int64 *v86; // rcx
  __int64 v87; // rax
  __int64 *v88; // rcx
  __int64 v89; // rax
  __int64 *v90; // rcx
  __int64 v91; // rax
  __int64 *v92; // rcx
  __int64 v93; // rax
  __int64 *v94; // rcx
  __int64 v95; // rax
  __int64 *v96; // rcx
  __int64 v97; // rax
  __int64 *v98; // rcx
  __int64 v99; // rax
  __int64 v100; // rax
  __int64 v101; // rax
  __int64 *v103; // rcx
  __int64 v104; // rax
  __int64 *v105; // rcx
  __int64 v106; // rax
  char v107; // [rsp+20h] [rbp-E0h]
  char v108; // [rsp+20h] [rbp-E0h]
  char v109[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v110; // [rsp+48h] [rbp-B8h]
  unsigned int v111; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v112; // [rsp+58h] [rbp-A8h]
  __int64 v113; // [rsp+60h] [rbp-A0h]
  _QWORD *v114; // [rsp+68h] [rbp-98h]
  _QWORD *v115; // [rsp+70h] [rbp-90h]
  unsigned __int64 v116; // [rsp+78h] [rbp-88h] BYREF
  __int64 v117; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v118; // [rsp+88h] [rbp-78h] BYREF
  IMFMediaBuffer *pBuffer; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v120; // [rsp+98h] [rbp-68h] BYREF
  __int64 v121; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v122; // [rsp+A8h] [rbp-58h] BYREF
  IMFMediaBuffer *ppBuffer[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v124[272]; // [rsp+C0h] [rbp-40h] BYREF

  v115 = a3;
  v114 = a2;
  v3 = a1;
  v113 = a1;
  v4 = 0;
  pBuffer = 0;
  v121 = 0;
  v122 = 0;
  v112 = 0;
  if ( !a2 || !a3 )
  {
    sub_1800F62FC(&v122);
    sub_1800F62FC(&v121);
    sub_1800F62FC(&pBuffer);
    return 2147500035LL;
  }
  *a2 = 0;
  *a3 = 0;
  sub_1800F82E4();
  *(_QWORD *)(v3 + 40) = 0;
  *(_DWORD *)(v3 + 48) = 0;
  sub_180059AB4(v109, "CHEIFStreamReader::ParseStream", 157);
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(v3 + 56) + 40LL))(
         *(_QWORD *)(v3 + 56),
         0,
         0,
         0);
  if ( v6 < 0 )
  {
    v9 = (__int64 *)qword_180685260;
    if ( !qword_180685260 )
    {
      v9 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( *((_BYTE *)v9 + 8) )
    {
      v10 = sub_18005AE04(v9, v5, v7, v8);
      if ( *(_DWORD *)(v10 + 1996) != v6 )
        sub_180207168(v10, "CHEIFStreamReader::ParseStream", 157, (unsigned int)v6);
    }
    if ( byte_180685210 )
    {
      v11 = 16;
      goto LABEL_11;
    }
    goto LABEL_215;
  }
  LODWORD(v12) = 0x10000;
  v110 = 0x10000;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        if ( v4 + (unsigned int)v12 > *(_QWORD *)(v3 + 32) )
        {
          LODWORD(v12) = *(_DWORD *)(v3 + 32) - v4;
          v110 = (unsigned int)v12;
        }
        if ( !(_DWORD)v12 || !pBuffer && v4 + (unsigned int)v12 <= v112 )
          goto LABEL_210;
        v112 = v4 + (unsigned int)v12;
        v117 = 0;
        v120 = 0;
        v111 = 0;
        v118 = 0;
        v116 = 0;
        if ( !pBuffer )
        {
          v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD, IMFMediaBuffer **))(*(_QWORD *)(v3 + 24)
                                                                                               + 48LL))(
                 v3 + 24,
                 v4,
                 (unsigned int)v12,
                 &pBuffer);
          if ( v6 < 0 )
          {
            v73 = (__int64 *)qword_180685260;
            if ( !qword_180685260 )
            {
              v73 = &qword_180684620;
              qword_180685260 = (__int64)&qword_180684620;
            }
            if ( *((_BYTE *)v73 + 8) )
            {
              v74 = sub_18005AE04(v73, v13, v14, v15);
              if ( *(_DWORD *)(v74 + 1996) != v6 )
                sub_180207168(v74, "CHEIFStreamReader::ParseStream", 190, (unsigned int)v6);
            }
            if ( byte_180685210 )
            {
              v11 = 17;
              goto LABEL_11;
            }
            goto LABEL_215;
          }
        }
        v6 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64 *, _QWORD, unsigned int *))pBuffer->lpVtbl->Lock)(
               pBuffer,
               &v117,
               0,
               &v120);
        if ( v6 < 0 )
        {
          v105 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v105 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( *((_BYTE *)v105 + 8) )
          {
            v106 = sub_18005AE04(v105, v16, v17, v18);
            if ( *(_DWORD *)(v106 + 1996) != v6 )
              sub_180207168(v106, "CHEIFStreamReader::ParseStream", 193, (unsigned int)v6);
          }
          if ( !byte_180685210 )
            goto LABEL_215;
          v11 = 18;
LABEL_11:
          sub_180105A84(*((_QWORD *)RequestContext + 2), v11, &stru_1805D9498, v3, v6);
          goto LABEL_215;
        }
        v6 = sub_18014AAA4(v120, v117, (unsigned int)&v111, (unsigned int)&v116, (__int64)&v118);
        ((void (__fastcall *)(IMFMediaBuffer *))pBuffer->lpVtbl->Unlock)(pBuffer);
        if ( v6 != -1072863856 )
          break;
        if ( !v120 )
          *(_QWORD *)(v3 + 32) = v4;
        LODWORD(v12) = 0x10000;
        v110 = 0x10000;
        if ( pBuffer )
          sub_1800F73E8(&pBuffer, 0);
        v6 = 0;
      }
      if ( v6 < 0 )
      {
        v103 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v103 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v103 + 8) )
        {
          v104 = sub_18005AE04(v103, v19, v20, v21);
          if ( *(_DWORD *)(v104 + 1996) != v6 )
            sub_180207168(v104, "CHEIFStreamReader::ParseStream", 425, (unsigned int)v6);
        }
        if ( !byte_180685210 )
          goto LABEL_215;
        v11 = 40;
        goto LABEL_11;
      }
      v22 = byte_180685211;
      v23 = v111;
      v24 = v116;
      if ( (unsigned __int8)byte_180685211 >= 0x10u )
      {
        v107 = BYTE2(v111);
        sub_1801059DC(*((_QWORD *)RequestContext + 7), v19, v20, HIBYTE(v111));
        v22 = byte_180685211;
      }
      v25 = v118;
      if ( v24 )
      {
        v29 = v24 + v4;
        if ( v24 + v4 < v4 )
        {
          v29 = -1;
LABEL_198:
          if ( (unsigned __int8)v22 >= 4u )
          {
            sub_180105968(*((_QWORD *)RequestContext + 7), v118, v20, v29, *(_QWORD *)(v3 + 32));
            v22 = byte_180685211;
          }
          if ( v121 )
          {
            if ( (unsigned __int8)v22 >= 4u )
              sub_18007980C(*((_QWORD *)RequestContext + 7), 22, &stru_1805D9498);
LABEL_210:
            if ( !v121 )
              *(_QWORD *)(v3 + 40) = 0;
            if ( !v122 )
              *(_DWORD *)(v3 + 48) = 0;
            v100 = v121;
            v121 = 0;
            *v114 = v100;
            v101 = v122;
            v122 = 0;
            *v115 = v101;
            goto LABEL_215;
          }
          v98 = (__int64 *)qword_180685260;
          v6 = -1072875842;
          if ( !qword_180685260 )
          {
            v98 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( *((_BYTE *)v98 + 8) )
          {
            v99 = sub_18005AE04(v98, v25, v20, v29);
            if ( *(_DWORD *)(v99 + 1996) != -1072875842 )
              sub_180207168(v99, "CHEIFStreamReader::ParseStream", 242, 3222091454LL);
          }
          if ( !byte_180685210 )
            goto LABEL_215;
          v28 = 23;
LABEL_40:
          sub_180105A84(*((_QWORD *)RequestContext + 2), v28, &stru_1805D9498, v3, -1072875842);
          goto LABEL_215;
        }
        if ( v29 > *(_QWORD *)(v3 + 32) )
          goto LABEL_198;
      }
      else
      {
        v24 = *(_QWORD *)(v3 + 32) - v4;
        if ( v24 < v118 )
        {
          v26 = (__int64 *)qword_180685260;
          v6 = -1072875842;
          if ( !qword_180685260 )
          {
            v26 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( *((_BYTE *)v26 + 8) )
          {
            v27 = sub_18005AE04(v26, v118, v20, v21);
            if ( *(_DWORD *)(v27 + 1996) != -1072875842 )
              sub_180207168(v27, "CHEIFStreamReader::ParseStream", 223, 3222091454LL);
          }
          if ( !byte_180685210 )
            goto LABEL_215;
          v28 = 20;
          goto LABEL_40;
        }
      }
      v30 = v120 >= v24 || (v23 == 1835295092 || v23 == 1718773093) && v120 >= v118;
      if ( v23 != 1718183032 && v23 != 1718773093 )
        break;
      if ( !v30 )
      {
LABEL_118:
        v12 = 16;
        goto LABEL_119;
      }
      v6 = sub_1800F71B8(v3, 5, v4, v24, v107);
      if ( v6 < 0 )
      {
        v96 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v96 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v96 + 8) )
        {
          v97 = sub_18005AE04(v96, v67, v68, v69);
          if ( *(_DWORD *)(v97 + 1996) != v6 )
            sub_180207168(v97, "CHEIFStreamReader::ParseStream", 278, (unsigned int)v6);
        }
        if ( !byte_180685210 )
          goto LABEL_215;
        v11 = 26;
        goto LABEL_11;
      }
LABEL_111:
      if ( !v24 )
        goto LABEL_210;
      if ( v24 + v4 >= v120 + v4 )
      {
        v4 += v24;
        v12 = 0x10000;
LABEL_119:
        v110 = v12;
        goto LABEL_120;
      }
      ppBuffer[0] = 0;
      v6 = MFCreateMediaBufferWrapper(pBuffer, v24, v120 - v24, ppBuffer);
      if ( v6 < 0 )
      {
        v94 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v94 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v94 + 8) )
        {
          v95 = sub_18005AE04(v94, v70, v71, v72);
          if ( *(_DWORD *)(v95 + 1996) != v6 )
            sub_180207168(v95, "CHEIFStreamReader::ParseStream", 406, (unsigned int)v6);
        }
        if ( byte_180685210 )
          sub_180105A84(*((_QWORD *)RequestContext + 2), 39, &stru_1805D9498, v3, v6);
        sub_1800F62FC(ppBuffer);
        goto LABEL_215;
      }
      if ( pBuffer != ppBuffer[0] )
        sub_1800F73E8(&pBuffer, ppBuffer[0]);
      v4 += v24;
      LODWORD(v12) = v110 - v24;
      v110 = (unsigned int)(v110 - v24);
      sub_1800F62FC(ppBuffer);
    }
    if ( v23 == 1835295092 )
    {
      if ( !v30 )
        goto LABEL_118;
      v58 = v24 - v118;
      v6 = sub_1800F71B8(v3, 3, v118, (unsigned int)v24 - v118, v107);
      if ( v6 < 0 )
      {
        v92 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v92 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v92 + 8) )
        {
          v93 = sub_18005AE04(v92, v59, v60, v61);
          if ( *(_DWORD *)(v93 + 1996) != v6 )
            sub_180207168(v93, "CHEIFStreamReader::ParseStream", 259, (unsigned int)v6);
        }
        if ( !byte_180685210 )
          goto LABEL_215;
        v11 = 24;
        goto LABEL_11;
      }
      v6 = sub_1800F71B8(v3, 4, (unsigned int)v4 + v118, v58, v108);
      if ( v6 < 0 )
      {
        v65 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v65 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v65 + 8) )
        {
          v66 = sub_18005AE04(v65, v62, v63, v64);
          if ( *(_DWORD *)(v66 + 1996) != v6 )
            sub_180207168(v66, "CHEIFStreamReader::ParseStream", 260, (unsigned int)v6);
        }
        if ( byte_180685210 )
        {
          v11 = 25;
          goto LABEL_11;
        }
        goto LABEL_215;
      }
      goto LABEL_111;
    }
    if ( v23 == 1835365473 && !v121 )
      break;
    if ( v23 != 1836019574 || v122 )
    {
      v6 = sub_1800F71B8(v3, 6, v4, v24, v107);
      if ( v6 < 0 )
      {
        v34 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v34 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v34 + 8) )
        {
          v35 = sub_18005AE04(v34, v31, v32, v33);
          if ( *(_DWORD *)(v35 + 1996) != v6 )
            sub_180207168(v35, "CHEIFStreamReader::ParseStream", 378, (unsigned int)v6);
        }
        if ( byte_180685210 )
        {
          v11 = 36;
          goto LABEL_11;
        }
        goto LABEL_215;
      }
      goto LABEL_111;
    }
    *(_DWORD *)(v3 + 48) = v24;
    if ( v30 )
    {
      v6 = sub_180157A84(pBuffer, &v122, 4);
      if ( v6 < 0 )
      {
        v90 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v90 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v90 + 8) )
        {
          v91 = sub_18005AE04(v90, v44, v45, v46);
          if ( *(_DWORD *)(v91 + 1996) != v6 )
            sub_180207168(v91, "CHEIFStreamReader::ParseStream", 359, (unsigned int)v6);
        }
        if ( !byte_180685210 )
          goto LABEL_215;
        v11 = 33;
        goto LABEL_11;
      }
      if ( v121 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v121 + 24LL))(v121, v122);
        if ( v6 < 0 )
        {
          v88 = (__int64 *)qword_180685260;
          if ( !qword_180685260 )
          {
            v88 = &qword_180684620;
            qword_180685260 = (__int64)&qword_180684620;
          }
          if ( *((_BYTE *)v88 + 8) )
          {
            v89 = sub_18005AE04(v88, v47, v48, v49);
            if ( *(_DWORD *)(v89 + 1996) != v6 )
              sub_180207168(v89, "CHEIFStreamReader::ParseStream", 363, (unsigned int)v6);
          }
          if ( !byte_180685210 )
            goto LABEL_215;
          v11 = 34;
          goto LABEL_11;
        }
      }
      v6 = sub_1800F71B8(v3, 2, v4, *(_DWORD *)(v3 + 48), v107);
      if ( v6 < 0 )
      {
        v53 = (__int64 *)qword_180685260;
        if ( !qword_180685260 )
        {
          v53 = &qword_180684620;
          qword_180685260 = (__int64)&qword_180684620;
        }
        if ( *((_BYTE *)v53 + 8) )
        {
          v54 = sub_18005AE04(v53, v50, v51, v52);
          if ( *(_DWORD *)(v54 + 1996) != v6 )
            sub_180207168(v54, "CHEIFStreamReader::ParseStream", 366, (unsigned int)v6);
        }
        if ( byte_180685210 )
        {
          v11 = 35;
          goto LABEL_11;
        }
        goto LABEL_215;
      }
      goto LABEL_111;
    }
LABEL_88:
    v55 = v24;
    if ( !v24 )
      goto LABEL_111;
    v110 = v24;
    LODWORD(v12) = v24;
    if ( v24 > 0xC800000 )
    {
      if ( (unsigned __int8)v22 >= 4u )
        sub_180105908(*((_QWORD *)RequestContext + 7), 37, &stru_1805D9498, v24);
      v56 = (__int64 *)qword_180685260;
      v6 = -1072875842;
      if ( !qword_180685260 )
      {
        v56 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v56 + 8) )
      {
        v57 = sub_18005AE04(v56, v25, v20, v55);
        if ( *(_DWORD *)(v57 + 1996) != -1072875842 )
          sub_180207168(v57, "CHEIFStreamReader::ParseStream", 391, 3222091454LL);
      }
      if ( !byte_180685210 )
        goto LABEL_215;
      v28 = 38;
      goto LABEL_40;
    }
LABEL_120:
    if ( pBuffer )
      sub_1800F73E8(&pBuffer, 0);
  }
  *(_QWORD *)(v3 + 40) = v24;
  if ( !v30 )
    goto LABEL_88;
  v6 = sub_18018B2A0(pBuffer, &v121, *(_QWORD *)(v3 + 64));
  if ( v6 < 0 )
  {
    v116 = 0;
    v118 = 0;
    if ( ((int (__fastcall *)(IMFMediaBuffer *, unsigned __int64 *, _QWORD, unsigned int *))pBuffer->lpVtbl->Lock)(
           pBuffer,
           &v116,
           0,
           &v118) >= 0 )
    {
      v80 = 0;
      if ( (unsigned __int8)byte_180685211 >= 0x10u )
        sub_180079880(*((_QWORD *)RequestContext + 7), 27, &stru_1805D9498, (unsigned int)v6, v118);
      v81 = 0;
      if ( v118 )
      {
        do
        {
          if ( v80 < 0 )
            break;
          v82 = 0;
          v83 = v116 + v81;
          do
          {
            if ( v82 + v81 >= v118 )
              break;
            if ( v80 < 0 )
              break;
            v84 = sub_18005BAB0(&v124[2 * v82], 257 - 2 * v82, "%02x", *(unsigned __int8 *)(v82 + v83));
            ++v82;
            v80 = v84;
          }
          while ( 2 * v82 < 0x100 );
          if ( (unsigned __int8)byte_180685211 >= 0x10u )
          {
            v85 = v124;
            if ( v80 < 0 )
              v85 = "failed!";
            sub_180079B90(*((_QWORD *)RequestContext + 7), 28, &stru_1805D9498, v85);
          }
          v81 += v82;
        }
        while ( v81 < v118 );
        v3 = v113;
      }
      if ( (unsigned __int8)byte_180685211 >= 0x10u )
        sub_18007980C(*((_QWORD *)RequestContext + 7), 29, &stru_1805D9498);
      ((void (__fastcall *)(IMFMediaBuffer *))pBuffer->lpVtbl->Unlock)(pBuffer);
    }
    v86 = (__int64 *)qword_180685260;
    if ( !qword_180685260 )
    {
      v86 = &qword_180684620;
      qword_180685260 = (__int64)&qword_180684620;
    }
    if ( *((_BYTE *)v86 + 8) )
    {
      v87 = sub_18005AE04(v86, v77, v78, v79);
      if ( *(_DWORD *)(v87 + 1996) != v6 )
        sub_180207168(v87, "CHEIFStreamReader::ParseStream", 330, (unsigned int)v6);
    }
    if ( !byte_180685210 )
      goto LABEL_215;
    v11 = 30;
    goto LABEL_11;
  }
  if ( !v122 || (v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v121 + 24LL))(v121), v6 >= 0) )
  {
    v6 = sub_1800F71B8(v3, 1, v4, *(_QWORD *)(v3 + 40), v107);
    if ( v6 < 0 )
    {
      v42 = (__int64 *)qword_180685260;
      if ( !qword_180685260 )
      {
        v42 = &qword_180684620;
        qword_180685260 = (__int64)&qword_180684620;
      }
      if ( *((_BYTE *)v42 + 8) )
      {
        v43 = sub_18005AE04(v42, v39, v40, v41);
        if ( *(_DWORD *)(v43 + 1996) != v6 )
          sub_180207168(v43, "CHEIFStreamReader::ParseStream", 337, (unsigned int)v6);
      }
      if ( byte_180685210 )
      {
        v11 = 32;
        goto LABEL_11;
      }
      goto LABEL_215;
    }
    goto LABEL_111;
  }
  v75 = (__int64 *)qword_180685260;
  if ( !qword_180685260 )
  {
    v75 = &qword_180684620;
    qword_180685260 = (__int64)&qword_180684620;
  }
  if ( *((_BYTE *)v75 + 8) )
  {
    v76 = sub_18005AE04(v75, v36, v37, v38);
    if ( *(_DWORD *)(v76 + 1996) != v6 )
      sub_180207168(v76, "CHEIFStreamReader::ParseStream", 334, (unsigned int)v6);
  }
  if ( byte_180685210 )
  {
    v11 = 31;
    goto LABEL_11;
  }
LABEL_215:
  sub_180059EAC(v109);
  sub_1800F62FC(&v122);
  sub_1800F62FC(&v121);
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
