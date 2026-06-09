# CDefClient::GetData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x180077ec8`
- end: `0x18007810b`
- name: `?GetData@CDefClient@@AEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `579`
- prototype: `HRESULT __fastcall(CDefClient *this, tagFORMATETC *pformatetc, tagSTGMEDIUM *pmedium)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800792a0`
- `0x180079f94`

## callees

- `0x180017b84`
- `0x180046460`
- `0x180077ec8`
- `0x18007f480`
- `0x1800ab6d8`
- `0x1800d8010`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x1800780b8`
- `KERNELBASE!GlobalFree` at `0x1800780b8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180078071`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180078071`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18007800f`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18007800f`
- `api-ms-win-core-com-l2-1-1!GetHGlobalFromILockBytes` at `0x180078046`
- `api-ms-win-core-com-l2-1-1!GetHGlobalFromILockBytes` at `0x180078046`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x180077f62`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x180077f62`
- `api-ms-win-core-com-l2-1-1!ReadClassStg` at `0x180077ff5`
- `api-ms-win-core-com-l2-1-1!ReadClassStg` at `0x180077ff5`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x180077f87`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x180077f87`

## pseudocode

```c
__int64 __fastcall CDefClient::GetData(CDefClient *this, tagFORMATETC *pformatetc, tagSTGMEDIUM *pmedium)
{
  IDataObject *m_lpdataObj; // rcx
  unsigned int v6; // r13d
  struct IUnknownVtbl *lpVtbl; // r9
  unsigned int ILockBytesOnHGlobal; // ebx
  IPersistStorage *v9; // rcx
  IStorage **p_m_pstgNative; // rsi
  IStorage *m_pstgNative; // rdx
  BOOL v12; // r8d
  HBITMAP v13; // rax
  HBITMAP v14; // rbx
  IPersistStorage *v15; // rcx
  IPersistStorage *pPersistStg; // [rsp+20h] [rbp-30h] BYREF
  void *hNative; // [rsp+28h] [rbp-28h] BYREF
  _GUID clsid; // [rsp+30h] [rbp-20h] BYREF

  m_lpdataObj = this->m_lpdataObj;
  pPersistStg = 0;
  hNative = 0;
  v6 = 0;
  clsid = 0;
  lpVtbl = m_lpdataObj->lpVtbl;
  if ( pformatetc->cfFormat != g_cfNative )
    return ((unsigned int (*)(void))lpVtbl[1].QueryInterface)();
  ILockBytesOnHGlobal = ((__int64 (__fastcall *)(IDataObject *, GUID *, IPersistStorage **))lpVtbl->QueryInterface)(
                          m_lpdataObj,
                          &IID_IPersistStorage,
                          &pPersistStg);
  if ( !ILockBytesOnHGlobal )
  {
    v9 = pPersistStg;
    if ( !pPersistStg )
      goto $errRtn_63;
    p_m_pstgNative = &this->m_pstgNative;
    m_pstgNative = this->m_pstgNative;
    if ( m_pstgNative )
    {
      v12 = 1;
      goto LABEL_10;
    }
    ILockBytesOnHGlobal = CreateILockBytesOnHGlobal(0, 1, &this->m_plkbytNative);
    if ( !ILockBytesOnHGlobal )
    {
      ILockBytesOnHGlobal = StgCreateDocfileOnILockBytes(this->m_plkbytNative, 0x1012u, 0, &this->m_pstgNative);
      if ( !ILockBytesOnHGlobal )
      {
        m_pstgNative = *p_m_pstgNative;
        if ( *p_m_pstgNative )
        {
          v9 = pPersistStg;
          v12 = 0;
LABEL_10:
          this->m_fInOleSave = 1;
          ILockBytesOnHGlobal = OleSave(v9, m_pstgNative, v12);
          ((void (__fastcall *)(IPersistStorage *, _QWORD))pPersistStg->lpVtbl[2].Release)(pPersistStg, 0);
          this->m_fInOleSave = 0;
          if ( !ILockBytesOnHGlobal )
          {
            ILockBytesOnHGlobal = ReadClassStg(*p_m_pstgNative, &clsid);
            if ( !ILockBytesOnHGlobal )
            {
              if ( CoIsOle1Class(&clsid) )
              {
                v6 = ILockBytesOnHGlobal + 1;
                ILockBytesOnHGlobal = StRead10NativeData(*p_m_pstgNative, &hNative);
                if ( !ILockBytesOnHGlobal )
                {
                  pmedium->hBitmap = (HBITMAP)hNative;
LABEL_19:
                  v15 = pPersistStg;
                  pmedium->tymed = 1;
                  pmedium->pUnkForRelease = 0;
                  ((void (__fastcall *)(IPersistStorage *))v15->lpVtbl->Release)(v15);
                  return 0;
                }
              }
              else
              {
                ILockBytesOnHGlobal = GetHGlobalFromILockBytes(this->m_plkbytNative, &hNative);
                if ( !ILockBytesOnHGlobal )
                {
                  v13 = (HBITMAP)UtDupGlobal(hNative, 0x2002u);
                  v14 = v13;
                  if ( v13 )
                    GlobalSize(v13);
                  pmedium->hBitmap = v14;
                  goto LABEL_19;
                }
              }
            }
          }
        }
      }
    }
  }
  v9 = pPersistStg;
$errRtn_63:
  if ( hNative && v6 )
  {
    GlobalFree(hNative);
    v9 = pPersistStg;
  }
  if ( v9 )
    ((void (__fastcall *)(IPersistStorage *))v9->lpVtbl->Release)(v9);
  pmedium->tymed = 0;
  pmedium->pUnkForRelease = 0;
  return ILockBytesOnHGlobal;
}

```

## disassembly

```asm
0x180077ec8  push    rbp
0x180077eca  push    rbx
0x180077ecb  push    rsi
0x180077ecc  push    rdi
0x180077ecd  push    r12
0x180077ecf  push    r13
0x180077ed1  push    r14
0x180077ed3  mov     rbp, rsp
0x180077ed6  sub     rsp, 50h
0x180077eda  mov     rax, cs:__security_cookie
0x180077ee1  xor     rax, rsp
0x180077ee4  mov     [rbp+var_10], rax
0x180077ee8  movzx   eax, cs:?g_cfNative@@3GA; ushort g_cfNative
0x180077eef  xor     r12d, r12d
0x180077ef2  mov     r14, this
0x180077ef5  mov     this, [this+48h]
0x180077ef9  xorps   xmm0, xmm0
0x180077efc  mov     [rbp+pPersistStg], r12
0x180077f00  mov     rdi, pmedium
0x180077f03  mov     [rbp+hNative], r12
0x180077f07  mov     r13d, r12d
0x180077f0a  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x180077f0e  mov     r9, [this]
0x180077f11  cmp     [pformatetc], ax
0x180077f14  jnz     loc_1800780E2
0x180077f1a  mov     rax, [r9]
0x180077f1d  lea     pmedium, [rbp+pPersistStg]
0x180077f21  lea     pformatetc, IID_IPersistStorage
0x180077f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077f2d  mov     ebx, eax
0x180077f2f  test    eax, eax
0x180077f31  jnz     loc_1800780A3
0x180077f37  mov     this, [rbp+pPersistStg]; pPS
0x180077f3b  test    this, this
0x180077f3e  jz      $errRtn_63
0x180077f44  lea     rsi, [r14+0D8h]
0x180077f4b  mov     pformatetc, [rsi]; pStg
0x180077f4e  test    pformatetc, pformatetc
0x180077f51  jnz     short loc_180077FB5
0x180077f53  lea     r12, [r14+0D0h]
0x180077f5a  xor     ecx, ecx; hGlobal
0x180077f5c  mov     pmedium, r12; pplkbyt
0x180077f5f  lea     edx, [rax+1]; fDeleteOnRelease
0x180077f62  call    cs:__imp_CreateILockBytesOnHGlobal
0x180077f69  nop     dword ptr [rax+rax+00h]
0x180077f6e  mov     ebx, eax
0x180077f70  test    eax, eax
0x180077f72  jnz     loc_1800780A0
0x180077f78  mov     this, [r12]; plkbyt
0x180077f7c  mov     r9, rsi; ppstgOpen
0x180077f7f  xor     r8d, r8d; reserved
0x180077f82  mov     edx, 1012h; grfMode
0x180077f87  call    cs:__imp_StgCreateDocfileOnILockBytes
0x180077f8e  nop     dword ptr [rax+rax+00h]
0x180077f93  xor     r12d, r12d
0x180077f96  mov     ebx, eax
0x180077f98  test    eax, eax
0x180077f9a  jnz     loc_1800780A3
0x180077fa0  mov     pformatetc, [rsi]
0x180077fa3  test    pformatetc, pformatetc
0x180077fa6  jz      loc_1800780A3
0x180077fac  mov     this, [rbp+pPersistStg]
0x180077fb0  xor     r8d, r8d
0x180077fb3  jmp     short loc_180077FBB
0x180077fb5  mov     r8d, 1; fSameAsLoad
0x180077fbb  mov     dword ptr [r14+0A4h], 1
0x180077fc6  call    OleSave
0x180077fcb  mov     this, [rbp+pPersistStg]
0x180077fcf  mov     ebx, eax
0x180077fd1  xor     edx, edx
0x180077fd3  mov     rax, [this]
0x180077fd6  mov     rax, [rax+40h]
0x180077fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077fdf  mov     [r14+0A4h], r12d
0x180077fe6  test    ebx, ebx
0x180077fe8  jnz     loc_1800780A3
0x180077fee  mov     this, [rsi]; pStg
0x180077ff1  lea     pformatetc, [rbp+clsid]; pclsid
0x180077ff5  call    cs:__imp_ReadClassStg
0x180077ffc  nop     dword ptr [rax+rax+00h]
0x180078001  mov     ebx, eax
0x180078003  test    eax, eax
0x180078005  jnz     loc_1800780A3
0x18007800b  lea     this, [rbp+clsid]; rclsid
0x18007800f  call    cs:__imp_CoIsOle1Class
0x180078016  nop     dword ptr [rax+rax+00h]
0x18007801b  lea     pformatetc, [rbp+hNative]; phglobal
0x18007801f  test    eax, eax
0x180078021  jz      short loc_18007803F
0x180078023  mov     this, [rsi]; pstg
0x180078026  lea     r13d, [rbx+1]
0x18007802a  call    ?StRead10NativeData@@YAJPEAUIStorage@@PEAPEAX@Z; StRead10NativeData(IStorage *,void * *)
0x18007802f  mov     ebx, eax
0x180078031  test    eax, eax
0x180078033  jnz     short loc_1800780A3
0x180078035  mov     rax, [rbp+hNative]
0x180078039  mov     [rdi+8], rax
0x18007803d  jmp     short loc_180078081
0x18007803f  mov     this, [r14+0D0h]; plkbyt
0x180078046  call    cs:__imp_GetHGlobalFromILockBytes
0x18007804d  nop     dword ptr [rax+rax+00h]
0x180078052  mov     ebx, eax
0x180078054  test    eax, eax
0x180078056  jnz     short loc_1800780A3
0x180078058  mov     this, [rbp+hNative]; hsrc
0x18007805c  mov     edx, 2002h; uiFlags
0x180078061  call    ?UtDupGlobal@@YAPEAXPEAXI@Z; UtDupGlobal(void *,uint)
0x180078066  mov     rbx, rax
0x180078069  test    rax, rax
0x18007806c  jz      short loc_18007807D
0x18007806e  mov     this, rax; hMem
0x180078071  call    cs:__imp_GlobalSize
0x180078078  nop     dword ptr [rax+rax+00h]
0x18007807d  mov     [rdi+8], rbx
0x180078081  mov     this, [rbp+pPersistStg]
0x180078085  mov     dword ptr [rdi], 1
0x18007808b  mov     [rdi+10h], r12
0x18007808f  mov     rax, [this]
0x180078092  mov     rax, [rax+10h]
0x180078096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007809b  mov     ebx, r12d
0x18007809e  jmp     short $exitRtn_16
0x1800780a0  xor     r12d, r12d
0x1800780a3  mov     this, [rbp+pPersistStg]
0x1800780a7  mov     rax, [rbp+hNative]
0x1800780ab  test    rax, rax
0x1800780ae  jz      short loc_1800780C8
0x1800780b0  test    r13d, r13d
0x1800780b3  jz      short loc_1800780C8
0x1800780b5  mov     this, rax; hMem
0x1800780b8  call    cs:__imp_GlobalFree
0x1800780bf  nop     dword ptr [rax+rax+00h]
0x1800780c4  mov     this, [rbp+pPersistStg]
0x1800780c8  test    this, this
0x1800780cb  jz      short loc_1800780D9
0x1800780cd  mov     rax, [this]
0x1800780d0  mov     rax, [rax+10h]
0x1800780d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800780d9  mov     [rdi], r12d
0x1800780dc  mov     [rdi+10h], r12
0x1800780e0  jmp     short $exitRtn_16
0x1800780e2  mov     rax, [r9+18h]
0x1800780e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800780eb  mov     ebx, eax
0x1800780ed  mov     eax, ebx
0x1800780ef  mov     this, [rbp+var_10]
0x1800780f3  xor     this, rsp; StackCookie
0x1800780f6  call    __security_check_cookie
0x1800780fb  add     rsp, 50h
0x1800780ff  pop     r14
0x180078101  pop     r13
0x180078103  pop     r12
0x180078105  pop     rdi
0x180078106  pop     rsi
0x180078107  pop     rbx
0x180078108  pop     rbp
0x180078109  retn
```
