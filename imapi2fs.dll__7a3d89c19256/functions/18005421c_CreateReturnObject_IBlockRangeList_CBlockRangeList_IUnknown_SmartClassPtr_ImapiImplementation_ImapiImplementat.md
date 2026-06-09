# CreateReturnObject<IBlockRangeList,CBlockRangeList>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)

- ea: `0x18005421c`
- end: `0x180054427`
- name: `??$CreateReturnObject@UIBlockRangeList@@VCBlockRangeList@@@@YAPEAUIBlockRangeList@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180056410`

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
- `0x18005421c`
- `0x180054834`
- `0x180088010`

## string_xrefs

- `0x180054298`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`
- `0x1800543b4`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`

## pseudocode

```c
__int64 __fastcall CreateReturnObject<IBlockRangeList,CBlockRangeList>(
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
  v4 = ATL::CComObject<CBlockRangeList>::CreateInstance(&v18);
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
          &GUID_b507ca26_2204_11dd_966a_001aa01bbc58,
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
0x18005421c  mov     [rsp-28h+arg_0], rbx
0x180054221  mov     [rsp-28h+arg_8], rdx
0x180054226  push    rbp
0x180054227  push    rsi
0x180054228  push    rdi
0x180054229  push    r14
0x18005422b  push    r15
0x18005422d  mov     rbp, rsp
0x180054230  sub     rsp, 80h
0x180054237  mov     rdi, rdx
0x18005423a  mov     r15, rcx
0x18005423d  mov     [rbp+arg_10], 0
0x180054245  lea     rcx, [rbp+arg_10]
0x180054249  call    ?CreateInstance@?$CComObject@VCBlockRangeList@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CBlockRangeList>::CreateInstance(ATL::CComObject<CBlockRangeList> * *)
0x18005424e  mov     ebx, eax
0x180054250  test    eax, eax
0x180054252  jns     loc_1800542E5
0x180054258  mov     ecx, 58h ; 'X'; unsigned __int64
0x18005425d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180054262  mov     [rbp+arg_10], rax
0x180054266  test    rax, rax
0x180054269  jz      short loc_180054276
0x18005426b  mov     edx, ebx; int
0x18005426d  mov     rcx, rax; this
0x180054270  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x180054275  nop
0x180054276  mov     rdx, rax
0x180054279  lea     rcx, [rbp+arg_10]
0x18005427d  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180054282  nop
0x180054283  mov     rbx, [rbp+arg_10]
0x180054287  test    rbx, rbx
0x18005428a  jz      short loc_1800542C4
0x18005428c  cmp     qword ptr [rbx], 0
0x180054290  jz      short loc_1800542C4
0x180054292  mov     r8d, 0D0h; int
0x180054298  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x18005429f  mov     rcx, [rbx]; this
0x1800542a2  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x1800542a7  mov     [rbp+pExceptionObject], rbx
0x1800542ab  test    rbx, rbx
0x1800542ae  jz      short loc_1800542B3
0x1800542b0  inc     dword ptr [rbx+8]
0x1800542b3  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800542ba  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800542be  call    _CxxThrowException_0
0x1800542c4  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x1800542cb  lea     rcx, [rbp+var_58]; this
0x1800542cf  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x1800542d4  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x1800542db  lea     rcx, [rbp+var_58]; pExceptionObject
0x1800542df  call    _CxxThrowException_0
0x1800542e5  mov     r14, [rbp+arg_10]
0x1800542e9  lea     rsi, [r14+48h]
0x1800542ed  mov     rax, [rsi]
0x1800542f0  mov     rcx, rsi
0x1800542f3  mov     rax, [rax+8]
0x1800542f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800542fc  mov     rax, [rdi]
0x1800542ff  mov     [rbp+arg_10], rax
0x180054303  test    rax, rax
0x180054306  jz      short loc_18005430B
0x180054308  inc     dword ptr [rax+8]
0x18005430b  lea     rdx, [rbp+arg_10]
0x18005430f  mov     rcx, r14
0x180054312  call    ?Init@ImapiComReturnObject@@QEAAXV?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; ImapiComReturnObject::Init(SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x180054317  mov     rax, [r14]
0x18005431a  mov     rbx, [rax+10h]
0x18005431e  mov     [rbp+arg_10], r15
0x180054322  lea     rcx, [rbp+arg_10]
0x180054326  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_AddRef(void)
0x18005432b  lea     rdx, [rbp+arg_10]
0x18005432f  mov     rcx, r14
0x180054332  mov     rax, rbx
0x180054335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005433a  mov     [rbp+arg_18], 0
0x180054342  mov     rax, [rsi]
0x180054345  lea     r8, [rbp+arg_18]
0x180054349  lea     rdx, _GUID_b507ca26_2204_11dd_966a_001aa01bbc58
0x180054350  mov     rcx, rsi
0x180054353  mov     rax, [rax]
0x180054356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005435b  mov     ebx, eax
0x18005435d  mov     rdx, [rsi]
0x180054360  mov     rcx, rsi
0x180054363  mov     rax, [rdx+10h]
0x180054367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005436c  test    ebx, ebx
0x18005436e  jns     loc_180054401
0x180054374  mov     ecx, 58h ; 'X'; unsigned __int64
0x180054379  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005437e  mov     [rbp+arg_10], rax
0x180054382  test    rax, rax
0x180054385  jz      short loc_180054392
0x180054387  mov     edx, ebx; int
0x180054389  mov     rcx, rax; this
0x18005438c  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x180054391  nop
0x180054392  mov     rdx, rax
0x180054395  lea     rcx, [rbp+arg_10]
0x180054399  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18005439e  nop
0x18005439f  mov     rbx, [rbp+arg_10]
0x1800543a3  test    rbx, rbx
0x1800543a6  jz      short loc_1800543E0
0x1800543a8  cmp     qword ptr [rbx], 0
0x1800543ac  jz      short loc_1800543E0
0x1800543ae  mov     r8d, 0E0h; int
0x1800543b4  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x1800543bb  mov     rcx, [rbx]; this
0x1800543be  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x1800543c3  mov     [rbp+pExceptionObject], rbx
0x1800543c7  test    rbx, rbx
0x1800543ca  jz      short loc_1800543CF
0x1800543cc  inc     dword ptr [rbx+8]
0x1800543cf  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x1800543d6  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800543da  call    _CxxThrowException_0
0x1800543e0  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x1800543e7  lea     rcx, [rbp+var_58]; this
0x1800543eb  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x1800543f0  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x1800543f7  lea     rcx, [rbp+var_58]; pExceptionObject
0x1800543fb  call    _CxxThrowException_0
0x180054401  mov     rbx, [rbp+arg_18]
0x180054405  mov     rcx, rdi; void *
0x180054408  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18005440d  mov     rax, rbx
0x180054410  mov     rbx, [rsp+80h+arg_0]
0x180054418  add     rsp, 80h
0x18005441f  pop     r15
0x180054421  pop     r14
0x180054423  pop     rdi
0x180054424  pop     rsi
0x180054425  pop     rbp
0x180054426  retn
```
