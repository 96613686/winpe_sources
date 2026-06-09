# CDefClient::GetData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x18007ea04`
- end: `0x18007ec1c`
- name: `?GetData@CDefClient@@AEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `536`
- prototype: `__int64 __fastcall(CDefClient *this, tagFORMATETC *pformatetc, tagSTGMEDIUM *pmedium)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007fbfc`
- `0x1800807a4`

## callees

- `0x18002c4e4`
- `0x180052390`
- `0x18007ea04`
- `0x180084d90`
- `0x1800a49e4`
- `0x1800ce010`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x18007ebd0`
- `KERNELBASE!GlobalFree` at `0x18007ebd0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18007eb8f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x18007eb8f`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18007eb39`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18007eb39`
- `api-ms-win-core-com-l2-1-1!GetHGlobalFromILockBytes` at `0x18007eb6a`
- `api-ms-win-core-com-l2-1-1!GetHGlobalFromILockBytes` at `0x18007eb6a`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x18007ea9e`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x18007ea9e`
- `api-ms-win-core-com-l2-1-1!ReadClassStg` at `0x18007eb25`
- `api-ms-win-core-com-l2-1-1!ReadClassStg` at `0x18007eb25`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x18007eabd`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x18007eabd`

## pseudocode

```c
__int64 __fastcall CDefClient::GetData(CDefClient *this, tagFORMATETC *pformatetc, tagSTGMEDIUM *pmedium)
{
  IDataObject *m_lpdataObj; // rcx
  struct IUnknownVtbl *lpVtbl; // r9
  unsigned int v7; // r13d
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
  clsid = 0;
  lpVtbl = m_lpdataObj->lpVtbl;
  if ( pformatetc->cfFormat != g_cfNative )
    return ((unsigned int (*)(void))lpVtbl[1].QueryInterface)();
  v7 = 0;
  ILockBytesOnHGlobal = ((__int64 (__fastcall *)(IDataObject *, GUID *, IPersistStorage **))lpVtbl->QueryInterface)(
                          m_lpdataObj,
                          &IID_IPersistStorage,
                          &pPersistStg);
  if ( !ILockBytesOnHGlobal )
  {
    v9 = pPersistStg;
    if ( !pPersistStg )
      goto $errRtn_96;
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
                v7 = ILockBytesOnHGlobal + 1;
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
$errRtn_96:
  if ( hNative && v7 )
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
0x18007ea04  push    rbp
0x18007ea06  push    rbx
0x18007ea07  push    rsi
0x18007ea08  push    rdi
0x18007ea09  push    r12
0x18007ea0b  push    r13
0x18007ea0d  push    r14
0x18007ea0f  mov     rbp, rsp
0x18007ea12  sub     rsp, 50h
0x18007ea16  mov     rax, cs:__security_cookie
0x18007ea1d  xor     rax, rsp
0x18007ea20  mov     [rbp+var_10], rax
0x18007ea24  movzx   eax, cs:?g_cfNative@@3GA; ushort g_cfNative
0x18007ea2b  xor     r12d, r12d
0x18007ea2e  mov     r14, this
0x18007ea31  mov     this, [this+48h]
0x18007ea35  xorps   xmm0, xmm0
0x18007ea38  mov     [rbp+pPersistStg], r12
0x18007ea3c  mov     rdi, pmedium
0x18007ea3f  mov     [rbp+hNative], r12
0x18007ea43  movups  xmmword ptr [rbp+clsid.Data1], xmm0
0x18007ea47  mov     r9, [this]
0x18007ea4a  cmp     [pformatetc], ax
0x18007ea4d  jnz     loc_18007EBF4
0x18007ea53  mov     rax, [r9]
0x18007ea56  lea     pmedium, [rbp+pPersistStg]
0x18007ea5a  lea     pformatetc, IID_IPersistStorage
0x18007ea61  mov     r13d, r12d
0x18007ea64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ea69  mov     ebx, eax
0x18007ea6b  test    eax, eax
0x18007ea6d  jnz     loc_18007EBBB
0x18007ea73  mov     this, [rbp+pPersistStg]; pPS
0x18007ea77  test    this, this
0x18007ea7a  jz      $errRtn_96
0x18007ea80  lea     rsi, [r14+0D8h]
0x18007ea87  mov     pformatetc, [rsi]; pStg
0x18007ea8a  test    pformatetc, pformatetc
0x18007ea8d  jnz     short loc_18007EAE5
0x18007ea8f  lea     r12, [r14+0D0h]
0x18007ea96  xor     ecx, ecx; hGlobal
0x18007ea98  mov     pmedium, r12; pplkbyt
0x18007ea9b  lea     edx, [rax+1]; fDeleteOnRelease
0x18007ea9e  call    cs:__imp_CreateILockBytesOnHGlobal
0x18007eaa4  mov     ebx, eax
0x18007eaa6  test    eax, eax
0x18007eaa8  jnz     loc_18007EBB8
0x18007eaae  mov     this, [r12]; plkbyt
0x18007eab2  mov     r9, rsi; ppstgOpen
0x18007eab5  xor     r8d, r8d; reserved
0x18007eab8  mov     edx, 1012h; grfMode
0x18007eabd  call    cs:__imp_StgCreateDocfileOnILockBytes
0x18007eac3  xor     r12d, r12d
0x18007eac6  mov     ebx, eax
0x18007eac8  test    eax, eax
0x18007eaca  jnz     loc_18007EBBB
0x18007ead0  mov     pformatetc, [rsi]
0x18007ead3  test    pformatetc, pformatetc
0x18007ead6  jz      loc_18007EBBB
0x18007eadc  mov     this, [rbp+pPersistStg]
0x18007eae0  xor     r8d, r8d
0x18007eae3  jmp     short loc_18007EAEB
0x18007eae5  mov     r8d, 1; fSameAsLoad
0x18007eaeb  mov     dword ptr [r14+0A4h], 1
0x18007eaf6  call    OleSave
0x18007eafb  mov     this, [rbp+pPersistStg]
0x18007eaff  mov     ebx, eax
0x18007eb01  xor     edx, edx
0x18007eb03  mov     rax, [this]
0x18007eb06  mov     rax, [rax+40h]
0x18007eb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb0f  mov     [r14+0A4h], r12d
0x18007eb16  test    ebx, ebx
0x18007eb18  jnz     loc_18007EBBB
0x18007eb1e  mov     this, [rsi]; pStg
0x18007eb21  lea     pformatetc, [rbp+clsid]; pclsid
0x18007eb25  call    cs:__imp_ReadClassStg
0x18007eb2b  mov     ebx, eax
0x18007eb2d  test    eax, eax
0x18007eb2f  jnz     loc_18007EBBB
0x18007eb35  lea     this, [rbp+clsid]; rclsid
0x18007eb39  call    cs:__imp_CoIsOle1Class
0x18007eb3f  lea     pformatetc, [rbp+hNative]; phglobal
0x18007eb43  test    eax, eax
0x18007eb45  jz      short loc_18007EB63
0x18007eb47  mov     this, [rsi]; pstg
0x18007eb4a  lea     r13d, [rbx+1]
0x18007eb4e  call    ?StRead10NativeData@@YAJPEAUIStorage@@PEAPEAX@Z; StRead10NativeData(IStorage *,void * *)
0x18007eb53  mov     ebx, eax
0x18007eb55  test    eax, eax
0x18007eb57  jnz     short loc_18007EBBB
0x18007eb59  mov     rax, [rbp+hNative]
0x18007eb5d  mov     [rdi+8], rax
0x18007eb61  jmp     short loc_18007EB99
0x18007eb63  mov     this, [r14+0D0h]; plkbyt
0x18007eb6a  call    cs:__imp_GetHGlobalFromILockBytes
0x18007eb70  mov     ebx, eax
0x18007eb72  test    eax, eax
0x18007eb74  jnz     short loc_18007EBBB
0x18007eb76  mov     this, [rbp+hNative]; hsrc
0x18007eb7a  mov     edx, 2002h; uiFlags
0x18007eb7f  call    ?UtDupGlobal@@YAPEAXPEAXI@Z; UtDupGlobal(void *,uint)
0x18007eb84  mov     rbx, rax
0x18007eb87  test    rax, rax
0x18007eb8a  jz      short loc_18007EB95
0x18007eb8c  mov     this, rax; hMem
0x18007eb8f  call    cs:__imp_GlobalSize
0x18007eb95  mov     [rdi+8], rbx
0x18007eb99  mov     this, [rbp+pPersistStg]
0x18007eb9d  mov     dword ptr [rdi], 1
0x18007eba3  mov     [rdi+10h], r12
0x18007eba7  mov     rax, [this]
0x18007ebaa  mov     rax, [rax+10h]
0x18007ebae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ebb3  mov     ebx, r12d
0x18007ebb6  jmp     short $exitRtn_17
0x18007ebb8  xor     r12d, r12d
0x18007ebbb  mov     this, [rbp+pPersistStg]
0x18007ebbf  mov     rax, [rbp+hNative]
0x18007ebc3  test    rax, rax
0x18007ebc6  jz      short loc_18007EBDA
0x18007ebc8  test    r13d, r13d
0x18007ebcb  jz      short loc_18007EBDA
0x18007ebcd  mov     this, rax; hMem
0x18007ebd0  call    cs:__imp_GlobalFree
0x18007ebd6  mov     this, [rbp+pPersistStg]
0x18007ebda  test    this, this
0x18007ebdd  jz      short loc_18007EBEB
0x18007ebdf  mov     rax, [this]
0x18007ebe2  mov     rax, [rax+10h]
0x18007ebe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ebeb  mov     [rdi], r12d
0x18007ebee  mov     [rdi+10h], r12
0x18007ebf2  jmp     short $exitRtn_17
0x18007ebf4  mov     rax, [r9+18h]
0x18007ebf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ebfd  mov     ebx, eax
0x18007ebff  mov     eax, ebx
0x18007ec01  mov     this, [rbp+var_10]
0x18007ec05  xor     this, rsp; StackCookie
0x18007ec08  call    __security_check_cookie
0x18007ec0d  add     rsp, 50h
0x18007ec11  pop     r14
0x18007ec13  pop     r13
0x18007ec15  pop     r12
0x18007ec17  pop     rdi
0x18007ec18  pop     rsi
0x18007ec19  pop     rbx
0x18007ec1a  pop     rbp
0x18007ec1b  retn
```
