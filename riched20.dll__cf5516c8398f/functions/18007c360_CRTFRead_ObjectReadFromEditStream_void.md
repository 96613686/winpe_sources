# CRTFRead::ObjectReadFromEditStream(void)

- ea: `0x18007c360`
- end: `0x18007c89d`
- name: `?ObjectReadFromEditStream@CRTFRead@@AEAAHXZ`
- size: `1341`
- prototype: `__int64 __fastcall(CRTFRead *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800026c0`

## callees

- `0x180032db0`
- `0x180038bd0`
- `0x180041adc`
- `0x18005bb98`
- `0x18006fe60`
- `0x18007c360`
- `0x18007c8a4`
- `0x18008c118`
- `0x18008c1bc`
- `0x18008c8dc`
- `0x18008fef8`
- `0x180090508`
- `0x1800907ac`
- `0x18009110a`
- `0x180091140`
- `0x180092010`

## string_xrefs

- `0x18007c40b`: `CLSIDFromProgID`

## pseudocode

```c
__int64 __fastcall CRTFRead::ObjectReadFromEditStream(CRTFRead *this)
{
  CTxtEdit *v2; // rcx
  unsigned int v3; // r12d
  struct CObjectMgr *ObjectMgr; // r15
  __int64 v5; // rsi
  __int64 v6; // r14
  struct COLE32_PROC *Ole32Procs; // rax
  void (__fastcall **v8)(__int64, CLSID *); // rbx
  LPSTORAGE pstg; // rsi
  struct COLE32_PROC *v10; // rax
  _QWORD *v11; // rbx
  LPOLECLIENTSITE polesite; // rcx
  const struct _GUID *v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rbx
  int v16; // ecx
  __int64 v17; // rbx
  int v18; // eax
  DWORD dwFlags; // ecx
  unsigned int v20; // r8d
  struct IStorageVtbl *lpVtbl; // rax
  unsigned int v22; // r8d
  LPOLECLIENTSITE v23; // rax
  struct IOleObject *poleobj; // rcx
  CTxtRange *v25; // rcx
  struct IUndoBuilder *v26; // r9
  int v27; // eax
  int v29; // [rsp+28h] [rbp-D8h]
  struct IAdviseSink *v30; // [rsp+30h] [rbp-D0h]
  _BYTE v31[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v32; // [rsp+44h] [rbp-BCh] BYREF
  int v33; // [rsp+48h] [rbp-B8h] BYREF
  int v34[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h] BYREF
  struct tagSTGMEDIUM hMem; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v39[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v40; // [rsp+B8h] [rbp-48h]
  struct _reobject v41; // [rsp+C0h] [rbp-40h] BYREF
  CLSID v42; // [rsp+110h] [rbp+10h] BYREF

  v2 = (CTxtEdit *)*((_QWORD *)this + 7);
  v32 = -4;
  v3 = 0;
  v35 = 0;
  v36 = 0;
  ObjectMgr = CTxtEdit::GetObjectMgr(v2);
  memset_0(&v41, 0, sizeof(v41));
  v40 = 0;
  memset(v39, 0, sizeof(v39));
  if ( !ObjectMgr )
    goto LABEL_42;
  v5 = *((_QWORD *)ObjectMgr + 4);
  if ( !v5 )
    goto LABEL_42;
  v6 = *(_QWORD *)(*((_QWORD *)this + 79) + 56LL);
  if ( v6 )
  {
    Ole32Procs = CThreadData::GetOle32Procs();
    v8 = (void (__fastcall **)(__int64, CLSID *))((char *)Ole32Procs + 296);
    if ( !*((_QWORD *)Ole32Procs + 37) )
      SetProcAddr((char *)Ole32Procs + 296, 1, "CLSIDFromProgID");
    if ( *v8 )
      (*v8)(v6, &v41.clsid);
  }
  if ( (*(unsigned int (__fastcall **)(__int64, LPSTORAGE *))(*(_QWORD *)v5 + 24LL))(v5, &v41.pstg) )
    goto LABEL_42;
  pstg = v41.pstg;
  v10 = CThreadData::GetOle32Procs();
  v11 = (_QWORD *)((char *)v10 + 304);
  if ( !*((_QWORD *)v10 + 38) )
    SetProcAddr((char *)v10 + 304, 1, "OleConvertOLESTREAMToIStorage");
  if ( !*v11 || ((unsigned int (__fastcall *)(char *, LPSTORAGE, _QWORD))*v11)((char *)this + 640, pstg, 0) )
    goto LABEL_42;
  (*(void (__fastcall **)(__int64, LPOLECLIENTSITE *))(*(_QWORD *)(*((_QWORD *)this + 7) + 8LL) + 24LL))(
    *((_QWORD *)this + 7) + 8LL,
    &v41.polesite);
  polesite = v41.polesite;
  if ( !v41.polesite )
    goto LABEL_43;
  if ( (unsigned int)QueryRtfObj(*((struct CTxtEdit **)this + 7), v41.pstg)
    || (unsigned int)CW32System::OleLoad(v41.pstg, v13, v41.polesite, (void **)&v41.poleobj) )
  {
    goto LABEL_42;
  }
  v42 = 0;
  if ( !((unsigned int (__fastcall *)(LPOLEOBJECT, CLSID *))v41.poleobj->lpVtbl->GetUserClassID)(v41.poleobj, &v42) )
    v41.clsid = v42;
  v14 = *((_QWORD *)this + 8);
  v15 = *((_QWORD *)this + 79);
  v41.cbStruct = 72;
  v41.cp = *(_DWORD *)(v14 + 40);
  v16 = *(_DWORD *)(v15 + 24) * CW32System::MulDiv(*(_DWORD *)(v15 + 16), 127, 72);
  v17 = *((_QWORD *)this + 79);
  v41.sizel.cx = v16 / 100;
  v41.sizel.cy = (int)(*(_DWORD *)(v17 + 28) * CW32System::MulDiv(*(_DWORD *)(v17 + 20), 127, 72)) / 100;
  v18 = ObjectReadSiteFlags(&v41);
  dwFlags = v41.dwFlags;
  v41.dvaspect = 1;
  if ( v18 )
    dwFlags = 1;
  v41.dwFlags = dwFlags;
  if ( !((__int64 (__fastcall *)(LPOLEOBJECT, GUID *, __int64 *))v41.poleobj->lpVtbl->QueryInterface)(
          v41.poleobj,
          &IID_IOleCache,
          &v35)
    && !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v35 + 40LL))(v35, &v36) )
  {
    while ( !(*(unsigned int (__fastcall **)(__int64, __int64, _OWORD *, _QWORD))(*(_QWORD *)v36 + 24LL))(
               v36,
               1,
               v39,
               0) )
    {
      if ( LOWORD(v39[0]) == 3 )
      {
        *(_QWORD *)v34 = 0;
        v33 = 0;
        memset(&hMem, 0, sizeof(hMem));
        if ( !(**(unsigned int (__fastcall ***)(__int64, GUID *, int *))v35)(v35, &IID_IDataObject, v34)
          && !(*(unsigned int (__fastcall **)(_QWORD, _OWORD *, struct tagSTGMEDIUM *))(**(_QWORD **)v34 + 24LL))(
                *(_QWORD *)v34,
                v39,
                &hMem)
          && (unsigned int)FIsIconMetafilePict(hMem.hBitmap) )
        {
          OleStdSwitchDisplayAspect(v41.poleobj, &v41.dvaspect, v20, hMem.hBitmap, 1, v29, v30, &v33);
        }
        CW32System::ReleaseStgMedium(&hMem);
        if ( *(_QWORD *)v34 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v34 + 16LL))(*(_QWORD *)v34);
        break;
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
  if ( v41.dvaspect == 1 )
  {
    *(_QWORD *)v34 = 0;
    v31[0] = 0;
    lpVtbl = v41.pstg->lpVtbl;
    v33 = 0;
    if ( !((unsigned int (__fastcall *)(LPSTORAGE, __int64 *, _QWORD, __int64, _DWORD))lpVtbl->OpenStream)(
            v41.pstg,
            qword_180099CA8,
            0,
            16,
            0)
      && !(*(unsigned int (__fastcall **)(_QWORD, _BYTE *, __int64, _QWORD))(**(_QWORD **)v34 + 24LL))(
            *(_QWORD *)v34,
            v31,
            1,
            0)
      && (v31[0] & 0x40) != 0 )
    {
      v23 = v41.polesite;
      *((_WORD *)this + 236) |= 6u;
      poleobj = v41.poleobj;
      *((_QWORD *)this + 58) = v23;
      OleStdSwitchDisplayAspect(poleobj, &v41.dvaspect, v22, 0, 1, (int)v34, v30, &v33);
    }
    if ( *(_QWORD *)v34 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v34 + 16LL))(*(_QWORD *)v34);
  }
  v25 = (CTxtRange *)*((_QWORD *)this + 8);
  v41.dwFlags &= ~0x10u;
  CTxtRange::Set_iCF(v25, -1);
  (*(void (__fastcall **)(_QWORD, __int64, __int16 *, _QWORD, _DWORD, _QWORD, _DWORD))(**((_QWORD **)this + 8) + 560LL))(
    *((_QWORD *)this + 8),
    1,
    &v32,
    0,
    0,
    0,
    0);
  if ( (unsigned int)CObjectMgr::InsertObject(ObjectMgr, v41.cp, &v41, v26) )
  {
LABEL_42:
    polesite = v41.polesite;
  }
  else
  {
    v37 = 0;
    v27 = ((__int64 (__fastcall *)(LPOLEOBJECT, _QWORD, __int64 *))v41.poleobj->lpVtbl->GetExtent)(
            v41.poleobj,
            v41.dvaspect,
            &v37);
    polesite = v41.polesite;
    if ( v27 )
    {
      *((_WORD *)this + 236) |= 4u;
      *((_QWORD *)this + 58) = polesite;
    }
    v3 = 1;
  }
LABEL_43:
  if ( v41.pstg )
  {
    ((void (__fastcall *)(LPSTORAGE))v41.pstg->lpVtbl->Release)(v41.pstg);
    polesite = v41.polesite;
  }
  if ( polesite
    && ((int (__fastcall *)(LPOLECLIENTSITE))polesite->lpVtbl->Release)(polesite) <= 0
    && (LPOLECLIENTSITE)*((_QWORD *)this + 58) == v41.polesite )
  {
    *((_QWORD *)this + 58) = 0;
  }
  if ( v41.poleobj )
    ((void (__fastcall *)(LPOLEOBJECT))v41.poleobj->lpVtbl->Release)(v41.poleobj);
  return v3;
}

```

## disassembly

```asm
0x18007c360  push    rbp
0x18007c362  push    rbx
0x18007c363  push    rsi
0x18007c364  push    rdi
0x18007c365  push    r12
0x18007c367  push    r13
0x18007c369  push    r14
0x18007c36b  push    r15
0x18007c36d  lea     rbp, [rsp-38h]
0x18007c372  sub     rsp, 138h
0x18007c379  mov     rax, cs:__security_cookie
0x18007c380  xor     rax, rsp
0x18007c383  mov     [rbp+70h+var_50], rax
0x18007c387  mov     rdi, rcx
0x18007c38a  mov     eax, 0FFFCh
0x18007c38f  mov     rcx, [rcx+38h]; this
0x18007c393  xor     r13d, r13d
0x18007c396  mov     [rsp+170h+var_12C], ax
0x18007c39b  mov     r12d, r13d
0x18007c39e  call    ?GetObjectMgr@CTxtEdit@@QEAAPEAVCObjectMgr@@XZ; CTxtEdit::GetObjectMgr(void)
0x18007c3a3  xor     edx, edx; Val
0x18007c3a5  mov     [rsp+170h+var_118], r13
0x18007c3aa  lea     r8d, [r13+48h]; Size
0x18007c3ae  mov     [rsp+170h+var_110], r13
0x18007c3b3  lea     rcx, [rbp+70h+var_B0]; void *
0x18007c3b7  mov     r15, rax
0x18007c3ba  call    memset_0
0x18007c3bf  xorps   xmm0, xmm0
0x18007c3c2  xor     eax, eax
0x18007c3c4  mov     [rbp+70h+var_B8], rax
0x18007c3c8  movups  [rbp+70h+var_E8], xmm0
0x18007c3cc  movups  [rbp+70h+var_D8], xmm0
0x18007c3d0  movups  [rbp+70h+var_C8], xmm0
0x18007c3d4  test    r15, r15
0x18007c3d7  jz      loc_18007C81C
0x18007c3dd  mov     rsi, [r15+20h]
0x18007c3e1  test    rsi, rsi
0x18007c3e4  jz      loc_18007C81C
0x18007c3ea  mov     rax, [rdi+278h]
0x18007c3f1  mov     r14, [rax+38h]
0x18007c3f5  test    r14, r14
0x18007c3f8  jz      short loc_18007C432
0x18007c3fa  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18007c3ff  lea     rbx, [rax+128h]
0x18007c406  cmp     [rbx], r13
0x18007c409  jnz     short loc_18007C41E
0x18007c40b  lea     r8, aClsidfromprogi; "CLSIDFromProgID"
0x18007c412  mov     rcx, rbx
0x18007c415  lea     edx, [r13+1]
0x18007c419  call    SetProcAddr
0x18007c41e  mov     rax, [rbx]
0x18007c421  test    rax, rax
0x18007c424  jz      short loc_18007C432
0x18007c426  lea     rdx, [rbp+70h+var_B0.clsid]
0x18007c42a  mov     rcx, r14
0x18007c42d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c432  mov     rax, [rsi]
0x18007c435  lea     rdx, [rbp+70h+var_B0.pstg]
0x18007c439  mov     rcx, rsi
0x18007c43c  mov     rax, [rax+18h]
0x18007c440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c445  test    eax, eax
0x18007c447  jnz     loc_18007C81C
0x18007c44d  mov     rsi, [rbp+70h+var_B0.pstg]
0x18007c451  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18007c456  lea     rbx, [rax+130h]
0x18007c45d  cmp     [rbx], r13
0x18007c460  jnz     short loc_18007C476
0x18007c462  lea     r8, aOleconvertoles; "OleConvertOLESTREAMToIStorage"
0x18007c469  mov     edx, 1
0x18007c46e  mov     rcx, rbx
0x18007c471  call    SetProcAddr
0x18007c476  mov     rax, [rbx]
0x18007c479  test    rax, rax
0x18007c47c  jz      loc_18007C81C
0x18007c482  lea     rcx, [rdi+280h]
0x18007c489  xor     r8d, r8d
0x18007c48c  mov     rdx, rsi
0x18007c48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c494  test    eax, eax
0x18007c496  jnz     loc_18007C81C
0x18007c49c  mov     rcx, [rdi+38h]
0x18007c4a0  lea     rdx, [rbp+70h+var_B0.polesite]
0x18007c4a4  add     rcx, 8
0x18007c4a8  mov     rax, [rcx]
0x18007c4ab  mov     rax, [rax+18h]
0x18007c4af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c4b4  mov     rcx, [rbp+70h+var_B0.polesite]
0x18007c4b8  test    rcx, rcx
0x18007c4bb  jz      loc_18007C820
0x18007c4c1  mov     rdx, [rbp+70h+var_B0.pstg]; struct IStorage *
0x18007c4c5  mov     rcx, [rdi+38h]; struct CTxtEdit *
0x18007c4c9  call    ?QueryRtfObj@@YAJPEAVCTxtEdit@@PEAUIStorage@@@Z; QueryRtfObj(CTxtEdit *,IStorage *)
0x18007c4ce  test    eax, eax
0x18007c4d0  jnz     loc_18007C81C
0x18007c4d6  mov     r8, [rbp+70h+var_B0.polesite]; struct IOleClientSite *
0x18007c4da  lea     r9, [rbp+70h+var_B0.poleobj]; void **
0x18007c4de  mov     rcx, [rbp+70h+var_B0.pstg]; struct IStorage *
0x18007c4e2  call    ?OleLoad@CW32System@@SAJPEAUIStorage@@AEBU_GUID@@PEAUIOleClientSite@@PEAPEAX@Z; CW32System::OleLoad(IStorage *,_GUID const &,IOleClientSite *,void * *)
0x18007c4e7  test    eax, eax
0x18007c4e9  jnz     loc_18007C81C
0x18007c4ef  mov     rcx, [rbp+70h+var_B0.poleobj]
0x18007c4f3  lea     rdx, [rbp+70h+var_60]
0x18007c4f7  xorps   xmm0, xmm0
0x18007c4fa  movups  [rbp+70h+var_60], xmm0
0x18007c4fe  mov     rax, [rcx]
0x18007c501  mov     rax, [rax+78h]
0x18007c505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c50a  test    eax, eax
0x18007c50c  jnz     short loc_18007C517
0x18007c50e  movups  xmm0, [rbp+70h+var_60]
0x18007c512  movdqu  xmmword ptr [rbp+70h+var_B0.clsid.Data1], xmm0
0x18007c517  mov     rax, [rdi+40h]
0x18007c51b  mov     r8d, 48h ; 'H'; int
0x18007c521  mov     rbx, [rdi+278h]
0x18007c528  mov     [rbp+70h+var_B0.cbStruct], 48h ; 'H'
0x18007c52f  mov     ecx, [rax+28h]
0x18007c532  lea     r14d, [r8+37h]
0x18007c536  mov     [rbp+70h+var_B0.cp], ecx
0x18007c539  mov     edx, r14d; int
0x18007c53c  mov     ecx, [rbx+10h]; int
0x18007c53f  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x18007c544  mov     ecx, eax
0x18007c546  lea     r8d, [r14-37h]; int
0x18007c54a  imul    ecx, [rbx+18h]
0x18007c54e  mov     esi, 51EB851Fh
0x18007c553  mov     rbx, [rdi+278h]
0x18007c55a  mov     eax, esi
0x18007c55c  imul    ecx
0x18007c55e  sar     edx, 5
0x18007c561  mov     eax, edx
0x18007c563  shr     eax, 1Fh
0x18007c566  add     edx, eax
0x18007c568  mov     [rbp+70h+var_B0.sizel.cx], edx
0x18007c56b  mov     edx, r14d; int
0x18007c56e  mov     ecx, [rbx+14h]; int
0x18007c571  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x18007c576  mov     ecx, eax
0x18007c578  mov     eax, esi
0x18007c57a  imul    ecx, [rbx+1Ch]
0x18007c57e  imul    ecx
0x18007c580  lea     rcx, [rbp+70h+var_B0]; struct _reobject *
0x18007c584  sar     edx, 5
0x18007c587  mov     eax, edx
0x18007c589  shr     eax, 1Fh
0x18007c58c  add     edx, eax
0x18007c58e  mov     [rbp+70h+var_B0.sizel.cy], edx
0x18007c591  call    ?ObjectReadSiteFlags@@YAJPEAU_reobject@@@Z; ObjectReadSiteFlags(_reobject *)
0x18007c596  mov     ecx, [rbp+70h+var_B0.dwFlags]
0x18007c599  lea     ebx, [r14-7Eh]
0x18007c59d  test    eax, eax
0x18007c59f  mov     [rbp+70h+var_B0.dvaspect], ebx
0x18007c5a2  lea     r8, [rsp+170h+var_118]
0x18007c5a7  cmovnz  ecx, ebx
0x18007c5aa  lea     rdx, IID_IOleCache
0x18007c5b1  mov     [rbp+70h+var_B0.dwFlags], ecx
0x18007c5b4  mov     rcx, [rbp+70h+var_B0.poleobj]
0x18007c5b8  mov     rax, [rcx]
0x18007c5bb  mov     rax, [rax]
0x18007c5be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c5c3  test    eax, eax
0x18007c5c5  jnz     loc_18007C6D8
0x18007c5cb  mov     rcx, [rsp+170h+var_118]
0x18007c5d0  lea     rdx, [rsp+170h+var_110]
0x18007c5d5  mov     rax, [rcx]
0x18007c5d8  mov     rax, [rax+28h]
0x18007c5dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c5e1  test    eax, eax
0x18007c5e3  jnz     loc_18007C6D8
0x18007c5e9  mov     rcx, [rsp+170h+var_110]
0x18007c5ee  lea     r8, [rbp+70h+var_E8]
0x18007c5f2  xor     r9d, r9d
0x18007c5f5  mov     edx, ebx
0x18007c5f7  mov     rax, [rcx]
0x18007c5fa  mov     rax, [rax+18h]
0x18007c5fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c603  test    eax, eax
0x18007c605  jnz     loc_18007C6B6
0x18007c60b  cmp     word ptr [rbp+70h+var_E8], 3
0x18007c610  jnz     short loc_18007C5E9
0x18007c612  mov     rcx, [rsp+170h+var_118]
0x18007c617  lea     r8, [rsp+170h+var_120]
0x18007c61c  xor     eax, eax
0x18007c61e  mov     qword ptr [rsp+170h+var_120], r13
0x18007c623  mov     [rbp+70h+var_F0], rax
0x18007c627  lea     rdx, IID_IDataObject
0x18007c62e  xorps   xmm0, xmm0
0x18007c631  mov     [rsp+170h+var_128], r13d
0x18007c636  movups  xmmword ptr [rsp+170h+hMem], xmm0
0x18007c63b  mov     rax, [rcx]
0x18007c63e  mov     rax, [rax]
0x18007c641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c646  test    eax, eax
0x18007c648  jnz     short loc_18007C696
0x18007c64a  mov     rcx, qword ptr [rsp+170h+var_120]
0x18007c64f  lea     r8, [rsp+170h+hMem]
0x18007c654  lea     rdx, [rbp+70h+var_E8]
0x18007c658  mov     rax, [rcx]
0x18007c65b  mov     rax, [rax+18h]
0x18007c65f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c664  test    eax, eax
0x18007c666  jnz     short loc_18007C696
0x18007c668  mov     rcx, [rsp+170h+hMem+8]; hMem
0x18007c66d  call    ?FIsIconMetafilePict@@YAHPEAX@Z; FIsIconMetafilePict(void *)
0x18007c672  test    eax, eax
0x18007c674  jz      short loc_18007C696
0x18007c676  mov     r9, [rsp+170h+hMem+8]; void *
0x18007c67b  lea     rax, [rsp+170h+var_128]
0x18007c680  mov     rcx, [rbp+70h+var_B0.poleobj]; struct IOleObject *
0x18007c684  lea     rdx, [rbp+70h+var_B0.dvaspect]; unsigned int *
0x18007c688  mov     [rsp+170h+var_138], rax; int *
0x18007c68d  mov     [rsp+170h+var_150], ebx; int
0x18007c691  call    ?OleStdSwitchDisplayAspect@@YAJPEAUIOleObject@@PEAKKPEAXHHPEAUIAdviseSink@@PEAH@Z; OleStdSwitchDisplayAspect(IOleObject *,ulong *,ulong,void *,int,int,IAdviseSink *,int *)
0x18007c696  lea     rcx, [rsp+170h+hMem]; struct tagSTGMEDIUM *
0x18007c69b  call    ?ReleaseStgMedium@CW32System@@SAJPEAUtagSTGMEDIUM@@@Z; CW32System::ReleaseStgMedium(tagSTGMEDIUM *)
0x18007c6a0  mov     rcx, qword ptr [rsp+170h+var_120]
0x18007c6a5  test    rcx, rcx
0x18007c6a8  jz      short loc_18007C6B6
0x18007c6aa  mov     rax, [rcx]
0x18007c6ad  mov     rax, [rax+10h]
0x18007c6b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c6b6  mov     rcx, [rsp+170h+var_118]
0x18007c6bb  mov     rax, [rcx]
0x18007c6be  mov     rax, [rax+10h]
0x18007c6c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c6c7  mov     rcx, [rsp+170h+var_110]
0x18007c6cc  mov     rax, [rcx]
0x18007c6cf  mov     rax, [rax+10h]
0x18007c6d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c6d8  cmp     [rbp+70h+var_B0.dvaspect], ebx
0x18007c6db  jnz     loc_18007C791
0x18007c6e1  mov     rcx, [rbp+70h+var_B0.pstg]
0x18007c6e5  lea     rdx, [rsp+170h+var_120]
0x18007c6ea  mov     qword ptr [rsp+170h+var_148], rdx; int
0x18007c6ef  mov     r9d, 10h
0x18007c6f5  mov     qword ptr [rsp+170h+var_120], r13
0x18007c6fa  lea     rdx, qword_180099CA8
0x18007c701  mov     [rsp+170h+var_130], r13b
0x18007c706  xor     r8d, r8d
0x18007c709  mov     rax, [rcx]
0x18007c70c  mov     [rsp+170h+var_128], r13d
0x18007c711  mov     [rsp+170h+var_150], r13d
0x18007c716  mov     rax, [rax+20h]
0x18007c71a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c71f  test    eax, eax
0x18007c721  jnz     short loc_18007C77B
0x18007c723  mov     rcx, qword ptr [rsp+170h+var_120]
0x18007c728  lea     rdx, [rsp+170h+var_130]
0x18007c72d  xor     r9d, r9d
0x18007c730  mov     r8d, ebx
0x18007c733  mov     rax, [rcx]
0x18007c736  mov     rax, [rax+18h]
0x18007c73a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c73f  test    eax, eax
0x18007c741  jnz     short loc_18007C77B
0x18007c743  test    [rsp+170h+var_130], 40h
0x18007c748  jz      short loc_18007C77B
0x18007c74a  mov     rax, [rbp+70h+var_B0.polesite]
0x18007c74e  lea     rdx, [rbp+70h+var_B0.dvaspect]; unsigned int *
0x18007c752  or      word ptr [rdi+1D8h], 6
0x18007c75a  xor     r9d, r9d; void *
0x18007c75d  mov     rcx, [rbp+70h+var_B0.poleobj]; struct IOleObject *
0x18007c761  mov     [rdi+1D0h], rax
0x18007c768  lea     rax, [rsp+170h+var_128]
0x18007c76d  mov     [rsp+170h+var_138], rax; int *
0x18007c772  mov     [rsp+170h+var_150], ebx; int
0x18007c776  call    ?OleStdSwitchDisplayAspect@@YAJPEAUIOleObject@@PEAKKPEAXHHPEAUIAdviseSink@@PEAH@Z; OleStdSwitchDisplayAspect(IOleObject *,ulong *,ulong,void *,int,int,IAdviseSink *,int *)
0x18007c77b  mov     rcx, qword ptr [rsp+170h+var_120]
0x18007c780  test    rcx, rcx
0x18007c783  jz      short loc_18007C791
0x18007c785  mov     rax, [rcx]
0x18007c788  mov     rax, [rax+10h]
0x18007c78c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c791  mov     rcx, [rdi+40h]; this
0x18007c795  or      edx, 0FFFFFFFFh; int
0x18007c798  and     [rbp+70h+var_B0.dwFlags], 0FFFFFFEFh
0x18007c79c  call    ?Set_iCF@CTxtRange@@QEAAHJ@Z; CTxtRange::Set_iCF(long)
0x18007c7a1  mov     rcx, [rdi+40h]
0x18007c7a5  lea     r8, [rsp+170h+var_12C]
0x18007c7aa  mov     dword ptr [rsp+170h+var_140], r13d
0x18007c7af  xor     r9d, r9d
0x18007c7b2  mov     qword ptr [rsp+170h+var_148], r13
0x18007c7b7  mov     edx, ebx
0x18007c7b9  mov     [rsp+170h+var_150], r13d
0x18007c7be  mov     rax, [rcx]
0x18007c7c1  mov     rax, [rax+230h]
0x18007c7c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c7cd  mov     edx, [rbp+70h+var_B0.cp]; int
0x18007c7d0  lea     r8, [rbp+70h+var_B0]; struct _reobject *
0x18007c7d4  mov     rcx, r15; this
0x18007c7d7  call    ?InsertObject@CObjectMgr@@QEAAJJPEAU_reobject@@PEAVIUndoBuilder@@@Z; CObjectMgr::InsertObject(long,_reobject *,IUndoBuilder *)
0x18007c7dc  test    eax, eax
0x18007c7de  jnz     short loc_18007C81C
0x18007c7e0  mov     rcx, [rbp+70h+var_B0.poleobj]
0x18007c7e4  lea     r8, [rsp+170h+var_108]
0x18007c7e9  mov     edx, [rbp+70h+var_B0.dvaspect]
0x18007c7ec  mov     [rsp+170h+var_108], r13
0x18007c7f1  mov     rax, [rcx]
0x18007c7f4  mov     rax, [rax+90h]
0x18007c7fb  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
