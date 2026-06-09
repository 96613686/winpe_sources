# CreateIndependantReturnObject<IStream,CFsiStream>(SmartClassPtr<ImapiImplementation,ImapiImplementation>)

- ea: `0x18000650c`
- end: `0x1800066e0`
- name: `??$CreateIndependantReturnObject@UIStream@@VCFsiStream@@@@YAPEAUIStream@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z`
- size: `468`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800066e8`

## callees

- `0x180003a20`
- `0x180005040`
- `0x18000650c`
- `0x180007198`
- `0x18000960c`
- `0x18000c8d0`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18003b2e4`
- `0x18003b434`
- `0x180088010`

## string_xrefs

- `0x18000657f`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`
- `0x180006678`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CreateIndependantReturnObject<IStream,CFsiStream>(CIMAPISystemException **a1)
{
  int v2; // ebx
  CIMAPISystemException *v3; // rax
  CIMAPISystemException *v4; // rbx
  CIMAPISystemException *v5; // rsi
  char *v6; // rbx
  CIMAPISystemException *v7; // rax
  int v8; // esi
  CIMAPISystemException *v9; // rax
  CIMAPISystemException *v10; // rbx
  __int64 v11; // rbx
  _BYTE v13[128]; // [rsp+20h] [rbp-29h] BYREF
  CIMAPISystemException *v14; // [rsp+B8h] [rbp+6Fh] BYREF
  __int64 v15; // [rsp+C0h] [rbp+77h] BYREF
  CIMAPISystemException *pExceptionObject; // [rsp+C8h] [rbp+7Fh] BYREF

  v14 = 0;
  v2 = ATL::CComObject<CFsiStream>::CreateInstance(&v14);
  if ( v2 < 0 )
  {
    v3 = (CIMAPISystemException *)operator new(0x58u);
    v14 = v3;
    if ( v3 )
      v3 = CIMAPISystemException::CIMAPISystemException(v3, v2);
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v14, v3);
    v4 = v14;
    if ( v14 && *(_QWORD *)v14 )
    {
      CIMAPIException::SetCodeRefInfo(
        *(CIMAPIException **)v14,
        "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\ImapiComInterface.h",
        239);
      pExceptionObject = v4;
      if ( v4 )
        ++*((_DWORD *)v4 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v13, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v13;
  }
  v5 = v14;
  v6 = (char *)v14 + 72;
  (*(void (__fastcall **)(__int64))(*((_QWORD *)v14 + 9) + 8LL))((__int64)v14 + 72);
  v7 = *a1;
  v14 = v7;
  if ( v7 )
    ++*((_DWORD *)v7 + 2);
  ImapiComReturnObject::Init(v5, &v14);
  v15 = 0;
  v8 = (**(__int64 (__fastcall ***)(char *, GUID *, __int64 *))v6)(v6, &GUID_0000000c_0000_0000_c000_000000000046, &v15);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v8 < 0 )
  {
    v9 = (CIMAPISystemException *)operator new(0x58u);
    v14 = v9;
    if ( v9 )
      v9 = CIMAPISystemException::CIMAPISystemException(v9, v8);
    SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v14, v9);
    v10 = v14;
    if ( v14 && *(_QWORD *)v14 )
    {
      CIMAPIException::SetCodeRefInfo(
        *(CIMAPIException **)v14,
        "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\ImapiComInterface.h",
        249);
      pExceptionObject = v10;
      if ( v10 )
        ++*((_DWORD *)v10 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v13, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v13;
  }
  v11 = v15;
  SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(a1);
  return v11;
}

```

## disassembly

```asm
0x18000650c  mov     [rsp-8+arg_0], rcx
0x180006511  push    rbp
0x180006512  push    rbx
0x180006513  push    rsi
0x180006514  push    rdi
0x180006515  lea     rbp, [rsp-3Fh]
0x18000651a  sub     rsp, 88h
0x180006521  mov     rdi, rcx
0x180006524  mov     [rbp+57h+arg_8], 0
0x18000652c  lea     rcx, [rbp+57h+arg_8]
0x180006530  call    ?CreateInstance@?$CComObject@VCFsiStream@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFsiStream>::CreateInstance(ATL::CComObject<CFsiStream> * *)
0x180006535  mov     ebx, eax
0x180006537  test    eax, eax
0x180006539  jns     loc_1800065CC
0x18000653f  mov     ecx, 58h ; 'X'; unsigned __int64
0x180006544  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006549  mov     [rbp+57h+arg_8], rax
0x18000654d  test    rax, rax
0x180006550  jz      short loc_18000655D
0x180006552  mov     edx, ebx; int
0x180006554  mov     rcx, rax; this
0x180006557  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18000655c  nop
0x18000655d  mov     rdx, rax
0x180006560  lea     rcx, [rbp+57h+arg_8]
0x180006564  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180006569  nop
0x18000656a  mov     rbx, [rbp+57h+arg_8]
0x18000656e  test    rbx, rbx
0x180006571  jz      short loc_1800065AB
0x180006573  cmp     qword ptr [rbx], 0
0x180006577  jz      short loc_1800065AB
0x180006579  mov     r8d, 0EFh; int
0x18000657f  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x180006586  mov     rcx, [rbx]; this
0x180006589  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18000658e  mov     [rbp+57h+pExceptionObject], rbx
0x180006592  test    rbx, rbx
0x180006595  jz      short loc_18000659A
0x180006597  inc     dword ptr [rbx+8]
0x18000659a  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800065a1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800065a5  call    _CxxThrowException_0
0x1800065ab  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x1800065b2  lea     rcx, [rbp+57h+var_80]; this
0x1800065b6  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x1800065bb  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x1800065c2  lea     rcx, [rbp+57h+var_80]; pExceptionObject
0x1800065c6  call    _CxxThrowException_0
0x1800065cc  mov     rsi, [rbp+57h+arg_8]
0x1800065d0  lea     rbx, [rsi+48h]
0x1800065d4  mov     rax, [rbx]
0x1800065d7  mov     rcx, rbx
0x1800065da  mov     rax, [rax+8]
0x1800065de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065e3  mov     rax, [rdi]
0x1800065e6  mov     [rbp+57h+arg_8], rax
0x1800065ea  test    rax, rax
0x1800065ed  jz      short loc_1800065F2
0x1800065ef  inc     dword ptr [rax+8]
0x1800065f2  lea     rdx, [rbp+57h+arg_8]
0x1800065f6  mov     rcx, rsi
0x1800065f9  call    ?Init@ImapiComReturnObject@@QEAAXV?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; ImapiComReturnObject::Init(SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x1800065fe  mov     [rbp+57h+arg_10], 0
0x180006606  mov     rax, [rbx]
0x180006609  lea     r8, [rbp+57h+arg_10]
0x18000660d  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180006614  mov     rcx, rbx
0x180006617  mov     rax, [rax]
0x18000661a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000661f  mov     esi, eax
0x180006621  mov     rdx, [rbx]
0x180006624  mov     rcx, rbx
0x180006627  mov     rax, [rdx+10h]
0x18000662b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006630  test    esi, esi
0x180006632  jns     loc_1800066C5
0x180006638  mov     ecx, 58h ; 'X'; unsigned __int64
0x18000663d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006642  mov     [rbp+57h+arg_8], rax
0x180006646  test    rax, rax
0x180006649  jz      short loc_180006656
0x18000664b  mov     edx, esi; int
0x18000664d  mov     rcx, rax; this
0x180006650  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x180006655  nop
0x180006656  mov     rdx, rax
0x180006659  lea     rcx, [rbp+57h+arg_8]
0x18000665d  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180006662  nop
0x180006663  mov     rbx, [rbp+57h+arg_8]
0x180006667  test    rbx, rbx
0x18000666a  jz      short loc_1800066A4
0x18000666c  cmp     qword ptr [rbx], 0
0x180006670  jz      short loc_1800066A4
0x180006672  mov     r8d, 0F9h; int
0x180006678  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x18000667f  mov     rcx, [rbx]; this
0x180006682  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180006687  mov     [rbp+57h+pExceptionObject], rbx
0x18000668b  test    rbx, rbx
0x18000668e  jz      short loc_180006693
0x180006690  inc     dword ptr [rbx+8]
0x180006693  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18000669a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18000669e  call    _CxxThrowException_0
0x1800066a4  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x1800066ab  lea     rcx, [rbp+57h+var_80]; this
0x1800066af  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x1800066b4  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x1800066bb  lea     rcx, [rbp+57h+var_80]; pExceptionObject
0x1800066bf  call    _CxxThrowException_0
0x1800066c5  mov     rbx, [rbp+57h+arg_10]
0x1800066c9  mov     rcx, rdi; void *
0x1800066cc  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x1800066d1  mov     rax, rbx
0x1800066d4  add     rsp, 88h
0x1800066db  pop     rdi
0x1800066dc  pop     rsi
0x1800066dd  pop     rbx
0x1800066de  pop     rbp
0x1800066df  retn
```
