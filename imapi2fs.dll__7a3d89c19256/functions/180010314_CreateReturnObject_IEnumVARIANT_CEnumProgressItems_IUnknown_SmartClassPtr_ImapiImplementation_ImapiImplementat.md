# CreateReturnObject<IEnumVARIANT,CEnumProgressItems>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)

- ea: `0x180010314`
- end: `0x18001051f`
- name: `??$CreateReturnObject@UIEnumVARIANT@@VCEnumProgressItems@@@@YAPEAUIEnumVARIANT@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z`
- size: `523`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180010530`
- `0x180056790`

## callees

- `0x180003a20`
- `0x180005040`
- `0x180007198`
- `0x18000960c`
- `0x18000c8d0`
- `0x18000f90c`
- `0x180010314`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18003b434`
- `0x180054944`
- `0x180088010`

## string_xrefs

- `0x180010390`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`
- `0x1800104ac`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CreateReturnObject<IEnumVARIANT,CEnumProgressItems>(
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
          &GUID_00020404_0000_0000_c000_000000000046,
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
0x180010314  mov     [rsp-28h+arg_0], rbx
0x180010319  mov     [rsp-28h+arg_8], rdx
0x18001031e  push    rbp
0x18001031f  push    rsi
0x180010320  push    rdi
0x180010321  push    r14
0x180010323  push    r15
0x180010325  mov     rbp, rsp
0x180010328  sub     rsp, 80h
0x18001032f  mov     rdi, rdx
0x180010332  mov     r15, rcx
0x180010335  mov     [rbp+arg_10], 0
0x18001033d  lea     rcx, [rbp+arg_10]
0x180010341  call    ?CreateInstance@?$CComObject@VCEnumProgressItems@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CEnumProgressItems>::CreateInstance(ATL::CComObject<CEnumProgressItems> * *)
0x180010346  mov     ebx, eax
0x180010348  test    eax, eax
0x18001034a  jns     loc_1800103DD
0x180010350  mov     ecx, 58h ; 'X'; unsigned __int64
0x180010355  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001035a  mov     [rbp+arg_10], rax
0x18001035e  test    rax, rax
0x180010361  jz      short loc_18001036E
0x180010363  mov     edx, ebx; int
0x180010365  mov     rcx, rax; this
0x180010368  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18001036d  nop
0x18001036e  mov     rdx, rax
0x180010371  lea     rcx, [rbp+arg_10]
0x180010375  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001037a  nop
0x18001037b  mov     rbx, [rbp+arg_10]
0x18001037f  test    rbx, rbx
0x180010382  jz      short loc_1800103BC
0x180010384  cmp     qword ptr [rbx], 0
0x180010388  jz      short loc_1800103BC
0x18001038a  mov     r8d, 0D0h; int
0x180010390  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x180010397  mov     rcx, [rbx]; this
0x18001039a  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18001039f  mov     [rbp+pExceptionObject], rbx
0x1800103a3  test    rbx, rbx
0x1800103a6  jz      short loc_1800103AB
0x1800103a8  inc     dword ptr [rbx+8]
0x1800103ab  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800103b2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800103b6  call    _CxxThrowException_0
0x1800103bc  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x1800103c3  lea     rcx, [rbp+var_58]; this
0x1800103c7  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x1800103cc  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x1800103d3  lea     rcx, [rbp+var_58]; pExceptionObject
0x1800103d7  call    _CxxThrowException_0
0x1800103dd  mov     r14, [rbp+arg_10]
0x1800103e1  lea     rsi, [r14+48h]
0x1800103e5  mov     rax, [rsi]
0x1800103e8  mov     rcx, rsi
0x1800103eb  mov     rax, [rax+8]
0x1800103ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103f4  mov     rax, [rdi]
0x1800103f7  mov     [rbp+arg_10], rax
0x1800103fb  test    rax, rax
0x1800103fe  jz      short loc_180010403
0x180010400  inc     dword ptr [rax+8]
0x180010403  lea     rdx, [rbp+arg_10]
0x180010407  mov     rcx, r14
0x18001040a  call    ?Init@ImapiComReturnObject@@QEAAXV?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; ImapiComReturnObject::Init(SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x18001040f  mov     rax, [r14]
0x180010412  mov     rbx, [rax+10h]
0x180010416  mov     [rbp+arg_10], r15
0x18001041a  lea     rcx, [rbp+arg_10]
0x18001041e  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_AddRef(void)
0x180010423  lea     rdx, [rbp+arg_10]
0x180010427  mov     rcx, r14
0x18001042a  mov     rax, rbx
0x18001042d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010432  mov     [rbp+arg_18], 0
0x18001043a  mov     rax, [rsi]
0x18001043d  lea     r8, [rbp+arg_18]
0x180010441  lea     rdx, _GUID_00020404_0000_0000_c000_000000000046
0x180010448  mov     rcx, rsi
0x18001044b  mov     rax, [rax]
0x18001044e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010453  mov     ebx, eax
0x180010455  mov     rdx, [rsi]
0x180010458  mov     rcx, rsi
0x18001045b  mov     rax, [rdx+10h]
0x18001045f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010464  test    ebx, ebx
0x180010466  jns     loc_1800104F9
0x18001046c  mov     ecx, 58h ; 'X'; unsigned __int64
0x180010471  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010476  mov     [rbp+arg_10], rax
0x18001047a  test    rax, rax
0x18001047d  jz      short loc_18001048A
0x18001047f  mov     edx, ebx; int
0x180010481  mov     rcx, rax; this
0x180010484  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x180010489  nop
0x18001048a  mov     rdx, rax
0x18001048d  lea     rcx, [rbp+arg_10]
0x180010491  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180010496  nop
0x180010497  mov     rbx, [rbp+arg_10]
0x18001049b  test    rbx, rbx
0x18001049e  jz      short loc_1800104D8
0x1800104a0  cmp     qword ptr [rbx], 0
0x1800104a4  jz      short loc_1800104D8
0x1800104a6  mov     r8d, 0E0h; int
0x1800104ac  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x1800104b3  mov     rcx, [rbx]; this
0x1800104b6  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x1800104bb  mov     [rbp+pExceptionObject], rbx
0x1800104bf  test    rbx, rbx
0x1800104c2  jz      short loc_1800104C7
0x1800104c4  inc     dword ptr [rbx+8]
0x1800104c7  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800104ce  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800104d2  call    _CxxThrowException_0
0x1800104d8  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x1800104df  lea     rcx, [rbp+var_58]; this
0x1800104e3  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x1800104e8  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x1800104ef  lea     rcx, [rbp+var_58]; pExceptionObject
0x1800104f3  call    _CxxThrowException_0
0x1800104f9  mov     rbx, [rbp+arg_18]
0x1800104fd  mov     rcx, rdi; void *
0x180010500  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x180010505  mov     rax, rbx
0x180010508  mov     rbx, [rsp+80h+arg_0]
0x180010510  add     rsp, 80h
0x180010517  pop     r15
0x180010519  pop     r14
0x18001051b  pop     rdi
0x18001051c  pop     rsi
0x18001051d  pop     rbp
0x18001051e  retn
```
