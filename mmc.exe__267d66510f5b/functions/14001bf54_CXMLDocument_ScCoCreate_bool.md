# CXMLDocument::ScCoCreate(bool)

- ea: `0x14001bf54`
- end: `0x14001c1c0`
- name: `?ScCoCreate@CXMLDocument@@QEAA?AVSC@mmcerror@@_N@Z`
- size: `620`
- prototype: `mmcerror::SC *__fastcall(LPVOID *, mmcerror::SC *, char)`
- caller_count: `6`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001b758`
- `0x140041d3c`
- `0x1400e073c`
- `0x1400e0d2c`
- `0x1400e1764`
- `0x1400e1a10`

## callees

- `0x14001bf54`
- `0x140029450`
- `0x14002ce60`
- `0x14003ce40`
- `0x140040d34`
- `0x140041074`
- `0x1400e061c`
- `0x1400e9e10`
- `0x1400f3010`

## import_xrefs

- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14001bfce`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14001c0b1`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14001c0e5`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14001c165`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14001c190`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14001bfce`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14001c0b1`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14001c0e5`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14001c165`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14001c190`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14001c00d`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14001c0bc`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14001c131`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14001c00d`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14001c0bc`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x14001c131`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x14001bf8d`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x14001bf8d`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14001bfb6`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14001c002`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14001bfb6`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14001c002`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14001bfc2`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14001c0ce`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14001c143`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14001bfc2`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14001c0ce`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x14001c143`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14001c0a5`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14001c0a5`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14001bfa0`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14001bfa0`
- `ole32!CoCreateInstance` at `0x14001bff5`
- `ole32!CoCreateInstance` at `0x14001bff5`

## string_xrefs

- `0x14001bf94`: `CXMLDocument::ScCoCreate`
- `0x14001c04b`: `<?xml version="1.0"?>\n<DUMMY/>`

## pseudocode

```c
mmcerror::SC *__fastcall CXMLDocument::ScCoCreate(LPVOID *a1, mmcerror::SC *a2, char a3)
{
  const struct mmcerror::SC *v6; // rdx
  __int64 Instance; // rdx
  __int64 v9; // rax
  _BYTE v10[24]; // [rsp+30h] [rbp-B8h] BYREF
  struct IUnknown *v11; // [rsp+48h] [rbp-A0h] BYREF
  _BYTE v12[8]; // [rsp+50h] [rbp-98h] BYREF
  mmcerror::SC *v13; // [rsp+58h] [rbp-90h]
  _BYTE v14[48]; // [rsp+68h] [rbp-80h] BYREF
  _OWORD v15[2]; // [rsp+98h] [rbp-50h] BYREF
  _OWORD v16[2]; // [rsp+B8h] [rbp-30h]

  v13 = a2;
  mmcerror::SC::SC((mmcerror::SC *)v10, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v10, L"CXMLDocument::ScCoCreate");
  if ( *a1 )
  {
    v6 = (const struct mmcerror::SC *)mmcerror::SC::operator=(v10, 2147549183LL);
LABEL_3:
    mmcerror::SC::SC(a2, v6);
    mmcerror::SC::~SC((mmcerror::SC *)v10);
    return a2;
  }
  Instance = (unsigned int)CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument, a1);
  mmcerror::SC::operator=(v10, Instance);
  if ( (unsigned __int8)mmcerror::SC::operator bool(v10) )
  {
LABEL_5:
    v6 = (const struct mmcerror::SC *)v10;
    goto LABEL_3;
  }
  (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)*a1 + 576LL))(*a1, 0xFFFFFFFFLL);
  CXMLElement::CXMLElement((CXMLElement *)v12, (struct IUnknown *)*a1);
  if ( !a3 )
  {
LABEL_12:
    _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(v12);
    goto LABEL_5;
  }
  v15[0] = *(_OWORD *)L"<?xml version=\"1.0\"?>\n<DUMMY/>";
  v15[1] = *(_OWORD *)L"rsion=\"1.0\"?>\n<DUMMY/>";
  v16[0] = *(_OWORD *)L".0\"?>\n<DUMMY/>";
  *(_OWORD *)((char *)v16 + 14) = *(_OWORD *)L"DUMMY/>";
  v9 = CXMLDocument::ScLoad(a1, v14, v15);
  mmcerror::SC::operator=(v10, v9);
  mmcerror::SC::~SC((mmcerror::SC *)v14);
  if ( (unsigned __int8)mmcerror::SC::operator bool(v10) )
  {
    mmcerror::SC::SC(a2, (const struct mmcerror::SC *)v10);
    _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(v12);
    mmcerror::SC::~SC((mmcerror::SC *)v10);
    return a2;
  }
  v11 = 0;
  ATL::AtlComQIPtrAssign(&v11, 0, &IID_IXMLDOMNode);
  CXMLDocument::get_root((CXMLDocument *)a1, (struct CXMLElement *)&v11);
  CXMLElement::removeChild((CXMLElement *)v12, (struct CXMLElement *)&v11);
  if ( !(unsigned __int8)mmcerror::SC::operator bool(v10) )
  {
    _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(&v11);
    goto LABEL_12;
  }
  mmcerror::SC::SC(a2, (const struct mmcerror::SC *)v10);
  _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(&v11);
  _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(v12);
  mmcerror::SC::~SC((mmcerror::SC *)v10);
  return a2;
}

```

## disassembly

```asm
0x14001bf54  mov     [rsp+arg_10], rbx
0x14001bf59  mov     [rsp+arg_18], rsi
0x14001bf5e  push    rdi
0x14001bf5f  sub     rsp, 0E0h
0x14001bf66  mov     rax, cs:__security_cookie
0x14001bf6d  xor     rax, rsp
0x14001bf70  mov     [rsp+0E8h+var_10], rax
0x14001bf78  mov     sil, r8b
0x14001bf7b  mov     rbx, rdx
0x14001bf7e  mov     rdi, rcx
0x14001bf81  mov     [rsp+0E8h+var_90], rdx
0x14001bf86  xor     edx, edx
0x14001bf88  lea     rcx, [rsp+0E8h+var_B8]
0x14001bf8d  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x14001bf93  nop
0x14001bf94  lea     rdx, aCxmldocumentSc; "CXMLDocument::ScCoCreate"
0x14001bf9b  lea     rcx, [rsp+0E8h+var_B8]
0x14001bfa0  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x14001bfa6  cmp     qword ptr [rdi], 0
0x14001bfaa  jz      short loc_14001BFDC
0x14001bfac  mov     edx, 8000FFFFh
0x14001bfb1  lea     rcx, [rsp+0E8h+var_B8]
0x14001bfb6  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x14001bfbc  mov     rdx, rax
0x14001bfbf  mov     rcx, rbx
0x14001bfc2  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x14001bfc8  nop
0x14001bfc9  lea     rcx, [rsp+0E8h+var_B8]
0x14001bfce  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14001bfd4  mov     rax, rbx
0x14001bfd7  jmp     loc_14001C19B
0x14001bfdc  mov     [rsp+0E8h+ppv], rdi; ppv
0x14001bfe1  lea     r9, IID_IXMLDOMDocument; riid
0x14001bfe8  xor     edx, edx; pUnkOuter
0x14001bfea  lea     r8d, [rdx+1]; dwClsContext
0x14001bfee  lea     rcx, CLSID_DOMDocument60; rclsid
0x14001bff5  call    cs:__imp_CoCreateInstance
0x14001bffb  mov     edx, eax
0x14001bffd  lea     rcx, [rsp+0E8h+var_B8]
0x14001c002  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x14001c008  lea     rcx, [rsp+0E8h+var_B8]
0x14001c00d  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x14001c013  test    al, al
0x14001c015  jz      short loc_14001C01E
0x14001c017  lea     rdx, [rsp+0E8h+var_B8]
0x14001c01c  jmp     short loc_14001BFBF
0x14001c01e  mov     rcx, [rdi]
0x14001c021  mov     rax, [rcx]
0x14001c024  or      edx, 0FFFFFFFFh
0x14001c027  mov     rax, [rax+240h]
0x14001c02e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c033  nop
0x14001c034  mov     rdx, [rdi]; struct IUnknown *
0x14001c037  lea     rcx, [rsp+0E8h+var_98]; this
0x14001c03c  call    ??0CXMLElement@@QEAA@PEAUIUnknown@@@Z; CXMLElement::CXMLElement(IUnknown *)
0x14001c041  nop
0x14001c042  test    sil, sil
0x14001c045  jz      loc_14001C17B
0x14001c04b  movups  xmm0, xmmword ptr cs:aXmlVersion10Du; "<?xml version=\"1.0\"?>\n<DUMMY/>"
0x14001c052  movups  [rsp+0E8h+var_50], xmm0
0x14001c05a  movups  xmm1, xmmword ptr cs:aXmlVersion10Du+10h; "rsion=\"1.0\"?>\n<DUMMY/>"
0x14001c061  movups  [rsp+0E8h+var_40], xmm1
0x14001c069  movups  xmm0, xmmword ptr cs:aXmlVersion10Du+20h; ".0\"?>\n<DUMMY/>"
0x14001c070  movups  xmmword ptr [rsp+0E8h+var_30], xmm0
0x14001c078  movups  xmm1, xmmword ptr cs:aXmlVersion10Du+2Eh; "DUMMY/>"
0x14001c07f  movups  xmmword ptr [rsp+0E8h+var_30+0Eh], xmm1
0x14001c087  lea     r8, [rsp+0E8h+var_50]
0x14001c08f  lea     rdx, [rsp+0E8h+var_80]
0x14001c094  mov     rcx, rdi
0x14001c097  call    ?ScLoad@CXMLDocument@@QEAA?AVSC@mmcerror@@PEBG@Z; CXMLDocument::ScLoad(ushort const *)
0x14001c09c  nop
0x14001c09d  mov     rdx, rax
0x14001c0a0  lea     rcx, [rsp+0E8h+var_B8]
0x14001c0a5  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x14001c0ab  nop
0x14001c0ac  lea     rcx, [rsp+0E8h+var_80]
0x14001c0b1  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14001c0b7  lea     rcx, [rsp+0E8h+var_B8]
0x14001c0bc  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x14001c0c2  test    al, al
0x14001c0c4  jz      short loc_14001C0F3
0x14001c0c6  lea     rdx, [rsp+0E8h+var_B8]
0x14001c0cb  mov     rcx, rbx
0x14001c0ce  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x14001c0d4  nop
0x14001c0d5  lea     rcx, [rsp+0E8h+var_98]
0x14001c0da  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIDropTarget@@$1?_GUID_00000122_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(void)
0x14001c0df  nop
0x14001c0e0  lea     rcx, [rsp+0E8h+var_B8]
0x14001c0e5  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14001c0eb  mov     rax, rbx
0x14001c0ee  jmp     loc_14001C19B
0x14001c0f3  mov     [rsp+0E8h+var_A0], 0
0x14001c0fc  lea     r8, IID_IXMLDOMNode; struct _GUID *
0x14001c103  xor     edx, edx; struct IUnknown *
0x14001c105  lea     rcx, [rsp+0E8h+var_A0]; struct IUnknown **
0x14001c10a  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x14001c10f  nop
0x14001c110  lea     rdx, [rsp+0E8h+var_A0]; struct CXMLElement *
0x14001c115  mov     rcx, rdi; this
0x14001c118  call    ?get_root@CXMLDocument@@QEAAXPEAVCXMLElement@@@Z; CXMLDocument::get_root(CXMLElement *)
0x14001c11d  lea     rdx, [rsp+0E8h+var_A0]; struct CXMLElement *
0x14001c122  lea     rcx, [rsp+0E8h+var_98]; this
0x14001c127  call    ?removeChild@CXMLElement@@QEAAXAEAV1@@Z; CXMLElement::removeChild(CXMLElement &)
0x14001c12c  lea     rcx, [rsp+0E8h+var_B8]
0x14001c131  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x14001c137  test    al, al
0x14001c139  jz      short loc_14001C170
0x14001c13b  lea     rdx, [rsp+0E8h+var_B8]
0x14001c140  mov     rcx, rbx
0x14001c143  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x14001c149  nop
0x14001c14a  lea     rcx, [rsp+0E8h+var_A0]
0x14001c14f  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIDropTarget@@$1?_GUID_00000122_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(void)
0x14001c154  nop
0x14001c155  lea     rcx, [rsp+0E8h+var_98]
0x14001c15a  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIDropTarget@@$1?_GUID_00000122_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(void)
0x14001c15f  nop
0x14001c160  lea     rcx, [rsp+0E8h+var_B8]
0x14001c165  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14001c16b  mov     rax, rbx
0x14001c16e  jmp     short loc_14001C19B
0x14001c170  lea     rcx, [rsp+0E8h+var_A0]
0x14001c175  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIDropTarget@@$1?_GUID_00000122_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(void)
0x14001c17a  nop
0x14001c17b  lea     rcx, [rsp+0E8h+var_98]
0x14001c180  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@UIDropTarget@@$1?_GUID_00000122_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IDropTarget,&__s_GUID const _GUID_00000122_0000_0000_c000_000000000046>>::_Release(void)
0x14001c185  nop
0x14001c186  jmp     loc_14001C017
0x14001c18b  lea     rcx, [rsp+0E8h+var_B8]
0x14001c190  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x14001c196  mov     rax, [rsp+0E8h+var_90]
0x14001c19b  mov     rcx, [rsp+0E8h+var_10]
0x14001c1a3  xor     rcx, rsp; StackCookie
0x14001c1a6  call    __security_check_cookie
0x14001c1ab  lea     r11, [rsp+0E8h+var_8]
0x14001c1b3  mov     rbx, [r11+20h]
0x14001c1b7  mov     rsi, [r11+28h]
0x14001c1bb  mov     rsp, r11
0x14001c1be  pop     rdi
0x14001c1bf  retn
```
