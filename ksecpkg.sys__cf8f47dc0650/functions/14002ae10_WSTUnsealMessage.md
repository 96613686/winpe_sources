# WSTUnsealMessage

- ea: `0x14002ae10`
- end: `0x14002bbf8`
- name: `WSTUnsealMessage`
- size: `3560`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140029780`

## callees

- `0x140007008`
- `0x140010160`
- `0x140010240`
- `0x1400102c0`
- `0x1400261e0`
- `0x14002ae10`
- `0x14002bf1c`

## string_xrefs

- `0x14002b3e1`: `onecore\ds\security\protocols\pku2u\message.cxx`
- `0x14002af1f`: `Can't have readonly & readonly_w_checksum\n`
- `0x14002b395`: `Failed to verify signature token: %#x\n`
- `0x14002ba24`: `SpUnsealMessage tempered header\n`

## pseudocode

```c
__int64 __fastcall WSTUnsealMessage(__int64 a1, __int64 a2, int a3, _DWORD *a4)
{
  unsigned int *v4; // rbx
  __int64 v5; // r13
  unsigned int v6; // r10d
  unsigned int v7; // r14d
  unsigned int v8; // r9d
  __int64 v9; // r12
  unsigned int v10; // r11d
  _QWORD *v11; // rax
  unsigned int *v12; // rdx
  int v13; // ecx
  int v14; // r8d
  int v15; // ebx
  __int64 v16; // r12
  __int128 v18; // xmm0
  unsigned __int8 *v19; // rdi
  unsigned int v20; // r9d
  char *v21; // r14
  unsigned __int8 v22; // dl
  unsigned int v23; // r11d
  char v24; // dl
  __int16 v25; // r8
  unsigned __int16 v26; // si
  int v27; // ecx
  unsigned int v28; // edx
  unsigned int v29; // r15d
  unsigned int v30; // r12d
  size_t v31; // r13
  char v32; // bl
  __int16 *v33; // r13
  size_t v34; // r15
  size_t v35; // rbx
  __int16 *v36; // rcx
  char *v37; // r14
  char *v38; // rax
  unsigned __int64 v39; // rcx
  int v40; // edx
  char v41; // r8
  int v42; // ecx
  int v43; // edx
  unsigned int v44; // r9d
  int v45; // ecx
  int v46; // eax
  char v47; // r15
  int v48; // eax
  unsigned __int8 *v49; // rdi
  int v50; // esi
  int v51; // r15d
  unsigned __int64 v52; // rdx
  int v53; // eax
  unsigned __int64 v54; // rdx
  size_t v55; // rsi
  unsigned int i; // r12d
  __int64 v57; // rcx
  __int64 v58; // r13
  int v59; // edx
  unsigned int v60; // r8d
  char *v61; // r10
  int v62; // r12d
  unsigned int v63; // ebx
  unsigned int v64; // r11d
  unsigned int v65; // r15d
  unsigned int v66; // r12d
  char v67; // dl
  int v68; // ecx
  int v69; // r9d
  int v70; // ecx
  unsigned __int8 *v71; // rsi
  __int64 v72; // rbx
  char v73; // cl
  int v74; // edx
  int v75; // r8d
  int v76; // ecx
  unsigned __int64 v77; // rdx
  int v78; // ecx
  int v79; // ecx
  unsigned __int64 v80; // rcx
  unsigned __int64 v81; // rcx
  char v82; // r8
  unsigned __int8 *v83; // r9
  __int64 j; // rdx
  unsigned __int8 v85; // cl
  unsigned __int8 v86; // al
  int v87; // eax
  int v88; // eax
  unsigned __int64 v89; // rcx
  char v90; // r8
  unsigned __int8 *v91; // r9
  __int64 k; // rdx
  unsigned __int8 v93; // cl
  char v94; // al
  unsigned int v95; // r8d
  unsigned int v96; // ecx
  char v97; // [rsp+50h] [rbp-B0h]
  __int64 v98; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v99; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v100; // [rsp+68h] [rbp-98h]
  unsigned int v101; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v102; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 *v103; // [rsp+78h] [rbp-88h] BYREF
  __int128 v104; // [rsp+80h] [rbp-80h] BYREF
  int v105; // [rsp+90h] [rbp-70h] BYREF
  __int64 v106; // [rsp+98h] [rbp-68h] BYREF
  void *v107; // [rsp+A0h] [rbp-60h]
  __int128 *v108; // [rsp+A8h] [rbp-58h]
  __int64 v109; // [rsp+B0h] [rbp-50h]
  size_t Size; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v111; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v112; // [rsp+D0h] [rbp-30h]
  __int64 v113; // [rsp+D8h] [rbp-28h]
  _DWORD *v114; // [rsp+E0h] [rbp-20h]
  unsigned int *v115; // [rsp+E8h] [rbp-18h]
  __int128 v116; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE Src[96]; // [rsp+100h] [rbp+0h] BYREF
  __int16 v118; // [rsp+160h] [rbp+60h] BYREF
  __int64 v119; // [rsp+162h] [rbp+62h] BYREF
  int v120; // [rsp+16Ah] [rbp+6Ah]
  __int16 v121; // [rsp+16Eh] [rbp+6Eh]
  _OWORD v122[7]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v123[64]; // [rsp+1E0h] [rbp+E0h] BYREF

  v114 = a4;
  v4 = 0;
  v98 = 0;
  v5 = 0;
  v99 = 0;
  v109 = 0;
  v6 = 0;
  v102 = 0;
  v7 = 0;
  v106 = 0;
  v101 = 0;
  v8 = 0;
  v105 = 0;
  Size = 0;
  v103 = 0;
  v9 = a1;
  LODWORD(v107) = a3;
  v10 = *(_DWORD *)(a2 + 4);
  v115 = (unsigned int *)(a2 + 4);
  v11 = (_QWORD *)(a2 + 8);
  v112 = (_QWORD *)(a2 + 8);
  v108 = (__int128 *)a2;
  v113 = a1;
  v111 = 0;
  v104 = 0;
  v116 = 0;
  while ( v8 < v10 )
  {
    v12 = (unsigned int *)(*v11 + 16LL * v8);
    v13 = v12[1];
    v14 = v13 & 0x10000000;
    if ( v13 < 0 && v14 )
    {
      v15 = -2146893048;
      if ( !KsecInfoLevel )
        return (unsigned int)v15;
      KsecDebugOut(1, "Can't have readonly & readonly_w_checksum\n");
LABEL_15:
      v16 = v98;
LABEL_16:
      if ( v102 && v16 )
        (*(void (__fastcall **)(__int64 *))(v16 + 40))(&v102);
      goto LABEL_19;
    }
    if ( (v13 & 0xFFFFFFF) == 2 )
    {
      v4 = (unsigned int *)(*v11 + 16LL * v8);
    }
    else if ( (v13 & 0xFFFFFFF) == 0xA )
    {
      v6 = *v12;
      v109 = *v11 + 16LL * v8;
    }
    else if ( v13 >= 0 )
    {
      v6 += *v12;
      if ( !v14 )
        v7 += *v12;
    }
    v11 = v112;
    ++v8;
  }
  if ( v109 )
  {
    if ( v4 )
    {
      if ( KsecInfoLevel )
        KsecDebugOut(1, "Both stream and signature buffer present\n");
LABEL_27:
      v15 = -1073741811;
      goto LABEL_15;
    }
    v104 = *(_OWORD *)v109;
    v18 = v104;
    DWORD1(v104) = 1;
    v111 = v18;
    DWORD1(v111) = 2;
    if ( (int)v104 - 2 < 0
      || (v19 = (unsigned __int8 *)(*((_QWORD *)&v104 + 1) + 2LL),
          v103 = (unsigned __int8 *)(*((_QWORD *)&v104 + 1) + 2LL),
          (unsigned int)(v104 - 2) < 0xE)
      || (v20 = v104 - 16, (int)v104 - 16 < 0) )
    {
      LODWORD(v104) = 0;
    }
    else
    {
      LODWORD(v104) = v104 - 16;
      v21 = (char *)(*((_QWORD *)&v104 + 1) + 16LL);
      *((_QWORD *)&v104 + 1) += 16LL;
      if ( v20 )
      {
        v22 = *v19;
        v23 = *(_DWORD *)v109 - v20;
        v100 = v23;
        DWORD1(v116) = 1;
        *((_QWORD *)&v116 + 1) = &v104;
        v24 = v22 & 2;
        if ( v24 )
          v25 = v19[3] + (v19[2] << 8);
        else
          v25 = 0;
        v26 = v25 + (v24 != 0 ? 28 : 12);
        if ( v24 )
          v27 = v19[3] + (v19[2] << 8);
        else
          v27 = 0;
        if ( v6 < v27 + (v24 != 0 ? 60 : 28) )
        {
          if ( KsecInfoLevel )
            KsecDebugOut(
              1,
              "SpUnsealMessage Stream buffer message too small: total buffer %d, ExpectedRRC %d\n",
              v6,
              v26);
LABEL_41:
          v15 = -2146893041;
          goto LABEL_15;
        }
        v28 = ((v19[4] << 8) + (unsigned int)v19[5]) % (v6 - 16);
        if ( (unsigned __int16)v28 <= v26 )
        {
          if ( (unsigned __int16)v28 < v26 )
          {
            v33 = &v118;
            *((_QWORD *)&v111 + 1) = &v118;
            v19 = (unsigned __int8 *)&v119;
            v103 = (unsigned __int8 *)&v119;
            if ( v26 >= 0x80u || v23 > 128 - (unsigned __int64)v26 )
            {
              if ( KsecInfoLevel )
                KsecDebugOut(1, "signature too small\n");
              goto LABEL_54;
            }
            v34 = (unsigned __int16)v28;
            v35 = v26 - (unsigned __int64)(unsigned __int16)v28;
            v36 = *(__int16 **)(v109 + 8);
            v118 = *v36;
            v119 = *(_QWORD *)(v36 + 1);
            v120 = *(_DWORD *)(v36 + 5);
            v121 = v36[7];
            memmove(v122, &v21[v20 - v35], v35);
            if ( (unsigned int)v26 + 16 >= 0x80 )
            {
              if ( KsecInfoLevel )
                KsecDebugOut(1, "signature too small for the header\n");
              goto LABEL_54;
            }
            memmove((char *)v122 + v35, v21, v34);
            v37 = &v21[v34];
            *((_QWORD *)&v104 + 1) = v37;
            if ( (v119 & 2) == 0 )
              goto LABEL_66;
            v38 = v37 + 16;
            *(_OWORD *)((char *)v122 + v26) = *(_OWORD *)v37;
LABEL_65:
            *((_QWORD *)&v104 + 1) = v38;
LABEL_66:
            v108 = &v116;
            v4 = (unsigned int *)&v111;
            v19[4] = HIBYTE(v26);
            v19[5] = v26;
            if ( (*v19 & 2) != 0 )
              v40 = v19[3] + (v19[2] << 8);
            else
              v40 = 0;
            v7 = -12 - 2 * ((*v19 & 2) != 0 ? 0x10 : 0) - v40 + v104;
            LODWORD(v104) = v7;
            v41 = *v19 & 2;
            if ( v41 )
              v42 = v19[3] + (v19[2] << 8);
            else
              v42 = 0;
            v43 = v41 != 0 ? 44 : 12;
            v44 = v100 + v42 + v43;
            LODWORD(v111) = v44;
            if ( KsecInfoLevel )
            {
              if ( v41 )
                v45 = v19[3] + (v19[2] << 8);
              else
                v45 = 0;
              KsecDebugOut(
                16,
                "RRC %d, data buffer %p, cbdata %d, sig buffer %p, cbsig %d, overhead %d\n",
                v26,
                *((const void **)&v104 + 1),
                v7,
                v33,
                v44,
                v45 + v43);
              v7 = v104;
            }
            v9 = v113;
            goto LABEL_78;
          }
          v26 = ((v19[4] << 8) + (unsigned int)v19[5]) % (v6 - 16);
        }
        else
        {
          v29 = (unsigned __int16)v28 - v26;
          if ( (unsigned __int16)v28 != v26 && v20 > 1 )
          {
            v30 = 0;
            v31 = v20 - 1;
            do
            {
              v32 = *v21;
              memmove(v19 + 14, v19 + 15, v31);
              ++v30;
              v21[v31] = v32;
            }
            while ( v30 < v29 );
            v21 = (char *)*((_QWORD *)&v104 + 1);
            v19 = v103;
          }
        }
        if ( (*v19 & 2) != 0 )
          v39 = v19[3] + ((unsigned __int64)v19[2] << 8);
        else
          v39 = 0;
        v33 = (__int16 *)*((_QWORD *)&v111 + 1);
        v38 = &v21[v39 + ((*v19 & 2) != 0 ? 44LL : 12LL)];
        goto LABEL_65;
      }
    }
    if ( KsecInfoLevel )
      KsecDebugOut(1, "Failed to find header on stream buffer\n");
    goto LABEL_27;
  }
  if ( !v4 )
  {
    if ( KsecInfoLevel )
      KsecDebugOut(
        1,
        "No signature buffer found. %s, line %d\n",
        "onecore\\ds\\security\\protocols\\pku2u\\message.cxx",
        2075);
    goto LABEL_27;
  }
LABEL_78:
  v46 = WSTVerifySignatureToken(v9, v4, 1, (unsigned int)v107, &v103, &v105, (int *)&v101, &v99, &Size);
  v15 = v46;
  if ( v46 < 0 )
  {
    if ( KsecInfoLevel )
      KsecDebugOut(1, "Failed to verify signature token: %#x\n", v46);
    goto LABEL_55;
  }
  if ( v105 == -2147483647 )
  {
    v47 = 0;
    v97 = 0;
    v7 = 0;
  }
  else
  {
    v47 = 1;
    v97 = 1;
    if ( (*(_DWORD *)(v9 + 108) & 0x10) == 0 )
    {
      if ( KsecInfoLevel )
        KsecDebugOut(1, "Tried to decrypt using non-confidential context\n");
LABEL_94:
      v15 = -2146893054;
      goto LABEL_55;
    }
  }
  v5 = v99;
  v100 = *(_DWORD *)(v99 + 4);
  if ( v100 > 0x20 )
  {
    v15 = -1073741637;
    goto LABEL_15;
  }
  v48 = CDLocateCheckSum(v101, &v98);
  v15 = v48;
  if ( v48 < 0 )
  {
    if ( KsecInfoLevel )
      KsecDebugOut(1, "Failed to load MD5 checksum: %#x\n", v48);
    goto LABEL_15;
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(v98 + 48))(
          *(_QWORD *)(v9 + 80),
          *(unsigned int *)(v9 + 72),
          (*(_DWORD *)(v9 + 104) & 4) != 0 ? 24 : 22,
          &v102);
  if ( v15 < 0 )
    goto LABEL_15;
  v49 = v103;
  if ( v47 )
  {
    if ( (*v103 & 2) != 0 )
      v50 = v103[3] + (v103[2] << 8);
    else
      v50 = 0;
    v51 = (*v103 & 2) != 0 ? 0x10 : 0;
    v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(v5 + 40))(
            *(_QWORD *)(v9 + 80),
            *(unsigned int *)(v9 + 72),
            (*(_DWORD *)(v9 + 104) & 4) != 0 ? 24 : 22,
            &v106);
    if ( v15 < 0 )
      goto LABEL_15;
    v7 += v50 + v51;
    if ( (*v49 & 2) != 0 )
      v52 = v49[3] + ((unsigned __int64)v49[2] << 8);
    else
      v52 = 0;
    v53 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, unsigned __int8 *))(v5 + 104))(
            v106,
            v7,
            16,
            &v49[v52 + 26 + (-(__int64)((*v49 & 2) != 0) & 0x10)]);
    v16 = v98;
    v15 = v53;
    if ( v53 < 0 )
      goto LABEL_16;
    v54 = (*v49 & 2) != 0 ? v49[3] + ((unsigned __int64)v49[2] << 8) : 0LL;
    v15 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int8 *))(v98 + 24))(
            v102,
            16,
            &v49[v54 + 26 + (-(__int64)((*v49 & 2) != 0) & 0x10)]);
    if ( v15 < 0 )
      goto LABEL_16;
    v47 = v97;
  }
  v55 = 0;
  v107 = 0;
  for ( i = 0; ; ++i )
  {
    v101 = i;
    if ( i >= *((_DWORD *)v108 + 1) )
      break;
    v57 = *((_QWORD *)v108 + 1);
    v58 = 2LL * i;
    v59 = *(_DWORD *)(v57 + 16LL * i + 4);
    if ( (v59 & 0xFFFFFFF) != 2 && v59 >= 0 )
    {
      v60 = *(_DWORD *)(v57 + 16LL * i);
      if ( v60 )
      {
        if ( !v47 || (v59 & 0x10000000) != 0 )
        {
          v65 = *(_DWORD *)(v57 + 16LL * i);
          v103 = *(unsigned __int8 **)(v57 + 16LL * i + 8);
        }
        else
        {
          v61 = *(char **)(v57 + 16LL * i + 8);
          v62 = *(_DWORD *)(v57 + 16LL * i);
          v63 = v100;
          if ( (_DWORD)v55 )
          {
            v64 = v100 - v55;
            v62 = v55 + v60 - v100;
            v103 = (unsigned __int8 *)&v61[v100 - (unsigned int)v55];
          }
          else
          {
            v103 = *(unsigned __int8 **)(v57 + 8 * v58 + 8);
            v64 = v100;
          }
          v65 = v62 & -v100;
          v66 = v62 - v65;
          v67 = *v49 & 2;
          if ( v67 )
            v68 = v49[3] + (v49[2] << 8);
          else
            v68 = 0;
          v69 = v67 != 0 ? 0x10 : 0;
          if ( v68 + v69 == v100 && !v66 )
          {
            v70 = v67 ? v49[3] + (v49[2] << 8) : 0;
            if ( v7 == v65 + v70 + v69 )
            {
              v65 -= v100;
              v66 = v100;
            }
          }
          if ( (_DWORD)v55 )
          {
            if ( v64 > v60 )
            {
              if ( KsecInfoLevel )
                KsecDebugOut(1, "insufficient buffer size %d\n", v60);
              goto LABEL_94;
            }
            Size = v64;
            memmove(&Src[v55], v61, v64);
            v7 -= v63;
            v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _BYTE *))(v99 + 104))(v106, v7, v63, Src);
            if ( v15 < 0 )
              goto LABEL_55;
            v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(v98 + 24))(v102, v100, Src);
            if ( v15 < 0 )
              goto LABEL_55;
            memmove(v107, Src, v55);
            memmove(*(void **)(*((_QWORD *)v108 + 1) + 8 * v58 + 8), &Src[v55], Size);
          }
          v7 -= v65;
          v71 = v103;
          v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int8 *))(v99 + 104))(v106, v7, v65, v103);
          if ( v15 < 0 )
            goto LABEL_55;
          v72 = v66;
          memmove(Src, &v71[v65], v66);
          v55 = v66;
          i = v101;
          v107 = (void *)(*(unsigned int *)(*((_QWORD *)v108 + 1) + 8 * v58)
                        + *(_QWORD *)(*((_QWORD *)v108 + 1) + 8 * v58 + 8)
                        - v72);
        }
        v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int8 *))(v98 + 24))(v102, v65, v103);
        if ( v15 < 0 )
          goto LABEL_55;
      }
    }
    v47 = v97;
  }
  *((_WORD *)v49 + 2) = 0;
  if ( v47 )
  {
    v73 = *v49 & 2;
    if ( v73 )
      v74 = v49[3] + (v49[2] << 8);
    else
      v74 = 0;
    v75 = v73 != 0 ? 0x10 : 0;
    if ( (unsigned int)(v55 + v74 + v75) > 0x60 )
    {
      if ( KsecInfoLevel )
      {
        if ( v73 )
          v76 = v49[3] + (v49[2] << 8);
        else
          v76 = 0;
        KsecDebugOut(1, "ExtraCount %d\n", v76 + v75);
      }
LABEL_54:
      v15 = -1073741637;
LABEL_55:
      v5 = v99;
      goto LABEL_15;
    }
    if ( v73 )
      v77 = v49[3] + ((unsigned __int64)v49[2] << 8);
    else
      v77 = 0;
    memmove(&Src[(unsigned int)v55], v49 + 14, v77 + (v73 != 0 ? 0x10 : 0));
    v5 = v99;
    if ( (*v49 & 2) != 0 )
      v78 = v49[3] + (v49[2] << 8);
    else
      v78 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _BYTE *))(v99 + 104))(
            v106,
            0,
            (unsigned int)v55 + v78 + ((*v49 & 2) != 0 ? 0x10 : 0),
            Src);
    if ( v15 < 0 )
      goto LABEL_15;
    v79 = (*v49 & 2) != 0 ? v49[3] + (v49[2] << 8) : 0;
    v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(v98 + 24))(
            v102,
            (unsigned int)v55 + v79 + ((*v49 & 2) != 0 ? 0x10 : 0),
            Src);
    if ( v15 < 0 )
      goto LABEL_15;
    memmove(v107, Src, (unsigned int)v55);
    if ( (*v49 & 2) != 0 )
      v80 = v49[3] + ((unsigned __int64)v49[2] << 8);
    else
      v80 = 0;
    memmove(v49 + 14, &Src[(unsigned int)v55], v80 + ((*v49 & 2) != 0 ? 0x10 : 0));
    if ( (*v49 & 2) != 0 )
      v81 = v49[3] + ((unsigned __int64)v49[2] << 8);
    else
      v81 = 0;
    v82 = 0;
    v83 = &v49[v81];
    for ( j = 0; j != 16; ++j )
    {
      v85 = v49[j - 2];
      v86 = v83[j + 14];
      v82 |= v86 ^ v85;
    }
    if ( v82 )
    {
      if ( KsecInfoLevel )
        KsecDebugOut(1, "SpUnsealMessage tempered header\n");
      goto LABEL_41;
    }
    v16 = v98;
    LODWORD(v55) = 0;
    v47 = v97;
  }
  else
  {
    v16 = v98;
    *((_WORD *)v49 + 1) = 0;
    v87 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int8 *))(v16 + 24))(v102, 16, v49 - 2);
    v5 = v99;
    v15 = v87;
    if ( v87 < 0 )
      goto LABEL_16;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(v16 + 32))(v102, v123);
  if ( v15 < 0 )
    goto LABEL_16;
  v88 = (*(__int64 (__fastcall **)(__int64 *))(v16 + 40))(&v102);
  v102 = 0;
  v15 = v88;
  if ( v88 >= 0 )
  {
    if ( v47 && (_DWORD)v55 )
    {
      if ( KsecInfoLevel )
        KsecDebugOut(1, "Non-aligned buffer size to SealMessage: %d extra bytes\n", v55);
      v15 = -2146893048;
    }
    else
    {
      if ( (*v49 & 2) != 0 )
        v89 = v49[3] + ((unsigned __int64)v49[2] << 8);
      else
        v89 = 0;
      v90 = 0;
      v91 = &v49[v89 + ((*v49 & 2) != 0 ? 0x10 : 0)];
      for ( k = 0; k != 12; ++k )
      {
        v93 = v91[k + 14];
        v94 = v123[k];
        v90 |= v94 ^ v93;
      }
      v5 = v99;
      if ( v90 )
      {
        if ( KsecInfoLevel )
          KsecDebugOut(1, "SpUnsealMessage bad checksum\n");
        v15 = -2146893041;
      }
      else
      {
        if ( v114 )
          *v114 = v105;
        if ( v109 )
        {
          v95 = v49[3] + (v49[2] << 8);
          if ( v100 < v95 || (unsigned int)v104 < v95 )
          {
            if ( KsecInfoLevel )
              KsecDebugOut(1, "Bad padding: %d bytes\n", v95);
            v15 = -1073741811;
          }
          else
          {
            v96 = 0;
            LODWORD(v104) = v104 - v95;
            while ( v96 < *v115 )
            {
              if ( (*(_DWORD *)(*v112 + 16LL * v96 + 4) & 0xFFFFFFF) == 1 )
              {
                *(_OWORD *)(*v112 + 16LL * v96) = v104;
                goto LABEL_16;
              }
              ++v96;
            }
          }
        }
      }
    }
    goto LABEL_16;
  }
LABEL_19:
  if ( v106 && v5 )
    (*(void (__fastcall **)(__int64 *))(v5 + 64))(&v106);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14002ae10  push    rbp
0x14002ae12  push    rbx
0x14002ae13  push    rsi
0x14002ae14  push    rdi
0x14002ae15  push    r12
0x14002ae17  push    r13
0x14002ae19  push    r14
0x14002ae1b  push    r15
0x14002ae1d  lea     rbp, [rsp-138h]
0x14002ae25  sub     rsp, 238h
0x14002ae2c  mov     rax, cs:__security_cookie
0x14002ae33  xor     rax, rsp
0x14002ae36  mov     [rbp+170h+var_50], rax
0x14002ae3d  xor     eax, eax
0x14002ae3f  mov     [rbp+170h+var_190], r9
0x14002ae43  mov     ebx, eax
0x14002ae45  mov     [rsp+270h+var_218], rax
0x14002ae4a  mov     r13d, eax
0x14002ae4d  mov     [rsp+270h+var_210], rax
0x14002ae52  mov     [rbp+170h+var_1C0], rax
0x14002ae56  mov     r10d, eax
0x14002ae59  mov     [rsp+270h+var_200], rax
0x14002ae5e  mov     r14d, eax
0x14002ae61  mov     [rbp+170h+var_1D8], rax
0x14002ae65  lea     esi, [rbx+1]
0x14002ae68  mov     [rsp+270h+var_204], eax
0x14002ae6c  mov     r9d, eax
0x14002ae6f  mov     [rbp+170h+var_1E0], eax
0x14002ae72  xorps   xmm0, xmm0
0x14002ae75  mov     [rbp+170h+Size], rax
0x14002ae79  xorps   xmm1, xmm1
0x14002ae7c  mov     [rsp+270h+var_1F8], rax
0x14002ae81  mov     r12, rcx
0x14002ae84  lea     rax, [rdx+4]
0x14002ae88  mov     dword ptr [rbp+170h+var_1D0], r8d
0x14002ae8c  mov     r11d, [rax]
0x14002ae8f  mov     [rbp+170h+var_188], rax
0x14002ae93  lea     rax, [rdx+8]
0x14002ae97  mov     [rbp+170h+var_1A0], rax
0x14002ae9b  mov     [rbp+170h+var_1C8], rdx
0x14002ae9f  mov     [rbp+170h+var_198], rcx
0x14002aea3  movups  [rbp+170h+var_1B0], xmm0
0x14002aea7  movups  [rbp+170h+var_1F0], xmm1
0x14002aeab  movups  [rbp+170h+var_180], xmm0
0x14002aeaf  cmp     r9d, r11d
0x14002aeb2  jnb     loc_14002AF8D
0x14002aeb8  mov     edx, r9d
0x14002aebb  shl     rdx, 4
0x14002aebf  add     rdx, [rax]
0x14002aec2  mov     ecx, [rdx+4]
0x14002aec5  mov     r8d, ecx
0x14002aec8  and     r8d, 10000000h
0x14002aecf  test    ecx, ecx
0x14002aed1  jns     short loc_14002AED8
0x14002aed3  test    r8d, r8d
0x14002aed6  jnz     short loc_14002AF11
0x14002aed8  mov     eax, ecx
0x14002aeda  and     eax, 0FFFFFFFh
0x14002aedf  cmp     eax, 2
0x14002aee2  jnz     short loc_14002AEE9
0x14002aee4  mov     rbx, rdx
0x14002aee7  jmp     short loc_14002AF08
0x14002aee9  cmp     eax, 0Ah
0x14002aeec  jnz     short loc_14002AEF7
0x14002aeee  mov     r10d, [rdx]
0x14002aef1  mov     [rbp+170h+var_1C0], rdx
0x14002aef5  jmp     short loc_14002AF08
0x14002aef7  test    ecx, ecx
0x14002aef9  js      short loc_14002AF08
0x14002aefb  mov     eax, [rdx]
0x14002aefd  add     r10d, eax
0x14002af00  test    r8d, r8d
0x14002af03  jnz     short loc_14002AF08
0x14002af05  add     r14d, eax
0x14002af08  mov     rax, [rbp+170h+var_1A0]
0x14002af0c  add     r9d, esi
0x14002af0f  jmp     short loc_14002AEAF
0x14002af11  cmp     cs:KsecInfoLevel, r13d
0x14002af18  mov     ebx, 80090308h
0x14002af1d  jz      short loc_14002AF67
0x14002af1f  lea     rdx, aCanTHaveReadon; "Can't have readonly & readonly_w_checks"...
0x14002af26  mov     ecx, esi
0x14002af28  call    KsecDebugOut
0x14002af2d  mov     r12, [rsp+270h+var_218]
0x14002af32  cmp     [rsp+270h+var_200], 0
0x14002af38  jz      short loc_14002AF4E
0x14002af3a  test    r12, r12
0x14002af3d  jz      short loc_14002AF4E
0x14002af3f  mov     rax, [r12+28h]
0x14002af44  lea     rcx, [rsp+270h+var_200]
0x14002af49  call    _guard_dispatch_icall
0x14002af4e  cmp     [rbp+170h+var_1D8], 0
0x14002af53  jz      short loc_14002AF67
0x14002af55  test    r13, r13
0x14002af58  jz      short loc_14002AF67
0x14002af5a  mov     rax, [r13+40h]
0x14002af5e  lea     rcx, [rbp+170h+var_1D8]
0x14002af62  call    _guard_dispatch_icall
0x14002af67  mov     eax, ebx
0x14002af69  mov     rcx, [rbp+170h+var_50]
0x14002af70  xor     rcx, rsp; StackCookie
0x14002af73  call    __security_check_cookie
0x14002af78  add     rsp, 238h
0x14002af7f  pop     r15
0x14002af81  pop     r14
0x14002af83  pop     r13
0x14002af85  pop     r12
0x14002af87  pop     rdi
0x14002af88  pop     rsi
0x14002af89  pop     rbx
0x14002af8a  pop     rbp
0x14002af8b  retn
0x14002af8d  mov     rcx, [rbp+170h+var_1C0]
0x14002af91  mov     r15d, 10h
0x14002af97  test    rcx, rcx
0x14002af9a  jz      loc_14002B3C5
0x14002afa0  test    rbx, rbx
0x14002afa3  jz      short loc_14002AFC6
0x14002afa5  cmp     cs:KsecInfoLevel, r13d
0x14002afac  jz      short loc_14002AFBC
0x14002afae  lea     rdx, aBothStreamAndS; "Both stream and signature buffer presen"...
0x14002afb5  mov     ecx, esi
0x14002afb7  call    KsecDebugOut
0x14002afbc  mov     ebx, 0C000000Dh
0x14002afc1  jmp     loc_14002AF2D
0x14002afc6  movups  xmm0, xmmword ptr [rcx]
0x14002afc9  movdqu  [rbp+170h+var_1F0], xmm0
0x14002afce  mov     r9d, dword ptr [rbp+170h+var_1F0]
0x14002afd2  add     r9d, 0FFFFFFFEh
0x14002afd6  mov     dword ptr [rbp+170h+var_1F0+4], esi
0x14002afd9  movdqu  [rbp+170h+var_1B0], xmm0
0x14002afde  mov     dword ptr [rbp+170h+var_1B0+4], 2
0x14002afe5  js      loc_14002B3A8
0x14002afeb  mov     rdi, qword ptr [rbp+170h+var_1F0+8]
0x14002afef  add     rdi, 2
0x14002aff3  mov     [rsp+270h+var_1F8], rdi
0x14002aff8  cmp     r9d, 0Eh
0x14002affc  jb      loc_14002B3A8
0x14002b002  add     r9d, 0FFFFFFF2h
0x14002b006  js      loc_14002B3A8
0x14002b00c  mov     dword ptr [rbp+170h+var_1F0], r9d
0x14002b010  lea     r14, [rdi+0Eh]
0x14002b014  mov     qword ptr [rbp+170h+var_1F0+8], r14
0x14002b018  test    r9d, r9d
0x14002b01b  jz      loc_14002B3AC
0x14002b021  mov     r11d, [rcx]
0x14002b024  lea     rax, [rbp+170h+var_1F0]
0x14002b028  mov     dl, [rdi]
0x14002b02a  sub     r11d, r9d
0x14002b02d  mov     [rsp+270h+var_208], r11d
0x14002b032  mov     dword ptr [rbp+170h+var_180+4], esi
0x14002b035  mov     qword ptr [rbp+170h+var_180+8], rax
0x14002b039  and     dl, 2
0x14002b03c  jz      short loc_14002B056
0x14002b03e  movzx   r8d, byte ptr [rdi+2]
0x14002b043  mov     ecx, 100h
0x14002b048  movzx   eax, byte ptr [rdi+3]
0x14002b04c  imul    r8d, ecx
0x14002b050  add     r8w, ax
0x14002b054  jmp     short loc_14002B05C
0x14002b056  xor     eax, eax
0x14002b058  movzx   r8d, ax
0x14002b05c  mov     al, dl
0x14002b05e  neg     al
0x14002b060  sbb     si, si
0x14002b063  and     si, r15w
0x14002b067  add     si, 0Ch
0x14002b06b  add     si, r8w
0x14002b06f  test    dl, dl
0x14002b071  jz      short loc_14002B082
0x14002b073  movzx   ecx, byte ptr [rdi+2]
0x14002b077  movzx   eax, byte ptr [rdi+3]
0x14002b07b  shl     ecx, 8
0x14002b07e  add     ecx, eax
0x14002b080  jmp     short loc_14002B084
0x14002b082  xor     ecx, ecx
0x14002b084  neg     dl
0x14002b086  sbb     eax, eax
0x14002b088  and     eax, 20h
0x14002b08b  add     eax, 1Ch
0x14002b08e  add     eax, ecx
0x14002b090  cmp     r10d, eax
0x14002b093  jnb     short loc_14002B0C0
0x14002b095  cmp     cs:KsecInfoLevel, r13d
0x14002b09c  jz      short loc_14002B0B6
0x14002b09e  movzx   r9d, si
0x14002b0a2  lea     rdx, aSpunsealmessag_1; "SpUnsealMessage Stream buffer message t"...
0x14002b0a9  mov     r8d, r10d
0x14002b0ac  mov     ecx, 1
0x14002b0b1  call    KsecDebugOut
0x14002b0b6  mov     ebx, 8009030Fh
0x14002b0bb  jmp     loc_14002AF2D
0x14002b0c0  movzx   r8d, byte ptr [rdi+4]
0x14002b0c5  lea     ecx, [r10-10h]
0x14002b0c9  movzx   eax, byte ptr [rdi+5]
0x14002b0cd  xor     edx, edx
0x14002b0cf  shl     r8d, 8
0x14002b0d3  add     eax, r8d
0x14002b0d6  div     ecx
0x14002b0d8  cmp     dx, si
0x14002b0db  jbe     short loc_14002B12A
0x14002b0dd  movzx   r15d, dx
0x14002b0e1  movzx   eax, si
0x14002b0e4  sub     r15d, eax
0x14002b0e7  jz      loc_14002B227
0x14002b0ed  cmp     r9d, 1
0x14002b0f1  jbe     loc_14002B227
0x14002b0f7  xor     r12d, r12d
0x14002b0fa  lea     r13d, [r9-1]
0x14002b0fe  mov     bl, [r14]
0x14002b101  lea     rdx, [r14+1]; Src
0x14002b105  mov     r8, r13; Size
0x14002b108  mov     rcx, r14; void *
0x14002b10b  call    memmove
0x14002b110  inc     r12d
0x14002b113  mov     [r14+r13], bl
0x14002b117  cmp     r12d, r15d
0x14002b11a  jb      short loc_14002B0FE
0x14002b11c  mov     r14, qword ptr [rbp+170h+var_1F0+8]
0x14002b120  mov     rdi, [rsp+270h+var_1F8]
0x14002b125  jmp     loc_14002B227
0x14002b12a  movzx   r8d, si
0x14002b12e  jnb     loc_14002B224
0x14002b134  mov     eax, 80h
0x14002b139  lea     r13, [rbp+170h+var_110]
0x14002b13d  mov     qword ptr [rbp+170h+var_1B0+8], r13
0x14002b141  lea     rdi, [rbp+170h+var_10E]
0x14002b145  mov     [rsp+270h+var_1F8], rdi
0x14002b14a  cmp     si, ax
0x14002b14d  jnb     loc_14002B212
0x14002b153  mov     ecx, eax
0x14002b155  movzx   r12d, si
0x14002b159  sub     rcx, r12
0x14002b15c  mov     eax, r11d
0x14002b15f  cmp     rax, rcx
0x14002b162  ja      loc_14002B212
0x14002b168  mov     rcx, [rbp+170h+var_1C0]
0x14002b16c  mov     ebx, r8d
0x14002b16f  movzx   r15d, dx
0x14002b173  sub     rbx, r15
0x14002b176  mov     edx, r9d
0x14002b179  sub     rdx, rbx
0x14002b17c  mov     r8, rbx; Size
0x14002b17f  mov     rcx, [rcx+8]
0x14002b183  add     rdx, r14; Src
0x14002b186  movzx   eax, word ptr [rcx]
0x14002b189  mov     [rbp+170h+var_110], ax
0x14002b18d  mov     rax, [rcx+2]
0x14002b191  mov     [rbp+170h+var_10E], rax
0x14002b195  mov     eax, [rcx+0Ah]
0x14002b198  mov     [rbp+170h+var_106], eax
0x14002b19b  movzx   eax, word ptr [rcx+0Eh]
0x14002b19f  lea     rcx, [rbp+170h+var_100]; void *
0x14002b1a3  mov     [rbp+170h+var_102], ax
0x14002b1a7  call    memmove
0x14002b1ac  movzx   eax, si
0x14002b1af  add     eax, 10h
0x14002b1b2  cmp     eax, 80h
0x14002b1b7  jb      short loc_14002B1E2
0x14002b1b9  cmp     cs:KsecInfoLevel, 0
0x14002b1c0  jz      short loc_14002B1D3
0x14002b1c2  lea     rdx, aSignatureTooSm_0; "signature too small for the header\n"
0x14002b1c9  mov     ecx, 1
0x14002b1ce  call    KsecDebugOut
0x14002b1d3  mov     ebx, 0C00000BBh
0x14002b1d8  mov     r13, [rsp+270h+var_210]
0x14002b1dd  jmp     loc_14002AF2D
0x14002b1e2  lea     rcx, [rbp+170h+var_100]
0x14002b1e6  mov     r8, r15; Size
0x14002b1e9  add     rcx, rbx; void *
0x14002b1ec  mov     rdx, r14; Src
0x14002b1ef  call    memmove
0x14002b1f4  add     r14, r15
0x14002b1f7  test    byte ptr [rbp+170h+var_10E], 2
0x14002b1fb  mov     qword ptr [rbp+170h+var_1F0+8], r14
0x14002b1ff  jz      short loc_14002B25B
0x14002b201  movups  xmm0, xmmword ptr [r14]
0x14002b205  lea     rax, [r14+10h]
0x14002b209  movdqu  [rbp+r12+170h+var_100], xmm0
0x14002b210  jmp     short loc_14002B257
0x14002b212  cmp     cs:KsecInfoLevel, 0
0x14002b219  jz      short loc_14002B1D3
0x14002b21b  lea     rdx, aSignatureTooSm; "signature too small\n"
0x14002b222  jmp     short loc_14002B1C9
0x14002b224  movzx   esi, dx
0x14002b227  mov     dl, [rdi]
0x14002b229  and     dl, 2
0x14002b22c  jz      short loc_14002B23F
0x14002b22e  movzx   ecx, byte ptr [rdi+2]
0x14002b232  movzx   eax, byte ptr [rdi+3]
0x14002b236  shl     rcx, 8
0x14002b23a  add     rcx, rax
0x14002b23d  jmp     short loc_14002B241
0x14002b23f  xor     ecx, ecx
0x14002b241  mov     r13, qword ptr [rbp+170h+var_1B0+8]
0x14002b245  neg     dl
0x14002b247  sbb     rax, rax
0x14002b24a  and     eax, 20h
0x14002b24d  add     rax, 0Ch
0x14002b251  add     rax, rcx
  ... truncated ...
```
