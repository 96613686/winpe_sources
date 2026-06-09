# CFsiDirectoryItem::get_Item(ushort *,IFsiItem * *)

- ea: `0x1800118b0`
- end: `0x180011c41`
- name: `?get_Item@CFsiDirectoryItem@@UEAAJPEAGPEAPEAUIFsiItem@@@Z`
- size: `913`
- prototype: `int(CFsiDirectoryItem *__hidden this, unsigned __int16 *, struct IFsiItem **)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180003a80`
- `0x1800040b0`
- `0x1800048e0`
- `0x180005040`
- `0x18000960c`
- `0x18000ba24`
- `0x18000c8d0`
- `0x18000d1c0`
- `0x1800118b0`
- `0x180011c48`
- `0x180018fdc`
- `0x1800199b8`
- `0x1800251dc`
- `0x18002d4e4`
- `0x180030b90`
- `0x18003bd18`
- `0x18003bf2c`

## string_xrefs

- `0x1800118c9`: `CFsiDirectoryItem::get_Item`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CFsiDirectoryItem::get_Item(CFsiDirectoryItem *this, unsigned __int16 *a2, struct IFsiItem **a3)
{
  unsigned int v6; // esi
  struct IFsiItem *Return; // rax
  CIMAPISystemException *v8; // rax
  CIMAPIException **v9; // rbx
  CIMAPISystemException *v10; // rax
  CIMAPIException **v11; // rbx
  CIMAPISystemException *v12; // rax
  CIMAPIException **v13; // rbx
  CIMAPIException **pExceptionObject; // [rsp+30h] [rbp-158h] BYREF
  CIMAPIException **v16; // [rsp+38h] [rbp-150h] BYREF
  _QWORD v17[2]; // [rsp+40h] [rbp-148h] BYREF
  _BYTE v18[8]; // [rsp+50h] [rbp-138h] BYREF
  _BYTE v19[88]; // [rsp+58h] [rbp-130h] BYREF
  _BYTE v20[88]; // [rsp+B0h] [rbp-D8h] BYREF
  _BYTE v21[128]; // [rsp+108h] [rbp-80h] BYREF
  CIMAPIException **v22; // [rsp+190h] [rbp+8h] BYREF
  CIMAPIException **v23; // [rsp+1A0h] [rbp+18h] BYREF
  char v24; // [rsp+1A8h] [rbp+20h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)v18, "CFsiDirectoryItem::get_Item");
  ImapiClearErrorInfo();
  v17[1] = (char *)this - 80;
  ImapiComObject::LockCS((CFsiDirectoryItem *)((char *)this - 80));
  try
  {
    if ( !a3 )
    {
      v12 = (CIMAPISystemException *)operator new(0x58u);
      v22 = (CIMAPIException **)v12;
      if ( v12 )
        v12 = CIMAPIException::CIMAPIException(v12, -2147467261, L"item");
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v22, v12);
      v13 = v22;
      if ( v22 && *v22 )
      {
        CIMAPIException::SetCodeRefInfo(*v22, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 92);
        v17[0] = v13;
        if ( v13 )
          ++*((_DWORD *)v13 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v17;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v21,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v21;
    }
    *a3 = 0;
    v6 = ValidateStringPointer(a2, 1u, 0x10000u);
    if ( v6 == -1062555391 || (v6 = ValidateStringPointer(a2, 1u, 0x10000u), v6 == -2147467261) )
    {
      v10 = (CIMAPISystemException *)operator new(0x58u);
      v22 = (CIMAPIException **)v10;
      if ( v10 )
        v10 = CIMAPIException::CIMAPIException(v10, v6, L"path");
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v22, v10);
      v11 = v22;
      if ( v22 && *v22 )
      {
        CIMAPIException::SetCodeRefInfo(*v22, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 97);
        v16 = v11;
        if ( v11 )
          ++*((_DWORD *)v11 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v16;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v20,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v20;
    }
    if ( (int)ValidateStringPointer(a2, 1u, 0x10000u) >= 0 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v24,
        a2);
      ImapiDirectoryInfo::GetFileDirRecord(**((_QWORD **)this + 8), &v23, &v24);
      if ( !v23 || !*v23 )
      {
        v8 = (CIMAPISystemException *)operator new(0x58u);
        v22 = (CIMAPIException **)v8;
        if ( v8 )
          v8 = CIMAPIException::CIMAPIException(v8, -1062555368, a2);
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v22, v8);
        v9 = v22;
        if ( v22 && *v22 )
        {
          CIMAPIException::SetCodeRefInfo(*v22, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 103);
          pExceptionObject = v9;
          if ( v9 )
            ++*((_DWORD *)v9 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v19,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v19;
      }
      if ( !*((_DWORD *)*v23 + 14) || *((_DWORD *)*v23 + 14) == 3 )
      {
        v22 = v23;
        if ( v23 )
          ++*((_DWORD *)v23 + 2);
        Return = (struct IFsiItem *)CreateReturnObject<IFsiItem,CFsiDirectoryItem>(
                                      *((CIMAPISystemException **)this - 2),
                                      (CIMAPISystemException **)&v22);
      }
      else
      {
        v22 = v23;
        if ( v23 )
          ++*((_DWORD *)v23 + 2);
        Return = (struct IFsiItem *)CreateReturnObject<IFsiItem,CFsiFileItem>(
                                      *((CIMAPISystemException **)this - 2),
                                      (CIMAPISystemException **)&v22);
      }
      *a3 = Return;
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v23);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v24);
    }
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_FsiDirectoryItem);
  }
  ImapiComObject::UnlockCS((CFsiDirectoryItem *)((char *)this - 80));
  MethodTrace::~MethodTrace((MethodTrace *)v18);
  return v6;
}

```

## disassembly

```asm
0x1800118b0  push    rbx
0x1800118b2  push    rsi
0x1800118b3  push    r12
0x1800118b5  push    r14
0x1800118b7  push    r15
0x1800118b9  sub     rsp, 160h
0x1800118c0  mov     r12, r8
0x1800118c3  mov     r14, rdx
0x1800118c6  mov     r15, rcx
0x1800118c9  lea     rdx, aCfsidirectoryi; "CFsiDirectoryItem::get_Item"
0x1800118d0  lea     rcx, [rsp+188h+var_138]; this
0x1800118d5  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x1800118da  nop
0x1800118db  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x1800118e0  nop
0x1800118e1  lea     rbx, [r15-50h]
0x1800118e5  mov     [rsp+188h+var_140], rbx
0x1800118ea  mov     rcx, rbx; this
0x1800118ed  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x1800118f2  test    r12, r12
0x1800118f5  jz      loc_180011B64
0x1800118fb  mov     qword ptr [r12], 0
0x180011903  mov     edx, 1; unsigned __int64
0x180011908  mov     r8d, 10000h; unsigned __int64
0x18001190e  mov     rcx, r14; pbstr
0x180011911  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x180011916  mov     esi, eax
0x180011918  cmp     eax, 0C0AAB101h
0x18001191d  jz      loc_180011ABB
0x180011923  mov     edx, 1; unsigned __int64
0x180011928  mov     r8d, 10000h; unsigned __int64
0x18001192e  mov     rcx, r14; pbstr
0x180011931  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x180011936  mov     esi, eax
0x180011938  cmp     eax, 80004003h
0x18001193d  jz      loc_180011ABB
0x180011943  mov     edx, 1; unsigned __int64
0x180011948  mov     r8d, 10000h; unsigned __int64
0x18001194e  mov     rcx, r14; pbstr
0x180011951  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x180011956  test    eax, eax
0x180011958  jns     short loc_18001195F
0x18001195a  jmp     loc_180011C1C
0x18001195f  mov     rdx, r14
0x180011962  lea     rcx, [rsp+188h+arg_18]
0x18001196a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001196f  nop
0x180011970  mov     rcx, [r15+40h]
0x180011974  lea     r8, [rsp+188h+arg_18]
0x18001197c  lea     rdx, [rsp+188h+arg_10]
0x180011984  mov     rcx, [rcx]
0x180011987  call    ?GetFileDirRecord@ImapiDirectoryInfo@@QEAA?AV?$SmartClassPtr@VImapiFsObjectBase@@VImapiImplementation@@@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N1@Z; ImapiDirectoryInfo::GetFileDirRecord(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,bool,bool)
0x18001198c  nop
0x18001198d  mov     rax, [rsp+188h+arg_10]
0x180011995  test    rax, rax
0x180011998  jz      short loc_180011A19
0x18001199a  cmp     qword ptr [rax], 0
0x18001199e  jz      short loc_180011A19
0x1800119a0  mov     rcx, [rax]
0x1800119a3  cmp     dword ptr [rcx+38h], 0
0x1800119a7  jz      short loc_1800119D2
0x1800119a9  cmp     dword ptr [rcx+38h], 3
0x1800119ad  jz      short loc_1800119D2
0x1800119af  mov     [rsp+188h+arg_0], rax
0x1800119b7  test    rax, rax
0x1800119ba  jz      short loc_1800119BF
0x1800119bc  inc     dword ptr [rax+8]
0x1800119bf  lea     rdx, [rsp+188h+arg_0]
0x1800119c7  mov     rcx, [r15-10h]
0x1800119cb  call    ??$CreateReturnObject@UIFsiItem@@VCFsiFileItem@@@@YAPEAUIFsiItem@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; CreateReturnObject<IFsiItem,CFsiFileItem>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x1800119d0  jmp     short loc_1800119F4
0x1800119d2  mov     [rsp+188h+arg_0], rax
0x1800119da  test    rax, rax
0x1800119dd  jz      short loc_1800119E2
0x1800119df  inc     dword ptr [rax+8]
0x1800119e2  lea     rdx, [rsp+188h+arg_0]
0x1800119ea  mov     rcx, [r15-10h]
0x1800119ee  call    ??$CreateReturnObject@UIFsiItem@@VCFsiDirectoryItem@@@@YAPEAUIFsiItem@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; CreateReturnObject<IFsiItem,CFsiDirectoryItem>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x1800119f3  nop
0x1800119f4  mov     [r12], rax
0x1800119f8  lea     rcx, [rsp+188h+arg_10]; void *
0x180011a00  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x180011a05  nop
0x180011a06  lea     rcx, [rsp+188h+arg_18]; void *
0x180011a0e  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180011a13  nop
0x180011a14  jmp     loc_180011C1C
0x180011a19  mov     ecx, 58h ; 'X'; unsigned __int64
0x180011a1e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011a23  mov     [rsp+188h+arg_0], rax
0x180011a2b  test    rax, rax
0x180011a2e  jz      short loc_180011A41
0x180011a30  mov     r8, r14
0x180011a33  mov     edx, 0C0AAB118h; int
0x180011a38  mov     rcx, rax; this
0x180011a3b  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180011a40  nop
0x180011a41  mov     rdx, rax
0x180011a44  lea     rcx, [rsp+188h+arg_0]
0x180011a4c  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180011a51  nop
0x180011a52  mov     rbx, [rsp+188h+arg_0]
0x180011a5a  test    rbx, rbx
0x180011a5d  jz      short loc_180011A98
0x180011a5f  cmp     qword ptr [rbx], 0
0x180011a63  jz      short loc_180011A98
0x180011a65  mov     r8d, 67h ; 'g'; int
0x180011a6b  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x180011a72  mov     rcx, [rbx]; this
0x180011a75  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180011a7a  mov     [rsp+188h+pExceptionObject], rbx
0x180011a7f  test    rbx, rbx
0x180011a82  jz      short loc_180011A87
0x180011a84  inc     dword ptr [rbx+8]
0x180011a87  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180011a8e  lea     rcx, [rsp+188h+pExceptionObject]; pExceptionObject
0x180011a93  call    _CxxThrowException_0
0x180011a98  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180011a9f  lea     rcx, [rsp+188h+var_130]; this
0x180011aa4  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180011aa9  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180011ab0  lea     rcx, [rsp+188h+var_130]; pExceptionObject
0x180011ab5  call    _CxxThrowException_0
0x180011abb  mov     ecx, 58h ; 'X'; unsigned __int64
0x180011ac0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011ac5  mov     [rsp+188h+arg_0], rax
0x180011acd  test    rax, rax
0x180011ad0  jz      short loc_180011AE4
0x180011ad2  lea     r8, aPath; "path"
0x180011ad9  mov     edx, esi; int
0x180011adb  mov     rcx, rax; this
0x180011ade  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180011ae3  nop
0x180011ae4  mov     rdx, rax
0x180011ae7  lea     rcx, [rsp+188h+arg_0]
0x180011aef  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180011af4  nop
0x180011af5  mov     rbx, [rsp+188h+arg_0]
0x180011afd  test    rbx, rbx
0x180011b00  jz      short loc_180011B3B
0x180011b02  cmp     qword ptr [rbx], 0
0x180011b06  jz      short loc_180011B3B
0x180011b08  mov     r8d, 61h ; 'a'; int
0x180011b0e  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x180011b15  mov     rcx, [rbx]; this
0x180011b18  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180011b1d  mov     [rsp+188h+var_150], rbx
0x180011b22  test    rbx, rbx
0x180011b25  jz      short loc_180011B2A
0x180011b27  inc     dword ptr [rbx+8]
0x180011b2a  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180011b31  lea     rcx, [rsp+188h+var_150]; pExceptionObject
0x180011b36  call    _CxxThrowException_0
0x180011b3b  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180011b42  lea     rcx, [rsp+188h+var_D8]; this
0x180011b4a  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180011b4f  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180011b56  lea     rcx, [rsp+188h+var_D8]; pExceptionObject
0x180011b5e  call    _CxxThrowException_0
0x180011b64  mov     ecx, 58h ; 'X'; unsigned __int64
0x180011b69  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011b6e  mov     [rsp+188h+arg_0], rax
0x180011b76  test    rax, rax
0x180011b79  jz      short loc_180011B90
0x180011b7b  lea     r8, aItem; "item"
0x180011b82  mov     edx, 80004003h; int
0x180011b87  mov     rcx, rax; this
0x180011b8a  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180011b8f  nop
0x180011b90  mov     rdx, rax
0x180011b93  lea     rcx, [rsp+188h+arg_0]
0x180011b9b  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180011ba0  nop
0x180011ba1  mov     rbx, [rsp+188h+arg_0]
0x180011ba9  test    rbx, rbx
0x180011bac  jz      short loc_180011BE7
0x180011bae  cmp     qword ptr [rbx], 0
0x180011bb2  jz      short loc_180011BE7
0x180011bb4  mov     r8d, 5Ch ; '\'; int
0x180011bba  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x180011bc1  mov     rcx, [rbx]; this
0x180011bc4  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180011bc9  mov     [rsp+188h+var_148], rbx
0x180011bce  test    rbx, rbx
0x180011bd1  jz      short loc_180011BD6
0x180011bd3  inc     dword ptr [rbx+8]
0x180011bd6  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180011bdd  lea     rcx, [rsp+188h+var_148]; pExceptionObject
0x180011be2  call    _CxxThrowException_0
0x180011be7  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180011bee  lea     rcx, [rsp+188h+var_80]; this
0x180011bf6  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180011bfb  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180011c02  lea     rcx, [rsp+188h+var_80]; pExceptionObject
0x180011c0a  call    _CxxThrowException_0
0x180011c10  mov     esi, dword ptr [rsp+188h+arg_0]
0x180011c17  mov     rbx, [rsp+188h+var_140]
0x180011c1c  mov     rcx, rbx; this
0x180011c1f  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x180011c24  nop
0x180011c25  lea     rcx, [rsp+188h+var_138]; this
0x180011c2a  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x180011c2f  mov     eax, esi
0x180011c31  add     rsp, 160h
0x180011c38  pop     r15
0x180011c3a  pop     r14
0x180011c3c  pop     r12
0x180011c3e  pop     rsi
0x180011c3f  pop     rbx
0x180011c40  retn
```
