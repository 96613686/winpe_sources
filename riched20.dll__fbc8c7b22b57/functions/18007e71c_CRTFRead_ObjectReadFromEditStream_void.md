# CRTFRead::ObjectReadFromEditStream(void)

- ea: `0x18007e71c`
- end: `0x18007ec5a`
- name: `?ObjectReadFromEditStream@CRTFRead@@AEAAHXZ`
- size: `1342`
- prototype: `__int64 __fastcall(CRTFRead *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002740`

## callees

- `0x18002da30`
- `0x180039990`
- `0x1800427ac`
- `0x18005d214`
- `0x180071cdc`
- `0x18007e71c`
- `0x18007ec60`
- `0x18008e7fc`
- `0x18008e8c0`
- `0x18008f020`
- `0x180092870`
- `0x180092ed0`
- `0x1800931b0`
- `0x180093bca`
- `0x180093c00`
- `0x180095010`

## string_xrefs

- `0x18007e7c7`: `CLSIDFromProgID`

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
      SetProcAddr((FARPROC *)Ole32Procs + 37, 1, "CLSIDFromProgID");
    if ( *v8 )
      (*v8)(v6, &v41.clsid);
  }
  if ( (*(unsigned int (__fastcall **)(__int64, LPSTORAGE *))(*(_QWORD *)v5 + 24LL))(v5, &v41.pstg) )
    goto LABEL_42;
  pstg = v41.pstg;
  v10 = CThreadData::GetOle32Procs();
  v11 = (_QWORD *)((char *)v10 + 304);
  if ( !*((_QWORD *)v10 + 38) )
    SetProcAddr((FARPROC *)v10 + 38, 1, "OleConvertOLESTREAMToIStorage");
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
            qword_18009CC90,
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
0x18007e71c  push    rbp
0x18007e71e  push    rbx
0x18007e71f  push    rsi
0x18007e720  push    rdi
0x18007e721  push    r12
0x18007e723  push    r13
0x18007e725  push    r14
0x18007e727  push    r15
0x18007e729  lea     rbp, [rsp-38h]
0x18007e72e  sub     rsp, 138h
0x18007e735  mov     rax, cs:__security_cookie
0x18007e73c  xor     rax, rsp
0x18007e73f  mov     [rbp+70h+var_50], rax
0x18007e743  mov     rdi, rcx
0x18007e746  mov     eax, 0FFFCh
0x18007e74b  mov     rcx, [rcx+38h]; this
0x18007e74f  xor     r13d, r13d
0x18007e752  mov     [rsp+170h+var_12C], ax
0x18007e757  mov     r12d, r13d
0x18007e75a  call    ?GetObjectMgr@CTxtEdit@@QEAAPEAVCObjectMgr@@XZ; CTxtEdit::GetObjectMgr(void)
0x18007e75f  xor     edx, edx; Val
0x18007e761  mov     [rsp+170h+var_118], r13
0x18007e766  lea     r8d, [r13+48h]; Size
0x18007e76a  mov     [rsp+170h+var_110], r13
0x18007e76f  lea     rcx, [rbp+70h+var_B0]; void *
0x18007e773  mov     r15, rax
0x18007e776  call    memset_0
0x18007e77b  xorps   xmm0, xmm0
0x18007e77e  xor     eax, eax
0x18007e780  mov     [rbp+70h+var_B8], rax
0x18007e784  movups  [rbp+70h+var_E8], xmm0
0x18007e788  movups  [rbp+70h+var_D8], xmm0
0x18007e78c  movups  [rbp+70h+var_C8], xmm0
0x18007e790  test    r15, r15
0x18007e793  jz      loc_18007EBD8
0x18007e799  mov     rsi, [r15+20h]
0x18007e79d  test    rsi, rsi
0x18007e7a0  jz      loc_18007EBD8
0x18007e7a6  mov     rax, [rdi+278h]
0x18007e7ad  mov     r14, [rax+38h]
0x18007e7b1  test    r14, r14
0x18007e7b4  jz      short loc_18007E7EE
0x18007e7b6  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18007e7bb  lea     rbx, [rax+128h]
0x18007e7c2  cmp     [rbx], r13
0x18007e7c5  jnz     short loc_18007E7DA
0x18007e7c7  lea     r8, aClsidfromprogi; "CLSIDFromProgID"
0x18007e7ce  mov     rcx, rbx
0x18007e7d1  lea     edx, [r13+1]
0x18007e7d5  call    SetProcAddr
0x18007e7da  mov     rax, [rbx]
0x18007e7dd  test    rax, rax
0x18007e7e0  jz      short loc_18007E7EE
0x18007e7e2  lea     rdx, [rbp+70h+var_B0.clsid]
0x18007e7e6  mov     rcx, r14
0x18007e7e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e7ee  mov     rax, [rsi]
0x18007e7f1  lea     rdx, [rbp+70h+var_B0.pstg]
0x18007e7f5  mov     rcx, rsi
0x18007e7f8  mov     rax, [rax+18h]
0x18007e7fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e801  test    eax, eax
0x18007e803  jnz     loc_18007EBD8
0x18007e809  mov     rsi, [rbp+70h+var_B0.pstg]
0x18007e80d  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18007e812  lea     rbx, [rax+130h]
0x18007e819  cmp     [rbx], r13
0x18007e81c  jnz     short loc_18007E832
0x18007e81e  lea     r8, aOleconvertoles; "OleConvertOLESTREAMToIStorage"
0x18007e825  mov     edx, 1
0x18007e82a  mov     rcx, rbx
0x18007e82d  call    SetProcAddr
0x18007e832  mov     rax, [rbx]
0x18007e835  test    rax, rax
0x18007e838  jz      loc_18007EBD8
0x18007e83e  lea     rcx, [rdi+280h]
0x18007e845  xor     r8d, r8d
0x18007e848  mov     rdx, rsi
0x18007e84b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e850  test    eax, eax
0x18007e852  jnz     loc_18007EBD8
0x18007e858  mov     rcx, [rdi+38h]
0x18007e85c  lea     rdx, [rbp+70h+var_B0.polesite]
0x18007e860  add     rcx, 8
0x18007e864  mov     rax, [rcx]
0x18007e867  mov     rax, [rax+18h]
0x18007e86b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e870  mov     rcx, [rbp+70h+var_B0.polesite]
0x18007e874  test    rcx, rcx
0x18007e877  jz      loc_18007EBDC
0x18007e87d  mov     rdx, [rbp+70h+var_B0.pstg]; struct IStorage *
0x18007e881  mov     rcx, [rdi+38h]; this
0x18007e885  call    ?QueryRtfObj@@YAJPEAVCTxtEdit@@PEAUIStorage@@@Z; QueryRtfObj(CTxtEdit *,IStorage *)
0x18007e88a  test    eax, eax
0x18007e88c  jnz     loc_18007EBD8
0x18007e892  mov     r8, [rbp+70h+var_B0.polesite]; struct IOleClientSite *
0x18007e896  lea     r9, [rbp+70h+var_B0.poleobj]; void **
0x18007e89a  mov     rcx, [rbp+70h+var_B0.pstg]; struct IStorage *
0x18007e89e  call    ?OleLoad@CW32System@@SAJPEAUIStorage@@AEBU_GUID@@PEAUIOleClientSite@@PEAPEAX@Z; CW32System::OleLoad(IStorage *,_GUID const &,IOleClientSite *,void * *)
0x18007e8a3  test    eax, eax
0x18007e8a5  jnz     loc_18007EBD8
0x18007e8ab  mov     rcx, [rbp+70h+var_B0.poleobj]
0x18007e8af  lea     rdx, [rbp+70h+var_60]
0x18007e8b3  xorps   xmm0, xmm0
0x18007e8b6  movups  [rbp+70h+var_60], xmm0
0x18007e8ba  mov     rax, [rcx]
0x18007e8bd  mov     rax, [rax+78h]
0x18007e8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e8c6  test    eax, eax
0x18007e8c8  jnz     short loc_18007E8D3
0x18007e8ca  movups  xmm0, [rbp+70h+var_60]
0x18007e8ce  movdqu  xmmword ptr [rbp+70h+var_B0.clsid.Data1], xmm0
0x18007e8d3  mov     rax, [rdi+40h]
0x18007e8d7  mov     r8d, 48h ; 'H'; int
0x18007e8dd  mov     rbx, [rdi+278h]
0x18007e8e4  mov     [rbp+70h+var_B0.cbStruct], 48h ; 'H'
0x18007e8eb  mov     ecx, [rax+28h]
0x18007e8ee  lea     r14d, [r8+37h]
0x18007e8f2  mov     [rbp+70h+var_B0.cp], ecx
0x18007e8f5  mov     edx, r14d; int
0x18007e8f8  mov     ecx, [rbx+10h]; int
0x18007e8fb  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x18007e900  mov     ecx, eax
0x18007e902  lea     r8d, [r14-37h]; int
0x18007e906  imul    ecx, [rbx+18h]
0x18007e90a  mov     esi, 51EB851Fh
0x18007e90f  mov     rbx, [rdi+278h]
0x18007e916  mov     eax, esi
0x18007e918  imul    ecx
0x18007e91a  sar     edx, 5
0x18007e91d  mov     eax, edx
0x18007e91f  shr     eax, 1Fh
0x18007e922  add     edx, eax
0x18007e924  mov     [rbp+70h+var_B0.sizel.cx], edx
0x18007e927  mov     edx, r14d; int
0x18007e92a  mov     ecx, [rbx+14h]; int
0x18007e92d  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x18007e932  mov     ecx, eax
0x18007e934  mov     eax, esi
0x18007e936  imul    ecx, [rbx+1Ch]
0x18007e93a  imul    ecx
0x18007e93c  lea     rcx, [rbp+70h+var_B0]; struct _reobject *
0x18007e940  sar     edx, 5
0x18007e943  mov     eax, edx
0x18007e945  shr     eax, 1Fh
0x18007e948  add     edx, eax
0x18007e94a  mov     [rbp+70h+var_B0.sizel.cy], edx
0x18007e94d  call    ?ObjectReadSiteFlags@@YAJPEAU_reobject@@@Z; ObjectReadSiteFlags(_reobject *)
0x18007e952  mov     ecx, [rbp+70h+var_B0.dwFlags]
0x18007e955  lea     ebx, [r14-7Eh]
0x18007e959  test    eax, eax
0x18007e95b  mov     [rbp+70h+var_B0.dvaspect], ebx
0x18007e95e  lea     r8, [rsp+170h+var_118]
0x18007e963  cmovnz  ecx, ebx
0x18007e966  lea     rdx, IID_IOleCache
0x18007e96d  mov     [rbp+70h+var_B0.dwFlags], ecx
0x18007e970  mov     rcx, [rbp+70h+var_B0.poleobj]
0x18007e974  mov     rax, [rcx]
0x18007e977  mov     rax, [rax]
0x18007e97a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e97f  test    eax, eax
0x18007e981  jnz     loc_18007EA94
0x18007e987  mov     rcx, [rsp+170h+var_118]
0x18007e98c  lea     rdx, [rsp+170h+var_110]
0x18007e991  mov     rax, [rcx]
0x18007e994  mov     rax, [rax+28h]
0x18007e998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e99d  test    eax, eax
0x18007e99f  jnz     loc_18007EA94
0x18007e9a5  mov     rcx, [rsp+170h+var_110]
0x18007e9aa  lea     r8, [rbp+70h+var_E8]
0x18007e9ae  xor     r9d, r9d
0x18007e9b1  mov     edx, ebx
0x18007e9b3  mov     rax, [rcx]
0x18007e9b6  mov     rax, [rax+18h]
0x18007e9ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e9bf  test    eax, eax
0x18007e9c1  jnz     loc_18007EA72
0x18007e9c7  cmp     word ptr [rbp+70h+var_E8], 3
0x18007e9cc  jnz     short loc_18007E9A5
0x18007e9ce  mov     rcx, [rsp+170h+var_118]
0x18007e9d3  lea     r8, [rsp+170h+var_120]
0x18007e9d8  xor     eax, eax
0x18007e9da  mov     qword ptr [rsp+170h+var_120], r13
0x18007e9df  mov     [rbp+70h+var_F0], rax
0x18007e9e3  lea     rdx, IID_IDataObject
0x18007e9ea  xorps   xmm0, xmm0
0x18007e9ed  mov     [rsp+170h+var_128], r13d
0x18007e9f2  movups  xmmword ptr [rsp+170h+hMem], xmm0
0x18007e9f7  mov     rax, [rcx]
0x18007e9fa  mov     rax, [rax]
0x18007e9fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ea02  test    eax, eax
0x18007ea04  jnz     short loc_18007EA52
0x18007ea06  mov     rcx, qword ptr [rsp+170h+var_120]
0x18007ea0b  lea     r8, [rsp+170h+hMem]
0x18007ea10  lea     rdx, [rbp+70h+var_E8]
0x18007ea14  mov     rax, [rcx]
0x18007ea17  mov     rax, [rax+18h]
0x18007ea1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ea20  test    eax, eax
0x18007ea22  jnz     short loc_18007EA52
0x18007ea24  mov     rcx, [rsp+170h+hMem+8]; hMem
0x18007ea29  call    ?FIsIconMetafilePict@@YAHPEAX@Z; FIsIconMetafilePict(void *)
0x18007ea2e  test    eax, eax
0x18007ea30  jz      short loc_18007EA52
0x18007ea32  mov     r9, [rsp+170h+hMem+8]; void *
0x18007ea37  lea     rax, [rsp+170h+var_128]
0x18007ea3c  mov     rcx, [rbp+70h+var_B0.poleobj]; struct IOleObject *
0x18007ea40  lea     rdx, [rbp+70h+var_B0.dvaspect]; unsigned int *
0x18007ea44  mov     [rsp+170h+var_138], rax; int *
0x18007ea49  mov     [rsp+170h+var_150], ebx; int
0x18007ea4d  call    ?OleStdSwitchDisplayAspect@@YAJPEAUIOleObject@@PEAKKPEAXHHPEAUIAdviseSink@@PEAH@Z; OleStdSwitchDisplayAspect(IOleObject *,ulong *,ulong,void *,int,int,IAdviseSink *,int *)
0x18007ea52  lea     rcx, [rsp+170h+hMem]; struct tagSTGMEDIUM *
0x18007ea57  call    ?ReleaseStgMedium@CW32System@@SAJPEAUtagSTGMEDIUM@@@Z; CW32System::ReleaseStgMedium(tagSTGMEDIUM *)
0x18007ea5c  mov     rcx, qword ptr [rsp+170h+var_120]
0x18007ea61  test    rcx, rcx
0x18007ea64  jz      short loc_18007EA72
0x18007ea66  mov     rax, [rcx]
0x18007ea69  mov     rax, [rax+10h]
0x18007ea6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ea72  mov     rcx, [rsp+170h+var_118]
0x18007ea77  mov     rax, [rcx]
0x18007ea7a  mov     rax, [rax+10h]
0x18007ea7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ea83  mov     rcx, [rsp+170h+var_110]
0x18007ea88  mov     rax, [rcx]
0x18007ea8b  mov     rax, [rax+10h]
0x18007ea8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ea94  cmp     [rbp+70h+var_B0.dvaspect], ebx
0x18007ea97  jnz     loc_18007EB4D
0x18007ea9d  mov     rcx, [rbp+70h+var_B0.pstg]
0x18007eaa1  lea     rdx, [rsp+170h+var_120]
0x18007eaa6  mov     qword ptr [rsp+170h+var_148], rdx; int
0x18007eaab  mov     r9d, 10h
0x18007eab1  mov     qword ptr [rsp+170h+var_120], r13
0x18007eab6  lea     rdx, qword_18009CC90
0x18007eabd  mov     [rsp+170h+var_130], r13b
0x18007eac2  xor     r8d, r8d
0x18007eac5  mov     rax, [rcx]
0x18007eac8  mov     [rsp+170h+var_128], r13d
0x18007eacd  mov     [rsp+170h+var_150], r13d
0x18007ead2  mov     rax, [rax+20h]
0x18007ead6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eadb  test    eax, eax
0x18007eadd  jnz     short loc_18007EB37
0x18007eadf  mov     rcx, qword ptr [rsp+170h+var_120]
0x18007eae4  lea     rdx, [rsp+170h+var_130]
0x18007eae9  xor     r9d, r9d
0x18007eaec  mov     r8d, ebx
0x18007eaef  mov     rax, [rcx]
0x18007eaf2  mov     rax, [rax+18h]
0x18007eaf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eafb  test    eax, eax
0x18007eafd  jnz     short loc_18007EB37
0x18007eaff  test    [rsp+170h+var_130], 40h
0x18007eb04  jz      short loc_18007EB37
0x18007eb06  mov     rax, [rbp+70h+var_B0.polesite]
0x18007eb0a  lea     rdx, [rbp+70h+var_B0.dvaspect]; unsigned int *
0x18007eb0e  or      word ptr [rdi+1D8h], 6
0x18007eb16  xor     r9d, r9d; void *
0x18007eb19  mov     rcx, [rbp+70h+var_B0.poleobj]; struct IOleObject *
0x18007eb1d  mov     [rdi+1D0h], rax
0x18007eb24  lea     rax, [rsp+170h+var_128]
0x18007eb29  mov     [rsp+170h+var_138], rax; int *
0x18007eb2e  mov     [rsp+170h+var_150], ebx; int
0x18007eb32  call    ?OleStdSwitchDisplayAspect@@YAJPEAUIOleObject@@PEAKKPEAXHHPEAUIAdviseSink@@PEAH@Z; OleStdSwitchDisplayAspect(IOleObject *,ulong *,ulong,void *,int,int,IAdviseSink *,int *)
0x18007eb37  mov     rcx, qword ptr [rsp+170h+var_120]
0x18007eb3c  test    rcx, rcx
0x18007eb3f  jz      short loc_18007EB4D
0x18007eb41  mov     rax, [rcx]
0x18007eb44  mov     rax, [rax+10h]
0x18007eb48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb4d  mov     rcx, [rdi+40h]; this
0x18007eb51  or      edx, 0FFFFFFFFh; int
0x18007eb54  and     [rbp+70h+var_B0.dwFlags], 0FFFFFFEFh
0x18007eb58  call    ?Set_iCF@CTxtRange@@QEAAHJ@Z; CTxtRange::Set_iCF(long)
0x18007eb5d  mov     rcx, [rdi+40h]
0x18007eb61  lea     r8, [rsp+170h+var_12C]
0x18007eb66  mov     dword ptr [rsp+170h+var_140], r13d
0x18007eb6b  xor     r9d, r9d
0x18007eb6e  mov     qword ptr [rsp+170h+var_148], r13
0x18007eb73  mov     edx, ebx
0x18007eb75  mov     [rsp+170h+var_150], r13d
0x18007eb7a  mov     rax, [rcx]
0x18007eb7d  mov     rax, [rax+230h]
0x18007eb84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb89  mov     edx, [rbp+70h+var_B0.cp]; int
0x18007eb8c  lea     r8, [rbp+70h+var_B0]; struct _reobject *
0x18007eb90  mov     rcx, r15; this
0x18007eb93  call    ?InsertObject@CObjectMgr@@QEAAJJPEAU_reobject@@PEAVIUndoBuilder@@@Z; CObjectMgr::InsertObject(long,_reobject *,IUndoBuilder *)
0x18007eb98  test    eax, eax
0x18007eb9a  jnz     short loc_18007EBD8
0x18007eb9c  mov     rcx, [rbp+70h+var_B0.poleobj]
0x18007eba0  lea     r8, [rsp+170h+var_108]
0x18007eba5  mov     edx, [rbp+70h+var_B0.dvaspect]
0x18007eba8  mov     [rsp+170h+var_108], r13
0x18007ebad  mov     rax, [rcx]
0x18007ebb0  mov     rax, [rax+90h]
0x18007ebb7  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
