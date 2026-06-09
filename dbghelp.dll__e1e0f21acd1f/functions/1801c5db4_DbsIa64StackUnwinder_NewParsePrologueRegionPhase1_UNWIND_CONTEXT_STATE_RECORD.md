# DbsIa64StackUnwinder::NewParsePrologueRegionPhase1(_UNWIND_CONTEXT *,_STATE_RECORD *)

- ea: `0x1801c5db4`
- end: `0x1801c6908`
- name: `?NewParsePrologueRegionPhase1@DbsIa64StackUnwinder@@IEAAXPEAU_UNWIND_CONTEXT@@PEAU_STATE_RECORD@@@Z`
- size: `2900`
- prototype: `void __fastcall(DbsIa64StackUnwinder *__hidden this, struct _UNWIND_CONTEXT *, struct _STATE_RECORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1801c72dc`

## callees

- `0x1801c5db4`
- `0x1801c6e8c`
- `0x180205010`

## string_xrefs

- `0x1801c5e4f`: `Invalid unwind descriptor!\n`
- `0x1801c64fc`: `Invalid record type for descriptor P8!\n`
- `0x1801c64a8`: `Unsupported Unwind Descriptor!\n`
- `0x1801c6325`: `invalid unwind descriptors\n`
- `0x1801c6599`: `Invalid descriptor!\n`

## pseudocode

```c
void __fastcall DbsIa64StackUnwinder::NewParsePrologueRegionPhase1(
        DbsIa64StackUnwinder *this,
        struct _UNWIND_CONTEXT *a2,
        struct _STATE_RECORD *a3)
{
  unsigned __int8 *v3; // r10
  int v5; // r11d
  char v6; // r8
  __int64 v8; // rbx
  DbsIa64StackUnwinder *v9; // r15
  unsigned int v10; // edx
  unsigned __int8 v11; // r14
  __int16 v12; // cx
  unsigned int v13; // r14d
  unsigned __int16 v14; // bx
  _QWORD *v15; // r12
  int v16; // r8d
  __int64 v17; // rcx
  int v18; // edx
  __int64 v19; // rax
  __int64 v20; // r9
  unsigned __int8 v21; // r13
  unsigned __int8 v22; // r14
  __int64 i; // rcx
  int v24; // r15d
  unsigned __int8 v25; // r14
  __int64 v26; // rcx
  int v27; // eax
  unsigned __int8 v28; // dl
  unsigned __int8 v29; // r8
  __int64 v30; // rcx
  int v31; // r9d
  __int64 v32; // r9
  const char *v33; // r8
  int v34; // edx
  char v35; // dl
  __int64 v36; // rax
  int v37; // r8d
  char v38; // cl
  int v39; // eax
  __int64 v40; // r14
  int v41; // ecx
  __int64 v42; // rbx
  unsigned int v43; // eax
  int v44; // edx
  unsigned int v45; // eax
  int v46; // ecx
  int v47; // ecx
  int v48; // ecx
  __int64 v49; // rcx
  const char *v50; // r8
  __int64 v51; // rbx
  unsigned int v52; // eax
  int v53; // edx
  __int64 v54; // r14
  __int64 v55; // rbx
  unsigned int v56; // eax
  int v57; // edx
  __int64 v58; // rbx
  unsigned int v59; // eax
  int v60; // edx
  __int16 v61; // cx
  int v62; // r15d
  int v63; // r12d
  char v64; // r14
  char v65; // al
  unsigned __int8 v66; // r13
  int v67; // eax
  unsigned __int8 v68; // dl
  int v69; // eax
  unsigned __int8 v70; // dl
  int v71; // eax
  int v72; // ecx
  unsigned int v73; // eax
  unsigned __int8 v74; // r8
  unsigned __int8 v75; // dl
  unsigned __int8 v76; // r13
  unsigned __int8 v77; // al
  int v78; // ebx
  __int64 v79; // rcx
  int v80; // eax
  unsigned __int8 v81; // bl
  __int64 v82; // r8
  int v83; // eax
  __int64 v84; // rcx
  unsigned int v85; // eax
  __int64 v86; // [rsp+20h] [rbp-48h]
  int v87; // [rsp+40h] [rbp-28h]
  unsigned int v88; // [rsp+44h] [rbp-24h]
  unsigned int v89; // [rsp+48h] [rbp-20h]
  unsigned __int8 *v90; // [rsp+50h] [rbp-18h]
  char v92; // [rsp+B8h] [rbp+50h]
  char v93; // [rsp+B8h] [rbp+50h]
  unsigned int v94; // [rsp+C0h] [rbp+58h] BYREF
  unsigned __int8 v95; // [rsp+C8h] [rbp+60h]

  v3 = (unsigned __int8 *)*((_QWORD *)a2 + 38);
  v5 = 0;
  v90 = v3;
  v6 = 1;
  v87 = 0;
  v92 = 1;
  v8 = *((unsigned int *)a3 + 13);
  v9 = this;
  v95 = v3[v8];
  if ( (v95 & 0xE0) == 0x40 )
  {
    v10 = *((_DWORD *)a2 + 78);
    v11 = v3[(unsigned int)(v8 + 1)];
    v94 = v8 + 2;
    v12 = v11 >> 7;
    v13 = v11 & 0x7F;
    v14 = v12 | (2 * (v95 & 7));
    ReadLEB128(v3, v10, &v94);
    v15 = (_QWORD *)((char *)v9 + 8);
    if ( v13 < 0x20 )
      (*(void (__fastcall **)(_QWORD, __int64, const char *))(*(_QWORD *)*v15 + 80LL))(
        *v15,
        1,
        "Invalid unwind descriptor!\n");
    (*(void (**)(_QWORD, __int64, const char *, ...))(*(_QWORD *)*v15 + 80LL))(
      *v15,
      1,
      "Region R2: rmask=%x,grsave=%d,length=%d\n",
      v14,
      v13,
      *((_DWORD *)a3 + 10));
    v16 = 0;
    v17 = 0;
    do
    {
      if ( (v14 & 1) != 0 )
      {
        v18 = 1 << v17;
        if ( !*((_BYTE *)a3 + 9) || (*((_WORD *)a3 + 6) & (unsigned __int16)v18) != 0 )
        {
          *((_DWORD *)a2 + 2 * v17) = 4 * (v13 + v16);
          if ( (*((_WORD *)a3 + 6) & (unsigned __int16)v18) == 0 )
          {
            *((_DWORD *)a2 + 2 * v17 + 1) = *((_DWORD *)a3 + 10);
            *((_WORD *)a3 + 6) |= 1 << v17;
          }
        }
        ++v16;
      }
      v14 >>= 1;
      v17 = (unsigned int)(v17 + 1);
    }
    while ( (unsigned int)v17 <= 3 );
    LODWORD(v8) = v94;
    v3 = v90;
    v6 = 1;
    v5 = 0;
  }
  else
  {
    v15 = (_QWORD *)((char *)this + 8);
  }
  if ( (unsigned int)v8 <= *((_DWORD *)a3 + 14) )
  {
    while ( 1 )
    {
      v19 = (unsigned int)v8;
      v8 = (unsigned int)(v8 + 1);
      v94 = v8;
      v20 = (unsigned int)v8;
      v95 = v3[v19];
      v21 = v95;
      if ( (v95 & 0xE0) == 0x80 )
        break;
      if ( (v95 & 0xF0) == 0xA0 )
      {
        v24 = v3[v8] & 0x7F;
        v25 = (v3[v8] >> 7) | (2 * (v95 & 0xF));
        LODWORD(v86) = v24;
        LODWORD(v8) = v8 + 1;
        (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)this + 1) + 80LL))(
          *((_QWORD *)this + 1),
          1,
          "Prolog P2: brmask=%x reg base=%d\n",
          v25,
          v86);
        v26 = 8;
        *((_WORD *)a3 + 6) |= v25 << 8;
        do
        {
          if ( (v25 & 1) != 0 )
          {
            v27 = v24++;
            *((_DWORD *)a2 + 2 * v26) = 4 * v27;
          }
          v25 >>= 1;
          ++v26;
        }
        while ( v26 != 13 );
        v9 = this;
        goto LABEL_116;
      }
      if ( (v95 & 0xF8) == 0xB0 )
      {
        v28 = v3[v8];
        v29 = (v28 >> 7) | (2 * (v95 & 7));
        LODWORD(v8) = v8 + 1;
        if ( v29 == 6 )
        {
          *((_BYTE *)a2 + 297) = v28 & 0x7F;
          goto LABEL_117;
        }
        v30 = *((unsigned __int8 *)&qword_18025A990[2] + v29);
        v31 = 1 << v30;
        if ( *((_BYTE *)a3 + 9) && (*((_WORD *)a3 + 6) & (unsigned __int16)v31) == 0 )
          goto LABEL_117;
        *((_DWORD *)a2 + 2 * v30) = 4 * (v28 & 0x7F);
        if ( (*((_WORD *)a3 + 6) & (unsigned __int16)v31) == 0 )
        {
          *((_DWORD *)a2 + 2 * v30 + 1) = *((_DWORD *)a3 + 10);
          *((_WORD *)a3 + 6) |= 1 << v30;
        }
        v32 = v29;
        v33 = "Prolog P3: type=%d reg=%d\n";
        v34 = *((_DWORD *)a2 + 2 * v30) >> 2;
LABEL_35:
        (*(void (__fastcall **)(_QWORD, __int64, const char *, __int64, int))(*(_QWORD *)*v15 + 80LL))(
          *v15,
          1,
          v33,
          v32,
          v34);
LABEL_116:
        v3 = v90;
        goto LABEL_117;
      }
      if ( v95 != 0xB8 )
      {
        if ( v95 == 0xB9 )
        {
          v35 = v3[v8] >> 4;
          v36 = (unsigned int)(v8 + 2);
          v37 = (((v3[v8] & 0xF) << 8) | v3[(unsigned int)(v8 + 1)]) << 8;
          LODWORD(v8) = v8 + 3;
          LODWORD(v36) = v3[v36];
          *((_BYTE *)a3 + 10) |= v35;
          *((_DWORD *)a3 + 4) |= v36 | v37;
          v33 = "Prolog P5: grmask = %x, frmask = %x\n";
          v34 = *((_DWORD *)a3 + 4);
          v32 = *((unsigned __int8 *)a3 + 10);
          goto LABEL_35;
        }
        if ( (v95 & 0xE0) == 0xC0 )
        {
          v38 = v95 & 0x10;
          if ( (v95 & 0x10) != 0 )
            *((_BYTE *)a3 + 10) |= v95 & 0xF;
          else
            *((_DWORD *)a3 + 4) |= v95 & 0xF;
          if ( v38 )
            v39 = *((unsigned __int8 *)a3 + 10);
          else
            v39 = *((_DWORD *)a3 + 4);
          (*(void (__fastcall **)(_QWORD, __int64, const char *, bool, int))(*(_QWORD *)*v15 + 80LL))(
            *v15,
            1,
            "Prolog P6: is_gr = %d, mask = %x\n",
            v38 != 0,
            v39);
          goto LABEL_116;
        }
        if ( (v95 & 0xF0) == 0xE0 )
        {
          v40 = v95 & 0xF;
          if ( (unsigned int)v40 > 8 )
          {
            if ( (_DWORD)v40 == 9 )
              goto LABEL_72;
            if ( (_DWORD)v40 != 10 )
            {
              v41 = v40 - 11;
              if ( (_DWORD)v40 != 11 )
                goto LABEL_66;
              goto LABEL_72;
            }
LABEL_71:
            ReadLEB128(v3, *((_DWORD *)a2 + 78), &v94);
          }
          else
          {
            if ( (_DWORD)v40 == 8 )
              goto LABEL_71;
            if ( (v95 & 0xF) != 0 )
            {
              if ( (_DWORD)v40 == 1 )
                goto LABEL_71;
              if ( (_DWORD)v40 != 2 )
              {
                v41 = v40 - 3;
                if ( (_DWORD)v40 == 3 )
                {
                  v42 = *((unsigned __int8 *)qword_18025A990 + v40);
                  v43 = ReadLEB128(v3, *((_DWORD *)a2 + 78), &v94);
                  v44 = 1 << v42;
                  if ( !*((_BYTE *)a3 + 9) || (*((_WORD *)a3 + 6) & (unsigned __int16)v44) != 0 )
                  {
                    *((_DWORD *)a2 + 2 * v42) = (4 * v43) | 2;
                    if ( (*((_WORD *)a3 + 6) & (unsigned __int16)v44) == 0 )
                    {
                      *((_DWORD *)a2 + 2 * v42 + 1) = *((_DWORD *)a3 + 10);
                      *((_WORD *)a3 + 6) |= 1 << v42;
                    }
                  }
                  (*(void (__fastcall **)(_QWORD, __int64, const char *, __int64, unsigned int))(*(_QWORD *)*v15 + 80LL))(
                    *v15,
                    1,
                    "Prolog P7: type=%d spoff = %d\n",
                    3,
                    v43);
                  goto LABEL_60;
                }
LABEL_66:
                v46 = v41 - 1;
                if ( v46 )
                {
                  v47 = v46 - 1;
                  if ( !v47 )
                    goto LABEL_72;
                  v48 = v47 - 1;
                  if ( v48 )
                  {
                    if ( v48 != 1 )
                    {
                      v49 = *v15;
                      v50 = "invalid unwind descriptors\n";
LABEL_115:
                      (*(void (__fastcall **)(__int64, __int64, const char *, __int64))(*(_QWORD *)v49 + 80LL))(
                        v49,
                        1,
                        v50,
                        v20);
                      goto LABEL_116;
                    }
LABEL_72:
                    v51 = *((unsigned __int8 *)qword_18025A990 + v40);
                    v52 = ReadLEB128(v3, *((_DWORD *)a2 + 78), &v94);
                    v53 = 1 << v51;
                    if ( !*((_BYTE *)a3 + 9) || (*((_WORD *)a3 + 6) & (unsigned __int16)v53) != 0 )
                    {
                      *((_DWORD *)a2 + 2 * v51) = (4 * v52) | 1;
                      if ( (*((_WORD *)a3 + 6) & (unsigned __int16)v53) == 0 )
                      {
                        *((_DWORD *)a2 + 2 * v51 + 1) = *((_DWORD *)a3 + 10);
                        *((_WORD *)a3 + 6) |= 1 << v51;
                      }
                    }
                    (*(void (__fastcall **)(_QWORD, __int64, const char *, _QWORD, unsigned int))(**((_QWORD **)v9 + 1)
                                                                                                + 80LL))(
                      *((_QWORD *)v9 + 1),
                      1,
                      "Prolog P7: type=%d pspoff= %d\n",
                      (unsigned int)v40,
                      v52);
                    goto LABEL_60;
                  }
                }
                goto LABEL_71;
              }
              v45 = ReadLEB128(v3, *((_DWORD *)a2 + 78), &v94);
              *((_DWORD *)a3 + 8) = v45;
              *((_DWORD *)a3 + 7) = v45;
              (*(void (__fastcall **)(_QWORD, __int64, const char *, __int64, unsigned int))(*(_QWORD *)*v15 + 80LL))(
                *v15,
                1,
                "Prolog P7: type=%d, spillbase=%d\n",
                2,
                v45);
            }
            else
            {
              ReadLEB128(v3, *((_DWORD *)a2 + 78), &v94);
              ReadLEB128(v90, *((_DWORD *)a2 + 78), &v94);
              (*(void (**)(_QWORD, __int64, const char *, ...))(*(_QWORD *)*v15 + 80LL))(
                *v15,
                1,
                "Prolog P7: type=%d Slot=%d FrameSize=%d\n");
            }
          }
LABEL_60:
          LODWORD(v8) = v94;
          goto LABEL_116;
        }
        if ( v95 == 0xF0 )
        {
          v54 = v3[v8];
          LODWORD(v8) = v8 + 1;
          v94 = v8;
          if ( (unsigned int)v54 > 9 )
          {
            switch ( (_DWORD)v54 )
            {
              case 0xA:
                goto LABEL_71;
              case 0xB:
                goto LABEL_88;
              case 0xC:
                goto LABEL_104;
              case 0xD:
                goto LABEL_71;
              case 0xE:
                goto LABEL_88;
              case 0xF:
                goto LABEL_104;
              case 0x10:
                goto LABEL_71;
              case 0x11:
LABEL_88:
                v55 = *((unsigned __int8 *)&qword_18025A990[4] + v54);
                v56 = ReadLEB128(v3, *((_DWORD *)a2 + 78), &v94);
                v57 = 1 << v55;
                if ( !*((_BYTE *)a3 + 9) || (*((_WORD *)a3 + 6) & (unsigned __int16)v57) != 0 )
                {
                  *((_DWORD *)a2 + 2 * v55) = (4 * v56) | 1;
                  if ( (*((_WORD *)a3 + 6) & (unsigned __int16)v57) == 0 )
                  {
                    *((_DWORD *)a2 + 2 * v55 + 1) = *((_DWORD *)a3 + 10);
                    *((_WORD *)a3 + 6) |= 1 << v55;
                  }
                }
                (*(void (__fastcall **)(_QWORD, __int64, const char *, _QWORD, unsigned int))(**((_QWORD **)v9 + 1)
                                                                                            + 80LL))(
                  *((_QWORD *)v9 + 1),
                  1,
                  "Prolog P8: type=%d pspoff= %d\n",
                  (unsigned int)v54,
                  v56);
                goto LABEL_60;
              case 0x12:
                goto LABEL_104;
            }
            v50 = "Invalid record type for descriptor P8!\n";
          }
          else
          {
            if ( (_DWORD)v54 == 9 )
              goto LABEL_104;
            if ( (_DWORD)v54 )
            {
              if ( (_DWORD)v54 != 1
                && (_DWORD)v54 != 2
                && (_DWORD)v54 != 3
                && (_DWORD)v54 != 4
                && (_DWORD)v54 != 5
                && (_DWORD)v54 != 6 )
              {
                if ( (_DWORD)v54 == 7 )
                  goto LABEL_71;
                goto LABEL_88;
              }
LABEL_104:
              v58 = *((unsigned __int8 *)&qword_18025A990[4] + v54);
              v59 = ReadLEB128(v3, *((_DWORD *)a2 + 78), &v94);
              v60 = 1 << v58;
              if ( !*((_BYTE *)a3 + 9) || (*((_WORD *)a3 + 6) & (unsigned __int16)v60) != 0 )
              {
                *((_DWORD *)a2 + 2 * v58) = (4 * v59) | 2;
                if ( (*((_WORD *)a3 + 6) & (unsigned __int16)v60) == 0 )
                {
                  *((_DWORD *)a2 + 2 * v58 + 1) = *((_DWORD *)a3 + 10);
                  *((_WORD *)a3 + 6) |= 1 << v58;
                }
              }
              (*(void (__fastcall **)(_QWORD, __int64, const char *, _QWORD, unsigned int))(**((_QWORD **)v9 + 1) + 80LL))(
                *((_QWORD *)v9 + 1),
                1,
                "Prolog P8: type=%d spoff= %d\n",
                (unsigned int)v54,
                v59);
              goto LABEL_60;
            }
            v50 = "Unsupported Unwind Descriptor!\n";
          }
LABEL_114:
          v49 = *((_QWORD *)v9 + 1);
          goto LABEL_115;
        }
        if ( v95 == 0xF1 )
        {
          LODWORD(v8) = v8 + 2;
          v50 = "Format P9 not supported yet!\n";
          goto LABEL_114;
        }
        if ( v95 != 0xFF )
        {
          v50 = "Invalid descriptor!\n";
          goto LABEL_114;
        }
        LODWORD(v8) = v8 + 2;
LABEL_117:
        v6 = v92;
        v5 = v87;
        goto LABEL_118;
      }
      v6 = 0;
      v92 = 0;
      v5 = v8;
      LODWORD(v8) = v8 + ((unsigned int)(*((_DWORD *)a3 + 10) + 3) >> 2);
      v87 = v20;
LABEL_118:
      if ( (unsigned int)v8 > *((_DWORD *)a3 + 14) )
        goto LABEL_119;
    }
    v22 = v95 & 0x1F;
    *((_WORD *)a3 + 6) |= (v95 & 0x1F) << 8;
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)v9 + 1) + 80LL))(
      *((_QWORD *)v9 + 1),
      1,
      "Prolog P1: brmask=%x\n",
      v21 & 0x1F);
    for ( i = 8; i != 13; ++i )
    {
      if ( (v22 & 1) != 0 )
      {
        *((_DWORD *)a2 + 2 * i) &= ~2u;
        *((_DWORD *)a2 + 2 * i) |= 1u;
        *((_DWORD *)a2 + 2 * i + 1) = *((_DWORD *)a3 + 10);
      }
      v22 >>= 1;
    }
    goto LABEL_116;
  }
LABEL_119:
  v61 = *((_WORD *)a3 + 6);
  v62 = *((unsigned __int8 *)a3 + 10);
  v63 = *((_DWORD *)a3 + 4);
  v64 = HIBYTE(v61);
  if ( v63 | v62 | HIBYTE(v61) )
  {
    v65 = *((_BYTE *)a3 + 9);
    if ( v6 )
    {
      if ( v65 )
      {
        *((_BYTE *)a3 + 10) = 0;
        *((_WORD *)a3 + 6) = (unsigned __int8)v61;
        *((_DWORD *)a3 + 4) = 0;
      }
      else
      {
        *((_DWORD *)a3 + 7) &= 0xFFFFFFFC;
        v66 = 19;
        while ( (v63 & 0xFFFFF) != 0 )
        {
          if ( (v63 & 0x80000) != 0 )
          {
            v67 = *((_DWORD *)a3 + 7) + 4;
            *((_DWORD *)a3 + 7) = v67;
            *((_DWORD *)a2 + 2 * v66 + 26) &= 3u;
            *((_DWORD *)a2 + 2 * v66 + 26) |= 4 * v67;
          }
          v63 *= 2;
          --v66;
        }
        v68 = 12;
        while ( (v64 & 0x1F) != 0 )
        {
          if ( (v64 & 0x10) != 0 && (*((_DWORD *)a2 + 2 * v68) & 3) == 1 )
          {
            v69 = *((_DWORD *)a3 + 7) + 2;
            *((_DWORD *)a3 + 7) = v69;
            *((_DWORD *)a2 + 2 * v68) &= 3u;
            *((_DWORD *)a2 + 2 * v68) |= 4 * v69;
          }
          v64 *= 2;
          --v68;
        }
        v70 = 3;
        while ( (v62 & 0xF) != 0 )
        {
          if ( (v62 & 8) != 0 )
          {
            v71 = *((_DWORD *)a3 + 7) + 2;
            *((_DWORD *)a3 + 7) = v71;
            *((_DWORD *)a2 + 2 * v70 + 66) &= 3u;
            *((_DWORD *)a2 + 2 * v70 + 66) |= 4 * v71;
          }
          LOBYTE(v62) = 2 * v62;
          --v70;
        }
      }
      return;
    }
    if ( v65 )
    {
      *((_BYTE *)a3 + 10) = 0;
      *((_WORD *)a3 + 6) = (unsigned __int8)v61;
      *((_DWORD *)a3 + 4) = 0;
      v72 = *((_DWORD *)a2 + 80) - *((_DWORD *)a3 + 9);
    }
    else
    {
      v72 = *((_DWORD *)a3 + 10);
    }
    LOBYTE(v73) = 0;
    v89 = v72;
    v88 = 0;
    v74 = 3;
    LOBYTE(v94) = 3;
    v75 = 4;
    v93 = 4;
    v76 = 19;
    if ( !v72 )
      return;
    while ( 1 )
    {
      if ( (v73 & 3) != 0 )
      {
        v77 = 4 * v95;
      }
      else
      {
        v87 = v5 + 1;
        v77 = v3[v5];
      }
      v95 = v77;
      if ( (v77 & 0xC0) == 0x40 )
        break;
      if ( (v77 & 0xC0) == 0x80 )
      {
        if ( (v62 & 8) == 0 )
        {
          do
          {
            if ( !v74 )
              break;
            --v74;
            LOBYTE(v62) = 2 * v62;
          }
          while ( (v62 & 8) == 0 );
          LOBYTE(v94) = v74;
        }
        v81 = v74;
        (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)this + 1) + 80LL))(
          *((_QWORD *)this + 1),
          1,
          "spilled register S%lx\n",
          v74);
        v82 = (unsigned __int8)v94;
        v75 = v93;
        *((_BYTE *)a3 + 10) |= 1 << v81;
        *((_DWORD *)a2 + 2 * v82 + 67) = v88;
        *((_DWORD *)a3 + 7) += 2;
        v83 = *((_DWORD *)a3 + 7);
        *((_DWORD *)a2 + 2 * v82 + 66) &= 3u;
        *((_DWORD *)a2 + 2 * v82 + 66) |= 4 * v83;
        v74 = v82 - 1;
        LOBYTE(v94) = v74;
        LOBYTE(v62) = 2 * v62;
        goto LABEL_167;
      }
      if ( (v77 & 0xC0) == 0xC0 )
      {
        if ( (v64 & 0x10) == 0 )
        {
          do
          {
            if ( !v75 )
              break;
            --v75;
            v64 *= 2;
          }
          while ( (v64 & 0x10) == 0 );
          v93 = v75;
        }
        v78 = v75;
        (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)this + 1) + 80LL))(
          *((_QWORD *)this + 1),
          1,
          "spilled register BS%lx\n",
          v75);
        v79 = (unsigned int)(v78 + 8);
        *((_WORD *)a3 + 6) |= 1 << (v78 + 8);
        *((_DWORD *)a2 + 2 * v79 + 1) = v88;
        if ( (*((_DWORD *)a2 + 2 * v79) & 3) == 1 )
        {
          *((_DWORD *)a3 + 7) += 2;
          v80 = *((_DWORD *)a3 + 7);
          *((_DWORD *)a2 + 2 * v79) &= 3u;
          *((_DWORD *)a2 + 2 * v79) |= 4 * v80;
        }
        v75 = --v93;
        v64 *= 2;
        goto LABEL_166;
      }
LABEL_167:
      v3 = v90;
      v73 = v88 + 1;
      v5 = v87;
      v88 = v73;
      if ( v73 >= v89 )
        return;
    }
    while ( (v63 & 0x80000) == 0 && v76 )
    {
      --v76;
      v63 *= 2;
    }
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)this + 1) + 80LL))(
      *((_QWORD *)this + 1),
      1,
      "spilled register FS%lx\n",
      v76);
    v75 = v93;
    *((_DWORD *)a3 + 4) |= 1 << v76;
    v84 = v76--;
    *((_DWORD *)a2 + 2 * v84 + 27) = v88;
    v85 = ((*((_DWORD *)a3 + 7) + 2) & 0xFFFFFFFC) + 4;
    *((_DWORD *)a3 + 7) = v85;
    *((_DWORD *)a2 + 2 * v84 + 26) &= 3u;
    *((_DWORD *)a2 + 2 * v84 + 26) |= 4 * v85;
    v63 *= 2;
LABEL_166:
    v74 = v94;
    goto LABEL_167;
  }
}

```

## disassembly

```asm
0x1801c5db4  mov     [rsp-40h+arg_0], rcx
0x1801c5db9  push    rbp
0x1801c5dba  push    rbx
0x1801c5dbb  push    rsi
0x1801c5dbc  push    rdi
0x1801c5dbd  push    r12
0x1801c5dbf  push    r13
0x1801c5dc1  push    r14
0x1801c5dc3  push    r15
0x1801c5dc5  mov     rbp, rsp
0x1801c5dc8  sub     rsp, 68h
0x1801c5dcc  mov     r10, [rdx+130h]
0x1801c5dd3  mov     rdi, r8
0x1801c5dd6  xor     r11d, r11d
0x1801c5dd9  mov     [rbp+var_18], r10
0x1801c5ddd  mov     r8b, 1
0x1801c5de0  mov     [rbp+var_28], r11d
0x1801c5de4  mov     rsi, rdx
0x1801c5de7  mov     [rbp+arg_8], r8b
0x1801c5deb  mov     ebx, [rdi+34h]
0x1801c5dee  mov     r15, rcx
0x1801c5df1  mov     r13b, [rbx+r10]
0x1801c5df5  mov     al, r13b
0x1801c5df8  mov     [rbp+arg_18], r13b
0x1801c5dfc  and     al, 0E0h
0x1801c5dfe  cmp     al, 40h ; '@'
0x1801c5e00  jnz     loc_1801C5EF4
0x1801c5e06  mov     edx, [rdx+138h]; unsigned int
0x1801c5e0c  lea     ecx, [rbx+1]
0x1801c5e0f  movzx   r14d, byte ptr [rcx+r10]
0x1801c5e14  lea     eax, [rcx+1]
0x1801c5e17  mov     [rbp+arg_10], eax
0x1801c5e1a  lea     r8, [rbp+arg_10]; unsigned int *
0x1801c5e1e  mov     al, r13b
0x1801c5e21  and     al, 7
0x1801c5e23  movzx   ebx, al
0x1801c5e26  mov     al, r14b
0x1801c5e29  shr     al, 7
0x1801c5e2c  add     bx, bx
0x1801c5e2f  movzx   ecx, al
0x1801c5e32  and     r14d, 7Fh
0x1801c5e36  or      bx, cx
0x1801c5e39  mov     rcx, r10; unsigned __int8 *
0x1801c5e3c  call    ?ReadLEB128@@YAKPEAEKPEAK@Z; ReadLEB128(uchar *,ulong,ulong *)
0x1801c5e41  lea     r12, [r15+8]
0x1801c5e45  cmp     r14d, 20h ; ' '
0x1801c5e49  jnb     short loc_1801C5E67
0x1801c5e4b  mov     rcx, [r12]
0x1801c5e4f  lea     r8, aInvalidUnwindD; "Invalid unwind descriptor!\n"
0x1801c5e56  mov     edx, 1
0x1801c5e5b  mov     rax, [rcx]
0x1801c5e5e  mov     rax, [rax+50h]
0x1801c5e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c5e67  mov     edx, [rdi+28h]
0x1801c5e6a  lea     r8, aRegionR2RmaskX; "Region R2: rmask=%x,grsave=%d,length=%d"...
0x1801c5e71  mov     rcx, [r12]
0x1801c5e75  mov     [rsp+68h+var_40], edx
0x1801c5e79  mov     edx, 1
0x1801c5e7e  movzx   r9d, bx
0x1801c5e82  mov     dword ptr [rsp+68h+var_48], r14d
0x1801c5e87  mov     rax, [rcx]
0x1801c5e8a  mov     rax, [rax+50h]
0x1801c5e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c5e93  xor     r8d, r8d
0x1801c5e96  xor     ecx, ecx
0x1801c5e98  test    bl, 1
0x1801c5e9b  jz      short loc_1801C5ED9
0x1801c5e9d  mov     edx, 1
0x1801c5ea2  shl     edx, cl
0x1801c5ea4  cmp     byte ptr [rdi+9], 0
0x1801c5ea8  jz      short loc_1801C5EB2
0x1801c5eaa  movzx   eax, word ptr [rdi+0Ch]
0x1801c5eae  test    edx, eax
0x1801c5eb0  jz      short loc_1801C5ED6
0x1801c5eb2  lea     eax, [r14+r8]
0x1801c5eb6  shl     eax, 2
0x1801c5eb9  mov     [rsi+rcx*8], eax
0x1801c5ebc  movzx   eax, word ptr [rdi+0Ch]
0x1801c5ec0  test    edx, eax
0x1801c5ec2  jnz     short loc_1801C5ED6
0x1801c5ec4  mov     eax, [rdi+28h]
0x1801c5ec7  mov     [rsi+rcx*8+4], eax
0x1801c5ecb  movzx   eax, word ptr [rdi+0Ch]
0x1801c5ecf  bts     eax, ecx
0x1801c5ed2  mov     [rdi+0Ch], ax
0x1801c5ed6  inc     r8d
0x1801c5ed9  shr     bx, 1
0x1801c5edc  inc     ecx
0x1801c5ede  cmp     ecx, 3
0x1801c5ee1  jbe     short loc_1801C5E98
0x1801c5ee3  mov     ebx, [rbp+arg_10]
0x1801c5ee6  mov     r10, [rbp+var_18]
0x1801c5eea  mov     r8b, [rbp+arg_8]
0x1801c5eee  mov     r11d, [rbp+var_28]
0x1801c5ef2  jmp     short loc_1801C5EF8
0x1801c5ef4  lea     r12, [rcx+8]
0x1801c5ef8  mov     r9d, 0FFh
0x1801c5efe  cmp     ebx, [rdi+38h]
0x1801c5f01  ja      loc_1801C65D0
0x1801c5f07  mov     eax, ebx
0x1801c5f09  lea     r11, __ImageBase
0x1801c5f10  inc     ebx
0x1801c5f12  mov     [rbp+arg_10], ebx
0x1801c5f15  mov     r9d, ebx
0x1801c5f18  movzx   r13d, byte ptr [rax+r10]
0x1801c5f1d  mov     dl, r13b
0x1801c5f20  mov     [rbp+arg_18], r13b
0x1801c5f24  and     dl, 0E0h
0x1801c5f27  cmp     dl, 80h
0x1801c5f2a  jnz     short loc_1801C5F8A
0x1801c5f2c  mov     r14b, r13b
0x1801c5f2f  lea     r8, aPrologP1Brmask; "Prolog P1: brmask=%x\n"
0x1801c5f36  and     r14b, 1Fh
0x1801c5f3a  mov     edx, 1
0x1801c5f3f  movzx   eax, r14b
0x1801c5f43  shl     ax, 8
0x1801c5f47  or      [rdi+0Ch], ax
0x1801c5f4b  mov     rcx, [r15+8]
0x1801c5f4f  movzx   r9d, r14b
0x1801c5f53  mov     rax, [rcx]
0x1801c5f56  mov     rax, [rax+50h]
0x1801c5f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c5f5f  mov     ecx, 8
0x1801c5f64  test    r14b, 1
0x1801c5f68  jz      short loc_1801C5F79
0x1801c5f6a  and     dword ptr [rsi+rcx*8], 0FFFFFFFDh
0x1801c5f6e  or      dword ptr [rsi+rcx*8], 1
0x1801c5f72  mov     eax, [rdi+28h]
0x1801c5f75  mov     [rsi+rcx*8+4], eax
0x1801c5f79  shr     r14b, 1
0x1801c5f7c  inc     rcx
0x1801c5f7f  cmp     rcx, 0Dh
0x1801c5f83  jnz     short loc_1801C5F64
0x1801c5f85  jmp     loc_1801C65B5
0x1801c5f8a  mov     cl, r13b
0x1801c5f8d  and     cl, 0F0h
0x1801c5f90  cmp     cl, 0A0h
0x1801c5f93  jnz     short loc_1801C6014
0x1801c5f95  movzx   ecx, byte ptr [rbx+r10]
0x1801c5f9a  lea     r8, aPrologP2Brmask; "Prolog P2: brmask=%x reg base=%d\n"
0x1801c5fa1  mov     r15d, ecx
0x1801c5fa4  mov     r14b, r13b
0x1801c5fa7  shr     cl, 7
0x1801c5faa  and     r14b, 0Fh
0x1801c5fae  add     r14b, r14b
0x1801c5fb1  and     r15d, 7Fh
0x1801c5fb5  or      r14b, cl
0x1801c5fb8  mov     dword ptr [rsp+68h+var_48], r15d
0x1801c5fbd  mov     rcx, [rbp+arg_0]
0x1801c5fc1  mov     edx, 1
0x1801c5fc6  movzx   r9d, r14b
0x1801c5fca  inc     ebx
0x1801c5fcc  mov     rcx, [rcx+8]
0x1801c5fd0  mov     rax, [rcx]
0x1801c5fd3  mov     rax, [rax+50h]
0x1801c5fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c5fdc  movzx   eax, r14b
0x1801c5fe0  mov     ecx, 8
0x1801c5fe5  shl     ax, 8
0x1801c5fe9  or      [rdi+0Ch], ax
0x1801c5fed  test    r14b, 1
0x1801c5ff1  jz      short loc_1801C5FFF
0x1801c5ff3  mov     eax, r15d
0x1801c5ff6  inc     r15d
0x1801c5ff9  shl     eax, 2
0x1801c5ffc  mov     [rsi+rcx*8], eax
0x1801c5fff  shr     r14b, 1
0x1801c6002  inc     rcx
0x1801c6005  cmp     rcx, 0Dh
0x1801c6009  jnz     short loc_1801C5FED
0x1801c600b  mov     r15, [rbp+arg_0]
0x1801c600f  jmp     loc_1801C65B5
0x1801c6014  mov     al, r13b
0x1801c6017  and     al, 0F8h
0x1801c6019  cmp     al, 0B0h
0x1801c601b  jnz     loc_1801C60D0
0x1801c6021  movzx   edx, byte ptr [rbx+r10]
0x1801c6026  mov     r8b, r13b
0x1801c6029  and     r8b, 7
0x1801c602d  mov     al, dl
0x1801c602f  add     r8b, r8b
0x1801c6032  shr     al, 7
0x1801c6035  or      r8b, al
0x1801c6038  inc     ebx
0x1801c603a  cmp     r8b, 6
0x1801c603e  jnz     short loc_1801C604E
0x1801c6040  and     dl, 7Fh
0x1801c6043  mov     [rsi+129h], dl
0x1801c6049  jmp     loc_1801C65B9
0x1801c604e  movzx   eax, r8b
0x1801c6052  mov     r9d, 1
0x1801c6058  movzx   ecx, byte ptr [rax+r11+25A9A0h]
0x1801c6061  shl     r9d, cl
0x1801c6064  cmp     byte ptr [rdi+9], 0
0x1801c6068  jz      short loc_1801C6077
0x1801c606a  movzx   eax, word ptr [rdi+0Ch]
0x1801c606e  test    r9d, eax
0x1801c6071  jz      loc_1801C65B9
0x1801c6077  mov     eax, edx
0x1801c6079  mov     r10, rcx
0x1801c607c  and     eax, 7Fh
0x1801c607f  shl     eax, 2
0x1801c6082  mov     [rsi+rcx*8], eax
0x1801c6085  movzx   eax, word ptr [rdi+0Ch]
0x1801c6089  test    r9d, eax
0x1801c608c  jnz     short loc_1801C60A0
0x1801c608e  mov     eax, [rdi+28h]
0x1801c6091  mov     [rsi+rcx*8+4], eax
0x1801c6095  movzx   eax, word ptr [rdi+0Ch]
0x1801c6099  bts     eax, ecx
0x1801c609c  mov     [rdi+0Ch], ax
0x1801c60a0  mov     edx, [rsi+r10*8]
0x1801c60a4  movzx   r9d, r8b
0x1801c60a8  lea     r8, aPrologP3TypeDR; "Prolog P3: type=%d reg=%d\n"
0x1801c60af  shr     edx, 2
0x1801c60b2  mov     rcx, [r12]
0x1801c60b6  mov     dword ptr [rsp+68h+var_48], edx
0x1801c60ba  mov     rax, [rcx]
0x1801c60bd  mov     rax, [rax+50h]
0x1801c60c1  mov     edx, 1
0x1801c60c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c60cb  jmp     loc_1801C65B5
0x1801c60d0  cmp     r13b, 0B8h
0x1801c60d4  jnz     short loc_1801C60F5
0x1801c60d6  mov     ebx, [rdi+28h]
0x1801c60d9  xor     r8b, r8b
0x1801c60dc  add     ebx, 3
0x1801c60df  mov     [rbp+arg_8], r8b
0x1801c60e3  shr     ebx, 2
0x1801c60e6  mov     r11d, r9d
0x1801c60e9  add     ebx, r9d
0x1801c60ec  mov     [rbp+var_28], r9d
0x1801c60f0  jmp     loc_1801C65C1
0x1801c60f5  cmp     r13b, 0B9h
0x1801c60f9  jnz     short loc_1801C6143
0x1801c60fb  movzx   edx, byte ptr [rbx+r10]
0x1801c6100  lea     eax, [rbx+1]
0x1801c6103  movzx   r8d, byte ptr [rax+r10]
0x1801c6108  mov     eax, edx
0x1801c610a  and     eax, 0Fh
0x1801c610d  shr     dl, 4
0x1801c6110  shl     eax, 8
0x1801c6113  or      r8d, eax
0x1801c6116  lea     eax, [rbx+2]
0x1801c6119  shl     r8d, 8
0x1801c611d  add     ebx, 3
0x1801c6120  movzx   eax, byte ptr [rax+r10]
0x1801c6125  or      [rdi+0Ah], dl
0x1801c6128  or      r8d, eax
0x1801c612b  or      [rdi+10h], r8d
0x1801c612f  lea     r8, aPrologP5Grmask; "Prolog P5: grmask = %x, frmask = %x\n"
0x1801c6136  mov     edx, [rdi+10h]
0x1801c6139  movzx   r9d, byte ptr [rdi+0Ah]
0x1801c613e  jmp     loc_1801C60B2
0x1801c6143  cmp     dl, 0C0h
0x1801c6146  jnz     short loc_1801C619A
0x1801c6148  mov     cl, r13b
0x1801c614b  and     cl, 10h
0x1801c614e  jz      short loc_1801C615A
0x1801c6150  mov     al, r13b
0x1801c6153  and     al, 0Fh
0x1801c6155  or      [rdi+0Ah], al
0x1801c6158  jmp     short loc_1801C6163
0x1801c615a  mov     eax, r13d
0x1801c615d  and     eax, 0Fh
0x1801c6160  or      [rdi+10h], eax
0x1801c6163  mov     r10, [r12]
0x1801c6167  mov     rax, [r10]
0x1801c616a  mov     r11, [rax+50h]
0x1801c616e  test    cl, cl
0x1801c6170  jz      short loc_1801C6178
0x1801c6172  movzx   eax, byte ptr [rdi+0Ah]
0x1801c6176  jmp     short loc_1801C617B
0x1801c6178  mov     eax, [rdi+10h]
0x1801c617b  xor     r9d, r9d
0x1801c617e  mov     dword ptr [rsp+68h+var_48], eax
0x1801c6182  test    cl, cl
0x1801c6184  lea     r8, aPrologP6IsGrDM; "Prolog P6: is_gr = %d, mask = %x\n"
0x1801c618b  mov     rcx, r10
0x1801c618e  mov     rax, r11
0x1801c6191  setnz   r9b
0x1801c6195  jmp     loc_1801C60C1
0x1801c619a  cmp     cl, 0E0h
0x1801c619d  jnz     loc_1801C63BC
0x1801c61a3  mov     al, r13b
0x1801c61a6  and     al, 0Fh
0x1801c61a8  movzx   r14d, al
0x1801c61ac  cmp     r14d, 8
0x1801c61b0  ja      loc_1801C62FB
0x1801c61b6  jz      loc_1801C6331
0x1801c61bc  mov     ecx, r14d
0x1801c61bf  test    al, al
0x1801c61c1  jz      loc_1801C62A6
0x1801c61c7  sub     ecx, 1
0x1801c61ca  jz      loc_1801C6331
0x1801c61d0  sub     ecx, 1
0x1801c61d3  jz      loc_1801C626D
0x1801c61d9  sub     ecx, 1
0x1801c61dc  jnz     loc_1801C630D
0x1801c61e2  mov     edx, [rsi+138h]; unsigned int
  ... truncated ...
```
