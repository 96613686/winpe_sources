# CreateReturnObject<IFsiDirectoryItem,CFsiDirectoryItem>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)

- ea: `0x180011c68`
- end: `0x180011e73`
- name: `??$CreateReturnObject@UIFsiDirectoryItem@@VCFsiDirectoryItem@@@@YAPEAUIFsiDirectoryItem@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z`
- size: `523`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011070`
- `0x1800115d0`

## callees

- `0x180003a20`
- `0x180005040`
- `0x180007198`
- `0x18000960c`
- `0x18000c8d0`
- `0x18000f90c`
- `0x180011c68`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18003b434`
- `0x18003d844`
- `0x180088010`

## string_xrefs

- `0x180011ce4`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`
- `0x180011e00`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`

## pseudocode

```c
__int64 __fastcall CreateReturnObject<IFsiDirectoryItem,CFsiDirectoryItem>(
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
          &GUID_2c941fdc_975b_59be_a960_9a2a262853a5,
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
0x180011c68  mov     [rsp-28h+arg_0], rbx
0x180011c6d  mov     [rsp-28h+arg_8], rdx
0x180011c72  push    rbp
0x180011c73  push    rsi
0x180011c74  push    rdi
0x180011c75  push    r14
0x180011c77  push    r15
0x180011c79  mov     rbp, rsp
0x180011c7c  sub     rsp, 80h
0x180011c83  mov     rdi, rdx
0x180011c86  mov     r15, rcx
0x180011c89  mov     [rbp+arg_10], 0
0x180011c91  lea     rcx, [rbp+arg_10]
0x180011c95  call    ?CreateInstance@?$CComObject@VCFsiDirectoryItem@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFsiDirectoryItem>::CreateInstance(ATL::CComObject<CFsiDirectoryItem> * *)
0x180011c9a  mov     ebx, eax
0x180011c9c  test    eax, eax
0x180011c9e  jns     loc_180011D31
0x180011ca4  mov     ecx, 58h ; 'X'; unsigned __int64
0x180011ca9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011cae  mov     [rbp+arg_10], rax
0x180011cb2  test    rax, rax
0x180011cb5  jz      short loc_180011CC2
0x180011cb7  mov     edx, ebx; int
0x180011cb9  mov     rcx, rax; this
0x180011cbc  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x180011cc1  nop
0x180011cc2  mov     rdx, rax
0x180011cc5  lea     rcx, [rbp+arg_10]
0x180011cc9  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180011cce  nop
0x180011ccf  mov     rbx, [rbp+arg_10]
0x180011cd3  test    rbx, rbx
0x180011cd6  jz      short loc_180011D10
0x180011cd8  cmp     qword ptr [rbx], 0
0x180011cdc  jz      short loc_180011D10
0x180011cde  mov     r8d, 0D0h; int
0x180011ce4  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x180011ceb  mov     rcx, [rbx]; this
0x180011cee  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180011cf3  mov     [rbp+pExceptionObject], rbx
0x180011cf7  test    rbx, rbx
0x180011cfa  jz      short loc_180011CFF
0x180011cfc  inc     dword ptr [rbx+8]
0x180011cff  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180011d06  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011d0a  call    _CxxThrowException_0
0x180011d10  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180011d17  lea     rcx, [rbp+var_58]; this
0x180011d1b  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180011d20  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180011d27  lea     rcx, [rbp+var_58]; pExceptionObject
0x180011d2b  call    _CxxThrowException_0
0x180011d31  mov     r14, [rbp+arg_10]
0x180011d35  lea     rsi, [r14+48h]
0x180011d39  mov     rax, [rsi]
0x180011d3c  mov     rcx, rsi
0x180011d3f  mov     rax, [rax+8]
0x180011d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d48  mov     rax, [rdi]
0x180011d4b  mov     [rbp+arg_10], rax
0x180011d4f  test    rax, rax
0x180011d52  jz      short loc_180011D57
0x180011d54  inc     dword ptr [rax+8]
0x180011d57  lea     rdx, [rbp+arg_10]
0x180011d5b  mov     rcx, r14
0x180011d5e  call    ?Init@ImapiComReturnObject@@QEAAXV?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; ImapiComReturnObject::Init(SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x180011d63  mov     rax, [r14]
0x180011d66  mov     rbx, [rax+10h]
0x180011d6a  mov     [rbp+arg_10], r15
0x180011d6e  lea     rcx, [rbp+arg_10]
0x180011d72  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_AddRef(void)
0x180011d77  lea     rdx, [rbp+arg_10]
0x180011d7b  mov     rcx, r14
0x180011d7e  mov     rax, rbx
0x180011d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d86  mov     [rbp+arg_18], 0
0x180011d8e  mov     rax, [rsi]
0x180011d91  lea     r8, [rbp+arg_18]
0x180011d95  lea     rdx, _GUID_2c941fdc_975b_59be_a960_9a2a262853a5
0x180011d9c  mov     rcx, rsi
0x180011d9f  mov     rax, [rax]
0x180011da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011da7  mov     ebx, eax
0x180011da9  mov     rdx, [rsi]
0x180011dac  mov     rcx, rsi
0x180011daf  mov     rax, [rdx+10h]
0x180011db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011db8  test    ebx, ebx
0x180011dba  jns     loc_180011E4D
0x180011dc0  mov     ecx, 58h ; 'X'; unsigned __int64
0x180011dc5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011dca  mov     [rbp+arg_10], rax
0x180011dce  test    rax, rax
0x180011dd1  jz      short loc_180011DDE
0x180011dd3  mov     edx, ebx; int
0x180011dd5  mov     rcx, rax; this
0x180011dd8  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x180011ddd  nop
0x180011dde  mov     rdx, rax
0x180011de1  lea     rcx, [rbp+arg_10]
0x180011de5  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180011dea  nop
0x180011deb  mov     rbx, [rbp+arg_10]
0x180011def  test    rbx, rbx
0x180011df2  jz      short loc_180011E2C
0x180011df4  cmp     qword ptr [rbx], 0
0x180011df8  jz      short loc_180011E2C
0x180011dfa  mov     r8d, 0E0h; int
0x180011e00  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x180011e07  mov     rcx, [rbx]; this
0x180011e0a  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180011e0f  mov     [rbp+pExceptionObject], rbx
0x180011e13  test    rbx, rbx
0x180011e16  jz      short loc_180011E1B
0x180011e18  inc     dword ptr [rbx+8]
0x180011e1b  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180011e22  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180011e26  call    _CxxThrowException_0
0x180011e2c  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180011e33  lea     rcx, [rbp+var_58]; this
0x180011e37  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180011e3c  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180011e43  lea     rcx, [rbp+var_58]; pExceptionObject
0x180011e47  call    _CxxThrowException_0
0x180011e4d  mov     rbx, [rbp+arg_18]
0x180011e51  mov     rcx, rdi; void *
0x180011e54  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x180011e59  mov     rax, rbx
0x180011e5c  mov     rbx, [rsp+80h+arg_0]
0x180011e64  add     rsp, 80h
0x180011e6b  pop     r15
0x180011e6d  pop     r14
0x180011e6f  pop     rdi
0x180011e70  pop     rsi
0x180011e71  pop     rbp
0x180011e72  retn
```
