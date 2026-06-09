# ATL::CDynamicAccessor::BindColumns(IUnknown *)

- ea: `0x180007dac`
- end: `0x180008b07`
- name: `?BindColumns@CDynamicAccessor@ATL@@QEAAJPEAUIUnknown@@@Z`
- size: `3419`
- prototype: `__int64 __fastcall(ATL::CDynamicAccessor *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009790`

## callees

- `0x180001170`
- `0x1800011c4`
- `0x18000278c`
- `0x180007d58`
- `0x180007dac`
- `0x180008ffc`
- `0x1800090c8`
- `0x18000ab2e`
- `0x18000c010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000803d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008417`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008423`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008663`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000866f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008920`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000892c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800089ee`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800089fa`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008ab6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008ac2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000803d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008417`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008423`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008663`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000866f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008920`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000892c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800089ee`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800089fa`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008ab6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008ac2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008407`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000864b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000890e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800089dc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008a9a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008407`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000864b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000890e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800089dc`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008a9a`

## pseudocode

```c
__int64 __fastcall ATL::CDynamicAccessor::BindColumns(ATL::CDynamicAccessor *this, struct IUnknown *a2)
{
  ATL::CDynamicAccessor *v3; // r14
  int v4; // ebx
  unsigned __int64 *v6; // rsi
  size_t v7; // rax
  _DWORD *v8; // rax
  void **v9; // r15
  size_t v10; // r13
  _DWORD *v11; // rsi
  unsigned __int64 v12; // rcx
  __int64 v13; // r9
  __int64 v14; // r11
  unsigned __int64 v15; // rdx
  __int64 v16; // rax
  __int16 v17; // dx
  unsigned __int64 v18; // r12
  __int64 v19; // r10
  unsigned __int64 v20; // r10
  __int64 v21; // r11
  char v22; // r8
  char v23; // dl
  __int64 v24; // r9
  __int16 v25; // cx
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // r12
  unsigned int Alignment; // eax
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // r10
  size_t v33; // rcx
  unsigned __int64 v34; // r8
  unsigned __int64 v35; // r8
  __int64 v36; // r10
  char v37; // dl
  char v38; // cl
  __int64 v39; // rax
  GUID v40; // xmm0
  char *v41; // rcx
  __int64 v42; // r8
  __int64 *v43; // rdx
  unsigned int v44; // esi
  unsigned int i; // r14d
  __int64 v46; // r12
  unsigned int v47; // eax
  __int64 v48; // r8
  __int64 v49; // r9
  unsigned __int64 v50; // r10
  size_t v51; // rcx
  unsigned __int64 v52; // rax
  unsigned __int64 v53; // r9
  unsigned __int64 v54; // r9
  __int64 v55; // r10
  char v56; // r8
  char v57; // dl
  __int64 v58; // rcx
  int v59; // eax
  __int64 v60; // r12
  __int16 v61; // cx
  char *v62; // rcx
  __int64 *v63; // rdx
  unsigned int v64; // esi
  unsigned int v65; // r14d
  _DWORD *v66; // rbx
  void *v67; // rbx
  unsigned int v68; // eax
  unsigned __int64 v69; // r8
  __int64 v70; // r9
  size_t v71; // rcx
  unsigned __int64 v72; // rax
  unsigned __int64 v73; // r9
  unsigned __int64 v74; // r9
  __int64 v75; // r10
  char v76; // r8
  char v77; // dl
  __int64 v78; // rcx
  __int16 v79; // r13
  _DWORD *v80; // rax
  unsigned int v81; // eax
  unsigned __int64 v82; // r8
  __int64 v83; // r10
  size_t v84; // rcx
  unsigned __int64 v85; // r9
  __int64 v86; // r10
  int v87; // eax
  _DWORD *v88; // r12
  unsigned __int64 *v89; // rax
  __int64 *v90; // r10
  int AccessorMemory; // eax
  unsigned int j; // esi
  void **p_lpVtbl; // rsi
  unsigned __int64 *v94; // rax
  unsigned int v95; // esi
  int v96; // esi
  unsigned __int64 v97; // r14
  unsigned int v98; // [rsp+20h] [rbp-108h]
  unsigned __int16 v99; // [rsp+40h] [rbp-E8h]
  unsigned int v100; // [rsp+40h] [rbp-E8h]
  char *v101; // [rsp+40h] [rbp-E8h]
  unsigned int v102; // [rsp+40h] [rbp-E8h]
  unsigned int v103; // [rsp+40h] [rbp-E8h]
  unsigned __int64 *v104; // [rsp+48h] [rbp-E0h]
  _QWORD *v105; // [rsp+50h] [rbp-D8h] BYREF
  __int64 *v106; // [rsp+58h] [rbp-D0h]
  __int64 v107; // [rsp+60h] [rbp-C8h]
  int v108; // [rsp+68h] [rbp-C0h]
  __int64 v109; // [rsp+70h] [rbp-B8h]
  char *v110; // [rsp+78h] [rbp-B0h]
  _DWORD *v111; // [rsp+80h] [rbp-A8h]
  _DWORD *v112; // [rsp+88h] [rbp-A0h]
  unsigned __int64 *v113; // [rsp+90h] [rbp-98h]
  _DWORD *v114; // [rsp+98h] [rbp-90h]
  int v115[2]; // [rsp+A0h] [rbp-88h] BYREF
  _DWORD *v116; // [rsp+A8h] [rbp-80h]
  size_t v117; // [rsp+B0h] [rbp-78h]
  _DWORD *v118; // [rsp+B8h] [rbp-70h]
  void **v119; // [rsp+C0h] [rbp-68h]
  unsigned int v120[2]; // [rsp+C8h] [rbp-60h] BYREF
  __int64 *v121; // [rsp+D0h] [rbp-58h]
  GUID v122; // [rsp+D8h] [rbp-50h]
  unsigned int v125; // [rsp+138h] [rbp+10h]
  struct IUnknown *v126; // [rsp+138h] [rbp+10h]
  struct IUnknown *v127; // [rsp+138h] [rbp+10h]
  _QWORD *v128; // [rsp+140h] [rbp+18h] BYREF
  __int64 *v129; // [rsp+148h] [rbp+20h]

  v3 = this;
  if ( !a2 )
    return 2147500037LL;
  v122 = GUID_0c733a30_2a1c_11ce_ade5_00aa0044773d;
  v105 = 0;
  v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD **))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_0c733a8c_2a1c_11ce_ade5_00aa0044773d,
         &v105);
  if ( v4 < 0 )
  {
    if ( v105 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v105 + 16LL))(v105, *v105);
    return (unsigned int)v4;
  }
  v106 = (__int64 *)((char *)v3 + 40);
  v129 = (__int64 *)((char *)v3 + 40);
  if ( *((_QWORD *)v3 + 5) )
  {
    *((_BYTE *)v3 + 56) = 1;
    v6 = (unsigned __int64 *)((char *)v3 + 24);
    v104 = (unsigned __int64 *)((char *)v3 + 24);
  }
  else
  {
    v128 = 0;
    v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD **))a2->lpVtbl->QueryInterface)(
           a2,
           &GUID_0c733a11_2a1c_11ce_ade5_00aa0044773d,
           &v128);
    if ( v4 < 0 )
    {
      if ( v128 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v128 + 16LL))(v128, *v128);
      if ( !v105 )
        return (unsigned int)v4;
      goto LABEL_11;
    }
    v6 = (unsigned __int64 *)((char *)v3 + 24);
    v104 = (unsigned __int64 *)((char *)v3 + 24);
    v4 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64, __int64))(*v128 + 24LL))(
           v128,
           (__int64)v3 + 24,
           (__int64)v3 + 40,
           (__int64)v3 + 48);
    if ( v4 < 0 )
    {
      if ( v128 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v128 + 16LL))(v128, *v128);
      if ( !v105 )
        return (unsigned int)v4;
LABEL_11:
      (*(void (__fastcall **)(_QWORD *))(*v105 + 16LL))(v105);
      return (unsigned int)v4;
    }
    *((_BYTE *)v3 + 56) = 0;
    if ( v128 )
      (*(void (__fastcall **)(_QWORD *))(*v128 + 16LL))(v128);
  }
  v113 = v6;
  v112 = 0;
  v7 = 88 * *v6;
  if ( !is_mul_ok(*v6, 0x58u) )
    v7 = -1;
  try
  {
    v8 = operator new[](v7);
    v88 = v8;
    v111 = v8;
    v112 = v8;
  }
  catch ( ... )
  {
    v3 = this;
    v88 = v112;
    v111 = v112;
    v6 = v113;
    v104 = v113;
    v106 = v129;
  }
  if ( !v88 )
  {
LABEL_130:
    if ( v105 )
      (*(void (__fastcall **)(_QWORD *))(*v105 + 16LL))(v105);
    return 2147942414LL;
  }
  try
  {
    v67 = v88;
    v116 = v88;
    v118 = v88;
    v9 = (void **)((char *)v3 + 32);
    *((_QWORD *)v3 + 4) = operator new[](*v6);
    v89 = v104;
    v90 = v106;
  }
  catch ( ... )
  {
    v3 = this;
    v9 = (void **)((char *)this + 32);
    v88 = v112;
    v111 = v112;
    v67 = v118;
    v116 = v118;
    v89 = v113;
    v104 = v113;
    v90 = v129;
    v106 = v129;
  }
  v119 = v9;
  if ( !*v9 )
  {
    operator delete[](v88);
    goto LABEL_130;
  }
  v121 = v90;
  LOBYTE(v128) = 0;
  v10 = 0;
  v117 = 0;
  v11 = v88;
  v114 = v88;
  v12 = 0;
  v108 = 13;
  while ( 1 )
  {
    LODWORD(v129) = v12;
    if ( v12 >= *v89 )
      break;
    *((_BYTE *)*v9 + v12) = 0;
    v13 = 80 * v12;
    v109 = 80 * v12;
    v107 = 80 * v12;
    v14 = *v90;
    v15 = *(_QWORD *)(80 * v12 + *v90 + 32);
    v16 = 80 * v12 + *v90;
    if ( v15 > *((_QWORD *)v3 + 8) )
    {
      v17 = *(_WORD *)(v16 + 40);
      if ( v17 != (_WORD)v108 )
      {
        if ( *((_DWORD *)v3 + 15) == 2 )
        {
          if ( v10 + 7 < v10 )
          {
            v18 = -1;
            v19 = 10;
            goto LABEL_33;
          }
          v18 = (v10 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
          v19 = v18 + 11;
          if ( v18 + 11 >= v18 + 8 )
LABEL_33:
            v20 = v19 & 0xFFFFFFFFFFFFFFFCuLL;
          else
            v20 = -1;
          *(_QWORD *)(v13 + v14 + 32) = 0;
          if ( !v11 )
            goto LABEL_145;
          v21 = 0;
          v22 = *(_BYTE *)(v13 + *v106 + 43);
          v23 = *(_BYTE *)(v13 + *v106 + 42);
          v24 = *(_QWORD *)(v13 + *v106 + 32);
          v25 = *(_WORD *)(*v106 + v109 + 40);
          v26 = *(_QWORD *)(*v106 + v109 + 16);
          *(_QWORD *)(v11 + 15) = 0;
          *((_QWORD *)v11 + 5) = 0;
          *(_QWORD *)v11 = v26;
          *((_WORD *)v11 + 42) = v25;
          *((_BYTE *)v11 + 86) = v23;
          *((_BYTE *)v11 + 87) = v22;
          v11[20] = 0;
          *((_QWORD *)v11 + 1) = 0;
          *((_QWORD *)v11 + 2) = 0;
          *((_QWORD *)v11 + 3) = 0;
          *((_QWORD *)v11 + 4) = 0;
          *((_QWORD *)v11 + 6) = 0;
          *((_QWORD *)v11 + 9) = v24;
          v11[14] = 0;
          if ( v18 )
          {
            v11[14] = 2;
            *((_QWORD *)v11 + 2) = v18;
            v27 = 6;
          }
          else
          {
            v27 = 4;
          }
LABEL_40:
          if ( v20 )
          {
LABEL_77:
            v11[14] = v27;
            *((_QWORD *)v11 + 3) = v20;
          }
          goto LABEL_78;
        }
        if ( *((_DWORD *)v3 + 15) == 1 )
        {
          *(_WORD *)(v16 + 40) = v17 | 0x4000;
          *(_QWORD *)(v13 + *v90 + 32) = 8;
          *((_BYTE *)*v9 + v12) = 1;
          v28 = *v90;
          v107 = *(_QWORD *)(v13 + *v90 + 32);
          v99 = *(_WORD *)(v13 + v28 + 40);
          Alignment = ATL::CDynamicAccessor::GetAlignment(v99);
          v33 = v10 + Alignment - 1;
          if ( v33 >= v10 )
            v21 = v33 & ~(Alignment - 1LL);
          else
            v21 = v30;
          v34 = v21 + v32 + 7;
          if ( v34 < v21 + v32 )
          {
            v35 = -1;
            v36 = 10;
            goto LABEL_48;
          }
          v35 = v34 & 0xFFFFFFFFFFFFFFF8uLL;
          v36 = v35 + 11;
          if ( v35 + 11 >= v35 + 8 )
LABEL_48:
            v20 = v36 & 0xFFFFFFFFFFFFFFFCuLL;
          else
            v20 = -1;
          if ( !v11 )
            goto LABEL_145;
          v37 = *(_BYTE *)(v31 + v28 + 43);
          v38 = *(_BYTE *)(v31 + v28 + 42);
          v39 = *(_QWORD *)(v31 + v28 + 16);
          *(_QWORD *)(v11 + 15) = 0;
          *((_QWORD *)v11 + 5) = 0;
          *(_QWORD *)v11 = v39;
          *((_WORD *)v11 + 42) = v99;
          *((_BYTE *)v11 + 86) = v38;
          *((_BYTE *)v11 + 87) = v37;
          v11[20] = 0;
          *((_QWORD *)v11 + 2) = 0;
          *((_QWORD *)v11 + 3) = 0;
          *((_QWORD *)v11 + 4) = 0;
          *((_QWORD *)v11 + 6) = 0;
          *((_QWORD *)v11 + 9) = v107;
          v11[14] = 1;
          *((_QWORD *)v11 + 1) = v21;
          if ( v35 )
          {
            v11[14] = 3;
            *((_QWORD *)v11 + 2) = v35;
            v27 = 7;
          }
          else
          {
            v27 = 5;
          }
          goto LABEL_40;
        }
        if ( !(_BYTE)v128 )
        {
          v120[0] = 137;
          v120[1] = 139;
          *(_QWORD *)v115 = 0;
          ATL::CDynamicAccessor::GetRowsetProperties((ATL::CDynamicAccessor *)v12, a2, v120, v115, v98);
          if ( v115[0] )
          {
            v40 = GUID_0c733a30_2a1c_11ce_ade5_00aa0044773d;
            goto LABEL_60;
          }
          if ( v115[1] )
          {
            v40 = GUID_0000000c_0000_0000_c000_000000000046;
LABEL_60:
            v122 = v40;
          }
          LOBYTE(v128) = 1;
        }
        v41 = (char *)operator new(0x14u);
        v110 = v41;
        v42 = v109;
        v43 = v106;
        if ( !v41 )
        {
          v44 = 0;
          for ( i = (unsigned int)v129; v44 < i; ++v44 )
            operator delete(*(void **)&v88[22 * v44 + 10]);
LABEL_129:
          operator delete[](*v9);
          *v9 = 0;
          operator delete[](v67);
          goto LABEL_130;
        }
        *(_DWORD *)v41 = 0;
        *(GUID *)(v41 + 4) = v122;
        *(_WORD *)(v42 + *v43 + 40) = 13;
        *(_QWORD *)(v42 + *v43 + 32) = 8;
        v46 = *v43;
        v107 = *(_QWORD *)(v42 + *v43 + 32);
        v100 = *(unsigned __int16 *)(v42 + v46 + 40);
        v47 = ATL::CDynamicAccessor::GetAlignment(v100);
        v51 = v10 + v47 - 1;
        if ( v51 >= v10 )
          v21 = v51 & ~(v47 - 1LL);
        else
          v21 = v50;
        v52 = v49 + v21;
        v53 = v49 + v21 + 7;
        if ( v53 < v52 )
        {
          v54 = v50;
          v55 = 10;
          goto LABEL_71;
        }
        v54 = v53 & 0xFFFFFFFFFFFFFFF8uLL;
        v55 = v54 + 11;
        if ( v54 + 11 >= v54 + 8 )
LABEL_71:
          v20 = v55 & 0xFFFFFFFFFFFFFFFCuLL;
        else
          v20 = -1;
        if ( !v11 )
          goto LABEL_145;
        v56 = *(_BYTE *)(v48 + v46 + 43);
        v57 = *(_BYTE *)(v46 + v109 + 42);
        v58 = *(_QWORD *)(v46 + v109 + 16);
        v11[15] = (v100 >> 14) & 1;
        *((_QWORD *)v11 + 5) = v110;
        v11[16] = 0;
        *(_QWORD *)v11 = v58;
        *((_WORD *)v11 + 42) = v100;
        *((_BYTE *)v11 + 86) = v57;
        *((_BYTE *)v11 + 87) = v56;
        v11[20] = 0;
        *((_QWORD *)v11 + 1) = v21;
        *((_QWORD *)v11 + 2) = 0;
        *((_QWORD *)v11 + 3) = 0;
        *((_QWORD *)v11 + 4) = 0;
        *((_QWORD *)v11 + 6) = 0;
        *((_QWORD *)v11 + 9) = v107;
        v11[14] = 1;
        v59 = 1;
        if ( v54 )
        {
          v59 = 3;
          v11[14] = 3;
          *((_QWORD *)v11 + 2) = v54;
        }
        if ( v20 )
        {
          v27 = v59 | 4;
          goto LABEL_77;
        }
LABEL_78:
        v60 = v109;
        goto LABEL_115;
      }
      v15 = *(_QWORD *)(v13 + v14 + 32);
    }
    v61 = *(_WORD *)(v16 + 40);
    if ( v61 != 13 )
    {
      if ( v61 == 129 )
        *(_QWORD *)(v13 + v14 + 32) = v15 + 1;
      if ( *(_WORD *)(v13 + *v90 + 40) == 130 )
        *(_QWORD *)(v13 + *v90 + 32) = 2LL * *(_QWORD *)(v13 + *v90 + 32) + 2;
      v107 = *v90;
      v110 = *(char **)(v13 + v107 + 32);
      v103 = *(unsigned __int16 *)(v13 + v107 + 40);
      v81 = ATL::CDynamicAccessor::GetAlignment(v103);
      v84 = v10 + v81 - 1;
      if ( v84 >= v10 )
        v21 = v84 & ~(v81 - 1LL);
      else
        v21 = v82;
      v85 = v21 + v83 + 7;
      if ( v85 < v21 + v83 )
      {
        v74 = v82;
        v86 = 10;
        goto LABEL_108;
      }
      v74 = v85 & 0xFFFFFFFFFFFFFFF8uLL;
      v86 = v74 + 11;
      if ( v74 + 11 >= v74 + 8 )
LABEL_108:
        v20 = v86 & 0xFFFFFFFFFFFFFFFCuLL;
      else
        v20 = v82;
      if ( !v11 )
LABEL_145:
        ATL::AtlThrowImpl(-2147467259);
      v60 = v109;
      v76 = *(_BYTE *)(v109 + v107 + 43);
      v77 = *(_BYTE *)(v109 + v107 + 42);
      v78 = *(_QWORD *)(v109 + v107 + 16);
      v79 = v103;
      v11[15] = (v103 >> 14) & 1;
      *((_QWORD *)v11 + 5) = 0;
      v80 = v110;
      goto LABEL_111;
    }
    try
    {
      v62 = (char *)operator new(0x14u);
      v110 = v62;
      v101 = v62;
      v60 = v109;
      v63 = v106;
    }
    catch ( ... )
    {
      v108 = 13;
      v3 = this;
      v10 = v117;
      v111 = v112;
      v67 = v118;
      v116 = v118;
      v11 = v114;
      v62 = v101;
      v110 = v101;
      v63 = v121;
      v106 = v121;
      v60 = v107;
      v104 = v113;
      v9 = v119;
    }
    if ( !v62 )
    {
      v64 = 0;
      v65 = (unsigned int)v129;
      if ( (_DWORD)v129 )
      {
        v66 = v111;
        do
          operator delete(*(void **)&v66[22 * v64++ + 10]);
        while ( v64 < v65 );
        v67 = v116;
      }
      goto LABEL_129;
    }
    *(_DWORD *)v62 = 0;
    *(GUID *)(v62 + 4) = GUID_00000000_0000_0000_c000_000000000046;
    *(_WORD *)(v60 + *v63 + 40) = 13;
    *(_QWORD *)(v60 + *v63 + 32) = 8;
    v107 = *v63;
    v114 = *(_DWORD **)(v60 + v107 + 32);
    v102 = *(unsigned __int16 *)(v60 + v107 + 40);
    v68 = ATL::CDynamicAccessor::GetAlignment(v102);
    v71 = v10 + v68 - 1;
    if ( v71 >= v10 )
      v21 = v71 & ~(v68 - 1LL);
    else
      v21 = v69;
    v72 = v21 + v70;
    v73 = v21 + v70 + 7;
    if ( v73 >= v72 )
    {
      v74 = v73 & 0xFFFFFFFFFFFFFFF8uLL;
      v75 = v74 + 11;
      if ( v74 + 11 < v74 + 8 )
      {
        v20 = v69;
        goto LABEL_95;
      }
    }
    else
    {
      v74 = v69;
      v75 = 10;
    }
    v20 = v75 & 0xFFFFFFFFFFFFFFFCuLL;
LABEL_95:
    if ( !v11 )
      goto LABEL_145;
    v76 = *(_BYTE *)(v60 + v107 + 43);
    v77 = *(_BYTE *)(v60 + v107 + 42);
    v78 = *(_QWORD *)(v60 + v107 + 16);
    v79 = v102;
    v11[15] = (v102 >> 14) & 1;
    *((_QWORD *)v11 + 5) = v110;
    v80 = v114;
LABEL_111:
    *((_QWORD *)v11 + 9) = v80;
    v87 = 1;
    v11[14] = 1;
    *((_QWORD *)v11 + 6) = 0;
    *((_QWORD *)v11 + 4) = 0;
    *((_QWORD *)v11 + 3) = 0;
    *((_QWORD *)v11 + 2) = 0;
    *((_QWORD *)v11 + 1) = v21;
    v11[20] = 0;
    *((_BYTE *)v11 + 87) = v76;
    *((_BYTE *)v11 + 86) = v77;
    *((_WORD *)v11 + 42) = v79;
    *(_QWORD *)v11 = v78;
    v11[16] = 0;
    if ( v74 )
    {
      v87 = 3;
      v11[14] = 3;
      *((_QWORD *)v11 + 2) = v74;
    }
    if ( v20 )
    {
      *((_QWORD *)v11 + 3) = v20;
      v11[14] = v87 | 4;
    }
LABEL_115:
    *(_QWORD *)(v60 + *v106 + 8) = v21;
    v12 = (unsigned int)((_DWORD)v129 + 1);
    v10 = v20 + 4;
    v117 = v20 + 4;
    v11 += 22;
    v114 = v11;
    v88 = v111;
    v89 = v104;
    v90 = v106;
  }
  if ( !*(_QWORD *)v3 )
  {
    AccessorMemory = ATL::CAccessorBase::AllocateAccessorMemory(v3);
    v125 = AccessorMemory;
    if ( AccessorMemory < 0 )
    {
      for ( j = 0; j < *v104; ++j )
        operator delete(*(void **)&v88[22 * j + 10]);
      operator delete[](*v9);
      *v9 = 0;
      operator delete[](v67);
      if ( v105 )
        (*(void (__fastcall **)(_QWORD *))(*v105 + 16LL))(v105);
      return v125;
    }
    *(_BYTE *)(*(_QWORD *)v3 + 8LL) = 1;
  }
  try
  {
    p_lpVtbl = (void **)((char *)v3 + 16);
    v126 = (struct IUnknown *)((char *)v3 + 16);
    *((_QWORD *)v3 + 2) = 0;
    *((_QWORD *)v3 + 2) = operator new[](v10);
    v94 = v104;
  }
  catch ( ... )
  {
    v3 = this;
    v10 = v117;
    v88 = v112;
    v67 = v118;
    v94 = v113;
    v104 = v113;
    v9 = v119;
    p_lpVtbl = (void **)&v126->lpVtbl;
  }
  if ( !*p_lpVtbl )
  {
    v95 = 0;
    if ( *v94 )
    {
      do
        operator delete(*(void **)&v88[22 * v95++ + 10]);
      while ( v95 < *v104 );
    }
    goto LABEL_129;
  }
  memset_0(*p_lpVtbl, 0, v10);
  if ( *(_QWORD *)v3 && v105 )
  {
    v127 = (struct IUnknown *)*v104;
    v96 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, unsigned __int64, _DWORD *, size_t, _QWORD, _QWORD))(*v105 + 32LL))(
            v105,
            v88[16] != 0 ? 4 : 2,
            *v104,
            v88,
            v10,
            *(_QWORD *)v3,
            0);
    v97 = 0;
    if ( v127 )
    {
      do
        operator delete(*(void **)&v88[22 * v97++ + 10]);
      while ( v97 < (unsigned __int64)v127 );
    }
  }
  else
  {
    v96 = -2147467259;
  }
  if ( v96 < 0 )
  {
    operator delete[](*v9);
    *v9 = 0;
  }
  operator delete[](v67);
  if ( v105 )
    (*(void (__fastcall **)(_QWORD *, _QWORD))(*v105 + 16LL))(v105, *v105);
  return (unsigned int)v96;
}

```

## disassembly

```asm
0x180007dac  mov     [rsp+arg_8], rdx
0x180007db1  mov     [rsp+arg_0], rcx
0x180007db6  push    rbx
0x180007db7  push    rsi
0x180007db8  push    rdi
0x180007db9  push    r12
0x180007dbb  push    r13
0x180007dbd  push    r14
0x180007dbf  push    r15
0x180007dc1  sub     rsp, 0F0h
0x180007dc8  mov     rsi, rdx
0x180007dcb  mov     r14, rcx
0x180007dce  xor     edi, edi
0x180007dd0  test    rdx, rdx
0x180007dd3  jz      loc_180008AE4
0x180007dd9  movups  xmm0, xmmword ptr cs:_GUID_0c733a30_2a1c_11ce_ade5_00aa0044773d.Data1
0x180007de0  movdqu  [rsp+128h+var_50], xmm0
0x180007de9  mov     [rsp+128h+var_D8], rdi
0x180007dee  mov     rax, [rdx]
0x180007df1  lea     r8, [rsp+128h+var_D8]
0x180007df6  lea     rdx, _GUID_0c733a8c_2a1c_11ce_ade5_00aa0044773d
0x180007dfd  mov     rcx, rsi
0x180007e00  mov     rax, [rax]
0x180007e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e08  mov     ebx, eax
0x180007e0a  test    eax, eax
0x180007e0c  jns     short loc_180007E2C
0x180007e0e  mov     rcx, [rsp+128h+var_D8]
0x180007e13  test    rcx, rcx
0x180007e16  jz      short loc_180007E25
0x180007e18  mov     rdx, [rcx]
0x180007e1b  mov     rax, [rdx+10h]
0x180007e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e24  nop
0x180007e25  mov     eax, ebx
0x180007e27  jmp     loc_180008AE9
0x180007e2c  lea     r15, [r14+28h]
0x180007e30  mov     [rsp+128h+var_D0], r15
0x180007e35  mov     [rsp+128h+arg_18], r15
0x180007e3d  cmp     [r15], rdi
0x180007e40  jnz     loc_180007F27
0x180007e46  mov     [rsp+128h+arg_10], rdi
0x180007e4e  mov     rax, [rsi]
0x180007e51  lea     r8, [rsp+128h+arg_10]
0x180007e59  lea     rdx, _GUID_0c733a11_2a1c_11ce_ade5_00aa0044773d
0x180007e60  mov     rcx, rsi
0x180007e63  mov     rax, [rax]
0x180007e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e6b  mov     ebx, eax
0x180007e6d  test    eax, eax
0x180007e6f  jns     short loc_180007EA4
0x180007e71  mov     rcx, [rsp+128h+arg_10]
0x180007e79  test    rcx, rcx
0x180007e7c  jz      short loc_180007E8B
0x180007e7e  mov     rdx, [rcx]
0x180007e81  mov     rax, [rdx+10h]
0x180007e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e8a  nop
0x180007e8b  mov     rcx, [rsp+128h+var_D8]
0x180007e90  test    rcx, rcx
0x180007e93  jz      short loc_180007EA2
0x180007e95  mov     rax, [rcx]
0x180007e98  mov     rax, [rax+10h]
0x180007e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ea1  nop
0x180007ea2  jmp     short loc_180007E25
0x180007ea4  mov     rcx, [rsp+128h+arg_10]
0x180007eac  lea     rsi, [r14+18h]
0x180007eb0  mov     [rsp+128h+var_E0], rsi
0x180007eb5  mov     rax, [rcx]
0x180007eb8  lea     r9, [r14+30h]
0x180007ebc  mov     r8, r15
0x180007ebf  mov     rdx, rsi
0x180007ec2  mov     rax, [rax+18h]
0x180007ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ecb  mov     ebx, eax
0x180007ecd  test    eax, eax
0x180007ecf  jns     short loc_180007F07
0x180007ed1  mov     rcx, [rsp+128h+arg_10]
0x180007ed9  test    rcx, rcx
0x180007edc  jz      short loc_180007EEB
0x180007ede  mov     rdx, [rcx]
0x180007ee1  mov     rax, [rdx+10h]
0x180007ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eea  nop
0x180007eeb  mov     rcx, [rsp+128h+var_D8]
0x180007ef0  test    rcx, rcx
0x180007ef3  jz      short loc_180007F02
0x180007ef5  mov     rax, [rcx]
0x180007ef8  mov     rax, [rax+10h]
0x180007efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f01  nop
0x180007f02  jmp     loc_180007E25
0x180007f07  mov     [r14+38h], dil
0x180007f0b  mov     rcx, [rsp+128h+arg_10]
0x180007f13  test    rcx, rcx
0x180007f16  jz      short loc_180007F25
0x180007f18  mov     rax, [rcx]
0x180007f1b  mov     rax, [rax+10h]
0x180007f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f24  nop
0x180007f25  jmp     short loc_180007F35
0x180007f27  mov     byte ptr [r14+38h], 1
0x180007f2c  lea     rsi, [r14+18h]
0x180007f30  mov     [rsp+128h+var_E0], rsi
0x180007f35  mov     [rsp+128h+var_98], rsi
0x180007f3d  mov     [rsp+128h+var_A0], rdi
0x180007f45  mov     eax, 58h ; 'X'
0x180007f4a  mul     qword ptr [rsi]
0x180007f4d  mov     r10, 0FFFFFFFFFFFFFFFFh
0x180007f54  cmovb   rax, r10
0x180007f58  mov     rcx, rax; unsigned __int64
0x180007f5b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007f60  mov     r12, rax
0x180007f63  mov     [rsp+128h+var_A8], rax
0x180007f6b  mov     [rsp+128h+var_A0], rax
0x180007f73  jmp     short loc_180007FA9
0x180007f75  xor     edi, edi
0x180007f77  mov     r14, [rsp+128h+arg_0]
0x180007f7f  mov     r12, [rsp+128h+var_A0]
0x180007f87  mov     [rsp+128h+var_A8], r12
0x180007f8f  mov     rsi, [rsp+128h+var_98]
0x180007f97  mov     [rsp+128h+var_E0], rsi
0x180007f9c  mov     rax, [rsp+128h+arg_18]
0x180007fa4  mov     [rsp+128h+var_D0], rax
0x180007fa9  test    r12, r12
0x180007fac  jnz     short loc_180007FB3
0x180007fae  jmp     loc_180008A01
0x180007fb3  mov     rbx, r12
0x180007fb6  mov     [rsp+128h+var_80], rbx
0x180007fbe  mov     [rsp+128h+var_70], rbx
0x180007fc6  mov     rcx, [rsi]; unsigned __int64
0x180007fc9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007fce  lea     r15, [r14+20h]
0x180007fd2  mov     [r15], rax
0x180007fd5  mov     rax, [rsp+128h+var_E0]
0x180007fda  mov     r10, [rsp+128h+var_D0]
0x180007fdf  jmp     short loc_180008029
0x180007fe1  mov     r14, [rsp+128h+arg_0]
0x180007fe9  lea     r15, [r14+20h]
0x180007fed  xor     edi, edi
0x180007fef  mov     r12, [rsp+128h+var_A0]
0x180007ff7  mov     [rsp+128h+var_A8], r12
0x180007fff  mov     rbx, [rsp+128h+var_70]
0x180008007  mov     [rsp+128h+var_80], rbx
0x18000800f  mov     rax, [rsp+128h+var_98]
0x180008017  mov     [rsp+128h+var_E0], rax
0x18000801c  mov     r10, [rsp+128h+arg_18]
0x180008024  mov     [rsp+128h+var_D0], r10
0x180008029  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000802d  mov     [rsp+128h+var_68], r15
0x180008035  cmp     [r15], rdi
0x180008038  jnz     short loc_180008049
0x18000803a  mov     rcx, r12
0x18000803d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008043  nop
0x180008044  jmp     loc_180008A01
0x180008049  mov     [rsp+128h+var_58], r10
0x180008051  mov     byte ptr [rsp+128h+arg_10], dil
0x180008059  mov     r13, rdi
0x18000805c  mov     [rsp+128h+var_78], rdi
0x180008064  mov     rsi, r12
0x180008067  mov     [rsp+128h+var_90], r12
0x18000806f  mov     ecx, edi; this
0x180008071  mov     [rsp+128h+var_C0], 0Dh
0x180008079  mov     dword ptr [rsp+128h+arg_18], ecx
0x180008080  cmp     rcx, [rax]
0x180008083  jnb     loc_1800088DF
0x180008089  mov     rax, [r15]
0x18000808c  mov     [rcx+rax], dil
0x180008090  lea     r9, [rcx+rcx*4]
0x180008094  shl     r9, 4
0x180008098  mov     [rsp+128h+var_B8], r9
0x18000809d  mov     [rsp+128h+var_C8], r9
0x1800080a2  mov     r11, [r10]
0x1800080a5  mov     rdx, [r9+r11+20h]
0x1800080aa  lea     rax, [r9+r11]
0x1800080ae  cmp     rdx, [r14+40h]
0x1800080b2  jbe     loc_18000856E
0x1800080b8  movzx   edx, word ptr [rax+28h]
0x1800080bc  cmp     dx, word ptr [rsp+128h+var_C0]
0x1800080c1  jz      loc_180008569
0x1800080c7  cmp     dword ptr [r14+3Ch], 2
0x1800080cc  jnz     loc_1800081A4
0x1800080d2  lea     r12, [r13+7]
0x1800080d6  cmp     r12, r13
0x1800080d9  jnb     loc_180008173
0x1800080df  mov     r12, r8
0x1800080e2  mov     r10d, 0Ah
0x1800080e8  and     r10, 0FFFFFFFFFFFFFFFCh
0x1800080ec  mov     [r9+r11+20h], rdi
0x1800080f1  test    rsi, rsi
0x1800080f4  jz      loc_180008AFC
0x1800080fa  mov     r11, rdi
0x1800080fd  mov     rax, [rsp+128h+var_D0]
0x180008102  mov     rax, [rax]
0x180008105  mov     r8b, [r9+rax+2Bh]
0x18000810a  mov     dl, [r9+rax+2Ah]
0x18000810f  mov     r9, [r9+rax+20h]
0x180008114  mov     r13, [rsp+128h+var_B8]
0x180008119  movzx   ecx, word ptr [rax+r13+28h]
0x18000811f  mov     rax, [rax+r13+10h]
0x180008124  mov     qword ptr [rsi+3Ch], 0
0x18000812c  mov     [rsi+28h], rdi
0x180008130  mov     [rsi], rax
0x180008133  mov     [rsi+54h], cx
0x180008137  mov     [rsi+56h], dl
0x18000813a  mov     [rsi+57h], r8b
0x18000813e  mov     [rsi+50h], edi
0x180008141  mov     [rsi+8], rdi
0x180008145  mov     [rsi+10h], rdi
0x180008149  mov     [rsi+18h], rdi
0x18000814d  mov     [rsi+20h], rdi
0x180008151  mov     [rsi+30h], rdi
0x180008155  mov     [rsi+48h], r9
0x180008159  mov     [rsi+38h], edi
0x18000815c  test    r12, r12
0x18000815f  jz      short loc_180008191
0x180008161  mov     dword ptr [rsi+38h], 2
0x180008168  mov     [rsi+10h], r12
0x18000816c  mov     eax, 6
0x180008171  jmp     short loc_180008196
0x180008173  and     r12, 0FFFFFFFFFFFFFFF8h
0x180008177  lea     rax, [r12+8]
0x18000817c  lea     r10, [rax+3]
0x180008180  cmp     r10, rax
0x180008183  jnb     loc_1800080E8
0x180008189  mov     r10, r8
0x18000818c  jmp     loc_1800080EC
0x180008191  mov     eax, 4
0x180008196  test    r10, r10
0x180008199  jz      loc_180008541
0x18000819f  jmp     loc_18000853A
0x1800081a4  cmp     dword ptr [r14+3Ch], 1
0x1800081a9  jnz     loc_1800082C1
0x1800081af  or      dx, 4000h
0x1800081b4  mov     [rax+28h], dx
0x1800081b8  mov     rax, [r10]
0x1800081bb  mov     qword ptr [r9+rax+20h], 8
0x1800081c4  mov     rax, [r15]
0x1800081c7  mov     byte ptr [rcx+rax], 1
0x1800081cb  mov     r12, [r10]
0x1800081ce  mov     r10, [r9+r12+20h]
0x1800081d3  mov     [rsp+128h+var_C8], r10
0x1800081d8  movzx   eax, word ptr [r9+r12+28h]
0x1800081de  mov     dword ptr [rsp+128h+var_E8], eax
0x1800081e2  movzx   ecx, ax; unsigned __int16
0x1800081e5  call    ?GetAlignment@CDynamicAccessor@ATL@@SA_KG@Z; ATL::CDynamicAccessor::GetAlignment(ushort)
0x1800081ea  lea     ecx, [rax-1]
0x1800081ed  add     rcx, r13
0x1800081f0  cmp     rcx, r13
0x1800081f3  jnb     short loc_1800081FA
0x1800081f5  mov     r11, r8
0x1800081f8  jmp     short loc_180008206
0x1800081fa  mov     r11d, eax
0x1800081fd  dec     r11
0x180008200  not     r11
0x180008203  and     r11, rcx
0x180008206  lea     rax, [r11+r10]
0x18000820a  lea     r8, [rax+7]
0x18000820e  cmp     r8, rax
0x180008211  jnb     loc_180008299
0x180008217  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000821b  lea     r10d, [r8+0Bh]
0x18000821f  and     r10, 0FFFFFFFFFFFFFFFCh
0x180008223  test    rsi, rsi
0x180008226  jz      loc_180008AFC
0x18000822c  mov     dl, [r9+r12+2Bh]
0x180008231  mov     cl, [r9+r12+2Ah]
0x180008236  mov     rax, [r9+r12+10h]
0x18000823b  mov     qword ptr [rsi+3Ch], 0
0x180008243  mov     [rsi+28h], rdi
0x180008247  mov     [rsi], rax
0x18000824a  mov     eax, dword ptr [rsp+128h+var_E8]
0x18000824e  mov     [rsi+54h], ax
0x180008252  mov     [rsi+56h], cl
0x180008255  mov     [rsi+57h], dl
0x180008258  mov     [rsi+50h], edi
0x18000825b  mov     [rsi+10h], rdi
0x18000825f  mov     [rsi+18h], rdi
0x180008263  mov     [rsi+20h], rdi
0x180008267  mov     [rsi+30h], rdi
0x18000826b  mov     rax, [rsp+128h+var_C8]
0x180008270  mov     [rsi+48h], rax
0x180008274  mov     dword ptr [rsi+38h], 1
0x18000827b  mov     [rsi+8], r11
0x18000827f  test    r8, r8
0x180008282  jz      short loc_1800082B7
0x180008284  mov     dword ptr [rsi+38h], 3
0x18000828b  mov     [rsi+10h], r8
0x18000828f  mov     eax, 7
0x180008294  jmp     loc_180008196
0x180008299  and     r8, 0FFFFFFFFFFFFFFF8h
0x18000829d  lea     rax, [r8+8]
0x1800082a1  lea     r10, [rax+3]
0x1800082a5  cmp     r10, rax
0x1800082a8  jnb     loc_18000821F
0x1800082ae  or      r10, 0FFFFFFFFFFFFFFFFh
0x1800082b2  jmp     loc_180008223
0x1800082b7  mov     eax, 5
  ... truncated ...
```
