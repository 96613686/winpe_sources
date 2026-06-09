# CConsoleFilePersistor::ScLoadXMLDocumentFromFile(CXMLDocument &,ushort const *,bool)

- ea: `0x180127e68`
- end: `0x18012807c`
- name: `?ScLoadXMLDocumentFromFile@CConsoleFilePersistor@@CA?AVSC@mmcerror@@AEAVCXMLDocument@@PEBG_N@Z`
- size: `532`
- prototype: `mmcerror::SC *__fastcall(mmcerror::SC *, __int64, __int64, char)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006ec64`
- `0x180127778`

## callees

- `0x180016bd4`
- `0x180017b60`
- `0x1800304c0`
- `0x180056a94`
- `0x18012748c`
- `0x180127e68`
- `0x180128408`
- `0x18013f010`

## import_xrefs

- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180127e8d`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x180127e8d`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180127f37`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180127fd6`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180127f37`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x180127fd6`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x180127efa`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x180128026`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x180128046`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x180127efa`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x180128026`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x180128046`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180127ed4`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180127f8e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180128019`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180127ed4`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180127f8e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x180128019`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180127e9f`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x180127e9f`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180127ee9`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180127f41`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180127fa3`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180127fe0`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180128002`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180127ee9`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180127f41`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180127fa3`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180127fe0`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x180128002`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180127edf`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180127f99`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180128031`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180128065`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180127edf`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180127f99`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180128031`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x180128065`
- `ole32!CreateStreamOnHGlobal` at `0x180127f2b`
- `ole32!CreateStreamOnHGlobal` at `0x180127f2b`

## string_xrefs

- `0x180127e94`: `CConsoleFilePersistor::ScLoadXMLDocumentFromFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
mmcerror::SC *__fastcall CConsoleFilePersistor::ScLoadXMLDocumentFromFile(
        mmcerror::SC *a1,
        __int64 a2,
        __int64 a3,
        char a4)
{
  __int64 v8; // rax
  unsigned int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned int v12; // eax
  __int64 v13; // r9
  const struct mmcerror::SC *v14; // rdx
  LPSTREAM ppstm; // [rsp+20h] [rbp-49h] BYREF
  _BYTE v17[24]; // [rsp+28h] [rbp-41h] BYREF
  HGLOBAL hGlobal; // [rsp+40h] [rbp-29h] BYREF
  __int64 v19; // [rsp+48h] [rbp-21h]
  int v20; // [rsp+50h] [rbp-19h]
  __int64 v21; // [rsp+58h] [rbp-11h]
  _BYTE v22[24]; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v23[64]; // [rsp+80h] [rbp+17h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v17, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v17, L"CConsoleFilePersistor::ScLoadXMLDocumentFromFile");
  hGlobal = 0;
  v19 = 0;
  v20 = 0;
  v8 = ScReadDataFromFile(v23, a3, &hGlobal);
  mmcerror::SC::operator=(v17, v8);
  mmcerror::SC::~SC((mmcerror::SC *)v23);
  if ( (unsigned __int8)mmcerror::SC::operator bool(v17) )
  {
    mmcerror::SC::SC(a1, (const struct mmcerror::SC *)v17);
  }
  else
  {
    ppstm = 0;
    ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(&ppstm);
    ppstm = 0;
    v9 = CreateStreamOnHGlobal(hGlobal, 1, &ppstm);
    mmcerror::SC::operator=(v17, v9);
    if ( (unsigned __int8)mmcerror::SC::operator bool(v17) )
      goto LABEL_12;
    v21 = (unsigned int)v19;
    hGlobal = 0;
    v19 = 0;
    v20 = 0;
    v10 = ScCheckPointers(v23, ppstm, 2147549183LL);
    mmcerror::SC::operator=(v17, v10);
    mmcerror::SC::~SC((mmcerror::SC *)v23);
    if ( (unsigned __int8)mmcerror::SC::operator bool(v17)
      || (v11 = _com_ptr_t<_com_IIID<IWaitDialog,&_GUID const IID_IWaitDialog>>::operator->(&ppstm),
          v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 48LL))(v11, v21),
          mmcerror::SC::operator=(v17, v12),
          (unsigned __int8)mmcerror::SC::operator bool(v17)) )
    {
LABEL_12:
      mmcerror::SC::SC(a1, (const struct mmcerror::SC *)v17);
    }
    else
    {
      LOBYTE(v13) = a4;
      CXMLDocument::ScLoad(a2, v22, ppstm, v13);
      if ( (unsigned __int8)mmcerror::SC::operator bool(v22) )
      {
        if ( !a4 )
          mmcerror::SC::operator=(v17, v22);
        v14 = (const struct mmcerror::SC *)v22;
      }
      else
      {
        v14 = (const struct mmcerror::SC *)v17;
      }
      mmcerror::SC::SC(a1, v14);
      mmcerror::SC::~SC((mmcerror::SC *)v22);
    }
    ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(&ppstm);
  }
  CXMLAutoBinary::~CXMLAutoBinary((CXMLAutoBinary *)&hGlobal);
  mmcerror::SC::~SC((mmcerror::SC *)v17);
  return a1;
}

```

## disassembly

```asm
0x180127e68  push    rbp
0x180127e6a  push    rbx
0x180127e6b  push    rsi
0x180127e6c  push    rdi
0x180127e6d  push    r14
0x180127e6f  lea     rbp, [rsp-37h]
0x180127e74  sub     rsp, 0A0h
0x180127e7b  mov     sil, r9b
0x180127e7e  mov     rbx, r8
0x180127e81  mov     r14, rdx
0x180127e84  mov     rdi, rcx
0x180127e87  xor     edx, edx
0x180127e89  lea     rcx, [rbp+57h+var_98]
0x180127e8d  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x180127e93  nop
0x180127e94  lea     rdx, aCconsolefilepe_2; "CConsoleFilePersistor::ScLoadXMLDocumen"...
0x180127e9b  lea     rcx, [rbp+57h+var_98]
0x180127e9f  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x180127ea5  mov     [rbp+57h+hGlobal], 0
0x180127ead  mov     [rbp+57h+var_78], 0
0x180127eb5  mov     [rbp+57h+var_70], 0
0x180127ebc  lea     r8, [rbp+57h+hGlobal]
0x180127ec0  mov     rdx, rbx
0x180127ec3  lea     rcx, [rbp+57h+var_40]
0x180127ec7  call    ScReadDataFromFile
0x180127ecc  nop
0x180127ecd  mov     rdx, rax
0x180127ed0  lea     rcx, [rbp+57h+var_98]
0x180127ed4  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x180127eda  nop
0x180127edb  lea     rcx, [rbp+57h+var_40]
0x180127edf  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180127ee5  lea     rcx, [rbp+57h+var_98]
0x180127ee9  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180127eef  test    al, al
0x180127ef1  jz      short loc_180127F05
0x180127ef3  lea     rdx, [rbp+57h+var_98]
0x180127ef7  mov     rcx, rdi
0x180127efa  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x180127f00  jmp     loc_180128057
0x180127f05  mov     [rbp+57h+ppstm], 0
0x180127f0d  lea     rcx, [rbp+57h+ppstm]
0x180127f11  call    ??1?$CComPtr@UIProvideClassInfo2@@@ATL@@QEAA@XZ; ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(void)
0x180127f16  mov     [rbp+57h+ppstm], 0
0x180127f1e  lea     r8, [rbp+57h+ppstm]; ppstm
0x180127f22  mov     edx, 1; fDeleteOnRelease
0x180127f27  mov     rcx, [rbp+57h+hGlobal]; hGlobal
0x180127f2b  call    cs:__imp_CreateStreamOnHGlobal
0x180127f31  mov     edx, eax
0x180127f33  lea     rcx, [rbp+57h+var_98]
0x180127f37  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180127f3d  lea     rcx, [rbp+57h+var_98]
0x180127f41  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180127f47  test    al, al
0x180127f49  jnz     loc_18012803F
0x180127f4f  mov     eax, dword ptr [rbp+57h+var_78]
0x180127f52  mov     dword ptr [rbp+57h+var_68], eax
0x180127f55  mov     dword ptr [rbp+57h+var_68+4], 0
0x180127f5c  mov     [rbp+57h+hGlobal], 0
0x180127f64  mov     [rbp+57h+var_78], 0
0x180127f6c  mov     [rbp+57h+var_70], 0
0x180127f73  mov     r8d, 8000FFFFh
0x180127f79  mov     rdx, [rbp+57h+ppstm]
0x180127f7d  lea     rcx, [rbp+57h+var_40]
0x180127f81  call    ?ScCheckPointers@@YA?AVSC@mmcerror@@PEBXJ@Z; ScCheckPointers(void const *,long)
0x180127f86  nop
0x180127f87  mov     rdx, rax
0x180127f8a  lea     rcx, [rbp+57h+var_98]
0x180127f8e  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x180127f94  nop
0x180127f95  lea     rcx, [rbp+57h+var_40]
0x180127f99  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180127f9f  lea     rcx, [rbp+57h+var_98]
0x180127fa3  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180127fa9  test    al, al
0x180127fab  jnz     loc_18012803F
0x180127fb1  lea     rcx, [rbp+57h+ppstm]
0x180127fb5  call    ??C?$_com_ptr_t@V?$_com_IIID@UIWaitDialog@@$1?IID_IWaitDialog@@3U_GUID@@B@@@@QEBAPEAUIWaitDialog@@XZ; _com_ptr_t<_com_IIID<IWaitDialog,&_GUID const IID_IWaitDialog>>::operator->(void)
0x180127fba  mov     r8, rax
0x180127fbd  mov     rcx, [rax]
0x180127fc0  mov     rax, [rcx+30h]
0x180127fc4  mov     rdx, [rbp+57h+var_68]
0x180127fc8  mov     rcx, r8
0x180127fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180127fd0  mov     edx, eax
0x180127fd2  lea     rcx, [rbp+57h+var_98]
0x180127fd6  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x180127fdc  lea     rcx, [rbp+57h+var_98]
0x180127fe0  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180127fe6  test    al, al
0x180127fe8  jnz     short loc_18012803F
0x180127fea  mov     r9b, sil
0x180127fed  mov     r8, [rbp+57h+ppstm]
0x180127ff1  lea     rdx, [rbp+57h+var_58]
0x180127ff5  mov     rcx, r14
0x180127ff8  call    ?ScLoad@CXMLDocument@@QEAA?AVSC@mmcerror@@PEAUIStream@@_N@Z; CXMLDocument::ScLoad(IStream *,bool)
0x180127ffd  nop
0x180127ffe  lea     rcx, [rbp+57h+var_58]
0x180128002  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x180128008  test    al, al
0x18012800a  jz      short loc_180128039
0x18012800c  test    sil, sil
0x18012800f  jnz     short loc_18012801F
0x180128011  lea     rdx, [rbp+57h+var_58]
0x180128015  lea     rcx, [rbp+57h+var_98]
0x180128019  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x18012801f  lea     rdx, [rbp+57h+var_58]
0x180128023  mov     rcx, rdi
0x180128026  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x18012802c  nop
0x18012802d  lea     rcx, [rbp+57h+var_58]
0x180128031  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x180128037  jmp     short loc_18012804D
0x180128039  lea     rdx, [rbp+57h+var_98]
0x18012803d  jmp     short loc_180128023
0x18012803f  lea     rdx, [rbp+57h+var_98]
0x180128043  mov     rcx, rdi
0x180128046  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x18012804c  nop
0x18012804d  lea     rcx, [rbp+57h+ppstm]
0x180128051  call    ??1?$CComPtr@UIProvideClassInfo2@@@ATL@@QEAA@XZ; ATL::CComPtr<IProvideClassInfo2>::~CComPtr<IProvideClassInfo2>(void)
0x180128056  nop
0x180128057  lea     rcx, [rbp+57h+hGlobal]; this
0x18012805b  call    ??1CXMLAutoBinary@@QEAA@XZ; CXMLAutoBinary::~CXMLAutoBinary(void)
0x180128060  nop
0x180128061  lea     rcx, [rbp+57h+var_98]
0x180128065  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x18012806b  mov     rax, rdi
0x18012806e  add     rsp, 0A0h
0x180128075  pop     r14
0x180128077  pop     rdi
0x180128078  pop     rsi
0x180128079  pop     rbx
0x18012807a  pop     rbp
0x18012807b  retn
```
