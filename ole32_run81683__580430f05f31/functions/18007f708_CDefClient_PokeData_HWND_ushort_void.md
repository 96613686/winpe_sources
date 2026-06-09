# CDefClient::PokeData(HWND__ *,ushort,void *)

- ea: `0x18007f708`
- end: `0x18007f9fc`
- name: `?PokeData@CDefClient@@QEAAJPEAUHWND__@@GPEAX@Z`
- size: `756`
- prototype: `HRESULT __fastcall(CDefClient *this, HWND__ *aItem, unsigned __int16 hPoke, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007c9d8`

## callees

- `0x18000aab0`
- `0x18007bac0`
- `0x18007c850`
- `0x18007e524`
- `0x18007ee34`
- `0x18007f708`
- `0x180081004`
- `0x1800ce010`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x18007f9c4`
- `KERNELBASE!GlobalFree` at `0x18007f9c4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007f9b1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007f9b1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007f785`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18007f785`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x18007f814`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x18007f814`
- `api-ms-win-core-com-l2-1-1!StgIsStorageILockBytes` at `0x18007f842`
- `api-ms-win-core-com-l2-1-1!StgIsStorageILockBytes` at `0x18007f842`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x18007f862`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x18007f862`

## pseudocode

```c
__int64 __fastcall CDefClient::PokeData(CDefClient *this, IPersistStorage *aItem, unsigned __int16 hPoke, void *a4)
{
  DVTARGETDEVICE *m_ptd; // rax
  DDEPOKE *v7; // rax
  CLIPFORMAT cfFormat; // r14
  unsigned int inited; // ebx
  int v10; // r12d
  HBITMAP hBitmap; // rcx
  DWORD v12; // eax
  ILockBytes **p_m_plkbytNative; // r14
  IStorage **p_m_pstgNative; // r15
  CDDEServer *m_psrvrParent; // rdx
  unsigned __int16 m_aItem; // ax
  CNVTYP m_cnvtyp; // r9d
  ATOM m_aClass; // r8
  tagSTGMEDIUM medium; // [rsp+40h] [rbp-40h] BYREF
  tagFORMATETC formatetc; // [rsp+58h] [rbp-28h] BYREF
  ILockBytes *plkbyt; // [rsp+C0h] [rbp+40h] BYREF
  IPersistStorage *pPersistStg; // [rsp+C8h] [rbp+48h] BYREF

  pPersistStg = aItem;
  m_ptd = this->m_ptd;
  pPersistStg = 0;
  *(_DWORD *)(&formatetc.cfFormat + 1) = 0;
  *(&formatetc.cfFormat + 3) = 0;
  *(_QWORD *)&formatetc.tymed = 1;
  formatetc.dwAspect = 1;
  *(_QWORD *)&medium.tymed = 1;
  this->m_aItem = hPoke;
  formatetc.cfFormat = 0;
  formatetc.ptd = m_ptd;
  formatetc.lindex = -1;
  *(_OWORD *)&medium.hBitmap = 0;
  if ( !a4 || (v7 = (DDEPOKE *)GlobalLock(a4)) == 0 )
  {
    v10 = 0;
    inited = -2147024882;
    goto $errRtn_98;
  }
  cfFormat = v7->cfFormat;
  formatetc.cfFormat = cfFormat;
  inited = -2147418113;
  v10 = (*(_WORD *)v7 >> 13) & 1;
  medium.hBitmap = MakeItemData(v7, a4, cfFormat);
  hBitmap = medium.hBitmap;
  if ( !medium.hBitmap )
    goto $errRtn_98;
  if ( cfFormat == 3 )
  {
    v12 = 32;
LABEL_8:
    formatetc.tymed = v12;
    medium.tymed = v12;
    goto LABEL_9;
  }
  if ( cfFormat == 2 )
  {
    v12 = 16;
    goto LABEL_8;
  }
LABEL_9:
  if ( formatetc.cfFormat != g_cfNative )
  {
    if ( !this->m_fGotEditNoPokeNativeYet || (inited = CDefClient::DoInitNew(this)) == 0 )
    {
      inited = ((__int64 (__fastcall *)(IDataObject *, tagFORMATETC *, tagSTGMEDIUM *, __int64))this->m_lpdataObj->lpVtbl[2].AddRef)(
                 this->m_lpdataObj,
                 &formatetc,
                 &medium,
                 1);
      if ( inited )
      {
        if ( medium.hBitmap )
          ReleaseStgMedium(&medium);
        goto $errRtn_98;
      }
      goto LABEL_13;
    }
LABEL_11:
    if ( medium.hBitmap )
      ReleaseStgMedium(&medium);
LABEL_13:
    medium.hBitmap = 0;
    goto $errRtn_98;
  }
  p_m_plkbytNative = &this->m_plkbytNative;
  this->m_fGotEditNoPokeNativeYet = 0;
  inited = CreateILockBytesOnHGlobal(hBitmap, 1, &this->m_plkbytNative);
  if ( inited )
    goto LABEL_11;
  p_m_pstgNative = &this->m_pstgNative;
  if ( StgIsStorageILockBytes(*p_m_plkbytNative) )
  {
    m_psrvrParent = this->m_psrvrParent;
    m_aItem = this->m_aItem;
    m_cnvtyp = m_psrvrParent->m_cnvtyp;
    m_aClass = m_psrvrParent->m_aClass;
    LOWORD(m_psrvrParent) = m_psrvrParent->m_aOriginalClass;
    plkbyt = 0;
    inited = wCreateStgAroundNative(
               medium.hBitmap,
               (ATOM)m_psrvrParent,
               m_aClass,
               m_cnvtyp,
               m_aItem,
               &this->m_pstgNative,
               &plkbyt);
    if ( inited )
      goto $errRtn_98;
    if ( *p_m_plkbytNative )
    {
      ((void (__fastcall *)(ILockBytes *))(*p_m_plkbytNative)->lpVtbl->Release)(*p_m_plkbytNative);
      medium.hBitmap = 0;
    }
    *p_m_plkbytNative = plkbyt;
  }
  else
  {
    inited = StgOpenStorageOnILockBytes(*p_m_plkbytNative, 0, 0x12u, 0, 0, &this->m_pstgNative);
    if ( inited )
      goto $errRtn_98;
  }
  if ( !*p_m_pstgNative )
    return 2147549183LL;
  inited = ((__int64 (__fastcall *)(IOleObject *, GUID *, IPersistStorage **))this->m_lpoleObj->lpVtbl->QueryInterface)(
             this->m_lpoleObj,
             &IID_IPersistStorage,
             &pPersistStg);
  if ( !inited )
  {
    inited = ((__int64 (__fastcall *)(IPersistStorage *, IStorage *))pPersistStg->lpVtbl[2].QueryInterface)(
               pPersistStg,
               *p_m_pstgNative);
    ((void (__fastcall *)(IPersistStorage *))pPersistStg->lpVtbl->Release)(pPersistStg);
    pPersistStg = 0;
    if ( !inited )
    {
      inited = CDefClient::SetClientSite(this);
      if ( !inited )
        inited = CDefClient::DoOle20Advise(this, OLE_CLOSED, 0);
    }
  }
$errRtn_98:
  GlobalUnlock(a4);
  if ( v10 && a4 )
    GlobalFree(a4);
  if ( pPersistStg )
    ((void (__fastcall *)(IPersistStorage *))pPersistStg->lpVtbl->Release)(pPersistStg);
  return inited;
}

```

## disassembly

```asm
0x18007f708  mov     [rsp-38h+arg_10], rbx
0x18007f70d  mov     [rsp-38h+pPersistStg], rdx
0x18007f712  push    rbp
0x18007f713  push    rsi
0x18007f714  push    rdi
0x18007f715  push    r12
0x18007f717  push    r13
0x18007f719  push    r14
0x18007f71b  push    r15
0x18007f71d  mov     rbp, rsp
0x18007f720  sub     rsp, 80h
0x18007f727  mov     rax, [this+0F0h]
0x18007f72e  xor     r13d, r13d
0x18007f731  mov     [rbp+pPersistStg], r13
0x18007f735  xorps   xmm0, xmm0
0x18007f738  mov     dword ptr [rbp+formatetc+2], r13d
0x18007f73c  mov     rsi, hPoke
0x18007f73f  mov     word ptr [rbp+formatetc+6], r13w
0x18007f744  mov     rdi, this
0x18007f747  mov     qword ptr [rbp+formatetc.tymed], 1
0x18007f74f  lea     r15d, [r13+1]
0x18007f753  mov     [rbp+formatetc.dwAspect], r15d
0x18007f757  mov     qword ptr [rbp+medium.tymed], 1
0x18007f75f  mov     [this+5Ch], aItem
0x18007f764  mov     [rbp+formatetc.cfFormat], r13w
0x18007f769  mov     [rbp+formatetc.ptd], rax
0x18007f76d  mov     [rbp+formatetc.lindex], 0FFFFFFFFh
0x18007f774  movdqu  xmmword ptr [rbp+medium.8], xmm0
0x18007f779  test    hPoke, hPoke
0x18007f77c  jz      loc_18007F9A6
0x18007f782  mov     this, hPoke; hMem
0x18007f785  call    cs:__imp_GlobalLock
0x18007f78b  test    rax, rax
0x18007f78e  jz      loc_18007F9A6
0x18007f794  movzx   r14d, word ptr [rax+2]
0x18007f799  mov     rdx, rsi; hPoke
0x18007f79c  mov     [rbp+formatetc.cfFormat], r14w
0x18007f7a1  movzx   r8d, r14w; cfFormat
0x18007f7a5  movzx   r12d, word ptr [rax]
0x18007f7a9  mov     this, rax; lpPoke
0x18007f7ac  shr     r12d, 0Dh
0x18007f7b0  mov     ebx, 8000FFFFh
0x18007f7b5  and     r12d, r15d
0x18007f7b8  call    ?MakeItemData@@YAPEAXPEAUDDEPOKE@@PEAXG@Z; MakeItemData(DDEPOKE *,void *,ushort)
0x18007f7bd  mov     qword ptr [rbp+medium.8], rax
0x18007f7c1  mov     this, rax; hGlobal
0x18007f7c4  test    rax, rax
0x18007f7c7  jz      $errRtn_98
0x18007f7cd  lea     eax, [r13+2]
0x18007f7d1  cmp     r14w, 3
0x18007f7d6  jnz     short loc_18007F7DE
0x18007f7d8  lea     eax, [r13+20h]
0x18007f7dc  jmp     short loc_18007F7E9
0x18007f7de  cmp     r14w, ax
0x18007f7e2  jnz     short loc_18007F7EF
0x18007f7e4  mov     eax, 10h
0x18007f7e9  mov     [rbp+formatetc.tymed], eax
0x18007f7ec  mov     [rbp+medium.tymed], eax
0x18007f7ef  movzx   eax, cs:?g_cfNative@@3GA; ushort g_cfNative
0x18007f7f6  cmp     [rbp+formatetc.cfFormat], ax
0x18007f7fa  jnz     loc_18007F955
0x18007f800  lea     r14, [rdi+0D0h]
0x18007f807  mov     [rdi+0FCh], r13d
0x18007f80e  mov     r8, r14; pplkbyt
0x18007f811  mov     edx, r15d; fDeleteOnRelease
0x18007f814  call    cs:__imp_CreateILockBytesOnHGlobal
0x18007f81a  mov     ebx, eax
0x18007f81c  test    eax, eax
0x18007f81e  jz      short loc_18007F838
0x18007f820  cmp     qword ptr [rbp+medium.8], r13
0x18007f824  jz      short loc_18007F82F
0x18007f826  lea     this, [rbp+medium]; LPSTGMEDIUM
0x18007f82a  call    ReleaseStgMedium
0x18007f82f  mov     qword ptr [rbp+medium.8], r13
0x18007f833  jmp     $errRtn_98
0x18007f838  mov     this, [r14]; plkbyt
0x18007f83b  lea     r15, [rdi+0D8h]
0x18007f842  call    cs:__imp_StgIsStorageILockBytes
0x18007f848  test    eax, eax
0x18007f84a  jnz     short loc_18007F874
0x18007f84c  mov     this, [r14]; plkbyt
0x18007f84f  lea     r8d, [rax+12h]; grfMode
0x18007f853  mov     [rsp+80h+ppstgOpen], r15; ppstgOpen
0x18007f858  xor     r9d, r9d; snbExclude
0x18007f85b  xor     edx, edx; pstgPriority
0x18007f85d  mov     [rsp+80h+reserved], r13d; reserved
0x18007f862  call    cs:__imp_StgOpenStorageOnILockBytes
0x18007f868  mov     ebx, eax
0x18007f86a  test    eax, eax
0x18007f86c  jnz     $errRtn_98
0x18007f872  jmp     short loc_18007F8D5
0x18007f874  mov     rdx, [rdi+0E8h]
0x18007f87b  lea     rax, [rbp+plkbyt]
0x18007f87f  mov     this, qword ptr [rbp+medium.8]; hNative
0x18007f883  mov     [rsp+80h+pplkbyt], rax; pplkbyt
0x18007f888  movzx   eax, word ptr [rdi+5Ch]
0x18007f88c  mov     r9d, [rdx+6Ch]; cnvtyp
0x18007f890  movzx   r8d, word ptr [rdx+74h]; aClassNew
0x18007f895  movzx   edx, word ptr [rdx+76h]; aClassOld
0x18007f899  mov     [rsp+80h+ppstgOpen], r15; ppstg
0x18007f89e  mov     [rbp+plkbyt], r13
0x18007f8a2  mov     word ptr [rsp+80h+reserved], ax; aItem
0x18007f8a7  call    ?wCreateStgAroundNative@@YAJPEAXGGW4CNVTYP@@GPEAPEAUIStorage@@PEAPEAUILockBytes@@@Z; wCreateStgAroundNative(void *,ushort,ushort,CNVTYP,ushort,IStorage * *,ILockBytes * *)
0x18007f8ac  mov     ebx, eax
0x18007f8ae  test    eax, eax
0x18007f8b0  jnz     $errRtn_98
0x18007f8b6  mov     this, [r14]
0x18007f8b9  test    this, this
0x18007f8bc  jz      short loc_18007F8CE
0x18007f8be  mov     rax, [this]
0x18007f8c1  mov     rax, [rax+10h]
0x18007f8c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f8ca  mov     qword ptr [rbp+medium.8], r13
0x18007f8ce  mov     this, [rbp+plkbyt]
0x18007f8d2  mov     [r14], this
0x18007f8d5  cmp     [r15], r13
0x18007f8d8  jnz     short loc_18007F8E4
0x18007f8da  mov     eax, 8000FFFFh
0x18007f8df  jmp     loc_18007F9E1
0x18007f8e4  mov     this, [rdi+40h]
0x18007f8e8  lea     r8, [rbp+pPersistStg]
0x18007f8ec  lea     rdx, IID_IPersistStorage
0x18007f8f3  mov     rax, [this]
0x18007f8f6  mov     rax, [rax]
0x18007f8f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f8fe  mov     ebx, eax
0x18007f900  test    eax, eax
0x18007f902  jnz     $errRtn_98
0x18007f908  mov     this, [rbp+pPersistStg]
0x18007f90c  mov     rdx, [r15]
0x18007f90f  mov     rax, [this]
0x18007f912  mov     rax, [rax+30h]
0x18007f916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f91b  mov     this, [rbp+pPersistStg]
0x18007f91f  mov     ebx, eax
0x18007f921  mov     rax, [this]
0x18007f924  mov     rax, [rax+10h]
0x18007f928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f92d  mov     [rbp+pPersistStg], r13
0x18007f931  test    ebx, ebx
0x18007f933  jnz     short $errRtn_98
0x18007f935  mov     this, rdi; this
0x18007f938  call    ?SetClientSite@CDefClient@@QEAAJXZ; CDefClient::SetClientSite(void)
0x18007f93d  mov     ebx, eax
0x18007f93f  test    eax, eax
0x18007f941  jnz     short $errRtn_98
0x18007f943  xor     r8d, r8d; cf
0x18007f946  lea     edx, [rax+2]; options
0x18007f949  mov     this, rdi; this
0x18007f94c  call    ?DoOle20Advise@CDefClient@@QEAAJW4OLE_NOTIFICATION@@G@Z; CDefClient::DoOle20Advise(OLE_NOTIFICATION,ushort)
0x18007f951  mov     ebx, eax
0x18007f953  jmp     short $errRtn_98
0x18007f955  cmp     [rdi+0FCh], r13d
0x18007f95c  jz      short loc_18007F970
0x18007f95e  mov     this, rdi; this
0x18007f961  call    ?DoInitNew@CDefClient@@QEAAJXZ; CDefClient::DoInitNew(void)
0x18007f966  mov     ebx, eax
0x18007f968  test    eax, eax
0x18007f96a  jnz     loc_18007F820
0x18007f970  mov     this, [rdi+48h]
0x18007f974  lea     r8, [rbp+medium]
0x18007f978  mov     r9d, r15d
0x18007f97b  lea     rdx, [rbp+formatetc]
0x18007f97f  mov     rax, [this]
0x18007f982  mov     rax, [rax+38h]
0x18007f986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f98b  mov     ebx, eax
0x18007f98d  test    eax, eax
0x18007f98f  jz      loc_18007F82F
0x18007f995  cmp     qword ptr [rbp+medium.8], r13
0x18007f999  jz      short $errRtn_98
0x18007f99b  lea     this, [rbp+medium]; LPSTGMEDIUM
0x18007f99f  call    ReleaseStgMedium
0x18007f9a4  jmp     short $errRtn_98
0x18007f9a6  mov     r12d, r13d
0x18007f9a9  mov     ebx, 8007000Eh
0x18007f9ae  mov     this, rsi; hMem
0x18007f9b1  call    cs:__imp_GlobalUnlock
0x18007f9b7  test    r12d, r12d
0x18007f9ba  jz      short loc_18007F9CA
0x18007f9bc  test    rsi, rsi
0x18007f9bf  jz      short loc_18007F9CA
0x18007f9c1  mov     this, rsi; hMem
0x18007f9c4  call    cs:__imp_GlobalFree
0x18007f9ca  mov     this, [rbp+pPersistStg]
0x18007f9ce  test    this, this
0x18007f9d1  jz      short loc_18007F9DF
0x18007f9d3  mov     rax, [this]
0x18007f9d6  mov     rax, [rax+10h]
0x18007f9da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f9df  mov     eax, ebx
0x18007f9e1  mov     rbx, [rsp+80h+arg_10]
0x18007f9e9  add     rsp, 80h
0x18007f9f0  pop     r15
0x18007f9f2  pop     r14
0x18007f9f4  pop     r13
0x18007f9f6  pop     r12
0x18007f9f8  pop     rdi
0x18007f9f9  pop     rsi
0x18007f9fa  pop     rbp
0x18007f9fb  retn
```
