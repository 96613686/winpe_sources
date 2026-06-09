# WSTUnsealMessage

- ea: `0x1800332b0`
- end: `0x18003418b`
- name: `WSTUnsealMessage`
- size: `3803`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024a10`

## callees

- `0x1800210f0`
- `0x180023cb8`
- `0x180023ce0`
- `0x18002b408`
- `0x18002b744`
- `0x180032234`
- `0x1800332b0`
- `0x180034534`
- `0x180044f8c`
- `0x180044f98`
- `0x180046010`

## import_xrefs

- `cryptdll!CDLocateCheckSum` at `0x18003391b`
- `cryptdll!CDLocateCheckSum` at `0x18003391b`

## string_xrefs

- `0x1800338c9`: `onecore\ds\security\protocols\pku2u\message.cxx`

## pseudocode

```c
__int64 __fastcall WSTUnsealMessage(void *a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  _BYTE *v4; // rdi
  unsigned int *v5; // rcx
  _QWORD *v6; // rax
  size_t *v7; // rbx
  __int64 v8; // r12
  unsigned int v9; // r10d
  unsigned int v10; // r15d
  unsigned int v11; // r9d
  unsigned int *v12; // rdx
  int v13; // ecx
  int v14; // ebx
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int128 v17; // xmm0
  char *v18; // rdi
  unsigned int v19; // r9d
  char *v20; // r15
  char v21; // dl
  unsigned int v22; // r11d
  char v23; // dl
  __int16 v24; // r8
  unsigned __int16 v25; // si
  int v26; // ecx
  unsigned int v27; // edx
  unsigned int v28; // r12d
  unsigned int v29; // r13d
  size_t v30; // r14
  char v31; // bl
  __int16 *v32; // rcx
  size_t v33; // r12
  size_t v34; // rbx
  _QWORD *v35; // rcx
  __int64 v36; // rdx
  char *v37; // r15
  char *v38; // rax
  unsigned __int64 v39; // rcx
  int v40; // edx
  int v41; // ecx
  __int64 v42; // rdx
  int v43; // r10d
  int v44; // ecx
  int v45; // eax
  _QWORD *v46; // rcx
  __int64 v47; // rdx
  char v48; // r12
  __int64 v49; // r13
  __int64 *v50; // rdi
  int v51; // esi
  int v52; // r12d
  unsigned __int64 v53; // rdx
  unsigned __int64 v54; // rdx
  size_t v55; // rsi
  unsigned int i; // r13d
  __int64 v57; // rcx
  __int64 v58; // rdx
  int v59; // r8d
  __int64 v60; // r9
  char *v61; // r10
  int v62; // r13d
  unsigned int v63; // r11d
  unsigned int v64; // r12d
  unsigned int v65; // r13d
  char v66; // dl
  int v67; // ecx
  int v68; // r8d
  int v69; // ecx
  char *v70; // rsi
  __int64 v71; // rbx
  char v72; // cl
  int v73; // edx
  int v74; // r8d
  int v75; // ecx
  unsigned __int64 v76; // rdx
  int v77; // ecx
  int v78; // ecx
  unsigned __int64 v79; // rcx
  unsigned __int64 v80; // rcx
  char v81; // r8
  _BYTE *v82; // r9
  __int64 j; // rdx
  char v84; // cl
  char v85; // al
  _QWORD *v86; // rcx
  __int64 v87; // rdx
  int v88; // eax
  unsigned __int64 v89; // rcx
  char v90; // r8
  _BYTE *v91; // r9
  __int64 k; // rdx
  char v93; // cl
  char v94; // al
  __int64 *v95; // rdi
  __int64 v96; // r9
  unsigned int v97; // ecx
  char v99; // [rsp+50h] [rbp-B0h]
  unsigned int v100; // [rsp+54h] [rbp-ACh]
  unsigned int v101; // [rsp+54h] [rbp-ACh]
  unsigned int v102; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v103; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v104; // [rsp+68h] [rbp-98h] BYREF
  __int128 v105; // [rsp+70h] [rbp-90h] BYREF
  int v106; // [rsp+80h] [rbp-80h] BYREF
  __int64 v107; // [rsp+88h] [rbp-78h] BYREF
  char *v108; // [rsp+90h] [rbp-70h]
  __int64 *v109; // [rsp+98h] [rbp-68h] BYREF
  __int64 v110; // [rsp+A0h] [rbp-60h] BYREF
  void *v111; // [rsp+A8h] [rbp-58h]
  __int128 *v112; // [rsp+B0h] [rbp-50h]
  __int64 v113; // [rsp+B8h] [rbp-48h] BYREF
  size_t Size[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v115; // [rsp+D0h] [rbp-30h]
  _QWORD *v116; // [rsp+D8h] [rbp-28h]
  unsigned int *v117; // [rsp+E0h] [rbp-20h]
  _DWORD *v118; // [rsp+E8h] [rbp-18h]
  __int128 v119; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE Src[96]; // [rsp+100h] [rbp+0h] BYREF
  __int16 v121; // [rsp+160h] [rbp+60h] BYREF
  __int64 v122; // [rsp+162h] [rbp+62h] BYREF
  int v123; // [rsp+16Ah] [rbp+6Ah]
  __int16 v124; // [rsp+16Eh] [rbp+6Eh]
  _OWORD v125[7]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v126[64]; // [rsp+1E0h] [rbp+E0h] BYREF

  v111 = a1;
  v118 = a4;
  v4 = a1;
  LODWORD(v108) = a3;
  v5 = (unsigned int *)(a2 + 4);
  v112 = (__int128 *)a2;
  v117 = (unsigned int *)(a2 + 4);
  v6 = (_QWORD *)(a2 + 8);
  v104 = 0;
  v110 = 0;
  v7 = 0;
  v8 = 0;
  v115 = 0;
  *(_OWORD *)Size = 0;
  v103 = 0;
  v9 = 0;
  v105 = 0;
  v107 = 0;
  v10 = 0;
  v119 = 0;
  v102 = 0;
  v11 = 0;
  v106 = 0;
  v113 = 0;
  v109 = 0;
  v116 = (_QWORD *)(a2 + 8);
  while ( 1 )
  {
    if ( v11 >= *v5 )
    {
      if ( !v8 )
      {
        if ( !v7 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              50,
              (unsigned int)&WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids,
              (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\message.cxx",
              27);
          goto LABEL_22;
        }
LABEL_76:
        LOBYTE(a3) = 1;
        v45 = WSTVerifySignatureToken(
                (_DWORD)v4,
                (_DWORD)v7,
                a3,
                (_DWORD)v108,
                (__int64)&v109,
                (__int64)&v106,
                (__int64)&v102,
                (__int64)&v110,
                (__int64)&v113);
        v14 = v45;
        if ( v45 < 0 )
        {
          v46 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_217;
          v47 = 51;
          goto LABEL_80;
        }
        if ( v106 == -2147483647 )
        {
          v48 = 0;
          v99 = 0;
          v10 = 0;
        }
        else
        {
          v48 = 1;
          v99 = 1;
          if ( (v4[84] & 0x10) == 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids);
LABEL_100:
            v14 = -2146893054;
            goto LABEL_217;
          }
        }
        v49 = v110;
        v101 = *(_DWORD *)(v110 + 4);
        if ( v101 <= 0x20 )
        {
          v45 = CDLocateCheckSum(v102, &v104);
          v14 = v45;
          if ( v45 < 0 )
          {
            v46 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_217;
            v47 = 53;
LABEL_80:
            WPP_SF_d(v46[2], v47, &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids, (unsigned int)v45);
            goto LABEL_217;
          }
          v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(v104 + 48))(
                  *((_QWORD *)v4 + 7),
                  *((unsigned int *)v4 + 12),
                  (*((_DWORD *)v4 + 20) & 4) != 0 ? 24 : 22,
                  &v103);
          if ( v14 < 0 )
            goto LABEL_217;
          v50 = v109;
          if ( v48 )
          {
            if ( (*(_BYTE *)v109 & 2) != 0 )
              v51 = *((unsigned __int8 *)v109 + 3) + (*((unsigned __int8 *)v109 + 2) << 8);
            else
              v51 = 0;
            v52 = (*(_BYTE *)v109 & 2) != 0 ? 0x10 : 0;
            v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(v49 + 40))(
                    *((_QWORD *)v111 + 7),
                    *((unsigned int *)v111 + 12),
                    (*((_DWORD *)v111 + 20) & 4) != 0 ? 24 : 22,
                    &v107);
            if ( v14 < 0 )
              goto LABEL_217;
            v10 += v51 + v52;
            v53 = (*(_BYTE *)v50 & 2) != 0
                ? *((unsigned __int8 *)v50 + 3) + ((unsigned __int64)*((unsigned __int8 *)v50 + 2) << 8)
                : 0LL;
            v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(v49 + 104))(
                    v107,
                    v10,
                    16,
                    (_BYTE *)v50 + v53 + (-(__int64)((*(_BYTE *)v50 & 2) != 0) & 0x10) + 26);
            if ( v14 < 0 )
              goto LABEL_217;
            v54 = (*(_BYTE *)v50 & 2) != 0
                ? *((unsigned __int8 *)v50 + 3) + ((unsigned __int64)*((unsigned __int8 *)v50 + 2) << 8)
                : 0LL;
            v14 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(v104 + 24))(
                    v103,
                    16,
                    (_BYTE *)v50 + v54 + (-(__int64)((*(_BYTE *)v50 & 2) != 0) & 0x10) + 26);
            if ( v14 < 0 )
              goto LABEL_217;
            v48 = v99;
          }
          v55 = 0;
          v111 = 0;
          for ( i = 0; ; ++i )
          {
            v102 = i;
            if ( i >= *((_DWORD *)v112 + 1) )
              break;
            v57 = *((_QWORD *)v112 + 1);
            v58 = 16LL * i;
            v113 = v58;
            v59 = *(_DWORD *)(v57 + v58 + 4);
            if ( (v59 & 0xFFFFFFF) != 2 && v59 >= 0 )
            {
              v60 = *(unsigned int *)(v57 + 16LL * i);
              if ( (_DWORD)v60 )
              {
                if ( !v48 || (v59 & 0x10000000) != 0 )
                {
                  v64 = *(_DWORD *)(v57 + 16LL * i);
                  v108 = *(char **)(v57 + v58 + 8);
                }
                else
                {
                  v61 = *(char **)(v57 + v58 + 8);
                  v62 = *(_DWORD *)(v57 + 16LL * i);
                  if ( (_DWORD)v55 )
                  {
                    v63 = v101 - v55;
                    v62 = v55 + v60 - v101;
                    v108 = &v61[v101 - (unsigned int)v55];
                  }
                  else
                  {
                    v108 = *(char **)(v57 + v58 + 8);
                    v63 = v101;
                  }
                  v64 = v62 & -v101;
                  v65 = v62 - v64;
                  v66 = *(_BYTE *)v50 & 2;
                  if ( v66 )
                    v67 = *((unsigned __int8 *)v50 + 3) + (*((unsigned __int8 *)v50 + 2) << 8);
                  else
                    v67 = 0;
                  v68 = v66 != 0 ? 0x10 : 0;
                  if ( v68 + v67 == v101 && !v65 )
                  {
                    v69 = v66 ? *((unsigned __int8 *)v50 + 3) + (*((unsigned __int8 *)v50 + 2) << 8) : 0;
                    if ( v10 == v69 + v68 + v64 )
                    {
                      v64 -= v101;
                      v65 = v101;
                    }
                  }
                  if ( (_DWORD)v55 )
                  {
                    if ( v63 > (unsigned int)v60 )
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          54,
                          &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids,
                          v60);
                      goto LABEL_100;
                    }
                    Size[0] = v63;
                    memcpy_0(&Src[v55], v61, v63);
                    v10 -= v101;
                    v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _BYTE *))(v110 + 104))(
                            v107,
                            v10,
                            v101,
                            Src);
                    if ( v14 < 0 )
                      goto LABEL_217;
                    v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(v104 + 24))(v103, v101, Src);
                    if ( v14 < 0 )
                      goto LABEL_217;
                    memcpy_0(v111, Src, v55);
                    memcpy_0(*(void **)(*((_QWORD *)v112 + 1) + v113 + 8), &Src[v55], Size[0]);
                  }
                  v10 -= v64;
                  v70 = v108;
                  v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, char *))(v110 + 104))(v107, v10, v64, v108);
                  if ( v14 < 0 )
                    goto LABEL_217;
                  v71 = v65;
                  memcpy_0(Src, &v70[v64], v65);
                  v55 = v65;
                  i = v102;
                  v111 = (void *)(*(unsigned int *)(*((_QWORD *)v112 + 1) + v113)
                                + *(_QWORD *)(*((_QWORD *)v112 + 1) + v113 + 8)
                                - v71);
                }
                v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(v104 + 24))(v103, v64, v108);
                if ( v14 < 0 )
                  goto LABEL_217;
              }
            }
            v48 = v99;
          }
          *((_WORD *)v50 + 2) = 0;
          if ( v48 )
          {
            v72 = *(_BYTE *)v50 & 2;
            if ( v72 )
              v73 = *((unsigned __int8 *)v50 + 3) + (*((unsigned __int8 *)v50 + 2) << 8);
            else
              v73 = 0;
            v74 = v72 != 0 ? 0x10 : 0;
            if ( (unsigned int)(v55 + v74 + v73) > 0x60 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                if ( v72 )
                  v75 = *((unsigned __int8 *)v50 + 3) + (*((unsigned __int8 *)v50 + 2) << 8);
                else
                  v75 = 0;
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  55,
                  &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids,
                  (unsigned int)(v74 + v75));
              }
              goto LABEL_56;
            }
            if ( v72 )
              v76 = *((unsigned __int8 *)v50 + 3) + ((unsigned __int64)*((unsigned __int8 *)v50 + 2) << 8);
            else
              v76 = 0;
            memcpy_0(&Src[(unsigned int)v55], (char *)v50 + 14, v76 + (v72 != 0 ? 0x10 : 0));
            if ( (*(_BYTE *)v50 & 2) != 0 )
              v77 = *((unsigned __int8 *)v50 + 3) + (*((unsigned __int8 *)v50 + 2) << 8);
            else
              v77 = 0;
            v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _BYTE *))(v110 + 104))(
                    v107,
                    0,
                    (unsigned int)v55 + v77 + ((*(_BYTE *)v50 & 2) != 0 ? 0x10 : 0),
                    Src);
            if ( v14 < 0 )
              goto LABEL_217;
            v78 = (*(_BYTE *)v50 & 2) != 0 ? *((unsigned __int8 *)v50 + 3) + (*((unsigned __int8 *)v50 + 2) << 8) : 0;
            v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(v104 + 24))(
                    v103,
                    (unsigned int)v55 + v78 + ((*(_BYTE *)v50 & 2) != 0 ? 0x10 : 0),
                    Src);
            if ( v14 < 0 )
              goto LABEL_217;
            memcpy_0(v111, Src, (unsigned int)v55);
            if ( (*(_BYTE *)v50 & 2) != 0 )
              v79 = *((unsigned __int8 *)v50 + 3) + ((unsigned __int64)*((unsigned __int8 *)v50 + 2) << 8);
            else
              v79 = 0;
            memcpy_0((char *)v50 + 14, &Src[(unsigned int)v55], v79 + ((*(_BYTE *)v50 & 2) != 0 ? 0x10 : 0));
            if ( (*(_BYTE *)v50 & 2) != 0 )
              v80 = *((unsigned __int8 *)v50 + 3) + ((unsigned __int64)*((unsigned __int8 *)v50 + 2) << 8);
            else
              v80 = 0;
            v81 = 0;
            v82 = (char *)v50 + v80;
            for ( j = 0; j != 16; ++j )
            {
              v84 = v82[j + 14];
              v85 = *((_BYTE *)v50 + j - 2);
              v81 |= v85 ^ v84;
            }
            if ( v81 )
            {
              v86 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v87 = 56;
LABEL_215:
                WPP_SF_(v86[2], v87, &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids);
              }
LABEL_216:
              v14 = -2146893041;
              goto LABEL_217;
            }
            v48 = v99;
            LODWORD(v55) = 0;
          }
          else
          {
            *((_WORD *)v50 + 1) = 0;
            v14 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(v104 + 24))(v103, 16, (_BYTE *)v50 - 2);
            if ( v14 < 0 )
              goto LABEL_217;
          }
          v14 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(v104 + 32))(v103, v126);
          if ( v14 < 0 )
            goto LABEL_217;
          v88 = (*(__int64 (__fastcall **)(__int64 *))(v104 + 40))(&v103);
          v103 = 0;
          v14 = v88;
          if ( v88 < 0 )
            goto LABEL_220;
          if ( v48 && (_DWORD)v55 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                57,
                &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids,
                (unsigned int)v55);
            v14 = -2146893048;
            goto LABEL_217;
          }
          if ( (*(_BYTE *)v50 & 2) != 0 )
            v89 = *((unsigned __int8 *)v50 + 3) + ((unsigned __int64)*((unsigned __int8 *)v50 + 2) << 8);
          else
            v89 = 0;
          v90 = 0;
          v91 = (char *)v50 + v89 + ((*(_BYTE *)v50 & 2) != 0 ? 0x10 : 0);
          for ( k = 0; k != 12; ++k )
          {
            v93 = v126[k];
            v94 = v91[k + 14];
            v90 |= v94 ^ v93;
          }
          v95 = v109;
          if ( !v90 )
          {
            if ( v118 )
              *v118 = v106;
            if ( !v115 )
              goto LABEL_217;
            v96 = *((unsigned __int8 *)v95 + 3) + (*((unsigned __int8 *)v95 + 2) << 8);
            if ( v101 >= (unsigned int)v96 && (unsigned int)v105 >= (unsigned int)v96 )
            {
              v97 = 0;
              LODWORD(v105) = v105 - v96;
              while ( v97 < *v117 )
              {
                if ( (*(_DWORD *)(*v116 + 16LL * v97 + 4) & 0xFFFFFFF) == 1 )
                {
                  *(_OWORD *)(*v116 + 16LL * v97) = v105;
                  goto LABEL_217;
                }
                ++v97;
              }
              goto LABEL_217;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids, v96);
            goto LABEL_22;
          }
          v86 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v87 = 58;
            goto LABEL_215;
          }
          goto LABEL_216;
        }
LABEL_56:
        v14 = -1073741637;
        goto LABEL_217;
      }
      if ( v7 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_22;
        v16 = 44;
LABEL_21:
        WPP_SF_(v15[2], v16, &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids);
LABEL_22:
        v14 = -1073741811;
LABEL_217:
        if ( v103 && v104 )
          (*(void (__fastcall **)(__int64 *))(v104 + 40))(&v103);
LABEL_220:
        if ( v107 && v110 )
          (*(void (__fastcall **)(__int64 *))(v110 + 64))(&v107);
        return (unsigned int)v14;
      }
      v105 = *(_OWORD *)v8;
      v17 = v105;
      DWORD1(v105) = 1;
      *(_OWORD *)Size = v17;
      HIDWORD(Size[0]) = 2;
      if ( (int)v105 - 2 < 0
        || (v18 = (char *)(*((_QWORD *)&v105 + 1) + 2LL),
            v109 = (__int64 *)(*((_QWORD *)&v105 + 1) + 2LL),
            (unsigned int)(v105 - 2) < 0xE)
        || (v19 = v105 - 16, (int)v105 - 16 < 0) )
      {
        LODWORD(v105) = 0;
      }
      else
      {
        LODWORD(v105) = v105 - 16;
        v20 = (char *)(*((_QWORD *)&v105 + 1) + 16LL);
        *((_QWORD *)&v105 + 1) += 16LL;
        if ( v19 )
        {
          v21 = *v18;
          v22 = *(_DWORD *)v8 - v19;
          v100 = v22;
          DWORD1(v119) = 1;
          *((_QWORD *)&v119 + 1) = &v105;
          v23 = v21 & 2;
          if ( v23 )
            v24 = (unsigned __int8)v18[3] + ((unsigned __int8)v18[2] << 8);
          else
            v24 = 0;
          v25 = v24 + (v23 != 0 ? 28 : 12);
          if ( v23 )
            v26 = (unsigned __int8)v18[3] + ((unsigned __int8)v18[2] << 8);
          else
            v26 = 0;
          if ( v9 < v26 + (v23 != 0 ? 60 : 28) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                46,
                &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids,
                v9,
                v25);
            goto LABEL_216;
          }
          a3 = (unsigned __int8)v18[4] << 8;
          v27 = ((unsigned int)a3 + (unsigned __int8)v18[5]) % (v9 - 16);
          if ( (unsigned __int16)v27 <= v25 )
          {
            a3 = v25;
            if ( (unsigned __int16)v27 < v25 )
            {
              Size[1] = (size_t)&v121;
              v18 = (char *)&v122;
              v109 = &v122;
              if ( v25 >= 0x80u || v22 > 128 - (unsigned __int64)v25 )
              {
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  goto LABEL_56;
                v36 = 47;
              }
              else
              {
                v32 = *(__int16 **)(v8 + 8);
                v33 = (unsigned __int16)v27;
                v34 = v25 - (unsigned __int64)(unsigned __int16)v27;
                v121 = *v32;
                v122 = *(_QWORD *)(v32 + 1);
                v123 = *(_DWORD *)(v32 + 5);
                v124 = v32[7];
                memcpy_0(v125, &v20[v19 - v34], v34);
                if ( (unsigned int)v25 + 16 < 0x80 )
                {
                  memcpy_0((char *)v125 + v34, v20, v33);
                  v37 = &v20[v33];
                  *((_QWORD *)&v105 + 1) = v37;
                  if ( (v122 & 2) == 0 )
                  {
LABEL_63:
                    v112 = &v119;
                    v7 = Size;
                    v18[4] = HIBYTE(v25);
                    v18[5] = v25;
                    if ( (*v18 & 2) != 0 )
                      v40 = (unsigned __int8)v18[3] + ((unsigned __int8)v18[2] << 8);
                    else
                      v40 = 0;
                    v10 = -12 - 2 * ((*v18 & 2) != 0 ? 0x10 : 0) - v40 + v105;
                    LODWORD(v105) = v10;
                    LOBYTE(a3) = *v18 & 2;
                    if ( (_BYTE)a3 )
                      v41 = (unsigned __int8)v18[3] + ((unsigned __int8)v18[2] << 8);
                    else
                      v41 = 0;
                    v42 = (_BYTE)a3 != 0 ? 44 : 12;
                    v43 = v100 + v41 + v42;
                    LODWORD(Size[0]) = v43;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                    {
                      if ( (_BYTE)a3 )
                        v44 = (unsigned __int8)v18[3] + ((unsigned __int8)v18[2] << 8);
                      else
                        v44 = 0;
                      WPP_SF_dqdqdd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        v42,
                        a3,
                        v25,
                        *((_QWORD *)&v105 + 1),
                        v10,
                        Size[1],
                        v43,
                        v44 + v42);
                      v10 = v105;
                    }
                    v4 = v111;
                    goto LABEL_76;
                  }
                  v38 = v37 + 16;
                  *(_OWORD *)((char *)v125 + v25) = *(_OWORD *)v37;
LABEL_62:
                  *((_QWORD *)&v105 + 1) = v38;
                  goto LABEL_63;
                }
                v35 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  goto LABEL_56;
                v36 = 48;
              }
              WPP_SF_(v35[2], v36, &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids);
              goto LABEL_56;
            }
            v25 = v27;
          }
          else
          {
            v28 = (unsigned __int16)v27 - v25;
            if ( (unsigned __int16)v27 != v25 && v19 > 1 )
            {
              v29 = 0;
              v30 = v19 - 1;
              do
              {
                v31 = *v20;
                memmove_0(v18 + 14, v18 + 15, v30);
                ++v29;
                v20[v30] = v31;
              }
              while ( v29 < v28 );
              v20 = (char *)*((_QWORD *)&v105 + 1);
              v18 = (char *)v109;
            }
          }
          if ( (*v18 & 2) != 0 )
            v39 = (unsigned __int8)v18[3] + ((unsigned __int64)(unsigned __int8)v18[2] << 8);
          else
            v39 = 0;
          v38 = &v20[v39 + ((*v18 & 2) != 0 ? 44LL : 12LL)];
          goto LABEL_62;
        }
      }
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_22;
      v16 = 45;
      goto LABEL_21;
    }
    v12 = (unsigned int *)(*v6 + 16LL * v11);
    v13 = v12[1];
    LODWORD(a3) = v13 & 0x10000000;
    if ( v13 < 0 )
    {
      if ( (_DWORD)a3 )
        break;
    }
    if ( (v13 & 0xFFFFFFF) == 2 )
    {
      v7 = (size_t *)(*v6 + 16LL * v11);
    }
    else if ( (v13 & 0xFFFFFFF) == 0xA )
    {
      v9 = *v12;
      v8 = *v6 + 16LL * v11;
      v115 = v8;
    }
    else if ( v13 >= 0 )
    {
      v9 += *v12;
      if ( !(_DWORD)a3 )
        v10 += *v12;
    }
    v6 = v116;
    ++v11;
    v5 = v117;
  }
  v14 = -2146893048;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids);
    goto LABEL_217;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800332b0  push    rbp
0x1800332b2  push    rbx
0x1800332b3  push    rsi
0x1800332b4  push    rdi
0x1800332b5  push    r12
0x1800332b7  push    r13
0x1800332b9  push    r14
0x1800332bb  push    r15
0x1800332bd  lea     rbp, [rsp-138h]
0x1800332c5  sub     rsp, 238h
0x1800332cc  mov     rax, cs:__security_cookie
0x1800332d3  xor     rax, rsp
0x1800332d6  mov     [rbp+170h+var_50], rax
0x1800332dd  xor     r11d, r11d
0x1800332e0  mov     [rbp+170h+var_1C8], rcx
0x1800332e4  xorps   xmm0, xmm0
0x1800332e7  mov     [rbp+170h+var_188], r9
0x1800332eb  mov     rdi, rcx
0x1800332ee  mov     dword ptr [rbp+170h+var_1E0], r8d
0x1800332f2  lea     rcx, [rdx+4]
0x1800332f6  mov     [rbp+170h+var_1C0], rdx
0x1800332fa  xorps   xmm1, xmm1
0x1800332fd  mov     [rbp+170h+var_190], rcx
0x180033301  lea     rax, [rdx+8]
0x180033305  mov     [rsp+270h+var_208], r11
0x18003330a  mov     [rbp+170h+var_1D0], r11
0x18003330e  mov     ebx, r11d
0x180033311  mov     r12d, r11d
0x180033314  mov     [rbp+170h+var_1A0], r11
0x180033318  movups  xmmword ptr [rbp+170h+Size], xmm0
0x18003331c  mov     [rsp+270h+var_210], r11
0x180033321  mov     r10d, r11d
0x180033324  movups  [rsp+270h+var_200], xmm1
0x180033329  mov     [rbp+170h+var_1E8], r11
0x18003332d  mov     r15d, r11d
0x180033330  movups  [rbp+170h+var_180], xmm0
0x180033334  mov     [rsp+270h+var_218], r11d
0x180033339  mov     r9d, r11d
0x18003333c  mov     [rbp+170h+var_1F0], r11d
0x180033340  mov     [rbp+170h+var_1B8], r11
0x180033344  mov     [rbp+170h+var_1D8], r11
0x180033348  mov     [rbp+170h+var_198], rax
0x18003334c  cmp     r9d, [rcx]
0x18003334f  jnb     loc_1800333F3
0x180033355  mov     edx, r9d
0x180033358  shl     rdx, 4
0x18003335c  add     rdx, [rax]
0x18003335f  mov     ecx, [rdx+4]
0x180033362  mov     r8d, ecx
0x180033365  and     r8d, 10000000h
0x18003336c  test    ecx, ecx
0x18003336e  jns     short loc_180033375
0x180033370  test    r8d, r8d
0x180033373  jnz     short loc_1800333B3
0x180033375  mov     eax, ecx
0x180033377  and     eax, 0FFFFFFFh
0x18003337c  cmp     eax, 2
0x18003337f  jnz     short loc_180033386
0x180033381  mov     rbx, rdx
0x180033384  jmp     short loc_1800333A6
0x180033386  cmp     eax, 0Ah
0x180033389  jnz     short loc_180033397
0x18003338b  mov     r10d, [rdx]
0x18003338e  mov     r12, rdx
0x180033391  mov     [rbp+170h+var_1A0], rdx
0x180033395  jmp     short loc_1800333A6
0x180033397  test    ecx, ecx
0x180033399  js      short loc_1800333A6
0x18003339b  add     r10d, [rdx]
0x18003339e  test    r8d, r8d
0x1800333a1  jnz     short loc_1800333A6
0x1800333a3  add     r15d, [rdx]
0x1800333a6  mov     rax, [rbp+170h+var_198]
0x1800333aa  inc     r9d
0x1800333ad  mov     rcx, [rbp+170h+var_190]
0x1800333b1  jmp     short loc_18003334C
0x1800333b3  mov     ebx, 80090308h
0x1800333b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800333bf  lea     r14, WPP_GLOBAL_Control
0x1800333c6  cmp     rcx, r14
0x1800333c9  jz      loc_180034166
0x1800333cf  test    byte ptr [rcx+1Ch], 1
0x1800333d3  jz      loc_180034166
0x1800333d9  mov     rcx, [rcx+10h]
0x1800333dd  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x1800333e4  mov     edx, 2Bh ; '+'
0x1800333e9  call    WPP_SF_
0x1800333ee  jmp     loc_180034129
0x1800333f3  lea     r14, WPP_GLOBAL_Control
0x1800333fa  mov     r13d, 10h
0x180033400  test    r12, r12
0x180033403  jz      loc_18003389F
0x180033409  test    rbx, rbx
0x18003340c  jz      short loc_18003343E
0x18003340e  mov     rcx, cs:WPP_GLOBAL_Control
0x180033415  cmp     rcx, r14
0x180033418  jz      short loc_180033434
0x18003341a  test    byte ptr [rcx+1Ch], 1
0x18003341e  jz      short loc_180033434
0x180033420  lea     edx, [r13+1Ch]
0x180033424  mov     rcx, [rcx+10h]
0x180033428  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x18003342f  call    WPP_SF_
0x180033434  mov     ebx, 0C000000Dh
0x180033439  jmp     loc_180034129
0x18003343e  movups  xmm0, xmmword ptr [r12]
0x180033443  movdqu  [rsp+270h+var_200], xmm0
0x180033449  mov     r9d, dword ptr [rsp+270h+var_200]
0x18003344e  add     r9d, 0FFFFFFFEh
0x180033452  mov     dword ptr [rsp+270h+var_200+4], 1
0x18003345a  movdqu  xmmword ptr [rbp+170h+Size], xmm0
0x18003345f  mov     dword ptr [rbp+170h+Size+4], 2
0x180033466  js      loc_180033876
0x18003346c  mov     rdi, qword ptr [rsp+270h+var_200+8]
0x180033471  add     rdi, 2
0x180033475  mov     [rbp+170h+var_1D8], rdi
0x180033479  cmp     r9d, 0Eh
0x18003347d  jb      loc_180033876
0x180033483  add     r9d, 0FFFFFFF2h
0x180033487  js      loc_180033876
0x18003348d  mov     dword ptr [rsp+270h+var_200], r9d
0x180033492  lea     r15, [rdi+0Eh]
0x180033496  mov     qword ptr [rsp+270h+var_200+8], r15
0x18003349b  test    r9d, r9d
0x18003349e  jz      loc_18003387B
0x1800334a4  mov     r11d, [r12]
0x1800334a8  lea     rax, [rsp+270h+var_200]
0x1800334ad  mov     dl, [rdi]
0x1800334af  sub     r11d, r9d
0x1800334b2  mov     [rsp+270h+var_21C], r11d
0x1800334b7  mov     dword ptr [rbp+170h+var_180+4], 1
0x1800334be  mov     qword ptr [rbp+170h+var_180+8], rax
0x1800334c2  and     dl, 2
0x1800334c5  jz      short loc_1800334DF
0x1800334c7  movzx   r8d, byte ptr [rdi+2]
0x1800334cc  mov     ecx, 100h
0x1800334d1  movzx   eax, byte ptr [rdi+3]
0x1800334d5  imul    r8d, ecx
0x1800334d9  add     r8w, ax
0x1800334dd  jmp     short loc_1800334E5
0x1800334df  xor     eax, eax
0x1800334e1  movzx   r8d, ax
0x1800334e5  mov     al, dl
0x1800334e7  neg     al
0x1800334e9  sbb     si, si
0x1800334ec  and     si, r13w
0x1800334f0  add     si, 0Ch
0x1800334f4  add     si, r8w
0x1800334f8  test    dl, dl
0x1800334fa  jz      short loc_18003350B
0x1800334fc  movzx   ecx, byte ptr [rdi+2]
0x180033500  movzx   eax, byte ptr [rdi+3]
0x180033504  shl     ecx, 8
0x180033507  add     ecx, eax
0x180033509  jmp     short loc_18003350D
0x18003350b  xor     ecx, ecx
0x18003350d  neg     dl
0x18003350f  sbb     eax, eax
0x180033511  and     eax, 20h
0x180033514  add     eax, 1Ch
0x180033517  add     eax, ecx
0x180033519  cmp     r10d, eax
0x18003351c  jnb     short loc_18003355C
0x18003351e  mov     rcx, cs:WPP_GLOBAL_Control
0x180033525  cmp     rcx, r14
0x180033528  jz      loc_180034124
0x18003352e  test    byte ptr [rcx+1Ch], 1
0x180033532  jz      loc_180034124
0x180033538  mov     rcx, [rcx+10h]
0x18003353c  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x180033543  movzx   eax, si
0x180033546  mov     edx, 2Eh ; '.'
0x18003354b  mov     r9d, r10d
0x18003354e  mov     dword ptr [rsp+270h+var_250], eax
0x180033552  call    WPP_SF_dd
0x180033557  jmp     loc_180034124
0x18003355c  movzx   r8d, byte ptr [rdi+4]
0x180033561  lea     ecx, [r10-10h]
0x180033565  movzx   eax, byte ptr [rdi+5]
0x180033569  xor     edx, edx
0x18003356b  shl     r8d, 8
0x18003356f  add     eax, r8d
0x180033572  div     ecx
0x180033574  cmp     dx, si
0x180033577  jbe     short loc_1800335CD
0x180033579  movzx   eax, si
0x18003357c  movzx   r12d, dx
0x180033580  sub     r12d, eax
0x180033583  jz      loc_1800336D6
0x180033589  cmp     r9d, 1
0x18003358d  jbe     loc_1800336D6
0x180033593  xor     r13d, r13d
0x180033596  lea     r14d, [r9-1]
0x18003359a  mov     bl, [r15]
0x18003359d  lea     rdx, [r15+1]; Src
0x1800335a1  mov     r8, r14; Size
0x1800335a4  mov     rcx, r15; void *
0x1800335a7  call    memmove_0
0x1800335ac  inc     r13d
0x1800335af  mov     [r14+r15], bl
0x1800335b3  cmp     r13d, r12d
0x1800335b6  jb      short loc_18003359A
0x1800335b8  mov     r15, qword ptr [rsp+270h+var_200+8]
0x1800335bd  lea     r14, WPP_GLOBAL_Control
0x1800335c4  mov     rdi, [rbp+170h+var_1D8]
0x1800335c8  jmp     loc_1800336D6
0x1800335cd  movzx   r8d, si
0x1800335d1  jnb     loc_1800336D3
0x1800335d7  lea     rax, [rbp+170h+var_110]
0x1800335db  mov     [rbp+170h+Size+8], rax
0x1800335df  lea     rdi, [rbp+170h+var_10E]
0x1800335e3  mov     eax, 80h
0x1800335e8  mov     [rbp+170h+var_1D8], rdi
0x1800335ec  cmp     si, ax
0x1800335ef  jnb     loc_1800336A2
0x1800335f5  mov     ecx, eax
0x1800335f7  movzx   r13d, si
0x1800335fb  sub     rcx, r13
0x1800335fe  mov     eax, r11d
0x180033601  cmp     rax, rcx
0x180033604  ja      loc_1800336A2
0x18003360a  mov     rcx, [r12+8]
0x18003360f  mov     ebx, r8d
0x180033612  movzx   r12d, dx
0x180033616  sub     rbx, r12
0x180033619  mov     edx, r9d
0x18003361c  sub     rdx, rbx
0x18003361f  mov     r8, rbx; Size
0x180033622  movzx   eax, word ptr [rcx]
0x180033625  add     rdx, r15; Src
0x180033628  mov     [rbp+170h+var_110], ax
0x18003362c  mov     rax, [rcx+2]
0x180033630  mov     [rbp+170h+var_10E], rax
0x180033634  mov     eax, [rcx+0Ah]
0x180033637  mov     [rbp+170h+var_106], eax
0x18003363a  movzx   eax, word ptr [rcx+0Eh]
0x18003363e  lea     rcx, [rbp+170h+var_100]; void *
0x180033642  mov     [rbp+170h+var_102], ax
0x180033646  call    memcpy_0
0x18003364b  movzx   eax, si
0x18003364e  add     eax, 10h
0x180033651  cmp     eax, 80h
0x180033656  jb      short loc_180033671
0x180033658  mov     rcx, cs:WPP_GLOBAL_Control
0x18003365f  cmp     rcx, r14
0x180033662  jz      short loc_1800336C9
0x180033664  test    byte ptr [rcx+1Ch], 1
0x180033668  jz      short loc_1800336C9
0x18003366a  mov     edx, 30h ; '0'
0x18003366f  jmp     short loc_1800336B9
0x180033671  lea     rcx, [rbp+170h+var_100]
0x180033675  mov     r8, r12; Size
0x180033678  add     rcx, rbx; void *
0x18003367b  mov     rdx, r15; Src
0x18003367e  call    memcpy_0
0x180033683  add     r15, r12
0x180033686  test    byte ptr [rbp+170h+var_10E], 2
0x18003368a  mov     qword ptr [rsp+270h+var_200+8], r15
0x18003368f  jz      short loc_180033707
0x180033691  movups  xmm0, xmmword ptr [r15]
0x180033695  lea     rax, [r15+10h]
0x180033699  movdqu  [rbp+r13+170h+var_100], xmm0
0x1800336a0  jmp     short loc_180033702
0x1800336a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800336a9  cmp     rcx, r14
0x1800336ac  jz      short loc_1800336C9
0x1800336ae  test    byte ptr [rcx+1Ch], 1
0x1800336b2  jz      short loc_1800336C9
0x1800336b4  mov     edx, 2Fh ; '/'
0x1800336b9  mov     rcx, [rcx+10h]
0x1800336bd  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x1800336c4  call    WPP_SF_
0x1800336c9  mov     ebx, 0C00000BBh
0x1800336ce  jmp     loc_180034129
0x1800336d3  movzx   esi, dx
0x1800336d6  mov     dl, [rdi]
0x1800336d8  and     dl, 2
0x1800336db  jz      short loc_1800336EE
0x1800336dd  movzx   ecx, byte ptr [rdi+2]
0x1800336e1  movzx   eax, byte ptr [rdi+3]
0x1800336e5  shl     rcx, 8
0x1800336e9  add     rcx, rax
0x1800336ec  jmp     short loc_1800336F0
0x1800336ee  xor     ecx, ecx
0x1800336f0  neg     dl
0x1800336f2  sbb     rax, rax
0x1800336f5  and     eax, 20h
0x1800336f8  add     rax, 0Ch
0x1800336fc  add     rax, rcx
0x1800336ff  add     rax, r15
0x180033702  mov     qword ptr [rsp+270h+var_200+8], rax
0x180033707  lea     rax, [rbp+170h+var_180]
0x18003370b  mov     [rbp+170h+var_1C0], rax
0x18003370f  lea     rbx, [rbp+170h+Size]
0x180033713  movzx   eax, si
0x180033716  shr     ax, 8
0x18003371a  mov     [rdi+4], al
0x18003371d  mov     [rdi+5], sil
0x180033721  mov     cl, [rdi]
0x180033723  and     cl, 2
  ... truncated ...
```
