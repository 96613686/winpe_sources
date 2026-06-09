# CreateReturnObject<IProgressItems,CProgressItems>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)

- ea: `0x1800138d8`
- end: `0x180013ae3`
- name: `??$CreateReturnObject@UIProgressItems@@VCProgressItems@@@@YAPEAUIProgressItems@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z`
- size: `523`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180013750`

## callees

- `0x180003a20`
- `0x180005040`
- `0x180007198`
- `0x18000960c`
- `0x18000c8d0`
- `0x18000f90c`
- `0x1800138d8`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18003b434`
- `0x180054b74`
- `0x180088010`

## string_xrefs

- `0x180013954`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`
- `0x180013a70`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`

## pseudocode

```c
__int64 __fastcall CreateReturnObject<IProgressItems,CProgressItems>(
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
  v4 = ATL::CComObject<CProgressItems>::CreateInstance(&v18);
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
          &GUID_2c941fd7_975b_59be_a960_9a2a262853a5,
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
0x1800138d8  mov     [rsp-28h+arg_0], rbx
0x1800138dd  mov     [rsp-28h+arg_8], rdx
0x1800138e2  push    rbp
0x1800138e3  push    rsi
0x1800138e4  push    rdi
0x1800138e5  push    r14
0x1800138e7  push    r15
0x1800138e9  mov     rbp, rsp
0x1800138ec  sub     rsp, 80h
0x1800138f3  mov     rdi, rdx
0x1800138f6  mov     r15, rcx
0x1800138f9  mov     [rbp+arg_10], 0
0x180013901  lea     rcx, [rbp+arg_10]
0x180013905  call    ?CreateInstance@?$CComObject@VCProgressItems@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CProgressItems>::CreateInstance(ATL::CComObject<CProgressItems> * *)
0x18001390a  mov     ebx, eax
0x18001390c  test    eax, eax
0x18001390e  jns     loc_1800139A1
0x180013914  mov     ecx, 58h ; 'X'; unsigned __int64
0x180013919  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001391e  mov     [rbp+arg_10], rax
0x180013922  test    rax, rax
0x180013925  jz      short loc_180013932
0x180013927  mov     edx, ebx; int
0x180013929  mov     rcx, rax; this
0x18001392c  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x180013931  nop
0x180013932  mov     rdx, rax
0x180013935  lea     rcx, [rbp+arg_10]
0x180013939  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001393e  nop
0x18001393f  mov     rbx, [rbp+arg_10]
0x180013943  test    rbx, rbx
0x180013946  jz      short loc_180013980
0x180013948  cmp     qword ptr [rbx], 0
0x18001394c  jz      short loc_180013980
0x18001394e  mov     r8d, 0D0h; int
0x180013954  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x18001395b  mov     rcx, [rbx]; this
0x18001395e  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180013963  mov     [rbp+pExceptionObject], rbx
0x180013967  test    rbx, rbx
0x18001396a  jz      short loc_18001396F
0x18001396c  inc     dword ptr [rbx+8]
0x18001396f  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180013976  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001397a  call    _CxxThrowException_0
0x180013980  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180013987  lea     rcx, [rbp+var_58]; this
0x18001398b  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180013990  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180013997  lea     rcx, [rbp+var_58]; pExceptionObject
0x18001399b  call    _CxxThrowException_0
0x1800139a1  mov     r14, [rbp+arg_10]
0x1800139a5  lea     rsi, [r14+48h]
0x1800139a9  mov     rax, [rsi]
0x1800139ac  mov     rcx, rsi
0x1800139af  mov     rax, [rax+8]
0x1800139b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139b8  mov     rax, [rdi]
0x1800139bb  mov     [rbp+arg_10], rax
0x1800139bf  test    rax, rax
0x1800139c2  jz      short loc_1800139C7
0x1800139c4  inc     dword ptr [rax+8]
0x1800139c7  lea     rdx, [rbp+arg_10]
0x1800139cb  mov     rcx, r14
0x1800139ce  call    ?Init@ImapiComReturnObject@@QEAAXV?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; ImapiComReturnObject::Init(SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x1800139d3  mov     rax, [r14]
0x1800139d6  mov     rbx, [rax+10h]
0x1800139da  mov     [rbp+arg_10], r15
0x1800139de  lea     rcx, [rbp+arg_10]
0x1800139e2  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UIStream@@$1?_GUID_0000000c_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<IStream,&__s_GUID const _GUID_0000000c_0000_0000_c000_000000000046>>::_AddRef(void)
0x1800139e7  lea     rdx, [rbp+arg_10]
0x1800139eb  mov     rcx, r14
0x1800139ee  mov     rax, rbx
0x1800139f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139f6  mov     [rbp+arg_18], 0
0x1800139fe  mov     rax, [rsi]
0x180013a01  lea     r8, [rbp+arg_18]
0x180013a05  lea     rdx, _GUID_2c941fd7_975b_59be_a960_9a2a262853a5
0x180013a0c  mov     rcx, rsi
0x180013a0f  mov     rax, [rax]
0x180013a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a17  mov     ebx, eax
0x180013a19  mov     rdx, [rsi]
0x180013a1c  mov     rcx, rsi
0x180013a1f  mov     rax, [rdx+10h]
0x180013a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a28  test    ebx, ebx
0x180013a2a  jns     loc_180013ABD
0x180013a30  mov     ecx, 58h ; 'X'; unsigned __int64
0x180013a35  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013a3a  mov     [rbp+arg_10], rax
0x180013a3e  test    rax, rax
0x180013a41  jz      short loc_180013A4E
0x180013a43  mov     edx, ebx; int
0x180013a45  mov     rcx, rax; this
0x180013a48  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x180013a4d  nop
0x180013a4e  mov     rdx, rax
0x180013a51  lea     rcx, [rbp+arg_10]
0x180013a55  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180013a5a  nop
0x180013a5b  mov     rbx, [rbp+arg_10]
0x180013a5f  test    rbx, rbx
0x180013a62  jz      short loc_180013A9C
0x180013a64  cmp     qword ptr [rbx], 0
0x180013a68  jz      short loc_180013A9C
0x180013a6a  mov     r8d, 0E0h; int
0x180013a70  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x180013a77  mov     rcx, [rbx]; this
0x180013a7a  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180013a7f  mov     [rbp+pExceptionObject], rbx
0x180013a83  test    rbx, rbx
0x180013a86  jz      short loc_180013A8B
0x180013a88  inc     dword ptr [rbx+8]
0x180013a8b  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180013a92  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180013a96  call    _CxxThrowException_0
0x180013a9c  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180013aa3  lea     rcx, [rbp+var_58]; this
0x180013aa7  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180013aac  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180013ab3  lea     rcx, [rbp+var_58]; pExceptionObject
0x180013ab7  call    _CxxThrowException_0
0x180013abd  mov     rbx, [rbp+arg_18]
0x180013ac1  mov     rcx, rdi; void *
0x180013ac4  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x180013ac9  mov     rax, rbx
0x180013acc  mov     rbx, [rsp+80h+arg_0]
0x180013ad4  add     rsp, 80h
0x180013adb  pop     r15
0x180013add  pop     r14
0x180013adf  pop     rdi
0x180013ae0  pop     rsi
0x180013ae1  pop     rbp
0x180013ae2  retn
```
