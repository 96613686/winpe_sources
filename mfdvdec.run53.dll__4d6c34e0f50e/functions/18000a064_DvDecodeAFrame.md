# DvDecodeAFrame

- ea: `0x18000a064`
- end: `0x18000b833`
- name: `DvDecodeAFrame`
- size: `6095`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006b70`

## callees

- `0x18000a064`
- `0x18001aa20`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall DvDecodeAFrame(__int64 a1, int a2, __int64 a3, __int64 a4, int a5, int a6, __int64 a7)
{
  int *v7; // rbx
  _DWORD *v8; // r15
  _DWORD *v9; // r13
  __int64 (__fastcall *v10)(); // r12
  int v11; // edi
  __int64 v12; // rdx
  __int64 (__fastcall **v13)(int, int, int, int, int); // r8
  __int64 (__fastcall **v14)(int, int, int, int, __int64, int); // r13
  __int64 (__fastcall **v15)(int, int, int, int, __int64, int); // r11
  __int64 (__fastcall **v16)(); // r15
  __int64 (__fastcall **v17)(); // rdx
  int v18; // r10d
  int v19; // r9d
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // r10d
  int v25; // eax
  int v26; // esi
  __int64 (__fastcall *v27)(int, int, int, int, int); // rdx
  bool v28; // zf
  __int64 (__fastcall *v29)(); // rax
  __int64 (__fastcall *v30)(int, int, int, int, __int64, int); // r11
  __int64 (__fastcall *v31)(); // rcx
  int v32; // esi
  int v33; // esi
  bool v34; // zf
  __int64 (__fastcall *v35)(int, int, int, int, __int64, int); // r11
  int v36; // esi
  int *v37; // r11
  __int64 (__fastcall *v38)(int, int, int, int, int); // rdx
  __int64 (__fastcall *v39)(); // rcx
  __int64 (__fastcall *v40)(int, int, int, int, int); // rdx
  __int64 (__fastcall **v41)(); // r12
  __int64 (__fastcall **v42)(); // rcx
  __int64 (__fastcall **v43)(int, int, int, int, __int64, int); // rax
  __int64 (__fastcall *v44)(); // rcx
  int v45; // ecx
  __int64 (__fastcall **v46)(); // r12
  int v47; // ecx
  int v48; // ecx
  int v49; // ecx
  int v50; // ecx
  int v51; // ecx
  int v52; // ecx
  int v53; // eax
  __int64 (__fastcall *v54)(int, int, int, int, __int64, int); // rax
  __int64 (__fastcall *v55)(int, int, int, int, __int64, int); // rcx
  __int64 (__fastcall *v56)(int, int, int, int, int); // rdx
  __int64 (__fastcall *v57)(int, int, int, int, int); // rax
  int v58; // ecx
  __int64 v59; // rcx
  int v60; // ecx
  int v61; // ecx
  int v62; // ecx
  int v63; // ecx
  int v64; // ecx
  int v65; // ecx
  int v66; // edx
  int v67; // ecx
  int v68; // edx
  int v69; // ecx
  int v70; // edx
  int v71; // ecx
  int v72; // ecx
  int v73; // ecx
  int v74; // ecx
  int v75; // ecx
  int v76; // edx
  int v77; // ecx
  int v78; // edx
  int v79; // ecx
  int v80; // eax
  int v81; // edi
  int v82; // edi
  int v83; // edi
  __int64 v84; // rdx
  int v85; // edx
  int v86; // edx
  int v87; // ecx
  int v88; // r15d
  int v89; // edx
  int v90; // ecx
  int v91; // ecx
  int v92; // r14d
  int v93; // eax
  int v94; // eax
  int v95; // eax
  __int64 (__fastcall *v96)(); // rax
  int v97; // eax
  __int64 (__fastcall *v98)(); // rax
  __int64 (__fastcall *v99)(); // rax
  __int64 (__fastcall *v100)(); // rax
  __int64 (__fastcall *v101)(); // rcx
  int v102; // ecx
  int v103; // ecx
  int v104; // ecx
  int v105; // ecx
  int v106; // ecx
  int v107; // ecx
  int v108; // ecx
  __int64 (__fastcall *v109)(); // rax
  __int64 (__fastcall *v110)(); // rax
  int v111; // r9d
  int v112; // ecx
  int v113; // edx
  int v114; // edx
  int v115; // edx
  int v116; // ecx
  int v117; // edx
  int v118; // edx
  int v119; // edx
  int v120; // ecx
  int v121; // edx
  int v122; // edx
  int v123; // edx
  int v124; // ecx
  int v125; // edx
  int v126; // edx
  int v127; // edx
  int v128; // eax
  int v129; // r8d
  __int128 v131; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall *v132)(int, int, int, int, int); // [rsp+40h] [rbp-C0h] BYREF
  __int128 v133; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall *v134)(int, int, int, int, __int64, int); // [rsp+58h] [rbp-A8h] BYREF
  __int128 v135; // [rsp+60h] [rbp-A0h] BYREF
  __int64 (__fastcall *v136)(); // [rsp+70h] [rbp-90h] BYREF
  __int128 v137; // [rsp+78h] [rbp-88h] BYREF
  __int64 (__fastcall *v138)(int, int, int, int, __int64, int); // [rsp+88h] [rbp-78h] BYREF
  __int128 v139; // [rsp+90h] [rbp-70h] BYREF
  __int64 (__fastcall *v140)(int, int, int, int, __int64, int); // [rsp+A0h] [rbp-60h] BYREF
  __int128 v141; // [rsp+A8h] [rbp-58h] BYREF
  __int64 (__fastcall *v142)(); // [rsp+B8h] [rbp-48h] BYREF
  __int128 v143; // [rsp+C0h] [rbp-40h] BYREF
  __int64 (__fastcall *v144)(); // [rsp+D0h] [rbp-30h] BYREF
  __int64 (__fastcall **v145)(int, int, int, int, __int64, int); // [rsp+D8h] [rbp-28h]
  __int64 (__fastcall **v146)(); // [rsp+E0h] [rbp-20h]
  __int64 (__fastcall **v147)(); // [rsp+E8h] [rbp-18h]
  __int64 (__fastcall **v148)(int, int, int, int, __int64, int); // [rsp+F0h] [rbp-10h]
  __int64 (__fastcall **v149)(); // [rsp+F8h] [rbp-8h]
  __int64 (__fastcall **v150)(); // [rsp+100h] [rbp+0h]
  __int64 (__fastcall **v151)(); // [rsp+108h] [rbp+8h]
  __int128 v152; // [rsp+110h] [rbp+10h] BYREF
  __int64 (__fastcall *v153)(); // [rsp+120h] [rbp+20h] BYREF
  __int128 v154; // [rsp+128h] [rbp+28h] BYREF
  __int64 (__fastcall *v155)(); // [rsp+138h] [rbp+38h] BYREF
  __int128 v156; // [rsp+140h] [rbp+40h] BYREF
  __int64 (__fastcall *v157)(_QWORD); // [rsp+150h] [rbp+50h] BYREF
  __int128 v158; // [rsp+158h] [rbp+58h] BYREF
  __int64 (__fastcall *v159)(_QWORD); // [rsp+168h] [rbp+68h] BYREF
  __int64 v160; // [rsp+170h] [rbp+70h] BYREF
  int v161; // [rsp+178h] [rbp+78h]
  int v162; // [rsp+17Ch] [rbp+7Ch]
  __int64 v164; // [rsp+1D0h] [rbp+D0h]

  v164 = a3;
  v132 = 0;
  v138 = 0;
  v140 = 0;
  v134 = 0;
  v136 = 0;
  v144 = 0;
  v142 = 0;
  v153 = 0;
  v157 = 0;
  v155 = 0;
  v159 = 0;
  v162 = 0;
  v131 = 0;
  v137 = 0;
  v139 = 0;
  v133 = 0;
  v135 = 0;
  v143 = 0;
  v141 = 0;
  v152 = 0;
  v156 = 0;
  v154 = 0;
  v158 = 0;
  if ( !a5 || !a2 )
    return 2147500037LL;
  v161 = a2 - 1;
  v7 = (int *)((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL);
  v160 = a1;
  v8 = v7 + 2410;
  v9 = v7 + 108395;
  if ( *(_BYTE *)v7 != 1 )
  {
    *v8 = 0;
    *v9 = 0;
  }
  v10 = *(__int64 (__fastcall **)())(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x20);
  v11 = a6;
  if ( a5 == *v8 && a6 == *v9 && *(_BYTE *)v7 == 1 )
  {
    v12 = a1;
LABEL_251:
    ((void (__fastcall *)(__int64 *, __int64, __int64, int *))v10)(&v160, v12, a3, v7);
    return 0;
  }
  VLDecodeTableInit();
  *(_BYTE *)v7 = 1;
  *v8 = a5;
  *v9 = a6;
  if ( (a5 & 0x22000) == 0 )
    return 2147500037LL;
  if ( (a5 & 0x2000000) != 0 )
  {
    v146 = (__int64 (__fastcall **)())&v157;
    v149 = &v153;
    v147 = &v136;
    v150 = (__int64 (__fastcall **)())&v159;
    v148 = &v134;
    v151 = &v142;
    v13 = &v132;
    v14 = &v138;
    v15 = &v140;
    v16 = &v155;
    v17 = &v144;
  }
  else if ( (a5 & 0x1000000) != 0 )
  {
    v146 = (__int64 (__fastcall **)())&v156 + 1;
    v149 = (__int64 (__fastcall **)())&v152 + 1;
    v147 = (__int64 (__fastcall **)())&v135 + 1;
    v150 = (__int64 (__fastcall **)())&v158 + 1;
    v148 = (__int64 (__fastcall **)(int, int, int, int, __int64, int))&v133 + 1;
    v151 = (__int64 (__fastcall **)())&v141 + 1;
    v13 = (__int64 (__fastcall **)(int, int, int, int, int))&v131 + 1;
    v14 = (__int64 (__fastcall **)(int, int, int, int, __int64, int))&v137 + 1;
    v15 = (__int64 (__fastcall **)(int, int, int, int, __int64, int))&v139 + 1;
    v16 = (__int64 (__fastcall **)())&v154 + 1;
    v17 = (__int64 (__fastcall **)())&v143 + 1;
  }
  else
  {
    v146 = (__int64 (__fastcall **)())&v156;
    v13 = (__int64 (__fastcall **)(int, int, int, int, int))&v131;
    v147 = (__int64 (__fastcall **)())&v135;
    v14 = (__int64 (__fastcall **)(int, int, int, int, __int64, int))&v137;
    v148 = (__int64 (__fastcall **)(int, int, int, int, __int64, int))&v133;
    v15 = (__int64 (__fastcall **)(int, int, int, int, __int64, int))&v139;
    v149 = (__int64 (__fastcall **)())&v152;
    v16 = (__int64 (__fastcall **)())&v154;
    v150 = (__int64 (__fastcall **)())&v158;
    v17 = (__int64 (__fastcall **)())&v143;
    v151 = (__int64 (__fastcall **)())&v141;
  }
  v18 = 48;
  v145 = v15;
  v19 = 16;
  if ( (a5 & 0x30) == 0x10 )
  {
    v20 = 10;
  }
  else
  {
    if ( (a5 & 0x30) != 0x20 )
      return 2147500037LL;
    v20 = 12;
  }
  *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xE4) = v20;
  v21 = a5 & 0xF;
  if ( (a5 & 0x20010) == 0 )
  {
    v93 = v21 - 1;
    if ( v93 )
    {
      v94 = v93 - 1;
      if ( v94 )
      {
        v18 = 2;
        v95 = v94 - 2;
        if ( v95 )
        {
          if ( v95 != 4 )
          {
            v18 = 0;
            v19 = 0;
LABEL_246:
            v111 = *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) * v19;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C) = v111;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xCC) = 3 * v111;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = 0;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x44) = v111;
            v112 = v111 + *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x48) = v112;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x4C) = v112 + v18;
            v113 = v112 - *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C) + v18;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x50) = v113;
            v114 = v113 - *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x54) = v114;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x58) = v114 + v18;
            v115 = v18 + *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C) + v114;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x5C) = v115;
            v116 = v115 + *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x60) = v116;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x64) = v116 + v18;
            v117 = v116 - *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C) + v18;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x68) = v117;
            v118 = v117 - *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x6C) = v118;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x70) = v118 + v18;
            v119 = v18 + *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C) + v118;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x74) = v119;
            v120 = v119 + *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x78) = v120;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x7C) = v120 + v18;
            v121 = v120 - *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C) + v18;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) = v121;
            v122 = v121 - *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x84) = v122;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x88) = v122 + v18;
            v123 = v18 + *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C) + v122;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x8C) = v123;
            v124 = v123 + *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x90) = v124;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x94) = v124 + v18;
            v125 = v124 - *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C) + v18;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x98) = v125;
            v126 = v125 - *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x9C) = v126;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xA0) = v126 + v18;
            v127 = v18 + *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C) + v126;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xA4) = v127;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xA8) = v127
                                                                    + *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL)
                                                                                + 0x3C);
            v128 = *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xCC);
            if ( v128 < 0 )
              v129 = *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x38)
                   - *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xE4) * v128;
            else
              v129 = 0;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xC4) = v129;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xBC) = 9 * v18 + v129;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xB8) = v129 + 18 * v18;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xC8) = v129 + 36 * v18;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xC0) = 9 * v18 + v129 + 18 * v18;
LABEL_250:
            a3 = v164;
            v12 = a1;
            *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) = v10;
            goto LABEL_251;
          }
          if ( (unsigned int)(a6 + 87) <= 0xAE )
            return 2147500037LL;
          v10 = decode62588;
          v19 = 2;
          switch ( a5 & 0x1FC0 )
          {
            case 64:
              v99 = rgbtransYUY2DCout625;
              break;
            case 128:
              v99 = rgbtransUYVYDCout625;
              break;
            case 256:
              v100 = rgbtrans24bitDCout625_DR219;
              v18 = 6;
              if ( (a5 & 0x100000) == 0 )
                v100 = rgbtrans24bitDCout625;
              *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 8) = v100;
              v97 = 3 * a6;
              goto LABEL_245;
            case 512:
              v99 = rgbtrans16bit1DCout625;
              break;
            case 1024:
              v99 = rgbtrans16bit0DCout625;
              break;
            case 2048:
              v98 = rgbtrans8bitDCout625;
LABEL_164:
              *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 8) = v98;
              *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) = v11;
              goto LABEL_246;
            case 4352:
              v96 = rgbtrans32bitDCout625_DR219;
              v18 = 8;
              if ( (a5 & 0x100000) == 0 )
                v96 = rgbtrans32bitDCout625;
              *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 8) = v96;
              v97 = 4 * a6;
              goto LABEL_245;
            default:
              return 2147500037LL;
          }
          v18 = 4;
          goto LABEL_244;
        }
        if ( (unsigned int)(a6 + 179) <= 0x166 )
          return 2147500037LL;
        switch ( a5 & 0x1FC0 )
        {
          case 64:
            v98 = rgbtransYUY2out625;
            break;
          case 128:
            v98 = rgbtransUYVYout625;
            break;
          case 256:
            v18 = 12;
            v11 = 3 * a6;
            v101 = rgbtrans24bitout625;
            v98 = rgbtrans24bitout625_DR219;
LABEL_186:
            if ( (a5 & 0x100000) == 0 )
              v98 = v101;
            goto LABEL_192;
          case 512:
            v98 = rgbtrans16bit1out625;
            break;
          case 1024:
            v98 = rgbtrans16bit0out625;
            break;
          case 2048:
            v18 = 4;
            v98 = rgbtrans8bitout625;
LABEL_192:
            v10 = decode625180;
            v19 = 4;
            goto LABEL_164;
          case 4352:
            v18 = 16;
            v11 = 4 * a6;
            v98 = rgbtrans32bitout625_DR219;
            v101 = rgbtrans32bitout625;
            goto LABEL_186;
          default:
            return 2147500037LL;
        }
        v11 = 2 * a6;
        v18 = 8;
        goto LABEL_192;
      }
      if ( (unsigned int)(a6 + 359) <= 0x2CE )
        return 2147500037LL;
      *(_QWORD *)&v158 = decode625360;
      *((_QWORD *)&v158 + 1) = rgbtransYUY2FulloutRight;
      v159 = rgbtransYUY2FulloutRight;
      if ( (a5 & 0x1FC0) == 0x40 )
      {
        *(_QWORD *)&v141 = rgbtransYUY2out625;
        v142 = rgbtransYUY2out625;
      }
      else if ( (a5 & 0x1FC0) == 0x80 )
      {
        *(_QWORD *)&v141 = rgbtransUYVYout625;
        v142 = rgbtransUYVYout625;
      }
      else
      {
        if ( (a5 & 0x1FC0) == 0x100 )
        {
          if ( (a5 & 0x100000) != 0 )
          {
            *(_QWORD *)&v141 = rgbtrans24bitout625_DR219;
            v142 = rgbtrans24bitout625_DR219;
          }
          else
          {
            *(_QWORD *)&v141 = rgbtrans24bitout625;
            v142 = rgbtrans24bitout625;
          }
          v18 = 24;
          v11 = 3 * a6;
          goto LABEL_215;
        }
        if ( (a5 & 0x1FC0) == 0x200 )
        {
          *(_QWORD *)&v141 = rgbtrans16bit1out625;
          v142 = rgbtrans16bit1out625;
        }
        else
        {
          if ( (a5 & 0x1FC0) != 0x400 )
          {
            if ( (a5 & 0x1FC0) == 0x800 )
            {
              v18 = 8;
              *(_QWORD *)&v141 = rgbtrans8bitout625;
              v142 = rgbtrans8bitout625;
            }
            else
            {
              if ( (a5 & 0x1FC0) != 0x1100 )
                return 2147500037LL;
              if ( (a5 & 0x100000) != 0 )
              {
                *(_QWORD *)&v141 = rgbtrans32bitout625_DR219;
                v142 = rgbtrans32bitout625_DR219;
              }
              else
              {
                *(_QWORD *)&v141 = rgbtrans32bitout625;
                v142 = rgbtrans32bitout625;
              }
              v18 = 32;
              v11 = 4 * a6;
            }
            goto LABEL_215;
          }
          *(_QWORD *)&v141 = rgbtrans16bit0out625;
          v142 = rgbtrans16bit0out625;
        }
      }
      v11 = 2 * a6;
      v18 = 16;
LABEL_215:
      v19 = 8;
      *((_QWORD *)&v141 + 1) = rgbtransYUY2FulloutRight;
      v10 = *v150;
      v98 = *v151;
      goto LABEL_164;
    }
    if ( (unsigned int)(a6 + 719) <= 0x59E )
      return 2147500037LL;
    v102 = a5 & 0x1FC0;
    *((_QWORD *)&v154 + 1) = rgbtransYUY2FulloutRight;
    *(_QWORD *)&v154 = decode625720;
    if ( ((v102 - 64) & 0xFFFFFF3F) != 0 || v102 == 192 )
      v155 = decode625720;
    else
      v155 = decode625720SSE2;
    v10 = *v16;
    *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xFC) = 0;
    v103 = v102 - 64;
    if ( v103 )
    {
      v104 = v103 - 64;
      if ( v104 )
      {
        v105 = v104 - 128;
        if ( !v105 )
        {
          if ( (a5 & 0x100000) != 0 )
          {
            *(_QWORD *)&v143 = rgbtrans24bitout625_DR219;
            *((_QWORD *)&v143 + 1) = rgbtransYUY2FulloutRight;
            v109 = rgbtransPAL_RGB888Fullout_DR219SSE2;
          }
          else
          {
            *((_QWORD *)&v143 + 1) = rgbtransYUY2FulloutRight;
            v109 = rgbtransPAL_RGB888FulloutSSE2;
            *(_QWORD *)&v143 = rgbtrans24bitout625;
          }
          v144 = v109;
          *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 8) = *v17;
          v97 = 3 * a6;
          goto LABEL_245;
        }
        v106 = v105 - 256;
        if ( v106 )
        {
          v107 = v106 - 512;
          if ( v107 )
          {
            v108 = v107 - 1024;
            if ( !v108 )
            {
              *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) = a6;
              *(_QWORD *)&v143 = rgbtrans8bitout625;
              v18 = 16;
              v144 = rgbtrans8bitout625;
              *((_QWORD *)&v143 + 1) = rgbtransYUY2FulloutRight;
              *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 8) = *v17;
              goto LABEL_246;
            }
            if ( v108 != 2304 )
              return 2147500037LL;
            if ( (a5 & 0x100000) != 0 )
            {
              *(_QWORD *)&v143 = rgbtrans32bitout625_DR219;
              v144 = rgbtrans32bitout625_DR219;
            }
            else
            {
              *(_QWORD *)&v143 = rgbtrans32bitout625;
              v144 = rgbtrans32bitout625;
            }
            *((_QWORD *)&v143 + 1) = rgbtransYUY2FulloutRight;
            v18 = 64;
            *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 8) = *v17;
            v97 = 4 * a6;
LABEL_245:
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) = v97;
            goto LABEL_246;
          }
          *(_QWORD *)&v143 = rgbtrans16bit0out625;
          v144 = rgbtrans16bit0out625;
        }
        else
        {
          *(_QWORD *)&v143 = rgbtrans16bit1out625;
          v144 = rgbtrans16bit1out625;
        }
        *((_QWORD *)&v143 + 1) = rgbtransYUY2FulloutRight;
        goto LABEL_243;
      }
      *(_QWORD *)&v143 = rgbtransUYVYout625;
      *((_QWORD *)&v143 + 1) = rgbtransYUY2FulloutRight;
      v110 = rgbtransPAL_UYVYFulloutSSE2;
    }
    else
    {
      *(_QWORD *)&v143 = rgbtransYUY2out625;
      *((_QWORD *)&v143 + 1) = rgbtransYUY2FulloutRight;
      v110 = rgbtransPAL_YUY2FulloutSSE2;
    }
    v144 = v110;
LABEL_243:
    v99 = *v17;
    v18 = 32;
LABEL_244:
    *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 8) = v99;
    v97 = 2 * a6;
    goto LABEL_245;
  }
  v22 = v21 - 1;
  if ( !v22 )
  {
    if ( (unsigned int)(a6 + 719) <= 0x59E )
      return 2147500037LL;
    v45 = a5 & 0x1FC0;
    *((_QWORD *)&v152 + 1) = rgbtransYUY2FulloutRight;
    *(_QWORD *)&v152 = decode720;
    if ( ((v45 - 64) & 0xFFFFFF3F) != 0 || v45 == 192 )
      v153 = decode720;
    else
      v153 = decode720SSE2;
    v46 = v149;
    v24 = 8;
    *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xFC) = 0;
    v10 = *v46;
    v47 = v45 - 64;
    if ( v47 )
    {
      v48 = v47 - 64;
      if ( v48 )
      {
        v49 = v48 - 128;
        if ( !v49 )
        {
          *((_QWORD *)&v137 + 1) = rgbtransYUY2FulloutRight;
          if ( (a5 & 0x100000) != 0 )
          {
            *(_QWORD *)&v137 = rgbtrans24bitout2_DR219;
            v138 = (__int64 (__fastcall *)(int, int, int, int, __int64, int))rgbtransRGB888Fullout_DR219SSE2;
            *(_QWORD *)&v131 = rgbtranshC_DR219;
            *(_QWORD *)&v139 = rgbtrans24bitoutRight2_DR219;
            *((_QWORD *)&v139 + 1) = rgbtransYUY2FulloutRight;
            v140 = (__int64 (__fastcall *)(int, int, int, int, __int64, int))rgbtransRGB888FulloutRight_DR219SSE2;
            *((_QWORD *)&v131 + 1) = rgbtransYUY2FulloutRight;
            v57 = rgbtransh_DR219SSE2;
          }
          else
          {
            *(_QWORD *)&v137 = rgbtrans24bitout2;
            v138 = (__int64 (__fastcall *)(int, int, int, int, __int64, int))rgbtransRGB888FulloutSSE2;
            *(_QWORD *)&v139 = rgbtrans24bitoutRight2;
            *((_QWORD *)&v139 + 1) = rgbtransYUY2FulloutRight;
            v140 = (__int64 (__fastcall *)(int, int, int, int, __int64, int))rgbtransRGB888FulloutRightSSE2;
            *(_QWORD *)&v131 = rgbtranshC;
            *((_QWORD *)&v131 + 1) = rgbtransYUY2FulloutRight;
            v57 = rgbtranshSSE2;
          }
          v132 = v57;
          v19 = 96;
          *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 8) = *v14;
          *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = *v145;
          *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = *v13;
          v53 = 3 * a6;
          goto LABEL_133;
        }
        v50 = v49 - 256;
        if ( v50 )
        {
          v51 = v50 - 512;
          if ( v51 )
          {
            v52 = v51 - 1024;
            if ( !v52 )
            {
              v19 = 32;
              *((_QWORD *)&v137 + 1) = rgbtransYUY2FulloutRight;
              *(_QWORD *)&v137 = rgbtrans8bitout2;
              *(_QWORD *)&v139 = rgbtrans8bitoutRight2;
              v140 = rgbtrans8bitoutRight2;
              *((_QWORD *)&v139 + 1) = rgbtransYUY2FulloutRight;
              *((_QWORD *)&v131 + 1) = rgbtransYUY2FulloutRight;
              v138 = rgbtrans8bitout2;
              *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 8) = *v14;
              v54 = *v15;
              v37 = v7 + 14;
              *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = v54;
              *(_QWORD *)&v131 = rgbtranshRGB242C;
              v132 = rgbtranshRGB242C;
              *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = *v13;
              *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) = a6;
              goto LABEL_134;
            }
            if ( v52 != 2304 )
              return 2147500037LL;
            *((_QWORD *)&v137 + 1) = rgbtransYUY2FulloutRight;
            if ( (a5 & 0x100000) != 0 )
            {
              *(_QWORD *)&v137 = rgbtrans32bitout2_DR219;
              *(_QWORD *)&v139 = rgbtrans32bitoutRight2_DR219;
              v140 = rgbtrans32bitoutRight2_DR219;
              *((_QWORD *)&v139 + 1) = rgbtransYUY2FulloutRight;
              v138 = rgbtrans32bitout2_DR219;
              *(_QWORD *)&v131 = rgbtranshC32bit_DR219;
              v132 = rgbtranshC32bit_DR219;
            }
            else
            {
              *(_QWORD *)&v137 = rgbtrans32bitout2;
              *((_QWORD *)&v139 + 1) = rgbtransYUY2FulloutRight;
              v138 = rgbtrans32bitout2;
              *(_QWORD *)&v131 = rgbtranshC32bit;
              v132 = rgbtranshC32bit;
              *(_QWORD *)&v139 = rgbtrans32bitoutRight2;
              v140 = rgbtrans32bitoutRight2;
            }
            *((_QWORD *)&v131 + 1) = rgbtransYUY2FulloutRight;
            v19 = 128;
            *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 8) = *v14;
            *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = *v145;
            *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = *v13;
            v53 = 4 * a6;
LABEL_133:
            v37 = v7 + 14;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) = v53;
LABEL_134:
            v58 = *v37 * v24;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C) = v58;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xCC) = 6 * v58;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x44) = v58;
            v59 = 0;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = 0;
            do
            {
              *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 4 * v59 + 0x48) = *(_DWORD *)(((a7 + 63)
                                                                                             & 0xFFFFFFFFFFFFFFC0uLL)
                                                                                            + 0x3C)
                                                                                + *(_DWORD *)(((a7 + 63)
                                                                                             & 0xFFFFFFFFFFFFFFC0uLL)
                                                                                            + 4 * v59
                                                                                            + 0x44);
              ++v59;
            }
            while ( v59 != 4 );
            v60 = v19 + *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x54);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x58) = v60;
            v61 = v60 - *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x5C) = v61;
            v62 = v61 - *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x60) = v62;
            v63 = v62 - *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x64) = v63;
            v64 = v63 - *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x68) = v64;
            v65 = v64 - *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x6C) = v65;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x70) = v65 + v19;
            v66 = *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C) + v19 + v65;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x74) = v66;
            v67 = v66 + *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x78) = v67;
            v68 = v67 + *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x7C) = v68;
            v69 = v68 + *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) = v69;
            v70 = v69 + *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x84) = v70;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x88) = v70 + v19;
            v71 = v70 - *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C) + v19;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x8C) = v71;
            v72 = v71 - *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x90) = v72;
            v73 = v72 - *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x94) = v73;
            v74 = v73 - *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x98) = v74;
            v75 = v74 - *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x9C) = v75;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xA0) = v75 + v19;
            v76 = *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C) + v19 + v75;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xA4) = v76;
            v77 = v76 + *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xA8) = v77;
            v78 = v77 + *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xAC) = v78;
            v79 = v78 + *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x3C);
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xB0) = v79;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xB4) = *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL)
                                                                                + 0x3C)
                                                                    + v79;
            v80 = *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xCC);
            if ( v80 < 0 )
              v81 = *v37 - *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xE4) * v80;
            else
              v81 = 0;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xC4) = v81;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xBC) = 4 * v19 + v81;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xB8) = 9 * v19 + v81;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xC0) = v81 + 13 * v19;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xC8) = v81 + 18 * v19;
            v82 = 92;
            if ( *v37 <= 0 )
              v82 = -92;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x25A4) = v82;
            v83 = v24 * v82;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x258C) = 6 * v83;
            v84 = 0;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2500) = 0;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2504) = v83;
            do
            {
              *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 4 * v84 + 0x2508) = v83
                                                                                  + *(_DWORD *)(((a7 + 63)
                                                                                               & 0xFFFFFFFFFFFFFFC0uLL)
                                                                                              + 4 * v84
                                                                                              + 0x2504);
              ++v84;
            }
            while ( v84 != 4 );
            v85 = *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2514) + 4;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2518) = v85;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x251C) = v85 - v83;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2520) = v85 - 2 * v83;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2524) = v85 - 3 * v83;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2528) = v85 - 4 * v83;
            v86 = v85 - 5 * v83;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x252C) = v86;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2530) = v86 + 4;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2534) = v83 + v86 + 4;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2538) = v86 + 2 * v83 + 4;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x253C) = v86 + 3 * v83 + 4;
            v87 = v86 + 4 + 4 * v83;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2540) = v87;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2544) = v87 + v83;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2548) = v87 + v83 + 4;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x254C) = v87 + 4;
            v88 = 4 - 2 * v83;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2550) = v87 - v83 + 4;
            v89 = v88 + v87;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2554) = v88 + v87;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x255C) = v88 + v87 - 2 * v83;
            v90 = v88 + v87 - v83;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2558) = v90;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2560) = v89 + v88;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2564) = v90 + 4;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2568) = v89 + 4;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x256C) = v89 + 4 + v83;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2570) = v89 + 4 + 2 * v83;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2574) = v89 + 4 + 3 * v83;
            v91 = *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x25A4);
            if ( v91 < 0 )
              v92 = v91 * (1 - 6 * *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0xE4) * v24);
            else
              v92 = 0;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2584) = v92;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x257C) = v92 + 16;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2578) = v92 + 36;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2580) = v92 + 52;
            *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x2588) = v92 + 72;
            goto LABEL_250;
          }
          *((_QWORD *)&v137 + 1) = rgbtransYUY2FulloutRight;
          v55 = rgbtrans16bit0out2;
          *(_QWORD *)&v139 = rgbtrans16bit0outRight2;
          v56 = rgbtranshRGB555C;
          v140 = rgbtrans16bit0outRight2;
          *((_QWORD *)&v139 + 1) = rgbtransYUY2FulloutRight;
        }
        else
        {
          *((_QWORD *)&v137 + 1) = rgbtransYUY2FulloutRight;
          v55 = rgbtrans16bit1out2;
          *(_QWORD *)&v139 = rgbtrans16bit1outRight2;
          v56 = rgbtranshRGB565C;
          v140 = rgbtrans16bit1outRight2;
          *((_QWORD *)&v139 + 1) = rgbtransYUY2FulloutRight;
        }
        v132 = v56;
        v138 = v55;
        *((_QWORD *)&v131 + 1) = rgbtransYUY2FulloutRight;
      }
      else
      {
        *((_QWORD *)&v137 + 1) = rgbtransYUY2FulloutRight;
        v55 = rgbtransUYVYout2;
        v138 = (__int64 (__fastcall *)(int, int, int, int, __int64, int))rgbtransUYVYFulloutSSE2;
        v56 = rgbtranshUYVYC;
        *(_QWORD *)&v139 = rgbtransUYVYoutRight2;
        *((_QWORD *)&v139 + 1) = rgbtransYUY2FulloutRight;
        v140 = (__int64 (__fastcall *)(int, int, int, int, __int64, int))rgbtransUYVYFulloutRightSSE2;
        *((_QWORD *)&v131 + 1) = rgbtransYUY2FulloutRight;
        v132 = rgbtranshUYVYSSE2;
      }
      *(_QWORD *)&v137 = v55;
      *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 8) = *v14;
      *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = *v15;
      *(_QWORD *)&v131 = v56;
      *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = *v13;
    }
    else
    {
      *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = 0;
      *((_QWORD *)&v137 + 1) = rgbtransYUY2FulloutRight;
      *(_QWORD *)&v137 = rgbtransYUY2out2;
      v138 = (__int64 (__fastcall *)(int, int, int, int, __int64, int))rgbtransYUY2FulloutSSE2;
      *(_QWORD *)&v139 = rgbtransYUY2outRight2;
      *((_QWORD *)&v139 + 1) = rgbtransYUY2FulloutRight;
      v140 = (__int64 (__fastcall *)(int, int, int, int, __int64, int))rgbtransYUY2FulloutRightSSE2;
      *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 8) = *v14;
      *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = *v15;
    }
    v19 = 64;
    v53 = 2 * a6;
    goto LABEL_133;
  }
  v23 = v22 - 1;
  if ( !v23 )
  {
    if ( (unsigned int)(a6 + 359) <= 0x2CE )
      return 2147500037LL;
    *(_QWORD *)&v156 = decode360;
    *((_QWORD *)&v156 + 1) = rgbtransYUY2FulloutRight;
    v157 = rgbtransYUY2FulloutRight;
    if ( (a5 & 0x1FC0) == 0x40 )
    {
      v38 = 0;
      *((_QWORD *)&v133 + 1) = rgbtransYUY2FulloutRight;
      v39 = rgbtransYUY2out2;
      *(_QWORD *)&v135 = rgbtransYUY2outRight2;
      v136 = rgbtransYUY2outRight2;
      *((_QWORD *)&v135 + 1) = rgbtransYUY2FulloutRight;
    }
    else
    {
      switch ( a5 & 0x1FC0 )
      {
        case 128:
          *((_QWORD *)&v133 + 1) = rgbtransYUY2FulloutRight;
          v39 = (__int64 (__fastcall *)())rgbtransUYVYout2;
          *(_QWORD *)&v135 = rgbtransUYVYoutRight2;
          v40 = rgbtranshUYVYC;
          v136 = (__int64 (__fastcall *)())rgbtransUYVYoutRight2;
          *((_QWORD *)&v135 + 1) = rgbtransYUY2FulloutRight;
          break;
        case 256:
          *((_QWORD *)&v133 + 1) = rgbtransYUY2FulloutRight;
          if ( (a5 & 0x100000) != 0 )
          {
            *(_QWORD *)&v133 = rgbtrans24bitout2_DR219;
            *(_QWORD *)&v135 = rgbtrans24bitoutRight2_DR219;
            v136 = (__int64 (__fastcall *)())rgbtrans24bitoutRight2_DR219;
            *((_QWORD *)&v135 + 1) = rgbtransYUY2FulloutRight;
            v134 = rgbtrans24bitout2_DR219;
            *(_QWORD *)&v131 = rgbtranshC_DR219;
            v132 = rgbtranshC_DR219;
          }
          else
          {
            *(_QWORD *)&v133 = rgbtrans24bitout2;
            *((_QWORD *)&v135 + 1) = rgbtransYUY2FulloutRight;
            v134 = rgbtrans24bitout2;
            *(_QWORD *)&v131 = rgbtranshC;
            v132 = rgbtranshC;
            *(_QWORD *)&v135 = rgbtrans24bitoutRight2;
            v136 = (__int64 (__fastcall *)())rgbtrans24bitoutRight2;
          }
          *((_QWORD *)&v131 + 1) = rgbtransYUY2FulloutRight;
          v11 = 3 * a6;
          v38 = *v13;
          v19 = 48;
          goto LABEL_104;
        case 512:
          *((_QWORD *)&v133 + 1) = rgbtransYUY2FulloutRight;
          v39 = (__int64 (__fastcall *)())rgbtrans16bit1out2;
          *(_QWORD *)&v135 = rgbtrans16bit1outRight2;
          v40 = rgbtranshRGB565C;
          v136 = (__int64 (__fastcall *)())rgbtrans16bit1outRight2;
          *((_QWORD *)&v135 + 1) = rgbtransYUY2FulloutRight;
          break;
        case 1024:
          *((_QWORD *)&v133 + 1) = rgbtransYUY2FulloutRight;
          v39 = (__int64 (__fastcall *)())rgbtrans16bit0out2;
          *(_QWORD *)&v135 = rgbtrans16bit0outRight2;
          v40 = rgbtranshRGB555C;
          v136 = (__int64 (__fastcall *)())rgbtrans16bit0outRight2;
          *((_QWORD *)&v135 + 1) = rgbtransYUY2FulloutRight;
          break;
        case 2048:
          *(_QWORD *)&v131 = rgbtranshRGB242C;
          *((_QWORD *)&v133 + 1) = rgbtransYUY2FulloutRight;
          v39 = (__int64 (__fastcall *)())rgbtrans8bitout2;
          v132 = rgbtranshRGB242C;
          *(_QWORD *)&v135 = rgbtrans8bitoutRight2;
          v136 = (__int64 (__fastcall *)())rgbtrans8bitoutRight2;
          *((_QWORD *)&v135 + 1) = rgbtransYUY2FulloutRight;
          *((_QWORD *)&v131 + 1) = rgbtransYUY2FulloutRight;
          v38 = *v13;
          goto LABEL_103;
        case 4352:
          *((_QWORD *)&v133 + 1) = rgbtransYUY2FulloutRight;
          if ( (a5 & 0x100000) != 0 )
          {
            *(_QWORD *)&v133 = rgbtrans32bitout2_DR219;
            *(_QWORD *)&v135 = rgbtrans32bitoutRight2_DR219;
            v136 = (__int64 (__fastcall *)())rgbtrans32bitoutRight2_DR219;
            *((_QWORD *)&v135 + 1) = rgbtransYUY2FulloutRight;
            v134 = rgbtrans32bitout2_DR219;
            *(_QWORD *)&v131 = rgbtranshC32bit_DR219;
            v132 = rgbtranshC32bit_DR219;
          }
          else
          {
            *(_QWORD *)&v133 = rgbtrans32bitout2;
            *((_QWORD *)&v135 + 1) = rgbtransYUY2FulloutRight;
            v134 = rgbtrans32bitout2;
            *(_QWORD *)&v131 = rgbtranshC32bit;
            v132 = rgbtranshC32bit;
            *(_QWORD *)&v135 = rgbtrans32bitoutRight2;
            v136 = (__int64 (__fastcall *)())rgbtrans32bitoutRight2;
          }
          *((_QWORD *)&v131 + 1) = rgbtransYUY2FulloutRight;
          v19 = 64;
          v38 = *v13;
          v11 = 4 * a6;
          goto LABEL_104;
        default:
          return 2147500037LL;
      }
      *(_QWORD *)&v131 = v40;
      v132 = v40;
      *((_QWORD *)&v131 + 1) = rgbtransYUY2FulloutRight;
      v38 = *v13;
    }
    v11 = 2 * a6;
    v19 = 32;
LABEL_103:
    *(_QWORD *)&v133 = v39;
    v134 = (__int64 (__fastcall *)(int, int, int, int, __int64, int))v39;
LABEL_104:
    v41 = v146;
    v24 = 4;
    v42 = v147;
    v37 = v7 + 14;
    v43 = v148;
    *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) = v11;
    v10 = *v41;
    v44 = *v42;
    *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 8) = *v43;
    *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = v44;
    *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = v38;
    goto LABEL_134;
  }
  v24 = 2;
  v25 = v23 - 2;
  if ( !v25 )
  {
    if ( (unsigned int)(a6 + 175) <= 0x15E )
      return 2147500037LL;
    switch ( a5 & 0x1FC0 )
    {
      case 64:
        v11 = 2 * a6;
        v29 = rgbtransYUY2outRight2;
        v27 = 0;
        v31 = rgbtransYUY2out2;
        break;
      case 128:
        v11 = 2 * a6;
        v27 = rgbtranshUYVYC;
        v29 = (__int64 (__fastcall *)())rgbtransUYVYoutRight2;
        v31 = (__int64 (__fastcall *)())rgbtransUYVYout2;
        break;
      case 256:
        v36 = a5 & 0x100000;
        v19 = 24;
        v27 = rgbtranshC_DR219;
        if ( (a5 & 0x100000) == 0 )
          v27 = rgbtranshC;
        v11 = 3 * a6;
        v34 = v36 == 0;
        v29 = (__int64 (__fastcall *)())rgbtrans24bitoutRight2_DR219;
        v35 = rgbtrans24bitout2;
        if ( !v36 )
          v29 = (__int64 (__fastcall *)())rgbtrans24bitoutRight2;
        v31 = (__int64 (__fastcall *)())rgbtrans24bitout2_DR219;
LABEL_73:
        if ( v34 )
          v31 = (__int64 (__fastcall *)())v35;
        break;
      case 512:
        v11 = 2 * a6;
        v27 = rgbtranshRGB565C;
        v29 = (__int64 (__fastcall *)())rgbtrans16bit1outRight2;
        v31 = (__int64 (__fastcall *)())rgbtrans16bit1out2;
        break;
      case 1024:
        v11 = 2 * a6;
        v27 = rgbtranshRGB555C;
        v29 = (__int64 (__fastcall *)())rgbtrans16bit0outRight2;
        v31 = (__int64 (__fastcall *)())rgbtrans16bit0out2;
        break;
      case 2048:
        v19 = 8;
        v27 = rgbtranshRGB242C;
        v29 = (__int64 (__fastcall *)())rgbtrans8bitoutRight2;
        v31 = (__int64 (__fastcall *)())rgbtrans8bitout2;
        break;
      case 4352:
        v33 = a5 & 0x100000;
        v19 = 32;
        v27 = rgbtranshC32bit_DR219;
        if ( (a5 & 0x100000) == 0 )
          v27 = rgbtranshC32bit;
        v11 = 4 * a6;
        v34 = v33 == 0;
        v29 = (__int64 (__fastcall *)())rgbtrans32bitoutRight2_DR219;
        v35 = rgbtrans32bitout2;
        if ( !v33 )
          v29 = (__int64 (__fastcall *)())rgbtrans32bitoutRight2;
        v31 = (__int64 (__fastcall *)())rgbtrans32bitout2_DR219;
        goto LABEL_73;
      default:
        return 2147500037LL;
    }
    v10 = decode180;
    goto LABEL_79;
  }
  if ( v25 != 4 || (unsigned int)(a6 + 87) <= 0xAE )
    return 2147500037LL;
  switch ( a5 & 0x1FC0 )
  {
    case 64:
      v11 = 2 * a6;
      v29 = rgbtransYUY2outRight2;
      v27 = 0;
      v31 = rgbtransYUY2out2;
      goto LABEL_50;
    case 128:
      v11 = 2 * a6;
      v27 = rgbtranshUYVYC;
      v29 = (__int64 (__fastcall *)())rgbtransUYVYoutRight2;
      v31 = (__int64 (__fastcall *)())rgbtransUYVYout2;
      goto LABEL_50;
    case 256:
      v32 = a5 & 0x100000;
      v19 = 12;
      v27 = rgbtranshC_DR219;
      if ( (a5 & 0x100000) == 0 )
        v27 = rgbtranshC;
      v28 = v32 == 0;
      v29 = (__int64 (__fastcall *)())rgbtrans24bitoutRight2_DR219;
      v11 = 3 * a6;
      if ( !v32 )
        v29 = (__int64 (__fastcall *)())rgbtrans24bitoutRight2;
      v30 = rgbtrans24bitout2;
      v31 = (__int64 (__fastcall *)())rgbtrans24bitout2_DR219;
      goto LABEL_45;
    case 512:
      v11 = 2 * a6;
      v27 = rgbtranshRGB565C;
      v29 = (__int64 (__fastcall *)())rgbtrans16bit1outRight2;
      v31 = (__int64 (__fastcall *)())rgbtrans16bit1out2;
      goto LABEL_50;
    case 1024:
      v11 = 2 * a6;
      v27 = rgbtranshRGB555C;
      v29 = (__int64 (__fastcall *)())rgbtrans16bit0outRight2;
      v31 = (__int64 (__fastcall *)())rgbtrans16bit0out2;
LABEL_50:
      v19 = 8;
      goto LABEL_51;
    case 2048:
      v19 = 4;
      v27 = rgbtranshRGB242C;
      v29 = (__int64 (__fastcall *)())rgbtrans8bitoutRight2;
      v31 = (__int64 (__fastcall *)())rgbtrans8bitout2;
LABEL_51:
      v10 = decode88;
      v24 = 1;
LABEL_79:
      *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 8) = v31;
      v37 = v7 + 14;
      *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = v29;
      *(_QWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = v27;
      *(_DWORD *)(((a7 + 63) & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) = v11;
      goto LABEL_134;
    case 4352:
      v26 = a5 & 0x100000;
      v27 = rgbtranshC32bit_DR219;
      if ( (a5 & 0x100000) == 0 )
        v27 = rgbtranshC32bit;
      v11 = 4 * a6;
      v28 = v26 == 0;
      v29 = (__int64 (__fastcall *)())rgbtrans32bitoutRight2_DR219;
      v30 = rgbtrans32bitout2;
      if ( !v26 )
        v29 = (__int64 (__fastcall *)())rgbtrans32bitoutRight2;
      v31 = (__int64 (__fastcall *)())rgbtrans32bitout2_DR219;
LABEL_45:
      if ( v28 )
        v31 = (__int64 (__fastcall *)())v30;
      goto LABEL_51;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18000a064  mov     [rsp-8+arg_8], rbx
0x18000a069  mov     [rsp-8+arg_10], r8
0x18000a06e  mov     [rsp-8+arg_0], rcx
0x18000a073  push    rbp
0x18000a074  push    rsi
0x18000a075  push    rdi
0x18000a076  push    r12
0x18000a078  push    r13
0x18000a07a  push    r14
0x18000a07c  push    r15
0x18000a07e  lea     rbp, [rsp-80h]
0x18000a083  sub     rsp, 180h
0x18000a08a  mov     esi, [rbp+0B0h+arg_20]
0x18000a090  xor     eax, eax
0x18000a092  xorps   xmm0, xmm0
0x18000a095  mov     [rsp+1B0h+var_170], rax
0x18000a09a  xorps   xmm1, xmm1
0x18000a09d  mov     [rbp+0B0h+var_128], rax
0x18000a0a1  xor     r9d, r9d
0x18000a0a4  mov     [rbp+0B0h+var_110], rax
0x18000a0a8  mov     [rsp+1B0h+var_158], rax
0x18000a0ad  mov     [rsp+1B0h+var_140], rax
0x18000a0b2  mov     [rbp+0B0h+var_E0], rax
0x18000a0b6  mov     [rbp+0B0h+var_F8], rax
0x18000a0ba  mov     [rbp+0B0h+var_90], rax
0x18000a0be  mov     [rbp+0B0h+var_60], rax
0x18000a0c2  mov     [rbp+0B0h+var_78], rax
0x18000a0c6  mov     [rbp+0B0h+var_48], rax
0x18000a0ca  mov     [rbp+0B0h+var_34], r9d
0x18000a0ce  movups  [rsp+1B0h+var_180], xmm0
0x18000a0d3  movups  [rsp+1B0h+var_138], xmm1
0x18000a0d8  movups  [rbp+0B0h+var_120], xmm0
0x18000a0dc  movups  [rsp+1B0h+var_168], xmm1
0x18000a0e1  movups  [rsp+1B0h+var_150], xmm0
0x18000a0e6  movups  [rbp+0B0h+var_F0], xmm1
0x18000a0ea  movups  [rbp+0B0h+var_108], xmm0
0x18000a0ee  movups  [rbp+0B0h+var_A0], xmm1
0x18000a0f2  movups  [rbp+0B0h+var_70], xmm0
0x18000a0f6  movups  [rbp+0B0h+var_88], xmm1
0x18000a0fa  movups  [rbp+0B0h+var_58], xmm0
0x18000a0fe  test    esi, esi
0x18000a100  jz      loc_18000B813
0x18000a106  test    edx, edx
0x18000a108  jz      loc_18000B813
0x18000a10e  mov     rbx, [rbp+0B0h+arg_30]
0x18000a115  lea     eax, [rdx-1]
0x18000a118  add     rbx, 3Fh ; '?'
0x18000a11c  mov     [rbp+0B0h+var_38], eax
0x18000a11f  and     rbx, 0FFFFFFFFFFFFFFC0h
0x18000a123  mov     [rbp+0B0h+var_40], rcx
0x18000a127  lea     r14d, [r9+1]
0x18000a12b  lea     r15, [rbx+25A8h]
0x18000a132  lea     r13, [rbx+69DACh]
0x18000a139  cmp     [rbx], r14b
0x18000a13c  jz      short loc_18000A145
0x18000a13e  mov     [r15], r9d
0x18000a141  mov     [r13+0], r9d
0x18000a145  mov     r12, [rbx+20h]
0x18000a149  mov     edi, [rbp+0B0h+arg_28]
0x18000a14f  cmp     esi, [r15]
0x18000a152  jnz     short loc_18000A167
0x18000a154  cmp     edi, [r13+0]
0x18000a158  jnz     short loc_18000A167
0x18000a15a  cmp     [rbx], r14b
0x18000a15d  jnz     short loc_18000A167
0x18000a15f  mov     rdx, rcx
0x18000a162  jmp     loc_18000B800
0x18000a167  call    VLDecodeTableInit
0x18000a16c  mov     [rbx], r14b
0x18000a16f  mov     [r15], esi
0x18000a172  mov     [r13+0], edi
0x18000a176  test    esi, 22000h
0x18000a17c  jz      loc_18000B813
0x18000a182  bt      esi, 19h
0x18000a186  jnb     short loc_18000A1D4
0x18000a188  lea     rax, [rbp+0B0h+var_60]
0x18000a18c  lea     rcx, [rbp+0B0h+var_90]
0x18000a190  mov     [rbp+0B0h+var_D0], rax
0x18000a194  mov     [rbp+0B0h+var_B8], rcx
0x18000a198  lea     rax, [rsp+1B0h+var_140]
0x18000a19d  lea     rcx, [rbp+0B0h+var_48]
0x18000a1a1  mov     [rbp+0B0h+var_C8], rax
0x18000a1a5  mov     [rbp+0B0h+var_B0], rcx
0x18000a1a9  lea     rax, [rsp+1B0h+var_158]
0x18000a1ae  lea     rcx, [rbp+0B0h+var_F8]
0x18000a1b2  mov     [rbp+0B0h+var_C0], rax
0x18000a1b6  mov     [rbp+0B0h+var_A8], rcx
0x18000a1ba  lea     r8, [rsp+1B0h+var_170]
0x18000a1bf  lea     r13, [rbp+0B0h+var_128]
0x18000a1c3  lea     r11, [rbp+0B0h+var_110]
0x18000a1c7  lea     r15, [rbp+0B0h+var_78]
0x18000a1cb  lea     rdx, [rbp+0B0h+var_E0]
0x18000a1cf  jmp     loc_18000A26B
0x18000a1d4  bt      esi, 18h
0x18000a1d8  jnb     short loc_18000A223
0x18000a1da  lea     rax, [rbp+0B0h+var_70+8]
0x18000a1de  lea     rcx, [rbp+0B0h+var_A0+8]
0x18000a1e2  mov     [rbp+0B0h+var_D0], rax
0x18000a1e6  mov     [rbp+0B0h+var_B8], rcx
0x18000a1ea  lea     rax, [rsp+1B0h+var_150+8]
0x18000a1ef  lea     rcx, [rbp+0B0h+var_58+8]
0x18000a1f3  mov     [rbp+0B0h+var_C8], rax
0x18000a1f7  mov     [rbp+0B0h+var_B0], rcx
0x18000a1fb  lea     rax, [rsp+1B0h+var_168+8]
0x18000a200  lea     rcx, [rbp+0B0h+var_108+8]
0x18000a204  mov     [rbp+0B0h+var_C0], rax
0x18000a208  mov     [rbp+0B0h+var_A8], rcx
0x18000a20c  lea     r8, [rsp+1B0h+var_180+8]
0x18000a211  lea     r13, [rbp+0B0h+var_138+8]
0x18000a215  lea     r11, [rbp+0B0h+var_120+8]
0x18000a219  lea     r15, [rbp+0B0h+var_88+8]
0x18000a21d  lea     rdx, [rbp+0B0h+var_F0+8]
0x18000a221  jmp     short loc_18000A26B
0x18000a223  lea     rax, [rbp+0B0h+var_70]
0x18000a227  mov     [rbp+0B0h+var_D0], rax
0x18000a22b  lea     r8, [rsp+1B0h+var_180]
0x18000a230  lea     rax, [rsp+1B0h+var_150]
0x18000a235  mov     [rbp+0B0h+var_C8], rax
0x18000a239  lea     r13, [rsp+1B0h+var_138]
0x18000a23e  lea     rax, [rsp+1B0h+var_168]
0x18000a243  mov     [rbp+0B0h+var_C0], rax
0x18000a247  lea     r11, [rbp+0B0h+var_120]
0x18000a24b  lea     rax, [rbp+0B0h+var_A0]
0x18000a24f  mov     [rbp+0B0h+var_B8], rax
0x18000a253  lea     r15, [rbp+0B0h+var_88]
0x18000a257  lea     rax, [rbp+0B0h+var_58]
0x18000a25b  mov     [rbp+0B0h+var_B0], rax
0x18000a25f  lea     rdx, [rbp+0B0h+var_F0]
0x18000a263  lea     rax, [rbp+0B0h+var_108]
0x18000a267  mov     [rbp+0B0h+var_A8], rax
0x18000a26b  mov     r10d, 30h ; '0'
0x18000a271  mov     [rbp+0B0h+var_D8], r11
0x18000a275  mov     eax, esi
0x18000a277  and     eax, r10d
0x18000a27a  lea     r9d, [r10-20h]
0x18000a27e  lea     ecx, [r10-24h]
0x18000a282  cmp     eax, r9d
0x18000a285  jz      short loc_18000A294
0x18000a287  cmp     eax, 20h ; ' '
0x18000a28a  jnz     loc_18000B813
0x18000a290  mov     eax, ecx
0x18000a292  jmp     short loc_18000A299
0x18000a294  mov     eax, 0Ah
0x18000a299  mov     [rbx+0E4h], eax
0x18000a29f  mov     eax, esi
0x18000a2a1  and     eax, 0Fh
0x18000a2a4  test    esi, 20010h
0x18000a2aa  jz      loc_18000B113
0x18000a2b0  mov     r15d, 4
0x18000a2b6  sub     eax, r14d
0x18000a2b9  jz      loc_18000A985
0x18000a2bf  sub     eax, r14d
0x18000a2c2  jz      loc_18000A5DF
0x18000a2c8  lea     r10d, [r15-2]
0x18000a2cc  sub     eax, r10d
0x18000a2cf  jz      loc_18000A452
0x18000a2d5  cmp     eax, r15d
0x18000a2d8  jnz     loc_18000B813
0x18000a2de  lea     eax, [rdi+57h]
0x18000a2e1  cmp     eax, 0AEh
0x18000a2e6  jbe     loc_18000B813
0x18000a2ec  mov     eax, esi
0x18000a2ee  and     eax, 1FC0h
0x18000a2f3  sub     eax, 40h ; '@'
0x18000a2f6  jz      loc_18000A42B
0x18000a2fc  sub     eax, 40h ; '@'
0x18000a2ff  jz      loc_18000A412
0x18000a305  sub     eax, 80h
0x18000a30a  jz      loc_18000A3CC
0x18000a310  sub     eax, 100h
0x18000a315  jz      loc_18000A3B3
0x18000a31b  sub     eax, 200h
0x18000a320  jz      short loc_18000A397
0x18000a322  sub     eax, 400h
0x18000a327  jz      short loc_18000A37A
0x18000a329  cmp     eax, 900h
0x18000a32e  jnz     loc_18000B813
0x18000a334  and     esi, 100000h
0x18000a33a  lea     rax, rgbtranshC32bit
0x18000a341  lea     rcx, rgbtrans32bitoutRight2
0x18000a348  lea     rdx, rgbtranshC32bit_DR219
0x18000a34f  cmovz   rdx, rax
0x18000a353  lea     edi, ds:0[rdi*4]
0x18000a35a  test    esi, esi
0x18000a35c  lea     rax, rgbtrans32bitoutRight2_DR219
0x18000a363  lea     r11, rgbtrans32bitout2
0x18000a36a  cmovz   rax, rcx
0x18000a36e  lea     rcx, rgbtrans32bitout2_DR219
0x18000a375  jmp     loc_18000A40C
0x18000a37a  mov     r9d, r15d
0x18000a37d  lea     rdx, rgbtranshRGB242C
0x18000a384  lea     rax, rgbtrans8bitoutRight2
0x18000a38b  lea     rcx, rgbtrans8bitout2
0x18000a392  jmp     loc_18000A443
0x18000a397  add     edi, edi
0x18000a399  lea     rdx, rgbtranshRGB555C
0x18000a3a0  lea     rax, rgbtrans16bit0outRight2
0x18000a3a7  lea     rcx, rgbtrans16bit0out2
0x18000a3ae  jmp     loc_18000A43D
0x18000a3b3  add     edi, edi
0x18000a3b5  lea     rdx, rgbtranshRGB565C
0x18000a3bc  lea     rax, rgbtrans16bit1outRight2
0x18000a3c3  lea     rcx, rgbtrans16bit1out2
0x18000a3ca  jmp     short loc_18000A43D
0x18000a3cc  and     esi, 100000h
0x18000a3d2  lea     rax, rgbtranshC
0x18000a3d9  mov     r9d, ecx
0x18000a3dc  lea     rdx, rgbtranshC_DR219
0x18000a3e3  cmovz   rdx, rax
0x18000a3e7  lea     rcx, rgbtrans24bitoutRight2
0x18000a3ee  test    esi, esi
0x18000a3f0  lea     rax, rgbtrans24bitoutRight2_DR219
0x18000a3f7  lea     edi, [rdi+rdi*2]
0x18000a3fa  cmovz   rax, rcx
0x18000a3fe  lea     r11, rgbtrans24bitout2
0x18000a405  lea     rcx, rgbtrans24bitout2_DR219
0x18000a40c  cmovz   rcx, r11
0x18000a410  jmp     short loc_18000A443
0x18000a412  add     edi, edi
0x18000a414  lea     rdx, rgbtranshUYVYC
0x18000a41b  lea     rax, rgbtransUYVYoutRight2
0x18000a422  lea     rcx, rgbtransUYVYout2
0x18000a429  jmp     short loc_18000A43D
0x18000a42b  add     edi, edi
0x18000a42d  lea     rax, rgbtransYUY2outRight2
0x18000a434  xor     edx, edx
0x18000a436  lea     rcx, rgbtransYUY2out2
0x18000a43d  mov     r9d, 8
0x18000a443  lea     r12, decode88
0x18000a44a  mov     r10d, r14d
0x18000a44d  jmp     loc_18000A5C7
0x18000a452  lea     eax, [rdi+0AFh]
0x18000a458  cmp     eax, 15Eh
0x18000a45d  jbe     loc_18000B813
0x18000a463  mov     eax, esi
0x18000a465  and     eax, 1FC0h
0x18000a46a  sub     eax, 40h ; '@'
0x18000a46d  jz      loc_18000A5AE
0x18000a473  sub     eax, 40h ; '@'
0x18000a476  jz      loc_18000A595
0x18000a47c  sub     eax, 80h
0x18000a481  jz      loc_18000A54C
0x18000a487  sub     eax, 100h
0x18000a48c  jz      loc_18000A533
0x18000a492  sub     eax, 200h
0x18000a497  jz      short loc_18000A517
0x18000a499  sub     eax, 400h
0x18000a49e  jz      short loc_18000A4F7
0x18000a4a0  cmp     eax, 900h
0x18000a4a5  jnz     loc_18000B813
0x18000a4ab  and     esi, 100000h
0x18000a4b1  lea     rax, rgbtranshC32bit
0x18000a4b8  lea     rcx, rgbtrans32bitoutRight2
0x18000a4bf  mov     r9d, 20h ; ' '
0x18000a4c5  lea     rdx, rgbtranshC32bit_DR219
0x18000a4cc  cmovz   rdx, rax
0x18000a4d0  lea     edi, ds:0[rdi*4]
0x18000a4d7  test    esi, esi
0x18000a4d9  lea     rax, rgbtrans32bitoutRight2_DR219
0x18000a4e0  lea     r11, rgbtrans32bitout2
0x18000a4e7  cmovz   rax, rcx
0x18000a4eb  lea     rcx, rgbtrans32bitout2_DR219
0x18000a4f2  jmp     loc_18000A58F
0x18000a4f7  mov     r9d, 8
0x18000a4fd  lea     rdx, rgbtranshRGB242C
0x18000a504  lea     rax, rgbtrans8bitoutRight2
0x18000a50b  lea     rcx, rgbtrans8bitout2
0x18000a512  jmp     loc_18000A5C0
0x18000a517  add     edi, edi
0x18000a519  lea     rdx, rgbtranshRGB555C
0x18000a520  lea     rax, rgbtrans16bit0outRight2
0x18000a527  lea     rcx, rgbtrans16bit0out2
0x18000a52e  jmp     loc_18000A5C0
0x18000a533  add     edi, edi
0x18000a535  lea     rdx, rgbtranshRGB565C
0x18000a53c  lea     rax, rgbtrans16bit1outRight2
0x18000a543  lea     rcx, rgbtrans16bit1out2
0x18000a54a  jmp     short loc_18000A5C0
0x18000a54c  and     esi, 100000h
0x18000a552  lea     rax, rgbtranshC
0x18000a559  lea     rcx, rgbtrans24bitoutRight2
0x18000a560  mov     r9d, 18h
0x18000a566  lea     rdx, rgbtranshC_DR219
0x18000a56d  cmovz   rdx, rax
0x18000a571  lea     edi, [rdi+rdi*2]
0x18000a574  test    esi, esi
0x18000a576  lea     rax, rgbtrans24bitoutRight2_DR219
0x18000a57d  lea     r11, rgbtrans24bitout2
0x18000a584  cmovz   rax, rcx
0x18000a588  lea     rcx, rgbtrans24bitout2_DR219
0x18000a58f  cmovz   rcx, r11
0x18000a593  jmp     short loc_18000A5C0
0x18000a595  add     edi, edi
0x18000a597  lea     rdx, rgbtranshUYVYC
0x18000a59e  lea     rax, rgbtransUYVYoutRight2
0x18000a5a5  lea     rcx, rgbtransUYVYout2
0x18000a5ac  jmp     short loc_18000A5C0
0x18000a5ae  add     edi, edi
0x18000a5b0  lea     rax, rgbtransYUY2outRight2
0x18000a5b7  xor     edx, edx
  ... truncated ...
```
