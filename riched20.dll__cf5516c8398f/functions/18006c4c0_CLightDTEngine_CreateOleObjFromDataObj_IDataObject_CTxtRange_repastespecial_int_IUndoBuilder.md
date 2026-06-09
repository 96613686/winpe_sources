# CLightDTEngine::CreateOleObjFromDataObj(IDataObject *,CTxtRange *,_repastespecial *,int,IUndoBuilder *)

- ea: `0x18006c4c0`
- end: `0x18006c8af`
- name: `?CreateOleObjFromDataObj@CLightDTEngine@@QEAAJPEAUIDataObject@@PEAVCTxtRange@@PEAU_repastespecial@@HPEAVIUndoBuilder@@@Z`
- size: `1007`
- prototype: `int(CLightDTEngine *__hidden this, struct IDataObject *, struct CTxtRange *, struct _repastespecial *, int, struct IUndoBuilder *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18006cc4c`

## callees

- `0x18004b528`
- `0x18006c4c0`
- `0x18008c1bc`
- `0x18008c8dc`
- `0x18008fbd0`
- `0x18008fc64`
- `0x18008fcfc`
- `0x180090508`
- `0x18009110a`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x18006c608`
- `KERNEL32!GlobalLock` at `0x18006c608`
- `KERNEL32!GlobalUnlock` at `0x18006c61d`
- `KERNEL32!GlobalUnlock` at `0x18006c61d`

## pseudocode

```c
__int64 __fastcall CLightDTEngine::CreateOleObjFromDataObj(
        CLightDTEngine *this,
        struct IDataObject *a2,
        struct CTxtRange *a3,
        struct _repastespecial *a4,
        int a5,
        struct IUndoBuilder *a6)
{
  __int64 v9; // rax
  DWORD dwAspect; // edi
  __int64 v11; // rcx
  __int64 v12; // rbx
  void *dwParam; // r13
  struct IDataObjectVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetData)(IDataObject *, FORMATETC *, STGMEDIUM *); // rax
  HBITMAP hBitmap; // r15
  _DWORD *v18; // rax
  GUID v19; // xmm0
  unsigned int v20; // ebx
  __int64 v21; // r15
  unsigned int v22; // eax
  __int64 v23; // r8
  LPOLECLIENTSITE polesite; // rcx
  unsigned int v25; // eax
  unsigned int v26; // r8d
  int v27; // eax
  DWORD dwFlags; // ecx
  struct CTxtRange *v29; // rbx
  struct IOleClientSite *v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+28h] [rbp-D8h]
  struct IAdviseSink *v32; // [rsp+30h] [rbp-D0h]
  unsigned int v33; // [rsp+40h] [rbp-C0h] BYREF
  int v34[2]; // [rsp+48h] [rbp-B8h] BYREF
  SIZEL v35; // [rsp+50h] [rbp-B0h] BYREF
  struct tagFORMATETC v36; // [rsp+58h] [rbp-A8h] BYREF
  struct IUndoBuilder *v37; // [rsp+78h] [rbp-88h]
  struct CTxtRange *v38; // [rsp+80h] [rbp-80h]
  __int128 v39; // [rsp+88h] [rbp-78h] BYREF
  __int128 v40; // [rsp+98h] [rbp-68h]
  struct tagSTGMEDIUM hMem; // [rsp+A8h] [rbp-58h] BYREF
  struct _reobject v42; // [rsp+C0h] [rbp-40h] BYREF

  *(_QWORD *)v34 = this;
  v37 = a6;
  v38 = a3;
  if ( !a2 || !a3 )
    return 2147500037LL;
  memset_0(&v42, 0, sizeof(v42));
  v9 = *(_QWORD *)this;
  v35 = 0;
  dwAspect = 0;
  v39 = 0;
  v40 = 0;
  v11 = *(_QWORD *)(v9 + 136);
  if ( v11 )
    v12 = *(_QWORD *)(v11 + 32);
  else
    v12 = 0;
  memset(&v36, 0, sizeof(v36));
  if ( !v12 )
    return 2147500034LL;
  dwParam = 0;
  memset(&hMem, 0, sizeof(hMem));
  if ( (unsigned int)(a5 - 7) <= 2 )
    dwAspect = 1;
  if ( a5 == 13 )
    dwAspect = 4;
  v33 = dwAspect;
  if ( a4 )
  {
    if ( dwAspect )
      goto LABEL_22;
    dwAspect = a4->dwAspect;
    v33 = dwAspect;
    if ( dwAspect == 4 )
      dwParam = (void *)a4->dwParam;
  }
  if ( !dwAspect )
  {
    LOWORD(v39) = xmmword_1800A3170;
    lpVtbl = a2->lpVtbl;
    LODWORD(v40) = 1;
    *((_QWORD *)&v39 + 1) = 0;
    GetData = lpVtbl->GetData;
    *(_QWORD *)((char *)&v40 + 4) = 0x1FFFFFFFFLL;
    if ( ((unsigned int (__fastcall *)(struct IDataObject *, __int128 *, struct tagSTGMEDIUM *))GetData)(
           a2,
           &v39,
           &hMem) )
    {
      goto LABEL_21;
    }
    hBitmap = hMem.hBitmap;
    v18 = GlobalLock(hMem.hBitmap);
    if ( v18 )
    {
      dwAspect = v18[5];
      v33 = dwAspect;
    }
    GlobalUnlock(hBitmap);
    CW32System::ReleaseStgMedium(&hMem);
    if ( !dwAspect )
    {
LABEL_21:
      dwAspect = 1;
      v33 = 1;
    }
  }
LABEL_22:
  if ( (unsigned int)(a5 - 7) <= 2 )
  {
    if ( a5 == 7 )
      v19 = CLSID_StaticMetafile;
    else
      v19 = CLSID_StaticDib;
    v42.clsid = v19;
  }
  v20 = (*(__int64 (__fastcall **)(__int64, LPSTORAGE *))(*(_QWORD *)v12 + 24LL))(v12, &v42.pstg);
  if ( v20 )
    goto LABEL_46;
  v21 = *(_QWORD *)v34;
  v22 = (*(__int64 (__fastcall **)(__int64, LPOLECLIENTSITE *))(*(_QWORD *)(**(_QWORD **)v34 + 8LL) + 24LL))(
          **(_QWORD **)v34 + 8LL,
          &v42.polesite);
  polesite = v42.polesite;
  v20 = v22;
  if ( v42.polesite )
  {
    *(_QWORD *)&v36.cfFormat = 0;
    *(_QWORD *)&v36.tymed = 0;
    v36.ptd = 0;
    v36.dwAspect = dwAspect;
    v36.lindex = -1;
    if ( (unsigned int)(a5 - 7) > 2 )
    {
      if ( a5 == 6 || (*(_DWORD *)(**(_QWORD **)v34 + 180LL) & 0x80000) != 0 && a5 == 13 )
        v25 = CW32System::OleCreateLinkFromData(a2, 0, v23, &v36, v30, v42.pstg, (void **)&v42.poleobj);
      else
        v25 = CW32System::OleCreateFromData(a2, 0, v23, &v36, v30, v42.pstg, (void **)&v42.poleobj);
    }
    else
    {
      v25 = CW32System::OleCreateStaticFromData(a2, 0, v23, &v36, v30, v42.pstg, (void **)&v42.poleobj);
    }
    v20 = v25;
    if ( !v25
      && ((unsigned int)(a5 - 7) <= 2
       || (v20 = ((__int64 (__fastcall *)(LPOLEOBJECT, CLSID *))v42.poleobj->lpVtbl->GetUserClassID)(
                   v42.poleobj,
                   &v42.clsid)) == 0) )
    {
      if ( !dwParam
        || (v34[0] = 0, (v20 = OleStdSwitchDisplayAspect(v42.poleobj, &v33, v26, dwParam, 0, v31, v32, v34)) == 0)
        && (dwAspect = v33,
            (v20 = ((__int64 (__fastcall *)(LPOLEOBJECT, _QWORD, SIZEL *))v42.poleobj->lpVtbl->GetExtent)(
                     v42.poleobj,
                     v33,
                     &v35)) == 0) )
      {
        v27 = ObjectReadSiteFlags(&v42);
        dwFlags = v42.dwFlags;
        v29 = v38;
        if ( v27 )
          dwFlags = 1;
        v42.dwFlags = dwFlags;
        CTxtRange::Delete(v38, v37, 1);
        v42.cp = *((_DWORD *)v29 + 10);
        v42.sizel = v35;
        v42.cbStruct = 72;
        v42.dvaspect = dwAspect;
        v20 = ((__int64 (__fastcall *)(LPOLEOBJECT, LPOLECLIENTSITE))v42.poleobj->lpVtbl->SetClientSite)(
                v42.poleobj,
                v42.polesite);
        if ( !v20 )
          v20 = (*(__int64 (__fastcall **)(__int64, struct _reobject *))(*(_QWORD *)(*(_QWORD *)v21 + 8LL) + 56LL))(
                  *(_QWORD *)v21 + 8LL,
                  &v42);
      }
    }
LABEL_46:
    polesite = v42.polesite;
  }
  if ( v42.poleobj )
  {
    ((void (__fastcall *)(LPOLEOBJECT))v42.poleobj->lpVtbl->Release)(v42.poleobj);
    polesite = v42.polesite;
  }
  if ( polesite )
    ((void (__fastcall *)(LPOLECLIENTSITE))polesite->lpVtbl->Release)(polesite);
  if ( v42.pstg )
    ((void (__fastcall *)(LPSTORAGE))v42.pstg->lpVtbl->Release)(v42.pstg);
  return v20;
}

```

## disassembly

```asm
0x18006c4c0  push    rbp
0x18006c4c2  push    rbx
0x18006c4c3  push    rsi
0x18006c4c4  push    rdi
0x18006c4c5  push    r12
0x18006c4c7  push    r13
0x18006c4c9  push    r14
0x18006c4cb  push    r15
0x18006c4cd  lea     rbp, [rsp-28h]
0x18006c4d2  sub     rsp, 128h
0x18006c4d9  mov     rax, cs:__security_cookie
0x18006c4e0  xor     rax, rsp
0x18006c4e3  mov     [rbp+60h+var_50], rax
0x18006c4e7  mov     qword ptr [rsp+160h+var_118], rcx
0x18006c4ec  mov     rbx, rcx
0x18006c4ef  mov     rcx, [rbp+60h+arg_28]
0x18006c4f6  mov     rax, r8
0x18006c4f9  mov     [rsp+160h+var_E8], rcx
0x18006c4fe  mov     r15, r9
0x18006c501  mov     [rbp+60h+var_E0], rax
0x18006c505  mov     r12, rdx
0x18006c508  test    rdx, rdx
0x18006c50b  jz      loc_18006C88A
0x18006c511  test    rax, rax
0x18006c514  jz      loc_18006C88A
0x18006c51a  xor     edx, edx; Val
0x18006c51c  lea     rcx, [rbp+60h+var_A0]; void *
0x18006c520  lea     r8d, [rdx+48h]; Size
0x18006c524  call    memset_0
0x18006c529  mov     rax, [rbx]
0x18006c52c  xorps   xmm0, xmm0
0x18006c52f  mov     [rsp+160h+var_110], 0
0x18006c538  xor     edi, edi
0x18006c53a  movups  [rbp+60h+var_D8], xmm0
0x18006c53e  movups  [rbp+60h+var_C8], xmm0
0x18006c542  mov     rcx, [rax+88h]
0x18006c549  test    rcx, rcx
0x18006c54c  jz      short loc_18006C554
0x18006c54e  mov     rbx, [rcx+20h]
0x18006c552  jmp     short loc_18006C556
0x18006c554  xor     ebx, ebx
0x18006c556  mov     esi, [rbp+60h+arg_20]
0x18006c55c  xor     r14d, r14d
0x18006c55f  movups  xmmword ptr [rsp+160h+var_108.cfFormat], xmm0
0x18006c564  movups  xmmword ptr [rsp+160h+var_108.dwAspect], xmm0
0x18006c569  lea     eax, [rsi-7]
0x18006c56c  cmp     eax, 2
0x18006c56f  setbe   r14b
0x18006c573  test    rbx, rbx
0x18006c576  jnz     short loc_18006C582
0x18006c578  mov     eax, 80004002h
0x18006c57d  jmp     loc_18006C88F
0x18006c582  xor     eax, eax
0x18006c584  xor     r13d, r13d
0x18006c587  test    r14d, r14d
0x18006c58a  mov     [rbp+60h+var_A8], rax
0x18006c58e  movups  xmmword ptr [rbp+60h+hMem], xmm0
0x18006c592  lea     ecx, [rax+1]
0x18006c595  cmovnz  edi, ecx
0x18006c598  lea     eax, [rcx+3]
0x18006c59b  cmp     esi, 0Dh
0x18006c59e  cmovz   edi, eax
0x18006c5a1  mov     [rsp+160h+var_120], edi
0x18006c5a5  test    r15, r15
0x18006c5a8  jz      short loc_18006C5C1
0x18006c5aa  test    edi, edi
0x18006c5ac  jnz     loc_18006C639
0x18006c5b2  mov     edi, [r15]
0x18006c5b5  mov     [rsp+160h+var_120], edi
0x18006c5b9  cmp     edi, eax
0x18006c5bb  jnz     short loc_18006C5C1
0x18006c5bd  mov     r13, [r15+4]
0x18006c5c1  test    edi, edi
0x18006c5c3  jnz     short loc_18006C639
0x18006c5c5  movzx   eax, word ptr cs:xmmword_1800A3170
0x18006c5cc  lea     r8, [rbp+60h+hMem]
0x18006c5d0  mov     word ptr [rbp+60h+var_D8], ax
0x18006c5d4  lea     rdx, [rbp+60h+var_D8]
0x18006c5d8  mov     rax, [r12]
0x18006c5dc  mov     dword ptr [rbp+60h+var_C8], ecx
0x18006c5df  mov     dword ptr [rbp+60h+var_C8+8], ecx
0x18006c5e2  mov     rcx, r12
0x18006c5e5  mov     qword ptr [rbp+60h+var_D8+8], 0
0x18006c5ed  mov     rax, [rax+18h]
0x18006c5f1  mov     dword ptr [rbp+60h+var_C8+4], 0FFFFFFFFh
0x18006c5f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c5fd  test    eax, eax
0x18006c5ff  jnz     short loc_18006C630
0x18006c601  mov     r15, [rbp+60h+hMem+8]
0x18006c605  mov     rcx, r15; hMem
0x18006c608  call    cs:__imp_GlobalLock
0x18006c60e  test    rax, rax
0x18006c611  jz      short loc_18006C61A
0x18006c613  mov     edi, [rax+14h]
0x18006c616  mov     [rsp+160h+var_120], edi
0x18006c61a  mov     rcx, r15; hMem
0x18006c61d  call    cs:__imp_GlobalUnlock
0x18006c623  lea     rcx, [rbp+60h+hMem]; struct tagSTGMEDIUM *
0x18006c627  call    ?ReleaseStgMedium@CW32System@@SAJPEAUtagSTGMEDIUM@@@Z; CW32System::ReleaseStgMedium(tagSTGMEDIUM *)
0x18006c62c  test    edi, edi
0x18006c62e  jnz     short loc_18006C639
0x18006c630  mov     edi, 1
0x18006c635  mov     [rsp+160h+var_120], edi
0x18006c639  test    r14d, r14d
0x18006c63c  jz      short loc_18006C658
0x18006c63e  cmp     esi, 7
0x18006c641  jnz     short loc_18006C64C
0x18006c643  movups  xmm0, xmmword ptr cs:CLSID_StaticMetafile.Data1
0x18006c64a  jmp     short loc_18006C653
0x18006c64c  movups  xmm0, xmmword ptr cs:CLSID_StaticDib.Data1
0x18006c653  movdqu  xmmword ptr [rbp+60h+var_A0.clsid.Data1], xmm0
0x18006c658  mov     rax, [rbx]
0x18006c65b  lea     rdx, [rbp+60h+var_A0.pstg]
0x18006c65f  mov     rcx, rbx
0x18006c662  mov     rax, [rax+18h]
0x18006c666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c66b  mov     ebx, eax
0x18006c66d  test    eax, eax
0x18006c66f  jnz     loc_18006C840
0x18006c675  mov     r15, qword ptr [rsp+160h+var_118]
0x18006c67a  lea     rdx, [rbp+60h+var_A0.polesite]
0x18006c67e  mov     rcx, [r15]
0x18006c681  add     rcx, 8
0x18006c685  mov     rax, [rcx]
0x18006c688  mov     rax, [rax+18h]
0x18006c68c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c691  mov     rcx, [rbp+60h+var_A0.polesite]
0x18006c695  xor     edx, edx; struct _GUID *
0x18006c697  mov     ebx, eax
0x18006c699  test    rcx, rcx
0x18006c69c  jz      loc_18006C844
0x18006c6a2  mov     qword ptr [rsp+160h+var_108.cfFormat], rdx
0x18006c6a7  mov     qword ptr [rsp+160h+var_108.tymed], rdx
0x18006c6ac  mov     [rsp+160h+var_108.ptd], rdx
0x18006c6b1  mov     [rsp+160h+var_108.dwAspect], edi
0x18006c6b5  mov     [rsp+160h+var_108.lindex], 0FFFFFFFFh
0x18006c6bd  test    r14d, r14d
0x18006c6c0  jz      short loc_18006C6E3
0x18006c6c2  lea     rax, [rbp+60h+var_A0.poleobj]
0x18006c6c6  mov     rcx, r12; struct IDataObject *
0x18006c6c9  mov     [rsp+160h+var_130], rax; void **
0x18006c6ce  lea     r9, [rsp+160h+var_108]; struct tagFORMATETC *
0x18006c6d3  mov     rax, [rbp+60h+var_A0.pstg]
0x18006c6d7  mov     [rsp+160h+var_138], rax; struct IStorage *
0x18006c6dc  call    ?OleCreateStaticFromData@CW32System@@SAJPEAUIDataObject@@AEBU_GUID@@KPEAUtagFORMATETC@@PEAUIOleClientSite@@PEAUIStorage@@PEAPEAX@Z; CW32System::OleCreateStaticFromData(IDataObject *,_GUID const &,ulong,tagFORMATETC *,IOleClientSite *,IStorage *,void * *)
0x18006c6e1  jmp     short loc_18006C73C
0x18006c6e3  cmp     esi, 6
0x18006c6e6  jz      short loc_18006C71D
0x18006c6e8  mov     rax, [r15]
0x18006c6eb  test    dword ptr [rax+0B4h], 80000h
0x18006c6f5  jz      short loc_18006C6FC
0x18006c6f7  cmp     esi, 0Dh
0x18006c6fa  jz      short loc_18006C71D
0x18006c6fc  lea     rax, [rbp+60h+var_A0.poleobj]
0x18006c700  mov     rcx, r12; struct IDataObject *
0x18006c703  mov     [rsp+160h+var_130], rax; void **
0x18006c708  lea     r9, [rsp+160h+var_108]; struct tagFORMATETC *
0x18006c70d  mov     rax, [rbp+60h+var_A0.pstg]
0x18006c711  mov     [rsp+160h+var_138], rax; struct IStorage *
0x18006c716  call    ?OleCreateFromData@CW32System@@SAJPEAUIDataObject@@AEBU_GUID@@KPEAUtagFORMATETC@@PEAUIOleClientSite@@PEAUIStorage@@PEAPEAX@Z; CW32System::OleCreateFromData(IDataObject *,_GUID const &,ulong,tagFORMATETC *,IOleClientSite *,IStorage *,void * *)
0x18006c71b  jmp     short loc_18006C73C
0x18006c71d  lea     rax, [rbp+60h+var_A0.poleobj]
0x18006c721  mov     rcx, r12; struct IDataObject *
0x18006c724  mov     [rsp+160h+var_130], rax; struct IAdviseSink *
0x18006c729  lea     r9, [rsp+160h+var_108]; struct tagFORMATETC *
0x18006c72e  mov     rax, [rbp+60h+var_A0.pstg]
0x18006c732  mov     [rsp+160h+var_138], rax; int
0x18006c737  call    ?OleCreateLinkFromData@CW32System@@SAJPEAUIDataObject@@AEBU_GUID@@KPEAUtagFORMATETC@@PEAUIOleClientSite@@PEAUIStorage@@PEAPEAX@Z; CW32System::OleCreateLinkFromData(IDataObject *,_GUID const &,ulong,tagFORMATETC *,IOleClientSite *,IStorage *,void * *)
0x18006c73c  mov     ebx, eax
0x18006c73e  test    eax, eax
0x18006c740  jnz     loc_18006C840
0x18006c746  test    r14d, r14d
0x18006c749  jnz     short loc_18006C769
0x18006c74b  mov     rcx, [rbp+60h+var_A0.poleobj]
0x18006c74f  lea     rdx, [rbp+60h+var_A0.clsid]
0x18006c753  mov     rax, [rcx]
0x18006c756  mov     rax, [rax+78h]
0x18006c75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c75f  mov     ebx, eax
0x18006c761  test    eax, eax
0x18006c763  jnz     loc_18006C840
0x18006c769  test    r13, r13
0x18006c76c  jz      short loc_18006C7C7
0x18006c76e  mov     rcx, [rbp+60h+var_A0.poleobj]; struct IOleObject *
0x18006c772  lea     rax, [rsp+160h+var_118]
0x18006c777  mov     [rsp+160h+var_128], rax; int *
0x18006c77c  lea     rdx, [rsp+160h+var_120]; unsigned int *
0x18006c781  mov     r9, r13; void *
0x18006c784  mov     dword ptr [rsp+160h+var_140], 0; int
0x18006c78c  mov     [rsp+160h+var_118], 0
0x18006c794  call    ?OleStdSwitchDisplayAspect@@YAJPEAUIOleObject@@PEAKKPEAXHHPEAUIAdviseSink@@PEAH@Z; OleStdSwitchDisplayAspect(IOleObject *,ulong *,ulong,void *,int,int,IAdviseSink *,int *)
0x18006c799  mov     ebx, eax
0x18006c79b  test    eax, eax
0x18006c79d  jnz     loc_18006C840
0x18006c7a3  mov     rcx, [rbp+60h+var_A0.poleobj]
0x18006c7a7  lea     r8, [rsp+160h+var_110]
0x18006c7ac  mov     edi, [rsp+160h+var_120]
0x18006c7b0  mov     edx, edi
0x18006c7b2  mov     rax, [rcx]
0x18006c7b5  mov     rax, [rax+90h]
0x18006c7bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c7c1  mov     ebx, eax
0x18006c7c3  test    eax, eax
0x18006c7c5  jnz     short loc_18006C840
0x18006c7c7  lea     rcx, [rbp+60h+var_A0]; struct _reobject *
0x18006c7cb  call    ?ObjectReadSiteFlags@@YAJPEAU_reobject@@@Z; ObjectReadSiteFlags(_reobject *)
0x18006c7d0  mov     ecx, [rbp+60h+var_A0.dwFlags]
0x18006c7d3  test    eax, eax
0x18006c7d5  mov     rbx, [rbp+60h+var_E0]
0x18006c7d9  mov     eax, 1
0x18006c7de  mov     rdx, [rsp+160h+var_E8]
0x18006c7e3  cmovnz  ecx, eax
0x18006c7e6  mov     [rbp+60h+var_A0.dwFlags], ecx
0x18006c7e9  mov     r8d, eax
0x18006c7ec  mov     rcx, rbx
0x18006c7ef  call    ?Delete@CTxtRange@@QEAAXPEAVIUndoBuilder@@W4SELRR@@@Z; CTxtRange::Delete(IUndoBuilder *,SELRR)
0x18006c7f4  mov     eax, [rbx+28h]
0x18006c7f7  mov     rcx, [rbp+60h+var_A0.poleobj]
0x18006c7fb  mov     rdx, [rbp+60h+var_A0.polesite]
0x18006c7ff  mov     [rbp+60h+var_A0.cp], eax
0x18006c802  mov     rax, [rsp+160h+var_110]
0x18006c807  mov     qword ptr [rbp+60h+var_A0.sizel.cx], rax
0x18006c80b  mov     [rbp+60h+var_A0.cbStruct], 48h ; 'H'
0x18006c812  mov     [rbp+60h+var_A0.dvaspect], edi
0x18006c815  mov     rax, [rcx]
0x18006c818  mov     rax, [rax+18h]
0x18006c81c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c821  mov     ebx, eax
0x18006c823  test    eax, eax
0x18006c825  jnz     short loc_18006C840
0x18006c827  mov     rcx, [r15]
0x18006c82a  lea     rdx, [rbp+60h+var_A0]
0x18006c82e  add     rcx, 8
0x18006c832  mov     rax, [rcx]
0x18006c835  mov     rax, [rax+38h]
0x18006c839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c83e  mov     ebx, eax
0x18006c840  mov     rcx, [rbp+60h+var_A0.polesite]
0x18006c844  mov     rdx, [rbp+60h+var_A0.poleobj]
0x18006c848  test    rdx, rdx
0x18006c84b  jz      short loc_18006C860
0x18006c84d  mov     rax, [rdx]
0x18006c850  mov     rcx, rdx
0x18006c853  mov     rax, [rax+10h]
0x18006c857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c85c  mov     rcx, [rbp+60h+var_A0.polesite]
0x18006c860  test    rcx, rcx
0x18006c863  jz      short loc_18006C871
0x18006c865  mov     rax, [rcx]
0x18006c868  mov     rax, [rax+10h]
0x18006c86c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c871  mov     rcx, [rbp+60h+var_A0.pstg]
0x18006c875  test    rcx, rcx
0x18006c878  jz      short loc_18006C886
0x18006c87a  mov     rax, [rcx]
0x18006c87d  mov     rax, [rax+10h]
0x18006c881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c886  mov     eax, ebx
0x18006c888  jmp     short loc_18006C88F
0x18006c88a  mov     eax, 80004005h
0x18006c88f  mov     rcx, [rbp+60h+var_50]
0x18006c893  xor     rcx, rsp; StackCookie
0x18006c896  call    __security_check_cookie
0x18006c89b  add     rsp, 128h
0x18006c8a2  pop     r15
0x18006c8a4  pop     r14
0x18006c8a6  pop     r13
0x18006c8a8  pop     r12
0x18006c8aa  pop     rdi
0x18006c8ab  pop     rsi
0x18006c8ac  pop     rbx
0x18006c8ad  pop     rbp
0x18006c8ae  retn
```
