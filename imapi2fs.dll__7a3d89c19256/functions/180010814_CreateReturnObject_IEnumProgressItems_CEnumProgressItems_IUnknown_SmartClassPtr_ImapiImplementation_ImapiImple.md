# CreateReturnObject<IEnumProgressItems,CEnumProgressItems>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)

- ea: `0x180010814`
- end: `0x180010a1f`
- name: `??$CreateReturnObject@UIEnumProgressItems@@VCEnumProgressItems@@@@YAPEAUIEnumProgressItems@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z`
- size: `523`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180010a30`
- `0x1800546d0`

## callees

- `0x180003a20`
- `0x180005040`
- `0x180007198`
- `0x18000960c`
- `0x18000c8d0`
- `0x18000f90c`
- `0x180010814`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18003b434`
- `0x180054944`
- `0x180088010`

## string_xrefs

- `0x180010890`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`
- `0x1800109ac`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`

## pseudocode

```c
__int64 __fastcall CreateReturnObject<IEnumProgressItems,CEnumProgressItems>(
        CIMAPISystemException *a1,
        CIMAPISystemException **a2)
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
  v4 = ATL::CComObject<CEnumProgressItems>::CreateInstance(&v18);
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
          &GUID_2c941fd6_975b_59be_a960_9a2a262853a5,
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
0x180010814  mov     [rsp-28h+arg_0], rbx
0x180010819  mov     [rsp-28h+arg_8], rdx
0x18001081e  push    rbp
0x18001081f  push    rsi
0x180010820  push    rdi
0x180010821  push    r14
0x180010823  push    r15
0x180010825  mov     rbp, rsp
0x180010828  sub     rsp, 80h
0x18001082f  mov     rdi, rdx
0x180010832  mov     r15, rcx
0x180010835  mov     [rbp+arg_10], 0
0x18001083d  lea     rcx, [rbp+arg_10]
0x180010841  call    ?CreateInstance@?$CComObject@VCEnumProgressItems@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CEnumProgressItems>::CreateInstance(ATL::CComObject<CEnumProgressItems> * *)
0x180010846  mov     ebx, eax
0x180010848  test    eax, eax
0x18001084a  jns     loc_1800108DD
0x180010850  mov     ecx, 58h ; 'X'; unsigned __int64
0x180010855  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001085a  mov     [rbp+arg_10], rax
0x18001085e  test    rax, rax
0x180010861  jz      short loc_18001086E
0x180010863  mov     edx, ebx; int
0x180010865  mov     rcx, rax; this
0x180010868  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18001086d  nop
0x18001086e  mov     rdx, rax
0x180010871  lea     rcx, [rbp+arg_10]
0x180010875  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001087a  nop
0x18001087b  mov     rbx, [rbp+arg_10]
0x18001087f  test    rbx, rbx
0x180010882  jz      short loc_1800108BC
0x180010884  cmp     qword ptr [rbx], 0
0x180010888  jz      short loc_1800108BC
0x18001088a  mov     r8d, 0D0h; int
0x180010890  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x180010897  mov     rcx, [rbx]; this
0x18001089a  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18001089f  mov     [rbp+pExceptionObject], rbx
0x1800108a3  test    rbx, rbx
0x1800108a6  jz      short loc_1800108AB
0x1800108a8  inc     dword ptr [rbx+8]
0x1800108ab  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800108b2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800108b6  call    _CxxThrowException_0
0x1800108bc  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x1800108c3  lea     rcx, [rbp+var_58]; this
0x1800108c7  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x1800108cc  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x1800108d3  lea     rcx, [rbp+var_58]; pExceptionObject
0x1800108d7  call    _CxxThrowException_0
0x1800108dd  mov     r14, [rbp+arg_10]
0x1800108e1  lea     rsi, [r14+48h]
0x1800108e5  mov     rax, [rsi]
0x1800108e8  mov     rcx, rsi
0x1800108eb  mov     rax, [rax+8]
0x1800108ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108f4  mov     rax, [rdi]
0x1800108f7  mov     [rbp+arg_10], rax
0x1800108fb  test    rax, rax
0x1800108fe  jz      short loc_180010903
0x180010900  inc     dword ptr [rax+8]
0x180010903  lea     rdx, [rbp+arg_10]
0x180010907  mov     rcx, r14
0x18001090a  call    ?Init@ImapiComReturnObject@@QEAAXV?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; ImapiComReturnObject::Init(SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x18001090f  mov     rax, [r14]
0x180010912  mov     rbx, [rax+10h]
0x180010916  mov     [rbp+arg_10], r15
0x18001091a  lea     rcx, [rbp+arg_10]
0x18001091e  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_AddRef(void)
0x180010923  lea     rdx, [rbp+arg_10]
0x180010927  mov     rcx, r14
0x18001092a  mov     rax, rbx
0x18001092d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010932  mov     [rbp+arg_18], 0
0x18001093a  mov     rax, [rsi]
0x18001093d  lea     r8, [rbp+arg_18]
0x180010941  lea     rdx, _GUID_2c941fd6_975b_59be_a960_9a2a262853a5
0x180010948  mov     rcx, rsi
0x18001094b  mov     rax, [rax]
0x18001094e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010953  mov     ebx, eax
0x180010955  mov     rdx, [rsi]
0x180010958  mov     rcx, rsi
0x18001095b  mov     rax, [rdx+10h]
0x18001095f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010964  test    ebx, ebx
0x180010966  jns     loc_1800109F9
0x18001096c  mov     ecx, 58h ; 'X'; unsigned __int64
0x180010971  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010976  mov     [rbp+arg_10], rax
0x18001097a  test    rax, rax
0x18001097d  jz      short loc_18001098A
0x18001097f  mov     edx, ebx; int
0x180010981  mov     rcx, rax; this
0x180010984  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x180010989  nop
0x18001098a  mov     rdx, rax
0x18001098d  lea     rcx, [rbp+arg_10]
0x180010991  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180010996  nop
0x180010997  mov     rbx, [rbp+arg_10]
0x18001099b  test    rbx, rbx
0x18001099e  jz      short loc_1800109D8
0x1800109a0  cmp     qword ptr [rbx], 0
0x1800109a4  jz      short loc_1800109D8
0x1800109a6  mov     r8d, 0E0h; int
0x1800109ac  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x1800109b3  mov     rcx, [rbx]; this
0x1800109b6  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x1800109bb  mov     [rbp+pExceptionObject], rbx
0x1800109bf  test    rbx, rbx
0x1800109c2  jz      short loc_1800109C7
0x1800109c4  inc     dword ptr [rbx+8]
0x1800109c7  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800109ce  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800109d2  call    _CxxThrowException_0
0x1800109d8  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x1800109df  lea     rcx, [rbp+var_58]; this
0x1800109e3  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x1800109e8  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x1800109ef  lea     rcx, [rbp+var_58]; pExceptionObject
0x1800109f3  call    _CxxThrowException_0
0x1800109f9  mov     rbx, [rbp+arg_18]
0x1800109fd  mov     rcx, rdi; void *
0x180010a00  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x180010a05  mov     rax, rbx
0x180010a08  mov     rbx, [rsp+80h+arg_0]
0x180010a10  add     rsp, 80h
0x180010a17  pop     r15
0x180010a19  pop     r14
0x180010a1b  pop     rdi
0x180010a1c  pop     rsi
0x180010a1d  pop     rbp
0x180010a1e  retn
```
