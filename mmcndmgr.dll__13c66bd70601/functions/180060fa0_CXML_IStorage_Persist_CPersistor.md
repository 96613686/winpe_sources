# CXML_IStorage::Persist(CPersistor &)

- ea: `0x180060fa0`
- end: `0x180061280`
- name: `?Persist@CXML_IStorage@@UEAAXAEAVCPersistor@@@Z`
- size: `736`
- prototype: `void __fastcall(CXML_IStorage *__hidden this, struct CPersistor *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180016bd4`
- `0x180017b60`
- `0x1800234d0`
- `0x180053bb0`
- `0x180056a94`
- `0x180060fa0`
- `0x180126b60`
- `0x1801270ec`
- `0x180134502`
- `0x180134540`
- `0x18013f010`

## import_xrefs

- `mmcbase!?Throw@SC@mmcerror@@QEAAXXZ` at `0x180061078`
- `mmcbase!?Throw@SC@mmcerror@@QEAAXXZ` at `0x1800610cc`
- `mmcbase!?Throw@SC@mmcerror@@QEAAXXZ` at `0x18006111d`
- `mmcbase!?Throw@SC@mmcerror@@QEAAXXZ` at `0x180061172`
- `mmcbase!?Throw@SC@mmcerror@@QEAAXXZ` at `0x1800611ad`
- `mmcbase!?Throw@SC@mmcerror@@QEAAXXZ` at `0x180061208`
- `mmcbase!?Throw@SC@mmcerror@@QEAAXXZ` at `0x180061078`
- `mmcbase!?Throw@SC@mmcerror@@QEAAXXZ` at `0x1800610cc`
- `mmcbase!?Throw@SC@mmcerror@@QEAAXXZ` at `0x18006111d`
- `mmcbase!?Throw@SC@mmcerror@@QEAAXXZ` at `0x180061172`
- `mmcbase!?Throw@SC@mmcerror@@QEAAXXZ` at `0x1800611ad`
- `mmcbase!?Throw@SC@mmcerror@@QEAAXXZ` at `0x180061208`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180060fcf`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180060fcf`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006105e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800610b2`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180061103`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180061193`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800611ee`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18006105e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800610b2`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180061103`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180061193`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x1800611ee`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18006114d`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18006114d`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180060fe2`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180060fe2`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180061069`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1800610bd`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18006110e`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180061163`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18006119e`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1800611f9`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180061069`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1800610bd`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18006110e`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180061163`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18006119e`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1800611f9`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180061158`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18006125b`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180061158`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18006125b`
- `ole32!StgOpenStorageOnILockBytes` at `0x1800610f6`
- `ole32!StgOpenStorageOnILockBytes` at `0x1800610f6`
- `ole32!GetHGlobalFromILockBytes` at `0x180061186`
- `ole32!GetHGlobalFromILockBytes` at `0x180061186`
- `ole32!CreateILockBytesOnHGlobal` at `0x180061051`
- `ole32!CreateILockBytesOnHGlobal` at `0x180061051`

## string_xrefs

- `0x180060fd6`: `CXML_IStorage::Persist`

## pseudocode

```c
void __fastcall CXML_IStorage::Persist(CXML_IStorage *this, struct CPersistor *a2)
{
  ILockBytes **v4; // rdi
  unsigned int ILockBytesOnHGlobal; // eax
  __int64 v6; // rax
  unsigned int v7; // eax
  IStorage **ppstgOpen; // rbx
  unsigned int v9; // eax
  mmcerror::SC *v10; // rax
  unsigned int HGlobalFromILockBytes; // eax
  __int64 v12; // rax
  unsigned int v13; // eax
  _BYTE v14[8]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v15[24]; // [rsp+38h] [rbp-C8h] BYREF
  HGLOBAL phglobal[2]; // [rsp+50h] [rbp-B0h] BYREF
  HGLOBAL hGlobal; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v18; // [rsp+68h] [rbp-98h]
  int v19; // [rsp+70h] [rbp-90h]
  __int64 v20; // [rsp+78h] [rbp-88h] BYREF
  __int64 v21; // [rsp+80h] [rbp-80h]
  int v22; // [rsp+88h] [rbp-78h]
  int v23; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v24; // [rsp+98h] [rbp-68h]
  _BYTE v25[16]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v26; // [rsp+C0h] [rbp-40h]

  mmcerror::SC::SC((mmcerror::SC *)v15, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v15, L"CXML_IStorage::Persist");
  if ( *((_BYTE *)a2 + 24) )
  {
    hGlobal = 0;
    v18 = 0;
    v19 = 0;
    LODWORD(phglobal[0]) = 13;
    phglobal[1] = &hGlobal;
    CPersistor::PersistContents(a2, phglobal);
    v4 = (ILockBytes **)((char *)this + 16);
    _com_ptr_t<_com_IIID<IPropertySheetCallback,&_GUID const IID_IPropertySheetCallback>>::operator=(
      (char *)this + 16,
      0);
    phglobal[0] = (HGLOBAL)(unsigned int)v18;
    ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>((char *)this + 16);
    *((_QWORD *)this + 2) = 0;
    ILockBytesOnHGlobal = CreateILockBytesOnHGlobal(hGlobal, 1, (LPLOCKBYTES *)this + 2);
    mmcerror::SC::operator=(v15, ILockBytesOnHGlobal);
    if ( (unsigned __int8)mmcerror::SC::operator bool(v15) )
      mmcerror::SC::Throw((mmcerror::SC *)v15);
    hGlobal = 0;
    v18 = 0;
    v19 = 0;
    v6 = _com_ptr_t<_com_IIID<IWaitDialog,&_GUID const IID_IWaitDialog>>::operator->((char *)this + 16);
    v7 = (*(__int64 (__fastcall **)(__int64, HGLOBAL))(*(_QWORD *)v6 + 48LL))(v6, phglobal[0]);
    mmcerror::SC::operator=(v15, v7);
    if ( (unsigned __int8)mmcerror::SC::operator bool(v15) )
      mmcerror::SC::Throw((mmcerror::SC *)v15);
    ppstgOpen = (IStorage **)((char *)this + 8);
    ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(ppstgOpen);
    *ppstgOpen = 0;
    v9 = StgOpenStorageOnILockBytes(*v4, 0, 0x12u, 0, 0, ppstgOpen);
    mmcerror::SC::operator=(v15, v9);
    if ( (unsigned __int8)mmcerror::SC::operator bool(v15) )
      mmcerror::SC::Throw((mmcerror::SC *)v15);
    CXMLAutoBinary::~CXMLAutoBinary((CXMLAutoBinary *)&hGlobal);
  }
  else
  {
    v10 = CXML_IStorage::ScInitialize((__int64)this, (mmcerror::SC *)&v23, v14);
    mmcerror::SC::operator=(v15, v10);
    mmcerror::SC::~SC((mmcerror::SC *)&v23);
    if ( (unsigned __int8)mmcerror::SC::operator bool(v15) )
      mmcerror::SC::Throw((mmcerror::SC *)v15);
    phglobal[0] = 0;
    HGlobalFromILockBytes = GetHGlobalFromILockBytes(*((LPLOCKBYTES *)this + 2), phglobal);
    mmcerror::SC::operator=(v15, HGlobalFromILockBytes);
    if ( (unsigned __int8)mmcerror::SC::operator bool(v15) )
      mmcerror::SC::Throw((mmcerror::SC *)v15);
    memset_0(v25, 0, 0x50u);
    v12 = _com_ptr_t<_com_IIID<IWaitDialog,&_GUID const IID_IWaitDialog>>::operator->((char *)this + 16);
    v13 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v12 + 72LL))(v12, v25, 1);
    mmcerror::SC::operator=(v15, v13);
    if ( (unsigned __int8)mmcerror::SC::operator bool(v15) )
      mmcerror::SC::Throw((mmcerror::SC *)v15);
    v20 = 0;
    v21 = 0;
    v22 = 0;
    CXMLBinary::Attach((CXMLBinary *)&v20, phglobal[0], (unsigned int)v26);
    v23 = 13;
    v24 = &v20;
    CPersistor::PersistContents(a2, &v23);
    v20 = 0;
    v21 = 0;
    v22 = 0;
  }
  mmcerror::SC::~SC((mmcerror::SC *)v15);
}

```

## disassembly

```asm
0x180060fa0  mov     [rsp-8+arg_10], rbx
0x180060fa5  push    rbp
0x180060fa6  push    rsi
0x180060fa7  push    rdi
0x180060fa8  lea     rbp, [rsp-10h]
0x180060fad  sub     rsp, 110h
0x180060fb4  mov     rax, cs:__security_cookie
0x180060fbb  xor     rax, rsp
0x180060fbe  mov     [rbp+20h+var_20], rax
0x180060fc2  mov     rdi, rdx
0x180060fc5  mov     rbx, rcx
0x180060fc8  xor     edx, edx
0x180060fca  lea     rcx, [rsp+120h+var_E8]
0x180060fcf  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x180060fd5  nop
0x180060fd6  lea     rdx, aCxmlIstoragePe; "CXML_IStorage::Persist"
0x180060fdd  lea     rcx, [rsp+120h+var_E8]
0x180060fe2  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x180060fe8  xor     esi, esi
0x180060fea  cmp     [rdi+18h], sil
0x180060fee  jz      loc_180061133
0x180060ff4  mov     [rsp+120h+hGlobal], rsi
0x180060ff9  mov     [rsp+120h+var_B8], rsi
0x180060ffe  mov     [rsp+120h+var_B0], esi
0x180061002  mov     dword ptr [rsp+120h+phglobal], 0Dh
0x18006100a  lea     rax, [rsp+120h+hGlobal]
0x18006100f  mov     [rsp+120h+var_C8], rax
0x180061014  lea     rdx, [rsp+120h+phglobal]
0x180061019  mov     rcx, rdi
0x18006101c  call    ?PersistContents@CPersistor@@QEAAXVCXMLValue@@@Z; CPersistor::PersistContents(CXMLValue)
0x180061021  lea     rdi, [rbx+10h]
0x180061025  xor     edx, edx
0x180061027  mov     rcx, rdi
0x18006102a  call    ??4?$_com_ptr_t@V?$_com_IIID@UIPropertySheetCallback@@$1?IID_IPropertySheetCallback@@3U_GUID@@B@@@@QEAAAEAV0@PEAUIPropertySheetCallback@@@Z; _com_ptr_t<_com_IIID<IPropertySheetCallback,&_GUID const IID_IPropertySheetCallback>>::operator=(IPropertySheetCallback *)
0x18006102f  mov     eax, dword ptr [rsp+120h+var_B8]
0x180061033  mov     dword ptr [rsp+120h+phglobal], eax
0x180061037  mov     dword ptr [rsp+120h+phglobal+4], esi
0x18006103b  mov     rcx, rdi
0x18006103e  call    ??1?$CComPtr@UIProvideClassInfo2@@@ATL@@QEAA@XZ; ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(void)
0x180061043  mov     [rdi], rsi
0x180061046  mov     r8, rdi; pplkbyt
0x180061049  lea     edx, [rsi+1]; fDeleteOnRelease
0x18006104c  mov     rcx, [rsp+120h+hGlobal]; hGlobal
0x180061051  call    cs:__imp_CreateILockBytesOnHGlobal
0x180061057  mov     edx, eax
0x180061059  lea     rcx, [rsp+120h+var_E8]
0x18006105e  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180061064  lea     rcx, [rsp+120h+var_E8]
0x180061069  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18006106f  test    al, al
0x180061071  jz      short loc_18006107E
0x180061073  lea     rcx, [rsp+120h+var_E8]
0x180061078  call    cs:__imp_?Throw@SC@mmcerror@@QEAAXXZ; mmcerror::SC::Throw(void)
0x18006107e  mov     [rsp+120h+hGlobal], rsi
0x180061083  mov     [rsp+120h+var_B8], rsi
0x180061088  mov     [rsp+120h+var_B0], esi
0x18006108c  mov     rcx, rdi
0x18006108f  call    ??C?$_com_ptr_t@V?$_com_IIID@UIWaitDialog@@$1?IID_IWaitDialog@@3U_GUID@@B@@@@QEBAPEAUIWaitDialog@@XZ; _com_ptr_t<_com_IIID<IWaitDialog,&_GUID const IID_IWaitDialog>>::operator->(void)
0x180061094  mov     r8, rax
0x180061097  mov     rcx, [rax]
0x18006109a  mov     rax, [rcx+30h]
0x18006109e  mov     rdx, [rsp+120h+phglobal]
0x1800610a3  mov     rcx, r8
0x1800610a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800610ab  mov     edx, eax
0x1800610ad  lea     rcx, [rsp+120h+var_E8]
0x1800610b2  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1800610b8  lea     rcx, [rsp+120h+var_E8]
0x1800610bd  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1800610c3  test    al, al
0x1800610c5  jz      short loc_1800610D2
0x1800610c7  lea     rcx, [rsp+120h+var_E8]
0x1800610cc  call    cs:__imp_?Throw@SC@mmcerror@@QEAAXXZ; mmcerror::SC::Throw(void)
0x1800610d2  add     rbx, 8
0x1800610d6  mov     rcx, rbx
0x1800610d9  call    ??1?$CComPtr@UIProvideClassInfo2@@@ATL@@QEAA@XZ; ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(void)
0x1800610de  mov     [rbx], rsi
0x1800610e1  mov     [rsp+120h+ppstgOpen], rbx; ppstgOpen
0x1800610e6  mov     [rsp+120h+reserved], esi; reserved
0x1800610ea  xor     r9d, r9d; snbExclude
0x1800610ed  xor     edx, edx; pstgPriority
0x1800610ef  lea     r8d, [r9+12h]; grfMode
0x1800610f3  mov     rcx, [rdi]; plkbyt
0x1800610f6  call    cs:__imp_StgOpenStorageOnILockBytes
0x1800610fc  mov     edx, eax
0x1800610fe  lea     rcx, [rsp+120h+var_E8]
0x180061103  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180061109  lea     rcx, [rsp+120h+var_E8]
0x18006110e  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180061114  test    al, al
0x180061116  jz      short loc_180061124
0x180061118  lea     rcx, [rsp+120h+var_E8]
0x18006111d  call    cs:__imp_?Throw@SC@mmcerror@@QEAAXXZ; mmcerror::SC::Throw(void)
0x180061123  nop
0x180061124  lea     rcx, [rsp+120h+hGlobal]; this
0x180061129  call    ??1CXMLAutoBinary@@QEAA@XZ; CXMLAutoBinary::~CXMLAutoBinary(void)
0x18006112e  jmp     loc_180061256
0x180061133  lea     r8, [rsp+120h+var_F0]
0x180061138  lea     rdx, [rbp+20h+var_90]
0x18006113c  mov     rcx, rbx
0x18006113f  call    ?ScInitialize@CXML_IStorage@@QEAA?AVSC@mmcerror@@AEA_N@Z; CXML_IStorage::ScInitialize(bool &)
0x180061144  nop
0x180061145  mov     rdx, rax
0x180061148  lea     rcx, [rsp+120h+var_E8]
0x18006114d  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x180061153  nop
0x180061154  lea     rcx, [rbp+20h+var_90]
0x180061158  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18006115e  lea     rcx, [rsp+120h+var_E8]
0x180061163  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180061169  test    al, al
0x18006116b  jz      short loc_180061178
0x18006116d  lea     rcx, [rsp+120h+var_E8]
0x180061172  call    cs:__imp_?Throw@SC@mmcerror@@QEAAXXZ; mmcerror::SC::Throw(void)
0x180061178  mov     [rsp+120h+phglobal], rsi
0x18006117d  lea     rdx, [rsp+120h+phglobal]; phglobal
0x180061182  mov     rcx, [rbx+10h]; plkbyt
0x180061186  call    cs:__imp_GetHGlobalFromILockBytes
0x18006118c  mov     edx, eax
0x18006118e  lea     rcx, [rsp+120h+var_E8]
0x180061193  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180061199  lea     rcx, [rsp+120h+var_E8]
0x18006119e  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1800611a4  test    al, al
0x1800611a6  jz      short loc_1800611B3
0x1800611a8  lea     rcx, [rsp+120h+var_E8]
0x1800611ad  call    cs:__imp_?Throw@SC@mmcerror@@QEAAXXZ; mmcerror::SC::Throw(void)
0x1800611b3  xor     edx, edx; Val
0x1800611b5  lea     r8d, [rdx+50h]; Size
0x1800611b9  lea     rcx, [rbp+20h+var_70]; void *
0x1800611bd  call    memset_0
0x1800611c2  lea     rcx, [rbx+10h]
0x1800611c6  call    ??C?$_com_ptr_t@V?$_com_IIID@UIWaitDialog@@$1?IID_IWaitDialog@@3U_GUID@@B@@@@QEBAPEAUIWaitDialog@@XZ; _com_ptr_t<_com_IIID<IWaitDialog,&_GUID const IID_IWaitDialog>>::operator->(void)
0x1800611cb  mov     r9, rax
0x1800611ce  mov     rcx, [rax]
0x1800611d1  mov     rax, [rcx+48h]
0x1800611d5  mov     r8d, 1
0x1800611db  lea     rdx, [rbp+20h+var_70]
0x1800611df  mov     rcx, r9
0x1800611e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800611e7  mov     edx, eax
0x1800611e9  lea     rcx, [rsp+120h+var_E8]
0x1800611ee  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x1800611f4  lea     rcx, [rsp+120h+var_E8]
0x1800611f9  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1800611ff  test    al, al
0x180061201  jz      short loc_18006120E
0x180061203  lea     rcx, [rsp+120h+var_E8]
0x180061208  call    cs:__imp_?Throw@SC@mmcerror@@QEAAXXZ; mmcerror::SC::Throw(void)
0x18006120e  mov     [rsp+120h+var_A8], rsi
0x180061213  mov     [rbp+20h+var_A0], rsi
0x180061217  mov     [rbp+20h+var_98], esi
0x18006121a  mov     r8d, dword ptr [rbp+20h+var_60]; unsigned __int64
0x18006121e  mov     rdx, [rsp+120h+phglobal]; void *
0x180061223  lea     rcx, [rsp+120h+var_A8]; this
0x180061228  call    ?Attach@CXMLBinary@@QEAAXPEAX_K@Z; CXMLBinary::Attach(void *,unsigned __int64)
0x18006122d  mov     [rbp+20h+var_90], 0Dh
0x180061234  lea     rax, [rsp+120h+var_A8]
0x180061239  mov     [rbp+20h+var_88], rax
0x18006123d  lea     rdx, [rbp+20h+var_90]
0x180061241  mov     rcx, rdi
0x180061244  call    ?PersistContents@CPersistor@@QEAAXVCXMLValue@@@Z; CPersistor::PersistContents(CXMLValue)
0x180061249  nop
0x18006124a  mov     [rsp+120h+var_A8], rsi
0x18006124f  mov     [rbp+20h+var_A0], rsi
0x180061253  mov     [rbp+20h+var_98], esi
0x180061256  lea     rcx, [rsp+120h+var_E8]
0x18006125b  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180061261  mov     rcx, [rbp+20h+var_20]
0x180061265  xor     rcx, rsp; StackCookie
0x180061268  call    __security_check_cookie
0x18006126d  mov     rbx, [rsp+120h+arg_10]
0x180061275  add     rsp, 110h
0x18006127c  pop     rdi
0x18006127d  pop     rsi
0x18006127e  pop     rbp
0x18006127f  retn
```
