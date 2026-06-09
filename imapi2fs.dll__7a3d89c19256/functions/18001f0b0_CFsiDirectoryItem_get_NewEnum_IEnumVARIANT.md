# CFsiDirectoryItem::get__NewEnum(IEnumVARIANT * *)

- ea: `0x18001f0b0`
- end: `0x18001f273`
- name: `?get__NewEnum@CFsiDirectoryItem@@UEAAJPEAPEAUIEnumVARIANT@@@Z`
- size: `451`
- prototype: `__int64 __fastcall(CFsiDirectoryItem *__hidden this, struct IEnumVARIANT **)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003580`
- `0x180003a20`
- `0x1800040b0`
- `0x1800048e0`
- `0x180005040`
- `0x18000960c`
- `0x18000c8d0`
- `0x18000f90c`
- `0x180011c48`
- `0x180018fdc`
- `0x1800199b8`
- `0x18001f0b0`
- `0x18001f27c`
- `0x18001f2a0`
- `0x1800251dc`
- `0x18002d4e4`

## string_xrefs

- `0x18001f0c3`: `CFsiDirectoryItem::get__NewEnum`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CFsiDirectoryItem::get__NewEnum(CFsiDirectoryItem *this, struct IEnumVARIANT **a2)
{
  CIMAPISystemException *v4; // rax
  CIMAPISystemException *v5; // rax
  CIMAPIException **v6; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-A8h] BYREF
  char v9[8]; // [rsp+28h] [rbp-A0h] BYREF
  CIMAPISystemException **v10; // [rsp+30h] [rbp-98h]
  CIMAPIException ***v11; // [rsp+38h] [rbp-90h]
  _BYTE v12[136]; // [rsp+40h] [rbp-88h] BYREF
  CIMAPIException **v13; // [rsp+D0h] [rbp+8h] BYREF
  CIMAPISystemException *v14; // [rsp+D8h] [rbp+10h] BYREF
  CIMAPISystemException *v15; // [rsp+E0h] [rbp+18h] BYREF
  char *v16; // [rsp+E8h] [rbp+20h]

  MethodTrace::MethodTrace((MethodTrace *)v9, "CFsiDirectoryItem::get__NewEnum");
  ImapiClearErrorInfo();
  v16 = (char *)this - 80;
  ImapiComObject::LockCS((CFsiDirectoryItem *)((char *)this - 80));
  try
  {
    if ( !a2 )
    {
      v5 = (CIMAPISystemException *)operator new(0x58u);
      v13 = (CIMAPIException **)v5;
      if ( v5 )
        v5 = CIMAPIException::CIMAPIException(v5, -2147467261, L"NewEnum");
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v13, v5);
      v6 = v13;
      if ( v13 && *v13 )
      {
        CIMAPIException::SetCodeRefInfo(*v13, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 57);
        pExceptionObject = v6;
        if ( v6 )
          ++*((_DWORD *)v6 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v12,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v12;
    }
    v4 = (CIMAPISystemException *)*((_QWORD *)this + 8);
    v14 = v4;
    if ( v4 )
      ++*((_DWORD *)v4 + 2);
    v10 = &v14;
    v13 = (CIMAPIException **)*((_QWORD *)this - 2);
    _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_AddRef(&v13);
    v11 = &v13;
    *a2 = 0;
    v15 = v14;
    if ( v14 )
      ++*((_DWORD *)v14 + 2);
    *a2 = (struct IEnumVARIANT *)CreateReturnObject<IEnumVARIANT,CEnumFsiItems>((CIMAPISystemException *)v13, &v15);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v14);
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_FsiDirectoryItem);
  }
  ImapiComObject::UnlockCS((CFsiDirectoryItem *)((char *)this - 80));
  MethodTrace::~MethodTrace((MethodTrace *)v9);
  return 0;
}

```

## disassembly

```asm
0x18001f0b0  push    rbx
0x18001f0b2  push    rsi
0x18001f0b3  push    rdi
0x18001f0b4  push    r14
0x18001f0b6  sub     rsp, 0A8h
0x18001f0bd  mov     rsi, rdx
0x18001f0c0  mov     rdi, rcx
0x18001f0c3  lea     rdx, aCfsidirectoryi_17; "CFsiDirectoryItem::get__NewEnum"
0x18001f0ca  lea     rcx, [rsp+0C8h+var_A0]; this
0x18001f0cf  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18001f0d4  nop
0x18001f0d5  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18001f0da  nop
0x18001f0db  lea     rbx, [rdi-50h]
0x18001f0df  mov     [rsp+0C8h+arg_18], rbx
0x18001f0e7  mov     rcx, rbx; this
0x18001f0ea  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18001f0ef  test    rsi, rsi
0x18001f0f2  jz      loc_18001F19A
0x18001f0f8  xor     r14d, r14d
0x18001f0fb  mov     rax, [rdi+40h]
0x18001f0ff  mov     [rsp+0C8h+arg_8], rax
0x18001f107  test    rax, rax
0x18001f10a  jz      short loc_18001F10F
0x18001f10c  inc     dword ptr [rax+8]
0x18001f10f  lea     rax, [rsp+0C8h+arg_8]
0x18001f117  mov     [rsp+0C8h+var_98], rax
0x18001f11c  mov     rax, [rdi-10h]
0x18001f120  mov     [rsp+0C8h+arg_0], rax
0x18001f128  lea     rcx, [rsp+0C8h+arg_0]
0x18001f130  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_AddRef(void)
0x18001f135  lea     rax, [rsp+0C8h+arg_0]
0x18001f13d  mov     [rsp+0C8h+var_90], rax
0x18001f142  mov     qword ptr [rsi], 0
0x18001f149  mov     rax, [rsp+0C8h+arg_8]
0x18001f151  mov     [rsp+0C8h+arg_10], rax
0x18001f159  test    rax, rax
0x18001f15c  jz      short loc_18001F161
0x18001f15e  inc     dword ptr [rax+8]
0x18001f161  lea     rdx, [rsp+0C8h+arg_10]
0x18001f169  mov     rcx, [rsp+0C8h+arg_0]
0x18001f171  call    ??$CreateReturnObject@UIEnumVARIANT@@VCEnumFsiItems@@@@YAPEAUIEnumVARIANT@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; CreateReturnObject<IEnumVARIANT,CEnumFsiItems>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x18001f176  mov     [rsi], rax
0x18001f179  lea     rcx, [rsp+0C8h+arg_0]
0x18001f181  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001f186  nop
0x18001f187  lea     rcx, [rsp+0C8h+arg_8]; void *
0x18001f18f  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18001f194  nop
0x18001f195  jmp     loc_18001F250
0x18001f19a  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001f19f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f1a4  mov     [rsp+0C8h+arg_0], rax
0x18001f1ac  test    rax, rax
0x18001f1af  jz      short loc_18001F1C6
0x18001f1b1  lea     r8, aNewenum; "NewEnum"
0x18001f1b8  mov     edx, 80004003h; int
0x18001f1bd  mov     rcx, rax; this
0x18001f1c0  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18001f1c5  nop
0x18001f1c6  mov     rdx, rax
0x18001f1c9  lea     rcx, [rsp+0C8h+arg_0]
0x18001f1d1  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001f1d6  nop
0x18001f1d7  mov     rbx, [rsp+0C8h+arg_0]
0x18001f1df  test    rbx, rbx
0x18001f1e2  jz      short loc_18001F21D
0x18001f1e4  cmp     qword ptr [rbx], 0
0x18001f1e8  jz      short loc_18001F21D
0x18001f1ea  mov     r8d, 39h ; '9'; int
0x18001f1f0  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18001f1f7  mov     rcx, [rbx]; this
0x18001f1fa  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18001f1ff  mov     [rsp+0C8h+pExceptionObject], rbx
0x18001f204  test    rbx, rbx
0x18001f207  jz      short loc_18001F20C
0x18001f209  inc     dword ptr [rbx+8]
0x18001f20c  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18001f213  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18001f218  call    _CxxThrowException_0
0x18001f21d  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18001f224  lea     rcx, [rsp+0C8h+var_88]; this
0x18001f229  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18001f22e  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18001f235  lea     rcx, [rsp+0C8h+var_88]; pExceptionObject
0x18001f23a  call    _CxxThrowException_0
0x18001f240  mov     r14d, dword ptr [rsp+0C8h+arg_0]
0x18001f248  mov     rbx, [rsp+0C8h+arg_18]
0x18001f250  mov     rcx, rbx; this
0x18001f253  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x18001f258  nop
0x18001f259  lea     rcx, [rsp+0C8h+var_A0]; this
0x18001f25e  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18001f263  mov     eax, r14d
0x18001f266  add     rsp, 0A8h
0x18001f26d  pop     r14
0x18001f26f  pop     rdi
0x18001f270  pop     rsi
0x18001f271  pop     rbx
0x18001f272  retn
```
