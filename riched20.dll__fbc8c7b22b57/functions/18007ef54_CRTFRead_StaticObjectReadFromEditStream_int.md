# CRTFRead::StaticObjectReadFromEditStream(int)

- ea: `0x18007ef54`
- end: `0x18007f74b`
- name: `?StaticObjectReadFromEditStream@CRTFRead@@AEAAHH@Z`
- size: `2039`
- prototype: `int(CRTFRead *__hidden this, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002740`

## callees

- `0x18002720c`
- `0x1800274a0`
- `0x18002da30`
- `0x180039990`
- `0x1800427ac`
- `0x18004bac8`
- `0x18005d214`
- `0x180071cdc`
- `0x18007ef54`
- `0x1800931b0`
- `0x180093bca`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x18007f2c4`
- `KERNEL32!GlobalAlloc` at `0x18007f2c4`
- `KERNEL32!GlobalLock` at `0x18007f2d8`
- `KERNEL32!GlobalLock` at `0x18007f2d8`
- `KERNEL32!GlobalUnlock` at `0x18007f1d5`
- `KERNEL32!GlobalUnlock` at `0x18007f214`
- `KERNEL32!GlobalUnlock` at `0x18007f360`
- `KERNEL32!GlobalUnlock` at `0x18007f1d5`
- `KERNEL32!GlobalUnlock` at `0x18007f214`
- `KERNEL32!GlobalUnlock` at `0x18007f360`
- `GDI32!DeleteObject` at `0x18007f701`
- `GDI32!DeleteObject` at `0x18007f701`

## string_xrefs

- `0x18007f243`: `CreateStreamOnHGlobal`
- `0x18007f41a`: `OleCreateDefaultHandler`

## pseudocode

```c
__int64 __fastcall CRTFRead::StaticObjectReadFromEditStream(CRTFRead *this, unsigned int a2)
{
  SIZE_T v2; // r14
  CTxtEdit *v4; // rcx
  void *(__fastcall *v5)(struct _rtfobject *, void **); // r12
  int v6; // edi
  void *v7; // r15
  __int64 v8; // r13
  __int16 *v9; // rdx
  __int16 v10; // ax
  int v11; // ecx
  int v12; // ecx
  GUID v13; // xmm0
  int v14; // ebx
  int v15; // ecx
  __int64 v16; // rbx
  int v17; // ecx
  _WORD *v18; // rax
  struct COLE32_PROC *Ole32Procs; // rax
  struct COLE32_PROC *v20; // rbx
  _DWORD *v21; // rbx
  int v22; // eax
  __int64 v23; // r8
  __int64 v24; // rbx
  struct COLE32_PROC *v25; // rax
  __int64 (__fastcall **v26)(__int64, HGLOBAL *); // rdi
  void *v27; // rax
  struct COLE32_PROC *v28; // rax
  __int64 (__fastcall **v29)(CLSID *, _QWORD, GUID *, LPOLEOBJECT *); // rbx
  unsigned int v30; // ebx
  __int64 v31; // rcx
  __int64 (__fastcall ***v32)(_QWORD, GUID *, LPOLEOBJECT *); // rcx
  int v33; // eax
  LPOLECLIENTSITE polesite; // rbx
  _DWORD *v35; // rax
  LONG *v36; // rcx
  struct IUndoBuilder *v37; // r9
  int inserted; // eax
  __int16 v40; // [rsp+44h] [rbp-BCh] BYREF
  HGLOBAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+58h] [rbp-A8h] BYREF
  int v44; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v45; // [rsp+68h] [rbp-98h] BYREF
  HGLOBAL ho[3]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v47; // [rsp+88h] [rbp-78h] BYREF
  __int128 v48; // [rsp+98h] [rbp-68h]
  __int64 v49; // [rsp+A8h] [rbp-58h]
  CObjectMgr *ObjectMgr; // [rsp+B0h] [rbp-50h]
  struct _reobject v51; // [rsp+C0h] [rbp-40h] BYREF

  v2 = a2;
  v44 = 0;
  v4 = (CTxtEdit *)*((_QWORD *)this + 7);
  v40 = -4;
  v5 = 0;
  v47 = 0;
  hMem = 0;
  v6 = -2147467259;
  v48 = 0;
  ObjectMgr = CTxtEdit::GetObjectMgr(v4);
  v45 = 0;
  v42 = 0;
  memset_0(&v51, 0, sizeof(v51));
  v43 = 0;
  v7 = 0;
  memset(ho, 0, sizeof(ho));
  if ( !ObjectMgr )
    goto LABEL_16;
  v8 = *((_QWORD *)ObjectMgr + 4);
  v9 = (__int16 *)*((_QWORD *)this + 79);
  *((_QWORD *)&v47 + 1) = 0;
  v10 = 2;
  LODWORD(v48) = 1;
  *(_QWORD *)((char *)&v48 + 4) = 0xFFFFFFFFLL;
  v11 = *v9;
  v49 = v8;
  if ( !v11 )
  {
    DWORD2(v48) = 16;
    v5 = ObHBuildBitmap;
LABEL_8:
    v13 = CLSID_StaticDib;
    LOWORD(v47) = v10;
    goto LABEL_9;
  }
  v12 = v11 - 1;
  if ( v12 )
  {
    if ( v12 != 1 )
      goto LABEL_10;
    v10 = 8;
    DWORD2(v48) = 1;
    v5 = ObHBuildDib;
    goto LABEL_8;
  }
  v13 = CLSID_StaticMetafile;
  LOWORD(v47) = 3;
  v5 = ObHBuildMetafilePict;
  DWORD2(v48) = 32;
LABEL_9:
  v51.clsid = v13;
LABEL_10:
  v14 = *((_DWORD *)v9 + 6);
  v15 = v14 * CW32System::MulDiv(v9[16], 127, 72);
  v16 = *((_QWORD *)this + 79);
  v51.sizel.cx = v15 / 100;
  v17 = *(_DWORD *)(v16 + 28) * CW32System::MulDiv(*(__int16 *)(v16 + 34), 127, 72);
  *(_OWORD *)&ho[1] = 0;
  v51.sizel.cy = v17 / 100;
  LODWORD(ho[0]) = DWORD2(v48);
  if ( v8 )
  {
    if ( (*((_BYTE *)this + 472) & 4) == 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, LPSTORAGE *))(*(_QWORD *)v8 + 24LL))(v8, &v51.pstg);
      if ( v6 )
        goto LABEL_13;
    }
    Ole32Procs = CThreadData::GetOle32Procs();
    v20 = (struct COLE32_PROC *)((char *)Ole32Procs + 272);
    if ( !*((_QWORD *)Ole32Procs + 34) )
      SetProcAddr((char *)Ole32Procs + 272, 1, "CreateStreamOnHGlobal");
    if ( *(_QWORD *)v20 )
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))v20)(0, 0, &v43);
      if ( !v6 )
      {
        LODWORD(v2) = 0x4000;
        while ( 1 )
        {
          v7 = CW32System::PvAlloc(v2, 0);
          if ( v7 )
            goto LABEL_48;
          LODWORD(v2) = v2 - 1024;
          if ( (int)v2 < 1024 )
            goto LABEL_42;
        }
      }
    }
    else
    {
      v6 = -2147467259;
    }
    LODWORD(v5) = 0;
    goto LABEL_14;
  }
  if ( !(_DWORD)v2 )
    goto LABEL_46;
  hMem = GlobalAlloc(0, v2);
  v7 = GlobalLock(hMem);
  if ( !v7 )
    goto LABEL_13;
LABEL_48:
  v21 = (_DWORD *)((char *)this + 48);
  while ( 1 )
  {
    v22 = (**((__int64 (__fastcall ***)(char *, void *, _QWORD))this + 80))((char *)this + 640, v7, (unsigned int)v2);
    v23 = (unsigned int)v22;
    if ( v22 <= 0 )
      break;
    v21 = (_DWORD *)((char *)this + 48);
    if ( *((_DWORD *)this + 12) )
      break;
    if ( v43 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, _QWORD))(*(_QWORD *)v43 + 32LL))(
             v43,
             v7,
             (unsigned int)v22,
             0);
      if ( v6 )
        goto LABEL_42;
    }
  }
  if ( *v21 )
    goto LABEL_13;
  if ( hMem )
  {
    GlobalUnlock(hMem);
    v7 = 0;
  }
  v24 = v43;
  if ( v43 )
  {
    v25 = CThreadData::GetOle32Procs();
    v26 = (__int64 (__fastcall **)(__int64, HGLOBAL *))((char *)v25 + 280);
    if ( !*((_QWORD *)v25 + 35) )
      SetProcAddr((char *)v25 + 280, 1, "GetHGlobalFromStream");
    if ( !*v26 )
      goto LABEL_73;
    v6 = (*v26)(v24, &hMem);
    if ( v6 )
      goto LABEL_13;
  }
  if ( !v5 )
  {
LABEL_46:
    LODWORD(v5) = 1;
    goto LABEL_14;
  }
  v27 = (void *)((__int64 (__fastcall *)(_QWORD, HGLOBAL *, __int64))v5)(*((_QWORD *)this + 79), &hMem, v23);
  ho[1] = v27;
  if ( !v49 )
    goto LABEL_84;
  if ( !v27 )
    goto LABEL_13;
  if ( (*((_BYTE *)this + 472) & 4) == 0 )
  {
    v28 = CThreadData::GetOle32Procs();
    v29 = (__int64 (__fastcall **)(CLSID *, _QWORD, GUID *, LPOLEOBJECT *))((char *)v28 + 288);
    if ( !*((_QWORD *)v28 + 36) )
      SetProcAddr((char *)v28 + 288, 1, "OleCreateDefaultHandler");
    if ( *v29 )
    {
      v6 = (*v29)(&v51.clsid, 0, &IID_IOleObject, &v51.poleobj);
      if ( !v6 )
      {
        v6 = ((__int64 (__fastcall *)(LPOLEOBJECT, GUID *, __int64 *))v51.poleobj->lpVtbl->QueryInterface)(
               v51.poleobj,
               &IID_IPersistStorage,
               &v45);
        if ( v6 )
          goto LABEL_42;
        v6 = (*(__int64 (__fastcall **)(__int64, LPSTORAGE))(*(_QWORD *)v45 + 40LL))(v45, v51.pstg);
        if ( v6 )
          goto LABEL_42;
        v30 = 2;
        goto LABEL_78;
      }
LABEL_13:
      LODWORD(v5) = 0;
      goto LABEL_14;
    }
LABEL_73:
    v6 = -2147467259;
    goto LABEL_13;
  }
  v31 = *((_QWORD *)this + 58);
  if ( !v31 )
    goto LABEL_73;
  v32 = *(__int64 (__fastcall ****)(_QWORD, GUID *, LPOLEOBJECT *))(v31 + 72);
  if ( !v32 )
    goto LABEL_73;
  v6 = (**v32)(v32, &IID_IOleObject, &v51.poleobj);
  if ( v6 < 0 )
    goto LABEL_13;
  v30 = 1;
  LODWORD(v48) = (*((_BYTE *)this + 472) & 2) != 0 ? 4 : 1;
LABEL_78:
  v6 = ((__int64 (__fastcall *)(LPOLEOBJECT, GUID *, __int64 *))v51.poleobj->lpVtbl->QueryInterface)(
         v51.poleobj,
         &IID_IOleCache,
         &v42);
  if ( v6 )
    goto LABEL_13;
  v6 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, int *))(*(_QWORD *)v42 + 24LL))(v42, &v47, v30, &v44);
  if ( v6 < 0 )
    goto LABEL_13;
  v33 = (*(__int64 (__fastcall **)(__int64, __int128 *, HGLOBAL *, __int64))(*(_QWORD *)v42 + 56LL))(v42, &v47, ho, 1);
  v6 = v33;
  if ( v33 )
  {
    if ( v33 >= 0 )
    {
      ho[1] = 0;
      goto LABEL_13;
    }
    goto LABEL_42;
  }
  ho[1] = 0;
LABEL_84:
  if ( (*((_BYTE *)this + 472) & 4) == 0 )
  {
    (*(void (__fastcall **)(__int64, LPOLECLIENTSITE *))(*(_QWORD *)(*((_QWORD *)this + 7) + 8LL) + 24LL))(
      *((_QWORD *)this + 7) + 8LL,
      &v51.polesite);
    if ( !v51.polesite )
      goto LABEL_13;
    if ( v51.poleobj )
    {
      v6 = ((__int64 (__fastcall *)(LPOLEOBJECT))v51.poleobj->lpVtbl->SetClientSite)(v51.poleobj);
      if ( v6 )
        goto LABEL_42;
      if ( v51.poleobj )
        goto LABEL_92;
    }
    if ( **((_WORD **)this + 79) != 2 )
      goto LABEL_13;
    polesite = v51.polesite;
    v35 = CW32System::PvAlloc(0x10u, 0x40u);
    if ( v35 )
    {
      polesite[15].lpVtbl = (struct IOleClientSiteVtbl *)hMem;
      *v35 = *(_DWORD *)(*((_QWORD *)this + 79) + 24LL);
      v35[1] = *(_DWORD *)(*((_QWORD *)this + 79) + 28LL);
      *((_WORD *)v35 + 4) = *(_WORD *)(*((_QWORD *)this + 79) + 32LL);
      *((_WORD *)v35 + 5) = *(_WORD *)(*((_QWORD *)this + 79) + 34LL);
      *((_WORD *)v35 + 6) = *(_WORD *)(*((_QWORD *)this + 79) + 8LL);
      polesite[17].lpVtbl = (struct IOleClientSiteVtbl *)v35;
      ho[1] = 0;
LABEL_92:
      v36 = (LONG *)*((_QWORD *)this + 8);
      v51.cbStruct = 72;
      v51.cp = v36[10];
      v51.dvaspect = 1;
      v51.dwFlags = 1;
      CTxtRange::Set_iCF((CTxtRange *)v36, -1);
      (*(void (__fastcall **)(_QWORD, __int64, __int16 *, _QWORD, _DWORD, _QWORD, _DWORD))(**((_QWORD **)this + 8)
                                                                                         + 560LL))(
        *((_QWORD *)this + 8),
        1,
        &v40,
        0,
        0,
        0,
        0);
      inserted = CObjectMgr::InsertObject(ObjectMgr, v51.cp, &v51, v37);
      v6 = 0;
      if ( inserted != 1 )
        v6 = inserted;
      goto LABEL_96;
    }
LABEL_42:
    LODWORD(v5) = 0;
    goto LABEL_14;
  }
  *(SIZEL *)(*((_QWORD *)this + 58) + 104LL) = v51.sizel;
LABEL_96:
  LODWORD(v5) = 1;
LABEL_14:
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
LABEL_16:
  if ( v51.pstg )
    ((void (__fastcall *)(LPSTORAGE))v51.pstg->lpVtbl->Release)(v51.pstg);
  if ( v51.polesite )
    ((void (__fastcall *)(LPOLECLIENTSITE))v51.polesite->lpVtbl->Release)(v51.polesite);
  if ( v51.poleobj )
    ((void (__fastcall *)(LPOLEOBJECT))v51.poleobj->lpVtbl->Release)(v51.poleobj);
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    CW32System::FreePv(v7);
    v7 = 0;
  }
  if ( v6 || *((_DWORD *)this + 12) )
  {
    if ( v7 )
      GlobalUnlock(hMem);
    CW32System::GlobalFree(hMem);
  }
  if ( ho[1] )
  {
    v18 = (_WORD *)*((_QWORD *)this + 79);
    if ( *v18 )
    {
      if ( *v18 == 1 )
      {
        GlobalUnlock(ho[1]);
        CW32System::GlobalFree(ho[1]);
      }
    }
    else
    {
      DeleteObject(ho[1]);
    }
  }
  *((_QWORD *)this + 58) = 0;
  *((_WORD *)this + 236) &= 0xFFF9u;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007ef54  mov     [rsp-8+arg_10], rbx
0x18007ef59  push    rbp
0x18007ef5a  push    rsi
0x18007ef5b  push    rdi
0x18007ef5c  push    r12
0x18007ef5e  push    r13
0x18007ef60  push    r14
0x18007ef62  push    r15
0x18007ef64  lea     rbp, [rsp-20h]
0x18007ef69  sub     rsp, 120h
0x18007ef70  mov     rax, cs:__security_cookie
0x18007ef77  xor     rax, rsp
0x18007ef7a  mov     [rbp+50h+var_40], rax
0x18007ef7e  xor     r13d, r13d
0x18007ef81  mov     r14d, edx
0x18007ef84  xorps   xmm0, xmm0
0x18007ef87  mov     [rsp+150h+var_F0], r13d
0x18007ef8c  mov     rsi, rcx
0x18007ef8f  mov     [rsp+150h+var_110], r13d
0x18007ef94  mov     rcx, [rcx+38h]; this
0x18007ef98  mov     eax, 0FFFCh
0x18007ef9d  mov     [rsp+150h+var_10C], ax
0x18007efa2  mov     r12d, r13d
0x18007efa5  movups  [rbp+50h+var_C8], xmm0
0x18007efa9  mov     [rsp+150h+hMem], r13
0x18007efae  mov     edi, 80004005h
0x18007efb3  movups  [rbp+50h+var_B8], xmm0
0x18007efb7  call    ?GetObjectMgr@CTxtEdit@@QEAAPEAVCObjectMgr@@XZ; CTxtEdit::GetObjectMgr(void)
0x18007efbc  xor     edx, edx; Val
0x18007efbe  mov     [rbp+50h+var_A0], rax
0x18007efc2  lea     r8d, [r13+48h]; Size
0x18007efc6  mov     [rsp+150h+var_E8], r13
0x18007efcb  lea     rcx, [rbp+50h+var_90]; void *
0x18007efcf  mov     [rsp+150h+var_100], r13
0x18007efd4  mov     rbx, rax
0x18007efd7  call    memset_0
0x18007efdc  xor     eax, eax
0x18007efde  mov     [rsp+150h+var_F8], r13
0x18007efe3  mov     [rbp+50h+var_D0], rax
0x18007efe7  xorps   xmm0, xmm0
0x18007efea  mov     r15d, r13d
0x18007efed  movups  xmmword ptr [rsp+150h+ho], xmm0
0x18007eff2  test    rbx, rbx
0x18007eff5  jz      loc_18007F145
0x18007effb  mov     r13, [rbx+20h]
0x18007efff  lea     r8d, [r15+1]
0x18007f003  mov     rdx, [rsi+278h]
0x18007f00a  lea     r9d, [r15+3]
0x18007f00e  mov     qword ptr [rbp+50h+var_C8+8], rax
0x18007f012  mov     dword ptr [rbp+50h+var_B8+8], eax
0x18007f015  lea     eax, [r15+2]
0x18007f019  mov     dword ptr [rbp+50h+var_B8], r8d
0x18007f01d  mov     dword ptr [rbp+50h+var_B8+4], 0FFFFFFFFh
0x18007f024  movsx   ecx, word ptr [rdx]
0x18007f027  mov     [rbp+50h+var_A8], r13
0x18007f02b  test    ecx, ecx
0x18007f02d  jz      short loc_18007F066
0x18007f02f  sub     ecx, r8d
0x18007f032  jz      short loc_18007F04A
0x18007f034  cmp     ecx, r8d
0x18007f037  jnz     short loc_18007F084
0x18007f039  lea     eax, [r15+8]
0x18007f03d  mov     dword ptr [rbp+50h+var_B8+8], r8d
0x18007f041  lea     r12, ?ObHBuildDib@@YAPEAXPEAU_rtfobject@@AEAPEAX@Z; ObHBuildDib(_rtfobject *,void * &)
0x18007f048  jmp     short loc_18007F074
0x18007f04a  movups  xmm0, xmmword ptr cs:CLSID_StaticMetafile.Data1
0x18007f051  mov     word ptr [rbp+50h+var_C8], r9w
0x18007f056  lea     r12, ?ObHBuildMetafilePict@@YAPEAXPEAU_rtfobject@@AEAPEAX@Z; ObHBuildMetafilePict(_rtfobject *,void * &)
0x18007f05d  mov     dword ptr [rbp+50h+var_B8+8], 20h ; ' '
0x18007f064  jmp     short loc_18007F07F
0x18007f066  mov     dword ptr [rbp+50h+var_B8+8], 10h
0x18007f06d  lea     r12, ?ObHBuildBitmap@@YAPEAXPEAU_rtfobject@@AEAPEAX@Z; ObHBuildBitmap(_rtfobject *,void * &)
0x18007f074  movups  xmm0, xmmword ptr cs:CLSID_StaticDib.Data1
0x18007f07b  mov     word ptr [rbp+50h+var_C8], ax
0x18007f07f  movdqu  xmmword ptr [rbp+50h+var_90.clsid.Data1], xmm0
0x18007f084  mov     ebx, [rdx+18h]
0x18007f087  movsx   ecx, word ptr [rdx+20h]; int
0x18007f08b  mov     edx, 7Fh; int
0x18007f090  lea     r8d, [rdx-37h]; int
0x18007f094  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x18007f099  mov     ecx, eax
0x18007f09b  mov     eax, 51EB851Fh
0x18007f0a0  imul    ecx, ebx
0x18007f0a3  mov     rbx, [rsi+278h]
0x18007f0aa  imul    ecx
0x18007f0ac  sar     edx, 5
0x18007f0af  mov     eax, edx
0x18007f0b1  shr     eax, 1Fh
0x18007f0b4  add     edx, eax
0x18007f0b6  mov     [rbp+50h+var_90.sizel.cx], edx
0x18007f0b9  mov     edx, 7Fh; int
0x18007f0be  movsx   ecx, word ptr [rbx+22h]; int
0x18007f0c2  lea     r8d, [rdx-37h]; int
0x18007f0c6  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x18007f0cb  mov     ecx, eax
0x18007f0cd  xorps   xmm0, xmm0
0x18007f0d0  imul    ecx, [rbx+1Ch]
0x18007f0d4  mov     eax, 51EB851Fh
0x18007f0d9  movdqu  xmmword ptr [rsp+150h+ho+8], xmm0
0x18007f0df  imul    ecx
0x18007f0e1  sar     edx, 5
0x18007f0e4  mov     eax, edx
0x18007f0e6  shr     eax, 1Fh
0x18007f0e9  add     edx, eax
0x18007f0eb  mov     eax, dword ptr [rbp+50h+var_B8+8]
0x18007f0ee  mov     [rbp+50h+var_90.sizel.cy], edx
0x18007f0f1  mov     dword ptr [rsp+150h+ho], eax
0x18007f0f5  test    r13, r13
0x18007f0f8  jz      loc_18007F2AF
0x18007f0fe  test    byte ptr [rsi+1D8h], 4
0x18007f105  jnz     loc_18007F22F
0x18007f10b  mov     rax, [r13+0]
0x18007f10f  lea     rdx, [rbp+50h+var_90.pstg]
0x18007f113  mov     rcx, r13
0x18007f116  mov     rax, [rax+18h]
0x18007f11a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f11f  xor     r13d, r13d
0x18007f122  mov     edi, eax
0x18007f124  test    eax, eax
0x18007f126  jz      loc_18007F232
0x18007f12c  mov     r12d, r13d
0x18007f12f  mov     rcx, [rsp+150h+var_100]
0x18007f134  test    rcx, rcx
0x18007f137  jz      short loc_18007F145
0x18007f139  mov     rax, [rcx]
0x18007f13c  mov     rax, [rax+10h]
0x18007f140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f145  mov     rcx, [rbp+50h+var_90.pstg]
0x18007f149  test    rcx, rcx
0x18007f14c  jz      short loc_18007F15A
0x18007f14e  mov     rax, [rcx]
0x18007f151  mov     rax, [rax+10h]
0x18007f155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f15a  mov     rdx, [rbp+50h+var_90.polesite]
0x18007f15e  test    rdx, rdx
0x18007f161  jz      short loc_18007F172
0x18007f163  mov     rax, [rdx]
0x18007f166  mov     rcx, rdx
0x18007f169  mov     rax, [rax+10h]
0x18007f16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f172  mov     rcx, [rbp+50h+var_90.poleobj]
0x18007f176  test    rcx, rcx
0x18007f179  jz      short loc_18007F187
0x18007f17b  mov     rax, [rcx]
0x18007f17e  mov     rax, [rax+10h]
0x18007f182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f187  mov     rcx, [rsp+150h+var_E8]
0x18007f18c  test    rcx, rcx
0x18007f18f  jz      short loc_18007F19D
0x18007f191  mov     rax, [rcx]
0x18007f194  mov     rax, [rax+10h]
0x18007f198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f19d  mov     rbx, [rsp+150h+var_F8]
0x18007f1a2  test    rbx, rbx
0x18007f1a5  jz      short loc_18007F1C1
0x18007f1a7  mov     rax, [rbx]
0x18007f1aa  mov     rcx, rbx
0x18007f1ad  mov     rax, [rax+10h]
0x18007f1b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f1b6  mov     rcx, r15; lpMem
0x18007f1b9  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x18007f1be  mov     r15, r13
0x18007f1c1  test    edi, edi
0x18007f1c3  jnz     short loc_18007F1CB
0x18007f1c5  cmp     [rsi+30h], r13d
0x18007f1c9  jz      short loc_18007F1EB
0x18007f1cb  test    r15, r15
0x18007f1ce  jz      short loc_18007F1E1
0x18007f1d0  mov     rcx, [rsp+150h+hMem]; hMem
0x18007f1d5  call    cs:__imp_GlobalUnlock
0x18007f1dc  nop     dword ptr [rax+rax+00h]
0x18007f1e1  mov     rcx, [rsp+150h+hMem]; void *
0x18007f1e6  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18007f1eb  mov     rcx, [rsp+150h+ho+8]; hMem
0x18007f1f0  test    rcx, rcx
0x18007f1f3  jz      loc_18007F70D
0x18007f1f9  mov     rax, [rsi+278h]
0x18007f200  movsx   edx, word ptr [rax]
0x18007f203  test    edx, edx
0x18007f205  jz      loc_18007F6FC
0x18007f20b  cmp     edx, 1
0x18007f20e  jnz     loc_18007F70D
0x18007f214  call    cs:__imp_GlobalUnlock
0x18007f21b  nop     dword ptr [rax+rax+00h]
0x18007f220  mov     rcx, [rsp+150h+ho+8]; void *
0x18007f225  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18007f22a  jmp     loc_18007F70D
0x18007f22f  xor     r13d, r13d
0x18007f232  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18007f237  lea     rbx, [rax+110h]
0x18007f23e  cmp     [rbx], r13
0x18007f241  jnz     short loc_18007F257
0x18007f243  lea     r8, aCreatestreamon; "CreateStreamOnHGlobal"
0x18007f24a  mov     edx, 1
0x18007f24f  mov     rcx, rbx
0x18007f252  call    SetProcAddr
0x18007f257  mov     rax, [rbx]
0x18007f25a  test    rax, rax
0x18007f25d  jz      short loc_18007F2A2
0x18007f25f  lea     r8, [rsp+150h+var_F8]
0x18007f264  xor     edx, edx
0x18007f266  xor     ecx, ecx
0x18007f268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f26d  mov     edi, eax
0x18007f26f  test    eax, eax
0x18007f271  jnz     short loc_18007F2A7
0x18007f273  mov     ebx, 400h
0x18007f278  mov     r14d, 4000h
0x18007f27e  xor     edx, edx; unsigned int
0x18007f280  mov     ecx, r14d; unsigned int
0x18007f283  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x18007f288  mov     r15, rax
0x18007f28b  test    rax, rax
0x18007f28e  jnz     short loc_18007F2F0
0x18007f290  sub     r14d, ebx
0x18007f293  cmp     r14d, ebx
0x18007f296  jge     short loc_18007F27E
0x18007f298  mov     r12d, [rsp+150h+var_110]
0x18007f29d  jmp     loc_18007F12F
0x18007f2a2  mov     edi, 80004005h
0x18007f2a7  mov     r12d, r15d
0x18007f2aa  jmp     loc_18007F12F
0x18007f2af  test    r14d, r14d
0x18007f2b2  jnz     short loc_18007F2BF
0x18007f2b4  mov     r12d, 1
0x18007f2ba  jmp     loc_18007F12F
0x18007f2bf  mov     rdx, r14; dwBytes
0x18007f2c2  xor     ecx, ecx; uFlags
0x18007f2c4  call    cs:__imp_GlobalAlloc
0x18007f2cb  nop     dword ptr [rax+rax+00h]
0x18007f2d0  mov     rcx, rax; hMem
0x18007f2d3  mov     [rsp+150h+hMem], rax
0x18007f2d8  call    cs:__imp_GlobalLock
0x18007f2df  nop     dword ptr [rax+rax+00h]
0x18007f2e4  mov     r15, rax
0x18007f2e7  test    rax, rax
0x18007f2ea  jz      loc_18007F12C
0x18007f2f0  lea     r13, [rsi+280h]
0x18007f2f7  lea     rbx, [rsi+30h]
0x18007f2fb  mov     rax, [r13+0]
0x18007f2ff  mov     r8d, r14d
0x18007f302  mov     rdx, r15
0x18007f305  mov     rcx, r13
0x18007f308  mov     rax, [rax]
0x18007f30b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f310  mov     r8d, eax
0x18007f313  test    eax, eax
0x18007f315  jle     short loc_18007F34A
0x18007f317  lea     rbx, [rsi+30h]
0x18007f31b  cmp     dword ptr [rbx], 0
0x18007f31e  jnz     short loc_18007F34A
0x18007f320  mov     rcx, [rsp+150h+var_F8]
0x18007f325  test    rcx, rcx
0x18007f328  jz      short loc_18007F2FB
0x18007f32a  mov     rax, [rcx]
0x18007f32d  xor     r9d, r9d
0x18007f330  mov     rdx, r15
0x18007f333  mov     rax, [rax+20h]
0x18007f337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f33c  mov     edi, eax
0x18007f33e  test    eax, eax
0x18007f340  jz      short loc_18007F2FB
0x18007f342  xor     r13d, r13d
0x18007f345  jmp     loc_18007F298
0x18007f34a  xor     r13d, r13d
0x18007f34d  cmp     [rbx], r13d
0x18007f350  jnz     loc_18007F12C
0x18007f356  mov     rcx, [rsp+150h+hMem]; hMem
0x18007f35b  test    rcx, rcx
0x18007f35e  jz      short loc_18007F36F
0x18007f360  call    cs:__imp_GlobalUnlock
0x18007f367  nop     dword ptr [rax+rax+00h]
0x18007f36c  mov     r15d, r13d
0x18007f36f  mov     rbx, [rsp+150h+var_F8]
0x18007f374  test    rbx, rbx
0x18007f377  jz      short loc_18007F3C1
0x18007f379  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18007f37e  lea     rdi, [rax+118h]
0x18007f385  cmp     [rdi], r13
0x18007f388  jnz     short loc_18007F39E
0x18007f38a  lea     r8, aGethglobalfrom; "GetHGlobalFromStream"
0x18007f391  mov     edx, 1
0x18007f396  mov     rcx, rdi
0x18007f399  call    SetProcAddr
0x18007f39e  mov     rax, [rdi]
0x18007f3a1  test    rax, rax
0x18007f3a4  jz      loc_18007F4A1
0x18007f3aa  lea     rdx, [rsp+150h+hMem]
0x18007f3af  mov     rcx, rbx
0x18007f3b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f3b7  mov     edi, eax
0x18007f3b9  test    eax, eax
0x18007f3bb  jnz     loc_18007F12C
0x18007f3c1  test    r12, r12
0x18007f3c4  jz      loc_18007F2B4
0x18007f3ca  mov     rcx, [rsi+278h]
0x18007f3d1  lea     rdx, [rsp+150h+hMem]
0x18007f3d6  mov     rax, r12
0x18007f3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f3de  mov     [rsp+150h+ho+8], rax
  ... truncated ...
```
