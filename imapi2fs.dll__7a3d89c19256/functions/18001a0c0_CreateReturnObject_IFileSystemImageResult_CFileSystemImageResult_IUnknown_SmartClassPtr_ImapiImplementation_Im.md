# CreateReturnObject<IFileSystemImageResult,CFileSystemImageResult>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)

- ea: `0x18001a0c0`
- end: `0x18001a2cb`
- name: `??$CreateReturnObject@UIFileSystemImageResult@@VCFileSystemImageResult@@@@YAPEAUIFileSystemImageResult@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180019dd0`

## callees

- `0x180003a20`
- `0x180005040`
- `0x180007198`
- `0x18000960c`
- `0x18000c8d0`
- `0x18000f90c`
- `0x18001a0c0`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18003b434`
- `0x180056e20`
- `0x180088010`

## string_xrefs

- `0x18001a13c`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`
- `0x18001a258`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`

## pseudocode

```c
__int64 __fastcall CreateReturnObject<IFileSystemImageResult,CFileSystemImageResult>(
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
  v4 = ATL::CComObject<CFileSystemImageResult>::CreateInstance(&v18);
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
          &GUID_2c941fd8_975b_59be_a960_9a2a262853a5,
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
0x18001a0c0  mov     [rsp-28h+arg_0], rbx
0x18001a0c5  mov     [rsp-28h+arg_8], rdx
0x18001a0ca  push    rbp
0x18001a0cb  push    rsi
0x18001a0cc  push    rdi
0x18001a0cd  push    r14
0x18001a0cf  push    r15
0x18001a0d1  mov     rbp, rsp
0x18001a0d4  sub     rsp, 80h
0x18001a0db  mov     rdi, rdx
0x18001a0de  mov     r15, rcx
0x18001a0e1  mov     [rbp+arg_10], 0
0x18001a0e9  lea     rcx, [rbp+arg_10]
0x18001a0ed  call    ?CreateInstance@?$CComObject@VCFileSystemImageResult@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFileSystemImageResult>::CreateInstance(ATL::CComObject<CFileSystemImageResult> * *)
0x18001a0f2  mov     ebx, eax
0x18001a0f4  test    eax, eax
0x18001a0f6  jns     loc_18001A189
0x18001a0fc  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001a101  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a106  mov     [rbp+arg_10], rax
0x18001a10a  test    rax, rax
0x18001a10d  jz      short loc_18001A11A
0x18001a10f  mov     edx, ebx; int
0x18001a111  mov     rcx, rax; this
0x18001a114  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18001a119  nop
0x18001a11a  mov     rdx, rax
0x18001a11d  lea     rcx, [rbp+arg_10]
0x18001a121  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001a126  nop
0x18001a127  mov     rbx, [rbp+arg_10]
0x18001a12b  test    rbx, rbx
0x18001a12e  jz      short loc_18001A168
0x18001a130  cmp     qword ptr [rbx], 0
0x18001a134  jz      short loc_18001A168
0x18001a136  mov     r8d, 0D0h; int
0x18001a13c  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x18001a143  mov     rcx, [rbx]; this
0x18001a146  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18001a14b  mov     [rbp+pExceptionObject], rbx
0x18001a14f  test    rbx, rbx
0x18001a152  jz      short loc_18001A157
0x18001a154  inc     dword ptr [rbx+8]
0x18001a157  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18001a15e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a162  call    _CxxThrowException_0
0x18001a168  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18001a16f  lea     rcx, [rbp+var_58]; this
0x18001a173  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18001a178  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18001a17f  lea     rcx, [rbp+var_58]; pExceptionObject
0x18001a183  call    _CxxThrowException_0
0x18001a189  mov     r14, [rbp+arg_10]
0x18001a18d  lea     rsi, [r14+48h]
0x18001a191  mov     rax, [rsi]
0x18001a194  mov     rcx, rsi
0x18001a197  mov     rax, [rax+8]
0x18001a19b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1a0  mov     rax, [rdi]
0x18001a1a3  mov     [rbp+arg_10], rax
0x18001a1a7  test    rax, rax
0x18001a1aa  jz      short loc_18001A1AF
0x18001a1ac  inc     dword ptr [rax+8]
0x18001a1af  lea     rdx, [rbp+arg_10]
0x18001a1b3  mov     rcx, r14
0x18001a1b6  call    ?Init@ImapiComReturnObject@@QEAAXV?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; ImapiComReturnObject::Init(SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x18001a1bb  mov     rax, [r14]
0x18001a1be  mov     rbx, [rax+10h]
0x18001a1c2  mov     [rbp+arg_10], r15
0x18001a1c6  lea     rcx, [rbp+arg_10]
0x18001a1ca  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_AddRef(void)
0x18001a1cf  lea     rdx, [rbp+arg_10]
0x18001a1d3  mov     rcx, r14
0x18001a1d6  mov     rax, rbx
0x18001a1d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1de  mov     [rbp+arg_18], 0
0x18001a1e6  mov     rax, [rsi]
0x18001a1e9  lea     r8, [rbp+arg_18]
0x18001a1ed  lea     rdx, _GUID_2c941fd8_975b_59be_a960_9a2a262853a5
0x18001a1f4  mov     rcx, rsi
0x18001a1f7  mov     rax, [rax]
0x18001a1fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1ff  mov     ebx, eax
0x18001a201  mov     rdx, [rsi]
0x18001a204  mov     rcx, rsi
0x18001a207  mov     rax, [rdx+10h]
0x18001a20b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a210  test    ebx, ebx
0x18001a212  jns     loc_18001A2A5
0x18001a218  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001a21d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a222  mov     [rbp+arg_10], rax
0x18001a226  test    rax, rax
0x18001a229  jz      short loc_18001A236
0x18001a22b  mov     edx, ebx; int
0x18001a22d  mov     rcx, rax; this
0x18001a230  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18001a235  nop
0x18001a236  mov     rdx, rax
0x18001a239  lea     rcx, [rbp+arg_10]
0x18001a23d  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001a242  nop
0x18001a243  mov     rbx, [rbp+arg_10]
0x18001a247  test    rbx, rbx
0x18001a24a  jz      short loc_18001A284
0x18001a24c  cmp     qword ptr [rbx], 0
0x18001a250  jz      short loc_18001A284
0x18001a252  mov     r8d, 0E0h; int
0x18001a258  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x18001a25f  mov     rcx, [rbx]; this
0x18001a262  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18001a267  mov     [rbp+pExceptionObject], rbx
0x18001a26b  test    rbx, rbx
0x18001a26e  jz      short loc_18001A273
0x18001a270  inc     dword ptr [rbx+8]
0x18001a273  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18001a27a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a27e  call    _CxxThrowException_0
0x18001a284  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18001a28b  lea     rcx, [rbp+var_58]; this
0x18001a28f  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18001a294  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18001a29b  lea     rcx, [rbp+var_58]; pExceptionObject
0x18001a29f  call    _CxxThrowException_0
0x18001a2a5  mov     rbx, [rbp+arg_18]
0x18001a2a9  mov     rcx, rdi; void *
0x18001a2ac  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18001a2b1  mov     rax, rbx
0x18001a2b4  mov     rbx, [rsp+80h+arg_0]
0x18001a2bc  add     rsp, 80h
0x18001a2c3  pop     r15
0x18001a2c5  pop     r14
0x18001a2c7  pop     rdi
0x18001a2c8  pop     rsi
0x18001a2c9  pop     rbp
0x18001a2ca  retn
```
