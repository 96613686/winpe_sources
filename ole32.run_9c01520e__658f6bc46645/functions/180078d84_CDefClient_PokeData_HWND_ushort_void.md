# CDefClient::PokeData(HWND__ *,ushort,void *)

- ea: `0x180078d84`
- end: `0x180079096`
- name: `?PokeData@CDefClient@@QEAAJPEAUHWND__@@GPEAX@Z`
- size: `786`
- prototype: `HRESULT __fastcall(CDefClient *this, HWND__ *aItem, unsigned __int16 hPoke, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180075bbc`

## callees

- `0x180008d60`
- `0x180074b6c`
- `0x180075a28`
- `0x180077928`
- `0x1800783a0`
- `0x180078d84`
- `0x18007a934`
- `0x1800d8010`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x180079057`
- `KERNELBASE!GlobalFree` at `0x180079057`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007903e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18007903e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180078e06`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180078e06`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x180078e92`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x180078e92`
- `api-ms-win-core-com-l2-1-1!StgIsStorageILockBytes` at `0x180078ec6`
- `api-ms-win-core-com-l2-1-1!StgIsStorageILockBytes` at `0x180078ec6`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x180078eec`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x180078eec`

## pseudocode

```c
__int64 __fastcall CDefClient::PokeData(CDefClient *this, IPersistStorage *aItem, unsigned __int16 hPoke, void *a4)
{
  DVTARGETDEVICE *m_ptd; // rax
  unsigned int inited; // ebx
  int v8; // r12d
  DDEPOKE *v9; // rax
  CLIPFORMAT cfFormat; // si
  HBITMAP hBitmap; // rcx
  DWORD v12; // eax
  ILockBytes **p_m_plkbytNative; // rsi
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
  formatetc.lindex = -1;
  m_ptd = this->m_ptd;
  pPersistStg = 0;
  *(_DWORD *)(&formatetc.cfFormat + 1) = 0;
  *(&formatetc.cfFormat + 3) = 0;
  formatetc.dwAspect = 1;
  inited = -2147418113;
  *(_QWORD *)&formatetc.tymed = 1;
  v8 = 0;
  *(_QWORD *)&medium.tymed = 1;
  this->m_aItem = hPoke;
  formatetc.cfFormat = 0;
  formatetc.ptd = m_ptd;
  *(_OWORD *)&medium.hBitmap = 0;
  if ( !a4 || (v9 = (DDEPOKE *)GlobalLock(a4)) == 0 )
  {
    inited = -2147024882;
    goto $errRtn_66;
  }
  cfFormat = v9->cfFormat;
  formatetc.cfFormat = cfFormat;
  v8 = (*(_WORD *)v9 >> 13) & 1;
  medium.hBitmap = (HBITMAP)MakeItemData(v9, a4, cfFormat);
  hBitmap = medium.hBitmap;
  if ( !medium.hBitmap )
    goto $errRtn_66;
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
        goto $errRtn_66;
      }
      goto LABEL_13;
    }
LABEL_11:
    if ( medium.hBitmap )
      ReleaseStgMedium(&medium);
LABEL_13:
    medium.hBitmap = 0;
    goto $errRtn_66;
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
      goto $errRtn_66;
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
      goto $errRtn_66;
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
$errRtn_66:
  GlobalUnlock(a4);
  if ( v8 && a4 )
    GlobalFree(a4);
  if ( pPersistStg )
    ((void (__fastcall *)(IPersistStorage *))pPersistStg->lpVtbl->Release)(pPersistStg);
  return inited;
}

```

## disassembly

```asm
0x180078d84  mov     [rsp-38h+arg_10], rbx
0x180078d89  mov     [rsp-38h+pPersistStg], rdx
0x180078d8e  push    rbp
0x180078d8f  push    rsi
0x180078d90  push    rdi
0x180078d91  push    r12
0x180078d93  push    r13
0x180078d95  push    r14
0x180078d97  push    r15
0x180078d99  mov     rbp, rsp
0x180078d9c  sub     rsp, 80h
0x180078da3  or      [rbp+formatetc.lindex], 0FFFFFFFFh
0x180078da7  xor     r13d, r13d
0x180078daa  mov     rax, [this+0F0h]
0x180078db1  xorps   xmm0, xmm0
0x180078db4  mov     [rbp+pPersistStg], r13
0x180078db8  mov     r14, hPoke
0x180078dbb  mov     dword ptr [rbp+formatetc+2], r13d
0x180078dbf  mov     rdi, this
0x180078dc2  mov     word ptr [rbp+formatetc+6], r13w
0x180078dc7  lea     r15d, [r13+1]
0x180078dcb  mov     [rbp+formatetc.dwAspect], r15d
0x180078dcf  mov     ebx, 8000FFFFh
0x180078dd4  mov     qword ptr [rbp+formatetc.tymed], 1
0x180078ddc  mov     r12d, r13d
0x180078ddf  mov     qword ptr [rbp+medium.tymed], 1
0x180078de7  mov     [this+5Ch], aItem
0x180078dec  mov     [rbp+formatetc.cfFormat], r13w
0x180078df1  mov     [rbp+formatetc.ptd], rax
0x180078df5  movdqu  xmmword ptr [rbp+medium.8], xmm0
0x180078dfa  test    hPoke, hPoke
0x180078dfd  jz      loc_180079036
0x180078e03  mov     this, hPoke; hMem
0x180078e06  call    cs:__imp_GlobalLock
0x180078e0d  nop     dword ptr [rax+rax+00h]
0x180078e12  test    rax, rax
0x180078e15  jz      loc_180079036
0x180078e1b  movzx   esi, word ptr [rax+2]
0x180078e1f  mov     rdx, r14; hPoke
0x180078e22  mov     [rbp+formatetc.cfFormat], si
0x180078e26  movzx   r8d, si; cfFormat
0x180078e2a  movzx   r12d, word ptr [rax]
0x180078e2e  mov     this, rax; lpPoke
0x180078e31  shr     r12d, 0Dh
0x180078e35  and     r12d, r15d
0x180078e38  call    ?MakeItemData@@YAPEAXPEAUDDEPOKE@@PEAXG@Z; MakeItemData(DDEPOKE *,void *,ushort)
0x180078e3d  mov     qword ptr [rbp+medium.8], rax
0x180078e41  mov     this, rax; hGlobal
0x180078e44  test    rax, rax
0x180078e47  jz      $errRtn_66
0x180078e4d  lea     eax, [r13+2]
0x180078e51  cmp     si, 3
0x180078e55  jnz     short loc_180078E5D
0x180078e57  lea     eax, [r13+20h]
0x180078e5b  jmp     short loc_180078E67
0x180078e5d  cmp     si, ax
0x180078e60  jnz     short loc_180078E6D
0x180078e62  mov     eax, 10h
0x180078e67  mov     [rbp+formatetc.tymed], eax
0x180078e6a  mov     [rbp+medium.tymed], eax
0x180078e6d  movzx   eax, cs:?g_cfNative@@3GA; ushort g_cfNative
0x180078e74  cmp     [rbp+formatetc.cfFormat], ax
0x180078e78  jnz     loc_180078FE5
0x180078e7e  lea     rsi, [rdi+0D0h]
0x180078e85  mov     [rdi+0FCh], r13d
0x180078e8c  mov     r8, rsi; pplkbyt
0x180078e8f  mov     edx, r15d; fDeleteOnRelease
0x180078e92  call    cs:__imp_CreateILockBytesOnHGlobal
0x180078e99  nop     dword ptr [rax+rax+00h]
0x180078e9e  mov     ebx, eax
0x180078ea0  test    eax, eax
0x180078ea2  jz      short loc_180078EBC
0x180078ea4  cmp     qword ptr [rbp+medium.8], r13
0x180078ea8  jz      short loc_180078EB3
0x180078eaa  lea     this, [rbp+medium]; LPSTGMEDIUM
0x180078eae  call    ReleaseStgMedium
0x180078eb3  mov     qword ptr [rbp+medium.8], r13
0x180078eb7  jmp     $errRtn_66
0x180078ebc  mov     this, [rsi]; plkbyt
0x180078ebf  lea     r15, [rdi+0D8h]
0x180078ec6  call    cs:__imp_StgIsStorageILockBytes
0x180078ecd  nop     dword ptr [rax+rax+00h]
0x180078ed2  test    eax, eax
0x180078ed4  jnz     short loc_180078F04
0x180078ed6  mov     this, [rsi]; plkbyt
0x180078ed9  lea     r8d, [rax+12h]; grfMode
0x180078edd  mov     [rsp+80h+ppstgOpen], r15; ppstgOpen
0x180078ee2  xor     r9d, r9d; snbExclude
0x180078ee5  xor     edx, edx; pstgPriority
0x180078ee7  mov     [rsp+80h+reserved], r13d; reserved
0x180078eec  call    cs:__imp_StgOpenStorageOnILockBytes
0x180078ef3  nop     dword ptr [rax+rax+00h]
0x180078ef8  mov     ebx, eax
0x180078efa  test    eax, eax
0x180078efc  jnz     $errRtn_66
0x180078f02  jmp     short loc_180078F65
0x180078f04  mov     rdx, [rdi+0E8h]
0x180078f0b  lea     rax, [rbp+plkbyt]
0x180078f0f  mov     this, qword ptr [rbp+medium.8]; hNative
0x180078f13  mov     [rsp+80h+pplkbyt], rax; pplkbyt
0x180078f18  movzx   eax, word ptr [rdi+5Ch]
0x180078f1c  mov     r9d, [rdx+6Ch]; cnvtyp
0x180078f20  movzx   r8d, word ptr [rdx+74h]; aClassNew
0x180078f25  movzx   edx, word ptr [rdx+76h]; aClassOld
0x180078f29  mov     [rsp+80h+ppstgOpen], r15; ppstg
0x180078f2e  mov     [rbp+plkbyt], r13
0x180078f32  mov     word ptr [rsp+80h+reserved], ax; aItem
0x180078f37  call    ?wCreateStgAroundNative@@YAJPEAXGGW4CNVTYP@@GPEAPEAUIStorage@@PEAPEAUILockBytes@@@Z; wCreateStgAroundNative(void *,ushort,ushort,CNVTYP,ushort,IStorage * *,ILockBytes * *)
0x180078f3c  mov     ebx, eax
0x180078f3e  test    eax, eax
0x180078f40  jnz     $errRtn_66
0x180078f46  mov     this, [rsi]
0x180078f49  test    this, this
0x180078f4c  jz      short loc_180078F5E
0x180078f4e  mov     rax, [this]
0x180078f51  mov     rax, [rax+10h]
0x180078f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078f5a  mov     qword ptr [rbp+medium.8], r13
0x180078f5e  mov     this, [rbp+plkbyt]
0x180078f62  mov     [rsi], this
0x180078f65  cmp     [r15], r13
0x180078f68  jnz     short loc_180078F74
0x180078f6a  mov     eax, 8000FFFFh
0x180078f6f  jmp     loc_18007907A
0x180078f74  mov     this, [rdi+40h]
0x180078f78  lea     r8, [rbp+pPersistStg]
0x180078f7c  lea     rdx, IID_IPersistStorage
0x180078f83  mov     rax, [this]
0x180078f86  mov     rax, [rax]
0x180078f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078f8e  mov     ebx, eax
0x180078f90  test    eax, eax
0x180078f92  jnz     $errRtn_66
0x180078f98  mov     this, [rbp+pPersistStg]
0x180078f9c  mov     rdx, [r15]
0x180078f9f  mov     rax, [this]
0x180078fa2  mov     rax, [rax+30h]
0x180078fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078fab  mov     this, [rbp+pPersistStg]
0x180078faf  mov     ebx, eax
0x180078fb1  mov     rax, [this]
0x180078fb4  mov     rax, [rax+10h]
0x180078fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078fbd  mov     [rbp+pPersistStg], r13
0x180078fc1  test    ebx, ebx
0x180078fc3  jnz     short $errRtn_66
0x180078fc5  mov     this, rdi; this
0x180078fc8  call    ?SetClientSite@CDefClient@@QEAAJXZ; CDefClient::SetClientSite(void)
0x180078fcd  mov     ebx, eax
0x180078fcf  test    eax, eax
0x180078fd1  jnz     short $errRtn_66
0x180078fd3  xor     r8d, r8d; cf
0x180078fd6  lea     edx, [rax+2]; options
0x180078fd9  mov     this, rdi; this
0x180078fdc  call    ?DoOle20Advise@CDefClient@@QEAAJW4OLE_NOTIFICATION@@G@Z; CDefClient::DoOle20Advise(OLE_NOTIFICATION,ushort)
0x180078fe1  mov     ebx, eax
0x180078fe3  jmp     short $errRtn_66
0x180078fe5  cmp     [rdi+0FCh], r13d
0x180078fec  jz      short loc_180079000
0x180078fee  mov     this, rdi; this
0x180078ff1  call    ?DoInitNew@CDefClient@@QEAAJXZ; CDefClient::DoInitNew(void)
0x180078ff6  mov     ebx, eax
0x180078ff8  test    eax, eax
0x180078ffa  jnz     loc_180078EA4
0x180079000  mov     this, [rdi+48h]
0x180079004  lea     r8, [rbp+medium]
0x180079008  mov     r9d, r15d
0x18007900b  lea     rdx, [rbp+formatetc]
0x18007900f  mov     rax, [this]
0x180079012  mov     rax, [rax+38h]
0x180079016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007901b  mov     ebx, eax
0x18007901d  test    eax, eax
0x18007901f  jz      loc_180078EB3
0x180079025  cmp     qword ptr [rbp+medium.8], r13
0x180079029  jz      short $errRtn_66
0x18007902b  lea     this, [rbp+medium]; LPSTGMEDIUM
0x18007902f  call    ReleaseStgMedium
0x180079034  jmp     short $errRtn_66
0x180079036  mov     ebx, 8007000Eh
0x18007903b  mov     this, r14; hMem
0x18007903e  call    cs:__imp_GlobalUnlock
0x180079045  nop     dword ptr [rax+rax+00h]
0x18007904a  test    r12d, r12d
0x18007904d  jz      short loc_180079063
0x18007904f  test    r14, r14
0x180079052  jz      short loc_180079063
0x180079054  mov     this, r14; hMem
0x180079057  call    cs:__imp_GlobalFree
0x18007905e  nop     dword ptr [rax+rax+00h]
0x180079063  mov     this, [rbp+pPersistStg]
0x180079067  test    this, this
0x18007906a  jz      short loc_180079078
0x18007906c  mov     rax, [this]
0x18007906f  mov     rax, [rax+10h]
0x180079073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079078  mov     eax, ebx
0x18007907a  mov     rbx, [rsp+80h+arg_10]
0x180079082  add     rsp, 80h
0x180079089  pop     r15
0x18007908b  pop     r14
0x18007908d  pop     r13
0x18007908f  pop     r12
0x180079091  pop     rdi
0x180079092  pop     rsi
0x180079093  pop     rbp
0x180079094  retn
```
