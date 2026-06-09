# CRTFObject::InitReadStaticObject(_reobject &,void * &,int,int,int,CTxtRange *,IStream *)

- ea: `0x18015a000`
- end: `0x18015a66b`
- name: `?InitReadStaticObject@CRTFObject@@AEAAJAEAU_reobject@@AEAPEAXHHHPEAVCTxtRange@@PEAUIStream@@@Z`
- size: `1643`
- prototype: `__int64 __fastcall(CRTFObject *__hidden this, struct _reobject *, void **, int, int, int, struct CTxtRange *, struct IStream *)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800cf408`
- `0x1801814b0`
- `0x18019c280`

## callees

- `0x18000f430`
- `0x18008a47c`
- `0x1800cfe20`
- `0x1800dce08`
- `0x1800dce48`
- `0x18012c68c`
- `0x18012c7a0`
- `0x18013d268`
- `0x180149808`
- `0x18015a000`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18015a61f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18015a61f`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteEnhMetaFile` at `0x18015a60d`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteEnhMetaFile` at `0x18015a60d`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18015a303`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18015a63a`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18015a303`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18015a63a`

## string_xrefs

- `0x18015a38c`: `OleCreateDefaultHandler`

## pseudocode

```c
__int64 __fastcall CRTFObject::InitReadStaticObject(
        CRTFObject *this,
        struct _reobject *a2,
        void **a3,
        int a4,
        int a5,
        int a6,
        struct CTxtRange *a7,
        struct IStream *a8)
{
  __int64 v10; // rcx
  __int64 v11; // r15
  __int64 v12; // rbx
  CTxtEdit *v13; // rcx
  unsigned int v14; // eax
  void *(__fastcall *v15)(struct CRTFObject *, void **); // r14
  GUID v16; // xmm0
  int v17; // r11d
  LONG v18; // eax
  int v19; // r12d
  LONG v20; // eax
  int v21; // r11d
  int v22; // r13d
  int v23; // edx
  int v24; // edx
  __int64 v25; // rcx
  bool v26; // zf
  void **v27; // r12
  __int64 v28; // rcx
  void *v29; // rcx
  int v30; // ebx
  int v31; // r13d
  struct COLE32_PROC *Ole32Procs; // rax
  struct COLE32_PROC *v33; // r14
  __int64 (__fastcall *v34)(CLSID *, _QWORD, GUID *, LPOLEOBJECT *); // rax
  LPOLEOBJECT *p_poleobj; // r14
  unsigned int v36; // r12d
  struct IOleClientSiteVtbl *lpVtbl; // rcx
  int v38; // eax
  LPOLECLIENTSITE v39; // rbx
  _DWORD *v40; // rdx
  void **v41; // rcx
  LPOLECLIENTSITE polesite; // [rsp+30h] [rbp-50h]
  LPOLECLIENTSITE *p_polesite; // [rsp+38h] [rbp-48h]
  HENHMETAFILE hmf[3]; // [rsp+40h] [rbp-40h] BYREF
  __int128 v46; // [rsp+58h] [rbp-28h] BYREF
  __int128 v47; // [rsp+68h] [rbp-18h]
  int v48; // [rsp+C8h] [rbp+48h] BYREF
  void **v49; // [rsp+D0h] [rbp+50h]
  int v50; // [rsp+D8h] [rbp+58h]

  v50 = a4;
  v49 = a3;
  v48 = 0;
  v10 = *((_QWORD *)a7 + 3);
  if ( v10 )
    v11 = *(_QWORD *)(v10 + 40);
  else
    v11 = 0;
  p_polesite = &a2->polesite;
  polesite = a2->polesite;
  v46 = 0;
  v47 = 0;
  v12 = *(_QWORD *)(v11 + 256);
  a7 = 0;
  a8 = 0;
  memset(hmf, 0, sizeof(hmf));
  if ( !CTxtEdit::GetRECallback((CTxtEdit *)v11) || !CTxtEdit::GetObjectMgr(v13) )
    return 2147500037LL;
  v14 = *((_DWORD *)this + 8) - 1;
  *((_QWORD *)&v46 + 1) = 0;
  *(_QWORD *)&v47 = 0xFFFFFFFF00000001uLL;
  v15 = 0;
  DWORD2(v47) = 0;
  if ( v14 > 0x3E7 )
    *((_DWORD *)this + 8) = 100;
  if ( (unsigned int)(*((_DWORD *)this + 9) - 1) > 0x3E7 )
    *((_DWORD *)this + 9) = 100;
  if ( !*(_WORD *)this )
  {
    v15 = ObHBuildBitmap;
LABEL_20:
    v16 = CLSID_StaticDib;
    v17 = 16;
    LOWORD(v46) = 2;
    goto LABEL_21;
  }
  if ( *(_WORD *)this == 1 )
  {
    v16 = CLSID_StaticMetafile;
    LOWORD(v46) = 3;
    v15 = ObHBuildMetafilePict;
    v17 = 32;
LABEL_21:
    DWORD2(v47) = v17;
    goto LABEL_22;
  }
  if ( *(_WORD *)this != 2 )
  {
    if ( *(_WORD *)this != 3 && *(_WORD *)this != 4 )
    {
      if ( *(_WORD *)this != 9 )
        goto LABEL_23;
      v16 = CLSID_Picture_EnhMetafile;
      LOWORD(v46) = 14;
      v17 = 64;
      v15 = ObHBuildEnhMetafilePict;
      goto LABEL_21;
    }
    goto LABEL_20;
  }
  v16 = CLSID_StaticDib;
  LOWORD(v46) = 8;
  v15 = ObHBuildDib;
  DWORD2(v47) = 1;
LABEL_22:
  a2->clsid = v16;
LABEL_23:
  a2->dvaspect = 1;
  v18 = CW32System::MulDivFunc(*((__int16 *)this + 20), 127, 72);
  a2->sizel.cx = v18;
  v19 = v18;
  v20 = CW32System::MulDivFunc(*((__int16 *)this + 21), 127, 72);
  a2->sizel.cy = v20;
  v22 = v20;
  v23 = *((_DWORD *)this + 8);
  if ( (unsigned int)(v23 - 1) <= 0x3E7 )
    a2->sizel.cx = CW32System::MulDivFunc(v19, v23, 100);
  v24 = *((_DWORD *)this + 9);
  if ( (unsigned int)(v24 - 1) <= 0x3E7 )
    a2->sizel.cy = CW32System::MulDivFunc(v22, v24, 100);
  LODWORD(hmf[0]) = v21;
  *(_OWORD *)&hmf[1] = 0;
  if ( v12 && v50 )
  {
    *(_BYTE *)(v12 + 143) = *(_BYTE *)this;
    *(_BYTE *)(v12 + 144) = *((_BYTE *)this + 2);
    v25 = *((unsigned int *)this + 5);
    if ( (unsigned int)(v25 + 0x8000) > 0xFFFF )
      goto LABEL_42;
    *(_WORD *)(v12 + 164) = v25;
    v25 = *((unsigned int *)this + 6);
    if ( (unsigned int)(v25 + 0x8000) > 0xFFFF )
      goto LABEL_42;
    *(_WORD *)(v12 + 166) = v25;
    v25 = *((unsigned int *)this + 8);
    if ( (unsigned int)(v25 + 0x8000) > 0xFFFF )
      goto LABEL_42;
    *(_WORD *)(v12 + 168) = v25;
    v25 = *((unsigned int *)this + 9);
    if ( (unsigned int)(v25 + 0x8000) > 0xFFFF
      || (*(_WORD *)(v12 + 170) = v25,
          *(_WORD *)(v12 + 172) = *((_WORD *)this + 20),
          *(_WORD *)(v12 + 174) = *((_WORD *)this + 21),
          v25 = *((unsigned int *)this + 24),
          (unsigned int)(v25 + 0x8000) > 0xFFFF)
      || (*(_WORD *)(v12 + 176) = v25, v25 = *((unsigned int *)this + 25), (unsigned int)(v25 + 0x8000) > 0xFFFF) )
    {
LABEL_42:
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v25, 0xFFFF);
    }
    v26 = *(_BYTE *)(v12 + 139) == 3;
    v27 = v49;
    *(_WORD *)(v12 + 178) = v25;
    *(_OWORD *)(v12 + 148) = *(_OWORD *)((char *)this + 52);
    *(_QWORD *)(v12 + 88) = *v27;
    if ( v26 )
    {
      v28 = *(_QWORD *)(v12 + 104);
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      v29 = *(void **)(v12 + 96);
      *(_QWORD *)(v12 + 104) = 0;
      if ( v29 )
        DeleteObject(v29);
      *(_QWORD *)(v12 + 96) = 0;
    }
    *(_BYTE *)(v12 + 139) = 3;
    *(_DWORD *)(v11 + 184) &= ~0x10000000u;
  }
  else
  {
    v27 = v49;
  }
  v30 = -2147467259;
  if ( (unsigned __int16)(*(_WORD *)this - 3) <= 1u )
    goto LABEL_77;
  if ( !v15 )
    goto LABEL_76;
  hmf[1] = (HENHMETAFILE)v15(this, v27);
  if ( hmf[1] )
  {
    v31 = a5;
    if ( a5 )
    {
      if ( !polesite )
        goto LABEL_77;
      lpVtbl = polesite[7].lpVtbl;
      if ( !lpVtbl )
        goto LABEL_77;
      p_poleobj = &a2->poleobj;
      (*(void (__fastcall **)(struct IOleClientSiteVtbl *, GUID *, LPOLEOBJECT *))lpVtbl->QueryInterface)(
        lpVtbl,
        &IID_IOleObject,
        &a2->poleobj);
      v36 = 1;
      LODWORD(v47) = 4;
      if ( !a6 )
        LODWORD(v47) = 1;
    }
    else
    {
      Ole32Procs = CThreadData::GetOle32Procs();
      v33 = (struct COLE32_PROC *)((char *)Ole32Procs + 304);
      if ( !*((_QWORD *)Ole32Procs + 38) )
        SetProcAddr((char *)Ole32Procs + 304, (unsigned int)(v31 + 1), "OleCreateDefaultHandler");
      v34 = *(__int64 (__fastcall **)(CLSID *, _QWORD, GUID *, LPOLEOBJECT *))v33;
      if ( !*(_QWORD *)v33 )
        goto LABEL_77;
      p_poleobj = &a2->poleobj;
      v30 = v34(&a2->clsid, 0, &IID_IOleObject, &a2->poleobj);
      if ( v30 )
        goto LABEL_77;
      v30 = CW32System::WriteClassStg(a2->pstg, &a2->clsid);
      if ( v30 )
        goto LABEL_77;
      v30 = ((__int64 (__fastcall *)(LPOLEOBJECT, GUID *, struct IStream **))(*p_poleobj)->lpVtbl->QueryInterface)(
              *p_poleobj,
              &IID_IPersistStorage,
              &a8);
      if ( v30 )
        goto LABEL_77;
      v30 = (*(__int64 (__fastcall **)(struct IStream *, LPSTORAGE))(*(_QWORD *)a8 + 40LL))(a8, a2->pstg);
      if ( v30 )
        goto LABEL_77;
      v36 = 2;
    }
    if ( !*p_poleobj
      || (v30 = ((__int64 (__fastcall *)(LPOLEOBJECT, GUID *, struct CTxtRange **))(*p_poleobj)->lpVtbl->QueryInterface)(
                  *p_poleobj,
                  &IID_IOleCache,
                  &a7)) == 0 )
    {
      if ( a7 )
      {
        v30 = (*(__int64 (__fastcall **)(struct CTxtRange *, __int128 *, _QWORD, int *))(*(_QWORD *)a7 + 24LL))(
                a7,
                &v46,
                v36,
                &v48);
        if ( v30 < 0 )
          goto LABEL_77;
        v38 = (*(__int64 (__fastcall **)(struct CTxtRange *, __int128 *, HENHMETAFILE *, __int64))(*(_QWORD *)a7 + 56LL))(
                a7,
                &v46,
                hmf,
                1);
        v30 = v38;
        if ( v38 )
        {
          if ( v38 >= 0 )
            hmf[1] = 0;
          goto LABEL_77;
        }
        hmf[1] = 0;
      }
      if ( v31 )
      {
        *(SIZEL *)((char *)polesite + 84) = a2->sizel;
        goto LABEL_76;
      }
      (*(void (__fastcall **)(__int64, LPOLECLIENTSITE *))(*(_QWORD *)(v11 + 8) + 24LL))(v11 + 8, p_polesite);
      if ( !*p_polesite )
        goto LABEL_77;
      if ( *p_poleobj )
      {
        v30 = ((__int64 (__fastcall *)(LPOLEOBJECT))(*p_poleobj)->lpVtbl->SetClientSite)(*p_poleobj);
        if ( v30 )
          goto LABEL_77;
      }
      if ( *p_poleobj )
        goto LABEL_76;
      if ( *(_WORD *)this == 2 )
      {
        v39 = *p_polesite;
        v40 = operator new(0x10u);
        v40[2] = 0;
        *((_WORD *)v40 + 6) = 0;
        v41 = v49;
        *(_QWORD *)v40 = 0;
        v39[14].lpVtbl = (struct IOleClientSiteVtbl *)*v41;
        *v40 = *((_DWORD *)this + 8);
        v40[1] = *((_DWORD *)this + 9);
        *((_WORD *)v40 + 4) = *((_WORD *)this + 20);
        *((_WORD *)v40 + 5) = *((_WORD *)this + 21);
        *((_WORD *)v40 + 6) = *((_WORD *)this + 4);
        v39[16].lpVtbl = (struct IOleClientSiteVtbl *)v40;
        hmf[1] = 0;
LABEL_76:
        v30 = 0;
      }
    }
  }
LABEL_77:
  if ( a7 )
    (*(void (__fastcall **)(struct CTxtRange *))(*(_QWORD *)a7 + 16LL))(a7);
  if ( a8 )
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)a8 + 16LL))(a8);
  if ( hmf[1] )
  {
    if ( *(_WORD *)this )
    {
      if ( *(_WORD *)this == 1 )
      {
        GlobalUnlock(hmf[1]);
        CW32System::GlobalFree(hmf[1]);
      }
      else if ( *(_WORD *)this == 9 )
      {
        DeleteEnhMetaFile(hmf[1]);
      }
    }
    else
    {
      DeleteObject(hmf[1]);
    }
  }
  return (unsigned int)v30;
}

```

## disassembly

```asm
0x18015a000  mov     [rsp-38h+arg_0], rbx
0x18015a005  mov     [rsp-38h+arg_18], r9d
0x18015a00a  mov     [rsp-38h+arg_10], r8
0x18015a00f  push    rbp
0x18015a010  push    rsi
0x18015a011  push    rdi
0x18015a012  push    r12
0x18015a014  push    r13
0x18015a016  push    r14
0x18015a018  push    r15
0x18015a01a  mov     rbp, rsp
0x18015a01d  sub     rsp, 80h
0x18015a024  mov     rax, [rbp+arg_30]
0x18015a028  xor     r12d, r12d
0x18015a02b  mov     rdi, rcx
0x18015a02e  mov     [rbp+arg_8], r12d
0x18015a032  mov     rsi, rdx
0x18015a035  mov     rcx, [rax+18h]
0x18015a039  test    rcx, rcx
0x18015a03c  jz      short loc_18015A044
0x18015a03e  mov     r15, [rcx+28h]
0x18015a042  jmp     short loc_18015A047
0x18015a044  mov     r15, r12
0x18015a047  xorps   xmm0, xmm0
0x18015a04a  lea     rax, [rdx+28h]
0x18015a04e  mov     [rbp+var_48], rax
0x18015a052  mov     rcx, r15; this
0x18015a055  mov     rax, [rax]
0x18015a058  mov     [rbp+var_50], rax
0x18015a05c  xor     eax, eax
0x18015a05e  movups  [rbp+var_28], xmm0
0x18015a062  movups  [rbp+var_18], xmm0
0x18015a066  mov     rbx, [r15+100h]
0x18015a06d  mov     [rbp+var_30], rax
0x18015a071  mov     [rbp+arg_30], r12
0x18015a075  mov     [rbp+arg_38], r12
0x18015a079  movups  xmmword ptr [rbp+hmf], xmm0
0x18015a07d  call    ?GetRECallback@CTxtEdit@@QEAAPEAUIRichEditOleCallback@@XZ; CTxtEdit::GetRECallback(void)
0x18015a082  test    rax, rax
0x18015a085  jz      loc_18015A64A
0x18015a08b  call    ?GetObjectMgr@CTxtEdit@@QEAAPEAVCObjectMgr@@XZ; CTxtEdit::GetObjectMgr(void)
0x18015a090  test    rax, rax
0x18015a093  jz      loc_18015A64A
0x18015a099  mov     eax, [rdi+20h]
0x18015a09c  mov     edx, 1
0x18015a0a1  sub     eax, edx
0x18015a0a3  mov     qword ptr [rbp+var_28+8], r12
0x18015a0a7  mov     r8d, 3E7h
0x18015a0ad  mov     dword ptr [rbp+var_18], edx
0x18015a0b0  mov     dword ptr [rbp+var_18+4], 0FFFFFFFFh
0x18015a0b7  mov     r14, r12
0x18015a0ba  mov     dword ptr [rbp+var_18+8], r12d
0x18015a0be  lea     ecx, [rdx+63h]
0x18015a0c1  mov     r11d, r12d
0x18015a0c4  cmp     eax, r8d
0x18015a0c7  jbe     short loc_18015A0CC
0x18015a0c9  mov     [rdi+20h], ecx
0x18015a0cc  mov     eax, [rdi+24h]
0x18015a0cf  sub     eax, edx
0x18015a0d1  cmp     eax, r8d
0x18015a0d4  jbe     short loc_18015A0D9
0x18015a0d6  mov     [rdi+24h], ecx
0x18015a0d9  movsx   ecx, word ptr [rdi]
0x18015a0dc  mov     eax, 3
0x18015a0e1  lea     r8d, [rax-1]
0x18015a0e5  lea     r9d, [rax+5]
0x18015a0e9  test    ecx, ecx
0x18015a0eb  jz      short loc_18015A152
0x18015a0ed  sub     ecx, edx
0x18015a0ef  jz      short loc_18015A138
0x18015a0f1  sub     ecx, edx
0x18015a0f3  jz      short loc_18015A11D
0x18015a0f5  sub     ecx, edx
0x18015a0f7  jz      short loc_18015A159
0x18015a0f9  sub     ecx, edx
0x18015a0fb  jz      short loc_18015A159
0x18015a0fd  cmp     ecx, 5
0x18015a100  jnz     short loc_18015A174
0x18015a102  movups  xmm0, xmmword ptr cs:CLSID_Picture_EnhMetafile.Data1
0x18015a109  lea     eax, [rcx+9]
0x18015a10c  mov     word ptr [rbp+var_28], ax
0x18015a110  lea     r11d, [r8+3Eh]
0x18015a114  lea     r14, ?ObHBuildEnhMetafilePict@@YAPEAXPEAVCRTFObject@@AEAPEAX@Z; ObHBuildEnhMetafilePict(CRTFObject *,void * &)
0x18015a11b  jmp     short loc_18015A16B
0x18015a11d  movups  xmm0, xmmword ptr cs:CLSID_StaticDib.Data1
0x18015a124  mov     word ptr [rbp+var_28], r9w
0x18015a129  lea     r14, ?ObHBuildDib@@YAPEAXPEAVCRTFObject@@AEAPEAX@Z; ObHBuildDib(CRTFObject *,void * &)
0x18015a130  mov     r11d, edx
0x18015a133  mov     dword ptr [rbp+var_18+8], edx
0x18015a136  jmp     short loc_18015A16F
0x18015a138  movups  xmm0, xmmword ptr cs:CLSID_StaticMetafile.Data1
0x18015a13f  mov     word ptr [rbp+var_28], ax
0x18015a143  lea     r14, ?ObHBuildMetafilePict@@YAPEAXPEAVCRTFObject@@AEAPEAX@Z; ObHBuildMetafilePict(CRTFObject *,void * &)
0x18015a14a  mov     r11d, 20h ; ' '
0x18015a150  jmp     short loc_18015A16B
0x18015a152  lea     r14, ?ObHBuildBitmap@@YAPEAXPEAVCRTFObject@@AEAPEAX@Z; ObHBuildBitmap(CRTFObject *,void * &)
0x18015a159  movups  xmm0, xmmword ptr cs:CLSID_StaticDib.Data1
0x18015a160  mov     r11d, 10h
0x18015a166  mov     word ptr [rbp+var_28], r8w
0x18015a16b  mov     dword ptr [rbp+var_18+8], r11d
0x18015a16f  movdqu  xmmword ptr [rsi+8], xmm0
0x18015a174  mov     [rsi+38h], edx
0x18015a177  mov     r8d, 48h ; 'H'; int
0x18015a17d  movsx   ecx, word ptr [rdi+28h]; int
0x18015a181  lea     r13d, [r8+37h]
0x18015a185  mov     edx, r13d; int
0x18015a188  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18015a18d  mov     [rsi+30h], eax
0x18015a190  lea     r8d, [r13-37h]; int
0x18015a194  movsx   ecx, word ptr [rdi+2Ah]; int
0x18015a198  mov     edx, r13d; int
0x18015a19b  mov     r12d, eax
0x18015a19e  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18015a1a3  mov     [rsi+34h], eax
0x18015a1a6  mov     r13d, eax
0x18015a1a9  mov     edx, [rdi+20h]; int
0x18015a1ac  lea     ecx, [rdx-1]
0x18015a1af  cmp     ecx, 3E7h
0x18015a1b5  ja      short loc_18015A1C8
0x18015a1b7  mov     r8d, 64h ; 'd'; int
0x18015a1bd  mov     ecx, r12d; int
0x18015a1c0  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18015a1c5  mov     [rsi+30h], eax
0x18015a1c8  mov     edx, [rdi+24h]; int
0x18015a1cb  lea     eax, [rdx-1]
0x18015a1ce  cmp     eax, 3E7h
0x18015a1d3  ja      short loc_18015A1E6
0x18015a1d5  mov     r8d, 64h ; 'd'; int
0x18015a1db  mov     ecx, r13d; int
0x18015a1de  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18015a1e3  mov     [rsi+34h], eax
0x18015a1e6  xor     r13d, r13d
0x18015a1e9  mov     dword ptr [rbp+hmf], r11d
0x18015a1ed  xorps   xmm0, xmm0
0x18015a1f0  movdqu  xmmword ptr [rbp+hmf+8], xmm0
0x18015a1f5  test    rbx, rbx
0x18015a1f8  jz      loc_18015A32B
0x18015a1fe  cmp     [rbp+arg_18], r13d
0x18015a202  jz      loc_18015A32B
0x18015a208  mov     al, [rdi]
0x18015a20a  mov     edx, 0FFFFh
0x18015a20f  mov     [rbx+8Fh], al
0x18015a215  mov     al, [rdi+2]
0x18015a218  mov     [rbx+90h], al
0x18015a21e  mov     ecx, [rdi+14h]
0x18015a221  lea     eax, [rcx+8000h]
0x18015a227  cmp     eax, edx
0x18015a229  ja      loc_18015A325
0x18015a22f  mov     [rbx+0A4h], cx
0x18015a236  mov     ecx, [rdi+18h]
0x18015a239  lea     eax, [rcx+8000h]
0x18015a23f  cmp     eax, edx
0x18015a241  ja      loc_18015A325
0x18015a247  mov     [rbx+0A6h], cx
0x18015a24e  mov     ecx, [rdi+20h]
0x18015a251  lea     eax, [rcx+8000h]
0x18015a257  cmp     eax, edx
0x18015a259  ja      loc_18015A325
0x18015a25f  mov     [rbx+0A8h], cx
0x18015a266  mov     ecx, [rdi+24h]
0x18015a269  lea     eax, [rcx+8000h]
0x18015a26f  cmp     eax, edx
0x18015a271  ja      loc_18015A325
0x18015a277  mov     [rbx+0AAh], cx
0x18015a27e  movzx   eax, word ptr [rdi+28h]
0x18015a282  mov     [rbx+0ACh], ax
0x18015a289  movzx   eax, word ptr [rdi+2Ah]
0x18015a28d  mov     [rbx+0AEh], ax
0x18015a294  mov     ecx, [rdi+60h]
0x18015a297  lea     eax, [rcx+8000h]
0x18015a29d  cmp     eax, edx
0x18015a29f  ja      loc_18015A325
0x18015a2a5  mov     [rbx+0B0h], cx
0x18015a2ac  mov     ecx, [rdi+64h]
0x18015a2af  lea     eax, [rcx+8000h]
0x18015a2b5  cmp     eax, edx
0x18015a2b7  ja      short loc_18015A325
0x18015a2b9  cmp     byte ptr [rbx+8Bh], 3
0x18015a2c0  mov     r12, [rbp+arg_10]
0x18015a2c4  mov     [rbx+0B2h], cx
0x18015a2cb  movups  xmm0, xmmword ptr [rdi+34h]
0x18015a2cf  movdqu  xmmword ptr [rbx+94h], xmm0
0x18015a2d7  mov     rax, [r12]
0x18015a2db  mov     [rbx+58h], rax
0x18015a2df  jnz     short loc_18015A313
0x18015a2e1  mov     rcx, [rbx+68h]
0x18015a2e5  test    rcx, rcx
0x18015a2e8  jz      short loc_18015A2F6
0x18015a2ea  mov     rax, [rcx]
0x18015a2ed  mov     rax, [rax+10h]
0x18015a2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a2f6  mov     rcx, [rbx+60h]; ho
0x18015a2fa  mov     [rbx+68h], r13
0x18015a2fe  test    rcx, rcx
0x18015a301  jz      short loc_18015A30F
0x18015a303  call    cs:__imp_DeleteObject
0x18015a30a  nop     dword ptr [rax+rax+00h]
0x18015a30f  mov     [rbx+60h], r13
0x18015a313  mov     byte ptr [rbx+8Bh], 3
0x18015a31a  btr     dword ptr [r15+0B8h], 1Ch
0x18015a323  jmp     short loc_18015A32F
0x18015a325  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18015a32b  mov     r12, [rbp+arg_10]
0x18015a32f  movzx   ecx, word ptr [rdi]
0x18015a332  mov     eax, 1
0x18015a337  sub     cx, 3
0x18015a33b  mov     ebx, 80004005h
0x18015a340  cmp     cx, ax
0x18015a343  jbe     loc_18015A5C9
0x18015a349  test    r14, r14
0x18015a34c  jz      loc_18015A5C7
0x18015a352  mov     rdx, r12
0x18015a355  mov     rcx, rdi
0x18015a358  mov     rax, r14
0x18015a35b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a360  mov     [rbp+hmf+8], rax
0x18015a364  test    rax, rax
0x18015a367  jz      loc_18015A5C9
0x18015a36d  mov     r13d, [rbp+arg_20]
0x18015a371  test    r13d, r13d
0x18015a374  jnz     loc_18015A42C
0x18015a37a  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18015a37f  lea     r14, [rax+130h]
0x18015a386  cmp     qword ptr [r14], 0
0x18015a38a  jnz     short loc_18015A39F
0x18015a38c  lea     r8, aOlecreatedefau; "OleCreateDefaultHandler"
0x18015a393  mov     rcx, r14
0x18015a396  lea     edx, [r13+1]
0x18015a39a  call    ?SetProcAddr@@YAXAEAPEAXW4DLL_ENUM@@PEBD@Z; SetProcAddr(void * &,DLL_ENUM,char const *)
0x18015a39f  mov     rax, [r14]
0x18015a3a2  test    rax, rax
0x18015a3a5  jz      loc_18015A5C9
0x18015a3ab  lea     r14, [rsi+18h]
0x18015a3af  xor     edx, edx
0x18015a3b1  mov     r9, r14
0x18015a3b4  lea     r8, IID_IOleObject
0x18015a3bb  lea     rcx, [rsi+8]
0x18015a3bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a3c4  mov     ebx, eax
0x18015a3c6  test    eax, eax
0x18015a3c8  jnz     loc_18015A5C9
0x18015a3ce  mov     rcx, [rsi+20h]; struct IStorage *
0x18015a3d2  lea     rdx, [rsi+8]; struct _GUID *
0x18015a3d6  call    ?WriteClassStg@CW32System@@SAJPEAUIStorage@@AEBU_GUID@@@Z; CW32System::WriteClassStg(IStorage *,_GUID const &)
0x18015a3db  mov     ebx, eax
0x18015a3dd  test    eax, eax
0x18015a3df  jnz     loc_18015A5C9
0x18015a3e5  mov     rcx, [r14]
0x18015a3e8  lea     r8, [rbp+arg_38]
0x18015a3ec  lea     rdx, IID_IPersistStorage
0x18015a3f3  mov     rax, [rcx]
0x18015a3f6  mov     rax, [rax]
0x18015a3f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a3fe  mov     ebx, eax
0x18015a400  test    eax, eax
0x18015a402  jnz     loc_18015A5C9
0x18015a408  mov     rcx, [rbp+arg_38]
0x18015a40c  mov     rdx, [rsi+20h]
0x18015a410  mov     rax, [rcx]
0x18015a413  mov     rax, [rax+28h]
0x18015a417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a41c  mov     ebx, eax
0x18015a41e  test    eax, eax
0x18015a420  jnz     loc_18015A5C9
0x18015a426  lea     r12d, [rax+2]
0x18015a42a  jmp     short loc_18015A477
0x18015a42c  mov     rax, [rbp+var_50]
0x18015a430  test    rax, rax
0x18015a433  jz      loc_18015A5C9
0x18015a439  mov     rcx, [rax+38h]
0x18015a43d  test    rcx, rcx
0x18015a440  jz      loc_18015A5C9
0x18015a446  mov     rax, [rcx]
0x18015a449  lea     r14, [rsi+18h]
0x18015a44d  mov     r8, r14
0x18015a450  lea     rdx, IID_IOleObject
0x18015a457  mov     rax, [rax]
0x18015a45a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a45f  cmp     [rbp+arg_28], 0
0x18015a463  mov     eax, 1
0x18015a468  mov     r12d, eax
0x18015a46b  mov     dword ptr [rbp+var_18], 4
0x18015a472  jnz     short loc_18015A477
0x18015a474  mov     dword ptr [rbp+var_18], eax
0x18015a477  mov     rcx, [r14]
0x18015a47a  test    rcx, rcx
0x18015a47d  jz      short loc_18015A49F
0x18015a47f  mov     rax, [rcx]
0x18015a482  lea     r8, [rbp+arg_30]
0x18015a486  lea     rdx, IID_IOleCache
0x18015a48d  mov     rax, [rax]
0x18015a490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a495  mov     ebx, eax
0x18015a497  test    eax, eax
0x18015a499  jnz     loc_18015A5C9
0x18015a49f  mov     rcx, [rbp+arg_30]
0x18015a4a3  test    rcx, rcx
0x18015a4a6  jz      short loc_18015A508
0x18015a4a8  mov     rax, [rcx]
0x18015a4ab  lea     r9, [rbp+arg_8]
  ... truncated ...
```
