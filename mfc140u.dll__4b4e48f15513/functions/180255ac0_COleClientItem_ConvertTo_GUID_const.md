# COleClientItem::ConvertTo(_GUID const &)

- ea: `0x180255ac0`
- end: `0x180255c84`
- name: `?ConvertTo@COleClientItem@@UEAAHAEBU_GUID@@@Z`
- size: `452`
- prototype: `int __fastcall(COleClientItem *this, const _GUID *clsidNew)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18024f610`
- `0x18024fb20`
- `0x180252d38`
- `0x180255ac0`
- `0x180278484`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180255bb4`
- `ole32!CoTaskMemFree` at `0x180255bbe`
- `ole32!CoTaskMemFree` at `0x180255bb4`
- `ole32!CoTaskMemFree` at `0x180255bbe`
- `ole32!SetConvertStg` at `0x180255b7b`
- `ole32!SetConvertStg` at `0x180255b7b`
- `ole32!WriteFmtUserTypeStg` at `0x180255b6b`
- `ole32!WriteFmtUserTypeStg` at `0x180255b9f`
- `ole32!WriteFmtUserTypeStg` at `0x180255b6b`
- `ole32!WriteFmtUserTypeStg` at `0x180255b9f`
- `ole32!WriteClassStg` at `0x180255b54`
- `ole32!WriteClassStg` at `0x180255b8e`
- `ole32!WriteClassStg` at `0x180255b54`
- `ole32!WriteClassStg` at `0x180255b8e`
- `ole32!OleRegGetUserType` at `0x180255b3c`
- `ole32!OleRegGetUserType` at `0x180255b3c`
- `ole32!ReadClassStg` at `0x180255afd`
- `ole32!ReadClassStg` at `0x180255afd`
- `ole32!ReadFmtUserTypeStg` at `0x180255b1f`
- `ole32!ReadFmtUserTypeStg` at `0x180255b1f`

## pseudocode

```c
__int64 __fastcall COleClientItem::ConvertTo(COleClientItem *this, const _GUID *clsidNew)
{
  IStorage *m_lpStorage; // rsi
  const _GUID *v5; // rdx
  HRESULT v6; // ebx
  IOleObject *m_lpObject; // r14
  IViewObject2 *m_lpViewObject; // r15
  unsigned int m_dwConnection; // r12d
  int (__fastcall *FinishCreate)(COleClientItem *, int); // rbx
  IStorage *v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // ebx
  ClassesAllowedInStorage cclsidAllowed; // [rsp+20h] [rbp-40h]
  unsigned int pStg; // [rsp+28h] [rbp-38h]
  CLIPFORMAT pcf[2]; // [rsp+30h] [rbp-30h] BYREF
  _WORD v18[2]; // [rsp+34h] [rbp-2Ch] BYREF
  IViewObject2 *lpViewObject; // [rsp+38h] [rbp-28h] BYREF
  IOleObject *lpObject; // [rsp+40h] [rbp-20h] BYREF
  CLSID pclsid; // [rsp+48h] [rbp-18h] BYREF

  COleClientItem::Close(this, OLECLOSE_SAVEIFDIRTY);
  m_lpStorage = this->m_lpStorage;
  v6 = ReadClassStg(m_lpStorage, &pclsid);
  if ( !v6 )
  {
    lpObject = 0;
    ReadFmtUserTypeStg(m_lpStorage, pcf, (LPOLESTR *)&lpObject);
    v18[0] = 0;
    lpViewObject = 0;
    if ( OleRegGetUserType(clsidNew, 1u, (LPOLESTR *)&lpViewObject) )
      lpViewObject = (IViewObject2 *)v18;
    v6 = WriteClassStg(m_lpStorage, clsidNew);
    if ( !v6
      && (WriteFmtUserTypeStg(m_lpStorage, pcf[0], (LPOLESTR)lpViewObject) || (v6 = SetConvertStg(m_lpStorage, 1)) != 0) )
    {
      WriteClassStg(m_lpStorage, &pclsid);
      v6 = WriteFmtUserTypeStg(m_lpStorage, pcf[0], (LPOLESTR)lpObject);
    }
    if ( lpViewObject != (IViewObject2 *)v18 )
      CoTaskMemFree(lpViewObject);
    CoTaskMemFree(lpObject);
  }
  this->m_scLast = v6;
  if ( v6 < 0 )
    return 0;
  m_lpObject = this->m_lpObject;
  m_lpViewObject = this->m_lpViewObject;
  m_dwConnection = this->m_dwConnection;
  pStg = this->m_nClassesAllowedInStorage;
  FinishCreate = this->FinishCreate;
  cclsidAllowed.rgclsidAllowed = (const _GUID *)this->m_ClassesAllowedInStorage;
  v12 = this->m_lpStorage;
  lpObject = m_lpObject;
  lpViewObject = m_lpViewObject;
  this->m_lpObject = 0;
  this->m_lpViewObject = 0;
  this->m_dwConnection = 0;
  v13 = AfxInternalOleLoadFromStorage(v12, v5, 0, (void **)&this->m_lpObject, cclsidAllowed, pStg);
  v14 = FinishCreate(this, v13);
  if ( v14 )
  {
    _AfxRelease(&lpObject);
    _AfxRelease(&lpViewObject);
  }
  else
  {
    this->m_lpObject = m_lpObject;
    this->m_lpViewObject = m_lpViewObject;
    this->m_dwConnection = m_dwConnection;
    COleClientItem::UpdateItemType(this);
  }
  return v14;
}

```

## disassembly

```asm
0x180255ac0  mov     [rsp-38h+arg_10], rbx
0x180255ac5  push    rbp
0x180255ac6  push    rsi
0x180255ac7  push    rdi
0x180255ac8  push    r12
0x180255aca  push    r13
0x180255acc  push    r14
0x180255ace  push    r15
0x180255ad0  mov     rbp, rsp
0x180255ad3  sub     rsp, 60h
0x180255ad7  mov     rax, cs:__security_cookie
0x180255ade  xor     rax, rsp
0x180255ae1  mov     [rbp+var_8], rax
0x180255ae5  mov     r14, clsidNew
0x180255ae8  mov     rdi, this
0x180255aeb  xor     edx, edx; dwCloseOption
0x180255aed  call    ?Close@COleClientItem@@QEAAXW4tagOLECLOSE@@@Z; COleClientItem::Close(tagOLECLOSE)
0x180255af2  mov     rsi, [rdi+68h]
0x180255af6  lea     clsidNew, [rbp+pclsid]; pclsid
0x180255afa  mov     this, rsi; pStg
0x180255afd  call    cs:__imp_ReadClassStg
0x180255b03  xor     r13d, r13d
0x180255b06  mov     ebx, eax
0x180255b08  test    eax, eax
0x180255b0a  jnz     loc_180255BC4
0x180255b10  lea     r8, [rbp+lpObject]; lplpszUserType
0x180255b14  mov     [rbp+lpObject], r13
0x180255b18  lea     clsidNew, [rbp+pcf]; pcf
0x180255b1c  mov     this, rsi; pstg
0x180255b1f  call    cs:__imp_ReadFmtUserTypeStg
0x180255b25  lea     r15d, [rbx+1]
0x180255b29  mov     [rbp+var_2C], r13w
0x180255b2e  mov     edx, r15d; dwFormOfType
0x180255b31  mov     [rbp+lpViewObject], r13
0x180255b35  lea     r8, [rbp+lpViewObject]; pszUserType
0x180255b39  mov     this, r14; clsid
0x180255b3c  call    cs:__imp_OleRegGetUserType
0x180255b42  test    eax, eax
0x180255b44  jz      short loc_180255B4E
0x180255b46  lea     rax, [rbp+var_2C]
0x180255b4a  mov     [rbp+lpViewObject], rax
0x180255b4e  mov     clsidNew, r14; rclsid
0x180255b51  mov     this, rsi; pStg
0x180255b54  call    cs:__imp_WriteClassStg
0x180255b5a  mov     ebx, eax
0x180255b5c  test    eax, eax
0x180255b5e  jnz     short loc_180255BA7
0x180255b60  mov     r8, [rbp+lpViewObject]; lpszUserType
0x180255b64  mov     this, rsi; pstg
0x180255b67  movzx   edx, [rbp+pcf]; cf
0x180255b6b  call    cs:__imp_WriteFmtUserTypeStg
0x180255b71  test    eax, eax
0x180255b73  jnz     short loc_180255B87
0x180255b75  mov     edx, r15d; fConvert
0x180255b78  mov     this, rsi; pStg
0x180255b7b  call    cs:__imp_SetConvertStg
0x180255b81  mov     ebx, eax
0x180255b83  test    eax, eax
0x180255b85  jz      short loc_180255BA7
0x180255b87  lea     clsidNew, [rbp+pclsid]; rclsid
0x180255b8b  mov     this, rsi; pStg
0x180255b8e  call    cs:__imp_WriteClassStg
0x180255b94  mov     r8, [rbp+lpObject]; lpszUserType
0x180255b98  mov     this, rsi; pstg
0x180255b9b  movzx   edx, [rbp+pcf]; cf
0x180255b9f  call    cs:__imp_WriteFmtUserTypeStg
0x180255ba5  mov     ebx, eax
0x180255ba7  mov     this, [rbp+lpViewObject]; pv
0x180255bab  lea     rax, [rbp+var_2C]
0x180255baf  cmp     this, rax
0x180255bb2  jz      short loc_180255BBA
0x180255bb4  call    cs:__imp_CoTaskMemFree
0x180255bba  mov     this, [rbp+lpObject]; pv
0x180255bbe  call    cs:__imp_CoTaskMemFree
0x180255bc4  mov     [rdi+60h], ebx
0x180255bc7  test    ebx, ebx
0x180255bc9  jns     short loc_180255BD2
0x180255bcb  xor     eax, eax
0x180255bcd  jmp     loc_180255C60
0x180255bd2  mov     ecx, [rdi+0D0h]
0x180255bd8  lea     rsi, [rdi+48h]
0x180255bdc  mov     r14, [rsi]
0x180255bdf  mov     r9, rsi; rgclsidAllowed
0x180255be2  mov     r15, [rdi+50h]
0x180255be6  xor     r8d, r8d; ppvObj
0x180255be9  mov     rax, [rdi]
0x180255bec  mov     r12d, [rdi+78h]
0x180255bf0  mov     [rsp+60h+pStg], ecx; pStg
0x180255bf4  mov     this, [rdi+0C8h]
0x180255bfb  mov     rbx, [rax+198h]
0x180255c02  mov     qword ptr [rsp+60h+cclsidAllowed], this; cclsidAllowed
0x180255c07  mov     this, [rdi+68h]; pStg
0x180255c0b  mov     [rbp+lpObject], r14
0x180255c0f  mov     [rbp+lpViewObject], r15
0x180255c13  mov     [rsi], r13
0x180255c16  mov     [rdi+50h], r13
0x180255c1a  mov     [rdi+78h], r13d
0x180255c1e  call    ?AfxInternalOleLoadFromStorage@@YAJPEAUIStorage@@AEBU_GUID@@PEAUIOleClientSite@@PEAPEAXTClassesAllowedInStorage@@K@Z; AfxInternalOleLoadFromStorage(IStorage *,_GUID const &,IOleClientSite *,void * *,ClassesAllowedInStorage,ulong)
0x180255c23  mov     edx, eax
0x180255c25  mov     this, rdi
0x180255c28  mov     rax, rbx
0x180255c2b  call    cs:__guard_dispatch_icall_fptr
0x180255c31  mov     ebx, eax
0x180255c33  test    eax, eax
0x180255c35  jz      short loc_180255C4B
0x180255c37  lea     this, [rbp+lpObject]; lplpUnknown
0x180255c3b  call    ?_AfxRelease@@YAKPEAPEAUIUnknown@@@Z; _AfxRelease(IUnknown * *)
0x180255c40  lea     this, [rbp+lpViewObject]; lplpUnknown
0x180255c44  call    ?_AfxRelease@@YAKPEAPEAUIUnknown@@@Z; _AfxRelease(IUnknown * *)
0x180255c49  jmp     short loc_180255C5E
0x180255c4b  mov     this, rdi; this
0x180255c4e  mov     [rsi], r14
0x180255c51  mov     [rdi+50h], r15
0x180255c55  mov     [rdi+78h], r12d
0x180255c59  call    ?UpdateItemType@COleClientItem@@QEAAXXZ; COleClientItem::UpdateItemType(void)
0x180255c5e  mov     eax, ebx
0x180255c60  mov     this, [rbp+var_8]
0x180255c64  xor     this, rsp; StackCookie
0x180255c67  call    __security_check_cookie
0x180255c6c  mov     rbx, [rsp+60h+arg_10]
0x180255c74  add     rsp, 60h
0x180255c78  pop     r15
0x180255c7a  pop     r14
0x180255c7c  pop     r13
0x180255c7e  pop     r12
0x180255c80  pop     rdi
0x180255c81  pop     rsi
0x180255c82  pop     rbp
0x180255c83  retn
```
