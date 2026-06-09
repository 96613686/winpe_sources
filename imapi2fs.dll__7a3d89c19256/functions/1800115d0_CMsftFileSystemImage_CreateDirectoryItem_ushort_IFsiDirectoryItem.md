# CMsftFileSystemImage::CreateDirectoryItem(ushort *,IFsiDirectoryItem * *)

- ea: `0x1800115d0`
- end: `0x1800118a1`
- name: `?CreateDirectoryItem@CMsftFileSystemImage@@UEAAJPEAGPEAPEAUIFsiDirectoryItem@@@Z`
- size: `721`
- prototype: `int(CMsftFileSystemImage *__hidden this, unsigned __int16 *, struct IFsiDirectoryItem **)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

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
- `0x1800115d0`
- `0x180011c48`
- `0x180011c68`
- `0x180018fdc`
- `0x1800199b8`
- `0x1800251dc`
- `0x18002d4e4`
- `0x180030b90`
- `0x180051904`

## string_xrefs

- `0x1800115e9`: `CMsftFileSystemImage::CreateDirectoryItem`

## pseudocode

```c
__int64 __fastcall CMsftFileSystemImage::CreateDirectoryItem(
        CMsftFileSystemImage *this,
        unsigned __int16 *a2,
        struct IFsiDirectoryItem **a3)
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

  MethodTrace::MethodTrace((MethodTrace *)v15, "CMsftFileSystemImage::CreateDirectoryItem");
  ImapiClearErrorInfo();
  v14[1] = (char *)this + 80;
  ImapiComObject::LockCS((CMsftFileSystemImage *)((char *)this + 80));
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
        839);
      v14[0] = v11;
      if ( v11 )
        ++*((_DWORD *)v11 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v14;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v17, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
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
        844);
      pExceptionObject = v9;
      if ( v9 )
        ++*((_DWORD *)v9 + 2);
      throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
    }
    CIMAPIException::CIMAPIException((CIMAPIException *)v16, (const struct CIMAPIException *)&CIMAPIException::badAlloc);
    throw (CIMAPIException *)v16;
  }
  if ( (int)ValidateStringPointer(a2, 1u, 0x10000u) >= 0 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v20,
      a2);
    v7 = (CIMAPISystemException *)operator new(0x318u);
    v18 = (CIMAPIException **)v7;
    if ( v7 )
      v7 = (CIMAPISystemException *)ImapiDirectoryInfo::ImapiDirectoryInfo(v7);
    SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(&v19, v7);
    v18 = v19;
    if ( v19 )
      ++*((_DWORD *)v19 + 2);
    *a3 = (struct IFsiDirectoryItem *)CreateReturnObject<IFsiDirectoryItem,CFsiDirectoryItem>(
                                        this,
                                        (CIMAPISystemException **)&v18);
    SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v19);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v20);
  }
  ImapiComObject::UnlockCS((CMsftFileSystemImage *)((char *)this + 80));
  MethodTrace::~MethodTrace((MethodTrace *)v15);
  return v6;
}

```

## disassembly

```asm
0x1800115d0  push    rbx
0x1800115d2  push    rsi
0x1800115d3  push    r13
0x1800115d5  push    r14
0x1800115d7  push    r15
0x1800115d9  sub     rsp, 0F0h
0x1800115e0  mov     r15, r8
0x1800115e3  mov     r14, rdx
0x1800115e6  mov     r13, rcx
0x1800115e9  lea     rdx, aCmsftfilesyste_2; "CMsftFileSystemImage::CreateDirectoryIt"...
0x1800115f0  lea     rcx, [rsp+118h+var_E0]; this
0x1800115f5  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x1800115fa  nop
0x1800115fb  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x180011600  nop
0x180011601  lea     rbx, [r13+50h]
0x180011605  mov     [rsp+118h+var_E8], rbx
0x18001160a  mov     rcx, rbx; this
0x18001160d  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x180011612  test    r15, r15
0x180011615  jz      loc_1800117C4
0x18001161b  mov     qword ptr [r15], 0
0x180011622  mov     edx, 1; unsigned __int64
0x180011627  mov     r8d, 10000h; unsigned __int64
0x18001162d  mov     rcx, r14; pbstr
0x180011630  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x180011635  mov     esi, eax
0x180011637  cmp     eax, 0C0AAB101h
0x18001163c  jz      loc_180011721
0x180011642  mov     edx, 1; unsigned __int64
0x180011647  mov     r8d, 10000h; unsigned __int64
0x18001164d  mov     rcx, r14; pbstr
0x180011650  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x180011655  mov     esi, eax
0x180011657  cmp     eax, 80004003h
0x18001165c  jz      loc_180011721
0x180011662  mov     edx, 1; unsigned __int64
0x180011667  mov     r8d, 10000h; unsigned __int64
0x18001166d  mov     rcx, r14; pbstr
0x180011670  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x180011675  test    eax, eax
0x180011677  jns     short loc_18001167E
0x180011679  jmp     loc_18001187C
0x18001167e  mov     rdx, r14
0x180011681  lea     rcx, [rsp+118h+arg_18]
0x180011689  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001168e  nop
0x18001168f  mov     ecx, 318h; unsigned __int64
0x180011694  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011699  mov     [rsp+118h+arg_0], rax
0x1800116a1  test    rax, rax
0x1800116a4  jz      short loc_1800116C4
0x1800116a6  mov     rdx, [r13+0D0h]
0x1800116ad  xor     r9d, r9d
0x1800116b0  lea     r8, [rsp+118h+arg_18]
0x1800116b8  mov     rdx, [rdx]
0x1800116bb  mov     rcx, rax; this
0x1800116be  call    ??0ImapiDirectoryInfo@@QEAA@AEAVFileSystemImage@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVImapiFsObjectBase@@@Z; ImapiDirectoryInfo::ImapiDirectoryInfo(FileSystemImage &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ImapiFsObjectBase *)
0x1800116c3  nop
0x1800116c4  mov     rdx, rax
0x1800116c7  lea     rcx, [rsp+118h+arg_10]
0x1800116cf  call    ??0?$SmartPtr@VImportMetadata@@@@QEAA@PEAVImportMetadata@@@Z; SmartPtr<ImportMetadata>::SmartPtr<ImportMetadata>(ImportMetadata *)
0x1800116d4  nop
0x1800116d5  mov     rax, [rsp+118h+arg_10]
0x1800116dd  mov     [rsp+118h+arg_0], rax
0x1800116e5  test    rax, rax
0x1800116e8  jz      short loc_1800116ED
0x1800116ea  inc     dword ptr [rax+8]
0x1800116ed  lea     rdx, [rsp+118h+arg_0]
0x1800116f5  mov     rcx, r13
0x1800116f8  call    ??$CreateReturnObject@UIFsiDirectoryItem@@VCFsiDirectoryItem@@@@YAPEAUIFsiDirectoryItem@@PEAUIUnknown@@V?$SmartClassPtr@VImapiImplementation@@V1@@@@Z; CreateReturnObject<IFsiDirectoryItem,CFsiDirectoryItem>(IUnknown *,SmartClassPtr<ImapiImplementation,ImapiImplementation>)
0x1800116fd  mov     [r15], rax
0x180011700  lea     rcx, [rsp+118h+arg_10]; void *
0x180011708  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18001170d  nop
0x18001170e  lea     rcx, [rsp+118h+arg_18]; void *
0x180011716  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001171b  nop
0x18001171c  jmp     loc_18001187C
0x180011721  mov     ecx, 58h ; 'X'; unsigned __int64
0x180011726  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001172b  mov     [rsp+118h+arg_0], rax
0x180011733  test    rax, rax
0x180011736  jz      short loc_18001174A
0x180011738  lea     r8, aName; "name"
0x18001173f  mov     edx, esi; int
0x180011741  mov     rcx, rax; this
0x180011744  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180011749  nop
0x18001174a  mov     rdx, rax
0x18001174d  lea     rcx, [rsp+118h+arg_0]
0x180011755  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18001175a  nop
0x18001175b  mov     rbx, [rsp+118h+arg_0]
0x180011763  test    rbx, rbx
0x180011766  jz      short loc_1800117A1
0x180011768  cmp     qword ptr [rbx], 0
0x18001176c  jz      short loc_1800117A1
0x18001176e  mov     r8d, 34Ch; int
0x180011774  lea     rdx, aDriversStorage_0; "drivers\\storage\\imapi2\\filesystemima"...
0x18001177b  mov     rcx, [rbx]; this
0x18001177e  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180011783  mov     [rsp+118h+pExceptionObject], rbx
0x180011788  test    rbx, rbx
0x18001178b  jz      short loc_180011790
0x18001178d  inc     dword ptr [rbx+8]
0x180011790  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180011797  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18001179c  call    _CxxThrowException_0
0x1800117a1  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x1800117a8  lea     rcx, [rsp+118h+var_D8]; this
0x1800117ad  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x1800117b2  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x1800117b9  lea     rcx, [rsp+118h+var_D8]; pExceptionObject
0x1800117be  call    _CxxThrowException_0
0x1800117c4  mov     ecx, 58h ; 'X'; unsigned __int64
0x1800117c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800117ce  mov     [rsp+118h+arg_0], rax
0x1800117d6  test    rax, rax
0x1800117d9  jz      short loc_1800117F0
0x1800117db  lea     r8, aNewitem; "newItem"
0x1800117e2  mov     edx, 80004003h; int
0x1800117e7  mov     rcx, rax; this
0x1800117ea  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x1800117ef  nop
0x1800117f0  mov     rdx, rax
0x1800117f3  lea     rcx, [rsp+118h+arg_0]
0x1800117fb  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180011800  nop
0x180011801  mov     rbx, [rsp+118h+arg_0]
0x180011809  test    rbx, rbx
0x18001180c  jz      short loc_180011847
0x18001180e  cmp     qword ptr [rbx], 0
0x180011812  jz      short loc_180011847
0x180011814  mov     r8d, 347h; int
0x18001181a  lea     rdx, aDriversStorage_0; "drivers\\storage\\imapi2\\filesystemima"...
0x180011821  mov     rcx, [rbx]; this
0x180011824  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180011829  mov     [rsp+118h+var_F0], rbx
0x18001182e  test    rbx, rbx
0x180011831  jz      short loc_180011836
0x180011833  inc     dword ptr [rbx+8]
0x180011836  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18001183d  lea     rcx, [rsp+118h+var_F0]; pExceptionObject
0x180011842  call    _CxxThrowException_0
0x180011847  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18001184e  lea     rcx, [rsp+118h+var_80]; this
0x180011856  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18001185b  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180011862  lea     rcx, [rsp+118h+var_80]; pExceptionObject
0x18001186a  call    _CxxThrowException_0
0x180011870  mov     esi, dword ptr [rsp+118h+arg_0]
0x180011877  mov     rbx, [rsp+118h+var_E8]
0x18001187c  mov     rcx, rbx; this
0x18001187f  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x180011884  nop
0x180011885  lea     rcx, [rsp+118h+var_E0]; this
0x18001188a  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18001188f  mov     eax, esi
0x180011891  add     rsp, 0F0h
0x180011898  pop     r15
0x18001189a  pop     r14
0x18001189c  pop     r13
0x18001189e  pop     rsi
0x18001189f  pop     rbx
0x1800118a0  retn
```
