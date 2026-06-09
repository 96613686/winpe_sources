# CreateReturnObject<IStream,CFsiStream>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)

- ea: `0x180011e7c`
- end: `0x180012087`
- name: `??$CreateReturnObject@UIStream@@VCFsiStream@@@@YAPEAUIStream@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z`
- size: `523`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800106a0`
- `0x180011400`

## callees

- `0x180003a20`
- `0x180005040`
- `0x180007198`
- `0x18000960c`
- `0x18000c8d0`
- `0x18000f90c`
- `0x180011e7c`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18003b2e4`
- `0x18003b434`
- `0x180088010`

## string_xrefs

- `0x180011ef8`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`
- `0x180012014`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`

## pseudocode

```c
__int64 __fastcall CreateReturnObject<IStream,CFsiStream>(CIMAPISystemException *a1, CIMAPISystemException **a2)
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
  v4 = ATL::CComObject<CFsiStream>::CreateInstance(&v18);
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
          &GUID_0000000c_0000_0000_c000_000000000046,
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
0x180011e7c  mov     [rsp-28h+arg_0], rbx
0x180011e81  mov     [rsp-28h+arg_8], rdx
0x180011e86  push    rbp
0x180011e87  push    rsi
0x180011e88  push    rdi
0x180011e89  push    r14
0x180011e8b  push    r15
0x180011e8d  mov     rbp, rsp
0x180011e90  sub     rsp, 80h
0x180011e97  mov     rdi, rdx
0x180011e9a  mov     r15, rcx
0x180011e9d  mov     [rbp+arg_10], 0
0x180011ea5  lea     rcx, [rbp+arg_10]
0x180011ea9  call    ?CreateInstance@?$CComObject@VCFsiStream@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFsiStream>::CreateInstance(ATL::CComObject<CFsiStream> * *)
0x180011eae  mov     ebx, eax
0x180011eb0  test    eax, eax
0x180011eb2  jns     loc_180011F45
0x180011eb8  mov     ecx, 58h ; 'X'; unsigned __int64
0x180011ebd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011ec2  mov     [rbp+arg_10], rax
0x180011ec6  test    rax, rax
0x180011ec9  jz      short loc_180011ED6
0x180011ecb  mov     edx, ebx; int
0x180011ecd  mov     rcx, rax; this
0x180011ed0  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x180011ed5  nop
0x180011ed6  mov     rdx, rax
0x180011ed9  lea     rcx, [rbp+arg_10]
0x180011edd  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180011ee2  nop
0x180011ee3  mov     rbx, [rbp+arg_10]
0x180011ee7  test    rbx, rbx
0x180011eea  jz      short loc_180011F24
0x180011eec  cmp     qword ptr [rbx], 0
0x180011ef0  jz      short loc_180011F24
0x180011ef2  mov     r8d, 0D0h; int
0x180011ef8  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x180011eff  mov     rcx, [rbx]; this
0x180011f02  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180011f07  mov     [rbp+pExceptionObject], rbx
0x180011f0b  test    rbx, rbx
0x180011f0e  jz      short loc_180011F13
0x180011f10  inc     dword ptr [rbx+8]
0x180011f13  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180011f1a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011f1e  call    _CxxThrowException_0
0x180011f24  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180011f2b  lea     rcx, [rbp+var_58]; this
0x180011f2f  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180011f34  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180011f3b  lea     rcx, [rbp+var_58]; pExceptionObject
0x180011f3f  call    _CxxThrowException_0
0x180011f45  mov     r14, [rbp+arg_10]
0x180011f49  lea     rsi, [r14+48h]
0x180011f4d  mov     rax, [rsi]
0x180011f50  mov     rcx, rsi
0x180011f53  mov     rax, [rax+8]
0x180011f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f5c  mov     rax, [rdi]
0x180011f5f  mov     [rbp+arg_10], rax
0x180011f63  test    rax, rax
0x180011f66  jz      short loc_180011F6B
0x180011f68  inc     dword ptr [rax+8]
0x180011f6b  lea     rdx, [rbp+arg_10]
0x180011f6f  mov     rcx, r14
0x180011f72  call    ?Init@ImapiComReturnObject@@QEAAXV?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; ImapiComReturnObject::Init(SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x180011f77  mov     rax, [r14]
0x180011f7a  mov     rbx, [rax+10h]
0x180011f7e  mov     [rbp+arg_10], r15
0x180011f82  lea     rcx, [rbp+arg_10]
0x180011f86  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_AddRef(void)
0x180011f8b  lea     rdx, [rbp+arg_10]
0x180011f8f  mov     rcx, r14
0x180011f92  mov     rax, rbx
0x180011f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f9a  mov     [rbp+arg_18], 0
0x180011fa2  mov     rax, [rsi]
0x180011fa5  lea     r8, [rbp+arg_18]
0x180011fa9  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180011fb0  mov     rcx, rsi
0x180011fb3  mov     rax, [rax]
0x180011fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fbb  mov     ebx, eax
0x180011fbd  mov     rdx, [rsi]
0x180011fc0  mov     rcx, rsi
0x180011fc3  mov     rax, [rdx+10h]
0x180011fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fcc  test    ebx, ebx
0x180011fce  jns     loc_180012061
0x180011fd4  mov     ecx, 58h ; 'X'; unsigned __int64
0x180011fd9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011fde  mov     [rbp+arg_10], rax
0x180011fe2  test    rax, rax
0x180011fe5  jz      short loc_180011FF2
0x180011fe7  mov     edx, ebx; int
0x180011fe9  mov     rcx, rax; this
0x180011fec  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x180011ff1  nop
0x180011ff2  mov     rdx, rax
0x180011ff5  lea     rcx, [rbp+arg_10]
0x180011ff9  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180011ffe  nop
0x180011fff  mov     rbx, [rbp+arg_10]
0x180012003  test    rbx, rbx
0x180012006  jz      short loc_180012040
0x180012008  cmp     qword ptr [rbx], 0
0x18001200c  jz      short loc_180012040
0x18001200e  mov     r8d, 0E0h; int
0x180012014  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x18001201b  mov     rcx, [rbx]; this
0x18001201e  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180012023  mov     [rbp+pExceptionObject], rbx
0x180012027  test    rbx, rbx
0x18001202a  jz      short loc_18001202F
0x18001202c  inc     dword ptr [rbx+8]
0x18001202f  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180012036  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001203a  call    _CxxThrowException_0
0x180012040  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180012047  lea     rcx, [rbp+var_58]; this
0x18001204b  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180012050  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180012057  lea     rcx, [rbp+var_58]; pExceptionObject
0x18001205b  call    _CxxThrowException_0
0x180012061  mov     rbx, [rbp+arg_18]
0x180012065  mov     rcx, rdi; void *
0x180012068  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18001206d  mov     rax, rbx
0x180012070  mov     rbx, [rsp+80h+arg_0]
0x180012078  add     rsp, 80h
0x18001207f  pop     r15
0x180012081  pop     r14
0x180012083  pop     rdi
0x180012084  pop     rsi
0x180012085  pop     rbp
0x180012086  retn
```
