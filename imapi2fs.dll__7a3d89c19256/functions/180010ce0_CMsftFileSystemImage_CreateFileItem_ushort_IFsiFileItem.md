# CMsftFileSystemImage::CreateFileItem(ushort *,IFsiFileItem * *)

- ea: `0x180010ce0`
- end: `0x180010fb1`
- name: `?CreateFileItem@CMsftFileSystemImage@@UEAAJPEAGPEAPEAUIFsiFileItem@@@Z`
- size: `721`
- prototype: `int(CMsftFileSystemImage *__hidden this, unsigned __int16 *, struct IFsiFileItem **)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180003a80`
- `0x1800040b0`
- `0x1800048e0`
- `0x180005040`
- `0x18000726c`
- `0x18000960c`
- `0x18000c8d0`
- `0x18000d1c0`
- `0x180010ce0`
- `0x180011c48`
- `0x1800128b4`
- `0x180018fdc`
- `0x1800199b8`
- `0x1800251dc`
- `0x18002d4e4`
- `0x180030b90`
- `0x180051b50`

## string_xrefs

- `0x180010cf9`: `CMsftFileSystemImage::CreateFileItem`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CMsftFileSystemImage::CreateFileItem(
        CMsftFileSystemImage *this,
        unsigned __int16 *a2,
        struct IFsiFileItem **a3)
{
  unsigned int v6; // esi
  CIMAPISystemException *v7; // rax
  CIMAPISystemException *v8; // rax
  CIMAPIException **v9; // rbx
  CIMAPISystemException *v10; // rax
  CIMAPIException **v11; // rbx
  CIMAPIException **pExceptionObject; // [rsp+20h] [rbp-F8h] BYREF
  _QWORD v14[2]; // [rsp+28h] [rbp-F0h] BYREF
  _BYTE v15[8]; // [rsp+38h] [rbp-E0h] BYREF
  _BYTE v16[88]; // [rsp+40h] [rbp-D8h] BYREF
  _BYTE v17[128]; // [rsp+98h] [rbp-80h] BYREF
  CIMAPIException **v18; // [rsp+120h] [rbp+8h] BYREF
  CIMAPIException **v19; // [rsp+130h] [rbp+18h] BYREF
  char v20; // [rsp+138h] [rbp+20h] BYREF

  MethodTrace::MethodTrace((MethodTrace *)v15, "CMsftFileSystemImage::CreateFileItem");
  ImapiClearErrorInfo();
  v14[1] = (char *)this + 80;
  ImapiComObject::LockCS((CMsftFileSystemImage *)((char *)this + 80));
  try
  {
    if ( !a3 )
    {
      v10 = (CIMAPISystemException *)operator new(0x58u);
      v18 = (CIMAPIException **)v10;
      if ( v10 )
        v10 = CIMAPIException::CIMAPIException(v10, -2147467261, L"newItem");
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v18, v10);
      v11 = v18;
      if ( v18 && *v18 )
      {
        CIMAPIException::SetCodeRefInfo(
          *v18,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\filesystemimage.cpp",
          858);
        v14[0] = v11;
        if ( v11 )
          ++*((_DWORD *)v11 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v14;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v17,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v17;
    }
    *a3 = 0;
    v6 = ValidateStringPointer(a2, 1u, 0x10000u);
    if ( v6 == -1062555391 || (v6 = ValidateStringPointer(a2, 1u, 0x10000u), v6 == -2147467261) )
    {
      v8 = (CIMAPISystemException *)operator new(0x58u);
      v18 = (CIMAPIException **)v8;
      if ( v8 )
        v8 = CIMAPIException::CIMAPIException(v8, v6, L"name");
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v18, v8);
      v9 = v18;
      if ( v18 && *v18 )
      {
        CIMAPIException::SetCodeRefInfo(
          *v18,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\filesystemimage.cpp",
          863);
        pExceptionObject = v9;
        if ( v9 )
          ++*((_DWORD *)v9 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v16,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v16;
    }
    if ( (int)ValidateStringPointer(a2, 1u, 0x10000u) >= 0 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v20,
        a2);
      v7 = (CIMAPISystemException *)operator new(0x120u);
      v18 = (CIMAPIException **)v7;
      if ( v7 )
        v7 = (CIMAPISystemException *)ImapiFileInfo::ImapiFileInfo(v7, **((_QWORD **)this + 26), 0, &v20);
      SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v19, v7);
      v18 = v19;
      if ( v19 )
        ++*((_DWORD *)v19 + 2);
      *a3 = (struct IFsiFileItem *)CreateReturnObject<IFsiFileItem,CFsiFileItem>(this, (CIMAPISystemException **)&v18);
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v19);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v20);
    }
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_MsftFileSystemImage);
  }
  ImapiComObject::UnlockCS((CMsftFileSystemImage *)((char *)this + 80));
  MethodTrace::~MethodTrace((MethodTrace *)v15);
  return v6;
}

```

## disassembly

```asm
0x180010ce0  push    rbx
0x180010ce2  push    rsi
0x180010ce3  push    r13
0x180010ce5  push    r14
0x180010ce7  push    r15
0x180010ce9  sub     rsp, 0F0h
0x180010cf0  mov     r15, r8
0x180010cf3  mov     r14, rdx
0x180010cf6  mov     r13, rcx
0x180010cf9  lea     rdx, aCmsftfilesyste_40; "CMsftFileSystemImage::CreateFileItem"
0x180010d00  lea     rcx, [rsp+118h+var_E0]; this
0x180010d05  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x180010d0a  nop
0x180010d0b  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x180010d10  nop
0x180010d11  lea     rbx, [r13+50h]
0x180010d15  mov     [rsp+118h+var_E8], rbx
0x180010d1a  mov     rcx, rbx; this
0x180010d1d  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x180010d22  test    r15, r15
0x180010d25  jz      loc_180010ED4
0x180010d2b  mov     qword ptr [r15], 0
0x180010d32  mov     edx, 1; unsigned __int64
0x180010d37  mov     r8d, 10000h; unsigned __int64
0x180010d3d  mov     rcx, r14; pbstr
0x180010d40  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x180010d45  mov     esi, eax
0x180010d47  cmp     eax, 0C0AAB101h
0x180010d4c  jz      loc_180010E31
0x180010d52  mov     edx, 1; unsigned __int64
0x180010d57  mov     r8d, 10000h; unsigned __int64
0x180010d5d  mov     rcx, r14; pbstr
0x180010d60  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x180010d65  mov     esi, eax
0x180010d67  cmp     eax, 80004003h
0x180010d6c  jz      loc_180010E31
0x180010d72  mov     edx, 1; unsigned __int64
0x180010d77  mov     r8d, 10000h; unsigned __int64
0x180010d7d  mov     rcx, r14; pbstr
0x180010d80  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x180010d85  test    eax, eax
0x180010d87  jns     short loc_180010D8E
0x180010d89  jmp     loc_180010F8C
0x180010d8e  mov     rdx, r14
0x180010d91  lea     rcx, [rsp+118h+arg_18]
0x180010d99  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180010d9e  nop
0x180010d9f  mov     ecx, 120h; unsigned __int64
0x180010da4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010da9  mov     [rsp+118h+arg_0], rax
0x180010db1  test    rax, rax
0x180010db4  jz      short loc_180010DD4
0x180010db6  mov     rdx, [r13+0D0h]
0x180010dbd  lea     r9, [rsp+118h+arg_18]
0x180010dc5  xor     r8d, r8d
0x180010dc8  mov     rdx, [rdx]
0x180010dcb  mov     rcx, rax
0x180010dce  call    ??0ImapiFileInfo@@QEAA@AEAVFileSystemImage@@PEAVImapiFsObjectBase@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; ImapiFileInfo::ImapiFileInfo(FileSystemImage &,ImapiFsObjectBase *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180010dd3  nop
0x180010dd4  mov     rdx, rax
0x180010dd7  lea     rcx, [rsp+118h+arg_10]
0x180010ddf  call    ??0?$SmartPtr@VImportMetadata@@@@QEAA@PEAVImportMetadata@@@Z; SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(ImportMetadata *)
0x180010de4  nop
0x180010de5  mov     rax, [rsp+118h+arg_10]
0x180010ded  mov     [rsp+118h+arg_0], rax
0x180010df5  test    rax, rax
0x180010df8  jz      short loc_180010DFD
0x180010dfa  inc     dword ptr [rax+8]
0x180010dfd  lea     rdx, [rsp+118h+arg_0]
0x180010e05  mov     rcx, r13
0x180010e08  call    ??$CreateReturnObject@UIFsiFileItem@@VCFsiFileItem@@@@YAPEAUIFsiFileItem@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; CreateReturnObject<IFsiFileItem,CFsiFileItem>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x180010e0d  mov     [r15], rax
0x180010e10  lea     rcx, [rsp+118h+arg_10]; void *
0x180010e18  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x180010e1d  nop
0x180010e1e  lea     rcx, [rsp+118h+arg_18]; void *
0x180010e26  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180010e2b  nop
0x180010e2c  jmp     loc_180010F8C
0x180010e31  mov     ecx, 58h ; 'X'; unsigned __int64
0x180010e36  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010e3b  mov     [rsp+118h+arg_0], rax
0x180010e43  test    rax, rax
0x180010e46  jz      short loc_180010E5A
0x180010e48  lea     r8, aName; "name"
0x180010e4f  mov     edx, esi; int
0x180010e51  mov     rcx, rax; this
0x180010e54  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180010e59  nop
0x180010e5a  mov     rdx, rax
0x180010e5d  lea     rcx, [rsp+118h+arg_0]
0x180010e65  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180010e6a  nop
0x180010e6b  mov     rbx, [rsp+118h+arg_0]
0x180010e73  test    rbx, rbx
0x180010e76  jz      short loc_180010EB1
0x180010e78  cmp     qword ptr [rbx], 0
0x180010e7c  jz      short loc_180010EB1
0x180010e7e  mov     r8d, 35Fh; int
0x180010e84  lea     rdx, aDriversStorage_0; "drivers\\storage\\imapi2\\filesystemima"...
0x180010e8b  mov     rcx, [rbx]; this
0x180010e8e  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180010e93  mov     [rsp+118h+pExceptionObject], rbx
0x180010e98  test    rbx, rbx
0x180010e9b  jz      short loc_180010EA0
0x180010e9d  inc     dword ptr [rbx+8]
0x180010ea0  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180010ea7  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x180010eac  call    _CxxThrowException_0
0x180010eb1  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180010eb8  lea     rcx, [rsp+118h+var_D8]; this
0x180010ebd  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180010ec2  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180010ec9  lea     rcx, [rsp+118h+var_D8]; pExceptionObject
0x180010ece  call    _CxxThrowException_0
0x180010ed4  mov     ecx, 58h ; 'X'; unsigned __int64
0x180010ed9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010ede  mov     [rsp+118h+arg_0], rax
0x180010ee6  test    rax, rax
0x180010ee9  jz      short loc_180010F00
0x180010eeb  lea     r8, aNewitem; "newItem"
0x180010ef2  mov     edx, 80004003h; int
0x180010ef7  mov     rcx, rax; this
0x180010efa  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180010eff  nop
0x180010f00  mov     rdx, rax
0x180010f03  lea     rcx, [rsp+118h+arg_0]
0x180010f0b  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180010f10  nop
0x180010f11  mov     rbx, [rsp+118h+arg_0]
0x180010f19  test    rbx, rbx
0x180010f1c  jz      short loc_180010F57
0x180010f1e  cmp     qword ptr [rbx], 0
0x180010f22  jz      short loc_180010F57
0x180010f24  mov     r8d, 35Ah; int
0x180010f2a  lea     rdx, aDriversStorage_0; "drivers\\storage\\imapi2\\filesystemima"...
0x180010f31  mov     rcx, [rbx]; this
0x180010f34  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180010f39  mov     [rsp+118h+var_F0], rbx
0x180010f3e  test    rbx, rbx
0x180010f41  jz      short loc_180010F46
0x180010f43  inc     dword ptr [rbx+8]
0x180010f46  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180010f4d  lea     rcx, [rsp+118h+var_F0]; pExceptionObject
0x180010f52  call    _CxxThrowException_0
0x180010f57  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180010f5e  lea     rcx, [rsp+118h+var_80]; this
0x180010f66  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180010f6b  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180010f72  lea     rcx, [rsp+118h+var_80]; pExceptionObject
0x180010f7a  call    _CxxThrowException_0
0x180010f80  mov     esi, dword ptr [rsp+118h+arg_0]
0x180010f87  mov     rbx, [rsp+118h+var_E8]
0x180010f8c  mov     rcx, rbx; this
0x180010f8f  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x180010f94  nop
0x180010f95  lea     rcx, [rsp+118h+var_E0]; this
0x180010f9a  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x180010f9f  mov     eax, esi
0x180010fa1  add     rsp, 0F0h
0x180010fa8  pop     r15
0x180010faa  pop     r14
0x180010fac  pop     r13
0x180010fae  pop     rsi
0x180010faf  pop     rbx
0x180010fb0  retn
```
