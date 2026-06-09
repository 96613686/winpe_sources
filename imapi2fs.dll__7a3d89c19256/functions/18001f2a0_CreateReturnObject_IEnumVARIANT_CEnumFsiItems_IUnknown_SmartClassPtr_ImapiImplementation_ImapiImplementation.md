# CreateReturnObject<IEnumVARIANT,CEnumFsiItems>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)

- ea: `0x18001f2a0`
- end: `0x18001f4ab`
- name: `??$CreateReturnObject@UIEnumVARIANT@@VCEnumFsiItems@@@@YAPEAUIEnumVARIANT@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z`
- size: `523`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18001edd0`
- `0x18001ef40`
- `0x18001f0b0`

## callees

- `0x180003a20`
- `0x180005040`
- `0x180007198`
- `0x18000960c`
- `0x18000c8d0`
- `0x18000f90c`
- `0x18001f2a0`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18003b434`
- `0x18003d79c`
- `0x180088010`

## string_xrefs

- `0x18001f31c`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`
- `0x18001f438`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`

## pseudocode

```c
__int64 __fastcall CreateReturnObject<IEnumVARIANT,CEnumFsiItems>(
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
0x18001f2a0  mov     [rsp-28h+arg_0], rbx
0x18001f2a5  mov     [rsp-28h+arg_8], rdx
0x18001f2aa  push    rbp
0x18001f2ab  push    rsi
0x18001f2ac  push    rdi
0x18001f2ad  push    r14
0x18001f2af  push    r15
0x18001f2b1  mov     rbp, rsp
0x18001f2b4  sub     rsp, 80h
0x18001f2bb  mov     rdi, rdx
0x18001f2be  mov     r15, rcx
0x18001f2c1  mov     [rbp+arg_10], 0
0x18001f2c9  lea     rcx, [rbp+arg_10]
0x18001f2cd  call    ?CreateInstance@?$CComObject@VCEnumFsiItems@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CEnumFsiItems>::CreateInstance(ATL::CComObject<CEnumFsiItems> * *)
0x18001f2d2  mov     ebx, eax
0x18001f2d4  test    eax, eax
0x18001f2d6  jns     loc_18001F369
0x18001f2dc  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001f2e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f2e6  mov     [rbp+arg_10], rax
0x18001f2ea  test    rax, rax
0x18001f2ed  jz      short loc_18001F2FA
0x18001f2ef  mov     edx, ebx; int
0x18001f2f1  mov     rcx, rax; this
0x18001f2f4  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18001f2f9  nop
0x18001f2fa  mov     rdx, rax
0x18001f2fd  lea     rcx, [rbp+arg_10]
0x18001f301  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001f306  nop
0x18001f307  mov     rbx, [rbp+arg_10]
0x18001f30b  test    rbx, rbx
0x18001f30e  jz      short loc_18001F348
0x18001f310  cmp     qword ptr [rbx], 0
0x18001f314  jz      short loc_18001F348
0x18001f316  mov     r8d, 0D0h; int
0x18001f31c  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x18001f323  mov     rcx, [rbx]; this
0x18001f326  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18001f32b  mov     [rbp+pExceptionObject], rbx
0x18001f32f  test    rbx, rbx
0x18001f332  jz      short loc_18001F337
0x18001f334  inc     dword ptr [rbx+8]
0x18001f337  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18001f33e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001f342  call    _CxxThrowException_0
0x18001f348  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18001f34f  lea     rcx, [rbp+var_58]; this
0x18001f353  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18001f358  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18001f35f  lea     rcx, [rbp+var_58]; pExceptionObject
0x18001f363  call    _CxxThrowException_0
0x18001f369  mov     r14, [rbp+arg_10]
0x18001f36d  lea     rsi, [r14+48h]
0x18001f371  mov     rax, [rsi]
0x18001f374  mov     rcx, rsi
0x18001f377  mov     rax, [rax+8]
0x18001f37b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f380  mov     rax, [rdi]
0x18001f383  mov     [rbp+arg_10], rax
0x18001f387  test    rax, rax
0x18001f38a  jz      short loc_18001F38F
0x18001f38c  inc     dword ptr [rax+8]
0x18001f38f  lea     rdx, [rbp+arg_10]
0x18001f393  mov     rcx, r14
0x18001f396  call    ?Init@ImapiComReturnObject@@QEAAXV?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; ImapiComReturnObject::Init(SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x18001f39b  mov     rax, [r14]
0x18001f39e  mov     rbx, [rax+10h]
0x18001f3a2  mov     [rbp+arg_10], r15
0x18001f3a6  lea     rcx, [rbp+arg_10]
0x18001f3aa  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_AddRef(void)
0x18001f3af  lea     rdx, [rbp+arg_10]
0x18001f3b3  mov     rcx, r14
0x18001f3b6  mov     rax, rbx
0x18001f3b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3be  mov     [rbp+arg_18], 0
0x18001f3c6  mov     rax, [rsi]
0x18001f3c9  lea     r8, [rbp+arg_18]
0x18001f3cd  lea     rdx, _GUID_00020404_0000_0000_c000_000000000046
0x18001f3d4  mov     rcx, rsi
0x18001f3d7  mov     rax, [rax]
0x18001f3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3df  mov     ebx, eax
0x18001f3e1  mov     rdx, [rsi]
0x18001f3e4  mov     rcx, rsi
0x18001f3e7  mov     rax, [rdx+10h]
0x18001f3eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3f0  test    ebx, ebx
0x18001f3f2  jns     loc_18001F485
0x18001f3f8  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001f3fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f402  mov     [rbp+arg_10], rax
0x18001f406  test    rax, rax
0x18001f409  jz      short loc_18001F416
0x18001f40b  mov     edx, ebx; int
0x18001f40d  mov     rcx, rax; this
0x18001f410  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18001f415  nop
0x18001f416  mov     rdx, rax
0x18001f419  lea     rcx, [rbp+arg_10]
0x18001f41d  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001f422  nop
0x18001f423  mov     rbx, [rbp+arg_10]
0x18001f427  test    rbx, rbx
0x18001f42a  jz      short loc_18001F464
0x18001f42c  cmp     qword ptr [rbx], 0
0x18001f430  jz      short loc_18001F464
0x18001f432  mov     r8d, 0E0h; int
0x18001f438  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x18001f43f  mov     rcx, [rbx]; this
0x18001f442  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18001f447  mov     [rbp+pExceptionObject], rbx
0x18001f44b  test    rbx, rbx
0x18001f44e  jz      short loc_18001F453
0x18001f450  inc     dword ptr [rbx+8]
0x18001f453  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18001f45a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001f45e  call    _CxxThrowException_0
0x18001f464  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18001f46b  lea     rcx, [rbp+var_58]; this
0x18001f46f  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18001f474  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18001f47b  lea     rcx, [rbp+var_58]; pExceptionObject
0x18001f47f  call    _CxxThrowException_0
0x18001f485  mov     rbx, [rbp+arg_18]
0x18001f489  mov     rcx, rdi; void *
0x18001f48c  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18001f491  mov     rax, rbx
0x18001f494  mov     rbx, [rsp+80h+arg_0]
0x18001f49c  add     rsp, 80h
0x18001f4a3  pop     r15
0x18001f4a5  pop     r14
0x18001f4a7  pop     rdi
0x18001f4a8  pop     rsi
0x18001f4a9  pop     rbp
0x18001f4aa  retn
```
