# mp3ScaleFactorRead(CBitStream &,MP3SI_GRCH &,MP3SCF &,MPEG_INFO const &,int const *,int,int)

- ea: `0x180004ac0`
- end: `0x1800056b8`
- name: `?mp3ScaleFactorRead@@YAXAEAVCBitStream@@AEAUMP3SI_GRCH@@AEAUMP3SCF@@AEBUMPEG_INFO@@PEBHHH@Z`
- size: `3064`
- prototype: `void __usercall(struct CBitStream *this@<rcx>, struct MP3SI_GRCH *@<rdx>, struct MP3SCF *@<r8>, const struct MPEG_INFO *@<r9>, const int *, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003b80`

## callees

- `0x180004ac0`
- `0x180005f80`

## pseudocode

```c
void __fastcall mp3ScaleFactorRead(
        struct CBitStream *this,
        struct MP3SI_GRCH *a2,
        struct MP3SCF *a3,
        const struct MPEG_INFO *a4,
        const int *a5,
        int a6,
        int a7)
{
  int k; // ebp
  int v11; // r8d
  int v12; // r12d
  int v13; // r11d
  __int64 v14; // r14
  unsigned int v15; // r10d
  __int64 v16; // rax
  unsigned int v17; // ecx
  unsigned __int16 v18; // di
  int v19; // eax
  __int64 v20; // rdx
  int v21; // r11d
  __int64 v22; // r14
  unsigned int v23; // r10d
  __int64 v24; // rax
  unsigned int v25; // ecx
  unsigned __int16 v26; // di
  int v27; // eax
  __int64 v28; // rdx
  struct MP3SCF *v29; // rax
  __int64 v30; // rbp
  struct MP3SCF *v31; // rcx
  int v32; // r12d
  int *v33; // r14
  __int64 v34; // rdi
  int v35; // eax
  int v36; // r8d
  int v37; // r14d
  __int64 v38; // rbp
  __int64 v39; // r12
  __int64 *v40; // rcx
  struct MP3SCF *v41; // rax
  int v42; // r14d
  int v43; // r15d
  __int64 v44; // r12
  int v45; // ebp
  int v46; // r13d
  __int64 v47; // rdi
  char v48; // al
  int v49; // r8d
  int v50; // r8d
  int v51; // ebp
  struct MP3SCF *v52; // r15
  __int64 v53; // r14
  int v54; // r15d
  int v55; // r12d
  int m; // r13d
  __int64 v57; // rdi
  __int64 *v58; // r12
  __int64 i; // r14
  __int64 j; // rbp
  int v61; // r8d
  unsigned int v62; // r15d
  int v63; // edi
  struct MP3SCF *v64; // r12
  int v65; // ecx
  int v66; // ebp
  int v67; // r13d
  int v68; // r12d
  __int64 v69; // rdi
  __int64 *v70; // r12
  __int64 v71; // r15
  int v72; // ebp
  unsigned int v73; // ecx
  int v74; // r12d
  int v75; // r13d
  __int64 v76; // rdi
  int Bits; // eax
  unsigned int v78; // edx
  int v79; // eax
  unsigned int v80; // edx
  int v81; // eax
  __int64 *v82; // [rsp+20h] [rbp-A8h]
  unsigned int v83[4]; // [rsp+28h] [rbp-A0h]
  struct MP3SCF *v84; // [rsp+38h] [rbp-90h]
  struct MP3SCF *v85; // [rsp+40h] [rbp-88h]
  struct MP3SCF *v86; // [rsp+48h] [rbp-80h]
  struct MP3SCF *v87; // [rsp+50h] [rbp-78h]
  struct MP3SCF *v88; // [rsp+58h] [rbp-70h]
  struct MP3SCF *v89; // [rsp+60h] [rbp-68h]
  struct MP3SCF *v90; // [rsp+68h] [rbp-60h]
  struct MP3SCF *v91; // [rsp+70h] [rbp-58h]
  struct MP3SCF *v92; // [rsp+78h] [rbp-50h]
  struct MP3SCF *v93; // [rsp+80h] [rbp-48h]

  *((_DWORD *)this + 8) = 0;
  if ( *((_BYTE *)a4 + 32) )
  {
    if ( *((_DWORD *)a2 + 4) && *((_DWORD *)a2 + 5) == 2 )
    {
      if ( *((_DWORD *)a2 + 6) )
      {
        *(_DWORD *)a3 = CBitStream::GetBits(this, dword_180015BE0[*((int *)a2 + 3)]);
        *((_DWORD *)a3 + 1) = CBitStream::GetBits(this, dword_180015BE0[*((int *)a2 + 3)]);
        *((_DWORD *)a3 + 2) = CBitStream::GetBits(this, dword_180015BE0[*((int *)a2 + 3)]);
        *((_DWORD *)a3 + 3) = CBitStream::GetBits(this, dword_180015BE0[*((int *)a2 + 3)]);
        *((_DWORD *)a3 + 4) = CBitStream::GetBits(this, dword_180015BE0[*((int *)a2 + 3)]);
        *((_DWORD *)a3 + 5) = CBitStream::GetBits(this, dword_180015BE0[*((int *)a2 + 3)]);
        *((_DWORD *)a3 + 6) = CBitStream::GetBits(this, dword_180015BE0[*((int *)a2 + 3)]);
        *((_DWORD *)a3 + 7) = CBitStream::GetBits(this, dword_180015BE0[*((int *)a2 + 3)]);
        for ( i = 3; i != 6; ++i )
        {
          *((_DWORD *)a3 + i + 23) = CBitStream::GetBits(this, dword_180015BE0[*((int *)a2 + 3)]);
          *((_DWORD *)a3 + i + 36) = CBitStream::GetBits(this, dword_180015BE0[*((int *)a2 + 3)]);
          *((_DWORD *)a3 + i + 49) = CBitStream::GetBits(this, dword_180015BE0[*((int *)a2 + 3)]);
        }
        for ( j = 6; j != 12; ++j )
        {
          *((_DWORD *)a3 + j + 23) = CBitStream::GetBits(this, dword_180015C20[*((int *)a2 + 3)]);
          *((_DWORD *)a3 + j + 36) = CBitStream::GetBits(this, dword_180015C20[*((int *)a2 + 3)]);
          *((_DWORD *)a3 + j + 49) = CBitStream::GetBits(this, dword_180015C20[*((int *)a2 + 3)]);
        }
        *((_DWORD *)a3 + 35) = 0;
        *((_DWORD *)a3 + 48) = 0;
        *((_DWORD *)a3 + 61) = 0;
        *((_DWORD *)a3 + 62) = 7;
        *((_DWORD *)a3 + 63) = 7;
        *((_DWORD *)a3 + 64) = 7;
        *((_DWORD *)a3 + 65) = 7;
        *((_DWORD *)a3 + 66) = 7;
        *((_DWORD *)a3 + 67) = 7;
        *((_DWORD *)a3 + 68) = 7;
        *((_DWORD *)a3 + 69) = 7;
        *((_DWORD *)a3 + 70) = 7;
        *((_DWORD *)a3 + 71) = 7;
        *((_DWORD *)a3 + 72) = 7;
        *((_DWORD *)a3 + 73) = 7;
        *((_DWORD *)a3 + 74) = 7;
        *((_DWORD *)a3 + 75) = 7;
        *((_DWORD *)a3 + 76) = 7;
        *((_DWORD *)a3 + 77) = 7;
        *((_DWORD *)a3 + 78) = 7;
        *((_DWORD *)a3 + 79) = 7;
        *((_DWORD *)a3 + 80) = 7;
        *((_DWORD *)a3 + 81) = 7;
        *((_DWORD *)a3 + 82) = 7;
        *((_DWORD *)a3 + 83) = 7;
        *((_DWORD *)a3 + 84) = 7;
      }
      else
      {
        v29 = 0;
        do
        {
          v30 = dword_180015BB4[(_QWORD)v29];
          v31 = (struct MP3SCF *)((char *)v29 + 1);
          v32 = dword_180015BB4[(_QWORD)v29 + 1];
          v85 = (struct MP3SCF *)((char *)v29 + 1);
          if ( (int)v30 < v32 )
          {
            v33 = &dword_180015BE0[16 * (_QWORD)v29];
            v34 = v30;
            do
            {
              *((_DWORD *)a3 + v34 + 23) = CBitStream::GetBits(this, v33[*((int *)a2 + 3)]);
              *((_DWORD *)a3 + v34 + 36) = CBitStream::GetBits(this, v33[*((int *)a2 + 3)]);
              LODWORD(v30) = v30 + 1;
              *((_DWORD *)a3 + v34++ + 49) = CBitStream::GetBits(this, v33[*((int *)a2 + 3)]);
            }
            while ( (int)v30 < v32 );
            v31 = v85;
          }
          v29 = v31;
        }
        while ( v31 != (struct MP3SCF *)2 );
        *((_DWORD *)a3 + 35) = 0;
        *((_DWORD *)a3 + 48) = 0;
        *((_DWORD *)a3 + 61) = 0;
      }
      *(_QWORD *)v83 = a3;
      v86 = a3;
      v84 = a3;
      v88 = a3;
      v89 = a3;
      v90 = a3;
      v91 = a3;
      v92 = a3;
      v93 = a3;
      v87 = a3;
      *((_DWORD *)a3 + 85) = 7;
      *((_DWORD *)a3 + 86) = 7;
      *((_DWORD *)a3 + 87) = 7;
      *((_DWORD *)a3 + 88) = 7;
      *((_DWORD *)a3 + 89) = 7;
      *((_DWORD *)a3 + 90) = 7;
      *((_DWORD *)a3 + 91) = 7;
      v85 = a3;
      *((_DWORD *)a3 + 92) = 7;
      *((_DWORD *)a3 + 93) = 7;
      *((_DWORD *)a3 + 94) = 7;
      *(_DWORD *)(*(_QWORD *)v83 + 380LL) = 7;
      *((_DWORD *)a3 + 96) = 7;
      *((_DWORD *)a3 + 97) = 7;
    }
    else
    {
      for ( k = 0; k < 4; ++k )
      {
        if ( !a6 || !a5[k] )
        {
          v11 = *(_DWORD *)&byte_180015BA0[4 * k];
          v12 = dword_180015BA4[k];
          if ( v11 < v12 )
          {
            if ( (unsigned int)k >= 2 )
            {
              do
              {
                v21 = *((_DWORD *)this + 9);
                v22 = *((_QWORD *)this + 6);
                v23 = dword_180015C20[*((int *)a2 + 3)];
                v24 = (v21 >> 3) & 0xFFFFFFFE;
                v25 = 16 - (v21 & 0xF);
                if ( v23 > v25 )
                  v26 = ((*(unsigned __int8 *)((unsigned int)(v24 + 1) + v22)
                        | (unsigned __int16)(*(unsigned __int8 *)(v24 + v22) << 8)) << (*((_BYTE *)this + 36) & 0xF))
                      | ((unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                                & (*((_DWORD *)this + 4) - 1))
                                                               + 1
                                                               + v22)
                                          | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                                 & (*((_DWORD *)this + 4) - 1))
                                                                + v22) << 8)) >> v25);
                else
                  v26 = (*(unsigned __int8 *)((unsigned int)(v24 + 1) + v22)
                       | (unsigned __int16)(*(unsigned __int8 *)(v24 + v22) << 8)) << (*((_BYTE *)this + 36) & 0xF);
                v27 = *((_DWORD *)this + 5);
                *((_DWORD *)this + 8) += v23;
                *((_DWORD *)this + 6) -= v23;
                *((_DWORD *)this + 9) = (v27 - 1) & (v21 + v23);
                v28 = v11++;
                *((_DWORD *)a3 + v28) = v26 >> (16 - v23);
              }
              while ( v11 < v12 );
            }
            else
            {
              do
              {
                v13 = *((_DWORD *)this + 9);
                v14 = *((_QWORD *)this + 6);
                v15 = dword_180015BE0[*((int *)a2 + 3)];
                v16 = (v13 >> 3) & 0xFFFFFFFE;
                v17 = 16 - (v13 & 0xF);
                if ( v15 > v17 )
                  v18 = ((*(unsigned __int8 *)((unsigned int)(v16 + 1) + v14)
                        | (unsigned __int16)(*(unsigned __int8 *)(v16 + v14) << 8)) << (*((_BYTE *)this + 36) & 0xF))
                      | ((unsigned __int16)(*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                                & (*((_DWORD *)this + 4) - 1))
                                                               + 1
                                                               + v14)
                                          | (*(unsigned __int8 *)(((((*((int *)this + 9) >> 3) & 0xFFFFFFFE) + 2)
                                                                 & (*((_DWORD *)this + 4) - 1))
                                                                + v14) << 8)) >> v17);
                else
                  v18 = (*(unsigned __int8 *)((unsigned int)(v16 + 1) + v14)
                       | (unsigned __int16)(*(unsigned __int8 *)(v16 + v14) << 8)) << (*((_BYTE *)this + 36) & 0xF);
                v19 = *((_DWORD *)this + 5);
                *((_DWORD *)this + 8) += v15;
                *((_DWORD *)this + 6) -= v15;
                *((_DWORD *)this + 9) = (v19 - 1) & (v13 + v15);
                v20 = v11++;
                *((_DWORD *)a3 + v20) = v18 >> (16 - v15);
              }
              while ( v11 < v12 );
            }
          }
        }
      }
      *(_QWORD *)((char *)a3 + 84) = 0;
      *((_DWORD *)a3 + 62) = 7;
      *((_DWORD *)a3 + 63) = 7;
      *((_DWORD *)a3 + 64) = 7;
      *((_DWORD *)a3 + 65) = 7;
      *((_DWORD *)a3 + 66) = 7;
      *((_DWORD *)a3 + 67) = 7;
      *((_DWORD *)a3 + 68) = 7;
      *((_DWORD *)a3 + 69) = 7;
      *((_DWORD *)a3 + 70) = 7;
      *((_DWORD *)a3 + 71) = 7;
      *((_DWORD *)a3 + 72) = 7;
      *((_DWORD *)a3 + 73) = 7;
      *((_DWORD *)a3 + 74) = 7;
      *((_DWORD *)a3 + 75) = 7;
      *((_DWORD *)a3 + 76) = 7;
      *((_DWORD *)a3 + 77) = 7;
      *((_DWORD *)a3 + 78) = 7;
      *((_DWORD *)a3 + 79) = 7;
      *((_DWORD *)a3 + 80) = 7;
      *((_DWORD *)a3 + 81) = 7;
      *((_DWORD *)a3 + 82) = 7;
      *((_DWORD *)a3 + 83) = 7;
      *((_DWORD *)a3 + 84) = 7;
    }
    return;
  }
  v35 = *((_DWORD *)a4 + 4);
  v36 = *((_DWORD *)a2 + 3);
  *((_DWORD *)a2 + 15) = 0;
  v37 = 3;
  *(_OWORD *)v83 = 0;
  if ( (v35 & 1) != 0 && a7 == 1 )
  {
    v48 = v36;
    v49 = v36 >> 1;
    *((_DWORD *)a2 + 18) = v48 & 1;
    if ( v49 < 180 )
    {
      v40 = qword_180014DD0;
      v38 = 9;
      v39 = 9;
      v83[0] = v49 / 36;
      v50 = v49 % 36;
      v83[1] = v50 / 6;
      v83[2] = v50 % 6;
      goto LABEL_34;
    }
    if ( v49 < 244 )
    {
      v38 = 12;
      v39 = 12;
      v83[0] = ((v49 - 180) >> 4) & 3;
      v83[1] = ((v49 - 180) >> 2) & 3;
      v83[2] = (v49 - 180) & 3;
      v40 = qword_180014E00;
      goto LABEL_34;
    }
    if ( v49 <= 255 )
    {
      v38 = 15;
      v39 = 15;
      v83[0] = (v49 - 244) / 3;
      v83[1] = (v49 - 244) % 3;
      v40 = qword_180014E30;
      goto LABEL_34;
    }
LABEL_33:
    v38 = 0;
    v39 = 0;
    v40 = qword_180014D40;
    goto LABEL_34;
  }
  *((_DWORD *)a2 + 18) = 0;
  if ( v36 < 400 )
  {
    v83[0] = (v36 >> 4) / 5;
    v83[1] = (v36 >> 4) % 5;
    v83[2] = (v36 >> 2) & 3;
    v83[3] = v36 & 3;
    goto LABEL_33;
  }
  if ( v36 >= 500 )
  {
    if ( v36 >= 512 )
      goto LABEL_33;
    *((_DWORD *)a2 + 15) = 1;
    v38 = 6;
    v39 = 6;
    v83[0] = (v36 - 500) / 3;
    v83[1] = (v36 - 500) % 3;
    v40 = qword_180014DA0;
  }
  else
  {
    v61 = v36 - 400;
    v38 = 3;
    v39 = 3;
    v83[0] = (v61 >> 2) / 5;
    v83[1] = (v61 >> 2) % 5;
    v83[2] = v61 & 3;
    v40 = qword_180014D70;
  }
LABEL_34:
  v82 = v40;
  if ( *((_DWORD *)a2 + 5) == 2 )
  {
    if ( *((_DWORD *)a2 + 6) )
    {
      v62 = v83[0];
      v63 = dword_180015BC0[v83[0]];
      *(_DWORD *)a3 = CBitStream::GetBits(this, v83[0]);
      *((_DWORD *)a3 + 62) = v63;
      *((_DWORD *)a3 + 1) = CBitStream::GetBits(this, v62);
      *((_DWORD *)a3 + 63) = v63;
      *((_DWORD *)a3 + 2) = CBitStream::GetBits(this, v62);
      *((_DWORD *)a3 + 64) = v63;
      *((_DWORD *)a3 + 3) = CBitStream::GetBits(this, v62);
      *((_DWORD *)a3 + 65) = v63;
      *((_DWORD *)a3 + 4) = CBitStream::GetBits(this, v62);
      *((_DWORD *)a3 + 66) = v63;
      *((_DWORD *)a3 + 5) = CBitStream::GetBits(this, v62);
      v64 = (struct MP3SCF *)(v38 + 2);
      *((_DWORD *)a3 + 67) = v63;
      v84 = (struct MP3SCF *)(v38 + 2);
      v65 = (LODWORD(qword_180014D40[2 * v38 + 4]) - 6) / 3;
      if ( v65 > 0 )
      {
        v66 = 0;
        v67 = v65;
        v68 = v63;
        do
        {
          v69 = v37;
          *((_DWORD *)a3 + v37 + 23) = CBitStream::GetBits(this, v62);
          *((_DWORD *)a3 + v37++ + 36) = CBitStream::GetBits(this, v62);
          *((_DWORD *)a3 + v69 + 49) = CBitStream::GetBits(this, v62);
          ++v66;
          *((_DWORD *)a3 + v69 + 85) = v68;
        }
        while ( v66 < v67 );
        v64 = v84;
      }
      v70 = &qword_180014D40[2 * (_QWORD)v64];
      v71 = 1;
      v84 = (struct MP3SCF *)v70;
      do
      {
        v72 = *((_DWORD *)v70 + v71) / 3;
        if ( v72 > 0 )
        {
          v74 = 0;
          LODWORD(v86) = v83[v71];
          v73 = (unsigned int)v86;
          v75 = dword_180015BC0[(int)v86];
          do
          {
            v76 = v37;
            Bits = CBitStream::GetBits(this, v73);
            v78 = v83[v71];
            *((_DWORD *)a3 + v37 + 23) = Bits;
            v79 = CBitStream::GetBits(this, v78);
            v80 = v83[v71];
            *((_DWORD *)a3 + v37 + 36) = v79;
            v81 = CBitStream::GetBits(this, v80);
            v73 = (unsigned int)v86;
            ++v37;
            ++v74;
            *((_DWORD *)a3 + v76 + 49) = v81;
            *((_DWORD *)a3 + v76 + 85) = v75;
          }
          while ( v74 < v72 );
          v70 = (__int64 *)v84;
        }
        ++v71;
      }
      while ( v71 != 4 );
    }
    else
    {
      v58 = &qword_180014D50[2 * v39];
      LODWORD(v84) = 0;
      v87 = (struct MP3SCF *)v58;
      v52 = 0;
      v85 = 0;
      do
      {
        v51 = *((_DWORD *)v58 + (_QWORD)v52) / 3;
        if ( v51 > 0 )
        {
          v53 = (int)v83[(_QWORD)v52];
          v54 = (int)v84;
          v55 = dword_180015BC0[v53];
          for ( m = 0; m < v51; ++m )
          {
            v57 = v54;
            *((_DWORD *)a3 + v54 + 23) = CBitStream::GetBits(this, v53);
            *((_DWORD *)a3 + v54++ + 36) = CBitStream::GetBits(this, v53);
            *((_DWORD *)a3 + v57 + 49) = CBitStream::GetBits(this, v53);
            *((_DWORD *)a3 + v57 + 85) = v55;
          }
          v58 = (__int64 *)v87;
          LODWORD(v84) = v54;
          v52 = v85;
        }
        v52 = (struct MP3SCF *)((char *)v52 + 1);
        v85 = v52;
      }
      while ( v52 != (struct MP3SCF *)4 );
    }
    *((_DWORD *)a3 + 35) = 0;
    *((_DWORD *)a3 + 48) = 0;
    *((_DWORD *)a3 + 61) = 0;
    *((_DWORD *)a3 + 97) = 1;
  }
  else
  {
    v41 = 0;
    v42 = 0;
    v85 = 0;
    do
    {
      v43 = *((_DWORD *)v40 + (_QWORD)v41);
      if ( v43 > 0 )
      {
        v44 = (int)v83[(_QWORD)v41];
        v45 = 0;
        v46 = dword_180015BC0[v44];
        do
        {
          v47 = v42++;
          *((_DWORD *)a3 + v47) = CBitStream::GetBits(this, v44);
          ++v45;
          *((_DWORD *)a3 + v47 + 62) = v46;
        }
        while ( v45 < v43 );
        v41 = v85;
        v40 = v82;
      }
      v41 = (struct MP3SCF *)((char *)v41 + 1);
      v85 = v41;
    }
    while ( v41 != (struct MP3SCF *)4 );
    *(_QWORD *)((char *)a3 + 84) = 0;
    *((_DWORD *)a3 + 83) = 1;
    *((_DWORD *)a3 + 84) = 1;
  }
}

```

## disassembly

```asm
0x180004ac0  mov     [rsp+arg_18], rbx
0x180004ac5  push    rbp
0x180004ac6  push    rsi
0x180004ac7  push    rdi
0x180004ac8  push    r12
0x180004aca  push    r13
0x180004acc  push    r14
0x180004ace  push    r15
0x180004ad0  sub     rsp, 90h
0x180004ad7  xor     edi, edi
0x180004ad9  mov     rsi, r8
0x180004adc  mov     [rcx+20h], edi
0x180004adf  mov     r15, rdx
0x180004ae2  mov     rbx, rcx
0x180004ae5  cmp     [r9+20h], dil
0x180004ae9  jz      loc_180004F25
0x180004aef  cmp     [rdx+10h], edi
0x180004af2  jnz     loc_180004D80
0x180004af8  mov     ebp, edi
0x180004afa  lea     r13, cs:180000000h
0x180004b01  cmp     [rsp+0C8h+arg_28], 0
0x180004b09  mov     r12d, ebp
0x180004b0c  lea     r8, ds:0[r12*4]
0x180004b14  jz      loc_180004BE6
0x180004b1a  mov     rax, [rsp+0C8h+arg_20]
0x180004b22  cmp     dword ptr [rax+r8], 0
0x180004b27  jz      loc_180004BE6
0x180004b2d  inc     ebp
0x180004b2f  cmp     ebp, 4
0x180004b32  jl      short loc_180004B01
0x180004b34  mov     eax, 7
0x180004b39  mov     qword ptr [rsi+54h], 0
0x180004b41  mov     [rsi+0F8h], eax
0x180004b47  mov     [rsi+0FCh], eax
0x180004b4d  mov     [rsi+100h], eax
0x180004b53  mov     [rsi+104h], eax
0x180004b59  mov     [rsi+108h], eax
0x180004b5f  mov     [rsi+10Ch], eax
0x180004b65  mov     [rsi+110h], eax
0x180004b6b  mov     [rsi+114h], eax
0x180004b71  mov     [rsi+118h], eax
0x180004b77  mov     [rsi+11Ch], eax
0x180004b7d  mov     [rsi+120h], eax
0x180004b83  mov     [rsi+124h], eax
0x180004b89  mov     [rsi+128h], eax
0x180004b8f  mov     [rsi+12Ch], eax
0x180004b95  mov     [rsi+130h], eax
0x180004b9b  mov     [rsi+134h], eax
0x180004ba1  mov     [rsi+138h], eax
0x180004ba7  mov     [rsi+13Ch], eax
0x180004bad  mov     [rsi+140h], eax
0x180004bb3  mov     [rsi+144h], eax
0x180004bb9  mov     [rsi+148h], eax
0x180004bbf  mov     [rsi+14Ch], eax
0x180004bc5  mov     [rsi+150h], eax
0x180004bcb  mov     rbx, [rsp+0C8h+arg_18]
0x180004bd3  add     rsp, 90h
0x180004bda  pop     r15
0x180004bdc  pop     r14
0x180004bde  pop     r13
0x180004be0  pop     r12
0x180004be2  pop     rdi
0x180004be3  pop     rsi
0x180004be4  pop     rbp
0x180004be5  retn
0x180004be6  mov     r8d, [r8+r13+15BA0h]
0x180004bee  mov     r12d, ds:rva dword_180015BA4[r13+r12*4]
0x180004bf6  cmp     r8d, r12d
0x180004bf9  jge     loc_180004B2D
0x180004bff  cmp     ebp, 2
0x180004c02  jnb     loc_180004CA0
0x180004c08  movsxd  rax, dword ptr [r15+0Ch]
0x180004c0c  mov     r11d, [rbx+24h]
0x180004c10  mov     edx, r11d
0x180004c13  mov     r14, [rbx+30h]
0x180004c17  and     edx, 0Fh
0x180004c1a  mov     ecx, edx
0x180004c1c  mov     r10d, ds:rva dword_180015BE0[r13+rax*4]
0x180004c24  mov     eax, r11d
0x180004c27  sar     eax, 3
0x180004c2a  and     eax, 0FFFFFFFEh
0x180004c2d  mov     edi, eax
0x180004c2f  movzx   r9d, byte ptr [rax+r14]
0x180004c34  inc     eax
0x180004c36  shl     r9w, 8
0x180004c3b  movzx   eax, byte ptr [rax+r14]
0x180004c40  or      r9w, ax
0x180004c44  shl     r9w, cl
0x180004c48  mov     ecx, 10h
0x180004c4d  sub     ecx, edx
0x180004c4f  cmp     r10d, ecx
0x180004c52  ja      loc_180004D2A
0x180004c58  movzx   edi, r9w
0x180004c5c  mov     eax, [rbx+14h]
0x180004c5f  lea     ecx, [r11+r10]
0x180004c63  add     [rbx+20h], r10d
0x180004c67  dec     eax
0x180004c69  sub     [rbx+18h], r10d
0x180004c6d  and     ecx, eax
0x180004c6f  mov     [rbx+24h], ecx
0x180004c72  mov     ecx, 10h
0x180004c77  sub     cl, r10b
0x180004c7a  movsxd  rdx, r8d
0x180004c7d  movzx   eax, di
0x180004c80  inc     r8d
0x180004c83  shr     eax, cl
0x180004c85  mov     [rsi+rdx*4], eax
0x180004c88  cmp     r8d, r12d
0x180004c8b  jl      loc_180004C08
0x180004c91  jmp     loc_180004B2D
0x180004ca0  movsxd  rax, dword ptr [r15+0Ch]
0x180004ca4  mov     r11d, [rbx+24h]
0x180004ca8  mov     edx, r11d
0x180004cab  mov     r14, [rbx+30h]
0x180004caf  and     edx, 0Fh
0x180004cb2  mov     ecx, edx
0x180004cb4  mov     r10d, ds:rva dword_180015C20[r13+rax*4]
0x180004cbc  mov     eax, r11d
0x180004cbf  sar     eax, 3
0x180004cc2  and     eax, 0FFFFFFFEh
0x180004cc5  mov     edi, eax
0x180004cc7  movzx   r9d, byte ptr [rax+r14]
0x180004ccc  inc     eax
0x180004cce  shl     r9w, 8
0x180004cd3  movzx   eax, byte ptr [rax+r14]
0x180004cd8  or      r9w, ax
0x180004cdc  shl     r9w, cl
0x180004ce0  mov     ecx, 10h
0x180004ce5  sub     ecx, edx
0x180004ce7  cmp     r10d, ecx
0x180004cea  ja      short loc_180004D55
0x180004cec  movzx   edi, r9w
0x180004cf0  mov     eax, [rbx+14h]
0x180004cf3  lea     ecx, [r11+r10]
0x180004cf7  add     [rbx+20h], r10d
0x180004cfb  dec     eax
0x180004cfd  sub     [rbx+18h], r10d
0x180004d01  and     ecx, eax
0x180004d03  mov     [rbx+24h], ecx
0x180004d06  mov     ecx, 10h
0x180004d0b  sub     cl, r10b
0x180004d0e  movsxd  rdx, r8d
0x180004d11  movzx   eax, di
0x180004d14  inc     r8d
0x180004d17  shr     eax, cl
0x180004d19  mov     [rsi+rdx*4], eax
0x180004d1c  cmp     r8d, r12d
0x180004d1f  jl      loc_180004CA0
0x180004d25  jmp     loc_180004B2D
0x180004d2a  mov     edx, [rbx+10h]
0x180004d2d  lea     eax, [rdi+2]
0x180004d30  dec     edx
0x180004d32  and     edx, eax
0x180004d34  mov     eax, edx
0x180004d36  movzx   edi, byte ptr [rdx+r14]
0x180004d3b  shl     di, 8
0x180004d3f  inc     eax
0x180004d41  movzx   eax, byte ptr [rax+r14]
0x180004d46  or      di, ax
0x180004d49  shr     di, cl
0x180004d4c  or      di, r9w
0x180004d50  jmp     loc_180004C5C
0x180004d55  mov     edx, [rbx+10h]
0x180004d58  lea     eax, [rdi+2]
0x180004d5b  dec     edx
0x180004d5d  and     edx, eax
0x180004d5f  mov     eax, edx
0x180004d61  movzx   edi, byte ptr [rdx+r14]
0x180004d66  shl     di, 8
0x180004d6a  inc     eax
0x180004d6c  movzx   eax, byte ptr [rax+r14]
0x180004d71  or      di, ax
0x180004d74  shr     di, cl
0x180004d77  or      di, r9w
0x180004d7b  jmp     loc_180004CF0
0x180004d80  cmp     dword ptr [rdx+14h], 2
0x180004d84  jnz     loc_180004AF8
0x180004d8a  lea     r13, cs:180000000h
0x180004d91  cmp     [rdx+18h], edi
0x180004d94  jnz     loc_1800051A1
0x180004d9a  mov     rax, rdi
0x180004d9d  movsxd  rbp, ds:rva dword_180015BB4[r13+rax*4]
0x180004da5  lea     rcx, [rax+1]
0x180004da9  mov     r12d, ds:rva dword_180015BB4[r13+rcx*4]
0x180004db1  mov     [rsp+0C8h+var_88], rcx
0x180004db6  cmp     ebp, r12d
0x180004db9  jge     short loc_180004E22
0x180004dbb  shl     rax, 6
0x180004dbf  lea     r14, rva dword_180015BE0[r13]
0x180004dc6  add     r14, rax
0x180004dc9  mov     rdi, rbp
0x180004dcc  nop     dword ptr [rax+00h]
0x180004dd0  movsxd  rdx, dword ptr [r15+0Ch]
0x180004dd4  mov     rcx, rbx; this
0x180004dd7  mov     edx, [r14+rdx*4]; unsigned int
0x180004ddb  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x180004de0  mov     [rsi+rdi*4+5Ch], eax
0x180004de4  mov     rcx, rbx; this
0x180004de7  movsxd  rdx, dword ptr [r15+0Ch]
0x180004deb  mov     edx, [r14+rdx*4]; unsigned int
0x180004def  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x180004df4  mov     [rsi+rdi*4+90h], eax
0x180004dfb  mov     rcx, rbx; this
0x180004dfe  movsxd  rdx, dword ptr [r15+0Ch]
0x180004e02  mov     edx, [r14+rdx*4]; unsigned int
0x180004e06  call    ?GetBits@CBitStream@@QEAAII@Z; CBitStream::GetBits(uint)
0x180004e0b  inc     ebp
0x180004e0d  mov     [rsi+rdi*4+0C4h], eax
0x180004e14  lea     rdi, [rdi+1]
0x180004e18  cmp     ebp, r12d
0x180004e1b  jl      short loc_180004DD0
0x180004e1d  mov     rcx, [rsp+0C8h+var_88]
0x180004e22  mov     rax, rcx
0x180004e25  cmp     rcx, 2
0x180004e29  jnz     loc_180004D9D
0x180004e2f  mov     dword ptr [rsi+8Ch], 0
0x180004e39  mov     eax, 7
0x180004e3e  mov     dword ptr [rsi+0C0h], 0
0x180004e48  mov     dword ptr [rsi+0F4h], 0
0x180004e52  mov     qword ptr [rsp+0C8h+var_A0], rsi
0x180004e57  mov     edi, 168h
0x180004e5c  mov     ebx, 16Ch
0x180004e61  mov     [rsp+0C8h+var_A8], rsi
0x180004e66  mov     r11d, 170h
0x180004e6c  mov     [rsp+0C8h+var_80], rsi
0x180004e71  mov     r10d, 174h
0x180004e77  mov     [rsp+0C8h+var_90], rsi
0x180004e7c  mov     r9d, 178h
0x180004e82  mov     [rsp+0C8h+var_70], rsi
0x180004e87  mov     r8d, 17Ch
0x180004e8d  mov     [rsp+0C8h+var_68], rsi
0x180004e92  mov     edx, 180h
0x180004e97  mov     [rsp+0C8h+var_60], rsi
0x180004e9c  mov     r13d, 154h
0x180004ea2  mov     [rsp+0C8h+var_58], rsi
0x180004ea7  mov     ebp, 158h
0x180004eac  mov     [rsp+0C8h+var_50], rsi
0x180004eb1  mov     r12d, 15Ch
0x180004eb7  mov     [rsp+0C8h+var_48], rsi
0x180004ebf  mov     r15d, 160h
0x180004ec5  mov     [rsp+0C8h+var_78], rsi
0x180004eca  mov     [rsi+r13], eax
0x180004ece  mov     r14d, 164h
0x180004ed4  mov     [rsi+rbp], eax
0x180004ed7  mov     ecx, 184h
0x180004edc  mov     [r12+rsi], eax
0x180004ee0  mov     [r15+rsi], eax
0x180004ee4  mov     [r14+rsi], eax
0x180004ee8  mov     [rdi+rsi], eax
0x180004eeb  mov     rdi, rsi
0x180004eee  mov     [rbx+rsi], eax
0x180004ef1  mov     rbx, rsi
0x180004ef4  mov     [rsp+0C8h+var_88], rsi
0x180004ef9  mov     [r11+rbx], eax
0x180004efd  mov     r11, rsi
0x180004f00  mov     [r10+rsi], eax
0x180004f04  mov     r10, rsi
0x180004f07  mov     [r9+rsi], eax
0x180004f0b  mov     r9, qword ptr [rsp+0C8h+var_A0]
0x180004f10  mov     [r8+r9], eax
0x180004f14  mov     r8, rsi
0x180004f17  mov     [rdx+rsi], eax
0x180004f1a  mov     rdx, rsi
0x180004f1d  mov     [rcx+rdx], eax
0x180004f20  jmp     loc_180004BCB
0x180004f25  mov     eax, [r9+10h]
0x180004f29  lea     r10, qword_180014D40
0x180004f30  mov     r8d, [rdx+0Ch]
0x180004f34  xorps   xmm0, xmm0
0x180004f37  mov     [rdx+3Ch], edi
0x180004f3a  mov     r9d, 0F4h
0x180004f40  mov     r14d, 3
0x180004f46  movdqu  xmmword ptr [rsp+0C8h+var_A0], xmm0
0x180004f4c  test    al, 1
0x180004f4e  jnz     loc_180005055
0x180004f54  mov     [rdx+48h], edi
0x180004f57  cmp     r8d, 190h
0x180004f5e  jge     loc_180005437
0x180004f64  mov     ecx, r8d
0x180004f67  mov     eax, 66666667h
0x180004f6c  sar     ecx, 4
0x180004f6f  imul    ecx
0x180004f71  sar     edx, 1
0x180004f73  mov     eax, edx
0x180004f75  shr     eax, 1Fh
0x180004f78  add     edx, eax
0x180004f7a  mov     [rsp+0C8h+var_A0], edx
0x180004f7e  lea     eax, [rdx+rdx*4]
0x180004f81  sub     ecx, eax
0x180004f83  mov     eax, r8d
0x180004f86  sar     eax, 2
0x180004f89  and     eax, r14d
0x180004f8c  mov     [rsp+0C8h+var_A0+4], ecx
0x180004f90  and     r8d, r14d
0x180004f93  mov     [rsp+0C8h+var_A0+8], eax
0x180004f97  mov     [rsp+0C8h+var_A0+0Ch], r8d
0x180004f9c  mov     rbp, rdi
0x180004f9f  mov     r12, rdi
0x180004fa2  mov     rcx, r10
0x180004fa5  cmp     dword ptr [r15+14h], 2
  ... truncated ...
```
