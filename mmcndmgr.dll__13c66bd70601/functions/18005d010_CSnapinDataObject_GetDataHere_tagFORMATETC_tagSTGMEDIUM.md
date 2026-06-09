# CSnapinDataObject::GetDataHere(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x18005d010`
- end: `0x18005d300`
- name: `?GetDataHere@CSnapinDataObject@@UEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `752`
- prototype: `__int64 __fastcall(CSnapinDataObject *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180016bd4`
- `0x180017b60`
- `0x18003a698`
- `0x18005d010`
- `0x18005d308`
- `0x1800743b4`
- `0x18012a0f8`
- `0x1801344ea`
- `0x18013f010`

## import_xrefs

- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18005d118`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18005d2cd`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18005d118`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x18005d2cd`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18005d034`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x18005d034`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18005d10f`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18005d162`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18005d2c4`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18005d10f`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18005d162`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x18005d2c4`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18005d069`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x18005d069`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18005d046`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x18005d046`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005d07e`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005d16c`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005d07e`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x18005d16c`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005d074`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005d2e3`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005d074`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x18005d2e3`
- `USER32!RegisterClipboardFormatW` at `0x18005d0a1`
- `USER32!RegisterClipboardFormatW` at `0x18005d0b4`
- `USER32!RegisterClipboardFormatW` at `0x18005d0c7`
- `USER32!RegisterClipboardFormatW` at `0x18005d0da`
- `USER32!RegisterClipboardFormatW` at `0x18005d0ed`
- `USER32!RegisterClipboardFormatW` at `0x18005d0a1`
- `USER32!RegisterClipboardFormatW` at `0x18005d0b4`
- `USER32!RegisterClipboardFormatW` at `0x18005d0c7`
- `USER32!RegisterClipboardFormatW` at `0x18005d0da`
- `USER32!RegisterClipboardFormatW` at `0x18005d0ed`
- `ole32!CreateStreamOnHGlobal` at `0x18005d156`
- `ole32!CreateStreamOnHGlobal` at `0x18005d156`

## string_xrefs

- `0x18005d0d3`: `CCF_SNAPIN_CLASSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSnapinDataObject::GetDataHere(
        CSnapinDataObject *this,
        struct tagFORMATETC *a2,
        struct tagSTGMEDIUM *a3)
{
  __int64 v6; // rax
  mmcerror::SC *v7; // rcx
  unsigned int v8; // ebx
  int cfFormat; // esi
  HBITMAP hBitmap; // rbx
  unsigned int v11; // eax
  CSnapinDataObject *v12; // rcx
  unsigned __int16 *v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rdx
  const unsigned __int16 *v16; // r8
  __int64 v17; // rax
  mmcerror::SC *v18; // rcx
  LPSTREAM ppstm; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v21[24]; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v22[32]; // [rsp+50h] [rbp-20h] BYREF
  int v23; // [rsp+A8h] [rbp+38h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v21, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v21, L"CSnapinDataObject::GetDataHere");
  v6 = ScCheckPointers(v22, a2, a3, 2147942487LL);
  mmcerror::SC::operator=(v21, v6);
  mmcerror::SC::~SC((mmcerror::SC *)v22);
  if ( (unsigned __int8)mmcerror::SC::operator bool(v21) )
  {
    v7 = (mmcerror::SC *)v21;
LABEL_7:
    v8 = mmcerror::SC::ToHr(v7);
    goto LABEL_30;
  }
  if ( !byte_1801C75FC )
  {
    CSnapinDataObject::s_cfNodeType = RegisterClipboardFormatW(L"CCF_NODETYPE");
    CSnapinDataObject::s_cfNodeTypeString = RegisterClipboardFormatW(L"CCF_SZNODETYPE");
    CSnapinDataObject::s_cfDisplayName = RegisterClipboardFormatW(L"CCF_DISPLAY_NAME");
    CSnapinDataObject::s_cfCoClass = RegisterClipboardFormatW(L"CCF_SNAPIN_CLASSID");
    CSnapinDataObject::s_cfSnapinPreloads = RegisterClipboardFormatW(L"CCF_SNAPIN_PRELOADS");
    byte_1801C75FC = 1;
  }
  if ( a2->tymed != 1 )
  {
    v7 = (mmcerror::SC *)mmcerror::SC::operator=(v21, 2147745897LL);
    goto LABEL_7;
  }
  cfFormat = a2->cfFormat;
  ppstm = 0;
  hBitmap = a3->hBitmap;
  a3->pUnkForRelease = 0;
  ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(&ppstm);
  ppstm = 0;
  v11 = CreateStreamOnHGlobal(hBitmap, 0, &ppstm);
  mmcerror::SC::operator=(v21, v11);
  if ( (unsigned __int8)mmcerror::SC::operator bool(v21) )
    goto LABEL_27;
  v13 = (unsigned __int16 *)_RTDynamicCast_0(
                              *((_QWORD *)this + 10),
                              0,
                              &IComponentData `RTTI Type Descriptor',
                              &CSnapinComponentDataImpl `RTTI Type Descriptor',
                              0);
  if ( v13 )
  {
    if ( cfFormat == CSnapinDataObject::s_cfNodeType )
    {
      v14 = _com_ptr_t<_com_IIID<IWaitDialog,&_GUID const IID_IWaitDialog>>::operator->(&ppstm);
      v15 = *(_QWORD *)((*(__int64 (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v13 + 80LL))(v13) + 48);
    }
    else
    {
      if ( cfFormat != CSnapinDataObject::s_cfCoClass )
      {
        if ( cfFormat == CSnapinDataObject::s_cfNodeTypeString )
        {
          v16 = *(const unsigned __int16 **)((*(__int64 (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v13 + 80LL))(v13)
                                           + 56);
        }
        else
        {
          if ( cfFormat != CSnapinDataObject::s_cfDisplayName )
          {
            if ( cfFormat != CSnapinDataObject::s_cfSnapinPreloads )
            {
              v18 = (mmcerror::SC *)mmcerror::SC::operator=(v21, 2147745898LL);
              goto LABEL_29;
            }
            v23 = 1;
            v17 = _com_ptr_t<_com_IIID<IWaitDialog,&_GUID const IID_IWaitDialog>>::operator->(&ppstm);
            (*(void (__fastcall **)(__int64, int *, __int64))(*(_QWORD *)v17 + 32LL))(v17, &v23, 4);
LABEL_27:
            v18 = (mmcerror::SC *)v21;
LABEL_29:
            v8 = mmcerror::SC::ToHr(v18);
            ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(&ppstm);
            goto LABEL_30;
          }
          v16 = v13 + 80;
          if ( *((_QWORD *)v13 + 23) >= 8u )
            v16 = *(const unsigned __int16 **)v16;
        }
        CSnapinDataObject::WriteString(v12, ppstm, v16);
        goto LABEL_27;
      }
      v14 = _com_ptr_t<_com_IIID<IWaitDialog,&_GUID const IID_IWaitDialog>>::operator->(&ppstm);
      v15 = *(_QWORD *)((*(__int64 (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v13 + 80LL))(v13) + 32);
    }
    WriteScalar__GUID_(v14, v15);
    goto LABEL_27;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_92046b9d13f4309e06923444decfc0b8_Traceguids);
  ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(&ppstm);
  v8 = -2147418113;
LABEL_30:
  mmcerror::SC::~SC((mmcerror::SC *)v21);
  return v8;
}

```

## disassembly

```asm
0x18005d010  mov     [rsp-18h+arg_0], rbx
0x18005d015  mov     [rsp-18h+arg_8], rsi
0x18005d01a  push    rbp
0x18005d01b  push    rdi
0x18005d01c  push    r14
0x18005d01e  mov     rbp, rsp
0x18005d021  sub     rsp, 70h
0x18005d025  mov     rdi, r8
0x18005d028  mov     rbx, rdx
0x18005d02b  mov     r14, rcx
0x18005d02e  xor     edx, edx
0x18005d030  lea     rcx, [rbp+var_38]
0x18005d034  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x18005d03a  nop
0x18005d03b  lea     rdx, aCsnapindataobj; "CSnapinDataObject::GetDataHere"
0x18005d042  lea     rcx, [rbp+var_38]
0x18005d046  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x18005d04c  mov     r9d, 80070057h
0x18005d052  mov     r8, rdi
0x18005d055  mov     rdx, rbx
0x18005d058  lea     rcx, [rbp+var_20]
0x18005d05c  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBX0J@Z; ScCheckPointers(void const *,void const *,long)
0x18005d061  nop
0x18005d062  mov     rdx, rax
0x18005d065  lea     rcx, [rbp+var_38]
0x18005d069  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x18005d06f  nop
0x18005d070  lea     rcx, [rbp+var_20]
0x18005d074  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18005d07a  lea     rcx, [rbp+var_38]
0x18005d07e  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18005d084  test    al, al
0x18005d086  jz      short loc_18005D091
0x18005d088  lea     rcx, [rbp+var_38]
0x18005d08c  jmp     loc_18005D118
0x18005d091  cmp     cs:byte_1801C75FC, 0
0x18005d098  jnz     short loc_18005D100
0x18005d09a  lea     rcx, szFormat; "CCF_NODETYPE"
0x18005d0a1  call    cs:__imp_RegisterClipboardFormatW
0x18005d0a7  mov     cs:?s_cfNodeType@CSnapinDataObject@@0IA, eax; uint CSnapinDataObject::s_cfNodeType
0x18005d0ad  lea     rcx, aCcfSznodetype; "CCF_SZNODETYPE"
0x18005d0b4  call    cs:__imp_RegisterClipboardFormatW
0x18005d0ba  mov     cs:?s_cfNodeTypeString@CSnapinDataObject@@0IA, eax; uint CSnapinDataObject::s_cfNodeTypeString
0x18005d0c0  lea     rcx, aCcfDisplayName; "CCF_DISPLAY_NAME"
0x18005d0c7  call    cs:__imp_RegisterClipboardFormatW
0x18005d0cd  mov     cs:?s_cfDisplayName@CSnapinDataObject@@0IA, eax; uint CSnapinDataObject::s_cfDisplayName
0x18005d0d3  lea     rcx, aCcfSnapinClass_0; "CCF_SNAPIN_CLASSID"
0x18005d0da  call    cs:__imp_RegisterClipboardFormatW
0x18005d0e0  mov     cs:?s_cfCoClass@CSnapinDataObject@@0IA, eax; uint CSnapinDataObject::s_cfCoClass
0x18005d0e6  lea     rcx, aCcfSnapinPrelo; "CCF_SNAPIN_PRELOADS"
0x18005d0ed  call    cs:__imp_RegisterClipboardFormatW
0x18005d0f3  mov     cs:?s_cfSnapinPreloads@CSnapinDataObject@@0IA, eax; uint CSnapinDataObject::s_cfSnapinPreloads
0x18005d0f9  mov     cs:byte_1801C75FC, 1
0x18005d100  cmp     dword ptr [rbx+18h], 1
0x18005d104  jz      short loc_18005D125
0x18005d106  mov     edx, 80040069h
0x18005d10b  lea     rcx, [rbp+var_38]
0x18005d10f  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18005d115  mov     rcx, rax
0x18005d118  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x18005d11e  mov     ebx, eax
0x18005d120  jmp     loc_18005D2DF
0x18005d125  movzx   esi, word ptr [rbx]
0x18005d128  mov     [rbp+ppstm], 0
0x18005d130  mov     rbx, [rdi+8]
0x18005d134  mov     qword ptr [rdi+10h], 0
0x18005d13c  lea     rcx, [rbp+ppstm]
0x18005d140  call    ??1?$CComPtr@UIProvideClassInfo2@@@ATL@@QEAA@XZ; ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(void)
0x18005d145  mov     [rbp+ppstm], 0
0x18005d14d  lea     r8, [rbp+ppstm]; ppstm
0x18005d151  xor     edx, edx; fDeleteOnRelease
0x18005d153  mov     rcx, rbx; hGlobal
0x18005d156  call    cs:__imp_CreateStreamOnHGlobal
0x18005d15c  mov     edx, eax
0x18005d15e  lea     rcx, [rbp+var_38]
0x18005d162  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18005d168  lea     rcx, [rbp+var_38]
0x18005d16c  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x18005d172  test    al, al
0x18005d174  jnz     loc_18005D2B5
0x18005d17a  mov     [rsp+70h+var_50], 0
0x18005d182  lea     r9, ??_R0?AVCSnapinComponentDataImpl@@@8; CSnapinComponentDataImpl `RTTI Type Descriptor'
0x18005d189  lea     r8, ??_R0?AUIComponentData@@@8; IComponentData `RTTI Type Descriptor'
0x18005d190  xor     edx, edx
0x18005d192  mov     rcx, [r14+50h]
0x18005d196  call    __RTDynamicCast_0
0x18005d19b  mov     rdi, rax
0x18005d19e  test    rax, rax
0x18005d1a1  jnz     short loc_18005D1E3
0x18005d1a3  lea     rax, WPP_GLOBAL_Control
0x18005d1aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d1b1  cmp     rcx, rax
0x18005d1b4  jz      short loc_18005D1D0
0x18005d1b6  cmp     byte ptr [rcx+19h], 2
0x18005d1ba  jb      short loc_18005D1D0
0x18005d1bc  lea     edx, [rdi+0Dh]
0x18005d1bf  lea     r8, WPP_92046b9d13f4309e06923444decfc0b8_Traceguids
0x18005d1c6  mov     rcx, [rcx+10h]
0x18005d1ca  call    WPP_SF_
0x18005d1cf  nop
0x18005d1d0  lea     rcx, [rbp+ppstm]
0x18005d1d4  call    ??1?$CComPtr@UIProvideClassInfo2@@@ATL@@QEAA@XZ; ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(void)
0x18005d1d9  mov     ebx, 8000FFFFh
0x18005d1de  jmp     loc_18005D2DF
0x18005d1e3  mov     eax, esi
0x18005d1e5  cmp     esi, cs:?s_cfNodeType@CSnapinDataObject@@0IA; uint CSnapinDataObject::s_cfNodeType
0x18005d1eb  jnz     short loc_18005D20E
0x18005d1ed  lea     rcx, [rbp+ppstm]
0x18005d1f1  call    ??C?$_com_ptr_t@V?$_com_IIID@UIWaitDialog@@$1?IID_IWaitDialog@@3U_GUID@@B@@@@QEBAPEAUIWaitDialog@@XZ; _com_ptr_t<_com_IIID<IWaitDialog,&_GUID const IID_IWaitDialog>>::operator->(void)
0x18005d1f6  mov     rbx, rax
0x18005d1f9  mov     rcx, [rdi]
0x18005d1fc  mov     rax, [rcx+50h]
0x18005d200  mov     rcx, rdi
0x18005d203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d208  mov     rdx, [rax+30h]
0x18005d20c  jmp     short loc_18005D235
0x18005d20e  cmp     eax, cs:?s_cfCoClass@CSnapinDataObject@@0IA; uint CSnapinDataObject::s_cfCoClass
0x18005d214  jnz     short loc_18005D23F
0x18005d216  lea     rcx, [rbp+ppstm]
0x18005d21a  call    ??C?$_com_ptr_t@V?$_com_IIID@UIWaitDialog@@$1?IID_IWaitDialog@@3U_GUID@@B@@@@QEBAPEAUIWaitDialog@@XZ; _com_ptr_t<_com_IIID<IWaitDialog,&_GUID const IID_IWaitDialog>>::operator->(void)
0x18005d21f  mov     rbx, rax
0x18005d222  mov     rcx, [rdi]
0x18005d225  mov     rax, [rcx+50h]
0x18005d229  mov     rcx, rdi
0x18005d22c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d231  mov     rdx, [rax+20h]
0x18005d235  mov     rcx, rbx
0x18005d238  call    WriteScalar__GUID_
0x18005d23d  jmp     short loc_18005D2B5
0x18005d23f  cmp     eax, cs:?s_cfNodeTypeString@CSnapinDataObject@@0IA; uint CSnapinDataObject::s_cfNodeTypeString
0x18005d245  jnz     short loc_18005D25C
0x18005d247  mov     rax, [rdi]
0x18005d24a  mov     rcx, rdi
0x18005d24d  mov     rax, [rax+50h]
0x18005d251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d256  mov     r8, [rax+38h]
0x18005d25a  jmp     short loc_18005D275
0x18005d25c  cmp     eax, cs:?s_cfDisplayName@CSnapinDataObject@@0IA; uint CSnapinDataObject::s_cfDisplayName
0x18005d262  jnz     short loc_18005D280
0x18005d264  lea     r8, [rdi+0A0h]
0x18005d26b  cmp     qword ptr [r8+18h], 8
0x18005d270  jb      short loc_18005D275
0x18005d272  mov     r8, [r8]; unsigned __int16 *
0x18005d275  mov     rdx, [rbp+ppstm]; struct IStream *
0x18005d279  call    ?WriteString@CSnapinDataObject@@AEAAJPEAUIStream@@PEBG@Z; CSnapinDataObject::WriteString(IStream *,ushort const *)
0x18005d27e  jmp     short loc_18005D2B5
0x18005d280  cmp     eax, cs:?s_cfSnapinPreloads@CSnapinDataObject@@0IA; uint CSnapinDataObject::s_cfSnapinPreloads
0x18005d286  jnz     short loc_18005D2BB
0x18005d288  mov     [rbp+arg_18], 1
0x18005d28f  lea     rcx, [rbp+ppstm]
0x18005d293  call    ??C?$_com_ptr_t@V?$_com_IIID@UIWaitDialog@@$1?IID_IWaitDialog@@3U_GUID@@B@@@@QEBAPEAUIWaitDialog@@XZ; _com_ptr_t<_com_IIID<IWaitDialog,&_GUID const IID_IWaitDialog>>::operator->(void)
0x18005d298  mov     r10, rax
0x18005d29b  mov     rcx, [rax]
0x18005d29e  mov     rax, [rcx+20h]
0x18005d2a2  xor     r9d, r9d
0x18005d2a5  lea     r8d, [r9+4]
0x18005d2a9  lea     rdx, [rbp+arg_18]
0x18005d2ad  mov     rcx, r10
0x18005d2b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d2b5  lea     rcx, [rbp+var_38]
0x18005d2b9  jmp     short loc_18005D2CD
0x18005d2bb  mov     edx, 8004006Ah
0x18005d2c0  lea     rcx, [rbp+var_38]
0x18005d2c4  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x18005d2ca  mov     rcx, rax
0x18005d2cd  call    cs:__imp_?ToHr@SC@mmcerror@@QEBAJXZ; mmcerror::SC::ToHr(void)
0x18005d2d3  mov     ebx, eax
0x18005d2d5  lea     rcx, [rbp+ppstm]
0x18005d2d9  call    ??1?$CComPtr@UIProvideClassInfo2@@@ATL@@QEAA@XZ; ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(void)
0x18005d2de  nop
0x18005d2df  lea     rcx, [rbp+var_38]
0x18005d2e3  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18005d2e9  mov     eax, ebx
0x18005d2eb  lea     r11, [rsp+70h+var_s0]
0x18005d2f0  mov     rbx, [r11+20h]
0x18005d2f4  mov     rsi, [r11+28h]
0x18005d2f8  mov     rsp, r11
0x18005d2fb  pop     r14
0x18005d2fd  pop     rdi
0x18005d2fe  pop     rbp
0x18005d2ff  retn
```
