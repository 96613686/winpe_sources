# CreateReturnObject<IFsiFileItem2,CFsiFileItem>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)

- ea: `0x18001d0f4`
- end: `0x18001d2ff`
- name: `??$CreateReturnObject@UIFsiFileItem2@@VCFsiFileItem@@@@YAPEAUIFsiFileItem2@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18001ce80`

## callees

- `0x180003a20`
- `0x180005040`
- `0x180007198`
- `0x18000960c`
- `0x18000c8d0`
- `0x18000f90c`
- `0x18001d0f4`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18003b434`
- `0x18003d954`
- `0x180088010`

## string_xrefs

- `0x18001d170`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`
- `0x18001d28c`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`

## pseudocode

```c
__int64 __fastcall CreateReturnObject<IFsiFileItem2,CFsiFileItem>(
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
          &GUID_199d0c19_11e1_40eb_8ec2_c8c822a07792,
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
0x18001d0f4  mov     [rsp-28h+arg_0], rbx
0x18001d0f9  mov     [rsp-28h+arg_8], rdx
0x18001d0fe  push    rbp
0x18001d0ff  push    rsi
0x18001d100  push    rdi
0x18001d101  push    r14
0x18001d103  push    r15
0x18001d105  mov     rbp, rsp
0x18001d108  sub     rsp, 80h
0x18001d10f  mov     rdi, rdx
0x18001d112  mov     r15, rcx
0x18001d115  mov     [rbp+arg_10], 0
0x18001d11d  lea     rcx, [rbp+arg_10]
0x18001d121  call    ?CreateInstance@?$CComObject@VCFsiFileItem@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFsiFileItem>::CreateInstance(ATL::CComObject<CFsiFileItem> * *)
0x18001d126  mov     ebx, eax
0x18001d128  test    eax, eax
0x18001d12a  jns     loc_18001D1BD
0x18001d130  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001d135  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d13a  mov     [rbp+arg_10], rax
0x18001d13e  test    rax, rax
0x18001d141  jz      short loc_18001D14E
0x18001d143  mov     edx, ebx; int
0x18001d145  mov     rcx, rax; this
0x18001d148  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18001d14d  nop
0x18001d14e  mov     rdx, rax
0x18001d151  lea     rcx, [rbp+arg_10]
0x18001d155  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001d15a  nop
0x18001d15b  mov     rbx, [rbp+arg_10]
0x18001d15f  test    rbx, rbx
0x18001d162  jz      short loc_18001D19C
0x18001d164  cmp     qword ptr [rbx], 0
0x18001d168  jz      short loc_18001D19C
0x18001d16a  mov     r8d, 0D0h; int
0x18001d170  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x18001d177  mov     rcx, [rbx]; this
0x18001d17a  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18001d17f  mov     [rbp+pExceptionObject], rbx
0x18001d183  test    rbx, rbx
0x18001d186  jz      short loc_18001D18B
0x18001d188  inc     dword ptr [rbx+8]
0x18001d18b  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18001d192  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d196  call    _CxxThrowException_0
0x18001d19c  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18001d1a3  lea     rcx, [rbp+var_58]; this
0x18001d1a7  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18001d1ac  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18001d1b3  lea     rcx, [rbp+var_58]; pExceptionObject
0x18001d1b7  call    _CxxThrowException_0
0x18001d1bd  mov     r14, [rbp+arg_10]
0x18001d1c1  lea     rsi, [r14+48h]
0x18001d1c5  mov     rax, [rsi]
0x18001d1c8  mov     rcx, rsi
0x18001d1cb  mov     rax, [rax+8]
0x18001d1cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1d4  mov     rax, [rdi]
0x18001d1d7  mov     [rbp+arg_10], rax
0x18001d1db  test    rax, rax
0x18001d1de  jz      short loc_18001D1E3
0x18001d1e0  inc     dword ptr [rax+8]
0x18001d1e3  lea     rdx, [rbp+arg_10]
0x18001d1e7  mov     rcx, r14
0x18001d1ea  call    ?Init@ImapiComReturnObject@@QEAAXV?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; ImapiComReturnObject::Init(SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x18001d1ef  mov     rax, [r14]
0x18001d1f2  mov     rbx, [rax+10h]
0x18001d1f6  mov     [rbp+arg_10], r15
0x18001d1fa  lea     rcx, [rbp+arg_10]
0x18001d1fe  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_AddRef(void)
0x18001d203  lea     rdx, [rbp+arg_10]
0x18001d207  mov     rcx, r14
0x18001d20a  mov     rax, rbx
0x18001d20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d212  mov     [rbp+arg_18], 0
0x18001d21a  mov     rax, [rsi]
0x18001d21d  lea     r8, [rbp+arg_18]
0x18001d221  lea     rdx, _GUID_199d0c19_11e1_40eb_8ec2_c8c822a07792
0x18001d228  mov     rcx, rsi
0x18001d22b  mov     rax, [rax]
0x18001d22e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d233  mov     ebx, eax
0x18001d235  mov     rdx, [rsi]
0x18001d238  mov     rcx, rsi
0x18001d23b  mov     rax, [rdx+10h]
0x18001d23f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d244  test    ebx, ebx
0x18001d246  jns     loc_18001D2D9
0x18001d24c  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001d251  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d256  mov     [rbp+arg_10], rax
0x18001d25a  test    rax, rax
0x18001d25d  jz      short loc_18001D26A
0x18001d25f  mov     edx, ebx; int
0x18001d261  mov     rcx, rax; this
0x18001d264  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18001d269  nop
0x18001d26a  mov     rdx, rax
0x18001d26d  lea     rcx, [rbp+arg_10]
0x18001d271  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001d276  nop
0x18001d277  mov     rbx, [rbp+arg_10]
0x18001d27b  test    rbx, rbx
0x18001d27e  jz      short loc_18001D2B8
0x18001d280  cmp     qword ptr [rbx], 0
0x18001d284  jz      short loc_18001D2B8
0x18001d286  mov     r8d, 0E0h; int
0x18001d28c  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x18001d293  mov     rcx, [rbx]; this
0x18001d296  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18001d29b  mov     [rbp+pExceptionObject], rbx
0x18001d29f  test    rbx, rbx
0x18001d2a2  jz      short loc_18001D2A7
0x18001d2a4  inc     dword ptr [rbx+8]
0x18001d2a7  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18001d2ae  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d2b2  call    _CxxThrowException_0
0x18001d2b8  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18001d2bf  lea     rcx, [rbp+var_58]; this
0x18001d2c3  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18001d2c8  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18001d2cf  lea     rcx, [rbp+var_58]; pExceptionObject
0x18001d2d3  call    _CxxThrowException_0
0x18001d2d9  mov     rbx, [rbp+arg_18]
0x18001d2dd  mov     rcx, rdi; void *
0x18001d2e0  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18001d2e5  mov     rax, rbx
0x18001d2e8  mov     rbx, [rsp+80h+arg_0]
0x18001d2f0  add     rsp, 80h
0x18001d2f7  pop     r15
0x18001d2f9  pop     r14
0x18001d2fb  pop     rdi
0x18001d2fc  pop     rsi
0x18001d2fd  pop     rbp
0x18001d2fe  retn
```
