# PDBCopy::CopyPrivateSymbols(Mod *,Mod *)

- ea: `0x18002f020`
- end: `0x1800303d8`
- name: `?CopyPrivateSymbols@PDBCopy@@AEAAHPEAUMod@@0@Z`
- size: `5048`
- prototype: `__int64 __fastcall(PDBCopy *__hidden this, struct Mod *, struct Mod *)`
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x18002e960`

## callees

- `0x180026980`
- `0x180026990`
- `0x180027430`
- `0x1800274e0`
- `0x180029320`
- `0x180029550`
- `0x18002a050`
- `0x18002a270`
- `0x18002c610`
- `0x18002f020`
- `0x180034060`
- `0x1800354f0`
- `0x180037c50`
- `0x1801693d5`
- `0x180169430`
- `0x18018c350`
- `0x18018c480`
- `0x1801bf2d0`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18002f4a2`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18002f4b6`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18002f4a2`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x18002f4b6`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18002f48a`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18002f48a`

## pseudocode

```c
// Hidden C++ exception states: #wind=40
__int64 __fastcall PDBCopy::CopyPrivateSymbols(struct PDB **this, struct Mod *a2, struct Mod *a3)
{
  PDBCopy *v4; // r12
  int v5; // eax
  struct PDB *v7; // rax
  size_t v8; // rsi
  PSGSI1::EnumPubsByAddr *v9; // rcx
  char *v10; // r15
  PSGSI1::EnumPubsByAddr *v11; // r14
  unsigned int v12; // eax
  int v13; // ecx
  unsigned __int8 *v14; // r13
  PSGSI1::EnumPubsByAddr *v15; // r15
  PSGSI1::EnumPubsByAddr *v16; // rsi
  unsigned __int8 *v17; // rbx
  enum PDBErrors *v18; // r12
  unsigned __int8 *v19; // rax
  PSGSI1::EnumPubsByAddr *v20; // rcx
  PSGSI1::EnumPubsByAddr *v21; // rcx
  PSGSI1::EnumPubsByAddr *v22; // rcx
  PSGSI1::EnumPubsByAddr *v23; // rcx
  int v24; // eax
  const char *v25; // r12
  unsigned __int16 v26; // bx
  size_t v27; // rbx
  size_t v28; // rax
  rsize_t v29; // rbx
  PSGSI1::EnumPubsByAddr *v30; // rcx
  char *v31; // rax
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rcx
  unsigned __int64 v35; // r12
  unsigned __int64 v36; // rbx
  unsigned __int64 v37; // rax
  char *v38; // rax
  unsigned __int64 v39; // rcx
  unsigned __int64 v40; // rdx
  unsigned __int64 v41; // rax
  bool v42; // zf
  size_t v43; // rax
  void *v44; // rax
  PSGSI1::EnumPubsByAddr *v45; // rcx
  size_t v46; // rbx
  PSGSI1::EnumPubsByAddr *v47; // rcx
  int v48; // ebx
  int v49; // eax
  PSGSI1::EnumPubsByAddr *v50; // rcx
  PSGSI1::EnumPubsByAddr *v51; // rcx
  PSGSI1::EnumPubsByAddr *v52; // rcx
  __int16 v53; // cx
  int v54; // eax
  PSGSI1::EnumPubsByAddr *v55; // rcx
  __int64 v56; // r12
  int v57; // eax
  PSGSI1::EnumPubsByAddr *v58; // rcx
  const struct SYMTYPE *v59; // r12
  PSGSI1::EnumPubsByAddr *v60; // rcx
  PSGSI1::EnumPubsByAddr *v61; // rcx
  unsigned __int8 *v62; // rax
  int v63; // eax
  PSGSI1::EnumPubsByAddr *v64; // rcx
  PSGSI1::EnumPubsByAddr *v65; // rcx
  PSGSI1::EnumPubsByAddr *v66; // rcx
  PSGSI1::EnumPubsByAddr *v67; // rcx
  PSGSI1::EnumPubsByAddr *v68; // rcx
  PSGSI1::EnumPubsByAddr *v69; // rbx
  PSGSI1::EnumPubsByAddr *v70; // r13
  int v71; // r12d
  int v72; // r15d
  PSGSI1::EnumPubsByAddr *v73; // r12
  PSGSI1::EnumPubsByAddr *v74; // r13
  unsigned __int64 v75; // r12
  PSGSI1::EnumPubsByAddr *v76; // rbx
  PSGSI1::EnumPubsByAddr *v77; // rcx
  PSGSI1::EnumPubsByAddr *v78; // rcx
  PSGSI1::EnumPubsByAddr *v79; // rcx
  PSGSI1::EnumPubsByAddr *v80; // rcx
  PSGSI1::EnumPubsByAddr *v81; // rcx
  PSGSI1::EnumPubsByAddr *v82; // rcx
  void *Src[2]; // [rsp+20h] [rbp-168h] BYREF
  char *v84; // [rsp+30h] [rbp-158h]
  char *Destination[2]; // [rsp+38h] [rbp-150h] BYREF
  __int64 v86; // [rsp+48h] [rbp-140h]
  PSGSI1::EnumPubsByAddr *v87; // [rsp+50h] [rbp-138h]
  int v88; // [rsp+58h] [rbp-130h]
  int v89; // [rsp+5Ch] [rbp-12Ch] BYREF
  void **v90; // [rsp+60h] [rbp-128h] BYREF
  PSGSI1::EnumPubsByAddr *v91[2]; // [rsp+68h] [rbp-120h]
  int v92; // [rsp+78h] [rbp-110h]
  __int64 v93; // [rsp+80h] [rbp-108h]
  __int64 v94; // [rsp+88h] [rbp-100h]
  __int16 v95; // [rsp+90h] [rbp-F8h]
  int v96; // [rsp+98h] [rbp-F0h] BYREF
  unsigned __int8 *v97; // [rsp+A0h] [rbp-E8h]
  void **v98; // [rsp+A8h] [rbp-E0h] BYREF
  PSGSI1::EnumPubsByAddr *v99[2]; // [rsp+B0h] [rbp-D8h]
  int v100; // [rsp+C0h] [rbp-C8h]
  __int64 v101; // [rsp+C8h] [rbp-C0h]
  __int64 v102; // [rsp+D0h] [rbp-B8h]
  __int16 v103; // [rsp+D8h] [rbp-B0h]
  const struct SYMTYPE *v104; // [rsp+E0h] [rbp-A8h]
  unsigned int (__fastcall *v105)(struct PDB *, unsigned __int64); // [rsp+E8h] [rbp-A0h]
  char *v106; // [rsp+F0h] [rbp-98h]
  void **v107; // [rsp+F8h] [rbp-90h] BYREF
  void *v108[2]; // [rsp+100h] [rbp-88h]
  int v109; // [rsp+110h] [rbp-78h]
  __int64 v110; // [rsp+118h] [rbp-70h]
  __int64 v111; // [rsp+120h] [rbp-68h]
  __int16 v112; // [rsp+128h] [rbp-60h]
  __int64 v113; // [rsp+130h] [rbp-58h]
  enum PDBErrors *v114; // [rsp+138h] [rbp-50h]
  unsigned __int64 v115; // [rsp+140h] [rbp-48h]
  __int64 v116; // [rsp+148h] [rbp-40h]
  char *v119; // [rsp+1A8h] [rbp+20h] BYREF

  v116 = -2;
  v4 = (PDBCopy *)this;
  v5 = *((_DWORD *)this + 24);
  if ( (v5 & 0x20) != 0 )
    return PDBCopy::ProcessModInMiniPDB((PDBCopy *)this, a2, a3);
  v105 = 0;
  if ( (v5 & 4) != 0 )
  {
    v7 = this[10];
    if ( v7 )
      v105 = (unsigned int (__fastcall *)(struct PDB *, unsigned __int64))((__int64 (__fastcall *)(struct PDB *, __int64))v7)(
                                                                            this[11],
                                                                            1);
  }
  v107 = &pdb_internal::Buffer::`vftable';
  v109 = 0;
  *(_OWORD *)v108 = 0;
  v110 = 0;
  v111 = 0;
  v112 = 257;
  v90 = &pdb_internal::Buffer::`vftable';
  v92 = 0;
  *(_OWORD *)v91 = 0;
  v93 = 0;
  v94 = 0;
  v95 = 257;
  if ( !(*(unsigned int (__fastcall **)(struct Mod *, _QWORD, int *))(*(_QWORD *)a2 + 72LL))(a2, 0, &v96) )
  {
    PDBCopy::SetLastError(v4, *(struct PDB **)v4);
    return 0;
  }
  v8 = v96;
  if ( v96 && !(unsigned int)pdb_internal::Buffer::grow((pdb_internal::Buffer *)&v107, v96) )
  {
    *((_DWORD *)v4 + 25) = 2;
    v9 = (PSGSI1::EnumPubsByAddr *)v108[0];
    if ( v108[0] )
      goto LABEL_284;
    return 0;
  }
  v10 = (char *)v108[1];
  memset_0(v108[1], 0, v8);
  v11 = (PSGSI1::EnumPubsByAddr *)v108[0];
  if ( v108[0] )
  {
    v108[1] = &v10[v8];
  }
  else
  {
    v108[1] = 0;
    v11 = 0;
    v108[0] = 0;
  }
  if ( !(*(unsigned int (__fastcall **)(struct Mod *, PSGSI1::EnumPubsByAddr *, int *))(*(_QWORD *)a2 + 72LL))(
          a2,
          v11,
          &v96) )
  {
    PDBCopy::SetLastError(v4, *(struct PDB **)v4);
    goto LABEL_282;
  }
  v12 = *((_DWORD *)v4 + 24);
  v13 = v12 >> 2;
  LOBYTE(v13) = (v12 & 4) != 0;
  v89 = v13;
  v12 >>= 3;
  LOBYTE(v12) = v12 & 1;
  v88 = v12;
  v104 = 0;
  *(_OWORD *)Destination = 0;
  v86 = 0;
  *(_OWORD *)Src = 0;
  v84 = 0;
  v14 = (unsigned __int8 *)v11 + 4;
  v15 = v91[1];
  v16 = v91[0];
  LODWORD(v87) = v91[0];
  v17 = (unsigned __int8 *)v108[1];
  while ( 1 )
  {
    while ( 1 )
    {
      if ( v14 >= v17 )
      {
        v89 = LODWORD(v91[1]) - (_DWORD)v87;
        if ( LODWORD(v91[1]) == (_DWORD)v87 )
        {
          v66 = (PSGSI1::EnumPubsByAddr *)Src[0];
          if ( Src[0] )
          {
            if ( (unsigned __int64)(2 * ((v84 - (char *)Src[0]) >> 1)) >= 0x1000 )
            {
              if ( (unsigned __int64)Src[0] - *((_QWORD *)Src[0] - 1) - 8 > 0x1F )
                goto LABEL_286;
              v66 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Src[0] - 1);
            }
            PSGSI1::EnumPubsByAddr::release(v66);
            *(_OWORD *)Src = 0;
            v84 = 0;
          }
          v67 = (PSGSI1::EnumPubsByAddr *)Destination[0];
          if ( Destination[0] )
          {
            if ( v86 - (unsigned __int64)Destination[0] >= 0x1000 )
            {
              if ( (unsigned __int64)&Destination[0][-*((_QWORD *)Destination[0] - 1) - 8] > 0x1F )
                goto LABEL_287;
              v67 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Destination[0] - 1);
            }
            PSGSI1::EnumPubsByAddr::release(v67);
            *(_OWORD *)Destination = 0;
            v86 = 0;
          }
          if ( v16 )
            PSGSI1::EnumPubsByAddr::release(v16);
          if ( v11 )
            PSGSI1::EnumPubsByAddr::release(v11);
          return 1;
        }
        v98 = &pdb_internal::Buffer::`vftable';
        v100 = 0;
        *(_OWORD *)v99 = 0;
        v101 = 0;
        v102 = 0;
        v103 = 257;
        LODWORD(v119) = 241;
        if ( !v11 || !(unsigned int)pdb_internal::Buffer::grow((pdb_internal::Buffer *)&v98, 4) )
          goto LABEL_267;
        v68 = v99[1];
        v69 = v99[0];
        if ( v99[0] )
        {
          v70 = (PSGSI1::EnumPubsByAddr *)((char *)v99[1] + 4);
          v99[1] = (PSGSI1::EnumPubsByAddr *)((char *)v99[1] + 4);
          v71 = (_DWORD)v68 + 4;
        }
        else
        {
          v70 = 0;
          v99[1] = 0;
          v69 = 0;
          v99[0] = 0;
          v71 = 0;
        }
        memcpy_avx(v68, v11, 4u);
        v72 = (int)v69;
        if ( v100 + (int)v69 - v71 < 4 )
        {
          if ( (unsigned int)pdb_internal::Buffer::grow((pdb_internal::Buffer *)&v98, 4) )
          {
            v70 = v99[1];
            v69 = v99[0];
            v72 = (int)v99[0];
            goto LABEL_222;
          }
          goto LABEL_267;
        }
LABEL_222:
        if ( v69 )
        {
          v73 = (PSGSI1::EnumPubsByAddr *)((char *)v70 + 4);
          v99[1] = (PSGSI1::EnumPubsByAddr *)((char *)v70 + 4);
          v88 = (_DWORD)v70 + 4;
        }
        else
        {
          v73 = 0;
          v99[1] = 0;
          v69 = 0;
          v99[0] = 0;
          v88 = 0;
          v72 = 0;
        }
        memcpy_avx(v70, &v119, 4u);
        if ( v100 + v72 - v88 < 4 )
        {
          if ( !(unsigned int)pdb_internal::Buffer::grow((pdb_internal::Buffer *)&v98, 4) )
            goto LABEL_267;
          v73 = v99[1];
          v69 = v99[0];
          v72 = (int)v99[0];
        }
        if ( v69 )
        {
          v74 = (PSGSI1::EnumPubsByAddr *)((char *)v73 + 4);
          v99[1] = (PSGSI1::EnumPubsByAddr *)((char *)v73 + 4);
          LODWORD(v119) = (_DWORD)v73 + 4;
        }
        else
        {
          v74 = 0;
          v99[1] = 0;
          v69 = 0;
          v99[0] = 0;
          LODWORD(v119) = 0;
          v72 = 0;
        }
        memcpy_avx(v73, &v89, 4u);
        if ( v16 )
        {
          v75 = v89;
          if ( v89 >= 0 )
          {
            if ( v89 > v100 + v72 - (int)v119 )
            {
              if ( !(unsigned int)pdb_internal::Buffer::grow((pdb_internal::Buffer *)&v98, v89) )
                goto LABEL_267;
              v74 = v99[1];
              v69 = v99[0];
            }
            if ( v69 )
            {
              v99[1] = (PSGSI1::EnumPubsByAddr *)((char *)v74 + v75);
            }
            else
            {
              v99[1] = 0;
              v99[0] = 0;
            }
            memcpy_avx(v74, v16, v75);
            if ( (unsigned int)pdb_internal::Buffer::AppendZeroes((pdb_internal::Buffer *)&v98, -(int)v75 & 3) )
            {
              v76 = v99[0];
              if ( !(*(unsigned int (__fastcall **)(struct Mod *, PSGSI1::EnumPubsByAddr *, _QWORD))(*(_QWORD *)a3 + 24LL))(
                      a3,
                      v99[0],
                      (unsigned int)(LODWORD(v99[1]) - LODWORD(v99[0]))) )
              {
                PDBCopy::SetLastError((PDBCopy *)this, this[1]);
                if ( v76 )
                  PSGSI1::EnumPubsByAddr::release(v76);
                v77 = (PSGSI1::EnumPubsByAddr *)Src[0];
                if ( Src[0] )
                {
                  if ( (unsigned __int64)(2 * ((v84 - (char *)Src[0]) >> 1)) >= 0x1000 )
                  {
                    if ( (unsigned __int64)Src[0] - *((_QWORD *)Src[0] - 1) - 8 > 0x1F )
                      goto LABEL_286;
                    v77 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Src[0] - 1);
                  }
                  PSGSI1::EnumPubsByAddr::release(v77);
                  *(_OWORD *)Src = 0;
                  v84 = 0;
                }
                v78 = (PSGSI1::EnumPubsByAddr *)Destination[0];
                if ( Destination[0] )
                {
                  if ( v86 - (unsigned __int64)Destination[0] >= 0x1000 )
                  {
                    if ( (unsigned __int64)&Destination[0][-*((_QWORD *)Destination[0] - 1) - 8] > 0x1F )
                      goto LABEL_287;
                    v78 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Destination[0] - 1);
                  }
                  PSGSI1::EnumPubsByAddr::release(v78);
                  *(_OWORD *)Destination = 0;
                  v86 = 0;
                }
                PSGSI1::EnumPubsByAddr::release(v16);
                PSGSI1::EnumPubsByAddr::release(v11);
                return 0;
              }
              if ( v76 )
                PSGSI1::EnumPubsByAddr::release(v76);
              v79 = (PSGSI1::EnumPubsByAddr *)Src[0];
              if ( Src[0] )
              {
                if ( (unsigned __int64)(2 * ((v84 - (char *)Src[0]) >> 1)) >= 0x1000 )
                {
                  if ( (unsigned __int64)Src[0] - *((_QWORD *)Src[0] - 1) - 8 > 0x1F )
                    goto LABEL_286;
                  v79 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Src[0] - 1);
                }
                PSGSI1::EnumPubsByAddr::release(v79);
                *(_OWORD *)Src = 0;
                v84 = 0;
              }
              v80 = (PSGSI1::EnumPubsByAddr *)Destination[0];
              if ( Destination[0] )
              {
                if ( v86 - (unsigned __int64)Destination[0] >= 0x1000 )
                {
                  if ( (unsigned __int64)&Destination[0][-*((_QWORD *)Destination[0] - 1) - 8] > 0x1F )
                    goto LABEL_287;
                  v80 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Destination[0] - 1);
                }
                PSGSI1::EnumPubsByAddr::release(v80);
                *(_OWORD *)Destination = 0;
                v86 = 0;
              }
              PSGSI1::EnumPubsByAddr::release(v16);
              PSGSI1::EnumPubsByAddr::release(v11);
              return 1;
            }
LABEL_267:
            v69 = v99[0];
          }
        }
        *((_DWORD *)this + 25) = 2;
        if ( v69 )
          PSGSI1::EnumPubsByAddr::release(v69);
        v81 = (PSGSI1::EnumPubsByAddr *)Src[0];
        if ( Src[0] )
        {
          if ( (unsigned __int64)(2 * ((v84 - (char *)Src[0]) >> 1)) >= 0x1000 )
          {
            if ( (unsigned __int64)Src[0] - *((_QWORD *)Src[0] - 1) - 8 > 0x1F )
              goto LABEL_286;
            v81 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Src[0] - 1);
          }
          PSGSI1::EnumPubsByAddr::release(v81);
          *(_OWORD *)Src = 0;
          v84 = 0;
        }
        v82 = (PSGSI1::EnumPubsByAddr *)Destination[0];
        if ( Destination[0] )
        {
          if ( v86 - (unsigned __int64)Destination[0] >= 0x1000 )
          {
            if ( (unsigned __int64)&Destination[0][-*((_QWORD *)Destination[0] - 1) - 8] > 0x1F )
              goto LABEL_287;
            v82 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Destination[0] - 1);
          }
          PSGSI1::EnumPubsByAddr::release(v82);
          *(_OWORD *)Destination = 0;
          v86 = 0;
        }
        if ( !v16 )
          goto LABEL_282;
        goto LABEL_281;
      }
      v18 = (PDBCopy *)((char *)v4 + 100);
      v114 = v18;
      v19 = pbEndSym((const struct SYMTYPE *)v14, v17, v18);
      v97 = v19;
      if ( *(_DWORD *)v18 )
      {
        v20 = (PSGSI1::EnumPubsByAddr *)Src[0];
        if ( Src[0] )
        {
          if ( (unsigned __int64)(2 * ((v84 - (char *)Src[0]) >> 1)) >= 0x1000 )
          {
            if ( (unsigned __int64)Src[0] - *((_QWORD *)Src[0] - 1) - 8 > 0x1F )
              goto LABEL_286;
            v20 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Src[0] - 1);
          }
          PSGSI1::EnumPubsByAddr::release(v20);
          *(_OWORD *)Src = 0;
          v84 = 0;
        }
        v21 = (PSGSI1::EnumPubsByAddr *)Destination[0];
        if ( !Destination[0] )
          goto LABEL_30;
        if ( v86 - (unsigned __int64)Destination[0] < 0x1000 )
        {
LABEL_29:
          PSGSI1::EnumPubsByAddr::release(v21);
          *(_OWORD *)Destination = 0;
          v86 = 0;
LABEL_30:
          if ( !v16 )
            goto LABEL_282;
LABEL_281:
          PSGSI1::EnumPubsByAddr::release(v16);
LABEL_282:
          if ( v11 )
          {
            v9 = v11;
            goto LABEL_284;
          }
          return 0;
        }
        if ( (unsigned __int64)&Destination[0][-*((_QWORD *)Destination[0] - 1) - 8] <= 0x1F )
        {
          v21 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Destination[0] - 1);
          goto LABEL_29;
        }
LABEL_287:
        __fastfail(5u);
      }
      if ( v19 > v17 )
      {
        *(_DWORD *)v18 = 13;
        v22 = (PSGSI1::EnumPubsByAddr *)Src[0];
        if ( !Src[0] )
          goto LABEL_38;
        if ( (unsigned __int64)(2 * ((v84 - (char *)Src[0]) >> 1)) < 0x1000 )
          goto LABEL_37;
        if ( (unsigned __int64)Src[0] - *((_QWORD *)Src[0] - 1) - 8 <= 0x1F )
        {
          v22 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Src[0] - 1);
LABEL_37:
          PSGSI1::EnumPubsByAddr::release(v22);
          *(_OWORD *)Src = 0;
          v84 = 0;
LABEL_38:
          v23 = (PSGSI1::EnumPubsByAddr *)Destination[0];
          if ( Destination[0] )
          {
            if ( v86 - (unsigned __int64)Destination[0] >= 0x1000 )
            {
              if ( (unsigned __int64)&Destination[0][-*((_QWORD *)Destination[0] - 1) - 8] > 0x1F )
                goto LABEL_287;
              v23 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Destination[0] - 1);
            }
            PSGSI1::EnumPubsByAddr::release(v23);
            *(_OWORD *)Destination = 0;
            v86 = 0;
          }
          if ( !v16 )
            goto LABEL_282;
          goto LABEL_281;
        }
LABEL_286:
        __fastfail(5u);
      }
      if ( (_BYTE)v89 && *((_WORD *)v14 + 1) == 4121 )
        break;
      v53 = *((_WORD *)v14 + 1);
      if ( (unsigned __int16)(v53 - 4367) > 1u && (unsigned __int16)(v53 - 4466) > 1u )
      {
        if ( v53 == 6 )
        {
          if ( v14 != (unsigned __int8 *)v104 )
            goto LABEL_116;
          v48 = (_DWORD)v97 - (_DWORD)v14;
          if ( (int)v97 - (int)v14 < 0 )
            goto LABEL_138;
          if ( v48 > v92 + (int)v87 - (int)v15 )
          {
            v54 = pdb_internal::Buffer::grow((pdb_internal::Buffer *)&v90, v48);
            v16 = v91[0];
            if ( !v54 )
            {
LABEL_138:
              *(_DWORD *)v18 = 2;
              if ( Src[0] )
              {
                std::allocator<wchar_t>::deallocate(Src, Src[0], (v84 - (char *)Src[0]) >> 1);
                *(_OWORD *)Src = 0;
                v84 = 0;
              }
              v55 = (PSGSI1::EnumPubsByAddr *)Destination[0];
              if ( Destination[0] )
              {
                if ( v86 - (unsigned __int64)Destination[0] >= 0x1000 )
                {
                  if ( (unsigned __int64)&Destination[0][-*((_QWORD *)Destination[0] - 1) - 8] > 0x1F )
                    goto LABEL_287;
                  v55 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Destination[0] - 1);
                }
                PSGSI1::EnumPubsByAddr::release(v55);
                *(_OWORD *)Destination = 0;
                v86 = 0;
              }
              if ( !v16 )
                goto LABEL_282;
              goto LABEL_146;
            }
            v15 = v91[1];
            LODWORD(v87) = v91[0];
          }
          v104 = 0;
        }
        else
        {
          if ( v53 != 4402 )
            goto LABEL_116;
          v48 = (_DWORD)v97 - (_DWORD)v14;
          if ( (int)v97 - (int)v14 < 0 )
            goto LABEL_154;
          v56 = *((unsigned int *)v14 + 2);
          if ( v48 > v92 + (int)v87 - (int)v15 )
          {
            v57 = pdb_internal::Buffer::grow((pdb_internal::Buffer *)&v90, v48);
            v16 = v91[0];
            if ( !v57 )
            {
              v18 = v114;
LABEL_154:
              *(_DWORD *)v18 = 2;
              if ( Src[0] )
              {
                std::allocator<wchar_t>::deallocate(Src, Src[0], (v84 - (char *)Src[0]) >> 1);
                *(_OWORD *)Src = 0;
                v84 = 0;
              }
              v58 = (PSGSI1::EnumPubsByAddr *)Destination[0];
              if ( Destination[0] )
              {
                if ( v86 - (unsigned __int64)Destination[0] >= 0x1000 )
                {
                  if ( (unsigned __int64)&Destination[0][-*((_QWORD *)Destination[0] - 1) - 8] > 0x1F )
                    goto LABEL_287;
                  v58 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Destination[0] - 1);
                }
                PSGSI1::EnumPubsByAddr::release(v58);
                *(_OWORD *)Destination = 0;
                v86 = 0;
              }
              if ( !v16 )
                goto LABEL_282;
LABEL_146:
              PSGSI1::EnumPubsByAddr::release(v16);
              goto LABEL_282;
            }
            v15 = v91[1];
            LODWORD(v87) = v91[0];
          }
          v104 = (PSGSI1::EnumPubsByAddr *)((char *)v11 + v56);
        }
        goto LABEL_112;
      }
      v59 = (PSGSI1::EnumPubsByAddr *)((char *)v11 + *((unsigned int *)v14 + 2));
      if ( v59 >= (const struct SYMTYPE *)v17 )
      {
        *((_DWORD *)this + 25) = 13;
        v60 = (PSGSI1::EnumPubsByAddr *)Src[0];
        if ( Src[0] )
        {
          if ( (unsigned __int64)(2 * ((v84 - (char *)Src[0]) >> 1)) >= 0x1000 )
          {
            if ( (unsigned __int64)Src[0] - *((_QWORD *)Src[0] - 1) - 8 > 0x1F )
              goto LABEL_286;
            v60 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Src[0] - 1);
          }
          PSGSI1::EnumPubsByAddr::release(v60);
          *(_OWORD *)Src = 0;
          v84 = 0;
        }
        v61 = (PSGSI1::EnumPubsByAddr *)Destination[0];
        if ( Destination[0] )
        {
          if ( v86 - (unsigned __int64)Destination[0] >= 0x1000 )
          {
            if ( (unsigned __int64)&Destination[0][-*((_QWORD *)Destination[0] - 1) - 8] > 0x1F )
              goto LABEL_287;
            v61 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Destination[0] - 1);
          }
          PSGSI1::EnumPubsByAddr::release(v61);
          *(_OWORD *)Destination = 0;
          v86 = 0;
        }
        if ( !v16 )
          goto LABEL_282;
        goto LABEL_281;
      }
      if ( v53 != 4368 && v53 != 4466
        || (LODWORD(v119) = 0, v62 = pbEndSym(v59, v17, (enum PDBErrors *)&v119), !(_DWORD)v119)
        && v62 < v17
        && *((_WORD *)v62 + 1) == 4402 )
      {
        *((_DWORD *)v14 + 7) = 0;
        v48 = (_DWORD)v97 - (_DWORD)v14;
        if ( (int)v97 - (int)v14 < 0 )
          goto LABEL_186;
        if ( v48 > v92 + (int)v87 - (int)v15 )
        {
          v63 = pdb_internal::Buffer::grow((pdb_internal::Buffer *)&v90, v48);
          v16 = v91[0];
          if ( !v63 )
          {
LABEL_186:
            *((_DWORD *)this + 25) = 2;
            v64 = (PSGSI1::EnumPubsByAddr *)Src[0];
            if ( !Src[0] )
              goto LABEL_191;
            if ( (unsigned __int64)(2 * ((v84 - (char *)Src[0]) >> 1)) < 0x1000 )
              goto LABEL_190;
            if ( (unsigned __int64)Src[0] - *((_QWORD *)Src[0] - 1) - 8 <= 0x1F )
            {
              v64 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Src[0] - 1);
LABEL_190:
              PSGSI1::EnumPubsByAddr::release(v64);
              *(_OWORD *)Src = 0;
              v84 = 0;
LABEL_191:
              v65 = (PSGSI1::EnumPubsByAddr *)Destination[0];
              if ( Destination[0] )
              {
                if ( v86 - (unsigned __int64)Destination[0] >= 0x1000 )
                {
                  if ( (unsigned __int64)&Destination[0][-*((_QWORD *)Destination[0] - 1) - 8] > 0x1F )
                    goto LABEL_287;
                  v65 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Destination[0] - 1);
                }
                PSGSI1::EnumPubsByAddr::release(v65);
                *(_OWORD *)Destination = 0;
                v86 = 0;
              }
              if ( !v16 )
                goto LABEL_282;
              goto LABEL_281;
            }
            goto LABEL_286;
          }
          v15 = v91[1];
          LODWORD(v87) = v91[0];
        }
        v104 = v59;
        goto LABEL_112;
      }
LABEL_116:
      v4 = (PDBCopy *)this;
      v14 = v97;
    }
    if ( !v105 )
      goto LABEL_108;
    v24 = *((unsigned __int16 *)v14 + 5);
    if ( !(_WORD)v24 )
      goto LABEL_116;
    if ( (_BYTE)v88 )
    {
      v25 = (const char *)(v14 + 12);
      v26 = 0;
      if ( v24 - 1 > 0 )
      {
        do
        {
          v25 += strlen_0(v25) + 1;
          ++v26;
        }
        while ( v26 < *((unsigned __int16 *)v14 + 5) - 1 );
      }
      v27 = strlen_0(v25);
      v28 = strlen_0((const char *)v14 + 12);
      try
      {
        v29 = v28 + v27 + 2;
        std::vector<unsigned char>::_Resize<std::_Value_init_tag>(Destination, v29, &v119);
        v119 = Destination[0];
        strcpy_s(Destination[0], v29, (const char *)v14 + 12);
        _o_strcat_s(v119, v29, ";");
        _o_strcat_s(v119, v29, v25);
        v31 = v119;
      }
      catch ( std::bad_alloc )
      {
        *((_DWORD *)this + 25) = 2;
        if ( Src[0] )
        {
          std::allocator<wchar_t>::deallocate(Src, Src[0], (v84 - (char *)Src[0]) >> 1);
          *(_OWORD *)Src = 0;
          v84 = 0;
        }
        v30 = (PSGSI1::EnumPubsByAddr *)Destination[0];
        if ( Destination[0] )
        {
          if ( v86 - (unsigned __int64)Destination[0] >= 0x1000 )
          {
            if ( (unsigned __int64)&Destination[0][-*((_QWORD *)Destination[0] - 1) - 8] > 0x1F )
              goto LABEL_287;
            v30 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Destination[0] - 1);
          }
          PSGSI1::EnumPubsByAddr::release(v30);
          *(_OWORD *)Destination = 0;
          v86 = 0;
        }
        if ( v91[0] )
          PSGSI1::EnumPubsByAddr::release(v91[0]);
        v9 = (PSGSI1::EnumPubsByAddr *)v108[0];
        if ( v108[0] )
          goto LABEL_284;
        return 0;
      }
    }
    else
    {
      v31 = (char *)(v14 + 12);
      v119 = (char *)(v14 + 12);
    }
    v32 = UnicodeLengthOfUTF8(v31);
    try
    {
      v34 = v32;
      v113 = v32;
      v35 = 2 * v32;
      v106 = (char *)Src[1];
      v36 = (unsigned __int64)Src[0];
      v37 = ((char *)Src[1] - (char *)Src[0]) >> 1;
      v115 = v37;
      if ( v35 < v37 )
      {
        v38 = (char *)Src[0] + 2 * v35;
LABEL_91:
        Src[1] = v38;
        goto LABEL_298;
      }
      if ( v35 <= v37 )
        goto LABEL_298;
      v39 = (v84 - (char *)Src[0]) >> 1;
      if ( v35 <= v39 )
      {
        v46 = 2 * (v35 - v37);
        memset_0(Src[1], 0, v46);
        v38 = &v106[v46];
        v36 = (unsigned __int64)Src[0];
        v34 = v113;
        goto LABEL_91;
      }
      if ( v35 > 0x7FFFFFFFFFFFFFFFLL )
        std::vector<TPI1::PRECEX>::_Xlength(v39, v33, 0x7FFFFFFFFFFFFFFFLL);
      v40 = v39 >> 1;
      if ( v39 > 0x7FFFFFFFFFFFFFFFLL - (v39 >> 1) )
LABEL_290:
        std::_Throw_bad_array_new_length();
      v41 = v40 + v39;
      if ( v40 + v39 >= v35 )
      {
        if ( v41 > 0x7FFFFFFFFFFFFFFFLL )
          std::_Throw_bad_array_new_length();
      }
      else
      {
        v41 = v35;
      }
      v42 = 2 * v41 == 0;
      v43 = 2 * v41;
      v106 = (char *)v43;
      if ( v42 )
      {
        v36 = 0;
      }
      else if ( v43 < 0x1000 )
      {
        v36 = (unsigned __int64)operator new(v43);
      }
      else
      {
        if ( v43 + 39 < v43 )
          goto LABEL_290;
        v44 = operator new(v43 + 39);
        if ( !v44 )
LABEL_89:
          __fastfail(5u);
        v36 = ((unsigned __int64)v44 + 39) & 0xFFFFFFFFFFFFFFE0uLL;
        *(_QWORD *)(v36 - 8) = v44;
      }
      memset_0((void *)(v36 + 2 * v115), 0, 2 * (v35 - v115));
      memmove_0((void *)v36, Src[0], (char *)Src[1] - (char *)Src[0]);
      v45 = (PSGSI1::EnumPubsByAddr *)Src[0];
      if ( Src[0] )
      {
        if ( (unsigned __int64)(2 * ((v84 - (char *)Src[0]) >> 1)) >= 0x1000 )
        {
          if ( (unsigned __int64)Src[0] - *((_QWORD *)Src[0] - 1) - 8 > 0x1F )
            goto LABEL_89;
          v45 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Src[0] - 1);
        }
        PSGSI1::EnumPubsByAddr::release(v45);
      }
      Src[0] = (void *)v36;
      Src[1] = (void *)(v36 + 2 * v35);
      v84 = &v106[v36];
      v34 = v113;
    }
    catch ( std::bad_alloc )
    {
      *((_DWORD *)this + 25) = 2;
      if ( Src[0] )
      {
        std::allocator<wchar_t>::deallocate(Src, Src[0], (v84 - (char *)Src[0]) >> 1);
        *(_OWORD *)Src = 0;
        v84 = 0;
      }
      v47 = (PSGSI1::EnumPubsByAddr *)Destination[0];
      if ( !Destination[0] )
        goto LABEL_103;
      if ( v86 - (unsigned __int64)Destination[0] < 0x1000 )
        goto LABEL_102;
      if ( (unsigned __int64)&Destination[0][-*((_QWORD *)Destination[0] - 1) - 8] > 0x1F )
        goto LABEL_287;
      v47 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Destination[0] - 1);
LABEL_102:
      PSGSI1::EnumPubsByAddr::release(v47);
      *(_OWORD *)Destination = 0;
      v86 = 0;
LABEL_103:
      if ( v91[0] )
        PSGSI1::EnumPubsByAddr::release(v91[0]);
      v9 = (PSGSI1::EnumPubsByAddr *)v108[0];
      if ( v108[0] )
LABEL_284:
        PSGSI1::EnumPubsByAddr::release(v9);
      return 0;
    }
LABEL_298:
    if ( v36 )
    {
      UTF8ToUnicode(v119, v36, v34);
      v36 = (unsigned __int64)Src[0];
    }
    v4 = (PDBCopy *)this;
    if ( v105(this[11], v36) )
    {
      v18 = v114;
      LODWORD(v19) = (_DWORD)v97;
LABEL_108:
      v48 = (_DWORD)v19 - (_DWORD)v14;
      if ( (int)v19 - (int)v14 < 0 )
        goto LABEL_117;
      if ( v48 > v92 + (int)v87 - (int)v15 )
      {
        v49 = pdb_internal::Buffer::grow((pdb_internal::Buffer *)&v90, v48);
        v16 = v91[0];
        if ( !v49 )
        {
LABEL_117:
          *(_DWORD *)v18 = 2;
          v51 = (PSGSI1::EnumPubsByAddr *)Src[0];
          if ( Src[0] )
          {
            if ( (unsigned __int64)(2 * ((v84 - (char *)Src[0]) >> 1)) >= 0x1000 )
            {
              if ( (unsigned __int64)Src[0] - *((_QWORD *)Src[0] - 1) - 8 > 0x1F )
                goto LABEL_286;
              v51 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Src[0] - 1);
            }
            PSGSI1::EnumPubsByAddr::release(v51);
            *(_OWORD *)Src = 0;
            v84 = 0;
          }
          v52 = (PSGSI1::EnumPubsByAddr *)Destination[0];
          if ( Destination[0] )
          {
            if ( v86 - (unsigned __int64)Destination[0] >= 0x1000 )
            {
              if ( (unsigned __int64)&Destination[0][-*((_QWORD *)Destination[0] - 1) - 8] > 0x1F )
                goto LABEL_287;
              v52 = (PSGSI1::EnumPubsByAddr *)*((_QWORD *)Destination[0] - 1);
            }
            PSGSI1::EnumPubsByAddr::release(v52);
            *(_OWORD *)Destination = 0;
            v86 = 0;
          }
          if ( !v16 )
            goto LABEL_282;
          goto LABEL_281;
        }
        v15 = v91[1];
        v87 = v91[0];
      }
LABEL_112:
      v50 = v15;
      if ( v16 )
      {
        v15 = (PSGSI1::EnumPubsByAddr *)((char *)v15 + v48);
        v91[1] = v15;
      }
      else
      {
        v15 = 0;
        v91[1] = 0;
        v16 = 0;
        v91[0] = 0;
        LODWORD(v87) = 0;
      }
      memcpy_avx(v50, v14, v48);
      v17 = (unsigned __int8 *)v108[1];
      goto LABEL_116;
    }
    v17 = (unsigned __int8 *)v108[1];
    v14 = v97;
  }
}

```

## disassembly

```asm
0x18002f020  mov     [rsp+arg_10], r8
0x18002f025  mov     [rsp+arg_0], rcx
0x18002f02a  push    rbx
0x18002f02b  push    rsi
0x18002f02c  push    rdi
0x18002f02d  push    r12
0x18002f02f  push    r13
0x18002f031  push    r14
0x18002f033  push    r15
0x18002f035  sub     rsp, 150h
0x18002f03c  mov     [rsp+188h+var_40], 0FFFFFFFFFFFFFFFEh
0x18002f048  mov     rbx, rdx
0x18002f04b  mov     r12, rcx
0x18002f04e  mov     eax, [rcx+60h]
0x18002f051  test    al, 20h
0x18002f053  jz      short loc_18002F05F
0x18002f055  call    ?ProcessModInMiniPDB@PDBCopy@@AEAAHPEAUMod@@0@Z; PDBCopy::ProcessModInMiniPDB(Mod *,Mod *)
0x18002f05a  jmp     loc_1800303A6
0x18002f05f  xor     edi, edi
0x18002f061  mov     [rsp+188h+var_A0], rdi
0x18002f069  test    al, 4
0x18002f06b  jz      short loc_18002F08D
0x18002f06d  mov     rax, [rcx+50h]
0x18002f071  test    rax, rax
0x18002f074  jz      short loc_18002F08D
0x18002f076  mov     edx, 1
0x18002f07b  mov     rcx, [rcx+58h]
0x18002f07f  call    cs:__guard_dispatch_icall_fptr
0x18002f085  mov     [rsp+188h+var_A0], rax
0x18002f08d  lea     rax, ??_7Buffer@pdb_internal@@6B@; const pdb_internal::Buffer::`vftable'
0x18002f094  mov     [rsp+188h+var_90], rax
0x18002f09c  mov     [rsp+188h+var_78], edi
0x18002f0a3  xorps   xmm0, xmm0
0x18002f0a6  movdqu  xmmword ptr [rsp+188h+var_88], xmm0
0x18002f0af  mov     [rsp+188h+var_70], rdi
0x18002f0b7  mov     [rsp+188h+var_68], rdi
0x18002f0bf  mov     [rsp+188h+var_60], 101h
0x18002f0c9  mov     [rsp+188h+var_128], rax
0x18002f0ce  mov     [rsp+188h+var_110], edi
0x18002f0d2  movdqu  xmmword ptr [rsp+188h+var_120], xmm0
0x18002f0d8  mov     [rsp+188h+var_108], rdi
0x18002f0e0  mov     [rsp+188h+var_100], rdi
0x18002f0e8  mov     [rsp+188h+var_F8], 101h
0x18002f0f2  mov     rax, [rbx]
0x18002f0f5  lea     r8, [rsp+188h+var_F0]
0x18002f0fd  xor     edx, edx
0x18002f0ff  mov     rcx, rbx
0x18002f102  mov     rax, [rax+48h]
0x18002f106  call    cs:__guard_dispatch_icall_fptr
0x18002f10c  test    eax, eax
0x18002f10e  jnz     short loc_18002F122
0x18002f110  mov     rdx, [r12]; struct PDB *
0x18002f114  mov     rcx, r12; this
0x18002f117  call    ?SetLastError@PDBCopy@@QEAAXPEAUPDB@@@Z; PDBCopy::SetLastError(PDB *)
0x18002f11c  nop
0x18002f11d  jmp     loc_1800303A4
0x18002f122  movsxd  rsi, [rsp+188h+var_F0]
0x18002f12a  test    esi, esi
0x18002f12c  jz      short loc_18002F160
0x18002f12e  mov     edx, esi; int
0x18002f130  lea     rcx, [rsp+188h+var_90]; this
0x18002f138  call    ?grow@Buffer@pdb_internal@@AEAAHJ@Z; pdb_internal::Buffer::grow(long)
0x18002f13d  test    eax, eax
0x18002f13f  jnz     short loc_18002F160
0x18002f141  mov     dword ptr [r12+64h], 2
0x18002f14a  mov     rcx, [rsp+188h+var_88]
0x18002f152  test    rcx, rcx
0x18002f155  jz      loc_1800303A4
0x18002f15b  jmp     loc_18003039E
0x18002f160  mov     r8, rsi; Size
0x18002f163  xor     edx, edx; Val
0x18002f165  mov     r15, [rsp+188h+var_88+8]
0x18002f16d  mov     rcx, r15; void *
0x18002f170  call    memset_0
0x18002f175  mov     r14, [rsp+188h+var_88]
0x18002f17d  test    r14, r14
0x18002f180  jnz     short loc_18002F197
0x18002f182  mov     [rsp+188h+var_88+8], rdi
0x18002f18a  mov     r14, rdi
0x18002f18d  mov     [rsp+188h+var_88], rdi
0x18002f195  jmp     short loc_18002F1A2
0x18002f197  add     r15, rsi
0x18002f19a  mov     [rsp+188h+var_88+8], r15
0x18002f1a2  mov     rax, [rbx]
0x18002f1a5  lea     r8, [rsp+188h+var_F0]
0x18002f1ad  mov     rdx, r14
0x18002f1b0  mov     rcx, rbx
0x18002f1b3  mov     rax, [rax+48h]
0x18002f1b7  call    cs:__guard_dispatch_icall_fptr
0x18002f1bd  test    eax, eax
0x18002f1bf  jnz     short loc_18002F1D3
0x18002f1c1  mov     rdx, [r12]; struct PDB *
0x18002f1c5  mov     rcx, r12; this
0x18002f1c8  call    ?SetLastError@PDBCopy@@QEAAXPEAUPDB@@@Z; PDBCopy::SetLastError(PDB *)
0x18002f1cd  nop
0x18002f1ce  jmp     loc_180030396
0x18002f1d3  mov     eax, [r12+60h]
0x18002f1d8  mov     ecx, eax
0x18002f1da  shr     ecx, 2
0x18002f1dd  and     cl, 1
0x18002f1e0  mov     [rsp+188h+var_12C], ecx
0x18002f1e4  shr     eax, 3
0x18002f1e7  and     al, 1
0x18002f1e9  mov     [rsp+188h+var_130], eax
0x18002f1ed  mov     [rsp+188h+var_A8], rdi
0x18002f1f5  xorps   xmm0, xmm0
0x18002f1f8  movdqu  xmmword ptr [rsp+188h+Destination], xmm0
0x18002f1fe  mov     [rsp+188h+var_140], rdi
0x18002f203  movdqu  xmmword ptr [rsp+188h+Src], xmm0
0x18002f209  mov     [rsp+188h+var_158], rdi
0x18002f20e  lea     r13, [r14+4]
0x18002f212  mov     r15, [rsp+188h+var_120+8]
0x18002f217  mov     rsi, [rsp+188h+var_120]
0x18002f21c  mov     dword ptr [rsp+188h+var_138], esi
0x18002f220  mov     rbx, [rsp+188h+var_88+8]
0x18002f228  nop     dword ptr [rax+rax+00000000h]
0x18002f230  cmp     r13, rbx
0x18002f233  jnb     loc_18002FDB1
0x18002f239  add     r12, 64h ; 'd'
0x18002f23d  mov     [rsp+188h+var_50], r12
0x18002f245  mov     r8, r12; enum PDBErrors *
0x18002f248  mov     rdx, rbx; void *
0x18002f24b  mov     rcx, r13; struct SYMTYPE *
0x18002f24e  call    ?pbEndSym@@YAPEAEPEBUSYMTYPE@@PEBXPEAW4PDBErrors@@@Z; pbEndSym(SYMTYPE const *,void const *,PDBErrors *)
0x18002f253  mov     [rsp+188h+var_E8], rax
0x18002f25b  cmp     dword ptr [r12], 0
0x18002f260  jz      loc_18002F314
0x18002f266  mov     rcx, [rsp+188h+Src]
0x18002f26b  test    rcx, rcx
0x18002f26e  jz      short loc_18002F2B7
0x18002f270  mov     rax, [rsp+188h+var_158]
0x18002f275  sub     rax, rcx
0x18002f278  sar     rax, 1
0x18002f27b  lea     rdx, [rax+rax]
0x18002f27f  cmp     rdx, 1000h
0x18002f286  jb      short loc_18002F2A4
0x18002f288  mov     rax, [rcx-8]
0x18002f28c  sub     rcx, rax
0x18002f28f  sub     rcx, 8
0x18002f293  cmp     rcx, 1Fh
0x18002f297  ja      loc_1800303B9
0x18002f29d  add     rdx, 27h ; '''
0x18002f2a1  mov     rcx, rax; this
0x18002f2a4  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x18002f2a9  xorps   xmm0, xmm0
0x18002f2ac  movdqu  xmmword ptr [rsp+188h+Src], xmm0
0x18002f2b2  mov     [rsp+188h+var_158], rdi
0x18002f2b7  mov     rcx, [rsp+188h+Destination]
0x18002f2bc  test    rcx, rcx
0x18002f2bf  jz      short loc_18002F301
0x18002f2c1  mov     rdx, [rsp+188h+var_140]
0x18002f2c6  sub     rdx, rcx
0x18002f2c9  cmp     rdx, 1000h
0x18002f2d0  jb      short loc_18002F2EE
0x18002f2d2  mov     rax, [rcx-8]
0x18002f2d6  sub     rcx, rax
0x18002f2d9  sub     rcx, 8
0x18002f2dd  cmp     rcx, 1Fh
0x18002f2e1  ja      loc_1800303C0
0x18002f2e7  add     rdx, 27h ; '''
0x18002f2eb  mov     rcx, rax; this
0x18002f2ee  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x18002f2f3  xorps   xmm0, xmm0
0x18002f2f6  movdqu  xmmword ptr [rsp+188h+Destination], xmm0
0x18002f2fc  mov     [rsp+188h+var_140], rdi
0x18002f301  test    rsi, rsi
0x18002f304  jz      short loc_18002F30F
0x18002f306  mov     rcx, rsi; this
0x18002f309  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x18002f30e  nop
0x18002f30f  jmp     loc_180030396
0x18002f314  cmp     rax, rbx
0x18002f317  jbe     loc_18002F3D3
0x18002f31d  mov     dword ptr [r12], 0Dh
0x18002f325  mov     rcx, [rsp+188h+Src]
0x18002f32a  test    rcx, rcx
0x18002f32d  jz      short loc_18002F376
0x18002f32f  mov     rax, [rsp+188h+var_158]
0x18002f334  sub     rax, rcx
0x18002f337  sar     rax, 1
0x18002f33a  lea     rdx, [rax+rax]
0x18002f33e  cmp     rdx, 1000h
0x18002f345  jb      short loc_18002F363
0x18002f347  mov     rax, [rcx-8]
0x18002f34b  sub     rcx, rax
0x18002f34e  sub     rcx, 8
0x18002f352  cmp     rcx, 1Fh
0x18002f356  ja      loc_1800303B9
0x18002f35c  add     rdx, 27h ; '''
0x18002f360  mov     rcx, rax; this
0x18002f363  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x18002f368  xorps   xmm0, xmm0
0x18002f36b  movdqu  xmmword ptr [rsp+188h+Src], xmm0
0x18002f371  mov     [rsp+188h+var_158], rdi
0x18002f376  mov     rcx, [rsp+188h+Destination]
0x18002f37b  test    rcx, rcx
0x18002f37e  jz      short loc_18002F3C0
0x18002f380  mov     rdx, [rsp+188h+var_140]
0x18002f385  sub     rdx, rcx
0x18002f388  cmp     rdx, 1000h
0x18002f38f  jb      short loc_18002F3AD
0x18002f391  mov     rax, [rcx-8]
0x18002f395  sub     rcx, rax
0x18002f398  sub     rcx, 8
0x18002f39c  cmp     rcx, 1Fh
0x18002f3a0  ja      loc_1800303C0
0x18002f3a6  add     rdx, 27h ; '''
0x18002f3aa  mov     rcx, rax; this
0x18002f3ad  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x18002f3b2  xorps   xmm0, xmm0
0x18002f3b5  movdqu  xmmword ptr [rsp+188h+Destination], xmm0
0x18002f3bb  mov     [rsp+188h+var_140], rdi
0x18002f3c0  test    rsi, rsi
0x18002f3c3  jz      short loc_18002F3CE
0x18002f3c5  mov     rcx, rsi; this
0x18002f3c8  call    ?release@EnumPubsByAddr@PSGSI1@@UEAAXXZ; PSGSI1::EnumPubsByAddr::release(void)
0x18002f3cd  nop
0x18002f3ce  jmp     loc_180030396
0x18002f3d3  cmp     byte ptr [rsp+188h+var_12C], 0
0x18002f3d8  jz      loc_18002F97A
0x18002f3de  mov     ecx, 1019h
0x18002f3e3  cmp     [r13+2], cx
0x18002f3e8  jnz     loc_18002F97A
0x18002f3ee  cmp     [rsp+188h+var_A0], 0
0x18002f3f7  jz      loc_18002F841
0x18002f3fd  movzx   eax, word ptr [r13+0Ah]
0x18002f402  test    ax, ax
0x18002f405  jz      loc_18002F8AF
0x18002f40b  lea     rcx, [r13+0Ch]
0x18002f40f  cmp     byte ptr [rsp+188h+var_130], 0
0x18002f414  jz      loc_18002F56C
0x18002f41a  mov     r12, rcx
0x18002f41d  movzx   ebx, di
0x18002f420  dec     eax
0x18002f422  test    eax, eax
0x18002f424  jle     short loc_18002F445
0x18002f426  mov     rcx, r12; Str
0x18002f429  call    strlen_0
0x18002f42e  inc     r12
0x18002f431  add     r12, rax
0x18002f434  inc     bx
0x18002f437  movzx   ecx, word ptr [r13+0Ah]
0x18002f43c  dec     ecx
0x18002f43e  movzx   eax, bx
0x18002f441  cmp     eax, ecx
0x18002f443  jl      short loc_18002F426
0x18002f445  mov     rcx, r12; Str
0x18002f448  call    strlen_0
0x18002f44d  mov     rbx, rax
0x18002f450  lea     rcx, [r13+0Ch]; Str
0x18002f454  call    strlen_0
0x18002f459  add     rbx, 2
0x18002f45d  add     rbx, rax
0x18002f460  lea     r8, [rsp+188h+arg_18]
0x18002f468  mov     rdx, rbx
0x18002f46b  lea     rcx, [rsp+188h+Destination]
0x18002f470  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002f475  nop
0x18002f476  mov     rcx, [rsp+188h+Destination]; Destination
0x18002f47b  mov     [rsp+188h+arg_18], rcx
0x18002f483  lea     r8, [r13+0Ch]; Source
0x18002f487  mov     rdx, rbx; SizeInBytes
0x18002f48a  call    cs:__imp_strcpy_s
0x18002f490  lea     r8, asc_18022D160; ";"
0x18002f497  mov     rdx, rbx
0x18002f49a  mov     rcx, [rsp+188h+arg_18]
0x18002f4a2  call    cs:__imp__o_strcat_s
0x18002f4a8  mov     r8, r12
0x18002f4ab  mov     rdx, rbx
0x18002f4ae  mov     rcx, [rsp+188h+arg_18]
0x18002f4b6  call    cs:__imp__o_strcat_s
0x18002f4bc  mov     rax, [rsp+188h+arg_18]
0x18002f4c4  jmp     loc_18002F577
0x18002f4c9  mov     rdx, [rsp+188h+Src]
0x18002f4ce  test    rdx, rdx
0x18002f4d1  jz      short loc_18002F4FA
0x18002f4d3  mov     r8, [rsp+188h+var_158]
0x18002f4d8  sub     r8, rdx
0x18002f4db  sar     r8, 1
0x18002f4de  lea     rcx, [rsp+188h+Src]
0x18002f4e3  call    ?deallocate@?$allocator@_W@std@@QEAAXQEA_W_K@Z; std::allocator<wchar_t>::deallocate(wchar_t * const,unsigned __int64)
0x18002f4e8  xorps   xmm0, xmm0
0x18002f4eb  movdqu  xmmword ptr [rsp+188h+Src], xmm0
0x18002f4f1  xor     edi, edi
0x18002f4f3  mov     [rsp+188h+var_158], rdi
0x18002f4f8  jmp     short loc_18002F4FC
0x18002f4fa  xor     edi, edi
0x18002f4fc  mov     rcx, [rsp+188h+Destination]
0x18002f501  test    rcx, rcx
0x18002f504  jz      short loc_18002F546
0x18002f506  mov     rdx, [rsp+188h+var_140]
0x18002f50b  sub     rdx, rcx
0x18002f50e  cmp     rdx, 1000h
0x18002f515  jb      short loc_18002F533
0x18002f517  mov     rax, [rcx-8]
0x18002f51b  sub     rcx, rax
0x18002f51e  sub     rcx, 8
0x18002f522  cmp     rcx, 1Fh
0x18002f526  ja      loc_1800303C0
0x18002f52c  add     rdx, 27h ; '''
  ... truncated ...
```
