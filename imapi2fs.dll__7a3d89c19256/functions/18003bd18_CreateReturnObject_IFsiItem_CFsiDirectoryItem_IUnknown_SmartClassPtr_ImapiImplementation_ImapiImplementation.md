# CreateReturnObject<IFsiItem,CFsiDirectoryItem>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)

- ea: `0x18003bd18`
- end: `0x18003bf23`
- name: `??$CreateReturnObject@UIFsiItem@@VCFsiDirectoryItem@@@@YAPEAUIFsiItem@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z`
- size: `523`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

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
- `0x18003bd18`
- `0x18003d844`
- `0x180088010`

## string_xrefs

- `0x18003bd94`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`
- `0x18003beb0`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`

## pseudocode

```c
__int64 __fastcall CreateReturnObject<IFsiItem,CFsiDirectoryItem>(
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
  v4 = ATL::CComObject<CFsiDirectoryItem>::CreateInstance(&v18);
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
0x18003bd18  mov     [rsp-28h+arg_0], rbx
0x18003bd1d  mov     [rsp-28h+arg_8], rdx
0x18003bd22  push    rbp
0x18003bd23  push    rsi
0x18003bd24  push    rdi
0x18003bd25  push    r14
0x18003bd27  push    r15
0x18003bd29  mov     rbp, rsp
0x18003bd2c  sub     rsp, 80h
0x18003bd33  mov     rdi, rdx
0x18003bd36  mov     r15, rcx
0x18003bd39  mov     [rbp+arg_10], 0
0x18003bd41  lea     rcx, [rbp+arg_10]
0x18003bd45  call    ?CreateInstance@?$CComObject@VCFsiDirectoryItem@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFsiDirectoryItem>::CreateInstance(ATL::CComObject<CFsiDirectoryItem> * *)
0x18003bd4a  mov     ebx, eax
0x18003bd4c  test    eax, eax
0x18003bd4e  jns     loc_18003BDE1
0x18003bd54  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003bd59  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003bd5e  mov     [rbp+arg_10], rax
0x18003bd62  test    rax, rax
0x18003bd65  jz      short loc_18003BD72
0x18003bd67  mov     edx, ebx; int
0x18003bd69  mov     rcx, rax; this
0x18003bd6c  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18003bd71  nop
0x18003bd72  mov     rdx, rax
0x18003bd75  lea     rcx, [rbp+arg_10]
0x18003bd79  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003bd7e  nop
0x18003bd7f  mov     rbx, [rbp+arg_10]
0x18003bd83  test    rbx, rbx
0x18003bd86  jz      short loc_18003BDC0
0x18003bd88  cmp     qword ptr [rbx], 0
0x18003bd8c  jz      short loc_18003BDC0
0x18003bd8e  mov     r8d, 0D0h; int
0x18003bd94  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x18003bd9b  mov     rcx, [rbx]; this
0x18003bd9e  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003bda3  mov     [rbp+pExceptionObject], rbx
0x18003bda7  test    rbx, rbx
0x18003bdaa  jz      short loc_18003BDAF
0x18003bdac  inc     dword ptr [rbx+8]
0x18003bdaf  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003bdb6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003bdba  call    _CxxThrowException_0
0x18003bdc0  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003bdc7  lea     rcx, [rbp+var_58]; this
0x18003bdcb  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003bdd0  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003bdd7  lea     rcx, [rbp+var_58]; pExceptionObject
0x18003bddb  call    _CxxThrowException_0
0x18003bde1  mov     r14, [rbp+arg_10]
0x18003bde5  lea     rsi, [r14+48h]
0x18003bde9  mov     rax, [rsi]
0x18003bdec  mov     rcx, rsi
0x18003bdef  mov     rax, [rax+8]
0x18003bdf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdf8  mov     rax, [rdi]
0x18003bdfb  mov     [rbp+arg_10], rax
0x18003bdff  test    rax, rax
0x18003be02  jz      short loc_18003BE07
0x18003be04  inc     dword ptr [rax+8]
0x18003be07  lea     rdx, [rbp+arg_10]
0x18003be0b  mov     rcx, r14
0x18003be0e  call    ?Init@ImapiComReturnObject@@QEAAXV?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; ImapiComReturnObject::Init(SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x18003be13  mov     rax, [r14]
0x18003be16  mov     rbx, [rax+10h]
0x18003be1a  mov     [rbp+arg_10], r15
0x18003be1e  lea     rcx, [rbp+arg_10]
0x18003be22  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_AddRef(void)
0x18003be27  lea     rdx, [rbp+arg_10]
0x18003be2b  mov     rcx, r14
0x18003be2e  mov     rax, rbx
0x18003be31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be36  mov     [rbp+arg_18], 0
0x18003be3e  mov     rax, [rsi]
0x18003be41  lea     r8, [rbp+arg_18]
0x18003be45  lea     rdx, _GUID_2c941fd9_975b_59be_a960_9a2a262853a5
0x18003be4c  mov     rcx, rsi
0x18003be4f  mov     rax, [rax]
0x18003be52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be57  mov     ebx, eax
0x18003be59  mov     rdx, [rsi]
0x18003be5c  mov     rcx, rsi
0x18003be5f  mov     rax, [rdx+10h]
0x18003be63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be68  test    ebx, ebx
0x18003be6a  jns     loc_18003BEFD
0x18003be70  mov     ecx, 58h ; 'X'; unsigned __int64
0x18003be75  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003be7a  mov     [rbp+arg_10], rax
0x18003be7e  test    rax, rax
0x18003be81  jz      short loc_18003BE8E
0x18003be83  mov     edx, ebx; int
0x18003be85  mov     rcx, rax; this
0x18003be88  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18003be8d  nop
0x18003be8e  mov     rdx, rax
0x18003be91  lea     rcx, [rbp+arg_10]
0x18003be95  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18003be9a  nop
0x18003be9b  mov     rbx, [rbp+arg_10]
0x18003be9f  test    rbx, rbx
0x18003bea2  jz      short loc_18003BEDC
0x18003bea4  cmp     qword ptr [rbx], 0
0x18003bea8  jz      short loc_18003BEDC
0x18003beaa  mov     r8d, 0E0h; int
0x18003beb0  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x18003beb7  mov     rcx, [rbx]; this
0x18003beba  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18003bebf  mov     [rbp+pExceptionObject], rbx
0x18003bec3  test    rbx, rbx
0x18003bec6  jz      short loc_18003BECB
0x18003bec8  inc     dword ptr [rbx+8]
0x18003becb  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18003bed2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003bed6  call    _CxxThrowException_0
0x18003bedc  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18003bee3  lea     rcx, [rbp+var_58]; this
0x18003bee7  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18003beec  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18003bef3  lea     rcx, [rbp+var_58]; pExceptionObject
0x18003bef7  call    _CxxThrowException_0
0x18003befd  mov     rbx, [rbp+arg_18]
0x18003bf01  mov     rcx, rdi; void *
0x18003bf04  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18003bf09  mov     rax, rbx
0x18003bf0c  mov     rbx, [rsp+80h+arg_0]
0x18003bf14  add     rsp, 80h
0x18003bf1b  pop     r15
0x18003bf1d  pop     r14
0x18003bf1f  pop     rdi
0x18003bf20  pop     rsi
0x18003bf21  pop     rbp
0x18003bf22  retn
```
