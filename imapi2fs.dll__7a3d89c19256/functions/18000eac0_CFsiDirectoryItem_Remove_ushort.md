# CFsiDirectoryItem::Remove(ushort *)

- ea: `0x18000eac0`
- end: `0x18000ef3a`
- name: `?Remove@CFsiDirectoryItem@@UEAAJPEAG@Z`
- size: `1146`
- prototype: `int(CFsiDirectoryItem *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

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
- `0x18000eac0`
- `0x18000f28c`
- `0x180011c48`
- `0x1800133c0`
- `0x180018fdc`
- `0x1800199b8`
- `0x180023c08`
- `0x1800251dc`
- `0x18002d4e4`
- `0x180030b90`
- `0x180047c94`

## string_xrefs

- `0x18000eb03`: `CFsiDirectoryItem::Remove`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CFsiDirectoryItem::Remove(CFsiDirectoryItem *this, unsigned __int16 *a2)
{
  ImapiComObject *v4; // r13
  unsigned int v5; // r12d
  int v6; // eax
  int v7; // ebx
  __int64 v8; // rax
  CIMAPIException *v9; // rbx
  const struct ATL::CComBSTR *FullPathOriginal; // rax
  CIMAPIException *v11; // rax
  CIMAPIException **v12; // rbx
  CIMAPIException *v13; // rax
  CIMAPIException *v14; // rax
  CIMAPIException **v15; // rbx
  char v16; // dl
  __int64 v17; // rcx
  CIMAPIException *v18; // rax
  CIMAPIException *v19; // rax
  CIMAPIException **v20; // rbx
  CIMAPIException *v21; // rax
  CIMAPIException *v22; // rax
  CIMAPIException **v23; // rbx
  CIMAPIException **v25; // [rsp+30h] [rbp-1C8h] BYREF
  CIMAPIException **v26; // [rsp+38h] [rbp-1C0h] BYREF
  CIMAPIException **pExceptionObject; // [rsp+40h] [rbp-1B8h] BYREF
  CIMAPIException **v28; // [rsp+48h] [rbp-1B0h] BYREF
  CIMAPIException **v29; // [rsp+50h] [rbp-1A8h] BYREF
  _QWORD v30[2]; // [rsp+58h] [rbp-1A0h] BYREF
  char v31[8]; // [rsp+68h] [rbp-190h] BYREF
  _BYTE v32[88]; // [rsp+70h] [rbp-188h] BYREF
  _BYTE v33[88]; // [rsp+C8h] [rbp-130h] BYREF
  _BYTE v34[88]; // [rsp+120h] [rbp-D8h] BYREF
  _BYTE v35[128]; // [rsp+178h] [rbp-80h] BYREF
  __int64 v36; // [rsp+210h] [rbp+18h] BYREF
  unsigned int v37; // [rsp+218h] [rbp+20h]

  v4 = (CFsiDirectoryItem *)((char *)this - 80);
  v30[1] = (char *)this - 80;
  v5 = *(_DWORD *)(*(_QWORD *)(**((_QWORD **)this + 8) + 64LL) + 20LL);
  v37 = v5;
  MethodTrace::MethodTrace((MethodTrace *)v31, "CFsiDirectoryItem::Remove");
  ImapiClearErrorInfo();
  ImapiComObject::LockCS(v4);
  v6 = ValidateStringPointer(a2, 1u, 0x10000u);
  try
  {
    v7 = v6;
    if ( v6 == -1062555391 || (v7 = ValidateStringPointer(a2, 1u, 0x10000u), v7 == -2147467261) )
    {
      v21 = (CIMAPIException *)operator new(0x58u);
      v25 = (CIMAPIException **)v21;
      if ( v21 )
        v22 = CIMAPIException::CIMAPIException(v21, v7, L"path");
      else
        v22 = 0;
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v25, v22);
      v23 = v25;
      if ( v25 && *v25 )
      {
        CIMAPIException::SetCodeRefInfo(*v25, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 749);
        v30[0] = v23;
        if ( v23 )
          ++*((_DWORD *)v23 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)v30;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v35,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v35;
    }
    if ( (int)ValidateStringPointer(a2, 1u, 0x10000u) >= 0 )
    {
      v8 = **((_QWORD **)this + 8);
      if ( !*(_QWORD *)(v8 + 72) )
      {
        v9 = (CIMAPIException *)operator new(0x58u);
        v25 = (CIMAPIException **)v9;
        if ( v9 )
        {
          FullPathOriginal = ImapiFsObjectBase::GetFullPathOriginal(**((ImapiFsObjectBase ***)this + 8));
          v11 = CIMAPIException::CIMAPIException(v9, -1062555381, *(_QWORD *)FullPathOriginal);
        }
        else
        {
          v11 = 0;
        }
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v25, v11);
        v12 = v25;
        if ( v25 && *v25 )
        {
          CIMAPIException::SetCodeRefInfo(*v25, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 753);
          pExceptionObject = v12;
          if ( v12 )
            ++*((_DWORD *)v12 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v32,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v32;
      }
      if ( *(int *)(*(_QWORD *)(v8 + 64) + 8LL) > 0 )
      {
        v13 = (CIMAPIException *)operator new(0x58u);
        v25 = (CIMAPIException **)v13;
        if ( v13 )
          v14 = CIMAPIException::CIMAPIException(v13, -1062555390);
        else
          v14 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v25, v14);
        v15 = v25;
        if ( v25 && *v25 )
        {
          CIMAPIException::SetCodeRefInfo(*v25, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 757);
          v28 = v15;
          if ( v15 )
            ++*((_DWORD *)v15 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v28;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v33,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v33;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v36,
        a2);
      ImapiDirectoryInfo::GetFileDirRecord(**((_QWORD **)this + 8), &v26, &v36);
      if ( !v26 || !*v26 )
      {
        v18 = (CIMAPIException *)operator new(0x58u);
        v25 = (CIMAPIException **)v18;
        if ( v18 )
          v19 = CIMAPIException::CIMAPIException(v18, -1062555368, v36);
        else
          v19 = 0;
        SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v25, v19);
        v20 = v25;
        if ( v25 && *v25 )
        {
          CIMAPIException::SetCodeRefInfo(*v25, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiitem.cpp", 763);
          v29 = v20;
          if ( v20 )
            ++*((_DWORD *)v20 + 2);
          throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&v29;
        }
        CIMAPIException::CIMAPIException(
          (CIMAPIException *)v34,
          (const struct CIMAPIException *)&CIMAPIException::badAlloc);
        throw (CIMAPIException *)v34;
      }
      if ( !*((_DWORD *)*v26 + 14) || (v16 = 0, *((_DWORD *)*v26 + 14) == 3) )
        v16 = 1;
      v17 = **((_QWORD **)this + 8);
      v25 = v26;
      ++*((_DWORD *)v26 + 2);
      if ( v16 )
        ImapiDirectoryInfo::RemoveDirectoryItem(v17, &v25, 0);
      else
        ImapiDirectoryInfo::RemoveFileItem(v17, &v25);
      SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(&v26);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v36);
    }
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_FsiDirectoryItem);
  }
  if ( v7 < 0 )
    FileSystemImage::RollbackRecover(*(FileSystemImage **)(**((_QWORD **)this + 8) + 64LL), v5, 1);
  ImapiComObject::UnlockCS(v4);
  MethodTrace::~MethodTrace((MethodTrace *)v31);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000eac0  mov     [rsp+arg_8], rbx
0x18000eac5  mov     [rsp+arg_0], rcx
0x18000eaca  push    rdi
0x18000eacb  push    r12
0x18000eacd  push    r13
0x18000eacf  push    r14
0x18000ead1  push    r15
0x18000ead3  sub     rsp, 1D0h
0x18000eada  mov     r15, rdx
0x18000eadd  mov     r14, rcx
0x18000eae0  lea     r13, [rcx-50h]
0x18000eae4  mov     [rsp+1F8h+var_198], r13
0x18000eae9  mov     rax, [r13+90h]
0x18000eaf0  mov     r8, [rax]
0x18000eaf3  mov     rax, [r8+40h]
0x18000eaf7  mov     r12d, [rax+14h]
0x18000eafb  mov     [rsp+1F8h+arg_18], r12d
0x18000eb03  lea     rdx, aCfsidirectoryi_8; "CFsiDirectoryItem::Remove"
0x18000eb0a  lea     rcx, [rsp+1F8h+var_190]; this
0x18000eb0f  call    ??0MethodTrace@@QEAA@PEBD@Z; MethodTrace::MethodTrace(char const *)
0x18000eb14  nop
0x18000eb15  call    ?ImapiClearErrorInfo@@YAXXZ; ImapiClearErrorInfo(void)
0x18000eb1a  nop
0x18000eb1b  mov     rcx, r13; this
0x18000eb1e  call    ?LockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::LockCS(void)
0x18000eb23  mov     edi, 10000h
0x18000eb28  mov     r8d, edi; unsigned __int64
0x18000eb2b  mov     edx, 1; unsigned __int64
0x18000eb30  mov     rcx, r15; pbstr
0x18000eb33  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18000eb38  mov     ebx, eax
0x18000eb3a  cmp     eax, 0C0AAB101h
0x18000eb3f  jz      loc_18000EE31
0x18000eb45  mov     r8d, edi; unsigned __int64
0x18000eb48  mov     edx, 1; unsigned __int64
0x18000eb4d  mov     rcx, r15; pbstr
0x18000eb50  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18000eb55  mov     ebx, eax
0x18000eb57  cmp     eax, 80004003h
0x18000eb5c  jz      loc_18000EE31
0x18000eb62  mov     r8d, edi; unsigned __int64
0x18000eb65  mov     edx, 1; unsigned __int64
0x18000eb6a  mov     rcx, r15; pbstr
0x18000eb6d  call    ?ValidateStringPointer@@YAJPEAG_K1@Z; ValidateStringPointer(ushort *,unsigned __int64,unsigned __int64)
0x18000eb72  xor     edi, edi
0x18000eb74  test    eax, eax
0x18000eb76  jns     short loc_18000EB7D
0x18000eb78  jmp     loc_18000EEF2
0x18000eb7d  mov     rax, [r14+40h]
0x18000eb81  mov     rax, [rax]
0x18000eb84  cmp     [rax+48h], rdi
0x18000eb88  jnz     loc_18000EC39
0x18000eb8e  mov     ecx, 58h ; 'X'; unsigned __int64
0x18000eb93  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000eb98  mov     rbx, rax
0x18000eb9b  mov     [rsp+1F8h+var_1C8], rax
0x18000eba0  test    rax, rax
0x18000eba3  jz      short loc_18000EBC3
0x18000eba5  mov     rcx, [r14+40h]
0x18000eba9  mov     rcx, [rcx]; this
0x18000ebac  call    ?GetFullPathOriginal@ImapiFsObjectBase@@QEAAAEBVCComBSTR@ATL@@XZ; ImapiFsObjectBase::GetFullPathOriginal(void)
0x18000ebb1  mov     r8, [rax]
0x18000ebb4  mov     edx, 0C0AAB10Bh; int
0x18000ebb9  mov     rcx, rbx; this
0x18000ebbc  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18000ebc1  jmp     short loc_18000EBC6
0x18000ebc3  mov     rax, rdi
0x18000ebc6  mov     rdx, rax
0x18000ebc9  lea     rcx, [rsp+1F8h+var_1C8]
0x18000ebce  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18000ebd3  nop
0x18000ebd4  mov     rbx, [rsp+1F8h+var_1C8]
0x18000ebd9  test    rbx, rbx
0x18000ebdc  jz      short loc_18000EC16
0x18000ebde  cmp     [rbx], rdi
0x18000ebe1  jz      short loc_18000EC16
0x18000ebe3  mov     r8d, 2F1h; int
0x18000ebe9  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18000ebf0  mov     rcx, [rbx]; this
0x18000ebf3  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18000ebf8  mov     [rsp+1F8h+pExceptionObject], rbx
0x18000ebfd  test    rbx, rbx
0x18000ec00  jz      short loc_18000EC05
0x18000ec02  inc     dword ptr [rbx+8]
0x18000ec05  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18000ec0c  lea     rcx, [rsp+1F8h+pExceptionObject]; pExceptionObject
0x18000ec11  call    _CxxThrowException_0
0x18000ec16  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18000ec1d  lea     rcx, [rsp+1F8h+var_188]; this
0x18000ec22  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18000ec27  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18000ec2e  lea     rcx, [rsp+1F8h+var_188]; pExceptionObject
0x18000ec33  call    _CxxThrowException_0
0x18000ec39  mov     rax, [rax+40h]
0x18000ec3d  cmp     [rax+8], edi
0x18000ec40  jle     loc_18000ECE5
0x18000ec46  mov     ecx, 58h ; 'X'; unsigned __int64
0x18000ec4b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ec50  mov     [rsp+1F8h+var_1C8], rax
0x18000ec55  test    rax, rax
0x18000ec58  jz      short loc_18000EC69
0x18000ec5a  mov     edx, 0C0AAB102h; int
0x18000ec5f  mov     rcx, rax; this
0x18000ec62  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18000ec67  jmp     short loc_18000EC6C
0x18000ec69  mov     rax, rdi
0x18000ec6c  mov     rdx, rax
0x18000ec6f  lea     rcx, [rsp+1F8h+var_1C8]
0x18000ec74  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18000ec79  nop
0x18000ec7a  mov     rbx, [rsp+1F8h+var_1C8]
0x18000ec7f  test    rbx, rbx
0x18000ec82  jz      short loc_18000ECBC
0x18000ec84  cmp     [rbx], rdi
0x18000ec87  jz      short loc_18000ECBC
0x18000ec89  mov     r8d, 2F5h; int
0x18000ec8f  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18000ec96  mov     rcx, [rbx]; this
0x18000ec99  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18000ec9e  mov     [rsp+1F8h+var_1B0], rbx
0x18000eca3  test    rbx, rbx
0x18000eca6  jz      short loc_18000ECAB
0x18000eca8  inc     dword ptr [rbx+8]
0x18000ecab  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18000ecb2  lea     rcx, [rsp+1F8h+var_1B0]; pExceptionObject
0x18000ecb7  call    _CxxThrowException_0
0x18000ecbc  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18000ecc3  lea     rcx, [rsp+1F8h+var_130]; this
0x18000eccb  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18000ecd0  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18000ecd7  lea     rcx, [rsp+1F8h+var_130]; pExceptionObject
0x18000ecdf  call    _CxxThrowException_0
0x18000ece5  mov     rdx, r15
0x18000ece8  lea     rcx, [rsp+1F8h+arg_10]
0x18000ecf0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000ecf5  nop
0x18000ecf6  mov     rcx, [r14+40h]
0x18000ecfa  lea     r8, [rsp+1F8h+arg_10]
0x18000ed02  lea     rdx, [rsp+1F8h+var_1C0]
0x18000ed07  mov     rcx, [rcx]
0x18000ed0a  call    ?GetFileDirRecord@ImapiDirectoryInfo@@QEAA?AV?$SmartClassPtr@VImapiFsObjectBase@@VImapiImplementation@@@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N1@Z; ImapiDirectoryInfo::GetFileDirRecord(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,bool,bool)
0x18000ed0f  nop
0x18000ed10  mov     rax, [rsp+1F8h+var_1C0]
0x18000ed15  test    rax, rax
0x18000ed18  jz      short loc_18000ED8A
0x18000ed1a  cmp     [rax], rdi
0x18000ed1d  jz      short loc_18000ED8A
0x18000ed1f  mov     rcx, [rax]
0x18000ed22  cmp     [rcx+38h], edi
0x18000ed25  jz      short loc_18000ED30
0x18000ed27  cmp     dword ptr [rcx+38h], 3
0x18000ed2b  mov     dl, dil
0x18000ed2e  jnz     short loc_18000ED32
0x18000ed30  mov     dl, 1
0x18000ed32  mov     rcx, [r14+40h]
0x18000ed36  mov     rcx, [rcx]
0x18000ed39  mov     [rsp+1F8h+var_1C8], rax
0x18000ed3e  test    dl, dl
0x18000ed40  jz      short loc_18000ED59
0x18000ed42  test    rax, rax
0x18000ed45  jz      short loc_18000ED4A
0x18000ed47  inc     dword ptr [rax+8]
0x18000ed4a  xor     r8d, r8d
0x18000ed4d  lea     rdx, [rsp+1F8h+var_1C8]
0x18000ed52  call    ?RemoveDirectoryItem@ImapiDirectoryInfo@@QEAAXV?$SmartClassPtr@VImapiDirectoryInfo@@VImapiImplementation@@@@_N@Z; ImapiDirectoryInfo::RemoveDirectoryItem(SmartClassPtr<ImapiDirectoryInfo,ImapiImplementation>,bool)
0x18000ed57  jmp     short loc_18000ED6C
0x18000ed59  test    rax, rax
0x18000ed5c  jz      short loc_18000ED61
0x18000ed5e  inc     dword ptr [rax+8]
0x18000ed61  lea     rdx, [rsp+1F8h+var_1C8]
0x18000ed66  call    ?RemoveFileItem@ImapiDirectoryInfo@@QEAAXV?$SmartClassPtr@VImapiFileInfo@@VImapiImplementation@@@@@Z; ImapiDirectoryInfo::RemoveFileItem(SmartClassPtr<ImapiFileInfo,ImapiImplementation>)
0x18000ed6b  nop
0x18000ed6c  lea     rcx, [rsp+1F8h+var_1C0]; void *
0x18000ed71  call    ??1?$SmartPtr@VVolumeRecognitionStructureBase@@@@QEAA@XZ; SmartPtr<VolumeRecognitionStructureBase>::~SmartPtr<VolumeRecognitionStructureBase>(void)
0x18000ed76  nop
0x18000ed77  lea     rcx, [rsp+1F8h+arg_10]; void *
0x18000ed7f  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000ed84  nop
0x18000ed85  jmp     loc_18000EEF2
0x18000ed8a  mov     ecx, 58h ; 'X'; unsigned __int64
0x18000ed8f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ed94  mov     [rsp+1F8h+var_1C8], rax
0x18000ed99  test    rax, rax
0x18000ed9c  jz      short loc_18000EDB5
0x18000ed9e  mov     r8, [rsp+1F8h+arg_10]
0x18000eda6  mov     edx, 0C0AAB118h; int
0x18000edab  mov     rcx, rax; this
0x18000edae  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18000edb3  jmp     short loc_18000EDB8
0x18000edb5  mov     rax, rdi
0x18000edb8  mov     rdx, rax
0x18000edbb  lea     rcx, [rsp+1F8h+var_1C8]
0x18000edc0  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18000edc5  nop
0x18000edc6  mov     rbx, [rsp+1F8h+var_1C8]
0x18000edcb  test    rbx, rbx
0x18000edce  jz      short loc_18000EE08
0x18000edd0  cmp     [rbx], rdi
0x18000edd3  jz      short loc_18000EE08
0x18000edd5  mov     r8d, 2FBh; int
0x18000eddb  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18000ede2  mov     rcx, [rbx]; this
0x18000ede5  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18000edea  mov     [rsp+1F8h+var_1A8], rbx
0x18000edef  test    rbx, rbx
0x18000edf2  jz      short loc_18000EDF7
0x18000edf4  inc     dword ptr [rbx+8]
0x18000edf7  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18000edfe  lea     rcx, [rsp+1F8h+var_1A8]; pExceptionObject
0x18000ee03  call    _CxxThrowException_0
0x18000ee08  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18000ee0f  lea     rcx, [rsp+1F8h+var_D8]; this
0x18000ee17  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18000ee1c  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18000ee23  lea     rcx, [rsp+1F8h+var_D8]; pExceptionObject
0x18000ee2b  call    _CxxThrowException_0
0x18000ee31  mov     ecx, 58h ; 'X'; unsigned __int64
0x18000ee36  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ee3b  mov     [rsp+1F8h+var_1C8], rax
0x18000ee40  xor     edi, edi
0x18000ee42  test    rax, rax
0x18000ee45  jz      short loc_18000EE5A
0x18000ee47  lea     r8, aPath; "path"
0x18000ee4e  mov     edx, ebx; int
0x18000ee50  mov     rcx, rax; this
0x18000ee53  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18000ee58  jmp     short loc_18000EE5D
0x18000ee5a  mov     rax, rdi
0x18000ee5d  mov     rdx, rax
0x18000ee60  lea     rcx, [rsp+1F8h+var_1C8]
0x18000ee65  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18000ee6a  nop
0x18000ee6b  mov     rbx, [rsp+1F8h+var_1C8]
0x18000ee70  test    rbx, rbx
0x18000ee73  jz      short loc_18000EEAD
0x18000ee75  cmp     [rbx], rdi
0x18000ee78  jz      short loc_18000EEAD
0x18000ee7a  mov     r8d, 2EDh; int
0x18000ee80  lea     rdx, aDriversStorage_1; "drivers\\storage\\imapi2\\filesystemima"...
0x18000ee87  mov     rcx, [rbx]; this
0x18000ee8a  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18000ee8f  mov     [rsp+1F8h+var_1A0], rbx
0x18000ee94  test    rbx, rbx
0x18000ee97  jz      short loc_18000EE9C
0x18000ee99  inc     dword ptr [rbx+8]
0x18000ee9c  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18000eea3  lea     rcx, [rsp+1F8h+var_1A0]; pExceptionObject
0x18000eea8  call    _CxxThrowException_0
0x18000eead  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18000eeb4  lea     rcx, [rsp+1F8h+var_80]; this
0x18000eebc  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18000eec1  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18000eec8  lea     rcx, [rsp+1F8h+var_80]; pExceptionObject
0x18000eed0  call    _CxxThrowException_0
0x18000eed6  mov     r14, [rsp+1F8h+arg_0]
0x18000eede  mov     ebx, dword ptr [rsp+1F8h+arg_10]
0x18000eee5  mov     r13, [rsp+1F8h+var_198]
0x18000eeea  mov     r12d, [rsp+1F8h+arg_18]
0x18000eef2  test    ebx, ebx
0x18000eef4  jns     short loc_18000EF0C
0x18000eef6  mov     rax, [r14+40h]
0x18000eefa  mov     rcx, [rax]
0x18000eefd  mov     r8b, 1; bool
0x18000ef00  mov     edx, r12d; unsigned int
0x18000ef03  mov     rcx, [rcx+40h]; this
0x18000ef07  call    ?RollbackRecover@FileSystemImage@@AEAAXK_N@Z; FileSystemImage::RollbackRecover(ulong,bool)
0x18000ef0c  mov     rcx, r13; this
0x18000ef0f  call    ?UnlockCS@ImapiComObject@@IEAAXXZ; ImapiComObject::UnlockCS(void)
0x18000ef14  nop
0x18000ef15  lea     rcx, [rsp+1F8h+var_190]; this
0x18000ef1a  call    ??1MethodTrace@@QEAA@XZ; MethodTrace::~MethodTrace(void)
0x18000ef1f  mov     eax, ebx
0x18000ef21  mov     rbx, [rsp+1F8h+arg_8]
0x18000ef29  add     rsp, 1D0h
0x18000ef30  pop     r15
0x18000ef32  pop     r14
0x18000ef34  pop     r13
0x18000ef36  pop     r12
0x18000ef38  pop     rdi
0x18000ef39  retn
```
