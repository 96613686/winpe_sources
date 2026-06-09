# CreateReturnObject<IFsiFileItem,CFsiFileItem>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)

- ea: `0x1800128b4`
- end: `0x180012abf`
- name: `??$CreateReturnObject@UIFsiFileItem@@VCFsiFileItem@@@@YAPEAUIFsiFileItem@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180010ce0`

## callees

- `0x180003a20`
- `0x180005040`
- `0x180007198`
- `0x18000960c`
- `0x18000c8d0`
- `0x18000f90c`
- `0x1800128b4`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18003b434`
- `0x18003d954`
- `0x180088010`

## string_xrefs

- `0x180012930`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`
- `0x180012a4c`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`

## pseudocode

```c
__int64 __fastcall CreateReturnObject<IFsiFileItem,CFsiFileItem>(CIMAPISystemException *a1, CIMAPISystemException **a2)
{
  int v4; // ebx
  CIMAPISystemException *v5; // rax
  CIMAPISystemException *v6; // rbx
  CIMAPISystemException *v7; // r14
  char *v8; // rsi
  CIMAPISystemException *v9; // rax
  void (__fastcall *v10)(CIMAPISystemException *, CIMAPISystemException **); // rbx
  int v11; // ebx
  CIMAPISystemException *v12; // rax
  CIMAPISystemException *v13; // rbx
  __int64 v14; // rbx
  CIMAPISystemException *pExceptionObject; // [rsp+20h] [rbp-60h] BYREF
  _BYTE v17[88]; // [rsp+28h] [rbp-58h] BYREF
  CIMAPISystemException *v18; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v19; // [rsp+C8h] [rbp+48h] BYREF

  v18 = 0;
  v4 = ATL::CComObject<CFsiFileItem>::CreateInstance(&v18);
  if ( v4 < 0 )
  {
    v5 = (CIMAPISystemException *)operator new(0x58u);
    v18 = v5;
    if ( v5 )
      v5 = CIMAPISystemException::CIMAPISystemException(v5, v4);
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v18, v5);
    v6 = v18;
    if ( v18 && *(_QWORD *)v18 )
    {
      CIMAPIException::SetCodeRefInfo(
        *(CIMAPIException **)v18,
        "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\ImapiComInterface.h",
        208);
      pExceptionObject = v6;
      if ( v6 )
        ++*((_DWORD *)v6 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v17, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v17;
  }
  v7 = v18;
  v8 = (char *)v18 + 72;
  (*(void (__fastcall **)(__int64))(*((_QWORD *)v18 + 9) + 8LL))((__int64)v18 + 72);
  v9 = *a2;
  v18 = v9;
  if ( v9 )
    ++*((_DWORD *)v9 + 2);
  ImapiComReturnObject::Init(v7, &v18);
  v10 = *(void (__fastcall **)(CIMAPISystemException *, CIMAPISystemException **))(*(_QWORD *)v7 + 16LL);
  v18 = a1;
  _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_AddRef(&v18);
  v10(v7, &v18);
  v19 = 0;
  v11 = (**(__int64 (__fastcall ***)(char *, GUID *, __int64 *))v8)(
          v8,
          &GUID_2c941fdb_975b_59be_a960_9a2a262853a5,
          &v19);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v11 < 0 )
  {
    v12 = (CIMAPISystemException *)operator new(0x58u);
    v18 = v12;
    if ( v12 )
      v12 = CIMAPISystemException::CIMAPISystemException(v12, v11);
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v18, v12);
    v13 = v18;
    if ( v18 && *(_QWORD *)v18 )
    {
      CIMAPIException::SetCodeRefInfo(
        *(CIMAPIException **)v18,
        "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\ImapiComInterface.h",
        224);
      pExceptionObject = v13;
      if ( v13 )
        ++*((_DWORD *)v13 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v17, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v17;
  }
  v14 = v19;
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(a2);
  return v14;
}

```

## disassembly

```asm
0x1800128b4  mov     [rsp-28h+arg_0], rbx
0x1800128b9  mov     [rsp-28h+arg_8], rdx
0x1800128be  push    rbp
0x1800128bf  push    rsi
0x1800128c0  push    rdi
0x1800128c1  push    r14
0x1800128c3  push    r15
0x1800128c5  mov     rbp, rsp
0x1800128c8  sub     rsp, 80h
0x1800128cf  mov     rdi, rdx
0x1800128d2  mov     r15, rcx
0x1800128d5  mov     [rbp+arg_10], 0
0x1800128dd  lea     rcx, [rbp+arg_10]
0x1800128e1  call    ?CreateInstance@?$CComObject@VCFsiFileItem@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFsiFileItem>::CreateInstance(ATL::CComObject<CFsiFileItem> * *)
0x1800128e6  mov     ebx, eax
0x1800128e8  test    eax, eax
0x1800128ea  jns     loc_18001297D
0x1800128f0  mov     ecx, 58h ; 'X'; unsigned __int64
0x1800128f5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800128fa  mov     [rbp+arg_10], rax
0x1800128fe  test    rax, rax
0x180012901  jz      short loc_18001290E
0x180012903  mov     edx, ebx; int
0x180012905  mov     rcx, rax; this
0x180012908  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18001290d  nop
0x18001290e  mov     rdx, rax
0x180012911  lea     rcx, [rbp+arg_10]
0x180012915  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001291a  nop
0x18001291b  mov     rbx, [rbp+arg_10]
0x18001291f  test    rbx, rbx
0x180012922  jz      short loc_18001295C
0x180012924  cmp     qword ptr [rbx], 0
0x180012928  jz      short loc_18001295C
0x18001292a  mov     r8d, 0D0h; int
0x180012930  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x180012937  mov     rcx, [rbx]; this
0x18001293a  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18001293f  mov     [rbp+pExceptionObject], rbx
0x180012943  test    rbx, rbx
0x180012946  jz      short loc_18001294B
0x180012948  inc     dword ptr [rbx+8]
0x18001294b  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180012952  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180012956  call    _CxxThrowException_0
0x18001295c  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180012963  lea     rcx, [rbp+var_58]; this
0x180012967  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18001296c  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180012973  lea     rcx, [rbp+var_58]; pExceptionObject
0x180012977  call    _CxxThrowException_0
0x18001297d  mov     r14, [rbp+arg_10]
0x180012981  lea     rsi, [r14+48h]
0x180012985  mov     rax, [rsi]
0x180012988  mov     rcx, rsi
0x18001298b  mov     rax, [rax+8]
0x18001298f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012994  mov     rax, [rdi]
0x180012997  mov     [rbp+arg_10], rax
0x18001299b  test    rax, rax
0x18001299e  jz      short loc_1800129A3
0x1800129a0  inc     dword ptr [rax+8]
0x1800129a3  lea     rdx, [rbp+arg_10]
0x1800129a7  mov     rcx, r14
0x1800129aa  call    ?Init@ImapiComReturnObject@@QEAAXV?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; ImapiComReturnObject::Init(SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x1800129af  mov     rax, [r14]
0x1800129b2  mov     rbx, [rax+10h]
0x1800129b6  mov     [rbp+arg_10], r15
0x1800129ba  lea     rcx, [rbp+arg_10]
0x1800129be  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_AddRef(void)
0x1800129c3  lea     rdx, [rbp+arg_10]
0x1800129c7  mov     rcx, r14
0x1800129ca  mov     rax, rbx
0x1800129cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129d2  mov     [rbp+arg_18], 0
0x1800129da  mov     rax, [rsi]
0x1800129dd  lea     r8, [rbp+arg_18]
0x1800129e1  lea     rdx, _GUID_2c941fdb_975b_59be_a960_9a2a262853a5
0x1800129e8  mov     rcx, rsi
0x1800129eb  mov     rax, [rax]
0x1800129ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129f3  mov     ebx, eax
0x1800129f5  mov     rdx, [rsi]
0x1800129f8  mov     rcx, rsi
0x1800129fb  mov     rax, [rdx+10h]
0x1800129ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a04  test    ebx, ebx
0x180012a06  jns     loc_180012A99
0x180012a0c  mov     ecx, 58h ; 'X'; unsigned __int64
0x180012a11  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012a16  mov     [rbp+arg_10], rax
0x180012a1a  test    rax, rax
0x180012a1d  jz      short loc_180012A2A
0x180012a1f  mov     edx, ebx; int
0x180012a21  mov     rcx, rax; this
0x180012a24  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x180012a29  nop
0x180012a2a  mov     rdx, rax
0x180012a2d  lea     rcx, [rbp+arg_10]
0x180012a31  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180012a36  nop
0x180012a37  mov     rbx, [rbp+arg_10]
0x180012a3b  test    rbx, rbx
0x180012a3e  jz      short loc_180012A78
0x180012a40  cmp     qword ptr [rbx], 0
0x180012a44  jz      short loc_180012A78
0x180012a46  mov     r8d, 0E0h; int
0x180012a4c  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x180012a53  mov     rcx, [rbx]; this
0x180012a56  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180012a5b  mov     [rbp+pExceptionObject], rbx
0x180012a5f  test    rbx, rbx
0x180012a62  jz      short loc_180012A67
0x180012a64  inc     dword ptr [rbx+8]
0x180012a67  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180012a6e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180012a72  call    _CxxThrowException_0
0x180012a78  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180012a7f  lea     rcx, [rbp+var_58]; this
0x180012a83  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180012a88  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180012a8f  lea     rcx, [rbp+var_58]; pExceptionObject
0x180012a93  call    _CxxThrowException_0
0x180012a99  mov     rbx, [rbp+arg_18]
0x180012a9d  mov     rcx, rdi; void *
0x180012aa0  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x180012aa5  mov     rax, rbx
0x180012aa8  mov     rbx, [rsp+80h+arg_0]
0x180012ab0  add     rsp, 80h
0x180012ab7  pop     r15
0x180012ab9  pop     r14
0x180012abb  pop     rdi
0x180012abc  pop     rsi
0x180012abd  pop     rbp
0x180012abe  retn
```
