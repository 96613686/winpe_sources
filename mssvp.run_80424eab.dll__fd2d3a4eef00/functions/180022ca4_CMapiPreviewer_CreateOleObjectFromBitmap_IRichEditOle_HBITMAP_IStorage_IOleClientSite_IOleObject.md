# CMapiPreviewer::CreateOleObjectFromBitmap(IRichEditOle *,HBITMAP__ *,IStorage * *,IOleClientSite * *,IOleObject * *)

- ea: `0x180022ca4`
- end: `0x180022e0b`
- name: `?CreateOleObjectFromBitmap@CMapiPreviewer@@CAJPEAUIRichEditOle@@PEAUHBITMAP__@@PEAPEAUIStorage@@PEAPEAUIOleClientSite@@PEAPEAUIOleObject@@@Z`
- size: `359`
- prototype: `__int64 __fastcall(struct IRichEditOle *, HBITMAP, struct IStorage **, struct IOleClientSite **, struct IOleObject **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800265dc`

## callees

- `0x180005210`
- `0x1800083f8`
- `0x180022bc0`
- `0x180022ca4`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x180022cf3`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x180022cf3`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x180022cd8`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x180022cd8`
- `ext-ms-win-com-ole32-l1-1-2!OleSetContainedObject` at `0x180022dd3`
- `ext-ms-win-com-ole32-l1-1-2!OleSetContainedObject` at `0x180022dd3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMapiPreviewer::CreateOleObjectFromBitmap(
        struct IRichEditOle *a1,
        HBITMAP a2,
        struct IStorage **a3,
        struct IOleClientSite **a4,
        struct IOleObject **a5)
{
  HRESULT DocfileOnILockBytes; // ebx
  struct IDataObject *v10; // rdi
  LPUNKNOWN *v11; // r14
  const struct _GUID *v12; // rdx
  unsigned int v13; // r8d
  struct IDataObject *v15; // [rsp+40h] [rbp-21h] BYREF
  __int128 v16; // [rsp+48h] [rbp-19h]
  tagFORMATETC v17; // [rsp+60h] [rbp-1h] BYREF
  LPLOCKBYTES pplkbyt; // [rsp+C8h] [rbp+67h] BYREF

  pplkbyt = 0;
  DocfileOnILockBytes = CreateILockBytesOnHGlobal(0, 1, &pplkbyt);
  if ( DocfileOnILockBytes >= 0 )
  {
    DocfileOnILockBytes = StgCreateDocfileOnILockBytes(pplkbyt, 0x1012u, 0, a3);
    if ( DocfileOnILockBytes >= 0 )
      DocfileOnILockBytes = ((__int64 (__fastcall *)(struct IRichEditOle *, struct IOleClientSite **))a1->lpVtbl->GetClientSite)(
                              a1,
                              a4);
  }
  *(_DWORD *)(&v17.cfFormat + 1) = 0;
  *(&v17.cfFormat + 3) = 0;
  *(_QWORD *)&v17.tymed = 16;
  v17.cfFormat = 2;
  v17.ptd = 0;
  v17.dwAspect = 1;
  v17.lindex = -1;
  *(_QWORD *)&v16 = 16;
  *((_QWORD *)&v16 + 1) = a2;
  v15 = 0;
  if ( DocfileOnILockBytes >= 0 )
  {
    DocfileOnILockBytes = ATL::CComObject<CAttachmentImageDataObject>::CreateInstance(&v15);
    v10 = v15;
    if ( DocfileOnILockBytes >= 0 )
    {
      ((void (__fastcall *)(struct IDataObject *))v15->lpVtbl->AddRef)(v15);
      *(_OWORD *)&v10[8].lpVtbl = v16;
      v10[10].lpVtbl = 0;
      *(tagFORMATETC *)&v10[11].lpVtbl = v17;
      v11 = (LPUNKNOWN *)a5;
      DocfileOnILockBytes = OleCreateStaticFromDataHelper(v10, v12, v13, &v17, *a4, *a3, (void **)a5);
      if ( DocfileOnILockBytes >= 0 )
        DocfileOnILockBytes = OleSetContainedObject(*v11, 1);
    }
    if ( v10 )
      ((void (__fastcall *)(struct IDataObject *))v10->lpVtbl->Release)(v10);
  }
  ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&pplkbyt);
  return (unsigned int)DocfileOnILockBytes;
}

```

## disassembly

```asm
0x180022ca4  push    rbp
0x180022ca6  push    rbx
0x180022ca7  push    rsi
0x180022ca8  push    rdi
0x180022ca9  push    r14
0x180022cab  push    r15
0x180022cad  lea     rbp, [rsp-27h]
0x180022cb2  sub     rsp, 88h
0x180022cb9  mov     r15, r9
0x180022cbc  mov     rsi, r8
0x180022cbf  mov     r14, rdx
0x180022cc2  mov     rdi, rcx
0x180022cc5  mov     [rbp+4Fh+pplkbyt], 0
0x180022ccd  lea     r8, [rbp+4Fh+pplkbyt]; pplkbyt
0x180022cd1  mov     edx, 1; fDeleteOnRelease
0x180022cd6  xor     ecx, ecx; hGlobal
0x180022cd8  call    cs:__imp_CreateILockBytesOnHGlobal
0x180022cde  mov     ebx, eax
0x180022ce0  test    eax, eax
0x180022ce2  js      short loc_180022D13
0x180022ce4  mov     r9, rsi; ppstgOpen
0x180022ce7  xor     r8d, r8d; reserved
0x180022cea  mov     edx, 1012h; grfMode
0x180022cef  mov     rcx, [rbp+4Fh+pplkbyt]; plkbyt
0x180022cf3  call    cs:__imp_StgCreateDocfileOnILockBytes
0x180022cf9  mov     ebx, eax
0x180022cfb  test    eax, eax
0x180022cfd  js      short loc_180022D13
0x180022cff  mov     rax, [rdi]
0x180022d02  mov     rdx, r15
0x180022d05  mov     rcx, rdi
0x180022d08  mov     rax, [rax+18h]
0x180022d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d11  mov     ebx, eax
0x180022d13  mov     dword ptr [rbp+4Fh+var_50+2], 0
0x180022d1a  xor     eax, eax
0x180022d1c  mov     word ptr [rbp+4Fh+var_50+6], ax
0x180022d20  mov     qword ptr [rbp+4Fh+var_50.tymed], 10h
0x180022d28  mov     eax, 2
0x180022d2d  mov     [rbp+4Fh+var_50.cfFormat], ax
0x180022d31  mov     [rbp+4Fh+var_50.ptd], 0
0x180022d39  mov     [rbp+4Fh+var_50.dwAspect], 1
0x180022d40  mov     [rbp+4Fh+var_50.lindex], 0FFFFFFFFh
0x180022d47  mov     qword ptr [rbp+4Fh+var_68], 10h
0x180022d4f  mov     qword ptr [rbp+4Fh+var_68+8], r14
0x180022d53  xor     r14d, r14d
0x180022d56  mov     [rbp+4Fh+var_70], r14
0x180022d5a  test    ebx, ebx
0x180022d5c  js      loc_180022DF0
0x180022d62  lea     rcx, [rbp+4Fh+var_70]
0x180022d66  call    ?CreateInstance@?$CComObject@VCAttachmentImageDataObject@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CAttachmentImageDataObject>::CreateInstance(ATL::CComObject<CAttachmentImageDataObject> * *)
0x180022d6b  mov     ebx, eax
0x180022d6d  mov     rdi, [rbp+4Fh+var_70]
0x180022d71  test    eax, eax
0x180022d73  js      short loc_180022DDB
0x180022d75  mov     rax, [rdi]
0x180022d78  mov     rcx, rdi
0x180022d7b  mov     rax, [rax+8]
0x180022d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d84  movups  xmm0, [rbp+4Fh+var_68]
0x180022d88  movups  xmmword ptr [rdi+40h], xmm0
0x180022d8c  mov     [rdi+50h], r14
0x180022d90  movups  xmm0, xmmword ptr [rbp+4Fh+var_50.cfFormat]
0x180022d94  movups  xmmword ptr [rdi+58h], xmm0
0x180022d98  movups  xmm1, xmmword ptr [rbp+4Fh+var_50.dwAspect]
0x180022d9c  movups  xmmword ptr [rdi+68h], xmm1
0x180022da0  mov     r14, [rbp+4Fh+arg_20]
0x180022da4  mov     [rsp+0B0h+var_80], r14; void **
0x180022da9  mov     rax, [rsi]
0x180022dac  mov     [rsp+0B0h+var_88], rax; struct IStorage *
0x180022db1  mov     rax, [r15]
0x180022db4  mov     [rsp+0B0h+var_90], rax; struct IOleClientSite *
0x180022db9  lea     r9, [rbp+4Fh+var_50]; struct tagFORMATETC *
0x180022dbd  mov     rcx, rdi; struct IDataObject *
0x180022dc0  call    ?OleCreateStaticFromDataHelper@@YAJPEAUIDataObject@@AEBU_GUID@@KPEAUtagFORMATETC@@PEAUIOleClientSite@@PEAUIStorage@@PEAPEAX@Z; OleCreateStaticFromDataHelper(IDataObject *,_GUID const &,ulong,tagFORMATETC *,IOleClientSite *,IStorage *,void * *)
0x180022dc5  mov     ebx, eax
0x180022dc7  test    eax, eax
0x180022dc9  js      short loc_180022DDB
0x180022dcb  mov     edx, 1; fContained
0x180022dd0  mov     rcx, [r14]; pUnknown
0x180022dd3  call    cs:__imp_OleSetContainedObject
0x180022dd9  mov     ebx, eax
0x180022ddb  test    rdi, rdi
0x180022dde  jz      short loc_180022DF0
0x180022de0  mov     rax, [rdi]
0x180022de3  mov     rcx, rdi
0x180022de6  mov     rax, [rax+10h]
0x180022dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022def  nop
0x180022df0  lea     rcx, [rbp+4Fh+pplkbyt]
0x180022df4  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180022df9  mov     eax, ebx
0x180022dfb  add     rsp, 88h
0x180022e02  pop     r15
0x180022e04  pop     r14
0x180022e06  pop     rdi
0x180022e07  pop     rsi
0x180022e08  pop     rbx
0x180022e09  pop     rbp
0x180022e0a  retn
```
