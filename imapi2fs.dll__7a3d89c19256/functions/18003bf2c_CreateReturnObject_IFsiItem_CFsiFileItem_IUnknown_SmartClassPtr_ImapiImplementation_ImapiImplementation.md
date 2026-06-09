# CreateReturnObject<IFsiItem,CFsiFileItem>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)

- ea: `0x18003bf2c`
- end: `0x18003c137`
- name: `??$CreateReturnObject@UIFsiItem@@VCFsiFileItem@@@@YAPEAUIFsiItem@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z`
- size: `523`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800118b0`
- `0x18003e750`
- `0x18003ea30`

## callees

- `0x180003a20`
- `0x180005040`
- `0x180007198`
- `0x18000960c`
- `0x18000c8d0`
- `0x18000f90c`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18003b434`
- `0x18003bf2c`
- `0x18003d954`
- `0x180088010`

## string_xrefs

- `0x18003bfa8`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`
- `0x18003c0c4`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`

## pseudocode

```c
__int64 __fastcall CreateReturnObject<IFsiItem,CFsiFileItem>(CIMAPISystemException *a1, CIMAPISystemException **a2)
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
          &GUID_2c941fd9_975b_59be_a960_9a2a262853a5,
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
0x18003bf2c  mov     [rsp-28h+arg_0], rbx
0x18003bf31  mov     [rsp-28h+arg_8], rdx
0x18003bf36  push    rbp
0x18003bf37  push    rsi
0x18003bf38  push    rdi
0x18003bf39  push    r14
0x18003bf3b  push    r15
0x18003bf3d  mov     rbp, rsp
0x18003bf40  sub     rsp, 80h
0x18003bf47  mov     rdi, rdx
0x18003bf4a  mov     r15, rcx
0x18003bf4d  mov     [rbp+arg_10], 0
0x18003bf55  lea     rcx, [rbp+arg_10]
0x18003bf59  call    ?CreateInstance@?$CComObject@VCFsiFileItem@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFsiFileItem>::CreateInstance(ATL::CComObject<CFsiFileItem> * *)
0x18003bf5e  mov     ebx, eax
0x18003bf60  test    eax, eax
0x18003bf62  jns     loc_18003BFF5
0x18003bf68  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003bf6d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003bf72  mov     [rbp+arg_10], rax
0x18003bf76  test    rax, rax
0x18003bf79  jz      short loc_18003BF86
0x18003bf7b  mov     edx, ebx; int
0x18003bf7d  mov     rcx, rax; this
0x18003bf80  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18003bf85  nop
0x18003bf86  mov     rdx, rax
0x18003bf89  lea     rcx, [rbp+arg_10]
0x18003bf8d  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003bf92  nop
0x18003bf93  mov     rbx, [rbp+arg_10]
0x18003bf97  test    rbx, rbx
0x18003bf9a  jz      short loc_18003BFD4
0x18003bf9c  cmp     qword ptr [rbx], 0
0x18003bfa0  jz      short loc_18003BFD4
0x18003bfa2  mov     r8d, 0D0h; int
0x18003bfa8  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x18003bfaf  mov     rcx, [rbx]; this
0x18003bfb2  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003bfb7  mov     [rbp+pExceptionObject], rbx
0x18003bfbb  test    rbx, rbx
0x18003bfbe  jz      short loc_18003BFC3
0x18003bfc0  inc     dword ptr [rbx+8]
0x18003bfc3  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003bfca  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003bfce  call    _CxxThrowException_0
0x18003bfd4  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003bfdb  lea     rcx, [rbp+var_58]; this
0x18003bfdf  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003bfe4  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003bfeb  lea     rcx, [rbp+var_58]; pExceptionObject
0x18003bfef  call    _CxxThrowException_0
0x18003bff5  mov     r14, [rbp+arg_10]
0x18003bff9  lea     rsi, [r14+48h]
0x18003bffd  mov     rax, [rsi]
0x18003c000  mov     rcx, rsi
0x18003c003  mov     rax, [rax+8]
0x18003c007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c00c  mov     rax, [rdi]
0x18003c00f  mov     [rbp+arg_10], rax
0x18003c013  test    rax, rax
0x18003c016  jz      short loc_18003C01B
0x18003c018  inc     dword ptr [rax+8]
0x18003c01b  lea     rdx, [rbp+arg_10]
0x18003c01f  mov     rcx, r14
0x18003c022  call    ?Init@ImapiComReturnObject@@QEAAXV?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; ImapiComReturnObject::Init(SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x18003c027  mov     rax, [r14]
0x18003c02a  mov     rbx, [rax+10h]
0x18003c02e  mov     [rbp+arg_10], r15
0x18003c032  lea     rcx, [rbp+arg_10]
0x18003c036  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_AddRef(void)
0x18003c03b  lea     rdx, [rbp+arg_10]
0x18003c03f  mov     rcx, r14
0x18003c042  mov     rax, rbx
0x18003c045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c04a  mov     [rbp+arg_18], 0
0x18003c052  mov     rax, [rsi]
0x18003c055  lea     r8, [rbp+arg_18]
0x18003c059  lea     rdx, _GUID_2c941fd9_975b_59be_a960_9a2a262853a5
0x18003c060  mov     rcx, rsi
0x18003c063  mov     rax, [rax]
0x18003c066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c06b  mov     ebx, eax
0x18003c06d  mov     rdx, [rsi]
0x18003c070  mov     rcx, rsi
0x18003c073  mov     rax, [rdx+10h]
0x18003c077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c07c  test    ebx, ebx
0x18003c07e  jns     loc_18003C111
0x18003c084  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003c089  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003c08e  mov     [rbp+arg_10], rax
0x18003c092  test    rax, rax
0x18003c095  jz      short loc_18003C0A2
0x18003c097  mov     edx, ebx; int
0x18003c099  mov     rcx, rax; this
0x18003c09c  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18003c0a1  nop
0x18003c0a2  mov     rdx, rax
0x18003c0a5  lea     rcx, [rbp+arg_10]
0x18003c0a9  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003c0ae  nop
0x18003c0af  mov     rbx, [rbp+arg_10]
0x18003c0b3  test    rbx, rbx
0x18003c0b6  jz      short loc_18003C0F0
0x18003c0b8  cmp     qword ptr [rbx], 0
0x18003c0bc  jz      short loc_18003C0F0
0x18003c0be  mov     r8d, 0E0h; int
0x18003c0c4  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x18003c0cb  mov     rcx, [rbx]; this
0x18003c0ce  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003c0d3  mov     [rbp+pExceptionObject], rbx
0x18003c0d7  test    rbx, rbx
0x18003c0da  jz      short loc_18003C0DF
0x18003c0dc  inc     dword ptr [rbx+8]
0x18003c0df  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003c0e6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003c0ea  call    _CxxThrowException_0
0x18003c0f0  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003c0f7  lea     rcx, [rbp+var_58]; this
0x18003c0fb  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003c100  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003c107  lea     rcx, [rbp+var_58]; pExceptionObject
0x18003c10b  call    _CxxThrowException_0
0x18003c111  mov     rbx, [rbp+arg_18]
0x18003c115  mov     rcx, rdi; void *
0x18003c118  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18003c11d  mov     rax, rbx
0x18003c120  mov     rbx, [rsp+80h+arg_0]
0x18003c128  add     rsp, 80h
0x18003c12f  pop     r15
0x18003c131  pop     r14
0x18003c133  pop     rdi
0x18003c134  pop     rsi
0x18003c135  pop     rbp
0x18003c136  retn
```
