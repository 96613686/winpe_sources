# CreateReturnObject<IEnumFsiItems,CEnumFsiItems>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)

- ea: `0x18001d694`
- end: `0x18001d89f`
- name: `??$CreateReturnObject@UIEnumFsiItems@@VCEnumFsiItems@@@@YAPEAUIEnumFsiItems@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z`
- size: `523`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18000fd20`
- `0x18001d530`

## callees

- `0x180003a20`
- `0x180005040`
- `0x180007198`
- `0x18000960c`
- `0x18000c8d0`
- `0x18000f90c`
- `0x18001d694`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18003b434`
- `0x18003d79c`
- `0x180088010`

## string_xrefs

- `0x18001d710`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`
- `0x18001d82c`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`

## pseudocode

```c
__int64 __fastcall CreateReturnObject<IEnumFsiItems,CEnumFsiItems>(
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
  v4 = ATL::CComObject<CEnumFsiItems>::CreateInstance(&v18);
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
          &GUID_2c941fda_975b_59be_a960_9a2a262853a5,
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
0x18001d694  mov     [rsp-28h+arg_0], rbx
0x18001d699  mov     [rsp-28h+arg_8], rdx
0x18001d69e  push    rbp
0x18001d69f  push    rsi
0x18001d6a0  push    rdi
0x18001d6a1  push    r14
0x18001d6a3  push    r15
0x18001d6a5  mov     rbp, rsp
0x18001d6a8  sub     rsp, 80h
0x18001d6af  mov     rdi, rdx
0x18001d6b2  mov     r15, rcx
0x18001d6b5  mov     [rbp+arg_10], 0
0x18001d6bd  lea     rcx, [rbp+arg_10]
0x18001d6c1  call    ?CreateInstance@?$CComObject@VCEnumFsiItems@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CEnumFsiItems>::CreateInstance(ATL::CComObject<CEnumFsiItems> * *)
0x18001d6c6  mov     ebx, eax
0x18001d6c8  test    eax, eax
0x18001d6ca  jns     loc_18001D75D
0x18001d6d0  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001d6d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d6da  mov     [rbp+arg_10], rax
0x18001d6de  test    rax, rax
0x18001d6e1  jz      short loc_18001D6EE
0x18001d6e3  mov     edx, ebx; int
0x18001d6e5  mov     rcx, rax; this
0x18001d6e8  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18001d6ed  nop
0x18001d6ee  mov     rdx, rax
0x18001d6f1  lea     rcx, [rbp+arg_10]
0x18001d6f5  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001d6fa  nop
0x18001d6fb  mov     rbx, [rbp+arg_10]
0x18001d6ff  test    rbx, rbx
0x18001d702  jz      short loc_18001D73C
0x18001d704  cmp     qword ptr [rbx], 0
0x18001d708  jz      short loc_18001D73C
0x18001d70a  mov     r8d, 0D0h; int
0x18001d710  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x18001d717  mov     rcx, [rbx]; this
0x18001d71a  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18001d71f  mov     [rbp+pExceptionObject], rbx
0x18001d723  test    rbx, rbx
0x18001d726  jz      short loc_18001D72B
0x18001d728  inc     dword ptr [rbx+8]
0x18001d72b  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18001d732  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d736  call    _CxxThrowException_0
0x18001d73c  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18001d743  lea     rcx, [rbp+var_58]; this
0x18001d747  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18001d74c  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18001d753  lea     rcx, [rbp+var_58]; pExceptionObject
0x18001d757  call    _CxxThrowException_0
0x18001d75d  mov     r14, [rbp+arg_10]
0x18001d761  lea     rsi, [r14+48h]
0x18001d765  mov     rax, [rsi]
0x18001d768  mov     rcx, rsi
0x18001d76b  mov     rax, [rax+8]
0x18001d76f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d774  mov     rax, [rdi]
0x18001d777  mov     [rbp+arg_10], rax
0x18001d77b  test    rax, rax
0x18001d77e  jz      short loc_18001D783
0x18001d780  inc     dword ptr [rax+8]
0x18001d783  lea     rdx, [rbp+arg_10]
0x18001d787  mov     rcx, r14
0x18001d78a  call    ?Init@ImapiComReturnObject@@QEAAXV?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; ImapiComReturnObject::Init(SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x18001d78f  mov     rax, [r14]
0x18001d792  mov     rbx, [rax+10h]
0x18001d796  mov     [rbp+arg_10], r15
0x18001d79a  lea     rcx, [rbp+arg_10]
0x18001d79e  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_AddRef(void)
0x18001d7a3  lea     rdx, [rbp+arg_10]
0x18001d7a7  mov     rcx, r14
0x18001d7aa  mov     rax, rbx
0x18001d7ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7b2  mov     [rbp+arg_18], 0
0x18001d7ba  mov     rax, [rsi]
0x18001d7bd  lea     r8, [rbp+arg_18]
0x18001d7c1  lea     rdx, _GUID_2c941fda_975b_59be_a960_9a2a262853a5
0x18001d7c8  mov     rcx, rsi
0x18001d7cb  mov     rax, [rax]
0x18001d7ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7d3  mov     ebx, eax
0x18001d7d5  mov     rdx, [rsi]
0x18001d7d8  mov     rcx, rsi
0x18001d7db  mov     rax, [rdx+10h]
0x18001d7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7e4  test    ebx, ebx
0x18001d7e6  jns     loc_18001D879
0x18001d7ec  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001d7f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d7f6  mov     [rbp+arg_10], rax
0x18001d7fa  test    rax, rax
0x18001d7fd  jz      short loc_18001D80A
0x18001d7ff  mov     edx, ebx; int
0x18001d801  mov     rcx, rax; this
0x18001d804  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18001d809  nop
0x18001d80a  mov     rdx, rax
0x18001d80d  lea     rcx, [rbp+arg_10]
0x18001d811  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001d816  nop
0x18001d817  mov     rbx, [rbp+arg_10]
0x18001d81b  test    rbx, rbx
0x18001d81e  jz      short loc_18001D858
0x18001d820  cmp     qword ptr [rbx], 0
0x18001d824  jz      short loc_18001D858
0x18001d826  mov     r8d, 0E0h; int
0x18001d82c  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x18001d833  mov     rcx, [rbx]; this
0x18001d836  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18001d83b  mov     [rbp+pExceptionObject], rbx
0x18001d83f  test    rbx, rbx
0x18001d842  jz      short loc_18001D847
0x18001d844  inc     dword ptr [rbx+8]
0x18001d847  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18001d84e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001d852  call    _CxxThrowException_0
0x18001d858  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18001d85f  lea     rcx, [rbp+var_58]; this
0x18001d863  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18001d868  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18001d86f  lea     rcx, [rbp+var_58]; pExceptionObject
0x18001d873  call    _CxxThrowException_0
0x18001d879  mov     rbx, [rbp+arg_18]
0x18001d87d  mov     rcx, rdi; void *
0x18001d880  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18001d885  mov     rax, rbx
0x18001d888  mov     rbx, [rsp+80h+arg_0]
0x18001d890  add     rsp, 80h
0x18001d897  pop     r15
0x18001d899  pop     r14
0x18001d89b  pop     rdi
0x18001d89c  pop     rsi
0x18001d89d  pop     rbp
0x18001d89e  retn
```
