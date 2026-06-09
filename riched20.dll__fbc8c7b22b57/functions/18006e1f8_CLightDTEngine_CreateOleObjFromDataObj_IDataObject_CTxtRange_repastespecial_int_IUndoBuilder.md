# CLightDTEngine::CreateOleObjFromDataObj(IDataObject *,CTxtRange *,_repastespecial *,int,IUndoBuilder *)

- ea: `0x18006e1f8`
- end: `0x18006e5f4`
- name: `?CreateOleObjFromDataObj@CLightDTEngine@@QEAAJPEAUIDataObject@@PEAVCTxtRange@@PEAU_repastespecial@@HPEAVIUndoBuilder@@@Z`
- size: `1020`
- prototype: `int(CLightDTEngine *__hidden this, struct IDataObject *, struct CTxtRange *, struct _repastespecial *, int, struct IUndoBuilder *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18006e9a8`

## callees

- `0x18004c6f0`
- `0x1800559d8`
- `0x18006e1f8`
- `0x18008e8c0`
- `0x18008f020`
- `0x18009253c`
- `0x1800925d4`
- `0x180092670`
- `0x180092ed0`
- `0x180093bca`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x18006e33a`
- `KERNEL32!GlobalLock` at `0x18006e33a`
- `KERNEL32!GlobalUnlock` at `0x18006e355`
- `KERNEL32!GlobalUnlock` at `0x18006e355`

## pseudocode

```c
__int64 __fastcall CLightDTEngine::CreateOleObjFromDataObj(
        CTxtEdit **this,
        struct IDataObject *a2,
        struct CTxtRange *a3,
        struct _repastespecial *a4,
        int a5,
        struct IUndoBuilder *a6)
{
  CTxtEdit *v9; // rcx
  struct IRichEditOleCallback *RECallback; // r8
  void *dwParam; // r12
  unsigned int dwAspect; // edi
  struct IDataObjectVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetData)(IDataObject *, FORMATETC *, STGMEDIUM *); // rax
  HBITMAP hBitmap; // rbx
  _DWORD *v17; // rax
  GUID v18; // xmm0
  unsigned int v19; // ebx
  unsigned int v20; // eax
  __int64 v21; // r8
  LPOLECLIENTSITE polesite; // rcx
  unsigned int v23; // eax
  unsigned int v24; // r8d
  int v25; // eax
  DWORD dwFlags; // ecx
  struct CTxtRange *v27; // rbx
  struct IOleClientSite *v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+28h] [rbp-D8h]
  struct IAdviseSink *v30; // [rsp+30h] [rbp-D0h]
  unsigned int v31; // [rsp+40h] [rbp-C0h] BYREF
  int v32[2]; // [rsp+48h] [rbp-B8h] BYREF
  SIZEL v33; // [rsp+50h] [rbp-B0h] BYREF
  struct tagFORMATETC v34; // [rsp+58h] [rbp-A8h] BYREF
  struct IUndoBuilder *v35; // [rsp+78h] [rbp-88h]
  struct CTxtRange *v36; // [rsp+80h] [rbp-80h]
  __int128 v37; // [rsp+88h] [rbp-78h] BYREF
  __int128 v38; // [rsp+98h] [rbp-68h]
  struct tagSTGMEDIUM hMem; // [rsp+A8h] [rbp-58h] BYREF
  struct _reobject v40; // [rsp+C0h] [rbp-40h] BYREF

  v35 = a6;
  v36 = a3;
  if ( !a2 || !a3 )
    return 2147500037LL;
  memset_0(&v40, 0, sizeof(v40));
  v9 = *this;
  v37 = 0;
  v33 = 0;
  v38 = 0;
  RECallback = CTxtEdit::GetRECallback(v9);
  *(_QWORD *)v32 = RECallback;
  memset(&v34, 0, sizeof(v34));
  if ( !RECallback )
    return 2147500034LL;
  dwParam = 0;
  memset(&hMem, 0, sizeof(hMem));
  dwAspect = (unsigned int)(a5 - 7) <= 2;
  if ( a5 == 13 )
    dwAspect = 4;
  v31 = dwAspect;
  if ( a4 )
  {
    if ( dwAspect )
      goto LABEL_18;
    dwAspect = a4->dwAspect;
    v31 = dwAspect;
    if ( dwAspect == 4 )
      dwParam = (void *)a4->dwParam;
  }
  if ( !dwAspect )
  {
    LOWORD(v37) = xmmword_1800A6270;
    lpVtbl = a2->lpVtbl;
    LODWORD(v38) = 1;
    *((_QWORD *)&v37 + 1) = 0;
    GetData = lpVtbl->GetData;
    *(_QWORD *)((char *)&v38 + 4) = 0x1FFFFFFFFLL;
    if ( ((unsigned int (__fastcall *)(struct IDataObject *, __int128 *, struct tagSTGMEDIUM *))GetData)(
           a2,
           &v37,
           &hMem) )
    {
      goto LABEL_16;
    }
    hBitmap = hMem.hBitmap;
    v17 = GlobalLock(hMem.hBitmap);
    if ( v17 )
    {
      dwAspect = v17[5];
      v31 = dwAspect;
    }
    GlobalUnlock(hBitmap);
    CW32System::ReleaseStgMedium(&hMem);
    if ( !dwAspect )
    {
LABEL_16:
      dwAspect = 1;
      v31 = 1;
    }
    RECallback = *(struct IRichEditOleCallback **)v32;
  }
LABEL_18:
  if ( (unsigned int)(a5 - 7) <= 2 )
  {
    if ( a5 == 7 )
      v18 = CLSID_StaticMetafile;
    else
      v18 = CLSID_StaticDib;
    v40.clsid = v18;
  }
  v19 = ((__int64 (__fastcall *)(struct IRichEditOleCallback *, LPSTORAGE *))RECallback->lpVtbl->GetNewStorage)(
          RECallback,
          &v40.pstg);
  if ( v19 )
    goto LABEL_42;
  v20 = (*(__int64 (__fastcall **)(__int64, LPOLECLIENTSITE *))(*((_QWORD *)*this + 1) + 24LL))(
          (__int64)*this + 8,
          &v40.polesite);
  polesite = v40.polesite;
  v19 = v20;
  if ( v40.polesite )
  {
    *(_QWORD *)&v34.cfFormat = 0;
    *(_QWORD *)&v34.tymed = 0;
    v34.ptd = 0;
    v34.dwAspect = dwAspect;
    v34.lindex = -1;
    if ( (unsigned int)(a5 - 7) > 2 )
    {
      if ( a5 == 6 || (*((_DWORD *)*this + 45) & 0x80000) != 0 && a5 == 13 )
        v23 = CW32System::OleCreateLinkFromData(a2, 0, v21, &v34, v28, v40.pstg, (void **)&v40.poleobj);
      else
        v23 = CW32System::OleCreateFromData(a2, 0, v21, &v34, v28, v40.pstg, (void **)&v40.poleobj);
    }
    else
    {
      v23 = CW32System::OleCreateStaticFromData(a2, 0, v21, &v34, v28, v40.pstg, (void **)&v40.poleobj);
    }
    v19 = v23;
    if ( !v23
      && ((unsigned int)(a5 - 7) <= 2
       || (v19 = ((__int64 (__fastcall *)(LPOLEOBJECT, CLSID *))v40.poleobj->lpVtbl->GetUserClassID)(
                   v40.poleobj,
                   &v40.clsid)) == 0) )
    {
      if ( !dwParam
        || (v32[0] = 0, (v19 = OleStdSwitchDisplayAspect(v40.poleobj, &v31, v24, dwParam, 0, v29, v30, v32)) == 0)
        && (dwAspect = v31,
            (v19 = ((__int64 (__fastcall *)(LPOLEOBJECT, _QWORD, SIZEL *))v40.poleobj->lpVtbl->GetExtent)(
                     v40.poleobj,
                     v31,
                     &v33)) == 0) )
      {
        v25 = ObjectReadSiteFlags(&v40);
        dwFlags = v40.dwFlags;
        v27 = v36;
        if ( v25 )
          dwFlags = 1;
        v40.dwFlags = dwFlags;
        CTxtRange::Delete(v36, v35, 1);
        v40.cp = *((_DWORD *)v27 + 10);
        v40.sizel = v33;
        v40.cbStruct = 72;
        v40.dvaspect = dwAspect;
        v19 = ((__int64 (__fastcall *)(LPOLEOBJECT, LPOLECLIENTSITE))v40.poleobj->lpVtbl->SetClientSite)(
                v40.poleobj,
                v40.polesite);
        if ( !v19 )
          v19 = (*(__int64 (__fastcall **)(__int64, struct _reobject *))(*((_QWORD *)*this + 1) + 56LL))(
                  (__int64)*this + 8,
                  &v40);
      }
    }
LABEL_42:
    polesite = v40.polesite;
  }
  if ( v40.poleobj )
  {
    ((void (__fastcall *)(LPOLEOBJECT))v40.poleobj->lpVtbl->Release)(v40.poleobj);
    polesite = v40.polesite;
  }
  if ( polesite )
    ((void (__fastcall *)(LPOLECLIENTSITE))polesite->lpVtbl->Release)(polesite);
  if ( v40.pstg )
    ((void (__fastcall *)(LPSTORAGE))v40.pstg->lpVtbl->Release)(v40.pstg);
  return v19;
}

```

## disassembly

```asm
0x18006e1f8  push    rbp
0x18006e1fa  push    rbx
0x18006e1fb  push    rsi
0x18006e1fc  push    rdi
0x18006e1fd  push    r12
0x18006e1ff  push    r13
0x18006e201  push    r14
0x18006e203  push    r15
0x18006e205  lea     rbp, [rsp-28h]
0x18006e20a  sub     rsp, 128h
0x18006e211  mov     rax, cs:__security_cookie
0x18006e218  xor     rax, rsp
0x18006e21b  mov     [rbp+60h+var_50], rax
0x18006e21f  mov     r13, rcx
0x18006e222  mov     rcx, [rbp+60h+arg_28]
0x18006e229  mov     [rsp+160h+var_E8], rcx
0x18006e22e  mov     rax, r8
0x18006e231  mov     [rbp+60h+var_E0], rax
0x18006e235  mov     rbx, r9
0x18006e238  mov     rsi, rdx
0x18006e23b  test    rdx, rdx
0x18006e23e  jz      loc_18006E5CE
0x18006e244  test    rax, rax
0x18006e247  jz      loc_18006E5CE
0x18006e24d  xor     edx, edx; Val
0x18006e24f  lea     rcx, [rbp+60h+var_A0]; void *
0x18006e253  lea     r8d, [rdx+48h]; Size
0x18006e257  call    memset_0
0x18006e25c  mov     rcx, [r13+0]; this
0x18006e260  xorps   xmm0, xmm0
0x18006e263  movups  [rbp+60h+var_D8], xmm0
0x18006e267  mov     [rsp+160h+var_110], 0
0x18006e270  xor     edi, edi
0x18006e272  movups  [rbp+60h+var_C8], xmm0
0x18006e276  call    ?GetRECallback@CTxtEdit@@QEAAPEAUIRichEditOleCallback@@XZ; CTxtEdit::GetRECallback(void)
0x18006e27b  mov     r14d, [rbp+60h+arg_20]
0x18006e282  xor     r15d, r15d
0x18006e285  mov     r8, rax
0x18006e288  mov     qword ptr [rsp+160h+var_118], rax
0x18006e28d  movups  xmmword ptr [rsp+160h+var_108.cfFormat], xmm0
0x18006e292  lea     ecx, [r14-7]
0x18006e296  cmp     ecx, 2
0x18006e299  movups  xmmword ptr [rsp+160h+var_108.dwAspect], xmm0
0x18006e29e  setbe   r15b
0x18006e2a2  test    rax, rax
0x18006e2a5  jnz     short loc_18006E2B1
0x18006e2a7  mov     eax, 80004002h
0x18006e2ac  jmp     loc_18006E5D3
0x18006e2b1  xor     eax, eax
0x18006e2b3  xor     r12d, r12d
0x18006e2b6  test    r15d, r15d
0x18006e2b9  mov     [rbp+60h+var_A8], rax
0x18006e2bd  movups  xmmword ptr [rbp+60h+hMem], xmm0
0x18006e2c1  lea     ecx, [rax+1]
0x18006e2c4  cmovnz  edi, ecx
0x18006e2c7  lea     eax, [rcx+3]
0x18006e2ca  cmp     r14d, 0Dh
0x18006e2ce  cmovz   edi, eax
0x18006e2d1  mov     [rsp+160h+var_120], edi
0x18006e2d5  test    rbx, rbx
0x18006e2d8  jz      short loc_18006E2F0
0x18006e2da  test    edi, edi
0x18006e2dc  jnz     loc_18006E37C
0x18006e2e2  mov     edi, [rbx]
0x18006e2e4  mov     [rsp+160h+var_120], edi
0x18006e2e8  cmp     edi, eax
0x18006e2ea  jnz     short loc_18006E2F0
0x18006e2ec  mov     r12, [rbx+4]
0x18006e2f0  test    edi, edi
0x18006e2f2  jnz     loc_18006E37C
0x18006e2f8  movzx   eax, word ptr cs:xmmword_1800A6270
0x18006e2ff  lea     r8, [rbp+60h+hMem]
0x18006e303  mov     word ptr [rbp+60h+var_D8], ax
0x18006e307  lea     rdx, [rbp+60h+var_D8]
0x18006e30b  mov     rax, [rsi]
0x18006e30e  mov     dword ptr [rbp+60h+var_C8], ecx
0x18006e311  mov     dword ptr [rbp+60h+var_C8+8], ecx
0x18006e314  mov     rcx, rsi
0x18006e317  mov     qword ptr [rbp+60h+var_D8+8], 0
0x18006e31f  mov     rax, [rax+18h]
0x18006e323  mov     dword ptr [rbp+60h+var_C8+4], 0FFFFFFFFh
0x18006e32a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e32f  test    eax, eax
0x18006e331  jnz     short loc_18006E36E
0x18006e333  mov     rbx, [rbp+60h+hMem+8]
0x18006e337  mov     rcx, rbx; hMem
0x18006e33a  call    cs:__imp_GlobalLock
0x18006e341  nop     dword ptr [rax+rax+00h]
0x18006e346  test    rax, rax
0x18006e349  jz      short loc_18006E352
0x18006e34b  mov     edi, [rax+14h]
0x18006e34e  mov     [rsp+160h+var_120], edi
0x18006e352  mov     rcx, rbx; hMem
0x18006e355  call    cs:__imp_GlobalUnlock
0x18006e35c  nop     dword ptr [rax+rax+00h]
0x18006e361  lea     rcx, [rbp+60h+hMem]; struct tagSTGMEDIUM *
0x18006e365  call    ?ReleaseStgMedium@CW32System@@SAJPEAUtagSTGMEDIUM@@@Z; CW32System::ReleaseStgMedium(tagSTGMEDIUM *)
0x18006e36a  test    edi, edi
0x18006e36c  jnz     short loc_18006E377
0x18006e36e  mov     edi, 1
0x18006e373  mov     [rsp+160h+var_120], edi
0x18006e377  mov     r8, qword ptr [rsp+160h+var_118]
0x18006e37c  test    r15d, r15d
0x18006e37f  jz      short loc_18006E39C
0x18006e381  cmp     r14d, 7
0x18006e385  jnz     short loc_18006E390
0x18006e387  movups  xmm0, xmmword ptr cs:CLSID_StaticMetafile.Data1
0x18006e38e  jmp     short loc_18006E397
0x18006e390  movups  xmm0, xmmword ptr cs:CLSID_StaticDib.Data1
0x18006e397  movdqu  xmmword ptr [rbp+60h+var_A0.clsid.Data1], xmm0
0x18006e39c  mov     rax, [r8]
0x18006e39f  lea     rdx, [rbp+60h+var_A0.pstg]
0x18006e3a3  mov     rcx, r8
0x18006e3a6  mov     rax, [rax+18h]
0x18006e3aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e3af  mov     ebx, eax
0x18006e3b1  test    eax, eax
0x18006e3b3  jnz     loc_18006E584
0x18006e3b9  mov     rcx, [r13+0]
0x18006e3bd  lea     rdx, [rbp+60h+var_A0.polesite]
0x18006e3c1  add     rcx, 8
0x18006e3c5  mov     rax, [rcx]
0x18006e3c8  mov     rax, [rax+18h]
0x18006e3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e3d1  mov     rcx, [rbp+60h+var_A0.polesite]
0x18006e3d5  xor     edx, edx; struct _GUID *
0x18006e3d7  mov     ebx, eax
0x18006e3d9  test    rcx, rcx
0x18006e3dc  jz      loc_18006E588
0x18006e3e2  mov     qword ptr [rsp+160h+var_108.cfFormat], rdx
0x18006e3e7  mov     qword ptr [rsp+160h+var_108.tymed], rdx
0x18006e3ec  mov     [rsp+160h+var_108.ptd], rdx
0x18006e3f1  mov     [rsp+160h+var_108.dwAspect], edi
0x18006e3f5  mov     [rsp+160h+var_108.lindex], 0FFFFFFFFh
0x18006e3fd  test    r15d, r15d
0x18006e400  jz      short loc_18006E423
0x18006e402  lea     rax, [rbp+60h+var_A0.poleobj]
0x18006e406  mov     rcx, rsi; struct IDataObject *
0x18006e409  mov     [rsp+160h+var_130], rax; void **
0x18006e40e  lea     r9, [rsp+160h+var_108]; struct tagFORMATETC *
0x18006e413  mov     rax, [rbp+60h+var_A0.pstg]
0x18006e417  mov     [rsp+160h+var_138], rax; struct IStorage *
0x18006e41c  call    ?OleCreateStaticFromData@CW32System@@SAJPEAUIDataObject@@AEBU_GUID@@KPEAUtagFORMATETC@@PEAUIOleClientSite@@PEAUIStorage@@PEAPEAX@Z; CW32System::OleCreateStaticFromData(IDataObject *,_GUID const &,ulong,tagFORMATETC *,IOleClientSite *,IStorage *,void * *)
0x18006e421  jmp     short loc_18006E47F
0x18006e423  cmp     r14d, 6
0x18006e427  jz      short loc_18006E460
0x18006e429  mov     rax, [r13+0]
0x18006e42d  test    dword ptr [rax+0B4h], 80000h
0x18006e437  jz      short loc_18006E43F
0x18006e439  cmp     r14d, 0Dh
0x18006e43d  jz      short loc_18006E460
0x18006e43f  lea     rax, [rbp+60h+var_A0.poleobj]
0x18006e443  mov     rcx, rsi; struct IDataObject *
0x18006e446  mov     [rsp+160h+var_130], rax; void **
0x18006e44b  lea     r9, [rsp+160h+var_108]; struct tagFORMATETC *
0x18006e450  mov     rax, [rbp+60h+var_A0.pstg]
0x18006e454  mov     [rsp+160h+var_138], rax; struct IStorage *
0x18006e459  call    ?OleCreateFromData@CW32System@@SAJPEAUIDataObject@@AEBU_GUID@@KPEAUtagFORMATETC@@PEAUIOleClientSite@@PEAUIStorage@@PEAPEAX@Z; CW32System::OleCreateFromData(IDataObject *,_GUID const &,ulong,tagFORMATETC *,IOleClientSite *,IStorage *,void * *)
0x18006e45e  jmp     short loc_18006E47F
0x18006e460  lea     rax, [rbp+60h+var_A0.poleobj]
0x18006e464  mov     rcx, rsi; struct IDataObject *
0x18006e467  mov     [rsp+160h+var_130], rax; struct IAdviseSink *
0x18006e46c  lea     r9, [rsp+160h+var_108]; struct tagFORMATETC *
0x18006e471  mov     rax, [rbp+60h+var_A0.pstg]
0x18006e475  mov     [rsp+160h+var_138], rax; int
0x18006e47a  call    ?OleCreateLinkFromData@CW32System@@SAJPEAUIDataObject@@AEBU_GUID@@KPEAUtagFORMATETC@@PEAUIOleClientSite@@PEAUIStorage@@PEAPEAX@Z; CW32System::OleCreateLinkFromData(IDataObject *,_GUID const &,ulong,tagFORMATETC *,IOleClientSite *,IStorage *,void * *)
0x18006e47f  mov     ebx, eax
0x18006e481  test    eax, eax
0x18006e483  jnz     loc_18006E584
0x18006e489  test    r15d, r15d
0x18006e48c  jnz     short loc_18006E4AC
0x18006e48e  mov     rcx, [rbp+60h+var_A0.poleobj]
0x18006e492  lea     rdx, [rbp+60h+var_A0.clsid]
0x18006e496  mov     rax, [rcx]
0x18006e499  mov     rax, [rax+78h]
0x18006e49d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e4a2  mov     ebx, eax
0x18006e4a4  test    eax, eax
0x18006e4a6  jnz     loc_18006E584
0x18006e4ac  test    r12, r12
0x18006e4af  jz      short loc_18006E50A
0x18006e4b1  mov     rcx, [rbp+60h+var_A0.poleobj]; struct IOleObject *
0x18006e4b5  lea     rax, [rsp+160h+var_118]
0x18006e4ba  mov     [rsp+160h+var_128], rax; int *
0x18006e4bf  lea     rdx, [rsp+160h+var_120]; unsigned int *
0x18006e4c4  mov     r9, r12; void *
0x18006e4c7  mov     dword ptr [rsp+160h+var_140], 0; int
0x18006e4cf  mov     [rsp+160h+var_118], 0
0x18006e4d7  call    ?OleStdSwitchDisplayAspect@@YAJPEAUIOleObject@@PEAKKPEAXHHPEAUIAdviseSink@@PEAH@Z; OleStdSwitchDisplayAspect(IOleObject *,ulong *,ulong,void *,int,int,IAdviseSink *,int *)
0x18006e4dc  mov     ebx, eax
0x18006e4de  test    eax, eax
0x18006e4e0  jnz     loc_18006E584
0x18006e4e6  mov     rcx, [rbp+60h+var_A0.poleobj]
0x18006e4ea  lea     r8, [rsp+160h+var_110]
0x18006e4ef  mov     edi, [rsp+160h+var_120]
0x18006e4f3  mov     edx, edi
0x18006e4f5  mov     rax, [rcx]
0x18006e4f8  mov     rax, [rax+90h]
0x18006e4ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e504  mov     ebx, eax
0x18006e506  test    eax, eax
0x18006e508  jnz     short loc_18006E584
0x18006e50a  lea     rcx, [rbp+60h+var_A0]; struct _reobject *
0x18006e50e  call    ?ObjectReadSiteFlags@@YAJPEAU_reobject@@@Z; ObjectReadSiteFlags(_reobject *)
0x18006e513  mov     ecx, [rbp+60h+var_A0.dwFlags]
0x18006e516  test    eax, eax
0x18006e518  mov     rbx, [rbp+60h+var_E0]
0x18006e51c  mov     eax, 1
0x18006e521  mov     rdx, [rsp+160h+var_E8]
0x18006e526  cmovnz  ecx, eax
0x18006e529  mov     [rbp+60h+var_A0.dwFlags], ecx
0x18006e52c  mov     r8d, eax
0x18006e52f  mov     rcx, rbx
0x18006e532  call    ?Delete@CTxtRange@@QEAAXPEAVIUndoBuilder@@W4SELRR@@@Z; CTxtRange::Delete(IUndoBuilder *,SELRR)
0x18006e537  mov     eax, [rbx+28h]
0x18006e53a  mov     rcx, [rbp+60h+var_A0.poleobj]
0x18006e53e  mov     rdx, [rbp+60h+var_A0.polesite]
0x18006e542  mov     [rbp+60h+var_A0.cp], eax
0x18006e545  mov     rax, [rsp+160h+var_110]
0x18006e54a  mov     qword ptr [rbp+60h+var_A0.sizel.cx], rax
0x18006e54e  mov     [rbp+60h+var_A0.cbStruct], 48h ; 'H'
0x18006e555  mov     [rbp+60h+var_A0.dvaspect], edi
0x18006e558  mov     rax, [rcx]
0x18006e55b  mov     rax, [rax+18h]
0x18006e55f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e564  mov     ebx, eax
0x18006e566  test    eax, eax
0x18006e568  jnz     short loc_18006E584
0x18006e56a  mov     rcx, [r13+0]
0x18006e56e  lea     rdx, [rbp+60h+var_A0]
0x18006e572  add     rcx, 8
0x18006e576  mov     rax, [rcx]
0x18006e579  mov     rax, [rax+38h]
0x18006e57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e582  mov     ebx, eax
0x18006e584  mov     rcx, [rbp+60h+var_A0.polesite]
0x18006e588  mov     rdx, [rbp+60h+var_A0.poleobj]
0x18006e58c  test    rdx, rdx
0x18006e58f  jz      short loc_18006E5A4
0x18006e591  mov     rax, [rdx]
0x18006e594  mov     rcx, rdx
0x18006e597  mov     rax, [rax+10h]
0x18006e59b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e5a0  mov     rcx, [rbp+60h+var_A0.polesite]
0x18006e5a4  test    rcx, rcx
0x18006e5a7  jz      short loc_18006E5B5
0x18006e5a9  mov     rax, [rcx]
0x18006e5ac  mov     rax, [rax+10h]
0x18006e5b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e5b5  mov     rcx, [rbp+60h+var_A0.pstg]
0x18006e5b9  test    rcx, rcx
0x18006e5bc  jz      short loc_18006E5CA
0x18006e5be  mov     rax, [rcx]
0x18006e5c1  mov     rax, [rax+10h]
0x18006e5c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e5ca  mov     eax, ebx
0x18006e5cc  jmp     short loc_18006E5D3
0x18006e5ce  mov     eax, 80004005h
0x18006e5d3  mov     rcx, [rbp+60h+var_50]
0x18006e5d7  xor     rcx, rsp; StackCookie
0x18006e5da  call    __security_check_cookie
0x18006e5df  add     rsp, 128h
0x18006e5e6  pop     r15
0x18006e5e8  pop     r14
0x18006e5ea  pop     r13
0x18006e5ec  pop     r12
0x18006e5ee  pop     rdi
0x18006e5ef  pop     rsi
0x18006e5f0  pop     rbx
0x18006e5f1  pop     rbp
0x18006e5f2  retn
```
