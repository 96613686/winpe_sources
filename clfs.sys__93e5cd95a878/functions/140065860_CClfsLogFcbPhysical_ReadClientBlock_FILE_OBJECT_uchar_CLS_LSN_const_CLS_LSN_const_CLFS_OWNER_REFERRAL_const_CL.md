# CClfsLogFcbPhysical::ReadClientBlock(_FILE_OBJECT *,uchar,_CLS_LSN const &,_CLS_LSN const &,_CLFS_OWNER_REFERRAL const &,_CLFS_OWNER_ENTRY const * const,ulong,_CLFS_READ_BUFFER const &,ulong,IClfsRequestAsync *,ulong,_CLS_LSN &,ulong &)

- ea: `0x140065860`
- end: `0x1400664a7`
- name: `?ReadClientBlock@CClfsLogFcbPhysical@@QEAAJPEAU_FILE_OBJECT@@EAEBT_CLS_LSN@@1AEBU_CLFS_OWNER_REFERRAL@@QEBU_CLFS_OWNER_ENTRY@@KAEBU_CLFS_READ_BUFFER@@KPEAUIClfsRequestAsync@@KAEAT3@AEAK@Z`
- size: `3143`
- prototype: `int(CClfsLogFcbPhysical *__hidden this, struct _FILE_OBJECT *, unsigned __int8, const union _CLS_LSN *, const union _CLS_LSN *, const struct _CLFS_OWNER_REFERRAL *, const struct _CLFS_OWNER_ENTRY *const, unsigned int, const struct _CLFS_READ_BUFFER *, unsigned int, struct IClfsRequestAsync *, unsigned int, union _CLS_LSN *, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x140064b00`

## callees

- `0x140003590`
- `0x140005f00`
- `0x1400166f8`
- `0x14001685c`
- `0x140017f20`
- `0x140017f80`
- `0x140018280`
- `0x140065860`
- `0x1400664b0`
- `0x140066cc0`
- `0x140066e90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140066347`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066347`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400662aa`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400662aa`

## pseudocode

```c
__int64 __fastcall CClfsLogFcbPhysical::ReadClientBlock(
        CClfsLogFcbPhysical *this,
        struct _FILE_OBJECT *a2,
        char a3,
        const union _CLS_LSN *a4,
        const union _CLS_LSN *a5,
        const struct _CLFS_OWNER_REFERRAL *a6,
        const struct _CLFS_OWNER_ENTRY *a7,
        unsigned int a8,
        const struct _CLFS_READ_BUFFER *a9,
        unsigned int a10,
        struct IClfsRequestAsync *a11,
        unsigned int a12,
        union _CLS_LSN *a13,
        unsigned int *a14)
{
  const CLFS_LSN *v14; // r15
  __int64 v15; // rax
  unsigned int v16; // ecx
  __int64 v17; // rsi
  __int64 v18; // rbx
  CLFS_CONTAINER_ID v19; // eax
  union _CLS_LSN v20; // rdi
  union _CLS_LSN v21; // r8
  char v22; // al
  char *v23; // rcx
  char v24; // al
  int v25; // r14d
  unsigned __int64 v26; // r9
  CLFS_RECORD_INDEX v27; // edx
  __int64 v28; // rcx
  unsigned __int64 v29; // rdx
  unsigned __int64 v30; // rtt
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // rcx
  unsigned __int64 v33; // rbx
  char v34; // al
  ULONGLONG v35; // rcx
  unsigned __int64 v36; // r10
  unsigned __int64 v37; // r11
  unsigned __int64 v38; // r9
  unsigned __int64 v39; // rdx
  char v40; // r10
  const struct _CLFS_OWNER_REFERRAL *v41; // r9
  char i; // al
  char j; // dl
  CLFS_RECORD_INDEX v44; // edx
  CLFS_CONTAINER_ID cidContainer; // eax
  unsigned __int64 v46; // r8
  unsigned __int64 v47; // rdx
  unsigned __int64 v48; // rtt
  unsigned __int64 v49; // rcx
  union _CLS_LSN v50; // rcx
  int v51; // eax
  __int64 v52; // rax
  int v53; // ecx
  unsigned int v54; // eax
  int v55; // ecx
  int v56; // eax
  unsigned int v57; // r15d
  char v58; // al
  unsigned __int64 ullOffset; // r8
  unsigned __int64 v60; // r11
  unsigned __int64 v61; // r9
  unsigned __int64 v62; // r10
  unsigned __int64 v63; // rdx
  char *v64; // r9
  char v65; // al
  char *v66; // rdx
  char v67; // al
  int v68; // ebx
  SIZE_T v69; // rax
  PVOID PoolWithTag; // rax
  void *v71; // rbx
  int v72; // r8d
  int v73; // r9d
  __int128 *v75; // [rsp+20h] [rbp-168h]
  unsigned int v76[2]; // [rsp+70h] [rbp-118h] BYREF
  unsigned int v77; // [rsp+78h] [rbp-110h] BYREF
  int v78; // [rsp+7Ch] [rbp-10Ch]
  unsigned int v79; // [rsp+80h] [rbp-108h]
  unsigned __int64 v80; // [rsp+88h] [rbp-100h]
  CLFS_LSN v81; // [rsp+90h] [rbp-F8h]
  union _CLS_LSN v82; // [rsp+98h] [rbp-F0h] BYREF
  __int64 v83; // [rsp+A0h] [rbp-E8h]
  unsigned int v84; // [rsp+A8h] [rbp-E0h]
  union _CLS_LSN v85; // [rsp+B0h] [rbp-D8h] BYREF
  __int128 v86; // [rsp+B8h] [rbp-D0h] BYREF
  __int64 v87; // [rsp+C8h] [rbp-C0h]
  ULONGLONG v88; // [rsp+D0h] [rbp-B8h]
  __int64 v89; // [rsp+D8h] [rbp-B0h]
  __int64 v90; // [rsp+E0h] [rbp-A8h]
  int v91; // [rsp+E8h] [rbp-A0h]
  int v92; // [rsp+ECh] [rbp-9Ch]
  __int64 v93; // [rsp+F0h] [rbp-98h]
  int v94; // [rsp+F8h] [rbp-90h]
  int v95; // [rsp+FCh] [rbp-8Ch]
  unsigned __int64 v96; // [rsp+100h] [rbp-88h]
  __int64 v97; // [rsp+108h] [rbp-80h]
  __int64 v98; // [rsp+110h] [rbp-78h]
  int v99; // [rsp+118h] [rbp-70h]
  int v100; // [rsp+11Ch] [rbp-6Ch]
  int v101; // [rsp+120h] [rbp-68h]
  CLFS_CONTAINER_ID v102; // [rsp+124h] [rbp-64h]
  int v103; // [rsp+130h] [rbp-58h]
  int v104; // [rsp+134h] [rbp-54h]
  CLFS_LSN v105; // [rsp+138h] [rbp-50h]
  union _CLS_LSN v106; // [rsp+140h] [rbp-48h] BYREF
  signed int v111; // [rsp+1C8h] [rbp+40h]

  v14 = a4;
  v15 = *((_QWORD *)this + 89);
  v82 = CLFS_LSN_INVALID;
  *(CLFS_LSN *)v76 = CLFS_LSN_INVALID;
  v86 = 0;
  v87 = 0;
  v77 = 0;
  v79 = 0;
  v16 = *(_DWORD *)(v15 + 144);
  if ( v16 - 1 > 0xFFF || (v16 & 0x1FF) != 0 || 0x1000 % v16 )
    return 3221225624LL;
  v111 = -1073741275;
  v78 = 0;
  LODWORD(v17) = 0;
  *a13 = CLFS_LSN_INVALID;
  *a14 = 0;
  if ( a11 )
    v78 = (*(__int64 (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)a11 + 16LL))(a11);
  v18 = ClfsLsnBlockOffset(v14);
  v19 = ClfsLsnContainer(v14);
  if ( v19 == -1 || (v18 & 0x1FF) != 0 )
  {
    v21 = CLFS_LSN_INVALID;
    v20 = CLFS_LSN_INVALID;
  }
  else
  {
    v85.ullOffset = __PAIR64__(v19, v18);
    v20.ullOffset = v18 | ((unsigned __int64)v19 << 32);
    v21 = CLFS_LSN_INVALID;
  }
  v106 = v20;
  while ( 1 )
  {
    if ( (unsigned int)v17 >= 0x3F8 || (v22 = *((_BYTE *)a7 + 2 * (unsigned int)v17 + 1)) == 0 )
    {
      v25 = 0;
      goto LABEL_44;
    }
    if ( v22 == -1 && *((_BYTE *)a7 + 2 * (unsigned int)v17) == 0xFF )
      break;
    LODWORD(v17) = v17 + 1;
  }
  v25 = -1073741275;
LABEL_44:
  if ( v25 < 0 )
  {
    v68 = v25;
  }
  else
  {
    v40 = a3;
    if ( (unsigned int)v17 >= 0x3F8 )
    {
LABEL_132:
      v25 = -1073741275;
    }
    else
    {
      for ( i = *((_BYTE *)a7 + 2 * (unsigned int)v17); ; i = *((_BYTE *)a7 + 2 * v17) )
      {
        if ( i == a3 )
        {
          v25 = 0;
          goto LABEL_49;
        }
        if ( (unsigned int)v17 >= 0x3F8 )
          break;
        v17 = (unsigned int)(v17 + 1);
        if ( (unsigned int)v17 >= 0x3F8 )
          goto LABEL_132;
        while ( (unsigned int)v17 < 0x3F8 )
        {
          v66 = (char *)a7 + 2 * v17;
          v67 = v66[1];
          if ( !v67 )
            break;
          if ( v67 == -1 && *v66 == -1 )
            goto LABEL_132;
          v17 = (unsigned int)(v17 + 1);
        }
      }
      v25 = -1073741275;
    }
LABEL_49:
    if ( v25 >= 0 )
    {
      v41 = a6;
      v35 = *(_QWORD *)a6;
      *(_QWORD *)v76 = *(_QWORD *)a6;
      v86 = *(_OWORD *)a9;
      v87 = *((_QWORD *)a9 + 2);
      while ( 1 )
      {
        if ( (unsigned int)v17 >= 0x3F8 )
          goto LABEL_154;
        if ( *a14 >= a10 )
          goto LABEL_154;
        v88 = v35;
        if ( v41 == (const struct _CLFS_OWNER_REFERRAL *)-8LL || v35 >= *((_QWORD *)v41 + 1) )
          goto LABEL_154;
        for ( j = *((_BYTE *)a7 + 2 * (unsigned int)v17); ; j = *((_BYTE *)a7 + 2 * v17) )
        {
          if ( j == v40 )
          {
            v25 = 0;
            goto LABEL_58;
          }
          if ( (unsigned int)v17 >= 0x3F8 )
            break;
          v17 = (unsigned int)(v17 + 1);
          if ( (unsigned int)v17 >= 0x3F8 )
            break;
          while ( (unsigned int)v17 < 0x3F8 )
          {
            v64 = (char *)a7 + 2 * v17;
            v65 = v64[1];
            if ( !v65 )
              break;
            if ( v65 == -1 && *v64 == -1 )
              goto LABEL_118;
            v17 = (unsigned int)(v17 + 1);
          }
        }
LABEL_118:
        v25 = -1073741275;
LABEL_58:
        if ( v25 < 0 )
        {
LABEL_154:
          v68 = v111;
          goto LABEL_155;
        }
        if ( v20.ullOffset == v35 )
          goto LABEL_65;
        if ( v14 && v14->ullOffset < __PAIR64__(HIDWORD(v88), v35) )
        {
          if ( v20.ullOffset != v35 && a13 && v21.ullOffset == a13->ullOffset )
          {
            v68 = -1073741275;
            goto LABEL_155;
          }
LABEL_65:
          v97 = 0;
          v98 = 0;
          if ( a5 && v21.ullOffset == a5->ullOffset )
          {
            v81 = v21;
            v50 = v21;
          }
          else if ( CClfsLogFcbPhysical::ValidateContainerSize(this) )
          {
            v44 = -1;
            if ( a5 )
              v44 = a5->offset.idxRecord & 0xFFFFFE00;
            cidContainer = -1;
            if ( a5 )
              cidContainer = a5->offset.cidContainer;
            v46 = *((_QWORD *)this + 87);
            v48 = (unsigned int)((_DWORD)v17 << 9) + v46 * cidContainer + v44;
            v47 = v48 % v46;
            v49 = v48 / v46;
            if ( (v48 / v46) >> 32 )
            {
              v21 = CLFS_LSN_INVALID;
              v81 = CLFS_LSN_INVALID;
              v50 = CLFS_LSN_INVALID;
            }
            else if ( HIDWORD(v47) )
            {
              v21 = CLFS_LSN_INVALID;
              v81 = CLFS_LSN_INVALID;
              v50 = CLFS_LSN_INVALID;
            }
            else
            {
              if ( (_DWORD)v49 == -1 || (v47 & 0x1FF) != 0 )
              {
                v21 = CLFS_LSN_INVALID;
                v50 = CLFS_LSN_INVALID;
              }
              else
              {
                v100 = v49;
                v99 = v47;
                v50.ullOffset = (unsigned int)v47 | ((unsigned __int64)(unsigned int)v49 << 32);
                v21 = CLFS_LSN_INVALID;
              }
              v81 = v50;
            }
          }
          else
          {
            v21 = CLFS_LSN_INVALID;
            v81 = CLFS_LSN_INVALID;
            v50 = CLFS_LSN_INVALID;
          }
          v82 = v50;
          v51 = -1;
          if ( v14 )
            v51 = v14->offset.idxRecord & 0x1FF;
          if ( v50.offset.cidContainer != -1 && (v51 & 0xFFFFFE00) == 0 )
          {
            v102 = v50.offset.cidContainer;
            v52 = v50.offset.idxRecord & 0xFFFFFE00 | v51;
            v101 = v52;
            v21.ullOffset = v52 | (HIDWORD(v50.ullOffset) << 32);
          }
          v82 = v21;
          v111 = CClfsLogFcbPhysical::CacheBlock(this, a2, &v82, &v77);
          if ( v111 < 0 )
            goto LABEL_153;
          v53 = *(_DWORD *)(*((_QWORD *)this + 89) + 144LL);
          if ( v53 )
            v54 = -v53 & (v53 + (v77 << 9) - 1);
          else
            v54 = 0;
          v77 = v54 >> 9;
          v55 = *a14;
          if ( v54 >> 9 > a10 - *a14 )
            v77 = a10 - *a14;
          LODWORD(v87) = *((_DWORD *)a9 + 4) + (v55 << 9);
          v75 = &v86;
          v56 = (*(__int64 (__fastcall **)(CClfsLogFcbPhysical *, struct _FILE_OBJECT *, union _CLS_LSN *, __int64))(*(_QWORD *)this + 128LL))(
                  this,
                  a2,
                  &v82,
                  1);
          v111 = v56;
          if ( v56 < 0 )
          {
LABEL_153:
            v21 = CLFS_LSN_INVALID;
            goto LABEL_154;
          }
          v57 = v79 >> 9;
          if ( v56 == 259 )
            v25 = 259;
          *a14 += v57;
          v58 = (*(__int64 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 312LL))(this);
          v35 = *(_QWORD *)v76;
          if ( !v58 || (ullOffset = CLFS_LSN_INVALID.ullOffset, CLFS_LSN_INVALID.ullOffset == *(_QWORD *)v76) )
          {
            v105 = CLFS_LSN_INVALID;
            ullOffset = CLFS_LSN_INVALID.ullOffset;
          }
          else
          {
            v84 = v76[0] & 0xFFFFFE00;
            v60 = *((_QWORD *)this + 87);
            v61 = ((((__int64)((v76[0] & 0xFFFFFE00) + v76[1] * v60) >> 63) & 0x7FFFF)
                 + (v76[0] & 0xFFFFFE00)
                 + v76[1] * v60)
                & 0xFFFFFFFFFFF80000uLL;
            v62 = (v61 + 520192) / v60;
            if ( (_DWORD)v62 != -1 )
            {
              v63 = (v61 + 520192) % v60;
              if ( (v63 & 0x1FF) == 0 )
              {
                v104 = (v61 + 520192) / v60;
                v103 = (v61 + 520192) % v60;
                ullOffset = (unsigned int)v63 | ((unsigned __int64)(unsigned int)v62 << 32);
              }
            }
            v105.ullOffset = ullOffset;
          }
          if ( ullOffset == *(_QWORD *)v76 )
          {
            v35 = *(_QWORD *)CClfsLogFcbPhysical::AddLsnOffset(this, &v85, (unsigned int)v76).ullOffset;
            *(_QWORD *)v76 = v35;
          }
          a13->ullOffset = v35;
          LODWORD(v17) = v57 + v17;
          v14 = a4;
LABEL_100:
          v21 = CLFS_LSN_INVALID;
          goto LABEL_42;
        }
        v17 = (unsigned int)(v17 + 1);
        if ( (unsigned int)v17 >= 0x3F8 )
        {
          v25 = -1073741275;
        }
        else
        {
          while ( 1 )
          {
            v23 = (char *)a7 + 2 * v17;
            v24 = v23[1];
            if ( !v24 )
            {
LABEL_18:
              v25 = 0;
              goto LABEL_19;
            }
            if ( v24 == -1 && *v23 == -1 )
              break;
            v17 = (unsigned int)(v17 + 1);
            if ( (unsigned int)v17 >= 0x3F8 )
              goto LABEL_18;
          }
          v25 = -1073741275;
        }
LABEL_19:
        if ( v25 < 0 )
          goto LABEL_154;
        v89 = 0;
        v90 = 0;
        if ( a5 && v21.ullOffset == a5->ullOffset )
        {
          v80 = v21.ullOffset;
          v32 = v21.ullOffset;
          v33 = v21.ullOffset;
        }
        else
        {
          v26 = *((_QWORD *)this + 87);
          if ( !v26 || (v26 & 0xFFF) != 0 || v26 > 0x100000000LL )
          {
            v69 = 2 * (((unsigned __int64)*((unsigned __int16 *)this + 160) >> 1) + 1);
            if ( !is_mul_ok(((unsigned __int64)*((unsigned __int16 *)this + 160) >> 1) + 1, 2u) )
              v69 = -1;
            PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, v69, 0x73666C43u);
            v71 = PoolWithTag;
            if ( PoolWithTag )
            {
              memset(PoolWithTag, 0, *((unsigned __int16 *)this + 160) + 2LL);
              memmove(v71, *((const void **)this + 41), *((unsigned __int16 *)this + 160));
              if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
              {
                WPP_SF_sdiSi(
                  *((_QWORD *)WPP_GLOBAL_Control + 3),
                  (_DWORD)this,
                  v72,
                  v73,
                  (_DWORD)v75,
                  (char)this,
                  (__int64)v71,
                  *((_QWORD *)this + 87));
              }
              ExFreePoolWithTag(v71, 0);
            }
            else if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
                   && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
            {
              WPP_SF_sdii(*((_QWORD *)WPP_GLOBAL_Control + 3));
            }
            v32 = CLFS_LSN_INVALID.ullOffset;
            v33 = CLFS_LSN_INVALID.ullOffset;
          }
          else
          {
            v27 = -1;
            if ( a5 )
              v27 = a5->offset.idxRecord & 0xFFFFFE00;
            v28 = 0xFFFFFFFFLL;
            if ( a5 )
              v28 = a5->offset.cidContainer;
            v30 = (unsigned int)((_DWORD)v17 << 9) + v26 * v28 + v27;
            v29 = v30 % v26;
            v31 = v30 / v26;
            if ( (v30 / v26) >> 32 )
            {
              v80 = v21.ullOffset;
              v32 = v21.ullOffset;
              v33 = v21.ullOffset;
              goto LABEL_36;
            }
            if ( HIDWORD(v29) )
            {
              v80 = v21.ullOffset;
              v32 = v21.ullOffset;
              v33 = v21.ullOffset;
              goto LABEL_36;
            }
            if ( (_DWORD)v31 == -1 || (v29 & 0x1FF) != 0 )
            {
              v32 = v21.ullOffset;
            }
            else
            {
              v92 = v31;
              v91 = v29;
              v32 = (unsigned int)v29 | ((unsigned __int64)(unsigned int)v31 << 32);
            }
            v33 = v21.ullOffset;
          }
          v80 = v32;
        }
LABEL_36:
        *(_QWORD *)v76 = v32;
        v83 = 0;
        v93 = 0;
        v34 = (*(__int64 (__fastcall **)(CClfsLogFcbPhysical *))(*(_QWORD *)this + 312LL))(this);
        v21 = CLFS_LSN_INVALID;
        v35 = *(_QWORD *)v76;
        if ( v34 && CLFS_LSN_INVALID.ullOffset != *(_QWORD *)v76 )
        {
          LODWORD(v83) = v76[0] & 0xFFFFFE00;
          v36 = *((_QWORD *)this + 87);
          v37 = ((((__int64)((v76[0] & 0xFFFFFE00) + v36 * v76[1]) >> 63) & 0x7FFFF)
               + (v76[0] & 0xFFFFFE00)
               + v36 * v76[1])
              & 0xFFFFFFFFFFF80000uLL;
          v38 = (v37 + 520192) / v36;
          if ( (_DWORD)v38 == -1 || (v39 = (v37 + 520192) % v36, (v39 & 0x1FF) != 0) )
          {
            v33 = CLFS_LSN_INVALID.ullOffset;
          }
          else
          {
            v95 = (v37 + 520192) / v36;
            v94 = (v37 + 520192) % v36;
            v33 = (unsigned int)v39 | ((unsigned __int64)(unsigned int)v38 << 32);
          }
        }
        v96 = v33;
        if ( v33 == *(_QWORD *)v76 )
        {
          v35 = *(_QWORD *)CClfsLogFcbPhysical::AddLsnOffset(this, &v106, (unsigned int)v76).ullOffset;
          *(_QWORD *)v76 = v35;
          goto LABEL_100;
        }
LABEL_42:
        v40 = a3;
        v41 = a6;
      }
    }
    v68 = v25;
  }
LABEL_155:
  if ( !a13 || v21.ullOffset != a13->ullOffset )
    v68 = v25;
  if ( a11 && v78 )
  {
    if ( v68 < 0 )
      (*(void (__fastcall **)(struct IClfsRequestAsync *, _QWORD, _QWORD))(*(_QWORD *)a11 + 88LL))(
        a11,
        (unsigned int)v68,
        0);
    if ( (*(unsigned int (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)a11 + 24LL))(a11) )
      return 259;
  }
  return (unsigned int)v68;
}

```

## disassembly

```asm
0x140065860  mov     r11, rsp
0x140065863  mov     [r11+20h], r9
0x140065867  mov     [r11+18h], r8b
0x14006586b  mov     [r11+10h], rdx
0x14006586f  mov     [r11+8], rcx
0x140065873  push    rbx
0x140065874  push    rsi
0x140065875  push    rdi
0x140065876  push    r12
0x140065878  push    r13
0x14006587a  push    r14
0x14006587c  push    r15
0x14006587e  sub     rsp, 150h
0x140065885  mov     r15, r9
0x140065888  mov     rax, [rcx+2C8h]
0x14006588f  mov     r10, qword ptr cs:CLFS_LSN_INVALID
0x140065896  mov     [r11-0F0h], r10
0x14006589d  mov     qword ptr [rsp+188h+var_118], r10
0x1400658a2  xorps   xmm0, xmm0
0x1400658a5  movdqu  [rsp+188h+var_D0], xmm0
0x1400658ae  xor     r8d, r8d
0x1400658b1  mov     [r11-0C0h], r8
0x1400658b8  mov     [rsp+188h+var_110], r8d
0x1400658bd  mov     [r11-108h], r8d
0x1400658c4  mov     ecx, [rax+90h]
0x1400658ca  lea     eax, [rcx-1]
0x1400658cd  cmp     eax, 0FFFh
0x1400658d2  ja      loc_1400664A0
0x1400658d8  test    ecx, 1FFh
0x1400658de  jnz     loc_1400664A0
0x1400658e4  xor     edx, edx
0x1400658e6  mov     eax, 1000h
0x1400658eb  div     ecx
0x1400658ed  test    edx, edx
0x1400658ef  jnz     loc_1400664A0
0x1400658f5  mov     r13, [rsp+188h+arg_20]
0x1400658fd  mov     ebx, 0C0000225h
0x140065902  mov     [r11+40h], ebx
0x140065906  mov     [rsp+188h+var_128], ebx
0x14006590a  mov     [rsp+188h+var_120], r8d
0x14006590f  mov     [rsp+188h+var_10C], r8d
0x140065914  mov     esi, r8d
0x140065917  mov     rax, [rsp+188h+arg_60]
0x14006591f  mov     [rax], r10
0x140065922  mov     rcx, [rsp+188h+arg_68]
0x14006592a  mov     [rcx], r8d
0x14006592d  mov     rcx, [rsp+188h+arg_50]
0x140065935  test    rcx, rcx
0x140065938  jz      short loc_14006594A
0x14006593a  mov     rax, [rcx]
0x14006593d  mov     rax, [rax+10h]
0x140065941  call    _guard_dispatch_icall
0x140065946  mov     [rsp+188h+var_10C], eax
0x14006594a  mov     rcx, r15; plsn
0x14006594d  call    ClfsLsnBlockOffset
0x140065952  mov     ebx, eax
0x140065954  mov     rcx, r15; plsn
0x140065957  call    ClfsLsnContainer
0x14006595c  cmp     eax, 0FFFFFFFFh
0x14006595f  jz      loc_140066231
0x140065965  test    ebx, 1FFh
0x14006596b  jnz     loc_140066231
0x140065971  mov     dword ptr [rsp+188h+var_D8+4], eax
0x140065978  mov     dword ptr [rsp+188h+var_D8], ebx
0x14006597f  mov     edi, eax
0x140065981  shl     rdi, 20h
0x140065985  or      rdi, rbx
0x140065988  mov     r8, qword ptr cs:CLFS_LSN_INVALID
0x14006598f  mov     qword ptr [rsp+188h+var_48], rdi
0x140065997  mov     r12, [rsp+188h+arg_30]
0x14006599f  nop
0x1400659a0  mov     ecx, esi
0x1400659a2  cmp     esi, 3F8h
0x1400659a8  jnb     loc_140065BF7
0x1400659ae  movzx   eax, byte ptr [r12+rcx*2+1]
0x1400659b4  test    al, al
0x1400659b6  jz      loc_140065BF7
0x1400659bc  cmp     al, 0FFh
0x1400659be  jz      loc_140066240
0x1400659c4  inc     esi
0x1400659c6  mov     [rsp+188h+var_124], esi
0x1400659ca  jmp     short loc_1400659A0
0x1400659cc  inc     esi
0x1400659ce  mov     [rsp+188h+var_124], esi
0x1400659d2  cmp     esi, 3F8h
0x1400659d8  jnb     loc_140066102
0x1400659de  lea     rcx, [r12+rsi*2]
0x1400659e2  movzx   eax, byte ptr [rcx+1]
0x1400659e6  test    al, al
0x1400659e8  jz      short loc_140065A00
0x1400659ea  cmp     al, 0FFh
0x1400659ec  jz      loc_140066149
0x1400659f2  inc     esi
0x1400659f4  mov     [rsp+188h+var_124], esi
0x1400659f8  cmp     esi, 3F8h
0x1400659fe  jb      short loc_1400659DE
0x140065a00  mov     r14d, r11d
0x140065a03  mov     [rsp+188h+var_120], r14d
0x140065a08  test    r14d, r14d
0x140065a0b  js      loc_140066425
0x140065a11  mov     eax, esi
0x140065a13  shl     eax, 9
0x140065a16  mov     [rsp+188h+var_B0], 0
0x140065a22  mov     [rsp+188h+var_A8], 0
0x140065a2e  test    r13, r13
0x140065a31  jz      short loc_140065A3D
0x140065a33  cmp     r8, [r13+0]
0x140065a37  jz      loc_1400660EF
0x140065a3d  mov     rcx, [rsp+188h+arg_0]
0x140065a45  mov     r9, [rcx+2B8h]
0x140065a4c  test    r9, r9
0x140065a4f  jz      loc_14006627C
0x140065a55  test    r9, 0FFFh
0x140065a5c  jnz     loc_14006627C
0x140065a62  cmp     r9, rbx
0x140065a65  ja      loc_14006627C
0x140065a6b  mov     edx, 0FFFFFFFFh
0x140065a70  test    r13, r13
0x140065a73  jz      short loc_140065A7F
0x140065a75  mov     edx, [r13+0]
0x140065a79  and     edx, 0FFFFFE00h
0x140065a7f  mov     ecx, 0FFFFFFFFh
0x140065a84  test    r13, r13
0x140065a87  jz      short loc_140065A8D
0x140065a89  mov     ecx, [r13+4]
0x140065a8d  imul    rcx, r9
0x140065a91  add     rcx, rax
0x140065a94  mov     eax, edx
0x140065a96  add     rax, rcx
0x140065a99  xor     edx, edx
0x140065a9b  div     r9
0x140065a9e  mov     rcx, rax
0x140065aa1  shr     rax, 20h
0x140065aa5  test    eax, eax
0x140065aa7  jnz     loc_1400661EC
0x140065aad  mov     rax, rdx
0x140065ab0  shr     rax, 20h
0x140065ab4  test    eax, eax
0x140065ab6  jnz     loc_140066136
0x140065abc  cmp     ecx, 0FFFFFFFFh
0x140065abf  jz      loc_140066165
0x140065ac5  test    edx, 1FFh
0x140065acb  jnz     loc_140066165
0x140065ad1  mov     [rsp+188h+var_9C], ecx
0x140065ad8  mov     [rsp+188h+var_A0], edx
0x140065adf  mov     ecx, ecx
0x140065ae1  shl     rcx, 20h
0x140065ae5  mov     eax, edx
0x140065ae7  or      rcx, rax
0x140065aea  mov     rbx, r8
0x140065aed  mov     [rsp+188h+var_100], rcx
0x140065af5  mov     qword ptr [rsp+188h+var_118], rcx
0x140065afa  mov     [rsp+188h+var_E8], 0
0x140065b06  mov     [rsp+188h+var_98], 0
0x140065b12  mov     rcx, [rsp+188h+arg_0]
0x140065b1a  mov     rax, [rcx]
0x140065b1d  mov     rax, [rax+138h]
0x140065b24  call    _guard_dispatch_icall
0x140065b29  mov     r8, qword ptr cs:CLFS_LSN_INVALID
0x140065b30  mov     rcx, qword ptr [rsp+188h+var_118]
0x140065b35  test    al, al
0x140065b37  jz      loc_140065BD0
0x140065b3d  cmp     r8, rcx
0x140065b40  jz      loc_140065BD0
0x140065b46  mov     r9d, ecx
0x140065b49  and     r9d, 0FFFFFE00h
0x140065b50  mov     dword ptr [rsp+188h+var_E8], r9d
0x140065b58  mov     r10, [rsp+188h+arg_0]
0x140065b60  mov     r10, [r10+2B8h]
0x140065b67  mov     eax, [rsp+188h+var_118+4]
0x140065b6b  imul    rax, r10
0x140065b6f  add     rax, r9
0x140065b72  cqo
0x140065b74  and     edx, 7FFFFh
0x140065b7a  lea     r11, [rdx+rax]
0x140065b7e  and     r11, 0FFFFFFFFFFF80000h
0x140065b85  xor     edx, edx
0x140065b87  lea     rax, [r11+7F000h]
0x140065b8e  div     r10
0x140065b91  mov     r9, rax
0x140065b94  cmp     eax, 0FFFFFFFFh
0x140065b97  jz      loc_14006615D
0x140065b9d  xor     edx, edx
0x140065b9f  lea     rax, [r11+7F000h]
0x140065ba6  div     r10
0x140065ba9  test    edx, 1FFh
0x140065baf  jnz     loc_14006615D
0x140065bb5  mov     eax, edx
0x140065bb7  mov     [rsp+188h+var_8C], r9d
0x140065bbf  mov     [rsp+188h+var_90], edx
0x140065bc6  mov     ebx, r9d
0x140065bc9  shl     rbx, 20h
0x140065bcd  or      rbx, rax
0x140065bd0  mov     [rsp+188h+var_88], rbx
0x140065bd8  cmp     rbx, rcx
0x140065bdb  jz      loc_1400663A2
0x140065be1  movzx   r10d, [rsp+188h+arg_10]
0x140065bea  mov     r9, [rsp+188h+arg_28]
0x140065bf2  xor     r11d, r11d
0x140065bf5  jmp     short loc_140065C70
0x140065bf7  xor     r11d, r11d
0x140065bfa  mov     r14d, r11d
0x140065bfd  mov     [rsp+188h+var_120], r14d
0x140065c02  test    r14d, r14d
0x140065c05  js      loc_140066259
0x140065c0b  movzx   r10d, [rsp+188h+arg_10]
0x140065c14  cmp     esi, 3F8h
0x140065c1a  jnb     loc_140066226
0x140065c20  movzx   eax, byte ptr [r12+rcx*2]
0x140065c25  cmp     al, r10b
0x140065c28  jnz     loc_1400661A8
0x140065c2e  mov     r14d, r11d
0x140065c31  mov     [rsp+188h+var_120], r14d
0x140065c36  test    r14d, r14d
0x140065c39  js      loc_140066270
0x140065c3f  mov     r9, [rsp+188h+arg_28]
0x140065c47  mov     rcx, [r9]
0x140065c4a  mov     qword ptr [rsp+188h+var_118], rcx
0x140065c4f  mov     rax, [rsp+188h+arg_40]
0x140065c57  movups  xmm0, xmmword ptr [rax]
0x140065c5a  movups  [rsp+188h+var_D0], xmm0
0x140065c62  movsd   xmm1, qword ptr [rax+10h]
0x140065c67  movsd   [rsp+188h+var_C0], xmm1
0x140065c70  mov     rbx, 100000000h
0x140065c7a  cmp     esi, 3F8h
0x140065c80  jnb     loc_140066425
0x140065c86  mov     rax, [rsp+188h+arg_68]
0x140065c8e  mov     edx, [rsp+188h+arg_48]
0x140065c95  cmp     [rax], edx
0x140065c97  jnb     loc_140066425
0x140065c9d  mov     [rsp+188h+var_B8], rcx
0x140065ca5  lea     rdx, [r9+8]
0x140065ca9  test    rdx, rdx
0x140065cac  jz      loc_140066425
0x140065cb2  mov     rax, rcx
0x140065cb5  shr     rax, 20h
0x140065cb9  cmp     eax, [rdx+4]
0x140065cbc  ja      loc_140066425
0x140065cc2  jnz     short loc_140065CCC
0x140065cc4  cmp     ecx, [rdx]
0x140065cc6  jnb     loc_140066425
0x140065ccc  mov     eax, esi
0x140065cce  movzx   edx, byte ptr [r12+rax*2]
0x140065cd3  cmp     dl, r10b
0x140065cd6  jnz     loc_14006609F
0x140065cdc  mov     r14d, r11d
0x140065cdf  mov     [rsp+188h+var_120], r14d
0x140065ce4  test    r14d, r14d
0x140065ce7  js      loc_140066425
0x140065ced  cmp     rdi, rcx
0x140065cf0  jz      short loc_140065D32
0x140065cf2  test    r15, r15
0x140065cf5  jz      loc_1400659CC
0x140065cfb  mov     eax, dword ptr [rsp+188h+var_B8+4]
0x140065d02  cmp     [r15+4], eax
0x140065d06  ja      loc_1400659CC
0x140065d0c  jnz     short loc_140065D17
0x140065d0e  cmp     [r15], ecx
0x140065d11  jnb     loc_1400659CC
0x140065d17  cmp     rdi, rcx
0x140065d1a  jz      short loc_140065D32
0x140065d1c  mov     rax, [rsp+188h+arg_60]
0x140065d24  test    rax, rax
0x140065d27  jz      short loc_140065D32
0x140065d29  cmp     r8, [rax]
0x140065d2c  jz      loc_1400663CF
0x140065d32  mov     ebx, esi
0x140065d34  shl     ebx, 9
0x140065d37  mov     [rsp+188h+var_80], 0
0x140065d43  mov     [rsp+188h+var_78], 0
0x140065d4f  test    r13, r13
0x140065d52  jz      short loc_140065D5E
0x140065d54  cmp     r8, [r13+0]
0x140065d58  jz      loc_14006611D
0x140065d5e  mov     rcx, [rsp+188h+arg_0]; this
0x140065d66  call    ?ValidateContainerSize@CClfsLogFcbPhysical@@AEAAEXZ; CClfsLogFcbPhysical::ValidateContainerSize(void)
0x140065d6b  test    al, al
0x140065d6d  jz      loc_1400663DA
0x140065d73  mov     edx, 0FFFFFFFFh
0x140065d78  test    r13, r13
0x140065d7b  jz      short loc_140065D87
0x140065d7d  mov     edx, [r13+0]
0x140065d81  and     edx, 0FFFFFE00h
0x140065d87  mov     eax, 0FFFFFFFFh
0x140065d8c  test    r13, r13
0x140065d8f  jz      short loc_140065D95
0x140065d91  mov     eax, [r13+4]
0x140065d95  mov     r10, [rsp+188h+arg_0]
0x140065d9d  mov     r8, [r10+2B8h]
0x140065da4  mov     ecx, eax
0x140065da6  imul    rcx, r8
0x140065daa  mov     eax, ebx
0x140065dac  add     rcx, rax
0x140065daf  mov     eax, edx
0x140065db1  add     rax, rcx
0x140065db4  xor     edx, edx
0x140065db6  div     r8
0x140065db9  mov     rcx, rax
0x140065dbc  shr     rax, 20h
0x140065dc0  test    eax, eax
  ... truncated ...
```
