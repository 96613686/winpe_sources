# CreateReturnObject<IFsiNamedStreams,CFsiNamedStreams>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)

- ea: `0x180021f6c`
- end: `0x180022177`
- name: `??$CreateReturnObject@UIFsiNamedStreams@@VCFsiNamedStreams@@@@YAPEAUIFsiNamedStreams@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180021d10`

## callees

- `0x180003a20`
- `0x180005040`
- `0x180007198`
- `0x18000960c`
- `0x18000c8d0`
- `0x18000f90c`
- `0x180021f6c`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18003b434`
- `0x18003da70`
- `0x180088010`

## string_xrefs

- `0x180021fe8`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`
- `0x180022104`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`

## pseudocode

```c
__int64 __fastcall CreateReturnObject<IFsiNamedStreams,CFsiNamedStreams>(
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
  v4 = ATL::CComObject<CFsiNamedStreams>::CreateInstance(&v18);
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
          &GUID_ed79ba56_5294_4250_8d46_f9aecee23459,
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
0x180021f6c  mov     [rsp-28h+arg_0], rbx
0x180021f71  mov     [rsp-28h+arg_8], rdx
0x180021f76  push    rbp
0x180021f77  push    rsi
0x180021f78  push    rdi
0x180021f79  push    r14
0x180021f7b  push    r15
0x180021f7d  mov     rbp, rsp
0x180021f80  sub     rsp, 80h
0x180021f87  mov     rdi, rdx
0x180021f8a  mov     r15, rcx
0x180021f8d  mov     [rbp+arg_10], 0
0x180021f95  lea     rcx, [rbp+arg_10]
0x180021f99  call    ?CreateInstance@?$CComObject@VCFsiNamedStreams@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFsiNamedStreams>::CreateInstance(ATL::CComObject<CFsiNamedStreams> * *)
0x180021f9e  mov     ebx, eax
0x180021fa0  test    eax, eax
0x180021fa2  jns     loc_180022035
0x180021fa8  mov     ecx, 58h ; 'X'; unsigned __int64
0x180021fad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021fb2  mov     [rbp+arg_10], rax
0x180021fb6  test    rax, rax
0x180021fb9  jz      short loc_180021FC6
0x180021fbb  mov     edx, ebx; int
0x180021fbd  mov     rcx, rax; this
0x180021fc0  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x180021fc5  nop
0x180021fc6  mov     rdx, rax
0x180021fc9  lea     rcx, [rbp+arg_10]
0x180021fcd  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180021fd2  nop
0x180021fd3  mov     rbx, [rbp+arg_10]
0x180021fd7  test    rbx, rbx
0x180021fda  jz      short loc_180022014
0x180021fdc  cmp     qword ptr [rbx], 0
0x180021fe0  jz      short loc_180022014
0x180021fe2  mov     r8d, 0D0h; int
0x180021fe8  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x180021fef  mov     rcx, [rbx]; this
0x180021ff2  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180021ff7  mov     [rbp+pExceptionObject], rbx
0x180021ffb  test    rbx, rbx
0x180021ffe  jz      short loc_180022003
0x180022000  inc     dword ptr [rbx+8]
0x180022003  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18002200a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002200e  call    _CxxThrowException_0
0x180022014  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18002201b  lea     rcx, [rbp+var_58]; this
0x18002201f  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180022024  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18002202b  lea     rcx, [rbp+var_58]; pExceptionObject
0x18002202f  call    _CxxThrowException_0
0x180022035  mov     r14, [rbp+arg_10]
0x180022039  lea     rsi, [r14+48h]
0x18002203d  mov     rax, [rsi]
0x180022040  mov     rcx, rsi
0x180022043  mov     rax, [rax+8]
0x180022047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002204c  mov     rax, [rdi]
0x18002204f  mov     [rbp+arg_10], rax
0x180022053  test    rax, rax
0x180022056  jz      short loc_18002205B
0x180022058  inc     dword ptr [rax+8]
0x18002205b  lea     rdx, [rbp+arg_10]
0x18002205f  mov     rcx, r14
0x180022062  call    ?Init@ImapiComReturnObject@@QEAAXV?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; ImapiComReturnObject::Init(SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x180022067  mov     rax, [r14]
0x18002206a  mov     rbx, [rax+10h]
0x18002206e  mov     [rbp+arg_10], r15
0x180022072  lea     rcx, [rbp+arg_10]
0x180022076  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_AddRef(void)
0x18002207b  lea     rdx, [rbp+arg_10]
0x18002207f  mov     rcx, r14
0x180022082  mov     rax, rbx
0x180022085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002208a  mov     [rbp+arg_18], 0
0x180022092  mov     rax, [rsi]
0x180022095  lea     r8, [rbp+arg_18]
0x180022099  lea     rdx, _GUID_ed79ba56_5294_4250_8d46_f9aecee23459
0x1800220a0  mov     rcx, rsi
0x1800220a3  mov     rax, [rax]
0x1800220a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220ab  mov     ebx, eax
0x1800220ad  mov     rdx, [rsi]
0x1800220b0  mov     rcx, rsi
0x1800220b3  mov     rax, [rdx+10h]
0x1800220b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220bc  test    ebx, ebx
0x1800220be  jns     loc_180022151
0x1800220c4  mov     ecx, 58h ; 'X'; unsigned __int64
0x1800220c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800220ce  mov     [rbp+arg_10], rax
0x1800220d2  test    rax, rax
0x1800220d5  jz      short loc_1800220E2
0x1800220d7  mov     edx, ebx; int
0x1800220d9  mov     rcx, rax; this
0x1800220dc  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x1800220e1  nop
0x1800220e2  mov     rdx, rax
0x1800220e5  lea     rcx, [rbp+arg_10]
0x1800220e9  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x1800220ee  nop
0x1800220ef  mov     rbx, [rbp+arg_10]
0x1800220f3  test    rbx, rbx
0x1800220f6  jz      short loc_180022130
0x1800220f8  cmp     qword ptr [rbx], 0
0x1800220fc  jz      short loc_180022130
0x1800220fe  mov     r8d, 0E0h; int
0x180022104  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x18002210b  mov     rcx, [rbx]; this
0x18002210e  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180022113  mov     [rbp+pExceptionObject], rbx
0x180022117  test    rbx, rbx
0x18002211a  jz      short loc_18002211F
0x18002211c  inc     dword ptr [rbx+8]
0x18002211f  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180022126  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002212a  call    _CxxThrowException_0
0x180022130  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180022137  lea     rcx, [rbp+var_58]; this
0x18002213b  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180022140  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180022147  lea     rcx, [rbp+var_58]; pExceptionObject
0x18002214b  call    _CxxThrowException_0
0x180022151  mov     rbx, [rbp+arg_18]
0x180022155  mov     rcx, rdi; void *
0x180022158  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18002215d  mov     rax, rbx
0x180022160  mov     rbx, [rsp+80h+arg_0]
0x180022168  add     rsp, 80h
0x18002216f  pop     r15
0x180022171  pop     r14
0x180022173  pop     rdi
0x180022174  pop     rsi
0x180022175  pop     rbp
0x180022176  retn
```
