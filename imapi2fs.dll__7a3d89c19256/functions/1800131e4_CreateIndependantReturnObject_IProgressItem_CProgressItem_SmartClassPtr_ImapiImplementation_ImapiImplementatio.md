# CreateIndependantReturnObject<IProgressItem,CProgressItem>(SmartClassPtr<ImapiImplementation,ImapiImplementation>)

- ea: `0x1800131e4`
- end: `0x1800133b8`
- name: `??$CreateIndependantReturnObject@UIProgressItem@@VCProgressItem@@@@YAPEAUIProgressItem@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z`
- size: `468`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `5`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180012f30`
- `0x180013500`
- `0x180054ef0`
- `0x180055290`
- `0x180055670`

## callees

- `0x180003a20`
- `0x180005040`
- `0x180007198`
- `0x18000960c`
- `0x18000c8d0`
- `0x1800131e4`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18003b434`
- `0x180054a64`
- `0x180088010`

## string_xrefs

- `0x180013257`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`
- `0x180013350`: `drivers\storage\imapi2\filesystemimaging\fsi\ImapiComInterface.h`

## pseudocode

```c
__int64 __fastcall CreateIndependantReturnObject<IProgressItem,CProgressItem>(CIMAPISystemException **a1)
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
  v2 = ATL::CComObject<CProgressItem>::CreateInstance(&v14);
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
  v8 = (**(__int64 (__fastcall ***)(char *, GUID *, __int64 *))v6)(v6, &GUID_2c941fd5_975b_59be_a960_9a2a262853a5, &v15);
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
0x1800131e4  mov     [rsp-8+arg_0], rcx
0x1800131e9  push    rbp
0x1800131ea  push    rbx
0x1800131eb  push    rsi
0x1800131ec  push    rdi
0x1800131ed  lea     rbp, [rsp-3Fh]
0x1800131f2  sub     rsp, 88h
0x1800131f9  mov     rdi, rcx
0x1800131fc  mov     [rbp+57h+arg_8], 0
0x180013204  lea     rcx, [rbp+57h+arg_8]
0x180013208  call    ?CreateInstance@?$CComObject@VCProgressItem@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CProgressItem>::CreateInstance(ATL::CComObject<CProgressItem> * *)
0x18001320d  mov     ebx, eax
0x18001320f  test    eax, eax
0x180013211  jns     loc_1800132A4
0x180013217  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001321c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013221  mov     [rbp+57h+arg_8], rax
0x180013225  test    rax, rax
0x180013228  jz      short loc_180013235
0x18001322a  mov     edx, ebx; int
0x18001322c  mov     rcx, rax; this
0x18001322f  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x180013234  nop
0x180013235  mov     rdx, rax
0x180013238  lea     rcx, [rbp+57h+arg_8]
0x18001323c  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180013241  nop
0x180013242  mov     rbx, [rbp+57h+arg_8]
0x180013246  test    rbx, rbx
0x180013249  jz      short loc_180013283
0x18001324b  cmp     qword ptr [rbx], 0
0x18001324f  jz      short loc_180013283
0x180013251  mov     r8d, 0EFh; int
0x180013257  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x18001325e  mov     rcx, [rbx]; this
0x180013261  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180013266  mov     [rbp+57h+pExceptionObject], rbx
0x18001326a  test    rbx, rbx
0x18001326d  jz      short loc_180013272
0x18001326f  inc     dword ptr [rbx+8]
0x180013272  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180013279  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001327d  call    _CxxThrowException_0
0x180013283  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18001328a  lea     rcx, [rbp+57h+var_80]; this
0x18001328e  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180013293  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18001329a  lea     rcx, [rbp+57h+var_80]; pExceptionObject
0x18001329e  call    _CxxThrowException_0
0x1800132a4  mov     rsi, [rbp+57h+arg_8]
0x1800132a8  lea     rbx, [rsi+48h]
0x1800132ac  mov     rax, [rbx]
0x1800132af  mov     rcx, rbx
0x1800132b2  mov     rax, [rax+8]
0x1800132b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132bb  mov     rax, [rdi]
0x1800132be  mov     [rbp+57h+arg_8], rax
0x1800132c2  test    rax, rax
0x1800132c5  jz      short loc_1800132CA
0x1800132c7  inc     dword ptr [rax+8]
0x1800132ca  lea     rdx, [rbp+57h+arg_8]
0x1800132ce  mov     rcx, rsi
0x1800132d1  call    ?Init@ImapiComReturnObject@@QEAAXV?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; ImapiComReturnObject::Init(SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x1800132d6  mov     [rbp+57h+arg_10], 0
0x1800132de  mov     rax, [rbx]
0x1800132e1  lea     r8, [rbp+57h+arg_10]
0x1800132e5  lea     rdx, _GUID_2c941fd5_975b_59be_a960_9a2a262853a5
0x1800132ec  mov     rcx, rbx
0x1800132ef  mov     rax, [rax]
0x1800132f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132f7  mov     esi, eax
0x1800132f9  mov     rdx, [rbx]
0x1800132fc  mov     rcx, rbx
0x1800132ff  mov     rax, [rdx+10h]
0x180013303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013308  test    esi, esi
0x18001330a  jns     loc_18001339D
0x180013310  mov     ecx, 58h ; 'X'; unsigned __int64
0x180013315  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001331a  mov     [rbp+57h+arg_8], rax
0x18001331e  test    rax, rax
0x180013321  jz      short loc_18001332E
0x180013323  mov     edx, esi; int
0x180013325  mov     rcx, rax; this
0x180013328  call    ??0CIMAPISystemException@@QEAA@JZZ; CIMAPISystemException::CIMAPISystemException(long,...)
0x18001332d  nop
0x18001332e  mov     rdx, rax
0x180013331  lea     rcx, [rbp+57h+arg_8]
0x180013335  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001333a  nop
0x18001333b  mov     rbx, [rbp+57h+arg_8]
0x18001333f  test    rbx, rbx
0x180013342  jz      short loc_18001337C
0x180013344  cmp     qword ptr [rbx], 0
0x180013348  jz      short loc_18001337C
0x18001334a  mov     r8d, 0F9h; int
0x180013350  lea     rdx, aDriversStorage_10; "drivers\\storage\\imapi2\\filesystemima"...
0x180013357  mov     rcx, [rbx]; this
0x18001335a  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18001335f  mov     [rbp+57h+pExceptionObject], rbx
0x180013363  test    rbx, rbx
0x180013366  jz      short loc_18001336B
0x180013368  inc     dword ptr [rbx+8]
0x18001336b  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180013372  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180013376  call    _CxxThrowException_0
0x18001337c  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180013383  lea     rcx, [rbp+57h+var_80]; this
0x180013387  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18001338c  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180013393  lea     rcx, [rbp+57h+var_80]; pExceptionObject
0x180013397  call    _CxxThrowException_0
0x18001339d  mov     rbx, [rbp+57h+arg_10]
0x1800133a1  mov     rcx, rdi; void *
0x1800133a4  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x1800133a9  mov     rax, rbx
0x1800133ac  add     rsp, 88h
0x1800133b3  pop     rdi
0x1800133b4  pop     rsi
0x1800133b5  pop     rbx
0x1800133b6  pop     rbp
0x1800133b7  retn
```
