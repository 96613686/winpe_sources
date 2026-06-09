# CreateReturnObject<IDispatch,CBlockRange>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)

- ea: `0x18001e268`
- end: `0x18001e473`
- name: `??$CreateReturnObject@UIDispatch@@VCBlockRange@@@@YAPEAUIDispatch@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001e0a0`

## callees

- `0x180003a20`
- `0x180005040`
- `0x180007198`
- `0x18000960c`
- `0x18000c8d0`
- `0x18000f90c`
- `0x18001e268`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18003b434`
- `0x18005c380`
- `0x180088010`

## string_xrefs

- `0x18001e2e4`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`
- `0x18001e400`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`

## pseudocode

```c
__int64 __fastcall CreateReturnObject<IDispatch,CBlockRange>(CIMAPISystemException *a1, CIMAPISystemException **a2)
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
  v4 = ATL::CComObject<CBlockRange>::CreateInstance(&v18);
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
          &GUID_00020400_0000_0000_c000_000000000046,
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
0x18001e268  mov     [rsp-28h+arg_0], rbx
0x18001e26d  mov     [rsp-28h+arg_8], rdx
0x18001e272  push    rbp
0x18001e273  push    rsi
0x18001e274  push    rdi
0x18001e275  push    r14
0x18001e277  push    r15
0x18001e279  mov     rbp, rsp
0x18001e27c  sub     rsp, 80h
0x18001e283  mov     rdi, rdx
0x18001e286  mov     r15, rcx
0x18001e289  mov     [rbp+arg_10], 0
0x18001e291  lea     rcx, [rbp+arg_10]
0x18001e295  call    ?CreateInstance@?$CComObject@VCBlockRange@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CBlockRange>::CreateInstance(ATL::CComObject<CBlockRange> * *)
0x18001e29a  mov     ebx, eax
0x18001e29c  test    eax, eax
0x18001e29e  jns     loc_18001E331
0x18001e2a4  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001e2a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e2ae  mov     [rbp+arg_10], rax
0x18001e2b2  test    rax, rax
0x18001e2b5  jz      short loc_18001E2C2
0x18001e2b7  mov     edx, ebx; int
0x18001e2b9  mov     rcx, rax; this
0x18001e2bc  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18001e2c1  nop
0x18001e2c2  mov     rdx, rax
0x18001e2c5  lea     rcx, [rbp+arg_10]
0x18001e2c9  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001e2ce  nop
0x18001e2cf  mov     rbx, [rbp+arg_10]
0x18001e2d3  test    rbx, rbx
0x18001e2d6  jz      short loc_18001E310
0x18001e2d8  cmp     qword ptr [rbx], 0
0x18001e2dc  jz      short loc_18001E310
0x18001e2de  mov     r8d, 0D0h; int
0x18001e2e4  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x18001e2eb  mov     rcx, [rbx]; this
0x18001e2ee  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18001e2f3  mov     [rbp+pExceptionObject], rbx
0x18001e2f7  test    rbx, rbx
0x18001e2fa  jz      short loc_18001E2FF
0x18001e2fc  inc     dword ptr [rbx+8]
0x18001e2ff  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18001e306  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e30a  call    _CxxThrowException_0
0x18001e310  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18001e317  lea     rcx, [rbp+var_58]; this
0x18001e31b  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18001e320  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18001e327  lea     rcx, [rbp+var_58]; pExceptionObject
0x18001e32b  call    _CxxThrowException_0
0x18001e331  mov     r14, [rbp+arg_10]
0x18001e335  lea     rsi, [r14+48h]
0x18001e339  mov     rax, [rsi]
0x18001e33c  mov     rcx, rsi
0x18001e33f  mov     rax, [rax+8]
0x18001e343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e348  mov     rax, [rdi]
0x18001e34b  mov     [rbp+arg_10], rax
0x18001e34f  test    rax, rax
0x18001e352  jz      short loc_18001E357
0x18001e354  inc     dword ptr [rax+8]
0x18001e357  lea     rdx, [rbp+arg_10]
0x18001e35b  mov     rcx, r14
0x18001e35e  call    ?Init@ImapiComReturnObject@@QEAAXV?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; ImapiComReturnObject::Init(SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x18001e363  mov     rax, [r14]
0x18001e366  mov     rbx, [rax+10h]
0x18001e36a  mov     [rbp+arg_10], r15
0x18001e36e  lea     rcx, [rbp+arg_10]
0x18001e372  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_AddRef(void)
0x18001e377  lea     rdx, [rbp+arg_10]
0x18001e37b  mov     rcx, r14
0x18001e37e  mov     rax, rbx
0x18001e381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e386  mov     [rbp+arg_18], 0
0x18001e38e  mov     rax, [rsi]
0x18001e391  lea     r8, [rbp+arg_18]
0x18001e395  lea     rdx, _GUID_00020400_0000_0000_c000_000000000046
0x18001e39c  mov     rcx, rsi
0x18001e39f  mov     rax, [rax]
0x18001e3a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3a7  mov     ebx, eax
0x18001e3a9  mov     rdx, [rsi]
0x18001e3ac  mov     rcx, rsi
0x18001e3af  mov     rax, [rdx+10h]
0x18001e3b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3b8  test    ebx, ebx
0x18001e3ba  jns     loc_18001E44D
0x18001e3c0  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001e3c5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e3ca  mov     [rbp+arg_10], rax
0x18001e3ce  test    rax, rax
0x18001e3d1  jz      short loc_18001E3DE
0x18001e3d3  mov     edx, ebx; int
0x18001e3d5  mov     rcx, rax; this
0x18001e3d8  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18001e3dd  nop
0x18001e3de  mov     rdx, rax
0x18001e3e1  lea     rcx, [rbp+arg_10]
0x18001e3e5  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001e3ea  nop
0x18001e3eb  mov     rbx, [rbp+arg_10]
0x18001e3ef  test    rbx, rbx
0x18001e3f2  jz      short loc_18001E42C
0x18001e3f4  cmp     qword ptr [rbx], 0
0x18001e3f8  jz      short loc_18001E42C
0x18001e3fa  mov     r8d, 0E0h; int
0x18001e400  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x18001e407  mov     rcx, [rbx]; this
0x18001e40a  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18001e40f  mov     [rbp+pExceptionObject], rbx
0x18001e413  test    rbx, rbx
0x18001e416  jz      short loc_18001E41B
0x18001e418  inc     dword ptr [rbx+8]
0x18001e41b  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18001e422  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001e426  call    _CxxThrowException_0
0x18001e42c  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18001e433  lea     rcx, [rbp+var_58]; this
0x18001e437  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18001e43c  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18001e443  lea     rcx, [rbp+var_58]; pExceptionObject
0x18001e447  call    _CxxThrowException_0
0x18001e44d  mov     rbx, [rbp+arg_18]
0x18001e451  mov     rcx, rdi; void *
0x18001e454  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18001e459  mov     rax, rbx
0x18001e45c  mov     rbx, [rsp+80h+arg_0]
0x18001e464  add     rsp, 80h
0x18001e46b  pop     r15
0x18001e46d  pop     r14
0x18001e46f  pop     rdi
0x18001e470  pop     rsi
0x18001e471  pop     rbp
0x18001e472  retn
```
